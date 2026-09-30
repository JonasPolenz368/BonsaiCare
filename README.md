# Bonsai Tracker — Rechtliches

Die Rechtstexte zur iOS-App **Bonsai Tracker**, veröffentlicht über GitHub Pages.

Dieses Verzeichnis ist als **eigenes Repository** gedacht, genau wie bei Fermento. Der
App-Quellcode gehört nicht hierher: GitHub Pages veröffentlicht alles, was im Branch liegt,
und das Projekt-Repo enthält interne Notizen.

## Veröffentlichen

```bash
cd legal
git init && git add . && git commit -m "Legal pages"
git branch -M main
git remote add origin git@github.com:JonasPolenz368/BonsaiTracker.git
git push -u origin main
```

Dann in den Repository-Einstellungen: **Settings → Pages → Source: Deploy from a branch →
Branch: `main`, Folder: `/docs`**.

Die Seiten liegen danach unter:

| Seite | URL |
|---|---|
| Übersicht | `https://jonaspolenz368.github.io/BonsaiTracker/` |
| Nutzungsbedingungen | `https://jonaspolenz368.github.io/BonsaiTracker/terms.html` |
| Datenschutzerklärung | `https://jonaspolenz368.github.io/BonsaiTracker/privacy.html` |
| Impressum | `https://jonaspolenz368.github.io/BonsaiTracker/impressum.html` |

Heißt das Repository anders, ändern sich die URLs entsprechend. Sie stehen an genau einer
Stelle in der App: `ios/App/Core/Legal.swift`. Ein Test schlägt fehl, solange dort noch
`example.com` steht.

## Was wo hin muss

- **App Store Connect → App-Datenschutz**: die URL der Datenschutzerklärung.
- **App Store Connect → App-Informationen**: die URL der Nutzungsbedingungen (EULA-Feld nur,
  wenn eine eigene EULA gewünscht ist — hier gilt Apples Standard-EULA, siehe § 1).
- **In der App**: Einstellungen und Paywall verlinken beide Seiten bereits.

## Pflege

Die Texte beschreiben, was die App tatsächlich tut. Ändert sich eine Datenverarbeitung, muss
die Datenschutzerklärung mit: besonders die Abschnitte 2.5 (Installations-Kennung), 2.6 (Scan)
und 3 (keine Nutzungsstatistik). Der Abschnitt 3 stimmt nur, solange
`AnalyticsService.track` nichts sendet.

Beide Sprachen stehen in derselben Datei, je in einem `<section data-lang="…">`. Eine weitere
Sprache ist ein weiterer Block plus ein Eintrag in der `.langbar`.
# BonsaiCare
