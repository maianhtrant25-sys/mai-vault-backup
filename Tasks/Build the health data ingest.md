---
date: 2026-10-16
type: task
status: waiting
priority: 🟢
tags:
  - task
  - health
  - automation
related-projects:
  - "[[Projects/Health and training data pipeline]]"
ai-first: true
---

## For future agent

Host-side engineering task for [[Projects/Health and training data pipeline]], raised 2026-10-16. Turns the iPhone's health exports into vault notes. Waiting on the data-path decision and on a first export existing. No due date was given.

## Scope

- Fetch: pull the export, whatever the chosen path delivers - a cloud drive via API, files ingested at our endpoint, or a file that LiveSync has already replicated.
- Parse: daily metrics (steps, active energy, HR and HRV, resting HR, sleep score, wrist temperature) plus workouts.
- Write: the day's note, following the vault's Visual Formatting Rules in [[_CLAUDE.md]]; keep values machine-readable in frontmatter so a Bases view can compute trends.
- Verify: re-read the written note and compare it against the source export before reporting success.

## Status

- 🔗 Card in `📋 This Week` on [[Main]]; depends on [[Set up Health Auto Export on Mai's iPhone]].
- A weekly review cron writing into `Reviews/` is part of this task, not a separate one.
- Owner: the agent, under the operator's supervision.
