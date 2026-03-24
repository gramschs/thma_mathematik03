# Matrizenaddition

In den letzten beiden Kapiteln haben wir gelernt, was Matrizen sind, und
ausgewählte besondere Matrizen kennengelernt. In diesem Kapitel werden wir zum
ersten Mal mit Matrizen rechnen.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können zwei Matrizen **addieren**, also die Summe zweier Matrizen
  bilden.
* [ ] Sie können die **Differenz zweier Matrizen** berechnen, also Matrizen
  subtrahieren.
```

## Addition von zwei Matrizen

Wir greifen das Beispiel auf, ein Fußballspiel statistisch auszuwerten, um im
darauffolgenden Training Defizite der Mannschaft zu reduzieren. Dazu wird das
Passspiel der ersten fünf Minuten in einer Tabelle protokolliert (wir zeigen
hier nur das Passspiel von vier Spielern):

| | Spieler 1 | Spieler 2 | Spieler 3 | Spieler 4 |
| --- | --- | --- | --- | --- |
| Spieler 1 | 0 | 8 | 3 | 20 |
| Spieler 2 | 2 | 0 | 6 | 9 |
| Spieler 3 | 17 | 4 | 0 | 2 |
| Spieler 4 | 0 | 3 | 1 | 0 |

Die Tabelle lesen wir folgendermaßen. In der ersten Zeile stehen die Pässe des
Spielers 1 an die anderen Spieler. Spieler 1 hat also 0-mal sich selbst
angespielt, 8-mal Spieler 2 angespielt, 3-mal Spieler 3 und am häufigsten
Spieler 4, den 20-mal von Spieler 1 angespielt wurde. Wir speichern diese
Informationen etwas kompakter in der Matrix $\textbf{P}_1$

\begin{equation*}
\mathbf{P}_1 = \begin{pmatrix}
0 & 8 & 3 & 20 \\
2 & 0 & 6 & 9 \\
17 & 4 & 0 & 2 \\
0 & 3 & 1 & 0 \\
\end{pmatrix}.
\end{equation*}

In den nächsten 5 Minuten werden die folgenden Pässe mitprotokolliert

| | Spieler 1 | Spieler 2 | Spieler 3 | Spieler 4 |
| --- | --- | --- | --- | --- |
| Spieler 1 | 0 | 6 | 8 | 15 |
| Spieler 2 | 4 | 0 | 6 | 9 |
| Spieler 3 | 7 | 4 | 0 | 3 |
| Spieler 4 | 0 | 4 | 0 | 0 |

und als Matrix gespeichert:

\begin{equation*}
\mathbf{P}_2 = \begin{pmatrix}
0 & 6 & 8 & 15 \\
4 & 0 & 6 & 9 \\
7 & 4 & 0 & 3 \\
0 & 4 & 0 & 0 \\
\end{pmatrix}.
\end{equation*}

Wenn wir jetzt wissen wollen, wie viele Pässe in den ersten 10 Minuten insgesamt
von einem Spieler zu den anderen gespielt wurden, müssen wir jede Pässe
addieren:

| | Spieler 1 | Spieler 2 | Spieler 3 | Spieler 4 |
| --- | --- | --- | --- | --- |
| Spieler 1 | 0 | 8+6 | 3+8 | 20+15 |
| Spieler 2 | 2+4 | 0 | 6+6 | 9+9 |
| Spieler 3 | 17+7 | 4+4 | 0 | 2+3 |
| Spieler 4 | 0 | 3+4 | 1+0 | 0 |

Mathematisch ausgedrückt wird jedes Element der Matrix zu dem Element addiert,
das die gleiche Position hat. Das setzt natürlich voraus, dass die beiden
Matrizen die gleiche Dimension haben.

\begin{equation*}
\mathbf{P}_1 + \mathbf{P}_2 =
\begin{pmatrix}
0 & 8 & 3 & 20 \\
2 & 0 & 6 & 9 \\
17 & 4 & 0 & 2 \\
0 & 3 & 1 & 0 \\
\end{pmatrix} +
\begin{pmatrix}
0 & 6 & 8 & 15 \\
4 & 0 & 6 & 9 \\
7 & 4 & 0 & 3 \\
0 & 4 & 0 & 0 \\
\end{pmatrix} =
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

```{dropdown} Video "Addition von Matrizen" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/1LQbgBPYflM"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Differenz von Matrizen

Die Subtraktion zweier Matrizen ist streng genommen keine eigene
Rechenoperation, sondern eine Kombination der Vektoraddition und der
Skalarmultiplikation mit dem Faktor $-1$, die wir im nächsten Kapitel
kennenlernen werden. Um Berechnungen zu vereinfachen führen wir dennoch die
**Subtraktion zweier Matrizen** als elementweise Subtraktion der Einträge ein:

\begin{equation*}
\mathbf{A} - \mathbf{B} =
\begin{pmatrix}
a_{11} - b_{11} & a_{12} - b_{12} & \ldots & a_{1n} - b_{1n} \\
a_{21} - b_{21} & a_{22} - b_{22} & \ldots & a_{2n} - b_{2n} \\
\vdots          & \vdots          &        & \vdots \\
a_{m1} - b_{m1} & a_{m2} - b_{m2} & \ldots & a_{mn} - b_{mn} \\
\end{pmatrix}.
\end{equation*}

Soll beispielsweise die Differenz der folgenden zwei Matrizen gebildet werden,
werden die entsprechenden Einträge der beiden Matrizen elementweise voneinander
subtrahiert:

\begin{equation*}
\begin{pmatrix} 3 & -5 \\ 1.5 & 8 \end{pmatrix} -
\begin{pmatrix} 2 &  3 \\ 0   & -3 \end{pmatrix} =
\begin{pmatrix} 1 & -8 \\ 1.5 & 11 \end{pmatrix}.
\end{equation*}

Wie bei der Vektoraddition kann die Differenz zweier Matrizen nur gebildet
werden, wenn die Dimension der beiden Matrizen übereinstimmt, d.h. die Anzahl an
Zeilen und Spalten übereinstimmt.

## Zusammenfassung und Ausblick

Nachdem wir in diesem Kapitel gelernt haben, wie zwei Matrizen addiert oder
subtrahiert werden, wird es im nächsten Kapitel darum gehen, eine Matrix mit
einem Skalar zu multiplizieren.
