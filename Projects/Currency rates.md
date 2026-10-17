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

Daily currency tracking for Mai, who receives RUB and converts it into VND through USD (and sometimes the other way round). One scheduled job posts a digest at 12:30 MSK into the Telegram topic "💱 Currency rates" and writes two vault series: the market side (CBR official, MOEX, a fixed panel of Moscow bank cash quotes, Vietcombank) in [[Knowledge/Currency rates history]], and Mai's own conversion rate in [[Knowledge/Mai's RUB-VND conversions]]. Extended 2026-10-17 with the fixed Moscow bank panel and her own rate; the State Bank of Vietnam central rate is still unsourced (see Open items).

## Delivery

- Job: `currency-rates-daily` (id `8f063bb739bd`) - every day at 12:30 MSK into the Telegram topic 💱 Currency rates (thread 186 of the group "Em trợ lý"), replies enabled.
- Step order in the job: (1) wake the browser, (2) `/opt/data/scripts/collect_bank_rates.py` for the Moscow bank panel, (3) `python3 /opt/data/scripts/currency_rates.py` for the deterministic digest and both vault writes, (4) post the digest.
- The browser step cannot be skipped: Banki.ru is a JavaScript app and only a real Chrome renders it. A cold browser makes every bank come back `n/a`, so the job wakes it first.
- Timing rationale: the Bank of Russia publishes around 11:30 MSK (effective the next day); the SBV publishes around 08:00 ICT = 04:00 MSK.
- Weekends: MOEX has no session, so the digest's MOEX row shows the last session's close and says so in a footnote; the CBR does publish a rate for Saturday that then carries into Monday. The MOEX board reports no `TRADEDATE` - the session date comes from `SYSTIME`.

## Moscow bank panel (chosen 2026-10-17)

Cash USD quotes in Moscow, one page per bank on Banki.ru; `buy USD` is the cheapest office price for getting a dollar, `sell USD` the best office price for selling one to that bank.

| Bank | Slug | Points (2026-10-17) |
|---|---|---|
| Альфа-Банк | `alfabank` | 50 |
| Газпромбанк | `gazprombank` | 32 |
| ПСБ | `promsvyazbank` | 25 |
| Ак Барс Банк | `akbars` | 3 |
| Экспобанк | `expobank` | 4 |
| КАМКОМБАНК | `kamkombank` | 35 |

Why these six: they are Moscow banks that actually publish retail USD cash quotes with exchange points, and the set spans the real spread - from Ак Барс and КАМКОМБАНК (tight, near-market) to Газпромбанк and ПСБ (wide). Panel definition: `/opt/data/cache/currency-rates/bank-panel.json`.

The aggregator's own Moscow list shows only a rate-ranked top 10 that changes membership daily, which is useless as a time series - hence one page per bank instead. Its "more than 22 banks" figure covers banks whose own pages carry no quote.

**Not trackable.** Сбербанк, ВТБ, Т-Банк, Райффайзенбанк, Совкомбанк and Уралсиб publish no USD cash quote in the aggregator (their pages answer "Нет информации об актуальном курсе в этом банке"), and their own sites are unreachable from the agent host (certificate/privacy error), so their in-app rates cannot be collected here at all. If a rate from one of them matters, Mai has to report it herself.

## Sources (all tested 2026-10-17)

| Value | Source | Status |
|---|---|---|
| USD/RUB central bank | CBR official XML, `cbr.ru/scripts/XML_daily.asp` | works |
| USD/RUB market | MOEX ISS, `USD000UTSTOM` (USDRUB_TOM, board CETS) | works, live quotes |
| USD/RUB bank quotes | `banki.ru/products/currency/bank/<slug>/usd/moskva/` | works, browser only; a plain HTTP fetch returns a bot page |
| USD/VND bank | Vietcombank XML (buy / transfer / sell) | works |
| USD/RUB and USD/VND market mid | ExchangeRate-API v4 (free, no key) | works |
| USD/VND central bank | SBV central rate, `sbv.gov.vn` | **not sourced** - the portal is a JavaScript app; the legacy endpoint 404s and the current page returns an application error to our browser |
| Cross-check | CBR quotes VND directly, so a central-bank-derived cross is available | works |

## Mai's own rate

- Canonical unit: **VND per 1 RUB**. Her route is RUB → USD → VND, so the effective rate is `VND per USD / RUB per USD`.
- She sends it in chat and it is recorded with `python3 /opt/data/scripts/currency_rates.py --set-rate <value>`; two legs also work (`--set-rate --usd-rub 84.5 --usd-vnd 25700`), and a single value below 1 is read as RUB per 1 VND and inverted. Optional `--amount`, `--dir r2v|v2r`, `--note`, `--date`.
- Raw entries (legs, amount, direction, note) live outside the vault in `/opt/data/cache/currency-rates/my-rates.json`; the readable row goes to [[Knowledge/Mai's RUB-VND conversions]].
- Market comparison in that note: today's cheapest Moscow bank price for buying a dollar combined with the Vietcombank transfer rate; `Diff = Mine / Market - 1`, so a positive number means she did better than the market.

## History and files

- [[Knowledge/Currency rates history]] - market series (CBR, MOEX, banks buy/sell, Vietcombank) plus today's bank panel; newest row first.
- [[Knowledge/Mai's RUB-VND conversions]] - her rate against the market, one row per day she converts.
- `/opt/data/cache/currency-rates/history.json` - full market series, 400 days, includes the fields the table does not show.
- `/opt/data/cache/currency-rates/banks-YYYY-MM-DD.json` - per-bank and per-office quotes for that day; a failed run keeps the earlier quotes and flags itself instead of writing `n/a` over good data.

## Open items

- ⚠️ Confirm the amount Mai converts: her 2026-10-17 rate is recorded but the volume is not - her stated 938 RUB profit implies about 10.6M VND, roughly 34,050 RUB of the 35,000 RUB position opened on 16 October. Card on [[Main]].
- ⚠️ Source the SBV central rate (a news mirror or a small exchange-rate API would do), or decide to publish the CBR cross plus Vietcombank instead. Card on [[Main]].

## Key Decisions

**2026-10-17 (first pass, Telegram)**

- Delivery at 12:30 MSK; digest lives in its own Telegram topic.
- Report both a market rate (MOEX) and Russian bank rates, with the extremes.
- Keep the history; no extra currency pairs, no alert thresholds, no special weekend formatting.

**2026-10-17 (second pass, this thread)**

- Replace the aggregator's shifting top-10 with a fixed six-bank Moscow panel, one page per bank.
- A bank never sells a dollar for less than it pays for one, so the higher figure of a quoted pair is the price of acquiring a dollar and the lower one the selling proceeds; the panel is built on that reading.
- Track Mai's own rate as a separate series in its own note, normalised to VND per 1 RUB.
- Market RUB → VND is computed as the cheapest Moscow bank buy price for USD combined with the Vietcombank transfer rate - the route she actually uses.

**2026-10-17 (third pass, this thread)**

- The market comparison is direction-aware. A VND→RUB day is measured against the mirror route (Vietcombank's sell price for a dollar divided by the best panel bank bid) and `Diff` is inverted, so a positive figure always means Mai did better than the market whichever way the money went. Before the fix her 85.8-per-26,000 deal read as -0.37% against the RUB→VND route; the corrected figure is +1.36%.
- `/opt/data/scripts/rub_vnd_deal.py` added for one-off trade assessments: profit, derived volume and every market route expressed in her own units (RUB per 26,000 VND), with all inputs printed.
