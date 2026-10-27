---
date: 2026-10-18
updated: 2026-10-26
type: project
status: active
tags:
  - project
  - learning
  - chinese
ai-first: true
related-people: []
related-projects: []
summary: Daily 15-minute learning habit - practical AI four days a week, Mandarin three days a week, with a 10:00 and a bedtime touchpoint.
---

## For future agent

Mai's personal learning track, opened 2026-10-18 at her request. Fifteen minutes a day split between practical AI (four days a week) and beginner Mandarin (three days a week). She confirmed that three goals apply at once: it should be enjoyable and new, immediately usable, and give her useful background knowledge - she did not ask for a project of her own. This note holds the schedule, the daily lesson format and the result of the one-week trial that precedes any longer commitment.

## 🎯 Focus

- **AI first, practically.** She steered this on 2026-10-26 after the first trial: the AI lessons must serve her own work and her own judgement, not theory about models. Four strands, one per AI day: **real work with the assistant** (Monday) - one task she actually has, the sentence to type, what to check; **not being fooled** (Tuesday) - one failure mode, a two-minute test; **building a skill for the assistant** (Thursday) - one procedure of hers turned into a named skill, what she says, how she checks it; **standing up an assistant from nothing** (Saturday) - one step of the setup checklist in her own terms, what she does herself, how she knows it worked.
- **Mandarin second, deliberately slow.** She picked Mandarin over Spanish on 2026-10-18 after the trade-off was stated: characters and tones make the first two months slower, while her Vietnamese ear and the Sino-Vietnamese vocabulary help later.
- **Habit before depth.** Fifteen minutes every day for a week is worth more than a two-hour session that is never repeated.

## Schedule (owner-confirmed 2026-10-18)

- **Morning (10:00 MSK) - 10 minutes:** the day's new lesson. Moved from 12:30 on 2026-10-19 at Mai's request - 12:30 was too late in her day.
- **Bedtime - 5 minutes:** quick recall, three questions answered by voice message or one line of text.
- Total 15 minutes a day, 105 minutes a week - inside the one-to-two hour weekly budget she set.
- Weekly split: four AI days (60 minutes) and three Mandarin days (45 minutes).
- Delivery: Telegram forum topic "📚 Học mỗi ngày" in the group `Em trợ lý`, thread id 456 - full target `telegram:-1003779912075:456` (created 2026-10-18 with `createForumTopic`, verified by a send/delete round trip). Both jobs post there, not in the main thread, so the daily lesson never buries other work.

## Daily lesson format

- One question the day answers, one short explanation, one two-minute action she actually does.
- Examples come from her own data where possible - her FatSecret diary, her rate notes - never an invented case.
- Delivered as a Telegram text message plus a voice version; the weekly summary of what she covered lands in this note, not in `Daily/`.

## Test week 2026-10-19 to 2026-10-25

The point is to find out whether two daily touchpoints fit her day before any longer plan is agreed.

- Success means: she opens at least 5 of the 7 morning lessons and answers at least 4 bedtime recalls.
- Counted from the scheduler reports under `$HERMES_HOME/cron/output/<job_id>/`, not from memory.
- Review on 2026-10-25: keep both slots, keep one, or move the times.
- **Result (2026-10-25):** 7 of 7 morning lessons were delivered (reports `2026-10-19` to `2026-10-25` in `$HERMES_HOME/cron/output/e614cf9fbbd0/`), and 4 of 7 bedtime recalls were answered - on 20, 22, 23 and 25 October - which meets the four-answer bar exactly. Whether she opened the lessons cannot be measured from Telegram, so that half of the test is unproven.
- **Decision (2026-10-25):** Mai kept both slots - 10:00 and 22:00 - unchanged.

## Trial week 2 (2026-10-27 to 2026-11-02)

She asked for a second week with different AI content, then a joint review and a longer plan. Same two touchpoints and the same Mandarin strand; only the AI half changes.

- AI days sit at Monday, Tuesday, Thursday and Saturday, one strand each: **real work with the assistant** (Monday), **not being fooled** (Tuesday), **building a skill for the assistant** (Thursday), **standing up an assistant from nothing** (Saturday). Her own words for what she wants: how to put the assistant to work in her daily job, how to make a skill for it, and what she has to do when the assistant is brand new and nothing has been installed yet, the way Konstantin set this one up.
- Weekdays are unchanged for Mandarin: Wednesday, Friday, Sunday.
- Success means: four AI lessons that touch her own work rather than the internals of a model, and at least four bedtime recalls answered.
- Review on 2026-11-02, together, from the scheduler reports; the outcome decides the longer plan.

## 💡 Decisions

