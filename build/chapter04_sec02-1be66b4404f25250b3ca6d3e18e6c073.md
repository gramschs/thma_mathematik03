---
authors:
  - name: Simone Gramsch
---

# 4.2 Definition und Eigenschaften linearer Abbildungen

In Kapitel 4.1 haben wir Matrizen als Abbildungen kennengelernt, die Vektoren
strecken, spiegeln, scheren, drehen oder projizieren. Offen geblieben ist,
warum diese Abbildungen linear heißen und warum das Verschieben nicht
dazugehört. In diesem Kapitel lernen wir die beiden Rechenregeln kennen, die
hinter dem Namen stecken, und einen Trick, mit dem auch Verschiebungen zur
Matrixmultiplikation werden. Im Maschinenbau setzt man mit diesen Regeln zum
Beispiel die Verformung eines Bauteils unter mehreren Lasten aus den einzelnen
Lastfällen zusammen, und CAD-Programme fassen mit dem Trick Drehen und
Verschieben in einer einzigen Matrix zusammen.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, wann eine Abbildung **linear** ist, und kennen die beiden
  Eigenschaften **Homogenität** und **Additivität**.
* [ ] Sie können begründen, warum jede Abbildung
  $F_{\mathbf{A}}(\vec{v}) = \mathbf{A}\vec{v}$ linear ist.
* [ ] Sie können mit dem **Superpositionsprinzip** das Bild einer
  **Linearkombination** aus den Bildern der einzelnen Vektoren berechnen.
* [ ] Sie wissen, dass jede lineare Abbildung den Nullvektor auf den
  Nullvektor abbildet, und erkennen damit die **Verschiebung** als nicht
  lineare Abbildung.
* [ ] Sie können an den Komponenten einer Abbildung erkennen, ob sie linear
  ist.
* [ ] Sie können Verschiebungen und lineare Abbildungen der Ebene in
  **homogenen Koordinaten** als $3\times 3$-Matrizen schreiben und
  hintereinander ausführen.
```

## Was macht eine Abbildung linear?

In Kapitel 4.1 haben wir mit der Matrix

\begin{equation*}
\mathbf{A} = \begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}
\end{equation*}

die Bilder $F_{\mathbf{A}}(\vec{v}) = (5, 6)^{\top}$ von
$\vec{v} = (1, 1)^{\top}$ und $F_{\mathbf{A}}(\vec{u}) = (1, -3)^{\top}$ von
$\vec{u} = (2, -1)^{\top}$ berechnet. *Müssen wir für das Dreifache von
$\vec{v}$ wieder die Matrix mit einem Vektor multiplizieren?* Wir rechnen es
nach:

\begin{equation*}
F_{\mathbf{A}}(3\vec{v})
= \begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}
\begin{pmatrix} 3 \\ 3 \end{pmatrix}
= \begin{pmatrix} 15 \\ 18 \end{pmatrix}
= 3\begin{pmatrix} 5 \\ 6 \end{pmatrix}
= 3\,F_{\mathbf{A}}(\vec{v}).
\end{equation*}

Das Bild des dreifachen Vektors ist das Dreifache des Bildes. Es spielt also
keine Rolle, ob wir erst strecken und dann abbilden oder erst abbilden und dann
strecken. Genauso gehen wir mit der Summe $\vec{v} + \vec{u} = (3, 0)^{\top}$
vor:

\begin{equation*}
F_{\mathbf{A}}(\vec{v} + \vec{u})
= \begin{pmatrix} 2 & 3 \\ 1 & 5 \end{pmatrix}
\begin{pmatrix} 3 \\ 0 \end{pmatrix}
= \begin{pmatrix} 6 \\ 3 \end{pmatrix}
= \begin{pmatrix} 5 \\ 6 \end{pmatrix} + \begin{pmatrix} 1 \\ -3 \end{pmatrix}
= F_{\mathbf{A}}(\vec{v}) + F_{\mathbf{A}}(\vec{u}).
\end{equation*}

Auch hier liefert erst addieren und dann abbilden dasselbe wie erst abbilden
und dann addieren. Das ist kein Zufall. Für einen beliebigen Vektor
$(x, y)^{\top}$ und eine beliebige Zahl $\alpha$ steckt in jedem Summanden der
Faktor $\alpha$, und wir können ihn ausklammern:

\begin{equation*}
\mathbf{A}\begin{pmatrix} \alpha x \\ \alpha y \end{pmatrix}
= \begin{pmatrix} 2\alpha x + 3\alpha y \\ \alpha x + 5\alpha y \end{pmatrix}
= \alpha\begin{pmatrix} 2x + 3y \\ x + 5y \end{pmatrix}
= \alpha\,\mathbf{A}\begin{pmatrix} x \\ y \end{pmatrix}.
\end{equation*}

Dieses Ausklammern funktioniert für jede Matrix. Für die Summe müssen wir gar
nicht rechnen, denn Vektoren sind Matrizen mit einer Spalte, und nach dem
Distributivgesetz aus Kapitel 1.4 gilt
$\mathbf{A}(\vec{v} + \vec{u}) = \mathbf{A}\vec{v} + \mathbf{A}\vec{u}$. Genau
diese beiden Eigenschaften geben einer Abbildung den Namen linear.

```{admonition} Was macht eine Abbildung linear?
:class: note
Eine Abbildung $F: \mathbb{R}^n \to \mathbb{R}^m$ heißt **linear**, wenn sie
für alle Vektoren $\vec{v}, \vec{v}_1, \vec{v}_2 \in \mathbb{R}^n$ und alle
Zahlen $\alpha \in \mathbb{R}$ die folgenden beiden Eigenschaften besitzt.

