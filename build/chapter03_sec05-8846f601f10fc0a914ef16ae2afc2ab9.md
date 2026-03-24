# Bild und Rang einer Matrix

Wir haben im vorigen Kapitel den Kern einer Matrix kennengelernt: die Menge der
Eingabevektoren, die auf den Nullvektor abgebildet werden. Nun stellen wir die
umgekehrte Frage: Welche Vektoren können überhaupt als Ergebnis einer linearen
Abbildung auftreten? Diese Frage führt zum Begriff des Bildes einer Matrix und
zur damit eng verwandten Größe des Rangs.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie kennen die Definition des **Bildes** einer Matrix und können es geometrisch
  interpretieren.
* Sie wissen, dass das Bild einer Matrix durch die **Spalten der Matrix**
  aufgespannt wird.
* Sie kennen die Definition des **Rangs** einer Matrix als Dimension des Bildes.
* Sie können den Rang einer Matrix bestimmen, indem Sie die Anzahl der linear
  unabhängigen Spalten zählen.
* Sie können überprüfen, ob ein gegebener Vektor im Bild einer Matrix liegt.
```

## Motivation: Welche Vektoren sind erreichbar?

Wir betrachten erneut die Projektionsmatrix auf die $xy$-Ebene:

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}.
\end{equation*}

Welche Vektoren $\vec{w}$ können als Ergebnis $\vec{w} = \mathbf{A} \cdot \vec{v}$
auftreten? Für einen beliebigen Eingabevektor $\vec{v} = \begin{pmatrix} x \\ y \\ z
\end{pmatrix}$ ergibt die Abbildung:

\begin{equation*}
\mathbf{A} \cdot \begin{pmatrix} x \\ y \\ z \end{pmatrix}
= \begin{pmatrix} x \\ y \\ 0 \end{pmatrix}.
\end{equation*}

Das Ergebnis hat immer eine dritte Komponente gleich null. Kein Vektor der Form
$\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$ kann jemals als Ergebnis auftreten.
Die Menge aller erreichbaren Ausgabevektoren ist genau die $xy$-Ebene. Diese Menge
heißt das **Bild** der Matrix.

## Definition des Bildes

```{admonition} Was ist ... das Bild einer Matrix?
:class: note
Sei $F_{\mathbf{A}}: \mathbb{R}^n \to \mathbb{R}^m$ eine lineare Abbildung mit der
Matrix $\mathbf{A} \in \mathbb{R}^{m \times n}$. Das **Bild** von $\mathbf{A}$,
geschrieben $\text{Bild}(\mathbf{A})$, ist die Menge aller Vektoren
$\vec{w} \in \mathbb{R}^m$, die als Ergebnis der Abbildung auftreten können:

\begin{equation*}
\text{Bild}(\mathbf{A}) = \{ \vec{w} \in \mathbb{R}^m \mid \vec{w} = \mathbf{A} \cdot \vec{v}
\text{ für ein } \vec{v} \in \mathbb{R}^n \}.
\end{equation*}
```

## Das Bild als Spaltenraum

Das Bild einer Matrix lässt sich besonders einfach berechnen, wenn man die
Matrix-Vektor-Multiplikation als Linearkombination der Spalten der Matrix schreibt.
Für eine $m \times n$-Matrix $\mathbf{A} = (\vec{a}_1, \vec{a}_2, \ldots, \vec{a}_n)$
mit den Spaltenvektoren $\vec{a}_j$ gilt:

\begin{equation*}
\mathbf{A} \cdot \vec{v}
= \begin{pmatrix} | & | & & | \\ \vec{a}_1 & \vec{a}_2 & \cdots & \vec{a}_n \\ | & | & & | \end{pmatrix}
\cdot \begin{pmatrix} v_1 \\ v_2 \\ \vdots \\ v_n \end{pmatrix}
= v_1 \cdot \vec{a}_1 + v_2 \cdot \vec{a}_2 + \cdots + v_n \cdot \vec{a}_n.
\end{equation*}

Das Ergebnis ist also immer eine Linearkombination der Spalten von $\mathbf{A}$. Das
Bild ist damit genau die Menge aller Linearkombinationen der Spalten, der sogenannte
**Spaltenraum** der Matrix. Das Bild wird durch die Spalten der Matrix aufgespannt.

## Definition und Berechnung des Rangs

Die Dimension des Bildes, also die Anzahl der linear unabhängigen Spalten der Matrix,
heißt **Rang** der Matrix:

```{admonition} Was ist ... der Rang einer Matrix?
:class: note
Der **Rang** einer Matrix $\mathbf{A}$, geschrieben $\text{Rang}(\mathbf{A})$, ist
die Dimension des Bildes von $\mathbf{A}$:

\begin{equation*}
\text{Rang}(\mathbf{A}) = \dim(\text{Bild}(\mathbf{A})).
\end{equation*}

