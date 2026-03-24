# Partikuläre Lösung der inhomogenen DGL 2. Ordnung und Resonanz

Wir können die homogene DGL 2. Ordnung bereits vollständig lösen. Jetzt
ergänzen wir das Verfahren um eine **partikuläre Lösung** der inhomogenen DGL
und lernen ein wichtiges Sonderphänomen kennen: die **Resonanz**.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie können eine partikuläre Lösung der inhomogenen linearen gDGL 2. Ordnung
  mit konstanten Koeffizienten

  $$y'' + ay' + by = g(x)$$

  durch einen **Ansatz vom Typ der rechten Seite** berechnen. Sie wählen den
  Ansatz aus der folgenden Tabelle und bestimmen die Konstanten durch
  Einsetzen und Koeffizientenvergleich:

  | Störfunktion $g(x)$ | Ansatz $y_p(x)$ |
  |---|---|
  | Polynom Grad $n$, $b \neq 0$ | $C_n x^n + \ldots + C_0$ |
  | Polynom Grad $n$, $b = 0$, $a \neq 0$ | $x(C_n x^n + \ldots + C_0)$ |
  | Polynom Grad $n$, $b = 0$, $a = 0$ | $x^2(C_n x^n + \ldots + C_0)$ |
  | $A\sin(\omega_g x)$ oder $B\cos(\omega_g x)$, $\pm i\omega_g \neq \lambda_{1/2}$ | $C_1\sin(\omega_g x) + C_2\cos(\omega_g x)$ |
  | $A\sin(\omega_g x)$ oder $B\cos(\omega_g x)$, $\pm i\omega_g = \lambda_{1/2}$ | $x\bigl(C_1\sin(\omega_g x) + C_2\cos(\omega_g x)\bigr)$ |
  | $Ae^{cx}$, $c \neq \lambda_{1/2}$ | $Ce^{cx}$ |
  | $Ae^{cx}$, $c = \lambda_1$ oder $\lambda_2$ (einfach) | $Cxe^{cx}$ |
  | $Ae^{cx}$, $c = \lambda_{1/2}$ (doppelt) | $Cx^2 e^{cx}$ |

* Sie kennen das Phänomen der **Resonanz**: Resonanz liegt vor, wenn die
  Störfunktion $g(x)$ bereits in der allgemeinen Lösung der homogenen DGL
  enthalten ist (d.h. wenn $g(x)$ eine Lösung der homogenen DGL ist).
* Sie können den **Resonanzfall** erkennen, indem Sie prüfen, ob der
  Exponent bzw. die Frequenz der Störfunktion eine Lösung der
  charakteristischen Gleichung ist.
* Sie können im Resonanzfall den entsprechend modifizierten Ansatz aus der
  Tabelle anwenden (Multiplikation mit $x$ bzw. $x^2$) und damit die
  allgemeine Lösung der inhomogenen DGL bestimmen.
```

## Zusammenfassung und Ausblick

Mit dem Störansatz für die DGL 2. Ordnung und dem Resonanzkonzept sind nun alle
wesentlichen Lösungsverfahren für lineare gDGLen mit konstanten Koeffizienten
beisammen. Den Abschluss bildet eine **Übersicht** aller erlernten Methoden im
nächsten Abschnitt.
