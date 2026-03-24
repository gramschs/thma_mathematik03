# Variation der Konstanten

Homogene lineare DGLen 1. Ordnung können wir bereits lösen. Um auch
**inhomogene** lineare DGLen 1. Ordnung lösen zu können, nutzen wir die
Linearitätseigenschaft aus: Die allgemeine Lösung setzt sich aus der Lösung
der zugehörigen homogenen DGL und einer speziellen (partikulären) Lösung der
inhomogenen DGL zusammen. Letztere bestimmen wir mit dem Verfahren der
**Variation der Konstanten**.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie benutzen die folgende **Notation** für die Lösungen der inhomogenen und
  der zugehörigen homogenen linearen gDGL 1. Ordnung:
    * $y_p$: spezielle (partikuläre) Lösung der inhomogenen DGL
      $y'(x) + f(x)\cdot y = g(x)$, bestimmt durch Variation der Konstanten.
    * $y_h$: allgemeine Lösung der homogenen DGL
      $y'(x) + f(x)\cdot y = 0$, bestimmt durch Separation der Variablen.
* Sie wissen, dass sich die **allgemeine Lösung** der inhomogenen linearen
  gDGL 1. Ordnung als Summe zusammensetzt:

  $$y_\text{allgemein}(x) = y_h(x) + y_p(x)$$

* Sie beherrschen das **Verfahren der Variation der Konstanten** und können
  damit eine partikuläre Lösung berechnen:
    1. Berechne $y_h(x) = A\,e^{-\int f(x)\,dx}$.
    2. Ersetze die Konstante $A$ durch eine Funktion $A(x)$.
    3. Bestimme $A(x)$ durch Einsetzen von $y_p = A(x)\,e^{-\int f(x)\,dx}$
       in die DGL; es ergibt sich $A(x) = \int g(x)\,e^{\int f(x)\,dx}\,dx$.
    4. Die partikuläre Lösung lautet:
       $y_p(x) = \left[\int g(x)\,e^{\int f(x)\,dx}\,dx\right] e^{-\int f(x)\,dx}$.
* Sie können die **allgemeine Lösungsformel** direkt anwenden:

  $$y_\text{allgemein}(x) = A\,e^{-\int f(x)\,dx}
    + \left[\int g(x)\,e^{\int f(x)\,dx}\,dx\right] e^{-\int f(x)\,dx}$$
```

## Zusammenfassung und Ausblick

Das Verfahren der Variation der Konstanten liefert uns ein allgemeines Werkzeug
für inhomogene lineare DGLen 1. Ordnung. Im nächsten Abschnitt spezialisieren
wir dieses Verfahren auf den wichtigen Spezialfall **konstanter Koeffizienten**,
wo sich die Formeln noch weiter vereinfachen und eine Tabelle von Standardansätzen
genutzt werden kann.
