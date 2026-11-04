---
authors:
  - name: Simone Gramsch
---

# 10.1 Variation der Konstanten

In Kapitel 9.4 haben wir gesehen, dass sich die allgemeine Lösung einer
inhomogenen linearen DGL aus der homogenen Lösung und einer einzigen
partikulären Lösung zusammensetzt. Bei $y' + 2y = 4$ war diese partikuläre
Lösung eine Konstante, die wir durch einen einfachen Versuch gefunden haben.
In diesem Kapitel lernen wir ein Verfahren kennen, das die partikuläre Lösung
nicht errät, sondern aus der homogenen Lösung berechnet. Im Maschinenbau
braucht man es vor allem bei variablen Koeffizienten, die entstehen, wenn sich
eine Kenngröße während des Vorgangs ändert, etwa die Masse einer Rakete, die
Treibstoff verbrennt.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können erklären, warum Raten bei einer linearen DGL mit variablen
  Koeffizienten selten zum Ziel führt.
* [ ] Sie kennen die Idee der **Variation der Konstanten**, die Konstante $A$
  der homogenen Lösung durch eine Funktion $A(x)$ zu ersetzen.
* [ ] Sie können mit der Variation der Konstanten Schritt für Schritt eine
  partikuläre Lösung einer linearen DGL 1. Ordnung berechnen.
* [ ] Sie können begründen, warum sich beim Einsetzen des Ansatzes die Terme
  mit $A(x)$ aufheben.
