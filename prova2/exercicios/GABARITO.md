# Prova 2 — Gabarito das questões de estudo (prints em `prova2/exercicios/`)

## Questão 1 (`image.png`) — Reconhecimento de sentença com tabela preditiva (autômato de pilha)

Sentença: `x[y]=zz`. Tabela: S→X[Y]=Z (x) · X→xJ (x) · Y→yK (y) · Z→zL (z) · J→ε ([), J→X (x) · K→ε (]), K→Y (y) · L→Z (z), L→ε ($).

**Como fazer:** olhe o topo da pilha (último símbolo à direita) e o 1º símbolo da entrada.
- Topo é **não terminal** → procure a célula [topo, entrada] na tabela; a saída é essa produção. Tira o topo e empilha o lado direito **ao contrário** (o 1º símbolo fica no topo). Se for ε, só tira.
- Topo é **terminal igual à entrada** → desempilha e avança a entrada. Saída `-`.
- Topo `$` e entrada `$` → sentença **Reconhecida**. Célula vazia ou terminal diferente → **Não Reconhecida**.

| Pilha | Entrada | Saída |
|---|---|---|
| $S | x[y]=zz$ | S → X[Y]=Z |
| $Z=]Y[X | x[y]=zz$ | X → xJ |
| $Z=]Y[Jx | x[y]=zz$ | - |
| $Z=]Y[J | [y]=zz$ | J → ε |
| $Z=]Y[ | [y]=zz$ | - |
| $Z=]Y | y]=zz$ | Y → yK |
| $Z=]Ky | y]=zz$ | - |
| $Z=]K | ]=zz$ | K → ε |
| $Z=] | ]=zz$ | - |
| $Z= | =zz$ | - |
| $Z | zz$ | Z → zL |
| $Lz | zz$ | - |
| $L | z$ | L → Z |
| $Z | z$ | Z → zL |
| $Lz | z$ | - |
| $L | $ | L → ε |
| $ | $ | - |
| | Sentença | **Reconhecida** |

Opção que sobra (pegadinha): `Z → LL` não existe na tabela.

## Questão 2 (`image copy.png`) — FIRST/FOLLOW + preencher tabela preditiva

G: I → 01A2V · V → 45N7 | ε · A → N6N · N → 4I | 34 (o `I` em `4I` é o não terminal I).

- FIRST(I) = {0} · FIRST(V) = {4, ε} · FIRST(A) = FIRST(N) = {3, 4} · FIRST(N) = {3, 4}
- FOLLOW(I) = {$} ∪ FOLLOW(N) = {$, 2, 6, 7} (I é o último em N → 4I)
- FOLLOW(V) = FOLLOW(I) = {$, 2, 6, 7} · FOLLOW(A) = {2} · FOLLOW(N) = {7, 6} ∪ FOLLOW(A) = {2, 6, 7}

**Como fazer a tabela:** produção A → α vai nas colunas de FIRST(α). Se α = ε (ou α deriva ε), vai nas colunas de FOLLOW(A).

| | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | $ |
|---|---|---|---|---|---|---|---|---|---|
| I | I→01A2V | | | - | - | | | | |
| V | - | - | V→ε | - | V→45N7 | - | V→ε | V→ε | V→ε |
| A | - | | | A→N6N | A→N6N | | | | |
| N | - | | | N→34 | N→4I | | | | |

## Questão 3 (`image copy 2.png`) — Ações de redução na tabela LR (SLR) — **a, b**

**Como fazer:** item completo (ponto no fim) A → α. no estado Ii → `rN` (N = número da produção) na **linha i**, nas colunas do **FOLLOW(A)**. S' → S. → `OK` (aceita) na coluna $.
- a ✔ Y → *FY. é a produção 7, FOLLOW(Y) = {+, $, )} → r7 na linha 1.
- b ✔ S' → S. → OK na coluna $.
- c ✘ não é e1; S' → S. dá aceitação.
- d ✘ pegadinha: o item é F → (.S) (ponto no meio, não está completo) → não tem redução.
- e ✘ troca linha e produção: o certo é r7 na linha 1, não r1 na linha 7.

## Questão 4 (`image copy 3.png`) — Tabela de símbolos — **e. Das ações semânticas**

Aula11 sl.17: "As ações semânticas inseridas no analisador sintático serão responsáveis por inserir os identificadores na Tabela de Símbolos". As ações semânticas (trechos de código ligados às produções) inserem os identificadores e seus atributos (tipo etc.) na tabela de símbolos. CLOSURE e GOTO são da montagem da tabela LR.

