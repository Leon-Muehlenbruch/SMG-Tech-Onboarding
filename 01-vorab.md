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
