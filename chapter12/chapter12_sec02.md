---
authors:
  - name: Simone Gramsch
---

# 12.2 Grundschwingung und Oberschwingungen

In Abschnitt 12.1 haben wir den Kolbenhub der Kurbelwelle mit der einfachen
Funktion $f(t) = 3\,\sin(\omega_0 t)$ modelliert. Das ist eine nützliche
Vereinfachung, aber wer schon einmal einen laufenden Motor gehört hat, ahnt,
dass das echte Signal komplizierter ist: Der Klang ändert sich mit der
Drehzahl, und bei manchen Drehzahlen entstehen störende Geräusche, die auf
bestimmte Schwingungsanteile zurückgehen. *Wie lässt sich das mathematisch
erfassen?* Die Antwort führt uns auf die Begriffe Grundschwingung und
Oberschwingung.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie kennen die Begriffe **Grundschwingung** und **Grundfrequenz** und
  können die Grundfrequenz $f_0 = 1/T$ aus der Periode $T$ berechnen.
* [ ] Sie kennen den Begriff **Oberschwingung** und können die Kreisfrequenzen
  der ersten Oberschwingungen zu einer gegebenen Grundfrequenz bestimmen.
* [ ] Sie können erklären, warum Oberschwingungen ganzzahlige Vielfache der
  Grundfrequenz sind, und diese Eigenschaft mit der Periodizität begründen.
* [ ] Sie können eine einfache Überlagerung von Grundschwingung und
  Oberschwingungen grafisch und rechnerisch auswerten.
```

## Was ist die Grundschwingung?

Wir kehren zu unserer Kurbelwelle mit der Periode $T = 0.04~\text{s}$ zurück.
Das einfachste periodische Signal mit genau dieser Periode ist eine
Sinusfunktion, die pro Zeitintervall der Länge $T$ genau einen vollständigen
Schwingungszyklus ausführt. Diese elementare Schwingung nennen wir die
**Grundschwingung** des Systems.

Neben der Kreisfrequenz $\omega_0 = 2\pi/T$ aus Abschnitt 12.1 ist es in der
Akustik und der Messtechnik üblich, die Schwingungsgeschwindigkeit durch die
**Grundfrequenz** $f_0$ anzugeben. Sie gibt an, wie viele vollständige
Schwingungszyklen pro Sekunde stattfinden.

```{admonition} Was ist ... die Grundschwingung?
:class: note
Zu einer periodischen Funktion mit Periode $T$ ist die **Grundschwingung** die
Sinusfunktion mit derselben Periode $T$. Ihre **Grundfrequenz** ist

\begin{equation*}
f_0 = \frac{1}{T},
\end{equation*}

gemessen in Hertz ($\text{Hz} = \text{s}^{-1}$). Die zugehörige
**Kreisfrequenz** ist $\omega_0 = 2\pi\,f_0 = 2\pi/T$.
```

Für die Kurbelwelle mit $T = 0.04~\text{s}$ ergibt sich

\begin{equation*}
f_0 = \frac{1}{T} = \frac{1}{0.04~\text{s}} = 25~\text{Hz}.
\end{equation*}

Die Kurbelwelle führt also $25$ Umdrehungen pro Sekunde aus. Das entspricht
der Drehzahl $n = 25~\text{s}^{-1} = 1500~\text{min}^{-1}$, die wir in
Abschnitt 12.1 als Ausgangspunkt gewählt haben. Die Kreisfrequenz der
Grundschwingung ist

\begin{equation*}
\omega_0 = 2\pi\,f_0 = 2\pi \cdot 25~\text{Hz} = 50\pi~\text{rad\,s}^{-1}
\approx 157.1~\text{rad\,s}^{-1}.
\end{equation*}

## Was sind Oberschwingungen?

Ein reales Motorsignal enthält neben der Grundschwingung weitere schnellere
Schwingungsanteile. Beim Vierzylindermotor zündet jeder Zylinder bei jeder
zweiten Kurbelwellenumdrehung, die Zündfrequenz beträgt also das Doppelte der
Grundfrequenz. Dazu kommen mechanische Ungleichförmigkeiten, die noch höhere
Frequenzanteile erzeugen. *Warum sind diese Zusatzfrequenzen ausgerechnet
ganzzahlige Vielfache der Grundfrequenz?*

Der Grund ist die Periodizität. Das Gesamtsignal soll nach der Zeit $T$
wieder denselben Wert annehmen. Eine Sinusfunktion mit der Frequenz $k \cdot
f_0$ führt in der Zeit $T$ genau $k$ vollständige Zyklen aus und erfüllt
damit $f(t + T) = f(t)$ automatisch. Eine Frequenz, die kein ganzzahliges
Vielfaches von $f_0$ ist, würde hingegen nach der Zeit $T$ an einer anderen
Stelle im Zyklus stehen und die Periodizität des Gesamtsignals zerstören.

```{admonition} Was ist ... eine Oberschwingung?
:class: note
Zu einer Grundfrequenz $f_0$ ist die **$k$-te Oberschwingung** ($k = 2, 3,
4, \ldots$) die Sinusfunktion mit der Frequenz

\begin{equation*}
f_k = k \cdot f_0
\end{equation*}

und der Kreisfrequenz

