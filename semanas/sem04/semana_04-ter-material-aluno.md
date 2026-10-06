# Semana 4 — Terça-feira

## Engenharia de Requisitos Assistida por IA — Lab prático (caso PetFood)

**CIN0136: Desenvolvimento de Software | CIn-UFPE |** **E132 | 17:00–18:40**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 7, seções 7.1.2–7.2.4 (User Stories, backlog, MoSCoW) — revisão da Semana 3 📖 _Engenharia de Software Moderna_ (Valente) — Cap. 3 (Histórias de Usuário, critérios INVEST, priorização)

**Traga para a aula:** os três entregáveis de ontem (Canvas de Visão PetFood, fronteira do MVP e o esboço da instrução de projeto), seu material da Semana 3 (INVEST, exemplo de Gherkin) e um notebook com acesso a um assistente de IA (Claude ou equivalente).

> 🔗 **Esta aula continua a de ontem.** Na segunda fizemos o *zoom out* — enquadramos o problema e recortamos o escopo (Canvas de Visão + fronteira do MVP). Hoje é o *zoom in*: pegamos esse escopo e o traduzimos em um backlog de histórias executáveis. Se você não estava ontem, peça o Canvas de Visão à sua equipe antes de começar.

> ⚠️ **Regra de ouro desta aula:** a IA **não elicita** o requisito do stakeholder por você, **não decide** o valor de negócio por você, e **não assume** a responsabilidade pelo que a equipe entrega. Ela acelera a estruturação, expõe lacunas e serve de par crítico. Você continua sendo o engenheiro de requisitos.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Distinguir o uso **ingênuo** ("gere um backlog pra mim") do uso **engenheirado** de IA em engenharia de requisitos
- Partir de um **escopo já definido** (o Canvas de Visão de ontem) para gerar histórias — em vez de gerar histórias no vácuo
- **Completar** a instrução de projeto da equipe (iniciada ontem) com o formato de história, INVEST e Gherkin
- Executar um ciclo assistido: elicitação → geração → **crítica humana** → refino
- Escrever histórias de usuário com critérios de aceitação em Gherkin (incluindo caso de falha) usando a IA como amplificadora, não como substituta
- Reconhecer os limites do que a IA pode fazer em engenharia de requisitos

---

## 1. O ponto de partida: ingênuo vs. engenheirado

Antes de tudo, um experimento. O professor vai mostrar duas formas de pedir a mesma coisa a um assistente de IA.

**Prompt ingênuo:**

```
Gere um backlog para um app de doação de comida para pets.
```

**Prompt engenheirado:** (contexto + papel + insumo real + formato + pedido de crítica)

Anote a diferença que você observou entre as duas saídas:

```
O que o backlog ingênuo tinha de errado / genérico:



O que mudou quando o prompt foi engenheirado:


```

> A lição central: **a qualidade da saída é limitada pela qualidade do insumo e da instrução.** A IA não sabe nada sobre o problema real do seu stakeholder. Se você não trouxer esse conhecimento, ela preenche com suposições genéricas — e você acaba com um backlog que serve para qualquer app e para nenhum projeto.

---

## 2. Completando a instrução de projeto da equipe

Ontem sua equipe **começou** a instrução de projeto — o bloco com o contexto do produto (nome, personas, fronteira do MVP). Hoje vamos **completá-la** com a parte que faltava: o papel do assistente, o formato de história, os critérios INVEST e o formato Gherkin.

Isso conecta com uma prática de engenharia real: **padronizar o time**. Uma instrução compartilhada garante que todos produzam artefatos no mesmo formato — e reaproveitem o escopo já definido, sem reescrever tudo a cada vez.

### Instrução de projeto completa (parta do esboço de ontem e acrescente)

> As três primeiras linhas (CONTEXTO DO PROJETO) você já tem do Canvas de Visão de ontem. Complete as demais.

