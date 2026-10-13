---
authors:
  - name: Simone Gramsch
---

# 5.2 Orthogonale Matrizen

In Kapitel 5.1 haben wir Koordinaten bezüglich einer Basis mit der Inversen
berechnet, die wir zuvor erst bestimmen mussten. Jetzt suchen wir Basen, bei
denen wir die Inverse ohne jede Rechnung hinschreiben können, weil sie einfach
die Transponierte ist. Dahinter steckt eine geometrische Eigenschaft, die wir
aus Mathematik 1 kennen: Die Basisvektoren stehen senkrecht aufeinander und
haben die Länge $1$. Im Maschinenbau begegnen uns solche Matrizen überall dort,
wo ein Bauteil gedreht oder zwischen rechtwinkligen Koordinatensystemen
umgerechnet wird, ohne dass sich seine Maße ändern.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, wann eine Matrix **orthogonal** ist, und können das an ihren
  Spalten oder mit $\mathbf{M}^{\top}\mathbf{M} = \mathbf{E}$ prüfen.
* [ ] Sie können die Inverse einer orthogonalen Matrix ohne Rechnung als
  $\mathbf{M}^{-1} = \mathbf{M}^{\top}$ angeben.
* [ ] Sie wissen, dass orthogonale Matrizen **längentreu** und **winkeltreu**
  abbilden.
* [ ] Sie wissen, dass orthogonale Matrizen die Determinante $1$ oder $-1$
  haben und dass der Umkehrschluss nicht gilt.
* [ ] Sie können Koordinaten bezüglich einer **Orthonormalbasis** mit
  Skalarprodukten berechnen.
```

## Wann ist eine Matrix orthogonal?

In Kapitel 5.1 haben wir Koordinaten bezüglich der Basis
$\vec{b}_1 = (2, 1)^{\top}$, $\vec{b}_2 = (-1, 1)^{\top}$ berechnet. Dort hieß
die Matrix mit diesen Spalten $\mathbf{A}$, in diesem Kapitel nennen wir sie

\begin{equation*}
\mathbf{B} = \begin{pmatrix} 2 & -1 \\ 1 & 1 \end{pmatrix}.
\end{equation*}

Für ihre Inverse brauchten wir die Determinante und die Formel aus Kapitel
2.2. *Wann könnten wir uns diese Rechnung sparen, weil die Inverse einfach die
Transponierte ist?* Dann müsste $\mathbf{B}^{\top}\mathbf{B} = \mathbf{E}$
gelten. Wir rechnen nach:

\begin{equation*}
\mathbf{B}^{\top}\mathbf{B}
= \begin{pmatrix} 2 & 1 \\ -1 & 1 \end{pmatrix}
\begin{pmatrix} 2 & -1 \\ 1 & 1 \end{pmatrix}
= \begin{pmatrix} 5 & -1 \\ -1 & 2 \end{pmatrix}.
\end{equation*}

Nach Kapitel 1.4 ist jeder Eintrag das Skalarprodukt einer Zeile von
$\mathbf{B}^{\top}$ mit einer Spalte von $\mathbf{B}$, und nach Kapitel 2.1
sind die Zeilen von $\mathbf{B}^{\top}$ gerade die Spalten von $\mathbf{B}$.
Links oben steht also $\vec{b}_1\cdot\vec{b}_1 = 5$, das Quadrat der Länge
$|\vec{b}_1| = \sqrt{5}$, und rechts unten $\vec{b}_2\cdot\vec{b}_2 = 2$. Auf
den beiden anderen Plätzen steht das Skalarprodukt
$\vec{b}_1\cdot\vec{b}_2 = -2 + 1 = -1$.

Damit die Einheitsmatrix herauskommt, müssten beide Spalten die Länge $1$
haben, und ihr Skalarprodukt müsste $0$ sein. Aus Mathematik 1 wissen wir, dass
zwei Vektoren senkrecht aufeinander stehen, wenn ihr Skalarprodukt $0$ ist. Wir
bauen uns deshalb eine Matrix, deren Spalten beide Wünsche erfüllen. In der
Ebene erhalten wir einen senkrechten Vektor, indem wir die beiden Komponenten
vertauschen und bei einer das Vorzeichen ändern. Aus $(3, 4)^{\top}$ wird so
$(-4, 3)^{\top}$, und tatsächlich ist
$(3, 4)^{\top}\cdot(-4, 3)^{\top} = -12 + 12 = 0$.

Beide Vektoren haben die Länge $\sqrt{3^2 + 4^2} = 5$. Teilen wir sie durch
ihre Länge, werden sie wie in Mathematik 1 normiert: Sie behalten ihre Richtung
und haben danach die Länge $1$. Als durchgehendes Beispiel für dieses Kapitel
nehmen wir die normierten Vektoren und die Matrix mit diesen Spalten:

\begin{equation*}
\vec{a}_1 = \frac{1}{5}\begin{pmatrix} 3 \\ 4 \end{pmatrix}, \quad
\vec{a}_2 = \frac{1}{5}\begin{pmatrix} -4 \\ 3 \end{pmatrix}, \quad
\mathbf{A} = \frac{1}{5}\begin{pmatrix} 3 & -4 \\ 4 & 3 \end{pmatrix}.
\end{equation*}

Den gemeinsamen Faktor $\frac{1}{5}$ haben wir wie bei der
Skalarmultiplikation aus Kapitel 1.3 vor die Matrix gezogen. Jetzt prüfen wir,
ob $\mathbf{A}^{\top}\mathbf{A}$ die Einheitsmatrix ist:

\begin{equation*}
\mathbf{A}^{\top}\mathbf{A}
= \frac{1}{25}\begin{pmatrix} 3 & 4 \\ -4 & 3 \end{pmatrix}
\begin{pmatrix} 3 & -4 \\ 4 & 3 \end{pmatrix}
= \frac{1}{25}\begin{pmatrix} 9 + 16 & -12 + 12 \\ -12 + 12 & 16 + 9 \end{pmatrix}
= \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}.
\end{equation*}

Der Vorfaktor $\frac{1}{25} = \frac{1}{5}\cdot\frac{1}{5}$ stammt aus den
beiden Matrizen. Auf der Diagonalen stehen wieder die Längenquadrate
$\vec{a}_1\cdot\vec{a}_1 = \vec{a}_2\cdot\vec{a}_2 = 1$, daneben das
Skalarprodukt $\vec{a}_1\cdot\vec{a}_2 = 0$. Matrizen mit dieser Eigenschaft
bekommen einen eigenen Namen.

```{admonition} Was ist ... eine orthogonale Matrix?
:class: note
Vektoren, die alle die Länge $1$ haben und paarweise senkrecht aufeinander
stehen, heißen **orthonormal**. Eine quadratische Matrix $\mathbf{M}$ heißt
**orthogonal**, wenn ihre Spalten orthonormal sind. Gleichwertig dazu ist die
Bedingung

