# Berechnung der Eigenvektoren

Wir kennen jetzt die Eigenwerte einer Matrix, aber die Richtungen, die diesen
Eigenwerten entsprechen, fehlen noch. In der Schwingungsanalyse sind das die
Schwingungsformen, in der Festigkeitslehre die Richtungen der Hauptspannungen.
Die Berechnung dieser Richtungen, der Eigenvektoren, ist der nächste logische
Schritt, und wir werden sehen, dass es sich um das Lösen eines homogenen
linearen Gleichungssystems handelt, eine Aufgabe, die wir bereits beherrschen.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können zu einem gegebenen Eigenwert $\lambda_i$ den zugehörigen
  **Eigenvektor** berechnen, indem Sie das homogene lineare Gleichungssystem
  $(\mathbf{A} - \lambda_i\mathbf{E})\vec{v} = \vec{0}$ lösen.
* [ ] Sie wissen, dass Eigenvektoren **nicht eindeutig bestimmt** sind: Jedes
  skalare Vielfache eines Eigenvektors ist ebenfalls ein Eigenvektor zum selben
  Eigenwert.
* [ ] Sie können Eigenvektoren **normieren**, sodass sie die Länge Eins haben.
* [ ] Sie kennen den Begriff des **Eigenraums**
  $\text{Eig}_{\mathbf{A}}(\lambda) = \text{Kern}(\mathbf{A} - \lambda\mathbf{E})$
  und wissen, dass er alle Eigenvektoren zum Eigenwert $\lambda$ enthält.
```

## Wie erhalten wir den Eigenvektor aus dem Eigenwert?

Ist der Eigenwert $\lambda$ bekannt, suchen wir alle Vektoren $\vec{v} \neq \vec{0}$,
die die Gleichung $\mathbf{A}\vec{v} = \lambda\vec{v}$ erfüllen. Wir formen
um:

\begin{equation*}
(\mathbf{A} - \lambda\mathbf{E})\vec{v} = \vec{0}.
\end{equation*}

Das ist ein homogenes lineares Gleichungssystem mit der Koeffizientenmatrix
$\mathbf{A} - \lambda\mathbf{E}$. Da wir $\lambda$ so gewählt haben, dass
$\det(\mathbf{A} - \lambda\mathbf{E}) = 0$ gilt, ist diese Matrix nicht
invertierbar. Das Gleichungssystem hat daher unendlich viele Lösungen: neben
dem Nullvektor gibt es immer nichttriviale Lösungen, und genau das sind die
Eigenvektoren.

Die Menge aller Lösungen dieses Gleichungssystems bildet den **Eigenraum**
zum Eigenwert $\lambda$:

\begin{equation*}
\text{Eig}_{\mathbf{A}}(\lambda) = \{\vec{v} \in \mathbb{R}^n \mid
(\mathbf{A} - \lambda\mathbf{E})\vec{v} = \vec{0}\}.
\end{equation*}

Dieser Eigenraum enthält den Nullvektor und alle Eigenvektoren zu $\lambda$.
Er ist immer mindestens eindimensional, da der Eigenwert $\lambda$ eine Nullstelle
des charakteristischen Polynoms ist.

## Wie werden Eigenvektoren für $2\times 2$-Matrizen berechnet?

Wir setzen die Berechnung aus dem letzten Abschnitt fort. Zu der Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 6 & 2 \\ 2 & 3 \end{pmatrix}
\end{equation*}

haben wir die Eigenwerte $\lambda_1 = 7$ und $\lambda_2 = 2$ bestimmt.

**Eigenvektor zum Eigenwert $\lambda_1 = 7$:**

Wir stellen das Gleichungssystem $(\mathbf{A} - 7\mathbf{E})\vec{v} = \vec{0}$
auf:

\begin{equation*}
\mathbf{A} - 7\mathbf{E} =
\begin{pmatrix} 6 - 7 & 2 \\ 2 & 3 - 7 \end{pmatrix} =
\begin{pmatrix} -1 & 2 \\ 2 & -4 \end{pmatrix}.
\end{equation*}

Das Gleichungssystem lautet:

\begin{align*}
-x + 2y &= 0, \\
2x - 4y &= 0.
\end{align*}

Beide Gleichungen sind äquivalent (die zweite ist das $(-2)$-fache der ersten).
Aus der ersten Gleichung folgt $x = 2y$. Mit $y = s$ als freiem Parameter
ergibt sich:

\begin{equation*}
\vec{v}_1 = s\cdot\begin{pmatrix} 2 \\ 1 \end{pmatrix}, \quad s \neq 0.
\end{equation*}

Als normierten Eigenvektor wählen wir $s = 1$ und normieren:

\begin{equation*}
\hat{v}_1 = \frac{1}{\|\vec{v}_1\|}\vec{v}_1 = \frac{1}{\sqrt{5}}
\begin{pmatrix} 2 \\ 1 \end{pmatrix}.
\end{equation*}

Wir überprüfen: $\mathbf{A}\vec{v}_1 = \begin{pmatrix} 6\cdot2+2\cdot1 \\ 2\cdot2+3\cdot1 \end{pmatrix} = \begin{pmatrix} 14 \\ 7 \end{pmatrix} = 7\cdot\begin{pmatrix} 2 \\ 1 \end{pmatrix}$. Das Ergebnis stimmt.

**Eigenvektor zum Eigenwert $\lambda_2 = 2$:**

Wir stellen das Gleichungssystem $(\mathbf{A} - 2\mathbf{E})\vec{v} = \vec{0}$
auf:

\begin{equation*}
\mathbf{A} - 2\mathbf{E} =
\begin{pmatrix} 4 & 2 \\ 2 & 1 \end{pmatrix}.
\end{equation*}

Das Gleichungssystem lautet:

\begin{align*}
4x + 2y &= 0, \\
2x + y &= 0.
\end{align*}

Aus der zweiten Gleichung folgt $y = -2x$. Mit $x = t$ als freiem Parameter:

\begin{equation*}
\vec{v}_2 = t\cdot\begin{pmatrix} 1 \\ -2 \end{pmatrix}, \quad t \neq 0.
\end{equation*}

Wir überprüfen: $\mathbf{A}\vec{v}_2 = \begin{pmatrix} 6-4 \\ 2-6 \end{pmatrix} = \begin{pmatrix} 2 \\ -4 \end{pmatrix} = 2\cdot\begin{pmatrix} 1 \\ -2 \end{pmatrix}$. Korrekt.

Es fällt auf: Die beiden Eigenvektoren $\vec{v}_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$
und $\vec{v}_2 = \begin{pmatrix} 1 \\ -2 \end{pmatrix}$ stehen senkrecht
aufeinander, denn $\vec{v}_1 \cdot \vec{v}_2 = 2\cdot 1 + 1\cdot(-2) = 0$.
Das ist kein Zufall: Für symmetrische Matrizen wie $\mathbf{A}$ sind die
Eigenvektoren zu verschiedenen Eigenwerten stets orthogonal. Diese Eigenschaft
ist für die Anwendung in der Festigkeitslehre und in der Schwingungsanalyse
fundamental.

```{dropdown} Video "Eigenwerte, Eigenvektoren 2x2" von Daniel Jung
<iframe width="560" height="315" src="https://www.youtube.com/embed/Rr0aa7oo5u8"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Wie werden Eigenvektoren für $3\times 3$-Matrizen berechnet?

