# BlackChaos Craft

Ein Voxel-Kriegsspiel im Minecraft-Stil — komplett im Browser, eine einzige HTML-Datei.
Riesige Welt, **6 steuerbare Fahrzeuge** (Panzer, Jeep, Flugzeug, Helikopter, Kanonenboot, U-Boot), zwei Spielmodi.

## ▶ Jetzt spielen

**Live im Browser:** https://rafaelmitschke-ai.github.io/blackchaos-craft/

(Wird über GitHub Pages bereitgestellt — nach einem Push kann der Link ein paar Minuten brauchen, bis er aktiv ist. Funktioniert am besten in Chrome oder Edge am Desktop; Touch-Steuerung für Handy/Tablet ist eingebaut.)

## Spielmodi

| Modus | Beschreibung |
|---|---|
| ⚔ **Kriegsmodus** | Überlebe endlose **Gegner-Wellen**. Abschüsse und Abbauen bringen **Kristalle ◆** fürs Crafting. Game Over zählt deinen Score & Highscore. |
| 🏗 **Kreativmodus** | Freies Bauen ohne Gegner und ohne Schaden. Alle Fahrzeuge und Craftings **kostenlos** (Tasten T/P/H/J/B/U). |

## Nutzung

### Variante 1 — direkt im Browser (am einfachsten)
Den Live-Link oben öffnen, **Spielmodus anklicken** (aktiviert Maussteuerung + Sound) und loslegen.
Deine Fahrzeuge stehen direkt am Spawn — erkennbar am **lila Marker ▼** über jedem Fahrzeug.

### Variante 2 — lokal aus dem Repo
```bash
git clone https://github.com/rafaelmitschke-ai/blackchaos-craft.git
cd blackchaos-craft
```
Dann entweder `index.html` per Doppelklick öffnen, oder einen lokalen Server starten:
```bash
python -m http.server 8000
# Browser: http://localhost:8000
```
> Eine Internetverbindung ist nötig, da die 3D-Bibliothek **Three.js** über ein CDN geladen wird.

## Features

- **Riesenwelt** — 432×432 Blöcke (20× Fläche), prozedural: Hügel, Seen, Strände, Schneeberge, Wälder, Erz-Adern im Untergrund
- **6 Fahrzeuge** — **Panzer** (Kanone), **Jeep** (schnell, MG), **Flugzeug** (MG + Bomben), **Helikopter** (schwebt frei), **Kanonenboot** (Wasser), **U-Boot** (taucht, Torpedos) — alle mit lila Marker ▼, werden mitgespeichert
- **Kriegs-Überlebensmodus** — Gegner-KI, endlose Wellen, steigende Schwierigkeit, Score & Highscore — **als eigene Option** neben dem Kreativmodus
- **Großes Crafting-System** — 12 Rezepte: alle 6 Fahrzeuge, Auto-Geschütztürme, Heilung, Max-HP, Blaster-Upgrades (3 Stufen), Raketenwerfer, Jetpack
- **15 platzierbare Blocktypen** — u. a. Glas, **TNT (Kettenreaktion!)**, Lampe (leuchtet nachts), Obsidian (explosionsfest), Schnee, Eis, Chaos-Block
- **Erz-Wirtschaft** — Kohle (◆3), Eisen (◆6), Gold (◆12), Diamant (◆25) beim Abbau; selbst gesetzte Blöcke geben nichts (kein Farmen)
- **Sound & Musik** — prozedurale Effekte (Schüsse, Explosionen, Motoren, Torpedos) und düsterer Soundtrack, ganz ohne Audiodateien
- **Tag/Nacht-Zyklus** — Chaos-Sonne, Mond, Sterne, dynamisches Licht
- **Effekte** — Terrain-Zerstörung, Screen-Shake, Schadens-Vignette, Mündungsfeuer
- **Speichern & Laden** — Welt (RLE-komprimiert), Fortschritt, Fahrzeuge und Türme im Browser; Autosave jede Minute
- **Touch-Steuerung** — virtueller Joystick + Buttons auf Mobilgeräten

## Steuerung

| Taste | Aktion |
|---|---|
| WASD | Bewegen |
| Leertaste | Springen (mit Jetpack: fliegen) |
| Shift | Sprinten |
| Maus | Umsehen |
| Linksklick | Block abbauen / feuern |
| Rechtsklick | Block setzen |
| F / R | Blaster / Rakete (craftbar) |
| 1–9 / Mausrad | Block auswählen (15 Typen) |
| E | Fahrzeug ein-/aussteigen |
| C | Crafting-Menü |
| T / P / H / J / B / U | Panzer / Flugzeug / Heli / Jeep / Boot / U-Boot (nur Kreativmodus) |
| K / L | Spiel speichern / laden |
| M / N | Musik / Sound an-aus |

**Panzer:** W/S fahren · A/D lenken · Klick = Kanone
**Jeep:** wie Panzer, aber schnell · Klick = MG
**Flugzeug:** W/S Gas · Maus = nicken/gieren · A/D = gieren · Klick = MG · Leertaste = Bombe
**Helikopter:** Leertaste/Shift = hoch/runter · W/S = vor/zurück · A/D = drehen · Klick = MG
**Kanonenboot:** W/S · A/D · Klick = Kanone (nur auf Wasser)
**U-Boot:** W/S · A/D · Leertaste/Shift = auf-/abtauchen · Klick = Torpedo

## Technik

- Einzelne `index.html`, kein Build-Schritt, keine Abhängigkeiten außer Three.js (CDN)
- [Three.js](https://threejs.org/) r149 für das WebGL-Rendering
- Eigene Voxel-Engine: Chunk-Meshing (729 Chunks), prozedurales Terrain (fBm-Noise), Erz-Generierung, Fahrzeug- und Projektilphysik, Gegner-KI, TNT-Kettenreaktionen
- Speicherstände RLE-komprimiert (9 MB Weltdaten → unter 1 MB im localStorage)
- Prozeduraler Sound über die Web Audio API (keine Audiodateien nötig)
