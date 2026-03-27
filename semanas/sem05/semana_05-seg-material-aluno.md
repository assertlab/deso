# Semana 5 — Segunda-feira

## O que é qualidade de software? (Não é só "funcionar")

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **30/03/2026 | E132 | 18:50–20:30**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 8, seções 8.1.1 a 8.1.8

Se você não leu antes de vir, tudo bem — mas leia antes da próxima aula.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar por que "funcionar" não é sinônimo de "ter qualidade"
- Identificar e descrever os principais atributos de qualidade de software (funcionalidade, desempenho, usabilidade, confiabilidade, segurança, manutenibilidade)
- Avaliar criticamente a qualidade de softwares conhecidos usando critérios objetivos
- Relacionar os atributos de qualidade com o projeto que sua equipe está desenvolvendo para o stakeholder

---

## 1. Uma pergunta antes de começar

> _"Dê uma nota de 1 a 5 para a qualidade do WhatsApp. Agora justifique."_

Use este espaço para anotar sua resposta antes da discussão:

```
Sua nota:
Justificativa:


```

Agora compare com a pessoa ao seu lado. Vocês deram a mesma nota? Se não, o que divergiu?

---

## 2. Qualidade de software: muito além de "funcionar"

Quando dizemos que um software "tem qualidade", estamos fazendo uma afirmação que envolve múltiplas dimensões. O Cap. 8 do livro-texto apresenta os **critérios de qualidade** que a Engenharia de Software utiliza para avaliar e medir essa qualidade de forma objetiva.

### Os atributos de qualidade

|Atributo|O que significa|Pergunta-chave|
|---|---|---|
|**Funcionalidade**|O software faz o que deveria fazer?|As features atendem aos requisitos?|
|**Desempenho**|O software responde rápido o suficiente?|O tempo de resposta é aceitável para o usuário?|
|**Usabilidade**|O software é fácil de usar?|O usuário consegue completar tarefas sem frustração?|
|**Confiabilidade**|O software funciona de forma consistente?|Ele falha com frequência? Como lida com erros?|
|**Segurança**|O software protege os dados do usuário?|Há vulnerabilidades conhecidas? Os dados estão protegidos?|
|**Manutenibilidade**|O software é fácil de modificar e evoluir?|Outro desenvolvedor consegue entender e alterar o código?|

### Uma analogia útil

Pense num carro. Ele "funciona" — liga e anda. Mas isso basta? E se freia mal (confiabilidade)? E se gasta 25 litros por quilômetro (desempenho)? E se o painel é tão confuso que você erra os botões no escuro (usabilidade)? E se qualquer oficina se recusa a mexer nele porque o motor é inacessível (manutenibilidade)?

Software é a mesma coisa. "Funcionar" é o mínimo — e muitas vezes nem é o mais difícil de alcançar.

---

## 3. Exercício: avaliando softwares conhecidos

Para cada software abaixo, dê uma nota de 1 (péssimo) a 5 (excelente) em cada atributo:

|Atributo|Instagram|SIGAA/SIG@|Seu projeto|
|---|---|---|---|
|Funcionalidade||||
|Desempenho||||
|Usabilidade||||
|Confiabilidade||||
|Segurança||||
|Manutenibilidade|—|—||

**Reflexão:** em qual atributo a maioria da turma discordou mais? Por que isso acontece?

```
Sua observação:


```

---

## 4. E no nosso projeto?

Nas últimas semanas, vocês construíram um backlog com user stories e critérios de aceitação em Gherkin (Semana 4 no Strateegia). Agora pense: os critérios de aceitação que vocês escreveram capturam apenas a funcionalidade, ou também dizem algo sobre outros atributos de qualidade?

**Qual atributo de qualidade é mais crítico para o seu stakeholder? Por quê?**

```
Atributo mais crítico:
Justificativa:


```

**Qual atributo de qualidade vocês ainda não discutiram como equipe?**

```
Atributo negligenciado:
O que poderíamos fazer de diferente:


```

---

## 5. A tensão entre atributos

Na prática, os atributos de qualidade competem entre si. Exemplos de tensões comuns:

- **Segurança × Usabilidade:** autenticação em dois fatores é mais segura, mas mais trabalhosa para o usuário
- **Desempenho × Manutenibilidade:** otimizações agressivas tornam o código mais rápido, mas mais difícil de manter
- **Funcionalidade × Confiabilidade:** adicionar muitas features aumenta a superfície de bugs

> _"Não existe software perfeito em todos os atributos. Existe software que faz as escolhas certas para o contexto."_

**Anote aqui:** qual tensão de atributos você acha mais relevante para o projeto da sua equipe?

```
Sua resposta:


```

---

## 6. Qualidade como postura, não como etapa final

Um conceito central que vamos aprofundar amanhã: qualidade não é algo que se "verifica no final do projeto". É uma **postura contínua** — presente em cada decisão, cada commit, cada conversa com o stakeholder.

Lembrem dos critérios de aceitação em Gherkin que vocês escreveram na Semana 4. Eles já são uma expressão de qualidade esperada: descrevem comportamentos que o software deve exibir. Se o software não atende ao critério, ele não tem qualidade naquela dimensão. Amanhã vamos explorar como medir e garantir isso de forma sistemática.

---

## 7. Questões estruturantes para reflexão

_(O professor selecionará duas para discutir com a turma)_

> _"Como a definição de 'qualidade' muda dependendo de quem avalia — o desenvolvedor, o usuário final, ou o stakeholder que financiou o projeto?"_

> _"É possível medir qualidade de software de forma objetiva? Ou toda avaliação de qualidade é, no fundo, subjetiva?"_

```
Sua posição:


```

---

## 8. Para a próxima aula (Terça-feira)

📖 **Leitura obrigatória:** Cap. 8, seções 8.2 e 8.3 (Técnicas de medição; Avaliação contínua)

**Traga para a aula:** uma reflexão sobre esta pergunta — _"Quando entregarmos o produto ao stakeholder, como ele saberá se tem qualidade?"_

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_ _Referência: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 8, seções 8.1.1–8.1.8._
