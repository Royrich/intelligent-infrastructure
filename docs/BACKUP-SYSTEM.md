# Backup & Version Control System

Three-layer backup infrastructure for time-machine recovery at any granularity.

## Why This Matters

In knowledge work, recovery velocity matters. When you make a mistake or change your mind, being able to restore to a known-good state in seconds—not minutes or hours—keeps momentum. This system makes that possible.

---

## Three Layers of Protection

### Layer 1: Incremental Backups — Every Change, Just the Files Changing

**Trigger:** Automatic before every modification  
**What gets backed up:** Only the files being changed  
**Preservation:** Folder structure intact, complete manifest of what changed

**How it works:**
1. You ask me to update `LEARNING-LIFECYCLE.md`
2. I backup *only that file* with timestamp and reason
3. I make the change
4. You have a restore point for that specific change

**Example backup structure:**
```
Backups/Workspace/Incremental/2026-03-01-224232/
├── manifest.json
│   ├── reason: "Add Keep/Discard gate to Note-Taking"
│   ├── files: 1
│   └── timestamp: 2026-03-01-224232
└── storytelling-engine/
    └── LEARNING-LIFECYCLE.md (backup of that file)
```

**Restore time:** < 30 seconds  
**Scope:** Pinpoint—restore exactly what you want  

---

### Layer 2: Full Workspace Snapshots — Safety Checkpoints

**Trigger:** Manual, before major refactors or architecture changes  
**What gets backed up:** Complete workspace (excludes git history, node_modules)  
**Preservation:** One complete snapshot per trigger

**How it works:**
1. About to make major system changes
2. Create full snapshot with description
3. System backups entire workspace structure
4. You can restore to that complete state anytime

**Example backup:**
```
Backups/Workspace/2026-03-01-142530/
├── manifest.json
│   ├── description: "Before updating ORCHESTRATION-LAYER and PIPELINES"
│   ├── size: 145 MB
│   └── files: 1247
└── [entire workspace snapshot]
```

**Restore time:** 1-2 minutes (full restore)  
**Scope:** Complete—go back to known-good architectural state  

---

### Layer 3: Portfolio Commit Backups — Git-Linked Version Control

**Trigger:** Automatic on every git commit (via post-commit hook)  
**What gets backed up:** Portfolio folder at each commit  
**Preservation:** Linked to commit hash and message

**How it works:**
1. You make changes to portfolio files
2. You `git commit`
3. Git hook automatically runs backup
4. Backup timestamped with commit hash and message
5. You have portfolio snapshot at each commit

**Example backup:**
```
Backups/GitHub-portfolio/2026-03-01-222210-44ed008/
├── manifest.json
│   ├── commit_hash: 44ed008
│   ├── commit_message: "Upload first portfolio work"
│   └── timestamp: 2026-03-01-222210
└── [portfolio folder snapshot]
```

**Restore time:** < 30 seconds (portfolio-specific)  
**Scope:** Portfolio only—isolated from workspace changes  

---

## Recovery Workflows

### Undo Last Document Change
```
Tools:
  .\restore-incremental-backup.ps1 -Type workspace

Flow:
  1. See list of incremental backups (most recent first)
  2. Pick the one you want
  3. Confirm (shows what will be overwritten)
  4. Done—file restored to previous state
```

### Restore to Yesterday's Workspace State
```
Tools:
  .\restore-backup.ps1 -Type workspace

Flow:
  1. See full workspace snapshots with timestamps
  2. Pick one from yesterday
  3. Get safety backup created automatically
  4. Restore completes
  5. If something's wrong, restore the safety backup
```

### Revert Portfolio to Specific Commit
```
Tools:
  .\restore-backup.ps1 -Type portfolio

Flow:
  1. See all portfolio backups linked to commits
  2. Pick backup from commit X
  3. Portfolio restored to that commit state
  4. You can still undo this via safety backup
```

---

## Key Design Principles

✅ **Incremental by default** — Minimal backups for fast iteration  
✅ **Full snapshots on demand** — Fallback for major changes  
✅ **Automatic portfolio versioning** — Every commit is safe/restorable  
✅ **Safety backups** — Restore creates snapshot before overwriting  
✅ **Complete manifests** — Know exactly what each backup contains  
✅ **7-day retention** — Auto-cleanup keeps storage sane  
✅ **No deletion philosophy** — Everything archived, nothing lost  

---

## Typical Scenarios

### Scenario 1: Quick Fix
```
"Update SKILLS-REFERENCE.md with new skill category"
↓ [incremental backup of SKILLS-REFERENCE.md]
↓ [make change]
↓ [done in 2 minutes with full recovery point]
```

### Scenario 2: Major Refactor
```
"Reorganize learning system with new skill structure"
↓ [create full workspace snapshot]
↓ [make changes to 5+ files]
↓ [test]
↓ [if needed: restore full snapshot, start over]
```

### Scenario 3: Portfolio Work
```
"Add case study to portfolio about agent architecture"
↓ [make changes, git add ., git commit]
↓ [automatic portfolio backup runs]
↓ [portfolio accessible at that commit point forever]
```

---

## Storage & Maintenance

**Space usage:**
- Incremental backup (1-2 files): 0.01-0.5 MB
- Full workspace snapshot: 100-150 MB
- Portfolio backup: 0.05-0.5 MB per commit

**Retention:**
- Backups older than 7 days auto-delete
- Safety backups preserved separately
- Git history maintained in repos (separate from backups)

**No manual maintenance:** Clean up happens automatically after each backup

---

## Built-In Transparency

Every backup includes a `manifest.json`:
```json
{
  "timestamp": "2026-03-01-224232",
  "reason": "Add Keep/Discard gate to Note-Taking",
  "files_backed_up": [
    {
      "path": "storytelling-engine/LEARNING-LIFECYCLE.md",
      "type": "file",
      "size_mb": 0.15
    }
  ],
  "total_files": 1,
  "total_size_mb": 0.15,
  "created_at": "2026-03-01T22:42:32.1234567+01:00"
}
```

You always know what was backed up, when, and why.

---

## Philosophy

This system embodies a specific principle: **make forward progress without fear**.

- Version control (git) handles code history
- Backups handle workspace/working state history
- Incremental backups handle granular change recovery
- Full backups handle architectural recovery

Together, you can experiment confidently knowing any state is recoverable.

---

## See Also

- [Backup Scripts & Commands](../../Backups/)
- [Storytelling Engine System Overview](../storytelling-engine/)
- [Project: Backup System Design](../projects/storytelling-engine/)
