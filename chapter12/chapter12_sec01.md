# Fourier-Reihen – Einführung und Motivation

Was hat ein Lied, das Sie Shazam vorspielen, mit Mathematik zu tun? Mehr als man
zunächst vermuten würde. Die App zerlegt das aufgenommene Tonsignal mit Hilfe der
**Fast-Fourier-Transformation** in seine Frequenzbestandteile und vergleicht dieses
Spektrum mit einer Datenbank von Millionen Liedern. Grundlage dafür ist die
**Fourier-Reihe** – die Darstellung einer periodischen Funktion als (unendliche)
Summe von Sinus- und Kosinusfunktionen.

In Mathematik 2 haben Sie Funktionen durch **Taylor-Reihen** angenähert, deren
Basisfunktionen Potenzen $x^k$ sind. Taylor-Reihen sind in der Nähe eines
Entwicklungspunkts optimal, konvergieren jedoch langsam für $|x - x_0| \to \infty$
und versagen bei unstetigen Funktionen. Bei der **Fourier-Reihe** sind die
Basisfunktionen $\sin(k\omega t)$ und $\cos(k\omega t)$; ihr entscheidender Vorteil
ist, dass sie auch an **Sprungstellen** konvergiert.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie kennen eine ingenieurwissenschaftliche Motivation für Fourier-Reihen
  (z.B. Shazam, Signalverarbeitung, Klangfarbe von Musikinstrumenten).
* Sie wissen, dass bei einer Fourier-Reihe die **Basisfunktionen**
  $\sin(k\omega t)$ und $\cos(k\omega t)$ sind (im Gegensatz zu
  Potenzen $x^k$ bei Taylor-Reihen).
* Sie kennen den wesentlichen **Vorteil der Fourier-Reihe** gegenüber der
  Taylor-Reihe: Fourier-Reihen können auch unstetige, nicht differenzierbare
  Funktionen annähern.
```

## Zusammenfassung und Ausblick

Fourier-Reihen sind das mathematische Fundament der Signal- und Bildverarbeitung.
In den folgenden Abschnitten erarbeiten wir zunächst das notwendige Grundwissen
zu periodischen und trigonometrischen Funktionen und berechnen dann systematisch
reelle und komplexe Fourier-Reihen.
