# Geführte Übung zu Kapitel 9: Lineare Differentialgleichungen 1. Ordnung

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Kapitel 9 hat genau vier
Unterkapitel, daher entspricht Block 1 bis 4 direkt 9.1 bis 9.4. Block 1, 2
und 4 verwenden durchgehend denselben RL-Reihenschwingkreis (R und L
identisch), damit die homogene Lösung aus Block 2 in Block 4 direkt
wiederverwendet werden kann.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, lineare ODEs klassifizieren (Kap. 9.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, die homogene Lösung (Kap. 9.2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, die partikuläre Lösung (Kap. 9.3) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, technische Anwendung RL-Kreis (Kap. 9.4) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Lineare ODEs klassifizieren

Bezug: Kapitel 9.1, Lineare Differentialgleichungen, Struktur erkennen und benennen

```{admonition} Aufgabe 1: Struktur von ODEs bestimmen
:class: tip
Ein RL-Reihenkreis mit Widerstand $R$, Induktivität $L$ und
Gleichspannungsquelle $U_0$ führt auf die ODE für den Strom $i(t)$:

$$\dot{i} + \frac{R}{L}\,i = \frac{U_0}{L}.$$

**a)** Klassifizieren Sie die folgenden fünf ODEs jeweils als linear oder
nichtlinear. Für die linearen ODEs geben Sie zusätzlich an, ob sie homogen
oder inhomogen sind und ob sie konstante oder variable Koeffizienten
haben.

| ODE | linear? | homogen? | Koeffizienten |
|---|---|---|---|
| $\dot{i}+\frac{R}{L}i=\frac{U_0}{L}$ | | | |
| $\dot{i}+\frac{R}{L}i=0$ | | | |
| $y'+\frac{2}{x}y=x^3$ | | | |
| $\dot{y}=y^2-4$ | | | |
| $\dot{y}+y\dot{y}=3$ | | | |

**b)** Geben Sie für die erste Gleichung (den RL-Kreis) explizit die
Koeffizientenfunktion $a_0(t)$ und die Störfunktion $g(t)$ in der
Standardform $\dot{i}+a_0(t)\,i=g(t)$ an.

**Zusatz (für schnelle Gruppen):** Nennen Sie die triviale Lösung der
homogenen RL-Gleichung (zweite Zeile der Tabelle) und verifizieren Sie sie
durch Einsetzen.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)**

| ODE | linear? | homogen? | Koeffizienten |
|---|---|---|---|
| $\dot{i}+\frac{R}{L}i=\frac{U_0}{L}$ | ja | nein | konstant |
| $\dot{i}+\frac{R}{L}i=0$ | ja | ja | konstant |
| $y'+\frac{2}{x}y=x^3$ | ja | nein | variabel |
| $\dot{y}=y^2-4$ | nein | — | — |
| $\dot{y}+y\dot{y}=3$ | nein | — | — |

**b)** $a_0(t) = \dfrac{R}{L}$ und $g(t) = \dfrac{U_0}{L}$.

**Zusatz:** Die triviale Lösung ist $i(t)=0$. Einsetzen: $\dot{i}+\frac{R}{L}i
= 0+\frac{R}{L}\cdot 0 = 0$, die Gleichung ist erfüllt.
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe füllt die Tabelle aus a) vollständig an der Tafel aus, b)
wird mündlich ergänzt. Coaching Impuls: Woran erkennen Sie sofort, dass die
letzten beiden Gleichungen nichtlinear sind?
```

---

## Block 2 (0:25 bis 0:45) · Die homogene Lösung

Bezug: Kapitel 9.2, Die homogene Lösung, warum ein Exponentialansatz funktioniert

```{admonition} Aufgabe 2: Homogene Lösung, konstant und variabel
:class: tip
Für den RL-Kreis aus Block 1 mit $R=50\ \Omega$ und $L=2$ H lautet die
homogene Gleichung

$$\dot{i} + 25\,i = 0.$$

**a)** Leiten Sie die allgemeine Lösung $i_h(t)$ vollständig durch
Trennung der Variablen her.

**b)** Bestätigen Sie Ihr Ergebnis mit der Formel $y_h(x) = A\,e^{-\int
f(x)\,dx}$ für konstante Koeffizienten.

Betrachten Sie nun die ODE mit variablem Koeffizienten

$$y' + 3x^2\,y = 0.$$

**c)** Bestimmen Sie die allgemeine Lösung $y_h(x)$ mit Hilfe der Formel
$y_h(x) = A\,e^{-\int f(x)\,dx}$.

**d)** Verifizieren Sie die Lösung aus c) durch Einsetzen in die ODE.

**Zusatz (für schnelle Gruppen):** Nennen Sie eine physikalische Situation,
in der ein variabler Koeffizient wie $f(x)=3x^2$ auftreten könnte.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** $$\frac{di}{i} = -25\,dt \Rightarrow \ln|i| = -25t+C_1
\Rightarrow i_h(t) = A\,e^{-25t}, \quad A\in\mathbb{R}.$$

**b)** Mit $f(t)=25$ (konstant) gilt $\int f(t)\,dt = 25t$, also
$$i_h(t) = A\,e^{-25t},$$
was mit a) übereinstimmt.

**c)** Mit $f(x)=3x^2$ gilt $\int 3x^2\,dx = x^3$, also
$$y_h(x) = A\,e^{-x^3}, \quad A\in\mathbb{R}.$$

**d)** $y_h'(x) = A\cdot(-3x^2)\,e^{-x^3}$. Einsetzen:
$$y_h' + 3x^2\,y_h = -3x^2 A\,e^{-x^3} + 3x^2 A\,e^{-x^3} = 0. \quad \checkmark$$

**Zusatz:** Zum Beispiel eine Kühlrippe, deren Wärmeübergangskoeffizient
sich entlang ihrer Länge $x$ ändert, oder ein Balken mit ortsabhängigem
Querschnitt, wie im Kapiteltext erwähnt.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet a) bis d) vollständig an der Tafel, der Zusatz wird
mündlich ergänzt. Das Ergebnis aus a) wird in Block 4 wiederverwendet.
Coaching Impuls für c): Welche Stammfunktion gehört zu $3x^2$?
```

---

## Block 3 (0:50 bis 1:10) · Die partikuläre Lösung

Bezug: Kapitel 9.3, Die partikuläre Lösung, einen passenden Ansatz erraten und bestimmen

```{admonition} Aufgabe 3: Ansatz vom Typ der rechten Seite
:class: tip
Gegeben sei die inhomogene ODE

$$y' + 2y = 6x.$$

**a)** Welchen Ansatz wählen Sie für $y_p(x)$? Begründen Sie mit der
Ansatztabelle aus dem Kapitel.

**b)** Setzen Sie den Ansatz in die ODE ein und bestimmen Sie die
unbekannten Koeffizienten durch Koeffizientenvergleich.

**c)** Geben Sie die allgemeine Lösung $y_{\text{allgemein}} = y_h+y_p$
an. Die homogene Lösung dürfen Sie ohne erneute Rechnung als
$y_h=A\,e^{-2x}$ verwenden.

**d)** Bestimmen Sie mit der Anfangsbedingung $y(0)=2$ die spezielle
Lösung.

**Zusatz (für schnelle Gruppen):** Bestimmen Sie die partikuläre Lösung
von $y'+3y=4e^{x}$ mit dem passenden Exponentialansatz.
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** Die Störfunktion $g(x)=6x$ ist ein Polynom vom Grad $1$, also
wählen wir den Ansatz $y_p(x) = a\,x+b$.

**b)** $y_p'=a$. Einsetzen: $a+2(ax+b) = 2ax+(a+2b) \stackrel{!}{=} 6x+0$.
Koeffizientenvergleich: $2a=6 \Rightarrow a=3$ und $a+2b=0 \Rightarrow
b=-1{,}5$. Also $y_p(x) = 3x-1{,}5$.

**c)** $$y_{\text{allgemein}}(x) = A\,e^{-2x} + 3x - 1{,}5$$

**d)** $y(0) = A - 1{,}5 = 2 \Rightarrow A = 3{,}5$. Die spezielle Lösung
lautet
$$y(x) = 3{,}5\,e^{-2x} + 3x - 1{,}5.$$

**Zusatz:** Ansatz $y_p=C\,e^{x}$ (da der Exponent $1$ nicht mit dem
homogenen Exponenten $-3$ übereinstimmt, kein Resonanzfall). $y_p'=Ce^x$.
Einsetzen: $Ce^x+3Ce^x=4Ce^x \stackrel{!}{=} 4e^x \Rightarrow C=1$, also
$y_p(x)=e^x$.
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe rechnet a) bis d) vollständig an der Tafel, der Zusatz wird
nur bei verbleibender Zeit ergänzt. Coaching Impuls für b): Welche
Potenzen von $x$ müssen auf beiden Seiten der Gleichung jeweils
übereinstimmen?
```

---

## Block 4 (1:10 bis 1:30) · Technische Anwendung, RL-Kreis

Bezug: Kapitel 9.4, Technische Anwendungen linearer ODEs 1. Ordnung

```{admonition} Aufgabe 4: Stromanstieg im RL-Kreis
:class: tip
Wir vervollständigen den RL-Kreis aus Block 1 und 2 mit $R=50\ \Omega$,
$L=2$ H und einer Gleichspannungsquelle $U_0=100$ V. Zu Beginn ist die
Spule stromlos, $i(0)=0$.

**a)** Stellen Sie mit der Maschenregel $U_0 = L\dot{i}+Ri$ die ODE in
Standardform $\dot{i}+\frac{R}{L}i=\frac{U_0}{L}$ auf und setzen Sie die
Zahlenwerte ein.

**b)** Übernehmen Sie die homogene Lösung aus Block 2.

**c)** Bestimmen Sie die partikuläre Lösung $i_p$ mit dem Ansatz für eine
konstante Störfunktion.

**d)** Geben Sie die allgemeine Lösung an und bestimmen Sie mit
$i(0)=0$ die spezielle Lösung $i(t)$.

**e)** Berechnen Sie den Strom nach einer Zeitkonstante $\tau = L/R$ und
geben Sie an, wie viel Prozent des Endwerts das entspricht.

**f)** Identifizieren Sie in der Lösung aus d) den transienten und den
stationären Anteil.

**Zusatz (für schnelle Gruppen):** Vergleichen Sie qualitativ mit dem
RC-Ladevorgang aus dem Kapiteltext: Welche Rolle übernimmt hier die
Induktivität $L$ im Vergleich zur Kapazität $C$ dort?
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** $$\dot{i} + \frac{50}{2}\,i = \frac{100}{2} \Rightarrow \dot{i} +
25\,i = 50$$

**b)** $i_h(t) = A\,e^{-25t}$ (aus Block 2a).

**c)** Ansatz $i_p=C$, also $\dot{i}_p=0$. Einsetzen: $25C \stackrel{!}{=}
50 \Rightarrow C=2$. Also $i_p = 2$ A.

**d)** Allgemeine Lösung: $i(t) = A\,e^{-25t}+2$. Mit $i(0)=A+2=0
\Rightarrow A=-2$:
$$i(t) = 2\left(1-e^{-25t}\right)\ \text{A}.$$

**e)** $\tau = \dfrac{L}{R} = \dfrac{2}{50} = 0{,}04$ s.
$$i(\tau) = 2(1-e^{-1}) \approx 2\cdot 0{,}632 \approx 1{,}26\ \text{A},$$
das entspricht rund $63{,}2\ \%$ des Endwerts $2$ A.

**f)** Der transiente Anteil ist $-2\,e^{-25t}$ (klingt ab), der
stationäre Anteil ist $2$ A (bleibt dauerhaft).

**Zusatz:** Die Induktivität $L$ übernimmt hier dieselbe Rolle wie die
Kapazität $C$ beim RC-Kreis: Sie bestimmt zusammen mit $R$ die
Zeitkonstante ($\tau=L/R$ statt $\tau=RC$), mit der sich das System dem
stationären Endzustand annähert. Während der Kondensator eine plötzliche
Spannungsänderung verhindert, verhindert die Induktivität eine plötzliche
Stromänderung.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe bearbeitet a), c) und d) vollständig an der Tafel, e) und
f) werden mündlich ergänzt. Da dies der letzte Block des Kapitels ist,
eignet sich der Zusatz gut als Zusammenfassung, wie sich Struktur und
Interpretation über verschiedene physikalische Systeme hinweg wiederholen.
```
