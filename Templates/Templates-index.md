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

## Visual formatting blocks (owner, 2026-10-16)

Copy-ready pieces for the templates of this folder, taken from the "Visual Formatting Rules" section of [[_CLAUDE.md]]. They are presentation only: frontmatter, note types, filenames and links stay exactly as OSB defines them. `Daily Note.md` is deliberately excluded at this stage.

Callouts - only for the exceptional, never for ordinary notes:

> [!important] A decision that changed direction.

> [!warning] An active risk or blocker.

> [!question] An open question that needs the owner's answer.

Dated entry - a bold one-line lead plus 2-4 short sub-bullets:

**YYYY-MM-DD** - Short title

- What was done.
- Why it was needed / what caused it.
- 🔗 Result or link.

Heading emoji vocabulary (only where the meaning matches): 🎯 focus · ⏰ deadlines · ⚠️ risks · 💡 decisions · 🔧 fixes · 🔍 findings · ✅ done · 🔗 links.

## Related

- [[_CLAUDE.md]] - operating manual (Do Not Touch: `Templates/`)
- [[Home]] - vault dashboard
- [[Templates-index]] - this seed

Replace this seed with real templates, or delete it once they exist.
