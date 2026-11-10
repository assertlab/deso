# Semana 14 — Containerização + Entrega formal

**CIN0136: Desenvolvimento de Software | CIn-UFPE**

---

## Por que esta semana importa

O Sprint 4 encerrou na quinta da Semana 13: o MVP foi estabilizado, a retrospectiva foi feita, e o produto está pronto para ir ao mundo. A Semana 14 opera em dois planos ao mesmo tempo.

No plano do **projeto**, é a semana da entrega formal ao stakeholder real — a culminação de quatro sprints de trabalho. O produto sai do repositório e passa para as mãos de quem vai usá-lo. Isso é irreversível, e é exatamente o que deve ser.

No plano da **formação profissional**, é a semana em que a disciplina olha além do semestre. O projeto está entregue — não há mais sprint, não há mais prazo de entrega. Esse espaço é usado para cobrir uma competência fundamental que nenhuma plataforma de deploy abstrai completamente: **containerização com Docker**. Todo desenvolvedor que entra no mercado hoje encontra Docker no onboarding, nos pipelines de CI/CD, nas configurações de ambiente. Saber o que acontece por baixo dos panos transforma quem usa ferramentas em quem entende sistemas.

---

## Aulas desta semana

| Dia | Horário | Sala | Tema | Materiais |
|-----|---------|------|------|-----------|
| 🔵 Segunda | 18:50–20:30 | E132 | Do código ao container: introdução ao Docker | [Material do Aluno](./semana_14-seg-material-aluno.md) · [Slides](./CIN0136-DESO-W14L41-Do-Código-ao-Container.pdf) · Guia do Professor |
| 🟢 Terça | 17:00–18:40 | E132 | Orquestrando serviços com Docker Compose (e onde entra o Kubernetes) | [Material do Aluno](./semana_14-ter-material-aluno.md) · [Slides](./CIN0136-DESO-W14L42-Orquestrando-Serviços-com-Docker-Compose.pdf) · Guia do Professor |
| 🟠 Quinta | 17:00–20:30 | Grad04 | Entrega formal ao stakeholder + Coleta de feedback real | — |

---

## Leituras prévias por dia

### 🔵 Segunda-feira

Nenhuma. Venha com o **repositório do projeto acessível**.

### 🟢 Terça-feira

Nenhuma. Revise mentalmente os conceitos de Docker da aula de segunda — em especial o `nginx.conf` do frontend.

### 🟠 Quinta-feira

Nenhuma. Prepare a demo e os artefatos de entrega da equipe.

---

## Objetivos da semana

Ao final desta semana, você deve ser capaz de:

1. Explicar o problema de paridade de ambiente que Docker resolve, com exemplos da própria experiência no semestre
2. Descrever um container como processo isolado que compartilha o kernel do host, e distingui-lo de uma máquina virtual
3. Distinguir imagem de container com precisão conceitual
4. Ler, interpretar e escrever um `Dockerfile` para aplicações Node.js e React
5. Entender e utilizar `docker-compose.yml` para subir um sistema com frontend, backend e banco de dados
6. Compreender como o nome de serviço funciona como hostname na rede interna do Compose
7. Conectar os conceitos de containerização com o que plataformas como Railway e Render fazem por baixo dos panos
8. Distinguir Docker, Docker Compose e Kubernetes, e argumentar quando um orquestrador vale o custo
9. Realizar a entrega formal do produto ao stakeholder com clareza e profissionalismo

---

## Entregáveis com prazo

| Entregável | Descrição | Prazo |
|------------|-----------|-------|
| **Produto entregue ao stakeholder** | Repositório + deploy + documentação | Quinta, durante a aula |
| **Feedback formal do stakeholder** | Formulário preenchido pela equipe com o stakeholder | Quinta, durante a aula |
| **Material de preparação para apresentação acadêmica** | Insumos da equipe para a Semana 15 | Quinta, ao final da aula |

> **Nota:** Não há entregável técnico associado às aulas de Docker (segunda e terça). O conteúdo é formativo — faz parte da sua bagagem profissional, não do Sprint 4.

---

## Recursos relevantes

### Docker e Kubernetes — documentação e referências

- 📄 [Docker — Get Started](https://docs.docker.com/get-started/) — guia oficial de introdução
- 📄 [Dockerfile reference](https://docs.docker.com/reference/dockerfile/) — referência completa das instruções
- 📄 [Docker Compose — Getting Started](https://docs.docker.com/compose/gettingstarted/) — guia oficial do Compose
- 📄 [Best practices for writing Dockerfiles](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/) — incluindo a estratégia de cache de camadas
- 📄 [Node.js — calendário de versões](https://nodejs.org/en/about/previous-releases) — qual versão usar no `FROM` (use uma LTS com suporte ativo)
- 📄 [Kubernetes — Overview](https://kubernetes.io/docs/concepts/overview/) — para quem quiser ir além (fora da avaliação)
- 📄 [Kompose](https://kompose.io) — converte um `docker-compose.yml` em manifestos Kubernetes (fora da avaliação)

### Referências bibliográficas da disciplina

Os livros-texto não têm um capítulo sobre Docker — a documentação oficial é a fonte primária deste conteúdo. Mas o tema aparece em pontos que vale conectar:

- Garcia, V. C. *Engenharia de Software em Dimensões*. ASSERT Lab, 2025. **Cap. 10, seção 10.3.2** (container scanning no pipeline de CI/CD) e **Cap. 14, seção 14.5.2** (plataformas de orquestração de contêineres)
- Valente, M. T. *Engenharia de Software Moderna*. **Cap. 10, seção 10.4** (Deployment Contínuo) — o contexto de entrega automatizada em que containers se inserem

### Ferramentas

- **Docker Desktop** (Windows/macOS) ou **Docker Engine** (Linux)
- **Podman** — alternativa compatível: os mesmos comandos, trocando `docker` por `podman`

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

*CIN0136 — Desenvolvimento de Software | CIn-UFPE | Sprint 4*
