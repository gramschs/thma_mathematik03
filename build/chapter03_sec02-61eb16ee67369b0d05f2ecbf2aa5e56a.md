---
authors:
  - name: Simone Gramsch
---

# 3.2 Laplacescher Entwicklungssatz

In Abschnitt 3.1 haben wir Determinanten von $2\times 2$- und
$3\times 3$-Matrizen berechnet. *Aber was tun wir, wenn die Matrix größer ist?*
Die Regel von Sarrus hilft dann nicht weiter, und wir brauchen ein Verfahren,
das für jede quadratische Matrix funktioniert. Im Maschinenbau sind große
Matrizen der Normalfall, etwa wenn ein Bauteil für eine Simulation in viele
kleine Elemente zerlegt wird.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können zu einem Eintrag $a_{ij}$ die zugehörige **Untermatrix**
  $\mathbf{A}_{ij}$ bestimmen.
* [ ] Sie kennen das **Vorzeichenschema** des Entwicklungssatzes.
* [ ] Sie können die Determinante einer $n\times n$-Matrix mit dem
  **Laplaceschen Entwicklungssatz** nach einer beliebigen Zeile oder Spalte
  berechnen.
* [ ] Sie wählen die Entwicklungszeile oder -spalte so, dass möglichst wenig
  Rechenaufwand entsteht.
* [ ] Sie wissen, warum der Entwicklungssatz für große Matrizen zu aufwendig
  ist.
