# Orthogonale Matrizen

Orthogonale Matrizen spielen eine wichtige Rolle zur Beschreibung von Drehungen
und Spiegelungen in der Geometrie. In diesem Kapitel werden die Definition und
Eigenschaften orthogonaler Matrizen vorgestellt sowie deren
Anwendungsmöglichkeiten erläutert.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie wissen, was eine **orthogonale** Matrix ist.
* Sie kennen die wichtigsten **Eigenschaften von orthogonalen Matrizen**.
```

## Orthogonale Matrix

Eine quadratische Matrix $\mathbf{Q}\in\mathbb{R}^{n\times n}$ heißt orthogonal,
wenn sie die Bedingung erfüllt:

\begin{equation*}
\mathbf{Q}^{T}\cdot\mathbf{Q} = \mathbf{Q}\cdot\mathbf{Q}^{T} = \mathbf{E},
\end{equation*}

wobei $\mathbf{Q}^{T}$ die Transponierte von $\mathbf{Q}$ ist. Mit $\mathbf{E}$
bezeichnen wir wie üblich die Einheitsmatrix.

Eine orthogonale Matrix hat die Eigenschaft, dass ihre Zeilen- und
Spaltenvektoren paarweise orthonormal sind, d.h. sie sind orthogonal zueinander
und haben jeweils die Länge 1.

Ein Beispiel für eine orthogonale Matrix ist

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}.
\end{equation*}

Um zu überprüfen, ob $\mathbf{A}$ orthogonal ist, müssen wir die Definition
anwenden und zeigen, dass $\mathbf{A}^{T}\cdot\mathbf{A}=\mathbf{E}$ gilt. Wir
berechnen zunächst die transponierte Matrix:

\begin{equation*}
\mathbf{A}^T = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}.
\end{equation*}

Dann multiplizieren wir $\mathbf{A}^{T}$ mit $\mathbf{A}$:

\begin{equation*}
\mathbf{A}^{T}\cdot\mathbf{A} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}
\cdot \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}.
\end{equation*}

Das ergibt

\begin{equation*}
\mathbf{A}^T \cdot\mathbf{A} =
\begin{pmatrix} (0 \cdot 0 + (-1) \cdot (-1)) & (0 \cdot 1 + (-1) \cdot 0) \\
(1 \cdot 0 + 0 \cdot (-1)) & (1 \cdot 1 + 0 \cdot 0) \end{pmatrix}
= \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}.
\end{equation*}

Das Ergebnis ist die Einheitsmatrix der Dimension $2\times 2$. Ein weiteres sehr
bekanntes Beispiel einer orthogonalen Matrix ist die $2\times 2$-Rotationsmatrix

\begin{equation*}
\mathbf{R}(\varphi) =
\begin{pmatrix}\cos(\varphi)&-\sin(\varphi) \\ \sin(\varphi)&\cos(\varphi)\end{pmatrix},
\end{equation*}

die für jeden Winkel $\varphi$ orthogonal ist. Wir bilden zuerst die Transponierte:

\begin{equation*}
\mathbf{R}^T(\varphi) =
\begin{pmatrix} \cos(\varphi) & \sin(\varphi) \\ -\sin(\varphi) & \cos(\varphi) \end{pmatrix}.
\end{equation*}

Das ergibt

\begin{equation*} \begin{split} &\mathbf{R}^T(\varphi)\cdot \mathbf{R}(\varphi) = \\
&= \begin{pmatrix}
\cos^2(\varphi) + \sin^2(\varphi) & \cos(\varphi)(-\sin(\varphi)) + \sin(\varphi) \cos(\varphi) \\
(-\sin(\varphi))\cos(\varphi) + \cos(\varphi)\sin(\varphi) & \sin^2(\varphi) + \cos^2(\varphi)
\end{pmatrix}.
\end{split} \end{equation*}

Die trigonometrischen Terme können weiter vereinfacht werden, denn es gelten:

- $\cos^2(\varphi) + \sin^2(\varphi) = 1$ (trigonometrische Identität)
- $\cos(\varphi)(-\sin(\varphi)) + \sin(\varphi)\cos(\varphi) = 0$
- $(- \sin(\varphi))\cos(\varphi) + \cos(\varphi)\sin(\varphi) = 0$
- $\sin^2(\varphi) + \cos^2(\varphi) = 1$

Somit erhalten wir erneut die $2\times 2$-Einheitsmatrix

\begin{equation*}
\mathbf{R}^T(\varphi)\cdot \mathbf{R}(\varphi) =
\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}.
\end{equation*}

## Eigenschaften von orthogonalen Matrizen

### Längen- und Winkeltreue

Wird eine orthogonale Matrix $\mathbf{Q}$ mit einem Vektor multipliziert, ändert
sich seine Länge nicht. Es gilt also

\begin{equation*}
\|\mathbf{Q}\cdot\vec{x}\| = \|\vec{x}\|.
\end{equation*}

Auch der Winkel zwischen zwei Vektoren bleibt erhalten. Es gilt

\begin{equation*}
\left(\mathbf{Q}\cdot\vec{x}\right) \cdot \left(\mathbf{Q}\cdot\vec{y}\right)
= \vec{x}\cdot\vec{y}.
\end{equation*}

Gemäß der geometrischen Interpretation des Skalarproduktes bleibt der Winkel
also gleich. Diese Eigenschaften von orthogonalen Matrizen werden ausgenutzt, um
Drehungen und Spiegelungen zu beschreiben.

### Determinante orthogonaler Matrizen ist Eins

Die Determinante einer orthogonalen Matrix ist immer $\pm 1$. Eine Determinante
von $1$ bedeutet, dass die Transformation eine Drehung ist, während $−1$ auf
eine Spiegelung hinweist.

### Invertierbarkeit

Jede orthogonale Matrix ist invertierbar, und ihre Inverse ist gleich ihrer
Transponierten:

\begin{equation*}
\mathbf{A}^{-1} = \mathbf{A}^{T}.
\end{equation*}

Diese Eigenschaft und auch die anderen werden in dem folgenden Video demonstriert.

```{dropdown} Video "Orthogonale Matrizen" von MathePeter
<iframe width="560" height="315" src="https://www.youtube.com/embed/X4oTwBusjMk"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir die Definition und Eigenschaften orthogonaler
Matrizen kennengelernt. Orthogonale Matrizen werden insbesondere dann verwendet,
wenn Längen und Winkel unverändert bleiben müssen. Im nächsten Kapitel werden
wir erneut auf das Thema Lösen von linearen Gleichungssystemen zuwenden, diesmal
aber die Matrizenschreibweise benutzen.
