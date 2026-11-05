---
title: "IT English: For Software Developers and Tech Writers"
meta_description: "Practical IT English for Sri Lankan tech professionals — coding reviews, documentation, Slack communication, and the vocabulary that lands with international teams."
slug: it-english-sri-lanka
primary_keyword: it english sri lanka
secondary_keywords: [english for developers sri lanka, tech english vocabulary, coding english, documentation english]
target_audience: software developers, QA engineers, technical writers
word_count_target: 1300
---

# IT English: For Software Developers and Tech Writers

Sri Lanka's tech sector works in English. Most companies have international clients or distributed teams. Code reviews, pull request descriptions, Slack conversations, documentation — all in English. Yet many strong developers are held back by communication, not coding.

Here's the practical guide to the English specific to tech work.

## Where IT English differs from general English

### Shorter, more direct

Tech communication values speed and clarity. Long formal paragraphs don't fit a Slack-based workflow.

### Specific vocabulary

- Technical terms (the obvious part).
- Workplace conventions (standup, retro, PR, async).
- Problem-solving vocabulary (edge case, regression, flaky test).

### Writing matters more than you think

Slack, GitHub PRs, Jira tickets, documentation — tech is a writing-heavy job even for developers. Clear writing lifts your reputation.

## Core IT vocabulary

### Development workflow

- **Pull request (PR) / merge request (MR)** — a proposed code change.
- **Review** — examining a PR for quality.
- **Approve, request changes, comment** — the three main PR actions.
- **Merge** — combining a PR into the main branch.
- **Deploy / release** — pushing code to production.
- **Rollback** — reverting a deployment.
- **Hotfix** — urgent fix to a production issue.
- **Feature branch** — a branch for developing a specific feature.
- **Main / master** — the primary branch.

### Methodologies

- **Agile** — iterative development framework.
- **Sprint** — a short development cycle (usually 2 weeks).
- **Standup** — daily short team meeting.
- **Retro (retrospective)** — looking back on a sprint.
- **Backlog** — list of pending work.
- **Ticket / issue** — a unit of work in a tracking system.
- **Story / epic** — larger units of work in agile.
- **Groomed / refined** — tickets that have been clarified and estimated.

### Problem types

- **Bug** — defect in code.
- **Regression** — something that used to work breaking.
- **Edge case** — rare situation code didn't anticipate.
- **Flaky test** — test that sometimes passes, sometimes fails.
- **Memory leak** — program using more and more memory over time.
- **Race condition** — timing-dependent bug.
- **Null pointer / undefined behaviour** — common classes of bug.
- **Technical debt** — accumulated maintenance cost from shortcuts.

### Communication conventions

- **Async** — asynchronous, not in real time. *"Let's handle this async."*
- **DM** — direct message.
- **Thread** — a specific conversation branch in Slack.
- **FYI** — for your information.
- **Heads up** — advance warning.
- **PTAL** — please take a look.
- **LGTM** — looks good to me.
- **WIP** — work in progress.
- **Nit** — a small, non-blocking comment in code review.
- **Blocker** — something preventing progress.

## Writing a good pull request description

### Weak PR description

> *Fixed the bug*

Zero context. Reviewer has to dig to understand.

### Strong PR description

> **Title:** Fix timezone handling in order confirmation email
>
> **Description:**
>
> *The confirmation email was showing UTC timestamps instead of the user's local timezone. This was reported in #ticket-1234.*
>
> **Root cause:** We were passing the raw timestamp to the email template without converting to the user's timezone, which is stored in the user profile.
>
> **Fix:** Updated the email service to pull the user's timezone and apply it before rendering.
>
> **Testing:**
> - Added unit tests covering 3 timezones (UTC, IST, PST).
> - Verified manually with test accounts in each timezone.
>
> **Reviewer notes:** The timezone conversion is now centralised in `emailService.formatDateForUser()` — happy to extract it further if the reviewer prefers.

Takes 2 minutes to write. Saves 10 minutes of back-and-forth per reviewer.

## Code review English

### Making a suggestion

- *"Consider using X here — it handles the edge case where..."*
- *"We could simplify this by..."*
- *"This might be clearer as..."*
- *"What do you think about renaming this to..."*

### Flagging a concern

- *"I think there's a bug here — if the user is null, this will crash."*
- *"This changes the public API — we need to check who's using it."*
- *"This might not scale beyond 10k users — have we tested at load?"*

### Agreeing

- *"LGTM once the test is added."*
- *"Approved — thanks for the fix."*
- *"Good catch."*