\begin{equation*}
\mathbf{M}^{\top}\mathbf{M} = \mathbf{E}.
\end{equation*}

Eine orthogonale Matrix ist invertierbar, und ihre Inverse ist ihre
Transponierte:

\begin{equation*}
\mathbf{M}^{-1} = \mathbf{M}^{\top}.
\end{equation*}
```

Die Spalten von $\mathbf{A}$ haben wir gerade so gebaut, dass sie orthonormal
sind. Also ist $\mathbf{A}$ orthogonal, und wir können die Inverse ohne
Rechnung hinschreiben:

\begin{equation*}
\mathbf{A}^{-1} = \mathbf{A}^{\top}
= \frac{1}{5}\begin{pmatrix} 3 & 4 \\ -4 & 3 \end{pmatrix}.
\end{equation*}

In den Zeilen von $\mathbf{A}^{-1}$ stehen die Basisvektoren $\vec{a}_1$ und
$\vec{a}_2$. Nach Kapitel 2.2 muss die Inverse auch von rechts die
Einheitsmatrix liefern. Zur Probe multiplizieren wir deshalb in der anderen
Reihenfolge:

\begin{equation*}
\mathbf{A}\mathbf{A}^{\top}
= \frac{1}{25}\begin{pmatrix} 3 & -4 \\ 4 & 3 \end{pmatrix}
\begin{pmatrix} 3 & 4 \\ -4 & 3 \end{pmatrix}
= \frac{1}{25}\begin{pmatrix} 9 + 16 & 12 - 12 \\ 12 - 12 & 16 + 9 \end{pmatrix}
= \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}.
\end{equation*}

Diesmal sind die Einträge Skalarprodukte der Zeilen $\frac{1}{5}(3, -4)$ und
$\frac{1}{5}(4, 3)$ von $\mathbf{A}$. Auch die Zeilen einer orthogonalen Matrix
sind also orthonormal. Bei einer $3\times 3$-Matrix prüfen wir genauso, nur
sind es dann drei Längen und drei Skalarprodukte.

```{dropdown} Video "Orthogonale Matrizen" von MathePeter
<iframe width="560" height="315" src="https://www.youtube.com/embed/X4oTwBusjMk"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Was bleibt bei einer orthogonalen Abbildung erhalten?

