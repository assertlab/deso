# Semana 14 — Segunda-feira

## Do código ao container: introdução ao Docker

**CIN0136: Desenvolvimento de Software | CIn-UFPE |** **E132 | 18:50–20:30**

---

## Leitura Prévia

Não há leitura prévia obrigatória. Venha com o repositório do seu projeto acessível — vamos usá-lo como referência durante a aula.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar o problema que Docker resolve e por que ele é relevante na prática profissional
- Descrever o que um container é por dentro: um processo isolado que compartilha o kernel do host
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

Mesmo quando você não escreve um Dockerfile, as plataformas de deploy empacotam e isolam sua aplicação de forma parecida: Railway e Render constroem uma imagem a partir do seu repositório; a Vercel usa outro modelo (funções serverless e arquivos estáticos em CDN), mas o princípio de "empacotar o ambiente junto com o código" é o mesmo. Entender o que acontece nos bastidores torna você um profissional mais capaz.

---

## 2. Conceitos fundamentais

### O que é um container, afinal?

Um container **não é uma máquina virtual**. É um processo comum do sistema operacional, rodando com isolamento:

- **Namespaces** limitam o que o processo _vê_: seu próprio sistema de arquivos, sua rede, sua lista de processos, seus usuários.
- **cgroups** limitam quanto ele _usa_: CPU, memória, I/O.
- **Capabilities** e filtros de chamadas de sistema restringem o que ele pode _fazer_.

Todos os containers de uma máquina **compartilham o kernel do host**. Não há um sistema operacional convidado inteiro, como numa VM — por isso um container sobe em segundos e ocupa pouco.

> No Windows e no macOS, o Docker Desktop roda uma pequena VM Linux para fornecer esse kernel. É por isso que você vê uma "VM" mesmo usando containers.

### Imagem vs. Container

A distinção mais importante para começar:

|Conceito|Analogia|O que é na prática|
|---|---|---|
|**Imagem**|Receita de bolo|Um pacote imutável com o sistema de arquivos, dependências e instruções de inicialização. Existe até ser removida com `docker rmi`|
|**Container**|O bolo assado|Uma instância em execução de uma imagem — tem processo, tem memória, tem estado. Quando o processo termina, o container fica **parado** (não some) até ser removido com `docker rm`|

Uma mesma imagem pode gerar múltiplos containers rodando simultaneamente. Parar ou remover um container não destrói a imagem.

### O que é um Dockerfile?

Um `Dockerfile` é o arquivo de texto que define como construir uma imagem. É uma sequência de instruções: parte de uma imagem base, copia arquivos, instala dependências, define o comando de inicialização. Cada instrução gera uma **camada**, e o Docker guarda as camadas em cache para acelerar os próximos builds.

**Principais instruções:**

|Instrução|O que faz|
|---|---|
|`FROM`|Define a imagem base (ponto de partida)|
|`WORKDIR`|Define o diretório de trabalho dentro do container|
|`COPY`|Copia arquivos do host para o container|
|`RUN`|Executa um comando durante a construção da imagem|
|`EXPOSE`|Declara a porta que o container vai usar — **só documenta, não publica** (quem publica é o `-p` do `docker run`)|
|`CMD`|Define o comando padrão ao iniciar o container|

---

## 3. Dockerfile do PetFood — backend (Node.js/Express)

O sistema PetFood tem um backend em Node.js com Express. Veja como containerizá-lo:

```dockerfile
# ── Etapa 1: imagem base ──────────────────────────────────────────────────────
# Partimos da imagem oficial do Node.js 24 (versão LTS ativa), variante "alpine"
# Alpine é uma distribuição Linux mínima: a imagem node:24-alpine é muito menor
# que a node:24 (baseada em Debian)
FROM node:24-alpine

# ── Etapa 2: diretório de trabalho ───────────────────────────────────────────
# Todos os comandos seguintes serão executados a partir deste diretório
# Se não existir, o Docker cria automaticamente
WORKDIR /app

# ── Etapa 3: dependências ─────────────────────────────────────────────────────
# Copiamos APENAS os arquivos de manifesto primeiro (package.json e package-lock.json)
# Isso aproveita o cache de camadas do Docker: se as dependências não mudaram,
# o Docker não reinstala tudo a cada build
COPY package*.json ./

# Instala as dependências de produção (sem devDependencies), exatamente
# nas versões do package-lock.json
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

> **Por que Node 24?** O Node.js 20 chegou ao fim de vida (EOL) em abril de 2026 e não recebe mais correções de segurança. A versão que você escolhe no `FROM` também é uma decisão de engenharia — e uma versão sem suporte é dívida técnica.

> **Alpine nem sempre serve.** O Alpine usa a biblioteca C `musl` em vez da `glibc`. Dependências com código nativo (por exemplo `bcrypt`, `sharp`, Prisma) podem falhar nele. Nesse caso, use `node:24-slim`: baseada em Debian, mas enxuta.

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
FROM node:24-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm ci

# Copiamos o código-fonte do React
COPY . .

# O Vite embute as variáveis VITE_* no código durante o build.
# /api é um caminho relativo: o navegador chama o próprio nginx, que repassa ao backend
ARG VITE_API_URL=/api

# Gera os arquivos estáticos otimizados em /app/dist
RUN npm run build

# ── Stage 2: produção ─────────────────────────────────────────────────────────
# Usamos nginx para servir os arquivos estáticos — muito mais leve que Node
# O Docker descarta completamente o Stage 1 após o build
FROM nginx:alpine

# Nossa configuração do nginx (ver seção 5)
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copiamos APENAS os arquivos compilados do Stage 1
# Nada do Node, npm ou código-fonte vai para a imagem final
COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

# nginx já tem um CMD padrão — não precisamos redefinir
```

**A vantagem do multi-stage build:**

- A imagem final contém apenas nginx, sua configuração e os arquivos estáticos
- Todo o Node.js, npm e código-fonte ficam de fora
- Resultado: imagem de produção muito menor e mais segura — confira o tamanho real com `docker images`

---

## 5. O nginx.conf do frontend

O nginx padrão só serve arquivos. Para uma aplicação React precisamos de duas coisas a mais, descritas num `nginx.conf` na pasta do frontend:

```nginx
server {
  listen 80;
  root /usr/share/nginx/html;

  # SPA: rotas do React Router (ex.: /produtos/42) caem no index.html.
  # Sem isso, recarregar a página numa rota interna dá 404.
  location / {
    try_files $uri $uri/ /index.html;
  }

  # Chamadas à API vão para o serviço "backend"
  location /api/ {
    proxy_pass http://backend:3000;
  }
}
```

> ⚠️ O nome `backend` só existe dentro da rede do **Docker Compose**, que veremos amanhã. Se você rodar o container do frontend sozinho com `docker run`, o nginx não encontra esse host e não sobe. Hoje, na prática, vamos rodar apenas o backend.

---

## 6. Comandos essenciais do ciclo de vida

```bash
# Construir uma imagem a partir do Dockerfile no diretório atual
# -t dá um nome e uma tag para a imagem (nome:tag)
docker build -t petfood-backend:1.0 .

# Listar imagens disponíveis localmente (repare na coluna SIZE)
docker images

# Rodar um container a partir de uma imagem
# -d roda em background (detached)
# --name dá um nome ao container (mais fácil que o ID)
# -p mapeia porta-do-host:porta-do-container
docker run -d --name backend -p 3000:3000 petfood-backend:1.0

# Listar containers em execução (-a inclui os parados)
docker ps

# Ver logs de um container (-f acompanha em tempo real)
docker logs -f backend

# Parar um container (ele continua existindo, parado)
docker stop backend

# Remover um container parado
docker rm backend
```

> **Usa Podman?** Os comandos são os mesmos — basta trocar `docker` por `podman` (`podman build`, `podman run`...). O Podman também aceita um arquivo chamado `Containerfile` no lugar do `Dockerfile`.

**Anote aqui** — o que acontece se você rodar `docker run` duas vezes com a mesma imagem? E se as duas execuções usarem o mesmo `-p 3000:3000`?

```
Sua resposta:


```

---

## 7. O arquivo .dockerignore

Assim como `.gitignore` evita que arquivos desnecessários vão para o repositório, `.dockerignore` evita que eles sejam copiados para a imagem:

```
# .dockerignore — para o backend Node.js
# (comentários ficam em linhas próprias, começando com #;
#  um "#" no fim da linha NÃO é comentário, vira parte do padrão)

# serão instalados dentro do container
node_modules

# segredos não devem estar na imagem
.env

# histórico do git não é necessário
.git

# logs locais
*.log

# será gerado pelo build
dist
```

Sem `.dockerignore`, o `COPY . .` copiaria `node_modules` para dentro do container — o que desperdiça espaço e pode introduzir binários compilados para o sistema operacional errado.

---

## 8. Questão estruturante para reflexão

> _"Você acaba de ver que Docker empacota código + ambiente juntos. Pensando no projeto que você desenvolveu esse semestre: quais problemas de ambiente sua equipe encontrou que um container poderia ter evitado?"_

```
Sua resposta:


```

---

## 9. Para a próxima aula (Terça-feira)

Na terça veremos **Docker Compose** — como subir o backend, o frontend e o banco de dados do PetFood juntos, com um único comando, e como o nome `backend` do `nginx.conf` passa a existir. No fim da aula, veremos também onde o Kubernetes entra nessa história (e quando ele não vale o custo).

Não há leitura prévia.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE_
_Referências: Documentação oficial do Docker (docs.docker.com) — Get Started e Dockerfile reference. | Node.js — calendário de versões (nodejs.org/en/about/previous-releases). | Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 10, seção 10.3.2 (container scanning no pipeline)._
