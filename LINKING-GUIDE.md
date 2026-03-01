# Linking Internal Work to GitHub Portfolio

How to move work from your **internal storytelling engine** to your **public GitHub portfolio**.

---

## The Two Systems

### **System 1: Internal (storytelling-engine/)**
- Raw field notes
- Architecture reasoning
- Design conversations
- Learning notes
- ADRs and architecture summaries
- Everything in progress or for personal use

### **System 2: Public (github-portfolio/)**
- Polished, publication-ready artifacts
- Code and documentation
- Portfolio narratives
- What you publish to GitHub
- What you want the world to see

---

## When to Link

**Trigger:** You have a completed piece of work that's portfolio-worthy.

Examples:
- ✅ You finished a Bicep module with architecture decisions
- ✅ You built an agent with clear design thinking
- ✅ You created automation that solved a business problem
- ✅ You learned something foundational enough to teach

---

## The Linking Process (Step by Step)

### **Phase 1: Verify It's Ready**
In `storytelling-engine/projects/[name]/`:

```
✓ Field notes captured? (notes.md exists)
✓ ADR or Architecture Summary written? (artifacts/adr/ or artifacts/architecture-summary/)
✓ Code/module in place? (code/ or external link)
✓ Portfolio Narrative Skill applied? (positioned for external readers)
✓ QA gate passed? (no outstanding issues)
```

If YES to most → Ready to link.  
If NO → Go back and finish internal work first.

---

### **Phase 2: Create Public Project Folder**

In `github-portfolio/projects/[project-name]/`:

```
github-portfolio/projects/[project-name]/
├── README.md                    ← Public-facing overview
├── code/                        ← Source code (or reference)
├── docs/
│   ├── architecture.md          ← Copy from internal ADR/summary
│   ├── decisions.md             ← Key design choices
│   └── evolution.md             ← Future direction
├── diagrams/
│   └── [mermaid diagrams]
└── PORTFOLIO-NOTES.md           ← Links back to internal
```

---

### **Phase 3: Write the GitHub README**

This is **different** from your internal README.

**Internal README** (`storytelling-engine/`):
- What the project is
- Status
- Quick links to artifacts
- For you and your team

**GitHub README** (`github-portfolio/`):
- **Why** you built it (problem it solves)
- **How** it works (architecture overview)
- **What** you learned (professional growth)
- **How** it demonstrates your engineering thinking
- How to use it / what to look at

**Structure:**
```markdown
# [Project Name]

## The Problem
What business/technical problem does this solve?
Why did you tackle it?

## The Solution
High-level architecture.
Key design decisions.
Why you chose this approach.

## Technical Deep Dive
[Link to architecture summary or ADR]

## Key Insights
What did you learn?
What would you do differently?
What does this teach someone about your engineering?

## Code & Artifacts
[Links to code, modules, etc]

## Design Decisions
[Link to ADR-001, ADR-002, etc]

## Evolution Path
Where could this go next?
How would you extend it?

## Portfolio Insight
Why this matters as a portfolio piece:
- Shows [specific skill]
- Demonstrates [engineering principle]
- Solves [type of problem]
```

---

### **Phase 4: Copy & Adapt Documents**

From internal → public:

**File: `storytelling-engine/projects/[name]/artifacts/adr/ADR-001.md`**
↓ Copy and adapt for external readers ↓
**File: `github-portfolio/projects/[name]/docs/ADR-001.md`**

(Remove internal-only context, keep the reasoning)

**File: `storytelling-engine/projects/[name]/artifacts/architecture-summary/summary.md`**
↓ Copy and adapt ↓
**File: `github-portfolio/projects/[name]/docs/architecture.md`**

---

### **Phase 5: Create PORTFOLIO-NOTES.md**

Link back to your internal work:

```markdown
# Internal Documentation

This project's full internal analysis:

## Field Notes
[storytelling-engine/field-notes/[project-slug]/]
```

Why? **Because your process matters.**

Hiring managers care about:
- How you think about problems
- Your design discipline
- Your iteration process
- Your architectural reasoning

By linking to internal field notes, you show them:
> "Here's the work. But here's also my thinking, my conversations, my iterations."

