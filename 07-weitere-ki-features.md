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

> Diese Seite wächst, sobald weitere SMG-spezifische KI-Features freigeschaltet werden.
