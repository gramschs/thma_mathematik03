---
authors:
  - name: Simone Gramsch
---

# 11.3 Die charakteristische Gleichung: der Fall reeller Eigenwerte

In Abschnitt 10.2 haben wir gesehen, dass die allgemeine Lösung der homogenen
ODE 2. Ordnung die Form $y_h = C_1 y_1 + C_2 y_2$ hat, sobald $y_1$ und $y_2$
ein Fundamentalsystem bilden. Was noch fehlt, ist ein systematisches Verfahren,
um solche Fundamentallösungen zu finden, ohne raten zu müssen. Die Idee stammt
aus Abschnitt 8.2: Weil die Lösung einer homogenen linearen ODE mit konstanten
Koeffizienten stets eine Exponentialfunktion ist oder aus ihr hervorgeht, liegt
der Exponentialansatz nahe. Bei der ODE 2. Ordnung führt er auf eine quadratische
Gleichung, deren Lösungen direkt die Fundamentallösungen liefern.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können den **Exponentialansatz** $y(x) = e^{\lambda x}$ in die homogene
  lineare ODE 2. Ordnung einsetzen und daraus die **charakteristische Gleichung**
  $\lambda^2 + a\lambda + b = 0$ herleiten.
* [ ] Sie können die Diskriminante $D = \tfrac{a^2}{4} - b$ berechnen und die
  Fälle $D > 0$ und $D = 0$ identifizieren.
* [ ] Sie können für $D > 0$ die zwei reellen Eigenwerte $\lambda_1 \neq \lambda_2$
  bestimmen und das Fundamentalsystem $\{e^{\lambda_1 x},\, e^{\lambda_2 x}\}$
  angeben.
* [ ] Sie können für $D = 0$ den doppelten Eigenwert $\lambda$ bestimmen und das
  Fundamentalsystem $\{e^{\lambda x},\, x\,e^{\lambda x}\}$ angeben.
* [ ] Sie können für beide Fälle die allgemeine Lösung
  $y_h(x) = C_1 y_1(x) + C_2 y_2(x)$ aufschreiben und an Anfangsbedingungen
  anpassen.
```

## Wie führt der Exponentialansatz auf eine quadratische Gleichung?

Wir betrachten die homogene lineare ODE 2. Ordnung mit konstanten Koeffizienten:

\begin{equation*}
y''(x) + a\,y'(x) + b\,y(x) = 0, \quad a, b \in \mathbb{R}.
\end{equation*}

In Abschnitt 8.2 hat der Exponentialansatz für die ODE 1. Ordnung funktioniert,
weil Ableiten einer Exponentialfunktion wieder eine Exponentialfunktion ergibt.
Dasselbe gilt für die zweite Ableitung. Wir setzen $y(x) = e^{\lambda x}$ an
und berechnen:

\begin{equation*}
y = e^{\lambda x}, \qquad y' = \lambda\,e^{\lambda x}, \qquad
y'' = \lambda^2\,e^{\lambda x}.
\end{equation*}

Einsetzen in die ODE ergibt:

\begin{equation*}
\lambda^2\,e^{\lambda x} + a\,\lambda\,e^{\lambda x} + b\,e^{\lambda x} = 0.
\end{equation*}

Da $e^{\lambda x} > 0$ für alle $x$, dürfen wir durch $e^{\lambda x}$ dividieren
und erhalten die charakteristische Gleichung:

\begin{equation*}
\lambda^2 + a\,\lambda + b = 0.
\end{equation*}

```{admonition} Was ist ... die charakteristische Gleichung einer ODE 2. Ordnung?
:class: note
Die quadratische Gleichung

\begin{equation*}
\lambda^2 + a\,\lambda + b = 0
\end{equation*}

