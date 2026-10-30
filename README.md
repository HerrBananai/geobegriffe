# Geo-Begriffe – Geographie lernen (Web-App)

Statische PWA zum Lernen von **525 Geographie-Fachbegriffen** (Q12/Q13) – Karteikarten,
Quiz und Paare zuordnen, Offline-Speicherung, Dark Mode.

Kein Build, kein Framework: reines HTML/CSS/JS. Der Ordnerinhalt **ist** die Website.

## Deploy auf Vercel (1 Klick)

[![Vercel deployen](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/HerrBananai/geobegriffe)

Oder manuell:

1. <https://vercel.com/new> → **Import Git Repository** → dieses Repo wählen
2. Framework-Preset: **Other** (kein Build-Command, Output-Directory `.`)
3. **Deploy** – fertig, die App läuft unter `<projektname>.vercel.app`

Die Einstellungen stehen fertig in `vercel.json` (inkl. Cache-Header, damit das
Service-Worker-Update nicht im Browser-Cache hängen bleibt).

## Eigene Domain (optional, später)

1. Vercel → Projekt → **Settings → Domains** → Domain eintragen
2. Beim Domain-Anbieter DNS setzen (entweder CNAME auf `cname.vercel-dns.com`
   oder A-Record auf `76.76.21.21`)
3. Vercel stellt automatisch HTTPS aus

## Abi-Quiz (neu)

Tab **„Abi"** (oder Startseite → „Abi-Quiz starten"): 36 Multiple-Choice-Fragen
zu Klima, Tropen, Polare, Mittlere Breiten, Hochgebirge, Naturkatastrophen,
Entwicklung, Globalisierung, Bevölkerung, Urbanisierung und Migration – mit
Erklärung nach jeder Antwort, XP- und Edelstein-Belohnung. Fragen basieren auf
den Lösungen zu „Diercke Geographie 12 Bayern" (Westermann).

Wechseln in der App unter **Startseite → Einstellungen → Design**:

- **Duolingo** (Start) – Nunito, Grün, 3D-Buttons
- **Vivid** – Plus Jakarta Sans, Mesh-Verlauf, Glas-Karten
- **Swiss** – Space Grotesk, Schwarz-Weiß + Signalrot

Die Styles stehen in `styles-duo.css` (Duolingo) und `styles-designs.css`
(Vivid/Swiss) über `html[data-design="…"`-Selektoren; `styles.css` ist die
gemeinsame Basis.
`styles-xp.css` (Retro) und `styles-archive-designs.css` (verworfene Entwürfe)
sind **nicht** eingebunden – nur zur Aufbewahrung.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Einstieg, Design-/Theme-Vorauswahl |
| `app.js` | komplette App (Daten, Ansichten, Spiele) |
| `sw.js` | Service Worker, Offline-Cache (Version `geo-begriffe-v8`) |
| `data/terms.json` | 525 Begriffe inkl. Definitionen |
| `manifest.webmanifest` | PWA-Metadaten |