```

## Warum hilft Raten bei $y' + \frac{1}{x}\,y = x$ nicht weiter?

Wir betrachten die DGL

\begin{equation*}
y' + \frac{1}{x}\,y = x, \qquad x > 0,
\end{equation*}

die wir in Kapitel 9.2 aus $x\,y' + y = x^2$ gewonnen haben. Wie in Kapitel
9.3 rechnen wir auf dem Intervall $x > 0$, für $x < 0$ ergeben sich dieselben
Formeln. Die homogene Lösung kennen wir bereits, sie lautet
$y_h = \frac{A}{x}$. Nach Kapitel 9.4 fehlt uns also nur noch eine einzige
partikuläre Lösung $y_p$. Bei $y' + 2y = 4$ hat eine Konstante geholfen, weil
die rechte Seite konstant war. Hier ist die rechte Seite eine Gerade, und es
liegt nahe, auch für $y_p$ eine Gerade $y = mx + n$ zu versuchen. Mit $y' = m$
ergibt die linke Seite

\begin{equation*}
m + \frac{1}{x}\,(mx + n) = 2m + \frac{n}{x}.
\end{equation*}

Das soll für alle $x > 0$ gleich $x$ sein. Für große $x$ nähert sich die linke
Seite aber der Zahl $2m$, während die rechte Seite über alle Grenzen wächst.
Keine Wahl von $m$ und $n$ löst also die DGL, und eine Konstante, der Fall
$m = 0$, erst recht nicht.

*Woran liegt das?* Der Koeffizient $\frac{1}{x}$ macht aus dem Term $mx$ die
Konstante $m$, er senkt also die Potenz von $x$ um eins. Bei konstanten
Koeffizienten passiert das nicht. Setzen wir die Gerade in $y' + 2y$ ein,
erhalten wir $m + 2mx + 2n$, also wieder eine Gerade. Eine Funktion von
derselben Bauart wie die rechte Seite auszuprobieren, ist deshalb vor allem
bei konstanten Koeffizienten aussichtsreich. Wann genau das klappt,
untersuchen wir in Kapitel 10.3. Hier könnten wir weiterprobieren, etwa mit
höheren Potenzen von $x$. Bei jeder neuen DGL müssten wir dann aber von vorn
überlegen, was der Koeffizient aus unserem Versuch macht.

*Gibt es einen Weg, der ganz ohne Raten auskommt?* Wir nutzen, was wir schon
wissen. Die homogene Lösung $y_h = \frac{A}{x}$ macht die linke Seite für jede
Konstante $A$ zu null und löst die inhomogene DGL deshalb nie. Die Konstante
$A$ hat also keinerlei Einfluss auf die linke Seite. Das ändert sich, wenn
wir $A$ nicht mehr als feste Zahl betrachten, sondern als Funktion, die sich
mit $x$ verändern darf. *Kann eine solche Funktion $A(x)$ die linke Seite
gerade so verändern, dass dort $x$ entsteht?*

## Wie wird aus der Konstanten eine Funktion?

Wir ersetzen in der homogenen Lösung die Konstante $A$ durch eine noch
unbekannte Funktion $A(x)$ und machen damit den Ansatz

\begin{equation*}
y_p = A(x) \cdot \frac{1}{x}.
\end{equation*}

Gesucht ist jetzt keine Zahl mehr, sondern die Funktion $A(x)$. Um den Ansatz
in die DGL einzusetzen, brauchen wir seine Ableitung. Weil $y_p$ ein Produkt
aus zwei Funktionen von $x$ ist, verwenden wir die Produktregel:

\begin{equation*}
y_p' = A'(x) \cdot \frac{1}{x} + A(x) \cdot \left(-\frac{1}{x^2}\right).
\end{equation*}

Der erste Summand entsteht durch das Ableiten von $A(x)$, der zweite durch das
Ableiten von $\frac{1}{x}$. Wäre $A$ konstant, gäbe es nur den zweiten
Summanden. Jetzt setzen wir $y_p$ und $y_p'$ in die linke Seite der DGL ein:

\begin{equation*}
y_p' + \frac{1}{x}\,y_p
= \frac{A'(x)}{x} - \frac{A(x)}{x^2} + \frac{A(x)}{x^2}
= \frac{A'(x)}{x}.
\end{equation*}

Die beiden Terme mit $A(x)$ heben sich auf, und übrig bleibt nur der Term mit
der Ableitung $A'(x)$. Die DGL verlangt, dass dieser Term gleich der rechten
Seite $x$ ist:

\begin{equation*}
\frac{A'(x)}{x} = x
\quad\Rightarrow\quad
A'(x) = x^2.
\end{equation*}

Aus der DGL für $y$ ist damit eine viel einfachere Gleichung für $A(x)$
geworden, die wir durch Integrieren lösen. Wir erhalten
$A(x) = \frac{x^3}{3}$ und brauchen keine Integrationskonstante, denn wir
suchen nur eine einzige partikuläre Lösung. Eingesetzt in den Ansatz ergibt
sich

\begin{equation*}
y_p = \frac{x^3}{3} \cdot \frac{1}{x} = \frac{x^2}{3}.
\end{equation*}

Zur Probe ist $y_p' = \frac{2x}{3}$ und $\frac{1}{x}\,y_p = \frac{x}{3}$, die
linke Seite ist also $\frac{2x}{3} + \frac{x}{3} = x$. Nach Kapitel 9.4 lautet
die allgemeine Lösung

\begin{equation*}
y = y_h + y_p = \frac{A}{x} + \frac{x^2}{3}, \qquad A \in \mathbb{R}.
\end{equation*}

Die Parabel $\frac{x^2}{3}$ ist genau die höhere Potenz, die wir im ersten
Abschnitt hätten erraten müssen. Hier haben wir sie gefunden, ohne zu
überlegen, was der Koeffizient $\frac{1}{x}$ aus einem Versuch macht. Hätten
wir beim Integrieren doch eine Konstante $C$ mitgenommen, also
$A(x) = \frac{x^3}{3} + C$, so wäre $\frac{C}{x} + \frac{x^2}{3}$
herausgekommen. Das ist bereits die allgemeine Lösung, und die
Integrationskonstante übernimmt die Rolle von $A$ in der homogenen Lösung. Weil
wir die Konstante der homogenen Lösung durch eine veränderliche Funktion
ersetzen, heißt das Verfahren **Variation der Konstanten**.

<!-- markdownlint-disable MD013 -->
```{dropdown} Video "Spezielle Lösung der inhomogenen linearen DGL 1. Ordnung" von Prof. Hielscher (TH Mannheim)
<iframe width="927" height="588"
src="https://www.youtube.com/embed/k3AZSl7wfy4?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07"
title="Spezielle Lösung der inhomogenen linearen DGL 1. Ordnung" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

