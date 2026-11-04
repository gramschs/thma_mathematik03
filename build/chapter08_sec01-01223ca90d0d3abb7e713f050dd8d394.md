---
authors:
  - name: Simone Gramsch
---

# 8.1 Was ist eine Differentialgleichung?

Mit Kapitel 7 haben wir die lineare Algebra abgeschlossen. Dort waren die
Unbekannten stets Zahlen oder Vektoren, etwa die Lösung $\vec{x}$ eines
linearen Gleichungssystems in Kapitel 2.4 oder ein Eigenvektor in Kapitel 6. In
den Ingenieurwissenschaften wird aber oft keine Zahl gesucht, sondern eine
Funktion, und in der Gleichung für diese Funktion kommen ihre Ableitungen vor.
Solche Gleichungen beschreiben im Maschinenbau zum Beispiel die
Fallgeschwindigkeit mit Luftwiderstand, die Biegelinie eines Balkens oder den
Temperaturverlauf in einem Bauteil.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, was eine **gewöhnliche Differentialgleichung** ist, und
  können sie von Gleichungen unterscheiden, in denen eine Zahl gesucht ist.
* [ ] Sie können die **Ordnung** einer Differentialgleichung bestimmen.
* [ ] Sie können Differentialgleichungen in Strich-, Punkt- und
  Leibniz-Schreibweise lesen und zwischen **expliziter** und **impliziter**
  Form unterscheiden.
* [ ] Sie können durch Einsetzen nachweisen, dass eine Funktion eine
  **Lösung** einer Differentialgleichung ist.
* [ ] Sie wissen, was die **allgemeine Lösung** einer Differentialgleichung
  ist und warum sie bei einer Differentialgleichung $n$-ter Ordnung $n$ frei
  wählbare Konstanten enthält.
```

## Wie wird aus einer Änderungsrate eine Gleichung?

Aus der Schule kennen wir Gleichungen, deren Lösungen Zahlen sind. Die
quadratische Gleichung $x^2 - x - 6 = 0$ wird zum Beispiel von $x_1 = -2$ und
$x_2 = 3$ erfüllt. Dass diese beiden Zahlen Lösungen sind, prüfen wir durch
Einsetzen: $(-2)^2 - (-2) - 6 = 4 + 2 - 6 = 0$ und $3^2 - 3 - 6 = 0$. Wie wir
auf die Lösungen kommen, ob durch Raten, mit einer Lösungsformel oder mit dem
Computer, ist eine eigene Frage. Auch sehen wir einer Gleichung nicht sofort
an, ob sie überhaupt lösbar ist und wie viele Lösungen sie hat. Bei den
linearen Gleichungssystemen in Kapitel 2.4 gab es je nach Matrix und rechter
Seite keine, genau eine oder unendlich viele Lösungen.

Jetzt suchen wir statt einer Zahl eine Funktion. Wir stellen uns eine Kurve
$y(x)$ vor, deren Steigung an jeder Stelle $x$ genau das $x$-Fache ihres
Funktionswerts ist. Die Steigung ist die Ableitung $y'(x)$, also die
Änderungsrate von $y$, und damit lautet unsere Forderung

\begin{equation*}
y'(x) = x \cdot y(x).
\end{equation*}

Links steht die Ableitung der gesuchten Funktion, rechts die Funktion selbst,
multipliziert mit der Stelle $x$. Die Gleichung soll nicht nur an einer
einzelnen Stelle gelten, sondern für jedes $x$. An der Stelle $x = 0$ muss die
Kurve also waagerecht verlaufen, und an der Stelle $x = 2$ muss ihre Steigung
doppelt so groß sein wie ihr Funktionswert.

*Welche Funktion kommt infrage?* Weil in der Ableitung die Funktion selbst
wieder auftauchen soll, liegt die $e$-Funktion nahe. Für $y = e^x$ ist
$y' = e^x$, die rechte Seite lautet aber $x \cdot e^x$. Beide stimmen nur an
der Stelle $x = 1$ überein, und das reicht nicht. Beim nächsten Versuch
$y = e^{x^2}$ liefert die Kettenregel $y' = 2x\,e^{x^2} = 2x \cdot y$, also einen
Faktor $2$ zu viel. Halbieren wir den Exponenten, verschwindet dieser Faktor:

\begin{equation*}
y(x) = e^{\frac{x^2}{2}}
\quad\Rightarrow\quad
y'(x) = e^{\frac{x^2}{2}} \cdot \frac{2x}{2} = x \cdot e^{\frac{x^2}{2}}
= x \cdot y(x).
\end{equation*}

Die innere Ableitung von $\frac{x^2}{2}$ ist $x$, und genau dieser Faktor wird
verlangt. Linke und rechte Seite stimmen für jedes $x$ überein, die Funktion
$y = e^{x^2/2}$ erfüllt also unsere Forderung. Wir haben damit die Begriffe,
die wir von Gleichungen für Zahlen kennen, auf eine neue Art von Gleichung
übertragen. Gesucht ist eine Funktion, in der Gleichung kommen die Funktion
und ihre Ableitung vor, und ob eine Funktion die Gleichung erfüllt, prüfen wir
wieder durch Einsetzen.

```{admonition} Was ist ... eine Differentialgleichung?
:class: note
Eine **Differentialgleichung**, kurz **DGL**, ist eine Gleichung für eine
gesuchte Funktion $y(x)$, in der mindestens eine Ableitung von $y$ vorkommt.
Außerdem dürfen $y$ selbst und die Variable $x$ darin auftreten. Hängt die
gesuchte Funktion nur von einer einzigen Variablen ab, heißt die Gleichung
**gewöhnliche Differentialgleichung**. Statt $y(x)$ und $y'(x)$ schreiben wir
oft kurz $y$ und $y'$.
```

Unsere Gleichung $y' = xy$ ist eine gewöhnliche DGL, denn die gesuchte Funktion
$y$ hängt nur von $x$ ab, und ihre Ableitung $y'$ kommt vor. Hängt die gesuchte
Funktion dagegen von mehreren Variablen ab, etwa von Ort und Zeit, enthält die
Gleichung partielle Ableitungen und heißt **partielle Differentialgleichung**.
Solche Gleichungen behandeln wir in diesem Kurs nicht, mit DGL meinen wir
deshalb immer eine gewöhnliche DGL. Im Englischen heißen sie *ordinary
differential equations*, kurz ODE.

Nicht jede Gleichung, in der $x$ und $y$ vorkommen, ist eine DGL. Die
Kreisgleichung $x^2 + y^2 = 4$ beschreibt zwar eine Kurve, enthält aber keine
Ableitung. Auch $y = x^2 + 1$ ist keine DGL, denn hier ist nichts gesucht, die
Gleichung legt die Funktion direkt fest. Entscheidend ist, dass eine unbekannte
Funktion gesucht wird und dass mindestens eine ihrer Ableitungen in der
Gleichung auftaucht.

```{dropdown} Video "Gewöhnliche Differentialgleichungen - Einführung" von Prof. Hielscher (TH Mannheim)
<iframe width="966" height="613"
src="https://www.youtube.com/embed/yFjYQ_J1Uwo?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07"
title="Gewöhnliche Differentialgleichungen - Einführung" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