heißt **charakteristische Gleichung** der homogenen linearen ODE 2. Ordnung
$y'' + ay' + by = 0$. Ihre Lösungen $\lambda$ heißen **Eigenwerte** der ODE.
Jeder Eigenwert $\lambda$ liefert eine Lösung $e^{\lambda x}$ der homogenen ODE.
```

Diese Gleichung begegnet uns hier nicht zum ersten Mal: In Abschnitt 4.6 haben
wir die Eigenwerte einer $2\times 2$-Matrix als Nullstellen des charakteristischen
Polynoms $\det(\mathbf{A} - \lambda\mathbf{E}) = 0$ bestimmt, das für
$2\times 2$-Matrizen ebenfalls auf eine quadratische Gleichung führt. Der
Zusammenhang ist kein Zufall und wird in der linearen Algebra vertieft.

Die Lösungsformel für die charakteristische Gleichung lautet mit der
Diskriminante $D = a^2/4 - b$:

\begin{equation*}
\lambda_{1,2} = -\frac{a}{2} \pm \sqrt{D}.
\end{equation*}

Je nach Vorzeichen von $D$ entstehen drei strukturell verschiedene Fälle. Dieser
Abschnitt behandelt $D > 0$ und $D = 0$; der Fall $D < 0$ folgt in Abschnitt
10.4.

## Der Fall $D > 0$: stark gedämpfte Schwebebahn

Für $D > 0$ liefert die Lösungsformel zwei verschiedene reelle Eigenwerte
$\lambda_1 \neq \lambda_2$. Jeder ergibt eine Lösung der homogenen ODE.
Da $\lambda_1 \neq \lambda_2$, sind die beiden Exponentialfunktionen linear
unabhängig. Wir rechnen das mit der Wronski-Determinante nach:

\begin{align*}
W(e^{\lambda_1 x}, e^{\lambda_2 x})
&= e^{\lambda_1 x}\cdot\lambda_2\,e^{\lambda_2 x} -
 e^{\lambda_2 x}\cdot\lambda_1\,e^{\lambda_1 x}
 = (\lambda_2 - \lambda_1)\,e^{(\lambda_1+\lambda_2)x} \neq 0,
\end{align*}

denn $\lambda_1 \neq \lambda_2$ und $e^{(\lambda_1+\lambda_2)x} > 0$ für alle $x$.

```{admonition} Fundamentalsystem für $D > 0$
:class: note
Sind $\lambda_1 \neq \lambda_2$ zwei reelle Lösungen der charakteristischen
Gleichung, so ist $\{e^{\lambda_1 x},\, e^{\lambda_2 x}\}$ ein Fundamentalsystem
und die allgemeine Lösung lautet

