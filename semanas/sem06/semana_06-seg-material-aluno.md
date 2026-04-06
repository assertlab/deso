# Semana 6 — Segunda-feira

## Introdução ao Design e Projeto de Arquitetura de Software

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **06/04/2026 | E132 | 18:50–20:30**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 14, seções 14.1.1 e 14.1.2 (Princípios fundamentais de arquitetura; Integração no design de software)

📖 _Engenharia de Software Moderna_ — Cap. 7, seções iniciais (Arquitetura em Camadas e MVC)

Se você não leu antes de vir, leia antes da próxima aula — o conteúdo de terça pressupõe este.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar o que é arquitetura de software e por que ela importa mais do que parece no início de um projeto
- Descrever como HTTP, TCP/IP e o modelo cliente-servidor funcionam juntos para fazer uma aplicação web funcionar
- Identificar as três camadas de uma arquitetura web (apresentação, lógica, dados) e mapear onde o React, o Express e o banco de dados do seu projeto se encaixam
- Começar a formular argumentos sobre por que separar em camadas é uma decisão de design, não só de organização de pastas

---

## 1. Uma pergunta antes de começar

> _"O que acontece exatamente entre o momento em que você digita uma URL no navegador e o momento em que a página aparece?"_

Anote o que você sabe (ou acha que sabe) antes da discussão:

```
Sua resposta inicial:




```

---

## 2. A Web como arquitetura cliente-servidor

A Web não é um conjunto de arquivos. É uma **arquitetura distribuída** onde clientes fazem perguntas e servidores respondem — tudo seguindo protocolos bem definidos.

### 2.1 TCP/IP — a fundação invisível

Antes de qualquer comunicação web, há uma camada de transporte responsável por garantir que os dados cheguem:

| Protocolo | O que faz |
|-----------|-----------|
| **IP** | Endereça máquinas na rede (ex: `128.32.244.172`). O endereço `127.0.0.1` é "este computador" — seu `localhost` |
| **TCP** | Garante que os pacotes cheguem na ordem certa e sem erros. Sem TCP, pacotes perdidos ficariam perdidos |
| **Porta** | Permite que uma mesma máquina tenha vários serviços rodando (porta 3000 = seu Express, porta 5432 = seu PostgreSQL) |

### 2.2 HTTP — o protocolo que fala com a aplicação

HTTP é um protocolo de **requisição e resposta** que roda sobre TCP/IP. Cada interação tem duas partes:

**Requisição (cliente → servidor):**
```
GET /api/pets HTTP/1.1
Host: localhost:3000
Accept: application/json
```

**Resposta (servidor → cliente):**
```
HTTP/1.1 200 OK
Content-Type: application/json

[{ "id": 1, "name": "Rex", "species": "dog" }]
```

### 2.3 Métodos HTTP e o conceito de rota

Uma **rota** é a combinação de método HTTP + URI. O mesmo caminho `/api/pets` se comporta de forma completamente diferente dependendo do método:

| Rota | Semântica esperada |
|------|-------------------|
| `GET /api/pets` | Listar todos os pets |
| `POST /api/pets` | Criar um novo pet |
| `GET /api/pets/42` | Buscar o pet com id 42 |
| `PUT /api/pets/42` | Atualizar o pet 42 |
| `DELETE /api/pets/42` | Remover o pet 42 |

> 💡 **GETs devem ser side-effect-free**: chamar `GET /api/pets` 10 vezes não deve mudar nada no servidor. Isso permite cache, repetição segura e debugging mais fácil.

### Códigos de status HTTP — a resposta fala por si

| Faixa | Significado | Exemplos |
|-------|-------------|---------|
| `2xx` | Sucesso | `200 OK`, `201 Created`, `204 No Content` |
| `3xx` | Redirecionamento | `301 Moved Permanently` |
| `4xx` | Erro do cliente | `400 Bad Request`, `404 Not Found`, `401 Unauthorized` |
| `5xx` | Erro do servidor | `500 Internal Server Error` |

**Exercício rápido:** Sem abrir o código, qual código HTTP seu projeto deveria retornar quando alguém tenta criar um pet sem fornecer o nome? Anote:

```
Sua resposta e justificativa:


```

---

## 3. Arquitetura em 3 Camadas

A pergunta central do design arquitetural não é "como fazer funcionar?" — é **"como organizar para que funcione, escale e seja mantido?"**

A **arquitetura em 3 camadas** é a resposta mais consolidada para aplicações web:

```
┌─────────────────────────────────┐
│   APRESENTAÇÃO (Presentation)   │  ← React, HTML, CSS
│   O que o usuário vê e toca     │
└─────────────────┬───────────────┘
                  │ HTTP (JSON)
┌─────────────────▼───────────────┐
│   LÓGICA (Application/Logic)    │  ← Express, Node.js
│   As regras do negócio          │
└─────────────────┬───────────────┘
                  │ SQL / ORM
┌─────────────────▼───────────────┐
│   DADOS (Persistence)           │  ← SQLite, PostgreSQL
│   Onde as informações vivem     │
└─────────────────────────────────┘
```

