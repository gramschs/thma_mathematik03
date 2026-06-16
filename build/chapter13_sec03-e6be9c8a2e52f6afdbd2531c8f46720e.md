---
authors:
  - name: Simone Gramsch
---

# 13.3 Die komplexe Fourierreihe

In Abschnitt 13.2 haben wir gesehen, dass die Fourierkoeffizienten der
Lagerkraft wie $1/n$ abklingen und damit auch hohe Frequenzen noch spürbar
beitragen. In der Schwingungsdiagnose stellt man genau diese Information
grafisch dar: Ein FFT-Analysator zeigt für eine gemessene Lagerkraft ein
Spektrum, in dem über jeder Frequenz ein einziger Amplitudenwert steht.
Unsere reelle Fourierreihe liefert dagegen pro Frequenz zwei Zahlen, nämlich
$a_n$ und $b_n$. *Lässt sich die Reihe so umschreiben, dass jede Frequenz nur
noch einen einzigen Koeffizienten trägt?* Die Antwort liefert die eulersche
Formel, die uns in Abschnitt 10.4 bereits geholfen hat, komplexe Eigenwerte
in reelle Schwingungslösungen zu übersetzen.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie kennen die **komplexe Fourierreihe** mit den Koeffizienten $c_n$
  und können beide Formeln (Reihe und Koeffizienten) angeben.
* [ ] Sie können die komplexen Fourierkoeffizienten $c_n$ aus den reellen
  Koeffizienten $a_n$ und $b_n$ umrechnen und umgekehrt.
* [ ] Sie können das **Amplitudenspektrum** eines periodischen Signals aus
  den $c_n$ berechnen und technisch interpretieren.
* [ ] Sie verstehen, wie die eulersche Formel die reelle und die komplexe
  Darstellung der Fourierreihe miteinander verbindet.
```

## Wie kommt die komplexe Exponentialfunktion in die Fourierreihe?

Wir erinnern uns an Abschnitt 10.4: Die eulersche Formel

\begin{equation*}
e^{i\varphi} = \cos\varphi + i\,\sin\varphi
\end{equation*}

verbindet die komplexe Exponentialfunktion mit Kosinus und Sinus. Dort haben
wir sie benutzt, um aus komplexen Eigenwerten reelle Schwingungslösungen zu
gewinnen. Jetzt lesen wir sie in der Gegenrichtung: Wir lösen nach Kosinus und
Sinus auf. Schreiben wir die Formel einmal für $\varphi$ und einmal für
$-\varphi$ auf und addieren beziehungsweise subtrahieren beide Gleichungen,
so erhalten wir

\begin{equation*}
\cos\varphi = \frac{e^{i\varphi} + e^{-i\varphi}}{2}
\qquad \text{und} \qquad
\sin\varphi = \frac{e^{i\varphi} - e^{-i\varphi}}{2i}.
\end{equation*}

Jede reelle Schwingung ist also eine Überlagerung zweier komplexer
Exponentialfunktionen mit den Frequenzen $+\varphi$ und $-\varphi$. Genau das
setzen wir jetzt in einen Summanden der reellen Fourierreihe aus Abschnitt
12.3 ein:

\begin{align*}
a_n\cos(n\omega_0 t) + b_n\sin(n\omega_0 t)
&= \frac{a_n}{2}\bigl(e^{in\omega_0 t} + e^{-in\omega_0 t}\bigr) +
   \frac{b_n}{2i}\bigl(e^{in\omega_0 t} - e^{-in\omega_0 t}\bigr) \\
&= \frac{a_n - i\,b_n}{2}\,e^{in\omega_0 t} +
   \frac{a_n + i\,b_n}{2}\,e^{-in\omega_0 t}.
\end{align*}

Dabei haben wir $1/i = -i$ benutzt. Jeder reelle Summand zerfällt also in
zwei komplexe Exponentialterme, einen mit positiver Frequenz $n\omega_0$ und
einen mit negativer Frequenz $-n\omega_0$. Vor jedem Exponentialterm steht
nur noch eine einzige komplexe Zahl. Diese Zahlen bekommen einen Namen: Wir
setzen $c_n = (a_n - i\,b_n)/2$ und $c_{-n} = (a_n + i\,b_n)/2$, und für den
Mittelwert $c_0 = a_0/2$. Lassen wir den Summationsindex damit von $-\infty$
bis $+\infty$ laufen, entsteht eine bemerkenswert kompakte Darstellung.

```{admonition} Was ist ... die komplexe Fourierreihe?
:class: note
Die **komplexe Fourierreihe** einer periodischen Funktion $f$ mit Periode $T$
und Kreisfrequenz $\omega_0 = 2\pi/T$ ist

