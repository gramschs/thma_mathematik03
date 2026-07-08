---
authors:
  - name: Simone Gramsch
---

# 11.4 Komplexe Eigenwerte und das Modell der gedämpften Schwingung

In Abschnitt 10.3 haben wir gesehen, dass die charakteristische Gleichung für
$D > 0$ oder $D = 0$ reelle Eigenwerte liefert und die zugehörigen Lösungen
monoton gegen null abklingen. Die Schwebebahn schwingt in diesen Fällen nicht,
sondern kriecht zurück in die Ruhelage. *Aber genau das hat die Bahn in der
Realität nicht getan*: Sie pendelt mehrmals hin und her. Das ist der Fall $D <
0$, bei dem die charakteristische Gleichung keine reellen Lösungen besitzt. Der
Exponentialansatz liefert dann komplexe Eigenwerte, und es braucht einen
weiteren Schritt, um daraus reelle Fundamentallösungen zu gewinnen. Dieser
Schritt ist die eulersche Formel, die komplexe Exponentialfunktionen mit Kosinus
und Sinus verbindet.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können für $D < 0$ die beiden konjugiert komplexen Eigenwerte
  \begin{equation*}\lambda_{1,2} = -\alpha \pm i\,\omega_d\end{equation*}
  bestimmen und Real- und Imaginärteil benennen.
* [ ] Sie wissen, wie die **eulersche Formel** $e^{i\varphi} = \cos\varphi +
  i\sin\varphi$ genutzt wird, um komplexe Exponentialfunktionen in reelle
  Lösungen umzuschreiben.
* [ ] Sie können das **reelle Fundamentalsystem**
  $\{e^{-\alpha x}\cos(\omega_d x),\; e^{-\alpha x}\sin(\omega_d x)\}$ angeben
  und die allgemeine Lösung
  \begin{equation*}
  y_h(x) = e^{-\alpha x}\bigl(C_1\cos(\omega_d x) + C_2\sin(\omega_d x)\bigr)
  \end{equation*}
  aufschreiben.
* [ ] Sie können die Parameter $\alpha$ (Abklingrate) und $\omega_d$ (gedämpfte
  Kreisfrequenz) physikalisch als **gedämpfte Schwingung** interpretieren und
  von der ungedämpften Eigenkreisfrequenz $\omega_0$ aus Abschnitt 10.1
  unterscheiden.
