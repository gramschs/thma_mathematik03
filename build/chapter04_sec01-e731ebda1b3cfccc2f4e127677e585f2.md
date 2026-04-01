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
\cos\varphi & -\sin\varphi \\
\sin\varphi &  \cos\varphi
\end{pmatrix}
\end{equation*}

beschrieben. Für $\varphi = 30°$ gilt $\cos(30°) = \frac{\sqrt{3}}{2}$ und
$\sin(30°) = \frac{1}{2}$, also:

\begin{equation*}
\mathbf{R}(30°) =
\begin{pmatrix}
\dfrac{\sqrt{3}}{2} & -\dfrac{1}{2}\\
\dfrac{1}{2}        &  \dfrac{\sqrt{3}}{2}
\end{pmatrix}.
\end{equation*}

Die neue Position des Greifers berechnen wir durch die Matrix-Vektor-Multiplikation,
wie wir sie im Kapitel für lineare Abbildungen eingeführt haben:

\begin{equation*}
\mathbf{R}(30°) \cdot \begin{pmatrix} 1 \\ 0 \end{pmatrix} =
\begin{pmatrix}
\dfrac{\sqrt{3}}{2} & -\dfrac{1}{2}\\
\dfrac{1}{2}        &  \dfrac{\sqrt{3}}{2}
\end{pmatrix}
\cdot
\begin{pmatrix} 1 \\ 0 \end{pmatrix} =
\begin{pmatrix} \dfrac{\sqrt{3}}{2}  \dfrac{1}{2} \end{pmatrix}
\approx
\begin{pmatrix} 0.87\text{m} \\ 0.50\text{m} \end{pmatrix}.
\end{equation*}

Der Greifer befindet sich nach der Drehung bei etwa
$(0.87 \text{m}, 0.50 \text{m})^T$. Das ist ein Punkt im ersten Quadranten, der
den Winkel 30° mit der x-Achse einschließt. Wir prüfen seinen Abstand vom
Gelenk:

\begin{equation*}
\sqrt{\left(\frac{\sqrt{3}}{2}\right)^2 + \left(\frac{1}{2}\right)^2}
= \sqrt{\frac{3}{4} + \frac{1}{4}} = 1 \text{m}.
\end{equation*}

Die Armlänge hat sich nicht verändert. Gilt das wirklich für jeden Vektor
und jeden Drehwinkel, oder ist das ein Zufall für diesen speziellen Startpunkt?
Diese Frage beantworten wir im Abschnitt über geometrische Eigenschaften. Zunächst
schauen wir genauer hin, was an der Matrix $\mathbf{R}(30°)$ so besonders ist.

## Wann nennen wir eine Matrix orthogonal?

Wir betrachten die beiden Spaltenvektoren von $\mathbf{R}(30°)$:

\begin{equation*}
\vec{r}_1 = \begin{pmatrix} \dfrac{\sqrt{3}}{2} \\ \dfrac{1}{2} \end{pmatrix},
\qquad
\vec{r}_2 = \begin{pmatrix} -\dfrac{1}{2} \\ \dfrac{\sqrt{3}}{2} \end{pmatrix}.
\end{equation*}

Wir berechnen ihre Längen:

\begin{align*}
|\vec{r}_1| &= \sqrt{\frac{3}{4} + \frac{1}{4}} = 1,\\
|\vec{r}_2| &= \sqrt{\frac{1}{4} + \frac{3}{4}} = 1.
\end{align*}

Beide Spaltenvektoren haben die Länge 1, sie sind normiert. Zusätzlich berechnen
wir ihr Skalarprodukt:
\begin{equation*}
\vec{r}_1 \cdot \vec{r}_2
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

Man kann genauso gut fordern, dass die Zeilen ein Orthonormalsystem bilden;
beides ist äquivalent.

