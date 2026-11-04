---
authors:
  - name: Simone Gramsch
---

# 8.2 Anfangs- und Randwertprobleme

In Kapitel 8.1 haben wir gesehen, dass eine DGL unendlich viele Lösungen hat,
die wir in der allgemeinen Lösung mit frei wählbaren Konstanten
zusammenfassen. Für eine Anwendung brauchen wir aber meist eine einzige
Lösung. Die Konstanten raten wir dann nicht, sondern legen sie durch
zusätzliche Informationen fest, etwa durch einen bekannten Startwert. Im
Maschinenbau sind das zum Beispiel die Anfangsauslenkung und die
Anfangsgeschwindigkeit eines Schwingers oder die Lagerung eines Balkens an
seinen beiden Enden.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, was ein **Anfangswertproblem** ist, und können aus der
  allgemeinen Lösung die **spezielle Lösung** berechnen.
* [ ] Sie wissen, dass eine DGL $n$-ter Ordnung $n$ Bedingungen braucht, um
  eine Lösung festzulegen.
* [ ] Sie können die Konstanten einer DGL 2. Ordnung aus einem linearen
  Gleichungssystem bestimmen.
* [ ] Sie wissen, was ein **Randwertproblem** ist, und können Anfangs- und
  Randbedingungen unterscheiden.
* [ ] Sie wissen, dass ein Randwertproblem auch keine oder unendlich viele
  Lösungen haben kann.
```

## Wie legt eine Anfangsbedingung die Lösung fest?

In Kapitel 8.1 haben wir für die DGL $y' = xy$ die allgemeine Lösung

\begin{equation*}
y = A\,e^{\frac{x^2}{2}}
\end{equation*}

gefunden. Jede Wahl der Konstanten $A$ liefert eine Lösungskurve, und durch
jeden Punkt der Ebene geht genau eine dieser Kurven. *Welche Kurve geht durch
den Punkt $(0, 2)$?* Dass die Kurve durch diesen Punkt geht, bedeutet
$y(0) = 2$. Wir setzen $x = 0$ in die allgemeine Lösung ein und erhalten

\begin{equation*}
y(0) = A\,e^{0} = A = 2.
\end{equation*}

Mit $A = 2$ lautet die gesuchte Lösung $y = 2e^{x^2/2}$. Zur Probe prüfen wir
beide Forderungen. Die Bedingung ist erfüllt, denn $y(0) = 2e^{0} = 2$, und die
DGL ist erfüllt, weil wir in Kapitel 8.1 nachgewiesen haben, dass
$A\,e^{x^2/2}$ für jedes $A$ eine Lösung ist. Die folgende Abbildung zeigt,
wie die Bedingung aus der Schar genau eine Kurve auswählt.

```{figure} pics/anfangswertproblem_exponential.svg
---
name: anfangswertproblem_exponential
---
Darstellung der Lösungskurve von $y' = xy$ durch den Punkt $(0, 2)$ zwischen
weiteren Kurven der Schar.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Eine Bedingung wie $y(0) = 2$ heißt **Anfangsbedingung**, weil sie oft den
Zustand am Anfang eines Vorgangs beschreibt, wenn die Variable die Zeit ist.
Die Stelle muss aber nicht null sein. Fordern wir etwa $y(2) = 1$, so ergibt
das Einsetzen

\begin{equation*}
y(2) = A\,e^{\frac{4}{2}} = A\,e^{2} = 1
\quad\Rightarrow\quad
A = e^{-2}.
\end{equation*}

Die Lösung lautet dann $y = e^{-2}\,e^{x^2/2} = e^{x^2/2 - 2}$, und die Probe
$y(2) = e^{2 - 2} = e^{0} = 1$ bestätigt die Bedingung. Anders als bei
$x = 0$ ist $A$ hier nicht gleich dem vorgegebenen Wert, wir müssen also
wirklich nach $A$ auflösen. In beiden Fällen ist am Ende eine Lösung ohne frei
wählbare Konstante übrig geblieben.

