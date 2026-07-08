---
authors:
  - name: Simone Gramsch
---

# 14.2 Konvergenzgeschwindigkeit und Gibbssches Phänomen

In Abschnitt 12.4 haben wir beobachtet, dass die Partialsummen der
Rechteck-Lagerkraft an den Sprungstellen stets überschießen, egal wie viele
Terme wir mitnehmen. Die Dreiecksschwingung aus Abschnitt 13.1 verhält sich
ganz anders: Ihre Partialsummen schmiegen sich gleichmäßig an die Funktion an,
und ihre Koeffizienten klingen wie $1/n^2$ ab statt wie $1/n$. *Was genau
passiert an einer Sprungstelle, wenn wir unendlich viele Terme summieren, und
warum bestimmt die Glattheit einer Funktion das Tempo der Konvergenz?* Beide
Fragen führen auf das Konvergenzverhalten der Fourierreihe, das wir in diesem
Abschnitt klären.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können den Wert berechnen, gegen den eine Fourierreihe an einer
  **Sprungstelle** konvergiert, und das Ergebnis physikalisch interpretieren.
* [ ] Sie können aus dem **Abklingverhalten** der Fourierkoeffizienten auf
  die Glattheit einer Funktion schließen und umgekehrt.
* [ ] Sie kennen das **Gibbssche Phänomen** und können es qualitativ
  beschreiben: Wo tritt es auf, und warum verschwindet es auch bei sehr
  vielen Termen nicht?
```

## Gegen welchen Wert konvergiert die Reihe an einer Sprungstelle?

An Stetigkeitsstellen ist die Lage einfach: Dort konvergieren die
Partialsummen $S_N(t)$ für $N \to \infty$ gegen den Funktionswert $f(t)$. An
Sprungstellen kann die Reihe nicht gleichzeitig gegen zwei verschiedene Werte
konvergieren, sie wählt einen Mittelweg. Welchen, das haben wir bereits in
Abschnitt 12.3 bei den Dirichlet-Bedingungen festgehalten: An einer
Sprungstelle $t^*$ konvergiert die Fourierreihe gegen den Mittelwert der
beiden einseitigen Grenzwerte,

\begin{equation*}
\frac{f(t^*-) + f(t^*+)}{2},
\end{equation*}

wobei $f(t^*-)$ den linksseitigen und $f(t^*+)$ den rechtsseitigen Grenzwert
bezeichnet. Jetzt wenden wir diese Aussage erstmals konkret an.

Die Rechteck-Lagerkraft aus Abschnitt 12.4 hat Sprungstellen bei $t^* = 0$ und
$t^* = \pm\pi$. An der Stelle $t^* = 0$ gilt $f(0-) = -1$ (linksseitiger
Grenzwert aus dem Intervall $[-\pi, 0)$) und $f(0+) = +1$ (rechtsseitiger
Grenzwert aus dem Intervall $[0, \pi)$). Der Konvergenzwert der Fourierreihe
an dieser Stelle ist damit

\begin{equation*}
\frac{f(0-) + f(0+)}{2} = \frac{-1 + 1}{2} = 0.
\end{equation*}

An der Stelle $t^* = \pi$ springt die Funktion von $+1$ auf $-1$ (periodische
Fortsetzung), der Konvergenzwert ist ebenfalls $0$. Physikalisch ist das
plausibel: Im Moment des Kraftrichtungswechsels liefert die Reihe genau den
Nulldurchgang der Lagerkraft. Zur Verifikation werfen wir einen Blick zurück
auf die Partialsummen in Abschnitt 12.4: Alle Kurven $S_1$, $S_3$ und $S_9$
laufen an den Sprungstellen tatsächlich durch den Wert $0$. $\checkmark$

## Warum konvergiert die Dreiecksreihe so viel schneller?

Der Vergleich unserer beiden Leitrechnungen zeigt ein Muster. Die
Rechteck-Lagerkraft hat Sprungstellen, ihre Koeffizienten klingen wie $1/n$
ab, und wir brauchten in Abschnitt 12.4 viele Terme für eine brauchbare
Näherung. Die Dreiecksschwingung ist überall stetig und hat nur Knickstellen,
an denen die Ableitung springt; ihre Koeffizienten klingen wie $1/n^2$ ab,
und schon $S_3$ lag in Abschnitt 13.1 nur noch $5\,\%$ vom exakten Wert
entfernt. *Ist das ein allgemeines Prinzip?*

Ja, und es lässt sich anschaulich begründen: Die Dreiecksschwingung entsteht,
grob gesprochen, durch Integration der Rechteckschwingung, und jede
Integration bringt im Frequenzbereich einen zusätzlichen Faktor $1/n$. Je
glatter eine Funktion ist, desto weniger hochfrequente Anteile braucht ihre
Fourierreihe, desto schneller klingen die Koeffizienten ab und desto weniger
Terme genügen für eine vorgegebene Genauigkeit. Die folgende Übersicht fasst
die drei wichtigsten Fälle zusammen:

| Verhalten der Funktion | Abklingen der Koeffizienten | Beispiel | Beispiel im Maschinenbau |
| --- | --- | --- | --- |
| Sprungstelle | $\sim 1/n$ | Rechteckschwingung | schaltende Lagerkraft, Taktventil |
| stetig, Knick in der Ableitung | $\sim 1/n^2$ | Dreiecksschwingung | Hubkurve eines Nockens |
| beliebig oft differenzierbar | schneller als jede Potenz $1/n^k$ | Sinusschwingung | ideale Unwuchterregung |

Wie drastisch der Unterschied zwischen beiden Abklingraten ausfällt, zeigt der
direkte Vergleich der Koeffizientenbeträge unserer beiden Leitbeispiele.

```{figure} pics/chap13_sec02_fig02.svg
---
name: chap13_sec02_fig02
---
Abklingverhalten der Fourierkoeffizienten von Rechteck- und Dreiecksschwingung
im Vergleich.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Für die Praxis bedeutet das: Wer in der Messtechnik ein Signal mit scharfen
Flanken analysiert, muss mit einem breiten Frequenzspektrum rechnen, denn die
hohen Frequenzanteile sterben nur langsam aus. In der Auslegung von
Nockenprofilen wird deshalb gezielt auf stetige Übergänge mit stetigen
Ableitungen geachtet, um hochfrequente Anregungen des Ventiltriebs klein zu
halten.

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
Partialsumme $S_{15}$ der Fourierreihe der Rechteck-Lagerkraft in der Nähe der
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

