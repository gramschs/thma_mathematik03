# Was ist eine Matrix?

In diesem Kapitel werden wir zunächst den Begriff **Matrix** und die
verschiedenen Bestandteile einer Matrix kennenlernen.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie wissen, was eine **Matrix** ist.
* Sie kennen den Unterschied zwischen einem **Zeilenvektor** und einem
  **Spaltenvektor**. 
* Sie können die Teile einer Matrix benennen, d.h. Sie wissen, was die folgenden
  Begriffe bedeuten: 
    * **Element**, 
    * **Zeilenindex**, 
    * **Spaltenindex** und
    * **Hauptdiagonale**.
* Sie wissen, was die **Dimension** einer Matrix ist und wann zwei Matrizen
  **gleich** sind.
* Sie können beurteilen, ob eine Matrix **quadratisch** ist.
```

## Matrix

Im Alltag werden häufig Tabellen benutzt, um Daten zu erfassen. Vor allem im
Profisport ist es mittlerweile Standard, möglichst viele Daten im Training und
im Wettkampf zu erfassen, um die Leistungen der Sportlerinnen und Sportler zu
optimieren. Im Folgenden werden wir 3x3-Basketball betrachten, das seit 2020
olympisch ist. Zwei Basketballteams mit drei Spielern treten gegeneinander an.
Anders als beim klassischen Basketball wird nur auf einen Korb geworfen.

Wir möchten nun das Passspiel der Spieler analysieren und legen dazu eine Tabelle an.

| | Spieler 1 | Spieler 2 | Spieler 3 |
| --- | --- | --- | --- |
| **Spieler 1** | | | |
| **Spieler 2** | | | |
| **Spieler 3** | | | |

Die Pässe werden wie folgt mitprotokolliert. Passt Spieler 1 den Ball zu Spieler
3, dann machen wir in dem Feld in der erste Zeile (Spieler 1) und der dritten
Spalte (Spieler 3) einen Strich.

| | Spieler 1 | Spieler 2 | Spieler 3 |
| --- | --- | --- | --- |
| Spieler 1 | | | \| |
| Spieler 2 | | | |
| Spieler 3 | | | |

Spielt dann Spieler 3 den Ball an Spieler 2 weiter, machen wir in der dritten
Zeile und der zweiten Spalte einen Strich.

| | Spieler 1 | Spieler 2 | Spieler 3 |
| --- | --- | --- | --- |
| Spieler 1 | | | \| |
| Spieler 2 | | | |
| Spieler 3 | | \| | |

Am Ende zählen wir die Striche bzw. die Anzahl der Pässe und erhalten
beispielsweise folgende Tabelle:

| | Spieler 1 | Spieler 2 | Spieler 3 |
| --- | --- | --- | --- |
| Spieler 1 | 0 | 1 | 3 |
| Spieler 2 | 2 | 0 | 0 |
| Spieler 3 | 1 | 2 | 0 |

In der Mathematik schreibt man solche Tabellen etwas kürzer, indem die
Beschriftungen der Zeilen und Spalten sowie Einheiten weggelassen werden. Die
Zahlen werden stattdessen rechteckig angeordnet und mit runden Klammern
umrandet:

\begin{equation*}
\begin{pmatrix}
0 & 1 & 3\\
2 & 0 & 0\\
1 & 2 & 0\\
\end{pmatrix}.
\end{equation*}

In der englischsprachigen Literatur werden oft eckige Klammern verwendet:

\begin{equation*}
\begin{bmatrix}
0 & 1 & 3\\
2 & 0 & 0\\
1 & 2 & 0\\
\end{bmatrix}
\end{equation*}

In diesem Vorlesungsskript wird die Notation mit runden Klammern verwendet.
Damit kommen wir zum Fachbegriff Matrix. Eine solche rechteckige Anordnung von
Zahlen nennen wir **Matrix**. Die Mehrzahl des Wortes Matrix lautet
**Matrizen**. Der Plural ist unregelmäßig.

```{admonition}  Was ist ... eine Matrix?
:class: note
Eine rechteckige Anordnung von Zahlen wird in der Mathematik **Matrix** genannt.
```

## Bestandteile einer Matrix

Wir werden später noch sehen, dass Matrizen eine sehr kompakte Art und Weise
sind, Informationen zu kodieren. Mit Matrizen kann aber auch gerechnet werden.
Beispielsweise können wir in jeder Spalte die Summe bilden. Dadurch können wir
statistisch ermitteln, wie oft ein Spieler angespielt wurde. Bevor wir jedoch
zum Rechnen mit Matrizen kommen, lernen wir zunächst die Fachbegriffe für die
einzelnen Bestandteile einer Matrix kennen.

Ein wichtiges Merkmal einer Matrix ist die Anzahl ihrer Zeilen und die Anzahl
ihrer Spalten. Im obigen Beispiel hatten wir drei Zeilen und drei Spalten. Die
Einträge in der Matrix sind reelle Zahlen. Wir schreiben daher

\begin{equation*}
\begin{pmatrix}
0 & 1 & 3\\
2 & 0 & 0\\
1 & 2 & 0\\
\end{pmatrix} \in \mathbb{R}^{3\times 3}
\end{equation*}

und sagen, dass diese Matrix eine $3\times 3$-Matrix ist (sprich: 3 Kreuz 3).
Die kombinierte Angabe der Zeilen- und Spaltenanzahl nennen wir **Dimension**
der Matrix. Bei der Angabe der Dimension kommt immer die Anzahl der Zeilen
zuerst und die Angabe der Spalten als zweites.

Für Matrizen verwenden wir meistens Großbuchstaben, die fettgedruckt werden,
hier beispielsweise $\mathbf{A}$, weil es sich um die Anzahl der Pässe handelt:

\begin{equation*}
\mathbf{A} =
\begin{pmatrix}
0 & 1 & 3\\
2 & 0 & 0\\
1 & 2 & 0\\
\end{pmatrix}.
\end{equation*}

Als nächstes möchten wir wissen, wie viele Pässe Spieler 3 zu Spieler 2 gespielt
hat. Dazu suchen wir in der Matrix diejenige Zahl heraus, die in der 3. Zeile
und der 2. Spalte steht. In der Mathematik sagt man zu diesem Eintrag
**Element**. Die Positionen der Elemente werden durch die Angabe der
Zeilennummer und der Spaltennummer eindeutig bestimmt. Anstatt Position wird in
der Mathematik der Fachbegriff **Index** verwendet. Wir schreiben das Element
mit Zeilenindex 3 und Spaltenindex 2 als

\begin{equation*}
a_{3 2} = 2
\end{equation*}

mit einem Kleinbuchstaben (wir nehmen hier "a", weil die Matrix mit $\mathbf{A}$
bezeichnet wurde). Beispielsweise hat eine $3\times 2$-Matrix die folgende
allgemeine Struktur:

\begin{equation*}
\mathbf{A} = \begin{pmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22} \\
a_{31} & a_{32} \\
\end{pmatrix}.
\end{equation*}

Zwei Matrizen $\mathbf{A}$ und $\mathbf{B}$ sind **gleich**, wenn sie dieselbe
Dimension haben und wenn jedes Element $a_{ij}$ der ersten Matrix $\mathbf{A}$
mit jedem Element $b_{ij}$ der zweiten Matrix $\mathbf{B}$ übereinstimmt.

Schneiden wir aus der Matrix eine ganze Zeile aus, z.B. die 2. Zeile, erhalten
wir einen Vektor

\begin{equation*}
\vec{z}_{2} = \begin{pmatrix} 2 & 0 & 0\end{pmatrix}.
\end{equation*}

Damit wissen wir, zu wem der Spieler 2 gepasst hat. Dieser Vektor wird
**Zeilenvektor** genannt. Wir können aber eine solche Zeile auch als eine
$1\times 3$-Matrix interpretieren.

Wollen wir umgekehrt wissen, von wem der Spieler 2 angespielt wurde, müssen wir
die 2. Spalte betrachten:

\begin{equation*}
\vec{s}_{2} = \begin{pmatrix}
1\\
0\\
2\\
\end{pmatrix}.
\end{equation*}

Spieler 2 wurde einmal von Spieler 1 angespielt und zweimal von Spieler 3. Eine
komplette Spalte einer Matrix wird **Spaltenvektor** genannt. Auch hier können
wir die Spalte alternativ als $3\times 1$-Matrix interpretieren.

Die letzte Bezeichnung eines Bestandteils einer Matrix, die wir hier an dieser
Stelle einführen, ist der Begriff der Hauptdiagonale. Die **Hauptdiagonale**
einer Matrix besteht aus den Elementen, bei denen Zeilen- und Spaltenindex
übereinstimmen. In dem obigen Beispiel sind das die Elemente $a_{11}$, $a_{22}$
und $a_{33}$, also die Zahlen 0, 0 und 0. Da wir in unserem Beispiel die Pässe
von einem Spieler zu einem anderen Spieler mitprotokollieren, sind die Elemente
der Hauptdiagonale zunächst Null. Was diese Elemente bedeuten könnten, werden
wir später noch sehen.

Die folgende Grafik fasst die Bezeichnungen der Bestandteile einer Matrix
übersichtlich zusammen.

```{figure} pics/matrix_bezeichnungen.svg
---
class: responsive-figure-50
name: matrix_bezeichnungen
---
Bezeichnungen einer Matrix (Quelle:
Ralf Pfeifer [Wikimedia Commons](https://commons.wikimedia.org/w/index.php?curid=50327598),
Lizenz: [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/))
```

## Quadratische Matrizen

Nachdem wir nun die allgemeine Struktur einer Matrix kennengelernt haben,
betrachten wir einen besonderen Typ von Matrix. Eine besondere Art von Matrix
ist die **quadratische Matrix**. Bei einer quadratischen Matrix ist die Anzahl
der Zeilen $m$ gleich der Anzahl der Spalten $n$, also $m = n$. Beispielsweise
ist die $2\times 2$-Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix}
1 & -1 \\
0.5 & 17 \\
\end{pmatrix} \in \mathbb{R}^{2\times 2}
\end{equation*}

eine quadratische Matrix. Auch die oben eingeführte Matrix mit der Anzahl der
Pässe ist eine quadratische Matrix. Um zu verstehen, wann eine Matrix nicht
quadratisch ist, betrachten wir ein anderes Beispiel aus dem Alltag: ein
Haushaltsbuch. Protokollieren wir Eingaben und Ausgaben im ersten Quartal, so
haben wir drei Spalten (Monate) und mehr als drei Zeilen (Posten) wie in dem
folgenden Beispiel:

| | Januar | Februar | März |
| --- | --- | --- | --- |
| BAFöG | 956.00 € | 956.00 € | 956.00 € |
| Miete | -530.00 € | -530.00 € | -530.00 € |
| Fitnessstudio | -24.99 € | -24.99 € | -24.99 € |
| Essen | -108.74 € | -90.56 € | -110.50 € |
| Netflix | -12.99 € | -12.99 € | -17.99 € |

Die Tabelle als Matrix formuliert ergibt eine $5\times 3$-Matrix

$$\mathbf{H}=\begin{pmatrix}
956 & 956 & 956\\
-530 & -530 & -530 \\
-24.99 & -24.99 & -24.99 \\
-108.74 & -90.56 & -110.50\\
-12.99 & -12.99 & -17.99\\
\end{pmatrix}$$

und ist somit *keine* quadratische Matrix.

In dem folgenden Video werden der Begriff Matrix, die Bestandteile einer Matrix
und quadratische Matrizen erläutert.

```{dropdown} Video "Matrix" von Mathematische Methoden
<iframe width="560" height="315" src="https://www.youtube.com/embed/voCDFoBxvC8"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Zusammenfassung und Ausblick

In diesem Kapitel haben wir Fachbegriffe eingeführt, um eine Matrix zu
beschreiben. Mit der quadratischen Matrix haben wir einen ersten speziellen Typ
einer Matrix kennengelernt. In den nächsten Kapiteln werden wir weitere besondere
Matrizen betrachten, bevor wir zu den Rechenoperationen für Matrizen kommen.
