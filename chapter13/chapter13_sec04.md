---
authors:
  - name: Simone Gramsch
---

# 13.4 Erzwungene Schwingung mit periodischer Erregung

In Abschnitt 13.3 haben wir gesehen, dass die Lagerkraft unserer Kurbelwelle
zu etwa $81\,\%$ aus der Grundschwingung und zu $19\,\%$ aus höheren
Oberschwingungen besteht. Der Klirrfaktor von rund $0.435$ zeigt, dass die
Oberschwingungen insgesamt nicht vernachlässigbar sind. Jetzt stellen wir die
entscheidende Ingenieursfrage: *Welche dieser Oberschwingungen kann das Lager
in Resonanz treiben, und wie geht man damit rechnerisch um?* Die Antwort
verbindet die Fourieranalyse aus den Kapiteln 12 und 13 mit der Theorie der
erzwungenen Schwingungen aus Kapitel 11.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie verstehen, wie das **Superpositionsprinzip** bei linearen ODEs
  erlaubt, eine periodisch erregte Schwingung komponentenweise zu lösen.
* [ ] Sie können die Grundidee der Lösung skizzieren: Fourierreihe der
  Erregung aufstellen, jede Komponente separat durch die ODE schicken,
  Ergebnisse überlagern.
* [ ] Sie kennen die Bedeutung von **Resonanz** im Zusammenhang mit der
  Fourierzerlegung und können erklären, welche Oberwelle eines
  Erregersignals ein System in Resonanz versetzen kann.
* [ ] Sie wissen, dass es neben der reellen auch eine **komplexe
  Darstellung** der Fourierreihe gibt, und kennen den konzeptionellen
  Schritt zur **Fouriertransformation**.
```

## Die Grundidee: Superposition und Fourierzerlegung

In Kapitel 11 haben wir die erzwungene Schwingung für eine einzelne
Sinuskraft $F(t) = F_0\,\sin(\Omega t)$ gelöst. Die Lagerkraft unserer
Kurbelwelle ist aber keine reine Sinusschwingung, sondern enthält viele
Oberschwingungen. Das Feder-Masse-System mit Eigenfrequenz $\omega_{\text{sys}}$
und Masse $m$ wird durch diese komplizierte Kraft erregt:

\begin{equation*}
m\,y''(t) + k\,y(t) = F(t),
\quad \omega_{\text{sys}} = \sqrt{\frac{k}{m}}.
\end{equation*}

*Wie löst man eine solche ODE, wenn $F(t)$ keine einfache Sinusfunktion ist?*
Die Antwort liegt im Superpositionsprinzip, das wir aus Kapitel 8 kennen: Bei
einer linearen ODE darf man Lösungen addieren. Wenn $y_1$ die Antwort auf
$F_1$ ist und $y_2$ die Antwort auf $F_2$, dann ist $y_1 + y_2$ die Antwort
auf $F_1 + F_2$.

```{admonition} Lösungsstrategie für periodische Erregung
:class: note
Sei $F(t)$ eine periodische Erregerkraft mit der Fourierreihe

\begin{equation*}
F(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty}
\bigl(a_n\cos(n\omega_0 t) + b_n\sin(n\omega_0 t)\bigr).
\end{equation*}

Die vollständige Lösung der linearen ODE $m\,y'' + k\,y = F(t)$ ergibt sich
in drei Schritten:

1. **Fourierzerlegung:** Fourierkoeffizienten $a_n$ und $b_n$ der Erregerkraft
   berechnen.
2. **Komponentenweise Lösung:** Für jeden Term $a_n\cos(n\omega_0 t)$ und
   $b_n\sin(n\omega_0 t)$ die partikuläre Lösung $y_{p,n}$ separat bestimmen
   (Ansatz aus Kapitel 11).
3. **Überlagerung:** Die Gesamtlösung ist $y_p(t) = \sum_{n} y_{p,n}(t)$,
   ergänzt um die homogene Lösung $y_h$.
