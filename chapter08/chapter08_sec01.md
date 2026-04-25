---
authors:
  - name: Simone Gramsch
---

# 8.1 Lineare Differentialgleichungen: Struktur erkennen und benennen

In Kapitel 7 haben wir zwei Lösungsverfahren für ODEs 1. Ordnung kennengelernt: die
Trennung der Variablen und die Substitution. Beide greifen, wenn die rechte Seite eine
bestimmte algebraische Struktur hat. Viele ODEs, die in der Ingenieurpraxis auftreten,
besitzen eine noch tiefere Eigenschaft, die wir bisher nicht explizit benannt haben:
**Linearität**. Die Fallschirmspringer-Gleichung $\dot{v} + kv = 9{,}81~\text{m\,s}^{-2}$
aus Kapitel 6 ist ein erstes Beispiel dafür. In diesem Abschnitt lernen wir, was Linearität
bedeutet, wie sie sich in der Gleichungsstruktur zeigt und welche weiteren Unterscheidungen
für lineare ODEs relevant sind. Das Verständnis dieser Klassifikation ist die Voraussetzung
für die Lösungstheorie, die in den folgenden Abschnitten entwickelt wird.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, wie eine **lineare gewöhnliche Differentialgleichung** definiert ist,
  und können sie von einer nichtlinearen DGL unterscheiden.
* [ ] Sie können eine lineare DGL als **homogen** oder **inhomogen** klassifizieren und
  wissen, dass die Störfunktion $g(x)$ den Unterschied ausmacht.
* [ ] Sie wissen, dass jede homogene lineare DGL die **triviale Lösung** $y(x) = 0$
  besitzt.
* [ ] Sie können eine lineare DGL **mit konstanten Koeffizienten** von einer linearen DGL
  mit variablen Koeffizienten unterscheiden.
```

## Was bedeutet es, dass eine ODE "linear" ist?

Wir betrachten noch einmal die Fallschirmspringer-Gleichung in der Form, die wir in
Abschnitt 6.1 aufgestellt haben:

\begin{equation*}
\dot{v} + k\,v = 9{,}81~\text{m\,s}^{-2}.
\end{equation*}

Die gesuchte Funktion $v(t)$ und ihre Ableitung $\dot{v}$ erscheinen beide genau zur
ersten Potenz. Sie werden nicht miteinander multipliziert, nicht quadriert und nicht in
eine nichtlineare Funktion wie $\sin$ oder $\exp$ eingesetzt. Genau das meinen wir mit
Linearität: Die unbekannte Funktion und alle ihre Ableitungen treten ausschließlich linear
auf.

*Was würde die Linearität zerstören?* Bereits eine kleine Modifikation des Modells reicht.
Wäre der Luftwiderstand quadratisch in der Geschwindigkeit, also $F_L = b\,v^2$ statt
$F_L = b\,v$, so lautete die ODE:

\begin{equation*}
\dot{v} + k\,v^2 = 9{,}81~\text{m\,s}^{-2}.
\end{equation*}

Hier erscheint $v^2$. Das ist kein linearer Term, und die Gleichung ist nichtlinear.
Ebenso nichtlinear wären $\dot{v} = \sin(v)$ oder $\dot{v} \cdot v = 1$: im ersten Fall
steckt $v$ in einer nichtlinearen Funktion, im zweiten Beispiel werden $\dot{v}$ und $v$
miteinander multipliziert.

Die allgemeine Form einer linearen ODE $n$-ter Ordnung lautet:

\begin{equation*}
y^{(n)} + a_{n-1}(x)\,y^{(n-1)} + \cdots + a_1(x)\,y' + a_0(x)\,y = g(x).
\end{equation*}

Jede Ableitung $y^{(k)}$ tritt genau einmal und zur ersten Potenz auf, multipliziert mit
einem Koeffizient $a_k(x)$, der von $x$ abhängen darf, aber nicht von $y$. Die rechte
Seite $g(x)$ hängt ebenfalls nur von $x$ ab.

```{admonition} Was ist ... eine lineare ODE?
:class: note
Eine **lineare gewöhnliche Differentialgleichung** $n$-ter Ordnung hat die Form

