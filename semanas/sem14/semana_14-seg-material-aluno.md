# Semana 14 — Segunda-feira

## Do código ao container: introdução ao Docker

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **15/06/2026 | E132 | 18:50–20:30**

---

## Leitura Prévia

Não há leitura prévia obrigatória. Venha com o repositório do seu projeto acessível — vamos usá-lo como referência durante a aula.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar o problema que Docker resolve e por que ele é relevante na prática profissional
- Entender a diferença entre imagem e container
- Ler e interpretar um `Dockerfile` simples para uma aplicação Node.js/React
- Identificar os comandos essenciais do ciclo de vida de um container

---

## 1. O problema que Docker resolve

Pense nesta cena: você termina uma feature, testa na sua máquina, tudo funciona. Faz o push. Alguém do time clona o repositório e reclama que não sobe. Ou pior — o deploy vai para o servidor e quebra silenciosamente.

Esse problema tem nome: **"na minha máquina funciona"** (_works on my machine_). Ele existe porque o ambiente onde o software roda é tão importante quanto o código em si. Versão do Node, variáveis de ambiente, configuração do sistema operacional, dependências nativas — qualquer diferença pode mudar o comportamento do sistema.

**Docker resolve isso empacotando o software junto com o ambiente em que ele roda.**

Em vez de distribuir código e torcer para que o ambiente do destinatário seja compatível, você distribui uma **imagem** que já contém tudo: o runtime, as dependências, as configurações. Onde essa imagem rodar, o comportamento será o mesmo.

### Por que isso importa para a vida profissional?

Docker não é uma tecnologia esotérica de infraestrutura. Ele aparece:

- No onboarding de novos desenvolvedores ("rode `docker compose up` e o ambiente sobe")
- Em pipelines de CI/CD que precisam de ambientes reproduzíveis
- Em plataformas como Railway, Render e Google Cloud Run — que recebem containers como unidade de deploy
- Em qualquer empresa que precisa garantir paridade entre desenvolvimento, teste e produção

Mesmo quando você usa Vercel ou Railway e não vê Docker explicitamente, **essas plataformas containerizam sua aplicação por baixo dos panos**. Entender o que acontece nos bastidores torna você um profissional mais capaz.

---

## 2. Conceitos fundamentais

### Imagem vs. Container

A distinção mais importante para começar:

|Conceito|Analogia|O que é na prática|
|---|---|---|
|**Imagem**|Receita de bolo|Um pacote imutável com o sistema de arquivos, dependências e instruções de inicialização|
|**Container**|O bolo assado|Uma instância em execução de uma imagem — tem processo, tem memória, tem estado|

Uma mesma imagem pode gerar múltiplos containers rodando simultaneamente. Parar um container não destrói a imagem.

### O que é um Dockerfile?

Um `Dockerfile` é o arquivo de texto que define como construir uma imagem. É uma sequência de instruções: parte de uma imagem base, copia arquivos, instala dependências, define o comando de inicialização.

**Principais instruções:**

|Instrução|O que faz|
|---|---|
|`FROM`|Define a imagem base (ponto de partida)|
|`WORKDIR`|Define o diretório de trabalho dentro do container|
|`COPY`|Copia arquivos do host para o container|
|`RUN`|Executa um comando durante a construção da imagem|
|`EXPOSE`|Declara a porta que o container vai usar (documentação)|
|`CMD`|Define o comando padrão ao iniciar o container|

---

## 3. Dockerfile do PetFood — backend (Node.js/Express)

O sistema PetFood tem um backend em Node.js com Express. Veja como containerizá-lo:

```dockerfile
# ── Etapa 1: imagem base ──────────────────────────────────────────────────────
# Partimos da imagem oficial do Node.js versão 20 (LTS), variante "alpine"
# Alpine é uma distribuição Linux mínima (~5MB), ideal para containers de produção
FROM node:20-alpine

# ── Etapa 2: diretório de trabalho ───────────────────────────────────────────
# Todos os comandos seguintes serão executados a partir deste diretório
# Se não existir, o Docker cria automaticamente
WORKDIR /app

# ── Etapa 3: dependências ─────────────────────────────────────────────────────
# Copiamos APENAS os arquivos de manifesto primeiro (package.json e package-lock.json)
# Isso aproveita o cache de camadas do Docker: se as dependências não mudaram,
# o Docker não reinstala tudo a cada build
COPY package*.json ./

# Instala as dependências de produção (sem devDependencies)
RUN npm ci --omit=dev

# ── Etapa 4: código-fonte ─────────────────────────────────────────────────────
# Agora copiamos o restante do código
# (separado do passo anterior para aproveitar o cache)
COPY . .

# ── Etapa 5: porta e inicialização ───────────────────────────────────────────
# Declaramos que o container escuta na porta 3000
# EXPOSE é documentação — não publica a porta automaticamente
EXPOSE 3000

# Define o comando que inicia o servidor quando o container sobe
CMD ["node", "src/index.js"]
```

**Anote aqui** — por que copiamos `package*.json` separado do restante do código?

```
Sua resposta:


```

---

## 4. Dockerfile do PetFood — frontend (React)

O frontend React precisa de uma estratégia diferente: o código precisa ser compilado (`npm run build`) antes de ser servido. Usamos um **multi-stage build** para separar o ambiente de build do ambiente de produção:

```dockerfile
# ── Stage 1: build ────────────────────────────────────────────────────────────
# Usamos Node para compilar o React — este stage não vai para produção
FROM node:20-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm ci

# Copiamos o código-fonte do React
COPY . .

# Gera os arquivos estáticos otimizados em /app/dist (ou /app/build)
RUN npm run build

# ── Stage 2: produção ─────────────────────────────────────────────────────────
# Usamos nginx para servir os arquivos estáticos — muito mais leve que Node
# O Docker descarta completamente o Stage 1 após o build
FROM nginx:alpine

# Copiamos APENAS os arquivos compilados do Stage 1
# Nada do Node, npm ou código-fonte vai para a imagem final
COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

# nginx já tem um CMD padrão — não precisamos redefinir
```

**A vantagem do multi-stage build:**

- A imagem final contém apenas nginx + arquivos estáticos
- Todo o Node.js, npm e código-fonte ficam de fora
- Resultado: imagem de produção muito menor e mais segura

---

## 5. Comandos essenciais do ciclo de vida

```bash
# Construir uma imagem a partir do Dockerfile no diretório atual
# -t dá um nome (tag) para a imagem
docker build -t petfood-backend .

# Listar imagens disponíveis localmente
docker images

# Rodar um container a partir de uma imagem
# -p mapeia porta-do-host:porta-do-container
# -d roda em background (detached)
docker run -d -p 3000:3000 petfood-backend

# Listar containers em execução
docker ps

# Ver logs de um container (pelo ID ou nome)
docker logs <container_id>

# Parar um container
docker stop <container_id>

# Remover um container parado
docker rm <container_id>
```

**Anote aqui** — o que acontece se você rodar `docker run` duas vezes com a mesma imagem?

```
Sua resposta:


```

---

## 6. O arquivo .dockerignore

Assim como `.gitignore` evita que arquivos desnecessários vão para o repositório, `.dockerignore` evita que eles sejam copiados para a imagem:

```
# .dockerignore — para o backend Node.js
node_modules        # não copie: serão instalados dentro do container
.env                # não copie: segredos não devem estar na imagem
.git                # não copie: histórico do git não é necessário
*.log               # não copie: logs locais
dist                # não copie: será gerado pelo build
```

Sem `.dockerignore`, o `COPY . .` copiaria `node_modules` para dentro do container — o que desperdiça espaço e pode introduzir binários compilados para o sistema operacional errado.

---

## 7. Questão estruturante para reflexão

> _"Você acaba de ver que Docker empacota código + ambiente juntos. Pensando no projeto que você desenvolveu esse semestre: quais problemas de ambiente sua equipe encontrou que um container poderia ter evitado?"_

```
Sua resposta:


```

---

## 8. Para a próxima aula (Terça-feira)

Na terça veremos **Docker Compose** — como orquestrar o backend, o frontend e o banco de dados do PetFood juntos, com um único comando. Traga o Dockerfile desta aula em mente; vamos usá-lo como ponto de partida.

Não há leitura prévia.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
