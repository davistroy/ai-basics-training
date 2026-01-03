# **POWERPOINT PRESENTATION: BLOCK 3 WEEK 4**
## **Multi-Step Agents**

**Block:** 3: AI Automation Architecture
**Week Number:** 4
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 participants with multi-tool agents from Week 3

**Key Thesis:** Complex multi-step tasks require explicit planning separated from execution, with the Four Tiers of context management and checkpoint/resume capabilities transforming fragile prototypes into production-ready systems.

**Week Learning Objectives:** By the end of this session, participants will:
1. Create planning prompts that decompose complex tasks into steps
2. Implement state management using the Four Tiers of context
3. Build checkpoint/resume capability for long-running tasks
4. Apply progressive disclosure for efficient context management

**Entry Criteria:** (What participants should have before this session)
- [ ] Multiple MCP servers configured (Week 3)
- [ ] Tool chaining implemented
- [ ] 10+ agent executions logged
- [ ] Error handling robust (Week 2)

**Exit Criteria:** (What participants should be able to do after this session)
- [ ] Explain the Plan-Execute pattern
- [ ] Describe the Four Tiers of context
- [ ] Implement state tracking for multi-step execution
- [ ] Create checkpoints and resume from them

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Complex Task Decomposition (10 min) - Slides 4-8
3. Segment 2: State Management Across Steps (14 min) - Slides 9-15
4. Segment 3: Checkpoint and Resume (12 min) - Slides 16-21
5. Segment 4: Long-Running Patterns + Close (6 min) - Slides 22-25

**Total Slides:** 25

---

## SLIDE 1: TITLE SLIDE

**Title:** Block 3 Week 4: Multi-Step Agents

**Subtitle:** Complex Tasks, State Management, and Recovery

**Content:**
- AI Practitioner Training Program
- Block 3: AI Automation Architecture

**Graphic:** Clean title slide with green theme (Block 3 color). Visual of stepped process with checkpoint markers.

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Week 4: Multi-Step Agents. We're at the halfway point of Block 3, and today we tackle one of the most challenging problems in agent development - handling complex tasks that span multiple steps and potentially multiple sessions.

Last week you configured multiple tools and learned chaining patterns. Today we're adding the intelligence layer - planning, state management, and recovery.

Quick check: Who has tool chains working from Week 3? What was the most steps you chained together?

[Wait for 1-2 responses]

Good. We're going to take those chains and make them robust enough for production use."

[Transition: Click to next slide]

---

## SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Week 3 Recap |
| 3-13 min | Segment 1 | Complex Task Decomposition |
| 13-27 min | Segment 2 | State Management |
| 27-39 min | Segment 3 | Checkpoint and Resume |
| 39-45 min | Segment 4 | Long-Running Patterns + Close |

**Graphic:** Timeline showing session flow with green accent colors

**SPEAKER NOTES:**

"Here's our roadmap:

First, complex task decomposition - how to break big tasks into manageable steps with explicit planning.

Then, state management - the Four Tiers of context and how to track progress across steps. This is the core concept today.

Checkpoint and resume - critical for reliability. What happens when things fail midway?

We close with long-running task patterns and homework preview.

Let's dive in."

[Transition]

---

## SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Create planning prompts for complex tasks**
   - Decompose tasks into structured steps

2. **Implement state management with Four Tiers**
   - Not everything belongs in active context

3. **Build checkpoint/resume capability**
   - Recovery without restart

4. **Apply progressive disclosure**
   - Load context on-demand, not upfront

**Graphic:** Checklist visual with green checkboxes

**SPEAKER NOTES:**

"Four objectives for today.

[Read each]

By the end, your agent will be able to handle tasks too complex for single-prompt execution, track its progress, and recover from failures.

Your homework this week includes building the planning system, state management, and testing checkpoint/resume.

Let's start with task decomposition."

[Transition: Click to Segment 1]

---

## SEGMENT 1: COMPLEX TASK DECOMPOSITION
### Duration: 10 minutes | Slides 4-8

---

## SLIDE 4: THE CHALLENGE

**Title:** Why Single-Prompt Fails

**Content:**

**The Problem:**
Give an agent a complex task, and it often:
- Gets lost partway through
- Produces poor quality results
- Fails without clear reason
- Takes wrong paths

**Root Cause:**
No explicit plan. Agent makes it up as it goes.

**The Solution:**
Separate PLANNING from EXECUTION.

**Graphic:** Agent getting lost in a maze vs. following a map

**SPEAKER NOTES:**

"[Hook - The problem]"

