---
id: 001-System-Verification
aliases:
  - Smoke Test
  - commissioning
tags:
  - meta
  - system
  - test
status: In Progress
---

# 🚀 System Verification Checklist (v1.6.0)

**Objective:** Validate the integrity of the Mac Mini 2025 DevOps Environment.

## 1. Dashboard & Telemetry (The Cockpit)
- [ ] **Startup:** Restart Neovim. Does the "DEVOPS KNOWLEDGE SYSTEM" header appear?
- [ ] **Telemetry:** Do you see live stats (CPU/Mem/Disk) in the dashboard center?
    - *If "No":* Did you create/chmod `~/.config/nvim/scripts/telem.sh`?
- [ ] **Smart Launch:** From the Dashboard, press `<leader>on`.
    - *Pass Criteria:* Does it open a **new** buffer without the "Buffer not modifiable" error?

## 2. Knowledge Management (The Brain)
- [ ] **Workspace Routing:**
    - Run `:ObsidianWorkspace devops`. Create a note. Check file path: is it in `~/obsidian/devops`?
    - Run `:ObsidianWorkspace personal`. Create a note. Check file path: is it in `~/obsidian/personal`?
- [ ] **Templating:**
    - inside a note, press `<leader>ot`. Select `daily-note`.
    - *Pass Criteria:* Does it insert the Date/Time headers?
- [ ] **Search:** Press `<leader>oo`. Does it grep through your notes?

## 3. DevOps Engineering Stack (The Tools)
- [ ] **Context Awareness (Lualine):**
    - Create a file named `main.tf`.
    - *Pass Criteria:* Does the bottom bar icon change to "󱁢 IaC" (Purple)?
    - Rename it to `Dockerfile`.
    - *Pass Criteria:* Does the icon change to " OPS" (Blue)?
- [ ] **Pre-Flight Check (Snacks):**
    - Inside `main.tf`, write some garbage text.
    - Press `<leader>tv`.
    - *Pass Criteria:* Does a floating terminal appear running `terraform validate`?
- [ ] **Git Operations:**
    - Press `<leader>gg`.
    - *Pass Criteria:* Does LazyGit open as a floating window?

## 4. UI & Aesthetics (The Experience)
- [ ] **Mission Control:**
    - Press `<leader>tm`.
    - *Pass Criteria:* Does the theme toggle between "Muted" (Dark Grey) and "High Contrast" (Deep Blue)?

## 5. Sync & Backup
- [ ] **Auto-Save:** Save this file (`:w`).
- [ ] **Verification:** Open a terminal in `~/obsidian/devops`. Run `git log`.
    - *Pass Criteria:* Do you see a commit message "Auto-save"?

---
**Sign-off:**
**Engineer:** __________________
**Date:** {{date}}
