# PLANO DE ENSINO — CIN0136: Desenvolvimento de Software (v7)

## Bacharelado em Sistemas de Informação | Centro de Informática — UFPE

**Período Letivo:** 2026.1 | **Semestre Ideal:** 2º  
**Carga Horária:** 120h (60h Teóricas + 60h Práticas)  
**Créditos:** 6  
**Pré-requisito:** Introdução à Programação  
**Projeto de Extensão Vinculado:** Sim — curricularização da extensão conforme diretrizes MEC  
**Horários:**

| Dia | Horário | Duração | Natureza |
|-----|---------|---------|----------|
| Segunda-feira | 17:00–18:40 | 2h | Teórica — Conceitos, leituras, debates |
| Terça-feira | 18:50–20:30 | 2h | Teórica — Aprofundamento, estudos de caso, questões estruturantes |
| Quinta-feira | 17:00–20:30 | 4h | Prática — Consolidação, workshops, laboratórios, projeto com stakeholder |

---

## 1. FILOSOFIA E ABORDAGEM PEDAGÓGICA

### 1.1 Princípios Norteadores

Este plano de ensino foi construído a partir de quatro premissas fundamentais:

**Premissa 1 — A imaturidade é o ponto de partida, não um obstáculo.** Os alunos do 2º período possuem, em geral, apenas um semestre de programação (tipicamente em Python ou C). Muitos ainda não consolidaram pensamento algorítmico, não têm experiência com projetos colaborativos e desconhecem o ecossistema profissional de desenvolvimento de software. O plano trata essa condição com realismo: os conceitos são introduzidos de forma gradual, a complexidade escala progressivamente, e cada nova camada se apoia na anterior.

**Premissa 2 — Soft skills não se ensinam em tópicos isolados; emergem de práticas intencionais.** Competências como trabalho em equipe, resolução de problemas, ética e comunicação não são conteúdos a serem "ministrados" em aulas específicas. Elas são cultivadas através de atividades cuidadosamente desenhadas — interações com stakeholders reais, debates estruturados, revisões por pares, retrospectivas, apresentações e decisões coletivas — que permeiam todo o semestre.

**Premissa 3 — Aprender a desenvolver software é aprender a pensar sobre o desenvolvimento de software.** A disciplina não visa apenas transmitir técnicas, mas desenvolver a capacidade de refletir criticamente sobre quando, por que e como aplicá-las. Isso prepara o aluno tanto para o exercício profissional imediato quanto para as transformações que inevitavelmente ocorrerão ao longo da sua carreira — incluindo a crescente mediação por ferramentas de Inteligência Artificial, que será aprofundada na disciplina ESAIA (IF1015) no 6º período.

**Premissa 4 — Problemas reais geram aprendizados reais.** A integração do projeto de extensão com demandantes externos não é um acessório pedagógico — é o motor central da disciplina. Quando o aluno sabe que existe alguém esperando o resultado do seu trabalho, a motivação muda de natureza: deixa de ser extrínseca (nota) e passa a ser intrínseca (responsabilidade, orgulho, impacto). Essa vivência profissional desde o 2º período é um diferencial formativo que prepara para o mercado de trabalho com dois anos de antecedência.

### 1.2 Metodologia

A disciplina opera sobre três eixos metodológicos integrados:

**Eixo 1 — Sala de Aula Invertida.** Antes de cada encontro teórico (segunda e terça), os alunos realizam leituras preparatórias a partir dos capítulos do livro-texto *Engenharia de Software em Dimensões* (Garcia, 2025). O tempo presencial é dedicado a debates estruturados, análise crítica, questões estruturantes e cenários de decisão — nunca a aulas meramente expositivas. O professor atua como facilitador e provocador.

**Eixo 2 — Projeto Integrador com Stakeholder Real (Extensão).** As equipes trabalham em projetos reais demandados por parceiros externos, dentro do projeto de extensão vinculado à disciplina. Isso atende à curricularização da extensão conforme diretrizes do MEC e oferece aos alunos vivência profissional autêntica: comunicação com não-técnicos, negociação de escopo, entregas incrementais com feedback real.

