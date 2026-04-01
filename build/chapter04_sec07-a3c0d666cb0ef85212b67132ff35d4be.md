# Berechnung der Eigenvektoren

```{admonition} Hinweis
:class: warning
Dieses Vorlesungsskript befindet sich gerade in Bearbeitung.
```

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können zu einem gegebenen Eigenwert $\lambda_i$ den zugehörigen
  **Eigenvektor** berechnen, indem Sie das homogene lineare Gleichungssystem
  $(\mathbf{A} - \lambda_i\mathbf{E})\vec{v} = \vec{0}$ lösen.
* [ ] Sie wissen, dass Eigenvektoren **nicht eindeutig bestimmt** sind: Jedes
  skalare Vielfache eines Eigenvektors ist ebenfalls ein Eigenvektor zum selben
  Eigenwert.
* [ ] Sie können Eigenvektoren **normieren**, sodass sie die Länge Eins haben.
* [ ] Sie kennen den Begriff des **Eigenraums**
  $\text{Eig}_{\mathbf{A}}(\lambda) = \text{Kern}(\mathbf{A} - \lambda\mathbf{E})$
  und wissen, dass er alle Eigenvektoren zum Eigenwert $\lambda$ enthält.
```

## Wie werden die Eigenvektoren für 2x2-Matrizen berechnet?

Ist ein Eigenwert $\lambda$ gefunden, so lassen sich die zugehörigen
Eigenvektoren $\vec{v}$ berechnen, indem das Gleichungssystem

$$
(\mathbf{A} - \lambda \mathbf{E}) \vec{v} = \vec{0}
$$

gelöst wird. Dies führt auf ein lineares Gleichungssystem, dessen Lösungen die
Eigenvektoren der Matrix $\mathbf{A}$ sind.

Wir demonstrieren die Vorgehensweise an dem Beispiel aus dem letzten Kapitel.
Mit Hilfe der charakteristischen Gleichung haben wir bereits zu der Matrix

$$\mathbf{A} = \begin{pmatrix} 6 & 2 \\ 2 & 3 \end{pmatrix}.$$

die beiden Eigenwerte $\lambda_1 = 7$ und $\lambda_2 = 2$ gefunden. Zu jedem
dieser beiden Eigenwerte wird nun der dazugehörige Eigenvektor berechnet.

### Eigenvektor zu $\lambda_1 = 7$

Das Gleichungssystem lautet:

$$
(\mathbf{A} - 7 \mathbf{E}) \vec{v}_{1} = \vec{0}.
$$

Die Matrix $\mathbf{A} - 7 \mathbf{E}$ ist:

$$
\mathbf{A} - 7 \mathbf{E} =
\begin{pmatrix} 6 - 7 & 2 \\ 2 & 3 - 7 \end{pmatrix} =
\begin{pmatrix} -1 & 2 \\ 2 & -4 \end{pmatrix}.
$$

Somit müssen wir das lineare Gleichungssystem

$$
\begin{pmatrix} -1 & 2 \\ 2 & -4 \end{pmatrix} \cdot
\begin{pmatrix} x \\ y \end{pmatrix} =
\begin{pmatrix} 0 \\ 0 \end{pmatrix}
$$

lösen. Dies ergibt zwei Gleichungen:

\begin{align*}
-1 x + 2 y &= 0 \quad \text{(I)}\\
2 x - 4 y &= 0 \quad \text{(II)}
\end{align*}

Gleichung (I) lösen wir nach $x$ auf:

$$x = 2 y.$$

Setzen wir dies in Gleichung (II) ein:

$$
2 (2 y) - 4 y = 0 \quad \Rightarrow \quad 4 y - 4 y = 0.
$$

Dies ist immer erfüllt, wir haben unendlich viele Lösungen. Daher wählen wir
einen Parameter $s$ für $y$, also

$$y = s,$$

was $x = 2s$ ergibt. Die Menge aller Eigenvektoren zu $\lambda_1 = 7$ ist also

$$
\vec{v}_1 = s\cdot\begin{pmatrix} 2 \\ 1 \end{pmatrix}.
$$

### Eigenvektor zu $\lambda_2 = 2$

Das Gleichungssystem lautet:

$$(\mathbf{A} - 2 \mathbf{E}) \vec{v}_{2} = \vec{0}.$$

Die Matrix $\mathbf{A} - 2 \mathbf{E}$ ist:

$$
\mathbf{A} - 2 \mathbf{E} =
\begin{pmatrix} 6 - 2 & 2 \\ 2 & 3 - 2 \end{pmatrix} =
\begin{pmatrix} 4 & 2 \\ 2 & 1 \end{pmatrix}.
$$

Das lineare Gleichungssystem lautet

$$
\begin{pmatrix} 4 & 2 \\ 2 & 1 \end{pmatrix} \cdot
\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}.
$$

Dies ergibt zwei Gleichungen:

\begin{align*}
4 x + 2 y &= 0 \quad \text{(I)}\\
2 x + 1 y &= 0 \quad \text{(II)}
\end{align*}

Gleichung (II) lösen wir nach $y$ auf:

$$y = -2 x.$$

Setzen wir dies in Gleichung (I) ein:

$$
4 x + 2 (-2 x) = 0 \quad \Rightarrow \quad 4 x - 4 x = 0.
$$

Dies ist immer erfüllt, daher wählen wir $x = t$, was $y = -2 t$ ergibt.

Der Eigenvektor zu $\lambda_2 = 2$ ist also

$$
\vec{v}_2 = t\cdot\begin{pmatrix} 1 \\ -2 \end{pmatrix}.
$$

In dem folgenden Video wird ein weiteres Beispiel gerechnet.

```{dropdown} Video "Eigenwerte, Eigenvektoren 2x2" von Daniel Jung
<iframe width="560" height="315" src="https://www.youtube.com/embed/Rr0aa7oo5u8"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Wie werden die Eigenvektoren für 3x3-Matrizen berechnet?

