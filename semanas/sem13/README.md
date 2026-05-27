# Semana 13 — Reflexão + Prova 2 + Sprint 4 Review

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1**
**08 a 11 de junho de 2026**

---

## Por que esta semana importa

A Semana 13 é a semana de fechamento do **Ensaio** — o maior movimento da Mini-Sinfonia, que ocupou as Semanas 6 a 13 com oito semanas de construção em quatro sprints. Não por acaso, ela é estruturada em três momentos complementares: olhar para trás (segunda), ser avaliado individualmente (terça) e apresentar ao stakeholder o produto que chegou até aqui (quinta).

É a última semana antes da Ressonância. O que for entregue na quinta-feira ao stakeholder é o que vai para a fase final. Não haverá mais sprints.

---

## Aulas desta semana

| Dia | Data | Tema | Materiais | Sala | Horário |
|-----|------|------|-----------|------|---------|
| 🔵 Segunda | 08/06 | Reflexão: da ideia ao produto | [Aluno](./semana_13-seg-material-aluno.md) · [Professor](./semana_13-seg-material-professor.md) | E132 | 18:50–20:30 |
| 🟢 Terça | 09/06 | ✏️ PROVA 2 | [Aluno](./semana_13-ter-material-aluno.md) · [Professor](./semana_13-ter-material-professor.md) | E132 | 17:00–18:40 |
| 🟠 Quinta | 11/06 | Sprint 4 Review + Estabilização final do MVP | *(sessão com stakeholder — sem material teórico)* | Grad04 | 17:00–20:30 |

---

## Objetivos da semana

Ao final desta semana, cada aluno e cada equipe devem ter:

- Revisitado criticamente o arco de decisões técnicas e de produto dos Sprints 2 a 4
- Demonstrado compreensão individual dos conteúdos das Semanas 8–12 (Prova 2)
- Apresentado ao stakeholder o MVP estabilizado com demo funcional, feedback incorporado e retrospectiva documentada
- Iniciado a escrita do EI4 — Reflexão Técnica e Profissional

---

## Leituras prévias por dia

| Dia | Leitura prévia |
|-----|---------------|
| 🔵 Segunda | Nenhuma — aula de reflexão guiada. Traga a memória do projeto. |
| 🟢 Terça | Nenhuma — PROVA 2. Revise os conteúdos das Semanas 8–12 (ver guia no material do aluno). |
| 🟠 Quinta | Nenhuma — sessão com stakeholder. Traga o projeto em estado de demo. |

---

## Entregáveis com prazo

| Entregável | Quem | Prazo | Via |
|-----------|------|-------|-----|
| ✅ Sprint 4 Review — MVP estabilizado + feedback + retrospectiva | Equipes | 11/06 (quinta) | Sessão presencial com stakeholder |
| 📝 EI4 — Reflexão Técnica e Profissional | Individual | 14/06 (domingo) | Formulário do professor |

> **Sobre o EI4:** é o último exercício individual do semestre. Pede uma reflexão escrita sobre a jornada técnica e profissional dos Sprints — decisões tomadas, aprendizados, o que faria diferente. O conteúdo produzido na aula de segunda-feira é insumo direto para este exercício.

---

## Checklist para o Sprint 4 Review (quinta-feira)

Antes de chegar na quinta, cada equipe deve garantir:

- [ ] Produto funcionando de ponta a ponta sem intervenção manual
- [ ] Testes principais passando (ao menos unitários e um E2E crítico)
- [ ] README atualizado — outra pessoa conseguiria rodar o projeto?
- [ ] Diagramas C4 (N1 e N2) commitados no repositório
- [ ] Deploy funcional para a demonstração (localhost ou ambiente real)
- [ ] Backlog organizado — o que foi entregue vs. o que ficou pendente está claro
- [ ] Demo ensaiada: 10 min de apresentação + 5 min de perguntas do stakeholder

---

## Conteúdo da Prova 2

A Prova 2 (terça, 09/06) cobre as **Semanas 8 a 12**:

| Tema | Referências |
|------|------------|
| Testes: pirâmide, Vitest, Playwright, TDD, BDD/Gherkin | Garcia Cap. 9 · Valente Cap. 8 |
| Refactoring: code smells, catálogo de Fowler, refatoração segura | Valente Cap. 9 |
| Manutenção e dívida técnica: tipos, dívida intencional vs. acidental | Garcia Cap. 19, seções 19.1–19.3 |
| Qualidade arquitetural: coesão, acoplamento, C4, debugging | Garcia Cap. 14 · Valente Cap. 5 e 7 |
| Code Review e Documentação: checklist avançado, README | Garcia Cap. 3 (seção 3.5) · Cap. 19 (seção 19.4) |

**Formato:** questões dissertativas e de análise de caso. Não há múltipla escolha. Exemplos do projeto são bem-vindos quando conectados ao conceito pedido.

---

## Recursos relevantes

### Livros-texto

- **Garcia** — *Engenharia de Software em Dimensões* (ASSERT Lab, 2025): Cap. 3, 9, 14, 19
- **Valente** — *Engenharia de Software Moderna* (2022, [engsoftmoderna.info](https://engsoftmoderna.info)): Cap. 5, 7, 8, 9

### Materiais das semanas anteriores (revisão para a prova)

- [Semana 8 — Balanço + Prova 1](../semana_08/)
- [Semana 9 — Testes: Vitest e Playwright](../semana_09/)
- [Semana 10 — Refactoring e Manutenção](../semana_10/)
- [Semana 11 — Qualidade arquitetural e Debugging](../semana_11/)
- [Semana 12 — Code Review e Documentação](../semana_12/)

### Ferramentas para o Sprint 4 Review

- [Vitest](https://vitest.dev/): testes unitários
- [Playwright](https://playwright.dev/): testes E2E
- [Mermaid](https://mermaid.js.org/): diagramas C4 no repositório
- GitHub Projects: kanban atualizado

---

## Onde esta semana se encaixa na Mini-Sinfonia

```
┌─────────────┐    ┌─────────────┐    ┌─────────────────────────────────┐    ┌─────────────┐
│  EXPOSIÇÃO  │ →  │ COMPOSIÇÃO  │ →  │            ENSAIO               │ →  │ RESSONÂNCIA │
│  Sem 1–3    │    │  Sem 3–5    │    │          Sem 6–13               │    │  Sem 14–15  │
└─────────────┘    └─────────────┘    └─────────────────────────────────┘    └─────────────┘
                                                              ▲
                                                         [Você está aqui]
                                                         Semana 13 — fechamento
                                                         do último sprint
```

O **Ensaio** durou oito semanas. A Semana 13 é o seu compasso final: reflexão, avaliação individual, entrega ao stakeholder. Na semana seguinte começa a **Ressonância** — e o produto precisa estar pronto para ser entregue de verdade.

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
_Sprint 4 — último sprint do Ensaio da Mini-Sinfonia_
