# Plan: Semesterstruktur und Umbau Sprint 02

Stand: 2026-10-09

## Rahmenbedingungen

- 14 Wochen, 4 SWS, 5 ECTS (150 h). Die Kollegin hat 15 Wochen, also fünf Sprints
  zu je drei Wochen.
- Verbindlich ist nur das Modulhandbuch (`~/TH_Mannheim/lectures/mathematik03_de/MAT3_Modulhandbuch.pdf`).
- Gemeinsame Materialbasis mit der Kollegin (gegenseitige Vertretung): dieselben
  fünf Booklets, dieselbe Reihenfolge, dieselben Sprintgrenzen. Unterschied nur
  im Tempo. Inhalte außerhalb des Modulhandbuchs werden nicht gelöscht, sondern
  in Skript und Booklet als **Vertiefung** gekennzeichnet.
- Ein Skriptkapitel pro Woche; vier Dateien pro Kapitel, drei inhaltliche H2 pro
  Datei.

## Semesterplan: 3 + 4 + 2 + 3 + 2 Wochen

| Wochen | Sprint | Kapitel | Vertiefung (nicht im Modulhandbuch) | Sterne/Woche | Fähnchen/Woche |
| --- | --- | --- | --- | --- | --- |
| 1–3 | S01 Matrizen | 1–3 (unverändert) | – | 19 | 2,3 |
| 4–7 | S02 Anwendung Matrizen | 4–7 | – | 20 / 20 / 17 / 8 | 3,3 |
| 8–9 | S03 DGL Teil 1 | 8–9 (aus bisher 7–9) | Richtungsfelder, Euler-Verfahren | 21 | ca. 3,5 |
| 10–12 | S04 DGL Teil 2 | 10–12 (Nummern bleiben) | – | 17 | 4,0 |
| 13–14 | S05 Fourier | 13–14 (unverändert) | komplexe Fourierreihe | 12,5 | 3,5 |

Sterne = Summe der Schwierigkeitssterne der Booklet-Aufgaben; Fähnchen = Aufwand
laut Lernplan der Kollegin. Werte pro Woche ohne Vertiefung.

Begründung (Analyse 2026-10-07): Verteilt man 14 Wochen proportional zur Last,
bekommt S02 3,6 Wochen (Sterne) bzw. 3,4 (Fähnchen). Bisher (3+3+3+3+2) lagen S02
mit 4,3 und S05 mit 5,0 Fähnchen pro Woche deutlich über den anderen Sprints. S03
statt S04 auf zwei Wochen, weil S04 sonst 26 Sterne pro Woche hätte, während in S03
Richtungsfelder und Euler (8 Aufgaben, 4 Fähnchen) außerhalb des Modulhandbuchs
liegen.

## Sprint 02: Kapitel 4–7 (Wochen 4–7)

Die vier Abschnitte des umsortierten Booklets entsprechen genau den vier Wochen.
Aufgabennummern unten sind die **neuen** Nummern im Booklet.

### Woche 4, Kapitel 4: Lineare Abbildungen (Booklet-Abschnitt 1, 20 Sterne)

| Datei | Quelle | H2-Abschnitte | Aufgaben |
| --- | --- | --- | --- |
| 4.1 Lineare Abbildungen in 2D und 3D | 4.1 | Was macht eine Matrix mit einem Vektor? · Wie verändern Matrizen die Ebene? · Was ändert sich im Raum? | 1–4 |
| 4.2 Definition und Eigenschaften | 4.2 + neu | Was macht eine Abbildung linear? · Welche Abbildungen sind nicht linear? · Wie wird eine Verschiebung doch zur Matrixmultiplikation? | 5 |
| 4.3 Kern und lineare Unabhängigkeit | 4.3 + neu | Welche Vektoren verschwinden? · Wie berechnen wir den Kern? · Wann sind Vektoren linear unabhängig? | 6–9 |
| 4.4 Bild, Rang und Dimensionsformel | 4.4 | Welche Ausgabevektoren sind erreichbar? · Wie hängen Rang und Kern zusammen? · Wann ist ein Gleichungssystem lösbar? | 10–13 |

