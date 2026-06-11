# BlackChaos Craft

Ein Voxel-Sandbox-Spiel im Minecraft-Stil — komplett im Browser, eine einzige HTML-Datei.
Zusätzlich zu den klassischen Bau-Optionen gibt es **Panzer** und **Flugzeuge**.

## ▶ Jetzt spielen

**Live im Browser:** https://rafaelmitschke-ai.github.io/blackchaos-craft/

(Wird über GitHub Pages bereitgestellt — nach dem ersten Push kann der Link ein paar Minuten brauchen, bis er aktiv ist. Funktioniert am besten in Chrome oder Edge am Desktop.)

## Nutzung

### Variante 1 — direkt im Browser (am einfachsten)
Den Live-Link oben öffnen, auf **„Klicken zum Starten"** klicken (aktiviert die Maussteuerung) und loslegen.

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

- Prozedural generierte Welt (96×96) mit Hügeln, Seen, Stränden und Bäumen
- Blöcke abbauen und setzen (9 Blocktypen, inkl. lila „Chaos"-Block)
- Kreativmodus mit Hotbar (Tasten 1–9 oder Mausrad)
- **Panzer**: fahrbar, Kanone zerstört Blöcke mit Explosionen
- **Flugzeug**: Start, Flug, Bordkanone und Bomben
- Düster-lila „BlackChaos"-Himmel mit Chaos-Sonne und Sternen

## Steuerung

| Taste | Aktion |
|---|---|
| WASD | Bewegen |
| Leertaste | Springen |
| Shift | Sprinten |
| Maus | Umsehen |
| Linksklick | Block abbauen |
| Rechtsklick | Block setzen |
| 1–9 / Mausrad | Block auswählen |
| E | Fahrzeug ein-/aussteigen |
| T / P | Panzer / Flugzeug spawnen |

**Panzer:** W/S fahren · A/D lenken · Leertaste oder Klick = Kanone
**Flugzeug:** W/S Gas · Maus = nicken/gieren · A/D = gieren · Klick = MG · Leertaste = Bombe

## Technik

- Einzelne `index.html`, kein Build-Schritt
- [Three.js](https://threejs.org/) r149 (via CDN) für das WebGL-Rendering
- Eigene Voxel-Engine mit Chunk-Meshing, prozeduraler Terrain-Generierung (fBm-Noise) und einfacher Fahrzeugphysik