```{dropdown} Video "Gewöhnliche Differentialgleichung" von Simone Gramsch
<iframe
src="https://frankfurt-university.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=2df731d3-5569-405e-b6ed-b0180090a481&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all"
height="405" width="720" style="border: 1px solid #464646;" allowfullscreen
allow="autoplay"></iframe>
```

## Was ist die Ordnung einer DGL?

In $y' = xy$ kommt nur die erste Ableitung vor. Eine DGL darf aber auch höhere
Ableitungen enthalten. Als zweites Beispiel nehmen wir

\begin{equation*}
y'' + 9y = 0.
\end{equation*}

Gesucht ist eine Funktion $y$, deren zweite Ableitung $y''$ zusammen mit dem
Neunfachen von $y$ null ergibt. Anders gesagt muss die Funktion zweimal
abgeleitet das $(-9)$-Fache von sich selbst ergeben. *Kennen wir eine Funktion,
die nach zweimaligem Ableiten bis auf einen Faktor wieder sich selbst ergibt?*
Die Antwort heben wir uns für den nächsten Abschnitt auf. Schon jetzt sehen wir
aber den wesentlichen Unterschied zu $y' = xy$, denn hier müssen wir die
gesuchte Funktion zweimal ableiten, um die Gleichung überhaupt prüfen zu
können. Die höchste Ableitung ist so wichtig, dass wir DGL danach einteilen.

```{admonition} Was ist ... die Ordnung einer DGL?
:class: note
Die **Ordnung** einer DGL ist die Ordnung der höchsten Ableitung der gesuchten
Funktion, die in der Gleichung vorkommt. Eine DGL $n$-ter Ordnung enthält also
die Ableitung $y^{(n)}$, aber keine höhere.
```

