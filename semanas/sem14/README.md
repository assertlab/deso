# Semana 14 — Containerização + Entrega formal

**CIN0136: Desenvolvimento de Software | CIn-UFPE | 2026.1**
📅 15–18 de junho de 2026

---

## Por que esta semana importa

O Sprint 4 encerrou na quinta da Semana 13: o MVP foi estabilizado, a retrospectiva foi feita, e o produto está pronto para ir ao mundo. A Semana 14 opera em dois planos ao mesmo tempo.

No plano do **projeto**, é a semana da entrega formal ao stakeholder real — a culminação de quatro sprints de trabalho. O produto sai do repositório e passa para as mãos de quem vai usá-lo. Isso é irreversível, e é exatamente o que deve ser.

No plano da **formação profissional**, é a semana em que a disciplina olha além do semestre. O projeto está entregue — não há mais sprint, não há mais prazo de entrega. Esse espaço é usado para cobrir uma competência fundamental que nenhuma plataforma de deploy abstrai completamente: **containerização com Docker**. Todo desenvolvedor que entra no mercado hoje encontra Docker no onboarding, nos pipelines de CI/CD, nas configurações de ambiente. Saber o que acontece por baixo dos panos transforma quem usa ferramentas em quem entende sistemas.

---

## Aulas da semana

| Data | Tipo | Tema | Leitura prévia | Materiais |
|---|---|---|---|---|
| Seg 15/06 | 📘 Teórica | Do código ao container: introdução ao Docker | — | [Material do aluno](semana_14-seg-material-aluno.md) · [Guia do professor](semana_14-seg-material-professor.md) |
| Ter 16/06 | 📘 Teórica | Orquestrando serviços com Docker Compose | — | [Material do aluno](semana_14-ter-material-aluno.md) · [Guia do professor](semana_14-ter-material-professor.md) |
| Qui 18/06 | 🟠 Lab/Entrega | Entrega formal ao stakeholder + Coleta de feedback real | — | — |

---

## Leituras prévias por dia

| Dia | Leitura |
|---|---|
| Segunda 15/06 | Nenhuma. Venha com o repositório do projeto acessível. |
| Terça 16/06 | Nenhuma. Revise mentalmente os conceitos de Docker da aula de segunda. |
| Quinta 18/06 | Nenhuma. Prepare a demo e os artefatos de entrega da equipe. |

---

## Objetivos da semana

Ao final desta semana, o aluno será capaz de:

1. Explicar o problema de paridade de ambiente que Docker resolve, com exemplos da própria experiência no semestre
2. Distinguir imagem de container com precisão conceitual
3. Ler, interpretar e escrever um `Dockerfile` para aplicações Node.js e React
4. Entender e utilizar `docker-compose.yml` para orquestrar um sistema com frontend, backend e banco de dados
5. Compreender como o nome de serviço funciona como hostname na rede interna do Compose
6. Conectar os conceitos de containerização com o que plataformas como Railway e Render fazem por baixo dos panos
7. Realizar a entrega formal do produto ao stakeholder com clareza e profissionalismo

---

## Entregáveis e prazos

| Entregável | Prazo | Responsável |
|---|---|---|
| Produto entregue ao stakeholder (repositório + deploy + documentação) | Qui 18/06 durante a aula | Equipe |
| Feedback formal do stakeholder preenchido | Qui 18/06 durante a aula | Equipe + stakeholder |
| Material de preparação para apresentação acadêmica | Qui 18/06 ao final da aula | Equipe |

> **Nota:** Não há entregável técnico associado às aulas de Docker (segunda e terça). O conteúdo é formativo — faz parte da sua bagagem profissional, não do Sprint 4.

---

## Recursos relevantes

### Docker — documentação e referências

- 📄 [Docker — Get Started](https://docs.docker.com/get-started/) — guia oficial de introdução
- 📄 [Dockerfile reference](https://docs.docker.com/reference/dockerfile/) — referência completa das instruções
- 📄 [Docker Compose — Getting Started](https://docs.docker.com/compose/gettingstarted/) — guia oficial do Compose
- 📄 [Best practices for writing Dockerfiles](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/) — incluindo a estratégia de cache de camadas

### Artefatos desta semana

- 📋 [Outline de slides — segunda (Docker)](semana_14-seg-outline-slides.md)
- 📋 [Outline de slides — terça (Docker Compose)](semana_14-ter-outline-slides.md)

### Referências bibliográficas da disciplina

Os livros-texto da disciplina (Garcia e Valente) não cobrem Docker diretamente — o tema pertence ao domínio de infraestrutura e DevOps, que amadureceu depois das edições de referência. A documentação oficial do Docker é a fonte primária para este conteúdo.

---

## Conexão com o semestre

```
Sprint 0        Sprint 1        Sprint 2        Sprint 3        Sprint 4
(Sem 1–3)       (Sem 4–5)       (Sem 6–8)       (Sem 9–11)      (Sem 12–14)
Descoberta      Fundamentos     Construção      Qualidade       Consolidação
                                                                     ↑
                                                             [Você está aqui]
                                                          Entrega formal + Docker
```

O Sprint 4 cobre as Semanas 12, 13 e 14. A Semana 12 foi de code review cruzado e documentação; a Semana 13 foi de estabilização final e Prova 2; esta semana fecha o arco com a entrega ao stakeholder na quinta. As aulas de segunda e terça aproveitam o espaço pós-sprint para formação profissional — um conteúdo que não caberia em nenhuma semana anterior sem competir com as entregas de sprint.

A Semana 15 traz as apresentações acadêmicas, onde cada equipe conta a história completa do seu semestre. O que foi construído, como foi construído, e o que foi aprendido — Docker incluído.

---

*CIN0136 — Desenvolvimento de Software | CIn-UFPE | 2026.1*