In Kapitel 4.1 haben wir gesehen, dass die Drehung und die Scherung beide die
Determinante $1$ haben, aber nur die Scherung das Einheitsquadrat verzerrt.
Die Determinante verrät
also nicht, ob Längen und Winkel erhalten bleiben. *Wie verhält sich unsere
orthogonale Matrix $\mathbf{A}$?* Wir bilden die Vektoren
$\vec{x} = (1, 2)^{\top}$ und $\vec{y} = (3, 1)^{\top}$ ab:

\begin{align*}
\mathbf{A}\vec{x}
&= \frac{1}{5}\begin{pmatrix} 3 & -4 \\ 4 & 3 \end{pmatrix}
\begin{pmatrix} 1 \\ 2 \end{pmatrix}
= \frac{1}{5}\begin{pmatrix} 3 - 8 \\ 4 + 6 \end{pmatrix}
= \begin{pmatrix} -1 \\ 2 \end{pmatrix}, \\
\mathbf{A}\vec{y}
&= \frac{1}{5}\begin{pmatrix} 3 & -4 \\ 4 & 3 \end{pmatrix}
\begin{pmatrix} 3 \\ 1 \end{pmatrix}
= \frac{1}{5}\begin{pmatrix} 9 - 4 \\ 12 + 3 \end{pmatrix}
= \begin{pmatrix} 1 \\ 3 \end{pmatrix}.
\end{align*}

Die Längen ändern sich nicht, denn $|\vec{x}| = \sqrt{1 + 4} = \sqrt{5}$ und
$|\mathbf{A}\vec{x}| = \sqrt{1 + 4} = \sqrt{5}$, ebenso
$|\vec{y}| = \sqrt{9 + 1} = \sqrt{10}$ und
$|\mathbf{A}\vec{y}| = \sqrt{1 + 9} = \sqrt{10}$. Auch das Skalarprodukt
bleibt gleich: $\vec{x}\cdot\vec{y} = 3 + 2 = 5$ und
$(\mathbf{A}\vec{x})\cdot(\mathbf{A}\vec{y}) = -1 + 6 = 5$. Den Winkel
zwischen zwei Vektoren berechnen wir wie in Mathematik 1 aus

\begin{equation*}
\cos(\varphi) = \frac{\vec{x}\cdot\vec{y}}{|\vec{x}|\,|\vec{y}|}
= \frac{5}{\sqrt{5}\cdot\sqrt{10}} = \frac{5}{\sqrt{50}} = \frac{1}{\sqrt{2}}.
\end{equation*}

Dabei ist $\varphi$ der Winkel zwischen $\vec{x}$ und $\vec{y}$, hier also
$\varphi = 45^\circ$. Für die Bildvektoren stehen in Zähler und Nenner
dieselben Zahlen, also schließen auch $\mathbf{A}\vec{x}$ und
$\mathbf{A}\vec{y}$ einen Winkel von $45^\circ$ ein.

*Ist das bei $\mathbf{A}$ nur Zufall?* Um das zu klären, schreiben wir das
Skalarprodukt nach Kapitel 1.4 als Produkt einer Zeile mit einer Spalte, also
$\vec{x}\cdot\vec{y} = \vec{x}^{\top}\vec{y}$. Für eine orthogonale Matrix
$\mathbf{M}$ erhalten wir dann mit der Regel
$(\mathbf{M}\vec{x})^{\top} = \vec{x}^{\top}\mathbf{M}^{\top}$ aus Kapitel 2.1

\begin{equation*}
(\mathbf{M}\vec{x})\cdot(\mathbf{M}\vec{y})
= (\mathbf{M}\vec{x})^{\top}\,\mathbf{M}\vec{y}
= \vec{x}^{\top}\mathbf{M}^{\top}\mathbf{M}\,\vec{y}
= \vec{x}^{\top}\vec{y}
= \vec{x}\cdot\vec{y}.
\end{equation*}

Im dritten Schritt haben wir $\mathbf{M}^{\top}\mathbf{M} = \mathbf{E}$
verwendet. Eine orthogonale Matrix ändert also kein einziges Skalarprodukt.
Längen berechnen wir mit $|\vec{x}| = \sqrt{\vec{x}\cdot\vec{x}}$ und Winkel
mit der Formel für $\cos(\varphi)$, also beide allein aus Skalarprodukten.
Deshalb bleiben auch sie erhalten.

