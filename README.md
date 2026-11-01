# Burning Chrome · Sonic Flames

Zweisprachiger Begleiter zum Konzeptalbum **The Burning Chrome Symphony Dreamscape**.

- Zieladresse: https://burningchrome.someswans.de
- 15 Kapitel mit DE/EN-Umschaltung, Original-Liedtexten und Coverbildern
- 15 vollständige Songs als MP3, direkt abspielbar
- Statische Webseite: kein Node.js, npm oder Build-Schritt auf dem Server nötig

## Plesk verbinden (Pull und Deployment manuell)

Die Domain zeigt bereits die Plesk-Standardseite. DNS und HTTPS müssen für diesen Ablauf nicht auf GitHub umgestellt werden. GitHub liefert den Quellstand an Plesk; Plesk liefert die Webseite unter der Domain aus.

1. In Plesk **Websites & Domains → burningchrome.someswans.de → Git** öffnen und ein Repository hinzufügen.
2. **Remote Git-Hosting**, Repository `https://github.com/micatgthb/burningchrome.git`, Branch `main` wählen. Das Repository ist öffentlich; ein GitHub-Passwort oder Token ist zum Lesen nicht nötig.
3. Einen eigenen Bereitstellungspfad für diese Domain auswählen. Keine Verzeichnisse eines anderen Projekts verwenden.
4. **Manuelle Bereitstellung** auswählen, damit Pull und Deploy bewusst ausgelöst werden.
5. In den Hosting-Einstellungen der Domain das **Dokumentenstammverzeichnis auf den Unterordner `dist` dieses Bereitstellungspfads** setzen. Beispiel: Wird nach `burningchrome` bereitgestellt, lautet das Webverzeichnis `burningchrome/dist`. Den tatsächlichen Pfad zeigt Plesk an.
6. Du führst anschließend **Updates abrufen / Pull** und **Bereitstellen / Deploy** aus.
7. https://burningchrome.someswans.de öffnen; Sprachwechsel und Audioplayer prüfen.

Wichtig: Nicht das Repository als GitHub Pages veröffentlichen und keinen CNAME auf GitHub setzen. Die Domain bleibt beim vorhandenen Plesk-Hosting. Keine automatische Bereitstellung und kein Webhook sind eingerichtet.

## Dateien

`dist/index.html`, `style.css`, `app.js` und `data.json` bilden die Webseite. `dist/covers/` enthält die ausgewählten Cover, `dist/audio/` die MP3-Hördateien. Das Projekt ist ohne serverseitige Laufzeit lauffähig.

Lokal: `python3 -m http.server 8765 --directory dist` und http://127.0.0.1:8765 öffnen.

## Redaktioneller Stand

Die Liedtexte folgen zunächst den Vorlagen für den Sänger. Der Abgleich mit dem veröffentlichten Gesang folgt später. Spotify, Apple Music und Amazon Music sind als Suchlinks pro Song eingebunden; bestätigte direkte Veröffentlichungslinks werden später eingesetzt. Dauerhafte QR-Codes werden erst nach Bestätigung der Domain und Kapiteladressen erzeugt.

Credits unterscheiden Micha (Michael Bollow, Gitarre und Synthesizer) und Michi Kalab (Piano ausschließlich bei Chiba City And No Return).

Die Sites-Konfiguration, Arbeitsquellen, WAV-Master und Buch-PDFs sind nicht Bestandteil dieses Web-Repositories. Die Webseite enthält MP3-Hörfassungen, keine WAV-Master.
