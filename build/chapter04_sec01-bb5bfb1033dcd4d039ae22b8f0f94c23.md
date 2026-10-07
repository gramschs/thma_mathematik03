---
authors:
  - name: Simone Gramsch
---

# 4.1 Lineare Abbildungen in 2D und 3D

In Kapitel 2.4 haben wir Gleichungssysteme in der Form $\mathbf{A}\vec{x} =
\vec{b}$ geschrieben und den Vektor $\vec{x}$ gesucht. Jetzt drehen wir die
Blickrichtung um: Wir geben einen Vektor vor, multiplizieren ihn mit einer
Matrix und fragen, wo der neue Vektor liegt. So wird jede Matrix zu einer
Vorschrift, die jeden Punkt der Ebene oder des Raums auf einen neuen Punkt
abbildet. Im Maschinenbau stecken solche Abbildungen zum Beispiel hinter dem
Spiegeln und Skalieren von Bauteilen im CAD-Programm oder hinter der
Darstellung verformter Bauteile in einer FEM-Simulation.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können eine Matrix als **lineare Abbildung**
  $F_{\mathbf{A}}(\vec{v}) = \mathbf{A}\vec{v}$ auffassen und Bildvektoren
  berechnen.
* [ ] Sie wissen, dass die Spalten einer Matrix die Bilder der
  **Einheitsvektoren** sind, und können damit zu einer geometrischen
  Beschreibung die passende Matrix aufstellen.
* [ ] Sie können **Streckung**, **Spiegelung**, **Scherung** und
  **Projektion** in der Ebene und im Raum an ihrer Matrix erkennen.
* [ ] Sie können mit der Determinante angeben, wie eine Abbildung
  Flächeninhalt oder Volumen und die **Orientierung** verändert.
* [ ] Sie wissen, dass eine $m\times n$-Matrix eine Abbildung vom
  $\mathbb{R}^n$ in den $\mathbb{R}^m$ beschreibt.
```

## Was macht eine Matrix mit einem Vektor?

In Kapitel 3.1 haben wir die Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}
\end{equation*}

untersucht und ihre Determinante $\det(\mathbf{A}) = 7$ berechnet. Jetzt
multiplizieren wir $\mathbf{A}$ mit dem Vektor $\vec{v} = (1, 1)^{\top}$:

\begin{equation*}
\mathbf{A}\vec{v}
= \begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}
\begin{pmatrix} 1 \\ 1 \end{pmatrix}
= \begin{pmatrix} 2 + 3 \\ 1 + 5 \end{pmatrix}
= \begin{pmatrix} 5 \\ 6 \end{pmatrix}.
\end{equation*}

Geometrisch gelesen wandert der Punkt $(1, 1)$ an die Stelle $(5, 6)$. Genauso
bekommt jeder andere Vektor der Ebene einen neuen Vektor zugeordnet. *Können
wir vorhersagen, wohin ein beliebiger Vektor wandert, ohne jedes Mal neu zu
rechnen?* Dazu probieren wir die Einheitsvektoren $\vec{e}_1 = (1, 0)^{\top}$
und $\vec{e}_2 = (0, 1)^{\top}$ aus, also die Spalten der Einheitsmatrix
$\mathbf{E}$ aus Kapitel 1.2:

\begin{equation*}
\mathbf{A}\vec{e}_1
= \begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}
\begin{pmatrix} 1 \\ 0 \end{pmatrix}
= \begin{pmatrix} 2 \\ 1 \end{pmatrix},
\qquad
\mathbf{A}\vec{e}_2
= \begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}
\begin{pmatrix} 0 \\ 1 \end{pmatrix}
= \begin{pmatrix} 3 \\ 5 \end{pmatrix}.
\end{equation*}

Heraus kommen genau die beiden Spalten von $\mathbf{A}$, die wir ab jetzt
$\vec{a}_1$ und $\vec{a}_2$ nennen. Das ist kein Zufall, denn beim
Multiplizieren mit $\vec{e}_1$ wird die erste Spalte mit $1$ und die zweite
mit $0$ gewichtet. Für einen allgemeinen Vektor $\vec{v} = (x, y)^{\top}$
sortieren wir das Ergebnis nach $x$ und $y$:

\begin{equation*}
\mathbf{A}\begin{pmatrix} x \\ y \end{pmatrix}
= \begin{pmatrix} 2x + 3y \\ x + 5y \end{pmatrix}
= x\begin{pmatrix} 2 \\ 1 \end{pmatrix} + y\begin{pmatrix} 3 \\ 5 \end{pmatrix}
= x\,\vec{a}_1 + y\,\vec{a}_2.
\end{equation*}

Der Vektor $\vec{v} = x\,\vec{e}_1 + y\,\vec{e}_2$ und sein Bild
$x\,\vec{a}_1 + y\,\vec{a}_2$ setzen sich also auf dieselbe Weise zusammen,
einmal aus den Einheitsvektoren und einmal aus den Spalten. Wenn wir wissen,
wohin die Einheitsvektoren abgebildet werden, kennen wir die ganze Abbildung.
Dasselbe gilt für jede quadratische Matrix, im Raum etwa mit drei
Einheitsvektoren und drei Spalten.

```{admonition} Was ist ... eine lineare Abbildung?
:class: note
Eine quadratische Matrix $\mathbf{M}$ mit $n$ Zeilen und $n$ Spalten ordnet
jedem Vektor $\vec{v} \in \mathbb{R}^n$ den **Bildvektor**
$\vec{w} = \mathbf{M}\vec{v}$ zu. Diese Zuordnung heißt **lineare Abbildung**
und wird als

