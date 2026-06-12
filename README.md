# BlackChaos Craft

Ein Voxel-Kriegsspiel im Minecraft-Stil — komplett im Browser, eine einzige HTML-Datei.
Riesige Welt, **6 steuerbare Fahrzeuge** (Panzer, Jeep, Flugzeug, Helikopter, Kanonenboot, U-Boot), zwei Spielmodi.

## ▶ Jetzt spielen

**Live im Browser:** https://rafaelmitschke-ai.github.io/blackchaos-craft/

(Wird über GitHub Pages bereitgestellt — nach einem Push kann der Link ein paar Minuten brauchen, bis er aktiv ist. Funktioniert am besten in Chrome oder Edge am Desktop; Touch-Steuerung für Handy/Tablet ist eingebaut.)

## Spielmodi

| Modus | Beschreibung |
|---|---|
| ⚔ **Kriegsmodus** | Überlebe endlose **Gegner-Wellen** (5 Gegnertypen, **Boss alle 5 Wellen**). Abschüsse und Abbauen bringen **Kristalle ◆** fürs Crafting. Game Over zählt deinen Score & Highscore. |
| 🏗 **Kreativmodus** | Freies Bauen ohne Gegner und ohne Schaden. Alle Fahrzeuge und Craftings **kostenlos** (Tasten T/P/H/J/B/U). |
| 🌐 **CO-OP** | Spiele **mit Freunden in einer Welt** (Krieg oder Kreativ)! Einer hostet und teilt den 5-stelligen **Raum-Code**, die anderen treten damit bei — direkte P2P-Verbindung via WebRTC, kein Server-Setup nötig. Stirbst du im Co-op, respawnst du am Spawn (−30 % Kristalle). |

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

- **Riesenwelt** — 432×432 Blöcke (20× Fläche), prozedural: Hügel, Seen, Strände, Schneeberge, **Wüsten**, Wälder, Erz-Adern und **Höhlensysteme** im Untergrund
- **Erkundung lohnt sich** — ~70 Ruinen & Häuser mit **Schatztruhen** (20–60 Kristalle, 15 % Jackpot mit Vollheilung); nachts erwachen im Kriegsmodus **Chaos-Schleicher**
- **Minimap** — Gelände, Fahrzeuge (lila), Gegner (rot), Schleicher (pink), Türme und dein Blickwinkel-Pfeil; oben rechts
- **Chunk-Streaming** — nur die Welt um dich herum wird geladen: Start in ~1 Sekunde, flüssige FPS auch auf schwächeren PCs; **Sichtweite einstellbar** (Startbildschirm: 4–10 Chunks, dazu Maus-Empfindlichkeit)
- **Co-op-Multiplayer** — P2P via WebRTC (PeerJS): hosten, Raum-Code teilen, gemeinsam bauen & kämpfen; geteilte Welt, synchronisierte Fahrzeuge, Gegner und Explosionen
- **8 Fahrzeuge mit HP & Zerstörung** — **Panzer**, **Jeep**, **Flugzeug**, **Helikopter**, **Kanonenboot**, **U-Boot**, **Artillerie** (Steilfeuer) und **Kampf-Mech** (Doppel-MG + Raketen, klettert 2 Blöcke); zerstörte Fahrzeuge hinterlassen Wracks, Reparatur craftbar
- **5 Gegnertypen + Bosse** — Panzer, Flugzeuge, Infanterie, Kampfhelikopter; alle 5 Wellen ein **Boss** mit Lebensbalken und Dreifach-Salven
- **Waffen-Arsenal zu Fuß** — Blaster (3 Upgrade-Stufen), **Schrotflinte**, **Sniper** (Q wechselt), **Granaten** (G), **platzierbare Minen** (V), Raketenwerfer (R)
- **KI-Soldaten** — craftbare Verbündete, die dir folgen und mitkämpfen (max 5)
- **Großes Crafting-System** — 20 Rezepte: Fahrzeuge, Waffen, Geschütztürme, Heilung, Max-HP, Reparatur, Jetpack
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
| F / Q | Waffe abfeuern / wechseln |
| G / V / R | Granate · Mine · Rakete (craftbar) |
| 1–9 / Mausrad | Block auswählen (15 Typen) |
| E | Fahrzeug ein-/aussteigen |
| C | Crafting-Menü (20 Rezepte) |
| T / P / H / J / B / U | Panzer / Flugzeug / Heli / Jeep / Boot / U-Boot (nur Kreativmodus) |
| K / L | Spiel speichern / laden |
| M / N | Musik / Sound an-aus |

**Panzer:** W/S fahren · A/D lenken · Klick = Kanone
**Jeep:** wie Panzer, aber schnell · Klick = MG
**Flugzeug:** W/S Gas · Maus = nicken/gieren · A/D = gieren · Klick = MG · Leertaste = Bombe
**Helikopter:** Leertaste/Shift = hoch/runter · W/S = vor/zurück · A/D = drehen · Klick = MG
**Kanonenboot:** W/S · A/D · Klick = Kanone (nur auf Wasser)
**U-Boot:** W/S · A/D · Leertaste/Shift = auf-/abtauchen · Klick = Torpedo
**Artillerie:** langsam, aber verheerendes Steilfeuer (Klick)
**Kampf-Mech:** W/S · A/D · Klick = Doppel-MG · Leertaste = Rakete

## Co-op spielen

1. Spieler 1 wählt **🌐 CO-OP** → **Hosten** (Krieg oder Kreativ) und bekommt einen 5-stelligen Raum-Code.
2. Spieler 2 öffnet dieselbe Seite, wählt **🌐 CO-OP**, tippt den Code ein → **Beitreten**.
3. Die Welt wird automatisch übertragen (wenige Sekunden), dann spielt ihr zusammen — Mitspieler erscheinen mit cyanfarbenem Marker, auch auf der Minimap.

> Die Verbindung läuft direkt zwischen den Browsern (WebRTC). Der kostenlose PeerJS-Vermittlungsdienst wird nur für den Verbindungsaufbau genutzt. Speichern/Laden ist im Co-op deaktiviert.

## Technik

- Einzelne `index.html`, kein Build-Schritt, keine Abhängigkeiten außer Three.js (CDN)
- [Three.js](https://threejs.org/) r149 für das WebGL-Rendering
- Eigene Voxel-Engine: Chunk-Meshing (729 Chunks), prozedurales Terrain (fBm-Noise), Erz-Generierung, Fahrzeug- und Projektilphysik, Gegner-KI, TNT-Kettenreaktionen
- Speicherstände RLE-komprimiert (9 MB Weltdaten → unter 1 MB im localStorage)
- Prozeduraler Sound über die Web Audio API (keine Audiodateien nötig)
