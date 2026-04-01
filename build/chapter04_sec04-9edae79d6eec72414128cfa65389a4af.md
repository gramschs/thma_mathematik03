# Drehmatrizen im R³

In der Ebene genügt ein einziger Winkel, um eine Drehung vollständig zu
beschreiben. Im dreidimensionalen Raum ist das nicht mehr ausreichend. Eine
Turbinenschaufel, ein Robotergelenk oder ein Flugkörper kann um drei
verschiedene Achsen rotieren, und die Reihenfolge dieser Drehungen spielt
dabei eine entscheidende Rolle. Dieses Phänomen begegnet uns in der
Luft- und Raumfahrttechnik ebenso wie in der Robotik und der rechnergestützten
Kinematikanalyse.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie kennen die **Drehmatrizen um die Koordinatenachsen** im $\mathbb{R}^3$:
  $\mathbf{D}_x(\alpha)$, $\mathbf{D}_y(\beta)$ und $\mathbf{D}_z(\gamma)$.
* [ ] Sie wissen, dass eine allgemeine räumliche Drehung durch Hintereinanderausführung
  dreier Achsendrehungen beschrieben werden kann:
  \begin{equation*}
  \mathbf{D}(\alpha, \beta, \gamma) = \mathbf{D}_x(\alpha)\,\mathbf{D}_y(\beta)\,\mathbf{D}_z(\gamma).
  \end{equation*}
* [ ] Sie kennen den Begriff der **Kardanwinkel** (auch Euler-Winkel genannt) und
  wissen, dass die Reihenfolge der Drehungen das Ergebnis beeinflusst.
* [ ] Sie wissen, dass das Produkt orthogonaler Matrizen wieder eine orthogonale
  Matrix ist, und können dies auf verkettete Drehungen anwenden.
```

## Wie beschreiben wir eine Drehung im Raum?

Wir betrachten eine Messsonde an einem Roboterarm, die im Raum ausgerichtet
werden soll. In der Ausgangsstellung zeigt der Sensor in die positive
$z$-Richtung. Nun soll er zunächst um die $x$-Achse um den Winkel $\alpha$
und anschließend um die $z$-Achse um den Winkel $\gamma$ geschwenkt werden.
Jede dieser Teilbewegungen ist eine Drehung um eine der drei Koordinatenachsen,
und jede lässt sich durch eine eigene $3\times 3$-Matrix beschreiben.

Die Idee ist dieselbe wie in zwei Dimensionen: Eine Drehung um eine Achse
lässt die zugehörige Komponente unverändert und dreht die beiden anderen
Komponenten gemäß der zweidimensionalen Drehmatrix.

## Die drei Grunddrehmatrizen

Eine Drehung um die $x$-Achse um den Winkel $\alpha$ lässt die $x$-Komponente
unverändert und dreht die $yz$-Ebene:

\begin{equation*}
\mathbf{D}_x(\alpha) =
\begin{pmatrix}
1 & 0 & 0 \\
0 & \cos\alpha & -\sin\alpha \\
0 & \sin\alpha & \cos\alpha
\end{pmatrix}.
\end{equation*}

Entsprechend dreht eine Drehung um die $y$-Achse um den Winkel $\beta$ die
$xz$-Ebene und lässt die $y$-Komponente fest:

\begin{equation*}
\mathbf{D}_y(\beta) =
\begin{pmatrix}
\cos\beta & 0 & \sin\beta \\
0 & 1 & 0 \\
-\sin\beta & 0 & \cos\beta
\end{pmatrix}.
\end{equation*}

Zu beachten ist das Vorzeichen: Bei der Drehung um die $y$-Achse erscheint
$\sin\beta$ in der oberen rechten Position und $-\sin\beta$ in der unteren
linken. Das folgt aus der Rechtshändigkeitskonvention des Koordinatensystems.
Schließlich dreht die Drehung um die $z$-Achse um den Winkel $\gamma$ die
$xy$-Ebene:

\begin{equation*}
\mathbf{D}_z(\gamma) =
\begin{pmatrix}
\cos\gamma & -\sin\gamma & 0 \\
\sin\gamma & \cos\gamma & 0 \\
0 & 0 & 1
\end{pmatrix}.
\end{equation*}

Diese drei Matrizen kennen wir bereits strukturell aus Kapitel 4.1: Jede von
ihnen ist eine orthogonale Matrix mit Determinante $1$.

```{admonition} Was ist ... eine räumliche Drehmatrix?
:class: note
Eine **räumliche Drehmatrix** ist eine orthogonale $3\times 3$-Matrix mit
$\det(\mathbf{D}) = 1$. Jede allgemeine Drehung im $\mathbb{R}^3$ kann als
Produkt von drei Grunddrehungen um die Koordinatenachsen geschrieben werden:

\begin{equation*}
\mathbf{D}(\alpha, \beta, \gamma) =
\mathbf{D}_x(\alpha)\cdot\mathbf{D}_y(\beta)\cdot\mathbf{D}_z(\gamma).
\end{equation*}

