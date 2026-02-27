# Avaliação

**CIN0136: Desenvolvimento de Software · CIn-UFPE · 2026.1**

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

Quatro entregas individuais ao longo do semestre. Enunciados completos em [`exercicios/`](../exercicios/):

| Exercício | Entrega | Tema |
|-----------|---------|------|
| [EI1 — Portfólio Git](../exercicios/EI1-portfolio-git.md) | 29/03 (Dom) | Repositório com 10+ commits semânticos, branches, merge e reflexão |
| [EI2 — Documento de Requisitos](../exercicios/EI2-documento-requisitos.md) | 12/04 (Dom) | 5 user stories com critérios de aceitação, MoSCoW justificado |
| [EI3 — Testes em JavaScript](../exercicios/EI3-testes-js.md) | 17/05 (Dom) | Suite Vitest + Playwright em módulo com bugs intencionais |
| [EI4 — Reflexão Técnica e Profissional](../exercicios/EI4-reflexao-tecnica.md) | 14/06 (Dom) | Documento reflexivo 2–3 páginas sobre decisões, stakeholder e trajetória |

### 1.3 Missões

Ao longo do semestre o professor poderá lançar **missões** — desafios opcionais de curto prazo ligados ao tema da semana ou a oportunidades de aplicação extra. Cada missão é anunciada com pelo menos uma semana de antecedência e tem critérios de avaliação explícitos.

**Política de atrasos (EI e missões):** até 48h de atraso → desconto de 20%. Após 48h → não pontua.

---

## 2. Projeto em Equipe — 60%

O projeto é avaliado em dois blocos: os checkpoints incrementais ao longo dos sprints (que valem a maior parte) e a entrega final com apresentação acadêmica.

### 2.1 Checkpoints / Sprint Reviews

Cinco momentos formais de avaliação, cada um com o stakeholder presente. A equipe é avaliada como um todo — o feedback do parceiro integra a nota.

| Checkpoint | Data | Peso no componente |
|-----------|------|--------------------|
| ✅ Review Sprint 0 | 09/04 | 10% |
| ✅ Review Sprint 1 | 30/04 | 20% |
| ✅ Review Sprint 2 | 14/05 | 25% |
| ✅ Review Sprint 3 | 28/05 | 25% |
| ✅ Review Sprint 4 | 11/06 | 20% |

**O que é avaliado em cada review:**

| Checkpoint | Foco da avaliação |
|-----------|-----------------|
| Sprint 0 | Canvas de Visão · backlog priorizado · protótipo hi-fi · escopo aprovado pelo stakeholder |
| Sprint 1 | Primeiras features funcionando · arquitetura documentada · testes iniciais |
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

**Entrega formal ao stakeholder — Semana 14 (18/06)**

A equipe entrega ao parceiro: repositório com código, deploy funcional, README completo e guia de uso. O stakeholder preenche o [Formulário de Feedback](../projeto/formulario-feedback-stakeholder.md), que integra a avaliação deste bloco.

**Apresentação acadêmica — Semana 15 (29 e 30/06)**

12 minutos + 5 minutos de Q&A, seguindo obrigatoriamente os 4 movimentos da Mini-Sinfonia:

1. **Exposição** — o problema, o stakeholder, o contexto
2. **Composição** — as decisões de design, os protótipos, o Canvas de Visão
3. **Ensaio** — a arquitetura, o código, os testes, os sprint reviews
4. **Ressonância** — a entrega, o feedback real do stakeholder, as lições aprendidas

**Rubrica da apresentação:**

| Critério | Peso | Descrição |
|----------|------|-----------|
| **Clareza narrativa** | 25% | A história do projeto é compreensível para quem não acompanhou? Os 4 movimentos estão claros? |
| **Profundidade técnica** | 30% | As decisões técnicas são explicadas com fundamento? Os desafios são apresentados honestamente? |
| **Demonstração do produto** | 25% | O produto funciona ao vivo? A demo cobre os casos de uso principais? |
| **Reflexão sobre o impacto** | 20% | A equipe articula o que o produto mudou para o stakeholder? O que faria diferente? |

---

## 3. Provas — 40% (2 × 20%)

Duas provas escritas individuais, de consulta fechada, com questões abertas que privilegiam raciocínio e aplicação sobre memorização.

| Prova | Data | Conteúdo |
|-------|------|-----------|
| **Prova 1** | 05/05/2026 (Ter · Semana 8) | ES · Git · Code Review · Processos ágeis · Requisitos e User Stories · Princípios de design · C4 Model · Qualidade de software |
| **Prova 2** | 09/06/2026 (Ter · Semana 13) | Testes (Vitest e Playwright) · Refactoring · Manutenção · Dívida técnica · Qualidade arquitetural · Code review avançado · Documentação |

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

*CIN0136 — Desenvolvimento de Software · CIn-UFPE · 2026.1*