*Und was sagt die Determinante?* Aus $\mathbf{M}^{\top}\mathbf{M} = \mathbf{E}$
folgt mit der Produktregel aus Kapitel 3.3 und
$\det(\mathbf{M}^{\top}) = \det(\mathbf{M})$

\begin{equation*}
1 = \det(\mathbf{E}) = \det(\mathbf{M}^{\top}\mathbf{M})
= \det(\mathbf{M}^{\top})\cdot\det(\mathbf{M})
= \big(\det(\mathbf{M})\big)^2.
\end{equation*}

Das Quadrat der Determinante ist also $1$, und die Determinante selbst kann nur
$1$ oder $-1$ sein. Nach Kapitel 4.1 bleibt damit auch der Flächeninhalt jeder
Figur erhalten.

```{admonition} Was bleibt bei einer orthogonalen Abbildung erhalten?
:class: note
Für eine orthogonale Matrix $\mathbf{M}$ und alle Vektoren $\vec{x}$ und
$\vec{y}$ gilt $(\mathbf{M}\vec{x})\cdot(\mathbf{M}\vec{y}) = \vec{x}\cdot\vec{y}$.
Daraus folgt:

* Es gilt $|\mathbf{M}\vec{x}| = |\vec{x}|$. Die Abbildung ist **längentreu**.
* Die Bilder $\mathbf{M}\vec{x}$ und $\mathbf{M}\vec{y}$ schließen denselben
  Winkel ein wie $\vec{x}$ und $\vec{y}$. Die Abbildung ist **winkeltreu**.
* Die Determinante ist $\det(\mathbf{M}) = 1$ oder $\det(\mathbf{M}) = -1$.
```

Die Längen- und die Winkeltreue haben wir an $\vec{x}$ und $\vec{y}$ schon
nachgerechnet. Für die Determinante unseres Beispiels erhalten wir

\begin{equation*}
\det(\mathbf{A})
= \frac{3}{5}\cdot\frac{3}{5} - \left(-\frac{4}{5}\right)\cdot\frac{4}{5}
= \frac{9}{25} + \frac{16}{25} = 1.
\end{equation*}

Mit $\det(\mathbf{A}) = 1$ bleibt nach Kapitel 4.1 auch die Orientierung
erhalten. Längentreu, winkeltreu und ohne Umkehr der Orientierung, so verhält
sich eine Drehung um den Ursprung. Um welchen Winkel $\mathbf{A}$ die Ebene
dreht, finden wir in Kapitel 5.4 heraus, wenn wir die Drehmatrix für beliebige
Winkel aufstellen.

Auch die Determinante $-1$ kommt vor. Die Spiegelung an der
Winkelhalbierenden $y = x$ aus Kapitel 4.1 hat die Spalten $\vec{e}_2$ und
$\vec{e}_1$, ist also orthogonal und kehrt mit der Determinante $-1$ die
Orientierung um. Der Umkehrschluss gilt allerdings nicht: Die Scherung aus
Kapitel 4.1 hat ebenfalls die Determinante $1$, aber ihre Spalten
$(1, 0)^{\top}$ und $(1, 1)^{\top}$ stehen nicht senkrecht aufeinander. Eine
Matrix mit Determinante $1$ oder $-1$ ist also nicht automatisch orthogonal.

