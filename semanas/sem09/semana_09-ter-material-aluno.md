# Semana 9 — Terça-feira

## Testes de aceitação + BDD e Gherkin como especificação executável

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **12/05/2026 | E132 | 17:00–18:40**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 9, seção 9.2.4 (Testes de Aceitação) + revisitar Cap. 7 (User Stories)

**Traga para a aula:** o backlog do projeto com os critérios de aceitação Gherkin escritos na Semana 4 (Strateegia).

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar o que é BDD (Behavior-Driven Development) e como conecta requisitos, testes e desenvolvimento
- Usar o formato Gherkin (Dado/Quando/Então) para especificar cenários de aceitação completos — incluindo cenários de falha
- Compreender o papel do Playwright como ferramenta de automação de testes e2e/aceitação
- Transformar user stories e critérios Gherkin do projeto em cenários BDD formais prontos para automação

---

## 1. Subindo na pirâmide

Ontem, vocês formalizaram os tipos de teste e viram que a maioria dos testes do projeto está na base (unitários) e no meio (integração). Hoje, vamos ao topo: **testes de aceitação**.

A pergunta que muda:

```
Testes unitários:    "A função funciona?"
Testes de integração: "Os módulos conversam?"
Testes de aceitação:  "O USUÁRIO consegue fazer o que precisa?"
```

Testes de aceitação respondem: **"O software faz o que o stakeholder esperava?"** São poucos, mas são os que decidem se a entrega será aceita ou rejeitada na Sprint Review de quinta.

---

## 2. BDD — Behavior-Driven Development

BDD é uma abordagem em que o **comportamento esperado** do software é especificado **antes** (ou junto) do código, usando uma linguagem que desenvolvedores e stakeholders conseguem entender.

```
Requisito → Comportamento esperado → Cenário Gherkin → Código → Teste automatizado
```

Vocês já percorreram as primeiras etapas desse caminho:

- **Semana 3:** user stories escritas
- **Semana 4:** critérios de aceitação em Gherkin (Strateegia)
- **Semana 5:** Definition of Done com "funcionalidade testada"
- **Semana 8:** testes unitários e de integração com Vitest
- **Hoje:** cenários BDD formais → amanhã: testes automatizados com Playwright

---

## 3. O formato Gherkin: da Semana 4 para cá

Vocês já conhecem o formato básico da Semana 4:

```gherkin
Dado que [contexto / pré-condição]
Quando [ação do usuário]
Então [resultado esperado]
```

Agora, a estrutura completa de uma Feature:

```gherkin
Funcionalidade: Filtro de produtos por preço
  Como cliente da loja
  Quero filtrar produtos por faixa de preço
  Para encontrar itens dentro do meu orçamento

  Cenário: Filtro com resultados
    Dado que estou na página de listagem de produtos
      E existem 20 produtos cadastrados com preços variados
    Quando seleciono a faixa "R$50 a R$100"
      E clico em "Filtrar"
    Então apenas produtos com preço entre R$50 e R$100 são exibidos
      E a contagem de resultados é atualizada

  Cenário: Filtro sem resultados
    Dado que estou na página de listagem de produtos
      E todos os produtos custam mais de R$500
    Quando seleciono a faixa "R$10 a R$50"
      E clico em "Filtrar"
    Então nenhum produto é exibido
      E a mensagem "Nenhum produto encontrado nessa faixa" aparece
```

### O que mudou desde a Semana 4

- **Funcionalidade** agrupa cenários relacionados
- **Como/Quero/Para** é a user story original — a rastreabilidade é direta
- **Cenários de falha** são obrigatórios — não apenas o caminho feliz
- **Cada cenário é um teste automatizável** — isso é a novidade de hoje

---

## 4. Cenários de falha: a metade que faltava

Na Semana 4, a maioria de vocês provavelmente escreveu apenas cenários de sucesso. Mas o BDD exige que você pense no que acontece quando algo dá errado.

### Exemplo: login

**Cenário de sucesso:**

```gherkin
Dado que estou na página de login
  E tenho uma conta com email "ana@email.com"
Quando preencho email "ana@email.com" e senha "minha-senha"
  E clico em "Entrar"
Então sou redirecionada para a página inicial
  E vejo a mensagem "Bem-vinda, Ana"
```

**Cenário de falha — senha errada:**

```gherkin
Dado que estou na página de login
Quando preencho email "ana@email.com" e senha "senha-errada"
  E clico em "Entrar"
Então permaneço na página de login
  E vejo a mensagem "Email ou senha incorretos"
  E o campo de senha é limpo
```

