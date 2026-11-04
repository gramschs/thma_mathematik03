---
authors:
  - name: Simone Gramsch
---

# 10.3 Konstante Koeffizienten

Mit der Lösungsformel aus Kapitel 10.2 können wir jede lineare DGL 1. Ordnung
lösen, sofern wir die Integrale berechnen können. In Kapitel 9.2 haben wir
lineare DGL mit konstanten Koeffizienten als besonders einfache Klasse
kennengelernt. In diesem Kapitel sehen wir, wie sich die Lösungsformel für sie
vereinfacht und dass wir die partikuläre Lösung dann oft sogar ganz ohne
Integral finden. Im Maschinenbau beschreiben solche DGL mit einer
periodischen rechten Seite etwa ein Bauteil, das im Takt einer Maschine
erwärmt wird.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können die Lösungsformel für lineare DGL mit konstanten
  Koeffizienten $y' + a\,y = g(x)$ angeben und anwenden, auch wenn dafür
  zweimal partiell integriert werden muss.
* [ ] Sie können mit dem **Ansatz vom Typ der rechten Seite** und einem
  **Koeffizientenvergleich** eine partikuläre Lösung bestimmen.
* [ ] Sie können den Ansatz passend zur Störfunktion wählen, auch wenn sie
  eine Summe oder ein Produkt ist.
* [ ] Sie erkennen den **Resonanzfall** und wissen, warum der Ansatz dann einen
  zusätzlichen Faktor $x$ braucht.
```

## Was vereinfacht sich für $y' + a\,y = g(x)$?

Ist der Koeffizient eine Konstante, also $f(x) = a$, dann ist
$\int a\,dx = ax$. Die homogene Lösung ist wie in Kapitel 9.3 die
Exponentialfunktion $A\,e^{-ax}$, und in der Lösungsformel aus Kapitel 10.2
werden die beiden Faktoren $e^{\int f(x)\,dx}$ und $e^{-\int f(x)\,dx}$ zu
$e^{ax}$ und $e^{-ax}$. Nur das Integral über die Störfunktion bleibt übrig.

<!-- markdownlint-disable -->
```{admonition} Was ist ... die Lösungsformel bei konstanten Koeffizienten?
:class: note
Die allgemeine Lösung der linearen DGL $y' + a\,y = g(x)$ mit einer
Konstanten $a$ ist

