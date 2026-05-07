# 📝 Guide: Conventional Commits für Einsteiger

Schluss mit Commit-Nachrichten wie „update", „fix" oder „test1". **Conventional Commits** sorgen für ein sauberes, lesbares Git-Log, das sowohl Menschen als auch Maschinen (KI-Tools) verstehen.

## 1. Das Grundformat
Jede Nachricht folgt diesem einfachen Schema:

`typ(bereich): beschreibung`

*   **Typ:** Was wurde gemacht? (Pflicht)
*   **Bereich (Scope):** Welcher Teil wurde geändert? (Optional, z. B. `login`, `api`, `ui`)
*   **Beschreibung:** Kurz, knapp und im Imperativ (Befehlsform), z. B. „add login button" statt „added login button".

---

## 2. Die wichtigsten Typen
Für den Anfang reichen diese sechs Typen völlig aus:

| Typ | Bedeutung |
| :--- | :--- |
| **`feat`** | Ein neues Feature (Funktion) wird hinzugefügt. |
| **`fix`** | Ein Fehler (Bug) wurde behoben. |
| **`docs`** | Änderungen an der Dokumentation (z. B. README.md). |
| **`style`** | Formatierung, Semikolons, Leerzeichen (keine Logik-Änderung). |
| **`refactor`** | Code-Verbesserung, die weder Bugfix noch Feature ist. |
| **`chore`** | Wartungsaufgaben (Updates von Bibliotheken, Build-Tools). |

---

## 3. Beispiele aus dem Alltag
*   **Feature:** `feat(auth): add password reset functionality`
*   **Bugfix:** `fix(ui): repair broken navigation link on mobile`
*   **Doku:** `docs: update installation instructions`
*   **Breaking Change:** `feat!: change api response format` (Das **!** signalisiert: Vorsicht, das bricht alte Funktionen!)

---

## 4. 🤖 Profi-Tipp: KI & Programmieragenten nutzen
Heutzutage musst du die Nachrichten oft gar nicht mehr selbst tippen. KI-gestützte Editoren (z. B. Cursor) oder Agenten (wie Claude oder GitHub Copilot) können deine Änderungen analysieren und direkt die passende Nachricht vorschlagen.

### Automatisierung über MD-Dateien
Du kannst deinem Agenten diese Regeln fest vorgeben, damit er sich immer daran hält. Erstelle dazu einfach eine Datei wie `AGENTS.md`, `CLAUDE.md` oder `.cursorrules` im Hauptverzeichnis deines Projekts:

> **Konfiguration für KI-Agenten:**
> "Bitte verwende für alle Git-Commits in diesem Projekt strikt den Conventional Commits Standard (feat, fix, docs, etc.). Schreibe die Nachrichten kurz, prägnant und auf Englisch."

---

## 5. Warum das Ganze?
1.  **Ordnung:** Du verstehst auch in sechs Monaten noch, was du heute getan hast.
2.  **Teamwork:** Deine Kollegen sehen sofort, welche Commits wichtig sind (z. B. Features vs. Refactoring).
3.  **Automatisierung:** Tools können aus diesen Nachrichten automatisch Versionsnummern vergeben oder Changelogs generieren.

**Goldene Regel:** Schreib deine Commits so, dass dein zukünftiges Ich dich dafür lieben wird!
