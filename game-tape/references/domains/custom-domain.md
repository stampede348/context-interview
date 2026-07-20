# The Domain Generator

This is how Game Tape serves any profession without a prebuilt profile — a trial lawyer, a wedding DJ, a stand-up comic, an ER charge nurse, a youth soccer coach, a live streamer. Interview the user about their craft, then mint a `tape-domain.md` for their project knowledge. Every future session detects and uses it automatically.

Bar for the output: a generated profile must be as sharp as the bundled ones. Vague anchors produce vague debriefs produce a useless log. The quality test for every line you write: **if a camera watched the performance, could it verify this?** "Good opening" fails the test. "Room aligned on the problem before the first screen" passes.

## Step 0 — The Fit Test

Game Tape works on performances that are:

1. **Repeated** — it happens again, so learning compounds
2. **Bounded** — a start and an end you can point to
3. **Observable** — you can tell, from signals in or right after the performance, what landed and what didn't

If the user's work fails one of these (e.g., "writing my novel" — not bounded or repeated in the right way), say so plainly and suggest the closest bounded unit that would work (e.g., "each critique-group reading of a chapter" passes all three). Don't force a bad fit; a system built on a bad unit produces noise.

## Step 1 — The Interview (one question at a time)

1. **The unit.** "What's one performance — the thing that repeats? Where does it start and end?" **If the craft has two performance types** (a coach's training sessions vs. match days; a lawyer's depositions vs. trial days; a chef's prep vs. service), don't force a choice and don't build two systems: make the type a **context field**, and write anchors that bite for both types. Only split into a primary unit if the anchors genuinely can't cover both without going mushy — mushy anchors are the worse failure.
2. **The arena.** "Who's on the other side — audience, counterparty, panel, patients, players? What are they hoping happens?"
3. **Winning.** "Right as it ends, how do you know it went well? What do you see or hear? And how do you know it went badly?" *(This defines "landed" — push past feelings to observable signals.)*
4. **The sideways moments.** "What are the 2–3 ways it most often goes wrong mid-performance — the pressure moments, hard questions, or resistance you face?" *(This defines the friction categories.)*
5. **The craft.** "What's the technical skill that separates someone good at this from someone great, executed live under pressure?" *(This anchors Command.)*
6. **The variance.** "What changes most about how you have to perform — the audience type, the setting, the stakes, the material? Pick the 2–3 that matter." *(These become the context fields — what Pre-Game matches on and Film Review splits by.)*

Extract from conversation first — if the user already described their work, confirm rather than re-ask.

## Step 2 — Map to the Five Slots

Fill the anchors using their answers. The slots never change; only the anchors do:

- **The Open** — from their unit + arena: what does starting cold vs. commanding the first minutes look like *here*?
- **The Thread** — what's the spine in this craft (a lesson objective, a set list's arc, a case theory, a match plan)? 1 = sequence of parts; 5 = every part serves the spine.
- **Command** — directly from Q5. Make the 1 concrete (the observable failure mode) and the 5 concrete (the observable mastery).
- **The Turn** — from Q4: the pressure moments, and what folding vs. converting them looks like.
- **The Close** — from Q3: what does a secured ending look like, and what does trailing off look like? Where useful, add a scoring tripwire like the bundled profiles do ("if X didn't happen, Close scores 3 or below").

## Step 3 — Build the Drilling Rows

Ask: "After one of these, what do you catch yourself saying when it was just okay?" Take their 2–3 stock vague answers and write the converting question for each — the question that forces a specific moment. Model them on the bundled profiles' rows.

## Step 4 — Produce the File

Generate `tape-domain.md` using this exact structure (identical to bundled profiles, so the engine reads it the same way):

```markdown
# Domain: [Name] (custom)

**Fits:** [who]
**One performance =** [the unit]
**"Landed" means:** [observable signals from Q3]

## Context Fields (Phase 0)
- [field 1] ([examples])
- [field 2] ([examples])

## The Five Dimensions
| Slot | 1 looks like | 5 looks like |
|---|---|---|
| **The Open** | [observable] | [observable] |
| **The Thread** | [observable] | [observable] |
| **Command** | [observable] | [observable] |
| **The Turn** | [observable] | [observable] |
| **The Close** | [observable] | [observable] |

## Phase 1 Phrasing
- Highlight: "[question in their language]"
- Stall: "[question in their language]"
- Surprise: "[question in their language]"

## Drilling Table Additions
| They say | Ask this |
|---|---|
| "[their stock vague answer]" | "[converting question]" |

## Friction Categories
[from Q4, with verdict language: what landed / neutral / lost looks like here]

## The Close, Specifically
[the tripwire rule, if one emerged]
```

Read the draft back in one screen — the five dimensions and "landed" definition — and ask for one correction, not open-ended feedback. Then run the update loop from SKILL.md: create the complete file, present it, and tell the user to add `tape-domain.md` to project knowledge alongside the three data files.

## Step 5 — Prove It Immediately

Offer to run their most recent performance through the debrief right now. A generated domain earns trust by producing a sharp first entry within ten minutes of existing — and the first debrief is also where weak anchors reveal themselves. If an anchor doesn't bite during that first debrief, fix it on the spot and regenerate the file.