\begin{equation*}
y = \underbrace{A\,e^{-ax}}_{y_h} +
\underbrace{\left[\int g(x)\,e^{ax}\,dx\right] e^{-ax}}_{y_p},
\qquad A \in \mathbb{R}.
\end{equation*}
```
<!-- markdownlint-enable -->

Als erste Probe nehmen wir $y' + 2y = 4$ aus Kapitel 9. Mit $a = 2$ und
$g(x) = 4$ ist $\int 4\,e^{2x}\,dx = 2\,e^{2x}$, und mit dem Faktor $e^{-2x}$
ergibt sich $y_p = 2$. Die Formel findet also von selbst die
Gleichgewichtslösung, die wir in Kapitel 9.4 durch einen Versuch gefunden
haben. Als zweites Beispiel betrachten wir eine periodische Störfunktion:

\begin{equation*}
y' + 3y = -\cos(x).
\end{equation*}

Hier ist $a = 3$, und die homogene Lösung ist $y_h = A\,e^{-3x}$. Für $y_p$
brauchen wir das Integral $\int -\cos(x)\,e^{3x}\,dx$. Wir berechnen zunächst
$I = \int \cos(x)\,e^{3x}\,dx$ mit partieller Integration. Dabei leiten wir den
Kosinus ab und integrieren die Exponentialfunktion:

\begin{equation*}
I = \frac{1}{3}\cos(x)\,e^{3x} + \frac{1}{3}\int \sin(x)\,e^{3x}\,dx.
\end{equation*}

*Haben wir damit etwas gewonnen?* Auf den ersten Blick nicht, denn das neue
Integral ist genauso schwer wie das alte. Wir integrieren aber ein zweites Mal
partiell, wieder mit der Exponentialfunktion als dem Faktor, den wir
integrieren:

\begin{equation*}
\int \sin(x)\,e^{3x}\,dx = \frac{1}{3}\sin(x)\,e^{3x} - \frac{1}{3}\,I.
\end{equation*}

Jetzt taucht rechts wieder das gesuchte Integral $I$ auf. Setzen wir das
Ergebnis oben ein, erhalten wir eine Gleichung, die wir nach $I$ auflösen
können:

\begin{align*}
I &= \frac{1}{3}\cos(x)\,e^{3x} + \frac{1}{9}\sin(x)\,e^{3x} - \frac{1}{9}\,I \\
\Rightarrow\quad \frac{10}{9}\,I &=
\frac{1}{9}\,\big(3\cos(x) + \sin(x)\big)\,e^{3x} \\
\Rightarrow\quad I &= \frac{1}{10}\,\big(3\cos(x) + \sin(x)\big)\,e^{3x}.
\end{align*}

Das gesuchte Integral ist $-I$. Multiplizieren wir es mit $e^{-3x}$, kürzen
sich die Exponentialfunktionen, und es bleibt

\begin{equation*}
y_p = -\frac{3}{10}\cos(x) - \frac{1}{10}\sin(x).
\end{equation*}

Zur Probe ist $y_p' = \frac{3}{10}\sin(x) - \frac{1}{10}\cos(x)$ und
$3y_p = -\frac{9}{10}\cos(x) - \frac{3}{10}\sin(x)$. In der Summe heben sich
die Sinusterme auf, und von den Kosinustermen bleibt
$-\frac{10}{10}\cos(x) = -\cos(x)$. Die allgemeine Lösung ist also
$y = A\,e^{-3x} - \frac{3}{10}\cos(x) - \frac{1}{10}\sin(x)$.

## Wann ist der Ansatz vom Typ der rechten Seite schneller?

Die partikuläre Lösung von $y' + 3y = -\cos(x)$ besteht aus einem Sinus und
einem Kosinus mit demselben Argument $x$ wie die Störfunktion. *Hätten wir das
nicht schon vorher ahnen können?* Leiten wir eine Summe aus $\sin(x)$ und
$\cos(x)$ ab, erhalten wir wieder eine solche Summe, und wenn wir das Dreifache
der Funktion addieren, ändert sich daran nichts. Anders als der Koeffizient
$\frac{1}{x}$ in Kapitel 10.1 verändert ein konstanter Koeffizient die Bauart
einer Funktion nicht. Wir können deshalb mit zwei unbekannten Zahlen $C_1$ und
$C_2$ den Ansatz $y_p = C_1\sin(x) + C_2\cos(x)$ machen. Mit
$y_p' = C_1\cos(x) - C_2\sin(x)$ ergibt die linke Seite

\begin{equation*}
y_p' + 3y_p = (3C_1 - C_2)\sin(x) + (C_1 + 3C_2)\cos(x).
\end{equation*}

Das soll für alle $x$ gleich $-\cos(x) = 0 \cdot \sin(x) - 1 \cdot \cos(x)$
sein. Das gelingt, wenn die Faktoren vor $\sin(x)$ und vor $\cos(x)$ auf beiden
Seiten übereinstimmen. Diesen Schritt nennen wir **Koeffizientenvergleich**. Er
liefert das lineare Gleichungssystem

\begin{equation*}
\begin{pmatrix} 3 & -1 \\ 1 & 3 \end{pmatrix}
\begin{pmatrix} C_1 \\ C_2 \end{pmatrix} =
\begin{pmatrix} 0 \\ -1 \end{pmatrix}.
\end{equation*}

Die erste Zeile gehört zu $\sin(x)$, die zweite zu $\cos(x)$. Die
Determinante der Matrix ist $3 \cdot 3 - (-1) \cdot 1 = 10 \neq 0$. Nach
Kapitel 3.1 ist die Matrix also invertierbar, und nach Kapitel 2.4 hat das
System genau eine Lösung. Aus der ersten Zeile folgt
$C_2 = 3C_1$, eingesetzt in die zweite $10\,C_1 = -1$. Damit ist
$C_1 = -\frac{1}{10}$ und $C_2 = -\frac{3}{10}$, und wir erhalten dieselbe
partikuläre Lösung wie mit der Lösungsformel, nur ohne partielle Integration.
Einen Ansatz, der die Bauart der Störfunktion nachahmt, nennen wir **Ansatz vom
Typ der rechten Seite**.

<!-- markdownlint-disable MD013 -->
```{admonition} Welcher Ansatz passt zu welcher Störfunktion?
:class: note
Für die DGL $y' + a\,y = g(x)$ mit einer Konstanten $a$ finden wir eine
partikuläre Lösung mit dem folgenden Ansatz. Die Zahlen $C_0, C_1, \ldots$
bestimmen wir durch Einsetzen und Koeffizientenvergleich.

