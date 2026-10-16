---
date: 2026-10-16
type: task
status: waiting
priority: 🟡
tags:
  - task
  - health
related-projects:
  - "[[Projects/Health and training data pipeline]]"
ai-first: true
---

## For future agent

Device-side task for Mai on her iPhone, raised 2026-10-16. Installs and configures the Apple Health exporter that feeds [[Projects/Health and training data pipeline]]; it blocks the whole ingest pipeline. A paid tier is required because automations are Premium-only in Health Auto Export. No due date was given. The agent cannot install or configure iOS apps itself.

## Steps

- Install Health Auto Export from the App Store and grant it read access to Apple Health.
- Buy Premium - $24.99 lifetime is cheaper than the $5.99 yearly or $0.99 monthly options.
- Create two automations: **Health Metrics** (daily aggregate) and **Workouts**, export format JSON.
- Point the destination at whichever path the owners choose: a cloud drive, a REST endpoint, or a Shortcut that writes into this vault.
- Confirm the first export exists and that the agent can read it.

## Status

- 🔗 Card in `📋 This Week` on [[Main]] - currently blocked on the path decision in [[Projects/Health and training data pipeline]].
- Owner: Mai (device work).
