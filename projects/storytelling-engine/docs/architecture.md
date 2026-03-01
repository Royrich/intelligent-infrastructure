# Architecture & Technical Design: Storytelling Engine

## Overview

A **modular skill-based artifact generation system** that transforms raw work into polished, architecture-visible outputs through composable pipelines and intelligent orchestration.

The system demonstrates:
- Intentional architectural discipline
- Constraint-driven design improvements
- Scalable composition patterns
- Operational excellence

---

## Core Architecture: Four Components

### 1. Skill Library (12 Atomic Capabilities)

Each skill is **independent, well-defined, and reusable**:

| Skill | Purpose | Activation |
|-------|---------|------------|
| **Context Capture** | Extract signal from raw work (what, why, constraints, learning) | Always first; establishes foundation |
| **Architecture Reasoning** | Explain why design choices matter; document trade-offs | After Context Capture; focuses on rationale |
| **Brainstorm** | Explore solution spaces systematically; generate alternatives | For design exploration; before decisions |
| **Diagram** | Visualize systems (flows, architecture, relationships) | When visual clarity needed |
| **Note-Taking** | Distill learning; structure knowledge | After studying; before keep/discard |
| **Flashcards** | Encode knowledge for spaced repetition | Optional; for recall testing |
| **Scenario Generation** | Create applied practice scenarios | Optional; for reinforcement |
| **Portfolio Narrative** | Position work for external readers; career narrative | Before publication; elevates for audience |
| **Documentation Formatting** | Structure outputs consistently; ensure readability | Always last; final polish |
| **Voice** | Apply consistent tone, identity, perspective | Across all outputs; policy-enforced |
| **Dynamic Naming** | Generate clear, descriptive names for artifacts | For all named entities |
| **Observation Pattern** | Surface patterns across artifacts | Analytical; comparative |

**Key Design:** Each skill has:
- `SKILL.md` — Behavioral rules, activation conditions, input/output structure, integration logic
- `README.md` — What it is, what it does, how it works, how to use it, examples, troubleshooting

This enables:
- ✅ Clear mental models for operators
- ✅ Quick onboarding for new users
- ✅ Reusability across projects
- ✅ Predictable integration

---

### 2. Orchestration Layer

The "brain" that coordinates skills into deterministic pipelines.

#### Pipelines

**Scaffold Pipeline:**
```
Brainstorm → Dynamic Naming → Context Capture → Documentation Formatting
```
Creates project structure and initial naming.

**Design Exploration Pipeline:**
```
Context Capture → Architecture Reasoning → Diagram → Documentation Formatting → Voice → Finalize
```
Transforms raw work into architecture-visible artifacts.

**Learning Cycle Pipeline:**
```
Note-Taking → [DECISION: Keep?] → (Flashcards | Scenario Generation | Discard)
```
Curates learning with intentional keep/discard gates.

#### Orchestration Features

**Context Store:**
- Maintains state across skill executions
- Passes outputs forward as inputs
- Tracks decisions at gates
- Enables reproducibility

**Skill Registry:**
- Logs which skills were used, in what order
- Records activation conditions
- Tracks execution time and quality signals
- Enables audit and observability

**Policy Engine:**
- Enforces voice rules across all outputs
- Validates naming consistency
- Checks QA standards before finalization
- Prevents low-quality publication

**Run Traces:**
- Complete history of every skill invocation
- Input/output for each step
- Decision points and rationale
- Enables reproducibility and learning

**Non-Destructive Saves:**
- **Soft Save** — Iteration-safe, preserves history, allows backtracking
- **Finalize** — Locks artifact, prevents accidental overwrites, marks publication-ready

**QA Gates:**
- Pre-finalization review of key metrics
- Voice consistency validation
- Structural completeness check
- Quality bar enforcement

#### Integration Logic

Skills don't stand alone. Orchestration enables:
- Skills pass refined output forward
- Each skill enriches prior context
- Policy engine applies voice globally
- Decisions cascade appropriately

---

### 3. Three-Layer Separation

Different audiences, different optimization criteria:

#### Layer 1: Internal (storytelling-engine/)
**Audience:** You + collaborators  
**Optimization:** Honesty, raw signal, complete reasoning  
**Content:** Field notes, drafts, experimental work  
**Visibility:** Private, unpolished  

**Structure:**
```
projects/[name]/
├── field-notes/       ← Quick captures (5-10 min, weekly)
├── artifacts/
│   ├── adr/           ← Architectural Decision Records
│   ├── architecture-summary/
│   └── research/
├── README.md
└── project-metadata.yaml
```

#### Layer 2: Learning (learning/)
**Audience:** You + others learning from pattern  
**Optimization:** Signal retention, high-value knowledge  
**Content:** Curated learning notes, flashcards, scenarios  
**Visibility:** Personal, intentionally curated  
**Gate:** Explicit "Keep Long-Term?" decision  

**Structure:**
```
learning/
├── topics/
│   ├── [topic]/
│   │   ├── notes.md
│   │   ├── flashcards.md      (optional)
│   │   └── scenarios.md        (optional)
```

#### Layer 3: Public (github-portfolio/)
**Audience:** Hiring managers, other engineers, career narrative  
**Optimization:** Clarity, architecture visibility, professional polish  
**Content:** Published projects with reasoning  
**Visibility:** GitHub, external  

**Structure:**
```
projects/[name]/
├── README.md          ← Executive overview
├── docs/
│   ├── architecture.md
│   └── design-decisions.md
├── diagrams/
├── code/              (if applicable)
└── PORTFOLIO-NOTES.md
```

---

### 4. Decision Gates

Intentional friction prevents information overload:

#### Gate 1: Keep Learning Long-Term?
**Activation:** After Note-Taking skill completes  
**Options:**
- **YES** → Add to learning/topics/, optional flashcards/scenarios
- **NO** → Discard archived form (learning remains, artifact doesn't)

**Why?** Prevents "knowledge vault graveyard." Only high-signal learning persists 5+ years.

#### Gate 2: Portfolio-Worthy?
**Activation:** When internal artifact is complete  
**Options:**
- **YES** → Copy to github-portfolio/, elevate narrative, publish
- **NO** → Keep internal, mark as reference

**Why?** Not all work deserves public visibility. Only best work, with reasoning visible.

---

## Design Challenges & Solutions

### Challenge 1: Shallow Documentation

**Problem:** Most systems document *what* but not *why*, *how*, or *integration*.  
**Solution:** Depth A specifications — each skill has behavioral rules, activation conditions, structured outputs, integration logic.  
**Result:** Professional-grade, senior-level quality across all artifacts.  
**Trade-off:** More complex specs, but onboarding docs compensate.

### Challenge 2: Output Size Limits

**Problem:** Large drops can exceed message limits, causing truncation/corruption.  
**Solution:** Batch delivery strategy — deliver skills two at a time, user controls pacing with "Go" commands.  
**Result:** Clean, paste-ready artifacts, no corruption.  
**Trade-off:** Requires manual pacing, but guarantees integrity.

### Challenge 3: Consistency Drift

**Problem:** Manual application of voice/style across 12 skills = inevitable inconsistency.  
**Solution:** Voice Engine — policy engine applies tone, identity, and style rules globally.  
**Result:** Consistent identity across all outputs without manual effort.  
**Trade-off:** Policy rules must be well-defined, but once set, they're automatic.

### Challenge 4: Onboarding Friction

**Problem:** Complex skill system could be hard for collaborators to learn.  
**Solution:** Clear READMEs for every skill — what is it, what does it do, how it works, how to use it, examples, troubleshooting.  
**Result:** Operators can be productive quickly without memorizing specs.  
**Trade-off:** More documentation to maintain, but pays for itself.

### Challenge 5: Iteration Safety

**Problem:** How to support refinement without accidentally losing prior work?  
**Solution:** Non-destructive save semantics — Soft Save for iteration, Finalize for publication.  
**Result:** Safe iteration loops, complete audit trail, no accidental overwrites.  
**Trade-off:** Requires discipline on when to finalize.

### Challenge 6: Portfolio Visibility

**Problem:** Best work stays hidden or scattered across platforms.  
**Solution:** Three-layer system surfaces only portfolio-worthy work to GitHub with reasoning visible.  
**Result:** GitHub portfolio shows thinking, not just code.  
**Trade-off:** Requires intentional curation at a gate.

---

## Data Flow: Raw Work → Published Artifact

```
RAW WORK
   ↓
[Scaffold Pipeline]
Creates structure + naming
   ↓
[Design Exploration Pipeline]
Context → Reasoning → Diagrams → Documentation → Voice → QA Gate → Finalize
   ↓
INTERNAL ARTIFACT READY
(Field notes + ADRs in storytelling-engine/)
   ↓
DECISION 1: Keep Learning?
├─ NO: Discard
└─ YES: Add to learning/topics/
        ├─ Flashcards (optional)
        └─ Scenarios (optional)
   ↓
DECISION 2: Portfolio-Worthy?
├─ NO: Keep internal (reference)
└─ YES: Copy to github-portfolio/
        ├─ Elevate narrative
        ├─ Polish documentation
        ├─ Link back to internal
        └─ Publish to GitHub
   ↓
CAREER VISIBILITY
```

---

## Key Design Principles

### Principle 1: Modularity Over Monolith
**Why?** Clean mental models, composition, reusability, clear boundaries.  
**Applied:** Each skill is atomic and independently testable.  
**Result:** Easy to add, replace, or reorder skills in pipelines.

### Principle 2: Depth Over Breadth
**Why?** Shallow documentation wastes time in ramp-up; depth scales.  
**Applied:** Every skill has behavioral rules, examples, troubleshooting.  
**Result:** Operators become productive faster and produce better outputs.

### Principle 3: Intentional Friction Creates Quality
**Why?** Every filter (keep/discard, portfolio gate) improves signal-to-noise.  
**Applied:** Explicit decisions at each gate; no automatic filtering.  
**Result:** Only high-confidence artifacts advance to next layer.

### Principle 4: Policy Over Manual Enforcement
**Why?** Manual consistency is fragile; policies are reliable.  
**Applied:** Voice engine + QA gates enforce standards automatically.  
**Result:** Professional output quality without per-artifact effort.

### Principle 5: Observable Systems
**Why?** Transparency enables learning, debugging, and improvement.  
**Applied:** Run traces, context store, skill registry, decision logs.  
**Result:** Complete provenance for every artifact.

---

## Trade-offs Accepted

| Decision | Gain | Loss | Trade-off Worth It |
|----------|------|------|-------------------|
| Modular skills (12) | Reusability, clarity | Management overhead | ✅ Yes (composition) |
| Depth A specs | Professional quality | Complexity | ✅ Yes (onboarding docs help) |
| Batch delivery | Integrity, no corruption | Manual pacing | ✅ Yes (artifact quality critical) |
| Voice engine (policy) | Consistency | Less freeform | ✅ Yes (branding) |
| Three layers | Clarity, safety, intentionality | More structure | ✅ Yes (intentionality valuable) |
| Keep/discard gates | High-signal vault | User friction | ✅ Yes (prevents decay) |

---

## Long-Term Evolution

**Phase 1 (Current):** System designed, documented, tested end-to-end  
**Phase 2 (Month 1-2):** Operational mastery (learning plans, flashcards, scenarios, quiz)  
**Phase 3 (Month 3):** Real project capture and iteration  
**Phase 4 (Month 6+):** Patterns emerge, optimizations possible  
**Phase 5 (Year 1+):** Extend to team, content generation, speaking/writing  

Possible future enhancements:
- AI-assisted skill suggestions ("You just captured this — try Architecture Reasoning next")
- Personal knowledge graph (visual connection of concepts)
- Speaking/writing pipeline (articles, conference talks derived from projects)
- Team collaboration (shared skill library, collaborative projects)

---

## Confidence Assessment

**Architecture:** High (designed from constraints, tested end-to-end)  
**Operability:** High (clear semantics, decision gates, audit trails)  
**Scalability:** High (modular skills, deterministic pipelines)  
**Learning Curve:** Medium-High (rich system, but good onboarding docs)  
**Long-Term Viability:** High (incentivizes regular use, compounds value)

**Overall:** System is production-ready for intentional portfolio development.

