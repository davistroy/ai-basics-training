# Week 4: Multi-Step Agents

**Block:** 3 - AI Automation Architecture
**Duration:** 45 min live workshop + 75 min self-paced exercises

---

## Entry Criteria

- [ ] Multiple MCP servers configured
- [ ] Tool chaining implemented
- [ ] 10+ agent executions logged
- [ ] Error handling robust

## Exit Criteria

- [ ] Agent handles complex multi-step tasks
- [ ] Planning/execution split understood
- [ ] Agent maintains context across steps
- [ ] Checkpoint/resume capability implemented
- [ ] Long-running task management in place

---

## Workshop Content (45 minutes)

### Segment 1: Complex Task Decomposition (10 min)

**The challenge:** Single-prompt agents struggle with complex tasks

**The solution:** Explicit planning and step execution

**Two-phase approach:**
```
Phase 1: PLAN
- Analyze the full task
- Break into discrete steps
- Identify dependencies
- Estimate effort/risk

Phase 2: EXECUTE
- Execute steps in order
- Validate each step
- Adjust plan if needed
- Report progress
```

**Planning prompt pattern:**
```markdown
Given this task: [TASK]

Create an execution plan:
1. List all steps needed
2. Identify dependencies between steps
3. Note which tools each step requires
4. Estimate complexity (simple/medium/complex)
5. Identify potential failure points

Output as structured plan.
```

### Segment 2: State Management Across Steps (14 min)

**Context Architecture - The Four Tiers:**

Not everything belongs in active context:

| Tier | What | Example | Loading |
|------|------|---------|---------|
| **Tier 1: Working Context** | Active now | Current prompt, immediate task | Always loaded |
| **Tier 2: Session State** | This conversation | Structured event stream | Filtered as needed |
| **Tier 3: Persistent Memory** | Across sessions | Progress records, learnings | Retrieved on-demand |
| **Tier 4: Artifacts** | Large data | Files, databases | Referenced, not pasted |

**The Attention Budget:**
- Context is a finite resource
- Find the SMALLEST set of HIGH-SIGNAL tokens
- More context often makes performance WORSE (research-backed)
- Progressive disclosure over pre-loading

**For your multi-step agent:**
- Tier 1: Current step instructions only
- Tier 2: Step results and running summary
- Tier 3: Checkpoint files
- Tier 4: Full documents referenced by path

**State management strategies:**

1. **Explicit state object:**
```json
{
  "task_id": "unique-id",
  "current_step": 3,
  "completed_steps": [1, 2],
  "step_results": {
    "step_1": { "status": "success", "output": "..." },
    "step_2": { "status": "success", "output": "..." }
  },
  "context": {
    "key_decisions": [],
    "important_data": {}
  }
}
```

2. **Running summary:**
   - After each step, summarize progress
   - Include in next step's context
   - Prevents context window overflow

3. **Checkpoint files:**
   - Save state to file after each step
   - Enables resume after failure
   - Audit trail for debugging

### Segment 3: Checkpoint and Resume (12 min)

**Why checkpoints matter:**
- Long tasks may fail midway
- Expensive to restart from beginning
- Enables reliable multi-day tasks

**Checkpoint implementation:**
```
FOR each step:
  Load checkpoint (if exists)
  IF step already completed:
    Skip to next
  ELSE:
    Execute step
    Save checkpoint
  Validate before continuing
```

**Checkpoint file structure:**
```json
{
  "checkpoint_id": "chk-20241230-001",
  "task_id": "task-xyz",
  "timestamp": "2024-12-30T10:30:00Z",
  "phase": "execution",
  "current_step": 3,
  "total_steps": 7,
  "state": { /* full state object */ },
  "recoverable": true,
  "notes": "Completed data gathering, starting analysis"
}
```

### Segment 4: Long-Running Task Patterns (9 min)

**Handling extended tasks:**
- Break into session-sized chunks
- Clear handoff between sessions
- Human check-in points

**Progress reporting:**
```
[Step 2/7] Gathering data from source A... ✓ Complete
[Step 3/7] Analyzing patterns... In Progress (45%)
```

**Timeout management:**
- Set maximum time per step
- Save and resume on timeout
- Alert on extended delays

---

## Self-Paced Exercises (75 minutes total)

### Exercise 4.1: Task Planning System (30 minutes)

*Implement structured planning*

1. **Create planning prompt:**

