---
id: 099-tmux-cheatsheet
aliases:
  - Tmux Navigation
  - Mission Control Guide
  - Unibody Workflow
tags:
  - devops
  - tool/tmux
  - workflow/efficiency
  - phase-0
date: "2025-12-31"
---

# 🕹️ Tmux & Mission Control Cheat Sheet

> [!NOTE] Philosophy
> This system uses a **"Unibody"** configuration. Neovim splits and Tmux panes are treated as a single navigation surface using `Ctrl` + `Direction`.

## 1. 🪟 Panes (Screen Splits)
*Manage the subdivisions within your current view.*

| Action | Key Binding | Context / Notes |
| :--- | :--- | :--- |
| **Move Focus** | `Ctrl` + `h` `j` `k` `l` | **No Prefix.** Works across Neovim & Tmux seamlessly. |
| **Resize Pane** | `Prefix` + `h` `j` `k` `l` | **Repeatable.** Tap multiple times to grow/shrink. |
| **Split Vertical** | `Prefix` + `%` | Creates side-by-side layout. |
| **Split Horizontal** | `Prefix` + `"` | Creates top-bottom layout. |
| **Maximize (Zoom)** | `Prefix` + `m` | Toggles full screen focus on active pane. |
| **Close Pane** | `Prefix` + `x` | Prompts for confirmation (`y`). |

## 2. 📑 Windows (Workspaces)
*Manage separate desktops (Tabs). In our "Mission Control" setup, these are pre-defined.*

| Action | Key Binding | Result |
| :--- | :--- | :--- |
| **Go to Editor** | `Prefix` + `1` | Jumps to **1:Editor** (Neovim/Obsidian). |
| **Go to Terminal** | `Prefix` + `2` | Jumps to **2:Terminal** (System Shell). |
| **Go to Monitor** | `Prefix` + `3` | Jumps to **3:Monitor** (Btop/K9s). |
| **Next Window** | `Prefix` + `n` | Cycles forward. |
| **Prev Window** | `Prefix` + `p` | Cycles backward. |
| **New Window** | `Prefix` + `c` | Creates a fresh workspace. |
| **Rename** | `Prefix` + `,` | Renames current window for clarity. |

## 3. 💾 Sessions (The Persistent World)
*Manage the lifecycle of your work environment.*

| Action | Command / Key | Description |
| :--- | :--- | :--- |
| **Start / Resume** | `~/bin/mission-control.sh` | **Preferred Method.** Idempotent launch script. |
| **Detach (Pause)** | `Prefix` + `d` | Leaves background processes running. |
| **List Sessions** | `Prefix` + `s` | Visual menu to switch between projects. |
| **Scroll Mode** | `Prefix` + `[` | Enter Copy Mode (Use `vi` keys to scroll). |
| **Kill Server** | `tmux kill-server` | **Hard Reset.** Destroys all active sessions. |

## 🛠️ Visual Indicators (Titanium Theme)

- **Teal Border** (`#008080`): The currently active pane. Input will go here.
- **Grey Border**: Inactive panes.
- **Status Bar (Bottom):**
    - `1:Editor*`: Asterisk denotes active window.
    - `MacMini 25`: Verifies you are connected to the host.

---
**Prefix Key:** `Ctrl + b` (Default) OR `Ctrl + a` (Custom)
