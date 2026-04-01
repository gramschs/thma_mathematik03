# Eigenwerte und Eigenvektoren: Motivation und Definition

Bisher haben wir Matrizen als Werkzeuge für lineare Gleichungssysteme und als
Beschreibung von Drehungen und Transformationen kennengelernt. Jetzt stellen
wir eine ganz andere Frage: *Gibt es Richtungen im Raum, die durch eine
Matrixtransformation nicht verbogen, sondern nur gestreckt oder gestaucht
werden?* Diese Frage führt uns direkt zum Begriff der Eigenwerte und
Eigenvektoren, der zu den bedeutsamsten Konzepten der gesamten linearen
Algebra gehört.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie verstehen, was ein **Eigenvektor** und ein **Eigenwert** einer
  quadratischen Matrix sind, und können die definierende Gleichung
  \begin{equation*}
  \mathbf{A}\cdot\vec{v} = \lambda\cdot\vec{v}
  \end{equation*} 
  erläutern.
* [ ] Sie können geometrisch beschreiben, was es bedeutet, dass ein Vektor
  Eigenvektor einer Abbildung ist: Er wird durch die Abbildung nur gestreckt
  oder gestaucht, nicht gedreht.
* [ ] Sie wissen, dass der Nullvektor kein Eigenvektor ist.
* [ ] Sie kennen mindestens zwei maschinenbauliche Anwendungen von Eigenwerten,
  etwa **Hauptspannungen** in der Festigkeitslehre und **Eigenfrequenzen** in
  der Schwingungsanalyse.
```

## Wo begegnen uns Eigenwerte im Maschinenbau?

In der Festigkeitslehre wird der Spannungszustand an einem Punkt eines Bauteils
durch den Spannungstensor beschrieben, eine symmetrische $3\times 3$-Matrix.
Die Frage, welche Schnittflächen an diesem Punkt keine Schubspannungen erfahren
und nur durch Normalspannungen belastet sind, führt auf ein Eigenwertproblem.
Die Eigenwerte des Spannungstensors sind die **Hauptspannungen**, und die
Eigenvektoren zeigen in die **Hauptspannungsrichtungen**. Diese Größen sind für
die Auslegung von Bauteilen unter Betriebslast unverzichtbar.

Ein zweites, sehr vertrautes Beispiel aus dem Maschinenbau sind schwingungsfähige
Systeme. Ein einfacher Zweimassenschwinger besteht aus zwei Massen, die über
Federn miteinander und mit einem Rahmen verbunden sind. Die Differentialgleichungen
der Bewegung lassen sich in Matrizenform schreiben. Die Frequenzen, bei denen
das System resonant schwingt, die **Eigenfrequenzen**, sind direkt mit den
Eigenwerten der Systemmatrix verknüpft. Wir werden diesen Zusammenhang im
weiteren Verlauf des Kurses noch vertiefen.

## Was ist ein Eigenvektor?

Wir betrachten eine konkrete Situation. Gegeben sei die Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 6 & 2 \\ 2 & 3 \end{pmatrix}.
\end{equation*}

Wir multiplizieren verschiedene Vektoren mit $\mathbf{A}$ und beobachten,
was geschieht. Für den Vektor $\vec{u} = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$
ergibt sich:

\begin{equation*}
\mathbf{A}\cdot\vec{u} = \begin{pmatrix} 6 \\ 2 \end{pmatrix}.
\end{equation*}

Der Vektor zeigt nach der Transformation in eine andere Richtung. Versuchen
wir es mit $\vec{v} = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$:

\begin{equation*}
\mathbf{A}\cdot\vec{v} =
\begin{pmatrix} 6 & 2 \\ 2 & 3 \end{pmatrix}
\begin{pmatrix} 2 \\ 1 \end{pmatrix} =
\begin{pmatrix} 14 \\ 7 \end{pmatrix} = 7 \cdot \begin{pmatrix} 2 \\ 1 \end{pmatrix}
= 7\cdot\vec{v}.
\end{equation*}

Hier passiert etwas Besonderes: Das Ergebnis ist dasselbe wie $\vec{v}$,
lediglich mit dem Faktor $7$ gestreckt. Die Matrix hat die Richtung von $\vec{v}$
vollständig erhalten und ihn nur skaliert. Genau solche Vektoren nennen wir
Eigenvektoren.

```{admonition} Was sind ... Eigenwert und Eigenvektor?
:class: note
Ein Vektor $\vec{v} \neq \vec{0}$ heißt **Eigenvektor** der quadratischen
Matrix $\mathbf{A}$, wenn es eine reelle Zahl $\lambda$ gibt, sodass