```{dropdown} Video "Orthogonale Matrizen" von Prof. Hielscher
<iframe width="742" height="613"
src="https://www.youtube.com/embed/3RCcnjyKRPg?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07"
title="Orthogonale Matrizen" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

## Warum wird der Basiswechsel so einfach?

Wegen $\det(\mathbf{A}) = 1 \neq 0$ bilden die Spalten $\vec{a}_1$ und
$\vec{a}_2$ nach Kapitel 5.1 eine Basis der Ebene. Das gilt für jede
orthogonale Matrix, denn ihre Determinante ist $1$ oder $-1$ und damit nie
$0$. Den Koordinatenvektor bezüglich dieser Basis berechnen wir wie in Kapitel
5.1 mit der Inversen, und die ist jetzt einfach die Transponierte. *Wie viel
Arbeit spart uns das?* Für $\vec{u} = (5, 5)^{\top}$ erhalten wir

\begin{equation*}
[\vec{u}]_{\mathbf{A}} = \mathbf{A}^{\top}\vec{u}
= \frac{1}{5}\begin{pmatrix} 3 & 4 \\ -4 & 3 \end{pmatrix}
\begin{pmatrix} 5 \\ 5 \end{pmatrix}
= \frac{1}{5}\begin{pmatrix} 15 + 20 \\ -20 + 15 \end{pmatrix}
= \begin{pmatrix} 7 \\ -1 \end{pmatrix}.
\end{equation*}

Die Koordinaten von $\vec{u}$ bezüglich $\vec{a}_1, \vec{a}_2$ sind also $7$
und $-1$. Zur Probe setzen wir sie als Vorfaktoren ein und erhalten
$7\,\vec{a}_1 - \vec{a}_2 = \frac{1}{5}(21 + 4,\ 28 - 3)^{\top} = (5, 5)^{\top}$.
*Was steckt hinter diesen beiden Zahlen?* Die Zeilen von $\mathbf{A}^{\top}$
sind die Basisvektoren $\vec{a}_1$ und $\vec{a}_2$, jede Koordinate ist also
ein Skalarprodukt: $\vec{a}_1\cdot\vec{u} = 7$ und $\vec{a}_2\cdot\vec{u} = -1$.
Wir müssen weder ein Gleichungssystem lösen noch eine Inverse ausrechnen.

```{admonition} Wie berechnen wir Koordinaten bezüglich einer Orthonormalbasis?
:class: note
Die Spalten $\vec{m}_1, \ldots, \vec{m}_n$ einer orthogonalen
$n\times n$-Matrix $\mathbf{M}$ bilden eine Basis des $\mathbb{R}^n$, eine
sogenannte **Orthonormalbasis**. Für jeden Vektor $\vec{x} \in \mathbb{R}^n$
ist der Koordinatenvektor bezüglich dieser Basis

\begin{equation*}
[\vec{x}]_{\mathbf{M}} = \mathbf{M}^{\top}\vec{x}
= \begin{pmatrix} \vec{m}_1\cdot\vec{x} \\ \vdots \\ \vec{m}_n\cdot\vec{x} \end{pmatrix}.
\end{equation*}

Die $i$-te Koordinate ist das Skalarprodukt von $\vec{x}$ mit dem $i$-ten
Basisvektor.
```

Für unser Beispiel hat das Skalarprodukt $\vec{a}_1\cdot\vec{u} = 7$ auch eine
anschauliche Bedeutung. In der folgenden Abbildung gehen wir siebenmal den
Pfeil $\vec{a}_1$ entlang und dann einmal den Pfeil $\vec{a}_2$ rückwärts. Weil
$\vec{a}_2$ senkrecht auf $\vec{a}_1$ steht, knickt der Weg im rechten Winkel
ab. Der Punkt $7\,\vec{a}_1$ ist also der Fußpunkt des Lots, das wir von der
Spitze von $\vec{u}$ auf die Gerade durch $\vec{a}_1$ fällen.

```{figure} pics/vektor_orthonormalbasis.svg
---
name: vektor_orthonormalbasis
---
Darstellung des Vektors $\vec{u}$ bezüglich der Orthonormalbasis
$\vec{a}_1, \vec{a}_2$ mit ihrem Gitter.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Im rechtwinkligen Dreieck aus dem Ursprung, dem Lotfußpunkt und der Spitze von
$\vec{u}$ ist $\vec{u}$ die Hypotenuse. Die Koordinate $7$ ist die Länge der
Ankathete, also $|\vec{u}|\cos(\varphi)$ mit dem Winkel $\varphi$ zwischen
$\vec{u}$ und $\vec{a}_1$, und das ist wegen $|\vec{a}_1| = 1$ genau das
Skalarprodukt $\vec{a}_1\cdot\vec{u}$. Das Gitter der Orthonormalbasis ist
kein schiefes Gitter wie in Kapitel 5.1, sondern das gewohnte Kästchengitter,
nur gedreht. Deshalb können wir die Koordinaten wie gewohnt über das Lot
ablesen.

*Und im Raum?* Dort spielt die Orthonormalbasis ihren Vorteil erst richtig
aus. In Kapitel 5.1 haben wir die Koordinaten von $\vec{w} = (1, 2, 3)^{\top}$
bezüglich einer Basis des $\mathbb{R}^3$ mit dem Gauß-Algorithmus bestimmt.
Jetzt nehmen wir als Basis die Spalten $\vec{d}_1, \vec{d}_2, \vec{d}_3$ der
Matrix

