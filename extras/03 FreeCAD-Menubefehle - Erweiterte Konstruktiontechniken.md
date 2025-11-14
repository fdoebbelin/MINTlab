## 1. Spiegeln (Mirrored)

### Beschreibung
Das Werkzeug **Spiegeln** erzeugt eine gespiegelte Kopie eines Features (z.B. Pocket, Pad, Bohrung) an einer Symmetrieebene. Dies ist besonders nützlich für symmetrische Bauteile und spart Zeit, da nicht jedes Feature manuell dupliziert werden muss.

### Aufruf

**Methode 1: Über das Kontextmenü**
1. Im Modellbaum (linke Seite) das zu spiegelnde Feature (z.B. Pocket) auswählen
2. Rechtsklick auf das Feature
3. Im Kontextmenü **„Mirrored"** auswählen

**Methode 2: Über das Menü**
```
Menü → Part Design → Mirrored
```

**Voraussetzung:** Das Feature, das gespiegelt werden soll, muss vorher im Modellbaum markiert sein.

### Parameter im Dialog

| Parameter | Beschreibung |
|-----------|--------------|
| **Ebene (Mirror plane)** | Auswahl der Spiegelachse: Vertikale Skizzenachse, Horizontale Skizzenachse, XY-Ebene, XZ-Ebene, YZ-Ebene oder Referenz auswählen |
| **Krper transformieren** | Option zur Transformation des gesamten Körpers |
| **Element hinzufügen/entfernen** | Weitere Features zur Spiegelung hinzufügen oder entfernen |

### Beispiel aus dem PDF (Abschnitt 5.1.19)

**Ausgangssituation:** Ein Body mit einem Quader und einer Bohrung.

**Schritt-für-Schritt:**
1. Datei mit Body, Quader und Bohrung laden
2. Element **Bohrung** im Modellbaum markieren
3. Werkzeug **Spiegeln** auswählen (Rechtsklick → Mirrored)
4. Im Dialog die **Ebene** auswählen, z.B. **„Vertikale Skizzenachse"**
5. Mit **OK** bestätigen

**Ergebnis:** Die Bohrung wird an der gewählten Ebene gespiegelt und erscheint auf der gegenüberliegenden Seite des Bauteils.

**Wichtig:** Die Wahl der richtigen Spiegelachse ist entscheidend:
- **YZ-Ebene:** Spiegelt in X-Richtung (links-rechts)
- **XZ-Ebene:** Spiegelt in Y-Richtung (vorne-hinten)
- **XY-Ebene:** Spiegelt in Z-Richtung (oben-unten)

---

## 2. Lineares Muster (LinearPattern)

### Beschreibung
Mit dem Werkzeug **Lineares Muster** wird eine Reihe von Kopien eines Features in einer geraden Linie mit gleichmäßigen Abständen erzeugt. Dies ist ideal für Bohrungsreihen, Schlitze oder andere sich wiederholende Elemente.

### Aufruf

**Methode 1: Über das Kontextmenü**
1. Im Modellbaum das zu kopierende Feature markieren
2. Rechtsklick auf das Feature
3. Im Kontextmenü **„LinearPattern"** auswählen

**Methode 2: Über das Menü**
```
Menü → Part Design → LinearPattern
```

**Voraussetzung:** Das Feature muss vorher markiert sein.

### Parameter im Dialog

| Parameter | Beschreibung |
|-----------|--------------|
| **Richtung (Direction)** | Achse für das Muster: Horizontale/Vertikale Skizzenachse, Basis X/Y/Z-Achse oder Referenz auswählen |
| **Richtung umkehren** | Kehrt die Richtung des Musters um |
| **Modus** | Wahl zwischen **Gesamtlänge** (Gesamtabstand aller Elemente) oder **Versetzen** (Abstand zwischen einzelnen Elementen) |
| **Länge** | Bei Modus „Gesamtlänge": Gesamtlänge der Anordnung in mm<br>Bei Modus „Versetzen": Abstand zwischen den Elementen in mm |
| **Vorkommen (Occurrences)** | Anzahl der Kopien **inklusive Original** |

### Beispiel aus dem PDF (Abschnitt 5.1.20)

**Ausgangssituation:** Ein Body mit einer einzelnen Bohrung.

