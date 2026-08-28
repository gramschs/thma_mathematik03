# Geführte Übung zu Kapitel 10: Variation der Konstanten und Methodenüberblick

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Kapitel 10 hat nur drei statt
vier Unterkapitel. Abschnitt 10.2 behandelt zwei klar getrennte Situationen,
die Kompaktformel im Normalfall und den Resonanzfall, daher wurde er auf
Block 2 und Block 3 aufgeteilt, damit das 4 Blöcke Format erhalten bleibt.
Block 4 entspricht dem Methodenüberblick aus 10.3 und dient als
Zusammenfassung des gesamten Blocks zu ODEs 1. Ordnung.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, Variation der Konstanten (Kap. 10.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Kompaktformel ohne Resonanz (Kap. 10.2, Teil 1) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, der Resonanzfall (Kap. 10.2, Teil 2) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, Methodenüberblick (Kap. 10.3) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Variation der Konstanten

Bezug: Kapitel 10.1, Variation der Konstanten

```{admonition} Aufgabe 1: Eine ODE mit variablem Koeffizienten
:class: tip
Gegeben sei die lineare ODE

$$y' + \frac{2}{x}\,y = x^2.$$

**a)** Bestimmen Sie die homogene Lösung $y_h(x)$ mit $f(x)=\dfrac{2}{x}$.

**b)** Machen Sie den Ansatz $y_p(x) = \dfrac{A(x)}{x^2}$ und leiten Sie
$y_p'(x)$ mit der Quotientenregel her.

**c)** Setzen Sie $y_p$ und $y_p'$ in die ODE ein und zeigen Sie, dass sich
alle Terme mit $A(x)$ selbst aufheben, sodass nur ein Term mit $A'(x)$
übrig bleibt.

**d)** Stellen Sie die Bestimmungsgleichung für $A'(x)$ auf und berechnen
Sie $A(x)$ durch Integration.

**e)** Geben Sie die allgemeine Lösung $y_{\text{allgemein}}(x)$ an und
benennen Sie darin $y_h$ und $y_p$.

**Zusatz (für schnelle Gruppen):** Verifizieren Sie $y_p=\dfrac{x^3}{5}$
durch Einsetzen in die ursprüngliche ODE.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** $\int \frac{2}{x}\,dx = 2\ln x$ (für $x>0$), also
$$y_h(x) = A\,e^{-2\ln x} = \frac{A}{x^2}, \quad A\in\mathbb{R}.$$

**b)** $$y_p'(x) = \frac{A'(x)}{x^2} - \frac{2A(x)}{x^3}$$

**c)** $$y_p' + \frac{2}{x}y_p = \frac{A'(x)}{x^2} - \frac{2A(x)}{x^3} +
\frac{2}{x}\cdot\frac{A(x)}{x^2} = \frac{A'(x)}{x^2} - \frac{2A(x)}{x^3} +
\frac{2A(x)}{x^3} = \frac{A'(x)}{x^2}$$
Die Terme mit $A(x)$ heben sich auf, da $A(x)/x^2$ die homogene Gleichung
erfüllt.

**d)** $$\frac{A'(x)}{x^2} \stackrel{!}{=} x^2 \Rightarrow A'(x) = x^4
\Rightarrow A(x) = \frac{x^5}{5} + C, \quad C\in\mathbb{R}$$

**e)** $$y_{\text{allgemein}}(x) = \frac{A(x)}{x^2} =
\frac{\frac{x^5}{5}+C}{x^2} = \underbrace{\frac{C}{x^2}}_{=y_h} +
\underbrace{\frac{x^3}{5}}_{=y_p}$$

**Zusatz:** $y_p' = \dfrac{3x^2}{5}$. Einsetzen:
$$y_p' + \frac{2}{x}y_p = \frac{3x^2}{5} + \frac{2}{x}\cdot\frac{x^3}{5} =
\frac{3x^2}{5}+\frac{2x^2}{5} = x^2. \quad \checkmark$$
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe rechnet b) bis e) vollständig an der Tafel, a) wird
mündlich ergänzt. Coaching Impuls für c): Warum ist es kein Zufall, dass
sich die $A(x)$ Terme aufheben?
```

---

## Block 2 (0:25 bis 0:45) · Kompaktformel ohne Resonanz

Bezug: Kapitel 10.2, erster Teil, die Kompaktformel für konstante Koeffizienten

```{admonition} Aufgabe 2: Kompaktformel anwenden
:class: tip
Gegeben sei die lineare ODE mit konstantem Koeffizienten

$$y' + 4y = 5\,e^{-x}.$$

**a)** Bestimmen Sie $a$ und die Störfunktion $g(x)$. Prüfen Sie, ob
Resonanz vorliegt, indem Sie den Exponenten von $g(x)$ mit $-a$
vergleichen.

**b)** Berechnen Sie das Integral $\displaystyle\int g(x)\,e^{ax}\,dx$.

**c)** Bestimmen Sie damit $y_p(x)$ über die Kompaktformel.

**d)** Geben Sie die allgemeine Lösung $y_{\text{allgemein}}(x)$ an.

**Zusatz (für schnelle Gruppen):** Bestimmen Sie mit $y(0)=2$ die spezielle
Lösung.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** $a=4$, $g(x)=5e^{-x}$, also Exponent $b=-1$. Es gilt $-a=-4 \neq
-1=b$, also liegt **keine** Resonanz vor.

**b)** $$\int 5e^{-x}\cdot e^{4x}\,dx = \int 5e^{3x}\,dx =
\frac{5}{3}e^{3x}$$

**c)** $$y_p(x) = \frac{5}{3}e^{3x}\cdot e^{-4x} = \frac{5}{3}e^{-x}$$

**d)** $$y_{\text{allgemein}}(x) = A\,e^{-4x} + \frac{5}{3}e^{-x}, \quad
A\in\mathbb{R}$$

**Zusatz:** $y(0) = A+\dfrac{5}{3} = 2 \Rightarrow A = \dfrac{1}{3}$. Die
spezielle Lösung lautet
$$y(x) = \frac{1}{3}e^{-4x} + \frac{5}{3}e^{-x}.$$
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet a) bis c) vollständig an der Tafel, d) wird
mündlich ergänzt. Coaching Impuls für a): Welche zwei Zahlen müssen Sie
vergleichen, um Resonanz auszuschließen?
```

---

## Block 3 (0:50 bis 1:10) · Der Resonanzfall

Bezug: Kapitel 10.2, zweiter Teil, der Resonanzfall

```{admonition} Aufgabe 3: Wenn der Standardansatz versagt
:class: tip
Gegeben sei die lineare ODE

$$y' - 3y = 4\,e^{3x}.$$

**a)** Bestimmen Sie $a$ und den Exponenten $b$ der Störfunktion. Zeigen
Sie, dass hier Resonanz vorliegt.

**b)** Zeigen Sie durch Einsetzen, dass der Standardansatz $y_p=C\,e^{3x}$
versagt.

**c)** Berechnen Sie mit der Kompaktformel das Integral
$\displaystyle\int g(x)\,e^{ax}\,dx$ und daraus $y_p(x)$.

**d)** Geben Sie die allgemeine Lösung an und identifizieren Sie die
Struktur $C\,x\,e^{bx}$ in $y_p$.

**Zusatz (für schnelle Gruppen):** Bestimmen Sie mit $y(0)=1$ die spezielle
Lösung.
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** In der Form $y'+ay=g(x)$ ist $a=-3$ und $g(x)=4e^{3x}$, also $b=3$.
Es gilt $-a=-(-3)=3=b$, also liegt Resonanz vor.

**b)** $y_p'-3y_p = 3Ce^{3x}-3Ce^{3x}=0 \neq 4e^{3x}$ für jedes $C$. Der
Ansatz versagt, weil $Ce^{3x}$ bereits die homogene Gleichung löst.

**c)** $$\int 4e^{3x}\cdot e^{-3x}\,dx = \int 4\,dx = 4x$$
$$y_p(x) = 4x\cdot e^{3x}$$

**d)** $$y_{\text{allgemein}}(x) = A\,e^{3x} + 4x\,e^{3x} = (A+4x)\,e^{3x}$$
Die partikuläre Lösung $y_p=4xe^{3x}$ hat genau die Struktur $C\,x\,e^{bx}$
mit $C=4$ und $b=3$.

**Zusatz:** $y(0) = A+0 = 1 \Rightarrow A=1$. Die spezielle Lösung lautet
$$y(x) = (1+4x)\,e^{3x}.$$
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe rechnet a) bis c) vollständig an der Tafel, d) wird
mündlich ergänzt. Coaching Impuls für b): Warum ergibt jeder Vielfache von
$e^{3x}$ beim Einsetzen zwingend Null?
```

---

## Block 4 (1:10 bis 1:30) · Methodenüberblick

Bezug: Kapitel 10.3, welches Verfahren für welche ODE?

```{admonition} Aufgabe 4: Erkennen, dann lösen
:class: tip
**a)** Ordnen Sie jede der folgenden ODEs, ohne zu rechnen, dem passenden
Lösungsverfahren zu: Trennung der Variablen, Substitution, Ansatz vom Typ
der rechten Seite oder Variation der Konstanten.

| ODE | Verfahren |
|---|---|
| $y' = (x+1)\,y$ | |
| $y' = (3x-y)^2+1$ | |
| $y'+5y=2\cos(x)$ | |
| $y'+\frac{1}{x^2}\,y=e^{x}$ | |

**b)** Lösen Sie die dritte ODE aus der Tabelle, $y'+5y=2\cos(x)$,
vollständig: Bestimmen Sie $y_h$, wählen Sie den passenden Ansatz für
$y_p$, führen Sie den Koeffizientenvergleich durch und geben Sie die
allgemeine Lösung an.

**c)** Bestimmen Sie mit $y(0)=0$ die spezielle Lösung.

**Zusatz (für schnelle Gruppen):** Die ODE $y'+5y=3e^{-5x}$ hat denselben
Koeffizienten $a=5$ wie Teilaufgabe b). Erklären Sie, ohne zu rechnen,
warum hier im Gegensatz zu b) ein Resonanzfall vorliegt.
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)**

| ODE | Verfahren |
|---|---|
| $y'=(x+1)y$ | Trennung der Variablen |
| $y'=(3x-y)^2+1$ | Substitution |
| $y'+5y=2\cos(x)$ | Ansatz vom Typ der rechten Seite |
| $y'+\frac{1}{x^2}y=e^x$ | Variation der Konstanten |

**b)** Homogene Lösung: $y_h=A\,e^{-5x}$. Ansatz $y_p=P\cos(x)+Q\sin(x)$,
$y_p'=-P\sin(x)+Q\cos(x)$. Einsetzen:
$$(Q+5P)\cos(x)+(5Q-P)\sin(x) \stackrel{!}{=} 2\cos(x)+0\sin(x)$$
Koeffizientenvergleich: $Q+5P=2$ und $5Q-P=0 \Rightarrow P=5Q$. Einsetzen:
$Q+25Q=26Q=2 \Rightarrow Q=\frac{1}{13}$, $P=\frac{5}{13}$.
$$y_{\text{allgemein}}(x) = A\,e^{-5x} + \frac{5}{13}\cos(x) +
\frac{1}{13}\sin(x)$$

**c)** $y(0) = A+\dfrac{5}{13} = 0 \Rightarrow A=-\dfrac{5}{13}$. Die
spezielle Lösung lautet
$$y(x) = -\frac{5}{13}e^{-5x} + \frac{5}{13}\cos(x) + \frac{1}{13}\sin(x).$$

**Zusatz:** Bei $y'+5y=3e^{-5x}$ ist $a=5$ und der Exponent der
Störfunktion $b=-5$. Es gilt $-a=-5=b$, also stimmt der Exponent der
Störfunktion mit dem der homogenen Lösung $y_h=Ae^{-5x}$ überein, das ist
per Definition der Resonanzfall. In Teilaufgabe b) ist die Störfunktion
dagegen trigonometrisch und hat keine mit $y_h$ vergleichbare
Exponentialform, daher tritt dort keine Resonanz auf.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe füllt die Tabelle aus a) an der Tafel aus und rechnet b)
vollständig, c) wird mündlich ergänzt. Da dies der letzte Block vor dem
Wechsel zu ODEs 2. Ordnung ist, eignet sich der Zusatz gut als Brücke zur
Resonanz bei Schwingungssystemen in Kapitel 11.
```
