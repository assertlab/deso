# PLANO DE ENSINO — CIN0136: Desenvolvimento de Software (v7)

## Bacharelado em Sistemas de Informação | Centro de Informática — UFPE

**Professor:** Vinicius Cardoso Garcia, PhD  
**Período Letivo:** 2026.1 | **Semestre Ideal:** 2º  
**Carga Horária:** 120h (60h Teóricas + 60h Práticas)  
**Créditos:** 6  
**Pré-requisito:** Introdução à Programação  
**Projeto de Extensão Vinculado:** Sim — curricularização da extensão conforme diretrizes MEC  
**Horários:**

| Dia | Horário | Duração | Natureza |
|-----|---------|---------|----------|
| Segunda-feira | 18:50–20:30 | 2h | Teórica — Conceitos, leituras, debates |
| Terça-feira | 17:00–18:40 | 2h | Teórica — Aprofundamento, estudos de caso, questões estruturantes |
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

**Eixo 3 — Mini-Sinfonia como Framework do Projeto.** O projeto segue uma versão simplificada da Metodologia Sinfonia (Garcia & Medeiros, 2025), adaptada para o nível de maturidade do público-alvo, garantindo que os alunos vivenciem um processo estruturado de descoberta, design, construção e validação.

### 1.3 Ritmo Semanal — O Ciclo de Três Tempos

A estrutura semanal segue uma progressão deliberada que respeita os diferentes tempos de aprendizagem:

| Tempo | Dia | Metáfora | Função Pedagógica |
|-------|-----|----------|-------------------|
| 1º Tempo — Exposição | Segunda (2h) | "Abrir a partitura" | Introduzir conceitos novos a partir de leituras prévias. O professor contextualiza, provoca e debate. Foco em *o quê* e *por quê*. |
| 2º Tempo — Aprofundamento | Terça (2h) | "Estudar os compassos" | Aprofundar com estudos de caso, questões estruturantes do livro, cenários de decisão. Foco em *e se?* e *depende de quê?*. |
| 3º Tempo — Consolidação e Projeto | Quinta (4h) | "Ensaiar a peça" | Prática guiada, workshops, laboratórios e **trabalho no projeto real com stakeholder**. Foco em *fazer*, *entregar* e *aprender fazendo*. |

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
| Banco de dados | SQLite (início) → PostgreSQL (se necessário) | Simplicidade para 2º período; migração natural |
| Deploy | Vercel (frontend) + Render ou Railway (backend) | Free tiers generosos; deploy simples |

**Nota sobre Next.js:** Embora seja uma ferramenta excelente e dominante no mercado, a mistura de server/client components e as convenções de roteamento de Next.js adicionam complexidade conceitual que compete com o foco da disciplina (engenharia de software, não domínio de framework). React via Vite mantém a separação frontend/backend explícita, reforçando os conceitos de modularização e arquitetura. Next.js é apresentado como "o que vocês encontrarão no mercado" — e poderá ser explorado na ESAIA.

**Nota sobre a transição de linguagem:** Os alunos chegam com experiência em Python ou C. O nivelamento em JavaScript acontece de forma distribuída nas semanas iniciais, contextualizado no projeto e nas ferramentas introduzidas progressivamente (Node.js, Express, Git), para que a transição seja motivada por um propósito concreto, não abstrato.

### 1.5 Estratégia de Avaliação

| Componente | Peso | Descrição |
|------------|------|-----------|
| Projeto em Equipe | 60% | Sprint 0 review + 4 sprint reviews com stakeholder + entrega formal + apresentação acadêmica |
| Provas (2 × 20%) | 40% | Duas provas escritas individuais (Semana 8 e Semana 13) |
| Participação, Exercícios Individuais e Missões | +10% *(extra)* | Engajamento nos debates, 4 exercícios individuais (EI1–EI4) e missões opcionais ao longo do semestre |

> A nota base é formada pelo Projeto (60%) e pelas Provas (40%). O componente extra é adicional — pode elevar a nota acima de 10,0 até o limite institucional. Detalhamento completo em `docs/avaliacao.md`.

---

## 2. FLUXO GERAL DO SEMESTRE

