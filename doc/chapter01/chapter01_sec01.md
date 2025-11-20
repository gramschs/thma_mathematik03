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

Im Alltag werden häufig Tabellen benutzt, um Daten zu erfassen. Beispielsweise
könnte man eine Tabelle nutzen, um die Einnahmen und Ausgaben eines jeden Monats
zu protokollieren. In den Zeilen stehen die Kategorien wie beispielsweise BAFöG,
Miete, Abo für das Fitnessstudio oder die Gesamtausgaben für Essen in dem
jeweiligen Monat. Spaltenweise werden nun die Gesamtsumme an Ausgaben oder
Einnahmen für diese Kategorie aufgeführt. Positive Zahlen stehen für die
Einnahmen, negative Zahlen für Ausgaben.

|   | Januar | Februar | März  | April  |
|---|---|---|---|---|
| BAFöG | 956.00 €| 956.00 €| 956.00 €| 956.00 €|
| Miete | -530.00 € | -530.00 € | -530.00 € | -530.00 € |
| Fitnessstudio | -24.99 € | -24.99 € | -24.99 € |-24.99 € |
| Essen | -108.74 €  | -90.56 €| -110.50 € | -95.80 €|
| Netflix |-12.99 € | -12.99 € | -17.99 € | -17.99 €|

In der Mathematik schreibt man solche Tabellen etwas kürzer, indem die
Beschriftungen der Zeilen und Spalten sowie Einheiten weggelassen werden. Die
Zahlen werden stattdessen rechteckig angeordnet und mit runden Klammern
umrandet:

\begin{equation*}
\begin{pmatrix}
956 & 956 & 956 & 956 \\
-530 & -530 & -530 & -530 \\
-24.99 & -24.99 & -24.99 & -24.99 \\
-108.74 & -90.56 & -110.50 & -95.80 \\
-12.99 & -12.99 & -17.99 & -17.99 \\
\end{pmatrix}.
\end{equation*}

Im englischsprachigen Raum werden auch eckige Klammern verwendet:

\begin{equation*}
\begin{bmatrix}
956 & 956 & 956 & 956 \\
-530 & -530 & -530 & -530 \\
-24.99 & -24.99 & -24.99 & -24.99 \\
-108.74 & -90.56 & -110.50 & -95.80 \\
-12.99 & -12.99 & -17.99 & -17.99 \\
\end{bmatrix}
\end{equation*}

In diesem Vorlesungsskript wird die Notation mit runden Klammern verwendet.
Damit kommen wir zum Fachbegriff Matrix. Eine solche rechteckige Anordnung von
Zahlen nennen wir **Matrix**. Die Mehrzahl des Wortes Matrix lautet
**Matrizen**. Der Plural ist unregelmäßig.

```{admonition}  Was ist ... eine Matrix?
:class: note
Ein rechteckig angeordnetes Zahlenschema wird in der Mathematik Matrix genannt.
```

## Bestandteile einer Matrix

Wir werden später noch sehen, dass Matrizen eine sehr kompakte Art und Weise
sind, Informationen zu kodieren. Mit Matrizen kann aber auch gerechnet werden.
Beispielsweise könnten wir nun in jeder Zeile der Matrix den Mittelwert bilden,
um die durchschnittlichen Eingaben und Ausgaben über das Jahr hinweg zu
analysieren. Bevor wir jedoch zum Rechnen mit Matrizen kommen, lernen wir
zunächst die Fachbegriffe für die einzelnen Bestandteile einer Matrix kennen.

Ein wichtiges Merkmal einer Matrix ist die Anzahl ihrer Zeilen und die Anzahl
ihrer Spalten. Im obigen Beispiel hatten wir fünf Zeilen und vier Spalten. Die
Einträge in der Matrix sind reelle Zahlen. Wir schreiben daher

