# Agora Session State
## Last Updated: 2025-12-23T02:45:00Z

## Active Thread
After crystallizing HEAD 014 (RAG design), pivoted to deeper questions: **Should we build classic RAG at all?** Two key insights emerged:

### Insight 1: Flat Chunking is Severance
When we chunk Liu's book and embed it, we sever it from its relational structure. Liu isn't presenting facts—she's making *moves*: contesting Searle, recovering Masterman, reframing Shannon through Wittgenstein. Flat chunking loses the argumentative structure. We can retrieve *what Liu said* but not *the move Liu was making*.

Academic discourse is inherently relational:
- **Contests**: argues against a position
- **Extends**: builds on prior work  
- **Recovers**: brings back forgotten threads
- **Reframes**: applies new lens to old material

The lattice captures this for our crystallizations. But ingested content doesn't get this treatment—yet.

### Insight 2: Classic RAG Benchmarks Won't Work
If we measure with classic metrics (retrieval precision, answer accuracy, faithfulness), we optimize for flat retrieval—and miss what makes the lattice valuable.

**What relational intelligence would measure**:
- Provenance tracing: Can system reconstruct a claim's lineage?
- Contestation awareness: Does it surface debates, not flatten to consensus?
- Discourse move recognition: Classify rhetorical function, not just content
- Relational coherence: Do answers preserve argument structure?
- Grounding quality: Trace abstract claims to concrete examples
- Connection discovery: Find relationships that emerge from structure

**Possible query types for relational benchmark**:
1. Lineage queries: "What is X's intellectual heritage?"
2. Contestation queries: "What does X argue against Y about Z?"
3. Move queries: "What is X doing when they say Y?"
4. Connection queries: "How does A relate to B through C?"
5. Grounding queries: "What examples support abstract claim X?"

### The Meta-Question
Maybe we shouldn't build "RAG + lattice" at all. Maybe we should build a **Discourse Navigation System**:
- Content ingested with relational structure
- Queries interpreted as discourse questions
- Responses preserve argumentative structure
- System thinks in terms of moves, positions, lineages

## Key Insights (Cumulative)
1. Dual-legibility solved by zi-principle: same lattice, different resolution
2. Grounding constraint ensures HEADs stay connected to embodied experience
3. Evolution is architecturally necessary (prevents ossification)
4. The Human Friction Problem—metabolization as meaning-making
5. Severance as the act that produces loneliness; provenance as counter-extraction
6. MCP server enables persistent lattice—first piece of Agora infrastructure
7. Forward-looking provenance: grounding isn't ethics, it's architecture
8. Lattice as navigation layer: not storage but a map for reasoning
9. Lattice as query planner: plans retrieval, scaffolds reasoning, RAG executes
10. Lattice as complementary layer to optical tokens
11. Lattice as learned semantic component: abstraction is perspectival
12. Lattice temporality: content frozen, structure evolves
13. RAG landscape: GraphRAG, RAPTOR try to build what lattice already has
14. **Flat chunking performs severance on relational content**
15. **Classic RAG benchmarks measure retrieval, not relational intelligence**

## Available HEADs (14)
- 001: Core Lattice synthesis ← extended_by: [012]
- 002: Temporal dynamics, grounding constraint ← extended_by: [005, 013]
- 003: Liu-Masterman synthesis
- 004: Lattice-Lite protocol ← extended_by: [009]
- 005: Why evolution is architecturally necessary ← extended_by: [013]
- 006: Human Friction Problem / Loneliness Edge
- 007: Severance, Provenance, Counter-Extraction ← extended_by: [013]
- 008: Forward-Looking Provenance
- 009: Lattice as Navigation Layer ← extended_by: [010]
- 010: Lattice as Query Planner ← extended_by: [011, 012, 014]
- 011: Complementary to Optical Tokens ← extended_by: [012, 014]
- 012: Learned Semantic Component ← extended_by: [014]
- 013: Lattice Temporality
- 014: Lattice-Enabled RAG System Design

## Open Design Questions
1. **What to build?** Classic RAG isn't exciting. What's the minimal test of relational value?
2. **Relational ingestion**: How to preserve discourse structure when ingesting content?
3. **Benchmarking**: How to measure discourse fidelity, contestation awareness, lineage tracing?
4. **Levels of integration**: Chunk tagging (light) vs relational extraction (medium) vs lattice digestion (deep)?

## Infrastructure Status
- [x] MCP server operational (lattice-mcp-server v1.1.0)
- [x] GitHub persistence live
- [x] 14 HEADs crystallized
- [x] Forward edges implemented
- [ ] Relational ingestion design
- [ ] Relational benchmark design
- [ ] Implementation (TBD what to build)

## For Next Session
- Decide: Build classic RAG as baseline, or skip to relational approach?
- Consider: HEAD 015 on relational intelligence benchmarking?
- Consider: Prototype focused on one relational capability (e.g., contestation surfacing)?
- Test case: Use Liu text for relational ingestion experiment?

## Context Pressure Level
HIGH - compaction likely imminent. Key insights captured above.
