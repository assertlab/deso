# Semana 9 — Segunda-feira

## Por que testar? Tipos de teste, pirâmide e cobertura

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **11/05/2026 | E132 | 18:50–20:30**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 9, seções 9.1 a 9.4 (Evolução histórica dos testes; Tipos de teste; Estratégias de cobertura; Desafios e vantagens)

📖 _Engenharia de Software Moderna_ — Cap. 8 (Testes: Unidade, integração, sistema, cobertura, TDD)

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar por que testar é essencial e como testes funcionam como rede de segurança para evolução do código
- Distinguir os quatro níveis de teste: unitário, integração, sistema e aceitação
- Descrever a pirâmide de testes e justificar a lógica econômica por trás da sua forma
- Relacionar cobertura de testes com qualidade — e entender os limites dessa relação
- Conectar a experiência prática com Vitest (Semana 8) aos conceitos formais apresentados hoje

---

## 1. Da prática para a teoria

Na semana passada, no lab de quinta-feira, vocês configuraram o Vitest, escreveram pelo menos 10 testes e viveram na pele o que significa ver um teste falhar — e depois passar. Hoje, vamos dar nome e estrutura ao que vocês fizeram.

Uma pergunta para começar:

> _"Dos testes que vocês escreveram na semana passada, quantos testam uma função isolada? Quantos testam a comunicação entre módulos? Quantos testam o sistema completo do ponto de vista do usuário?"_

```
Sua estimativa:
- Funções isoladas: ___
- Comunicação entre módulos: ___
- Sistema do ponto de vista do usuário: ___
```

A resposta revela em que nível da pirâmide vocês estão trabalhando — e o que falta.

---

## 2. Por que testar?

Vocês já viveram o "por que" na prática. Agora, os argumentos formais:

**Prevenção de regressões.** Quando você muda uma linha de código, como saber que não quebrou algo que já funcionava? Se existe um teste para aquele comportamento, ele responde em milissegundos.

**Documentação executável.** Um teste bem escrito é uma especificação viva do que o sistema faz. Diferente de um documento que pode ficar desatualizado, o teste falha se o comportamento mudar.

**Confiança para evoluir.** Sem testes, cada mudança é um salto de fé. Com testes, é uma decisão informada: mudo, rodo, vejo se algo quebrou.

**Comunicação de expectativas.** Testes de aceitação, em particular, falam a língua do usuário — exatamente como os cenários Gherkin que vocês escreveram na Semana 4.

O Cap. 9 do Garcia resume: quanto mais cedo um defeito é encontrado, mais barato é corrigi-lo. Um bug descoberto em produção pode custar até 100 vezes mais que um descoberto em teste unitário.

---

## 3. Os quatro níveis de teste

### Testes unitários

Testam a **menor unidade isolada** — uma função, um método, um módulo. São os que vocês mais escreveram na Semana 8.

```javascript
// Exemplo: função pura
function calcularDesconto(valor, percentual) {
  if (percentual < 0 || percentual > 100) throw new Error('Percentual inválido');
  return valor - (valor * percentual / 100);
}

// Teste unitário
test('aplica desconto de 10% em R$100', () => {
  expect(calcularDesconto(100, 10)).toBe(90);
});

test('rejeita percentual negativo', () => {
  expect(() => calcularDesconto(100, -5)).toThrow('Percentual inválido');
});
```

### Testes de integração

Testam se **dois ou mais módulos funcionam juntos**. Exemplo: a rota Express chama o serviço, que consulta o banco, e o resultado volta correto.

```javascript
// Teste de integração com supertest
import request from 'supertest';
import app from '../app.js';

test('GET /api/produtos retorna lista com status 200', async () => {
  const res = await request(app).get('/api/produtos');
  expect(res.status).toBe(200);
  expect(Array.isArray(res.body)).toBe(true);
});
```

Se vocês usaram `supertest` no lab da Semana 8, já escreveram testes de integração.

### Testes de sistema (end-to-end)

Testam o **sistema completo** — frontend conectando com backend, dados fluindo de ponta a ponta, do ponto de vista técnico.

### Testes de aceitação

Testam se o **sistema atende aos critérios do usuário**. São escritos na perspectiva de quem usa, não de quem codifica. Lembra dos critérios Gherkin da Semana 4?

```gherkin
Dado que estou na página de listagem de produtos
Quando seleciono a faixa de preço "R$50 a R$100"
Então apenas produtos nessa faixa são exibidos
```

Esse cenário é uma especificação de teste de aceitação. Amanhã vamos aprofundar como transformá-lo em teste automatizado com Playwright.

