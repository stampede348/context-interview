---
name: game-tape
description: "A performance debrief system for anyone whose work involves a repeated, high-stakes performance — sales demos, investor pitches, job interviews, keynotes and talks, classes and training sessions, negotiations, auditions, client meetings, coaching sessions. Runs a 10-minute structured debrief after each performance, builds a persistent playbook of what works, preps a one-page card before the next one, and surfaces patterns across performances. Use whenever the user finishes any performance ('just got out of the interview', 'the demo went badly', 'gave my talk today', 'how do you think I did'), wants a debrief, retro, or post-mortem, wants prep ('prep me', 'pre-game', 'I have a pitch tomorrow'), asks what patterns are showing up ('film review', 'game tape'), or asks whether this system can adapt to their profession or craft. Also trigger on any mention of the files tape-log.md, playbook.md, plays.md, or tape-domain.md."
---

# Game Tape

Athletes get elite by reviewing film. Most professionals never do. A sales engineer runs demo #40 no better than demo #12; a candidate walks out of an interview and loses every signal the room gave them; a speaker gives the same talk with the same flat middle for years. The intelligence each performance generates — what landed, where the room was lost, which hard question keeps recurring — evaporates in the parking lot.

Game Tape is the film room. It runs a tight post-performance debrief, files what happened into a persistent library, and pays it back before the next performance. Consistency doesn't come from more knowledge — it comes from reviewing the same tape, scoring the same dimensions, and changing one thing at a time.

## The System in One Paragraph

Three markdown files live in a Claude Project's knowledge. After every performance, a debrief (10 minutes, hard cap) becomes a structured log entry, updates a living playbook of recurring friction and tested responses, and promotes moments that landed into a plays library. Before the next performance, Pre-Game mode turns that library into a one-page card. Every ~5 performances, Film Review analyzes the log for patterns invisible from inside any single performance. A **domain profile** adapts the whole engine — vocabulary, score anchors, debrief questions — to the user's actual craft. No database, no code. The files ARE the memory.

## The Three Files

| File | Role | Rule of thumb |
|---|---|---|
| `tape-log.md` | One structured entry per performance. The film archive. | Newest at the TOP. Never delete entries. |
| `playbook.md` | Recurring friction — objections, hard questions, pressure moments — with the responses that actually work, and a track record. | One block per distinct friction point. Update the record every recurrence. |
| `plays.md` | Moves that consistently land, and exactly when to run them. | A play needs 2+ landed runs before promotion. |

**IDs:** log entries `GT-YYYYMMDD-NN`, friction blocks `FR-NN`, plays `PLAY-NN`. Permanent — they're what makes cross-referencing work.

## Domains: How the Engine Adapts

The engine is universal; the domain profile makes it specific. Resolve the domain in this order — never run a debrief without one loaded:

1. **Custom profile in project knowledge?** If `tape-domain.md` exists in project context, it wins. Read it.
2. **Bundled profile matches?** Read the matching file from `references/domains/`:

   | User's craft | Profile |
   |---|---|
   | Sales demos, presales, founder/investor pitches | `demos-pitches.md` |
   | Job interviews (candidate side) | `interviews.md` |
   | Talks, keynotes, webinars, panels | `speaking.md` |
   | Teaching, corporate training, workshops, coaching | `teaching-training.md` |
   | Negotiations, high-stakes deal conversations | `negotiation.md` |

3. **Nothing fits?** Run the domain generator: read `references/domains/custom-domain.md` and follow it. It interviews the user about their craft and produces a `tape-domain.md` for their project knowledge. This is how the system serves a trial lawyer, a wedding DJ, a stand-up comic, or an ER charge nurse without a prebuilt profile.

The domain profile supplies: vocabulary, the context fields that segment performances, the 1/5 anchors for all five score dimensions, domain phrasing for the debrief questions, extra drilling-table rows, and what "friction" and "landed" look like in that craft. Everything else — modes, files, rules, formats — is this engine and never changes.

## First-Run Setup

When the three data files aren't in context, don't improvise into the void — an entry that isn't filed doesn't exist. Walk the user through this once:

1. **Resolve the domain** (order above). If generating a custom one, do that first — it produces `tape-domain.md`.
2. **Best home: a dedicated Claude Project.** Recommend one just for Game Tape — mixing these files into a project with lots of other knowledge dilutes both. Generate the three starter files from `assets/` and have the user add them (plus any `tape-domain.md`) to the project's knowledge.
3. **No Projects available?** The system still works: the user keeps the files locally and attaches them at the start of each session. Same files, same loop — just say so plainly rather than presenting Projects as a requirement.
4. **Codename mapping stays out.** The user keeps the codename→real-name mapping wherever they already keep private notes (their head, their CRM). Never offer to store it in the files — that would defeat the point of codenames.

Then offer to file their most recent performance as GT-01 on the spot. A system with one real entry survives; a system set up "for next time" usually doesn't get a next time.

## Pick the Mode

Decide from context — ask only if genuinely ambiguous:

| Signal | Mode |
|---|---|
| Performance just happened ("just got out", "debrief", "it went...") | **Debrief** |
| Performance coming up ("prep me", "tomorrow", user shares prep context) | **Pre-Game** |
| "Patterns", "film review", or the log just hit a multiple of 5 | **Film Review** |

---

## Mode 1: Debrief

