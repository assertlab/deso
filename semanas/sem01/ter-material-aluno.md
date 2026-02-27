# Semana 1 — Terça-feira
## Ecossistema do desenvolvimento de software + Introdução à Sinfonia

**CIN0136: Desenvolvimento de Software · CIn-UFPE · 2026.1**
**03/03/2026 · E232 · 18:50–20:30**

---

## Leitura Prévia

📖 *Engenharia de Software em Dimensões* — Cap. 1, seções 1.4, 1.5, 1.6 e 1.7
📖 *Sinfonia* — Cap. 2: Visão Geral dos 4 Movimentos

**Traga para a aula:** uma dúvida ou uma discordância do que você leu — não uma pergunta de confirmação, mas algo que te fez pensar "espera, mas e se...".

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Mapear os papéis, atividades e artefatos do ecossistema de desenvolvimento de software
- Descrever os 4 movimentos da Mini-Sinfonia e relacioná-los com o semestre
- Saber quem são os membros da sua equipe e qual projeto será desenvolvido
- Ter assinado o [Código de Conduta e Ética](../../docs/codigo-conduta.md)

---

## 1. O ecossistema de desenvolvimento de software

Desenvolver software envolve muito mais do que escrever código. Há um ecossistema completo de **papéis**, **atividades** e **artefatos** que precisam funcionar juntos.

### Atividade coletiva — mapa mental

Durante a aula, a turma vai construir coletivamente um mapa dos três eixos abaixo. Use este espaço para registrar o que emergir da discussão.

**Papéis** — quem está envolvido em fazer um software existir?

| Técnicos | De produto | De processo |
|---------|-----------|------------|
| | | |
| | | |
| | | |

**Atividades** — o que precisa acontecer, da ideia ao produto em produção?

*Descuberta · Construção · Entrega*

**Artefatos** — o que é produzido em cada fase?

*Requisitos · Código · Documentação*

---

### Papéis que você vai exercer neste semestre

Este semestre é incomum: cada equipe de 4–5 pessoas vai cobrir quase todos os papéis do ecossistema. Marque os que você acha que vai exercer:

- [ ] Desenvolvedor (frontend / backend / full stack)
- [ ] Designer de interface (wireframes, protótipos)
- [ ] Engenheiro de requisitos (entender e documentar o que o parceiro precisa)
- [ ] Testador (escrever e executar testes)
- [ ] Revisor de código (code review em PRs de colegas)
- [ ] Documentador (README, decisões arquiteturais)
- [ ] Facilitador da comunicação com o stakeholder
- [ ] Apresentador (apresentação acadêmica final)

---

## 2. A Mini-Sinfonia: o framework do projeto

O projeto que você vai desenvolver este semestre segue a estrutura da **Mini-Sinfonia** — uma adaptação da Metodologia Sinfonia (Garcia & Medeiros, 2025) para o contexto do 2º período.

```
EXPOSIÇÃO → COMPOSIÇÃO → ENSAIO → RESSONÂNCIA
Descobrir    Projetar    Construir  Entregar e aprender
Sem 1–3      Sem 3–5     Sem 6–13   Sem 14–15
```

### O que cada movimento significa na prática

**🔍 Exposição — Semanas 1 a 3**

Você ainda não sabe o suficiente para construir nada. O objetivo é *descobrir*: conhecer o parceiro, entender o problema real, explorar o contexto.

> O erro mais comum: querer propor soluções antes de entender o problema.

**🎨 Composição — Semanas 3 a 5**

Você projeta a solução: wireframes, protótipos, backlog de funcionalidades, Canvas de Visão. Ao final da Semana 5, o parceiro aprova o escopo. Só então o desenvolvimento começa.

> O erro mais comum: prometer mais do que é possível construir em 8 semanas.

**🔨 Ensaio — Semanas 6 a 13**

Oito semanas de construção em 4 sprints de 2 semanas cada. Cada sprint termina com uma revisão com o parceiro.

> O erro mais comum: acumular dívida técnica e tentar resolver tudo no final.

