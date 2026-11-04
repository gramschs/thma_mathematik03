---
authors:
  - name: Simone Gramsch
---

# 10.2 Die Lösungsformel

In Kapitel 10.1 haben wir mit der Variation der Konstanten eine partikuläre
Lösung von $y' + \frac{1}{x}\,y = x$ berechnet. Bei beiden Beispielen sind wir
dieselben vier Schritte gegangen, und am Ende stand jedes Mal ein Integral für
$A(x)$. In diesem Kapitel fassen wir die Schritte zu einer einzigen Formel
zusammen, legen die freie Konstante mit einer Anfangsbedingung fest und sehen,
dass die Formel sogar bei manchen nichtlinearen DGL hilft. Im Maschinenbau ist
meist ein Anfangszustand bekannt, etwa die Temperatur eines Bauteils zu Beginn
eines Versuchs, und gesucht ist der Verlauf danach.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können die **Lösungsformel** für lineare DGL 1. Ordnung
  $y' + f(x)\,y = g(x)$ aus der Variation der Konstanten herleiten und
  anwenden.
* [ ] Sie wissen, warum die Integrale in der Lösungsformel ohne
  Integrationskonstanten auskommen.
* [ ] Sie können ein Anfangswertproblem für eine lineare DGL 1. Ordnung lösen
  und das Intervall der Lösung angeben.
* [ ] Sie können eine nichtlineare DGL mit der Substitution $z = y^2$ in eine
  lineare DGL überführen und lösen.
```

## Wie lautet die Formel für beliebige Koeffizienten?

Am Ende von Kapitel 10.1 stand für eine beliebige lineare DGL
$y' + f(x)\,y = g(x)$ die Gleichung $A'(x) = g(x)\,e^{\int f(x)\,dx}$.
Integrieren liefert $A(x)$, und zusammen mit dem Ansatz
$y_p = A(x) \cdot e^{-\int f(x)\,dx}$ erhalten wir

\begin{equation*}
y_p = \left[\int g(x)\,e^{\int f(x)\,dx}\,dx\right] e^{-\int f(x)\,dx}.
\end{equation*}

In der eckigen Klammer steht die Funktion $A(x)$, dahinter die Funktion
$y_1 = e^{-\int f(x)\,dx}$ aus der homogenen Lösung. Addieren wir die homogene
Lösung $y_h = A\,e^{-\int f(x)\,dx}$, haben wir die allgemeine Lösung in einer
einzigen Formel. Die vier Schritte aus Kapitel 10.1 sind darin schon
ausgeführt, wir müssen nur noch die Integrale berechnen.

*Müssen wir bei den Integralen Integrationskonstanten addieren?* In der Formel
stehen zwei Arten von Integralen, das innere $\int f(x)\,dx$ im Exponenten und
das äußere über $g(x)\,e^{\int f(x)\,dx}$. Für das innere Integral gilt
dasselbe wie in Kapitel 9.3. Ersetzen wir die Stammfunktion $F$ durch $F + K$
mit einer Zahl $K$, wird aus $e^{F}$ der Ausdruck $e^{K}\,e^{F}$ und aus
$e^{-F}$ der Ausdruck $e^{-K}\,e^{-F}$. In $y_p$ kommen beide vor, und wegen
$e^{K} \cdot e^{-K} = 1$ hebt sich die Zahl $K$ heraus. Die Konstante des
äußeren Integrals würde dagegen wie in Kapitel 10.1 ein Vielfaches von $y_1$
erzeugen, also einen Teil der homogenen Lösung. Weil wir $y_h$ ohnehin
addieren, lassen wir auch sie weg.

<!-- markdownlint-disable -->
```{admonition} Was ist ... die Lösungsformel für lineare DGL 1. Ordnung?
:class: note
Die allgemeine Lösung der linearen DGL $y' + f(x)\,y = g(x)$ ist

