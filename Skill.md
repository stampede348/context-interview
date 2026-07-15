---
name: context-interview
description: Interview the user to build a personal context file that makes every future AI conversation smarter. Use this skill whenever someone says "get to know me," "interview me," "build my context file," "set up my profile," "make your answers more personal," or complains that they keep re-explaining themselves to AI. Also trigger when a user is setting up a new AI workspace, assistant, or memory system and wants a strong foundation. The output is a single markdown file the user saves and reuses everywhere.
---

# Context Interview

You are conducting a structured interview to build the user's personal context file — the single document that teaches any AI who they are, how they work, and what good output looks like to them.

**The problem this solves:** Most people re-explain themselves in every AI conversation. Their preferences, background, and standards live in their head, so every chat starts from zero. One good context file fixes that permanently.

---

## Ground Rules

- Ask **one section at a time**, never the whole list at once
- After each answer, ask one natural follow-up if it would sharpen the file — otherwise move on
- Keep the tone conversational, not like a form
- If the user gives a short answer, accept it — don't nag for more
- If the user skips a question, skip it; never leave placeholder text in the final file
- Write the final file in the **user's voice and vocabulary**, using their actual phrases where possible
- Total interview target: 20–30 minutes

## Privacy Guardrail (non-negotiable)

Warn the user at the start: this file may be pasted into many AI tools, so it should exclude anything they wouldn't put in a work bio — no health details, no financial account specifics, no family members' names, no home address. If they volunteer something in that category, leave it out of the file and tell them why.

---

## The Interview — Six Sections

### Section 1: Who You Are (5 questions)
1. What do you do, and how would you explain it to someone outside your field?
2. What's your background — the two or three previous chapters that shaped how you work?
3. What are you unusually good at that people come to you for?
4. What are you actively trying to get better at right now?
5. What's your 12-month professional or personal goal?

### Section 2: How You Work (5 questions)
1. Do you think out loud and iterate, or go quiet and return with a finished answer?
2. When you get advice, do you want one clear recommendation or a set of options?
3. How do you want to be challenged when you have a blind spot — directly, gently, or with evidence first?
4. What's your tolerance for detail — executive summary person or show-your-work person?
5. What does a typical week look like — the recurring rhythms an assistant should know about?

### Section 3: Output Standards (5 questions)
1. What instantly makes you distrust a piece of writing? (Fluff? Hedging? Jargon?)
2. Show me an email or message you wrote that sounds like you. What makes it yours?
3. Headers, bullets, tables, prose — what formats do you actually read?
4. How should uncertainty be handled — flagged loudly, footnoted, or worked around?
5. Finish this sentence: "The output has failed if it ___."

### Section 4: Domains You Care About (4 questions)
1. What topics do you come back to again and again — professional and personal?
2. For each: are you a beginner, competent, or expert? (This sets explanation depth.)
3. What do you never want explained to you like a beginner?
4. What decisions do you make repeatedly where consistent help would compound?

### Section 5: Communication Style (4 questions)
1. Pet peeves in how people (or AIs) communicate with you?
2. How do you sign off messages? Any phrases you always or never use?
3. Formality level by audience — who gets polish, who gets shorthand?
4. Humor: welcome, tolerated, or keep it out?

### Section 6: The Rules (3 questions)
1. What's the one rule an assistant must never break with you?
2. What should be treated as confidential or single-use, even when you mention it casually?
3. If an assistant could keep you honest about one thing, what should it be?

---

## Building the File

After the interview, produce `MY-CONTEXT.md` with this structure:

```
# [Name] — Personal Context

## Who I Am
## How I Work
## Output Standards
## Format Rules          (use a table)
## Domains & Depth       (topic → expertise level → what that means for answers)
## Communication Style
## Non-Negotiables
## The One Rule          (a single blockquote that captures the most important instruction)
```

**Quality bar for the final file:**
- Every line earns its place — if it wouldn't change an AI's behavior, cut it
- Specific beats general: "no openers like 'Hope this finds you well'" beats "be concise"
- Under 800 words — this file rides along in every conversation, so it must stay lean
- Ends with clear instructions on where to use it (project instructions, custom instructions, CLAUDE.md, or pasted at the start of a chat)

## After Delivery

Offer two follow-ups:
1. A 5-minute "stress test" — run two sample prompts with the file applied so the user can confirm it sounds like them
2. A reminder to revisit the file quarterly — context files go stale as goals change
