---
date: 2026-10-15
type: note
tags:
  - template
  - seed
ai-first: true
---

## For future agent

Seed note for `Templates/` in `mai-vault`, written 2026-10-15 so this folder replicates through LiveSync to Mai's laptop and iPhone (LiveSync copies files, not empty directories). It holds no template yet. Templates for daily notes, dev logs, meetings and reviews belong here and are read by the `/obsidian-*` commands before they create a note of that type.

## Purpose

- One file per note type: `Daily Note.md`, `Dev Log.md`, `Meeting.md`, `Weekly Review.md`
- Templates are **never modified** during normal vault operations - they are filled *into* new notes, not edited
- When a command finds a matching template, it copies its structure; unfilled Templater syntax (`<% ... %>`) must not survive into a real note

## Related

- [[_CLAUDE.md]] - operating manual (Do Not Touch: `Templates/`)
- [[Home]] - vault dashboard
- [[Templates-index]] - this seed

Replace this seed with real templates, or delete it once they exist.
