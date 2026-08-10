# Semana 1 — Terça-feira
## Ecossistema do desenvolvimento de software

**CIN0136: Desenvolvimento de Software · CIn-UFPE**

---

## Leitura Prévia

📖 *Engenharia de Software em Dimensões* — Cap. 1, seções 1.4, 1.5, 1.6 e 1.7

**Traga para a aula:** uma dúvida ou uma discordância do que você leu — não uma pergunta de confirmação, mas algo que te fez pensar "espera, mas e se...".

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Mapear os papéis, atividades e artefatos do ecossistema de desenvolvimento de software
- Compreender como o semestre se organiza em ciclos ágeis baseados em sprints
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

*Descoberta · Construção · Entrega*

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

## 2. Como o semestre se organiza: ciclos ágeis por sprints

O projeto que você vai desenvolver este semestre é conduzido em **ciclos ágeis baseados em sprints** — ciclos curtos e incrementais, no espírito das metodologias ágeis que você vai estudar já na Semana 2. Em vez de planejar tudo no início e construir de uma vez, a equipe descobre, projeta, constrói e valida em ciclos sucessivos, com feedback real do parceiro a cada etapa.

O semestre percorre três grandes fases:

```
SPRINT 0          SPRINTS 1–4              ENCERRAMENTO
Descobrir e       Construir e testar       Entregar e
projetar          (4 ciclos incrementais)  refletir
```

### O que cada fase significa na prática

**🔍 Sprint 0 — Descobrir e projetar**

No começo você ainda não sabe o suficiente para construir nada. O objetivo é *descobrir*: conhecer o parceiro, entender o problema real, explorar o contexto. Em seguida, *projetar*: prototipar, priorizar o backlog e fechar o escopo do MVP com o parceiro. Só quando o escopo está aprovado o desenvolvimento começa.

> O erro mais comum: querer propor soluções antes de entender o problema — e prometer mais do que é possível construir no tempo disponível.

**🔨 Sprints 1–4 — Construir e testar**

O produto é construído de forma incremental, em quatro sprints de aproximadamente duas semanas cada. Cada sprint termina com uma revisão (Sprint Review) com o parceiro, que valida o que foi entregue e ajuda a priorizar o próximo ciclo.

> O erro mais comum: acumular dívida técnica ao longo dos sprints e tentar resolver tudo no final. A regra da disciplina é clara: nenhuma feature é considerada pronta sem pelo menos um teste.

**🚀 Encerramento — Entregar e refletir**

Entrega formal ao parceiro, apresentação acadêmica e retrospectiva. O produto vai continuar existindo e sendo usado — ou não — depois que o semestre acabar. Essa consciência deve orientar suas decisões de qualidade desde o primeiro dia.

> O erro mais comum: deixar documentação e deploy para o final.

---

### Os marcos do projeto

| Fase | Marco |
|------|-------|
| Sprint 0 | Escopo do MVP aprovado pelo parceiro — ✅ Review Sprint 0 |
| Sprint 1 | Primeiras funcionalidades sobre a arquitetura definida — ✅ Sprint 1 Review |
| Sprint 2 | Features core do MVP + testes — ✅ Sprint 2 Review |
| Sprint 3 | Qualidade e refactoring — ✅ Sprint 3 Review |
| Sprint 4 | MVP estabilizado — ✅ Sprint 4 Review |
| Encerramento | 🎯 Entrega formal + apresentações acadêmicas |

> As datas de cada marco estão na planilha de plano de aulas do semestre corrente.

---

## 3. Qualidade contínua

A seção 1.4 do livro apresenta o conceito de **qualidade contínua**: garantir que a qualidade seja uma prioridade em todas as fases do desenvolvimento, não apenas no final.

Na prática, isso se traduz em:

- **TDD (Test-Driven Development):** escrever o teste antes do código
- **CI (Continuous Integration):** integrar o código frequentemente, não acumular tudo no final
- **CD (Continuous Delivery):** manter o produto sempre em estado de entregável

Você vai aprender e praticar os três ao longo do semestre. O importante agora é o princípio: **qualidade não é uma etapa — é uma postura**.

---

## 4. Carreiras em Engenharia de Software

A seção 1.6 apresenta a diversidade de trajetórias na área:

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

Você vai receber o documento durante a aula. Leia com atenção antes de assinar e identifique:

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
- Participar de um workshop ágil: como um processo de trabalho ajuda uma equipe a colaborar
- Configurar o quadro Kanban da equipe (GitHub Projects)
- Ter o primeiro encontro com o stakeholder do seu projeto para construir o backlog inicial

**Prepare-se:**
- Leia o roteiro com atenção
- Combine com a equipe quem será o facilitador e o escriba
- Não venha com soluções prontas — venha com curiosidade e perguntas

---

*CIN0136 — Desenvolvimento de Software · CIn-UFPE*
*Referência: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 1, seções 1.4–1.7.*
