---
tags: [profile, preferences, working-style]
---

# Preferences & Working Style

← [[hisham]]

## Language & Writing

- Always use **British English** (en-GB spelling): "organise", "licencing", "colour", "realise", etc.
- Configure all spell checkers, LTeX, and language tools for `en-GB`.

## Personal Interests

- Deep passion for **Logic and Mathematics**. Self-studied from leaving the Faculty of Science (~2016) and throughout the Faculty of Commerce until graduation in 2020; suspended thereafter by KSA accounting work, never withdrawn.
- Formal re-entry to mathematics is **postponed** behind two gates: (i) Odoo Functional Consultant certification, and (ii) primary Aletheum business setup — ERP+CRM, website, and essential legal documents (tax ID, commercial registration). The 2026-05-13 Enderton attempt is paused under this gating.
- Currently focused on mastering business analysis methodology, techniques, and applications.
- Plays **chess** on Chess.com: username `logician666x` (original `logician666` was deleted during a difficult period).

## File & Identifier Naming

- **Kebab (`-`)** separates distinct concepts; **snake (`_`)** glues tokens within a single concept.
- Example: `flat6labs-odoo_acct` reads as `[flat6labs] — [odoo account]`; `forever_bikes-kyc.md` reads as `[forever bikes] — [kyc]`.
- Applies to filenames, folders, branches, and any user-facing slug. Lowercase throughout unless context requires otherwise.

## Fragrance

- Prefers **masculine, sharp, fresh** profiles: aquatic and citrus notes with a cold/icy/menthol feel.
- Family: fresh aquatic / ozonic / mentholated citrus (e.g. Adidas Ice Dive, Davidoff Cool Water territory).
- Avoid: warm/oriental, amber, musk-forward, spicy, gourmand, woody-sweet.

## Tool Preferences

- **Spotify:** Use `spotify-player` (TUI) as primary client, or the web player (`https://open.spotify.com/...`) as fallback. Never use the desktop Flatpak app or the `spotify:` URI protocol — the desktop app is considered a resource hog.
- **Terminal-first:** Strongly prefer CLI, daemon-based, or config-file-driven solutions over GUI tools. Avoid recommending KDE-integrated or GUI-heavy tools.
- **Flatpak over Snap:** When packaging matters, prefer Flatpak. Snap was removed from the system entirely (2026-05-07).

## NeoVim

- **Never** set `textwidth` or `colorcolumn` for markdown or text filetypes. Hard-wrapping is unwanted in prose files.
- Soft-wrap settings (`wrap`, `linebreak`, `breakindent`) are acceptable.

## Terminal Theming

- **Palette-tracking over fixed hex.** TUI themes should use named colours (or `colorN` indices 0–15) so they follow the active terminal palette. When Kitty swaps its Aletheum dark↔light scheme (via `aletheum-theme-current.conf`), every palette-tracking TUI updates on next redraw without further configuration.
- Avoid `#RRGGBB` themes unless a pixel-perfect brand match is required *and* the full terminal stack supports truecolour (terminal + multiplexer terminfo with `Tc` + application built with truecolour).
- Use `bold` and `reverse` attributes aggressively for emphasis (indicator, status bar, search hits) — relying on colour alone is fragile across palette swaps.

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

## Journal scope

- Journals (`thoughts/journal/` and per-project `notes/journals/`) record **actions taken and activities performed** — what I did, decided, or hit a wall on. They are a chronological log of work.
- Journals are **not** a notebook for information acquired or retrieved during a session. Validated knowledge routes to `knowledge/nodes/…` via `/knowledge-scribe` (or `knowledge/nodes/inbox/` if unvalidated). Project-specific findings route to the project's structured documentation (e.g. `analysis-docs/syrs/` in `odoo-ref`).
- When a session produces both action and learning: log the action in the journal, scribe the learning to the knowledge graph or project docs. The journal entry may *reference* the knowledge node, but the answer content does not live in the journal.
- Rationale: two stores, two roles. Journal answers "what did I do on date X?" — knowledge graph answers "what do I know about topic Y?". Mixing them breaks both queries.