```markdown
# Task Planning Prompt

## System Message
You are a task planning agent. Your job is to analyze complex tasks and create detailed execution plans.

## Instructions
Given a task, create a plan with:

1. **Task Analysis**
   - What is the core objective?
   - What are the key deliverables?
   - What constraints exist?

2. **Step Breakdown**
   For each step provide:
   - Step number and name
   - Description of what happens
   - Required inputs
   - Expected outputs
   - Tools needed
   - Dependencies (which steps must complete first)
   - Estimated complexity (simple/medium/complex)
   - Potential failure points

3. **Execution Order**
   - List steps in execution order
   - Note any parallel opportunities
   - Identify critical path

4. **Validation Checkpoints**
   - After which steps to validate?
   - What to check?
   - Go/no-go criteria

## Output Format
\`\`\`json
{
  "task_summary": "...",
  "total_steps": N,
  "estimated_complexity": "...",
  "steps": [
    {
      "step_number": 1,
      "name": "...",
      "description": "...",
      "inputs": [...],
      "outputs": [...],
      "tools": [...],
      "dependencies": [],
      "complexity": "simple|medium|complex",
      "failure_risks": [...]
    }
  ],
  "execution_order": [1, 2, 3, ...],
  "checkpoints": [...]
}
\`\`\`
```

2. **Test with your agent task:**
   - Submit your capstone task for planning
   - Review generated plan
   - Refine based on output

3. **Integrate planning into agent:**
   - Add planning phase before execution
   - Store plan for reference during execution

**Deliverable:** Planning prompt + generated plan for your agent

---

### Exercise 4.2: State Management Implementation (25 minutes)

*Build reliable state tracking*

1. **Create state management system:**

```markdown
# State Management Design

## State Object Schema
\`\`\`json
{
  "$schema": "agent-state-v1",

  "execution": {
    "task_id": "string",
    "started_at": "ISO-8601",
    "status": "planning|executing|paused|completed|failed"
  },

  "plan": {
    "total_steps": 0,
    "steps": []
  },

  "progress": {
    "current_step": 0,
    "completed_steps": [],
    "failed_steps": []
  },

  "step_results": {
    "step_1": {
      "status": "pending|in_progress|success|failed",
      "started_at": null,
      "completed_at": null,
      "output": null,
      "error": null
    }
  },

  "context": {
    "key_decisions": [],
    "accumulated_data": {},
    "important_findings": []
  },

  "metadata": {
    "last_updated": "ISO-8601",
    "checkpoint_count": 0,
    "total_duration_seconds": 0
  }
}
\`\`\`

## State Operations

### Initialize State
[When and how to create initial state]

### Update State
[After each step completion]

### Read State
[At each step start]

### Save Checkpoint
[When to persist to file]

### Load Checkpoint
[How to resume from file]
```

2. **Implement in your agent:**
   - Add state initialization
   - Update state after each step
   - Include state in context for each step

**Deliverable:** State management design + implementation

---

### Exercise 4.3: Checkpoint System (20 minutes)

*Enable recovery and resume*

1. **Implement checkpoint system:**

```markdown
# Checkpoint Implementation

## Checkpoint Triggers
Save checkpoint:
- [ ] After each step completion
- [ ] Before risky operations
- [ ] On error (before failing)
- [ ] Periodically (every N minutes)

## Checkpoint Storage
- Location: `/agents/[name]/checkpoints/`
- Filename: `chk-[task_id]-[step]-[timestamp].json`
- Retention: Keep last 5 checkpoints

## Checkpoint Contents
\`\`\`json
{
  "checkpoint_id": "chk-xxx",
  "created_at": "ISO-8601",
  "task_id": "xxx",
  "resumable": true,
  "state": { /* full state object */ },
  "next_step": { /* what to do on resume */ },
  "context_summary": "Human-readable summary of progress"
}
\`\`\`

## Resume Process
1. Find latest checkpoint for task
2. Validate checkpoint integrity
3. Load state
4. Display summary for confirmation
5. Resume from next_step

## Testing
- [ ] Create checkpoint mid-task
- [ ] Simulate failure
- [ ] Resume from checkpoint
- [ ] Verify correct continuation
```

2. **Test checkpoint/resume:**
   - Run agent partially
   - Stop execution
   - Resume from checkpoint
   - Verify correct continuation

**Deliverable:** Checkpoint system + successful resume test

---

## Key Takeaways

1. **Plan before execute** - Complex tasks need explicit planning
2. **The Four Tiers of context** - Not everything belongs in active context
3. **State management enables multi-step** - Track progress explicitly
4. **Checkpoints enable recovery** - Save state for resume on failure
5. **Progressive disclosure** - Load context on-demand, not upfront

---

## Preparation for Week 5

- Complete checkpoint implementation
- Run a multi-step task end-to-end
- Document any state management challenges
- Next week: Agent specialization and orchestration

---

## Resources

- [State Management Patterns](https://docs.anthropic.com/en/docs/agents)
- [Long-Running Processes](https://martinfowler.com/articles/patterns-of-distributed-systems/saga.html)
