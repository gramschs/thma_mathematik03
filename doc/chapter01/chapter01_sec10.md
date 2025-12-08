# Determinanten

In den vorangegangenen Kapiteln haben wir Matrizen kennengelernt, die eine
besondere Struktur haben. In diesem Kapitel geht es um eine Eigenschaft von
quadratischen Matrizen, die durch eine Zahl gemessen wird und nützliche
Anwendungen hat, die sogenannte Determinante.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie können die **Determinante** einer $2\times 2$-Matrix berechnen.
* Sie können die Determinante einer $n\times n$-Matrix mit $n>2$ berechnen,
  indem Sie den **Laplaceschen Entwicklungssatz** anwenden.
```

## Determinante von $2\times 2$-Matrizen

Die Determinante gibt es nur für quadratische Matrizen. Für eine $2\times
2$-Matrix

$$\mathbf{A} = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$$

wird die Determinante durch den Ausdruck $a\cdot d - c\cdot b$ berechnet.Die
Determinante ordnet jeder quadratischen Matrix eine reelle Zahl zu. Diese
Eigenschaft ist also eine Funktion und wird in der Regel mit $\det$ abgekürzt.
Es gilt also

$$\det(\mathbf{A}) = a\cdot d - c\cdot b.$$

Manchmal werden auch zwei senkrechte Striche genommen, die die Matrixklammern
ersetzen, um die Determinante einer Matrix zu kennzeichnen:

$$\left|\begin{matrix} a & b \\ c & d \end{matrix}\right|
= a\cdot d - c\cdot b.$$

Wir betrachten ein Beispiel:

$$\det\begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix} =
\left|\begin{matrix} 2 & 3 \\ 1 & 5 \end{matrix}\right| =
2\cdot 5 - 1\cdot 3 = 7.$$

## Determinante von $3\times 3$-Matrizen

TODO: Sarrus
