# Squidlet

**A tiny Claude helper critter that floats over your desktop.**

Squidlet shows a live roster of every running Claude Code session — one face per session, colored by what it's doing (working, done, needs you) — mirrors that state onto your RGB keyboard, and turns finishing real work into a game you can switch off with one click.

This repo is the **auto-update feed and installer downloads**. Source is private.

## Install

1. Download the latest **`Squidlet-Setup-x.y.z.exe`** from [Releases](../../releases/latest).
2. Run it (SmartScreen: *More info → Run anyway* — the build is unsigned).
3. Launch. Squidlet wires itself into Claude Code automatically — nothing to configure.

Prefer no install? Every release also has a single-file **portable exe**.
Installed copies check this feed and offer updates automatically (Settings → Updates).

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
| 🔧 | **Zero-setup install** — wires its own Claude Code hooks on first launch; a Setup panel diagnoses anything missing (Claude Code, Node.js, OpenRGB) and links the fix. |

## Requirements

Squidlet runs on Windows on its own, but the integrations need their tools present — it warns in-app about any that are missing:

- **Roster** — [Claude Code](https://claude.com/claude-code) installed, Node.js on PATH
- **Translate / Summarize** — the `claude` CLI, logged in
- **Keyboard lighting** — [OpenRGB](https://openrgb.org/) with its SDK server running (optional)

## Changelog

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
