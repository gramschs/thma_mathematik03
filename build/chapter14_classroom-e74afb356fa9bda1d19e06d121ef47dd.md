# Geführte Übung zu Kapitel 14: Symmetrie, Konvergenz und komplexe Fourierreihe

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Kapitel 14 hat genau vier
Unterkapitel, daher entspricht Block 1 bis 4 direkt 14.1 bis 14.4. Alle vier
Blöcke greifen auf das Ventiltaktsignal aus Kapitel 13, Block 4 zurück
($f(t)=\pm 3$, $T=2\pi$, $\omega_0=1$, $b_n=12/(n\pi)$ für ungerades $n$),
damit Symmetrie, Konvergenz, komplexe Darstellung und Resonanz als
zusammenhängende Untersuchung eines einzigen Signals erlebt werden.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, gerade und ungerade Funktionen (Kap. 14.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Konvergenz und Gibbssches Phänomen (Kap. 14.2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, komplexe Fourierreihe (Kap. 14.3) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, erzwungene Schwingung mit periodischer Erregung (Kap. 14.4) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Gerade und ungerade Funktionen

Bezug: Kapitel 14.1, Symmetrie nutzen, Kosinus- und Sinusreihen

```{admonition} Aufgabe 1: Symmetrie erkennen und ausnutzen
:class: tip
**a)** Das Ventiltaktsignal aus Kapitel 13, Block 4,
$f(t)=\begin{cases}-3,& -\pi\leq t<0\\ 3,& 0\leq t<\pi\end{cases}$,
erfüllt $f(-t)=-f(t)$. Welche Konsequenz hat das für die Koeffizienten
$a_n$?

Ein Nockenprofil hat den symmetrischen Hub

$$g(t) = 2(\pi - |t|), \quad t\in[-\pi,\pi), \quad T=2\pi.$$

**b)** Prüfen Sie mit der Definition, ob $g$ gerade oder ungerade ist.

**c)** Berechnen Sie mit der vereinfachten Formel für gerade Funktionen,
$a_0=\frac{4}{T}\int_0^{T/2} g(t)\,dt$, den Koeffizienten $a_0$.

**d)** Begründen Sie ohne Rechnung, dass $b_n=0$ für alle $n$ gilt.

**e)** Die weiteren Koeffizienten lauten $a_n=\dfrac{8}{n^2\pi}$ für
ungerades $n$ und $0$ für gerades $n$ (Herleitung analog zum Kapiteltext,
hier nicht neu zu berechnen). Geben Sie die vollständige Fourierreihe von
$g$ in kompakter Summenform an.

**Zusatz (für schnelle Gruppen):** Vergleichen Sie das Abklingverhalten
$a_n\sim 1/n^2$ von $g$ mit $b_n\sim 1/n$ von $f$ aus a). Welche
Eigenschaft der beiden Funktionen (Sprungstellen versus Knickstellen)
erklärt den Unterschied?
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** Da $f$ ungerade ist, gilt $a_n=0$ für alle $n\geq 0$, die
Fourierreihe ist eine reine Sinusreihe.

**b)** $g(-t)=2(\pi-|-t|)=2(\pi-|t|)=g(t)$, also ist $g$ **gerade**.

**c)** Auf $[0,\pi)$ gilt $g(t)=2(\pi-t)$.
$$a_0 = \frac{4}{2\pi}\int_0^{\pi} 2(\pi-t)\,dt =
\frac{2}{\pi}\left[2\pi t - t^2\right]_0^{\pi} =
\frac{2}{\pi}(2\pi^2-\pi^2) = \frac{2}{\pi}\cdot\pi^2 = 2\pi$$

**d)** $g$ ist gerade, das Produkt aus einer geraden Funktion und der
ungeraden Sinusfunktion ist ungerade, und das Integral einer ungeraden
Funktion über ein symmetrisches Intervall verschwindet. Also $b_n=0$ für
alle $n$.

**e)** Mit $a_0/2=\pi$ und $n=2k-1$:
$$g(t) = \pi + \frac{8}{\pi}\sum_{k=1}^{\infty}
\frac{\cos\bigl((2k-1)t\bigr)}{(2k-1)^2}$$

**Zusatz:** $f$ hat echte Sprungstellen bei $t=0,\pm\pi$, während $g$
überall stetig ist und nur Knickstellen (Sprünge in der Ableitung) hat.
Sprungstellen führen zu langsam abklingenden Koeffizienten ($1/n$),
Knickstellen ohne Sprünge im Funktionswert zu schneller abklingenden
Koeffizienten ($1/n^2$).
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe rechnet b) und c) vollständig an der Tafel, a) und d)
werden mündlich ergänzt. Coaching Impuls für b): Skizzieren Sie $g$ kurz,
erkennen Sie die Symmetrie auch grafisch?
```

---

## Block 2 (0:25 bis 0:45) · Konvergenz und Gibbssches Phänomen

Bezug: Kapitel 14.2, Konvergenzgeschwindigkeit und Gibbssches Phänomen

```{admonition} Aufgabe 2: Überschwingen an der Sprungstelle
:class: tip
Wir betrachten wieder das Ventiltaktsignal $f(t)=\pm 3$ aus Block 1a).

**a)** An welchen Stellen im Intervall $[-\pi,\pi)$ hat $f$
Sprungstellen?

**b)** Bestimmen Sie den Wert, gegen den die Fourierreihe von $f$ an der
Stelle $t=0$ konvergiert.

**c)** Bestimmen Sie die Sprunghöhe $\Delta=f(0+)-f(0-)$ und schätzen Sie
mit der Faustregel $\delta\approx 0{,}09\cdot|\Delta|$ das Gibbssche
Überschwingen ab.

**d)** Auf welchen ungefähren Wert steigen die Partialsummen von $f$ also
kurz vor der Sprungstelle an, obwohl $f$ selbst nur bis $3$ reicht?

**e)** Vergleichen Sie mit der Dreiecksschwingung $g$ aus Block 1: Zeigt
$g$ ebenfalls ein Gibbssches Überschwingen? Begründen Sie mit den
Dirichlet-Bedingungen beziehungsweise der Stetigkeit von $g$.

**Zusatz (für schnelle Gruppen):** Nennen Sie eine technische Situation,
in der das Gibbssche Phänomen bei der Auslegung eines Filters oder einer
Steuerung berücksichtigt werden muss.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** Sprungstellen bei $t=0$ und $t=\pm\pi$.

**b)** $\dfrac{f(0-)+f(0+)}{2} = \dfrac{-3+3}{2} = 0$.

**c)** $\Delta = 3-(-3) = 6$. Überschwingen
$\delta \approx 0{,}09\cdot 6 = 0{,}54$.

**d)** Die Partialsummen erreichen nahe der Sprungstelle Werte von
ungefähr $3+0{,}54=3{,}54$, obwohl $f$ nur zwischen $-3$ und $3$
variiert.

**e)** Nein, $g$ zeigt kein Gibbssches Überschwingen, da $g$ überall
stetig ist (keine Sprungstellen, nur Knickstellen). Das Gibbssche
Phänomen tritt ausschließlich an echten Sprungstellen auf.

**Zusatz:** Zum Beispiel bei Schaltimpulsen eines Hydraulikventils oder
bei abrupten Lastwechseln, wo eine aus endlich vielen Harmonischen
rekonstruierte Kraft die Spitzenlast nahe dem Umschaltmoment systematisch
überschätzt.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe bearbeitet a) bis d) vollständig an der Tafel, e) wird
mündlich ergänzt. Coaching Impuls für e): Welche Voraussetzung aus den
Dirichlet-Bedingungen unterscheidet $f$ und $g$ an dieser Stelle?
```

---

## Block 3 (0:50 bis 1:10) · Die komplexe Fourierreihe

Bezug: Kapitel 14.3, die komplexe Fourierreihe

```{admonition} Aufgabe 3: Komplexe Koeffizienten des Ventiltaktsignals
:class: tip
Für das Ventiltaktsignal $f(t)=\pm 3$ aus Block 1 und 2 gilt $a_0=0$,
$a_n=0$ für alle $n$, und $b_n=\dfrac{12}{n\pi}$ für ungerades $n$
(sonst $0$), siehe Kapitel 13, Block 4.

**a)** Berechnen Sie $c_0$, $c_n$ und $c_{-n}$ für ungerades $n$ mit den
Umrechnungsformeln.

**b)** Prüfen Sie, dass $c_{-n}=\overline{c_n}$ gilt, wie es für eine
reellwertige Funktion sein muss.

**c)** Verifizieren Sie durch Rückrechnung: Berechnen Sie
$c_1 e^{it}+c_{-1}e^{-it}$ und zeigen Sie, dass sich $b_1\sin(t)$ mit
$b_1=12/\pi$ ergibt.

**d)** Geben Sie die Amplitude der ersten Harmonischen
$\hat{A}_1=2|c_1|$ an und vergleichen Sie mit $b_1$.

**e)** Geben Sie $|c_n|$ allgemein für ungerades $n$ an und beschreiben
Sie in einem Satz, wie das Amplitudenspektrum von $f$ aussieht.

**Zusatz (für schnelle Gruppen):** Berechnen Sie $|c_3|$ und die
physikalische Amplitude $\hat{A}_3$. Welchen Bruchteil von $\hat{A}_1$
trägt die dritte Harmonische bei?
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** $c_0=\dfrac{a_0}{2}=0$. Für ungerades $n$:
$$c_n = \frac{a_n-ib_n}{2} = \frac{0-i\cdot\frac{12}{n\pi}}{2} =
-\frac{6i}{n\pi}, \qquad
c_{-n} = \frac{a_n+ib_n}{2} = \frac{6i}{n\pi}$$

**b)** $\overline{c_n} = \overline{-\frac{6i}{n\pi}} = \frac{6i}{n\pi} =
c_{-n}$. $\checkmark$

**c)**
$$c_1e^{it}+c_{-1}e^{-it} = -\frac{6i}{\pi}e^{it}+\frac{6i}{\pi}e^{-it}
= -\frac{6i}{\pi}\bigl(e^{it}-e^{-it}\bigr) =
-\frac{6i}{\pi}\cdot 2i\sin(t) = \frac{12}{\pi}\sin(t)$$
Das stimmt mit $b_1\sin(t)$, $b_1=12/\pi$, überein. $\checkmark$

**d)** $|c_1|=\dfrac{6}{\pi}$, also $\hat{A}_1=2\cdot\dfrac{6}{\pi} =
\dfrac{12}{\pi} = b_1$, wie erwartet, da $a_1=0$.

**e)** $|c_n|=\dfrac{6}{n\pi}$ für ungerades $n$, sonst $0$. Das
Amplitudenspektrum besteht also nur aus Linien bei den ungeraden
Vielfachen von $\omega_0=1$, deren Höhen wie $1/n$ abklingen.

**Zusatz:** $|c_3|=\dfrac{6}{3\pi}=\dfrac{2}{\pi}$, also
$\hat{A}_3=2\cdot\dfrac{2}{\pi}=\dfrac{4}{\pi}$. Es gilt
$\hat{A}_3/\hat{A}_1 = \dfrac{4/\pi}{12/\pi} = \dfrac{1}{3}$, die dritte
Harmonische trägt also ein Drittel der Grundschwingungsamplitude.
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe rechnet a) und c) vollständig an der Tafel, b), d) und e)
werden mündlich ergänzt. Coaching Impuls für a): Welche Formel brauchen
Sie, wenn $a_n=0$ ist und nur $b_n$ übrig bleibt?
```

---

## Block 4 (1:10 bis 1:30) · Erzwungene Schwingung mit periodischer Erregung

Bezug: Kapitel 14.4, erzwungene Schwingung mit periodischer Erregung

```{admonition} Aufgabe 4: Welche Harmonische gefährdet das System?
:class: tip
Ein Feder-Masse-System mit Eigenkreisfrequenz $\omega_{\text{sys}}=3$
rad/s wird durch die Kraft $F(t)=F_0\cdot f(t)$ erregt, wobei $f$ das
Ventiltaktsignal aus den Blöcken 1 bis 3 ist ($\omega_0=1$ rad/s).

**a)** Bestimmen Sie die Ordnung $n$ der Harmonischen, bei der
$n\,\omega_0=\omega_{\text{sys}}$ gilt.

**b)** Ist $n$ aus a) eine Harmonische mit nichtverschwindendem
Koeffizienten? Begründen Sie mit der Symmetrie von $f$.

**c)** Bestimmen Sie die Amplitude dieser resonanzgefährdenden
Harmonischen, $\hat{F}_n = b_n\cdot F_0$.

**d)** Vergleichen Sie $\hat{F}_n$ mit der Grundschwingungsamplitude
$\hat{F}_1=b_1\cdot F_0$. Welchen Bruchteil trägt die gefährliche
Harmonische bei?

**e)** Beschreiben Sie in Stichworten die dreistufige Lösungsstrategie
für die vollständige Antwort des Systems auf $F(t)$ (kein vollständiges
Lösen nötig).

**Zusatz (für schnelle Gruppen):** Geben Sie die allgemeine Formel
$\omega_0' = \omega_{\text{sys}}/n$ für weitere kritische
Grundkreisfrequenzen an und berechnen Sie die Werte für $n=5$ und $n=7$.
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** $n = \dfrac{\omega_{\text{sys}}}{\omega_0} = \dfrac{3}{1} = 3$.

**b)** Ja, $n=3$ ist ungerade, und für das Ventiltaktsignal gilt
$b_n\neq 0$ für alle ungeraden $n$. Resonanz tritt also tatsächlich auf.

**c)** $\hat{F}_3 = b_3\cdot F_0 = \dfrac{12}{3\pi}\,F_0 =
\dfrac{4}{\pi}\,F_0 \approx 1{,}27\,F_0$.

**d)** $\hat{F}_1 = b_1\cdot F_0 = \dfrac{12}{\pi}\,F_0$. Verhältnis:
$$\frac{\hat{F}_3}{\hat{F}_1} = \frac{4/\pi}{12/\pi} = \frac{1}{3}$$
Die dritte Harmonische trägt ein Drittel der
Grundschwingungsamplitude bei, ein keineswegs vernachlässigbarer Anteil.

**e)** 1. Fourierzerlegung: Koeffizienten $a_n$, $b_n$ von $F(t)$
bestimmen. 2. Komponentenweise Lösung: für jeden Term $a_n\cos(n\omega_0
t)$ und $b_n\sin(n\omega_0 t)$ die partikuläre Lösung einzeln mit dem
Ansatz vom Typ der rechten Seite bestimmen. 3. Überlagerung: alle
partikulären Lösungen sowie die homogene Lösung addieren.

**Zusatz:** $\omega_0' = \omega_{\text{sys}}/n = 3/n$. Für $n=5$:
$\omega_0'=0{,}6$ rad/s. Für $n=7$: $\omega_0'\approx 0{,}4286$ rad/s.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe bearbeitet a) bis d) vollständig an der Tafel, e) wird
mündlich zusammengefasst. Da dies der letzte Block des letzten Kapitels
ist, eignet sich der Zusatz gut als Abschlussdiskussion über kritische
Drehzahlen beim Hochlauf, und ein kurzer Ausblick auf die
Fouriertransformation für nichtperiodische Signale rundet die Übung ab.
```
