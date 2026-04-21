---
authors:
  - name: Simone Gramsch
---

# Richtungsfelder: Lösungskurven sehen, bevor man rechnet

In Abschnitt 6.1 haben wir die spezielle Lösung $v(t) = v_\infty(1 - e^{-kt})$
durch Einsetzen und Verifizieren kennengelernt, aber noch nicht hergeleitet.
Bevor wir in Abschnitt 6.4 das erste systematische Lösungsverfahren entwickeln,
machen wir einen Schritt zurück und fragen: Was lässt sich über die Lösungen
einer ODE sagen, ohne sie überhaupt zu berechnen? Die Antwort steckt bereits in
der ODE selbst, denn $\dot{v} = g - kv$ schreibt in jedem Punkt des
$(t, v)$-Koordinatensystems eine Steigung vor. Aus diesen Steigungen lässt sich
ein Bild aufbauen, das den qualitativen Verlauf aller Lösungskurven auf einmal
zeigt.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, dass eine ODE 1. Ordnung in expliziter Form $\dot{v} = F(t, v)$
  in jedem Punkt $(t, v)$ die **Steigung der Lösungskurve** durch diesen
  Punkt vorschreibt.
* [ ] Sie können zu einer ODE 1. Ordnung ein **Richtungsfeld** skizzieren,
  indem Sie an ausgewählten Punkten Linienelemente mit der jeweiligen Steigung
  $F(t, v)$ einzeichnen.
* [ ] Sie kennen den Begriff der **Isoklinen** und können die Nullisokline
  einer ODE bestimmen und physikalisch interpretieren.
* [ ] Sie können zu einem gegebenen Startpunkt eine **Lösungskurve** in ein
  Richtungsfeld einzeichnen, indem Sie den Linienelementen folgen.
```

## Was schreibt eine ODE in jedem Punkt vor?

Unsere ODE lautet $\dot{v} = g - kv$. Die rechte Seite hängt nur von $v$ ab,
nicht von $t$. Das bedeutet: Überall auf derselben waagerechten Linie
$v = \text{const}$ ist die vorgeschriebene Steigung gleich. Wir berechnen die
Steigung an einigen konkreten Geschwindigkeitswerten:

| Geschwindigkeit $v$ | Steigung $\dot{v} = g - kv$ | Interpretation |
| --- | --- | --- |
| $0~\text{m\,s}^{-1}$ | $9.81~\text{m\,s}^{-2}$ | Starke Beschleunigung aus der Ruhe |
| $30~\text{m\,s}^{-1}$ | $3.81~\text{m\,s}^{-2}$ | Deutlich schwächere Beschleunigung |
| $49.05~\text{m\,s}^{-1}$ | $0~\text{m\,s}^{-2}$ | Keine Beschleunigung: Grenzgeschwindigkeit |
| $65~\text{m\,s}^{-1}$ | $-3.19~\text{m\,s}^{-2}$ | Verzögerung: Luftwiderstand überwiegt |

An jedem dieser Punkte zeichnen wir ein kurzes Linienelement mit der
entsprechenden Steigung ein. Die Gesamtheit aller solcher Linienelemente über
ein Gitter von Punkten heißt **Richtungsfeld** der ODE.

```{admonition} Was ist ... ein Richtungsfeld?
:class: note
Das **Richtungsfeld** einer ODE 1. Ordnung in expliziter Form $\dot{y} = F(t, y)$
ist die Gesamtheit aller Linienelemente im $(t, y)$-Koordinatensystem. Am
Punkt $(t_0, y_0)$ hat das Linienelement die Steigung $F(t_0, y_0)$.

Eine **Isokline** zur Steigung $c$ ist die Menge aller Punkte, an denen die
vorgeschriebene Steigung gleich $c$ ist:

\begin{equation*}
F(t, y) = c.
\end{equation*}

Die Isokline zur Steigung $c = 0$ heißt **Nullisokline**.
```

Für unsere ODE $\dot{v} = g - kv$ ist die Nullisokline die Lösung von
$g - kv = 0$, also die waagerechte Gerade $v = g/k = 49.05~\text{m\,s}^{-1}$.
Das ist genau die Grenzgeschwindigkeit $v_\infty$. Da die rechte Seite nicht
von $t$ abhängt, sind alle Isoklinen waagerechte Geraden, jeweils bei
$v = (g - c)/k$ für eine gewählte Steigung $c$.

```{figure} richtungsfeld_fallschirmspringer.svg
:name: fig-richtungsfeld
:width: 80%
Richtungsfeld der ODE $\dot{v} = g - kv$ mit $k = 0.2~\text{s}^{-1}$ und
$g = 9.81~\text{m\,s}^{-2}$. Die gestrichelte Linie bei $v_\infty = 49.05~\text{m\,s}^{-1}$
ist die Nullisokline. Eingezeichnet sind Lösungskurven für die Anfangswerte
$v(0) = 0$, $v(0) = 30~\text{m\,s}^{-1}$ und $v(0) = 70~\text{m\,s}^{-1}$.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