* **Homogenität:** $F(\alpha\vec{v}) = \alpha\,F(\vec{v})$.
* **Additivität:** $F(\vec{v}_1 + \vec{v}_2) = F(\vec{v}_1) + F(\vec{v}_2)$.

Jede Abbildung $F_{\mathbf{M}}(\vec{v}) = \mathbf{M}\vec{v}$ mit einer
$m\times n$-Matrix $\mathbf{M}$ ist in diesem Sinne linear.
```

Kombinieren wir beide Eigenschaften, können wir das Bild von
$2\vec{v} - \vec{u} = (0, 3)^{\top}$ ohne die Matrix aus den bekannten Bildern
zusammensetzen:

\begin{equation*}
F_{\mathbf{A}}(2\vec{v} - \vec{u})
= 2\,F_{\mathbf{A}}(\vec{v}) - F_{\mathbf{A}}(\vec{u})
= 2\begin{pmatrix} 5 \\ 6 \end{pmatrix} - \begin{pmatrix} 1 \\ -3 \end{pmatrix}
= \begin{pmatrix} 9 \\ 15 \end{pmatrix}.
\end{equation*}

Zur Probe rechnen wir direkt mit der Matrix und erhalten die Komponenten
$2\cdot 0 + 3\cdot 3 = 9$ und $1\cdot 0 + 5\cdot 3 = 15$. Einen Ausdruck wie
$2\vec{v} - \vec{u}$, in dem wir Vektoren mit Zahlen multiplizieren und dann
addieren, nennen wir eine **Linearkombination** der Vektoren $\vec{v}$ und
$\vec{u}$. Eine lineare Abbildung verwandelt jede Linearkombination in die
entsprechende Linearkombination der Bilder. Wir dürfen die Wirkungen der
einzelnen Vektoren also getrennt berechnen und anschließend überlagern.

```{admonition} Was besagt das Superpositionsprinzip?
:class: note
Für eine lineare Abbildung $F$, Vektoren $\vec{v}_1, \ldots, \vec{v}_k$ und
Zahlen $\alpha_1, \ldots, \alpha_k$ gilt das **Superpositionsprinzip**

\begin{equation*}
F(\alpha_1\vec{v}_1 + \ldots + \alpha_k\vec{v}_k)
= \alpha_1 F(\vec{v}_1) + \ldots + \alpha_k F(\vec{v}_k).
\end{equation*}

