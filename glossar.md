---
title: Glossar
nav_order: 7
---

# Glossar

Schnell-Nachschlagen für Begriffe, die im Setup auftauchen.

---

## Allgemein

**CLI** *(Command Line Interface)*
Programme, die über Texteingabe im Terminal gesteuert werden – im Gegensatz zu klickbaren Apps mit grafischer Oberfläche. Beispiel: `gh` ist eine CLI.

**Terminal**
Die macOS-App, in der man Befehle an das System schickt. Spotlight (`Cmd + Leertaste`) → „Terminal" eingeben.

**Pfad** *(Path)*
Adresse einer Datei oder eines Ordners auf dem Mac, z. B. `/Users/leon/Documents/Github`. Die Tilde `~` ist eine Abkürzung für das eigene Benutzerverzeichnis.

**Working Directory**
Der Ordner, in dem ein Tool gerade arbeitet. In Claude Code ist das der gewählte Projekt-Ordner.

**Markdown / `.md`**
Einfaches Textformat für formatierte Dokumente (Überschriften, Listen, Links). Diese Doku ist in Markdown geschrieben.

**`.pkg`-Datei**
macOS-Installationsformat. Doppelklick startet einen geführten Installer.

---

## Git & GitHub

**Repository** *(Repo)*
Ein Projekt-Container mit allen Dateien plus deren Versionsgeschichte. Liegt einmal lokal auf deinem Mac und einmal bei GitHub im Internet.

**Clone** *(Klonen)*
Eine Kopie eines Repos von GitHub auf den lokalen Mac herunterladen – inklusive der gesamten Geschichte.

**Commit**
Ein gespeicherter Stand eines Projekts mit Beschreibung („Was wurde geändert und warum?"). Lokal – wird erst beim Push geteilt.

**Push**
Die eigenen lokalen Commits zu GitHub hochladen, damit andere sie sehen.

**Pull**
Änderungen, die andere bei GitHub gemacht haben, lokal nachladen.

**Fetch**
Wie Pull, aber nur „schauen, was sich auf GitHub getan hat", ohne lokal etwas zu übernehmen.

**Branch**
Ein paralleler Arbeitszweig im selben Repo. Standard ist `main`. Wird genutzt, um Änderungen zu entwickeln, ohne `main` direkt anzufassen.

**Remote**
Das Gegenstück zum lokalen Repo – typischerweise das Repo bei GitHub. Der Standard-Remote heißt `origin`.

**Origin**
Default-Name für den GitHub-Remote eines geklonten Repos.

**Pull Request** *(PR)*
Vorschlag, einen Branch in einen anderen zu integrieren. Andere können kommentieren, bevor er übernommen wird.

**Issue**
Eintrag auf GitHub für Bugs, Feature-Wünsche oder Diskussionen.

**Organisation** *(Org)*
Gemeinsamer Account auf GitHub für Firmen oder Teams. Bei uns: `SawatzkiMühlenbruch GmbH`.

---

## Authentifizierung

**Token**
Langer zufälliger String, der ein Passwort ersetzt – wird automatisch erzeugt und kann jederzeit widerrufen werden.

**OAuth**
Verfahren, mit dem Apps wie Claude oder GitHub Desktop einen Token im Namen des Nutzers bekommen, ohne dass die App das Passwort sieht.

**Schlüsselbund** *(Keychain)*
Der macOS-eigene Passwort- und Token-Speicher. Hier liegen die GitHub-Credentials nach `gh auth login`.

**HTTPS**
Verschlüsseltes Internet-Protokoll. Wir nutzen HTTPS-URLs für Git, weil sie ohne SSH-Key-Setup funktionieren.

---

## Claude

**MCP** *(Model Context Protocol)*
Offener Standard, mit dem Claude neue Fähigkeiten dazubekommt – etwa Datei-Zugriff oder GitHub-Anbindung.

**Connector / Konnektor**
Eine konkrete MCP-Anbindung in Claude Desktop, z. B. „Filesystem" oder „GitHub".

**Workspace**
Anthropics Begriff für eine Account-Gruppierung. Es gibt einen persönlichen Workspace und den Firmen-Workspace `SawatzkiMühlenbruch GmbH`.

**Skill**
Vorkonfigurierte Fähigkeit, die der Admin auf Org-Ebene bereitstellt – etwa firmenspezifische Workflows.

**Claude Chat vs. Claude Code**
Siehe [3.5 in Kapitel 3](03-claude.html#35-claude-chat-vs-claude-code--kurz-erklärt).

---

## Tooling

**Node.js**
JavaScript-Laufzeit, die viele Tools im Hintergrund brauchen. Siehe [Software-Referenz](software/nodejs.html).

**npm**
Paketmanager, den Node.js mitbringt – installiert JavaScript-Tools.

**Compiler**
Programm, das Quellcode in maschinenausführbare Form übersetzt. Wird beim Installieren mancher Pakete automatisch genutzt.

**LTS** *(Long Term Support)*
Besonders lang gepflegte Version eines Tools. Bei Node.js immer die empfohlene Wahl.

**Apple Silicon vs. Intel**
Zwei verschiedene Mac-Prozessor-Architekturen. Bei Software-Downloads gibt's oft separate Versionen:
- **Apple Silicon** = Macs mit M1/M2/M3/M4-Chip (ab Ende 2020)
- **Intel** = Macs vor 2020

Architektur prüfen: 🍎-Menü → „Über diesen Mac".