```{admonition} Was ist ... eine spezielle Lösung?
:class: note
Eine Lösung einer DGL, die keine frei wählbaren Konstanten mehr enthält, heißt
**spezielle Lösung**. Wir erhalten sie aus der allgemeinen Lösung, indem wir
die Konstanten durch zusätzliche Bedingungen festlegen.
```

Für $y' = xy$ ist $y = 2e^{x^2/2}$ die spezielle Lösung zur Bedingung
$y(0) = 2$ und $y = e^{x^2/2 - 2}$ die spezielle Lösung zur Bedingung
$y(2) = 1$. Manche Bücher nennen die spezielle Lösung auch partikuläre Lösung.
In Kapitel 9 verwenden wir dieses Wort für eine bestimmte spezielle Lösung, die
beim Lösen eine besondere Rolle spielt. Allgemein bedeutet eine Bedingung $y(x_0) = y_0$ geometrisch, dass
die Lösungskurve durch den Punkt $(x_0, y_0)$ geht. Bei einer DGL 1. Ordnung
reicht eine einzige solche Bedingung, denn die allgemeine Lösung enthält nur
eine Konstante. Wir setzen die Bedingung ein, erhalten eine Gleichung für die
Konstante und lösen sie.

## Was ändert sich bei einer DGL 2. Ordnung?

Für die DGL $y'' + 9y = 0$ haben wir in Kapitel 8.1 die allgemeine Lösung

\begin{equation*}
y = C_1\cos(3x) + C_2\sin(3x)
\end{equation*}

nachgewiesen. Sie enthält zwei Konstanten. *Reicht auch hier eine einzige
Bedingung?* Wir fordern wie eben, dass die Kurve durch einen Punkt geht, etwa
$y(0) = 1$. Wegen $\cos(0) = 1$ und $\sin(0) = 0$ liefert das Einsetzen
$C_1 = 1$, über $C_2$ sagt die Bedingung aber nichts aus. Es bleiben unendlich
viele Lösungen $y = \cos(3x) + C_2\sin(3x)$, und alle gehen durch den Punkt
$(0, 1)$.

```{figure} pics/kurvenschar_zweite_ordnung.svg
---
name: kurvenschar_zweite_ordnung
---
Darstellung der Lösungen $y = \cos(3x) + C_2\sin(3x)$ von $y'' + 9y = 0$ für
fünf Werte von $C_2$.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Die Kurven gehen zwar alle durch $(0, 1)$, verlassen den Punkt aber mit
unterschiedlicher Steigung. Leiten wir die allgemeine Lösung ab, erhalten wir

\begin{equation*}
y' = -3C_1\sin(3x) + 3C_2\cos(3x),
\end{equation*}

und an der Stelle $x = 0$ bleibt davon $y'(0) = 3C_2$ übrig. Die Steigung im
Startpunkt legt also die zweite Konstante fest. Fordern wir zusätzlich
$y'(0) = 6$, folgt $3C_2 = 6$ und damit $C_2 = 2$. Die spezielle Lösung lautet

\begin{equation*}
y = \cos(3x) + 2\sin(3x).
\end{equation*}

Zur Probe setzen wir ein. Es gilt $y(0) = 1 + 0 = 1$, und mit der Ableitung
$y' = -3\sin(3x) + 6\cos(3x)$ erhalten wir $y'(0) = 0 + 6 = 6$. Die DGL selbst
ist für jede Wahl der Konstanten erfüllt. In der Abbildung ist das die
dunkelblaue Kurve, die von allen gezeichneten Kurven am steilsten durch
$(0, 1)$ ansteigt.

Allgemein liefern zwei Bedingungen $y(0) = y_0$ und $y'(0) = y_1$ zwei
Gleichungen für die beiden Konstanten, nämlich $C_1 = y_0$ und $3C_2 = y_1$.
Das ist ein lineares Gleichungssystem wie in Kapitel 2.4 mit der
Koeffizientenmatrix

\begin{equation*}
\begin{pmatrix} 1 & 0 \\ 0 & 3 \end{pmatrix}.
\end{equation*}

Ihre Determinante ist $3 \neq 0$, nach Kapitel 3.1 ist die Matrix also
invertierbar, und nach Kapitel 2.4 hat das System für jede rechte Seite genau
eine Lösung. Welchen Startwert und welche Startsteigung wir auch vorgeben, es
gibt immer genau eine passende Kurve. Dass die Bedingungen hier an derselben
Stelle stehen, ist kein Zufall, sondern das Kennzeichen eines
Anfangswertproblems.

```{admonition} Was ist ... ein Anfangswertproblem?
:class: note
Ein **Anfangswertproblem**, kurz **AWP**, besteht aus einer DGL $n$-ter
Ordnung und $n$ Anfangsbedingungen an einer einzigen Stelle $x_0$:

\begin{equation*}
y(x_0) = y_0, \quad y'(x_0) = y_1, \quad \ldots, \quad
y^{(n-1)}(x_0) = y_{n-1}.
\end{equation*}
```

Die DGL $y'' + 9y = 0$ mit $y(0) = 1$ und $y'(0) = 6$ ist ein AWP mit $n = 2$
und $x_0 = 0$, die DGL $y' = xy$ mit $y(0) = 2$ ein AWP mit $n = 1$.
Vorgegeben werden der Funktionswert und die Ableitungen bis zur Ordnung
$n - 1$, die höchste Ableitung dagegen nicht. Ihren Wert legt die DGL selbst
fest, in unserem Beispiel ist $y''(0) = -9y(0) = -9$. Bei einer DGL dritter
Ordnung bräuchten wir entsprechend $y(x_0)$, $y'(x_0)$ und $y''(x_0)$, und
umgekehrt verrät die Anzahl der Bedingungen, welche Ordnung die DGL hat. In
Kapitel 11 sehen wir, dass hinter der Determinante des Gleichungssystems für
die Konstanten ein eigener Begriff steckt, mit dem wir prüfen, ob zwei
Lösungen wirklich alle Lösungen erzeugen.

## Was ist ein Randwertproblem?

Bisher haben wir beide Bedingungen an derselben Stelle gestellt. Wir können
aber auch zwei Funktionswerte an verschiedenen Stellen vorgeben, etwa
$y(0) = 1$ und $y\left(\frac{\pi}{6}\right) = 2$. Die erste Bedingung liefert
wieder $C_1 = 1$. Für die zweite brauchen wir
$\cos\left(\frac{\pi}{2}\right) = 0$ und $\sin\left(\frac{\pi}{2}\right) = 1$:

\begin{equation*}
y\left(\frac{\pi}{6}\right) = C_1\cos\left(\frac{\pi}{2}\right) +
C_2\sin\left(\frac{\pi}{2}\right) = C_2 = 2.
\end{equation*}

Mit $C_1 = 1$ und $C_2 = 2$ erhalten wir wieder $y = \cos(3x) + 2\sin(3x)$,
also dieselbe Funktion wie beim Anfangswertproblem, und die Probe
$y\left(\frac{\pi}{6}\right) = 0 + 2 = 2$ bestätigt die zweite Bedingung. In der
Abbildung sehen wir, warum das klappt. An der Stelle $\frac{\pi}{6}$ hat jede
Kurve den Funktionswert $C_2$, die Kurven liegen dort weit auseinander, und
genau eine von ihnen geht durch $\left(\frac{\pi}{6}, 2\right)$. Dieselbe Kurve
lässt sich also durch Startwert und Startsteigung oder durch zwei Punkte
festlegen.

```{admonition} Was ist ... ein Randwertproblem?
:class: note
Ein **Randwertproblem**, kurz **RWP**, besteht aus einer DGL $n$-ter Ordnung
und $n$ **Randbedingungen** an den Funktionswert oder an Ableitungen, die an
mindestens zwei verschiedenen Stellen gestellt werden.
```

Unser Beispiel ist ein RWP mit $n = 2$ und den beiden Stellen $0$ und
$\frac{\pi}{6}$. Der Name kommt daher, dass die Stellen oft die Enden, also die
Ränder, des Intervalls sind, auf dem wir die Lösung suchen. Auch eine
Bedingung an die Ableitung zählt mit, etwa ein Funktionswert an der einen und
eine Steigung an der anderen Stelle. Ein RWP für eine DGL 1. Ordnung gibt es
dagegen nicht. Sie bekommt nur eine einzige Bedingung, und die steht
zwangsläufig an einer einzigen Stelle, also handelt es sich um ein AWP.

*Hat ein RWP immer genau eine Lösung, so wie unser AWP?* Wir verschieben die
zweite Stelle nach $\frac{\pi}{3}$. Wegen $\cos(\pi) = -1$ und $\sin(\pi) = 0$
gilt für jede Lösung

\begin{equation*}
y\left(\frac{\pi}{3}\right) = C_1\cos(\pi) + C_2\sin(\pi) = -C_1.
\end{equation*}

Der Wert an dieser Stelle hängt gar nicht von $C_2$ ab. Fordern wir $y(0) = 1$
und $y\left(\frac{\pi}{3}\right) = -1$, ergeben beide Bedingungen $C_1 = 1$,
und $C_2$ bleibt frei. Dieses RWP hat unendlich viele Lösungen, und in der
Abbildung gehen tatsächlich alle Kurven auch durch den Punkt
$\left(\frac{\pi}{3}, -1\right)$. Fordern wir stattdessen
$y\left(\frac{\pi}{3}\right) = 1$, verlangt die zweite Bedingung $C_1 = -1$ und
widerspricht damit der ersten. Dieses RWP hat überhaupt keine Lösung.

Das Gleichungssystem zeigt, woran das liegt. Für zwei Funktionswerte an den
Stellen $0$ und $b$ lauten die Gleichungen $C_1 = y_0$ und
$C_1\cos(3b) + C_2\sin(3b) = y_1$, die Koeffizientenmatrix ist also

\begin{equation*}
\begin{pmatrix} 1 & 0 \\ \cos(3b) & \sin(3b) \end{pmatrix}
\end{equation*}

mit der Determinante $\sin(3b)$. Für $b = \frac{\pi}{6}$ ist sie $1$, und es
gibt genau eine Lösung. Für $b = \frac{\pi}{3}$ ist sie $\sin(\pi) = 0$, und
nach Kapitel 2.4 hat das System dann je nach rechter Seite keine oder
unendlich viele Lösungen. Beim AWP war die Determinante dagegen immer $3$. Ob
ein RWP eindeutig lösbar ist, hängt also von der Lage der Stellen ab, und das
macht RWP schwieriger als AWP.

```{dropdown} Video "Anfangswert- und Randwertprobleme" von Prof. Hielscher (TH Mannheim)
<iframe width="966" height="613"
src="https://www.youtube.com/embed/kEuTsYsK5nk?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07"
title="Anfangswert- und Randwertprobleme" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Eine DGL $n$-ter Ordnung braucht $n$ Bedingungen, um aus der allgemeinen Lösung
eine spezielle Lösung auszuwählen. Stehen alle Bedingungen an derselben Stelle,
sprechen wir von einem Anfangswertproblem, sonst von einem Randwertproblem. Bei
$y'' + 9y = 0$ führen die Bedingungen auf ein lineares Gleichungssystem für
$C_1$ und $C_2$, das beim AWP immer genau eine Lösung hat, beim RWP je nach
Lage der Stellen aber auch keine oder unendlich viele. Bisher haben wir die
allgemeine Lösung stets vorgegeben bekommen oder geraten. Wer sehen möchte,
wie die Lösungskurven von $y' = xy$ ohne Formel entstehen, findet in
Kapitel 8.3 das Richtungsfeld als Vertiefung. In Kapitel 8.4 berechnen wir die
allgemeine Lösung von $y' = xy$ dann mit der Trennung der Variablen.
