---
date: 2026-11-03
type: note
tags:
  - hermes
  - course
  - learning
ai-first: true
summary: Map of Tonbi's 10-module Hermes Agent Masterclass, the order Mai follows it in, and a plain-language glossary of the technical words she meets in the videos.
---

## For future agent

On 2026-11-03 Mai sent Module 3 of the "Hermes Agent Masterclass" and said the videos are full of technical words she does not understand, and she wants to be taught from this material as someone who knows nothing yet. This note is the reference behind the daily AI lessons: which modules exist, the order she follows, and a one-line explanation of every term she will meet. The lessons themselves live in [[Projects/Daily learning - AI and Chinese]] (Progress) and in the chat; this note only holds the map and the vocabulary.

## The course

- "Hermes Agent Masterclass" by Tonbi's AI Garage - 10 modules, about 5h14m, from a fresh install to a hardened multi-agent setup. The index page with all ten modules is `https://hermesatlas.com/masterclass`.
- Module 3, the one she sent: `https://www.youtube.com/watch?v=ZKZLko9kLm4` - memory, plugins, Honcho, Obsidian.

## Module list

| # | Topic | What it covers |
|---|---|---|
| 1 | Installation, setup, basic commands | install the agent, first chat, first commands |
| 2 | Gateway | run it always-on and reach it from Telegram or Discord |
| 3 | Memory, plugins, Honcho, Obsidian | the two memory files, how memory loads and is written, session search, memory plugins, the vault |
| 4 | Skills | what a skill is, how the agent picks one, how new ones are written |
| 5 | Providers, models, local inference | which model does what, cost, fallback, running a model locally |
| 6 | Tools and MCP | what a tool is, tool sets, MCP servers as adapters |
| 7 | Cron and automation | scheduled jobs, monitors, delivery targets |
| 8 | Subagents | delegating work to parallel agents |
| 9 | Profiles | separate agents for separate jobs, each with its own memory |
| 10 | Security | who may talk to the agent, what it may touch, approvals |

## Order for Mai

Not the course's own order. Start with the modules about things she already uses every day, and leave installation for later, when she wants to do it with her own hands on a machine.

1. **Module 3 - memory** (she sent it): what the agent remembers, and why it sometimes forgets.
2. **Module 4 - skills**: turning one of her own procedures into a skill.
3. **Module 7 - cron**: the 10:00 lesson and 22:00 recall as a concrete example.
4. **Modules 1 and 2 - install and gateway**: what she would have to do from an empty machine.
5. **Module 6 - tools and MCP**, then **9 - profiles**, then **10 - security**.
6. Modules 5 and 8 last: model choice and subagents are the least useful until the rest is solid.

## Glossary

One line each, written for someone starting from zero.

- **Token** - the unit the model reads and writes in; roughly part of a word. Cost and limits are counted in tokens, not words.
- **Context window** - everything the model can see at once in one turn: the system prompt, the conversation, tool results. It is finite.
- **System prompt** - the instruction block the agent is given before the conversation starts: who it is, its rules, its memory. The user does not see it.
- **Prompt caching** - reusing the unchanged beginning of the prompt instead of reprocessing it, which makes long sessions affordable. Changing the beginning throws the cache away.
- **Markdown** - plain text with light formatting (`#`, `-`, `**bold**`). The memory files and the vault are markdown.
- **memory.md** - the agent's own notes: environment, projects, decisions, lessons.
- **user.md** - the agent's model of the person it works for: role, preferences, style.
- **Session** - one continuous conversation. Memory files load at the start of each session.
- **Frozen snapshot** - memory is read once at session start; a write lands on disk immediately but only shows up in the next session.
- **FTS5 / full-text search** - searching old conversations by exact words, not by meaning. Built into SQLite.
- **SQLite / state.db** - the single database file where every past conversation is stored and searched.
- **Embedding** - turning text into a list of numbers so similar meanings sit close together.
- **Vector store** - the place those numbers are kept, used for search by meaning.
- **Semantic search** - finding things by meaning rather than by exact words.
- **Plugin** - an add-on that extends the agent, often swapping one back end for another (a memory provider, a browser engine).
- **Skill** - a written procedure the agent loads when the task matches; the agent's "how to do this" memory.
- **Vault** - a folder of markdown notes (Obsidian) that both the person and the agent can read and search.
- **Wikilink** - a link written as `[[Note name]]`, which the vault turns into a connection between notes.
- **Tool** - a function the agent can call (read a file, run a command, search the web). The model decides, the tool acts.
- **MCP** - a standard way for the agent to plug into outside tools and data without a custom integration each time.
- **Cron job** - a task the system runs on a schedule, in a fresh session, without a person present.
- **Subagent / delegation** - handing a piece of work to another agent process that reports back.
- **Profile** - a separate agent instance with its own memory, skills and settings.
- **Gateway** - the always-on process that connects the agent to Telegram, Discord and the rest.
- **API key** - the secret that proves to a model provider that the request is paid for. Never written into a note.
- **Prompt injection** - instructions hidden inside a web page, email or document, written to make the agent obey the document instead of its owner.

## Links

- [[Projects/Daily learning - AI and Chinese]] - the learning track these lessons belong to
- [[index]]
