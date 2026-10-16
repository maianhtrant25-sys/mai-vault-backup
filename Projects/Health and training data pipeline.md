---
date: 2026-10-16
type: project
status: planning
tags:
  - project
  - health
  - automation
ai-first: true
---

## For future agent

Project opened 2026-10-16 (Telegram) to bring Mai's health and training data into this vault automatically and make it useful: Apple Health and Apple Watch SE 3 metrics, gym training, and - once the developer app exists - per-ingredient nutrition from FatSecret. Apple Health has **no public API**, so the pipeline starts with an exporter app on her iPhone; the chosen candidate is Health Auto Export (HAE). Nothing is built yet and the data path is an open decision. Health data is sensitive - see the privacy note at the bottom.

## Goal

One place - this vault - where daily health, training and nutrition numbers land without manual entry, with weekly reviews the agent writes and can reason over later.

## Data available (checked 2026-10-16/17)

- Apple Watch SE 3: steps, active and total energy, heart rate and HRV, resting HR, workouts, sleep stages and sleep score, respiratory rate, wrist-temperature deviation, cardio-fitness estimate, stand hours, distance. **No ECG, no blood oxygen, no hypertension detection** on this model.
- Gym training: per-set detail only with a logging app - Hevy has a public API for Pro users. Apple's native Workout app gives type, duration, HR and calories only.
- Nutrition: FatSecret diary API - prerequisite tracked in [[Create the FatSecret developer app]].

## Candidate data paths (decision open)

| Path | Mechanism | Trade-off |
|---|---|---|
| 1 | HAE Premium exports daily JSON/CSV to iCloud, Google Drive or Dropbox; the agent pulls it on a cron | No inbound ports; data transits a cloud provider |
| 2 | HAE Premium POSTs JSON to a token-protected endpoint on our infra | Data stays in our infra; needs a reverse-proxy route |
| 3 | HAE Premium triggers a Shortcut that writes a file into the vault on the phone; LiveSync carries it to the host | No new infrastructure - reuses the existing sync; raw exports live inside her vault |

HAE pricing (their FAQ, 2026-08-23): automations need **Premium** - $0.99/month, $5.99/year or $24.99 lifetime; the free tier is the dashboard and widgets only.

## Open decisions

- Which path (1, 2 or 3) - and if path 2, whether the operator can expose a protected ingest route.
- Where the data lives: a new `Health/` folder (a folder-map change in [[_CLAUDE.md]], so it needs the owners' approval) or frontmatter inside the existing `Daily/` notes.

## Key Decisions

- None recorded yet.

## Plan (phase 1)

- Health Auto Export automations on Mai's iPhone: daily Health Metrics aggregate plus Workouts, JSON.
- Ingest on the host: fetch, parse, write the day's note, expose trend formulas through a Bases view.
- Weekly review cron: training load against nutrition, steps, sleep score, HRV and resting-HR flags, written into `Reviews/`.
- Charts rendered as images so they appear on the phone without additional Obsidian plugins.

## Later / optional

- Hevy Pro public API for lift-level progression (estimated 1RM trends per exercise).
- Tailscale plus HAE's built-in MCP server on the iPhone for live queries instead of daily dumps.
- Withings scale, or Oura and Whoop APIs, if those devices ever join the picture.

## Privacy note

Health data is sensitive. Path 1 stores it with a cloud provider; path 2 keeps it inside our infrastructure; path 3 puts it into this vault, which syncs (encrypted in transit) to `mai-sync.koska.pro` and to the devices. The owners should pick knowingly.

## Status

- Planning, nothing built. Cards are on [[Main]]; the nutrition dependency is [[Create the FatSecret developer app]].
