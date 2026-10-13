---
authors:
  - name: Simone Gramsch
---

# 5.4 Drehmatrizen

In Kapitel 5.2 haben wir mit $\mathbf{A}$ eine orthogonale Matrix mit der
Determinante $1$ kennengelernt, die die Ebene um den Ursprung dreht. Um welchen
Winkel, ist offen geblieben. In diesem Kapitel stellen wir die Drehmatrix für
einen beliebigen Winkel auf und beantworten damit auch diese Frage. Im
Maschinenbau stecken Drehmatrizen zum Beispiel hinter dem Drehen eines Bauteils
im CAD-Programm und hinter der Umrechnung zwischen gegeneinander gedrehten
Koordinatensystemen.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können die **Drehmatrix** $\mathbf{D}(\varphi)$ der Ebene aus den
  Bildern der Einheitsvektoren aufstellen.
* [ ] Sie können den Drehwinkel einer Drehmatrix ablesen.
* [ ] Sie können nachweisen, dass jede Drehmatrix orthogonal ist und die
  Determinante $1$ hat.
* [ ] Sie können eine Drehung mit der Transponierten rückgängig machen.
* [ ] Sie wissen, dass sich bei zwei Drehungen der Ebene die Winkel addieren
  und die Reihenfolge keine Rolle spielt.
```

## Wie dreht eine Matrix die Ebene?

In Kapitel 4.1 haben wir die Drehung um $90^\circ$ gegen den Uhrzeigersinn
kennengelernt. Sie bringt $\vec{e}_1$ auf $\vec{e}_2$ und $\vec{e}_2$ auf
$-\vec{e}_1$, und weil die Spalten einer Matrix die Bilder der
Einheitsvektoren sind, gehört zu ihr die Matrix

\begin{equation*}
\begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}.
\end{equation*}

*Wie sieht die Matrix für einen beliebigen Winkel $\varphi$ aus?* Wir gehen
genauso vor und fragen, wohin die Einheitsvektoren wandern. Der Vektor
$\vec{e}_1$ hat die Länge $1$, seine Spitze liegt also auf dem Einheitskreis.
Nach der Drehung um $\varphi$ schließt er mit der $x$-Achse den Winkel
$\varphi$ ein, und aus Mathematik 1 wissen wir, dass der Punkt des
Einheitskreises zu diesem Winkel die Koordinaten $\cos\varphi$ und
$\sin\varphi$ hat.

Den Vektor $\vec{e}_2$ erreichen wir von $\vec{e}_1$ aus durch eine
Vierteldrehung gegen den Uhrzeigersinn. Weil sich die ganze Ebene starr
mitdreht, gilt das auch für die Bilder. Das Bild von $\vec{e}_2$ entsteht also
aus $(\cos\varphi, \sin\varphi)^{\top}$ durch die Drehung um $90^\circ$. Nach
der Matrix oben vertauscht diese Drehung die beiden Komponenten und ändert das
Vorzeichen der neuen ersten Komponente, genau wie beim senkrechten Vektor in
Kapitel 5.2. Das Bild von $\vec{e}_2$ ist damit
$(-\sin\varphi, \cos\varphi)^{\top}$, wie die folgende Abbildung zeigt.

```{figure} pics/drehung_einheitsvektoren.svg
---
name: drehung_einheitsvektoren
---
Darstellung der Einheitsvektoren und ihrer Bilder bei einer Drehung um den
Winkel $\varphi$ gegen den Uhrzeigersinn.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Schreiben wir die beiden Bilder als Spalten in eine Matrix, erhalten wir die
gesuchte Matrix der Drehung um $\varphi$. Zur Probe setzen wir $\varphi = 90^\circ$
ein. Mit $\cos 90^\circ = 0$ und $\sin 90^\circ = 1$ entsteht wieder die Matrix
aus Kapitel 4.1.

```{admonition} Was ist ... eine Drehmatrix?
:class: note
Die Drehung der Ebene um den Ursprung um den Winkel $\varphi$ gegen den
Uhrzeigersinn hat die **Drehmatrix**

\begin{equation*}
\mathbf{D}(\varphi) =
\begin{pmatrix} \cos\varphi & -\sin\varphi \\ \sin\varphi & \cos\varphi \end{pmatrix}.
\end{equation*}

Ihre Spalten sind die Bilder von $\vec{e}_1$ und $\vec{e}_2$. Bei einem
negativen Winkel dreht sie im Uhrzeigersinn.
```

Jetzt können wir die offene Frage aus Kapitel 5.2 beantworten. *Hat die Matrix
$\mathbf{A}$ die Form einer Drehmatrix?* Wir ziehen den Faktor $\frac{1}{5}$ in
die Matrix hinein:

\begin{equation*}
\mathbf{A} = \frac{1}{5}\begin{pmatrix} 3 & -4 \\ 4 & 3 \end{pmatrix}
= \begin{pmatrix} \frac{3}{5} & -\frac{4}{5} \\[2pt] \frac{4}{5} & \frac{3}{5} \end{pmatrix}.
\end{equation*}

Auf der Diagonalen steht zweimal derselbe Wert, und die beiden anderen Einträge
unterscheiden sich nur im Vorzeichen. Mit $\cos\varphi = \frac{3}{5}$ und
$\sin\varphi = \frac{4}{5}$ ist also $\mathbf{A} = \mathbf{D}(\varphi)$, und
der Taschenrechner liefert $\varphi = \arccos\frac{3}{5} \approx 53{,}13^\circ$.
Den Kosinus allein dürfen wir dabei nicht nehmen, denn auch $-53{,}13^\circ$
hat den Kosinus $\frac{3}{5}$. Erst das positive Vorzeichen von
$\sin\varphi = \frac{4}{5}$ zeigt, dass $\mathbf{A}$ gegen den Uhrzeigersinn
dreht. Zur Probe nehmen wir $\vec{x} = (1, 2)^{\top}$ und sein Bild
$\mathbf{A}\vec{x} = (-1, 2)^{\top}$ aus Kapitel 5.2. Beide haben die Länge
$\sqrt{5}$, und für den Winkel zwischen ihnen gilt
$\cos\varphi = \frac{-1 + 4}{\sqrt{5}\cdot\sqrt{5}} = \frac{3}{5}$.

## Warum ist jede Drehmatrix orthogonal?

Für $\mathbf{A}$ haben wir in Kapitel 5.2 nachgerechnet, dass die Spalten
orthonormal sind. *Gilt das für jeden Drehwinkel?* Wir berechnen für
$\mathbf{D}(\varphi)$ die Längenquadrate der beiden Spalten und ihr
Skalarprodukt:

\begin{align*}
\cos^2\varphi + \sin^2\varphi &= 1, \\
(-\sin\varphi)^2 + \cos^2\varphi &= 1, \\
\cos\varphi\cdot(-\sin\varphi) + \sin\varphi\cdot\cos\varphi &= 0.
\end{align*}

Die ersten beiden Zeilen sind der trigonometrische Pythagoras aus Mathematik 1,
in der dritten heben sich die beiden Summanden auf. Die Spalten sind also für
jeden Winkel orthonormal, und $\mathbf{D}(\varphi)$ ist orthogonal. Das passt
zur Anschauung, denn die Spalten sind die gedrehten Einheitsvektoren, und eine
Drehung ändert weder ihre Längen noch den rechten Winkel zwischen ihnen. Die
Determinante ist

\begin{equation*}
\det(\mathbf{D}(\varphi))
= \cos\varphi\cdot\cos\varphi - (-\sin\varphi)\cdot\sin\varphi
= \cos^2\varphi + \sin^2\varphi = 1,
\end{equation*}

nach Kapitel 4.1 bleibt die Orientierung also immer erhalten. Als orthogonale
Matrix hat $\mathbf{D}(\varphi)$ nach Kapitel 5.2 die Transponierte als
Inverse. Mit $\cos(-\varphi) = \cos\varphi$ und $\sin(-\varphi) = -\sin\varphi$
aus Mathematik 1 erkennen wir in ihr eine bekannte Drehmatrix:

\begin{equation*}
\mathbf{D}(\varphi)^{\top}
= \begin{pmatrix} \cos\varphi & \sin\varphi \\ -\sin\varphi & \cos\varphi \end{pmatrix}
= \begin{pmatrix} \cos(-\varphi) & -\sin(-\varphi) \\ \sin(-\varphi) & \cos(-\varphi) \end{pmatrix}
= \mathbf{D}(-\varphi).
\end{equation*}

Die Inverse dreht also um denselben Winkel zurück, wie wir es von einer
Umkehrabbildung erwarten. *Ist umgekehrt jede orthogonale Matrix mit der
Determinante $1$ eine Drehmatrix?* Die erste Spalte einer orthogonalen
$2\times 2$-Matrix hat die Länge $1$ und hat deshalb wie oben die Komponenten
$\cos\varphi$ und $\sin\varphi$ für einen passenden Winkel $\varphi$. Die
zweite Spalte hat ebenfalls die Länge $1$ und steht senkrecht auf der ersten.
Dafür kommen nur $(-\sin\varphi, \cos\varphi)^{\top}$ und der Gegenvektor
$(\sin\varphi, -\cos\varphi)^{\top}$ in Frage. Im ersten Fall erhalten wir
$\mathbf{D}(\varphi)$, im zweiten eine Matrix mit der Determinante
$-\cos^2\varphi - \sin^2\varphi = -1$, also eine Spiegelung wie die an der
Winkelhalbierenden aus Kapitel 4.1.

