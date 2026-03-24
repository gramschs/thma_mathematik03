---
authors:
  - name: "Simone Gramsch"
---

# Determinante für größere Matrizen: der Laplacesche Entwicklungssatz

Im letzten Kapitel haben wir mit der Regel von Sarrus gelernt, wie wir die
Determinante einer $3\times 3$-Matrix berechnen. Die Regel ist anschaulich und
lässt sich gut merken. *Aber was tun wir, wenn die Matrix größer ist?* Die
Sarrus-Regel gilt ausschließlich für $3\times 3$-Matrizen und lässt sich nicht
auf höhere Dimensionen übertragen. Wir brauchen also ein allgemeineres Verfahren,
das für jede quadratische Matrix funktioniert.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, warum die Regel von Sarrus auf Matrizen der Dimension $n > 3$
  nicht anwendbar ist.
* [ ] Sie können zu einem Element $a_{ij}$ die zugehörige **Untermatrix**
  $\mathbf{A}_{ij}$ bestimmen.
* [ ] Sie können die Determinante einer $n\times n$-Matrix mit dem
  **Laplaceschen Entwicklungssatz** nach einer beliebigen Zeile oder Spalte
  berechnen.
* [ ] Sie wählen die Entwicklungszeile oder -spalte strategisch aus, um den
  Rechenaufwand zu minimieren.
```

## Warum reicht die Sarrus-Regel nicht aus?

Die Determinante einer $n\times n$-Matrix ist als Summe über alle $n!$
Permutationen der Spaltenindizes definiert. Für $n = 3$ sind das $3! = 6$ Terme,
und die Sarrus-Regel liefert genau diese 6 Diagonalprodukte. Das ist kein
allgemeines Prinzip, sondern ein glücklicher Spezialfall: Nur bei $n = 3$
stimmt die Anzahl der Diagonalen mit der Anzahl der Determinantenterme überein.
Für $n = 4$ hingegen hat die Determinante $4! = 24$ Terme. Ein
Diagonalverfahren kann das nicht abbilden.

Die Grundidee des **Laplaceschen Entwicklungssatzes** ist stattdessen folgende:
Wir zerlegen das $n\times n$-Problem rekursiv in mehrere
$(n-1)\times(n-1)$-Probleme. Eine $4\times 4$-Determinante wird so auf
$3\times 3$-Determinanten zurückgeführt, die wir mit Sarrus lösen können.

## Was ist eine Untermatrix?

Bevor wir die Formel aufschreiben, führen wir einen neuen Begriff ein. Die
**Untermatrix** $\mathbf{A}_{ij}$ entsteht, indem wir aus der Matrix
$\mathbf{A}$ die $i$-te Zeile und die $j$-te Spalte vollständig streichen. Das
Ergebnis hat eine Zeile und eine Spalte weniger als die ursprüngliche Matrix.

Als Beispiel betrachten wir die $4\times 4$-Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix}
1 & 2 & 0 & 3 \\
4 & 5 & 1 & 0 \\
0 & 3 & 2 & 1 \\
2 & 0 & 4 & 1
\end{pmatrix}.
\end{equation*}

Die Untermatrix $\mathbf{A}_{12}$ ergibt sich, indem wir die erste Zeile und die
zweite Spalte streichen:

\begin{equation*}
\mathbf{A}_{12} = \begin{pmatrix}
4 & 1 & 0 \\
0 & 2 & 1 \\
2 & 4 & 1
\end{pmatrix}.
\end{equation*}

```{admonition} Was ist ... eine Untermatrix?
:class: note
Die **Untermatrix** $\mathbf{A}_{ij}$ einer $n\times n$-Matrix $\mathbf{A}$
entsteht durch Streichen der $i$-ten Zeile und der $j$-ten Spalte. Sie hat die
Dimension $(n-1)\times(n-1)$.
```

## Wie lautet der Laplacesche Entwicklungssatz?

Wir entwickeln die Determinante nach der $i$-ten Zeile:

\begin{equation*}
\det(\mathbf{A}) = \sum_{j=1}^{n} (-1)^{i+j}\cdot a_{ij}\cdot\det(\mathbf{A}_{ij}).
\end{equation*}

Jedes Element $a_{ij}$ der gewählten Zeile wird mit der Determinante seiner
Untermatrix multipliziert. Das Vorzeichen $(-1)^{i+j}$ wechselt schachbrettartig
zwischen $+$ und $-$. Für eine $4\times 4$-Matrix sieht dieses Muster so aus:

<!-- markdownlint-disable MD032 -->
<!-- markdownlint-disable MD004 -->
\begin{equation*}
\begin{pmatrix}
+ & - & + & - \\
- & + & - & + \\
+ & - & + & - \\
- & + & - & +
\end{pmatrix}.
\end{equation*}
<!-- markdownlint-ensable MD004 -->
<!-- markdownlint-ensable MD032 -->

Analog entwickeln wir nach der $j$-ten Spalte:

\begin{equation*}
\det(\mathbf{A}) = \sum_{i=1}^{n} (-1)^{i+j}\cdot a_{ij}\cdot\det(\mathbf{A}_{ij}).
\end{equation*}

Das Ergebnis ist in beiden Fällen dasselbe. Wir dürfen also frei wählen,
nach welcher Zeile oder Spalte wir entwickeln.

```{dropdown} Video "Determinante - Laplace Entwicklungssatz" von Mathematrick
<iframe width="560" height="315" src="https://www.youtube.com/embed/3cG0HWdmHLI?si=UT5KjVo88k9dNPoj"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Wie wählen wir die Entwicklungszeile geschickt?