\begin{equation*}
F_{\mathbf{M}}: \mathbb{R}^n \to \mathbb{R}^n, \quad
F_{\mathbf{M}}(\vec{v}) = \mathbf{M}\vec{v} = \vec{w}
\end{equation*}

geschrieben. Die Angabe $\mathbb{R}^n \to \mathbb{R}^n$ besagt, dass die
Eingabevektoren und die Bildvektoren beide im $\mathbb{R}^n$ liegen. Die
$j$-te Spalte von $\mathbf{M}$ ist das Bild $F_{\mathbf{M}}(\vec{e}_j)$ des
$j$-ten Einheitsvektors.
```

Warum diese Abbildungen linear heißen, klären wir in Kapitel 4.2. Mit der Box
berechnen wir das Bild von $\vec{u} = (2, -1)^{\top}$, ohne Zeile mal Spalte
zu rechnen:

\begin{equation*}
F_{\mathbf{A}}(\vec{u})
= 2\,\vec{a}_1 - 1\,\vec{a}_2
= \begin{pmatrix} 4 \\ 2 \end{pmatrix} - \begin{pmatrix} 3 \\ 5 \end{pmatrix}
= \begin{pmatrix} 1 \\ -3 \end{pmatrix}.
\end{equation*}

Zur Probe rechnen wir doch Zeile mal Spalte und erhalten
$2\cdot 2 + 3\cdot(-1) = 1$ und $1\cdot 2 + 5\cdot(-1) = -3$. Beide Wege
liefern denselben Bildvektor.

```{dropdown} Video "Linear transformations and matrices" von 3Blue1Brown
<iframe width="1018" height="572" src="https://www.youtube.com/embed/kYB8IZa5AuE" title="Linear transformations and matrices | Chapter 3, Essence of linear algebra" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Wie verändern Matrizen die Ebene?

Jetzt schicken wir eine ganze Fläche durch die Abbildung, nämlich das
**Einheitsquadrat** aus allen Punkten $x\,\vec{e}_1 + y\,\vec{e}_2$ mit
$0 \leq x \leq 1$ und $0 \leq y \leq 1$. Unter $F_{\mathbf{A}}$ landet jeder
dieser Punkte bei $x\,\vec{a}_1 + y\,\vec{a}_2$. Das Bild des
Einheitsquadrats ist also das Parallelogramm, das die Spalten von $\mathbf{A}$
aufspannen.

