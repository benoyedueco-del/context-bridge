# Context Bridge™ — Interrogation Prompt
**Version:** 1.0
**Use this when:** You are the receiving AI. You have read the Context Bridge document(s). You want to close the last 10% gap that no structured document can fully capture.

---

## The Last 10% Problem

Every Context Bridge document, no matter how thorough, captures approximately 85–95% of a project's working intelligence. The gap is not a flaw in the protocol. It is structural.

What gets lost is not decisions or architecture — those are captured. What gets lost is **operational micro-knowledge**: the things a colleague knows from working alongside someone for months but would never think to write in a formal handoff document.

This prompt closes that gap. Run it against the exporting AI before the handoff is complete.

---

## When To Run This

After you have:
1. Received and read all Context Bridge documents
2. Run the Receiving AI Primer and confirmed your understanding
3. Identified gaps, ambiguities, or uncertainties in what you received

Before you:
1. Begin active work on the project
2. Send any EIPs or task instructions to execution tools
3. Make any decisions based on numbers or system states you cannot verify

---

## Instructions

Give this prompt to the **exporting AI** — the one you are taking over from. It still has session memory of the operational details that didn't make it into the bridge document.

---

```
I am the receiving AI taking over this project. I have read your Context Bridge document completely.

Before the handoff is final, I need to close the last 10% gap — the operational micro-knowledge that structured documents cannot fully capture.

Please answer these questions directly and specifically. Do not repeat what is already in the bridge document. I need what isn't there.

============================================================
INTERROGATION PROTOCOL — LAST 10% GAP CLOSURE
============================================================

QUESTION 1 — KNOWN FAILURE CASES
What specific sources, sites, APIs, systems, or tools were attempted during this project and failed?
For each:
  - What was attempted
  - Why it failed (bot protection, rate limit, restructured page, access denied, inconsistent data)
  - Whether it was resolved, worked around, or is still an open trap
  - Whether the receiving AI should attempt it again or avoid it entirely

Do not list general categories. Name the specific cases.

---

QUESTION 2 — NUMBER PROVENANCE
For every significant metric, count, baseline, or threshold referenced in the bridge document:
  - Where did this number actually come from?
  - Is it from an early version/estimate, or from actual system output?
  - Has it been validated, or is it an assumption that was never challenged?
  - Would it still be valid under the current version of the system or rules?

This matters because a number from V1 may not port into V2 without recalculation.

---

QUESTION 3 — ID AND MAPPING RELATIONSHIPS
For every system, dataset, or module that references IDs:
  - Do IDs from System A map cleanly to IDs in System B?
  - Are they completely separate ID systems requiring fuzzy matching or manual mapping?
  - Are there known orphaned records, mismatches, or ID collisions?
  - Has any mapping work been done, or does it still need to be built?

---

QUESTION 4 — CODE VS DOCUMENT EXISTENCE
For every system, algorithm, schema, feature, or module referenced in the bridge document:
  - Does it exist as RUNNING CODE or only as a design document / description?
  - If it exists as code — where does it live and what is its current state?
  - If it exists only as a document — has it ever been implemented or tested?

The receiving AI must not treat a paper design as implemented infrastructure.

---

QUESTION 5 — VERBAL DECISIONS NEVER WRITTEN DOWN
What choices, constraints, or directions were established verbally in conversation but never became a formal entry in any document?
  - Things the human said once in passing that became an implicit constraint
  - Scope decisions made informally
  - Preferences expressed but never documented as rules
  - Anything you acted on but never wrote down

---

QUESTION 6 — EXECUTION TOOL QUIRKS
If execution tools (Manus, code runners, scrapers, or others) were used:
  - Are there session limits, file size constraints, or sequencing requirements?
  - Are there tasks that must be run in a specific order for non-obvious reasons?
  - Are there tool-specific failure modes the receiving AI should know about?
  - Are there tasks that have been attempted multiple times and consistently fail?

---

QUESTION 7 — WHAT WOULD YOU WARN ME ABOUT
If you were briefing a replacement colleague — not an AI — what would you pull them aside and say quietly before they touched the project?

These are the things that don't fit in a formal document but matter for execution.
Answer this question even if you think everything important is already in the bridge.
There is always something.

---

QUESTION 8 — WHAT SHOULD THE HUMAN CONFIRM BEFORE I ACT
Based on the full project history — not just the bridge document — what are the 3-5 things the human should personally verify or confirm before I begin active work?

These are things where your memory says one thing but you're not certain it's still current, or where a decision was made but you're not sure the human still wants it.

---

QUESTION 9 — UNREAD FILE ARTIFACTS IN STORAGE
What files, datasets, exports, or outputs were generated during this project
that were NEVER printed or quoted in any conversation message?

These exist only in storage systems — S3 buckets, databases, local file systems,
tool output directories. No AI in the receiving chain has ever seen their contents.
The receiving AI is completely blind to them unless you name them here.

For each unread artifact:
  - File name or identifier
  - What it contains (schema, record count, field names if known)
  - Where it lives (storage system, path, bucket name)
  - How to access it (command, API call, direct download)
  - Whether you are certain it exists or only believe it does
  - Whether it is the current/final version or may have been superseded

This question is the most commonly skipped. It is not optional.
The receiving AI cannot ask Manus or any execution tool to work with data
it does not know exists.

============================================================
FORMAT YOUR ANSWERS
============================================================

Answer each question with a number header.
Be specific — name actual cases, actual numbers, actual systems.
If a question has no answer, say "None identified" — do not skip it.
Do not repeat content already in the bridge document.
This is the gap-fill. Fill the gaps.

============================================================
```