**Eixo 3 — Ciclos Ágeis de Desenvolvimento Baseados em Sprints.** O projeto é conduzido em ciclos incrementais curtos, no espírito das metodologias ágeis estudadas na disciplina. **Uma Sprint 0** de descoberta e preparação (entendimento do problema, elicitação de requisitos, prototipagem e fechamento de escopo com o stakeholder) antecede **quatro sprints de construção (Sprints 1–4)**, cada uma encerrada por uma review com o demandante real. Essa cadência garante que os alunos vivenciem um processo completo (da descoberta à entrega) com feedback frequente e melhoria contínua, dimensionado para o nível de maturidade do 2º período.

### 1.3 Ritmo Semanal — Os Três Momentos da Semana

A estrutura semanal segue uma progressão deliberada que respeita os diferentes tempos de aprendizagem:

| Tempo | Dia | Metáfora | Função Pedagógica |
|-------|-----|----------|-------------------|
| 1 — Exposição | Segunda (2h) | "Abrir a partitura" | Introduzir conceitos novos a partir de leituras prévias. O professor contextualiza, provoca e debate. Foco em *o quê* e *por quê*. |
| 2 — Aprofundamento | Terça (2h) | "Estudar os compassos" | Aprofundar com estudos de caso, questões estruturantes do livro, cenários de decisão. Foco em *e se?* e *depende de quê?*. |
| 3 — Consolidação e Projeto | Quinta (4h) | "Ensaiar a peça" | Prática guiada, workshops, laboratórios e **trabalho no projeto real com stakeholder**. Foco em *fazer*, *entregar* e *aprender fazendo*. |

Essa cadência garante que nenhum conceito seja cobrado na prática sem antes ter sido discutido e analisado criticamente. A quinta-feira é o "dia do projeto" desde a Semana 1 — o espaço onde a teoria ganha corpo, os erros são esperados e o aprendizado é consolidado pela experiência concreta.

### 1.4 Stack Tecnológica

A disciplina utiliza o ecossistema JavaScript, alinhado às oportunidades de mercado e à convergência das ferramentas modernas de desenvolvimento (incluindo as assistidas por IA):

| Camada | Tecnologia | Justificativa |
|--------|-----------|---------------|
| Linguagem | JavaScript (ES6+) / TypeScript (opcional) | Unifica frontend e backend; reduz carga cognitiva |
| Runtime/Backend | Node.js + Express | Simplicidade, vasto ecossistema, padrão de mercado |
| Frontend | React (via Vite) | Padrão de mercado, compatível com ferramentas IA |
| Testes unitários | Vitest | Rápido, API compatível com Jest, integrado ao Vite |
| Testes e2e/aceitação | Playwright | Moderno, cross-browser, boa documentação |
| Linter/Formatter | ESLint + Prettier | Qualidade e consistência de código desde o dia 1 |
| Banco de dados | SQLite | Banco local, zero-config, versionável junto ao repositório; elimina dependência de serviços gerenciados externos e mantém o foco no 2º período |
| Deploy | Vercel (frontend) + Render ou Railway (backend) | Free tiers generosos; deploy simples |
| Containerização | Docker (ou podman) + Docker Compose (ou podman-compose) | Paridade de ambiente; padrão de mercado; introduzido na Semana 14 |

**Nota sobre Next.js:** Embora seja uma ferramenta excelente e dominante no mercado, a mistura de server/client components e as convenções de roteamento de Next.js adicionam complexidade conceitual que compete com o foco da disciplina (engenharia de software, não domínio de framework). React via Vite mantém a separação frontend/backend explícita, reforçando os conceitos de modularização e arquitetura. Next.js é apresentado como "o que vocês encontrarão no mercado" — e poderá ser explorado na ESAIA.

**Nota sobre a transição de linguagem:** Os alunos chegam com experiência em Python ou C. O nivelamento em JavaScript acontece de forma distribuída nas semanas iniciais, contextualizado no projeto e nas ferramentas introduzidas progressivamente (Node.js, Express, Git), para que a transição seja motivada por um propósito concreto, não abstrato.

### 1.5 Estratégia de Avaliação

| Componente | Peso | Descrição |
|------------|------|-----------|
| Projeto em Equipe | 60% | Sprint 0 review + 4 sprint reviews com stakeholder + entrega formal + apresentação acadêmica |
| Provas (2 × 20%) | 40% | Duas provas escritas individuais (Semana 9 e Semana 14) |
| Participação, Exercícios Individuais e Missões | +10% *(extra)* | Engajamento nos debates, 4 exercícios individuais (EI1–EI4) e missões opcionais ao longo do semestre |

