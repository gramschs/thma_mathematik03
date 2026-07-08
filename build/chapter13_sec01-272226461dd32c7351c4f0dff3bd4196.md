---
authors:
  - name: Simone Gramsch
---

# 13.1 Periodische Funktionen und periodische Fortsetzung

In Abschnitt 11.4 haben wir gesehen, dass eine rotierende Unwucht eine
periodische Kraft erzeugt und das System bei Resonanz zum Verhängnis werden
kann. Dort haben wir diese Kraft einfach als $F(t) = F_0\,\sin(\Omega t)$
angesetzt. Jetzt treten wir einen Schritt zurück und fragen: *Was macht eine
Funktion überhaupt periodisch, und wie beschreiben wir solche Funktionen
präzise?* Als Leitbeispiel dient uns eine Kurbelwelle, die mit
$n = 1500~\text{min}^{-1}$ dreht und dabei eine periodische Kraft auf ein
Pleuellager ausübt. Dieses Szenario begleitet uns durch den gesamten Abschnitt.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können erklären, was eine **periodische Funktion** ist, und die
  definierende Eigenschaft $f(t + T) = f(t)$ anwenden.
* [ ] Sie kennen die Begriffe **Periode** $T$, **Kreisfrequenz**
  $\omega_0 = 2\pi/T$ und **Amplitude** und können alle drei Größen aus
  einer gegebenen Schwingung ablesen oder berechnen.
* [ ] Sie können eine auf einem Intervall definierte Funktion **periodisch
  fortsetzen** und den Funktionswert an einer beliebigen Stelle der
  Fortsetzung ablesen.
```

## Was macht eine Funktion periodisch?

Wir beobachten die Kurbelwelle: Nach jeder vollständigen Umdrehung befindet
sich der Kolben wieder in derselben Position, die Kraft auf das Lager hat
wieder denselben Wert. Was auch immer in einer Umdrehung passiert, es
wiederholt sich in der nächsten exakt genauso. Dieses Muster kennen wir aus
dem Alltag: Der Stundenzeiger einer Uhr zeigt nach zwölf Stunden wieder auf
dieselbe Position, eine Melodie kehrt nach einer bestimmten Anzahl von Takten
zum Anfang zurück.

Das entscheidende Merkmal ist der feste Abstand, nach dem sich die
Funktionswerte wiederholen. Wir nennen diesen Abstand die **Periode** und
bezeichnen sie mit $T$.

```{admonition} Was ist ... eine periodische Funktion?
:class: note
Eine Funktion $f$ heißt **periodisch** mit der **Periode** $T > 0$, wenn für
alle $t$ gilt:

\begin{equation*}
f(t + T) = f(t).
\end{equation*}

Der kleinste solche Wert $T$ heißt **Grundperiode** oder einfach die Periode
von $f$.
```

Wenden wir das auf die Kurbelwelle an. Die Drehzahl $n = 1500~\text{min}^{-1}$
bedeutet, dass die Welle in einer Minute $1500$ vollständige Umdrehungen
ausführt. Die Zeit für eine einzige Umdrehung ist damit

\begin{equation*}
T = \frac{1}{n} = \frac{1}{1500~\text{min}^{-1}} = \frac{1}{25~\text{s}^{-1}}
= 0.04~\text{s} = 40~\text{ms}.
\end{equation*}

Die Kraft auf das Lager hat also die Periode $T = 40~\text{ms}$. Das heißt
konkret: Wenn wir den Kraftverlauf bei $t = 0$ kennen, dann ist der Kraftwert
bei $t = 40~\text{ms}$ identisch, bei $t = 80~\text{ms}$ wieder identisch, und
so weiter. Wir prüfen die Definitionsbedingung: $f(t + 0.04~\text{s}) = f(t)$
für alle $t$. Jede Kurve, die den Kolbenhub korrekt modelliert, muss diese
Gleichung erfüllen.

## Wie liest man Kreisfrequenz und Amplitude ab?

Die Periode $T$ ist eine natürliche Kenngröße, wenn wir an der Zeit denken.
In der Schwingungslehre und der Regelungstechnik arbeitet man jedoch häufig
lieber mit der **Kreisfrequenz** $\omega_0$, weil sie direkt in den Argumenten
von Sinus- und Kosinusfunktionen auftaucht. Wir erinnern uns an Kapitel 11:
Dort erschien $\omega_0 = \sqrt{k/m}$ als Eigenfrequenz des Feder-Masse-Systems.
*Wie hängt diese Größe mit der Periode zusammen?*

Eine Sinusfunktion der Form $\sin(\omega_0 t)$ durchläuft genau dann einen
vollständigen Schwingungszyklus, wenn das Argument $\omega_0 t$ den Wert $2\pi$
erreicht. Das geschieht zum Zeitpunkt $t = T$, also wenn $\omega_0 \cdot T =
2\pi$ gilt. Auflösen nach $\omega_0$ liefert die Formel.

```{admonition} Was sind ... Kreisfrequenz und Amplitude?
:class: note
Für eine periodische Schwingung mit Periode $T$ ist die **Kreisfrequenz**

