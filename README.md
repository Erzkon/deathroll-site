# deathroll-site

Statische Webseite für **Deathroll – Party Dice**: Support, FAQ, Datenschutzerklärung und Impressum.
Reines HTML/CSS, keine externen Ressourcen, keine Cookies, kein JavaScript, keine Analyse.

| Datei | Inhalt |
|-------|--------|
| `index.html` / `en.html` | Startseite mit Spielerklärung, Support und FAQ (DE / EN) |
| `privacy.html` / `privacy-en.html` | Datenschutzerklärung (DE / EN) |
| `impressum.html` | Impressum (DE, auf allen Seiten im Footer verlinkt) |
| `style.css` | Gemeinsames Stylesheet im Look der App |
| `icon.png` | App-Icon, 256 × 256 px |
| `.nojekyll` | GitHub Pages liefert die Dateien unverändert aus (kein Jekyll) |

Die App verlinkt auf `https://erzkon.github.io/deathroll-site/` (Support) und
`…/privacy.html` bzw. `…/privacy-en.html` (Datenschutz, je nach Sprache).

## Vor der Veröffentlichung: Platzhalter ausfüllen

Diese Platzhalter kommen in `index.html`, `en.html`, `privacy.html`, `privacy-en.html` und `impressum.html` vor
und müssen überall ersetzt werden:

| Platzhalter | Ersetzen durch |
|-------------|----------------|
| `[NAME]` | Vor- und Nachname (bzw. Name des Anbieters) |
| `[STRASSE HAUSNUMMER]` | Straße und Hausnummer (ladungsfähige Anschrift, kein Postfach) |
| `[PLZ ORT]` | Postleitzahl und Ort |
| `[E-MAIL]` | Kontakt-E-Mail-Adresse (auch in den `mailto:`-Links) |

Prüfen, ob noch Platzhalter übrig sind:

```bash
grep -n "\[NAME\]\|\[STRASSE HAUSNUMMER\]\|\[PLZ ORT\]\|\[E-MAIL\]" *.html
```

Außerdem das Stand-Datum in `privacy.html` und `privacy-en.html` aktualisieren, wenn sich Inhalte ändern.

> Hinweis: Datenschutzerklärung und Impressum sind sorgfältig formulierte Vorlagen, aber keine Rechtsberatung.
> Vor der Veröffentlichung bitte prüfen (lassen), ob sie zur eigenen Situation passen.

## GitHub Pages aktivieren

1. Repository auf GitHub anlegen: `Erzkon/deathroll-site` (öffentlich; Pages für private Repos erfordert einen bezahlten Plan).
2. Platzhalter ausfüllen, committen und pushen: `git push -u origin main`
3. Auf GitHub: **Settings → Pages → Build and deployment → Source: „Deploy from a branch“**,
   Branch **main**, Ordner **/ (root)**, speichern.
4. Nach ein bis zwei Minuten ist die Seite unter `https://erzkon.github.io/deathroll-site/` erreichbar.
5. In App Store Connect eintragen: Support-URL `https://erzkon.github.io/deathroll-site/`,
   Datenschutz-URL `https://erzkon.github.io/deathroll-site/privacy.html`.

## Lokal ansehen

```bash
python3 -m http.server 8000
# dann http://localhost:8000 öffnen
```