**🎵 Ressonância — Semanas 14 e 15**

Entrega formal ao parceiro, apresentação acadêmica, retrospectiva. "Ressonância" porque o produto vai continuar existindo depois que o semestre acabar.

> O erro mais comum: deixar documentação e deploy para esta fase.

---

### Calendário dos marcos

| Fase | Semanas | Marco |
|------|---------|-------|
| Exposição | 1–3 | Protótipos low-fi validados com o parceiro |
| Composição | 3–5 | ✅ Canvas de Visão + backlog aprovado — Review Sprint 0 (09/04) |
| Ensaio · Sprint 1 | 6–7 | ✅ Primeiras funcionalidades (30/04) |
| Ensaio · Sprint 2 | 8–9 | ✅ Features core do MVP (14/05) |
| Ensaio · Sprint 3 | 10–11 | ✅ Qualidade e refactoring (28/05) |
| Ensaio · Sprint 4 | 12–13 | ✅ MVP estabilizado (11/06) |
| Ressonância | 14–15 | 🎯 Entrega formal (18/06) + Apresentações (29–30/06) |

---

## 3. Qualidade contínua

O Cap. 1.4 do livro apresenta o conceito de **qualidade contínua**: garantir que a qualidade seja uma prioridade em todas as fases do desenvolvimento, não apenas no final.

Na prática, isso se traduz em:

- **TDD (Test-Driven Development):** escrever o teste antes do código
- **CI (Continuous Integration):** integrar o código frequentemente, não acumular tudo no final
- **CD (Continuous Delivery):** manter o produto sempre em estado de entregável

Você vai aprender e praticar os três ao longo do semestre. O importante agora é o princípio: **qualidade não é uma etapa — é uma postura**.

---

## 4. Carreiras em Engenharia de Software

O Cap. 1.6 apresenta a diversidade de trajetórias na área:

| Trajetória | Foco |
|-----------|------|
| Desenvolvimento (frontend/backend/full stack) | Construção de produtos |
| QA / Engenharia de Testes | Qualidade e confiabilidade |
| DevOps / SRE | Entrega contínua e operação |
| Engenharia de dados | Pipelines e infraestrutura de dados |
| Product Engineering | Intersecção entre produto e tecnologia |
| Pesquisa e inovação | Novas tecnologias e métodos |

Competências valorizadas em **todas** as trajetórias: adaptabilidade, trabalho em equipe, comunicação clara, pensamento crítico.

---

## 5. Código de Conduta e Ética

Você vai receber o documento impresso durante a aula. Leia com atenção antes de assinar e identifique:

- Uma cláusula que achou **surpreendente**
- Uma cláusula que acha **difícil de cumprir**

Versão completa disponível em → [docs/codigo-conduta.md](../../docs/codigo-conduta.md)

---

## 6. Equipe e projeto

A composição das equipes e a alocação dos stakeholders está em → [equipes.md](../../equipes.md)

---

## 7. Questão estruturante para reflexão

> *"De que forma as práticas de qualidade contínua e as metodologias ágeis impactam a colaboração entre equipes e a adaptação do software aos objetivos de negócio?"*

*Anote sua perspectiva antes da discussão.*

---

## 8. Para a próxima aula (Quinta-feira)

📖 **Leia antes da aula:** [Roteiro para o 1º Contato com o Stakeholder](../../projeto/roteiro-primeiro-contato.md)

**Na quinta você vai:**
- 2h de nivelamento de JavaScript (foco na transição de Python/C para JS)
- Primeiro encontro com o stakeholder do seu projeto

**Prepare-se:**
- Leia o roteiro com atenção
- Combine com a equipe quem será o facilitador e o escriba
- Não venha com soluções prontas — venha com curiosidade e perguntas

---

*CIN0136 — Desenvolvimento de Software · CIn-UFPE · 2026.1*
*Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 1, seções 1.4–1.7.*
*Garcia, V. C.; Medeiros, R. P. Sinfonia: Metodologia para Desenvolvimento de Produtos de IA. TDS Books, 2025. Cap. 2.*