\begin{equation*}
y^{(n)} + a_{n-1}(x)\,y^{(n-1)} + \cdots + a_1(x)\,y' + a_0(x)\,y = g(x),
\end{equation*}

wobei die Koeffizientenfunktionen $a_0(x), \ldots, a_{n-1}(x)$ und die rechte Seite
$g(x)$ nur von $x$ abhängen. Die gesuchte Funktion $y$ und alle ihre Ableitungen
erscheinen ausschließlich zur ersten Potenz und werden nicht miteinander multipliziert.

Eine ODE, die diese Form nicht hat, heißt **nichtlinear**.
```

Die Fallschirmspringer-Gleichung $\dot{v} + k\,v = 9{,}81~\text{m\,s}^{-2}$ ist eine
lineare ODE 1. Ordnung mit $n = 1$, $a_0(t) = k$ und $g(t) = 9{,}81~\text{m\,s}^{-2}$.
Die Torricellische Ausflussgleichung $\dot{h} = -k\sqrt{h}$ aus Abschnitt 7.3 ist
hingegen nichtlinear: $\sqrt{h} = h^{1/2}$ ist kein linearer Term in $h$.

## Homogen oder inhomogen?

Innerhalb der linearen ODEs gibt es eine weitere wichtige Unterscheidung. Wir schauen auf
die rechte Seite der allgemeinen Form, die Funktion $g(x)$.

Bei der Fallschirmspringer-Gleichung $\dot{v} + k\,v = 9{,}81~\text{m\,s}^{-2}$ ist die
rechte Seite die konstante Funktion $g(t) = 9{,}81~\text{m\,s}^{-2}$, die nirgends gleich
null ist. Das physikalische Bild dahinter: Die Schwerkraft treibt das System ständig an,
auch wenn die Geschwindigkeit null ist. Eine solche ODE heißt **inhomogen**.

Streichen wir die Antriebskraft, ergibt sich die vereinfachte Gleichung
$\dot{v} + k\,v = 0$. Physikalisch beschreibt das einen Körper, der ohne äußere Kraft
nur durch Reibung gebremst wird. Hier ist $g(t) = 0$ für alle $t$. Eine solche ODE heißt
**homogen**.

```{admonition} Was ist ... eine homogene und eine inhomogene lineare ODE?
:class: note
Eine lineare ODE

\begin{equation*}
y^{(n)} + a_{n-1}(x)\,y^{(n-1)} + \cdots + a_0(x)\,y = g(x)
\end{equation*}

