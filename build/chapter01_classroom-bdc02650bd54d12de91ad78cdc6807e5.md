# Geführte Übung zu Kapitel 1: Matrizen

Format: 4 Blöcke à 20 Minuten + 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede*r einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
- Jeder Block: kurze Aufgabenstellung (Beamer) → ca. 13 Min. Arbeitszeit
  (inkl. Coaching der Tafelgruppe) → ca. 6 Min. gemeinsame Besprechung.
- **Coaching-Prinzip:** Fragen statt Ansagen. Die Kreide bleibt bei den
  Studierenden. Beispiele: „Was fällt dir an dieser Position auf?“, „Was habt
  ihr in der letzten Aufgabe an dieser Stelle gemacht – hilft das hier auch?“,
  „Was müsste gelten, damit das definiert ist?“
- Erste ca. 10 Minuten der Arbeitsphase möglichst selbständig ringen lassen
  (kurzer Rundgang durch den Raum), erst in den letzten Minuten gezielt bei
  der Tafelgruppe einsteigen.
- Musterlösungen sind als Dropdown eingeklappt – erst nach der Arbeitsphase
  öffnen.
- Zeitangaben sind Richtwerte; wichtiger als exaktes Timing ist der Rhythmus
  aus Rechnen – Tafel – Besprechen.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00–0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05–0:25 | Block 1 | Aufgabe 1 – Matrix-Grundbegriffe (Kap. 1.1) |
| 0:25–0:45 | Block 2 | Aufgabe 2 – Besondere Matrizen (Kap. 1.2) |
| 0:45–0:50 | Pause | kurze Verschnaufpause |
| 0:50–1:10 | Block 3 | Aufgabe 3 – Addition & Skalarmultiplikation (Kap. 1.3) |
| 1:10–1:30 | Block 4 | Aufgabe 4 – Matrizenmultiplikation (Kap. 1.4) |

## Tafelgruppen-Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05–0:25) · Matrix-Grundbegriffe

*Bezug: Kapitel 1.1 – Was ist eine Matrix?*

```{admonition} Aufgabe 1: Wärmestrommatrix
:class: tip
An einem Getriebegehäuse werden vier benachbarte Bauteile ($B_1$ bis $B_4$)
betrachtet. Der Wärmestrom (in Watt) von einem Bauteil zum jeweils
benachbarten Bauteil wird in der Matrix $\mathbf{W}$ erfasst. Der Eintrag
$w_{ij}$ gibt den Wärmestrom von Bauteil $i$ zu Bauteil $j$ an.

$$\mathbf{W} = \begin{pmatrix}
0 & 12 & 5 & 0 \\
3 & 0 & 0 & 8 \\
5 & 0 & 0 & 2 \\
0 & 6 & 3 & 0 \\
\end{pmatrix}$$

**a)** Welche Dimension hat $\mathbf{W}$?

**b)** Wie groß ist der Wärmestrom von Bauteil 3 zu Bauteil 1? Geben Sie den
zugehörigen Matrixeintrag mit korrektem Index an.

**c)** Geben Sie den Zeilenvektor für Bauteil 2 an und beschreiben Sie in
einem Satz, was er aussagt.

**d)** Geben Sie den Spaltenvektor für Bauteil 4 an und beschreiben Sie, was
er aussagt.

**e)** Bestimmen Sie die Hauptdiagonale von $\mathbf{W}$. Warum ist es
inhaltlich sinnvoll, dass hier nur Nullen stehen?

**f)** Ist $\mathbf{W}$ quadratisch? Begründen Sie mit der Definition.

**Zusatz (für schnelle Gruppen):** Ein Prüfstand misst an 3 Messpunkten über
5 Zeitpunkte Dehnungswerte, notiert als Matrix $\mathbf{M} \in
\mathbb{R}^{3\times 5}$. Ist $\mathbf{M}$ quadratisch? Begründen Sie.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** $\mathbf{W}$ hat 4 Zeilen und 4 Spalten, also die Dimension
$4\times 4$.

**b)** Wärmestrom von Bauteil 3 zu Bauteil 1 steht in Zeile 3, Spalte 1:
$w_{31} = 5$ Watt.

**c)** Zeilenvektor Bauteil 2: $\vec{z}_2 = \begin{pmatrix}3 & 0 & 0 &
8\end{pmatrix}$. Bauteil 2 gibt 3 W an Bauteil 1, 0 W an sich selbst, 0 W an
Bauteil 3 und 8 W an Bauteil 4 ab.

**d)** Spaltenvektor Bauteil 4: $\vec{s}_4 = \begin{pmatrix}0\\ 8\\ 2\\
0\end{pmatrix}$. Er zeigt, wie viel Wärme Bauteil 4 von jedem anderen Bauteil
empfängt (0 W von B1, 8 W von B2, 2 W von B3, 0 W von sich selbst).

**e)** Hauptdiagonale: $w_{11}=w_{22}=w_{33}=w_{44}=0$. Ein Bauteil überträgt
keine Wärme „an sich selbst“, daher sind diese Einträge per Definition Null.

**f)** Ja, $\mathbf{W}$ ist quadratisch, da die Anzahl der Zeilen ($m=4$)
gleich der Anzahl der Spalten ($n=4$) ist.

**Zusatz:** Nein, $\mathbf{M}$ ist nicht quadratisch, da $m=3 \neq 5=n$.
```