### 3.1 Por que separar em camadas?

A separação não é burocracia — é uma decisão com consequências concretas:

| Sem separação | Com separação |
|---------------|---------------|
| Mudar o banco de dados quebra a interface | Só a camada de dados precisa mudar |
| Dois devs editam o mesmo arquivo | Cada um trabalha na sua camada |
| Testar a lógica exige renderizar a tela | Lógica é testável de forma isolada |
| Escalar o servidor significa escalar tudo | Pode escalar camadas independentemente |

**Debate para a aula:** "Por que separar em camadas se isso complica o código?" — você vai defender qual lado?

```
Meu argumento (escreva antes da discussão):


```

### 3.2 Escalabilidade e shared-nothing

À medida que uma aplicação cresce, cada camada pode ser replicada de forma independente. O modelo **shared-nothing** garante que os servidores de aplicação não compartilhem estado entre si — qualquer requisição pode ser atendida por qualquer instância.

```
                     ┌─── App Server 1 ───┐
Load Balancer ──────►├─── App Server 2 ───┤──► Banco de Dados
                     └─── App Server 3 ───┘
```

---

## 4. MVC — um padrão dentro da camada de lógica

O **MVC (Model-View-Controller)** é um padrão arquitetural que organiza a camada de lógica em três responsabilidades:

```
Requisição HTTP
       │
       ▼
   Controller ──► busca/modifica dados ──► Model (dados/BD)
       │
       ▼
    View (ou resposta JSON)
```

| Componente | Responsabilidade | No seu projeto |
|------------|-----------------|----------------|
| **Model** | Representar e persistir dados | Funções/queries de banco |
| **View** | Apresentar os dados | React (frontend) ou JSON (API) |
| **Controller** | Coordenar a interação | Handlers do Express |

> 💡 Em APIs REST (como o Express do seu projeto), a "View" é substituída por uma resposta JSON. O React, que consome essa API, faz o papel de View no frontend.

---

## 5. SOA — quando o sistema cresce além de uma aplicação

A **Arquitetura Orientada a Serviços (SOA)** surge quando uma única aplicação não é suficiente. Em vez de um monolito, o sistema é composto de serviços independentes que se comunicam por APIs.

O caso da Amazon (2002) é emblemático: o então CEO Jeff Bezos mandou um e-mail interno exigindo que **todos os times expusessem seus sistemas como serviços** com APIs bem definidas — qualquer comunicação que não fosse via API seria proibida. O resultado foi o que virou a AWS.

### Prós e contras de SOA

| Prós | Contras |
|------|---------|
| Reusabilidade de serviços | Estado distribuído é mais difícil de gerenciar |
| Cada serviço pode usar a tecnologia mais adequada | Serialização de dados na fronteira |
| Mais fácil de escalar individualmente | Latência de rede adicionada |
| Times independentes por serviço | Debugging distribuído é mais complexo |

---

## 6. Mapeando o seu projeto nas camadas

Agora aplique o que aprendeu. Para o projeto da sua equipe:

### 6.1 Arquitetura atual

| Camada | Tecnologia que usamos | Responsável na equipe |
|--------|----------------------|----------------------|
| Apresentação | | |
| Lógica | | |
| Dados | | |

### 6.2 Uma requisição típica no seu projeto

Escolha uma user story do backlog da equipe e trace o caminho completo de uma requisição:

```
User Story escolhida: ________________________________

1. Usuário faz o quê no frontend? 
   _____________________________________________

2. Qual requisição HTTP é enviada? (método + rota)
   _____________________________________________

3. O que o Express faz com ela?
   _____________________________________________

4. Que dados são consultados/modificados no banco?
   _____________________________________________

5. O que é retornado para o frontend?
   _____________________________________________
```

---

## 7. Questão estruturante

> _"Se a arquitetura em camadas complica o código, por que equipes profissionais continuam adotando-a mesmo em projetos pequenos?"_

```
Sua reflexão (escreva ao final da aula, não antes):



```

---

## 8. Para a próxima aula (Terça-feira)

📖 **Leitura:** Cap. 14, seções 14.1.1–14.1.2 (continuação, se ainda não terminou) + _Engenharia de Software Moderna_, Cap. 5 (Princípios de Projeto: Coesão, Acoplamento, Ocultamento de Informação)

**Traga:** dois trechos do código do seu projeto — um que você acha que está bem organizado e um que te incomoda mas você não sabe exatamente por quê. Terça a gente vai dar nome ao que você está sentindo.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
_Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 14. | Valente, M. T. Engenharia de Software Moderna, 2020. Cap. 7._
