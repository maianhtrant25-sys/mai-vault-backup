---

kanban-plugin: board

---

## 📥 Backlog

- [ ] 🟢 **Evaluate Hevy Pro API for lift-level tracking** · @TBD
	Public API for Hevy Pro users; would give per-set progression and estimated 1RM trends per exercise. Only if Mai wants lift-level detail. See [[Projects/Health and training data pipeline]].
- [ ] 🟢 **Tailscale plus HAE MCP for live health queries** · @TBD
	Health Auto Export's built-in iPhone MCP server is documented LAN-only; a VPN between phone and host would allow live queries instead of daily dumps. Untested from the host. See [[Projects/Health and training data pipeline]].

## 📋 This Week

- [ ] 🟡 **Choose the health data path and vault home** · @TBD
	Mai and Konstantin pick between cloud-drive pull, our own ingest endpoint, or a Shortcut writing into the vault; also whether health data gets a new `Health/` folder or `Daily/` frontmatter. Blocks the pipeline. See [[Projects/Health and training data pipeline]].
- [ ] 🟡 **Set up Health Auto Export on Mai's iPhone** · @TBD
	Premium tier plus two JSON automations (daily metrics, workouts); destination follows the path decision. See [[Set up Health Auto Export on Mai's iPhone]].
- [ ] 🟢 **Build the health data ingest** · @TBD
	Fetch, parse, write the day's note, expose trends through a Bases view; the weekly review cron into `Reviews/` is part of it. See [[Build the health data ingest]].
- [ ] 🟡 **Source the SBV central rate for USD/VND** · @TBD
	The State Bank of Vietnam portal is a JavaScript app and returns an application error to our IPs; the daily digest ships the CBR cross plus Vietcombank instead. Options: a rate API with SBV coverage, a Vietnamese news mirror, or proxying the SBV page. See [[Projects/Currency rates]].

## 🔨 In Progress

## ⏳ Waiting On

## ✅ Done

- [x] 🟡 **Create the FatSecret developer app** · @2026-10-18
	Registered on platform.fatsecret.com, keys verified live, Mai authorized the app, and a per-ingredient diary entry was created, read back and deleted. See [[Create the FatSecret developer app]].
- [x] 🟡 **Confirm the format of Mai's daily rate** · @2026-10-17
	Resolved: she quotes a pair as "<RUB> / 26,000 VND" together with a direction, e.g. "85.8 / 26000" for VND→RUB. The tracker reads every form, and each day is now compared against the market route for the direction she actually used. No digest nudge needed. See [[Projects/Currency rates]].