- 4.2 neu: **homogene Koordinaten** (Modulhandbuch, fehlt bisher). Anknüpfung an
  die Translation als Gegenbeispiel. Superpositionsprinzip in den ersten Abschnitt.
  Booklet hat dazu keine Aufgabe (mit Kollegin abstimmen).
- 4.3 neu: formale Definition lineare Unabhängigkeit über $V\vec\lambda = \vec 0$,
  also linear unabhängig genau dann, wenn $\text{Kern}(V) = \{\vec 0\}$. Rückverweis
  auf 3.4 (dort nur informell, Determinantenkriterium nur quadratisch). Beispiel:
  drei Vektoren im $\mathbb{R}^4$.
- Streichen: 4.3 „Geometrische Bedeutung und Anwendungen“; 4.2 drittes Video.
- Übersichtstabellen in 4.1 und 4.4 in den letzten Abschnitt integrieren.
- 4.1 ergänzt (2026-10-07, wegen Aufgaben 1, 3, 4 und Modulhandbuch „Drehung“):
  Drehung um $90^\circ$ als $\mathbf{R}$ (fünftes Teilbild in
  `abbildungen_einheitsquadrat`); Hintereinanderausführung als Matrixprodukt in
  Abschnitt 2 (Scherung $\mathbf{D}$, Spiegelung $\mathbf{C}$,
  $\mathbf{C}\mathbf{D} \neq \mathbf{D}\mathbf{C}$, Produktregel, Inverse als
  Umkehrabbildung); Tabelle mit Streckfaktoren $s_1, s_2, s_3$. Folgen: 4.2
  (homogene Koordinaten) und 5.4 (Reihenfolge der Drehungen) auf die
  Hintereinanderausführung in 4.1 zurückverweisen, 5.4 greift $\mathbf{R}$ als
  $R(90^\circ)$ auf. Abschnitt 2 ist jetzt der längste (ca. 170 Zeilen).
- 4.2 umgebaut (2026-10-07): Superposition und Rekonstruktion aus zwei
  Bildvektoren im ersten Abschnitt (4.3 verweist darauf), $F(\vec 0) = \vec 0$
  eröffnet den zweiten. Dritter Abschnitt neu: Verschiebung $\vec t = (1, 2)^{\top}$
  als $\mathbf{B}$, gedeutet als Scherung des $\mathbb{R}^3$; $\mathbf{A}$ als
  $\hat{\mathbf{A}}$; $\mathbf{B}\hat{\mathbf{A}}$ und $\hat{\mathbf{A}}\mathbf{B}$
  mit $\mathbf{A}\vec t$ in der letzten Spalte; Stolperfalle zu den drei
  Bedeutungen von „homogen“. 5.4 kann auf die homogenen Koordinaten
  zurückverweisen (4.2 sagt nur, dass sich Drehungen und Verschiebungen damit
  kombinieren lassen, ohne ein Versprechen für 5.4).
- 4.3 (2026-10-07): Planpunkte waren schon umgesetzt. Ergänzt: Ablesen der
  Abhängigkeit über die Zeilen von $\mathbf{V}$ (für Aufg. 9a, eigenes Beispiel
  in der Ebene $y = 2x$), „geschlossener Polygonzug“ wie in Aufg. 8,
  Rückverweis Gauß vs. Gauß-Jordan (2.2) präzisiert, Video 3Blue1Brown
  „Linear combinations, span, and basis vectors“.
- 4.4 neu geschrieben (2026-10-07): durchgehendes Beispiel $\mathbf{B}$ aus 4.3
  (Bild $= \langle \vec b_1, \vec b_2\rangle$, Ebene $r_1 + r_2 - 3r_3 = 0$);
  eingeführt: lineare Hülle $\langle\ldots\rangle$, Dimension (maximale Anzahl
  linear unabhängiger Vektoren), Rang über Pivotelemente, Dimensionsformel mit
  Begründung über Pivot- und freie Spalten, Lösungsmenge
  $\vec x_p + \text{Kern}$ (für $\vec r = (6,3,3)^{\top}$ enthält sie
  $(1,1,1)^{\top}$). MB-Bezüge aus den Abschnitten entfernt. Tabelle mit vier
  Rangfällen im dritten Abschnitt. 5.1 soll lineare Hülle und Dimension nicht
  neu definieren, sondern zurückverweisen; 6.4 kann auf die Dimensionsformel
  verweisen (4.4 kündigt das für Kapitel 6 an).

