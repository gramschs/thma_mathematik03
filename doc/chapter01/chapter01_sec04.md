# Skalarmultiplikation

Anstatt eine Matrix mehrfach zu sich selbst zu addieren, können wir dies durch
die Multiplikation mit einem Skalar vereinfachen. In diesem Kapitel betrachten
wir daher die Skalarmultiplikation und die dazugehörigen Rechenregeln.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie sind in der Lage, eine Matrix mit einem Skalar multiplizieren, also eine
  **Skalarmultiplikation** durchführen.
* Sie können die **Differenz zweier Matrizen** berechnen, also Matrizen subtrahieren.
* Sie beherrschen die Rechenregeln für die Addition von Matrizen und für die
  Skalarmultiplikation, insbesondere
  * das **Kommutativgesetz**: 
    \begin{equation*}\mathbf{A}+\mathbf{B} = \mathbf{B}+\mathbf{A}\end{equation*},
  * das **Assoziativgesetz**: 
    \begin{equation*}(\mathbf{A}+\mathbf{B})+\mathbf{C} = \mathbf{A} +
      (\mathbf{B}+\mathbf{C}),\end{equation*} 
  * und das **Distributivgesetz** für die Skalarmultiplikation: 
    \begin{align*}
    (s+t)\cdot\mathbf{A} &= s\cdot\mathbf{A}+t\cdot\mathbf{A}\\
    s\cdot(\mathbf{A}+\mathbf{B}) &= s\cdot\mathbf{A} + s\cdot\mathbf{B}\\
    \end{align*}
```

## Skalar mal Matrix

Wir greifen erneut das Beispiel auf, bei dem Fußballspieler sich gegenseitig
Pässe zuspielen und die Pässe mitprotokolliert werden, damit die
Spielerleistungen statistisch ausgewertet werden können.  Diesmal betrachten wir
jedoch die Pässe während des Trainings. Im Training werden die Spieler in
Vierergruppen aufgeteilt, und jeder Spieler soll jedem anderen fünfmal den Ball
zuspielen. Die aufgezeichneten Pässe sind in der folgenden Matrix kodiert:

$$\mathbf{A} = \begin{pmatrix}
0 & 5 & 5 & 5 \\
5 & 0 & 5 & 5 \\
5 & 4 & 0 & 5 \\
5 & 5 & 5 & 0 \\
\end{pmatrix}.$$

Zur Erinnerung: Eine 5 in der ersten Zeile und in der zweiten Spalte (also
$a_{12} = 5$) bedeutet, dass der 1. Spieler dem 2. Spieler fünfmal den Ball
zugespielt hat. Es fällt jedoch auf, dass die Übung nicht korrekt ausgeführt
wurde, da der 3. Spieler den 2. Spieler nur viermal angespielt hat ($a_{32}=4$),
während der 2. Spieler den 3. Spieler wie gefordert fünfmal angespielt hat
($a_{23}=5$).

Nun soll diese Übung zwei weitere Male korrekt wiederholt werden. Diesmal
verläuft die Übung fehlerfrei, und die neue Matrix zeigt die korrekten Pässe des
zweiten und dritten Durchgangs:

$$\mathbf{B} = \begin{pmatrix}
0 & 5 & 5 & 5 \\
5 & 0 & 5 & 5 \\
5 & 5 & 0 & 5 \\
5 & 5 & 5 & 0 \\
\end{pmatrix}.$$

Nach Abschluss der drei Übungen sollen alle Pässe insgesamt summiert werden. Wir
könnten jedes Element einzeln addieren, indem wir die Anzahl der Pässe für jede
Übung zusammenzählen:

$$\mathbf{A} + \mathbf{B} + \mathbf{B} =
\begin{pmatrix}
0+0+0 & 5+5+5 & 5+5+5 & 5+5+5 \\
5+5+5 & 0+5+5 & 5+5+5 & 5+5+5 \\
5+5+5 & 4+5+5 & 0+5+5 & 5+5+5 \\
5+5+5 & 5+5+5 & 5+5+5 & 0+5+5 \\
\end{pmatrix}$$

Da die zweite und dritte Übung identisch abliefen, können wir die Pässe der
zweiten und dritten Übung auch direkt verdoppeln:

$$\mathbf{B} + \mathbf{B} = 2\cdot\mathbf{B} =
\begin{pmatrix}
2\cdot 0 & 2\cdot 5 & 2\cdot 5 & 2\cdot 5 \\
2\cdot 5 & 2\cdot 0 & 2\cdot 5 & 2\cdot 5 \\
2\cdot 5 & 2\cdot 5 & 2\cdot 0 & 2\cdot 5 \\
2\cdot 5 & 2\cdot 5 & 2\cdot 5 & 2\cdot 0 \\
\end{pmatrix}=
\begin{pmatrix}
0 & 10 & 10 & 10 \\
10 & 0 & 10 & 10 \\
10 & 10 & 0 & 10 \\
10 & 10 & 10 & 0 \\
\end{pmatrix}$$

Allgemein wird bei einer Skalarmultiplikation eine Matrix mit einer reellen Zahl
(Skalar) multipliziert, indem jedes Element der Matrix mit dem Skalar
multipliziert wird.

```{admonition} Was ist ... die Skalarmultiplikation?
:class: note
Bei der Skalarmultiplikation wird ein Skalar mit einer Matrix multipliziert,
indem jedes Element der Matrix mit diesem Skalar multipliziert wird.
```

Ein weiteres Beispiel für eine Skalarmultiplikation ist die folgende Rechnung,
bei der jedes Element der Matrix mit dem Bruch $1/2$ multipliziert wird:

$$\frac{1}{2}\cdot\begin{pmatrix} 2 & 7 \\ -10 & \frac{3}{5} \end{pmatrix} =
\begin{pmatrix} 1 & 3.5 \\ -5 & \frac{3}{10} \end{pmatrix}.$$

Das folgende Video veranschaulicht ein weiteres Beispiel zur Skalarmultiplikation.

```{dropdown} Video "Skalarmultiplikation" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/1fIxfjWammQ"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Rechengesetze für die Addition und Skalarmultiplikation von Matrizen

