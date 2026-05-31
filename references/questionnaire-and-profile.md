# Questionnaire & profile

Used in Mode B (guided setup). The interview is conducted **one question at a time, conversationally** — this file is the bank to draw from, not a form to paste.

## The question bank

Pick what's relevant, reorder freely, and follow interesting threads. Aim for ~8–12 questions total.

1. **Role & context** — What's your line of work or main role? Are you solo, on a team, or running something? What world/industry do you operate in?
2. **Time-eaters** *(most important)* — What takes up the most time each week? What's repetitive, tedious, or annoying enough that you put it off?
3. **Hand-off wish** — If you could fully delegate one or two things tomorrow, what would they be?
4. **Current projects** — What are you actively working on right now? Any deadlines or goals in the next few weeks?
5. **Tools & where stuff lives** — What software do you use daily (email, docs, sheets, design, socials, code)? Where does your data live (Google Drive, Notion, local files)? Anything you constantly copy-paste between apps?
6. **What you make** — Do you produce content or deliverables? What formats (video, writing, social posts, slides, reports, spreadsheets)?
7. **Hobbies & side projects** — What do you do outside work, or on the side, that an assistant could help with?
8. **Goals & constraints** — Top thing you want taken off your plate? How comfortable are you with technical setup (plug-and-play vs. configuring things)? Anything off-limits or sensitive?

Probes to deepen thin answers: "What does that look like step by step?", "How often?", "What's the worst part of it?", "What do you do right before/after that?"

## Profile schema

Fill this in after the interview. Leave a field blank rather than inventing — blanks are honest and discovery still works with a partial profile.

```yaml
# skill-profile
role:                 # e.g. "freelance video editor"
industry:             # e.g. "media / content"
work_context:         # solo | small team | company
current_projects:     # [ ... actively working on ]
recurring_tasks:      # [ ... weekly time-eaters ]
pain_points:          # [ ... what they want gone ]
tools:                # [ ... software used daily ]
data_locations:       # [ ... Google Drive, Notion, local, etc. ]
content_types:        # [ ... video, writing, slides, sheets, social ]
hobbies:              # [ ... ]
side_projects:        # [ ... ]
agent_goals:          # [ ... top things to hand off, priority order ]
technical_comfort:    # low | medium | high
constraints:          # [ ... off-limits / sensitive ]
```

`recurring_tasks`, `pain_points`, and `agent_goals` are the high-value fields — they drive matching. If they're thin, ask one or two more questions before moving on.

## Saving the profile

Save the confirmed profile so future sessions reuse it without re-interviewing. Default location:

```
<agent-data-dir>/skill-profile.md
```

If the agent's data directory is unknown, ask once or fall back to the working directory and tell the person the path. Write the YAML block above plus a short plain-language summary paragraph at the top so they can skim it.

## Turning the profile into needs

Convert the profile into task-shaped needs for discovery — one concrete task each, drawn mainly from `pain_points`, `recurring_tasks`, and `agent_goals`:

- Good: "draft replies to incoming customer emails"
- Good: "turn a long recording into short vertical clips"
- Too vague: "help with email"
- Too broad: "run my whole business"

3–6 sharp needs beat a dozen mushy ones. Then run the discovery workflow (`references/skill-discovery.md`) once per need.
