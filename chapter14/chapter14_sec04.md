---
authors:
  - name: Simone Gramsch
---

# 14.4 Erzwungene Schwingung mit periodischer Erregung

In Abschnitt 13.3 haben wir das Amplitudenspektrum der Lagerkraft unserer
Kurbelwelle berechnet: Neben der Grundschwingung bei $25~\text{Hz}$ enthält
es Spektrallinien bei $75~\text{Hz}$, $125~\text{Hz}$ und allen weiteren
ungeraden Vielfachen der Grundfrequenz, deren Amplituden wie $1/n$ abklingen.
Die Linie bei $75~\text{Hz}$ trägt noch ein Drittel der
Grundschwingungsamplitude. Jetzt stellen wir die entscheidende
Ingenieursfrage: *Welche dieser Oberschwingungen kann das Lager in Resonanz
treiben, und wie geht man damit rechnerisch um?* Die Antwort verbindet die
Fourieranalyse aus den Kapiteln 12 und 13 mit der Theorie der erzwungenen
Schwingungen aus Kapitel 11.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie verstehen, wie das **Superpositionsprinzip** bei linearen ODEs
  erlaubt, eine periodisch erregte Schwingung komponentenweise zu lösen.
* [ ] Sie können die Grundidee der Lösung skizzieren: Fourierreihe der
  Erregung aufstellen, jede Komponente separat durch die ODE schicken,
  Ergebnisse überlagern.
* [ ] Sie können mithilfe des Amplitudenspektrums die **resonanzgefährdende
  Harmonische** eines Erregersignals identifizieren und kritische
  Drehzahlen berechnen.
* [ ] Sie kennen den konzeptionellen Schritt von der Fourierreihe zur
  **Fouriertransformation** für nicht-periodische Signale.
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

