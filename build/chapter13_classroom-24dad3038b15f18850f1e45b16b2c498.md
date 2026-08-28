# Geführte Übung zu Kapitel 13: Fourierreihen

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Kapitel 13 hat genau vier
Unterkapitel, daher entspricht Block 1 bis 4 direkt 13.1 bis 13.4. Block 1
und 2 verwenden ein Lüfterrad mit $n=1200$ min$^{-1}$ als durchgehendes
Beispiel ($T=50$ ms). Block 3 und 4 wechseln, wie im Kapiteltext auch, zu
abstrakten periodischen Funktionen, damit die Integrale übersichtlich
bleiben.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, periodische Funktionen (Kap. 13.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Grund- und Oberschwingungen (Kap. 13.2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, Fourierkoeffizienten, $a_0$ und Dirichlet (Kap. 13.3) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, vollständige Fourierreihe berechnen (Kap. 13.4) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Periodische Funktionen

Bezug: Kapitel 13.1, periodische Funktionen und periodische Fortsetzung

```{admonition} Aufgabe 1: Schwingung eines Lüfterrads
:class: tip
Ein Lüfterrad dreht mit $n=1200$ min$^{-1}$.

**a)** Berechnen Sie die Periode $T$ einer Umdrehung.

**b)** Berechnen Sie die Kreisfrequenz $\omega_0=2\pi/T$.

Die Schwingung eines Sensors am Lüftergehäuse wird vereinfacht durch
$f(t)=4\sin(\omega_0 t)$ mm modelliert.

**c)** Verifizieren Sie durch Einsetzen, dass $f(t+T)=f(t)$ gilt.

Ein Messgerät liefert auf dem Intervall $[0, T)$ die Funktion
$g(t)=4\sin\!\left(\frac{2\pi}{T}t\right)+\sin\!\left(\frac{4\pi}{T}t\right)$.

**d)** Bestimmen Sie für $t_1=130$ ms und $t_2=-15$ ms den jeweils
reduzierten Zeitpunkt im Grundintervall $[0,T)$ und geben Sie
$\tilde{g}(t_1)$ sowie $\tilde{g}(t_2)$ in Form von $g(\ldots)$ an.

**Zusatz (für schnelle Gruppen):** Bestätigen Sie
$\tilde{g}(t_2+T)=\tilde{g}(t_2)$ anhand Ihres Ergebnisses aus d).
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** $n=1200$ min$^{-1}=20$ Umdrehungen/s, also
$$T=\frac{1}{20\ \text{s}^{-1}} = 0{,}05\ \text{s} = 50\ \text{ms}.$$

**b)** $$\omega_0=\frac{2\pi}{0{,}05\ \text{s}} = 40\pi\ \text{rad/s}
\approx 125{,}7\ \text{rad/s}.$$

**c)** $f(t+T)=4\sin(40\pi(t+0{,}05))=4\sin(40\pi t+2\pi)=4\sin(40\pi t)=
f(t)$, da $40\pi\cdot 0{,}05=2\pi$. $\checkmark$

**d)** Für $t_1=130$ ms: $\dfrac{t_1}{T}=\dfrac{130}{50}=2{,}6
\Rightarrow k=\lfloor 2{,}6\rfloor=2$. Reduziert:
$130-2\cdot 50=30$ ms, also $\tilde{g}(130\ \text{ms})=g(30\ \text{ms})$.

Für $t_2=-15$ ms: $\dfrac{t_2}{T}=\dfrac{-15}{50}=-0{,}3
\Rightarrow k=\lfloor -0{,}3\rfloor=-1$. Reduziert:
$-15-(-1)\cdot 50=35$ ms, also $\tilde{g}(-15\ \text{ms})=g(35\ \text{ms})$.

**Zusatz:** $\tilde{g}(t_2+T)=\tilde{g}(35\ \text{ms})=g(35\ \text{ms})$,
das stimmt mit $\tilde{g}(t_2)=g(35\ \text{ms})$ aus d) überein.
$\checkmark$
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe rechnet a), b) und d) vollständig an der Tafel, c) wird
mündlich ergänzt. Coaching Impuls für d): Was genau bewirkt die
Abrundungsfunktion $\lfloor \cdot \rfloor$ hier?
```

---

## Block 2 (0:25 bis 0:45) · Grund- und Oberschwingungen

Bezug: Kapitel 13.2, Grundschwingung und Oberschwingungen

```{admonition} Aufgabe 2: Schaufelfrequenz des Lüfterrads
:class: tip
Wir bleiben beim Lüfterrad aus Block 1, $T=50$ ms.

**a)** Berechnen Sie die Grundfrequenz $f_0=1/T$.

**b)** Berechnen Sie die zugehörige Kreisfrequenz $\omega_0=2\pi f_0$ und
vergleichen Sie mit Block 1b).

Das Lüfterrad hat $5$ Schaufeln. Jede vorbeilaufende Schaufel erzeugt
einen Kraftstoß, sodass die Schaufelfrequenz der $5$. Harmonischen
entspricht.

**c)** Berechnen Sie Frequenz $f_5$ und Kreisfrequenz $\omega_5$ dieser
$5$. Harmonischen.

**d)** Die Grundschwingung hat die Amplitude $A_1=4$ mm, die
Schaufelfrequenz-Komponente $A_5=0{,}6$ mm. Bilden Sie
$s(t)=A_1\sin(\omega_0 t)+A_5\sin(5\omega_0 t)$ und bestätigen Sie, dass
beide Anteile nach der Zeit $T$ eine ganzzahlige Anzahl von Zyklen
durchlaufen haben.

**e)** Ein auffälliger Peak bei $100$ Hz in einer Schwingungsmessung des
Lüfters, worauf deutet er hin?

**Zusatz (für schnelle Gruppen):** Berechnen Sie Frequenz und
Kreisfrequenz der $3$. Harmonischen und überlegen Sie, welches
physikalische Phänomen (z. B. eine Unwucht oder eine Asymmetrie) einen
Peak bei dieser Ordnung erzeugen könnte.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** $f_0=\dfrac{1}{0{,}05\ \text{s}}=20$ Hz.

**b)** $\omega_0=2\pi\cdot 20=40\pi\ \text{rad/s}$, identisch mit Block
1b).

**c)** $f_5=5\cdot 20=100$ Hz, $\omega_5=5\cdot 40\pi=200\pi\ \text{rad/s}
\approx 628{,}3\ \text{rad/s}$.

**d)** $s(t)=4\sin(40\pi t)+0{,}6\sin(200\pi t)$. Nach der Zeit $T=0{,}05$
s gilt $\omega_0 T=40\pi\cdot 0{,}05=2\pi$ (ein Zyklus) und
$5\omega_0 T=200\pi\cdot 0{,}05=10\pi=5\cdot 2\pi$ (fünf Zyklen). Beide
Anteile kehren also zum Ausgangswert zurück, $s(t+T)=s(t)$.

**e)** Ein Peak bei $100$ Hz entspricht der $5$. Harmonischen und deutet
auf die Schaufelfrequenz des Lüfterrads hin, also auf die periodische
Kraftanregung durch die vorbeilaufenden Schaufeln.

**Zusatz:** $f_3=3\cdot 20=60$ Hz, $\omega_3=3\cdot 40\pi=120\pi\
\text{rad/s}\approx 377{,}0\ \text{rad/s}$. Ein Peak bei $60$ Hz könnte
zum Beispiel auf eine Unwucht oder eine dreifache Asymmetrie des
Laufrads hindeuten.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet a) bis d) vollständig an der Tafel, e) wird
mündlich ergänzt. Coaching Impuls für d): Woran erkennen Sie sofort, ohne
weiter zu rechnen, dass die Summe $s(t)$ periodisch mit $T$ ist?
```

---

## Block 3 (0:50 bis 1:10) · Fourierkoeffizienten, $a_0$ und Dirichlet-Bedingungen

Bezug: Kapitel 13.3, die Fourierreihe und ihre Koeffizienten

```{admonition} Aufgabe 3: Mittelwert eines Drucksignals
:class: tip
Das Drucksignal einer Kolbenpumpe wird über eine Periode $T=50$ ms durch

$$f(t) = \begin{cases} 6, & 0 \leq t < T/3, \\ -1, & T/3 \leq t < T
\end{cases}$$

modelliert (Werte in bar).

**a)** Stellen Sie das Integral für $a_0=\frac{2}{T}\int_{-T/2}^{T/2}
f(t)\,dt$ auf, aufgeteilt in die beiden Teilintervalle.

**b)** Berechnen Sie $a_0$.

**c)** Interpretieren Sie $a_0/2$ als Mittelwert und bestätigen Sie das
Ergebnis anhand der Zeitanteile ($1/3$ der Periode bei $6$ bar, $2/3$ bei
$-1$ bar).

**d)** Prüfen Sie, ob $f$ die Dirichlet-Bedingungen erfüllt, und geben Sie
an, gegen welchen Wert die Fourierreihe an der Sprungstelle $t=T/3$
konvergiert.

**Zusatz (für schnelle Gruppen):** Stellen Sie, ohne es auszuwerten, das
Integral für $a_n$ ($n\geq 1$) für dieses $f$ auf.
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** $$a_0 = \frac{2}{T}\left(\int_0^{T/3} 6\,dt +
\int_{T/3}^{T} (-1)\,dt\right)$$

**b)**
$$a_0 = \frac{2}{T}\left(6\cdot\frac{T}{3} + (-1)\cdot\frac{2T}{3}\right)
= \frac{2}{T}\left(2T-\frac{2T}{3}\right) = \frac{2}{T}\cdot\frac{4T}{3}
= \frac{8}{3} \approx 2{,}67$$

**c)** Der Mittelwert ist $a_0/2=4/3\approx 1{,}33$ bar. Zeitgewichtet:
$6\cdot\frac{1}{3}+(-1)\cdot\frac{2}{3} = 2-\frac{2}{3}=\frac{4}{3}$,
stimmt überein. $\checkmark$

**d)** Auf beiden Teilintervallen ist $f$ konstant, also stetig und
monoton, und an der Sprungstelle $t=T/3$ existieren beide einseitigen
Grenzwerte ($6$ von links, $-1$ von rechts). Die Dirichlet-Bedingungen
sind erfüllt. Die Fourierreihe konvergiert bei $t=T/3$ gegen den
Mittelwert $\dfrac{6+(-1)}{2}=2{,}5$ bar.

**Zusatz:**
$$a_n = \frac{2}{T}\left(\int_0^{T/3} 6\cos(n\omega_0 t)\,dt +
\int_{T/3}^{T} (-1)\cos(n\omega_0 t)\,dt\right)$$
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe rechnet a) bis c) vollständig an der Tafel, d) wird
mündlich ergänzt. Coaching Impuls für c): Warum ist es sinnvoll, das
Ergebnis über die Zeitanteile gegenzuprüfen, statt der Integralrechnung
blind zu vertrauen?
```

---

## Block 4 (1:10 bis 1:30) · Vollständige Fourierreihe berechnen

Bezug: Kapitel 13.4, Fourierreihen berechnen, Beispiele

```{admonition} Aufgabe 4: Fourierreihe eines Ventiltaktsignals
:class: tip
Ein Zweiwege-Schaltventil erzeugt ein symmetrisches Rechtecksignal mit
Periode $T=2\pi$ und Kreisfrequenz $\omega_0=1$:

$$f(t) = \begin{cases} -3, & -\pi \leq t < 0, \\ \phantom{-}3, & 0 \leq t
< \pi. \end{cases}$$

**a)** Begründen Sie ohne Rechnung, dass $a_0=0$ gilt.

**b)** Begründen Sie mit einem Symmetrieargument, warum alle $a_n=0$
sind.

**c)** Berechnen Sie $b_n=\frac{1}{\pi}\int_{-\pi}^{\pi}
f(t)\sin(nt)\,dt$ vollständig (Integral aufteilen, Stammfunktionen
bestimmen, Grenzen einsetzen, nach geradem/ungeradem $n$ unterscheiden).

**d)** Geben Sie die vollständige Fourierreihe in kompakter Summenform
an.

**e)** Werten Sie die erste Partialsumme $S_1(t)=\frac{12}{\pi}\sin(t)$
bei $t=\pi/2$ aus und vergleichen Sie mit dem exakten Funktionswert
$f(\pi/2)=3$.

**Zusatz (für schnelle Gruppen):** Ergänzen Sie den nächsten
nichtverschwindenden Term ($n=3$) zu $S_3(\pi/2)$ und vergleichen Sie die
Abweichung von $f(\pi/2)=3$ mit der aus e).
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** $f$ ist antisymmetrisch um die Zeitachse und verbringt gleich viel
Zeit bei $+3$ wie bei $-3$, der Mittelwert und damit $a_0$ ist null.

**b)** $f$ ist eine ungerade Funktion, $f(-t)=-f(t)$. Die
Kosinusfunktion ist gerade. Das Produkt aus ungerader und gerader
Funktion ist ungerade, und das Integral einer ungeraden Funktion über
ein symmetrisches Intervall ist stets null, also $a_n=0$ für alle $n$.

**c)**
$$b_n = \frac{1}{\pi}\left(\int_{-\pi}^0 (-3)\sin(nt)\,dt +
\int_0^{\pi} 3\sin(nt)\,dt\right)
= \frac{3}{n\pi}\bigl(1-(-1)^n\bigr) +
\frac{3}{n\pi}\bigl(1-(-1)^n\bigr) = \frac{6}{n\pi}\bigl(1-(-1)^n\bigr)$$
Für gerades $n$ ist $1-(-1)^n=0$, für ungerades $n$ ist $1-(-1)^n=2$,
also
$$b_n = \begin{cases} 0, & n \text{ gerade}, \\[4pt] \dfrac{12}{n\pi}, &
n \text{ ungerade}. \end{cases}$$

**d)** Mit $n=2k-1$:
$$f(t) = \frac{12}{\pi}\sum_{k=1}^{\infty}
\frac{\sin\bigl((2k-1)t\bigr)}{2k-1}$$

**e)** $S_1\!\left(\frac{\pi}{2}\right) = \dfrac{12}{\pi}\sin\!\left(
\dfrac{\pi}{2}\right) = \dfrac{12}{\pi} \approx 3{,}82$. Das ist etwa
$27\,\%$ mehr als der exakte Wert $f(\pi/2)=3$.

**Zusatz:** $$S_3\!\left(\frac{\pi}{2}\right) = \frac{12}{\pi}\sin\!
\left(\frac{\pi}{2}\right) + \frac{12}{3\pi}\sin\!\left(\frac{3\pi}{2}
\right) = \frac{12}{\pi} - \frac{4}{\pi} = \frac{8}{\pi} \approx 2{,}55$$
Die Abweichung von $f(\pi/2)=3$ beträgt jetzt nur noch etwa $15\,\%$,
deutlich weniger als bei $S_1$.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe rechnet c) und d) vollständig an der Tafel, a), b) und e)
werden mündlich ergänzt. Da dies der letzte Block des Kapitels ist,
eignet sich der Zusatz gut als Vorschau auf das Gibbssche Phänomen, das
in Kapitel 14 vertieft wird.
```
