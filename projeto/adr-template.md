# ADR-NNNN: [Título curto e descritivo da decisão]

> *Use um título que descreva a decisão tomada, não o problema. Ex.: "Usar PostgreSQL como banco de dados principal" e não "Escolha do banco de dados".*

---

**Status:** `Proposto` | `Aceito` | `Deprecado` | `Substituído por ADR-NNNN`
**Data:** AAAA-MM-DD
**Decisores:** *Nome(s) de quem participou da decisão*

---

## Contexto e Problema

*Descreva o contexto em que a decisão foi necessária e o problema que precisava ser resolvido. Seja objetivo — 2 a 4 frases. Use linguagem neutra; não defenda ainda nenhuma opção.*

**Exemplo:**
> O projeto precisa persistir dados de usuários e tarefas entre sessões. Precisamos escolher como e onde armazenar esses dados considerando que a equipe tem experiência limitada com bancos de dados e o prazo do Sprint 1 é curto.

---

## Opções Consideradas

*Liste as alternativas que a equipe avaliou. Pelo menos duas. Uma linha por opção é suficiente aqui.*

- Opção A: [nome da opção]
- Opção B: [nome da opção]
- Opção C: [nome da opção] *(se houver)*

---

## Decisão

*Descreva a escolha feita. Use voz ativa: "Decidimos usar…". Inclua a justificativa principal — por que esta opção e não as outras.*

**Exemplo:**
> Decidimos usar SQLite durante o desenvolvimento e os primeiros sprints. A escolha se justifica pela simplicidade de setup (sem servidor separado), familiaridade da equipe com SQL básico e adequação ao volume de dados esperado no MVP. Caso o projeto escale além do MVP, revisaremos esta decisão.

---

## Consequências

*Liste os efeitos concretos desta decisão — positivos, negativos e neutros. Não omita os negativos.*

**Bom, porque:**
- …

**Ruim, porque:**
- …

**Neutro / a observar:**
- …

---

## Referências

*Links, discussões, issues ou outros ADRs relacionados. Remova esta seção se não houver referências.*

- [Link para issue ou discussão no GitHub]
- [ADR relacionado, se houver]

---

*CIN0136 — Desenvolvimento de Software · CIn-UFPE*
*Baseado no template MADR light: https://adr.github.io/madr/*
