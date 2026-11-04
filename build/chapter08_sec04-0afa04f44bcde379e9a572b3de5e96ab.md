---
authors:
  - name: Simone Gramsch
---

# 8.4 Trennung der Variablen

In Kapitel 8.1 haben wir die allgemeine Lösung $y = A\,e^{x^2/2}$ der DGL
$y' = xy$ erraten und durch Einsetzen bestätigt, und in Kapitel 8.2 haben wir
daraus mit einer Anfangsbedingung eine spezielle Lösung ausgewählt. Offen
geblieben ist, wie wir auf eine solche Formel kommen, ohne sie zu raten, und ob
es neben ihr noch weitere Lösungen gibt. In diesem Kapitel lernen wir das erste
Lösungsverfahren kennen, das beide Fragen beantwortet. Im Maschinenbau führen
zum Beispiel das Ausfließen eines Behälters oder die Seilreibung an einer
Trommel auf DGL, die sich mit diesem Verfahren lösen lassen.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie erkennen eine **trennbare** DGL 1. Ordnung an der Form
  $y' = f(x) \cdot g(y)$.
* [ ] Sie können eine trennbare DGL mit der **Trennung der Variablen** lösen.
* [ ] Sie können mit der allgemeinen Lösung ein Anfangswertproblem lösen und
  dabei ein Vorzeichen und den Definitionsbereich richtig wählen.
* [ ] Sie wissen, dass jede Nullstelle von $g$ eine **konstante Lösung**
  liefert, und prüfen, ob sie in der allgemeinen Lösung enthalten ist.
```

## Wann lässt sich eine DGL trennen?

In der DGL $y' = xy$ ist die rechte Seite ein Produkt aus zwei Faktoren. Der
eine Faktor $x$ hängt nur von der Variablen ab, der andere Faktor $y$ nur von
der gesuchten Funktion. Diese Bauart erlaubt einen Trick, den wir in Kapitel
8.1 schon angekündigt haben. Schreiben wir die Ableitung in der
Leibniz-Schreibweise als $\frac{dy}{dx}$, können wir alles, was $y$ enthält, auf
die eine Seite der Gleichung bringen und alles, was $x$ enthält, auf die andere.
Die Variablen werden dabei voneinander getrennt, und genau daher hat das
Verfahren seinen Namen.

```{admonition} Was ist ... eine trennbare DGL?
:class: note
Eine DGL 1. Ordnung heißt **trennbar** oder **separierbar**, wenn sie sich in
der Form

\begin{equation*}
y' = f(x) \cdot g(y)
\end{equation*}

