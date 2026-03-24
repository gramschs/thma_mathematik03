# Fourier-Reihe

Die **Fourier-Reihe** ist die Reihenentwicklung einer periodischen,
abschnittsweise stetigen Funktion in eine Summe von Sinus- und
Kosinusfunktionen. Die entscheidende Frage ist: Wie berechnet man die
Koeffizienten $a_k$ und $b_k$ optimal? Die Antwort liefert ein
Minimierungsprinzip: Man wählt die Koeffizienten so, dass das Fehlerintegral
zwischen der Funktion und dem trigonometrischen Polynom minimal wird.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie wissen, dass sich fast alle integrierbaren Funktionen $f$ mit Periode
  $T$ als **Fourier-Reihe** darstellen lassen:

  $$S_f(t) = \frac{a_0}{2} + \sum_{k=1}^\infty \bigl(a_k\cos(k\omega t)
    + b_k\sin(k\omega t)\bigr), \quad \omega = \frac{2\pi}{T}$$

* Sie können die **Fourier-Koeffizienten** $a_0$, $a_k$ und $b_k$ berechnen:

  $$a_k = \frac{2}{T}\int_{-T/2}^{T/2} f(t)\cos(k\omega t)\,dt, \quad k = 0,1,2,\ldots$$

  $$b_k = \frac{2}{T}\int_{-T/2}^{T/2} f(t)\sin(k\omega t)\,dt, \quad k = 1,2,\ldots$$

* Sie können die Herleitung der Fourier-Koeffizienten aus dem
  **Minimierungsprinzip** des Fehlerintegrals nachvollziehen.
* Sie kennen folgende **Eigenschaften** der Fourier-Koeffizienten:
    * Fourier-Koeffizienten sind nichts anderes als **Mittelwerte** periodischer
      Funktionen.
    * Für stetige Funktionen gilt $a_k, b_k \sim \frac{1}{k^2}$, d.h. die
      Koeffizienten werden mit wachsendem $k$ immer kleiner.
    * An **Unstetigkeitsstellen** gilt nur noch $a_k, b_k \sim \frac{1}{k}$.
    * Die Summe periodischer Funktionen ist wieder periodisch.
* Sie können **Symmetrieeigenschaften** einer Funktion beim Berechnen der
  Fourier-Koeffizienten ausnutzen:
    * Ist $f$ eine **gerade** Funktion, so gilt $b_k = 0$ für alle $k$
      (reine Kosinusreihe).
    * Ist $f$ eine **ungerade** Funktion, so gilt $a_k = 0$ für alle $k$
      (reine Sinusreihe).
```

## Zusammenfassung und Ausblick

Wir können nun zu jeder geeigneten periodischen Funktion eine Fourier-Reihe
mit reellen Koeffizienten berechnen. Im nächsten Abschnitt betrachten wir ein wichtiges Phänomen, das beim
Approximieren von Funktionen mit Sprungstellen auftritt: das
**Gibbssche Phänomen**.
