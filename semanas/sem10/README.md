# Semana 10 — Refactoring, Manutenção e Dívida Técnica

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1**
**Sprint 3 — Semanas 10 e 11**

---

## Aulas desta semana

| Dia | Tema | Material do Aluno | Guia do Professor |
|---|---|---|---|
| 🔵 Segunda, 18/05 | Refactoring: melhorar sem quebrar | [semana_10-seg-material-aluno.md](./semana_10-seg-material-aluno.md) | [semana_10-seg-material-professor.md](./semana_10-seg-material-professor.md) |
| 🟢 Terça, 19/05 | Manutenção, evolução e dívida técnica | [semana_10-ter-material-aluno.md](./semana_10-ter-material-aluno.md) | [semana_10-ter-material-professor.md](./semana_10-ter-material-professor.md) |
| 🟠 Quinta, 21/05 | Lab Refactoring + Desenvolvimento Sprint 3 | *(lab prático — sem material teórico)* | — |

---

## Leituras prévias

### Segunda-feira (18/05)
- 📖 **Garcia** — *Engenharia de Software em Dimensões*, Cap. 19, seções **19.2** (Tipos de Manutenção) e **19.3.1** (Refatoração Contínua)
- 📖 **Valente** — *Engenharia de Software Moderna*, Cap. 9 — seções: Catálogo de Refactorings; Prática de Refactoring; Refactorings Automatizados

### Terça-feira (19/05)
- 📖 **Garcia** — *Engenharia de Software em Dimensões*, Cap. 19, seções **19.1** (Evolução histórica da manutenção) e **19.4** (Documentação e gerenciamento de conhecimento)
- 📖 **Valente** — *Engenharia de Software Moderna*, Cap. 9 — seção: Code Smells (relação com dívida técnica e manutenção)

### Quinta-feira (21/05)
- Sem leitura prévia formal — venha com o ambiente de desenvolvimento funcionando.

---

## Objetivos da semana

Ao final da Semana 10, o aluno será capaz de:

- Definir refactoring com precisão e distingui-lo de correção de bugs e adição de features
- Identificar code smells em código JavaScript e associar cada um a uma refatoração correspondente
- Aplicar as refatorações fundamentais: Extract Function, Rename, Replace Magic Number, Guard Clauses, Eliminate Duplicate Code
- Classificar atividades de manutenção nos quatro tipos: corretiva, adaptativa, evolutiva, preventiva
- Explicar o conceito de dívida técnica e identificar onde ela está acumulada no próprio projeto
- Conduzir um ciclo completo de refactoring com testes verdes em cada passo

---

## Entregáveis com prazo

| Entregável | Prazo | Observações |
|---|---|---|
| 🔴 **Exercício Individual 3 — "Testes em JavaScript"** | **Domingo, 24/05** | Lançado na Quinta da Semana 9. Dado um módulo Node.js/Express: (1) testes de unidade com Vitest, (2) testes de aceitação, (3) relatório de cobertura, (4) análise crítica dos resultados. |
| ✅ **Sprint 3 — Início** | A partir de 21/05 | Desenvolvimento das features do Sprint 3 tem início no lab de quinta-feira. |

---

## Recursos relevantes

### Livros-texto
- Garcia, V. C. *Engenharia de Software em Dimensões*. ASSERT Lab, 2025. **Cap. 19** (Manutenção, Refactoring, Dívida Técnica, Documentação)
- Valente, M. T. *Engenharia de Software Moderna*. 2020. **Cap. 9** (Refactoring: Catálogo, Code Smells, Prática)

### Referências complementares
- Fowler, M. *Refactoring: Improving the Design of Existing Code*. 2ª ed. Addison-Wesley, 2018. — O livro de referência da área. O catálogo online está disponível em [refactoring.com](https://refactoring.com).
- Fowler, M. *TechnicalDebt* (bloga post). [martinfowler.com/bliki/TechnicalDebt.html](https://martinfowler.com/bliki/TechnicalDebt.html) — Leitura curta e direta ao ponto.

### Ferramentas
- **SonarLint** (extensão VS Code): analisa code smells em tempo real enquanto você digita
- **Vitest**: framework de testes para JavaScript/TypeScript — já utilizado no curso
- **Git**: `git diff` e histórico de commits como documentação de refactoring

---

## Por que esta semana importa para o Sprint 3

A Semana 10 marca a **entrada no Sprint 3** — o terceiro e último sprint de construção antes da estabilização final do MVP.

Até aqui, o foco foi **construir**: features, testes de aceitação, integração entre camadas, demo para o stakeholder. A Sprint 2 Review trouxe feedback real — e com ela, uma verdade desconfortável: código escrito sob pressão de prazo, aprendendo a stack ao mesmo tempo, acumula dívida técnica. Não por incompetência — por necessidade.

O Sprint 3 tem um duplo foco: continuar entregando features, mas fazendo isso sobre uma base de código mais limpa. É por isso que a Semana 10 começa com refactoring, não com novas funcionalidades. **Um sprint de qualidade não é o oposto de um sprint produtivo — é a condição para que os próximos sprints sejam produtivos.**

A conexão com a Sinfonia é direta: estamos no movimento de **Ensaio**, que é sobre construir *e testar*. "Testar" aqui inclui testar o próprio código — sua clareza, sua manutenibilidade, sua capacidade de evoluir. Software que não resiste a mudanças não está pronto para a Ressonância.

> O erro mais comum nesta fase é deixar para "refatorar depois". Depois é o Sprint 4 — que tem sua própria pressão. Refatorem agora, enquanto o contexto ainda está fresco.

---

*CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1*
*Última atualização: 18/05/2026*
