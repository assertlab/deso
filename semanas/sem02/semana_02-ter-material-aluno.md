# Semana 2 — Terça-feira

## Metodologias ágeis: Scrum, Kanban e a escolha do processo

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **10/03/2026 | E232 | 18:50–20:30**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 4, seções 4.3, 4.4 e 4.5

**Traga para a aula:** se vocês fossem escolher um processo para o projeto **hoje**, qual seria — Scrum, Kanban ou outro? Por quê? Você vai defender sua posição.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Descrever os elementos centrais do Scrum (papéis, eventos, artefatos) e do Kanban (fluxo, WIP, visualização)
- Comparar Scrum e Kanban com base em critérios concretos de contexto
- Argumentar qual processo é mais adequado para o projeto da disciplina
- Identificar pelo menos dois riscos do processo escolhido e como mitigá-los

---

## 1. Sua posição antes da discussão

Qual processo você escolheria para o projeto da equipe?

```
Minha escolha:


Meu principal argumento:


```

---

## 2. Scrum

Scrum é um framework ágil baseado em ciclos de tempo fixo chamados **sprints**. Cada sprint tem duração definida (geralmente 1–4 semanas) e termina com um produto funcional para revisar com o stakeholder.

### Os três papéis

|Papel|Responsabilidade principal|
|---|---|
|**Product Owner**|Guarda o backlog, prioriza o que entra no próximo sprint, representa os interesses do stakeholder|
|**Scrum Master**|Garante que o processo está funcionando, remove impedimentos, facilita as cerimônias|
|**Time de Desenvolvimento**|Autogerenciado, decide como o trabalho será feito, se compromete com o que cabe no sprint|

**No projeto de vocês:** quem exerceria cada papel? Lembre que num time pequeno os papéis podem ser fluidos, mas alguém precisa ser o guardião do backlog e alguém precisa garantir que o processo está sendo seguido.

```
Product Owner da nossa equipe:
Scrum Master da nossa equipe:
```

### Os quatro eventos principais

|Evento|Quando|Propósito|
|---|---|---|
|**Sprint Planning**|Início do sprint|O time decide o que vai entregar e como|
|**Daily Standup**|Diariamente (máx. 15 min)|Sincronização: o que fiz, o que vou fazer, o que está me bloqueando|
|**Sprint Review**|Final do sprint|Demonstração ao stakeholder do que foi construído|
|**Sprint Retrospectiva**|Final do sprint|O time reflete sobre o processo: o que funcionou, o que melhorar|

### O Sprint como compromisso

Um sprint não é "vamos tentar". É um compromisso de entrega. Ao final, o time tem algo funcionando para mostrar — não uma lista de tarefas em andamento.

> O erro mais comum: colocar mais itens no sprint do que o time consegue entregar. A sprint planning existe para evitar isso.

---

## 3. Kanban

Kanban é uma abordagem de gestão de fluxo. Não tem sprints nem papéis fixos — o foco é tornar o trabalho visível, limitar o trabalho em progresso (WIP) e otimizar o fluxo de entrega.

### Os princípios centrais

**1. Visualize o trabalho**

Torne todo o trabalho visível num board. Cada item tem um estado claro: Backlog → To Do → In Progress → Review → Done.

Vocês já fizeram isso na Semana 1 — o board do GitHub Projects é o Kanban da equipe.

**2. Limite o trabalho em progresso (WIP)**

O Kanban define um limite máximo de itens simultâneos em cada coluna. Se "In Progress" tem limite de 2 e já há 2 itens lá, nenhum novo item pode entrar até que um seja concluído.

> Por que limitar? Porque trabalhar em muitas coisas ao mesmo tempo aumenta o cycle time — o tempo que um item leva do início ao fim. Foco em menos itens acelera a entrega real.

**3. Gerencie o fluxo**

O objetivo do Kanban não é ter todos ocupados — é ter itens fluindo até a conclusão. Um time onde todos estão "ocupados" mas nada está sendo entregue está com o fluxo bloqueado.

### O que o Kanban não tem (que o Scrum tem)

