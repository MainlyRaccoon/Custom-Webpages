# Mainlys Custom Webpages

Sammlung selbst gebauter Webseiten — von Gaming-Guides bis Tools.
Jede Seite ist eine eigenständige HTML-Datei ohne Build-System.

## Seiten

| Datei | Beschreibung |
|---|---|
| `index.html` | Hub-Übersicht mit Suchfunktion und Filter-Pills |
| `payday2-dlc-guide.html` | PAYDAY 2 Waffen-DLC Guide mit Ampel-Bewertung |
| `warhammer-dlc-guide.html` | Total War: Warhammer DLC Guide (WH I / II / III) |

---

## Regeln für neue Seiten

### 1. Datum der letzten Aktualisierung — oben rechts, jede Seite

Jede HTML-Seite muss in der **oberen rechten Ecke** ein Badge mit dem Datum der letzten inhaltlichen Aktualisierung zeigen.

**HTML** — direkt nach `<body>`, vor dem ersten Layout-Element:
```html
<div class="last-updated">Aktualisiert: <span>Monat JJJJ</span></div>
```

**CSS** — ans Ende des `<style>`-Blocks, vor dem letzten `@media`-Block:
```css
.last-updated{
  position: fixed;
  top: 0; right: 0;
  z-index: 100;
  background: rgba(0,0,0,0.88);
  backdrop-filter: blur(4px);
  border-bottom-left-radius: 4px;
  border: 1px solid <Linienfarbe der Seite>;
  border-top: none; border-right: none;
  padding: 5px 12px;
  font-size: 10px;
  letter-spacing: 0.08em;
  color: <gedimmte Textfarbe der Seite>;
  font-family: <Schriftart der Seite>;
  pointer-events: none;
}
.last-updated span{ color: <Akzentfarbe der Seite>; }
```

Das Datum anpassen, sobald sich **Inhalte** ändern (neue Einträge, korrigierte Daten).
Reine CSS/Design-Fixes zählen nicht als inhaltliche Aktualisierung.

---

### 2. Neue Seite im Hub eintragen

Jede neue Seite bekommt einen Eintrag im `sites`-Array in `index.html`:

```js
{
  icon: "🎮",           // Emoji als Icon
  name: "Titel",        // Angezeigter Name
  desc: "Kurzbeschreibung der Seite.",
  tags: ["Gaming"],     // Werden automatisch zu Filter-Pills
  url: "dateiname.html" // Relativer Pfad
}
```

---

### 3. Allgemeine Konventionen

- Alle Seiten sind **einzelne HTML-Dateien** (CSS + JS inline, kein Build-Schritt).
- Sprache: **Deutsch** (`<html lang="de">`).
- Google Fonts sind erlaubt (via `@import`), keine anderen externen Abhängigkeiten.
- Jede Seite hat einen **"← Zurück zum Hub"**-Link zurück zu `index.html`.
