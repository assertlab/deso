# ✏️ Exercícios Escolares

**CIN0136: Desenvolvimento de Software · CIn-UFPE**

---

> Esta pasta reúne os **Exercícios Escolares (EE) já aplicados** na disciplina, sempre acompanhados do respectivo **espelho de correção**. O objetivo é duplo: oferecer aos alunos mais um material de estudo e revisão, e disponibilizar a professores e profissionais um banco de questões comentadas que pode ser reutilizado e adaptado.
>
> Os Exercícios Escolares são as **provas** descritas em [docs/avaliacao.md](../docs/avaliacao.md#3-provas--40-2--20). O EE1 cobre as Semanas 1–7; o EE2, todo o conteúdo do semestre. Não confundir com os Exercícios Individuais (EI1–EI4), que ficam em [`exercicios/`](../exercicios/).

---

## Avaliações publicadas

| Semestre | Avaliação | Data | Escopo | Formato | Prova | Espelho |
|----------|-----------|------|--------|---------|-------|---------|
| 2026.2 | [EE1](2026-2/EE1/) | 13/10/2026 | Semanas 1–7 | Somatório · 10 questões + 1 bônus · 4 tipos (A–D) | [PDF](2026-2/EE1/CIN0136_2026_2_EE1.pdf) | [PDF](2026-2/EE1/CIN0136_2026_2_EE1_Espelho.pdf) |

> Uma avaliação só é publicada aqui **depois** de aplicada e corrigida.

---

## O modelo somatório

Os Exercícios Escolares podem ser objetivos diretos, objetivos no modelo somatório ou mistos (objetivas + dissertativas); ver [docs/avaliacao.md](../docs/avaliacao.md#3-provas--40-2--20). O EE1 de 2026.2 usou o **modelo somatório com nota parcial**:

- Cada questão traz um cenário e de 5 a 7 alternativas.
- Cada alternativa vale uma potência de 2 conforme a sua posição: a 1ª vale 2, a 2ª vale 4, a 3ª vale 8, e assim por diante (2, 4, 8, 16, 32, 64, 128).
- O aluno marca as alternativas que julga verdadeiras e escreve a **soma** dos valores marcados.
- Correção de cada questão (vale 1,0 ponto):
  - marcou **qualquer alternativa falsa** → a questão vale 0,0;
  - marcou **só verdadeiras, mas não todas** → nota proporcional: (corretas marcadas ÷ total de corretas) × 1,0;
  - marcou **todas as corretas e nenhuma falsa** → 1,0.

Como cada soma corresponde a uma única combinação de alternativas, o número escrito identifica exatamente o que foi marcado.

### Por que há "tipos" (A, B, C, D)?

Para turmas grandes, a mesma avaliação é aplicada em quatro tipos paralelos. Eles cobrem os mesmos temas com o mesmo nível de dificuldade, mas diferem em pontos controlados:

| Tipo | O que muda em relação ao A |
|------|----------------------------|
| **A** | Versão base |
| **B** | Reordenação das alternativas (o gabarito numérico muda automaticamente) |
| **C** | Uma alternativa falsa substituída por outra mais sutil + reordenação |
| **D** | Um elemento do cenário é alterado de modo a inverter o valor de verdade de uma ou mais alternativas + reordenação |

O tipo D é o mais instrutivo para estudo: compare-o com o A e observe como **uma única mudança no contexto** torna verdadeira uma afirmação que antes era falsa (ou o contrário). É exatamente esse raciocínio, ler o cenário e não decorar a resposta, que a avaliação procura medir.

---

## Como estudar com este material

1. **Resolva antes de olhar o espelho.** Escolha um tipo, cronometre 2 horas e responda sem consulta, como na prova real.
2. **Corrija pelo espelho.** Para cada alternativa, o espelho indica se é verdadeira ou falsa e **por quê**. Leia as justificativas mesmo das alternativas que você acertou: acertar pelo motivo errado também é um erro.
3. **Resolva outro tipo da mesma questão**, principalmente o D, e veja se o seu raciocínio se sustenta quando o cenário muda.
4. **Leve para o projeto.** Os cenários são análogos fictícios ao projeto de extensão (ONG Raízes Urbanas) e ao estudo de caso PetFood. Pergunte-se onde a mesma decisão aparece no trabalho da sua equipe.

---

## Para professores e profissionais

Fique à vontade para usar, adaptar e redistribuir as questões, nos termos da [licença MIT](../LICENSE) do repositório; agradecemos a citação da fonte. Algumas notas de uso:

- **Distratores plausíveis.** As alternativas falsas são inteiramente falsas (sem "premissa verdadeira + conclusão falsa"), mas costumam invocar princípios reais aplicados fora do seu domínio de validade.
- **Ruído informacional.** Os cenários incluem detalhes irrelevantes de propósito; filtrar o que importa faz parte da competência avaliada. O espelho identifica esses ruídos.
- **Reuso.** Como os gabaritos são públicos, recomenda-se reordenar alternativas ou aplicar a técnica do tipo D (mudar o cenário para inverter uma alternativa) antes de reutilizar uma questão.

---

## Estrutura da pasta

```
exercicios-escolares/
├── README.md                          ← Você está aqui
└── 2026-2/
    └── EE1/
        ├── README.md                  ← Escopo, temas e guia da avaliação
        ├── CIN0136_2026_2_EE1.pdf          ← Prova (tipos A, B, C e D)
        └── CIN0136_2026_2_EE1_Espelho.pdf  ← Espelho de correção comentado
```

---

*CIN0136 — Desenvolvimento de Software · CIn-UFPE*
