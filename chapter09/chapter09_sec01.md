---
authors:
  - name: Simone Gramsch
---

# 9.1 Substitution

In Kapitel 8.4 haben wir trennbare DGL $y' = f(x) \cdot g(y)$ gelöst, indem
wir die Variablen getrennt und beide Seiten integriert haben. Am Ende stand die
Frage, was wir mit einer DGL wie $y' = (x + y)^2$ machen, deren rechte Seite
sich nicht in ein Produkt zerlegen lässt. In diesem Kapitel lernen wir einen
Trick kennen, der solche DGL in trennbare DGL verwandelt: Wir ersetzen die
gesuchte Funktion durch eine neue. Variablenwechsel dieser Art sind im
Maschinenbau ein Standardwerkzeug, etwa wenn in der Strömungslehre oder der
Wärmeübertragung mit dimensionslosen Größen gerechnet wird.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie erkennen DGL der Form $y' = f(ax + by + c)$ und
  $y' = f\left(\frac{y}{x}\right)$.
* [ ] Sie können eine solche DGL mit einer **Substitution** in eine trennbare
  DGL für die neue Funktion $u$ umformen und dabei $u'$ richtig berechnen.
* [ ] Sie können die trennbare DGL für $u$ lösen und durch
  **Resubstitution** die Lösung $y$ angeben.
* [ ] Sie prüfen, ob die Nullstellen der rechten Seite der DGL für $u$
  zusätzliche Lösungen liefern.
```

## Warum scheitert die direkte Trennung?

Wir betrachten die DGL $y' = (x + y)^2$. Multiplizieren wir die rechte Seite
aus, erhalten wir $x^2 + 2xy + y^2$, also eine Summe und kein Produkt. *Gibt es
vielleicht eine geschickte Umformung, die doch noch ein Produkt
$f(x) \cdot g(y)$ liefert?* Nein, und das sehen wir an den Nullstellen. Ein
Produkt $f(x) \cdot g(y)$ ist genau dann null, wenn einer der beiden Faktoren
null ist. Ist $f(x_0) = 0$, verschwindet es auf der ganzen senkrechten Geraden
$x = x_0$, ist $g(y_0) = 0$, auf der ganzen waagerechten Geraden $y = y_0$. Der
Ausdruck $(x + y)^2$ ist dagegen genau auf der Geraden $y = -x$ null, und die
ist schräg. Die DGL ist also nicht trennbar.

Was wir aber sehen: Die rechte Seite hängt nicht auf beliebige Weise von $x$ und
$y$ ab, sondern nur von der Summe $x + y$. Diese Beobachtung kennen wir aus der
Integralrechnung. Bei einem Integral wie $\int (2x + 1)^5\,dx$ geben wir dem
inneren Ausdruck einen neuen Namen $u = 2x + 1$ und erhalten ein einfacheres
Integral. Dasselbe versuchen wir jetzt mit der DGL. Wir führen eine neue
Funktion ein,

\begin{equation*}
u(x) = x + y(x),
\end{equation*}

und hoffen, dass die DGL für $u$ einfacher ist als die für $y$. Ein solcher
Wechsel zu einer neuen Funktion heißt **Substitution**.

Für die neue DGL brauchen wir die Ableitung $u'$. Dabei müssen wir aufpassen:
$y$ ist keine Konstante, sondern selbst eine Funktion von $x$. Beim Ableiten
von $u = x + y$ nach $x$ verschwindet $y$ deshalb nicht, sondern wird zu $y'$:

\begin{equation*}
u' = 1 + y'.
\end{equation*}

Jetzt setzen wir die DGL ein. Für $y'$ schreiben wir $(x + y)^2$, und das ist
nach unserer Definition $u^2$. So entsteht

\begin{equation*}
u' = 1 + u^2.
\end{equation*}

In dieser DGL kommt $x$ gar nicht mehr vor. Sie ist trennbar mit dem Faktor $1$
für $x$ und dem Faktor $1 + u^2$ für $u$, und trennbare DGL können wir seit
Kapitel 8.4 lösen.

## Wie hilft die Substitution $u = ax + by + c$?

Wir lösen $u' = 1 + u^2$ mit der Trennung der Variablen. Der Faktor $1 + u^2$
ist nie null, wir dürfen also ohne Ausnahme durch ihn teilen. Die Stammfunktion
von $\frac{1}{1 + u^2}$ ist der Arkustangens:

\begin{equation*}
\frac{1}{1 + u^2}\,du = dx
\quad\Rightarrow\quad
\int \frac{1}{1 + u^2}\,du = \int 1\,dx
\quad\Rightarrow\quad
\arctan(u) = x + C.
\end{equation*}

Nach $u$ aufgelöst ist $u = \tan(x + C)$. Damit kennen wir die neue Funktion,
gesucht ist aber $y$. Wir machen deshalb die Substitution rückgängig und setzen
$u = x + y$ wieder ein. Dieser Schritt heißt **Resubstitution**:

\begin{equation*}
x + y = \tan(x + C)
\quad\Rightarrow\quad
y = \tan(x + C) - x, \qquad C \in \mathbb{R}.
\end{equation*}

Zur Probe leiten wir ab. Mit $\tan'(z) = 1 + \tan^2(z)$ ist
$y' = 1 + \tan^2(x + C) - 1 = \tan^2(x + C)$. Auf der rechten Seite der DGL
steht $(x + y)^2 = \tan^2(x + C)$, beide Seiten stimmen also überein. Wie in
Kapitel 8.4 ist jede dieser Lösungen nur auf einem Intervall definiert, hier
zwischen zwei benachbarten Polstellen des Tangens, an denen $x + C$ ein
ungerades Vielfaches von $\frac{\pi}{2}$ ist.

Der Trick funktioniert immer dann, wenn die rechte Seite nur von einer
Kombination $ax + by + c$ abhängt. Die Ableitung von $u = ax + by + c$ ist
$u' = a + by'$, und weil $y' = f(u)$ ist, entsteht die DGL $u' = a + b\,f(u)$.
Auch sie enthält $x$ nicht mehr und ist deshalb trennbar. In unserem Beispiel
ist $a = b = 1$, $c = 0$ und $f(u) = u^2$.

```{admonition} Wie lösen wir eine DGL $y' = f(ax + by + c)$?
:class: note
Für eine DGL $y' = f(ax + by + c)$ mit Konstanten $a, b, c$ und $b \neq 0$
gehen wir in vier Schritten vor:

1. Wir substituieren $u = ax + by + c$ und leiten ab: $u' = a + b\,y'$.
2. Wir setzen $y' = f(u)$ ein und erhalten die trennbare DGL
   $u' = a + b\,f(u)$.
3. Wir lösen sie mit der Trennung der Variablen. Jede Nullstelle $u_0$ von
   $a + b\,f(u)$ liefert zusätzlich die konstante Lösung $u = u_0$.
4. Wir resubstituieren, setzen also $u = ax + by + c$ ein und lösen nach $y$
   auf.
```

In Schritt 3 steckt dieselbe Vorsicht wie in Kapitel 8.4. Bei $y' = (x + y)^2$
hat $1 + u^2$ keine Nullstelle, und es kommt keine Lösung hinzu. Ändern wir die
DGL nur leicht zu $y' = (x + y)^2 - 1$, so liefert dieselbe Substitution
$u' = 1 + (u^2 - 1) = u^2$. Das ist genau die DGL $y' = y^2$ aus Kapitel 8.4,
nur mit $u$ statt $y$. Ihre Lösungen kennen wir schon: $u = -\frac{1}{x + C}$
und die konstante Lösung $u = 0$. Nach der Resubstitution sind das
$y = -x - \frac{1}{x + C}$ und die Gerade $y = -x$. Die Gerade bestätigen wir
sofort durch Einsetzen, denn $y' = -1$ und $(x - x)^2 - 1 = -1$.

<!-- markdownlint-disable MD013 -->
```{dropdown} Video "Trennung der Variable nach vorheriger Substitution" von Prof. Hielscher (TH Mannheim)
<iframe width="927" height="588"
src="https://www.youtube.com/embed/A0Cg4tRNrfI?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07"
title="DGL 1. Ordnung - Trennung der Variable nach vorheriger Substitution"
frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Differentialgleichung lösen durch Substitution" von Kochrezepte für Mathematik
<iframe width="927" height="521" src="https://www.youtube.com/embed/oIjnic9GT3o"
title="Differentialgleichung lösen durch Substitution - DGL" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```
<!-- markdownlint-enable MD013 -->

## Wie hilft die Substitution $u = y/x$?

Nicht jede rechte Seite hängt von einer Summe ab. Wir betrachten die DGL

\begin{equation*}
x^2\,y' = x^2 + xy + y^2, \qquad x \neq 0.
\end{equation*}

Auf der rechten Seite fällt auf, dass jeder Summand dieselbe Gesamtpotenz hat:
In $x^2$, $xy$ und $y^2$ kommen $x$ und $y$ zusammen jeweils zweimal vor.
Teilen wir durch $x^2$, erhalten wir

\begin{equation*}
y' = 1 + \frac{y}{x} + \left(\frac{y}{x}\right)^2.
\end{equation*}

Jetzt hängt die rechte Seite nur noch vom Quotienten $\frac{y}{x}$ ab. Diesmal
substituieren wir also $u = \frac{y}{x}$. Zum Ableiten schreiben wir die
Substitution als $y = x \cdot u$ und verwenden die Produktregel, denn $u$ ist
wieder eine Funktion von $x$:

\begin{equation*}
y' = 1 \cdot u + x \cdot u' = u + x\,u'.
\end{equation*}

Mit $y' = 1 + u + u^2$ wird daraus $u + x\,u' = 1 + u + u^2$. Das $u$ auf beiden
Seiten hebt sich weg, und es bleibt

\begin{equation*}
x\,u' = 1 + u^2
\quad\Rightarrow\quad
u' = \frac{1}{x} \cdot (1 + u^2).
\end{equation*}

Diese DGL ist trennbar, mit dem Faktor $\frac{1}{x}$ für $x$ und dem Faktor
$1 + u^2$ für $u$. Es ist sogar derselbe Faktor wie im zweiten Abschnitt, nur
dass jetzt rechts $\frac{1}{x}$ statt $1$ steht:

\begin{equation*}
\int \frac{1}{1 + u^2}\,du = \int \frac{1}{x}\,dx
\quad\Rightarrow\quad
\arctan(u) = \ln|x| + C
\quad\Rightarrow\quad
u = \tan\big(\ln|x| + C\big).
\end{equation*}

Die Resubstitution $y = x \cdot u$ ergibt die allgemeine Lösung

\begin{equation*}
y = x\,\tan\big(\ln|x| + C\big), \qquad C \in \mathbb{R}.
\end{equation*}

Zur Probe leiten wir mit der Produkt- und der Kettenregel ab. Mit
$u = \tan(\ln|x| + C)$ und $\frac{d}{dx}\ln|x| = \frac{1}{x}$ ist

\begin{align*}
y' &= \tan\big(\ln|x| + C\big) +
  x \cdot \big(1 + \tan^2(\ln|x| + C)\big) \cdot \frac{1}{x} \\
&= u + 1 + u^2.
\end{align*}

Das ist wegen $u = \frac{y}{x}$ genau die rechte Seite
$1 + \frac{y}{x} + \left(\frac{y}{x}\right)^2$ der DGL.

```{admonition} Wie lösen wir eine DGL $y' = f\left(\frac{y}{x}\right)$?
:class: note
Für eine DGL $y' = f\left(\frac{y}{x}\right)$ mit $x \neq 0$ gehen wir in vier
Schritten vor:

1. Wir substituieren $u = \frac{y}{x}$, also $y = x\,u$, und leiten mit der
   Produktregel ab: $y' = u + x\,u'$.
2. Wir setzen $y' = f(u)$ ein und erhalten die trennbare DGL
   $u' = \frac{1}{x} \cdot \big(f(u) - u\big)$.
3. Wir lösen sie mit der Trennung der Variablen. Jede Nullstelle $u_0$ von
   $f(u) - u$ liefert zusätzlich die konstante Lösung $u = u_0$.
4. Wir resubstituieren, setzen also $y = x\,u$.
```

Im Beispiel ist $f(u) = 1 + u + u^2$ und $f(u) - u = 1 + u^2$. Dieser Ausdruck
hat keine Nullstelle, und es kommt keine Lösung hinzu. Hat $f(u) - u$ dagegen
eine Nullstelle $u_0$, dann ist $u = u_0$ konstant, und die Resubstitution
liefert die Ursprungsgerade $y = u_0\,x$. Eine Integrationskonstante kommt
dabei nicht hinzu, denn in diesem Fall wird nichts integriert.

## Zusammenfassung und Ausblick

Hängt die rechte Seite einer DGL nur von einer Kombination $ax + by + c$ oder
nur vom Quotienten $\frac{y}{x}$ ab, führen wir diese Kombination als neue
Funktion $u$ ein. Beim Ableiten dürfen wir nicht vergessen, dass $y$ von $x$
abhängt. Die DGL für $u$ ist trennbar, und nach der Trennung der Variablen
liefert die Resubstitution die Lösung $y$. Wie in Kapitel 8.4 prüfen wir, ob
Nullstellen zusätzliche Lösungen ergeben. In Kapitel 9.2 lernen wir mit den
linearen DGL eine Klasse kennen, deren Lösungen immer nach demselben Muster
aufgebaut sind, sodass wir keine passende Substitution suchen müssen. Ganz
verschwindet die Substitution aber nicht: In Kapitel 10.2 macht sie aus einer
nichtlinearen DGL eine lineare.
