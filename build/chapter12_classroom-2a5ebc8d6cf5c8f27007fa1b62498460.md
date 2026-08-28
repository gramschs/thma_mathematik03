# Geführte Übung zu Kapitel 12: Erzwungene Schwingungen und Resonanz

Format: 4 Blöcke à 20 Minuten plus 10 Minuten Puffer. Pro Block rechnet eine
Tafelgruppe vorne mit, die übrigen Studierenden allein oder zu zweit an den
Plätzen. Am Ende der Sitzung war jede Person einmal an der Tafel.

```{admonition} Hinweise für die Lehrperson
:class: tip
Jeder Block besteht aus einer kurzen Aufgabenstellung, etwa 13 Minuten
Arbeitszeit inklusive Coaching der Tafelgruppe und etwa 6 Minuten gemeinsamer
Besprechung. Coaching Prinzip: Fragen statt Ansagen, die Kreide bleibt bei
den Studierenden. Musterlösungen sind zum Aufklappen eingeklappt und sollten
erst nach der Arbeitsphase geöffnet werden. Kapitel 12 hat genau vier
Unterkapitel, daher entspricht Block 1 bis 4 direkt 12.1 bis 12.4. Block 1
und 2 verwenden dasselbe Feder-Masse-Dämpfer-System wie Block 3 aus
Kapitel 11 ($m=2$ kg, $k=8$ N/m, $d=10$ Ns/m, Eigenwerte $-1$ und $-4$).
Block 3 und 4 verwenden den ungedämpften Fall desselben Systems ($d=0$,
$\omega_0=2$ rad/s), der bereits in Block 1 aus Kapitel 11 vorkam.
```

## Ablaufplan

| Zeit | Phase | Inhalt |
|---|---|---|
| 0:00 bis 0:05 | Organisation | Begrüßung, Tafelgruppe für Block 1 erinnern |
| 0:05 bis 0:25 | Block 1 | Aufgabe 1, Ansatz vom Typ der rechten Seite (Kap. 12.1) |
| 0:25 bis 0:45 | Block 2 | Aufgabe 2, Resonanzfall und AWP (Kap. 12.2) |
| 0:45 bis 0:50 | Pause | kurze Verschnaufpause |
| 0:50 bis 1:10 | Block 3 | Aufgabe 3, Bewegungsgleichung und Schwingungsgleichung (Kap. 12.3) |
| 1:10 bis 1:30 | Block 4 | Aufgabe 4, erzwungene Schwingung und Resonanz (Kap. 12.4) |

## Tafelgruppen Zuordnung (vorab ausfüllen)

| Block | Gruppe | Namen |
|---|---|---|
| 1 | A | |
| 2 | B | |
| 3 | C | |
| 4 | D | |

---

## Block 1 (0:05 bis 0:25) · Ansatz vom Typ der rechten Seite

Bezug: Kapitel 12.1, die partikuläre Lösung, Ansatz vom Typ der rechten Seite

```{admonition} Aufgabe 1: Stoßkraft ohne Resonanz
:class: tip
Das Feder-Masse-Dämpfer-System aus Kapitel 11, Block 3 ($m=2$ kg, $k=8$
N/m, $d=10$ Ns/m, homogene Lösung $y_h=C_1e^{-t}+C_2e^{-4t}$) wird jetzt
durch einen Stoß mit $F(t) = 12\,e^{-2t}$ N belastet.

**a)** Stellen Sie mit $g(t)=F(t)/m$ die inhomogene ODE
$y''+5y'+4y=g(t)$ in Zahlen auf.

**b)** Prüfen Sie, ob der Exponent von $g(t)$ mit einem der Eigenwerte
$\lambda_1=-1$ oder $\lambda_2=-4$ übereinstimmt. Liegt Resonanz vor?

**c)** Bestimmen Sie mit dem Ansatz $y_p=A\,e^{-2t}$ die partikuläre
Lösung.

**d)** Geben Sie die allgemeine Lösung $y_{\text{allgemein}}(t)$ an.

**Zusatz (für schnelle Gruppen):** Verifizieren Sie $y_p$ durch Einsetzen
in die ODE.
```

