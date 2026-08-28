# Geführte Übung zu Kapitel 11: Lineare ODEs 2. Ordnung, homogener Fall

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Kapitel 11 hat genau vier
Unterkapitel, daher entspricht Block 1 bis 4 direkt 11.1 bis 11.4. Alle vier
Blöcke verwenden dasselbe Feder-Masse-System ($m=2$ kg, $k=8$ N/m) mit
wachsender Dämpfungskonstante $c$, sodass die Studierenden am Ende des
Kapitels alle drei Fälle (Schwingungsfall, aperiodischer Grenzfall,
Kriechfall) am selben System durchlaufen haben.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, ODE 2. Ordnung und AWP (Kap. 11.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Fundamentalsystem und Wronski-Determinante (Kap. 11.2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, charakteristische Gleichung, reelle Eigenwerte (Kap. 11.3) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, komplexe Eigenwerte, gedämpfte Schwingung (Kap. 11.4) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · ODE 2. Ordnung und Anfangswertproblem

Bezug: Kapitel 11.1, lineare ODE 2. Ordnung

```{admonition} Aufgabe 1: Ungedämpfter Feder-Masse-Schwinger
:class: tip
Eine Sensormasse $m=2$ kg hängt an einer Feder mit Federsteifigkeit
$k=8$ N/m. Dämpfung und äußere Kraft werden zunächst vernachlässigt. Das
Newtonsche Gesetz liefert $m\ddot{x} + kx = 0$.

**a)** Teilen Sie durch $m$ und geben Sie die ODE in der Form $\ddot{x} +
b\,x = 0$ an.

**b)** Ist diese ODE homogen oder inhomogen? Begründen Sie.

**c)** Es wird behauptet, dass $x_h(t) = C_1\cos(2t) + C_2\sin(2t)$ die
ODE aus a) löst. Verifizieren Sie das durch zweimaliges Ableiten und
Einsetzen.

**d)** Die Masse wird um $x(0)=0{,}05$ m ausgelenkt und ohne
Anfangsgeschwindigkeit losgelassen, $\dot{x}(0)=0$. Bestimmen Sie $C_1$
und $C_2$.

**Zusatz (für schnelle Gruppen):** Berechnen Sie die Schwingungsdauer $T$
dieser Bewegung.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** $$\ddot{x} + \frac{k}{m}\,x = 0 \Rightarrow \ddot{x} + 4x = 0$$

**b)** Homogen, da die rechte Seite $g(t)=0$ ist, es wirkt keine äußere
Kraft.

**c)** $\dot{x}_h = -2C_1\sin(2t)+2C_2\cos(2t)$,
$\ddot{x}_h=-4C_1\cos(2t)-4C_2\sin(2t) = -4x_h$. Einsetzen:
$$\ddot{x}_h+4x_h = -4x_h+4x_h = 0. \quad \checkmark$$

**d)** $x_h(0)=C_1=0{,}05$. $\dot{x}_h(0)=2C_2=0 \Rightarrow C_2=0$. Die
spezielle Lösung lautet
$$x(t) = 0{,}05\cos(2t)\ \text{m}.$$

**Zusatz:** $T = \dfrac{2\pi}{\omega_0} = \dfrac{2\pi}{2} = \pi \approx
3{,}14\ \text{s}$.
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe bearbeitet a), c) und d) vollständig an der Tafel, b) wird
mündlich ergänzt. Coaching Impuls für d): Welche der beiden
Anfangsbedingungen bestimmt $C_1$, welche $C_2$?
```

---

## Block 2 (0:25 bis 0:45) · Fundamentalsystem und Wronski-Determinante

Bezug: Kapitel 11.2, wann spannen zwei Lösungen den Lösungsraum auf?

```{admonition} Aufgabe 2: Bildet das Paar ein Fundamentalsystem?
:class: tip
Wir bleiben beim Feder-Masse-System aus Block 1, $\ddot{x}+4x=0$.

**a)** Prüfen Sie mit der Wronski-Determinante, ob das Paar
$\{\cos(2t),\,4\cos(2t)\}$ linear unabhängig ist.

**b)** Prüfen Sie mit der Wronski-Determinante, ob das Paar
$\{\cos(2t),\,\sin(2t)\}$ linear unabhängig ist, und geben Sie die
allgemeine Lösung $x_h(t)$ an.

**c)** Erklären Sie in ein bis zwei Sätzen, warum das Anfangswertproblem
aus Block 1 mit dem Paar aus a) nicht für jede beliebige
Anfangsbedingung $\dot{x}(0)\neq 0$ lösbar wäre.

**Zusatz (für schnelle Gruppen):** Prüfen Sie mit der Wronski-Determinante,
ob auch das Paar $\{\cos(2t)+\sin(2t),\,\cos(2t)-\sin(2t)\}$ ein
Fundamentalsystem bildet.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** Mit $y_1=\cos(2t)$, $y_1'=-2\sin(2t)$, $y_2=4\cos(2t)$,
$y_2'=-8\sin(2t)$:
$$W = \cos(2t)\cdot(-8\sin(2t)) - 4\cos(2t)\cdot(-2\sin(2t)) =
-8\cos\sin+8\cos\sin = 0.$$
Die Wronski-Determinante ist identisch null, das Paar ist linear abhängig
(da $4\cos(2t)$ ein Vielfaches von $\cos(2t)$ ist).

**b)** Mit $y_1'=-2\sin(2t)$, $y_2'=2\cos(2t)$:
$$W = \cos(2t)\cdot 2\cos(2t) - \sin(2t)\cdot(-2\sin(2t)) =
2\cos^2(2t)+2\sin^2(2t) = 2 \neq 0.$$
Das Paar ist linear unabhängig und bildet ein Fundamentalsystem. Die
allgemeine Lösung lautet $x_h(t)=C_1\cos(2t)+C_2\sin(2t)$.

**c)** Mit dem Paar aus a) hätte jede Linearkombination
$C_1\cos(2t)+C_2\cdot 4\cos(2t) = (C_1+4C_2)\cos(2t)$ bei $t=0$ stets die
Ableitung null. Eine Anfangsbedingung $\dot{x}(0)\neq 0$ ließe sich damit
niemals erfüllen, das Paar deckt nicht den gesamten Lösungsraum ab.

**Zusatz:** Mit $y_1=\cos(2t)+\sin(2t)$, $y_1'=2\cos(2t)-2\sin(2t)$,
$y_2=\cos(2t)-\sin(2t)$, $y_2'=-2\sin(2t)-2\cos(2t)$:
$$W = y_1 y_2' - y_2 y_1' = -2(\cos(2t)+\sin(2t))^2 -
2(\cos(2t)-\sin(2t))^2 = -2\cdot 2 = -4 \neq 0.$$
Auch dieses Paar ist linear unabhängig und bildet ein Fundamentalsystem.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet a) und b) vollständig an der Tafel, c) wird
mündlich ergänzt. Coaching Impuls für a): Was fällt Ihnen auf, wenn Sie
$y_2$ als Vielfaches von $y_1$ erkennen, noch bevor Sie rechnen?
```

---

## Block 3 (0:50 bis 1:10) · Charakteristische Gleichung, reelle Eigenwerte

Bezug: Kapitel 11.3, die charakteristische Gleichung, der Fall reeller Eigenwerte

```{admonition} Aufgabe 3: Gedämpfter Schwinger, Kriechfall
:class: tip
Das Feder-Masse-System aus Block 1 und 2 erhält jetzt einen Dämpfer mit
$c=10$ Ns/m. Die Bewegungsgleichung lautet $m\ddot{x}+c\dot{x}+kx=0$ mit
$m=2$ kg und $k=8$ N/m.

**a)** Teilen Sie durch $m$, stellen Sie die charakteristische Gleichung
$\lambda^2+a\lambda+b=0$ auf und berechnen Sie die Diskriminante $D$.

**b)** Bestimmen Sie die beiden Eigenwerte $\lambda_1$ und $\lambda_2$.

**c)** Geben Sie die allgemeine Lösung $x_h(t)$ an.

**d)** Bestimmen Sie mit $x(0)=0{,}05$ m und $\dot{x}(0)=0$ die spezielle
Lösung.

**Zusatz (für schnelle Gruppen):** Bestimmen Sie die kritische
Dämpfungskonstante $c_{\text{krit}}$, für die $D=0$ gilt (aperiodischer
Grenzfall), und geben Sie den zugehörigen doppelten Eigenwert an.
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** $a=\dfrac{c}{m}=5$, $b=\dfrac{k}{m}=4$. Charakteristische Gleichung:
$\lambda^2+5\lambda+4=0$. $D = \dfrac{a^2}{4}-b = \dfrac{25}{4}-4 =
2{,}25 > 0$.

**b)** $\lambda_{1,2} = -2{,}5\pm\sqrt{2{,}25} = -2{,}5\pm 1{,}5$, also
$\lambda_1=-1$ und $\lambda_2=-4$.

**c)** $$x_h(t) = C_1\,e^{-t} + C_2\,e^{-4t}$$

**d)** $C_1+C_2=0{,}05$ und $-C_1-4C_2=0 \Rightarrow C_1=-4C_2$. Einsetzen:
$-4C_2+C_2=-3C_2=0{,}05 \Rightarrow C_2=-\dfrac{1}{60}$,
$C_1=\dfrac{1}{15}$. Die spezielle Lösung lautet
$$x(t) = \frac{1}{15}e^{-t} - \frac{1}{60}e^{-4t}\ \text{m}.$$
Der Wagen kehrt ohne Schwingung in die Ruhelage zurück (Kriechfall).

**Zusatz:** $D=0 \Rightarrow \dfrac{a^2}{4}=b=4 \Rightarrow a=4$, also
$c_{\text{krit}}=a\cdot m = 4\cdot 2 = 8$ Ns/m. Der doppelte Eigenwert ist
$\lambda=-\dfrac{a}{2}=-2$.
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe rechnet a) bis c) vollständig an der Tafel, d) wird
ebenfalls an der Tafel gelöst. Coaching Impuls für b): Welches Vorzeichen
müssen beide Eigenwerte haben, damit die Schwingung überhaupt abklingt?
```

---

## Block 4 (1:10 bis 1:30) · Komplexe Eigenwerte, gedämpfte Schwingung

Bezug: Kapitel 11.4, komplexe Eigenwerte und das Modell der gedämpften Schwingung

```{admonition} Aufgabe 4: Schwach gedämpfter Schwinger
:class: tip
Dasselbe Feder-Masse-System erhält jetzt einen deutlich schwächeren
Dämpfer mit $c=2$ Ns/m ($m=2$ kg, $k=8$ N/m).

**a)** Zeigen Sie, dass für diese Dämpfung $D<0$ gilt (Schwingungsfall).

**b)** Bestimmen Sie die Abklingrate $\alpha$ und die gedämpfte
Kreisfrequenz $\omega_d$.

**c)** Geben Sie das reelle Fundamentalsystem und die allgemeine Lösung
$x_h(t)$ an.

**d)** Bestimmen Sie mit $x(0)=0{,}05$ m und $\dot{x}(0)=0$ die spezielle
Lösung.

**e)** Vergleichen Sie $\omega_d$ mit der ungedämpften Eigenkreisfrequenz
$\omega_0=2$ rad/s aus Block 1. Was fällt auf?

**Zusatz (für schnelle Gruppen):** Ordnen Sie die drei in diesem Kapitel
untersuchten Dämpfungskonstanten $c=2$ Ns/m (dieser Block), $c=8$ Ns/m
(Block 3, Zusatz) und $c=10$ Ns/m (Block 3) der Größe nach und geben Sie
jeweils an, welcher der drei Fälle (Schwingungsfall, aperiodischer
Grenzfall, Kriechfall) vorliegt.
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** $a=\dfrac{c}{m}=1$, $b=4$. $D=\dfrac{a^2}{4}-b = 0{,}25-4 = -3{,}75
< 0$, also liegt der Schwingungsfall vor.

**b)** $\alpha = \dfrac{a}{2} = 0{,}5\ \text{s}^{-1}$, $\omega_d =
\sqrt{b-\frac{a^2}{4}} = \sqrt{3{,}75} \approx 1{,}94\ \text{rad/s}$.

**c)** Fundamentalsystem $\{e^{-0{,}5t}\cos(1{,}94t),\,
e^{-0{,}5t}\sin(1{,}94t)\}$. Allgemeine Lösung:
$$x_h(t) = e^{-0{,}5t}\bigl(C_1\cos(1{,}94t)+C_2\sin(1{,}94t)\bigr)$$

**d)** $x_h(0)=C_1=0{,}05$. $\dot{x}_h(0) = -\alpha C_1+\omega_d C_2 = 0
\Rightarrow C_2 = \dfrac{\alpha C_1}{\omega_d} = \dfrac{0{,}5\cdot
0{,}05}{1{,}94} \approx 0{,}0129$. Die spezielle Lösung lautet
$$x(t) \approx e^{-0{,}5t}\bigl(0{,}05\cos(1{,}94t) +
0{,}0129\sin(1{,}94t)\bigr)\ \text{m}.$$

**e)** $\omega_d\approx 1{,}94\ \text{rad/s}$ ist kleiner als
$\omega_0=2\ \text{rad/s}$. Die Dämpfung verlangsamt die Schwingung
gegenüber dem ungedämpften Fall.

**Zusatz:** Der Größe nach: $c=2$ Ns/m (Schwingungsfall, $D<0$), $c=8$
Ns/m (aperiodischer Grenzfall, $D=0$), $c=10$ Ns/m (Kriechfall, $D>0$).
Mit wachsender Dämpfung durchläuft das System also genau die drei Fälle
in dieser Reihenfolge.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe bearbeitet a) bis d) vollständig an der Tafel, e) wird
mündlich ergänzt. Da dies der letzte Block des Kapitels ist, eignet sich
der Zusatz gut als Zusammenfassung des gesamten Kapitels und als Ausblick
auf die erzwungene Schwingung und Resonanz in Kapitel 12.
```
