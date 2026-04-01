# Orthogonale Matrizen

In Kapitel 3 haben wir lineare Abbildungen als das Werkzeug kennengelernt, mit dem
wir geometrische Transformationen wie Drehungen und Spiegelungen formal
beschreiben können. Stellen wir uns jetzt einen Roboterarm in einer
automatisierten Fertigungsanlage vor: Der Arm dreht sich um sein Gelenk, um ein
Werkstück zu greifen, und das Steuerprogramm muss die neue Greiferposition in
Echtzeit berechnen. Genau für solche Koordinatentransformationen gibt es eine
besondere Klasse von Matrizen, die **orthogonalen Matrizen**. Sie sind nicht
nur besonders einfach zu invertieren, sie stellen auch sicher, dass Längen,
Winkel und Volumina bei der Transformation unverändert bleiben.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie kennen die **Definition einer orthogonalen Matrix**: Eine quadratische
  Matrix $\mathbf{A}$ heißt orthogonal, wenn ihre Spalten normiert und paarweise
  senkrecht aufeinander stehen.
* [ ] Sie kennen die äquivalente Bedingung $\mathbf{A} \cdot \mathbf{A}^T =
  \mathbf{E}$ und können sie zur Überprüfung verwenden.
* [ ] Sie wissen, dass für eine orthogonale Matrix $\mathbf{A}^{-1} = \mathbf{A}^T$
  gilt, und können die Inverse damit ohne Rechnung angeben.
* [ ] Sie wissen, dass $\det(\mathbf{A}) = \pm 1$ für jede orthogonale Matrix gilt.
* [ ] Sie kennen die drei geometrischen Eigenschaften orthogonaler Abbildungen:
  **Längenerhaltung**, **Winkelerhaltung** und **Volumenerhaltung**.
```

## Wie beschreiben wir eine Drehung als Matrixoperation?

Ein Roboterarm dreht sich in der Ebene um $\varphi = 30°$ gegen den
Uhrzeigersinn um sein Gelenk im Ursprung. Im Ruhezustand sitzt der Greifer bei
$(1, 0)^T$ (in Metern), also direkt auf der positiven $x$-Achse, genau
1 m vom Gelenk entfernt. *Wo befindet sich der Greifer nach der
Drehung?*

Eine ebene Drehung um den Winkel $\varphi$ um den Ursprung wird durch die
Rotationsmatrix

\begin{equation*}
\mathbf{R}(\varphi) =
\begin{pmatrix}
\cos\varphi & -\sin\varphi \
\sin\varphi &  \cos\varphi
\end{pmatrix}
\end{equation*}

beschrieben. Für $\varphi = 30°$ gilt $\cos 30° = \frac{\sqrt{3}}{2}$ und
$\sin 30° = \frac{1}{2}$, also:

\begin{equation*}
\mathbf{R}(30°) =
\begin{pmatrix}
\dfrac{\sqrt{3}}{2} & -\dfrac{1}{2}
\dfrac{1}{2}        &  \dfrac{\sqrt{3}}{2}
\end{pmatrix}.
\end{equation*}

Die neue Position des Greifers berechnen wir durch die Matrix-Vektor-Multiplikation,
wie wir sie im Kapitel für lineare Abbildungen eingeführt haben:

\begin{equation*}
\mathbf{R}(30°) \cdot \begin{pmatrix} 1 \ 0 \end{pmatrix}
\begin{pmatrix}
\dfrac{\sqrt{3}}{2} & -\dfrac{1}{2}
\dfrac{1}{2}        &  \dfrac{\sqrt{3}}{2}
\end{pmatrix}
\cdot
\begin{pmatrix} 1 \ 0 \end{pmatrix}
\begin{pmatrix} \dfrac{\sqrt{3}}{2}  \dfrac{1}{2} \end{pmatrix}
\approx
\begin{pmatrix} 0{,}87,\text{m} \ 0{,}50,\text{m} \end{pmatrix}.
\end{equation*}

Der Greifer befindet sich nach der Drehung bei etwa
(0,87 m, 0,50 m)$^T$. Das ist ein Punkt im ersten
Quadranten, der den Winkel 30° mit der x-Achse einschließt. Wir prüfen
seinen Abstand vom Gelenk:

\begin{equation*}
\sqrt{\left(\frac{\sqrt{3}}{2}\right)^2 + \left(\frac{1}{2}\right)^2}
= \sqrt{\frac{3}{4} + \frac{1}{4}} = 1,\text{m}.
\end{equation*}

Die Armlänge hat sich nicht verändert. Gilt das wirklich für jeden Vektor
und jeden Drehwinkel, oder ist das ein Zufall für diesen speziellen Startpunkt?
Diese Frage beantworten wir im Abschnitt über geometrische Eigenschaften. Zunächst
schauen wir genauer hin, was an der Matrix $\mathbf{R}(30°)$ so besonders ist.

## Wann nennen wir eine Matrix orthogonal?

Wir betrachten die beiden Spaltenvektoren von $\mathbf{R}(30°)$:

\begin{equation*}
\vec{q}_1 = \begin{pmatrix} \dfrac{\sqrt{3}}{2} \dfrac{1}{2} \end{pmatrix},
\qquad
\vec{q}_2 = \begin{pmatrix} -\dfrac{1}{2} \dfrac{\sqrt{3}}{2} \end{pmatrix}.
\end{equation*}

Wir berechnen ihre Längen:

\begin{align*}
|\vec{q}_1| &= \sqrt{\frac{3}{4} + \frac{1}{4}} = 1,
|\vec{q}_2| &= \sqrt{\frac{1}{4} + \frac{3}{4}} = 1.
\end{align*}

Beide Spaltenvektoren haben die Länge 1, sie sind normiert. Zusätzlich berechnen
wir ihr Skalarprodukt:
\begin{equation*}
\vec{q}_1 \cdot \vec{q}_2
= \frac{\sqrt{3}}{2} \cdot \left(-\frac{1}{2}\right) + \frac{1}{2} \cdot
\frac{\sqrt{3}}{2}
= -\frac{\sqrt{3}}{4} + \frac{\sqrt{3}}{4} = 0.
\end{equation*}
Die Spaltenvektoren stehen also senkrecht aufeinander. Normiert und paarweise
senkrecht: Eine solche Menge von Vektoren nennen wir ein Orthonormalsystem.
Matrizen, deren Spaltenvektoren ein Orthonormalsystem bilden, haben einen eigenen
Namen.

```{admonition} Was ist ... eine orthogonale Matrix?
:class: note
Eine quadratische Matrix $\mathbf{Q} \in \mathbb{R}^{n \times n}$ heißt
**orthogonal**, wenn ihre Spaltenvektoren paarweise senkrecht zueinander stehen
und alle die Länge 1 haben.

