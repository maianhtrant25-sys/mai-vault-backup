---
date: 2026-10-16
type: task
status: waiting
priority: 🟡
tags:
  - task
  - fatsecret
related-projects:
  - "[[Projects/Health and training data pipeline]]"
ai-first: true
---

## For future agent

Setup task raised by Konstantin on 2026-10-16 (Telegram thread): register a FatSecret Platform **developer account and app**, so the agent can write per-ingredient food diary entries into Mai's FatSecret account. The whole FatSecret integration is blocked on this task. No due date was given - the card sits in `📋 This Week`. Credentials must never be stored in this vault.

## What is needed

- Register at `https://platform.fatsecret.com/register` - free Basic tier, 5,000 API calls/day, US dataset.
- Collect from the app's page: **Client ID + Client Secret** (OAuth 2.0) and **Consumer Key + Consumer Secret** (OAuth 1.0 - the profile and diary flow is OAuth 1.0 only).
- Hand them over through the deployment environment (`/run/s6/container_environment/` or `/opt/data/.env`) - never in the vault, never in chat.

## Why

Mai logs every meal and wants **per-ingredient** entries. FatSecret's official diary API covers exactly that: `food_entry.create` (food_id + serving_id + number of units + meal + date), `food_entries.get`, copy entries between dates, and saved meals.

Open point, checked against the FatSecret docs on 2026-10-16: their documentation marks some diary methods "Premier Exclusive"; whether diary **writes** are included in the free Basic tier could not be confirmed from public documentation and needs one live test.

## Status

- 🔗 Card in `📋 This Week` on [[Main]] - the vault's first kanban board.
- Next step once the keys exist: OAuth 1.0 three-legged authorization by Mai (she approves once herself; the agent never handles her password), then log one test entry and read it back from the diary.
- Fallback if the tier blocks writes: the agent computes kcal / protein / carbs / fat per ingredient and Mai quick-adds them in the app.
