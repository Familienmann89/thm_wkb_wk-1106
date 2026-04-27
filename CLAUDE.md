# CLAUDE.md — Working Rules for This Repo

Repo purpose: course handbook + grading materials for **WK_1106 Wirtschaftsinformatik-Projekt I (Softwaretechnik), SS 2026** at THM (B.Sc. Wirtschaftsinformatik, StudiumPlus program).

Owner: Prof. Dr. Carsten Lucke. Repository is public; the README is the binding course document for students.

---

## 1. Files and their roles

| File | Role | Audience |
|---|---|---|
| `README.md` | Course handbook (milestones, grading, git rules, AI policy) | students |
| `BEWERTUNG.md` | Per-group grading template (one filled copy per project, kept locally) | Lucke (grading) |
| `TEAMINFO.md` | Template students copy into their own repo at M0+ | students |
| `MOODLE-ANKUENDIGUNG-SS2026.html` | HTML announcement for Moodle (Moodle ignores Markdown here) | Moodle |
| `.gitignore` | macOS / OneDrive / editor noise | – |
| `.claude/commands/*` | local slash commands for Claude Code | Lucke |

---

## 2. Language rules

- **Student-facing / user-facing documents** (`README.md`, `BEWERTUNG.md`, `TEAMINFO.md`, `MOODLE-ANKUENDIGUNG-*.html`): **always German**.
- **Internal files** (`CLAUDE.md`, `.claude/**`): English is fine.
- **Commit messages:** always English.
- **Code/tool/CLI terms:** keep original (e.g. "Conventional Commits", "Git-Tag", "arc42").
- **Date format in German docs:** weekday + German month, e.g. `Fr, 8. Mai 2026`.

---

## 3. Consistency rules (mandatory)

The following documents must stay in sync. When you change one, update every place that mirrors it.

### 3.1 Grading criteria
- **Source of truth:** `BEWERTUNG.md` (full criteria tables with point distribution).
- **Mirror:** `README.md` section **10.3** ("Bewertungskriterien je Säule (Übersicht)") — lists the same criterion names, **without** the per-criterion points.
- If a criterion is added, renamed, or removed: update both files.

### 3.2 Milestones / dates
- **Source of truth:** `README.md` section **3** ("Termine und Meilensteine für SS 2026").
- **Mirror:** `MOODLE-ANKUENDIGUNG-SS2026.html` (overview list), as long as the announcement has not been posted yet.
- If a date changes after the announcement is already live in Moodle, post a separate correction announcement instead of silently rewriting the HTML.

### 3.3 TEAMINFO template
- Lives in **two places**: standalone `TEAMINFO.md` and an embedded code block in `README.md` section **4**.
- Both copies must match exactly (fields, order, notes).
- Update flow: edit `TEAMINFO.md` first, then mirror into the `README.md` code block.

### 3.4 Git rules
- **Source of truth:** `README.md` section **8** ("Git-Repository — Anforderungen").
- References in `MOODLE-ANKUENDIGUNG-SS2026.html` must remain compatible (Conventional Commits, tag-based submission, repo visibility).

---

## 4. Privacy (DSGVO) — top-level principle

**Student data privacy is critical. Never instruct students to do anything that would require them to publish personal data they could legitimately keep private.**

Concrete consequences for this repo:

- `TEAMINFO.md` and the embedded template block in `README.md` must contain only the **minimum data** needed to identify the team (name, study program, role).
- **Email addresses** in templates are **optional**, never mandatory. A single team contact is enough; individual members must not be forced to publish their THM email.
- **Phone numbers** are not allowed in public templates.
- **Matrikel-Nummern** are forbidden in any public file. The binding member list with Matrikel-Nummern is sent only via the M3 submission email to Lucke (`README.md` section 5.3).
- **Git author identity in commits:** require only a stable author name (so contributions can be attributed). Do not require students to expose their THM email — GitHub's `noreply` email or any other personal email choice is acceptable.
- `BEWERTUNG.md` has columns for Matrikel-Nr and individual notes. Filled-in instances are kept **locally** in Lucke's grade archive, never committed to this public repo or to any student repo.

When changing any student-facing rule, ask: *Does this force a student to publish data they could legitimately keep private?* If yes, soften the requirement.

---

## 5. Commit discipline

- **Conventional Commits** for every commit (the same standard students must follow).
- Subject in lowercase, imperative mood, no trailing period.
- Examples:
  - `docs: clarify section heading binds milestones to SS 2026`
  - `feat(grading): add Tests/QS criterion in pillar 3`
  - `chore: add .gitignore for macOS noise`
- **Never commit without explicit instruction.** Apply edits, show status, propose commit message, wait for OK.
- Force-push, amend, `--no-verify`, `reset --hard` only on explicit user request.

---

## 6. Change checklist

Before committing any content change, walk through:

- [ ] Grading criteria changed? → `README.md` (10.3) **and** `BEWERTUNG.md` in sync.
- [ ] Date / milestone changed? → `README.md` (3) **and** `MOODLE-ANKUENDIGUNG-SS2026.html`.
- [ ] TEAMINFO fields changed? → `TEAMINFO.md` **and** `README.md` section 4 code block.
- [ ] Section numbering in `README.md` contiguous and cross-references correct?
- [ ] Privacy: no Matrikel-Nr / phone in public templates? Email handled as optional (single team contact is enough)?
- [ ] No requirement on students forces them to publish personal data?
- [ ] Commit message in English, Conventional Commits format?

---

## 7. Tone toward students

- Direct and respectful, never condescending.
- AI tooling is treated as **allowed and realistic** — disclosure obligation and individual code walkthrough are the counter-controls, not a ban.
- Hurdle rule and the option of an individual grade adjustment are **announced explicitly** — no hidden rules.
