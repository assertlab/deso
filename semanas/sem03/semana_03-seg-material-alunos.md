# Semana 3 — Segunda-feira

## Requisitos funcionais, não funcionais e técnicas de elicitação

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **17:00–18:40**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 6, seções 6.1 e 6.2 _(Requisitos Funcionais e Não Funcionais; Técnicas de Elicitação)_

📖 _Engenharia de Software Moderna_ (Valente) — Cap. 3, introdução _(Histórias de Usuário; MVP — disponível em engsoftmoderna.info)_

Se não leu antes de vir, leia antes da terça. A aula de amanhã assume que você conhece o vocabulário básico de requisitos.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Distinguir requisitos funcionais de não funcionais e classificar exemplos concretos
- Nomear pelo menos três técnicas de elicitação e indicar quando cada uma é adequada
- Identificar, no próprio projeto, requisitos já levantados que ainda não foram formalizados

---

## 1. Exercício de abertura — 2 minutos

> _Você tem 2 minutos. Escreva tudo que o WhatsApp faz. Seja específico._

```
[Escreva aqui — não leia o resto da página antes de tentar]




```

Após a atividade coletiva em sala, use este espaço para registrar o que a sua lista deixou de fora:

```
O que eu não listei mas os colegas listaram:


O que aprendi com a divergência das listas:


```

---

## 2. O problema de descrever software

Quando diferentes pessoas descrevem o mesmo sistema, elas falam de coisas distintas: o que ele faz, como ele funciona por dentro, como parece na tela, o que acontece quando falha. Nenhuma perspectiva está errada — mas todas juntas ainda são incompletas.

**Requisitos** são a tentativa de tornar explícito e verificável o que o sistema precisa ser.

> _Um bom requisito é aquele sobre o qual duas pessoas da equipe leem e entendem a mesma coisa._

---

## 3. Requisitos Funcionais

Descrevem **o que o sistema deve fazer** — comportamentos, funções, serviços.

A característica central: é possível verificar se o requisito foi atendido. Ou o sistema faz, ou não faz.

**Exemplos:**

|Requisito|Verificável?|
|---|---|
|"O usuário pode enviar uma mensagem de texto."|✅ Sim — é possível testar|
|"O usuário pode criar grupos de até 1024 participantes."|✅ Sim — número concreto|
|"O sistema deve ter uma boa interface."|❌ Não — "boa" não é verificável|

**Do seu projeto:**

Liste dois requisitos funcionais que você já identificou nas conversas com o stakeholder — mesmo que ainda informais:

```
RF1:


RF2:


```

---

## 4. Requisitos Não Funcionais

Descrevem **como o sistema deve se comportar** — qualidade, restrições, atributos. São também chamados de _atributos de qualidade_ ou _requisitos de qualidade_.

Categorias principais:

|Categoria|Exemplo|
|---|---|
|**Desempenho**|"A página deve carregar em menos de 2 segundos."|
|**Segurança**|"Senhas devem ser armazenadas com hash bcrypt."|
|**Usabilidade**|"O sistema deve ser acessível por leitores de tela (WCAG 2.1)."|
|**Manutenibilidade**|"O código deve ter cobertura mínima de 80% de testes."|
|**Disponibilidade**|"O sistema deve estar disponível 99,5% do tempo."|
|**Escalabilidade**|"O sistema deve suportar até 500 usuários simultâneos."|

**Atenção:** requisitos não funcionais mal escritos são inúteis. Compare:

|Mal escrito|Bem escrito|
|---|---|
|"O sistema deve ser rápido."|"O sistema deve responder a qualquer requisição em menos de 500ms."|
|"O sistema deve ser seguro."|"Dados sensíveis devem ser criptografados em repouso com AES-256."|
|"O sistema deve ser fácil de usar."|"Um usuário sem treinamento deve conseguir completar o cadastro em menos de 3 minutos."|

**Do seu projeto:**

Liste dois requisitos não funcionais que você acredita que o projeto vai precisar. Pode ser uma hipótese — você confirmará com o stakeholder na quinta:

```
RNF1 (categoria: ____________):


RNF2 (categoria: ____________):


```

---

## 5. Quiz: Funcional ou Não Funcional?

Classifique cada item abaixo. Para os que forem não funcionais, indique também a categoria:

|Requisito|F ou NF?|Categoria (se NF)|
|---|---|---|
|"O usuário pode filtrar produtos por categoria."|||
|"O sistema deve processar até 500 requisições simultâneas."|||
|"O usuário pode redefinir sua senha."|||
|"A interface deve seguir as diretrizes WCAG 2.1."|||
|"O sistema deve notificar o usuário quando o estoque cair abaixo de 10 unidades."|||
|"O sistema deve criptografar as mensagens de ponta a ponta."|||

