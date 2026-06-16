---
authors:
  - name: Simone Gramsch
---

# 13.3 Energieinhalt und Klirrfaktor

In Abschnitt 13.2 haben wir gesehen, dass die Fourierreihe an Sprungstellen
nicht gleichmäßig konvergiert und das Gibbssche Phänomen unvermeidlich ist.
Jetzt stellen wir eine andere Frage: Nicht wie gut die Partialsumme die
Funktion annähert, sondern wie viel Energie in den einzelnen Oberschwingungen
einer periodischen Lagerkraft steckt. In Kapitel 11 haben wir gelernt, dass
eine Oberschwingung, deren Frequenz mit der Eigenfrequenz des Lagers
übereinstimmt, Resonanz auslösen kann. *Aber welche Oberschwingung ist der
gefährlichste Kandidat, und wie groß ist ihr Energieanteil?* Die Antwort
liefern das Parsevalsche Theorem und der Klirrfaktor.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können das **Parsevalsche Theorem** anwenden, um den mittleren
  quadratischen Energieinhalt eines periodischen Signals aus seinen
  Fourierkoeffizienten zu berechnen.
* [ ] Sie kennen den Begriff des **Klirrfaktors** und können ihn aus den
  Fourierkoeffizienten eines Signals berechnen.
* [ ] Sie verstehen, was ein kleiner bzw. großer Klirrfaktor über die
  Signalqualität in einer technischen Anwendung aussagt.
```

## Was meinen wir mit dem Energieinhalt einer periodischen Kraft?

In der Schwingungslehre ist nicht die Spitzenkraft allein entscheidend, sondern
ihr mittlerer Effekt über eine gesamte Periode. Ein kurzer, scharfer Kraftstoß
und eine dauerhafte, moderate Schwingkraft können dieselbe Spitzenkraft haben,
aber völlig unterschiedliche Auswirkungen auf ein Bauteil. Das physikalisch
relevante Maß ist das zeitliche Mittel des Kraftquadrats, der sogenannte
**Effektivwert**.

Als Modell verwenden wir die periodische Lagerkraft aus Abschnitt 12.4, die wir
als symmetrische Rechteckschwingung mit Periode $T = 2\pi$ beschrieben haben:

\begin{equation*}
f(t) = \begin{cases}
\phantom{-}1, & -\pi \leq t < 0, \\
-1, & \phantom{-}0 \leq t < \pi.
\end{cases}
\end{equation*}

```{admonition} Was ist ... der Energieinhalt eines periodischen Signals?
:class: note
Der **Energieinhalt** (mittlere quadratische Energie) eines periodischen
Signals $f$ mit Periode $T$ ist

\begin{equation*}
E = \frac{1}{T}\int_{-T/2}^{T/2} f(t)^2\,dt.
\end{equation*}

In der Elektrotechnik entspricht das dem Quadrat des Effektivwerts einer
Spannung oder eines Stroms. In der Schwingungslehre entspricht es dem
quadratischen Mittelwert einer Schwingkraft oder Beschleunigung.
```

Für die Rechteck-Lagerkraft ist die Rechnung einfach: Da $f(t)^2 = 1$ für alle
$t$, gilt

\begin{equation*}
E = \frac{1}{T}\int_{-T/2}^{T/2} 1\,dt = 1.
\end{equation*}

Diesen Wert $E = 1$ werden wir gleich als Kontrollgröße nutzen.

## Das Parsevalsche Theorem: Energie aus den Fourierkoeffizienten

Für ein gemessenes Lagerkraftsignal mit vielen Oberschwingungen ist das direkte
Integral oft unpraktisch. *Lässt sich $E$ auch direkt aus den
Fourierkoeffizienten ablesen?* Das Parsevalsche Theorem gibt eine elegante
positive Antwort.

```{admonition} Was ist ... das Parsevalsche Theorem?
:class: note
Kann $f$ in eine Fourierreihe mit Koeffizienten $a_n$ und $b_n$ entwickelt
werden, so gilt:

\begin{equation*}
E = \frac{1}{T}\int_{-T/2}^{T/2} f(t)^2\,dt
= \frac{a_0^2}{4} + \frac{1}{2}\sum_{n=1}^{\infty}
\bigl(a_n^2 + b_n^2\bigr).
\end{equation*}

