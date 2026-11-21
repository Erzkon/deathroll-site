# deathroll-site

Statische Webseite für **Deathroll – Party Dice**: Support, FAQ und Datenschutzerklärung.
Reines HTML/CSS, keine externen Ressourcen, keine Cookies, kein JavaScript, keine Analyse.

| Datei | Inhalt |
|-------|--------|
| `index.html` / `en.html` | Startseite mit Spielerklärung, Support und FAQ (DE / EN) |
| `es.html` / `fr.html` / `it.html` / `pt-br.html` | Startseite auf Spanisch, Französisch, Italienisch, Portugiesisch (BR), ab 2.0; verlinken auf die englische Datenschutzerklärung |
| `privacy.html` / `privacy-en.html` | Datenschutzerklärung (DE / EN) |
| `style.css` | Gemeinsames Stylesheet im Look der App |
| `icon.png` | App-Icon, 256 × 256 px |
| `.nojekyll` | GitHub Pages liefert die Dateien unverändert aus (kein Jekyll) |

Die App verlinkt auf `https://erzkon.github.io/deathroll-site/` (Support) und
`…/privacy.html` bzw. `…/privacy-en.html` (Datenschutz, je nach Sprache).

## Vor der Veröffentlichung: Platzhalter ausfüllen

Diese Platzhalter kommen in `index.html`, `en.html`, `privacy.html` und `privacy-en.html` vor
(und in `es.html`, `fr.html`, `it.html`, `pt-br.html`) und müssen überall ersetzt werden (eine Postanschrift wird bewusst nicht angegeben):

| Platzhalter | Ersetzen durch |
|-------------|----------------|
| `Kevin Bolte` | Vor- und Nachname (Verantwortlicher in der Datenschutzerklärung) |
| `erzkon.dev@gmail.com` | Kontakt-E-Mail-Adresse (auch in den `mailto:`-Links und im Footer) |

Prüfen, ob noch Platzhalter übrig sind:

```bash
grep -n "\[NAME\]\|\[E-MAIL\]" *.html
```

Außerdem das Stand-Datum in `privacy.html` und `privacy-en.html` aktualisieren, wenn sich Inhalte ändern.

> Hinweis: Die Datenschutzerklärung ist eine sorgfältig formulierte Vorlage, aber keine Rechtsberatung.
> Vor der Veröffentlichung bitte prüfen (lassen), ob sie zur eigenen Situation passen.

## GitHub Pages aktivieren

1. Repository auf GitHub anlegen: `Erzkon/deathroll-site` (öffentlich; Pages für private Repos erfordert einen bezahlten Plan).
2. Platzhalter ausfüllen, committen und pushen: `git push -u origin main`
3. Auf GitHub: **Settings → Pages → Build and deployment → Source: „Deploy from a branch“**,
   Branch **main**, Ordner **/ (root)**, speichern.
4. Nach ein bis zwei Minuten ist die Seite unter `https://erzkon.github.io/deathroll-site/` erreichbar.
5. In App Store Connect eintragen: Support-URL `https://erzkon.github.io/deathroll-site/`,
   Datenschutz-URL `https://erzkon.github.io/deathroll-site/privacy.html`.

## Release-Branches

Änderungen für kommende App-Versionen liegen auf eigenen Branches und gehen erst live, wenn die jeweilige
Version im App Store verfügbar ist:

| Branch | Inhalt | Wann mergen und pushen |
|--------|--------|------------------------|
| `release-1.0` | Button „Im App Store laden“ / „Download on the App Store“ auf der Startseite (DE/EN) | sobald **1.0** im App Store live ist |
| `release-1.2` | baut auf `release-1.0` auf: Feature-Liste (Klassisch, Elimination, Statistik, Erfolge, „Wer fängt an?“), Datenschutzerklärung „Lokale Speicherung“ für 1.2, Stand-Datum | sobald **1.2** im App Store live ist |
| `release-2.0` | baut auf `release-1.2` auf: Feature „Jeder am eigenen iPhone“ (Nearby, Online, Browser), 25 Erfolge, FAQ „Android“ und „Internet“, Datenschutzerklärung Abschnitt 5 „Gemeinsam spielen“, Stand-Datum, Startseite zusätzlich auf ES/FR/IT/PT mit Sprachumschalter | sobald **2.0** im App Store live ist |

```bash
# 1.0 ist live
git switch main && git merge --ff-only release-1.0 && git push

# 1.2 ist live (danach)
git switch main && git merge --ff-only release-1.2 && git push

# 2.0 ist live (danach)
git switch main && git merge --ff-only release-2.0 && git push
```

Vor dem Merge von `release-1.2` bzw. `release-2.0` das Stand-Datum in `privacy.html` / `privacy-en.html` auf den Veröffentlichungstag setzen.

## Lokal ansehen

```bash
python3 -m http.server 8000
# dann http://localhost:8000 öffnen
```
