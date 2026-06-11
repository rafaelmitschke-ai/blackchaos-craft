# BlackChaos Craft

Ein Voxel-Kriegsspiel im Minecraft-Stil — komplett im Browser, eine einzige HTML-Datei.
Baue, kämpfe und überlebe Wellen von Gegnern mit **Panzern, Flugzeugen und Helikoptern**.

## ▶ Jetzt spielen

**Live im Browser:** https://rafaelmitschke-ai.github.io/blackchaos-craft/

(Wird über GitHub Pages bereitgestellt — nach einem Push kann der Link ein paar Minuten brauchen, bis er aktiv ist. Funktioniert am besten in Chrome oder Edge am Desktop; Touch-Steuerung für Handy/Tablet ist eingebaut.)

## Spielprinzip

Überlebe immer härtere **Gegner-Wellen**. Jeder Abschuss und jeder abgebaute Block bringt **Kristalle ◆**. Im Crafting-Menü baust du davon deine Armee auf: Panzer, Flugzeuge, Helikopter, automatische Geschütztürme — oder heilst dich und erhöhst deine maximale Gesundheit. Stirbst du, ist die Runde vorbei und dein Score zählt.

## Nutzung

### Variante 1 — direkt im Browser (am einfachsten)
Den Live-Link oben öffnen, auf **„Klicken zum Starten"** klicken (aktiviert Maussteuerung + Sound) und loslegen.

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

- **Kriegs-Überlebensmodus** — Gegner-KI (Panzer & Flugzeuge), endlose Wellen, steigende Schwierigkeit, Lebensanzeige, Score & Highscore
- **Kristall-Wirtschaft & Crafting** — Kristalle durch Abbauen und Abschüsse; Fahrzeuge, Geschütztürme, Heilung und HP-Upgrades bauen
- **Drei Fahrzeuge** — fahrbarer **Panzer** (Kanone), **Flugzeug** (MG + Bomben), **Helikopter** (schwebt frei)
- **Auto-Geschütztürme** — craftbare Türme, die selbstständig auf Gegner feuern
- **Bauen wie in Minecraft** — 9 Blocktypen abbauen/setzen, Hotbar (1–9 / Mausrad)
- **Prozedurale Welt** (96×96) mit Hügeln, Seen, Stränden, Bäumen und umherstreifenden Kreaturen
- **Sound & Musik** — prozedurale Effekte (Schüsse, Explosionen, Motoren) und düsterer Soundtrack
- **Tag/Nacht-Zyklus** — wandernde Chaos-Sonne, Mond und Sterne; dynamisches Licht
- **Effekte** — Explosionen mit Terrain-Zerstörung, Mündungsfeuer, Screen-Shake, Schadens-Vignette
- **Speichern & Laden** — Welt und Fortschritt im Browser (localStorage), inkl. Autosave
- **Touch-Steuerung** — virtueller Joystick + Buttons auf Mobilgeräten

## Steuerung

| Taste | Aktion |
|---|---|
| WASD | Bewegen |
| Leertaste | Springen |
| Shift | Sprinten |
| Maus | Umsehen |
| Linksklick | Block abbauen / feuern |
| Rechtsklick | Block setzen |
| F | Zu Fuß: Blaster abfeuern |
| 1–9 / Mausrad | Block auswählen |
| E | Fahrzeug ein-/aussteigen (nächstes entern) |
| C | Crafting-Menü |
| T / P / H | Panzer / Flugzeug / Helikopter spawnen |
| K / L | Spiel speichern / laden |
| M / N | Musik / Sound an-aus |

**Panzer:** W/S fahren · A/D lenken · Leertaste oder Klick = Kanone
**Flugzeug:** W/S Gas · Maus = nicken/gieren · A/D = gieren · Klick = MG · Leertaste = Bombe
**Helikopter:** Leertaste/Shift = hoch/runter · W/S = vor/zurück · A/D = drehen · Klick = MG

## Technik

- Einzelne `index.html`, kein Build-Schritt, keine Abhängigkeiten außer Three.js (CDN)
- [Three.js](https://threejs.org/) r149 für das WebGL-Rendering
- Eigene Voxel-Engine: Chunk-Meshing, prozedurales Terrain (fBm-Noise), Fahrzeug- und Projektilphysik, Gegner-KI
- Prozeduraler Sound über die Web Audio API (keine Audiodateien nötig)
