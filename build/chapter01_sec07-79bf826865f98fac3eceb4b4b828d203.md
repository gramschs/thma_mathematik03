# Inverse Matrizen

Bisher haben wir die Addition, Subtraktion und Multiplikation von Matrizen
kennengelernt. Gibt es eine Division? Ein Division wie wir sie von den reellen
Zahlen kennen, gibt es nicht. Aber für quadratische Matrizen können wir manchmal
die sogenannte inverse Matrix bilden. Die inverse Matrix ist vergleichbar mit
dem Kehrwert einer Zahl und hat wichtige Anwendungen.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie wissen, was die **inverse Matrix** einer quadratischen
  Matrix ist und wann es erlaubt ist, sie zu berechnen.
* Sie kennen den Fachbegriff **invertierbar**.
* Sie können die **Inverse einer $2\times 2$-Matrix** berechnen.
* Sie können die **Inverse einer Diagonalmatrix** angeben und berechnen.
* Sie können die **Inverse einer $n\times n$-Matrix** für $n>2$ berechnen.
```

## Inverse Matrix von $2\times 2$-Matrizen

Anhand der Überschrift können Sie schon erahnen, dass der Fachbegriff **inverse
Matrix** nur für quadratische Matrizen definiert ist. Wir beginnen mit der
Inversen einer $2 \times 2$-Matrix, also allgemein einer Matrix der Form

\begin{equation*}
\mathbf{A} = \begin{pmatrix} a & b \\ c & d \end{pmatrix}.
\end{equation*}

Wenn der Ausdruck $a\cdot d - c\cdot b$ *ungleich Null* ist, also

\begin{equation*}
a\cdot d - c\cdot b \textcolor{red}{\neq} 0
\end{equation*}

gilt, dann können wir die Inverse $\mathbf{A}^{-1}$ mit der Definition

\begin{equation*}
\mathbf{A}^{-1}=
\frac{1}{a\cdot d - c\cdot b} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
\end{equation*}

bilden. Jetzt ist auch ersichtlich, warum wir $a\cdot d - c\cdot b \neq 0$
gefordert haben, denn das Teilen durch Null ist strikt verboten. Wir werden
später lernen, dass dieser Ausdruck Determinante genannt wird.

Betrachten wir als Beispiel die Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}.
\end{equation*}

Wir testen, ob die Matrix invertierbar ist:

\begin{equation*}
a\cdot d - c\cdot b = 2 \cdot 5 - 1 \cdot 3 = 10 - 3 = 7 \neq 0.
\end{equation*}

Da dieser Ausdruck ungleich null ist, können wir die Inverse der Matrix
berechnen. Wir setzen die Werte in die allgemeine Formel ein:

\begin{equation*}
\mathbf{A}^{-1} = \frac{1}{7} \begin{pmatrix} 5 & -3 \\ -1 & 2 \end{pmatrix}.
\end{equation*}

Das ergibt die Inverse:

\begin{equation*}
\mathbf{A}^{-1} =
\begin{pmatrix} \frac{5}{7} & \frac{-3}{7} \\ \frac{-1}{7} & \frac{2}{7} \end{pmatrix}.
\end{equation*}

Warum ist die Inverse so interessant? Wir berechnen das Matrizenprodukt
$\mathbf{A}\cdot\mathbf{A}^{-1}$:

\begin{equation*}
\begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix} \cdot
\frac{1}{7} \begin{pmatrix} 5 & -3 \\ -1 & 2 \end{pmatrix} =
\begin{pmatrix} 1 & 0 \\ 0 & 1 \\ \end{pmatrix}.
\end{equation*}

Das Ergebnis ist die Einheitsmatrix der Dimension $2\times 2$. Tatsächlich ist
das auch die Definition der inversen Matrix.

```{admonition} Was ist ... die inverse Matrix?
:class: note
Die inverse Matrix $\mathbf{A}^{-1}$ einer quadratischen Matrix $\mathbf{A}$ ist
ebenfalls eine quadratische Matrix, die die Einheitsmatrix $\mathbf{E}$ ergibt,
wenn sie mit der ursprünglichen Matrix $\mathbf{A}$ multipliziert wird:

\begin{equation*}
\mathbf{A}^{-1}\cdot \mathbf{A} = \mathbf{E}.
\end{equation*}