\begin{equation*}
\begin{pmatrix}
956 & 956 & 956 & 956 \\
-530 & -530 & -530 & -530 \\
-24.99 & -24.99 & -24.99 & -24.99 \\
-108.74 & -90.56 & -110.50 & -95.80 \\
-12.99 & -12.99 & -17.99 & -17.99 \\
\end{pmatrix} \in \mathbb{R}^{5\times 4}
\end{equation*}

und sagen, dass diese Matrix eine $5\times 4$-Matrix ist (sprich: 5 Kreuz 4).
Die kombinierte Angabe der Anzahl Zeilen und Anzahl Spalten nennen wir
**Dimension** der Matrix. Bei der Angabe der Dimension kommt immer die Anzahl
der Zeilen zuerst und die Angabe der Spalten als zweites.

Um über einzelne Zahlen in der Matrix reden zu können, können wir ihre Position
in der Matrix angeben. Beispielsweise steht in 5. Zeile und in der 2. Spalte die
Zahl -12.99. Anstatt Position wird in der Mathematik der Fachbegriff **Index**
verwendet und der Eintrag an dieser Stelle heißt **Element**. Wir schreiben das
Element mit Zeilenindex 5 und Spaltenindex 2 als

\begin{equation*}
a_{5 2} = -12.99.
\end{equation*}

Der Zeilenindex und der Spaltenindex werden klein an den Variablennamen
geschrieben, der üblicherweise mit einem kleinen Buchstaben bezeichnet wird. Die
Angabe

\begin{equation*}
a_{5 3}
\end{equation*}

bedeutet also, dass das Element der Matrix in der 5. Zeile und 3. Spalte gemeint
ist und wir lesen ab, dass

\begin{equation*}
a_{5 3}=-17.99.
\end{equation*}

Das Netflix-Abo ist also teurer geworden. Vergleichen wir zwei Matrizen, dann
sind die beiden Matrizen **gleich**, wenn jedes Element $a_{ij}$ der ersten
Matrix $A$ mit jedem Element $b_{ij}$ der zweiten Matrix $B$ übereinstimmt.

Üblicherweise werden Matrizen mit einem großen fettgedrucktem Buchstaben
bezeichnet, so dass beispielsweise eine $3\times 2$-Matrix die folgende
allgemeine Struktur hat:

\begin{equation*}
\mathbf{A} = \begin{pmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22} \\
a_{31} & a_{32} \\
\end{pmatrix}.
\end{equation*}

Schneiden wir aus der Matrix eine ganze Zeile aus, z.B. die 4. Zeile, erhalten
wir einen Vektor

\begin{equation*}
\vec{z}_{4} = \begin{pmatrix} -108.74 & -90.56 & -110.50 & -95.80\end{pmatrix}.
\end{equation*}

Dieser Vektor wird  **Zeilenvektor** genannt. Ein **Spaltenvektor** ist eine
ganze Spalte der Matrix, z.B. die erste Spalte

\begin{equation*}
\vec{s}_{1} = \begin{pmatrix}
956 \\
-530 \\
-24.99 \\
-108.74 \\
-12.99 \\
\end{pmatrix}.
\end{equation*}

Die letzte Bezeichnung eines Bestandteils einer Matrix, die wir hier an dieser
Stelle einführen, ist der Begriff der Hauptdiagonalen. Die **Hauptdiagonale**
einer Matrix sind die Elemente, bei der Zeilenindex und Spaltenindex
übereinstimmen. In dem obigen Beispiel sind das die Elemente $a_{11}$, $a_{22}$,
$a_{33}$ und $a_{44}$, also die Zahlen 956, -530, -24.99 und -95.8.

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

Wir werden noch einige besondere Matrizen kennenlernen. Eine besondere Art von
Matrix ist die **quadratische Matrix**. Bei einer quadratischen Matrix ist die
Anzahl der Zeilen $m$ gleich der Anzahl der Spalten $n$, also $m = n$.
Beispielsweise ist die $2\times 2$-Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix}
1 & -1 \\
0.5 & 17 \\
\end{pmatrix} \in \mathbb{R}^{2\times 2}
\end{equation*}

eine quadratische Matrix.

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