```

## Wie hängt eine $3\times 3$-Determinante mit $2\times 2$-Determinanten zusammen?

Wir greifen die Matrix aus Abschnitt 3.1 wieder auf:

\begin{equation*}
\mathbf{C} =
\begin{pmatrix}
2 & 1 & 3 \\
0 & -1 & 4 \\
5 & 2 & -2
\end{pmatrix},
\qquad \det(\mathbf{C}) = 23.
\end{equation*}

Mit der Regel von Sarrus haben wir sechs Produkte gebildet, drei entlang der
roten Pfeile ($4$, $20$ und $0$) und drei entlang der blauen Pfeile ($-15$, $16$
und $0$). In jedem dieser Produkte kommt genau ein Eintrag aus der ersten Zeile
vor. Wir sortieren die sechs Produkte deshalb danach, welchen Eintrag der ersten
Zeile sie enthalten, und klammern diesen Eintrag aus:

\begin{align*}
\det(\mathbf{C})
&= 2\cdot\big((-1)\cdot(-2) - 2\cdot 4\big)
- 1\cdot\big(0\cdot(-2) - 5\cdot 4\big)
+ 3\cdot\big(0\cdot 2 - 5\cdot(-1)\big) \\
&= 2\cdot(-6) - 1\cdot(-20) + 3\cdot 5 \\
&= -12 + 20 + 15 = 23.
\end{align*}

Multiplizieren wir die Klammern wieder aus, erhalten wir tatsächlich die sechs
Sarrus-Produkte: $2\cdot(-6) = 4 - 16$, dann $-1\cdot(-20) = 20 - 0$ und
schließlich $3\cdot 5 = 0 - (-15)$. Interessant ist, was in den Klammern steht.
Jede Klammer ist die Determinante einer $2\times 2$-Matrix, und zwar genau der
Matrix, die übrig bleibt, wenn wir in $\mathbf{C}$ die erste Zeile und die
Spalte des ausgeklammerten Eintrags streichen. Beim Eintrag $1$ in der zweiten
Spalte bleibt zum Beispiel

\begin{equation*}
\mathbf{C}_{12} = \begin{pmatrix} 0 & 4 \\ 5 & -2 \end{pmatrix},
\qquad
\det(\mathbf{C}_{12}) = 0\cdot(-2) - 5\cdot 4 = -20.
\end{equation*}

Die $3\times 3$-Determinante zerfällt also in drei $2\times 2$-Determinanten.
Die Vorzeichen davor wechseln dabei zwischen $+$, $-$ und $+$.

## Was ist eine Untermatrix?

Die kleinen Matrizen, die beim Streichen einer Zeile und einer Spalte
entstehen, spielen im Folgenden die Hauptrolle. Deshalb geben wir ihnen einen
Namen.

```{admonition} Was ist ... eine Untermatrix?
:class: note
Die **Untermatrix** $\mathbf{A}_{ij}$ einer $n\times n$-Matrix $\mathbf{A}$
entsteht, indem wir die $i$-te Zeile und die $j$-te Spalte von $\mathbf{A}$
streichen. Sie hat die Dimension $(n-1)\times(n-1)$. Ihre Determinante
$\det(\mathbf{A}_{ij})$ heißt **Unterdeterminante**. In anderen Büchern wird
die Untermatrix auch **Streichmatrix** genannt.
```

Für unsere Matrix $\mathbf{C}$ gehören zu den Einträgen der ersten Zeile die
drei Untermatrizen

\begin{equation*}
\mathbf{C}_{11} = \begin{pmatrix} -1 & 4 \\ 2 & -2 \end{pmatrix}, \quad
\mathbf{C}_{12} = \begin{pmatrix} 0 & 4 \\ 5 & -2 \end{pmatrix}, \quad
\mathbf{C}_{13} = \begin{pmatrix} 0 & -1 \\ 5 & 2 \end{pmatrix}.
\end{equation*}

Ihre Unterdeterminanten sind $\det(\mathbf{C}_{11}) = -6$,
$\det(\mathbf{C}_{12}) = -20$ und $\det(\mathbf{C}_{13}) = 5$. Das sind genau
die Werte, die wir oben in den Klammern gefunden haben.

## Funktioniert das auch mit anderen Zeilen und Spalten?

*Ist die erste Zeile etwas Besonderes, oder dürfen wir auch eine andere Zeile
oder Spalte wählen?* Wir probieren es mit der ersten Spalte von $\mathbf{C}$
aus, also mit den Einträgen $2$, $0$ und $5$. Auch hier multiplizieren wir jeden
Eintrag mit seiner Unterdeterminante:

\begin{align*}
\det(\mathbf{C})
&= 2\cdot\det(\mathbf{C}_{11}) - 0\cdot\det(\mathbf{C}_{21})
+ 5\cdot\det(\mathbf{C}_{31}) \\
&= 2\cdot\left|\begin{matrix} -1 & 4 \\ 2 & -2 \end{matrix}\right|
+ 5\cdot\left|\begin{matrix} 1 & 3 \\ -1 & 4 \end{matrix}\right|
= 2\cdot(-6) + 5\cdot 7 = 23.
\end{align*}

Das Ergebnis stimmt wieder. Weil $c_{21} = 0$ ist, fällt der mittlere Summand
weg, und wir mussten nur zwei Unterdeterminanten berechnen statt drei. Das
Vorzeichen vor jedem Summanden hängt davon ab, wo der Eintrag in der Matrix
steht. Es ist $+$, wenn die Summe aus Zeilen- und Spaltennummer gerade ist, und
$-$, wenn sie ungerade ist. Kurz geschrieben ist das der Faktor $(-1)^{i+j}$.
Für eine $4\times 4$-Matrix ergibt sich das folgende Vorzeichenschema, das wie
ein Schachbrett aussieht:

<!-- markdownlint-disable -->
\begin{equation*}
\begin{pmatrix}
+ & - & + & - \\
- & + & - & + \\
+ & - & + & - \\
- & + & - & +
\end{pmatrix}.
\end{equation*}
<!-- markdownlint-enable -->

Der Eintrag $c_{21}$ steht in Zeile $2$ und Spalte $1$. Wegen $2 + 1 = 3$
bekommt er das Vorzeichen $-$, und genau so haben wir oben gerechnet.

```{admonition} Was ist ... der Laplacesche Entwicklungssatz?
:class: note
Die Determinante einer $n\times n$-Matrix $\mathbf{A}$ lässt sich nach einer
beliebigen Zeile $i$ entwickeln,

\begin{equation*}
\det(\mathbf{A}) = \sum_{j=1}^{n} (-1)^{i+j}\cdot a_{ij}\cdot\det(\mathbf{A}_{ij}),
\end{equation*}

oder nach einer beliebigen Spalte $j$,

\begin{equation*}
\det(\mathbf{A}) = \sum_{i=1}^{n} (-1)^{i+j}\cdot a_{ij}\cdot\det(\mathbf{A}_{ij}).
\end{equation*}

