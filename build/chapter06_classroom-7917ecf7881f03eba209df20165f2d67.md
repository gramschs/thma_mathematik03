# Geführte Übung zu Kapitel 6: Eigenwerte, Eigenvektoren und Diagonalisierung

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Kapitel 6 hat fünf statt vier
Unterkapitel. Da die Berechnung der Eigenwerte (6.2) und die anschließende
Berechnung der zugehörigen Eigenvektoren (6.3) ohnehin ein zusammenhängendes
Rechenverfahren bilden, wurden beide Unterkapitel in Block 2 zusammengefasst,
damit das 4 Blöcke Format erhalten bleibt. Block 2, 3 und 4 verwenden
dieselbe Matrix als Trägheitstensor, damit Eigenwertberechnung,
Diagonalisierung und Anwendung als ein zusammenhängendes Beispiel erlebt
werden.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, Koordinatendarstellung bezüglich einer Basis (Kap. 6.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Eigenwerte und Eigenvektoren berechnen (Kap. 6.2 und 6.3) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, symmetrische Matrizen und Diagonalisierung (Kap. 6.4) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, Anwendungen der Diagonalisierung (Kap. 6.5) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Koordinatendarstellung bezüglich einer Basis

Bezug: Kapitel 6.1, Koordinatendarstellung bezüglich einer Basis

```{admonition} Aufgabe 1: Koordinaten in einem schiefen Sensorsystem
:class: tip
Ein Messsystem verwendet die beiden Richtungsvektoren

$$\vec{v}_1 = \begin{pmatrix}2\\ 1\end{pmatrix}, \quad \vec{v}_2 =
\begin{pmatrix}1\\ 3\end{pmatrix}$$

als Basis $V = (\vec{v}_1\mid\vec{v}_2)$.

**a)** Berechnen Sie $\det(V)$ und bestätigen Sie damit, dass $\vec{v}_1$
und $\vec{v}_2$ tatsächlich eine Basis des $\mathbb{R}^2$ bilden.

**b)** Bestimmen Sie den Koordinatenvektor $[\vec{a}]_V$ des Vektors
$\vec{a} = \begin{pmatrix}8\\ 9\end{pmatrix}$ bezüglich $V$, indem Sie das
Gleichungssystem $\lambda_1\vec{v}_1+\lambda_2\vec{v}_2=\vec{a}$ lösen.

**c)** Nennen Sie eine Anwendung aus dem Maschinenbau, bei der ein Wechsel
von der Standardbasis zu einer anderen Basis sinnvoll ist.

**Zusatz (für schnelle Gruppen):** Gegeben sei die Basis $W =
(\vec{w}_1\mid\vec{w}_2\mid\vec{w}_3)$ mit $\vec{w}_1 = \begin{pmatrix}1\\
0\\ 1\end{pmatrix}$, $\vec{w}_2 = \begin{pmatrix}0\\ 1\\ 1\end{pmatrix}$,
$\vec{w}_3 = \begin{pmatrix}1\\ 1\\ 0\end{pmatrix}$. Bestimmen Sie den
Koordinatenvektor $[\vec{b}]_W$ für $\vec{b} = \begin{pmatrix}4\\ 3\\
5\end{pmatrix}$.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** $\det(V) = 2\cdot 3-1\cdot 1 = 5 \neq 0$, also bilden $\vec{v}_1$
und $\vec{v}_2$ eine Basis.

**b)** Aus $2\lambda_1+\lambda_2=8$ und $\lambda_1+3\lambda_2=9$ folgt mit
Einsetzen $\lambda_2=8-2\lambda_1$ in die zweite Gleichung:
$\lambda_1+3(8-2\lambda_1)=9 \Rightarrow -5\lambda_1=-15 \Rightarrow
\lambda_1=3$, also $\lambda_2=2$. Damit ist
$$[\vec{a}]_V = \begin{pmatrix}3\\ 2\end{pmatrix}.$$
Probe: $3\cdot\begin{pmatrix}2\\ 1\end{pmatrix}+2\cdot\begin{pmatrix}1\\
3\end{pmatrix} = \begin{pmatrix}8\\ 9\end{pmatrix}$ $\checkmark$

**c)** Zum Beispiel die Roboterkinematik (körperfestes statt weltfestes
Koordinatensystem), die Hauptachsentransformation in der Festigkeitslehre
oder die Modalanalyse in der Schwingungstechnik.

**Zusatz:** Aus $\lambda_1+\lambda_3=4$, $\lambda_2+\lambda_3=3$ und
$\lambda_1+\lambda_2=5$ folgt mit $\lambda_1=4-\lambda_3$,
$\lambda_2=3-\lambda_3$ eingesetzt in die dritte Gleichung:
$(4-\lambda_3)+(3-\lambda_3)=5 \Rightarrow \lambda_3=1$, also
$\lambda_1=3$, $\lambda_2=2$. Damit ist
$$[\vec{b}]_W = \begin{pmatrix}3\\ 2\\ 1\end{pmatrix}.$$
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe bearbeitet a) und b) vollständig an der Tafel, c) wird
mündlich ergänzt. Coaching Impuls für b): Welche Gleichung liefert Ihnen am
einfachsten eine der beiden Unbekannten?
```

---

## Block 2 (0:25 bis 0:45) · Eigenwerte und Eigenvektoren berechnen

Bezug: Kapitel 6.2 und 6.3, Berechnung der Eigenwerte und der Eigenvektoren

```{admonition} Aufgabe 2: Trägheitstensor eines unsymmetrischen Profils
:class: tip
Der Trägheitstensor eines Balkenquerschnitts (Einheiten $10^4\ \text{mm}^4$)
lautet bezüglich des ursprünglichen Koordinatensystems

$$\mathbf{I} = \begin{pmatrix}8 & -2\\ -2 & 5\end{pmatrix}.$$

**a)** Stellen Sie das charakteristische Polynom $p(\lambda) =
\det(\mathbf{I}-\lambda\mathbf{E})$ auf und vereinfachen Sie es zu einer
quadratischen Gleichung in $\lambda$.

**b)** Bestimmen Sie die Nullstellen von $p(\lambda)$, also die Eigenwerte
$\lambda_1$ und $\lambda_2$.

**c)** Bestimmen Sie für $\lambda_1$ den zugehörigen Eigenvektor durch
Lösen von $(\mathbf{I}-\lambda_1\mathbf{E})\vec{v}=\vec{0}$.

**d)** Bestimmen Sie für $\lambda_2$ den zugehörigen Eigenvektor durch
Lösen von $(\mathbf{I}-\lambda_2\mathbf{E})\vec{v}=\vec{0}$.

**e)** Prüfen Sie, dass die beiden Eigenvektoren orthogonal sind. Warum ist
das kein Zufall?

**Zusatz (für schnelle Gruppen):** Lesen Sie die Eigenwerte der
Dreiecksmatrix $\mathbf{T} = \begin{pmatrix}6 & 3 & -1\\ 0 & 2 & 4\\ 0 & 0 &
-3\end{pmatrix}$ direkt ab, ohne das charakteristische Polynom zu
berechnen.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** $p(\lambda) = (8-\lambda)(5-\lambda) - (-2)(-2) = \lambda^2 -
13\lambda + 40 - 4 = \lambda^2 - 13\lambda + 36$.

**b)** Mit der pq-Formel: $\lambda_{1/2} = \dfrac{13}{2} \pm
\sqrt{\dfrac{169}{4}-36} = \dfrac{13}{2}\pm\dfrac{5}{2}$, also $\lambda_1 =
9$ und $\lambda_2 = 4$.

**c)** $\mathbf{I}-9\mathbf{E} = \begin{pmatrix}-1 & -2\\ -2 &
-4\end{pmatrix}$. Aus $-v_1-2v_2=0$ folgt $v_1=-2v_2$, also
$$\vec{v}_1 = \begin{pmatrix}-2\\ 1\end{pmatrix}.$$
Probe: $\mathbf{I}\vec{v}_1 = \begin{pmatrix}-16-2\\ 4+5\end{pmatrix} =
\begin{pmatrix}-18\\ 9\end{pmatrix} = 9\cdot\begin{pmatrix}-2\\
1\end{pmatrix}$ $\checkmark$

**d)** $\mathbf{I}-4\mathbf{E} = \begin{pmatrix}4 & -2\\ -2 &
1\end{pmatrix}$. Aus $4v_1-2v_2=0$ folgt $v_2=2v_1$, also
$$\vec{v}_2 = \begin{pmatrix}1\\ 2\end{pmatrix}.$$
Probe: $\mathbf{I}\vec{v}_2 = \begin{pmatrix}8-4\\ -2+10\end{pmatrix} =
\begin{pmatrix}4\\ 8\end{pmatrix} = 4\cdot\begin{pmatrix}1\\ 2\end{pmatrix}$
$\checkmark$

**e)** $\vec{v}_1\cdot\vec{v}_2 = -2\cdot 1+1\cdot 2 = 0$. Das ist kein
Zufall, da $\mathbf{I}$ symmetrisch ist und Eigenvektoren symmetrischer
Matrizen zu verschiedenen Eigenwerten stets orthogonal sind.

**Zusatz:** Die Eigenwerte einer Dreiecksmatrix stehen direkt auf der
Hauptdiagonale: $\lambda_1=6$, $\lambda_2=2$, $\lambda_3=-3$.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet a) bis d) vollständig an der Tafel, e) wird
mündlich ergänzt. Das Ergebnis wird für Block 3 und 4 wiederverwendet,
daher lohnt es sich, es sichtbar stehen zu lassen. Coaching Impuls für c)
und d): Warum liefert eine der beiden Zeilen keine neue Information?
```

---

## Block 3 (0:50 bis 1:10) · Symmetrische Matrizen und Diagonalisierung

Bezug: Kapitel 6.4, Symmetrische Matrizen und Diagonalisierung

```{admonition} Aufgabe 3: Diagonalisierung des Trägheitstensors
:class: tip
Wir verwenden erneut die Matrix aus Block 2:

$$\mathbf{I} = \begin{pmatrix}8 & -2\\ -2 & 5\end{pmatrix}, \quad
\lambda_1=9\ (\vec{v}_1=\begin{pmatrix}-2\\ 1\end{pmatrix}), \quad
\lambda_2=4\ (\vec{v}_2=\begin{pmatrix}1\\ 2\end{pmatrix}).$$

**a)** Schreiben Sie die Eigenvektoren als Spalten der Matrix $\mathbf{V}$.

**b)** Bestätigen Sie die Diagonalisierung über die Probe
$\mathbf{I}\mathbf{V} = \mathbf{V}\mathbf{D}$ mit $\mathbf{D} =
\begin{pmatrix}9 & 0\\ 0 & 4\end{pmatrix}$, indem Sie beide Seiten
vollständig berechnen.

**c)** Normieren Sie die Eigenvektoren und geben Sie die orthogonale Matrix
$\mathbf{Q}$ an, sodass $\mathbf{D} = \mathbf{Q}^{\top}\mathbf{I}\mathbf{Q}$
gilt.

**d)** Gegeben sei $\mathbf{B} = \begin{pmatrix}4 & 1\\ 0 &
4\end{pmatrix}$. Zeigen Sie, dass der Eigenwert $\lambda=4$ die
algebraische Vielfachheit $2$, aber nur die geometrische Vielfachheit $1$
besitzt. Ist $\mathbf{B}$ diagonalisierbar?

**e)** Warum garantiert der Spektralsatz, dass eine Situation wie bei
$\mathbf{B}$ für den symmetrischen Trägheitstensor $\mathbf{I}$ niemals
auftreten kann?
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** $\mathbf{V} = \begin{pmatrix}-2 & 1\\ 1 & 2\end{pmatrix}$

**b)** $$\mathbf{I}\mathbf{V} = \begin{pmatrix}8 & -2\\ -2 &
5\end{pmatrix}\begin{pmatrix}-2 & 1\\ 1 & 2\end{pmatrix} =
\begin{pmatrix}-18 & 4\\ 9 & 8\end{pmatrix}$$
$$\mathbf{V}\mathbf{D} = \begin{pmatrix}-2 & 1\\ 1 &
2\end{pmatrix}\begin{pmatrix}9 & 0\\ 0 & 4\end{pmatrix} =
\begin{pmatrix}-18 & 4\\ 9 & 8\end{pmatrix}$$
Beide Seiten stimmen überein.

**c)** $\|\vec{v}_1\| = \sqrt{4+1} = \sqrt{5}$, $\|\vec{v}_2\| =
\sqrt{1+4} = \sqrt{5}$, also
$$\mathbf{Q} = \frac{1}{\sqrt{5}}\begin{pmatrix}-2 & 1\\ 1 &
2\end{pmatrix}.$$

**d)** Das charakteristische Polynom ist $(4-\lambda)^2=0$, also $\lambda=4$
mit algebraischer Vielfachheit $m_4=2$. Die Eigenvektorgleichung
$(\mathbf{B}-4\mathbf{E})\vec{v}=\vec{0}$ lautet
$\begin{pmatrix}0 & 1\\ 0 & 0\end{pmatrix}\vec{v}=\vec{0}$, also $v_2=0$
und $v_1$ frei. Der Eigenraum ist nur eindimensional,
$d_4=1<m_4=2$. $\mathbf{B}$ ist also nicht diagonalisierbar.

**e)** Der Spektralsatz garantiert, dass für jede symmetrische Matrix und
jeden Eigenwert $d_\lambda=m_\lambda$ gilt. Da $\mathbf{I}$ symmetrisch
ist, kann die bei $\mathbf{B}$ auftretende Situation ($d_\lambda<m_\lambda$)
für $\mathbf{I}$ nicht vorkommen, die Diagonalisierung gelingt also immer.
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe rechnet b) und d) vollständig an der Tafel, a), c) und e)
werden mündlich ergänzt. Coaching Impuls für d): Wie viele frei wählbare
Parameter liefert das Gleichungssystem, und was sagt das über die Dimension
des Eigenraums aus?
```

---

## Block 4 (1:10 bis 1:30) · Anwendungen der Diagonalisierung

Bezug: Kapitel 6.5, Anwendungen der Diagonalisierung

```{admonition} Aufgabe 4: Hauptachsen und Modalanalyse
:class: tip
**a)** Geben Sie für den Trägheitstensor $\mathbf{I}$ aus Block 2 und 3 die
Hauptträgheitsmomente mit Einheit an und nennen Sie die Richtung (den
Eigenvektor), in die das größere Hauptträgheitsmoment zeigt.

Ein Zweimassenschwinger mit $m=1$ kg hat die Steifigkeitsmatrix

$$\mathbf{K} = \begin{pmatrix}5 & -1\\ -1 & 5\end{pmatrix}\ \frac{\text{N}}{\text{m}}.$$

**b)** Bestimmen Sie die Eigenwerte von $\mathbf{K}$ über das
charakteristische Polynom.

**c)** Berechnen Sie die Eigenkreisfrequenzen $\omega_1$ und $\omega_2$ des
Systems.

**d)** Bestimmen Sie die Eigenvektoren (Eigenformen) zu beiden Eigenwerten
und beschreiben Sie in einem Satz, wie sich die beiden Massen bei jeder
Eigenform relativ zueinander bewegen.

**e)** Welchen Vorteil bietet die Diagonalisierung für die Berechnung der
Bewegungsgleichungen dieses Systems?
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** Die Hauptträgheitsmomente sind $I_1 = 9\cdot 10^4\ \text{mm}^4$ und
$I_2 = 4\cdot 10^4\ \text{mm}^4$. Das größere Hauptträgheitsmoment $I_1$
zeigt in Richtung des Eigenvektors $\vec{v}_1=\begin{pmatrix}-2\\
1\end{pmatrix}$.

**b)** $p(\lambda) = (5-\lambda)^2-1 = \lambda^2-10\lambda+24$. Mit der
pq-Formel: $\lambda_{1/2} = 5\pm\sqrt{25-24} = 5\pm 1$, also $\lambda_1=6$
und $\lambda_2=4$.

**c)** $\omega_1 = \sqrt{\lambda_1} = \sqrt{6} \approx 2{,}45\
\frac{\text{rad}}{\text{s}}$, $\omega_2 = \sqrt{\lambda_2} = \sqrt{4} = 2\
\frac{\text{rad}}{\text{s}}$.

**d)** Für $\lambda_1=6$: $\mathbf{K}-6\mathbf{E} = \begin{pmatrix}-1 &
-1\\ -1 & -1\end{pmatrix}$, also $v_2=-v_1$ und
$\vec{v}_1=\begin{pmatrix}1\\ -1\end{pmatrix}$. Die beiden Massen bewegen
sich gegenläufig, während eine Masse nach links geht, geht die andere nach
rechts.

Für $\lambda_2=4$: $\mathbf{K}-4\mathbf{E} = \begin{pmatrix}1 & -1\\ -1 &
1\end{pmatrix}$, also $v_1=v_2$ und $\vec{v}_2=\begin{pmatrix}1\\
1\end{pmatrix}$. Die beiden Massen bewegen sich gemeinsam in dieselbe
Richtung.

**e)** In der Basis der Eigenvektoren zerfällt das gekoppelte
Gleichungssystem in zwei vollständig unabhängige Einzelschwingungen, die
jede für sich separat berechnet werden können, statt das gekoppelte System
gemeinsam lösen zu müssen.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe bearbeitet b) bis d) vollständig an der Tafel, a) und e)
werden mündlich ergänzt. Da dies der letzte Block des Kapitels ist, eignet
sich e) gut als Zusammenfassung des gesamten Kapitels vor dem Ausblick auf
Kapitel 7.
```
