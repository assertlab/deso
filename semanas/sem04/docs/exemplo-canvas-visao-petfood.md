# Canvas de Visão — PetFood

> **Exemplo de referência** · Entregável do lab de segunda (Semana 4) · Equipe fictícia "Grupo 3"
> Construído com apoio de IA a partir da fala do stakeholder e revisado pela equipe.

---

## Problema

A ONG recebe ração doada e a redistribui para famílias de baixa renda que têm cães e gatos. Hoje todo o controle acontece no WhatsApp e numa planilha, e o fluxo se perde em três pontos: a família alega que não recebeu e ninguém consegue confirmar; os voluntários não sabem quanto há em estoque no depósito; e o doador não tem retorno sobre o destino da ração que doou. O resultado é retrabalho, conflito com as famílias e perda de doadores por falta de transparência.

---

## Personas principais

- **Voluntário (operador):** registra as doações que chegam, acompanha o estoque e organiza as retiradas. É quem mais usa o sistema no dia a dia. Precisa de algo rápido, que funcione no celular e não dependa de garimpar mensagens.
- **Família beneficiária:** recebe a ração em retiradas agendadas. Precisa saber quando e onde retirar, e ter o recebimento registrado para evitar a dúvida do "recebeu ou não recebeu".
- **Doador:** entrega ração à ONG. Precisa de confirmação de que a doação foi registrada e, idealmente, de um retorno de que ela chegou a uma família.
- **Coordenador da ONG (secundária):** enxerga o estoque total e o histórico para tomar decisões e prestar contas. Não opera o dia a dia, mas depende dos dados que o sistema consolida.

---

## Proposta de valor

Substituir o "WhatsApp + planilha" por um registro único e confiável do fluxo de ração, do recebimento à entrega. Diferente do controle atual, o PetFood mantém o estoque sempre atualizado a cada doação e retirada, elimina a dúvida sobre quem recebeu (cada entrega fica registrada) e devolve transparência ao doador. O ganho não é "ter um app": é parar de perder ração no meio do caminho e parar de perder doador por falta de retorno.

---

## Objetivos do produto

- Dar aos voluntários uma visão confiável e em tempo real do estoque, sem conferência manual.
- Acabar com a ambiguidade "a família recebeu?" por meio do registro de cada entrega.
- Aumentar a retenção de doadores oferecendo retorno sobre o destino da doação.
- Reduzir o tempo que o voluntário gasta hoje coordenando tudo por mensagem.

---

## Fronteira do MVP

> Este é o campo que a equipe **decidiu**, não pediu pronto à IA. Cada item tem justificativa.

### DENTRO do MVP

| Item | Por que está dentro |
|------|---------------------|
| Registrar doação que chega (quantidade + doador) | É a entrada do fluxo; sem isso não há estoque nem rastreio. É a dor mais concreta citada pelo stakeholder. |
| Visualizar o estoque atual | Resolve diretamente o "não sabemos quanto tem". Deriva automaticamente dos registros de entrada e saída. |
| Registrar a entrega/retirada por uma família | Mata a ambiguidade "recebeu ou não recebeu", que é a maior fonte de conflito hoje. |
| Autenticação de voluntário | Os registros precisam ter autor; lida com dados de famílias vulneráveis. É pré-condição de confiança nos dados. |

### FORA (por enquanto)

| Item | Por que fica fora AGORA |
|------|--------------------------|
| Agendamento das retiradas pelas famílias | O stakeholder pediu, mas envolve um segundo tipo de usuário (a família) e um fluxo de calendário. Registrar a entrega já resolve o conflito principal; agendar é o próximo passo, não o primeiro. |
| Portal do doador com rastreio "sua ração chegou" | Alto valor de retenção, mas é um terceiro perfil de usuário e depende do fluxo interno já estar sólido. Entra depois que registro e entrega estiverem confiáveis. |
| Relatórios e prestação de contas do coordenador | Útil, mas é consumo de dados que só faz sentido depois que os dados existirem e forem confiáveis. |
| Notificações automáticas (WhatsApp/SMS) | Conveniência, não a dor central. Adiável sem comprometer o valor do MVP. |

> **Raciocínio do recorte:** a menor coisa que já resolve a dor principal da ONG é *registrar o que entra, ver o estoque e registrar o que sai, com autor confiável*. Tudo que envolve um segundo ou terceiro perfil de usuário (família agendando, doador acompanhando) foi empurrado para fora do primeiro ciclo.

---

## Premissas & riscos

- **Premissa:** os voluntários têm smartphone e acesso à internet no depósito. (Se falso, muda tudo — confirmar com o stakeholder.)
- **Premissa:** há um número pequeno e estável de voluntários, que podem ser cadastrados manualmente no início.
- **Risco:** os dados das famílias são sensíveis (situação de vulnerabilidade). Tratamento inadequado é risco real — reforça a necessidade de autenticação já no MVP.
- **Risco:** se o registro for mais trabalhoso que o WhatsApp atual, os voluntários não adotam. Simplicidade é requisito, não enfeite.

---

## Métrica de sucesso

- O estoque exibido no sistema bate com a contagem física do depósito (confiabilidade do dado).
- Zero casos de "não sei se a família recebeu" após a adoção — toda entrega tem registro.
- Voluntários deixam de usar a planilha paralela (sinal de que o sistema substituiu o processo antigo).

---

## Perguntas em aberto (para levar ao stakeholder)

> Lacunas que a elicitação assistida ajudou a revelar. São o insumo mais valioso da conversa de refinamento.

- As famílias precisam de acesso ao sistema no MVP, ou basta o voluntário registrar a entrega por elas?
- Como uma família é identificada na retirada — nome, documento, um cadastro prévio? Há preocupação de privacidade nisso?
- A ração é controlada só por quantidade (kg), ou também por tipo/marca (cão vs. gato, filhote vs. adulto)?
- Quantos voluntários operam hoje? Todos podem registrar, ou há papéis diferentes?
- Existe mais de um ponto de estoque/depósito, ou é um só?

---

_Exemplo produzido para apoiar a condução da aula de terça (Semana 4) · CIN0136 · CIn-UFPE · 2026.1_
_Nota didática: este canvas é o tipo de entregável esperado ao final da segunda. Ele parte da fronteira do MVP definida pela equipe (campo não-terceirizável) e alimenta diretamente a geração de histórias na terça — cada item "DENTRO do MVP" vira uma ou mais histórias de usuário._
