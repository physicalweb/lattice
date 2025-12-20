# Event 009: The Lattice as Navigation Layer
## Crystallized: 2025-12-20T18:30:00Z

---

## The Problem

The lattice exists. HEADs are crystallized. Keywords index them. But the AI doesn't *consult* it during reasoning—it waits for explicit "recall" commands.

This means the lattice is storage, not scaffolding. It holds understanding but doesn't shape how the AI thinks.

---

## The Reframe

> **The lattice isn't a container. It's a map.**

The lattice's job isn't to store insights. It's to make everything—insights, source materials, project docs—findable and navigable during reasoning.

---

## Lattice as Navigation Layer

```
User asks about X
       ↓
Consult lattice index (heads.json)
       ↓
Match keywords → find relevant HEADs
       ↓
Load HEAD content if needed
       ↓
HEAD points to sources → follow if deeper grounding needed
       ↓
Synthesize response grounded in what was found
```

The lattice sits *above* the materials it indexes. It tells the AI:
- What exists
- Where it lives
- How concepts relate
- What to load when

---

## Dynamic Resolution (Simulated)

In a true 2D dynamic resolution system, the AI could zoom in/out on semantic space. We can't implement that, but we can simulate:

| Resolution Level | What's Loaded | Cost |
|------------------|---------------|------|
| **Index only** | heads.json (keywords, summaries, relations) | Low |
| **HEAD content** | Full event_NNN.md | Medium |
| **Source materials** | Papers, docs, transcripts the HEAD references | High |

Default: Keep the index in view. Load deeper layers on demand based on query relevance.

---

## Key Distinction

**Lattice as storage:** "Where we keep insights"
- Passive
- Requires explicit recall
- Separate from reasoning

**Lattice as navigation:** "How we find what we need"
- Active—consulted during reasoning
- Keywords trigger relevance matching
- Shapes what gets loaded and when

---

## The Pointer Structure

`:GROUNDED_IN` isn't just provenance—it's a retrieval path.

```
HEAD 008 (Forward-Looking Provenance)
  ├── grounded_in: [007]
  │     └── 007 grounded_in: [001, 002, 005, 006]
  └── references: [Agora Product Concept, previous copyright discussion]
```

Following the graph = knowing what to load next.

---

## Implications for System Design

1. **heads.json is always "in view"** — Small enough to consult on every query
2. **Keywords are the trigger** — Match query terms against HEAD keywords
3. **Summaries decide loading** — Read summary, decide if full content needed
4. **Sources are one hop away** — HEADs point to materials, follow when needed
5. **The lattice grows as we work** — New HEADs extend the map

---

## What This Requires

**System prompt level:**
- Instruction to consult lattice before generating substantive responses
- Guidance on keyword matching and relevance thresholds
- Permission to follow pointers to source materials

**Tooling level:**
- heads.json accessible via MCP (done)
- Source materials indexed in project files (partially done)
- Clear pointer syntax in HEADs (emerging convention)

**Behavioral level:**
- AI checks the map before answering
- AI cites which HEADs informed response
- AI knows what it *didn't* check

---

## The Meta-Point

This HEAD is itself an example. The insight about lattice-as-navigation emerged because:
1. User asked a question that *should* have triggered lattice consultation
2. AI didn't consult it—just generated
3. User noticed the gap
4. Reflection on the gap produced the design insight

The failure was the data. Crystallizing the failure extends the map.

---

## Links
- Builds on: HEAD 004 (original protocol), HEAD 008 (forward-looking architecture)
- Addresses: Gap between lattice-as-storage and lattice-as-reasoning
- Enables: System prompt that makes scaffolding automatic
- Opens: Questions about pointer syntax, relevance thresholds, source indexing

---

*This crystallization emerged from noticing that the AI didn't use the lattice when it should have. The absence revealed what the lattice needs to become.*