```{dropdown} Video "Inhomogene lineare DGL 1. Ordnung, Variation der Konstanten" von Sciencebarbie
<iframe width="927" height="521" src="https://www.youtube.com/embed/DD8blQLaHDM"
title="Inhomogene lineare DGL 1. Ordnung, Variation der Konstanten"
frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```
<!-- markdownlint-enable MD013 -->

## Warum fällt beim Einsetzen immer ein Term weg?

Im Beispiel haben sich die Terme $-\frac{A(x)}{x^2}$ und $\frac{A(x)}{x^2}$
gegenseitig aufgehoben. *War das Glück, oder passiert das bei jeder linearen
DGL?* Um das zu klären, betrachten wir eine beliebige lineare DGL
$y' + f(x)\,y = g(x)$. Ihre homogene Lösung ist nach Kapitel 9.3 ein
Vielfaches $A \cdot y_1$ der Funktion

\begin{equation*}
y_1 = e^{-\int f(x)\,dx},
\end{equation*}

die selbst die homogene DGL löst, also $y_1' + f(x)\,y_1 = 0$ erfüllt. Im
Beispiel war $y_1 = \frac{1}{x}$. Der Ansatz der Variation der Konstanten
lautet $y_p = A(x) \cdot y_1$. Mit der Produktregel und anschließendem
Ausklammern von $A(x)$ wird die linke Seite zu

<!-- markdownlint-disable -->
\begin{equation*}
y_p' + f(x)\,y_p
= A'(x)\,y_1 + A(x)\,y_1' + f(x)\,A(x)\,y_1
= A'(x)\,y_1 + A(x)\,\underbrace{\big(y_1' + f(x)\,y_1\big)}_{=\,0}.
\end{equation*}
<!-- markdownlint-enable -->

Die Klammer ist null, weil $y_1$ die homogene DGL löst. Der Term mit $A(x)$
fällt also immer weg, und zwar aus demselben Grund, aus dem die homogene Lösung
in Kapitel 9.4 auf der linken Seite stets null ergeben hat. Übrig bleibt die
Gleichung $A'(x)\,y_1 = g(x)$. Weil die Exponentialfunktion $y_1$ nie null
wird, dürfen wir durch sie teilen und erhalten

\begin{equation*}
A'(x) = \frac{g(x)}{y_1} = g(x)\,e^{\int f(x)\,dx}.
\end{equation*}

In dieser Gleichung kommt $A(x)$ selbst nicht mehr vor, sondern nur seine
Ableitung. Wir finden $A(x)$ deshalb immer durch Integrieren, ganz gleich,
welche Koeffizienten und welche Störfunktion die DGL hat. Ob das Integral
leicht oder schwer ist, hängt allerdings von $f$ und $g$ ab.

```{admonition} Wie funktioniert die Variation der Konstanten?
:class: note
Eine partikuläre Lösung der linearen DGL $y' + f(x)\,y = g(x)$ bestimmen wir
in vier Schritten:

1. Wir lösen die zugehörige homogene DGL und erhalten $y_h = A \cdot y_1$ mit
   $y_1 = e^{-\int f(x)\,dx}$.
2. Wir ersetzen die Konstante $A$ durch eine Funktion $A(x)$ und machen den
   Ansatz $y_p = A(x) \cdot y_1$.
3. Wir setzen den Ansatz in die DGL ein. Die Terme mit $A(x)$ heben sich auf,
   und es bleibt $A'(x)\,y_1 = g(x)$.
4. Wir bestimmen $A(x)$ durch Integrieren und setzen es in den Ansatz ein.

Die allgemeine Lösung ist dann $y = y_h + y_p$.
```

