---
authors:
  - name: Simone Gramsch
---

# 9.1 Variation der Konstanten: aus einer Konstante wird eine Funktion

In Abschnitt 8.3 haben wir die partikuläre Lösung einer inhomogenen linearen ODE durch
den Ansatz vom Typ der rechten Seite gewonnen: Wir erraten die Form von $y_p$ aus der
Störfunktion und bestimmen die Koeffizienten durch Vergleich. Das Verfahren ist schnell,
aber begrenzt: Es setzt konstante Koeffizienten voraus und funktioniert nur, wenn die
Störfunktion in die Ansatztabelle passt. Sobald der Koeffizient $f(x)$ von $x$ abhängt,
gibt es keine Ansatztabelle mehr, die systematisch greift. Wir brauchen ein universelles
Verfahren. Die **Variation der Konstanten** liefert es: Sie berechnet $y_p$ aus $y_h$
heraus, ohne dass wir die Form der Lösung vorher kennen müssen, und funktioniert für
beliebige Störfunktionen und beliebige Koeffizienten $f(x)$.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie kennen die Notation $y_h$, $y_p$ und $y_{\text{allgemein}}$ für die Lösungen
  einer linearen inhomogenen ODE 1. Ordnung und wissen, welche Rolle jede Lösung spielt.
* [ ] Sie wissen, dass sich die allgemeine Lösung der inhomogenen linearen ODE
  $y' + f(x) \cdot y = g(x)$ als Summe
  \begin{equation*}
  y_{\text{allgemein}}(x) = y_h(x) + y_p(x)
  \end{equation*}
  aus homogener Lösung und partikulärer Lösung zusammensetzt.
* [ ] Sie beherrschen das **Verfahren der Variation der Konstanten**: Sie ersetzen die
  Konstante $A$ in $y_h$ durch eine Funktion $A(x)$ und bestimmen $A(x)$ durch Einsetzen
  in die ODE.
* [ ] Sie können die allgemeine Lösungsformel
  \begin{equation*}
  y_{\text{allgemein}}(x) = A \cdot e^{-\int f(x)\,dx}
    + \left[\int g(x)\,e^{\int f(x)\,dx}\,dx\right] e^{-\int f(x)\,dx}
  \end{equation*}
  auf eine gegebene lineare inhomogene ODE 1. Ordnung anwenden.
```

## Wann stößt der Ansatz vom Typ der rechten Seite an seine Grenzen?

Wir betrachten die ODE

\begin{equation*}
y' + \frac{1}{x}\,y = x.
\end{equation*}

Die Störfunktion $g(x) = x$ ist ein Polynom ersten Grades; laut Ansatztabelle aus
Abschnitt 8.3 würden wir $y_p = Ax + B$ versuchen. Wir leiten ab und setzen ein:

\begin{equation*}
A + \frac{1}{x}(Ax + B) = A + A + \frac{B}{x} = 2A + \frac{B}{x}
\stackrel{!}{=} x.
\end{equation*}

Ein Koeffizientenvergleich scheitert: Auf der linken Seite stehen Terme mit $x^0$ und
$x^{-1}$, auf der rechten Seite steht $x^1$. Kein Wahl von $A$ und $B$ bringt diese
Seiten zur Übereinstimmung. Der variable Koeffizient $1/x$ erzeugt beim Einsetzen neue
Terme, die der Ansatz nicht vorgesehen hat.

*Was ist der Ausweg?* Die Idee der Variation der Konstanten: Statt die Form von $y_p$
zu erraten, bauen wir sie systematisch aus der bereits bekannten homogenen Lösung $y_h$.

## Die Idee: aus einer Konstante wird eine Funktion

Als erstes bestimmen wir $y_h$. Mit $f(x) = 1/x$ und $\int \frac{1}{x}\,dx = \ln x$
(für $x > 0$) liefert die Formel aus Abschnitt 8.2:

\begin{equation*}
y_h(x) = A\,e^{-\ln x} = \frac{A}{x}, \quad A \in \mathbb{R}.
\end{equation*}

Die Funktion $y_h = A/x$ erfüllt die homogene Gleichung $y' + \frac{1}{x}y = 0$ für
jedes konstante $A$. Der entscheidende Gedanke der Variation der Konstanten: *Darf $A$
auch von $x$ abhängen?* Wir ersetzen die Konstante $A$ durch eine noch unbekannte
Funktion $A(x)$ und machen den Ansatz:

\begin{equation*}
y_p(x) = \frac{A(x)}{x}.
\end{equation*}

Wenn wir $A(x)$ so wählen, dass $y_p$ die inhomogene Gleichung erfüllt, haben wir die
partikuläre Lösung gefunden. Die freie Funktion $A(x)$ übernimmt damit die Rolle, die
in 8.3 der Ansatzkoeffizient spielte — aber jetzt ohne Einschränkung auf bestimmte
Typen der Störfunktion.

## Das Verfahren Schritt für Schritt

**Schritt 1: $y_p$ ableiten.** Mit der Quotientenregel:

\begin{equation*}
y_p'(x) = \frac{A'(x) \cdot x - A(x) \cdot 1}{x^2}
         = \frac{A'(x)}{x} - \frac{A(x)}{x^2}.
\end{equation*}

**Schritt 2: In die ODE einsetzen.**

\begin{align*}
y_p' + \frac{1}{x}\,y_p
  &= \frac{A'(x)}{x} - \frac{A(x)}{x^2} + \frac{1}{x} \cdot \frac{A(x)}{x} \\
  &= \frac{A'(x)}{x} - \frac{A(x)}{x^2} + \frac{A(x)}{x^2} \\
  &= \frac{A'(x)}{x}.
\end{align*}

Die Terme mit $A(x)$ heben sich auf. Das ist kein Zufall: Es liegt daran, dass $A(x)/x$
die homogene Gleichung erfüllt, also $y_h' + \frac{1}{x}y_h = 0$ gilt. Übrig bleibt
nur der Term mit $A'(x)$.

**Schritt 3: Bestimmungsgleichung für $A'(x)$ aufstellen.** Die ODE fordert:

\begin{equation*}
\frac{A'(x)}{x} \stackrel{!}{=} x
\quad \Rightarrow \quad
A'(x) = x^2.
\end{equation*}

**Schritt 4: $A(x)$ durch Integration bestimmen.**

\begin{equation*}
A(x) = \int x^2\,dx = \frac{x^3}{3} + C, \quad C \in \mathbb{R}.
\end{equation*}

**Schritt 5: Allgemeine Lösung aufschreiben.**

<!-- markdownlint-disable -->
\begin{equation*}
y_{\text{allgemein}}(x) = \frac{A(x)}{x}
  = \frac{\dfrac{x^3}{3} + C}{x}
  = \underbrace{\frac{C}{x}}_{= \,y_h} + \underbrace{\frac{x^2}{3}}_{= \,y_p}.
\end{equation*}
<!-- markdownlint-enable -->

Die Integrationskonstante $C$ erzeugt wieder den homogenen Anteil $y_h = C/x$; der
verbleibende Term $y_p = x^2/3$ ist die partikuläre Lösung.

**Verifikation.** Mit $y' = -C/x^2 + 2x/3$:

\begin{align*}
y' + \frac{1}{x}\,y
  &= \left(-\frac{C}{x^2} + \frac{2x}{3}\right) +
     \frac{1}{x}\left(\frac{C}{x} + \frac{x^2}{3}\right) \\
  &= -\frac{C}{x^2} + \frac{2x}{3} + \frac{C}{x^2} + \frac{x}{3} \\
  &= x. \quad \checkmark
\end{align*}

## Die allgemeine Lösungsformel

Das Verfahren, das wir gerade am Beispiel durchgeführt haben, gilt für jede
lineare ODE 1. Ordnung $y' + f(x)\,y = g(x)$. Wir setzen allgemein $y_p =
A(x)\,e^{-\int f\,dx}$ in die ODE ein. Die Terme mit $A(x)$ heben sich stets auf
(aus demselben Grund wie im Beispiel), und es verbleibt:

\begin{equation*}
A'(x)\,e^{-\int f\,dx} = g(x)
\quad \Rightarrow \quad
A'(x) = g(x)\,e^{\int f(x)\,dx}.
\end{equation*}

Integration liefert $A(x) = \int g(x)\,e^{\int f(x)\,dx}\,dx + C$.
Einsetzen in $y_p = A(x)\,e^{-\int f\,dx}$ ergibt die allgemeine Lösung:

```{admonition} Was ist ... die Lösungsformel der Variation der Konstanten?
:class: note
Die allgemeine Lösung der linearen ODE 1. Ordnung $y' + f(x)\,y = g(x)$ lautet

