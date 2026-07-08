---
authors:
  - name: Simone Gramsch
---

# 4.4 Bild, Rang und Dimensionsformel

Im vorigen Abschnitt haben wir den Kern einer Matrix untersucht: die Menge aller
Eingabevektoren, die durch die Abbildung auf den Nullvektor fallen. Nun drehen wir
die Perspektive um und fragen: Welche Vektoren können überhaupt als Ergebnis einer
linearen Abbildung auftreten? Diese Frage führt auf zwei eng verwandte Begriffe,
das Bild und den Rang, die bestimmen, ob ein Kräftegleichgewicht in der
Strukturmechanik existiert, ob ein Reglerauftrag erfüllbar ist und ob ein
FEM-System eine Lösung besitzt.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie kennen die Definition des **Bildes** einer Matrix und können es
  geometrisch interpretieren.
* [ ] Sie wissen, dass das Bild einer Matrix durch die **Spalten der Matrix**
  aufgespannt wird.
* [ ] Sie kennen die Definition des **Rangs** als Dimension des Bildes und
  können ihn durch Auszählen linear unabhängiger Spalten bestimmen.
* [ ] Sie kennen die **Dimensionsformel** und können sie anwenden:
  \begin{equation*}
  \dim(\text{Kern}(\mathbf{A})) + \text{Rang}(\mathbf{A}) = n.
  \end{equation*}
* [ ] Sie können die Lösbarkeit eines linearen Gleichungssystems
  $\mathbf{A}\vec{x} = \vec{b}$ mit dem Kriterium $\vec{b} \in \text{Bild}(\mathbf{A})$
  beurteilen.
```

## Welche Ausgabevektoren sind erreichbar?

Wir greifen das Beispiel aus dem vorigen Abschnitt auf: die Projektionsmatrix
auf die $xy$-Ebene, die industrielle Bildverarbeitungssysteme als Kameramodell
verwenden.

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}.
\end{equation*}

Der Kern dieser Matrix ist die gesamte $z$-Achse: Alle Punkte, die senkrecht
über dem Ursprung stehen, werden auf den Nullvektor abgebildet. *Aber kann die
Kamera überhaupt jeden Punkt im $\mathbb{R}^3$ als Ausgabe erzeugen?* Für einen
beliebigen Eingabevektor $\vec{v} = \begin{pmatrix} x \\ y \\ z \end{pmatrix}$
liefert die Abbildung:

\begin{equation*}
\mathbf{A}\cdot\begin{pmatrix} x \\ y \\ z \end{pmatrix}
= \begin{pmatrix} x \\ y \\ 0 \end{pmatrix}.
\end{equation*}

Das Ergebnis hat immer eine dritte Komponente gleich null. Ein Vektor wie
$\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$ kann niemals als Ausgabe auftreten.
Kein Bildverarbeitungssystem kann einen Punkt außerhalb seiner Bildebene
rekonstruieren: Was die Kamera liefert, liegt immer in der $xy$-Ebene. Diese
Menge aller erreichbaren Ausgabevektoren heißt das **Bild** der Matrix.

```{admonition} Was ist ... das Bild einer Matrix?
:class: note
Sei $F_{\mathbf{A}}: \mathbb{R}^n \to \mathbb{R}^m$ eine lineare Abbildung
mit der Matrix $\mathbf{A} \in \mathbb{R}^{m \times n}$. Das **Bild** von
$\mathbf{A}$, geschrieben $\text{Bild}(\mathbf{A})$, ist die Menge aller
Vektoren $\vec{w} \in \mathbb{R}^m$, die als Ergebnis der Abbildung auftreten
können:

\begin{equation*}
\text{Bild}(\mathbf{A}) = \{\,\vec{w} \in \mathbb{R}^m
\mid \vec{w} = \mathbf{A}\cdot\vec{v}
\text{ für ein } \vec{v} \in \mathbb{R}^n\,\}.
\end{equation*}
```

Für unsere Projektionsmatrix ist das Bild die gesamte $xy$-Ebene: alle Vektoren
der Form $\begin{pmatrix} x \\ y \\ 0 \end{pmatrix}$ mit beliebigen
$x, y \in \mathbb{R}$.

## Das Bild wird von den Spalten aufgespannt

Wie bestimmen wir das Bild einer Matrix konkret? Der Schlüssel liegt in der
Schreibweise der Matrix-Vektor-Multiplikation als Linearkombination. Für eine
$m\times n$-Matrix $\mathbf{A} = (\vec{a}_1, \vec{a}_2, \ldots, \vec{a}_n)$
mit Spaltenvektoren $\vec{a}_j$ gilt:

\begin{equation*}
\mathbf{A}\cdot\vec{v}
= v_1\cdot\vec{a}_1 + v_2\cdot\vec{a}_2 + \cdots + v_n\cdot\vec{a}_n.
\end{equation*}

Jede mögliche Ausgabe ist also eine Linearkombination der Spalten von
$\mathbf{A}$, wobei die Einträge von $\vec{v}$ als Koeffizienten dienen.
Das Bild ist genau die Menge aller solchen Linearkombinationen, der sogenannte
**Spaltenraum** der Matrix. In der FEM ist diese Interpretation direkt erkennbar:
Die Spalten der globalen Steifigkeitsmatrix $\mathbf{K}$ sind die
Kräftevektoren, die entstehen, wenn man jeweils genau einen Freiheitsgrad um
eine Einheit auslenkt. Das Bild von $\mathbf{K}$ ist damit die Menge aller
möglichen inneren Kräftezustände der Struktur.

## Wie groß ist das Bild? Der Rang

Das Bild wird von den Spalten aufgespannt, aber nicht alle Spalten müssen dazu
beitragen: Ist eine Spalte eine Linearkombination der anderen, so liefert sie
keine neue Richtung. Die Anzahl der linear unabhängigen Spalten, also die
Dimension des Bildes, heißt der **Rang** der Matrix.

```{admonition} Was ist ... der Rang einer Matrix?
:class: note
Der **Rang** einer Matrix $\mathbf{A}$, geschrieben $\text{Rang}(\mathbf{A})$,
ist die Dimension des Bildes von $\mathbf{A}$:

\begin{equation*}
\text{Rang}(\mathbf{A}) = \dim(\text{Bild}(\mathbf{A})).
\end{equation*}

Der Rang entspricht der maximalen Anzahl linear unabhängiger Spalten (und
gleichwertig: Zeilen) der Matrix. Für eine $m\times n$-Matrix gilt stets
$\text{Rang}(\mathbf{A}) \leq \min(m, n)$.
```

Wir bestimmen Bild und Rang an zwei Beispielen.

**Beispiel 1:** Für die Matrix

\begin{equation*}
\mathbf{C} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}
\end{equation*}

trägt die mittlere Spalte (nur Nullen) nichts zum Bild bei. Die beiden übrigen
Spalten $\begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$ und
$\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$ sind linear unabhängig, daher gilt:

\begin{equation*}
\text{Bild}(\mathbf{C}) =
\left\langle \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix},
\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix} \right\rangle, \quad
\text{Rang}(\mathbf{C}) = 2.
\end{equation*}

Das Bild ist die $xz$-Ebene im $\mathbb{R}^3$.

**Beispiel 2:** Für die Matrix

\begin{equation*}
\mathbf{D} = \begin{pmatrix} 1 & 2 & 2 \\ 1 & -1 & 2 \\ 0 & 0 & 0 \\ 0 & 1 & 0
\end{pmatrix} \in \mathbb{R}^{4\times 3}
\end{equation*}

ist die dritte Spalte ein Vielfaches der ersten:
$\begin{pmatrix} 2 \\ 2 \\ 0 \\ 0 \end{pmatrix} = 2\cdot\begin{pmatrix} 1 \\ 1 \\ 0 \\ 0 \end{pmatrix}$.
Sie trägt keine neue Richtung bei. Die ersten beiden Spalten sind linear
unabhängig, daher gilt:

\begin{equation*}
\text{Bild}(\mathbf{D}) =
\left\langle \begin{pmatrix} 1 \\ 1 \\ 0 \\ 0 \end{pmatrix},
\begin{pmatrix} 2 \\ -1 \\ 0 \\ 1 \end{pmatrix} \right\rangle, \quad
\text{Rang}(\mathbf{D}) = 2.
\end{equation*}

```{dropdown} Video "Bild einer Matrix berechnen" von Loay
<iframe width="1054" height="593" src="https://www.youtube.com/embed/FD03SOlmnvM"
title="BILD einer Matrix berechnen. Einfach und schnell erklärt" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Was verbindet Kern und Bild? Die Dimensionsformel

