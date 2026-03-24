# Instruktionen: Vorlesungsskript Mathematik für Maschinenbau (MyST/Jupyter Book v2)

---

## Kontext

Dieses Vorlesungsskript richtet sich an Maschinenbaustudenten im zweiten oder
dritten Semester. Es wird nach dem **Inverted-Classroom-Prinzip** eingesetzt:
Die Studierenden lesen das Skript und schauen die eingebetteten Videos
eigenständig zu Hause. Die Präsenzzeit wird für Diskussion und Aufgaben genutzt.

Das Skript wird mit **Jupyter Book Version 2 (MyST Markdown)** erstellt und als
HTML auf **GitHub Pages** gehostet. Alle Dateien sind `.md`-Dateien im
MyST-Format.

Das Skript ist in Kapitel (`chapter0X`) und Sektionen (`chapter0X_secYY.md`)
aufgeteilt. Beispiel: `chapter03_sec01.md`, `chapter03_sec02.md`, usw.

---

## Dateistruktur und Datei-Header

Jede Sektion ist eine eigenständige `.md`-Datei (ca. 150 bis 300 Zeilen). Jede
Datei beginnt mit einem YAML-Front-Matter-Block:

```markdown
---
authors:
  - name:
---
```

Unmittelbar danach folgt der H1-Titel der Sektion. Unterabschnitte verwenden
H2-Überschriften.

---

## Pflichtstruktur jeder Sektion

Jede Sektion folgt **exakt** diesem narrativen Bogen, ohne Abweichung:

```
# Titel der Sektion

Einleitungsabsatz (2–4 Sätze): Anknüpfung an die vorherige Sektion,
Einführung eines konkreten physikalischen oder technischen Szenarios,
das das neue Konzept motiviert. Niemals mit einer Definition oder
einer Formel beginnen.

## Lernziele

[Lernziele-Admonition, siehe unten]

## Abschnitt 1

[Vom konkreten Beispiel zur informellen Beschreibung zur formalen
Definitionsbox, siehe Prinzip "Erst Beispiel, dann abstrakt"]

## Abschnitt 2

...

## Zusammenfassung und Ausblick

Kurzer Rückblick (2–4 Sätze). Vorschau auf die nächste Sektion.
Konkreter Vorwärtsverweis auf ein späteres Thema im Kurs.
```

---

## Prinzip: Erst Beispiel, dann abstrakt

Dies ist das wichtigste inhaltliche Gestaltungsprinzip des gesamten Skripts.
Jeder neue Begriff und jede neue Formel wird nach dem folgenden Dreischritt
eingeführt:

1. **Konkretes Beispiel zuerst.** Wir beobachten ein physikalisches oder
   technisches Phänomen oder ein Beispiel aus dem Alltag von Studierenden und beschreiben es in Alltagssprache. Die
   Studierenden sollen das Gefühl haben, dass die Mathematik eine Antwort
   auf eine echte Frage ist.
2. **Informelle Beschreibung.** Wir benennen das Muster, das wir im Beispiel
   sehen, und formulieren es noch ohne formale Notation.
3. **Formale Definition (Definitionsbox).** Erst jetzt schreiben wir die
   abstrakte Definition oder Formel. Die Definitionsbox fasst zusammen,
   sie führt nicht ein.

Nach jeder Definitionsbox wird die Definition **sofort auf das laufende
Beispiel angewendet** und mit konkreten Zahlen durchgerechnet. Ergebnisse
werden durch Einsetzen oder Randwertprüfung verifiziert. Dieser
Verifikationsschritt wird explizit ausgeschrieben.

**Falsch:** *"Eine Matrix heißt invertierbar, wenn ... Betrachten wir nun
folgendes Beispiel."*

**Richtig:** *"Wir haben gerade gesehen, dass das Gleichungssystem genau eine
Lösung hat. Das ist kein Zufall: Es liegt daran, dass die Koeffizientenmatrix
eine Inverse besitzt. Matrizen mit dieser Eigenschaft nennen wir ..."*

---

## Storytelling: Das durchgehende Beispiel

