# AGENTS.md — Browser-Games

Regeln und Kontext für alle Agenten, die in diesem Projekt arbeiten.
Jedes neue Spiel MUSS diese Vorgaben einhalten, bevor es als fertig gilt.

## Ziel

Kleine Browsergames als **einzelne, eigenständige HTML-Dateien** (HTML + CSS + JS inline, keine Build-Tools, keine Abhängigkeiten, keine Installation). Jede Spiel-Datei liegt direkt im Projektordner und wird in `index.html` verlinkt.

## Pflichten (PFLICHT = muss, sonst ist das Spiel nicht fertig)

### Plattform- & Eingabekompatibilität

- **Spielbar auf iPad und iPhone** (Safari/iOS).
- **Spielbar auf dem PC** (Desktop-Browser) **mit Maus und Tastatur**.
- **Touchscreen-Kompatibilität ist Pflicht.** Jedes Steuerbare Element muss per Touch bedienbar sein:
  - `pointer`-Events statt reiner `mouse`-Events (`pointerdown`/`pointermove`/`pointerup`), damit Touch, Stift und Maus identisch behandelt werden.
  - Touch-Targets groß genug halten (mind. ~44×44 px).
  - Kein reines Hover-Dependent-Design: nichts Wesentliches darf nur per `:hover` erreichbar sein.
  - `touch-action: none` auf dem Spielbereich/Canvas, um Scroll- und Zoom-Gesten während des Spielens zu unterdrücken.
  - Keine Rechtsklick-/Context-Menu-Abhängigkeiten.

### Technik

- `viewport`-Meta-Tag mit `width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no`.
- Responsive: muss in **Hoch- UND Querformat** sowie auf Desktop-Breiten funktionieren; kein fester Pixel-Layout.
- `prefers-reduced-motion` respektieren (Animationen reduzieren).
- Keine Konsole-Errors (sauberes `console`-Log) und keine unbehandelten Exceptions.
- Tastatursteuerung: Fokus-States sichtbar (`:focus-visible`), relevante Aktionen per Pfeiltasten/Leertaste/Enter erreichbar.
- Spiellogik framerate-unabhängig halten (Delta-Time), nicht an `requestAnimationFrame`-Aufrufe koppeln.
- Sounds nur optional (z. B. erst nach erstem User-Input starten, iOS-Autoplay-Regeln beachten) und mit Stummschalt-Möglichkeit.

### Stil

- Dunkles, konsistentes Design wie die bestehenden Spiele (`index.html`, `snake.html`, `feuer.html`).
- Deutsch als Standardsprache für UI-Texte.
- Nach dem Hinzufügen: Karte in `index.html` ergänzen (Zähler oben zählt automatisch).

### Verifikation vor „fertig"

- In einem echten Browser (oder Headless-Chromium) öffnen: Rendering, saubere Console, Steuerung per **Maus**, per **Tastatur** und per **Touch** (pointer-Events simuliert) prüfen.
- Auf schmalem Viewport (z. B. 400 px) und quer (z. B. 800×400) auf Layout-Brüche prüfen.

## Spiel-Ideen (Backlog)

Schon vorhandene Ideen für weitere Spiele:

- **Tower-Defence** — Türme platzieren und Upgrades, Wellen abwehren.
- **Asteroids** — Klassiker: Raumschiff drehen, schießen, Asteroiden zerspringen.
- **Flipper (Pinball)** — Schläger per Touch/Klick/Leertaste, Kugel kontrollieren.

Zusätzlich liegen in `index.html` unter „Ideen & Baustellen" die **Kleinkind-Ideen (4–6 Jahre)**: Blubber-See, Frucht-Fang, Wegweiser, Farb-Blitz.

## Workflow-Kurzregeln

1. Neues Spiel = eine neue `spielname.html` im Projektordner.
2. Alle PFLICHTen oben abhaken (vor allem: Touch + Maus + Tastatur, iOS/PC).
3. In `index.html` als fertige Karte eintragen (oder in „Ideen" belassen, bis es spielbar ist).
4. Verifikation ausführen und erst dann als fertig melden.
