# Event 014: Lattice-Enabled RAG System Design
## Crystallized: 2025-12-23

---

## The Research Context

Before building our own RAG, we surveyed the 2024-2025 landscape. Key findings:

### Major Paradigms

| Approach | Key Innovation | Relevance to Lattice |
|----------|----------------|----------------------|
| **GraphRAG** (Microsoft) | Builds knowledge graph from corpus; community detection + hierarchical summaries; enables "global" queries | Very high—our lattice IS a knowledge graph |
| **Contextual Retrieval** (Anthropic) | Adds chunk-specific context before embedding; 49-67% retrieval improvement | Medium—could apply to PhraseEvent level |
| **RAPTOR** | Recursive clustering + summarization; builds hierarchical tree from bottom-up | High—similar to lattice abstraction hierarchy |
| **Self-RAG / Adaptive RAG** | Model decides when/whether to retrieve; self-critique of outputs | Medium—lattice could inform these decisions |
| **Agentic RAG** | Agents orchestrate multi-step retrieval with reflection, planning, tool use | High—lattice as query planner (HEAD 010) |

### Key Techniques in Modern RAG

1. **Hybrid Search**: Combine dense embeddings (semantic) with sparse BM25 (keyword). Reciprocal Rank Fusion to merge. Anthropic reports 49% reduction in retrieval failures.

2. **Reranking**: Two-stage retrieval—fast initial retrieval (top 100-150), then cross-encoder reranking to top 10-20. Cross-encoders analyze query-document pairs jointly, much more accurate than bi-encoders.

3. **Contextual Chunking**: Add document-level context to each chunk before embedding. Reduces retrieval errors by up to 67%.

4. **Hierarchical Summarization** (RAPTOR-style): Cluster similar chunks, generate summaries, repeat recursively. Enables answering both granular and thematic queries.

5. **Quality Assessment**: Sufficient context detection—does retrieved content actually answer the question? Enables selective generation and abstention.

---

## The Core Insight

> **The lattice already IS the semantic structure that GraphRAG and RAPTOR are trying to build automatically.**

GraphRAG extracts entities and relationships from text using LLMs. We're *crystallizing* HEADs manually through collaborative reasoning.

RAPTOR builds hierarchical summaries. Our HEADs *are* summaries at different abstraction levels, with explicit `:grounded_in` and `:extended_by` edges.

**The lattice advantage**: Our structure has *provenance* and *contestation* built in—something automatic extraction misses. We know where HEADs came from, what they're grounded in, what extends them, what contests them.

Automatic methods extract structure. We *crystallize* understanding. Different epistemic status.

---

## Proposed Architecture: Lattice-Guided RAG

```
┌─────────────────────────────────────────────────────────────┐
│                    QUERY UNDERSTANDING                       │
│  - Parse query                                               │
│  - Match against lattice HEADs (keywords, summaries)         │
│  - Determine query type: local (specific) vs global (theme)  │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    LATTICE NAVIGATION                        │
│  - If HEAD match: follow edges (:grounded_in, :extended_by)  │
│  - Determine resolution level needed                         │
│  - Generate retrieval plan (which sources, what depth)       │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    HYBRID RETRIEVAL                          │
│  - Dense embeddings (semantic similarity)                    │
│  - Sparse BM25 (keyword matching)                            │
│  - Lattice-boosted: boost scores for chunks linked to        │
│    relevant HEADs                                            │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    RERANKING                                 │
│  - Cross-encoder reranking on top candidates                 │
│  - Optional: Lattice-informed reranking (does chunk          │
│    support a HEAD the query needs?)                          │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    CONTEXT ASSEMBLY                          │
│  - Include relevant HEAD summaries as scaffolding            │
│  - Include top reranked chunks as evidence                   │
│  - Structure context by lattice relationships                │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                    GENERATION + GROUNDING                    │
│  - Generate response                                         │
│  - Cite sources (chunks AND HEADs)                           │
│  - Surface contestation if relevant HEADs conflict           │
└─────────────────────────────────────────────────────────────┘
```

### What Makes This Different from GraphRAG

| GraphRAG | Lattice-Guided RAG |
|----------|-------------------|
| Automatically extracts entities/relations | HEADs crystallized through collaborative reasoning |
| Community detection for clustering | Explicit edge types with semantic meaning |
| No provenance—extracted structure | Full provenance—HEADs trace to sources |
| No contestation | Explicit `:contested_by` edges |
| Static after indexing | Evolving through conversation |
| Global/Local query modes | Resolution-adaptive based on lattice structure |

---

## Implementation Plan

### Phase 1: Basic RAG (Establish Baseline)

**Goal**: Working RAG system we control, comparable to project RAG.

**Stack**:
- Vector store: Chroma (local, no infrastructure)
- Embeddings: OpenAI text-embedding-3-small (or voyage-3)
- Documents: Ingest project files (Liu PDFs, Agora docs)

**Deliverable**: 
- MCP tools: `agora_rag_ingest`, `agora_rag_search`
- Baseline metrics on test queries

### Phase 2: Add Hybrid + Reranking

**Goal**: Implement techniques that research shows improve retrieval.

**Additions**:
- BM25 index alongside vector store
- Reciprocal Rank Fusion for combining results
- Cross-encoder reranking (bge-reranker or FlashRank)

