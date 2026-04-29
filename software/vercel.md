---
title: Vercel (+ V0)
parent: Software-Referenz
nav_order: 8
---

# Vercel (+ V0)

## Was ist das?

**Vercel** ist eine Hosting-Plattform, die GitHub-Repos automatisch zu live laufenden Websites macht. Bei jedem Push auf `main` startet ein Build und das Ergebnis ist sofort online.

**V0** (<https://v0.dev>) ist Vercels AI-Generator: Aus einem Text-Prompt entsteht eine kleine Next.js-App, die direkt bei Vercel landet – *ohne* dazwischen­geschaltetes GitHub-Repo.

## Warum brauchen wir es bei SMG?

- Das Hosting jeder Center-/Kunden-Website läuft über Vercel.
- Auto-Deploy: kein manuelles „Hochladen" nötig, ein Push reicht.
- V0 erlaubt schnelles Prototyping, das trotzdem in der gleichen Vercel-Welt landet wie die regulären Projekte.

## Wer wird hier eigentlich autorisiert?

| Autorisierung | Eingerichtet in | Wirkt für |
|---|---|---|
| **Vercel-Account → Firmen-Team** | vercel.com ([5.2](../05-vercel.html#52-firmen-team-beitreten)) | dich als User innerhalb des Firmen-Workspaces |
| **Vercel ↔ GitHub** | Vercel Settings → Git ([5.3](../05-vercel.html#53-github-verbindung-autorisieren)) | Vercel darf SMG-Repos lesen + auf Pushes hören |
| **Vercel ↔ Claude** | Claude Connectors ([5.5](../05-vercel.html#55-vercel-konnektor-in-claude-einrichten)) | Claude darf Vercel-Projekte einsehen/steuern |

Drei Stellen, drei Zwecke – bewusst getrennt.

## Wichtige Konzepte

| Begriff | Bedeutung |
|---|---|
| **Projekt** | Entspricht meist 1:1 einem GitHub-Repo (oder einem V0-Build). |
| **Deployment** | Eine konkrete Version, die Vercel gebaut hat. Jeder Push erzeugt eines. |
| **Production** | Was unter der Haupt-Domain läuft (Push auf `main`). |
| **Preview** | Automatisch generierte URL pro Branch/PR – zum Testen ohne Live-Risiko. |
| **Build-Logs** | Konsolenausgabe des Builds; hilfreich bei Fehlersuche. |

## Wie prüfe ich, ob's läuft?

1. <https://vercel.com> einloggen.
2. Oben links Workspace **SawatzkiMühlenbruch GmbH** ausgewählt.
3. Mehrere Projekte in der Liste sichtbar.
4. Im Chat: Claude listet die Projekte (siehe [6.1](../06-test-vercel-claude.html#61-vercel-verbindung-im-chat-prüfen)).

## Häufige Fragen

**Ich habe versehentlich ein Projekt in meinem Free-Account angelegt – was tun?**
Im Vercel-Dashboard auf das Projekt → **Settings → „Transfer Project"** → Ziel-Workspace `SawatzkiMühlenbruch GmbH` wählen.

**Wo bekomme ich die Live-URL?**
Im Vercel-Dashboard auf das Projekt → oben rechts steht die Production-URL. Oder im Chat: *„Was ist die Production-URL von Projekt X?"*

**Ein Build ist fehlgeschlagen – wo schaue ich nach?**
Im Vercel-Dashboard auf das fehlgeschlagene Deployment → Reiter **„Build Logs"**. Oder Claude fragen: *„Zeig mir die Build-Logs des letzten fehlgeschlagenen Deployments im Projekt X."*

**Kann Claude Code etwas „in V0" machen?**
Eingeschränkt. Claude kann V0-Projekte über den Konnektor *einsehen und steuern* (Deployments, Domains, Logs). Lokales Editieren der Quelle ist nicht möglich, weil V0 keine Source ins Filesystem legt – die Quelle bleibt in der V0-/Vercel-Cloud.

**Kann ich einen alten Stand zurückrollen?**
Ja. Im Vercel-Dashboard auf das Projekt → **Deployments** → bei einem älteren Deployment auf das Drei-Punkte-Menü → **„Promote to Production"**.