### Woche 5, Kapitel 5: Basis, orthogonale Matrizen und Drehungen (Abschnitt 2, 20 Sterne)

| Datei | Quelle | H2-Abschnitte | Aufgaben |
| --- | --- | --- | --- |
| 5.1 Basis und Koordinaten | 6.1 | Was ist eine Basis? · Wie stellen wir einen Vektor in einer anderen Basis dar? · Was hat der Basiswechsel mit der Inversen zu tun? | 16–21 |
| 5.2 Orthogonale Matrizen | 5.1 (neu schreiben) | Wann ist eine Matrix orthogonal? · Was bleibt bei einer orthogonalen Abbildung erhalten? · Warum wird der Basiswechsel so einfach? | 14, 15 (Warm-up), 22–24 |
| 5.3 Gram-Schmidt-Verfahren | 5.2 | unverändert | 25, 26 |
| 5.4 Drehmatrizen | 5.3 + 5.4 | Wie dreht eine Matrix die Ebene? · Wie drehen wir um die Koordinatenachsen? · Warum kommt es auf die Reihenfolge an? | 27, 28 |

- Roter Faden: Koordinaten bzgl. $V$ erfordern ein LGS; ist $V$ orthogonal, gilt
  $[\vec a]_Q = Q^{\top}\vec a$; Gram-Schmidt baut eine solche Basis; Drehungen sind
  orthogonal mit $\det = 1$.
- 5.2 neu schreiben (alte 5.1: 133 Zeilen, 2 Lernziele, kein durchgehendes Beispiel,
  `$$`-Formeln). „Umkehrschluss gilt nicht“ bei $\det = \pm 1$ ergänzen.
- Orthogonalitätsnachweis für $R(\varphi)$ nur einmal (in 5.4).
- Aus alter 6.1 streichen: „Wiederholung: Lineare Unabhängigkeit“ (jetzt 4.3),
  „Anwendungen im Maschinenbau“.

### Woche 6, Kapitel 6: Eigenwerte und Eigenvektoren (Abschnitt 3, 17 Sterne)

| Datei | Quelle | H2-Abschnitte | Aufgaben |
| --- | --- | --- | --- |
| 6.1 Eigenwerte und Eigenvektoren | 5.5 | Welche Vektoren behalten ihre Richtung? · Was bedeutet der Eigenwert geometrisch? · Warum ist der Nullvektor kein Eigenvektor? (Titel offen) | 32 |
| 6.2 Das charakteristische Polynom | 6.2 | Wie kommen wir von der Eigenwertgleichung zum Polynom? · Wie berechnen wir Eigenwerte für 2×2- und 3×3-Matrizen? · Wann können wir Eigenwerte direkt ablesen? | 29 (Warm-up), 33–37 |
| 6.3 Eigenvektoren und Eigenraum | 6.3 (Teil 1, 2) | Wie führt der Eigenwert auf den Eigenvektor? · Was ist der Eigenraum? · Wie normieren wir Eigenvektoren? (Titel offen) | 31 (Warm-up), 38–41 |
| 6.4 Algebraische und geometrische Vielfachheit | 6.3 (Teil 3) + neu | Was bedeutet ein mehrfacher Eigenwert? · Wie viele Eigenvektoren gibt es? · Wie hängen Vielfachheit und Rang zusammen? (Titel offen) | 30 (Warm-up), 42–44 |

- 6.1: MB-Abschnitte aus 5.5 („Wo begegnen uns Eigenwerte“, „Festigkeitslehre“)
  streichen, Hinweis nur in der Einleitung.
- 6.2: Stolperfalle „Drehmatrix hat keine reellen Eigenwerte“ (Rückverweis 5.4);
  dazu passen die Aufgaben 36, 37 (komplexe Eigenwerte).
- 6.4 neu: $\sum m_\lambda = n$ und $d_\lambda = n - \text{Rang}(A - \lambda E)$
  (Rückverweis auf die Dimensionsformel in 4.4).

