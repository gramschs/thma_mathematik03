# Lineare Gleichungssysteme mit Matrizenrechnung lösen

In diesem Kapitel lernen wir, wie lineare Gleichungssysteme durch die Anwendung
von Matrizen und deren Inversen gelöst werden können.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie verstehen, wie lineare Gleichungssysteme mit Hilfe von Matrizen
  dargestellt werden können.
* Sie können eine inverse Matrix dazu benutzen, ein lineares Gleichungssystem zu
  lösen.
* Sie können den **Gauß-Algorithmus in Matrix-Darstellung** zur Lösung von
  linearen Gleichungssystemen anwenden.
```

## Matrixdarstellung eines linearen Gleichungssystems

Ein lineares Gleichungssystem kann kompakt in Matrixform dargestellt werden.
Betrachten wir ein allgemeines lineares Gleichungssystem mit $n$ Gleichungen und
$n$ Unbekannten:

\begin{align*}
a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n &= b_1 \\
a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n &= b_2 \\
\vdots \\
a_{n1}x_1 + a_{n2}x_2 + \dots + a_{nn}x_n &= b_n.
\end{align*}

Dies lässt sich in kompakter Matrixschreibweise darstellen als:

\begin{equation*}
\mathbf{A} \vec{x} = \vec{b},
\end{equation*}

wobei $\mathbf{A} \in \mathbb{R}^{n \times n}$ die **Koeffizientenmatrix**
  
\begin{equation*}
\mathbf{A} = \begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \dots & a_{nn}
\end{pmatrix}
\end{equation*}

ist und $\vec{x} \in \mathbb{R}^n$ der **Vektor der Unbekannten** mit

\begin{equation*}
\vec{x} = \begin{pmatrix}
x_1 \\
x_2 \\
\vdots \\
x_n
\end{pmatrix}.
\end{equation*}

Die rechte Seite des linearen Gleichungssystems wird im **Ergebnisvektor**
$\vec{b} \in \mathbb{R}^n $ zusammengefasst:

\begin{equation*}
\vec{b} = \begin{pmatrix}
b_1 \\
b_2 \\
\vdots \\
b_n
\end{pmatrix}.
\end{equation*}

Betrachten wir das folgende lineare Gleichungssystem:

\begin{equation*}
\begin{align*}
3x_1 - 4x_2 - 4x_3 &= -4  \\
6x_1 - 6x_2 - 7x_3 &= -11 \\
-3x_1 + 6x_2 + 7x_3 &= 11 \\
\end{align*}
\end{equation*}

Dieses Gleichungssystem können wir in Matrixform darstellen. Die
Koeffizientenmatrix $\mathbf{A}$ ist:

\begin{equation*}
\mathbf{A} = \begin{pmatrix}
3 & -4 & -4 \\
6 & -6 & -7 \\
-3 & 6 & 7
\end{pmatrix}.
\end{equation*}

Der Vektor der Unbekannten $\vec{x}$ ist:

\begin{equation*}
\vec{x} = \begin{pmatrix}
x_1 \\
x_2 \\
x_3
\end{pmatrix}
\end{equation*}

und der Ergebnisvektor $\vec{b}$ ist:

\begin{equation*}
\vec{b} = \begin{pmatrix}
-4 \\
-11 \\
11
\end{pmatrix}.
\end{equation*}

Das gesamte lineare Gleichungssystem lässt sich nun in Matrixform schreiben als
$\mathbf{A} \vec{x} = \vec{b}$, also

\begin{equation*}
\begin{pmatrix}
3 & -4 & -4 \\
6 & -6 & -7 \\
-3 & 6 & 7
\end{pmatrix}
\begin{pmatrix}
x_1 \\
x_2 \\
x_3
\end{pmatrix}
= \begin{pmatrix}
-4 \\
-11 \\
11
\end{pmatrix}.
\end{equation*}

## Lösung des linearen Gleichungssystems mit Hilfe der inversen Matrix

Um das zuvor dargestellte lineare Gleichungssystem zu lösen, können wir die
Inverse der Koeffizientenmatrix $ \mathbf{A}$ berechnen, sofern
$\det(\mathbf{A})\neq 0$ ist. Die Lösung eines linearen Gleichungssystems der
Form

\begin{equation*}
\mathbf{A} \vec{x} = \vec{b}
\end{equation*}

kann dann durch die folgende Gleichung bestimmt werden:

\begin{equation*}
\vec{x} = \mathbf{A}^{-1} \vec{b}.
\end{equation*}

Diese Rechnung führen wir nun für das Beispiel aus.

Zuerst überprüfen wir, ob die Matrix $\mathbf{A}$ eine Inverse besitzt, indem
wir ihre Determinante berechnen. Die Determinante von $\mathbf{A}$ berechnet
sich wie folgt:

\begin{equation*}
\det(\mathbf{A}) = 3 \cdot \det\begin{pmatrix} -6 & -7 \\ 6 & 7 \end{pmatrix} - (-4) \cdot
\det\begin{pmatrix} 6 & -7 \\ -3 & 7 \end{pmatrix} - 4 \cdot
\det\begin{pmatrix} 6 & -6 \\ -3 & 6 \end{pmatrix}.
\end{equation*}

Dies ergibt:

\begin{equation*}
\det(\mathbf{A}) = 3 \cdot (-42 + 42) + 4 \cdot (42 - 21) - 4 \cdot (36 - 18)
= 12.
\end{equation*}

Da $\det(\mathbf{A}) \neq 0$ gilt, hat die Koeffizientenmatrix eine Inverse. Wir
rechnen die inverse Matrix $\mathbf{A}^{-1}$ mit dem Gauß-Algorithmus aus und
erhalten

\begin{equation*}
\mathbf{A}^{-1} = \frac{1}{12}\cdot
\begin{pmatrix}
0 & 4 & 4 \\
-21 & 9 & -3 \\
18 & -6 & 6 \\
\end{pmatrix}.
\end{equation*}

Die gesuchte Lösung des linearen Gleichungssystems erhalten wir nun, indem wir
die Inverse mit dem Ergebnisvektor multiplizieren:

\begin{equation*}
\vec{x}=\mathbf{A}^{-1}\cdot\vec{b}=
\frac{1}{12}\cdot
\begin{pmatrix}
0 & 4 & 4 \\
-21 & 9 & -3 \\
18 & -6 & 6 \\
\end{pmatrix} \cdot
\begin{pmatrix}
-4 \\
-11 \\
11
\end{pmatrix} =
\begin{pmatrix}
0 \\ -4 \\ 5
\end{pmatrix}.
\end{equation*}

Die gesuchte Lösung ist also $x_1 = 0$, $x_2 = -4$ und $x_3 = 5$.

Haben wir einmal die inverse Marix bestimmt, können wir sie immer wieder
benutzen. Sollte nun ein anderes Gleichungssystem gelöst werden, bei dem die
Koeffizientenmatrix gleich bleibt, sich aber der Ergebnisvektor ändert, brauchen
wir nur die Inverse mit dem neuen Ergebnisvektor zu multiplizieren.

Sollten wir sicher sein, dass wir nur für einen einzigen Ergebnisvektor das
lineare Gleichungssystem lösen wollen, können wir den Gauß-Algorithmus auch
direkt mit der Koeffizientenmatrix und dem Ergebnisvektor durchführen. Diese
Kurzschreibweise nennt man **erweiterte Koeffizientenmatrix**. Sie wird in dem
folgenden Video vorgestellt.

```{dropdown} Video "Lineare Gleichungssysteme (LGS) lösen - Gauß Verfahren" von MathePeter
<iframe width="560" height="315" src="https://www.youtube.com/embed/ac8r-E5h9FI?si=kStQbW4DMKyP7odg"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir eine alternative Darstellung kennengelernt, lineare
Gleichungssysteme mit Matrizen zu lösen. Insbesondere Computerprogramme und
Verfahren der Künstlichen Intelligenz nutzen diese kompakte und effiziente Art
und Weise, Informationen darzustellen und zu verarbeiten. Im nächsten Kapitel
werden wir Eigenschaften von Matrizen lernen, die zur Beschreibung von
schwingenden Systemen essentiell sind.
