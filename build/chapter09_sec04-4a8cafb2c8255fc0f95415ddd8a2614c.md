# Lineare inhomogene gDGL 1. Ordnung mit konstanten Koeffizienten

Ein besonders häufig auftretender Spezialfall ist die lineare inhomogene DGL
1. Ordnung mit **konstanten Koeffizienten**:

$$y' + ay = g(x), \quad a \in \mathbb{R},\; a = \text{const.}$$

Hier vereinfacht sich die allgemeine Lösungsformel erheblich. Zusätzlich steht
uns für die partikuläre Lösung ein praktisches Hilfsmittel zur Verfügung: der
**Ansatz vom Typ der rechten Seite** (Störansatz).

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie können die vereinfachte **Lösungsformel für konstante Koeffizienten**
  anwenden:

  $$y_\text{allgemein}(x) = A\,e^{-ax}
    + \left[\int g(x)\,e^{ax}\,dx\right] e^{-ax}$$

* Sie können diese Formel aus dem Verfahren der Variation der Konstanten
  **herleiten** (d.h. die einzelnen Schritte begründen).
* Sie können alternativ zur Variation der Konstanten eine partikuläre Lösung
  mit einem **Ansatz vom Typ der rechten Seite** bestimmen. Dazu wählen Sie
  aus der folgenden Tabelle den passenden Ansatz:

  | Störfunktion $g(x)$ | Ansatz für $y_p(x)$ |
  |---|---|
  | Polynom vom Grad $n$ | $C_n x^n + \ldots + C_0$ |
  | $A\sin(\omega x)$, $B\cos(\omega x)$ oder Summe | $C_1\sin(\omega x) + C_2\cos(\omega x)$ |
  | $A e^{bx}$, $b \neq -a$ | $C e^{bx}$ |
  | $A e^{bx}$, $b = -a$ (Resonanz) | $C x e^{bx}$ |

* Sie können durch **Koeffizientenvergleich** die unbekannten Konstanten $C_n$
  im Ansatz bestimmen.
* Sie können den passenden Ansatz auch angeben, wenn die Störfunktion eine
  **Summe oder ein Produkt** verschiedener Typen aus der Tabelle ist.
```

## Zusammenfassung und Ausblick

Für lineare inhomogene DGLen 1. Ordnung mit konstanten Koeffizienten stehen uns
nun zwei gleichwertige Wege zur Verfügung: die Variation der Konstanten und der
Störansatz. Im nächsten Abschnitt steigen wir auf **DGLen 2. Ordnung** um und
führen dafür das Konzept des **Fundamentalsystems** ein.
