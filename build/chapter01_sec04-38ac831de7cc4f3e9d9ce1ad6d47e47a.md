---
authors:
  - name: Simone Gramsch
---

# 1.4 Matrizenmultiplikation

Nachdem wir in den vorangegangenen Kapiteln die Addition von Matrizen und die
Multiplikation einer Matrix mit einem Skalar kennengelernt haben, kehren wir
noch einmal zu unserer Passmatrix $\mathbf{P}$ zurück. Wir wissen bereits, wie
oft jeder Spieler jeden anderen in den ersten zehn Minuten angespielt hat. Der
Trainer möchte nun aber wissen, wie viele Pässe insgesamt in Richtung Offensive
und wie viele in Richtung Defensive gespielt wurden, je nachdem, welcher
Mannschaftsposition der jeweilige Passempfänger angehört. Diese Frage lässt sich
weder durch Addition noch durch Skalarmultiplikation beantworten. Wir brauchen
eine neue Rechenoperation: die Matrizenmultiplikation.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können zwei Matrizen miteinander multiplizieren.
* [ ] Sie wissen, dass die Matrizenmultiplikation *nicht kommutativ* ist, das
  heißt, dass im Allgemeinen
  \begin{equation*}
  \mathbf{A}\cdot\mathbf{B} \textcolor{red}{\neq} \mathbf{B}\cdot\mathbf{A}
  \end{equation*}
  gilt.
* [ ] Sie kennen das **Assoziativgesetz** der Matrizenmultiplikation.
* [ ] Sie kennen das **Distributivgesetz** der Matrizenmultiplikation.
```

## Wie multiplizieren wir zwei Matrizen?

Wir kodieren die Mannschaftsposition jedes Spielers in einer
**Zuordnungsmatrix** $\mathbf{Z}$ der Dimension $4\times 2$. Spieler 1 und 2
gehören zur Offensive, Spieler 3 und 4 zur Defensive. Jede Zeile von
$\mathbf{Z}$ enthält deshalb eine 1 in der Spalte, die der jeweiligen Position
entspricht, und sonst Nullen:

\begin{equation*}
\mathbf{Z} = \begin{pmatrix} 1 & 0 \\ 1 & 0 \\ 0 & 1 \\ 0 & 1 \end{pmatrix}.
\end{equation*}

Zur Erinnerung, die Summe der Pässe aus den ersten zehn Minuten hatten wir in
Kapitel 1.3 als

\begin{equation*}
\mathbf{P} = \begin{pmatrix}
0 & 14 & 11 & 35 \\
6 & 0 & 12 & 18 \\
24 & 8 & 0 & 5 \\
0 & 7 & 1 & 0 \\
\end{pmatrix}
\end{equation*}

berechnet. Wie viele Pässe hat also Spieler 1 insgesamt an die Offensive
gespielt? Spieler 1 hat 0 Pässe an sich selbst und 14 Pässe an Spieler 2
gespielt, beide gehören zur Offensive. Die Pässe an Spieler 3 und 4 zählen
nicht mit, da diese zur Defensive gehören. Also ergeben sich $0 + 14 = 14$
Pässe an die Offensive. Genau dieses Muster, jeden Eintrag der Zeile mit dem
passenden Eintrag der Spalte von $\mathbf{Z}$ zu multiplizieren und die
Ergebnisse zu summieren, ist die Struktur eines Skalarprodukts zwischen einer
Zeile von $\mathbf{P}$ und einer Spalte von $\mathbf{Z}$.

*Aber wie übertragen wir dieses Prinzip auf eine allgemeine Rechenvorschrift?*

```{admonition} Was ist ... die Matrizenmultiplikation?
:class: note
Für eine Matrix $\mathbf{A}$ der Dimension $m \times n$ und eine Matrix
$\mathbf{B}$ der Dimension $n \times p$ ist das **Matrixprodukt** $\mathbf{C} =
\mathbf{A}\cdot\mathbf{B}$ definiert, wenn die Spaltenanzahl von $\mathbf{A}$
mit der Zeilenanzahl von $\mathbf{B}$ übereinstimmt. Die Produktmatrix
$\mathbf{C}$ hat die Dimension $m \times p$. Ihr Eintrag $c_{ij}$ ergibt sich
als **Skalarprodukt** der $i$-ten Zeile von $\mathbf{A}$ mit der $j$-ten Spalte
von $\mathbf{B}$:

\begin{equation*}
c_{ij} = \sum_{k=1}^{n} a_{ik}\,b_{kj}.
\end{equation*}
```

Die folgende Skizze verdeutlicht die Dimensionsbedingung noch einmal
allgemein.

```{figure} pics/matrix_multiplication_qtl1.svg
---
width: 50%
name: matrix_multiplication
---
Anforderungen an Spaltenanzahl der ersten Matrix und Zeilenanzahl der zweiten Matrix
(Quelle: Quartl [Wikimedia Commons](https://de.wikipedia.org/wiki/Datei:Matrix_multiplication_qtl1.svg),
Lizenz: [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/))
```

Matrizenmultiplikationen dieser Art begegnen uns auch in der Robotik. Bei
einem mehrgelenkigen Roboterarm wird die Gesamtorientierung des Greifers durch
die Multiplikation der Rotationsmatrizen aller Gelenke berechnet, wobei jede
einzelne Matrix genau wie hier über das Matrixprodukt verkettet wird.

Wir wenden die Definition nun vollständig auf unser Beispiel an. Da
$\mathbf{P}$ die Dimension $4\times 4$ und $\mathbf{Z}$ die Dimension
$4\times 2$ hat, stimmt die Spaltenanzahl von $\mathbf{P}$ mit der
Zeilenanzahl von $\mathbf{Z}$ überein, das Produkt $\mathbf{P}\cdot\mathbf{Z}$
ist also definiert und hat die Dimension $4\times 2$.

Für die erste Zeile der Produktmatrix berechnen wir die Skalarprodukte der
ersten Zeile von $\mathbf{P}$ mit der ersten und zweiten Spalte von
$\mathbf{Z}$:

\begin{align*}
c_{11} &= \begin{pmatrix} 0 & 14 & 11 & 35 \end{pmatrix} \cdot
\begin{pmatrix} 1 \\ 1 \\ 0 \\ 0 \end{pmatrix} =
0\cdot 1+14\cdot 1+11\cdot 0+35\cdot 0 = 14, \\
c_{12} &= \begin{pmatrix} 0 & 14 & 11 & 35 \end{pmatrix} \cdot
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 1 \end{pmatrix} =
0\cdot 0+14\cdot 0+11\cdot 1+35\cdot 1 = 46.
\end{align*}

Für die zweite Zeile gehen wir genauso vor, diesmal mit der zweiten Zeile von
$\mathbf{P}$:

\begin{align*}
c_{21} &= \begin{pmatrix} 6 & 0 & 12 & 18 \end{pmatrix} \cdot
\begin{pmatrix} 1 \\ 1 \\ 0 \\ 0 \end{pmatrix} = 6+0+0+0 = 6, \\
c_{22} &= \begin{pmatrix} 6 & 0 & 12 & 18 \end{pmatrix} \cdot
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 1 \end{pmatrix} = 0+0+12+18 = 30.
\end{align*}

Die dritte und vierte Zeile berechnen wir analog aus den entsprechenden Zeilen
von $\mathbf{P}$. Insgesamt erhalten wir

\begin{equation*}
\mathbf{P}\cdot\mathbf{Z} =
\begin{pmatrix}
0 & 14 & 11 & 35 \\
6 & 0 & 12 & 18 \\
24 & 8 & 0 & 5 \\
0 & 7 & 1 & 0 \\
\end{pmatrix} \cdot
\begin{pmatrix} 1 & 0 \\ 1 & 0 \\ 0 & 1 \\ 0 & 1 \end{pmatrix} =
\begin{pmatrix}
14 & 46 \\
6 & 30 \\
32 & 5 \\
7 & 1 \\
\end{pmatrix}.
\end{equation*}

Der Eintrag in Zeile 3, Spalte 1 ist $24+8=32$ ✓. Das bedeutet, Spieler 3 hat
in den ersten zehn Minuten insgesamt 32 Pässe an die beiden Offensivspieler
gespielt, während er nur 5 Pässe an die Defensive gespielt hat. Der Trainer
kann diese Verteilung nun direkt aus der Produktmatrix ablesen.

## Wie behalten wir bei größeren Matrizen den Überblick?

Bei größeren Matrizen wird es schnell unübersichtlich, wenn wir jedes
Skalarprodukt einzeln aufschreiben. Das sogenannte **Falk-Schema** hilft, alle
Skalarprodukte gleichzeitig im Blick zu behalten. Dazu schreiben wir
$\mathbf{Z}$ oben rechts und $\mathbf{P}$ unten links, wie in der folgenden
Tabelle:

\begin{equation*}
\begin{array}{cccc|cc}
   &   &   &    & 1 & 0 \\
   &   &   &    & 1 & 0 \\
   &   &   &    & 0 & 1 \\
   &   &   &    & 0 & 1 \\
\hline
0  & 14 & 11 & 35 & \mathbf{14} & \mathbf{46} \\
6  & 0  & 12 & 18 & \mathbf{6}  & \mathbf{30} \\
24 & 8  & 0  & 5  & \mathbf{32} & \mathbf{5}  \\
0  & 7  & 1  & 0  & \mathbf{7}  & \mathbf{1}  \\
\end{array}
\end{equation*}

Jede fett gedruckte Zelle unten rechts entsteht als Skalarprodukt aus der Zeile
von $\mathbf{P}$ links daneben und der Spalte von $\mathbf{Z}$ darüber, genau
die Rechnungen, die wir eben von Hand durchgeführt haben. Wichtig ist, dass
das Falk-Schema nur eine Rechenhilfe ist. Das endgültige Ergebnis, die
Produktmatrix $\mathbf{P}\cdot\mathbf{Z}$, wird separat notiert und nicht nur
im Schema stehen gelassen.

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

## Gilt das Kommutativgesetz auch hier?

Bei der Vektoraddition und der Skalarmultiplikation aus Kapitel 1.3 haben sich
die Rechenregeln der reellen Zahlen direkt auf die Matrizenoperationen
übertragen, da diese elementweise ausgeführt werden. Bei der
Matrizenmultiplikation ist das anders, denn hier wird nicht elementweise
gerechnet. *Dürfen wir also die Reihenfolge vertauschen und stattdessen
$\mathbf{Z}\cdot\mathbf{P}$ berechnen?*

Das ist bereits aus einem einfachen Grund nicht möglich: $\mathbf{Z}$ hat zwei
Spalten, $\mathbf{P}$ hat vier Zeilen. Da die Spaltenanzahl der ersten Matrix
nicht mit der Zeilenanzahl der zweiten übereinstimmt, ist $\mathbf{Z}\cdot
\mathbf{P}$ gar nicht definiert. Das passt auch inhaltlich, denn
$\mathbf{Z}$ ordnet lediglich zu, welcher Mannschaftsposition ein Spieler
angehört, eine Multiplikation von Position mal Passmatrix ergibt keinen Sinn.

Selbst wenn die Dimensionen zweier Matrizen passen, gilt das Kommutativgesetz
meist trotzdem nicht, wie das folgende Beispiel zeigt. Es gilt:

\begin{equation*}
\mathbf{A}\cdot\mathbf{B} =
\begin{pmatrix} 1 & 2 \\ 3 & 4 \\ \end{pmatrix} \cdot
\begin{pmatrix} 0 & 1 \\ 1 & 0 \\ \end{pmatrix} =
\begin{pmatrix} 2 & 1 \\ 4 & 3 \\ \end{pmatrix},
\end{equation*}

doch für $\mathbf{B}\cdot\mathbf{A}$ erhalten wir:

\begin{equation*}
\mathbf{B}\cdot\mathbf{A} =
\begin{pmatrix} 0 & 1 \\ 1 & 0 \\ \end{pmatrix} \cdot
\begin{pmatrix} 1 & 2 \\ 3 & 4 \\ \end{pmatrix} =
\begin{pmatrix} 3 & 4 \\ 1 & 2 \\ \end{pmatrix}.
\end{equation*}

Die beiden Ergebnisse unterscheiden sich, also gilt $\mathbf{A}\cdot\mathbf{B}
\neq \mathbf{B}\cdot\mathbf{A}$. Es gibt zwar Ausnahmen, in denen
$\mathbf{A}\cdot\mathbf{B} = \mathbf{B}\cdot\mathbf{A}$ gilt, doch in den
meisten Fällen ist das nicht so.

## Welche Rechenregeln gelten dann noch?

Auch wenn das Kommutativgesetz für die Matrizenmultiplikation nicht gilt,
sind nicht alle vertrauten Rechenregeln verloren. Es gelten weiterhin das
Assoziativgesetz

\begin{equation*}
(\mathbf{A}\cdot\mathbf{B})\cdot\mathbf{C} = \mathbf{A}\cdot(\mathbf{B}\cdot\mathbf{C})
\end{equation*}

und das Distributivgesetz

\begin{align*}
\mathbf{A}\cdot(\mathbf{B}+\mathbf{C}) &= \mathbf{A}\cdot\mathbf{B} + \mathbf{A}\cdot\mathbf{C} \\
(\mathbf{A}+\mathbf{B})\cdot\mathbf{C} &= \mathbf{A}\cdot\mathbf{C} + \mathbf{B}\cdot\mathbf{C}.
\end{align*}

Diese beiden Gesetze erlauben es uns, komplexere Matrizenprodukte umzuformen
und zu vereinfachen, ohne jedes Mal alle Einträge einzeln neu berechnen zu
müssen. In der Mehrkörpersimulation nutzt man das Assoziativgesetz
beispielsweise, um lange Ketten von Transformationsmatrizen bei der Berechnung
eines Kinematikmodells beliebig zu klammern, ohne dass sich das Ergebnis
ändert. Genau das wird uns in Kapitel 2 nützlich sein, wenn wir lineare
Gleichungssysteme in Matrixschreibweise lösen.

```{dropdown} Video "Rechenregeln Matrizen (Teil 3)" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/4XwlwmIDsPo"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
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
nächsten Kapitel, Kapitel 2 zu inversen Matrizen und linearen
Gleichungssystemen, beginnen wir mit Abschnitt 2.1 zu transponierten und
symmetrischen Matrizen, bevor wir uns der Berechnung inverser Matrizen
zuwenden.
