# CONTEXT BRIDGE™ — Example: Software Project Intelligence Transfer

> This is a sample Context Bridge document showing what a well-produced bridge looks like for a software build project. All project details are fictional and for illustration only.

---

**Document title:** CONTEXT BRIDGE™ — DataSync API Intelligence Transfer
**Exporting AI:** ChatGPT (GPT-4o)
**Receiving AI:** Any
**Export Date:** 2026-03-01
**Conversation Scope:** Full backend API design, database schema, and authentication layer for DataSync
**Session Count:** ~22 sessions over 6 weeks
**Bridge Version:** 2.0

---

### SECTION 1: PROJECT KERNEL

DataSync is a REST API that enables real-time data synchronization between mobile clients and a central PostgreSQL database. It serves small teams (2–20 users) who need offline-first mobile apps with conflict resolution. The system's core value is deterministic conflict resolution — last-write-wins with a vector clock fallback. Without the conflict resolution layer, the product has no differentiation and cannot be trusted with financial or inventory data.

---

### SECTION 2: CURRENT STATE

[COMPLETED] — PostgreSQL schema v3 (users, sessions, records, sync_log tables)
[COMPLETED] — JWT authentication with refresh token rotation
[COMPLETED] — Basic CRUD endpoints for /records
[IN_PROGRESS] — Conflict resolution engine (vector clock logic written, not tested)
[IN_PROGRESS] — Rate limiting middleware (designed, not implemented)
[NOT_STARTED] — WebSocket layer for real-time push
[NOT_STARTED] — Admin dashboard
[BLOCKED] — Load testing blocked on: conflict resolution engine must be complete first

---

### SECTION 3: ARCHITECTURE & SYSTEM STATE

[LOCKED] — Language: Node.js (TypeScript)
[LOCKED] — Database: PostgreSQL 15 via Supabase
[LOCKED] — Auth: JWT (access token 15min, refresh token 7 days, rotation on use)
[LOCKED] — API style: REST (GraphQL was considered and rejected — see Section 5)
[LOCKED] — Schema version: v3 (do not alter without migration script)
[LOCKED] — Conflict strategy: vector clock, last-write-wins fallback
[PROVISIONAL] — Hosting: Railway (may move to Fly.io if cost becomes issue)
[PROVISIONAL] — Rate limiting: 100 req/min per user (threshold not validated)

---

### SECTION 4: CRITICAL DECISIONS MADE

[2026-01-15] [USER-DECISION] [RECALLED] — PostgreSQL over MongoDB. Reason: relational integrity needed for sync_log foreign keys. MongoDB's flexible schema was seen as a liability for audit trails.

[2026-01-22] [USER-DECISION] [RECALLED] — Offline-first scope is v1 only for read operations. Write conflicts will require connectivity at v1. Full offline writes are v2.

[2026-02-10] [USER-DECISION] [RECALLED] — No multi-tenancy in v1. Single-org deployment only. Multi-tenancy is v2 and requires schema partitioning rethink.

[2026-02-28] [USER-DECISION] [INFERRED] — Admin dashboard is deprioritized until conflict engine is stable. Human confirmed verbally but not in writing.

---

### SECTION 5: REJECTED PATHS & PIVOTS

[2026-01-10] [REJECTED] [RECALLED] — GraphQL: Rejected because the team has no GraphQL experience and the query flexibility is not needed for v1's fixed data model. Do not re-propose.

[2026-01-20] [REJECTED] [RECALLED] — Firebase Realtime Database: Rejected because vendor lock-in and inability to run SQL analytics on sync data. Do not re-propose.

[2026-02-05] [REJECTED] [RECALLED] — Operational Transformation for conflict resolution: Rejected as too complex for the data types involved. Vector clocks are sufficient and the team can reason about them. Do not re-propose.

---

### SECTION 6: AI CONTRIBUTIONS

[CRITICAL] [RECALLED] — Designed the sync_log table schema with vector clock columns. This is the architectural foundation of the entire conflict resolution system.

[CRITICAL] [RECALLED] — Wrote the JWT refresh token rotation logic. Prevents token replay attacks. Human reviewed and approved without changes.

[SIGNIFICANT] [RECALLED] — Identified that offline write conflicts require connectivity at v1 — saved the team from scoping a feature that would have delayed launch by 2 months.

[SIGNIFICANT] [INFERRED] — Produced the full TypeScript interface definitions for the API request/response contracts. These are in /src/types/api.ts.

[SUPPORTIVE] [RECALLED] — Wrote the initial README structure. Human revised the positioning section significantly.

---

### SECTION 7: WHAT FAILED OR SURPRISED

[2026-02-01] [FAILURE] [RECALLED] — First version of conflict resolution used timestamps only. Failed because clients with clock skew produced silent data corruption. Replaced with vector clocks. Lesson: never use wall-clock time as the sole arbiter of write order in distributed systems.

[2026-02-20] [SURPRISE] [RECALLED] — Supabase's row-level security (RLS) policies interfered with the sync_log trigger. Unexpected behavior: RLS blocked the trigger's service-role writes. Resolved by explicitly granting service role bypass on sync_log. Document this in the schema README.