> A nota base é formada pelo Projeto (60%) e pelas Provas (40%). O componente extra é adicional podendo ser apicado ou não, a critérios dos professores. Detalhamento completo em `docs/avaliacao.md`.

---

## 2. FLUXO GERAL DO SEMESTRE

O semestre é organizado em torno do ciclo de vida do projeto real, com a teoria servindo ao projeto:

```
┌─────────────────────────────────────────────────────────────────────────┐
│                   SPRINT 0 — Descoberta e Preparação                    │
│                         Semanas 1–4 (4 semanas)                         │
│                                                                         │
│  Sem 1: Acolhimento + Fundamentos de ES + Backlog com stakeholder       │
│  Sem 2: Processos ágeis + Validação do protótipo + Fechamento de escopo │
│  Sem 3: Requisitos + User Stories + Nivelamento JS + 1º contato         │
│  Sem 4: Strateegia (escopo e backlog) + Refinamento com stakeholder     │
│                                                                         │
│  → Entrega: Protótipo hi-fi validado + Backlog priorizado + Escopo      │
├─────────────────────────────────────────────────────────────────────────┤
│                   SPRINTS 1–4 — Construção Incremental                  │
│                       Semanas 5–13 (~2 sem/sprint)                      │
│                                                                         │
│  Semana CBSOFT (Sem 5): Desenvolvimento autônomo — primeiras features   │
│  Sprint 1 (Sem 5–7):  Qualidade + Arquitetura/C4 + Sprint 1 Review      │
│  Sprint 2 (Sem 8–9):  Testes (Vitest/Playwright) + Features core        │
│  Sprint 3 (Sem 10–11): Refactoring + Manutenção + Features complementar │
│  Sprint 4 (Sem 12–13): Code Review + Docker + Estabilização             │
│                                                                         │
│  → Cada sprint: Review com stakeholder na quinta da semana de fecho     │
├─────────────────────────────────────────────────────────────────────────┤
│                    ENCERRAMENTO — Entrega e Reflexão                    │
│                        Semanas 14–16 (3 semanas)                        │
│                                                                         │
│  Sem 14: Reflexão + Prova 2 + Entrega formal ao stakeholder (feira)     │
│  Sem 15: Estabilização + Apresentações Acadêmicas + Segunda-chamada     │
│  Sem 16: Apresentações + Prova Final                                    │
│                                                                         │
│  → Entrega: Produto funcional + Feedback + Reflexão individual          │
└─────────────────────────────────────────────────────────────────────────┘
```

### 2.1 Mapeamento das Fases do Projeto

| Fase do Projeto | Foco | Semanas | Artefato de Saída |
|-----------------|------|---------|-------------------|
| **Sprint 0** — Descoberta e Preparação | Entender o problema, elicitar requisitos, prototipar e fechar escopo | 1–4 | Protótipo hi-fi validado + Backlog priorizado + Escopo fechado com stakeholder |
| **Sprint Week (CBSOFT)** — Ponte | Primeiras features de forma autônoma; gerar dores de código que motivam Arquitetura | 5 | Mínimo 2 features funcionando + registro de decisões técnicas |
| **Sprints 1–4** — Construção Incremental | Arquitetura, testes, refactoring, code review e estabilização | 6–13 | MVP funcional, testado e documentado |
| **Encerramento** — Entrega e Reflexão | Entrega formal, apresentações e reflexão | 14–16 | Produto entregue ao stakeholder + Feedback formal + Documento de Reflexão individual |

### 2.2 Correspondência Ementa → Livro-Texto → Semanas