Jeder Term $\frac{1}{2}(a_n^2 + b_n^2)$ ist der **Energiebeitrag der
$n$-ten Oberschwingung**. Der Term $a_0^2/4$ ist der Energiebeitrag des
Gleichanteils.
```

Das Theorem sagt: Die Gesamtenergie verteilt sich auf alle Oberschwingungen,
und die Energiebeiträge addieren sich ohne Wechselwirkung. Das ist ein direktes
Abbild der Orthogonalität der Sinus- und Kosinusfunktionen aus Abschnitt 12.3.

Wir wenden das Theorem auf die Rechteck-Lagerkraft an. Aus Abschnitt 12.4
kennen wir die Fourierkoeffizienten: $a_0 = 0$, $a_n = 0$ für alle $n \geq 1$,
und

\begin{equation*}
b_n = \begin{cases}
0, & n \text{ gerade}, \\[4pt]
\dfrac{-4}{n\pi}, & n \text{ ungerade}.
\end{cases}
\end{equation*}

Die Parsevalsche Summe lautet damit

\begin{align*}
E &= \frac{1}{2}\sum_{\substack{n=1 \\ n \text{ ungerade}}}^{\infty} b_n^2
= \frac{1}{2}\sum_{k=1}^{\infty}\left(\frac{4}{(2k-1)\pi}\right)^2
= \frac{8}{\pi^2}\sum_{k=1}^{\infty}\frac{1}{(2k-1)^2}.
\end{align*}

Da wir wissen, dass $E = 1$ gelten muss, folgt daraus

\begin{equation*}
\sum_{k=1}^{\infty}\frac{1}{(2k-1)^2}
= 1 + \frac{1}{9} + \frac{1}{25} + \ldots = \frac{\pi^2}{8}. \quad \checkmark
\end{equation*}

Das ist ein bekanntes Ergebnis der Analysis. Das Parsevalsche Theorem liefert
es hier als Nebenprodukt einer ingenieurmäßigen Rechnung.

Physikalisch lesen wir aus der Summe ab, wie die Energie auf die
Oberschwingungen verteilt ist. Die Grundschwingung ($k = 1$) trägt
$\frac{8}{\pi^2} \approx 0.811$ zur Gesamtenergie bei, also etwa $81\,\%$. Die
erste Oberschwingung ($k = 2$, also $n = 3$) trägt $\frac{8}{9\pi^2} \approx
0.090$ bei, knapp $9\,\%$. Die höheren Oberschwingungen teilen sich die
verbleibenden $10\,\%$.

## Was ist der Klirrfaktor?

Die Grundschwingung der Lagerkraft ist der gewünschte, konstruktiv unvermeidbare
Anteil. Die Oberschwingungen sind der störende Rest: Sie können Resonanzen
anregen, die das Lager belasten, und erzeugen akustische Emissionen. *Wie groß
ist dieser unerwünschte Anteil insgesamt, bezogen auf die Gesamtenergie?*

```{admonition} Was ist ... der Klirrfaktor?
:class: note
Der **Klirrfaktor** $k$ eines periodischen Signals ist definiert als

\begin{equation*}
k = \sqrt{\frac{E_{\text{Ober}}}{E_{\text{gesamt}}}},
\end{equation*}

wobei $E_{\text{gesamt}}$ die gesamte mittlere quadratische Energie und
$E_{\text{Ober}}$ die Energie aller Oberschwingungen ohne Grundschwingung und
ohne Gleichanteil ist:

\begin{equation*}
E_{\text{Ober}} = E_{\text{gesamt}} - \frac{a_0^2}{4}
- \frac{1}{2}\bigl(a_1^2 + b_1^2\bigr).
\end{equation*}

Ein Klirrfaktor nahe $0$ bedeutet ein nahezu sinusförmiges Signal. Ein
Klirrfaktor nahe $1$ bedeutet, dass die Oberschwingungen die Gesamtenergie
dominieren.
```

Für die Rechteck-Lagerkraft berechnen wir zunächst die Energie der
Grundschwingung. Mit $a_1 = 0$ und $b_1 = -4/\pi$ gilt

\begin{equation*}
E_{\text{Grund}} = \frac{1}{2}\,b_1^2 = \frac{1}{2}\cdot\frac{16}{\pi^2}
= \frac{8}{\pi^2} \approx 0.811.
\end{equation*}

Die Oberschwingungsenergie ist

\begin{equation*}
E_{\text{Ober}} = E_{\text{gesamt}} - E_{\text{Grund}}
= 1 - \frac{8}{\pi^2} \approx 0.189.
\end{equation*}

Der Klirrfaktor beträgt damit

\begin{equation*}
k = \sqrt{\frac{E_{\text{Ober}}}{E_{\text{gesamt}}}}
= \sqrt{1 - \frac{8}{\pi^2}}
\approx \sqrt{0.189} \approx 0.435.
\end{equation*}

Etwa $43\,\%$ der Signalamplitude entfallen also auf Oberschwingungen. Das
ist ein hoher Wert, der erklärt, warum eine reale Kurbelwelle mit einem
rechteckförmigen Kraftprofil in der Praxis durch aufwendige Lagergestaltung
und Dämpfungsmaßnahmen entschärft wird. Ein Motor mit einem möglichst
sinusförmigen Drehmomentprofil hat einen deutlich kleineren Klirrfaktor und
damit weniger unerwünschte Oberschwingungsanregungen. In Abschnitt 13.4
werden wir sehen, welche dieser Oberschwingungen besonders gefährlich ist,
nämlich diejenige, deren Frequenz der Eigenfrequenz des Systems am nächsten
liegt.

## Zusammenfassung und Ausblick

Das Parsevalsche Theorem verbindet den Zeitbereich (Integral von $f^2$) mit
dem Frequenzbereich (Summe der quadratischen Fourierkoeffizienten): Die
Energie verteilt sich additiv auf alle Oberschwingungen. Der Klirrfaktor
fasst den Oberschwingungsanteil in einer einzigen Kennzahl zusammen und ist
in der Antriebstechnik und Messtechnik ein gängiges Qualitätsmaß. In
Abschnitt 13.4 schließen wir den Bogen zu Kapitel 11: Wir nutzen die
Fourierzerlegung der Erregerkraft, um die erzwungene Schwingung eines
Feder-Masse-Systems unter periodischer Erregung komponentenweise zu lösen
und die resonanzgefährdende Oberschwingung zu identifizieren.
