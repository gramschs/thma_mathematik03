# Grundwissen – Periodische und trigonometrische Funktionen

Bevor wir Fourier-Reihen berechnen können, klären wir die grundlegenden Begriffe
rund um **periodische Funktionen** und **trigonometrische Polynome**. Dieses
Grundwissen ist die Voraussetzung für alle weiteren Abschnitte dieses Kapitels.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie kennen **periodische Funktionen** wie
  $\sin(t)$, $\cos(t)$, $A\sin(\omega t + \varphi)$, $A\cos(\omega t + \varphi)$
  und können diese skizzieren.
* Ihnen sind die Begriffe **Periode** $T$ (auch Schwingungsdauer), **Kreisfrequenz**
  $\omega$ und **Amplitude** $A$ bekannt und Sie können diese in einer Skizze
  eintragen.
* Sie kennen den Zusammenhang zwischen Periode und Kreisfrequenz:

  $$T = \frac{2\pi}{\omega}$$

* Sie können **periodische Fortsetzungen** von Funktionen erkennen und selbst
  aufstellen. Ist $f(t)$ auf $[a,b]$ definiert, so lautet die periodische
  Fortsetzung $f(t + Tn) = f(t)$ mit $n \in \mathbb{Z}$.
* Sie können den **Mittelwert** $m$ einer periodischen Funktion $f$ mit Periode
  $T$ berechnen:

  $$m = \frac{1}{T}\int_{-T/2}^{T/2} f(t)\,dt \qquad \text{oder} \qquad
    m = \frac{1}{T}\int_0^T f(t)\,dt$$

  und diesen Wert grafisch interpretieren.
* Sie kennen die Definition eines **trigonometrischen Polynoms vom Grad** $n$:

  $$p_n(t) = \frac{a_0}{2} + \sum_{k=1}^n \bigl[a_k\cos(k\omega t) + b_k\sin(k\omega t)\bigr],
    \quad T = \frac{2\pi}{\omega}$$

* Sie können ein trigonometrisches Polynom von einer **trigonometrischen Reihe**

  $$p(t) = \frac{a_0}{2} + \sum_{k=1}^\infty \bigl[a_k\cos(k\omega t) + b_k\sin(k\omega t)\bigr]$$

  unterscheiden.
* Sie kennen die Sonderfälle **Kosinusreihe** ($b_k = 0$ für alle $k$) und
  **Sinusreihe** ($a_k = 0$ für alle $k$).
* Sie kennen die Begriffe **Grundschwingung** ($k=1$) und
  **Oberschwingungen** ($k \geq 2$).
```

## Zusammenfassung und Ausblick

Mit diesen Grundbegriffen können wir periodische Funktionen klassifizieren,
ihren Mittelwert berechnen und sie als trigonometrische Polynome oder Reihen
beschreiben. Im nächsten Abschnitt lernen wir, wie wir die Koeffizienten einer
solchen Reihe systematisch aus einer gegebenen Funktion berechnen – die
eigentliche **Fourier-Reihe**.
