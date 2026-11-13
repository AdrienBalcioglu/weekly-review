# Weekly Review — a skill for Claude

A Claude skill that closes your week on one page: what got done, where the time went, what slipped, and three priorities for next week.

- **Done**: outcomes of the week, not activity
- **Time**: hours in meetings, biggest blocks, longest free stretch
- **Slipped**: overdue tasks and people still waiting for an answer
- **Next week**: three proposed priorities, each with a first step

It works with whatever is connected: calendar, email, chat, tasks. A missing source means a skipped section, never a guess.

## Install

### Claude Code

```bash
git clone https://github.com/AdrienBalcioglu/weekly-review.git ~/.claude/skills/weekly-review
```

### Claude (claude.ai / desktop)

1. Download [`SKILL.md`](SKILL.md).
2. Put it in a folder named `weekly-review` and zip the folder.
3. In Claude, go to **Settings → Capabilities → Skills** and upload the zip.

## Use

```
/weekly-review
```

or just ask: *"Give me my weekly review."*

You can also say: *"Schedule /weekly-review every Friday at 16:30"*.

## Principles

- **Read-only.** It never sends, replies, accepts or archives anything.
- **No invention.** Every claim comes from a source, with its date.
- **Private.** Nothing is stored; everything is read fresh on each run.
- **Short.** One page.

## License

[MIT](LICENSE) © 2026 Adrien Balcioglu
