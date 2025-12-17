# Rechenregeln inverse Matrizen

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
wird, mit dem Kehrwert multipliziert werden muss.

### Inverse bei symmetrischen Matrizen

Ist eine Matrix symmetrisch, ist ihre inverse Matrix ebenfalls symmetrisch.

Die oben genannten Rechenregeln werden auch in dem folgenden Video erläutert.

```{dropdown} Video "Inverse Matrix, Rechenregeln II" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/6JHgy82gwiI?si=EPTgIjTOjyCvW2qp"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir die Berechnung und Eigenschaften der Inversen von
Matrizen behandelt. Dabei haben wir gesehen, dass die Inverse existiert, wenn
die Determinante ungleich null ist, und wie man sie mit dem Gauß-Algorithmus
berechnet.

Im nächsten Kapitel werden wir orthogonale Matrizen untersuchen, die besondere
Eigenschaften haben, wie die Gleichheit von Transponierter und Inverser. Diese
Matrizen werden beispielsweise in der Robotik eingesetzt, um Rotationen zu
beschreiben.
