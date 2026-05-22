---
tags: [profile, preferences, working-style]
---

# Preferences & Working Style

← [[hisham]]

## Language & Writing

- Always use **British English** (en-GB spelling): "organise", "licencing", "colour", "realise", etc.
- Configure all spell checkers, LTeX, and language tools for `en-GB`.

## Personal Interests

- Deep passion for **Logic and Mathematics** — has been interested since age 20.
- Aspires to formally study Logic and Maths once current BA career is established.
- Currently focused on mastering business analysis methodology, techniques, and applications.
- Plays **chess** on Chess.com: username `logician666x` (original `logician666` was deleted during a difficult period).

## File & Identifier Naming

- **Kebab (`-`)** separates distinct concepts; **snake (`_`)** glues tokens within a single concept.
- Example: `flat6labs-odoo_acct` reads as `[flat6labs] — [odoo account]`; `forever_bikes-kyc.md` reads as `[forever bikes] — [kyc]`.
- Applies to filenames, folders, branches, and any user-facing slug. Lowercase throughout unless context requires otherwise.

## Tool Preferences

- **Spotify:** Always open via web browser (`https://open.spotify.com/...`). Never use the desktop Flatpak app or the `spotify:` URI protocol. The web player is preferred; the desktop app is considered a resource hog.
- **Terminal-first:** Strongly prefer CLI, daemon-based, or config-file-driven solutions over GUI tools. Avoid recommending KDE-integrated or GUI-heavy tools.
- **Flatpak over Snap:** When packaging matters, prefer Flatpak. Snap was removed from the system entirely (2026-05-07).

## NeoVim

- **Never** set `textwidth` or `colorcolumn` for markdown or text filetypes. Hard-wrapping is unwanted in prose files.
- Soft-wrap settings (`wrap`, `linebreak`, `breakindent`) are acceptable.

## Collaboration Style

- Prefers terse, direct responses — no trailing summaries explaining what was just done.
- Comfortable with deep technical detail; treat as a power user.
- Values rigour and formal correctness — sloppy approximations are not appreciated.
- Expects tools and assistants to remember context and not repeat guidance.

## Project Repo Layout

Every project repository follows this subdirectory convention:

- `notes/` — Obsidian vault root for the project.
- `documentation/` — Sphinx docs (if the project has docs).
- `requirements/` — StrictDoc requirements (if the project has formal requirements).

## Obsidian / Notes

- Per-project Obsidian vault lives at `notes/` inside the project repo.
- Work journals at `notes/journals/daily/daily_jrnl-YYYYMMDD.md` — one file per day, sessions as H2 sections.
- Journal YAML frontmatter: `date: YYYY-MM-DD`, `tags: [daily-journal, project/{name}]`.
- Never create a flat `notes/journal.md` — always use the daily path.
