# Avaliação

**CIN0136: Desenvolvimento de Software · CIn-UFPE**

---

## Visão Geral

A nota final é composta por dois componentes obrigatórios — Projeto e Provas — mais um componente extra que pode elevar a nota acima da base.

| # | Componente | Peso | Natureza |
|---|-----------|------|---------|
| 1 | Participação, Exercícios Individuais e Missões | **+10%** *(extra)* | Individual · contínua + entregas pontuais |
| 2 | Projeto em Equipe | **60%** | Equipe · 5 checkpoints ao longo dos sprints |
| 3 | Provas (2 × 20%) | **40%** | Individual · 2 momentos formais |

> **Nota base:** Projeto (60%) + Provas (40%) = 100%.
> O componente extra soma sobre a nota base — quem acumular o bônus máximo não pode ultrapassar 10,0 (limite institucional).
> **Nota mínima para aprovação:** 7,0.
> **Frequência mínima:** 75% das aulas (conforme regulamento da UFPE).

---

## 1. Participação, Exercícios Individuais e Missões — +10% *(extra)*

Este componente é inteiramente adicional. Quem não entregar nada aqui ainda pode ser aprovado pelos outros dois. Quem se engajar ativamente ganha uma margem real sobre a nota base.

O componente reúne três tipos de contribuição:

### 1.1 Participação e debates

Engajamento nas leituras prévias e qualidade das contribuições nos debates em sala. Não é presença passiva — é a qualidade da participação: perguntas que aprofundam, discordâncias fundamentadas, conexões entre teoria e projeto.

| Nível | Descrição |
|-------|-----------|
| **Ausente / Passivo** | Não leu, não contribuiu ou contribuição irrelevante |
| **Presente** | Leu, acompanhou o debate, contribuiu quando provocado |
| **Ativo** | Leu criticamente, trouxe perspectiva própria, aprofundou o debate |

### 1.2 Exercícios Práticos Individuais (EI1–EI4)

Quatro entregas individuais ao longo do semestre, ancoradas nas fases do projeto. Enunciados completos em [`exercicios/`](../exercicios/):

| Exercício | Entrega | Tema |
|-----------|---------|------|
| [EI1 — Portfólio Git](../exercicios/EI1-portfolio-git.md) | Sprint 0 | Repositório com 10+ commits semânticos, branches, merge e reflexão |
| [EI2 — Documento de Requisitos](../exercicios/EI2-documento-requisitos.md) | Sprint 0 | 5 user stories com critérios de aceitação, MoSCoW justificado |
| [EI3 — Testes em JavaScript](../exercicios/EI3-testes-js.md) | Sprint 2 | Suite Vitest + Playwright em módulo com bugs intencionais |
| [EI4 — Reflexão Técnica e Profissional](../exercicios/EI4-reflexao-tecnica.md) | Sprint 4 | Documento reflexivo 2–3 páginas sobre decisões, stakeholder e trajetória |

> As datas exatas de entrega estão na planilha de plano de aulas do semestre corrente.

### 1.3 Missões

Ao longo do semestre o professor poderá lançar **missões** — desafios opcionais de curto prazo ligados ao tema da semana ou a oportunidades de aplicação extra. Cada missão é anunciada com pelo menos uma semana de antecedência e tem critérios de avaliação explícitos.

**Política de atrasos (EI e missões):** até 48h de atraso → desconto de 20%. Após 48h → não pontua.

---

## 2. Projeto em Equipe — 60%

O projeto é avaliado em dois blocos: os checkpoints incrementais ao longo dos sprints (que valem a maior parte) e a entrega final com apresentação acadêmica.

### 2.1 Checkpoints / Sprint Reviews

Cinco momentos formais de avaliação, cada um com o stakeholder presente. A equipe é avaliada como um todo — o feedback do parceiro integra a nota.

| Checkpoint | Peso no componente |
|-----------|--------------------|
| ✅ Review Sprint 0 | 10% |
| ✅ Review Sprint 1 | 20% |
| ✅ Review Sprint 2 | 25% |
| ✅ Review Sprint 3 | 25% |
| ✅ Review Sprint 4 | 20% |

> As datas de cada review estão na planilha de plano de aulas do semestre corrente.

**O que é avaliado em cada review:**

| Checkpoint | Foco da avaliação |
|-----------|-----------------|
| Sprint 0 | Backlog priorizado · protótipo hi-fi · escopo do MVP aprovado pelo stakeholder |
| Sprint 1 | Primeiras features funcionando · arquitetura documentada (C4, UML, ADR) · testes iniciais |
| Sprint 2 | Features core do MVP · testes de aceitação com Playwright |
| Sprint 3 | Qualidade aplicada · refactoring documentado · testes verdes |
| Sprint 4 | MVP estabilizado · documentação completa · deploy funcional |