```{figure} pics/einheitsquadrat_parallelogramm.svg
---
class: responsive-figure-50
name: einheitsquadrat_parallelogramm
---
Darstellung des Einheitsquadrats (gelb) und seines Bildes unter
$F_{\mathbf{A}}$, des von $\vec{a}_1$ und $\vec{a}_2$ aufgespannten
Parallelogramms (blau).
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Nach Kapitel 3.1 hat dieses Parallelogramm den Flächeninhalt
$|\det(\mathbf{A})| = 7$. *Wächst jede Fläche um diesen Faktor?* Wir prüfen es
am Rechteck mit den Kanten $2\,\vec{e}_1$ und $\vec{e}_2$, das den
Flächeninhalt $2$ hat. Die Kanten werden auf $2\,\vec{a}_1 = (4, 2)^{\top}$ und
$\vec{a}_2 = (3, 5)^{\top}$ abgebildet, und das Parallelogramm aus diesen
Vektoren hat den Flächeninhalt $|4\cdot 5 - 2\cdot 3| = 14 = 7\cdot 2$. Weil
sich jede Figur aus kleinen Quadraten zusammensetzen lässt, wächst tatsächlich
jeder Flächeninhalt um den Faktor $7$.

Die Abbildung zeigt noch eine zweite Eigenschaft. Von $\vec{e}_1$ aus
erreichen wir $\vec{e}_2$ durch eine Drehung gegen den Uhrzeigersinn, und auf
dem kürzesten Weg gilt dasselbe für $\vec{a}_1$ und $\vec{a}_2$, wie die grauen
Bögen zeigen. Wir sagen, dass $F_{\mathbf{A}}$ die **Orientierung** erhält.
*Kann eine Abbildung die Orientierung auch umkehren?*

Um das zu klären, gehen wir umgekehrt vor und setzen zu einer gewünschten
Wirkung die Matrix aus den Bildern der Einheitsvektoren zusammen. Bei einer
**Streckung** um den Faktor $2$ wandern $\vec{e}_1$ und $\vec{e}_2$ auf ihr
Doppeltes. Bei der **Spiegelung** an der Winkelhalbierenden $y = x$ tauschen
sie ihre Plätze. Bei einer **Scherung** bleibt $\vec{e}_1$ liegen, und
$\vec{e}_2$ kippt wie bei Kursivschrift nach $(1, 1)^{\top}$. Bei der
**Projektion** auf die $x$-Achse bleibt $\vec{e}_1$ liegen, und $\vec{e}_2$
fällt auf den Nullvektor. Als Spalten geschrieben ergeben sich die Matrizen

\begin{equation*}
\mathbf{B} = \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix}, \quad
\mathbf{C} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad
\mathbf{D} = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \quad
\mathbf{P} = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}
\end{equation*}

für Streckung, Spiegelung, Scherung und Projektion. Die folgende Abbildung
zeigt, was sie aus dem Einheitsquadrat machen.

```{figure} pics/abbildungen_einheitsquadrat.svg
---
class: responsive-figure-50
name: abbildungen_einheitsquadrat
---
Darstellung des Einheitsquadrats (gestrichelt) und seiner Bilder unter
Streckung, Spiegelung, Scherung und Projektion.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Die Determinanten passen zu den Bildern. Bei der Streckung werden beide Seiten
doppelt so lang, und der Flächeninhalt wächst auf
$\det(\mathbf{B}) = 2\cdot 2 - 0\cdot 0 = 4$. Die Scherung macht das Quadrat
schief, lässt aber Grundseite und Höhe gleich, passend zu
$\det(\mathbf{D}) = 1\cdot 1 - 0\cdot 1 = 1$. Die Projektion drückt das
Quadrat auf eine Strecke zusammen, und es ist $\det(\mathbf{P}) = 0$. Bei der
Spiegelung ist das Bild wieder das Einheitsquadrat, aber wegen
$\mathbf{C}\vec{e}_1 = \vec{e}_2$ und $\mathbf{C}\vec{e}_2 = \vec{e}_1$
erreichen wir $\mathbf{C}\vec{e}_2$ von $\mathbf{C}\vec{e}_1$ aus auf dem
kürzesten Weg nur im Uhrzeigersinn. Die Spiegelung kehrt also die
Orientierung um, und genau das zeigt
$\det(\mathbf{C}) = 0\cdot 0 - 1\cdot 1 = -1$ an.