\begin{equation*}
y_h(x) = C_1\,e^{\lambda_1 x} + C_2\,e^{\lambda_2 x}, \quad C_1, C_2 \in \mathbb{R}.
\end{equation*}
```

Wenn die Dämpfungskonstante der Schwebebahn so groß gewählt wird, dass $D > 0$
gilt, kehrt der Fahrwagen nach einer Auslenkung ohne Schwingung in die Ruhelage
zurück. Dieses Verhalten nennt man in der Schwingungslehre **Kriechfall** oder
**aperiodisches Verhalten**.

Wir wählen $a = 4.0~\text{s}^{-1}$ und $b = \omega_0^2 \approx 3.27~\text{s}^{-2}$.
Die Diskriminante ist

\begin{equation*}
D = \frac{(4.0)^2}{4} - 3.27 = 4.00 - 3.27 = 0.73~\text{s}^{-2} > 0.
\end{equation*}

Die Eigenwerte lauten:

\begin{equation*}
\lambda_{1,2} = -2.0 \pm \sqrt{0.73} = -2.0 \pm 0.854~\text{s}^{-1},
\end{equation*}

also $\lambda_1 \approx -1.15~\text{s}^{-1}$ und $\lambda_2 \approx -2.85~\text{s}^{-1}$.
Beide Eigenwerte sind negativ, sodass beide Exponentialterme für $t \to \infty$
abklingen. Die allgemeine Lösung lautet:

\begin{equation*}
\varphi_h(t) = C_1\,e^{-1.15\,t} + C_2\,e^{-2.85\,t}.
\end{equation*}

Aus den Anfangsbedingungen $\varphi(0) = 0.231$ und $\varphi'(0) = 0$ folgt das
Gleichungssystem

\begin{align*}
C_1 + C_2 &= 0.231, \\
-1.15\,C_1 - 2.85\,C_2 &= 0.
\end{align*}

Aus der zweiten Gleichung ergibt sich $C_1 = -2.48\,C_2$. Einsetzen in die erste:

\begin{equation*}
-2.48\,C_2 + C_2 = -1.48\,C_2 = 0.231
\qquad \Rightarrow \qquad
C_2 \approx -0.156, \quad C_1 \approx 0.387.
\end{equation*}

Die partikuläre Lösung des Anfangswertproblems lautet:

\begin{equation*}
\varphi(t) = 0.387\,e^{-1.15\,t} - 0.156\,e^{-2.85\,t}.
\end{equation*}

*Was sagt das physikalisch?* Der Wagen kehrt ohne eine einzige Schwingung
in die Ruhelage zurück. Der schnellere Term $e^{-2.85\,t}$ bestimmt das
Anfangsverhalten, der langsamere Term $e^{-1.15\,t}$ das Langzeitverhalten.
Ob das für den Fahrkomfort optimal ist, wird in Kapitel 11 untersucht, wenn
erzwungene Schwingungen durch äußere Anregung hinzukommen.

## Der Fall $D = 0$: aperiodischer Grenzfall

Wenn $D$ genau null ist, hat die charakteristische Gleichung einen doppelten
Eigenwert:

\begin{equation*}
\lambda = -\frac{a}{2}.
\end{equation*}

Das liefert zunächst nur eine Fundamentallösung $y_1 = e^{\lambda x}$. *Woher
kommt die zweite?* Man kann zeigen, dass $y_2(x) = x\,e^{\lambda x}$ ebenfalls
die homogene ODE erfüllt. Wir überprüfen das durch direktes Einsetzen. Die
Ableitungen von $y_2$ lauten:

\begin{align*}
y_2' &= e^{\lambda x} + \lambda x\,e^{\lambda x} = (1 + \lambda x)\,e^{\lambda x}, \\
y_2'' &= \lambda\,e^{\lambda x} + \lambda\,(1 + \lambda x)\,e^{\lambda x}
        = (2\lambda + \lambda^2 x)\,e^{\lambda x}.
\end{align*}

Einsetzen in $y'' + ay' + by$:

\begin{align*}
y_2'' + a\,y_2' + b\,y_2
&= e^{\lambda x}\Bigl[(2\lambda + a) +
   \underbrace{(\lambda^2 + a\lambda + b)}_{=\,0}\cdot x\Bigr]
 = e^{\lambda x}\!\left[2\left(-\tfrac{a}{2}\right) + a\right]
 = 0. \quad \checkmark
\end{align*}

Die Wronski-Determinante bestätigt die lineare Unabhängigkeit von $y_1$ und $y_2$:

\begin{equation*}
W(e^{\lambda x}, x\,e^{\lambda x})
= e^{\lambda x}\cdot(1 + \lambda x)\,e^{\lambda x} -
x\,e^{\lambda x}\cdot\lambda\,e^{\lambda x}
= e^{2\lambda x}(1 + \lambda x - \lambda x)
= e^{2\lambda x} \neq 0.
\end{equation*}

```{admonition} Fundamentalsystem für $D = 0$
:class: note
Hat die charakteristische Gleichung den doppelten Eigenwert $\lambda = -a/2$,
so ist $\{e^{\lambda x},\, x\,e^{\lambda x}\}$ ein Fundamentalsystem und die
allgemeine Lösung lautet

