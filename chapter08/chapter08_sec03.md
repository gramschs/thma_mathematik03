---
authors:
  - name: Simone Gramsch
kernelspec:
  name: python3
  display_name: 'Python 3'
---

# 8.3 Richtungsfelder und Euler-Verfahren (Vertiefung)

```{admonition} Dieses Kapitel wird gerade überarbeitet
:class: warning
Das Skript wird gerade an den neuen Zeitplan angepasst. Dieses Kapitel ist
rechtzeitig vor der zugehörigen Vorlesung fertig überarbeitet. Bis dahin können
sich Aufbau und Inhalt noch ändern.
Vorerst stehen hier die bisherigen Kapitel 7.2 und 7.3 hintereinander.
Es ist eine Vertiefung und kein Prüfungsstoff.
```

## Richtungsfelder: Lösungskurven sehen, bevor man rechnet

In Abschnitt 6.1 haben wir die spezielle Lösung $v(t) = v_\infty(1 - e^{-kt})$
durch Einsetzen und Verifizieren kennengelernt, aber noch nicht hergeleitet.
Bevor wir in Abschnitt 6.4 das erste systematische Lösungsverfahren entwickeln,
machen wir einen Schritt zurück und fragen: Was lässt sich über die Lösungen
einer ODE sagen, ohne sie überhaupt zu berechnen? Die Antwort steckt bereits in
der ODE selbst, denn $\dot{v} = g - kv$ schreibt in jedem Punkt des
$(t, v)$-Koordinatensystems eine Steigung vor. Aus diesen Steigungen lässt sich
ein Bild aufbauen, das den qualitativen Verlauf aller Lösungskurven auf einmal
zeigt.

### Lernziele

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

### Was schreibt eine ODE in jedem Punkt vor?

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

```{figure} pics/chap06_richtungsfeld_fallschirmspringer.svg
:name: chap06_richtungsfeld_fallschirmspringer
:width: 80%
Richtungsfeld der ODE $\dot{v} = g - kv$ mit $k = 0.2~\text{s}^{-1}$ und
$g = 9.81~\text{m\,s}^{-2}$. Die gestrichelte Linie bei $v_\infty = 49.05~\text{m\,s}^{-1}$
ist die Nullisokline. Eingezeichnet sind Lösungskurven für die Anfangswerte
$v(0) = 0$, $v(0) = 30~\text{m\,s}^{-1}$ und $v(0) = 70~\text{m\,s}^{-1}$.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

### Was verrät das Richtungsfeld über alle Lösungen?

*Müssen wir die ODE lösen, um zu wissen, wohin sich die Geschwindigkeit
langfristig entwickelt?* Nein. Das Richtungsfeld zeigt es sofort, und das
gilt auch dann, wenn sich eine ODE gar nicht analytisch lösen lässt: Wir
sehen dennoch, wie sich Lösungen qualitativ verhalten. Unterhalb der
Nullisokline bei $v_\infty = 49.05~\text{m\,s}^{-1}$ zeigen alle
Linienelemente nach oben: Die Geschwindigkeit nimmt zu. Oberhalb zeigen sie
nach unten: Die Geschwindigkeit nimmt ab. Genau auf der Nullisokline sind die
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
teilt die $(t, v)$-Ebene in eine Beschleunigungs- und eine Verzögerungszone.

### Wie zeichnet man eine Lösungskurve ein?

Eine Lösungskurve durch einen Startpunkt $(t_0, v_0)$ zu skizzieren bedeutet,
den Linienelementen des Richtungsfeldes zu folgen: Man beginnt am Startpunkt,
bewegt sich ein kurzes Stück in Richtung des dortigen Linienelementes, liest am
neuen Punkt die nächste Steigung ab und setzt die Kurve fort. Dieses Vorgehen
ist qualitativ; ein exakter Algorithmus daraus wird das Euler-Verfahren in
Abschnitt 6.3 sein.

<!-- markdownlint-disable MD033 -->
<div id="applet-container-720">

<iframe
  src="https://gramschs.github.io/thma_mathematik03_assets/interactive/chapter06/chap06_richtungsfeld.html"
  width="100%"
  frameborder="0"
  scrolling="no">
</iframe>

</div>
<!-- markdownlint-enable MD033 -->

Für unser AWP $v(0) = 0$ beginnt die Kurve bei $(0, 0)$. Das Linienelement
dort hat die Steigung $\dot{v}(0) = g = 9.81~\text{m\,s}^{-2}$, die Kurve
startet also steil. Mit wachsendem $v$ nimmt die Steigung ab, die Kurve flacht
sich ab und schmiegt sich von unten an die Nullisokline $v = v_\infty$ an.
Das stimmt genau mit der in Abschnitt 6.1 berechneten Lösung
$v(t) = v_\infty(1 - e^{-0.2\,t})$ überein: steiler Anstieg nahe $t = 0$,
asymptotische Annäherung an $v_\infty$ für große $t$.

### Weiteres Lernmaterial

Das folgende Video zeigt das Richtungsfeld **bis** ca. Zeitindex 8:16 min.

```{dropdown} Video "Graphische und numerische Lösung für DGL 1. Ordnung" von Prof. Hielscher
<iframe width="966" height="613" src="https://www.youtube.com/embed/7J5cJspIpl8?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07" title="graphische und numerische Lösung für DGL 1. Ordnung" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

