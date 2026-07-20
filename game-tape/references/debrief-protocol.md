# The Debrief Protocol

Run within 24 hours of the performance — same day is best; memory of specific moments decays fast. Ten minutes, hard cap. One question at a time, conversationally. Load the domain profile first — it supplies the phrasing, the context fields, and the score anchors used below.

The phases are ordered deliberately: context while it's cheap, the vivid moments while they're fresh, the analytical work after, the commitment last so it's what the user walks away holding.

## Phase 0 — Context (60 seconds)

Get these in one or two exchanges, not seven questions:

- Codename for the counterparty/event (assign now if new — check tape-log.md for existing codenames first)
- The domain's **context fields** (the profile defines them — e.g., vertical + persona for demos; company stage + round for interviews)
- Which performance this is in the sequence (first meeting, third interview round, repeat of a talk...)
- Stakes/stage, in the domain's terms

If the user ran Pre-Game before this performance, most of this is on that card — confirm, don't re-ask.

## Phase 1 — The Tape (3 minutes)

Three questions, in order, phrased per the domain profile:

1. **The highlight.** "What's the one moment you'd put in a highlight reel?" Drill to specifics: what was happening, who reacted, what did they say or do? This is raw material for `plays.md`.
2. **The stall.** "Where did you lose them — even for a minute?" The moment attention dropped, energy dipped, or the counterparty pulled back. What exactly were you doing when it happened?
3. **The surprise.** "What surprised you?" Something said, asked, or cared about that wasn't in the plan. Surprises are where the other side's real priorities leak out.

### The Vague-Answer Drilling Table

Debrief answers arrive vague because the user is tired. Never file a vague answer — convert it. Universal rows below; the domain profile adds craft-specific ones.

| They say | Ask this |
|---|---|
| "It went well" | "What's the single moment that made it go well — what was happening right then?" |
| "They seemed into it" | "Who specifically, and at which part? What did they do or say?" |
| "It was fine, pretty standard" | "If you could re-run one section tomorrow, which one — and which would you cut?" |
| "The usual pushback" | "Give me the exact sentence the most skeptical person said." |
| "I fumbled a bit" | "Where exactly were you when it happened, and what were you trying to get to?" |
| "I think it landed" | "What did they say or do at the end that tells you that? Exact words if you can." |

## Phase 2 — Friction & Unknowns (3 minutes)

1. **Friction raised.** For each friction moment (the domain profile defines what counts — objections, hard questions, pressure tactics, confusion): their words as close to verbatim as memory allows, how the user responded, and a verdict — **landed / neutral / lost them**. The verdict is what builds the playbook's track record.
2. **What the user couldn't answer or handle.** Each becomes an open item with an owner and a date. Pre-Game surfaces these before the next meeting with this counterparty.

Cross-check `playbook.md` while doing this: recurring friction → update its track record; new friction → mint an FR-NN block.

## Phase 3 — The Score (2 minutes)

Ask for all five numbers in one exchange — Open, Thread, Command, Turn, Close — 1 to 5, using the domain profile's anchors. Then one follow-up only: **"One line — why the lowest score?"** Don't litigate the other four.

## Phase 4 — The One Thing (90 seconds)

1. **Check the streak first.** Pull the One Thing from the previous entry: "Last time you committed to [X]. Did it happen?" Record yes/no. No judgment either way — the streak data does the talking in Film Review.
2. **Set the next one.** "One thing you'll do differently next time — just one." If they offer three, make them pick. Usually the lowest score points at it.

## Filing the Entry

Append to the TOP of `tape-log.md` in this exact format:

```markdown
## GT-YYYYMMDD-NN — [Codename / event] — #[n]
- **Date:** YYYY-MM-DD | **Context:** [domain context fields] | **Stakes:** [stage]
- **Ran:** [what was performed / covered]
- **Score:** O:[n] T:[n] Cm:[n] Tu:[n] Cl:[n] → [total]/25 *(lowest: [slot] — [one-line reason])*

**Highlight:** [the moment, specific — what was happening + the reaction]
**Stall:** [where they were lost + what was happening]
**Surprise:** [what wasn't in the plan]

**Friction:** FR-NN [landed/neutral/lost], FR-NN [verdict] *(new: FR-NN "[short label]")*
**Open items:** [item — due date] *(or "none")*

**Prev One Thing:** [what it was] — [DONE / MISSED]
**One Thing next:** [the single commitment]
```

Then update `playbook.md` (track records + any new blocks) and check `plays.md`: any highlight moment now landed 2+ times across entries gets promoted to a PLAY-NN block. Finish with the update loop from SKILL.md — regenerate complete files, present them, one line on what to replace.

### Friction block format (playbook.md)

```markdown
## FR-NN — [short label]
- **The friction:** "[their words / the pressure moment]"
- **Raised in:** [contexts it's come from, using the domain's context fields]
- **Seen:** [n] times — first: GT-XX | **Landed responses:** [n]/[n]
- **Best response:** [the framing/move that worked, one or two lines]
- **Avoid:** [what didn't land] *(omit until known)*
```

### Play block format (plays.md)

```markdown
## PLAY-NN — [name]
- **Run it when:** [context + moment in the performance]
- **The move:** [what to do and say, 2–3 lines]
- **Record:** [n] runs, [n] landed — GT-XX, GT-XX
- **Context notes:** [where it over/under-performs, only once the record shows it — e.g., "3/3 with practitioner audiences; 0/2 with exec-only rooms"]
```

## The Lightning Debrief (3 minutes, fallback only)

When there's genuinely no time, ask exactly three things: (1) the highlight moment, (2) friction + verdicts, (3) the One Thing (after checking the streak). File a thin entry marked `*(lightning)*`, skip the score. Use sparingly — three lightning entries in a row is a signal to raise in the next full debrief.
