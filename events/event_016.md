# Event 016: The Lattice as Semantic Space with Projective Views
## Crystallized: 2025-12-23

---

## The Provocation

In designing document lifecycle and workflows, we kept falling into a "layers" model: lattice above sources, outputs below. But this flattens something inherently spatial. The user observed: we need snapshot views for different purposes—theory depth, product coherence, external sharing. These aren't layers; they're **projections of a semantic space**.

---

## The Spatial Model

The lattice isn't a layer *above* sources. It's a **navigable semantic space** where HEADs and sources coexist, connected by typed edges.

```
            ┌─────────────────────────────────┐
            │                                 │
            │    SEMANTIC SPACE               │
            │                                 │
            │   ○ HEAD    ○ HEAD              │
            │    ╲         ╱                  │
            │     ╲       ╱                   │
            │      ○ HEAD ────── ○ HEAD       │
            │       │                         │
            │       │ :grounded_in            │
            │       ▼                         │
            │    ▓▓▓▓▓ source                 │
            │                                 │
            └─────────────────────────────────┘
                          │
        ┌─────────────────┼─────────────────┐
        ▼                 ▼                 ▼
   [THEORY VIEW]    [PRODUCT VIEW]    [SHARE VIEW]
```

**Views are projections** of this space for specific purposes. Different purposes require different projections—but they draw from the same underlying structure.

---

## Views as Projections

| View | Purpose | Projects |
|------|---------|----------|
| **Theory Depth** | Assess foundational completeness | HEADs tagged `theory`, grounding chains, gaps |
| **Product Coherence** | Check concept→feature alignment | `concept`/`feature` HEADs, dependencies, orphans |
| **Implementation Status** | Track what's built vs designed | Feature HEADs, code links, missing pieces |
| **External Share** | Communicate to audience X | Selected HEADs rendered as narrative |
| **Research Handoff** | Feed to other AI (Gemini, etc.) | Structured context, questions, source pointers |
| **Navigation** | Live reasoning during session | Keyword-matched HEADs, edge traversal |

Each view:
- Queries the same semantic space
- Filters/shapes by view criteria
- Renders for its purpose
- Can be live (always-current) or snapshot (point-in-time)

---

## Connection to "Language in Use"

This echoes the foundational insight: meaning is context-dependent, "language in use" (Wittgenstein via Masterman via Liu).

- The semantic space holds potential meaning
- A **view** is a context of use—it actualizes relevant meaning for a purpose
- Different contexts (theory assessment, product planning, external communication) project different aspects of the same space

The lattice doesn't have one meaning. It has meaning *relative to the view being projected*.

---

## Snapshot = Rendered View at a Moment

A "snapshot" isn't a state dump. It's a **view rendered at a point in time**:

- Theory snapshot: "Theoretical foundation as of Dec 23, gaps flagged"
- Product snapshot: "Product concept with features traced to concepts"
- Share snapshot: "Briefing for [audience] covering [scope]"

Snapshots can be **frozen**—becoming sources for future work. This completes the lifecycle:

```
Space → View → Rendered Snapshot → Frozen → Becomes Source in Space
```

---

## Implications for Architecture

### 1. Aspects Become First-Class

Not just tags but **query dimensions**:
- `theory`, `concept`, `feature`, `implementation`
- A HEAD can span multiple aspects
- Views filter by aspect

### 2. Views Need Explicit Definition

Each view has:
- **Filter criteria** (which HEADs/sources)
- **Projection logic** (what to include, what depth)
- **Rendering format** (narrative, structured, visual)

### 3. Rendering is a Capability

The system should support:
```
Define View → Project Space → Render Output
```

This isn't just "export"—it's purposive projection.

### 4. Live vs Snapshot

| Type | Updates | Use Case |
|------|---------|----------|
| **Live view** | Always current | Navigation during session |
| **Snapshot** | Point-in-time | Assessment, sharing, handoff |

---

## Relation to Earlier HEADs

- **HEAD 001 (zi-principle)**: The fan structure is spatial—apex to base. Views are different angles on the fan.
- **HEAD 009 (navigation layer)**: Navigation is one view type—the live, interactive projection.
- **HEAD 015 (retrieval as grounding)**: Navigate at HEAD level, ground at source level—describes traversal within the space, not layers above/below.
- **HEAD 013 (temporality)**: Snapshots frozen as sources = the augmentation model applied to views.

---

## Open Questions

1. **View definitions**: What exactly constitutes each view type? What are the filter/projection/render specs?

2. **Aspect taxonomy**: Is `theory/concept/feature` sufficient? What about `strategic`, `implementation`, `critique`?

3. **View tooling**: How do we actually project views? Manual query? Automated rendering? 

4. **Cross-view coherence**: How do we ensure theory view and product view don't drift apart?

---

## Key Quotes

> "Different purposes require different projections—but they draw from the same underlying structure."

> "The lattice doesn't have one meaning. It has meaning *relative to the view being projected*."

> "A snapshot isn't a state dump. It's a view rendered at a point in time."

---

*This HEAD evolves the lattice concept from "navigation layer + grounding sources" to "semantic space with projective views." The spatial model better captures how the same structure serves multiple purposes through different projections.*
