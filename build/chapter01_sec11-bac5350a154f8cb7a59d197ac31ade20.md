# TODO: Eigenschaften von Determinanten

Die Determinante ist eine Eigenschaft von quadratischen Matrizen, aber sie
selbst hat auch wiederum Eigenschaften und Besonderheiten, die wir hier
notieren. Diese Eigenschaften helfen uns vor allem, die Berechnung von
Determinanten zu vereinfachen.

## Lernziele

```{admonition} Lernziele
:class: attention
Sie kennen die in diesem Kapitel aufgelisteten Eigenschaften von Determinanten
und können die Rechenregeln anwenden.
```

## Determinante Null

* Hat die Matrix eine Zeile oder eine Spalte, die komplett aus Nullen besteht,
  dann ist die Determinante Null.
* Sind zwei Zeilen gleich, ist die Determinante Null.
* Sind zwei Spalten gleich, ist die Determinante Null.

## Determinante von besonderen Matrizen

* Die Determinante der Einheitsmatrix ist Eins.

## Rechenregeln

Die folgenden Rechenregeln für Determinanten gelten für quadratische Matrizen,
d.h. $\mathbf{A}\in\mathbb{R}^{n\times n}$ und $\mathbf{B}\in\mathbb{R}^{n\times
n}$.

* Die Determinante der transponierten Marix ist gleich der Determinanten der
  ursprünglichen Matrix. Es gilt also:
  \begin{equation*} \det(\mathbf{A}^{T}) = \det(\mathbf{A}). \end{equation*}
* Die Determinante eines Produkts von quadratischen Matrizen ist gleich dem
  Produkt der Determinanten der einzelnen Matrizen. Es gilt also:
  \begin{equation*}
  \det(\mathbf{A}\cdot\mathbf{B}) = \det(\mathbf{A})\cdot\det(\mathbf{B}).
  \end{equation*}
* Multipliziert man eine Zeile der Matrix mit einem Skalar, so wird auch die
  Determinante mit diesem Skalar multipliziert. Multipliziert man die gesamte
  Matrix mit diesem Skalar $s$, also jede Zeile der Matrix, dann erhalten wir
  \begin{equation*}
  \det(s\cdot\mathbf{A}) = s^{n}\cdot\det(\mathbf{A}), \quad s\in\mathbb{R}.
  \end{equation*}

* Vertauscht man zwei Zeilen, dann wechselt das Vorzeichen der Determinante.
* Vertauscht man zwei Spalten, dann wechselt das Vorzeichen der Determinante.
* Addiert man das Vielfache einer anderen Zeile(Spalte) zu einer anderen Zeile,
    dann ändert sich die Determinante nicht. Das kann man ausnutzen, um die
    Determinante einer Matrix beispielsweise mit dem Gauß-Algorithmus zu
    berechnen oder viele Nullen in der Matrix zu erzeugen.

Diese und weitere Rechenregeln werden auch in dem folgenden Video erläutert.

```{dropdown} Video "Rechenregeln für Determinanten" von MathePeter
<iframe width="560" height="315" src="https://www.youtube.com/embed/jDerrYHsLcY?si=NQI8V8OeTT034bKN" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Zunächst ist die Determinante nur eine Kennzahl einer quadratischen Matrix. Wir
haben uns in diesem Kapitel mit der Definition und den Rechenregeln beschäftigt.
In den nächsten Kapiteln werden wir die Determinante anwenden um beispielsweise
zu entscheiden, ob eine Matrix invertierbar ist oder um die Eigenwerte und
Eigenvektoren von Matrizen zu berechnen.
