# Semana 4 — Segunda-feira

## Escopo do Produto Assistido por IA — Lab prático (caso PetFood)

**CIN0136: Desenvolvimento de Software | CIn-UFPE |** **E132 | 18:50–20:30**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 6, seções 6.1–6.2 (elicitação, vieses cognitivos) — revisão da Semana 3 📖 _Engenharia de Software Moderna_ (Valente) — Cap. 3 (MVP, escopo, personas)

**Traga para a aula:** seu material da Semana 3 e um notebook com acesso a um assistente de IA (Claude ou equivalente).

> ⚠️ **Regra de ouro desta aula:** a IA ajuda a **explorar e estruturar** o espaço do problema — mas o **recorte do escopo** (o que fica dentro e o que fica fora do MVP) é decisão da equipe, defendida com argumento. A IA amplia sua visão; ela não decide o produto por você.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Reconhecer que a equipe **não enxerga o mesmo escopo** antes de alinhá-lo explicitamente
- Usar IA para **explorar o espaço do problema** — personas, cenários e o problema por trás do problema — sem se ancorar na primeira ideia
- Construir um **Canvas de Visão enxuto** assistido por IA (problema, personas, proposta de valor)
- Definir a **fronteira do MVP** (dentro/fora) com justificativa — o passo que não se terceiriza
- Iniciar a **instrução de projeto** da equipe, que será completada na aula de terça

---

## 1. Divergência às cegas (antes de qualquer IA)

Antes de abrir qualquer assistente, um experimento. **Sozinho, sem conversar com ninguém e sem IA**, escreva em 3–4 frases qual é o escopo essencial do PetFood: que problema resolve, para quem, e qual o valor entregue.

```
Sua visão do escopo do PetFood (individual, sem consultar ninguém):




```

Agora comparem, em equipe. Quantas visões diferentes apareceram?

```
O que divergiu entre as visões da equipe:



```

> A lição: **"escopo" não é óbvio.** Mesmo em uma equipe pequena, cada pessoa enxerga um produto ligeiramente diferente. Alinhar essa visão é trabalho de engenharia — e é por isso que existe um artefato para isso (o Canvas de Visão). Se você deixar a IA falar primeiro, todo mundo se ancora na versão dela e essa divergência valiosa desaparece. Por isso pensamos sozinhos primeiro.

---

## 2. Explorar o espaço do problema com IA

Agora a IA entra — não para decidir o escopo, mas para **ampliar** o que a equipe consegue enxergar. Um bom assistente, bem instruído, funciona como um parceiro que pergunta "e você pensou em...?".

### Notas fictícias do "stakeholder PetFood" (seu insumo)

> _"A gente é uma ONG que recebe doações de ração e distribui para famílias de baixa renda que têm pets. Hoje controlamos tudo no WhatsApp e numa planilha, e vive dando confusão: a família diz que não recebeu, a gente não sabe quanto tem em estoque, e os doadores querem saber pra onde foi a ração deles. Precisava de um jeito de registrar as doações que chegam, ver quanto tem em estoque, e agendar as retiradas pelas famílias. Ah, e o doador adoraria ver que a doação dele foi entregue."_

Peça ao assistente que, a partir dessas notas, **levante** (não decida):

- Personas que talvez a equipe não tenha considerado (quem mais toca esse sistema?)
- Cenários de uso além do óbvio
- O "problema por trás do problema" (o que a ONG realmente quer resolver?)

Anote 2 coisas que a IA levantou e que a equipe **não** tinha pensado:

```
1.

2.
```

> 🧠 **Conexão com os vieses do Cap. 6:** a IA mal instruída sofre de **ancoragem** — fixa na primeira interpretação — e reforça seu **viés de confirmação** (concorda com o que você já pensava). Peça explicitamente que ela **desafie** sua visão, traga o que está faltando, aponte quem você esqueceu. É assim que ela vira ferramenta de ampliação, não espelho.

