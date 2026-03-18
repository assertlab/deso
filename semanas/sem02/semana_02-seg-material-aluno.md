# Semana 2 — Segunda-feira

## Por que versionar? Fundamentos de Git

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **09/03/2026 | E132 | 17:00–18:40**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 3, seções 3.1, 3.2 e 3.3

Se você não leu antes de vir, tudo bem — mas leia antes da próxima aula.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar por que o versionamento é indispensável no desenvolvimento de software colaborativo
- Descrever o modelo mental do Git: working directory → staging area → repository
- Distinguir os conceitos de commit, branch e merge e o papel de cada um
- Conectar o problema de colaboração do seu projeto ao que o Git resolve

---

## 1. Uma pergunta antes de começar

> _"Você já perdeu código? Já teve medo de alterar algo que funcionava?"_

Use este espaço para anotar sua resposta antes da discussão:

```
Sua resposta inicial:


```

---

## 2. O problema que o Git resolve

Antes de aprender Git, vale entender por que ele existe.

### A versão manual que todo mundo já fez

Quem nunca teve uma estrutura como essa?

```
projeto/
├── trabalho_v1.py
├── trabalho_v2.py
├── trabalho_final.py
├── trabalho_final_MESMO.py
└── trabalho_final_AGORA_VAI_definitivo.py
```

Isso é controle de versão manual. Funciona enquanto você trabalha sozinho num arquivo simples. Mas falha quando:

- O projeto tem dezenas de arquivos
- Mais de uma pessoa precisa trabalhar ao mesmo tempo
- Você precisa saber **por que** uma mudança foi feita, não só **o que** mudou
- Você precisa voltar para um estado anterior específico

### O problema de colaboração

Imagine que você e mais três colegas estão trabalhando no mesmo arquivo `server.js`. Cada um faz uma mudança diferente ao longo do dia. Como vocês juntam tudo ao final?

**Anote aqui** — qual seria sua solução sem Git?

```
Sua resposta:


```

---

## 3. O modelo mental do Git

O Git organiza seu trabalho em três zonas distintas. Entender esse modelo é mais importante do que memorizar comandos.

```
┌─────────────────────┐        ┌─────────────────────┐        ┌─────────────────────┐
│                     │        │                     │        │                     │
│  Working Directory  │──────▶│    Staging Area     │──────▶│     Repository      │
│                     │git add │                     │git commit                   │
│   (suas edições)    │        │  (o que vai entrar  │        │  (histórico perma-  │
│                     │        │   no próximo commit)│        │   nente de versões) │
└─────────────────────┘        └─────────────────────┘        └─────────────────────┘
```

### Working Directory

É sua mesa de trabalho. Tudo que você está editando agora — arquivos modificados, criados, deletados — mas ainda não comprometido com o histórico.

### Staging Area

A antessala do commit. Você **escolhe** o que vai fazer parte da próxima versão. Isso permite um controle fino: num dia em que você editou 10 arquivos, pode fazer 3 commits distintos, cada um com um propósito específico.

**Por que a Staging Area existe?** Porque nem toda mudança que você faz num dia precisa ir junta num único commit. Commits com propósito único contam histórias claras.

### Repository

O histórico permanente. Cada commit é um snapshot do projeto num momento específico, associado a:

- Um identificador único (hash SHA-1)
- Uma mensagem descritiva
- Autor e data
- Um ponteiro para o commit anterior

Esse histórico **não desaparece**. É o que transforma Git em máquina do tempo.

---

## 4. Os três conceitos fundamentais

### Commits — registros de mudança

O commit é a operação central do Git. Cada commit registra um conjunto de mudanças com uma mensagem que explica **o porquê**.

**Boas mensagens de commit fazem diferença:**

|Mensagem fraca|Mensagem forte|
|---|---|
|`atualiza código`|`fix: corrige erro de validação no formulário de login`|
|`mais mudanças`|`feat: adiciona endpoint de listagem de projetos`|
|`arrumei`|`refactor: extrai função de cálculo para módulo separado`|

O padrão `tipo: descrição` é chamado **Conventional Commits**. Você vai praticar isso na quinta-feira.

### Branches — linhas paralelas de desenvolvimento

Uma branch é uma linha independente de desenvolvimento. Ela permite que diferentes pessoas (ou você mesmo em momentos diferentes) trabalhem em funcionalidades distintas sem interferir umas nas outras.

```
main ────●────────────────────────────●────▶
          \                          /
           ●──●──● (feature/login) ●
```

> O erro mais comum: trabalhar tudo na branch `main`. Isso elimina o principal benefício das branches.

### Merge — integração de branches

Quando o trabalho numa branch está pronto, ele precisa ser integrado à branch principal. Isso se chama merge. Pode acontecer automaticamente ou exigir resolução manual de conflitos — quando duas branches modificaram o mesmo trecho de código de formas diferentes.

**Branches e merge são o coração da colaboração em equipe.** Você vai aprofundar isso amanhã — incluindo qual estratégia de branch faz sentido para o projeto de vocês.

---

## 5. Ciclo básico do Git — acompanhe a demonstração

Durante a demonstração ao vivo, use este espaço para anotar os comandos e o que cada um faz:

|Comando|O que faz|
|---|---|
|`git init`||
|`git status`||
|`git add <arquivo>`||
|`git commit -m "mensagem"`||
|`git log`||
|`git log --oneline`||
|`git diff`||

---

## 6. Por que o histórico é poder

Um repositório Git bem mantido não é apenas backup — é **rastreabilidade**. Com um histórico limpo, você consegue:

- Saber **o que** mudou em qualquer momento do projeto
- Saber **quem** fez cada mudança e **quando**
- Saber **por que** a mudança foi feita (se a mensagem de commit for boa)
- Voltar para qualquer estado anterior do projeto
- Identificar em qual commit um bug foi introduzido

**No seu projeto de extensão**, esse histórico vai ser parte da entrega. Mais importante: você vai precisar dele quando, na Semana 10, precisar entender por que tomou uma decisão na Semana 6.

**Anote aqui** — cite um cenário do seu projeto onde um histórico bem documentado seria especialmente valioso:

```
Sua resposta:


```

---

## 7. Gestão de Configuração: além do Git

O Cap. 3.1 apresenta a **Gestão de Configuração** como a disciplina mais ampla da qual o versionamento é uma parte. Ela inclui:

- **Identificação de configuração:** quais itens precisam ser controlados (código, testes, documentação, configurações de ambiente)
- **Controle de mudanças:** processos para aprovar e registrar alterações
- **Auditoria de configuração:** verificação de que o produto é consistente com o que foi especificado
- **Rastreabilidade:** conexão entre requisitos, código e testes

O Git é a ferramenta que implementa grande parte dessas práticas no dia a dia. Mas a ferramenta serve à disciplina — não o contrário.

---

## 8. Questão estruturante para reflexão

> _"Por que o versionamento é considerado uma prática indispensável no desenvolvimento de software moderno? O que mudaria no projeto de vocês se ele não existisse?"_

Anote sua perspectiva antes da discussão:

```
Sua resposta inicial:


```

---

## 9. Para a próxima aula (Terça-feira)

📖 **Leitura obrigatória:** Cap. 3, seções 3.4.1 a 3.4.6

**Traga para a aula:** uma resposta para esta pergunta — "qual das estratégias de branch que você vai ler (Git Flow, Feature Branch, Trunk-Based) faria mais sentido para o projeto da sua equipe? Por quê?"

Não é uma pergunta com resposta certa. É uma pergunta de julgamento — e você vai defender sua resposta amanhã.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_ _Referência: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 3, seções 3.1–3.3._
