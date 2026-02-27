# Rubrica de Code Review

**CIN0136: Desenvolvimento de Software · CIn-UFPE · 2026.1**

---

> **Como usar esta rubrica:** Aplique a cada Pull Request que você revisar. Avalie cada dimensão, registre comentários no próprio PR do GitHub e informe a decisão final ao final da revisão. O objetivo não é punir — é garantir que o código que entra no repositório principal atende a um padrão acordado por toda a equipe.
>
> A rubrica é usada pelo revisor. O autor do PR não preenche — ele responde aos comentários.

---

## Informações do PR

| Campo | |
|-------|-|
| **Título do PR** | |
| **Autor** | |
| **Revisor** | |
| **Data da revisão** | |
| **Branch de origem → destino** | |
| **Link do PR** | |

---

## Dimensão 1 — Correção e Funcionalidade

> *O código faz o que diz que faz? Os critérios de aceitação da user story foram atendidos?*

| Critério | ✅ OK | ⚠️ Ajuste necessário | ❌ Bloqueante |
|----------|-------|---------------------|--------------|
| A funcionalidade descrita na user story está implementada | | | |
| Os critérios de aceitação foram atendidos (verificar no backlog) | | | |
| Não há regressões óbvias em funcionalidades existentes | | | |
| Casos extremos e entradas inválidas são tratados | | | |

**Comentários:**

```
[Descreva o que encontrou — seja específico: linha, função, comportamento observado vs. esperado]
```

---

## Dimensão 2 — Testes

> *O código vem acompanhado de testes que verificam o comportamento implementado?*

| Critério | ✅ OK | ⚠️ Ajuste necessário | ❌ Bloqueante |
|----------|-------|---------------------|--------------|
| Há pelo menos 1 teste para cada nova funcionalidade | | | |
| Os testes cobrem casos normais (happy path) | | | |
| Os testes cobrem pelo menos 1 caso extremo ou de erro | | | |
| Todos os testes existentes passam (nenhuma regressão) | | | |
| Os testes são legíveis — o nome descreve o que está sendo testado | | | |

**Comentários:**

```
[Ex: "A função processPayment não tem teste para o caso em que o valor é negativo"]
```

---

## Dimensão 3 — Qualidade e Legibilidade do Código

> *Outro membro da equipe consegue entender e modificar este código sem precisar perguntar ao autor?*

| Critério | ✅ OK | ⚠️ Ajuste necessário | ❌ Bloqueante |
|----------|-------|---------------------|--------------|
| Nomes de variáveis, funções e arquivos são descritivos e em inglês | | | |
| Funções têm uma responsabilidade clara (não fazem "tudo") | | | |
| Não há código comentado ou `console.log` de debug esquecido | | | |
| Não há duplicação de lógica que poderia ser extraída | | | |
| ESLint e Prettier passam sem erros (verificar CI) | | | |
| Comentários explicam o "por quê", não o "o quê" | | | |

**Comentários:**

```
[Ex: "A função getUserData faz validação, busca no banco e formata a resposta — considere separar em 3 funções"]
```

---

## Dimensão 4 — Segurança e Boas Práticas

> *O código não introduz vulnerabilidades ou problemas de segurança básicos?*

| Critério | ✅ OK | ⚠️ Ajuste necessário | ❌ Bloqueante |
|----------|-------|---------------------|--------------|
| Nenhuma credencial, chave de API ou senha hardcoded no código | | | |
| Entradas do usuário são validadas antes de serem usadas | | | |
| Dados sensíveis não são expostos em logs ou respostas de API | | | |
| Dependências novas adicionadas são necessárias e conhecidas (sem pacotes suspeitos) | | | |

**Comentários:**

```
[Ex: "A rota POST /login não valida se o campo email é uma string antes de consultar o banco"]
```

---

## Dimensão 5 — Tamanho e Escopo do PR

> *O PR está focado em uma coisa? É possível revisar em um tempo razoável?*

| Critério | ✅ OK | ⚠️ Ajuste necessário | ❌ Bloqueante |
|----------|-------|---------------------|--------------|
| O PR resolve uma única funcionalidade ou problema (não mistura coisas não relacionadas) | | | |
| O tamanho é razoável para revisão (idealmente < 400 linhas alteradas) | | | |
| A descrição do PR explica o que foi feito e por quê | | | |
| PRs muito grandes foram justificados ou divididos quando possível | | | |

**Comentários:**

```
[Ex: "Este PR mistura a feature de login com refactoring do módulo de usuários — considere separar"]
```

---

## Decisão Final

| Decisão | |
|---------|---|
| ✅ **Aprovar** — código pronto para merge | ☐ |
| 🔄 **Aprovar com ressalvas** — merge ok, mas os comentários devem ser endereçados em seguida | ☐ |
| ⚠️ **Solicitar mudanças** — não fazer merge até os itens marcados como "Ajuste necessário" serem resolvidos | ☐ |
| ❌ **Bloquear** — há pelo menos um item "Bloqueante"; não fazer merge até resolução e nova revisão | ☐ |

**Comentário geral para o autor:**

```
[Escreva aqui sua avaliação global — o que está bom, o que precisa mudar, o que aprendeu com este PR]
```

---

## Guia de tom para comentários

A forma como você comenta importa tanto quanto o que você comenta. Siga estas diretrizes:

**✅ Bom comentário:**
> "A função `calculateTotal` está fazendo três coisas diferentes — validação, cálculo e formatação. Extrair cada uma em sua própria função tornaria o código mais testável e mais fácil de modificar. O que acha?"

**❌ Comentário problemático:**
> "Esse código tá uma bagunça."

**Regras básicas:**
- Critique o código, não a pessoa
- Seja específico — "linha 42" é melhor que "em vários lugares"
- Explique o porquê da sugestão, não só o o quê
- Use "considere", "e se", "o que acha de" em vez de "faça", "mude", "corrija"
- Distingua entre bloqueante ("isso vai causar bug em produção") e sugestão ("seria mais legível assim")
- Reconheça o que está bem — um comentário positivo no meio da revisão não é fraqueza

---

## Escala de severidade dos comentários no GitHub

Use etiquetas nos comentários para clareza:

| Etiqueta | Significado |
|----------|------------|
| `[bloqueante]` | Deve ser resolvido antes do merge — bug, segurança, ou viola critério de aceitação |
| `[ajuste]` | Deve ser resolvido antes do merge — qualidade, legibilidade, teste faltando |
| `[sugestão]` | Não bloqueia o merge — melhoria opcional, ponto de discussão |
| `[dúvida]` | Pergunta ao autor — não bloqueia, mas a resposta pode mudar a avaliação |
| `[elogio]` | Algo que vale destacar positivamente |

---

*CIN0136 — Desenvolvimento de Software · CIn-UFPE · 2026.1*
