---
authors:
  - name: Simone Gramsch
---

# 6.3 Berechnung der Eigenvektoren

Im vorigen Abschnitt haben wir die Eigenwerte einer Matrix als Nullstellen des
charakteristischen Polynoms berechnet. Für den Spannungstensor eines Bauteils
lieferte das die Hauptspannungen. Jetzt beantworten wir die nächste Frage: In
welchen Richtungen treten diese Hauptspannungen auf? Diese Richtungen sind die
Eigenvektoren, und ihre Berechnung führt auf ein homogenes lineares
Gleichungssystem der Art, die wir in Kapitel 3 beim Kern einer Matrix
kennengelernt haben.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können zu einem gegebenen Eigenwert $\lambda_i$ die zugehörigen
  **Eigenvektoren** berechnen, indem Sie das homogene lineare Gleichungssystem
  $(\mathbf{A} - \lambda_i \mathbf{E})\vec{v} = \vec{0}$ lösen.
* [ ] Sie kennen den Begriff des **Eigenraums**
  $\text{Eig}_{\mathbf{A}}(\lambda) = \text{Kern}(\mathbf{A} - \lambda\mathbf{E})$
  und wissen, dass Eigenvektoren nicht eindeutig bestimmt sind.
* [ ] Sie können Eigenvektoren auf die Länge Eins **normieren**.
* [ ] Sie kennen den Unterschied zwischen **algebraischer Vielfachheit**
  $m_\lambda$ und **geometrischer Vielfachheit** $d_\lambda$ und wissen, dass
  stets $1 \leq d_\lambda \leq m_\lambda$ gilt.
* [ ] Sie wissen, dass bei symmetrischen Matrizen stets $d_\lambda = m_\lambda$
  gilt und Eigenvektoren zu verschiedenen Eigenwerten orthogonal sind.
```

## Wie führt der Eigenwert auf den Eigenvektor?

Sei $\lambda$ ein bekannter Eigenwert der Matrix $\mathbf{A}$. Wir suchen alle
Vektoren $\vec{v} \neq \vec{0}$, für die $\mathbf{A}\vec{v} = \lambda\vec{v}$
gilt. Wir bringen alles auf eine Seite und klammern aus:

\begin{equation*}
(\mathbf{A} - \lambda\mathbf{E})\,\vec{v} = \vec{0}.
\end{equation*}

Das ist ein homogenes lineares Gleichungssystem. Da $\lambda$ eine Nullstelle des
charakteristischen Polynoms ist, gilt $\det(\mathbf{A} - \lambda\mathbf{E}) = 0$:
Die Koeffizientenmatrix ist nicht invertierbar und besitzt damit einen nichttrivialen
Kern. Genau dieser Kern enthält die gesuchten Eigenvektoren.

```{admonition} Was ist ... der Eigenraum?
:class: note
Sei $\lambda$ ein Eigenwert der Matrix $\mathbf{A} \in \mathbb{R}^{n \times n}$.
Der **Eigenraum** zum Eigenwert $\lambda$ ist

\begin{equation*}
\text{Eig}_{\mathbf{A}}(\lambda)
= \text{Kern}(\mathbf{A} - \lambda\mathbf{E})
= \{\,\vec{v} \in \mathbb{R}^n \mid (\mathbf{A} - \lambda\mathbf{E})\vec{v} = \vec{0}\,\}.
\end{equation*}