Diese Aussage heißt **Laplacescher Entwicklungssatz**. Das Ergebnis hängt nicht
davon ab, welche Zeile oder Spalte wir wählen. Den Ausdruck
$(-1)^{i+j}\cdot\det(\mathbf{A}_{ij})$ nennt man auch **Kofaktor** des Eintrags
$a_{ij}$.
```

Für unsere Matrix $\mathbf{C}$ mit $n = 3$ und der Entwicklung nach der ersten
Zeile ($i = 1$) lautet die Summe ausgeschrieben

\begin{align*}
\det(\mathbf{C})
&= (-1)^{1+1}\cdot 2\cdot\det(\mathbf{C}_{11})
+ (-1)^{1+2}\cdot 1\cdot\det(\mathbf{C}_{12})
+ (-1)^{1+3}\cdot 3\cdot\det(\mathbf{C}_{13}) \\
&= 2\cdot(-6) - 1\cdot(-20) + 3\cdot 5 = 23.
\end{align*}

Das ist genau die Rechnung, mit der wir diesen Abschnitt begonnen haben. Neu ist
nur, dass der Entwicklungssatz nicht auf $3\times 3$-Matrizen beschränkt ist.
Bei einer $4\times 4$-Matrix führt er die Determinante auf
$3\times 3$-Determinanten zurück, die wir mit Sarrus berechnen können.

```{dropdown} Video "Determinante - Laplace Entwicklungssatz" von Mathematrick
<iframe width="560" height="315" src="https://www.youtube.com/embed/3cG0HWdmHLI?si=UT5KjVo88k9dNPoj"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Determinante berechnen (Laplace)" von MathePeter
<iframe width="1018" height="572"
src="https://www.youtube.com/embed/5TprkT5tHPo" frameborder="0" allow="accelerometer;
autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture;
web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
</iframe>
```

## Wie wählen wir die Entwicklungszeile geschickt?

Jetzt wenden wir den Entwicklungssatz auf eine $4\times 4$-Matrix an:

\begin{equation*}
\mathbf{A} = \begin{pmatrix}
1 & 2 & 0 & 3 \\
2 & 1 & 1 & 4 \\
3 & 1 & 0 & 2 \\
1 & 3 & 2 & 1
\end{pmatrix}.
\end{equation*}

*Welche Zeile oder Spalte wählen wir am besten?* Jede Null in der gewählten
Zeile oder Spalte lässt einen ganzen Summanden wegfallen und erspart uns eine
vollständige $3\times 3$-Rechnung. Die erste und die dritte Zeile enthalten je
eine Null, die dritte Spalte enthält dagegen zwei Nullen ($a_{13} = 0$ und
$a_{33} = 0$). Wir entwickeln daher nach der dritten Spalte. Laut Schachbrett
gehören zur dritten Spalte die Vorzeichen $+$, $-$, $+$ und $-$:

\begin{align*}
\det(\mathbf{A})
&= 0\cdot\det(\mathbf{A}_{13}) - 1\cdot\det(\mathbf{A}_{23})
+ 0\cdot\det(\mathbf{A}_{33}) - 2\cdot\det(\mathbf{A}_{43}) \\
&= -\det(\mathbf{A}_{23}) - 2\cdot\det(\mathbf{A}_{43}).
\end{align*}

Wir brauchen also nur zwei Untermatrizen. Für $\mathbf{A}_{23}$ streichen wir
die zweite Zeile und die dritte Spalte, für $\mathbf{A}_{43}$ die vierte Zeile
und die dritte Spalte:

\begin{equation*}
\mathbf{A}_{23} = \begin{pmatrix}
1 & 2 & 3 \\
3 & 1 & 2 \\
1 & 3 & 1
\end{pmatrix}, \quad
\mathbf{A}_{43} = \begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 4 \\
3 & 1 & 2
\end{pmatrix}.
\end{equation*}

Beide $3\times 3$-Determinanten berechnen wir mit der Regel von Sarrus. Die
ersten drei Produkte gehören zu den roten Pfeilen, die Produkte in der Klammer
zu den blauen:

\begin{align*}
\det(\mathbf{A}_{23})
&= 1\cdot 1\cdot 1 + 2\cdot 2\cdot 1 + 3\cdot 3\cdot 3
- \left(3\cdot 1\cdot 1 + 1\cdot 2\cdot 3 + 2\cdot 3\cdot 1\right)
= 32 - 15 = 17,\\
\det(\mathbf{A}_{43})
&= 1\cdot 1\cdot 2 + 2\cdot 4\cdot 3 + 3\cdot 2\cdot 1
- \left(3\cdot 1\cdot 3 + 1\cdot 4\cdot 1 + 2\cdot 2\cdot 2\right)
= 32 - 21 = 11.
\end{align*}

Einsetzen in die Entwicklung nach der dritten Spalte liefert

\begin{equation*}
\det(\mathbf{A}) = -17 - 2\cdot 11 = -39.
\end{equation*}

Hätten wir nach der ersten Zeile entwickelt, wären es drei
$3\times 3$-Determinanten gewesen. Genau diese Rechnung nutzen wir als Probe.

```{dropdown} Probe: Entwicklung nach der ersten Zeile
Die erste Zeile enthält nur eine Null ($a_{13} = 0$). Mit den Vorzeichen $+$,
$-$, $+$ und $-$ erhalten wir

