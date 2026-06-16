---
authors:
  - name: Simone Gramsch
---

# 12.3 Die Fourierreihe und ihre Koeffizienten

In Abschnitt 12.2 haben wir gesehen, dass sich ein reales Motorsignal als
Überlagerung einer Grundschwingung und ihrer Oberschwingungen beschreiben lässt.
Wir wussten dort aber noch nicht, mit welchen Amplituden die einzelnen Anteile
auftreten. *Wie bestimmt man diese Amplituden systematisch, wenn man nur die
Funktion selbst kennt?* Die Antwort geben Formeln, die das zentrale
Rechenwerkzeug dieses Kapitels bilden.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können die Formeln für die Fourierkoeffizienten $a_0$,
  $a_n$ und $b_n$ korrekt aufschreiben und die Bedeutung jedes Terms erläutern.
* [ ] Sie verstehen, dass die Fourierreihe eine periodische Funktion als
  Überlagerung von Sinus- und Kosinusschwingungen darstellt, und können
  diesen Zusammenhang in eigenen Worten beschreiben.
* [ ] Sie können die **Fourierreihe** einer gegebenen periodischen Funktion
  formal aufstellen und die ersten Partialsummen angeben.
* [ ] Sie kennen die **Dirichlet-Bedingungen** und können für typische
  technische Signale entscheiden, ob eine Fourierreihe konvergiert.
```

## Vom trigonometrischen Polynom zur Fourierreihe

In Abschnitt 12.2 haben wir ein Signal aus zwei Termen zusammengesetzt:
Grundschwingung plus erste Oberschwingung. Das Ergebnis war eine kompliziertere
periodische Funktion. Wir können diesen Gedanken umkehren: Jede periodische
Funktion lässt sich als Summe von Sinus- und Kosinusfunktionen unterschiedlicher
Frequenz schreiben. Eine endliche solche Summe nennt man ein
**trigonometrisches Polynom**.

```{admonition} Was ist ... ein trigonometrisches Polynom?
:class: note
Ein **trigonometrisches Polynom** vom Grad $N$ zur Kreisfrequenz
$\omega_0 = 2\pi/T$ ist eine Funktion der Form

\begin{equation*}
S_N(t) = \frac{a_0}{2} + \sum_{n=1}^{N}
\bigl(a_n \cos(n\,\omega_0\,t) + b_n \sin(n\,\omega_0\,t)\bigr).
\end{equation*}

Die Konstanten $a_0,\, a_1,\, b_1,\, a_2,\, b_2,\, \ldots$ heißen
**Fourierkoeffizienten**. Der Term $a_0/2$ beschreibt den Mittelwert der
Funktion über eine Periode.
```

Der Faktor $\frac{1}{2}$ vor $a_0$ wirkt zunächst willkürlich. Er kommt daher,
dass die Kosinusfunktion für $n = 0$ den konstanten Wert $\cos(0) = 1$ hat,
und die zugehörige Integrationsformel dann dieselbe Gestalt wie für alle
anderen $a_n$ annimmt. Wir halten uns an diese in der Literatur übliche
Schreibweise.

Je höher wir den Grad $N$ wählen, desto mehr Schwingungsanteile nehmen wir mit.
Die Frage ist: Welche Koeffizienten $a_n$ und $b_n$ muss man wählen, damit das
trigonometrische Polynom die gegebene Funktion $f$ möglichst gut annähert?

## Wie berechnet man die Fourierkoeffizienten?

Die entscheidende mathematische Eigenschaft der Sinus- und Kosinusfunktionen
ist ihre **Orthogonalität**: Integriert man das Produkt zweier verschiedener
Sinus- und Kosinusfunktionen über eine vollständige Periode, ergibt sich stets
null. Nur wenn man eine Funktion mit sich selbst multipliziert, erhält man einen
von null verschiedenen Wert. Dieses Prinzip ist vergleichbar mit dem
Skalarprodukt senkrechter Vektoren: $\vec{e}_1 \cdot \vec{e}_2 = 0$, aber
$\vec{e}_1 \cdot \vec{e}_1 = 1$.

Nutzt man diese Orthogonalität aus und multipliziert beide Seiten des
trigonometrischen Polynoms mit $\cos(n\,\omega_0\,t)$ beziehungsweise
$\sin(n\,\omega_0\,t)$ und integriert dann über eine Periode, so fallen alle
Terme bis auf einen heraus. Das Ergebnis sind die folgenden Formeln zur
Berechnung der Fourierkoeffizienten.

```{admonition} Wie werden die Fourierkoeffizientne berechnet?
:class: note
Sei $f$ eine periodische Funktion mit Periode $T$ und Kreisfrequenz
$\omega_0 = 2\pi/T$. Die **Fourierkoeffizienten** von $f$ werden berechnet als

\begin{align*}
a_n &= \frac{2}{T} \int_{-T/2}^{T/2} f(t)\,\cos(n\,\omega_0\,t)\,dt,
\quad n = 0, 1, 2, \ldots \\
b_n &= \frac{2}{T} \int_{-T/2}^{T/2} f(t)\,\sin(n\,\omega_0\,t)\,dt,
\quad n = 1, 2, \ldots
\end{align*}