```{admonition} Musterlösung Aufgabe 1
:class: tip
:class: dropdown
**a)** $g(t) = \dfrac{12\,e^{-2t}}{2} = 6\,e^{-2t}$, also
$$y''+5y'+4y = 6\,e^{-2t}.$$

**b)** Der Exponent ist $-2$. Da $-2\neq -1$ und $-2\neq -4$, liegt
**keine** Resonanz vor.

**c)** $y_p'=-2Ae^{-2t}$, $y_p''=4Ae^{-2t}$. Einsetzen:
$$4A-10A+4A = -2A \stackrel{!}{=} 6 \Rightarrow A=-3$$
Also $y_p(t) = -3\,e^{-2t}$.

**d)** $$y_{\text{allgemein}}(t) = C_1\,e^{-t}+C_2\,e^{-4t} - 3\,e^{-2t}$$

**Zusatz:** Mit $A=-3$: $y_p''=-12e^{-2t}$, $5y_p'=30e^{-2t}$,
$4y_p=-12e^{-2t}$. Summe: $-12+30-12=6$, also $6e^{-2t}$. $\checkmark$
```

```{admonition} Tafel Hinweis Block 1
:class: note
Die Tafelgruppe rechnet a) bis c) vollständig an der Tafel, d) wird
mündlich ergänzt. Coaching Impuls für b): Was würde beim Einsetzen
passieren, wenn der Exponent zufällig mit einem Eigenwert übereinstimmen
würde?
```

---

## Block 2 (0:25 bis 0:45) · Resonanzfall und Anfangswertproblem

Bezug: Kapitel 12.2, der Resonanzfall und das Anfangswertproblem

```{admonition} Aufgabe 2: Wenn die Stoßkraft im Takt des Systems wirkt
:class: tip
Dasselbe System wird jetzt durch $F(t) = 12\,e^{-t}$ N belastet.

**a)** Zeigen Sie, dass der Exponent von $g(t)=F(t)/m$ mit dem Eigenwert
$\lambda_1=-1$ übereinstimmt, also Resonanz vorliegt.

**b)** Zeigen Sie durch Einsetzen, dass der Standardansatz $y_p=A\,e^{-t}$
versagt.

**c)** Bestimmen Sie mit dem modifizierten Ansatz $y_p=A\,t\,e^{-t}$ die
partikuläre Lösung.

**d)** Geben Sie die allgemeine Lösung $y_{\text{allgemein}}(t)$ an.

**e)** Das System startet in Ruhe, $y(0)=0$ und $y'(0)=0$. Bestimmen Sie
die spezielle Lösung.

**Zusatz (für schnelle Gruppen):** Der Term $2t\,e^{-t}$ in der Lösung
wächst zunächst an, bevor er gegen null geht. Bestimmen Sie den Zeitpunkt
des Maximums.
```

```{admonition} Musterlösung Aufgabe 2
:class: tip
:class: dropdown
**a)** $g(t)=6e^{-t}$, Exponent $-1=\lambda_1$. Resonanz liegt vor.

**b)** Mit $y_p=Ae^{-t}$: $y_p'=-Ae^{-t}$, $y_p''=Ae^{-t}$. Einsetzen:
$A-5A+4A=0 \neq 6e^{-t}$ für jedes $A$. Der Ansatz versagt.

**c)** $y_p'=A(1-t)e^{-t}$, $y_p''=A(t-2)e^{-t}$. Einsetzen:
$$A(t-2)+5A(1-t)+4At = A[(t-2)+5(1-t)+4t] = 3A \stackrel{!}{=} 6
\Rightarrow A=2$$
Also $y_p(t) = 2t\,e^{-t}$.

**d)** $$y_{\text{allgemein}}(t) = C_1e^{-t}+C_2e^{-4t}+2t\,e^{-t}$$

**e)** $y(0)=C_1+C_2=0$. $y'(t)=-C_1e^{-t}-4C_2e^{-4t}+2(1-t)e^{-t}$,
$y'(0)=-C_1-4C_2+2=0 \Rightarrow C_1+4C_2=2$. Aus $C_1=-C_2$ folgt
$3C_2=2 \Rightarrow C_2=\tfrac{2}{3}$, $C_1=-\tfrac{2}{3}$. Die spezielle
Lösung lautet
$$y(t) = -\frac{2}{3}e^{-t}+\frac{2}{3}e^{-4t}+2t\,e^{-t}.$$

**Zusatz:** $\dfrac{d}{dt}[t\,e^{-t}] = e^{-t}(1-t) = 0 \Rightarrow t=1$.
Das Maximum liegt bei $t=1$ s.
```

