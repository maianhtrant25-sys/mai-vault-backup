---
date: 2026-10-15
type: note
tags:
  - board
  - seed
ai-first: true
---

## For future agent

Seed note for `Boards/` in `mai-vault`, written 2026-10-15 so this folder replicates through LiveSync to Mai's laptop and iPhone (LiveSync copies files, not empty directories). No owner content lives here yet. This folder holds the kanban boards used by `/obsidian-task` and `/obsidian-board`.

## Purpose

- One file per board; boards carry the `kanban-plugin: board` frontmatter
- Columns: `📥 Backlog` · `📋 This Week` · `🔨 In Progress` · `⏳ Waiting On` · `✅ Done`
- Priority markers: 🔴 critical · 🟡 important · 🟢 low
- Card format: `- [ ] 🔴 **Title** · @{YYYY-MM-DD}` then a tab-indented description line with `[[links]]`
- Completed cards move to `✅ Done` struck through: `- [x] ~~🔴 **Title**~~ ✅ Date`

## Related

- [[_CLAUDE.md]] - operating manual (kanban convention, propagation rules)
- [[Home]] - vault dashboard
- [[Boards-index]] - this seed

Replace or delete this seed once real board files exist here.