\begin{equation*}
\omega_0 = \frac{2\pi}{T}.
\end{equation*}

Die **Amplitude** $\hat{f}$ ist der maximale Betrag, den die Funktion annimmt:

\begin{equation*}
\hat{f} = \max_{t} |f(t)|.
\end{equation*}

Die Einheit der Kreisfrequenz ist $\text{rad}\,\text{s}^{-1}$, also Radiant
pro Sekunde.
```

Für unsere Kurbelwelle mit $T = 40~\text{ms} = 0.04~\text{s}$ ergibt sich

\begin{equation*}
\omega_0 = \frac{2\pi}{0.04~\text{s}} = 50\pi~\text{rad\,s}^{-1}
\approx 157.1~\text{rad\,s}^{-1}.
\end{equation*}

Modellieren wir den Kolbenhub vereinfacht als $f(t) = 3\,\sin(\omega_0 t)$ mit
der Hubhöhe in Zentimetern, dann beträgt die Amplitude $\hat{f} = 3~\text{cm}$.
Der maximale Ausschlag des Kolbens aus der Mittellage beträgt also $3~\text{cm}$
nach oben und $3~\text{cm}$ nach unten.

Zur Kontrolle setzen wir $\omega_0 = 50\pi~\text{rad\,s}^{-1}$ und $T =
0.04~\text{s}$ in die Definitionsbedingung ein:

\begin{equation*}
f(t + T) = 3\,\sin\!\bigl(50\pi\,(t + 0.04)\bigr)
= 3\,\sin(50\pi\,t + 2\pi)
= 3\,\sin(50\pi\,t)
= f(t). \quad \checkmark
\end{equation*}

Der Term $2\pi$ im Argument verschiebt die Sinusfunktion um genau einen vollen
Umlauf, der Funktionswert bleibt unverändert.

```{figure} pics/chap12_sec01_fig01.svg
---
name: chap12_sec01_fig01
---
Kolbenhub $f(t) = 3\,\sin(50\pi\,t)$ über zwei Perioden. Die Periode
$T = 40~\text{ms}$ und die Amplitude $\hat{f} = 3~\text{cm}$ sind
eingezeichnet.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

## Wie setzt man eine Funktion periodisch fort?

In der Messtechnik und der Signalverarbeitung nehmen wir ein Signal oft nur
über ein einziges Zeitfenster auf, beispielsweise genau eine Umdrehung der
Kurbelwelle, also das Intervall $[0,\, T]$. Das Messgerät liefert uns eine
Funktion $g$, die nur auf diesem Intervall definiert ist. *Was tun wir, wenn
wir den Signalwert zu einem Zeitpunkt außerhalb des Messfensters benötigen?*

Die Antwort liegt auf der Hand: Wir verlängern die Funktion, indem wir das
Muster aus $[0, T]$ immer wieder nach rechts und nach links aneinanderhängen.
Das nennt man die **periodische Fortsetzung** von $g$.

```{admonition} Was ist ... die periodische Fortsetzung?
:class: note
Sei $g$ eine Funktion, die auf dem Intervall $[0, T)$ definiert ist. Die
**periodische Fortsetzung** von $g$ mit der Periode $T$ ist die Funktion
$\tilde{g}$, die für jedes $t \in \mathbb{R}$ durch

\begin{equation*}
\tilde{g}(t) = g(t - k \cdot T)
\end{equation*}

definiert wird, wobei $k \in \mathbb{Z}$ die eindeutig bestimmte ganze Zahl
ist, für die $t - k \cdot T \in [0, T)$ gilt.
```