"Here's what happens when you give a complex task to an unprepared agent.

[Walk through problems]

Gets lost - loses track of the goal halfway through. Produces poor results - because it took shortcuts. Fails mysteriously - no clear reason why. Takes wrong paths - because it didn't consider alternatives.

[Root cause]

The root cause is no explicit plan. The agent makes it up as it goes. Works for simple tasks, fails for complex ones.

[Solution]

The solution is separating planning from execution. Create the roadmap first, then follow it."

[Transition]

---

## SLIDE 5: THE TWO-PHASE APPROACH

**Title:** Plan First, Execute Second

**Content:**

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

**Why This Works:**
- Planning uses full context to create roadmap
- Execution follows roadmap with focused context
- Validation catches problems early
- Adjustments happen consciously, not randomly

**Graphic:** Two-phase flow diagram

**GRAPHICS:**

**Graphic 1: Two-Phase Agent Approach**
- Purpose: Illustrate separation of planning from execution for complex multi-step tasks
- Type: Two-phase sequential diagram
- Elements: Phase 1 and Phase 2 boxes with distinct activities; connecting arrow
- Labels:
  - Phase 1 box: "PLAN" (blue)
    - "Analyze full task"
    - "Break into discrete steps"
    - "Identify dependencies"
    - "Estimate effort/risk"
    - Output: "Execution Plan (JSON)"
  - Arrow: "Plan becomes roadmap →"
  - Phase 2 box: "EXECUTE" (green)
    - "Execute steps in order"
    - "Validate each step"
    - "Adjust plan if needed"
    - "Report progress"
    - Output: "Completed Task + State"
  - Key insight: "Planning uses full context | Execution uses focused context"
- Relationships: Sequential phases; plan informs execution; validation creates feedback loop

**SPEAKER NOTES:**

"The two-phase approach.

[Walk through Phase 1]

Planning happens first, with full task context. Analyze the whole thing. Break into discrete steps. Identify what depends on what. Estimate complexity and risk.

[Walk through Phase 2]

Execution follows the plan. Execute steps in order. Validate each step completed successfully. Adjust the plan if needed - consciously, not randomly. Report progress so you know where you are.

[Why it works]

Planning uses the big picture to create a good roadmap. Execution focuses on one step at a time. Problems are caught by validation, not discovered randomly."

[Transition]

---

## SLIDE 6: PLANNING PROMPT PATTERN

**Title:** How to Generate Plans

**Content:**

**Planning Prompt Structure:**

1. **Task Analysis**
   - Core objective? Key deliverables? Constraints?

2. **Step Breakdown**
   - Step name, description, inputs, outputs, tools
   - Dependencies, complexity, failure points

3. **Execution Order**
   - Sequence, parallel opportunities, critical path

4. **Validation Checkpoints**
   - Where to validate, what to check, go/no-go criteria

**Graphic:** Planning prompt structure diagram

**GRAPHICS:**

**Graphic 1: Planning Prompt Structure**
- Purpose: Show the four essential sections of an effective planning prompt
- Type: Structured template diagram
- Elements: Four stacked sections representing planning components
- Labels:
  - Section 1: "TASK ANALYSIS"
    - "Core objective? Key deliverables? Constraints?"
  - Section 2: "STEP BREAKDOWN"
    - "Step name, description, inputs, outputs, tools"
    - "Dependencies, complexity, failure points"
  - Section 3: "EXECUTION ORDER"
    - "Sequence, parallel opportunities, critical path"
  - Section 4: "VALIDATION CHECKPOINTS"
    - "Where to validate, what to check, go/no-go criteria"
  - Output arrow: "Complete Execution Plan"
- Relationships: Progressive detail from high-level to specific; each section builds on previous

**SPEAKER NOTES:**

"Here's how to structure a planning prompt.

[Walk through sections]

Task Analysis - understand the big picture. What's the objective? What must we deliver? What constraints exist?

Step Breakdown - this is the detailed work. Each step needs name, description, inputs, outputs, tools needed. Plus dependencies, complexity estimate, and what could go wrong.

Execution Order - sequence the steps. Are any independent and can run in parallel? What's the critical path - the longest chain?

Validation Checkpoints - where do we pause and check? What makes a step successful? What's the go/no-go criteria?

Exercise 4.1 has you create this for your capstone task."

[Transition]

---

## SLIDE 7: WHEN TO USE PLANNING

**Title:** Planning vs. Just Doing

**Content:**

**Use Planning When:**
- Task has 5+ steps
- Multiple decision points
- Getting lost is costly
- Dependencies between steps
- Long execution time

