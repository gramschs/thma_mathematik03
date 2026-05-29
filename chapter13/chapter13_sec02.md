---
authors:
  - name: Simone Gramsch
---

# 13.2 Konvergenz, Sprungstellen und Gibbssches Phänomen

In Abschnitt 12.4 haben wir beobachtet, dass die Partialsummen der
Rechteckschwingung an den Sprungstellen stets überschießen, egal wie viele
Terme wir mitnehmen. In Abschnitt 13.1 haben wir gesehen, dass die
Partialsummen der Dreiecksschwingung gleichmäßig konvergieren, ohne dieses
Überschießen. *Was ist der Unterschied zwischen den beiden Funktionen, und was
passiert an einer Sprungstelle, wenn wir unendlich viele Terme summieren?*
Beide Fragen führen auf das Konvergenzverhalten der Fourierreihe an
Unstetigkeitsstellen.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie kennen die **Dirichlet-Bedingungen** und können für typische
  technische Signale entscheiden, ob eine Fourierreihe konvergiert.
* [ ] Sie wissen, gegen welchen Wert eine Fourierreihe an einer
  **Sprungstelle** konvergiert, und können diesen Wert aus dem Signal
  ablesen.
* [ ] Sie kennen das **Gibbssche Phänomen** und können es qualitativ
  beschreiben: Wo tritt es auf, und warum verschwindet es auch bei sehr
  vielen Termen nicht?
```

## Wo konvergiert die Fourierreihe?

In Abschnitt 12.3 haben wir die Dirichlet-Bedingungen als hinreichende
Voraussetzung für die Konvergenz der Fourierreihe kennengelernt. Beide
Bedingungen waren dort erfüllt, und wir haben die Konvergenz als gesichert
angenommen. Jetzt schauen wir genauer hin: *Gegen welchen Wert konvergiert
die Reihe, und gilt das gleichmäßig überall?*

An Stetigkeitsstellen ist die Antwort einfach: Dort konvergieren die
Partialsummen $S_N(t)$ für $N \to \infty$ gegen den Funktionswert $f(t)$. Je
glatter die Funktion in der Umgebung des Punktes, desto schneller läuft diese
Konvergenz. An Sprungstellen ist die Situation anders. Die Fourierreihe kann
nicht gleichzeitig gegen zwei verschiedene Werte konvergieren, sie wählt einen
Mittelweg.

```{admonition} Konvergenz an Sprungstellen
:class: note
Erfüllt $f$ die Dirichlet-Bedingungen und hat bei $t^*$ eine Sprungstelle, so
konvergiert die Fourierreihe an dieser Stelle gegen den Mittelwert der beiden
einseitigen Grenzwerte:

\begin{equation*}
\frac{f(t^*-) + f(t^*+)}{2}.
\end{equation*}

Dabei bezeichnet $f(t^*-)$ den linksseitigen und $f(t^*+)$ den rechtsseitigen
Grenzwert an der Stelle $t^*$.
```

Wir wenden das auf die Rechteckschwingung aus Abschnitt 12.4 an. Die
Sprungstellen liegen bei $t^* = 0$ und $t^* = \pm\pi$. An der Stelle $t^* =
0$ gilt $f(0-) = 1$ (linksseitiger Grenzwert aus dem Intervall $[-\pi, 0)$)
und $f(0+) = -1$ (rechtsseitiger Grenzwert aus dem Intervall $[0, \pi)$). Der
Konvergenzwert der Fourierreihe an dieser Stelle ist damit

\begin{equation*}
\frac{f(0-) + f(0+)}{2} = \frac{1 + (-1)}{2} = 0.
\end{equation*}

An der Stelle $t^* = \pi$ springt die Funktion von $-1$ auf $+1$ (periodische
Fortsetzung), der Konvergenzwert ist ebenfalls $0$. Die Partialsummen
konvergieren also an den Sprungstellen gegen $0$, nicht gegen $+1$ oder $-1$.

## Was ist das Gibbssche Phänomen?

Selbst wenn wir wissen, gegen welchen Wert die Fourierreihe konvergiert, bleibt
eine auffällige Beobachtung aus den Abbildungen in Abschnitt 12.4: Kurz vor
und kurz hinter jeder Sprungstelle überschießt die Partialsumme $S_N$ den
Funktionswert deutlich. Und dieses Überschießen wird mit wachsendem $N$ nicht
kleiner, es wird nur schmaler.

```{figure} pics/chap13_sec02_fig01.svg
---
name: chap13_sec02_fig01
---
Partialsumme $S_{15}$ der Fourierreihe der Rechteckschwingung in der Nähe der
Sprungstelle bei $t = 0$. Das Überschießen beträgt unabhängig von $N$ stets
etwa $9\,\%$ der Sprunghöhe.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Dieses Verhalten ist kein Rechenfehler und kein Zufall. Es ist ein
strukturelles Merkmal jeder Fourierreihe an Sprungstellen und trägt den Namen
seines Entdeckers.