| Conteúdo Programático (Ementa) | Capítulo(s) do Livro | Semana(s) |
|-------------------------------|---------------------|-----------|
| Introdução ao gerenciamento de projetos e à Engenharia de Software | Cap. 1 — Fundamentos de ES | 1 |
| Metodologias ágeis de desenvolvimento | **Cap. 4 — Processos de Software** | 2 |
| Engenharia de Requisitos ágil (requisitos, user stories, Gherkin) | **Cap. 6 e Cap. 7 — Requisitos e User Stories** | **3–4** |
| Qualidade de software (atributos, medição) | **Cap. 8 — Qualidade de Software** | **5** |
| Design, arquitetura de software e modularização | **Cap. 14 — Arquitetura, C4 Model, qualidade arquitetural** | **6–7, 11** |
| **Modelagem com UML (Classe, ER, Sequência) e documentação de decisões (ADR)** | **Cap. 14 (C4 e complementos)** | **7** |
| Controle de versão, PRs e Code Review | **Cap. 3 — Versionamento, Git, PRs, Code Review** | **1, 12** |
| Testes de software (unitário, integração, aceitação, BDD) | **Cap. 9 — Testes** | **8–9** |
| Refactoring, manutenção e dívida técnica | **Cap. 19 — Manutenção, refactoring, dívida técnica** | **10, 12** |
| Containerização e deploy | Documentação oficial do Docker e Docker Compose | **13** |

### 2.3 Mapa de Leitura por Livro-Texto

Enquanto a §2.2 mostra onde cada item da ementa é tratado, esta seção oferece a visão complementar por livro — quais capítulos de cada obra são mobilizados ao longo do semestre. Útil para planejar as leituras e enxergar a cobertura de cada referência.

**Garcia — *Engenharia de Software em Dimensões* (2025):**

| Capítulo | Tema | Semanas |
|---------|------|---------|
| Cap. 1 (1.1–1.7) | Fundamentos de ES, ecossistema, carreiras | 1 |
| Cap. 4 (4.1–4.5) | Processos de software, modelos, Scrum, Kanban | 2 |
| Cap. 6 (6.1–6.2) | Requisitos funcionais e não funcionais, elicitação | 3–4 |
| Cap. 7 (7.1.2–7.2.4) | User Stories, backlog, MoSCoW, WSJF | 3–4 |
| Cap. 8 (8.1–8.3) | Qualidade de software, critérios, medição | 5 |
| Cap. 14 (14.1–14.8) | Arquitetura, C4 Model, UML, ADR, qualidade arquitetural | 6–7, 11 |
| Cap. 9 (9.1–9.4) | Testes: tipos, pirâmide, cobertura, aceitação | 8–9 |
| Cap. 3 (3.1–3.7) | Versionamento, Git, PRs, Code Review, licenças | 12 |
| Cap. 19 (19.1–19.4) | Manutenção, refactoring, dívida técnica, documentação | 10, 12 |

**Valente — *Engenharia de Software Moderna* (2022):**

| Capítulo | Tema | Semanas |
|---------|------|---------|
| Cap. 1 — Introdução | Contexto histórico, panorama da ES | 1 |
| Cap. 2 — Processos | Manifesto Ágil, Scrum, Kanban | 2 |
| Cap. 3 — Requisitos | Histórias de Usuário, MVP, priorização | 3–4 |
| Cap. 8 — Testes | Unidade, integração, sistema, cobertura, TDD | 5, 8–9 |
| Cap. 5 — Princípios de Projeto | Coesão, acoplamento, SOLID | 6–7, 11 |
| Cap. 7 — Arquitetura | Camadas, MVC, microsserviços, trade-offs | 6–7 |
| Cap. 9 — Refactoring | Catálogo, code smells, prática | 10, 12 |
| Cap. 10 — DevOps | Controle de versões, integração contínua, deploy | 12 |

