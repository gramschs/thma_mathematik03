# Three.js L-Profil Transformationen - Anleitung

## Übersicht

Dieses Template visualisiert lineare Abbildungen (Drehung, Spiegelung, Skalierung) eines L-Profils in 2D mit Three.js. Es ist als Lernressource für Maschinenbau-Studierende konzipiert.

## Schnellstart

1. Öffne `l-profil-transformation.html` direkt im Browser (Firefox, Chrome, Edge)
2. Keine Installation nötig - Three.js wird von CDN geladen
3. Funktioniert offline nach dem ersten Laden (CDN cached)

## Struktur des Codes

### 1. Three.js Grundsetup

```javascript
// Szene = Container für alle 3D-Objekte
scene = new THREE.Scene();

// Orthographische Kamera = keine Perspektive, parallele Projektion
// Perfekt für technische 2D-Ansichten
camera = new THREE.OrthographicCamera(...);

// Renderer = zeichnet die Szene
renderer = new THREE.WebGLRenderer({ antialias: true });
```

**Warum orthographische Kamera?**

- Parallele Linien bleiben parallel (wie im technischen Zeichnen)
- Keine Verzerrung durch Perspektive
- Ideal für 2D-Mathematik in xy-Ebene

### 2. L-Profil erstellen

```javascript
// THREE.Shape = 2D-Kontur definieren
const shape = new THREE.Shape();
shape.moveTo(0, 0);
shape.lineTo(0, 3);
// ... weitere Punkte

// Shape zu 3D-Geometrie konvertieren (mit z=0)
const geometry = new THREE.ShapeGeometry(shape);

// Material + Mesh erstellen
const material = new THREE.MeshBasicMaterial({ color: 0x2196F3 });
lProfile = new THREE.Mesh(geometry, material);
```

**Wichtig:**

- `ShapeGeometry` erstellt eine flache Geometrie in der xy-Ebene
- Später für 3D: `ExtrudeGeometry` verwenden!

### 3. Transformationen

```javascript
// Rotation um z-Achse (senkrecht zur xy-Ebene)
lProfile.rotation.z = angleRad;

// Skalierung
lProfile.scale.set(scaleX, scaleY, 1);
```

**Transformationsreihenfolge in Three.js:**

1. Scale (Skalierung)
2. Rotation (Drehung)
3. Translation (Verschiebung)

Diese Reihenfolge ist fest in Three.js!

### 4. Matrix-Darstellung

Die 2×2-Transformationsmatrix wird aus Rotation und Skalierung berechnet:

```javascript
// Rotationsmatrix * Skalierungsmatrix
const a = cos(α) * scaleX;
const b = -sin(α) * scaleX;
const c = sin(α) * scaleY;
const d = cos(α) * scaleY;
```

**Matrix:**

```
┌       ┐
│ a  b  │
│ c  d  │
└       ┘
```

## Integration in MyST/Jupyter Book

### Option 1: Inline HTML (einfach)

In deiner `.md`-Datei:

```markdown
```{raw} html
<iframe src="l-profil-transformation.html" width="850" height="900" frameborder="0"></iframe>
\```
```

### Option 2: Separates JavaScript (sauber)

1. Three.js-Code in separate Datei: `assets/l-profil.js`
2. In MyST einbinden:

```markdown
```{raw} html
<div id="canvas-container"></div>
<script src="https://cdn.jsdelivr.net/npm/three@0.160.0/build/three.min.js"></script>
<script src="../assets/l-profil.js"></script>
\```
```

## Erweiterungsmöglichkeiten

### 1. Verkettung von Transformationen zeigen

```javascript
// Button "Verkettung demonstrieren"
function showComposition() {
    // Erst drehen um 45°
    applyRotation(45);
    
    setTimeout(() => {
        // Dann spiegeln an x-Achse
        mirrorX();
    }, 1000);
}
```

### 2. Eigenvektoren visualisieren

```javascript
// Für Spiegelung an y=x sind die Eigenvektoren:
// v1 = (1, 1) mit Eigenwert λ=1
// v2 = (1, -1) mit Eigenwert λ=-1

function drawEigenvectors() {
    const arrow1 = new THREE.ArrowHelper(
        new THREE.Vector3(1, 1, 0).normalize(),
        new THREE.Vector3(0, 0, 0),
        3,
        0xff00ff
    );
    scene.add(arrow1);
}
```

### 3. Schrittweise Animation

```javascript
let animationProgress = 0;

function animateTransformation() {
    animationProgress += 0.01;
    
    // Interpoliere zwischen 0° und Zielwinkel
    currentRotation = targetAngle * animationProgress;
    
    if (animationProgress < 1) {
        requestAnimationFrame(animateTransformation);
    }
    
    applyTransformation();
}
```

