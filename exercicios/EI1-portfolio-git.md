# EI1 — Portfólio Git

**CIN0136: Desenvolvimento de Software · CIn-UFPE · 2026.1**
**Entrega:** até domingo, 29/03/2026 às 23:59
**Peso:** componente extra (+10%) · individual

---

## Contexto

Git não é uma ferramenta que se aprende lendo — se aprende usando. Este exercício é a sua primeira prova prática de que você sabe trabalhar com controle de versão de forma profissional: não apenas commitar arquivos, mas comunicar intenções, organizar trabalho em branches e colaborar de forma estruturada.

Você vai construir um **repositório Git pessoal** que documenta sua evolução com a ferramenta ao longo das Semanas 2 e 3. O repositório em si é o exercício — o que está dentro dele é a evidência.

---

## Objetivos de aprendizagem

Ao completar este exercício, você será capaz de:

- Usar commits semânticos para comunicar intenções de mudança
- Organizar trabalho paralelo com branches e fazer merges com conflito
- Usar Pull Requests como unidade de revisão de código
- Refletir criticamente sobre o próprio processo de aprendizagem

---

## O que entregar

Um repositório Git **público** no GitHub com a seguinte estrutura mínima:

```
seu-portfolio-git/
├── README.md              ← apresentação do repositório e índice
├── REFLEXAO.md            ← reflexão pessoal (ver seção abaixo)
├── exercicios/
│   ├── ex01-commits/      ← arquivos do exercício de commits
│   ├── ex02-branches/     ← arquivos do exercício de branches
│   └── ex03-conflito/     ← evidência de resolução de conflito
└── projeto/
    └── hello-world/       ← mini-projeto usado nos exercícios
```

---

## Requisitos obrigatórios

### R1 — Commits semânticos (mínimo 10)

Todos os commits do repositório devem seguir o padrão de **Conventional Commits**:

```
<tipo>(<escopo opcional>): <descrição curta>

Tipos válidos:
  feat     → nova funcionalidade ou arquivo
  fix      → correção de erro
  docs     → alteração em documentação
  refactor → melhoria de código sem mudança de comportamento
  test     → adição ou modificação de testes
  chore    → configuração, dependências, gitignore, etc.
```

**Exemplos de commits válidos:**
```
feat(hello-world): adiciona rota GET /usuarios
docs(readme): descreve estrutura do repositório
fix(ex02): corrige bug na função de ordenação
refactor(ex01): extrai lógica de validação para função separada
```

**Exemplos de commits inválidos:**
```
atualização
ok
commit 3
wip
ajustes finais
```

> ⚠️ Commits inválidos contam negativamente na avaliação. Prefira 8 commits semânticos a 15 commits sem padrão.

---

### R2 — Uso de branches (mínimo 3 branches além da main)

Demonstre que você sabe trabalhar com branches criando pelo menos **3 branches com propósitos distintos** e fazendo o merge de todas elas na `main` antes da entrega.

Cada branch deve:
- Ter um nome descritivo no padrão `tipo/descricao` (ex: `feat/rota-usuarios`, `fix/validacao-email`, `docs/atualiza-readme`)
- Conter pelo menos 2 commits
- Ter sido mergeada via Pull Request (ver R3)

---

### R3 — Pull Requests (mínimo 2)

Pelo menos 2 das branches devem ser mergeadas via **Pull Request** no GitHub (não via linha de comando direto). Cada PR deve ter:

- Título descritivo
- Descrição de 2–3 frases explicando o que foi feito
- Pelo menos 1 comentário seu próprio (auto-review, dúvida, observação)

> Dica: o GitHub permite que você abra e faça merge de PRs no seu próprio repositório. Isso é prática válida e comum.

---

### R4 — Resolução de conflito (mínimo 1)

Demonstre que você sabe resolver um merge conflict. Para isso:

1. Crie duas branches a partir de um mesmo commit
2. Faça mudanças no **mesmo trecho** do mesmo arquivo em ambas
3. Faça o merge da primeira branch na `main`
4. Tente fazer o merge da segunda — você encontrará um conflito
5. Resolva o conflito manualmente e complete o merge

No arquivo `exercicios/ex03-conflito/REGISTRO.md`, descreva:
- O que causou o conflito (qual arquivo, qual trecho)
- Como você decidiu qual versão manter
- O comando ou ação usada para marcar o conflito como resolvido

---

### R5 — REFLEXAO.md (mínimo 400 palavras)

Um documento de reflexão pessoal com três seções obrigatórias:

**O que foi difícil**
O que você achou mais complicado neste exercício? Onde travou? O que exigiu mais tentativa e erro? Seja específico — "branches foram difíceis" não é suficiente; "entender o estado do HEAD durante um merge conflict" é.

**O que ficou claro**
O que você entendeu de verdade, de um jeito que vai ficar? Pode ser um conceito, um comando, uma analogia que fez sentido.

**O que ainda é confuso**
O que você fez funcionar sem entender completamente por quê? Que dúvida sobrou que você vai precisar resolver nas próximas semanas?

> A reflexão é avaliada pela **honestidade e profundidade**, não pelo otimismo. "Entendi tudo, foi fácil" é a pior resposta possível.

---

## Critérios de avaliação

| Critério | Peso | Descrição |
|----------|------|-----------|
| **Commits semânticos** | 30% | Quantidade, variedade de tipos, mensagens descritivas e corretas |
| **Branches e merges** | 25% | Nomes adequados, histórico limpo, PRs com descrição |
| **Resolução de conflito** | 20% | Conflito real criado e resolvido, registro documentado |
| **REFLEXAO.md** | 25% | Profundidade, honestidade, especificidade |

---

## Instruções de entrega

1. Certifique-se de que o repositório está **público**
2. Preencha o campo `Repositório` na sua linha do arquivo [`equipes.md`](../equipes.md) do repositório da disciplina — ou envie o link conforme instrução do professor
3. Prazo: **29/03/2026 (domingo) às 23:59**
4. Atraso de até 48h → desconto de 20%. Após 48h → não pontua

---

## Dúvidas frequentes

**Posso usar interface gráfica (VS Code, GitHub Desktop) em vez da linha de comando?**
Sim. O que importa é o resultado no repositório, não como você chegou lá. Dito isso, recomendamos a linha de comando — você vai precisar dela em situações que nenhuma interface resolve.

**O repositório precisa ter código funcional?**
Não necessariamente. O foco é no processo Git, não no produto. Um repositório com arquivos de texto, markdown ou código simples é suficiente — desde que o histórico de commits conte uma história coerente.

**Posso usar o repositório do projeto da equipe?**
Não. Este exercício é individual e requer um repositório pessoal separado.

**E se eu fizer mais de 10 commits ou mais de 3 branches?**
Ótimo — não há máximo. O mínimo existe para garantir que a prática aconteceu; o máximo não existe porque mais prática é sempre melhor.

---

*CIN0136 — Desenvolvimento de Software · CIn-UFPE · 2026.1*
