# Gram-Schmidt-Verfahren

Im letzten Kapitel haben wir orthogonale Matrizen kennengelernt und gesehen,
dass ihre Spalten paarweise orthonormal sind. In der Ingenieurpraxis arbeiten
wir jedoch häufig mit Koordinatensystemen, die aus messtechnischen oder
konstruktiven Gründen nicht von vornherein orthogonal sind. *Wie verwandeln
wir ein beliebiges, linear unabhängiges Koordinatensystem in ein orthonormales?*
Das Gram-Schmidt-Verfahren liefert genau diese Antwort.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können das **Gram-Schmidt-Verfahren** auf eine Menge linear unabhängiger
  Vektoren $\vec{v}_1, \ldots, \vec{v}_n$ anwenden, um daraus paarweise orthogonale
  Vektoren $\vec{w}_1, \ldots, \vec{w}_n$ zu erzeugen, die denselben Vektorraum
  aufspannen.
* [ ] Sie können das Gram-Schmidt-Verfahren zur **Orthonormalisierung** verwenden,
  indem Sie die orthogonalisierten Vektoren abschließend normieren.
* [ ] Sie verstehen den Unterschied zwischen **Orthogonalisierung** (paarweise
  senkrecht) und **Orthonormalisierung** (paarweise senkrecht und normiert).
```

## Warum brauchen wir orthonormale Basen?

In der Finite-Elemente-Methode und in der Strukturmechanik werden
Verschiebungsfelder und Spannungszustände oft in lokalen Koordinatensystemen
beschrieben, die sich von Element zu Element unterscheiden. Wenn diese lokalen
Systeme orthonormal sind, vereinfachen sich die Steifigkeitsmatrizen erheblich:
Transformationsmatrizen werden zu orthogonalen Matrizen, und die Inverse ist
einfach die Transponierte. Das spart Rechenaufwand und vermeidet numerische
Fehler.

Stellen wir uns ein konkretes Beispiel vor. Ein Messsystem liefert uns drei
Richtungsvektoren, die die Hauptrichtungen eines Bauteils beschreiben:

\begin{equation*}
\vec{v}_1 = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}, \quad
\vec{v}_2 = \begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix}, \quad
\vec{v}_3 = \begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix}.
\end{equation*}

Diese drei Vektoren sind linear unabhängig, wie wir mit der Determinante
überprüfen können. Sie sind jedoch nicht orthogonal zueinander: das
Skalarprodukt $\vec{v}_1 \cdot \vec{v}_2 = 1 \neq 0$ zeigt, dass zwischen
den ersten beiden ein von Null verschiedener Winkel besteht. Das
Gram-Schmidt-Verfahren wird uns erlauben, aus diesen drei Vektoren drei
paarweise senkrechte Vektoren zu erzeugen, die denselben Raum aufspannen.

## Was leistet das Gram-Schmidt-Verfahren?

Der Grundgedanke ist einfach: Wir nehmen den ersten Vektor unverändert und
bauen jeden weiteren Vektor so um, dass er zu allen vorherigen senkrecht
steht. Dazu subtrahieren wir von jedem neuen Vektor alle seine Anteile in
Richtung der bereits orthogonalisierten Vektoren. Was übrig bleibt, steht
dann senkrecht auf allen bisherigen.

Diesen Anteil in Richtung eines anderen Vektors nennen wir **Projektion**.
Die Projektion von $\vec{v}$ auf einen Vektor $\vec{w}$ ist derjenige Anteil
von $\vec{v}$, der in Richtung $\vec{w}$ zeigt:

\begin{equation*}
\text{proj}_{\vec{w}}(\vec{v}) =
\frac{\vec{v} \cdot \vec{w}}{\vec{w} \cdot \vec{w}} \cdot \vec{w}.
\end{equation*}

Der Ausdruck $\frac{\vec{v} \cdot \vec{w}}{\vec{w} \cdot \vec{w}}$ ist ein
Skalar, der angibt, wie viel von $\vec{v}$ in Richtung $\vec{w}$ steckt.
Multipliziert mit $\vec{w}$ ergibt sich der Vektor, der abgezogen werden muss.

```{admonition} Was ist ... das Gram-Schmidt-Verfahren?
:class: note
Gegeben seien $n$ linear unabhängige Vektoren $\vec{v}_1, \ldots, \vec{v}_n$.
Das **Gram-Schmidt-Verfahren** erzeugt daraus $n$ paarweise orthogonale
Vektoren $\vec{w}_1, \ldots, \vec{w}_n$ nach der Vorschrift:

\begin{align*}
\vec{w}_1 &= \vec{v}_1, \\
\vec{w}_k &= \vec{v}_k - \sum_{j=1}^{k-1}
  \frac{\vec{v}_k \cdot \vec{w}_j}{\vec{w}_j \cdot \vec{w}_j} \cdot \vec{w}_j,
  \quad k = 2, 3, \ldots, n.
\end{align*}

Werden die Vektoren abschließend auf die Länge Eins normiert, spricht man von
**Orthonormalisierung**:

\begin{equation*}
\vec{e}_k = \frac{\vec{w}_k}{\|\vec{w}_k\|}.
\end{equation*}
```

## Wie wenden wir das Verfahren konkret an?

Wir wenden das Gram-Schmidt-Verfahren nun auf unser Beispiel an und berechnen
Schritt für Schritt die drei orthogonalen Vektoren.

**Schritt 1:** Der erste Vektor wird direkt übernommen:

\begin{equation*}
\vec{w}_1 = \vec{v}_1 = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}.
\end{equation*}

**Schritt 2:** Vom zweiten Vektor $\vec{v}_2$ subtrahieren wir seinen Anteil
in Richtung $\vec{w}_1$. Dazu berechnen wir zunächst das Skalarprodukt und die
Norm:

\begin{equation*}
\vec{v}_2 \cdot \vec{w}_1 = 1 \cdot 1 + 0 \cdot 1 + 1 \cdot 0 = 1, \quad
\vec{w}_1 \cdot \vec{w}_1 = 1 + 1 + 0 = 2.
\end{equation*}

Damit ergibt sich:

\begin{equation*}
\vec{w}_2 = \vec{v}_2 - \frac{1}{2} \vec{w}_1 =
\begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix} -
\frac{1}{2}\begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix} =
\begin{pmatrix} \frac{1}{2} \\ -\frac{1}{2} \\ 1 \end{pmatrix}.
\end{equation*}

Wir überprüfen die Orthogonalität:
$\vec{w}_1 \cdot \vec{w}_2 = 1 \cdot \frac{1}{2} + 1 \cdot (-\frac{1}{2}) + 0 \cdot 1 = 0$.
Das Ergebnis stimmt.

**Schritt 3:** Vom dritten Vektor $\vec{v}_3$ subtrahieren wir die Anteile in
Richtung $\vec{w}_1$ und $\vec{w}_2$:

\begin{equation*}
\vec{v}_3 \cdot \vec{w}_1 = 0 + 1 + 0 = 1, \quad
\vec{v}_3 \cdot \vec{w}_2 = 0 \cdot \tfrac{1}{2} + 1 \cdot (-\tfrac{1}{2}) + 1 \cdot 1
= \tfrac{1}{2}, \quad
\vec{w}_2 \cdot \vec{w}_2 = \tfrac{1}{4} + \tfrac{1}{4} + 1 = \tfrac{3}{2}.
\end{equation*}

Damit ergibt sich:

\begin{align*}
\vec{w}_3
&= \vec{v}_3 - \frac{1}{2}\vec{w}_1 - \frac{\frac{1}{2}}{\frac{3}{2}}\vec{w}_2 \\ -
&= \begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix}
\frac{1}{2}\begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix} -
\frac{1}{3}\begin{pmatrix} \frac{1}{2} \\ -\frac{1}{2} \\ 1 \end{pmatrix} \\
&= \begin{pmatrix} 0 - \frac{1}{2} - \frac{1}{6} \\ 1 - \frac{1}{2} + \frac{1}{6} \\ 1 - 0 - \frac{1}{3} \end{pmatrix}
= \begin{pmatrix} -\frac{2}{3} \\ \frac{2}{3} \\ \frac{2}{3} \end{pmatrix}.
\end{align*}

Eine abschließende Probe zeigt: $\vec{w}_1 \cdot \vec{w}_3 = -\frac{2}{3} + \frac{2}{3} = 0$
und $\vec{w}_2 \cdot \vec{w}_3 = \frac{1}{2} \cdot (-\frac{2}{3}) + (-\frac{1}{2}) \cdot \frac{2}{3} + 1 \cdot \frac{2}{3} = -\frac{1}{3} - \frac{1}{3} + \frac{2}{3} = 0$.

Alle drei Vektoren stehen paarweise senkrecht aufeinander.

## Wie normieren wir die orthogonalen Vektoren?

Die Orthonormalisierung ist der letzte Schritt: Wir teilen jeden Vektor durch
seine Länge. Das liefert die Einheitsvektoren

\begin{align*}
\vec{e}_1 &= \frac{\vec{w}_1}{\|\vec{w}_1\|} = \frac{1}{\sqrt{2}}
\begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}, \\
\vec{e}_2 &= \frac{\vec{w}_2}{\|\vec{w}_2\|} = \frac{1}{\sqrt{3/2}}
\begin{pmatrix} \frac{1}{2} \\ -\frac{1}{2} \\ 1 \end{pmatrix}
= \frac{1}{\sqrt{6}}
\begin{pmatrix} 1 \\ -1 \\ 2 \end{pmatrix}, \\
\vec{e}_3 &= \frac{\vec{w}_3}{\|\vec{w}_3\|} = \frac{3}{2\sqrt{3}}
\begin{pmatrix} -\frac{2}{3} \\ \frac{2}{3} \\ \frac{2}{3} \end{pmatrix}
= \frac{1}{\sqrt{3}}
\begin{pmatrix} -1 \\ 1 \\ 1 \end{pmatrix}.
\end{align*}

Diese drei Vektoren bilden eine orthonormale Basis des $\mathbb{R}^3$. Schreiben
wir sie als Spalten in eine Matrix, erhalten wir eine orthogonale Matrix im
Sinne von Kapitel 4.1. Das Gram-Schmidt-Verfahren ist damit ein konstruktives
Werkzeug, um orthogonale Matrizen aus beliebigen linear unabhängigen Vektoren
aufzubauen. In der Regelungstechnik und der Robotik wird genau dieser Schritt
genutzt, um lokale Koordinatensysteme numerisch zu stabilisieren.

*Und was passiert, wenn wir statt eines lokalen Koordinatensystems eines Bauteils
die Schwingungsformen einer Struktur betrachten? Dann begegnen wir einem noch
tieferen Zusammenhang zwischen orthogonalen Basen und Matrizen, den wir in den
Kapiteln über Eigenwerte und Eigenvektoren aufdecken werden.*

```{dropdown} Video "Gram Schmidt" von Mathematrick
<iframe width="1020" height="574" src="https://www.youtube.com/embed/oJkqxWrQM88"
title="Gram Schmidt Verfahren Beispiel - Orthogonalisierungsverfahren mit 3 Vektoren"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