schreiben lässt. Dabei hängt die Funktion $f$ nur von $x$ ab und die Funktion
$g$ nur von $y$.
```

Für unsere DGL $y' = xy$ ist $f(x) = x$ und $g(y) = y$. Manchmal ist die
Produktform erst auf den zweiten Blick zu sehen. Die DGL $y' = e^{x + y}$ ist
trennbar, denn nach dem Potenzgesetz gilt $e^{x + y} = e^x \cdot e^y$, also
$f(x) = e^x$ und $g(y) = e^y$. Auch ein Faktor, der konstant ist, zählt mit. In
$y' = y^2$ ist $f(x) = 1$, und in $y' = 3x^2$ ist $g(y) = 1$. Die zweite
Gleichung enthält $y$ gar nicht mehr, und wir lösen sie wie die einfachsten
DGL aus Kapitel 8.1 durch Integrieren.

Steht eine DGL in impliziter Form da, lösen wir sie vorher nach $y'$ auf. Aus
$y\,y' = \cos(x)$ wird für $y \neq 0$ die explizite Form

\begin{equation*}
y' = \cos(x) \cdot \frac{1}{y},
\end{equation*}

also eine trennbare DGL mit $f(x) = \cos(x)$ und $g(y) = \frac{1}{y}$. *Ist
damit jede DGL 1. Ordnung trennbar?* Nein. In $y' = x + y$ steht auf der
rechten Seite eine Summe, und sie lässt sich nicht in ein Produkt aus einem
Faktor mit $x$ und einem Faktor mit $y$ zerlegen. Solche DGL lösen wir in
Kapitel 9 mit anderen Mitteln.

## Wie funktioniert das Verfahren?

Wir lösen $y' = xy$ Schritt für Schritt. Zunächst schreiben wir die Ableitung
als $\frac{dy}{dx}$ und bringen für $y \neq 0$ alle Terme mit $y$ nach links,
alle Terme mit $x$ nach rechts:

\begin{equation*}
\frac{dy}{dx} = x \cdot y
\quad\Rightarrow\quad
\frac{1}{y}\,dy = x\,dx.
\end{equation*}

Dann integrieren wir beide Seiten, die linke nach $y$ und die rechte nach $x$.
Bei beiden Integrationen entsteht eine Konstante, die wir zu einer einzigen
Konstanten $C = C_2 - C_1$ auf der rechten Seite zusammenfassen:

\begin{equation*}
\int \frac{1}{y}\,dy = \int x\,dx
\quad\Rightarrow\quad
\ln|y| = \frac{x^2}{2} + C.
\end{equation*}

Zum Schluss lösen wir nach $y$ auf. Die $e$-Funktion hebt den Logarithmus auf,
und das Potenzgesetz zieht die Konstante als Faktor heraus:

\begin{equation*}
|y| = e^{\frac{x^2}{2} + C} = e^{C} \cdot e^{\frac{x^2}{2}}
\quad\Rightarrow\quad
y = \pm e^{C} \cdot e^{\frac{x^2}{2}}.
\end{equation*}

Die Zahl $e^C$ kann jeden positiven Wert annehmen, und mit dem Vorzeichen
davor ergibt $\pm e^C$ jede Zahl außer null. Wir fassen sie zu einer neuen
Konstanten $A$ zusammen und erhalten $y = A\,e^{x^2/2}$ mit $A \neq 0$. Das ist
genau die Formel, die wir in Kapitel 8.1 erraten haben, und diesmal haben wir
sie hergeleitet. Den ausgeschlossenen Fall $y = 0$ holen wir im dritten
Abschnitt nach.

*Dürfen wir mit $dy$ und $dx$ überhaupt rechnen wie mit Zahlen?* Die
Kettenregel zeigt, dass das Ergebnis stimmt. Ist $G$ eine Stammfunktion von
$\frac{1}{g}$ und $F$ eine Stammfunktion von $f$, dann gilt für jede Lösung
$y(x)$ der trennbaren DGL

\begin{equation*}
\frac{d}{dx}\,G\big(y(x)\big) = G'\big(y(x)\big) \cdot y'(x)
= \frac{y'(x)}{g\big(y(x)\big)} = f(x) = \frac{d}{dx}\,F(x).
\end{equation*}

Zwei Funktionen mit derselben Ableitung unterscheiden sich nur um eine
Konstante, also ist $G(y) = F(x) + C$. Genau diese Gleichung liefert auch das
formale Rechnen mit $dy$ und $dx$, denn auf beiden Wegen stehen links die
Stammfunktion von $\frac{1}{g}$ und rechts die von $f$.

```{admonition} Wie funktioniert die Trennung der Variablen?
:class: note
Eine trennbare DGL $y' = f(x) \cdot g(y)$ lösen wir für $g(y) \neq 0$ in vier
Schritten:

1. Wir schreiben $y'$ als $\frac{dy}{dx}$ und trennen die Variablen:
   $\frac{1}{g(y)}\,dy = f(x)\,dx$.
2. Wir integrieren beide Seiten: $\int \frac{1}{g(y)}\,dy = \int f(x)\,dx$.
3. Wir setzen die Stammfunktionen ein und fassen die beiden
   Integrationskonstanten zu einer Konstanten $C$ zusammen.
4. Wir lösen nach $y$ auf, falls das möglich ist.

