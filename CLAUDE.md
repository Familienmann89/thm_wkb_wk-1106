# CLAUDE.md — Working Rules for This Repo

Repo purpose: course handbook + grading materials for **WK_1106 Wirtschaftsinformatik-Projekt I (Softwaretechnik), SS 2026** at THM (B.Sc. Wirtschaftsinformatik, StudiumPlus program).

Owner: Prof. Dr. Carsten Lucke. Repository is public; the README is the binding course document for students.

---

## 1. Files and their roles

### Tracked (public)

| File | Role | Audience |
|---|---|---|
| `README.md` | Course handbook (milestones, grading, git rules, AI policy) | students |
| `BEWERTUNG.md` | Per-group grading template (filled copies kept locally, never committed) | Lucke (grading) |
| `TEAMINFO.md` | Template students copy into their own repo at M0+ | students |
| `MOODLE-ANKUENDIGUNG-SS2026.html` | HTML announcement for the Moodle forum (one-shot at semester start) | Moodle |
| `MOODLE-INDEX-BLOCK-SS2026.html` | HTML text block for the Moodle course landing page (permanent pointer to this repo) | Moodle |
| `.gitignore` | macOS / OneDrive / editor noise + secret files | – |
| `.claude/commands/*` | local slash commands for Claude Code | Lucke |
| `CLAUDE.md` | this file | Claude / Lucke |

### Untracked (gitignored — local only, never push)

| File | Reason |
|---|---|
| `MOODLE.md` | contains the Moodle enrollment key |
| `moodle-qr.png` | QR code for the Moodle course URL (low risk, paired with key file) |

### Referenced from README (external)

- `https://github.com/carstenlucke/herold` — running example for Siedersleben spec + arc42 architecture (see `README.md` section 6.3, with disclaimer "work in progress").

---

## 2. Language rules

- **Student-facing / user-facing documents** (`README.md`, `BEWERTUNG.md`, `TEAMINFO.md`, `MOODLE-*.html`, `MOODLE.md`): **always German**.
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
- `MOODLE-INDEX-BLOCK-SS2026.html` does not list dates (intentional — it is a permanent pointer to the repo, kept date-free so it does not go stale).
- If a date changes after the announcement is already live in Moodle, post a separate correction announcement instead of silently rewriting the HTML.

### 3.3 TEAMINFO template
- Lives in **two places**: standalone `TEAMINFO.md` and an embedded code block in `README.md` section **4**.
- Both copies must match exactly (fields, order, notes).
- Update flow: edit `TEAMINFO.md` first, then mirror into the `README.md` code block.

### 3.4 Git rules
- **Source of truth:** `README.md` section **8** ("Git-Repository — Anforderungen").
- References in `MOODLE-ANKUENDIGUNG-SS2026.html` and `MOODLE-INDEX-BLOCK-SS2026.html` must remain compatible (Conventional Commits, tag-based submission, repo visibility).

---

## 3a. Secrets / non-public material

The repository is public. The following must **never** be committed:

- **Moodle enrollment key** — kept only in the gitignored `MOODLE.md`. Anyone with the key can self-enroll, defeating access control. Never reference the actual key value in any tracked file.
- **API keys, tokens, passwords**, `.env` files.
- **Filled-in `BEWERTUNG.md` instances** (contain Matrikel-Nummern, grades, notes about individual students).
- **Personal data** of students beyond what `TEAMINFO.md` schema allows publicly.

Mechanism: `.gitignore` lists known secret files. When a new file with sensitive content is created, **add it to `.gitignore` before staging anything**, and verify with `git check-ignore <file>` that it is excluded.

If a secret is accidentally committed: rotate the secret first (e.g. ask Moodle admin for a new enrollment key), then rewrite history. Do not just delete the file in a follow-up commit — the history still leaks it.

---

## 4. Privacy (DSGVO) — top-level principle

**Student data privacy is critical. Never instruct students to do anything that would require them to publish personal data they could legitimately keep private.**

Concrete consequences for this repo:

- **Public `TEAMINFO.md`** (and its embedded template block in `README.md` section 4) contains exactly three columns: **Name, Studiengang, Rolle** — nothing more. No emails, no phone numbers, no Matrikel-Nummern.
- **Full member data is transmitted by email only.** The project lead emails the binding member list (Name, Matrikel-Nr., THM-Mail, Studiengang, Rolle) to Lucke at **M0+** at the latest, and updates it via the M3 submission email if anything changed.
- **Phone numbers** are not collected.
- **Git author identity in commits:** require only a stable, attribute-able author name. Students freely choose which email they configure on their commits — we do not mandate a specific address.
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
- [ ] Secrets / non-public material: anything new with credentials, enrollment keys, filled grades? → add to `.gitignore` **before** staging, verify with `git check-ignore`.
- [ ] Commit message in English, Conventional Commits format?

---

## 7. Tone toward students

- Direct and respectful, never condescending.
- AI tooling is treated as **allowed and realistic** — disclosure obligation and individual code walkthrough are the counter-controls, not a ban.
- Hurdle rule and the option of an individual grade adjustment are **announced explicitly** — no hidden rules.
