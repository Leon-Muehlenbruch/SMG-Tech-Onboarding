---
title: Filesystem MCP
parent: Software-Referenz
nav_order: 5
---

# Filesystem MCP

## Was ist das?

Ein **MCP** („Model Context Protocol") ist eine Erweiterung, die Claude neue Fähigkeiten gibt. Das **Filesystem-MCP** im Speziellen erlaubt Claude, **Dateien auf deinem Mac zu lesen und zu schreiben** – allerdings nur in den Ordnern, die du explizit freigegeben hast.

Bei uns: Freigegeben ist genau **`~/Documents/Github`**.

## Warum brauchen wir es bei SMG?

- Damit Claude im normalen Chat (nicht nur im Code-Modus) auf Projektdateien zugreifen kann.
- Damit du Dateien einfach per „Schau dir mal die Datei … an" referenzieren kannst, ohne sie hochzuladen.
- Damit Claude erstellte Inhalte direkt am richtigen Ort speichern kann.

## Wo ist es konfiguriert?

In Claude Desktop unter **Einstellungen → Connectors → Filesystem**.

## Was darf Claude damit?

| Aktion | Erlaubt? |
|---|---|
| Dateien in `~/Documents/Github/**` lesen | ✅ |
| Dateien in `~/Documents/Github/**` ändern/anlegen | ✅ (du wirst pro Aktion gefragt) |
| Dateien außerhalb dieses Ordners ansehen | ❌ |
| Datei nach `~/Downloads` schreiben | ❌ |

## Wie prüfe ich, ob's läuft?

Im Chat fragen:

> „Bitte liste mir alle Ordner unter `~/Documents/Github` auf."

Wenn Claude die Liste zurückgibt, ist alles gut.

## Häufige Fragen

**Was, wenn ich einen weiteren Ordner freigeben will?**
Im Konnektor-Dialog kann ein zweiter Pfad ergänzt werden. Vorher mit dem Admin abstimmen, ob das gewünscht ist – die Standardannahme ist: alles Arbeitsbezogene gehört in `~/Documents/Github`.

**Sind meine Dateien jetzt „in der Cloud"?**
Nein. Das Filesystem-MCP läuft **lokal** auf deinem Mac. Übertragen werden nur die Dateiinhalte, die Claude für eine konkrete Antwort braucht.

**Wieso passiert nichts, wenn ich nach einer Datei frage?**
Vermutlich liegt die Datei nicht im freigegebenen Pfad. Datei in `~/Documents/Github` (oder ein Unterordner) verschieben.