Repare: a mensagem de erro é a mesma para "senha errada" e "conta inexistente". Isso é uma decisão de segurança — e o teste **documenta** essa decisão.

### A regra prática

Para cada cenário de sucesso, pergunte-se:

- E se o campo estiver vazio?
- E se o usuário não tiver permissão?
- E se o dado não existir?
- E se a rede cair no meio da operação?

---

## 5. BDD como ferramenta de descoberta

O benefício mais poderoso do BDD não é a automação — é a **descoberta**. Ao escrever cenários formais, vocês vão encontrar:

- **Detalhes que ninguém especificou:** "Vejo 'Bem-vinda, Ana'" → de onde vem o nome? A user story não mencionava nome de exibição.
- **Decisões implícitas:** "O campo de senha é limpo" → quem decidiu isso? Está documentado?
- **Ambiguidades na user story:** se vocês não conseguem escrever o cenário, é porque a story precisa ser refinada.

> _"Escrever cenários BDD revela o que você não sabia que não sabia."_

---

## 6. Playwright: do cenário à automação

O **Playwright** é uma ferramenta que automatiza interações com o navegador. Ele simula o que o usuário faz: clicar, digitar, navegar, esperar elementos aparecerem.

### Vitest vs. Playwright

|Ferramenta|Nível|O que testa|Ambiente|
|---|---|---|---|
|**Vitest**|Unitário / integração|Funções, módulos, rotas|Node.js|
|**Playwright**|e2e / aceitação|Aplicação completa|Navegador real|

### De Gherkin a Playwright

O cenário Gherkin se traduz diretamente em código Playwright:

```javascript
import { test, expect } from '@playwright/test';

test('filtra produtos por faixa de preço', async ({ page }) => {
  // Dado que estou na página de listagem
  await page.goto('/produtos');

  // Quando seleciono a faixa de preço
  await page.selectOption('#faixa-preco', '50-100');
  await page.click('button#filtrar');

  // Então apenas produtos filtrados aparecem
  const produtos = page.locator('.produto-card');
  await expect(produtos).not.toHaveCount(0);

  // E todos estão na faixa correta
  const precos = await page.locator('.produto-preco').allTextContents();
  for (const preco of precos) {
    const valor = parseFloat(preco.replace('R$', '').replace(',', '.'));
    expect(valor).toBeGreaterThanOrEqual(50);
    expect(valor).toBeLessThanOrEqual(100);
  }
});
```

Cada linha corresponde a um passo do Gherkin. O Playwright não "sabe" Gherkin — mas o desenvolvedor que escreve o teste usa o cenário como guia.

Na quinta, vocês vão escrever testes como esse para o projeto real.

---

## 7. Exercício: do backlog ao cenário BDD

Abra o backlog do projeto — os critérios Gherkin da Semana 4. Escolha **2 user stories** que serão demonstradas na Sprint 2 Review de quinta e reescreva como cenários BDD completos:

**User Story 1:**

```
Funcionalidade:
  Como
  Quero
  Para

  Cenário: [sucesso]
    Dado que
    Quando
    Então

  Cenário: [falha]
    Dado que
    Quando
    Então
```

**User Story 2:**

```
Funcionalidade:
  Como
  Quero
  Para

  Cenário: [sucesso]
    Dado que
    Quando
    Então

  Cenário: [falha]
    Dado que
    Quando
    Então
```

**Reflexão:** O que você descobriu ao reescrever os critérios da Semana 4 como cenários formais? Alguma ambiguidade apareceu?

```
Sua resposta:


```

---

## 8. Questão estruturante para reflexão

> _"O que muda quando o cenário de teste existe antes do código — e o que muda quando ele só é escrito depois? Qual abordagem dá mais confiança ao stakeholder?"_

```
Sua resposta:


```

---

## 9. Para a próxima aula (Quinta-feira)

Na quinta vocês têm a **Sprint 2 Review com o stakeholder**. Prepare-se:

- Na primeira metade da quinta (2h): cada equipe implementa **pelo menos 3 cenários de teste de aceitação com Playwright** baseados nos cenários BDD escritos hoje
- Na segunda metade (2h): **Sprint 2 Review** — demo ao stakeholder + feedback + retrospectiva
- O **EI3 — Testes em JavaScript** será publicado após a Sprint Review (entrega até domingo)

**Conexão com a demo:** os testes de aceitação que vocês escrevem hoje e implementam quinta são a rede de segurança para a demo. Se passam, vocês têm confiança para demonstrar. Se não passam, vocês sabem exatamente o que falta.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_ _Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 9, seção 9.2.4; Cap. 7._ _Valente, M. T. Engenharia de Software Moderna. 2022. Cap. 8 — Testes de Sistema._