Das Vorgehen ist dasselbe: Für jeden Eigenwert $\lambda_i$ lösen wir das
homogene Gleichungssystem $(\mathbf{A} - \lambda_i\mathbf{E})\vec{v} = \vec{0}$.
Wir betrachten die Matrix aus dem letzten Abschnitt:

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 5 & -1 & 2 \\ -1 & 5 & 2 \\ 2 & 2 & 2 \end{pmatrix}
\end{equation*}

mit den Eigenwerten $\lambda_1 = \lambda_2 = 6$ und $\lambda_3 = 0$.

**Eigenvektoren zum Eigenwert $\lambda = 6$:**

Die Matrix $\mathbf{A} - 6\mathbf{E}$ lautet:

\begin{equation*}
\mathbf{A} - 6\mathbf{E} =
\begin{pmatrix} -1 & -1 & 2 \\ -1 & -1 & 2 \\ 2 & 2 & -4 \end{pmatrix}.
\end{equation*}

Alle drei Zeilen sind Vielfache voneinander: die zweite Zeile ist identisch
mit der ersten, die dritte ist das $(-2)$-fache der ersten. Das Gleichungssystem
hat also de facto nur eine unabhängige Gleichung:

\begin{equation*}
-x - y + 2z = 0 \quad \Rightarrow \quad x = -y + 2z.
\end{equation*}

Wir wählen $y = s$ und $z = t$ als freie Parameter und erhalten:

\begin{equation*}
\vec{v} = \begin{pmatrix} -s + 2t \\ s \\ t \end{pmatrix} =
s\begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix} + t\begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}.
\end{equation*}

