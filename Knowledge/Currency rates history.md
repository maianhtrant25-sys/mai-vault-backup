---
date: 2026-10-30
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
| 2026-10-30 | 80.6761 | 80.88 | 80.89 | 82.30 | 25,600 |
| 2026-10-29 | 80.8664 | 81.19 | 80.48 | 82.01 | 25,640 |
| 2026-10-28 | 80.5307 | 80.91 | 80.33 | 82.32 | 25,640 |
| 2026-10-27 | 80.4909 | 80.95 | 80.37 | 82.41 | 25,640 |
| 2026-10-26 | 80.5381 | 80.75 | 80.58 | 82.03 | 25,670 |
| 2026-10-25 | 80.5381 | 80.81 | 81.20 | 82.26 | 25,640 |
| 2026-10-24 | 80.5381 | 80.81 | 80.89 | 82.01 | 25,640 |
| 2026-10-23 | 81.1255 | 80.80 | 80.79 | 82.22 | 25,640 |
| 2026-10-22 | 81.9739 | 81.36 | 81.45 | 83.51 | 25,650 |
| 2026-10-21 | 82.8879 | 82.43 | 82.27 | 84.10 | 25,690 |
| 2026-10-20 | 82.8504 | 82.95 | 82.70 | 84.21 | 25,680 |
| 2026-10-19 | 83.6177 | 83.26 | 83.16 | 84.61 | 25,720 |
| 2026-10-18 | 83.6177 | 83.73 | 84.50 | 85.01 | 25,700 |
| 2026-10-17 | 83.6177 | 83.73 | 84.50 | 84.91 | 25,700 |

## Moscow bank panel (latest snapshot)

Cash USD quotes in Moscow for the banks chosen on 2026-10-17. `Buy USD` is the cheapest office
price for getting a dollar, `Sell USD` the best office price for selling one; the per-bank
office detail lives in `/opt/data/cache/currency-rates/banks-<date>.json`.

| Bank | Buy USD | Sell USD | Exchange points |
|---|---|---|---|
| Альфа-Банк | 82.90 | 80.50 | 50 |
| Газпромбанк | 80.89 | 81.81 | n/a |
| ПСБ | 83.51 | 77.84 | 25 |
| Ак Барс Банк | 82.00 | 81.50 | 3 |
| Экспобанк | 83.10 | 81.90 | 4 |
| КАМКОМБАНК | 81.59 | 82.30 | 35 |