Das Verfahren heißt **Trennung der Variablen** oder Separation der Variablen.
```

Mit der allgemeinen Lösung lösen wir wie in Kapitel 8.2 auch das
Anfangswertproblem mit $y(0) = 2$. Aus $y(0) = A\,e^{0} = A = 2$ folgt die
spezielle Lösung $y = 2e^{x^2/2}$. Nicht immer ist die Konstante aber so
bequem ein Faktor. Wir lösen deshalb noch die DGL $y\,y' = \cos(x)$ aus dem
ersten Abschnitt, und zwar mit der Anfangsbedingung $y(0) = -1$. In der
expliziten Form $\frac{dy}{dx} = \frac{\cos(x)}{y}$ trennen wir die Variablen
und integrieren:

\begin{equation*}
y\,dy = \cos(x)\,dx
\quad\Rightarrow\quad
\int y\,dy = \int \cos(x)\,dx
\quad\Rightarrow\quad
\frac{y^2}{2} = \sin(x) + C.
\end{equation*}

Nach Multiplikation mit $2$ ziehen wir die Wurzel. Dabei entstehen zwei
Vorzeichen:

\begin{equation*}
y = \pm\sqrt{2\sin(x) + 2C}.
\end{equation*}

Diesmal steckt die Konstante unter der Wurzel. Welches Vorzeichen wir brauchen,
entscheidet die Anfangsbedingung. Weil $y(0) = -1$ negativ ist, kommt nur das
Minuszeichen infrage, und aus $-\sqrt{2C} = -1$ folgt $2C = 1$. Die spezielle
Lösung lautet

\begin{equation*}
y = -\sqrt{2\sin(x) + 1}.
\end{equation*}

Zur Probe ist $y(0) = -\sqrt{1} = -1$. Die Kettenregel liefert
$y' = -\frac{\cos(x)}{\sqrt{2\sin(x) + 1}}$, und das Produkt
$y\,y'$ ergibt $\cos(x)$, weil sich die beiden Wurzeln und die beiden
Minuszeichen wegheben. Die Lösung existiert allerdings nicht überall. Unter der
Wurzel muss $2\sin(x) + 1 > 0$ gelten, also $\sin(x) > -\frac{1}{2}$, und das
Intervall um die Startstelle $0$, auf dem das zutrifft, ist
$-\frac{\pi}{6} < x < \frac{7\pi}{6}$. Wie in der Definition aus Kapitel 8.1
ist die Lösung also eine Lösung auf einem Intervall, hier auf
$I = \left(-\frac{\pi}{6}, \frac{7\pi}{6}\right)$.

```{dropdown} Video "Lösung separable Differentialgleichung" von Simone Gramsch
<iframe
src="https://frankfurt-university.cloud.panopto.eu/Panopto/Pages/Embed.aspx?id=bc52e263-cf13-4313-8f1f-ad53009d2b3c&autoplay=false&offerviewer=true&showtitle=true&showbrand=true&captions=false&interactivity=all"
height="405" width="720" style="border: 1px solid #464646;" allowfullscreen
allow="autoplay"></iframe>
```

## Was passiert, wenn $g(y) = 0$ ist?

Beim Trennen von $y' = xy$ haben wir durch $g(y) = y$ geteilt und deshalb
$y = 0$ ausgeschlossen. Die Nullfunktion ist aber eine Lösung, denn
$y' = 0 = x \cdot 0$. Sie passt sogar in die Formel, nämlich mit $A = 0$. Damit
lautet die allgemeine Lösung

\begin{equation*}
y = A\,e^{\frac{x^2}{2}}, \qquad A \in \mathbb{R}.
\end{equation*}

Jetzt können wir auch die Frage aus Kapitel 8.1 beantworten. Jede Lösung, die
nicht die Nullfunktion ist, hat nach unserer Herleitung die Form $A\,e^{x^2/2}$
mit $A \neq 0$, und die Nullfunktion gehört mit $A = 0$ ebenfalls dazu.
Weitere Lösungen von $y' = xy$ gibt es also nicht.

*Steckt die konstante Lösung immer in der allgemeinen Lösung?* Wir trennen die
Variablen in $y' = y^2$ mit $f(x) = 1$ und $g(y) = y^2$. Für $y \neq 0$
erhalten wir

\begin{equation*}
\int \frac{1}{y^2}\,dy = \int 1\,dx
\quad\Rightarrow\quad
-\frac{1}{y} = x + C
\quad\Rightarrow\quad
y = -\frac{1}{x + C}.
\end{equation*}

Auch hier ist die Nullfunktion eine Lösung, denn $0 = 0^2$. Der Bruch
$-\frac{1}{x + C}$ wird aber für keine Wahl von $C$ zur Nullfunktion. Die
Lösung $y = 0$ ist beim Trennen verloren gegangen, und wir müssen sie
ausdrücklich zur Schar dazuschreiben. Die Lösungen von $y' = y^2$ sind also
$y = -\frac{1}{x + C}$ mit $C \in \mathbb{R}$ und zusätzlich $y = 0$.

```{admonition} Was liefern die Nullstellen von g?
:class: note
Ist $y^*$ eine Nullstelle von $g$, also $g(y^*) = 0$, dann ist die konstante
Funktion $y = y^*$ eine Lösung der trennbaren DGL $y' = f(x) \cdot g(y)$, denn
beide Seiten sind null. Nach der Trennung der Variablen prüfen wir für jede
Nullstelle von $g$, ob diese **konstante Lösung** in der allgemeinen Lösung
enthalten ist. Wenn nicht, geben wir sie zusätzlich an.
```

Für $y' = y^2$ ist $y^* = 0$ die einzige Nullstelle von $g(y) = y^2$, und die
zugehörige konstante Lösung fehlt in der Schar. Das spielt beim
Anfangswertproblem eine Rolle. Zur Anfangsbedingung $y(0) = 0$ passt kein $C$,
die einzige Lösung ist die konstante Lösung $y = 0$. Zur Anfangsbedingung
$y(0) = 1$ gehört dagegen $-\frac{1}{C} = 1$, also $C = -1$ und

\begin{equation*}
y = -\frac{1}{x - 1} = \frac{1}{1 - x}.
\end{equation*}

Zur Probe ist $y(0) = 1$ und $y' = \frac{1}{(1 - x)^2} = y^2$. Bei $x = 1$
hat diese Lösung einen Pol. Sie existiert deshalb nur auf dem Intervall
$x < 1$, obwohl die DGL $y' = y^2$ selbst für alle $x$ sinnvoll ist. Bei
$y\,y' = \cos(x)$ aus dem zweiten Abschnitt hat $g(y) = \frac{1}{y}$ dagegen
keine Nullstelle, und es gibt keine konstante Lösung. Wer Kapitel 8.3 gelesen
hat, erkennt die konstanten Lösungen im Richtungsfeld wieder. Sie sind die
waagerechten Nullisoklinen, auf denen die Linienelemente entlang der Linie
selbst liegen.

```{dropdown} Video "Trennung der Variablen" von Prof. Hielscher (TH Mannheim)
<iframe width="927" height="588"
src="https://www.youtube.com/embed/IPbG7lnzccE?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07"
title="DGL 1. Ordnung - Trennung der Variable" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Eine trennbare DGL $y' = f(x) \cdot g(y)$ lösen wir, indem wir die Variablen
trennen, beide Seiten integrieren und nach $y$ auflösen. Für $y' = xy$ haben wir
so die allgemeine Lösung $y = A\,e^{x^2/2}$ hergeleitet und gezeigt, dass es
keine weiteren Lösungen gibt. Jede Nullstelle von $g$ liefert eine konstante
Lösung, die wir gesondert prüfen müssen, wie bei $y' = y^2$. Die Anfangsbedingung
entscheidet über die Konstante, manchmal auch über ein Vorzeichen, und die
spezielle Lösung existiert oft nur auf einem Intervall. In Kapitel 9 sehen wir,
wie eine Substitution DGL wie $y' = (x + y)^2$ in trennbare DGL verwandelt, und
lernen mit den linearen DGL eine weitere Klasse kennen, zu der auch
$y' = x + y$ gehört. Wer sehen möchte, wie der Computer DGL ohne Lösungsformel
behandelt, findet in Kapitel 8.5 das Euler-Verfahren als Vertiefung, dort auch
für $y' = y^2$.