### Zusammenfassung und Ausblick

Das Richtungsfeld einer ODE 1. Ordnung macht die qualitative Struktur aller
Lösungskurven sichtbar, ohne dass eine einzige Lösung berechnet werden muss.
Das ist besonders wertvoll, wenn eine analytische Lösung nicht existiert oder
schwer zu finden ist. Die Nullisokline teilt die $(t, v)$-Ebene in zwei
Bereiche mit positiver und negativer Steigung und zeigt stabile
Gleichgewichtszustände. Für unser Fallbeispiel ist
$v_\infty = 49.05~\text{m\,s}^{-1}$ ein solcher Attraktor: Alle Startbedingungen
führen zur selben Grenzgeschwindigkeit.

In Abschnitt 6.3 machen wir das visuelle Abschätzen zu einem rechenbaren
Verfahren: Das Euler-Verfahren ersetzt das Folgen von Linienelementen durch
eine systematische Schrittformel und liefert eine numerische Näherungslösung
für beliebige Startbedingungen.

## Das Euler-Verfahren: eine Lösungskurve Schritt für Schritt verfolgen

In Abschnitt 6.2 haben wir gesehen, wie man einer Lösungskurve im Richtungsfeld
mit dem Auge folgt: Man beginnt am Startpunkt und bewegt sich immer in Richtung
des dortigen Linienelementes. Das ist qualitativ überzeugend, aber für
ingenieurmäßige Berechnungen nicht präzise genug. Jetzt machen wir aus dieser
Idee einen Algorithmus. Das Euler-Verfahren ist das einfachste numerische
Verfahren zur Lösung von ODEs und bildet die Grundlage für alle modernen
Simulationswerkzeuge in der Strömungsmechanik, der Mehrkörperdynamik und der
Regelungstechnik.

### Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können die **Euler-Formel**
  $v_{n+1} = v_n + h \cdot F(t_n, v_n)$ aus dem Differenzenquotienten
  herleiten.
* [ ] Sie können das **Euler-Verfahren** als nummerierten Algorithmus
  formulieren und auf ein gegebenes AWP anwenden.
* [ ] Sie können die entstehende **Punktfolge** $(t_n, v_n)$ tabellarisch
  berechnen und als Polygonzug im Richtungsfeld interpretieren.
* [ ] Sie kennen die **Schwächen des Euler-Verfahrens**: akkumulierender
  Fehler und starke Abhängigkeit von der Schrittweite $h$.
```

### Wie wird aus einem Linienelement ein Rechenschritt?

Im Richtungsfeld aus Abschnitt 6.2 haben wir gesehen: Am Punkt $(t_n, v_n)$
hat die Lösungskurve die Steigung $F(t_n, v_n) = g - k v_n$. Die Idee des
Euler-Verfahrens ist, diese Steigung für einen kleinen Zeitschritt der Länge
$h$ als konstant anzunehmen und damit den nächsten Punkt der Kurve zu
berechnen. Das entspricht dem Ersetzen der Ableitung durch einen
Differenzenquotienten:

\begin{equation*}
\dot{v}(t_n) \approx \frac{v_{n+1} - v_n}{h}.
\end{equation*}

Wir setzen $\dot{v}(t_n) = F(t_n, v_n)$ ein und lösen nach $v_{n+1}$ auf:

\begin{equation*}
v_{n+1} = v_n + h \cdot F(t_n, v_n).
\end{equation*}

Das ist die **Euler-Formel**. Aus dem aktuellen Wert $v_n$ und der aktuellen
Steigung berechnen wir den nächsten Wert $v_{n+1}$. Die entstehende
Punktfolge $(t_0, v_0), (t_1, v_1), (t_2, v_2), \ldots$ bildet einen
Polygonzug, der im Richtungsfeld ungefähr entlang der Linienelemente verläuft
und die Lösungskurve annähert.

```{admonition} Was ist ... das Euler-Verfahren?
:class: note
Gegeben sei das AWP $\dot{y} = F(t, y)$, $y(t_0) = y_0$, und eine
Schrittweite $h > 0$ sowie eine Endzeit $T$. Das **explizite Euler-Verfahren**
läuft nach folgendem Algorithmus:

1. Setze $t_0 = t_\text{Start}$, $y_0 = y_\text{Start}$.
2. Berechne die Steigung am aktuellen Punkt: $F(t_n, y_n)$.
3. Berechne den nächsten Wert: $y_{n+1} = y_n + h \cdot F(t_n, y_n)$.
4. Setze $t_{n+1} = t_n + h$.
5. Wiederhole ab Schritt 2, solange $t_n \leq T$.

Jeder Schritt ersetzt die Kurve lokal durch ihre Tangente am Punkt $(t_n, y_n)$.
```

Wir führen den Algorithmus für unser AWP $\dot{v} = g - kv$, $v(0) = 0$ mit
der groben Schrittweite $h = 5~\text{s}$ von Hand durch. Die Schrittweite ist
bewusst groß gewählt, damit der Fehler deutlich sichtbar wird.

**Schritt 0:** $t_0 = 0~\text{s}$, $v_0 = 0~\text{m\,s}^{-1}$.

\begin{equation*}
F(0,\; 0) = 9.81 - 0.2 \cdot 0 = 9.81~\text{m\,s}^{-2}.
\end{equation*}

\begin{equation*}
v_1 = 0 + 5 \cdot 9.81 = 49.05~\text{m\,s}^{-1}.
\end{equation*}

**Schritt 1:** $t_1 = 5~\text{s}$, $v_1 = 49.05~\text{m\,s}^{-1}$.

\begin{equation*}
F(5,\; 49.05) = 9.81 - 0.2 \cdot 49.05 = 9.81 - 9.81 = 0~\text{m\,s}^{-2}.
\end{equation*}

\begin{equation*}
v_2 = 49.05 + 5 \cdot 0 = 49.05~\text{m\,s}^{-1}.
\end{equation*}

Das Verfahren bleibt ab dem zweiten Schritt exakt auf der Grenzgeschwindigkeit
stehen. *Was ist passiert?* Die Schrittweite $h = 5~\text{s}$ ist so groß, dass
der erste Schritt direkt von $v = 0$ auf $v = v_\infty$ springt, weit über
die tatsächliche Kurve hinaus. Die Steigung am neuen Punkt ist exakt null,
also verändert sich die Näherung danach nicht mehr.

### Wie gut ist die Näherung, und was tun wir dagegen?

Der Vergleich mit der exakten Lösung $v(t) = v_\infty(1 - e^{-kt})$ aus
Abschnitt 6.1 zeigt das Ausmaß des Fehlers:

| $n$ | $t_n~\text{(s)}$ | $v_n$ Euler $\text{(m\,s}^{-1})$ | $v(t_n)$ exakt $\text{(m\,s}^{-1})$ | Fehler $\text{(m\,s}^{-1})$ |
| --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | 0 |
| 1 | 5 | 49.05 | 31.01 | +18.04 |
| 2 | 10 | 49.05 | 42.41 | +6.64 |
| 3 | 15 | 49.05 | 46.61 | +2.44 |

Der Fehler im ersten Schritt beträgt über $18~\text{m\,s}^{-1}$, fast
$65~\text{km\,h}^{-1}$. Der Grund liegt in der starken Krümmung der
Lösungskurve nahe $t = 0$: Die Steigung ändert sich dort rasch, aber das
Euler-Verfahren verwendet nur die Steigung am linken Rand des Intervalls und
ignoriert diese Änderung vollständig. Der Fehler jedes Schritts schlägt sich
dabei in den Ausgangswert des nächsten Schritts nieder, weshalb sich der
Gesamtfehler über viele Schritte hinweg aufsummiert.

Das Mittel gegen diesen Fehler ist eine kleinere Schrittweite. Mit $h = 2~\text{s}$
oder $h = 0.5~\text{s}$ nähert sich der Polygonzug der exakten Kurve deutlich
besser an. Die Rechnung von Hand wird dabei schnell mühsam. Genau hier hilft
der Computer.

Die folgenden zwei Code-Zellen sind **optional** und richten sich an
Studierende mit Python-Vorkenntnissen sowie an alle, die einen Vorgeschmack auf
die Vorlesung Angewandte Numerik bekommen möchten. Die erste Zelle implementiert
den Euler-Algorithmus direkt nach obiger Schritt-für-Schritt-Beschreibung, die
zweite erzeugt den interaktiven Vergleichsplot.

```{code-cell} python
import numpy as np