| Störfunktion $g(x)$ | Ansatz für $y_p$ |
| --- | --- |
| Polynom vom Grad $n$, nur für $a \neq 0$ | $C_nx^n + \ldots + C_1x + C_0$ |
| $\alpha\sin(\omega x) + \beta\cos(\omega x)$ | $C_1\sin(\omega x) + C_2\cos(\omega x)$ |
| $\alpha\,e^{bx}$ mit $b \neq -a$ | $C\,e^{bx}$ |

Der Ansatz für $\sin(\omega x)$ und $\cos(\omega x)$ enthält immer beide
Funktionen, auch wenn $\alpha$ oder $\beta$ null ist. Ist $g$ eine Summe
solcher Funktionen, ist der Ansatz die Summe der Ansätze. Ist $g$ ein Produkt,
ist der Ansatz das Produkt, etwa $(C_1x + C_0)\,e^{bx}$ für $x\,e^{bx}$.
```
<!-- markdownlint-enable MD013 -->

Mit dieser Tabelle lösen wir ein Versprechen aus Kapitel 9.4 ein. Dort haben
wir für $y' - y = x$ die partikuläre Lösung $-x - 1$ angegeben, ohne zu sagen,
wie wir darauf kommen. Die Störfunktion $g(x) = x$ ist ein Polynom vom Grad
$1$, und es ist $a = -1 \neq 0$. Der Ansatz lautet also $y_p = C_1x + C_0$, und
Einsetzen ergibt

\begin{equation*}
y_p' - y_p = C_1 - C_1x - C_0 = -C_1\,x + (C_1 - C_0) \stackrel{!}{=} x.
\end{equation*}

Der Koeffizientenvergleich vor $x$ liefert $-C_1 = 1$, der Vergleich der
Konstanten $C_1 - C_0 = 0$. Also ist $C_1 = C_0 = -1$ und $y_p = -x - 1$ wie in
Kapitel 9.4. Obwohl $g$ keinen konstanten Term hat, brauchen wir $C_0$ im
Ansatz, denn die Ableitung von $C_1x$ ist die Konstante $C_1$. Passt die
Störfunktion in die Tabelle, ist der Ansatz meist schneller als die
Lösungsformel, weil wir nur ableiten und ein Gleichungssystem lösen. Die
Lösungsformel brauchen wir bei variablen Koeffizienten und bei
Störfunktionen, die in keiner Zeile der Tabelle stehen.

<!-- markdownlint-disable MD013 -->
```{dropdown} Video "Lineare DGL 1. Ordnung mit konstanten Koeffizienten" von Prof. Hielscher (TH Mannheim)
<iframe width="927" height="588"
src="https://www.youtube.com/embed/AkJjvVmJuh8?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07"
title="Lineare DGL 1. Ordnung mit konstanten Koeffizienten" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

```{dropdown} Video "Lineare DGL 1. Ordnung, quadratischer Lösungsansatz" von Mathe mit Nina
<iframe width="927" height="521" src="https://www.youtube.com/embed/pyErs6V7lR0"
title="Lineare DGL 1. Ordnung, quadratischer Lösungsansatz" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```
<!-- markdownlint-enable MD013 -->

## Was passiert, wenn $g$ schon in $y_h$ steckt?

Wir ändern die rechte Seite und betrachten

\begin{equation*}
y' + 3y = e^{-3x}.
\end{equation*}

Die homogene Lösung ist wie im ersten Abschnitt $y_h = A\,e^{-3x}$. Würden wir
die Tabelle ohne die Bedingung $b \neq -a$ anwenden, versuchten wir
$y_p = C\,e^{-3x}$. Einsetzen ergibt aber
$-3C\,e^{-3x} + 3C\,e^{-3x} = 0$, für jede Wahl von $C$. Die rechte Seite
$e^{-3x}$ erreichen wir so nie. *Warum versagt der Ansatz ausgerechnet hier?*
Die Funktion $C\,e^{-3x}$ ist eine homogene Lösung, und die ergibt nach
Kapitel 9.4 auf der linken Seite immer null. Hier ist $b = -3 = -a$, und genau
diesen Fall schließt die Tabelle aus.

Die Lösungsformel kommt dagegen ohne Raten aus. Mit $a = 3$ ist

\begin{equation*}
\int e^{-3x}\,e^{3x}\,dx = \int 1\,dx = x
\quad\Rightarrow\quad
y_p = x\,e^{-3x}.
\end{equation*}

