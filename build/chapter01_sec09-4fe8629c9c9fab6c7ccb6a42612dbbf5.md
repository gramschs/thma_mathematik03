# Determinanten

In den vorangegangenen Kapiteln haben wir Matrizen kennengelernt, die eine
besondere Struktur haben. In diesem Kapitel geht es um eine Eigenschaft von
quadratischen Matrizen, die durch eine Zahl gemessen wird und nützliche
Anwendungen hat, die sogenannte Determinante.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie können die **Determinante** einer $2\times 2$-Matrix berechnen.
* Sie können die Determinante einer $3\times 3$-Matrix berechnen, indem Sie die
  **Regel von Sarrus** anwenden.
```

## Determinante von $2\times 2$-Matrizen

Die Determinante gibt es nur für quadratische Matrizen. Für eine $2\times
2$-Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} a & b \\ c & d \end{pmatrix}
\end{equation*}

wird die Determinante durch den Ausdruck $a\cdot d - c\cdot b$ berechnet.Die
Determinante ordnet jeder quadratischen Matrix eine reelle Zahl zu. Diese
Eigenschaft ist also eine Funktion und wird in der Regel mit $\det$ abgekürzt.
Es gilt also

\begin{equation*}
\det(\mathbf{A}) = a\cdot d - c\cdot b.
\end{equation*}

Manchmal werden auch zwei senkrechte Striche genommen, die die Matrixklammern
ersetzen, um die Determinante einer Matrix zu kennzeichnen:

\begin{equation*}
\left|\begin{matrix} a & b \\ c & d \end{matrix}\right|
= a\cdot d - c\cdot b.
\end{equation*}

In diesem Skript verwendet wir die Funktionsschreibweise $\det()$.

Hinweis: Diesen Ausdruck haben wir bereits kennengelernt. Es ist der gleiche
Ausdruck, den wir verwendet haben, um zu testen, ob eine $2\times 2$-Matrix
invertierbar ist.

Wir betrachten ein Beispiel:

\begin{equation*}
\det\begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix} =
\left|\begin{matrix} 2 & 3 \\ 1 & 5 \end{matrix}\right| =
2\cdot 5 - 1\cdot 3 = 7.
\end{equation*}

## Determinante von $3\times 3$-Matrizen

Nun betrachten wir $3\times 3$-Matrizen. Eine solche Matrix hat im Allgemeinen
die Form

\begin{equation*}
\mathbf{A} =
\begin{pmatrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}\\
\end{pmatrix}.
\end{equation*}

Die Determinante der Matrix wird mit der **Regel von Sarrus** berechnet:

\begin{equation*}
\det(\mathbf{A}) =
a_{11} a_{22} a_{33} + a_{12} a_{23} a_{31} + a_{13} a_{21} a_{32} -
a_{13} a_{22} a_{31} - a_{11} a_{23} a_{32} - a_{12} a_{21} a_{33}.
\end{equation*}

Es ist schwieirg, sich die Reihenfolge der Summanden zu merken. Daher gibt es
eine Eselsbrücke, die visuell veranschaulicht, welches Element in welcher
Reihenfolge multipliziert und summiert werden muss.

```{figure} pics/sarrus_rule.svg
---
class: responsive-figure-50
name: sarrus_rule
---
Eselsbrücke für die Regel von Sarrus
(Quelle: [Kmhkmh](https://commons.wikimedia.org/w/index.php?curid=127614131);
Lizenz: CC BY 4.0)
```

## Zusammenfassung und Ausblick

TODO
