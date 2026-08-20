# 🎮 Browser-Games

Kleine Browsergames — **direkt im Browser spielbar, ohne Installation, ohne Build-Tools.**
Jedes Spiel ist eine einzelne, eigenständige HTML-Datei (HTML + CSS + JS inline).

> **Live spielen:** <https://flathack.github.io/BrowserGames/>

## 🕹️ Die Spiele

| Spiel | Datei | Beschreibung |
|-------|-------|--------------|
| 🐍 Snake | [`snake.html`](snake.html) | Der Klassiker — mit Maus, Tastatur und Touch steuerbar. |
| 🚒 Brandquadrat | [`feuer.html`](feuer.html) | Feuerwehraufgabe — Brände löschen, Zeit im Blick behalten. |
| 🧺 Frucht-Fang | [`frucht.html`](frucht.html) | Für die ganz Kleinen (4–6 J.) — Korb schieben, Früchte auffangen. Groß, langsam, ohne Zeitdruck, mit viel Lob. |

### 🧸 Kleinkind-Kiste (4–6 Jahre) — Ideen & Baustellen

Spiele für die ganz Kleinen: groß, langsam, ohne Zeitdruck und mit viel Lob.
**Frucht-Fang ist fertig und spielbar** 🎉 (siehe Tabelle oben). Noch als Platzhalter in [`index.html`](index.html) hinterlegt:

- 💦 **Blubber-See** — Fische nach oben schwimmen lassen
- 🐰 **Wegweiser** — Hase zur Karotte begleiten
- 🎨 **Farb-Blitz** — „Zeig mir Rot!" — passende Kachel antippen

## 📦 Weitere Spiel-Ideen (Backlog)

- 🏰 **Tower-Defence** — Türme platzieren und upgraden, Wellen abwehren
- ☄️ **Asteroids** — Raumschiff drehen, schießen, Asteroiden zerspringen lassen
- 🎱 **Flipper** — Schläger per Touch/Klick/Leertaste, Kugel kontrollieren

## 🚀 Schnell starten

**Option A — Online (empfohlen):**
Einfach im Browser öffnen: <https://flathack.github.io/BrowserGames/>

**Option B — Lokal:**
1. Repo klonen:
   ```bash
   git clone https://github.com/flathack/BrowserGames.git
   cd BrowserGames
   ```
2. `index.html` per Doppelklick im Browser öffnen — fertig.
   Kein Server, kein npm, keine Abhängigkeiten.

## 📱 Plattform & Steuerung

Jedes Spiel muss auf allen drei Plattformen spielbar sein:

| Plattform | Steuerung |
|-----------|-----------|
| 💻 PC | **Maus** und **Tastatur** |
| 📱 iPhone / 📟 iPad (iOS) | **Touch** |

**Touchscreen-Kompatibilität ist Pflicht.** Die Details (Pointer-Events, Touch-Targets, Viewport, `touch-action`, `prefers-reduced-motion`, Verifikation) stehen in [`agents.md`](agents.md).

## 📁 Struktur

```
BrowserGames/
├── index.html      # Hauptseite — verlinkt auf alle Spiele + Ideen
├── snake.html      # 🐍 Snake
├── feuer.html      # 🚒 Brandquadrat
├── agents.md       # Regeln & Definition-of-Done für alle Spiele
└── readme.md       # Diese Datei
```

## ➕ Neues Spiel hinzufügen

1. Neue Datei `spielname.html` im Projektordner anlegen.
2. Alle PFLICHTen aus [`agents.md`](agents.md) abhaken (vor allem: **Touch + Maus + Tastatur**, iOS/PC).
3. In `index.html` als fertige Karte eintragen (der Zähler oben passt sich automatisch an).
4. Verifikation durchführen (s. `agents.md`), commit + push — GitHub Pages baut automatisch nach.

## 🛠️ Technik

- Reines HTML/CSS/JS, keine Abhängigkeiten, keine Build-Schritte.
- GitHub Pages als Hosting (Repo `main`-Branch, Root-Pfad).
- Framerate-unabhängige Spiellogik (Delta-Time).
- `prefers-reduced-motion` wird respektiert.

---

Alle Games programmiert von **Hermes Agent** mit dem **Qwen 3.8 27B-Modell.**
