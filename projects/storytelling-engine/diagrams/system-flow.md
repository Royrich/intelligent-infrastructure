## Pipeline: Scaffold

```mermaid
graph LR
    A["Start:<br/>New Project"] --> B["Brainstorm Skill<br/>(Explore solution space)"]
    B --> C["Dynamic Naming<br/>(Generate clear names)"]
    C --> D["Context Capture<br/>(Extract signals)"]
    D --> E["Documentation<br/>Formatting"]
    E --> F["Project Structure<br/>Ready"]
    
    style B fill:#fff9c4
    style C fill:#ffecb3
    style D fill:#ffe082
    style E fill:#ffd54f
    style F fill:#ffca28
```

**Output:** Named project with index structure ready for work

---

## Pipeline: Design Exploration

```mermaid
graph LR
    A["Raw Work"] --> B["Context Capture<br/>(What, why,<br/>constraints)"]
    B --> C["Architecture<br/>Reasoning<br/>(Why matters,<br/>trade-offs)"]
    C --> D["Diagram<br/>(Visualize<br/>structure)"]
    D --> E["Documentation<br/>Formatting<br/>(Structure<br/>consistently)"]
    E --> F["Voice<br/>(Apply identity<br/>& tone)"]
    F --> G["QA Gate<br/>(Check quality<br/>& completeness)"]
    G --> H["Finalize<br/>(Lock artifact,<br/>mark complete)"]
    H --> I["Internal Artifact<br/>(Vault-ready)"]
    
    style A fill:#e1f5ff
    style B fill:#b3e5fc
    style C fill:#81d4fa
    style D fill:#4fc3f7
    style E fill:#29b6f6
    style F fill:#03a9f4
    style G fill:#039be5,stroke:#d32f2f,stroke-width:2px
    style H fill:#0288d1
    style I fill:#0277bd
```

**Output:** Field notes, ADRs, or Architecture Summary — publication-ready internally

---

## Pipeline: Learning Cycle

```mermaid
graph TD
    A["Study Topic"] --> B["Note-Taking Skill<br/>(Distill learning)"]
    B --> C["DECISION: Keep<br/>Long-Term?"]
    C -->|NO| D["Discard<br/>(Learning stays,<br/>archive doesn't)"]
    C -->|YES| E["Add to vault<br/>(learning/topics/)"]
    E --> F{"Generate<br/>Practice Aids?"}
    F -->|Optional| G["Flashcards<br/>(Spaced recall)"]
    F -->|Optional| H["Scenarios<br/>(Applied practice)"]
    G --> I["Knowledge<br/>Compounds"]
    H --> I
    
    style B fill:#ce93d8
    style C fill:#ffccbc,stroke:#ff6f00,stroke-width:2px
    style D fill:#ffcdd2
    style E fill:#ba68c8
    style F fill:#ab47bc
    style G fill:#9c27b0
    style H fill:#8e24aa
    style I fill:#6a1b9a
```

**Output:** Curated long-term knowledge with optional reinforcement aids

---

## Complete System: Three Layers