---

## 3. Canvas de Visão enxuto (assistido)

Consolide o que emergiu em um **Canvas de Visão enxuto**. A IA ajuda a estruturar e redigir; a equipe decide o conteúdo.

```
CANVAS DE VISÃO — PetFood

PROBLEMA
(qual dor real da ONG estamos resolvendo?)


PERSONAS PRINCIPAIS
(quem usa o sistema — e o papel de cada um)


PROPOSTA DE VALOR
(por que esse produto é melhor que o WhatsApp + planilha de hoje?)


```

> A IA é boa em transformar suas ideias soltas em texto organizado. Use-a para isso. Mas leia cada linha e pergunte: _"isso é verdade sobre o PetFood, ou é uma suposição genérica que ela inventou?"_ Corte o que for genérico.

---

## 4. A fronteira do MVP — o passo que não se terceiriza

Aqui está a decisão mais importante da aula, e a que **você não pode pedir pronta à IA**: o que entra no MVP e o que fica de fora.

Preencha em equipe. Cada item precisa de uma **justificativa de uma linha** — por que dentro, ou por que fora _por enquanto_.

| DENTRO do MVP | Por quê? |
|---|---|
| | |
| | |
| | |

| FORA (por enquanto) | Por quê? |
|---|---|
| | |
| | |
| | |

Agora use a IA como **advogado do diabo do recorte**: peça que ela questione suas escolhas ("por que rastrear a entrega ao doador está fora, se foi algo que o stakeholder pediu?"). Você **não precisa concordar** — o objetivo é estressar sua justificativa.

```
O contra-argumento mais forte que a IA levantou sobre nossa fronteira:



Mantivemos ou mudamos a decisão? Por quê?

```

> 🎯 Um bom recorte de MVP é aquele que você **consegue defender**. Se a IA derrubou sua justificativa com um argumento, ou a justificativa era fraca (revise) ou você precisa de mais informação do stakeholder (anote como pergunta em aberto).

---

## 5. Semente da instrução de projeto

Amanhã (terça) sua equipe vai gerar o backlog com apoio de IA — e para isso precisará de uma **instrução de projeto**: um bloco de contexto reutilizável que "ensina" o assistente a trabalhar do jeito da equipe. Ela **começa hoje**.

Registre as primeiras linhas com o que você já sabe:

```
CONTEXTO DO PROJETO
- Produto: PetFood — [uma frase do canvas]
- Personas principais: [do canvas]
- Fronteira do MVP: [resumo do que está dentro]

(amanhã completaremos com: papel do assistente, formato de história,
INVEST, formato Gherkin, o que não fazer)
```

---

## 6. Entregáveis do lab

Ao final da aula, sua equipe deve ter:

1. ✅ **Canvas de Visão PetFood enxuto** (problema, personas, proposta de valor)
2. ✅ **Fronteira do MVP** (dentro/fora) com justificativa por item
3. ✅ **Esboço inicial da instrução de projeto** (contexto do produto)

> 💾 Guarde esses três artefatos: eles são o **insumo da aula de terça**, onde viram o backlog.

---

## 7. Para a próxima aula (Terça-feira)

Amanhã pegamos o Canvas de Visão e a fronteira do MVP definidos hoje e os traduzimos em um **backlog de histórias de usuário** — com INVEST, Gherkin e priorização — tudo assistido por IA.

**Traga:** os três entregáveis de hoje e o mesmo acesso ao assistente de IA.

> 🔎 A tarefa de transferência para o **projeto real** virá na terça. Adianto o espírito dela: como o escopo do seu projeto real **já foi aprovado pelo stakeholder** (Semana 2), você não vai recriá-lo — vai **auditá-lo e refiná-lo** com o processo que treinou aqui.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE_ _Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 6 (seções 6.1–6.2)._ _Valente, M. T. Engenharia de Software Moderna. 2022. Cap. 3 — Requisitos._
