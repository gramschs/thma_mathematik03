---
authors:
  - name: Simone Gramsch
---

# 8.2 Die homogene Lösung: warum ein Exponentialansatz funktioniert

In Abschnitt 8.1 haben wir lineare ODEs nach drei Kriterien klassifiziert: linear oder
nichtlinear, homogen oder inhomogen, konstante oder variable Koeffizienten. Jetzt lösen
wir die einfachste dieser Klassen: die homogene lineare ODE 1. Ordnung
$y' + f(x)\,y = 0$. Der Lösungsweg führt direkt über die Trennung der Variablen aus
Abschnitt 7.1, die wir bereits für die Fallschirmspringer-Gleichung eingesetzt haben.
Das Ergebnis ist stets eine Exponentialfunktion, und genau das erklärt rückblickend,
warum ein Exponentialansatz für lineare ODEs mit konstanten Koeffizienten der natürliche
erste Versuch ist. Dieses Prinzip bauen wir in Kapitel 10 für ODEs 2. Ordnung
systematisch aus.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können die allgemeine Lösung $y_h$ der homogenen linearen DGL 1. Ordnung
  $y' + f(x) \cdot y = 0$ mit Hilfe der Separation der Variablen herleiten.
* [ ] Sie können die Formel
  \begin{equation*}
  y_h(x) = A \cdot e^{-\int f(x)\, dx}, \quad A \in \mathbb{R}
  \end{equation*}
  auf eine gegebene homogene lineare DGL 1. Ordnung anwenden.
* [ ] Sie können den Sonderfall konstanter Koeffizienten $y' + ay = 0$ direkt lösen
  und die Lösung $y_h(x) = A \cdot e^{-ax}$ angeben.
```

## Was beschreibt die homogene Gleichung physikalisch?

Aus der Fallschirmspringer-Gleichung $\dot{v} + kv = 9{,}81~\text{m\,s}^{-2}$ wird die
zugehörige homogene ODE, indem wir die Störfunktion auf null setzen:

\begin{equation*}
\dot{v} + k\,v = 0.
\end{equation*}

Physikalisch beschreibt das einen Körper, der sich ausschließlich durch Luftreibung
verlangsamt, ohne dass eine äußere Kraft antreibt. *Was erwarten wir qualitativ?* Die
Geschwindigkeit sollte monoton abnehmen und sich asymptotisch dem Ruhezustand $v = 0$
annähern. Das stimmt mit der trivialen Lösung $v = 0$ überein, die in Abschnitt 8.1 für
jede homogene lineare ODE festgestellt wurde.

Die rechte Seite der homogenen ODE lässt sich als $f(t) \cdot g(v) = 1 \cdot (-kv)$
schreiben. Die Gleichung ist also separierbar, und wir können das Verfahren aus
Abschnitt 7.1 direkt anwenden.

## Wie leiten wir die homogene Lösung her?

Das Verfahren folgt den vier Schritten der Trennung der Variablen. Wir setzen $v \neq 0$
voraus und dividieren durch $v$:

**Schritt 1: Trennen.**

\begin{equation*}
\frac{dv}{v} = -k\,dt.
\end{equation*}

**Schritt 2 und 3: Integrieren und Stammfunktion einsetzen.**

\begin{equation*}
\int \frac{dv}{v} = \int -k\,dt
\quad \Rightarrow \quad
\ln|v| = -kt + C_1, \quad C_1 \in \mathbb{R}.
\end{equation*}

**Schritt 4: Auflösen.** Wir nehmen auf beiden Seiten die Exponentialfunktion und
fassen alle Konstanten in $A \in \mathbb{R}$ zusammen:

\begin{equation*}
v_h(t) = A\,e^{-kt}, \quad A \in \mathbb{R}.
\end{equation*}

Das Vorzeichen von $v$ wird in $A$ absorbiert; für $A = 0$ entsteht die triviale Lösung
$v = 0$, die damit automatisch enthalten ist.

**Verifikation.** Einsetzen in $\dot{v} + kv = 0$:

\begin{equation*}
\dot{v}_h + k\,v_h
  = -Ak\,e^{-kt} + k \cdot A\,e^{-kt}
  = 0. \quad \checkmark
\end{equation*}

Das physikalische Bild bestätigt die Erwartung: Für $k = 0{,}2~\text{s}^{-1}$ und
$A > 0$ klingt $v_h(t)$ exponentiell ab und strebt gegen null. Ohne antreibende Kraft
kommt der Körper durch Reibung zur Ruhe. In der Regelungstechnik, die Sie in höheren
Semestern kennenlernen werden, beschreibt genau diese Lösung das freie Einschwingen eines
Systems nach dem Abschalten des Eingangssignals.

## Die allgemeine Formel für beliebiges $f(x)$

Das gerade durchgeführte Verfahren überträgt sich wörtlich auf die allgemeine homogene
lineare ODE 1. Ordnung $y' + f(x)\,y = 0$. Wir trennen die Variablen für $y \neq 0$:

\begin{equation*}
\frac{dy}{y} = -f(x)\,dx.
\end{equation*}

Integration beider Seiten und Auflösen nach $y$ liefert:

\begin{equation*}
\ln|y| = -\int f(x)\,dx + C_1
\quad \Rightarrow \quad
y_h(x) = A\,e^{-\int f(x)\,dx}, \quad A \in \mathbb{R}.
\end{equation*}

```{admonition} Was ist ... die homogene Lösung einer linearen ODE 1. Ordnung?
:class: note
Die allgemeine Lösung der homogenen linearen ODE 1. Ordnung $y' + f(x)\,y = 0$ lautet

