---
authors:
  - name: Simone Gramsch
---

# 7.3 Technische Anwendungen der Separation der Variablen

In den Abschnitten 7.1 und 7.2 haben wir zwei analytische Lösungsverfahren entwickelt:
die Trennung der Variablen für ODEs der Form $y' = f(x) \cdot g(y)$ und die Substitution
für ODEs der Form $y' = f(ax + by + c)$. Jetzt wenden wir beide Verfahren auf konkrete
Ingenieurprobleme an. Der Schwerpunkt liegt dabei auf den Schritten, die in 7.1 und 7.2
noch fehlten: eine physikalische Situation als ODE zu formulieren, den richtigen Lösungsweg
zu erkennen und das mathematische Ergebnis physikalisch zu deuten.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können zu einer physikalischen Problemstellung die zugehörige ODE aufstellen
  und als separierbar identifizieren.
* [ ] Sie können die **Euler-Eytelwein-Gleichung** $F' = \mu\,F$ durch Separation lösen,
  das Ergebnis auf ein Riementrieb-Beispiel mit konkreten Zahlenwerten anwenden und
  physikalisch interpretieren.
* [ ] Sie können die **Torricellische Ausflussgleichung** $\dot{h} = -k\sqrt{h}$ durch
  Separation lösen, die Entleerungszeit berechnen und das Ergebnis physikalisch deuten.
* [ ] Sie können anhand der Struktur der rechten Seite einer ODE entscheiden, ob die
  direkte Separation (Abschnitt 7.1) oder die Substitutionsmethode (Abschnitt 7.2)
  anzuwenden ist.
