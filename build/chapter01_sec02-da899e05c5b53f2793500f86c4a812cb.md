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
beispielsweise während eines 3x3-Basketballspiels die Pässe eines Spielers zu jedem
anderen Spieler gezählt werden, können wir dazu eine Tabelle mit 3 Zeilen und
3 Spalten benutzen. Spielt beispielsweise Spieler 2 den Ball Spieler 3 zu, dann
erhöhen wir die Anzahl der Pässe in Zeile 2 und Spalte 3. Spielt umgekehrt
Spieler 3 den Ball an Spieler 2, erhöhen wir die Anzahl der Pässe in Zeile 3 und
Spalte 2. Zu Beginn des Spiels ist die Tabelle jedoch komplett mit Nullen
gefüllt.

|   | Spieler 1 | Spieler 2 | Spieler 3 |
|---|---|---|---|
| Spieler 1 | 0 | 0 | 0 |
| Spieler 2 | 0 | 0 | 0 |
| Spieler 3 | 0 | 0 | 0 |

In Kurzschreibweise sieht die dazugehörige Matrix zu Beginn des Basketballspiels
also folgendermaßen aus:

\begin{equation*}
\begin{pmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0 \\
\end{pmatrix}.
\end{equation*}

Um eine Nullmatrix kürzer zu beschreiben, hat sich die folgende Notation
eingebürgert: $\mathbf{0}_{3\times 3}$. Die Null wird fettgedruckt und die
Dimension der Matrix wird tiefgestellt an die fettgedruckte Null geschrieben.
$\mathbf{0}_{3\times 3}$ hat also die Dimension $3\times 3$ oder anders
ausgedrückt ist $\mathbf{0}_{3\times 3}$ eine Matrix mit 3 Zeilen und 3 Spalten,
die komplett mit Nullen gefüllt ist:

$$\mathbf{0}_{3\times 3} =
\begin{pmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0 \\
\end{pmatrix}.$$

Nullmatrizen müssen nicht quadratisch sein. Beispielsweise sieht die Nullmatrix
der Dimension $2\times 4$ so aus

$$\mathbf{0}_{2\times 4} =
\begin{pmatrix}
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0\\
\end{pmatrix}$$

und die Nullmatrix der Dimension $5\times 2$ so:

$$\mathbf{0}_{5\times 2} =
\begin{pmatrix}
0 & 0\\
0 & 0\\
0 & 0\\
0 & 0\\
0 & 0\\
\end{pmatrix}.$$

```{admonition} Was ist ... eine Nullmatrix?
:class: note
Eine Matrix, bei der alle Elemente Null sind, heißt **Nullmatrix**.
```

## Diagonalmatrix und Einheitsmatrix

Im vorherigen Kapitel haben wir den Fachbegriff Hauptdiagonale kennengelernt.
Damit sind die Einträge einer Matrix gemeint, bei denen der Zeilenindex gleich
dem Spaltenindex ist, also $a_{11}$, $a_{22}$, $a_{33}$, und so weiter.

In dem Beispiel mit dem 3x3-Basketballspiel sind die Elemente auf der
Hauptdiagonale immer Null, weil ein Spieler nicht zu sich selbst passen kann.
Nun beobachten wir, wie oft ein Spieler dribbelt, bevor er den Ball zu einem
anderen Spieler passt. Genauer gesagt: Wir zählen, wie oft ein Spieler den Ball
berührt, bevor er ihn weiterpasst. Diese Anzahl sammeln wir in einer einfachen
Tabelle:

| Spieler 1 | Spieler 2 | Spieler 3 |
|--- |--- |---|
| 6 | 7 | 4 |

Mathematisch können wir diese Tabelle als einen Zeilenvektor kodieren:

\begin{equation*}
\vec{b} = \begin{pmatrix} 6 & 7 & 4 \end{pmatrix}.
\end{equation*}

Wir können aber auch bei unserer Matrixstruktur bleiben und die Anzahl der
Ballkontakte folgendermaßen notieren:

\begin{equation*}
\mathbf{B} = \begin{pmatrix}
6 & 0 & 0\\
0 & 7 & 0 \\
0 & 0 & 4\\
\end{pmatrix}.
\end{equation*}

Auf den ersten Blick erscheint diese Schreibweise komplizierter als die einfache
Tabelle oder der Zeilenvektor. Dennoch bietet die Matrix-Darstellung einen
Vorteil. Wir können die Anzahl der Pässe

\begin{equation*}
\mathbf{P} = \begin{pmatrix}
0 & 1 & 3\\
2 & 0 & 0\\
1 & 2 & 0\\
\end{pmatrix}
\end{equation*}

und die Anzahl der Ballkontakte auch gemeinsam in einer Matrix auflisten, wenn
wir vereinbaren, dass die Elemente der Hauptdiagonale bedeuten, dass ein Spieler
zu sich selbst passt, also dribbelt. Dann ist die gemeinsame Matrix

\begin{equation*}
\mathbf{G} = \begin{pmatrix}
6 & 1 & 3\\
2 & 7 & 0\\
1 & 2 & 4\\
\end{pmatrix}.
\end{equation*}

In vielen technischen Anwendungen hat die Hauptdiagonale eine besondere
Bedeutung, beispielsweise bei der Beschreibung von Trägheitsmomenten um die
Hauptachsen eines Körpers. Das führt uns zu dem Begriff Diagonalmatrix.

```{admonition} Was ist ... eine Diagonalmatrix?
:class: note
Eine *quadratische* Matrix, bei der alle Elemente *außerhalb* der Hauptdiagonale
Null sind, wird **Diagonalmatrix** genannt. Die Hauptdiagonale kann beliebige
Werte (auch Null) enthalten.
```

In dem Beispiel

\begin{equation*}
\mathbf{B} = \begin{pmatrix}
-2 & 1 \\
0 & 4 \\
\end{pmatrix}
\end{equation*}

ist das Element $b_{12} = 1$ nicht Null, obwohl es ein Element außerhalb der
Hauptdiagonale ist. Daher ist dieses Beispiel $\mathbf{B}$ keine Diagonalmatrix,
weil bei einer Diagonalmatrix *jeder* Eintrag außerhalb der Hauptdiagonale Null
sein muss.

Da es bei Diagonalmatrizen nur auf die Elemente der Hauptdiagonale ankommt,
können wir eine Diagonalmatrix auch kürzer schreiben und die vielen Nullen
weglassen. Dazu verwenden wir $\text{diag}$, also

\begin{equation*}
\mathbf{A} = \text{diag}(-2,4) = \begin{pmatrix}
-2 & 0 \\
0 & 4 \\
\end{pmatrix}.
\end{equation*}

Ein weiteres Beispiel für eine Diagonalmatrix ist

\begin{equation*}
\mathbf{C} = \text{diag}(0,2) = \begin{pmatrix}
0 & 0 \\
0 & 2 \\
\end{pmatrix}.
\end{equation*}

Es dürfen auch Nullen in der Hauptdiagonale sein.

Eine besondere Diagonalmatrix ist die sogenannte **Einheitsmatrix**. Eine
Einheitsmatrix ist zunächst einmal eine Diagonalmatrix. Damit ist sie also
quadratisch und alle Elemente außerhalb der Hauptdiagonale sind Null. Damit
eine Diagonalmatrix zu einer Einheitsmatrix wird, müssen zusätzlich alle
Elemente auf der Hauptdiagonale gleich der Zahl Eins sein. Oft wird sie mit
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

```{admonition} Was ist ... die Einheitsmatrix?
:class: note
Eine *quadratische* Matrix, bei der alle Elemente *außerhalb* der Hauptdiagonale
Null sind und alle Elemente der Hauptdiagonale Eins sind, wird
**Einheitsmatrix** genannt.
```

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

Wir können auch fordern, dass bei der Dreiecksmatrix die Elemente der
Hauptdiagonale Null sind, wie in dem folgenden Beispiel:

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
der Hauptdiagonale Null sind. Schematisch hat eine obere Dreiecksmatrix die
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
Basketballmatrix mit den Pässen. Ihre praktische Bedeutung zeigt sich jedoch
beim Lösen von linearen Gleichungssystemen, das wir in einem späteren Kapitel
behandeln.

```{admonition} Was ist ... eine Dreiecksmatrix?
:class: note
Eine **obere Dreiecksmatrix** ist eine quadratische Matrix, bei der alle
Einträge unterhalb der Hauptdiagonale Null sind. Eine **untere Dreiecksmatrix**
ist eine quadratische Matrix, bei der alle Einträge oberhalb der Hauptdiagonale
Null sind.
```

Das folgende Video stellt diese speziellen Matrizen noch einmal vor.

```{dropdown} Video "Spezielle Matrizen" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/tSPrqJXubww"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir vier Typen von Matrizen kennengelernt: Nullmatrix,
Diagonalmatrix, Einheitsmatrix und Dreiecksmatrix. Diese unterscheiden sich
durch die Position ihrer Null- und Eins-Einträge. Es gibt noch mehr Matrizen,
die einen besonderen Aufbau haben wie etwa transponierte oder symmetrische
Matrizen. Diese lernen wir in einem späteren Kapitel kennen. Zunächst
beschäftigen wir uns mit der Addition von Matrizen.