```mermaid
graph TB
    subgraph Raw["📥 RAW WORK"]
        RW["Code, Design,<br/>Learning, Discussion"]
    end
    
    subgraph Scaffold["🏗️ SCAFFOLD PIPELINE"]
        Br["Brainstorm"]
        DN["Dynamic Naming"]
        CC["Context Capture"]
        DF["Documentation<br/>Formatting"]
    end
    
    subgraph Explore["🔍 DESIGN EXPLORATION PIPELINE"]
        CC2["Context Capture"]
        AR["Architecture<br/>Reasoning"]
        DG["Diagram"]
        DF2["Documentation<br/>Formatting"]
        VC["Voice &<br/>Identity"]
        QA["QA Gate"]
        FZ["Finalize"]
    end
    
    subgraph Internal["🔒 INTERNAL LAYER<br/>(storytelling-engine/)"]
        IA["Field Notes,<br/>ADRs,<br/>Architecture<br/>Summaries"]
    end
    
    subgraph Learn["📚 LEARNING PIPELINE"]
        NT["Note-Taking"]
        KD["Keep/Discard<br/>Gate"]
        FC["Flashcards<br/>(opt.)"]
        SC["Scenarios<br/>(opt.)"]
    end
    
    subgraph Learning["📚 LEARNING LAYER<br/>(learning/)"]
        LV["Curated Topics<br/>+ Practice Aids"]
    end
    
    subgraph PubPort["🌐 PORTFOLIO DECISION"]
        PG["Portfolio-Worthy?"]
    end
    
    subgraph Public["🌐 PUBLIC LAYER<br/>(github-portfolio/)"]
        PA["Published<br/>Projects"]
        GH["GitHub<br/>Repo"]
    end
    
    RW --> Br
    Br --> DN
    DN --> CC
    CC --> DF
    DF -->|Project Structure| IA
    
    RW --> CC2
    CC2 --> AR
    AR --> DG
    DG --> DF2
    DF2 --> VC
    VC --> QA
    QA -->|Approved| FZ
    FZ -->|Complete| IA
    
    IA -->|Extract Learning| NT
    NT --> KD
    KD -->|YES| FC
    KD -->|YES| SC
    KD -->|NO| D["🗑️ Discard<br/>Archive"]
    FC --> LV
    SC --> LV
    
    IA --> PG
    PG -->|YES| PA
    PG -->|NO| KeepInt["🔒 Keep Internal"]
    PA -->|Publish| GH
    
    style Raw fill:#e1f5ff,stroke:#01579b,stroke-width:2px
    style Scaffold fill:#fff9c4,stroke:#f57c00,stroke-width:2px
    style Explore fill:#fff9c4,stroke:#f57c00,stroke-width:2px
    style Internal fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    style Learn fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    style Learning fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    style PubPort fill:#ffccbc,stroke:#ff6f00,stroke-width:2px
    style Public fill:#e8f5e9,stroke:#388e3c,stroke-width:2px
    
    style QA fill:#ffccbc,stroke:#d32f2f,stroke-width:2px
    style KD fill:#ffccbc,stroke:#d32f2f,stroke-width:2px
    style PG fill:#ffccbc,stroke:#d32f2f,stroke-width:2px
```

---

## The 12 Skills & Their Application

| Skill | When Used | Transforms |
|-------|-----------|-----------|
| **Brainstorm** | Project start | Undefined space → Multiple options |
| **Dynamic Naming** | Project naming | Raw ideas → Clear descriptors |
| **Context Capture** | Work/learning complete | Raw experience → Structured signals |
| **Architecture Reasoning** | Explaining decisions | Decisions → Justified rationale |
| **Diagram** | When clarity needed | Complex systems → Visual models |
| **Note-Taking** | Learning moment | Study → Structured knowledge |
| **Flashcards** | Knowledge reinforcement | Notes → Recall testing |
| **Scenarios** | Applied learning | Knowledge → Practice situations |
| **Documentation Formatting** | Final polish | Rough artifact → Professional output |
| **Portfolio Narrative** | Before publication | Technical artifact → External story |
| **Voice** | Across all outputs | Variable tone → Consistent identity |
| **Observation Pattern** | Comparative analysis | Artifacts → Patterns across work |

---

## Decision Gates (Intentional Friction)

```mermaid
graph LR
    A["Field Note<br/>Captured"] --> B["Gate 1:<br/>Keep Learning?"]
    B -->|Yes| C["Add to vault<br/>(learning/topics/)"]
    B -->|No| D["Discard archive<br/>(learning persists)"]
    
    E["Artifact<br/>Finalized"] --> F["Gate 2:<br/>Portfolio<br/>Worthy?"]
    F -->|Yes| G["Move to<br/>github-portfolio/"]
    F -->|No| H["Keep internal<br/>(reference only)"]
    
    style B fill:#ffccbc,stroke:#ff6f00,stroke-width:3px
    style F fill:#ffccbc,stroke:#ff6f00,stroke-width:3px
    style C fill:#c8e6c9
    style D fill:#ffcdd2
    style G fill:#a5d6a7
    style H fill:#cfd8dc
```

Each gate ensures only high-signal work advances. **This is where intentionality happens.**

---

## Orchestration Features

**Context Store:** Stateful coordination across skill pipeline  
**Skill Registry:** Logs execution, enables audit and observability  
**Policy Engine:** Enforces voice, naming, QA consistently  
**Run Traces:** Complete history → reproducibility  
**Non-destructive Saves:** Soft Save (iterate) vs Finalize (lock)  
**QA Gates:** Pre-publication quality bar checks