### Woche 7, Kapitel 7: Diagonalisierung und Anwendungen (Abschnitt 4, 8 Sterne)

| Datei | Quelle | H2-Abschnitte | Aufgaben |
| --- | --- | --- | --- |
| 7.1 Diagonalisierung | 6.4 (Teil 2) + neu | Wie wird aus den Eigenvektoren eine Diagonalmatrix? · Wann ist eine Matrix diagonalisierbar? · Wie berechnen wir Matrixpotenzen? | 45–48 |
| 7.2 Symmetrische Matrizen und Spektralsatz | 6.4 (Teil 1, 3) + neu | Warum stehen die Eigenvektoren senkrecht aufeinander? · Wie vereinfacht sich die Diagonalisierung? · Was tun bei mehrfachen Eigenwerten? | – |
| 7.3 Anwendungen der Eigenwertberechnung | 6.5 (neu schreiben) | offen | – |

- 7.1: ähnliche Matrizen mit beiden Eigenschaften (gleiche Eigenwerte;
  $\vec v$ Eigenvektor von $A$ genau dann, wenn $B^{-1}\vec v$ Eigenvektor von
  $B^{-1}AB$); Kriterium mit $\sum m_\lambda = n$; $A^n = VD^nV^{-1}$.
  Durchgehendes Beispiel nicht symmetrisch, damit $V^{-1} \neq V^{\top}$ sichtbar wird.
- 7.2, 3. Abschnitt: Gram-Schmidt im Eigenraum (Versprechen aus 5.3 einlösen).
  3×3-Beispiel $\begin{pmatrix} 5&-1&2\\-1&5&2\\2&2&2 \end{pmatrix}$: Eigenvektoren
  $(-1,1,0)^{\top}$ und $(2,0,1)^{\top}$ zu $\lambda = 6$ nicht orthogonal.
- 7.3: Modulhandbuch verlangt „Anwendung der Eigenwertberechnung“. Die alte 6.5
  verweist auf nicht existierende Beispiele und setzt TM-Wissen voraus. Neu schreiben,
  sodass die Mathematik ohne Vorwissen aus anderen Fächern verständlich ist
  (Hauptachsentransformation, entkoppelte Systeme); Hauptspannungen,
  Trägheitstensor, Modalanalyse als Hinweis in der Einleitung.
- Woche 7 ist bewusst leicht: Puffer und Festigung vor den DGL.
- Booklet-Abschnitt 4 hat keine Aufgaben zu $A^n$, Spektralsatz und Anwendungen
  (mit Kollegin abstimmen).

### Offene Entscheidungen Sprint 02

1. Komplexe Eigenwerte (Aufgaben 36, 37): Empfehlung nur Stolperfalle, Aufgaben
   als Vertiefung.
2. Inhalt von 7.3.

## Sprint 03: Kapitel 8–9 (Wochen 8–9)

Geplant am 2026-10-09 nach Lektüre der alten Kapitel 7–9. Die bisherigen zehn
Dateien werden auf acht verdichtet. Grundlage ist Booklet 03 in der Fassung v2
(`booklets/Sprint03_Booklet_DGL_Teil1_v2.pdf`, Quelle `booklets_src/Sprint03_extended/`),
die als Abschnitt 5 die linearen DGL enthält. Aufgabennummern unten sind die Nummern
in v2.

Sterne (aktive Aufgaben): Grundwissen 15 (Aufg. 1–12), Richtungsfeld 2 (16), Euler 5
(19, 20), Trennung 8 (21–25), Substitution 7 (26–29), lineare DGL 12 (30–38).
Warm-ups 13–15 und 17–18 ohne Sterne. Damit 23 Sterne in Woche 8 (plus 7 Vertiefung)
und 19 in Woche 9. Die Alternative „Substitution noch in Woche 8“ hätte 30 zu 12
ergeben.

Alle alten DGL-Dateien sind noch nicht nach den aktuellen Instruktionen
überarbeitet: Abschnittsnummern im Text um eins verschoben (6.x statt 7.x usw.),
H2 „Weiteres Lernmaterial“ mit gesammelten Videos, bis zu fünf Videos pro Datei,
`$$` in Lernzielen, MB-Anwendungen in den Abschnitten. Jede Datei wird also wie
Kapitel 4 umgebaut, nicht nur verschoben.

