# Lineare gewöhnliche Differentialgleichungen – Einführung

Lineare gewöhnliche Differentialgleichungen (gDGLen) begegnen uns in vielen
ingenieurwissenschaftlichen Anwendungen. Ein klassisches Beispiel aus dem
Maschinenbau ist die Beschreibung von Schwingungsvorgängen, etwa bei der
**Nockenwelle**: Die Umwandlung rotatorischer Bewegung in translatorische
Bewegung lässt sich durch eine lineare gDGL 2. Ordnung modellieren. Dasselbe
mathematische Modell – die gedämpfte Schwingungsgleichung

$$0 = \ddot{\varphi} + 2\delta\dot{\varphi} + \omega_0^2\varphi$$

– wird Ihnen auch in der Vorlesung Maschinendynamik wieder begegnen.

In diesem Kapitel erarbeiten wir systematisch die Theorie und Lösungsverfahren
für lineare gDGLen 1. und 2. Ordnung.

## Lernziele

```{admonition} Lernziele
:class: attention
* Sie kennen ein ingenieurwissenschaftliches Beispiel (Nockenwelle/gedämpfter
  Schwinger), das auf eine **lineare gewöhnliche Differentialgleichung 2. Ordnung**
  führt.
* Sie können die Bewegungsgleichung eines einfachen Feder-Dämpfer-Systems
  aufstellen und in die Standardform
  $\ddot{\varphi} + 2\delta\dot{\varphi} + \omega_0^2\varphi = 0$
  bringen.
* Sie wissen, welche physikalische Bedeutung die **Eigenfrequenz** $\omega_0$
  und die **Dämpfungskonstante** $\delta$ haben.
```

## Zusammenfassung und Ausblick

Die Nockenwelle zeigt exemplarisch, warum lineare gDGLen für den Maschinenbau
zentral sind. In den folgenden Abschnitten erarbeiten wir zunächst das
notwendige Grundwissen zu linearen gDGLen und lernen dann schrittweise die
wichtigsten Lösungsverfahren kennen.
