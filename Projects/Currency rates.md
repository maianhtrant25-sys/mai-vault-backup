---
date: 2026-10-17
type: project
status: active
tags:
  - project
  - finance
  - automation
ai-first: true
---

## For future agent

Project opened 2026-10-17 (Telegram, by Mai): send a daily currency digest with the **central-bank rate and the market rate** for **USD/RUB** and **USD/VND**, plus the best and worst Russian bank rate for USD. It runs every day at 12:30 MSK into its own Telegram topic, "💱 Currency rates", as a scheduled job plus a stdlib-only collector script. The State Bank of Vietnam's own central rate is still unsourced (see Open items).

## Delivery

- Job: `currency-rates-daily` (id `8f063bb739bd`) - every day at 12:30 MSK, delivers into the Telegram topic 💱 Currency rates (thread 186 of the group "Em trợ lý"), replies enabled.
- Step 1, deterministic: `/opt/data/scripts/currency_rates.py` - CBR official, MOEX, market mid, Vietcombank, the CBR cross, and both history writes.
- Step 2, agent: opens `banki.ru/products/currency/usd/` in the browser (the page renders only with JavaScript) and reports the highest and the lowest bank rate.
- Timing rationale: the Bank of Russia publishes around 11:30 MSK (effective the next day); the SBV publishes around 08:00 ICT = 04:00 MSK.

## Sources (all tested 2026-10-17)

| Value | Source | Status |
|---|---|---|
| USD/RUB central bank | CBR official XML, `cbr.ru/scripts/XML_daily.asp` | works |
| USD/RUB market | MOEX ISS, `USD000UTSTOM` (USDRUB_TOM, board CETS) | works, live quotes |
| USD/RUB bank extremes | `banki.ru/products/currency/usd/` | works, browser only (JavaScript app); on that page the first `NN,NN ₽` figure is the CBR rate and the following ones are bank quotes. The page picks a city from the connection's IP - it currently lists **Nizhny Novgorod** offers, so pin the city in the URL if that ever matters |
| USD/VND bank | Vietcombank XML (buy / transfer / sell) | works |
| USD/RUB and USD/VND market mid | ExchangeRate-API v4 (free, no key) | works |
| USD/VND central bank | SBV central rate, `sbv.gov.vn` | **not sourced** - the portal is a JavaScript app; the legacy endpoint 404s and the current page returns an application error to our browser |
| Cross-check | CBR quotes VND directly, so a central-bank-derived cross is available | works |

## History

- Vault: [[Knowledge/Currency rates history]] - rolling table, one row per day, newest first, maintained by the collector script.
- Outside the vault: `/opt/data/cache/currency-rates/history.json` - the full JSON series (capped at 400 entries), used for day-over-day deltas.

## Open items

- Source the SBV central rate (a news mirror or a small exchange-rate API would do), or decide to publish the CBR cross plus Vietcombank instead. Card on [[Main]].

## Key Decisions (Mai, 2026-10-17)

- Delivery stays at 12:30 MSK.
- Show both MOEX and a Russian bank rate, reporting the highest and the lowest bank rate from banki.ru.
- Keep the history - now a vault table plus the JSON series outside.
- No extra currency pairs for now, no alert thresholds, no special weekend formatting.
- The digest lives in its own Telegram topic rather than the main thread.
