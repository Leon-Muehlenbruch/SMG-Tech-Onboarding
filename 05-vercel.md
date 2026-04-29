---
title: 5. Vercel
nav_order: 6
---

# Kapitel 5 – Vercel

Vercel ist die Hosting-Plattform, auf der unsere Websites laufen. Jedes Projekt-Repo bei GitHub hat ein zugehöriges **Vercel-Projekt** – bei jedem Push auf `main` deployt Vercel die Site automatisch neu.

Außerdem nutzen wir **V0** (<https://v0.dev>) – ein KI-Werkzeug von Vercel, das ganze Mini-Apps aus Text-Prompts generiert. V0-Projekte landen direkt bei Vercel, **ohne über ein GitHub-Repo zu gehen**.

---

## 5.1 Vercel-Account erstellen

1. Browser → <https://vercel.com/signup>
2. **„Continue with Email"** → Account mit der **Firmen-E-Mail-Adresse** anlegen.
3. Bestätigungs-Mail öffnen und Link klicken.
4. Profilangaben ausfüllen (Username, Passwort).

> **⚠️ Wichtig:** Mit dem neuen Account bekommst du automatisch einen kostenlosen **persönlichen Workspace** (Free-Plan). **Lege dort niemals SMG-Projekte an** – die gehören in den Firmen-Workspace, der gleich folgt.

---

## 5.2 Firmen-Team beitreten

Der Admin hat dich vorab in das Vercel-Team **SawatzkiMühlenbruch GmbH** eingeladen.

1. Nach dem Login: oben links auf den **Workspace-Switcher** klicken.
2. Falls eine Einladung wartet: **„Accept invitation"**.
3. Anschließend **SawatzkiMühlenbruch GmbH** als aktiven Workspace wählen.

Du erkennst, dass alles passt, wenn:

- der Workspace-Switcher oben links den Firmen-Namen anzeigt,
- du **mehrere bestehende Projekte** in der Übersicht siehst (statt eines leeren Dashboards).

> **Falls keine Einladung erscheint:** Admin Bescheid geben.
>
> **Goldene Regel:** Beim Anlegen, Importieren oder Verbinden eines Projekts immer prüfen, ob oben links der **Firmen-Workspace** aktiv ist – nicht der persönliche Free-Account.

---

## 5.3 GitHub-Verbindung autorisieren

Damit Vercel weiß, wann auf einem GitHub-Repo etwas Neues passiert ist, muss die GitHub-App von Vercel auf der SMG-Org installiert sein. Diese Installation hat der Admin in der Regel bereits **auf Org-Ebene** erledigt – du musst nur prüfen, dass dein eigener Account angebunden ist.

> **🔑 Was wird hier autorisiert?**
> Diesmal autorisieren wir **Vercel**, GitHub-Webhooks und Repo-Zugriff für die SMG-Org zu erhalten – analog zu den bisherigen Auth-Schichten:
>
> | Schritt | Wer wird autorisiert? |
> |---|---|
> | [2.6 GitHub CLI](02-github.html#26-github-cli-installieren-und-authentifizieren) | Dein Mac (lokales Git) |
> | [3.7 GitHub-Connection](03-claude.html#37-github-connection-einrichten) | Claude (App) |
> | **5.3 Vercel-GitHub-App** | **Vercel** |

1. Im Vercel-Dashboard auf **Settings → Git**.
2. Bei **„GitHub"** sollte stehen: „Connected as `<dein-username>`".
3. Falls nicht: **„Connect"** klicken → mit GitHub einloggen → SMG-Org auswählen.

---

## 5.4 V0 – Projekte ohne GitHub-Repo

V0 ist Vercels AI-Builder unter <https://v0.dev>. Drei Dinge, die du beim Onboarding wissen musst:

1. V0-Projekte werden **direkt in Vercel deployt**. Es gibt **kein GitHub-Repo**, das du klonen oder lokal in `~/Documents/Github` haben kannst.
2. Trotzdem tauchen V0-Projekte in der Vercel-Projektliste auf – wie alle anderen Projekte auch.
3. Sie sind über den **Vercel-Konnektor in Claude** (siehe nächster Schritt) **vollständig steuerbar**: Build-Logs, Deployments, Domains, Rollbacks. Was nicht geht: an deren *Source* lokal arbeiten – die Quelle bleibt in der V0-/Vercel-Cloud.

> Wenn du also über Claude einen V0-Build inspizierst und nichts findest, was nach Repo aussieht – das ist **erwartet**, kein Fehler.

---

## 5.5 Vercel-Konnektor in Claude einrichten

Damit Claude im Chat Deployments einsehen, Build-Logs lesen und (sofern erlaubt) Deploys auslösen kann.

1. Claude Desktop → **Einstellungen → Connectors**.
2. Konnektor **„Vercel"** suchen → **„Connect"**.
3. Browser öffnet sich → bei der Authorisierung den **Firmen-Workspace** auswählen (nicht den persönlichen Free-Account!).
4. Bestätigung erteilen.
5. Zurück in Claude → der Konnektor zeigt **„Connected"**.
6. Claude Desktop einmal neustarten (⌘ + Q → neu öffnen), damit der Konnektor sicher geladen wird.

> **Wenn Claude später nur einen leeren Vercel-Account sieht:** Bei der OAuth-Bestätigung wurde der falsche Workspace gewählt. Konnektor entfernen und neu verbinden, dabei explizit **SawatzkiMühlenbruch GmbH** bestätigen.

---

## 5.6 Preview vs. Production – kurz erklärt

| | Preview | Production |
|---|---|---|
| Wann erzeugt? | Bei Push auf jeden Branch oder bei jedem PR | Bei Push auf `main` |
| URL | Eindeutig generiert, z. B. `<projekt>-git-<branch>.vercel.app` | Stabile Domain, z. B. `<projekt>.vercel.app` oder Custom-Domain |
| Wofür? | Änderungen testen, ohne Live-Site zu beeinflussen | Was die Welt sieht |

Heißt: Während du an einem Branch arbeitest, hast du immer eine funktionierende Test-URL. Erst beim Merge in `main` wird die produktive Site aktualisiert.

---

Mehr Details siehe [Software-Referenz: Vercel](software/vercel.html).
Weiter geht's mit **[Kapitel 6 – Test Vercel/Claude](06-test-vercel-claude.html)**.
