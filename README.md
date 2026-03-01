# Infrastructure as a Platform

This portfolio showcases my work in infrastructure engineering, cloud architecture, and platform design.

Each project includes:
- **Why** I built it — the problem it solves
- **How** it works — architecture and design reasoning  
- **What** I learned — reflections and design decisions
- Code, diagrams, and architectural documentation

## Projects

Browse by category or see [all projects](portfolio/projects-overview.md).

### Infrastructure & IaC
- Cloud architecture for hybrid environments
- Infrastructure-as-code patterns and tooling
- Cost-aware infrastructure design

### AI & Automation
- Intelligent systems and agent design
- Workflow automation and platform integration
- AI-augmented infrastructure

### Platform Engineering
- Reusable infrastructure components
- Platform abstractions and design patterns
- Cross-functional system design

---

## What This Portfolio Shows

**Not just code — reasoning.**

Each project documents:
- Architectural decisions and trade-offs
- Constraints that shaped design choices
- Evolution path and long-term thinking
- Problem-solving approach

See the [portfolio landing page](portfolio/) to learn more about my engineering philosophy.

## Featured: Storytelling Engine System

**[Explore →](projects/storytelling-engine/README.md)**

A comprehensive system for capturing, curating, and publishing work intentionally. Rather than waiting for "perfect" projects to happen, this system is *designed* to systematically document thinking, reason through decisions, and build a career narrative continuously.

Demonstrates systems thinking applied to knowledge management and portfolio development.

---

## Learning Lifecycle System

**Continuous Knowledge Evolution**

Integrated into the storytelling engine is a comprehensive learning system that captures, reinforces, and validates knowledge through three complementary skills:

### Core Learning Skills

**Note-Taking** — Structured capture with quality gates
- Four-axis extraction (WHAT, WHY, CONSTRAINTS, LEARNING)
- Actionable insights with connections to other knowledge
- Quality gate: Keep or Discard (only valuable notes enter spaced repetition)

**Flashcards** — Spaced repetition for retention
- One concept per card, testable format
- Spaced review schedule (Days 1, 3, 7, 14, 30)
- Grounded in architecture decisions and learning outcomes

**Scenario Generation** — Validate learning through simulation
- Realistic test scenarios based on real constraints
- Hypothesis → outcome → learning loop
- Strengthens deep understanding of design decisions

**See:** [Learning Lifecycle System](docs/LEARNING-SYSTEM.md)

---

## Backup & Version Control System

**Time-Machine Backups for Everything**

Built-in backup infrastructure ensures all work is protected with granular, timestamped recovery:

### Three-Layer Backup Strategy

**Incremental Backups** — Every change, just the files changing
- Auto-backup before any modification
- Preserves folder structure in backup
- Complete manifest of what changed and why
- 7-day retention with auto-cleanup

**Full Workspace Snapshots** — Safety checkpoints
- Manual snapshots before major refactors
- Complete workspace preservation
- Easy rollback to known-good states
- 7-day retention

**Portfolio Commit Backups** — Git-linked version control
- Auto-backup on every commit (via git hook)
- Linked to commit hash and message
- Full portfolio state at each commit point
- 7-day retention

### Recovery Capabilities

- Browse all backups with descriptions and timestamps
- Restore any incremental backup in seconds
- Safety backup created automatically before restore
- Complete audit trail of all changes

**See:** [Backup System](docs/BACKUP-SYSTEM.md)

---

## Browse This Portfolio

```
projects/
├── [project-name]/
│   ├── README.md                  ← Overview & architecture
│   ├── code/                      ← Source code & modules
│   ├── docs/                      ← Design docs, ADRs
│   └── diagrams/                  ← Architecture diagrams
│
portfolio/
├── README.md                      ← My engineering philosophy
└── projects-overview.md           ← All projects listed
```

---

## Questions?

Each project README explains:
- What problem it solves
- Why I chose this approach
- How it demonstrates specific engineering principles
- Where to find the code and detailed documentation