### 4. Mehrere Objekte gleichzeitig transformieren

```javascript
// Array von Objekten
const objects = [lProfile, anotherShape];

objects.forEach(obj => {
    obj.rotation.z = angleRad;
});
```

### 5. Spur des Objekts zeichnen (Trail)

```javascript
// Speichere Positionen von Eckpunkten
const trail = [];

function updateTrail() {
    // Position eines Eckpunkts speichern
    const cornerPos = lProfile.localToWorld(new THREE.Vector3(3, 1, 0));
    trail.push(cornerPos);
    
    // Linie durch alle Punkte zeichnen
    const trailGeometry = new THREE.BufferGeometry().setFromPoints(trail);
    const trailLine = new THREE.Line(trailGeometry, trailMaterial);
}
```

## Übergang zu 3D (Phase 2)

Für die 3D-Phase mit FreeCAD musst du:

### 1. Perspektivische Kamera verwenden

```javascript
camera = new THREE.PerspectiveCamera(
    45,                           // Blickwinkel
    width / height,               // Seitenverhältnis
    0.1,                          // Near clipping
    1000                          // Far clipping
);
camera.position.set(10, 10, 10); // Schräg von oben
camera.lookAt(0, 0, 0);          // Blick zum Ursprung
```

### 2. OrbitControls hinzufügen (Maus-Steuerung)

```javascript
import { OrbitControls } from 'three/addons/controls/OrbitControls.js';

const controls = new OrbitControls(camera, renderer.domElement);
controls.enableDamping = true; // Sanfte Bewegung
```

### 3. ExtrudeGeometry für 3D-Profil

```javascript
const extrudeSettings = {
    depth: 2,              // Tiefe des Profils
    bevelEnabled: false
};

const geometry = new THREE.ExtrudeGeometry(shape, extrudeSettings);
```

### 4. STL/OBJ von FreeCAD laden

```javascript
import { STLLoader } from 'three/addons/loaders/STLLoader.js';

const loader = new STLLoader();
loader.load('models/l-profile.stl', function(geometry) {
    const material = new THREE.MeshPhongMaterial({ color: 0x2196F3 });
    const mesh = new THREE.Mesh(geometry, material);
    scene.add(mesh);
});
```

## Performance-Tipps

1. **Geometrie nur einmal erstellen**: Transformiere das Mesh, nicht die Geometrie
2. **Material-Wiederverwendung**: Ein Material für mehrere Meshes
3. **Dispose nicht vergessener Objekte**: `geometry.dispose()`, `material.dispose()`

## Häufige Anfängerfehler

### ❌ Falsch: Geometrie jedes Mal neu erstellen
```javascript
function applyTransformation() {
    scene.remove(lProfile);
    createLProfile(); // Ineffizient!
}
```

### ✅ Richtig: Mesh transformieren
```javascript
function applyTransformation() {
    lProfile.rotation.z = angleRad;
    lProfile.scale.set(scaleX, scaleY, 1);
}
```

### ❌ Falsch: Winkel in Grad verwenden
```javascript
lProfile.rotation.z = 45; // Three.js erwartet Radiant!
```

### ✅ Richtig: In Radiant umrechnen
```javascript
const angleRad = (45 * Math.PI) / 180;
lProfile.rotation.z = angleRad;
```

## Lernressourcen

1. **Three.js Fundamentals**: https://threejs.org/manual/
   - Beginne mit den ersten 10 Kapiteln
   - Fokus: Szene, Kamera, Geometrie, Material

2. **Three.js Examples**: https://threejs.org/examples/
   - Viele Beispiele zum Lernen und Anpassen

3. **Math-Visualisierung mit Three.js**:
   - https://github.com/mrdoob/three.js/tree/master/examples
   - Suche nach "math" oder "geometry"

4. **YouTube: Three.js Journey** (Bruno Simon)
   - Exzellente Video-Tutorial-Serie

## Nächste Schritte für deine Vorlesung

1. **Phase 1 (aktuell)**: 2D-Transformationen verstehen
2. **Animation hinzufügen**: Schrittweise Drehung zeigen
3. **Verkettung demonstrieren**: Erst drehen, dann spiegeln
4. **Phase 2 vorbereiten**: 3D-Version mit FreeCAD-Import
5. **Digitale Zwillinge**: Komplexere Bauteile, Sensordaten, Echtzeit-Updates

## Fragen?

Wenn du Fragen hast oder bestimmte Features implementieren möchtest, lass es mich wissen!

**Viel Erfolg beim Lehren der Mathematik mit Three.js! 🚀**
