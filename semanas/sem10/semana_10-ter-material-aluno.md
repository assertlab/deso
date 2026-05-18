# Semana 10 — Terça-feira

## Manutenção, evolução e dívida técnica

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **19/05/2026 | E132 | 17:00–18:40**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 19, seções 19.1 (Evolução histórica da manutenção) e 19.4 (Documentação e gerenciamento de conhecimento)

📖 _Engenharia de Software Moderna_ — Cap. 9, seção Code Smells (relação com dívida técnica e manutenção)

**Traga para a aula:** uma observação honesta sobre onde a dívida técnica está mais evidente no código do seu projeto. Pode ser um nome de variável ruim, uma função longa que faz tudo, um arquivo que ninguém quer mexer. Não precisa ser formal.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Distinguir os quatro tipos de manutenção de software (corretiva, adaptativa, evolutiva, preventiva)
- Explicar por que software "nunca está pronto" em termos técnicos e econômicos
- Definir dívida técnica e identificar as formas como ela se acumula
- Reconhecer e nomear a dívida técnica no código do seu próprio projeto

---

## 1. Uma pergunta antes de começar

> _"Um software que foi entregue ao cliente e está funcionando perfeitamente — o trabalho do desenvolvedor acabou?"_

Use este espaço para anotar sua resposta antes da discussão:

```
Sua resposta inicial:


```

---

## 2. Software nunca está "pronto"

Uma das ilusões mais comuns sobre desenvolvimento de software é a ideia de que existe um ponto de conclusão — um momento em que o código está feito e o desenvolvedor pode seguir em frente definitivamente.

Na prática, a realidade é diferente. O ambiente muda: o sistema operacional recebe uma atualização, uma biblioteca de terceiros quebra a compatibilidade, a legislação impõe um novo requisito. Os usuários descobrem comportamentos inesperados. O negócio evolui e pede novas funcionalidades. O próprio código se deteriora com o tempo — não porque alguém mexeu nele errado, mas porque o entorno mudou.

O Garcia (seção 19.1) documenta essa evolução histórica: a manutenção de software começou a ser estudada seriamente nos anos 1970, quando as organizações perceberam que o custo de manter sistemas existentes superava o custo de construir sistemas novos. Hoje, estima-se que 60–80% do esforço total de uma equipe de desenvolvimento vai para manutenção, não para criação.

---

## 3. Os quatro tipos de manutenção

| Tipo | O que é | Exemplo |
|---|---|---|
| **Corretiva** | Consertar bugs e falhas | Usuário reportou que o login falha com senhas especiais |
| **Adaptativa** | Adaptar o sistema a mudanças externas | A API de pagamento mudou a versão — precisamos atualizar a integração |
| **Evolutiva** | Adicionar ou modificar funcionalidades conforme o negócio muda | O stakeholder quer um relatório em PDF que não estava no escopo original |
| **Preventiva** | Melhorar o sistema para facilitar manutenções futuras | Refatorar um módulo confuso antes que ele vire um problema sério |

**Identifique no seu projeto:** Qual tipo de manutenção ocorreu mais nas últimas semanas? Anote abaixo.

```
Tipo mais frequente:

Exemplo concreto:

```

**A manutenção mais difícil de justificar** é a preventiva. Corrigir um bug é urgente — ninguém questiona. Adaptar a uma nova API é necessário — ninguém questiona. Mas investir tempo para melhorar código que está "funcionando"? Isso exige uma cultura de engenharia madura.

---

## 4. Dívida técnica: quando os atalhos de hoje cobram juros amanhã

O conceito de **dívida técnica** foi introduzido por Ward Cunningham nos anos 1990. A metáfora é financeira, e é poderosa:

> _"Dívida técnica são os atalhos de design e implementação que tomamos no passado e que agora cobram 'juros' na forma de lentidão, fragilidade e dificuldade de mudança."_

Como qualquer dívida financeira, a dívida técnica tem dois componentes:

- **Principal:** o custo de fazer o certo que foi adiado
- **Juros:** o esforço adicional que cada mudança exige por causa do atalho tomado

A dívida em si não é necessariamente ruim — às vezes o atalho certo no momento certo permite entregar valor antes. O problema é quando a dívida se acumula sem ser paga, até o ponto em que o sistema se torna muito difícil de evoluir.

### Como a dívida se acumula

```
Atalho hoje → Código funciona → Não tem tempo de limpar → Próxima feature mais difícil
→ Outro atalho → Mais atalhos → Módulo que ninguém quer mexer → Sistema que "funciona mas..."
→ Reescrita completa (ou abandono)
```

### Dívida técnica vs. legado