Für die Rechteck-Lagerkraft beträgt die Sprunghöhe $|\Delta| = 2$, das
Überschießen beläuft sich also auf etwa $0.09 \cdot 2 = 0.18$. Die
Partialsumme erreicht nahe der Sprungstelle Werte von ungefähr $\pm 1.18$,
obwohl die Funktion selbst nur zwischen $-1$ und $+1$ variiert. Für das Lager
heißt das: Eine aus endlich vielen Harmonischen rekonstruierte Kraft
überschätzt die Spitzenlast in der Nähe des Umschaltmoments systematisch um
knapp ein Fünftel der Sprunghöhe.

In der Messtechnik und der digitalen Signalverarbeitung ist das Gibbssche
Phänomen praktisch relevant: Wann immer ein Signal scharfe Flanken hat,
etwa bei Schaltimpulsen eines Hydraulikventils oder bei abrupten
Lastwechseln, entstehen nach einer Fourieranalyse und Rücktransformation
diese Überschwinger. Bei der Auslegung von Filtern in der Regelungstechnik
muss man diesen Effekt berücksichtigen, um unerwünschte Schwingungen in der
Steuergröße zu vermeiden.

## Zusammenfassung und Ausblick

An Stetigkeitsstellen konvergiert die Fourierreihe gegen den Funktionswert,
an Sprungstellen gegen den Mittelwert der einseitigen Grenzwerte. Wie schnell
die Konvergenz läuft, verrät das Abklingverhalten der Koeffizienten: Je
glatter die Funktion, desto schneller sterben die hohen Frequenzanteile aus.
Das Gibbssche Phänomen zeigt schließlich, dass die Konvergenz an
Sprungstellen nicht gleichmäßig ist: Der Überschwinger von rund $9\,\%$ der
Sprunghöhe bleibt bei beliebig vielen Termen erhalten.

Bisher führt jede Frequenz in der Fourierreihe zwei Koeffizienten $a_n$ und
$b_n$ mit sich. Für die Frage, wie stark die Lagerkraft bei einer bestimmten
Frequenz schwingt, ist das unhandlich. In Abschnitt 13.3 schreiben wir die
Fourierreihe mithilfe der eulerschen Formel aus Abschnitt 10.4 in eine
komplexe Form um, in der jede Frequenz nur noch einen einzigen Koeffizienten
trägt, und gewinnen daraus das Amplitudenspektrum der Lagerkraft.
