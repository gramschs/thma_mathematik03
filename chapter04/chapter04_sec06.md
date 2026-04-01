# Berechnung der Eigenwerte

Im letzten Abschnitt haben wir den Eigenvektor von $\mathbf{A}$ durch
glückliches Raten gefunden. In der Praxis mit großen Matrizen ist das natürlich
keine taugliche Methode. Wir brauchen ein systematisches Verfahren. Die
Schlüsselidee ist dabei eine Bedingung, die wir bereits kennen: die
Determinante. Wenn wir die Eigenwertgleichung geschickt umformulieren, führt
sie direkt auf die Suche nach den Nullstellen eines Polynoms.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können die Eigenwerte einer quadratischen Matrix $\mathbf{A}$ berechnen,
  indem Sie das **charakteristische Polynom**
  $p(\lambda) = \det(\mathbf{A} - \lambda\mathbf{E}) = 0$
  aufstellen und lösen.
* [ ] Sie können das charakteristische Polynom für $2\times 2$- und
  $3\times 3$-Matrizen explizit berechnen.
* [ ] Sie wissen, dass eine $n\times n$-Matrix **höchstens $n$ verschiedene
  Eigenwerte** besitzen kann.
* [ ] Sie können die Eigenwerte einer **Diagonal- oder Dreiecksmatrix** direkt
  aus der Diagonalen ablesen, ohne das charakteristische Polynom berechnen
  zu müssen.
```

## Wie kommen wir von der Eigenwertgleichung zum charakteristischen Polynom?

Wir starten mit der definierenden Gleichung $\mathbf{A}\vec{v} = \lambda\vec{v}$
und bringen alles auf eine Seite:

\begin{equation*}
\mathbf{A}\vec{v} - \lambda\vec{v} = \vec{0}.
\end{equation*}

Da wir $\mathbf{A}$ und $\lambda\mathbf{E}$ beide mit $\vec{v}$ multiplizieren,
können wir ausklammern:

\begin{equation*}
(\mathbf{A} - \lambda\mathbf{E})\vec{v} = \vec{0}.
\end{equation*}

Das ist ein homogenes lineares Gleichungssystem. Es hat eine nichttriviale
Lösung $\vec{v} \neq \vec{0}$ genau dann, wenn die Koeffizientenmatrix
$\mathbf{A} - \lambda\mathbf{E}$ nicht invertierbar ist, also wenn ihre
Determinante null ist. Aus dem Kapitel über Determinanten wissen wir: eine
Matrix ist genau dann nicht invertierbar, wenn ihre Determinante verschwindet.
Damit ergibt sich die Bedingung für Eigenwerte:

\begin{equation*}
\det(\mathbf{A} - \lambda\mathbf{E}) = 0.
\end{equation*}

```{admonition} Was ist ... das charakteristische Polynom?
:class: note
Für eine quadratische Matrix $\mathbf{A} \in \mathbb{R}^{n\times n}$ heißt der
Ausdruck

\begin{equation*}
p(\lambda) = \det(\mathbf{A} - \lambda\mathbf{E})
\end{equation*}

