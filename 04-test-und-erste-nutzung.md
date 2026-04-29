---
title: 4. Test & erste Nutzung
nav_order: 5
---

# Kapitel 4 – Test & erste Nutzung

Wir verifizieren, dass alle Komponenten miteinander reden, und führen den ersten echten Roundtrip aus: Aufgabe an Claude → Code-Änderung → Push auf GitHub.

---

## 4.1 Verbindungen im Chat prüfen

1. Claude Desktop öffnen → neues Chat-Fenster (Cmd + N).
2. Folgendes eintippen und absenden:

   > „Hast du Zugriff auf das Filesystem unter `~/Documents/Github` und auf meine GitHub-Connection?
   > Liste mir bitte alle Ordner auf, die du im Filesystem siehst, und nenne ein Repository, das du über GitHub erreichen kannst."

3. Claude sollte:
   - den Ordner `SMG-Test_repository` aus 2.5 auflisten,
   - mindestens ein Repo aus der Organisation nennen.

> **Wenn das nicht klappt:** Zurück zu [3.6](03-claude.html#36-filesystem-mcp-einrichten) und [3.7](03-claude.html#37-github-connection-einrichten), Konnektor erneut verbinden, App neu starten.

---

## 4.2 Claude Code öffnen und neues Projekt anlegen

1. In Claude Desktop oben in den **„Code"**-Tab wechseln.
2. **„New Project"** klicken.
3. Als Working Directory den Repo-Ordner wählen:

   ```
   ~/Documents/Github/SMG-Test_repository
   ```

4. Projekt benennen (z. B. `SMG-Test`) → bestätigen.

Claude indexiert kurz die Dateien im Ordner.

---

## 4.3 Test-Aufgabe geben

> **🚧 Inhalt der Test-Aufgabe noch festzulegen.**
> Vorschläge zur Diskussion:
> - „Lege im Repo eine Datei `hallo-<dein-name>.md` an, schreibe einen kurzen Vorstellungstext rein."
> - „Ergänze in der `README.md` einen Eintrag mit deinem Namen unter der Überschrift `## Team`."
>
> Wenn entschieden, hier ersetzen.

Im Code-Tab in das Eingabefeld die Aufgabe eingeben und absenden. Claude zeigt:

- welche Dateien er liest,
- welche Änderungen er vorschlägt,
- bittet dich ggf. um Bestätigung vor dem Schreiben.

Bestätigen, bis die Datei lokal angelegt/geändert ist.

---

## 4.4 GitHub-Authentifizierung einrichten (GitHub CLI)

Damit Claude Code beim Pushen auf das Remote-Repo schreiben darf, brauchen wir eine **lokale Git-Authentifizierung am Mac**. Wir nutzen dafür die offizielle **GitHub CLI** (`gh`).

> **🔑 Wichtig zu verstehen: Was wird hier eigentlich autorisiert?**
>
> Wir autorisieren in diesem Schritt **den Mac selbst** gegenüber GitHub – **nicht Claude direkt**.
>
> | Schritt | Was wird autorisiert? | Wofür? |
> |---|---|---|
> | [3.7 GitHub-Connection](03-claude.html#37-github-connection-einrichten) | **Claude** (die App) | Lesen von Repos, Issues, PRs *im Chat* |
> | **4.4 GitHub-CLI (`gh`)** | **Dieser Mac** (lokales Git) | Schreibende Git-Operationen wie `git push` |
>
> Claude Code nutzt für Git-Operationen schlicht den **lokalen Git-Stack** auf deinem Mac. Sobald der mit GitHub verbunden ist (über die Schlüsselbund-Anbindung von `gh`), kann Claude pushen, indem er einfach `git push` aufruft – und das verwendet automatisch die Credentials deines PCs. Claude muss dafür **kein eigenes GitHub-Passwort und keinen eigenen Token bekommen**.
>
> Das ist sicherheitstechnisch der saubere Weg: Tokens wandern nicht durch die KI, sondern liegen ausschließlich im macOS-Schlüsselbund.

### a) GitHub CLI installieren

1. Browser → <https://github.com/cli/cli/releases/latest>
2. Im Abschnitt **„Assets"** die passende Datei laden:
   - Apple-Silicon-Mac (M1/M2/M3/M4): `gh_*_macOS_arm64.pkg`
   - Intel-Mac: `gh_*_macOS_amd64.pkg`
3. `.pkg`-Datei doppelklicken und Installer durchklicken.
4. Im Terminal verifizieren:

   ```bash
   gh --version
   ```

### b) Authentifizierung durchführen

Im Terminal eingeben:

```bash
gh auth login
```

Im interaktiven Dialog der Reihe nach auswählen:

1. **GitHub.com**
2. Protokoll: **HTTPS**
3. „Authenticate Git with your GitHub credentials?" → **Y**
4. „How would you like to authenticate?" → **Login with a web browser**
5. Den angezeigten 8-stelligen Code merken → Enter drücken → der Browser öffnet sich → Code eintragen → Account-Autorisierung bestätigen.

### c) Verifizieren

```bash
gh auth status
```

Erwartete Ausgabe (sinngemäß):

```
github.com
  ✓ Logged in to github.com as <dein-username>
  ✓ Git operations for github.com configured to use https protocol.
```

### Was passiert da technisch?

`gh` legt einen OAuth-Token im **macOS-Schlüsselbund** ab und konfiguriert `git` so, dass jede Verbindung zu github.com automatisch diesen Token verwendet. Du musst dich nie wieder einloggen oder Tokens manuell verwalten – auch nicht nach einem Reboot.

Mehr Details siehe [Software-Referenz: GitHub CLI](software/github-cli.html).

---

## 4.5 Pushen via Claude Code

1. Im Code-Tab eingeben:

   > „Pushe die Änderungen."

2. Claude führt aus (in dieser oder ähnlicher Reihenfolge):
   - `git status`
   - `git add <datei>`
   - `git commit -m "<sinnvolle Nachricht>"`
   - `git push`
3. Eventuelle Rückfragen (z. B. zur Commit-Message) beantworten.

---

## 4.6 Push auf GitHub verifizieren

1. Browser → <https://github.com/SawatzkiMühlenbruchGmbH/SMG-Test_repository>
2. Im Reiter **„Code"** prüfen, ob die Datei aus 4.3 erschienen ist.
3. Im Reiter **„Commits"** den frisch gepushten Commit mit deinem Namen finden.

🎉 **Wenn das alles klappt, ist das Setup erfolgreich abgeschlossen.**

---

## ✅ Abschluss-Check Gesamt-Setup

- [ ] Claude erkennt Filesystem & GitHub im Chat
- [ ] Test-Projekt in Claude Code angelegt
- [ ] Test-Aufgabe ausgeführt, Datei lokal verändert
- [ ] GitHub-Auth eingerichtet
- [ ] Push erfolgreich auf github.com sichtbar

Bei Problemen → Admin oder [Software-Referenz](software/) konsultieren.
