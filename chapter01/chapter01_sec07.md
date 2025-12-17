# Inverse Matrizen

In dem vorangegangenen Kapitel haben wir die Determinante kennengelernt. Mit
Hilfe der Determinante können wir beispielsweise entscheiden, ob ein lineares
Gleichungssystem eindeutig lösbar ist oder nicht. Dazu behandeln wir in diesem
Kapitel das Thema inverse Matrizen.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie wissen, wann es erlaubt ist, die **inverse Matrix** einer quadratischen
  Matrix zu berechnen und welche Rolle die Determinante dabei spielt.
* Sie können die **Inverse einer $2\times 2$-Matrix** berechnen.
* Sie können die **Inverse einer $n\times n$-Matrix** für $n>2$ berechnen.
* Sie kennen die **Rechenregeln für inverse Matrizen** und können sie anwenden.
```

## Inverse Matrix von $2\times 2$-Matrizen

Anhand der Überschrift können Sie schon erahnen, dass auch der Fachbegriff
**inverse Matrix** nur für quadratische Matrizen definiert ist. Wir beginnen mit
der Inversen einer $2 \times 2$-Matrix, also allgemein einer Matrix der Form

\begin{equation*}
\mathbf{A} = \begin{pmatrix} a & b \\ c & d \end{pmatrix}.
\end{equation*}

Wenn die Determinante dieser Matrix *ungleich Null* ist, können wir die Inverse
$\mathbf{A}^{-1}$ mit der Definition

\begin{equation*}
\mathbf{A}^{-1}=
\frac{1}{\det(\mathbf{A})} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
\end{equation*}

bilden. Jetzt ist auch ersichtlich, warum wir $\det{(\mathbf{A})}$ gefordert
haben, denn das Teilen durch Null ist strikt verboten.

Betrachten wir als Beispiel die Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}.
\end{equation*}

Die Determinante lautet

\begin{equation*}
\det(\mathbf{A}) = 2 \cdot 5 - 1 \cdot 3 = 10 - 3 = 7 \neq 0.
\end{equation*}

Da die Determinante ungleich null ist, können wir die Inverse der Matrix
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
ebenfalls eine quadratische Matrix, die wenn sie mit der ursprünglichen Matrix
multipliziert wird, die Einheitsmatrix $\mathbf{E}$ ergibt:

\begin{equation*}
\mathbf{A}^{-1}\cdot \mathbf{A} = \mathbf{E}.
\end{equation*}
```

## Inverse Matrix von $n \times n$-Matrizen

Die obige Definition einer inversen Matrix ist für alle quadratischen Matrizen
gültig. Auch bei einer quadratischen $n\times n$-Matrix $\mathbf{A}$ ist also
die inverse Matrix $\mathbf{A}^{-1}$ diejenige Matrix, für die dann
$\mathbf{A}^{-1}\cdot\mathbf{A}=\mathbf{E}$ gilt. Leider gibt es keine so schöne
einfache Formel zur Berechnung der Inversen. Die Berechnung der Inversen einer
$n \times n$-Matrix ist aufwändiger als bei $2 \times 2$-Matrizen und erfordert
in der Regel eine systematische Methode. Eines der bekanntesten Verfahren ist
der Gauß-Algorithmus, den wir auch schon zur Lösung eines linearen
Gleichungssystems kennengelernt haben.

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