## Questão 5 (`image copy 4.png`) — LEX/FLEX — **d, e** (não há slide de Lex; resposta pela teoria padrão do Lex/Flex)

- a ✘ o Lex recebe o arquivo .l/.lex e **gera um programa em C** (lex.yy.c); quem lê o texto e extrai os tokens é o programa gerado, depois de compilado.
- b ✘ `%{ ... %}` é código C copiado sem mudanças (includes, constantes). As ações ficam na seção de regras, entre `%%` e `%%`.
- c ✘ `{numero}` usa a definição regular chamada **numero**; NUM é a constante do token (declarada em `%{ %}`), não uma definição regular.
- d ✔ `%{ %}` serve para declarar constantes/código C copiados sem modificação.
- e ✔ dá para reutilizar definições anteriores: `n_real {digito}.{digito}+`.

## Questão 6 (`image copy 5.png`) — Análise sintática ascendente — **c**

- a ✘ pela definição (Aula09 sl.2): "consiste na construção de uma árvore de derivação... a partir das folhas indo em direção à raiz". Atenção: o sl.3 diz que "na prática, ela nunca é efetivamente construída" — se a frase falar "na prática", é ✔.
- b ✘ partir do símbolo inicial e substituir até gerar a sentença é a descendente (top-down).
- c ✔ Aula09 sl.2: "também chamada de abordagem bottom-up, ou shift-reduce".
- d ✘ top-down é a descendente.
- e ✘ LR canônico é o mais poderoso (Aula09 sl.10), mas "analisadores LR funcionam com um autômato de pilha" (sl.11).

## Questão 7 (`image copy 6.png`) — Coleção canônica / CLOSURE — **c, e**

G: A' → A · A → aAa | B · B → bAb | cc
- **CLOSURE:** para cada item com o ponto antes de um não terminal X, acrescenta todos os itens iniciais de X (X → .γ), repetindo até não entrar nada novo.
- I0 = CLOSURE({A' → .A}) = {A' → .A, A → .aAa, A → .B, B → .bAb, B → .cc}
- a ✘ sempre precisa da CLOSURE, mesmo com a gramática aumentada.
- b ✘ falta A → .aAa.
- c ✔ o primeiro item canônico (I0) é CLOSURE(A' → .A).
- d ✘ GOTO serve para os próximos itens, não para o I0.
- e ✔ CLOSURE(A → .B) = {A → .B, B → .bAb, B → .cc}.

## Questão 8 (`image copy 7.png`) — Tabela LR ao contrário → resultados do GOTO

**Como fazer:** `eN` na coluna de um terminal x da linha i → GOTO(Ii, x) = IN. Número N na coluna de transição de um não terminal X → GOTO(Ii, X) = IN. `rN` (redução) e célula vazia → `-`.

| | a | b | c | $ | A | B |
|---|---|---|---|---|---|---|
| GOTO(I0, ·) | - | I1 | - | - | - | - |
| GOTO(I1, ·) | - | - (r1) | I2 | - | I1 | I2 |
| GOTO(I2, ·) | - | - (r2) | - | I3 | - | - |

## Questão 9 (`image copy 8.png`) — Termos da análise LR

| Conceito | Termo |
|---|---|
| Conjunto de itens canônicos usado para montar a tabela LR | Coleção canônica |
| Recebe um conjunto de itens e acrescenta os itens iniciais dos não terminais que aparecem depois do ponto | Função CLOSURE |
| Ponto depois do último símbolo do lado direito | Item completo |
| Ponto antes do primeiro símbolo do lado direito | Item inicial |
| Recebe itens + símbolo, devolve os itens com o ponto deslocado para depois do símbolo | Função GOTO |
| Conjunto de itens produzido pela aplicação do GOTO | Item canônico |
| Criada ao acrescentar uma produção nova só para o símbolo inicial | Gramática aumentada |
| Produções em diferentes momentos, marcadas pelo ponto "." | Itens de gramática |

## Questão 10 (`image copy 9.png`) — FIRST e FOLLOW (múltipla escolha) — **a**

G: A → i[B]=C · B → n | nB · C → n | i | iC
- FIRST(A) = {i} · FIRST(B) = {n} · FIRST(C) = {n, i}
- FOLLOW(A) = {$} (símbolo inicial) · FOLLOW(B) = {]} (vem antes de `]` em A → i[B]=C; em B → nB só soma o próprio FOLLOW(B)) · FOLLOW(C) = FOLLOW(A) = {$} (último em A → ...=C)
- Pegadinha da c e da d: FOLLOW(B) = {], $}. O $ só entra no FOLLOW do símbolo inicial ou de quem herda o FOLLOW dele.
