---
authors:
  - name: Simone Gramsch
---

# 3.1 Determinanten

In Kapitel 2 haben wir inverse Matrizen berechnet und lineare Gleichungssysteme
gelöst. Dabei ist uns bei $2\times 2$-Matrizen ein unscheinbarer Ausdruck
begegnet, der darüber entscheidet, ob eine Matrix überhaupt invertierbar ist. In
diesem Abschnitt geben wir diesem Ausdruck einen Namen und übertragen ihn auf
$3\times 3$-Matrizen. Im Maschinenbau brauchen wir diese sogenannte Determinante
immer dann, wenn wir prüfen, ob ein Gleichungssystem eindeutig lösbar ist, und
bei der Berechnung von Eigenfrequenzen.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, was die **Determinante** einer quadratischen Matrix ist und
  wie sie mit der Invertierbarkeit zusammenhängt.
* [ ] Sie können die Determinante einer $2\times 2$-Matrix berechnen.
* [ ] Sie können den Betrag der Determinante einer $2\times 2$-Matrix als
  **Flächeninhalt eines Parallelogramms** deuten.
* [ ] Sie können die Determinante einer $3\times 3$-Matrix mit der **Regel von
  Sarrus** berechnen.
* [ ] Sie wissen, dass die Regel von Sarrus nur für $3\times 3$-Matrizen gilt.
```

## Wann ist eine $2\times 2$-Matrix invertierbar?

In Abschnitt 2.2 haben wir die Inverse der Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}
\end{equation*}

berechnet. Bevor wir die Formel für die Inverse anwenden durften, mussten wir
einen Test durchführen:

\begin{equation*}
2\cdot 5 - 1\cdot 3 = 7 \neq 0.
\end{equation*}

Dabei ist $2\cdot 5$ das Produkt der Einträge auf der Hauptdiagonalen von
$\mathbf{A}$ und $1\cdot 3$ das Produkt der beiden übrigen Einträge auf der
Nebendiagonalen. Weil die Differenz ungleich null ist, besitzt $\mathbf{A}$ eine
Inverse. Die $7$ tauchte dort sogar wieder auf, nämlich als Nenner des Bruchs
vor der Matrix.

*Aber was passiert, wenn diese Zahl null ist?* Wir betrachten die Matrix

\begin{equation*}
\mathbf{B} = \begin{pmatrix} 2 & 3 \\ 4 & 6 \end{pmatrix}
\end{equation*}

und führen denselben Test durch: $2\cdot 6 - 4\cdot 3 = 12 - 12 = 0$. In der
Formel für die Inverse müssten wir jetzt durch null teilen, und das ist nicht
erlaubt. Die Matrix $\mathbf{B}$ ist also nicht invertierbar. Auffällig ist,
dass die zweite Zeile von $\mathbf{B}$ genau doppelt so groß ist wie die erste.
Auf diesen Zusammenhang kommen wir in Abschnitt 3.3 zurück.

Eine einzige Zahl, die wir aus den vier Einträgen berechnen, entscheidet also
darüber, ob eine $2\times 2$-Matrix invertierbar ist. Weil diese Zahl so viel
über die Matrix verrät, bekommt sie einen eigenen Namen.

```{admonition} Was ist ... die Determinante einer $2\times 2$-Matrix?
:class: note
Die **Determinante** ist eine Funktion, die jeder quadratischen Matrix eine
reelle Zahl zuordnet. Für eine $2\times 2$-Matrix

\begin{equation*}
\mathbf{M} = \begin{pmatrix} a & b \\ c & d \end{pmatrix}
\end{equation*}

ist sie das Produkt der Hauptdiagonalen minus das Produkt der Nebendiagonalen:

\begin{equation*}
\det(\mathbf{M}) = a\cdot d - c\cdot b.
\end{equation*}

Manchmal werden die Matrixklammern auch durch zwei senkrechte Striche ersetzt:

\begin{equation*}
\left|\begin{matrix} a & b \\ c & d \end{matrix}\right| = a\cdot d - c\cdot b.
\end{equation*}
```

In diesem Skript verwenden wir die Funktionsschreibweise $\det(\cdot)$. Für
unsere beiden Beispielmatrizen erhalten wir

\begin{equation*}
\det(\mathbf{A}) = 2\cdot 5 - 1\cdot 3 = 7
\quad\text{und}\quad
\det(\mathbf{B}) = 2\cdot 6 - 4\cdot 3 = 0.
\end{equation*}

Mit der Determinante können wir die Inverse von $\mathbf{A}$ aus Abschnitt 2.2
kompakt schreiben. Wir vertauschen die beiden Einträge auf der Hauptdiagonalen,
ändern das Vorzeichen der beiden Einträge auf der Nebendiagonalen und teilen
durch die Determinante:

\begin{equation*}
\mathbf{A}^{-1} = \frac{1}{\det(\mathbf{A})}
\begin{pmatrix} 5 & -3 \\ -1 & 2 \end{pmatrix}
= \frac{1}{7} \begin{pmatrix} 5 & -3 \\ -1 & 2 \end{pmatrix}.
\end{equation*}

Die Determinante $\det(\mathbf{A}) = 7$ steht hier im Nenner. Zur Probe
multiplizieren wir $\mathbf{A}$ mit der Matrix ohne den Vorfaktor:

\begin{equation*}
\begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}
\begin{pmatrix} 5 & -3 \\ -1 & 2 \end{pmatrix}
= \begin{pmatrix} 10 - 3 & -6 + 6 \\ 5 - 5 & -3 + 10 \end{pmatrix}
= \begin{pmatrix} 7 & 0 \\ 0 & 7 \end{pmatrix}.
\end{equation*}

Auf der Diagonalen steht jeweils die Determinante $7$. Erst der Vorfaktor
$\frac{1}{7}$ macht daraus die Einheitsmatrix $\mathbf{E}$. Bei $\mathbf{B}$
stünde auf der Diagonalen eine $0$, und keine Zahl könnte daraus eine $1$
machen. Eine $2\times 2$-Matrix ist also genau dann invertierbar, wenn ihre
Determinante ungleich null ist.

## Was hat die Determinante mit Flächen zu tun?

Die Determinante lässt sich auch geometrisch deuten. Dazu fassen wir die beiden
Spalten von $\mathbf{A}$ als Vektoren in der Ebene auf:

\begin{equation*}
\vec{a}_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}, \quad
\vec{a}_2 = \begin{pmatrix} 3 \\ 5 \end{pmatrix}.
\end{equation*}

Die beiden Spaltenvektoren $\vec{a}_1$ und $\vec{a}_2$ spannen ein
Parallelogramm auf. Sein Flächeninhalt ist genau der Betrag der Determinante,
hier also $|\det(\mathbf{A})| = 7$. Am einfachsten sehen wir das an einer Matrix,
deren Spalten entlang der Koordinatenachsen zeigen:

\begin{equation*}
\det\begin{pmatrix} 3 & 0 \\ 0 & 2 \end{pmatrix} = 3\cdot 2 - 0\cdot 0 = 6.
\end{equation*}

Die Spalten $(3, 0)^{\top}$ und $(0, 2)^{\top}$ spannen ein Rechteck mit den
Seitenlängen $3$ und $2$ auf, und dessen Flächeninhalt ist tatsächlich $6$.

Den Betrag brauchen wir, weil die Determinante auch negativ sein kann.
Vertauschen wir die beiden Spalten von $\mathbf{A}$, erhalten wir
$3\cdot 1 - 5\cdot 2 = -7$. Das Parallelogramm ist dasselbe, nur die
Reihenfolge der Vektoren hat sich geändert. Bei $\mathbf{B}$ zeigen die Spalten
$(2, 4)^{\top}$ und $(3, 6)^{\top}$ in dieselbe Richtung. Das Parallelogramm
fällt zu einer Strecke zusammen und hat den Flächeninhalt $0$, passend zu
$\det(\mathbf{B}) = 0$. In Abschnitt 3.4 übertragen wir diese Idee auf drei
Vektoren im Raum. Dort wird aus der Fläche ein Volumen.

## Wie berechnen wir die Determinante einer $3\times 3$-Matrix?

Auch jede $3\times 3$-Matrix hat eine Determinante, und auch sie entscheidet
über die Invertierbarkeit. In Abschnitt 2.2 mussten wir für eine
$3\times 3$-Matrix den Gauß-Jordan-Algorithmus vollständig durchlaufen, um zu
erfahren, ob eine Inverse existiert. Mit der Determinante geht das schneller.
Wir betrachten die Matrix

\begin{equation*}
\mathbf{C} =
\begin{pmatrix}
2 & 1 & 3 \\
0 & -1 & 4 \\
5 & 2 & -2
\end{pmatrix}.
\end{equation*}

Die Idee aus dem $2\times 2$-Fall übertragen wir: Wir multiplizieren Einträge
entlang von Diagonalen. Produkte entlang der Diagonalen von links oben nach
rechts unten werden addiert, Produkte von links unten nach rechts oben werden
abgezogen. Damit jede Diagonale genau drei Einträge trifft, schreiben wir die
ersten beiden Spalten rechts noch einmal daneben:

\begin{equation*}
\begin{array}{ccc|cc}
2  &  1 &  3 & 2  &  1 \\
0  & -1 &  4 & 0  & -1 \\
5  &  2 & -2 & 5  &  2
\end{array}
\end{equation*}

Diese Hilfskonstruktion ist keine Matrix. Daher schreiben wir nicht
$\mathbf{C} = $ davor und erweitern auch nicht die Matrix selbst. Die folgende
Abbildung zeigt das Schema für allgemeine Einträge $a_{ij}$. Die wiederholten
Spalten sind grau, die Diagonalen, deren Produkte addiert werden, sind mit roten
Pfeilen markiert, und die Diagonalen, deren Produkte abgezogen werden, mit
blauen Pfeilen.

```{figure} pics/sarrus_rule.svg
---
class: responsive-figure-50
name: sarrus_rule
---
Eselsbrücke für die Regel von Sarrus
(Quelle: [Kmhkmh - Wikimedia](https://commons.wikimedia.org/w/index.php?curid=127614131);
Lizenz: CC BY 4.0)
```

Wir beginnen mit dem roten Pfeil ganz links und arbeiten uns nach rechts vor:

\begin{align*}
&\textcolor{red}{\text{1. roter Pfeil}} = 2 \cdot (-1) \cdot (-2) = 4, \\
&\textcolor{red}{\text{2. roter Pfeil}} = 1 \cdot 4 \cdot 5 = 20, \\
&\textcolor{red}{\text{3. roter Pfeil}} = 3 \cdot 0 \cdot 2 = 0.
\end{align*}

Dann beginnen wir wieder links und berechnen die Produkte entlang der blauen
Pfeile:

\begin{align*}
&\textcolor{blue}{\text{1. blauer Pfeil}} = 5 \cdot (-1) \cdot 3 = -15, \\
&\textcolor{blue}{\text{2. blauer Pfeil}} = 2 \cdot 4 \cdot 2 = 16, \\
&\textcolor{blue}{\text{3. blauer Pfeil}} = (-2) \cdot 0 \cdot 1 = 0.
\end{align*}

Die roten Produkte addieren wir, die blauen ziehen wir ab:

\begin{equation*}
\det(\mathbf{C}) = 4 + 20 + 0 - (-15) - 16 - 0 = 23.
\end{equation*}

Wir haben also sechs Produkte aus jeweils drei Einträgen gebildet. In jedem
Produkt kommt aus jeder Zeile und aus jeder Spalte genau ein Eintrag vor. Drei
Produkte gehen mit positivem Vorzeichen in die Summe ein, drei mit negativem.
Die allgemeine Formel ist schwer zu merken, das Schema mit den Pfeilen dagegen
leicht.

```{admonition} Was ist ... die Regel von Sarrus?
:class: note
Die Determinante einer $3\times 3$-Matrix

\begin{equation*}
\mathbf{M} =
\begin{pmatrix}
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}
\end{pmatrix}
\end{equation*}