*Welche Zeile oder Spalte wählen wir am besten?* Wir suchen diejenige mit den
meisten Nullen. Jede Null setzt einen ganzen Summanden auf Null und spart uns
eine vollständige $3\times 3$-Rechnung. In unserer Matrix enthält die erste
Zeile an Position $a_{13} = 0$ eine Null. Wir entwickeln daher nach der ersten
Zeile.

Mit dem Vorzeichenmuster $+, -, +, -$ ergibt sich:

<!-- markdownlint-disable MD049 -->
\begin{align*}
\det(\mathbf{A})
&= (+1)\cdot 1 \cdot\det(\mathbf{A}_{11}) +
(-1)\cdot 2 \cdot\det(\mathbf{A}_{12}) +
(+1)\cdot 0 \cdot\det(\mathbf{A}_{13}) +
(-1)\cdot 3 \cdot\det(\mathbf{A}_{14}).
\end{align*}
<!-- markdownlint-ensable MD049 -->

Da $a_{13} = 0$ ist, fällt der dritte Summand sofort weg. Wir benötigen nur
drei Untermatrizen:

\begin{equation*}
\mathbf{A}_{11} = \begin{pmatrix}
5 & 1 & 0 \\
3 & 2 & 1 \\
0 & 4 & 1
\end{pmatrix}, \quad
\mathbf{A}_{12} = \begin{pmatrix}
4 & 1 & 0 \\
0 & 2 & 1 \\
2 & 4 & 1
\end{pmatrix}, \quad
\mathbf{A}_{14} = \begin{pmatrix}
4 & 5 & 1 \\
0 & 3 & 2 \\
2 & 0 & 4
\end{pmatrix}.
\end{equation*}

Wir berechnen die drei $3\times 3$-Determinanten mit der Sarrus-Regel:

\begin{align*}
\det(\mathbf{A}_{11})
&= 5\cdot 2\cdot 1 + 1\cdot 1\cdot 0 + 0\cdot 3\cdot 4 -
 \left(0\cdot 2\cdot 0 + 4\cdot 1\cdot 5 + 1\cdot 3\cdot 1\right)
= 10 - 23 = -13,\\
\det(\mathbf{A}_{12})
&= 4\cdot 2\cdot 1 + 1\cdot 1\cdot 2 + 0\cdot 0\cdot 4 -
 \left(2\cdot 2\cdot 0 + 4\cdot 1\cdot 4 + 1\cdot 0\cdot 1\right)
= 10 - 16 = -6,\\
\det(\mathbf{A}_{14})
&= 4\cdot 3\cdot 4 + 5\cdot 2\cdot 2 + 1\cdot 0\cdot 0 -
 \left(2\cdot 3\cdot 1 + 0\cdot 2\cdot 4 + 4\cdot 0\cdot 5\right)
= 68 - 6 = 62.
\end{align*}

Einsetzen in den Entwicklungssatz liefert:

\begin{equation*}
\det(\mathbf{A})
= 1\cdot(-13) - 2\cdot(-6) + 0 - 3\cdot 62
= -13 + 12 - 186 = -187.
\end{equation*}

Als Probe entwickeln wir nach der dritten Zeile, die ebenfalls eine Null enthält
($a_{31} = 0$), und erhalten erneut $\det(\mathbf{A}) = -187$. Das bestätigt,
dass das Ergebnis unabhängig von der Wahl der Entwicklungszeile ist.

```{admonition} Übung: Berechnung von Determinanten
:class: tip
Gehen Sie auf die Internetseite

> [https://matex.mint-kolleg.kit.edu/MATeX/browse.php](https://matex.mint-kolleg.kit.edu/MATeX/browse.php)

und wählen Sie dort `02 LA: Determinantenberechnung` aus. Wählen Sie dann `Mit
zufälligen Parametern starten` aus. Fangen Sie bei Stufe 1 an. Wenn Sie dreimal
hintereinander eine Aufgabe korrekt gelöst haben, gehen Sie zu Stufe 2 weiter.
Sobald Sie auf Stufe 2 dreimal hintereinander eine Aufgabe gelöst haben, gehen
Sie weiter zu Stufe 3.

Hinweis: Die Frage nach der Invertierbarkeit können Sie vorerst ignorieren.
```

## Zusammenfassung und Ausblick

Mit dem Laplaceschen Entwicklungssatz können wir Determinanten beliebig großer
quadratischer Matrizen berechnen, indem wir das Problem schrittweise auf kleinere
Untermatrizen reduzieren. Den Rechenaufwand halten wir gering, indem wir immer
nach der Zeile oder Spalte mit den meisten Nullen entwickeln. Im nächsten Kapitel
lernen wir Rechenregeln kennen, die es erlauben, gezielt Nullen in eine Matrix
einzufügen, und die Determinantenberechnung damit erheblich beschleunigen.
