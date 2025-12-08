# Matrizenmultiplikation

Nachdem wir in den vorangegangenen Kapiteln die Addition von Matrizen und die
Multiplikation einer Matrix mit einem Skalar behandelt haben, wenden wir uns nun
der Matrizenmultiplikation zu. Im Gegensatz zu den zuvor genannten Operationen
erfolgt die Matrizenmultiplikation nicht elementweise *nicht elementweise*.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie können zwei Matrizen miteinander multiplizieren.
* Sie wissen, dass die Matrixmultiplikation *nicht kommutativ* ist, d.h. dass im 
  Allgemeinen $\mathbf{A}\cdot\mathbf{B} \textcolor{red}{\neq}
  \mathbf{B}\cdot\mathbf{A}$ gilt.
* Sie können die Rechenregeln der Matrizenmultiplikation anwenden, insbesondere
  * Assoziativgesetz und
  * Distributivgesetz.
```

## Matrix mal Matrix

Anders als man vielleicht erwarten würde, erfolgt die Matrizenmultiplikation
nicht elementweise. Daher müssen die Matrizen auch nicht die gleiche Dimension
haben. Stattdessen muss die Anzahl der Spalten der ersten Matrix mit der Anzahl
der Zeilen der zweiten Matrix übereinstimmen. Das Ergebnis ist dann eine Matrix
mit der Zeilenanzahl der ersten und der Spaltenanzahl der zweiten Matrix. Sie
wird **Produktmatrix** genannt. Hat die erste Matrix $\mathbf{A}$ fünf Zeilen
und drei Spalten und die zweite Matrix $\mathbf{B}$ drei Zeilen und vier
Spalten, dann hat die Produktmatrix $\mathbf{C}$ fünf Zeilen und vier Spalten.
Dieses Prinzip wird in der folgenden Skizze verdeutlicht.

```{figure} pics/matrix_multiplication_qtl1.svg
---
width: 50%
name: matrix_multiplication
---
Anforderungen an Spaltenanzahl der ersten Matrix und Zeilenanzahl der zweiten Matrix,
Quelle: Quartl [Wikimedia Commons]
(https://de.wikipedia.org/wiki/Datei:Matrix_multiplication_qtl1.svg),
Lizenz: [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)
```

Nun kennen wir die Bedingungen, unter denen zwei Matrizen multipliziert werden
dürfen, und wissen, welche Dimension die Produktmatrix hat. Aber wie wird die
Matrizenmultiplikation tatsächlich durchgeführt? Dazu betrachten wir ein
Beispiel. Gegeben seien die beiden Matrizen:

$$\mathbf{A} =
\begin{pmatrix}
1 & 0  \\
2 & -1 \\
3 & 3  \\
4 & 1  \\
\end{pmatrix} \; \text{ und } \;
\mathbf{B} =
\begin{pmatrix}
-1 & 0 & 2 \\
 2 & 3 & 5 \\
\end{pmatrix}.$$

Zunächst überprüfen wir, ob wir die beiden Matrizen multiplizieren dürfen. Da
die Spaltenanzahl der ersten Matrix $\mathbf{A}$ zwei und die Zeilenanzahl der
zweiten Matrix $\mathbf{B}$ ebenfalls zwei ist, dürfen wir das Matrixprodukt
berechnen. Die Produktmatrix wird die Dimension $4\times 3$ haben und die
folgende Form annehmen:

$$\mathbf{C} =
\begin{pmatrix}
c_{11} & c_{12} & c_{13} \\
c_{21} & c_{22} & c_{23} \\
c_{31} & c_{32} & c_{33} \\
c_{41} & c_{42} & c_{43} \\
\end{pmatrix}.$$

Um das Element in der ersten Zeile und ersten Spalte, also $c_{11}$, zu
berechnen, nehmen wir die erste Zeile von $\mathbf{A}$ und die erste Spalte von
$\mathbf{B}$ und bilden das *Skalarprodukt* dieser beiden Vektoren:

$$c_{11} =
\begin{pmatrix} 1 & 0 \end{pmatrix} \cdot \begin{pmatrix} -1 \\ 2 \end{pmatrix} =
1\cdot(-1)+0\cdot 2 = -1.
$$

Dann berechnen wir das Element $c_{12}$, indem wir die erste Zeile von
$\mathbf{A}$ mit der zweiten Spalte von $\mathbf{B}$ elementweise multiplizieren
und aufaddieren:

$$c_{12} =
\begin{pmatrix} 1 & 0 \end{pmatrix} \cdot \begin{pmatrix} 0 \\ 3 \end{pmatrix} =
1\cdot 0 + 0\cdot 3 = 0.
$$

Das Element $c_{13}$ berechnen wir analog aus dem Skalarprodukt der ersten Zeile
von $\mathbf{A}$ mit der dritten Spalte von $\mathbf{B}$:

$$c_{13} =
\begin{pmatrix} 1 & 0 \end{pmatrix} \cdot \begin{pmatrix} 2 \\ 5 \end{pmatrix} =
1\cdot 2 + 0\cdot 5 = 2.
$$

Damit haben wir die ersten drei Elemente der Produktmatrix $\mathbf{C}$
berechnet:

$$\mathbf{C} =
\begin{pmatrix}
-1 & 0 & 2 \\
c_{21} & c_{22} & c_{23} \\
c_{31} & c_{32} & c_{33} \\
c_{41} & c_{42} & c_{43} \\
\end{pmatrix}.$$

Um die zweite Zeile der Produktmatrix zu berechnen, berechnen wir das
Skalarprodukt der zweiten Zeile von $\mathbf{A}$ mit der ersten, zweiten und
dritten Spalte von $\mathbf{B}$:

\begin{align*}
c_{21} &=
\begin{pmatrix} 2 & -1 \end{pmatrix} \cdot \begin{pmatrix} -1 \\ 2 \end{pmatrix} =
2\cdot (-1) + (-1)\cdot 2 = -4, \\
c_{22} &=
\begin{pmatrix} 2 & -1 \end{pmatrix} \cdot \begin{pmatrix} 0 \\ 3 \end{pmatrix} =
2\cdot 0 + (-1)\cdot 3 = -3, \\
c_{23} &=
\begin{pmatrix} 2 & -1 \end{pmatrix} \cdot \begin{pmatrix} 2 \\ 5 \end{pmatrix} =
2\cdot 2 + (-1)\cdot 5 = -1. \\
\end{align*}

Damit haben wir die Hälfte der Elemente von $\mathbf{C}$ berechnet:

$$\mathbf{C} =
\begin{pmatrix}
-1 & 0 & 2 \\
-4 & -3 & -1 \\
c_{31} & c_{32} & c_{33} \\
c_{41} & c_{42} & c_{43} \\
\end{pmatrix}.$$

Für die dritte Zeile von $\mathbf{C}$ berechnen wir die Skalarprodukte der
dritten Zeile von $\mathbf{A}$ mit der ersten, zweiten und dritten Spalte von
$\mathbf{B}$. Und zuletzt berechnen wir noch die vierte Zeile von $\mathbf{C}$
auf die gleiche Weise. Insgesamt erhalten wir

$$\mathbf{A}\cdot\mathbf{B} =
\begin{pmatrix}
1 & 0  \\
2 & -1 \\
3 & 3  \\
4 & 1  \\
\end{pmatrix} \cdot
\begin{pmatrix}
-1 & 0 & 2 \\
 2 & 3 & 5 \\
\end{pmatrix} =
\begin{pmatrix}
-1 & 0 & 2 \\
-4 & -3 & -1 \\
 3 & 9 & 21 \\
-2 & 3 & 13 \\
\end{pmatrix}.
$$

Um den Überblick bei der Matrizenmultiplikation zu behalten, kann das sogenannte
**Falk-Schema** genutzt werden. Es hilft, die einzelnen Skalarprodukte
übersichtlich zu organisieren und ist besonders in der Zwischenrechnung
nützlich. Wichtig ist jedoch, dass das endgültige Ergebnis, die Produktmatrix,
separat notiert wird und nicht nur die Zahlen im Falk-Schema stehen bleiben.

```{dropdown} Video "Matrizenmultiplikation (Teil 1)" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/69WvslZmW0s"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{dropdown} Video "Matrizenmultiplikation (Teil 2)" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/tdHmtlEgtPg"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{dropdown} Video "Matrix-Multiplikation" von Mathematrick
<iframe width="560" height="315" src="https://www.youtube.com/embed/uIykRXQhQtE"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Rechenregeln für die Matrizenmultiplikation

Bei der Vektoraddition und der Skalarmultiplikation haben sich die Rechenregeln
aus der Addition und Multiplikation reeller Zahlen direkt auf die entsprechenden
Matrizenoperationen übertragen, da diese elementweise ausgeführt werden. Das ist
bei der Matrizenmultiplikation nicht der Fall, weshalb das Kommutativgesetz
nicht gilt. Es gibt zwar Ausnahmen, in denen $\mathbf{A}\cdot\mathbf{B} =
\mathbf{B}\cdot\mathbf{A}$ gilt, doch in den meisten Fällen ist das nicht so.

Im obigen Beispiel haben wir berechnet:

$$\mathbf{A}\cdot\mathbf{B} =
\begin{pmatrix}
1 & 0  \\
2 & -1 \\
3 & 3  \\
4 & 1  \\
\end{pmatrix} \cdot
\begin{pmatrix}
-1 & 0 & 2 \\
 2 & 3 & 5 \\
\end{pmatrix} =
\begin{pmatrix}
-1 & 0 & 2 \\
-4 & -3 & -1 \\
 3 & 9 & 21 \\
-2 & 3 & 13 \\
\end{pmatrix}.
$$

Wenn wir jedoch $\mathbf{B}\cdot\mathbf{A}$ berechnen wollen, also

$$\mathbf{B}\cdot\mathbf{A} =
\begin{pmatrix}
-1 & 0 & 2 \\
 2 & 3 & 5 \\
\end{pmatrix} \cdot
\begin{pmatrix}
1 & 0  \\
2 & -1 \\
3 & 3  \\
4 & 1  \\
\end{pmatrix},
$$

wäre das gar nicht möglich, da die Anzahl der Spalten der ersten Matrix drei und
die Anzahl der Zeilen der zweiten Matrix vier ist. Selbst wenn die Dimensionen
der beiden Matrizen passen würden, gilt das Kommutativgesetz meist nicht, wie
das folgende Beispiel zeigt. Es gilt:

$$\mathbf{A}\cdot\mathbf{B} =
\begin{pmatrix} 1 & 2 \\ 3 & 4 \\ \end{pmatrix} \cdot
\begin{pmatrix} 0 & 1 \\ 1 & 0 \\ \end{pmatrix} =
\begin{pmatrix} 2 & 1 \\ 4 & 3 \\ \end{pmatrix},
$$

doch für $\mathbf{B}\cdot\mathbf{A}$ erhalten wir:

$$\mathbf{B}\cdot\mathbf{A} =
\begin{pmatrix} 0 & 1 \\ 1 & 0 \\ \end{pmatrix} \cdot
\begin{pmatrix} 1 & 2 \\ 3 & 4 \\ \end{pmatrix} =
\begin{pmatrix} 3 & 4 \\ 1 & 2 \\ \end{pmatrix}.
$$

Glücklicherweise gelten für die Matrizenmultiplikation das Assoziativgesetz und
das Distributivgesetz, die uns das Rechnen mit Matrizen häufig erleichtern:

\begin{align*}
(\mathbf{A}\cdot\mathbf{B})\cdot\mathbf{C} &= \mathbf{A}\cdot(\mathbf{B}\cdot\mathbf{C}) \\
\mathbf{A}\cdot(\mathbf{B}+\mathbf{C}) &= \mathbf{A}\cdot\mathbf{B} + \mathbf{A}\cdot\mathbf{C} \\
(\mathbf{A}+\mathbf{B})\cdot\mathbf{C} &= \mathbf{A}\cdot\mathbf{C} + \mathbf{B}\cdot\mathbf{C}
\end{align*}

Diese Regeln sind besonders nützlich, wenn es darum geht, komplexere
Matrizenprodukte zu berechnen. In den folgenden Videos wird auf die Rechenregeln
für Matrizen ausführlich eingegangen.

```{dropdown} Video "Rechenregeln Matrizen (Teil 3)" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/4XwlwmIDsPo" 
itle="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{dropdown} Video "Rechenregeln Matrizen (Teil 4)" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/ELENZnzZVgI"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{dropdown} Video "Rechenregeln Matrizen (Teil 5)" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/4-E-gSlQu9A"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir uns mit der Matrizenmultiplikation beschäftigt und
die dazugehörigen Rechenregeln kennengelernt. Wir haben verstanden, dass die
Matrizenmultiplikation nicht elementweise erfolgt und das Kommutativgesetz in
der Regel nicht gilt. Dafür gelten jedoch das Assoziativ- und das
Distributivgesetz, die uns helfen, komplexere Berechnungen zu vereinfachen.

Damit sind die grundlegenden Rechenoperationen für Matrizen abgeschlossen. Im
nächsten Kapitel wenden wir uns besonderen Matrizenarten zu, wie z. B.
transponierten Matrizen, Dreiecksmatrizen und symmetrischen Matrizen.