berechnen wir mit der **Regel von Sarrus**:

\begin{align*}
\det(\mathbf{M}) =\; &a_{11} a_{22} a_{33} + a_{12} a_{23} a_{31}
+ a_{13} a_{21} a_{32} \\
&- a_{13} a_{22} a_{31} - a_{11} a_{23} a_{32} - a_{12} a_{21} a_{33}.
\end{align*}

Die ersten drei Summanden gehören zu den roten Pfeilen, die letzten drei zu den
blauen Pfeilen.
```

Zur Probe setzen wir die Einträge von $\mathbf{C}$ direkt in die Formel ein, ohne
das Pfeilschema zu benutzen:

\begin{align*}
\det(\mathbf{C})
&= 2\cdot(-1)\cdot(-2) + 1\cdot 4\cdot 5 + 3\cdot 0\cdot 2 \\
&\quad - 3\cdot(-1)\cdot 5 - 2\cdot 4\cdot 2 - 1\cdot 0\cdot(-2) \\
&= 4 + 20 + 0 + 15 - 16 - 0 = 23.
\end{align*}

Beide Wege liefern dasselbe Ergebnis. Wegen $\det(\mathbf{C}) = 23 \neq 0$ ist
$\mathbf{C}$ invertierbar, ohne dass wir die Inverse ausrechnen mussten. Dass
dieses Kriterium für quadratische Matrizen jeder Größe gilt, sehen wir in
Abschnitt 3.4.

```{admonition} Funktioniert die Regel von Sarrus auch für $4\times 4$-Matrizen?
:class: danger
Nein. Die Regel von Sarrus gilt ausschließlich für $3\times 3$-Matrizen.
Übertragen wir das Pfeilschema auf eine $4\times 4$-Matrix, erhalten wir nur
acht Produkte. Die Determinante einer $4\times 4$-Matrix besteht aber aus $24$
Summanden. Das Ergebnis wäre daher im Allgemeinen falsch.
```

```{dropdown} Video "Regel von Sarrus" von Mathematrick
<iframe width="1018" height="572" src="https://www.youtube.com/embed/dJ7d9wwC2sw" title="DETERMINANTE 3x3 Matrix berechnen - Regel von Sarrus, Matrizen, Beispiele" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Determinante berechnen (Sarrus)" von MathePeter
<iframe width="1018" height="572" src="https://www.youtube.com/embed/60OOoaX6UKM" title="Determinante berechnen (Regel von Sarrus)" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Die Determinante ordnet jeder quadratischen Matrix eine Zahl zu. Ist sie
ungleich null, ist die Matrix invertierbar, und bei $2\times 2$-Matrizen gibt
ihr Betrag den Flächeninhalt des Parallelogramms an, das die Spalten aufspannen.
Für $2\times 2$-Matrizen berechnen wir sie als Differenz zweier
Diagonalprodukte, für $3\times 3$-Matrizen mit der Regel von Sarrus. Für größere
Matrizen versagt jedes solche Diagonalschema. Der Laplacesche Entwicklungssatz
löst dieses Problem, indem er eine große Determinante schrittweise auf
$3\times 3$-Determinanten zurückführt. Im Kapitel über Eigenwerte wird dann
ausgerechnet die Frage, wann eine Determinante null wird, zum wichtigsten
Werkzeug.
