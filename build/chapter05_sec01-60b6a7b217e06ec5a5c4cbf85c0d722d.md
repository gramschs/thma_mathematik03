# Eigenwerte: algebraische und geometrische Vielfachheit

Eigenwerte verraten uns, welche Streckfaktoren eine Matrixtransformation hat.
Aber reicht die bloße Kenntnis der Eigenwerte aus, um eine Matrix vollständig zu
verstehen? Und was passiert, wenn ein Eigenwert mehrfach auftritt? Gibt es dann
auch mehrere Eigenvektoren? Diese Fragen führen uns auf zwei Begriffe, die
entscheiden, ob eine Matrix in eine besonders einfache Form gebracht werden kann.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie kennen den Begriff der **algebraischen Vielfachheit** $m_\lambda$ eines
  Eigenwerts als Vielfachheit der zugehörigen Nullstelle des charakteristischen
  Polynoms.
* [ ] Sie kennen den Begriff der **geometrischen Vielfachheit** $d_\lambda$ eines
  Eigenwerts als Dimension des zugehörigen Eigenraums:
  $d_\lambda = \dim(\text{Kern}(\mathbf{A} - \lambda\mathbf{E}))$.
* [ ] Sie wissen, dass stets $1 \leq d_\lambda \leq m_\lambda$ gilt, und können an
  Beispielen erläutern, wann die Ungleichung strikt ist.
* [ ] Sie können für einen gegebenen Eigenwert sowohl $m_\lambda$ als auch
  $d_\lambda$ berechnen und die Ergebnisse vergleichen.
```

## Das Hauptbeispiel: Trägheitstensor eines L-Profils

In der Technischen Mechanik beschreibt der **Flächenträgheitstensor** eines
Balkenquerschnitts, wie widerstandsfähig ein Querschnitt gegen Biegung in
verschiedene Richtungen ist. Für einen Balken mit L-förmigem Querschnitt —
wie er etwa bei Stahlträgern in Brücken und Maschinenbetten verwendet wird —
lautet dieser Tensor in einem gegebenen Koordinatensystem:

\begin{equation*}
\mathbf{I} = \begin{pmatrix} 5 & 2 \\ 2 & 2 \end{pmatrix} \cdot 10^4 \,\text{mm}^4.
\end{equation*}

Die Diagonaleinträge sind die Flächenträgheitsmomente bezüglich der beiden
Koordinatenachsen, der Nebendiagonaleintrag ist das gemischte Trägheitsmoment.
Da das Koordinatensystem schräg zum Profil liegt, ist der Nebendiagonaleintrag
von Null verschieden. Die Frage des Ingenieurs lautet: *In welchen Richtungen
treten die größte und kleinste Biegesteifigkeit auf, und wie groß sind sie?*
Diese Richtungen und Werte sind genau die Eigenvektoren und Eigenwerte von
$\mathbf{I}$.

Wir berechnen das charakteristische Polynom:

\begin{equation*}
p(\lambda) = \det(\mathbf{I} - \lambda\mathbf{E}) =
(5 - \lambda)(2 - \lambda) - 2 \cdot 2 = \lambda^2 - 7\lambda + 6 =
(\lambda - 6)(\lambda - 1).
\end{equation*}

Die beiden Eigenwerte sind $\lambda_1 = 6$ und $\lambda_2 = 1$ (in Einheiten
von $10^4\,\text{mm}^4$). Beide Nullstellen sind **einfach**, das heißt, jede
tritt genau einmal als Nullstelle des charakteristischen Polynoms auf.

## Algebraische Vielfachheit

Die **algebraische Vielfachheit** $m_\lambda$ eines Eigenwerts $\lambda$ ist
die Vielfachheit, mit der $\lambda$ als Nullstelle des charakteristischen
Polynoms auftritt.

```{admonition} Was ist ... die algebraische Vielfachheit?
:class: note
Sei $p(\lambda) = \det(\mathbf{A} - \lambda\mathbf{E})$ das charakteristische
Polynom einer $n\times n$-Matrix $\mathbf{A}$. Die **algebraische Vielfachheit**
$m_\lambda$ eines Eigenwerts $\lambda$ ist die größte natürliche Zahl, für die
gilt:

\begin{equation*}
p(\lambda) = (\lambda_0 - \lambda)^{m_{\lambda}} \cdot q(\lambda),
\end{equation*}

