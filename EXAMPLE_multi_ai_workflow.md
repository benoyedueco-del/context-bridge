# CONTEXT BRIDGE™ — Example: Multi-AI Workflow Intelligence Transfer

> This sample shows what a bridge looks like when a project has been distributed across multiple AI tools simultaneously — one AI for research, one for architecture, one for execution. All project details are fictional and for illustration only.

---

**Document title:** CONTEXT BRIDGE™ — MarketLens Platform Multi-AI Intelligence Transfer
**Exporting AI:** Claude (Anthropic) — Architecture & Strategy sessions
**Receiving AI:** Any
**Export Date:** 2026-03-10
**Conversation Scope:** Platform architecture, business model, and API design for MarketLens
**Session Count:** ~15 sessions (Claude); ~20 sessions (ChatGPT); ~8 sessions (Manus)
**Bridge Version:** 2.0

---

### SECTION 1: PROJECT KERNEL

MarketLens is a B2B market intelligence platform that aggregates competitor pricing, feature, and positioning data for SaaS companies. It serves product and strategy teams at mid-market SaaS companies ($5M–$50M ARR) who currently track competitors manually in spreadsheets. The platform's core value is automated competitive intelligence delivered as structured, actionable data — not raw scraped content. Without the data normalization layer that converts heterogeneous competitor signals into a standard schema, the product is just another scraper, and there are dozens of those.

---

### SECTION 2: CURRENT STATE

[COMPLETED] — Full platform architecture design (Claude sessions)
[COMPLETED] — Business model and pricing structure finalized (Claude sessions)
[COMPLETED] — Competitive landscape research across 14 existing tools (ChatGPT sessions)
[COMPLETED] — Data schema for competitor profile objects (Claude sessions)
[IN_PROGRESS] — Web scraping infrastructure for 3 pilot competitor sites (Manus sessions)
[IN_PROGRESS] — API endpoint design for /competitors and /signals (Claude sessions)
[NOT_STARTED] — Frontend dashboard
[NOT_STARTED] — Customer onboarding flow
[BLOCKED] — Scraping infrastructure blocked on: robots.txt compliance review not complete

---

### SECTION 3: ARCHITECTURE & SYSTEM STATE

[LOCKED] — Core language: Python (FastAPI backend)
[LOCKED] — Data schema: CompetitorProfile object with 22 normalized fields (see Section 12)
[LOCKED] — Scraping strategy: Playwright headless browser + structured extraction, NOT raw HTML parsing
[LOCKED] — Storage: PostgreSQL for structured data, S3 for raw HTML snapshots
[LOCKED] — API design: REST with versioning (/v1/)
[LOCKED] — Pricing model: Per-seat SaaS, $299/seat/month, minimum 3 seats
[PROVISIONAL] — Hosting: AWS (region not decided)
[PROVISIONAL] — Scraping frequency: Daily (not validated against rate limits)
[UNCERTAIN] — Real-time alerting architecture: discussed but not designed

---

### SECTION 4: CRITICAL DECISIONS MADE

[2026-02-01] [USER-DECISION] [RECALLED] — Target market narrowed to SaaS companies only. Rejected broader "any B2B company" scope because data normalization is only feasible when competitor products have predictable web presence patterns.

[2026-02-15] [USER-DECISION] [RECALLED] — No raw data export in v1. Platform delivers insights only, not data dumps. Reason: raw data export commoditizes the product and enables competitors to copy the data layer.

[2026-02-20] [USER-DECISION] [RECALLED] — Pricing at $299/seat/month (not freemium). Reason: freemium attracts users who want data without paying; target buyer is a budget-holding VP who expects to pay.

[2026-03-01] [USER-DECISION] [INFERRED] — Pilot with 3 customers before scaling scraping infrastructure. Human approved pilot approach but timeline not confirmed.

---

### SECTION 5: REJECTED PATHS & PIVOTS

[2026-01-20] [REJECTED] [RECALLED] — Consumer-facing product (tracking competitors for individuals): Rejected. Sales cycle too long, willingness to pay too low, support burden too high.

