# HEAD 019: The Technical Stack Blueprint

## Created: 2025-12-24T10:30:00Z
## Updated: 2025-12-24T11:00:00Z (ChatGPT research folded in)

## Core Insight

> **The components to build Agora exist; we need to orchestrate, not invent.**
> HippoRAG's Personalized PageRank is the navigation algorithm for Layer 2.
> AIF (Argument Interchange Format) provides the contestation schema.
> Self-evolving memory (GraphMem) offers the path to automated crystallization.

## Grounded In

- HEAD 015 (Retrieval as Grounding) — PPR enables "navigate then ground"
- HEAD 017 (Differentiation Analysis) — confirms strategic positioning
- HEAD 018 (Social Topology) — PPR spreads activation through social space
- HEAD 013 (Lattice Temporality) — self-evolving memory aligns with Talmudic model
- Source: Gemini Deep Research Report (Agora_Lattice_Research_Plan_Execution.pdf)
- Source: ChatGPT MCP Survey (ChatGPT_5_2_Thinking_mcp_ecosystem_survey_open_source_canvas_notes.md)
- Source: ChatGPT NotebookLM Survey (chatgpt5_2_notebooklm_ecosystem_survey_task2.md)

## Multi-Model Convergence

Three models (Claude, Gemini, ChatGPT) independently converged on:

| Finding | Claude | Gemini | ChatGPT |
|---------|--------|--------|---------|
| Contestation as differentiator | ✓ | ✓ | ✓ |
| Neo4j for graph | ✓ | ✓ | ✓ |
| Orchestration pattern | ✓ | ✓ | ✓ |
| Human crystallization central | ✓ | ✓ | ✓ |
| Provenance as architectural | ✓ | ✓ | ✓ |
| Open Notebook as reference | — | ✓ | ✓ |
| HippoRAG/PPR (unique) | — | ✓ | — |
| Self-evolving memory (unique) | — | ✓ | — |
| Per-claim citation (unique) | — | — | ✓ |

## The Industry Bifurcation

Two optimization targets in the market:

| Approach | Optimizes For | Examples | Agora Position |
|----------|---------------|----------|----------------|
| **Compression & Consensus** | Unified answers, hallucination reduction | NotebookLM, GraphRAG | Competitor approach |
| **Context & Contestation** | Preserved tension, social provenance | Agora Lattice | Our differentiator |

NotebookLM "smooths over contradictions to present a unified, reliable answer."
Agora preserves disagreement as first-class structure.

## The Three-Layer Stack

### Layer 3: Orchestrated Interface (The Router)

**Component**: NCP (Natural Context Provider) or similar
**Alternatives from ChatGPT survey**:
- **1MCPServer** — "MCP of MCPs," auto-discovery
- **Archestra** — K8s-native, enterprise governance

**Function**: Intent-based routing, "Chief of Staff" pattern
**Key Insight**: Expose high-level intents (explore, ground, contest), not raw tools

The Router intercepts user intent and dynamically loads appropriate MCP tools:
- Graph navigation → Neo4j MCP
- Vector search → Zilliz MCP  
- Citation lookup → Zotero MCP

This prevents "tool sprawl" and context window bloat.

### Layer 2: Semantic Topology (The Lattice)

**Storage**: Neo4j (via mcp-neo4j)
- Schemaless, supports arbitrary typed edges
- Allows our specific edge vocabulary: `:grounded_in`, `:contested_by`, `:extends`, `:superseded_by`

**Alternative from ChatGPT**: Basic Memory (graph-based markdown, AGPL)

**Navigation**: HippoRAG's Personalized PageRank (PPR)
- Neurobiologically inspired (Hippocampal Indexing Theory)
- "Spreading activation" through associative graph
- Enables one-shot multi-hop reasoning
- Finds semantic regions, not just keyword matches

**Schema**: Argument Interchange Format (AIF)
- Don't invent contestation schema from scratch
- Reify arguments as nodes: `Claim A → Inference → Claim B`
- Attach metadata to the act of disagreement itself

### Layer 1: Commodity Infrastructure (Content)

**Vector Storage**: Zilliz/Milvus (via zilliz-mcp)
- Hybrid search: vector similarity + scalar filtering
- Filter by edge_type while searching semantic space

