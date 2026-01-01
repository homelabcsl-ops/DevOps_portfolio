---
id: 098-changelog-phase0
aliases:
  - Phase 0 Changelog
  - System Update 2025-12-31
tags:
  - changelog
  - system-manual
  - phase-0
  - tmux
  - wezterm
date: "2025-12-31"
---

# 📝 System Change Log: Phase 0 (Cockpit Drill)

**Objective:** Establish Frictionless "Mission Control" Environment
**Status:** Implemented & Verified

## 1. Interface Unification (WezTerm)
**File:** `~/.config/wezterm/wezterm.lua`

* **Action:** Navigation Passthrough
    * **Change:** Added `config.keys` mapping to forward `CTRL + h/j/k/l` directly to Tmux, bypassing WezTerm interception.
* **Action:** Auto-Launch
    * **Change:** Set `default_prog` to execute `~/bin/mission-control.sh` on startup.

## 2. Workspace Multiplexer (Tmux)
**File:** `~/.tmux.conf`

* **Action:** Smart Navigation
    * **Change:** Implemented `is_vim` logic to seamlessly switch between Neovim splits and Tmux panes using standard directional keys.
* **Action:** Visual Hierarchy (Titanium Theme)
    * **Active Border:** Teal (`#008080`) to denote focus.
    * **Inactive Border:** Grey (`colour237`) to reduce noise.
    * **Status Bar:** Configured for DevOps context (K8s Context | Git Branch | Hostname).
* **Action:** Keybindings
    * **Resizing:** Added `bind -r` for `h/j/k/l` (Resize by 5 cells).
    * **Zoom:** Added `bind m` to toggle pane maximization.

## 3. Automation Scripts
**File:** `~/bin/mission-control.sh` (New File)

* **Action:** Idempotent Startup
    * **Logic:** Script checks for "DKS-Main" session.
        * **If missing:** Builds 3-window layout.
        * **If exists:** Attaches immediately.
* **Layout Definition:**
    1.  **Editor:** `~/obsidian/devops` + `nvim`
    2.  **Terminal:** `~` (Home)
    3.  **Monitor:** `btop` (Split with `k9s`)

## 4. Neovim Integration
**File:** `~/.config/nvim/lua/plugins/tmux.lua` (New File)

* **Action:** Plugin Installation
    * **Change:** Added `christoomey/vim-tmux-navigator` to enable the Neovim side of the "Unibody" navigation.

---
- [ ] **Next Step:** Full system restart (or `kill-server`) required to apply all hooks.

### 🎨 Visual Polish Update (Addendum)

**Date:** 2026-01-01
**Context:** Finalizing Phase 0 Aesthetic

#### 1. WezTerm Configuration
**File:** `~/.config/wezterm/wezterm.lua`
* **Action:** Transparency & Blur (Glass Effect)
    * **Change:** Added `config.window_background_opacity = 0.8`.
    * **Change:** Added `config.macos_window_background_blur = 10`.
    * **Result:** Terminal now has a semi-transparent "frosted glass" background, improving integration with the macOS environment while maintaining the "Titanium" color scheme.

   ### 🎨 Visual Calibration: Exact "Carbonfox" Match (Update 1.2)

**Date:** 2026-01-01
**Objective:** Synchronize WezTerm colors 1:1 with LazyVim `theme.lua` overrides.

#### 1. WezTerm Configuration
**File:** `~/.config/wezterm/wezterm.lua`
* **Action:** Hardcoded Palette Alignment
    * **Background:** Set to `#161616` (Deep Charcoal) to match `nightfox.nvim` `bg1` override.
    * **Selection:** Set to `#2b2b2b` to match `sel0` override.
    * **Foreground:** Set to `#b6b8bb` (Foggy Grey).
    * **Reason:** Eliminates visual "jump" when opening/closing Neovim.
* **Action:** ANSI Palette Standardization
    * **Colors:** Mapped strictly to Carbonfox defaults (e.g., Yellow = `#08bdba` Teal).
* **Action:** Visual Integration
    * **Glass Effect:** Retained `opacity = 0.8` and `blur = 10` for macOS integration. 
