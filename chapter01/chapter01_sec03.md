---
authors:
  - name: Simone Gramsch
---

# 1.3 Addition und Skalarmultiplikation

In den letzten beiden Kapiteln haben wir anhand des 3x3-Basketballspiels
gelernt, was Matrizen sind und welche besonderen Formen wie die Einheitsmatrix
oder die Dreiecksmatrix es gibt. Für die folgenden Rechenoperationen wechseln
wir das Beispiel zu einem Fußballtraining. Anders als beim 3x3-Basketball mit
seiner festen Dreierbesetzung erlaubt uns eine Trainingsgruppe mit frei
wählbarer Größe, sowohl gleich große als auch unterschiedlich große Matrizen zu
betrachten, was insbesondere bei der Matrizenmultiplikation im nächsten Kapitel
wichtig wird. Jetzt rechnen wir zum ersten Mal mit Matrizen. Zwei Operationen
stehen im Mittelpunkt: die elementweise Addition zweier Matrizen und die
Multiplikation einer Matrix mit einer reellen Zahl, die wir Skalarmultiplikation
nennen. Beide begegnen uns überall dort im Maschinenbau, wo Daten aus
verschiedenen Lastfällen überlagert oder mit Faktoren gewichtet werden.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können zwei Matrizen **addieren** (**Summe**) und **subtrahieren**
  (**Differenz**).
* [ ] Sie können eine Matrix mit einem reellen Skalar multiplizieren
  (**Skalarmultiplikation**).
* [ ] Sie kennen das **Kommutativgesetz** für die Matrizenaddition: 
  $$\mathbf{A} + \mathbf{B} = \mathbf{B} + \mathbf{A}.$$
* [ ] Sie kennen das **Assoziativgesetz** für die Matrizenaddition:
  $$(\mathbf{A}+\mathbf{B})+\mathbf{C} = \mathbf{A}+(\mathbf{B}+\mathbf{C}).$$
* [ ] Sie können das **Distributivgesetz** anwenden: 
  \begin{align*}
  s\cdot(\mathbf{A}+\mathbf{B}) = s\cdot\mathbf{A}+s\cdot\mathbf{B},\\
  (s+t)\cdot\mathbf{A} = s\cdot\mathbf{A}+t\cdot\mathbf{A}.
  \end{align*}
```

## Wie addieren wir zwei Matrizen?

Stellen wir uns vor, wir werten ein Fußballspiel statistisch aus, um im
anschließenden Training gezielte Schwerpunkte setzen zu können. In den ersten
fünf Minuten protokollieren wir das Passspiel von vier Spielern:

| | Spieler 1 | Spieler 2 | Spieler 3 | Spieler 4 |
| --- | --- | --- | --- | --- |
| **Spieler 1** | 0 | 8 | 3 | 20 |
| **Spieler 2** | 2 | 0 | 6 | 9 |
| **Spieler 3** | 17 | 4 | 0 | 2 |
| **Spieler 4** | 0 | 3 | 1 | 0 |

Jeder Eintrag gibt an, wie oft der Spieler in der entsprechenden Zeile den
Spieler in der entsprechenden Spalte angespielt hat. Spieler 1 hat zum Beispiel
8 Pässe zu Spieler 2 gespielt, aber nur 3 zu Spieler 3. Diese Daten speichern
wir kompakt als Matrix $\mathbf{P}_1$:

\begin{equation*}
\mathbf{P}_1 = \begin{pmatrix}
0 & 8 & 3 & 20 \\
2 & 0 & 6 & 9 \\
17 & 4 & 0 & 2 \\
0 & 3 & 1 & 0 \\
\end{pmatrix}.
\end{equation*}

In den nächsten fünf Minuten wird das Passspiel weiter protokolliert und in der
Matrix $\mathbf{P}_2$ gespeichert:

\begin{equation*}
\mathbf{P}_2 = \begin{pmatrix}
0 & 6 & 8 & 15 \\
4 & 0 & 6 & 9 \\
7 & 4 & 0 & 3 \\
0 & 4 & 0 & 0 \\
\end{pmatrix}.
\end{equation*}

*Wie viele Pässe hat jeder Spieler in den ersten zehn Minuten insgesamt
gespielt?* Wir zählen die Pässe jeder Spielerpaarung aus beiden Intervallen
zusammen, addieren also Position für Position:

\begin{equation*}
\mathbf{P}_1 + \mathbf{P}_2 =
\begin{pmatrix}
0+0 & 8+6 & 3+8 & 20+15 \\
2+4 & 0+0 & 6+6 & 9+9 \\
17+7 & 4+4 & 0+0 & 2+3 \\
0+0 & 3+4 & 1+0 & 0+0 \\
\end{pmatrix} =
\begin{pmatrix}
0 & 14 & 11 & 35 \\
6 & 0 & 12 & 18 \\
24 & 8 & 0 & 5 \\
0 & 7 & 1 & 0 \\
\end{pmatrix}.
\end{equation*}

Das Muster ist klar: Wir addieren jeweils die Einträge, die dieselbe Position
haben. Voraussetzung ist, dass beide Matrizen dieselbe Dimension besitzen.

```{admonition} Was ist ... die Matrizenaddition?
:class: note
Zwei Matrizen $\mathbf{A}$ und $\mathbf{B}$ der gleichen Dimension $m \times n$
werden **addiert**, indem ihre Einträge an gleicher Position addiert werden:

\begin{equation*}
\mathbf{A} + \mathbf{B} =
\begin{pmatrix}
a_{11} + b_{11} & a_{12} + b_{12} & \ldots & a_{1n} + b_{1n} \\
a_{21} + b_{21} & a_{22} + b_{22} & \ldots & a_{2n} + b_{2n} \\
\vdots          & \vdots          &        & \vdots \\
a_{m1} + b_{m1} & a_{m2} + b_{m2} & \ldots & a_{mn} + b_{mn} \\
\end{pmatrix}.
\end{equation*}

Haben $\mathbf{A}$ und $\mathbf{B}$ unterschiedliche Dimensionen, ist die
Addition nicht definiert.
```

Wir überprüfen die Definition an unserem Passbeispiel. Zum Beispiel ergibt sich
der Eintrag in Zeile 3, Spalte 1 als $17 + 7 = 24$ ✓, wie wir oben berechnet
haben.

In der Finite-Elemente-Methode werden die Steifigkeitsmatrizen einzelner
Bauelemente elementweise zur globalen Steifigkeitsmatrix aufaddiert. Die
Rechenoperation ist dieselbe, die wir gerade am Passbeispiel gesehen haben, nur
mit größeren Matrizen.

```{dropdown} Video "Addition von Matrizen" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/1LQbgBPYflM"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Was bedeutet es, eine Matrix mit einer Zahl zu multiplizieren?

Im Training werden die Spieler in Vierergruppen aufgeteilt, und jeder soll jedem
anderen fünfmal den Ball zuspielen. Die Pässe des ersten Durchgangs sind in der
Matrix $\mathbf{A}$ gespeichert:

\begin{equation*}
\mathbf{A} = \begin{pmatrix}
0 & 5 & 5 & 5 \\
5 & 0 & 5 & 5 \\
5 & 4 & 0 & 5 \\
5 & 5 & 5 & 0 \\
\end{pmatrix}.
\end{equation*}

Wir erkennen, dass Spieler 3 Spieler 2 nur viermal angespielt hat
($a_{32} = 4$ statt $5$). Der zweite und dritte Durchgang verlaufen fehlerfrei
und liefern beide dieselbe Matrix $\mathbf{B}$:

\begin{equation*}
\mathbf{B} = \begin{pmatrix}
0 & 5 & 5 & 5 \\
5 & 0 & 5 & 5 \\
5 & 5 & 0 & 5 \\
5 & 5 & 5 & 0 \\
\end{pmatrix}.
\end{equation*}

Die Gesamtsumme über alle drei Durchgänge ist $\mathbf{A} + \mathbf{B} +
\mathbf{B}$. Da der zweite und dritte Durchgang identisch sind, liegt es nahe,
stattdessen $\mathbf{A} + 2\mathbf{B}$ zu schreiben. Was steckt hinter dem
Faktor $2$ vor der Matrix? Wir multiplizieren jeden Eintrag von $\mathbf{B}$
mit $2$:

\begin{equation*}
2 \cdot \mathbf{B} =
\begin{pmatrix}
2 \cdot 0 & 2 \cdot 5 & 2 \cdot 5 & 2 \cdot 5 \\
2 \cdot 5 & 2 \cdot 0 & 2 \cdot 5 & 2 \cdot 5 \\
2 \cdot 5 & 2 \cdot 5 & 2 \cdot 0 & 2 \cdot 5 \\
2 \cdot 5 & 2 \cdot 5 & 2 \cdot 5 & 2 \cdot 0 \\
\end{pmatrix} =
\begin{pmatrix}
0 & 10 & 10 & 10 \\
10 & 0 & 10 & 10 \\
10 & 10 & 0 & 10 \\
10 & 10 & 10 & 0 \\
\end{pmatrix}.
\end{equation*}

Das Ergebnis ist identisch mit $\mathbf{B} + \mathbf{B}$. Das allgemeine Prinzip
ist klar: Jeder Eintrag der Matrix wird mit der reellen Zahl multipliziert.

```{admonition} Was ist ... die Skalarmultiplikation?
:class: note
Bei der **Skalarmultiplikation** wird ein Skalar $s \in \mathbb{R}$ mit einer
Matrix $\mathbf{A}$ der Dimension $m \times n$ multipliziert, indem jeder
Eintrag der Matrix mit $s$ multipliziert wird:

\begin{equation*}
s \cdot \mathbf{A} =
\begin{pmatrix}
s \cdot a_{11} & s \cdot a_{12} & \ldots & s \cdot a_{1n} \\
s \cdot a_{21} & s \cdot a_{22} & \ldots & s \cdot a_{2n} \\
\vdots         & \vdots         &        & \vdots \\
s \cdot a_{m1} & s \cdot a_{m2} & \ldots & s \cdot a_{mn} \\
\end{pmatrix}.
\end{equation*}
```

Wir verifizieren die Definition an unserem Trainingsbeispiel. Der Eintrag in
Zeile 3, Spalte 2 von $2\mathbf{B}$ ist $2 \cdot b_{32} = 2 \cdot 5 = 10$ ✓.
Das stimmt mit der berechneten Matrix überein.

In der Technischen Mechanik wird die Skalarmultiplikation eingesetzt, wenn
Lastmatrizen mit einem Sicherheitsbeiwert multipliziert werden, um die
bemessungsrelevante Beanspruchung zu erhalten. Auch die Kalibrierung von
Messdaten durch einen Korrekturfaktor ist im Kern eine Skalarmultiplikation.

