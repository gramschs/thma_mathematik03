# Anwendungen der Diagonalisierung

Wir haben in diesem Kapitel das Werkzeug der Diagonalisierung vollständig
entwickelt. Jetzt setzen wir es ein. Der Trägheitstensor des L-Profils und der
Spannungstensor haben uns als Leitbeispiele begleitet, und beide sind bereits
vollständig behandelt. In diesem Abschnitt fassen wir die Ergebnisse dieser
beiden Beispiele aus Ingenieurperspektive zusammen und fügen eine dritte
wichtige Anwendung hinzu: die Modalanalyse schwingender Systeme.

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können erläutern, wie die Diagonalisierung des **Trägheitstensors**
  die Hauptträgheitsmomente und Hauptträgheitsachsen eines Querschnitts liefert.
* [ ] Sie können den Zusammenhang zwischen Diagonalisierung und der Berechnung
  von **Hauptspannungen** erläutern: Die Eigenwerte des Spannungstensors sind
  die Hauptspannungen, die Eigenvektoren geben die Hauptspannungsrichtungen an.
* [ ] Sie können erläutern, wie die Diagonalisierung in der **Modalanalyse**
  eingesetzt wird: Ein gekoppeltes Schwingungssystem zerfällt in der Basis der
  Eigenvektoren in unabhängige Einzelschwingungen.
