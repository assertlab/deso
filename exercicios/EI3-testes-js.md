# EI3 — Testes em JavaScript

**CIN0136: Desenvolvimento de Software · CIn-UFPE · 2026.1**
**Entrega:** até domingo, 17/05/2026 às 23:59
**Peso:** componente extra (+10%) · individual

---

## Contexto

Nas Semanas 8 e 9 você aprendeu a pirâmide de testes, escreveu os primeiros testes com Vitest no projeto da equipe e viu Playwright em ação. Este exercício é a sua prova individual de que você sabe escrever testes de forma intencional — não apenas testes que passam, mas testes que **encontram bugs**.

Você vai receber um módulo JavaScript com bugs intencionais. Sua missão é escrever uma suite de testes que os descubra, documentar o que encontrou e escrever um teste de aceitação end-to-end com Playwright.

---

## Objetivos de aprendizagem

Ao completar este exercício, você será capaz de:

- Escrever testes unitários com Vitest para cobrir happy path e casos extremos
- Usar testes como ferramenta de descoberta de bugs (não apenas validação)
- Escrever pelo menos 1 teste de aceitação com Playwright
- Documentar decisões de teste de forma clara

---

## Ponto de partida

Clone ou baixe o repositório de base fornecido pelo professor:

```bash
git clone https://github.com/cin0136-2026-1/EI3-base
cd EI3-base
npm install
```

O repositório contém:

```
EI3-base/
├── src/
│   ├── carrinho.js         ← módulo principal com bugs intencionais
│   ├── validacao.js        ← módulo auxiliar com bugs intencionais
│   └── server.js           ← servidor Express com 2 rotas (GET e POST)
├── package.json
└── README.md               ← instruções de execução
```

> ⚠️ **Não modifique os arquivos em `src/`.** Seu trabalho é escrever testes que revelem os bugs — não corrigir os bugs.

---

## O que entregar

Um repositório Git **público** no GitHub, derivado (fork) do repositório base, com os seguintes arquivos adicionados por você:

```
EI3-base/
├── src/                    ← não modificado
├── tests/
│   ├── carrinho.test.js    ← sua suite de testes unitários
│   ├── validacao.test.js   ← sua suite de testes unitários
│   └── aceitacao.spec.js   ← seu teste de aceitação com Playwright
└── ANALISE.md              ← documento de análise (ver abaixo)
```

---

## Requisitos obrigatórios

### R1 — Testes unitários com Vitest (mínimo 12 testes)

Escreva testes para `carrinho.js` e `validacao.js` cobrindo:

**Para cada função testada, inclua obrigatoriamente:**
- Pelo menos 1 teste de **happy path** — entrada válida, resultado esperado
- Pelo menos 1 teste de **caso extremo** — limite, valor zero, lista vazia, string vazia, etc.
- Pelo menos 1 teste de **entrada inválida** — null, undefined, tipo errado, valor negativo

**Padrão de nomenclatura obrigatório:**

```javascript
describe('nomeDaFuncao', () => {
  it('deve [resultado esperado] quando [condição]', () => {
    // arrange - arrange - act - assert
  })
})
```

**Exemplo:**

```javascript
describe('calcularTotal', () => {
  it('deve retornar 0 quando o carrinho está vazio', () => {
    const carrinho = []
    const total = calcularTotal(carrinho)
    expect(total).toBe(0)
  })

  it('deve somar corretamente os preços de múltiplos itens', () => {
    const carrinho = [
      { nome: 'Item A', preco: 10.00, quantidade: 2 },
      { nome: 'Item B', preco: 5.50, quantidade: 1 }
    ]
    expect(calcularTotal(carrinho)).toBe(25.50)
  })

  it('deve lançar erro quando o carrinho é null', () => {
    expect(() => calcularTotal(null)).toThrow()
  })
})
```

---

### R2 — Teste de aceitação com Playwright (mínimo 1 cenário, mínimo 3 passos)

Escreva um teste end-to-end para uma das rotas do `server.js`. O teste deve:

- Iniciar a aplicação (ou assumir que está rodando em `localhost:3000`)
- Simular uma interação real (requisição HTTP ou interação de UI se houver)
- Verificar o resultado na perspectiva do usuário/consumidor da API