Eine Matrix, die eine inverse Matrix besitzt, wird **invertierbar** genannt.
```

## Inverse von Diagonalmatrizen

Wenn eine quadratische Matrix eine Inverse besitzt, ist diese inverse Matrix
eindeutig. Im Fall von $2\times 2$-Matrizen lässt sich die Inverse mit der
obigen Formel sehr einfach angeben. Auch im Fall von Diagonalmatrizen gibt es
eine einfache Rechenvorschrift, um die inverse Matrix zu bestimmen. Wir
betrachten das Beispiel

\begin{equation*}
\mathbf{D} = \begin{pmatrix}
2 & 0 & 0\\
0 & \frac{1}{3} & 0 \\
0 & 0 & 4\\ \end{pmatrix}.
\end{equation*}

Wir raten die inverse Matrix

\begin{equation*}
\mathbf{D}^{-1} = \begin{pmatrix}
\frac{1}{2} & 0 & 0\\
0 & 3 & 0 \\
0 & 0 & \frac{1}{4}\\ \end{pmatrix}
\end{equation*}

und überprüfen durch Matrixmultiplikation, ob unsere Vermutung stimmt und die
Einheitsmatrix $E$ das Ergebnis der Multiplikation ist:

\begin{equation*}
\mathbf{D}\cdot \mathbf{D}^{-1} =
\begin{pmatrix}
2 & 0 & 0\\
0 & \frac{1}{3} & 0\\
0 & 0 & 4\\ \end{pmatrix} \cdot
\begin{pmatrix}
\frac{1}{2} & 0 & 0\\
0 & 3 & 0\\
0 & 0 & \frac{1}{4}\\ \end{pmatrix} =
\begin{pmatrix}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1\\ \end{pmatrix} = \mathbf{E}.
\end{equation*}

In der Tat stimmt unser Verdacht, wir mussten nur entlang der Hauptdiagonale die
Kehrwerte der Elemente bilden und konnten so die inverse Matrix einfach
bestimmen. Diese Rechenvorschrift gilt allgemein für Diagonalmatrizen. Ist eine
Diagonalmatrix in der allgemeinen Form

\begin{equation*}
\mathbf{D} =
\begin{pmatrix}
d_{11} & 0 & \ldots & 0\\
0 & d_{22} & \ldots & 0\\
\vdots & \vdots & \ddots & \vdots\\
0 & 0 & \ldots & d_{nn}\\
\end{pmatrix}
\end{equation*}

gegeben, dann ist ihre inverse Matrix

\begin{equation*}
\mathbf{D}^{-1} =
\begin{pmatrix}
\frac{1}{d_{11}} & 0 & \ldots & 0\\
0 & \frac{1}{d_{22}} & \ldots & 0\\
\vdots & \vdots & \ddots & \vdots\\
0 & 0 & \ldots & \frac{1}{d_{nn}}\\
\end{pmatrix}
\end{equation*}

Die inverse Matrix einer $2\times 2$-Matrix und einer Diagonalmatrix lässt sich
sehr leicht bestimmen. Komplizierter wird es, wenn die Matrix keine
Diagonalmatrix ist und vor allem, wenn sie mehr als zwei Zeilen/Spalten hat.

## Inverse Matrix von $n \times n$-Matrizen

Die obige Definition einer inversen Matrix ist für alle quadratischen Matrizen
gültig. Auch bei einer quadratischen $n\times n$-Matrix $\mathbf{A}$ ist also
die inverse Matrix $\mathbf{A}^{-1}$ diejenige Matrix, für die dann
$\mathbf{A}^{-1}\cdot\mathbf{A}=\mathbf{E}$ gilt. Leider gibt es keine so schöne
einfache Formel zur Berechnung der Inversen. Auch gibt es keinen einfachen Test,
ob die Inverse überhaupt existiert. Die Berechnung der Inversen einer $n \times
n$-Matrix ist aufwändiger als bei $2 \times 2$-Matrizen und erfordert in der
Regel eine systematische Methode. Eines der bekanntesten Verfahren ist der
Gauß-Algorithmus, den wir auch schon zur Lösung eines linearen Gleichungssystems
kennengelernt haben.

Das Gauß-Verfahren funktioniert durch das Anwenden von elementaren
Zeilenumformungen auf die Matrix $\mathbf{A}$, bis sie in die Einheitsmatrix
$\mathbf{E}$ umgewandelt ist. Dieselben Umformungen werden parallel auf eine
Einheitsmatrix der gleichen Dimension angewendet, um schließlich die Inverse zu
erhalten. Der Algorithmus verläuft in den folgenden Schritten:

1. Gegeben ist eine Matrix $\mathbf{A} \in \mathbb{R}^{n \times n}$.
2. Füge rechts neben $\mathbf{A}$ die Einheitsmatrix $\mathbf{E}$ dazu.
3. Wende elementare Zeilenumformungen an, um $\mathbf{A}$ in die Einheitsmatrix
   $\mathbf{E}$ zu überführen.
4. Führe die gleichen Zeilenumformungen mit der Einheitsmatrix $\mathbf{E}$
   rechts daneben durch.
5. Ist die ursprüngliche Matrix $\mathbf{A}$ in die Einheitsmatrix umgeformt,
   dann ist die ursprüngliche Einheitsmatrix rechts daneben nun die gesuchte
   inverse Matrix.

Am einfachsten ist es, sich den Gauß-Algorithmus im folgenden Video anzusehen.

```{dropdown} Video "INVERSE MATRIX 3x3 berechnen" von Mathematrick
<iframe width="560" height="315" src="https://www.youtube.com/embed/usya1zz-skM?si=TfW-HC43dbkEjoog"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben Sie gelernt, was die Inverse einer Matrix ist, wann sie
überhaupt existiert und wie sie für $2\times 2$-Matrizen, Diagonalmatrizen und
beliebige $n\times n$-Matrizen berechnet wird. Im nächsten Kapitel werden wir
Rechenregeln für inverse Matrizen lernen.