Unsere Gleichung $y' = xy$ ist damit eine DGL 1. Ordnung, die Gleichung
$y'' + 9y = 0$ eine DGL 2. Ordnung. Dass $y'$ in der zweiten Gleichung fehlt,
spielt keine Rolle, denn es zählt nur die höchste Ableitung. Auch eine Potenz
ändert die Ordnung nicht. Die Gleichung $(y')^2 + y^2 = 1$ ist eine
DGL 1. Ordnung, obwohl die Ableitung darin quadriert wird.

```{dropdown} Video "Ordnung einer gewöhnlichen Differentialgleichung" von Simone Gramsch
<iframe
src="https://frankfurt-university.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=e9c4b3da-35c2-4320-babb-b0180090ad24&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all"
height="405" width="720" style="border: 1px solid #464646;" allowfullscreen
allow="autoplay"></iframe>
```

Je nach Anwendung sehen DGL sehr unterschiedlich aus, weil die Bezeichnungen
aus dem jeweiligen Zusammenhang stammen. Die Variable $x$, von der die gesuchte
Funktion abhängt, heißt **unabhängige Variable**. Die gesuchte Funktion $y$
heißt auch **abhängige Variable**, obwohl sie eine Funktion ist. Hängt die
gesuchte Funktion von der Zeit ab, heißt die unabhängige Variable meist $t$,
und die Ableitung nach der Zeit wird in den Ingenieurwissenschaften gern mit
einem Punkt über dem Funktionsnamen geschrieben. Oft heißt die gesuchte
Funktion dann $x(t)$, und unsere Gleichung $y' = xy$ wird zu

\begin{equation*}
\dot{x} = t \cdot x.
\end{equation*}

Der Buchstabe $x$ hat hier die Rolle gewechselt, er bezeichnet jetzt die
gesuchte Funktion und nicht mehr die Variable. Zwei Punkte stehen für die
zweite Ableitung nach der Zeit, aus $y'' + 9y = 0$ wird so $\ddot{x} + 9x = 0$.
Die dritte Schreibweise stammt von Leibniz und schreibt die Ableitung als
Quotient $\frac{dy}{dx}$:

\begin{equation*}
\frac{dy}{dx} = x \cdot y
\qquad\text{und}\qquad
\frac{d^2y}{dx^2} + 9y = 0.
\end{equation*}

Die hochgestellte $2$ in $\frac{d^2y}{dx^2}$ zeigt die zweite Ableitung an, die
Ordnung können wir also auch hier direkt ablesen. Alle drei Schreibweisen
drücken dieselbe Frage aus, für die erste Gleichung etwa: Welche Funktion hat
an jeder Stelle eine Steigung, die gleich dem Produkt aus Stelle und
Funktionswert ist? In Kapitel 8.4 zahlt sich die Leibniz-Schreibweise aus,
denn dort rechnen wir mit $\frac{dy}{dx}$ wie mit einem Bruch und lösen
$y' = xy$, ohne zu raten.

Bei $y' = xy$ steht die höchste Ableitung allein auf der linken Seite, und alle
anderen Terme stehen rechts. Das muss nicht so sein. In $y'' + 9y = 0$ stehen
alle Terme links, und auf der rechten Seite steht die Null. Durch Umstellen
erhalten wir $y'' = -9y$, und jetzt ist die Gleichung nach der höchsten
Ableitung aufgelöst.

```{admonition} Was ist ... eine explizite und eine implizite DGL?
:class: note
Eine DGL $n$-ter Ordnung heißt **explizit**, wenn sie nach der höchsten
Ableitung aufgelöst ist, also die Form

\begin{equation*}
y^{(n)} = F\left(x, y, y', \ldots, y^{(n-1)}\right)
\end{equation*}

hat. Steht sie dagegen in der Form

\begin{equation*}
G\left(x, y, y', \ldots, y^{(n)}\right) = 0,
\end{equation*}

heißt sie **implizit**.
```

Die Gleichung $y' = xy$ ist explizit mit $F(x, y) = xy$. Die Gleichung
$y'' + 9y = 0$ ist implizit mit $G(x, y, y', y'') = y'' + 9y$, und ihre
explizite Form lautet $y'' = -9y$. Ob die allein stehende höchste Ableitung
links oder rechts vom Gleichheitszeichen steht, ist dabei gleichgültig. Eine
explizite DGL lässt sich durch Umstellen immer in eine implizite verwandeln,
umgekehrt gelingt das nicht immer so glatt. Lösen wir $(y')^2 + y^2 = 1$ nach
$y'$ auf, erhalten wir $y' = \sqrt{1 - y^2}$ oder $y' = -\sqrt{1 - y^2}$, also
gleich zwei explizite DGL statt einer.

```{dropdown} Video "Explizite und implizite Differentialgleichungen" von Simone Gramsch
<iframe
src="https://frankfurt-university.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=f685aee3-bac5-4459-839e-b01800ec5f8a&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all"
height="405" width="720" style="border: 1px solid #464646;" allowfullscreen
allow="autoplay"></iframe>
```

## Was ist eine Lösung, und warum gibt es unendlich viele?

Im ersten Abschnitt haben wir geprüft, ob $e^{x^2/2}$ die DGL $y' = xy$
erfüllt, indem wir die Funktion und ihre Ableitung eingesetzt haben. Damit das
überhaupt geht, muss die Funktion so oft differenzierbar sein, wie die Ordnung
der DGL angibt. Außerdem soll die Gleichung nicht nur an einzelnen Stellen
gelten, sondern auf einem ganzen Intervall.

```{admonition} Was ist ... eine Lösung einer DGL?
:class: note
Eine Funktion $y$ heißt **Lösung** einer DGL $n$-ter Ordnung auf einem
Intervall $I$, wenn sie dort $n$-mal differenzierbar ist und die DGL für alle
$x \in I$ erfüllt, sobald wir $y$ und ihre Ableitungen einsetzen.
```

Die Funktion $y = e^{x^2/2}$ ist auf ganz $\mathbb{R}$ differenzierbar, und die
Probe aus dem ersten Abschnitt gilt für jedes $x$. Sie ist also eine Lösung von
$y' = xy$ auf $I = \mathbb{R}$. Die Funktion $y = e^x$ ist dagegen keine
Lösung, denn $e^x = x\,e^x$ gilt nur an der einzelnen Stelle $x = 1$ und auf
keinem Intervall. Wie bei Gleichungen für Zahlen ist auch nicht jede DGL
lösbar. Die DGL $(y')^2 + 1 = 0$ hat keine Lösung, weil ein Quadrat nie
negativ ist, so wie die Gleichung $x^2 + 1 = 0$ keine reelle Lösung hat.

*Ist $e^{x^2/2}$ die einzige Lösung von $y' = xy$?* Probieren wir das Doppelte,
also $y = 2e^{x^2/2}$. Der Faktor $2$ bleibt beim Ableiten erhalten, und wir
erhalten $y' = 2x\,e^{x^2/2} = x \cdot 2e^{x^2/2} = x \cdot y$. Mit jedem
anderen Faktor klappt das genauso. Für eine beliebige Konstante $A$ gilt

\begin{equation*}
y = A\,e^{\frac{x^2}{2}}
\quad\Rightarrow\quad
y' = A\,x\,e^{\frac{x^2}{2}} = x \cdot A\,e^{\frac{x^2}{2}} = x \cdot y.
\end{equation*}

Die Konstante $A$ wandert beim Ableiten unverändert mit, und die Probe gelingt
für jedes $A \in \mathbb{R}$. Das gilt sogar für $A = 0$, denn die Nullfunktion
$y = 0$ hat die Ableitung $y' = 0 = x \cdot 0$. Die DGL hat also unendlich
viele Lösungen, für jede Wahl von $A$ eine. Die folgende Abbildung zeigt fünf
davon.

```{figure} pics/kurvenschar_exponential.svg
---
name: kurvenschar_exponential
---
Darstellung der Lösungen $y = A\,e^{x^2/2}$ der DGL $y' = xy$ für fünf Werte
von $A$.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Alle Kurven verlaufen an der Stelle $x = 0$ waagerecht, wie es die DGL verlangt,
und je weiter wir uns von $x = 0$ entfernen, desto steiler werden sie. Die
Konstante $A$ ist genau der Funktionswert an der Stelle $x = 0$, denn
$A\,e^{0} = A$. Zwei verschiedene Kurven der Schar schneiden sich nirgends, und
durch jeden Punkt der Ebene geht genau eine von ihnen.

*Woher kommen die vielen Lösungen?* Am deutlichsten sehen wir das an einer DGL,
in der die gesuchte Funktion selbst gar nicht vorkommt, etwa

\begin{equation*}
y'' = -\sin(x).
\end{equation*}

Diese DGL lösen wir, indem wir zweimal unbestimmt integrieren. Die erste
Integration liefert $y' = \cos(x) + C_1$, die zweite

\begin{equation*}
y = \sin(x) + C_1\,x + C_2.
\end{equation*}

Bei jeder Integration entsteht eine Integrationskonstante, und weil wir zweimal
integrieren, enthält das Ergebnis die beiden Konstanten $C_1$ und $C_2$. Zur
Probe leiten wir zweimal ab. Dabei fallen beide Konstanten weg, und es bleibt
$y'' = -\sin(x)$, ganz gleich, wie wir $C_1$ und $C_2$ wählen. Je höher die
Ordnung, desto öfter müssen wir integrieren und desto mehr Konstanten
entstehen. Das erinnert an die linearen Gleichungssysteme aus Kapitel 4.3. Dort
haben wir unendlich viele Lösungen mit freien Parametern beschrieben, die wir
beliebig wählen durften, und bei einer DGL übernehmen die Konstanten diese
Rolle.

Bei $y'' + 9y = 0$ steht die gesuchte Funktion auch in der expliziten Form
$y'' = -9y$ auf der rechten Seite, und einfaches Integrieren hilft nicht weiter.
Wir suchen eine Funktion, die zweimal abgeleitet das $(-9)$-Fache von sich
selbst ergibt. Der Sinus wird nach zweimaligem Ableiten zum negativen Sinus,
und der Faktor $9 = 3^2$ deutet auf $\sin(3x)$ hin. Tatsächlich liefert die
Kettenregel $(\sin(3x))' = 3\cos(3x)$ und $(\sin(3x))'' = -9\sin(3x)$, und
genauso ist $(\cos(3x))'' = -9\cos(3x)$. Für eine Kombination mit zwei
Konstanten $C_1$ und $C_2$ gilt deshalb

\begin{align*}
y &= C_1\cos(3x) + C_2\sin(3x),\\
y'' &= -9C_1\cos(3x) - 9C_2\sin(3x) = -9y.
\end{align*}

Damit ist $y'' + 9y = 0$ für alle $x \in \mathbb{R}$ erfüllt, und zwar für jede
Wahl von $C_1$ und $C_2$. Wieder hat eine DGL 2. Ordnung zwei frei wählbare
Konstanten, und wie bei $y' = xy$ beschreibt eine einzige Formel mit
Konstanten eine ganze Schar von Lösungen.

```{admonition} Was ist ... die allgemeine Lösung einer DGL?
:class: note
Eine Lösungsformel, die noch frei wählbare Konstanten enthält und damit eine
ganze Schar von Lösungen beschreibt, heißt **allgemeine Lösung** der DGL. Bei
einer DGL $n$-ter Ordnung enthält die allgemeine Lösung $n$ Konstanten.
```

Für unsere beiden Beispiele bedeutet das: $y = A\,e^{x^2/2}$ ist die allgemeine
Lösung der DGL $y' = xy$ mit einer Konstanten, und
$y = C_1\cos(3x) + C_2\sin(3x)$ ist die allgemeine Lösung der DGL
$y'' + 9y = 0$ mit zwei Konstanten. Wenn wir von *der* Lösung einer DGL
sprechen, meinen wir also eigentlich unendlich viele Funktionen. Wie wir die
Konstanten nennen, ist dabei egal, üblich sind $A$, $C$ oder $C_1$ und $C_2$.

*Haben wir mit $A\,e^{x^2/2}$ aber wirklich alle Lösungen von $y' = xy$
erfasst?* Durch Einsetzen können wir nur bestätigen, dass eine Funktion eine
Lösung ist, nicht aber, dass es keine weiteren gibt. In Kapitel 8.4 leiten wir
die Lösung mit der Trennung der Variablen her, statt sie zu raten, und sehen
dabei, dass keine weiteren Lösungen hinzukommen.

```{dropdown} Video "Allgemeine Lösung einer DGL" von Simone Gramsch
<iframe
src="https://frankfurt-university.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=b7d5b60a-2bd6-42a6-9f6a-b01800ebb264&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all"
height="405" width="720" style="border: 1px solid #464646;" allowfullscreen
allow="autoplay"></iframe>
```

## Zusammenfassung und Ausblick

Eine Differentialgleichung ist eine Gleichung für eine gesuchte Funktion, in
der auch Ableitungen dieser Funktion vorkommen. Ihre Ordnung ist die Ordnung
der höchsten Ableitung, und ob eine Funktion eine Lösung ist, prüfen wir durch
Einsetzen. Die DGL $y' = xy$ hat die allgemeine Lösung $y = A\,e^{x^2/2}$ mit
einer Konstanten, die DGL $y'' + 9y = 0$ die allgemeine Lösung
$y = C_1\cos(3x) + C_2\sin(3x)$ mit zwei Konstanten. *Wie wählen wir aus einer
solchen Schar eine einzige Lösung aus, und wie viele Bedingungen brauchen wir
dafür?* Das klären wir in Kapitel 8.2 mit Anfangs- und Randbedingungen. In
Kapitel 11 lernen wir dann ein Verfahren, mit dem wir Gleichungen wie
$y'' + 9y = 0$ lösen, ohne raten zu müssen.