```{admonition} Was ist ... das Gibbssche Phänomen?
:class: note
An einer Sprungstelle der Höhe $\Delta = f(t^*+) - f(t^*-)$ überschießen die
Partialsummen $S_N$ der Fourierreihe den Funktionswert um etwa

\begin{equation*}
\delta \approx 0.09 \cdot |\Delta|,
\end{equation*}

also ungefähr $9\,\%$ der Sprunghöhe. Dieser Überschwinger wird mit
wachsendem $N$ zwar schmaler, aber nicht kleiner. Er verschwindet auch im
Grenzfall $N \to \infty$ nicht vollständig. Dieses Verhalten heißt
**Gibbssches Phänomen**.
```

Für die Rechteckschwingung beträgt die Sprunghöhe $|\Delta| = 2$, das
Überschießen beläuft sich also auf etwa $0.09 \cdot 2 = 0.18$. Die
Partialsumme erreicht nahe der Sprungstelle Werte von ungefähr $\pm 1.18$,
obwohl die Funktion selbst nur zwischen $-1$ und $+1$ variiert.

In der Messtechnik und der digitalen Signalverarbeitung ist das Gibbssche
Phänomen praktisch relevant: Wann immer ein Signal scharfe Flanken hat,
etwa bei Schaltimpulsen eines Hydraulikventils oder bei abrupten
Lastwechseln, entstehen nach einer Fourieranalyse und Rücktransformation
diese Überschwinger. Bei der Auslegung von Filtern in der Regelungstechnik
muss man diesen Effekt berücksichtigen, um unerwünschte Schwingungen in der
Steuergröße zu vermeiden.

Der Kontrast zur Dreiecksschwingung aus Abschnitt 13.1 ist aufschlussreich.
Die Dreiecksschwingung hat keine Sprungstellen, nur Knickstellen, an denen
$f$ stetig ist, aber ihre Ableitung springt. Dort klingen die Koeffizienten
wie $1/n^2$ ab statt wie $1/n$, und die Partialsummen konvergieren gleichmäßig
ohne dauerhaftes Überschießen. Die Glattheit der Funktion bestimmt also direkt,
wie schnell die Koeffizienten abklingen und ob das Gibbssche Phänomen auftritt:
Sprungstellen erzeugen es, bloße Knickstellen nicht.

## Zusammenfassung und Ausblick

An Stetigkeitsstellen konvergiert die Fourierreihe gegen den Funktionswert,
an Sprungstellen gegen den Mittelwert der einseitigen Grenzwerte. Das
Gibbssche Phänomen zeigt, dass die Konvergenz an Sprungstellen nicht
gleichmäßig ist: Der Überschwinger von rund $9\,\%$ der Sprunghöhe bleibt
bei beliebig vielen Termen erhalten. In Abschnitt 13.3 verlassen wir das
Konvergenzverhalten und fragen stattdessen nach dem Energieinhalt eines
periodischen Signals: Das Parsevalsche Theorem liefert eine elegante Formel,
mit der sich die Gesamtenergie eines Signals direkt aus den
Fourierkoeffizienten ablesen lässt.