---

### SECTION 8: OPEN PROBLEMS

[PRIORITY: CRITICAL] — Conflict resolution engine has not been tested with concurrent writes from 3+ clients. Edge cases with partial network failures are unknown.

[PRIORITY: HIGH] — Rate limiting threshold (100 req/min) is a guess. Needs load testing to validate.

[PRIORITY: HIGH] — No error handling strategy defined for sync failures that corrupt the sync_log. Currently: silent failure. This needs a dead-letter queue or retry mechanism.

[PRIORITY: MEDIUM] — No migration strategy documented for schema changes post-launch.

[PRIORITY: LOW] — TypeScript strict mode is off. Should be enabled before production.

---

### SECTION 9: NON-NEGOTIABLE RULES

1. Never alter the sync_log table schema without a migration script. Data integrity depends on it.
2. Never use wall-clock timestamps as the primary conflict resolution mechanism. Vector clocks only.
3. Never implement multi-tenancy features in v1. This requires a full schema redesign.
4. Never suggest Firebase, MongoDB, or GraphQL. All three have been explicitly rejected.
5. All new endpoints must have TypeScript types defined in /src/types/api.ts before implementation.
6. JWT refresh token rotation is not optional. Do not simplify this for development convenience.

---

### SECTION 10: COLD-START BRIEFING FOR RECEIVING AI

If you are a new AI picking up this work, here is what you need to know:

1. This is a REST API for offline-first mobile data sync. The conflict resolution engine is the entire product.
2. The human's highest priority is shipping a reliable conflict resolution engine before anything else.
3. Current active work: completing and testing the vector clock conflict resolution engine.
4. Do NOT suggest GraphQL, Firebase, MongoDB, or Operational Transformation — all rejected.
5. The schema is at v3 and is LOCKED. Do not suggest schema changes without a migration plan.
6. The human is technical (senior level), prefers structured output, and makes fast decisions.
7. The most dangerous open problem is untested concurrent write conflicts. Address this before anything.
8. Key file: /src/types/api.ts contains all TypeScript contracts — always update this first.
9. Supabase RLS has a known gotcha with triggers — see Section 7 before touching RLS policies.
10. The immediate next action is: write the test suite for the conflict resolution engine.

---

### SECTION 11: HUMAN WORKING PATTERNS

- Prefers structured output with clear sections. Does not like long prose explanations.
- Makes fast decisions once trade-offs are clearly presented.
- Trusts AI output that shows reasoning, not just conclusions.
- Technical skill level: senior full-stack developer. Does not need basics explained.
- Prefers proactive direction over being asked many clarifying questions.
- Reacted negatively to one instance of the AI suggesting a pivot without evidence — stay evidence-based.

---

### SECTION 12: KEY ARTIFACTS & DELIVERABLES

- PostgreSQL schema v3 — full table definitions — /db/schema_v3.sql — [DELIVERED]
- TypeScript API types — full request/response interfaces — /src/types/api.ts — [DELIVERED]
- JWT auth module — access + refresh token rotation — /src/auth/jwt.ts — [DELIVERED]
- Vector clock implementation — conflict resolution core — /src/sync/vector-clock.ts — [IN_PROGRESS]
- API endpoint stubs — CRUD for /records — /src/routes/records.ts — [DELIVERED]

---

### SECTION 13: GLOSSARY

SYNC_LOG: The append-only audit table that records every write operation with its vector clock state.
VECTOR CLOCK: A logical clock mechanism that tracks causal relationships between distributed writes to enable deterministic conflict resolution.
OFFLINE-FIRST: Architecture where the client functions fully without network connectivity and syncs when connectivity is restored.
REFRESH TOKEN ROTATION: Security pattern where each use of a refresh token invalidates it and issues a new one, preventing token replay attacks.
CONFLICT RESOLUTION: The process of determining which write wins when two clients modify the same record without synchronizing first.

---

### SECTION 14: HUMAN REVIEW FLAGS

[UNCERTAIN] — Admin dashboard deprioritization was confirmed verbally but not in a session message. Verify before assuming it is deferred.
[INFERRED] — The 100 req/min rate limit threshold was proposed by the AI and the human did not object. This does not mean it was validated — it needs load testing.
[UNCERTAIN] — Railway vs. Fly.io hosting decision is unresolved. Human mentioned cost concerns but made no final call.

---

### SECTION 15: RELATIONSHIP TO OTHER AI SESSIONS

None documented. All work on this project was conducted in this single AI session series.

---

### SECTION 16: EXPORT INTEGRITY STATEMENT

1. COMPLETENESS: Approximately 85%. The conflict resolution engine's internal logic was developed iteratively across many sessions and some intermediate design decisions may not be fully captured here.

2. HIGHEST-RISK ASSUMPTION: A receiving AI might assume the conflict resolution engine is production-ready because the code exists. It is not. It has not been tested under concurrent load.

3. WHAT'S MISSING: Inline code comments and implementation rationale that exist only in conversation context, not in the exported files.

4. CONFLICTS WITH OTHER BRIDGES: None — single AI source.