**Schritt-für-Schritt:**
1. Element **Bohrung** im Modellbaum markieren
2. Werkzeug **Lineares Muster** auswählen
3. Im Dialog folgende Werte einstellen:
   - **Richtung:** Horizontale Skizzenachse (oder Basis X-Achse)
   - **Modus:** Gesamtlänge
   - **Länge:** 80 mm
   - **Vorkommen:** 4
4. Mit **OK** bestätigen

**Ergebnis:** 4 Bohrungen in einer Reihe, gleichmäßig über 80 mm verteilt. Der Abstand zwischen den Bohrungen beträgt automatisch 80 mm ÷ (4-1) = 26,67 mm.

**Alternative mit Modus „Versetzen":**
- **Modus:** Versetzen
- **Länge (Spacing):** 20 mm (Abstand zwischen den Bohrungen)
- **Vorkommen:** 5

→ Ergebnis: 5 Bohrungen mit je 20 mm Abstand = Gesamtlänge 80 mm

**Hinweis:** Das Ausgangsobjekt wird mitgezählt! Bei 5 Vorkommen erhält man 1 Original + 4 Kopien = 5 Elemente insgesamt.

---

## 3. Polares Muster (PolarPattern)

### Beschreibung
Mit dem Werkzeug **Polares Muster** wird eine kreisförmige Anordnung von Features erzeugt. Die Kopien werden gleichmäßig um eine Achse verteilt. Dies wird häufig für Lochkreise, Flanschen oder Turbinenschaufeln verwendet.

### Aufruf

**Methode 1: Über das Kontextmenü**
1. Im Modellbaum das/die zu kopierende(n) Feature(s) markieren (mit Strg-Taste für Mehrfachauswahl)
2. Rechtsklick auf das Feature
3. Im Kontextmenü **„PolarPattern"** auswählen

**Methode 2: Über das Menü**
```
Menü → Part Design → PolarPattern
```

### Parameter im Dialog

| Parameter | Beschreibung |
|-----------|--------------|
| **Achse (Axis)** | Rotationsachse: Basis X/Y/Z-Achse oder Referenz auswählen |
| **Richtung umkehren** | Kehrt die Drehrichtung um |
| **Modus** | Wahl zwischen **Gesamtwinkel** (z.B. 360° für Vollkreis) oder **Versatzwinkel** (Winkel zwischen den Elementen) |
| **Winkel (Angle)** | Bei Modus „Gesamtwinkel": Gesamtwinkel in Grad (360° = Vollkreis)<br>Bei Modus „Versatzwinkel": Winkel zwischen den Kopien |
| **Vorkommen (Occurrences)** | Anzahl der Kopien **inklusive Original** |

### Beispiel aus dem PDF (Abschnitt 5.1.21)

**Ausgangssituation:** Ein Flansch mit einer Bohrung und einer Fase.

**Schritt-für-Schritt:**
1. Zwei Elemente im Modellbaum markieren: **Bohrung** und **Fase** (Strg-Taste gedrückt halten)
2. Werkzeug **Polares Muster** auswählen
3. Im Dialog folgende Werte einstellen:
   - **Achse:** Basis Z-Achse (senkrecht zur Flanschebene)
   - **Modus:** Gesamtwinkel
   - **Winkel:** 360° (vollständiger Kreis)
   - **Vorkommen:** 8
4. Mit **OK** bestätigen

**Ergebnis:** 8 Bohrungen (mit Fasen) gleichmäßig auf einem Kreis verteilt. Der Winkelabstand beträgt automatisch 360° ÷ 8 = 45° zwischen den Bohrungen.

**Typische Achsenwahl:**
- **Z-Achse:** Vertikale Anordnung (von oben gesehen kreisförmig)
- **X-Achse:** Anordnung um die Vorwärts-Rückwärts-Achse
- **Y-Achse:** Anordnung um die Links-Rechts-Achse

**Beispiel Lochkreis mit 6 Bohrungen:**
- **Vorkommen:** 6
- **Winkel:** 360°
- **Ergebnis:** 6 Bohrungen mit je 60° Abstand

---

## 4. Verrundung / Abrundung (Fillet)

### Beschreibung
Das Werkzeug **Verrundung** (Fillet) rundet einzelne Kanten, ganze Flächen oder alle Kanten eines Bodys mit einem wählbaren Radius ab. Verrundungen werden verwendet für:
- **Design:** Modernes, wertiges Aussehen
- **Sicherheit:** Keine scharfen Kanten
- **Ergonomie:** Angenehme Haptik
- **Technik:** Spannungsreduktion, höhere Festigkeit

### Aufruf

