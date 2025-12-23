# Agora Session State
## Last Updated: 2025-12-23T19:00:00Z

---

## Active Thread: Research Execution — MCP & NotebookLM Ecosystem

### What Happened This Session

1. **HEAD 018 crystallized: The Social Topology of Knowledge**
   - Reframes HEAD 017's "contestation mechanics" as broader social topology
   - Not relations between facts—relations between people in life situations
   - The lattice IS the co-development process, not a tool for it

2. **Architecture discussion: RAPTOR and content layer**
   - Three-layer model clarified: Practice → Lattice → Content
   - RAPTOR-style tools can be content layer; lattice is our semantic contribution
   - "Own the lattice layer, borrow the content layer"

3. **Research plan created** (research_plan_mcp_notebooklm.md)
   - Four tasks: MCP ecosystem, NotebookLM alternatives, RAPTOR, graph systems
   - Structured for parallel model execution

4. **Research executed** (research_findings_mcp_notebooklm.md)
   - MCP ecosystem surveyed: 6+ directories, dozens of relevant servers
   - NotebookLM alternatives: SurfSense, Open Notebook, AnythingLLM
   - RAPTOR: Official impl + LlamaIndex pack ready for use
   - Graph systems: GraphRAG, Mem0 (hybrid vector + graph)

---

## Key Research Findings

### Top Candidates for Content Layer

1. **Chroma MCP Server** — Official, production-ready, direct integration
2. **LlamaIndex RAPTOR Pack** — Hierarchical retrieval, tree traversal/collapsed modes
3. **Mem0** — Hybrid architecture pattern (vector + graph + key-value)

### Critical Gap Confirmed

**No existing tool models social topology of knowledge.**

All systems model:
- Entity-relationship (facts and connections)
- Semantic similarity (embedding space)

None model:
- "Who speaks from what position"
- Preserved disagreement as structure
- Constitutive provenance

**This validates HEAD 018's reframe: our focus on social topology is genuinely differentiated.**

### Strategic Implications

**Use:**
- Chroma MCP for vector storage
- LlamaIndex RAPTOR for hierarchical chunking
- Open source embeddings (sentence-transformers)

**Learn from:**
- Mem0's hybrid architecture
- GraphRAG's community detection
- SurfSense's integration patterns

**Build ourselves:**
- Position annotation on HEADs
- Contestation as first-class structure
- Constitutive provenance (`:grounded_in` as architectural)
- Crystallization through dialogue

---

## Documents Created This Session

1. **HEAD 018** (event_018.md) — The Social Topology of Knowledge
2. **research_plan_mcp_notebooklm.md** — Research handoff document
3. **research_findings_mcp_notebooklm.md** — Comprehensive research results

All copied to /mnt/project/ for persistence.

---

## Lattice State

- **18 HEADs crystallized** (001-018)
- HEAD 018 reframes 017 (contestation mechanics → social topology)

---

## Seeds

### Seed 1: Persona as Counter-Mimicry
LLMs mimic domain/register. Persona provides stable orientation. Taylor's "Strong Evaluator" = deep frameworks grounding identity. (From earlier session)

---

## For Next Session

- Consolidate parallel research from other models
- Consider hands-on prototyping with Chroma MCP + RAPTOR
- How does "position" get represented in HEAD metadata?
- What edge types model social relations?