---

### **Phase 6: Gather Code**

Options:
1. **Code lives in this folder** → Copy to `github-portfolio/projects/[name]/code/`
2. **Code in separate repo** → Link to it in README
3. **Hybrid** → Summary + code in separate location

Whatever you choose, make it clear in your README.

---

### **Phase 7: Organize Diagrams**

From `storytelling-engine/projects/[name]/diagrams/`:
- Copy mermaid files to `github-portfolio/projects/[name]/diagrams/`
- Embed in README or docs
- Ensure they render on GitHub

---

### **Phase 8: Write PORTFOLIO-POSITIONING (Optional)**

If this is a major piece, create a narrative document:

```markdown
# Why This Project Matters

## Career Narrative
This project demonstrates:
- [Specific skill]
- [Problem-solving approach]
- [Engineering principle you embody]

## Audience
- Hiring managers looking for [role type]
- Engineers interested in [domain]
- Teams solving [problem class]

## Key Takeaways
1. [Insight 1 about the work]
2. [Insight 2 about your thinking]
3. [Insight 3 about the domain]

## What This Says About Me
This work signals:
- I think architecturally
- I reason about [constraints/trade-offs/scale]
- I document my decisions
- I iterate and learn
```

---

### **Phase 9: Link from Portfolio Summary**

In `github-portfolio/portfolio/projects-overview.md`:
- Add entry for this project
- One-line description
- Link to project folder

---

### **Phase 10: Ready for GitHub**

When Phase 1-9 complete:
- Commit to GitHub
- Link from your profile README
- Share with relevant communities (LinkedIn, Twitter, etc.)

---

## Quick Checklist

```
☐ Internal work complete (field notes + ADR)
☐ Portfolio Narrative Skill applied
☐ GitHub project folder created
☐ GitHub README written (why + how + what-you-learned)
☐ Docs copied & adapted (ADR, architecture summary)
☐ Code organized (in folder or linked)
☐ Diagrams included
☐ PORTFOLIO-NOTES.md links back to internal
☐ Added to portfolio-overview.md
☐ Ready to push to GitHub
```

---

## Examples of Linked Work

### Example 1: Cost Monitor Module
```
Internal:
  storytelling-engine/projects/azure-cost-monitor/
  ├── field-notes/2026-03-01-cost-monitor-overview.md
  ├── artifacts/adr/ADR-001-daily-polling.md
  └── code/cost-monitor.bicep

Public:
  github-portfolio/projects/azure-cost-monitor/
  ├── README.md (why I built it, how it works, what I learned)
  ├── docs/architecture.md (copied + adapted from ADR)
  ├── code/cost-monitor.bicep (same as internal)
  └── PORTFOLIO-NOTES.md (links back)
```

### Example 2: HR Automation Agent
```
Internal:
  storytelling-engine/field-notes/hr-automation-agent/
  ├── 2026-03-02-design-conversation.md
  ├── 2026-03-05-iteration-learnings.md
  └── storytelling-engine/projects/hr-automation-agent/...

Public:
  github-portfolio/projects/hr-automation-agent/
  ├── README.md (design thinking, constraint discovery, phasing)
  ├── docs/design-approach.md (agent design philosophy)
  ├── docs/phase1-learnings.md (iteration insights)
  └── PORTFOLIO-NOTES.md (links to all internal field notes)
```

---

## Why This Two-System Approach

**Internal storytelling engine:**
- Raw, honest, unfiltered
- For learning and processing
- Includes everything (finished, rough, exploratory)
- Only you see it

**GitHub portfolio:**
- Polished, curated, positioned
- For showing what you've built
- Only includes portfolio-worthy work
- The world sees it

**Linking them:**
- Shows your process, not just product
- Demonstrates architectural thinking
- Differentiates you from "just code on GitHub"
- Makes portfolio reviewers trust your work

---

## When NOT to Publish

Some work stays internal:
- One-off explorations
- Reference implementations
- Work still in iteration
- Highly specific to your workplace
- Not portfolio-strengthening

That's fine. Not everything needs to be public. But the best work should be documented both places — internal for reasoning, GitHub for impact.