```{admonition} Tafel-Hinweis Block 1
:class: note
Die Tafelgruppe bearbeitet und präsentiert a)–f) vollständig (Teile ggf. auf
mehrere Personen verteilen). Coaching-Impuls, falls die Gruppe bei e) stockt:
„Was würde es bedeuten, wenn $w_{11}$ ungleich Null wäre?“
```

---

## Block 2 (0:25–0:45) · Besondere Matrizen

*Bezug: Kapitel 1.2 – Besondere Matrizen*

```{admonition} Aufgabe 2: Matrizen erkennen und konstruieren
:class: tip
**a) Zuordnen.** Ordnen Sie jede der folgenden Matrizen den passenden
Begriffen zu: *Nullmatrix, Diagonalmatrix, Einheitsmatrix, obere
Dreiecksmatrix, untere Dreiecksmatrix, strikte (echte) Dreiecksmatrix, keins
davon.* Mehrfachnennungen sind möglich.

$$\mathbf{M}_1 = \begin{pmatrix}3 & 0 & 0\\ 0 & 0 & 0\\ 0 & 0 &
-2\end{pmatrix} \quad
\mathbf{M}_2 = \begin{pmatrix}1 & 0 & 0\\ 0 & 1 & 0\\ 0 & 0 &
1\end{pmatrix} \quad
\mathbf{M}_3 = \begin{pmatrix}0 & 0\\ 0 & 0\end{pmatrix}$$

$$\mathbf{M}_4 = \begin{pmatrix}2 & 0 & 0\\ -1 & 3 & 0\\ 4 & 5 &
6\end{pmatrix} \quad
\mathbf{M}_5 = \begin{pmatrix}1 & 2 & 0\\ 0 & 3 & -1\\ 0 & 0 &
4\end{pmatrix} \quad
\mathbf{M}_6 = \begin{pmatrix}1 & 2\\ 3 & 4\end{pmatrix}$$

**b) Trägheitsmatrix.** Ein rotationssymmetrisches Bauteil hat bezüglich
seiner Hauptachsen die Trägheitsmomente $I_x = 0{,}8\ \text{kg}\,\text{m}^2$,
$I_y = 0{,}8\ \text{kg}\,\text{m}^2$, $I_z = 1{,}4\ \text{kg}\,\text{m}^2$;
alle Deviationsmomente (Kopplungsterme) sind Null. Geben Sie die
Trägheitsmatrix zunächst in $\text{diag}(\ldots)$-Schreibweise und dann als
vollständige Matrix an.

**c) LR-Zerlegung.** Bei der LR-Zerlegung eines Gleichungssystems entsteht
die Matrix

$$\mathbf{L} = \begin{pmatrix}1 & 0 & 0\\ 2 & 1 & 0\\ -1 & 3 &
1\end{pmatrix}.$$

Um welchen Matrixtyp handelt es sich? Ist $\mathbf{L}$ eine *strikte* untere
Dreiecksmatrix? Begründen Sie.

**d) Verständnisfrage.** Erklären Sie, warum die Einheitsmatrix gleichzeitig
eine Diagonalmatrix, eine obere Dreiecksmatrix *und* eine untere
Dreiecksmatrix ist.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)**
- $\mathbf{M}_1$: Diagonalmatrix (quadratisch, alle Einträge außerhalb der
  Hauptdiagonale Null; ein Diagonaleintrag darf ebenfalls Null sein).
- $\mathbf{M}_2$: Einheitsmatrix (und damit auch Diagonalmatrix, obere und
  untere Dreiecksmatrix).
- $\mathbf{M}_3$: Nullmatrix (und damit auch Diagonalmatrix sowie strikte
  obere/untere Dreiecksmatrix).
- $\mathbf{M}_4$: untere Dreiecksmatrix (nicht strikt, da Hauptdiagonale
  $\neq 0$; keine Diagonalmatrix, da Einträge unterhalb der Hauptdiagonale
  $\neq 0$).
- $\mathbf{M}_5$: obere Dreiecksmatrix (nicht strikt, aus demselben Grund wie
  oben).
- $\mathbf{M}_6$: keins der genannten Typen (quadratisch, aber weder
  Dreiecks- noch Diagonalmatrix).

**b)** $\text{diag}(0{,}8,\ 0{,}8,\ 1{,}4) = \begin{pmatrix}0{,}8 & 0 & 0\\ 0
& 0{,}8 & 0\\ 0 & 0 & 1{,}4\end{pmatrix}$

**c)** $\mathbf{L}$ ist eine untere Dreiecksmatrix (alle Einträge oberhalb
der Hauptdiagonale sind Null). Sie ist *keine* strikte untere
Dreiecksmatrix, da die Hauptdiagonale nicht aus Nullen besteht
($l_{11}=l_{22}=l_{33}=1$).

**d)** Die Einheitsmatrix hat auf der Hauptdiagonale nur Einsen und
außerhalb nur Nullen. Da alle Einträge außerhalb der Hauptdiagonale Null
sind, erfüllt sie die Bedingung für eine Diagonalmatrix. Da insbesondere
alle Einträge unterhalb der Hauptdiagonale Null sind, ist sie zugleich eine
obere Dreiecksmatrix; da alle Einträge oberhalb der Hauptdiagonale Null
sind, ist sie zugleich eine untere Dreiecksmatrix. Die Kategorien schließen
sich also nicht gegenseitig aus, sondern die Einheitsmatrix ist ein
Spezialfall mehrerer Typen gleichzeitig.
```

