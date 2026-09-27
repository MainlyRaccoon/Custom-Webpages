# TrashCats Rezeptbuch

Eine einzelne, selbstgebaute Rezeptsammlung — kein Build-System, keine Abhängigkeiten außer Google Fonts.

## Seite

| Datei         | Beschreibung                                                      |
| ------------- | ------------------------------------------------------------------ |
| `index.html`  | Rezeptbuch mit Suchfunktion, Filter-Pills und Rezept-Detailansicht |

---

## Regeln

### 1. Datum der letzten Aktualisierung — oben rechts

Die Seite zeigt in der **oberen rechten Ecke** ein Badge mit dem Datum der letzten inhaltlichen Aktualisierung (`.last-updated` im `<body>`). Anpassen, sobald ein Rezept hinzugefügt, entfernt oder inhaltlich geändert wird. Reine CSS/Design-Fixes zählen nicht als inhaltliche Aktualisierung.

### 2. Neues Rezept eintragen

Jedes Rezept ist ein Objekt im `recipes`-Array in `index.html`:

```
{
  icon: "🍞",              // Emoji als Icon
  name: "Titel",           // Angezeigter Rezeptname
  category: "Brot & Gebäck", // Hauptkategorie
  tags: ["Brot", "Vegan"], // Werden automatisch zu Filter-Pills
  time: "10–24 Std Gare + 25–30 Min Backzeit",
  difficulty: "Einfach",   // Einfach / Mittel / Schwer
  desc: "Kurzbeschreibung für die Karte.",
  ingredients: [
    "500 g Mehl",
    "300 ml Wasser"
  ],
  steps: [
    "Teig kneten: Beschreibung des Schritts.",
    "Backen: Beschreibung des Schritts."
  ],
  notes: "Optionale Tipps oder Varianten." // Feld weglassen, wenn nicht nötig
}
```

Der Teil eines Steps vor dem ersten Doppelpunkt wird in der Detailansicht automatisch fett dargestellt (z.B. **Teig kneten:**).

### 3. Allgemeine Konventionen

- Die Seite ist eine **einzelne HTML-Datei** (CSS + JS inline, kein Build-Schritt).
- Sprache: **Deutsch** (`<html lang="de">`).
- Google Fonts sind erlaubt (via `@import`), keine anderen externen Abhängigkeiten.
- Theme: Raccoon 🦝 + Black Cat 🐈‍⬛ — Orange (`--accent`) für den Waschbären, Violett (`--cat`) für die Katze, dunkler Hintergrund.

---
