# Ezra skills

Skill packs for [Ezra](https://tryezra.ai), the AI employee that lives in your Slack. An admin imports a pack once and every skill in it becomes available to your Ezra.

## Event Scout

Ezra finds the events worth your time, or your team's, and posts the best three each morning.

- **Finds the rooms nobody lists.** Beyond Luma, Partiful and Eventbrite, it watches the accounts that announce events in their own posts on Instagram, LinkedIn and X, often two days out with no listing anywhere.
- **Scores against what you need now:** hiring, fundraising, customers, a specific person to meet. General networking is out unless you ask for it.
- **Posts three, not thirty.** Every digest ends with a Sources line saying what was checked and what failed.
- **Never registers you.** Reply `go 2` and it puts a hold on your calendar and hands you the link. Reply `skip 2 too far` and it learns.
- **Checks what you send it.** Drop a screenshot of an event and get go or skip in two lines.
- **Keeps the record in a Google Sheet you own:** the brief you can edit, and every event seen with what came of it.

One skill, `event-scout`. Ezra reads only the part the moment needs:

| File | Used when |
|---|---|
| `SKILL.md` | Always. What Event Scout is and which file to read |
| `setup.md` | Setting up: interview, watchlist, sheet, one live run, daily cron |
| `run.md` | The daily run, your `go` / `skip` / `more` replies, and the follow-up after an event |
| `check.md` | Go or skip on one event you share |

### Requirements

- Ezra's web research (page reads, search and scrapers) enabled for the workspace.
- Google connected in Ezra: Sheets and Calendar. Gmail if invites should count.

### Install

1. Admin UI → **Skill packs** → **Register**: this repository's URL and a pinned commit.
2. Open the pack, **Import all**.

### Use

- **For yourself:** DM Ezra, "set up event scout."
- **For a team:** create a channel such as `#events`, invite Ezra, and say "@Ezra set up event scout for this channel."

### Cost

Scraper runs are billed per post by the scraper's publisher. At the Apify Store prices listed on 2026-09-28 (Instagram $0.0015, LinkedIn $0.002, X $0.0004 per item), a 40-account watchlist posting about once a day each comes to a few cents a day. That's an estimate, not a quote.

## License

MIT