Sobald die Eigenwerte $\lambda_1, \lambda_2, \lambda_3$ gefunden sind, können
die zugehörigen Eigenvektoren durch Lösen des Gleichungssystems

$$
(\mathbf{A} - \lambda \mathbf{E})\cdot\vec{v} = \vec{0}
$$

bestimmt werden. Für jeden Eigenwert $\lambda$ ergibt dieses System eine oder
mehrere Lösungen, die die Eigenvektoren der Matrix darstellen.

Kehren wir zurück zu dem Beispiel

$$ \mathbf{A} = \begin{pmatrix} 5 & -1 & 2 \\ -1 & 5 & 2 \\ 2 & 2 & 2
\end{pmatrix}$$

aus dem letzten Kapitel zurück. Wir hatten die drei Eigenwerte $\{6, 6, 0\}$
ermittelt. Für den Eigenwert $\lambda_1 = 6$ lösen wir das Gleichungssystem:

$$ (\mathbf{A} - 6 \mathbf{E}) \cdot \vec{v} = \vec{0}. $$

Die Matrix $\mathbf{A} - 6 \mathbf{E}$ lautet:

$$ \mathbf{A} - 6 \mathbf{E} = \begin{pmatrix} -1 & -1 & 2 \\ -1 & -1 & 2 \\ 2 &
2 & -4 \end{pmatrix}.$$

Durch Lösen des linearen Gleichungssystems erhalten wir den Eigenvektor

$$\vec{v}_1 = \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}.$$

Wir haben diesmal darauf verzichtet, die Menge alle Eigenvektoren mit einem
Parameter darszustellen, sondern stattdessen einen Repräsentanten gewählt. Alle
weiteren Eigenvektoren zu $\lambda_1 = 6$ sind Vielfache von $\vec{v}_1$.

Für $\lambda_2 = 6$ und $\lambda_3 = 0$ führen wir ähnliche Berechnungen durch
und erhalten die Eigenvektoren

$$\vec{v}_2 = \begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix}
\; \text{ und } \;
\vec{v}_3 = \begin{pmatrix} -1 \\ -1 \\ 2 \end{pmatrix}.$$

Ein weiteres Beispiel wird in dem folgenden Video vorgerechnet.

```{dropdown} Video "Eigenwerte und Eigenvektoren berechnen" von Mathematrick
<iframe width="560" height="315" src="https://www.youtube.com/embed/72nXOF8KxEg"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```
