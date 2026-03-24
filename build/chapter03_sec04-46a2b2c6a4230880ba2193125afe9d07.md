# Kern einer Matrix

Wir wissen nun, was eine lineare Abbildung ist und welche Eigenschaften sie erfüllt.
Als nächstes stellen wir die Frage: Welche Eingabevektoren werden durch eine gegebene
Abbildung auf den Nullvektor abgebildet? Die Antwort auf diese Frage führt zum Begriff
des Kerns einer Matrix. Im Maschinenbau taucht der Kern an überraschend vielen Stellen
auf: Er bestimmt, wie viele Freiheitsgrade ein Mechanismus hat, ob eine Struktur
statisch bestimmt ist, und ob ein lineares Gleichungssystem eindeutig lösbar ist.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie kennen die Definition des **Kerns** einer Matrix und können ihn geometrisch
  interpretieren.
* Sie können den Kern einer Matrix berechnen, indem Sie das homogene lineare
  Gleichungssystem $\mathbf{A} \cdot \vec{v} = \vec{0}$ lösen.
* Sie kennen die **Dimension des Kerns** und können diese aus den Lösungen des
  Gleichungssystems ablesen.
* Sie wissen, dass der Kern immer mindestens den Nullvektor enthält, und können
  beurteilen, ob der Kern nur den Nullvektor enthält oder weitere Vektoren umfasst.
```

## Motivation: Welche Vektoren verschwinden?

Wir betrachten die Projektion auf die $xy$-Ebene, die wir im vorigen Kapitel bereits
kennengelernt haben:

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}.
\end{equation*}

Diese Matrix modelliert beispielsweise eine industrielle Kamera, die ein
dreidimensionales Objekt auf eine zweidimensionale Ebene projiziert. Dabei gehen
alle Informationen über die Tiefe ($z$-Koordinate) verloren. Welche Vektoren
$\vec{v} = \begin{pmatrix} x \\ y \\ z \end{pmatrix}$ werden durch diese Abbildung
auf den Nullvektor abgebildet? Wir berechnen:

\begin{equation*}
\begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}
\cdot \begin{pmatrix} x \\ y \\ z \end{pmatrix}
= \begin{pmatrix} x \\ y \\ 0 \end{pmatrix}
= \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}.
\end{equation*}

Das liefert die Bedingungen $x = 0$ und $y = 0$, während $z$ beliebig sein kann.
Die Menge aller Vektoren, die auf $\vec{0}$ abgebildet werden, ist also die
$z$-Achse:

\begin{equation*}
\left\{ \begin{pmatrix} 0 \\ 0 \\ z \end{pmatrix} \,\middle|\, z \in \mathbb{R} \right\}
= t \cdot \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}.
\end{equation*}

Geometrisch bedeutet das: Alle Punkte, die direkt senkrecht über dem Ursprung
der $xy$-Ebene liegen, werden auf den Ursprung projiziert. Die Information über ihre
Höhe geht bei der Projektion vollständig verloren. Diese Menge heißt der
**Kern** der Matrix.

## Definition des Kerns

```{admonition} Was ist ... der Kern einer Matrix?
:class: note
Sei $F_{\mathbf{A}}: \mathbb{R}^n \to \mathbb{R}^m$ eine lineare Abbildung mit der
Matrix $\mathbf{A} \in \mathbb{R}^{m \times n}$. Der **Kern** von $\mathbf{A}$,
geschrieben $\text{Kern}(\mathbf{A})$, ist die Menge aller Vektoren
$\vec{v} \in \mathbb{R}^n$, die durch die Abbildung auf den Nullvektor abgebildet
werden:

\begin{equation*}
\text{Kern}(\mathbf{A}) = \{ \vec{v} \in \mathbb{R}^n \mid \mathbf{A} \cdot \vec{v} = \vec{0} \}.
\end{equation*}