**Read `references/debrief-protocol.md` and run it** with the domain profile loaded. The protocol is the question sequence, the drilling table for vague answers, and the exact filing formats. Don't wing it from memory — the ordering is deliberate.

Ground rules that govern every debrief:

- **One question at a time.** This is a conversation, not a form. A form gets abandoned by performance #3.
- **Mine the dump first.** Real users often open with a paragraph of how it went before any question is asked. That narrative IS debrief data — extract everything it already answers, then ask only the questions it didn't. Marching someone through questions they've already answered is how the 10-minute cap gets blown.
- **Never accept vague.** "It went well" is not data. Drill to the specific moment — what was happening, who reacted, what they said. The drilling table exists for exactly this.
- **10 minutes, hard cap.** If time is short, run the Lightning Debrief (protocol, bottom section) — 3 questions, 3 minutes. A thin entry beats no entry.
- **Codename first.** Assign the counterparty/event a codename before anything else (see Non-Negotiable Rules).
- **End with the update loop.** A debrief that doesn't produce updated files taught the system nothing.

## Mode 2: Pre-Game

Input: whatever the user provides. Ask only for what's missing AND would change the card.

1. **Check the debt.** Scan `tape-log.md` — does the most recent performance have an entry? If not, stop and run a Lightning Debrief first. Debrief-before-prep is how the loop stays honest. Surface any open items owed to this counterparty.
2. **Pull the plays.** From `plays.md`, the 2–3 plays whose context matches this performance — use the domain's context fields, not just topic. A play with a strong record in the wrong context doesn't make the card. If nothing matches yet, say so and offer the closest analog, flagged as untested here.
3. **Pull the friction.** From `playbook.md`, the 3–4 friction points whose "raised in" contexts match, each with its best-tested response.
   - **Empty or thin library?** The first Pre-Game still earns its keep: build the friction section from the domain profile's friction categories as hypotheses, clearly flagged as untested ("expect some version of: ..."), and skip the plays section rather than inventing plays. The card gets sharper with every debrief — say so.
4. **Pull the One Thing.** The active commitment from the latest entry. This performance is where it gets executed.

Output — always this card, one page max:

```
PRE-GAME — [Codename / event] — [date]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
CONTEXT:      [domain context fields]
OPEN ITEMS:   [owed follow-ups / carried commitments, or "none"]

RUN THESE PLAYS:
  • PLAY-NN [name] — when: [trigger moment]

EXPECT THIS FRICTION:
  • FR-NN "[friction point]" → [best response, one line]

THE ONE THING: [the single improvement being executed]
```

## Mode 3: Film Review

**Read `references/film-review.md` and follow it.** Trigger proactively when the log hits a multiple of 5 ("That's #10 filed — want the film review?"), or whenever asked.

---

## The Five Dimensions

Every debrief scores the same five dimensions, 1–5. The slots are universal; the domain profile supplies what 1 and 5 look like in that craft. Same rubric every time — you can't trend what you don't measure consistently.

| Slot | What it measures, in any craft |
|---|---|
| **The Open** | How the performance started. Did the first minutes frame everything, or did you start cold? |
| **The Thread** | Structure and story. Did every part serve one spine, or was it a sequence of parts? |
| **Command** | Craft execution — the technical skill of the domain, performed under pressure. |
| **The Turn** | Friction handling. What happened when resistance, hard questions, or surprises hit. |
| **The Close** | How it ended. Was the outcome secured, or did it trail off? |

Scores are self-reported and that's fine — the value is the trend line, not any single number. Ask for a one-line reason on the lowest score only; don't litigate all five.

## Non-Negotiable Rules

1. **Codenames only.** Names of companies, counterparties, and people never enter the files. Assign a codename at first debrief (any scheme — colors, birds, mountains) and record nothing that couldn't be posted publicly. Privacy rule first, and it's also what makes the library safe to keep and share.
2. **Never fabricate a pattern.** Two occurrences is a coincidence; three is a pattern worth naming. "No pattern yet" is always an acceptable finding and a more valuable one than a forced insight.
3. **Debrief before the next prep.** Pre-Game checks the log first. Skipping debriefs is how the system quietly dies; the skill enforces the sequence so willpower doesn't have to.
4. **One Thing means one.** Each debrief ends with a single behavioral change. A list of five improvements produces zero. Track whether the last One Thing happened — the streak is reviewed in Film Review.
5. **The files are the truth.** If conversation memory and the files disagree, the files win.
6. **Under 10 minutes or it dies.** The debrief's enemy isn't quality, it's friction. Any question that doesn't change what gets filed gets cut.
7. **No domain, no debrief.** Resolve or generate the domain profile before filing anything. Generic entries scored against no anchors are noise dressed as data.

## The Update Loop (how persistence works)

Claude can't write directly into project knowledge, so every change follows the same loop:

1. Read the current files from project context.
2. Produce the **complete updated file(s)** — never fragments or diffs — with create_file, and present them with present_files.
3. Tell the user exactly which file(s) to replace in project knowledge, in one line.

If a debrief produces an entry but not the regenerated files, the system learned nothing. Never skip step 2. The same loop persists a generated `tape-domain.md`.

## House Style

- Lead with the answer or the card — context after, never before.
- Short questions during debriefs. The user just finished performing; their energy is spent.
- Plain words. "The room went quiet when the pricing slide came up" beats any amount of analysis-speak.
- Cite entries by ID (GT-20260719-01 on first mention, GT-01 after).
