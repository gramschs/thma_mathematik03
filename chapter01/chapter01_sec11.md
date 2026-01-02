# TODO: Eigenschaften von Determinanten

Die Determinante ist eine Eigenschaft von quadratischen Matrizen, aber sie
selbst hat auch wiederum Eigenschaften und Besonderheiten, die wir hier
notieren.

1. Die Determinante der Einheitmatrix ist Eins.
2. Die Determinante der transponierten Marix ist gleich der Determinanten der
   ursprünglichen Matrix.
3. Für quadratische Matrizen gleicher Dimension gilt:

   $$\det(\mathbf{A}\cdot\mathbf{B}) = \det(\mathbf{A})\cdot\det(\mathbf{B}).$$
4. Multipliziert man eine Zeile der Matrix mit einem Skalar, so wird auch die
   Determinante mit diesen Skalar multipliziert.
5. Ist $s$ ein Skalar und $\mathbf{A}$ eine quadratische Matrix der Dimension
   $n\times n$, dann gilt:

   \begin{equation*}
   \det(s\cdot\mathbf{A}) = s^{n}\cdot\det(\mathbf{A}).
   \end{equation*}

6. Hat die Matrix eine Zeile oder eine Spalte, die komplett aus Nullen besteht,
   dann ist die Determinante Null.
7. Sind zwei Zeilen gleich, ist die Determinante Null.
8. Sind zwei Spalten gleich, ist die Determinante Null.
9. Vertauscht man zwei Zeilen, dann wechselt das Vorzeichen der Determinante.
10. Vertauscht man zwei Spalten, dann wechselt das Vorzeichen der Determinante.
11. Addiert man das Vielfache einer anderen Zeile(Spalte) zu einer anderen Zeile, dann
    ändert sich die Determinante nicht. Das kann man ausnutzen, um die
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