_(Respostas discutidas em sala)_

---

## 6. Técnicas de Elicitação

Elicitação é o processo de extrair requisitos das pessoas que têm o conhecimento do problema. O nome é técnico, mas a ideia é simples: entender o que o parceiro precisa de verdade, não apenas o que ele pede.

### Entrevistas

A técnica mais comum — e a mais mal aplicada. O erro clássico é perguntar "o que você quer?" em vez de explorar o problema.

Perguntas que abrem território:

|Pergunta|Por que funciona|
|---|---|
|"Me conta como você faz isso hoje."|Revela o processo atual, não o desejo|
|"O que acontece quando dá errado?"|Revela casos de falha não óbvios|
|"Quem mais usa isso? O que eles precisam?"|Revela stakeholders esquecidos|
|"O que tornaria isso um sucesso para você?"|Revela critério de aceitação implícito|
|"O que você faz hoje para compensar o que o sistema não faz?"|Revela lacunas não verbalizadas|

**Anote aqui** — uma pergunta que você faria ao seu stakeholder que ainda não fez:

---

### Workshops de Requisitos

Útil quando há múltiplos stakeholders com perspectivas diferentes ou conflitantes. O workshop cria um espaço estruturado para negociação explícita — todo mundo na mesma sala, tomando decisões juntos.

Para os projetos deste semestre: provavelmente não necessário, mas reconheça quando a situação pede.

---

### Observação

Observar o usuário trabalhando no ambiente natural — sem perguntar, só assistindo.

Revela o que ninguém pensa em mencionar porque "é óbvio para quem trabalha aqui". Exemplos clássicos: o caderninho ao lado do computador com anotações que o sistema não suporta; a planilha auxiliar que todo mundo usa mas ninguém documentou; o atalho de teclado que a equipe inteira conhece mas nenhum usuário novo consegue descobrir.

**Pergunta para reflexão:**

> Você visitou o espaço de trabalho do seu parceiro? Viu como eles operam hoje? O que você observou que não estava no briefing inicial?

```
[Anote aqui]


```

---

### Prototipagem como Elicitação

Um protótipo não é apenas a apresentação de uma solução — é uma **pergunta visual**. Muitos clientes não conseguem descrever o que querem em palavras, mas reconhecem imediatamente quando veem algo que não é o que queriam.

> _"Não é bem isso"_ é uma das respostas mais valiosas que um protótipo pode provocar.

Quando o parceiro rejeita algo no protótipo, ele está revelando um requisito que não sabia que tinha. Registre tudo.

---

## 7. As técnicas que você já usou sem saber

Reflita sobre as Semanas 1 e 2:

|Técnica|Você usou?|O que descobriu com ela?|
|---|---|---|
|Entrevistas com o stakeholder|||
|Observação do contexto de trabalho|||
|Prototipagem (wireframes, sketches)|||
|Workshops com a equipe para debater requisitos|||

**O que você ainda não sabe sobre o problema do parceiro?**

_(Anote as lacunas — elas vão guiar a sessão de quinta-feira)_

```
1.

2.

3.
```

---

## 8. Questão estruturante para reflexão

> _"Qual é o risco de começar a implementar sem requisitos bem definidos? E qual é o risco de esperar demais para começar enquanto tenta definir tudo?"_

Esta tensão não tem resposta certa. É a questão central da Engenharia de Requisitos em contextos ágeis — e você vai vivê-la neste semestre.

```
Sua perspectiva antes do debate:


```

---

## 9. Para a próxima aula (Terça-feira)

📖 **Leitura obrigatória:** Garcia, Cap. 7, seções 7.1.2–7.2.4 + Valente, Cap. 3 (User Stories + priorização)

**Traga para a aula:** pelo menos 3 user stories do seu projeto escritas no formato abaixo. Podem ser imperfeitas — serão o ponto de partida do workshop:

```
Como [persona / tipo de usuário],
quero [funcionalidade / ação],
para [benefício / resultado esperado].
```

**Exemplo:**

> "Como gestor da organização, quero visualizar um relatório mensal de atendimentos para apresentar à diretoria sem precisar compilar dados manualmente."

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_ _Referência principal: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 6._ _Referência complementar: Valente, M. T. Engenharia de Software Moderna. 2022. Cap. 3. engsoftmoderna.info_
