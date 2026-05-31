---
name: skill-recommender
description: Finds the right agent skills for any person — technical or not — and helps install them safely from the open skills ecosystem. Works two ways. If someone names a concrete task ("find a skill for X", "is there a skill for X", "can you do X", "I wish I had help with X"), it searches the ecosystem directly. If someone is new or unsure ("what skills do I need", "help me get set up", "recommend skills for me", "what can you actually help me with"), it runs a short, friendly questionnaire about their work, projects, tools, and hobbies, then finds skills tailored to them. Use this for ANY request to discover, recommend, search for, compare, or set up agent skills, for onboarding a new user, or whenever someone wishes they had help with a task and a matching skill might exist — even if they never say the word "skill". Covers every domain, not just coding.
---

# Skill Recommender

Most people can't choose skills they don't know exist, and hunting through GitHub to download random skills is slow and risky. This skill solves both: it figures out what a person actually needs — either from a task they name or from a short interview — then searches the open skills ecosystem, checks each candidate for quality and safety, and offers to install the good ones.

It is built for **everyone**, not just developers. Use plain language, avoid jargon unless the person uses it first, and search across all domains (writing, admin, finance, content, research, home life, hobbies — not just code).

## Two ways in — pick the right one

**Mode A — Direct lookup.** The person names a specific task or capability ("is there a skill that drafts invoices?", "find me something for editing podcasts"). Go straight to discovery. Do **not** make them sit through an interview for a single need.

**Mode B — Guided setup.** The person is new, unsure, or wants broad recommendations ("what should I install?", "help me get set up", "what can you help me with?"). Run the interview first, then discovery.

If it's unclear which they want, ask one quick question: *"Do you already have a specific task in mind, or would you like me to figure out what'd help you?"* Then proceed accordingly.

---

## Mode A — Direct lookup

1. Restate the need as one clear task in plain words.
2. Run the **discovery workflow** below.
3. Present what you find and offer to install it (with their OK).

That's it — keep it fast.

---

## Mode B — Guided setup

### Phase 1 — Interview

Ask questions **one at a time, conversationally.** Never paste a whole questionnaire as a wall of text — that's the exact experience this skill exists to replace. Wait for each answer, react briefly, then ask the next thing.

What makes the interview good:

- **Be adaptive.** The areas below are a map, not a script. Follow interesting threads; skip anything clearly irrelevant.
- **Keep it short** — roughly 8–12 questions total. A warm chat, not an interrogation. Combine small related questions.
- **Use what you already know.** If the person already told you their job, tools, or projects earlier (or it's in saved context), don't re-ask — acknowledge and move on.
- **Dig for pain, not just facts.** The most useful thing for matching is knowing what eats their time and what they'd love to hand off. Spend your best questions there.

Cover these areas (reorder and prune freely): role & context; weekly time-eaters *(most important)*; what they'd hand off tomorrow; current projects & deadlines; tools they use and where their data lives; what they create; hobbies & side projects; top goal and how comfortable they are with technical setup.

The full question bank, probes, and the profile schema are in `references/questionnaire-and-profile.md` — read it when running this phase.

When you can paint a clear picture, **stop asking.**

### Phase 2 — Build the profile

Summarize what you heard into the structured profile in `references/questionnaire-and-profile.md`. **Reflect it back** in a few plain sentences ("Here's what I picked up — correct me if I'm off") and let them fix it; people often add their most useful detail right here. Then save the profile to a file so it can be reused later without re-interviewing (path and format in the reference file).

### Phase 3 — Discovery per need

Turn the profile into a flat list of **task-shaped needs** — one concrete task each, phrased plainly (e.g. "draft replies to customer emails", "turn a long recording into short clips", "track unpaid invoices"). Pull them from the person's pain points and goals; don't pad the list. Then run the discovery workflow once per need and aggregate the results into a single shortlist.

---

## Discovery workflow (used by both modes)

This is the engine. Full details — exact CLI commands, the all-domain category map, quality verification, install steps, and the safety rules — are in `references/skill-discovery.md`. Read it before running discovery. In short:

1. **Understand the need** — domain + specific task; is it common enough that a skill likely exists?
2. **Check the catalog/leaderboard** on skills.sh for a well-known, popular skill in that area.
3. **Search** with `npx skills find <keywords>` if the leaderboard doesn't cover it. Use general, plain-language keywords spanning any domain.
4. **Verify quality before recommending** — install count, source reputation, repo stars. Never recommend on a raw search hit alone.
5. **Present** the matches clearly.
6. **Offer to install** — only after explicit user confirmation.

---

## Presenting results

Aggregate everything into one prioritized shortlist:

```
## Skills I'd set you up with

### Start here
1. **<skill name>** — <one line: what it does>
   Why you: <tie to a specific thing they said, or to the task they named>
   Source / popularity: <owner/repo · install count>
   Setup: <plug-and-play | needs config | needs an API key>
   Install: <the exact command>

### Worth adding soon
...

### Nice-to-have
...
```

Rules:

- **Every "Why you" points to something concrete** — an interview answer (Mode B) or the task they asked for (Mode A). No generic filler.
- **Order by impact**, not category — biggest time/pain saver first.
- **Be honest about effort and trust.** Flag anything that needs setup, credentials, or comes from a low-popularity / unknown source.
- Keep it digestible — 3–7 strong picks, not everything that vaguely matches.
- In Mode B, end by noting where the profile was saved and that they can re-run anytime to refresh as new skills get published.

## Installing

Installing a skill changes the person's system, so **always get an explicit yes first**, show the exact command, then run it. Prefer well-established, audited skills; if the best match is from an unknown or low-star source, say so plainly and let the person decide. Never silently install anything.

## When nothing's found

Don't fabricate recommendations or pull skills from untrusted corners of the internet. Instead: say plainly that no good match exists yet, offer to help with the task directly using your general abilities, and mention they could create their own skill (the ecosystem is community-driven and growing, so a gap today may be filled tomorrow). Details in `references/skill-discovery.md`.
