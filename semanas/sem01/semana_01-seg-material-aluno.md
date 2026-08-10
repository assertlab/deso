# Semana 1 — Segunda-feira
## O mundo além do código

**CIN0136: Desenvolvimento de Software · CIn-UFPE**

---

## Leitura Prévia

📖 *Engenharia de Software em Dimensões* — Cap. 1, seções 1.1, 1.2 e 1.3

Se você não leu antes de vir, tudo bem — mas leia antes da próxima aula.

---

## Objetivos desta aula

Ao final desta aula, você deve ser capaz de:

- Explicar com suas próprias palavras o que é Engenharia de Software e por que vai além da programação
- Identificar pelo menos dois desafios técnicos e dois desafios organizacionais do desenvolvimento de software
- Entender o que você vai construir neste semestre e com quem

---

## 1. Uma pergunta antes de começar

> *"Qual é a diferença entre programar e desenvolver software?"*

*Anote sua resposta inicial antes da discussão — ela vai ser útil para comparar com o que você vai pensar no final do semestre.*

---

## 2. O que é Engenharia de Software?

Engenharia de Software é uma área multidisciplinar dedicada ao **desenvolvimento, operação, manutenção e evolução** de sistemas de software de alta qualidade.

A definição clássica de Sommerville (2015):

> *"A aplicação de uma abordagem sistemática, disciplinada e quantificável ao desenvolvimento, operação e manutenção de software."*

Repare nas três palavras: **sistemática**, **disciplinada**, **quantificável**. Elas descrevem exatamente o que separa engenharia de software de programação avulsa.

### O engenheiro de software não é "apenas" um programador

A programação é **uma das etapas** da Engenharia de Software — mas não a única. O engenheiro de software está envolvido em:

```
Requisitos → Planejamento → Design → Desenvolvimento → Testes → Implantação → Manutenção
                                                                              ↑
                                                              (e o ciclo recomeça)
```

Enquanto isso, o programador foca principalmente no bloco de Desenvolvimento.

### Por que isso importa para você?

Você vai desenvolver um produto real para uma organização real neste semestre. Programar é necessário — mas não suficiente. Você vai precisar entender o problema do parceiro, comunicar decisões, trabalhar em equipe, garantir que o código de outra pessoa faça sentido, e entregar algo que funcione mesmo quando você não estiver lá.

---

## 3. Desafios Técnicos vs. Organizacionais

A Engenharia de Software enfrenta dois tipos de desafios igualmente importantes.

### Desafios Técnicos

| Desafio | O que significa na prática |
|---------|-----------------------------|
| **Complexidade** | Sistemas modernos têm milhares de componentes interdependentes |
| **Escalabilidade** | O sistema precisa funcionar para 10 usuários E para 10 milhões |
| **Segurança** | Uma vulnerabilidade pode expor dados de usuários reais |
| **Desempenho** | Lentidão é um bug — o usuário abandona em segundos |

### Desafios Organizacionais

| Desafio | O que significa na prática |
|---------|-----------------------------|
| **Trabalho em equipe** | 4 pessoas no mesmo código ao mesmo tempo — o que pode dar errado? |
| **Comunicação** | O que o parceiro pediu e o que você entendeu podem ser coisas diferentes |
| **Alinhamento com objetivos** | Código perfeito que resolve o problema errado não serve para nada |
| **Gestão do tempo** | Funcionalidades sempre parecem maiores depois que você começa |

*Qual dos dois tipos de desafio você acha que vai te dar mais trabalho este semestre? Por quê? Anote antes da discussão.*

---

## 4. Dois exemplos para pensar

### Caso 1 — O script que funcionava

Um estudante de computação escreveu um script em Python que resolvia perfeitamente um problema do seu chefe. O script funcionava. Três meses depois, o chefe queria uma pequena mudança. O estudante tinha ido embora. Ninguém mais conseguia entender o código.

**O que deu errado?** Não foi a programação. Foi a falta de documentação, a ausência de testes, a estrutura impossível de manter. O código funcionava — mas não era *software de qualidade*.

### Caso 2 — O sistema hospitalar

Um sistema hospitalar que gerencia leitos de UTI tem um bug. Ele acontece em 0,01% dos casos — uma chance em 10.000. Num hospital com 500 pacientes por dia, isso é um potencial erro a cada 20 dias.

O programador fez tudo funcionar nos casos normais. O engenheiro de software teria ido além: testes para os casos extremos, revisão de código, análise de falhas, documentação para quem vier depois.

**Qual é a diferença?** Responsabilidade profissional e abordagem sistemática.

---

## 5. O que você vai construir este semestre

Este semestre, você vai trabalhar em equipe para desenvolver um **MVP (Produto Mínimo Viável)** para uma organização parceira real. Isso significa:

- Um **problema real** trazido por alguém de fora da universidade
- **Encontros formais** com o parceiro ao longo do semestre, um em cada fase do projeto
- Desenvolvimento em **sprints**, com entregas incrementais e revisões a cada ciclo
- Um **produto funcional, testado e documentado** ao final

O processo é conduzido em **ciclos ágeis baseados em sprints** — você vai entender melhor como o semestre se organiza na próxima aula.

Os projetos disponíveis e a alocação das equipes estão em → [equipes.md](../../equipes.md)

---

## 6. Questão estruturante para reflexão

> *"Como a Engenharia de Software pode contribuir para criar soluções tecnológicas que equilibrem inovação e confiabilidade, especialmente em um cenário de constante mudança tecnológica?"*

Esta não tem resposta certa. É uma pergunta para carregar com você ao longo do semestre.

---

## 7. Para a próxima aula (Terça-feira)

📖 **Leitura obrigatória:** Cap. 1, seções 1.4 a 1.7

**Traga para a aula:** uma dúvida ou uma discordância do que você leu. Não uma pergunta de confirmação — algo que te fez pensar "espera, mas e se...".

---

*CIN0136 — Desenvolvimento de Software · CIn-UFPE*
*Referência: Garcia, V. C. Engenharia de Software em Dimensões. ASSERT Lab, 2025. Cap. 1.*