---

## How To Use the Answers

When the exporting AI responds:

**Immediately add to MASTER_CONTEXT.md** — any answer that changes your understanding of the project state, system existence, or valid numbers.

**Flag for human confirmation** — any answer tagged [UNCERTAIN] or where the exporting AI expresses low confidence. Do not act on uncertain operational intelligence.

**Update your cold-start understanding** — revise Section 10 of the bridge in your working memory based on what you learned.

**Do not begin execution** until Question 4 (code vs document) and Question 9 (unread file artifacts) are fully answered. The most dangerous assumptions a receiving AI makes are treating a described system as a built one and treating a referenced dataset as visible when it has never been surfaced.

---

## The Human's 5 Questions

After running the Interrogation Prompt against the exporting AI, ask the human these 5 questions:

```
Before I begin active work, I need you to confirm five things:

1. [Most critical system or algorithm] — does this exist as running code right now,
   or is it still in design/document form?

2. [Most recent significant number] — is this from actual system output,
   or from an earlier estimate not yet validated?

3. [Most recent decision] — is this still the direction you want,
   or has your thinking changed since this was decided?

4. Are there any constraints, changes, or decisions made outside AI conversations
   — in emails, calls, or with other people — that I should know?

5. What is the single most important thing you want me to get right
   in the first session?
```

---

## The Interrogation Prompt in the Workflow

```
Context Bridge produced (by exporting AI)
          ↓
Receiving AI reads bridge + runs Primer
          ↓
Receiving AI runs Interrogation Prompt (against exporting AI)
          ↓
Receiving AI asks Human's 5 Questions
          ↓
Gaps closed. Human confirms critical facts.
          ↓
Receiving AI begins active work.
          ↓
Full handoff complete.
```

---

## The Four Prompts — Complete Reference

| Prompt | When | Direction |
|--------|------|-----------|
| **Main** | End of session | Human → Exporting AI |
| **Sync** | Merging multiple bridges | Human → Receiving AI |
| **Primer** | Starting new session | Human → Receiving AI |
| **Interrogation** | Closing the last 10% | Receiving AI → Exporting AI + Human |

---

*Context Bridge™ v3.0 — Because no project should die in a context window.*
