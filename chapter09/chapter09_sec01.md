# Variation der Konstanten: aus einer Konstante wird eine Funktion

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie kennen die **Notation** $y_h$, $y_p$ und $y_{\text{allgemein}}$ für die Lösungen einer linearen inhomogenen gDGL 1. Ordnung und wissen, welche Rolle jede Lösung spielt.
* [ ] Sie wissen, dass sich die allgemeine Lösung der inhomogenen linearen DGL $y' + f(x) \cdot y = g(x)$ als Summe
  \begin{equation*}
  y_{\text{allgemein}}(x) = y_h(x) + y_p(x)
  \end{equation*}
  aus homogener Lösung und partikulärer Lösung zusammensetzt.
* [ ] Sie beherrschen das **Verfahren der Variation der Konstanten**: Sie ersetzen die Konstante $A$ in $y_h$ durch eine Funktion $A(x)$ und bestimmen $A(x)$ durch Einsetzen in die DGL.
* [ ] Sie können die allgemeine Lösungsformel
  \begin{equation*}
  y_{\text{allgemein}}(x) = A \cdot e^{-\int f(x)\,dx} + \left[\int g(x)\, e^{\int f(x)\,dx}\,dx \right] e^{-\int f(x)\,dx}
  \end{equation*}
  auf eine gegebene lineare inhomogene gDGL 1. Ordnung anwenden.
```
