# Operation Log - `mai-vault`

This file is a **pointer only**. It carries no entries.

The vault logs every operation (save, ingest, health check, init, merge, structural change) in **one file per day**, append-only, at:

```
Logs/YYYY-MM-DD.md
```

Never delete or rewrite an entry in a per-day file - only append.

## Entry format

Inside `Logs/YYYY-MM-DD.md`, entries are:

```markdown
**HH:MM** - action | description
```

Examples:

```markdown
**00:24** - init | Vault initialized with _CLAUDE.md, index.md, Logs/
**14:07** - ingest | Source Title (article) - 3 created, 2 rewritten, 1 contradiction resolved
**22:00** - nightly | End of day + 2 flagged, 1 synthesized, 4 orphans linked
```

Per-day files carry frontmatter (`type: log`, `date`, `ai-first: true`) and a `## For future agent` preamble, so a future agent can read any single day's file standalone.

## Today

- [[Logs/2026-10-15]]

*(Migrating an older monolithic `log.md` that already holds `## YYYY-MM-DD` sections: run `python scripts/migrate_log.py --vault <vault>` from the obsidian-second-brain skill.)*
