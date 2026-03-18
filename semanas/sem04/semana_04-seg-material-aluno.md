# Semana 4 — Segunda-feira

## Por que a organização do código importa

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **23/03/2026 | E132 | 17:00–18:40**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 14, seções 14.1.1 e 14.1.2 (Princípios fundamentais; Integração no design)

📖 _Engenharia de Software Moderna_ (Valente) — Cap. 5: Princípios de Projeto (Integridade Conceitual; Ocultamento de Informação; Coesão; Acoplamento)

Se você não leu antes de vir, tudo bem — mas leia antes da próxima aula.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar por que a organização interna do código afeta diretamente a capacidade de uma equipe trabalhar junto
- Diferenciar coesão alta de coesão baixa com exemplos concretos em JavaScript
- Reconhecer acoplamento excessivo e explicar por que ele dificulta a manutenção
- Aplicar o princípio de separação de responsabilidades ao projeto da sua equipe

---

## 1. Uma pergunta antes de começar

> _"Se o código funciona, por que importa como ele está organizado?"_

Use este espaço para anotar sua resposta antes da discussão:

```
Sua resposta inicial:


```

---

## 2. Dois códigos, um problema

Considere estes dois trechos de JavaScript que fazem a mesma coisa — cadastrar um usuário e enviar um e-mail de boas-vindas:

### Versão A — Tudo junto

```javascript
app.post('/register', async (req, res) => {
  const { name, email, password } = req.body;
  if (!name || !email || !password) return res.status(400).json({ error: 'Campos obrigatórios' });
  if (password.length < 8) return res.status(400).json({ error: 'Senha fraca' });
  const existing = await db.query('SELECT * FROM users WHERE email = $1', [email]);
  if (existing.rows.length > 0) return res.status(409).json({ error: 'Email já cadastrado' });
  const hash = await bcrypt.hash(password, 10);
  const result = await db.query('INSERT INTO users (name, email, password) VALUES ($1, $2, $3) RETURNING id', [name, email, hash]);
  const userId = result.rows[0].id;
  await transporter.sendMail({
    from: 'noreply@app.com', to: email,
    subject: 'Bem-vindo!', html: `<h1>Olá ${name}!</h1><p>Sua conta foi criada.</p>`
  });
  res.status(201).json({ id: userId, name, email });
});
```

### Versão B — Responsabilidades separadas

```javascript
// userValidator.js
function validateRegistration({ name, email, password }) {
  if (!name || !email || !password) return 'Campos obrigatórios';
  if (password.length < 8) return 'Senha fraca';
  return null;
}

// userService.js
async function registerUser({ name, email, password }) {
  const exists = await userRepository.findByEmail(email);
  if (exists) throw new ConflictError('Email já cadastrado');
  const hash = await bcrypt.hash(password, 10);
  return userRepository.create({ name, email, password: hash });
}

// emailService.js
async function sendWelcome(user) {
  await transporter.sendMail({
    from: 'noreply@app.com', to: user.email,
    subject: 'Bem-vindo!', html: templates.welcome(user)
  });
}

// userController.js
app.post('/register', async (req, res) => {
  const error = validateRegistration(req.body);
  if (error) return res.status(400).json({ error });
  const user = await registerUser(req.body);
  await sendWelcome(user);
  res.status(201).json(user);
});
```

**Reflexão — anote aqui:**

Qual versão você prefere manter? Por quê?

```
Sua resposta:


```

Se um membro da sua equipe precisa mudar como o e-mail é enviado, em qual versão ele consegue fazer isso sem risco de quebrar o cadastro?

```
Sua resposta:


```

---

## 3. Princípios fundamentais de design de software

O capítulo 14 do livro apresenta princípios que guiam decisões sobre como organizar o código. Para o 2º período, os mais importantes são:

### Separação de Responsabilidades

