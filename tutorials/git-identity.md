# 👤 Guide: Git-Identität eindeutig setzen

Damit die Beteiligung am Code sauber **pro Person** nachvollziehbar ist (relevant spätestens für M3 / die Bewertung, siehe README Abschnitt 8.3 und 10.5), braucht es in jeder Gruppe eine eindeutige Zuordnung **Commit → Person**.

Wenn Commits unter dem reinen GitHub-/GitLab-Username laufen (z. B. `mikael123`), lässt sich von außen nicht erkennen, wer im Team das war. Bitte erledigt **eines der beiden** Verfahren je Gruppenmitglied.

---

## Option A — sauber: Git-Identität auf Klarnamen + THM-Mail setzen

Einmal pro Rechner im geklonten Projektordner ausführen:

```bash
git config user.name  "Vorname Nachname"
git config user.email "vorname.nachname@mnd.thm.de"
```

Wer das **systemweit** für alle Repositories setzen möchte (statt nur projektlokal):

```bash
git config --global user.name  "Vorname Nachname"
git config --global user.email "vorname.nachname@mnd.thm.de"
```

- Wirkt **ab dem nächsten Commit**.
- Zukünftige Commits sind damit eindeutig zuordenbar.
- Bestehende Commits müssen **nicht** umgeschrieben werden.

Prüfen, was aktuell gesetzt ist:

```bash
git config user.name
git config user.email
```

---

## Option B — minimal: Plattform-Username in TEAMINFO.md ergänzen

Wer die Git-Identität nicht ändern will/kann (z. B. weil derselbe Rechner für mehrere Projekte unter einem festen Account genutzt wird), trägt in der `TEAMINFO.md` pro Mitglied den **verwendeten Plattform-Username** ein:

```markdown
| Name | Studiengang | Rolle |
|---|---|---|
| Vorname Nachname (GitHub: mikael123) | WI B.Sc. | Projektleiter:in |
```

Damit lässt sich die Zuordnung über die `TEAMINFO.md` herstellen.

---

## Wichtig: Zeitpunkt

- **Vor dem nächsten Commit-Schub** umsetzen — je früher, desto weniger Historie ist betroffen.
- Bestehende Commits **nicht** nachträglich umschreiben (Filter-Branch / `git filter-repo`): das verändert die Historie auch für alle anderen im Team und macht mehr Probleme als es löst.
- Ab Setzung der Identität bzw. Eintragung in `TEAMINFO.md` ist alles Weitere abgedeckt.

---

## Hintergrund: Welche E-Mail-Adresse?

Aus Datenschutzsicht ist die Wahl der Commit-E-Mail **freigestellt** (siehe README Abschnitt 8.3). Verbindlich ist nur ein **stabiler, eindeutig zuordenbarer Name**. Wer auf GitHub die private Noreply-Adresse (`<id>+<username>@users.noreply.github.com`) nutzen möchte, kann das tun — solange der `user.name` als Klarname gesetzt ist oder die Zuordnung über Option B erfolgt.
