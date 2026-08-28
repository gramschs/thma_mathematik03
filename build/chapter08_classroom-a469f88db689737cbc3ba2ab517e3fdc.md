# Geführte Übung zu Kapitel 8: Separierbare Differentialgleichungen

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Kapitel 8 hat nur drei statt vier
Unterkapitel. Abschnitt 8.3 enthält im Buch bereits zwei voneinander
unabhängige technische Beispiele (Seilreibung und Behälterentleerung), daher
wurden diese auf Block 3 und Block 4 aufgeteilt, damit das 4 Blöcke Format
erhalten bleibt und jedes Anwendungsbeispiel den vollen Block für sich hat.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, Trennung der Variablen (Kap. 8.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Substitution (Kap. 8.2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, Anwendung Seilreibung (Kap. 8.3, Beispiel 1) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, Anwendung Behälterentleerung (Kap. 8.3, Beispiel 2) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Trennung der Variablen

Bezug: Kapitel 8.1, Trennung der Variablen

```{admonition} Aufgabe 1: Aushärten eines Klebstoffs
:class: tip
Bei einer chemischen Reaktion 2. Ordnung nimmt die Konzentration $c(t)$
eines Reaktanten gemäß

$$\dot{c} = -k\,c^2, \quad k = 0{,}5\ \frac{\text{L}}{\text{mol}\cdot
\text{min}}$$

ab. Zu Beginn liegt die Konzentration $c(0) = c_0 = 2\ \dfrac{\text{mol}}{\text{L}}$
vor.

**a)** Zeigen Sie, dass die ODE separierbar ist, indem Sie $f(t)$ und
$g(c)$ angeben.

**b)** Trennen Sie die Variablen (Schritt 1).

**c)** Integrieren Sie beide Seiten und lösen Sie nach $c$ auf, um die
allgemeine Lösung zu erhalten.

**d)** Setzen Sie die Anfangsbedingung $c(0)=2\ \text{mol/L}$ ein und geben
Sie die spezielle Lösung an.

**e)** Bestimmen Sie den Sonderfall $g(c)=0$ und deuten Sie die zugehörige
konstante Lösung physikalisch.

**Zusatz (für schnelle Gruppen):** Verifizieren Sie die spezielle Lösung
aus d) durch Einsetzen in die ursprüngliche ODE.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** $f(t) = 1$ (konstant, hängt nicht von $t$ ab) und $g(c) = -k c^2$.
Die rechte Seite ist ein Produkt eines reinen $t$-Anteils und eines reinen
$c$-Anteils, die ODE ist also separierbar.

**b)** $$\frac{dc}{c^2} = -k\,dt$$

**c)** $$\int c^{-2}\,dc = \int -k\,dt \Rightarrow -\frac{1}{c} = -kt+C_1
\Rightarrow \frac{1}{c} = kt+C \Rightarrow c(t) = \frac{1}{kt+C}$$

**d)** $c(0) = \dfrac{1}{C} = 2 \Rightarrow C = 0{,}5$. Damit
$$c(t) = \frac{1}{0{,}5t+0{,}5} = \frac{2}{t+1}\ \frac{\text{mol}}{\text{L}}.$$

**e)** $g(c)=c^2=0 \Rightarrow c=0$. Die konstante Lösung $c(t)=0$
bedeutet, dass der Reaktant vollständig verbraucht ist und die Reaktion
zum Stillstand kommt.

**Zusatz:** $\dot{c}(t) = -\dfrac{2}{(t+1)^2}$. Rechte Seite: $-k\,c^2 =
-0{,}5\cdot\left(\dfrac{2}{t+1}\right)^2 = -0{,}5\cdot\dfrac{4}{(t+1)^2} =
-\dfrac{2}{(t+1)^2}$. Beide Seiten stimmen überein.
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe bearbeitet b) bis d) vollständig an der Tafel, a) und e)
werden mündlich ergänzt. Coaching Impuls für c): Welche Stammfunktion
gehört zu $c^{-2}$?
```

---

## Block 2 (0:25 bis 0:45) · Substitution

Bezug: Kapitel 8.2, Substitution, wenn die Trennung scheitert

```{admonition} Aufgabe 2: Eine ODE mit Linearkombination
:class: tip
Gegeben sei die Differentialgleichung

$$y' = 2x+2y+1.$$

**a)** Zeigen Sie, dass sich diese ODE nicht direkt trennen lässt, aber
die Form $y' = f(ax+by+c)$ hat. Geben Sie $a$, $b$, $c$ und $f(u)$ an.

**b)** Führen Sie die Substitution $u = x+y$ durch und leiten Sie die
substituierte Gleichung $u' = \ldots$ her.

**c)** Lösen Sie die substituierte ODE durch Trennung der Variablen und
geben Sie die allgemeine Lösung für $u(x)$ an.

**d)** Resubstituieren Sie $u=x+y$ und geben Sie die allgemeine Lösung
$y(x)$ in den ursprünglichen Variablen an.

**e)** Bestimmen Sie den Sonderfall $a+b\cdot f(u)=0$ und geben Sie die
zugehörige singuläre Lösung $y(x)$ an.

**Zusatz (für schnelle Gruppen):** Verifizieren Sie die allgemeine Lösung
aus d) durch Einsetzen in die ursprüngliche ODE $y'=2x+2y+1$.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** Die rechte Seite $2x+2y+1$ lässt sich nicht als Produkt $f(x)\cdot
g(y)$ schreiben, da $x$ und $y$ additiv verknüpft sind. Es gilt jedoch
$y'=f(ax+by+c)$ mit $a=1$, $b=1$, $c=0$ und $f(u)=2u+1$.

**b)** Mit $u=x+y$ gilt $u'=1+y'$, also $y'=u'-1$. Einsetzen:
$$u'-1 = 2u+1 \Rightarrow u' = 2u+2 = 2(u+1)$$

**c)** $$\frac{du}{u+1} = 2\,dx \Rightarrow \ln|u+1| = 2x+C_1
\Rightarrow u+1 = C\,e^{2x} \Rightarrow u(x) = C\,e^{2x}-1$$

**d)** Resubstitution $x+y=Ce^{2x}-1$ liefert
$$y(x) = C\,e^{2x} - x - 1, \quad C\in\mathbb{R}.$$

**e)** $a+b\cdot f(u) = 1+2u+1 = 2u+2 = 0 \Rightarrow u=-1$. Resubstitution
$x+y=-1$ liefert die singuläre Lösung $y(x) = -x-1$.

**Zusatz:** $y'(x) = 2C\,e^{2x}-1$. Rechte Seite: $2x+2y+1 = 2x+2(Ce^{2x}-x-1)+1
= 2Ce^{2x}-1$. Beide Seiten stimmen überein.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet b) bis d) vollständig an der Tafel, a) und e)
werden mündlich ergänzt. Coaching Impuls für b): Wie hängt $u'$ mit $y'$
zusammen, wenn $u=x+y$ gilt?
```

---

## Block 3 (0:50 bis 1:10) · Anwendung: Seilreibung am Poller

Bezug: Kapitel 8.3, Beispiel 1, Seilkraft am Riementrieb

```{admonition} Aufgabe 3: Kraftübersetzung durch Seilreibung
:class: tip
Ein Seil wird um einen Poller mit Reibungskoeffizient $\mu = 0{,}25$
geschlungen. Die Haltekraft auf der Schlupfseite beträgt $F_0 = 150$ N. Die
Euler-Eytelwein-Gleichung lautet

$$\frac{dF}{d\varphi} = \mu\,F.$$

**a)** Lösen Sie diese ODE durch Trennung der Variablen und geben Sie die
allgemeine Lösung $F(\varphi)$ an.

**b)** Setzen Sie die Anfangsbedingung $F(0)=F_0$ ein und geben Sie die
spezielle Lösung an.

**c)** Berechnen Sie die Zugkraft $F$ für einen Umschlingungswinkel von
$\varphi = 270° = \frac{3\pi}{2}$.

**d)** Um welchen Faktor hat sich die Kraft gegenüber $F_0$ erhöht?

**Zusatz (für schnelle Gruppen):** Der Umschlingungswinkel wird auf $540°$
verdoppelt. Bestimmen Sie den neuen Kraftfaktor gegenüber $F_0$, ohne die
Rechnung aus c) komplett zu wiederholen. Nutzen Sie dazu die Struktur der
Exponentialfunktion.
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** $$\frac{dF}{F} = \mu\,d\varphi \Rightarrow \ln|F| = \mu\varphi+C_1
\Rightarrow F(\varphi) = C\,e^{\mu\varphi}$$

**b)** $F(0) = C = F_0$, also
$$F(\varphi) = F_0\,e^{\mu\varphi}.$$

**c)** $F\!\left(\dfrac{3\pi}{2}\right) = 150\cdot e^{0{,}25\cdot
\frac{3\pi}{2}} = 150\cdot e^{1{,}178} \approx 150\cdot 3{,}25 \approx
487\ \text{N}$.

**d)** Die Kraft hat sich um den Faktor $e^{1{,}178}\approx 3{,}25$
erhöht.

**Zusatz:** Da $F(\varphi) = F_0\,e^{\mu\varphi}$ gilt, führt eine
Verdopplung des Winkels zu einer Verdopplung des Exponenten, also zum
Quadrat des ursprünglichen Faktors: $e^{2\cdot 1{,}178} =
\left(e^{1{,}178}\right)^2 \approx 3{,}25^2 \approx 10{,}6$. Der
Kraftfaktor steigt also von rund $3{,}25$ auf rund $10{,}6$.
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe rechnet a) bis c) vollständig an der Tafel, d) wird
mündlich ergänzt. Coaching Impuls für den Zusatz: Was passiert mit
$e^{\mu\varphi}$, wenn Sie $\varphi$ im Exponenten verdoppeln?
```

---

## Block 4 (1:10 bis 1:30) · Anwendung: Entleerung eines Behälters

Bezug: Kapitel 8.3, Beispiel 2, Entleerung eines Hydraulikbehälters

```{admonition} Aufgabe 4: Auslaufzeit eines Tanks
:class: tip
Ein zylindrischer Behälter hat zum Zeitpunkt $t=0$ den Füllstand $h_0 =
1{,}0$ m. Nach dem Torricellischen Ausflussgesetz gilt

$$\dot{h} = -k\sqrt{h}, \quad k = 0{,}04\ \text{m}^{1/2}\text{s}^{-1}.$$

**a)** Trennen Sie die Variablen und integrieren Sie beide Seiten, bis Sie
einen Ausdruck der Form $\sqrt{h(t)} = \ldots$ erhalten (noch ohne
Anfangsbedingung).

**b)** Setzen Sie die Anfangsbedingung $h(0)=h_0=1{,}0$ m ein und geben
Sie die spezielle Lösung $h(t)$ an.

**c)** Berechnen Sie die Entleerungszeit $t_{\text{leer}}$, also den
Zeitpunkt, an dem $h=0$ gilt.

**d)** Berechnen Sie den Füllstand nach $t=20$ s.

**e)** Wäre die Entleerungszeit bei einem linearen Ausflussmodell
$\dot{h}=-k\,h$ endlich oder unendlich? Begründen Sie kurz.

**Zusatz (für schnelle Gruppen):** Verifizieren Sie die spezielle Lösung
aus b) durch Einsetzen in die ursprüngliche ODE.
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** $$\frac{dh}{\sqrt{h}} = -k\,dt \Rightarrow \int h^{-1/2}\,dh =
\int -k\,dt \Rightarrow 2\sqrt{h} = -kt+C_1 \Rightarrow \sqrt{h(t)} =
C_2 - \frac{k}{2}t$$

**b)** $\sqrt{h_0} = \sqrt{1{,}0} = 1 = C_2$, also
$$\sqrt{h(t)} = 1 - 0{,}02\,t \Rightarrow h(t) = (1-0{,}02\,t)^2\ \text{m}.$$

**c)** $1-0{,}02\,t_{\text{leer}} = 0 \Rightarrow t_{\text{leer}} =
\dfrac{1}{0{,}02} = 50\ \text{s}$.

**d)** $h(20) = (1-0{,}02\cdot 20)^2 = (1-0{,}4)^2 = 0{,}6^2 = 0{,}36\
\text{m}$.

**e)** Beim linearen Modell $\dot h=-kh$ nimmt $h$ exponentiell ab und
nähert sich nur asymptotisch der Null, ohne sie in endlicher Zeit exakt zu
erreichen. Die Entleerungszeit wäre also unendlich, im Gegensatz zum
Wurzelmodell, das den Behälter in $50$ s tatsächlich vollständig leert.

**Zusatz:** $\dot{h}(t) = 2(1-0{,}02t)\cdot(-0{,}02) = -0{,}04(1-0{,}02t)$.
Rechte Seite: $-k\sqrt{h(t)} = -0{,}04\sqrt{(1-0{,}02t)^2} =
-0{,}04(1-0{,}02t)$. Beide Seiten stimmen überein.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe rechnet a) bis c) vollständig an der Tafel, d) und e)
werden mündlich ergänzt. Da dies der letzte Block des Kapitels ist, eignet
sich e) gut als Zusammenfassung, warum die Struktur der rechten Seite über
die Lösungsmethode entscheidet, ein guter Übergang zu Kapitel 9.
```
