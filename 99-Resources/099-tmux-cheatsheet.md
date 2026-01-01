---
id: 099-tmux-cheatsheet
aliases: []
tags: []
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
| **Split Vertical** | `Prefix` + `%` | Creates side-by-side layout. (Shift+5) |
| **Split Horizontal** | `Prefix` + `"` | Creates top-bottom layout. |
| **Maximize (Zoom)** | `Prefix` + `m` | Toggles full screen focus on active pane. |
| **Close Pane** | `Prefix` + `x` | Prompts for confirmation (`y`). |
| **Break Pane** | `Prefix` + `!` | Pops pane out to its own Window. |

## 2. 📑 Windows (Workspaces)
*Manage separate desktops (Tabs). In "Mission Control", these are pre-defined.*

| Action | Key Binding | Result |
| :--- | :--- | :--- |
| **Go to Editor** | `Prefix` + `1` | **1:Editor** (Neovim/Obsidian). |
| **Go to Terminal** | `Prefix` + `2` | **2:Terminal** (System Shell). |
| **Go to Monitor** | `Prefix` + `3` | **3:Monitor** (Btop/K9s). |
| **Next Window** | `Prefix` + `n` | Cycles forward. |
| **Prev Window** | `Prefix` + `p` | Cycles backward. |
| **Rename** | `Prefix` + `,` | Renames current window. |

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

### ⚡ The 30-Second Daily Drill
*Execute this sequence daily to build muscle memory.*
1.  **Launch:** Start `~/bin/mission-control.sh`.
2.  **Check Monitors:** `Prefix` + `3`.
3.  **Focus Drill:** `Ctrl+l` (Right) -> `Ctrl+h` (Left).
4.  **Zoom Drill:** Focus on Btop -> `Prefix` + `m` (Maximize) -> `Prefix` + `m` (Restore).
5.  **Split Drill:** `Prefix` + `%` (Split Vertical) -> Type `echo test` -> `Prefix` + `x` (Close).
6.  **Return to Base:** `Prefix` + `1`.

**Prefix Key:** `Ctrl + a`
