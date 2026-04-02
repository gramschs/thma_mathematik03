---
authors:
  - name:
---

# Eigenwerte symmetrischer Matrizen

In Abschnitt 5.1 haben wir für den Trägheitstensor des L-Profils zwei
Eigenvektoren berechnet und am Ende beiläufig festgestellt, dass sie senkrecht
aufeinander stehen. War das Zufall? Und warum waren die Eigenwerte beide reell,
obwohl das charakteristische Polynom grundsätzlich auch komplexe Nullstellen
haben könnte? In diesem Abschnitt zeigen wir, dass beides kein Zufall ist,
sondern eine direkte Folge der Symmetrie der Matrix.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, dass alle Eigenwerte einer **symmetrischen Matrix** reell sind.
* [ ] Sie wissen, dass Eigenvektoren zu **verschiedenen Eigenwerten** einer
  symmetrischen Matrix stets senkrecht aufeinander stehen.
* [ ] Sie wissen, dass eine symmetrische $n\times n$-Matrix stets $n$ paarweise
  orthogonale Eigenvektoren besitzt.
* [ ] Sie können diese Eigenschaften am Trägheitstensor und am Spannungstensor
  erläutern.
```

## Warum sind die Eigenwerte immer reell?

In der Technischen Mechanik beschreiben symmetrische Matrizen physikalische
Größen wie den Spannungstensor oder den Trägheitstensor. Die Eigenwerte dieser
Tensoren sind Hauptspannungen oder Hauptträgheitsmomente. Solche Größen sind
stets reelle Zahlen, denn eine imaginäre Spannung hat keine physikalische
Bedeutung. Dass die Mathematik das automatisch garantiert, ist eine der
schönsten Eigenschaften symmetrischer Matrizen.

Wir überprüfen das zunächst an unserem L-Profil-Beispiel aus Abschnitt 5.1.
Der Trägheitstensor

\begin{equation*}
\mathbf{I} = \begin{pmatrix} 5 & 2 \\ 2 & 2 \end{pmatrix} \cdot 10^4\,\text{mm}^4
\end{equation*}

ist symmetrisch, denn er stimmt mit seiner Transponierten überein:
$\mathbf{I}^T = \mathbf{I}$. Das charakteristische Polynom lautet
$p(\lambda) = \lambda^2 - 7\lambda + 6$. Die Diskriminante ist
$\Delta = 49 - 24 = 25 > 0$, also gibt es zwei reelle Nullstellen. Das ist
hier offensichtlich. Bei einer $3\times 3$-Matrix oder größer ist es jedoch
keineswegs selbstverständlich, dass alle Nullstellen des charakteristischen
Polynoms reell sind.

```{admonition} Eigenwerte symmetrischer Matrizen sind reell
:class: note
Ist $\mathbf{A} \in \mathbb{R}^{n\times n}$ eine symmetrische Matrix
($\mathbf{A}^T = \mathbf{A}$), dann sind alle Eigenwerte von $\mathbf{A}$ reell.
```

Diese Aussage gilt für jede Dimension, also auch für den $3\times 3$-Spannungstensor
oder den $6\times 6$-Steifigkeitstensor in der FEM. Wir werden den Beweis hier
nicht im Detail führen, aber die Idee ist verständlich: Symmetrie erzwingt, dass
sich konjugiert komplexe Eigenwerte gegenseitig auslöschen.

## Warum stehen die Eigenvektoren senkrecht aufeinander?

In Abschnitt 5.1 haben wir für das L-Profil die beiden Eigenvektoren

\begin{equation*}
\vec{v}_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}
\quad \text{und} \quad
\vec{v}_2 = \begin{pmatrix} 1 \\ -2 \end{pmatrix}
\end{equation*}

zu den Eigenwerten $\lambda_1 = 6$ und $\lambda_2 = 1$ berechnet. Das
Skalarprodukt ergibt $\vec{v}_1 \cdot \vec{v}_2 = 2\cdot 1 + 1\cdot(-2) = 0$.
Die beiden Vektoren stehen tatsächlich senkrecht. *Aber gilt das immer, oder
nur für dieses besondere Beispiel?*

Wir zeigen, dass es für jede symmetrische Matrix gilt. Dazu gehen wir von zwei
verschiedenen Eigenwerten $\lambda_1 \neq \lambda_2$ und den zugehörigen
Eigenvektoren $\vec{v}_1$ und $\vec{v}_2$ aus. Es gilt:

\begin{equation*}
\mathbf{A}\vec{v}_1 = \lambda_1\vec{v}_1
\quad \text{und} \quad
\mathbf{A}\vec{v}_2 = \lambda_2\vec{v}_2.
\end{equation*}

Wir multiplizieren die erste Gleichung von links mit $\vec{v}_2^T$ und nutzen
die Symmetrie $\mathbf{A}^T = \mathbf{A}$:

\begin{align*}
\vec{v}_2^T \mathbf{A} \vec{v}_1 &= \lambda_1 \vec{v}_2^T \vec{v}_1, \\
(\mathbf{A}\vec{v}_2)^T \vec{v}_1 &= \lambda_1 \vec{v}_2^T \vec{v}_1, \\
\lambda_2 \vec{v}_2^T \vec{v}_1 &= \lambda_1 \vec{v}_2^T \vec{v}_1.
\end{align*}

Umstellen ergibt:

\begin{equation*}
(\lambda_2 - \lambda_1)\,\vec{v}_2^T \vec{v}_1 = 0.
\end{equation*}

Da $\lambda_1 \neq \lambda_2$ vorausgesetzt ist, muss $\vec{v}_2^T \vec{v}_1 = 0$
gelten. Das ist genau die Bedingung dafür, dass $\vec{v}_1$ und $\vec{v}_2$
senkrecht aufeinander stehen.

```{admonition} Eigenvektoren symmetrischer Matrizen sind orthogonal
:class: note
Ist $\mathbf{A} \in \mathbb{R}^{n\times n}$ eine symmetrische Matrix und sind
$\lambda_1 \neq \lambda_2$ zwei verschiedene Eigenwerte mit den zugehörigen
Eigenvektoren $\vec{v}_1$ und $\vec{v}_2$, dann gilt:

\begin{equation*}
\vec{v}_1 \cdot \vec{v}_2 = 0.
\end{equation*}

Die Eigenvektoren stehen senkrecht aufeinander.
```

Angewendet auf unser L-Profil bestätigt das die Rechnung von oben: Die
Hauptträgheitsachsen, also die Richtungen der größten und kleinsten
Biegesteifigkeit, stehen immer senkrecht aufeinander. Das ist eine fundamentale
geometrische Eigenschaft jedes Balkenquerschnitts mit symmetrischem Tensor.

## Was sagt uns das über die Diagonalisierung?

Wir haben jetzt zwei starke Aussagen: Alle Eigenwerte sind reell, und Eigenvektoren
zu verschiedenen Eigenwerten stehen senkrecht aufeinander. Zusammen ergeben
sie etwas noch Stärkeres.

Für eine symmetrische $n\times n$-Matrix lässt sich immer eine vollständige
Basis aus $n$ paarweise orthogonalen Eigenvektoren finden. Das gilt auch dann,
wenn ein Eigenwert mehrfach auftritt: In diesem Fall kann man die Eigenvektoren
im mehrdimensionalen Eigenraum so wählen, dass sie senkrecht aufeinander stehen.
Das Gram-Schmidt-Verfahren aus Abschnitt 4.2 leistet genau das.

```{admonition} Symmetrische Matrizen sind immer diagonalisierbar
:class: note
Eine symmetrische Matrix $\mathbf{A} \in \mathbb{R}^{n\times n}$ besitzt stets
$n$ paarweise orthogonale Eigenvektoren. Insbesondere gilt für alle Eigenwerte
$d_\lambda = m_\lambda$. Die Matrix ist immer diagonalisierbar, und die
Transformationsmatrix $\mathbf{V}$ kann sogar als orthogonale Matrix gewählt
werden.
```

Diese Aussage ist als **Spektralsatz** bekannt. Er ist einer der zentralen Sätze
der linearen Algebra. Für den Maschinenbau bedeutet er: Immer wenn ein
physikalischer Tensor symmetrisch ist, gibt es garantiert ein Koordinatensystem,
in dem er diagonal ist. Genau das sucht man in der Technischen Mechanik, wenn
man Hauptspannungen oder Hauptträgheitsachsen berechnet.

## Das Beispiel zu Ende: der Spannungstensor

Den Spektralsatz wenden wir abschließend auf ein zweites Standardbeispiel an,
das in der Festigkeitslehre allgegenwärtig ist. An einem belasteten Bauteil
liegt an einem bestimmten Punkt der folgende ebene **Spannungstensor** vor:

\begin{equation*}
\boldsymbol{\sigma} =
\begin{pmatrix} 7 & 2 \\ 2 & 4 \end{pmatrix}~\text{MPa}.
\end{equation*}

Die Einträge auf der Diagonale sind Normalspannungen in $x$- und $y$-Richtung,
der Nebendiagonaleintrag ist die Schubspannung. Der Tensor ist symmetrisch.
Wir berechnen die Eigenwerte:

\begin{equation*}
p(\lambda) = (7 - \lambda)(4 - \lambda) - 4 = \lambda^2 - 11\lambda + 24 = 0.
\end{equation*}

Mit der Lösungsformel ergibt sich:

\begin{equation*}
\lambda_{1,2} = \frac{11}{2} \pm \sqrt{\frac{121}{4} - 24} =
\frac{11}{2} \pm \sqrt{\frac{25}{4}} = \frac{11}{2} \pm \frac{5}{2}.
\end{equation*}

Die beiden Eigenwerte sind $\lambda_1 = 8~\text{MPa}$ und
$\lambda_2 = 3~\text{MPa}$. Das sind die **Hauptspannungen** des Spannungszustands,
also die größten und kleinsten Normalspannungen, die an diesem Punkt auftreten
können. Da der Spektralsatz gilt, stehen die zugehörigen Hauptspannungsrichtungen
garantiert senkrecht aufeinander.

Wir überprüfen das mit den Eigenvektoren. Für $\lambda_1 = 8$:

\begin{equation*}
\boldsymbol{\sigma} - 8\mathbf{E} =
\begin{pmatrix} -1 & 2 \\ 2 & -4 \end{pmatrix}
\quad \Rightarrow \quad
\vec{v}_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}.
\end{equation*}

Für $\lambda_2 = 3$:

\begin{equation*}
\boldsymbol{\sigma} - 3\mathbf{E} =
\begin{pmatrix} 4 & 2 \\ 2 & 1 \end{pmatrix}
\quad \Rightarrow \quad
\vec{v}_2 = \begin{pmatrix} 1 \\ -2 \end{pmatrix}.
\end{equation*}

Probe: $\vec{v}_1 \cdot \vec{v}_2 = 2\cdot 1 + 1\cdot(-2) = 0$. Die
Hauptspannungsrichtungen stehen tatsächlich senkrecht aufeinander. In der
Festigkeitslehre ist dieser Punkt der Ausgangspunkt für die Berechnung des
Mohrschen Spannungskreises und für Versagenskriterien wie das
von-Mises-Kriterium, die Sie in der Technischen Mechanik II vertiefen werden.

```{dropdown} Video "Eigenwerte und Eigenvektoren symmetrischer Matrizen" von MathePeter
<iframe width="560" height="315" src="https://www.youtube.com/embed/PLATZHALTER"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

Symmetrische Matrizen haben zwei außergewöhnliche Eigenschaften: Alle ihre
Eigenwerte sind reell, und ihre Eigenvektoren zu verschiedenen Eigenwerten
stehen senkrecht aufeinander. Zusammen garantieren diese Eigenschaften, dass
symmetrische Matrizen immer diagonalisierbar sind. Das ist der Spektralsatz,
und er erklärt, warum die Berechnung von Hauptspannungen und
Hauptträgheitsmomenten in der Praxis immer gelingt. In Abschnitt 5.3 führen
wir den Begriff der ähnlichen Matrizen ein, der den mathematischen Rahmen für
die Diagonalisierung liefert. In Abschnitt 5.4 werden wir dann sehen, wie man
jede diagonalisierbare Matrix konkret auf Diagonalform bringt.
