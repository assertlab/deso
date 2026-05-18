# Semana 11 — Terça-feira

## Debugging, robustez e preparação para Sprint Review

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **26/05/2026 | E132 | 17:00–18:40**

---

## Leitura Prévia

📖 Nenhuma leitura prévia formal para esta aula.

Traga o projeto rodando localmente e **um bug ou comportamento inesperado** que sua equipe não conseguiu explicar nos últimos dias. Se não tiver um bug, traga uma função que você não tem certeza se está funcionando corretamente.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Usar breakpoints no VS Code para inspecionar o estado do programa em tempo de execução
- Ler e interpretar stack traces para localizar a origem de erros
- Aplicar try/catch de forma estratégica em JavaScript — onde colocar e o que capturar
- Implementar respostas HTTP adequadas para erros no Express (4xx vs 5xx)
- Tratar erros em componentes React com error boundaries
- Preparar uma demonstração de qualidade para o stakeholder com foco nos fluxos críticos

---

## 1. Uma pergunta antes de começar

> _"Você já perdeu mais de uma hora em um bug que, quando encontrou, era uma linha de código — mas você não sabia onde procurar?"_

Esse é exatamente o problema que o debugging sistemático resolve: **não é o bug que demora, é a busca**.

Anote o último bug que levou mais tempo do que deveria para resolver:

```
O que o bug fazia:


Quanto tempo levou:


Como você finalmente encontrou:


```

---

## 2. O problema com o debugging por tentativa e erro

A maioria dos programadores inicia com um padrão de debugging que parece natural mas é ineficiente:

```
Bug aparece
    ↓
Adicionar console.log aleatório
    ↓
Não ajuda / confunde mais
    ↓
Adicionar mais console.log
    ↓
Não encontra → desespero → chuta alteração
    ↓
Bug "some" (mas pode voltar)
```

O problema não é usar `console.log` — é não ter uma **hipótese** antes de adicionar o log. Debugging eficiente é investigação científica:

```
Bug aparece
    ↓
Reproduzir de forma consistente
    ↓
Formular hipótese sobre a causa
    ↓
Testar a hipótese (breakpoint / log estratégico)
    ↓
Confirmar ou refutar → nova hipótese ou correção
    ↓
Escrever teste para garantir que não volta
```

---

## 3. Breakpoints no VS Code: o que é e como usar

Um **breakpoint** pausa a execução do programa em uma linha específica e permite inspecionar tudo: variáveis locais, pilha de chamadas, estado dos objetos.

### Como ativar para Node.js/Express

1. Abra o arquivo onde quer parar a execução
2. Clique na margem esquerda ao lado do número da linha (aparece um ponto vermelho)
3. No VS Code, pressione `F5` → selecione "Node.js"
4. A execução pausa na linha marcada

### O que inspecionar quando o programa está pausado

```
JANELA "VARIABLES"
├── Local → variáveis da função atual
├── Closure → variáveis do escopo exterior
└── Global → variáveis globais (raramente o problema)

JANELA "CALL STACK"
└── A sequência de chamadas que chegou até aqui
    (leia de baixo para cima — a origem está embaixo)

JANELA "WATCH"
└── Expressões que você quer monitorar continuamente
    (ex: req.body, user.id, array.length)
```

### Navegação durante o debug

| Tecla | O que faz |
|---|---|
| `F10` | Step Over — executa a linha atual, vai para a próxima |
| `F11` | Step Into — entra dentro da função chamada |
| `Shift+F11` | Step Out — sai da função atual |
| `F5` | Continue — continua até o próximo breakpoint |

**Quando usar cada um:**
- Step Over: para avançar sem entrar em detalhes
- Step Into: quando o bug provavelmente está dentro da função chamada
- Continue: quando você quer ver o próximo breakpoint

---

## 4. Lendo stack traces

Um stack trace é a trilha de pão que o erro deixa. Saber ler um stack trace é a diferença entre 5 minutos e 1 hora de debugging.

### Exemplo de stack trace em Node.js/Express

```
TypeError: Cannot read properties of undefined (reading 'name')
    at getUserName (/app/services/userService.js:23:20)   ← aqui está o erro
    at /app/routes/users.js:15:30                         ← quem chamou
    at Layer.handle [as handle_request] (/app/node_modules/express/lib/router/layer.js:95:5)
    at next (/app/node_modules/express/lib/router/route.js:137:13)
    ← ignore as linhas de node_modules — você não vai depurar o Express
```

**Regra prática:** leia o stack trace de cima para baixo, mas **pare na primeira linha que referencia o seu código** (não `node_modules`). Essa é a origem do erro.

### Exercício: decodifique este stack trace

```
Error: ENOENT: no such file or directory, open '/app/config/database.json'
    at Object.openSync (node:fs:596:3)
    at Object.readFileSync (node:fs:464:35)
    at loadConfig (/app/utils/config.js:8:18)
    at Object.<anonymous> (/app/server.js:3:1)
    at Module._compile (node:internal/modules/cjs/loader:1364:14)
```

**Responda:**
- Qual é o erro? _______________________________________________
- Em qual arquivo do **seu** código está a causa? _______________
- O que provavelmente está acontecendo? _________________________

---

## 5. Tratamento de erros em JavaScript: try/catch estratégico

`try/catch` não é para envolver o código inteiro — é para envolver **operações que podem falhar por razões fora do seu controle**: chamadas a banco de dados, leituras de arquivo, requests externos, parsing de JSON.

