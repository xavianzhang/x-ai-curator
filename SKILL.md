---
name: hermes-x-ai-curator
description: Use this skill when Hermes needs to gather the latest AI or tech news from the web, rank which items are most suitable for X posting, ask the user to choose which topics to publish, and then turn selected items into high-engagement X post templates in Chinese or English.
---

# Hermes X AI Curator

This skill is for a lightweight AI/tech interpretation workflow on X:

1. Collect recent AI/tech/news items from primary or high-signal sources.
2. Summarize each item in plain language.
3. Score whether the item is worth posting on X.
4. Present a shortlist and wait for the user's selection.
5. Convert selected items into multiple X-ready post templates.

Use this when the goal is speed, repeatability, and high-signal posting rather than deep research.

## Core Rules

- Prefer recent items from the last 24 to 72 hours unless the user asks for a longer window.
- Prefer primary sources first: official blogs, official X accounts, product changelogs, research labs, company press releases, GitHub releases, and original papers.
- Use secondary media only to discover items or add context.
- Never output a post that is just copied text from a source. Always rewrite with a clear angle.
- Favor items that trigger discussion, not just passive reading.
- If browsing is available, verify unstable facts before presenting them.
- Avoid spammy or manipulative post styles such as engagement bait, fake urgency, or vague hype.

## Fast Workflow

### Step 1: Gather candidate items

Search for 8 to 15 recent items across these buckets:

- Model launches or major updates
- AI tools or product features with obvious user impact
- Big company strategy moves in AI or tech
- Research breakthroughs with practical implications
- Creator economy or social platform changes relevant to X

For each candidate, capture:

- `title`
- `source`
- `publish_date`
- `url`
- `what_happened`
- `why_it_matters`

### Step 2: Score for X fitness

Score each item from 1 to 5 on:

- `timeliness`: is it fresh enough to matter now
- `clarity`: can normal users understand it quickly
- `discussion_potential`: will people argue, ask, or share
- `audience_fit`: useful for AI/tech-interested X users
- `durability`: still worth reading after 24 hours

Then classify:

- `A`: high priority, should likely post
- `B`: decent, post if it matches the account angle
- `C`: skip for now

Prefer A items that combine freshness and a clear implication.

### Step 3: Present shortlist to the user

Do not auto-generate final posts for everything. First show the shortlist.

Use this format:

```text
Candidate 1
Topic:
What happened:
Why it matters:
Why it may perform on X:
Suggested angle:
Priority: A

Candidate 2
...
```

At the end, ask the user to pick by number.

### Step 4: Turn chosen items into post templates

For each selected item, generate 3 versions:

- `quick_take`: short opinionated post
- `three_point_breakdown`: structured explanatory post
- `discussion_hook`: post designed to trigger replies

Each version must include:

- a strong first line
- one concrete fact
- one interpretation or consequence
- one clean closing line or question

Default length targets:

- `quick_take`: 70 to 140 Chinese characters or 40 to 90 English words
- `three_point_breakdown`: 140 to 280 Chinese characters or 90 to 180 English words
- `discussion_hook`: 80 to 180 Chinese characters or 50 to 120 English words

## Account Angle

Unless the user says otherwise, optimize for this account style:

- niche: AI and tech interpretation
- voice: sharp, simple, non-academic
- audience: curious builders, founders, operators, and early adopters
- goal: attract replies, reposts, and follows from people who care about AI product shifts

Default perspective:

- explain what changed
- explain who gains or loses
- explain what ordinary users or builders should do next

## Selection Heuristics

Good posting candidates often have at least 3 of these traits:

- a well-known company or founder is involved
- the update changes workflow, pricing, access, or distribution
- the item can be explained with a strong opinion in one sentence
- users can immediately test or feel the impact
- the news implies a broader trend

Weak candidates usually look like:

- incremental updates with no clear user impact
- vague rumor without source confidence
- highly technical research with no practical angle
- content already saturated unless the account has a distinct take

## Output Templates

Read [references/output-formats.md](references/output-formats.md) before generating the final response.

When writing posts, use [references/post-angles.md](references/post-angles.md) to select a framing angle.

## Default Response Contract

When the user asks for news selection:

1. Gather and rank candidates.
2. Show the shortlist.
3. Wait for the user's picks.

When the user asks to draft posts:

1. Confirm the selected items.
2. Generate 3 post variants per item.
3. Optionally add 3 to 5 reply ideas under each post if the user wants conversation support.

## Safety and Quality

- Do not fabricate source details.
- Separate facts from inference.
- If a fact is not verified, label it as unconfirmed.
- Avoid libel, impersonation, fake persona writing, or manipulated-media claims without evidence.
- Avoid direct copying from copyrighted articles beyond short, necessary excerpts.