Er enthält den Nullvektor und alle Eigenvektoren zu $\lambda$. Jedes von null
verschiedene skalare Vielfache eines Eigenvektors ist ebenfalls ein Eigenvektor
zum selben Eigenwert: Eigenvektoren sind nicht eindeutig bestimmt.
```

Der Eigenraum ist also der Kern einer bestimmten Matrix, und das Verfahren aus
Kapitel 3 zur Kernberechnung liefert unmittelbar die Eigenvektoren. In der
Festigkeitslehre entsprechen die Eigenvektoren des Spannungstensors den
Hauptspannungsrichtungen: Auf den zu diesen Richtungen gehörenden Schnittflächen
wirken ausschließlich Normalspannungen, keine Schubspannungen.

## Das vollständige Beispiel: Eigenvektoren der 2×2-Matrix

Wir setzen das Beispiel aus Abschnitt 5.2 fort. Die symmetrische Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 6 & 2 \\ 2 & 3 \end{pmatrix}
\end{equation*}

hat die Eigenwerte $\lambda_1 = 7$ und $\lambda_2 = 2$. Wir lösen für jeden
Eigenwert das homogene System $(\mathbf{A} - \lambda_i\mathbf{E})\vec{v} = \vec{0}$.

Für $\lambda_1 = 7$ lautet die Koeffizientenmatrix:

\begin{equation*}
\mathbf{A} - 7\mathbf{E} = \begin{pmatrix} -1 & 2 \\ 2 & -4 \end{pmatrix}.
\end{equation*}

Beide Zeilen sind proportional, das System hat nur eine unabhängige Gleichung:
$-v_1 + 2v_2 = 0$, also $v_1 = 2v_2$. Mit dem freien Parameter $v_2 = s$:

\begin{equation*}
\vec{v}_1 = s\begin{pmatrix} 2 \\ 1 \end{pmatrix}, \quad s \neq 0.
\end{equation*}

Probe: $\mathbf{A}\vec{v}_1 = \begin{pmatrix} 12 + 2 \\ 4 + 3 \end{pmatrix}
= \begin{pmatrix} 14 \\ 7 \end{pmatrix} = 7 \cdot \begin{pmatrix} 2 \\ 1 \end{pmatrix}$.
Das Ergebnis stimmt.

Für $\lambda_2 = 2$ lautet die Koeffizientenmatrix:

\begin{equation*}
\mathbf{A} - 2\mathbf{E} = \begin{pmatrix} 4 & 2 \\ 2 & 1 \end{pmatrix}.
\end{equation*}

Aus der zweiten Zeile folgt $v_2 = -2v_1$. Mit dem freien Parameter $v_1 = t$:

\begin{equation*}
\vec{v}_2 = t\begin{pmatrix} 1 \\ -2 \end{pmatrix}, \quad t \neq 0.
\end{equation*}

Probe: $\mathbf{A}\vec{v}_2 = \begin{pmatrix} 6 - 4 \\ 2 - 6 \end{pmatrix}
= \begin{pmatrix} 2 \\ -4 \end{pmatrix} = 2 \cdot \begin{pmatrix} 1 \\ -2 \end{pmatrix}$.
Korrekt.

Wir bemerken: $\vec{v}_1 \cdot \vec{v}_2 = 2 \cdot 1 + 1 \cdot (-2) = 0$. Die
beiden Eigenvektoren stehen senkrecht aufeinander, obwohl wir das nicht aktiv
herbeigeführt haben. Das ist kein Zufall, sondern eine Konsequenz der Symmetrie
der Matrix. Für symmetrische Matrizen stehen Eigenvektoren zu verschiedenen
Eigenwerten immer senkrecht aufeinander. Den Beweis führen wir in Abschnitt 5.4.

Normieren wir die Eigenvektoren auf Länge Eins, erhalten wir:

\begin{equation*}
\hat{v}_1 = \frac{1}{\sqrt{5}}\begin{pmatrix} 2 \\ 1 \end{pmatrix}, \quad
\hat{v}_2 = \frac{1}{\sqrt{5}}\begin{pmatrix} 1 \\ -2 \end{pmatrix}.
\end{equation*}

Interpretiert als ebenen Spannungstensor mit $\sigma_{xx} = 6~\text{MPa}$,
$\sigma_{yy} = 3~\text{MPa}$ und $\tau_{xy} = 2~\text{MPa}$ geben $\hat{v}_1$
und $\hat{v}_2$ die Hauptspannungsrichtungen an. Auf der zu $\hat{v}_1$ senkrechten
Schnittfläche wirkt die größte Normalspannung $\sigma_1 = 7~\text{MPa}$ ohne
jede Schubspannungskomponente.

```{dropdown} Video "Eigenwerte und Eigenvektoren berechnen" von MathePeter
<iframe width="1020" height="574"
src="https://www.youtube.com/embed/YMC_-87gbR8?list=PLvBnQVOJXCUF0BfLnT5kOu3N8ueAXSscb"
title="Eigenwerte und Eigenvektoren berechnen + wichtige Eigenschaften von EW&amp;EV"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media;
gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Was bedeutet es, wenn ein Eigenwert mehrfach auftritt?

Bisher hatte jeder Eigenwert genau einen unabhängigen Eigenvektor. *Was passiert,
wenn ein Eigenwert mehrfach als Nullstelle des charakteristischen Polynoms auftritt?*
Dann müssen wir zwischen zwei Zählweisen unterscheiden.