Die Äquivalenz beider Formulierungen sehen wir direkt: Der $(i,j)$-Eintrag des
Produkts $\mathbf{Q}^T \cdot \mathbf{Q}$ ist das Skalarprodukt des i-ten und
des j-ten Spaltenvektors von $\mathbf{Q}$. Sind diese für $i \neq j$ gleich
Null (Orthogonalität) und für $i = j$ gleich Eins (Normiertheit), so ergibt sich
genau die Einheitsmatrix. Wir bestätigen das für unser Roboterarm-Beispiel durch
explizite Rechnung:

\begin{align*}
\mathbf{R}^T(30°) \cdot \mathbf{R}(30°)
&=
\begin{pmatrix}
\dfrac{\sqrt{3}}{2} &  \dfrac{1}{2}\\
-\dfrac{1}{2}       &  \dfrac{\sqrt{3}}{2}
\end{pmatrix}
\cdot
\begin{pmatrix}
\dfrac{\sqrt{3}}{2} & -\dfrac{1}{2}\\
\dfrac{1}{2}        &  \dfrac{\sqrt{3}}{2}
\end{pmatrix}
&=
\begin{pmatrix}
\dfrac{3}{4} + \dfrac{1}{4} &
-\dfrac{\sqrt{3}}{4} + \dfrac{\sqrt{3}}{4}\\
-\dfrac{\sqrt{3}}{4} + \dfrac{\sqrt{3}}{4} &
\dfrac{1}{4} + \dfrac{3}{4}
\end{pmatrix} =
\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \mathbf{E}.
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

Das ist in der Praxis ein enormer Vorteil. In der Robotersteuerung werden
Koordinatentransformationen mehrere tausend Mal pro Sekunde ausgeführt. Würde man
jedes Mal den Gauß-Jordan-Algorithmus anwenden, wäre die Steuerung zu langsam.
Die Transponierte hingegen ist durch bloßes Vertauschen von Zeilen und Spalten
bestimmt, es fallen keine Multiplikationen oder Divisionen an. Für unser
Roboterarm-Beispiel bedeutet das: Die Rücktransformation, also das Zurückdrehen
um $30°$, ist einfach

\begin{equation*}
\mathbf{R}^{-1}(30°) = \mathbf{R}^T(30°) =
\begin{pmatrix}
\dfrac{\sqrt{3}}{2} &  \dfrac{1}{2}
-\dfrac{1}{2}       &  \dfrac{\sqrt{3}}{2}
\end{pmatrix}.
\end{equation*}
Wir überprüfen das, indem wir die Rücktransformation auf die Greiferposition
$\bigl(\frac{\sqrt{3}}{2},\, \frac{1}{2}\bigr)^T$ anwenden:

\begin{equation*}
\mathbf{R}^T(30°) \cdot
\begin{pmatrix} \dfrac{\sqrt{3}}{2} \dfrac{1}{2} \end{pmatrix}
\begin{pmatrix}
\dfrac{3}{4} + \dfrac{1}{4}
-\dfrac{\sqrt{3}}{4} + \dfrac{\sqrt{3}}{4}
\end{pmatrix}
\begin{pmatrix} 1 \ 0 \end{pmatrix}.
\end{equation*}

Der Greifer befindet sich damit wieder an seiner Ausgangsposition $(1, 0)^T$.

## Was verrät die Determinante über die Art der Transformation?

Nicht alle orthogonalen Matrizen beschreiben Drehungen. Auch Spiegelungen sind
orthogonale Abbildungen. Die Determinante entscheidet, welcher der beiden Fälle
vorliegt.

Wir leiten die möglichen Werte direkt aus der Orthogonalitätsbedingung her. Mit
dem Determinantenmultiplikationssatz gilt:

\begin{align*}
\det(\mathbf{Q}^T \cdot \mathbf{Q}) &= \det(\mathbf{E}) = 1, \
\det(\mathbf{Q}^T) \cdot \det(\mathbf{Q}) &= 1.
\end{align*}

Da $\det(\mathbf{Q}^T) = \det(\mathbf{Q})$ gilt, folgt:

\begin{equation*}
\bigl(\det(\mathbf{Q})\bigr)^2 = 1
\qquad \Longrightarrow \qquad
\det(\mathbf{Q}) = \pm 1.
\end{equation*}

```{admonition} Was verrät die Determinante einer orthogonalen Matrix?
:class: note
Für jede orthogonale Matrix $\mathbf{Q}$ gilt $\det(\mathbf{Q}) = +1$ oder
$\det(\mathbf{Q}) = -1$.

Matrizen mit $\det(\mathbf{Q}) = +1$ beschreiben **Drehungen**
(orientierungserhaltende Transformationen). Matrizen mit
$\det(\mathbf{Q}) = -1$ beschreiben **Spiegelungen**
(orientierungsumkehrende Transformationen).
```

Für unsere Rotationsmatrix berechnen wir:

\begin{equation*}
\det(\mathbf{R}(30°)) =
\frac{\sqrt{3}}{2} \cdot \frac{\sqrt{3}}{2}

\left(-\frac{1}{2}\right) \cdot \frac{1}{2}

= \frac{3}{4} + \frac{1}{4} = 1.
\end{equation*}

Es handelt sich um eine Drehung, was wir geometrisch erwartet hatten. Als
Gegenbeispiel betrachten wir die Spiegelung an der x-Achse, die einen Punkt
$(x, y)^T$ auf $(x, -y)^T$ abbildet:

\begin{equation*}
\mathbf{S} =
\begin{pmatrix}
1 &  0 \
0 & -1
\end{pmatrix}.
\end{equation*}

Wir überprüfen die Orthogonalitätsbedingung:

\begin{equation*}
\mathbf{S}^T \cdot \mathbf{S} =
\begin{pmatrix} 1 & 0 \ 0 & -1 \end{pmatrix}
\cdot
\begin{pmatrix} 1 & 0 \ 0 & -1 \end{pmatrix}
\begin{pmatrix} 1 & 0 \ 0 & 1 \end{pmatrix} = \mathbf{E}.
\end{equation*}

Die Matrix $\mathbf{S}$ ist orthogonal, aber $\det(\mathbf{S}) = -1$. In der
Konstruktion hat dieser Unterschied praktische Konsequenzen: Ein Bauteil, das in
der CAD-Software gespiegelt wird, ändert seine Händigkeit. Ein rechtsgewundenes
Gewinde wird zur linkshändigen Variante, die mit demselben Fertigungsverfahren
nicht hergestellt werden kann.

## Was bleibt bei einer orthogonalen Abbildung erhalten?

### Längen bleiben erhalten

Wir hatten beobachtet, dass der Greifer nach der Drehung noch genau 1 m vom
Gelenk entfernt ist. Das ist kein Zufall für den Startvektor
$(1,0)^T$. Für einen beliebigen Vektor $\vec{v} \in
\mathbb{R}^n$ und eine orthogonale Matrix
$\mathbf{Q}$ zeigen wir:

\begin{align*}
|\mathbf{Q} \cdot \vec{v}|^2
&= (\mathbf{Q} \cdot \vec{v})^T \cdot (\mathbf{Q} \cdot \vec{v}) \
&= \vec{v}^T \cdot \mathbf{Q}^T \cdot \mathbf{Q} \cdot \vec{v} \
&= \vec{v}^T \cdot \mathbf{E} \cdot \vec{v}
= |\vec{v}|^2.
\end{align*}

Also gilt $\|\mathbf{Q} \cdot \vec{v}\| = \|\vec{v}\|$ für jeden Vektor. In der
Technischen Mechanik ist das grundlegend: Wenn wir das Koordinatensystem drehen,
um in Hauptachsenrichtung zu rechnen, dürfen sich die Beträge von Kräften,
Momenten und Geschwindigkeiten nicht ändern. Orthogonale Matrizen garantieren
diese Konsistenz.

### Winkel bleiben erhalten

