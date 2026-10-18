---
date: 2026-10-18
updated: 2026-10-18
type: project
status: active
tags:
  - project
  - learning
  - chinese
ai-first: true
related-people: []
related-projects: []
summary: Daily 15-minute learning habit - practical AI four days a week, Mandarin three days a week, with a noon and a bedtime touchpoint.
---

## For future agent

Mai's personal learning track, opened 2026-10-18 at her request. Fifteen minutes a day split between practical AI (four days a week) and beginner Mandarin (three days a week). She confirmed that three goals apply at once: it should be enjoyable and new, immediately usable, and give her useful background knowledge - she did not ask for a project of her own. This note holds the schedule, the daily lesson format and the result of the one-week trial that precedes any longer commitment.

## 🎯 Focus

- **AI first, practically.** The first month is hands-on use of the agent in her daily life, not theory about models.
- **Mandarin second, deliberately slow.** She picked Mandarin over Spanish on 2026-10-18 after the trade-off was stated: characters and tones make the first two months slower, while her Vietnamese ear and the Sino-Vietnamese vocabulary help later.
- **Habit before depth.** Fifteen minutes every day for a week is worth more than a two-hour session that is never repeated.

## Schedule (owner-confirmed 2026-10-18)

- **Noon - 10 minutes:** the day's new lesson.
- **Bedtime - 5 minutes:** quick recall, three questions answered by voice message or one line of text.
- Total 15 minutes a day, 105 minutes a week - inside the one-to-two hour weekly budget she set.
- Weekly split: four AI days (60 minutes) and three Mandarin days (45 minutes).

## Daily lesson format

- One question the day answers, one short explanation, one two-minute action she actually does.
- Examples come from her own data where possible - her FatSecret diary, her rate notes - never an invented case.
- Delivered as a Telegram text message plus a voice version; the weekly summary of what she covered lands in this note, not in `Daily/`.

## Test week 2026-10-19 to 2026-10-25

The point is to find out whether two daily touchpoints fit her day before any longer plan is agreed.

- Success means: she opens at least 5 of the 7 noon lessons and answers at least 4 bedtime recalls.
- Counted from the scheduler reports under `$HERMES_HOME/cron/output/<job_id>/`, not from memory.
- Review on 2026-10-25: keep both slots, keep one, or move the times.

## Progress

- **2026-10-18** - project opened, two daily jobs scheduled, one-week trial agreed. No lesson delivered yet.

## ⚠️ Risks and open questions

- Voice output depends on a local TTS engine: `edge-tts` was installed in `/opt/data/tools/tts-venv` on 2026-10-18 and produces `vi-VN-HoaiMyNeural` and `zh-CN-XiaoxiaoNeural` audio, but sending a voice bubble from a cron run is untested.
- Mandarin needs pinyin and audio from day one; no textbook or course has been chosen yet.
- If she misses several days the plan is to slow the pace down, not to stack catch-up lessons.

## 🔗 Links

- [[Main]] - board card in 🔨 In Progress
- [[Logs/2026-10-18]] - opening entry