### Woche 8, Kapitel 8: Differentialgleichungen und Trennung der Variablen (Booklet-Abschnitte 1–4, 23 Sterne + 7 Vertiefung)

| Datei | Quelle | H2-Abschnitte | Aufgaben |
| --- | --- | --- | --- |
| 8.1 Was ist eine Differentialgleichung? | 7.1 (Teil 1) | Wie wird aus einer Änderungsrate eine Gleichung? · Was ist die Ordnung einer DGL? · Was ist eine Lösung, und warum gibt es unendlich viele? | 1–4, 7–9 |
| 8.2 Anfangs- und Randwertprobleme | 7.1 (Teil 2) + neu | Wie legt eine Anfangsbedingung die Lösung fest? · Was ändert sich bei einer DGL 2. Ordnung? · Was ist ein Randwertproblem? | 5, 6, 10–12 |
| 8.3 Richtungsfelder und Euler-Verfahren (Vertiefung) | 7.2 + 7.3 | Was schreibt eine DGL in jedem Punkt vor? · Wie folgen wir einer Lösungskurve im Richtungsfeld? · Wie wird aus einem Linienelement ein Rechenschritt? | 13–15 (Warm-up), 16, 17–18 (Warm-up), 19, 20 |
| 8.4 Trennung der Variablen | 8.1 | Wann lässt sich eine DGL trennen? · Wie funktioniert das Verfahren? · Was passiert, wenn $g(y) = 0$ ist? | 21–25 |

- 8.1: Schreibweisen (Punkt, Strich, Leibniz) und explizit/implizit (Aufg. 7, 9) in den
  zweiten Abschnitt. „Grad“ streichen, partielle DGL nur in einem Satz. Biegelinie
  und Wärmeleitung höchstens als Hinweis in der Einleitung.
- 8.2 neu: Die Booklet-Aufgaben 6, 8, 10–12 brauchen DGL 2. Ordnung mit
  gegebener allgemeiner Lösung (etwa $y'' + 9y = 0$) sowie zwei Bedingungen als AWP
  und als RWP. Vorwärtsverweis auf Kapitel 11.
- 8.3: 7.2 und 7.3 zusammenlegen und als Vertiefung kennzeichnen, mit dem Hinweis,
  dass Richtungsfelder und Euler-Verfahren nicht Prüfungsstoff für CA 3 sind
  (entschieden 2026-10-09). Die Python-Zellen in 7.3 sind schon optional; prüfen,
  ob sie bleiben.
- 8.4: Anfangsbedingung in den zweiten Abschnitt, Sonderfall $g(y) = 0$ als dritter.
  Rückverweis auf 8.3 (Nullisokline) nur als Vertiefungshinweis.
- Durchgehendes Beispiel: Der Fallschirmspringer leitet die DGL aus dem zweiten
  Newtonschen Gesetz her. Prüfen, ob die DGL einfach vorgegeben wird oder ein
  Beispiel ohne Physik (etwa Abkühlung) besser passt.
- Streichen: alte 8.3 „Technische Anwendungen der Separation“ (Riementrieb,
  Torricelli). Die Tabelle „Welche Methode für welche ODE?“ steckt schon in 10.3.

### Woche 9, Kapitel 9: Substitution und lineare DGL 1. Ordnung (Booklet-Abschnitte 4 Rest + 5, 19 Sterne)

| Datei | Quelle | H2-Abschnitte | Aufgaben |
| --- | --- | --- | --- |
| 9.1 Substitution | 8.2 + neu | Warum scheitert die direkte Trennung? · Wie hilft die Substitution $u = ax + by + c$? · Wie hilft die Substitution $u = y/x$? | 26–29 |
| 9.2 Lineare DGL erkennen | 9.1 | Was macht eine DGL linear? · Homogen oder inhomogen? · Konstante oder variable Koeffizienten? | 30–34, 37, 38 |
| 9.3 Die homogene lineare DGL | 9.2 | Wie lösen wir $y' + ay = 0$ durch Trennung? · Wie lautet die Lösungsformel für beliebige Koeffizienten? · Was liefert die Formel bei variablen Koeffizienten? | 35, 36 |
| 9.4 Die inhomogene lineare DGL | 9.3 | Warum reicht die homogene Lösung nicht aus? · Wie wählen wir den Ansatz vom Typ der rechten Seite? · Was ändert sich bei einer Sinus-Störfunktion? | – |