Die beiden Exponentialfunktionen heben sich im Integral auf, und wir
integrieren nur noch die Zahl $1$. Zur Probe ist
$y_p' = e^{-3x} - 3x\,e^{-3x}$, und zusammen mit $3y_p = 3x\,e^{-3x}$ bleibt
$e^{-3x}$. Die allgemeine Lösung lautet $y = (A + x)\,e^{-3x}$. Dass der Faktor
$x$ entsteht, ist kein Zufall. Für eine Störfunktion $g(x) = \alpha\,e^{bx}$
liefert die Formel das Integral $\int \alpha\,e^{(a + b)x}\,dx$. Für
$a + b \neq 0$ ist es $\frac{\alpha}{a + b}\,e^{(a + b)x}$, und nach dem
Multiplizieren mit $e^{-ax}$ bleibt $y_p = \frac{\alpha}{a + b}\,e^{bx}$. Das
ist genau der Ansatz $C\,e^{bx}$ aus der Tabelle, sogar mit fertig berechnetem
$C$. Für $a + b = 0$ dürfen wir nicht durch $a + b$ teilen. Dann ist der
Integrand die Konstante $\alpha$, das Integral ist $\alpha\,x$, und es folgt
$y_p = \alpha\,x\,e^{bx}$.

```{admonition} Was ist ... der Resonanzfall?
:class: note
Ist bei der DGL $y' + a\,y = \alpha\,e^{bx}$ der Exponent $b = -a$, dann ist
die Störfunktion selbst eine Lösung der homogenen DGL. Diesen Fall nennen wir
den **Resonanzfall**. Der Ansatz $C\,e^{bx}$ versagt, und wir verwenden
stattdessen den Ansatz

\begin{equation*}
y_p = C\,x\,e^{bx}.
\end{equation*}
```

Prüfen wir den Ansatz an $y' + 3y = e^{-3x}$. Mit $y_p = C\,x\,e^{-3x}$ ist
$y_p' = C\,e^{-3x} - 3C\,x\,e^{-3x}$, und beim Addieren von
$3y_p = 3C\,x\,e^{-3x}$ fallen die Terme mit $x$ weg. Es bleibt
$C\,e^{-3x} = e^{-3x}$, also $C = 1$, wie mit der Lösungsformel. Dieselbe
Ursache steckt hinter der Bedingung $a \neq 0$ in der ersten Zeile der
Tabelle. Für $a = 0$ lautet die DGL $y' = g(x)$, und ihre homogene Lösung ist
die Konstante $A$. Der Polynomansatz enthält mit $C_0$ also schon eine
homogene Lösung. Bei $y' = x$ führt der Ansatz $C_1x + C_0$ auf die Gleichung
$C_1 = x$, die für kein $C_1$ gilt. Stattdessen integrieren wir wie in Kapitel
8.1 direkt und erhalten $y = \frac{x^2}{2} + A$. Der Grad steigt dabei um eins,
so wie beim Resonanzfall ein Faktor $x$ hinzukommt.

## Zusammenfassung und Ausblick

Bei konstanten Koeffizienten vereinfacht sich die Lösungsformel zu
$y = A\,e^{-ax} + \left[\int g(x)\,e^{ax}\,dx\right] e^{-ax}$. Für
$y' + 3y = -\cos(x)$ verlangt sie zwei partielle Integrationen, der Ansatz
$C_1\sin(x) + C_2\cos(x)$ führt dagegen mit einem Koeffizientenvergleich auf
ein Gleichungssystem und dieselbe Lösung
$y_p = -\frac{3}{10}\cos(x) - \frac{1}{10}\sin(x)$. Der Ansatz vom Typ der
rechten Seite ist deshalb meist schneller, er funktioniert aber nur für die
Störfunktionen aus der Tabelle. Im Resonanzfall $b = -a$ steckt die
Störfunktion schon in $y_h$, und der Ansatz braucht einen zusätzlichen Faktor
$x$, den die Lösungsformel von selbst liefert. In Kapitel 10.4 ordnen wir alle
Verfahren für DGL 1. Ordnung und üben, das passende auszuwählen. Den Ansatz vom
Typ der rechten Seite und den Resonanzfall treffen wir in Kapitel 12 bei
linearen DGL 2. Ordnung wieder, wo der Faktor $x$ dazu führt, dass die
Ausschläge einer Schwingung immer größer werden.
