---
name: weekly-review
description: Build a one-page weekly review from the user's calendar, email and tasks — what got done, where the time went, what slipped, and the three priorities for next week. Use when the user types /weekly-review, asks for a weekly review, a week recap, "how did my week go", or wants this scheduled every Friday.
---

# Weekly review — one page to close the week

Produce a short **HTML page** that answers, at the end of a working week:

1. **What did I get done?**
2. **Where did my time go?**
3. **What slipped or is still waiting on me?**
4. **What are the three things that matter next week?**

The page must be readable in under three minutes. It is a mirror, not a report for a manager: say what the data shows, including the uncomfortable parts.

## Step 0 — Know the user and the week

- **Language**: the language the user writes in. Everything on the page uses it, with the date and time formats of that locale.
- **Week**: the current week, Monday to today, unless the user names another one. Run on a Monday morning, review the previous week.
- **Working hours**: use what the user said or what a `weekly-review.config.md` file states; otherwise assume 9:00 to 18:00, Monday to Friday.
- **Sources**: use whichever of calendar, email, chat and task tools are connected. Never ask the user to connect something mid-run; work with what is there.

If no source at all is connected, do not invent a week. Ask the user to tell you in a few lines what they worked on, and build the review from that.

## Step 1 — What got done

From tasks completed, emails sent, documents shared and meetings held, list the **outcomes** of the week, not the activity.

- Write "Sent the pricing proposal to the client", not "Worked on pricing".
- Group by project or theme when there are more than six items.
- Maximum ten items. If the week produced more, keep the ones with a visible result.
- Only list what a source confirms. A meeting on the calendar proves it was scheduled, not what it decided.

## Step 2 — Where the time went

From the calendar only:

- Total hours in meetings, and the share of working hours that represents.
- The three largest time blocks by topic or project.
- Longest uninterrupted free block of the week.
- One sentence of reading: for example "Meetings took 60% of your week, and no free block was longer than 90 minutes."

Skip all-day events, declined events and blocks marked as focus or personal. If the calendar is not connected, skip this section entirely.

## Step 3 — What slipped

- Tasks that were due this week and are still open.
- Email or chat threads where someone asked the user something and got no answer. Ignore newsletters, notifications and automated senders.
- Meetings that were cancelled or moved without a new date.

Maximum seven items, oldest first. For each, one line: what it is, who is waiting, since when.

## Step 4 — Three priorities for next week

Propose **three**, never more, from: what slipped, what is due next week, and what next week's calendar already commits to. For each, name the first concrete step.

State them as proposals. The user decides; you are giving them a starting point.

## Step 5 — Build the page

A single self-contained HTML file:

- One column, comfortable on a phone, light and dark mode via `prefers-color-scheme`.
- Title with the week's dates, then the four sections in order.
- No external scripts, fonts or images.
- A one-line footer naming the sources used and those that were missing.

Publish it as an artifact when that is available, otherwise save it as `weekly-review-<YYYY-MM-DD>.html`.

## Rules

- **Read-only.** Never send, reply, accept, decline, complete or archive anything.
- **No invention.** A missing source means a skipped section, with one line saying why.
- **No judgement of the person.** Describe the week, not the user.
- **Private.** Do not quote the body of emails or messages; describe what is pending in your own words.
- **Short.** If a section is empty, say so in one line and move on.

## Configuration (optional)

A `weekly-review.config.md` file may set: language, working hours, the first day of the week, projects to group by, senders or calendars to ignore, and extra sections (for example a KPI to check or a habit to track).

## Scheduling

If the user asks for it every week, propose Friday at 16:30 in their timezone and set it up with the scheduling tool available. In a scheduled run there is no one to ask: make the documented assumptions and note them in the footer.
