---
authors:
  - name: Simone Gramsch
---

# 5.4 Drehmatrizen

```{admonition} Dieses Kapitel wird gerade überarbeitet
:class: warning
Das Skript wird gerade an den neuen Zeitplan angepasst. Dieses Kapitel ist
rechtzeitig vor der zugehörigen Vorlesung fertig überarbeitet. Bis dahin können
sich Aufbau und Inhalt noch ändern.
Vorerst stehen hier die bisherigen Kapitel 5.3 und 5.4 hintereinander.
```

## Drehmatrizen im R²

Orthogonale Matrizen mit Determinante $+1$ beschreiben Drehungen. Das klingt
zunächst abstrakt, ist aber in der Ingenieurpraxis allgegenwärtig: In der
Robotik muss die Position eines Greifers nach einer Drehbewegung berechnet
werden, in der Messtechnik werden Koordinatensysteme von Sensoren auf das
Maschinensystem transformiert, und in der Technischen Mechanik werden Spannungen
aus einem schräg orientierten Schnitt in das globale Koordinatensystem
zurückgerechnet. In diesem Abschnitt lernen wir die Drehmatrix für die Ebene
kennen.

### Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie kennen die **Drehmatrix im $\mathbb{R}^2$** für eine Drehung um den
  Winkel $\varphi$ gegen den Uhrzeigersinn:
  \begin{equation*}
  \mathbf{D}(\varphi) = \begin{pmatrix} \cos\varphi & -\sin\varphi \\
  \sin\varphi & \cos\varphi \end{pmatrix}.
  \end{equation*}
* [ ] Sie können überprüfen, dass jede Drehmatrix eine orthogonale Matrix ist.
* [ ] Sie wissen, dass $\det(\mathbf{D}) = 1$ gilt, und können dies geometrisch
  begründen: Drehungen erhalten Längen, Winkel und Orientierung.
* [ ] Sie können die Drehmatrix anwenden, um einen Vektor oder ein Bauteilprofil
  um einen gegebenen Winkel zu drehen.
```

### Was soll eine Drehmatrix leisten?

Stellen wir uns den ebenen Roboterarm einer Fräsmaschine vor. Der Arm hat die
Länge $r = 5~\text{cm}$ und zeigt zunächst in die positive $x$-Richtung. Die
Spitze befindet sich also im Punkt

\begin{equation*}
\vec{p} = \begin{pmatrix} 5 \\ 0 \end{pmatrix}~\text{cm}.
\end{equation*}

Die Steuerung dreht den Arm um den Winkel $\varphi = 45°$ gegen den
Uhrzeigersinn. *Wo befindet sich die Spitze danach?* Geometrisch liegt die
Antwort auf der Hand: auf einem Kreis mit Radius $5~\text{cm}$, im Winkel
$45°$ zur $x$-Achse. In Koordinaten ausgedrückt:

\begin{equation*}
\vec{p}' = \begin{pmatrix} 5\cos 45° \\ 5\sin 45° \end{pmatrix} =
\begin{pmatrix} \frac{5}{\sqrt{2}} \\ \frac{5}{\sqrt{2}} \end{pmatrix} \approx
\begin{pmatrix} 3.54 \\ 3.54 \end{pmatrix}~\text{cm}.
\end{equation*}

Die geometrische Überlegung funktioniert, solange wir wissen, in welchem Winkel
der Ausgangsvektor zur $x$-Achse liegt. Für einen allgemeinen Startvektor
benötigen wir eine systematischere Methode. Genau das liefert die Drehmatrix.

### Woher kommt die Formel für die Drehmatrix?

Liegt ein Vektor $\vec{v} = \begin{pmatrix} x \\ y \end{pmatrix}$ vor, so liegt
er in einem Winkel $\alpha$ zur $x$-Achse mit $x = r\cos\alpha$ und
$y = r\sin\alpha$, wobei $r = \|\vec{v}\|$. Nach einer Drehung um $\varphi$
gegen den Uhrzeigersinn zeigt er in den Winkel $\alpha + \varphi$:

\begin{align*}
x' &= r\cos(\alpha + \varphi) = r\cos\alpha\cos\varphi - r\sin\alpha\sin\varphi
     = x\cos\varphi - y\sin\varphi, \\
y' &= r\sin(\alpha + \varphi) = r\cos\alpha\sin\varphi + r\sin\alpha\cos\varphi
     = x\sin\varphi + y\cos\varphi.
\end{align*}

Diese beiden Gleichungen lassen sich elegant als Matrixprodukt schreiben:

\begin{equation*}
\begin{pmatrix} x' \\ y' \end{pmatrix} =
\begin{pmatrix} \cos\varphi & -\sin\varphi \\ \sin\varphi & \cos\varphi \end{pmatrix}
\begin{pmatrix} x \\ y \end{pmatrix}.
\end{equation*}

Die Matrix auf der rechten Seite ist die gesuchte Drehmatrix.

```{admonition} Was ist ... die Drehmatrix im $\mathbb{R}^2$?
:class: note
Die **Drehmatrix** für eine Drehung um den Winkel $\varphi$ gegen den Uhrzeigersinn
ist:

\begin{equation*}
\mathbf{D}(\varphi) = \begin{pmatrix} \cos\varphi & -\sin\varphi \\
\sin\varphi & \cos\varphi \end{pmatrix}.
\end{equation*}

Für einen Vektor $\vec{v} \in \mathbb{R}^2$ liefert das Matrixprodukt
$\vec{v}' = \mathbf{D}(\varphi)\cdot\vec{v}$ den um $\varphi$ gedrehten Vektor.
```

Wir wenden die Drehmatrix auf unser Roboterarm-Beispiel an. Mit $\varphi = 45°$
und $\vec{p} = \begin{pmatrix} 5 \\ 0 \end{pmatrix}$ ergibt sich:

\begin{equation*}
\mathbf{D}(45°)\cdot\vec{p} =
\begin{pmatrix} \cos 45° & -\sin 45° \\ \sin 45° & \cos 45° \end{pmatrix}
\begin{pmatrix} 5 \\ 0 \end{pmatrix} =
\begin{pmatrix} 5\cos 45° \\ 5\sin 45° \end{pmatrix} \approx
\begin{pmatrix} 3.54 \\ 3.54 \end{pmatrix}~\text{cm}.
\end{equation*}

Das stimmt mit unserem geometrischen Ergebnis von oben überein.

### Warum ist die Drehmatrix orthogonal?

Wir überprüfen die Orthogonalitätsbedingung $\mathbf{D}^T\cdot\mathbf{D} = \mathbf{E}$.
Die Transponierte ist:

\begin{equation*}
\mathbf{D}^T(\varphi) = \begin{pmatrix} \cos\varphi & \sin\varphi \\
-\sin\varphi & \cos\varphi \end{pmatrix}.
\end{equation*}

Das Produkt ergibt:

\begin{equation*}
\mathbf{D}^T\cdot\mathbf{D} =
\begin{pmatrix} \cos^2\varphi + \sin^2\varphi & \cos\varphi\sin\varphi - \sin\varphi\cos\varphi \\
-\sin\varphi\cos\varphi + \cos\varphi\sin\varphi & \sin^2\varphi + \cos^2\varphi \end{pmatrix}
= \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \mathbf{E}.
\end{equation*}

Damit ist $\mathbf{D}^{-1} = \mathbf{D}^T = \mathbf{D}(-\varphi)$: Die Umkehrung
einer Drehung um $\varphi$ ist eine Drehung um $-\varphi$. Das ist geometrisch
einleuchtend.

Die Determinante berechnen wir direkt:

\begin{equation*}
\det(\mathbf{D}(\varphi)) = \cos^2\varphi + \sin^2\varphi = 1.
\end{equation*}

Da $\det(\mathbf{D}) = 1 > 0$, ändert sich die Orientierung nicht: ein
rechtshändiges Koordinatensystem bleibt rechtshändig. Wäre die Determinante
$-1$, würde es sich um eine Spiegelung handeln.

### Was passiert bei zwei hintereinander ausgeführten Drehungen?

In der Kinematik eines Roboters werden häufig mehrere Gelenke nacheinander
bewegt. Dreht der Arm zunächst um $\varphi_1$ und dann um $\varphi_2$, so
entspricht das einer Gesamtdrehung um $\varphi_1 + \varphi_2$. Das Assoziativgesetz
der Matrizenmultiplikation erlaubt es, dies kompakt zu schreiben:

\begin{equation*}
\mathbf{D}(\varphi_2)\cdot\mathbf{D}(\varphi_1) = \mathbf{D}(\varphi_1 + \varphi_2).
\end{equation*}

Diese Eigenschaft lässt sich mit dem Additionstheorem für den Kosinus und Sinus
nachrechnen. Für unseren Roboterarm bedeutet das: Eine Drehung um $30°$ gefolgt
von einer Drehung um $60°$ ergibt dasselbe wie eine einzige Drehung um $90°$.

*Und was geschieht, wenn wir in drei Dimensionen drehen wollen? Dann reicht eine
einzige Matrix nicht mehr aus, wie wir im nächsten Abschnitt sehen werden.

```{dropdown} Video "Orthogonale Matrizen, Drehmatrix" von MathePeter
<iframe width="1020" height="574" 
src="https://www.youtube.com/embed/Enj_IYsPfc8?list=PLvBnQVOJXCUEd5Zc4Y5ZcvQkCCglGLXkQ"
title="Orthogonale Matrizen im R^2 | Drehmatrix, Spiegelmatrix (Komplettübersicht)"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