```{admonition} Algebraische und geometrische Vielfachheit
:class: note
Sei $\lambda$ ein Eigenwert der Matrix $\mathbf{A}$.

Die **algebraische Vielfachheit** $m_\lambda$ ist die Vielfachheit von $\lambda$
als Nullstelle des charakteristischen Polynoms $p(\lambda)$.

Die **geometrische Vielfachheit** $d_\lambda$ ist die Dimension des Eigenraums:

\begin{equation*}
d_\lambda = \dim\!\bigl(\text{Eig}_{\mathbf{A}}(\lambda)\bigr)
= \dim\!\bigl(\text{Kern}(\mathbf{A} - \lambda\mathbf{E})\bigr).
\end{equation*}

Es gilt stets $1 \leq d_\lambda \leq m_\lambda$. Ist $d_\lambda < m_\lambda$
für mindestens einen Eigenwert, heißt die Matrix **defekt**.
```

Wir sehen das an einem 3×3-Beispiel. Die symmetrische Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 5 & -1 & 2 \\ -1 & 5 & 2 \\ 2 & 2 & 2 \end{pmatrix}
\end{equation*}

hat das charakteristische Polynom $p(\lambda) = -\lambda(\lambda - 6)^2$, also
den einfachen Eigenwert $\lambda_3 = 0$ ($m_0 = 1$) und den doppelten Eigenwert
$\lambda_{1,2} = 6$ ($m_6 = 2$).

Für $\lambda_{1,2} = 6$ lautet die Koeffizientenmatrix:

\begin{equation*}
\mathbf{A} - 6\mathbf{E} =
\begin{pmatrix} -1 & -1 & 2 \\ -1 & -1 & 2 \\ 2 & 2 & -4 \end{pmatrix}.
\end{equation*}

Alle drei Zeilen sind Vielfache voneinander, das System hat nur eine unabhängige
Gleichung: $-v_1 - v_2 + 2v_3 = 0$, also $v_1 = -v_2 + 2v_3$. Mit den freien
Parametern $v_2 = s$ und $v_3 = t$ ergibt sich:

\begin{equation*}
\vec{v} = s\begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix} +
t\begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}, \quad s, t \in \mathbb{R}.
\end{equation*}

Der Eigenraum ist zweidimensional: $d_6 = 2 = m_6$. Der doppelte Eigenwert hat
genau so viele unabhängige Eigenvektoren, wie er es algebraisch verspricht.

Für $\lambda_3 = 0$ lösen wir $\mathbf{A}\vec{v} = \vec{0}$ mit dem
Gauß-Algorithmus und erhalten $\vec{v}_3 = \begin{pmatrix} -1 \\ -1 \\ 2
\end{pmatrix}$ mit $d_0 = 1 = m_0$.

Probe: $\mathbf{A}\vec{v}_3
= \begin{pmatrix} -5+1+4 \\ 1-5+4 \\ -2-2+4 \end{pmatrix}
= \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$. Korrekt.

Den problematischen Fall $d_\lambda < m_\lambda$ zeigt die Matrix
$\mathbf{B} = \begin{pmatrix} 3 & 1 \\ 0 & 3 \end{pmatrix}$: Ihr Eigenwert
$\lambda = 3$ hat $m_3 = 2$, der Eigenraum ist jedoch nur eindimensional
($d_3 = 1$). Die Matrix ist defekt. Für alle symmetrischen Matrizen tritt
dieser Fall niemals auf: Dort gilt immer $d_\lambda = m_\lambda$ für alle
Eigenwerte, was wir in Abschnitt 5.4 beweisen werden.

## Zusammenfassung und Ausblick

Zu jedem Eigenwert $\lambda_i$ werden Eigenvektoren durch Lösung des homogenen
Gleichungssystems $(\mathbf{A} - \lambda_i\mathbf{E})\vec{v} = \vec{0}$ bestimmt.
Der zugehörige Eigenraum ist der Kern dieser Matrix und immer mindestens
eindimensional. Für symmetrische Matrizen, wie sie als Spannungstensoren,
Trägheitstensoren und Steifigkeitsmatrizen auftreten, gilt stets
$d_\lambda = m_\lambda$, und Eigenvektoren zu verschiedenen Eigenwerten stehen
immer senkrecht aufeinander. Im nächsten Abschnitt zeigen wir, warum das so ist
und wie es erlaubt, jede symmetrische Matrix durch eine Koordinatentransformation
auf Diagonalgestalt zu bringen.