Der Rang entspricht der maximalen Anzahl linear unabhängiger Spalten (oder
gleichwertig: Zeilen) der Matrix.
```

Um das Bild und den Rang zu bestimmen, sucht man die maximal linear unabhängigen
Spalten der Matrix. Diese spannen dann das Bild auf.

## Beispiele

**Beispiel 1:** Für die Diagonalmatrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
\end{equation*}

sind beide Spalten $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$ und $\begin{pmatrix} 0 \\ -1 \end{pmatrix}$
linear unabhängig. Das Bild ist:

\begin{equation*}
\text{Bild}(\mathbf{A}) = x_1 \cdot \begin{pmatrix} 1 \\ 0 \end{pmatrix}
+ x_2 \cdot \begin{pmatrix} 0 \\ -1 \end{pmatrix}, \quad x_1, x_2 \in \mathbb{R}.
\end{equation*}

Da die zwei Spalten linear unabhängig sind und den $\mathbb{R}^2$ aufspannen, ist
$\text{Rang}(\mathbf{A}) = 2$. Die Abbildung trifft jeden Vektor im $\mathbb{R}^2$.

**Beispiel 2:** Für die Projektionsmatrix

\begin{equation*}
\mathbf{C} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}
\end{equation*}

hat die mittlere Spalte nur Nullen. Sie ist daher als Linearkombination der anderen
Spalten darstellbar (mit dem Faktor null). Die beiden übrigen Spalten
$\begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$ und $\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$
sind linear unabhängig. Das Bild ist:

\begin{equation*}
\text{Bild}(\mathbf{C}) = x_1 \cdot \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}
+ x_2 \cdot \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}, \quad x_1, x_2 \in \mathbb{R}.
\end{equation*}

Das ist die $xz$-Ebene innerhalb des $\mathbb{R}^3$. Es gilt $\text{Rang}(\mathbf{C}) = 2$.

**Beispiel 3:** Für die Matrix

\begin{equation*}
\mathbf{D} = \begin{pmatrix} 1 & 2 & 2 \\ 1 & -1 & 2 \\ 0 & 0 & 0 \\ 0 & 1 & 0 \end{pmatrix}
\end{equation*}

überprüfen wir, ob die drei Spalten linear unabhängig sind. Wir schreiben die
Abbildung als Linearkombination der Spalten:

\begin{equation*}
\mathbf{D} \cdot \begin{pmatrix} v_1 \\ v_2 \\ v_3 \end{pmatrix}
= v_1 \cdot \begin{pmatrix} 1 \\ 1 \\ 0 \\ 0 \end{pmatrix}
+ v_2 \cdot \begin{pmatrix} 2 \\ -1 \\ 0 \\ 1 \end{pmatrix}
+ v_3 \cdot \begin{pmatrix} 2 \\ 2 \\ 0 \\ 0 \end{pmatrix}.
\end{equation*}

Die dritte Spalte ist ein Vielfaches der ersten: $\begin{pmatrix} 2 \\ 2 \\ 0 \\ 0 \end{pmatrix}
= 2 \cdot \begin{pmatrix} 1 \\ 1 \\ 0 \\ 0 \end{pmatrix}$. Daher ist die dritte Spalte
eine Linearkombination der ersten. Die ersten beiden Spalten dagegen sind linear
unabhängig. Das Bild ist:

\begin{equation*}
\text{Bild}(\mathbf{D}) = s \cdot \begin{pmatrix} 1 \\ 1 \\ 0 \\ 0 \end{pmatrix}
+ t \cdot \begin{pmatrix} 2 \\ -1 \\ 0 \\ 1 \end{pmatrix}, \quad s, t \in \mathbb{R},
\end{equation*}

und $\text{Rang}(\mathbf{D}) = 2$.

## Wann liegt ein Vektor im Bild?

In der Praxis stellt man häufig die Frage: Liegt ein gegebener Vektor $\vec{b}$ im
Bild der Matrix $\mathbf{A}$? Diese Frage ist gleichbedeutend damit, ob das lineare
Gleichungssystem $\mathbf{A} \cdot \vec{x} = \vec{b}$ lösbar ist. Falls $\vec{b}$
im Bild liegt, so gibt es mindestens ein $\vec{x}$, das auf $\vec{b}$ abgebildet
wird. Falls $\vec{b}$ nicht im Bild liegt, ist das Gleichungssystem unlösbar.

Als Beispiel: Im Falle der Projektionsmatrix
$\mathbf{C} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}$
liegt der Vektor $\vec{b} = \begin{pmatrix} 1 \\ 2 \\ 0 \end{pmatrix}$ nicht im
Bild, weil das Bild nur Vektoren mit einer mittleren Komponente von null enthält.
Das Gleichungssystem $\mathbf{C} \cdot \vec{x} = \vec{b}$ ist daher unlösbar.

```{dropdown} Video "Bild und Rang einer Matrix" von MathePeter
<iframe width="560" height="315" src="https://www.youtube.com/embed/uQhTuRlWMxw"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Das Bild einer Matrix ist die Menge aller Vektoren, die als Ergebnis der linearen
Abbildung auftreten können. Es wird durch die Spalten der Matrix aufgespannt, und
sein Rang gibt die Anzahl der linear unabhängigen Spalten an. Ein Vektor $\vec{b}$
liegt genau dann im Bild, wenn das lineare Gleichungssystem $\mathbf{A} \cdot \vec{x}
= \vec{b}$ lösbar ist. Im nächsten Kapitel stellen wir den Zusammenhang zwischen
der Dimension des Kerns und der Dimension des Bildes durch die Dimensionsformel her.
