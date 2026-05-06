---
title: 1. Vorab
nav_order: 2
---

# Kapitel 1 – Vorab

Bevor wir mit GitHub und Claude loslegen, richten wir den Mac so ein, dass die späteren Schritte sauber funktionieren.

---

## 1.1 Arbeitsordner anlegen

Lege im Finder folgenden Ordner an:

```
~/Documents/Github
```

Auf Deutsch: **Benutzer → Dokumente → Github**.

Dieser Ordner wird der **zentrale Ort für alle Repositories** und gleichzeitig der einzige Ordner, auf den die KI später Zugriff bekommt.

### Warum überhaupt lokal? Geht das nicht direkt auf github.com?

Eine berechtigte Frage – schließlich landen die Änderungen am Ende sowieso wieder online. Trotzdem brauchen wir eine lokale Kopie:

- **Git ist ein lokales Werkzeug.** GitHub ist „nur" der Server, auf dem die finale Version liegt. Bearbeitet wird grundsätzlich lokal, dann mit `git push` zurück synchronisiert. Das Modell ist: *editieren → committen → pushen*, nicht „live im Browser tippen".
- **Claude Code (und andere KI-Tools) brauchen direkten Datei-Zugriff.** Sie lesen und ändern Dateien auf der Festplatte – nicht über die GitHub-Weboberfläche. Ohne lokalen Ordner kein Claude Code.
- **Schnelles Ausprobieren.** Lokal kannst du Änderungen sofort starten, testen und wieder verwerfen, ohne dass jeder Zwischenstand auf GitHub auftaucht. Erst wenn etwas funktioniert, wird es hochgeladen.
- **Mehrere Änderungen sauber bündeln.** Du kannst lokal an mehreren Dateien arbeiten und das Ganze als *einen* sinnvollen Commit pushen, statt für jede Kleinigkeit einen Online-Edit zu machen.
- **Offline-fähig.** Im Zug, im Hotel-WLAN, bei kaputter Internetverbindung – lokal arbeiten geht trotzdem.

Direktes Editieren auf github.com (über das Stift-Symbol) ist daher nur für **Mini-Korrekturen** gedacht, etwa einen Tippfehler im README. Alles andere – Code, mehrere Dateien, KI-Unterstützung – passiert lokal in diesem Ordner.

---

## 1.2 Node.js installieren

Node.js wird von vielen Werkzeugen im Hintergrund benötigt – unter anderem von Claude und einigen MCPs.

1. Browser öffnen → <https://nodejs.org/>
2. Auf der Startseite den Button **„LTS"** (Long Term Support) anklicken und das `.pkg`-Installationsprogramm laden.
3. Heruntergeladene Datei doppelklicken und dem Installationsdialog folgen (Standardeinstellungen reichen).
4. Zur Kontrolle Terminal öffnen (Spotlight → „Terminal") und eingeben:

   ```bash
   node --version
   npm --version
   ```

   Beides sollte eine Versionsnummer ausgeben.

Mehr Details siehe [Software-Referenz: Node.js](software/nodejs.html).

---

## 1.3 Command Line Tools installieren

Die Apple Command Line Tools liefern u. a. `git` und Compiler, die einige Tools voraussetzen.

1. Terminal öffnen.
2. Folgenden Befehl eingeben und Enter drücken:

   ```bash
   xcode-select --install
   ```

3. Es öffnet sich ein Dialogfenster → auf **„Installieren"** klicken und Lizenzbedingungen akzeptieren.
4. Die Installation dauert je nach Internetverbindung 5–15 Minuten.
5. Zur Kontrolle:

   ```bash
   git --version
   ```

   Es sollte eine Versionsnummer angezeigt werden.

Mehr Details siehe [Software-Referenz: Command Line Tools](software/command-line-tools.html).
