# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A demo asset for recording a product video of **MCTASKI** (the mctaski-chrome browser widget). The repo contains:

- `faro-landing-en.html` — a self-contained single-file landing page for a fictional habit-tracking app called **Faro**. All CSS and JS are inline; no build step.
- `demo-recording-guide-en.md` — full script and setup instructions for the demo recording.

## Serving the page locally

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

No build, no npm, no dependencies to install.

## The 5 intentional bugs

The HTML ships with these bugs on purpose — they are the tasks dictated via the mctaski-chrome widget during the demo recording:

| # | Location | Bug |
|---|----------|-----|
| 1 | Hero `<h1>` | Typo: "intentioons" → "intentions" |
| 2 | CTA buttons | Color `#ff4500` (orange) → `var(--accent)` (teal) |
| 3 | Footer | Copyright year "2021" → "2026" |
| 4 | Features cards | Middle card has extra text, breaking equal height — fix with `align-items: stretch` or `height: 100%` |
| 5 | Navbar links | No hover state — add color transition to `var(--accent)` |

## CSS design tokens

Defined in `:root` at the top of `faro-landing-en.html`:

- `--accent: #2d5f5d` — primary teal (use for CTAs, hover states)
- `--accent-h: #1f4a48` — darker teal for pressed/active states
- `--terracotta: #c4794d` — secondary warm color (logo mark, accents)
- `--bg: #faf7f0` — page background
- `--text: #1c1c1a` — body text

## MCTASKI ecosystem context

- **mctaski-chrome** — browser extension widget (FAB) that captures tasks with page context.
- **MCTASKI dashboard** — runs at `http://localhost:7777`; tasks sync in real time from the widget.
- During the demo, tasks are dictated into the widget → appear on the dashboard → Claude executes them → each fix lands as a git commit.