```
CONTEXTO DO PROJETO            ← (já preenchido ontem, a partir do Canvas)
- Produto: PetFood — [uma frase sobre o problema que resolve]
- Personas principais: [do Canvas de Visão]
- Fronteira do MVP: [o que está dentro]
- Stack: React / Node.js / Express / PostgreSQL

PAPEL DO ASSISTENTE            ← (a partir daqui, completar hoje)
Aja como um analista de requisitos cético e experiente. Antes de gerar
qualquer artefato, aponte incertezas e faça perguntas quando faltar
informação. Não invente requisitos que não foram informados.

FORMATO DE HISTÓRIA DE USUÁRIO
Como [persona], quero [funcionalidade] para [benefício/valor].

CRITÉRIOS DE QUALIDADE (INVEST)
Toda história deve ser: Independente, Negociável, Valiosa,
Estimável, Pequena (Small) e Testável.

FORMATO DOS CRITÉRIOS DE ACEITAÇÃO (Gherkin)
Dado [contexto], Quando [ação], Então [resultado esperado].
Inclua sempre pelo menos um cenário de FALHA (caminho triste).

O QUE NÃO FAZER
- Não priorizar sozinho: a priorização de valor é decisão da equipe.
- Não assumir dados do stakeholder que não foram fornecidos.
```

> 💾 **Este é um entregável.** Salve a instrução da sua equipe — você vai reutilizá-la na tarefa pós-aula (projeto real) e nas sprints.

---

## 3. O caso de treino: PetFood (continuando de ontem)

Como ontem, você treina no PetFood — um caso controlado — antes de aplicar no projeto real. A diferença é que agora **você já tem o escopo**: o Canvas de Visão e a fronteira do MVP que sua equipe construiu na segunda. As histórias que você vai gerar hoje precisam caber **dentro** dessa fronteira. Histórias sobre coisas que ficaram "fora do MVP" não entram no backlog agora.

### Notas fictícias do "stakeholder PetFood" (relembrando o insumo)

> _"A gente é uma ONG que recebe doações de ração e distribui para famílias de baixa renda que têm pets. Hoje controlamos tudo no WhatsApp e numa planilha, e vive dando confusão: a família diz que não recebeu, a gente não sabe quanto tem em estoque, e os doadores querem saber pra onde foi a ração deles. Precisava de um jeito de registrar as doações que chegam, ver quanto tem em estoque, e agendar as retiradas pelas famílias. Ah, e o doador adoraria ver que a doação dele foi entregue."_

Marque o que você consegue extrair dessas notas:

- [ ] Personas envolvidas: _______________________________
- [ ] Pelo menos 3 funcionalidades candidatas: _______________________________
- [ ] Um requisito **não funcional** implícito: _______________________________
- [ ] Uma informação que **falta** e que você precisaria perguntar ao stakeholder: _______________________________

---

## 4. O ciclo assistido (o coração do lab)

Trabalhe em equipe. Repita este ciclo para **3 a 4 histórias** do PetFood.

### Passo 1 — Elicitação assistida

Cole a instrução de projeto (com o escopo de ontem), o Canvas de Visão e as notas do stakeholder no assistente. Peça que ele **faça perguntas** sobre o que está ambíguo ou faltando **dentro da fronteira do MVP** — **antes** de gerar qualquer história.

> 🎯 Se o assistente gerar histórias direto sem perguntar nada, seu prompt falhou. Bom insumo de requisitos começa com boas perguntas.

Anote 2 perguntas úteis que o assistente levantou (e que você mesmo não tinha pensado):

```
1.

2.
```

### Passo 2 — Geração

Só depois de responder às perguntas (com suposições razoáveis, já que o stakeholder do PetFood é fictício), peça a geração de 3–4 histórias no formato da instrução.

### Passo 3 — Crítica humana com INVEST (o passo que não pode ser terceirizado)

Pegue **cada** história gerada e avalie você mesmo contra o INVEST. Não peça isso pronto para a IA — este é o julgamento que a disciplina quer treinar em você.

| História | I | N | V | E | S | T | Problema encontrado |
|---|---|---|---|---|---|---|---|
| 1 | | | | | | | |
| 2 | | | | | | | |
| 3 | | | | | | | |

