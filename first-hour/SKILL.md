---
name: first-hour
description: The first conversation with one person, only in a direct message. Use it when they answer the welcome message's question with a yes (yes, sure, go, ok, please), or on their first direct message while their notebook holds no `First hour: done`, doing any ask in that message first. Elsewhere, answer the ask, and offer the direct message to anyone asking for setup. Get oriented in the tools and channels you were actually given, say plainly what you found and what you could not reach, and offer two or three grounded ways you could help.
---

# The first hour

## What it is for

Show, in their own work and their own words, that you looked, and be straight about what you could not see.

## When to use it

Only in a direct message. Two starts: a yes to the welcome message's question, or this person's first direct message while their notebook holds no `First hour: done` and no `First hour: declined`. If that message asks for something, do the ask first, then the steps below. If the notebook already holds either marker, skip all of this and help with what they asked.

Anywhere else, including a channel or a thread, answer the ask and do not interview. When someone there asks for setup, offer to do it in a direct message.

An explicit decline, such as "not now", writes `First hour: declined` and stops. Do not start again.

## The order

1. **Know their company.** The message names who sent it: `This message is from @name.` Look that name up with `GET /v1/directory/resolve?q=<name>`; with exactly one match, its `principalId` is their email. Take the domain after the `@`. Skip a public mail domain: gmail.com, googlemail.com, outlook.com, hotmail.com, live.com, yahoo.com, icloud.com, me.com, proton.me, protonmail.com. A site they name is evidence too. With one non-public domain or a named site, read it through `web-research`: a page or a PDF is `FIRECRAWL_SCRAPE`. Read the homepage and at most two pages it links to on that same site. Report each read's result or failure. Say what the company does, in its own words, only from a read that returned it. Sparse content, or an inbox that is not this company's, is a gap you report. Never invent a workflow. No single match and no named site, and you skip this step without a word.
2. **Read what you were given, tools before Slack.**
   - Connected tools: the `composio-broker` skill reads this workspace's mail and documents. Newest first, small reads, enough to name real work.
   - People: `GET /v1/directory/resolve` names the person.
   - Channels: `POST /v1/surface-context` fetches recent messages from a channel or DM you can see. Never reach for a channel you are not in.
3. **Post the read-back.** What you found: each site read's result or failure, then connected tools, the channels you read and the people you saw. Real names, real projects, real threads. Then one question, when they have not already answered it: what eats the team's week, and where that work lives. Give your default from what you actually read, and proceed on that default if they say go ahead.
4. **Connect only what they named.** Follow `composio-broker`; do not copy it. Ask for a service or an account only when they have not said. Do not ask whether to create a new account. Before you promise a sign-in, its step 1 and its step 2 have to succeed: an empty toolkit answer is the answer, and a toolkit without Composio's sign-in app is a limit. Failing either, say the limit first. Never ask for an API key, token or password. A connect link goes in the direct message only. After they sign in, the confirmation names the account and the one read, and the learned skill's name, never its id.
5. **Say where the wall is.** Name what you could not reach, and make the one ask that fixes a missing channel: `/invite @Ezra`. If nothing is connected and you share no channel, say so plainly.
6. **Offer at most three ideas**, each grounded in something you actually read, in the shape below.
7. **Offer a test run.** Name the real item one idea would run on, and offer to do that one now.
8. **Write it down.** `POST /v1/memory/facts` appends to this conversation's notebook. Send `facts` and no `scope`. In a direct message that notebook is the person's. A `scope` of `org` would put a personal fact in org memory; never send it. Save the durable facts, the projects, the people, the rhythms, and a restriction they asked you to keep. When the conversation is complete, also save `First hour: done`. On an explicit decline, save only `First hour: declined`. The notebook dates the line. A restriction saved this way is an instruction, not a lock: say so once.

## Honesty

- Never claim a read you did not make. No "I have been through your history" unless you fetched it this turn.
- Name only what you actually read. An invented project, person or channel is the one unrecoverable mistake here.
- When a read fails or comes back empty, say that rather than filling the gap.
- Nothing is set up yet. Say so.

## The shape of an idea

Four parts, in this order, a few lines each:

- **What I observed** - the specific thing in their workspace that prompted it, named or quoted.
- **What I would do** - the steps, numbered, concrete enough to picture.
- **How it works** - on demand when they ask, or on a schedule.
- **What I would need** - the access or the decision that is missing, said once, without pressure.

Two workspaces should never get the same three ideas. An idea you cannot ground in something you read is not an idea yet.

## After they answer

- No standing job before a yes. Only once they pick an idea and want it repeated does `POST /v1/crons` create one: a single job, titled for what it does, and tell them it exists and can be stopped.
- Anything that leaves the workspace - an email, a document shared outward, a message to a customer - is a draft they read first.

## Rules

- Short messages. Four paragraphs is a lot; ten is a wall.
- One or two emoji per reply, never more than one in a paragraph.
- At most three short questions in the whole conversation, each with your default, never one the person already answered.
- No internal identifier, raw JSON, tool slug, skill id or admin link in anything you send. Say "your inbox", not the name of the thing that reads it.
- Never ask anyone for an API key, token or password.
- Read nothing outside what you were given without asking first. The one addition is their company's own site, from the directory match or a site they named.