**Deliverable**:
- Measurable improvement over Phase 1
- Understanding of which techniques help most for our content

### Phase 3: Lattice Integration

**Goal**: The lattice guides retrieval, not just coexists with it.

**Components**:
1. **HEAD-chunk linking**: Which chunks support which HEADs?
   - Could be manual (explicit pointers)
   - Could be automatic (embed HEADs, find similar chunks)
   - Probably hybrid

2. **Query → HEAD matching**: Before retrieval, match query to relevant HEADs

3. **Lattice-boosted retrieval**: Chunks linked to relevant HEADs get score boost

4. **Context assembly**: Include HEAD summaries as scaffolding alongside retrieved chunks

5. **Grounding surfacing**: When generating, cite both chunks AND HEADs; surface contestation

**Deliverable**:
- Lattice-guided retrieval demonstrably better than vanilla
- Provenance visible in responses

### Phase 4: Evaluation

**Goal**: Rigorous comparison of approaches.

**Test set**:
- Granular queries (specific facts from documents)
- Thematic queries (synthesize across documents)
- Relational queries (how concepts connect)
- Contestation queries (where perspectives differ)

**Metrics**:
- Retrieval precision (are retrieved chunks relevant?)
- Answer quality (human judgment or LLM-as-judge)
- Grounding (can claims be traced to sources?)
- Contestation surfacing (does system identify tensions?)

**Comparisons**:
- Project RAG (current baseline)
- Our vanilla RAG (Phase 1)
- Hybrid + Reranking (Phase 2)
- Lattice-guided (Phase 3)

---

## Key Design Decisions

### 1. Chunking Strategy

Options:
- **Fixed size** (e.g., 500 tokens with 50 overlap): Simple, predictable
- **Semantic boundaries** (sentence/paragraph): Preserves meaning units
- **Contextual** (Anthropic-style): Add document context to each chunk

Recommendation: Start with fixed size + overlap for simplicity. Add contextual enrichment in Phase 2 if needed.

### 2. Embedding Model

Options:
- **OpenAI text-embedding-3-small**: Good quality, API cost
- **Voyage-3**: Anthropic-recommended, excellent for retrieval
- **BGE** (open source): Free, good quality, local compute

Recommendation: Start with OpenAI (familiar, easy). Consider Voyage for comparison.

### 3. HEAD-Chunk Linking

Options:
- **Manual**: Explicit pointers in HEAD metadata (`sources: [chunk_ids]`)
- **Automatic**: Embed HEAD summaries, find similar chunks
- **Hybrid**: Manual for existing HEADs, automatic for discovery

Recommendation: Hybrid. Manual links preserve provenance; automatic finds connections we missed.

### 4. Storage

Options:
- **Chroma**: Local, simple, good for prototyping
- **Pinecone**: Hosted, scales, costs money
- **LanceDB**: Local, good for hybrid search
- **Milvus**: More complex but powerful

Recommendation: Chroma for Phase 1-2. Evaluate LanceDB for hybrid search support.

### 5. Reranker

Options:
- **Cohere Rerank**: API, fast, accurate, costs money
- **bge-reranker**: Open source, good quality, local compute
- **FlashRank**: Lightweight, fast, lower accuracy
- **mxbai-rerank**: New SOTA, open source

Recommendation: Start with bge-reranker (free, good). Compare with Cohere for quality.

---

## What We're Testing

The fundamental hypothesis from HEAD 010-012:

> **Lattice-structured reasoning produces better outcomes than flat retrieval.**

Specifically:
1. Does matching queries to HEADs improve retrieval precision?
2. Does following lattice edges find relevant content that similarity misses?
3. Does including HEAD summaries in context improve answer quality?
4. Does surfacing contestation improve epistemic quality?

If yes: The lattice is a valuable semantic layer, worth the crystallization effort.

If no: We learn something important about where structure helps vs. hinders.

---

## Connection to Optical Tokens Vision (HEAD 011-012)

This RAG system is the **interface layer** we discussed. When optical tokens arrive:
- The lattice determines what comes into focus (attention topology)
- Retrieval becomes continuous resolution adjustment
- HEADs become attention anchors

But we can test the core hypothesis NOW with current RAG technology. Does structure help? The answer informs whether the optical token integration is worth pursuing.

---

## Immediate Next Steps

1. **Set up Chroma + basic ingestion** — get documents into vector store
2. **Build MCP tools** — `agora_rag_ingest`, `agora_rag_search`
3. **Create test query set** — mix of query types
4. **Baseline comparison** — our RAG vs project RAG on same queries
5. **Iterate based on results**

---

## Links
- Builds on: HEAD 010 (query planner), HEAD 011 (complementary to optical tokens), HEAD 012 (learned component)
- Informed by: GraphRAG, RAPTOR, Anthropic Contextual Retrieval, Agentic RAG literature
- Addresses: "How do we build RAG that integrates with the lattice?"
- Opens: Implementation, evaluation metrics, chunking strategy details

---

*This crystallization emerged from research into RAG state-of-the-art, recognizing that the lattice already provides what automatic methods try to build—with provenance and contestation as bonuses. Now we implement and test.*