\begin{equation*}
f(t) = \sum_{n=-\infty}^{\infty} c_n\,e^{i n \omega_0 t},
\qquad
c_n = \frac{1}{T}\int_{-T/2}^{T/2} f(t)\,e^{-i n \omega_0 t}\,dt.
\end{equation*}

Die **komplexen Fourierkoeffizienten** $c_n$ sind im Allgemeinen komplexe
Zahlen. Sie tragen Amplituden- und Phaseninformation der $n$-ten Schwingung
zugleich. Für eine reellwertige Funktion gilt stets $c_{-n} = \overline{c_n}$.
```

Statt zwei reeller Integralformeln für $a_n$ und $b_n$ gibt es nur noch eine
einzige Integralformel, und statt zweier Koeffizienten pro Frequenz nur noch
einen. Der Preis dafür ist, dass auch negative Indizes $n$ auftreten. Die
zugehörigen negativen Frequenzen sind kein physikalisches Mysterium, sondern
reine Buchhaltung: Erst das Paar aus $c_n\,e^{in\omega_0 t}$ und
$c_{-n}\,e^{-in\omega_0 t}$ ergibt zusammen eine reelle Schwingung, so wie
oben Kosinus und Sinus aus zwei Exponentialtermen zusammengesetzt waren.

Für das Umrechnen zwischen beiden Darstellungen halten wir die Formeln fest,
die wir gerade hergeleitet haben:

```{admonition} Wie wird zwischen reeller und komplexer Darstellung umgerechnet?
:class: note
Für $n \geq 1$ gilt

\begin{equation*}
c_0 = \frac{a_0}{2}, \qquad
c_n = \frac{a_n - i\,b_n}{2}, \qquad
c_{-n} = \frac{a_n + i\,b_n}{2},
\end{equation*}

und in der Gegenrichtung

\begin{equation*}
a_n = c_n + c_{-n}, \qquad
b_n = i\,\bigl(c_n - c_{-n}\bigr).
\end{equation*}

