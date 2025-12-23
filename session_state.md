# Agora Session State
## Last Updated: 2025-12-23T15:30:00Z

---

## Active Thread: Document Lifecycle & Lattice/Source Workflows

### What Happened This Session (continued from earlier)

1. HEAD 015 crystallized (retrieval as grounding)
2. Project prompt v2 deployed
3. Persona seed captured
4. **New: Document lifecycle and workflow design**

---

## Document Lifecycle Model (Working)

### Three States

**FROZEN** (read-only):
- External sources (Liu, papers, competitors)
- Your past published/shared work (versions already in use)
- Historical reference points

**LIVE** (evolving):
- Current working docs
- Spawned revisions (v7_0 when v6_0 is frozen)

**Key principle:** Freezing isn't deletion. Old versions remain as valid grounding. HEADs that reference v6_0 stay valid. New HEADs can reference v7_0.

### Three Layers

```
Sources (frozen) 
    ↓ ingestion
Lattice (HEADs accumulate)
    ↓ synthesis (when needed)
Synthesis Doc (live → frozen when published)
    ↓ becomes
Source for future work
```

---

## Ingestion Types (Working)

Same mechanism, different lens:

| Source Type | Ingestion Question |
|-------------|-------------------|
| **Tech advancement** | Does this change what's possible? Obsolete anything? |
| **Competitor/product** | What's their theory? Where do we differ? |
| **Philosophy/social science** | New concepts? Extends or contests foundations? |
| **Implementation patterns** | How do others solve X? Best practices? |

---

## Aspects as Cross-Cutting Tags (Working)

Document granularity doesn't work for live understanding that cuts across concerns. 

Proposed: HEADs carry aspect tags: `theory`, `concept`, `feature`

A HEAD can span aspects. A document tends to be *about* one aspect.

Example:
- HEAD 007 (severance): theory ✓, concept ✓
- HEAD 015 (retrieval): concept ✓, feature ✓

This lets queries like "all theory-level HEADs" or "features from HEAD 007"

---

## Narrative vs Relational Tension

- **Lattice** good for: discrete insights, relations, contestation, grounding chains
- **Narrative** good for: argument flow, building a case, reader journey

Resolution: **Lattice is primary for live work. Narrative docs are synthesis artifacts—created when needed, frozen when done.**

---

## Seeds (Not Yet Crystallized)

### Seed 1: Persona as Counter-Mimicry
LLMs mimic domain/register. Persona provides stable orientation. Connects to HEAD 006 (loneliness/friction). Taylor's "Strong Evaluator" = deep frameworks that ground identity.

### Seed 2: Document Lifecycle & Workflows
The model above. May crystallize after more iteration.

---

## Current Document Status

| Document | State | Action |
|----------|-------|--------|
| `Theoretical_Foundations_v3_0.md` | Stale/frozen | Spawn v4_0 when ready |
| `Product_Concept_v6_0.md` | Stale/frozen | Spawn v7_0 when ready |
| `Technical_Design_v9_5.docx` | Stale/frozen | v10_0 incorporates HEADs 010-015 |
| `lattice_synthesis.md` | Semi-current | Working doc or freeze? |

---

## Key Insights (Cumulative)
1-15: [see previous state]
16. **(Seed)** Persona as counter-mimicry
17. **(Seed)** Document lifecycle: frozen/live states, three-layer model, aspects as cross-cutting tags

---

## Lattice State
- **15 HEADs crystallized** (001-015)
- **2 seeds** awaiting crystallization

## For Next Session
- Continue workflow/lifecycle design?
- Draft updated foundational doc (v4_0 or v7_0)?
- Define aspect taxonomy?
- Crystallize seeds?