# Parameter des Modells
g  = 9.81   # Erdbeschleunigung in m/s^2
k  = 0.2    # Luftwiderstandskoeffizient in 1/s
v0 = 0.0    # Anfangsgeschwindigkeit in m/s
T  = 30.0   # Simulationsdauer in s

def euler(h):
    """Euler-Verfahren für dv/dt = g - k*v mit Schrittweite h."""
    t = np.arange(0.0, T + h, h)   # Schritt 1: Zeitgitter anlegen
    v = np.zeros(len(t))           # Ergebnisarray initialisieren
    v[0] = v0                      # Anfangsbedingung einsetzen
    for n in range(len(t) - 1):
        v[n+1] = v[n] + h * (g - k * v[n])   # Schritte 2-4: Euler-Formel
    return t, v

# Exakte Lösung zum Vergleich
t_ex = np.linspace(0, T, 300)
v_ex = (g / k) * (1 - np.exp(-k * t_ex))

# Ergebnisse für drei Schrittweiten ausgeben
for h in [5.0, 2.0, 0.5]:
    t, v = euler(h)
    print(f"h = {h} s:  v(5s) = {v[int(5/h)]:.2f} m/s  "
          f"(exakt: {v_ex[int(5/T*300)]:.2f} m/s)")
```

```{code-cell} python
import plotly.express as px
import pandas as pd

# Daten für alle Kurven zusammenstellen
rows = []
for h in [5.0, 2.0, 0.5]:
    t, v = euler(h)
    for ti, vi in zip(t, v):
        rows.append({'t': ti, 'v': vi, 'Kurve': f'Euler  h = {h} s'})
for ti, vi in zip(t_ex, v_ex):
    rows.append({'t': ti, 'v': vi, 'Kurve': 'Exakte Lösung'})

# Interaktiver Plot
fig = px.line(
    pd.DataFrame(rows), x='t', y='v', color='Kurve',
    labels={'t': 'Zeit t in s', 'v': 'Geschwindigkeit v in m/s'},
)
fig.add_hline(
    y=g / k, line_dash='dash', line_color='gray',
    annotation_text='Grenzgeschwindigkeit',
    annotation_position='bottom right',
)
fig.show()
```

*Was zeigt das Bild?* Mit $h = 5~\text{s}$ springt der Polygonzug sofort zur
Grenzgeschwindigkeit und bleibt dort. Mit $h = 0.5~\text{s}$ ist die Näherung
kaum noch vom exakten Verlauf zu unterscheiden. Die Schrittweite steuert also
den Kompromiss zwischen Rechenaufwand und Genauigkeit.

Das Euler-Verfahren ist das einfachste Mitglied einer ganzen Familie numerischer
Verfahren. In der Ingenieurpraxis werden genauere Methoden wie das
**Runge-Kutta-Verfahren 4. Ordnung** eingesetzt, das die Steigung nicht nur am
linken Rand, sondern an mehreren Stellen innerhalb des Intervalls auswertet.
Python, MATLAB und Simulink nutzen im Standard solche Verfahren.

### Weiteres Lernmaterial

Das folgende Video zeigt das Euler-Verfahren **ab** ca. Zeitindex 8:16 min.

```{dropdown} Video "Graphische und numerische Lösung für DGL 1. Ordnung" von Prof. Hielscher
<iframe width="966" height="613" src="https://www.youtube.com/embed/7J5cJspIpl8?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07" title="graphische und numerische Lösung für DGL 1. Ordnung" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

### Zusammenfassung und Ausblick

Das Euler-Verfahren übersetzt die geometrische Idee des Richtungsfeldes in
einen Algorithmus: In jedem Schritt wird die Lösungskurve durch ihre Tangente
ersetzt, und der nächste Punkt ergibt sich aus der Euler-Formel
$v_{n+1} = v_n + h \cdot F(t_n, v_n)$. Die entstehende Punktfolge bildet
einen Polygonzug, der im Richtungsfeld entlang der Linienelemente verläuft.
Die Schrittweite $h$ kontrolliert dabei den Fehler; wegen der Fehlerakkumulation
über viele Schritte ist eine kleine Schrittweite entscheidend für eine
brauchbare Näherung.

In Abschnitt 6.4 wechseln wir vom numerischen zum analytischen Standpunkt.
Die Methode der Trennung der Variablen liefert die exakte Lösung
$v(t) = v_\infty(1 - e^{-kt})$, mit der wir in diesem Abschnitt den
Euler-Fehler gemessen haben.
