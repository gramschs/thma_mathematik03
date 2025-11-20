# Besondere Matrizen

Einige Matrizen haben eine besondere Struktur oder spezielle Zahlenwerte und
werden so häufig in Rechnungen gebraucht, dass besondere Bezeichnungen für diese
Matrizen eingeführt worden sind. In diesem Kapitel geht es um die Nullmatrix, um
die Diagonalmatrix und die Einheitsmatrix sowie die Dreiecksmatrix.

## Lernziele

```{admonition} Lernziele
:class: attention
Sie kennen die besonderen Matrizen
* **Nullmatrix**,
* **Diagonalmatrix**,
* **Einheitsmatrix** und
* **untere Dreiecksmatrix** bzw. **obere Dreiecksmatrix**.
```

## Nullmatrix

Eine Matrix, bei der jeder Eintrag Null ist, kann sehr nützlich sein. Sollen
beispielsweise während eines Fußballspiels die Pässe eines Spielers zu jedem
anderen Spieler gezählt werden, können wir dazu eine Tabelle mit 11 Zeilen und
11 Spalten benutzen. Spielt beispielsweise Spieler 2 den Ball Spieler 3 zu, dann
erhöhen wir die Anzahl der Pässe in Zeile 2 und Spalte 3. Spielt umgekehrt
Spieler 3 den Ball an Spieler 2, erhöhen wir die Anzahl der Pässe in Zeile 3 und
Spalte 2. Zu Beginn des Spiels ist die Tabelle jedoch komplett mit Nullen
gefüllt.

|   | Spieler 1 | Spieler 2 | ... | Spieler 11 |
|---|---|---|---|---|
| **Spieler 1** | 0 | 0 | ... | 0 |
| **Spieler 2** | 0 | 0 | ... | 0 |
| **Spieler 3** | 0 | 0 | ... | 0 |
| $\qquad\vdots$ | ...  | ... | ... | $\vdots$ |
| **Spieler 11** | 0 | 0 | ... | 0 |

In Kurzschreibweise sieht die dazugehörige Matrix zu Beginn des Fußballspiels
also folgendermaßen aus:

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
eingebürgert: $\mathbf{0}_{2\times 3}$. Die Null wird fettgedruckt und die
Dimension der Matrix wird tiefgestellt an die fettgedruckte Null geschrieben.
$\mathbf{0}_{2\times 3}$ hat also die Dimension $2\times 3$ oder anders
ausgedrückt ist $\mathbf{0}_{2\times 3}$ eine Matrix mit 2 Zeilen und 3 Spalten,
die komplett mit Nullen gefüllt ist:

$$\mathbf{0}_{2\times 3} =
\begin{pmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
\end{pmatrix}.$$

Mit dieser Notation wird die obige Fußballmatrix als $\mathbf{0}_{11\times 11}$
notiert.

## Diagonalmatrix und Einheitsmatrix

Im vorherigen Kapitel haben wir den Fachbegriff Hauptdiagonale kennengelernt.
Damit sind die Einträge einer Matrix gemeint, bei denen der Zeilenindex gleich
dem Spaltenindex ist, also $a_{11}$, $a_{22}$, $a_{33}$, und so weiter.

Eine *quadratische* Matrix, bei der alle Elemente *außerhalb* der
Hauptdiagonalen Null sind, wird **Diagonalmatrix** genannt. In dem Beispiel

\begin{equation*}
\mathbf{A} = \begin{pmatrix}
-2 & 0 \\
0 & 4 \\
\end{pmatrix}
\end{equation*}

sind die Elemente $a_{12} = 0$ und $a_{21} = 0$, die außerhalb der
Hauptdiagonalen liegen, Null. Also ist $\mathbf{A}$ eine Diagonalmatrix.

In dem Beispiel

\begin{equation*}
\mathbf{B} = \begin{pmatrix}
-2 & 1 \\
0 & 4 \\
\end{pmatrix}
\end{equation*}

ist das Element $b_{12} = 1$ nicht Null, obwohl es ein Element außerhalb der
Hauptdiagonalen ist. Daher ist dieses Beispiel $\mathbf{B}$ keine
Diagonalmatrix.

Da es bei Diagonalmatrizen nur auf die Elemente der Hauptdiagonalen ankommt,
können wir eine Diagonalmatrix auch kürzer schreiben und die vielen Nullen
weglassen (das spart auch Speicher beim Computer). Dazu verwenden wir
$\text{diag}$, also

\begin{equation*}
\mathbf{A} = \begin{pmatrix}
-2 & 0 \\
0 & 4 \\
\end{pmatrix} =
\text{diag}(-2,4).
\end{equation*}

Ein weiteres Beispiel für eine Diagonalmatrix ist

\begin{equation*}
\mathbf{C} = \text{diag}(0,2) = \begin{pmatrix}
0 & 0 \\
0 & 2 \\
\end{pmatrix}.
\end{equation*}

Es dürfen auch Nullen in der Hauptdiagonalen sein.

Was bedeuten eigentlich die Einträge auf der Hauptdiagonalen unserer
Fußballmatrix? Ein Pass von Spieler 3 an Spieler 3 ergibt auf den ersten Blick
keinen Sinn. Wir können diese Einträge aber nutzen, um zu zählen, wie oft ein
Spieler den Ball bei sich behält und dribbelt, anstatt zu passen. Eine Matrix,
in der nur die Diagonalelemente von Null verschieden sind, würde also ein Spiel
beschreiben, in dem jeder Spieler nur dribbelt und niemand passt, was keine
besonders erfolgreiche Taktik ist! In der Praxis werden die Einträge außerhalb
der Hauptdiagonalen natürlich nicht alle Null sein. Dennoch zeigt dieses
Beispiel, wie die Struktur einer Diagonalmatrix interpretiert werden kann: Die
Diagonalelemente beschreiben, was ein Spieler "mit sich selbst" macht, während
die übrigen Elemente die Interaktionen zwischen verschiedenen Spielern erfassen.

Eine besondere Diagonalmatrix ist die sogenannte **Einheitsmatrix**. Eine
Einheitsmatrix ist zunächst einmal eine Diagonalmatrix. Damit ist sie also
quadratisch und alle Elemente außerhalb der Hauptdiagonalen sind Null. Damit
eine Diagonalmatrix zu einer Einheitsmatrix wird, müssen zusätzlich alle
Elemente auf der Hauptdiagonalen gleich der Zahl Eins sein. Oft wird sie mit
einem großen, fettgedruckten $\mathbf{E}$ oder $\mathbf{I}$ gekennzeichnet. Das
$\mathbf{I}$ kommt von dem englischen Begriff "identity matrix". An den
Variablennamen wird die Anzahl der Zeilen als tiefgestelltes Zeichen
geschrieben. Und da die Matrix quadratisch sein muss, ist dies gleich der Anzahl
der Spalten der Einheitsmatrix. Die Einheitsmatrix der Dimension $2\times 2$ ist

$$
\mathbf{E}_{2} =
\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
\quad \text{ oder } \quad
\mathbf{I}_{2} =
\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
$$

während die Einheitsmatrix der Dimension $4\times 4$ folgendermaßen geschrieben
wird:

$$\mathbf{E}_{4} = \mathbf{I}_{4} =
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end{pmatrix}. $$

## Dreiecksmatrix

Wie Diagonalmatrizen und Einheitsmatrizen sind auch Dreiecksmatrizen
*quadratisch*. Wenn zusätzlich alle Elemente oberhalb der Hauptdiagonale Null
sind, nennen wir eine solche Matrix eine **untere Dreiecksmatrix**.

Ein Beispiel für eine untere Dreiecksmatrix ist die Matrix

$$\mathbf{A} =
\begin{pmatrix}
1 & 0 & 0 & 0 \\
-17.5 & -1 & 0 & 0 \\
3 & \frac{2}{3} & 5 & 0 \\
5 & 0 & \sqrt{2} & \sqrt{5} \\
\end{pmatrix}.$$

Wir können auch fordern, dass die Elemente der Hauptdiagonalen Null sind, wie in
dem folgenden Beispiel:

$$\mathbf{B} =
\begin{pmatrix}
0 & 0 & 0 & 0 \\
-17.5 & 0 & 0 & 0 \\
3 & \frac{2}{3} & 0 & 0 \\
5 & 0 & \sqrt{2} & 0 \\
\end{pmatrix}.$$

Eine solche Matrix nennen wir **strikte untere Dreiecksmatrix** oder **echte
untere Dreiecksmatrix**.

Analog zu diesen Begriffen werden obere Dreiecksmatrizen definiert. Eine **obere
Dreiecksmatrix** ist eine *quadratische* Matrix, bei der alle Elemente unterhalb
der Hauptdiagonalen Null sind. Schematisch hat eine obere Dreiecksmatrix die
Struktur

$$\begin{pmatrix}
* & * & * & * \\
0 & * & * & * \\
0 & 0 & * & * \\
0 & 0 & 0 & * \\
\end{pmatrix}$$

und eine **echte obere Dreiecksmatrix** bzw. **strikte obere Dreiecksmatrix**
hat die Struktur

$$\begin{pmatrix}
0 & * & * & * \\
0 & 0 & * & * \\
0 & 0 & 0 & * \\
0 & 0 & 0 & 0 \\
\end{pmatrix}.$$

Dreiecksmatrizen wirken auf den ersten Blick weniger anschaulich als die
Fußballmatrix mit den Dribblings und den Pässen. Ihre praktische Bedeutung zeigt
sich jedoch beim Lösen von linearen Gleichungssystemen, das wir in einem
späteren Kapitel behandeln.

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