```{admonition} Tafel Hinweis Block 2
:class: note
Die Tafelgruppe rechnet c) bis e) vollständig an der Tafel, a) und b)
werden mündlich ergänzt. Coaching Impuls für c): Welcher Term hebt sich
beim Einsetzen dank der charakteristischen Gleichung stets auf?
```

---

## Block 3 (0:50 bis 1:10) · Bewegungsgleichung und Schwingungsgleichung

Bezug: Kapitel 12.3, Schwingungen und Bewegungsgleichungen

```{admonition} Aufgabe 3: Vom Newtonschen Gesetz zur Schwingungsgleichung
:class: tip
Ein Maschinenelement der Masse $m=2$ kg ist über eine Feder mit $k=8$ N/m
am Gestell befestigt, ohne Dämpfung und ohne äußere Kraft.

**a)** Nennen Sie die Federkraft und stellen Sie mit dem Newtonschen
Gesetz $m\,y''=F_{\text{ges}}$ die Bewegungsgleichung $y''+\omega_0^2 y=0$
auf.

**b)** Berechnen Sie die Eigenkreisfrequenz $\omega_0=\sqrt{k/m}$.

**c)** Geben Sie die allgemeine Lösung $y(t)=C_1\cos(\omega_0 t)+
C_2\sin(\omega_0 t)$ an und berechnen Sie die Schwingungsdauer $T$.

**d)** Das Element wird um $y_0=8$ mm ausgelenkt und ohne
Anfangsgeschwindigkeit losgelassen. Bestimmen Sie die spezielle Lösung.

**e)** Geben Sie Amplitude $\hat{y}$ und Phase $\varphi$ dieser Lösung in
der Amplituden-Phasen-Form an.

**Zusatz (für schnelle Gruppen):** Ein Fadenpendel hat die
Bewegungsgleichung $\varphi''+(g/L)\varphi=0$. Welche Pendellänge $L$
liefert näherungsweise dieselbe Eigenkreisfrequenz $\omega_0=2$ rad/s wie
unser Feder-Masse-System (mit $g=9{,}81$ m/s²)?
```

```{admonition} Musterlösung Aufgabe 3
:class: tip
:class: dropdown
**a)** Federkraft $F_F=-k\,y$. Mit $m\,y''=-k\,y$ und Division durch $m$:
$$y''+\frac{k}{m}\,y=0 \Rightarrow y''+\omega_0^2\,y=0$$

**b)** $\omega_0=\sqrt{8/2}=\sqrt{4}=2\ \text{rad/s}$.

**c)** $$y(t)=C_1\cos(2t)+C_2\sin(2t)$$
$T=\dfrac{2\pi}{\omega_0}=\dfrac{2\pi}{2}=\pi\approx 3{,}14$ s.

**d)** $y(0)=C_1=0{,}008 \Rightarrow C_1=0{,}008$. $y'(0)=2C_2=0
\Rightarrow C_2=0$. Die spezielle Lösung lautet
$$y(t) = 0{,}008\,\cos(2t)\ \text{m}.$$

**e)** $\hat{y}=\sqrt{C_1^2+C_2^2}=0{,}008$ m, $\varphi=0$, da
$\tan\varphi=C_2/C_1=0$.

**Zusatz:** Aus $\omega_0=\sqrt{g/L}=2$ folgt $L=g/\omega_0^2 =
9{,}81/4 \approx 2{,}45$ m.
```

```{admonition} Tafel Hinweis Block 3
:class: note
Die Tafelgruppe bearbeitet a) bis d) vollständig an der Tafel, e) wird
mündlich ergänzt. Coaching Impuls für b): Welche zwei Systemgrößen
bestimmen $\omega_0$, und welche Größe beeinflusst sie nicht?
```

---

## Block 4 (1:10 bis 1:30) · Erzwungene Schwingung und Resonanz

Bezug: Kapitel 12.4, erzwungene Schwingungen und Resonanz

