# Bewerbungs-Dashboard

Interaktives Dashboard zur Verwaltung von Bewerbungen mit echtem Zustandsmanagement und Persistierung.

## Features

- **Dynamische Statusverwaltung**: Bewerbungen zwischen Kategorien verschieben
- **Lokale Persistierung**: Daten werden im Browser gespeichert (localStorage)
- **Echtzeitaktualisierung**: Zahler und Listen aktualisieren sich sofort
- **Ablehngründe dokumentieren**: Gründe für nicht verfolgte Bewerbungen speichern
- **Responsive Design**: Funktioniert auf Desktop, Tablet und Mobile
- **Dark Mode Support**: Automatische Anpassung an Systemeinstellung
- **Farbpalette**: Einheitliches Design mit Gedämpftes Blaugrau

## Kategorien

1. **Zu bearbeiten** (📝) – Neu erfasste, noch nicht versandte Bewerbungen
2. **Bereit** (✅) – Fertig für Versand, warten auf Go
3. **Versendet** (📤) – Bereits versendete Bewerbungen
4. **Nicht verfolgt** (❌) – Abgelehnte oder nicht verfolgte Stellen
5. **Rückmeldung** (💬) – Bewerbungen mit Rückmeldung eingegangen
6. **Ergebnis** (🏆) – Finales Ergebnis (Zusage, Ablehnung)

## Funktionsweise

### Buttons in "Zu bearbeiten"

- **✓ Raus**: Bewerbung zu "Versendet" verschieben
- **✗ Nicht**: Bewerbung zu "Nicht verfolgt" verschieben (mit Grund)

### Datenspeicherung

Alle Daten werden lokal im Browser gespeichert (`localStorage`). Das bedeutet:

- Daten bleiben erhalten, auch wenn du die Seite neu lädst
- Daten sind nur auf diesem Computer/Browser verfügbar
- Um die Daten zu backup-en, kannst du die Developer Tools öffnen und `localStorage` exportieren

### Datenstruktur

Jede Bewerbung hat folgende Struktur:

```javascript
{
    id: 1,
    name: "Schuljobs.ch – BVJ Bern",
    type: "Initiative" | "Ausschreibung",
    category: "zu-bearbeiten" | "bereit" | "versendet" | "nicht-verfolgt" | "rueckmeldung" | "ergebnis",
    date: "ISO8601-Timestamp",
    reason: "Grund (nur bei 'nicht-verfolgt')" | null
}
```

## Installation & Verwendung

### Lokal testen

1. Datei `index.html` im Browser öffnen
2. Dashboard sollte sofort funktionieren

### Auf GitHub Pages deployen

1. Neues Repository erstellen (z.B. `bewerbungen-dashboard`)
2. Diese Dateien hochladen
3. Settings → Pages → Source auf `main` Branch einstellen
4. Dashboard ist dann unter `https://dudewithdog.github.io/bewerbungen-dashboard/` erreichbar

## Technologie

- **HTML5** – Semantisches Markup
- **CSS3** – Modern Styling mit CSS Custom Properties
- **Vanilla JavaScript** – Keine Dependencies
- **localStorage API** – Clientseitige Datenpersistierung

## Farben (Design Tokens)

```css
--primary: #4A5F3B      /* Gedämpftes Blaugrau */
--accent: #6F7353       /* Olivgrün */
--accent-dark: #5A4634  /* Dunkelbraun */
--secondary: #3D5F5C    /* Petrol/Teal */
```

## Roadmap

- [ ] Materialien & Ressourcen (CV-Versionen, Job-Plattformen, Dokumentation)
- [ ] 6-Phasen-Prozess (ausklappbar)
- [ ] Frageleitfaden (ausklappbar)
- [ ] Export-Funktion (JSON, CSV)
- [ ] Integration mit bewerbungen.md (auto-sync)
- [ ] Tagging & Filtering
- [ ] Suchfunktion
- [ ] Erinnerungen/Notifications

## Lizenz

Privat – Erik Roedenbeck (dudewithdog)
