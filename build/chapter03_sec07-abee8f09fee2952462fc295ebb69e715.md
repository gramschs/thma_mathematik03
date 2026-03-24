# Basiswechsel

Bisher haben wir Vektoren stets in kartesischen Koordinaten beschrieben, also
bezüglich der Standardbasis mit den Einheitsvektoren $\vec{e}_1$, $\vec{e}_2$ und
$\vec{e}_3$. In der Praxis ist das jedoch nicht immer die sinnvollste Wahl. Ein
Konstrukteur beschreibt ein Bauteil im körperfesten Koordinatensystem, das mit dem
Bauteil dreht und verschoben wird. Ein Schwingungsanalytiker wählt die
Eigenschwingungsformen als Basis, weil sich in dieser Basis die Bewegungsgleichungen
besonders einfach darstellen. In diesem Kapitel lernen wir, wie man denselben Vektor
in verschiedenen Basen darstellt und wie man zwischen Basen wechselt.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie wissen, was eine **Basis** des $\mathbb{R}^n$ ist, und kennen die
  **kanonische Basis**.
* Sie können einen Vektor $\vec{a} \in \mathbb{R}^n$ als **Linearkombination**
  von Basisvektoren darstellen.
* Sie kennen den **Koordinatenvektor** $_{V}\vec{a}$ eines Vektors $\vec{a}$
  bezüglich einer Basis $V$ und können ihn berechnen.
* Sie können einen **Basiswechsel** durchführen, indem Sie das lineare
  Gleichungssystem $V \cdot {}_{V}\vec{a} = \vec{a}$ lösen.
