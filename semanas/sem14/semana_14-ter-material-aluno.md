# Semana 14 — Terça-feira

## Orquestrando serviços com Docker Compose

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **16/06/2026 | E132 | 17:00–18:40**

---

## Leitura Prévia

Não há leitura prévia. Revise mentalmente o que vimos ontem: imagem, container, Dockerfile, ciclo de vida básico. Hoje construímos em cima disso.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar o problema que Docker Compose resolve em relação ao Docker isolado
- Ler e interpretar um arquivo `docker-compose.yml` com múltiplos serviços
- Entender como serviços se comunicam dentro de uma rede Compose
- Identificar o papel de volumes e variáveis de ambiente numa orquestração real

---

## 1. O problema do Docker isolado

Ontem vimos como containerizar um serviço. Mas o PetFood não é um serviço — é três:

```
┌─────────────────────────────────────────────────────────┐
│                    Sistema PetFood                       │
│                                                         │
│  ┌──────────────┐   ┌──────────────┐   ┌─────────────┐ │
│  │   Frontend   │──▶│   Backend    │──▶│    Banco    │ │
│  │    React     │   │   Express    │   │  PostgreSQL │ │
│  │   (nginx)    │   │  Node.js     │   │             │ │
│  └──────────────┘   └──────────────┘   └─────────────┘ │
└─────────────────────────────────────────────────────────┘
```

Para rodar isso com Docker puro, você precisaria de três `docker run` separados, configurar manualmente uma rede para que os containers se comuniquem, e lembrar de todos os parâmetros a cada vez. Qualquer membro novo do time teria que aprender exatamente essa sequência.

**Docker Compose resolve isso:** você descreve todos os serviços, suas relações e configurações num único arquivo `docker-compose.yml`, e sobe tudo com um único comando:

```bash
docker compose up
```

---

## 2. Anatomia do docker-compose.yml

O arquivo `docker-compose.yml` é escrito em YAML e organizado em **serviços** (_services_). Cada serviço é um container. Você também pode definir **volumes** (persistência de dados) e **redes** (comunicação entre serviços).

**Estrutura básica:**

```yaml
services:        # obrigatório — define os containers
  nome-servico:
    image: ...   # imagem pronta do Docker Hub
    build: ...   # ou: construir a partir de um Dockerfile local
    ports: ...   # mapeamento de portas host:container
    environment: # variáveis de ambiente
    depends_on:  # ordem de inicialização
    volumes:     # montagem de volumes

volumes:         # opcional — define volumes nomeados
  nome-volume:

networks:        # opcional — Docker Compose cria uma rede padrão automaticamente
```

---

## 3. docker-compose.yml do PetFood — completo e comentado

```yaml
# docker-compose.yml — Sistema PetFood
# Orquestra: frontend (React/nginx), backend (Express), banco (PostgreSQL)

services:

  # ── Serviço 1: banco de dados ───────────────────────────────────────────────
  db:
    # Usamos a imagem oficial do PostgreSQL versão 15
    # Não precisamos de Dockerfile para o banco — a imagem oficial é suficiente
    image: postgres:15-alpine

    # Variáveis de ambiente que o PostgreSQL usa na inicialização
    # Em produção real, use um arquivo .env ou um secrets manager
    environment:
      POSTGRES_DB: petfood
      POSTGRES_USER: petfood_user
      POSTGRES_PASSWORD: petfood_pass

    # Volume nomeado para persistir os dados entre reinicializações
    # Sem isso, os dados são perdidos quando o container é removido
    volumes:
      - db_data:/var/lib/postgresql/data

    # Expõe a porta do banco apenas internamente (sem publicar no host)
    # O backend se conecta via rede interna do Compose
    expose:
      - "5432"

  # ── Serviço 2: backend ──────────────────────────────────────────────────────
  backend:
    # Constrói a imagem a partir do Dockerfile no diretório ./backend
    build: ./backend

    # Publica a porta 3000 do container na porta 3000 do host
    ports:
      - "3000:3000"

    # Variáveis de ambiente passadas para a aplicação Node.js
    environment:
      NODE_ENV: production
      # Dentro da rede Compose, "db" é o hostname do serviço de banco
      # (o nome do serviço vira DNS automático)
      DATABASE_URL: postgresql://petfood_user:petfood_pass@db:5432/petfood
      PORT: 3000

    # O backend só inicia depois que o container do banco estiver de pé
    # Atenção: depends_on garante ordem de START, não de READINESS
    # O banco pode ainda estar inicializando quando o backend tentar conectar
    depends_on:
      - db

  # ── Serviço 3: frontend ─────────────────────────────────────────────────────
  frontend:
    # Constrói a partir do Dockerfile no diretório ./frontend
    # (o multi-stage build que vimos ontem)
    build: ./frontend

    # Publica a porta 80 do nginx na porta 8080 do host
    # Acesse o sistema em http://localhost:8080
    ports:
      - "8080:80"

    # O frontend só inicia depois do backend
    depends_on:
      - backend

# ── Volumes nomeados ───────────────────────────────────────────────────────────
# Volumes nomeados são gerenciados pelo Docker e persistem entre `docker compose down`
# Use `docker compose down -v` se quiser remover os dados também
volumes:
  db_data:
```

---

## 4. Como os serviços se comunicam

Dentro de uma rede Docker Compose, **cada serviço é acessível pelo seu próprio nome**. O Compose configura isso automaticamente — você não precisa saber endereços IP.

No exemplo acima:

- O backend se conecta ao banco usando o hostname `db` (não `localhost`, não um IP)
- O frontend acessa o backend usando `http://backend:3000` (dentro da rede interna)

```
Host (seu computador)
│
├── localhost:8080 ──▶ frontend (container)
│                          │
│                          └──▶ backend:3000 (via rede interna)
│                                    │
└── localhost:3000 ──▶ backend       └──▶ db:5432 (via rede interna)
```

**Por que isso importa?** Suas variáveis de ambiente de conexão mudam dependendo de onde o código está rodando. Em desenvolvimento local sem Docker, você usa `localhost`. Dentro do Compose, você usa o nome do serviço. Quem configura o ambiente configura a string de conexão.

---

## 5. Comandos essenciais do Docker Compose

```bash
# Subir todos os serviços em background (-d = detached)
docker compose up -d

# Ver os logs de todos os serviços (acompanhar em tempo real com -f)
docker compose logs -f

# Ver logs de um serviço específico
docker compose logs -f backend

# Ver o status de todos os serviços
docker compose ps

# Parar todos os serviços (mantém containers e volumes)
docker compose stop

# Parar E remover containers e rede (mantém volumes)
docker compose down

# Parar, remover containers, rede E volumes (apaga dados do banco!)
docker compose down -v

# Reconstruir imagens antes de subir (após mudança no Dockerfile)
docker compose up -d --build
```

**Anote aqui** — qual é a diferença entre `docker compose stop` e `docker compose down`?

```
Sua resposta:


```

---

## 6. Variáveis de ambiente e o arquivo .env

Colocar senhas diretamente no `docker-compose.yml` funciona, mas não é uma boa prática — você não quer commitar credenciais no repositório. A convenção é usar um arquivo `.env` na raiz do projeto:

```bash
# .env (nunca commite este arquivo — adicione ao .gitignore)
POSTGRES_DB=petfood
POSTGRES_USER=petfood_user
POSTGRES_PASSWORD=petfood_pass
DATABASE_URL=postgresql://petfood_user:petfood_pass@db:5432/petfood
```

E referenciar no `docker-compose.yml` com a sintaxe `${VARIAVEL}`:

```yaml
environment:
  POSTGRES_DB: ${POSTGRES_DB}
  POSTGRES_USER: ${POSTGRES_USER}
  POSTGRES_PASSWORD: ${POSTGRES_PASSWORD}
```

O Docker Compose carrega automaticamente o `.env` do diretório atual. O `.env` vai no `.gitignore` e no `.dockerignore`. Você distribui um `.env.example` com as variáveis necessárias mas sem os valores reais.

---

## 7. Docker Compose e as plataformas de deploy

Você pode estar pensando: "uso Vercel e Railway, o que Docker Compose tem a ver com isso?"

A resposta é: **Railway e similares aceitam containers como unidade de deploy**. Quando você conecta um repositório ao Railway, a plataforma detecta o `Dockerfile` (ou o `docker-compose.yml`) e constrói a imagem por conta própria.

O `docker-compose.yml` que você escreve para desenvolvimento local é também a base de entendimento para o que acontece em produção — mesmo que a plataforma abstraia a execução. Saber o que está dentro da caixa torna você capaz de depurar quando algo dá errado no deploy, configurar corretamente as variáveis de ambiente da plataforma, e entender os logs de erro que aparecem.

---

## 8. Tabela de referência rápida

|Cenário|Comando|
|---|---|
|Subir o ambiente pela primeira vez|`docker compose up -d --build`|
|Acompanhar o que está acontecendo|`docker compose logs -f`|
|Checar se os serviços subiram|`docker compose ps`|
|Parar sem perder dados|`docker compose stop`|
|Destruir tudo e recomeçar|`docker compose down -v`|
|Reconstruir após mudança no código|`docker compose up -d --build`|

---

## 9. Questão estruturante para reflexão

> _"Se o docker-compose.yml é o 'manual de montagem' do ambiente de desenvolvimento, o que ele diz sobre a responsabilidade de documentação de um engenheiro de software? Qual é a relação disso com o README que você escreveu para o seu projeto?"_

```
Sua resposta:


```

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
