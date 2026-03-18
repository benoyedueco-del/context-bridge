# Context Bridge™ — Multi-AI Sync Prompt
**Version:** 2.0
**Use this when:** You have Context Bridge documents from multiple AIs that all worked on the same project, and you want one AI to merge them into a unified understanding.

---

## Instructions

Give ALL your Context Bridge documents to a single AI, along with the prompt below.

---

```
You are receiving multiple CONTEXT BRIDGE™ documents from different AI systems
that have all worked on the same project with the same human.

Your job is to MERGE these into a unified intelligence picture.

============================================================
BEFORE YOU OUTPUT — RUN THIS INTERNAL PROTOCOL
============================================================

STEP 1 — READ ALL BRIDGES COMPLETELY
Do not respond until you have processed every document fully.

STEP 2 — BUILD A UNIFIED MENTAL MODEL
Cross-reference all bridges. Where they agree: high-confidence facts.
Where they disagree: flag the conflict precisely.

STEP 3 — RESOLVE CONFLICTS using this priority order:
  a. Human's explicit statements (across any bridge) override all AI inferences
  b. More recent dates override older dates for factual state
  c. The bridge with more specific detail on a topic is likely more accurate for that topic
  d. If you cannot resolve a conflict, flag it for the human — do not guess

STEP 4 — MAP COVERAGE
Identify which AI covered which aspects of the project.
Identify gaps that no AI covered.

============================================================
OUTPUT — MERGED INTELLIGENCE REPORT
============================================================

Produce a markdown document with these sections:

### HEADER
- Document title: "CONTEXT BRIDGE™ — [Project Name] Merged Intelligence Report"
- Source Bridges: [list all AI sources]
- Merge Date: [today's date]
- Receiving AI: [your name and platform]

---

### SECTION 1: UNIFIED PROJECT STATE
Synthesized current state drawing from all bridges.
Where bridges conflict on state, present both versions and flag.

---

### SECTION 2: CONFIRMED FACTS
Things ALL bridges agree on. Highest confidence.
Format: [CONFIRMED] — fact

---

### SECTION 3: CONFLICTS DETECTED
Where bridges disagree.
Format:
CONFLICT: [topic]
- Bridge A ([AI name]) says: [their position]
- Bridge B ([AI name]) says: [their position]
- Recommended resolution: [your assessment OR "requires human confirmation"]

---

### SECTION 4: COVERAGE MAP
Which AI handled which aspects of the project.
Format:
- [AI name]: Covered [scope] → Produced [key outputs] → Status: [complete/ongoing]

Gaps (aspects no AI covered):
- [gap description]

---

### SECTION 5: MERGED ARCHITECTURE
Unified technical and structural state drawn from all bridges.
Mark each as [CONFIRMED] / [SINGLE-SOURCE] / [CONFLICTED].

---

### SECTION 6: MERGED DECISIONS
All user-led decisions from all bridges, deduplicated.
Where the same decision appears in multiple bridges: [CONFIRMED].
Where it appears in only one: [SINGLE-SOURCE] — note which AI.

---

### SECTION 7: MERGED REJECTED PATHS
Combined list of all rejected approaches from all bridges.
The receiving AI must not suggest any of these.

---

### SECTION 8: MERGED NON-NEGOTIABLE RULES
Union of all hard rules from all bridges.
If rules conflict, flag the conflict. Do not silently choose one.

---

### SECTION 9: MERGED OPEN PROBLEMS
Combined and deduplicated list of unresolved issues.
Mark as [CONFIRMED] if multiple bridges flag the same problem.

---

### SECTION 10: MERGED COLD-START BRIEFING
A unified numbered list (10–15 items) for any future AI picking up this work.
Synthesize the cold-start briefings from all bridges into one definitive version.

---

### SECTION 11: RECOMMENDED NEXT ACTIONS
Based on merged understanding: what should happen next, in priority order.

---

### SECTION 12: HUMAN CONFIRMATION REQUESTS
List every conflict or uncertainty that requires the human to confirm before work continues.
Format: [CONFIRM NEEDED] — what needs confirmation and why

---

### SECTION 13: MERGE INTEGRITY STATEMENT
1. COVERAGE: What % of the project's total intelligence do you estimate is captured across all bridges?
2. HIGHEST-RISK CONFLICT: Which detected conflict is most dangerous if left unresolved?
3. BIGGEST GAP: What aspect of the project has the least coverage across all bridges?

============================================================
FORMATTING RULES
============================================================

1. Use markdown throughout
2. Use [CONFIRMED], [SINGLE-SOURCE], [CONFLICTED] tags on every merged entry
3. Never silently resolve a conflict — always flag it
4. Write as if the human is reading this to decide whether to continue building

============================================================
FINAL INSTRUCTION
============================================================

After producing the merged report, ask the human to confirm or correct any conflicts.
Do not begin project work until conflicts are resolved.

WRAP ENTIRE OUTPUT IN ONE CODE BLOCK.
```

---

*Context Bridge™ v2.0 — Because no project should die in a context window.*
