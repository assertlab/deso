# Semana 5 — Terça-feira

## Medição de qualidade e cultura de qualidade contínua

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **31/03/2026 | E132 | 17:00–18:40**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 8, seções 8.2 e 8.3

**Traga para a aula:** uma reflexão sobre esta pergunta — _"Quando entregarmos o produto ao stakeholder, como ele saberá se tem qualidade?"_

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Descrever técnicas para medir qualidade de software (métricas de código, análise estática, revisões)
- Explicar o conceito de avaliação contínua e por que qualidade não é "verificada no final"
- Analisar os critérios de aceitação em Gherkin da Semana 4 sob a ótica de qualidade
- Entender como a qualidade será operacionalizada no Definition of Done da equipe (quinta-feira)

---

## 1. A pergunta que trouxemos de segunda

> _"Quando entregarmos o produto ao stakeholder, como ele saberá se tem qualidade?"_

Anote sua reflexão antes da discussão:

```
Sua resposta:


```

O ponto central é: **qualidade precisa ser demonstrável**, não apenas afirmada. Quando você diz "o software tem qualidade", o stakeholder precisa ver evidências — não é uma questão de confiança, é uma questão de profissionalismo.

---

## 2. Como medir qualidade?

Na segunda, discutimos _o que_ é qualidade. Agora a pergunta é: _como sabemos se ela existe?_

### Técnicas de medição de qualidade

|Técnica|O que mede|Exemplo prático|
|---|---|---|
|**Métricas de código**|Complexidade, duplicação, tamanho|"Este módulo tem complexidade ciclomática 15 — alto demais"|
|**Análise estática**|Padrões de código, potenciais bugs, vulnerabilidades|ESLint reportando erros antes do commit|
|**Revisão por pares**|Legibilidade, design, correção lógica|Code review em Pull Requests|
|**Testes automatizados**|Funcionalidade, regressão, edge cases|Suite de testes rodando a cada PR|
|**Critérios de aceitação**|Comportamento esperado pelo usuário/stakeholder|Cenários Gherkin: Dado/Quando/Então|
|**Feedback do usuário**|Usabilidade, funcionalidade percebida|Stakeholder dizendo "não entendi este botão"|

---

## 3. Os critérios Gherkin da Semana 4 como expressão de qualidade

Na Semana 4, vocês escreveram critérios de aceitação em Gherkin no Strateegia. Cada critério no formato Dado/Quando/Então é uma declaração de qualidade esperada: descreve um comportamento que o software deve exibir para ser considerado "pronto".

Agora, a pergunta crítica: **os critérios que vocês escreveram capturam mais do que funcionalidade?**

### Análise rápida dos seus critérios Gherkin

Escolha 2–3 critérios de aceitação que sua equipe escreveu na Semana 4 e classifique:

|Critério Gherkin (resumo)|Atributo que captura|O que falta?|
|---|---|---|
||||
||||
||||

**Perguntas para reflexão:**

- Algum critério fala sobre velocidade de resposta (desempenho)?
- Algum critério descreve o que acontece quando algo dá errado (confiabilidade)?
- Algum critério trata de proteção de dados (segurança)?

Se a maioria dos critérios captura apenas funcionalidade, é hora de expandir — e o Definition of Done que a equipe vai definir na quinta-feira é o lugar certo para isso.

---

## 4. Qualidade contínua: não é uma fase, é uma postura

O conceito central da seção 8.3 do livro é a **avaliação contínua de qualidade**: em vez de verificar qualidade no final (quando já é tarde demais), incorporá-la em cada etapa do desenvolvimento.

### A analogia da receita de bolo

Se você está fazendo um bolo e só prova depois de pronto, pode descobrir que esqueceu o sal — e agora precisa jogar fora e recomeçar. Se você prova a massa antes de assar, o recheio antes de montar, e o resultado antes de servir, os problemas aparecem quando ainda são baratos de corrigir.

Software funciona da mesma forma:

```
  "Verificar no final"               "Qualidade contínua"
  ─────────────────────               ─────────────────────
  Código → Código → Código            Código → Review → Verifica
  → Código → Código → TESTE           → Código → Review → Verifica
  → MUITOS BUGS → RETRABALHO          → Código → Review → Verifica
                                       → POUCOS BUGS → CONFIANÇA
```

### Na prática do projeto

|Momento|Prática de qualidade contínua|
|---|---|
|Antes de codar|Discutir a solução com a equipe (evitar retrabalho)|
|No código|ESLint + Prettier formatando automaticamente (quando configurar)|
|Antes do merge|Code review + critérios de aceitação verificados|
|A cada sprint|Review com stakeholder (qualidade percebida)|
|Ao final|Testes automatizados + demo final|

Vocês ainda não configuraram todas essas práticas no projeto — e tudo bem. O Sprint 1, que começa na quinta, é a oportunidade de definir o **Definition of Done** da equipe: o conjunto mínimo de critérios que uma feature precisa atender para ser considerada "pronta". Qualidade contínua começa aí.

---

## 5. Debate: qualidade custa caro?

> _"Qualidade custa caro? Ou a falta de qualidade custa mais?"_

Considere estes cenários:

**Cenário A:** A equipe implementa uma feature em 2 dias, sem nenhuma verificação. Na semana seguinte, um problema aparece e leva 3 dias para ser encontrado e corrigido. Total: 5 dias.

**Cenário B:** A equipe implementa a mesma feature em 3 dias, verificando critérios de aceitação a cada passo. Na semana seguinte, um problema é detectado rapidamente. Total: 3 dias + 10 minutos.

Qual cenário vocês preferem viver no Sprint 1?

```
Sua reflexão:


```

---

## 6. O que vem pela frente: da qualidade à prática

O tema de qualidade abre um arco que vai se desdobrar nas próximas semanas:

|Semana|Como a qualidade ganha corpo|
|---|---|
|**5 (quinta, 09/04)**|Definição dos atributos prioritários + Definition of Done + início do Sprint 1|
|**6**|Design e Arquitetura — manutenibilidade ganha forma com princípios de organização do código|
|**8**|Lab de Testes com Vitest — testes automatizados como ferramenta de qualidade|
|**9**|Testes de aceitação + BDD — os cenários Gherkin da Semana 4 viram testes executáveis|

Qualidade não é um tema de uma semana. É um tema que permeia o semestre inteiro.

---

## 7. Questão estruturante para reflexão

> _"Se qualidade é tão importante, por que tantas empresas entregam software com bugs? O que impede a qualidade na prática — falta de competência, falta de tempo, ou falta de cultura?"_

```
Sua posição:


```

---

## 8. Para quinta-feira (09/04 — quinta da Semana 5, deslocada)

⚠️ A quinta-feira desta semana é **Quinta-feira Santa (02/04)** — sem aula. A aula prática acontece em **09/04**.

**Na quinta-feira 09/04 você vai:**

- Bloco 1 (2h): Definir os atributos de qualidade prioritários do projeto + revisar critérios Gherkin + definir o Definition of Done da equipe
- Bloco 2 (2h): Início do desenvolvimento do Sprint 1 — primeiras features do backlog

**Prepare-se:**

- Releia os critérios de aceitação em Gherkin que sua equipe escreveu na Semana 4
- Pense em quais atributos de qualidade são mais importantes para o stakeholder do seu projeto
- Traga uma proposta de Definition of Done para discutir com a equipe

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_ _Referência: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 8, seções 8.2–8.3._