das **charakteristische Polynom** von $\mathbf{A}$. Es ist ein Polynom vom Grad
$n$ in $\lambda$. Die Eigenwerte von $\mathbf{A}$ sind genau die reellen
Nullstellen von $p(\lambda)$. Die Gleichung $p(\lambda) = 0$ heißt die
**charakteristische Gleichung**.
```

Eine $n\times n$-Matrix hat also höchstens $n$ verschiedene Eigenwerte, da ein
Polynom vom Grad $n$ höchstens $n$ Nullstellen hat. Für $2\times 2$-Matrizen
ist das charakteristische Polynom quadratisch, für $3\times 3$-Matrizen kubisch.

## Wie berechnen wir Eigenwerte für eine $2\times 2$-Matrix?

Wir kehren zu der Matrix zurück, die wir im letzten Abschnitt untersucht haben:

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 6 & 2 \\ 2 & 3 \end{pmatrix}.
\end{equation*}

Die Matrix $\mathbf{A} - \lambda\mathbf{E}$ lautet:

\begin{equation*}
\mathbf{A} - \lambda\mathbf{E} =
\begin{pmatrix} 6 - \lambda & 2 \\ 2 & 3 - \lambda \end{pmatrix}.
\end{equation*}

Die Determinante dieser Matrix ist das charakteristische Polynom:

\begin{equation*}
p(\lambda) = \det\begin{pmatrix} 6 - \lambda & 2 \\ 2 & 3 - \lambda \end{pmatrix}
= (6 - \lambda)(3 - \lambda) - 2 \cdot 2.
\end{equation*}

Wir multiplizieren aus und vereinfachen:

\begin{equation*}
p(\lambda) = 18 - 9\lambda + \lambda^2 - 4 = \lambda^2 - 9\lambda + 14.
\end{equation*}

Die charakteristische Gleichung $p(\lambda) = 0$ lösen wir mit der pq-Formel:

\begin{align*}
\lambda_{1/2}
&= \frac{9}{2} \pm \sqrt{\frac{81}{4} - 14}
= \frac{9}{2} \pm \sqrt{\frac{25}{4}}
= \frac{9}{2} \pm \frac{5}{2}.
\end{align*}

Damit erhalten wir die beiden Eigenwerte:

\begin{equation*}
\lambda_{1} = 7 \quad \text{und} \quad \lambda_{2} = 2.
\end{equation*}

Das überprüfen wir sofort: $p(7) = 49 - 63 + 14 = 0$ und $p(2) = 4 - 18 + 14 = 0$.
Beide Werte sind tatsächlich Nullstellen des charakteristischen Polynoms.

Für den Maschinenbau ist dieses Beispiel nicht nur akademisch. Stellen wir uns
vor, $\mathbf{A}$ sei der ebene Spannungstensor eines Biegebalkens mit
$\sigma_{xx} = 6~\text{MPa}$, $\sigma_{yy} = 3~\text{MPa}$ und
$\tau_{xy} = 2~\text{MPa}$. Dann sind die Eigenwerte $\lambda_1 = 7~\text{MPa}$
und $\lambda_2 = 2~\text{MPa}$ die Hauptspannungen des Spannungszustands.

## Wie berechnen wir Eigenwerte für eine $3\times 3$-Matrix?

Das Verfahren ist identisch: charakteristisches Polynom aufstellen,
Nullstellen bestimmen. Der Unterschied ist, dass die Determinante einer
$3\times 3$-Matrix ein kubisches Polynom in $\lambda$ ergibt.

Wir betrachten die Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 5 & -1 & 2 \\ -1 & 5 & 2 \\ 2 & 2 & 2 \end{pmatrix}.
\end{equation*}

Die charakteristische Gleichung lautet:

\begin{equation*}
\det\begin{pmatrix} 5 - \lambda & -1 & 2 \\ -1 & 5 - \lambda & 2 \\ 2 & 2 & 2 - \lambda \end{pmatrix} = 0.
\end{equation*}

Die Berechnung der Determinante mit der Regel von Sarrus oder dem Laplaceschen
Entwicklungssatz ergibt nach Ausmultiplizieren:

\begin{equation*}
p(\lambda) = -\lambda^3 + 12\lambda^2 - 36\lambda = -\lambda(\lambda^2 - 12\lambda + 36)
= -\lambda(\lambda - 6)^2.
\end{equation*}

Die Nullstellen sind $\lambda_3 = 0$ und $\lambda_1 = \lambda_2 = 6$. Der
Eigenwert $\lambda = 6$ ist eine doppelte Nullstelle: Wir sagen, er hat die
**algebraische Vielfachheit** $2$. Die drei Eigenwerte der Matrix sind somit
$\{0, 6, 6\}$.

*Was bedeutet es, wenn ein Eigenwert gleich Null ist?* Dann ist
$\det(\mathbf{A} - 0 \cdot \mathbf{E}) = \det(\mathbf{A}) = 0$. Die Matrix ist
nicht invertierbar, und das lineare Gleichungssystem $\mathbf{A}\vec{x} = \vec{b}$
hat keine eindeutige Lösung für jeden beliebigen Ergebnisvektor $\vec{b}$.

## Können wir Eigenwerte manchmal direkt ablesen?

Ja. Für Dreiecks- und Diagonalmatrizen lässt sich das charakteristische Polynom
besonders einfach berechnen. Erinnern wir uns an die Eigenschaft aus Kapitel 1:
die Determinante einer Dreiecksmatrix ist das Produkt ihrer Diagonalelemente.
Damit gilt für eine obere Dreiecksmatrix mit den Einträgen $d_1, d_2, \ldots, d_n$
auf der Diagonale:

\begin{equation*}
p(\lambda) = \det(\mathbf{A} - \lambda\mathbf{E}) = (d_1 - \lambda)(d_2 - \lambda)\cdots(d_n - \lambda).
\end{equation*}

Die Nullstellen sind direkt die Diagonaleinträge: Die Eigenwerte einer
Dreiecksmatrix (oder Diagonalmatrix) stehen auf der Hauptdiagonale. Für die
Matrix

\begin{equation*}
\mathbf{T} = \begin{pmatrix} 3 & 1 & 7 \\ 0 & -2 & 4 \\ 0 & 0 & 5 \end{pmatrix}
\end{equation*}

können wir sofort ablesen: die Eigenwerte sind $\lambda_1 = 3$, $\lambda_2 = -2$
und $\lambda_3 = 5$.

## Zusammenfassung und Ausblick

Die Eigenwerte einer quadratischen Matrix werden als Nullstellen des
charakteristischen Polynoms $p(\lambda) = \det(\mathbf{A} - \lambda\mathbf{E}) = 0$
berechnet. Für $2\times 2$-Matrizen führt das auf eine quadratische, für
$3\times 3$-Matrizen auf eine kubische Gleichung. Dreiecks- und Diagonalmatrizen
erlauben das direkte Ablesen der Eigenwerte aus der Diagonale.

Jetzt kennen wir die Eigenwerte, aber noch nicht die zugehörigen Eigenvektoren.
Der nächste Abschnitt zeigt, wie man für jeden gefundenen Eigenwert $\lambda_i$
das homogene Gleichungssystem $(\mathbf{A} - \lambda_i\mathbf{E})\vec{v} = \vec{0}$
löst und damit die Eigenvektoren bestimmt.
