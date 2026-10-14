# Claude Operating Manual - Mai's Vault

> Read this file before doing anything in this vault.
> This is the single source of truth for how Claude operates here.

---

## Section 0 - AI-First Vault Rule (read first, applies to every note)

This vault is designed for **future agent** to read and reason over, not for human review. The owner rarely reads notes directly - they call Claude to retrieve, synthesize, and connect dots across accumulated knowledge.

**Every note Claude writes to this vault must follow these rules:**

1. **Self-contained context** - Each note must explain itself. Future-Claude may pull this single note via search with no surrounding context. Don't rely on backlinks alone for meaning.
2. **"For future agent" preamble** - Every note begins with a 2-3 sentence summary in plain English so Claude can decide relevance in 10 seconds before parsing the structured data.
3. **Rich, consistent frontmatter** - Filterable metadata (`type`, `date`, `tags`, `ai-first: true`, plus type-specific fields).
4. **Recency markers per claim** - When stating external facts, attach the date: "X raised $24M (as of 2026-04)" so future agent knows what to verify.
5. **Sources preserved verbatim** - Every external claim has its source URL inline so it can be re-verified.
6. **Cross-links are mandatory** - Every person, project, idea, decision, or concept referenced uses `[[wikilinks]]`.
7. **Confidence levels** - Where applicable, mark claims as `stated | high | medium | speculation`.

This rule applies to all `/obsidian-*` and `/research*` commands, all scheduled agents, and any direct vault writes.

---

## Section 0.5 - Verify Live State Before Acting

Before declaring a bug, drafting a fix, or writing architecture: read the actual code, schema, deployed branch, env, or live data. Speculation from stale context produces drafts that contradict reality.

- Read the schema or types before declaring a bug (real field names live in the code, not in memory)
- Grep the live file before any anchor-based patch
- Fetch live time, dates, and rates (never infer from training data)
- Verify env vars in the running process before blaming code

---

## Vault Identity

- **Owner:** Mai
- **Vault name:** `mai-vault`
- **Primary purpose:** Personal second brain - work notes, projects, knowledge, decisions, and captures for long-term agent retrieval.
- **Last updated:** 2026-10-15
- **Initialized by:** Hermes agent (`/obsidian-init`) on 2026-10-15 - see [[Logs/2026-10-15]]

---

## Sync (`mai-vault` via Obsidian LiveSync)

This vault is a device-synced Obsidian vault (LiveSync / CouchDB).

- **Database name:** `mai-vault`
- **Sync server:** `https://mai-sync.koska.pro`
- **User:** `maiagent`
- **Credentials:** stored on the devices only - the password and passphrase are deliberately **not** written into this vault.
- **Devices:** laptop + iPhone (Obsidian app)
- Note for future agent: LiveSync replicates *files*, so a folder with no note in it does not appear on the devices.

---

## Folder Map

| Folder | Purpose |
|---|---|
| `Daily/` | One note per day. Named `YYYY-MM-DD.md` |
| `Projects/` | Active and archived projects |
| `Tasks/` | Standalone task notes (linked from boards) |
| `Boards/` | Kanban boards |
| `People/` | One note per person |
| `Dev Logs/` | Technical work logs - dated, project-tagged |
| `Knowledge/` | Reference material and permanent notes; ADRs live here as `ADR-YYYY-MM-DD - Title.md` |
| `Ideas/` | Idea and concept notes |
| `Meetings/` | Meeting notes |
| `Reviews/` | Weekly / monthly reviews |
| `Research/` | Research output (Web, Deep, X-pulse, X-reads, YouTube, NotebookLM) |
| `Templates/` | Note templates |
| `Logs/` | Per-day operation log. Root `log.md` is a pointer only |
| `Bases/` | Obsidian Bases views (Projects, People, Tasks, Daily) |
| `.claude/` | Agent config for Claude Code sessions started in this vault |

Vault style: **Obsidian-style** (no `wiki/` folder). Resolve note folders per this table, not by inventing new names.

---

## Key Files

- **Dashboard:** `[[Home]]` - main navigation
- **Catalog:** `index.md` - every page, grouped by folder (read this first when navigating)
- **Operation log:** `Logs/YYYY-MM-DD.md` (root `log.md` explains the format)
- **Bases:** `Bases/Projects.base`, `Bases/People.base`, `Bases/Tasks.base`, `Bases/Daily.base`

---

## Active Context

> Update this section at the start of each major project or focus period.

**Current top priority:** Stand up the Hermes agent deployment for this vault (self-hosted agent host, `mai-vault` sync, and the agent's Obsidian skills) - status as of 2026-10-15: vault skeleton initialized, devices pending initial sync.
**Owner's devices:** laptop + iPhone with the Obsidian app.

---

## Auto-Save Rules

Claude should auto-save the following **without asking**:
- Decisions made in conversation → relevant project note + daily note
- New people mentioned → `People/` (create stub if needed)
- Tasks assigned or committed to → `Boards/` + `Tasks/` note
- Dev work done → `Dev Logs/` + project note + daily note
- Completed tasks → move on kanban to ✅ Done

Claude should **ask before saving**:
- Anything touching finances or personal financial data
- Private / journal material
- Anything that deletes or archives an existing note

---

## Naming Conventions

- Daily notes: `YYYY-MM-DD.md`
- Dev logs: `YYYY-MM-DD - Description.md`
- Tasks: descriptive title, no date prefix
- People: full name (e.g. `Jane Smith.md`)
- ADRs: `ADR-YYYY-MM-DD - Title.md`
- Archive prefix: `_archived_`
- ASCII hyphens only in filenames - never an em or en dash (link matching is literal)

---

## Frontmatter Requirements

Every note must have at minimum:

```yaml
---
type: [note-type]
date: YYYY-MM-DD
tags:
  - [note-type]
ai-first: true
---
```

Note types used here: `daily` | `project` | `task` | `person` | `devlog` | `log` | `idea` | `decision` | `adr` | `meeting` | `review` | `source` | `note`

---

## Kanban Convention

Columns in boards: `📥 Backlog` · `📋 This Week` · `🔨 In Progress` · `⏳ Waiting On` · `✅ Done`

Priority: 🔴 critical · 🟡 important · 🟢 low

Item format:

```
- [ ] 🔴 **Title** · @{YYYY-MM-DD}
	Description. [[Related Project]] [[Person]]
```

Completed:

```
- [x] ~~🔴 **Title**~~ ✅ Date
```

---

## Propagation Rules

| Event | Also update |
|---|---|
| New project | Board (Backlog) + today's daily note |
| Task done | Board (Done, strikethrough) + project note + daily note |
| Dev session | `Dev Logs/` + project note (Recent Activity) + daily note |
| Person interaction | Daily note + their `People/` note |
| Decision made | Project note (Key Decisions) + daily note |
| Research finding | `Research/` + related concept note + daily note |

---

## People to Know

| Person | Role | Notes |
|---|---|---|
| Mai | Vault owner | Sole owner of `mai-vault` |
| Konstantin | Hermes-side operator | Runs the agent host and the device-setup steps (source: Telegram thread, 2026-10-14/15) |

---

## Projects Currently Active

- None recorded yet. Add project notes to `Projects/` and link them here.

---

## Do Not Touch

- `Templates/` - never modify templates during normal vault operations
- `.obsidian/` - app configuration, owned by the Obsidian apps
- `.claude/` - agent config (single import line into this manual)
- Anything containing sync credentials - credentials live on the devices, never in vault notes

---

*This file was generated by the obsidian-second-brain skill (`/obsidian-init`) on 2026-10-15.*
*Regenerate with: "Claude, update my _CLAUDE.md"*