\begin{equation*}
y = \underbrace{A\,e^{-\int f(x)\,dx}}_{y_h} +
\underbrace{\left[\int g(x)\,e^{\int f(x)\,dx}\,dx\right]
e^{-\int f(x)\,dx}}_{y_p}, \qquad A \in \mathbb{R}.
\end{equation*}

Für die Integrale genügt jeweils irgendeine Stammfunktion, eine
Integrationskonstante ist nicht nötig.
```
<!-- markdownlint-enable -->

Für unser Beispiel $y' + \frac{1}{x}\,y = x$ ist $f(x) = \frac{1}{x}$ und
$g(x) = x$. Eine Stammfunktion von $f$ ist $\ln|x|$, auf dem Intervall $x > 0$
also $\ln(x)$. Damit ist $e^{\int f(x)\,dx} = e^{\ln(x)} = x$ und
$e^{-\int f(x)\,dx} = \frac{1}{x}$. Die Lösungsformel ergibt

\begin{equation*}
y = \frac{A}{x} + \left[\int x \cdot x\,dx\right] \cdot \frac{1}{x}
= \frac{A}{x} + \frac{x^3}{3} \cdot \frac{1}{x}
= \frac{A}{x} + \frac{x^2}{3},
\end{equation*}

also dieselbe allgemeine Lösung wie in Kapitel 10.1. Für $x < 0$ ist
$e^{\ln|x|} = |x| = -x$, dann ist das Integral $\int x \cdot (-x)\,dx =
-\frac{x^3}{3}$, und der Faktor dahinter ist $-\frac{1}{x}$. Das Produkt ist
wieder $\frac{x^2}{3}$, das Vorzeichen verschwindet wie in Kapitel 9.3. Bei
diesem Beispiel gibt es außerdem eine kurze Kontrolle. In der ursprünglichen
Form $x\,y' + y = x^2$ ist die linke Seite nach der Produktregel die Ableitung
$(x\,y)'$. Aus $(x\,y)' = x^2$ folgt durch Integrieren $x\,y = \frac{x^3}{3} +
A$, und Teilen durch $x$ liefert wieder $y = \frac{A}{x} + \frac{x^2}{3}$.

```{dropdown} Video "Lineare Differentialgleichung (DGL) 1. Ordnung" von MathePeter
<iframe width="927" height="521" src="https://www.youtube.com/embed/qwJPZHmNcIs"
title="Lineare Differentialgleichung (DGL) 1. Ordnung" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

## Wie legt ein Anfangswert die Konstante fest?

Die allgemeine Lösung $y = \frac{A}{x} + \frac{x^2}{3}$ ist eine Schar von
Funktionen. Wie in Kapitel 8.2 wählen wir mit einer Anfangsbedingung eine
einzelne Lösung aus. Wir verlangen, dass die Lösung durch den Punkt $(1, 0)$
geht, also $y(1) = 0$. Die Bedingung setzen wir wie in Kapitel 9.4 in die
allgemeine Lösung ein, also in die Summe $y_h + y_p$:

\begin{equation*}
y(1) = \frac{A}{1} + \frac{1^2}{3} = A + \frac{1}{3} = 0
\quad\Rightarrow\quad
A = -\frac{1}{3}.
\end{equation*}

Die Lösung des Anfangswertproblems ist damit

\begin{equation*}
y = \frac{x^2}{3} - \frac{1}{3x} = \frac{x^3 - 1}{3x}.
\end{equation*}

Zur Probe ist $y(1) = \frac{1 - 1}{3} = 0$. Für die DGL leiten wir ab,
$y' = \frac{2x}{3} + \frac{1}{3x^2}$, und mit
$\frac{1}{x}\,y = \frac{x}{3} - \frac{1}{3x^2}$ ergibt die linke Seite
$\frac{2x}{3} + \frac{x}{3} = x$. Hätten wir die Bedingung nur in $y_h$
eingesetzt, wäre $A = 0$ herausgekommen, und die Funktion $\frac{x^2}{3}$ hat
an der Stelle $1$ den Wert $\frac{1}{3}$ und nicht $0$.