- 9.1 neu: Substitution $u = y/x$ (Aufg. 27–29 verlangen sie, das Skript hat sie
  bisher nicht). Singuläre Lösungen nur kurz, als Stolperfalle.
- 9.4 muss in Kapitel 9 bleiben, weil 10.1 mit den Grenzen des Ansatzes beginnt.
  Booklet 03 hat dazu keine Aufgaben; die Aufgaben zum Störansatz stehen in Booklet 04,
  Abschnitt 3 (Woche 10).
- Streichen: alte 9.4 „Technische Anwendungen linearer ODEs“ (RC-Kreis, Wärmequelle).
  Modulhandbuch „Beispiele aus der Technik“ über die durchgehenden Beispiele und
  Hinweise in den Einleitungen abdecken.

### Umzug der Dateien (erledigt 2026-10-09)

Die Gliederung in `myst.yml` und die Dateien entsprechen seit 2026-10-09 schon dem
neuen Plan für Kapitel 5–9 (per `git mv`). Die Spalte „Quelle“ in den Tabellen
oben meint die alte Nummer; deren Inhalt steht jetzt bereits in der Zieldatei,
mit neuem H1-Titel und einem Hinweis `:class: warning` („Dieses Kapitel wird gerade
überarbeitet“), den auch alle Dateien von Kapitel 10–14 tragen. Beim Umbau einer
Datei den Hinweis wieder entfernen.

- Zusammengeführt: 5.4 enthält alte 5.3 und 5.4 hintereinander, 8.3 alte 7.2 und 7.3
  (Überschriften jeweils eine Ebene tiefer).
- Aufgeteilt: Der ganze Inhalt steht in der ersten Zieldatei (6.3, 7.1, 8.1); 6.4,
  7.2 und 8.2 sind Platzhalter, die nur aus dem Hinweis bestehen.
- Entfallen: alte 8.3 und 9.4, liegen als `chapter08_sec03_old.md` und
  `chapter09_sec04_old.md` im Repo.
- Bild `chap06_richtungsfeld_fallschirmspringer.svg` liegt jetzt in `chapter08/pics`.
  Applets liegen extern unter `thma_mathematik03_assets/interactive/chapter06/` und
  bleiben dort.
- 8.3 und 14.3 tragen „(Vertiefung)“ im Titel und im Hinweis „kein Prüfungsstoff“.

## Sprint 04 und 05: Kapitel 10–14 (Wochen 10–14)

Bleiben in Nummer und Zuschnitt. Zuordnung zu den Booklets:

| Woche | Kapitel | Booklet |
| --- | --- | --- |
| 10 | 10 Variation der Konstanten | 04, Abschnitte 2–3 |
| 11 | 11 Lineare DGL 2. Ordnung: homogene Lösung | 04, Abschnitt 4 |
| 12 | 12 Lineare DGL 2. Ordnung: Schwingungen und Resonanz | 04, Abschnitt 5 + Gemischte Aufgaben |
| 13 | 13 Fourierreihen I | 05, Abschnitt 1 + Anfang Abschnitt 2 |
| 14 | 14 Fourierreihen II | 05, Rest Abschnitt 2 + Abschnitt 3 (Vertiefung) |

Beim späteren Umbau zu erledigen (ändert den Zeitplan nicht):

- Booklet 04, Abschnitt 1 „Grundwissen“ enthält dieselben Aufgaben wie Booklet 03 v2,
  Abschnitt 5. Mit der Kollegin klären, ob er bleibt.
- Kapitel 10 hat nur drei Dateien.
- Abschnittsnummern im Text sind in Kapitel 10–14 um eins verschoben (10.1 nennt den
  Ansatz „Abschnitt 8.3“). Schlussüberschriften 12.4 „Zusammenfassung: Kapitel 11“ und
  14.4 „Zusammenfassung: Kapitel 12 und 13“.
