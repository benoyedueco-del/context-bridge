# Context Bridge™ — Complete Workflow Protocol
**Version:** 3.0
**This document is the authoritative guide to running Context Bridge correctly.**

A Context Bridge document is not the protocol. It is one artifact produced by the protocol. The protocol is a six-step workflow. Skipping any step reduces reliability. The steps exist because different types of intelligence require different extraction mechanisms.

---

## The Three Categories of Lost Intelligence

Before running the workflow, understand what you are trying to capture and why each requires a different mechanism:

**Category 1 — Decisions, architecture, rules, and state**
What was built, what was decided, what was rejected, what the current state is.
Captured by: Main Prompt Sections 1–16.
Reliability: High. This is what AIs naturally recall and organize.

**Category 2 — Operational micro-knowledge**
Execution-level reality that never rose to the level of a formal decision.
"Kingston returns 404s." "Dundee needs the `/entry-requirements` subpage."
"Manchester's course list is JS-rendered." Things a colleague knows from being in the trenches.
Captured by: Section 17 + Interrogation Prompt Questions 1–8.
Reliability: Medium without interrogation. High with it.

**Category 3 — File artifacts never surfaced in conversation**
Data files, datasets, exports, or outputs generated during the project that were never printed or quoted in any message. They exist only inside storage systems. No AI in the chain ever saw their contents as text.
Captured by: Section 12 (artifact registration) + Interrogation Prompt Question 9.
Reliability: Zero without explicit registration. High once registered.

**The rule that governs all three:**
No prompt can extract what was never said. Category 3 gaps are not fixed by better prompting — they are fixed by registering that the artifact exists and where it lives.

---

## The Six-Step Workflow

### Step 0 — Forensic Scan
**Who runs it:** The exporting AI, before producing any output.
**What it does:** Reads the entire conversation history systematically — not from memory, but as a deliberate top-to-bottom scan.

The exporting AI must flag, before writing anything:
- Every message where a decision was made
- Every message where a file was uploaded and what was found in it
- Every message where something failed or produced a surprising result
- Every metric, count, or baseline number that was stated
- Every rule, constraint, or non-negotiable that was set
- Every file, dataset, or output that was generated (whether or not it appeared as text)

This is the difference between a detective answering from memory and one who re-reads the entire case file before writing the report. The output of Step 0 is not visible to you — it is the internal preparation that makes Sections 1–18 accurate.

**Why it is Step 0 and not Step 1:**
Every other improvement to the protocol is marginal if the AI producing the bridge is working from selective recall. The forensic scan is the foundation. It is mandatory.

---

### Step 1 — Main Prompt
**Who runs it:** You, with the exporting AI.
**What it produces:** The Context Bridge document (18 sections).
**File:** `prompts/CONTEXT_BRIDGE_MAIN.md`

Run this at:
- The end of any significant session
- Before switching to a different AI tool
- When a conversation is getting long (checkpoint)
- At any major milestone

Name the output:
```
CONTEXT_BRIDGE_[PROJECT]_[YYYY-MM-DD].md
```

**Do not skip Section 12 or Section 17.** These capture Category 2 and Category 3 gaps. They feel informal compared to architecture sections. They are not. They are where the most operationally dangerous intelligence lives.

---

### Step 2 — Sync Prompt (if multi-AI)
**Who runs it:** You, with the receiving AI.
**What it produces:** A merged intelligence report with confirmed facts, detected conflicts, coverage map.
**File:** `prompts/CONTEXT_BRIDGE_SYNC.md`

Run this when:
- Multiple AIs have worked on the same project
- You have bridges from more than one AI to reconcile

The sync prompt detects where bridges agree (high confidence), where they conflict (flag for human resolution), and what no bridge covered (gaps).

**Do not skip conflict resolution.** When two bridges disagree on a decision or system state, do not let the receiving AI silently choose one. Surface the conflict. Resolve it with the human.

---

### Step 3 — Receiving AI Primer
**Who runs it:** You, at the start of a new conversation with a new AI.
**What it produces:** A confirmed understanding from the receiving AI before work begins.
**File:** `prompts/CONTEXT_BRIDGE_PRIMER.md`

The receiving AI must confirm:
1. What it understands the project to be
2. What it understands the current state to be
3. What it understands the immediate next action to be
4. Any conflicts or uncertainties it wants resolved

**Do not let the receiving AI skip confirmation and start working.** If it does, redirect it: "Stop — confirm your understanding first as instructed."

---

### Step 4 — Interrogation Prompt
**Who runs it:** The receiving AI, against the exporting AI.
**What it produces:** Answers to 9 targeted questions that close Category 2 and Category 3 gaps.
**File:** `prompts/CONTEXT_BRIDGE_INTERROGATION.md`

