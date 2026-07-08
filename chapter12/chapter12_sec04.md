---
authors:
  - name: Simone Gramsch
---

# 12.4 Erzwungene Schwingungen und Resonanz

In Abschnitt 11.3 schwang unser Maschinenelement ohne jede äußere Kraft mit
konstanter Amplitude: ein idealisiertes, aber physikalisch klares Bild. Jetzt
bringen wir eine periodische Kraft ins Spiel, wie sie in der Praxis durch eine
Unwucht in einem rotierenden Bauteil entsteht. *Was passiert, wenn die
Drehfrequenz des Rotors genau die Eigenfrequenz des Systems trifft?* Die
Antwort auf diese Frage ist eines der wichtigsten Entwurfskriterien im
Maschinenbau.

## Lernziele

```{admonition} Lernziele
:class: attention

* [ ] Sie können die inhomogene Schwingungsgleichung
  $y'' + \omega_0^2\,y = (F_0/m)\,\sin(\Omega t)$ aufstellen und die
  partikuläre Lösung für $\Omega \neq \omega_0$ durch den Ansatz
  $y_p = A\,\sin(\Omega t)$ berechnen.
* [ ] Sie kennen die **Resonanzamplitude**
  $\hat{y}_p = \frac{F_0/m}{|\omega_0^2 - \Omega^2|}$ und verstehen,
  warum sie für $\Omega \to \omega_0$ unbegrenzt wächst und nur für
  $\Omega \neq \omega_0$ sinnvoll definiert ist.
* [ ] Sie erkennen den Resonanzfall $\Omega = \omega_0$ und können erklären,
  warum der modifizierte Ansatz eine mit $t$ linear wachsende Lösung liefert,
  die zur **Resonanzkatastrophe** führt.
* [ ] Sie können die **kritische Drehzahl** als diejenige Betriebsdrehzahl
  beschreiben, bei der $\Omega = \omega_0$ gilt, und die Bedeutung dieser
  Größe für den Maschinenbau erläutern.
```

## Wie reagiert das System auf eine periodische Erregerkraft?

Eine rotierende Welle mit kleiner Unwucht erzeugt eine Kraft, die mit der
Drehfrequenz $\Omega$ periodisch schwankt. Wir modellieren diese Kraft als
$F(t) = F_0\,\sin(\Omega t)$ mit $F_0 = 4~\text{N}$. Um das Resonanzphänomen
in seiner reinsten Form zu zeigen, betrachten wir das ungedämpfte System
($d = 0$). Mit $m = 2~\text{kg}$, $\omega_0^2 = k/m = 2~\text{s}^{-2}$ und
$F_0/m = 2~\text{m\,s}^{-2}$ lautet die inhomogene Schwingungsgleichung:

\begin{equation*}
y'' + 2\,y = 2\,\sin(\Omega\,t).
\end{equation*}

Für $\Omega \neq \omega_0 = \sqrt{2}$ setzen wir den Ansatz
$y_p = A\,\sin(\Omega t) + B\,\cos(\Omega t)$ an. Da die ODE keinen $y'$-Term
enthält und die rechte Seite nur Sinus enthält, koppeln Sinus- und
Kosinusanteile im Koeffizientenvergleich nicht. Einsetzen liefert:

\begin{align*}
y_p'' + 2\,y_p
&= (2 - \Omega^2)(A\,\sin(\Omega t) + B\,\cos(\Omega t))
\stackrel{!}{=} 2\,\sin(\Omega t).
\end{align*}

Koeffizientenvergleich ergibt $B = 0$ und:

\begin{equation*}
(2 - \Omega^2)\,A = 2
\qquad \Rightarrow \qquad
A = \frac{2}{2 - \Omega^2}.
\end{equation*}

In allgemeiner Schreibweise mit $\omega_0^2 = k/m$ lautet die partikuläre
Lösung:

\begin{equation*}
y_p(t) = \frac{F_0/m}{\omega_0^2 - \Omega^2}\,\sin(\Omega\,t).
\end{equation*}

```{admonition} Was ist ... die Resonanzamplitude?
:class: note
Bei der ungedämpften erzwungenen Schwingung
$y'' + \omega_0^2\,y = (F_0/m)\,\sin(\Omega t)$ lautet die
**Resonanzamplitude** der partikulären Lösung:

\begin{equation*}
\hat{y}_p = \frac{F_0/m}{|\omega_0^2 - \Omega^2|}.
\end{equation*}

Diese Formel ist nur für $\Omega \neq \omega_0$ definiert: Im exakten
Resonanzfall $\Omega = \omega_0$ existiert keine sinusförmige stationäre
Antwort mehr; die partikuläre Lösung enthält dann einen Faktor $t$ und
wächst im Betrag mit der Zeit.

Für sehr langsame Erregung $\Omega \to 0$ gilt $\hat{y}_p \to F_0/k$: das
ist die statische Auslenkung unter der Kraft $F_0$. Für $\Omega \to \omega_0$
wächst $\hat{y}_p$ ohne Schranke. Im schwingungstechnischen Sinn bezeichnet
man genau diesen Fall der Frequenzgleichheit von Eigenfrequenz und
Erregerfrequenz als **Resonanz**.
```

Wir berechnen die vollständige Lösung für $\Omega = 1~\text{rad\,s}^{-1}$,
also für eine Drehzahl deutlich unterhalb der Eigenfrequenz
$\omega_0 = \sqrt{2} \approx 1.41~\text{rad\,s}^{-1}$:

\begin{equation*}
A = \frac{2}{2 - 1^2} = 2
\qquad \Rightarrow \qquad
y_p(t) = 2\,\sin(t).
\end{equation*}

Wir verifizieren durch Einsetzen:
$y_p'' + 2\,y_p = -2\sin(t) + 4\sin(t) = 2\sin(t)$. $\checkmark$

Für die Anfangsbedingungen $y(0) = 0$ und $y'(0) = 0$ (System startet in
Ruhe, die Unwuchtkraft setzt bei $t = 0$ ein) ergibt sich mit der allgemeinen
Lösung $y = C_1\cos(\sqrt{2}\,t) + C_2\sin(\sqrt{2}\,t) + 2\sin(t)$:

\begin{equation*}
C_1 = 0, \qquad \sqrt{2}\,C_2 + 2 = 0 \;\Rightarrow\; C_2 = -\sqrt{2}.
\end{equation*}

Die vollständige Lösung lautet:

\begin{equation*}
y(t) = -\sqrt{2}\,\sin(\sqrt{2}\,t) + 2\,\sin(t)~\text{m}.
\end{equation*}

Die Bewegung ist eine Überlagerung zweier Sinusschwingungen: die freie
Schwingung bei $\omega_0 = \sqrt{2}$ mit Amplitude $\sqrt{2} \approx 1.41~\text{m}$
und die erzwungene Schwingung bei $\Omega = 1$ mit Amplitude $2~\text{m}$. Beide
Amplituden sind endlich. Da die Frequenzen nahe beieinander liegen, zeigt der
Verlauf eine typische **Schwebung**: Die schnelle Schwingung wird von einer
langsam veränderlichen Hüllkurve mit der Differenzfrequenz $|\omega_0 - \Omega|$
moduliert. In der Maschinendynamik nennt man diesen Betriebszustand
den unterkritischen Betrieb: Die Drehfrequenz liegt unterhalb der kritischen
Drehzahl, die Schwingungen bleiben beherrschbar.

## Was passiert, wenn die Erregerfrequenz die Eigenfrequenz trifft?

Wir erhöhen die Drehzahl auf genau $\Omega = \omega_0 = \sqrt{2}~\text{rad\,s}^{-1}$.
Die ODE lautet jetzt:

\begin{equation*}
y'' + 2\,y = 2\,\sin(\sqrt{2}\,t).
\end{equation*}

Der Standardansatz $y_p = A\,\sin(\sqrt{2}\,t) + B\,\cos(\sqrt{2}\,t)$ schlägt
fehl, weil $\sin(\sqrt{2}\,t)$ und $\cos(\sqrt{2}\,t)$ Lösungen der homogenen
ODE sind. Einsetzen würde $0 = 2\sin(\sqrt{2}\,t)$ ergeben. Wie in Abschnitt
11.2 gezeigt, rettet ein zusätzlicher Faktor $t$ den Ansatz:

\begin{equation*}
y_p(t) = A\,t\,\sin(\sqrt{2}\,t) + B\,t\,\cos(\sqrt{2}\,t).
\end{equation*}

Wir berechnen $y_p'' + 2\,y_p$. Nach zweimaligem Ableiten und Vereinfachen
verbleiben nur die zeitlich konstanten Vorfaktoren:

\begin{equation*}
y_p'' + 2\,y_p = 2A\,\sqrt{2}\,\cos(\sqrt{2}\,t) - 2B\,\sqrt{2}\,\sin(\sqrt{2}\,t).
\end{equation*}

Der Koeffizientenvergleich mit $2\,\sin(\sqrt{2}\,t)$ liefert:

\begin{equation*}
2A\sqrt{2} = 0 \;\Rightarrow\; A = 0,
\qquad
-2B\sqrt{2} = 2 \;\Rightarrow\; B = -\frac{\sqrt{2}}{2}.
\end{equation*}

Die partikuläre Lösung im Resonanzfall lautet:

\begin{equation*}
y_p(t) = -\frac{\sqrt{2}}{2}\,t\,\cos(\sqrt{2}\,t).
\end{equation*}

Wir verifizieren durch Einsetzen. Mit $y_p'' = 2\sin(\sqrt{2}\,t) + \sqrt{2}\,t\,\cos(\sqrt{2}\,t)$
gilt:

\begin{equation*}
y_p'' + 2\,y_p
= 2\sin(\sqrt{2}\,t) + \sqrt{2}\,t\,\cos(\sqrt{2}\,t) -
  \sqrt{2}\,t\,\cos(\sqrt{2}\,t)
= 2\sin(\sqrt{2}\,t). \quad \checkmark
\end{equation*}

Für die Anfangsbedingungen $y(0) = 0$, $y'(0) = 0$ ergibt sich die vollständige
Lösung:

\begin{equation*}
y(t) = \tfrac{1}{2}\,\sin(\sqrt{2}\,t)
       - \tfrac{\sqrt{2}}{2}\,t\,\cos(\sqrt{2}\,t)~\text{m}.
\end{equation*}

Der erste Term $\tfrac{1}{2}\sin(\sqrt{2}\,t)$ ist eine gewöhnliche Sinusschwingung
mit beschränkter Amplitude. Der zweite Term $-\tfrac{\sqrt{2}}{2}\,t\,\cos(\sqrt{2}\,t)$
ist das Kennzeichen der **Resonanzkatastrophe**: Seine Amplitude $\tfrac{\sqrt{2}}{2}\,t$
wächst linear mit der Zeit ohne jede Schranke. Nach $t = 10~\text{s}$ beträgt
die Amplitude bereits $\tfrac{\sqrt{2}}{2} \cdot 10 \approx 7.1~\text{m}$, nach
$t = 100~\text{s}$ über $70~\text{m}$. Ein reales Bauteil würde bei einem
Bruchteil dieser Werte versagen.

