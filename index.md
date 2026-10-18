# Vault Catalog - `mai-vault`

> Every page in this vault, grouped by folder. Read this before searching: it is cheaper than a broad scan.
> Regenerate with `/obsidian-init` (it is always a fresh catalog of current vault state).

*Generated: 2026-10-15 (vault initialization - vault is otherwise empty, see note below).*

## Root

- [[Home]] - navigation hub and vault status
- [[_CLAUDE.md]] - operating manual (AI-first rule, folder map, conventions)
- `index.md` - this catalog
- `log.md` - operation-log format pointer (entries live in `Logs/`)

## Logs

- [[Logs/2026-10-15]] - vault initialized with `_CLAUDE.md`, `index.md`, `Logs/`
- [[Logs/2026-10-16]] - visual formatting rules (A-G) added and applied to three existing notes
- [[Logs/2026-10-17]] - health and training data pipeline created; currency digest extended with the Moscow bank panel and Mai's own rate
- [[Logs/2026-10-18]] - FatSecret task closed: keys verified live, Mai's authorization done, per-ingredient diary write tested and rolled back

## Tasks

- [[Create the FatSecret developer app]] - 🟡 waiting - register the FatSecret developer app so the agent can write diary entries (keys via env only)
- [[Set up Health Auto Export on Mai's iPhone]] - 🟡 waiting - install the Apple Health exporter and its two JSON automations
- [[Build the health data ingest]] - 🟢 waiting - fetch, parse and write daily health notes on the host

## Projects

- [[Projects/Health and training data pipeline]] - planning - health, training and nutrition data into the vault (opened 2026-10-16)
- [[Projects/Currency rates]] - active - daily USD/RUB and USD/VND digest, central bank plus a fixed Moscow bank panel and Mai's own conversion rate (opened 2026-10-17)

## Boards

- [[Main]] - kanban board: 📥 Backlog / 📋 This Week / 🔨 In Progress / ⏳ Waiting On / ✅ Done

## Knowledge

- [[Knowledge/Currency rates history]] - rolling daily table of the central-bank, MOEX and Moscow bank rates for USD/RUB plus USD/VND, and today's bank panel (maintained by the collector script; newest first)
- [[Knowledge/Mai's RUB-VND conversions]] - Mai's own RUB to VND conversion rate per day, next to what the market offered that day
- [[Knowledge/Selftest 2026-10-14]] - disposable self-test artifact written by the Hermes agent during deployment verification; safe to delete

## Bases

- `Bases/Projects.base` - projects by status
- `Bases/Tasks.base` - open/done tasks
- `Bases/People.base` - people notes
- `Bases/Daily.base` - daily notes table + calendar

## Folder seeds (one per folder - keeps the skeleton visible on devices)

LiveSync replicates files, not empty directories, so each folder carries one minimal seed note until real content lands:

- [[Daily-index]] - `Daily/` - one note per day
- [[Projects-index]] - `Projects/` - one note per project
- [[Tasks-index]] - `Tasks/` - standalone task notes
- [[Boards-index]] - `Boards/` - kanban boards
- [[People-index]] - `People/` - one note per person
- [[Dev-logs-index]] - `Dev Logs/` - dated technical work logs
- [[Ideas-index]] - `Ideas/` - idea and concept captures
- [[Meetings-index]] - `Meetings/` - one note per meeting
- [[Reviews-index]] - `Reviews/` - weekly / monthly reviews
- [[Research-index]] - `Research/` - research toolkit output
- [[Templates-index]] - `Templates/` - note templates (never edited in place)

Each seed states its folder's purpose, naming convention and frontmatter, and links back to [[Home]] and [[_CLAUDE.md]]. Delete a seed once real notes exist in its folder.

## Contents status

This vault was empty before initialization on 2026-10-15: no owner notes, no `Daily/` entries, no projects. Folders were seeded at 00:58 MSK the same day so the structure replicates to the devices. As of initialization the vault directory shows no files from the laptop or iPhone yet - regenerate this catalog once device content arrives.
