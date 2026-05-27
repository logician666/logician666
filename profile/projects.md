---
tags: [profile, projects]
---

# Projects

← [[hisham]]

## Personal Foundations — Five-Repo Architecture

These five repositories are the core of my personal foundations. Each is a bounded context; content never crosses boundaries.

| Repo | Models | Local path |
|---|---|---|
| [[#logician666 (this repo)]] | Identity, career, profile | `~/personal/logician666/` |
| [[#thoughts]] | Life strategy, direction, personal memory | `~/personal/thoughts/` |
| [[#knowledge]] | Formal learning system | `~/personal/knowledge/` |
| [[#sys-arch]] | Linux workstation setup, work tooling | `~/personal/sys-arch/` |
| [[#parkour]] | Physical training programme | `~/personal/parkour/` |

---

## logician666 (this repo)

**Repo:** [logician666/logician666](https://github.com/logician666/logician666)

- `README.md` — GitHub profile page
- `cv/cv.tex` — LaTeX CV (moderncv banking style, deep blue accent)
- `profile/` — this Obsidian vault; authoritative personal profile for AI context and self-reference

---

## thoughts

**Repo:** `logician666/thoughts` · **Local:** `~/personal/thoughts/`

Personal thinking repository — life strategy, direction-setting, decisions, memory of the past, contemplation of the future. Not a task tracker or learning portfolio.

**Structure:**
- `journal/` — daily journals
- `fragments/` — raw thought fragments
- `learning/` — exploratory learning notes (informal; formal nodes live in `knowledge/`)
- `memory/` — personal memories of significant moments
- `strategy/`, `decisions/`, `synthesis/`, `plans/` — structured reasoning artefacts

**Scope rule:** Never write formal knowledge nodes here. Never write parkour content here.

---

## knowledge

**Repo:** `logician666/knowledge` · **Local:** `~/personal/knowledge/`

Formal secondary brain — a dependency-ordered knowledge model, not a notes store. Authoritative node index and dependency graph live in `nodes/INDEX.md`; consult it (or query the Obsidian vault) rather than maintaining a node count here. Cluster directories:

- `formal-foundations/` — mathematical logic, ontology, relational theory, process theory/formal verification
- `domain-modelling/` — DDD, conceptual data modelling
- `modelling-notation/` — BPMN 2.0, UML 2.5, SysML 1.6, DMN 1.3, CMMN 1.1
- `enterprise-architecture/` — EA, BMM, ArchiMate 3.1, TOGAF 10th ed., European regulatory
- `requirements/` — RE (ISO 29148), software quality (ISO 25010), SDLC standards
- `implementation/` — Python type system, OOP, data access, domain architecture, testing, data analysis
- `systems-administration/` — Fedora, terminal stack, editor/multiplexer, mail, database
- `music/` — acoustics, music theory, tonal harmony, post-tonal, mathematical music theory
- `business-domains/` — capstone node

Governed by three skills: `/knowledge-inquirer` (read), `/knowledge-scribe` (write), `/knowledge-manager` (organise).

**Scope rule:** Never write personal strategy or life notes here. Never write parkour content here.

---

## sys-arch

**Repo:** [logician666/sys-arch](https://github.com/logician666/sys-arch) · **Local:** `~/personal/sys-arch/`

Ansible playbook that fully reproduces the Fedora workstation on a fresh machine.
Run: `ansible-playbook site.yml --ask-become-pass`

Key roles: packages (DNF/Flatpak), dotfiles (shell/git/kitty/tmux/starship/mutt/vscode/claude), neovim, tmux (TPM), python_packages, npm_packages, applications.

**sync.sh** pulls live dotfiles from `~` back into the repo (whitelist-based).
**Automated validation:** Weekly remote agent every Monday 08:00 Cairo — audits for gaps and opens a GitHub issue if problems are found.

*Minimal desktop migration in progress:* Moving from KDE Plasma to Kitty + Obsidian + Firefox. Snap removed; LibreOffice → Flatpak-only. Services cleanup still pending.

---

## parkour

**Repo:** `logician666/parkour` · **Local:** `~/personal/parkour/`

Obsidian vault containing a 16-week periodised conditioning programme with 6 gated phases:

| Phase | Weeks | Unlock condition |
|---|---|---|
| 1 Foundation | 1–2 | Starting phase |
| 2 Static Strength | 3–4 | All 6 Phase 1 sessions complete |
| 3 Dynamic Strength | 5–6 | 15 push-ups + wall sit 60s |
| 4 Explosive Power | 7–8 | Nordic curl 80% depth · stick landing 4/5 · dead hang 40s |
| 5 Body Control | 9–12 | Silent depth drop · explosive push-up hands airborne · reactive circuit stable |
| 6 Pre-Parkour Integration | 13–16 | Full Phase 5 assessment passed |

Dataview + Templater plugins. Session logs at `logs/` with `type: parkour-session` frontmatter.

**Scope rule:** Parkour content belongs exclusively here.

---

## Career Architecture

**Primary model:** Aletheum — a consultancy, not employment.
**Target market:** European market (Netherlands, Belgium, Germany) within 2–3 years.

**Certification path:**
1. Odoo Functional Consultant — Aletheum partner certification
2. Python — Odoo customisation depth
3. JavaScript — OWL framework / frontend
4. DevOps / Linux — infrastructure self-sufficiency
5. SE certifications (OMG modelling, SE BOK) — long-term architectural credentialing

RE/BA certifications (CPRE, TOGAF) are no longer being pursued as primary targets.