\begin{equation*}
y_h(x) = A\,e^{-\int f(x)\,dx}, \quad A \in \mathbb{R}.
\end{equation*}

Im Sonderfall konstanter Koeffizienten $f(x) = a = \mathrm{const}$ vereinfacht sich die
Formel zu

\begin{equation*}
y_h(x) = A\,e^{-ax}.
\end{equation*}

Die Funktion $y_h$ heißt **homogene Lösung**. Sie enthält eine freie Konstante $A$ und
bildet den ersten Baustein für die vollständige Lösung der inhomogenen Gleichung.
```

Für den Fallschirmspringer gilt $f(t) = k = 0{,}2~\text{s}^{-1}$, also
$\int f(t)\,dt = kt$. Die Formel liefert unmittelbar $v_h(t) = A\,e^{-kt}$, wie wir es
bereits durch explizite Rechnung hergeleitet haben.

## Was passiert bei variablem $f(x)$? Ein überraschendes Ergebnis

Die Stärke der Formel $y_h = A\,e^{-\int f(x)\,dx}$ zeigt sich erst bei variablen
Koeffizienten. Wir betrachten als zweites Beispiel:

\begin{equation*}
y' + 2x\,y = 0.
\end{equation*}

Hier ist $f(x) = 2x$. Das Integral des Koeffizienten ist $\int 2x\,dx = x^2$, also:

\begin{equation*}
y_h(x) = A\,e^{-x^2}, \quad A \in \mathbb{R}.
\end{equation*}

*Was ist das für eine Funktion?* Es ist die Gaußsche Glockenkurve, eine der bedeutendsten
Funktionen in Naturwissenschaft und Technik. In der Statistik beschreibt sie die
Normalverteilung, in der Messtechnik die Verteilung zufälliger Fehler, in der
Wärmeübertragung das Temperaturprofil eines Diffusionsvorgangs. Dass sie als Lösung einer
so einfachen ODE erscheint, ist kein Zufall: Die Trennungsmethode hat die Gaußkurve nicht
konstruiert, sondern zwingend aus der Gleichungsstruktur hergeleitet.

**Verifikation.** Einsetzen in $y' + 2xy = 0$:

\begin{align*}
y_h'(x) + 2x\,y_h(x)
  &= A\,(-2x)\,e^{-x^2} + 2x \cdot A\,e^{-x^2} \\
  &= -2Ax\,e^{-x^2} + 2Ax\,e^{-x^2} = 0. \quad \checkmark
\end{align*}

```{dropdown} Video "Homogene lineare DGL 1. Ordnung" von MathePeter
<iframe width="966" height="613"
  src="https://www.youtube.com/embed/PLACEHOLDER_MATEPETER_HOMOGEN_LINEAR"
  title="Homogene lineare DGL 1. Ordnung"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Die homogene lineare ODE 1. Ordnung $y' + f(x)\,y = 0$ ist stets separierbar. Die
Trennung der Variablen aus Abschnitt 7.1 liefert die allgemeine homogene Lösung
$y_h(x) = A\,e^{-\int f(x)\,dx}$, die für konstante Koeffizienten $f(x) = a$ zur
vertrauten Form $y_h = A\,e^{-ax}$ wird. Das Ergebnis ist immer eine Exponentialfunktion
oder entsteht aus ihr durch Integration des Koeffizienten. Genau darin liegt die Antwort
auf die Titelfrage: Der Exponentialansatz funktioniert bei linearen ODEs mit konstanten
Koeffizienten, weil er keine Vermutung, sondern eine erzwungene Konsequenz der
Gleichungsstruktur ist.

Die homogene Lösung $y_h$ enthält eine freie Konstante $A$ und beschreibt damit allein
noch keine eindeutige Bewegung. Sie ist aber der erste und entscheidende Baustein. In
Abschnitt 8.3 ergänzen wir sie durch eine partikuläre Lösung $y_p$, die die Störfunktion
$g(x)$ berücksichtigt. Für den Fallschirmspringer bedeutet das: $y_h = A\,e^{-kt}$
beschreibt das freie Abklingen, $y_p$ die durch die Schwerkraft erzwungene
Grenzgeschwindigkeit. Zusammen ergibt sich die vollständige Lösung
$v(t) = y_h + y_p$, die wir in Abschnitt 7.1 bereits hergeleitet haben.
