---
authors:
  - name: Simone Gramsch
---

# 6.4 Symmetrische Matrizen und Diagonalisierung

In Abschnitt 5.3 haben wir für die symmetrische Matrix
$\mathbf{A} = \begin{pmatrix} 6 & 2 \\ 2 & 3 \end{pmatrix}$
die Eigenvektoren $\vec{v}_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$ und
$\vec{v}_2 = \begin{pmatrix} 1 \\ -2 \end{pmatrix}$ berechnet und dabei
bemerkt: $\vec{v}_1 \cdot \vec{v}_2 = 0$. Wir haben das als Tatsache
festgehalten, aber noch nicht erklärt. In diesem Abschnitt zeigen wir, warum
das immer so ist, wenn die Matrix symmetrisch ist, und nutzen diese Eigenschaft
dann, um die Matrix auf eine besonders einfache Form zu bringen: eine
Diagonalmatrix, in der die Eigenwerte direkt ablesbar sind.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, dass alle Eigenwerte einer **symmetrischen Matrix** reell sind
  und können beweisen, dass Eigenvektoren zu verschiedenen Eigenwerten stets
  orthogonal sind.
* [ ] Sie verstehen, dass eine **Ähnlichkeitstransformation**
  $\mathbf{C} = \mathbf{B}^{-1}\mathbf{A}\mathbf{B}$ dieselbe lineare
  Abbildung in einem anderen Koordinatensystem beschreibt und die Eigenwerte
  erhält.
* [ ] Sie wissen, wann eine Matrix **diagonalisierbar** ist: genau dann, wenn
  für alle Eigenwerte $d_\lambda = m_\lambda$ gilt.
* [ ] Sie können eine diagonalisierbare Matrix **diagonalisieren**, indem Sie
  die Eigenvektoren als Spalten in $\mathbf{V}$ schreiben und
  $\mathbf{D} = \mathbf{V}^{-1}\mathbf{A}\mathbf{V}$ berechnen.
* [ ] Sie kennen den **Spektralsatz**: Jede symmetrische Matrix ist
  diagonalisierbar, und $\mathbf{V}$ kann als orthogonale Matrix $\mathbf{Q}$
  mit $\mathbf{Q}^{-1} = \mathbf{Q}^T$ gewählt werden.
```

## Warum sind Eigenvektoren symmetrischer Matrizen orthogonal?

In der Festigkeitslehre tritt der Spannungstensor als symmetrische Matrix auf.
Seine Eigenwerte, die Hauptspannungen, müssen reelle Größen sein: Eine imaginäre
Spannung hätte keine physikalische Bedeutung. Dass die Mathematik das automatisch
sicherstellt, ist eine der wichtigsten Eigenschaften symmetrischer Matrizen.
*Aber warum sind auch die Eigenvektoren stets orthogonal?* Wir zeigen das allgemein.

Seien $\lambda_1 \neq \lambda_2$ zwei Eigenwerte einer symmetrischen Matrix
$\mathbf{A}$ mit Eigenvektoren $\vec{v}_1$ und $\vec{v}_2$. Wir multiplizieren
die Gleichung $\mathbf{A}\vec{v}_1 = \lambda_1 \vec{v}_1$ von links mit
$\vec{v}_2^T$ und nutzen $\mathbf{A}^T = \mathbf{A}$:

\begin{align*}
\vec{v}_2^T \mathbf{A} \vec{v}_1 &= \lambda_1\, \vec{v}_2^T \vec{v}_1, \\
(\mathbf{A} \vec{v}_2)^T \vec{v}_1 &= \lambda_1\, \vec{v}_2^T \vec{v}_1, \\
\lambda_2\, \vec{v}_2^T \vec{v}_1 &= \lambda_1\, \vec{v}_2^T \vec{v}_1.
\end{align*}

Umstellen liefert $(\lambda_2 - \lambda_1)\,\vec{v}_2^T \vec{v}_1 = 0$. Da
$\lambda_1 \neq \lambda_2$ vorausgesetzt ist, muss $\vec{v}_2^T \vec{v}_1 = 0$
gelten. Die Orthogonalität folgt zwingend aus der Symmetrie.

```{admonition} Eigenwerte und Eigenvektoren symmetrischer Matrizen
:class: note
Sei $\mathbf{A} \in \mathbb{R}^{n \times n}$ eine symmetrische Matrix
($\mathbf{A}^T = \mathbf{A}$). Dann gilt:

1. Alle Eigenwerte von $\mathbf{A}$ sind **reell**.
2. Eigenvektoren zu verschiedenen Eigenwerten sind **orthogonal**:
   aus $\lambda_1 \neq \lambda_2$ folgt $\vec{v}_1 \cdot \vec{v}_2 = 0$.