- 14.3 komplexe Fourierreihe als Vertiefung kennzeichnen, mit dem Hinweis, dass sie
  nicht Prüfungsstoff für CA 4 ist (entschieden 2026-10-09).
- 11.1, 12.3, 12.4, 13.x und 14.x setzen MB-Beispiele (Schwebebahn, Kurbelwelle,
  Unwucht) als durchgehende Beispiele ein. Gegen die Instruktionen prüfen.

## Zeitplan für die Studierenden und CA

Dienstag Vorlesung, Freitag Übung. Die CA-Termine aus `admin/planung_wise26.html`
und `admin/ca_bedingungen.html` bleiben, nur der Prüfungsstoff von CA 2 und CA 3
verschiebt sich (alte DGL-Einführung von CA 2 nach CA 3).

| CA | Termin | Stoff alt | Stoff neu |
| --- | --- | --- | --- |
| CA 1 | Di 20.10.2026 | Kap. 1–4 | Kap. 1–4 (unverändert) |
| CA 2 | Di 10.11.2026 | Orth. Matrizen, Diagonalisierung, gewöhnliche DGL | Kap. 5–7 (nur noch Matrizen) |
| CA 3 | Di 01.12.2026 | Separation, lineare DGL, Variation der Konstanten | Kap. 8–10 ohne 8.3 (Richtungsfelder, Euler) |
| CA 4 | Di 12.01.2027 | Kap. 11–14 | Kap. 11–14 ohne 14.3 (komplexe Fourierreihe) |

Nachschreibetermin Fr 15.01.2027. `admin/planung_wise26.csv` ist veraltet (fünf
CAs, andere Termine) und wird nicht mehr gepflegt.

Termine für Skript und Booklets (Kapitel jeweils bis zum Dienstag der Woche online,
Booklet am Freitag davor):

| Woche | Di | Kapitel | Booklet |
| --- | --- | --- | --- |
| 5 | 20.10. | 5 Basis, orthogonale Matrizen und Drehungen | |
| 6 | 27.10. | 6 Eigenwerte und Eigenvektoren | |
| 7 | 03.11. | 7 Diagonalisierung und Anwendungen | |
| 8 | 10.11. | 8 Differentialgleichungen und Trennung der Variablen | 03 v2 am Fr 06.11. |
| 9 | 17.11. | 9 Substitution und lineare DGL 1. Ordnung | |
| 10 | 24.11. | 10 Variation der Konstanten | 04 am Fr 20.11. |
| 13 | 15.12. | 13 Fourierreihen I | 05 am Fr 11.12. |

Neue Fassungen zur Durchsicht: `admin/planung_wise26_neu.html` und
`admin/ca_bedingungen_neu.html` (Originale unverändert).

## Booklet Sprint 02 (Veröffentlichung Fr 2026-10-09)

Quelle: `~/TH_Mannheim/lectures/mathematik03_de/booklets_src/Mathe3_Booklet_Sprint02_Matrix_2/`
(kein git). Jede Aufgabe eine Datei in `Aufgaben/`, Reihenfolge über `\input` in
`main.tex`. Lösungen in denselben Dateien, Schalter `\Lsgtrue`/`\Kurzlsgtrue` in
`main.tex`.

### Erledigt am 2026-10-07

Backup der Quelle: `booklets_src/Mathe3_Booklet_Sprint02_Matrix_2_backup_2026-10-07.tar.gz`.
Neue PDFs zur Durchsicht: `booklets/Sprint02_*_neu.pdf` (alte PDFs unverändert).
Das Booklet passt ohne weitere Änderung zum Vier-Wochen-Plan.

- Aufgaben nach Skriptreihenfolge sortiert, Kommentare `% Skript x.y` in `main.tex`.
- Backlog Abschnitt 1 in Skriptreihenfolge; Basis-Teil nach `Backlogs/Basis_Backlog.tex`
  ausgelagert und in Abschnitt 2 eingebunden. Abschnitt 2 umbenannt in „Basis,
  orthogonale Matrizen und Drehmatrizen“, Einleitung ergänzt. Lernplan-Zeile
  umbenannt (Fähnchen unverändert).
