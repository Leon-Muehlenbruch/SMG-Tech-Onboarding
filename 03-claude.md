---
title: 3. Claude KI
nav_order: 4
---

# Kapitel 3 – Claude KI

---

## 3.1 Claude-Account erstellen

1. Browser → <https://claude.ai/>
2. **„Sign up"** klicken.
3. Account mit der **Firmen-E-Mail-Adresse** erstellen.
4. Bestätigungs-Code aus der E-Mail eintragen.
5. Profilangaben ausfüllen.

---

## 3.2 Workspace prüfen

Der Admin hat deinen Account vorab zur Organisation hinzugefügt. Beim ersten Login solltest du oben links den Workspace **SawatzkiMühlenbruch GmbH** bereits ausgewählt sehen – über diesen Workspace sind die firmenspezifischen Skills automatisch verfügbar.

> **Falls der Workspace nicht erscheint:** Admin Bescheid geben.

---

## 3.3 Claude Desktop installieren

1. Browser → <https://claude.ai/download>
2. **„Download for Mac"** klicken.
3. `.dmg`-Datei doppelklicken → Claude-App in den Ordner **Programme** ziehen.
4. App starten (Spotlight → „Claude").

Mehr Details siehe [Software-Referenz: Claude Desktop](software/claude-desktop.html).

---

## 3.4 In Claude Desktop einloggen

1. Beim ersten Start auf **„Sign in"** klicken.
2. Browser öffnet sich → mit dem Account aus 3.1 einloggen.
3. Autorisierung bestätigen → Browser leitet zurück in die App.
4. Workspace **SawatzkiMühlenbruch GmbH** auswählen.

---

## 3.5 Claude Chat, Claude Code und Cowork – kurz erklärt

Anthropic bietet drei Wege, mit Claude zu arbeiten. Wichtig zu verstehen, weil sie unterschiedlich funktionieren – auch was Konnektoren angeht.

| | Claude Chat | Claude Code | Cowork |
|---|---|---|---|
| **Wofür** | Allgemeine Fragen, Texte, Recherche, Brainstorming | Arbeit an Code-Projekten, Dateien lesen/ändern, Git-Operationen | Längere, agentische Aufgaben in einer Cloud-Sandbox |
| **Wo** | Hauptfenster der Claude-App / Browser | „Code"-Tab in der App bzw. CLI im Terminal | Im Browser auf <https://claude.ai> (Tab „Cowork") |
| **Wo läuft's** | Anthropic-Cloud (kein Systemzugriff) | Lokal auf deinem Mac | Remote-Sandbox bei Anthropic |
| **Dateizugriff** | Nur über MCPs (Filesystem, GitHub …) | Direkt im gewählten Projekt-Ordner | Eigener Sandbox-Workspace (Repo wird geklont) |
| **Wann nutzen** | „Erkläre mir X", „Formuliere eine Mail …" | „Bearbeite Datei Y", „Pushe meine Änderungen" | „Lass das im Hintergrund laufen, ohne meinen Mac zu blockieren" |

**Faustregel:**
- Reine Text-Antwort → **Chat**
- Lokale Datei oder Repo ändern → **Code**
- Längere Aufgabe parallel laufen lassen → **Cowork**

### MCPs und Konnektoren – was funktioniert wo?

Konnektoren laufen nicht in allen drei Umgebungen gleich:

| | Chat | Code | Cowork |
|---|---|---|---|
| Eingebauter **GitHub-Konnektor** (siehe 3.7) | ✅ | – nicht nötig, nutzt `gh` CLI direkt | – nutzt eigenes OAuth-Plugin |
| **Filesystem-MCP** (siehe 3.6) | ✅ (sonst kein Dateizugriff) | – nicht nötig (lokaler Zugriff) | – nicht nötig (Sandbox-Workspace) |
| **Custom MCPs** (Vercel, Supabase …) | ✅ über *Connectors*-Panel | ✅ über `.mcp.json` / `claude mcp add` | ✅ über Cowork-Einstellungen |
| **Engineering-Plugins** (Linear, Jira, Notion …) | – | ✅ über `/plugin` | ✅ vorinstalliert |

**Kurz gesagt:** Die in 3.6 und 3.7 eingerichteten Konnektoren sind primär für den **Chat** gedacht. In **Code** brauchst du sie meist nicht, weil dort direkter Datei-Zugriff besteht und GitHub über die `gh` CLI aus [Schritt 2.6](02-github.html#26-github-cli-installieren-und-authentifizieren) läuft. **Cowork** bringt eigene Plugins mit und konfiguriert MCPs separat.

---

## 3.6 Filesystem-MCP einrichten

Damit Claude im Chat auf den Arbeitsordner zugreifen kann.

1. In Claude Desktop oben rechts auf **Einstellungen (Zahnrad)**.
2. Reiter **„Connectors"** → **„Add custom connector"** (oder bei vorhandenem Skill: aus dem Marketplace wählen).
3. Konnektor **„Filesystem"** auswählen.
4. Im Pfad-Feld eintragen:

   ```
   /Users/<DEIN_BENUTZERNAME>/Documents/Github
   ```

   (Den Benutzernamen findest du im Terminal mit `whoami`.)
5. Speichern.

Mehr Details siehe [Software-Referenz: Filesystem MCP](software/filesystem-mcp.html).

---

## 3.7 GitHub-Connection einrichten

Damit Claude im Chat Repos auflisten, Issues lesen und PRs sehen kann.

> **🔑 Was wird hier autorisiert?**
> An dieser Stelle bekommt **Claude (die App)** lesenden Zugriff auf GitHub. Das ist **etwas anderes** als die Mac-Authentifizierung aus [Schritt 2.6](02-github.html#26-github-cli-installieren-und-authentifizieren), die fürs Pushen aus dem Terminal nötig war.
>
> | Schritt | Was wird autorisiert? | Wofür? |
> |---|---|---|
> | [2.6 GitHub CLI](02-github.html#26-github-cli-installieren-und-authentifizieren) | **Dieser Mac** (lokales Git) | Schreibende Git-Operationen wie `git push` |
> | **3.7 GitHub-Connection** | **Claude** (die App) | Lesen von Repos, Issues, PRs *im Chat* |

1. In Claude Desktop → **Einstellungen** → **Connectors**.
2. Konnektor **„GitHub"** suchen und **„Connect"** klicken.
3. Browser öffnet sich → mit dem GitHub-Account aus [Kapitel 2](02-github.html) einloggen.
4. Autorisierung der Organisation `SawatzkiMühlenbruch GmbH` bestätigen.
5. Zurück in Claude → der Konnektor zeigt jetzt **„Connected"**.

Mehr Details siehe [Software-Referenz: GitHub Connection](software/github-connection.html).

---

## 3.8 Claude Desktop neustarten

Damit beide Konnektoren sicher geladen werden:

1. Cmd + Q → Claude komplett beenden.
2. Claude erneut über Spotlight starten.
