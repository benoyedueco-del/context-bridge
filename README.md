# Context Bridge™
### The platform-neutral persistent intelligence layer for AI-augmented work.

> *Because no project should die in a context window.*

---

## The Problem

Every time you switch AI tools — or start a new conversation with the same AI — your project loses context. Months of decisions, architecture choices, rejected paths, and institutional knowledge: gone. You start over. Every single time.

Native AI memory doesn't solve this. ChatGPT remembers what you told ChatGPT. Claude remembers what you told Claude. The cross-platform gap doesn't shrink as memory improves — it widens. Each platform's memory becomes a silo.

**Context Bridge solves the portability problem, not the memory problem.**

---

## What It Is

A universal protocol that forces any AI to produce a structured intelligence transfer document — a **classified briefing**, not a summary — that any other AI can consume to pick up exactly where you left off.

Think of it as a **portable project brain** that lives outside every AI platform. Point any AI at it. It reads the current state, works, and you capture the delta back into the bridge.

---

## What Makes It Different From "Summarize Our Conversation"

| Aspect | Conversation Summary | Context Bridge™ |
|--------|---------------------|----------------|
| Structure | Chronological narrative | Classified intelligence briefing |
| Priority | Everything equal weight | Tagged CRITICAL / SIGNIFICANT / SUPPORTIVE |
| Decisions | Mentioned in passing | Explicitly locked, non-negotiable |
| Failures | Usually omitted | Documented to prevent repetition |
| Rules | Implied | Numbered, explicit, enforceable |
| Receiving AI | Guesses what matters | Told exactly what to do and not do |
| Human patterns | Ignored | Documented for communication calibration |
| Gaps | Hidden | Flagged as uncertain or inferred |
| Multi-AI sync | Not supported | Built-in merge protocol |
| Artifacts | Not tracked | Full inventory with status |
| Cross-AI conflicts | Invisible | Detected and flagged |

---

## The Three Prompts

| Prompt | When To Use | Give It To |
|--------|------------|------------|
| **[Main Prompt](prompts/CONTEXT_BRIDGE_MAIN.md)** | End of any AI conversation | The AI you're leaving |
| **[Sync Prompt](prompts/CONTEXT_BRIDGE_SYNC.md)** | Merging bridges from multiple AIs | The AI receiving multiple bridges |
| **[Receiving AI Primer](prompts/CONTEXT_BRIDGE_PRIMER.md)** | Starting a new conversation | The AI you're starting with |

---

## How To Use It

### Standard Handoff (One AI → Another)

```
1. Copy the Main Prompt
2. Paste it into the AI you've been working with
3. Download the document it produces
4. Give that document to your next AI with the Receiving AI Primer
5. The receiving AI picks up exactly where you left off
```

### Multi-AI Sync (Multiple AIs → One AI)

```
1. Give the Main Prompt to EACH AI that worked on the project
2. Download all Context Bridge documents
3. Give ALL documents + the Sync Prompt to the receiving AI
4. It merges all perspectives and flags any conflicts
```

### Checkpoint (Stay in Same AI, Refresh Context)

```
1. Run the Main Prompt mid-conversation
2. The AI produces a bridge document
3. Start a new conversation, feed it the bridge
4. Continue with a clean context window and no information loss
```

---

## Quick Start

**Step 1:** Open the [Main Prompt](prompts/CONTEXT_BRIDGE_MAIN.md)

**Step 2:** Copy the entire prompt block

**Step 3:** Paste into ChatGPT, Claude, Gemini, Manus, Grok, or any other AI at the end of your project conversation

**Step 4:** Download the document it produces. Name it:
```
CONTEXT_BRIDGE_[PROJECT]_[YYYY-MM-DD].md
```

**Step 5:** Give it to your next AI using the [Receiving AI Primer](prompts/CONTEXT_BRIDGE_PRIMER.md)

---

## Repository Structure

```
context-bridge/
├── README.md                          ← You are here
├── LICENSE                            ← MIT — free to use and fork
│
├── prompts/
│   ├── CONTEXT_BRIDGE_MAIN.md        ← The primary export prompt
│   ├── CONTEXT_BRIDGE_SYNC.md        ← Multi-AI merge prompt
│   └── CONTEXT_BRIDGE_PRIMER.md      ← Receiving AI onboarding prompt
│
├── examples/
│   ├── EXAMPLE_software_project.md   ← Sample bridge: software build
│   ├── EXAMPLE_research_project.md   ← Sample bridge: research workflow
│   └── EXAMPLE_multi_ai_workflow.md  ← Sample bridge: multi-AI project
│
└── docs/
    ├── WHY_THIS_EXISTS.md            ← The full problem statement
    ├── LIMITATIONS.md                ← What Context Bridge cannot do
    └── MASTER_CONTEXT_SCHEMA.md      ← For teams: the persistent layer design
```

---

## Compatibility

Works with any AI that can follow structured text instructions:

✅ ChatGPT (GPT-4o, o1, o3)
✅ Claude (Sonnet, Opus, Haiku)
✅ Gemini (Pro, Ultra)
✅ Manus
✅ Grok
✅ Copilot
✅ Mistral / Le Chat
✅ DeepSeek
✅ Llama (via any interface)
✅ Any future model

---

## The Architecture Insight

No single AI platform will ever build this. OpenAI cannot build a tool that helps you move context to Anthropic. Google cannot build a tool that feeds your project history to GPT. They are structurally incapable of occupying neutral ground — it destroys their retention model.

**Context Bridge is the Switzerland of AI infrastructure.** The moat is not the technology. It is the position.

---

## Roadmap

- [x] v1.0 — Single AI export prompt (14 sections)
- [x] v2.0 — Multi-AI sync protocol + Receiving AI Primer + Key Artifacts section
- [ ] v3.0 — EIP (Extraction & Intelligence Preservation) deep-project variant
- [ ] v4.0 — MASTER_CONTEXT.md persistent layer spec
- [ ] v5.0 — API-based auto-capture (no manual prompt required)
- [ ] App — Platform-neutral persistent intelligence hub

---

## Contributing

Context Bridge is an open protocol. The schema is designed to be a standard, not a product.

- Open issues for edge cases the prompt doesn't handle
- Submit PRs for new example bridges
- Fork it, adapt it, improve it

---

## License

MIT License. Free to use, fork, adapt, and build on.

See [LICENSE](LICENSE) for full terms.

---

## Origin

Context Bridge was designed by a knowledge worker who spent two years building complex AI-driven products across ChatGPT, Claude, and Manus simultaneously — and kept losing everything every time he switched tools or started a new session.

The protocol was built out of personal necessity. The insight that it could be a universal standard came from realizing that every knowledge worker in the world with a multi-AI workflow has exactly the same problem.

---

*Context Bridge™ — Because no project should die in a context window.*
