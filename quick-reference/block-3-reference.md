# Block 3 Quick Reference Card
## AI Automation Architecture

---

## Two-Agent Architecture Pattern

```
SETUP AGENT (runs once)          WORKER AGENT (runs repeatedly)
─────────────────────────        ────────────────────────────────
• Takes human request            • Reads current state from records
• Creates structured records     • Picks ONE incomplete task
• Defines goals, procedures      • Does work, validates, updates
• Then STOPS                     • STOPS after each task

     ↓ Creates                        ↓ Reads/Updates
┌─────────────────────────────────────────────────────────────┐
│                    STRUCTURED RECORDS                        │
│  (Goals, Progress, Procedures) — The system's memory        │
└─────────────────────────────────────────────────────────────┘
```

---

## Three Pillars of Domain Memory

| Pillar | What It Contains | Example |
|--------|------------------|---------|
| **Explicit Goals** | Testable success criteria | "All tests pass" not "Build login" |
| **Progress Records** | What's done, attempted, failed | "Tuesday: Approach A → timeout" |
| **Operating Procedures** | How to validate, when to escalate | "After change, run tests" |

---

## Agent Loop Pattern

```
START
  ↓
[Receive task/context]
  ↓
[Analyze] ←───────────────┐
  ↓                       │
[Decide next action]      │
  ↓                       │
[Execute with tool]       │
  ↓                       │
[Observe result]          │
  ↓                       │
[Goal achieved?]──No──────┘
  ↓ Yes
[Final output]
  ↓
END
```

**Safety limits:** Max iterations, timeout, consecutive error limit

---

## The 3-Failure Rule

```
Attempt 1: Fail → Agent reads error, adapts
Attempt 2: Fail → Agent tries different approach
Attempt 3: Fail → STOP and escalate to human

Why: After 3 failures, agent is stuck. More attempts won't help.
```

---

## Orchestration Patterns

| Pattern | When to Use | Complexity |
|---------|-------------|------------|
| **Sequential** | Clear stages, dependencies | Low |
| **Master-Worker** | Decomposable, parallelizable | Medium |
| **Parallel** | Independent analyses | Medium |
| **Team-Based** | Complex collaboration | High |

**Start simple:** Sequential or Master-Worker for most consulting tasks

---

## Context Tiers

| Tier | What | Load When |
|------|------|-----------|
| **1: Working** | Current prompt, task | Always |
| **2: Session** | Conversation state | Filter as needed |
| **3: Persistent** | Cross-session memory | On-demand |
| **4: Artifacts** | Files, databases | Reference only |

**Key insight:** Don't dump everything into context. Curate ruthlessly.

---

## State Object Template

```json
{
  "task_id": "unique-id",
  "status": "executing",
  "current_step": 3,
  "completed": [1, 2],
  "results": {
    "step_1": {"status": "success", "output": "..."},
    "step_2": {"status": "success", "output": "..."}
  },
  "context": {
    "key_decisions": [],
    "important_data": {}
  }
}
```

---

## Reliability Patterns

| Pattern | Purpose |
|---------|---------|
| **Circuit Breaker** | Stop calling failing services |
| **Timeout + Retry** | Don't wait forever, try again |
| **Graceful Degradation** | Partial success > total failure |
| **Checkpoint/Resume** | Recover from mid-task failures |

---

## Production Readiness Checklist

- [ ] Error handling for all failure modes
- [ ] Logging of all executions
- [ ] Alerting on failures
- [ ] Checkpoint/resume capability
- [ ] Performance within targets
- [ ] Cost within budget
- [ ] Security review complete
- [ ] Documentation complete
- [ ] Rollout plan ready

---

## ROI Quick Calculation

```
Time Saved = (Manual Minutes - Agent Minutes) × Executions
Value = Time Saved × Hourly Rate
Cost = AI API + Platform + Maintenance
Net ROI = Value - Cost
Payback = Development Investment ÷ Monthly Net Benefit
```

---

## Key Reminders

✓ Agents don't have memory—systems do
✓ Smaller agents = better performance
✓ 90% success rate = 10% failure rate (unacceptable for production)
✓ If you can't see it, you can't fix it
✓ Every production agent needs a kill switch
