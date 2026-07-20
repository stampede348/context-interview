# Film Review

The pattern analysis a single performance can never show. Run every ~5 log entries or on request. Minimum 3 entries before claiming any pattern — below that, say so and stop.

## What to Analyze

Work through these six lenses against `tape-log.md`, `playbook.md`, and `plays.md`. Report only what the entries actually support, with IDs as evidence.

1. **Score trends.** Per-dimension across entries — excluding lightning entries, which carry no scores; note how many were excluded. The interesting findings: the slot that's consistently lowest (that's the skill gap), the slot with the widest swing (that's the consistency gap — often more important), and any movement since a One Thing targeted it.
2. **Stall patterns.** Do stalls cluster? Same section of the performance, same counterparty type, same point in time (e.g., always ~40 minutes in)? A stall that recurs across different counterparties is a script problem, not an audience problem.
3. **Friction movement.** Which friction points are rising in frequency? Which have a weak landed-rate despite repeated attempts (the response needs rework)? Any friction that stopped appearing after a response or play changed?
4. **The One Thing streak.** Completion rate on commitments. A low streak isn't a discipline lecture — it usually means the One Things are too big. Recommend smaller ones.
5. **Play performance.** Hit rates from `plays.md`. Promote highlight moments with 2+ landed runs that haven't been minted yet. Flag any play under 50% landed for retirement or rework — a play that stopped working is stale intel.
6. **Context splits.** Do scores, stalls, or play results diverge across the domain's context fields? This is where "it isn't working" becomes "it isn't working *in final-round panels*" or "*with exec-only rooms*." Guardrail: never split a context with fewer than 3 entries in it — with small numbers, report "watching this context" instead of a finding, and never retire a play for failing in a context it was never built for; note the mismatch instead.

## Output Format

Always this card, then stop — no essay after it:

```
FILM REVIEW — entries GT-XX through GT-XX ([n] performances)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
HEADLINE:      [the single most important finding, one sentence]

SCORE TREND:   [avg total, direction] | Weakest: [slot] | Widest swing: [slot]

PATTERNS (evidence required):
  1. [pattern] — GT-XX, GT-XX, GT-XX
  2. [pattern] — [IDs]
  *(or: "No new patterns yet — [n] more entries needed to say more.")*

FRICTION WATCH:   [rising / weak-response friction, by FR-NN]
PLAYS:            [promote: ... | retire/rework: ... | or "no changes"]
ONE THING STREAK: [n]/[n] completed

THE CALL: [one specific recommendation for the next 5 performances]
```

## Honesty Rules

- Every pattern cites entry IDs. A pattern with no evidence line doesn't go in the card.
- Two occurrences is a coincidence. Say "watching this" rather than naming it a pattern.
- Scores are self-reported; treat them as directional, and say so if the user starts optimizing the number instead of the performance.
- If the log is thin or full of lightning entries, the finding IS the thinness — name it and recommend fuller debriefs before deeper analysis.
