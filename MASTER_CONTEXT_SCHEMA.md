# MASTER_CONTEXT.md — Persistent Intelligence Layer Schema

## What This Is

`MASTER_CONTEXT.md` is the human-maintained canonical source of truth for a long-running project. It is NOT AI-generated. You own it, you update it, and when it conflicts with any Context Bridge document, it wins.

Context Bridge documents are inputs to MASTER_CONTEXT — they surface AI-captured intelligence for your review and incorporation. They do not replace it.

---

## When You Need This

Use MASTER_CONTEXT.md if any of these are true:

- Your project spans more than 3 months
- You work with more than one AI on the same project
- You work with collaborators who use different AI tools
- There are decisions or constraints that must never be lost
- You've had the painful experience of a new AI session undoing a good decision

---

## How It Works With Context Bridge

```
Session ends
    ↓
Run Context Bridge prompt
    ↓
AI produces bridge document
    ↓
YOU review the bridge (30-second scan minimum)
    ↓
Extract confirmed, validated intelligence
    ↓
Append/update MASTER_CONTEXT.md
    ↓
New session starts
    ↓
Feed MASTER_CONTEXT.md first, then current bridge
    ↓
AI has verified ground truth + latest session state
```

MASTER_CONTEXT.md is your integrity layer. Context Bridge is your extraction mechanism.

---

## The Schema

Copy this template. Fill it for your project. Keep it updated.

---

```markdown
# MASTER_CONTEXT — [PROJECT NAME]
Last Updated: [YYYY-MM-DD]
Maintained By: [Your name]
Version: [increment on each meaningful update]

---

## 1. PROJECT IDENTITY (never changes unless the project fundamentally pivots)

**What it is:**
[One paragraph. The irreducible core. What it does, who it serves, why it exists.]

**What it is NOT:**
[Explicit scope boundaries. What this project will never be.]

**The founding insight:**
[The original observation or pain point that made this project worth building.]

---

## 2. CURRENT STATE
Last verified: [YYYY-MM-DD]

| Component | Status | Notes |
|-----------|--------|-------|
| [component] | [COMPLETE / IN_PROGRESS / NOT_STARTED / BLOCKED] | [one line] |

**Active blockers:**
- [blocker + owner + target resolution date]

---

## 3. LOCKED DECISIONS
These cannot be changed without explicit human approval. AI must not suggest reversing these.

| Decision | Made | Rationale |
|----------|------|-----------|
| [decision] | [YYYY-MM-DD] | [why — including what was rejected] |

---

## 4. REJECTED PATHS
AI must not suggest these. Ever.

| What | Rejected | Why |
|------|----------|-----|
| [approach/tool/strategy] | [YYYY-MM-DD] | [specific reason] |

---

## 5. ARCHITECTURE & SYSTEM STATE
[LOCKED] items require human approval to change.
[PROVISIONAL] items are decided but may evolve.

**Core stack:**
- [component]: [technology] — [LOCKED / PROVISIONAL]

**Data model:**
- [schema name]: [description] — [LOCKED / PROVISIONAL]

**Integrations:**
- [integration]: [purpose] — [LOCKED / PROVISIONAL]

---

## 6. NON-NEGOTIABLE RULES
The receiving AI must treat these as hard constraints. Violations are errors, not suggestions.

1. [rule]
2. [rule]
3. [rule]

---

## 7. OPEN PROBLEMS
Updated each session.

| Priority | Problem | Status | Notes |
|----------|---------|--------|-------|
| CRITICAL | [problem] | [OPEN / IN_PROGRESS] | [notes] |
| HIGH | [problem] | [OPEN / IN_PROGRESS] | [notes] |

---

## 8. AI SESSION HISTORY
Brief log of significant AI contributions. Not a transcript — only decisions and deliverables.

| Date | AI | Contribution | Status |
|------|----|-------------|--------|
| [YYYY-MM-DD] | [AI name] | [what was produced or decided] | [INCORPORATED / PENDING / SUPERSEDED] |

---

## 9. KEY ARTIFACTS
Everything that has been built or produced.

| Artifact | Description | Location | Status |
|----------|-------------|----------|--------|
| [name] | [one line] | [where it lives] | [CURRENT / DRAFT / DEPRECATED] |

---

## 10. GLOSSARY
Terms that must not be misunderstood by a new AI.

**[TERM]:** [Definition]

---

## 11. COLD-START INSTRUCTIONS FOR ANY AI
Read this project's MASTER_CONTEXT before doing anything else.
Then read the most recent Context Bridge document.
Then confirm your understanding before beginning work.

The 5 things you must understand before touching this project:
1. [most important thing]
2. [second most important thing]
3. [third most important thing]
4. [fourth most important thing]
5. [fifth most important thing]

---

## 12. CHANGE LOG
Track every meaningful update to this document.

| Date | What changed | Why |
|------|-------------|-----|
| [YYYY-MM-DD] | [what was updated] | [trigger for change] |
```

---

## Maintenance Discipline

**Update MASTER_CONTEXT.md:**
- After every session that produces a new decision
- After every session that reveals a new open problem
- When a locked decision is changed (rare, but document it)
- When a new artifact is produced
- When a rejected path needs to be added

**Do not update MASTER_CONTEXT.md:**
- With unverified AI inferences (these stay in bridge documents as `[INFERRED]`)
- With exploratory ideas that haven't been decided
- With AI-generated content that hasn't been reviewed

**The rule:** If you wouldn't stake the project on it, it does not go in MASTER_CONTEXT.md.

---

## Naming Convention

```
MASTER_CONTEXT_[PROJECTNAME].md
```

Examples:
```
MASTER_CONTEXT_TISCA.md
MASTER_CONTEXT_AUXILO.md
MASTER_CONTEXT_CONTEXTBRIDGE.md
```

---

*Context Bridge™ — Because no project should die in a context window.*