This step is mandatory, not optional. Every bridge leaves a gap. The interrogation closes it.

The 9 questions cover:
1. Known failure cases and problem sites
2. Number provenance (estimate vs actual output)
3. ID and mapping relationships between systems
4. Code vs document existence
5. Verbal decisions never written down
6. Execution tool quirks
7. The "pull aside" warning — what a colleague would say quietly
8. What the human must confirm before work begins
9. Unread file artifacts in storage (Category 3)

**Question 9 is the most commonly missed.** It surfaces the files that exist only in storage systems and were never quoted in any conversation. The university master index. The processed dataset. The export file. These are invisible to every AI unless named here.

---

### Step 5 — Human Confirmation
**Who runs it:** You, after reading the interrogation answers.
**What it produces:** Verified ground truth on the five highest-risk items.

Ask yourself — or have the receiving AI ask you — these five questions:

1. **Code vs document:** For the most critical system or algorithm — does it exist as running code right now, or only as a design document?
2. **Number source:** For the most significant metric — is it from actual system output, or from an earlier estimate never validated?
3. **Current direction:** For the most recent major decision — is this still the direction you want, or has your thinking changed?
4. **Out-of-AI decisions:** Are there any constraints, changes, or decisions made outside AI conversations (in emails, calls, with other people) that the receiving AI should know?
5. **First priority:** What is the single most important thing to get right in the first session?

**Do not skip this step on long-running projects.** The exporting AI's memory of what you want may lag behind your actual current thinking. This step synchronizes them.

---

### Step 6 — MASTER_CONTEXT Update
**Who runs it:** You.
**What it produces:** An updated MASTER_CONTEXT.md — the human-validated ground truth document.
**File:** `docs/MASTER_CONTEXT_SCHEMA.md`

After Steps 0–5 are complete, extract the confirmed, validated intelligence and incorporate it into MASTER_CONTEXT.md.

The rule: **MASTER_CONTEXT.md is always right. Bridges feed it. When they conflict, MASTER_CONTEXT.md wins.**

Update MASTER_CONTEXT after:
- Every session that produces a new decision
- Every session that reveals a new open problem or failure case
- Every step where a previously uncertain item is confirmed
- Every time a locked decision changes

**Do not put unverified AI inferences in MASTER_CONTEXT.md.** Items tagged `[INFERRED]` or `[UNCERTAIN]` stay in bridge documents until the human confirms them.

---

## Checkpoint Discipline

For long-running projects, run the Main Prompt (Step 1) periodically — not just at handoff.

**Recommended checkpoints:**
- Every 20–30 significant exchanges
- Before any major execution wave (before sending EIPs to Manus, before a major build sprint)
- Before any planned pause in the project
- Immediately after any significant failure or unexpected result

**Why periodic checkpoints matter:**
A bridge produced at month 2 captures things a bridge produced at month 6 cannot recover. Early-session context compresses into the background as recent sessions dominate recall. Periodic bridges create a chain of evidence rather than a single end-of-project dump.

---

## The Validation Test

The strongest quality test for a Context Bridge is the comparison test:

1. Export the full conversation (if your platform allows it)
2. Give both the bridge document and the full conversation to a fresh AI
3. Ask: "Does the bridge accurately represent the most important intelligence in this conversation? What is missing or wrong?"

This is not a routine step — it requires access to the full conversation export. But for long, high-stakes projects, it is the most reliable way to find what the bridge missed. The gaps it surfaces go directly into Section 17 and the Interrogation Prompt.

---

## The Complete Four-Prompt Reference

| Prompt | Step | Direction | Purpose |
|--------|------|-----------|---------|
| Main Prompt | 1 | You → Exporting AI | Produce the bridge document |
| Sync Prompt | 2 | You → Receiving AI | Merge multiple bridges |
| Receiving AI Primer | 3 | You → Receiving AI | Confirm understanding before work |
| Interrogation Prompt | 4 | Receiving AI → Exporting AI | Close the last 10% gap |

---

## What Context Bridge Cannot Do

No workflow closes every gap. Be honest about what remains structurally impossible:

- It cannot transfer the content of files that were never quoted in conversation. It can only register that they exist and where they live.
- It cannot transfer the full reasoning chain behind decisions made early in a project if those sessions are no longer in context.
- It cannot replace human judgment on whether the bridge accurately reflects current intent. Step 5 exists for this reason.
- It cannot be fully autonomous. The human is always the integrity layer.

For a complete treatment of limitations, see `docs/LIMITATIONS.md`.

---

*Context Bridge™ v3.0 — Because no project should die in a context window.*