heißt **homogen**, wenn $g(x) = 0$ für alle $x$ im Definitionsbereich gilt, und
**inhomogen**, wenn $g(x)$ nicht identisch null ist. Die Funktion $g(x)$ auf der rechten
Seite heißt **Störfunktion**.
```

Die homogene Form spielt in der Lösungstheorie eine zentrale Rolle. *Warum?* Weil jede
homogene lineare ODE eine ausgezeichnete Lösung besitzt, die wir sofort hinschreiben
können: die **triviale Lösung** $y(x) = 0$. Einsetzen bestätigt das sofort, denn alle
Ableitungen von $y = 0$ sind ebenfalls null:

\begin{equation*}
0^{(n)} + a_{n-1}(x)\cdot 0 + \cdots + a_0(x)\cdot 0 = 0 = g(x). \quad \checkmark
\end{equation*}

Diese triviale Lösung ist mathematisch wenig interessant, aber sie zeigt eine tiefe
Eigenschaft linearer ODEs: Das System „ruht" immer bei $y = 0$. In der Schwingungslehre,
die Sie in der Technischen Mechanik vertiefen werden, entspricht das dem ungestörten
Gleichgewichtszustand. Die Störfunktion $g(x)$ beschreibt dann eine äußere Anregung,
die das System aus diesem Gleichgewicht herausreißt.

## Konstante oder variable Koeffizienten?

Eine weitere Unterscheidung betrifft die Koeffizientenfunktionen $a_0(x), \ldots,
a_{n-1}(x)$. Hängen sie wirklich von $x$ ab, oder sind sie Konstanten?

Bei der Fallschirmspringer-Gleichung $\dot{v} + k\,v = 9{,}81~\text{m\,s}^{-2}$ ist
der Koeffizient vor $v$ die Konstante $k = 0{,}2~\text{s}^{-1}$. Sie hängt nicht von
$t$ ab. Das ist eine lineare ODE **mit konstanten Koeffizienten**.

Betrachten wir zum Vergleich die Gleichung

\begin{equation*}
y' + \frac{1}{x}\,y = x^2.
\end{equation*}

Hier ist der Koeffizient vor $y$ die Funktion $\frac{1}{x}$, die von $x$ abhängt.
Das ist eine lineare ODE **mit variablen Koeffizienten**. Solche Gleichungen treten
beispielsweise in der Wärmeübertragung auf, wenn der Wärmeübergangskoeffizient entlang
einer Kühlrippe mit dem Ort variiert, oder in der Strukturmechanik bei Balken mit
veränderlichem Querschnitt.

```{admonition} Was ist ... eine lineare ODE mit konstanten Koeffizienten?
:class: note
Eine lineare ODE heißt **lineare ODE mit konstanten Koeffizienten**, wenn alle
Koeffizientenfunktionen $a_0, \ldots, a_{n-1}$ konstant sind, also nicht von $x$
abhängen. Andernfalls spricht man von einer linearen ODE mit **variablen Koeffizienten**.
```

Für die Lösungstheorie ist diese Unterscheidung entscheidend: Lineare ODEs mit konstanten
Koeffizienten lassen sich vollständig und systematisch lösen, wie wir in den Abschnitten
8.2 und 8.3 sehen werden. Bei variablen Koeffizienten ist das im Allgemeinen schwieriger
und gelingt nur für spezielle Typen. Kapitel 8 konzentriert sich daher auf den Fall
konstanter Koeffizienten.

## Klassifikation auf einen Blick

Die drei Unterscheidungen lassen sich an konkreten Beispielen direkt ablesen:

| ODE | Linear? | Homogen? | Koeffizienten |
| --- | --- | --- | --- |
| $\dot{v} + k\,v = 9{,}81~\text{m\,s}^{-2}$ | ja | nein | konstant |
| $\dot{v} + k\,v = 0$ | ja | ja | konstant |
| $y' + \tfrac{1}{x}\,y = x^2$ | ja | nein | variabel |
| $\dot{h} + k\sqrt{h} = 0$ | nein | — | — |
| $y' = y^2$ | nein | — | — |

Bei nichtlinearen ODEs entfällt die Unterscheidung in homogen und inhomogen: Sie ist nur
für lineare ODEs definiert.

## Zusammenfassung und Ausblick

Eine lineare ODE zeichnet sich dadurch aus, dass die gesuchte Funktion und alle ihre
Ableitungen ausschließlich zur ersten Potenz auftreten. Innerhalb dieser Klasse
unterscheiden wir nach der Störfunktion $g(x)$: Bei $g(x) = 0$ ist die ODE homogen und
besitzt stets die triviale Lösung $y = 0$; bei $g(x) \not\equiv 0$ ist sie inhomogen.
Eine weitere Unterscheidung betrifft die Koeffizientenfunktionen: Konstante Koeffizienten
ermöglichen eine vollständige Lösungstheorie, während variable Koeffizienten den
Lösungsaufwand erheblich steigern.

In Abschnitt 8.2 entwickeln wir das Lösungsverfahren für lineare ODEs 1. Ordnung mit
konstanten Koeffizienten. Das Schlüsselwerkzeug ist die Variation der Konstanten, eine
Methode, die die homogene Lösung als Ausgangspunkt nimmt und daraus die vollständige
Lösung der inhomogenen Gleichung konstruiert.