Der Kern enthält immer mindestens den Nullvektor, da $\mathbf{A} \cdot \vec{0} =
\vec{0}$ für jede Matrix gilt.
```

Die Dimension des Kerns, also die Anzahl der linear unabhängigen Vektoren im Kern,
wird **Defekt** der Matrix genannt und mit $\dim(\text{Kern}(\mathbf{A}))$
bezeichnet.

## Berechnung des Kerns

Der Kern wird berechnet, indem man das **homogene lineare Gleichungssystem**

\begin{equation*}
\mathbf{A} \cdot \vec{v} = \vec{0}
\end{equation*}

löst. Dieses System hat immer mindestens die triviale Lösung $\vec{v} = \vec{0}$.
Wenn es weitere Lösungen gibt, bilden diese zusammen mit dem Nullvektor den Kern.

**Beispiel 1:** Wir berechnen den Kern der Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}.
\end{equation*}

Das homogene Gleichungssystem lautet:

\begin{equation*}
\begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
\cdot \begin{pmatrix} v_1 \\ v_2 \end{pmatrix}
= \begin{pmatrix} v_1 \\ -v_2 \end{pmatrix}
= \begin{pmatrix} 0 \\ 0 \end{pmatrix}.
\end{equation*}

Daraus folgt $v_1 = 0$ und $v_2 = 0$. Der Kern enthält nur den Nullvektor:

\begin{equation*}
\text{Kern}(\mathbf{A}) = \left\{ \begin{pmatrix} 0 \\ 0 \end{pmatrix} \right\}, \quad
\dim(\text{Kern}(\mathbf{A})) = 0.
\end{equation*}

Ein Kern, der nur den Nullvektor enthält, bedeutet, dass die Abbildung injektiv ist:
Verschiedene Eingabevektoren werden auf verschiedene Ausgabevektoren abgebildet. In
der Strukturmechanik entspricht das einer statisch bestimmten Lagerung: Die
Steifigkeitsmatrix hat einen trivialen Kern, das System hat eine eindeutige Lösung.

**Beispiel 2:** Wir berechnen den Kern der Matrix

\begin{equation*}
\mathbf{C} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}.
\end{equation*}

Das homogene Gleichungssystem lautet:

\begin{equation*}
\begin{pmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}
\cdot \begin{pmatrix} v_1 \\ v_2 \\ v_3 \end{pmatrix}
= \begin{pmatrix} v_1 \\ 0 \\ v_3 \end{pmatrix}
= \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}.
\end{equation*}

Aus der ersten und dritten Gleichung folgt $v_1 = 0$ und $v_3 = 0$. Die zweite
Gleichung ist immer erfüllt, unabhängig von $v_2$. Daher kann $v_2$ beliebig gewählt
werden:

\begin{equation*}
\text{Kern}(\mathbf{C}) = \left\{ t \cdot \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}
\;\middle|\; t \in \mathbb{R} \right\}, \quad \dim(\text{Kern}(\mathbf{C})) = 1.
\end{equation*}

Das ist geometrisch die $y$-Achse. In einem FEM-Modell ohne ausreichende Lagerung
entsprechen solche nichtrivalen Kern-Vektoren **Starrkörpermoden**: Bewegungen des
gesamten Netzes, die keine Verformungsenergie erzeugen. Bevor ein FEM-Solver rechnen
kann, müssen alle Starrkörpermoden durch Randbedingungen unterdrückt werden, also der
Kern der Steifigkeitsmatrix auf den Nullvektor reduziert werden.

**Beispiel 3:** Wir berechnen den Kern der Matrix

\begin{equation*}
\mathbf{D} = \begin{pmatrix} 1 & 2 & 2 \\ 1 & -1 & 2 \\ 0 & 0 & 0 \\ 0 & 1 & 0 \end{pmatrix}.
\end{equation*}

Das homogene Gleichungssystem $\mathbf{D} \cdot \vec{v} = \vec{0}$ lautet:

\begin{align*}
v_1 + 2v_2 + 2v_3 &= 0 \\
v_1 - v_2 + 2v_3  &= 0 \\
0                   &= 0 \\
v_2                 &= 0.
\end{align*}

Aus der vierten Gleichung folgt direkt $v_2 = 0$. Einsetzen in die erste Gleichung
liefert $v_1 + 2v_3 = 0$, also $v_1 = -2v_3$. Die Variable $v_3$ kann beliebig
gewählt werden. Wir setzen $v_3 = t$ mit $t \in \mathbb{R}$ und erhalten:

\begin{equation*}
\vec{v} = \begin{pmatrix} -2t \\ 0 \\ t \end{pmatrix}
= t \cdot \begin{pmatrix} -2 \\ 0 \\ 1 \end{pmatrix}, \quad t \in \mathbb{R}.
\end{equation*}

Der Kern ist:

\begin{equation*}
\text{Kern}(\mathbf{D}) = \left\{ t \cdot \begin{pmatrix} -2 \\ 0 \\ 1 \end{pmatrix}
\;\middle|\; t \in \mathbb{R} \right\}, \quad \dim(\text{Kern}(\mathbf{D})) = 1.
\end{equation*}

## Geometrische Bedeutung und Anwendungen

Der Kern einer Matrix lässt sich geometrisch als derjenige Teil des Eingaberaums
interpretieren, der durch die Abbildung auf den Ursprung kollabiert. Alle Vektoren im
Kern werden auf den Nullvektor abgebildet, sie gehen bei der Transformation vollständig
verloren.

Im Maschinenbau hat der Kern folgende Bedeutungen:

**Kinematik von Mechanismen:** Die Bewegungsmöglichkeiten eines Gelenkmechanismus
entsprechen dem Kern der sogenannten Jacobi-Matrix des Mechanismus. Ein
eindimensionaler Kern bedeutet genau einen kinematischen Freiheitsgrad, was bei
einem Scharniergelenk der Fall ist. Ein mehrdimensionaler Kern entspricht mehreren
unabhängigen Bewegungsmöglichkeiten.

**Statische Bestimmtheit:** Bei der Analyse von Fachwerken und Rahmenkonstruktionen
wird untersucht, ob die Gleichgewichtsbedingungen eine eindeutige Lösung für die
Stabkräfte liefern. Eine eindeutige Lösung existiert genau dann, wenn der Kern der
Gleichgewichtsmatrix trivial ist. Ist der Kern nichttrivial, so ist die Struktur
statisch unbestimmt oder kinematisch beweglich.

**FEM und Starrkörpermoden:** Wie oben beschrieben, entsprechen die Vektoren im Kern
der Steifigkeitsmatrix den Starrkörpermoden des nicht gelagerten Systems. Diese müssen
vor der Berechnung durch Randbedingungen beseitigt werden.

```{dropdown} Video "Kern einer Matrix" von MathePeter
<iframe width="560" height="315" src="https://www.youtube.com/embed/uQhTuRlWMxw"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Der Kern einer Matrix $\mathbf{A}$ ist die Menge aller Vektoren $\vec{v}$, für die
$\mathbf{A} \cdot \vec{v} = \vec{0}$ gilt. Er wird durch Lösung des homogenen
linearen Gleichungssystems berechnet und enthält immer mindestens den Nullvektor. Im
Maschinenbau beschreibt der Kern Freiheitsgrade von Mechanismen, Starrkörpermoden in
der FEM und die statische Bestimmtheit von Tragwerken. Im nächsten Kapitel lernen wir
das komplementäre Konzept kennen: das Bild einer Matrix, das beschreibt, welche
Vektoren überhaupt als Ergebnis der Abbildung auftreten können.