Das Bild einer Linearkombination ist also die Linearkombination der Bilder mit
denselben Zahlen. Es folgt, wenn wir Additivität und Homogenität mehrfach
hintereinander anwenden.
```

Besonders wichtig ist das Superpositionsprinzip für die Einheitsvektoren. Jeder
Vektor $(x, y)^{\top} = x\,\vec{e}_1 + y\,\vec{e}_2$ ist eine
Linearkombination von $\vec{e}_1$ und $\vec{e}_2$. Für jede lineare Abbildung
$F$ der Ebene gilt deshalb
$F(x\,\vec{e}_1 + y\,\vec{e}_2) = x\,F(\vec{e}_1) + y\,F(\vec{e}_2)$. Nach
Kapitel 4.1 kommt genau dasselbe heraus, wenn wir die Matrix mit den Spalten
$F(\vec{e}_1)$ und $F(\vec{e}_2)$ mit $(x, y)^{\top}$ multiplizieren. Jede
lineare Abbildung lässt sich also durch eine Matrix beschreiben, und jede
Matrix liefert eine lineare Abbildung.

*Was aber, wenn wir die Bilder der Einheitsvektoren gar nicht kennen?*
Angenommen, von einer linearen Abbildung $F$ wissen wir nur, dass sie
$\vec{v} = (1, 1)^{\top}$ auf $(5, 6)^{\top}$ und $\vec{u} = (2, -1)^{\top}$ auf
$(1, -3)^{\top}$ abbildet. Wegen $\vec{v} + \vec{u} = (3, 0)^{\top}$ ist
$\vec{e}_1 = \frac{1}{3}(\vec{v} + \vec{u})$ und damit
$\vec{e}_2 = \vec{v} - \vec{e}_1$. Das Superpositionsprinzip liefert

\begin{align*}
F(\vec{e}_1) &= \tfrac{1}{3}\big(F(\vec{v}) + F(\vec{u})\big)
= \tfrac{1}{3}\begin{pmatrix} 6 \\ 3 \end{pmatrix}
= \begin{pmatrix} 2 \\ 1 \end{pmatrix}, \\
F(\vec{e}_2) &= F(\vec{v}) - F(\vec{e}_1)
= \begin{pmatrix} 5 \\ 6 \end{pmatrix} - \begin{pmatrix} 2 \\ 1 \end{pmatrix}
= \begin{pmatrix} 3 \\ 5 \end{pmatrix}.
\end{align*}

Das sind die Spalten der gesuchten Matrix, und zur Probe vergleichen wir mit
$\mathbf{A}$: Es ist genau unsere Matrix. Aus zwei Bildvektoren haben wir also
die ganze Abbildung zurückgewonnen. Mit $\vec{v}$ und $2\vec{v}$ wäre das nicht
gelungen, denn beide zeigen in dieselbe Richtung, und $\vec{e}_1$ lässt sich
aus ihnen nicht kombinieren. Welche Vektoren sich für eine solche
Rekonstruktion eignen, klären wir in Kapitel 4.3 mit dem Begriff der linearen
Unabhängigkeit.

```{dropdown} Video "Matrizen als Abbildungen - Teil 1" von Prof. Hielscher
<iframe width="878" height="725"
src="https://www.youtube.com/embed/VUeOx_gXEoU?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07"
title="Matrizen als Abbildungen - Teil 1" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

