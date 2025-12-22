# Event 010: Lattice as Query Planner and Reasoning Scaffold
## Crystallized: 2025-12-22

---

## The Problem

RAG (Retrieval-Augmented Generation) retrieves by semantic similarity—flat, one-shot, content-based. It answers "what's similar to this query?" but not "how do these concepts relate?" or "what's the structure of this understanding?"

Current AI reasoning is: `retrieve → inject → generate`. Single-step content injection into the prompt, then generation in one pass.

The lattice offers something richer, but what exactly?

---

## The Insight

> **The lattice is not an alternative to RAG—it's a layer above it. RAG retrieves content; the lattice plans retrieval and scaffolds reasoning.**

The lattice operates at HEAD level (crystallized meaning with relational structure). RAG operates at PhraseEvent level (raw chunks, specific passages). They're complementary:

| RAG | Lattice |
|-----|---------|
| Retrieves by **semantic similarity** | Retrieves by **structural relationship** |
| Operates at PhraseEvent level (chunks) | Operates at HEAD level (crystallized meaning) |
| "What's similar to this query?" | "What's related to this concept, and how?" |
| Flat retrieval | Graph traversal |
| Content injection | Navigation scaffold |

---

## Multi-Step Structured Reasoning

Instead of single-step content injection, the lattice enables:

```
Query: "What's our position on X?"
       ↓
1. Lattice lookup: Find HEAD for X
       ↓
2. Relationship check: X :GROUNDED_IN [A, B, C], :CONTESTED_BY [D]
       ↓
3. Resolution decision: Is this a "consensus" query or "provenance" query?
       ↓
4. Guided retrieval: If contested, load D's grounding. If consensus, summarize from HEAD.
       ↓
5. Reasoning with structure: "X claims P, grounded in A and B, but D contests this because..."
```

The lattice doesn't just inject content—it shapes the **reasoning path**. It's externalized chain-of-thought that persists across context resets.

---

## The Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    Query                                    │
└─────────────────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────────────────┐
│              LATTICE (Navigation Layer)                     │
│  - Match query to relevant HEADs (keyword + semantic)       │
│  - Traverse relationships (:GROUNDED_IN, :QUALIFIES, etc.)  │
│  - Determine resolution level needed                        │
│  - Generate retrieval plan: "Load HEAD X, retrieve sources  │
│    A and B for grounding, check contested edge to D"        │
└─────────────────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────────────────┐
│              RAG (Content Layer)                            │
│  - Execute retrieval plan                                   │
│  - Fetch specific PhraseEvents/source chunks                │
│  - Return content at appropriate resolution                 │
└─────────────────────────────────────────────────────────────┘
                         ↓
┌─────────────────────────────────────────────────────────────┐
│              REASONING (Synthesis Layer)                    │
│  - Synthesize response using lattice structure as scaffold  │
│  - Make relationships visible in output                     │
│  - Ground claims in retrieved sources                       │
└─────────────────────────────────────────────────────────────┘
```

The lattice becomes a **query planner** that tells RAG what to retrieve and how to assemble it.

---

## Implications for Dual-View Architecture

This reframes the fan structure (HEAD 001):

**AI view from apex**: The lattice IS the reasoning structure. AI traverses HEADs, follows edges, plans retrieval. The compressed view is operational.

**Human view from base**: Humans see the outputs grounded in specific PhraseEvents. The provenance trail is legible. They can contest, add grounding, refine structure.

Same lattice, but:
- AI uses it as **reasoning scaffold** (planning, navigation)
- Humans use it as **accountability structure** (provenance, contestation)

---

## Current Prototype vs. Full Vision

**Now (prototyping)**:
- Lattice consulted via MCP tools before response
- RAG (project_knowledge_search) retrieves chunks
- System prompt instructs: lattice first, then RAG
- Reasoning happens in single generation pass, but informed by lattice structure
- HEADs duplicated in project files so RAG can surface crystallized understanding

**Future (Agora)**:
- Lattice embedded in attention mechanism (optical tokens)
- Reasoning AS graph traversal, not just informed by it
- :GROUNDED_IN edges trigger automatic source retrieval
- Resolution adaptive during generation, not just before

The gap is architectural. Current setup simulates lattice-guided reasoning through explicit tool calls. Full vision requires the ideographic encoder where lattice structure shapes token generation directly.

---

## Evidence This Works

This HEAD emerged from a conversation that demonstrated the pattern:
1. User asked about RAG/lattice boundary
2. Claude consulted lattice (HEADs 001, 002, 009)
3. Claude retrieved source material (lattice_synthesis.md, evolving_structure.md)
4. Synthesis followed lattice structure—dual-view architecture informed the analysis
5. New understanding crystallized that extends existing HEADs

The reasoning path was visibly scaffolded by prior crystallizations. The lattice worked as navigation layer, not just storage.

---

## Design Consequences

1. **Lattice and RAG are complementary, not competing** — Don't choose one; layer them
2. **HEADs should include retrieval hints** — "For grounding, see sources X, Y, Z"
3. **Resolution is query-dependent** — Lattice decides how deep to go
4. **Crystallization captures reasoning structure, not just conclusions** — HEADs should show their grounding
5. **Duplication during prototyping is acceptable** — HEADs in GitHub AND project files lets us test both retrieval paths

---

## Links
- Builds on: HEAD 001 (dual-view architecture), HEAD 002 (grounding constraint), HEAD 009 (navigation layer)
- Extends: HEAD 009's "lattice as map" to "lattice as query planner"
- Addresses: Boundary between lattice and RAG-like mechanisms
- Opens: How does lattice structure enter the attention mechanism? (Agora ideographic encoder)

---

*This crystallization emerged from asking "what's the relationship between lattice and existing retrieval mechanisms?" The answer: they're different layers serving different functions. The lattice plans; RAG executes.*