Vor dem ersten Schritt muss die DGL in der Form $y' + f(x)\,y = g(x)$ stehen.
Bei $x\,y' + y = x^2$ teilen wir also zuerst durch $x$, und dabei ändert sich
auch die rechte Seite: Die Störfunktion ist $g(x) = x$ und nicht $x^2$.

Nach diesen vier Schritten lösen wir noch eine zweite DGL, deren linke Seite
wir aus Kapitel 8 kennen:

\begin{equation*}
y' - x\,y = x\,e^{\frac{x^2}{2}}.
\end{equation*}

Die zugehörige homogene DGL $y' - xy = 0$ ist die DGL $y' = xy$ mit der
Lösung $y_h = A\,e^{\frac{x^2}{2}}$, also ist $y_1 = e^{\frac{x^2}{2}}$. Der
Ansatz lautet $y_p = A(x)\,e^{\frac{x^2}{2}}$. Seine Ableitung ist nach der
Produkt- und der Kettenregel
$y_p' = A'(x)\,e^{\frac{x^2}{2}} + A(x)\,x\,e^{\frac{x^2}{2}}$, und der zweite
Summand hebt sich beim Einsetzen gegen $-x\,y_p = -A(x)\,x\,e^{\frac{x^2}{2}}$
weg. Es bleibt $A'(x)\,e^{\frac{x^2}{2}} = x\,e^{\frac{x^2}{2}}$, also
$A'(x) = x$. Daraus folgt $A(x) = \frac{x^2}{2}$ und

\begin{equation*}
y_p = \frac{x^2}{2}\,e^{\frac{x^2}{2}}, \qquad
y = \left(A + \frac{x^2}{2}\right) e^{\frac{x^2}{2}}, \quad A \in \mathbb{R}.
\end{equation*}

Zur Probe leiten wir $y_p$ ab und erhalten
$y_p' = x\,e^{\frac{x^2}{2}} + \frac{x^3}{2}\,e^{\frac{x^2}{2}}$. Ziehen wir
$x\,y_p = \frac{x^3}{2}\,e^{\frac{x^2}{2}}$ ab, bleibt genau die rechte Seite
$x\,e^{\frac{x^2}{2}}$ stehen.

```{dropdown} Video "Variation der Konstanten, 1. Ordnung, Beispiel" von MathemaTrick
<iframe width="927" height="521" src="https://www.youtube.com/embed/AWdLkNZJZ70"
title="Differentialgleichung inhomogen lösen, Variation der Konstanten"
frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Bei einer linearen DGL mit variablen Koeffizienten hilft Raten kaum weiter,
weil die Koeffizienten aus einem Versuch eine Funktion anderer Bauart machen.
Die Variation der Konstanten ersetzt deshalb die Konstante $A$ der homogenen
Lösung durch eine Funktion $A(x)$. Beim Einsetzen fällt der Term mit $A(x)$
immer weg, weil $y_1$ die homogene DGL löst, und für $A'(x)$ bleibt eine
Gleichung, die wir durch Integrieren lösen. Für $y' + \frac{1}{x}\,y = x$
ergibt sich $y_p = \frac{x^2}{3}$ und die allgemeine Lösung
$\frac{A}{x} + \frac{x^2}{3}$. In Kapitel 10.2 fassen wir die vier Schritte zu
einer einzigen Formel zusammen und legen die Konstante $A$ mit einer
Anfangsbedingung fest. In Kapitel 10.3 sehen wir, dass die Variation der
Konstanten auch dort weiterhilft, wo ein sonst bewährter Ansatz plötzlich
versagt.
