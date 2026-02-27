# EI2 — Documento de Requisitos

**CIN0136: Desenvolvimento de Software · CIn-UFPE · 2026.1**
**Entrega:** até domingo, 12/04/2026 às 23:59
**Peso:** componente extra (+10%) · individual

---

## Contexto

Na Semana 4, sua equipe construiu coletivamente o backlog do projeto — priorizou, negociou e chegou a um conjunto de funcionalidades acordadas com o stakeholder. Este exercício pede algo diferente: que **você**, individualmente, escreva sua própria versão do documento de requisitos para o mesmo projeto.

Isso não é duplicação de trabalho — é prática deliberada. Escrever requisitos força você a pensar no problema com profundidade que uma discussão em grupo não exige. O documento da equipe foi construído em colaboração; este é construído pela sua compreensão pessoal.

Você pode (e deve) usar o que aprendeu nas sessões com o stakeholder. Mas as decisões de escopo, priorização e escrita são suas.

---

## Objetivos de aprendizagem

Ao completar este exercício, você será capaz de:

- Escrever user stories no formato correto com critérios de aceitação verificáveis
- Aplicar o método MoSCoW para priorização justificada de requisitos
- Identificar e documentar requisitos não funcionais relevantes para o projeto
- Distinguir o problema do usuário da solução técnica

---

## O que entregar

Um único arquivo Markdown: `EI2-requisitos-[seu-nome].md`

O documento deve ter as seguintes seções, nesta ordem:

---

## Estrutura do documento

### 1. Contexto do projeto (máximo 1 página)

Descreva o problema que o seu projeto resolve. Escreva para alguém que não sabe nada sobre o projeto — um novo desenvolvedor que está entrando na equipe. Inclua:

- Quem é o stakeholder e qual organização representa
- O problema central (em linguagem não técnica)
- Quem são os usuários afetados
- O que acontece hoje sem o produto (workaround atual)

> **Atenção:** Esta seção descreve o **problema**, não a solução. Não mencione tecnologias, frameworks ou funcionalidades aqui.

---

### 2. User Stories (mínimo 5, máximo 10)

Cada user story deve seguir o formato padrão:

```
Como [persona],
quero [ação ou funcionalidade],
para [benefício ou objetivo].
```

Seguido de **critérios de aceitação** no formato Dado-Quando-Então (BDD):

```
Dado que [contexto/pré-condição],
Quando [ação do usuário],
Então [resultado esperado].
```

**Exemplo completo:**

```
Como coordenadora de projetos sociais,
quero registrar a presença dos beneficiários nas atividades,
para ter um histórico que comprove o impacto do programa.

Critérios de aceitação:
  Dado que estou na tela de registro de presença de uma atividade,
  Quando seleciono o nome de um beneficiário e confirmo,
  Então o sistema registra a presença com data e hora e exibe confirmação.

  Dado que um beneficiário já teve presença registrada nesta atividade,
  Quando tento registrar novamente,
  Então o sistema exibe aviso de presença duplicada e não registra novamente.
```

**Requisitos para as user stories:**
- Cada user story deve ter pelo menos **2 critérios de aceitação**
- A persona deve ser consistente com o que foi descoberto nas sessões com o stakeholder
- Os critérios de aceitação devem ser **verificáveis** — deve ser possível escrever um teste automatizado a partir deles
- Evite critérios vagos como "o sistema deve ser rápido" ou "a interface deve ser amigável"

---

### 3. Priorização MoSCoW

Organize suas user stories na tabela abaixo e **justifique** cada prioridade em uma frase:

| ID | User Story (resumo) | Prioridade | Justificativa |
|----|---------------------|-----------|---------------|
| US01 | [título resumido] | Must | [por que é essencial para o MVP] |
| US02 | | Should | |
| US03 | | Could | |
| ... | | | |

**Legenda MoSCoW:**
- **Must** — o produto não funciona sem isso. Se não entregar, o MVP falhou.
- **Should** — importante, mas existe workaround. Deve entrar se o tempo permitir.
- **Could** — desejável, mas claramente opcional para o MVP.
- **Won't** — identificado e explicitamente deixado de fora desta versão.

> A distribuição precisa fazer sentido. Um documento com 8 "Must" e 0 "Should/Could/Won't" não está priorizando — está listando tudo como crítico, o que é contraditório.

---

### 4. Requisitos Não Funcionais (mínimo 2)

Requisitos não funcionais descrevem **como** o sistema deve se comportar, não **o que** ele faz.

Para cada requisito não funcional, preencha:

**RNF01 — [categoria: Desempenho / Segurança / Usabilidade / Disponibilidade / outro]**

- **Descrição:** [o que o sistema deve garantir]
- **Métrica:** [como saber se o requisito foi atendido — seja específico]
- **Contexto:** [por que este requisito é relevante para este projeto]

**Exemplo:**
> **RNF01 — Usabilidade**
> - **Descrição:** O sistema deve ser utilizável por pessoas sem experiência prévia com software de gestão
> - **Métrica:** Um usuário novo deve conseguir registrar presença em menos de 3 cliques, sem treinamento
> - **Contexto:** O stakeholder informou que os voluntários têm perfis variados e baixa familiaridade com tecnologia

---

### 5. O que ficou de fora e por quê (opcional, mas valorizado)

Se você identificou necessidades do stakeholder que decidiu **não incluir** neste documento — nem como Won't — explique brevemente o raciocínio. Isso demonstra maturidade de escopo.

---

## Critérios de avaliação

| Critério | Peso | Descrição |
|----------|------|-----------|
| **Qualidade das user stories** | 35% | Formato correto, critérios verificáveis, persona consistente com o projeto real |
| **Critérios de aceitação** | 25% | Especificidade, testabilidade, cobertura de casos alternativos |
| **Priorização MoSCoW** | 25% | Distribuição razoável, justificativas fundamentadas |
| **Requisitos não funcionais** | 15% | Relevância para o projeto, métrica concreta |

---

## Instruções de entrega

1. Nomeie o arquivo `EI2-requisitos-[seu-nome].md` (ex: `EI2-requisitos-ana-silva.md`)
2. Entregue conforme instrução do professor (repositório da disciplina ou plataforma indicada)
3. Prazo: **12/04/2026 (domingo) às 23:59**
4. Atraso de até 48h → desconto de 20%. Após 48h → não pontua

---

## Dúvidas frequentes

**Posso usar as mesmas user stories que a equipe definiu?**
Você pode partir das mesmas necessidades identificadas com o stakeholder, mas a escrita, os critérios de aceitação e a priorização devem ser seus. Copiar o documento da equipe sem reelaboração não é válido.

**E se o meu documento divergir do documento da equipe?**
Divergência é bem-vinda — e muito mais interessante do que um documento idêntico ao da equipe. O exercício é individual justamente para capturar perspectivas diferentes sobre o mesmo problema.

**Preciso escrever user stories para funcionalidades técnicas (ex: autenticação, banco de dados)?**
Não. User stories descrevem valor para o usuário. "Como sistema, quero salvar dados no banco" não é uma user story válida. Foque nas necessidades do usuário final.

**Meu projeto tem mais de uma persona. Devo cobrir todas?**
Foque na persona principal para o MVP. Se houver uma segunda persona relevante, você pode incluir 1–2 user stories para ela, mas não é obrigatório.

---

*CIN0136 — Desenvolvimento de Software · CIn-UFPE · 2026.1*