```{dropdown} Video "Gram Schmidt" von MathePeter
<iframe width="1020" height="574" src="https://www.youtube.com/embed/l6pr1W3MQoE"
title="Orthogonale Basis bestimmen (Gram Schmidt Orthogonalisierungsverfahren)"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

```{dropdown} Video "Gram-Schmidt" von The Bright Side of Mathematics
<iframe width="1020" height="566" src="https://www.youtube.com/embed/sqwVvJL3WTw"
title="Gram-Schmidt (Gram-Schmidt&#39;sches Orthonormalisierungsverfahren)" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture;
web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Das Gram-Schmidt-Verfahren wandelt ein linear unabhängiges Vektorensystem
schrittweise in ein orthogonales oder orthonormales um. Der Kernschritt ist die
Projektion: Von jedem neuen Vektor werden die bereits berechneten Richtungen
abgezogen. Das Ergebnis ist eine orthonormale Basis, aus der sich eine
orthogonale Matrix zusammensetzen lässt.

Im nächsten Abschnitt werden wir eine besonders wichtige Klasse orthogonaler
Matrizen genauer untersuchen: die Drehmatrizen. Sie beschreiben Rotationen in
der Ebene und treten in der Kinematik von Roboterarmen und in der
Koordinatentransformation von Messsystemen auf.
