# Rechenregeln inverse Matrizen

Was eine inverse Matrix ist und wie sie berechnet wird, haben wir im letzten
Kapitel gelernt. In diesem Kapitel werden wir uns damit beschäftigen,
Rechenregeln für inverse Matrizen zu nutzen. Die Rechnregeln helfen uns,
Rechnungen mit inversen Matrizen zu vereinfachen.

## Lernziele

```{admonition} Lernziele
:class: attention
Sie kennen die **Rechenregeln für inverse Matrizen** und können sie anwenden:

* [ ] $\mathbf{E}^{-1} = \mathbf{E}$,
* [ ] $\left(\mathbf{A} \cdot \mathbf{B}\right)^{-1} = \mathbf{B}^{-1} \cdot
  \mathbf{A}^{-1}$,
* [ ] $\left(\mathbf{A}^{-1}\right)^{-1} = \mathbf{A}$,
* [ ] $\left(\mathbf{A}^T\right)^{-1} = (\mathbf{A}^{-1})^T$,
* [ ] $(s \cdot \mathbf{A})^{-1} = \frac{1}{s} \cdot \mathbf{A}^{-1}, \quad s
  \neq 0$.

Darüber hinaus gilt: Die Inverse einer symmetrischen Matrix ist wieder
symmetrisch.

* [ ] Sie können **Matrizengleichungen** der Form $\mathbf{A}\mathbf{X} =
  \mathbf{B}$ und $\mathbf{X}\mathbf{A} = \mathbf{B}$ mit Hilfe der inversen
  Matrix nach $\mathbf{X}$ auflösen und kennen den Unterschied zur gewöhnlichen
  Algebra.
```

Gehen wir die Rechenregeln einzeln durch und erläutern wir sie.

## Eigenschaften und Rechenregeln für inverse Matrizen

Die Inverse einer Matrix hat mehrere nützliche Eigenschaften, die häufig in der
linearen Algebra und in Anwendungen wie der Lösung von linearen
Gleichungssystemen verwendet werden. Im Folgenden listen wir die wichtigsten
Eigenschaften der Inversen einer Matrix auf.

### Inverse der Einheitsmatrix

Die Einheitsmatrix $\mathbf{E}$ ist immer invertierbar, und ihre Inverse ist sie
selbst:

\begin{equation*}
\mathbf{E}^{-1} = \mathbf{E}.
\end{equation*}

Dies gilt für jede quadratische Einheitsmatrix beliebiger Dimension.

### Inverse des Produkts zweier Matrizen

Wenn $\mathbf{A}$ und $\mathbf{B}$ zwei invertierbare Matrizen der gleichen
Dimension sind, dann ist auch das Produkt $\mathbf{A} \cdot \mathbf{B}$
invertierbar, und es gilt:

\begin{equation*}
\left(\mathbf{A} \cdot \mathbf{B}\right)^{-1} = \mathbf{B}^{-1} \cdot \mathbf{A}^{-1}.
\end{equation*}

Die Reihenfolge wird bei der Multiplikation der Inversen umgekehrt. Eine
Eselsbrücke für diese Rechenregel wird in dem folgenden Video gezeigt.

```{dropdown} Video "Inverse Matrix, Rechenregeln I" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/t1K_B1pPqmc?si=TMRR6UnIpu5mmEn4"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

### Inverse der inversen Matrix

Die Inverse einer Matrix ist eindeutig, und die Inverse der inversen Matrix ist
die ursprüngliche Matrix:

\begin{equation*}
\left(\mathbf{A}^{-1}\right)^{-1} = \mathbf{A}.
\end{equation*}

### Inverse der Transponierten

Die Inverse der transponierten Matrix $\mathbf{A}^T$ ist die Transponierte der
Inversen von $\mathbf{A}$:

\begin{equation*}
\left(\mathbf{A}^T\right)^{-1} = (\mathbf{A}^{-1})^T.
\end{equation*}

Das bedeutet, dass die Operationen der Inversion und der Transposition
miteinander vertauschbar sind.

### Inverse bei Skalarmultiplikation

Ist $s$ ein Skalar und $\mathbf{A}$ eine $n \times n$-Matrix, dann gilt für die
Inverse des Produkts von $s$ und $\mathbf{A}$:

\begin{equation*}
(s \cdot \mathbf{A})^{-1} = \frac{1}{s} \cdot \mathbf{A}^{-1}, \quad s \neq 0.
\end{equation*}

Das bedeutet, dass wenn der Skalar $s$ aus der Inversenoperation herausgezogen
wird, mit dem Kehrwert multipliziert werden muss. Dazu muss der Skalar ungleich
Null sein.

### Inverse bei symmetrischen Matrizen

Ist eine Matrix symmetrisch, ist ihre inverse Matrix ebenfalls symmetrisch.

Die oben genannten Rechenregeln werden auch in dem folgenden Video erläutert.

```{dropdown} Video "Inverse Matrix, Rechenregeln II" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/6JHgy82gwiI?si=EPTgIjTOjyCvW2qp"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Matrizengleichungen lösen

