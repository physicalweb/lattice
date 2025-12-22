# Event 013: Lattice Temporality and the Question of Memory
## Crystallized: 2025-12-23

---

## The Provocation

If we now see the perspectival essence of abstraction (HEAD 012), what do we do about existing HEADs that assumed absolute abstraction? Do we change them? Augment them? Leave them?

In human psychology, there's the concept of **memory rewriting**—only possible when shocking dissonance comes into view (e.g., how trauma was "recorded" vs. how I see it now). But rewriting is dangerous. It can heal, but it can also falsify.

What temporality model does the lattice have? Is it all read-only? What happens when understanding evolves?

---

## The Core Tension

Two failure modes:

**Immutable HEADs (pure append-only)**:
- Understanding accumulates, but early crystallizations may mislead
- Someone reading HEAD 001 without HEAD 012 gets incomplete picture
- The lattice becomes archaeological—accurate to when things were written, but requiring excavation to reach current understanding

**Mutable HEADs (rewriting permitted)**:
- Risk losing the record of how understanding evolved
- The "rewriting danger"—past reasoning becomes inaccessible
- Can't distinguish between "we changed our minds" and "we always thought this"
- Loses the grounding that comes from seeing the path

---

## Current Implicit Model

Git gives us versioning at the file level. Semantically, we've been treating HEADs as **append-only**:
- We create new HEADs, we don't revise old ones
- HEAD 012 doesn't "fix" HEAD 001—it extends it
- The `:grounded_in` edges point backward, creating lineage

But this isn't explicit policy—it's emergent practice. And we have no forward-pointing edges.

---

## Proposed Model: Layered Augmentation

> **Content is read-only; structure evolves.**

The original HEAD is preserved at the content level, but:

1. **New edges can be added**:
   - `:EXTENDED_BY` — later HEAD develops this further
   - `:REFRAMED_BY` — later HEAD changes how to interpret this
   - `:SUPERSEDED_BY` — later HEAD replaces this (rare, for genuine errors)
   - `:CONTESTED_BY` — disagreement that remains unresolved

2. **Annotations can be appended** (like marginalia):
   - Lightweight additions without full recrystallization
   - "See HEAD 012 for perspectival refinement"
   - Warnings: "This assumed X, which we now question"

3. **The graph structure encodes evolution**:
   - Reading HEAD 001 alone → historical understanding
   - Following edges forward → evolved understanding
   - The lattice IS the record of how thought developed

```
HEAD 001 (original crystallization, content frozen)
    │
    ├── :EXTENDED_BY → HEAD 012 (perspectival abstraction)
    ├── :CONTESTED_BY → [future HEAD if disagreement emerges]
    ├── annotations: ["See HEAD 012 for refinement of abstraction model"]
    └── [content unchanged]
```

---

## The Analogy: Talmudic Commentary

The Talmud preserves the Mishnah (original text) while surrounding it with layers of commentary (Gemara), which itself accumulates further commentary over centuries. The original isn't rewritten—it's **contextualized** by what surrounds it.

Reading the Mishnah alone gives you the historical statement. Reading with the Gemara gives you the evolved understanding. The structure encodes the dialogue across time.

The lattice could work similarly:
- HEADs are the Mishnah (crystallized at a moment)
- Edges and annotations are the Gemara (accumulated understanding)
- The whole structure is the evolving text

---

## What This Means Practically

**For existing HEADs**:
- Don't change HEAD 001's content
- Add `:EXTENDED_BY` edge pointing to HEAD 012
- Optionally add annotation in heads.json: "see_also": ["012"]

**For future crystallization**:
- When new HEAD refines old one, explicitly create forward edge
- Consider: should the system prompt instruct Claude to follow `:EXTENDED_BY` edges when consulting HEADs?

**For genuine errors**:
- Rare `:SUPERSEDED_BY` edge marks a HEAD as obsolete
- Original content preserved (for record), but flagged
- This is the lattice equivalent of "retraction"

---

## Open Questions (Scaffolding for Future Work)

1. **Epochs or versions?**
   - Do HEADs have version numbers, or is versioning purely relational (via edges)?
   - Could there be "lattice epochs" marking major reconceptualizations?

2. **What triggers recrystallization vs. extension?**
   - When is a new HEAD warranted vs. an annotation on existing HEAD?
   - Threshold: "substantial new insight" vs. "refinement"

3. **Canonical reading paths**:
   - Is there a "current best understanding" view that follows all forward edges?
   - Or is the lattice always multi-path, requiring traversal choices?

4. **Error correction**:
   - How do we handle HEADs that are genuinely wrong (not just incomplete)?
   - `:SUPERSEDED_BY` is one option—are there others?

5. **Computational implications**:
   - If the lattice specialist (HEAD 012) infers relations, does it also infer temporal relations?
   - Can it detect when a HEAD needs extension vs. supersession?

6. **The grounding constraint over time**:
   - HEAD 002 says HEADs must stay grounded in embodied experience
   - Does grounding need to be re-verified as context evolves?
   - Can a HEAD that was grounded become ungrounded through drift?

---

## Connection to Severance

HEAD 007 identified severance as the act that produces loss—cutting value from its source. Memory rewriting is a form of severance: cutting present understanding from its developmental history.

The layered augmentation model is **anti-severance**: it preserves the connection between current understanding and its origins. You can always trace back. The lattice maintains provenance of thought itself.

---

## Implementation Notes

**Immediate** (minimal change):
- Add `extended_by` field to heads.json entries where applicable
- Update HEAD 001 to note "extended_by": ["012"]

**Near-term**:
- Define edge type semantics clearly (`:EXTENDED_BY` vs `:REFRAMED_BY` vs `:SUPERSEDED_BY`)
- Consider annotation format in heads.json

**Longer-term**:
- Query system that presents "current understanding" view (following forward edges)
- Detection of HEADs needing extension or supersession

---

## Links
- Builds on: HEAD 002 (grounding constraint, drift), HEAD 005 (evolution necessity), HEAD 007 (severance)
- Addresses: How does the lattice handle evolving understanding?
- Opens: Versioning policy, canonical views, error handling, temporal inference
- Methodological: This HEAD is itself "scaffolding for future thinking"—explicit about being incomplete

---

*This crystallization emerged from asking "what do we do when understanding evolves?" The answer: preserve content, evolve structure. The lattice records not just what we think, but how our thinking developed.*