Die Berechnung des richtigen $k$ funktioniert so: Wir suchen dasjenige
ganzzahlige Vielfache von $T$, das wir von $t$ subtrahieren müssen, damit das
Ergebnis im Grundintervall $[0, T)$ landet. Das entspricht der ganzzahligen
Division von $t$ durch $T$, also

\begin{equation*}
k = \left\lfloor \frac{t}{T} \right\rfloor,
\end{equation*}

wobei $\lfloor \cdot \rfloor$ die Abrundungsfunktion bezeichnet.

Konkret: Angenommen, die Messkurve des Kolbenhubs ist auf $[0, 40~\text{ms})$
durch

\begin{equation*}
g(t) = 3\,\sin\!\left(\frac{2\pi}{T}\,t\right) + 0.5\,\sin\!\left(\frac{4\pi}{T}\,t\right),
\quad t \in [0,\, 40~\text{ms}),
\end{equation*}

gegeben. Wir berechnen jetzt den Wert der periodischen Fortsetzung an zwei
Stellen außerhalb des Messfensters.

**Stelle $t_1 = 95~\text{ms}$:** Wir dividieren $95~\text{ms}$ durch
$T = 40~\text{ms}$:

\begin{equation*}
\frac{t_1}{T} = \frac{95}{40} = 2.375
\qquad \Rightarrow \qquad
k = \lfloor 2.375 \rfloor = 2.
\end{equation*}

Der reduzierte Zeitpunkt ist $t_1 - 2 \cdot T = 95~\text{ms} - 80~\text{ms}
= 15~\text{ms}$. Dieser Wert liegt in $[0, 40~\text{ms})$, also gilt

\begin{equation*}
\tilde{g}(95~\text{ms}) = g(15~\text{ms}).
\end{equation*}

**Stelle $t_2 = -15~\text{ms}$:** Hier liegt $t_2$ links vom Messfenster:

\begin{equation*}
\frac{t_2}{T} = \frac{-15}{40} = -0.375
\qquad \Rightarrow \qquad
k = \lfloor -0.375 \rfloor = -1.
\end{equation*}

Der reduzierte Zeitpunkt ist $t_2 - (-1) \cdot T = -15~\text{ms} +
40~\text{ms} = 25~\text{ms}$. Dieser Wert liegt in $[0, 40~\text{ms})$, also

\begin{equation*}
\tilde{g}(-15~\text{ms}) = g(25~\text{ms}).
\end{equation*}

Zur Kontrolle prüfen wir, ob $\tilde{g}$ tatsächlich periodisch ist:

\begin{equation*}
\tilde{g}(t_2 + T) = \tilde{g}(-15~\text{ms} + 40~\text{ms})
= \tilde{g}(25~\text{ms}) = g(25~\text{ms}) = \tilde{g}(t_2). \quad \checkmark
\end{equation*}

```{figure} pics/chap12_sec01_fig02.svg
---
name: chap12_sec01_fig02
width: 100%
---
Periodische Fortsetzung der Messkurve $g$ über mehrere Perioden. Die
Grundperiode $[0, T)$ ist gelb hinterlegt. Die Auswertungsstellen
$t_1 = 95~\text{ms}$ und $t_2 = -15~\text{ms}$ sind markiert und auf ihre
reduzierten Zeitpunkte im Grundintervall zurückgeführt.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

## Zusammenfassung und Ausblick

In diesem Abschnitt haben wir die drei grundlegenden Kenngrößen einer
periodischen Funktion kennengelernt: die Periode $T$, die Kreisfrequenz
$\omega_0 = 2\pi/T$ und die Amplitude $\hat{f}$. Außerdem haben wir gesehen,
wie man eine auf einem Intervall gemessene Funktion durch periodische
Fortsetzung auf die gesamte Zeitachse ausdehnt. Das Kurbelwellen-Beispiel hat
dabei gezeigt, dass sich alle drei Größen direkt aus technischen Angaben wie
der Drehzahl ablesen lassen.

Reale Signale wie der Kolbenhub einer Kurbelwelle sind selten eine reine
Sinusfunktion. In Abschnitt 12.2 werden wir sehen, dass sich solche Signale
aus mehreren Schwingungen unterschiedlicher Frequenz zusammensetzen, und wir
lernen die Begriffe Grundschwingung und Oberschwingung kennen.
