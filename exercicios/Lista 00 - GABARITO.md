# Lista 00 — GABARITO

Só abra depois de tentar. Se errou, volte à seção correspondente do guia.

---

## Parte A

**A1.** a) sim b) sim (a palavra vazia é palavra sobre qualquer alfabeto) c) **não** (o símbolo 2 não está em V) d) sim

**A2.** a) 4 b) 0 c) 1

**A3.** `ε, a, b, aa, ab, ba` (depois viriam bb, aaa, ...)

**A4.** V* inclui a palavra vazia ε; V+ não inclui.

**A5.** Uma linguagem pode ser infinita (ex.: V* inteiro, ou {aⁿb | n ≥ 0}). Um alfabeto é **sempre finito**, por definição.

---

## Parte B

**B1.** a) `aaaa` b) `ε` c) `abbb` d) `ababab` e) `aabb`

**B2.**
a) `b, ab, aab, aaab`
b) `ab, aab, aaab, aaaab`
c) `a, ab, abb, abbb`
d) `ε, ab, aabb, aaabbb`
e) `ab, abab, ababab, abababab`

**B3.**
a) só com `a` (n ≥ 1 garante pelo menos um a)
b) com `a` (n ≥ 1) ou com `b` (n = 0)
c) com `b` (n ≥ 1) ou com `a` (n = 0)

**B4.**
a) `{cdⁿ | n ≥ 0}`
b) `{xⁿy | n ≥ 1}`
c) `{0ⁿ1ⁿ | n ≥ 1}`
d) `{abⁿa | n ≥ 0}`

**B5.** `ab`, `aabb` e `aaabbb` pertencem (são a's seguidos de b's; n e m podem até ser iguais, só não são obrigados). `abab` **não** pertence, porque tem um `a` depois de um `b` — o molde exige todos os a's antes dos b's.

---

## Parte C

**C1.** Não-terminais: {S, A}. Terminais: {x, y}. Inicial: S.

**C2.** 3 produções.

**C3.**
```
S → xA
A → xA | y
```

**C4.** `S → xA` e `A → xA` continuam (o não-terminal A reaparece à direita). `A → y` para (só terminal à direita, nenhuma maiúscula sobra).

**C5.** `xxA` é **forma sentencial** (ainda tem não-terminal). `xxy` é **sentença** (só terminais).

---

## Parte D

**D1.**
```
S ⇒ xA      (S → xA)
  ⇒ xy      (A → y)
```

**D2.**
```
S ⇒ xA      (S → xA)
  ⇒ xxA     (A → xA)
  ⇒ xxxA    (A → xA)
  ⇒ xxxy    (A → y)
```

**D3.** `y` **não**: a única regra de S é `S → xA`, então toda palavra começa obrigatoriamente com x. `xyx` **não**: depois que A vira y não sobra nenhum não-terminal, então nada pode vir depois do y.

**D4.** L(G) = `{xⁿy | n ≥ 1}`

**D5.**
```
S ⇒ aSb ⇒ aabb                    (S → aSb, depois S → ab)
S ⇒ aSb ⇒ aaSbb ⇒ aaabbb          (S → aSb, S → aSb, S → ab)
```
L(G) = `{aⁿbⁿ | n ≥ 1}`

---

## Parte E

**E1.** **Tipo 3 (regular).** Todas as regras são da forma A → aB ou A → a.

**E2.** **Tipo 2 (livre de contexto).** Um único não-terminal à esquerda, mas `S → aSb` tem terminal depois do não-terminal (e `S → ab` tem dois terminais seguidos), o que não é permitido no tipo 3.

**E3.** **Tipo 2.** `S → AB` tem dois não-terminais à direita, o que quebra o formato do tipo 3. (Note que a linguagem {ab} é regular, mas essa *gramática* específica não está no formato regular.)

**E4.** **Tipo 1 (sensível ao contexto).** `CB → BC` tem dois símbolos à esquerda, então não é tipo 2. Nenhuma regra encolhe a cadeia (|esquerda| ≤ |direita| em todas), então é tipo 1.

**E5.** **Tipo 0 (irrestrita).** `AB → a` tem dois símbolos à esquerda e **encolhe** a cadeia (2 → 1), o que viola o tipo 1.

**E6.** **Verdadeiro.** A hierarquia é inclusiva: toda regra do tipo 3 (A → aB, A → a) tem um único não-terminal à esquerda, então também satisfaz o tipo 2.

**E7.** **Falso.** `ab` são dois terminais seguidos. Os únicos formatos permitidos são um terminal sozinho (`a`), um terminal seguido de **um não-terminal** (`aB`) ou ε. Para gerar `ab` de forma regular seria preciso `S → aB`, `B → b`.

---

## Parte F

**F1.**
```
S → aS | a
```

**F2.**
```
S → aS | bA
A → c
```

**F3.**
```
S → aSb | ab
```
**Não** pode ser regular. Uma gramática regular só "empurra" símbolos para um lado sem lembrar quantos já colocou; para garantir a mesma quantidade de a e b é preciso a regra `S → aSb`, que coloca um a e um b ao mesmo tempo, e isso só é possível com um terminal depois do não-terminal (tipo 2).
