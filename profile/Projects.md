---
tags: [profile, projects]
---

# Projects

← [[Hisham]]

## laboratory-configs (Ansible)

**Repo:** [logician666/laboratory-configs](https://github.com/logician666/laboratory-configs)
**Status:** Active, ongoing
**Created:** 2026-04-17

Ansible playbook that fully reproduces the Fedora KDE workstation on a fresh machine.
Run: `ansible-playbook site.yml --ask-become-pass`

Key roles: packages (DNF/Flatpak), dotfiles (shell/git/kitty/tmux/starship/mutt/vscode/claude), neovim (lazy.nvim + pinned plugins), tmux (TPM), python_packages, npm_packages, applications (AppImages + .local/opt).

Sensitive files excluded from git: mutt account credentials, OAuth tokens, `.git-credentials`, `.ssh/`. These must be restored manually from encrypted backup before running the playbook on a new machine.

**sync.sh** pulls live dotfiles from `~` back into the repo (whitelist-based, not wildcard).

**Automated validation:** Weekly remote agent every Monday 08:00 Cairo audits the playbook and opens a GitHub issue if gaps are found.

## Minimal Desktop Migration

**Status:** In progress (as of 2026-05)

Moving away from KDE Plasma UI towards a minimal, terminal-first desktop:
- **Target stack:** Kitty (terminal) + Obsidian (notes) + Firefox (browser)
- **Done:** Snap removed entirely; LibreOffice moved to Flatpak-only
- **Pending:** Disable/remove unused services: ModemManager, avahi-daemon, abrtd, cups, qemu-guest-agent, vmtools, livesys, iscsi, sssd; clean up virt-manager/libvirt; remove failed odoo.service + idle postgresql

## Personal GitHub Profile (this repo)

**Repo:** [logician666/logician666](https://github.com/logician666/logician666)

Contains:
- `README.md` — GitHub profile page
- `cv/cv.tex` — LaTeX CV (moderncv banking style, deep blue accent)
- `profile/` — this Obsidian vault (personal profile for AI context)