```{admonition} Welche Eigenschaften hat eine Drehmatrix?
:class: note
Jede Drehmatrix $\mathbf{D}(\varphi)$ ist orthogonal und hat die Determinante
$1$. Ihre Inverse ist die Drehung um den Winkel $-\varphi$:

\begin{equation*}
\mathbf{D}(\varphi)^{-1} = \mathbf{D}(\varphi)^{\top} = \mathbf{D}(-\varphi).
\end{equation*}

Umgekehrt ist jede orthogonale $2\times 2$-Matrix mit der Determinante $1$
eine Drehmatrix.
```

Für unser Beispiel bedeutet das: $\mathbf{A}^{-1} = \mathbf{A}^{\top}$ ist die
Drehung um $-53{,}13^\circ$. Zur Probe drehen wir den Bildvektor $(-1, 2)^{\top}$
zurück und erhalten

\begin{equation*}
\mathbf{A}^{\top}\begin{pmatrix} -1 \\ 2 \end{pmatrix}
= \frac{1}{5}\begin{pmatrix} 3 & 4 \\ -4 & 3 \end{pmatrix}
\begin{pmatrix} -1 \\ 2 \end{pmatrix}
= \frac{1}{5}\begin{pmatrix} -3 + 8 \\ 4 + 6 \end{pmatrix}
= \begin{pmatrix} 1 \\ 2 \end{pmatrix},
\end{equation*}

also wieder $\vec{x}$. Damit ist auch die Beobachtung aus Kapitel 5.2
bestätigt: Eine längentreue und winkeltreue Abbildung der Ebene, die die
Orientierung erhält, ist eine Drehung.

```{dropdown} Video "Orthogonale Matrizen im R^2" von MathePeter
<iframe width="1020" height="574"
src="https://www.youtube.com/embed/Enj_IYsPfc8?list=PLvBnQVOJXCUEd5Zc4Y5ZcvQkCCglGLXkQ"
title="Orthogonale Matrizen im R^2 | Drehmatrix, Spiegelmatrix (Komplettübersicht)"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media;
gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Was passiert, wenn wir zweimal drehen?

Wir drehen zweimal hintereinander um $45^\circ$ und erwarten insgesamt eine
Drehung um $90^\circ$. Mit $\cos 45^\circ = \sin 45^\circ = \frac{1}{\sqrt{2}}$
ist

\begin{equation*}
\mathbf{D}(45^\circ) = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & -1 \\ 1 & 1 \end{pmatrix}.
\end{equation*}

Nach Kapitel 4.1 gehört zur Hintereinanderausführung das Matrixprodukt. Den
Faktor $\frac{1}{\sqrt{2}}$ ziehen wir aus beiden Matrizen vor das Produkt und
erhalten

\begin{equation*}
\mathbf{D}(45^\circ)\,\mathbf{D}(45^\circ)
= \frac{1}{2}\begin{pmatrix} 1 & -1 \\ 1 & 1 \end{pmatrix}
\begin{pmatrix} 1 & -1 \\ 1 & 1 \end{pmatrix}
= \frac{1}{2}\begin{pmatrix} 0 & -2 \\ 2 & 0 \end{pmatrix}
= \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}.
\end{equation*}

Das ist die Drehung um $90^\circ$ aus dem ersten Abschnitt, die Winkel haben
sich also addiert. Das ist kein Zufall. Das Produkt zweier Drehmatrizen ist
nach der Produktregel aus Kapitel 3.3 wieder orthogonal mit der Determinante
$1 \cdot 1 = 1$ und damit selbst eine Drehmatrix. Ihren Winkel lesen wir am
Bild von $\vec{e}_1$ ab, das erst um den einen und dann um den anderen Winkel
weitergedreht wird. *Kommt es dabei auf die Reihenfolge an?* Bei Scherung und
Spiegelung in Kapitel 4.1 war das so. Bei zwei Drehungen ist die Summe der
Winkel in beiden Reihenfolgen dieselbe.

```{admonition} Was passiert bei zwei Drehungen nacheinander?
:class: note
Drehen wir die Ebene erst um den Winkel $\alpha$ und dann um den Winkel
$\beta$, so drehen wir sie insgesamt um $\alpha + \beta$:

\begin{equation*}
\mathbf{D}(\beta)\,\mathbf{D}(\alpha) = \mathbf{D}(\alpha + \beta)
= \mathbf{D}(\alpha)\,\mathbf{D}(\beta).
\end{equation*}

Zwei Drehungen der Ebene dürfen wir also vertauschen.
```

Wir prüfen das an unserem Beispiel und drehen erst mit $\mathbf{A}$ und dann um
$45^\circ$ und umgekehrt. Die Vorfaktoren $\frac{1}{5}$ und $\frac{1}{\sqrt{2}}$
ziehen wir wieder vor das Produkt:

\begin{align*}
\mathbf{D}(45^\circ)\,\mathbf{A}
&= \frac{1}{5\sqrt{2}}\begin{pmatrix} 1 & -1 \\ 1 & 1 \end{pmatrix}
\begin{pmatrix} 3 & -4 \\ 4 & 3 \end{pmatrix}
= \frac{1}{5\sqrt{2}}\begin{pmatrix} -1 & -7 \\ 7 & -1 \end{pmatrix}, \\
\mathbf{A}\,\mathbf{D}(45^\circ)
&= \frac{1}{5\sqrt{2}}\begin{pmatrix} 3 & -4 \\ 4 & 3 \end{pmatrix}
\begin{pmatrix} 1 & -1 \\ 1 & 1 \end{pmatrix}
= \frac{1}{5\sqrt{2}}\begin{pmatrix} -1 & -7 \\ 7 & -1 \end{pmatrix}.
\end{align*}

Beide Reihenfolgen liefern dieselbe Matrix, und das muss die Drehung um
$53{,}13^\circ + 45^\circ = 98{,}13^\circ$ sein. Zur Probe liefert der
Taschenrechner $\cos 98{,}13^\circ \approx -0{,}141$ und
$\sin 98{,}13^\circ \approx 0{,}990$, und genau das sind
$-\frac{1}{5\sqrt{2}}$ und $\frac{7}{5\sqrt{2}}$.

*Gilt das auch im Raum?* Dort drehen wir um eine Achse. Bei einer Drehung um
die $z$-Achse dreht sich die $xy$-Ebene wie bisher, und die $z$-Komponente
bleibt unverändert. In der Matrix steht deshalb unsere Drehmatrix links oben:

\begin{equation*}
\mathbf{D}_z(\varphi) =
\begin{pmatrix} \cos\varphi & -\sin\varphi & 0 \\ \sin\varphi & \cos\varphi & 0 \\ 0 & 0 & 1 \end{pmatrix}.
\end{equation*}

Entsprechend gibt es Drehungen um die $x$-Achse und um die $y$-Achse. Anders
als in der Ebene kommt es im Raum aber auf die Reihenfolge an. Das können wir
mit einem Buch ausprobieren, das flach vor uns auf dem Tisch liegt. Kippen wir
es erst um $90^\circ$ um eine waagerechte Achse und drehen es dann um $90^\circ$
um die senkrechte Achse, liegt es am Ende anders als bei umgekehrter
Reihenfolge. Drehungen im Raum vertiefen wir in diesem Kurs nicht weiter.

```{dropdown} Video "Orthogonale Matrizen im R^3" von MathePeter
<iframe width="1020" height="574"
src="https://www.youtube.com/embed/-Zp-hz7XevM?list=PLvBnQVOJXCUEd5Zc4Y5ZcvQkCCglGLXkQ"
title="Orthogonale Matrizen im R^3 | Drehmatrix, Spiegelmatrix, Drehspiegelmatrix (Komplettübersicht)"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media;
gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Die Drehmatrix $\mathbf{D}(\varphi)$ hat als Spalten die gedrehten
Einheitsvektoren $(\cos\varphi, \sin\varphi)^{\top}$ und
$(-\sin\varphi, \cos\varphi)^{\top}$. Sie ist orthogonal mit der Determinante
$1$, und umgekehrt ist jede orthogonale $2\times 2$-Matrix mit der Determinante
$1$ eine Drehmatrix. Rückgängig machen wir eine Drehung mit der Transponierten,
und bei zwei Drehungen addieren sich die Winkel in beliebiger Reihenfolge.
Unsere Matrix $\mathbf{A}$ aus Kapitel 5.2 dreht die Ebene um etwa
$53{,}13^\circ$. In Kapitel 6 suchen wir Vektoren, die eine Matrix nur
streckt, ohne ihre Richtung zu ändern. Bei einer Drehung um $53{,}13^\circ$
gibt es keinen solchen Vektor, und wir werden sehen, woran die Rechnung das
erkennt.