Der Eigenraum ist zweidimensional. Als zwei Basisvektoren wählen wir:

\begin{equation*}
\vec{v}_1 = \begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix}
\quad \text{und} \quad
\vec{v}_2 = \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}.
\end{equation*}

**Eigenvektor zum Eigenwert $\lambda_3 = 0$:**

Die Matrix $\mathbf{A} - 0\cdot\mathbf{E} = \mathbf{A}$ selbst ist die
Koeffizientenmatrix. Da $\det(\mathbf{A}) = 0$, hat das Gleichungssystem
$\mathbf{A}\vec{v} = \vec{0}$ nichttriviale Lösungen. Mit dem
Gauß-Algorithmus ergibt sich:

\begin{equation*}
\vec{v}_3 = \begin{pmatrix} -1 \\ -1 \\ 2 \end{pmatrix}.
\end{equation*}

Wir prüfen: $\mathbf{A}\vec{v}_3 = \begin{pmatrix} 5(-1)+(-1)(-1)+2\cdot2 \\ (-1)(-1)+5(-1)+2\cdot2 \\ 2(-1)+2(-1)+2\cdot2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$. Korrekt.

*Warum ist der Eigenraum zum Eigenwert $\lambda = 6$ zweidimensional und nicht
eindimensional?* Weil der Eigenwert $6$ die algebraische Vielfachheit $2$ hat.
Wenn ein Eigenwert mehrfach auftritt, kann sein Eigenraum eine entsprechend
höhere Dimension haben. Diese Situation begegnet uns in der Schwingungsanalyse
als **degenerierte Eigenfrequenz**: Zwei verschiedene Schwingungsformen des
Systems haben dieselbe Frequenz.

```{dropdown} Video "Eigenwerte und Eigenvektoren berechnen" von Mathematrick
<iframe width="560" height="315" src="https://www.youtube.com/embed/72nXOF8KxEg"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Was ist das Resultat: die Eigenzerlegung im Überblick

Fassen wir das Ergebnis für unser Hauptbeispiel zusammen. Die symmetrische
Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 6 & 2 \\ 2 & 3 \end{pmatrix}
\end{equation*}

hat die Eigenwertpaare

| Eigenwert $\lambda$ | Eigenvektor (normiert) | Bedeutung (Spannungstensor) |
| --- | --- | --- |
| $\lambda_1 = 7$ | $\frac{1}{\sqrt{5}}\begin{pmatrix} 2 \\ 1 \end{pmatrix}$ | Größte Hauptspannung |
| $\lambda_2 = 2$ | $\frac{1}{\sqrt{5}}\begin{pmatrix} 1 \\ -2 \end{pmatrix}$ | Kleinste Hauptspannung |

Die normierten Eigenvektoren stehen senkrecht aufeinander. Schreiben wir sie
als Spalten in eine Matrix, entsteht eine orthogonale Matrix. Damit schließt
sich der Bogen zu Kapitel 4.1: Die Eigenvektoren einer symmetrischen Matrix
liefern eine orthonormale Basis, die den gleichen Raum aufspannt wie die
Standardbasis, aber in den Hauptrichtungen der Transformation liegt. Genau das
nutzt man in der Technischen Mechanik, um den Spannungstensor auf seine
Diagonalform zu bringen.

## Zusammenfassung und Ausblick

Zu jedem Eigenwert $\lambda_i$ werden die Eigenvektoren berechnet, indem das
homogene Gleichungssystem $(\mathbf{A} - \lambda_i\mathbf{E})\vec{v} = \vec{0}$
gelöst wird. Eigenvektoren sind nicht eindeutig: Jedes Vielfache eines
Eigenvektors ist wieder ein Eigenvektor. Bei einem mehrfachen Eigenwert kann
der Eigenraum mehrdimensional sein.

Für symmetrische Matrizen sind die Eigenvektoren zu verschiedenen Eigenwerten
stets orthogonal. Dieser Satz, der im Spektraltheorem für symmetrische Matrizen
seinen vollständigen Ausdruck findet, hat weitreichende Konsequenzen: In der
Schwingungsanalyse erlaubt er die Entkopplung von Bewegungsgleichungen, in der
Festigkeitslehre die Berechnung der Hauptspannungen, und in der
Regelungstechnik die modalen Koordinaten. Diese Anwendungen werden Sie in den
Folgeveranstaltungen Technische Mechanik, Maschinendynamik und Regelungstechnik
vertiefen.
