# Gibbssches Phänomen

Beim Approximieren einer periodischen Funktion mit **Sprungstellen** durch eine
Fourier-Reihe tritt ein bemerkenswertes Verhalten auf: Auch wenn man immer mehr
Glieder der Reihe hinzunimmt, verschwinden die Über- und Unterschwinger an den
Sprungstellen nicht. Dieses Phänomen wird nach dem Mathematiker Josiah Willard
Gibbs benannt.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie verstehen das **Gibbssche Phänomen** und können es mit eigenen Worten
  erklären: An Sprungstellen einer Funktion treten bei der zugehörigen
  Fourier-Reihe Über- und Unterschwinger auf, deren relative Höhe im
  Grenzwert bei ca. **9 %** der Sprungamplitude liegt.
* Sie wissen, dass diese Überschwinger auch bei einer Erhöhung der Anzahl der
  Glieder der Fourier-Reihe **nicht verschwinden**, sondern sich lediglich der
  Sprungstelle nähern.
* Sie kennen die Voraussetzungen für das Auftreten des Gibbsschen Phänomens:
  Die Funktion muss **Unstetigkeitsstellen** (Sprünge) besitzen.
* Sie wissen, warum das Gibbssche Phänomen in der Praxis relevant ist, z.B.
  als Ursache von **Artefakten bei der Bildkompression** an harten
  Farbübergängen.
* Sie kennen den Zusammenhang zwischen Unstetigkeitsstellen und dem
  Abklingverhalten der Fourier-Koeffizienten: An Unstetigkeitsstellen gilt
  nur noch $a_k, b_k \sim \frac{1}{k}$ statt $\frac{1}{k^2}$.
```

## Zusammenfassung und Ausblick

Das Gibbssche Phänomen zeigt eine grundsätzliche Grenze der Fourier-Approximation
an Sprungstellen auf. Im nächsten Abschnitt wechseln wir zur **komplexen
Fourier-Reihe**, die auf der Eulerschen Formel basiert und eine kompaktere
alternative Darstellung bietet.
