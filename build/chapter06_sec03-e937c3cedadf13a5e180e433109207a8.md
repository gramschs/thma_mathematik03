# Numerisches Lösen – Das Euler-Verfahren

Analytische Lösungsformeln existieren nicht für jede gewöhnliche
Differentialgleichung. In solchen Fällen liefert das **explizite Euler-Verfahren**
(Polygonzugverfahren) eine näherungsweise numerische Lösung in Form einer
Wertetabelle.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können die **Herleitung des Polygonzugverfahrens** von Euler nachvollziehen:
  Der Differenzenquotient wird als Näherung für die Ableitung in der gDGL
  eingesetzt, woraus die Rekursionsformel folgt.
* [ ] Sie beherrschen das **explizite Euler-Verfahren** und können damit
  näherungsweise eine gDGL 1. Ordnung mit Anfangsbedingung lösen. Dazu wenden
  Sie die Rekursionsformel
  $$x_{n+1} = x_n + h, \qquad y_{n+1} = y_n + h \cdot F(x_n, y_n)$$
  schrittweise an.
* [ ] Sie sind in der Lage, die **numerische Lösungskurve** (Polygonzug) zu
  skizzieren und mit der exakten Lösungskurve zu vergleichen.
* [ ] Sie kennen die **Schwächen des Euler-Verfahrens** und können diese erläutern:
  * Es treten **akkumulierende Fehler** auf; die Genauigkeit nimmt mit
    wachsender Schrittweite $h$ ab.
  * Bei **senkrechten Tangenten** versagt das Verfahren, da dort die Steigung
    nicht mehr endlich ist.
```

## Das Polygonzugverfahren

Gegeben sei ein Anfangswertproblem der Form

$$y' = F(x, y), \qquad y(x_0) = y_0.$$

Die Grundidee des Euler-Verfahrens ist, die Ableitung $y'$ durch den
Differenzenquotient zu ersetzen:

$$y' \approx \frac{y_{n+1} - y_n}{x_{n+1} - x_n}.$$

Einsetzen und Umformen liefert die **Rekursionsformel**:

$$x_{n+1} = x_n + h, \qquad y_{n+1} = y_n + h \cdot F(x_n, y_n),$$

wobei $h = x_{n+1} - x_n$ die konstante **Schrittweite** ist.

```{admonition} Was ist ... das explizite Euler-Verfahren?
:class: note
Das **explizite Euler-Verfahren** (Polygonzugverfahren) berechnet ausgehend vom
Startpunkt $(x_0, y_0)$ schrittweise Näherungswerte $(x_n, y_n)$ der
Lösungskurve mithilfe der Rekursionsformel

$$x_{n+1} = x_n + h, \qquad y_{n+1} = y_n + h \cdot F(x_n, y_n).$$

Je kleiner die Schrittweite $h$ und je weniger die Lösungskurve $y(x)$ gekrümmt
ist, desto genauer ist die Näherung.
```

## Zusammenfassung und Ausblick

Das Euler-Verfahren ist das einfachste numerische Verfahren zur Lösung von
Anfangswertproblemen. Es veranschaulicht das Grundprinzip numerischer
Integrationsverfahren, hat jedoch aufgrund akkumulierender Fehler nur begrenzte
Genauigkeit. Im nächsten Kapitel wenden wir uns analytischen Methoden zu: der
**Separation der Variablen**.
