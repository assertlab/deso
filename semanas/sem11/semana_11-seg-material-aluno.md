# Semana 11 — Segunda-feira

## Impacto das decisões de design na qualidade

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1** **25/05/2026 | E132 | 18:50–20:30**

---

## Leitura Prévia

📖 _Engenharia de Software em Dimensões_ — Cap. 14, seções 14.7 e 14.8
_(Qualidade e Arquitetura; Impacto no sucesso do software)_

📖 _Engenharia de Software Moderna_ — Cap. 5 (SOLID e outros princípios — como más decisões geram problemas) + Cap. 7, seção Microsserviços (trade-offs arquiteturais)

Se você não leu antes de vir, leia antes da próxima aula — hoje o debate depende dessa base.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Analisar como decisões arquiteturais tomadas no início de um projeto se manifestam em problemas concretos de qualidade semanas depois
- Conectar os princípios SOLID com sintomas reais que sua equipe já está observando no código
- Identificar trade-offs em decisões de design e articular quais critérios guiaram as decisões da sua equipe
- Usar as seções 14.7–14.8 do livro como lente de análise para o seu próprio projeto

---

## 1. Uma pergunta antes de começar

> _"Você consegue apontar uma decisão arquitetural que sua equipe tomou nas Semanas 6 ou 7 e que hoje — semana 11 — está cobrado o preço?"_

Anote antes da discussão. Seja específico: qual foi a decisão, qual é o sintoma hoje.

```
Decisão tomada então:


Sintoma observado hoje:


```

---

## 2. O que o livro diz: qualidade e arquitetura

O Cap. 14 do Garcia argumenta que **cada decisão arquitetural tem um impacto direto e duradouro na qualidade e na sustentabilidade do produto**. Isso não é abstrato — é o que você está vivendo agora.

### 2.1 Como a arquitetura afeta a qualidade

Segundo as seções 14.7–14.8, a arquitetura impacta pelo menos quatro atributos de qualidade:

| Atributo | O que significa na prática |
|---|---|
| **Manutenibilidade** | Arquiteturas modulares facilitam mudanças sem efeito cascata |
| **Desempenho** | Escolhas de distribuição e acoplamento afetam tempo de resposta |
| **Segurança** | Segurança por design — não remendada depois |
| **Testabilidade** | Sistemas acoplados resistem a testes unitários |

**Releia a tabela pensando no seu projeto.** Marque o atributo que mais está sendo impactado positiva ou negativamente pelas suas escolhas:

- [ ] Manutenibilidade
- [ ] Desempenho
- [ ] Segurança
- [ ] Testabilidade

---

### 2.2 O impacto vai além da eficiência técnica

A seção 14.8.4 do livro faz uma afirmação importante:

> "O impacto do design e projeto da arquitetura de software vai além da eficiência técnica. Ele se reflete na qualidade do produto, na capacidade de inovação, na experiência do usuário e, em última instância, no sucesso do software no mercado."

Isso significa que a arquitetura não é uma decisão interna da equipe de desenvolvimento — ela afeta diretamente o que o **stakeholder experimenta**.

---

## 3. SOLID: princípios que viram problemas quando ignorados

O Valente (Cap. 5) apresenta o SOLID como um conjunto de princípios que orientam decisões de design. Mas a forma mais útil de aprender SOLID agora — na semana 11 — é pelo avesso: reconhecer os problemas que surgem quando eles são violados.

### O que cada princípio evita

| Princípio | Violação típica | Sintoma que você pode estar vendo |
|---|---|---|
| **Single Responsibility** | Um componente faz tudo | "Se eu mexer nessa parte, quebra lá" |
| **Open/Closed** | Adicionar feature exige modificar código existente | PRs enormes para mudar qualquer coisa |
| **Liskov Substitution** | Subtipos que quebram o comportamento esperado | Bugs difíceis de rastrear em herança |
| **Interface Segregation** | Dependências desnecessárias entre módulos | Componente A muda por causa de B, sem razão |
| **Dependency Inversion** | Módulos de alto nível dependem de detalhes | Testes unitários impossíveis sem infraestrutura real |