**Skip Planning When:**
- Simple, single-step tasks
- Well-defined workflows (already have the plan)
- Tasks that complete in 1-2 iterations

**Rule of Thumb:**
> "If you'd write a checklist before doing it yourself, the agent needs a plan too."

**Graphic:** Decision guide for planning vs. direct execution

**SPEAKER NOTES:**

"Don't over-engineer simple tasks.

[When to use]

Planning is for complex work. 5+ steps. Multiple decision points where you could go different ways. Tasks where getting lost is expensive. Dependencies between steps. Long execution times.

[When to skip]

Simple tasks don't need planning overhead. Single-step responses. Tasks you've already workflow-engineered. Quick completions.

[Rule of thumb]

If YOU would write a checklist before doing the task, the agent needs a plan too. If you'd just do it, the agent can too."

[Transition]

---

## SLIDE 8: PLAN OUTPUT FORMAT

**Title:** What Plans Look Like

**Content:**

```json
{
  "task_summary": "Research and summarize competitor landscape",
  "total_steps": 5,
  "estimated_complexity": "medium",
  "steps": [
    {
      "step_number": 1,
      "name": "Identify competitors",
      "inputs": ["Industry", "Region"],
      "outputs": ["Competitor list"],
      "tools": ["web_search"],
      "dependencies": [],
      "complexity": "simple"
    },
    {
      "step_number": 2,
      "name": "Gather company info",
      "dependencies": [1]
    }
  ],
  "checkpoints": [
    { "after_step": 2, "check": "All competitors have basic info" }
  ]
}
```

**Graphic:** JSON structure with annotations

**SPEAKER NOTES:**

"Here's what a plan looks like.

[Walk through structure]

Task summary at the top. Total steps and complexity estimate.

Each step has: number, name, inputs needed, outputs produced, tools required, dependencies on other steps, complexity.

Checkpoints define where to pause and validate.

[Key point]

This structured format lets the agent track progress systematically. It's not prose - it's executable structure."

[Transition: Click to Segment 2]

**BACKGROUND:**

**Rationale:**
- The Plan-Execute separation is the natural evolution of Week 1's Setup-Worker pattern applied to task decomposition
- Explicit planning creates artifact that serves as both execution roadmap and debugging reference
- Positions planning as architectural decision, not implementation detail - foundational for Week 5's orchestration where master agents plan and workers execute
- Counter-intuitive insight: Adding a planning step reduces total execution time by preventing thrashing

**Key Research & Citations:**
- **Anthropic Agent Best Practices (2025)**: Recommends agentic scaffolding with explicit decomposition step before task execution to improve reliability and reduce token waste from failed attempts
- **ReAct Pattern Research (Yao et al., 2023)**: Demonstrated that agents performing reasoning (planning) before action outperform direct action approaches by 20-30% on complex tasks
- **Software Engineering Planning Phase**: Waterfall, Agile, and modern methodologies all separate planning from implementation - same principle applies to autonomous agents

**Q&A Preparation:**
- *"Doesn't planning add overhead?"*: Upfront yes, but it prevents expensive failures. Planning phase uses fewer tokens than repeatedly attempting poorly-scoped tasks.
- *"What if the plan becomes outdated?"*: Plans should be living documents - agents update plans when conditions change. That's conscious adaptation vs. random thrashing.
- *"Can't the agent plan on-the-fly?"*: It can, but implicitly. Explicit plans enable validation, sharing across sessions, and human review before execution.

