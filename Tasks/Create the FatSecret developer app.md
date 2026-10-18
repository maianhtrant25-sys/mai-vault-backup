---
date: 2026-10-16
type: task
status: in-progress
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

Tier check (2026-10-18): the docs mark Premier-only methods with an asterisk, and `food_entry.create` carries none - so the diary write path should work on the free Basic edition (5,000 calls/day, US dataset, English only). One live test still has to confirm it.

## Progress

**2026-10-18 - registered; keys and authorization still to do**

- ✅ Konstantin registered a developer account on `platform.fatsecret.com` (reported in Telegram, 18 October).
- Next: generate the keys in "Generate / View API Keys" (Consumer Key + Secret for OAuth 1.0, Client ID + Secret for OAuth 2.0) and whitelist the host's public IP **143.20.37.247** under "IP Restrictions" (OAuth 2.0 is refused from unlisted IPs; up to 15 addresses).
- Then the OAuth 1.0 3-legged flow, done by **Mai on her own fatsecret.com account**: `POST https://authentication.fatsecret.com/oauth/request_token` (callback `oob`), `GET .../oauth/authorize?oauth_token=...`, then `GET .../oauth/access_token` with the verifier she is shown. She approves; the agent never sees her password.
- Then one live test: `foods.search` for a food_id, `food_entry.create` (food_id, food_entry_name, serving_id, number_of_units, meal, date as days since 1970-01-01), read back with `food_entries.get`, remove with `food_entry.delete`.
- Credentials travel through the deployment env only (`/opt/data/.env`: `FATSECRET_CONSUMER_KEY`, `FATSECRET_CONSUMER_SECRET`, `FATSECRET_CLIENT_ID`, `FATSECRET_CLIENT_SECRET`, then the access-token pair) - never in this vault, never in chat.

## Status

- 🔗 Card moved to `🔨 In Progress` on [[Main]].
- Fallback if the tier blocks writes: the agent computes kcal / protein / carbs / fat per ingredient and Mai quick-adds them in the app.