Der Koeffizient $a_0 = \frac{2}{T}\int_{-T/2}^{T/2} f(t)\,dt$ ist der
doppelte Mittelwert von $f$ über eine Periode.
```

Der Koeffizient $a_n$ gibt an, wie stark die $n$-te Kosinusschwingung in $f$
enthalten ist, der Koeffizient $b_n$ entsprechend für die $n$-te
Sinusschwingung. Ein großes $|a_3|$ bedeutet, dass die dritte Oberschwingung
des Kosinusanteils einen starken Einfluss auf das Signal hat.

Wir wenden die Formeln sofort auf unser Kurbelwellen-Signal an. Wir nehmen
vereinfachend an, dass der Kolbenhub auf einer Periode durch

\begin{equation*}
f(t) = \begin{cases}
2, & 0 \leq t < T/2, \\
-1, & T/2 \leq t < T
\end{cases}
\end{equation*}

beschrieben wird, also ein asymmetrisches Rechtecksignal mit den Werten $2$ und
$-1$ und der Periode $T = 0.04~\text{s}$. Wir berechnen zunächst $a_0$:

\begin{align*}
a_0 &= \frac{2}{T}\int_{-T/2}^{T/2} f(t)\,dt
= \frac{2}{T}\left(\int_{0}^{T/2} 2\,dt + \int_{T/2}^{T}(-1)\,dt\right) \\
&= \frac{2}{T}\left(2\cdot\frac{T}{2} + (-1)\cdot\frac{T}{2}\right)
= \frac{2}{T}\cdot\frac{T}{2} = 1.
\end{align*}

Der Mittelwert von $f$ über eine Periode beträgt $a_0/2 = 0.5$. Das ist
plausibel: Das Signal verbringt die halbe Zeit bei $+2$ und die halbe Zeit bei
$-1$, der arithmetische Mittelwert ist also $(2 + (-1))/2 = 0.5$.

## Was ist die Fourierreihe?

Lassen wir den Grad $N$ des trigonometrischen Polynoms gegen unendlich wachsen,
erhalten wir eine unendliche Summe. Diese heißt **Fourierreihe**.

```{admonition} Was ist ... die Fourierreihe?
:class: note
Die **Fourierreihe** einer periodischen Funktion $f$ mit Periode $T$ und
Kreisfrequenz $\omega_0 = 2\pi/T$ ist die unendliche Summe

\begin{equation*}
f(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty}
\bigl(a_n \cos(n\,\omega_0\,t) + b_n \sin(n\,\omega_0\,t)\bigr),
\end{equation*}

wobei die Koeffizienten $a_n$ und $b_n$ durch die Euler-Fourier-Formeln
berechnet werden.
```

Die **Partialsumme** $S_N$ ist die Näherung, die man erhält, wenn man die
Reihe nach $N$ Termen abbricht. Für $N = 1$ enthält $S_1$ nur Grundschwingung
und Mittelwert, für $N = 3$ kommen noch die erste und zweite Oberschwingung
hinzu. Je größer $N$, desto besser die Annäherung an $f$.

```{figure} pics/chap12_sec03_fig01.svg
---
name: chap12_sec03_fig01
---
Partialsummen $S_1$, $S_3$ und $S_7$ der Fourierreihe des asymmetrischen
Rechtecksignals. Mit wachsendem $N$ nähert sich die Partialsumme der
ursprünglichen Funktion an.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

## Wann konvergiert die Fourierreihe?

Die Frage, ob die Fourierreihe tatsächlich gegen $f$ konvergiert, ist nicht
trivial. Für praktische Anwendungen im Maschinenbau liefern die
**Dirichlet-Bedingungen** eine hinreichende Antwort.

```{admonition} Was sind ... die Dirichlet-Bedingungen?
:class: note
Eine periodische Funktion $f$ kann in eine konvergente Fourierreihe entwickelt
werden, wenn innerhalb einer Periode die folgenden beiden Bedingungen erfüllt
sind:

1. Das Periodenintervall lässt sich in endlich viele Teilintervalle unterteilen,
   auf denen $f$ stetig und monoton ist.
2. An jeder Unstetigkeitsstelle existieren der linksseitige und der
   rechtsseitige Grenzwert.

An einer Unstetigkeitsstelle $t^*$ konvergiert die Fourierreihe dann gegen den
Mittelwert der beiden einseitigen Grenzwerte:

\begin{equation*}
\frac{f(t^*-) + f(t^*+)}{2}.
\end{equation*}
```

Alle in der Ingenieurtechnik auftretenden Signale, also Rechteck-, Sägezahn-
und Dreiecksschwingungen, aber auch stückweise lineare Verläufe wie
Nockenprofile oder Ventilhubkurven, erfüllen diese Bedingungen. Die
Dirichlet-Bedingungen sind daher in der Praxis fast immer automatisch erfüllt.

Für unser asymmetrisches Rechtecksignal springt $f$ an den Stellen $t = 0$
und $t = T/2$. An der Stelle $t = 0$ beträgt der Mittelwert der einseitigen
Grenzwerte $(f(0-) + f(0+))/2 = (-1 + 2)/2 = 0.5$. Gegen diesen Wert
konvergiert die Fourierreihe an der Sprungstelle, nicht gegen $2$ oder $-1$.

## Zusammenfassung und Ausblick

Die Euler-Fourier-Formeln liefern zu jeder hinreichend regulären periodischen
Funktion eindeutig bestimmte Fourierkoeffizienten $a_n$ und $b_n$. Der
Koeffizient $a_0$ ist der doppelte Mittelwert, die übrigen Koeffizienten messen
den Anteil der jeweiligen Sinus- und Kosinusschwingung am Signal. Die
Dirichlet-Bedingungen garantieren die Konvergenz in allen technisch relevanten
Fällen. In Abschnitt 12.4 rechnen wir die Koeffizienten für ein konkretes
Beispiel vollständig durch und stellen die zugehörige Fourierreihe in
geschlossener Form auf.
