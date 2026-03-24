# Komplexe Fourier-Reihe

Im vorherigen Abschnitt haben wir das Gibbssche Phänomen kennengelernt.
Nun wechseln wir die Perspektive und nutzen die **Eulersche Formel**
$e^{i\varphi} = \cos(\varphi) + i\sin(\varphi)$
lässt sich jede reelle Fourier-Reihe in eine **komplexe Fourier-Reihe**
umschreiben und umgekehrt. Die Basisfunktionen sind nun die komplexen
Exponentialfunktionen $e^{ik\omega t}$, was in vielen Anwendungen (z.B.
Signalverarbeitung, Fourier-Transformation) eine kompaktere Schreibweise
ermöglicht.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie können die Herleitung von der **reellen zur komplexen Fourier-Reihe**
  nachvollziehen, indem Sie $\cos(k\omega t)$ und $\sin(k\omega t)$ mit Hilfe
  der Eulerschen Formel durch $e^{ik\omega t}$ und $e^{-ik\omega t}$
  ausdrücken.
* Sie können die **komplexe Fourier-Reihe** einer Funktion $f$ mit Periode
  $T$ berechnen:

  $$S_f(t) = \sum_{k=-\infty}^{\infty} c_k\, e^{ik\omega t}, \quad
    \omega = \frac{2\pi}{T}$$

  mit den **komplexen Fourier-Koeffizienten**:

  $$c_k = \frac{1}{T}\int_{-T/2}^{T/2} f(t)\,e^{-ik\omega t}\,dt,
    \quad k = 0, \pm 1, \pm 2, \ldots$$

* Sie kennen den **Zusammenhang zwischen reellen und komplexen
  Fourier-Koeffizienten** und können zwischen beiden Darstellungen umrechnen:

  | Reell → Komplex | Komplex → Reell |
  |---|---|
  | $c_0 = \dfrac{a_0}{2}$ | $a_0 = 2\,\mathrm{Re}(c_0)$ |
  | $c_k = \dfrac{a_k - ib_k}{2}$ | $a_k = 2\,\mathrm{Re}(c_k)$ |
  | $c_{-k} = \dfrac{a_k + ib_k}{2}$ | $b_k = -2\,\mathrm{Im}(c_k)$ |

* Sie kennen die Vereinfachungen für **gerade und ungerade Funktionen**:
    * Für eine **gerade** Funktion gilt: alle $c_k$ sind **reell**, die
      Fourier-Reihe ist eine reine Kosinusreihe mit
      $a_k = \dfrac{4}{T}\displaystyle\int_0^{T/2} f(t)\cos(k\omega t)\,dt$.
    * Für eine **ungerade** Funktion gilt: alle $c_k$ sind **rein imaginär**,
      die Fourier-Reihe ist eine reine Sinusreihe mit
      $b_k = \dfrac{4}{T}\displaystyle\int_0^{T/2} f(t)\sin(k\omega t)\,dt$.
* Sie können folgende **Rechenoperationen** mit Fourier-Reihen durchführen
  und die resultierenden Koeffizienten angeben:
    * **Addition einer Konstanten** $C$: nur $\tilde{a}_0 = a_0 + 2C$
      ändert sich, alle anderen Koeffizienten bleiben gleich.
    * **Multiplikation mit einer Konstanten** $C$ (Skalierung): alle
      Koeffizienten werden mit $C$ multipliziert.
    * **Addition zweier Fourier-Reihen** (Überlagerung): die Koeffizienten
      werden addiert (sofern beide Funktionen dieselbe Periode haben).
```

## Zusammenfassung und Ausblick

Mit der komplexen Fourier-Reihe verfügen wir über eine kompakte und
mächtige Darstellung periodischer Funktionen. Sie bildet die direkte
Grundlage für die **Fourier-Transformation**, mit der auch nicht-periodische
Signale analysiert werden können – ein zentrales Werkzeug in der Signal-
und Bildverarbeitung, das in weiterführenden Vorlesungen behandelt wird.
