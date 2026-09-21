# Linguagens Formais e Compiladores — pasta de estudo

Repositório de estudo da disciplina **Linguagens Formais e Compiladores** (Eng. de Computação, UNISC, Prof. Ivan L. Süptitz).
Usado por mais de uma pessoa para estudar com o Claude Code. Responda sempre em **português**.

## Como explicar (preferência de quem estuda aqui)

- Assuma que a pessoa **não sabe nada do conteúdo**: comece do zero, em linguagem simples, e só depois dê a definição formal.
- Sempre mostre **passo a passo com exemplo concreto** (derivação linha a linha, tabela de transição preenchida, etc.).
- Para exercícios, inclua um quadro **"Como fazer"** (o método) antes da resposta, e a resolução completa, não só o gabarito.
- Cite de qual aula/slide vem cada conceito. Os PDFs das aulas estão nesta pasta — leia-os com `pdftotext` (Python não está instalado nas máquinas; `pdftotext` está).

## Escopo da Prova 1 (Aulas 1 a 6)

| Aula | Conteúdo | Arquivo |
|---|---|---|
| 1 | Conceitos básicos, gramáticas, derivação, Hierarquia de Chomsky | `Aula01 - Gramáticas e a Hierarquia de Chomsky.pdf` |
| 2 | Gramáticas Regulares, Expressões Regulares, definições regulares, AFD e AFND | `Aula02 - Gramáticas Regulares Expressões Regulares AFD e AFND (1).pdf` + `Gabarito - Aula02 - ....pdf` |
| 3 | Determinização de AFND; AFND-ε e eliminação de movimentos vazios | `Aula03 - Determinização de AFND e AFND-e.pdf` + `Gabarito Lista 03.pdf` + `cap02 - Aula 3.pdf` (capítulo de apoio, Manacero) |
| 4 | GR → AF, ER → AF (Thompson), minimização de AFD | `Aula04 - Relação entre GR e ER com AF e Minimização de AFD.pdf` + `Gabarito Lista 4.pdf` |
| 5 | Fases da compilação, front-end/back-end, análise léxica, tokens e lexemas | `Aula05 - Fases da Compilação e Análise Léxica.pdf` |
| 6 | GLC, derivações e árvores, as 6 transformações em GLC (símbolos inúteis, ε-livre, produções simples, ambiguidade, recursão à esquerda, fatoração) | `Aula06 - Gramáticas Livres de Contexto.pdf` + `GabaritoAula06.pdf` |

## Materiais prontos (comece por eles)

- `Guia de Estudo - LFC Prova 1 (impressão, 6 pags).pdf` — guia completo das Aulas 1–6 explicado do zero, com passo a passo de cada técnica e as 12 questões do questionário do AVA resolvidas. Versão compacta em 2 colunas para imprimir.
- `Material Prova 1 - LFC.pdf` (13 págs) e `Material Prova 1 - LFC (compacto, 6 pags).pdf` — resumo por aula + 24 exercícios no modelo do questionário do AVA, cada um com "Como fazer" + gabarito resolvido.
- `exercicios/` — listas em Markdown com gabarito separado (`Lista 00 - Fundamentos e Gramaticas.md` / `Lista 00 - GABARITO.md`).
- `duvidas/` — prints de questões do questionário do AVA que geraram dúvida (`image copy N.png`). Ao criar exercícios, imite o formato dessas questões (relacionar colunas, completar, verdadeiro/falso, múltipla escolha).

## Convenções

- Novas listas de exercícios vão em `exercicios/`, sempre com o gabarito em arquivo separado.
- Novos prints de dúvidas vão em `duvidas/`.
- Material para imprimir: HTML com CSS compacto (2 colunas, ~6pt, margens 4,5mm) → PDF via Chrome headless `--print-to-pdf`.
- Não mover nem renomear os PDFs das aulas: os materiais prontos citam esses nomes.