```{admonition} Wie lautet die Lösungsstrategie für periodische Erregung?
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

## Welche Harmonische ist gefährlich?

Wir kehren zur Kurbelwelle zurück. Die Grundfrequenz der Lagerkraft beträgt
bei der Betriebsdrehzahl $1500~\text{min}^{-1}$ genau $f_0 = 25~\text{Hz}$,
die zugehörige Kreisfrequenz ist
$\omega_0 = 2\pi \cdot 25~\text{Hz} = 50\pi~\text{rad\,s}^{-1}$. Die $n$-te
Harmonische hat die Kreisfrequenz $n\omega_0 = 50\pi\,n~\text{rad\,s}^{-1}$.

Angenommen, das Pleuellager und die zugehörige Wellenbaugruppe haben die
Eigenfrequenz $\omega_{\text{sys}} = 150\pi~\text{rad\,s}^{-1} \approx
471~\text{rad\,s}^{-1}$, was einer Eigenfrequenz von $75~\text{Hz}$
entspricht. Wir suchen die Ordnung $n$ der Harmonischen, bei der Resonanz droht:

\begin{equation*}
n\,\omega_0 = \omega_{\text{sys}}
\quad \Rightarrow \quad
n = \frac{\omega_{\text{sys}}}{\omega_0}
= \frac{150\pi}{50\pi} = 3.
\end{equation*}

Die dritte Harmonische ($n = 3$) trifft die Eigenfrequenz des Lagers exakt.
Aus der Fourierreihe der Rechteck-Lagerkraft wissen wir aus Abschnitt 12.4,
dass $n = 3$ eine ungerade Zahl ist und damit ein nichtverschwindender
Koeffizient vorliegt: $b_3 = 4/(3\pi)$. Die Amplitude dieser Harmonischen
beträgt

\begin{equation*}
\hat{F}_3 = b_3 \cdot F_0 = \frac{4}{3\pi}\,F_0 \approx 0.42\,F_0,
\end{equation*}

wobei $F_0$ die Amplitude der Rechteck-Lagerkraft ist. Bezogen auf die
Grundschwingung mit $\hat{F}_1 = \frac{4}{\pi}\,F_0$ ist das exakt ein
Drittel, wie wir es in Abschnitt 13.3 im Spektrum abgelesen haben. Das ist
kein vernachlässigbarer Anteil.

%```{figure} pics/chap13_sec04_fig01.svg
%---
%name: chap13_sec04_fig01
%---
%Frequenzspektrum der Rechteck-Lagerkraft: Die Balken zeigen die Amplituden
%$\hat{F}_n$ der ersten Harmonischen. Die dritte Harmonische bei
%$75~\text{Hz}$ trifft die Eigenfrequenz des Lagers (rot markiert).
%(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
%```

Das Brisante an diesem Ergebnis: Die Resonanz droht nicht etwa nur in einem
kurzen Übergangsmoment, sondern genau bei der Betriebsdrehzahl
$1500~\text{min}^{-1}$, also im Dauerbetrieb. Aus Kapitel 11 wissen wir, was
das bedeutet: Trifft die Erregerfrequenz die Eigenfrequenz, wächst die
Schwingungsamplitude ohne Dämpfung unbegrenzt an. Konstruktiv gibt es zwei
Auswege, die Sie in der Technischen Mechanik und der Maschinendynamik
vertiefen werden: Entweder verschiebt man die Eigenfrequenz der
Lagerbaugruppe durch Änderung von Steifigkeit oder Masse aus dem Bereich der
starken Spektrallinien heraus, oder man führt gezielt Dämpfung ein, die die
Resonanzamplitude begrenzt.

*Und was passiert beim Hochlaufen der Kurbelwelle von null auf die
Betriebsdrehzahl?* Bei einer Drehzahl $N$ in $\text{min}^{-1}$ beträgt die
Grundfrequenz $f_0 = N/60$, und die $n$-te Harmonische trifft die
Eigenfrequenz $75~\text{Hz}$, sobald $n \cdot N/60 = 75~\text{Hz}$ gilt, also
bei den kritischen Drehzahlen

\begin{equation*}
N_{\text{krit}} = \frac{4500}{n}~\text{min}^{-1},
\qquad n = 1, 3, 5, 7, 9, \ldots
\end{equation*}

Nur die ungeraden $n$ zählen, weil die geraden Koeffizienten der
Rechteck-Lagerkraft verschwinden. Beim Hochlauf werden also nacheinander die
Drehzahlen $500~\text{min}^{-1}$ ($n = 9$), etwa $643~\text{min}^{-1}$
($n = 7$) und $900~\text{min}^{-1}$ ($n = 5$) durchfahren, bevor das System
bei $1500~\text{min}^{-1}$ ($n = 3$) in der Betriebsresonanz landet. Die
Stärke dieser Zwischenresonanzen nimmt mit $1/n$ ab: Bei
$500~\text{min}^{-1}$ regt die neunte Harmonische mit immerhin
$\hat{F}_9 = \frac{4}{9\pi}\,F_0 \approx 0.14\,F_0$ an. In der Praxis heißt
das: Der Hochlauf muss schnell genug durch diese Drehzahlbereiche geführt
werden, damit die Amplituden klein bleiben, und die Betriebsdrehzahl selbst
darf bei dieser Auslegung so nicht stehenbleiben.

Die Fourierzerlegung liefert hier also mehr als nur eine mathematische
Darstellung. Sie zeigt, bei welchen Betriebsdrehzahlen kritische
Resonanzzustände auftreten können, und zwar nicht nur für die
Grundschwingung, sondern für alle harmonischen Anteile der Erregerkraft.
In der Maschinenakustik und der Rotordynamik ist genau diese Analyse der
Ausgangspunkt für die konstruktive Auslegung.

## Ausblick: Von der Reihe zur Transformation

Die Fourierreihe, in reeller wie in komplexer Form, setzt ein periodisches
Signal voraus. Viele technische Signale sind aber nicht periodisch: ein
einzelner Stoß beim Anfahren, das Ausschwingen nach einer Notabschaltung,
ein einmaliger Lastwechsel. *Wie zerlegt man ein solches Signal in seine
Frequenzanteile?*

Die Antwort gibt die **Fouriertransformation**, die Verallgemeinerung der
Fourierreihe auf nicht-periodische Signale. Die komplexe Darstellung aus
Abschnitt 13.3 ist dafür der natürliche Ausgangspunkt: Aus der Summe über
die diskreten Frequenzen $n\omega_0$ wird ein Integral über ein
kontinuierliches Frequenzspektrum $\hat{f}(\omega)$. Die Fouriertransformation
ist das zentrale Werkzeug der modernen Signalverarbeitung, von der
Schwingungsdiagnose über die Bildverarbeitung bis zur Kommunikationstechnik.
In den Lehrveranstaltungen Regelungstechnik und Signalverarbeitung werden Sie
diese Methode systematisch vertiefen.

## Zusammenfassung: Kapitel 12 und 13

Mit diesem Abschnitt schließen wir das Thema Fourierreihen ab. Der Weg führte
von der periodischen Funktion (12.1) über Grundschwingung und Oberschwingungen
(12.2) zu den Euler-Fourier-Formeln (12.3) und den konkreten Rechenbeispielen
(12.4). In Kapitel 13 haben wir Symmetrie als Rechenhilfsmittel genutzt (13.1),
das Konvergenzverhalten und das Gibbssche Phänomen analysiert (13.2), die
komplexe Darstellung samt Amplitudenspektrum entwickelt (13.3) und schließlich
die Brücke zur erzwungenen Schwingung aus Kapitel 11 geschlagen (13.4).

Das durchgängige Leitbeispiel der Kurbelwelle hat dabei gezeigt, wie dieselbe
physikalische Fragestellung, nämlich die periodische Lagerkraft einer
rotierenden Welle, alle mathematischen Konzepte motiviert und verbindet. In
der Maschinenakustik, der Rotordynamik und der Regelungstechnik werden Sie
diese Werkzeuge auf komplexere Systeme anwenden und um die Fourier- und
Laplace-Transformation erweitern.