- Sprints fixos com comprometimento de entrega
- Papéis definidos
- Cerimônias obrigatórias (planning, review, retro)
- Métricas de velocidade por ciclo

---

## 4. Lean — o princípio que atravessa os dois

Lean não é um processo — é uma filosofia que influencia tanto o Scrum quanto o Kanban. O princípio central é **eliminar desperdício**.

No contexto de software, desperdício inclui:

- Funcionalidades construídas que ninguém usa
- Reuniões sem pauta ou sem decisão
- Código que nunca vai para produção
- Retrabalho causado por requisitos mal entendidos
- Espera: um item "em progresso" que ficou bloqueado por dias sem que ninguém notasse

**No projeto de vocês — quais desperdícios você prevê que vão aparecer?**

```
Desperdícios prováveis na nossa equipe:


```

---

## 5. Scrum vs. Kanban: quando usar cada um

|Critério|Scrum|Kanban|
|---|---|---|
|Tipo de demanda|Escopo definido, entregas planejadas|Demanda contínua, variável, imprevisível|
|Cadência|Sprints fixos (1–4 semanas)|Fluxo contínuo|
|Planejamento|Sprint planning com comprometimento|Just-in-time|
|Métricas|Velocity, burn-down|Cycle time, throughput, WIP|
|Revisão com stakeholder|Final de cada sprint (planejada)|A cada item concluído (contínua)|
|Melhor para...|Projetos com escopo e prazo definidos|Suporte, manutenção, operações contínuas|

**Atenção:** os dois não são mutuamente exclusivos. É comum usar o board Kanban como ferramenta de visualização dentro de um processo Scrum — que é exatamente o que o GitHub Projects permite.

---

## 6. Cenários de decisão

### Cenário A — A equipe de suporte

Uma equipe de 3 pessoas atende chamados de suporte de um sistema em produção. Chegam novos chamados todos os dias, com prioridades diferentes. Não há como planejar um sprint porque a demanda é imprevisível.

**Qual processo você recomendaria? Por quê?**

```
Minha resposta:


```

### Cenário B — O time de produto

Uma equipe de 5 pessoas está construindo um novo módulo de um sistema. Têm 3 meses e um escopo definido. O cliente participa de revisões a cada 2 semanas.

**Qual processo você recomendaria? Por quê?**

```
Minha resposta:


```

### Cenário C — O projeto de vocês

Equipe de 4–5 pessoas. 8 semanas de construção (Sprints 1–4). Stakeholder real com revisões planejadas. Escopo fechado ao final da Semana 3.

**Qual processo a equipe vai adotar? Qual é o principal risco desse processo no contexto de vocês?**

```
Decisão da equipe:


Principal risco:


Como mitigar:


```

---

## 7. Questões estruturantes para reflexão

Selecione **uma** para responder antes da discussão:

**Questão A:**

> _"Como você escolheria entre Scrum e Kanban para um projeto real? Quais fatores seriam determinantes na sua decisão?"_

**Questão B:**

> _"As metodologias ágeis prometem maior adaptabilidade e colaboração, mas também apresentam desafios. Quais são os principais riscos de adotar uma abordagem ágil sem a maturidade necessária?"_

```
Sua questão escolhida e resposta inicial:


```

---

## 8. Para a próxima aula (Quinta-feira)

**Na quinta você vai:**

- Revisar o Kanban criado na Semana 1 — ajustes com base no que aprendeu sobre processo
- Simular uma sprint planning com o backlog já levantado
- Refinar e priorizar colaborativamente os itens de backlog
- Definir a Definition of Done da equipe

**Prepare-se:**

- Tenha o board do GitHub Projects acessível
- Releia os itens de backlog que a equipe levantou com o stakeholder na Semana 1
- Pense: quais itens estão vagos demais para entrar num sprint? Quais já têm clareza suficiente?

---

## 9. Para a Semana 3 (Segunda-feira)

📖 **Leitura obrigatória:** Cap. 6, seções 6.1 e 6.2 (Requisitos Funcionais e Não Funcionais; Técnicas de Elicitação)

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_ _Referência: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 4, seções 4.3–4.5._
