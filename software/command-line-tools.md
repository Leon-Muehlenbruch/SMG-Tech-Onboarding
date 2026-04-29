---
title: Command Line Tools
parent: Software-Referenz
nav_order: 2
---

# Apple Command Line Tools

## Was ist das?

Die Command Line Tools (auch „Xcode CLT") sind ein **Paket grundlegender Entwicklungs­werkzeuge** von Apple. Es enthält unter anderem:

- `git` (Versionskontrolle)
- `clang` (C/C++-Compiler)
- `make`, `gcc`, viele Standard-Unix-Werkzeuge
- Header-Dateien für macOS

Es ist die abgespeckte Variante von Xcode – ohne die GUI-IDE, aber mit allen Kommandozeilen-Tools.

## Warum brauchen wir es bei SMG?

- **`git`** ist Voraussetzung für GitHub Desktop und für jede Code-Arbeit.
- Viele npm-Pakete und MCP-Server **kompilieren beim Installieren native Bestandteile** und brauchen dafür einen Compiler.
- Ohne CLT scheitern viele Installationen mit einer kryptischen „command not found"- oder „xcrun"-Fehlermeldung.

## Wo ist es installiert?

Systemweit unter `/Library/Developer/CommandLineTools/`. Die einzelnen Befehle liegen in `/usr/bin/`.

## Wie prüfe ich, ob's läuft?

```bash
git --version
xcode-select -p
```

`xcode-select -p` gibt den Installationspfad zurück, wenn alles ok ist.

## Update

macOS schlägt Updates über die **Software-Aktualisierung** in den Systemeinstellungen vor. Diese können einfach übernommen werden.

## Häufige Fragen

**Brauche ich Xcode (die große IDE) auch?**
Nein. Die CLT reichen für unsere Zwecke.

**Was passiert, wenn ich macOS upgrade?**
Manchmal müssen die CLT nach einem macOS-Major-Update neu installiert werden. Dann meldet sich z. B. `git` mit „xcrun: error: invalid active developer path". Lösung: erneut `xcode-select --install` ausführen.
