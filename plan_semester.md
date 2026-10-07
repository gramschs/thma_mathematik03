# Plan: Semesterstruktur und Umbau Sprint 02

Stand: 2026-10-07

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

## Sprint 03: Kapitel 8–9 (Wochen 8–9), noch zu planen

Bisherige Kapitel 7–9 (10 Dateien) auf zwei Kapitel verdichten. Grobe Idee:
Woche 8 „Was ist eine DGL?“ und Trennung der Variablen, Richtungsfeld und Euler als
Vertiefung; Woche 9 Substitution und lineare DGL 1. Ordnung. Substitution ist laut
Modulhandbuch Pflicht. Booklet S03: Grundwissen 15, Richtungsfeld 2, Euler 5,
Separation/Substitution 15, lineare DGL 10, Übersicht 2 Sterne. Vor der
Entscheidung Kapitel 7–9 lesen (eigener Chat).

Abhängigkeit: Der Ordner `chapter07` (DGL) muss umziehen, bevor das neue Kapitel 7
(Diagonalisierung) angelegt wird.

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

## Status

- [x] Semesterplan 3 + 4 + 2 + 3 + 2 festgelegt (2026-10-07)
- [x] Booklet Sprint 02 umsortiert und korrigiert (Durchsicht der `_neu`-PDFs ausstehend)
- [ ] Restliche Lösungen Booklet 02 prüfen (vor Fr 2026-10-09)
- [x] Kapitel 4 umgebaut (2026-10-07, MyST-Build ohne Fehler; noch nicht committet)
  - [x] 4.1
  - [x] 4.2
  - [x] 4.3
  - [x] 4.4
- [ ] Kapitel 5 umgebaut
- [ ] Ordner `chapter07` (DGL) verschoben
- [ ] Kapitel 6 umgebaut
- [ ] Kapitel 7 angelegt
- [ ] `myst.yml` und Querverweise in Kapitel 4–7 angepasst
- [ ] Sprint 03 geplant (Kapitel 7–9 alt lesen, eigener Chat)
- [ ] Abstimmung mit der Kollegin
