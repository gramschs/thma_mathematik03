# Geführte Übung zu Kapitel 5: Orthogonale Matrizen, Drehungen und Eigenwerte

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Kapitel 5 hat fünf statt vier
Unterkapitel. Da die Drehmatrix im $\mathbb{R}^2$ (5.3) und im $\mathbb{R}^3$
(5.4) dasselbe Prinzip nur in unterschiedlicher Dimension behandeln, wurden
beide Unterkapitel in Block 3 zusammengefasst, damit das 4 Blöcke Format
erhalten bleibt.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, orthogonale Matrizen (Kap. 5.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Gram-Schmidt-Verfahren (Kap. 5.2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, Drehmatrizen im R2 und R3 (Kap. 5.3 und 5.4) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, Eigenwerte und Eigenvektoren (Kap. 5.5) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Orthogonale Matrizen

Bezug: Kapitel 5.1, Orthogonale Matrizen

```{admonition} Aufgabe 1: Ausrichtungsmatrix eines Kraftsensors
:class: tip
Die Ausrichtung eines Kraftsensors relativ zum Maschinenkoordinatensystem
wird durch die Matrix

$$\mathbf{Q} = \begin{pmatrix}0{,}6 & 0{,}8\\ 0{,}8 & -0{,}6\end{pmatrix}$$

beschrieben.

**a)** Prüfen Sie mit der Definition, ob $\mathbf{Q}$ orthogonal ist, indem
Sie $\mathbf{Q}^{\top}\cdot\mathbf{Q}$ vollständig berechnen.

**b)** Berechnen Sie $\det(\mathbf{Q})$. Handelt es sich eher um eine
Drehung oder eine Spiegelung?

**c)** Geben Sie $\mathbf{Q}^{-1}$ an, ohne eine Inverse im eigentlichen
Sinn zu berechnen. Nutzen Sie dazu eine Eigenschaft orthogonaler Matrizen.

**d)** Prüfen Sie die Längentreue an einem konkreten Vektor: Berechnen Sie
$\mathbf{Q}\cdot\vec{v}$ für $\vec{v} = \begin{pmatrix}3\\ 4\end{pmatrix}$
und vergleichen Sie $\|\mathbf{Q}\vec{v}\|$ mit $\|\vec{v}\|$.

**Zusatz (für schnelle Gruppen):** Prüfen Sie, ob die Drehmatrix
$\mathbf{D}(60°) = \begin{pmatrix}\cos 60° & -\sin 60°\\ \sin 60° & \cos
60°\end{pmatrix}$ orthogonal ist, indem Sie $\mathbf{D}^{\top}\cdot
\mathbf{D}$ mit den exakten Werten $\cos 60° = 0{,}5$ und $\sin 60° =
\frac{\sqrt{3}}{2}$ berechnen.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** Da $\mathbf{Q}$ symmetrisch ist, gilt $\mathbf{Q}^{\top} =
\mathbf{Q}$, also $\mathbf{Q}^{\top}\cdot\mathbf{Q} = \mathbf{Q}\cdot
\mathbf{Q}$:
$$\begin{pmatrix}0{,}6 & 0{,}8\\ 0{,}8 & -0{,}6\end{pmatrix}\cdot
\begin{pmatrix}0{,}6 & 0{,}8\\ 0{,}8 & -0{,}6\end{pmatrix} =
\begin{pmatrix}0{,}36+0{,}64 & 0{,}48-0{,}48\\ 0{,}48-0{,}48 &
0{,}64+0{,}36\end{pmatrix} = \begin{pmatrix}1 & 0\\ 0 & 1\end{pmatrix}$$
$\mathbf{Q}$ ist also orthogonal.

**b)** $\det(\mathbf{Q}) = 0{,}6\cdot(-0{,}6) - 0{,}8\cdot 0{,}8 =
-0{,}36-0{,}64 = -1$. Eine Determinante von $-1$ deutet auf eine
Spiegelung hin.

**c)** Da $\mathbf{Q}$ orthogonal ist, gilt $\mathbf{Q}^{-1} =
\mathbf{Q}^{\top} = \begin{pmatrix}0{,}6 & 0{,}8\\ 0{,}8 &
-0{,}6\end{pmatrix}$ (hier zusätzlich identisch mit $\mathbf{Q}$ selbst,
da $\mathbf{Q}$ symmetrisch ist).

**d)** $\mathbf{Q}\vec{v} = \begin{pmatrix}0{,}6\cdot 3+0{,}8\cdot 4\\
0{,}8\cdot 3-0{,}6\cdot 4\end{pmatrix} = \begin{pmatrix}5\\ 0\end{pmatrix}$.
Es gilt $\|\vec{v}\| = \sqrt{3^2+4^2} = 5$ und $\|\mathbf{Q}\vec{v}\| =
\sqrt{5^2+0^2} = 5$. Die Länge bleibt erhalten.

**Zusatz:** $\mathbf{D}^{\top}(60°)\cdot\mathbf{D}(60°) =
\begin{pmatrix}\cos^2 60°+\sin^2 60° & 0\\ 0 & \sin^2 60°+\cos^2
60°\end{pmatrix} = \begin{pmatrix}1 & 0\\ 0 & 1\end{pmatrix}$, da
$\cos^2\varphi+\sin^2\varphi=1$ für jeden Winkel gilt. Die Drehmatrix ist
also orthogonal.
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe bearbeitet a) bis d) vollständig an der Tafel. Coaching
Impuls für c): Welche Rechenoperation spart Ihnen die Eigenschaft
orthogonaler Matrizen im Vergleich zur allgemeinen Matrixinversion?
```

---

## Block 2 (0:25 bis 0:45) · Gram-Schmidt-Verfahren

Bezug: Kapitel 5.2, Gram-Schmidt-Verfahren

```{admonition} Aufgabe 2: Orthonormalbasis aus Sensorachsen
:class: tip
Ein Kraftmessring liefert nach der Montage zwei leicht schiefe
Achsenvektoren:

$$\vec{v}_1 = \begin{pmatrix}2\\ 1\end{pmatrix}, \quad \vec{v}_2 =
\begin{pmatrix}1\\ 3\end{pmatrix}.$$

**a)** Zeigen Sie, dass $\vec{v}_1$ und $\vec{v}_2$ nicht orthogonal sind.

**b)** Führen Sie den ersten Schritt des Gram-Schmidt-Verfahrens durch:
$\vec{w}_1 = \vec{v}_1$.

**c)** Berechnen Sie den Projektionsskalar $\frac{\vec{v}_2\cdot
\vec{w}_1}{\vec{w}_1\cdot\vec{w}_1}$ und daraus $\vec{w}_2$.

**d)** Prüfen Sie, dass $\vec{w}_1$ und $\vec{w}_2$ orthogonal sind.

**e)** Normieren Sie $\vec{w}_1$ und $\vec{w}_2$ zu einer Orthonormalbasis
$\hat{e}_1$, $\hat{e}_2$.

**Zusatz (für schnelle Gruppen):** Bilden Sie aus $\hat{e}_1$ und
$\hat{e}_2$ die Matrix $\mathbf{Q} = (\hat{e}_1\ \hat{e}_2)$. Welche
Eigenschaft aus Kapitel 5.1 gilt für $\mathbf{Q}$ automatisch, ohne dass Sie
es erneut nachrechnen müssen?
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** $\vec{v}_1\cdot\vec{v}_2 = 2\cdot 1+1\cdot 3 = 5 \neq 0$, die
Vektoren sind also nicht orthogonal.

**b)** $\vec{w}_1 = \begin{pmatrix}2\\ 1\end{pmatrix}$.

**c)** $\dfrac{\vec{v}_2\cdot\vec{w}_1}{\vec{w}_1\cdot\vec{w}_1} =
\dfrac{1\cdot 2+3\cdot 1}{2^2+1^2} = \dfrac{5}{5} = 1$. Damit ist
$$\vec{w}_2 = \vec{v}_2 - 1\cdot\vec{w}_1 = \begin{pmatrix}1\\
3\end{pmatrix}-\begin{pmatrix}2\\ 1\end{pmatrix} = \begin{pmatrix}-1\\
2\end{pmatrix}.$$

**d)** $\vec{w}_1\cdot\vec{w}_2 = 2\cdot(-1)+1\cdot 2 = -2+2 = 0$, die
beiden Vektoren stehen also senkrecht aufeinander.

**e)** Es gilt $\|\vec{w}_1\| = \sqrt{4+1} = \sqrt{5}$ und $\|\vec{w}_2\| =
\sqrt{1+4} = \sqrt{5}$, also
$$\hat{e}_1 = \frac{1}{\sqrt{5}}\begin{pmatrix}2\\ 1\end{pmatrix}, \quad
\hat{e}_2 = \frac{1}{\sqrt{5}}\begin{pmatrix}-1\\ 2\end{pmatrix}.$$

**Zusatz:** $\mathbf{Q}$ ist automatisch orthogonal, da ihre Spalten
paarweise orthonormal sind. Damit gilt $\mathbf{Q}^{-1} =
\mathbf{Q}^{\top}$, ohne dass eine Inverse berechnet werden muss.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet b) bis e) vollständig an der Tafel, a) wird
mündlich ergänzt. Coaching Impuls für c): Was genau sagt der
Projektionsskalar über den Anteil von $\vec{v}_2$ in Richtung $\vec{w}_1$
aus?
```

---

## Block 3 (0:50 bis 1:10) · Drehmatrizen im R2 und R3

Bezug: Kapitel 5.3 und 5.4, Drehmatrizen im R2 und im R3

```{admonition} Aufgabe 3: Fräskopf und Messsonde drehen
:class: tip
Ein Fräskopf mit Länge $r = 8$ cm zeigt zunächst in positive $x$ Richtung,
$\vec{p} = \begin{pmatrix}8\\ 0\end{pmatrix}$ cm.

**a)** Der Fräskopf wird um $\varphi = 60°$ gegen den Uhrzeigersinn
gedreht. Berechnen Sie die neue Position mit der Drehmatrix
$\mathbf{D}(60°)$ (nutzen Sie $\cos 60° = 0{,}5$ und $\sin 60° \approx
0{,}866$).

**b)** Bestätigen Sie, dass $\|\vec{p}\,'\| = \|\vec{p}\|$ gilt.

Eine Messsonde an einem Roboterarm zeigt zunächst in $y$ Richtung,
$\vec{s} = \begin{pmatrix}0\\ 1\\ 0\end{pmatrix}$. Sie wird zunächst um die
$x$ Achse um $\alpha = 30°$ und danach um die $z$ Achse um $\gamma = 60°$
gedreht.

**c)** Berechnen Sie die Endausrichtung Schritt für Schritt, also zuerst
$\mathbf{D}_x(30°)\cdot\vec{s}$ und danach $\mathbf{D}_z(60°)$ angewendet
auf das Zwischenergebnis (nutzen Sie $\cos 30° = \sin 60° \approx 0{,}866$
und $\sin 30° = \cos 60° = 0{,}5$).

**d)** Welche Eigenschaft von $\mathbf{D}_x(\alpha)$ und
$\mathbf{D}_z(\gamma)$ sorgt dafür, dass die Länge der Sonde bei beiden
Teildrehungen erhalten bleibt? Nutzen Sie den Bezug zu Kapitel 5.1.

**Zusatz (für schnelle Gruppen):** Berechnen Sie zum Vergleich die
umgekehrte Reihenfolge $\mathbf{D}_x(30°)\cdot\mathbf{D}_z(60°)\cdot
\vec{s}$ und bestätigen Sie, dass sich ein anderes Ergebnis als in c)
ergibt.
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)**
$$\mathbf{D}(60°)\cdot\vec{p} = \begin{pmatrix}0{,}5 & -0{,}866\\ 0{,}866 &
0{,}5\end{pmatrix}\begin{pmatrix}8\\ 0\end{pmatrix} = \begin{pmatrix}4\\
6{,}93\end{pmatrix}\ \text{cm}$$

**b)** $\|\vec{p}\| = 8$. $\|\vec{p}\,'\| = \sqrt{4^2+6{,}93^2} =
\sqrt{16+48} = \sqrt{64} = 8$. Die Länge ist erhalten.

**c)** Schritt 1, Drehung um die $x$ Achse:
$$\mathbf{D}_x(30°)\cdot\vec{s} = \begin{pmatrix}1 & 0 & 0\\ 0 & 0{,}866 &
-0{,}5\\ 0 & 0{,}5 & 0{,}866\end{pmatrix}\begin{pmatrix}0\\ 1\\
0\end{pmatrix} = \begin{pmatrix}0\\ 0{,}866\\ 0{,}5\end{pmatrix}$$
Schritt 2, Drehung um die $z$ Achse:
$$\mathbf{D}_z(60°)\cdot\begin{pmatrix}0\\ 0{,}866\\ 0{,}5\end{pmatrix} =
\begin{pmatrix}0{,}5 & -0{,}866 & 0\\ 0{,}866 & 0{,}5 & 0\\ 0 & 0 &
1\end{pmatrix}\begin{pmatrix}0\\ 0{,}866\\ 0{,}5\end{pmatrix} =
\begin{pmatrix}-0{,}75\\ 0{,}43\\ 0{,}5\end{pmatrix}$$

**d)** Beide Drehmatrizen sind orthogonal (Kapitel 5.1), und orthogonale
Matrizen sind längentreu: $\|\mathbf{Q}\vec{x}\| = \|\vec{x}\|$ für jeden
Vektor $\vec{x}$. Deshalb ändert sich die Länge der Sonde bei keiner der
beiden Teildrehungen.

**Zusatz:** Schritt 1, Drehung um die $z$ Achse:
$$\mathbf{D}_z(60°)\cdot\vec{s} = \begin{pmatrix}-0{,}866\\ 0{,}5\\
0\end{pmatrix}$$
Schritt 2, Drehung um die $x$ Achse:
$$\mathbf{D}_x(30°)\cdot\begin{pmatrix}-0{,}866\\ 0{,}5\\ 0\end{pmatrix} =
\begin{pmatrix}-0{,}866\\ 0{,}43\\ 0{,}25\end{pmatrix}$$
Das Ergebnis unterscheidet sich von c), insbesondere in der ersten und
dritten Komponente. Die Reihenfolge der Drehungen beeinflusst also das
Ergebnis.
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe rechnet a) und c) vollständig an der Tafel, b) und d)
werden mündlich ergänzt. Coaching Impuls für c): Welche Komponente von
$\vec{s}$ bleibt bei einer Drehung um die $x$ Achse unverändert, und
warum?
```

---

## Block 4 (1:10 bis 1:30) · Eigenwerte und Eigenvektoren

Bezug: Kapitel 5.5, Eigenwerte und Eigenvektoren, Motivation und Definition

```{admonition} Aufgabe 4: Hauptspannungsrichtungen erkennen
:class: tip
Ein vereinfachter ebener Spannungstensor (Einheiten in MPa) lautet

$$\boldsymbol{\sigma} = \begin{pmatrix}7 & 3\\ 3 & -1\end{pmatrix}.$$

**a)** Prüfen Sie, ob $\vec{u} = \begin{pmatrix}1\\ 1\end{pmatrix}$ ein
Eigenvektor von $\boldsymbol{\sigma}$ ist, indem Sie
$\boldsymbol{\sigma}\cdot\vec{u}$ berechnen und mit $\vec{u}$ vergleichen.

**b)** Prüfen Sie, ob $\vec{v} = \begin{pmatrix}3\\ 1\end{pmatrix}$ ein
Eigenvektor ist. Falls ja, geben Sie den zugehörigen Eigenwert an.

**c)** Prüfen Sie, ob $\vec{w} = \begin{pmatrix}1\\ -3\end{pmatrix}$ ein
Eigenvektor ist. Falls ja, geben Sie den zugehörigen Eigenwert an. Was
bedeutet das Vorzeichen dieses Eigenwerts geometrisch?

**d)** Nennen Sie, ohne weitere Rechnung, zwei weitere Eigenvektoren von
$\boldsymbol{\sigma}$ zum selben Eigenwert wie in b).

**e)** Nennen Sie zwei Anwendungen aus dem Maschinenbau, in denen Eigenwerte
und Eigenvektoren eine zentrale Rolle spielen.

**Zusatz (für schnelle Gruppen):** Begründen Sie, warum der Nullvektor bei
keiner Matrix als Eigenvektor zugelassen wird, unabhängig von den
konkreten Werten der Matrix.
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** $\boldsymbol{\sigma}\cdot\vec{u} = \begin{pmatrix}7\cdot 1+3\cdot
1\\ 3\cdot 1+(-1)\cdot 1\end{pmatrix} = \begin{pmatrix}10\\
2\end{pmatrix}$. Da $\begin{pmatrix}10\\ 2\end{pmatrix}$ kein skalares
Vielfaches von $\begin{pmatrix}1\\ 1\end{pmatrix}$ ist (die Verhältnisse
$10/1$ und $2/1$ stimmen nicht überein), ist $\vec{u}$ kein Eigenvektor.

**b)** $\boldsymbol{\sigma}\cdot\vec{v} = \begin{pmatrix}7\cdot 3+3\cdot 1\\
3\cdot 3+(-1)\cdot 1\end{pmatrix} = \begin{pmatrix}24\\ 8\end{pmatrix} =
8\cdot\begin{pmatrix}3\\ 1\end{pmatrix}$. $\vec{v}$ ist also Eigenvektor
zum Eigenwert $\lambda = 8$.

**c)** $\boldsymbol{\sigma}\cdot\vec{w} = \begin{pmatrix}7\cdot 1+3\cdot
(-3)\\ 3\cdot 1+(-1)\cdot(-3)\end{pmatrix} = \begin{pmatrix}-2\\
6\end{pmatrix} = -2\cdot\begin{pmatrix}1\\ -3\end{pmatrix}$. $\vec{w}$ ist
Eigenvektor zum Eigenwert $\lambda = -2$. Das negative Vorzeichen bedeutet,
dass die Richtung von $\vec{w}$ umgekehrt und zusätzlich mit dem Faktor
$2$ skaliert wird.

**d)** Jedes skalare Vielfache von $\vec{v}$ ist ebenfalls Eigenvektor zum
Eigenwert $8$, zum Beispiel $\begin{pmatrix}6\\ 2\end{pmatrix}$ oder
$\begin{pmatrix}-3\\ -1\end{pmatrix}$.

**e)** Zum Beispiel Hauptspannungen in der Festigkeitslehre und
Eigenfrequenzen in der Schwingungsanalyse.

**Zusatz:** Für jede Matrix $\mathbf{A}$ und jeden Skalar $\lambda$ gilt
$\mathbf{A}\cdot\vec{0} = \vec{0} = \lambda\cdot\vec{0}$. Die Gleichung
wäre also für beliebiges $\lambda$ erfüllt und würde keine sinnvolle
Aussage über eine ausgezeichnete Richtung liefern. Deshalb wird der
Nullvektor per Definition als Eigenvektor ausgeschlossen.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe prüft a), b) und c) vollständig an der Tafel, d) und e)
werden mündlich ergänzt. Da dies der letzte Block des Kapitels ist, eignet
sich e) gut als Ausblick auf das charakteristische Polynom in Kapitel 6.
```