### Onde colocar try/catch no Express

```javascript
// ❌ Muito genérico — mascara bugs reais
try {
  const users = await getUsers();
  const filtered = users.filter(u => u.active); // se isso falhar, você não sabe por quê
  res.json(filtered);
} catch (err) {
  res.status(500).json({ error: 'Something went wrong' });
}

// ✅ Específico — captura o que pode falhar e deixa o resto propagar
const users = await getUsers().catch(err => {
  console.error('[DB] Falha ao buscar usuários:', err.message);
  res.status(503).json({ error: 'Database unavailable' });
  return null;
});

if (!users) return; // interrompe se o banco falhou

const filtered = users.filter(u => u.active); // isso não vai falhar — é lógica sua
res.json(filtered);
```

### Respostas HTTP para erros: 4xx vs 5xx

O status HTTP que você retorna informa ao cliente (e ao desenvolvedor que mantém o frontend) o que aconteceu:

| Status | Quando usar | Exemplo |
|---|---|---|
| `400 Bad Request` | O cliente mandou dados inválidos | Campo obrigatório ausente |
| `401 Unauthorized` | Não autenticado | Token ausente ou inválido |
| `403 Forbidden` | Autenticado mas sem permissão | Usuário comum tentando rota de admin |
| `404 Not Found` | Recurso não existe | `GET /users/9999` e o usuário não existe |
| `422 Unprocessable Entity` | Dados válidos no formato mas inválidos no negócio | Email já cadastrado |
| `500 Internal Server Error` | Erro inesperado no servidor | Banco caiu, exceção não tratada |
| `503 Service Unavailable` | Serviço dependente indisponível | Banco de dados fora do ar |

**Anote:** qual status HTTP seu backend usa quando algo dá errado atualmente? É sempre 500? Isso pode estar dificultando o debugging no frontend.

```
Status que nossa API usa hoje:


O que deveria usar:


```

---

## 6. Error Boundaries em React

No React, um erro em um componente sem tratamento derruba a árvore inteira — o usuário vê a tela branca. **Error Boundaries** interceptam erros em tempo de renderização e mostram um fallback.

### Implementação básica

```jsx
import { Component } from 'react';

class ErrorBoundary extends Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false, error: null };
  }

  static getDerivedStateFromError(error) {
    return { hasError: true, error };
  }

  componentDidCatch(error, info) {
    // Aqui você logaria para um serviço como Sentry
    console.error('[ErrorBoundary]', error, info.componentStack);
  }

  render() {
    if (this.state.hasError) {
      return (
        <div className="error-fallback">
          <h2>Algo deu errado.</h2>
          <button onClick={() => this.setState({ hasError: false })}>
            Tentar novamente
          </button>
        </div>
      );
    }
    return this.props.children;
  }
}

// Uso:
// <ErrorBoundary>
//   <MeuComponenteQuePodefFalhar />
// </ErrorBoundary>
```

**Onde colocar:**
- Ao redor de seções críticas da interface (lista de dados, formulários)
- Ao redor de componentes que fazem fetch de dados
- **Não** ao redor de componentes triviais (botões, textos estáticos)

---

## 7. console.log estratégico

Quando não usar breakpoints (ambiente de produção, código de colega), `console.log` ainda é válido — mas de forma estruturada:

```javascript
// ❌ Inútil
console.log(data);

// ✅ Útil: contexto + valor + localização
console.log('[userService.getById] userId recebido:', userId);
console.log('[userService.getById] resultado do banco:', JSON.stringify(user, null, 2));

// ✅ Para erros com contexto
console.error('[routes/users] Falha no GET /users/:id', {
  userId: req.params.id,
  error: err.message,
  stack: err.stack
});
```

**Regra:** se você vai adicionar um log, seja específico sobre **onde está** e **o que está imprimindo**. Logs genéricos aumentam o ruído, não diminuem.

---

## 8. Preparação para o Sprint Review (quinta-feira)

A Sprint 3 Review acontece quinta-feira. O stakeholder vai ver o produto. A aula de amanhã (quinta) começa com 2h de desenvolvimento final antes da review.

Use este checklist para garantir que a demo não vai travar:

### Checklist de robustez antes da demo

**Fluxos críticos (devem funcionar sem falhas):**
- [ ] Login / autenticação (se aplicável)
- [ ] Funcionalidade principal do MVP
- [ ] Criação de dados (formulário → banco → confirmação)
- [ ] Listagem / visualização de dados

**Tratamento de erros mínimo:**
- [ ] O que acontece se o banco de dados demorar? (loading state)
- [ ] O que acontece se o usuário submeter o formulário com dados inválidos?
- [ ] O que acontece se a tela de detalhes receber um ID inválido?

**Interface:**
- [ ] Sem console.error visível no DevTools durante o fluxo principal
- [ ] Sem tela branca em nenhum cenário esperado
- [ ] Mensagens de erro legíveis para o usuário (não "Error: 500")

**Dados:**
- [ ] Banco de dados com dados de demonstração reais (não "teste", "aaa", "123")
- [ ] Fluxo completo funciona do início ao fim sem intervenção manual

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula — cole stack traces, anote comandos, registre o que funcionou]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
_Sem leitura prévia formal. Referência de apoio: documentação do VS Code Debugger (https://code.visualstudio.com/docs/editor/debugging) e MDN Web Docs — Error handling (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)._
