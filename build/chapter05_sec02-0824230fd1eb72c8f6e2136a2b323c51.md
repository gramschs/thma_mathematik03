---
authors:
  - name: Simone Gramsch
---

# 5.2 Gram-Schmidt-Verfahren

Im vorigen Abschnitt haben wir gesehen, dass orthogonale Matrizen besonders
angenehme Eigenschaften besitzen: Ihre Inverse ist gleich ihrer Transponierten,
und sie erhalten Längen und Winkel. Diese Eigenschaften setzen voraus, dass die
Spalten der Matrix paarweise orthonormal sind. In der Ingenieurpraxis sind
Basisvektoren jedoch selten von vornherein orthogonal: Ein Messsystem liefert
Richtungen, die durch Kalibrierungsfehler leicht schief stehen, oder ein
Berechnungsverfahren erzeugt linear unabhängige Vektoren ohne Orthogonalitätsgarantie.
Das Gram-Schmidt-Verfahren baut aus solchen Vektoren systematisch eine
orthonormale Basis.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können das **Gram-Schmidt-Verfahren** auf linear unabhängige Vektoren
  $\vec{v}_1, \ldots, \vec{v}_n$ anwenden und daraus paarweise orthogonale
  Vektoren $\vec{w}_1, \ldots, \vec{w}_n$ erzeugen.
* [ ] Sie können die orthogonalisierten Vektoren **normieren** und damit eine
  **Orthonormalbasis** konstruieren.
* [ ] Sie verstehen den Unterschied zwischen **Orthogonalisierung** (paarweise
  senkrecht) und **Orthonormalisierung** (paarweise senkrecht und Länge eins).
```

## Warum macht Orthogonalität das Leben leichter?

Wir betrachten das Koordinatensystem eines ebenen Messsensors an einem
Robotergelenk. Der Sensor liefert nach der Kalibrierung zwei Richtungsvektoren:

\begin{equation*}
\vec{v}_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad
\vec{v}_2 = \begin{pmatrix} 3 \\ 1 \end{pmatrix}.
\end{equation*}

Beide Vektoren sind linear unabhängig, spannen also die Ebene auf. Orthogonal
sind sie jedoch nicht: $\vec{v}_1 \cdot \vec{v}_2 = 3 + 1 = 4 \neq 0$. Würde
die Robotersteuerung dieses schiefe System als Basis verwenden, müsste sie bei
jeder Koordinatentransformation die vollständige Inverse der Basismatrix
berechnen. Wären die Basisvektoren dagegen orthonormal, reduziert sich die
Inverse auf die Transponierte, was den Rechenaufwand erheblich senkt und
numerische Fehler vermeidet. *Wie erzeugen wir aus $\vec{v}_1$ und $\vec{v}_2$
ein orthonormales System, das denselben Raum aufspannt?*

## Was ist das Kernprinzip des Verfahrens?

Der Grundgedanke ist einfach: Wir übernehmen den ersten Vektor unverändert und
bauen jeden weiteren so um, dass er zu allen vorherigen senkrecht steht. Dazu
subtrahieren wir von jedem neuen Vektor seinen Anteil in Richtung der bereits
orthogonalisierten Vektoren. Dieser Anteil heißt die **Projektion** von
$\vec{v}$ auf $\vec{w}$:

\begin{equation*}
\text{proj}_{\vec{w}}(\vec{v})
= \frac{\vec{v} \cdot \vec{w}}{\vec{w} \cdot \vec{w}} \cdot \vec{w}.
\end{equation*}

Der Skalar $\frac{\vec{v} \cdot \vec{w}}{\vec{w} \cdot \vec{w}}$ gibt an, wie
viel von $\vec{v}$ in Richtung $\vec{w}$ steckt. Zieht man diesen Anteil ab,
bleibt ein Vektor übrig, der senkrecht auf $\vec{w}$ steht. Wiederholt man das
für jeden neuen Vektor, erhält man das Gram-Schmidt-Verfahren.

```{admonition} Was ist ... das Gram-Schmidt-Verfahren?
:class: note
Gegeben seien $n$ linear unabhängige Vektoren $\vec{v}_1, \ldots, \vec{v}_n$.
Das **Gram-Schmidt-Verfahren** erzeugt daraus $n$ paarweise orthogonale
Vektoren $\vec{w}_1, \ldots, \vec{w}_n$ nach der Vorschrift:

