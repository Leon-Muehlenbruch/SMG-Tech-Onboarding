---
title: Node.js
parent: Software-Referenz
nav_order: 1
---

# Node.js

## Was ist das?

Node.js ist eine **JavaScript-Laufzeitumgebung**. Sie erlaubt es, Programme, die in JavaScript geschrieben sind, direkt auf dem Mac auszuführen – ohne Browser drumherum. Mit Node.js kommt automatisch der Paketmanager **npm**, mit dem JavaScript-Tools heruntergeladen werden.

## Warum brauchen wir es bei SMG?

- Viele MCP-Server (Erweiterungen für Claude) sind in JavaScript geschrieben und brauchen Node.js zum Laufen.
- Diverse interne Tools, Build-Schritte und Skripte basieren auf Node.
- Ohne Node.js würden Teile der Claude-Integration einfach nicht starten.

## Wo ist es installiert?

Systemweit. Die Binaries liegen typischerweise unter:

```
/usr/local/bin/node
/usr/local/bin/npm
```

## Wie prüfe ich, ob's läuft?

Im Terminal:

```bash
node --version
npm --version
```

Beide Befehle sollten eine Versionsnummer ausgeben (z. B. `v20.x.x`).

## Update

Eine neue Version wird einfach durch das erneute Herunterladen der LTS-Version von <https://nodejs.org/> und Ausführen des Installers eingespielt.

## Häufige Fragen

**Muss ich da als Mitarbeitende:r jemals etwas mit machen?**
Nein. Node läuft im Hintergrund. Du merkst nur etwas davon, wenn ein Tool meckert, dass Node fehlt – dann an den Admin wenden.

**Was ist `npm`?**
Der Paketmanager, den Node mitbringt. Tools wie MCP-Server werden über `npm` installiert.
