# Semana 12 — Terça-feira

## Documentação, README e preparação para entrega

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **02/06/2026 | E132 | 17:00–18:40**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 19, seção 19.4 (Documentação e gerenciamento de conhecimento)

**Traga para a aula:** uma decisão técnica do projeto de vocês que nunca foi documentada em lugar nenhum.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Distinguir os tipos de documentação relevantes para um produto de software
- Avaliar a qualidade de um README com critérios objetivos
- Identificar quais decisões do seu projeto precisam ser registradas antes da entrega
- Entender por que documentação não é "o que sobra de tempo" — é parte do produto

---

## 1. Uma pergunta antes de começar

> _"Se você fosse embora amanhã e outra equipe assumisse o seu repositório, o que eles conseguiriam fazer sem precisar te perguntar nada?"_

Anote sua resposta individual:

```
Sua resposta:


```

---

## 2. O problema com documentação

Documentação tem má reputação. É a última coisa que entra no sprint, a primeira a ser cortada quando o prazo aperta, e normalmente um README com `# TODO: add docs`.

O Cap. 19.4 do Garcia define documentação como "o conjunto de artefatos que tornam o conhecimento sobre o sistema acessível além de quem o criou". Repare na definição: o objetivo não é registrar o que foi feito — é tornar conhecimento **acessível a outros**.

Isso muda a pergunta. Em vez de "o que documento?", a pergunta certa é: **"o que outra pessoa precisaria saber para trabalhar com isso?"**

---

## 3. O que documentar: uma taxonomia prática

### 3.1 README — a porta de entrada

O README é o primeiro e muitas vezes único documento que um novo desenvolvedor lê. Um bom README responde:

```
1. O que é isso?          → Descrição em 2–3 linhas
2. Para quem é?           → Contexto do usuário/organização
3. Como rodar?            → Pré-requisitos + comandos exatos
4. Como testar?           → Rodar a suíte de testes
5. Como está organizado?  → Estrutura de pastas em alto nível
6. Quem mantém?           → Equipe e contatos
```

**O que um README não deve ser:**

- Um histórico de desenvolvimento ("na Semana 6 fizemos X, depois mudamos para Y")
- Uma lista de intenções não implementadas
- Uma cópia do plano de ensino

---

### 3.2 Decisões arquiteturais — ADRs

Uma **ADR (Architecture Decision Record)** é um registro curto de uma decisão de design importante: o que foi decidido, por que, e quais alternativas foram descartadas.

Formato mínimo:

```markdown
## ADR 001 — [Título da decisão]

**Data:** DD/MM/AAAA
**Status:** Aceita

**Contexto:**
[Por que essa decisão precisou ser tomada?]

**Decisão:**
[O que foi decidido?]

**Consequências:**
[O que muda? O que fica mais fácil? O que fica mais difícil?]
```

Vocês não precisam de ADRs para cada commit — apenas para decisões que farão alguém perguntar "por que está assim?" no futuro.

---

### 3.3 Documentação inline — comentários de código

Comentários úteis explicam **por quê**, não **o quê**:

```javascript
// ❌ Ruim: explica o óbvio
// Incrementa o contador
counter++;

// ✅ Bom: explica a intenção não-óbvia
// Necessário porque a API do parceiro retorna status 200 mesmo em erros
// Verificamos o campo 'success' explicitamente por isso
if (response.success === false) { ... }
```

Regra prática: se o código precisa de comentário para ser entendido, primeiro tente reescrever o código para que ele se explique. Se ainda assim precisar de contexto adicional, aí comente.

---

### 3.4 Diagramas — o estado atual, não o estado planejado

Os diagramas C4 que vocês produziram no semestre precisam refletir como o sistema **está hoje**, não como foi planejado na Semana 7. Antes da entrega, verifiquem:

- O diagrama de contexto ainda representa os usuários e sistemas externos corretos?
- O diagrama de container mostra os serviços que realmente existem?
- Algum componente foi adicionado, removido ou renomeado desde o último update?

---

