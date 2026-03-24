# Grundwissen – Lineare gDGLen

Bevor wir Lösungsverfahren kennenlernen, klären wir die grundlegenden Begriffe
rund um lineare gewöhnliche Differentialgleichungen. Diese Definitionen bilden
die Basis für alle weiteren Abschnitte dieses Kapitels.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie wissen, wie eine **lineare gewöhnliche Differentialgleichung** (kurz:
  lineare DGL) definiert ist:

  $$y^{(n)} + f_{n-1}(x)\cdot y^{(n-1)} + \ldots + f_1(x)\cdot y' + f_0(x)\cdot y = g(x)$$

* Sie können zwischen einer **homogenen** ($g(x)=0$) und einer **inhomogenen**
  ($g(x)\neq 0$) linearen DGL unterscheiden; $g(x)$ wird dabei
  **Störfunktion** genannt.
* Sie wissen, dass jede homogene lineare DGL die **triviale Lösung** $y(x)=0$
  besitzt.
* Sie können zwischen einer linearen DGL **mit konstanten Koeffizienten**

  $$y' + 2y = x^2, \quad y'' - 3y' + 4y = e^{2x}$$

  und einer linearen DGL **ohne konstante Koeffizienten** unterscheiden:

  $$y' + \frac{1}{x}y = x, \quad y' + f(x)y = g(x)$$

* Sie können die allgemeine Lösung $y_h(x)$ einer **homogenen linearen DGL
  1. Ordnung**

  $$y' + f(x)\cdot y = 0$$

  mit zwei Methoden berechnen:
    * **Separation der Variablen** und
    * Anwenden der Formel $y_h(x) = A\cdot e^{-\int f(x)\,dx}$, $A \in \mathbb{R}$.
```

## Zusammenfassung und Ausblick

Mit diesen Grundbegriffen können wir lineare DGLen klassifizieren und einfache
homogene Gleichungen 1. Ordnung lösen. Im nächsten Abschnitt erweitern wir das
Repertoire auf inhomogene DGLen mit dem Verfahren der **Variation der
Konstanten**.
