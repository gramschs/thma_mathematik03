# Berechnung der Eigenwerte

```{admonition} Hinweis
:class: warning
Dieses Vorlesungsskript befindet sich gerade in Bearbeitung.
```

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können die Eigenwerte einer quadratischen Matrix $\mathbf{A}$ berechnen,
  indem Sie das **charakteristische Polynom**
  $p(\lambda) = \det(\mathbf{A} - \lambda\mathbf{E}) = 0$
  aufstellen und lösen.
* [ ] Sie können das charakteristische Polynom für $2\times 2$- und
  $3\times 3$-Matrizen explizit berechnen.
* [ ] Sie wissen, dass eine $n\times n$-Matrix **höchstens $n$ verschiedene
  Eigenwerte** besitzen kann.
* [ ] Sie können die Eigenwerte einer **Diagonal- oder Dreiecksmatrix** direkt
  aus der Diagonalen ablesen, ohne das charakteristische Polynom berechnen
  zu müssen.
```

## Wie werden Eigenwerte für eine 2x2-Matrix berechnet?

Um die Eigenwerte $\lambda$ einer $2 \times 2$-Matrix $\mathbf{A}$ zu berechnen,
muss die **charakteristische Gleichung** gelöst werden. Diese ergibt sich aus
der Determinante der Matrix $\mathbf{A} - \lambda \mathbf{E} $, wobei
$\mathbf{E}$ die Einheitsmatrix ist. Die charakteristische Gleichung lautet:

$$
\det(\mathbf{A} - \lambda \mathbf{E}) = 0.
$$

Für eine Matrix $\mathbf{A} = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$
ergibt sich die charakteristische Gleichung zu:

$$ \det\begin{pmatrix} a - \lambda & b \\ c & d - \lambda \end{pmatrix} = (a -
\lambda)(d - \lambda) - bc = 0. $$

Dies ist eine quadratische Gleichung für $\lambda$, deren Lösungen die
Eigenwerte der Matrix $\mathbf{A}$ sind.

**Beispiel:** Wir betrachten als Beispiel die $2\times 2$-Matrix

$$
\mathbf{A} = \begin{pmatrix} 6 & 2 \\ 2 & 3 \end{pmatrix}.
$$

Zunächst berechnen wir die Eigenwerte $\lambda$ der Matrix $\mathbf{A}$. Dazu
lösen wir die charakteristische Gleichung:

$$
\det(\mathbf{A} - \lambda \mathbf{E}) = 0.
$$

Die Matrix $\mathbf{A} - \lambda \mathbf{E}$ ergibt sich zu

$$
\mathbf{A} - \lambda \mathbf{E} =
\begin{pmatrix} 6 - \lambda & 2 \\ 2 & 3 - \lambda \end{pmatrix}.
$$

Nun berechnen wir die Determinante dieser Matrix:

$$
\det\begin{pmatrix} 6 - \lambda & 2 \\ 2 & 3 - \lambda \end{pmatrix}
= (6 - \lambda)(3 - \lambda) - 2 \cdot 2.
$$

Damit ergibt die charakteristische Gleichung

$$
(6 - \lambda)(3 - \lambda) - 4 =
18 - 9\lambda + \lambda^2 - 4 = \lambda^2 - 9\lambda + 14 = 0.
$$

Diese quadratische Gleichung lösen wir mit der pq-Formel:

\begin{align*}
\lambda_{1/2}
&= \frac{-(-9)}{2} \pm \sqrt{\frac{81}{4} - 14} \\
&= \frac{9}{2} \pm \sqrt{\frac{81-56}{4}} \\
&= \frac{9}{2} \pm \frac{5}{2}.
\end{align*}

Damit erhalten wir die beiden Eigenwerte

$$
\lambda_{1} = \frac{9}{2} + \frac{5}{2} = 7 \; \text{ und } \;
\lambda_{2} = \frac{9}{2} - \frac{5}{2} = 2.
$$

## Wie werden Eigenwerte für $3\times 3$-Matrizen berechnet?

Auch für $3\times 3$-Matrizen bleibt die Definition eines Eigenwertes und von
Eigenvektoren gleich. Eine quadratische Matrix $\mathbf{A} \in \mathbb{R}^{3
\times 3}$ hat einen Eigenvektor $\vec{v} \neq \vec{0}$, wenn gilt:

$$
\mathbf{A} \vec{v} = \lambda \vec{v}.
$$

Dabei ist $\lambda$ ein Eigenwert von $\mathbf{A}$ und $\vec{v}$ ist der
zugehörige Eigenvektor.

Auch die Vorgehensweise bei der Berechnung der Eigenwerte bleibt gleich. Um die
Eigenwerte einer $3 \times 3$-Matrix zu berechnen, müssen wir die
charakteristische Gleichung lösen. Diese Gleichung ergibt sich aus der
Determinante der Matrix $\mathbf{A} - \lambda \mathbf{E}$, wobei $\mathbf{E}$
die Einheitsmatrix ist:

$$ \det(\mathbf{A} - \lambda \mathbf{E}) = 0. $$

Für eine Matrix

$$\mathbf{A} = \begin{pmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} &
a_{23} \\ a_{31} & a_{32} & a_{33} \end{pmatrix}$$

ergibt sich die charakteristische Gleichung

$$ \det \begin{pmatrix} a_{11} - \lambda & a_{12} & a_{13} \\ a_{21} & a_{22} -
\lambda & a_{23} \\ a_{31} & a_{32} & a_{33} - \lambda \end{pmatrix} = 0. $$

Diese Gleichung ist ein **Polynom dritten Grades** für $\lambda$, dessen
Lösungen die Eigenwerte der Matrix $ \mathbf{A}$ sind. Der einzige Unterschied
zur Berechung der Eigenwerte für $2\times 2$-Matrizen ist also, dass die
charakteristische Gleichung mit einem Polynom dritten anstatt zweiten Grades
gebildet wird.

**Beispiel**: Gegeben sei beispielhaft die Matrix

$$ \mathbf{A} = \begin{pmatrix} 5 & -1 & 2 \\ -1 & 5 & 2 \\ 2 & 2 & 2
\end{pmatrix}. $$

Die charakteristische Gleichung lautet:

$$ \det\begin{pmatrix} 5 - \lambda & -1 & 2 \\ -1 & 5 - \lambda & 2 \\ 2 & 2 & 2
- \lambda \end{pmatrix} = 0.$$

Die Berechnung der Determinante ergibt:

$$ -\lambda^3+12\lambda^2-36\lambda = 0 $$

Es liegt ein Polynom dritten Grades vor, dessen Nullstellen $\lambda_1 = 6$,
$\lambda_2 = 6$ und $\lambda_3 = 0$ die Lösung der charakteristischen Gleichung
und damit die gesuchten Eigenwerte sind.