## 4. Bons e maus READMEs: análise comparativa

### Exemplo A

```markdown
# Projeto

Sistema desenvolvido para o stakeholder X.

## Tecnologias
- React
- Node.js
- PostgreSQL

## Como rodar
npm install
npm start
```

**O que falta?**

```
Anote aqui:


```

---

### Exemplo B

```markdown
# Sistema de Gestão de Reservas — ONG Recife Verde

Plataforma web para gerenciamento de reservas de espaços comunitários,
desenvolvida em parceria com a ONG Recife Verde no contexto do projeto
de extensão CIN0136/UFPE 2026.1.

## Pré-requisitos

- Node.js 20+
- PostgreSQL 15+
- Variáveis de ambiente: copie `.env.example` para `.env` e preencha

## Como rodar localmente

```bash
# 1. Instale as dependências
npm install

# 2. Configure o banco
npm run db:migrate
npm run db:seed  # dados de exemplo

# 3. Inicie o servidor de desenvolvimento
npm run dev
```

Acesse em: http://localhost:3000

## Como testar

```bash
npm run test          # testes unitários (Vitest)
npm run test:e2e      # testes de aceitação (Playwright)
npm run test:coverage # relatório de cobertura
```

## Estrutura do projeto

```
src/
  frontend/   → React + Vite
  backend/    → Express + Prisma
  tests/      → Vitest (unit) + Playwright (e2e)
docs/
  adrs/       → Decisões arquiteturais
  c4/         → Diagramas de arquitetura
```

## Equipe

[Lista de membros e contatos]
```

**O que este README faz bem?**

```
Anote aqui:


```

---

## 5. Checklist de entrega — documentação

Use este checklist antes da quinta-feira:

**README**
- [ ] Descrição do projeto em 2–3 linhas (problema + solução + organização parceira)
- [ ] Pré-requisitos completos (versões específicas de Node, variáveis de ambiente)
- [ ] Comandos de instalação e execução testados por alguém que não participou do desenvolvimento
- [ ] Como rodar os testes
- [ ] Estrutura de pastas explicada em alto nível

**Decisões arquiteturais**
- [ ] Pelo menos 3 decisões importantes do projeto estão documentadas (pode ser em ADR ou seção no README)
- [ ] A escolha do banco de dados está justificada
- [ ] Decisões de organização do código que não são óbvias estão registradas

**Diagramas**
- [ ] Diagrama C4 Nível 1 (Contexto) atualizado
- [ ] Diagrama C4 Nível 2 (Container) atualizado
- [ ] Diagramas estão no repositório (não só na apresentação)

**Código**
- [ ] Sem comentários `// TODO` ou `// fix this later` não resolvidos na entrega
- [ ] Sem código comentado sem justificativa

---

## 6. A pergunta que mais importa

> _"Se vocês fossem embora do projeto amanhã e outra equipe assumisse, o que seria mais difícil de entender? Esse é o lugar que mais precisa de documentação."_

Identifique os 3 pontos mais críticos do projeto de vocês:

```
1.


2.


3.

```

---

## 7. Questão estruturante para reflexão

> _"Código sem documentação é um ativo ou um passivo? A resposta muda dependendo de quanto tempo o software vai durar?"_

Anote sua perspectiva antes da discussão:

```
Sua resposta inicial:


```

---

## 8. Para a próxima aula (Quinta-feira)

Na quinta-feira, vocês vão realizar o code review cruzado entre equipes. Para isso, o repositório de vocês precisa estar revisável — e o README precisa ser a porta de entrada para quem nunca viu o projeto.

**Antes da quinta:**

- Aplique o checklist de documentação acima ao repositório
- Garanta que os comandos do README funcionam numa máquina limpa (ou peça a um colega para testar)
- Identifique o PR ou conjunto de mudanças que vocês querem que a outra equipe revise

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
_Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 19, seção 19.4._
_Valente, M. T. Engenharia de Software Moderna. 2020. Cap. 9 — Refactoring (code smells e código como documentação implícita)._
