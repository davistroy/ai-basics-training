# **BLOCK 3 WEEK 4: Multi-Step Agents**

**Block:** 3: AI Automation Architecture
**Week:** 4 of 8
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Block Navigation:** [Week 3 Participant Guide](../week-3/participant-guide.md) | **Week 4** | [Week 5 Participant Guide](../week-5/participant-guide.md)

**In This Guide:**
- [Learning Objectives](#learning-objectives)
- [Key Concepts](#key-concepts)
- [Workshop Recap](#workshop-recap)
- [Self-Paced Exercises](#self-paced-exercises)
- [Templates & Resources](#templates--resources)
- [Self-Assessment](#self-assessment)
- [Getting Help](#getting-help)

---

## Learning Objectives

By the end of this week, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Create planning prompts that decompose complex tasks into steps | Exercise 4.1 |
| 2 | Implement state management using the Four Tiers of context | Exercise 4.2 |
| 3 | Build checkpoint/resume capability for long-running tasks | Exercise 4.3 |
| 4 | Apply progressive disclosure for efficient context management | All Exercises |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Multiple MCP servers configured (Week 3)
- [ ] Tool chaining implemented (Week 3)
- [ ] 10+ agent executions logged
- [ ] Error handling robust (Week 2)

**Not ready?** You must have a working multi-tool agent before proceeding. Multi-step agents build on tool chaining foundations.

---

## Key Concepts

### Concept 1: Complex Task Decomposition

**Definition:**
The process of breaking a large task into discrete, manageable steps with explicit planning before execution.

**Why It Matters:**
Single-prompt agents struggle with complex tasks. They get lost, produce poor results, or fail partway through. Explicit planning creates a roadmap the agent can follow.

**The Two-Phase Approach:**
```
Phase 1: PLAN
├─ Analyze the full task
├─ Break into discrete steps
├─ Identify dependencies
└─ Estimate effort/risk

Phase 2: EXECUTE
├─ Execute steps in order
├─ Validate each step
├─ Adjust plan if needed
└─ Report progress
```

**When to Use Planning:**
- Tasks with 5+ steps
- Multiple decision points
- Where getting lost is costly
- Complex dependencies between steps

**When NOT to Use:**
- Simple, single-step tasks
- Well-defined workflows
- Tasks that complete in 1-2 iterations

---

### Concept 2: The Four Tiers of Context

**Definition:**
A framework for organizing what information should be available to the agent at different levels of persistence and accessibility.

**Why It Matters:**
More context often makes performance WORSE. Research shows that stuffing context windows degrades agent performance. The Four Tiers help you curate ruthlessly.

**The Tiers:**

| Tier | What | Example | Loading |
|------|------|---------|---------|
| **Tier 1: Working Context** | Active now | Current prompt, immediate task | Always loaded |
| **Tier 2: Session State** | This conversation | Structured event stream | Filtered as needed |
| **Tier 3: Persistent Memory** | Across sessions | Progress records, learnings | Retrieved on-demand |
| **Tier 4: Artifacts** | Large data | Files, databases | Referenced, not pasted |

**The Attention Budget:**
> "Find the SMALLEST set of HIGH-SIGNAL tokens."

**For Multi-Step Agents:**
- Tier 1: Current step instructions only
- Tier 2: Step results and running summary
- Tier 3: Checkpoint files
- Tier 4: Full documents (referenced by path)

**Common Mistake:**
Loading entire task history into context. This dilutes focus and wastes tokens. Load only what's needed for the current step.

---

### Concept 3: State Management Strategies

**Definition:**
Approaches for tracking agent progress, decisions, and context across multiple steps and potentially multiple sessions.

**Three Strategies:**

**1. Explicit State Object:**
```json
{
  "task_id": "unique-id",
  "current_step": 3,
  "completed_steps": [1, 2],
  "step_results": {
    "step_1": { "status": "success", "output": "..." },
    "step_2": { "status": "success", "output": "..." }
  }
}
```
- Best for: Complex multi-step execution
- Pros: Complete visibility, easy to debug
- Cons: Must be maintained explicitly

**2. Running Summary:**
- After each step, summarize progress
- Include summary in next step's context
- Best for: Preventing context window overflow
- Pros: Human-readable, compact
- Cons: May lose detail

**3. Checkpoint Files:**
- Save state to file after each step
- Enables resume after failure
- Best for: Long-running tasks
- Pros: Recovery, audit trail
- Cons: File management overhead

**Recommendation:** Use all three together - state object for active tracking, summaries for context management, checkpoints for persistence.

---

### Concept 4: Checkpoint and Resume

**Definition:**
A pattern for saving agent state periodically so that interrupted tasks can be resumed rather than restarted.

**Why It Matters:**
Long tasks may fail midway. Network issues, timeouts, unexpected errors all happen. Without checkpoints, you restart from the beginning. With checkpoints, you resume where you left off.

**Checkpoint Implementation Pattern:**
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

**Checkpoint File Structure:**
```json
{
  "checkpoint_id": "chk-20241230-001",
  "task_id": "task-xyz",
  "timestamp": "2024-12-30T10:30:00Z",
  "phase": "execution",
  "current_step": 3,
  "total_steps": 7,
  "state": { /* full state object */ },
  "resumable": true,
  "next_step": { /* what to do on resume */ },
  "context_summary": "Human-readable progress summary"
}
```

**Resume Process:**
1. Find latest checkpoint for task
2. Validate checkpoint integrity
3. Load state
4. Display summary for confirmation
5. Resume from next_step

---

### Concept 5: Long-Running Task Patterns

**Definition:**
Strategies for handling tasks that span multiple sessions or extended time periods.

**Handling Extended Tasks:**
- Break into session-sized chunks
- Clear handoff between sessions
- Human check-in points at milestones

**Progress Reporting:**
```
[Step 2/7] Gathering data from source A... ✓ Complete
[Step 3/7] Analyzing patterns... In Progress (45%)
```

**Timeout Management:**
- Set maximum time per step
- Save checkpoint on timeout
- Resume in next session
- Alert on extended delays

---

### Quick Reference: State Schema

```json
{
  "$schema": "agent-state-v1",

  "execution": {
    "task_id": "string",
    "started_at": "ISO-8601",
    "status": "planning|executing|paused|completed|failed"
  },

  "plan": {
    "total_steps": 0,
    "steps": [
      {
        "step_number": 1,
        "name": "string",
        "description": "string",
        "dependencies": [],
        "status": "pending|in_progress|completed|failed"
      }
    ]
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
```

---

## Workshop Recap

### Session Summary

**Today's Focus:** Complex task decomposition, state management across steps, and checkpoint/resume capabilities.

**Key Points from Each Segment:**

**Segment 1: Complex Task Decomposition**
- Single-prompt agents struggle with complex tasks
- Two-phase approach: PLAN then EXECUTE
- Planning creates roadmap; execution follows it
- Use for 5+ step tasks with decision points

**Segment 2: State Management Across Steps**
- Four Tiers of context: Working, Session, Persistent, Artifacts
- The Attention Budget: smallest set of high-signal tokens
- State object tracks task_id, current_step, results
- Load only what's needed for current step

**Segment 3: Checkpoint and Resume**
- Long tasks may fail midway - checkpoints enable recovery
- Save state after each step completion
- Checkpoint includes everything needed to resume
- Test resume BEFORE you need it

**Segment 4: Long-Running Task Patterns**
- Break into session-sized chunks
- Progress reporting keeps stakeholders informed
- Timeout management with checkpoint saves

### Demo Recap

**What Was Demonstrated:**
Multi-step agent with checkpoint/resume capability

**Key Steps:**
1. Showed checkpoint file structure with state
2. Demonstrated checkpoint creation after step completion
3. Simulated failure mid-execution
4. Loaded checkpoint and resumed
5. Completed remaining steps from checkpoint state

**Result:**
Agent recovered from mid-execution failure using checkpoint, completing the task without restarting.

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 4.1 | 30 min | Planning prompt + generated plan | Task decomposition |
| 4.2 | 25 min | State management design + implementation | State tracking |
| 4.3 | 20 min | Checkpoint system + resume test | Recovery capability |

---

### Exercise 4.1: Task Planning System

**Duration:** 30 minutes

**Purpose:**
Create a planning prompt that breaks complex tasks into structured, actionable plans. This enables your agent to handle tasks too complex for single-prompt execution.

**You Will Create:**
A planning prompt and a generated plan for your capstone task.

---

#### Instructions

**Step 1: Create Planning Prompt**

```markdown
# Task Planning Prompt

## System Message
You are a task planning agent. Your job is to analyze complex tasks and create detailed execution plans.

## Instructions
Given a task, create a plan with:

### 1. Task Analysis
- What is the core objective?
- What are the key deliverables?
- What constraints exist?
- What resources are available?

### 2. Step Breakdown
For each step provide:
- **Step number and name:** Clear identifier
- **Description:** What happens in this step
- **Required inputs:** What information/data is needed
- **Expected outputs:** What this step produces
- **Tools needed:** Which MCP tools are required
- **Dependencies:** Which steps must complete first
- **Estimated complexity:** Simple/Medium/Complex
- **Potential failure points:** What could go wrong

### 3. Execution Order
- List steps in execution order
- Note any parallel opportunities
- Identify critical path (longest dependency chain)

### 4. Validation Checkpoints
- After which steps should we validate?
- What should we check?
- Go/no-go criteria for continuing

## Output Format
\`\`\`json
{
  "task_summary": "...",
  "total_steps": N,
  "estimated_complexity": "simple|medium|complex",
  "estimated_duration_minutes": N,
  "steps": [
    {
      "step_number": 1,
      "name": "...",
      "description": "...",
      "inputs": ["..."],
      "outputs": ["..."],
      "tools": ["..."],
      "dependencies": [],
      "complexity": "simple|medium|complex",
      "failure_risks": ["..."]
    }
  ],
  "execution_order": [1, 2, 3],
  "parallel_opportunities": [],
  "checkpoints": [
    {
      "after_step": 2,
      "check": "...",
      "go_criteria": "..."
    }
  ]
}
\`\`\`
```

**Step 2: Test with Your Capstone Task**

Submit your capstone task to the planning prompt:

```markdown
# Test Execution

## Task Submitted
[Paste your capstone task description]

## Generated Plan
[Paste the JSON plan output]

## Plan Review
- [ ] All steps are actionable
- [ ] Dependencies are logical
- [ ] Tools are available
- [ ] Complexity estimates are realistic
- [ ] Checkpoints are at appropriate points
```

**Step 3: Refine Based on Output**

Review the generated plan and refine:
- Are any steps too vague?
- Are dependencies correct?
- Are there missing steps?
- Are failure points realistic?

**Step 4: Integrate into Agent System Prompt**

Add planning capability to your system prompt:

```markdown
## Task Planning

When given a complex task (more than 3 steps):
1. First, create an execution plan using the planning format
2. Output the plan for review
3. Wait for confirmation before executing
4. Execute steps in order, reporting progress
5. Save checkpoint after each completed step
```

---

#### Deliverable Specification

**File Name:** `planning-prompt.md` + `capstone-plan.json`

**Location:** `/agents/[agent-name]/prompts/`

**Quality Criteria:**
- [ ] Planning prompt produces structured JSON output
- [ ] Generated plan covers all capstone task aspects
- [ ] Each step has all required fields
- [ ] Dependencies are logically correct
- [ ] Checkpoints are at meaningful points

---

### Exercise 4.2: State Management Implementation

**Duration:** 25 minutes

**Purpose:**
Build a state tracking system that maintains agent progress across steps, enabling multi-step execution with full visibility.

**You Will Create:**
State management design and implementation integrated with your agent.

---

#### Instructions

**Step 1: Design State Schema**

Create your state object schema:

```markdown
# State Management Design

## State Object Schema

\`\`\`json
{
  "$schema": "agent-state-v1",

  "execution": {
    "task_id": "string - unique identifier for this execution",
    "started_at": "ISO-8601 timestamp",
    "status": "planning|executing|paused|completed|failed"
  },

  "plan": {
    "total_steps": "number",
    "steps": [
      {
        "step_number": "number",
        "name": "string",
        "description": "string",
        "dependencies": ["step numbers"],
        "status": "pending|in_progress|completed|failed"
      }
    ]
  },

  "progress": {
    "current_step": "number - step being executed",
    "completed_steps": ["numbers - finished steps"],
    "failed_steps": ["numbers - failed steps"]
  },

  "step_results": {
    "step_N": {
      "status": "pending|in_progress|success|failed",
      "started_at": "ISO-8601 or null",
      "completed_at": "ISO-8601 or null",
      "output": "any - step output data",
      "error": "string or null"
    }
  },

  "context": {
    "key_decisions": ["important decisions made"],
    "accumulated_data": {},
    "important_findings": ["discoveries during execution"]
  },

  "metadata": {
    "last_updated": "ISO-8601",
    "checkpoint_count": "number",
    "total_duration_seconds": "number"
  }
}
\`\`\`

## State Operations

### Initialize State
- When: At start of new task
- How: Create state object with execution.status = "planning"
- Include: task_id, started_at

### Update State
- When: After each step completion
- How: Update step_results, progress, metadata
- Include: New outputs, timing, decisions

### Read State
- When: At each step start
- How: Load current state, extract relevant context
- Include: Only what's needed for current step (Tier 1)

### Save Checkpoint
- When: After successful step, before risky operations
- How: Serialize full state to file
- Include: Everything needed to resume

### Load Checkpoint
- When: On resume or recovery
- How: Read file, validate, restore state
- Include: Integrity check before loading
```

**Step 2: Implement State Operations**

Add to your system prompt:

```markdown
## State Management

### State File Location
State is stored at: /agents/[name]/state/current-state.json

### State Operations

At task start:
1. Generate unique task_id
2. Initialize state object
3. Set status to "planning"
4. Save initial state

At each step start:
1. Read current state
2. Check dependencies completed
3. Update current_step
4. Set step status to "in_progress"
5. Save state

At each step end:
1. Update step_results with output
2. Set step status to "success" or "failed"
3. Update completed_steps or failed_steps
4. Update last_updated timestamp
5. Save state (checkpoint)

### Running Summary
After each step, append to context.key_decisions:
"Step [N]: [Brief summary of what was done and decided]"

Include only the summary in next step's context, not full results.
```

**Step 3: Test State Tracking**

Run your agent through a multi-step task and verify:

```markdown
# State Management Test

## Test Execution
- Task: [Brief description]
- Total steps: [N]

## State Snapshots

### After Step 1
\`\`\`json
[Paste state excerpt]
\`\`\`
- Status correct: [Yes/No]
- Results captured: [Yes/No]

### After Step 2
\`\`\`json
[Paste state excerpt]
\`\`\`
- Status correct: [Yes/No]
- Results captured: [Yes/No]

## Verification
- [ ] task_id consistent throughout
- [ ] current_step advances correctly
- [ ] step_results accumulate
- [ ] timestamps update
- [ ] context.key_decisions growing
```

---

#### Deliverable Specification

**File Name:** `state-management.md` + `state-schema.json`

**Location:** `/agents/[agent-name]/`

**Quality Criteria:**
- [ ] State schema includes all required sections
- [ ] Operations are clearly defined
- [ ] Implementation tested with multi-step execution
- [ ] Running summary prevents context overload

---

### Exercise 4.3: Checkpoint System

**Duration:** 20 minutes

**Purpose:**
Implement checkpoint/resume capability so your agent can recover from failures without restarting.

**You Will Create:**
A working checkpoint system with tested resume capability.

---

#### Instructions

**Step 1: Define Checkpoint Strategy**

```markdown
# Checkpoint Implementation

## Checkpoint Triggers
Save checkpoint:
- [ ] After each step completion
- [ ] Before risky operations
- [ ] On error (before failing)
- [ ] Periodically (every N minutes if running long)

## Checkpoint Storage
- **Location:** /agents/[name]/checkpoints/
- **Filename:** chk-[task_id]-[step]-[timestamp].json
- **Retention:** Keep last 5 checkpoints per task

## Checkpoint Contents
\`\`\`json
{
  "checkpoint_id": "chk-xxx-step3-20241230T103000",
  "created_at": "2024-12-30T10:30:00Z",
  "task_id": "xxx",
  "resumable": true,
  "state": {
    // Full state object from Exercise 4.2
  },
  "next_step": {
    "step_number": 4,
    "name": "Process results",
    "dependencies_met": true
  },
  "context_summary": "Completed data gathering (steps 1-3). Ready to process results."
}
\`\`\`

## Resume Process
1. **Find checkpoint:** List checkpoints for task_id, select latest
2. **Validate:** Check checkpoint integrity (file not corrupted)
3. **Load:** Parse state object
4. **Confirm:** Display context_summary, ask for confirmation
5. **Resume:** Continue from next_step
```

**Step 2: Add to System Prompt**

```markdown
## Checkpoint and Resume

### Saving Checkpoints
After completing each step:
1. Create checkpoint object with current state
2. Set next_step to upcoming step
3. Write context_summary (human-readable progress)
4. Save to /agents/[name]/checkpoints/chk-[task_id]-[step]-[timestamp].json

### Resuming from Checkpoint
When asked to resume task [task_id]:
1. List checkpoint files for that task_id
2. Load the most recent checkpoint
3. Display context_summary
4. Confirm resume is desired
5. Load state and continue from next_step

### Checkpoint Management
- Keep last 5 checkpoints per task
- Delete older checkpoints after successful completion
- On failure, keep all checkpoints for debugging
```

**Step 3: Test Checkpoint/Resume**

This is critical - test BEFORE you need it:

```markdown
# Checkpoint System Test

## Test 1: Create and Verify Checkpoint
1. Start multi-step task
2. Complete 2 steps
3. Verify checkpoint created

**Checkpoint file:**
\`\`\`
[Filename]
\`\`\`

**Contents preview:**
\`\`\`json
[First 20 lines of checkpoint]
\`\`\`

**Verification:**
- [ ] File created in correct location
- [ ] Contains complete state
- [ ] next_step is correct
- [ ] context_summary is readable

## Test 2: Resume from Checkpoint
1. Stop/simulate failure after step 2
2. Resume using checkpoint
3. Verify continuation from step 3

**Resume command/prompt:**
[How you triggered resume]

**Result:**
- [ ] Loaded correct checkpoint
- [ ] Displayed context_summary
- [ ] Continued from correct step
- [ ] Did NOT repeat completed steps

## Test 3: Complete After Resume
1. Continue from resumed state
2. Complete all remaining steps
3. Verify final state is correct

**Final state:**
- [ ] All steps marked complete
- [ ] Total duration includes both sessions
- [ ] Checkpoint cleaned up (or retained per policy)
```

---

#### Deliverable Specification

**File Name:** `checkpoint-system.md` + test checkpoints

**Location:** `/agents/[agent-name]/checkpoints/`

**Quality Criteria:**
- [ ] Checkpoint triggers defined
- [ ] Storage location and naming specified
- [ ] Resume process documented
- [ ] Test 1 passed (checkpoint created)
- [ ] Test 2 passed (resume works)
- [ ] Test 3 passed (completion after resume)

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| Planning Prompt | Task decomposition | Exercise 4.1 |
| State Schema | State object structure | Exercise 4.2 |
| Checkpoint Format | Checkpoint file structure | Exercise 4.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Anthropic Agent Documentation | Documentation | [docs.anthropic.com](https://docs.anthropic.com/en/docs/agents) | State management patterns |
| Saga Pattern | Reference | [Martin Fowler](https://martinfowler.com/articles/patterns-of-distributed-systems/saga.html) | Long-running processes |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Create planning prompts for complex tasks | Generated plan in Exercise 4.1 | |
| 2 | Implement state management with Four Tiers | Working state tracking in Exercise 4.2 | |
| 3 | Build checkpoint/resume capability | Tested resume in Exercise 4.3 | |
| 4 | Apply progressive disclosure | Only relevant context loaded per step | |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 4.1 output | `planning-prompt.md` + `capstone-plan.json` | `/agents/[name]/prompts/` | |
| Exercise 4.2 output | `state-management.md` + `state-schema.json` | `/agents/[name]/` | |
| Exercise 4.3 output | `checkpoint-system.md` + test files | `/agents/[name]/checkpoints/` | |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** Which concept was most valuable for your agent?

2. **What's still fuzzy?** What do you need more practice or clarification on?

3. **How will state management change your agent?** What can it handle now?

4. **Did checkpoint resume work first try?** What did you learn from testing?

---

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Tag your cohort for state management tips

### Common Questions This Week

**Q: My state file is getting huge - is that normal?**
A: Keep state minimal. Step results should be summaries, not full outputs. Store large data in separate files (Tier 4).

**Q: When should I use running summary vs. full state?**
A: Running summary goes in context (Tier 1-2). Full state stays in files (Tier 3-4). Summary enables understanding; state enables recovery.

**Q: My checkpoint resume doesn't work - what do I check?**
A: Verify: 1) File actually exists, 2) JSON is valid, 3) next_step references valid step, 4) Dependencies are marked complete.

### When to Ask for Help

- **Before asking:** Verify state file syntax, check file paths, test simpler scenarios
- **Good to ask:** "My checkpoint loads but resume fails at [specific point]. State shows [excerpt]. What am I missing?"
- **Include:** State excerpt, error message, what you expected vs. what happened

---

## Looking Ahead

### Next Week Preview: Week 5 - Agent Specialization and Orchestration

**Focus:**
Coordinating multiple specialized agents, supervisor patterns, and managing agent handoffs.

**How It Builds on This Week:**
Your multi-step agent becomes one of several agents that work together. State management enables clean handoffs between agents.

**To Prepare:**
- [ ] Complete all Week 4 exercises
- [ ] Ensure checkpoint/resume is tested and working
- [ ] Run a complete multi-step task end-to-end
- [ ] Review your agent's specific capabilities

---

## Glossary

| Term | Definition |
|------|------------|
| Task Decomposition | Breaking a complex task into discrete, manageable steps |
| Four Tiers | Context organization: Working, Session, Persistent, Artifacts |
| Working Context | Information actively needed for current operation |
| Session State | Information relevant to current conversation/session |
| Persistent Memory | Information that persists across sessions |
| Artifacts | Large data referenced but not loaded into context |
| State Object | Structured representation of agent progress and context |
| Checkpoint | Saved state snapshot enabling resume after failure |
| Progressive Disclosure | Loading context on-demand rather than pre-loading |
| Attention Budget | The limited capacity of the context window |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [Week 3 Participant Guide](../week-3/participant-guide.md) | **Week 4** | [Week 5 Participant Guide](../week-5/participant-guide.md)