**Methode 1: Über das Menü**
```
Menü → Part Design → Create a fillet
```

**Methode 2: Über die Werkzeugleiste**
- Fillet-Icon in der Werkzeugleiste anklicken

**Methode 3: Nach Kantenauswahl**
1. Kanten im 3D-Fenster anklicken (mit Shift für Mehrfachauswahl)
2. Dann Fillet-Werkzeug wählen

### Parameter im Dialog

| Parameter | Beschreibung |
|-----------|--------------|
| **Ausgewählte Kanten** | Liste der Kanten, die verrundet werden sollen (durch Anklicken im 3D-Fenster) |
| **Radius** | Radius der Verrundung in mm (z.B. 2 mm) |
| **Alle Kanten verrunden** | Option: Wenn aktiviert, werden alle Kanten des Bodys verrundet |

### Beispiel aus dem PDF (Abschnitt 5.1.14)

**Ausgangssituation:** Ein Pleuel mit scharfen Kanten.

**Schritt-für-Schritt:**
1. Datei mit Pleuel laden
2. Die **hintere obere Kante** im 3D-Fenster anklicken
3. Werkzeug **Verrundung** wählen
4. Im Dialog:
   - **Radius:** 7 mm eingeben
   - Mit **OK** bestätigen
5. Für weitere Verrundung: In die **Fläche der Verrundung** klicken
6. Im Dialog:
   - **Radius:** 3 mm
   - Mit **OK** bestätigen

**Ergebnis:** Die ausgewählten Kanten sind mit den entsprechenden Radien abgerundet.

**Tipp für Mehrfachauswahl:**
- Erste Kante anklicken
- **Shift gedrückt halten** und weitere Kanten anklicken
- Alle ausgewählten Kanten werden grün/rot hervorgehoben
- Dann im Dialog Radius eingeben

**Beispiel: Alle Kanten eines Quaders abrunden**
- Quader hat 12 Kanten (4 oben, 4 unten, 4 vertikal)
- Mit Shift+Klick alle gewünschten Kanten markieren
- Radius 2 mm eingeben
- Alle Kanten werden gleichzeitig verrundet

---

## 5. Fase (Chamfer)

### Beschreibung
Das Werkzeug **Fase** (Chamfer) schrägt einzelne Kanten, alle Kanten einer Fläche oder alle Kanten eines Bodys ab. Im Gegensatz zur Verrundung (rund) ist die Fase eine **planare Abschrägung**. Fasen werden verwendet für:
- **Montage:** Leichtere Passung von Teilen
- **Gratreduzierung:** Vermeidung von scharfen Kanten nach Bearbeitung
- **Funktionale Kanten:** Z.B. an Bohrungen, Gewindeeingängen
- **Design:** Technisches, kantiges Aussehen

### Aufruf

**Methode 1: Über das Menü**
```
Menü → Part Design → Create a chamfer
```

**Methode 2: Über die Werkzeugleiste**
- Chamfer-Icon in der Werkzeugleiste anklicken

**Methode 3: Nach Kantenauswahl**
1. Kanten im 3D-Fenster anklicken (mit Shift/Strg für Mehrfachauswahl)
2. Dann Chamfer-Werkzeug wählen

### Parameter im Dialog

