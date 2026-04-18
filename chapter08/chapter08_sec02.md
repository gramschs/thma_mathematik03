# Die homogene Lösung: warum ein Exponentialansatz funktioniert

```{admonition} Warnung
:class: warning
Dieses Vorlesungsskript befindet sich im Umbau.
```

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können die allgemeine Lösung $y_h$ der homogenen linearen DGL 1. Ordnung $y' + f(x) \cdot y = 0$ mit Hilfe der Separation der Variablen herleiten.
* [ ] Sie können die Formel
  \begin{equation*}
  y_h(x) = A \cdot e^{-\int f(x)\, dx}, \quad A \in \mathbb{R}
  \end{equation*}
  auf eine gegebene homogene lineare DGL 1. Ordnung anwenden.
* [ ] Sie können den Sonderfall konstanter Koeffizienten $y' + ay = 0$ direkt lösen und die Lösung $y_h(x) = A \cdot e^{-ax}$ angeben.
```