Die Amplitude der $n$-ten Harmonischen ist
$\hat{A}_n = \sqrt{a_n^2 + b_n^2} = 2\,|c_n|$.
```

## Welche komplexen Koeffizienten hat die Lagerkraft?

Wir wenden die Umrechnungsformeln auf unser Leitbeispiel an, die
Rechteck-Lagerkraft aus Abschnitt 12.4. Dort haben wir berechnet: $a_0 = 0$,
$a_n = 0$ für alle $n \geq 1$, und

\begin{equation*}
b_n = \begin{cases}
0, & n \text{ gerade}, \\[4pt]
\dfrac{4}{n\pi}, & n \text{ ungerade}.
\end{cases}
\end{equation*}

Damit ist $c_0 = 0$, und für gerades $n$ verschwinden alle $c_n$. Für
ungerades $n \geq 1$ liefert die Umrechnung

\begin{equation*}
c_n = \frac{0 - i\,\frac{4}{n\pi}}{2} = -\frac{2\,i}{n\pi},
\qquad
c_{-n} = +\frac{2\,i}{n\pi}.
\end{equation*}

Die Koeffizienten sind rein imaginär. Das ist kein Zufall, sondern die
komplexe Übersetzung der Symmetrieregel aus Abschnitt 13.1: Bei einer
ungeraden Funktion verschwinden alle $a_n$, also verschwinden die Realteile
aller $c_n$. Außerdem prüfen wir: $c_{-n} = \overline{c_n}$ ist erfüllt, wie
es für eine reellwertige Funktion sein muss. $\checkmark$

**Verifikation durch Rückrechnung.** Wir setzen das Koeffizientenpaar für
$n = \pm 1$ wieder in die komplexe Reihe ein und prüfen, ob die
Grundschwingung aus Abschnitt 12.4 herauskommt:

\begin{align*}
c_1\,e^{it} + c_{-1}\,e^{-it}
&= -\frac{2i}{\pi}\,e^{it} + \frac{2i}{\pi}\,e^{-it}
= -\frac{2i}{\pi}\bigl(e^{it} - e^{-it}\bigr) \\
&= -\frac{2i}{\pi}\cdot 2i\,\sin(t)
= \frac{4}{\pi}\,\sin(t).
\end{align*}

Das ist exakt der Term $b_1\sin(t)$ mit $b_1 = 4/\pi$ aus Abschnitt 12.4.
$\checkmark$ Die komplexe Darstellung enthält also dieselbe Information wie
die reelle, nur anders verpackt.

## Was zeigt das Amplitudenspektrum?

Jetzt ernten wir den eigentlichen Gewinn der komplexen Darstellung. Der
Betrag $|c_n|$ ist eine einzige reelle Zahl pro Frequenz, und genau diese
Zahlen trägt ein Spektrum auf.

```{admonition} Was ist ... das Amplitudenspektrum?
:class: note
Das **Amplitudenspektrum** eines periodischen Signals ist die Darstellung der
Beträge $|c_n|$ über den Frequenzen $n\,\omega_0$ mit
$n \in \mathbb{Z}$. Es zeigt auf einen Blick, welche Frequenzen im Signal
enthalten sind und wie stark sie beitragen. Die physikalische Amplitude der
$n$-ten Harmonischen ist $\hat{A}_n = 2\,|c_n|$, weil sich ihr Beitrag auf die
beiden Spektrallinien bei $+n\omega_0$ und $-n\omega_0$ verteilt.
```

Für die Lagerkraft $F(t) = F_0 \cdot f(t)$ mit der Grundfrequenz
$f_0 = 25~\text{Hz}$ aus Abschnitt 12.2 ergibt sich: Spektrallinien existieren
nur bei den ungeraden Vielfachen $\pm 25~\text{Hz}$, $\pm 75~\text{Hz}$,
$\pm 125~\text{Hz}$ und so weiter, mit den Beträgen

\begin{equation*}
|c_n| = \frac{2}{|n|\,\pi}\,F_0, \qquad n \text{ ungerade}.
\end{equation*}

Die Grundschwingung bei $25~\text{Hz}$ hat die physikalische Amplitude
$\hat{A}_1 = 2\,|c_1| = \frac{4}{\pi}\,F_0 \approx 1.27\,F_0$. Die
dritte Harmonische bei $75~\text{Hz}$ bringt es auf
$\hat{A}_3 = \frac{4}{3\pi}\,F_0 \approx 0.42\,F_0$, also exakt ein Drittel
der Grundschwingungsamplitude. Das langsame $1/n$-Abklingen aus Abschnitt
13.2 wird im Spektrum unmittelbar sichtbar.

%```{figure} pics/chap13_sec03_fig01.svg
%---
%name: chap13_sec03_fig01
%---
%Zweiseitiges Amplitudenspektrum $|c_n|$ der Rechteck-Lagerkraft: Spektrallinien
%nur bei ungeraden Vielfachen der Grundfrequenz $f_0 = 25~\text{Hz}$, symmetrisch
%zu positiven und negativen Frequenzen.
%(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
%```

In der Maschinendiagnose ist genau diese Darstellung das Standardwerkzeug:
Wälzlagerschäden, Unwuchten oder Zahneingriffsfehler verraten sich durch
charakteristische Linien im gemessenen Spektrum, und die Ordnungsanalyse
rotierender Maschinen trägt die Amplituden direkt über den Vielfachen der
Drehfrequenz auf. Auch die FFT-Algorithmen, die solche Messgeräte intern
verwenden, rechnen ausnahmslos mit der komplexen Darstellung, weil sie
algebraisch einfacher ist als das Hantieren mit getrennten Sinus- und
Kosinusanteilen. In der Lehrveranstaltung Regelungstechnik werden Sie der
komplexen Exponentialfunktion in Gestalt des Frequenzgangs $G(i\omega)$
wiederbegegnen.

## Zusammenfassung und Ausblick

Die eulersche Formel verwandelt die reelle Fourierreihe in eine kompakte
komplexe Form: ein Koeffizient $c_n$ pro Frequenz, eine einzige
Integralformel, und der Betrag $|c_n|$ liefert direkt das Amplitudenspektrum.
Für die Rechteck-Lagerkraft besteht das Spektrum aus Linien bei den ungeraden
Vielfachen der Grundfrequenz, deren Höhen wie $1/n$ abfallen.

Im Spektrum der Lagerkraft steht damit unübersehbar eine Linie bei
$75~\text{Hz}$ mit immerhin einem Drittel der Grundschwingungsamplitude.
*Was passiert, wenn genau bei dieser Frequenz die Eigenfrequenz des
Pleuellagers liegt?* In Abschnitt 13.4 schlagen wir den Bogen zurück zu den
erzwungenen Schwingungen aus Kapitel 11 und beantworten diese Frage
rechnerisch.
