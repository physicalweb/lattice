# HEAD 020: Bridge Architecture Decision Point

**Created**: 2025-12-25
**Status**: OPEN — Awaiting decision
**Grounded in**: 019 (Technical Stack), 015 (Retrieval as Grounding)

---

## The Fork

Two proposals for the prototype interface layer, with shared agreement on persistence:

### Shared Foundation (Decided)
- **Neo4j AuraDB** as unified persistence (graph + vector + full-text)
- **Lattice semantic model** transfers 100% to production
- **Cypher queries** transfer directly
- Target architecture requires custom UI anyway (React + Tiptap + Yjs)

### Option A: Open WebUI + MCP (Claude's Proposal)
- **Model**: Chat-first, AI orchestrates tool calls
- **Protocol**: MCP (emerging LLM-native standard)
- **Strength**: Simple deployment, multi-model switching, prompt iteration
- **Weakness**: Process logic hidden in prompts, MCP→FastAPI porting later
- **Best for**: Content work, accessing Gemini's 1M context window NOW

### Option B: Dify + FastAPI (Gemini's Counter)
- **Model**: Workflow-first, you design the process visually
- **Protocol**: FastAPI/OpenAPI (industry standard REST)
- **Strength**: Crystallization protocol is VISIBLE, FastAPI transfers directly
- **Weakness**: More upfront design, Dify abstraction layer
- **Best for**: Process design, the crystallization workflow IS the IP

---

## Gemini's Core Insight

> "Agora isn't just a chatbot; it is a **protocol for thinking**. You need to design the *process* (Draft → Critique → Check Provenance → Commit)."

This reframes what we're prototyping:
- Open WebUI = prototype the *content* (use AI to develop ideas)
- Dify = prototype the *process* (design how crystallization works)

---

## The Hybrid Resolution

These aren't mutually exclusive:

1. **Backend**: Use FastAPI (Gemini's point) — transfers directly to React app
2. **Interface**: Choose based on current focus:
   - Dify if iterating on workflow structure
   - Open WebUI if iterating on prompts + multi-model content

The document `Agora_Bridge_Architecture_v1.docx` was created assuming Open WebUI. If Dify is chosen, the backend section (Neo4j schema, Cypher queries) remains valid; only the interface and bridge layers change.

---

## Decision Criteria

| Priority | Choose |
|----------|--------|
| Gemini context window access NOW | Open WebUI |
| Workflow design is the focus | Dify |
| Minimize future porting | Dify (FastAPI native) |
| Fastest to working prototype | Open WebUI |
| Process visibility matters | Dify |

---

## Open Questions

1. Is the crystallization *process* the thing to prototype, or the *content* that emerges from it?
2. Can we start with Open WebUI for content work, add Dify workflows later?
3. Does FastAPI vs MCP matter if both are thin wrappers over Neo4j?

---

## Keywords
bridge, architecture, Open-WebUI, Dify, FastAPI, MCP, workflow, chat, orchestration, decision, interface, throwaway, pathway
