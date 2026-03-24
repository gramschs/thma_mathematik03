# Grundwissen über gewöhnliche Differentialgleichungen

In diesem Kapitel lernen wir die grundlegenden Begriffe rund um gewöhnliche
Differentialgleichungen kennen. Wir klären, was eine Differentialgleichung ist,
wie sie klassifiziert wird und was unter einer Lösung zu verstehen ist.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie wissen, wie eine **gewöhnliche Differentialgleichung** (kurz: **gDGL**, englisch:
  *ordinary differential equation*, **ODE**) definiert ist, und können diese von
  Gleichungen unterscheiden, in denen eine Zahl oder ein Vektor gesucht wird.
* Sie können die **Ordnung** einer gDGL bestimmen und insbesondere zwischen einer
  gDGL **1. Ordnung** und einer gDGL **2. Ordnung** unterscheiden.
* Sie können zwischen der **impliziten** und der **expliziten** Darstellung einer
  gDGL unterscheiden.
* Sie wissen, was ein **Anfangswertproblem (AWP)** ist.
* Sie wissen, was ein **Randwertproblem (RWP)** ist.
* Sie wissen, dass nicht jede gDGL lösbar ist, und kennen die Eigenschaften, die
  eine Funktion erfüllen muss, um als Lösung einer gDGL zu gelten.
* Sie kennen den Unterschied zwischen einer **allgemeinen Lösung** und einer
  **partikulären Lösung** (auch: speziellen Lösung) einer gDGL.
```

## Gewöhnliche Differentialgleichung

```{admonition} Was ist ... eine gewöhnliche Differentialgleichung?
:class: note
Eine **gewöhnliche Differentialgleichung** ist eine Gleichung zur Bestimmung einer
unbekannten Funktion $y(x)$ einer reellen Variablen $x$, in welcher die $n$-te
Ableitung $y^{(n)}(x)$ und im Allgemeinen weitere niedrigere Ableitungen sowie
$y(x)$ selbst vorkommen.

Die höchste vorkommende Ableitung bestimmt die **Ordnung** der gDGL.
```

Ist die gDGL nach der höchsten Ableitung aufgelöst, heißt sie **explizit**:

$$y^{(n)}(x) = F\!\left(y^{(n-1)}(x),\, y^{(n-2)}(x),\, \ldots,\, y'(x),\, y(x),\, x\right).$$

Lässt sie sich in der Form

$$G\!\left(y^{(n)}(x),\, y^{(n-1)}(x),\, \ldots,\, y',\, y,\, x\right) = 0$$

schreiben, heißt sie **implizit**.

## Anfangswertproblem und Randwertproblem

```{admonition} Was ist ... ein Anfangswertproblem?
:class: note
Ein **Anfangswertproblem (AWP)** besteht aus einer gDGL der Ordnung $n$ und genau
$n$ Bedingungen in Form von Funktionswert und Ableitungen an *einer einzigen*
Stelle $x_0$:

$$y(x_0) = y_0,\quad y'(x_0) = y_1,\quad \ldots,\quad y^{(n-1)}(x_0) = y_{n-1}.$$
```

```{admonition} Was ist ... ein Randwertproblem?
:class: note
Ein **Randwertproblem (RWP)** besteht aus einer gDGL der Ordnung $n$ und genau
$n$ Bedingungen in Form von Funktionswert und Ableitungen an *mindestens zwei
verschiedenen* Stellen.
```

## Allgemeine und partikuläre Lösung

```{admonition} Was ist ... eine Lösung einer gDGL?
:class: note
Eine Funktion $y \colon I \to \mathbb{R}$ heißt **Lösung** der gDGL auf dem
Intervall $I \subset \mathbb{R}$, wenn $y(x)$ und die Ableitungen
$y^{(1)}, \ldots, y^{(n)}$ die gDGL für alle $x \in I$ erfüllen.

Die **allgemeine Lösung** enthält freie Konstanten. Werden diese durch
Anfangs- oder Randwerte festgelegt, erhält man eine **partikuläre Lösung**.
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir die grundlegenden Begriffe der Theorie gewöhnlicher
Differentialgleichungen kennengelernt: Definition und Ordnung einer gDGL, implizite
und explizite Darstellung, Anfangswert- und Randwertproblem sowie den Unterschied
zwischen allgemeiner und partikulärer Lösung. Im nächsten Kapitel lernen wir, wie
man Lösungskurven einer gDGL grafisch mithilfe von Richtungsfeldern darstellen kann.
