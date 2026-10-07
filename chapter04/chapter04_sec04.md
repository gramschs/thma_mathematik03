---
authors:
  - name: Simone Gramsch
---

# 4.4 Bild, Rang und Dimensionsformel

In Kapitel 4.3 haben wir untersucht, welche Eingabevektoren eine Matrix auf
den Nullvektor abbildet. Jetzt schauen wir auf die andere Seite der Abbildung
und fragen, welche Vektoren als Ergebnis überhaupt vorkommen. Beide Fragen
hängen über eine einfache Formel zusammen, und gemeinsam beantworten sie, wann
ein Gleichungssystem lösbar ist und wie viele Lösungen es hat. Im Maschinenbau
entscheidet genau das zum Beispiel darüber, ob ein Tragwerk statisch bestimmt
ist oder ob das Gleichungssystem einer FEM-Rechnung eine eindeutige Lösung
besitzt.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, was das **Bild** einer Matrix ist, und können es als
  **lineare Hülle** der Spalten angeben.
* [ ] Sie können die **Dimension** von Kern und Bild angeben.
* [ ] Sie können den **Rang** einer Matrix mit dem Gauß-Algorithmus
  bestimmen.
* [ ] Sie kennen die **Dimensionsformel**
  $\dim(\text{Kern}(\mathbf{M})) + \text{Rang}(\mathbf{M}) = n$ und können
  damit eine der beiden Größen aus der anderen berechnen.
* [ ] Sie können mit dem Kriterium $\vec{r} \in \text{Bild}(\mathbf{M})$
  entscheiden, ob ein Gleichungssystem lösbar ist, und seine Lösungsmenge mit
  dem Kern beschreiben.
```

## Welche Ausgabevektoren sind erreichbar?

Wir beginnen wieder mit der Projektion auf die $x$-Achse aus Kapitel 4.1,

\begin{equation*}
\mathbf{P} = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}, \quad
\mathbf{P}\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} x \\ 0 \end{pmatrix}.
\end{equation*}

Jeder Bildvektor hat die zweite Komponente $0$. Ein Vektor wie
$(0, 1)^{\top}$ kommt also nie als Ergebnis heraus, erreichbar ist nur die
$x$-Achse. Bei der Matrix $\mathbf{A}$ aus Kapitel 4.1 ist es anders. Zu jedem
Vektor $\vec{w}$ ist $\mathbf{A}^{-1}\vec{w}$ ein Eingabevektor mit dem Bild
$\vec{w}$, erreichbar ist also die ganze Ebene.

*Und wenn wir einer Matrix nicht sofort ansehen, was erreichbar ist?* Wir
nehmen das durchgehende Beispiel aus Kapitel 4.3,

\begin{equation*}
\mathbf{B} = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 1 & 0 \\ 1 & 1 & 1 \end{pmatrix},
\end{equation*}

mit den Spalten $\vec{b}_1 = (1, 2, 1)^{\top}$, $\vec{b}_2 = (2, 1, 1)^{\top}$
und $\vec{b}_3 = (3, 0, 1)^{\top}$. Nach Kapitel 4.1 ist
$\mathbf{B}\vec{v} = v_1\vec{b}_1 + v_2\vec{b}_2 + v_3\vec{b}_3$, erreichbar
sind also genau die Linearkombinationen der Spalten. In Kapitel 4.3 haben wir
aber $\vec{b}_3 = 2\,\vec{b}_2 - \vec{b}_1$ gefunden. Damit lässt sich jede
dieser Linearkombinationen ohne $\vec{b}_3$ schreiben:

\begin{equation*}
v_1\vec{b}_1 + v_2\vec{b}_2 + v_3\vec{b}_3
= v_1\vec{b}_1 + v_2\vec{b}_2 + v_3\big(2\,\vec{b}_2 - \vec{b}_1\big)
= (v_1 - v_3)\,\vec{b}_1 + (v_2 + 2v_3)\,\vec{b}_2.
\end{equation*}

Die dritte Spalte bringt also keine neue Richtung hinzu. Erreichbar sind genau
die Linearkombinationen von $\vec{b}_1$ und $\vec{b}_2$, und weil keiner der
beiden ein Vielfaches des anderen ist, füllen sie eine Ebene durch den
Ursprung. Für $\vec{v} = (1, 1, 1)^{\top}$ liefert die rechte Seite
$0\cdot\vec{b}_1 + 3\,\vec{b}_2 = (6, 3, 3)^{\top}$. Zur Probe rechnen wir
direkt $\mathbf{B}(1, 1, 1)^{\top} = (1 + 2 + 3,\ 2 + 1 + 0,\ 1 + 1 + 1)^{\top} = (6, 3, 3)^{\top}$.

```{admonition} Was ist ... das Bild einer Matrix?
:class: note
Das **Bild** einer $m\times n$-Matrix $\mathbf{M}$ ist die Menge aller
Vektoren, die $F_{\mathbf{M}}$ als Ergebnis liefert:

\begin{equation*}
\text{Bild}(\mathbf{M})
= \left\{ \mathbf{M}\vec{x} \;\middle|\; \vec{x} \in \mathbb{R}^n \right\}.
\end{equation*}

Es besteht aus allen Linearkombinationen der Spalten
$\vec{m}_1, \ldots, \vec{m}_n$. Die Menge aller Linearkombinationen gegebener
Vektoren heißt ihre **lineare Hülle** und wird mit spitzen Klammern
geschrieben, also
$\text{Bild}(\mathbf{M}) = \langle \vec{m}_1, \ldots, \vec{m}_n \rangle$.
```

Für unsere drei Matrizen erhalten wir
$\text{Bild}(\mathbf{P}) = \langle (1, 0)^{\top}, (0, 0)^{\top} \rangle = \langle (1, 0)^{\top} \rangle$,
denn die Nullspalte trägt nichts bei. Weiter ist
$\text{Bild}(\mathbf{A}) = \mathbb{R}^2$ und
$\text{Bild}(\mathbf{B}) = \langle \vec{b}_1, \vec{b}_2, \vec{b}_3 \rangle = \langle \vec{b}_1, \vec{b}_2 \rangle$.
Bei $\mathbf{B}$ mussten wir dafür die Abhängigkeit der Spalten schon kennen.
*Wie finden wir bei einer größeren Matrix heraus, welche Spalten überflüssig
sind?*

```{admonition} Besteht das Bild aus den Spalten der Matrix?
:class: danger
Nein. Die Spalten liegen im Bild, aber das Bild enthält zusätzlich alle ihre
Linearkombinationen. Bei $\mathbf{B}$ sind das unendlich viele Vektoren, die
eine ganze Ebene füllen, zum Beispiel $(6, 3, 3)^{\top}$, der keine Spalte von
$\mathbf{B}$ ist. Die Spalten spannen das Bild nur auf.
```

```{dropdown} Video "Bild einer Matrix berechnen" von Loay
<iframe width="1054" height="593" src="https://www.youtube.com/embed/FD03SOlmnvM"
title="BILD einer Matrix berechnen. Einfach und schnell erklärt" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Wie hängen Rang und Kern zusammen?

Der Kern von $\mathbf{B}$ ist nach Kapitel 4.3 die Gerade
$t\,(1, -2, 1)^{\top}$, das Bild ist die Ebene
$\langle \vec{b}_1, \vec{b}_2 \rangle$. Eine Gerade beschreiben wir mit einem
Parameter, eine Ebene mit zweien. *Wie messen wir diese Größe allgemein?* Auf
einer Geraden durch den Ursprung finden wir nie zwei linear unabhängige
Vektoren, denn je zwei sind Vielfache voneinander. In einer Ebene finden wir
zwei, aber keine drei.

```{admonition} Was ist ... die Dimension von Kern und Bild?
:class: note
Die **Dimension** von Kern oder Bild ist die größte Anzahl linear
unabhängiger Vektoren, die wir darin finden. Besteht die Menge nur aus dem
Nullvektor, ist die Dimension $0$. Die Dimension des Bildes heißt **Rang**
der Matrix:

\begin{equation*}
\text{Rang}(\mathbf{M}) = \dim\big(\text{Bild}(\mathbf{M})\big).
\end{equation*}
```

