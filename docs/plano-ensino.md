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
| Containerização | Docker + Docker Compose | Paridade de ambiente; padrão de mercado; introduzido na Semana 14 |

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
│                         Semanas 1–6 (6 semanas)                        │
│                                                                         │
│  🎼 Sinfonia: EXPOSIÇÃO + COMPOSIÇÃO                                   │
│                                                                         │
│  Sem 1: Acolhimento + Processos ágeis (intro) + Backlog com stakeholder │
│  Sem 2: Processos ágeis (aprofundamento) + Refinamento do backlog       │
│  Sem 3: Requisitos formais + Validação do protótipo + Fechamento escopo │
│  Sem 4: Design e Arquitetura + Diagramas C4                             │
│  Sem 5: Git/GitHub + Setup do repositório do projeto real               │
│  Sem 6: PR/Code Review + Prototipagem com stakeholder                   │
│                                                                         │
│  → Entrega: Protótipo hi-fi validado + Backlog priorizado + Escopo     │
├─────────────────────────────────────────────────────────────────────────┤
│                  SPRINTS 1–4 — Construção Incremental                  │
│                       Semanas 7–14 (~2 sem/sprint)                     │
│                                                                         │
│  🎼 Sinfonia: ENSAIO                                                   │
│                                                                         │
│  Sprint 1 (Sem 7–8):  Qualidade + Setup técnico + Primeiras features   │
│  Sprint 2 (Sem 9–10): Testes + Features core do MVP                    │
│  Sprint 3 (Sem 11–12): Qualidade + Refactoring + Features complementar │
│  Sprint 4 (Sem 13–14): Refinamento + Code Review + Estabilização       │
│                                                                         │
│  → Cada sprint: Review com stakeholder na quinta da semana par          │
├─────────────────────────────────────────────────────────────────────────┤
│                    ENCERRAMENTO — Entrega e Reflexão                   │
│                        Semanas 14–15 (2 semanas)                       │
│                                                                         │
│  Sem 14: Containerização (Docker) + Entrega formal ao stakeholder       │
│  Sem 15: Apresentações acadêmicas + Retrospectiva + Encerramento       │
│                                                                         │
│  → Entrega: Produto funcional + Feedback + Reflexão individual          │
└─────────────────────────────────────────────────────────────────────────┘
```

### 2.1 Mapeamento Sinfonia → Semestre

| Movimento da Sinfonia | Fase do Semestre | Semanas | Artefato de Saída |
|----------------------|------------------|---------|-------------------|
| **Exposição** — Alinhar Estratégia | Sprint 0 (parte 1) | 1–3 | Canvas de Visão do Projeto (simplificado) |
| **Composição** — Desenhar a Solução | Sprint 0 (parte 2) | 3–5 | Protótipo hi-fi validado + Backlog priorizado |
| **Ensaio** — Construir e Testar | Sprints 1–4 | 6–13 | MVP funcional, testado e documentado |
| **Ressonância** — Medir e Aprender | Encerramento | 14–15 | Produto entregue ao stakeholder + Feedback formal + Documento de Reflexão individual |

### 2.2 Correspondência Ementa → Livro-Texto → Semanas

| Conteúdo Programático (Ementa) | Capítulo(s) do Livro | Semana(s) |
|-------------------------------|---------------------|-----------|
| Introdução ao gerenciamento de projetos | Cap. 1 — Engenharia de Software | 1 |
| Metodologias ágeis de desenvolvimento | Cap. 3 — Processos de Software | 2 |
| Intro à Engenharia de Requisitos ágil | Cap. 5 e Cap. 6 — Requisitos | 3 |
| Arquitetura de software e Modularização | Cap. 13 — Fundamentos de Arquitetura (seções selecionadas) | 4, 11 |
| Introdução ao controle de versão | Cap. 2 — Versionamento e Gerência de Configuração | 5–6 |
| Testes de software | Cap. 7 e Cap. 8 — Qualidade e Testes | 7–9 |
| Code Review | Cap. 2, seção 2.5 | 6, 12 |
| Refactoring | Cap. 18, seções 18.3–18.4 | 10, 12 |
| Containerização e deploy | Documentação oficial do Docker e Docker Compose | 14 |

---

## 3. CRONOGRAMA DETALHADO — SEMANA A SEMANA

> **Convenção de leitura:**
> - 🔵 **SEG** = Segunda-feira (2h, teórica — conceitos)
> - 🟢 **TER** = Terça-feira (2h, teórica — aprofundamento)
> - 🟠 **QUI** = Quinta-feira (4h, prática — consolidação e projeto)
> - 📖 = Leitura prévia obrigatória
> - 🎯 = Entregável da semana
> - 👤 = Momento de interação com stakeholder

---

## SPRINT 0 — DESCOBERTA E PREPARAÇÃO (Semanas 1–5)

### 🎼 Sinfonia: Exposição + Composição

> **Propósito:** Acolher, nivelar, formar equipes, conhecer o stakeholder, entender o problema, prototipar e fechar escopo. Os conceitos teóricos (ES, Git, processos, requisitos) são introduzidos **a serviço** do projeto desde o primeiro dia.

---

#### 📅 Semana 1 — Abertura: O que é desenvolver software? + Construção do Backlog

**🔵 SEG — O mundo além do código**

- 📖 Leitura prévia: Cap. 1, seções 1.1 a 1.3 (A Emergência de uma Disciplina; A Evolução dos Desafios e as Novas Crises do Software; Apresentando a PetFood)
- Dinâmica de apresentação: "Quem sou eu no contexto da tecnologia?"
- Discussão provocativa: "Qual é a diferença entre programar e desenvolver software?"
- Apresentação do plano de ensino, metodologia, contrato pedagógico e projeto de extensão
- Apresentação dos desafios/demandantes reais — visão geral dos projetos disponíveis

**🟢 TER — Ecossistema do desenvolvimento de software + Introdução à Sinfonia**

- 📖 Leitura prévia: Cap. 1, seções 1.4 a 1.7 (ES na Sociedade Contemporânea; O Valor Estratégico da ES; O Engenheiro de Software Moderno; Conclusão) + Sinfonia Cap. 2 (Visão Geral dos 4 Movimentos)
- Mapa mental coletivo: papéis, atividades e artefatos no desenvolvimento de software
- Apresentação da Mini-Sinfonia como framework do projeto do semestre
- Apresentação e assinatura do Código de Conduta e Ética
- Formação exploratória de equipes (4–5 integrantes) e alocação de stakeholders
- Debate com Questões Estruturantes do Cap. 1 (selecionar 2)

**🟠 QUI — Workshop Ágil + 👤 Construção do Backlog com Stakeholder (4h)**

- Bloco 1 (1.5h) — **Workshop Ágil:**
  - Atividade lúdica: "Construindo sem plano" (com LEGO ou equivalente digital) → repetir com mini-sprint estruturada → comparar
  - Configuração do quadro Kanban da equipe (GitHub Projects) com colunas: Backlog → To Do → In Progress → Review → Done
  - Planning poker simplificado: como estimar esforço
- Bloco 2 (2.5h) — **👤 Construção do backlog com stakeholder:**
  - 👤 Sessão com stakeholder: detalhar funcionalidades desejadas, priorizar juntos
  - Cada equipe transforma as conversas em itens de backlog (ainda informais — a formalização em user stories virá na Semana 3)
  - Priorização colaborativa: o que é mais urgente para o demandante? O que é mais viável para a equipe?
  - Definição dos papéis internos da equipe e acordos de trabalho
- 🎯 Quadro Kanban configurado + Backlog informal priorizado com stakeholder + Acordos de equipe
- Habilidades transversais: resolução de problemas, criatividade, negociação, trabalho em equipe

---

#### 📅 Semana 2 — Processos Ágeis

**🔵 SEG — Do caos ao processo: modelos de desenvolvimento de software**

- 📖 Leitura prévia: Cap. 3, seções 3.2 e 3.3 (A Sombra do Passado: O Modelo Cascata; Em Busca da Flexibilidade: Modelos Incremental e Iterativo)
- Modelos clássicos como respostas históricas a problemas de coordenação
- Debate: "O modelo cascata é realmente ruim ou apenas mal compreendido?"
- Análise: "Olhando para o nosso projeto real — o que já estamos fazendo que se parece com um processo?"

**🟢 TER — Metodologias ágeis: Scrum, Kanban e a escolha do processo**

- 📖 Leitura prévia: Cap. 3, seções 3.4 a 3.9 (A Revolução Ágil; Scrum: Ritmo e Foco; Kanban: Fluxo e Flexibilidade; Lean; Comparação; Critérios de escolha)
- Comparação prática: Scrum vs. Kanban — quando usar cada um?
- Debate com Questões Estruturantes do Cap. 3 (selecionar 2–3)
- Provocação: "Para o nosso projeto com stakeholder real, qual cadência faz mais sentido?"

**🟠 QUI — Consolidação Ágil + Refinamento do Backlog (4h)**

- Bloco 1 (1.5h) — **Consolidação Ágil:**
  - Revisão do quadro Kanban criado na Semana 1 — ajustes após a primeira semana de uso
  - Exercício: simulação de uma sprint planning com o backlog já levantado
  - Discussão: "O que descobrimos na construção do backlog que mudou nossa visão do processo?"
- Bloco 2 (2.5h) — **Refinamento do backlog:**
  - Revisão e consolidação dos itens de backlog levantados com o stakeholder na Semana 1
  - Primeira priorização colaborativa da equipe: o que entra no Sprint 0?
  - Definição de Definition of Done da equipe
  - Acordos de trabalho revistos com base no que aprenderam na primeira semana
- 🎯 Backlog refinado + Definition of Done + Sprint 0 planejado
- Habilidades transversais: colaboração, organização, negociação interna

---

#### 📅 Semana 3 — Requisitos + 👤 Validação e Fechamento de Escopo

**🔵 SEG — Requisitos funcionais, não funcionais e técnicas de elicitação**

- 📖 Leitura prévia: Cap. 5, seções 5.1 e 5.2 (Requisitos Funcionais e Não Funcionais; Técnicas de Elicitação em Profundidade)
- Exercício provocativo: "Descreva o que o WhatsApp faz" — observar como descrições divergem
- Distinção funcional vs. não funcional com exemplos concretos
- Técnicas de elicitação: entrevistas, workshops, observação, prototipagem
- Reflexão: "Quais técnicas já usamos com nosso stakeholder sem saber o nome delas?"

**🟢 TER — User Stories, backlog e priorização formal**

- 📖 Leitura prévia: Cap. 6, seções 6.1 a 6.4 (Da Descoberta à Especificação Ágil; User Stories: A Linguagem do Valor; Hierarquia do Backlog; Priorização; Refinamento Contínuo)
- Workshop: escrita de user stories no formato "Como [persona], quero [funcionalidade] para [benefício]"
- Critérios de qualidade (INVEST)
- Exercício de priorização com MoSCoW
- Debate com Questões Estruturantes do Cap. 6 (selecionar 2)

**🟠 QUI — 👤 Validação do Protótipo Hi-Fi + Fechamento de Escopo (4h)**

- 📖 Leitura prévia: Sinfonia — Cap. 4, seção 4.1 (Exposição) e Cap. 5, seção 5.1 (Composição)
- Bloco 1 (2h) — **Formalização:**
  - Cada equipe converte o backlog informal em user stories formais com critérios de aceitação
  - Priorização com MoSCoW do backlog completo
  - Preenchimento do Canvas de Visão do Projeto (versão simplificada do Canvas de Estratégia e Ação da Sinfonia)
  - Definição do MVP: "Se pudéssemos entregar apenas 3 funcionalidades, quais seriam?"
- Bloco 2 (2h) — **👤 Sessão de fechamento de escopo com stakeholder:**
  - Apresentação do protótipo hi-fi refinado
  - Apresentação do backlog priorizado e proposta de MVP
  - 👤 Stakeholder valida, ajusta, aprova o escopo
  - Registro formal: o que está dentro do MVP, o que fica para depois, o que mudou
- 🎯 Canvas de Visão + Backlog de user stories priorizado com MoSCoW + Protótipo hi-fi validado + Escopo fechado e assinado com stakeholder
- **Exercício Individual 2 — "Documento de Requisitos":** dado um sistema fictício, o aluno deve: (1) listar requisitos funcionais e não funcionais, (2) escrever 8 user stories com critérios de aceitação, (3) priorizar com MoSCoW, (4) identificar os 3 atributos de qualidade mais críticos e justificar (entrega até domingo)
- **✅ Review do Sprint 0:** Canvas de Visão + Backlog priorizado + Protótipo validado + Escopo fechado

---

#### 📅 Semana 4 — Princípios de Design e Arquitetura

**🔵 SEG — Por que a organização do código importa**

- 📖 Leitura prévia: Cap. 13, seções 13.1 e 13.3 (O Que é Arquitetura de Software; Princípios Fundamentais de Design de Código — SOLID, DRY, KISS)
- Exercício provocativo: dois códigos JavaScript que fazem a mesma coisa — um bem organizado, outro caótico. "Qual vocês preferem manter?"
- Princípios acessíveis para 2º período: separação de responsabilidades, coesão, acoplamento, abstração, nomes significativos
- Conexão com o projeto: "Como organizaremos nosso código para que 4 pessoas trabalhem sem pisar no pé uma da outra?"

**🟢 TER — C4 Model: desenhando a arquitetura do nosso projeto**

- 📖 Leitura prévia: Cap. 13, seção 13.5 (Comunicando a Arquitetura: O Poder do C4 Model — seções 13.5.1 O C4 Model como Ferramenta de Storytelling; 13.5.2 O Papel Complementar da UML)
- Demonstração: diagramas de Contexto (Nível 1) e Contêiner (Nível 2) para um sistema semelhante aos projetos das equipes
- Discussão: "Por que documentamos a arquitetura se ela pode mudar?"
- Ferramenta: Mermaid (integra com GitHub) ou draw.io

**🟠 QUI — Workshop de Arquitetura (4h)**

- Bloco 1 (2h) — **Workshop de Arquitetura:**
  - Cada equipe desenha os diagramas C4 do seu projeto: Contexto (Nível 1), Contêiner (Nível 2), Componentes (Nível 3 do módulo principal)
  - Definição da estrutura de pastas e módulos do projeto (backend: rotas, controllers, services, models; frontend: pages, components, hooks, services)
  - Decisões arquiteturais documentadas: "Escolhemos X porque..."
- Bloco 2 (2h) — **Aplicação no contexto do projeto:**
  - Discussão em equipe: como a arquitetura desenhada se conecta ao backlog e ao escopo fechado?
  - Refinamento dos diagramas com base no feedback entre equipes
  - Preparação para o setup técnico que virá na Semana 5
- 🎯 Diagramas C4 da equipe (Níveis 1, 2 e 3) + Decisões arquiteturais documentadas
- Habilidades transversais: pensamento sistêmico, comunicação técnica, tomada de decisão

---

#### 📅 Semana 5 — Git e GitHub: Trabalhando juntos no mesmo código

**🔵 SEG — Por que versionar? Fundamentos de Git**

- 📖 Leitura prévia: Cap. 2, seções 2.1 a 2.3 (O Desafio Inicial: Dois Desenvolvedores; A Escolha da Ferramenta: Centralizado vs. Distribuído; Os Primeiros Passos: Commit, Branch e Merge na Prática)
- Debate: "Você já perdeu código? Já teve medo de alterar algo que funcionava?"
- Demonstração ao vivo: ciclo básico do Git (init, add, commit, log, diff, status)
- Modelo mental: working directory → staging area → repository

**🟢 TER — Branches, merges e estratégias de colaboração**

- 📖 Leitura prévia: Cap. 2, seção 2.4 (Organizando o Caos: Git Flow; Trunk-Based Development; Feature Branching; Mantendo um Histórico Limpo — Merge vs. Rebase)
- Análise comparativa das estratégias para diferentes cenários
- Discussão: "Qual estratégia faz sentido para o nosso projeto de extensão?"
- Simulação conceitual de conflito de merge

**🟠 QUI — Laboratório Git + Setup do Repositório do Projeto Real (4h)**

- Bloco 1 (2h) — **Laboratório Git:**
  - Exercício individual: criar repositório JS, fazer 10 commits semânticos, criar e mesclar branches, navegar pelo histórico
  - Exercício em duplas: repositório compartilhado, feature branches, merge, simulação e resolução de conflitos — repetir até ficar natural
- Bloco 2 (2h) — **Setup do projeto real:**
  - Criação do repositório da equipe no GitHub: README estruturado, .gitignore (Node.js), licença, branch protection rules, template de PR
  - Scaffolding do projeto: `npm init`, estrutura de pastas (src/, tests/, docs/), configuração de ESLint + Prettier
  - Setup inicial do backend (Express) e frontend (Vite + React) — boilerplate funcional, já refletindo a arquitetura desenhada na Semana 4
  - Cada membro faz um commit inaugural no projeto real
- 🎯 Repositório individual (10+ commits) + Repositório do projeto real configurado e funcional (Hello World full-stack)
- **Exercício Individual 1 — "Meu portfólio Git":** repositório pessoal JavaScript com projeto organizado, commits semânticos, branches com propósito, README completo, e pelo menos 1 PR com self-review documentado (entrega até domingo)
- Habilidades transversais: colaboração, resolução de problemas, disciplina técnica

---

## SPRINTS 1–4 — CONSTRUÇÃO INCREMENTAL (Semanas 7–14)

### 🎼 Sinfonia: Ensaio — Construir e Testar

> **Propósito:** Construção incremental do MVP em 4 sprints de ~2 semanas cada. A teoria de cada quinzena é calibrada para o que a equipe precisa naquele momento do projeto. Sprint reviews com stakeholder acontecem na quinta-feira da semana par de cada sprint.

---

### 🏃 SPRINT 1 — Primeiras Funcionalidades (Semanas 7–8)

> **Foco técnico:** Qualidade de software, primeiras features sobre a arquitetura já definida no Sprint 0.

#### 📅 Semana 6 — Code Review + 👤 Prototipagem com Stakeholder

**🔵 SEG — Pull Requests e Code Review: mais que revisão técnica**

- 📖 Leitura prévia: Cap. 2, seção 2.5 (O Ritual da Qualidade: O Primeiro Pull Request — A Validação Colaborativa via Code Review; A Automação como Aliada)
- Demonstração: anatomia de um PR no GitHub (título, descrição, diff, comentários, aprovação)
- Discussão: "O que distingue um bom comentário de code review de um inútil?"
- Apresentação da rubrica de code review da disciplina

**🟢 TER — Propriedade intelectual, licenças e ética no desenvolvimento**

- 📖 Leitura prévia: Cap. 2, seções 2.6 e 2.7 (Benefícios da Gestão de Configuração na Prática; Conclusão: O Alicerce da Colaboração)
- Debate: "Quem é dono do código que vocês escreverão para o stakeholder? E se usarem código gerado por IA?"
- Licenças de software (MIT, GPL, Apache) e implicações para o projeto de extensão
- Questões éticas: plágio, atribuição, contribuições open source, responsabilidade com o demandante

**🟠 QUI — Laboratório Code Review + 👤 Prototipagem com Stakeholder (4h)**

- Bloco 1 (1.5h) — **Laboratório de Code Review:**
  - Exercício formal em duplas: abrir PR → revisar com checklist → solicitar mudanças → corrigir → aprovar → merge
  - Repetir com nova dupla para consolidar
- Bloco 2 (2.5h) — **👤 Composição: Prototipagem com o stakeholder:**
  - Mini-workshop de prototipagem rápida: sketches em papel → wireframes digitais (Figma free, Excalidraw ou similar)
  - Cada equipe constrói protótipos low-fi/mid-fi das telas principais com base no que aprendeu com o stakeholder
  - 👤 Sessão de validação com stakeholder: apresentar protótipos, coletar feedback direto, iterar ao vivo
  - Registrar: o que o stakeholder aprovou, o que pediu para mudar, o que gerou dúvida
- 🎯 4 PRs (2 abertos + 2 revisados) + Protótipos validados pelo stakeholder + Registro de feedback
- **✅ Review do Sprint 0:** Canvas de Visão + Backlog priorizado + Protótipo validado + Arquitetura definida + Escopo fechado
- Habilidades transversais: comunicação construtiva, feedback, empatia, propriedade intelectual

---

#### 📅 Semana 7 — Qualidade de Software + Início do Desenvolvimento

**🔵 SEG — O que é qualidade de software? (Não é só "funcionar")**

- 📖 Leitura prévia: Cap. 7, seções 7.1 e 7.2 (Os Atributos da Qualidade: Adequação Funcional, Usabilidade, Eficiência de Desempenho, Confiabilidade, Segurança, Manutenibilidade, Portabilidade; O Campo de Batalha dos Trade-offs)
- Atividade: classificar softwares conhecidos de 1 a 5 em qualidade — observar divergência de critérios
- Para cada atributo, identificação no projeto: "Qual é o mais crítico para o nosso stakeholder?"
- Debate com Questões Estruturantes do Cap. 7 (selecionar 2)

**🟢 TER — Medição de qualidade e cultura de qualidade contínua**

- 📖 Leitura prévia: Cap. 7, seções 7.3 a 7.5 (Anatomia da Dívida Técnica; Estratégias de Gerenciamento; Da Medição à Ação: Qualidade de Código, Análise Estática, Monitoramento, Cultura da Qualidade)
- Debate: "Qualidade custa caro? Ou a falta de qualidade custa mais?"
- Conexão com o stakeholder: "Quando entregarmos o produto, como o demandante saberá se tem qualidade?"
- Preparação para o início do desenvolvimento: critérios de qualidade que guiarão o Sprint 1

**🟠 QUI — Início do Desenvolvimento Sprint 1 (4h)**

- Bloco 1 (2h) — **Setup técnico e scaffold:**
  - Implementação do scaffold arquitetural real no repositório (com base nos diagramas C4 da Semana 4)
  - Divisão de tarefas: cada membro assume features do Sprint 1
  - Pair programming guiado — professor circula entre equipes
- Bloco 2 (2h) — **Desenvolvimento:**
  - Primeiros PRs com features reais
  - Aplicação dos critérios de qualidade discutidos nas aulas teóricas
  - Revisão de PRs entre pares usando a rubrica da disciplina
- 🎯 Scaffold arquitetural no repositório + Primeiras features em desenvolvimento + PRs abertos

---

### 🏃 SPRINT 2 — Testes + Features Core do MVP (Semanas 9–10)

> **Foco técnico:** Fundamentos de testes, pirâmide de testes, testes de unidade com Vitest, testes de aceitação.

#### 📅 Semana 8 — Fundamentos do Teste de Software + Sprint 1 Review

**🔵 SEG — Por que testar? Tipos de teste e a pirâmide**

- 📖 Leitura prévia: Cap. 8, seções 8.1 e 8.2 (A Evolução Histórica dos Testes; A Pirâmide de Testes Moderna — Unidade, Integração, Sistema/E2E, Aceitação)
- Analogia: "Você faria cirurgia com um médico que nunca treinou?"
- Pirâmide de testes: o que testar em cada nível e por quê
- Demonstração ao vivo: primeiro teste com Vitest em um módulo Node.js/Express

**🟢 TER — Cobertura, edge cases e estratégias de teste**

- 📖 Leitura prévia: Cap. 8, seções 8.3 a 8.6 (Técnicas Caixa-Preta e Caixa-Branca; Teste Exploratório; Estratégias de Cobertura; Desafios e Vantagens dos Testes)
- Discussão: "100% de cobertura significa 100% de qualidade? Por que não?"
- Exercício: "Encontre os bugs!" — código JavaScript com falhas sutis que bons testes revelariam
- Testes de aceitação: formato Dado-Quando-Então e conexão com user stories
- Debate com Questões Estruturantes do Cap. 8 (selecionar 2)

**🟠 QUI — Desenvolvimento + 👤 Sprint 1 Review com Stakeholder (4h)**

- Bloco 1 (2h) — **Desenvolvimento:**
  - Finalização das features do Sprint 1
  - Merge dos PRs pendentes, resolução de conflitos
  - Preparação da demo para o stakeholder
- Bloco 2 (2h) — **👤 Sprint 1 Review:**
  - Cada equipe demonstra ao stakeholder o que foi construído (10 min demo + 5 min feedback)
  - Stakeholder valida, sugere ajustes, prioriza próximos passos
  - Retrospectiva interna da equipe: "O que funcionou? O que precisamos melhorar?"
  - Planejamento do Sprint 2: ajuste do backlog com base no feedback
- 🎯 Features do Sprint 1 entregues + Feedback do stakeholder registrado + Retrospectiva documentada
- **✅ Sprint 1 Review:** Funcionalidades demonstradas + Diagramas C4 + Retrospectiva

---

#### 📅 Semana 9 — Testes de Aceitação + Laboratório de Testes

**🔵 SEG — Testes de aceitação e a perspectiva do usuário**

- 📖 Leitura prévia: Cap. 8, seção 8.2.5 (Além da Pirâmide: Testes de Aceitação) + revisitar Cap. 6 (User Stories — critérios de aceitação)
- Conexão: "User stories definem o que deve ser feito; testes de aceitação verificam se foi feito"
- Demonstração: Playwright para testes e2e de uma feature React
- Exercício: transformar 3 user stories em cenários de teste automatizado

**🟢 TER — Relação do profissional com a sociedade e a cultura digital**

- 📖 Leitura prévia: material complementar sobre ética em software, impacto social, viés
- Debate: "Software é neutro?" — estudo de caso sobre decisões técnicas com consequências sociais
- Reflexão: "O projeto que estamos construindo para o stakeholder poderia gerar impacto negativo não intencional?"
- Conexão com a extensão: responsabilidade social do desenvolvedor que constrói para a comunidade

**🟠 QUI — Laboratório de Testes + Desenvolvimento Sprint 2 (4h)**

- Bloco 1 (2h) — **Laboratório de Testes:**
  - Setup de Vitest no projeto real
  - Workshop progressivo: (1) testar uma função pura, (2) testar com edge cases, (3) testar uma rota Express com supertest, (4) gerar e interpretar relatório de cobertura
  - Pair testing: um escreve código, outro escreve teste
- Bloco 2 (2h) — **Desenvolvimento Sprint 2:**
  - Implementação das features core do MVP
  - Regra a partir de agora: **nenhuma feature é considerada "pronta" sem pelo menos 1 teste**
  - Professor circula com foco em qualidade de testes
- 🎯 Vitest configurado no projeto + Mínimo 10 testes no repositório + Features do Sprint 2 em progresso

---

### 🏃 SPRINT 3 — Qualidade + Refactoring (Semanas 11–12)

> **Foco técnico:** Refactoring, code smells, manutenção de software, melhoria contínua.

#### 📅 Semana 10 — Refactoring: Melhorar sem Quebrar + Sprint 2 Review

**🔵 SEG — Refactoring: o que é, por que fazer, como fazer com segurança**

- 📖 Leitura prévia: Cap. 18, seções 18.3 e 18.3.2 (A Dívida Técnica Volta a Atacar; O Legado Moderno; Refatoração Contínua: O Antídoto Contra a Entropia)
- Demonstração ao vivo em JavaScript: renomear variáveis, extrair funções, simplificar condicionais, eliminar duplicação
- Catálogo simplificado de "code smells" e refatorações correspondentes
- Regra de ouro: "Refactoring sem testes é andar no escuro"

**🟢 TER — Manutenção, evolução e dívida técnica**

- 📖 Leitura prévia: Cap. 18, seções 18.1 e 18.2 (O Fim da Lua de Mel: As Leis de Lehman; As Duas Leis da Arquitetura na Prática; As Quatro Faces da Manutenção)
- Discussão: "Software nunca está 'pronto'. O que acontece depois que entregamos ao stakeholder?"
- Tipos de manutenção: corretiva, adaptativa, evolutiva, preventiva
- Debate: "Se arquitetura ruim leva a software ruim, por que empresas acumulam dívida técnica?"
- Reflexão: "Olhando para o código que escrevemos até agora — onde está nossa dívida técnica?"

**🟠 QUI — Desenvolvimento + 👤 Sprint 2 Review com Stakeholder (4h)**

- Bloco 1 (2h) — **Desenvolvimento:**
  - Finalização das features core do Sprint 2
  - Implementação de testes de aceitação para as funcionalidades principais (mínimo 3 cenários Playwright)
  - Merge, resolução de conflitos, preparação da demo
- Bloco 2 (2h) — **👤 Sprint 2 Review:**
  - Demo ao stakeholder (10 min + 5 min feedback)
  - Foco: funcionalidades core do MVP estão de acordo com as expectativas?
  - Retrospectiva interna + planejamento do Sprint 3
- 🎯 Features core entregues e testadas + 3 testes e2e + Feedback do stakeholder + Retrospectiva
- **Exercício Individual 3 — "Testes em JavaScript":** dado um módulo Node.js/Express fornecido pelo professor: (1) escrever testes de unidade com Vitest, (2) escrever testes de aceitação, (3) gerar relatório de cobertura, (4) análise crítica dos resultados (entrega até domingo)
- **✅ Sprint 2 Review:** Features core + Testes (unitários e aceitação) + Retrospectiva

---

#### 📅 Semana 11 — Qualidade Arquitetural + Laboratório de Refactoring

**🔵 SEG — O impacto das decisões de design na qualidade do software**

- 📖 Leitura prévia: Cap. 13, seções 13.3 e 13.4 (Princípios SOLID; Filosofias DRY/KISS/YAGNI; Estilos Arquiteturais como Respostas a Trade-offs)
- Estudo de caso simplificado: cenário de decisão arquitetural e suas consequências
- Conexão com o projeto: "As decisões que tomamos na Semana 4 — qual impacto tiveram?"
- Debate com Questões Estruturantes do Cap. 13 (selecionar 2)

**🟢 TER — Debugging, robustez e preparação para a Sprint Review**

- Técnicas de debugging em JavaScript (breakpoints no VS Code, console.log estratégico, leitura de stack traces)
- Exercício rápido: "Encontre e corrija os 5 bugs" em código Node.js fornecido
- Tratamento de erros elegante: try/catch, error boundaries em React, respostas HTTP apropriadas
- Preparação para Sprint 3 Review: o que mostrar, como demonstrar evolução da qualidade

**🟠 QUI — Laboratório de Refactoring + Desenvolvimento Sprint 3 (4h)**

- Bloco 1 (2h) — **Laboratório de Refactoring:**
  - Exercício prático: dado um código JavaScript "smelly", aplicar 5 refatorações progressivas garantindo que testes continuam passando a cada passo
  - Pair refactoring: um navega, outro executa
  - Aplicação no projeto real: cada equipe identifica os 3 piores trechos do seu código e planeja refatorações
- Bloco 2 (2h) — **Desenvolvimento Sprint 3:**
  - Execução das refatorações planejadas no projeto
  - Implementação de features complementares
  - Verificação: todos os testes continuam verdes após cada refactoring
- 🎯 Exercício de refactoring completo + Refatorações aplicadas ao projeto (com testes verdes) + Features complementares em progresso

---

### 🏃 SPRINT 4 — Refinamento + Estabilização (Semanas 13–14)

> **Foco técnico:** Code review cruzado, estabilização, documentação, preparação para entrega final ao stakeholder.

#### 📅 Semana 12 — Code Review Cruzado + Sprint 3 Review

**🔵 SEG — Code Review como prática profissional (revisitado)**

- 📖 Leitura prévia: revisitar Cap. 2, seção 2.5 (O Ritual da Qualidade: Validação Colaborativa via Code Review) + Cap. 13, seção 13.5.1 (O C4 Model como Ferramenta de Storytelling — documentação arquitetural)
- Revisitar code review agora com maturidade: o que mudou desde a Semana 6?
- Checklist de qualidade avançado: legibilidade, testes, organização, tratamento de erros, convenções, documentação
- Discussão: "Vocês gostariam de manter o código que outra equipe escreveu?"

**🟢 TER — Documentação, README e preparação do produto para entrega**

- 📖 Leitura prévia: Cap. 18, seção 18.4 (Rumo a um Juramento: Leis Universais para a Engenharia de Software; Princípios para um Software Resiliente)
- O que documentar e para quem: README, guia de instalação, decisões arquiteturais
- Discussão: "Se vocês fossem embora amanhã, outra equipe conseguiria continuar o projeto?"
- Checklist de entrega: código limpo, testes passando, README completo, diagramas C4 atualizados

**🟠 QUI — 👤 Sprint 3 Review com Stakeholder + Retrospectiva (4h)**

- Bloco 1 (2h) — **Finalização e preparação:**
  - Garantir testes passando, features complementares completas, demonstração funcional
  - Code review cruzado rápido entre equipes como aquecimento
- Bloco 2 (2h) — **👤 Sprint 3 Review:**
  - Demo ao stakeholder (10 min + 5 min feedback)
  - Foco: qualidade perceptível — o produto está estável? A UX melhorou?
  - Discussão com stakeholder sobre prioridades finais do Sprint 4
  - Retrospectiva + planejamento do Sprint 4 (último sprint de desenvolvimento)
- 🎯 Features complementares + Refactoring aplicado + Feedback do stakeholder + Retrospectiva
- **✅ Sprint 3 Review:** Código refatorado + Qualidade evidenciada + Retrospectiva

---

#### 📅 Semana 13 — Estabilização + Code Review Cruzado Final

**🔵 SEG — Reflexão: da ideia ao produto — a jornada do Ensaio**

- Reflexão guiada: revisitar a jornada desde a Semana 1. O que sabíamos? O que aprendemos?
- Análise honesta: quais decisões foram boas? Quais refariamos diferente?
- Dívida técnica restante: o que não deu tempo de melhorar?
- Preparação emocional e técnica para a entrega ao stakeholder

**🟢 TER — Preparação para as apresentações e entrega final**

- Workshop: "Como demonstrar software de forma convincente"
- Estrutura da apresentação seguindo os 4 movimentos da Mini-Sinfonia: o que entendemos do problema (Exposição), como projetamos (Composição), como construímos e testamos (Ensaio), o que aprendemos (Ressonância)
- Ensaio rápido: cada equipe pratica (3 min) com feedback do professor

**🟠 QUI — Code Review Cruzado Final + Estabilização (4h)**

- Bloco 1 (2h) — **Code Review Cruzado formal:**
  - Cada equipe abre um PR com sua funcionalidade principal
  - Outra equipe realiza a revisão seguindo checklist avançado
  - Discussão pós-review: "Como foi dar e receber feedback de outra equipe?"
  - Incorporação do feedback recebido
- Bloco 2 (2h) — **Estabilização final:**
  - Correção dos pontos levantados no code review
  - Bug fixes, ajustes de UX, melhoria de mensagens de erro
  - Atualização de documentação (README, diagramas C4, guia de instalação)
  - Garantir: deploy funcional, demo sem surpresas
- 🎯 Code review cruzado completo + Feedback incorporado + Documentação atualizada + MVP estabilizado
- **Exercício Individual 4 — "Reflexão Técnica e Profissional":** análise crítica do próprio projeto: (1) decisões de design — quais foram boas, quais refaria, (2) dívidas técnicas identificadas, (3) o que aprendeu trabalhando com stakeholder real, (4) autoavaliação honesta da contribuição individual (entrega até domingo)
- Habilidades transversais: comunicação construtiva, humildade intelectual, profissionalismo

---

## ENCERRAMENTO — ENTREGA E REFLEXÃO (Semanas 14–15)

> **Propósito:** Entregar formalmente o produto ao stakeholder, refletir sobre a jornada completa e apresentar academicamente o trabalho realizado no semestre.

---

#### 📅 Semana 14 — Containerização com Docker + 👤 Entrega Formal ao Stakeholder

**🔵 SEG — Do código ao container: introdução ao Docker**

- Sem leitura prévia — traga o repositório do projeto acessível
- O problema "na minha máquina funciona": raiz técnica e por que Docker resolve
- Conceitos fundamentais: imagem vs. container (analogia receita/bolo)
- Anatomia do Dockerfile: `FROM`, `WORKDIR`, `COPY`, `RUN`, `EXPOSE`, `CMD`
- Dockerfile do backend PetFood (Node.js/Express): estratégia de cache de camadas e `npm ci --omit=dev`
- Multi-stage build para o frontend React: Node compila, nginx serve, imagem final < 30MB
- O arquivo `.dockerignore` e por que `node_modules` nunca deve entrar na imagem
- Ciclo de vida básico: `docker build`, `docker run`, `docker ps`, `docker logs`, `docker stop`
- Demonstração ao vivo com rebuild para evidenciar o funcionamento do cache de camadas
- *Referência: documentação oficial do Docker — nenhum dos livros-texto cobre este tema diretamente*

**🟢 TER — Orquestrando serviços com Docker Compose**

- Sem leitura prévia — revisar mentalmente os conceitos de Docker da aula de segunda
- O limite do Docker isolado para sistemas com múltiplos serviços
- Anatomia do `docker-compose.yml`: `services`, `image`, `build`, `ports`, `expose`, `environment`, `depends_on`, `volumes`
- DNS interno do Compose: nome do serviço como hostname — o que muda na `DATABASE_URL`
- `docker-compose.yml` completo e comentado para o sistema PetFood (React/nginx + Express + PostgreSQL)
- `expose` vs. `ports`: banco de dados nunca exposto diretamente ao host
- Volumes nomeados e persistência de dados: diferença entre `stop`, `down` e `down -v`
- Padrão `.env` + `.env.example` para credenciais — nunca commitar segredos
- Conexão com plataformas de deploy (Railway, Render): o que acontece por baixo dos panos
- Reflexão: `docker-compose.yml` como documentação executável vs. README
- *Referência: documentação oficial do Docker Compose — nenhum dos livros-texto cobre este tema diretamente*

**🟠 QUI — 👤 Entrega Formal ao Stakeholder (4h)**

- Bloco 0 (15 min) — **Abertura coletiva com todos os stakeholders presentes:**
  - Enquadramento do evento: entrega real para pessoas reais, sem slides
  - Critério de sucesso explícito: "o stakeholder consegue usar o que foi construído?"
- Bloco 1 (2h) — **Rodada de entregas em formato feira:**
  - Cada equipe em sua estação — laptop aberto, deploy funcionando
  - Stakeholders circulam; cada um recebe da sua equipe: demo (15 min) + preenchimento do formulário de feedback em silêncio (10 min) + entrega formal dos artefatos: link do repositório, deploy, README, guia de uso (5 min)
- Bloco 2 (45 min) — **Plenária de encerramento:**
  - Cada equipe compartilha em 2 minutos uma frase que o stakeholder disse que não esperavam ouvir
  - Professor observa padrões no conjunto das respostas
- Bloco 3 (até 45 min) — **Fala de encerramento + buffer:**
  - Nomeação da transformação vivida: de programadores a desenvolvedores de software
  - Conexão com o que vem a seguir: fundamentos como base para amplificação com IA
  - Buffer para conversas, celebração e encerramento natural
- 🎯 Produto entregue ao stakeholder + Formulário de feedback preenchido pelo stakeholder + Artefatos formais entregues (repositório, deploy, README, guia de uso)
- **✅ Encerramento do Projeto de Extensão**

---

#### 📅 Semana 15 — Apresentações Acadêmicas + Encerramento

**🔵 SEG — Apresentações Acadêmicas — Bloco 1**

- Apresentações formais (12 min + 5 min Q&A por equipe)
- Estrutura narrativa obrigatória — quatro perguntas em sequência:
  1. **O problema:** quem é o stakeholder, qual era a dor, por que valia a pena resolver
  2. **Como pensamos:** o que foi descoberto antes de construir, decisões de escopo e design
  3. **O que construímos:** demo do produto, decisões técnicas relevantes, o que ficou fora do MVP
  4. **O que aprendemos:** o que faria diferente, o que a experiência ensinou que nenhuma aula ensina
- Peer evaluation formativa (formulário estruturado — não conta na nota)

**🟢 TER — Apresentações Acadêmicas — Bloco 2**

- Continuação das apresentações com a mesma estrutura e critérios do Bloco 1
- Peer evaluation formativa

**🟠 QUI — Retrospectiva Final + Encerramento (4h)**

- Bloco 1 (2h) — **Retrospectiva coletiva:**
  - Atividade: "O que sabemos agora que não sabíamos na Aula 1?" — reflexão individual escrita, compartilhamento em grupos, plenária
  - Destaques do semestre escolhidos por pares
  - Conexão com o que vem a seguir: ESAIA (IF1015), estágio, primeiro emprego
- Bloco 2 (2h) — **Finalizações e encerramento:**
  - Documento de Reflexão individual (2–3 páginas): jornada pessoal, aprendizados técnicos e transversais, o que a extensão significou, autoavaliação honesta
  - Survey de feedback sobre a disciplina
  - Encerramento: palavras finais, celebração
- 🎯 **✅ Checkpoint Final:** MVP no repositório (código, testes, documentação, diagramas C4) + Apresentação acadêmica + Feedback do stakeholder + Documento de Reflexão individual

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

O stakeholder participa de **7 momentos formais** ao longo do semestre, garantindo que o projeto nunca se distancie das necessidades reais:

| Semana | Momento | Propósito |
|--------|---------|-----------|
| 1 | Backlog | Entender contexto, problema e priorizar funcionalidades juntos |
| 3 | Fechamento de escopo | Validar protótipo hi-fi, aprovar MVP |
| 6 | Prototipagem | Validar wireframes e fluxos iniciais |
| 8 | Sprint 1 Review | Validar primeiras funcionalidades |
| 10 | Sprint 2 Review | Validar features core do MVP |
| 12 | Sprint 3 Review | Validar qualidade e ajustes |
| 14 | Sprint 4 Review + Entrega formal | Validação final + entrega do produto + feedback estruturado |

---

## 6. INTEGRAÇÃO DAS HABILIDADES TRANSVERSAIS

| Habilidade Transversal | Práticas que a Desenvolvem | Momentos-Chave |
|------------------------|---------------------------|----------------|
| Mentalidade de resolução de problemas | Exercícios progressivos, debugging, sprints, problemas reais do stakeholder | Semanas 1, 8, 11, 12 |
| Criatividade | Prototipagem, Canvas de Visão, brainstorming, design de soluções | Semanas 3, 4, 6 |
| Trabalho em equipe | Projeto real em grupo (14 semanas), papéis, retrospectivas, sprints | Semanas 2–15 |
| Habilidades interpessoais | 7 sessões com stakeholder real, code reviews, apresentações, feedback | Semanas 1, 3, 6, 8, 10, 12, 14 |
| Relação com a sociedade e cultura digital | Debate sobre impacto social, viés, IA, extensão com impacto comunitário | Semanas 3, 9, 14 |
| Ética | Código de Conduta, licenças, responsabilidade com demandante, IA e autoria | Semanas 1, 6, 9 |
| Propriedade intelectual | Licenças, atribuição, código gerado por IA, acordo com stakeholder | Semana 6 |

---

## 7. RECURSOS E BIBLIOGRAFIA

### 7.1 Bibliografia Básica

1. **GARCIA, V. C.** *Engenharia de Software em Dimensões: Da base conceitual à prática profissional.* ASSERT Lab, 2025. Versão 2025.2.0. ISBN 978-65-01-62882-0. **(Livro-texto principal — 18 capítulos)**
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
| Node.js 20+ | Runtime JavaScript | Semana 5 |
| Express | Framework backend | Semana 5 |
| React (via Vite) | Framework frontend | Semana 5 |
| Vitest | Testes unitários | Semana 9 |
| Playwright | Testes e2e/aceitação | Semana 10 |
| ESLint + Prettier | Linter e formatter | Semana 5 |
| Git / GitHub | Versionamento e colaboração | Semana 5 |
| GitHub Projects | Gestão de projeto (Kanban) | Semana 1 |
| VS Code | IDE | Semana 5 |
| Mermaid / draw.io | Diagramas C4 | Semana 4 |
| Figma / Excalidraw | Prototipagem | Semana 6 |
| Vercel / Render / Railway | Deploy | Semana 7+ |
| Docker + Docker Compose | Containerização e orquestração local | Semana 14 |
| SQLite / PostgreSQL | Banco de dados | Conforme necessidade |

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
| Ressonância | Métricas de produção | Entrega formal em formato feira + feedback do stakeholder por formulário estruturado |
| Papéis | 8+ papéis especializados | 3–4 papéis genéricos por equipe |
| Linguagem de programação | TypeScript (foco IA/web) | JavaScript (ES6+), TypeScript opcional |

A vivência com a Mini-Sinfonia no 2º período cria familiaridade com o framework, que será aprofundado significativamente na ESAIA (IF1015, 6º período) com projetos de IA, Canvas completos e papéis especializados.

---

*Documento elaborado com base no Programa de Componente Curricular CIN0136, no livro "Engenharia de Software em Dimensões" (Garcia, 2025), na Metodologia Sinfonia (Garcia & Medeiros, 2025), nas diretrizes do MEC para curricularização da extensão e em 13 anos de experiência na disciplina de Engenharia de Software no CIn-UFPE.*

*v7 — 11/06/2026: Semana 14 remodelada. Aulas de segunda e terça substituídas por conteúdo de containerização (Docker e Docker Compose), com estudo de caso ancorado no sistema PetFood. Justificativa: conteúdo de formação profissional essencial, aproveitando o espaço pós-Sprint 4 sem competir com entregas. Docker e Docker Compose adicionados à stack tecnológica e à tabela de correspondência ementa→semanas.*