O Garcia (seção 19.3) apresenta um conceito que pode surpreender: um sistema pode ser "legado" mesmo sendo recente. "Legado" não é sobre a idade do código — é sobre a dificuldade de mudá-lo. Um microsserviço com dois anos de idade, escrito em linguagem moderna, mas sem testes e com acoplamento excessivo, já é um sistema legado.

**Reflexão:** Existe alguma parte do código do seu projeto que já se comporta como "legado moderno"? Descreva:

```
Parte do código:

Por que é difícil de mudar:

O que precisaria ser feito para melhorar:

```

---

## 5. Por que empresas acumulam dívida técnica?

Esta é a questão central do debate de hoje.

Se todo desenvolvedor sabe que dívida técnica é um problema, por que ela se acumula tão frequentemente? Algumas respostas comuns — e suas críticas:

| Justificativa comum | O que ela esconde |
|---|---|
| "Não tivemos tempo" | Tempo para refatorar nunca aparece — precisa ser planejado |
| "O prazo era urgente" | Urgência hoje = mais urgência amanhã, com juros |
| "Funciona, por que mudar?" | Funciona agora, sob as condições atuais |
| "É legível para quem escreveu" | Só para quem escreveu, e só enquanto lembra |
| "Vamos refatorar depois" | "Depois" raramente chega |

O problema mais profundo é **invisibilidade**: dívida técnica não aparece nos relatórios de progresso. Features aparecem no Kanban; código ruim, não. Os incentivos estão todos apontando para entregar mais, não para entregar melhor.

---

## 6. Debate estruturado

A turma vai discutir a seguinte questão em grupos pequenos (5 min) e depois compartilhar com a turma (10 min):

> _"Se arquitetura ruim leva a software ruim, por que empresas acumulam dívida técnica?"_

Use este espaço para registrar sua posição antes do debate:

```
Sua análise:


O que você acha que poderia mudar isso:


```

---

## 7. Documentação como ferramenta de manutenção

O Garcia (seção 19.4) trata documentação não como burocracia, mas como **gerenciamento de conhecimento**: o que foi decidido, por que foi decidido, e o que foi descartado.

Para o contexto de uma equipe pequena trabalhando num projeto de semestre, as formas mais valiosas de documentação são:

- **Commits descritivos:** `refactor: extrair função calcularDesconto` diz muito mais do que `fix`
- **README atualizado:** novos integrantes (ou você mesmo em 3 semanas) precisam conseguir rodar o projeto
- **Comentários de decisão:** não explique *o que* o código faz (o código já diz) — explique *por que* a decisão foi tomada assim: `// Usamos array aqui porque precisamos de ordem de inserção; Set não preserva`
- **PR descriptions:** cada pull request é um registro de uma mudança — a descrição é parte da documentação

**Checklist de documentação do seu projeto:**

- [ ] README explica como rodar o projeto do zero
- [ ] Commits têm mensagens que comunicam intenção
- [ ] Decisões técnicas importantes estão registradas em algum lugar
- [ ] Testes servem como documentação executável do comportamento esperado

---

## 8. Olhando para o próprio projeto

Esta semana, o Sprint 3 começa. É o momento de parar e olhar para o que foi construído com olhos críticos.

**Exercício de reflexão individual (3 min):**

Abra o repositório do seu projeto. Navegue pelo código. Responda:

```
1. Qual é o arquivo que você menos quer abrir para fazer uma mudança? Por quê?


2. Existe algum trecho que você escreveu e que hoje você não escreveria da mesma forma?


3. Se um novo integrante entrasse na equipe amanhã, qual seria a primeira dificuldade dele?


```

Estas não são perguntas com resposta certa. São o diagnóstico do ponto de partida do Sprint 3.

---

## 9. Questão estruturante para reflexão

> _"O software nunca está 'pronto' — mas há um momento em que ele está 'bom o suficiente'. Como uma equipe decide onde está esse limite? Quem deveria decidir?"_

Anote sua perspectiva antes da discussão:

```
Sua resposta inicial:


```

---

## 10. Para a próxima aula (Quinta-feira)

**Na quinta:**

- Bloco 1 (2h): exercício de refactoring em 5 passos progressivos com testes verdes — venha com o repositório clonado e o ambiente configurado
- Bloco 2 (2h): refatorações no projeto real + features complementares do Sprint 3

**Prepare-se:**

- Certifique-se de que o ambiente de desenvolvimento está funcionando na sua máquina
- Identifique 2–3 trechos do projeto que você quer refatorar durante o bloco 2
- Opcional: instale a extensão SonarLint no VS Code para ver code smells em tempo real

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
_Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 19, seções 19.1 e 19.4. Valente, M. T. Engenharia de Software Moderna. 2020. Cap. 9._
