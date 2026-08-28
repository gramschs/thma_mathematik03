# Geführte Übung zu Kapitel 7: Differentialgleichungen 1. Ordnung

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Kapitel 7 hat nur drei statt vier
Unterkapitel. Abschnitt 7.1 behandelt zwei recht unterschiedliche
Themenblöcke, Grundbegriffe wie Ordnung und Notation einerseits sowie
Lösungsbegriff und Anfangs beziehungsweise Randwertproblem andererseits,
daher wurde er auf Block 1 und Block 2 aufgeteilt, damit das 4 Blöcke Format
erhalten bleibt. Block 1 und 2 verwenden ein durchgehendes Beispiel
(Abkühlung eines Werkstücks), das auch in Block 3 und 4 weitergeführt wird.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, Grundbegriffe der ODE (Kap. 7.1, Teil 1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Lösungen, AWP und RWP (Kap. 7.1, Teil 2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, Richtungsfelder (Kap. 7.2) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, Euler-Verfahren (Kap. 7.3) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Grundbegriffe der ODE

Bezug: Kapitel 7.1, erster Teil, Was ist eine Differentialgleichung?

```{admonition} Aufgabe 1: ODEs erkennen und klassifizieren
:class: tip
**a)** Bestimmen Sie für jede der folgenden Gleichungen die Ordnung und
geben Sie an, ob es sich um eine gewöhnliche Differentialgleichung (ODE)
oder eine partielle Differentialgleichung (PDE) handelt.

| Gleichung | Ordnung | ODE oder PDE |
|---|---|---|
| $m\ddot{x} + c\dot{x} + kx = F(t)$ | | |
| $\dfrac{dT}{dt} = -a(T-T_U)$ | | |
| $\dfrac{\partial^2 u}{\partial x^2} + \dfrac{\partial^2 u}{\partial y^2} = 0$ | | |
| $EI\,w'''' = q(x)$ | | |

Ein Werkstück mit Anfangstemperatur $T(0) = 20\ °\text{C}$ wird in einen
Ofen mit konstanter Temperatur $T_U = 200\ °\text{C}$ gelegt. Nach dem
Newtonschen Abkühlungsgesetz ändert sich die Werkstücktemperatur $T(t)$
proportional zur Differenz zur Ofentemperatur:

$$\dot{T} = a\,(T_U - T), \quad a = 0{,}1\ \text{min}^{-1}.$$

**b)** Schreiben Sie diese Gleichung zusätzlich in Strich-Notation und in
Leibniz-Notation.

**c)** Bestimmen Sie Ordnung und Grad dieser Differentialgleichung und
begründen Sie Ihre Antwort kurz.

**Zusatz (für schnelle Gruppen):** Erklären Sie in ein bis zwei Sätzen,
warum die Wärmeleitungsgleichung eine PDE und keine ODE ist, während das
Newtonsche Abkühlungsgesetz oben eine ODE ist.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)**

| Gleichung | Ordnung | ODE oder PDE |
|---|---|---|
| $m\ddot{x}+c\dot{x}+kx=F(t)$ | 2 | ODE |
| $\dfrac{dT}{dt}=-a(T-T_U)$ | 1 | ODE |
| $\dfrac{\partial^2 u}{\partial x^2}+\dfrac{\partial^2 u}{\partial y^2}=0$ | 2 | PDE |
| $EI\,w''''=q(x)$ | 4 | ODE |

**b)** Strich-Notation: $T' = a(T_U-T)$. Leibniz-Notation:
$\dfrac{dT}{dt} = a(T_U-T)$.

**c)** Die Gleichung ist von 1. Ordnung, da nur die erste Ableitung
$\dot{T}$ auftritt, und von 1. Grad, da diese Ableitung linear (mit
Exponent 1) in der Gleichung erscheint.

**Zusatz:** Die Wärmeleitungsgleichung enthält partielle Ableitungen nach
zwei unabhängigen Variablen ($x$ und $y$ beziehungsweise $t$), die gesuchte
Funktion hängt also von mehreren Variablen gleichzeitig ab. Beim
Abkühlungsgesetz hängt $T$ dagegen nur von der einzigen Variable $t$ ab,
weshalb hier eine gewöhnliche Ableitung genügt.
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe füllt die Tabelle aus a) vollständig an der Tafel aus, b)
und c) werden mündlich ergänzt. Coaching Impuls: Woran erkennen Sie sofort,
ob mehr als eine unabhängige Variable im Spiel ist?
```

---

## Block 2 (0:25 bis 0:45) · Lösungen, Anfangs- und Randwertprobleme

Bezug: Kapitel 7.1, zweiter Teil, Lösungen und AWP/RWP

```{admonition} Aufgabe 2: Die Abkühlung des Werkstücks lösen
:class: tip
Wir bleiben beim Werkstück aus Block 1: $\dot{T} = a(T_U-T)$ mit $a =
0{,}1\ \text{min}^{-1}$, $T_U = 200\ °\text{C}$ und $T(0) = 20\ °\text{C}$.
Es wird behauptet, dass

$$T(t) = T_U + C\,e^{-at}$$

für jede Konstante $C$ eine Lösung der Differentialgleichung ist.

**a)** Verifizieren Sie diese Behauptung durch Einsetzen: Bilden Sie
$\dot{T}(t)$ und zeigen Sie, dass die rechte Seite $a(T_U-T(t))$ damit
übereinstimmt.

**b)** Setzen Sie die Anfangsbedingung $T(0)=20\ °\text{C}$ ein, um die
Konstante $C$ und damit die spezielle Lösung zu bestimmen.

**c)** Berechnen Sie mit der speziellen Lösung die Werkstücktemperatur nach
$10$ Minuten, $T(10)$.

**d)** Handelt es sich um ein Anfangswertproblem oder ein Randwertproblem?
Begründen Sie.

**Zusatz (für schnelle Gruppen):** Die Biegelinie eines beidseitig
gelagerten Balkens erfüllt $w(0)=0$ und $w(L)=0$. Erklären Sie, warum dies
ein Randwertproblem und kein Anfangswertproblem ist.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** $\dot{T}(t) = -aC\,e^{-at}$. Rechte Seite:
$$a(T_U-T(t)) = a\bigl(T_U - T_U - C e^{-at}\bigr) = -aC\,e^{-at}.$$
Beide Seiten stimmen für jedes $C$ überein, die Behauptung ist verifiziert.

**b)** $T(0) = T_U+C = 20 \Rightarrow C = 20-200 = -180$. Die spezielle
Lösung lautet
$$T(t) = 200 - 180\,e^{-0{,}1t}\ °\text{C}.$$

**c)** $T(10) = 200-180\,e^{-1} \approx 200-180\cdot 0{,}368 \approx
133{,}8\ °\text{C}$.

**d)** Es handelt sich um ein Anfangswertproblem, da die einzige Bedingung
$T(0)=20\ °\text{C}$ an einer einzigen Stelle, dem Startzeitpunkt $t=0$,
vorgegeben ist.

**Zusatz:** Die beiden Bedingungen $w(0)=0$ und $w(L)=0$ sind an zwei
verschiedenen Stellen vorgegeben, den beiden Balkenenden $x=0$ und $x=L$,
nicht an derselben Stelle. Das ist die definierende Eigenschaft eines
Randwertproblems.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet a) bis c) vollständig an der Tafel, d) wird
mündlich ergänzt. Das Ergebnis aus b) und c) wird in Block 4 zum Vergleich
mit dem Euler-Verfahren wiederverwendet. Coaching Impuls für a): Was genau
müssen Sie zeigen, damit eine Verifikation durch Einsetzen vollständig ist?
```

---

## Block 3 (0:50 bis 1:10) · Richtungsfelder

Bezug: Kapitel 7.2, Richtungsfelder

```{admonition} Aufgabe 3: Das Richtungsfeld der Abkühlung
:class: tip
Wir betrachten weiterhin $\dot{T} = a(T_U-T)$ mit $a=0{,}1\ \text{min}^{-1}$
und $T_U=200\ °\text{C}$.

**a)** Berechnen Sie die Steigung $\dot{T}$ für die Werte $T=20\ °\text{C}$,
$T=100\ °\text{C}$, $T=200\ °\text{C}$ und $T=250\ °\text{C}$.

**b)** Bestimmen Sie die Nullisokline dieser Differentialgleichung und
geben Sie ihre physikalische Bedeutung an.

**c)** Skizzieren Sie an der Tafel ein grobes Richtungsfeld: Zeichnen Sie
ein $(t,T)$-Koordinatensystem, tragen Sie die Nullisokline ein und deuten
Sie an ausgewählten Punkten oberhalb und unterhalb der Nullisokline die
Richtung der Linienelemente an (steigend oder fallend).

**d)** Handelt es sich bei $T_U$ um einen stabilen Gleichgewichtszustand
(Attraktor)? Begründen Sie mit dem Vorzeichen von $\dot{T}$ oberhalb und
unterhalb von $T_U$.

**Zusatz (für schnelle Gruppen):** Skizzieren Sie zusätzlich, wie die
Lösungskurve verliefe, wenn das Werkstück statt bei $20\ °\text{C}$ bei
$T(0)=250\ °\text{C}$ starten würde, also heißer als der Ofen ist.
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)**

| $T$ | $\dot{T} = 0{,}1\cdot(200-T)$ |
|---|---|
| $20\ °\text{C}$ | $18\ °\text{C/min}$ |
| $100\ °\text{C}$ | $10\ °\text{C/min}$ |
| $200\ °\text{C}$ | $0\ °\text{C/min}$ |
| $250\ °\text{C}$ | $-5\ °\text{C/min}$ |

**b)** Die Nullisokline ist die waagerechte Gerade $T=200\ °\text{C}$, also
genau die Ofentemperatur $T_U$. Auf dieser Linie ändert sich die
Werkstücktemperatur nicht mehr.

**c)** Unterhalb von $T=200\ °\text{C}$ zeigen alle Linienelemente nach
oben (steigende Temperatur), oberhalb zeigen sie nach unten (fallende
Temperatur), auf der Linie selbst sind sie waagerecht.

**d)** Ja, $T_U=200\ °\text{C}$ ist ein stabiler Gleichgewichtszustand. Für
$T<T_U$ ist $\dot{T}>0$, die Temperatur steigt gegen $T_U$; für $T>T_U$
ist $\dot{T}<0$, die Temperatur sinkt gegen $T_U$. Alle Lösungen streben
unabhängig vom Startwert gegen $T_U$.

**Zusatz:** Startet das Werkstück bei $T(0)=250\ °\text{C}$, liegt der
Startpunkt oberhalb der Nullisokline. Die Lösungskurve fällt von Beginn an
monoton und nähert sich von oben asymptotisch der Linie $T=200\ °\text{C}$
an, spiegelbildlich zur steigenden Kurve aus dem Hauptteil der Aufgabe.
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe zeichnet die Skizze aus c) vollständig an der Tafel, a)
und b) werden vorbereitend mündlich geklärt. Coaching Impuls für d): Was
bedeutet ein positives beziehungsweise negatives Vorzeichen von $\dot{T}$
für den Verlauf der Kurve?
```

---

## Block 4 (1:10 bis 1:30) · Euler-Verfahren

Bezug: Kapitel 7.3, Das Euler-Verfahren

```{admonition} Aufgabe 4: Abkühlung numerisch berechnen
:class: tip
Wir wenden das Euler-Verfahren auf $\dot{T}=a(T_U-T)$ mit $a=0{,}1\
\text{min}^{-1}$, $T_U=200\ °\text{C}$, $T(0)=20\ °\text{C}$ an, mit der
Schrittweite $h=5$ min.

**a)** Führen Sie den ersten Euler-Schritt von Hand durch: Berechnen Sie
$F(t_0,T_0)$ und daraus $T_1$ bei $t_1=5$ min.

**b)** Führen Sie den zweiten Euler-Schritt durch und berechnen Sie $T_2$
bei $t_2=10$ min.

**c)** Vergleichen Sie $T_2$ mit der exakten Lösung $T(10)$ aus Block 2.
Wie groß ist der Fehler?

**d)** Erklären Sie, warum die Euler-Näherung von der exakten Lösung
abweicht. Nutzen Sie dazu die Krümmung der Lösungskurve nahe $t=0$.

**Zusatz (für schnelle Gruppen):** Was würden Sie erwarten, wenn Sie
stattdessen mit der kleineren Schrittweite $h=1$ min rechnen würden, ohne
die Rechnung tatsächlich durchzuführen? Wie verändert sich der Fehler
vermutlich, und welchen Preis zahlt man dafür?
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** $F(t_0,T_0) = 0{,}1\cdot(200-20) = 18\ °\text{C/min}$.
$$T_1 = T_0+h\cdot F(t_0,T_0) = 20+5\cdot 18 = 110\ °\text{C}$$

**b)** $F(t_1,T_1) = 0{,}1\cdot(200-110) = 9\ °\text{C/min}$.
$$T_2 = T_1+h\cdot F(t_1,T_1) = 110+5\cdot 9 = 155\ °\text{C}$$

**c)** Die exakte Lösung liefert $T(10) \approx 133{,}8\ °\text{C}$
(Block 2c). Der Fehler beträgt $155-133{,}8 \approx 21{,}2\ °\text{C}$, die
Euler-Näherung überschätzt die Temperatur deutlich.

**d)** Die Lösungskurve ist nahe $t=0$ stark gekrümmt, da die Steigung
dort am größten ist und schnell abnimmt. Das Euler-Verfahren verwendet
jedoch für den gesamten Schritt nur die Steigung am linken Rand des
Intervalls und ignoriert, dass die Steigung im Verlauf des Schritts bereits
abnimmt. Dadurch wird die Temperatur zu stark erhöht, und dieser Fehler
setzt sich im nächsten Schritt fort.

**Zusatz:** Mit $h=1$ min würde der Fehler deutlich kleiner ausfallen, da
die Steigung innerhalb jedes einzelnen, kürzeren Schritts nahezu konstant
bleibt und die Tangente die Kurve besser annähert. Der Preis dafür ist ein
deutlich höherer Rechenaufwand, da für denselben Zeitraum fünfmal so viele
Schritte berechnet werden müssen.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe rechnet a) bis c) vollständig an der Tafel, d) wird
mündlich ergänzt. Da dies der letzte Block des Kapitels ist, eignet sich
der Zusatz gut als Übergang zur Diskussion genauerer Verfahren wie
Runge-Kutta in späteren Vorlesungen.
```