### Disagreeing politely

- *"I'd push back on this — the trade-off seems worse than the problem."*
- *"I understand the goal, but I'm worried about [specific concern]. Could we discuss?"*
- *"I prefer the original approach because..."*

Avoid harsh language. "This is wrong" lands badly in text; "I'd push back on this" starts a conversation.

## Standup English

A daily standup is 1–3 minutes per person. Structure:

- **Yesterday:** what you did.
- **Today:** what you plan to do.
- **Blockers:** anything stopping you.

### Example

> *"Yesterday I finished the login refactor PR and started on the password reset flow. Today I'll continue the password reset work and review Priya's analytics PR. No blockers."*

Three sentences. Clear. Done.

### Common mistakes

- Reporting every file touched instead of the overall work.
- Vague "worked on stuff" updates.
- Long explanations of technical details — save those for a sync.
- Not mentioning blockers because "I'll figure it out."

## Slack and chat English

### Opening a conversation

- *"Hey, quick question about the API spec..."*
- *"Hi, I'm seeing a weird error in prod — anyone else?"*
- *"Morning — anyone free for a 10-min pairing session?"*

### Asking for help

- *"I'm stuck on X. Here's what I've tried: ... Any ideas?"*
- *"Is there a reason we chose Y over Z for the auth flow?"*
- *"Could someone explain why this test is failing? Logs here: ..."*

Include what you've already tried. Shows you respect others' time.

### Replying

- *"Thanks — that fixed it."*
- *"Good question — let me check and come back."*
- *"On it. Will update in 30 min."*

### Avoiding

- *"Please help urgently!"* — pressure without context.
- *"Doesn't work."* — not actionable.
- Long walls of text without structure — use bullet points or threads.

## Documentation English

Technical documentation needs:

- **Short sentences.** One idea per sentence.
- **Clear structure.** Headings, subheadings, numbered steps.
- **Active voice.** "The server returns a token," not "A token is returned by the server."
- **Consistent terminology.** Don't switch between "user," "customer," and "account holder" in the same doc.
- **Examples.** Every abstract rule needs a concrete example.

### Example — API documentation

> *The `createOrder` endpoint accepts a POST request with the following body:*
>
> ```json
> {
>   "customer_id": "uuid",
>   "items": [...],
>   "shipping_address": {...}
> }
> ```
>
> *The endpoint returns a 201 with the order details on success, or 400 with error details if the request is malformed.*
>
> *Example error response:*
>
> ```json
> {
>   "error": "missing_field",
>   "field": "shipping_address"
> }
> ```

Structure. Example. Both success and error cases.

## Common Sri Lankan IT English mistakes

### 1. Over-formal English in Slack

- ✗ *"Dear team, kindly find attached the JIRA ticket for your gracious perusal."*
- ✓ *"Here's the ticket, PTAL."*

### 2. *Revert* for reply

Still appears in internal Sri Lankan tech teams. Use *get back to you* or *reply* with international teammates.

### 3. Dropping articles in writing

- ✗ *"Deploying fix to staging now."*
- ✓ *"Deploying the fix to staging now."* (Or informal: *"Pushing fix to staging."*)

### 4. Over-apologising

- ✗ *"So sorry, really sorry about the delay, my apologies..."*
- ✓ *"Sorry for the delay — will have this by EOD."*

### 5. Vague commitments

- ✗ *"I'll try to do it."*
- ✓ *"I'll have it done by Thursday — will update if blocked."*

## Where Woodberry Place fits

Our Business English programme includes a tech track covering PR descriptions, Slack communication, documentation, and standup English. Students work on actual (anonymised) workplace writing.

## Frequently asked questions

**Do I need good English to work in tech from Sri Lanka?**

Yes, for international clients and distributed teams. Local-only tech work can function in Sinhala or Tamil, but opportunities expand significantly with English.

**Which matters more for a developer — coding or English?**

Both. Strong coders with weak English are limited to local or offshore back-end roles. Strong coders with strong English access remote jobs, product leadership, and international teams.

**Can I learn IT English on my own?**

Partly. Read engineering blogs (Martin Fowler, Dan Luu, Julia Evans). Follow senior developers on Twitter / X / Mastodon. Write your own technical blog posts.

**What's the most important writing skill for a developer?**

Writing clear pull request descriptions. It's the one thing every teammate sees, and it defines how your work is understood and reviewed.

---

Working in tech and looking to sharpen your English? [See our Business English programme](https://woodberryplace.com/courses/spoken-english/) or contact us about tech-focused sessions.
