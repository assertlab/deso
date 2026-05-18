# Semana 12 — Segunda-feira

## Code Review como prática profissional (revisitado)

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **01/06/2026 | E132 | 18:50–20:30**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 3, seção 3.5.1 (Pull Requests e Code Reviews)
📖 _Engenharia de Software em Dimensões_ — Cap. 14, seção 14.6 (Documentação de Arquitetura com C4)

Se você leu na Semana 6, releia. O que você vai notar desta vez vai ser diferente.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Descrever o que mudou na sua compreensão de code review desde a Semana 6
- Aplicar um checklist avançado de code review a um PR real
- Articular por que code review é uma prática social tanto quanto técnica
- Identificar sinais de um review bom e de um review prejudicial

---

## 1. Uma pergunta antes de começar

> _"Se outra equipe fosse assumir o repositório de vocês amanhã, o que eles diriam sobre o código que vocês escreveram?"_

Anote sua resposta individual antes da discussão:

```
Sua resposta:


```

---

## 2. Você não é mais o mesmo desenvolvedor da Semana 6

Na Semana 6, você aprendeu o que é code review: a ideia de revisar código antes de mergear, checar erros óbvios, seguir convenções.

Agora estamos na Semana 12. Você tem 4 sprints de desenvolvimento real no currículo. Você já mergou código que quebrou coisa. Já revisou PR de colega e não pegou o bug que estava lá. Já recebeu feedback que foi difícil de ouvir — ou não recebeu feedback nenhum quando deveria ter recebido.

Com essa experiência, code review significa algo diferente.

### O que o código revela

Código bem revisado ao longo do tempo conta uma história:

```
Semana 6:  "Funciona? Então tá bom."
Semana 9:  "Funciona e tem teste? Ok."
Semana 12: "Funciona, tem teste, está legível, outra pessoa consegue manter?"
```

A pergunta da Semana 12 não é só "isso funciona?" — é "isso pode durar?".

---

## 3. Checklist avançado de Code Review

Use este checklist na quinta-feira durante o code review cruzado com outra equipe. Mas comece a pensar nele agora.

### Dimensão 1: Funcionalidade

- [ ] O código faz o que a user story diz que deveria fazer?
- [ ] Os casos de borda estão tratados? (e se o campo vier vazio? e se a API falhar?)
- [ ] Os erros são tratados de forma adequada ou apenas silenciados?

### Dimensão 2: Testes

- [ ] Existe cobertura de testes para a lógica crítica?
- [ ] Os testes são legíveis? Alguém que não escreveu consegue entender o que está sendo testado?
- [ ] Um teste passando significa que a funcionalidade funciona — ou apenas que o teste não falha?

### Dimensão 3: Legibilidade e manutenibilidade

- [ ] Os nomes de variáveis, funções e componentes comunicam intenção?
- [ ] Existe duplicação que poderia ser abstraída?
- [ ] O código vai precisar de comentário para ser entendido, ou ele se explica?

### Dimensão 4: Arquitetura e organização

- [ ] A mudança respeita a separação em camadas definida na Semana 7?
- [ ] Lógica de negócio está no lugar certo (não espalhada pelo frontend)?
- [ ] O PR adicionou responsabilidades a um módulo que já tinha responsabilidades demais?

### Dimensão 5: Documentação

- [ ] Decisões não-óbvias estão registradas (comentário, ADR, README)?
- [ ] O README reflete o estado atual do projeto?
- [ ] Os diagramas C4 precisam ser atualizados depois dessa mudança?

---

## 4. A parte que ninguém fala: code review é comunicação

O código de uma pessoa foi escrito com contexto que você não tem. Antes de dizer "isso está errado", pergunte: "Qual foi a razão para essa escolha?"

### Reviews que constroem vs. reviews que destroem

| Reviews que constroem | Reviews que destroem |
|---|---|
| "Considerei usar X aqui — o que você acha?" | "Isso está errado." |
| "Esse trecho ficou difícil de seguir para mim — poderia renomear Y para deixar mais claro?" | "Código confuso." |
| "Falta um teste para o caso em que o campo vem nulo" | "Sem testes suficientes." |
| "A função está fazendo duas coisas — faz sentido separar em duas?" | "Muito grande." |

A diferença não é só no tom — é na **ação que o comentário gera**. Um bom review deixa claro o que fazer, não apenas o que está ruim.

---

## 5. Comparação: onde você estava na Semana 6, onde está agora

Preencha a tabela abaixo com o que você se lembra (e o que notou relendo o conteúdo hoje):

| | Semana 6 | Semana 12 (agora) |
|---|---|---|
| O que eu verificava num PR | | |
| O que eu costumava ignorar | | |
| Como eu dava feedback | | |
| O que eu esperava receber como feedback | | |

---

## 6. Estudo de caso: o PR que passou por review e ainda quebrou prod

Cenário: uma equipe tinha um processo de code review bem definido. Todo PR precisava de aprovação de pelo menos dois membros antes de mergear. Mesmo assim, um PR aprovado por dois colegas derrubou o servidor de produção na sexta à noite.

**O que aconteceu?**

O PR mudava uma função de validação que era chamada em 7 lugares diferentes. O review focou na lógica nova — mas ninguém verificou onde mais essa função era usada.

**O que aprender com isso?**

```
Sua análise:


```

---

## 7. Para a quinta-feira

Na quinta, vocês vão realizar um code review cruzado formal: sua equipe vai revisar o repositório de outra equipe — e vice-versa.

**Prepare-se:**

- Organize os PRs abertos do repositório de vocês antes da aula
- Garanta que o README descreve como rodar o projeto localmente
- Identifique 2–3 pontos do código que você mesmo considera frágeis ou difíceis de entender

**O melhor review que você pode dar é aquele que você gostaria de ter recebido.**

---

## 8. Questão estruturante para reflexão

> _"Code review é uma prática técnica ou uma prática de cultura de equipe? Pode existir uma sem a outra?"_

Anote sua perspectiva antes da discussão:

```
Sua resposta inicial:


```

---

## 9. Para a próxima aula (Terça-feira)

📖 **Leitura obrigatória:** Cap. 19, seção 19.4 (Documentação e gerenciamento de conhecimento)

**Traga para a aula:** uma decisão técnica do projeto de vocês que nunca foi documentada. Não precisa ser grande — pode ser "por que usamos essa biblioteca" ou "por que a rota está organizada assim".

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
_Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 3, seção 3.5.1; Cap. 14, seção 14.6._
_Valente, M. T. Engenharia de Software Moderna. 2020. Cap. 10 — DevOps, seção 10.2._