Im vorigen Abschnitt haben wir für die Matrix $\mathbf{D}$ den Kern berechnet
und $\dim(\text{Kern}(\mathbf{D})) = 1$ erhalten. Jetzt kennen wir auch den Rang:
$\text{Rang}(\mathbf{D}) = 2$. Zusammen ergibt das $1 + 2 = 3$, genau die
Anzahl der Spalten von $\mathbf{D}$. *Ist das Zufall, oder steckt dahinter ein
allgemeines Gesetz?*

```{admonition} Was ist ... die Dimensionsformel?
:class: note
Sei $\mathbf{A} \in \mathbb{R}^{m \times n}$ eine Matrix. Dann gilt:

\begin{equation*}
\dim(\text{Kern}(\mathbf{A}))
+ \underbrace{\dim(\text{Bild}(\mathbf{A}))}_{\text{Rang}(\mathbf{A})} = n.
\end{equation*}

Die Summe aus der Dimension des Kerns und dem Rang der Matrix ergibt immer
die Anzahl $n$ der Spalten der Matrix.
```

Die Formel hat eine anschauliche Bedeutung: Von den $n$ Dimensionen des
Eingaberaums $\mathbb{R}^n$ werden $\dim(\text{Kern}(\mathbf{A}))$ Dimensionen
durch die Abbildung auf null reduziert. Diese Dimensionen gehen verloren. Die
verbleibenden $\text{Rang}(\mathbf{A})$ Dimensionen werden tatsächlich auf den
Ausgaberaum abgebildet und bilden das Bild.

Im Maschinenbau entspricht das der wohlbekannten Aussage über Freiheitsgrade und
Bindungen: Ein mechanisches System mit $n$ Koordinaten, das durch $b$ unabhängige
Bindungsgleichungen eingeschränkt wird, hat $f = n - b$ Freiheitsgrade. Das ist
genau die Dimensionsformel mit $b = \text{Rang}$ und $f = \dim(\text{Kern})$.

Die Dimensionsformel erlaubt es, eine der beiden Größen direkt aus der anderen
zu berechnen, ohne erneut ein Gleichungssystem lösen zu müssen. Für eine
invertierbare $n\times n$-Matrix gilt $\text{Rang}(\mathbf{A}) = n$, also:

\begin{equation*}
\dim(\text{Kern}(\mathbf{A})) = n - n = 0.
\end{equation*}

Der Kern enthält nur den Nullvektor, die Abbildung ist umkehrbar. Für die
Steifigkeitsmatrix in der FEM bedeutet das: Sie ist genau dann invertierbar
und das Gleichungssystem eindeutig lösbar, wenn alle Starrkörperbewegungen
durch Randbedingungen unterdrückt wurden.

## Wann ist ein Lastvektor aufnehmbar?

Eine unmittelbare Anwendung von Bild und Dimensionsformel ist die Frage nach
der Lösbarkeit linearer Gleichungssysteme. In der Strukturmechanik lautet die
Frage konkret: Kann die gegebene äußere Last $\vec{b}$ durch die inneren Kräfte
der Struktur aufgenommen werden? Das ist gleichbedeutend damit, ob das
Gleichungssystem $\mathbf{A}\vec{x} = \vec{b}$ lösbar ist.