- Korrigiert: S. 4 „wir“ → „wird“; S. 9 „Das Bild stellt die Anzahl …“; S. 20
  $|\vec F_A(\vec v)|$; S. 38 $\lambda_r$ → $\lambda_n$; Kasten S. 39 („Es müssen
  nicht unbedingt n linear unabhängige Eigenvektoren vorliegen“).
- Aufgaben/Lösungen (alte Nummern): Aufg. 27 Matrix $M$ falsch ausmultipliziert
  (z-x-z statt $D_x D_y D_z$), dazu Leerzeile im Mathemodus, an der die
  Langlösungen nicht mehr kompilierten; Aufg. 47 Eigenvektor $(5,3,3)^{\top}$ statt
  $(3,5,5)^{\top}$, Lösung nannte $\det \neq 0$ als Bedingung; Aufg. 48
  $V = (\vec v_1\ \vec v_2\ \vec v_3)$, Eigenvektor $(-2,1,1)^{\top}$ statt
  $(2,1,1)^{\top}$, falsche Probe.

Zuordnung alte → neue Aufgabennummer:

| Abschnitt | alt → neu |
| --- | --- |
| 1 Lineare Abbildungen | 4→1, 16→2, 17→3, 18→4, 1→5, 3→6, 7→7, 8→8, 9→9, 5→10, 6→11, 19→12, 2→13 |
| 2 Basis, orth. Matrizen, Drehmatrizen | 20→14, 21→15, 10→16, 11→17, 13→18, 12→19, 14→20, 15→21, 22→22, 26→23, 28→24, 24→25, 25→26, 23→27, 27→28 |
| 3 Eigenwerte und Eigenvektoren | 29→29, 30→30, 31→31, 35→32, 44→33, 32→34, 37→35, 36→36, 42→37, 33→38, 38→39, 39→40, 43→41, 40→42, 41→43, 34→44 |
| 4 Diagonalisierung | 45→45, 48→46, 46→47, 47→48 |

Offen: Die übrigen Lösungen sind nicht systematisch geprüft. In allen drei bisher
geöffneten Lösungen steckten Fehler.

## Abstimmung mit der Kollegin

- Korrigierte Fassung von Booklet 02 anbieten (Fehler betreffen beide).
- Kennzeichnung „Vertiefung“ für Richtungsfelder, Euler, komplexe Fourierreihe.
- Ggf. neue Aufgaben: homogene Koordinaten, $A^n$, Spektralsatz, Anwendungen.
- Booklet 03 in Fassung v2 (mit linearen DGL) verwenden; doppelter Abschnitt
  „Grundwissen“ in Booklet 04; Aufgaben zum Störansatz 1. Ordnung erst in Booklet 04.

## Status

- [x] Semesterplan 3 + 4 + 2 + 3 + 2 festgelegt (2026-10-07)
- [x] Booklet Sprint 02 umsortiert und korrigiert (Durchsicht der `_neu`-PDFs ausstehend)
- [ ] Restliche Lösungen Booklet 02 prüfen (vor Fr 2026-10-09)
- [x] Kapitel 4 umgebaut (2026-10-07, MyST-Build ohne Fehler; Commit `f545b95`)
  - [x] 4.1
  - [x] 4.2
  - [x] 4.3
  - [x] 4.4
- [ ] Kapitel 5 umgebaut
- [x] Gliederung Kapitel 5–9 umgestellt, Ordner `chapter07` (DGL) verschoben,
  Hinweis „wird überarbeitet“ ab Kapitel 5 (2026-10-09, MyST-Build ohne Warnungen)
- [ ] Kapitel 6 umgebaut
- [ ] Kapitel 7 angelegt
- [x] `myst.yml` an die neue Gliederung angepasst (2026-10-09)
- [ ] Querverweise im Text (Abschnittsnummern) in Kapitel 4–14 angepasst
- [x] Sprint 03 geplant (2026-10-09)
- [ ] Neuer Zeitplan und CA-Stoff an die Studierenden (`_neu`-Fassungen in `admin/`)
- [ ] Kapitel 8 und 9 umgebaut
- [ ] Abstimmung mit der Kollegin
