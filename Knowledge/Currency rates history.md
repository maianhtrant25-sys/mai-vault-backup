---
date: 2026-10-20
type: note
tags:
  - finance
  - rates
  - history
ai-first: true
summary: Daily USD/RUB and USD/VND rates from the central banks, MOEX and the Moscow bank panel, newest row first.
---

## For future agent

Rolling history for [[Projects/Currency rates]]: what one USD costs in RUB and what one USD
costs in VND, so the two sides of Mai's RUB -> USD -> VND route can be compared day by day.
One row per calendar day, newest first, maintained by `/opt/data/scripts/currency_rates.py`;
the full JSON series (including the fields this table does not show, e.g. the market mid and
the CBR cross) sits outside the vault at `/opt/data/cache/currency-rates/history.json`.

**Columns of the market table.** `CBR` = Bank of Russia official rate for USD. `MOEX` = last
USD/RUB TOM trade on the Moscow Exchange. `Banks buy USD` = cheapest price at which a dollar
can be bought in cash at the tracked Moscow banks (RUB per USD; what Mai would pay). `Banks
sell USD` = best price at which a dollar can be sold to those banks. `VCB transfer` = Vietcombank
transfer rate in VND per USD. A value of `n/a` means the source did not answer that day - it is
never estimated.

## Market rates

| Date | CBR USD/RUB | MOEX USD/RUB | Banks buy USD | Banks sell USD | VCB transfer |
|---|---|---|---|---|---|
| 2026-10-20 | 82.8504 | 83.02 | 82.70 | 84.21 | 25,680 |
| 2026-10-19 | 83.6177 | 83.26 | 83.16 | 84.61 | 25,720 |
| 2026-10-18 | 83.6177 | 83.73 | 84.50 | 85.01 | 25,700 |
| 2026-10-17 | 83.6177 | 83.73 | 84.50 | 84.91 | 25,700 |

## Moscow bank panel (latest snapshot)

Cash USD quotes in Moscow for the banks chosen on 2026-10-17. `Buy USD` is the cheapest office
price for getting a dollar, `Sell USD` the best office price for selling one; the per-bank
office detail lives in `/opt/data/cache/currency-rates/banks-<date>.json`.

| Bank | Buy USD | Sell USD | Exchange points |
|---|---|---|---|
| Альфа-Банк | 85.30 | 82.50 | 50 |
| Газпромбанк | 82.70 | 83.61 | n/a |
| ПСБ | 85.74 | 79.98 | 25 |
| Ак Барс Банк | 84.10 | 83.60 | 3 |
| Экспобанк | 84.90 | 83.90 | 4 |
| КАМКОМБАНК | 82.99 | 84.21 | 35 |