**Alternatives from ChatGPT**: Chroma MCP, Needle MCP (end-to-end RAG)

**Hierarchical Structure**: RAPTOR
- Recursive abstractive summarization
- Creates "table of contents" for corpus
- Good for Layer 1 "gist," but NOT the Lattice itself
- Algorithmic hierarchy ≠ semantic/social hierarchy

**Provenance**: Zotero MCP + OneCite (citation formatting)
- Full-text search across library
- Structured bibliographic metadata
- Dual API: Web (server-side) + Local (responsive UI)

**Enterprise Provenance**: OpenMetadata MCP (lineage/catalog)

## Key Implementation Patterns

### The Bifurcation Tool

When the Router detects conflict:
1. Do NOT synthesize into unified summary
2. Create two distinct HEAD nodes
3. Link with `:contested_by` edge
4. Preserve both positions in social topology

```
Source A ──grounded_in──▶ HEAD A
                              │
                        contested_by
                              │
Source B ──grounded_in──▶ HEAD B
```

### Provenance Enforcement

Every Node in Layer 2 MUST have `:grounded_in` edge to Layer 1.
Router logic rejects "orphan HEADs" lacking grounding.
This makes constitutive provenance architectural, not just ethical.

### Per-Claim Citation Granularity (ChatGPT insight)

NotebookLM citations are per-response chunk, not per-claim.
Agora should provide **per-claim traceability**:
- Multiple sources can ground a single claim
- A claim can contest another claim
- Export preserves grounding links

### Self-Evolving Memory (Future Direction)

GraphMem and MemGen offer:
- **Consolidation**: Automatic merging of similar nodes (technical crystallization)
- **Forgetting**: Decay of unused edges (keeps lattice relevant)

Aligns with our vision of crystallization as active, ongoing process.

## ChatGPT Key Insights

### "AI Structure as Starting Point"

> "AI-generated structure has limited value if it's not editable. Treat AI structure as a starting point for human crystallization, not the final artifact."

This validates human-in-the-loop crystallization as core to Agora.

### Domain-Scale Ingestion

> "Serious knowledge work often requires aggregating *domains*, not single documents."

Tools like WebSync (bulk site import) show demand for corpus-level ingestion.

### Build *With* vs Build *Around*

> "Provide first-class extensibility so the ecosystem can build *with* you, not *around* you."

The existence of unofficial NotebookLM APIs (AutoContent) shows what happens when platforms don't provide programmatic access. Agora must be API/MCP-first.

## RAPTOR vs HippoRAG: The Critical Distinction

| Aspect | RAPTOR | HippoRAG |
|--------|--------|----------|
| Structure | Hierarchical tree | Associative mesh |
| Retrieval | Layer-by-layer traversal | Personalized PageRank spreading |
| Abstraction | Algorithmic (vector similarity) | Semantic (entity relationships) |
| Multi-hop | Requires tree climbing | One-shot activation flow |
| Agora Use | Layer 1 (commodity summaries) | Layer 2 (lattice navigation) |

**Key Quote**: "HippoRAG enables Associative Retrieval... standard vector search fails to connect A and C. HippoRAG succeeds because the activation flows through the graph."

## Concrete Next Steps

1. **Orchestrator Prototype**: Deploy NCP with zilliz-mcp + mcp-neo4j
2. **Schema Definition**: Define Neo4j schema using AIF principles
3. **Navigation Experiment**: Implement PPR on small Neo4j dataset
4. **Crystallization UI**: Fork Open Notebook, implement debate script generation
5. **Per-Claim Citations**: Design grounding link model that supports multi-source claims
6. **API-First**: Ensure all Lattice operations are MCP-accessible from day one

## Keywords

HippoRAG, PPR, PageRank, NCP, Neo4j, Zilliz, RAPTOR, AIF, bifurcation, orchestration, Layer-1, Layer-2, Layer-3, stack, architecture, GraphMem, self-evolving, consolidation, per-claim, citation, multi-model

## Relations

- `:grounded_in` → HEAD 015, HEAD 017, HEAD 018, HEAD 013
- `:grounded_in` → Gemini Research Report, ChatGPT Research (2 files)
- `:extends` → HEAD 014 (RAG System Design)
- `:reframes` → HEAD 010 (Query Planner) — PPR is the specific algorithm
