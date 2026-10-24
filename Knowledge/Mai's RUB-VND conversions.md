---
date: 2026-10-24
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
first. She receives RUB and turns it into VND through USD, and sometimes back the other way.
Everything on this page is quoted in **her own unit: rubles per 26,000 VND**, the way she says
it ("85,8 / 26000"). The script still stores the canonical VND per 1 RUB in
`/opt/data/cache/currency-rates/my-rates.json` - a single value below 1 that she sends is read
as RUB per 1 VND and inverted, and two legs work as `--set-rate --usd-rub 84.5 --usd-vnd 25700`
- but this table never shows that unit, because it confuses her. Rows are written by
`/opt/data/scripts/currency_rates.py --set-rate ...`.

`Market` is what the same day's market offered for the SAME direction she converted in: on a
RUB->VND day the cheapest Moscow bank price for buying a dollar combined with the Vietcombank
transfer rate, on a VND->RUB day the mirror route (Vietcombank's sell price for a dollar
combined with the best price a panel bank pays for one). When a day has no bank or Vietcombank
figure (days before the bank panel existed, or a source outage), the fallback is that date's
CBR official cross, and a day with no data at all shows `n/a` instead of borrowing another
day's number.

`Result` is spelled out in words: the difference in rubles per 26,000 VND and whether she paid
less or got more than the market. A higher rate is better when she sells VND and a lower rate is
better when she buys it, and the words say which of the two happened, so there is no sign for
her to work out.

`Profit` belongs to a VND->RUB line: what that deal actually earned, in rubles - the amount times
`cost basis / selling rate - 1`, where the cost basis is the rate of her latest RUB->VND purchase
at or before the deal. It is exact while she works one position at a time and is not a FIFO
match, so overlapping positions would need more bookkeeping. `Total profit` sums the column.

| Date | Amount (₽ worth) | What she did | Your rate (₽ / 26,000 VND) | Market (₽ / 26,000 VND) | Result | Profit (₽) |
|---|---|---|---|---|---|---|
| 2026-10-17 | 34,000 | sent VND, got RUB | 85.80 | 84.65 | ✅ got 1.15 ₽ more than the market (1.36%) | **936.53** |
| 2026-10-16 | 1,124,038 (350,000,000 VND) | sent RUB, got VND | 83.50 | 84.93 | ✅ paid 1.43 ₽ less than the market (1.71%) | — |

**Total profit: 936.53 ₽**