O semestre é organizado em torno do ciclo de vida do projeto real, com a teoria servindo ao projeto:

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    SPRINT 0 — Descoberta e Preparação                  │
│                         Semanas 1–4 (4 semanas)                        │
│                                                                         │
│  🎼 Sinfonia: EXPOSIÇÃO + COMPOSIÇÃO                                   │
│                                                                         │
│  Sem 1: Acolhimento + Ecossistema de DS + Backlog com stakeholder      │
│  Sem 2: Processos ágeis + Fechamento de escopo com stakeholder         │
│  Sem 3: Requisitos formais + User Stories + Nivelamento JS             │
│  Sem 4: Strateegia: escopo e backlog + Refinamento com stakeholder     │
│                                                                         │
│  → Entrega: Backlog priorizado + Protótipo hi-fi + Escopo fechado     │
├─────────────────────────────────────────────────────────────────────────┤
│               SPRINT 1 — Primeiras Funcionalidades                     │
│                  Semanas 5–7 + Sprint Week (~4 semanas)                 │
│                                                                         │
│  🎼 Sinfonia: COMPOSIÇÃO → ENSAIO                                      │
│                                                                         │
│  Sem 5:  Qualidade de Software + Definition of Done + Início Sprint 1  │
│  Sem 6:  Design e Arquitetura Parte 1 (HTTP, 3 camadas, MVC, APIs)    │
│  ICSE:   Sprint Week — Desenvolvimento autônomo                        │
│  Sem 7:  Design e Arquitetura Parte 2 (C4 Model) + Sprint 1 Review    │
│                                                                         │
│  → Entrega: Features Sprint 1 + Diagramas C4 + Feedback stakeholder   │
├─────────────────────────────────────────────────────────────────────────┤
│               SPRINT 2 — Testes + Features Core do MVP                 │
│                       Semanas 8–9 (~2 semanas)                         │
│                                                                         │
│  🎼 Sinfonia: ENSAIO                                                   │
│                                                                         │
│  Sem 8:  Balanço + Prova 1 + Lab Vitest + Início Sprint 2             │
│  Sem 9:  Testes de Software + BDD/Gherkin + Sprint 2 Review           │
│                                                                         │
│  → Entrega: Features core + Testes (Vitest + Playwright) + Feedback   │
├─────────────────────────────────────────────────────────────────────────┤
│               SPRINT 3 — Refactoring + Qualidade                       │
│                      Semanas 10–11 (~2 semanas)                        │
│                                                                         │
│  🎼 Sinfonia: ENSAIO                                                   │
│                                                                         │
│  Sem 10: Refactoring + Manutenção + Dívida técnica                    │
│  Sem 11: Impacto do design na qualidade + Debugging + Sprint 3 Review │
│                                                                         │
│  → Entrega: Código refatorado + Qualidade evidenciada + Feedback      │
├─────────────────────────────────────────────────────────────────────────┤
│               SPRINT 4 — Estabilização + Entrega                       │
│                      Semanas 12–13 (~2 semanas)                        │
│                                                                         │
│  🎼 Sinfonia: ENSAIO → RESSONÂNCIA                                    │
│                                                                         │
│  Sem 12: Code Review avançado + Documentação + Code Review cruzado    │
│  Sem 13: Reflexão + Prova 2 + Sprint 4 Review + Estabilização        │
│                                                                         │
│  → Entrega: MVP estabilizado + Documentação + Feedback                │
├─────────────────────────────────────────────────────────────────────────┤
│                    RESSONÂNCIA — Entrega e Reflexão                     │
│                        Semanas 14–15 (2 semanas)                       │
│                                                                         │
│  🎼 Sinfonia: RESSONÂNCIA                                              │
│                                                                         │
│  Sem 14: Ressonância + Entrega formal ao stakeholder                   │
│  Sem 15: Apresentações acadêmicas + Segunda-chamada                    │
│                                                                         │
│  → Entrega: Produto entregue + Feedback formal + Apresentação         │
└─────────────────────────────────────────────────────────────────────────┘
```

### 2.1 Mapeamento Sinfonia → Semestre

| Movimento da Sinfonia | Fase do Semestre | Semanas | Artefato de Saída |
|----------------------|------------------|---------|-------------------|
| **Exposição** — Alinhar Estratégia | Sprint 0 (parte 1) | 1–3 | Canvas de Visão do Projeto (simplificado) |
| **Composição** — Desenhar a Solução | Sprint 0 (parte 2) + Sprint 1 | 3–7 | Protótipo hi-fi validado + Backlog priorizado + Arquitetura definida |
| **Ensaio** — Construir e Testar | Sprints 1–4 | 5–13 | MVP funcional, testado e documentado |
| **Ressonância** — Medir e Aprender | Entrega e Reflexão | 14–15 | Feedback do stakeholder + Documento de reflexão |

### 2.2 Correspondência Ementa → Livro-Texto → Semanas

| Conteúdo Programático (Ementa) | Capítulo(s) do Livro | Semana(s) |
|-------------------------------|---------------------|-----------|
| Introdução ao gerenciamento de projetos | Cap. 1 — Engenharia de Software | 1 |
| Metodologias ágeis de desenvolvimento | Cap. 4 — Processos de Software | 2 |
| Intro à Engenharia de Requisitos ágil | Cap. 6 e Cap. 7 — Requisitos e User Stories | 3 |
| Qualidade de software | Cap. 8 — Qualidade de Software | 5 |
| Arquitetura de software e Modularização | Cap. 14 — Fundamentos de Arquitetura | 6, 7, 11 |
| Testes de software | Cap. 9 — Testes | 9 |
| Refactoring e Manutenção | Cap. 19 — Manutenção e Evolução | 10 |
| Code Review | Cap. 3, seção 3.5 | 12 |
| Introdução ao controle de versão | Cap. 3 — Versionamento e Gerência de Configuração | *Momento prático a definir* |

---

## 3. CRONOGRAMA DETALHADO — SEMANA A SEMANA

> **Convenção de leitura:**
> - 🔵 **SEG** = Segunda-feira (2h, teórica — conceitos) — 18:50–20:30
> - 🟢 **TER** = Terça-feira (2h, teórica — aprofundamento) — 17:00–18:40
> - 🟠 **QUI** = Quinta-feira (4h, prática — consolidação e projeto) — 17:00–20:30
> - 📖 = Leitura prévia obrigatória
> - 🎯 = Entregável da semana
> - 👤 = Momento de interação com stakeholder

---

## SPRINT 0 — DESCOBERTA E PREPARAÇÃO (Semanas 1–4)

### 🎼 Sinfonia: Exposição + Composição

> **Propósito:** Acolher, nivelar, formar equipes, conhecer o stakeholder, entender o problema, prototipar e fechar escopo. Os conceitos teóricos (ES, processos, requisitos) são introduzidos **a serviço** do projeto desde o primeiro dia.

---

#### 📅 Semana 1 — Abertura: O que é desenvolver software? + Construção do Backlog

**🔵 SEG — O mundo além do código**

- 📖 Leitura prévia: Cap. 1, seções 1.1 a 1.3 (O que é ES? Diferencial da ES; Desafios técnicos e organizacionais)
- Dinâmica de apresentação: "Quem sou eu no contexto da tecnologia?"
- Discussão provocativa: "Qual é a diferença entre programar e desenvolver software?"
- Apresentação do plano de ensino, metodologia, contrato pedagógico e projeto de extensão
- Apresentação dos desafios/demandantes reais — visão geral dos projetos disponíveis

**🟢 TER — Ecossistema do desenvolvimento de software + Introdução à Sinfonia**

- 📖 Leitura prévia: Cap. 1, seções 1.4 a 1.7 + Sinfonia Cap. 2 (Visão Geral dos 4 Movimentos)
- Mapa mental coletivo: papéis, atividades e artefatos no desenvolvimento de software
- Apresentação da Mini-Sinfonia como framework do projeto do semestre
- Apresentação e assinatura do Código de Conduta e Ética
- Formação exploratória de equipes (4–5 integrantes) e alocação de stakeholders
- Debate com Questões Estruturantes do Cap. 1 (selecionar 2)

**🟠 QUI — Workshop Ágil + 👤 Construção do Backlog com Stakeholder (4h)**

- Bloco 1 (1.5h) — **Workshop Ágil:**
  - Atividade lúdica: "Construindo sem plano" → repetir com mini-sprint estruturada → comparar
  - Configuração do quadro Kanban da equipe (GitHub Projects ou Jira) com colunas: Backlog → To Do → In Progress → Review → Done
  - Planning poker simplificado: como estimar esforço
- Bloco 2 (2.5h) — **👤 Construção do backlog com stakeholder:**
  - 👤 Sessão com stakeholder: detalhar funcionalidades desejadas, priorizar juntos
  - Cada equipe transforma as conversas em itens de backlog (ainda informais — a formalização em user stories virá na Semana 3)
  - Priorização colaborativa: o que é mais urgente para o demandante? O que é mais viável para a equipe?
  - Definição dos papéis internos da equipe e acordos de trabalho
- 🎯 Quadro Kanban configurado + Backlog informal priorizado com stakeholder + Acordos de equipe
- **Exercício Individual 1 — "Portfólio Git"** (entrega domingo)

---

#### 📅 Semana 2 — Processos Ágeis + 👤 Fechamento de Escopo

**🔵 SEG — Do caos ao processo: modelos de desenvolvimento de software**

- 📖 Leitura prévia: Cap. 4, seções 4.1 e 4.2 (Modelo Cascata; Modelos Incremental e Iterativo)
- Modelos clássicos como respostas históricas a problemas de coordenação
- Debate: "O modelo cascata é realmente ruim ou apenas mal compreendido?"
- Análise: "Olhando para o nosso projeto real — o que já estamos fazendo que se parece com um processo?"

**🟢 TER — Metodologias ágeis: Scrum, Kanban e a escolha do processo**

- 📖 Leitura prévia: Cap. 4, seções 4.3 a 4.5 (Scrum, Kanban, Lean, Comparação, Critérios de escolha)
- Comparação prática: Scrum vs. Kanban — quando usar cada um?
- Debate com Questões Estruturantes do Cap. 4 (selecionar 2–3)
- Provocação: "Para o nosso projeto com stakeholder real, qual cadência faz mais sentido?"

**🟠 QUI — 👤 Validação do Protótipo Hi-Fi + Fechamento de Escopo (4h)**

- Bloco 1 (2h) — **Formalização:**
  - Conversão do backlog em user stories formais com critérios de aceitação
  - Priorização MoSCoW
  - Canvas de Visão simplificado
  - Definição do MVP
- Bloco 2 (2h) — **👤 Sessão de fechamento de escopo com stakeholder:**
  - Apresentação do protótipo hi-fi ao stakeholder
  - Validação, ajustes e aprovação formal do escopo
- 🎯 Canvas de Visão + Backlog MoSCoW + Protótipo hi-fi validado + Escopo aprovado
- **Exercício Individual 2 — "Documento de Requisitos"** (entrega domingo)
- **✅ Review Sprint 0**

---

#### 📅 Semana 3 — Requisitos + User Stories + Nivelamento JS

**🔵 SEG — Requisitos funcionais, não funcionais e técnicas de elicitação**

- 📖 Leitura prévia: Cap. 6, seções 6.1 e 6.2 (Requisitos Funcionais e Não Funcionais; Técnicas de Elicitação)
- Exercício provocativo: "Descreva o que o WhatsApp faz" — observar como descrições divergem
- Distinção funcional vs. não funcional com exemplos concretos
- Técnicas de elicitação: entrevistas, workshops, observação, prototipagem
- Reflexão: "Quais técnicas já usamos com nosso stakeholder sem saber o nome delas?"

**🟢 TER — User Stories, backlog e priorização formal**

- 📖 Leitura prévia: Cap. 7, seções 7.1.2 a 7.2.4 (User Stories, Epics, Features, MoSCoW, WSJF)
- Workshop: escrita de user stories no formato "Como [persona], quero [funcionalidade] para [benefício]"
- Critérios de qualidade (INVEST)
- Exercício de priorização com MoSCoW
- Debate com Questões Estruturantes do Cap. 7 (selecionar 2)

**🟠 QUI — Nivelamento JS + 👤 1º Contato com Stakeholder (4h)**

- Bloco 1 (2h) — **Nivelamento JavaScript:**
  - Variáveis, funções, arrays, objetos, arrow functions, template literals
  - Setup do ambiente (Node.js, VS Code, ESLint, Prettier)
  - Mini-servidor Express com 2 rotas JSON
- Bloco 2 (2h) — **👤 Primeiro contato formal com o stakeholder:**
  - Conversa guiada por roteiro mínimo
  - Plenária de encerramento
- 🎯 Ambiente JS funcional + Registro do 1º contato + Reflexão individual

---

#### 📅 Semana 4 — Strateegia: Escopo e Backlog

**🔵 SEG — Strateegia: visão do escopo do projeto**

- Dinâmica individual na Strateegia: cada estudante descreve em até 5 frases o escopo essencial do projeto (problema, personas, valor entregue)
- Leitura coletiva das respostas para evidenciar divergências de visão
- Discussão facilitada sobre alinhamento de escopo

**🟢 TER — Strateegia: construção inicial do backlog do produto**

- Dinâmica na Strateegia: cada estudante escreve user stories individuais (uma por resposta), indicando o épico correspondente, avaliação INVEST e pelo menos um critério de aceitação em formato Gherkin incluindo caso de falha
- Dinâmica de revisão coletiva: identificação de duplicatas, histórias fracas e primeiras sinalizações de prioridade

**🟠 QUI — 👤 Refinamento do Backlog com Feedback dos Stakeholders (4h)**

- Bloco 1 (2h) — **Apresentação dos resultados das dinâmicas Strateegia aos stakeholders:**
  - Visão de escopo e user stories levantadas
  - Coleta de feedback estruturado
- Bloco 2 (2h) — **Refinamento do backlog:**
  - Correção de stories, identificação de lacunas
  - Priorização MoSCoW inicial
  - Consolidação no Jira (ou GitHub Projects)
- 🎯 Backlog refinado e priorizado com feedback do stakeholder registrado

---

## SPRINT 1 — PRIMEIRAS FUNCIONALIDADES (Semanas 5–7 + Sprint Week)

### 🎼 Sinfonia: Composição → Ensaio

> **Propósito:** Estabelecer a base de qualidade, construir a arquitetura do projeto e entregar as primeiras funcionalidades ao stakeholder. A teoria de cada semana é calibrada para o que a equipe precisa naquele momento.

---

#### 📅 Semana 5 — Qualidade de Software

**🔵 SEG — O que é qualidade de software? Atributos e critérios**

- 📖 Leitura prévia: Cap. 8, seções 8.1.1 a 8.1.8 (Critérios de qualidade: funcionalidade, desempenho, usabilidade, confiabilidade, segurança, manutenibilidade)
- Atividade: classificar softwares conhecidos de 1 a 5 em qualidade — observar divergência de critérios
- Para cada atributo, identificação no projeto: "Qual é o mais crítico para o nosso stakeholder?"
- Debate: "Qualidade custa caro ou a falta dela custa mais?"
- Debate com Questões Estruturantes do Cap. 8 (selecionar 2)

**🟢 TER — Medição de qualidade e cultura de qualidade contínua**

- 📖 Leitura prévia: Cap. 8, seções 8.2 e 8.3 (Técnicas de medição; Avaliação contínua)
- Debate: "Quando entregarmos o produto, como o stakeholder saberá se tem qualidade?"
- Conexão com os critérios de aceitação em Gherkin da Semana 4: critérios de aceitação como expressão de qualidade esperada
- Introdução à ideia de que testes são uma das ferramentas de qualidade (preparação para semanas seguintes)

> 🔴 Quinta-feira Santa (02/04) — Sem aula. A quinta da Semana 5 é deslocada para 09/04.

**🟠 QUI (09/04) — Lab: Qualidade Aplicada ao Projeto + Início do Sprint 1 (4h)**

- Bloco 1 (2h) — **Qualidade aplicada:**
  - Cada equipe define os atributos de qualidade prioritários para seu projeto
  - Revisão dos critérios de aceitação Gherkin da Semana 4 sob a ótica de qualidade
  - Definição do "Definition of Done" da equipe para o Sprint 1
- Bloco 2 (2h) — **Início do desenvolvimento Sprint 1:**
  - Primeiras features do backlog
  - Setup técnico (se necessário)
  - Organização do trabalho no Jira (ou GitHub Projects)
- 🎯 Atributos de qualidade definidos + Definition of Done + Primeiras features em progresso

---

#### 📅 Semana 6 — Design e Arquitetura de Software (Parte 1)

**🔵 SEG — Introdução ao Design e Projeto de Arquitetura de Software**

- 📖 Leitura prévia: Cap. 14, seções 14.1.1 e 14.1.2 (Princípios fundamentais; Integração no design)
- Introdução à arquitetura web: HTTP, TCP/IP, modelo cliente-servidor e P2P
- Arquitetura em 3 camadas: apresentação, lógica de negócio, dados
- MVC como padrão organizacional
- Introdução a SOA (Service-Oriented Architecture)
- Conexão com o projeto: onde cada camada aparece (React = apresentação, Express = lógica, SQLite/PostgreSQL = dados)

**🟢 TER — O que são APIs + Princípios de design de software**

- 📖 Leitura prévia: Cap. 14, seções 14.1.1–14.1.2 (continuação) + Cap. 5 do Valente (Princípios de Projeto)
- O que é uma API — conceito geral e APIs web (REST)
- Anatomia de uma API Express: rotas, controllers, middleware
- Princípios de design: separação de responsabilidades, coesão, acoplamento, abstração, nomes significativos
- Como esses princípios impactam a manutenibilidade e a colaboração em equipe

> ⚠️ A quinta-feira 09/04 pertence ao calendário da Semana 5 (Aula 16 deslocada). A quinta da Semana 6 é 23/04 (ver abaixo — feriado de Tiradentes).

---

#### 📅 Sprint Week — ICSE (13–16/04/2026)

> Semana de desenvolvimento autônomo — professor em evento ICSE. Monitor disponível para suporte.

**🔵 SEG — Desenvolvimento autônomo — Sprint 1**

- Equipes trabalham no Sprint 1 com base na arquitetura definida na Semana 6
- Foco: implementar features respeitando a separação em camadas e o Definition of Done da Semana 5
- Atualização do Kanban no Jira (ou GitHub Projects)

**🟢 TER — Desenvolvimento autônomo — Sprint 1**

- Continuação: cadência de commits, organização do trabalho
- Registro de decisões técnicas no repositório

**🟠 QUI — Consolidação e preparação para Arquitetura Parte 2 (4h)**

- Consolidação do trabalho da semana
- Organização do repositório, atualização do Kanban
- Reflexão: "A arquitetura que planejamos na Sem 6 está se sustentando?"
- 🎯 Mínimo 2 features em progresso + Kanban atualizado + Registro de decisões técnicas

---

> 🔴 Feriado de Tiradentes — 20 e 21/04/2026 (Sem aulas de Segunda e Terça)

**🟠 QUI (23/04) — Lab: Arquitetura Aplicada ao Projeto + Desenvolvimento Sprint 1 (4h)**

> ⚠️ Única aula desta semana — segunda e terça são feriado. Pertence ao calendário da Semana 6.

- Bloco 1 (2h) — **Exercício prático:**
  - Mapear a arquitetura atual do projeto nas 3 camadas
  - Identificar onde os princípios de design estão sendo respeitados ou violados
  - Refatoração guiada de trechos problemáticos
  - Organização das rotas Express como API
- Bloco 2 (2h) — **Desenvolvimento Sprint 1**
- 🎯 Arquitetura mapeada + Código organizado + Features em progresso

---

#### 📅 Semana 7 — Design e Arquitetura de Software (Parte 2) + Sprint 1 Review

> ⚠️ Segunda e terça deslocadas do feriado de Tiradentes: ocorrem em 27 e 28/04.

**🔵 SEG (27/04) — Design e Arquitetura: padrões e estilos arquiteturais**

- 📖 Leitura prévia: Cap. 14, seções 14.3 a 14.5 (Padrões arquiteturais; Estilos; Trade-offs)
- Padrões fundamentais: Big Ball of Mud, Unitary Architecture, Client/Server
- Estilos arquiteturais: Camadas (aprofundamento), SOA, Microsserviços, Bounded Context
- Trade-offs: simplicidade vs. escalabilidade, monolito vs. distribuído
- Conexão: qual estilo se aplica ao projeto de cada equipe?

**🟢 TER (28/04) — Documentação de Arquitetura com o C4 Model**

- 📖 Leitura prévia: Cap. 14, seções 14.3.1–14.3.3 e 14.4 (Estrutura hierárquica do C4; C4 vs UML)
- Estrutura do C4: Contexto (N1), Contêiner (N2), Componentes (N3)
- Por que documentar arquitetura mesmo que mude
- Ferramentas: Mermaid e draw.io
- Hands-on com Mermaid aplicado ao projeto real

**🟠 QUI — Workshop C4 + Desenvolvimento + 👤 Sprint 1 Review (4h)**

- Bloco 1 (2h) — **Workshop C4:**
  - Cada equipe produz os diagramas C4 (N1 e N2) do projeto real usando Mermaid
  - Revisão dos princípios de design e arquitetura das Semanas 6–7
  - Merge de PRs e preparação da demo
- Bloco 2 (2h) — **👤 Sprint 1 Review:**
  - Demo ao stakeholder (10 min + 5 min feedback)
  - Retrospectiva interna + Planejamento do Sprint 2
- 🎯 Diagramas C4 no repositório + Features Sprint 1 + Feedback + Retrospectiva
- **✅ Sprint 1 Review**

---

## SPRINT 2 — TESTES + FEATURES CORE DO MVP (Semanas 8–9)

### 🎼 Sinfonia: Ensaio

> **Propósito:** Introduzir testes formais, consolidar a pirâmide de testes com Vitest e Playwright, e entregar as features core do MVP.

---

#### 📅 Semana 8 — Balanço + Prova 1 + Lab Testes com Vitest

**🔵 SEG — Balanço do Sprint 0 e Sprint 1**

- Aula reflexiva sem conteúdo novo
- Revisão do arco percorrido: ES → Processos → Requisitos → User Stories/Gherkin → Qualidade → Design/Arquitetura → C4 → Sprint 1
- Espaço para dúvidas emergentes
- Preparação conceitual para testes: por que testar? Tipos de teste e pirâmide (introdução rápida)
- Sem leitura prévia

**🟢 TER — ✏️ PROVA 1**

- Avaliação individual escrita (2h)
- Conteúdo: Semanas 1–7 — fundamentos de ES, processos ágeis, requisitos, user stories, Gherkin, qualidade de software, princípios de design, estilos arquiteturais, C4 Model

**🟠 QUI — Lab Testes com Vitest + Início do Sprint 2 (4h)**

- Bloco 1 (2h) — **Workshop Vitest:**
  - Setup de Vitest no projeto
  - Workshop progressivo em 4 fases: (1) função pura, (2) edge cases, (3) rota Express com supertest, (4) relatório de cobertura
  - Pair testing
- Bloco 2 (2h) — **Início Sprint 2:**
  - Implementação das features core com regra: nenhuma feature "pronta" sem pelo menos 1 teste
- 🎯 Vitest configurado + Mínimo 10 testes + Features Sprint 2 em progresso

---

#### 📅 Semana 9 — Testes de Software + BDD + Sprint 2 Review

**🔵 SEG — Por que testar? Tipos de teste, pirâmide e cobertura**

- 📖 Leitura prévia: Cap. 9, seções 9.1 a 9.4 (Tipos de teste; Pirâmide; Cobertura; Estratégias)
- Analogia: "Você faria cirurgia com um médico que nunca treinou?"
- Pirâmide de testes e a lógica econômica por trás da sua forma
- Cobertura — o que mede e suas limitações
- Conexão: os critérios Gherkin da Semana 4 e o Definition of Done da Semana 5 como base para testes de aceitação

**🟢 TER — Testes de aceitação + BDD e Gherkin como especificação executável**

- 📖 Leitura prévia: Cap. 9, seção 9.2.4 + revisitar Cap. 7 (User Stories)
- BDD — Behavior-Driven Development como ponte entre requisitos, testes e desenvolvimento
- O formato Gherkin (Dado/Quando/Então) como especificação executável
- Cenários de sucesso e de falha
- Playwright como ferramenta de automação e2e
- Demonstração: Playwright automatizando um cenário Gherkin

**🟠 QUI — Lab Testes de Aceitação + 👤 Sprint 2 Review (4h)**

- Bloco 1 (2h) — **Lab Playwright:**
  - Cada equipe implementa testes de aceitação (mínimo 3 cenários)
  - Merge, resolução de conflitos, preparação da demo
- Bloco 2 (2h) — **👤 Sprint 2 Review:**
  - Demo ao stakeholder (10 min + 5 min feedback)
  - Retrospectiva + Planejamento Sprint 3
- 🎯 Testes de aceitação + Features Sprint 2 + Feedback + Retrospectiva
- **Exercício Individual 3 — "Testes em JavaScript"** (entrega domingo)
- **✅ Sprint 2 Review**

---

## SPRINT 3 — REFACTORING + QUALIDADE (Semanas 10–11)

### 🎼 Sinfonia: Ensaio

> **Propósito:** Melhorar o código existente com refactoring, compreender dívida técnica, e evidenciar qualidade ao stakeholder.

---

#### 📅 Semana 10 — Refactoring + Manutenção + Sprint 3

**🔵 SEG — Refactoring: melhorar sem quebrar**

- 📖 Leitura prévia: Cap. 19, seções 19.2 e 19.3.1 (Tipos de Manutenção; Refatoração Contínua)
- Demonstração ao vivo em JS: renomear variáveis, extrair funções, simplificar condicionais, eliminar duplicação
- Catálogo de code smells
- Regra de ouro: "Refactoring sem testes é andar no escuro"

**🟢 TER — Manutenção, evolução e dívida técnica**

- 📖 Leitura prévia: Cap. 19, seções 19.1 e 19.4 (Evolução da manutenção; Documentação)
- Tipos de manutenção: corretiva, adaptativa, evolutiva, preventiva
- Debate: "Por que empresas acumulam dívida técnica?"
- Reflexão: "Onde está a dívida técnica no nosso código?"

**🟠 QUI — Lab Refactoring + Desenvolvimento Sprint 3 (4h)**

- Bloco 1 (2h) — **Lab Refactoring:**
  - Exercício: código JS "smelly" → 5 refatorações progressivas com testes verdes a cada passo
  - Pair refactoring
- Bloco 2 (2h) — **Desenvolvimento Sprint 3:**
  - Refatorações no projeto real + Features complementares
- 🎯 Exercício completo + Refatorações aplicadas + Features em progresso

---

#### 📅 Semana 11 — Design, Debugging + Sprint 3 Review

**🔵 SEG — Impacto das decisões de design na qualidade**

- 📖 Leitura prévia: Cap. 14, seções 14.7 e 14.8 (Qualidade e Arquitetura; Impacto no sucesso)
- Estudo de caso: decisão arquitetural e suas consequências
- Conexão: "As decisões das Semanas 6–7 — que impacto tiveram?"
- Debate com Questões Estruturantes do Cap. 14 (selecionar 2)

**🟢 TER — Debugging, robustez e preparação para Sprint Review**

- Técnicas de debugging: breakpoints no VS Code, console.log estratégico, stack traces
- Exercício: "Encontre e corrija os 5 bugs" em Node.js
- Tratamento de erros: try/catch, error boundaries em React, respostas HTTP adequadas
- Preparação da demo

**🟠 QUI — 👤 Sprint 3 Review + Retrospectiva (4h)**

- Bloco 1 (2h) — **Desenvolvimento final:**
  - Testes passando, features completas
- Bloco 2 (2h) — **👤 Sprint 3 Review:**
  - Demo ao stakeholder (10 min + 5 min feedback) com foco em qualidade
  - Prioridades finais, retrospectiva, planejamento Sprint 4
- 🎯 Features + Refactoring + Feedback + Retrospectiva
- **✅ Sprint 3 Review**

---

## SPRINT 4 — ESTABILIZAÇÃO + ENTREGA (Semanas 12–13)

### 🎼 Sinfonia: Ensaio → Ressonância

> **Propósito:** Code review cruzado, estabilização, documentação, preparação para entrega final ao stakeholder.

---

#### 📅 Semana 12 — Code Review + Documentação + Sprint 4

**🔵 SEG — Code Review como prática profissional (revisitado)**

- 📖 Leitura prévia: revisitar Cap. 3, seção 3.5.1 + Cap. 14, seção 14.6
- Revisitar code review com a maturidade adquirida
- Checklist avançado: legibilidade, testes, erros, convenções, documentação, diagramas C4
- Exemplos de reviews bons e ruins

**🟢 TER — Documentação, README e preparação para entrega**

- 📖 Leitura prévia: Cap. 19, seção 19.4
- O que documentar: README, guia de instalação, decisões arquiteturais, diagramas
- Reflexão: "Se a equipe fosse embora amanhã, outra conseguiria continuar?"
- Checklist de entrega

**🟠 QUI — Code Review Cruzado entre Equipes + Desenvolvimento Sprint 4 (4h)**

- Bloco 1 (2h) — **Code Review cruzado:**
  - Cada equipe abre PR; outra revisa com checklist avançado
  - Discussão pós-review
  - Incorporação do feedback
- Bloco 2 (2h) — **Desenvolvimento:**
  - Correções, bug fixes, ajustes de UX, atualização de documentação
- 🎯 Code review completo + Feedback incorporado + Documentação atualizada

---

#### 📅 Semana 13 — Reflexão + Prova 2 + Sprint 4 Review

**🔵 SEG — Reflexão: da ideia ao produto**

- Aula reflexiva sem conteúdo novo
- Revisão do arco das Semanas 8–12: testes e BDD, refactoring, qualidade arquitetural, code review avançado, documentação
- Análise das decisões de cada equipe
- Sem leitura prévia

**🟢 TER — ✏️ PROVA 2**

- Avaliação individual escrita (2h)
- Conteúdo: Semanas 8–12 — Testes (Vitest e Playwright), refactoring, code smells, manutenção, dívida técnica, qualidade arquitetural, code review avançado, documentação

**🟠 QUI — 👤 Sprint 4 Review + Estabilização Final do MVP (4h)**

- Bloco 1 (2h) — **Estabilização:**
  - Bug fixes finais, testes, README, diagramas C4, deploy funcional
- Bloco 2 (2h) — **👤 Sprint 4 Review:**
  - Demo completa do MVP (10 min + 5 min feedback)
  - Feedback final, retrospectiva
- 🎯 MVP estabilizado + Feedback final + Retrospectiva
- **Exercício Individual 4 — "Reflexão Técnica e Profissional"** (entrega domingo)
- **✅ Sprint 4 Review**

---

## RESSONÂNCIA — ENTREGA E REFLEXÃO (Semanas 14–15)

### 🎼 Sinfonia: Ressonância — Medir e Aprender

> **Propósito:** Entregar formalmente ao stakeholder, coletar feedback real, apresentar academicamente e refletir sobre a jornada completa.

---

#### 📅 Semana 14 — 👤 Entrega Formal ao Stakeholder

**🔵 SEG — Ressonância: o que significa medir e aprender**

- 📖 Leitura prévia: Sinfonia — Cap. 7, seção 7.1 (Propósito da Ressonância)
- Discussão: "Nosso software será um sucesso? Como medimos isso?"
- A perspectiva do stakeholder vs. a perspectiva técnica
- Preparação para a entrega: o que entregar, como, o que esperar

**🟢 TER — Impacto social da extensão e conexão com o futuro**

- Reflexão: impacto do projeto na organização do stakeholder
- Conexão: como os fundamentos serão amplificados pela IA — antecipação da ESAIA (IF1015)
- Workshop de apresentações com ensaio rápido (3 min por equipe)

**🟠 QUI — 👤 Entrega Formal ao Stakeholder + Coleta de Feedback Real (4h)**

- Bloco 1 (2h) — **Sessão formal de entrega:**
  - Apresentação (15 min + 10 min feedback)
  - Entrega de repositório/deploy/documentação
  - Formulário de feedback estruturado
- Bloco 2 (2h) — **Análise do feedback:**
  - Preparação para apresentação acadêmica
  - Início do Documento de Reflexão individual
- 🎯 Produto entregue + Feedback formal + Material para apresentação

---

> 🔴 Período de São João — 22 e 23/06/2026 (Sem aulas)

---

#### 📅 Semana 15 — Apresentações Acadêmicas

**🟠 QUI (25/06) — Apresentações Acadêmicas — Bloco 1**

- Apresentações formais (12 min + 5 min Q&A por equipe)
- Estrutura obrigatória seguindo os 4 movimentos da Mini-Sinfonia:
  1. **Exposição:** O problema, o stakeholder, o contexto
  2. **Composição:** Como projetamos a solução, protótipos, decisões de design
  3. **Ensaio:** Como construímos (arquitetura, código, testes), desafios técnicos, sprint reviews
  4. **Ressonância:** O que entregamos, feedback do stakeholder, lições aprendidas
- Peer evaluation estruturada

**🔵 SEG (29/06) — Apresentações Acadêmicas — Bloco 2**

- Continuação das apresentações (mesma estrutura)
- Peer evaluation

**🟢 TER (30/06) — Segunda-chamada**

---

#### 📅 Semana 16

**🟠 QUI (02/07) — Prova Final**

---

## 4. VISÃO CONSOLIDADA DO CRONOGRAMA

| Sem | Fase | Segunda (2h) | Terça (2h) | Quinta (4h) | Marco |
|-----|------|-------------|-----------|-------------|-------|
| 1 | Sprint 0 | Abertura: mundo além do código | Ecossistema + Intro Sinfonia | Workshop Ágil + 👤 Backlog com stakeholder | **EI1** |
| 2 | Sprint 0 | Modelos de processo | Metodologias ágeis | 👤 Validação protótipo + Fechamento escopo | **✅ R-S0** / **EI2** |
| 3 | Sprint 0 | Requisitos e elicitação | User Stories e priorização | Nivelamento JS + 👤 1º contato stakeholder | — |
| 4 | Sprint 0 | Strateegia: visão do escopo | Strateegia: backlog do produto | 👤 Refinamento do backlog com stakeholder | — |
| 5 | Sprint 1 | Qualidade: atributos | Qualidade: medição | 🔴 Qui Santa *(Qui reposta 09/04: DoD + Início Sprint 1)* | — |
| 6 | Sprint 1 | Design/Arq: HTTP, 3 camadas, MVC | Design/Arq: APIs, princípios de design | *(Qui 09/04 = Sem 5; Qui 23/04 = Lab Arq — ver feriado)* | — |
| ICSE | Sprint 1 | Dev autônomo | Dev autônomo | Consolidação Sprint 1 | — |
| — | *Tiradentes* | 🔴 Feriado 20/04 | 🔴 Feriado 21/04 | Lab Arquitetura + Dev Sprint 1 (23/04, Sem 6) | — |
| 7 | Sprint 1 | Padrões e estilos arquiteturais | C4 Model | Workshop C4 + 👤 Sprint 1 Review | **✅ R-S1** |
| 8 | Sprint 2 | Balanço Sprints 0–1 | ✏️ PROVA 1 | Lab Vitest + Início Sprint 2 | **P1** |
| 9 | Sprint 2 | Tipos de teste + pirâmide | BDD + Gherkin + Playwright | Lab Playwright + 👤 Sprint 2 Review | **✅ R-S2** / **EI3** |
| 10 | Sprint 3 | Refactoring | Manutenção e dívida técnica | Lab Refactoring + Dev Sprint 3 | — |
| 11 | Sprint 3 | Impacto do design na qualidade | Debugging e robustez | 👤 Sprint 3 Review + Retrospectiva | **✅ R-S3** |
| 12 | Sprint 4 | Code Review revisitado | Documentação e entrega | Code Review cruzado + Dev Sprint 4 | — |
| 13 | Sprint 4 | Reflexão: da ideia ao produto | ✏️ PROVA 2 | 👤 Sprint 4 Review + Estabilização | **✅ R-S4** / **P2** / **EI4** |
| 14 | Ressonância | Ressonância: medir e aprender | Impacto social + futuro (IA) | 👤 Entrega formal ao stakeholder | — |
| — | *São João* | 🔴 22/06 | 🔴 23/06 | — | — |
| 15 | Ressonância | 🎤 Apresentações — Bloco 2 (29/06) | Segunda-chamada (30/06) | 🎤 Apresentações — Bloco 1 (25/06) | **✅ Final** |
| 16 | — | — | — | Prova Final (02/07) | **PF** |

> Legenda: **👤** = interação com stakeholder | **✅ R-Sn** = Review do Sprint n | **EI** = Exercício Individual | **🎤** = Apresentação | **P1/P2** = Prova 1/2 | **PF** = Prova Final

---

## 5. SÍNTESE DOS MOMENTOS COM STAKEHOLDER

O stakeholder participa de **7 momentos formais** ao longo do semestre, garantindo que o projeto nunca se distancie das necessidades reais:

| Semana | Momento | Propósito |
|--------|---------|-----------|
| 1 | Backlog | Entender contexto, problema e priorizar funcionalidades juntos |
| 2 | Fechamento de escopo | Validar protótipo hi-fi, aprovar MVP |
| 4 | Refinamento do backlog | Validar user stories levantadas e priorizar com feedback |
| 7 | Sprint 1 Review | Validar primeiras funcionalidades |
| 9 | Sprint 2 Review | Validar features core do MVP |
| 11 | Sprint 3 Review | Validar qualidade e ajustes |
| 13–14 | Sprint 4 Review + Entrega formal | Validação final + entrega do produto + feedback estruturado |

---

## 6. INTEGRAÇÃO DAS HABILIDADES TRANSVERSAIS

| Habilidade Transversal | Práticas que a Desenvolvem | Momentos-Chave |
|------------------------|---------------------------|----------------|
| Mentalidade de resolução de problemas | Exercícios progressivos, debugging, sprints, problemas reais do stakeholder | Semanas 1, 8, 10, 11 |
| Criatividade | Prototipagem, Canvas de Visão, brainstorming, design de soluções | Semanas 2, 4, 6 |
| Trabalho em equipe | Projeto real em grupo (14 semanas), papéis, retrospectivas, sprints | Semanas 1–15 |
| Habilidades interpessoais | 7 sessões com stakeholder real, code reviews, apresentações, feedback | Semanas 1, 2, 4, 7, 9, 11, 13–14 |
| Relação com a sociedade e cultura digital | Debate sobre impacto social, viés, IA, extensão com impacto comunitário | Semanas 5, 14 |
| Ética | Código de Conduta, responsabilidade com demandante, IA e autoria | Semanas 1, 14 |
| Propriedade intelectual | Licenças, atribuição, código gerado por IA, acordo com stakeholder | *Momento prático a definir* |

---

## 7. RECURSOS E BIBLIOGRAFIA

### 7.1 Bibliografia Básica

1. **GARCIA, V. C.** *Engenharia de Software em Dimensões: Da base conceitual à prática profissional.* ASSERT Lab, 2025 (ed. 2025.2.0). **(Livro-texto principal)**
2. FOX, A.; PATTERSON, D. *Engineering Software As a Service: An Agile Approach Using Cloud Computing.*
3. MARTIN, R. C. *Clean Architecture: A Craftsman's Guide to Software Structure and Design.* Pearson, 1st ed.
4. VALENTE, M. T. *Engenharia de Software Moderna.* 2022.

### 7.2 Bibliografia Complementar

1. MARTIN, R. C. *Clean Code: A Handbook of Agile Software Craftsmanship.* Prentice Hall, 2008.
2. EVANS, E. *Domain-Driven Design.* Alta Books, 3ª ed.
3. SMART, J. *BDD in Action.* Manning Publications, 1st ed.
4. **GARCIA, V. C.; MEDEIROS, R. P.** *Sinfonia: Metodologia para Desenvolvimento de Produtos de IA.* TDS Books, 2025. **(Referência para o Projeto Integrador)**
5. FORSGREN, N.; HUMBLE, J.; KIM, G. *Accelerate.* IT Revolution Press, 2018.

### 7.3 Stack Tecnológica e Ferramentas

| Ferramenta | Propósito | Introdução |
|------------|-----------|------------|
| Node.js 20+ | Runtime JavaScript | Semana 3 |
| Express | Framework backend | Semana 3 |
| React (via Vite) | Framework frontend | Semana 3+ |
| Vitest | Testes unitários | Semana 8 |
| Playwright | Testes e2e/aceitação | Semana 9 |
| ESLint + Prettier | Linter e formatter | Semana 3 |
| Git / GitHub | Versionamento e colaboração | *Momento prático a definir* |
| Jira (ou GitHub Projects) | Gestão de projeto (Kanban) | Semana 1 |
| VS Code | IDE | Semana 3 |
| Mermaid / draw.io | Diagramas C4 | Semana 7 |
| Figma / Excalidraw | Prototipagem | Semana 2 |
| Vercel / Render | Deploy | Semana 7+ |
| SQLite / PostgreSQL | Banco de dados | Conforme necessidade |

---

## 8. NOTA SOBRE IA NO CONTEXTO DA DISCIPLINA

**Política de uso de IA:** Os alunos podem usar ferramentas de IA como auxiliares de aprendizagem (tirar dúvidas, entender conceitos, explorar alternativas de código), mas **todo código entregue deve ser compreendido, explicado e testado pelo aluno**. O uso de IA sem compreensão do output será tratado como equivalente a plágio. Os alunos devem documentar quando e como usaram IA nos seus commits e PRs.

**Conexão com o futuro:** Em momentos estratégicos, o professor contextualiza como as práticas aprendidas serão transformadas pela IA nos semestres seguintes, criando um arco narrativo que culmina na disciplina ESAIA (IF1015) no 6º período. A mensagem central é: "Os fundamentos que vocês estão construindo aqui — testes, arquitetura, requisitos, qualidade — não serão substituídos pela IA; serão amplificados por ela."

---

## 9. PROJETO DE EXTENSÃO — DIRETRIZES

### 9.1 Enquadramento

O projeto de extensão vinculado à disciplina atende à curricularização da extensão conforme diretrizes do MEC (Resolução CNE/CES nº 7/2018). As horas de extensão são computadas como parte da carga horária prática da disciplina.

### 9.2 Perfil dos Demandantes

Os stakeholders são parceiros externos — organizações do terceiro setor, pequenas empresas, coletivos comunitários ou departamentos internos da UFPE — que possuem demandas reais de soluções de software. Critérios de seleção:

- Problema com escopo viável para um semestre (MVP entregável)
- Disponibilidade para 7 sessões de interação com a equipe
- Compreensão de que o produto é desenvolvido por alunos em formação
- Compromisso com feedback construtivo e regular

### 9.3 Compromissos Mútuos

| Parte | Compromisso |
|-------|-------------|
| Equipe de alunos | Entregar MVP funcional, documentado e testado; comunicação profissional e regular; respeito a prazos |
| Stakeholder | Disponibilidade para 7 sessões; feedback honesto e construtivo; clareza na comunicação de necessidades |
| Professor | Mediação da relação; suporte técnico e pedagógico; garantia de que a extensão serve ao aprendizado |

### 9.4 Propriedade Intelectual

O código produzido é de propriedade compartilhada entre os alunos e a universidade, licenciado sob licença aberta (MIT ou similar), salvo acordo diferente com o stakeholder. Os alunos mantêm o direito de incluir o projeto em seus portfólios.

---

## 10. ADAPTAÇÃO DA SINFONIA PARA O CONTEXTO

| Aspecto | Sinfonia Original | Mini-Sinfonia (CIN0136) |
|---------|-------------------|--------------------------|
| Escopo | Produto de IA completo | Aplicação web com escopo calibrado para 2º período |
| Stakeholder | Equipe interna de produto | Demandante externo real (extensão) |
| Canvas de Estratégia e Ação | Completo (8+ campos) | Canvas de Visão simplificado (problema, persona, proposta de valor, escopo, riscos) |
| Canvas de Design de Experimento | Experimento com IA | Protótipo hi-fi + definição de MVP + hipótese de valor |
| Ciclos de desenvolvimento | Sprints Scrum completos | 4 sprints de ~2 semanas com reviews reais |
| Testes e validação | Canvas de Testes completo | Vitest (unitários) + Playwright (e2e) |
| Ressonância | Métricas de produção | Entrega formal + feedback real do stakeholder |
| Papéis | 8+ papéis especializados | 3–4 papéis genéricos por equipe |
| Linguagem de programação | TypeScript (foco IA/web) | JavaScript (ES6+), TypeScript opcional |

A vivência com a Mini-Sinfonia no 2º período cria familiaridade com o framework, que será aprofundado significativamente na ESAIA (IF1015, 6º período) com projetos de IA, Canvas completos e papéis especializados.

---

*Documento elaborado com base no Programa de Componente Curricular CIN0136, no livro "Engenharia de Software em Dimensões" (Garcia, 2025, ed. 2025.2.0), na Metodologia Sinfonia (Garcia & Medeiros, 2025), nas diretrizes do MEC para curricularização da extensão e em 13 anos de experiência na disciplina de Engenharia de Software no CIn-UFPE.*