\begin{equation*}
\mathbf{A}\cdot\vec{v} = \lambda\cdot\vec{v}
\end{equation*}

gilt. Die Zahl $\lambda$ heißt der zu $\vec{v}$ gehörende **Eigenwert**.

Der Nullvektor $\vec{0}$ ist ausdrücklich kein Eigenvektor, da
$\mathbf{A}\cdot\vec{0} = \vec{0} = \lambda\cdot\vec{0}$ für jedes $\lambda$
gilt und damit keine sinnvolle Aussage über eine Richtung liefert.
```

Wir haben bereits überprüft, dass $\vec{v} = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$
ein Eigenvektor von $\mathbf{A}$ zum Eigenwert $\lambda = 7$ ist. Jedes
skalare Vielfache $s\cdot\vec{v}$ mit $s \neq 0$ ist ebenfalls ein Eigenvektor
zum selben Eigenwert, denn:

\begin{equation*}
\mathbf{A}\cdot(s\vec{v}) = s\cdot(\mathbf{A}\vec{v}) = s\cdot 7\vec{v} = 7\cdot(s\vec{v}).
\end{equation*}

Es gibt also nicht den einen Eigenvektor zu einem Eigenwert, sondern eine ganze
Richtung im Raum. Alle Vielfachen von $\vec{v}$ bilden zusammen den
**Eigenraum** zum Eigenwert $\lambda = 7$.

## Was bedeutet ein negativer Eigenwert?

Ein Eigenwert $\lambda > 1$ entspricht einer Streckung in die Richtung des
Eigenvektors. Für $0 < \lambda < 1$ schrumpft der Vektor. Ist $\lambda < 0$,
kehrt sich die Richtung um, der Vektor wird gespiegelt und zusätzlich skaliert.
Für $\lambda = 0$ wäre $\mathbf{A}\vec{v} = \vec{0}$, was bedeutet, dass der
Eigenvektor auf den Nullvektor abgebildet wird. In diesem Fall ist die Matrix
nicht invertierbar, wie wir aus dem Kapitel über Determinanten wissen.

*Aber wie berechnet man Eigenwerte systematisch, ohne wie oben nach Vektoren
raten zu müssen?* Diese Frage führt auf das charakteristische Polynom, das wir
im nächsten Abschnitt kennenlernen.

## Eigenwerte und Eigenvektoren in der Festigkeitslehre

In der Technischen Mechanik beschreibt der ebene Spannungstensor den
Spannungszustand an einem Punkt eines dünnwandigen Bauteils:

\begin{equation*}
\boldsymbol{\sigma} =
\begin{pmatrix} \sigma_{xx} & \tau_{xy} \\ \tau_{xy} & \sigma_{yy} \end{pmatrix}.
\end{equation*}

Die Diagonalelemente sind Normalspannungen, die Nebendiagonalelemente sind
Schubspannungen. Die Eigenwerte dieser Matrix sind genau die Hauptspannungen
$\sigma_1$ und $\sigma_2$, auf die es für die Bewertung nach der Gestaltänderungs-
energiehypothese (von-Mises-Kriterium) ankommt. Die Eigenvektoren zeigen in die
Richtungen, in denen keine Schubspannungen auftreten. Diese Verbindung werden
Sie in der Technischen Mechanik II vertiefen.

```{dropdown} Video "Eigenwerte und Eigenvektoren - Einführung" von 3Blue1Brown (deutsch)
<iframe width="560" height="315" src="https://www.youtube.com/embed/PFDu9oVAE-g"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Ein Eigenvektor einer Matrix ist ein Vektor, dessen Richtung durch die
Matrixtransformation nicht geändert wird. Er wird nur gestreckt, gestaucht oder
gespiegelt, und der Streckungsfaktor ist der zugehörige Eigenwert. Der Nullvektor
ist ausdrücklich kein Eigenvektor.

Im nächsten Abschnitt lernen wir, wie wir die Eigenwerte einer Matrix
systematisch berechnen: über das charakteristische Polynom, das durch
$\det(\mathbf{A} - \lambda\mathbf{E}) = 0$ definiert ist. Die Kenntnis der
Determinante aus Kapitel 1 zahlt sich jetzt aus.
