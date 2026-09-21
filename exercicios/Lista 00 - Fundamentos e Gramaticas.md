# Lista 00 — Fundamentos e Gramáticas (Seção 0 + Aula 1)

Faça no papel ou aqui mesmo, embaixo de cada questão. O gabarito está em
`Lista 00 - GABARITO.md` — só abra depois de tentar.

---

## Parte A — Vocabulário (alfabeto, palavra, linguagem)

**A1.** Dado o alfabeto V = {0, 1}, diga se cada item abaixo é uma **palavra sobre V** (sim/não):

a) `0110`
b) `ε`
c) `102`
d) `1`

**A2.** Qual é o tamanho (quantidade de símbolos) de cada palavra?

a) `abba`
b) `ε`
c) `b`

**A3.** Dado V = {a, b}, escreva as **6 primeiras** palavras de V* em ordem de tamanho.

**A4.** Qual é a única diferença entre V* e V+?

**A5.** Uma linguagem pode ser infinita? E um alfabeto? Justifique em uma frase.

---

## Parte B — Notação de potência e moldes

**B1.** Escreva a palavra correspondente:

a) `a⁴`
b) `a⁰`
c) `ab³`
d) `(ab)³`
e) `a²b²`

**B2.** Liste as **4 primeiras** palavras (da menor para a maior) de cada linguagem:

a) `{aⁿb | n ≥ 0}`
b) `{aⁿb | n ≥ 1}`
c) `{abⁿ | n ≥ 0}`
d) `{aⁿbⁿ | n ≥ 0}`
e) `{(ab)ⁿ | n ≥ 1}`

**B3.** Para cada linguagem abaixo, diga com que símbolo(s) uma palavra **pode começar**:

a) `{aⁿb | n ≥ 1}`
b) `{aⁿb | n ≥ 0}`
c) `{bⁿa | n ≥ 0}`

**B4.** Escreva o molde (com a condição!) de cada linguagem descrita em português:

a) "Um `c`, seguido de zero ou mais `d`."
b) "Um ou mais `x`, seguidos de um único `y`."
c) "Mesma quantidade de `0` e `1`, todos os `0` antes dos `1`, pelo menos um de cada."
d) "Começa com `a`, termina com `a`, e no meio tem qualquer quantidade de `b` (inclusive nenhum)."

**B5.** As palavras `ab`, `aabb`, `aaabbb` pertencem a `{aⁿbᵐ | n, m ≥ 0}`? E `abab`? Justifique.

---

## Parte C — Os 4 componentes de uma gramática

Considere a gramática:

```
G = ({S, A}, {x, y}, P, S)
P = { S → xA,  A → xA,  A → y }
```

**C1.** Quais são os **não-terminais**? Quais são os **terminais**? Qual é o **símbolo inicial**?

**C2.** Quantas **produções** existem em P?

**C3.** Reescreva P usando a barra `|` para agrupar as regras de A.

**C4.** Quais regras servem para "continuar" (repetir) e qual serve para "parar"? Por quê?

**C5.** A cadeia `xxA` é uma **sentença** ou uma **forma sentencial**? E `xxy`?

---

## Parte D — Derivação

Use a mesma gramática da Parte C.

**D1.** Derive a palavra `xy` passo a passo, escrevendo qual regra usou em cada passo.

**D2.** Derive a palavra `xxxy`.

**D3.** É possível derivar a palavra `y`? E `xyx`? Explique.

**D4.** Descreva L(G) usando um molde com condição.

**D5.** Agora considere outra gramática:

```
S → aSb | ab
```

Derive `aabb` e `aaabbb`. Depois escreva L(G) como molde.

---

## Parte E — Hierarquia de Chomsky

Classifique cada gramática no tipo **mais restrito** possível (3, 2, 1 ou 0) e diga qual regra impediu de ser mais restrita ainda.

**E1.**
```
S → aS | b
```

**E2.**
```
S → aSb | ab
```

**E3.**
```
S → AB
A → a
B → b
```

**E4.**
```
S → aBC
CB → BC
B → b
C → c
```

**E5.**
```
S → ABC
AB → a
C → c
```

**E6.** Verdadeiro ou falso: "toda gramática regular também é livre de contexto". Justifique.

**E7.** Verdadeiro ou falso: "a regra `S → ab` é permitida numa gramática regular". Justifique olhando os formatos permitidos (A → aB, A → a, A → ε).

---

## Parte F — Construindo gramáticas (desafio)

**F1.** Escreva uma gramática regular para `{aⁿ | n ≥ 1}` (uma ou mais letras `a`).

**F2.** Escreva uma gramática regular para `{aⁿbc | n ≥ 0}`.

**F3.** Escreva uma gramática (do tipo que precisar) para `{aⁿbⁿ | n ≥ 1}`. Ela pode ser regular? Por quê?