```{admonition} Was verrät die Determinante über eine Abbildung?
:class: note
Für eine lineare Abbildung $F_{\mathbf{M}}$ der Ebene mit einer
$2\times 2$-Matrix $\mathbf{M}$ gilt:

* Flächeninhalte ändern sich um den Faktor $|\det(\mathbf{M})|$.
* Ist $\det(\mathbf{M}) > 0$, bleibt die Orientierung erhalten. Ist
  $\det(\mathbf{M}) < 0$, kehrt sie sich um.
* Ist $\det(\mathbf{M}) = 0$, fällt jede Fläche auf eine Strecke oder einen
  Punkt zusammen.
```

Für unser Beispiel bedeutet das: $F_{\mathbf{A}}$ vergrößert jeden
Flächeninhalt um den Faktor $7$ und erhält die Orientierung. *Lässt sich diese
Abbildung rückgängig machen?* Wegen $\det(\mathbf{A}) \neq 0$ ist
$\mathbf{A}$ invertierbar, und aus Kapitel 3.1 kennen wir

\begin{equation*}
\mathbf{A}^{-1} = \frac{1}{7}\begin{pmatrix} 5 & -3 \\ -1 & 2 \end{pmatrix}.
\end{equation*}

Diese Matrix bringt jeden Bildvektor an seinen Ausgangspunkt zurück, zum
Beispiel ist $\mathbf{A}^{-1}(5, 6)^{\top} = \frac{1}{7}(25 - 18, -5 +
12)^{\top} = (1, 1)^{\top}$. Allgemein gehört zum Nacheinanderausführen zweier
Abbildungen das Produkt ihrer Matrizen, wobei die zuerst ausgeführte rechts
steht. Hier ist das $\mathbf{A}^{-1}\mathbf{A} = \mathbf{E}$, also die
Abbildung, die nichts verändert. Weil die Matrizenmultiplikation nicht
kommutativ ist, kommt es dabei im Allgemeinen auf die Reihenfolge an, was uns
bei Drehungen in Kapitel 5.4 wieder begegnen wird. Die Umkehrabbildung
verkleinert Flächen um den Faktor $\frac{1}{7}$, passend zu
$\det(\mathbf{A}^{-1}) = \frac{1}{7}$ aus Kapitel 3.3. Die Projektion lässt
sich dagegen nicht umkehren, denn $(1, 0)^{\top}$ und $(1, 5)^{\top}$ landen
beide bei $(1, 0)^{\top}$.

```{admonition} Bleibt eine Figur unverändert, wenn $|\det(\mathbf{M})| = 1$ ist?
:class: danger
Nein. Die Scherung $\mathbf{D}$ hat die Determinante $1$, und trotzdem wird
aus dem Quadrat ein schiefes Parallelogramm. Die Determinante verrät nur, wie
sich Flächeninhalt und Orientierung ändern, aber nicht, ob Längen und Winkel
erhalten bleiben. Matrizen mit dieser stärkeren Eigenschaft lernen wir in
Kapitel 5.2 als orthogonale Matrizen kennen.
```

