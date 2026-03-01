# GitHub Portfolio Vault

This folder contains **public-ready artifacts** intended for GitHub publication.

It's the **outbound** version of your work — polished, linked, and portfolio-positioned.

## Structure

```
github-portfolio/
├── README.md                          ← This file (vault overview)
├── LINKING-GUIDE.md                   ← How to link internal → public
│
├── projects/
│   ├── [project-name]/
│   │   ├── README.md                  ← Project overview for GitHub
│   │   ├── code/                      ← Actual source code
│   │   ├── docs/                      ← Architecture docs, design docs
│   │   ├── diagrams/                  ← Mermaid or other diagrams
│   │   └── PORTFOLIO-NOTES.md         ← Link to internal field notes
│   │
│   ├── hybrid-platform-iac/
│   ├── ai-agent-framework/
│   ├── cost-monitoring-module/
│   └── [more projects...]
│
├── portfolio/
│   ├── README.md                      ← Portfolio landing page (profile-level)
│   ├── projects-overview.md           ← Your projects at a glance
│   ├── architecture-patterns.md       ← Cross-project architectural themes
│   ├── ai-automation-work.md          ← Dedicated to agent/automation
│   └── [more standalone content...]
│
└── public-templates/
    ├── project-readme-template.md
    ├── architecture-summary-template.md
    └── portfolio-artifact-template.md
```

---

## Two Types of Content Here

### **1. Project Folders** (`projects/[name]/`)
Each project you publish gets:
- **README.md** — Project overview (what it does, why it matters, how to use)
- **code/** — Actual source code, modules, scripts
- **docs/** — Architecture reasoning, design decisions, ADRs
- **diagrams/** — Visual architecture
- **PORTFOLIO-NOTES.md** — Link back to your internal field notes + storytelling engine artifacts

### **2. Portfolio Content** (`portfolio/`)
General portfolio materials:
- Your portfolio landing page (links to all projects)
- Cross-project themes (architecture patterns, AI integration, cost-awareness)
- Standalone narratives ("Here's how I think about hybrid cloud")
- Showcases of your methodologies

---

## The Linking Philosophy

**Internal System** (storytelling-engine/)
```
└── field-notes/project/
    └── notes about what you learned/built
└── projects/project/
    └── artifacts/ (ADRs, architecture summaries)
```

**External System** (github-portfolio/)
```
└── projects/project/
    └── PORTFOLIO-NOTES.md
        "See my internal analysis here: [link]"
    └── docs/
        └── ADR-001.md (copy from internal)
    └── README.md
        "This is why I built this, how it works, what you learn from it"
```

---

## Workflow: Internal → Public

```
INTERNAL WORK
(storytelling-engine/)
    ↓
Field notes captured
    ↓
ADR/Architecture Summary created
    ↓
DECISION: Portfolio-worthy?
    ├─ YES
    │  ↓
    │  Create project in github-portfolio/
    │  Copy polished docs + code
    │  Write README for external readers
    │  Link back to internal field notes
    │  Commit to GitHub
    │
    └─ NO
       Keep internal, don't publish
```

---

## Connection to GitHub

This folder is ready to become (or be linked from) a GitHub repository.

### **Option A: One Repo for Everything**
```
your-github-username/portfolio
├── projects/
│   ├── project-a/
│   ├── project-b/
│   └── ...
├── portfolio/
│   └── README.md
└── README.md (profile readme)
```

### **Option B: Multiple Repos**
```
your-github-username/
├── hybrid-platform-iac/       (separate repo)
├── ai-agent-framework/        (separate repo)
├── portfolio/                 (this folder)
└── [org profile README]
```

### **Option C: Hybrid**
```
your-github-username/portfolio/
├── projects/
│   ├── project-a/             (links to separate repo)
│   ├── project-b/             (links to separate repo)
│   └── local-projects/         (code stored here)
└── portfolio docs/
```

Choose what fits your GitHub strategy. This folder structure works with all three.

---

## How to Use

### **Step 1: Finish Internal Work**
Complete your field notes, ADR, and architecture summary in `storytelling-engine/`.

### **Step 2: Decide: Publish This?**
Is this portfolio-worthy? Does it show off your engineering thinking?

**If NO:** Leave it internal. Done.

**If YES:** Continue to Step 3.

### **Step 3: Create Project Folder**
```
mkdir github-portfolio/projects/[project-name]
```

### **Step 4: Gather Artifacts**
From `storytelling-engine/projects/[name]/artifacts/`:
- Copy ADR or Architecture Summary
- Copy any diagrams
- Gather code/modules

### **Step 5: Write GitHub README**
Create `github-portfolio/projects/[name]/README.md` that:
- Opens with "why I built this" (not just "what it does")
- Links to architecture decision documents
- Shows how it aligns with your engineering pillars
- Points to code/implementation
- References internal field notes (optional link)

### **Step 6: Link Back**
In `github-portfolio/projects/[name]/PORTFOLIO-NOTES.md`:
```markdown
# Internal Documentation

This project's internal analysis lives here:
- Field notes: `storytelling-engine/field-notes/[project]/`
- ADR/Architecture: `storytelling-engine/projects/[name]/artifacts/`
- Learning notes: `storytelling-engine/learning/topics/[related]/`
```

### **Step 7: Sync to GitHub**
When ready, connect this folder to GitHub and push.

---

## Key Principle

**This is the "publication" layer.**

Everything here should be:
- ✅ Polished
- ✅ External-reader friendly
- ✅ Linked back to internal reasoning
- ✅ Positioned for portfolio impact

If something is rough, unrefined, or just for you — it stays in `storytelling-engine/`.

---

## What's Not Here (Yet)

You'll populate this based on your real work:
- Actual project folders
- Code repositories
- Architecture documents
- Portfolio narratives

Start with your next completed piece of work and create a project folder.

---

## Quick Reference

| Folder | Purpose | Audience |
|--------|---------|----------|
| `storytelling-engine/` | Your working vault | You |
| `storytelling-engine/field-notes/` | Raw learning captured | You + future self |
| `storytelling-engine/projects/` | Work + reasoning | You + team |
| `github-portfolio/` | **Polished for GitHub** | You + world |
| `github-portfolio/projects/` | Published projects | Hiring managers, peers |
| `github-portfolio/portfolio/` | Your narrative | Hiring managers, colleagues |
