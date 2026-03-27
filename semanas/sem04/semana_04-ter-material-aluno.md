# Semana 4 — Terça-feira

## Strateegia: construção inicial do backlog do produto

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** | **24/03/2026 | E132 | 17:00–18:40**

---

## Sem leitura prévia formal para hoje

O insumo desta aula é o que você já tem: a visão de escopo construída ontem, as user stories e critérios INVEST estudados na Semana 3, e o Gherkin que você praticou nos slides L08.

Se quiser revisar antes de vir, releia os slides L08 — especialmente as seções sobre critérios de aceitação e o formato Dado/Quando/Então.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Escrever user stories no formato padrão com persona identificada e benefício claro
- Avaliar cada story com os critérios INVEST e identificar o que precisaria mudar
- Escrever pelo menos um critério de aceitação em formato Gherkin para cada story, incluindo um caso de falha
- Identificar a qual Épico cada story pertence

---

## 1. Da visão ao backlog: o que muda?

Ontem vocês descreveram o escopo do projeto em linguagem natural — problema, personas, valor. Hoje, esse escopo se transforma em itens de trabalho: as **user stories**.

A diferença entre visão e backlog não é de conteúdo — é de **granularidade e testabilidade**. Uma visão de escopo diz *o quê* e *para quem*. Uma user story desce um nível: diz *qual funcionalidade específica*, de *qual persona específica*, e define *como saberemos que está pronto*.

```
Visão de escopo → Épicos → Features → User Stories → Critérios de Aceitação
     (hoje)                              (hoje)              (hoje)
```

---

## 2. Revisão rápida: o formato da user story

```
Como [persona específica],
eu quero [ação/funcionalidade],
para que [benefício/valor concreto].
```

**As três armadilhas mais comuns:**

| Armadilha | Exemplo problemático | Por que é ruim |
|---|---|---|
| Persona genérica | "Como usuário..." | "Usuário" pode ser qualquer pessoa — a story não tem foco |
| Ação técnica | "...quero que o sistema salve no banco de dados..." | Isso é implementação, não valor para o usuário |
| Benefício vago | "...para ter uma melhor experiência." | Impossível verificar — como você saberia que funcionou? |

---

## 3. Revisão rápida: INVEST

Antes de considerar uma story pronta para entrar no backlog, ela precisa passar em seis critérios:

| Letra | Critério | A pergunta a fazer |
|---|---|---|
| **I** | Independent | Pode ser desenvolvida sem depender de outra story? |
| **N** | Negotiable | Os detalhes de implementação estão em aberto para discussão? |
| **V** | Valuable | Entrega valor real para o usuário — não apenas para o dev? |
| **E** | Estimable | É possível estimar o esforço necessário? |
| **S** | Small | Cabe dentro de um sprint? Se não, quebre. |
| **T** | Testable | Existe um critério verificável para saber que está pronta? |

**Regra prática:** se uma story falha no **T**, ela falha em tudo. Sem testabilidade, não há como saber se foi entregue.

---

## 4. Revisão rápida: Gherkin (Dado / Quando / Então)

O formato Gherkin transforma um critério de aceitação vago em uma especificação verificável:

```
Dado que [contexto / pré-condição]
Quando [ação do usuário]
Então [resultado esperado e verificável]
```

**Regra importante:** todo critério de aceitação precisa de pelo menos **dois cenários**:
- O **caminho feliz** — o que acontece quando tudo dá certo
- O **caso de falha** — o que acontece quando algo dá errado

**Exemplo completo:**

*Story:* "Como coordenadora do projeto, eu quero registrar a presença de um participante, para que o relatório de frequência seja atualizado automaticamente."

*Critério 1 — Caminho feliz:*
```
Dado que a coordenadora está autenticada no sistema
E o evento do dia está aberto para registro
Quando ela registra a presença de um participante pelo CPF
Então o participante aparece como "presente" no relatório do evento
```

*Critério 2 — Caso de falha:*
```
Dado que a coordenadora está autenticada no sistema
Quando ela tenta registrar um CPF que não existe no cadastro
Então o sistema exibe a mensagem "Participante não encontrado" e não altera o relatório
```

---

## 5. A dinâmica de hoje: Questão 2 no Strateegia

Você vai continuar no ponto de debate da sua equipe e responder à **Questão 2**.

> *Escreva **uma user story por resposta**, no formato padrão: "Como [persona], eu quero [funcionalidade], para que [benefício]." Para cada story, inclua também: (a) o Épico ao qual ela pertence, (b) uma avaliação rápida do INVEST — ela passa? o que precisaria mudar? — e (c) pelo menos um critério de aceitação no formato Gherkin (Dado / Quando / Então), incluindo um caso de falha. Responda quantas vezes achar necessário para cobrir o escopo do projeto. Cada resposta = uma story.*

### Template para cada resposta

```
Épico: [nome do épico ao qual esta story pertence]

User Story:
Como [persona específica],
eu quero [funcionalidade],
para que [benefício concreto].

Avaliação INVEST:
- I (Independent): [ ] Sim [ ] Não — justificativa:
- N (Negotiable): [ ] Sim [ ] Não — justificativa:
- V (Valuable): [ ] Sim [ ] Não — justificativa:
- E (Estimable): [ ] Sim [ ] Não — justificativa:
- S (Small): [ ] Sim [ ] Não — justificativa:
- T (Testable): [ ] Sim [ ] Não — justificativa:

Critério de aceitação — Caminho feliz:
Dado que
Quando
Então

Critério de aceitação — Caso de falha:
Dado que
Quando
Então
```

---

## 6. Dinâmica de revisão coletiva

Depois que todos tiverem escrito pelo menos 2–3 stories, o professor vai conduzir uma revisão coletiva das respostas. O objetivo não é corrigir — é identificar padrões.

Use este espaço para anotar durante a revisão:

```
Stories que parecem duplicadas (mesma funcionalidade descrita de formas diferentes):


Stories que parecem grandes demais (provavelmente são Features ou Épicos):


Stories com persona genérica ou benefício vago:


Stories que cobrem casos de falha de forma especialmente boa:


```

---

## 7. O que acontece na quinta?

Na quinta-feira, cada equipe vai apresentar os resultados das dinâmicas de segunda e terça aos seus respectivos stakeholders e coletar feedback estruturado. Depois, o backlog será refinado com base nesse feedback.

O material que você está produzindo hoje é o insumo direto para essa sessão.

**Antes de encerrar, pergunte a si mesmo:**
- As stories que escrevi cobrem o escopo que descrevi ontem?
- Há alguma área do projeto que ficou sem nenhuma story?
- Alguma story que eu escrevi seria melhor descrita como Épico ou Feature?

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

*CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1*
*Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 6 (seções 6.1–6.2) e Cap. 7 (seções 7.1.2–7.2.4). | Valente, M. T. Engenharia de Software Moderna. 2022. Cap. 3.*
