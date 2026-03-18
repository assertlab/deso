# Semana 3 — Terça-feira

## User Stories, backlog e priorização formal

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **18:50–20:30**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 7, seções 7.1.2 a 7.2.4 _(User Stories; Epics; Features; MoSCoW; WSJF)_

📖 _Engenharia de Software Moderna_ (Valente) — Cap. 3 _(Histórias de Usuário; critérios INVEST; priorização — engsoftmoderna.info)_

**Traga para esta aula:** pelo menos 3 user stories do seu projeto no formato padrão. Elas serão o ponto de partida dos workshops.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Escrever user stories no formato padrão com persona e benefício claros
- Avaliar a qualidade de uma story usando os critérios INVEST
- Escrever critérios de aceitação verificáveis no formato Gherkin
- Priorizar um backlog usando MoSCoW e defender as escolhas

---

## 1. Do requisito à user story

Ontem você aprendeu a distinguir o que o sistema deve _fazer_ do que ele deve _ser_. Hoje você vai aprender a escrever esses requisitos do ponto de vista de quem usa — e não do ponto de vista do sistema.

|Requisito tradicional|User Story|
|---|---|
|"O sistema deve autenticar usuários."|"Como usuário cadastrado, quero fazer login com e-mail e senha para acessar minha conta com segurança."|
|"O sistema deve gerar relatórios."|"Como gestor, quero exportar o relatório mensal em PDF para apresentar à diretoria sem compilar dados manualmente."|

**O que a user story tem que o requisito tradicional não tem:**

- A **persona** — quem usa, especificamente
- O **propósito** — por que isso importa para ela
- O foco no **usuário**, não no sistema

---

## 2. O formato padrão

```
Como [persona / tipo de usuário],
quero [funcionalidade / ação],
para [benefício / resultado esperado].
```

**Por que cada parte existe:**

**[persona]** → Force-se a pensar em quem usa de verdade. "Usuário" genérico é uma armadilha — quando todo mundo é o usuário, ninguém é. Personas diferentes têm necessidades diferentes.

**[funcionalidade]** → Descreve a ação, não a implementação técnica. "Quero ver um dashboard com gráficos de barras usando D3.js" já está dizendo como implementar — isso não é função da story.

**[benefício]** → Por que essa funcionalidade existe? Qual problema ela resolve? Uma story sem benefício claro é um sinal de que o requisito pode não ser necessário.

---

## 3. Workshop 1 — Revisar as stories que você trouxe (10 min)

Em dupla com um colega, revisem mutuamente as stories de cada um. Para cada story, verifiquem:

1. A persona é específica? (Não é apenas "usuário")
2. O benefício está claro — ou é genérico demais?
3. Dá para saber quando a story estará pronta?

**Suas stories originais:**

```
Story 1:


Story 2:


Story 3:
```

**Após a revisão em dupla — versões melhoradas:**

```
Story 1 (revisada):


Story 2 (revisada):


Story 3 (revisada):
```

---

## 4. INVEST — critérios de qualidade de uma user story

INVEST é um acrônimo para avaliar se uma story está bem escrita:

|Letra|Critério|Pergunta de verificação|
|---|---|---|
|**I**|Independent|Pode ser desenvolvida sem depender de outra story?|
|**N**|Negotiable|É uma conversa, não um contrato — pode ser ajustada?|
|**V**|Valuable|Entrega valor real para o usuário — não apenas para o desenvolvedor?|
|**E**|Estimable|É possível estimar o esforço necessário?|
|**S**|Small|Cabe num sprint de 2 semanas?|
|**T**|Testable|Dá para verificar objetivamente se está pronta?|

### Stories problemáticas — identifique o critério violado

|Story|Critério violado|Por quê?|
|---|---|---|
|"Como usuário, quero que o sistema seja rápido."|||
|"Como dev, quero refatorar o banco de dados para melhorar a performance."|||
|"Como gestor, quero gerenciar usuários, produtos, pedidos e relatórios."|||
|"Como usuário, quero fazer checkout — só depois que o carrinho estiver implementado."|||

_(Respostas discutidas em sala)_

---

## 5. Critérios de Aceitação

Um critério de aceitação responde: **quando esta story estará concluída?**

Sem critérios explícitos, "pronto" é uma opinião. Com critérios, é um fato verificável.

### Formato Gherkin: Dado / Quando / Então

```
Dado que [contexto / pré-condição]
Quando [ação do usuário]
Então [resultado esperado]
```

### Exemplo completo

**Story:** "Como usuário, quero redefinir minha senha para recuperar o acesso à conta."

**Critério 1 — fluxo principal:**

```
Dado que o usuário está na tela de login
Quando clica em "Esqueci minha senha" e informa o e-mail cadastrado
Então recebe um e-mail com link de redefinição válido por 1 hora
```

**Critério 2 — redefinição bem-sucedida:**

```
Dado que o usuário recebeu o link e clica dentro do prazo
Quando insere uma nova senha com no mínimo 8 caracteres
Então a senha é atualizada e ele é redirecionado para o login
```

**Critério 3 — caso de falha:**

