---
date: 2026-10-15
type: note
tags:
  - person
  - seed
ai-first: true
---

## For future agent

Seed note for `People/` in `mai-vault`, written 2026-10-15 so this folder replicates through LiveSync to Mai's laptop and iPhone (LiveSync copies files, not empty directories). No owner content lives here yet. This folder holds one note per person, maintained by `/obsidian-person`.

## Purpose

- One note per person: full name as the filename (e.g. `Jane Smith.md`), never a first name alone
- Frontmatter: `type: person`, `date`, `tags`, plus `role`, `company`, and a bi-temporal `timeline:` array for changes (role, company, location) - never overwrite a previous value, append a new entry
- Every interaction gets a line in that day's note in `Daily/`

## Related

- [[_CLAUDE.md]] - operating manual (bi-temporal facts, propagation rules)
- [[Home]] - vault dashboard
- `Bases/People.base` - people notes with staleness view

Replace or delete this seed once real person notes exist here.
