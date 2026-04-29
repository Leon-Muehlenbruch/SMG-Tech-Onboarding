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

## 3.5 Claude Chat vs. Claude Code – kurz erklärt

| | Claude Chat | Claude Code |
|---|---|---|
| **Wofür** | Allgemeine Fragen, Texte, Recherche, Brainstorming | Arbeit an Code-Projekten, Dateien lesen/ändern, Git-Operationen |
| **Wo** | Hauptfenster der Claude-App, oder im Browser | Eigenes Fenster in der Claude-App ("Code"-Tab) |
| **Dateizugriff** | Nur über MCPs (Filesystem, GitHub …) | Direkt im gewählten Projekt-Ordner |
| **Wann nutzen** | „Erkläre mir X", „Formuliere eine Mail …" | „Bearbeite die Datei Y", „Pushe meine Änderungen" |

**Faustregel:** Wenn die Antwort eine Datei verändern oder etwas im Repo machen soll → Claude Code. Sonst → Claude Chat.

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