```
Dado que o link de redefinição já expirou
Quando o usuário tenta acessá-lo
Então vê uma mensagem de erro e pode solicitar um novo link
```

**Observe:** os casos de falha são tão importantes quanto os casos de sucesso. Um produto que funciona perfeitamente em condições ideais e colapsa na primeira exceção não é um produto de qualidade.

---

### Escreva um critério de aceitação para uma das suas stories

Escolha a story mais importante do seu projeto e escreva pelo menos dois cenários:

**Story escolhida:**

**Critério 1:**

```
Dado que
Quando
Então
```

**Critério 2 (caso alternativo ou de falha):**

```
Dado que
Quando
Então
```

---

## 6. A hierarquia do backlog

Nem tudo no backlog tem o mesmo tamanho. A hierarquia ajuda a organizar:

```
Epic  →  Feature  →  User Story  →  Tarefa técnica (Task)
```

**Exemplo:**

|Nível|Exemplo|
|---|---|
|**Epic**|Autenticação de usuários|
|**Feature**|Login com e-mail e senha|
|**User Story**|"Como usuário cadastrado, quero fazer login com e-mail e senha para acessar minha conta."|
|**Task**|Criar rota `POST /auth/login` no backend|

**Regra prática:** se uma story não cabe num sprint de 2 semanas, é provável que seja uma Feature ou Epic disfarçada. Quebre.

---

## 7. MoSCoW — priorização explícita

MoSCoW é um método de classificar itens do backlog por prioridade:

|Categoria|O que significa|Critério de enquadramento|
|---|---|---|
|**M** — Must Have|Imprescindível|Sem isso, o produto não funciona ou perde todo o valor|
|**S** — Should Have|Importante|Alto valor, mas o lançamento pode acontecer sem isso|
|**C** — Could Have|Desejável|Bom ter se houver tempo — descartável sem grande impacto|
|**W** — Won't Have (now)|Fora do escopo atual|Reconhecido e explicitamente adiado — não é "nunca", é "não agora"|

### A armadilha do "tudo é Must Have"

Se você classificar 80% do backlog como Must Have, o problema está na conversa, não nas funcionalidades. Use estas perguntas para destravar a priorização com o parceiro:

- _"Se você pudesse lançar apenas 3 funcionalidades amanhã, quais seriam?"_
- _"O que acontece com seu trabalho/negócio se essa funcionalidade não existir no lançamento?"_
- _"Quem ficaria prejudicado se adiássemos isso para a segunda versão?"_

**Won't Have não é Never Have.** É uma promessa de honestidade: você reconhece a funcionalidade como válida, mas a exclui conscientemente do escopo atual. Isso precisa ser comunicado ao stakeholder — não silenciado.

---

## 8. Workshop 2 — Priorizar o backlog do projeto (10 min)

Em equipe, abram o backlog de vocês e classifiquem cada story em M, S, C ou W.

**Regras do workshop:**

- No máximo **40%** das stories podem ser Must Have
- Pelo menos **20%** devem ser Won't Have (now)
- Toda classificação precisa de uma justificativa em uma frase

_(A restrição de 40%/20% é artificial — existe para forçar a negociação explícita. No projeto real, o stakeholder terá sua própria visão.)_

**Backlog priorizado — registre aqui:**

|Story (resumo)|M/S/C/W|Justificativa|
|---|---|---|
||||
||||
||||
||||
||||
||||

---

## 9. Definindo o MVP

MVP (Produto Mínimo Viável) é o menor conjunto de funcionalidades que entrega valor real para o usuário.

**Regra prática para o projeto:**

- Todas as stories **Must Have** → compõem o MVP
- Stories **Should Have** → Sprint 2 ou 3
- Stories **Could Have** → backlog futuro, se houver tempo
- Stories **Won't Have** → documentar e comunicar ao stakeholder

**Pergunta para levar para a quinta-feira:**

> _"Se vocês tivessem que apresentar algo funcionando para o stakeholder na próxima semana, o que precisaria existir para que ele ficasse satisfeito?"_

---

## 10. Questão estruturante para reflexão

> _"Como você lida com a situação em que o stakeholder quer mudar os requisitos depois que o desenvolvimento já começou?"_

```
Sua perspectiva antes do debate:


```

---

## 11. Para a quinta-feira

**Tragam para a aula:**

- [ ] Backlog de user stories formais (formato padrão + critérios de aceitação)
- [ ] Priorização MoSCoW justificada para cada story
- [ ] Canvas de Visão do Projeto preenchido (ao menos um rascunho)
- [ ] Protótipo hi-fi refinado para apresentar ao stakeholder

**O que vai acontecer na quinta:**

- Bloco 1 (2h): formalizar tudo — converter backlog informal em stories, preencher Canvas de Visão, definir MVP
- Bloco 2 (2h): sessão com o stakeholder — apresentar protótipo + backlog + MVP para aprovação

Esta é a sessão de fechamento de escopo do Sprint 0. A partir daí, o que vai ser construído estará definido.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_ _Referência principal: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 7._ _Referência complementar: Valente, M. T. Engenharia de Software Moderna. 2022. Cap. 3. engsoftmoderna.info_