```{dropdown} Video "Matrizen als Abbildungen - Teil 2" von Prof. Hielscher
<iframe width="878" height="725"
src="https://www.youtube.com/embed/6RldoWw6L_8?list=PLlvMVb7Fec1LGxUqOpbsCwdgUZHp1It07"
title="Matrizen als Abbildungen - Teil 2" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

## Welche Abbildungen sind nicht linear?

Aus der Homogenität folgt eine einfache, aber wirkungsvolle Regel. Mit
$\alpha = 0$ erhalten wir
$F(\vec{0}) = F(0\cdot\vec{v}) = 0\cdot F(\vec{v}) = \vec{0}$. Jede lineare
Abbildung bildet also den Nullvektor auf den Nullvektor ab, und für
$F_{\mathbf{A}}$ ist das wegen $\mathbf{A}\vec{0} = \vec{0}$ offensichtlich.
Damit können wir manche Abbildungen sofort als nicht linear entlarven. Wir
betrachten die **Verschiebung** um den Vektor $\vec{t} = (1, 2)^{\top}$, die
auch Translation heißt:

\begin{equation*}
T(\vec{v}) = \vec{v} + \vec{t},
\quad\text{also}\quad
T\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} x + 1 \\ y + 2 \end{pmatrix}.
\end{equation*}

Die Abbildung $T$ schiebt jede Figur um eine Einheit nach rechts und zwei
Einheiten nach oben, ohne sie zu verzerren. Trotzdem ist sie nicht linear,
denn sie bildet den Nullvektor auf $T(\vec{0}) = \vec{t} \neq \vec{0}$ ab. An
unserem Beispiel sehen wir, dass auch die Additivität verletzt ist. Es ist
$T(\vec{v} + \vec{u}) = T(3, 0)^{\top} = (4, 2)^{\top}$, aber
$T(\vec{v}) + T(\vec{u}) = (2, 3)^{\top} + (3, 1)^{\top} = (5, 4)^{\top}$, weil
$\vec{t}$ in der Summe zweimal steckt. Eine $2\times 2$-Matrix für $T$ kann es
deshalb nicht geben, denn jede Matrix bildet $\vec{0}$ auf $\vec{0}$ ab.

```{admonition} Ist eine Abbildung linear, wenn sie den Nullvektor auf den Nullvektor abbildet?
:class: danger
Nicht unbedingt. Die Abbildung $Q(x, y) = (x^2, y)^{\top}$ erfüllt
$Q(\vec{0}) = \vec{0}$, verletzt aber die Homogenität. Für
$\vec{e}_1 = (1, 0)^{\top}$ ist $Q(2\vec{e}_1) = (4, 0)^{\top}$, aber
$2\,Q(\vec{e}_1) = (2, 0)^{\top}$. Der Test mit dem Nullvektor kann eine
Abbildung nur als nicht linear entlarven, aber nie ihre Linearität beweisen.
```

*Woran erkennen wir also, ob eine Abbildung linear ist?* Bei $F_{\mathbf{A}}$
lauten die Komponenten $2x + 3y$ und $x + 5y$. Jede Komponente ist eine Summe
von Vielfachen der Eingabekomponenten $x$ und $y$. Bei $T$ stört dagegen der
konstante Summand und bei $Q$ das Quadrat. Genau dieser Unterschied
entscheidet.

```{admonition} Woran erkennen wir eine lineare Abbildung?
:class: note
Eine Abbildung $F: \mathbb{R}^n \to \mathbb{R}^m$ ist genau dann linear, wenn
jede Komponente von $F(\vec{v})$ eine Summe von Vielfachen der Komponenten von
$\vec{v}$ ist. Dann lässt sie sich als $F(\vec{v}) = \mathbf{M}\vec{v}$
schreiben. Konstante Summanden, Potenzen und Produkte der Komponenten oder
Funktionen wie $\sin$ verhindern die Linearität.
```

Mit diesem Kriterium prüfen wir die Abbildung

\begin{equation*}
G\begin{pmatrix} x \\ y \end{pmatrix}
= \begin{pmatrix} x + 2y \\ 4y - x \end{pmatrix}.
\end{equation*}

Beide Komponenten sind Summen von Vielfachen von $x$ und $y$, also ist $G$
linear. Die Matrix finden wir wie in Kapitel 4.1 über die Bilder der
Einheitsvektoren $G(\vec{e}_1) = (1, -1)^{\top}$ und
$G(\vec{e}_2) = (2, 4)^{\top}$:

\begin{equation*}
G\begin{pmatrix} x \\ y \end{pmatrix}
= \begin{pmatrix} 1 & 2 \\ -1 & 4 \end{pmatrix}
\begin{pmatrix} x \\ y \end{pmatrix}.
\end{equation*}

Zur Probe multiplizieren wir aus und erhalten in der ersten Zeile $x + 2y$ und
in der zweiten $-x + 4y$, genau die Komponenten von $G$.

## Wie wird eine Verschiebung doch zur Matrixmultiplikation?

Dass es für die Verschiebung $T$ keine $2\times 2$-Matrix gibt, ist unbequem.
In Kapitel 4.1 haben wir mehrere Abbildungen hintereinander ausgeführt, indem
wir ihre Matrizen multipliziert haben, und genau das möchten wir auch mit
Verschiebungen tun. *Können wir $T$ trotzdem als Matrix schreiben?* Der Trick
besteht darin, jedem Punkt $(x, y)$ der Ebene eine dritte Komponente $1$
anzuhängen und mit dem Vektor $(x, y, 1)^{\top}$ zu rechnen. Dann leistet die
$3\times 3$-Matrix

\begin{equation*}
\mathbf{B} = \begin{pmatrix} 1 & 0 & 1 \\ 0 & 1 & 2 \\ 0 & 0 & 1 \end{pmatrix}
\end{equation*}

genau das Gewünschte, denn

\begin{equation*}
\mathbf{B}\begin{pmatrix} x \\ y \\ 1 \end{pmatrix}
= \begin{pmatrix} x + 1 \\ y + 2 \\ 1 \end{pmatrix}.
\end{equation*}

Die ersten beiden Komponenten sind die Koordinaten von $T(x, y)$, und die
letzte bleibt $1$. Für $\vec{v} = (1, 1)^{\top}$ rechnen wir mit $(1, 1, 1)^{\top}$
und erhalten $(2, 3, 1)^{\top}$, also den Punkt $(2, 3)$, wie es mit
$T(\vec{v}) = \vec{v} + \vec{t}$ sein muss. Die Verschiebung steckt in der
letzten Spalte von $\mathbf{B}$, und die angehängte $1$ sorgt dafür, dass sie
bei jedem Punkt genau einmal addiert wird.

*Widerspricht das nicht dem zweiten Abschnitt?* Nein, denn $\mathbf{B}$ ist
als $3\times 3$-Matrix linear und bildet den Nullvektor des $\mathbb{R}^3$ auf
sich ab. Der Ursprung der Ebene ist aber $(0, 0, 1)^{\top}$ und nicht der
Nullvektor, und ihn darf $\mathbf{B}$ auf $(1, 2, 1)^{\top}$ verschieben.
Geometrisch ist $\mathbf{B}$ eine Scherung des Raums wie $\mathbf{D}$ in
Kapitel 4.1, denn $\mathbf{B}(x, y, z)^{\top} = (x + z,\ y + 2z,\ z)^{\top}$
verschiebt jede waagerechte Ebene in der Höhe $z$ um $z\,\vec{t}$. Die Ebene in
der Höhe $1$, in der unsere Punkte liegen, rutscht also genau um $\vec{t}$.

Auch jede lineare Abbildung der Ebene lässt sich so schreiben. Wir setzen ihre
$2\times 2$-Matrix links oben ein und ergänzen die dritte Zeile und Spalte wie
bei der Einheitsmatrix, damit die angehängte $1$ erhalten bleibt.

```{admonition} Was sind ... homogene Koordinaten?
:class: note
In **homogenen Koordinaten** schreiben wir einen Punkt $(x, y)$ der Ebene als
Vektor $(x, y, 1)^{\top}$ im $\mathbb{R}^3$. Eine Verschiebung um
$\vec{t} = (t_1, t_2)^{\top}$ und eine lineare Abbildung mit der
$2\times 2$-Matrix $\mathbf{M}$ werden dann zu den $3\times 3$-Matrizen

