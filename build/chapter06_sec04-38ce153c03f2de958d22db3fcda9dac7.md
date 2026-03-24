# Separation der Variablen

Die **Separation der Variablen** (Trennung der Variablen) ist ein analytisches
Verfahren zur exakten Lösung gewöhnlicher Differentialgleichungen 1. Ordnung.
Im Gegensatz zu numerischen Näherungsverfahren liefert es eine geschlossene
Formel für die Lösungsfunktion.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie erkennen eine **separierbare** (trennbare) **gDGL 1. Ordnung** der Form
  $$y' = f(x) \cdot g(y).$$
* [ ] Sie beherrschen das Verfahren der **Separation der Variablen** und können
  damit eine separierbare gDGL 1. Ordnung lösen. Die vier Schritte sind:
  1. $y'$ formal durch $\dfrac{dy}{dx}$ ersetzen.
  2. Alle Terme in $y$ auf die linke, alle Terme in $x$ auf die rechte Seite
     bringen (unter der Annahme $g(y) \neq 0$):

     $$\frac{1}{g(y)}\, dy = f(x)\, dx.$$

  3. Beide Seiten **integrieren**:

     $$\int \frac{1}{g(y)}\, dy = \int f(x)\, dx.$$

  4. Falls möglich, die Gleichung nach $y$ auflösen (allgemeine Lösung).
     Den Fall $g(y) = 0$ gesondert untersuchen.

* [ ] Sie können eine gDGL der Form $y' = f(ax + by + c)$ mit $b \neq 0$ durch
  **Substitution** $u = ax + by + c$ auf eine separierbare DGL zurückführen
  und anschließend resubstituieren.
* [ ] Sie können eine gDGL der Form $y' = f\!\left(\dfrac{y}{x}\right)$ durch
  **Substitution** $u = \dfrac{y}{x}$ auf eine separierbare DGL zurückführen
  und anschließend resubstituieren.
```

## Separierbare Differentialgleichungen

```{admonition} Was ist ... eine separierbare gDGL?
:class: note
Eine gDGL 1. Ordnung heißt **separierbar** (trennbar), wenn sie sich als Produkt
einer Funktion in $x$ und einer Funktion in $y$ schreiben lässt:

$$y' = f(x) \cdot g(y).$$
```

## Separation der Variablen – Lösungsverfahren

Unter der Annahme $g(y) \neq 0$ lautet das Vorgehen:

$$\frac{dy}{dx} = f(x) \cdot g(y)
\;\;\Rightarrow\;\;
\frac{1}{g(y)}\, dy = f(x)\, dx
\;\;\Rightarrow\;\;
\int \frac{1}{g(y)}\, dy = \int f(x)\, dx + C, \quad C \in \mathbb{R}.$$

Den Fall $g(y) = 0$ prüft man separat: Gilt $g(y_0) = 0$ für ein $y_0$, so ist
$y \equiv y_0$ (konstante Funktion) eine mögliche weitere Lösung.

## Lösung durch Substitution

Für Gleichungen der Form $y' = f(ax + by + c)$ setzt man $u = ax + by + c$
und erhält nach Ableiten $u' = a + b \cdot y'$, woraus $y' = \frac{u'-a}{b}$
folgt. Einsetzen liefert eine neue separierbare DGL in $u$ und $x$. Nach dem
Lösen wird durch $y = \frac{1}{b}(u - ax - c)$ resubstituiert.

Für Gleichungen der Form $y' = f\!\left(\frac{y}{x}\right)$ setzt man
$u = \frac{y}{x}$, also $y = x \cdot u$, und erhält mit der Produktregel
$y' = u + x \cdot u'$. Einsetzen liefert eine separierbare DGL in $u$ und $x$.
Nach dem Lösen wird durch $y = u \cdot x$ resubstituiert.

## Zusammenfassung und Ausblick

Die Separation der Variablen ist das grundlegende analytische Lösungsverfahren
für separierbare gDGLn 1. Ordnung. Durch Substitution kann der Anwendungsbereich
auf weitere Klassen von Differentialgleichungen ausgedehnt werden. Im nächsten
Sprint lernen wir Methoden zur Lösung **linearer** gewöhnlicher
Differentialgleichungen kennen.
