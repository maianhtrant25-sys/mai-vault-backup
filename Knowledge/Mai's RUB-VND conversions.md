---
date: 2026-10-17
type: note
tags:
  - finance
  - rates
  - conversions
ai-first: true
summary: Mai's own RUB to VND conversion rate per day, next to what the market offered that day.
---

## For future agent

Mai's own conversion rate for [[Projects/Currency rates]], one row per day she converts, newest
first. She receives RUB and turns it into VND through USD (and sometimes the other way round),
so every rate here is normalised to one unit: **VND per 1 RUB**. A single number below 1 that
she sends is read as RUB per 1 VND and inverted before it is stored; if she sends both legs,
the effective rate is `VND per USD / RUB per USD`. Rows are written by
`/opt/data/scripts/currency_rates.py --set-rate ...` (call it when she states a rate in chat)
and the raw legs, amount, direction and note stay outside the vault in
`/opt/data/cache/currency-rates/my-rates.json`. The market side of the comparison comes from
[[Knowledge/Currency rates history]].

`Market` is what the same day's market offered for the SAME direction: on a RUB->VND day
the cheapest Moscow bank price for buying a dollar combined with the Vietcombank transfer
rate, on a VND->RUB day the mirror route (Vietcombank's sell price for a dollar combined
with the best price a panel bank pays for one). When a day has no bank or Vietcombank
figure (days before the bank panel existed, or a source outage), the fallback is that
date's CBR official cross (VND per USD / RUB per USD), and a day with no data at all shows
`n/a` instead of borrowing another day's number.
`Diff` is the signed advantage of Mai's rate over that day's market: `Mine / Market - 1` on
a RUB->VND day and `Market / Mine - 1` on a VND->RUB day, so **positive always means she did
better than the market**, whichever way the money went. `n/a` marks a day where the market
side had no source.

| Date | Dir | Amount | Mine (VND per RUB) | Market (VND per RUB) | Diff |
|---|---|---|---|---|---|
| 2026-10-17 | VND->RUB | n/a | 303.0303 | 307.1487 | +1.36% |
| 2026-10-16 | RUB->VND | 35,000 | 311.3772 | 306.1362 | +1.71% |