Die Winkel $\alpha$, $\beta$, $\gamma$ heißen **Kardanwinkel** (oder Euler-Winkel
je nach Konvention). Die Reihenfolge der Matrixmultiplikation legt die
Reihenfolge der Drehungen fest.
```

## Wie wenden wir die Drehmatrizen auf unser Beispiel an?

Zurück zur Messsonde. Der Sensor zeigt zu Beginn in $z$-Richtung:
$\vec{s} = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$. Wir drehen zunächst
um die $x$-Achse um $\alpha = 30°$ und danach um die $z$-Achse um
$\gamma = 45°$.

Schritt 1: Drehung um die $x$-Achse.

\begin{equation*}
\mathbf{D}_x(30°)\cdot\vec{s} =
\begin{pmatrix} 1 & 0 & 0 \\ 0 & \cos 30° & -\sin 30° \\ 0 & \sin 30° & \cos 30° \end{pmatrix}
\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} =
\begin{pmatrix} 0 \\ -\sin 30° \\ \cos 30° \end{pmatrix} \approx
\begin{pmatrix} 0 \\ -0.5 \\ 0.866 \end{pmatrix}.
\end{equation*}

Der Sensor zeigt jetzt schräg nach vorne unten in der $yz$-Ebene.

Schritt 2: Drehung des Ergebnisses um die $z$-Achse.

\begin{equation*}
\mathbf{D}_z(45°)\cdot\begin{pmatrix} 0 \\ -0.5 \\ 0.866 \end{pmatrix} =
\begin{pmatrix} \cos 45° & -\sin 45° & 0 \\ \sin 45° & \cos 45° & 0 \\ 0 & 0 & 1 \end{pmatrix}
\begin{pmatrix} 0 \\ -0.5 \\ 0.866 \end{pmatrix} \approx
\begin{pmatrix} 0.354 \\ -0.354 \\ 0.866 \end{pmatrix}.
\end{equation*}

Wir können beide Schritte auch zur Gesamtdrehmatrix kombinieren:
$\mathbf{D} = \mathbf{D}_z(45°)\cdot\mathbf{D}_x(30°)$. Die Länge des Sensors
ist erhalten: $\|\vec{s}'\| = \sqrt{0{,}354^2 + 0{,}354^2 + 0{,}866^2} \approx 1$.

## Warum ist die Reihenfolge der Drehungen wichtig?

Anders als bei reellen Zahlen gilt für Matrizen im Allgemeinen
$\mathbf{A}\cdot\mathbf{B} \neq \mathbf{B}\cdot\mathbf{A}$. Das hat für
Drehungen im Raum eine direkt spürbare Konsequenz: Erst um $x$, dann um $z$
drehen ergibt eine andere Endlage als erst um $z$, dann um $x$.

Wir überprüfen dies mit einem einfachen Beispiel. Mit dem Einheitsvektor
$\vec{e}_1 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$ und den Winkeln
$90°$ ergibt sich:

\begin{align*}
\mathbf{D}_x(90°)\cdot\mathbf{D}_z(90°)\cdot\vec{e}_1 &=
\mathbf{D}_x(90°)\cdot\begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix} =
\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}, \\
\mathbf{D}_z(90°)\cdot\mathbf{D}_x(90°)\cdot\vec{e}_1 &=
\mathbf{D}_z(90°)\cdot\begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix} =
\begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}.
\end{align*}

Die Endlagen unterscheiden sich. In der Robotik ist die Festlegung der
Drehungsreihenfolge daher eine Konvention, auf die sich alle Beteiligten
einigen müssen. In der Luftfahrt verwendet man typischerweise die Reihenfolge
Gieren, Nicken, Rollen (yaw, pitch, roll) gemäß der DIN-Norm für
Flugzustände.

*Wie hängen diese Drehmatrizen mit den Eigenwerten zusammen? Tatsächlich hat
jede Drehmatrix im $\mathbb{R}^3$ immer den Eigenwert $\lambda = 1$, und der
zugehörige Eigenvektor zeigt genau in die Drehachse. Diese Verbindung werden
wir in den folgenden Abschnitten dieses Kapitels herstellen.*

```{dropdown} Video "Rotationsmatrizen 3D" von MathePeter
<iframe width="560" height="315" src="https://www.youtube.com/embed/iVjFEKKlFfM"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Räumliche Drehungen werden durch orthogonale $3\times 3$-Matrizen mit
Determinante $1$ beschrieben. Jede allgemeine Drehung lässt sich als Produkt
von Grunddrehungen um die drei Koordinatenachsen darstellen. Die Reihenfolge
der Multiplikation ist entscheidend, weil Matrizenmultiplikation nicht
kommutativ ist.

Im nächsten Abschnitt wenden wir uns einem der wichtigsten Konzepte der linearen
Algebra zu: den Eigenwerten und Eigenvektoren. Sie beschreiben diejenigen
Richtungen, die eine Matrixtransformation invariant lässt. In der
Festigkeitslehre entsprechen sie den Hauptspannungsrichtungen, in der
Schwingungsanalyse den Eigenfrequenzen einer Struktur.
