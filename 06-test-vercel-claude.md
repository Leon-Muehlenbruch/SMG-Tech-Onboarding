---
title: 6. Test Vercel/Claude
nav_order: 7
---

# Kapitel 6 – Test Vercel/Claude

Wir verifizieren, dass Claude über den in [5.5](05-vercel.html#55-vercel-konnektor-in-claude-einrichten) eingerichteten Konnektor mit dem Firmen-Workspace bei Vercel reden kann – sowohl für GitHub-Repo-basierte als auch für V0-Projekte.

---

## 6.1 Vercel-Verbindung im Chat prüfen

1. Claude Desktop öffnen → neues Chat-Fenster (Cmd + N).
2. Folgendes eingeben:

   > „Liste mir bitte alle Vercel-Projekte im Workspace SawatzkiMühlenbruch GmbH auf."

3. Claude sollte mehrere Projekte aus dem Firmen-Account zurückgeben.

> **Wenn nur ein leeres oder fremdes Ergebnis kommt:** vermutlich ist beim OAuth in 5.5 der falsche Workspace gewählt worden. Konnektor entfernen und neu verbinden, dabei explizit den Firmen-Workspace bestätigen.

---

## 6.2 Build-Status nach dem Push aus Kapitel 4 abrufen

Im selben Chat:

> „Welches war das letzte Deployment im Projekt für `SMG-Test_repository`? Status, Commit-Hash und URL bitte."

Claude sollte das frisch gestartete oder abgeschlossene Deployment des Pushes aus [Schritt 4.4](04-test-und-erste-nutzung.html#44-pushen-via-claude-code) liefern.

Damit ist bewiesen: **Push aus Claude Code → GitHub → Vercel-Build → live**, alles ohne manuelles Klicken in Vercel.

---

## 6.3 Preview-URL und Build-Logs ziehen

> „Zeig mir die Build-Logs des letzten Deployments und die Preview-URL."

Claude liefert den Log-Auszug + die `*.vercel.app`-URL. URL im Browser öffnen → die deployte Version sollte erreichbar sein.

---

## 6.4 V0-Projekt einsehen

Falls im Workspace bereits ein V0-Projekt existiert:

> „Such mir ein V0-Projekt im Workspace und nenne mir dessen aktuelles Deployment plus URL."

Claude sollte ein V0-Projekt zurückgeben – auch ohne lokal verfügbares Repo. Das beweist, dass der Konnektor unabhängig vom Filesystem funktioniert ([Erklärung siehe 5.4](05-vercel.html#54-v0--projekte-ohne-github-repo)).

---

🎉 **Damit ist das gesamte Setup funktionsfähig.** Die drei Schichten – **GitHub**, **Claude**, **Vercel** – sind verbunden, und du kannst durchgängig vom Editor bis zur Live-Site arbeiten.
