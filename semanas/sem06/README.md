# Semana 6 — Design e Arquitetura de Software (Parte 1)

**CIN0136: Desenvolvimento de Software | CIn-UFPE**

---

## Aulas desta semana

| Dia | Horário | Sala | Tema | Materiais |
|-----|---------|------|------|-----------|
| 🔵 Segunda | 18:50–20:30 | E132 | Introdução ao Design e Projeto de Arquitetura de Software | [Material do Aluno](./semana_06-seg-material-aluno.md) · [Guia do Professor](./semana_06-seg-material-professor.md) |
| 🟢 Terça | 17:00–18:40 | E132 | O que são APIs + Princípios de design de software | [Material do Aluno](./semana_06-ter-material-aluno.md) · [Guia do Professor](./semana_06-ter-material-professor.md) |
| 🟠 Quinta | 17:00–20:30 | Grad04 | Lab (Workshop de Arquitetura): arquitetura aplicada ao projeto + Desenvolvimento Sprint 1 | *(materiais na pasta `lab`)* |

---

## Leituras prévias por dia

### 🔵 Segunda-feira — antes de vir para a aula

📖 **Garcia** — *Engenharia de Software em Dimensões*, Cap. 14, **seções 14.1.1 e 14.1.2**
> Princípios fundamentais de arquitetura de software; Integração no design

📖 **Valente** — *Engenharia de Software Moderna*, Cap. 7 **(seções iniciais)**
> Arquitetura em Camadas e MVC — base conceitual para o que será visto em aula

**Questões guia para a leitura:**
- O que torna uma decisão de design arquitetural diferente de uma decisão de implementação?
- Por que uma mudança no banco de dados pode afetar a camada de apresentação, e como a arquitetura em camadas evita isso?

### 🟢 Terça-feira — antes de vir para a aula

📖 **Garcia** — *Engenharia de Software em Dimensões*, Cap. 14, **seções 14.1.1–14.1.2** (continuação)

📖 **Valente** — *Engenharia de Software Moderna*, **Cap. 5** — Princípios de Projeto
> Integridade Conceitual, Ocultamento de Informação, Coesão, Acoplamento

**Trazer para a aula:** dois trechos do código do seu projeto — um que você acha bem organizado, outro que te incomoda sem saber exatamente por quê. A aula vai ajudar a nomear o que você está sentindo.

**Questões guia para a leitura:**
- O que é coesão? Como você reconhece um módulo com baixa coesão?
- Qual é a diferença entre acoplamento aceitável e acoplamento problemático?

### 🟠 Quinta-feira (Workshop de Arquitetura) — sem leitura prévia formal

Venha com o **repositório do projeto aberto** — o lab exigirá análise e refatoração do código real.

---

## Objetivos da semana

Ao final da Semana 6, você deve ser capaz de:

1. Explicar como HTTP, TCP/IP e o modelo cliente-servidor funcionam juntos numa aplicação web
2. Identificar as três camadas arquiteturais (apresentação, lógica, dados) e associá-las às tecnologias do projeto (React, Express, banco)
3. Descrever o papel de uma API como contrato documentado entre partes do sistema
4. Aplicar os princípios de separação de responsabilidades, coesão, baixo acoplamento e nomes significativos ao código do projeto
5. Mapear a arquitetura do projeto real nas 3 camadas e identificar violações de design
6. Ler um diagrama de sequência simples e relacionar cada seta a uma fronteira de responsabilidade
7. Registrar uma decisão de arquitetura em um ADR (Architecture Decision Record, formato Nygard)

---

## Entregáveis com prazo

| Entregável | Descrição | Prazo |
|------------|-----------|-------|
| **Mapeamento de camadas** (lab de quinta) | Diagrama simples (pode ser texto) mostrando onde cada camada existe no repositório da equipe | Durante o lab de quinta |
| **Estrutura de pastas organizada** (lab de quinta) | Repositório com separação routes / controllers / services / repositories no backend e pages / components / services no frontend | Ao final do lab de quinta |
| **Features em progresso** (lab de quinta) | Mínimo 2 features com código iniciado no repositório | Ao final do lab de quinta |
| **Decisões registradas em ADR** (lab de quinta) | Pasta `docs/` no repositório com pelo menos um ADR no formato Nygard (por exemplo, a decisão do banco de dados) | Ao final do lab de quinta |

> 📌 **EI2 — Portfólio de Requisitos** foi entregue na Semana 3. Verifique se está completo no repositório antes do lab.

---

## Recursos relevantes

### Referências principais

- Garcia, V. C. *Engenharia de Software em Dimensões*. ASSERT Lab, 2025. **Cap. 14** (seções 14.1–14.8)
- Valente, M. T. *Engenharia de Software Moderna*. 2020. **Cap. 5** (Princípios de Projeto) e **Cap. 7** (Arquitetura)

### Recursos complementares

- [MDN Web Docs — HTTP overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview) — referência definitiva sobre HTTP
- [Express.js — Routing](https://expressjs.com/en/guide/routing.html) — anatomia de rotas no Express
- [REST API Design Best Practices](https://www.freecodecamp.org/news/rest-api-best-practices-rest-endpoint-design-examples/) — boas práticas de design de API
- [Refactoring.Guru — Separation of Concerns](https://refactoring.guru/) — catálogo de princípios de design com exemplos
- [Mermaid Live Editor](https://mermaid.live) — para escrever e testar diagramas (sequência, fluxo, C4) como texto
- Nygard, M. *Documenting Architecture Decisions* (2011) — o artigo que originou o formato de ADR usado na disciplina (busque pelo título)

### Ferramentas

- **Postman** ou **Insomnia** — para explorar e testar APIs
- **Thunder Client** (extensão VS Code) — alternativa mais leve ao Postman
- **DevTools do Chrome** (aba Network) — para observar requisições HTTP em tempo real

---

## Por que esta semana importa para o Sprint 1

Você está no início do Sprint 1. O código que você escreve agora vai ser mantido por você — e pelos seus colegas de equipe — por mais 3 sprints. Esta é a semana em que a decisão de organizar bem o código (ou não) tem o menor custo e o maior impacto.

A separação em camadas que discutimos na segunda não é teoria desconectada da prática — é exatamente a estrutura que o Express e o React já sugerem. A decisão não é *se* vai ter camadas, mas *o quão bem definidas* elas estarão quando o Sprint 2 começar.

Os princípios de design da terça são o vocabulário que a equipe vai usar para revisar código uns dos outros. Sem esse vocabulário, o feedback de code review fica vago: "esse código tá feio". Com ele, o feedback fica acionável: "esse controller tem baixa coesão — a lógica de validação deveria estar num validator separado".

O código mostra *o quê*; um **ADR** registra *o porquê* de uma decisão de arquitetura (por que SQLite? por que camadas?). Em quatro semanas, ninguém vai lembrar por que uma decisão foi tomada, a menos que esteja escrito no repositório, em `docs/`.

O Workshop de Arquitetura é o momento de consolidar essas decisões no repositório real. Venha preparado.

---

*CIN0136 — Desenvolvimento de Software | CIn-UFPE | Sprint 1*
