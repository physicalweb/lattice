# Agora Session State
## Last Updated: 2025-12-23T02:05:00Z

## Active Thread
Completed RAG state-of-the-art research and crystallized design document (HEAD 014). Key insight: **the lattice already IS the semantic structure that GraphRAG and RAPTOR try to build automatically—with provenance and contestation as bonuses**. Four-phase implementation plan defined. Ready to build.

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
10. Lattice as complementary layer to optical tokens: labs build perception, Agora builds semantic organization
11. Lattice as learned semantic component: abstraction is perspectival; evolution toward "semantic cortex"
12. Lattice temporality: content frozen, structure evolves. Forward edges preserve provenance of thought itself.
13. **RAG landscape (2024-25): GraphRAG, RAPTOR, Contextual Retrieval, Agentic RAG. Lattice has what they're building—plus provenance and contestation.**

## Available HEADs (14)
- 001: Core Lattice synthesis (zi-principle, dual-legibility) ← extended_by: [012]
- 002: Temporal dynamics, grounding constraint ← extended_by: [005, 013]
- 003: Liu-Masterman synthesis
- 004: Lattice-Lite protocol (superseded by MCP) ← extended_by: [009]
- 005: Why evolution is architecturally necessary ← extended_by: [013]
- 006: Human Friction Problem / Loneliness Edge
- 007: Severance, Provenance, Counter-Extraction ← extended_by: [013]
- 008: Forward-Looking Provenance
- 009: Lattice as Navigation Layer ← extended_by: [010]
- 010: Lattice as Query Planner and Reasoning Scaffold ← extended_by: [011, 012, 014]
- 011: Lattice as Complementary Layer to Optical Tokens ← extended_by: [012, 014]
- 012: Lattice as Learned Semantic Component ← extended_by: [014]
- 013: Lattice Temporality and the Question of Memory
- 014: **Lattice-Enabled RAG System Design** ← NEW

## RAG Implementation Plan (from HEAD 014)

### Phase 1: Basic RAG (Baseline)
- Chroma vector store (local)
- OpenAI embeddings (text-embedding-3-small)
- Ingest project files (Liu PDFs, Agora docs)
- MCP tools: `agora_rag_ingest`, `agora_rag_search`

### Phase 2: Hybrid + Reranking
- Add BM25 index
- Reciprocal Rank Fusion
- Cross-encoder reranking (bge-reranker or FlashRank)

### Phase 3: Lattice Integration
- HEAD-chunk linking (which chunks support which HEADs?)
- Query → HEAD matching before retrieval
- Lattice-boosted retrieval scoring
- Context assembly with HEAD summaries as scaffolding

### Phase 4: Evaluation
- Test query set (granular, thematic, relational, contestation)
- Compare: project RAG vs vanilla vs hybrid vs lattice-guided

## Key Design Decisions (from HEAD 014)
| Decision | Recommendation |
|----------|----------------|
| Chunking | Fixed size + overlap (start simple) |
| Embeddings | OpenAI text-embedding-3-small |
| HEAD-chunk linking | Hybrid (manual for provenance, auto for discovery) |
| Storage | Chroma for Phase 1-2 |
| Reranker | bge-reranker (free, good) |

## Infrastructure Status
- [x] MCP server operational (lattice-mcp-server v1.1.0)
- [x] GitHub persistence live (physicalweb/lattice)
- [x] 14 HEADs crystallized
- [x] Forward edges (`extended_by`) implemented
- [x] RAG design document crystallized (HEAD 014)
- [ ] RAG Phase 1 implementation
- [ ] RAG Phase 2 implementation
- [ ] RAG Phase 3 (lattice integration)
- [ ] Evaluation framework

## Session Accomplishments (Current)
- Comprehensive RAG state-of-the-art research
- Surveyed: GraphRAG, RAPTOR, Contextual Retrieval, Agentic RAG, reranking models
- Crystallized HEAD 014: Lattice-Enabled RAG System Design
- Defined four-phase implementation plan
- Identified key design decisions

## Immediate Next Steps
1. **Set up Chroma + basic ingestion** — get documents into vector store
2. **Build MCP tools** — `agora_rag_ingest`, `agora_rag_search`
3. **Create test query set** — mix of query types
4. **Baseline comparison** — our RAG vs project RAG on same queries
5. **Iterate based on results**

## Open Questions
- How do other humans enter? (HEAD 006)
- Bootstrap problem for lattice specialist training (HEAD 012)
- Optimal chunking strategy for our content?
- How to evaluate "grounding quality" not just retrieval precision?

## Context Pressure Level
Low - lattice persists, design document crystallized, ready for implementation