\begin{equation*}
y_h(x) = (C_1 + C_2\,x)\,e^{\lambda x}, \quad C_1, C_2 \in \mathbb{R}.
\end{equation*}
```

Den Fall $D = 0$ nennt man in der Schwingungslehre den **aperiodischen
Grenzfall**: Es ist genau die Grenze zwischen schwingendem und kriechendem
Verhalten. Die zugehörige Dämpfungskonstante heißt **kritische Dämpfung**.

Für die Schwebebahn tritt kritische Dämpfung bei $a = 2\omega_0$ auf. Mit
$\omega_0 \approx 1.81~\text{s}^{-1}$ ist $a = 3.62~\text{s}^{-1}$.
Probe: $D = (3.62)^2/4 - 3.27 = 3.27 - 3.27 = 0$. Der doppelte Eigenwert
ist $\lambda = -1.81~\text{s}^{-1}$, und die allgemeine Lösung lautet

\begin{equation*}
\varphi_h(t) = (C_1 + C_2\,t)\,e^{-1.81\,t}.
\end{equation*}

Die Anfangsbedingungen $\varphi(0) = 0.231$ und $\varphi'(0) = 0$ ergeben:

\begin{align*}
\varphi(0) &= C_1 \stackrel{!}{=} 0.231, \\
\varphi'(0) &= C_2 - 1.81\cdot C_1 = C_2 - 0.418 \stackrel{!}{=} 0
\quad \Rightarrow \quad C_2 = 0.418.
\end{align*}

Die partikuläre Lösung lautet:

\begin{equation*}
\varphi(t) = (0.231 + 0.418\,t)\,e^{-1.81\,t}.
\end{equation*}

Der Wagen kehrt ohne Schwingung und dabei schnellstmöglich in die Ruhelage
zurück. In der Regelungstechnik und im Fahrzeugbau ist die kritische Dämpfung
daher ein häufiges Auslegungsziel.

```{dropdown} Video "Allgemeine Lösung" von Prof. Hielscher (TH Mannheim)
<iframe width="1106" height="702" src="https://www.youtube.com/embed/ofiDXMH428k?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07" title="Allgemeine Lösung der homogenen linearen DGL 2. Ordnung mit konstanten Koeffizienten" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Allgemeine Lösung Teil 2" von Prof. Hielscher (TH Mannheim)
<iframe width="1106" height="702" src="https://www.youtube.com/embed/kAshQrZljU4?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07" title="Allgemeine Lösungen der homogenen linearen DGL 2. Ordnung mit konstanten Koeffizienten - Teil 2" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Homogene Differentialgleichung 2. Ordnung (Teil 1)" von lernflix
<iframe width="1129" height="635" src="https://www.youtube.com/embed/S-3obH19RDo" title="Wie löse
ich eine homogene Differentialgleichung 2. Ordnung? | reelle  homogene Lösung" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture;
web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Homogene Differentialgleichung 2. Ordnung (Teil 2)" von lernflix
<iframe width="1129" height="635" src="https://www.youtube.com/embed/d8DJ4UkQMnQ?list=PLjVetqThgyWUzbQ8KdoaCGLwT7F2LUIVA" title="Wie löse ich eine homogene Differentialgleichung 2.Ordnung? | doppelte homogene Lösung | DGL" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Lineare DGL 2. Ordnung" von Mathe mit Nina
<iframe width="1129" height="635" src="https://www.youtube.com/embed/MZxec3G6AUI"
title="Lineare DGL 2. Ordnung - homogene Lösung Fallunterscheidung - schnell und einfach erklärt" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

## Zusammenfassung und Ausblick

Der Exponentialansatz $y = e^{\lambda x}$ reduziert die homogene ODE 2. Ordnung
auf die charakteristische Gleichung $\lambda^2 + a\lambda + b = 0$. Für $D > 0$
liefern zwei verschiedene reelle Eigenwerte direkt das Fundamentalsystem; für
$D = 0$ ergänzt das Produkt $x\,e^{\lambda x}$ die einzige Exponentiallösung zu
einem vollständigen Fundamentalsystem. In beiden Fällen klingen die Lösungen
monoton ab, sofern die Eigenwerte negativ sind.

Noch nicht behandelt ist der Fall $D < 0$: Die charakteristische Gleichung hat
dann keine reellen Lösungen, und der Exponentialansatz liefert zunächst komplexe
Ausdrücke. Abschnitt 10.4 zeigt, wie die Euler-Formel diese in reelle Kosinus-
und Sinusfunktionen umschreibt, und erklärt damit, warum die ungedämpfte
Schwebebahn aus Abschnitt 10.1 mit $\cos(\omega_0 t)$ und $\sin(\omega_0 t)$
schwingt.
