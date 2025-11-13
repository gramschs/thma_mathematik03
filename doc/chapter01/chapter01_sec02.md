# Besondere Matrizen

Einige Matrizen haben eine besondere Struktur oder spezielle Zahlenwerte und
werden so häufig in Rechnungen gebraucht, dass besondere Bezeichnungen für diese
Matrizen eingeführt worden sind. In diesem Kapitel geht es um die Nullmatrix, um
die Diagonalmatrix und die Einheitsmatrix.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie kennen die besonderen Matrizen 
    * **Nullmatrix**,
    * **Diagonalmatrix** und
    * **Einheitsmatrix**.
```

## Nullmatrix

Eine Matrix, bei der jeder Eintrag Null ist, kann sehr nützlich sein. Sollen
beispielsweise während eines Fußballspiels die Pässe eines Spielers zu jedem
anderen Spieler gezählt werden, dann ist es sinnvoll mit einer Matrix zu
starten, bei der jeder Eintrag Null ist. Sobald ein Spieler zu einem anderen
Spieler gepasst hat, wird an der entsprechenden Position der Wert um Eins
hochgezählt. Aber zu Beginn des Fußballspiels sieht die Matrix folgendermaßen
aus:

\begin{equation*}
\begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
\end{pmatrix}.
\end{equation*}

Um eine Nullmatrix kürzer zu beschreiben, hat sich die folgende Notation
eingebürgert: $\mathbf{0}_{2\times 3}$. Eine fettgedruckte Null mit der
Dimension als Index, also eine Nullmatrix mit zwei Zeilen und drei Spalten.
Damit würde die obige Fußballmatrix als $\mathbf{0}_{11\times 11}$ notiert
werden.

## Diagonalmatrix

Im vorherigen Kapitel haben wir den Fachbegriff Hauptdiagonale kennengelernt.
Damit sind die Einträge einer Matrix gemeint, bei denen die Zeilenposition
gleich der Spaltenposition ist, also $a_{11}$, $a_{22}$, $a_{33}$, und so
weiter. Eine Diagonalmatrix wird über alle anderen Elemente definiert.  

Eine *quadratische* Matrix, bei der alle Elemente außerhalb der Hauptdiagonalen
Null sind, wird **Diagonalmatrix** genannt. In dem Beispiel

\begin{equation*}
\mathbf{A} = \begin{pmatrix} -2 & 0 \\
0 & 4 \\
\end{pmatrix}
\end{equation*}

sind die Elemente $a_{12} = 0$ und $a_{21} = 0$, die nicht auf der
Hauptdiagonalen liegen, Null. Also ist $\mathbf{A}$ eine Diagonalmatrix.

## Einheitsmatrix

Eine besondere Diagonalmatrix ist die sogenannte **Einheitsmatrix**. Eine
Einheitsmatrix ist zunächst einmal eine Diagonalmatrix. Damit ist zie also
quadratisch und alle Elemente außerhalb der Hauptdiagonalen sind Null. Damit
eine Diagonalmatrix zu einer Einheitsmatrix wird, müssen zusätzlich alle
Elemente auf der Hauptdiagonalen gleich der Zahl Eins sein. Oft wird sie mit
einem großen, fettegdrucktem E oder I gekennzeichnet. An den Variablennamen wird
als tiefgestelltes Zeichen die Dimension der Matrix geschrieben. Und da die
Matrix quadratisch sein muss, reicht auch nur die Anzahl der Zeilen, wie die
folgenden Beispiele zeigen. Die Einheitsmatrix der Dimension $2\times 2$ ist

$$\mathbf{E}_{2} = \mathbf{I}_{2} =
\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix},$$

während die Einheitsmatrix der Dimension $4\times 4$ folgendermaßen geschrieben
wird:

$$\mathbf{E}_{4} = \mathbf{I}_{4} =
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end{pmatrix}. $$

Das folgende Video stellt diese speziellen Matrizen noch einmal vor.

```{dropdown} Video "Spezielle Matrizen" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/tSPrqJXubww"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir Matrizen kennengelernt, die einen besonderen Aufbau
haben oder bei denen die Zahlen 0 und 1 an bestimmten Positionen stehen. Es gibt
noch mehr Matrizen, die einen besonderen Aufbau haben wie beispielsweise
transponierte oder symmetrische Matrizen. Diese lernen wir in einem späteren
Kapitel kennen. Zunächst beschäftigen wir uns mit der Addition von Matrizen.