---

## 4. A pirâmide de testes

```
         ╱  ╲
        ╱ e2e ╲          ← Poucos, lentos, caros — validam a EXPERIÊNCIA do usuário
       ╱────────╲
      ╱integração╲       ← Verificam se os módulos CONVERSAM corretamente
     ╱────────────╲
    ╱   unitários   ╲    ← Muitos, rápidos, baratos — BASE de tudo
   ╱──────────────────╲
```

A forma da pirâmide reflete uma regra econômica:

|Nível|Quantidade|Velocidade|Custo de manutenção|
|---|---|---|---|
|Unitários|Muitos|Milissegundos|Baixo|
|Integração|Alguns|Segundos|Médio|
|Sistema/e2e|Poucos|Segundos a minutos|Alto|
|Aceitação|Poucos (críticos)|Variável|Alto|

**A regra:** a maioria dos seus testes deveria ser unitária. Os testes de aceitação são poucos, mas cobrem os cenários mais importantes para o stakeholder.

**O anti-pattern — o "cone de sorvete":** muitos testes manuais no topo, poucos automatizados na base. Resultado: lento, caro, inconsistente, e o time vive com medo de mudar qualquer coisa.

### Reflexão sobre o projeto

> _Olhe para os testes que vocês escreveram na Semana 8. A distribuição lembra uma pirâmide — ou um cone de sorvete?_

```
Sua análise:


```

---

## 5. Cobertura: o que mede e o que não mede

**Cobertura de testes** é a porcentagem do código executada quando os testes rodam. Na Semana 8, vocês viram o relatório de cobertura do Vitest. Agora, a provocação:

> _"100% de cobertura significa 100% de qualidade?"_

**Não.** Cobertura mede quais **linhas** foram executadas, não se o **comportamento** está correto.

```javascript
// Este teste atinge 100% de cobertura de calcularDesconto...
test('chama a função', () => {
  calcularDesconto(100, 10);
  // ...mas não verifica NADA. Zero assertions.
});
```

A linha foi executada. Cobertura 100%. Valor: zero.

### O que cobertura mede bem

- Identifica código **morto** (nunca executado)
- Revela áreas do código **sem nenhum teste**
- Dá uma visão geral de quão testado está o projeto

### O que cobertura NÃO mede

- Se os testes verificam o comportamento certo
- Se os **edge cases** estão cobertos
- Se os cenários do stakeholder estão validados

---

## 6. Edge cases: onde os bugs moram

Os defeitos mais perigosos vivem nos casos extremos:

- O que acontece se a lista estiver vazia?
- E se o usuário digitar um número negativo?
- E se o valor for `null` ou `undefined`?
- E se dois usuários tentarem a mesma operação ao mesmo tempo?

### Exercício: encontre os bugs!

```javascript
function dividir(a, b) {
  return a / b;
}

function buscarUsuario(id, usuarios) {
  return usuarios.find(u => u.id == id);
}

function formatarPreco(valor) {
  return "R$" + valor.toFixed(2);
}
```

Para cada função, identifique a entrada que causa problema:

|Função|Entrada problemática|O que acontece|
|---|---|---|
|`dividir`|||
|`buscarUsuario`|||
|`formatarPreco`|||

---

## 7. Testes como documentação executável

O Cap. 9 do Garcia destaca que testes funcionam como "documentação executável": diferente de um documento de requisitos que pode ficar desatualizado, o teste falha se o comportamento mudar. Isso é especialmente valioso no contexto do projeto de extensão — quando vocês entregarem o sistema ao stakeholder, os testes serão a documentação mais confiável de como o software se comporta.

Na Semana 5, vocês definiram o Definition of Done do projeto. Se "funcionalidade testada" faz parte desse DoD, então os testes não são opcionais — são parte da definição de "pronto".

---

## 8. Questão estruturante para reflexão

> _"O teste é uma rede de segurança que nos permite inovar com velocidade. Como uma cultura de testes robusta pode ser vista como uma vantagem competitiva — e não apenas um custo?"_

```
Sua resposta:


```

---

## 9. Para a próxima aula (Terça-feira)

📖 **Leitura obrigatória:** Cap. 9, seção 9.2.4 (Testes de Aceitação) + revisitar Cap. 7 (User Stories)

**Traga para a aula:** o backlog do projeto com os critérios de aceitação Gherkin escritos na Semana 4. Vamos transformá-los em testes automatizáveis com Playwright.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_ _Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 9, seções 9.1–9.4._ _Valente, M. T. Engenharia de Software Moderna. 2022. Cap. 8 — Testes._