\begin{equation*}
\mathbf{A}\cdot\vec{x} = \vec{b} \text{ ist lösbar}
\quad\Longleftrightarrow\quad
\vec{b} \in \text{Bild}(\mathbf{A}).
\end{equation*}

Das System ist genau dann lösbar, wenn $\vec{b}$ im Bild der Matrix liegt.
In der Regelungstechnik entspricht dieser Test der Steuerbarkeit: Kann ein
dynamisches System durch eine geeignete Eingabe in jeden gewünschten Zustand
überführt werden? Wenn das Bild der Eingangsmatrix den gesamten Zustandsraum
aufspannt (der Rang also maximal ist), ist das System vollständig steuerbar.
Den mathematischen Rahmen dafür werden Sie in der Vorlesung Regelungstechnik
vertiefen.

Hat $\mathbf{A}$ vollen Spaltenrang ($\text{Rang}(\mathbf{A}) = n$), ist der
Kern trivial und das Gleichungssystem hat höchstens eine Lösung. Liegt $\vec{b}$
im Bild, ist diese Lösung eindeutig. Ist der Rang kleiner als $n$, hat das
System entweder keine Lösung (wenn $\vec{b}$ nicht im Bild liegt) oder unendlich
viele (weil man zu jeder Lösung beliebige Kernvektoren addieren kann).

Als konkretes Zahlenbeispiel: Für unsere Projektionsmatrix $\mathbf{A}$ liegt
$\vec{b} = \begin{pmatrix} 3 \\ 5 \\ 0 \end{pmatrix}$ im Bild (dritte Komponente
null), während $\vec{b} = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$ nicht im
Bild liegt. Das Gleichungssystem $\mathbf{A}\vec{x} = \begin{pmatrix} 0 \\ 0 \\ 1
\end{pmatrix}$ ist unlösbar: Das Kameramodell kann keinen Punkt außerhalb der
Bildebene rekonstruieren.

```{dropdown} Video "Rang einer Matrix, Lösbarkeit von LGS" von Mathematische Methoden
<iframe width="1020" height="574" src="https://www.youtube.com/embed/UNDha90yrT0"
title="0162 Rang einer Matrix Lösbarkeit von LGS" frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;
picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Übersicht: Kern, Bild, Rang und Dimensionsformel

| Situation | $\dim(\text{Kern})$ | Rang | Bedeutung in der Praxis |
| --- | --- | --- | --- |
| Invertierbare $n\times n$-Matrix | $0$ | $n$ | Eindeutig lösbar, zum Beispiel gelagerte FEM-Struktur |
| Singuläre $n\times n$-Matrix | $\geq 1$ | $< n$ | Unendlich viele Lösungen oder unlösbar |
| Projektion auf Unterraum | $\geq 1$ | $< n$ | Dimensionsverlust, zum Beispiel Kameramodell |
| Nicht quadratisch, voller Rang | $n - m$ | $m$ | Überbestimmtes oder unterbestimmtes System |

## Zusammenfassung und Ausblick

Das Bild einer Matrix ist die Menge aller erreichbaren Ausgabevektoren: Es wird
durch die Spalten der Matrix aufgespannt, und der Rang gibt die Anzahl der linear
unabhängigen Spalten an. Die Dimensionsformel
$\dim(\text{Kern}(\mathbf{A})) + \text{Rang}(\mathbf{A}) = n$ verbindet diese
beiden Konzepte: Von den $n$ Eingabedimensionen werden einige im Kern vernichtet
und die übrigen bilden das Bild, analog zu Freiheitsgraden und Bindungen in der
Mechanik. Das Lösbarkeitsskriterium $\vec{b} \in \text{Bild}(\mathbf{A})$ ist
der Schlüssel zur Analyse von Tragwerken und Regelungssystemen auf ihre
Lösbarkeit. Im nächsten Abschnitt stellen wir das letzte Konzept dieses Kapitels
vor: die Koordinatendarstellung eines Vektors bezüglich einer anderen Basis, die
uns direkt auf das Thema Eigenwerte und Eigenvektoren in Kapitel 5 vorbereitet.