```

## Wiederholung: Lineare Unabhängigkeit und Basis

Bevor wir den Basiswechsel einführen, erinnern wir uns an die notwendigen
Grundbegriffe.

Vektoren $\vec{v}_1, \ldots, \vec{v}_m \in \mathbb{R}^n$ heißen **linear
unabhängig**, wenn die Vektorgleichung

\begin{equation*}
\lambda_1 \vec{v}_1 + \lambda_2 \vec{v}_2 + \cdots + \lambda_m \vec{v}_m = \vec{0}
\end{equation*}

nur für $\lambda_1 = \lambda_2 = \cdots = \lambda_m = 0$ erfüllt wird. Kein Vektor
lässt sich dann als Linearkombination der anderen darstellen.

Eine Menge von $n$ linear unabhängigen Vektoren $V = (\vec{v}_1, \ldots, \vec{v}_n)$
im $\mathbb{R}^n$ heißt **Basis** des $\mathbb{R}^n$. Eine Basis ermöglicht es,
jeden Vektor $\vec{a} \in \mathbb{R}^n$ als eindeutige Linearkombination der
Basisvektoren darzustellen.

Der Zusammenhang zwischen linearer Unabhängigkeit und Determinante ist dabei
besonders nützlich: Fasst man die Basisvektoren als Spalten einer quadratischen
Matrix $V = (\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n)$ zusammen, so gilt:

\begin{equation*}
\det(V) \neq 0 \quad \Longleftrightarrow \quad \vec{v}_1, \ldots, \vec{v}_n \text{ sind linear unabhängig}.
\end{equation*}

## Die kanonische Basis

Die einfachste und am häufigsten verwendete Basis ist die **kanonische Basis** (auch
Standardbasis genannt). Im $\mathbb{R}^2$ besteht sie aus den beiden Einheitsvektoren

\begin{equation*}
\vec{e}_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, \quad
\vec{e}_2 = \begin{pmatrix} 0 \\ 1 \end{pmatrix},
\end{equation*}

und im $\mathbb{R}^3$ aus den drei Einheitsvektoren

\begin{equation*}
\vec{e}_1 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}, \quad
\vec{e}_2 = \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}, \quad
\vec{e}_3 = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}.
\end{equation*}

Bezüglich der kanonischen Basis sind die Koordinaten eines Vektors $\vec{a}$ gerade
seine Einträge selbst:

\begin{equation*}
\vec{a} = \begin{pmatrix} a_1 \\ a_2 \\ a_3 \end{pmatrix}
= a_1 \cdot \vec{e}_1 + a_2 \cdot \vec{e}_2 + a_3 \cdot \vec{e}_3.
\end{equation*}

## Koordinatenvektoren bezüglich einer neuen Basis

Nun betrachten wir eine andere Basis $V = (\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n)$.
Jeder Vektor $\vec{a} \in \mathbb{R}^n$ lässt sich eindeutig als Linearkombination
der Basisvektoren schreiben:

\begin{equation*}
\vec{a} = \lambda_1 \vec{v}_1 + \lambda_2 \vec{v}_2 + \cdots + \lambda_n \vec{v}_n.
\end{equation*}

Die Koeffizienten $\lambda_1, \lambda_2, \ldots, \lambda_n$ dieser Linearkombination
heißen die **Koordinaten** von $\vec{a}$ bezüglich der Basis $V$. Sie werden im
**Koordinatenvektor** zusammengefasst:

\begin{equation*}
{}_V\vec{a} = \begin{pmatrix} \lambda_1 \\ \lambda_2 \\ \vdots \\ \lambda_n \end{pmatrix}.
\end{equation*}

Der gleiche geometrische Vektor $\vec{a}$ wird also durch verschiedene Zahlentupel
beschrieben, je nachdem welche Basis verwendet wird.

## Basiswechsel als lineares Gleichungssystem

Die Berechnung des Koordinatenvektors ${}_V\vec{a}$ führt auf ein lineares
Gleichungssystem. Schreibt man die Gleichung

\begin{equation*}
\vec{a} = \lambda_1 \vec{v}_1 + \lambda_2 \vec{v}_2 + \cdots + \lambda_n \vec{v}_n
\end{equation*}

in Matrixform, indem man die Basisvektoren als Spalten der Matrix $V$ zusammenfasst,
erhält man:

\begin{equation*}
\vec{a} = V \cdot {}_V\vec{a}, \quad \text{mit } V = (\vec{v}_1, \vec{v}_2, \ldots, \vec{v}_n).
\end{equation*}

Da $V$ aus linear unabhängigen Vektoren besteht, ist $\det(V) \neq 0$ und die Matrix
ist invertierbar. Der Koordinatenvektor ergibt sich daher durch:

\begin{equation*}
{}_V\vec{a} = V^{-1} \cdot \vec{a}.
\end{equation*}

In der Praxis berechnet man ${}_V\vec{a}$ meist nicht über die explizite Inverse,
sondern durch Lösung des Gleichungssystems $V \cdot {}_V\vec{a} = \vec{a}$ mit dem
Gauß-Algorithmus.

## Vollständiges Beispiel

Wir berechnen die Koordinaten des Vektors $\vec{a} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$
bezüglich der Basis

\begin{equation*}
V = (\vec{v}_1, \vec{v}_2, \vec{v}_3)
\quad \text{mit} \quad
\vec{v}_1 = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}, \quad
\vec{v}_2 = \begin{pmatrix} 0 \\ 2 \\ -2 \end{pmatrix}, \quad
\vec{v}_3 = \begin{pmatrix} -1 \\ 0 \\ -2 \end{pmatrix}.
\end{equation*}

Zunächst überprüfen wir, ob die Vektoren tatsächlich eine Basis bilden. Die
Koeffizientenmatrix ist

\begin{equation*}
V = \begin{pmatrix} 1 & 0 & -1 \\ 1 & 2 & 0 \\ 0 & -2 & -2 \end{pmatrix},
\end{equation*}

und es gilt $\det(V) \neq 0$, also sind die drei Vektoren linear unabhängig und
bilden eine Basis des $\mathbb{R}^3$.

Wir suchen $\lambda_1, \lambda_2, \lambda_3$ mit $\vec{a} = \lambda_1 \vec{v}_1 +
\lambda_2 \vec{v}_2 + \lambda_3 \vec{v}_3$, also

\begin{equation*}
\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}
= \lambda_1 \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}
+ \lambda_2 \begin{pmatrix} 0 \\ 2 \\ -2 \end{pmatrix}
+ \lambda_3 \begin{pmatrix} -1 \\ 0 \\ -2 \end{pmatrix}.
\end{equation*}

Das entspricht dem Gleichungssystem $V \cdot {}_V\vec{a} = \vec{a}$. Mit dem
Gauß-Algorithmus erhält man die Lösung

\begin{equation*}
\lambda_1 = -3, \quad \lambda_2 = \frac{5}{2}, \quad \lambda_3 = -4,
\end{equation*}

und damit den Koordinatenvektor

\begin{equation*}
{}_V\vec{a} = \begin{pmatrix} -3 \\ \frac{5}{2} \\ -4 \end{pmatrix}.
\end{equation*}

Zur Probe setzen wir ein:
$(-3) \cdot \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}
+ \frac{5}{2} \cdot \begin{pmatrix} 0 \\ 2 \\ -2 \end{pmatrix}
+ (-4) \cdot \begin{pmatrix} -1 \\ 0 \\ -2 \end{pmatrix}
= \begin{pmatrix} -3+0+4 \\ -3+5+0 \\ 0-5+8 \end{pmatrix}
= \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$. Das Ergebnis stimmt.

## Bedeutung des Basiswechsels im Maschinenbau

Der Basiswechsel ist in der Ingenieurpraxis überall präsent. Einige Beispiele:

**Körperfestes Koordinatensystem:** Ein Roboterarm wird zunächst in einem weltfesten
Koordinatensystem beschrieben. Für die Steuerung ist es jedoch günstiger, die
Koordinaten im körperfesten System des Armgliedes anzugeben. Der Übergang zwischen
beiden Systemen ist ein Basiswechsel.

**Modalanalyse:** Bei der Schwingungsanalyse von Maschinen und Strukturen wählt man
die Eigenvektoren der Massenmatrix als neue Basis. In dieser Basis zerfällt das
gekoppelte Schwingungssystem in unabhängige Einzelschwingungen, die getrennt
analysiert werden können. Das entspricht genau der Diagonalisierung, die in einem
späteren Kapitel behandelt wird.

**Hauptspannungen:** Im Kapitel über Eigenwerte und Eigenvektoren werden wir sehen,
dass der Spannungstensor in der Basis der Eigenvektoren eine Diagonalgestalt annimmt.
Die Diagonalelemente sind die Hauptspannungen. Auch das ist ein Basiswechsel.

```{admonition} Was ist ... ein Basiswechsel?
:class: note
Gegeben sei ein Vektor $\vec{a} \in \mathbb{R}^n$ und eine Basis
$V = (\vec{v}_1, \ldots, \vec{v}_n)$ des $\mathbb{R}^n$.

