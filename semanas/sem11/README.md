# Semana 11 — Design, Debugging + Sprint 3 Review

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1**
Sprint 3 · Semanas 10–11 · Ensaio

---

## Aulas desta semana

| Dia | Tema | Material do Aluno | Material do Professor |
|---|---|---|---|
| 🔵 **Segunda, 25/05** | Impacto das decisões de design na qualidade | [→ material-aluno](./semana_11-seg-material-aluno.md) | [→ material-professor](./semana_11-seg-material-professor.md) |
| 🟢 **Terça, 26/05** | Debugging, robustez e preparação para Sprint Review | [→ material-aluno](./semana_11-ter-material-aluno.md) | [→ material-professor](./semana_11-ter-material-professor.md) |
| 🟠 **Quinta, 28/05** | Sprint 3 Review com stakeholder + Retrospectiva | _(sessão com stakeholder — sem material escrito formal)_ | — |

---

## Leituras prévias por dia

### Segunda, 25/05

📖 **Garcia** — _Engenharia de Software em Dimensões_, Cap. 14, seções **14.7** e **14.8**
_(Qualidade e Arquitetura; Impacto no sucesso do software)_

📖 **Valente** — _Engenharia de Software Moderna_, Cap. **5** _(SOLID e outros princípios)_ + Cap. **7**, seção Microsserviços _(trade-offs arquiteturais)_

> Traga para a aula: uma decisão arquitetural que sua equipe tomou nas Semanas 6–7 e que hoje está gerando algum custo — um bug recorrente, dificuldade para adicionar features, acoplamento alto.

### Terça, 26/05

📖 **Sem leitura prévia formal.**

> Traga para a aula: notebook com o projeto rodando localmente e um bug ou comportamento inesperado que sua equipe não conseguiu explicar nos últimos dias.

---

## Objetivos da semana

Ao final desta semana, você deve ser capaz de:

- Analisar criticamente decisões arquiteturais do próprio projeto e identificar violações de princípios SOLID
- Articular trade-offs entre diferentes abordagens arquiteturais com o vocabulário técnico das seções 14.7–14.8
- Usar breakpoints no VS Code e interpretar stack traces para debugar JavaScript de forma sistemática
- Aplicar try/catch estratégico com respostas HTTP semanticamente corretas (4xx vs 5xx)
- Implementar um Error Boundary básico em React para evitar tela branca em produção
- Demonstrar ao stakeholder o MVP com foco em qualidade e robustez

---

## Entregáveis com prazo

| Entregável | Prazo | Observação |
|---|---|---|
| ✅ **Sprint 3 Review** — demo ao stakeholder | Quinta, 28/05 | Bloco 2 da aula de quinta (2h) |
| 📋 **Retrospectiva documentada** | Quinta, 28/05 (após a review) | Registrar no repositório ou Notion da equipe |
| 🗓️ **Planejamento do Sprint 4** | Quinta, 28/05 (após retrospectiva) | Backlog atualizado e prioridades definidas |

---

## Recursos relevantes

**Sobre debugging em JavaScript:**
- [VS Code Debugger — documentação oficial](https://code.visualstudio.com/docs/editor/debugging)
- [MDN — Error handling e try/catch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)
- [Node.js — Understanding Error Handling](https://nodejs.org/en/learn/getting-started/error-handling)

**Sobre status HTTP:**
- [MDN — HTTP response status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

**Sobre Error Boundaries em React:**
- [React Docs — Error Boundaries](https://react.dev/reference/react/Component#catching-rendering-errors-with-an-error-boundary)

**Leitura de referência (sem prévia formal):**
- Garcia, V. C. _Engenharia de Software em Dimensões_. ASSERT Lab, 2026. Cap. 14, seções 14.1–14.8.
- Valente, M. T. _Engenharia de Software Moderna_. Independente, 2022. Cap. 5 e Cap. 7.

---

## Por que esta semana importa para o Sprint 3

O Sprint 3 tem como foco **qualidade e refactoring** — e a Semana 11 é o seu encerramento. É o momento em que os conceitos técnicos do semestre inteiro se encontram com a realidade do produto que você está construindo.

A aula de segunda faz isso de forma reflexiva: as decisões arquiteturais que pareciam razoáveis nas Semanas 6 e 7 — quando o sistema era menor e mais simples — agora se revelam em custos concretos de manutenibilidade, testabilidade e acoplamento. Nomear esses custos com o vocabulário técnico correto (SOLID, atributos de qualidade, trade-offs) é o que transforma a experiência do projeto em aprendizado transferível.

A aula de terça faz isso de forma prática: o debugging sistemático com breakpoints é uma competência que diferencia desenvolvedores júnior de sênior. Mais do que a técnica em si, o que muda é a postura — hipótese antes do log, observação antes da correção.

E quinta é o momento de mostrar. O stakeholder vai experimentar o produto, não ouvir sobre ele. A qualidade que foi discutida na segunda, construída na semana 10 e estabilizada na terça é o que o stakeholder vai avaliar — mesmo sem saber que está avaliando qualidade técnica.

> **No mapa da Mini-Sinfonia:** a Semana 11 encerra o terceiro movimento do Ensaio. Saindo daqui, o Sprint 4 começa — a última rodada de desenvolvimento antes da Ressonância.

---

_CIN0136 — Desenvolvimento de Software · CIn-UFPE · 2026.1_
_Última atualização: maio/2026_