\begin{equation*}
y_{\text{allgemein}}(x)
  = \underbrace{A\,e^{-\int f(x)\,dx}}_{y_h}
  + \underbrace{\left[\int g(x)\,e^{\int f(x)\,dx}\,dx\right]
    e^{-\int f(x)\,dx}}_{y_p},
  \quad A \in \mathbb{R}.
\end{equation*}

Das Verfahren heißt **Variation der Konstanten**, weil die Konstante $A$ in
$y_h$ durch die Funktion $A(x) = \int g(x)\,e^{\int f(x)\,dx}\,dx$ ersetzt wird.
```

Wir prüfen die Formel an unserem Beispiel. Mit $f(x) = 1/x$ gilt
$e^{\int f\,dx} = e^{\ln x} = x$ und $e^{-\int f\,dx} = 1/x$. Einsetzen:

\begin{equation*}
y_{\text{allgemein}}
  = \frac{A}{x} + \left[\int x \cdot x\,dx\right] \cdot \frac{1}{x}
  = \frac{A}{x} + \frac{x^3/3}{x}
  = \frac{A}{x} + \frac{x^2}{3}.
\end{equation*}

Das stimmt exakt mit dem schrittweise hergeleiteten Ergebnis überein.

## Zusammenfassung und Ausblick

Die Variation der Konstanten löst jede lineare ODE 1. Ordnung $y' + f(x)\,y =
g(x)$, unabhängig davon, ob $f(x)$ konstant oder variabel ist und unabhängig von
der Form der Störfunktion $g(x)$. Der Schlüssel ist die Ersetzung der Konstante
$A$ in $y_h$ durch eine Funktion $A(x)$, die aus einem einzigen Integral
bestimmt wird. Am Beispiel $y' + \frac{1}{x}\,y = x$ haben wir gesehen, wie der
variable Koeffizient den Ansatz vom Typ der rechten Seite zum Scheitern bringt,
während die Variation der Konstanten direkt zur Lösung $C/x + x^2/3$ führt.

In Abschnitt 9.2 kehren wir zu linearen ODEs mit konstanten Koeffizienten zurück
und untersuchen den Resonanzfall: Wenn die Störfunktion $g(x)$ dieselbe
Exponentialform hat wie $y_h$, versagt der Standardansatz aus Abschnitt 8.3, und
die Variation der Konstanten liefert automatisch den richtigen modifizierten
Ansatz $y_p = C\,x\,e^{bx}$.
