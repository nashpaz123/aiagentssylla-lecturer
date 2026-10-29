# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

**Lecturer scripts** for a Hebrew-language "AI Agents" course (SPRINT Tech Academy), produced as **pre-recorded sessions**. The lecturer reads a script on camera while the student slides are shown on screen.

Student-facing materials (slides, labs, demos, assets) live in the sibling repo [`nashpaz123/aiagentssylla`](https://github.com/nashpaz123/aiagentssylla) (local path often `/stuff/prj/aiagentssylla/`). Keep both checkouts when editing so you can sync slide numbers.

## Per-session file structure and sync rules

Each session `NN` has:
- **This repo:** `NN-<topic>.md` — the **lecturer script** (full narration, camera cues, demos, appendices)
- **Student repo:** `NN-students-slides.md` — the deck shown on screen; plus `assets/NN/`, optional `labs/NN-*/`, `demos/NN-*/`, and `NN-exec-briefing.md` (sessions 7–8)

These rules come from the student README / recording SOP, and edits must keep them true:
- Slides are numbered `1…N`. For every student slide `## ‏N — Title`, the lecturer script has a matching block `## ‏N — Title` with `[סטודנטים · N]` and the same title. Never add lecturer content sections that have no matching student number. You may expand the narration inside a block.
- From session 2 on, every code or pseudocode block in the lecturer script must also appear in the student slide with the same number.
- Recording ≠ live class. Don't write pauses for thinking, audience Q&A or student solve-time. Exercises are lecturer demos with the full solution narrated aloud, or a lab the lecturer runs.
- Target length from session 2 on is about 2.5–3 hours of continuous recording (sessions 5–6 run about 2–2.5 hours), so scripts must be dense and fully narrated.
- From session 7 on, labs and demos are key/model-based (Anthropic, Claude Code, Cursor). **Don't build deterministic no-API fallback paths** for them.
- At the start of a session, recaps of the previous session are a short pointer only.

## Hebrew / RTL markdown conventions

- Every doc is wrapped in `<div dir="rtl" lang="he">…</div>`. Newer docs use `style="direction: rtl; text-align: right; unicode-bidi: embed;"`.
- A U+200F RLM character (`‏`) is placed at the start of headings, after list numbers, and at the start of table cells whose text begins with Latin characters or markup (e.g. `## ‏3 — …`, `1. ‏**Rules…`, `| ‏**MCP** |`). Without it, mixed Hebrew/English lines align left. Keep it when you add or edit such lines.
- Commit messages are in Hebrew and prefixed with the session, e.g. `מפגש 8: …`.
