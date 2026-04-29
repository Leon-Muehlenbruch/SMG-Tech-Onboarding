---
title: 3. Claude KI
nav_order: 4
---

# Kapitel 3 – Claude KI

Claude ist die KI, mit der wir täglich arbeiten – sowohl im klassischen Chat als auch direkt im Code.

---

## 3.1 Claude-Account erstellen

1. Browser → <https://claude.ai/>
2. **„Sign up"** klicken.
3. Account mit der **persönlichen E-Mail-Adresse** erstellen.
4. Bestätigungs-Code aus der E-Mail eintragen.
5. Profilangaben ausfüllen.

> **Warum die persönliche Mail?**
> Die Anthropic-Lizenzen sind so eingerichtet, dass private Accounts vom Admin in die Firmen-Organisation aufgenommen werden. Sobald das passiert ist, sind Firmen-spezifische **Skills automatisch verfügbar**.

---

## 3.2 Vom Admin zur Organisation hinzufügen lassen

1. Dem Admin per Slack/Mail mitteilen: *„Ich habe meinen Claude-Account angelegt unter `<deine.persönliche@mail>`. Bitte zur Organisation hinzufügen."*
2. Auf die Bestätigung warten.
3. Nach der Bestätigung: einmal aus Claude ausloggen und wieder einloggen, damit die Organisations-Zuordnung greift.

Du erkennst das daran, dass oben links im Workspace-Switcher die Organisation **SawatzkiMühlenbruch GmbH** auftaucht.

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

> **Hinweis:** Diese Connection gibt **Claude** lesenden GitHub-Zugriff. Sie ist **nicht dasselbe** wie die GitHub-Authentifizierung des Mac (siehe [Schritt 4.4](04-test-und-erste-nutzung.html#44-github-authentifizierung-einrichten-github-cli)), die später für `git push` benötigt wird.

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

---

## ✅ Abschluss-Check

- [ ] Claude-Account angelegt
- [ ] Account vom Admin in die Organisation aufgenommen
- [ ] Claude Desktop installiert, eingeloggt, Workspace `SawatzkiMühlenbruch GmbH` ausgewählt
- [ ] Filesystem-MCP zeigt auf `~/Documents/Github`
- [ ] GitHub-Connection ist verbunden
- [ ] Claude Desktop neugestartet

Weiter geht's mit **[Kapitel 4 – Test & erste Nutzung](04-test-und-erste-nutzung.html)**.