\begin{equation*}
\begin{pmatrix} 1 & 0 & t_1 \\ 0 & 1 & t_2 \\ 0 & 0 & 1 \end{pmatrix}
\quad\text{und}\quad
\begin{pmatrix} m_{11} & m_{12} & 0 \\ m_{21} & m_{22} & 0 \\ 0 & 0 & 1 \end{pmatrix}.
\end{equation*}

Mehrere Schritte fassen wir wie in Kapitel 4.1 durch Multiplizieren zu einer
Matrix zusammen, wobei der zuerst ausgeführte Schritt rechts steht. Die letzte
Komponente des Ergebnisses ist wieder $1$, die ersten beiden sind die
Koordinaten des Bildpunkts.
```

Für unser Beispiel wird $\mathbf{A}$ zur Matrix $\hat{\mathbf{A}}$, und wir
führen erst $F_{\mathbf{A}}$ und dann die Verschiebung $T$ aus:

\begin{equation*}
\mathbf{B}\hat{\mathbf{A}}
= \begin{pmatrix} 1 & 0 & 1 \\ 0 & 1 & 2 \\ 0 & 0 & 1 \end{pmatrix}
\begin{pmatrix} 2 & 3 & 0 \\ 1 & 5 & 0 \\ 0 & 0 & 1 \end{pmatrix}
= \begin{pmatrix} 2 & 3 & 1 \\ 1 & 5 & 2 \\ 0 & 0 & 1 \end{pmatrix}.
\end{equation*}

Diese eine Matrix bildet $(1, 1, 1)^{\top}$ auf
$(2 + 3 + 1,\ 1 + 5 + 2,\ 1)^{\top} = (6, 8, 1)^{\top}$ ab. Zur Probe gehen wir
schrittweise vor: $F_{\mathbf{A}}$ bringt $\vec{v}$ nach $(5, 6)^{\top}$, und
die Verschiebung um $(1, 2)^{\top}$ führt weiter zu $(6, 8)^{\top}$. *Kommt es
auch hier auf die Reihenfolge an?* Verschieben wir zuerst und bilden danach mit
$\mathbf{A}$ ab, ergibt sich

\begin{equation*}
\hat{\mathbf{A}}\mathbf{B}
= \begin{pmatrix} 2 & 3 & 0 \\ 1 & 5 & 0 \\ 0 & 0 & 1 \end{pmatrix}
\begin{pmatrix} 1 & 0 & 1 \\ 0 & 1 & 2 \\ 0 & 0 & 1 \end{pmatrix}
= \begin{pmatrix} 2 & 3 & 8 \\ 1 & 5 & 11 \\ 0 & 0 & 1 \end{pmatrix}.
\end{equation*}

In der letzten Spalte steht jetzt $\mathbf{A}\vec{t} = (8, 11)^{\top}$ statt
$\vec{t}$, denn die Verschiebung wird von $\mathbf{A}$ mit abgebildet. Der Punkt
$(1, 1)$ landet deshalb bei $(2 + 3 + 8,\ 1 + 5 + 11) = (13, 17)$. Schrittweise
erhalten wir dasselbe, denn $T(\vec{v}) = (2, 3)^{\top}$ und
$\mathbf{A}(2, 3)^{\top} = (4 + 9,\ 2 + 15)^{\top} = (13, 17)^{\top}$. Im Raum
funktioniert der Trick genauso mit einer vierten Komponente $1$ und
$4\times 4$-Matrizen. Zusammen mit den Drehmatrizen aus Kapitel 5.4 lässt sich
so jede Kombination aus Drehungen und Verschiebungen als eine einzige Matrix
schreiben.

```{admonition} Haben homogene Koordinaten etwas mit der Homogenität zu tun?
:class: danger
Trotz des ähnlichen Namens meinen beide etwas anderes. Die Homogenität aus dem
ersten Abschnitt ist die Rechenregel $F(\alpha\vec{v}) = \alpha\,F(\vec{v})$,
homogene Koordinaten sind die Schreibweise mit der angehängten $1$. Auch das
homogene Gleichungssystem, dem wir in Kapitel 4.3 begegnen, ist ein dritter,
eigener Begriff.
```

## Zusammenfassung und Ausblick

Eine Abbildung ist linear, wenn sie homogen und additiv ist. Zusammen ergeben
beide Eigenschaften das Superpositionsprinzip, und zu jeder linearen Abbildung
gehört die Matrix mit den Bildern der Einheitsvektoren als Spalten.
Verschiebungen sind nicht linear, weil sie den Nullvektor nicht festhalten. In
homogenen Koordinaten werden sie trotzdem zu Matrizen, und mehrere Schritte
lassen sich zu einem einzigen Matrixprodukt zusammenfassen. In Kapitel 4.3
fragen wir umgekehrt, welche Vektoren eine lineare Abbildung auf den
Nullvektor abbildet. Bei $\mathbf{A}$ ist das nur der Nullvektor selbst, bei
der Projektion aus Kapitel 4.1 dagegen eine ganze Gerade. Dem
Superpositionsprinzip begegnen wir außerdem wieder, wenn wir lineare
Differentialgleichungen lösen und ihre Lösung aus einfacheren Teillösungen
zusammensetzen.
