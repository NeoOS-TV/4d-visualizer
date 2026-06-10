[![pages-build-deployment](https://github.com/NeoOS-TV/4d-visualizer/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/NeoOS-TV/4d-visualizer/actions/workflows/pages/pages-build-deployment)

# 🌌 4D Visualizer — Tesseract

Eine interaktive Webanwendung zur Visualisierung vierdimensionaler Polytope in Echtzeit. Erkunde Tesseract (Hyperwürfel), 16-Zelle und 24-Zelle mit intuitiven Steuerungen für Desktop und Mobile.

## ✨ Features

- **3 verschiedene 4D-Objekte**: Tesseract, 16-Zelle, 24-Zelle
- **Responsive Design**: Optimiert für Desktop (Seitenleiste) und Mobile (Drawer)
- **Echtzeit-Rotation**: 6 unabhängige Rotationsebenen (XY, XZ, XW, YZ, YW, ZW)
- **6 Farbschemas**: Neon, Feuer, Matrix, Gold, Weiß, Pastell
- **Flexible Projektion**: Anpassbare 4D→3D und 3D→2D Projektion
- **Touch-Gestensteuerung**: 1-Finger für 3D, 2-Finger für 4D Rotation
- **Performance-Metriken**: Live FPS-Display

## 🎮 Steuerung

### Desktop
- **Drag**: 3D-Rotation (XZ/YZ Ebenen)
- **Shift+Drag**: 4D-Rotation (XW/YW Ebenen)
- **Seitenleiste**: Rotationsgeschwindigkeit, Projektion, Farbschemas, Objekt-Wahl

### Mobile
- **1 Finger ziehen**: 3D-Rotation
- **2 Finger ziehen**: 4D-Rotation
- **FABs (oben rechts)**: Pause, Reset, Achsen
- **Drawer (unten)**: Controls in 4 Tabs (Rotation, Form, Farbe, Info)

## 🚀 GitHub Pages Deployment

1. Gehe zu Repository Settings → Pages
2. Stelle "Source" auf `Deploy from a branch`
3. Wähle Branch `main` und Folder `/root`
4. Speichern — fertig! 🎉

Die App ist dann verfügbar unter: `https://neoos-tv.github.io/4d-visualizer/`

## 🎨 Technologie

- **Pure HTML5 Canvas**: Keine externen Abhängigkeiten
- **Vanilla JavaScript**: Effiziente 4D-Mathematik
- **Responsive CSS**: Grid & Flexbox Layout
- **Google Fonts**: Space Mono & Inter

## 📐 4D Mathematik

### Rotationen
Jede 4D-Rotation wird als Matrix-Multiplikation in einer der 6 orthogonalen Ebenen berechnet:
- **XY, XZ, XW, YZ, YW, ZW**

### Projektion
1. **4D → 3D**: Perspektivische Projektion mit Abstand `d4`
2. **3D → 2D**: Perspektivische Projektion mit Abstand `d3`
3. **Färbung**: W-Koordinate interpoliert zwischen zwei Schemafarben

## 🎯 Objekte

**Tesseract (Hyperwürfel)**
- 16 Ecken, 32 Kanten, 8 kubische Zellen
- Die 4D-Analogie zum 3D-Würfel

**16-Zelle (Hyperoktraeder)**
- 8 Ecken, 24 Kanten, 16 Tetraeder-Zellen
- Dual zum Tesseract

**24-Zelle**
- 24 Ecken, 96 Kanten, 24 Oktaeder-Zellen
- Das schönste reguläre Polytop in 4D

## 🔧 Anpassungen

### Geschwindigkeit ändern
Bearbeite in `index.html` die Default-Werte im `planes`-Array:
```javascript
const planes = [
  {id:'xy', ..., speed: 0},      // → speed ändern
  {id:'xw', ..., speed: 0.008},  // Standard: aktiviert
  // ...
];
```

### Neue Farbschemas
Füge zum `schemes`-Array hinzu:
```javascript
{name:'Dein Schema', a:[r,g,b], b:[r,g,b], bg:'#hex', swatch:'#hex'}
```

### Canvas-Auflösung
Ändere in `drawScene()` die `scale`-Variable für Zoom-Effekt.

## 📱 Browser-Support

- Chrome/Edge 60+
- Firefox 55+
- Safari 12+
- Mobile Safari (iOS 12+)

## 📄 Lizenz

MIT License — Frei nutzbar und modifizierbar.

---

**Viel Spaß beim Erforschen der vierten Dimension! 🌀**