```{admonition} Tafel-Hinweis Block 2
:class: note
Die Tafelgruppe stellt a) als Zuordnungstabelle dar (Matrixname → Begriff(e))
und ergänzt b)–d). Coaching-Impuls für c): „Was genau unterscheidet
‚Dreiecksmatrix' von ‚strikte Dreiecksmatrix' laut Definition?“
```

---

## Block 3 (0:50–1:10) · Addition & Skalarmultiplikation

*Bezug: Kapitel 1.3 – Addition und Skalarmultiplikation*

```{admonition} Aufgabe 3: Lastüberlagerung
:class: tip
Ein Bauteil wird an drei Messpunkten in $x$- und $y$-Richtung belastet
(Kräfte in kN). Für den Lastfall *Eigengewicht* gilt

$$\mathbf{F}_G = \begin{pmatrix}-5 & 0\\ -8 & 0\\ -6 & 0\end{pmatrix},$$

für den Lastfall *Wind*

$$\mathbf{F}_W = \begin{pmatrix}2 & 6\\ 1 & 9\\ 0 & 4\end{pmatrix}.$$

**a)** Berechnen Sie die Gesamtlast $\mathbf{F}_G + \mathbf{F}_W$ und
interpretieren Sie einen beliebigen Eintrag Ihrer Wahl.

**b)** Für die Windlast ist nach Norm ein Sicherheitsbeiwert von $1{,}5$ zu
berücksichtigen. Berechnen Sie $1{,}5 \cdot \mathbf{F}_W$.

**c)** Berechnen Sie die bemessungsrelevante Gesamtlast $\mathbf{F}_G +
1{,}5 \cdot \mathbf{F}_W$.

**d)** Berechnen Sie $\mathbf{F}_W - \mathbf{F}_G$ und beschreiben Sie in
einem Satz, was diese Differenz inhaltlich bedeutet.

**e)** Zeigen Sie anhand *eines* Eintrags Ihrer Wahl, dass
$1{,}5\cdot(\mathbf{F}_G + \mathbf{F}_W) = 1{,}5\cdot \mathbf{F}_G +
1{,}5\cdot \mathbf{F}_W$ gilt. Welches Rechengesetz wird hier bestätigt?
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)**
$$\mathbf{F}_G + \mathbf{F}_W = \begin{pmatrix}-3 & 6\\ -7 & 9\\ -6 &
4\end{pmatrix}$$
Zum Beispiel: An Messpunkt 2 wirkt in $x$-Richtung eine Gesamtkraft von
$-7$ kN.

**b)**
$$1{,}5\cdot \mathbf{F}_W = \begin{pmatrix}3 & 9\\ 1{,}5 & 13{,}5\\ 0 &
6\end{pmatrix}$$

**c)**
$$\mathbf{F}_G + 1{,}5\cdot \mathbf{F}_W = \begin{pmatrix}-2 & 9\\ -6{,}5 &
13{,}5\\ -6 & 6\end{pmatrix}$$

**d)**
$$\mathbf{F}_W - \mathbf{F}_G = \begin{pmatrix}7 & 6\\ 9 & 9\\ 6 &
4\end{pmatrix}$$
Die Differenz zeigt, um wie viel die Windlast an jedem Messpunkt und in
jeder Richtung von der Eigengewichtslast abweicht.

**e)** Beispiel Zeile 1, Spalte 2: Linke Seite: $(\mathbf{F}_G+\mathbf{F}_W)$
an dieser Position ist $0+6=6$, also $1{,}5\cdot 6 = 9$. Rechte Seite:
$1{,}5\cdot 0 + 1{,}5\cdot 6 = 0+9=9$. Beide Seiten stimmen überein ✓.
Bestätigt wird das **Distributivgesetz** $s\cdot(\mathbf{A}+\mathbf{B}) =
s\cdot\mathbf{A}+s\cdot\mathbf{B}$.
```

