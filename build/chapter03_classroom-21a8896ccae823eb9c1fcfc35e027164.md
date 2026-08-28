# Geführte Übung zu Kapitel 3: Determinanten

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Zeitangaben sind Richtwerte,
wichtiger als exaktes Timing ist der Rhythmus aus Rechnen, Tafel und
Besprechen.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, Determinanten von 2x2 und 3x3 Matrizen (Kap. 3.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Laplacescher Entwicklungssatz (Kap. 3.2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, Eigenschaften von Determinanten (Kap. 3.3) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, Anwendungen der Determinante (Kap. 3.4) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Determinanten von 2x2 und 3x3 Matrizen

Bezug: Kapitel 3.1, Determinanten

```{admonition} Aufgabe 1: Determinanten berechnen
:class: tip
Eine Kopplungsmatrix zweier Freiheitsgrade lautet

$$\mathbf{K}_1 = \begin{pmatrix}3 & 4\\ 2 & 5\end{pmatrix}.$$

**a)** Berechnen Sie $\det(\mathbf{K}_1)$. Ist $\mathbf{K}_1$ invertierbar?

Für ein Bauteil mit drei gekoppelten Freiheitsgraden liegt die
Steifigkeitsmatrix

$$\mathbf{A} = \begin{pmatrix}
2 & 0 & 1 \\
3 & 1 & -1 \\
0 & 4 & 2 \\
\end{pmatrix}$$

vor.

**b)** Berechnen Sie $\det(\mathbf{A})$ mit der Regel von Sarrus. Notieren
Sie dabei die sechs Produkte einzeln.

**c)** Welche Bedeutung hat $\det(\mathbf{A}) \neq 0$ für die
Steifigkeitsmatrix eines Bauteils? Nutzen Sie den Zusammenhang zwischen
Determinante und Invertierbarkeit aus Kapitel 2.

**Zusatz (für schnelle Gruppen):** Ein Kommilitone behauptet, die Regel von
Sarrus funktioniere genauso für $4\times 4$ Matrizen, wenn man die ersten
drei Spalten rechts wiederholt. Stimmt das? Begründen Sie kurz in ein bis
zwei Sätzen.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** $\det(\mathbf{K}_1) = 3\cdot 5 - 2\cdot 4 = 15-8=7 \neq 0$, also ist
$\mathbf{K}_1$ invertierbar.

**b)** Mit $a_{11}=2, a_{12}=0, a_{13}=1, a_{21}=3, a_{22}=1, a_{23}=-1,
a_{31}=0, a_{32}=4, a_{33}=2$:
$$\text{positive Diagonalen: } 2\cdot 1\cdot 2 + 0\cdot(-1)\cdot 0 + 1\cdot
3\cdot 4 = 4+0+12=16$$
$$\text{negative Diagonalen: } 1\cdot 1\cdot 0 + 2\cdot(-1)\cdot 4 +
0\cdot 3\cdot 2 = 0-8+0=-8$$
$$\det(\mathbf{A}) = 16-(-8) = 24$$

**c)** Da $\det(\mathbf{A}) = 24 \neq 0$ ist, ist $\mathbf{A}$ invertierbar.
Das Bauteil reagiert damit auf jede Belastung mit einer eindeutig bestimmten
Verschiebung, das Gleichungssystem $\mathbf{A}\vec{x}=\vec{b}$ besitzt für
jeden Lastvektor $\vec{b}$ genau eine Lösung.

**Zusatz:** Nein, das stimmt nicht. Die Regel von Sarrus liefert genau die
sechs Diagonalprodukte, die zur Summe aus $3! = 6$ Termen einer $3\times 3$
Determinante passen. Eine $4\times 4$ Determinante besteht dagegen aus $4! =
24$ Termen, die sich nicht durch einfaches Diagonalenlesen erfassen lassen.
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe rechnet b) vollständig mit allen sechs Produkten an der
Tafel vor, a) und c) werden mündlich ergänzt. Coaching Impuls für c): Wo
haben wir den Ausdruck $a\cdot d - c\cdot b$ schon einmal in Kapitel 2
verwendet?
```

---

## Block 2 (0:25 bis 0:45) · Laplacescher Entwicklungssatz

Bezug: Kapitel 3.2, Laplacescher Entwicklungssatz

```{admonition} Aufgabe 2: Determinante einer 4x4 Matrix
:class: tip
Gegeben sei die Matrix

$$\mathbf{B} = \begin{pmatrix}
3 & 0 & 2 & 0 \\
1 & 4 & 0 & 5 \\
0 & 2 & 1 & 0 \\
2 & 0 & 0 & 3 \\
\end{pmatrix}.$$

**a)** Welche Zeile oder Spalte enthält die meisten Nullen? Begründen Sie,
warum sich diese Wahl für die Entwicklung besonders eignet.

**b)** Bestimmen Sie die Untermatrizen $\mathbf{B}_{32}$ und
$\mathbf{B}_{33}$.

**c)** Geben Sie das Vorzeichen $(-1)^{i+j}$ für die Positionen $(3,2)$ und
$(3,3)$ an.

**d)** Berechnen Sie $\det(\mathbf{B}_{32})$ und $\det(\mathbf{B}_{33})$ mit
der Regel von Sarrus.

**e)** Bestimmen Sie $\det(\mathbf{B})$ durch Entwicklung nach der dritten
Zeile.

**Zusatz (für schnelle Gruppen):** Entwickeln Sie stattdessen nach der
zweiten Spalte (ebenfalls zwei Nullen) und bestätigen Sie, dass sich
derselbe Wert für $\det(\mathbf{B})$ ergibt.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** Die dritte Zeile $(0, 2, 1, 0)$ enthält zwei Nullen, ebenso die
zweite Spalte $(0, 4, 2, 0)$. Beide eignen sich, da jede Null einen
Summanden der Entwicklung sofort auf Null setzt und eine vollständige
$3\times 3$ Rechnung erspart. Im Folgenden wird nach der dritten Zeile
entwickelt.

**b)**
$$\mathbf{B}_{32} = \begin{pmatrix}3 & 2 & 0\\ 1 & 0 & 5\\ 2 & 0 &
3\end{pmatrix}, \quad
\mathbf{B}_{33} = \begin{pmatrix}3 & 0 & 0\\ 1 & 4 & 5\\ 2 & 0 &
3\end{pmatrix}$$

**c)** $(-1)^{3+2} = -1$ und $(-1)^{3+3} = +1$.

**d)** Für $\mathbf{B}_{32}$: positive Diagonalen $3\cdot 0\cdot 3 +
2\cdot 5\cdot 2 + 0\cdot 1\cdot 0 = 0+20+0=20$, negative Diagonalen
$0\cdot 0\cdot 2 + 3\cdot 5\cdot 0 + 2\cdot 1\cdot 3 = 0+0+6=6$, also
$\det(\mathbf{B}_{32}) = 20-6=14$.

Für $\mathbf{B}_{33}$: positive Diagonalen $3\cdot 4\cdot 3 + 0\cdot 5\cdot
2 + 0\cdot 1\cdot 0 = 36+0+0=36$, negative Diagonalen $0\cdot 4\cdot 2 +
3\cdot 5\cdot 0 + 0\cdot 1\cdot 3 = 0$, also $\det(\mathbf{B}_{33}) =
36-0=36$.

**e)**
$$\det(\mathbf{B}) = 0 + (-1)\cdot 2\cdot 14 + 1\cdot 1\cdot 36 + 0 =
-28+36=8$$

**Zusatz:** Entwicklung nach der zweiten Spalte mit den Untermatrizen
$\mathbf{B}_{22} = \begin{pmatrix}3 & 2 & 0\\ 0 & 1 & 0\\ 2 & 0 &
3\end{pmatrix}$ (mit $\det(\mathbf{B}_{22})=9$) und $\mathbf{B}_{32}$ von
oben ($\det=14$) liefert
$$\det(\mathbf{B}) = (+1)\cdot 4\cdot 9 + (-1)\cdot 2\cdot 14 = 36-28=8$$
Das bestätigt den Wert aus e).
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe bearbeitet a) bis e) vollständig an der Tafel, den Zusatz
gegebenenfalls nur im Plenum diskutieren statt vollständig vorzurechnen.
Coaching Impuls für a): Wie viele Rechnungen sparen Sie sich pro Null in der
Entwicklungszeile?
```

---

## Block 3 (0:50 bis 1:10) · Eigenschaften von Determinanten

Bezug: Kapitel 3.3, Eigenschaften von Determinanten

```{admonition} Aufgabe 3: Rechenregeln anwenden ohne zu rechnen
:class: tip
Beantworten Sie die folgenden Teilaufgaben möglichst ohne die Regel von
Sarrus vollständig auszuführen, sondern durch direktes Anwenden der
Eigenschaften aus diesem Kapitel.

**a)** $\mathbf{C} = \begin{pmatrix}5 & -2 & 7\\ 0 & 0 & 0\\ 3 & 1 &
9\end{pmatrix}$. Bestimmen Sie $\det(\mathbf{C})$.

**b)** $\mathbf{D} = \begin{pmatrix}3 & 6 & 9\\ 1 & 2 & 3\\ 5 & 7 &
2\end{pmatrix}$. Bestimmen Sie $\det(\mathbf{D})$. Welchen Zusammenhang
zwischen zwei Zeilen erkennen Sie?

**c)** $\mathbf{E} = \begin{pmatrix}4 & 2 & 1\\ 0 & -3 & 5\\ 0 & 0 &
2\end{pmatrix}$. Bestimmen Sie $\det(\mathbf{E})$.

**d)** Für eine $3\times 3$ Matrix $\mathbf{F}$ gilt $\det(\mathbf{F})=5$.
Bestimmen Sie $\det(2\mathbf{F})$.

**e)** Für zwei $3\times 3$ Matrizen gilt $\det(\mathbf{G})=3$ und
$\det(\mathbf{H})=-4$. Bestimmen Sie $\det(\mathbf{G}\cdot\mathbf{H})$.

**f)** Für eine Matrix $\mathbf{A}$ gilt $\det(\mathbf{A})=7$. Zwei Zeilen
von $\mathbf{A}$ werden vertauscht. Wie lautet die neue Determinante?

**Zusatz:** Erklären Sie mit der Regel $\det(\mathbf{A}^{\top}) =
\det(\mathbf{A})$, warum man beim Prüfen der Invertierbarkeit einer Matrix
wahlweise die Matrix selbst oder ihre Transponierte betrachten kann.
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** $\det(\mathbf{C})=0$, da die zweite Zeile vollständig aus Nullen
besteht.

**b)** $\det(\mathbf{D})=0$. Die erste Zeile ist das Dreifache der zweiten
Zeile, $(3,6,9) = 3\cdot(1,2,3)$.

**c)** $\mathbf{E}$ ist eine obere Dreiecksmatrix, daher ist die
Determinante das Produkt der Diagonalelemente: $\det(\mathbf{E}) = 4\cdot
(-3)\cdot 2 = -24$.

**d)** Für eine $n\times n$ Matrix gilt $\det(s\cdot\mathbf{F}) = s^n
\cdot\det(\mathbf{F})$. Mit $n=3$ und $s=2$ folgt $\det(2\mathbf{F}) =
2^3\cdot 5 = 40$.

**e)** $\det(\mathbf{G}\cdot\mathbf{H}) = \det(\mathbf{G})\cdot\det(\mathbf{H})
= 3\cdot(-4) = -12$.

**f)** Beim Vertauschen zweier Zeilen wechselt das Vorzeichen der
Determinante, also ist die neue Determinante $-7$.

**Zusatz:** Da $\det(\mathbf{A}^{\top}) = \det(\mathbf{A})$ gilt, ist
$\det(\mathbf{A})$ genau dann ungleich Null, wenn $\det(\mathbf{A}^{\top})$
ungleich Null ist. Beide Matrizen sind also entweder gemeinsam invertierbar
oder gemeinsam nicht invertierbar, weshalb es für die Prüfung der
Invertierbarkeit keine Rolle spielt, welche der beiden Matrizen man
betrachtet.
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe stellt für jede Teilaufgabe kurz an der Tafel dar, welche
Regel angewendet wurde, ohne die volle Sarrus Rechnung durchzuführen.
Coaching Impuls für b): Gibt es einen Faktor, mit dem eine Zeile
multipliziert eine andere Zeile ergibt?
```

---

## Block 4 (1:10 bis 1:30) · Anwendungen der Determinante

Bezug: Kapitel 3.4, Anwendungen von Determinanten

```{admonition} Aufgabe 4: Volumenelement in der FEM
:class: tip
Ein Volumenelement wird durch drei Kantenvektoren beschrieben:

$$\vec{a} = \begin{pmatrix}3\\ 0\\ 0\end{pmatrix}, \quad
\vec{b} = \begin{pmatrix}0\\ 2\\ 0\end{pmatrix}, \quad
\vec{c} = \begin{pmatrix}1\\ 2\\ 5\end{pmatrix}.$$

**a)** Bilden Sie die Matrix $\mathbf{M}$ aus den drei Vektoren als Zeilen
und berechnen Sie $\det(\mathbf{M})$. Sind die drei Vektoren linear
abhängig oder linear unabhängig?

**b)** Nehmen Sie an, $\mathbf{M}$ ist die Steifigkeitsmatrix des Elements
und $\vec{x}$, $\vec{b}$ Verschiebungs- und Lastvektor. Besitzt
$\mathbf{M}\vec{x} = \vec{b}$ für jeden Lastvektor $\vec{b}$ eine eindeutige
Lösung? Begründen Sie mit dem Ergebnis aus a).

**c)** Berechnen Sie mit dem Spatprodukt das Volumen des von $\vec{a}$,
$\vec{b}$, $\vec{c}$ aufgespannten Parallelepipeds.

**d)** Berechnen Sie das Vektorprodukt $\vec{a}\times\vec{b}$ und geben Sie
an, welchen Flächeninhalt und welche Richtung das Ergebnis beschreibt.

**e)** Was würde es für die Vernetzung eines Bauteils in der FEM bedeuten,
wenn für ein Element $\det(\mathbf{M}) = 0$ gelten würde?

**Zusatz (für schnelle Gruppen):** Berechnen Sie das Volumen alternativ als
$V = |\vec{a}\times\vec{b}|\cdot h$, wobei $h$ die dritte Komponente von
$\vec{c}$ ist, und vergleichen Sie mit dem Ergebnis aus c).
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)**
$$\mathbf{M} = \begin{pmatrix}3 & 0 & 0\\ 0 & 2 & 0\\ 1 & 2 &
5\end{pmatrix}$$
$\mathbf{M}$ ist eine untere Dreiecksmatrix, daher $\det(\mathbf{M}) =
3\cdot 2\cdot 5 = 30 \neq 0$. Die drei Vektoren sind also linear
unabhängig.

**b)** Ja. Da $\det(\mathbf{M}) \neq 0$ ist, besitzt $\mathbf{M}\vec{x} =
\vec{b}$ für jeden Lastvektor $\vec{b}$ genau eine Lösung.

**c)** $V = |\det(\mathbf{M})| = |30| = 30$.

**d)**
$$\vec{a}\times\vec{b} = \begin{pmatrix}0\cdot 0 - 0\cdot 2\\ 0\cdot 0 -
3\cdot 0\\ 3\cdot 2 - 0\cdot 0\end{pmatrix} = \begin{pmatrix}0\\ 0\\
6\end{pmatrix}$$
Der Betrag $6$ ist der Flächeninhalt des von $\vec{a}$ und $\vec{b}$
aufgespannten Parallelogramms, die Richtung des Ergebnisvektors zeigt in
$z$ Richtung, senkrecht zur $xy$ Ebene, in der $\vec{a}$ und $\vec{b}$
liegen.

**e)** Das Element hätte kein Volumen (ein entartetes Element), die
Steifigkeitsmatrix wäre nicht invertierbar und die FEM Simulation würde
numerisch instabil oder gar nicht lösbar sein. Solche Elemente müssen bei
der Vernetzung vermieden werden.

**Zusatz:** $V = |\vec{a}\times\vec{b}|\cdot h = 6\cdot 5 = 30$. Das
stimmt exakt mit dem Ergebnis aus c) überein.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe bearbeitet a) bis d) vollständig an der Tafel, e) wird im
Plenum diskutiert. Da dies der letzte Block ist, eignet sich e) gut als
Ausblick auf Kapitel 4 zu Rang, Kern und Bild einer Matrix.
```