> **Containerização (Semana 13):** Docker e Docker Compose não são cobertos por nenhum dos livros-texto. A referência primária é a documentação oficial ([docs.docker.com](https://docs.docker.com)). Ver também §7.4.

---

## 3. CRONOGRAMA DETALHADO — VISÃO GERAL

> **Fonte de verdade operacional:** o cronograma detalhado aula a aula (datas, salas, leituras por seção, blocos de laboratório e entregáveis) é mantido na **planilha de plano de aulas** do semestre vigente, versionada no repositório da disciplina. Esta seção apresenta apenas a estrutura macro e a lógica das fases; para o detalhe de cada encontro, consulte a planilha.

O semestre é organizado em **quatro fases**, conduzidas como ciclos ágeis baseados em sprints:

**Sprint 0 — Descoberta e Preparação (Semanas 1–4).** Acolhimento, formação de equipes, primeiro contato com o stakeholder, elicitação de requisitos, escrita de user stories com critérios de aceitação em Gherkin, prototipagem e fechamento de escopo. Os fundamentos de ES, processos ágeis e requisitos são introduzidos a serviço do projeto. Encerra com escopo validado e backlog priorizado.

**Sprint Week (Semana 5) — Ponte.** Semana de desenvolvimento autônomo, coincidente com o feriado de 7/9 e o CBSOFT. As equipes implementam as primeiras features guiadas pelos critérios Gherkin, sem aula presencial. O propósito é deliberado: gerar as primeiras dores de organização de código que motivarão o conteúdo de arquitetura da fase seguinte. A teoria de Qualidade de Software é vista nesta semana e alimenta reflexivamente o Sprint 1.

**Sprints 1–4 — Construção Incremental (Semanas 6–13).** Construção do MVP em ciclos de ~2 semanas, cada um encerrado por uma *review* com o stakeholder. A teoria de cada quinzena é calibrada para o que a equipe precisa naquele momento: arquitetura e C4 (Sprint 1), testes (Sprint 2), refactoring e manutenção (Sprint 3), code review e containerização (Sprint 4).

**Encerramento — Entrega e Reflexão (Semanas 14–16).** Entrega formal do produto ao stakeholder em formato feira, apresentações acadêmicas, provas e reflexão individual sobre a jornada.

### 3.1 Estrutura Semana a Semana

| Semana | Tema Central | Fase | Entregável-Chave |
|--------|--------------|------|------------------|
| 1 | Fundamentos de ES + Backlog com stakeholder | Sprint 0 | Kanban + backlog inicial + EI1 (Portfólio Git) |
| 2 | Processos ágeis + Fechamento de escopo | Sprint 0 | Backlog MoSCoW + protótipo validado + escopo aprovado · ✅ Review Sprint 0 |
| 3 | Requisitos + User Stories + Nivelamento JS | Sprint 0 | Ambiente JS + 1º contato com stakeholder + EI2 (Requisitos) |
| 4 | Strateegia: escopo e backlog do produto | Sprint 0 | Backlog refinado com feedback do stakeholder |
| 5 | Sprint Week (CBSOFT) + Qualidade de Software | Ponte | Mínimo 2 features + registro de decisões técnicas |
| 6 | Design e Arquitetura (Parte 1): camadas, APIs, princípios | Sprint 1 | Arquitetura mapeada + features em progresso |
| 7 | Arquitetura (Parte 2): estilos, C4, UML e ADR | Sprint 1 | Diagramas C4 + ADRs no repositório · ✅ Review Sprint 1 |
| 8 | Testes: pirâmide, cobertura, BDD + Lab Vitest | Sprint 2 | Vitest configurado + mínimo 10 testes |
| 9 | Prova 1 + Testes de aceitação (Playwright) | Sprint 2 | Testes e2e + EI3 (Testes em JS) · ✅ Review Sprint 2 |
| 10 | Refactoring + Manutenção e dívida técnica | Sprint 3 | Refatorações aplicadas com testes verdes |
| 11 | Qualidade arquitetural + Debugging | Sprint 3 | Features complementares · ✅ Review Sprint 3 |
| 12 | Code Review avançado + Documentação | Sprint 4 | Code review cruzado + documentação atualizada |
| 13 | Containerização (Docker/Compose) + Estabilização | Sprint 4 | MVP estabilizado + EI4 (Reflexão) · ✅ Review Sprint 4 |
| 14 | Reflexão + Prova 2 + Entrega formal (feira) | Encerramento | Produto entregue + feedback do stakeholder |
| 15 | Estabilização + Apresentações Acadêmicas | Encerramento | Apresentação formal + peer evaluation |
| 16 | Apresentações + Prova Final | Encerramento | — |

> **Feriados de segunda-feira em 2026.2:** 07/09 (Independência), 12/10 (N. Sra. Aparecida) e 02/11 (Finados). Os ajustes de calendário decorrentes estão refletidos na planilha de plano de aulas.

---

## 4. VISÃO CONSOLIDADA DO CRONOGRAMA

| Sem | Fase | Segunda (2h) | Terça (2h) | Quinta (4h) | Marco |
|-----|------|-------------|-----------|-------------|-------|
| 1 | Sprint 0 | Abertura: mundo além do código | Ecossistema + Intro Sinfonia | Workshop Ágil + 👤 Backlog com stakeholder | — |
| 2 | Sprint 0 | Modelos de processo | Metodologias ágeis | Consolidação ágil + Refinamento do backlog | — |
| 3 | Sprint 0 | Requisitos e elicitação | User Stories e priorização | 👤 Validação protótipo + Fechamento escopo | **✅ R-S0** / **EI2** |
| 4 | Sprint 0 | Princípios de design | C4 Model | Workshop de Arquitetura | — |
| 5 | Sprint 0 | Fundamentos de Git | Branches e estratégias | Lab Git + Setup repositório do projeto real | **EI1** |
| 6 | Sprint 0 | PR e Code Review | Licenças e ética | Lab Code Review + 👤 Prototipagem com stakeholder | — |
| 7 | Sprint 1 | Qualidade de software | Medição de qualidade | Início do desenvolvimento Sprint 1 | — |
| 8 | Sprint 1 | Tipos de teste e pirâmide | Cobertura e estratégias | Desenvolvimento + 👤 Sprint 1 Review | **✅ R-S1** |
| 9 | Sprint 2 | Testes de aceitação | Ética, sociedade e cultura digital | Lab Testes (Vitest) + Desenvolvimento Sprint 2 | — |
| 10 | Sprint 2 | Refactoring | Manutenção e dívida técnica | Desenvolvimento + 👤 Sprint 2 Review | **✅ R-S2** / **EI3** |
| 11 | Sprint 3 | Impacto do design na qualidade | Debugging e robustez | Lab Refactoring + Desenvolvimento Sprint 3 | — |
| 12 | Sprint 3 | Code Review revisitado | Documentação e entrega | 👤 Sprint 3 Review + Retrospectiva | **✅ R-S3** |
| 13 | Sprint 4 | Reflexão: da ideia ao produto | Preparação apresentações | Code Review cruzado + Estabilização final | **EI4** |
| 14 | Encerramento | O que você entregou? (reflexão) | Como você conta essa história? (roteiro) | 👤 Entrega formal ao stakeholder — formato feira | **✅ Enc. Extensão** |
| 15 | Encerramento | 🎤 Apresentações — Bloco 1 | 🎤 Apresentações — Bloco 2 | Retrospectiva final + Encerramento | **✅ Final** |

> Legenda: **👤** = interação com stakeholder | **✅ R-Sn** = Review do Sprint n | **EI** = Exercício Individual | **🎤** = Apresentação

---

## 5. SÍNTESE DOS MOMENTOS COM STAKEHOLDER

 stakeholder participa de **momentos formais** distribuídos ao longo de todo o projeto, garantindo que ele nunca se distancie das necessidades reais:

| Momento | Fase | Referência aproximada | Propósito |
|---------|------|----------------------|-----------|
| Construção do backlog | Sprint 0 | ~ Semana 1 | Entender contexto e problema; priorizar funcionalidades juntos |
| Fechamento de escopo | Sprint 0 | ~ Semana 2 | Validar protótipo hi-fi e aprovar o MVP · ✅ Review Sprint 0 |
| Primeiro contato estruturado | Sprint 0 | ~ Semana 3 | Aprofundar entendimento das necessidades com roteiro guiado |
| Refinamento do backlog (Strateegia) | Sprint 0 | ~ Semana 4 | Apresentar visão de escopo e user stories; coletar feedback estruturado |
| Sprint 1 Review | Sprint 1 | ~ Semana 7 | Validar primeiras funcionalidades sobre a arquitetura definida |
| Sprint 2 Review | Sprint 2 | ~ Semana 9 | Validar features core do MVP |
| Sprint 3 Review | Sprint 3 | ~ Semana 11 | Validar qualidade e ajustes |
| Sprint 4 Review | Sprint 4 | ~ Semana 13 | Validar estabilização do MVP |
| Entrega formal (feira) | Encerramento | ~ Semana 14 | Entrega do produto + feedback estruturado do demandante |

---

## 6. INTEGRAÇÃO DAS HABILIDADES TRANSVERSAIS

| Habilidade Transversal | Práticas que a Desenvolvem | Momentos-Chave |
|------------------------|---------------------------|----------------|
| Mentalidade de resolução de problemas | Exercícios progressivos, debugging, sprints, problemas reais do stakeholder | Ao longo de todo o projeto |
| Criatividade | Prototipagem, brainstorming, design de soluções | Sprint 0 |
| Trabalho em equipe | Projeto real em grupo, papéis, retrospectivas, sprints | Todos os sprints |
| Habilidades interpessoais | Sessões com stakeholder real, code reviews, apresentações, feedback | Sprint 0 e todas as sprint reviews |
| Comunicação técnica e pensamento sistêmico | Diagramas C4 e UML, ADRs, documentação de arquitetura | Sprint 1 em diante |
| Relação com a sociedade e cultura digital | Debate sobre impacto social, viés, IA, extensão com impacto comunitário | Sprint 0 e encerramento |
| Ética | Código de Conduta, licenças, responsabilidade com demandante, IA e autoria | Sprint 0, Sprint 1 |
| Propriedade intelectual | Licenças, atribuição, código gerado por IA, acordo com stakeholder | Sprint 1 |

---

## 7. RECURSOS E BIBLIOGRAFIA

### 7.1 Bibliografia Básica

1. **GARCIA, V. C.** *Engenharia de Software em Dimensões: Da base conceitual à prática profissional.* ASSERT Lab, 2025. Versão 2025.2.0. ISBN 978-65-01-62882-0. **(Livro-texto principal — 18 capítulos)**
2. VALENTE, M. T. *Engenharia de Software Moderna.* 2022. Disponível em <https://engsoftmoderna.info>
3. MARTIN, R. C. *Clean Architecture: A Craftsman's Guide to Software Structure and Design.* Pearson, 1st ed.
4. FOX, A.; PATTERSON, D. *Engineering Software As a Service: An Agile Approach Using Cloud Computing.*

### 7.2 Bibliografia Complementar

1. MARTIN, R. C. *Clean Code: A Handbook of Agile Software Craftsmanship.* Prentice Hall, 2008.
2. EVANS, E. *Domain-Driven Design.* Alta Books, 3ª ed.
3. SMART, J. *BDD in Action.* Manning Publications, 1st ed.
4. **GARCIA, V. C.; MEDEIROS, R. P.** *Sinfonia: Metodologia para Desenvolvimento de Produtos de IA.* TDS Books, 2025.
5. FORSGREN, N.; HUMBLE, J.; KIM, G. *Accelerate.* IT Revolution Press, 2018.

### 7.3 Stack Tecnológica e Ferramentas

| Ferramenta | Propósito | Quando entra no projeto |
|------------|-----------|-------------------------|
| Git / GitHub | Versionamento e colaboração | Sprint 0 — desde o primeiro dia |
| GitHub Projects | Gestão de projeto (Kanban) | Sprint 0 — desde o primeiro dia |
| VS Code | IDE | Sprint 0 — nivelamento técnico |
| Node.js 20+ | Runtime JavaScript | Sprint 0 — nivelamento técnico |
| Express | Framework backend | Sprint 0 — nivelamento técnico |
| React (via Vite) | Framework frontend | Sprint 0 — nivelamento técnico |
| ESLint + Prettier | Linter e formatter | Sprint 0 — desde o primeiro código |
| SQLite | Banco de dados local | Sprint 0 → uso ao longo dos sprints de construção |
| Mermaid / draw.io | Diagramas C4 e UML (Classe, ER, Sequência) | Sprint 1 — documentação de arquitetura |
| ADR (Markdown no repositório) | Registro de decisões arquiteturais | Sprint 1 — documentação de arquitetura |
| Vitest | Testes unitários | Sprint 2 — início dos testes |
| Playwright | Testes e2e / aceitação | Sprint 2 — testes de aceitação |
| Vercel / Render / Railway | Deploy | Sprints de construção — conforme necessidade |
| Docker + Docker Compose | Containerização e orquestração local | Sprint 4 — estabilização e entrega |

### 7.4 — Referências de Apoio (temas não cobertos pelos livros-texto)

- NYGARD, M. *Documenting Architecture Decisions.* 2011. (post seminal que introduziu os ADRs) — <https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions>
- *Architecture Decision Records* — <https://adr.github.io> (organização, templates e exemplos da comunidade)
- *Docker Documentation* — <https://docs.docker.com> (containerização e Docker Compose)

---

## 8. NOTA SOBRE IA NO CONTEXTO DA DISCIPLINA

**Política de uso de IA:** Os alunos podem usar ferramentas de IA como auxiliares de aprendizagem (tirar dúvidas, entender conceitos, explorar alternativas de código), mas **todo código entregue deve ser compreendido, explicado e testado pelo aluno**. O uso de IA sem compreensão do output será tratado como equivalente a plágio. Os alunos devem documentar quando e como usaram IA nos seus commits e PRs.

**Conexão com o futuro:** Em momentos estratégicos (Semanas 1, 6, 9, 14), o professor contextualiza como as práticas aprendidas serão transformadas pela IA nos semestres seguintes, criando um arco narrativo que culmina na disciplina ESAIA (IF1015) no 6º período. A mensagem central é: "Os fundamentos que vocês estão construindo aqui — Git, testes, arquitetura, requisitos, qualidade — não serão substituídos pela IA; serão amplificados por ela."

---

## 9. PROJETO DE EXTENSÃO — DIRETRIZES

### 9.1 Enquadramento

O projeto de extensão vinculado à disciplina atende à curricularização da extensão conforme diretrizes do MEC (Resolução CNE/CES nº 7/2018). As horas de extensão são computadas como parte da carga horária prática da disciplina.

### 9.2 Perfil dos Demandantes

Os stakeholders são parceiros externos — organizações do terceiro setor, pequenas empresas, coletivos comunitários ou departamentos internos da UFPE — que possuem demandas reais de soluções de software. Critérios de seleção:

- Problema com escopo viável para um semestre (MVP entregável)
- Disponibilidade para interação recorrente com a equipe ao longo do semestre (tipicamente uma sessão por fase do projeto)
- Compreensão de que o produto é desenvolvido por alunos em formação
- Compromisso com feedback construtivo e regular

### 9.3 Compromissos Mútuos

| Parte | Compromisso |
|-------|-------------|
| Equipe de alunos | Entregar MVP funcional, documentado e testado; comunicação profissional e regular; respeito a prazos |
| Stakeholder | Disponibilidade para as sessões de interação ao longo do projeto; feedback honesto e construtivo; clareza na comunicação de necessidades |
| Professor | Mediação da relação; suporte técnico e pedagógico; garantia de que a extensão serve ao aprendizado |

### 9.4 Propriedade Intelectual

O código produzido é de propriedade compartilhada entre os alunos e a universidade, licenciado sob licença aberta (MIT ou similar), salvo acordo diferente com o stakeholder. Os alunos mantêm o direito de incluir o projeto em seus portfólios.

---

*Documento elaborado com base no Programa de Componente Curricular CIN0136, no livro "Engenharia de Software em Dimensões" (Garcia, 2025), nas diretrizes do MEC para curricularização da extensão e em 13 anos de experiência na disciplina de Engenharia de Software no CIn-UFPE.*

*v7 — 11/06/2026: Semana 14 remodelada. Aulas de segunda e terça substituídas por conteúdo de containerização (Docker e Docker Compose), com estudo de caso ancorado no sistema PetFood. Justificativa: conteúdo de formação profissional essencial, aproveitando o espaço pós-Sprint 4 sem competir com entregas. Docker e Docker Compose adicionados à stack tecnológica e à tabela de correspondência ementa→semanas.*

*v8 — 10/08/2026 (2026.2): Remoção integral da Metodologia Sinfonia (framework e metáfora dos quatro movimentos), substituída pela descrição direta dos ciclos ágeis baseados em sprints (Sprint 0 + Sprints 1–4) que já estruturavam a disciplina. Cronograma detalhado (§3) substituído por visão macro que aponta para a planilha de plano de aulas como fonte de verdade operacional, eliminando duplicação. Padronização de SQLite como banco de dados local. Introdução de diagramas UML (Classe, ER, Sequência) como complemento ao C4 Model e ensino formal de ADRs (Architecture Decision Records), ambos ancorados no Sprint 1. Tabelas de ferramentas (§7.3), momentos com stakeholder (§5) e competências transversais (§6) reancoradas em fases do projeto em vez de semanas fixas, para maior estabilidade entre semestres. Nova subseção §7.4 com referências de apoio a temas fora dos livros-texto (ADR e Docker). Remoção da §10 ("Adaptação da Sinfonia"). Re-sincronização geral da numeração de capítulos e do calendário com o plano de aulas 2026.2.*