### Zusammenfassung und Ausblick

Die Drehmatrix $\mathbf{D}(\varphi)$ ist eine orthogonale $2\times 2$-Matrix mit
Determinante $1$. Sie dreht jeden Vektor um den Winkel $\varphi$ gegen den
Uhrzeigersinn, ohne seine Länge zu verändern. Aufeinanderfolgende Drehungen
werden durch einfaches Matrizenprodukt kombiniert.

Im nächsten Abschnitt erweitern wir diese Idee auf den dreidimensionalen Raum.
Dort lässt sich eine allgemeine Drehung als Produkt von drei Achsendrehungen
darstellen, die durch die sogenannten Kardanwinkel beschrieben werden. Diese
Darstellung ist in der Luft- und Raumfahrttechnik sowie in der Robotik fundamental.

## Drehmatrizen im R³

In der Ebene genügt ein einziger Winkel, um eine Drehung vollständig zu
beschreiben. Im dreidimensionalen Raum ist das nicht mehr ausreichend. Eine
Turbinenschaufel, ein Robotergelenk oder ein Flugkörper kann um drei
verschiedene Achsen rotieren, und die Reihenfolge dieser Drehungen spielt
dabei eine entscheidende Rolle. Dieses Phänomen begegnet uns in der
Luft- und Raumfahrttechnik ebenso wie in der Robotik und der rechnergestützten
Kinematikanalyse.

### Lernziele

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

### Wie beschreiben wir eine Drehung im Raum?

Wir betrachten eine Messsonde an einem Roboterarm, die im Raum ausgerichtet
werden soll. In der Ausgangsstellung zeigt der Sensor in die positive
$z$-Richtung. Nun soll er zunächst um die $x$-Achse um den Winkel $\alpha$
und anschließend um die $z$-Achse um den Winkel $\gamma$ geschwenkt werden.
Jede dieser Teilbewegungen ist eine Drehung um eine der drei Koordinatenachsen,
und jede lässt sich durch eine eigene $3\times 3$-Matrix beschreiben.

Die Idee ist dieselbe wie in zwei Dimensionen: Eine Drehung um eine Achse
lässt die zugehörige Komponente unverändert und dreht die beiden anderen
Komponenten gemäß der zweidimensionalen Drehmatrix.

### Die drei Grunddrehmatrizen

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

### Wie wenden wir die Drehmatrizen auf unser Beispiel an?

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
ist erhalten: $\|\vec{s}'\| = \sqrt{0.354^2 + 0.354^2 + 0.866^2} \approx 1$.

```{dropdown} Video "Drehmatrizen" von Prof. Hielscher
<iframe width="742" height="613" src="https://www.youtube.com/embed/aXAikhRe6v0?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07" title="Drehmatrizen" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture;
web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

### Warum ist die Reihenfolge der Drehungen wichtig?

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

```{dropdown} Video "Orthogonale Matrizen im R^3" von MathePeter
<iframe width="1020" height="574"
src="https://www.youtube.com/embed/-Zp-hz7XevM?list=PLvBnQVOJXCUEd5Zc4Y5ZcvQkCCglGLXkQ"
title="Orthogonale Matrizen im R^3 | Drehmatrix, Spiegelmatrix, Drehspiegelmatrix (Komplettübersicht)"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

### Zusammenfassung und Ausblick

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