\begin{equation*}
\det(\mathbf{A}) = 1\cdot\det(\mathbf{A}_{11}) - 2\cdot\det(\mathbf{A}_{12})
- 3\cdot\det(\mathbf{A}_{14}).
\end{equation*}

Die drei Untermatrizen und ihre Determinanten nach Sarrus sind

\begin{align*}
\det(\mathbf{A}_{11})
&= \left|\begin{matrix} 1 & 1 & 4 \\ 1 & 0 & 2 \\ 3 & 2 & 1 \end{matrix}\right|
= 0 + 6 + 8 - (0 + 4 + 1) = 9, \\
\det(\mathbf{A}_{12})
&= \left|\begin{matrix} 2 & 1 & 4 \\ 3 & 0 & 2 \\ 1 & 2 & 1 \end{matrix}\right|
= 0 + 2 + 24 - (0 + 8 + 3) = 15, \\
\det(\mathbf{A}_{14})
&= \left|\begin{matrix} 2 & 1 & 1 \\ 3 & 1 & 0 \\ 1 & 3 & 2 \end{matrix}\right|
= 4 + 0 + 9 - (1 + 0 + 6) = 6.
\end{align*}

Damit ist $\det(\mathbf{A}) = 1\cdot 9 - 2\cdot 15 - 3\cdot 6 = 9 - 30 - 18
= -39$. Beide Wege liefern dasselbe Ergebnis.
```

## Wie aufwendig ist der Entwicklungssatz?

Bei unserer $4\times 4$-Matrix hat die geschickte Wahl der Spalte eine ganze
$3\times 3$-Determinante eingespart. Ohne Nullen hätten wir vier
$3\times 3$-Determinanten mit je sechs Produkten gebraucht, insgesamt also
$4\cdot 6 = 24$ Produkte. Man kann zeigen, dass die vollständig entwickelte
Determinante einer $n\times n$-Matrix aus $n! = 1\cdot 2\cdot\ldots\cdot n$
Produkten besteht. Diese Zahl wächst dramatisch. Für $n = 10$ sind es bereits
$10! = 3\,628\,800$ Produkte, für $n = 20$ etwa $2{,}4\cdot 10^{18}$. Selbst ein
schneller Computer bräuchte dafür Jahre.

Für große Matrizen ist der Entwicklungssatz deshalb kein praktikables
Rechenverfahren. Er ist aber das richtige Werkzeug, wenn eine Matrix viele
Nullen enthält. *Können wir diese Nullen vielleicht selbst erzeugen?* Mit den
Zeilenumformungen aus dem Gauß-Jordan-Algorithmus in Abschnitt 2.2 kennen wir
bereits ein Verfahren, das genau das leistet. Wie sich die Determinante dabei
verändert, klären wir in Abschnitt 3.3.

```{admonition} Übung: Berechnung von Determinanten
:class: tip
Gehen Sie auf die Internetseite

> [https://matex.mint-kolleg.kit.edu/MATeX/browse.php](https://matex.mint-kolleg.kit.edu/MATeX/browse.php)

und wählen Sie dort `02 LA: Determinantenberechnung` aus. Wählen Sie dann `Mit
zufälligen Parametern starten` aus. Fangen Sie bei Stufe 1 an. Wenn Sie dreimal
hintereinander eine Aufgabe korrekt gelöst haben, gehen Sie zu Stufe 2 weiter.
Sobald Sie auf Stufe 2 dreimal hintereinander eine Aufgabe gelöst haben, gehen
Sie weiter zu Stufe 3.

Hinweis: Die Frage nach der Invertierbarkeit können Sie vorerst ignorieren.
```

## Zusammenfassung und Ausblick

Der Laplacesche Entwicklungssatz führt die Determinante einer
$n\times n$-Matrix auf Unterdeterminanten der Dimension $(n-1)\times(n-1)$
zurück. Die Vorzeichen folgen dem Schachbrettmuster $(-1)^{i+j}$, und wir
dürfen jede Zeile und jede Spalte wählen. Am wenigsten rechnen wir, wenn wir
nach der Zeile oder Spalte mit den meisten Nullen entwickeln. Die
$4\times 4$-Matrix $\mathbf{A}$ mit $\det(\mathbf{A}) = -39$ begegnet uns in
Abschnitt 3.3 wieder. Dort erzeugen wir mit Zeilenumformungen gezielt Nullen und
kommen so auch bei großen Matrizen mit wenig Aufwand zur Determinante.