```{admonition} Tafel-Hinweis Block 3
:class: note
Die Tafelgruppe rechnet a)–c) vollständig an der Tafel (Zwischenschritte
elementweise zeigen), d) und e) werden mündlich ergänzt. Coaching-Impuls:
„Welche Voraussetzung müssen zwei Matrizen erfüllen, damit ihr diese
Rechnung überhaupt durchführen dürft?“
```

---

## Block 4 (1:10–1:30) · Matrizenmultiplikation

*Bezug: Kapitel 1.4 – Matrizenmultiplikation*

```{admonition} Aufgabe 4: Produktionskosten
:class: tip
Ein Zulieferer fertigt an drei Standorten ($S_1, S_2, S_3$) drei
Bauteiltypen ($T_1, T_2, T_3$). Die wöchentliche Produktionsmenge (Stück) ist
in $\mathbf{P}$ erfasst:

$$\mathbf{P} = \begin{pmatrix}100 & 50 & 0\\ 0 & 80 & 40\\ 60 & 0 &
90\end{pmatrix}$$

(Zeilen: $S_1,S_2,S_3$; Spalten: $T_1,T_2,T_3$). Jeder Bauteiltyp verursacht
pro Stück Materialkosten (€) und eine Fertigungszeit (min), erfasst in
$\mathbf{K}$:

$$\mathbf{K} = \begin{pmatrix}8 & 5\\ 12 & 9\\ 6 & 3\end{pmatrix}$$

(Zeilen: $T_1,T_2,T_3$; Spalten: Kosten, Zeit).

**a)** Prüfen Sie, ob $\mathbf{P}\cdot\mathbf{K}$ definiert ist, und geben
Sie die Dimension des Ergebnisses an.

**b)** Berechnen Sie mit Hilfe des Skalarprodukts die Gesamtkosten und die
Gesamtfertigungszeit für Standort $S_1$ (erste Zeile des Produkts).

**c)** Berechnen Sie die vollständige Matrix $\mathbf{P}\cdot\mathbf{K}$
(nutzen Sie z. B. das Falk-Schema).

**d)** Ist auch $\mathbf{K}\cdot\mathbf{P}$ definiert? Begründen Sie anhand
der Dimensionen.

**e) Diskussion:** Angenommen, es soll zusätzlich ein pauschaler
Materialzuschlag von 10 % auf alle Kosten berücksichtigt werden. Überlegen
Sie gemeinsam: Welches Rechengesetz hilft Ihnen, den Zuschlag geschickt
einzurechnen, ohne die ganze Rechnung neu zu machen?
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** $\mathbf{P}$ hat die Dimension $3\times 3$, $\mathbf{K}$ die
Dimension $3\times 2$. Die Spaltenanzahl von $\mathbf{P}$ (= 3) stimmt mit
der Zeilenanzahl von $\mathbf{K}$ (= 3) überein, das Produkt ist also
definiert und hat die Dimension $3\times 2$.

**b)** Zeile 1 von $\mathbf{P}$: $(100,\ 50,\ 0)$.
- Kosten: $100\cdot 8 + 50\cdot 12 + 0\cdot 6 = 800+600+0 = 1400$ €
- Zeit: $100\cdot 5 + 50\cdot 9 + 0\cdot 3 = 500+450+0 = 950$ min

**c)** Analog für $S_2$ (Zeile $(0,80,40)$) und $S_3$ (Zeile $(60,0,90)$):
- $S_2$: Kosten $= 0\cdot8+80\cdot12+40\cdot6=960+240=1200$ €,
  Zeit $=0\cdot5+80\cdot9+40\cdot3=720+120=840$ min
- $S_3$: Kosten $=60\cdot8+0\cdot12+90\cdot6=480+540=1020$ €,
  Zeit $=60\cdot5+0\cdot9+90\cdot3=300+270=570$ min

$$\mathbf{P}\cdot\mathbf{K} = \begin{pmatrix}1400 & 950\\ 1200 & 840\\ 1020 &
570\end{pmatrix}$$

**d)** Nein. $\mathbf{K}$ hat 2 Spalten, $\mathbf{P}$ hat 3 Zeilen. Da
$2 \neq 3$, ist $\mathbf{K}\cdot\mathbf{P}$ nicht definiert.

**e)** Der Zuschlag ist eine Skalarmultiplikation mit $1{,}1$. Dank der
Rechengesetze lässt sich der Faktor $1{,}1$ direkt auf die Kostenspalte von
$\mathbf{K}$ anwenden, *bevor* mit $\mathbf{P}$ multipliziert wird - es muss
also nicht jede Zeile des Endergebnisses einzeln neu berechnet werden.
(Offene Diskussion - wichtig ist das Erkennen, dass Rechengesetze
Mehrfachrechnungen ersparen.)
```

```{admonition} Tafel-Hinweis Block 4
:class: note
Die Tafelgruppe berechnet a)-c) vollständig an der Tafel, idealerweise mit
Falk-Schema. d) und e) werden im Plenum diskutiert. Da dies der letzte Block
ist, eignet sich e) gut als Brücke zu Kapitel 2 (lineare Gleichungssysteme).
```
