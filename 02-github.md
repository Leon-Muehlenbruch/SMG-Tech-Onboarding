---
title: 2. GitHub
nav_order: 3
---

# Kapitel 2 – GitHub

GitHub ist die Plattform, auf der wir unsere Projekte (Repositories) speichern und gemeinsam an Code arbeiten.

---

## 2.1 GitHub-Account erstellen

1. Browser öffnen → <https://github.com/signup>
2. Account mit der **Firmen-E-Mail-Adresse** erstellen.
3. Passwort wählen (Passwortmanager empfohlen).
4. Username vergeben (z. B. `vorname-nachname-smg`).
5. Den Bestätigungs-Code aus der E-Mail eintragen.

> **Hinweis:** Für den persönlichen Workspace reicht der kostenlose Plan. Die Firmenfunktionen kommen über die Organisation.

---

## 2.2 Org-Einladung annehmen

Der Admin hat dich vorab zur Organisation **SawatzkiMühlenbruch GmbH** eingeladen. Die Einladung wird direkt in GitHub angezeigt — ein E-Mail-Client ist nicht nötig.

1. Im Browser auf <https://github.com/> einloggen.
2. Oben rechts auf das Profilbild → **„Your organizations"**.
3. Bei **SawatzkiMühlenbruch GmbH** auf **„Join"** klicken.

Du landest danach auf der Organisations-Seite und solltest dort als Mitglied gelistet sein.

> **Falls keine Einladung angezeigt wird:** Admin Bescheid geben.

---

## 2.3 GitHub Desktop installieren

GitHub Desktop ist die grafische Oberfläche, mit der wir Repositories ohne Terminal verwalten können.

1. Browser → <https://desktop.github.com/>
2. **„Download for macOS"** klicken.
3. Heruntergeladene `.zip` doppelklicken → die App `GitHub Desktop` in den Ordner **Programme** ziehen.
4. App starten (Spotlight → „GitHub Desktop").

Mehr Details siehe [Software-Referenz: GitHub Desktop](software/github-desktop.html).

---

## 2.4 In GitHub Desktop einloggen

1. Beim ersten Start auf **„Sign in to GitHub.com"** klicken.
2. Browser öffnet sich → mit dem eben erstellten Account einloggen.
3. Autorisierung bestätigen.
4. Zurück in GitHub Desktop:
   - Name und Commit-E-Mail werden vorausgefüllt → übernehmen.
   - Frage zu Usage-Daten beantworten (egal welche Auswahl).

---

## 2.5 Test-Repository klonen

> **Warum überhaupt lokal arbeiten, wenn die Daten doch auf GitHub liegen?**
> Auf GitHub liegt die *offizielle* Version eines Repositories – das ist der gemeinsame Speicher- und Austauschort fürs Team. Bearbeitet wird aber immer eine **lokale Kopie** auf deinem Mac. Werkzeuge wie Claude Code, Editoren oder das Terminal arbeiten direkt mit Dateien im Dateisystem, nicht mit der GitHub-Weboberfläche. Du machst lokal deine Änderungen, kannst sie ausprobieren, bevor jemand sie sieht – und schickst sie erst per `commit` + `push` zurück nach GitHub.
>
> Kurz: **GitHub = Lager**, **lokales Verzeichnis = Werkstatt**.

1. In GitHub Desktop oben links auf **„Current Repository"** → **„Clone repository…"**
2. Im Tab **„GitHub.com"** das Repo `SawatzkiMühlenbruchGmbH/SMG-Test_repository` auswählen.
3. **Wichtig:** Den Pfad belassen auf

   ```
   ~/Documents/Github/SMG-Test_repository
   ```

   (das ist der Standardpfad, wenn der Arbeitsordner aus [Kapitel 1](01-vorab.html) korrekt angelegt wurde).
4. Auf **„Clone"** klicken.

Nach wenigen Sekunden ist das Repository lokal vorhanden.

---

## 2.6 GitHub-CLI installieren und authentifizieren

GitHub Desktop bringt seine eigene Authentifizierung mit – fürs **Klonen** über die App reicht das. Für spätere `git push`-Operationen aus dem Terminal (z. B. wenn Claude Code Änderungen hochladen soll) brauchen wir zusätzlich eine **systemweite Git-Authentifizierung**. Dafür nutzen wir die offizielle **GitHub CLI** (`gh`).

> **🔑 Wichtig zu verstehen:**
> Wir autorisieren in diesem Schritt **den Mac selbst** gegenüber GitHub – nicht Claude direkt. Sobald der lokale Git mit GitHub verbunden ist (über den macOS-Schlüsselbund), kann jedes Tool, das `git push` aufruft – auch Claude Code – diese Verbindung nutzen, ohne ein eigenes Passwort oder einen eigenen Token zu sehen.

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

Mehr Details siehe [Software-Referenz: GitHub CLI](software/github-cli.html).
