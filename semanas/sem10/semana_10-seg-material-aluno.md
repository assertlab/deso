# Semana 10 — Segunda-feira

## Refactoring: melhorar sem quebrar

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **18/05/2026 | E132 | 18:50–20:30**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 19, seções 19.2 (Tipos de Manutenção) e 19.3.1 (Refatoração Contínua)

📖 _Engenharia de Software Moderna_ — Cap. 9 (seções: Catálogo de Refactorings; Prática de Refactoring; Refactorings Automatizados)

Se você não leu antes de vir, tudo bem — mas leia antes da próxima aula. A terça pressupõe que você leu as duas.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Definir refactoring com precisão: o que é, o que não é, e por que a distinção importa
- Identificar pelo menos cinco code smells e associar cada um a uma refatoração correspondente
- Aplicar as refatorações mais comuns em código JavaScript (renomear, extrair função, simplificar condicional, eliminar duplicação)
- Explicar por que refactoring sem testes é arriscado

---

## 1. Uma pergunta antes de começar

> _"Quando você muda o código de uma funcionalidade que já está funcionando, o que pode dar errado?"_

Use este espaço para anotar sua resposta antes da discussão:

```
Sua resposta inicial:


```

---

## 2. O que é refactoring — e o que não é

A definição de Martin Fowler, referência da área:

> _"Refactoring é o processo de reestruturar o código existente, alterando sua estrutura interna sem mudar seu comportamento externo."_

Três palavras para gravar: **reestruturar**, **sem mudar comportamento**. Isso significa:

- ✅ Refactoring: renomear uma variável `x` para `totalPedidos`
- ✅ Refactoring: extrair um bloco de 40 linhas em uma função separada
- ✅ Refactoring: substituir um `if/else` de 6 níveis por uma estrutura mais clara
- ❌ Não é refactoring: corrigir um bug enquanto reorganiza o código
- ❌ Não é refactoring: adicionar uma nova funcionalidade e "aproveitar para limpar"

**Por que essa distinção importa?** Porque misturar refactoring com mudanças de comportamento é a receita para introduzir bugs que são impossíveis de rastrear. Você não sabe se o bug veio da nova funcionalidade ou da limpeza.

---

## 3. Code smells: quando o código está "fedendo"

"Code smell" (Kent Beck & Martin Fowler) é qualquer característica no código que sugere um problema de design mais profundo. Não são bugs — o código pode funcionar — mas são sinais de que algo vai dificultar a manutenção no futuro.

### Catálogo simplificado

| Code Smell | O que parece | Refatoração associada |
|---|---|---|
| **Long Method** | Função com 80 linhas que faz tudo | Extract Function |
| **Magic Number** | `if (status === 3)` sem explicação | Replace Magic Number with Constant |
| **Duplicate Code** | O mesmo bloco copiado em 3 lugares | Extract Function / Pull Up Method |
| **Dead Code** | Variáveis e funções que nunca são usadas | Remove Dead Code |
| **Long Parameter List** | `function criar(nome, email, tel, end, cidade, cep)` | Introduce Parameter Object |
| **Feature Envy** | Uma função acessa dados de outro objeto mais do que os próprios | Move Function |
| **Mysterious Name** | `let d`, `function proc()`, `const x2` | Rename Variable/Function |
| **Nested Conditionals** | `if` dentro de `if` dentro de `if` | Extract Function / Guard Clauses |

**Pause e reflita:** Qual desses smells você já encontrou no código do seu projeto? Anote abaixo.

```
Code smell encontrado:

Onde está no projeto:

```

---

## 4. Demonstração ao vivo — acompanhe aqui

Durante a aula, o professor vai mostrar um código JavaScript com múltiplos code smells e refatorar passo a passo. Use este espaço para anotar o que está vendo.

### Código original (identifique os smells antes da discussão)

```javascript
// Versão original — identifique o que está errado
function proc(d) {
  let r = [];
  for (let i = 0; i < d.length; i++) {
    if (d[i].s === 1) {
      if (d[i].v > 100) {
        r.push({ id: d[i].id, v: d[i].v * 0.9, s: d[i].s });
      } else {
        r.push({ id: d[i].id, v: d[i].v, s: d[i].s });
      }
    }
  }
  for (let i = 0; i < d.length; i++) {
    if (d[i].s === 2) {
      if (d[i].v > 100) {
        r.push({ id: d[i].id, v: d[i].v * 0.85, s: d[i].s });
      } else {
        r.push({ id: d[i].id, v: d[i].v, s: d[i].s });
      }
    }
  }
  return r;
}
```

**Smells que você identificou antes da discussão:**

```
1.
2.
3.
```

### Espaço para anotar a versão refatorada

```javascript
// Versão refatorada — anote aqui conforme o professor demonstra




```

**O comportamento mudou?** Como você sabe que não mudou?

```
Resposta:

```

---

## 5. A regra de ouro

> _"Refactoring sem testes é andar no escuro."_

Se você não tem testes automatizados para verificar que o comportamento externo não mudou, cada refatoração é um ato de fé. Você assume que funcionou — mas não tem como confirmar.

A sequência segura é:
```
1. Testes verdes → 2. Refatorar → 3. Testes verdes → 4. Commit → 5. Repetir
```

Se os testes ficaram vermelhos após a refatoração, você introduziu um bug. Undo. Tente novamente.

**Conexão com o projeto:** Quantos testes automatizados o seu projeto tem hoje? Se a resposta for "poucos" ou "nenhum" — o Sprint 3 (que começa nesta semana) é o momento de mudar isso.

```
Testes no projeto hoje:

O que precisaria testar antes de refatorar:

```

---

## 6. Refactoring contínuo como cultura

O Cap. 19.3.1 do Garcia apresenta a **Regra do Escoteiro** como uma prática de refactoring contínuo:

> _"Deixe o acampamento sempre um pouco mais limpo do que você o encontrou."_

Na prática, isso significa: quando você vai trabalhar em uma funcionalidade nova, aproveita para melhorar um pouco o código ao redor — renomeia uma variável confusa, extrai uma função muito longa. Não é um projeto separado de "limpeza". É um hábito.

O risco do oposto — acumular sempre para "limpar depois" — tem nome: **dívida técnica**. Vamos falar mais sobre ela na terça-feira.

---

## 7. Questão estruturante para reflexão

> _"Se o refactoring não muda o comportamento externo do software, por que muitas equipes evitam fazê-lo? O que precisaria mudar na cultura de uma equipe para que a refatoração contínua fosse natural?"_

Anote sua perspectiva antes da discussão:

```
Sua resposta inicial:


```

---

## 8. Para a próxima aula (Terça-feira)

📖 **Leitura obrigatória:**
- Garcia — Cap. 19, seções 19.1 (Evolução histórica da manutenção) e 19.4 (Documentação e gerenciamento de conhecimento)
- Valente — Cap. 9, seção Code Smells (relação com dívida técnica e manutenção)

**Traga para a terça:** uma análise honesta de um trecho do código do projeto de vocês onde a dívida técnica é mais visível. Não precisa ser nada formal — uma observação, um link para o commit, ou uma descrição do que incomoda.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
_Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 19, seções 19.2 e 19.3.1. Valente, M. T. Engenharia de Software Moderna. 2020. Cap. 9._