Bei der Berechnung der Summe der Pässe aus den drei Übungen haben wir intuitiv
genutzt, dass die zweite und dritte Übung identisch abgelaufen sind, und uns
daher zunächst mit der Berechnung von zwei gleichen Matrizen befasst. Für die
vollständige Summe fehlt jedoch noch die Addition der Pässe aus der ersten
Übung:

$$2\cdot\mathbf{B} + \mathbf{A} =
\begin{pmatrix}
0 & 10 & 10 & 10 \\
10 & 0 & 10 & 10 \\
10 & 10 & 0 & 10 \\
10 & 10 & 10 & 0 \\
\end{pmatrix} +
\begin{pmatrix}
0 & 5 & 5 & 5 \\
5 & 0 & 5 & 5 \\
5 & 4 & 0 & 5 \\
5 & 5 & 5 & 0 \\
\end{pmatrix} =
\begin{pmatrix}
0 & 15 & 15 & 15 \\
15 & 0 & 15 & 15 \\
15 & 14 & 0 & 15 \\
15 & 15 & 15 & 0 \\
\end{pmatrix}.$$

Ist diese Vorgehensweise überhaupt erlaubt? Gilt also

$$2\cdot\mathbf{B} + \mathbf{A} \overset{?}{=} \mathbf{A} + \mathbf{B} + \mathbf{B} \,?$$

Ja, denn sowohl die Addition als auch die Skalarmultiplikation werden
*elementweise* mit reellen Zahlen durchgeführt. Für reelle Zahlen gelten das
Kommutativgesetz, das besagt, dass die Reihenfolge der Summanden keine Rolle
spielt, sowie das Assoziativgesetz, das sicherstellt, dass die Reihenfolge der
Gruppierungen bei der Addition ebenfalls irrelevant ist.

Da die Vektoraddition elementweise ausgeführt wird, überträgt sich das
Kommutativgesetz der reellen Zahlen auf Matrizen. Das bedeutet, dass die
Addition zweier Matrizen unabhängig von der Reihenfolge der Matrizen ist, wie
die folgende allgemeine Rechnung zeigt:

$$\mathbf{A} + \mathbf{B} =
\begin{pmatrix}
a_{11} + b_{11} & a_{12} + b_{12} & \ldots & a_{1n} + b_{1n} \\
a_{21} + b_{21} & a_{22} + b_{22} & \ldots & a_{2n} + b_{2n} \\
\vdots & \vdots &        & \vdots \\
a_{m1} + b_{m2} & a_{m2} + b_{m2} & \ldots & a_{mn} + b_{mn}
\end{pmatrix} +
\begin{pmatrix}
b_{11} + a_{11} & b_{12} + a_{12} & \ldots & b_{1n} + a_{1n} \\
b_{21} + a_{21} & b_{22} + a_{22} & \ldots & b_{2n} + a_{2n} \\
\vdots & \vdots &        & \vdots \\
b_{m1} + a_{m1} & b_{m2} + a_{m2} & \ldots & b_{mn} + a_{mn}
\end{pmatrix} =
\mathbf{B} + \mathbf{A}.$$

Auf dieselbe Weise kann auch das Assoziativgesetz angewendet werden: Es spielt
keine Rolle, ob man zuerst zwei Matrizen addiert und dann die dritte dazu nimmt
oder ob man zuerst eine Summe bildet und anschließend die verbleibenden Matrizen
addiert. Dies erlaubt es uns, die Berechnung zu vereinfachen, indem wir z. B.
direkt die Addition durch eine Skalarmultiplikation ersetzen. Anstatt
$(\mathbf{A} + \mathbf{B}) + \mathbf{B}$ zu berechnen ist es erlaubt $\mathbf{A} +
(\mathbf{B} + \mathbf{B}) = \mathbf{A} + 2\mathbf{B}$ zu verwenden.

Ebenso überträgt sich das Distributivgesetz von reellen Zahlen auf die Addition von Matrizen und die Skalarmultiplikation. Dabei gibt es zwei Möglichkeiten:

1. Ein Skalar wird mit der Summe zweier Matrizen multipliziert. Das entspricht
   der Verteilung des Skalars auf beide Matrizen, sodass jede Matrix einzeln mit
   dem Skalar multipliziert wird, also

   $$s\cdot\left(\mathbf{A} + \mathbf{B} \right) = s\cdot\mathbf{A} +
   s\cdot\mathbf{B}.$$

2. Zwei Skalare werden addiert und die resultierende Summe wird mit einer Matrix
   multipliziert. Dies entspricht der Multiplikation der Matrix mit jedem Skalar
   einzeln und der anschließenden Addition der Ergebnisse, also

   $$(s + t) \cdot \mathbf{A} = s\cdot\mathbf{A} + t\cdot\mathbf{A}.$$

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

## Differenz von Matrizen

Die Subtraktion zweier Matrizen ist streng genommen keine eigene
Rechenoperation, sondern eine Kombination der Vektoraddition und der
Skalarmultiplikation mit dem Faktor $-1$. Um Berechnungen zu vereinfachen führen
wir dennoch die **Subtraktion zweier Matrizen** als elementweise Subtraktion der
Einträge ein:

$$\mathbf{A} - \mathbf{B} =
\begin{pmatrix}
a_{11} - b_{11} & a_{12} - b_{12} & \ldots & a_{1n} - b_{1n} \\
a_{21} - b_{21} & a_{22} - b_{22} & \ldots & a_{2n} - b_{2n} \\
\vdots          & \vdots          &        & \vdots \\
a_{m1} - b_{m1} & a_{m2} - b_{m2} & \ldots & a_{mn} - b_{mn} \\
\end{pmatrix}.$$

Soll beispielsweise die Differenz der folgenden zwei Matrizen gebildet werden,
werden die entsprechenden Einträge der beiden Matrizen elementweise voneinander
subtrahiert:

$$
\begin{pmatrix} 3 & -5 \\ 1.5 & 8 \end{pmatrix} -
\begin{pmatrix} 2 &  3 \\ 0   & -3 \end{pmatrix} =
\begin{pmatrix} 1 & -8 \\ 1.5 & 11 \end{pmatrix}
.$$

Wie bei der Vektoraddition kann die Differenz zweier Matrizen nur gebildet
werden, wenn die Dimension der beiden Matrizen übereinstimmt, d.h. die Anzahl an
Zeilen und Spalten übereinstimmt.

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir die Skalarmultiplikation kennengelernt, bei der
jeder Eintrag einer Matrix mit einem Skalar multipliziert wird. Die
Rechengesetze der reellen Zahlen, wie das Kommutativ-, Assoziativ- und
Distributivgesetz, lassen sich auf die Vektoraddition und die
Skalarmultiplikation übertragen. Im nächsten Kapitel werden wir die
Multiplikation zweier Matrizen erlernen.
