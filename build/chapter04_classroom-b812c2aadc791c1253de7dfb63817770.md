# Geführte Übung zu Kapitel 4: Lineare Abbildungen, Kern und Bild

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
Besprechen. Block 3 und Block 4 verwenden dieselbe Matrix, damit die
Studierenden Kern, Bild und die Dimensionsformel als zusammenhängendes
Ergebnis erleben.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, lineare Abbildungen in 2D und 3D (Kap. 4.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Homogenität und Additivität (Kap. 4.2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, Kern einer Matrix (Kap. 4.3) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, Bild, Rang und Dimensionsformel (Kap. 4.4) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Lineare Abbildungen in 2D und 3D

Bezug: Kapitel 4.1, Lineare Abbildungen 2D und 3D

```{admonition} Aufgabe 1: Transformationen in CAD und Bildverarbeitung
:class: tip
**a)** Ein Bauteilprofil soll in einem CAD System gleichmäßig um den Faktor
$s = 1{,}5$ vergrößert werden. Geben Sie die Abbildungsmatrix an und
berechnen Sie das Bild des Punktes $\vec{v} = \begin{pmatrix}4\\
6\end{pmatrix}$. Ein Bereich des Profils hat einen Flächeninhalt von
$10\ \text{cm}^2$. Wie groß ist der Flächeninhalt nach der Streckung?

**b)** Ein rechteckiger Querschnitt wird durch eine Schubbelastung geschert,
beschrieben durch die Matrix $\mathbf{A}_{\text{Scherung}} =
\begin{pmatrix}1 & 0{,}4\\ 0 & 1\end{pmatrix}$. Berechnen Sie das Bild des
Punktes $\vec{v} = \begin{pmatrix}2\\ 5\end{pmatrix}$. Ändert sich der
Flächeninhalt des Querschnitts durch die Scherung?

**c)** Ein Bauteil wird an der $xy$ Ebene gespiegelt. Geben Sie die
zugehörige $3\times 3$ Matrix an und berechnen Sie das Bild des Punktes
$\vec{v} = \begin{pmatrix}3\\ -2\\ 7\end{pmatrix}$. Bleibt das Volumen
erhalten, und ändert sich die Orientierung?

**d)** Eine Messkamera projiziert einen Raumpunkt auf die $xz$ Ebene (die
$y$ Koordinate wird zu Null gesetzt). Geben Sie die zugehörige $3\times 3$
Matrix an, berechnen Sie das Bild von $\vec{v} = \begin{pmatrix}2\\ 5\\
-1\end{pmatrix}$ und bestimmen Sie die Determinante. Was bedeutet dieser
Wert geometrisch?

**Zusatz (für schnelle Gruppen):** Ein Bildverarbeitungssystem bildet einen
Raumpunkt direkt auf seine $x$ und $z$ Koordinate ab, beschrieben durch
$\mathbf{A} = \begin{pmatrix}1 & 0 & 0\\ 0 & 0 & 1\end{pmatrix}$. Berechnen
Sie das Bild von $\vec{v} = \begin{pmatrix}4\\ -3\\ 9\end{pmatrix}$ und
geben Sie Definitionsbereich und Wertebereich dieser Abbildung an.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** $\mathbf{A} = \begin{pmatrix}1{,}5 & 0\\ 0 &
1{,}5\end{pmatrix}$. Bild von $\vec{v}$:
$\begin{pmatrix}1{,}5\cdot 4\\ 1{,}5\cdot 6\end{pmatrix} =
\begin{pmatrix}6\\ 9\end{pmatrix}$. Der Skalierungsfaktor der Fläche ist
$\det(\mathbf{A}) = 1{,}5^2 = 2{,}25$, der neue Flächeninhalt also
$10\cdot 2{,}25 = 22{,}5\ \text{cm}^2$.

**b)** Bild von $\vec{v}$: $\begin{pmatrix}1\cdot 2 + 0{,}4\cdot 5\\ 0\cdot
2 + 1\cdot 5\end{pmatrix} = \begin{pmatrix}4\\ 5\end{pmatrix}$. Es gilt
$\det(\mathbf{A}_{\text{Scherung}}) = 1\cdot 1 - 0\cdot 0{,}4 = 1$, der
Flächeninhalt bleibt also unverändert.

**c)** $\mathbf{A} = \begin{pmatrix}1 & 0 & 0\\ 0 & 1 & 0\\ 0 & 0 &
-1\end{pmatrix}$. Bild von $\vec{v}$: $\begin{pmatrix}3\\ -2\\
-7\end{pmatrix}$. Es gilt $\det(\mathbf{A}) = 1\cdot 1\cdot(-1) = -1$. Der
Betrag ist Eins, also bleibt das Volumen erhalten, das negative Vorzeichen
zeigt eine Umkehrung der Orientierung an.

**d)** $\mathbf{A} = \begin{pmatrix}1 & 0 & 0\\ 0 & 0 & 0\\ 0 & 0 &
1\end{pmatrix}$. Bild von $\vec{v}$: $\begin{pmatrix}2\\ 0\\
-1\end{pmatrix}$. Es gilt $\det(\mathbf{A}) = 0$, da die Abbildung eine
Dimension reduziert, das Volumen jedes Körpers wird auf Null abgebildet.

**Zusatz:** Bild von $\vec{v}$: $\begin{pmatrix}1\cdot 4+0\cdot(-3)+0\cdot
9\\ 0\cdot 4+0\cdot(-3)+1\cdot 9\end{pmatrix} = \begin{pmatrix}4\\
9\end{pmatrix}$. Der Definitionsbereich ist $\mathbb{R}^3$, der
Wertebereich ist $\mathbb{R}^2$, die Abbildung ist also
$F_{\mathbf{A}}:\mathbb{R}^3 \to \mathbb{R}^2$.
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe bearbeitet a) bis d) vollständig, der Zusatz wird nur bei
verbleibender Zeit ergänzt. Coaching Impuls für c): Was sagt der Betrag der
Determinante aus, und was sagt das Vorzeichen aus?
```

---

## Block 2 (0:25 bis 0:45) · Homogenität und Additivität

Bezug: Kapitel 4.2, Definition und Eigenschaften linearer Abbildungen

```{admonition} Aufgabe 2: Linearität nachweisen und widerlegen
:class: tip
Gegeben sei die Matrix $\mathbf{A} = \begin{pmatrix}2 & 1\\ 0 &
3\end{pmatrix}$, die zwei gekoppelte elastische Freiheitsgrade beschreibt.

**a) Homogenität.** Prüfen Sie für $\vec{v} = \begin{pmatrix}3\\
-2\end{pmatrix}$ und $\alpha = 2$, ob $F_{\mathbf{A}}(\alpha\cdot\vec{v}) =
\alpha\cdot F_{\mathbf{A}}(\vec{v})$ gilt, indem Sie beide Seiten
vollständig berechnen.

**b) Additivität.** Prüfen Sie für $\vec{v}_1 = \begin{pmatrix}1\\
2\end{pmatrix}$ und $\vec{v}_2 = \begin{pmatrix}-3\\ 4\end{pmatrix}$, ob
$F_{\mathbf{A}}(\vec{v}_1+\vec{v}_2) = F_{\mathbf{A}}(\vec{v}_1) +
F_{\mathbf{A}}(\vec{v}_2)$ gilt, indem Sie beide Seiten vollständig
berechnen.

**c)** Erklären Sie in ein bis zwei Sätzen, wie sich das Hookesche Gesetz
$F = k\cdot x$ als Homogenität einer linearen Abbildung deuten lässt.

Betrachten Sie nun die Translation $f(\vec{v}) = \vec{v} + \vec{t}$ mit
$\vec{t} = \begin{pmatrix}5\\ 0\end{pmatrix}$.

**d)** Zeigen Sie, dass $f$ nicht linear ist, indem Sie prüfen, ob
$f(\vec{0}) = \vec{0}$ gilt.

**Zusatz (für schnelle Gruppen):** Zeigen Sie zusätzlich, dass $f$ auch die
Additivität verletzt. Berechnen Sie dazu $f(\vec{v}_1+\vec{v}_2)$ und
$f(\vec{v}_1)+f(\vec{v}_2)$ für $\vec{v}_1 = \begin{pmatrix}1\\
1\end{pmatrix}$ und $\vec{v}_2 = \begin{pmatrix}2\\ 3\end{pmatrix}$ und
vergleichen Sie die Ergebnisse.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** $\alpha\cdot\vec{v} = \begin{pmatrix}6\\ -4\end{pmatrix}$.
$$F_{\mathbf{A}}(\alpha\vec{v}) = \begin{pmatrix}2\cdot 6+1\cdot(-4)\\
0\cdot 6+3\cdot(-4)\end{pmatrix} = \begin{pmatrix}8\\ -12\end{pmatrix}$$
$$F_{\mathbf{A}}(\vec{v}) = \begin{pmatrix}2\cdot 3+1\cdot(-2)\\ 0\cdot
3+3\cdot(-2)\end{pmatrix} = \begin{pmatrix}4\\ -6\end{pmatrix}
\Rightarrow \alpha\cdot F_{\mathbf{A}}(\vec{v}) = \begin{pmatrix}8\\
-12\end{pmatrix}$$
Beide Seiten stimmen überein.

**b)** $\vec{v}_1+\vec{v}_2 = \begin{pmatrix}-2\\ 6\end{pmatrix}$.
$$F_{\mathbf{A}}(\vec{v}_1+\vec{v}_2) = \begin{pmatrix}2\cdot(-2)+1\cdot
6\\ 0\cdot(-2)+3\cdot 6\end{pmatrix} = \begin{pmatrix}2\\
18\end{pmatrix}$$
$$F_{\mathbf{A}}(\vec{v}_1) = \begin{pmatrix}4\\ 6\end{pmatrix}, \quad
F_{\mathbf{A}}(\vec{v}_2) = \begin{pmatrix}-2\\ 12\end{pmatrix}
\Rightarrow F_{\mathbf{A}}(\vec{v}_1)+F_{\mathbf{A}}(\vec{v}_2) =
\begin{pmatrix}2\\ 18\end{pmatrix}$$
Beide Seiten stimmen überein.

**c)** Verdoppelt man die Kraft $x$, so verdoppelt sich auch die Auslenkung
$F$, solange $k$ konstant bleibt. Das entspricht genau der Homogenität
$F_{\mathbf{A}}(\alpha\cdot x) = \alpha\cdot F_{\mathbf{A}}(x)$ mit
$\alpha$ als Skalierungsfaktor der Kraft.

**d)** $f(\vec{0}) = \begin{pmatrix}0\\ 0\end{pmatrix} +
\begin{pmatrix}5\\ 0\end{pmatrix} = \begin{pmatrix}5\\ 0\end{pmatrix} \neq
\begin{pmatrix}0\\ 0\end{pmatrix}$. Da eine lineare Abbildung den
Nullvektor immer auf den Nullvektor abbilden muss, ist $f$ nicht linear.

**Zusatz:** $\vec{v}_1+\vec{v}_2 = \begin{pmatrix}3\\ 4\end{pmatrix}$,
also $f(\vec{v}_1+\vec{v}_2) = \begin{pmatrix}8\\ 4\end{pmatrix}$.
$$f(\vec{v}_1) = \begin{pmatrix}6\\ 1\end{pmatrix}, \quad f(\vec{v}_2) =
\begin{pmatrix}7\\ 3\end{pmatrix} \Rightarrow f(\vec{v}_1)+f(\vec{v}_2) =
\begin{pmatrix}13\\ 4\end{pmatrix}$$
Da $\begin{pmatrix}8\\ 4\end{pmatrix} \neq \begin{pmatrix}13\\
4\end{pmatrix}$ ist, verletzt $f$ auch die Additivität.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet a), b) und d) vollständig an der Tafel, c) wird
mündlich ergänzt. Coaching Impuls für d): Welche notwendige Bedingung für
Linearität haben wir in diesem Kapitel kennengelernt?
```

---

## Block 3 (0:50 bis 1:10) · Kern einer Matrix

Bezug: Kapitel 4.3, Kern einer Matrix

```{admonition} Aufgabe 3: Freiheitsgrade eines Mechanismus
:class: tip
**a)** Bestimmen Sie den Kern von $\mathbf{K}_1 = \begin{pmatrix}1 & 0\\ 0 &
2\end{pmatrix}$, indem Sie $\mathbf{K}_1\vec{v} = \vec{0}$ lösen.

Ein ebener Gelenkmechanismus mit drei Koordinaten wird durch die
Kompatibilitätsmatrix

$$\mathbf{K}_2 = \begin{pmatrix}
1 & 2 & 1 \\
2 & 4 & 2 \\
1 & 0 & -1 \\
\end{pmatrix}$$

beschrieben.

**b)** Lösen Sie das homogene Gleichungssystem $\mathbf{K}_2\vec{v} =
\vec{0}$ vollständig und geben Sie $\text{Kern}(\mathbf{K}_2)$ sowie
$\dim(\text{Kern}(\mathbf{K}_2))$ an.

**c)** Welche Bedeutung hat $\dim(\text{Kern}(\mathbf{K}_2)) = 1$ für die
Beweglichkeit des Mechanismus? Nutzen Sie den Zusammenhang zwischen Kern
und kinematischen Freiheitsgraden aus dem Kapitel.

**Zusatz (für schnelle Gruppen):** Bestimmen Sie den Kern von

$$\mathbf{K}_3 = \begin{pmatrix}
1 & 0 & 3 \\
0 & 1 & 0 \\
0 & 0 & 0 \\
2 & 0 & 6 \\
\end{pmatrix}.$$
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** Aus $\mathbf{K}_1\vec{v}=\vec{0}$ folgt $v_1=0$ und $2v_2=0$, also
$v_2=0$. Der Kern enthält nur den Nullvektor, $\dim(\text{Kern}(\mathbf{K}_1))
= 0$.

**b)** Das Gleichungssystem lautet
$$v_1+2v_2+v_3=0, \quad 2v_1+4v_2+2v_3=0, \quad v_1-v_3=0.$$
Die zweite Gleichung ist das Doppelte der ersten und liefert keine neue
Information. Aus der dritten Gleichung folgt $v_1=v_3$. Eingesetzt in die
erste Gleichung: $v_3+2v_2+v_3=0 \Rightarrow v_2=-v_3$. Mit $v_3=t$ ergibt
sich
$$\text{Kern}(\mathbf{K}_2) = \left\{t\cdot\begin{pmatrix}1\\ -1\\
1\end{pmatrix}\;\middle|\; t\in\mathbb{R}\right\}, \quad
\dim(\text{Kern}(\mathbf{K}_2)) = 1.$$

**c)** Ein eindimensionaler Kern bedeutet genau einen kinematischen
Freiheitsgrad. Der Mechanismus kann sich also entlang genau einer
Bewegungsrichtung frei bewegen, ähnlich wie bei einem Scharniergelenk,
ohne dass die Kompatibilitätsbedingungen verletzt werden.

**Zusatz:** Aus $v_2=0$, $v_1+3v_3=0$ (also $v_1=-3v_3$) und den
redundanten Zeilen drei und vier folgt mit $v_3=t$:
$$\text{Kern}(\mathbf{K}_3) = \left\{t\cdot\begin{pmatrix}-3\\ 0\\
1\end{pmatrix}\;\middle|\; t\in\mathbb{R}\right\}, \quad
\dim(\text{Kern}(\mathbf{K}_3)) = 1.$$
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe löst b) vollständig an der Tafel, a) und c) werden mündlich
ergänzt. Die Matrix $\mathbf{K}_2$ wird in Block 4 wiederverwendet, daher
lohnt es sich, das Ergebnis für alle sichtbar stehen zu lassen. Coaching
Impuls für b): Welche der drei Gleichungen liefert wirklich neue
Information?
```

---

## Block 4 (1:10 bis 1:30) · Bild, Rang und Dimensionsformel

Bezug: Kapitel 4.4, Bild, Rang und Dimensionsformel

```{admonition} Aufgabe 4: Lösbarkeit des Mechanismus-Gleichungssystems
:class: tip
Wir verwenden erneut die Matrix aus Block 3:

$$\mathbf{K}_2 = \begin{pmatrix}
1 & 2 & 1 \\
2 & 4 & 2 \\
1 & 0 & -1 \\
\end{pmatrix}, \quad \dim(\text{Kern}(\mathbf{K}_2)) = 1.$$

**a)** Welche Spalte von $\mathbf{K}_2$ ist eine Linearkombination einer
anderen Spalte? Geben Sie $\text{Bild}(\mathbf{K}_2)$ als Spann der
verbleibenden linear unabhängigen Spalten an.

**b)** Bestimmen Sie $\text{Rang}(\mathbf{K}_2)$ durch Auszählen der linear
unabhängigen Spalten.

**c)** Bestätigen Sie Ihr Ergebnis aus b) mit Hilfe der Dimensionsformel
und dem in Block 3 berechneten Kern.

**d)** Prüfen Sie, ob $\vec{b} = \begin{pmatrix}3\\ 6\\ 1\end{pmatrix}$ im
Bild von $\mathbf{K}_2$ liegt, das heißt, ob $\mathbf{K}_2\vec{x}=\vec{b}$
lösbar ist. Geben Sie im Lösbarkeitsfall eine konkrete Lösung $\vec{x}$ an.

**e)** Ist die Lösung aus d) eindeutig? Begründen Sie mit dem Rang oder dem
Kern von $\mathbf{K}_2$.

**Zusatz (für schnelle Gruppen):** Geben Sie einen Vektor $\vec{b}'$ an,
der nicht im Bild von $\mathbf{K}_2$ liegt, und begründen Sie kurz warum.
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** Mit den Spalten $\vec{a}_1=\begin{pmatrix}1\\ 2\\ 1\end{pmatrix}$,
$\vec{a}_2=\begin{pmatrix}2\\ 4\\ 2\end{pmatrix}$,
$\vec{a}_3=\begin{pmatrix}1\\ 2\\ -1\end{pmatrix}$ gilt
$\vec{a}_2 = 2\cdot\vec{a}_1$, die zweite Spalte trägt also keine neue
Richtung bei. Es gilt
$$\text{Bild}(\mathbf{K}_2) = \left\langle
\begin{pmatrix}1\\ 2\\ 1\end{pmatrix}, \begin{pmatrix}1\\ 2\\
-1\end{pmatrix}\right\rangle.$$

**b)** $\vec{a}_1$ und $\vec{a}_3$ sind nicht proportional zueinander
(kein gemeinsamer Faktor erfüllt beide Zeilen gleichzeitig), also
$\text{Rang}(\mathbf{K}_2) = 2$.

**c)** Die Dimensionsformel lautet $\dim(\text{Kern}(\mathbf{K}_2)) +
\text{Rang}(\mathbf{K}_2) = n$ mit $n=3$ Spalten. Mit
$\dim(\text{Kern}(\mathbf{K}_2))=1$ aus Block 3 folgt
$\text{Rang}(\mathbf{K}_2) = 3-1 = 2$, was mit b) übereinstimmt.

**d)** Gesucht sind $c_1, c_3$ mit $c_1\vec{a}_1+c_3\vec{a}_3 = \vec{b}$:
$$c_1+c_3=3, \quad c_1-c_3=1 \Rightarrow c_1=2,\ c_3=1.$$
Die zweite Zeile $2c_1+2c_3=6$ ist automatisch erfüllt. Damit liegt
$\vec{b}$ im Bild, eine Lösung ist $\vec{x} = \begin{pmatrix}2\\ 0\\
1\end{pmatrix}$ (Probe: $\mathbf{K}_2\vec{x} = 2\vec{a}_1+0\cdot\vec{a}_2+
1\cdot\vec{a}_3 = \begin{pmatrix}3\\ 6\\ 1\end{pmatrix} = \vec{b}$
$\checkmark$).

**e)** Nein, die Lösung ist nicht eindeutig, da $\dim(\text{Kern}(\mathbf{K}_2))
= 1 \neq 0$ gilt. Die allgemeine Lösung lautet
$$\vec{x} = \begin{pmatrix}2\\ 0\\ 1\end{pmatrix} + t\cdot\begin{pmatrix}1\\
-1\\ 1\end{pmatrix}, \quad t\in\mathbb{R},$$
es gibt also unendlich viele Lösungen.

**Zusatz:** Zum Beispiel $\vec{b}' = \begin{pmatrix}1\\ 1\\ 0\end{pmatrix}$
liegt nicht im Bild. Mit dem Ansatz $c_1+c_3=1$ und $2c_1+2c_3=1$ ergibt
sich aus der zweiten Gleichung $c_1+c_3=0{,}5$, was der ersten Gleichung
widerspricht. Es gibt also keine Lösung, $\vec{b}'$ liegt außerhalb des
Bildes.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe bearbeitet a), b) und d) vollständig an der Tafel, c) und
e) werden mündlich ergänzt. Da dies der letzte Block des Kapitels ist,
eignet sich der Zusatz gut als Abschlussdiskussion vor dem Ausblick auf
Kapitel 5 zu Eigenwerten und Eigenvektoren.
```