**Estrutura sugerida:**

```javascript
// aceitacao.spec.js
import { test, expect } from '@playwright/test'

test.describe('POST /carrinho/adicionar', () => {
  test('deve retornar o carrinho atualizado ao adicionar item válido', async ({ request }) => {
    // dado que o servidor está rodando
    const response = await request.post('http://localhost:3000/carrinho/adicionar', {
      data: { nome: 'Produto X', preco: 29.90, quantidade: 1 }
    })
    // então a resposta deve ser 200 com o item no carrinho
    expect(response.status()).toBe(200)
    const body = await response.json()
    expect(body.itens).toHaveLength(1)
    expect(body.itens[0].nome).toBe('Produto X')
  })
})
```

---

### R3 — ANALISE.md

Um documento com três seções obrigatórias:

**Bugs encontrados**

Para cada bug identificado pelos seus testes, descreva:

```markdown
### Bug #1 — [nome descritivo]
- **Função afetada:** `nomeDaFuncao` em `arquivo.js`
- **Comportamento observado:** [o que o código faz]
- **Comportamento esperado:** [o que deveria fazer]
- **Teste que revelou:** `it('...')`
- **Entrada que reproduz o bug:** [exemplo concreto]
```

**Decisões de teste**

Explique em 1 parágrafo: Como você decidiu quais casos testar? Qual foi o seu raciocínio para escolher os casos extremos? Houve algum caso que você pensou em testar mas decidiu não testar — e por quê?

**Cobertura e lacunas**

Execute o relatório de cobertura (`npm run coverage`) e inclua a saída. Depois responda: quais partes do código seus testes **não** cobriram? Por que você escolheu não cobri-las?

---

## Executando os testes

```bash
# Testes unitários
npm test

# Testes unitários com watch
npm run test:watch

# Relatório de cobertura
npm run coverage

# Testes de aceitação (Playwright)
npx playwright test

# Testes de aceitação com interface visual
npx playwright test --ui
```

---

## Critérios de avaliação

| Critério | Peso | Descrição |
|----------|------|-----------|
| **Cobertura e diversidade dos testes unitários** | 35% | Happy path + casos extremos + entradas inválidas para cada função; nomenclatura correta |
| **Bugs encontrados e documentados** | 30% | Quantidade de bugs revelados, clareza da descrição no ANALISE.md |
| **Teste de aceitação com Playwright** | 20% | Cenário real, passos claros, assertions significativas |
| **ANALISE.md — decisões e lacunas** | 15% | Profundidade do raciocínio sobre escolhas de teste |

---

## Instruções de entrega

1. Faça **fork** do repositório base (não clone sem fork — o fork cria sua cópia pública rastreável)
2. Adicione seus arquivos de teste e o ANALISE.md
3. Certifique-se de que `npm test` passa **sem erros de sintaxe** (bugs nos testes são problema seu, não do módulo)
4. Entregue o link do seu fork conforme instrução do professor
5. Prazo: **17/05/2026 (domingo) às 23:59**
6. Atraso de até 48h → desconto de 20%. Após 48h → não pontua

---

## Dúvidas frequentes

**Os testes devem passar ou falhar?**
Depende. Os testes que cobrem comportamentos corretos devem **passar**. Os testes que revelam bugs devem **falhar** — afinal, o bug existe. Não "conserte" os testes para fazê-los passar se o módulo está errado. A falha é a evidência do bug.

**Quantos bugs existem no módulo?**
O professor não vai revelar isso antes da entrega. Parte do exercício é descobrir quantos há. Equipes que encontrarem todos os bugs receberão reconhecimento na aula de devolução.

**Posso usar IA para ajudar a escrever os testes?**
Sim, com a notação `[IA-assisted]` nos commits relevantes. Mas você deve ser capaz de explicar cada teste ao professor se pedido. Testes gerados por IA sem compreensão não são válidos — e testes gerados por IA frequentemente **perdem os casos mais interessantes**.

**E se o Playwright não conseguir conectar ao servidor?**
Certifique-se de que o servidor está rodando antes de executar os testes de aceitação. Se tiver problemas de configuração, documente no ANALISE.md — a tentativa conta.

---

*CIN0136 — Desenvolvimento de Software · CIn-UFPE · 2026.1*