\begin{equation*}
\omega_k = k \cdot \omega_0 = \frac{2\pi\,k}{T}.
\end{equation*}

Die Grundschwingung selbst entspricht dem Fall $k = 1$.
```

Für die Kurbelwelle mit $f_0 = 25~\text{Hz}$ berechnen wir die ersten drei
Oberschwingungen:

| Ordnung $k$ | Bezeichnung | Frequenz $f_k$ | Kreisfrequenz $\omega_k$ | Technische Bedeutung |
|---|---|---|---|---|
| $1$ | Grundschwingung | $25~\text{Hz}$ | $50\pi~\text{rad\,s}^{-1}$ | Kurbelwellenumdrehung |
| $2$ | 1. Oberschwingung | $50~\text{Hz}$ | $100\pi~\text{rad\,s}^{-1}$ | Zündfrequenz (4-Zylinder) |
| $3$ | 2. Oberschwingung | $75~\text{Hz}$ | $150\pi~\text{rad\,s}^{-1}$ | Drehmomentwelligkeit |
| $4$ | 3. Oberschwingung | $100~\text{Hz}$ | $200\pi~\text{rad\,s}^{-1}$ | Strukturresonanz möglich |

In der Maschinenakustik und der Schwingungsdiagnose ist diese Tabelle ein
Standardwerkzeug: Tritt in einer Frequenzanalyse ein auffälliger Peak bei
$50~\text{Hz}$ auf, deutet das auf ein Problem im Zündrhythmus hin; ein Peak
bei $100~\text{Hz}$ kann auf eine Strukturresonanz der vierten Ordnung
hinweisen.

## Wie überlagern sich Grundschwingung und Oberschwingungen?

Jede Oberschwingung trägt mit einer bestimmten Stärke zum Gesamtsignal bei.
Diese Stärke wird durch ihre **Amplitude** beschrieben. Wenn wir
Grundschwingung und erste Oberschwingung mit den Amplituden $A_1$ und $A_2$
überlagern, erhalten wir eine neue Funktion:

\begin{equation*}
s(t) = A_1\,\sin(\omega_0\,t) + A_2\,\sin(2\omega_0\,t).
\end{equation*}

Diese Funktion ist ebenfalls periodisch mit der Periode $T$, hat aber eine
kompliziertere Form als eine einzelne Sinusfunktion. Als konkretes Beispiel
wählen wir $A_1 = 3~\text{cm}$ und $A_2 = 0.8~\text{cm}$:

\begin{equation*}
s(t) = 3\,\sin(50\pi\,t) + 0.8\,\sin(100\pi\,t).
\end{equation*}

Wir prüfen, dass $s$ tatsächlich die Periode $T = 0.04~\text{s}$ hat:

\begin{align*}
s(t + T)
&= 3\,\sin\!\bigl(50\pi\,(t + 0.04)\bigr) + 0.8\,\sin\!\bigl(100\pi\,(t + 0.04)\bigr) \\
&= 3\,\sin(50\pi\,t + 2\pi) + 0.8\,\sin(100\pi\,t + 4\pi) \\
&= 3\,\sin(50\pi\,t) + 0.8\,\sin(100\pi\,t) = s(t). \quad \checkmark
\end{align*}

Die Grundschwingung durchläuft einen Zyklus ($+2\pi$), die erste
Oberschwingung genau zwei Zyklen ($+4\pi$). Beide landen wieder am
Ausgangspunkt.

```{figure} pics/chap12_sec02_fig01.svg
---
name: chap12_sec02_fig01
---
Überlagerung von Grundschwingung $3\,\sin(50\pi\,t)$ (blau) und erster
Oberschwingung $0.8\,\sin(100\pi\,t)$ (rot) zum Summensignal $s(t)$ (grau,
gestrichelt) über eine Periode $T = 0.04~\text{s}$.
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Das Summensignal sieht nicht mehr wie eine glatte Sinuswelle aus. Je mehr
Oberschwingungen wir hinzunehmen, desto stärker kann das Gesamtsignal von
einer reinen Sinusfunktion abweichen. Rechteck-, Sägezahn- und
Dreiecksschwingungen entstehen auf genau diese Weise aus unendlich vielen
überlagerten Oberschwingungen. *Aber wie findet man die richtigen Amplituden,
wenn man ein gemessenes Signal in seine Oberschwingungen zerlegen will?* Diese
Frage beantwortet das Werkzeug der Fourierreihe, das wir in Abschnitt 12.3
kennenlernen.

## Zusammenfassung und Ausblick

Jedes periodische Signal lässt sich als Überlagerung einer Grundschwingung
mit der Frequenz $f_0 = 1/T$ und ihrer Oberschwingungen mit den Frequenzen
$k \cdot f_0$ beschreiben. Die Oberschwingungen sind zwingend ganzzahlige
Vielfache der Grundfrequenz, weil nur so die Periodizität des Gesamtsignals
erhalten bleibt. In der Maschinenakustik und der Regelungstechnik ist die
Kenntnis der dominanten Oberschwingungen ein zentrales Diagnosewerkzeug.

In Abschnitt 12.3 lernen wir die **Fourierreihe** kennen: ein systematisches
Verfahren, mit dem sich jede periodische Funktion eindeutig in ihre
Grundschwingung und Oberschwingungen zerlegen lässt und die zugehörigen
Amplituden berechnet werden können.