\begin{equation*}
\mathbf{D} = \frac{1}{3}\begin{pmatrix} 2 & -1 & 2 \\ 2 & 2 & -1 \\ -1 & 2 & 2 \end{pmatrix}.
\end{equation*}

Jede Spalte hat die Länge $\frac{1}{3}\sqrt{4 + 4 + 1} = 1$, und die drei
Skalarprodukte $\vec{d}_1\cdot\vec{d}_2 = \frac{1}{9}(-2 + 4 - 2)$,
$\vec{d}_1\cdot\vec{d}_3 = \frac{1}{9}(4 - 2 - 2)$ und
$\vec{d}_2\cdot\vec{d}_3 = \frac{1}{9}(-2 - 2 + 4)$ sind alle $0$. Also ist
$\mathbf{D}$ orthogonal, und wir erhalten die Koordinaten mit drei
Skalarprodukten:

\begin{equation*}
[\vec{w}]_{\mathbf{D}} = \mathbf{D}^{\top}\vec{w}
= \frac{1}{3}\begin{pmatrix} 2 & 2 & -1 \\ -1 & 2 & 2 \\ 2 & -1 & 2 \end{pmatrix}
\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}
= \frac{1}{3}\begin{pmatrix} 2 + 4 - 3 \\ -1 + 4 + 6 \\ 2 - 2 + 6 \end{pmatrix}
= \begin{pmatrix} 1 \\ 3 \\ 2 \end{pmatrix}.
\end{equation*}

In den Zeilen von $\mathbf{D}^{\top}$ stehen die Basisvektoren
$\vec{d}_1, \vec{d}_2, \vec{d}_3$. Zur Probe rechnen wir
$\vec{d}_1 + 3\,\vec{d}_2 + 2\,\vec{d}_3
= \frac{1}{3}(2 - 3 + 4,\ 2 + 6 - 2,\ -1 + 6 + 4)^{\top} = (1, 2, 3)^{\top}$.
Statt Gauß-Algorithmus und Rückwärtseinsetzen mussten wir die Matrix nur
transponieren und multiplizieren. Auch die Inverse von $\mathbf{D}$ kennen wir
sofort, während wir sie bei einer beliebigen $3\times 3$-Matrix mit dem
Gauß-Jordan-Algorithmus aus Kapitel 2.2 berechnen müssten.

```{admonition} Dürfen wir Koordinaten immer als Skalarprodukte berechnen?
:class: danger
Nein, nur bezüglich einer Orthonormalbasis. Für die Basis
$\vec{b}_1, \vec{b}_2$ aus dem ersten Abschnitt und
$\vec{v} = (1, 5)^{\top}$ ergäben die Skalarprodukte
$\vec{b}_1\cdot\vec{v} = 2 + 5 = 7$ und $\vec{b}_2\cdot\vec{v} = -1 + 5 = 4$.
Der Koordinatenvektor aus Kapitel 5.1 ist aber
$[\vec{v}]_{\mathbf{B}} = (2, 3)^{\top}$, und die Probe
$7\,\vec{b}_1 + 4\,\vec{b}_2 = (14 - 4,\ 7 + 4)^{\top} = (10, 11)^{\top} \neq \vec{v}$
deckt den Fehler auf. Bevor wir Skalarprodukte verwenden, prüfen wir also, ob
die Basisvektoren orthonormal sind.
```

## Zusammenfassung und Ausblick

Eine quadratische Matrix ist orthogonal, wenn ihre Spalten orthonormal sind,
also die Länge $1$ haben und paarweise senkrecht aufeinander stehen. Dann gilt
$\mathbf{M}^{\top}\mathbf{M} = \mathbf{E}$, und die Inverse ist einfach die
Transponierte. Orthogonale Matrizen erhalten Skalarprodukte und damit Längen
und Winkel, und ihre Determinante ist $1$ oder $-1$, ohne dass umgekehrt jede
Matrix mit dieser Determinante orthogonal wäre. Bezüglich einer
Orthonormalbasis ist jede Koordinate ein Skalarprodukt mit einem Basisvektor.
In Kapitel 5.3 lernen wir mit dem Gram-Schmidt-Verfahren, wie wir aus einer
beliebigen Basis eine Orthonormalbasis bauen. In Kapitel 7 kommen dann die
Ideen aus Kapitel 5.1 und 5.2 zusammen: Für symmetrische Matrizen gibt es eine
Orthonormalbasis, in der die zugehörige Abbildung jeden Basisvektor nur
streckt.