Cada módulo, função ou classe deve ter **uma única razão para mudar**. Se um arquivo faz validação, acesso ao banco e envio de e-mail ao mesmo tempo, qualquer mudança em uma dessas partes pode quebrar as outras.

Na prática do projeto: separar rotas, controllers, services e models.

### Coesão

Um módulo é **coeso** quando tudo dentro dele está relacionado ao mesmo propósito. Uma função `registerUser` que também envia e-mail tem baixa coesão — ela mistura dois propósitos distintos.

| Coesão alta | Coesão baixa |
|---|---|
| `userService.js` cuida só de lógica de usuário | `utils.js` com 40 funções sobre assuntos diferentes |
| `emailService.js` cuida só de envio de e-mail | Um controller que faz validação, consulta ao banco e envio de e-mail |

### Acoplamento

Dois módulos são **acoplados** quando uma mudança em um exige mudança no outro. O objetivo é minimizar acoplamento — cada módulo deve depender o mínimo possível dos detalhes internos de outros módulos.

**Exemplo concreto:** se o `userController.js` acessar diretamente o banco de dados em vez de chamar o `userService.js`, qualquer mudança na estrutura do banco obriga a mudar o controller também. Com o service no meio, a mudança fica isolada.

### Abstração e nomes significativos

Bons nomes eliminam a necessidade de comentários. Compare:

```javascript
// Ruim
const d = new Date();
const x = d.getTime() - s.getTime();
if (x > 86400000) { ... }

// Bom
const now = new Date();
const elapsedMs = now.getTime() - sessionStart.getTime();
const ONE_DAY_MS = 24 * 60 * 60 * 1000;
if (elapsedMs > ONE_DAY_MS) { ... }
```

---

## 4. Conexão com o seu projeto

A partir desta semana, sua equipe começa a construir código de verdade. As decisões de organização que vocês tomarem agora vão definir se vocês conseguem trabalhar juntos nas próximas 8 semanas — ou se cada merge vai ser uma dor de cabeça.

**Perguntas para discutir com a equipe (na quinta-feira):**

- Como vamos organizar as pastas do projeto?
- Quem é responsável por cada módulo?
- Como evitamos que duas pessoas mexam na mesma coisa ao mesmo tempo?

**Estrutura sugerida para o projeto:**

```
projeto/
├── backend/
│   ├── src/
│   │   ├── routes/         ← definição de rotas
│   │   ├── controllers/    ← recebe request, chama service, retorna response
│   │   ├── services/       ← lógica de negócio
│   │   ├── repositories/   ← acesso ao banco de dados
│   │   └── utils/          ← funções auxiliares genéricas
│   └── tests/
├── frontend/
│   ├── src/
│   │   ├── pages/          ← páginas/telas da aplicação
│   │   ├── components/     ← componentes reutilizáveis
│   │   ├── hooks/          ← hooks customizados
│   │   └── services/       ← chamadas à API
│   └── tests/
└── docs/                   ← diagramas C4, ADRs, README
```

---

## 5. Questão estruturante para reflexão

> _"Como a organização interna de um sistema de software influencia a capacidade de uma equipe de mantê-lo e evoluí-lo ao longo do tempo?"_

Esta pergunta não tem resposta única. O que importa é que você consiga argumentar com exemplos concretos.

```
Sua resposta:


```

---

## 6. Para a próxima aula (Terça-feira)

📖 **Leitura obrigatória:** Cap. 14, seções 14.3.1 a 14.3.3 (Estrutura hierárquica do C4 Model) e seção 14.4 (C4 vs UML)

📖 **Leitura complementar:** Valente, Cap. 7 — Arquitetura (seções: Camadas; MVC)

**Traga para a aula:** um rascunho mental (ou no papel) de quem são os "atores" que interagem com o sistema do seu projeto e quais são os grandes blocos técnicos que vão existir.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_ _Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 14, seções 14.1.1–14.1.2._ _Valente, M. T. Engenharia de Software Moderna. 2022. Cap. 5._
