# Skill discovery (all domains)

This is the engine the skill uses to find and install skills from the open ecosystem. It started as a coding-focused workflow; here it's generalized so it works for anyone — writers, freelancers, parents, small-business owners, researchers, hobbyists — not just developers.

## What the Skills CLI is

`npx skills` is the package manager for the open agent skills ecosystem. Skills are modular packages (a `SKILL.md` plus optional resources) that teach an agent a new capability. The public catalog lives at https://skills.sh and the registry is community-driven — any public GitHub repo with a `SKILL.md` at its root is a valid source, across any subject, not only code.

Key commands:

- `npx skills find <keywords>` — search the index for skills
- `npx skills add <owner/repo>` or `npx skills add <owner/repo@skill>` — install a skill
- `npx skills list` — list installed skills
- `npx skills check` — check for updates
- `npx skills update` — update installed skills
- `npx skills init <name>` — scaffold a brand-new skill

## Step 1 — Understand the need

Identify:
- The **domain** (e.g. writing, scheduling, invoicing, video, research, parenting, gardening, coding).
- The **specific task** (e.g. "summarize meeting notes", "build a budget", "cut a podcast into clips").
- Whether it's **common enough** that a skill likely exists.

## Step 2 — Check the catalog/leaderboard first

Before searching, check skills.sh to see if a well-known skill already covers the domain. The leaderboard ranks by total installs, surfacing the most popular, battle-tested options. Established publishers (e.g. Vercel Labs, Anthropic, Browserbase) tend to be reliable, but plenty of strong community skills exist too.

## Step 3 — Search

If the leaderboard doesn't cover it, run:

```
npx skills find <keywords>
```

Use plain, specific, domain-agnostic keywords. Examples across audiences:

- "I want help answering customer emails" → `npx skills find customer email replies`
- "I need to plan a trip" → `npx skills find travel itinerary`
- "Help me keep track of invoices" → `npx skills find invoice tracking`
- "Turn my long videos into clips" → `npx skills find video clips`
- "I journal every day" → `npx skills find journaling`
- "Review my code" → `npx skills find code review`

## Category map (all users)

Use this to translate a person's world into search keywords. Coding is just one row, not the focus.

| Area | Example queries |
| --- | --- |
| Writing & communication | email, summarize, proofread, newsletter, copywriting |
| Admin & scheduling | calendar, meeting notes, reminders, to-do, workflow |
| Finance & money | invoice, budget, expenses, bookkeeping, receipts |
| Research & learning | research, summarize papers, flashcards, study, notes |
| Content creation | video, podcast, social posts, blog, thumbnails, captions |
| Design & visuals | image, slides, presentation, branding, layout |
| Home & personal | meal planning, shopping list, recipes, fitness, habits |
| Travel & events | itinerary, trip planning, event planning, packing |
| Data & docs | spreadsheet, PDF, data cleanup, forms, reports |
| Web & coding (technical users) | react, testing, deploy, docs, git, refactor |

## Step 4 — Verify quality before recommending

Never recommend on a raw search hit alone. Check:

- **Install count** — prefer 1K+ installs; treat anything under ~100 with caution.
- **Source reputation** — official/known publishers are safer than unknown authors.
- **Repo signals** — check the source GitHub repo; very low stars warrants skepticism.

skills.sh runs routine security audits on listed skills, which helps — but it's not a guarantee, so still apply the checks above. This matters even more for non-technical users, who are least able to spot a sketchy skill themselves; protecting them from junk or malicious skills is part of the job.

## Step 5 — Present options

For each relevant skill, give: what it does, the source and install count, the install command, and a link to learn more on skills.sh. Tie the recommendation back to what the person actually needs.

## Step 6 — Offer to install (with permission)

Installing changes the person's system, so confirm first. Once they say yes:

```
npx skills add <owner/repo@skill> -g -y
```

`-g` installs at the user level; `-y` skips prompts. Show the command before running it. If the best match is from a low-trust source, say so and let the person choose rather than installing quietly.

## When no skills are found

1. Say plainly that no existing skill matched.
2. Offer to help with the task directly using general capabilities.
3. Mention they could create their own skill (`npx skills init <name>`) — and that the registry is community-driven and growing, so gaps fill over time.

Never invent skills or fetch them from untrusted/unknown sources to fill a gap.

## A note on where this runs

These commands run on the agent's own machine (e.g. the Hermes VPS), which has Node and network access — not inside any sandbox. If `npx`/Node isn't available, tell the person what's needed rather than guessing.