**Rubrica por dimensão (aplicada a todos os reviews):**

| Dimensão | Peso | Critérios |
|----------|------|-----------|
| **Funcionalidade entregue** | 40% | As features prometidas estão funcionando? Os critérios de aceitação foram atendidos? |
| **Qualidade técnica** | 30% | O código tem testes? Os PRs passaram por review? Há dívida técnica não documentada? O Kanban reflete o trabalho real? |
| **Processo e colaboração** | 20% | Todos contribuíram? A retrospectiva foi feita e documentada? O próximo sprint foi planejado? |
| **Relação com o stakeholder** | 10% | A equipe veio preparada para a demo? O feedback foi registrado? A comunicação foi profissional? |

> O Review Sprint 0 não avalia código — avalia a qualidade da descoberta e a viabilidade do escopo definido.

### 2.2 Entrega Final + Apresentação Acadêmica

**Entrega formal ao stakeholder — fase de Encerramento**

A equipe entrega ao parceiro: repositório com código, deploy funcional, README completo e guia de uso. O stakeholder preenche o [Formulário de Feedback](../projeto/formulario-feedback-stakeholder.md), que integra a avaliação deste bloco.

**Apresentação acadêmica — fase de Encerramento**

12 minutos + 5 minutos de Q&A, seguindo a estrutura compartilhada pelos professores, que percorre o arco completo do projeto:

1. **O problema** — quem é o stakeholder, qual era a dor, por que valia a pena resolver
2. **As decisões** — o que foi descoberto antes de construir, as decisões de escopo e design
3. **A construção** — a arquitetura, o código, os testes, a evolução ao longo dos sprints
4. **Os aprendizados** — a entrega, o feedback real do stakeholder, o que faria diferente

**Rubrica da apresentação:**

| Critério | Peso | Descrição |
|----------|------|-----------|
| **Clareza narrativa** | 25% | A história do projeto é compreensível para quem não acompanhou? O arco está claro? |
| **Profundidade técnica** | 30% | As decisões técnicas são explicadas com fundamento? Os desafios são apresentados honestamente? |
| **Demonstração do produto** | 25% | O produto funciona ao vivo? A demo cobre os casos de uso principais? |
| **Reflexão sobre o impacto** | 20% | A equipe articula o que o produto mudou para o stakeholder? O que faria diferente? |

---

## 3. Provas — 40% (2 × 20%)

Duas provas escritas individuais, de consulta fechada, com questões abertas que privilegiam raciocínio e aplicação sobre memorização.

| Prova | Momento | Conteúdo |
|-------|---------|-----------|
| **Prova 1** | Sprint 2 (após o ciclo de arquitetura) | ES · Git · Code Review · Processos ágeis · Requisitos e User Stories · Princípios de design · C4 Model · Qualidade de software |
| **Prova 2** | Encerramento | Testes (Vitest e Playwright) · Refactoring · Manutenção · Dívida técnica · Qualidade arquitetural · Code review avançado · Documentação |

> As datas das provas estão na planilha de plano de aulas do semestre corrente.

**Prova Final e Segunda-chamada.** São mecanismos institucionais da UFPE, à parte da nota base descrita acima. A **Segunda-chamada** repõe uma prova perdida por motivo justificado; a **Prova Final** é a avaliação de recuperação para quem não atingir a nota mínima na média das avaliações. Nenhuma das duas entra na composição dos 40% — elas seguem o regulamento institucional. As datas constam na planilha de plano de aulas.

---

## 4. Política de Atrasos e Situações Excepcionais

| Entrega | Política |
|---------|---------|
| Exercícios individuais (EI) e missões | Até 48h de atraso → desconto de 20%. Após 48h → não pontua |
| Sprint Reviews | Sem reentrega — avaliação feita ao vivo na data marcada |
| Apresentação final | Datas fixas sem exceção (limitação de calendário acadêmico) |
| Situações excepcionais | Comunicar ao professor com antecedência; casos analisados individualmente |

---

## 5. Integridade Acadêmica

Todas as entregas estão sujeitas à política descrita no [Código de Conduta](codigo-conduta.md). O uso de IA é permitido como auxiliar — não como substituto da compreensão. Qualquer entrega em que o aluno não consiga explicar ao vivo o que foi produzido será considerada inválida.

---

*CIN0136 — Desenvolvimento de Software · CIn-UFPE*