```{dropdown} Video "The determinant" von 3Blue1Brown
<iframe width="1018" height="572" src="https://www.youtube.com/embed/Ip3X9LOh2dk" title="The determinant | Chapter 6, Essence of linear algebra" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Was ändert sich im Raum?

Im Raum gibt es drei Einheitsvektoren $\vec{e}_1$, $\vec{e}_2$ und
$\vec{e}_3$, und eine $3\times 3$-Matrix bildet sie auf ihre drei Spalten ab.
So wie das Einheitsquadrat unter $F_{\mathbf{A}}$ zum Parallelogramm wurde,
wird der **Einheitswürfel** mit den Kanten $\vec{e}_1$, $\vec{e}_2$ und
$\vec{e}_3$ zu dem Spat, den die drei Spalten aufspannen. In Kapitel 3.4 haben
wir gesehen, dass der Betrag der Determinante das Volumen dieses Spats ist. Die
Merkregel aus dem vorigen Abschnitt gilt im Raum also genauso, wenn wir
Flächeninhalt durch Volumen ersetzen.

Die Gegenstücke der ebenen Abbildungen stellen wir wieder über die Bilder der
Einheitsvektoren auf. Bei der Streckung um den Faktor $2$ wandern alle drei
Einheitsvektoren auf ihr Doppeltes. Bei der Spiegelung an der $xy$-Ebene
klappt $\vec{e}_3$ nach unten auf $-\vec{e}_3$, und bei der Projektion auf die
$xy$-Ebene fällt $\vec{e}_3$ auf den Nullvektor. Das ergibt die drei Matrizen

\begin{equation*}
\begin{pmatrix} 2 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix}, \quad
\begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & -1 \end{pmatrix}, \quad
\begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}.
\end{equation*}

Als Diagonalmatrizen haben sie nach Kapitel 3.3 das Produkt der
Diagonaleinträge als Determinante. Die Streckung hat die Determinante
$2^3 = 8$, denn jede Kante des Würfels wird doppelt so lang. Die Projektion
hat die Determinante $0$, denn sie drückt den Würfel auf das Einheitsquadrat in
der $xy$-Ebene platt. Die Spiegelung hat die Determinante $-1$. Sie lässt das
Volumen gleich, macht aber aus einem Rechtssystem, wie es Daumen, Zeigefinger
und Mittelfinger der rechten Hand bilden, ein Linkssystem.

*Muss eine Abbildung eigentlich im selben Raum bleiben?* Die Projektion auf die
$xy$-Ebene liefert Vektoren $(x, y, 0)^{\top}$, deren dritte Komponente keine
Information trägt. Lassen wir die dritte Zeile der Matrix weg, erhalten wir

\begin{equation*}
\begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \end{pmatrix}
\begin{pmatrix} x \\ y \\ z \end{pmatrix}
= \begin{pmatrix} x \\ y \end{pmatrix}.
\end{equation*}

Diese $2\times 3$-Matrix nimmt Vektoren aus dem $\mathbb{R}^3$ entgegen und
liefert Vektoren aus dem $\mathbb{R}^2$. Die Multiplikation ist nach Kapitel
1.4 definiert, weil die Matrix drei Spalten und der Vektor drei Einträge hat.
Die Spalten $(1, 0)^{\top}$, $(0, 1)^{\top}$ und $(0, 0)^{\top}$ sind wieder
die Bilder von $\vec{e}_1$, $\vec{e}_2$ und $\vec{e}_3$, nur liegen sie jetzt
in der Ebene. Den Vektor $(1, 1, 4)^{\top}$ etwa bildet die Matrix auf
$(1, 1)^{\top}$ ab, wie einen Schatten bei Licht senkrecht von oben.

```{admonition} Welche Räume verbindet eine $m\times n$-Matrix?
:class: note
Eine Matrix $\mathbf{M}$ mit $m$ Zeilen und $n$ Spalten beschreibt die
lineare Abbildung

\begin{equation*}
F_{\mathbf{M}}: \mathbb{R}^n \to \mathbb{R}^m, \quad
F_{\mathbf{M}}(\vec{v}) = \mathbf{M}\vec{v}.
\end{equation*}

