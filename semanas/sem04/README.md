# Semana 6 — Princípios de Design e Arquitetura

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1**

> 🎼 **Sprint 1 · Movimento: Ensaio** — Esta semana marca a transição da preparação para a construção. O Sprint 0 ficou para trás: vocês já conhecem o stakeholder, fecharam o escopo e dominam as ferramentas de versionamento e colaboração. Agora é hora de transformar o backlog em código. Mas código que será mantido por 4 pessoas durante 8 semanas precisa de organização intencional — e é exatamente isso que esta semana ensina. As decisões de design e arquitetura tomadas aqui vão determinar se o desenvolvimento dos próximos sprints será fluido ou doloroso.

---

## Aulas da Semana

| Dia | Horário | Tema | Material |
|-----|---------|------|----------|
| 🔵 Segunda 23/03 | 17:00–18:40 | Por que a organização do código importa | [Material do aluno](semana_06-seg-material-aluno.md) |
| 🟢 Terça 24/03 | 18:50–20:30 | C4 Model: desenhando a arquitetura do projeto | [Material do aluno](semana_06-ter-material-aluno.md) |
| 🟠 Quinta 26/03 | 17:00–20:30 | Workshop de Arquitetura + Início do Desenvolvimento | _(prática em laboratório)_ |

---

## Leituras Prévias

### Segunda-feira

📖 **Garcia** — Cap. 14, seções 14.1.1 e 14.1.2 (Princípios fundamentais de design; Integração no design)

📖 **Valente** — Cap. 5: Princípios de Projeto (Integridade Conceitual; Ocultamento de Informação; Coesão; Acoplamento)

### Terça-feira

📖 **Garcia** — Cap. 14, seções 14.3.1 a 14.3.3 (Estrutura hierárquica do C4 Model) e seção 14.4 (C4 vs UML)

📖 **Valente** — Cap. 7: Arquitetura (seções: Camadas; MVC)

### Quinta-feira

Sem leitura prévia — aula prática. Traga o rascunho dos diagramas C4 feitos na terça e o repositório clonado com ambiente funcionando.

---

## Objetivos da Semana

Ao final da Semana 6, você deve ser capaz de:

1. **Argumentar** por que a organização do código é tão importante quanto seu funcionamento
2. **Aplicar** princípios de separação de responsabilidades, coesão e acoplamento ao projeto real
3. **Documentar** a arquitetura do projeto com diagramas C4 (Níveis 1, 2 e 3)
4. **Implementar** a estrutura arquitetural no repositório (scaffold de pastas e módulos)
5. **Iniciar** o desenvolvimento das features do Sprint 1 com PRs reais

---

## Entregáveis e Prazos

| Entregável | Prazo | Onde entregar |
|------------|-------|---------------|
| Diagramas C4 (Nível 1, 2 e 3) | Quinta 09/04 — até o final da aula | No repositório do projeto, pasta `docs/` |
| Estrutura arquitetural implementada (scaffold) | Quinta 09/04 — até o final da aula | Repositório do projeto (branch `main`) |
| Decisões arquiteturais documentadas | Quinta 09/04 — até o final da aula | `docs/decisoes-arquiteturais.md` no repositório |
| Primeiros PRs com features do Sprint 1 | Quinta 09/04 — abertos durante a aula | Repositório do projeto |

---

## Recursos Relevantes

### Livros-texto

- Garcia, V. C. _Engenharia de Software em Dimensões_. ASSERT Lab, 2025. **Cap. 14**
- Valente, M. T. _Engenharia de Software Moderna_. 2022. **Cap. 5 e Cap. 7** — disponível em [engsoftmoderna.info](https://engsoftmoderna.info)

### Ferramentas

- [Mermaid](https://mermaid.js.org/) — diagramas como código, renderização nativa no GitHub
- [draw.io](https://app.diagrams.net/) — editor visual de diagramas (arquivos `.drawio` versionáveis)
- [C4 Model — site oficial](https://c4model.com/) — referência completa com exemplos

### Referências complementares

- Simon Brown. _The C4 Model for Visualising Software Architecture_ — [c4model.com](https://c4model.com/)
- Martin Fowler. _Who Needs an Architect?_ — reflexão sobre o papel da arquitetura em projetos ágeis

---

## Por que esta semana importa para o Sprint 1

O Sprint 1 (Semanas 6–7) é o primeiro ciclo de construção real. Ele termina na Semana 7 com a Sprint Review perante o stakeholder — vocês precisarão demonstrar funcionalidades concretas.

A Semana 6 é a fundação técnica desse sprint. Sem uma arquitetura combinada, 4 pessoas codificando ao mesmo tempo geram conflitos de merge, estruturas incompatíveis e retrabalho. Os diagramas C4 e o scaffold implementado nesta semana são o "mapa" que permite que a equipe se divida sem se perder.

Na prática: as equipes que investem tempo em organizar a arquitetura antes de codar entregam mais — e com menos estresse — do que as que pulam direto para a implementação. Esta semana é a diferença entre construir sobre uma base sólida e construir sobre areia.

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
