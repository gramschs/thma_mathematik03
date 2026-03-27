# Dimensionsformel

Kern und Bild einer Matrix beschreiben zwei grundlegende Aspekte einer linearen
Abbildung: Was geht verloren, und was ist erreichbar? In diesem Kapitel lernen wir
einen eleganten Zusammenhang zwischen der Dimension des Kerns und der Dimension des
Bildes kennen: die Dimensionsformel. Sie ist das mathematische Werkzeug hinter der
ingenieurmäßigen Faustregel, dass in einem System die Anzahl der Freiheitsgrade
plus die Anzahl der Bindungen gleich der Gesamtzahl der Koordinaten ist.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie kennen die **Dimensionsformel** und können sie anwenden:
  \begin{equation*}
  \dim(\text{Kern}(\mathbf{A})) + \dim(\text{Bild}(\mathbf{A})) = n,
  \end{equation*}
  wobei $n$ die Anzahl der Spalten der Matrix $\mathbf{A} \in \mathbb{R}^{m \times n}$ ist.
* Sie können aus der Dimension des Kerns die Dimension des Bildes bestimmen und
  umgekehrt.
* Sie können die Lösbarkeit eines linearen Gleichungssystems $\mathbf{A} \cdot \vec{x}
  = \vec{b}$ mit dem Kriterium $\vec{b} \in \text{Bild}(\mathbf{A})$ beurteilen.
```

## Die Dimensionsformel

Die Dimensionsformel stellt einen fundamentalen Zusammenhang zwischen dem Kern und
dem Bild einer linearen Abbildung her. Für eine Matrix $\mathbf{A} \in \mathbb{R}^{m \times n}$
gilt:

```{admonition} Was ist ... die Dimensionsformel?
:class: note
Sei $\mathbf{A} \in \mathbb{R}^{m \times n}$ eine Matrix. Dann gilt:

\begin{equation*}
\dim(\text{Kern}(\mathbf{A})) + \underbrace{\dim(\text{Bild}(\mathbf{A}))}_{\text{Rang}(\mathbf{A})} = n.
\end{equation*}