```

## Wie entstehen komplexe Eigenwerte?

Für $D < 0$ ist der Ausdruck unter der Wurzel in der Lösungsformel
$\lambda_{1,2} = -a/2 \pm \sqrt{D}$ negativ. Wir schreiben $D = -|D|$ und
erhalten:

\begin{equation*}
\lambda_{1,2} = -\frac{a}{2} \pm \sqrt{-|D|}
              = -\frac{a}{2} \pm i\sqrt{|D|}.
\end{equation*}

Wir führen zwei Abkürzungen ein:

\begin{equation*}
\alpha = \frac{a}{2} \geq 0
\qquad \text{und} \qquad
\omega_d = \sqrt{|D|} = \sqrt{b - \frac{a^2}{4}} > 0.
\end{equation*}

Die Eigenwerte sind dann das konjugiert komplexe Paar
$\lambda_{1,2} = -\alpha \pm i\,\omega_d$. Die Größe $\alpha$ heißt
**Abklingrate** und $\omega_d$ heißt **gedämpfte Kreisfrequenz**. Im Unterschied
zur ungedämpften Eigenkreisfrequenz $\omega_0 = \sqrt{b}$ aus Abschnitt 10.1
gilt stets $\omega_d < \omega_0$: Dämpfung verlangsamt die Schwingung.

Der Exponentialansatz liefert zunächst die komplexwertigen Lösungen

\begin{equation*}
y_1(x) = e^{(-\alpha + i\omega_d)x}
\quad \text{und} \quad
y_2(x) = e^{(-\alpha - i\omega_d)x}.
\end{equation*}

Für die Praxis brauchen wir reelle Lösungen. Die eulersche Formel stellt die
Verbindung her.

## Die eulersche Formel: von komplex nach reell

Die **eulersche Formel**

\begin{equation*}
e^{i\varphi} = \cos\varphi + i\sin\varphi, \quad \varphi \in \mathbb{R},
\end{equation*}

verknüpft die komplexe Exponentialfunktion mit Kosinus und Sinus. Sie ist nicht
mit dem Euler-Verfahren aus Abschnitt 6.3 zu verwechseln: Beide tragen den
Namen desselben Mathematikers, beschreiben aber völlig verschiedene Dinge. Die
eulersche Formel folgt formal aus den Potenzreihen von $e^z$, $\cos$ und $\sin$.

Wir wenden sie auf die komplexen Fundamentallösungen an:

\begin{align*}
e^{(-\alpha + i\omega_d)x}
&= e^{-\alpha x}\cdot e^{i\omega_d x}
 = e^{-\alpha x}\bigl(\cos(\omega_d x) + i\sin(\omega_d x)\bigr), \\
e^{(-\alpha - i\omega_d)x}
&= e^{-\alpha x}\cdot e^{-i\omega_d x}
 = e^{-\alpha x}\bigl(\cos(\omega_d x) - i\sin(\omega_d x)\bigr).
\end{align*}

Da die ODE reelle Koeffizienten hat, ist mit jeder komplexen Lösung auch ihr
Realteil und ihr Imaginärteil eine reelle Lösung. Wir bilden die Summe und
Differenz der beiden komplexen Lösungen:

\begin{align*}
\tilde{y}_1(x)
&= \frac{1}{2}\bigl(e^{\lambda_1 x} + e^{\lambda_2 x}\bigr)
 = e^{-\alpha x}\cos(\omega_d x), \\
\tilde{y}_2(x)
&= \frac{1}{2i}\bigl(e^{\lambda_1 x} - e^{\lambda_2 x}\bigr)
 = e^{-\alpha x}\sin(\omega_d x).
\end{align*}

Beide Funktionen sind reell, und da sie aus Linearkombinationen zweier
Lösungen entstehen, sind sie selbst Lösungen der homogenen ODE.

## Das reelle Fundamentalsystem

Wir berechnen die Wronski-Determinante von $\tilde{y}_1$ und $\tilde{y}_2$, um
lineare Unabhängigkeit zu bestätigen. Mit $u = e^{-\alpha x}\cos(\omega_d x)$
und $v = e^{-\alpha x}\sin(\omega_d x)$ lauten die Ableitungen:

\begin{align*}
u' &= e^{-\alpha x}\bigl(-\alpha\cos(\omega_d x) - \omega_d\sin(\omega_d x)\bigr), \\
v' &= e^{-\alpha x}\bigl(-\alpha\sin(\omega_d x) + \omega_d\cos(\omega_d x)\bigr).
\end{align*}

Die Wronski-Determinante ergibt:

\begin{align*}
W(u, v)
&= u\,v' - v\,u' \\
&= e^{-2\alpha x}\Bigl[
   \cos(\omega_d x)\bigl(-\alpha\sin + \omega_d\cos\bigr) -
   \sin(\omega_d x)\bigl(-\alpha\cos - \omega_d\sin\bigr)
   \Bigr] \\
&= e^{-2\alpha x}\bigl[-\alpha\cos\sin + \omega_d\cos^2 + \alpha\sin\cos + \omega_d\sin^2
   \bigr] \\
&= \omega_d\,e^{-2\alpha x}
   \underbrace{\bigl(\cos^2(\omega_d x) + \sin^2(\omega_d x)\bigr)}_{=\,1}
 = \omega_d\,e^{-2\alpha x} \neq 0,
\end{align*}

denn $\omega_d > 0$ und $e^{-2\alpha x} > 0$ für alle $x$.

```{admonition} Fundamentalsystem für $D < 0$
:class: note
Haben die Eigenwerte der charakteristischen Gleichung den konjugiert komplexen
Wert $\lambda_{1,2} = -\alpha \pm i\,\omega_d$ mit $\alpha = a/2$ und
$\omega_d = \sqrt{b - a^2/4}$, so ist
$\{e^{-\alpha x}\cos(\omega_d x),\; e^{-\alpha x}\sin(\omega_d x)\}$
ein Fundamentalsystem und die allgemeine Lösung lautet

