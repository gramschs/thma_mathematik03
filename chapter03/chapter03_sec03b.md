# Eigenwerte und Eigenvektoren von 3x3-Matrizen

In diesem Kapitel werden wir die Berechnung von Eigenwerten und Eigenvektoren
für $3 \times 3$-Matrizen Schritt für Schritt erläutern und praktische Beispiele
vorstellen.

## Lernziele

```{admonition} Lernziele
:class: attention
Sie können die **Eigenwerte** und **Eigenvektoren** einer $3\times 3$-Matrix
berechnen.
```

## Definition von Eigenwerten und Eigenvektoren

Auch für $3\times 3$-Matrizen bleibt die Definition eines Eigenwertes und von
eigenvektoren gleich. Eine quadratische Matrix $\mathbf{A} \in \mathbb{R}^{3
\times 3}$ hat einen Eigenvektor $\vec{v} \neq \vec{0}$, wenn gilt:

\begin{equation*}
\mathbf{A} \vec{v} = \lambda \vec{v}.
\end{equation*}

Dabei ist $\lambda$ ein Eigenwert von $\mathbf{A}$ und $\vec{v}$ ist der
zugehörige Eigenvektor.

## Berechnung der Eigenwerte für $3\times 3$-Matrizen

Auch die Vorgehensweise bei der Berechnung der Eigenwerte bleibt gleich. Um die
Eigenwerte einer $3 \times 3$-Matrix zu berechnen, müssen wir die
**charakteristische Gleichung** lösen. Diese Gleichung ergibt sich aus der
Determinante der Matrix $\mathbf{A} - \lambda \mathbf{E}$, wobei $\mathbf{E}$
die Einheitsmatrix ist:

\begin{equation*}
\det(\mathbf{A} - \lambda \mathbf{E}) = 0.
\end{equation*}

Für eine Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} &
a_{23} \\ a_{31} & a_{32} & a_{33} \end{pmatrix}
\end{equation*}

ergibt sich die charakteristische Gleichung

\begin{equation*}
\det \begin{pmatrix} a_{11} - \lambda & a_{12} & a_{13} \\ a_{21} & a_{22} -
\lambda & a_{23} \\ a_{31} & a_{32} & a_{33} - \lambda \end{pmatrix} = 0.
\end{equation*}

Diese Gleichung ist ein **Polynom dritten Grades** für $\lambda$, dessen
Lösungen die Eigenwerte der Matrix $ \mathbf{A}$ sind. Der einzige Unterschied
zur Berechung der Eigenwerte für $2\times 2$-Matrizen ist also, dass die
charakteristische Gleichung mit einem Polynom dritten anstatt zweiten Grades
gebildet wird.

Gegeben sei beispielhaft die Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 5 & -1 & 2 \\ -1 & 5 & 2 \\ 2 & 2 & 2
\end{pmatrix}.
\end{equation*}

Die charakteristische Gleichung lautet:

\begin{equation*}
\det\begin{pmatrix} 5 - \lambda & -1 & 2 \\ -1 & 5 - \lambda & 2 \\ 2 & 2 & 2 -
\lambda \end{pmatrix} = 0.
\end{equation*}

Die Berechnung der Determinante ergibt:

\begin{equation*}
-\lambda^3+12\lambda^2-36\lambda = 0
\end{equation*}

Es liegt ein Polynom dritten Grades vor, dessen Nullstellen $\lambda_1 = 6$,
$\lambda_2 = 6$ und $\lambda_3 = 0$ die Lösung der charakteristischen Gleichung
und damit die gesuchten Eigenwerte sind.

## Berechnung der Eigenvektoren

Sobald die Eigenwerte $\lambda_1, \lambda_2, \lambda_3$ gefunden sind, können
die zugehörigen Eigenvektoren durch Lösen des Gleichungssystems

\begin{equation*}
(\mathbf{A} - \lambda \mathbf{E})\cdot\vec{v} = \vec{0}
\end{equation*}

bestimmt werden. Für jeden Eigenwert $\lambda$ ergibt dieses System eine oder
mehrere Lösungen, die die Eigenvektoren der Matrix darstellen.

Kehren wir zurück zu dem obigen Beispiel. Für den Eigenwert $\lambda_1 = 6$
lösen wir das Gleichungssystem:

\begin{equation*}
(\mathbf{A} - 6 \mathbf{E}) \cdot \vec{v} = \vec{0}.
\end{equation*}

Die Matrix $\mathbf{A} - 6 \mathbf{E}$ lautet:

\begin{equation*}
\mathbf{A} - 6 \mathbf{E} = \begin{pmatrix} -1 & -1 & 2 \\ -1 & -1 & 2 \\ 2 &
2 & -4 \end{pmatrix}.
\end{equation*}

Durch Lösen des linearen Gleichungssystems erhalten wir den Eigenvektor

\begin{equation*}
\vec{v}_1 = \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}.
\end{equation*}

Wir haben diesmal darauf verzichtet, die Menge alle Eigenvektoren mit einem
Parameter darszustellen, sondern stattdessen einen Repräsentanten gewählt. Alle
weiteren Eigenvektoren zu $\lambda_1 = 6$ sind Vielfache von $\vec{v}_1$.

Für $\lambda_2 = 6$ und $\lambda_3 = 0$ führen wir ähnliche Berechnungen durch
und erhalten die Eigenvektoren

\begin{equation*}
\vec{v}_2 = \begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix}
\; \text{ und } \;
\vec{v}_3 = \begin{pmatrix} -1 \\ -1 \\ 2 \end{pmatrix}.
\end{equation*}

Ein weiteres Beispiel wird in dem folgenden Video vorgerechnet.

```{dropdown} Video "Eigenwerte und Eigenvektoren berechnen" von Mathematrick
<iframe width="560" height="315" src="https://www.youtube.com/embed/72nXOF8KxEg"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir gezeigt, wie die Eigenwerte und Eigenvektoren einer
$3 \times 3$-Matrix berechnet werden. Die Berechnung der Eigenwerte erfolgt
durch das Lösen der charakteristischen Gleichung, während die Eigenvektoren
durch Lösen eines homogenen Gleichungssystems bestimmt werden.