\begin{align*}
\vec{w}_1 &= \vec{v}_1, \\
\vec{w}_k &= \vec{v}_k
  - \sum_{j=1}^{k-1} \frac{\vec{v}_k \cdot \vec{w}_j}{\vec{w}_j \cdot \vec{w}_j}
  \cdot \vec{w}_j, \quad k = 2, 3, \ldots, n.
\end{align*}

Werden die Vektoren abschließend auf die Länge Eins normiert, spricht man von
**Orthonormalisierung**:

\begin{equation*}
\hat{e}_k = \frac{\vec{w}_k}{\|\vec{w}_k\|}.
\end{equation*}
```

## Wie wenden wir das Verfahren auf unser Beispiel an?

Wir kehren zu den Messsensor-Vektoren $\vec{v}_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$
und $\vec{v}_2 = \begin{pmatrix} 3 \\ 1 \end{pmatrix}$ zurück.

**Schritt 1:** Der erste Vektor wird direkt übernommen:

\begin{equation*}
\vec{w}_1 = \vec{v}_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}.
\end{equation*}

**Schritt 2:** Wir subtrahieren vom zweiten Vektor seinen Anteil in Richtung
$\vec{w}_1$. Dazu berechnen wir den Projektionsskalar:

\begin{equation*}
\frac{\vec{v}_2 \cdot \vec{w}_1}{\vec{w}_1 \cdot \vec{w}_1}
= \frac{3 \cdot 1 + 1 \cdot 1}{1^2 + 1^2} = \frac{4}{2} = 2.
\end{equation*}

Damit ergibt sich:

\begin{equation*}
\vec{w}_2 = \vec{v}_2 - 2\,\vec{w}_1
= \begin{pmatrix} 3 \\ 1 \end{pmatrix} - 2\begin{pmatrix} 1 \\ 1 \end{pmatrix}
= \begin{pmatrix} 1 \\ -1 \end{pmatrix}.
\end{equation*}

Wir prüfen die Orthogonalität: $\vec{w}_1 \cdot \vec{w}_2 = 1 \cdot 1 + 1 \cdot (-1) = 0$.
Die beiden Vektoren stehen tatsächlich senkrecht aufeinander.

**Normierung:** Um eine Orthonormalbasis zu erhalten, teilen wir beide Vektoren
durch ihre Länge. Da $\|\vec{w}_1\| = \|\vec{w}_2\| = \sqrt{2}$ gilt:

\begin{equation*}
\hat{e}_1 = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad
\hat{e}_2 = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix}.
\end{equation*}

Schreiben wir $\hat{e}_1$ und $\hat{e}_2$ als Spalten in eine Matrix, entsteht
eine orthogonale Matrix im Sinne von Abschnitt 5.1: $\mathbf{Q}^{-1} = \mathbf{Q}^T$.
Der Robotercontroller kann die Transformation zwischen dem Sensor-Koordinatensystem
und dem Weltkoordinatensystem jetzt mit einer einfachen Matrixtransposition
durchführen, ohne eine vollständige Matrixinversion zu berechnen.

```{dropdown} Video "Gram-Schmidt-Verfahren" von MathePeter
<iframe width="1020" height="574" src="https://www.youtube.com/embed/l6pr1W3MQoE"
title="Orthogonale Basis bestimmen (Gram Schmidt Orthogonalisierungsverfahren)"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media;
gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Das Gram-Schmidt-Verfahren wandelt ein linear unabhängiges Vektorensystem
schrittweise in ein orthogonales und durch anschließende Normierung in ein
orthonormales um. Der Kernschritt ist stets derselbe: Von jedem neuen Vektor
wird seine Projektion auf alle bereits orthogonalisierten Vektoren abgezogen,
sodass der Rest senkrecht auf ihnen steht. Im nächsten Abschnitt wenden wir
uns den Drehmatrizen zu, die eine besonders wichtige Klasse orthogonaler
Matrizen darstellen. Das Gram-Schmidt-Verfahren begegnet uns später erneut:
Wenn wir in Kapitel 6 symmetrische Matrizen diagonalisieren und ein Eigenwert
mehrfach auftritt, benötigen wir es, um die Eigenvektoren im mehrdimensionalen
Eigenraum orthogonalisieren zu können.