| Parameter | Beschreibung |
|-----------|--------------|
| **Ausgewählte Kanten** | Liste der Kanten, die gefast werden sollen |
| **Typ** | **Gleicher Abstand:** Symmetrische Fase<br>**Zwei Distanzen:** Unterschiedliche Abstände<br>**Distanz und Winkel:** Fasenabstand und Fasenwinkel |
| **Größe (Size)** | Größe der Fase in mm (bei Typ „Gleicher Abstand") |
| **Alle Kanten verwenden** | Option: Alle Kanten des Bodys fasen |

### Beispiel aus dem PDF (Abschnitt 5.1.15)

**Ausgangssituation:** Ein Pleuel mit kreisförmigen Durchbrüchen.

**Schritt-für-Schritt:**
1. Datei mit Pleuel laden
2. Die **obere Kante** des ersten kreisförmigen Durchbruchs anklicken
3. **Strg-Taste gedrückt halten** und die obere Kante des zweiten Durchbruchs anklicken
4. Werkzeug **Fase** wählen
5. Im Dialog:
   - **Typ:** Gleicher Abstand
   - **Größe:** 2 mm
   - Mit **OK** bestätigen

**Ergebnis:** Beide Bohrungskanten sind mit einer 2 mm-Fase versehen.

**Weitere Variante (Kranhaken-Beispiel, Abschnitt 5.6.4):**
- Zwei Flächen der Öse auswählen (mit Strg-Taste)
- Chamfer-Werkzeug wählen
- Typ: Gleicher Abstand, Größe: 1 mm
- Ergebnis: Fasen an den Kanten der Öse

**Unterschied Fillet vs. Chamfer:**

| Aspekt | Fillet (Verrundung) | Chamfer (Fase) |
|--------|---------------------|----------------|
| Form | Glatter Radius | Flache Anschrägung |
| Verwendung | Design, Ergonomie | Funktion, Montage |
| Beispiel | Außenkanten von Gehäusen | Bohrungseingänge |

---

## 6. Pad (Aufpolsterung)

### Beschreibung
Das Werkzeug **Pad** (Aufpolsterung) ist eines der grundlegendsten Modellierungswerkzeuge. Es extrudiert eine 2D-Skizze in die dritte Dimension und erzeugt Volumen. Obwohl Pad nicht explizit Teil von Modul 6 ist, wird es als Basiswerkzeug für alle Übungen benötigt.

### Aufruf
```
Menü → Part Design → Create a pad
```

### Parameter
- **Typ:** Dimension, Bis zur letzten, Bis zur nächsten, etc.
- **Länge:** Extrusionshöhe in mm
- **Symmetrisch zu einer Ebene:** Option für beidseitige Extrusion
- **Umgekehrt:** Richtung umkehren

---

## 7. Pocket (Vertiefung)

### Beschreibung
Das Werkzeug **Pocket** (Vertiefung) extrudiert eine Skizze in einen vorhandenen Body und erzeugt eine Aussparung oder Vertiefung.

### Aufruf
```
Menü → Part Design → Create a pocket
```

### Parameter
- **Typ:** Dimension, Durch alles, Bis zur ersten, etc.
- **Länge:** Tiefe der Vertiefung in mm
- **Umgekehrt:** Richtung umkehren

---

## Zusammenfassung: Menübefehle auf einen Blick

| Funktion | Menüpfad | Shortcut/Alternative | Wichtigste Parameter |
|----------|----------|---------------------|----------------------|
| **Spiegeln** | Part Design → Mirrored | Rechtsklick → Mirrored | Ebene (Mirror plane) |
| **Lineares Muster** | Part Design → LinearPattern | Rechtsklick → LinearPattern | Richtung, Modus, Länge, Vorkommen |
| **Polares Muster** | Part Design → PolarPattern | Rechtsklick → PolarPattern | Achse, Modus, Winkel, Vorkommen |
| **Verrundung** | Part Design → Create a fillet | Werkzeugleiste, Rechtsklick | Radius, Kantenauswahl |
| **Fase** | Part Design → Create a chamfer | Werkzeugleiste, Rechtsklick | Typ, Größe, Kantenauswahl |
| **Pad** | Part Design → Create a pad | Werkzeugleiste | Typ, Länge |
| **Pocket** | Part Design → Create a pocket | Werkzeugleiste | Typ, Länge |

---

## Tipps aus der Praxis

### Reihenfolge der Features
Die richtige Reihenfolge ist wichtig für ein erfolgreiches Modell:

1. **Basis erstellen** (Pad)
2. **Aussparungen/Bohrungen** (Pocket)
3. **Spiegeln** (Mirror) – **VOR** Mustern anwenden!
4. **Muster** (LinearPattern / PolarPattern)
5. **Verfeinerungen** (Fillet)
6. **Details** (Chamfer)

**Warum diese Reihenfolge?**
- Spiegeln wirkt auf ein einzelnes Feature
- Pattern basiert auf bereits gespiegelten Elementen
- Fillet & Chamfer kommen zum Schluss, um Berechnungskomplexität zu reduzieren

### Häufige Fehler und Lösungen

**Problem:** Spiegelung erscheint an falscher Stelle
- **Lösung:** Andere Spiegelungsebene wählen (XY, XZ oder YZ)

**Problem:** Lineares Muster hat falsche Anzahl
- **Lösung:** Vorkommen prüfen (Original wird mitgezählt!)

**Problem:** Fillet kann nicht angewendet werden
- **Lösung:** Radius zu groß → verkleinern

**Problem:** Polares Muster ist nicht gleichmäßig
- **Lösung:** Winkel auf 360° für Vollkreis setzen