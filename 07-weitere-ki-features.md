---
title: 7. Weitere KI Features
nav_order: 8
---

# Kapitel 7 – Weitere KI Features

> **Kein Setup-Schritt.** Diese Seite ist optional und beschreibt, was du *nach* abgeschlossenem Setup (Kapitel 1–6) zusätzlich mit Claude tun kannst. Erst nach erfolgreichem Setup-Test ansteuern, um sich nicht ablenken zu lassen.

---

## 7.1 Skills – was sind das?

In Claude Desktop sind über die Organisation `SawatzkiMühlenbruch GmbH` mehrere **Skills** verfügbar – vorkonfigurierte Fähigkeiten, die der Team-Lead auf Org-Ebene aktiviert hat. Du musst Skills nicht selbst installieren oder einrichten; sie sind automatisch da, sobald dein Workspace `SawatzkiMühlenbruch GmbH` aktiv ist (siehe [3.4](03-claude.html#34-in-claude-desktop-einloggen)).

Eine Übersicht aller verfügbaren Skills findest du in Claude Desktop unter **Einstellungen (⌘ + ,) → Skills**.

---

## 7.2 Der Cockpit-Skill

Der zentrale Skill für den Tagesbetrieb ist der **Cockpit-Skill**. Er hat Zugriff auf unsere CockpitOS-Datenbasis (Center, Shops, Posts, Kampagnen) und kann Anfragen darauf direkt im Chat beantworten oder Aktionen auslösen.

### Typische Anfragen

> „Liste mir alle Center auf, in denen es eine Deichmann-Filiale gibt."

> „Schreibe einen Post für alle Center, die zur Firma XY gehören."

Solche **Filter über mehrere Center hinweg** sind der Sweet Spot des Skills – per Hand wären das viele Klicks im Cockpit-UI, im Chat reicht eine einzige Frage.

### Wann Skill, wann Cockpit-UI?

| Aufgabe | Wo schneller? |
|---|---|
| Einzelne Änderung an einem bekannten Center | Cockpit-UI |
| Massenoperationen über viele Center | **Cockpit-Skill** |
| Recherche („wo ist Marke X vertreten?") | **Cockpit-Skill** |
| Detail-Bearbeitung mit Vorschau | Cockpit-UI |

Faustregel: Wo **Filter über mehrere Center** im Spiel sind, nimm den Skill.

---

## 7.3 Wenn der Skill nicht antwortet

1. **Workspace prüfen** – oben links muss `SawatzkiMühlenbruch GmbH` aktiv sein, nicht der persönliche Workspace.
2. **Einstellungen → Skills** – der Cockpit-Skill muss in der Liste erscheinen (und ggf. aktiviert sein).
3. Wenn er trotzdem nicht antwortet: Team-Lead Bescheid geben – möglicherweise liegt ein Auth- oder API-Problem auf Org-Ebene vor.

---

## 7.4 Permission-Prompts in Claude Code reduzieren

Claude Code (CLI/Desktop-Tab „Code") fragt bei „heiklen" Aktionen jedes Mal um Bestätigung – z. B. bei `git push` auf `main`, beim Löschen von Dateien oder Branches, beim Ändern von Settings. Das ist eine Sicherheitsfunktion, die vor versehentlichen Aktionen schützt. In Solo-Repos oder bei häufig wiederkehrenden Befehlen kann das aber bremsen.

### Gezielt einzelne Befehle vorab erlauben

1. Datei öffnen (anlegen, falls nicht vorhanden):

   ```
   ~/.claude/settings.json
   ```

2. Inhalt ergänzen (oder bestehendes `permissions.allow`-Array erweitern):

   ```json
   {
     "permissions": {
       "allow": [
         "Bash(git push:*)",
         "Bash(git commit:*)"
       ]
     }
   }
   ```

3. Claude Code neustarten.

Ab jetzt laufen diese Befehle ohne Rückfrage durch.

> **⚠️ Vorsicht:** Jede in `allow` aufgenommene Aktion läuft ohne Bestätigung. Nimm nur Befehle auf, deren Auswirkungen du kennst und akzeptierst – besonders bei `git push`, `rm` oder Schreiboperationen außerhalb des Projektordners. **Niemals** breite Wildcards wie `Bash(*)` eintragen.

### Automatischen Vorschlag nutzen

Im Claude-Code-Terminal kannst du den Slash-Command `/fewer-permission-prompts` ausführen. Er scannt deinen bisherigen Verlauf nach unkritischen Read-only-Bash-Calls und schlägt eine passende Allowlist vor – du musst sie nur noch bestätigen.

### Self-Modification-Schutz

Claude Code bearbeitet **keine eigenen Sicherheits-Settings**, auch nicht auf Anweisung. Schritt 1–3 oben musst du immer selbst machen – das ist gewollt und kein Bug.

---

> Diese Seite wächst, sobald weitere SMG-spezifische KI-Features freigeschaltet werden.