```{admonition} Aufgabe 4: Unwucht und kritische Drehzahl
:class: tip
Das ungedämpfte System aus Block 3 ($m=2$ kg, $\omega_0=2$ rad/s) wird
durch eine Unwuchtkraft $F(t)=F_0\sin(\Omega t)$ mit $F_0=8$ N angeregt.
Die ODE lautet $y''+4y = 4\sin(\Omega t)$.

**a)** Bestimmen Sie für $\Omega=1$ rad/s (also $\Omega\neq\omega_0$) mit
dem Ansatz $y_p=A\sin(\Omega t)$ die partikuläre Lösung.

**b)** Werten Sie die Resonanzamplituden-Formel $\hat{y}_p =
\frac{F_0/m}{|\omega_0^2-\Omega^2|}$ für $\Omega=1$ aus und vergleichen
Sie mit a).

Die Drehzahl wird jetzt auf $\Omega=\omega_0=2$ rad/s erhöht.

**c)** Erklären Sie kurz, warum der Standardansatz
$y_p=A\sin(2t)+B\cos(2t)$ hier versagt.

**d)** Bestimmen Sie mit dem modifizierten Ansatz $y_p=At\sin(2t)+
Bt\cos(2t)$ die partikuläre Lösung im Resonanzfall.

**e)** Bestimmen Sie mit $y(0)=0$ und $y'(0)=0$ die vollständige Lösung
im Resonanzfall.

**Zusatz (für schnelle Gruppen):** Berechnen Sie die Amplitude des
unbegrenzt wachsenden Terms bei $t=20$ s und bewerten Sie, ob ein solcher
Ausschlag für ein reales Maschinenelement realistisch wäre.
```

```{admonition} Musterlösung Aufgabe 4
:class: tip
:class: dropdown
**a)** Mit $y_p=A\sin(t)+B\cos(t)$ liefert der Koeffizientenvergleich
$B=0$ und $(4-1)A=4 \Rightarrow A=\tfrac{4}{3}$. Also
$$y_p(t) = \frac{4}{3}\sin(t).$$

**b)** $\hat{y}_p = \dfrac{4}{|4-1|} = \dfrac{4}{3}$, identisch mit dem
Ergebnis aus a).

**c)** $\sin(2t)$ und $\cos(2t)$ sind bereits Lösungen der homogenen ODE
$y''+4y=0$ (da $\omega_0=2$). Der Ansatz ergäbe beim Einsetzen $0$ auf der
linken Seite, was nicht mit $4\sin(2t)$ übereinstimmen kann.

**d)** Einsetzen des modifizierten Ansatzes liefert allgemein
$y_p''+4y_p = 2\cdot 2\cdot A\cos(2t) - 2\cdot 2\cdot B\sin(2t)$.
Koeffizientenvergleich mit $4\sin(2t)$: $4A=0 \Rightarrow A=0$ und
$-4B=4 \Rightarrow B=-1$. Also
$$y_p(t) = -t\cos(2t).$$

**e)** Mit $y=C_1\cos(2t)+C_2\sin(2t)-t\cos(2t)$: $y(0)=C_1=0$.
$y'(t)=-2C_1\sin(2t)+2C_2\cos(2t)-\cos(2t)+2t\sin(2t)$, also
$y'(0)=2C_2-1=0 \Rightarrow C_2=0{,}5$. Die vollständige Lösung lautet
$$y(t) = 0{,}5\sin(2t) - t\cos(2t)\ \text{m}.$$
Der Term $-t\cos(2t)$ wächst unbegrenzt mit $t$: das ist die
Resonanzkatastrophe.

**Zusatz:** Die Hüllkurve des wachsenden Terms ist $|t|$, bei $t=20$ s
also $20$ m. Ein Ausschlag dieser Größenordnung ist für ein reales
Maschinenelement völlig unrealistisch, das Bauteil würde lange vorher
versagen.
```

```{admonition} Tafel Hinweis Block 4
:class: note
Die Tafelgruppe bearbeitet a), d) und e) vollständig an der Tafel, b) und
c) werden mündlich ergänzt. Da dies der letzte Block des Kapitels ist,
eignet sich der Zusatz gut als Abschlussdiskussion über die praktische
Bedeutung der kritischen Drehzahl im Maschinenbau.
```