Die Anzahl $n$ der Spalten ist die Dimension des Raums, aus dem die
Eingabevektoren stammen. Die Anzahl $m$ der Zeilen ist die Dimension des
Raums, in dem die Bildvektoren liegen. Die $j$-te Spalte von $\mathbf{M}$ ist
das Bild des $j$-ten Einheitsvektors des $\mathbb{R}^n$.
```

Für die $2\times 3$-Matrix ist $n = 3$ und $m = 2$, passend zu unserer
Beobachtung. Für $\mathbf{A}$ ist $m = n = 2$, das ist der quadratische Fall
aus der ersten Box. Eine Determinante gibt es nur für quadratische Matrizen,
und bei einer Abbildung vom $\mathbb{R}^3$ in den $\mathbb{R}^2$ wäre ein
Faktor zwischen Volumen und Flächeninhalt auch gar nicht sinnvoll.

```{admonition} Bildet eine $2\times 3$-Matrix vom $\mathbb{R}^2$ in den $\mathbb{R}^3$ ab?
:class: danger
Nein, genau umgekehrt. Die erste Zahl in $2\times 3$ ist die Anzahl der Zeilen
und damit die Dimension der Bildvektoren. Mit einem Vektor aus dem
$\mathbb{R}^2$ lässt sich eine $2\times 3$-Matrix gar nicht multiplizieren,
weil zu ihren drei Spalten drei Einträge gehören.
```

Zum Abschluss stellen wir die Abbildungen aus diesem Kapitel zusammen, mit
einem allgemeinen Streckfaktor $s > 0$ und einem allgemeinen Scherfaktor $k$.

| Abbildung | Matrix | Determinante | Wirkung |
| --- | --- | --- | --- |
| Streckung um $s$ in der Ebene | $\begin{pmatrix} s & 0 \\ 0 & s \end{pmatrix}$ | $s^2$ | Flächeninhalt wird mit $s^2$ multipliziert |
| Spiegelung an $y = x$ | $\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$ | $-1$ | Flächeninhalt bleibt, Orientierung kehrt sich um |
| Scherung | $\begin{pmatrix} 1 & k \\ 0 & 1 \end{pmatrix}$ | $1$ | Flächeninhalt bleibt, Form ändert sich |
| Projektion auf die $x$-Achse | $\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}$ | $0$ | Fläche fällt auf eine Strecke |
| Streckung um $s$ im Raum | $\begin{pmatrix} s & 0 & 0 \\ 0 & s & 0 \\ 0 & 0 & s \end{pmatrix}$ | $s^3$ | Volumen wird mit $s^3$ multipliziert |
| Spiegelung an der $xy$-Ebene | $\begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & -1 \end{pmatrix}$ | $-1$ | Volumen bleibt, Orientierung kehrt sich um |
| Projektion auf die $xy$-Ebene | $\begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}$ | $0$ | Körper fällt auf eine Fläche |
| Projektion vom $\mathbb{R}^3$ in den $\mathbb{R}^2$ | $\begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \end{pmatrix}$ | keine | liefert die Koordinaten $(x, y)^{\top}$ |

## Zusammenfassung und Ausblick

Eine Matrix ordnet jedem Vektor einen Bildvektor zu, und ihre Spalten
verraten, wohin die Einheitsvektoren abgebildet werden. Damit lesen wir die
Wirkung einer Matrix ab und stellen umgekehrt zu einer geometrischen
Beschreibung die passende Matrix auf. Der Betrag der Determinante gibt an, um
welchen Faktor sich Flächeninhalte und Volumina ändern, und ihr Vorzeichen, ob
die Orientierung erhalten bleibt. In Kapitel 4.2 sehen wir, welche zwei
Rechenregeln hinter dem Namen lineare Abbildung stecken und warum ausgerechnet
das Verschieben aller Punkte keine lineare Abbildung ist. Bei der Spiegelung
$\mathbf{C}$ fällt außerdem auf, dass jeder Vektor auf der Winkelhalbierenden
$y = x$ an seinem Platz bleibt. Vektoren, deren Richtung eine Abbildung nicht
verändert, werden in Kapitel 6 als Eigenvektoren zum wichtigsten Werkzeug, um
eine Matrix zu verstehen.