Äquivalent gilt: $\mathbf{Q}$ ist genau dann orthogonal, wenn

\begin{equation*}
\mathbf{Q}^T \cdot \mathbf{Q} = \mathbf{E}
\end{equation*}

gilt, wobei $\mathbf{E}$ die Einheitsmatrix bezeichnet.
```

Die Äquivalenz beider Formulierungen sehen wir direkt: Der (i,j)-Eintrag des
Produkts $\mathbf{Q}^T \cdot \mathbf{Q}$ ist das Skalarprodukt des i-ten und
des j-ten Spaltenvektors von $\mathbf{Q}$. Sind diese für $i \neq j$ gleich
Null (Orthogonalität) und für $i = j$ gleich Eins (Normiertheit), so ergibt sich
genau die Einheitsmatrix. Wir bestätigen das für unser Roboterarm-Beispiel durch
explizite Rechnung:

\begin{align*}
\mathbf{R}^T(30°) \cdot \mathbf{R}(30°)
&=
\begin{pmatrix}
\dfrac{\sqrt{3}}{2} &  \dfrac{1}{2}
-\dfrac{1}{2}       &  \dfrac{\sqrt{3}}{2}
\end{pmatrix}
\cdot
\begin{pmatrix}
\dfrac{\sqrt{3}}{2} & -\dfrac{1}{2}
\dfrac{1}{2}        &  \dfrac{\sqrt{3}}{2}
\end{pmatrix}
&=
\begin{pmatrix}
\dfrac{3}{4} + \dfrac{1}{4} &
-\dfrac{\sqrt{3}}{4} + \dfrac{\sqrt{3}}{4}
-\dfrac{\sqrt{3}}{4} + \dfrac{\sqrt{3}}{4} &
\dfrac{1}{4} + \dfrac{3}{4}
\end{pmatrix}
\begin{pmatrix} 1 & 0 \ 0 & 1 \end{pmatrix} = \mathbf{E}.
\end{align*}

Die Matrix $\mathbf{R}(30°)$ ist damit orthogonal. Dieser Befund gilt für jeden
Winkel $\varphi$: Die Rotationsmatrix $\mathbf{R}(\varphi)$ ist stets orthogonal,
weil die Terme im Produkt dank des trigonometrischen Pythagoras
$\cos^2\varphi + \sin^2\varphi = 1$ immer zur Einheitsmatrix zusammenfallen.

## Warum ist die Inverse so leicht zu berechnen?

Aus $\mathbf{Q}^T \cdot \mathbf{Q} = \mathbf{E}$ folgt unmittelbar, dass
$\mathbf{Q}^T$ die Inverse von $\mathbf{Q}$ ist. Wir erinnern uns:
Eine Matrix $\mathbf{B}$ heißt die Inverse von $\mathbf{Q}$, wenn
$\mathbf{B} \cdot \mathbf{Q} = \mathbf{E}$ gilt. Genau diese Bedingung erfüllt
$\mathbf{Q}^T$ nach Definition.

```{admonition} Wie ... berechnen wir die Inverse einer orthogonalen Matrix?
:class: note
Ist $\mathbf{Q}$ eine orthogonale Matrix, so gilt

\begin{equation*}
\mathbf{Q}^{-1} = \mathbf{Q}^T.
\end{equation*}

Die Inverse einer orthogonalen Matrix ist gleich ihrer Transponierten und kann
damit ohne Rechenaufwand abgelesen werden.
```

