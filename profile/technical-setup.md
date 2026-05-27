---
tags: [profile, tech, setup]
---

# Technical Setup

← [[hisham]]

## Hardware

**Lenovo ThinkPad L13 Yoga Gen 2** (model 20VLS20600)
- NVMe SSD: 476.9 GB (`/dev/nvme0n1`)
- Dual-boot: Fedora KDE + Windows
- Has `thinkpad_acpi` support for fan control
- CPU power management: intel_pstate + EPP (no daemon; custom udev rule + systemd service)

### Partition Layout

| Partition | Size | FS | Mount | Notes |
|---|---|---|---|---|
| nvme0n1p1 | 1000 MB | vfat | /boot/efi | EFI (shared) |
| nvme0n1p2 | 16 MB | — | — | Windows MSR |
| nvme0n1p3 | 239 GB | ntfs | WIN | Windows C: |
| nvme0n1p4 | 980 MB | ntfs | — | Windows Recovery/OEM |
| nvme0n1p5 | 60 GB | ext4 | / | Fedora root |
| nvme0n1p6 | 100 GB | ext4 | /home | Fedora home |
| nvme0n1p7 | 60 GB | ntfs | SHARED | Cross-OS shared data |
| nvme0n1p8 | 14 GB | swap | [SWAP] | Linux swap (zram is primary) |
| nvme0n1p9 | 863 MB | — | — | Unknown/unformatted |
| nvme0n1p10 | 1000 MB | ntfs | WinRE_DRV | Windows Recovery Environment |

## Operating System

- **OS:** Fedora Linux (KDE Plasma)
- **Direction:** Migrating away from KDE UI towards a minimal desktop — **Kitty + Obsidian + Firefox only**
- **Display server:** Wayland (clipboard: `wl-copy`)
- **Shell:** Bash (primary), Xonsh (scripting/interactive experiments)

## Terminal Stack

| Tool | Role | Notes |
|---|---|---|
| **Kitty** | Terminal emulator | Glass-teal dark theme (Aletheum palette); Kitty graphics protocol enabled |
| **Tmux** | Multiplexer | TPM plugins; vi copy-mode; `wl-copy` integration |
| **NeoVim** | Editor | lazy.nvim plugin manager; Catppuccin theme; lazy-lock.json pins plugins |
| **Starship** | Prompt | Minimalist config with λ character; LaTeX module custom-built |
| **Bash / Xonsh** | Shell | `.bash_aliases`, `.bash_profile`, shell helpers in `~/.config/shell/` |
| **Git** | VCS | gh CLI; global gitignore; gitk config |

### NeoVim Details

- Plugin manager: lazy.nvim
- Config: `~/.config/nvim/init.lua` + `lua/config/` + `lua/plugins/`
- Plugin versions pinned in `lazy-lock.json`
- Theme: Catppuccin
- Key constraint: **never set `textwidth` or `colorcolumn` for markdown/text filetypes**

### Tmux Details

- Vi copy-mode (`mode-keys vi`)
- `v` to begin selection, `y` to copy (pipes to `wl-copy`, stays in scrollback — does not use `copy-pipe-and-cancel`)
- TPM plugins: tmux-resurrect + tmux-continuum (auto-restore, 15-min save interval)

## Fonts

- **Terminal font:** JetBrainsMono Nerd Font
- Installed manually to `~/.local/share/fonts/JetBrainsMonoNF/` (Fedora system package lacks NF glyphs)
- System package `jetbrains-mono-fonts-all` also present for non-NF use

## Applications

| App | Category | Notes |
|---|---|---|
| Firefox | Browser | Primary |
| Obsidian | Notes | Per-project vaults at `notes/` subdirectory |
| Mutt | Email | Multi-account: Outlook + Gmail via OAuth2 |
| Kitty | Terminal | See above |
| Calibre | eBooks | |
| Beets | Music library | Config at `~/.config/beets/` |
| VLC | Media | |
| GIMP / Inkscape | Graphics | |
| LibreOffice | Office | Flatpak only (`org.libreoffice.LibreOffice`) |
| Camunda Modeler | BPMN | Business process modelling |
| MuseScore | Music notation | |
| Archi | Enterprise Architecture | |
| ActivityWatch | Time tracking | |
| Beekeeper Studio | DB GUI | |
| JupyterLab | Data science | |
| Okular | PDF viewer | Flatpak |
| spotify-player | Music streaming (TUI) | Primary Spotify client — Aletheum-themed; like keybind configured |
| Spotify (web) | Music streaming | Fallback only — never the desktop Flatpak app |

## Ansible Configuration Repo

All system configuration is captured in `~/sys-arch/` (Ansible playbook).
Repo: [logician666/sys-arch](https://github.com/logician666/sys-arch)

Key roles: `packages`, `dotfiles`, `neovim`, `tmux`, `python_packages`, `npm_packages`, `applications`.
Run: `ansible-playbook site.yml --ask-become-pass`

A weekly remote validation routine (`ansible-validation-weekly`) runs every Monday at 08:00 Cairo via Claude Code Routines, auditing the playbook for gaps and opening a GitHub issue if problems are found.

## Project Structure Conventions

Every project repo follows:

```
notes/                          Obsidian vault root
documentation/                  Sphinx docs (if applicable)
requirements/                   StrictDoc requirements (if applicable)
notes/journals/daily/           Work journals (daily_jrnl-YYYYMMDD.md)
```

Journal files use YAML frontmatter with `date: YYYY-MM-DD` and `tags: [daily-journal, project/{name}]`.
