# Semana 13 — Terça-feira

## ✏️ PROVA 2

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **09/06/2026 | E132 | 17:00–18:40**

---

## Sobre esta aula

Esta aula é inteiramente dedicada à Prova 2. Não há leitura prévia, não há discussão, não há atividade em grupo.

Use este documento como guia de revisão — não como roteiro de aula.

---

## O que será avaliado

**Conteúdo: Semanas 8 a 12**

A prova cobre os cinco temas centrais do Ensaio (Sprints 2, 3 e 4):

| Tema | Semanas | Referências principais |
|------|---------|----------------------|
| Testes de software | 8, 9 | Garcia Cap. 9; Valente Cap. 8 |
| Refactoring | 10 | Valente Cap. 9 |
| Manutenção e dívida técnica | 10 | Garcia Cap. 19 |
| Qualidade arquitetural | 11 | Garcia Cap. 14; Valente Cap. 5 e 7 |
| Code Review e Documentação | 12 | Garcia Cap. 3 (seção 3.5) e Cap. 19 (seção 19.4) |

---

## Formato da prova

- **Questões dissertativas e de análise de caso**
- Não há múltipla escolha, verdadeiro/falso ou questões de completar lacunas
- O que se avalia: raciocínio, conexão entre conceitos, capacidade de aplicar teoria a situações concretas
- Você pode usar exemplos do seu próprio projeto nas respostas — isso é bem-vindo

---

## Guia de revisão por tema

### 1. Testes de software

**O que você precisa dominar:**

- **Pirâmide de testes:** por que a proporção importa (muitos unitários, poucos E2E)
- **Testes unitários:** granularidade, isolamento, o papel dos mocks
- **Testes de integração:** quando um teste unitário não é suficiente
- **Testes E2E (Playwright):** o que garantem que os outros não garantem; custo de manutenção
- **TDD:** o ciclo red → green → refactor; o que muda quando o teste vem antes
- **BDD e Gherkin:** _Given / When / Then_; por que escrever em linguagem de negócio

**Perguntas para autoavaliação:**

> "Por que escrever testes unitários se o produto funciona manualmente?"

> "Qual é a diferença entre um teste que passa e um teste que dá confiança?"

> "Uma equipe tem 90% de cobertura de código mas o produto falha na demo. O que pode ter acontecido?"

---

### 2. Refactoring

**O que você precisa dominar:**

- **Code smells:** pelo menos 5 exemplos com definição e consequência (ex: Long Method, Duplicate Code, Feature Envy, God Class, Dead Code)
- **Refactoring seguro:** por que só refatorar com testes verdes
- **Catálogo de Fowler:** as transformações mais comuns (Extract Method, Rename Variable, Move Function, Replace Conditional with Polymorphism)
- **Refactoring vs. reescrita:** quando refatorar e quando abandonar

**Perguntas para autoavaliação:**

> "Uma função tem 200 linhas e resolve 5 problemas diferentes. Qual o code smell? Qual a transformação indicada?"

> "Você quer refatorar um módulo crítico, mas não há testes. O que você faz primeiro?"

> "Existe refactoring que piora o código? Como você saberia?"

---

### 3. Manutenção e dívida técnica

**O que você precisa dominar:**

- **Tipos de manutenção:** corretiva (bugs), adaptativa (mudanças de ambiente), perfectiva (melhoria), preventiva (refactoring proativo)
- **Dívida técnica:** a metáfora financeira; dívida intencional vs. acidental; juros que o código paga
- **Quando contrair dívida faz sentido:** deadline, MVP, prova de conceito
- **Custo de manutenção ao longo do tempo:** por que o custo de mudança aumenta com o tempo sem refactoring

**Perguntas para autoavaliação:**

> "Qual a diferença entre manutenção corretiva e perfectiva? Dê um exemplo de cada um do contexto do projeto."

> "Uma equipe decidiu não escrever testes para entregar mais rápido. Isso é dívida técnica? É intencional ou acidental?"

> "Depois de quanto tempo de não-manutenção um sistema começa a ficar impossível de manter? Depende de quê?"

---

### 4. Qualidade arquitetural

**O que você precisa dominar:**

- **Coesão:** alta coesão como virtude; um módulo deve ter uma razão para existir
- **Acoplamento:** baixo acoplamento como virtude; dependências que podem se tornar prisões
- **Impacto de decisões de design:** como a arquitetura da Semana 9 (ou 6–7) afeta o que é possível fazer hoje
- **C4 Model como diagnóstico:** usar o diagrama para entender o que está errado
- **Debugging:** breakpoints, stack traces, tratamento de erros em JavaScript/Node

**Perguntas para autoavaliação:**

> "Uma mudança pequena em uma parte do sistema quebrou três partes que 'não deveriam ter relação'. O que isso indica arquiteturalmente?"

> "Alta coesão e baixo acoplamento são sempre atingíveis ao mesmo tempo? Em que situações há tensão entre os dois?"

> "Como os diagramas C4 podem ajudar a identificar problemas de acoplamento antes de abrir o código?"

---

### 5. Code Review e Documentação

**O que você precisa dominar:**

- **Checklist avançado de code review:** legibilidade, testes presentes, erros tratados, convenções respeitadas, documentação atualizada
- **O que não é code review:** revisão de estilo sem contexto, aprovação automática, review sem feedback
- **README como contrato:** o que um bom README deve conter; a pergunta "outra equipe conseguiria continuar?"
- **Documentação de decisões arquiteturais:** por que documentar o "porquê" é mais valioso que o "o quê"
- **Conhecimento como ativo:** dívida de documentação tem o mesmo risco que dívida técnica

**Perguntas para autoavaliação:**

> "Qual a diferença entre um PR aprovado e um PR que melhorou o código?"

> "Um desenvolvedor novo no projeto abre o README. O que ele precisaria encontrar para conseguir rodar o projeto localmente sem pedir ajuda?"

> "Uma equipe tem o código bem comentado linha a linha, mas nenhum documento de arquitetura. O que está faltando?"

---

## Na hora da prova

**Instruções gerais:**

- Leia o enunciado completo antes de começar a responder
- Gerencie o tempo: 100 minutos para todas as questões
- Respostas completas valem mais que respostas longas — vá direto ao ponto
- Exemplos do projeto enriquecem a resposta quando bem contextualizados
- Definições copiadas sem explicação própria não demonstram compreensão

**Deixe espaço para pensar antes de escrever.** A qualidade do raciocínio conta mais que a quantidade de palavras.

---

## Para a próxima aula (Quinta-feira)

🎯 **Sprint 4 Review + Estabilização final do MVP — 11/06/2026 | 17:00–20:30 | Grad04**

Leve para a quinta:
- O projeto em estado de demo (deploy funcional ou localhost estável)
- A demo ensaiada (10 min + 5 min de perguntas do stakeholder)
- O repositório organizado: README, diagramas C4, testes passando

EI4 — Reflexão Técnica e Profissional: entrega **domingo, 14/06**, via formulário do professor.

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
_Conteúdo avaliado: Semanas 8–12._
_Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 9, 14, 19._
_Valente, M. T. Engenharia de Software Moderna. 2022. Cap. 5, 7, 8, 9._