Die Summe aus der Dimension des Kerns und dem Rang der Matrix ergibt immer die
Anzahl der Spalten der Matrix.
```

Die Formel hat eine anschauliche Bedeutung: Von den $n$ Dimensionen des Eingaberaums
$\mathbb{R}^n$ werden $\dim(\text{Kern}(\mathbf{A}))$ Dimensionen durch die Abbildung
auf null reduziert. Sie gehen im Kern verloren. Die verbleibenden
$\text{Rang}(\mathbf{A})$ Dimensionen werden tatsächlich auf den Ausgaberaum
abgebildet und bilden das Bild.

Im Maschinenbau entspricht das der wohlbekannten Aussage über Freiheitsgrade und
Bindungen. Ein mechanisches System mit $n$ Koordinaten, das durch $b$ unabhängige
Bindungsgleichungen eingeschränkt wird, hat $f = n - b$ Freiheitsgrade. Das ist
genau die Dimensionsformel: $n$ Spalten insgesamt, $b = \text{Rang}$ davon liefern
das Bild, und $f = \dim(\text{Kern})$ verbleiben als freie Richtungen.

## Anwendung der Dimensionsformel

Die Dimensionsformel erlaubt es, aus einer bekannten Größe direkt die andere zu
berechnen, ohne erneut ein Gleichungssystem lösen zu müssen.

**Beispiel 1:** Wir betrachten erneut die Matrix

\begin{equation*}
\mathbf{D} = \begin{pmatrix} 1 & 2 & 2 \\ 1 & -1 & 2 \\ 0 & 0 & 0 \\ 0 & 1 & 0 \end{pmatrix}
\in \mathbb{R}^{4 \times 3}.
\end{equation*}

Aus dem vorigen Kapitel wissen wir:

\begin{equation*}
\text{Kern}(\mathbf{D}) = \left\{ t \cdot \begin{pmatrix} -2 \\ 0 \\ 1 \end{pmatrix}
\;\middle|\; t \in \mathbb{R} \right\}, \quad
\dim(\text{Kern}(\mathbf{D})) = 1.
\end{equation*}

Die Matrix hat $n = 3$ Spalten. Die Dimensionsformel liefert sofort:

\begin{equation*}
\dim(\text{Bild}(\mathbf{D})) = n - \dim(\text{Kern}(\mathbf{D})) = 3 - 1 = 2.
\end{equation*}

Das Bild wird also von zwei linear unabhängigen Vektoren aufgespannt, was wir im
vorigen Kapitel direkt bestätigt haben.

**Beispiel 2:** Für eine $3 \times 5$-Matrix $\mathbf{A}$ mit $n = 5$ Spalten sei
bekannt, dass $\text{Rang}(\mathbf{A}) = 3$ ist. Die Dimensionsformel liefert:

\begin{equation*}
\dim(\text{Kern}(\mathbf{A})) = 5 - 3 = 2.
\end{equation*}

Der Kern hat die Dimension 2: Es gibt zwei unabhängige Richtungen im $\mathbb{R}^5$,
die durch die Abbildung auf den Nullvektor fallen. In einem Mechanismus mit fünf
Koordinaten und drei unabhängigen Bindungsgleichungen entspricht das genau zwei
Freiheitsgraden.

**Beispiel 3:** Eine invertierbare $n \times n$-Matrix hat $\text{Rang}(\mathbf{A}) = n$,
da alle $n$ Spalten linear unabhängig sind. Die Dimensionsformel ergibt:

\begin{equation*}
\dim(\text{Kern}(\mathbf{A})) = n - n = 0.
\end{equation*}

Der Kern enthält nur den Nullvektor. Das bedeutet, die Abbildung ist umkehrbar und
die inverse Matrix $\mathbf{A}^{-1}$ existiert. Dies stimmt mit dem früheren
Ergebnis überein: Eine quadratische Matrix ist genau dann invertierbar, wenn ihre
Determinante von null verschieden ist. Für die Steifigkeitsmatrix in der FEM bedeutet
das: Sie ist genau dann invertierbar, wenn alle Starrkörperbewegungen durch
Randbedingungen unterdrückt wurden.

## Lösbarkeit linearer Gleichungssysteme

Die Dimensionsformel hat eine unmittelbare Anwendung in der Frage nach der Lösbarkeit
linearer Gleichungssysteme. Für das System

\begin{equation*}
\mathbf{A} \cdot \vec{x} = \vec{b}
\end{equation*}

gilt das folgende Lösbarkeitsskriterium, das direkt aus der Definition des Bildes
folgt:

\begin{equation*}
\mathbf{A} \cdot \vec{x} = \vec{b} \text{ ist lösbar} \quad \Longleftrightarrow \quad
\vec{b} \in \text{Bild}(\mathbf{A}).
\end{equation*>

Das Gleichungssystem ist genau dann lösbar, wenn der Vektor $\vec{b}$ im Bild der
Matrix liegt. Im Maschinenbau treten folgende Varianten auf:

Ist $\text{Rang}(\mathbf{A}) = n$ (voller Spaltenrang), so ist der Kern trivial und
das Gleichungssystem hat höchstens eine Lösung. Liegt $\vec{b}$ im Bild, ist diese
Lösung eindeutig. Ist der Rang kleiner als $n$, so hat das Gleichungssystem entweder
keine Lösung (wenn $\vec{b}$ nicht im Bild) oder unendlich viele Lösungen (weil man
zu jeder Lösung beliebige Kernvektoren addieren kann).

**Beispiel aus der Statik:** Betrachten wir ein einfach gestütztes Fachwerk mit der
Gleichgewichtsmatrix $\mathbf{A}$ und dem Lastvektor $\vec{b}$. Die Gleichgewichtsbedingung
$\mathbf{A} \cdot \vec{x} = \vec{b}$ hat genau dann eine eindeutige Lösung, wenn das
Fachwerk statisch bestimmt gelagert ist: $\text{Rang}(\mathbf{A}) = n$ und
$\vec{b} \in \text{Bild}(\mathbf{A})$.

## Übersicht: Kern, Bild, Rang und Dimensionsformel

| Situation | $\dim(\text{Kern})$ | $\text{Rang}$ | Ingenieurische Bedeutung |
| --- | --- | --- | --- |
| Invertierbare $n\times n$-Matrix | $0$ | $n$ | Eindeutig lösbar, z.B. gelagerte FEM-Struktur |
| Singulare $n\times n$-Matrix | $\geq 1$ | $< n$ | Unendlich viele Lösungen oder unlösbar |
| Projektion auf Unterraum | $\geq 1$ | $< n$ | Dimensionsverlust, z.B. Kameramodell |
| Nicht quadratisch, voller Rang | $n - m$ | $m$ | Überbestimmtes oder unterbestimmtes System |

## Zusammenfassung und Ausblick

Die Dimensionsformel $\dim(\text{Kern}(\mathbf{A})) + \text{Rang}(\mathbf{A}) = n$
verbindet Kern und Bild einer linearen Abbildung zu einem vollständigen Bild: Von den
$n$ Eingabedimensionen werden einige im Kern vernichtet und die übrigen bilden das
Bild. Diese Formel entspricht im Maschinenbau der Beziehung zwischen Freiheitsgraden,
Bindungen und Koordinaten. Das Lösbarkeitsskriterium $\vec{b} \in \text{Bild}(\mathbf{A})
$ ist der Schlüssel zur Analyse von Strukturen und Regelungssystemen auf ihre
Lösbarkeit. Im letzten Kapitel dieses Abschnitts lernen wir den Basiswechsel kennen,
der die Darstellung von Vektoren in verschiedenen Koordinatensystemen ermöglicht und
direkt auf das Thema Eigenwerte und Eigenvektoren im nächsten Kapitel führt.