```

## Beispiel 1: Seilkraft am Riementrieb

An einem Riementrieb läuft ein Flachriemen über eine Scheibe mit dem
Reibungskoeffizienten $\mu = 0.3$. Auf der Zugseite wirkt die große Kraft $F$, auf der
Schlupfseite die kleine Haltekraft $F_0$. *Wie ändert sich die Riemenkraft entlang des
Umschlingungsbogens, und wie groß ist der Kraftunterschied für eine Umschlingung von
$180°$?*

### Aufstellen der ODE

Wir betrachten ein infinitesimales Bogenelement des Riemens am Umschlingungswinkel
$\varphi$. Die Reibungskraft an diesem Element ist proportional zur lokalen Riemenkraft
$F(\varphi)$ und zum Winkelinkrement $d\varphi$. Das Kräftegleichgewicht ergibt die
**Euler-Eytelwein-Gleichung**:

\begin{equation*}
\frac{dF}{d\varphi} = \mu\,F.
\end{equation*}

Die gesuchte Funktion ist $F(\varphi)$, die unabhängige Variable ist der
Umschlingungswinkel $\varphi$. Die rechte Seite hat die Form $\mu \cdot F$, also
$f(\varphi) \cdot g(F) = \mu \cdot F$. Die ODE ist separierbar.

### Lösung durch Separation

Wir wenden das Verfahren aus Abschnitt 7.1 an. Die Anfangsbedingung ist $F(0) =
F_0$: die Riemenkraft an der Schlupfseite ($\varphi = 0$) ist bekannt.

**Trennen:**

\begin{equation*}
\frac{dF}{F} = \mu\,d\varphi.
\end{equation*}

**Integrieren und Stammfunktion einsetzen:**

\begin{equation*}
\ln|F| = \mu\varphi + C_1 \quad \Rightarrow \quad F(\varphi) = C\,e^{\mu\varphi},
\quad C > 0.
\end{equation*}

**Anfangsbedingung einsetzen:** $F(0) = C\,e^{0} = C = F_0$. Die spezielle
Lösung lautet:

\begin{equation*}
F(\varphi) = F_0\,e^{\mu\varphi}.
\end{equation*}

**Verifikation:** $F'(\varphi) = F_0\,\mu\,e^{\mu\varphi} = \mu \cdot
F(\varphi)$. $\checkmark$

### Ergebnis und physikalische Interpretation

Mit $\mu = 0.3$ und einer Umschlingung von $180°$, also $\varphi = \pi$:

\begin{equation*}
F(\pi) = F_0\,e^{0.3\pi} \approx F_0 \cdot 2.57.
\end{equation*}

Für eine Haltekraft von $F_0 = 200~\text{N}$ auf der Schlupfseite beträgt die Zugkraft
auf der Gegenseite also rund $514~\text{N}$, mehr als das Doppelte. Der Faktor
$e^{\mu\varphi}$ wächst exponentiell mit dem Umschlingungswinkel: Bei einer vollen
Umrundung ($\varphi = 2\pi$) betrüge das Verhältnis bereits $e^{0.6\pi} \approx 6.6$.
Dieses Prinzip nutzen Winden und Poller: Wenige Umschlingungen genügen, um sehr große
Lasten mit kleiner Haltekraft zu sichern. In der Auslegung von Riemengetrieben und
Seilzügen, die Sie in der Vorlesung Maschinenelemente vertiefen werden, ist das
Euler-Eytelwein-Gesetz eine Grundformel.

## Beispiel 2: Entleerung eines Hydraulikbehälters

Ein zylindrischer Hydraulikbehälter mit konstantem Querschnitt hat zum Zeitpunkt $t = 0$
einen Füllstand von $h_0 = 0.64~\text{m}$. Durch eine Bodenöffnung fließt Öl aus.
Nach dem Torricellischen Ausflussgesetz ist die Ausflussgeschwindigkeit proportional zur
Wurzel des aktuellen Füllstands. *Wann ist der Behälter leer, und wie verläuft der
Füllstand dabei zeitlich?*

<!-- markdownlint-disable -->
### Aufstellen der ODE
<!-- markdownlint-enable -->

Die Volumenänderungsrate im Behälter entspricht dem abfließenden Volumenstrom.
Mit dem Behälterquerschnitt $A$ und dem Ausflusskoeffizienten folgt nach
Division durch $A$ die **Torricellische Ausflussgleichung**:

\begin{equation*}
\dot{h} = -k\sqrt{h}, \quad k = 0.04~\text{m}^{1/2}\,\text{s}^{-1}.
\end{equation*}

Das negative Vorzeichen drückt aus, dass der Füllstand sinkt. Die rechte Seite
hat die Form $f(t) \cdot g(h) = (-k) \cdot \sqrt{h}$, die ODE ist also
separierbar.

Bevor wir durch $\sqrt{h}$ dividieren, prüfen wir den **Sonderfall** $g(h) =
\sqrt{h} = 0$, also $h = 0$: Ein leerer Behälter bleibt leer, $\dot{h} = 0$. Das
ist die konstante Lösung $h(t) = 0$, physikalisch trivial, aber mathematisch
vollständig.

<!-- markdownlint-disable -->
### Lösung durch Separation
<!-- markdownlint-enable -->

Die Anfangsbedingung ist $h(0) = h_0 = 0.64~\text{m}$. Wir setzen $h > 0$ voraus.

**Trennen:**

\begin{equation*}
\frac{dh}{\sqrt{h}} = -k\,dt.
\end{equation*}

**Integrieren und Stammfunktion einsetzen:**

\begin{equation*}
\int h^{-1/2}\,dh = \int -k\,dt \quad \Rightarrow \quad 2\sqrt{h} = -kt + C_1.
\end{equation*}

**Anfangsbedingung einsetzen:** $2\sqrt{h_0} = C_1$, also:

\begin{equation*}
\sqrt{h(t)} = \sqrt{h_0} - \frac{k}{2}\,t.
\end{equation*}

**Nach $h$ auflösen:** Quadrieren ergibt die spezielle Lösung:

\begin{equation*}
h(t) = \left(\sqrt{h_0} - \frac{k}{2}\,t\right)^2.
\end{equation*}

Diese Formel gilt, solange $\sqrt{h_0} - \frac{k}{2}\,t \geq 0$ ist. Danach gilt
$h(t) = 0$.

**Verifikation:** Die Ableitung der Lösung ist:

\begin{equation*}
\dot{h}(t) = 2\!\left(\sqrt{h_0} - \frac{k}{2}\,t\right)\cdot\left(-\frac{k}{2}\right)
           = -k\left(\sqrt{h_0} - \frac{k}{2}\,t\right).
\end{equation*}

Die rechte Seite der ODE ergibt:

\begin{equation*}
-k\sqrt{h(t)} = -k\sqrt{\left(\sqrt{h_0} - \frac{k}{2}\,t\right)^2}
              = -k\left(\sqrt{h_0} - \frac{k}{2}\,t\right). \quad \checkmark
\end{equation*}

<!-- markdownlint-disable -->
### Ergebnis und physikalische Interpretation
<!-- markdownlint-enable -->

Mit $h_0 = 0.64~\text{m}$, also $\sqrt{h_0} = 0.8~\text{m}^{1/2}$, und
$k = 0.04~\text{m}^{1/2}\,\text{s}^{-1}$:

\begin{equation*}
h(t) = \bigl(0.8 - 0.02\,t\bigr)^2~\text{m}.
\end{equation*}

Der Behälter ist leer, wenn $\sqrt{h} = 0$, also wenn $0.8 -
0.02\,t_{\text{leer}} = 0$:

\begin{equation*}
t_{\text{leer}} = \frac{2\sqrt{h_0}}{k} = \frac{2 \cdot 0.8}{0.04} = 40~\text{s}.
\end{equation*}

Das ist ein bemerkenswert konkretes Ergebnis: Der Behälter entleert sich in
endlicher Zeit. Im Vergleich dazu würde ein Modell mit linearem Ausfluss
($\dot{h} = -k\,h$) den Füllstand nur asymptotisch gegen null treiben, der
Behälter wäre theoretisch nie leer. Die Nichtlinearität $\sqrt{h}$ liefert hier
das physikalisch realistischere Bild. In der Hydraulik, die Sie in der
Strömungslehre vertiefen werden, bildet das Torricellische Ausflussgesetz die
Grundlage für die Dimensionierung von Ablaufventilen und
Druckausgleichsbehältern.

## Welche Methode für welche ODE?

Mit den Beispielen dieses Kapitels lässt sich eine einfache Entscheidungsregel formulieren.
Der erste Blick gilt der Struktur der rechten Seite:

<!-- markdownlint-disable -->
| Struktur der rechten Seite | Methode | Abschnitt |
| --- | --- | --- |
| $y' = f(x) \cdot g(y)$ (Produkt aus reinem $x$-Anteil und reinem $y$-Anteil) | Trennung der Variablen | 7.1 |
| $y' = f(ax + by + c)$ (Funktion einer Linearkombination) | Substitution $u = ax + by + c$ | 7.2 |
<!-- markdownlint-enable -->

In der Praxis empfiehlt es sich, zuerst auf eine Produktstruktur zu prüfen.
Gelingt die Faktorisierung nicht, ist zu fragen, ob die rechte Seite von einer
Linearkombination $ax + by + c$ abhängt. Trifft keine der beiden Formen zu,
führt weder Separation noch Substitution direkt zum Ziel. Für solche Fälle
stellt Kapitel 8 die Lösungstheorie linearer ODEs 1. Ordnung bereit, die einen
breiteren Bereich von Gleichungstypen abdeckt.

## Zusammenfassung und Ausblick

Die beiden Beispiele dieses Abschnitts zeigen das vollständige Vorgehen beim
Lösen technischer ODEs: Aus der Physik folgt die ODE, aus der Struktur der ODE
folgt die Methode, und aus der Lösung folgt eine physikalisch interpretierbare
Aussage. Die Euler-Eytelwein-Gleichung $F' = \mu F$ liefert das
Exponentialgesetz des Riementriebs, die Torricellische Gleichung $\dot{h} =
-k\sqrt{h}$ die endliche Entleerungszeit eines Hydraulikbehälters. In beiden
Fällen war die Separation der Variablen aus Abschnitt 7.1 das entscheidende
Werkzeug.

In Kapitel 8 erweitern wir den Lösungsbereich auf lineare ODEs 1. Ordnung der
Form $y' + p(x)\,y = q(x)$. Diese Gleichungen sind nicht mehr notwendigerweise
separierbar, erlauben aber eine systematische Lösungstheorie, die in der
Regelungstechnik und der Strukturmechanik allgegenwärtig ist.
