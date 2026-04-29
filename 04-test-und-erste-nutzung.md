---
title: 4. Test GitHub/Claude
nav_order: 5
---

# Kapitel 4 – Test GitHub/Claude

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

## 4.4 Pushen via Claude Code

Da die GitHub-Authentifizierung bereits in [Schritt 2.6](02-github.html#26-github-cli-installieren-und-authentifizieren) eingerichtet wurde, kann Claude Code direkt pushen.

1. Im Code-Tab eingeben:

   > „Pushe die Änderungen."

2. Claude führt aus (in dieser oder ähnlicher Reihenfolge):
   - `git status`
   - `git add <datei>`
   - `git commit -m "<sinnvolle Nachricht>"`
   - `git push`
3. Eventuelle Rückfragen (z. B. zur Commit-Message) beantworten.

---

## 4.5 Push auf GitHub verifizieren

1. Browser → <https://github.com/SawatzkiMühlenbruchGmbH/SMG-Test_repository>
2. Im Reiter **„Code"** prüfen, ob die Datei aus 4.3 erschienen ist.
3. Im Reiter **„Commits"** den frisch gepushten Commit mit deinem Namen finden.

✅ Damit funktioniert der Loop **GitHub ↔ Claude**. Weiter geht's mit **Vercel** in [Kapitel 5](05-vercel.html).