3. Es gibt immer eine vollständige Basis aus $n$ paarweise orthogonalen
   Eigenvektoren.
```

Für unsere Beispielmatrix bestätigt das die Rechnung aus Abschnitt 5.3:
$\vec{v}_1 \cdot \vec{v}_2 = 2 \cdot 1 + 1 \cdot (-2) = 0$. Spannungstensor,
Trägheitstensor und Steifigkeitsmatrix in der FEM sind allesamt symmetrisch.
Der Satz garantiert daher, dass ihre Eigenwerte stets reell und ihre
Eigenrichtungen stets orthogonal sind, unabhängig von der Wahl des
Koordinatensystems.

## Von den Eigenvektoren zur Diagonalmatrix

Wir kehren zu unserem Beispiel zurück. Wir schreiben die Eigenvektoren aus
Abschnitt 5.3 nebeneinander in eine Matrix:

\begin{equation*}
\mathbf{V} = \bigl(\vec{v}_1 \;\big|\; \vec{v}_2\bigr)
= \begin{pmatrix} 2 & 1 \\ 1 & -2 \end{pmatrix}.
\end{equation*}

Nun berechnen wir das Produkt $\mathbf{A}\mathbf{V}$. Da jede Spalte von
$\mathbf{V}$ ein Eigenvektor ist, gilt $\mathbf{A}\vec{v}_k = \lambda_k\vec{v}_k$,
und das Produkt lässt sich kompakt schreiben:

\begin{equation*}
\mathbf{A}\mathbf{V}
= \bigl(\mathbf{A}\vec{v}_1 \;\big|\; \mathbf{A}\vec{v}_2\bigr)
= \bigl(\lambda_1 \vec{v}_1 \;\big|\; \lambda_2 \vec{v}_2\bigr)
= \mathbf{V} \begin{pmatrix} 7 & 0 \\ 0 & 2 \end{pmatrix}
= \mathbf{V}\mathbf{D}.
\end{equation*}

Da $\mathbf{V}$ invertierbar ist (seine Spalten sind linear unabhängig), folgt
durch Linksmultiplikation mit $\mathbf{V}^{-1}$:

\begin{equation*}
\mathbf{D} = \mathbf{V}^{-1}\mathbf{A}\mathbf{V}
= \begin{pmatrix} 7 & 0 \\ 0 & 2 \end{pmatrix}.
\end{equation*}

Das Ergebnis ist eine Diagonalmatrix mit den Eigenwerten auf der Hauptdiagonale.
Wir verifizieren mit der Probe $\mathbf{A}\mathbf{V} = \mathbf{V}\mathbf{D}$:

\begin{equation*}
\mathbf{A}\mathbf{V} =
\begin{pmatrix} 6 & 2 \\ 2 & 3 \end{pmatrix}
\begin{pmatrix} 2 & 1 \\ 1 & -2 \end{pmatrix}
= \begin{pmatrix} 14 & 2 \\ 7 & -4 \end{pmatrix},
\qquad
\mathbf{V}\mathbf{D} =
\begin{pmatrix} 2 & 1 \\ 1 & -2 \end{pmatrix}
\begin{pmatrix} 7 & 0 \\ 0 & 2 \end{pmatrix}
= \begin{pmatrix} 14 & 2 \\ 7 & -4 \end{pmatrix}.
\end{equation*}

Beide Seiten stimmen überein. Die Transformation $\mathbf{A} \mapsto
\mathbf{V}^{-1}\mathbf{A}\mathbf{V}$ beschreibt dieselbe lineare Abbildung
wie $\mathbf{A}$, aber im Koordinatensystem der Eigenvektoren. Zwei Matrizen,
die durch eine solche Transformation miteinander zusammenhängen, nennen wir
**ähnlich**. Ähnliche Matrizen haben dieselben Eigenwerte, weil physikalische
Größen wie Hauptspannungen nicht davon abhängen können, in welchem
Koordinatensystem wir den Tensor aufschreiben.

```{admonition} Was sind ... ähnliche Matrizen und Diagonalisierung?
:class: note
Zwei Matrizen $\mathbf{A}, \mathbf{C} \in \mathbb{R}^{n \times n}$ heißen
**ähnlich**, wenn es eine invertierbare Matrix $\mathbf{B}$ gibt mit

\begin{equation*}
\mathbf{C} = \mathbf{B}^{-1}\mathbf{A}\mathbf{B}.
\end{equation*}

Ähnliche Matrizen beschreiben dieselbe lineare Abbildung in verschiedenen
Koordinatensystemen und haben dasselbe charakteristische Polynom und damit
dieselben Eigenwerte.