[2026-02-05] [REJECTED] [RECALLED] — LLM-generated competitive summaries as core product: Rejected. LLM hallucination risk unacceptable for competitive intelligence. Structured data is the product; LLM may assist UX only.

[2026-02-18] [REJECTED] [RECALLED] — Freemium pricing model: Rejected explicitly. See Section 4.

[2026-03-05] [REJECTED] [INFERRED] — GraphQL API: Rejected in favor of REST for same reasons as most projects — team familiarity and v1 data model is fixed enough that query flexibility is not needed.

---

### SECTION 6: AI CONTRIBUTIONS

**Claude (this bridge):**
[CRITICAL] [RECALLED] — Designed the 22-field CompetitorProfile schema. This is the data normalization layer that differentiates the product from raw scrapers.
[CRITICAL] [RECALLED] — Built the business model and pricing rationale. $299/seat/month with minimum 3 seats was Claude's recommendation, accepted without modification.
[SIGNIFICANT] [RECALLED] — Designed the REST API structure including the /signals endpoint concept (competitor change events, not just state).
[SUPPORTIVE] [RECALLED] — Produced the competitive positioning framework used in the pitch deck.

**ChatGPT (separate sessions — see Section 15):**
[CRITICAL] [INFERRED] — Produced the competitive landscape research covering 14 existing tools. This research is the basis for the positioning decisions.
[SIGNIFICANT] [INFERRED] — Helped develop the ICP (ideal customer profile) definition.

**Manus (separate sessions — see Section 15):**
[SIGNIFICANT] [INFERRED] — Built the initial Playwright scraping scripts for 3 pilot competitor sites.
[SUPPORTIVE] [INFERRED] — Produced the robots.txt compliance checklist (status: review in progress).

---

### SECTION 7: WHAT FAILED OR SURPRISED

[2026-02-10] [SURPRISE] [RECALLED] — The 22-field schema initially had 31 fields. Human's review cut 9 fields as either unmeasurable or irrelevant. Lesson: schema design needs human validation against actual data availability before locking.

[2026-03-08] [FAILURE] [INFERRED] — Manus's initial scraping scripts broke on one of the 3 pilot sites due to dynamic content loading. Playwright was already the chosen tool; the issue was selector fragility. Solution: CSS selectors replaced with semantic attribute selectors.

---

### SECTION 8: OPEN PROBLEMS

[PRIORITY: CRITICAL] — Robots.txt compliance review is incomplete. Scraping cannot scale until legal risk is assessed.
[PRIORITY: CRITICAL] — No customer validation yet. Pricing and ICP are based on research, not paying customers.
[PRIORITY: HIGH] — Real-time alerting (notifying users when a competitor changes pricing) is not designed. This is a top requested feature in early conversations.
[PRIORITY: HIGH] — Data freshness SLA not defined. How stale is "too stale" for competitive data?
[PRIORITY: MEDIUM] — No error handling for scraping failures. Currently: silent failure with no alerting.

---

### SECTION 9: NON-NEGOTIABLE RULES

1. No LLM-generated content as a primary data source. LLMs may assist UI/UX only.
2. No raw data export in v1. The product delivers insights, not dumps.
3. No freemium. Minimum 3-seat commitment on all plans.
4. The CompetitorProfile schema is locked at 22 fields. Changes require human approval and migration plan.
5. All scraping must pass robots.txt compliance review before scaling beyond 3 pilot sites.
6. Do not suggest broadening the target market beyond SaaS companies. This was explicitly narrowed.

---

### SECTION 10: COLD-START BRIEFING FOR RECEIVING AI

If you are a new AI picking up this work, here is what you need to know:

1. MarketLens is a B2B competitive intelligence platform for SaaS companies. The differentiator is structured, normalized data — not raw scraping.
2. This project has been split across THREE AIs: Claude (architecture/strategy), ChatGPT (research), Manus (scraping execution). You are getting the Claude bridge only. Request the others too.
3. The CompetitorProfile schema (22 fields) is the entire product's data foundation. Do not modify it casually.
4. Active blockers: robots.txt compliance review and customer validation. Do not design around these being resolved — they must be resolved.
5. Do not suggest LLM-generated competitive summaries as a core feature. Explicitly rejected.
6. Pricing is locked: $299/seat/month, minimum 3 seats. Do not re-open this debate.
7. The human makes fast, directive decisions and does not need options presented — present a recommendation with reasoning.
8. Immediate next action: complete the robots.txt compliance review, then begin customer discovery calls.
9. ChatGPT has the competitive research. Manus has the scraping scripts. This bridge has architecture and strategy.
10. The product does NOT have paying customers yet. All decisions are pre-revenue assumptions to be validated.