*Auf welchem Intervall gilt diese Lösung?* Die DGL ist an der Stelle $x = 0$
nicht definiert, denn dort müssten wir durch null teilen. Eine Lösung lebt
deshalb wie in Kapitel 8.1 auf einem Intervall, das die Stelle $0$ nicht
enthält. Weil die Anfangsstelle $x_0 = 1$ positiv ist, ist unsere Lösung auf
dem Intervall $x > 0$ definiert. Eine Anfangsbedingung an einer negativen
Stelle würde eine Lösung für $x < 0$ festlegen, und an der Stelle $0$ selbst
können wir gar keine Anfangsbedingung vorgeben. Ansonsten läuft durch jeden
Punkt $(x_0, y_0)$ genau eine Lösung, denn die Gleichung
$\frac{A}{x_0} + \frac{x_0^2}{3} = y_0$ hat für $x_0 \neq 0$ immer genau eine
Lösung $A$.

```{figure} pics/kurvenschar_variable_koeffizienten.svg
---
name: kurvenschar_variable_koeffizienten
---
Darstellung einiger Lösungen von $y' + \frac{1}{x}\,y = x$ für $x > 0$, die
sich alle der Parabel $y = \frac{x^2}{3}$ nähern.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Die Abbildung zeigt, wie sich die Lösungen für große $x$ der partikulären
Lösung $\frac{x^2}{3}$ nähern, denn der Anteil $\frac{A}{x}$ wird immer
kleiner. Das erinnert an die Gleichgewichtslösung aus Kapitel 9.4, nur dass
die Lösungen hier keiner Konstanten folgen, sondern einer Parabel. In der Nähe
von $x = 0$ verhalten sie sich dagegen ganz verschieden. Für $A > 0$ wachsen
sie über alle Grenzen, für $A < 0$ fallen sie, und nur die partikuläre Lösung
mit $A = 0$ bleibt beschränkt. Hervorgehoben ist die Lösung zu $y(1) = 0$ mit
$A = -\frac{1}{3}$.

## Wie wird eine nichtlineare DGL durch Substitution linear?

In Kapitel 9.1 haben wir mit einer Substitution aus einer DGL, die sich nicht
trennen ließ, eine trennbare DGL gemacht. Dieselbe Idee hilft manchmal auch,
eine nichtlineare DGL in eine lineare zu verwandeln. Wir betrachten

\begin{equation*}
2x\,y\,y' + y^2 = x^2, \qquad x > 0.
\end{equation*}

Nach Kapitel 9.2 ist diese DGL nichtlinear, denn $y$ und $y'$ werden
miteinander multipliziert, und $y$ kommt quadriert vor. *Fällt an den beiden
Termen $y\,y'$ und $y^2$ etwas auf?* Nach der Kettenregel ist die Ableitung von
$y^2$ gleich $2\,y\,y'$. Der Term $2\,y\,y'$ ist also die Ableitung von $y^2$.
Wir führen deshalb wie in Kapitel 9.1 eine neue Funktion ein:

\begin{equation*}
z = y^2, \qquad z' = 2\,y\,y'.
\end{equation*}

Damit wird $2x\,y\,y'$ zu $x\,z'$ und $y^2$ zu $z$, und die DGL lautet
$x\,z' + z = x^2$. Das ist unsere DGL aus Kapitel 9.2 und 10.1, nur mit $z$
statt $y$. Die Substitution hat die nichtlineare DGL also in eine lineare
verwandelt, deren allgemeine Lösung wir kennen:

\begin{equation*}
z = \frac{A}{x} + \frac{x^2}{3}, \qquad A \in \mathbb{R}.
\end{equation*}

Gesucht ist aber $y$. Bei der Resubstitution müssen wir aus $y^2 = z$ die
Wurzel ziehen, und dafür gibt es zwei Möglichkeiten,
$y = \sqrt{z}$ und $y = -\sqrt{z}$. Außerdem ist die Wurzel nur dort
definiert, wo $z$ nicht negativ ist.

```{admonition} Wie macht die Substitution $z = y^2$ eine DGL linear?
:class: note
Kommt die gesuchte Funktion $y$ in einer DGL 1. Ordnung nur in den Termen
$y\,y'$ und $y^2$ vor, jeweils mit Faktoren, die nur von $x$ abhängen, gehen
wir in vier Schritten vor:

1. Wir substituieren $z = y^2$ und ersetzen $y\,y'$ durch $\frac{1}{2}\,z'$.
2. Wir bringen die lineare DGL für $z$ in die Form $z' + f(x)\,z = g(x)$.
3. Wir lösen sie mit der Lösungsformel.
4. Wir resubstituieren $y = \pm\sqrt{z}$. Das Vorzeichen legt die
   Anfangsbedingung fest, und die Lösung existiert nur, wo $z$ positiv ist.
```

Im Beispiel sind die ersten drei Schritte erledigt. Für den vierten geben wir
die Anfangsbedingung $y(1) = -1$ vor. Wegen $z = y^2$ gilt dann $z(1) = 1$, und
aus $A + \frac{1}{3} = 1$ folgt $A = \frac{2}{3}$, also

\begin{equation*}
z = \frac{2}{3x} + \frac{x^2}{3} = \frac{x^3 + 2}{3x}.
\end{equation*}

Für $x > 0$ ist $z$ positiv. Weil die Anfangsbedingung einen negativen Wert
verlangt, wählen wir wie bei $y\,y' = \cos(x)$ in Kapitel 8.4 die negative
Wurzel:

\begin{equation*}
y = -\sqrt{\frac{x^3 + 2}{3x}}, \qquad x > 0.
\end{equation*}

Zur Probe ist $y(1) = -\sqrt{\frac{3}{3}} = -1$. Für die DGL nutzen wir
$y^2 = z$ und $2\,y\,y' = z'$. Die linke Seite $2x\,y\,y' + y^2$ ist damit
gleich $x\,z' + z$, und weil $z$ die lineare DGL löst, ist das $x^2$. Hätte
die Anfangsbedingung $y(1) = 1$ gelautet, wäre $z$ dasselbe gewesen, und nur
das Vorzeichen der Wurzel hätte sich geändert.

## Zusammenfassung und Ausblick

Die Variation der Konstanten lässt sich zu einer Lösungsformel zusammenfassen.
Die allgemeine Lösung von $y' + f(x)\,y = g(x)$ ist
$A\,e^{-\int f(x)\,dx} + \left[\int g(x)\,e^{\int f(x)\,dx}\,dx\right]
e^{-\int f(x)\,dx}$, und für beide Integrale genügt eine Stammfunktion ohne
Konstante. Eine Anfangsbedingung setzen wir in diese allgemeine Lösung ein,
und die Lösung lebt auf dem Intervall, das die Anfangsstelle enthält. Für
$y' + \frac{1}{x}\,y = x$ mit $y(1) = 0$ ergibt sich
$y = \frac{x^3 - 1}{3x}$ für $x > 0$. Mit der Substitution $z = y^2$ wird
außerdem aus einer nichtlinearen DGL wie $2x\,y\,y' + y^2 = x^2$ eine lineare.
In Kapitel 10.3 sehen wir, wie einfach die Formel bei konstanten Koeffizienten
wird und wann es dann einen noch schnelleren Weg gibt. Bei linearen DGL
2. Ordnung ab Kapitel 11 enthält die allgemeine Lösung zwei Konstanten, und
wir brauchen zwei Bedingungen, um sie festzulegen.