Der **Koordinatenvektor** ${}_V\vec{a}$ enthält die Koeffizienten
$\lambda_1, \ldots, \lambda_n$ der eindeutigen Darstellung

\begin{equation*}
\vec{a} = \lambda_1 \vec{v}_1 + \cdots + \lambda_n \vec{v}_n = V \cdot {}_V\vec{a}.
\end{equation*}

Der **Basiswechsel** wird berechnet durch Lösung des linearen Gleichungssystems

\begin{equation*}
V \cdot {}_V\vec{a} = \vec{a},
\end{equation*}

wobei $V = (\vec{v}_1, \ldots, \vec{v}_n)$ die Matrix der Basisvektoren als
Spalten ist.
```

```{dropdown} Video "Basiswechsel" von MathePeter
<iframe width="560" height="315" src="https://www.youtube.com/embed/3g1kBHgUWAY"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Eine Basis des $\mathbb{R}^n$ ist eine Menge von $n$ linear unabhängigen Vektoren,
bezüglich derer jeder Vektor eindeutig als Linearkombination dargestellt werden kann.
Der Basiswechsel berechnet den Koordinatenvektor eines gegebenen Vektors bezüglich
einer neuen Basis durch Lösung des Gleichungssystems $V \cdot {}_V\vec{a} = \vec{a}$.
Im Maschinenbau tritt der Basiswechsel in vielen Kontexten auf: bei der
Koordinatentransformation in der Robotik, bei der Modalanalyse und bei der Berechnung
von Hauptspannungen. Mit dem Basiswechsel haben wir nun alle Werkzeuge beisammen,
um im nächsten Kapitel orthogonale Matrizen und Drehmatrizen zu studieren, die
geometrisch besonders schöne und technisch besonders wichtige Basiswechsel darstellen.
