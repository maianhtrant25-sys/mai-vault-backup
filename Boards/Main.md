---

kanban-plugin: board

---

## 📥 Backlog

- [ ] 🟢 **Evaluate Hevy Pro API for lift-level tracking** · @TBD
	Public API for Hevy Pro users; would give per-set progression and estimated 1RM trends per exercise. Only if Mai wants lift-level detail. See [[Projects/Health and training data pipeline]].
- [ ] 🟢 **Tailscale plus HAE MCP for live health queries** · @TBD
	Health Auto Export's built-in iPhone MCP server is documented LAN-only; a VPN between phone and host would allow live queries instead of daily dumps. Untested from the host. See [[Projects/Health and training data pipeline]].

## 📋 This Week

- [ ] 🟡 **Create the FatSecret developer app** · @TBD
	Konstantin (Hermes-side operator) registers the app at platform.fatsecret.com/register and delivers Client ID/Secret + Consumer Key/Secret through the deployment env only. Unblocks per-ingredient diary logging for Mai. See [[Create the FatSecret developer app]].
- [ ] 🟡 **Choose the health data path and vault home** · @TBD
	Mai and Konstantin pick between cloud-drive pull, our own ingest endpoint, or a Shortcut writing into the vault; also whether health data gets a new `Health/` folder or `Daily/` frontmatter. Blocks the pipeline. See [[Projects/Health and training data pipeline]].
- [ ] 🟡 **Set up Health Auto Export on Mai's iPhone** · @TBD
	Premium tier plus two JSON automations (daily metrics, workouts); destination follows the path decision. See [[Set up Health Auto Export on Mai's iPhone]].
- [ ] 🟢 **Build the health data ingest** · @TBD
	Fetch, parse, write the day's note, expose trends through a Bases view; the weekly review cron into `Reviews/` is part of it. See [[Build the health data ingest]].

## 🔨 In Progress

## ⏳ Waiting On

## ✅ Done