## Was verrät das Richtungsfeld über alle Lösungen?

*Müssen wir die ODE lösen, um zu wissen, wohin sich die Geschwindigkeit
langfristig entwickelt?* Nein. Das Richtungsfeld zeigt es sofort. Unterhalb
der Nullisoklinen bei $v_\infty = 49.05~\text{m\,s}^{-1}$ zeigen alle
Linienelemente nach oben: Die Geschwindigkeit nimmt zu. Oberhalb zeigen sie
nach unten: Die Geschwindigkeit nimmt ab. Genau auf der Nullisoklinen sind die
Linienelemente waagerecht: Dort ändert sich die Geschwindigkeit nicht.

Dieses Bild beschreibt einen **stabilen Gleichgewichtszustand**. Jede Lösung,
die unterhalb von $v_\infty$ startet, steigt gegen $v_\infty$; jede Lösung,
die oberhalb startet, sinkt gegen $v_\infty$. Die Grenzgeschwindigkeit ist
ein Attraktor: Alle Lösungen streben auf sie zu, unabhängig vom Anfangswert.
In der Regelungstechnik, die Sie in höheren Semestern kennenlernen werden,
ist diese Analyse der Gleichgewichtszustände und ihrer Stabilität ein
zentrales Werkzeug für die Auslegung von Regelkreisen.

Die Beobachtung lässt sich direkt aus der ODE ablesen, ohne die Lösung zu
kennen: Ist $v < v_\infty$, dann ist $g - kv > 0$, also $\dot{v} > 0$; ist
$v > v_\infty$, dann ist $g - kv < 0$, also $\dot{v} < 0$. Die Nullisokline
teilt den Phasenraum in eine Beschleunigungs- und eine Verzögerungszone.

## Wie zeichnet man eine Lösungskurve ein?

Eine Lösungskurve durch einen Startpunkt $(t_0, v_0)$ zu skizzieren bedeutet,
den Linienelementen des Richtungsfeldes zu folgen: Man beginnt am Startpunkt,
bewegt sich ein kurzes Stück in Richtung des dortigen Linienelementes, liest am
neuen Punkt die nächste Steigung ab und setzt die Kurve fort. Dieses Vorgehen
ist qualitativ; ein exakter Algorithmus daraus wird das Euler-Verfahren in
Abschnitt 6.3 sein.

Für unser AWP $v(0) = 0$ beginnt die Kurve bei $(0, 0)$. Das Linienelement
dort hat die Steigung $\dot{v}(0) = g = 9.81~\text{m\,s}^{-2}$, die Kurve
startet also steil. Mit wachsendem $v$ nimmt die Steigung ab, die Kurve flacht
sich ab und schmiegt sich von unten an die Nullisokline $v = v_\infty$ an.
Das stimmt genau mit der in Abschnitt 6.1 berechneten Lösung
$v(t) = v_\infty(1 - e^{-0.2\,t})$ überein: steiler Anstieg nahe $t = 0$,
asymptotische Annäherung an $v_\infty$ für große $t$.

```{dropdown} Video "Richtungsfeld einer Differentialgleichung" von MathePeter
<iframe width="1020" height="574"
src="https://www.youtube.com/embed/PLACEHOLDER_63"
title="Richtungsfeld einer Differentialgleichung" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin"
allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Das Richtungsfeld einer ODE 1. Ordnung macht die qualitative Struktur aller
Lösungskurven sichtbar, ohne dass eine einzige Lösung berechnet werden muss.
Die Nullisokline trennt Bereiche mit positiver und negativer Steigung und
zeigt stabile Gleichgewichtszustände. Für unser Fallbeispiel ist
$v_\infty = 49.05~\text{m\,s}^{-1}$ ein solcher Attraktor: Alle Startbedingungen
führen zur selben Grenzgeschwindigkeit.

In Abschnitt 6.3 machen wir das visuelle Abschätzen zu einem rechenbaren
Verfahren: Das Euler-Verfahren ersetzt das Folgen von Linienelementen durch
eine systematische Schrittformel und liefert eine numerische Näherungslösung
für beliebige Startbedingungen.
