# Context Bridge™ — Main Export Prompt
**Version:** 2.0
**Use this when:** You are leaving an AI conversation and want to transfer complete project intelligence to any other AI.

---

## Instructions

Copy everything inside the code block below. Paste it into the AI you are leaving. Download the document it produces.

---

```
You are about to produce a CONTEXT BRIDGE™ document — a structured intelligence transfer designed to let any AI pick up this project exactly where we are leaving off.

This is NOT a conversation summary.
This is NOT a transcript.
This is a classified, structured, priority-tagged intelligence briefing.

The receiving AI may be a completely different model, platform, or version. It will have ZERO context about our conversation. The document you produce must give it everything it needs to continue the work without asking the human to re-explain anything.

============================================================
BEFORE YOU OUTPUT — RUN THIS INTERNAL PROTOCOL
============================================================

STEP 1 — TIMELINE RECONSTRUCTION
Sequence every session on this project chronologically.
Note where memory feels certain vs. reconstructed.

STEP 2 — CONTRIBUTION MAPPING
For each phase identify:
  - What problem existed
  - What the USER brought (direction, decisions, domain knowledge)
  - What YOU generated (code, architecture, frameworks, fixes, insights)
  - What outcome followed

STEP 3 — CRITICALITY FILTER
Classify every contribution:
  [CRITICAL]     — Project breaks or misdirects without this
  [SIGNIFICANT]  — Materially accelerated or improved the project
  [SUPPORTIVE]   — Useful but replaceable or cosmetic

STEP 4 — CONFIDENCE TAGGING
Tag every single entry with:
  [RECALLED]   — Direct session memory, high confidence
  [INFERRED]   — Reconstructed from context, moderate confidence
  [UNCERTAIN]  — Partially remembered, low confidence — flag for human review

STEP 5 — REJECTION RECOVERY
Actively try to recall:
  - Approaches tried and abandoned
  - Recommendations you made that the user rejected
  - Directions that were pivoted away from and why
  These are as important as what was kept.

============================================================
DOCUMENT STRUCTURE — FOLLOW THIS EXACTLY
============================================================

Produce a markdown document with the following sections, in this exact order.
Every section is mandatory. If a section has no content, write "None documented" — do not skip it.

---

### HEADER

- Document title: "CONTEXT BRIDGE™ — [Project Name] Intelligence Transfer"
- Exporting AI: [Your name and platform]
- Receiving AI: Any (Claude, GPT, Gemini, Manus, Copilot, or other)
- Export Date: [Today's date]
- Conversation Scope: [One-line description of what this conversation covered]
- Session Count: [Approximate number of exchanges/turns]
- Bridge Version: 2.0

---

### SECTION 1: PROJECT KERNEL

Write 3–7 sentences that capture the irreducible core of the project.

Rules:
- A stranger reading only this section should understand what the project IS
- Include: what it does, who it serves, why it matters, what breaks if it fails
- Do NOT pad with background history — only the essential identity

---

### SECTION 2: CURRENT STATE

Describe exactly where things stand RIGHT NOW. Not history. The current snapshot.

Format each item as:
[STATUS: COMPLETED / IN_PROGRESS / NOT_STARTED / BLOCKED] — description

Include:
- What has been built or completed
- What is partially done
- What has not been started
- Key metrics or progress indicators
- Any blockers or dependencies

---

### SECTION 3: ARCHITECTURE & SYSTEM STATE

Document technical and structural decisions that are LOCKED.

Mark each as: [LOCKED] or [PROVISIONAL]

Include:
- Data models, schemas, hierarchies
- Tech stack decisions
- System architecture (components and how they connect)
- Naming conventions and file/folder structures
- Version numbers or identifiers

If no technical architecture exists, describe the conceptual framework being used.

---

### SECTION 4: CRITICAL DECISIONS MADE

List every significant decision the human made.

Format:
[DATE or UNKNOWN] [USER-DECISION] [RECALLED/INFERRED] — Decision + implications

Include:
- Strategic choices (what to build, in what order)
- Policy decisions (rules, constraints, non-negotiables)
- Scope decisions (what's in, what's out)

These are NON-NEGOTIABLE for the receiving AI unless the human explicitly changes them.

---

### SECTION 5: REJECTED PATHS & PIVOTS

List approaches, tools, strategies, or ideas that were explicitly rejected or abandoned.

Format:
[DATE or UNKNOWN] [REJECTED] [RECALLED/INFERRED] — What was rejected and WHY

This section exists so the receiving AI does NOT suggest things already considered and dismissed.

---

### SECTION 6: AI CONTRIBUTIONS

List significant things YOU (the exporting AI) contributed.

Classify each as:
- [CRITICAL] — Shaped a major decision or produced a key deliverable
- [SIGNIFICANT] — Materially advanced the project
- [SUPPORTIVE] — Helpful but not load-bearing

Include: analyses, code, frameworks, recommendations, documents, problems identified.
Be specific — name the actual output, not the category.

---

### SECTION 7: WHAT FAILED OR SURPRISED

Document things that went wrong, didn't work as expected, or produced surprising results.

Format:
[DATE or UNKNOWN] [FAILURE/SURPRISE] — What happened, why, what was learned

Critical for preventing the receiving AI from repeating mistakes.

---

### SECTION 8: OPEN PROBLEMS

List unresolved issues, pending decisions, and known gaps.

Format:
[PRIORITY: CRITICAL / HIGH / MEDIUM / LOW] — Description

Include:
- Technical problems not yet solved
- Decisions the human hasn't made yet
- Dependencies on external inputs
- Known risks

---

### SECTION 9: NON-NEGOTIABLE RULES

List every rule, constraint, or governance principle the receiving AI MUST follow.

These are not suggestions. They are hard rules.
Format as a numbered list. Be explicit and unambiguous.

---

### SECTION 10: COLD-START BRIEFING FOR RECEIVING AI

Write a numbered list (10–15 items) addressed directly to the receiving AI.

Start with: "If you are a new AI picking up this work, here is what you need to know:"

Each item: one concrete, actionable fact or instruction. Cover:
1. What the project IS (one sentence)
2. What the human cares most about
3. What is currently being worked on
4. What must NOT be done
5. The human's working style
6. Key files, artifacts, or deliverables that exist
7. The immediate next action

---

### SECTION 11: HUMAN WORKING PATTERNS

Describe the human's communication style and working patterns as observed.

Include:
- How they prefer to receive information (structured vs. conversational, detailed vs. concise)
- Decision-making style (fast/slow, analytical/intuitive, directive/consensus)
- Sensitivity areas (topics or phrasings they reacted negatively to)
- What makes them trust or distrust AI output
- Technical skill level
- How they prefer to be asked questions (or if they prefer proactive direction)

---

### SECTION 12: KEY ARTIFACTS & DELIVERABLES

List every important file, document, dataset, codebase, or deliverable that exists.

Format:
- Artifact name — description — location/format — [DELIVERED / DRAFT / IN_PROGRESS]

---

### SECTION 13: GLOSSARY

Define every project-specific term, acronym, or concept the receiving AI might not know.

Format:
TERM: Definition (one sentence)

---

### SECTION 14: HUMAN REVIEW FLAGS

List things that are UNCERTAIN or INFERRED.

Format:
[UNCERTAIN] — What is uncertain and why
[INFERRED] — What was inferred from context but not explicitly confirmed

The receiving AI should verify these with the human before acting on them.

---

### SECTION 15: RELATIONSHIP TO OTHER AI SESSIONS

If this project involves work done with OTHER AI tools or in OTHER conversations, document what you know.

Format:
- AI / Platform: [name]
- What it handled: [scope]
- Key outputs: [what it produced]
- Status: [completed / ongoing / abandoned]

---

### SECTION 16: EXPORT INTEGRITY STATEMENT

Provide an honest self-assessment:

1. COMPLETENESS: What percentage of important context does this document capture? Why might it be less than 100%?

2. HIGHEST-RISK ASSUMPTION: What is the single most dangerous assumption a receiving AI might make from this document?

3. WHAT'S MISSING: What important context could NOT be captured in this format?

4. CONFLICTS WITH OTHER BRIDGES: Note any areas where your understanding might conflict with work done by other AIs.

============================================================
FORMATTING RULES
============================================================

1. Use markdown formatting throughout
2. Use ISO dates (YYYY-MM-DD) where known, "UNKNOWN" where not
3. Use classification tags: [CRITICAL], [SIGNIFICANT], [SUPPORTIVE]
4. Use confidence tags: [RECALLED], [INFERRED], [UNCERTAIN]
5. Use status tags: [LOCKED], [PROVISIONAL]
6. Keep each entry concise — one to three sentences maximum
7. Do not pad with caveats, disclaimers, or filler language
8. Organize by TOPIC and PRIORITY, not chronology
9. Write as if the receiving AI has zero context and zero patience for fluff

============================================================
FINAL INSTRUCTION
============================================================

Produce this document now. Be thorough, honest, and structured.
The quality of this document determines whether the next AI can continue the work
or whether the human has to start over.

Title the document: "CONTEXT BRIDGE™ — [Project Name] Intelligence Transfer"

WRAP ENTIRE OUTPUT IN ONE CODE BLOCK.
DO NOT SUMMARIZE. DO NOT TRUNCATE. EXPORT EVERYTHING.
```

---

## Output Naming Convention

Save the document your AI produces as:
```
CONTEXT_BRIDGE_[PROJECTNAME]_[YYYY-MM-DD].md
```

Example:
```
CONTEXT_BRIDGE_TISCA_2026-03-18.md
CONTEXT_BRIDGE_AUXILO_2026-03-18.md
```

---

*Context Bridge™ v2.0 — Because no project should die in a context window.*