Eine wichtige Anwendung der inversen Matrix ist das Lösen von
**Matrizengleichungen**. Das sind Gleichungen, bei denen die Unbekannte selbst
eine Matrix ist, die wir hier $\mathbf{X}$ nennen.

### Gleichung der Form $\mathbf{A}\mathbf{X} = \mathbf{B}$

Ist $\mathbf{A}$ eine invertierbare Matrix, so können wir die Gleichung

\begin{equation*}
\mathbf{A}\mathbf{X} = \mathbf{B}
\end{equation*}

nach $\mathbf{X}$ auflösen, indem wir **von links** mit $\mathbf{A}^{-1}$
multiplizieren:

\begin{equation*}
\mathbf{A}^{-1} \cdot \mathbf{A}\mathbf{X} = \mathbf{A}^{-1} \cdot \mathbf{B}
\quad \Rightarrow \quad
\mathbf{E}\mathbf{X} = \mathbf{A}^{-1}\mathbf{B}
\quad \Rightarrow \quad
\mathbf{X} = \mathbf{A}^{-1}\mathbf{B}.
\end{equation*}

### Gleichung der Form $\mathbf{X}\mathbf{A} = \mathbf{B}$

Steht die Unbekannte $\mathbf{X}$ hingegen auf der linken Seite des Produkts,
also

\begin{equation*}
\mathbf{X}\mathbf{A} = \mathbf{B},
\end{equation*}

so multiplizieren wir **von rechts** mit $\mathbf{A}^{-1}$:

\begin{equation*}
\mathbf{X}\mathbf{A} \cdot \mathbf{A}^{-1} = \mathbf{B} \cdot \mathbf{A}^{-1}
\quad \Rightarrow \quad
\mathbf{X}\mathbf{E} = \mathbf{B}\mathbf{A}^{-1}
\quad \Rightarrow \quad
\mathbf{X} = \mathbf{B}\mathbf{A}^{-1}.
\end{equation*}

```{admonition} Achtung: Reihenfolge beachten!
:class: warning
Im Gegensatz zur gewöhnlichen Algebra mit reellen Zahlen ist die Reihenfolge
bei der Matrizenmultiplikation entscheidend. Es gilt im Allgemeinen

\begin{equation*}
\mathbf{A}^{-1}\mathbf{B} \neq \mathbf{B}\mathbf{A}^{-1}.
\end{equation*}

Daher muss man genau beachten, ob $\mathbf{A}^{-1}$ von links oder von rechts
multipliziert wird. Die Faustregel lautet: Die inverse Matrix wird auf der
**gleichen Seite** multipliziert, auf der $\mathbf{A}$ in der ursprünglichen
Gleichung steht.
```

### Beispiel

Gegeben seien die Matrizen

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}
\quad \text{und} \quad
\mathbf{B} = \begin{pmatrix} 3 & 5 \\ 1 & 3 \end{pmatrix}.
\end{equation*}

**Aufgabe:** Bestimme $\mathbf{X}$ aus $\mathbf{A}\mathbf{X} = \mathbf{B}$.

Zunächst berechnen wir die Inverse von $\mathbf{A}$. Mit $\det(\mathbf{A}) =
2\cdot 1 - 1\cdot 1 = 1$ ergibt sich:

\begin{equation*}
\mathbf{A}^{-1} = \frac{1}{1}\begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix}
= \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix}.
\end{equation*}

Da $\mathbf{A}$ links steht, multiplizieren wir von links mit $\mathbf{A}^{-1}$:

\begin{equation*}
\mathbf{X} = \mathbf{A}^{-1}\mathbf{B} =
\begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix}
\begin{pmatrix} 3 & 5 \\ 1 & 3 \end{pmatrix} =
\begin{pmatrix} 2 & 2 \\ -1 & 1 \end{pmatrix}.
\end{equation*}

Die Probe bestätigt das Ergebnis:

\begin{equation*}
\mathbf{A}\mathbf{X} =
\begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}
\begin{pmatrix} 2 & 2 \\ -1 & 1 \end{pmatrix} =
\begin{pmatrix} 3 & 5 \\ 1 & 3 \end{pmatrix} = \mathbf{B}. \checkmark
\end{equation*}

## Zusammenfassung und Ausblick

Die Rechenregeln für inverse Matrizen vereinfachen so manche Rechnung. Besonders
beim Lösen von Matrizengleichungen ist zu beachten, dass die inverse Matrix stets
auf der richtigen Seite multipliziert werden muss, da die Matrizenmultiplikation
nicht kommutativ ist. In den nächsten Kapiteln werden wir uns mit einer sehr
wichtigen Eigenschaft einer Matrix beschäftigen, der sogenannten Determinante.