```

## Hauptträgheitsmomente und Hauptträgheitsachsen

Ein Balken mit L-förmigem Querschnitt wurde in diesem Kapitel als durchgehendes
Beispiel verwendet. Der Trägheitstensor im ursprünglichen Koordinatensystem

\begin{equation*}
\mathbf{I} = \begin{pmatrix} 5 & 2 \\ 2 & 2 \end{pmatrix} \cdot 10^4\,\text{mm}^4
\end{equation*}

hat den Nebendiagonaleintrag $2 \cdot 10^4\,\text{mm}^4$, weil die
Koordinatenachsen nicht mit den natürlichen Symmetrieachsen des Profils
übereinstimmen. Durch Diagonalisierung haben wir in Abschnitt 5.4 das
Koordinatensystem der Hauptträgheitsachsen gefunden:

\begin{equation*}
\mathbf{D} = \begin{pmatrix} 6 & 0 \\ 0 & 1 \end{pmatrix} \cdot 10^4\,\text{mm}^4.
\end{equation*}

Die Diagonaleinträge sind die **Hauptträgheitsmomente** $I_1 = 6 \cdot 10^4\,\text{mm}^4$
und $I_2 = 1 \cdot 10^4\,\text{mm}^4$. Die zugehörigen Eigenvektoren

\begin{equation*}
\vec{v}_1 = \frac{1}{\sqrt{5}}\begin{pmatrix} 2 \\ 1 \end{pmatrix}
\quad \text{und} \quad
\vec{v}_2 = \frac{1}{\sqrt{5}}\begin{pmatrix} 1 \\ -2 \end{pmatrix}
\end{equation*}

zeigen in die **Hauptträgheitsachsen**, also in die Richtungen der größten und
kleinsten Biegesteifigkeit. Um den Balken zu biegen, ist die Kraft in Richtung
$\vec{v}_2$ am wirksamsten, weil das kleinste Trägheitsmoment dort liegt.

Diese Information ist in der Praxis unverzichtbar: In der Norm DIN EN 1993
(Bemessung von Stahlbauten) werden alle Nachweise für Biegung und Knickung
bezüglich der Hauptträgheitsachsen geführt. Ohne die Diagonalisierung müsste
man mit dem ungünstigeren ursprünglichen Koordinatensystem rechnen und würde
dabei entweder auf der sicheren Seite zu konservativ oder im ungünstigen Fall
falsch liegen.

## Hauptspannungen und Hauptspannungsrichtungen

Der Spannungstensor an einem Punkt eines belasteten Bauteils beschreibt, welche
Normal- und Schubspannungen auf Schnittflächen in verschiedene Richtungen
wirken. Im Beispiel aus Abschnitt 5.2 lautete er:

\begin{equation*}
\boldsymbol{\sigma} = \begin{pmatrix} 7 & 2 \\ 2 & 4 \end{pmatrix}~\text{MPa}.
\end{equation*}

Durch Diagonalisierung haben wir in Abschnitt 5.4 die Hauptspannungen
$\sigma_1 = 8~\text{MPa}$ und $\sigma_2 = 3~\text{MPa}$ bestimmt. Die
zugehörigen Eigenvektoren geben die **Hauptspannungsrichtungen** an, also die
Schnittflächen, auf denen ausschließlich Normalspannungen und keine
Schubspannungen wirken.

*Warum ist das für die Auslegung wichtig?* Die meisten Versagenskriterien im
Maschinenbau, wie das von-Mises-Kriterium oder das Tresca-Kriterium, werden in
den Hauptspannungen formuliert. Konkret lautet die von-Mises-Vergleichsspannung
für den ebenen Spannungszustand:

\begin{equation*}
\sigma_V = \sqrt{\sigma_1^2 - \sigma_1\sigma_2 + \sigma_2^2}.
\end{equation*}

Für unser Beispiel ergibt sich:

\begin{equation*}
\sigma_V = \sqrt{8^2 - 8\cdot 3 + 3^2} = \sqrt{64 - 24 + 9} = \sqrt{49} = 7~\text{MPa}.
\end{equation*}

Diesen Wert vergleicht man mit der Streckgrenze des Werkstoffs. Die
Diagonalisierung ist hier also kein Selbstzweck, sondern der notwendige erste
Schritt vor dem Festigkeitsnachweis. In der Technischen Mechanik II werden Sie
diesen Zusammenhang für den räumlichen Spannungszustand mit einem $3\times 3$-Tensor
vertiefen.

## Modalanalyse: wenn Maschinen schwingen

Eine dritte, in der Praxis besonders wichtige Anwendung der Diagonalisierung
ist die Analyse schwingender Systeme. Jede Maschine schwingt, wenn sie in
Betrieb ist: Motoren, Pumpen, Brücken, Flugzeugtragflächen. Die Frage, bei
welchen Frequenzen Resonanz auftritt, entscheidet über Komfort, Lärm und im
Extremfall über das Versagen des Bauteils.

Wir betrachten ein einfaches Modell: zwei Massen $m_1$ und $m_2$, die über
Federn miteinander und mit einem festen Rahmen verbunden sind. Die Bewegung
beider Massen ist gekoppelt, weil die mittlere Feder beide Massen gleichzeitig
beeinflusst. Die Gleichgewichtsbedingung führt auf ein lineares
Gleichungssystem der Form

\begin{equation*}
\mathbf{K}\vec{x} = \omega^2 \mathbf{M}\vec{x},
\end{equation*}

wobei $\mathbf{K}$ die **Steifigkeitsmatrix**, $\mathbf{M}$ die **Massenmatrix**,
$\vec{x}$ der Vektor der Auslenkungen und $\omega$ die gesuchte Kreisfrequenz
ist. Das ist ein verallgemeinertes Eigenwertproblem. Für den Sonderfall gleicher
Massen $m_1 = m_2 = m$ vereinfacht es sich auf ein gewöhnliches Eigenwertproblem
für die Matrix $\mathbf{A} = \frac{1}{m}\mathbf{K}$.

Als konkretes Beispiel wählen wir $m = 1\,\text{kg}$ und die Steifigkeitsmatrix

\begin{equation*}
\mathbf{K} = \begin{pmatrix} 3 & -1 \\ -1 & 3 \end{pmatrix}~\frac{\text{N}}{\text{m}},
\end{equation*}

sodass $\mathbf{A} = \mathbf{K}$. Die Matrix ist symmetrisch, der Spektralsatz
garantiert, dass die Diagonalisierung gelingt. Wir berechnen die Eigenwerte:

\begin{equation*}
p(\lambda) = (3 - \lambda)^2 - 1 = \lambda^2 - 6\lambda + 8 = (\lambda - 4)(\lambda - 2) = 0.
\end{equation*}

Die Eigenwerte sind $\lambda_1 = 4$ und $\lambda_2 = 2$. Die zugehörigen
**Eigenkreisfrequenzen** sind:

\begin{equation*}
\omega_1 = \sqrt{\lambda_1} = 2~\frac{\text{rad}}{\text{s}}
\quad \text{und} \quad
\omega_2 = \sqrt{\lambda_2} = \sqrt{2}~\frac{\text{rad}}{\text{s}} \approx 1{,}41~\frac{\text{rad}}{\text{s}}.
\end{equation*}

Jetzt berechnen wir die Eigenvektoren. Für $\lambda_1 = 4$:

\begin{equation*}
\mathbf{A} - 4\mathbf{E} = \begin{pmatrix} -1 & -1 \\ -1 & -1 \end{pmatrix}
\quad \Rightarrow \quad
\vec{v}_1 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}.
\end{equation*}

Für $\lambda_2 = 2$:

\begin{equation*}
\mathbf{A} - 2\mathbf{E} = \begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}
\quad \Rightarrow \quad
\vec{v}_2 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}.
\end{equation*}

Diese Eigenvektoren sind die **Eigenformen** des Schwingungssystems. Sie
beschreiben, wie die beiden Massen bei der jeweiligen Eigenfrequenz relativ
zueinander schwingen. Im ersten Eigenvektor $\vec{v}_1 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}$
bewegen sich die beiden Massen in entgegengesetzte Richtungen: Die eine geht
nach links, während die andere nach rechts geht. Im zweiten Eigenvektor
$\vec{v}_2 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$ bewegen sich beide Massen
gemeinsam in dieselbe Richtung.

*Wozu hilft die Diagonalisierung hier?* Das originale System mit der Matrix
$\mathbf{A}$ beschreibt zwei gekoppelte Schwingungen: Die Bewegung von Masse 1
beeinflusst Masse 2 und umgekehrt. In der Basis der Eigenvektoren, also nach
der Transformation $\mathbf{D} = \mathbf{V}^{-1}\mathbf{A}\mathbf{V}$ mit

\begin{equation*}
\mathbf{V} = \begin{pmatrix} 1 & 1 \\ -1 & 1 \end{pmatrix}
\quad \text{und} \quad
\mathbf{D} = \begin{pmatrix} 4 & 0 \\ 0 & 2 \end{pmatrix},
\end{equation*}

zerfällt das gekoppelte System in zwei vollständig unabhängige Einzelschwingungen.
Jede Einzelschwingung lässt sich separat analysieren und lösen. Das ist der
zentrale Vorteil der Modalanalyse: Ein kompliziertes gekoppeltes System wird
durch Diagonalisierung in einfache Teilsysteme zerlegt. In der
Maschinendynamik, die Sie in höheren Semestern kennenlernen werden, bildet
dieses Prinzip die Grundlage für die rechnergestützte Schwingungsanalyse ganzer
Fahrzeuge, Turbinen und Brückentragwerke.

## Zusammenfassung

Die Diagonalisierung ist in allen drei Beispielen dasselbe mathematische
Werkzeug, aber die Interpretation der Eigenwerte und Eigenvektoren wechselt
mit dem physikalischen Kontext. Beim Trägheitstensor sind die Eigenwerte
Hauptträgheitsmomente und die Eigenvektoren Hauptachsen. Beim Spannungstensor
sind die Eigenwerte Hauptspannungen und die Eigenvektoren spannungsfreie
Schnittrichtungen. Bei der Modalanalyse sind die Wurzeln der Eigenwerte
Eigenfrequenzen und die Eigenvektoren Schwingungsformen. Das verbindende
Prinzip ist stets dasselbe: Im Koordinatensystem der Eigenvektoren wird eine
komplizierte, gekoppelte Beschreibung durch eine einfache, diagonale ersetzt.
