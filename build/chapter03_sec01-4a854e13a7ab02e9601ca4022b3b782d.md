# TODO: Lineare Abbildungen in 2D

```{admonition} Hinweis
:class: warning
Dieses Vorlesungsskript befindet sich in Bearbeitung.
```

In einer CAD-Software konstruieren wir ein L-Profil. Zunächst soll der
Querschnitt des L-Profils als Skizze in der Ebene konstruiert werden (2D). Damit
es später an der richtigen Stelle in die Baugruppe eingepasst werden kann,
möchten wir das Bauteil drehen, spiegeln oder skalieren können. In diesem
Kapitel beschäftigen wir uns damit, diese Operationen in der Ebene mathematisch
zu beschreiben.

## Lernziele

* Sie können eine Drehung um den Ursprung als lineare Abbildung in
  Matrix-Vektor-Schreibweise formulieren.

## Geometrische Transformationen im R²

TODO: einleitender Text

### Drehung um den Ursprung

Gegeben ist ein 30-20-5 L-Profil, d.h. ein Profil mit dem folgenden Querschnitt:

L-Profil um Winkel α drehen
Mathematische Beschreibung: Was passiert mit einem Punkt (x, y)?
Herleitung der Rotationsmatrix
Beispiele: 90°, 45°, beliebiger Winkel

### Spiegelung

L-Profil an x-Achse spiegeln
L-Profil an y-Achse spiegeln
Spiegelung an Gerade durch den Ursprung (z.B. y = x)
Matrizendarstellung

### Skalierung

Gleichmäßige Streckung (größeres/kleineres L-Profil)
Ungleichmäßige Skalierung (verschiedene Faktoren in x- und y-Richtung)
Matrix für Skalierung

## Das gemeinsame Prinzip: Lineare Abbildungen

### Matrixdarstellung

Beobachtung: Alle haben die Form y = A · x
Konstruktion der Matrix: Wohin gehen e₁ = (1, 0) und e₂ = (0, 1)?
Die Spalten der Matrix sind die Bilder der Basisvektoren

### Definition der linearen Abbildung

Was bleibt geometrisch erhalten? (Ursprung, Geraden, Parallelität)
Die beiden Linearitätsbedingungen:

f(u + v) = f(u) + f(v)
f(λu) = λf(u)

Nachweis für die geometrischen Beispiele

### Gegenbeispiel

Translation (Verschiebung) ist NICHT linear
Warum? Ursprung wird verschoben

## Arbeiten mit linearen Abbildungen

### Verkettung von Abbildungen

L-Profil erst drehen, dann spiegeln
Das entspricht: Matrizenmultiplikation
Wichtig: Reihenfolge ist entscheidend! (nicht kommutativ)
Beispielrechnung

### Umkehrabbildungen

Wann kann man eine Transformation rückgängig machen?
Inverse Matrix
Beispiel: Rückdrehung, Rückspiegelung
Determinante ≠ 0 als Bedingung

### Besondere Richtungen

Gibt es Punkte, die fest bleiben? (Fixpunkte → nur Ursprung)
Gibt es Richtungen, die erhalten bleiben? (invariante Richtungen)
Vorschau/Motivation: Eigenvektoren (werden später behandelt)

## Zusammenfassung und Ausblick

Kernbotschaften wiederholen
Lineare Abbildungen: Matrixdarstellung, Linearitätsbedingungen, Verkettung
Ausblick: "Im R³ funktioniert das ähnlich – und dort nutzen wir FreeCAD!"
