# Geführte Übung zu Kapitel 2: Transponierte, inverse Matrizen und lineare Gleichungssysteme

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
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, transponierte und symmetrische Matrizen (Kap. 2.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, inverse Matrizen (Kap. 2.2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, Rechenregeln und Matrizengleichungen (Kap. 2.3) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, lineare Gleichungssysteme lösen (Kap. 2.4) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Transponierte und symmetrische Matrizen

Bezug: Kapitel 2.1, Transponierte und symmetrische Matrizen

```{admonition} Aufgabe 1: Sensormatrix transponieren und Symmetrie prüfen
:class: tip
Ein Beschleunigungssensor misst an vier Zeitpunkten jeweils die drei
Achsen $x, y, z$ (Werte in $\text{m/s}^2$). Die Messreihe wird als Matrix
$\mathbf{A}$ gespeichert, jede Zeile ein Zeitpunkt, jede Spalte eine Achse:

$$\mathbf{A} = \begin{pmatrix}
2 & -1 & 0 \\
3 & 0 & 1 \\
-2 & 4 & 2 \\
1 & 1 & -3 \\
\end{pmatrix}$$

**a)** Welche Dimension hat $\mathbf{A}$? Bestimmen Sie $\mathbf{A}^{\top}$.

**b)** Welche Dimension hat $\mathbf{A}^{\top}$? Bestätigen Sie damit die
allgemeine Regel für die Dimension einer transponierten Matrix.

Für die weitere Auswertung wird zusätzlich der Abstand zwischen vier
Bohrungen auf einer Bauteilplatte in der Matrix $\mathbf{D}$ erfasst (Werte
in mm), $d_{ij}$ ist der Abstand zwischen Bohrung $i$ und Bohrung $j$:

$$\mathbf{D} = \begin{pmatrix}
0 & 12 & 8 & 5 \\
12 & 0 & 7 & 9 \\
8 & 7 & 0 & 4 \\
5 & 9 & 4 & 0 \\
\end{pmatrix}$$

**c)** Prüfen Sie rechnerisch mit der Definition, ob $\mathbf{D}$ symmetrisch
ist.

**d)** Nennen Sie ein Element außerhalb der Hauptdiagonale von $\mathbf{D}$
und sein Partnerelement, das wegen der Symmetrie denselben Wert haben muss.

Betrachten Sie zusätzlich die Matrizen

$$\mathbf{A}_2 = \begin{pmatrix}3 & 1\\ 0 & 2\end{pmatrix}, \quad
\mathbf{B}_2 = \begin{pmatrix}1 & 4\\ 2 & -1\end{pmatrix}.$$

**e)** Bestätigen Sie an diesem Beispiel die Rechenregel
$(\mathbf{A}_2+\mathbf{B}_2)^{\top} = \mathbf{A}_2^{\top}+\mathbf{B}_2^{\top}$
durch vollständiges Nachrechnen beider Seiten.

**Zusatz (für schnelle Gruppen):** Bestätigen Sie mit denselben Matrizen
$\mathbf{A}_2$ und $\mathbf{B}_2$ auch die Regel
$(\mathbf{A}_2\cdot\mathbf{B}_2)^{\top} = \mathbf{B}_2^{\top}\cdot\mathbf{A}_2^{\top}$.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** $\mathbf{A}$ hat die Dimension $4\times 3$.

$$\mathbf{A}^{\top} = \begin{pmatrix}
2 & 3 & -2 & 1 \\
-1 & 0 & 4 & 1 \\
0 & 1 & 2 & -3 \\
\end{pmatrix}$$

**b)** $\mathbf{A}^{\top}$ hat die Dimension $3\times 4$. Aus einer
$m\times n$ Matrix wird beim Transponieren eine $n\times m$ Matrix, hier also
aus $4\times 3$ die Dimension $3\times 4$.

**c)** Es gilt $d_{12}=d_{21}=12$, $d_{13}=d_{31}=8$, $d_{14}=d_{41}=5$,
$d_{23}=d_{32}=7$, $d_{24}=d_{42}=9$ und $d_{34}=d_{43}=4$. Für alle Indizes
$i,j$ gilt $d_{ij}=d_{ji}$, also ist $\mathbf{D}$ symmetrisch.

**d)** Zum Beispiel gehört zu $d_{13}=8$ (Bohrung 1 zu Bohrung 3) das
Partnerelement $d_{31}=8$ (Bohrung 3 zu Bohrung 1), beide haben denselben
Wert.

**e)** Linke Seite:
$$\mathbf{A}_2+\mathbf{B}_2 = \begin{pmatrix}4 & 5\\ 2 & 1\end{pmatrix}
\Rightarrow (\mathbf{A}_2+\mathbf{B}_2)^{\top} =
\begin{pmatrix}4 & 2\\ 5 & 1\end{pmatrix}.$$
Rechte Seite:
$$\mathbf{A}_2^{\top} = \begin{pmatrix}3 & 0\\ 1 & 2\end{pmatrix}, \quad
\mathbf{B}_2^{\top} = \begin{pmatrix}1 & 2\\ 4 & -1\end{pmatrix} \Rightarrow
\mathbf{A}_2^{\top}+\mathbf{B}_2^{\top} =
\begin{pmatrix}4 & 2\\ 5 & 1\end{pmatrix}.$$
Beide Seiten stimmen überein.

**Zusatz:**
$$\mathbf{A}_2\cdot\mathbf{B}_2 = \begin{pmatrix}5 & 11\\ 4 &
-2\end{pmatrix} \Rightarrow (\mathbf{A}_2\cdot\mathbf{B}_2)^{\top} =
\begin{pmatrix}5 & 4\\ 11 & -2\end{pmatrix}.$$
$$\mathbf{B}_2^{\top}\cdot\mathbf{A}_2^{\top} =
\begin{pmatrix}1 & 2\\ 4 & -1\end{pmatrix}\cdot
\begin{pmatrix}3 & 0\\ 1 & 2\end{pmatrix} =
\begin{pmatrix}5 & 4\\ 11 & -2\end{pmatrix}.$$
Beide Seiten stimmen überein, die Reihenfolge dreht sich bei der
Multiplikation also tatsächlich um.
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe bearbeitet a) bis d) vollständig, e) wird mündlich ergänzt.
Coaching Impuls für c): Welche zwei Zahlen müssen Sie an jeder Position
vergleichen, damit die Definition erfüllt ist?
```

---

## Block 2 (0:25 bis 0:45) · Inverse Matrizen

Bezug: Kapitel 2.2, Inverse Matrizen

```{admonition} Aufgabe 2: Inverse Matrizen bestimmen
:class: tip
Eine Kopplungsmatrix zweier Freiheitsgrade eines schwingenden Systems lautet

$$\mathbf{K} = \begin{pmatrix}4 & 1\\ 2 & 3\end{pmatrix}.$$

**a)** Prüfen Sie mit dem Ausdruck $a\cdot d - c\cdot b$, ob $\mathbf{K}$
invertierbar ist, und bestimmen Sie $\mathbf{K}^{-1}$.

**b)** Machen Sie die Probe, indem Sie $\mathbf{K}\cdot \mathbf{K}^{-1}$
berechnen.

Eine Dämpfungsmatrix eines entkoppelten Systems lautet

$$\mathbf{C} = \text{diag}(5,\ 0{,}2,\ 10)\ \left[\text{Ns/m}\right].$$

**c)** Geben Sie $\mathbf{C}^{-1}$ direkt mit der Kehrwertregel für
Diagonalmatrizen an.

**d)** Angenommen, ein Diagonaleintrag von $\mathbf{C}$ wäre Null. Warum wäre
$\mathbf{C}$ dann nicht invertierbar?

Für die $3\times 3$ Matrix

$$\mathbf{A}_3 = \begin{pmatrix}1 & 2 & 1\\ 2 & 5 & 0\\ 1 & 0 &
3\end{pmatrix}$$

soll die Inverse mit dem Gauß Jordan Algorithmus bestimmt werden.

**e)** Schreiben Sie die Einheitsmatrix $\mathbf{E}_3$ rechts neben
$\mathbf{A}_3$ und führen Sie nur den ersten Eliminationsschritt durch, das
heißt erzeugen Sie mit dem Pivotelement $a_{11}=1$ Nullen unterhalb davon in
der ersten Spalte. Geben Sie die resultierende erweiterte Matrix an.

**f)** Beschreiben Sie in Stichworten, welche weiteren Schritte nötig wären,
um $\mathbf{A}_3$ vollständig zu invertieren. Eine vollständige Rechnung ist
hier nicht gefordert.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** $a\cdot d - c\cdot b = 4\cdot 3 - 2\cdot 1 = 12-2=10 \neq 0$, also ist
$\mathbf{K}$ invertierbar.
$$\mathbf{K}^{-1} = \frac{1}{10}\begin{pmatrix}3 & -1\\ -2 & 4\end{pmatrix}$$

**b)**
$$\mathbf{K}\cdot \mathbf{K}^{-1} = \frac{1}{10}\begin{pmatrix}12-2 &
-4+4\\ 6-6 & -2+12\end{pmatrix} = \frac{1}{10}\begin{pmatrix}10 & 0\\ 0 &
10\end{pmatrix} = \begin{pmatrix}1 & 0\\ 0 & 1\end{pmatrix} \checkmark$$

**c)** $\mathbf{C}^{-1} = \text{diag}(0{,}2,\ 5,\ 0{,}1)$, da $1/5=0{,}2$,
$1/0{,}2=5$ und $1/10=0{,}1$.

**d)** Bei einer Inversen einer Diagonalmatrix wird jeder Diagonaleintrag
durch seinen Kehrwert ersetzt. Der Kehrwert von Null ist nicht definiert
(Division durch Null), also besäße $\mathbf{C}$ in diesem Fall keine
Inverse.

**e)** Ausgangspunkt:
$$\left(\begin{array}{ccc|ccc}
1 & 2 & 1 & 1 & 0 & 0 \\
2 & 5 & 0 & 0 & 1 & 0 \\
1 & 0 & 3 & 0 & 0 & 1 \\
\end{array}\right)$$
Nach $Z_2 \to Z_2 - 2\cdot Z_1$ und $Z_3 \to Z_3 - 1\cdot Z_1$:
$$\left(\begin{array}{ccc|ccc}
1 & 2 & 1 & 1 & 0 & 0 \\
0 & 1 & -2 & -2 & 1 & 0 \\
0 & -2 & 2 & -1 & 0 & 1 \\
\end{array}\right)$$

**f)** Als nächstes wird mit dem Pivotelement $a_{22}=1$ sowohl oberhalb als
auch unterhalb in der zweiten Spalte eine Null erzeugt. Danach wird das
verbleibende Element in der dritten Spalte auf ein Pivotelement gleich Eins
normiert und damit oberhalb Nullen erzeugt, bis links die Einheitsmatrix
steht. Die rechte Seite ist dann die gesuchte inverse Matrix
$\mathbf{A}_3^{-1}$.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet a) bis c) vollständig, e) wird ebenfalls an der
Tafel durchgeführt, f) wird mündlich im Plenum ergänzt. Coaching Impuls für
d): Was passiert bei reellen Zahlen, wenn Sie versuchen, durch Null zu
teilen?
```

---

## Block 3 (0:50 bis 1:10) · Rechenregeln und Matrizengleichungen

Bezug: Kapitel 2.3, Rechenregeln inverse Matrizen

```{admonition} Aufgabe 3: Rechenregeln und Matrizengleichungen
:class: tip
Gegeben seien die Matrizen

$$\mathbf{A} = \begin{pmatrix}1 & 0\\ 1 & 1\end{pmatrix}, \quad
\mathbf{B} = \begin{pmatrix}2 & 0\\ 0 & 1\end{pmatrix}.$$

**a)** Bestimmen Sie $\mathbf{A}^{-1}$ und $\mathbf{B}^{-1}$, berechnen Sie
anschließend $\mathbf{A}\cdot\mathbf{B}$ sowie $(\mathbf{A}\cdot\mathbf{B})^{-1}$
und getrennt davon $\mathbf{B}^{-1}\cdot\mathbf{A}^{-1}$. Bestätigen Sie
damit die Regel $(\mathbf{A}\cdot\mathbf{B})^{-1} =
\mathbf{B}^{-1}\cdot\mathbf{A}^{-1}$.

**b)** Gegeben sei die symmetrische Matrix
$\mathbf{S} = \begin{pmatrix}4 & 2\\ 2 & 3\end{pmatrix}$. Ist
$\mathbf{S}^{-1}$ ebenfalls symmetrisch? Begründen Sie ohne zu rechnen,
allein mit der passenden Rechenregel.

Für die folgenden Teilaufgaben gilt

$$\mathbf{A}_k = \begin{pmatrix}3 & 1\\ 2 & 1\end{pmatrix}, \quad
\mathbf{B}_k = \begin{pmatrix}5 & 4\\ 3 & 2\end{pmatrix}.$$

**c)** Lösen Sie die Matrizengleichung $\mathbf{A}_k\mathbf{X} = \mathbf{B}_k$
nach $\mathbf{X}$ auf und machen Sie die Probe.

**d)** Lösen Sie die Matrizengleichung $\mathbf{Y}\mathbf{A}_k = \mathbf{B}_k$
nach $\mathbf{Y}$ auf und machen Sie die Probe.

**e)** Vergleichen Sie die Ergebnisse aus c) und d). Warum unterscheiden sich
$\mathbf{X}$ und $\mathbf{Y}$, obwohl beide Male dieselben Matrizen
$\mathbf{A}_k$ und $\mathbf{B}_k$ verwendet wurden?
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** $\mathbf{A}^{-1} = \begin{pmatrix}1 & 0\\ -1 & 1\end{pmatrix}$,
$\mathbf{B}^{-1} = \begin{pmatrix}0{,}5 & 0\\ 0 & 1\end{pmatrix}$.
$$\mathbf{A}\cdot\mathbf{B} = \begin{pmatrix}2 & 0\\ 2 & 1\end{pmatrix}
\Rightarrow (\mathbf{A}\cdot\mathbf{B})^{-1} = \begin{pmatrix}0{,}5 & 0\\ -1
& 1\end{pmatrix}$$
$$\mathbf{B}^{-1}\cdot\mathbf{A}^{-1} =
\begin{pmatrix}0{,}5 & 0\\ 0 & 1\end{pmatrix}\cdot
\begin{pmatrix}1 & 0\\ -1 & 1\end{pmatrix} =
\begin{pmatrix}0{,}5 & 0\\ -1 & 1\end{pmatrix}$$
Beide Ergebnisse stimmen überein, die Regel ist bestätigt.

**b)** Ja, die Inverse einer symmetrischen Matrix ist wieder symmetrisch.
Das ist eine der Rechenregeln aus diesem Kapitel und gilt unabhängig von den
konkreten Werten in $\mathbf{S}$, solange $\mathbf{S}$ invertierbar ist.

**c)** $\det(\mathbf{A}_k) = 3\cdot 1 - 2\cdot 1 = 1$, also
$\mathbf{A}_k^{-1} = \begin{pmatrix}1 & -1\\ -2 & 3\end{pmatrix}$.
$$\mathbf{X} = \mathbf{A}_k^{-1}\mathbf{B}_k =
\begin{pmatrix}1 & -1\\ -2 & 3\end{pmatrix}
\begin{pmatrix}5 & 4\\ 3 & 2\end{pmatrix} =
\begin{pmatrix}2 & 2\\ -1 & -2\end{pmatrix}$$
Probe: $\mathbf{A}_k\mathbf{X} = \begin{pmatrix}3 & 1\\ 2 &
1\end{pmatrix}\begin{pmatrix}2 & 2\\ -1 & -2\end{pmatrix} =
\begin{pmatrix}5 & 4\\ 3 & 2\end{pmatrix} = \mathbf{B}_k$ ✓

**d)**
$$\mathbf{Y} = \mathbf{B}_k\mathbf{A}_k^{-1} =
\begin{pmatrix}5 & 4\\ 3 & 2\end{pmatrix}
\begin{pmatrix}1 & -1\\ -2 & 3\end{pmatrix} =
\begin{pmatrix}-3 & 7\\ -1 & 3\end{pmatrix}$$
Probe: $\mathbf{Y}\mathbf{A}_k = \begin{pmatrix}-3 & 7\\ -1 &
3\end{pmatrix}\begin{pmatrix}3 & 1\\ 2 & 1\end{pmatrix} =
\begin{pmatrix}5 & 4\\ 3 & 2\end{pmatrix} = \mathbf{B}_k$ ✓

**e)** Die Matrizenmultiplikation ist nicht kommutativ. Bei
$\mathbf{A}_k\mathbf{X}=\mathbf{B}_k$ muss von links mit
$\mathbf{A}_k^{-1}$ multipliziert werden, bei
$\mathbf{Y}\mathbf{A}_k=\mathbf{B}_k$ von rechts. Da die Reihenfolge der
Multiplikation das Ergebnis verändert, führen beide Wege im Allgemeinen zu
unterschiedlichen Lösungen.
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe rechnet c) und d) vollständig inklusive Probe an der Tafel,
a) und b) werden mündlich ergänzt. Coaching Impuls für e): Auf welcher Seite
der ursprünglichen Gleichung steht $\mathbf{A}_k$, und auf welcher Seite
multiplizieren Sie deshalb mit der Inversen?
```

---

## Block 4 (1:10 bis 1:30) · Lineare Gleichungssysteme lösen

Bezug: Kapitel 2.4, Lineare Gleichungssysteme mit Matrizenrechnung lösen

```{admonition} Aufgabe 4: Kräftegleichgewicht als lineares Gleichungssystem
:class: tip
An einem Fachwerkknoten mit zwei Stäben ergibt sich aus dem
Kräftegleichgewicht in $x$ und $y$ Richtung das folgende Gleichungssystem
für die beiden unbekannten Stabkräfte $F_1$ und $F_2$ (Kräfte in N):

$$2F_1 + F_2 = 700$$
$$F_1 + 3F_2 = 900$$

**a)** Stellen Sie das System in Matrixform $\mathbf{A}\vec{x}=\vec{b}$ dar
und benennen Sie die Koeffizientenmatrix $\mathbf{A}$, den Vektor der
Unbekannten $\vec{x}$ und den Ergebnisvektor $\vec{b}$.

**b)** Berechnen Sie $\det(\mathbf{A})$ und prüfen Sie, ob $\mathbf{A}$
invertierbar ist.

**c)** Bestimmen Sie $\mathbf{A}^{-1}$.

**d)** Berechnen Sie die Lösung $\vec{x} = \mathbf{A}^{-1}\vec{b}$ und
machen Sie die Probe an beiden ursprünglichen Gleichungen.

**e)** Im nächsten Lastfall ändert sich der Ergebnisvektor zu
$\vec{b}_2 = \begin{pmatrix}500\\ 750\end{pmatrix}$, während die
Koeffizientenmatrix $\mathbf{A}$ gleich bleibt. Bestimmen Sie die neue
Lösung, ohne die Inverse erneut zu berechnen.

**f)** Nennen Sie eine Situation aus dem Maschinenbau, in der genau dieses
Vorgehen, gleiche Koeffizientenmatrix mit mehreren unterschiedlichen
Ergebnisvektoren, praktisch nützlich ist.
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)**
$$\mathbf{A} = \begin{pmatrix}2 & 1\\ 1 & 3\end{pmatrix}, \quad
\vec{x} = \begin{pmatrix}F_1\\ F_2\end{pmatrix}, \quad
\vec{b} = \begin{pmatrix}700\\ 900\end{pmatrix}$$

**b)** $\det(\mathbf{A}) = 2\cdot 3 - 1\cdot 1 = 5 \neq 0$, also ist
$\mathbf{A}$ invertierbar.

**c)** $\mathbf{A}^{-1} = \dfrac{1}{5}\begin{pmatrix}3 & -1\\ -1 &
2\end{pmatrix}$

**d)**
$$\vec{x} = \mathbf{A}^{-1}\vec{b} = \frac{1}{5}\begin{pmatrix}3 & -1\\ -1
& 2\end{pmatrix}\begin{pmatrix}700\\ 900\end{pmatrix} =
\frac{1}{5}\begin{pmatrix}1200\\ 1100\end{pmatrix} =
\begin{pmatrix}240\\ 220\end{pmatrix}$$
Also $F_1 = 240$ N und $F_2 = 220$ N. Probe: $2\cdot 240+220=700$ ✓,
$240+3\cdot 220=900$ ✓

**e)**
$$\vec{x}_2 = \mathbf{A}^{-1}\vec{b}_2 = \frac{1}{5}\begin{pmatrix}3 & -1\\
-1 & 2\end{pmatrix}\begin{pmatrix}500\\ 750\end{pmatrix} =
\frac{1}{5}\begin{pmatrix}750\\ 1000\end{pmatrix} =
\begin{pmatrix}150\\ 200\end{pmatrix}$$
Also $F_1 = 150$ N und $F_2 = 200$ N für den neuen Lastfall.

**f)** Zum Beispiel in der FEM, wenn ein Bauteil mit derselben
Steifigkeitsmatrix für mehrere unterschiedliche Lastfälle ausgewertet werden
soll. Die Inverse beziehungsweise die einmal durchgeführte Zerlegung der
Koeffizientenmatrix muss dann nicht für jeden Lastfall neu berechnet werden.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe bearbeitet a) bis d) vollständig an der Tafel, e) wird
ebenfalls gerechnet, f) im Plenum diskutiert. Da dies der letzte Block ist,
eignet sich f) gut als Ausblick auf Anwendungen in der FEM.
```