Jede Sektion (und wenn möglich das gesamte Kapitel) soll ein **einziges
durchgehendes Beispiel** verwenden, das in der Einleitung eingeführt und in
jedem Abschnitt weiterentwickelt wird. Dieses Beispiel ist der narrative rote
Faden.

Regeln für das durchgehende Beispiel:

- Es muss **physikalisch konkret** und für den Maschinenbau relevant sein oder es muss aus dem Alltag stammen.
- Wenn eine neue Konfiguration des Beispiels eingeführt wird, beschreiben wir
  sie erst physikalisch, wählen dann Koordinaten oder Parameter und schreiben
  schließlich die Gleichung oder Matrix auf. Diese Reihenfolge ist verbindlich.
- Parameterwerte werden so gewählt, dass Zwischenergebnisse interpretierbar
  sind. Wir vermeiden trivial runde Zahlen ebenso wie Zahlen, die so
  unübersichtlich sind, dass sie vom Inhalt ablenken.
- Am Ende der Sektion soll das Beispiel vollständig abgeschlossen sein. Keine
  offenen Fragen, die nie beantwortet werden.

Für ein ganzes Kapitel empfiehlt sich ein **kapitelweites Leitbeispiel**, das
in der ersten Sektion eingeführt und in den folgenden Sektionen immer wieder
aufgegriffen wird.

---

## Überschriften von Unterabschnitten

Unterabschnittsüberschriften sollen als **Fragen oder kurze Aussagen**
formuliert werden, die ein Studierender natürlich stellen oder denken würde.

Gute Beispiele:
- "Wann ist ein Gleichungssystem eindeutig lösbar?"
- "Was verrät uns die Determinante über das Volumen?"
- "Wie berechnen wir das Vektorprodukt?"

Schlechte Beispiele (abstrakte Substantivphrasen):
- "Definition der Determinante"
- "Eigenschaften inverser Matrizen"
- "Anwendungen"

---

## Lernziele-Block (Pflichtformat)