wobei $q(\lambda)$ ein Polynom ist mit $q(\lambda_0) \neq 0$.
```

Im L-Profil-Beispiel gilt $m_{\lambda_1} = 1$ und $m_{\lambda_2} = 1$: Beide
Eigenwerte sind einfache Nullstellen. Das ist der unkomplizierte Normalfall —
zu jedem Eigenwert gibt es genau eine Hauptrichtung des Profils.

## Geometrische Vielfachheit

Kennen wir einen Eigenwert $\lambda$, berechnen wir die zugehörigen Eigenvektoren
als nichttriviale Lösungen des homogenen Gleichungssystems
$(\mathbf{A} - \lambda\mathbf{E})\vec{v} = \vec{0}$. Die Menge aller Lösungen
bildet den **Eigenraum**

\begin{equation*}
\text{Eig}_{\mathbf{A}}(\lambda) = \text{Kern}(\mathbf{A} - \lambda\mathbf{E}).
\end{equation*}

Die Dimension dieses Eigenraums — also die Anzahl der linear unabhängigen
Eigenvektoren zum Eigenwert $\lambda$ — nennen wir die **geometrische
Vielfachheit**.

```{admonition} Was ist ... die geometrische Vielfachheit?
:class: note
Die **geometrische Vielfachheit** $d_\lambda$ eines Eigenwerts $\lambda$ ist die
Dimension des zugehörigen Eigenraums:

\begin{equation*}
d_\lambda = \dim\!\left(\text{Kern}(\mathbf{A} - \lambda\mathbf{E})\right).
\end{equation*}

Sie gibt an, wie viele linear unabhängige Eigenvektoren zu $\lambda$ existieren.
```

Wir berechnen die geometrischen Vielfachheiten für unser L-Profil-Beispiel.

**Eigenraum zu $\lambda_1 = 6$:**

\begin{equation*}
\mathbf{I} - 6\mathbf{E} =
\begin{pmatrix} -1 & 2 \\ 2 & -4 \end{pmatrix}.
\end{equation*}

Das Gleichungssystem $(\mathbf{I} - 6\mathbf{E})\vec{v} = \vec{0}$ liefert
$-v_1 + 2v_2 = 0$, also $v_1 = 2v_2$. Mit dem freien Parameter $t$ ergibt sich:

\begin{equation*}
\vec{v}_1 = t\begin{pmatrix} 2 \\ 1 \end{pmatrix}, \quad t \neq 0.
\end{equation*}

Der Eigenraum ist eindimensional: $d_{\lambda_1} = 1$.

**Eigenraum zu $\lambda_2 = 1$:**

\begin{equation*}
\mathbf{I} - 1\cdot\mathbf{E} =
\begin{pmatrix} 4 & 2 \\ 2 & 1 \end{pmatrix}.
\end{equation*}

Das Gleichungssystem liefert $4v_1 + 2v_2 = 0$, also $v_2 = -2v_1$:

\begin{equation*}
\vec{v}_2 = t\begin{pmatrix} 1 \\ -2 \end{pmatrix}, \quad t \neq 0.
\end{equation*}

Auch hier ist der Eigenraum eindimensional: $d_{\lambda_2} = 1$.

Im L-Profil-Beispiel gilt also für beide Eigenwerte $d_\lambda = m_\lambda = 1$.
Das ist der günstige Fall: Zu jeder Hauptrichtung des Querschnitts gibt es
genau eine Biegeachse. Die Eigenvektoren $\vec{v}_1$ und $\vec{v}_2$ stehen
senkrecht aufeinander — eine Eigenschaft symmetrischer Matrizen, auf die wir
in Abschnitt 5.2 zurückkommen.

## Wenn ein Eigenwert mehrfach auftritt: der Kreisquerschnitt

*Was passiert, wenn ein Eigenwert mehrfach als Nullstelle auftritt?* Dann ist
entscheidend, ob auch der Eigenraum entsprechend größer wird.

Als zweites Beispiel betrachten wir einen Balken mit **kreisrundem Querschnitt**.
Ein Kreis ist rotationssymmetrisch, das heißt, die Biegesteifigkeit ist in jede
Richtung gleich groß. Der Flächenträgheitstensor hat daher die Form:

\begin{equation*}
\mathbf{K} = \begin{pmatrix} 4 & 0 \\ 0 & 4 \end{pmatrix} \cdot 10^4\,\text{mm}^4.
\end{equation*}

Das charakteristische Polynom ist:

\begin{equation*}
p(\lambda) = (4 - \lambda)^2.
\end{equation*}

Es gibt nur einen Eigenwert $\lambda = 4$, der als doppelte Nullstelle auftritt:
$m_\lambda = 2$.

Wir berechnen den Eigenraum:

\begin{equation*}
\mathbf{K} - 4\mathbf{E} = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}.
\end{equation*}

Das Gleichungssystem $(\mathbf{K} - 4\mathbf{E})\vec{v} = \vec{0}$ ist für
jeden Vektor erfüllt. Der Eigenraum ist der gesamte $\mathbb{R}^2$, also
zweidimensional: $d_\lambda = 2$.

Hier gilt $d_\lambda = m_\lambda = 2$. Das macht geometrisch Sinn: Beim
kreisrunden Querschnitt ist jede Richtung eine Hauptrichtung, denn die
Biegesteifigkeit ist überall gleich. Es gibt unendlich viele Eigenvektoren,
aber alle gehören zum selben Eigenwert.

## Die entscheidende Ungleichung

Die beiden bisherigen Beispiele zeigen den günstigen Fall $d_\lambda = m_\lambda$.
Es gilt jedoch immer nur die Ungleichung:

```{admonition} Zusammenhang zwischen algebraischer und geometrischer Vielfachheit
:class: note
Für jeden Eigenwert $\lambda$ einer quadratischen Matrix gilt stets:

\begin{equation*}
1 \leq d_\lambda \leq m_\lambda.
\end{equation*}

Die geometrische Vielfachheit ist mindestens Eins (da jeder Eigenwert mindestens
einen Eigenvektor hat) und höchstens so groß wie die algebraische Vielfachheit.
```

*Kann die Ungleichung auch strikt sein, also $d_\lambda < m_\lambda$ gelten?*
Ja — und genau das ist der problematische Fall. Wir betrachten als Gegenbeispiel
eine rein mathematische Matrix, die in der Ingenieurpraxis bei physikalischen
Tensoren nicht auftreten würde:

\begin{equation*}
\mathbf{B} = \begin{pmatrix} 3 & 1 \\ 0 & 3 \end{pmatrix}.
\end{equation*}

Das charakteristische Polynom ist $p(\lambda) = (3 - \lambda)^2$, also hat
$\lambda = 3$ die algebraische Vielfachheit $m_\lambda = 2$.

Der Eigenraum:

\begin{equation*}
\mathbf{B} - 3\mathbf{E} = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}.
\end{equation*}

Das Gleichungssystem liefert $v_2 = 0$, während $v_1$ frei ist:

\begin{equation*}
\vec{v} = t\begin{pmatrix} 1 \\ 0 \end{pmatrix}, \quad t \neq 0.
\end{equation*}

Der Eigenraum ist nur eindimensional: $d_\lambda = 1 < m_\lambda = 2$.

Zu dem doppelten Eigenwert $\lambda = 3$ existiert also nur ein einziger
(bis auf Vielfache) linear unabhängiger Eigenvektor. Eine solche Matrix heißt
**defekt**. Sie kann nicht diagonalisiert werden, was wir im nächsten Abschnitt
genauer verstehen werden.

```{admonition} Hinweis für symmetrische Matrizen
:class: tip
Für symmetrische Matrizen wie den Flächenträgheitstensor oder den
Spannungstensor tritt der defekte Fall $d_\lambda < m_\lambda$ niemals auf.
Für symmetrische Matrizen gilt stets $d_\lambda = m_\lambda$ für alle
Eigenwerte. Warum das so ist, erläutern wir in Abschnitt 5.2.
```

## Zusammenfassung und Ausblick

Die algebraische Vielfachheit $m_\lambda$ gibt an, wie oft ein Eigenwert als
Nullstelle des charakteristischen Polynoms auftritt. Die geometrische
Vielfachheit $d_\lambda$ gibt an, wie viele linear unabhängige Eigenvektoren
dazu existieren. Es gilt stets $d_\lambda \leq m_\lambda$.

Im günstigen Fall $d_\lambda = m_\lambda$ für alle Eigenwerte lässt sich die
Matrix in eine Diagonalmatrix transformieren — sie ist **diagonalisierbar**.
Im defekten Fall $d_\lambda < m_\lambda$ ist das nicht möglich. Für
symmetrische Matrizen ist der günstige Fall garantiert, was sie für
Ingenieuranwendungen besonders wertvoll macht. In Abschnitt 5.3 werden wir den
Begriff der ähnlichen Matrizen einführen, der den mathematischen Rahmen für die
Diagonalisierung liefert.