- **2026-10-26 - teaching method agreed:** the AI lessons run as a cycle she set - one exercise, a short plain explanation, then her questions and the agent's answers, with the depth set by her questions. When she asks how the agent did something, the answer is the real process trace (queries, sources accepted and rejected, tool failures, how much was read, what stayed uncertain), not a retelling of the domain.
- **2026-10-26 - four AI strands named by Mai:** later the same evening she made her wish concrete - applying the assistant to her daily work, making a skill for it, and knowing what to do when the assistant is fresh with nothing installed. The lesson prompt of job `e614cf9fbbd0` now assigns one strand per AI day (Monday work, Tuesday not being fooled, Thursday skills, Saturday setup), and tells the lesson never to assume she has root access or a terminal.
- **2026-10-26 - AI content changed for a second trial week:** Mai found the first week's AI lessons too far from what she wants and picked two directions: AI as an employee, and understanding AI so she is not fooled. The lesson prompt of job `e614cf9fbbd0` now alternates those two strands on the four AI days; Mandarin days are untouched. Second trial 2026-10-27 to 2026-11-02, reviewed together before any longer plan.
- **2026-10-24 - lesson format: plain label, no technical detail:** at Konstantin's request the morning message now opens with the single line `**Daily learning**`, and `cron.wrap_response` is off for the whole profile, so no "Cronjob Response" header, job id or "stop/manage" footer reaches the chat. Lesson bodies stay Vietnamese; the label is English.
- **2026-10-19 - lesson slot moved to 10:00 MSK:** Mai found 12:30 too late and proposed "around 10". Job `e614cf9fbbd0` now runs `every day at 10:00`; the bedtime recall stays at 22:00. Today's lesson was fired manually at 10:02 so day one of the trial is not lost.
- **2026-10-18 - voice for daily lessons:** `vi-VN-HoaiMyNeural` (edge-tts, rate -5%). Mai compared it against the male `vi-VN-NamMinhNeural` and a Google `gTTS` render of the same sentence and chose HoaiMy: "not northern, but rounder and clearer". A true northern accent was not available from either free engine.

## Progress

- **2026-10-27** - morning: Confidently wrong arithmetic - asking the assistant for every step and re-doing the steps yourself before a number goes to a customer
- **2026-10-26** - teaching method agreed (exercise → short explanation → her questions); process traces on request.
- **2026-10-26** - four AI strands fixed (work / not fooled / skills / standing it up); lesson prompt rewritten again the same evening.
- **2026-10-26** - second trial agreed (27/10-02/11); AI lessons rewritten to two strands: employee and not-being-fooled.
- **2026-10-26** - morning: Why one question can get two different answers - pinning the reply to a single named source so the model has nothing left to guess
- **2026-10-25** - trial week 19-25 reviewed: 7/7 lessons delivered, 4/7 recalls answered; new message format confirmed in production.
- **2026-10-25** - morning: Mandarin yes/no questions - the particle 吗 (ma) at the end turns a statement into a question without changing word order
- **2026-10-24** - morning: Model writes text, tools do the work - why a confident answer is not proof the note changed
- **2026-10-23** - morning: Mandarin measure words - why a counting word sits between number and noun
- **2026-10-22** - morning: Draft first, then fix - why editing a rough answer beats writing a perfect request
- **2026-10-21** - morning: Mandarin tones - why changing pitch changes the word
- **2026-10-20** - morning: Two layers of agent memory - conversation thread vs vault note
- **2026-10-19** - morning: Anatomy of a good request - task, data, output shape
- **2026-10-19** - lesson slot moved from 12:30 to 10:00 MSK; the day's lesson fired at 10:02.
- **2026-10-18** - project opened, two daily jobs scheduled, one-week trial agreed, voice fixed to `vi-VN-HoaiMyNeural`. No lesson delivered yet.

## ⚠️ Risks and open questions

- Voice output depends on a local TTS engine: `edge-tts` was installed in `/opt/data/tools/tts-venv` on 2026-10-18 and produces `vi-VN-HoaiMyNeural` and `zh-CN-XiaoxiaoNeural` audio, but sending a voice bubble from a cron run is untested.
- Mandarin needs pinyin and audio from day one; no textbook or course has been chosen yet.
- If she misses several days the plan is to slow the pace down, not to stack catch-up lessons.

## 🔗 Links

- [[Main]] - board card in 🔨 In Progress
- [[Logs/2026-10-18]] - opening entry
- [[Logs/2026-10-19]] - lesson slot moved to 10:00
- [[Logs/2026-10-24]] - cron wrapper off, lesson opens with "Daily learning"
- [[Logs/2026-10-25]] - trial week reviewed; new format confirmed in production
- [[Logs/2026-10-26]] - AI lessons retargeted; second trial week agreed