Auch das Skalarprodukt zweier Vektoren bleibt unter einer orthogonalen Abbildung
erhalten. Für $\vec{u}, \vec{v} \in \mathbb{R}^n$ gilt:

\begin{equation*}
(\mathbf{Q} \cdot \vec{u})^T \cdot (\mathbf{Q} \cdot \vec{v})
= \vec{u}^T \cdot \mathbf{Q}^T \cdot \mathbf{Q} \cdot \vec{v}
= \vec{u}^T \cdot \vec{v}.
\end{equation*}

Da der Winkel $\alpha$ zwischen zwei Vektoren über
$\vec{u} \cdot \vec{v} = \|\vec{u}\|\,\|\vec{v}\|\cos\alpha$ bestimmt wird
und sowohl Längen als auch Skalarprodukte erhalten bleiben, ist der Winkel nach
der Transformation derselbe wie vorher. Zwei Flächen, die in der Konstruktion
senkrecht aufeinanderstehen, sind es nach einer Koordinatendrehung noch immer.

### Flächen und Volumina bleiben erhalten

Da $|\det(\mathbf{Q})| = 1$ gilt, verändert eine orthogonale Abbildung weder
Flächen in 2D noch Volumina in 3D. In der Finite-Elemente-Methode ist das eine
wichtige Konsistenzbedingung: Koordinatentransformationen dürfen die Volumina der
Elemente nicht verfälschen, weil sonst die berechneten Spannungen und Verformungen
unphysikalisch würden.

Die folgende Tabelle fasst alle wesentlichen Eigenschaften zusammen:

| Eigenschaft | Formel | Anwendung im Maschinenbau |
| ----------- | ------ | ------------------------- |
| Orthogonalitätsbedingung | $\mathbf{Q}^T \cdot \mathbf{Q} = \mathbf{E}$ | Überprüfungskriterium |
| Einfache Inverse | $\mathbf{Q}^{-1} = \mathbf{Q}^T$ | Schnelle Rücktransformation in Echtzeit-Steuerungen |
| Determinante | $\det(\mathbf{Q}) = \pm 1$ | +1: Drehung, −1: Spiegelung |
| Längenerhaltung | $\|\mathbf{Q}\vec{v}\| = \|\vec{v}\|$ | Beträge von Kräften und Momenten bleiben erhalten |
| Winkelerhaltung | $(\mathbf{Q}\vec{u})^T(\mathbf{Q}\vec{v}) = \vec{u}^T\vec{v}$ | Rechte Winkel bleiben rechte Winkel |
| Flächen- und Volumenerhaltung | $\lvert\det(\mathbf{Q})\rvert = 1$ | Elementvolumina in der FEM bleiben korrekt |

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir orthogonale Matrizen als die Matrizen kennengelernt,
deren Spaltenvektoren ein Orthonormalsystem bilden. Wir haben drei gleichwertige
Sichtweisen auf diese Eigenschaft erarbeitet: die geometrische (normierte und
paarweise senkrechte Spalten), die algebraische
($\mathbf{Q}^{T}\cdot\mathbf{Q}=\mathbf{E}$) und die praktische
($\mathbf{Q}^{-1}=\mathbf{Q}^{T}$). Die Determinante entscheidet dabei, ob die
Matrix eine Drehung ($\det = +1$) oder eine Spiegelung ($\det = -1$) beschreibt.

Orthogonale Matrizen spielen eine Schlüsselrolle im nächsten großen Thema des
Kurses. Wir werden den Spektralsatz für symmetrische Matrizen kennenlernen, der
besagt, dass sich jede symmetrische Matrix durch eine orthogonale Matrix
diagonalisieren lässt. In der Technischen Mechanik entspricht das der Berechnung
der Hauptachsen des Trägheitstensors: Mit einer geeigneten Drehung des
Koordinatensystems, die genau durch eine orthogonale Matrix beschrieben wird,
lässt sich der Tensor in eine Diagonalmatrix überführen, aus der die
Hauptträgheitsmomente direkt abzulesen sind.
