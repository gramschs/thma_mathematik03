# Fundamentalsystem und Wronski-Determinante

Bei linearen DGLen 2. Ordnung benötigt die allgemeine Lösung der zugehörigen
homogenen Gleichung **zwei linear unabhängige** Lösungsfunktionen. Das Konzept
des **Fundamentalsystems** formalisiert diese Anforderung; die
**Wronski-Determinante** liefert uns ein rechnerisches Kriterium zur Überprüfung.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie kennen die Definition einer **linearen gDGL 2. Ordnung mit konstanten
  Koeffizienten**:

  $$y'' + ay' + by = g(x), \quad a, b \in \mathbb{R}$$

  Für $g(x) \neq 0$ heißt sie inhomogen.

* Sie können zu einer gegebenen inhomogenen linearen DGL 2. Ordnung die
  **zugehörige homogene DGL** aufstellen.
* Sie können die **partikuläre Lösung** einer linearen gDGL 2. Ordnung
  bestimmen, indem Sie die Anfangswerte
  $y(x_0) = y_0$, $y'(x_0) = v_0$
  in die allgemeine Lösung einsetzen.
* Sie wissen, was **Fundamentallösungen** und ein **Fundamentalsystem** sind:
  Zwei Lösungen $y_1$ und $y_2$ bilden ein Fundamentalsystem, wenn aus
  $c_1 y_1(x) + c_2 y_2(x) = 0$ für alle $x$ folgt, dass $c_1 = c_2 = 0$
  (d.h. $y_1$ und $y_2$ sind **linear unabhängig**).
* Sie können mit der **Wronski-Determinante** nachweisen, ob zwei Lösungen
  ein Fundamentalsystem bilden:

  $$W(y_1, y_2) = \det\begin{pmatrix} y_1(x) & y_2(x) \\ y_1'(x) & y_2'(x)
  \end{pmatrix} = y_1 y_2' - y_2 y_1' \neq 0 \quad \forall\, x \in \mathbb{R}$$

* Sie können ein Fundamentalsystem zur homogenen DGL $y'' + ay' + by = 0$
  berechnen, indem Sie den **Ansatz** $y(x) = e^{\lambda x}$ verwenden und die
  **charakteristische Gleichung** $\lambda^2 + a\lambda + b = 0$ lösen.
* Sie kennen die drei Fälle in Abhängigkeit der **Diskriminante**
  $D = \frac{a^2}{4} - b$ und können die zugehörigen Lösungsfunktionen
  (Eigenfunktionen) angeben:

  | Diskriminante | Fundamentalsystem |
  |---|---|
  | $D > 0$ (Kriechfall) | $y_1 = e^{\lambda_1 x}$, $y_2 = e^{\lambda_2 x}$ |
  | $D < 0$ (Schwingfall) | $y_1 = e^{-\alpha x}\cos(\omega_0 x)$, $y_2 = e^{-\alpha x}\sin(\omega_0 x)$ |
  | $D = 0$ (aperiod. Grenzfall) | $y_1 = e^{-\frac{a}{2}x}$, $y_2 = x\,e^{-\frac{a}{2}x}$ |
```

## Zusammenfassung und Ausblick

Mit dem Fundamentalsystem und der charakteristischen Gleichung können wir die
homogene DGL 2. Ordnung vollständig lösen. Was noch fehlt, ist eine
partikuläre Lösung der **inhomogenen** DGL 2. Ordnung – und das Phänomen der
**Resonanz**. Beides behandeln wir im nächsten Abschnitt.
