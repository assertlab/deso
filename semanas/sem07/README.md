# Semana 7 — Design e Arquitetura de Software (Parte 2) + Sprint 1 Review

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1**

> ⚠️ **Atenção:** Segunda e terça desta semana foram deslocadas pelo feriado de Tiradentes (20 e 21/04). Ocorrem em **27 e 28/04**. A quinta-feira (30/04) acontece normalmente.

---

## Aulas da semana

| Dia | Data | Horário | Sala | Tema | Materiais |
|-----|------|---------|------|------|-----------|
| Segunda | 27/04/2026 | 18:50–20:30 | E132 | Estilos Arquiteturais: trade-offs e decisões | [Material do Aluno](semana_07-seg-material-aluno.md) · [Guia do Professor](semana_07-seg-material-professor.md) |
| Terça | 28/04/2026 | 17:00–18:40 | E132 | C4 Model: desenhando a arquitetura do projeto | [Material do Aluno](semana_07-ter-material-aluno.md) · [Guia do Professor](semana_07-ter-material-professor.md) |
| Quinta | 30/04/2026 | 17:00–20:30 | Grad04 | Lab: C4 aplicado + Sprint 1 Review com stakeholder | — |

---

## Leituras prévias por dia

### Segunda — 27/04

> Tema: Estilos arquiteturais e trade-offs

**Garcia — _Engenharia de Software em Dimensões_, Cap. 14:**
- Seção 14.3 — Estilos arquiteturais monolíticos
- Seção 14.4 — Estilos arquiteturais distribuídos
- Seção 14.5 — Trade-offs e escolha arquitetural

**Valente — _Engenharia de Software Moderna_, Cap. 7:**
- Seções sobre Arquitetura em Camadas, MVC, Microsserviços e trade-offs

**Pergunta para trazer:** _Antes de qualquer debate — você diria que a arquitetura do seu projeto é mais próxima de um monolito em camadas ou de serviços distribuídos? Por quê?_

---

### Terça — 28/04

> Tema: C4 Model

**Garcia — _Engenharia de Software em Dimensões_, Cap. 14:**
- Seção 14.3.1 — Nível 1: Contexto
- Seção 14.3.2 — Nível 2: Contêiner
- Seção 14.3.3 — Nível 3: Componente
- Seção 14.4 — C4 vs. UML

**Valente — _Engenharia de Software Moderna_, Cap. 7:**
- Seções sobre Camadas e MVC (base para interpretar o Nível 3 do C4)

**Traga para a aula:** um esboço (pode ser foto de papel) de como seria o Diagrama de Contexto (N1) do seu projeto — quem usa o sistema e com o que ele se conecta. Não precisa estar perfeito.

---

## Objetivos da semana

Ao final da Semana 7, cada estudante deve ser capaz de:

- Nomear os principais estilos arquiteturais (Camadas, SOA, Microsserviços) e descrever as forças e fraquezas de cada um
- Aplicar o conceito de Bounded Context para justificar separação de responsabilidades
- Argumentar os trade-offs de monolito vs. distribuído para um contexto específico
- Criar diagramas C4 dos Níveis 1, 2 e 3 para o projeto real da equipe
- Usar Mermaid para manter os diagramas vivos no repositório
- Apresentar a arquitetura do sistema ao parceiro de forma inteligível

---

## Entregáveis com prazo

| Entregável | Responsável | Prazo |
|-----------|------------|-------|
| Diagrama C4 Nível 1 (Contexto) commitado no repositório | Equipe | Até **29/04** (antes da quinta) |
| Diagrama C4 Nível 2 (Contêiner) commitado no repositório | Equipe | Até **29/04** (antes da quinta) |
| Esboço do C4 Nível 3 (Componente do back-end) | Equipe | Até **30/04** (durante o lab de quinta) |
| Demo do Sprint 1 para o stakeholder (mínimo 1 feature funcional) | Equipe | **30/04** — Sprint 1 Review |

---

## Recursos relevantes

| Recurso | Descrição | Link |
|---------|-----------|------|
| Garcia — Cap. 14 | Arquitetura, C4 Model, qualidade arquitetural | [bit.ly/esdbook](https://bit.ly/esdbook) |
| Valente — Cap. 7 | Arquitetura: Camadas, MVC, Microsserviços | [engsoftmoderna.info](https://engsoftmoderna.info) |
| C4 Model — site oficial | Referência completa dos quatro níveis | [c4model.com](https://c4model.com) |
| Mermaid — editor online | Para criar e testar diagramas Mermaid | [mermaid.live](https://mermaid.live) |
| draw.io | Ferramenta visual para diagramas arquiteturais | [draw.io](https://draw.io) |
| Richards & Ford (2025) | _Fundamentals of Software Architecture_ — referência da 1ª e 2ª Lei | O'Reilly |

---

## Por que essa semana importa para a Sprint em que estamos

A Semana 7 é o encerramento do **Sprint 1** — e isso não é coincidência.

Durante a Sprint Week (13–16/04), as equipes codaram com autonomia. Agora é hora de olhar para o que foi construído e nomeá-lo: qual estilo arquitetural emergiu? A separação em camadas que foi planejada na Semana 6 sobreviveu à pressão de entrega? Onde o código desviou do que foi combinado — e foi intencional ou acidental?

O **C4 Model** é a ferramenta que permite responder essas perguntas visualmente, e mais do que isso: permite comunicar as respostas para o stakeholder. Na Sprint 1 Review (quinta, 30/04), o parceiro vai ver um diagrama de contexto — não código. Ele vai poder dizer se o sistema que a equipe está construindo é o sistema que ele imaginou. Essa é a função da documentação arquitetural neste estágio: criar alinhamento antes que o custo de mudar seja alto.

Nas semanas seguintes, a arquitetura vai ser revisitada. A Prova 1 (Semana 8) cobre o conteúdo das Semanas 1–7, incluindo estilos arquiteturais e C4. A Semana 9 revisita os diagramas com o projeto mais maduro. A Semana 11 olha retrospectivamente para as decisões de arquitetura e pergunta: valeram a pena?

Tudo começa aqui.

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
_Última atualização: Semana 7 / 2026.1_
