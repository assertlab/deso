# 📅 Semana 9 — Testes de Software + BDD + Sprint 2 Review

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1**

> **Sprint 2** · Fase Ensaio (Sinfonia) · Features Core do MVP

---

## 🎯 Objetivos da Semana

- Formalizar os conceitos de tipos de teste, pirâmide de testes e cobertura — conectando com a experiência prática do Vitest (Semana 8)
- Subir da base da pirâmide (unitários) ao topo (aceitação) com BDD e Playwright
- Transformar os critérios de aceitação Gherkin da Semana 4 em cenários BDD formais com caminhos de sucesso e falha
- Implementar testes de aceitação automatizados com Playwright no projeto
- Demonstrar as funcionalidades core do MVP ao stakeholder na Sprint 2 Review

---

## 📚 Aulas da Semana

|Dia|Tema|Material do Aluno|Horário|
|---|---|---|---|
|🔵 **SEG** 11/05|Por que testar? Tipos de teste, pirâmide e cobertura|semana_09-seg-material-aluno.md|18:50–20:30 · E132|
|🟢 **TER** 12/05|Testes de aceitação + BDD e Gherkin + Playwright|semana_09-ter-material-aluno.md|17:00–18:40 · E132|
|🟠 **QUI** 14/05|Lab Playwright + 👤 Sprint 2 Review com Stakeholder|_(sessão prática — sem material teórico)_|17:00–20:30 · Grad04|

---

## 📖 Leituras Prévias

|Dia|Leitura|Questão-guia|
|---|---|---|
|**Segunda**|Garcia — Cap. 9, seções 9.1–9.4 (Evolução histórica; Tipos; Cobertura; Desafios e vantagens) · Valente — Cap. 8: Testes de Unidade, Integração, Sistema, Cobertura, TDD|Se 100% de cobertura não garante qualidade, o que garante?|
|**Terça**|Garcia — Cap. 9, seção 9.2.4 (Testes de Aceitação) + revisitar Cap. 7 (User Stories)|Os critérios Gherkin da Semana 4 são claros o suficiente para automatizar sem perguntar nada?|
|**Quinta**|Sem leitura nova — traga os cenários BDD escritos na terça + backlog atualizado|—|

---

## 🎯 Entregáveis e Prazos

|Entregável|Descrição|Prazo|
|---|---|---|
|**Cenários BDD formais**|Cenários Gherkin completos (sucesso + falha) para as user stories da Sprint 2 Review|Terça (exercício em aula)|
|**Testes Playwright**|Mínimo 3 cenários de aceitação automatizados no projeto|Quinta (antes da Sprint Review)|
|**Sprint 2 Review**|Demo ao stakeholder + feedback registrado + retrospectiva|Quinta|
|**EI3 — Testes em JavaScript**|Exercício individual (publicado após Sprint Review)|Domingo 17/05|

---

## 🔗 Recursos Relevantes

|Recurso|Tipo|Link/Referência|
|---|---|---|
|Garcia, Cap. 9 — Testes de Software|Livro-texto|Seções 9.1–9.4|
|Valente, Cap. 8 — Testes|Livro-texto|engsoftmoderna.info|
|Playwright — Documentação oficial|Ferramenta|[playwright.dev](https://playwright.dev/)|
|Vitest — Documentação oficial|Ferramenta|[vitest.dev](https://vitest.dev/)|
|Formato Gherkin — Referência|Documentação|[cucumber.io/docs/gherkin](https://cucumber.io/docs/gherkin/)|

---

## 💡 Por que esta semana importa para a Sprint 2

A Sprint 2 é a sprint das features core do MVP. Vocês vêm construindo funcionalidades desde a Semana 8 e na quinta vão demonstrá-las ao stakeholder. Esta semana fecha o arco de testes com duas contribuições complementares:

**Segunda** formaliza o que vocês já viveram: na Semana 8, escreveram testes com Vitest sem ter o vocabulário formal. Agora vocês sabem situar cada teste na pirâmide, entender o que cobertura realmente mede, e identificar os edge cases que ainda não foram testados.

**Terça** sobe ao topo da pirâmide: testes de aceitação validam se o software faz o que o **usuário** espera — não apenas se o código funciona. Os cenários Gherkin da Semana 4 ganham uma nova vida como especificações BDD prontas para automação com Playwright.

A quinta é o ponto de convergência: na primeira metade, vocês transformam os cenários em testes reais; na segunda metade, demonstram ao stakeholder. Os testes de aceitação são a rede de segurança para a demo — se passam, vocês demonstram com confiança; se não passam, sabem exatamente o que falta antes que o stakeholder descubra.

A Semana 10 traz Refactoring — e refatorar com segurança **exige** testes. A suíte que vocês constroem esta semana é a base para tudo o que vem depois.

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
