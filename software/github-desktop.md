---
title: GitHub Desktop
parent: Software-Referenz
nav_order: 3
---

# GitHub Desktop

## Was ist das?

GitHub Desktop ist die **offizielle grafische Oberfläche von GitHub**. Sie übersetzt die typischen Git-Operationen (Clone, Commit, Push, Pull, Branch …) in Klicks – ohne dass man die Terminal-Befehle kennen muss.

## Warum brauchen wir es bei SMG?

- Senkt die Einstiegshürde für alle, die nicht aus der Software-Entwicklung kommen.
- Visualisiert Änderungen, Branches und History übersichtlich.
- Ist gleichzeitig ein **Quick-Check-Tool**: man sieht sofort, was sich seit dem letzten Push verändert hat.

Auch wenn Claude Code später viele Git-Operationen automatisiert übernimmt, ist GitHub Desktop unsere **Sichtbar­keits-Schicht**.

## Wo ist es installiert?

Im Ordner **Programme** als App `GitHub Desktop.app`.

## Wichtige Funktionen im Alltag

| Aufgabe | Wo? |
|---|---|
| Repo klonen | `File → Clone Repository…` |
| Aktuelle Änderungen sehen | linke Spalte „Changes" |
| Commit erstellen | unten links Nachricht eintragen → „Commit" |
| Push/Pull | oben rechts „Push origin" / „Fetch origin" |
| Branch wechseln | oben Mitte „Current Branch" |
| Repo auf github.com öffnen | `Repository → View on GitHub` |

## Wie prüfe ich, ob's läuft?

App starten → eingeloggter Benutzername steht oben rechts.
Mindestens ein Repository ist unter `Current Repository` auswählbar.

## Häufige Fragen

**Kollidiert das mit Claude Code?**
Nein. Beide arbeiten mit derselben lokalen Git-Konfiguration. Was Claude Code committet, sieht GitHub Desktop sofort und umgekehrt.

**Brauche ich es überhaupt, wenn Claude alles für mich macht?**
Ja – als Sicherheitsnetz. Ein Blick in GitHub Desktop zeigt dir vor jedem Push, was wirklich verändert wurde.
