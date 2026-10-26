# Nada Brahma – Die Welt ist Klang

Binauraler Tongenerator zur Meditation. Single-File-Build wie IRONLOG.

## Dateien
- `index.html` – komplette App
- `sw.js` – Network-First Service Worker (Version: `nadabrahma-v2`)
- `manifest.json` – PWA-Manifest
- `icon.svg`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`

## Deployment auf GitHub Pages
1. Auf GitHub neues Repo anlegen: **Repository name** `NadaBrahma`, **Public**.
2. Alle Dateien aus diesem Ordner ins Repo-Root hochladen (Add file → Upload files → Commit changes).
3. **Settings → Pages → Build and deployment**
   - **Source:** `Deploy from a branch`
   - **Branch:** `main`, Ordner `/ (root)` → **Save**
4. Nach 1–2 Minuten erreichbar unter `https://scarpenter666-design.github.io/NadaBrahma/`

## Aufs Handy
- **Android (Chrome):** Seite öffnen → Menü ⋮ → **App installieren** bzw. **Zum Startbildschirm hinzufügen**
- **iPhone (Safari):** Teilen-Symbol → **Zum Home-Bildschirm**

## Updates
Bei jeder Änderung in `sw.js` die Zeile `const VERSION = "nadabrahma-v2";` hochzählen (v2, v3 …).
Die App zeigt dann unten den Hinweis **Neue Version verfügbar → Neu laden**.

## Programme
| Programm | Dauer | Frequenz | Grundton |
|---|---|---|---|
| Kurze Pause | 5 min | 12 → 10 → 12 Hz | 220 Hz |
| Tiefenmeditation | 10 min | 10 → 6 (halten) → 10 Hz | 200 Hz |
| Fokus | 15 min | 10 → 14 (halten) → 12 Hz | 240 Hz |
| Lange Meditation | 20 min | 10 → 7 → 5 (halten) → 10 Hz | 180 Hz |
| Einschlafen | 30 min | 8 → 4 → 2 Hz, mit Rauschen | 150 Hz |

Eigene Programme: im Script das Array `PROGRAMS` erweitern. Ein Segment ist `[Dauer in s, Hz von, Hz bis, "Phasenname"]`.

## Sperrbildschirm
- Der Ton geht direkt an den Ausgang. Ein stummer `<audio>`-Loop und die Media-Session melden dem System „Medienwiedergabe“. Programme sind komplett im Audio-Thread vorgeplant.
- **Android:** läuft als installierte App normalerweise mit gesperrtem Bildschirm weiter.
- **iOS:** nicht garantiert. Safari pausiert Web-Audio teils beim Sperren. Notfalls Bildschirm an lassen (die App hält ihn per Wake Lock wach).