**Anote aqui** — qual princípio do SOLID você acha que sua equipe violou (conscientemente ou não)?

```
Princípio:
Onde:
Consequência observada:
```

---

## 4. Trade-offs arquiteturais: não existe bala de prata

Uma das lições mais importantes do Cap. 7 do Valente (e do Cap. 14 do Garcia) é que **toda decisão arquitetural é um trade-off**. Não existe arquitetura perfeita — existe arquitetura adequada ao contexto.

### O caso dos microsserviços

O Valente (Cap. 7) apresenta microsserviços como uma evolução do monólito — mas o ponto central não é "qual é melhor". É: **quais são os trade-offs de cada um?**

```
MONÓLITO                          MICROSSERVIÇOS
─────────────────────────         ─────────────────────────
✓ Simples de desenvolver          ✓ Escalável horizontalmente
✓ Fácil de testar localmente      ✓ Atualizações independentes
✓ Sem overhead de rede            ✓ Times podem trabalhar em paralelo
✗ Escala o sistema inteiro        ✗ Overhead de comunicação (rede)
✗ Risco de acoplamento alto       ✗ Complexidade de deploy e observabilidade
✗ Mudanças afetam tudo            ✗ Testes de integração mais difíceis
```

**Sua equipe escolheu uma arquitetura no início do semestre.** Ela ainda faz sentido para o que você está construindo? O que você mudaria se pudesse recomeçar?

```
O que faria diferente:


```

---

## 5. Estudo de caso — Trace o impacto

A turma vai analisar coletivamente o seguinte cenário:

> Uma equipe de 4 pessoas decidiu, na Semana 6, que o backend seria um único arquivo `server.js` de ~800 linhas. Acharam que era "mais simples para começar". Na Semana 10, precisaram adicionar autenticação. Mas a lógica de negócio, o acesso ao banco e as rotas estavam misturados. Adicionar autenticação levou 3 dias e gerou 4 bugs novos.

**Questões para discussão:**

1. Qual princípio SOLID foi violado pela arquitetura inicial?
2. Qual atributo de qualidade (tabela da seção 2.1) foi mais impactado?
3. O que a equipe poderia ter feito na Semana 6 para evitar esse custo na Semana 10?
4. Como isso se relaciona com a ideia de "dívida técnica" discutida na Semana 10?

```
Suas anotações do debate:




```

---

## 6. Conectando ao seu projeto

Use este espaço para mapear as decisões arquiteturais do seu projeto e seus impactos observados até agora:

| Decisão tomada (quando) | Atributo afetado | Impacto observado | Avaliação: boa decisão? |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

---

## 7. Questões estruturantes para reflexão

Selecione **uma** das questões abaixo para o debate da aula:

> **Questão A:** _"Como os princípios arquiteturais que estudamos (SOLID, separação de responsabilidades, desacoplamento) poderiam ter mudado uma decisão concreta que sua equipe tomou nos últimos três meses?"_

> **Questão B:** _"Em que momento uma 'boa decisão de arquitetura' se torna uma 'má decisão de arquitetura' — e quem é responsável por identificar essa transição?"_

Anote sua perspectiva antes da discussão:

```
Sua resposta inicial:



```

---

## 8. Para a próxima aula (Terça-feira)

📖 **Leitura prévia:** Nenhuma — amanhã é uma aula predominantemente prática.

**Traga para a terça:**
- Acesso ao repositório do projeto (VS Code aberto e pronto)
- Um bug ou comportamento inesperado que sua equipe não conseguiu explicar nos últimos dias
- Notebook com o projeto rodando localmente

A terça é sobre debugging real — e o melhor caso para debugar é o seu próprio.

---

## Espaço para anotações da aula

```
[Use este espaço livremente durante a aula]




```

---

_CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1_
_Referências: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2026. Cap. 14, seções 14.7–14.8._
_Valente, M. T. Engenharia de Software Moderna. Independente, 2022. Cap. 5 e Cap. 7._