```

Das ist kein neues Lösungsverfahren, sondern eine Kombination zweier bekannter
Werkzeuge: der Fourieranalyse und des Ansatzes vom Typ der rechten Seite aus
Kapitel 11. Die entscheidende Frage bei Schritt 2 ist dieselbe wie in Kapitel
11: Liegt die Erregerfrequenz $n\omega_0$ in der Nähe der Eigenfrequenz
$\omega_{\text{sys}}$?

## Welche Oberschwingung ist gefährlich?

Wir kehren zur Kurbelwelle zurück. Die Grundfrequenz der Lagerkraft beträgt
$f_0 = 25~\text{Hz}$, die zugehörige Kreisfrequenz ist
$\omega_0 = 2\pi \cdot 25~\text{Hz} = 50\pi~\text{rad\,s}^{-1}$. Die $n$-te
Oberschwingung hat die Kreisfrequenz $n\omega_0 = 50\pi\,n~\text{rad\,s}^{-1}$.

Angenommen, das Pleuellager und die zugehörige Wellenbaugruppe haben die
Eigenfrequenz $\omega_{\text{sys}} = 150\pi~\text{rad\,s}^{-1} \approx
471~\text{rad\,s}^{-1}$, was einer Eigenfrequenz von $75~\text{Hz}$
entspricht. Wir suchen die Oberschwingungsordnung $n$, bei der Resonanz droht:

\begin{equation*}
n\,\omega_0 = \omega_{\text{sys}}
\quad \Rightarrow \quad
n = \frac{\omega_{\text{sys}}}{\omega_0}
= \frac{150\pi}{50\pi} = 3.
\end{equation*}

Die dritte Oberschwingung ($n = 3$) trifft die Eigenfrequenz des Lagers exakt.
Aus der Fourierreihe der Rechteck-Lagerkraft wissen wir aus Abschnitt 12.4,
dass $n = 3$ eine ungerade Zahl ist und damit ein nichtverschwindender
Koeffizient vorliegt: $b_3 = -4/(3\pi)$. Die Amplitude dieser Oberschwingung
beträgt

\begin{equation*}
\hat{F}_3 = |b_3| \cdot F_0= \frac{4}{3\pi}\,F_0 \approx 0.424\,F_0,
\end{equation*}

wobei $F_0$ die Amplitude der Grundschwingung ist. Die dritte Oberschwingung
hat also noch gut $42\,\%$ der Amplitude der Grundschwingung. Das ist kein
vernachlässigbarer Anteil.

```{figure} pics/chap13_sec04_fig01.svg
---
name: chap13_sec04_fig01
---
Frequenzspektrum der Rechteck-Lagerkraft: Die Balken zeigen die Amplituden
$|b_n|$ der ersten Oberschwingungen. Die dritte Oberschwingung bei
$75~\text{Hz}$ trifft die Eigenfrequenz des Lagers (rot markiert).
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Was passiert beim Hochlaufen der Kurbelwelle auf die Betriebsdrehzahl von
$1500~\text{min}^{-1}$? Bei einer Drehzahl von $1500/3 = 500~\text{min}^{-1}$
hat die Grundschwingung die Frequenz $500/60 \approx 8.3~\text{Hz}$, und die
dritte Oberschwingung trifft genau $75~\text{Hz}$. Beim Durchfahren dieser
Drehzahl droht Resonanz. Das ist aus Kapitel 11 bekannt: Wenn die
Erregerfrequenz die Eigenfrequenz trifft, wächst die Schwingungsamplitude ohne
Dämpfung unbegrenzt. In der Praxis bedeutet das: Der Hochlauf muss schnell
genug durch diesen Drehzahlbereich geführt werden, um die Amplitude klein zu
halten.

Die Fourierzerlegung liefert hier also mehr als nur eine mathematische
Darstellung. Sie zeigt, bei welchen Betriebsdrehzahlen kritische
Resonanzzustände auftreten können, und zwar nicht nur für die
Grundschwingung, sondern für alle harmonischen Anteile der Erregerkraft.
In der Maschinenakustik und der Rotordynamik ist genau diese Analyse der
Ausgangspunkt für die konstruktive Auslegung.

## Ausblick: Wohin führt der Weg weiter?

Die reelle Fourierreihe, die wir in den Kapiteln 12 und 13 entwickelt haben,
ist das grundlegende Werkzeug. In weiterführenden Lehrveranstaltungen begegnen
Ihnen zwei wichtige Erweiterungen.

Die **komplexe Fourierreihe** schreibt dieselbe Reihe kompakter mit komplexen
Exponentialfunktionen:

\begin{equation*}
f(t) = \sum_{n=-\infty}^{\infty} c_n\,e^{in\omega_0 t},
\quad c_n = \frac{1}{T}\int_{-T/2}^{T/2} f(t)\,e^{-in\omega_0 t}\,dt.
\end{equation*}

Die Koeffizienten $c_n$ sind komplex und tragen Amplituden- und
Phaseninformation zugleich. Diese Darstellung ist in der Regelungstechnik und
der digitalen Signalverarbeitung Standard, weil sie algebraisch eleganter und
für die Herleitung des Frequenzgangs besser geeignet ist.

Die **Fouriertransformation** ist die Verallgemeinerung auf nicht-periodische
Signale. Statt einer diskreten Menge von Oberschwingungsfrequenzen
$n\omega_0$ erhält man ein kontinuierliches Frequenzspektrum $\hat{f}(\omega)$.
Sie ist das zentrale Werkzeug der modernen Signalverarbeitung, von der
Schwingungsdiagnose über die Bildverarbeitung bis zur Kommunikationstechnik.
In den Lehrveranstaltungen Regelungstechnik und Signalverarbeitung werden Sie
diese Methoden systematisch vertiefen.

## Zusammenfassung: Kapitel 12 und 13

Mit diesem Abschnitt schließen wir das Thema Fourierreihen ab. Der Weg führte
von der periodischen Funktion (12.1) über Grundschwingung und Oberschwingungen
(12.2) zu den Euler-Fourier-Formeln (12.3) und den konkreten Rechenbeispielen
(12.4). In Kapitel 13 haben wir Symmetrie als Rechenhilfsmittel genutzt (13.1),
das Konvergenzverhalten und das Gibbssche Phänomen analysiert (13.2), den
Energieinhalt mit dem Parsevalschen Theorem berechnet (13.3) und schließlich
die Brücke zur erzwungenen Schwingung aus Kapitel 11 geschlagen (13.4).

Das durchgängige Leitbeispiel der Kurbelwelle hat dabei gezeigt, wie dieselbe
physikalische Fragestellung, nämlich die periodische Lagerkraft einer
rotierenden Welle, alle mathematischen Konzepte motiviert und verbindet. In
der Maschinenakustik, der Rotordynamik und der Regelungstechnik werden Sie
diese Werkzeuge auf komplexere Systeme anwenden und um die Fourier- und
Laplace-Transformation erweitern.
