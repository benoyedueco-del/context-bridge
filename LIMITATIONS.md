# Context Bridge — Limitations

Context Bridge is a high-quality extraction scaffold. It is not a perfect intelligence transfer system. This document exists so users build appropriate trust — relying on it where it is strong, and verifying where it is not.

---

## What Context Bridge Cannot Fully Solve

### 1. AI Memory Is Reconstruction, Not Recording

When an AI produces a Context Bridge document, it is not playing back a recording of your conversation. It is reconstructing what happened from pattern-matching across its context window. The longer and more complex the project, the higher the reconstruction error.

This is why every entry in a Context Bridge document is tagged `[RECALLED]` or `[INFERRED]`. `[RECALLED]` means high confidence. `[INFERRED]` means the AI is deriving this from context, not direct memory. Treat inferred entries as hypotheses to be verified, not facts to be acted on.

### 2. Rejected Paths Are Systematically Underrepresented

The most valuable things to preserve — the approaches you explicitly rejected and why — are also the hardest to extract. AIs do not natively track what they didn't recommend. The Rejection Recovery step in the Context Bridge protocol specifically tries to surface these, but it is imperfect. You should manually add rejected paths you remember if they are important.

### 3. The Receiving AI Has No Verification Layer

When AI-B receives a Context Bridge from AI-A, it has no way to challenge or cross-check what it receives. It accepts the bridge as authoritative. If AI-A reconstructed something incorrectly, AI-B will build on that incorrect foundation — silently.

**Mitigation:** Use the **Interrogation Prompt** (see `prompts/CONTEXT_BRIDGE_INTERROGATION.md`). This is specifically designed to run after the bridge is received — it asks the exporting AI targeted questions about operational details, failure cases, number provenance, and code-vs-document existence that structured sections cannot fully surface. It closes the last 10% gap that every bridge leaves open. Always review a bridge before handing it off, and always run the Interrogation Prompt before beginning execution.

### 4. Implicit Context Is Partially Recoverable

Some of the most important project intelligence is never stated — it exists in the texture of how you interact. The constraints you never mentioned because they felt obvious. The priorities embedded in the tone of your questions. The half-finished thoughts that the AI picked up on.

Section 11 (Human Working Patterns) specifically tries to capture this. It is the section most likely to be incomplete or imprecise.

### 5. Long Projects Compress Nonlinearly

For projects spanning many months and dozens of sessions, early sessions are compressed into generalities and recent sessions dominate the bridge document. The evolution of thinking — the arc from early naive understanding to current sophistication — is partially lost. You get the current state but not the journey that justifies it.

**Mitigation:** Run Context Bridge checkpoints throughout a long project, not just at the end. A bridge produced at month 2 captures things a bridge produced at month 6 cannot recover.

### 6. The Receiving AI Still Needs You

Context Bridge significantly reduces the re-explanation burden. It does not eliminate the need for human judgment. The Receiving AI Primer instructs the new AI to confirm its understanding before beginning work precisely because bridges can be incomplete or contain inferred items.

Do not treat a Context Bridge handoff as fully autonomous. You are still the integrity layer.

---

## What the MASTER_CONTEXT.md Layer Solves

For long-running projects, a single Context Bridge document is not sufficient as a standalone protocol. The recommended architecture is:

```
Context Bridge (AI extraction) → human review → MASTER_CONTEXT.md (ground truth)
```

`MASTER_CONTEXT.md` is a human-maintained document that serves as the canonical source of truth for your project. It is not AI-generated. You own it. You update it. When it conflicts with a Context Bridge document, `MASTER_CONTEXT.md` wins.

Context Bridge feeds into `MASTER_CONTEXT.md` — it surfaces AI-captured intelligence for human validation and incorporation. It does not replace it.

See `docs/MASTER_CONTEXT_SCHEMA.md` for the recommended structure.

---

## When Context Bridge Is and Is Not Appropriate

| Use Case | Reliability | Notes |
|----------|------------|-------|
| Jogging your own memory at session start | High | Fast and useful |
| Single-session handoff with your review | High | Review before giving to next AI |
| Multi-session project checkpoint | Medium-High | Run periodically, not just at end |
| Input to MASTER_CONTEXT.md | High | With human validation |
| Fully autonomous AI-to-AI transfer, no human review | Low | Do not rely on this |
| Recovering months-old session context | Medium | Early sessions compress heavily |
| Multi-AI sync without Sync Prompt | Low | Always use the Sync Prompt for merging |

---

## The Honest One-Line Summary

Context Bridge is the best available tool for AI project intelligence transfer. It is not a substitute for a human-validated persistent document on projects that matter and last.

---

*Context Bridge™ — Because no project should die in a context window.*
