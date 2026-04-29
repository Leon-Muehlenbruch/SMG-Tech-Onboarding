---
title: GitHub CLI (gh)
parent: Software-Referenz
nav_order: 7
---

# GitHub CLI (`gh`)

## Was ist das?

`gh` ist das **offizielle Kommandozeilen-Tool von GitHub**. Es übernimmt zwei Hauptaufgaben auf deinem Mac:

1. **Authentifizierung** des lokalen Git-Stacks gegenüber GitHub (im Schlüsselbund hinterlegt).
2. **GitHub-API-Aufrufe** vom Terminal aus (Repos klonen, Issues anlegen, PRs öffnen …).

Für unser Onboarding ist Punkt 1 der entscheidende: Ohne `gh` müsste man Personal Access Tokens manuell anlegen und sicher ablegen.

## Warum brauchen wir es bei SMG?

- Damit `git push`/`git pull`/`git fetch` ohne ständige Passwort-Abfragen funktionieren.
- Damit **Claude Code** pushen kann, ohne selbst Credentials sehen zu müssen – Claude ruft schlicht `git push` auf, und der lokale Git verwendet automatisch den von `gh` hinterlegten Token aus dem macOS-Schlüsselbund.
- Damit kein Token-File irgendwo auf der Platte liegt.

## Wo ist es installiert?

Systemweit unter `/usr/local/bin/gh` (Intel-Mac) bzw. `/opt/homebrew/bin/gh` (Apple Silicon).

## Wer wird hier eigentlich autorisiert?

Sehr häufige Verwechslung – darum nochmal in Klartext:

| Autorisierung | Eingerichtet in | Wirkt für | Erlaubt |
|---|---|---|---|
| **GitHub-Connection** | Claude Desktop ([3.7](../03-claude.html#37-github-connection-einrichten)) | Claude (die App) | Lesen von Repos/Issues/PRs **im Chat** |
| **`gh auth login`** | Terminal ([4.4](../04-test-und-erste-nutzung.html#44-github-authentifizierung-einrichten-github-cli)) | Dein Mac (lokales Git) | Alle Git-Operationen, inkl. `push` |

Beide sind nötig, aber sie machen unterschiedliche Dinge.

## Wie prüfe ich, ob's läuft?

```bash
gh --version
gh auth status
```

`auth status` sollte „Logged in to github.com as …" zeigen.

## Nützliche Alltagsbefehle

| Aufgabe | Befehl |
|---|---|
| Aktuellen Login prüfen | `gh auth status` |
| Anderen Account ergänzen | `gh auth login` |
| Aktuelles Repo im Browser öffnen | `gh repo view --web` |
| Pull Request anlegen | `gh pr create` |
| PRs auflisten | `gh pr list` |

## Updates

Über den `.pkg`-Installer von <https://github.com/cli/cli/releases/latest> oder, falls Homebrew installiert ist:

```bash
brew upgrade gh
```

## Häufige Fragen

**Wo liegt der Token?**
Im macOS-Schlüsselbund (Keychain Access → Suche nach „github.com"). Nicht in einer Datei, nicht in `~/.gitconfig`.

**Was passiert, wenn ich mich auf github.com überall ausgelogge?**
Der bestehende OAuth-Token bleibt gültig, bis du ihn explizit widerrufst (github.com → Settings → Applications → Authorized OAuth Apps → „GitHub CLI" → Revoke).

**Brauche ich `gh` täglich?**
Nein – für die meisten Mitarbeitenden ist `gh` ein **stilles Backend-Werkzeug**, das nur einmal beim Onboarding eingerichtet wird. Danach passiert alles über GitHub Desktop oder Claude Code.