---

### SECTION 11: HUMAN WORKING PATTERNS

- Highly strategic thinker. Responds well to systems-level framing.
- Prefers structured output. Reacts poorly to long unstructured prose.
- Fast decision-maker once trade-offs are clear. Do not present 5 options — present 1 recommendation with reasoning.
- Trusts AI that shows its reasoning and flags uncertainty honestly.
- Technical understanding: product/strategy level, not deep engineering. Explain architectural implications in product terms.
- Strongly dislikes scope creep suggestions. Stay within defined boundaries unless asked to expand.

---

### SECTION 12: KEY ARTIFACTS & DELIVERABLES

- CompetitorProfile schema v1 — 22-field data model — documented in design doc — [DELIVERED]
- Platform architecture diagram — component map and data flows — Miro board — [DELIVERED]
- Pricing model rationale — $299/seat analysis — Claude session notes — [DELIVERED]
- Competitive landscape research — 14 tools analyzed — ChatGPT sessions — [DELIVERED]
- Playwright scraping scripts — 3 pilot sites — Manus sessions — [IN_PROGRESS]
- API endpoint design — /v1/competitors and /v1/signals — Claude sessions — [IN_PROGRESS]

---

### SECTION 13: GLOSSARY

COMPETITOR_PROFILE: The 22-field normalized data object that represents a single competitor's state at a point in time.
SIGNAL: A change event on a CompetitorProfile field — e.g., a pricing change, a new feature launch, a positioning shift.
ICP: Ideal Customer Profile — the specific type of company and buyer persona MarketLens is targeting.
PILOT: The 3 pre-revenue customers who have agreed to test the product in exchange for free access and feedback.
DATA NORMALIZATION: The process of converting heterogeneous competitor web data into the standardized CompetitorProfile schema.

---

### SECTION 14: HUMAN REVIEW FLAGS

[UNCERTAIN] — Pilot customer timeline: human approved pilot approach but specific timeline not confirmed in session.
[INFERRED] — Real-time alerting is a priority feature based on "early conversations" mentioned by human. The specific source or customers of these conversations was not identified.
[UNCERTAIN] — AWS region decision: mentioned as open but not discussed further. May have been decided outside this session.

---

### SECTION 15: RELATIONSHIP TO OTHER AI SESSIONS

- AI / Platform: ChatGPT (GPT-4o)
  What it handled: Competitive landscape research, ICP development, early pitch deck iteration
  Key outputs: 14-tool competitive analysis, ICP definition document
  Status: Ongoing (human still uses ChatGPT for research tasks)

- AI / Platform: Manus
  What it handled: Scraping infrastructure build, robots.txt compliance checklist
  Key outputs: Playwright scripts for 3 pilot sites, compliance checklist (incomplete)
  Status: Active — scraping build in progress, blocked on compliance review

---

### SECTION 16: EXPORT INTEGRITY STATEMENT

1. COMPLETENESS: This bridge captures approximately 80% of the architecture and strategy work done in Claude sessions. It does NOT capture the ChatGPT research sessions or the Manus execution sessions — those require separate bridges.

2. HIGHEST-RISK ASSUMPTION: A receiving AI might treat this bridge as the complete project picture. It is not. Two other AI sessions contain critical information (competitive research and scraping infrastructure) that are not in this document.

3. WHAT'S MISSING: The detailed reasoning behind which 9 fields were cut from the original 31-field schema. This context matters if the schema needs to be revisited.

4. CONFLICTS WITH OTHER BRIDGES: The ICP definition in this bridge (Claude's version) may differ from what ChatGPT developed in research sessions. The Sync Prompt should be used to merge and resolve.
