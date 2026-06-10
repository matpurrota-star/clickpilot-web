# clickpilot-web

Landingpage für **ClickPilot** — statische Seite (HTML/CSS, keine Build-Tools),
gehostet über GitHub Pages.

## Lokal ansehen

Einfach `index.html` im Browser öffnen — oder ein kleiner lokaler Server:

```bash
# Python
python -m http.server 8000
# dann http://localhost:8000 öffnen
```

## Struktur

| Datei | Zweck |
|---|---|
| `index.html` | Die Landingpage (Hero, Funktionen, Sicherheit, Screenshots, Installation, FAQ) |
| `styles.css` | Design-System (übernommen aus der App: `foundations.css`), Light/Dark via OS |
| `INSTALL.md` | Eigenständige Installationsanleitung — kann als `README.md` ins `clickpilot-releases`-Repo |
| `impressum.html` / `datenschutz.html` | Rechtliche Pflichtseiten (⚠️ Platzhalter, siehe unten) |
| `assets/` | Logo + **Screenshots** (noch einzufügen) |

## Noch zu erledigen

### 1. Screenshots einfügen
Die Seite zeigt aktuell schraffierte Platzhalter. Lege echte PNGs in `assets/` ab und
ersetze die Platzhalter-Blöcke in `index.html` (Suche nach `TODO`):

| Platzhalter | Datei | Inhalt |
|---|---|---|
| Hero | `assets/screenshot-hero.png` | Gesamtfenster der App (ca. 1840×1150 px) |
| Galerie | `assets/screenshot-chat.png` | Chat-Ansicht |
| Galerie | `assets/screenshot-permission.png` | Bestätigungs-Dialog vor einer Reparatur |
| Galerie | `assets/screenshot-diagnosis.png` | Diagnose-Ergebnis-Karte |
| Galerie | `assets/screenshot-log.png` | Protokoll-Ansicht |

### 2. Rechtstexte ausfüllen (Deutschland)
`impressum.html` und `datenschutz.html` sind **Platzhalter**. Für eine öffentlich
erreichbare Seite sind Impressum (§ 5 DDG) und Datenschutzerklärung (DSGVO) Pflicht.
Trage deine echten Angaben ein — im Zweifel rechtlich prüfen lassen. *(Dies ist keine
Rechtsberatung.)*

### 3. Preis-/Konto-Aussagen prüfen
Im Abschnitt „Sicherheit" und in der FAQ stehen Aussagen zum kostenlosen Konto und
Nutzungskontingent (mit `TODO` markiert). An das endgültige Monetarisierungsmodell anpassen.

### 4. Optional: eigene Domain
GitHub Pages erlaubt eine eigene Domain (z. B. `clickpilot.app`) — dann
`og:url`/`og:image` in `index.html` setzen und eine `CNAME`-Datei ergänzen.

## Deployment (GitHub Pages)

1. Repo `clickpilot-web` **public** auf GitHub anlegen, diesen Ordner pushen.
2. **Settings → Pages → Source: „Deploy from a branch" → Branch `main` / `/root`.**
3. Nach ein bis zwei Minuten ist die Seite unter
   `https://matpurrota-star.github.io/clickpilot-web/` erreichbar.

Die `.nojekyll`-Datei verhindert die Jekyll-Verarbeitung (für eine reine HTML-Seite
unnötig, aber unschädlich).
