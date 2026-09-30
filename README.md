# Squidlet

**A tiny Claude helper critter that floats over your desktop.**

Squidlet shows a live roster of every running Claude Code session — one face per session, colored by what it's doing (working, done, needs you) — mirrors that state onto your RGB keyboard, and turns finishing real work into a game you can switch off with one click.

This repo is the **auto-update feed and installer downloads**. Source is private.

## Install (three steps)

1. Download the latest **`Squidlet-Setup-x.y.z.exe`** from [Releases](../../releases/latest) and run it.
2. Windows will say *"Windows protected your PC"* — click **More info → Run anyway**. (The build isn’t code-signed yet; that’s all this means.)
3. **Start a Claude Code chat.** Squidlet connects itself to Claude Code the first time it opens — nothing to configure. Chats that were already open before that need a restart to show up.

The card tells you what to do next if anything is missing.

- **Want your keyboard to light up?** Tap the **💡 Want keyboard lighting?** tip on the card and press **Install OpenRGB now** — Squidlet installs the free OpenRGB app for you and turns the lights on when it’s done.
- **Where did it go?** The ✕ hides Squidlet to the system tray (by the clock). Click the tray icon to bring it back; right-click it for Settings, **Setup & requirements…**, and Quit.
- **Updates** arrive on their own: an "Update available" strip appears on the card (or check Settings → Updates).

Prefer no install? Every release also has a single-file **portable exe** (it can’t self-update).

## What it can do

| | Capability |
|---|---|
| 🐙 | **Mission-control roster** — one face per running Claude Code session, colored by state (working / done / needs-you). Each row shows what that Claude is doing *right now* (`⚙ npm test`, `✎ renderer.js`), what it just finished, and flags when it's stuck. Click to **jump to the live session** — its terminal, or a real chat in the Claude Desktop app. |
| 🔎 | **Search every chat** — full-text search across all your Claude Code transcripts on disk, most-recent-first with a snippet and match count per session. Pure local reads — no API traffic, works offline. |
| 🌈 | **Keyboard & RGB sync** — mirrors session state onto OpenRGB devices (keyboard, fans). Animated or static effects, brightness control, clean hand-back to firmware on idle or quit. |
| ⚡ | **One-click Claude actions** — Translate clipboard, Summarize my day, plus your own custom prompt buttons, via your existing `claude` CLI. No API key, no extra cost. |
| 🎮 | **Focus game layer** — earn points as sessions finish real work; quests, focus timer, flow bonuses, daily recap, and a store of unlockable faces, colors, and sounds. Or flip to Zen mode and it all goes quiet. |
| ⏱️ | **5-hour window tracker** — watches Claude's rolling rate-limit block and paints it as a progress line on the card, with a reset-time tooltip and a ceremony for fully-used blocks. |
| 🪟 | **Overlay controls** — always-on-top pinning, click-through mode for gaming, drag-resize, adjustable transparency, edge-snapping, remembered position, multi-monitor safe. |
| 🔄 | **Self-updating** — installed copies pull updates from this feed. |
| 🔧 | **Zero-setup install** — wires its own Claude Code hooks on first launch and needs nothing else installed. A Setup panel (tray → Setup & requirements…) shows what’s connected, and installs OpenRGB or Node.js for you in one click. Uninstalling removes the hooks again. |

## Requirements

Squidlet runs on Windows on its own, but the integrations need their tools present — it warns in-app about any that are missing:

- **Roster** — [Claude Code](https://claude.com/claude-code) installed. Nothing else: Squidlet brings its own runtime for the hooks. (Node.js is optional — if it’s on PATH the hooks run a touch faster.)
- **Translate / Summarize / custom prompts** — the `claude` CLI, logged in (optional; the roster works without it)
- **Keyboard lighting** — [OpenRGB](https://openrgb.org/) (optional; the card offers a one-click install)

## Changelog

### 0.1.71 — Sep 30, 2026 — easier first launch
- **Friendlier first launch** — an empty card says what to do, hiding to the tray explains itself once, and the Setup page is always one click away (tray → Setup & requirements…)
- **No extra installs** — Node.js is no longer required; the roster works out of the box (Node.js is still used automatically when present, ~30 ms faster per event)
- **One-click OpenRGB install** for keyboard lighting, right from the card; first launch without OpenRGB starts with sync off instead of a permanent warning
- **Translate picks your languages** (Settings → Actions), **cleaner uninstall** (hooks removed), and hooks that self-heal after the app is moved

### 0.1.43 – 0.1.70 — Sep 2026
- **Open the exact chat** — a click focuses the live window (terminal or Claude Desktop) without forking the session; the card always returns home afterwards
- **Terminal sessions are first-class** — same click behavior and green/amber bookkeeping whether Claude runs in a terminal or in the Desktop app
- **Codex (ChatGPT) support** — Codex threads join the roster when Codex is installed
- Many finish/stall accuracy fixes, a performance pass (no cursor hitches), and a drag fix for scaled displays

### 0.1.33 — Sep 1, 2026
- **Search every chat** — full-text search across all your Claude Code transcripts, most-recent-first with a snippet and per-session match count; pure local reads, no tokens
- **Open a session in the Claude Desktop app** — jump from a roster face straight into a real desktop chat, alongside the terminal resume
- **Cleaner orchestration finishes** — a `/review`, `/audit`, or Workflow that fans out background agents now celebrates once, at the real end, instead of firing a false "done" per turn boundary

### 0.1.26 — Aug 31, 2026
- **Mission control** — every roster row shows what its Claude is doing right now, what it just finished, and flags when it's stuck; click to jump to the live session's window
- **Per-project identity** — sessions grouped and colored by project, renamable
- **Windows toasts** — a native ping when a session needs you while the card is hidden (silenced during a focus timer)
- **Custom prompt buttons**, an optional **global show/hide hotkey**, and **response-time stats with 7-day trends**

### 0.1.17 — Aug 29, 2026
- **Claude 5-hour usage window** — bottom-edge progress line for your current rate-limit block: hover for the reset time, amber/red as it runs out, fireworks ceremony for a fully-worked block
- **Transparency slider** (30–100%) with live preview
- **Multi-monitor fix** — the card no longer snaps to the wrong screen near monitor edges
- Faster, boosted store music previews

### 0.1.5 – 0.1.16 (rolled into 0.1.17)
- **Focus game layer** — points for finishing (never fiddling), quests, focus timer, flow bonuses, level-ups, daily recap; Zen mode to silence it all
- **Points store** — unlockable faces, color families, sounds, and music tracks with previews
- **Auto-update system** — installed builds self-update from this feed
- **Multi-device RGB** — fans alongside the keyboard, plus game reward pulses
- Stability and customization passes across the card, settings, and RGB engine

### 0.1.4 — Aug 28, 2026
- First published build: live roster, OpenRGB keyboard sync, Translate / Summarize actions, tray controls, self-installing hooks