Eine Matrix $\mathbf{A}$ heißt **diagonalisierbar**, wenn eine invertierbare
Matrix $\mathbf{V}$ existiert, sodass $\mathbf{D} = \mathbf{V}^{-1}\mathbf{A}\mathbf{V}$
eine Diagonalmatrix ist. Die Spalten von $\mathbf{V}$ sind dann Eigenvektoren
von $\mathbf{A}$, die Diagonalelemente von $\mathbf{D}$ die zugehörigen
Eigenwerte in derselben Reihenfolge.

$\mathbf{A}$ ist genau dann diagonalisierbar, wenn für alle Eigenwerte gilt:
$d_\lambda = m_\lambda$.
```

Da $\mathbf{A}$ symmetrisch ist, sind die Eigenvektoren orthogonal und wir
können sie auf Länge Eins normieren. Die normierte Eigenvektormatrix

\begin{equation*}
\mathbf{Q} = \frac{1}{\sqrt{5}}\begin{pmatrix} 2 & 1 \\ 1 & -2 \end{pmatrix}
\end{equation*}

ist orthogonal im Sinne von Abschnitt 5.1: Es gilt $\mathbf{Q}^{-1} = \mathbf{Q}^T$.
Die Diagonalisierung nimmt damit die besonders einfache Form
$\mathbf{D} = \mathbf{Q}^T\mathbf{A}\mathbf{Q}$ an, ohne dass eine
Matrixinverse explizit berechnet werden muss.

```{dropdown} Video "Matrix diagonalisieren" von MathePeter
<iframe width="1020" height="574" src="https://www.youtube.com/embed/KmFq0Pl2nxM"
title="Matrix diagonalisieren + Matrixpotenzen Einfach Erklärt!"
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media;
gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Wann schlägt die Diagonalisierung fehl? Der Spektralsatz

*Ist jede Matrix diagonalisierbar?* Nein. In Abschnitt 5.3 haben wir die
Matrix $\mathbf{B} = \begin{pmatrix} 3 & 1 \\ 0 & 3 \end{pmatrix}$ gesehen,
deren Eigenwert $\lambda = 3$ algebraische Vielfachheit $m_3 = 2$ hat, aber
nur geometrische Vielfachheit $d_3 = 1$. Es gibt nicht genug linear
unabhängige Eigenvektoren, um eine invertierbare Matrix $\mathbf{V}$
aufzustellen. Die Diagonalisierungsformel ist dann nicht anwendbar.

Für den Maschinenbau entscheidend ist, dass dieser Fall bei allen physikalisch
relevanten Tensoren niemals auftreten kann:

```{admonition} Spektralsatz für symmetrische Matrizen
:class: note
Jede symmetrische Matrix $\mathbf{A} \in \mathbb{R}^{n \times n}$ ist
diagonalisierbar. Die Transformationsmatrix $\mathbf{V}$ kann stets so gewählt
werden, dass ihre Spalten paarweise orthonormal sind. In diesem Fall ist
$\mathbf{V} = \mathbf{Q}$ eine orthogonale Matrix mit
$\mathbf{Q}^{-1} = \mathbf{Q}^T$, und es gilt:

\begin{equation*}
\mathbf{D} = \mathbf{Q}^T\mathbf{A}\mathbf{Q},
\qquad
\mathbf{A} = \mathbf{Q}\mathbf{D}\mathbf{Q}^T.
\end{equation*}
```

Spannungstensor, Trägheitstensor, Massenmatrix und Steifigkeitsmatrix sind
allesamt symmetrisch. Der Spektralsatz garantiert, dass für all diese Matrizen
die Hauptachsentransformation immer gelingt: Es gibt immer ein Koordinatensystem,
in dem der Tensor diagonal ist und die physikalisch relevanten Größen direkt auf
der Diagonalen abgelesen werden können.

## Zusammenfassung und Ausblick

Symmetrische Matrizen haben zwei außergewöhnliche Eigenschaften: Alle
Eigenwerte sind reell, und Eigenvektoren zu verschiedenen Eigenwerten stehen
stets senkrecht aufeinander. Diese Symmetrieeigenschaft ist die Grundlage der
Diagonalisierung: Durch die Transformation $\mathbf{D} = \mathbf{Q}^T\mathbf{A}\mathbf{Q}$
mit der orthogonalen Eigenvektormatrix $\mathbf{Q}$ wird jede symmetrische
Matrix auf Diagonalgestalt gebracht. Der Spektralsatz garantiert, dass das
für alle physikalischen Tensoren im Maschinenbau immer gelingt. Im nächsten
Abschnitt wenden wir dieses Werkzeug auf drei konkrete Ingenieurprobleme an:
die Hauptträgheitsmomente eines Balkenprofils, die Hauptspannungen in einem
belasteten Bauteil und die Eigenfrequenzen eines Schwingungssystems.