Für $\mathbf{B}$ ist also $\dim(\text{Kern}(\mathbf{B})) = 1$ und
$\text{Rang}(\mathbf{B}) = 2$. Beim Kern der $2\times 3$-Matrix $\mathbf{C}$
aus Kapitel 4.3 gehören zu den beiden freien Parametern die Vektoren
$(-2, 1, 0)^{\top}$ und $(1, 0, 1)^{\top}$. Sie sind linear unabhängig, denn
in der zweiten Komponente steht nur beim ersten, in der dritten nur beim
zweiten Vektor ein Eintrag ungleich null. So ist es immer: Jeder freie
Parameter liefert eine eigene Richtung, und die Dimension des Kerns ist die
Anzahl der freien Parameter.

*Und wie finden wir den Rang, ohne nach Abhängigkeiten zwischen den Spalten zu
suchen?* Wir schauen noch einmal auf die Zeilenstufenform von $\mathbf{B}$ aus
Kapitel 4.3:

\begin{equation*}
\begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ 0 & 0 & 0 \end{pmatrix}.
\end{equation*}

Die Pivotelemente stehen in der ersten und zweiten Spalte, und genau
$\vec{b}_1$ und $\vec{b}_2$ spannen das Bild auf. Die dritte Spalte gehört zum
freien Parameter $t$, und der Kernvektor mit $t = 1$ liefert
$\vec{b}_1 - 2\,\vec{b}_2 + \vec{b}_3 = \vec{0}$, also gerade ihre
Abhängigkeit von den Pivotspalten. Allgemein ist jede Spalte ohne
Pivotelement auf diese Weise eine Linearkombination der Pivotspalten. Die
Pivotspalten allein sind dagegen linear unabhängig, denn ohne die übrigen
Spalten bliebe kein freier Parameter übrig.

```{admonition} Was besagt die Dimensionsformel?
:class: note
Bringen wir eine $m\times n$-Matrix $\mathbf{M}$ auf Zeilenstufenform, so ist
$\text{Rang}(\mathbf{M})$ die Anzahl der Pivotelemente und
$\dim(\text{Kern}(\mathbf{M}))$ die Anzahl der Spalten ohne Pivotelement.
Zusammen ergibt sich die **Dimensionsformel**

\begin{equation*}
\dim\big(\text{Kern}(\mathbf{M})\big) + \text{Rang}(\mathbf{M}) = n.
\end{equation*}

Weil in jeder Zeile und in jeder Spalte höchstens ein Pivotelement steht, gilt
außerdem $\text{Rang}(\mathbf{M}) \leq \min(m, n)$.
```

Für $\mathbf{B}$ ist $1 + 2 = 3$, und $n = 3$ ist die Anzahl der Spalten. Bei
$\mathbf{C}$ sparen wir uns mit der Formel sogar die Suche nach dem Bild. Aus
$\dim(\text{Kern}(\mathbf{C})) = 2$ folgt $\text{Rang}(\mathbf{C}) = 3 - 2 = 1$,
und tatsächlich sind alle Spalten Vielfache der ersten, nämlich
$(2, 4)^{\top} = 2\,(1, 2)^{\top}$ und $(-1, -2)^{\top} = -(1, 2)^{\top}$.
Also ist $\text{Bild}(\mathbf{C}) = \langle (1, 2)^{\top} \rangle$ eine Gerade.
Anschaulich gehen von den $n$ Richtungen des Eingaberaums so viele verloren,
wie der Kern Dimensionen hat, und die übrigen bleiben im Bild erhalten.

```{admonition} Liegen Kern und Bild im selben Raum?
:class: danger
Nicht unbedingt. Für eine $m\times n$-Matrix besteht der Kern aus
Eingabevektoren im $\mathbb{R}^n$ und das Bild aus Bildvektoren im
$\mathbb{R}^m$. Bei $\mathbf{C}$ ist der Kern eine Ebene im $\mathbb{R}^3$,
das Bild dagegen eine Gerade im $\mathbb{R}^2$. Deshalb steht in der
Dimensionsformel rechts die Spaltenzahl $n$ und nicht die Zeilenzahl $m$.
```

