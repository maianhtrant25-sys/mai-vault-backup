---
date: 2026-11-27
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
| 2026-11-27 | 82.1265 | n/a | 82.60 | 82.50 | 25,650 |
| 2026-11-26 | 82.3130 | n/a | 81.69 | 82.60 | 25,660 |
| 2026-11-25 | 82.1664 | n/a | 81.34 | 83.65 | 25,640 |
| 2026-11-24 | 82.1488 | n/a | 82.60 | 82.80 | 25,610 |
| 2026-11-23 | 82.1911 | 82.41 | 81.19 | 82.80 | 25,610 |
| 2026-11-22 | 82.1911 | 81.69 | 82.75 | 83.20 | 25,600 |
| 2026-11-21 | 82.1911 | 81.69 | 81.57 | 83.20 | 25,600 |
| 2026-11-20 | 81.9290 | 82.55 | 82.80 | 83.00 | 25,600 |
| 2026-11-19 | 82.2281 | 82.22 | 81.68 | 82.90 | 25,560 |
| 2026-11-18 | 82.4529 | 82.47 | 81.39 | 82.90 | 25,520 |
| 2026-11-17 | 82.5143 | 82.87 | 81.79 | 83.20 | 25,550 |
| 2026-11-16 | 82.1516 | 82.84 | 81.92 | 83.10 | 25,570 |
| 2026-11-15 | 82.1516 | 82.41 | 82.18 | 83.20 | 25,530 |
| 2026-11-14 | 82.1516 | 82.41 | 82.34 | 83.71 | 25,530 |
| 2026-11-13 | 82.9803 | 82.37 | 82.99 | 83.00 | 25,530 |
| 2026-11-12 | 82.6617 | 83.12 | 83.00 | 83.60 | 25,490 |
| 2026-11-11 | 82.5486 | 83.16 | 83.00 | 83.70 | 25,460 |
| 2026-11-10 | 82.7536 | 83.10 | 83.46 | 83.50 | 25,410 |
| 2026-11-09 | 82.1386 | 82.63 | 81.74 | 83.20 | 25,320 |
| 2026-11-08 | 82.1386 | 82.18 | 82.30 | 83.51 | 25,400 |
| 2026-11-07 | 82.1386 | 82.18 | 81.89 | 83.34 | 25,400 |
| 2026-11-06 | 81.7947 | 82.59 | 81.49 | 83.31 | 25,400 |
| 2026-11-05 | 81.6699 | 82.22 | 81.24 | 83.00 | 25,460 |
| 2026-11-04 | 81.6699 | 82.07 | 81.81 | 82.70 | 25,550 |
| 2026-11-03 | 80.9734 | 81.89 | 80.92 | 82.41 | 25,560 |
| 2026-11-02 | 80.5573 | 81.48 | 80.80 | 82.31 | 25,600 |
| 2026-11-01 | 80.5573 | 81.00 | 81.45 | 82.46 | 25,610 |
| 2026-10-31 | 80.5573 | 81.00 | 81.05 | 82.25 | 25,610 |
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
| Альфа-Банк | 83.90 | 81.80 | 51 |
| Газпромбанк | 83.10 | 81.50 | 29 |
| ПСБ | 83.17 | 81.37 | 29 |
| Ак Барс Банк | 82.60 | 82.00 | 3 |
| Экспобанк | 84.20 | 82.50 | 4 |
| КАМКОМБАНК | 83.25 | 81.70 | 36 |