**Sources:**
1. [Anthropic: Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) - Agentic scaffolding recommendations
2. [ReAct: Synergizing Reasoning and Acting](https://arxiv.org/abs/2210.03629) - Planning before action research
3. [Chain-of-Thought Prompting](https://arxiv.org/abs/2201.11903) - Reasoning process improvement

---

## SEGMENT 2: STATE MANAGEMENT
### Duration: 14 minutes | Slides 9-15

---

## SLIDE 9: THE CONTEXT PROBLEM

**Title:** More Context Isn't Better

**Content:**

**Common Assumption:**
"Give the agent all the information - it'll figure out what's relevant."

**Reality:**
Research shows more context often makes performance WORSE.
- Attention gets diluted
- Relevant info gets buried
- Token costs increase
- Response quality drops

**The Solution:**
The Four Tiers of Context

**Graphic:** Graph showing performance degrading as context size increases

**SPEAKER NOTES:**

"[Hook - Challenge the assumption]"

"There's a common assumption: give the agent everything, it'll figure out what matters.

[Reality check]

Research shows this is wrong. More context often makes performance WORSE.

Why? Attention gets diluted across more tokens. The relevant information gets buried in noise. Token costs go up. Response quality drops.

[Solution]

The solution is the Four Tiers of Context - a framework for deciding what goes where."

[Transition]

---

## SLIDE 10: THE FOUR TIERS

**Title:** Context Architecture

**Content:**

| Tier | What | Example | Loading |
|------|------|---------|---------|
| **Tier 1: Working** | Active now | Current prompt, immediate task | Always loaded |
| **Tier 2: Session** | This conversation | Event stream, recent results | Filtered |
| **Tier 3: Persistent** | Across sessions | Progress records, learnings | On-demand |
| **Tier 4: Artifacts** | Large data | Files, databases | Referenced |

**Key Principle:**
> "Find the SMALLEST set of HIGH-SIGNAL tokens."

**Graphic:** Pyramid showing tiers with examples

**GRAPHICS:**

**Graphic 1: Four-Tier Context Strategy Pyramid**
- Purpose: Visualize the hierarchy of context management from compact to expansive
- Type: Pyramid diagram with four tiers
- Elements: Pyramid with four horizontal sections; each tier larger than the one above
- Labels (bottom to top):
  - Tier 4 (base, largest): "LONG-TERM MEMORY"
    - "External files, databases"
    - "Rarely accessed, comprehensive history"
    - Example: "All past meeting notes"
  - Tier 3: "SESSION CONTEXT"
    - "Current conversation thread"
    - Example: "Today's discussion thread"
  - Tier 2: "WORKING MEMORY"
    - "Current task, active variables"
    - Example: "Step 3 of 7, last result: Success"
  - Tier 1 (top, smallest): "IMMEDIATE FOCUS"
    - "What agent is doing RIGHT NOW"
    - Example: "Reading file: config.json"
  - Principle: "Keep each tier minimal - only what's needed"
- Relationships: Increasing scope bottom to top; each tier serves different purpose; most-used at top (immediate focus)

**SPEAKER NOTES:**

"The Four Tiers of Context.

[Walk through tiers]

Tier 1 - Working Context. What's active right now. Current step instructions. Always loaded.

Tier 2 - Session State. This conversation. Results from previous steps. Filtered as needed - not everything.

Tier 3 - Persistent Memory. Across sessions. Progress records, lessons learned. Retrieved on-demand.

Tier 4 - Artifacts. Large data - files, databases. Referenced by path, not pasted in.

[Key principle]

Find the SMALLEST set of HIGH-SIGNAL tokens. Not everything that might be relevant. What's actually needed NOW."

[Transition]

---

## SLIDE 11: TIERS IN PRACTICE

**Title:** For Multi-Step Agents

**Content:**

**Tier 1 - Working Context:**
- Current step instructions only
- Immediate inputs for this step

**Tier 2 - Session State:**
- Running summary of progress
- Key decisions made
- Not full step outputs

**Tier 3 - Persistent Memory:**
- Checkpoint files
- Full state object
- Historical learnings

**Tier 4 - Artifacts:**
- Source documents (by path)
- Generated outputs (by path)
- Large data sets

**Graphic:** Four boxes with multi-step agent examples

**SPEAKER NOTES:**

"How does this apply to multi-step agents?

[Walk through each tier]

Tier 1 - only current step instructions. Not the whole plan, just this step.

Tier 2 - running summary. 'Completed steps 1-3, gathered data, ready to analyze.' Not the full data.

Tier 3 - checkpoint files with full state. Available but not loaded by default.

Tier 4 - large documents by reference. 'See /output/research.md' not the full content.

[Key point]

Each step loads only what it needs. Context stays focused."

[Transition]

---

## SLIDE 12: STATE OBJECT

**Title:** Tracking Progress

**Content:**

```json
{
  "task_id": "task-abc-123",
  "current_step": 3,
  "status": "executing",
  "completed_steps": [1, 2],
  "step_results": {
    "step_1": { "status": "success", "output": "..." },
    "step_2": { "status": "success", "output": "..." }
  },
  "context": {
    "key_decisions": [
      "Step 1: Chose approach A over B because...",
      "Step 2: Filtered to top 5 candidates"
    ]
  }
}
```

**The state object IS the agent's memory.**

**Graphic:** State object with highlighted sections

**SPEAKER NOTES:**

"The state object tracks everything.

[Walk through fields]

task_id - unique identifier. current_step - where we are now. status - planning, executing, paused, completed, failed.

completed_steps - what's done. step_results - output from each step.

context.key_decisions - the running summary. Brief notes on what happened and why.

[Key insight]

This state object IS the agent's memory. It doesn't remember between sessions - the state object does."

[Transition]

---

## SLIDE 13: STATE OPERATIONS

**Title:** Working with State

**Content:**

**Initialize** (at task start):
- Generate task_id
- Set status to "planning"
- Save initial state

**Update** (after each step):
- Record step result
- Update current_step
- Add to key_decisions
- Update timestamp

**Load** (at each step start):
- Read current state
- Extract only what's needed
- Check dependencies met

**Save** (checkpoint):
- Write full state to file
- Include everything for resume

**Graphic:** State operation flow diagram

**SPEAKER NOTES:**

"Four operations on state.

[Walk through each]

Initialize at task start. Generate unique ID, set status to planning, save the initial state.

Update after each step. Record what happened, advance current_step, add to key_decisions summary.

Load at each step start. Read current state, but extract only what's needed for THIS step. Check that dependencies are met.

Save as checkpoint. Write the full state to file. Everything needed to resume later.

Exercise 4.2 has you implement these operations."

[Transition]

---

## SLIDE 14: THE ATTENTION BUDGET

**Title:** Curate Ruthlessly

**Content:**

**The Problem:**
Context window is finite. Every token counts.

**The Strategy:**
- Tier 1: Include fully
- Tier 2: Summarize before including
- Tier 3: Retrieve only when needed
- Tier 4: Reference, don't include

**Example:**
Instead of:
> "Here are all 47 competitor profiles..."

Use:
> "Completed competitor research. Key finding: 3 major players, differentiated by [X]. Full data at /research/competitors.json"

**Graphic:** Before/after comparison of context

**SPEAKER NOTES:**

"Your context window has a budget. Spend it wisely.

[Strategy]

Tier 1 goes in fully - it's essential. Tier 2 gets summarized first - capture the key points. Tier 3 is retrieved only when needed - not pre-loaded. Tier 4 is referenced by path - never included.

[Example]

Bad: Paste all 47 competitor profiles into context. Good: Summary plus path to full data.

[Key insight]

Summaries carry the SIGNAL with fewer tokens. Full data is available if needed, but not cluttering context by default."

[Transition]

---

## SLIDE 15: RUNNING SUMMARY

**Title:** Summary as Memory

**Content:**

**After Each Step, Add:**
```
"Step [N]: [Brief description of action and result]"
```

**Example:**
```
key_decisions: [
  "Step 1: Searched for competitors, found 12 initial candidates",
  "Step 2: Filtered to 5 based on market share > 5%",
  "Step 3: Gathered detailed profiles, 3 have relevant tech stack"
]
```

**Why This Works:**
- Compact representation of progress
- Key information preserved
- Context stays manageable
- Human-readable for debugging

**Graphic:** Summary growing step by step

**SPEAKER NOTES:**

"The running summary is how you preserve context without bloating it.

[Pattern]

After each step, add one line: what you did, what resulted. Brief but informative.

[Example]

Three steps, three summary lines. Anyone reading this knows what happened without needing full details.

[Why it works]

Compact. Key info preserved. Context stays small. And it's human-readable - great for debugging.

Include this summary in context for the next step. Full results stay in state object."

[Transition: Click to Segment 3]

---

## SEGMENT 3: CHECKPOINT AND RESUME
### Duration: 12 minutes | Slides 16-21

---

## SLIDE 16: WHY CHECKPOINTS MATTER

**Title:** Recovery Without Restart

**Content:**

**The Problem:**
Long tasks may fail midway:
- Network issues
- Timeouts
- Unexpected errors
- Resource limits

**Without Checkpoints:**
Restart from the beginning. Waste time, money, and effort.

**With Checkpoints:**
Resume where you left off. Minimal lost progress.

**Graphic:** Comparison of restart vs. resume timelines

**SPEAKER NOTES:**

"[Hook - The failure scenario]"

"Long tasks fail. Network glitches. Timeouts. Unexpected errors. Rate limits.

[Without checkpoints]

Without checkpoints, you restart from the beginning. All that work - wasted. Time, tokens, effort - all lost.

[With checkpoints]

With checkpoints, you resume where you left off. Step 1-4 completed? Resume at step 5. Minimal loss.

For production agents, checkpoints aren't optional."

[Transition]

---

## SLIDE 17: CHECKPOINT IMPLEMENTATION

**Title:** The Pattern

**Content:**

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

**Key Principles:**
- Save AFTER successful completion
- Check BEFORE executing
- Validate at each step

**Graphic:** Checkpoint flow diagram

**GRAPHICS:**

**Graphic 1: Checkpoint Save/Resume Flow**
- Purpose: Show how checkpoints enable task recovery after interruptions
- Type: Flow diagram with save and resume paths
- Elements: Execution flow with checkpoint save points and resume entry
- Labels:
  - Main flow: "Step 1" → "Step 2" → "Step 3" → "Step 4" → "Step 5" → "Complete"
  - After each step: "Save checkpoint" (downward arrow to storage)
  - Storage: "Checkpoint Files" (persistent state)
  - Interruption point: "⚠ FAILURE at Step 3"
  - Resume flow: "Read checkpoint 2" → "Resume at Step 3" → Continue
  - Comparison:
    - Without checkpoints: "FAILURE → Restart from Step 1" (red path)
    - With checkpoints: "FAILURE → Resume from Step 3" (green path)
  - Time saved: "60% of work preserved"
- Relationships: Checkpoints create recovery points; failures don't require full restart; resume from last successful state

**SPEAKER NOTES:**

"The implementation pattern is straightforward.

[Walk through loop]

For each step: First, check if checkpoint exists. If this step is already marked complete, skip to the next one. If not complete, execute the step, then save a checkpoint. Validate before moving on.

[Key principles]

Save after success - don't checkpoint incomplete work. Check before executing - respect previous progress. Validate at each step - catch problems early.

This pattern makes your agent resumable."

[Transition]

---

## SLIDE 18: CHECKPOINT FILE STRUCTURE

**Title:** What to Save

**Content:**

```json
{
  "checkpoint_id": "chk-task123-step3-20241230T103000",
  "created_at": "2024-12-30T10:30:00Z",
  "task_id": "task-123",
  "resumable": true,
  "state": {
    "current_step": 3,
    "completed_steps": [1, 2],
    "step_results": {...}
  },
  "next_step": {
    "step_number": 4,
    "name": "Process results",
    "dependencies_met": true
  },
  "context_summary": "Completed data gathering (steps 1-3). Ready to process."
}
```

**Graphic:** Checkpoint structure with annotations

**SPEAKER NOTES:**

"What goes in a checkpoint?

[Walk through fields]

checkpoint_id - unique, includes task, step, timestamp. created_at - when saved. task_id - which task. resumable - boolean flag.

state - the full state object. Everything needed to continue.

next_step - what to do when resuming. Step number, name, whether dependencies are met.

context_summary - human-readable progress. 'Completed X, ready for Y.'

[Key point]

A good checkpoint lets ANY agent continue the work. Not just this one, not just right now. Any agent, any time."

[Transition]

---

## SLIDE 19: RESUME PROCESS

**Title:** How to Resume

**Content:**

**Resume Steps:**

1. **Find Checkpoint**
   - List checkpoints for task_id
   - Select most recent

2. **Validate**
   - Check file integrity
   - Verify resumable = true

3. **Load State**
   - Parse state object
   - Restore to memory

4. **Confirm**
   - Display context_summary
   - User confirms resume

5. **Continue**
   - Start from next_step
   - Normal execution continues

**Graphic:** Five-step resume flow

**SPEAKER NOTES:**

"Resuming from checkpoint has five steps.

[Walk through]

Find - look for checkpoints for this task, pick the latest.

Validate - is the file intact? Is resumable true?

Load - parse the state object, restore it.

Confirm - show the human the context summary. Make sure we're resuming the right thing.

Continue - start execution from next_step. Normal flow from there.

[Key point]

The confirm step is important. Don't blindly resume - verify you're continuing the right task from the right point."

[Transition]

---

## SLIDE 20: CHECKPOINT MANAGEMENT

**Title:** Practical Considerations

**Content:**

**When to Checkpoint:**
- After each successful step
- Before risky operations
- On error (before failing)
- Periodically for long steps

**Storage:**
- Location: `/agents/[name]/checkpoints/`
- Naming: `chk-[task_id]-[step]-[timestamp].json`
- Retention: Keep last 5 per task

**Cleanup:**
- Delete old checkpoints after task success
- Keep all on failure (for debugging)

**Graphic:** Checkpoint lifecycle diagram

**SPEAKER NOTES:**

"Practical checkpoint management.

[When to save]

After each successful step - the main trigger. Before risky operations - save your progress. On error - capture state before failing. Periodically for long steps - don't lose hours of work.

[Storage]

Clear naming convention - task, step, timestamp. Retention policy - keep last 5, don't let them pile up.

[Cleanup]

After success, clean up old checkpoints. After failure, keep them all - you'll need them for debugging."

[Transition]

---

## SLIDE 21: TEST BEFORE YOU NEED IT

**Title:** Testing Checkpoints

**Content:**

**Test Scenarios:**

1. **Create and Verify**
   - Run partway, check checkpoint exists
   - Verify contents are complete

2. **Resume from Checkpoint**
   - Stop mid-execution
   - Resume and verify continuation

3. **Complete After Resume**
   - Resume and finish
   - Verify final state is correct

**Key Point:**
> "Test resume BEFORE you need it in production."

**Graphic:** Three test scenarios checklist

**SPEAKER NOTES:**

"Don't wait until production to test checkpoints.

[Test scenarios]

First - create and verify. Run partway, check the checkpoint file exists and has complete data.

Second - resume test. Stop mid-execution, then resume. Does it continue from the right place?

Third - complete after resume. Resume and finish the task. Is the final state correct?

[Key point]

Test resume BEFORE you need it. In production, you'll be stressed when things fail. You want confidence the checkpoint system works."

[Transition: Click to Segment 4]

---

## SEGMENT 4: LONG-RUNNING PATTERNS + CLOSING
### Duration: 6 minutes | Slides 22-25

---

## SLIDE 22: LONG-RUNNING TASKS

**Title:** Extended Execution Patterns

**Content:**

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

**Graphic:** Long-running task timeline with checkpoints

**SPEAKER NOTES:**

"For tasks that span hours or days.

[Extended patterns]

Break into chunks - session-sized pieces. Clear handoffs - each session knows where to pick up. Human check-ins - don't let it run unsupervised forever.

[Progress reporting]

Keep stakeholders informed. Step X of Y, status, percentage if applicable.

[Timeout management]

Set time limits per step. If it times out, save checkpoint and stop gracefully. Resume in the next session."

[Transition]

---

## SLIDE 23: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| 4.1: Task Planning System | 30 min | Planning prompt + plan | Decomposition |
| 4.2: State Management | 25 min | State design + impl | Tracking |
| 4.3: Checkpoint System | 20 min | Checkpoint + test | Recovery |
| **Total** | **75 min** | | |

**Target:** Multi-step agent with state tracking and checkpoint/resume

**Graphic:** Exercise progression diagram

**SPEAKER NOTES:**

"Your homework for this week.

[Walk through exercises]

Exercise 4.1 - Task Planning System. 30 minutes. Create the planning prompt, generate a plan for your capstone task.

Exercise 4.2 - State Management. 25 minutes. Design your state schema, implement the operations, test tracking.

Exercise 4.3 - Checkpoint System. 20 minutes. Implement checkpointing, TEST resume capability.

[Target]

By end of week, your agent should handle multi-step tasks with full state tracking and recovery capability."

[Transition]

---

## SLIDE 24: RESOURCES

**Title:** Resources for This Week

**Content:**

**Templates & Files:**
- Planning prompt template - Participant Guide
- State schema template - Participant Guide
- Checkpoint format - Participant Guide

**Reference Materials:**
- [Anthropic Agent Documentation](https://docs.anthropic.com/en/docs/agents)
- [Saga Pattern for Long-Running Processes](https://martinfowler.com/articles/patterns-of-distributed-systems/saga.html)

**Support:**
- Questions: Support channel
- State management issues: Post schema + error for help

**Graphic:** Resource icons with links

**SPEAKER NOTES:**

"Resources for this week.

Templates are in your participant guide - planning prompt, state schema, checkpoint format.

[References]

Anthropic docs for agent patterns. Martin Fowler's saga pattern article for long-running process thinking.

If you're stuck on state management, post your schema and the error. We can help debug."

[Transition]

---

## SLIDE 25: NEXT WEEK PREVIEW

**Title:** Next Week: Agent Specialization and Orchestration

**Content:**

**Preview:**
Week 5 covers coordinating multiple specialized agents, supervisor patterns, and managing agent handoffs.

**What to Complete Before Then:**
- [ ] Exercise 4.1: Task Planning System
- [ ] Exercise 4.2: State Management Implementation
- [ ] Exercise 4.3: Checkpoint System with tested resume
- [ ] Run a complete multi-step task end-to-end

**Key Preparation:**
Your multi-step agent becomes one of several that work together.

**Graphic:** Preview showing orchestration diagram

**SPEAKER NOTES:**

"Next week is Agent Specialization and Orchestration.

We'll cover coordinating multiple specialized agents. Supervisor patterns for managing agent teams. Clean handoffs between agents.

[Requirements]

Your multi-step agent needs to work before Week 5. We'll be making it one of several agents that collaborate.

[Final close]

We're at the halfway point of Block 3. You now have agents that plan, track state, and recover from failures. That's production-ready foundation.

Questions before we wrap?

[Handle questions]

Great progress. See you next week!"

---

## APPENDICES

### Appendix A: Slide Type Definitions
**TITLE SLIDE** - Opens presentation | **CONCEPT INTRODUCTION** - Introduces framework | **FRAMEWORK / MODEL** - Structured approach | **PATTERN / BEST PRACTICE** - Proven approach | **ARCHITECTURE / DIAGRAM** - System structure

### Appendix B: Background Section Guidelines
**Rationale:** Explain slide's purpose | **Key Research & Citations:** **[Source (Year)]**: [Explanation] | **Q&A Preparation:** *"[Question]"*: [Response]

### Appendix C: Visual Design Guidelines
**Block 3 Color Scheme:** Primary Green #00CC99, Accent Teal #008B8B | **Theme:** Green for automation, Teal for orchestration

### Appendix D: Quality Checklist
- [ ] Key Thesis stated | [ ] Learning objectives actionable | [ ] Code syntactically correct | [ ] Examples Block 3-relevant

### Appendix E: Sources Section Guidelines

Include 3-7 sources per slide, formatted as:
```markdown
1. [Full title with hyperlink](URL) - [Brief description]
```

Source types:
- **Primary research**: Academic papers, official documentation
- **Industry reports**: Analyst reports, surveys, benchmarks
- **Practitioner content**: Blog posts, conference talks
- **Official documentation**: Product docs, API references

### Appendix F: Implementation Guidance Structure

**Getting Started (2-4 items):**
- Immediate actions (can do today)
- Low-barrier entry points
- Foundation-building steps

**Best Practices (3-5 items):**
- Proven approaches with specific criteria
- Patterns that scale
- Measurable success indicators

**Common Pitfalls (2-4 items):**
- Mistakes that seem logical but fail
- Anti-patterns to avoid
- Assumptions that mislead

**Tools & Technologies (2-4 categories):**
Format: **[Category]**: [Tool names] - [use case description]

### Appendix G: Visual/Graphic Description Guidelines

Describe graphics with enough detail for a designer:

1. **Type**: diagram, illustration, chart, photo, etc.
2. **Main elements**: What objects/shapes appear
3. **Arrangement**: Spatial relationships
4. **Labels/Text**: Any text in the graphic
5. **Communication goal**: What the visual conveys

### Appendix H: Visual Design Guidelines

**Block 3 Color Scheme:**
| Element | Color | Hex Code |
|---------|-------|----------|
| Primary | Green | #00CC99 |
| Accent | Teal | #008B8B |
| Background | White | #FFFFFF |
| Text | Dark Gray | #333333 |

**Block 3 Theme:**
- Green represents growth, automation, and intelligent systems
- Use green highlights for agent-related concepts
- Teal accents for orchestration and coordination
- Clean, modern aesthetic reflecting production engineering

**Graphic Suggestions:**
- Title slides: Agent/architecture visuals with green theme
- Architecture diagrams: Clear component separation
- Flow diagrams: Directional arrows showing data/control flow
- Comparison slides: Side-by-side or table formats

### Appendix I: Quality Checklist

**Content Quality:**
- [ ] Key Thesis clearly stated
- [ ] Learning objectives are actionable
- [ ] Each slide has clear purpose in narrative
- [ ] Transitions connect ideas smoothly
- [ ] Examples are Block 3-relevant (automation architecture)

**Background Sections:**
- [ ] Rationale explains slide's role in presentation
- [ ] Research citations support claims with specifics
- [ ] Q&A preparation addresses likely objections
- [ ] Sources are credible and linked

**Implementation Guidance:**
- [ ] Getting Started provides immediate actions
- [ ] Best Practices are specific and proven
- [ ] Common Pitfalls warn against real mistakes
- [ ] Tools recommended are current and relevant

**Technical Accuracy:**
- [ ] Code examples are syntactically correct
- [ ] Architectural patterns follow industry standards
- [ ] Metrics and calculations are accurate
- [ ] Links to external resources work

**Audience Engagement:**
- [ ] Speaker notes include engagement cues
- [ ] Questions prompt reflection
- [ ] Examples relate to consulting work
- [ ] Exercises connect to real capstone needs

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |
