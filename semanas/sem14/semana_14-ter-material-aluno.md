# Semana 14 — Terça-feira

## Orquestrando serviços com Docker Compose

**CIN0136: Desenvolvimento de Software | CIn-UFPE |** **E132 | 17:00–18:40**

---

## Leitura Prévia

Não há leitura prévia. Revise mentalmente o que vimos ontem: imagem, container, Dockerfile, ciclo de vida básico — e o `nginx.conf` do frontend, que apontava para um tal de `backend`. Hoje construímos em cima disso.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar o problema que Docker Compose resolve em relação ao Docker isolado
- Ler e interpretar um arquivo `docker-compose.yml` com múltiplos serviços
- Entender como serviços se comunicam dentro de uma rede Compose
- Identificar o papel de volumes, healthchecks e variáveis de ambiente num sistema real
- Distinguir Docker, Docker Compose e Kubernetes, e argumentar quando cada um faz sentido

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

> Neste curso, "orquestrar" com o Compose significa **coordenar vários containers numa mesma máquina**. Quando o mercado fala em "orquestrador", quase sempre está falando de outra ferramenta — veremos qual na seção 8.

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
    healthcheck: # como saber se o serviço está pronto de verdade

volumes:         # opcional — define volumes nomeados
  nome-volume:

networks:        # opcional — Docker Compose cria uma rede padrão automaticamente
```

> Você pode encontrar arquivos antigos começando com `version: "3.8"`. Essa chave é obsoleta na especificação atual do Compose e pode ser omitida.

---

## 3. docker-compose.yml do PetFood — completo e comentado

```yaml
# docker-compose.yml — Sistema PetFood
# Sobe frontend (React/nginx), backend (Express) e banco (PostgreSQL)
# Os valores ${...} vêm do arquivo .env (ver seção 6)

services:

  # ── Serviço 1: banco de dados ───────────────────────────────────────────────
  db:
    # Imagem oficial do PostgreSQL 15, variante alpine
    # Não precisamos de Dockerfile para o banco — a imagem oficial é suficiente
    image: postgres:15-alpine

    # Expõe a porta do banco apenas na rede interna (sem publicar no host)
    expose:
      - "5432"

    # Variáveis que o PostgreSQL usa na inicialização
    environment:
      POSTGRES_USER: ${DB_USER}
      POSTGRES_PASSWORD: ${DB_PASSWORD}
      POSTGRES_DB: ${DB_NAME}

    volumes:
      # Volume nomeado: os dados sobrevivem quando o container é removido
      - pgdata:/var/lib/postgresql/data
      # (opcional) script SQL executado só na primeira inicialização do banco
      - ./db/init.sql:/docker-entrypoint-initdb.d/init.sql

    # Como o Compose descobre que o banco está PRONTO, não só iniciado
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U ${DB_USER}"]
      interval: 5s
      timeout: 5s
      retries: 5

  # ── Serviço 2: backend ──────────────────────────────────────────────────────
  backend:
    # Constrói a imagem a partir do Dockerfile em ./backend (aula de ontem)
    build: ./backend

    # Publica a porta 3000 no host — útil para testar a API direto no dev
    ports:
      - "3000:3000"

    environment:
      NODE_ENV: production
      # "db" é o nome do serviço do banco: o Compose o resolve como hostname
      DATABASE_URL: postgresql://${DB_USER}:${DB_PASSWORD}@db:5432/${DB_NAME}
      PORT: 3000

    # Só sobe depois que o healthcheck do banco passar.
    # Sem a condição, depends_on garante apenas a ordem de START,
    # e o backend poderia tentar conectar num banco ainda inicializando.
    depends_on:
      db:
        condition: service_healthy

  # ── Serviço 3: frontend ─────────────────────────────────────────────────────
  frontend:
    # O multi-stage build de ontem, com o ARG do Vite
    build:
      context: ./frontend
      args:
        VITE_API_URL: /api   # o navegador chama /api no próprio nginx

    # Publica a porta 80 do nginx na porta 8080 do host
    # Acesse o sistema em http://localhost:8080
    ports:
      - "8080:80"

    depends_on:
      - backend

# ── Volumes nomeados ───────────────────────────────────────────────────────────
# Persistem entre `docker compose down`; `docker compose down -v` os apaga
volumes:
  pgdata:
```

---

## 4. Como os serviços se comunicam

Dentro de uma rede Docker Compose, **cada serviço é acessível pelo seu próprio nome**. O Compose configura isso automaticamente — você não precisa saber endereços IP.

No exemplo acima:

- O backend se conecta ao banco usando o hostname `db` (não `localhost`, não um IP)
- O nginx do frontend repassa as chamadas `/api` para `http://backend:3000` — é o `nginx.conf` de ontem, que agora funciona porque o nome `backend` existe

**Atenção a um equívoco comum:** quem chama a API não é o "container do frontend", é o **navegador**, que roda no seu computador e não conhece o nome `backend`. Por isso o React usa o caminho relativo `/api`: o navegador fala com o nginx, e o nginx (que está dentro da rede) fala com o backend.

```
Seu computador
│
├── Navegador ──▶ localhost:8080 ──▶ frontend (nginx)
│                  /  → arquivos do React       │
│                  /api/... ───────────────────┘
│                                   proxy_pass  │
│                                               ▼
│                                   backend:3000 ──▶ db:5432
│                                   (rede interna)   (rede interna)
│
└── curl / Postman ──▶ localhost:3000 ──▶ backend
                       (publicado só para facilitar testes no dev)
```

**Por que isso importa?** Suas variáveis de conexão mudam dependendo de onde o código está rodando. Em desenvolvimento local sem Docker, você usa `localhost`. Dentro do Compose, você usa o nome do serviço — dentro de um container, `localhost` é o próprio container. Quem configura o ambiente configura a string de conexão.

---

## 5. Comandos essenciais do Docker Compose

```bash
# Subir todos os serviços em background (-d = detached)
docker compose up -d

# Ver os logs de todos os serviços (acompanhar em tempo real com -f)
docker compose logs -f

# Ver logs de um serviço específico
docker compose logs -f backend

# Ver o status de todos os serviços (inclui o estado do healthcheck)
docker compose ps

# Abrir um shell dentro de um serviço em execução
docker compose exec backend sh

# Parar todos os serviços (mantém containers e volumes)
docker compose stop

# Parar E remover containers e rede (mantém volumes)
docker compose down

# Parar, remover containers, rede E volumes (apaga dados do banco!)
docker compose down -v

# Reconstruir imagens antes de subir (após mudança no Dockerfile ou no código)
docker compose up -d --build
```

> **Usa Podman?** O `podman compose` (ou o `podman-compose`) lê o mesmo arquivo.

**Anote aqui** — qual é a diferença entre `docker compose stop` e `docker compose down`?

```
Sua resposta:


```

---

## 6. Variáveis de ambiente e o arquivo .env

Repare que o `docker-compose.yml` da seção 3 não tem nenhuma senha escrita. Os valores `${...}` vêm de um arquivo `.env` na raiz do projeto, que o Docker Compose carrega automaticamente:

```bash
# .env (nunca commite este arquivo — adicione ao .gitignore)
DB_USER=petfood_user
DB_PASSWORD=troque_esta_senha
DB_NAME=petfood
```

A convenção usa dois arquivos complementares:

|Arquivo|Conteúdo|Vai para o Git?|
|---|---|---|
|`.env`|Valores reais (senhas, chaves)|**Nunca** — vai no `.gitignore` e no `.dockerignore`|
|`.env.example`|As mesmas chaves, sem valores|**Sempre** — quem clona sabe o que precisa preencher|

```bash
# .env.example
DB_USER=
DB_PASSWORD=
DB_NAME=
```

O mesmo `docker-compose.yml` serve para qualquer máquina de desenvolvimento ou teste: muda só o `.env`.

---

## 7. Docker Compose e as plataformas de deploy

Você pode estar pensando: "uso Vercel e Railway, o que Docker Compose tem a ver com isso?"

A resposta é: **Railway, Render e similares aceitam containers como unidade de deploy**. Quando você conecta um repositório, a plataforma detecta o `Dockerfile` de cada serviço e constrói a imagem por conta própria. O `docker-compose.yml`, em geral, **não é executado em produção**: cada serviço (backend, banco) é configurado separadamente na plataforma.

Os conceitos, porém, são os mesmos:

|No Compose|Na plataforma|
|---|---|
|Nome do serviço como hostname (`db`)|Hostname privado gerado pela plataforma, normalmente injetado como `DATABASE_URL`|
|`.env`|Variáveis de ambiente configuradas no painel|
|Volume nomeado|Disco persistente ou banco gerenciado|
|`healthcheck` / `depends_on`|Health checks da plataforma e ordem de deploy|

Saber o que está dentro da caixa torna você capaz de depurar quando algo dá errado no deploy, configurar corretamente as variáveis de ambiente da plataforma, e entender os logs de erro que aparecem.

---

## 8. E o Kubernetes?

Quando o mercado fala em "orquestrador", quase sempre está falando do **Kubernetes**. Eles não competem — cada um responde a uma pergunta diferente:

| |Docker|Docker Compose|Kubernetes|
|---|---|---|---|
|**Pergunta**|Como empacoto minha aplicação para rodar igual em qualquer lugar?|Como subo juntos os vários serviços do meu sistema?|Como mantenho o sistema no ar em várias máquinas, mesmo com falhas e picos de carga?|
|**Escopo**|1 container|1 máquina|Várias máquinas (cluster)|
|**Arquivo**|`Dockerfile`|`docker-compose.yml`|Manifestos YAML|

**A imagem é o elo comum.** O Kubernetes não constrói imagens: ele executa as mesmas imagens que o `docker build` gera. (Você pode ter lido que "o Kubernetes abandonou o Docker": em 2022 ele trocou o motor interno que usa para rodar containers, mas as imagens continuam funcionando normalmente.)

**Declarar uma vez × vigiar sempre.** O Compose aplica o estado que você descreveu, uma vez, numa máquina. O Kubernetes compara o tempo todo o que está rodando com o que foi declarado (`replicas: 3`): se um container cai, ele sobe outro; se uma máquina falha, as cópias vão para outra. Na analogia de ontem: você não diz "asse um bolo", você declara "quero sempre 3 bolos na vitrine", e o gerente da confeitaria cuida do resto.

**O que o Compose já te ensinou continua valendo:**

|No Compose|No Kubernetes|
|---|---|
|Nome do serviço como hostname|Mesma ideia, pelo nome do `Service`|
|`.env` para credenciais|`Secret` e `ConfigMap`|
|Volume nomeado|`PersistentVolumeClaim`|
|`healthcheck`|_Probes_ (readiness, liveness)|
|`depends_on`|Não existe: a aplicação precisa tolerar dependências fora do ar e tentar de novo|

**Então meu projeto precisa de Kubernetes?** Muito provavelmente não. Ele passa a valer o custo quando o sistema precisa de mais de uma máquina, a carga varia muito, ficar fora do ar custa caro, há muitas equipes publicando muitos serviços — e existe alguém para operar o cluster. Para um sistema com poucos serviços e poucos usuários, Compose numa máquina ou uma plataforma gerenciada resolve com muito menos esforço. **Escolher a ferramenta pelo problema, não pela fama, é uma decisão de engenharia.**

---

## 9. Tabela de referência rápida

|Cenário|Comando|
|---|---|
|Subir o ambiente pela primeira vez|`docker compose up -d --build`|
|Acompanhar o que está acontecendo|`docker compose logs -f`|
|Checar se os serviços subiram (e se estão saudáveis)|`docker compose ps`|
|Entrar num serviço para investigar|`docker compose exec backend sh`|
|Parar sem perder dados|`docker compose stop`|
|Destruir tudo e recomeçar|`docker compose down -v`|
|Reconstruir após mudança no código|`docker compose up -d --build`|

---

## 10. Questão estruturante para reflexão

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

_CIN0136 — Desenvolvimento de Software | CIn-UFPE_
_Referências: Documentação oficial do Docker Compose (docs.docker.com/compose). | Kubernetes — Overview (kubernetes.io/docs/concepts/overview). | Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 14, seção 14.5.2 (plataformas de orquestração de contêineres). | Valente, M. T. Engenharia de Software Moderna. Cap. 10, seção 10.4 (Deployment Contínuo)._