\begin{equation*}
y_h(x) = e^{-\alpha x}\bigl(C_1\cos(\omega_d x) + C_2\sin(\omega_d x)\bigr),
\quad C_1, C_2 \in \mathbb{R}.
\end{equation*}
```

## Die Schwebebahn im schwach gedämpften Fall

Wir wählen $a = 1.0~\text{s}^{-1}$ und $b = \omega_0^2 \approx 3.27~\text{s}^{-2}$.
Die Diskriminante ist

\begin{equation*}
D = \frac{(1.0)^2}{4} - 3.27 = 0.25 - 3.27 = -3.02~\text{s}^{-2} < 0.
\end{equation*}

Abklingrate und gedämpfte Kreisfrequenz lauten:

\begin{equation*}
\alpha = 0.5~\text{s}^{-1},
\qquad
\omega_d = \sqrt{3.02} \approx 1.74~\text{rad\,s}^{-1}.
\end{equation*}

Verglichen mit $\omega_0 \approx 1.81~\text{rad\,s}^{-1}$ ist $\omega_d$ etwas
kleiner: Die gedämpfte Schwingungsperiode beträgt $T_d = 2\pi/\omega_d \approx
3.61~\text{s}$ statt $T_0 \approx 3.47~\text{s}$. Die allgemeine Lösung lautet:

\begin{equation*}
\varphi_h(t) = e^{-0.5\,t}\bigl(C_1\cos(1.74\,t) + C_2\sin(1.74\,t)\bigr).
\end{equation*}

Die Anfangsbedingungen $\varphi(0) = 0.231$ und $\varphi'(0) = 0$ liefern
zunächst $C_1 = 0.231$. Die Ableitung bei $t = 0$ ergibt:

\begin{equation*}
\varphi'(0) = -\alpha C_1 + \omega_d C_2
= -0.5\cdot 0.231 + 1.74\cdot C_2 \stackrel{!}{=} 0
\qquad \Rightarrow \qquad
C_2 = \frac{0.116}{1.74} \approx 0.067.
\end{equation*}

Die partikuläre Lösung des Anfangswertproblems lautet:

\begin{equation*}
\varphi(t) = e^{-0.5\,t}\bigl(0.231\cos(1.74\,t) + 0.067\sin(1.74\,t)\bigr).
\end{equation*}

Der Faktor $e^{-0.5\,t}$ bestimmt, wie schnell die Schwingungsamplitude
abklingt. Nach einer gedämpften Periode $T_d \approx 3.61~\text{s}$ ist die
Hüllkurve auf $e^{-0.5\cdot 3.61} \approx 0.16$ des Ausgangswertes gesunken,
nach zwei Perioden auf etwa $0.03$. Der Fahrwagen schwingt also sichtbar, kehrt
aber innerhalb weniger Perioden in die Ruhelage zurück. *Ist das für die
Fahrgäste akzeptabel?* Das hängt vom Abstand zur nächsten Haltestelle ab: eine
ingenieurmäßige Auslegungsfrage, die über die Mathematik hinausgeht.

## Der vollständige Überblick: alle drei Fälle

Mit den Abschnitten 10.3 und 10.4 ist die Lösungstheorie für die homogene
lineare ODE 2. Ordnung mit konstanten Koeffizienten abgeschlossen. Die folgende
Tabelle fasst zusammen, welches Fundamentalsystem die charakteristische Gleichung
für jeden der drei Fälle liefert:

| Fall | Bedingung | Eigenwerte | Fundamentalsystem |
| ---- | --------- | ---------- | ----------------- |
| Kriechfall | $D > 0$ | $\lambda_1 \neq \lambda_2$ reell | $\{e^{\lambda_1 x},\, e^{\lambda_2 x}\}$ |
| Aperiod. Grenzfall | $D = 0$ | $\lambda$ doppelt reell | $\{e^{\lambda x},\, x\,e^{\lambda x}\}$ |
| Schwingungsfall | $D < 0$ | $-\alpha \pm i\omega_d$ komplex | $\{e^{-\alpha x}\cos(\omega_d x),\, e^{-\alpha x}\sin(\omega_d x)\}$ |

Für die Schwebebahn durchlaufen wir mit wachsender Dämpfungskonstante $a$ alle
drei Fälle: Bei kleinem $a$ schwingt der Wagen, beim kritischen Wert $a =
2\omega_0$ liegt der aperiodische Grenzfall vor, und bei starker Dämpfung
kriecht der Wagen ohne Überschwingen zurück.

```{dropdown} Video "Homogene DGL 2. Ordnung (Teil 3)" von lernflix
<iframe width="1129" height="635" src="https://www.youtube.com/embed/HbHhHP9domY"
title="Wie löse ich eine homogene Differentialgleichung 2. Ordnung? | komplexe homogene Lösung | DGL" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Hom. DGL 2. Ordnung" von Mathe ohne Magie
<iframe width="1129" height="635" src="https://www.youtube.com/embed/LN1WHesVpyc" title="Homogene lineare Differenzialgleichungen zweiter Ordnung mit konstanten Koeffizienten" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Die eulersche Formel überbrückt die Lücke zwischen komplexen Eigenwerten und
reellen Lösungen. Aus $e^{(-\alpha \pm i\omega_d)x}$ werden durch Real- und
Imaginärteiltrennung die Fundamentallösungen $e^{-\alpha x}\cos(\omega_d x)$
und $e^{-\alpha x}\sin(\omega_d x)$. Die allgemeine Lösung beschreibt eine
gedämpfte Schwingung, deren Amplitude exponentiell mit der Rate $\alpha$
abklingt und deren Frequenz $\omega_d$ kleiner als die ungedämpfte
Eigenkreisfrequenz $\omega_0$ ist.

Damit ist Kapitel 10 vollständig: Für jede homogene lineare ODE 2. Ordnung mit
konstanten Koeffizienten lässt sich das Fundamentalsystem systematisch aus den
Nullstellen der charakteristischen Gleichung bestimmen. In Kapitel 11 wird die
Störfunktion $g(x)$ hinzugefügt. Die partikuläre Lösung $y_p$ beschreibt den
erzwungenen Anteil der Schwingung, und ihr Zusammenspiel mit der homogenen
Lösung $y_h$ führt auf das zentrale Phänomen der Schwingungslehre: die Resonanz.