```{dropdown} Video "Skalarmultiplikation" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/1fIxfjWammQ"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Wie subtrahieren wir zwei Matrizen?

Die **Subtraktion** zweier Matrizen ist keine eigenständige Operation, sondern
eine Kombination der Addition und der Skalarmultiplikation mit dem Faktor $-1$.
Es gilt:

\begin{equation*}
\mathbf{A} - \mathbf{B} = \mathbf{A} + (-1) \cdot \mathbf{B}.
\end{equation*}

In der Praxis schreiben wir die Differenz direkt elementweise: Der Eintrag an
Position $(i, j)$ der Differenz ist $a_{ij} - b_{ij}$. Um zum Beispiel
festzustellen, um wie viele Pässe jede Spielerpaarung im zweiten
Fünf-Minuten-Abschnitt vom ersten abweicht, berechnen wir $\mathbf{P}_2 -
\mathbf{P}_1$:

\begin{equation*}
\mathbf{P}_2 - \mathbf{P}_1 =
\begin{pmatrix}
0-0   & 6-8   & 8-3 & 15-20 \\
4-2   & 0-0   & 6-6 & 9-9 \\
7-17  & 4-4   & 0-0 & 3-2 \\
0-0   & 4-3   & 0-1 & 0-0 \\
\end{pmatrix} =
\begin{pmatrix}
0   & -2 & 5  & -5 \\
2   &  0 & 0  &  0 \\
-10 &  0 & 0  &  1 \\
0   &  1 & -1 &  0 \\
\end{pmatrix}.
\end{equation*}

Der Eintrag $-10$ in Zeile 3, Spalte 1 zeigt, dass Spieler 3 im zweiten
Abschnitt deutlich weniger zu Spieler 1 gespielt hat als im ersten. Wie bei der
Addition gilt auch hier: Die Subtraktion ist nur definiert, wenn beide Matrizen
dieselbe Dimension haben.

## Welche Rechengesetze gelten für Addition und Skalarmultiplikation?

Kehren wir zu unserem Trainingsbeispiel zurück. Wir haben die Gesamtsumme als
$2\mathbf{B} + \mathbf{A}$ berechnet. *Ist es erlaubt, die Reihenfolge zu
tauschen und stattdessen $\mathbf{A} + 2\mathbf{B}$ zu schreiben?* Und dürfen
wir $\mathbf{B} + \mathbf{B}$ durch $2\mathbf{B}$ ersetzen?

Ja, denn Addition und Skalarmultiplikation werden elementweise mit reellen Zahlen
ausgeführt. Für reelle Zahlen gelten das Kommutativ-, das Assoziativ- und das
Distributivgesetz, und diese übertragen sich vollständig auf Matrizen.

Das **Kommutativgesetz** besagt, dass die Reihenfolge der Summanden keine Rolle
spielt:

\begin{equation*}
\mathbf{A} + \mathbf{B} = \mathbf{B} + \mathbf{A}.
\end{equation*}

Das **Assoziativgesetz** besagt, dass die Klammerung bei der Addition irrelevant
ist:

\begin{equation*}
(\mathbf{A}+\mathbf{B})+\mathbf{C} = \mathbf{A}+(\mathbf{B}+\mathbf{C}).
\end{equation*}

Dank des Assoziativgesetzes dürfen wir $\mathbf{A} + (\mathbf{B} + \mathbf{B})$
zu $\mathbf{A} + 2\mathbf{B}$ vereinfachen.

Für die Skalarmultiplikation gelten zudem zwei **Distributivgesetze**. Ein Skalar
$s$ lässt sich über eine Matrizensumme verteilen:

\begin{equation*}
s \cdot (\mathbf{A} + \mathbf{B}) = s \cdot \mathbf{A} + s \cdot \mathbf{B}.
\end{equation*}

Eine Summe zweier Skalare lässt sich auf eine Matrix verteilen:

\begin{equation*}
(s + t) \cdot \mathbf{A} = s \cdot \mathbf{A} + t \cdot \mathbf{A}.
\end{equation*}

Wir verifizieren das erste Distributivgesetz an einem konkreten Beispiel. Mit
$s = 3$, $\mathbf{A} = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}$ und
$\mathbf{B} = \begin{pmatrix} 2 & 0 \\ 1 & 3 \end{pmatrix}$ gilt:

\begin{align*}
s \cdot (\mathbf{A} + \mathbf{B})
&= 3 \cdot \begin{pmatrix} 3 & 2 \\ 1 & 4 \end{pmatrix}
 = \begin{pmatrix} 9 & 6 \\ 3 & 12 \end{pmatrix}, \\[6pt]
s \cdot \mathbf{A} + s \cdot \mathbf{B}
&= \begin{pmatrix} 3 & 6 \\ 0 & 3 \end{pmatrix} +
   \begin{pmatrix} 6 & 0 \\ 3 & 9 \end{pmatrix}
 = \begin{pmatrix} 9 & 6 \\ 3 & 12 \end{pmatrix}. \quad \checkmark
\end{align*}

Beide Wege führen zum selben Ergebnis, das Distributivgesetz gilt also auch für
Matrizen.

```{dropdown} Video "Rechenregeln Matrizen (Teil 1)" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/_9vYtSLNLNI"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

```{dropdown} Video "Rechenregeln Matrizen (Teil 2)" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/cpVJV6j0O4U"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir die Addition, die Skalarmultiplikation und die
Subtraktion von Matrizen kennengelernt. Alle drei Operationen werden elementweise
ausgeführt und setzen voraus, dass alle beteiligten Matrizen dieselbe Dimension
haben. Die vertrauten Rechengesetze der reellen Zahlen übertragen sich
vollständig auf diese Operationen.

Im nächsten Kapitel begegnet uns eine ganz andere Art der Multiplikation: die
Matrizenmultiplikation, bei der zwei Matrizen miteinander multipliziert werden.
Diese Operation ist deutlich komplexer als die elementweise Skalarmultiplikation,
und sie zeigt eine überraschende Eigenschaft: Das Kommutativgesetz gilt im
Allgemeinen nicht mehr. Genau diese Matrizenmultiplikation ist das Fundament für
die linearen Gleichungssysteme und Eigenwertprobleme, die wir in den späteren
Kapiteln behandeln werden.
