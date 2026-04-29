---
title: GitHub Connection
parent: Software-Referenz
nav_order: 6
---

# GitHub Connection

## Was ist das?

Ein offizieller Konnektor von Anthropic, der Claude **direkten Zugriff auf GitHub** gibt. Claude kann darüber:

- Repositories auflisten,
- Issues und Pull Requests lesen,
- Datei-Inhalte aus Repos abrufen,
- (je nach Konfiguration) Kommentare oder Issues anlegen.

## Warum brauchen wir es bei SMG?

- Du kannst im Chat fragen: *„Was sind die offenen Issues in Repo X?"* – ohne den Browser zu wechseln.
- Code-Reviews und Recherche werden deutlich schneller, weil Claude die relevanten Dateien selbst zieht.
- Im Code-Modus ergänzt der Konnektor die lokale Sicht um die Remote-Sicht (z. B. „Was steht im PR-Beschreibungstext, der zu diesem Branch gehört?").

## Wo ist es konfiguriert?

In Claude Desktop unter **Einstellungen → Connectors → GitHub**.

Die Autorisierung läuft per OAuth über github.com – es wird **kein Token manuell eingerichtet**. Der Konnektor agiert mit den Rechten deines GitHub-Accounts (also: alles, was du selbst sehen darfst, sieht Claude auch).

## Wie prüfe ich, ob's läuft?

Im Chat fragen:

> „Welche Repositories der Organisation `SawatzkiMühlenbruch GmbH` siehst du?"

Es sollten mindestens die internen Repos auftauchen, in denen du Mitglied bist.

## Häufige Fragen

**Kann Claude Code damit pushen?**
Nein. Der GitHub-Konnektor ist für **Lese-Operationen** und API-Aktionen wie Issues. Pushes laufen über den **lokalen Git-Stack** und brauchen eine separate [GitHub-Authentifizierung](../04-test-und-erste-nutzung.html#44-github-authentifizierung-einrichten).

**Sieht Claude private Repos anderer Organisationen, in denen ich bin?**
Nur, wenn du es bei der OAuth-Autorisierung erlaubt hast. Die Empfehlung ist, den Zugriff auf die SMG-Org zu beschränken.

**Was tun, wenn der Status auf „Disconnected" springt?**
Auf den Konnektor klicken → **„Reconnect"** → erneut autorisieren. Das passiert gelegentlich nach Passwort-/2FA-Änderungen.