```{dropdown} Video "Inverse matrices, column space and null space" von 3Blue1Brown
<iframe width="1018" height="572" src="https://www.youtube.com/embed/uQhTuRlWMxw" title="Inverse matrices, column space and null space | Chapter 7, Essence of linear algebra" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Wann ist ein Gleichungssystem lösbar?

In Kapitel 3.4 haben wir festgehalten, dass ein Gleichungssystem
$\mathbf{M}\vec{x} = \vec{r}$ mit $\det(\mathbf{M}) = 0$ entweder keine oder
unendlich viele Lösungen hat. Mit Bild und Kern können wir jetzt vorhersagen,
welcher Fall eintritt. Ein Vektor $\vec{x}$ löst $\mathbf{B}\vec{x} = \vec{r}$
genau dann, wenn $\vec{r}$ sein Bild ist. Das System ist also genau dann
lösbar, wenn $\vec{r}$ im Bild von $\mathbf{B}$ liegt. *Welche rechten Seiten
sind das?* Wir formen die erweiterte Koeffizientenmatrix aus Kapitel 2.4 mit
denselben Zeilenumformungen wie in Kapitel 4.3 um, diesmal mit einer
allgemeinen rechten Seite:

\begin{equation*}
\left(\begin{array}{ccc|c}
1 & 2 & 3 & r_1 \\ 2 & 1 & 0 & r_2 \\ 1 & 1 & 1 & r_3
\end{array}\right)
\;\to\;
\left(\begin{array}{ccc|c}
1 & 2 & 3 & r_1 \\ 0 & -3 & -6 & r_2 - 2r_1 \\ 0 & 0 & 0 & r_3 - \frac{1}{3}(r_1 + r_2)
\end{array}\right).
\end{equation*}

Die letzte Zeile lautet $0 = r_3 - \frac{1}{3}(r_1 + r_2)$. Das System ist
also genau dann lösbar, wenn $r_1 + r_2 - 3r_3 = 0$ gilt, und diese Gleichung
beschreibt die Ebene $\text{Bild}(\mathbf{B})$. Die Spalten erfüllen sie, etwa
$\vec{b}_1$ mit $1 + 2 - 3 = 0$. Für $\vec{r} = (1, 0, 0)^{\top}$ ist dagegen
$1 + 0 - 0 \neq 0$, die letzte Zeile wird zum Widerspruch
$0 = -\frac{1}{3}$, und es gibt keine Lösung.

Für die rechte Seite $\vec{r} = (6, 3, 3)^{\top}$ aus dem ersten Abschnitt ist
$6 + 3 - 9 = 0$. Rückwärtseinsetzen mit $x_3 = t$ liefert aus
$-3x_2 - 6t = 3 - 12 = -9$ den Wert $x_2 = 3 - 2t$ und aus
$x_1 + 2(3 - 2t) + 3t = 6$ den Wert $x_1 = t$. Die Lösungsmenge ist

\begin{equation*}
\vec{x} = \begin{pmatrix} 0 \\ 3 \\ 0 \end{pmatrix} +
t\begin{pmatrix} 1 \\ -2 \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}.
\end{equation*}

Das ist eine einzelne Lösung plus der Kern von $\mathbf{B}$. Für $t = 0$
erhalten wir die Darstellung $3\,\vec{b}_2$ aus dem ersten Abschnitt, für
$t = 1$ den Vektor $(1, 1, 1)^{\top}$, mit dem wir begonnen haben. Zur Probe
ist $\mathbf{B}(0, 3, 0)^{\top} = 3\,\vec{b}_2 = (6, 3, 3)^{\top}$, und der
Kernanteil trägt wegen $\mathbf{B}(1, -2, 1)^{\top} = \vec{0}$ nichts bei. Das
ist kein Zufall: Lösen $\vec{x}$ und $\vec{y}$ beide das System, so ist
$\mathbf{B}(\vec{x} - \vec{y}) = \vec{r} - \vec{r} = \vec{0}$, ihre Differenz
liegt also im Kern.

```{admonition} Wann ist ein Gleichungssystem lösbar?
:class: note
Für eine $m\times n$-Matrix $\mathbf{M}$ und $\vec{r} \in \mathbb{R}^m$ gilt:

* $\mathbf{M}\vec{x} = \vec{r}$ ist genau dann lösbar, wenn
  $\vec{r} \in \text{Bild}(\mathbf{M})$ ist. In der Zeilenstufenform der
  erweiterten Koeffizientenmatrix trifft dann keine Nullzeile links auf eine
  Zahl ungleich null rechts.
* Ist $\vec{x}_p$ eine Lösung, besteht die Lösungsmenge aus allen Vektoren
  $\vec{x}_p + \vec{k}$ mit $\vec{k} \in \text{Kern}(\mathbf{M})$.