```{figure} pics/chap11_sec04_fig01.svg
:name: fig-chap11-sec04-resonanzkatastrophe

Zeitverlauf der vollständigen Lösung im Resonanzfall $\Omega = \omega_0 = \sqrt{2}\,\text{rad\,s}^{-1}$ mit den Hüllkurven $\pm\tfrac{\sqrt{2}}{2}\,t$, die das unbegrenzte lineare Amplitudenwachstum zeigen.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

```{admonition} Merkregel: Resonanz und kritische Drehzahl
:class: note
Die **kritische Drehzahl** $n_{\text{krit}}$ einer Welle oder eines Rotors ist
die Drehzahl, bei der die Erregerfrequenz $\Omega = 2\pi\,n$ mit der
Eigenfrequenz $\omega_0 = \sqrt{k/m}$ übereinstimmt:

\begin{equation*}
n_{\text{krit}} = \frac{\omega_0}{2\pi} = \frac{1}{2\pi}\sqrt{\frac{k}{m}}.
\end{equation*}

Im schwingungstechnischen Sinn spricht man genau in diesem Fall
$\Omega = \omega_0$ von **Resonanz**. Im Maschinenbau wird die kritische
Drehzahl entweder durch gezielte Dämpfung entschärft oder durch konstruktive
Maßnahmen so gelegt, dass der Betriebsbereich sie weit verfehlt.
```

```{figure} pics/chap11_sec04_fig02.svg
:name: fig-chap11-sec04-amplitudenfrequenzgang

Amplitudenfrequenzgang der ungedämpften erzwungenen Schwingung: Die normierte Resonanzamplitude $\hat{y}_p\,k/F_0$ divergiert bei $\Omega = \omega_0$ und nähert sich für $\Omega \to 0$ dem statischen Wert $F_0/k$ an.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

In der Ingenieurpraxis ist reiner Resonanzbetrieb ohne Dämpfung nie dauerhaft
möglich: Jedes reale System hat eine Restdämpfung, die das unbegrenzte Anwachsen
verhindert und die Amplitude auf einen endlichen, wenn auch sehr großen Wert
begrenzt. Trotzdem können beim Hochlaufen eines Motors auf Betriebsdrehzahl
oder beim Abfahren die kritischen Drehzahlen durchfahren werden. Ingenieurinnen
und Ingenieure müssen dann sicherstellen, dass die Anlage schnell genug durch
den Resonanzbereich geführt wird, bevor die Schwingungsamplituden gefährliche
Werte annehmen. In der Maschinenakustik, der Schwingungslehre und der
Rotordynamik werden Sie diese Fragen systematisch vertiefen.

```{admonition} Lernkontrolle
:class: tip
[![Logo](../logos/quiz_play_badge.svg)](https://gramschs.github.io/thma_mathematik03_assets/interactive/chapter11/chap11_sec04_quiz.html)
```

## Zusammenfassung: Kapitel 11

Mit Abschnitt 11.4 schließt sich der Bogen von Kapitel 11. Aus dem Newtonschen
Gesetz haben wir die Bewegungsgleichung des Feder-Masse-Systems hergeleitet,
mit den Methoden aus Kapitel 10 die homogene Lösung $y_h$ bestimmt und in den
Abschnitten 11.1 bis 11.4 die partikuläre Lösung $y_p$ für alle technisch
wichtigen Störfunktionen berechnet: abklingende Stoßkräfte, den Resonanzfall
mit wachsendem Ansatz, und periodische Erregerkräfte bis hin zur
Resonanzkatastrophe.

Die allgemeine Lösung $y_{\text{allgemein}} = y_h + y_p$ ist damit das
vollständige Werkzeug zur Beschreibung linearer Schwingungssysteme. Die freien
Konstanten legen Anfangslage und Anfangsgeschwindigkeit fest, die Eigenfrequenz
$\omega_0$ ist eine reine Systemeigenschaft, und die Resonanz tritt genau dann
auf, wenn Erreger und System im selben Takt schwingen. Dieses Grundprinzip
bleibt in allen späteren Lehrveranstaltungen wie der Technischen Mechanik 3,
der Maschinendynamik und der Schwingungsmesstechnik erhalten, auch wenn die
Systeme dort komplexer und die Methoden verfeinert sind.
