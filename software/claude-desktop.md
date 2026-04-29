---
title: Claude Desktop
parent: Software-Referenz
nav_order: 4
---

# Claude Desktop

## Was ist das?

Claude Desktop ist die **native Mac-App** von Anthropic. Sie bündelt zwei Arbeitsmodi:

- **Chat** – klassische Konversation mit Claude (wie auf claude.ai).
- **Code** – ein eigener Modus für Arbeit an Code-Projekten, mit Datei-, Git- und Terminal-Zugriff.

## Warum brauchen wir es bei SMG?

- Schneller Start als die Browser-Version.
- **MCPs** (Model Context Protocol – Konnektoren wie Filesystem oder GitHub) lassen sich nur in der Desktop-App konfigurieren.
- Skills, die der Admin der Organisation zuweist, sind direkt verfügbar.

## Wo ist es installiert?

Im Ordner **Programme** als App `Claude.app`.

## Wichtige Funktionen im Alltag

| Funktion | Wo? |
|---|---|
| Workspace wechseln | oben links (Avatar/Org-Name) |
| Konnektoren verwalten | Einstellungen (⌘ + ,) → „Connectors" |
| Skills | Einstellungen → „Skills" |
| Code-Modus öffnen | Tab „Code" oben |
| Verlauf | linke Sidebar |

## Wie prüfe ich, ob's läuft?

- Login funktioniert (Avatar oben links sichtbar).
- Workspace `SawatzkiMühlenbruch GmbH` ist auswählbar.
- Unter `Connectors` sind **Filesystem** und **GitHub** mit grünem „Connected"-Status sichtbar (siehe Workflow-[Kapitel 3](../03-claude.html)).

## Updates

Claude Desktop lädt Updates automatisch im Hintergrund. Beim Neustart der App ist die neue Version aktiv.

## Häufige Fragen

**Brauche ich noch claude.ai im Browser?**
Nein, aber es funktioniert weiter. Der Browser ist nützlich, wenn der Mac mal nicht zur Hand ist.

**Was tun, wenn die App nach einem Update Connectors „verliert"?**
Einmal komplett beenden (⌘ + Q) und neu starten. Falls weiterhin weg → Konnektor neu verbinden (siehe [Filesystem MCP](filesystem-mcp.html) / [GitHub Connection](github-connection.html)).
