# Learning Lifecycle System

A three-skill system for continuous knowledge evolution, built into the storytelling engine.

## Why This Matters

Rather than hoping learning happens passively, the storytelling engine actively structures knowledge capture, reinforcement, and validation. Every experience becomes a learning opportunity with a clear path from raw discovery to retained knowledge.

---

## The Three Skills

### 1. Note-Taking — Structured Capture with Quality Gates

**Purpose:** Extract actionable learning from experience

**How it works:**
- Captures along four dimensions: WHAT, WHY, CONSTRAINTS, LEARNING
- Links observations to related knowledge
- Flags uncertainties explicitly
- Connects to downstream applications

**Quality Gate:** After note creation, the system asks: **"Keep this note for learning, or discard?"**
- **KEEP:** Note passes quality threshold, enters spaced repetition schedule
- **DISCARD:** Note archived but preserved, doesn't clutter active learning

**Output:** Structured learning note ready for next phase

---

### 2. Flashcards — Spaced Repetition for Long-Term Retention

**Purpose:** Reinforce knowledge through scientifically-proven spacing

**How it works:**
- One concept per card, testable format
- Review schedule optimized for human memory:
  - Day 1: Immediate (100% review)
  - Day 3: Reinforce (80% review)
  - Day 7: Strengthen (60% review)
  - Day 14: Solidify (40% review)
  - Day 30: Master (20% review)

**Quality signals:**
- Cards are grounded in actual decisions or learning
- Questions are precise, answers are concise
- Difficulty level guides review intensity

**Outcome:** Knowledge that sticks, not just surface familiarity

---

### 3. Scenario Generation — Test Knowledge Through Simulation

**Purpose:** Validate understanding by working through realistic "what-if" situations

**How it works:**
- Creates scenarios based on real constraints (time, budget, team size)
- State hypothesis: "If X happens, then Y will occur"
- Work through the scenario
- Compare expectations to outcomes
- Extract learning about design resilience

**Applications:**
- Architecture Reasoning validation (do our design decisions hold under stress?)
- Learning Cycle testing (do I actually understand this concept?)
- Risk exploration (what breaks if constraints change?)

**Outcome:** Deep understanding grounded in realistic application

---

## The Flow

```
Experience Happens
    ↓
Note-Taking captures 4 dimensions
    ↓
Quality Gate: Keep? → NO = Archive
           └── YES ↓
Flashcards extracts core concepts
    ↓
Spaced review schedule begins (Days 1,3,7,14,30)
    ↓
Scenario Generation tests understanding
    ↓
Knowledge validated & integrated
```

---

## Key Principles

✅ **Actionability** — Learning must be usable in real work  
✅ **Connections** — Link new knowledge to existing understanding  
✅ **Quality Gates** — Only valuable learning enters the system  
✅ **Spacing** — Repetition at scientifically-optimal intervals  
✅ **Validation** — Test through realistic scenarios  
✅ **Preservation** — Nothing is deleted, only archived  

---

## Integration Points

The learning system integrates with the storytelling engine:
- **Context Capture** → LEARNING dimension becomes notes
- **Architecture Reasoning** → Decisions become flashcard topics
- **Scenario Generation** → Tests design assumptions
- **Portfolio Narrative** → Learning demonstrates depth and evolution

---

## Example Learning Cycle

**Scenario:** You design a PostgreSQL database migration

**Note-Taking:**
```
WHAT: Migrated from monolith to PostgreSQL with read replicas
WHY: Needed complex queries + horizontal read scaling
CONSTRAINTS: 2-week timeline, must maintain consistency
LEARNING: Read replicas easier than write scaling; consistency matters more than we thought
```

**Keep/Discard Check:** ✓ KEEP — Actionable insight about database architecture

**Flashcards created:**
- "When should you choose PostgreSQL vs DynamoDB?"
- "What's the difference between read-scaling and write-scaling?"
- "How do read replicas maintain consistency?"

**Spaced Review:** Days 1, 3, 7, 14, 30 — by day 30, this is deep knowledge

**Scenario Generated:**
- "If read traffic increased 10x, would our design hold?"
- "What if consistency requirements changed?"
- Result: You understand the design deeply, not just surface-level

**Portfolio Impact:**
- You can now explain database decisions with authority
- You understand the reasoning, not just the choice
- You can predict what would break under different conditions

---

## Building Your Knowledge Graph

Over time, as you create notes, flashcards, and scenarios, you build a personal knowledge graph:
- Design patterns you've validated
- Architecture principles you've tested
- Engineering insights grounded in real experience
- A portfolio that demonstrates thinking, not just doing

This becomes your competitive advantage: not just work completed, but why it matters and how you'd approach similar problems differently.

---

## See Also

- [Storytelling Engine System Overview](../storytelling-engine/) 
- [Skills Reference — Learning Lifecycles](../storytelling-engine/LEARNING-LIFECYCLE.md)
- [Case Study: Using Learning Cycles](../projects/storytelling-engine/)