```markdown
## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie wissen, was eine **lineare Abbildung** ist.
* [ ] Sie kennen die **Matrix-Vektor-Schreibweise**
  $F_{\mathbf{A}}(\vec{v}) = \mathbf{A} \cdot \vec{v} = \vec{w}$.
* [ ] Sie können ...
```
```

Regeln:

- Jedes Lernziel beginnt mit `* [ ]` (Checkbox-Syntax).
- Schlüsselbegriffe werden **fettgedruckt**.
- Lernziele beginnen mit "Sie wissen", "Sie können", "Sie kennen" oder
  "Sie verstehen".
- Anzahl: 3 bis 6 Lernziele pro Sektion.
- Keine Unteraufzählungen innerhalb eines Lernziels.
- Der Lernziele-Block erscheint **unmittelbar nach dem H1-Titel**, vor dem
  ersten Fließtextabsatz.

---

## Definitionsboxen

Für neue Fachbegriffe wird eine Box im Format `note` verwendet:

```markdown
```{admonition} Was ist ... eine lineare Abbildung?
:class: note
Fließtext der Definition. Formeln in LaTeX.
```
```

Regeln:

- Definitionsboxen erscheinen **nach** der informellen Einführung im
  Fließtext, niemals davor.
- Unmittelbar nach jeder Definitionsbox folgt die Anwendung auf das
  durchgehende Beispiel mit konkreten Zahlen.
- Für wichtige Merkregeln oder Zusammenfassungen ebenfalls `:class: note`.

---

## Sprache und Stil

- Sprache: **Deutsch**.
- Kein Gedankenstrich (`–`) im Fließtext. Satzkonstruktionen umformulieren
  oder einen Punkt setzen.
- Kein `d.h.` oder `z.B.` mitten im Satz. Entweder ausschreiben oder in
  Klammern setzen.
- **Fettdruck** wird ausschließlich beim erstmaligen Einführen eines
  Fachbegriffs verwendet, nicht zur allgemeinen Hervorhebung im Fließtext.
- **Anrede:** Im Fließtext konsequent Wir-Formulierungen. Die einzige
  Ausnahme sind die Lernziele, die "Sie" verwenden.
- Ton: klar, präzise, aber motivierend. Näher an einem gesprochenen Vortrag
  als an einem Lehrbuch. Nicht trocken.
- **Rhetorische Fragen** sind ausdrücklich erwünscht, um Aufmerksamkeit zu
  lenken und Spannung zu erzeugen. Sie werden *kursiv* gesetzt:
  *Aber was passiert, wenn die Determinante gleich Null ist?*
- Absatzlänge: 3 bis 6 Sätze. Keine Stichpunktlisten im Fließtext, außer
  in den Lernzielen und Definitionsboxen.

---

## Rückverweise und Vorwärtsverweise

Jede Sektion soll enthalten:

- Mindestens einen **Rückverweis** auf ein Konzept aus einer früheren
  Sektion. Dieser zeigt den Studierenden, dass das Skript einen kohärenten
  Faden hat.
- Mindestens einen **Vorwärtsverweis** auf ein späteres Thema, entweder im
  gleichen Kapitel oder in einem späteren Kapitel. Vorwärtsverweise sollen
  konkret genug sein, um echte Neugier zu wecken, aber vage genug, um nicht
  die Antwort vorwegzunehmen.

Gute Stellen für Vorwärtsverweise:
- Im Fließtext, wo ein Zusammenhang angedeutet wird: "Den Grund dafür werden
  wir verstehen, wenn wir im Kapitel über Eigenwerte ..."
- In der Zusammenfassung, als expliziter Ausblick.

Schlechte Vorwärtsverweise:
- "Dies wird später behandelt." (zu vage)
- "Im nächsten Abschnitt sehen wir ..." (zu selbstverständlich)

---

## YouTube-Videos

```markdown
```{dropdown} Video "Titel des Videos" von Kanalname
<iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID"
title="YouTube video player" frameborder="0" allow="accelerometer; autoplay;
clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```
```

Regeln:

- Videos werden **direkt nach dem Unterabschnitt** eingebettet, in dem das
  entsprechende Konzept eingeführt wurde. Nicht alle Videos am Ende der
  Sektion sammeln.
- Videos sind eine Vertiefung, kein Ersatz für den Fließtext.
- Bevorzugte Kanäle: **MathePeter**, **Mathematische Methoden**,
  **3Blue1Brown**.
- Video-URLs sind Platzhalter, sofern keine konkreten Links bekannt sind.
- Pro Sektion 1 bis 2 Videos.

---

## LaTeX-Formeln

- Abgesetzte Formeln: `\begin{equation*} ... \end{equation*}` (keine
  Nummerierung).
- Mehrzeilige Rechnungen: `\begin{align*} ... \end{align*}`.
- Inline-Formeln: `$...$`.
- Vektoren: `\vec{v}`, Matrizen: `\mathbf{A}`.
- Mengen: `\mathbb{R}^n`.
- Kein `$$...$$` für abgesetzte Formeln.
- Jede abgesetzte Formel wird im anschließenden Satz erklärt: Was bedeuten
  die Symbole im Kontext des laufenden Beispiels?
- Physikalische Einheiten erscheinen direkt in Formeln als `~\text{Einheit}`.

---

## Maschinenbau-Bezüge (zentrale Anforderung)

**Jede Sektion muss Maschinenbau-Bezüge enthalten**, nicht nur in der
Einleitung, sondern verteilt im Fließtext. Ziel: Die Studierenden sollen
verstehen, wozu sie die Mathematik brauchen, weil sie die Werkzeuge für
konkrete Ingenieurprobleme liefert.

### Regeln für MB-Bezüge

1. MB-Bezüge werden **direkt in den Fließtext eingebaut**, nicht als
   separate Box.
2. MB-Bezüge motivieren die Mathematik, sie illustrieren sie nicht nur
   nachträglich. Der Bezug soll am Anfang eines Abschnitts stehen und die
   Frage aufwerfen, die die Mathematik dann beantwortet.
3. Wenn möglich, wird auf spätere Lehrveranstaltungen verwiesen ("In der
   Technischen Mechanik werden Sie ...").
4. Vorwärtsverweise innerhalb des Skripts sind ausdrücklich erwünscht
   ("Den mathematischen Apparat dafür lernen wir im Kapitel über
   Eigenwerte").

---

## Tabellen mit Maschinenbau-Spalte

Übersichtstabellen sollen, wo sinnvoll, eine Spalte "Beispiel im
Maschinenbau" enthalten:

```markdown
| Transformation | Matrix $\mathbf{A}$ | $\det(\mathbf{A})$ | Beispiel im Maschinenbau |
| --- | --- | --- | --- |
| Gleichm. Streckung um $s$ | $\begin{pmatrix} s & 0 \\ 0 & s \end{pmatrix}$ | $s^2$ | Maßstabsänderung in CAD |
```

---

## TikZ-Abbildungen

Alle Abbildungen werden als eigenständige `standalone`-Dokumente in LaTeX
erstellt, nach SVG exportiert und über eine `{figure}`-Direktive in die
MyST-Markdown-Quelldatei eingebunden.

### Präambel-Vorlage

Jede TikZ-Datei verwendet ausnahmslos die folgende Präambel:

```latex
\documentclass[11pt]{standalone}
\usepackage{amssymb}
\usepackage{amsmath}
\usepackage[no-math]{fontspec}
\usepackage{unicode-math}
\usepackage{libertinus}
\usepackage{pgf,xcolor}
\usepackage{tikz}
\usetikzlibrary{arrows.meta, backgrounds}
\usepackage{pgfplots}
\pgfplotsset{compat=newest}
```

`pgfplots` wird in jeder Datei eingebunden, auch wenn die Abbildung nur
reines TikZ verwendet, damit die Präambel über alle Dateien identisch bleibt.
Die Kompilierung erfolgt mit `lualatex` (wegen `fontspec` und `libertinus`).

### Schrift

Die Schrift ist durchgehend **Libertinus**: Libertinus Serif für Textlabels
und Libertinus Math für mathematische Symbole. Damit stimmen Labels in
Abbildungen visuell mit dem Inline-Text des Jupyter Books überein.

Keine anderen Schriftfamilien verwenden (insbesondere nicht TeX Gyre Heros
oder Computer Modern).

### Farbpalette

Alle sieben Farben werden in jeder Datei definiert, auch wenn nur eine
Teilmenge verwendet wird:

```latex
\definecolor{my_darkgray}{HTML}{484949}
\definecolor{my_lightgray}{HTML}{F3F4F4}
\definecolor{my_darkblue}{HTML}{005A94}
\definecolor{my_lightblue}{HTML}{CCDEE9}
\definecolor{my_yellow}{HTML}{FFEC7F}
\definecolor{my_red}{HTML}{E60000}
\definecolor{my_orange}{HTML}{E87846}
```

Keine ad-hoc-Farbnamen wie `lightblue`, `myblue` oder `highlight`
einführen. Alle Farben kommen ausnahmslos aus dieser Palette.

**Zweifarbige Abbildungen (Standardfall):** `my_darkblue` für das primäre
Element (Konturlinie, Hauptkurve, dominante Region) und `my_lightblue` für
das sekundäre Element (Füllung, Hintergrundregion, zweite Kurve).

**Dreifarbige Funktionsgraphen:** `my_darkblue` für die erste Kurve,
`my_red` für die zweite, `my_orange` für die dritte. `my_yellow` nicht für
Kurvenlinien verwenden (zu wenig Kontrast auf hellgrauem Hintergrund).
`my_yellow` ist für hervorgehobene Füllregionen reserviert.

**Text und Annotationen:** `my_darkgray` für sekundäre Labels. `my_darkblue`
für Labels, die mathematische Objekte bezeichnen. Standard-TikZ-Schwarz ist
für Elementlabels innerhalb von Diagrammen zulässig.

### Hintergrundpanel

Jede Abbildung hat ein explizites Hintergrundpanel mit `my_lightgray`. Dies
gewährleistet korrekte Darstellung in hellen und dunklen Browser-Themes.

```latex
\begin{tikzpicture}[
    show background rectangle,
    background rectangle/.style={fill=my_lightgray, rounded corners=8pt},
    inner frame sep=0.8cm
]
```

`inner frame sep=0.3cm` nur für breite, flache Abbildungen wie Zahlenstrahlen
verwenden. In allen anderen Fällen `0.8cm`.

### Achsenstil für Funktionsgraphen (pgfplots)

```latex
\begin{axis}[
    axis lines = center,
    xlabel = {$x$},
    ylabel = {$y$},
    grid = both,
    axis equal,
    axis line style={thick},
]
```

`axis equal` nur weglassen, wenn das natürliche Seitenverhältnis der Funktion
den Graphen bei gleicher Skalierung unleserlich macht. Die Ausnahme mit einem
Kommentar dokumentieren.

Alle Kurven:

```latex
\addplot[draw=my_darkblue, samples=300, ultra thick, domain=a:b]{ ... };
```

Bei Polstellen oder anderen Singularitäten: die Domain auf separate
`\addplot`-Aufrufe aufteilen, einen pro stetigem Ast.

### Legenden

Bei mehr als einer Kurve eine Legende einfügen:

```latex
legend pos=north west,
legend style={font=\small},
legend cell align=left,
```

`\addlegendentry{...}` direkt nach dem jeweiligen `\addplot`-Aufruf setzen.
Nicht den `legend entries={...}`-Schlüssel am Axis-Objekt verwenden.

### Abbildungsunterschriften

Jede Abbildung in der MyST-Quelldatei erhält eine Beschriftung der Form:

```
Darstellung von [was die Abbildung zeigt].
(Quelle: eigene Abbildung; Lizenz [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0))
```

Den beschreibenden Teil auf einen Satz begrenzen. Keine Informationen
wiederholen, die bereits im umgebenden Text stehen.

### Dateinamen

Dateinamen beschreibend und in Kleinbuchstaben mit Unterstrichen. Kein
Kapitel- oder Sektionsnummer im Dateinamen. Das Sprachkürzel `_DE` oder
`_EN` nur anhängen, wenn zwei Sprachversionen derselben Abbildung existieren.

---

## Qualitätskriterien vor dem Abliefern

Vor dem Ausgeben einer Sektion prüfen:

- [ ] YAML-Front-Matter-Block vorhanden?
- [ ] Einleitung beginnt mit einem konkreten Szenario, nicht mit einer
  Definition?
- [ ] Lernziele mit `* [ ]` formatiert, unmittelbar nach dem H1-Titel?
- [ ] Prinzip "Erst Beispiel, dann abstrakt" in jedem Abschnitt eingehalten?
- [ ] Durchgehendes Beispiel mit konkreten Zahlen vorhanden und am Ende
  vollständig abgeschlossen?
- [ ] Definitionsboxen erscheinen nach der informellen Einführung?
- [ ] Jede Definitionsbox sofort auf das Beispiel angewendet?
- [ ] Ergebnis explizit verifiziert (Einsetzen, Randwert, o.Ä.)?
- [ ] Unterabschnittsüberschriften als Fragen oder natürliche Aussagen
  formuliert?
- [ ] Mindestens eine rhetorische Frage im Fließtext, kursiv gesetzt?
- [ ] Mindestens 2 MB-Bezüge im Fließtext (nicht nur in der Einleitung)?
- [ ] Mindestens 1 Rückverweis auf eine frühere Sektion?
- [ ] Mindestens 1 Vorwärtsverweis auf ein späteres Kapitel oder eine
  spätere Lehrveranstaltung?
- [ ] Kein Gedankenstrich im Fließtext?
- [ ] Kein Fettdruck außer bei der Ersteinführung eines Fachbegriffs?
- [ ] Videos direkt nach dem jeweiligen Unterabschnitt eingebettet?
- [ ] Zusammenfassung mit konkretem Ausblick auf die nächste Sektion?
- [ ] TikZ-Dateien konform mit Präambel, Farbpalette und Hintergrundpanel?