* Die Lösung ist also genau dann eindeutig, wenn
  $\text{Kern}(\mathbf{M}) = \{\vec{0}\}$ ist, also wenn
  $\text{Rang}(\mathbf{M}) = n$ gilt.
```

Jetzt verstehen wir auch die Aussage aus Kapitel 3.4. Eine quadratische Matrix
mit $\det(\mathbf{M}) \neq 0$ hat linear unabhängige Spalten und damit den
Rang $n$. Nach der Dimensionsformel ist ihr Kern $\{\vec{0}\}$, und ihr Bild
füllt mit $n$ Dimensionen den ganzen $\mathbb{R}^n$, also gibt es für jede
rechte Seite genau eine Lösung. Bei $\det(\mathbf{M}) = 0$ ist der Rang
kleiner als $n$. Dann ist das Bild zu klein für manche rechten Seiten, und wo
es eine Lösung gibt, kommt mit dem Kern eine ganze Schar weiterer Lösungen
dazu.

```{admonition} Hat ein Gleichungssystem mit mehr Unbekannten als Gleichungen immer unendlich viele Lösungen?
:class: danger
Nein, es kann auch unlösbar sein. Für $\mathbf{C}$ aus Kapitel 4.3 und
$\vec{r} = (1, 0)^{\top}$ lauten die Gleichungen $x_1 + 2x_2 - x_3 = 1$ und
$2x_1 + 4x_2 - 2x_3 = 0$. Die linke Seite der zweiten Gleichung ist das
Doppelte der ersten, die rechte nicht, also gibt es keine Lösung. Richtig ist
nur: Wenn ein solches System lösbar ist, hat es unendlich viele Lösungen, denn
nach der Dimensionsformel hat der Kern mindestens die Dimension $n - m \geq 1$.
```

Zum Abschluss fassen wir zusammen, wie der Rang einer $m\times n$-Matrix über
die Lösungen von $\mathbf{M}\vec{x} = \vec{r}$ entscheidet. Wegen
$\text{Rang}(\mathbf{M}) \leq \min(m, n)$ gibt es genau vier Fälle.

| Fall | $\dim(\text{Kern})$ | Lösungen von $\mathbf{M}\vec{x} = \vec{r}$ | Beispiel |
| --- | --- | --- | --- |
| $\text{Rang} = m = n$ | $0$ | genau eine für jedes $\vec{r}$ | $\mathbf{A}$ |
| $\text{Rang} = n < m$ | $0$ | keine oder genau eine | $4\times 3$-Matrix $\mathbf{V}$ aus Kapitel 4.3 |
| $\text{Rang} = m < n$ | $n - m$ | unendlich viele für jedes $\vec{r}$ | Projektion vom $\mathbb{R}^3$ in den $\mathbb{R}^2$ aus Kapitel 4.1 |
| $\text{Rang} < m$ und $\text{Rang} < n$ | $n - \text{Rang}$ | keine oder unendlich viele | $\mathbf{P}$, $\mathbf{B}$, $\mathbf{C}$ |

```{dropdown} Video "Rang einer Matrix, Lösbarkeit von LGS" von Mathematische Methoden
<iframe width="1020" height="574" src="https://www.youtube.com/embed/UNDha90yrT0"
title="0162 Rang einer Matrix Lösbarkeit von LGS" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Das Bild einer Matrix ist die lineare Hülle ihrer Spalten, und seine Dimension
ist der Rang. Wir bestimmen ihn wie den Kern mit dem Gauß-Algorithmus, indem
wir die Pivotelemente zählen, und die Dimensionsformel verbindet beide Größen
mit der Spaltenzahl. Ein Gleichungssystem ist genau dann lösbar, wenn die
rechte Seite im Bild liegt, und seine Lösungen unterscheiden sich um Vektoren
aus dem Kern. In Kapitel 5.1 nennen wir linear unabhängige Vektoren, deren
lineare Hülle der ganze Raum ist, eine Basis und stellen Vektoren in einer
solchen Basis dar. Die Dimensionsformel begegnet uns in Kapitel 6 wieder, wenn
wir zählen, wie viele linear unabhängige Eigenvektoren zu einem Eigenwert
gehören.