> Uma armadilha comum: histórias geradas por IA costumam ser **grandes demais** (violam o "Small") ou **não testáveis** (o benefício é vago). Caia em cima dessas duas.

### Passo 4 — Refino e Gherkin com caso de falha

Devolva suas críticas ao assistente ("esta história não é testável porque…") e peça o refino. Depois, para cada história refinada, produza os critérios de aceitação em Gherkin — **exigindo o cenário de falha**.

Exemplo de estrutura esperada:

```gherkin
Cenário: Registro de doação com sucesso
  Dado que sou um voluntário autenticado
  Quando registro uma doação de 10kg de ração
  Então o estoque total aumenta em 10kg
  E a doação aparece no histórico do doador

Cenário: Registro de doação com quantidade inválida  (← caminho triste)
  Dado que sou um voluntário autenticado
  Quando tento registrar uma doação com quantidade zero ou negativa
  Então o sistema rejeita o registro
  E exibe uma mensagem de erro clara
```

### Passo 5 — Priorização (você decide, a IA questiona)

Priorize suas histórias com **MoSCoW** (Must / Should / Could / Won't). Depois, use a IA como **advogado do diabo**: peça que ela questione sua priorização ("por que isso é Must e não Should?"). Você **não** precisa concordar — o objetivo é estressar sua justificativa de valor.

```
Minha priorização:
Must:
Should:
Could:
Won't (por agora):

O contra-argumento mais forte que a IA levantou:

```

---

## 5. A fronteira: o que a IA não faz

Complete com a turma no fechamento:

- A IA não pode **_______________** o requisito do stakeholder real (só quem faz isso é você, na conversa).
- A IA não pode decidir o **_______________** de negócio (isso é decisão da equipe com o parceiro).
- A IA não pode assumir a **_______________** pelo que a equipe entrega.
- Se você não consegue **_______________** cada história ao vivo, ela não é sua.

---

## 6. Entregáveis do lab

Ao final da aula, sua equipe deve ter:

1. ✅ A **instrução de projeto** da equipe (salva e versionada)
2. ✅ **3–4 histórias PetFood** refinadas, com tabela INVEST preenchida e Gherkin (com caso de falha)
3. ✅ A priorização MoSCoW dessas histórias com justificativa

---

## 7. Para a próxima aula (Quinta-feira) — Tarefa de transferência

🎯 **Agora vale para o seu projeto real.** Aplique o processo que treinou no PetFood — mas com uma diferença importante: o escopo do seu projeto **já foi aprovado pelo stakeholder** (Canvas de Visão, Semana 2). Você **não vai recriá-lo** — vai **auditá-lo e refiná-lo** com apoio de IA, e então gerar o backlog.

**Parte 1 — Auditoria do escopo (não recriação):**

- Adapte a instrução de projeto ao seu produto real (partindo do Canvas de Visão já aprovado)
- Use a IA para **auditar** o Canvas: que personas ficaram de fora? que requisito não funcional está implícito e não foi dito? a fronteira do MVP tem ambiguidades?
- Registre o que a auditoria revelou (sem alterar o escopo aprovado — isso se conversa com o stakeholder)

**Parte 2 — Backlog do projeto real:**

- Um backlog inicial de **5–8 histórias**, dentro da fronteira do MVP aprovada, cada uma com:
  - avaliação INVEST
  - pelo menos 1 critério de aceitação em Gherkin **com caso de falha**
  - classificação MoSCoW
- Uma lista de **perguntas em aberto** para levar ao stakeholder na quinta (as lacunas que a auditoria e a elicitação assistida revelaram)

**Entregar antes da sessão de quinta.**

> Na quinta você vai **refinar backlog e escopo com o stakeholder real**. As lacunas que a IA ajudou a encontrar são exatamente o que torna essa conversa valiosa — leve boas perguntas, não um backlog "pronto".

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE_

_Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 6 (seções 6.1–6.2) e Cap. 7 (seções 7.1.2–7.2.4)._ _Valente, M. T. Engenharia de Software Moderna. 2022. Cap. 3 — Requisitos._
