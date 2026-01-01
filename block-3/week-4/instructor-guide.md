# **INSTRUCTOR GUIDE: BLOCK 3 WEEK 4**
## **Multi-Step Agents**

**Block:** 3: AI Automation Architecture
**Week:** 4 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Complex task decomposition, state management, and checkpoint/resume |
| **Difficulty Level** | High |
| **Prep Time Required** | 60 minutes |
| **Demo Required** | Yes - Multi-step agent with checkpoint/resume |
| **Tech Setup Needed** | Multi-tool agent ready, state file examples, checkpoint demos |
| **Common Challenges** | State management complexity; understanding context tiers |

---

## Navigation

**Block Navigation:** [Week 3 Instructor Guide](../week-3/instructor-guide.md) | **Week 4** | [Week 5 Instructor Guide](../week-5/instructor-guide.md)

**Related Materials:**
- [Week 4 Presentation Slides](presentation.md)
- [Week 4 Participant Guide](participant-guide.md)
- [Block 3 Main Document](../block-3.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 4 materials | |
| Prepare state examples | Create sample state.json files | |
| Build checkpoint demo | Working checkpoint/resume example | |
| Check participant progress | Review who has multi-tool agents | |
| Review Week 3 | Check tool chain implementations | |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test demo agent with checkpoints | |
| Load presentation | Have slides ready and tested | |
| Test checkpoint demo | Run complete checkpoint/resume 3+ times | |
| Prepare state templates | Have JSON schemas ready to show | |
| Check common issues | Prepare fixes for typical state management problems | |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, demo agent, state files | |
| Test share | Verify screen sharing works | |
| Load demo state | Have mid-execution checkpoint ready | |
| Start recording | If session is recorded | |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Week 3 recap | Check multi-tool status |
| 0:03 | 10 min | Segment 1 | Complex Task Decomposition | Planning patterns |
| 0:13 | 14 min | Segment 2 | State Management Across Steps | Core concept |
| 0:27 | 12 min | Segment 3 | Checkpoint and Resume | Critical for reliability |
| 0:39 | 6 min | Segment 4 | Long-Running Task Patterns + Close | Homework preview |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Reference Four Tiers in guide rather than explaining all
- Show one checkpoint format instead of detailed walkthrough
- Skip progress reporting patterns (reference in guide)

**If Running Ahead:**
- More discussion on participant-specific state needs
- Extended Q&A on checkpoint strategies
- Discuss long-running task scheduling

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:13 | Compress planning prompt pattern |
| End Segment 2 | 0:27 | Reduce state schema walkthrough |
| Start Closing | 0:39 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants
2. Quick status check on multi-tool agents
3. Connect Week 3 tool chains to multi-step need
4. Preview today's session

**Opening Script:**
> "Welcome to Week 4: Multi-Step Agents. This is where we tackle the challenge of complex tasks that span multiple steps and potentially multiple sessions. Last week you configured multiple tools and learned chaining patterns. Today we're adding the intelligence layer - planning, state management, and recovery. By the end, your agent will be able to handle tasks that take many steps to complete."

**Engagement Opportunity:**
> "Quick check: Who has tool chains working from Week 3? What was the most steps you chained together?"

[Wait for 1-2 responses]

---

### Segment 1: Complex Task Decomposition (10 minutes)

**Learning Objective:** Understand planning/execution split for complex tasks

**Slides:** 3-7

#### Content Delivery

**Key Point 1: The Challenge**
- Main message: Single-prompt agents struggle with complex tasks
- Problem framing: "Give an agent a big task, it often gets lost or produces poor results"
- Solution preview: "Explicit planning and step-by-step execution"

**Key Point 2: Two-Phase Approach**
- Main message: PLAN first, then EXECUTE
- Framework: Planning creates the roadmap; execution follows it
- Key insight: "Separate the 'what to do' from the 'doing it'"

**Key Point 3: Planning Prompt Pattern**
- Main message: Structured prompt that produces execution plan
- Template walkthrough: Task analysis → Step breakdown → Execution order → Validation points
- Practice preview: "Exercise 4.1 has you create this for your agent"

#### Facilitation Notes

**Watch For:**
- Confusion about when to use planning (not for simple tasks)
- Over-engineering the planning phase

**If Asked About Simple Tasks:**
> "For simple tasks, planning is overhead. This pattern is for complex, multi-step work where the agent might get lost without structure."

**Transition to Segment 2:**
> "Planning creates the roadmap. But how does the agent track where it is on that roadmap? That's state management."

---

### Segment 2: State Management Across Steps (14 minutes)

**Learning Objective:** Implement state tracking for multi-step agents

**Slides:** 8-14

#### Content Delivery

**Key Point 1: Context Architecture - The Four Tiers**
- Main message: Not everything belongs in active context
- Framework: Working Context → Session State → Persistent Memory → Artifacts
- Key insight: "More context often makes performance WORSE"

**Key Point 2: The Attention Budget**
- Main message: Context is finite - curate ruthlessly
- Framework: Find smallest set of high-signal tokens
- Real-world application: "Include current step instructions, not entire task history"

**Key Point 3: State Management Strategies**
- Main message: Three approaches - explicit state object, running summary, checkpoint files
- State object walkthrough: Show JSON schema with task_id, current_step, results
- When to use each: Object for active state, summary for context, files for persistence

**Key Point 4: State Object Schema**
- Main message: Structured state enables reliable multi-step execution
- Schema walkthrough: execution, plan, progress, step_results, context, metadata
- Key insight: "The state object IS the agent's memory"

#### Facilitation Notes

**Common Confusion Point:**
"How much state do I keep in context?"

**Clarification Approach:**
> "Only what's needed for the current step. The state file stores everything - you load what's relevant. Think of it like a database: you don't load every record into memory."

**Transition to Segment 3:**
> "State management tracks progress. But what happens when execution fails mid-way? That's where checkpoints come in."

---

### Segment 3: Checkpoint and Resume (12 minutes)

**Learning Objective:** Implement checkpoint/resume for reliable long-running tasks

**Slides:** 15-20

#### Content Delivery

**Key Point 1: Why Checkpoints Matter**
- Main message: Long tasks may fail midway; restarting from beginning is expensive
- Problem scenarios: Network failure, timeout, unexpected error
- Solution: "Save state periodically so you can resume, not restart"

**Key Point 2: Checkpoint Implementation**
- Main message: Save state after each step, check for checkpoint on start
- Pattern walkthrough: FOR each step → Check if done → Execute → Save checkpoint
- Key insight: "Idempotent steps are your friend - safe to re-run if needed"

**Key Point 3: Checkpoint File Structure**
- Main message: Include everything needed to resume
- Schema walkthrough: checkpoint_id, task_id, state, next_step, resumable
- Key insight: "A good checkpoint lets any agent continue the work"

**Key Point 4: Resume Process**
- Main message: Find checkpoint → Validate → Load state → Continue
- Process walkthrough: Five steps from finding to resuming
- Testing importance: "Test resume BEFORE you need it in production"

#### Demo Instructions

**Demo Duration:** 4 minutes (within segment)

**Setup Required:**
- Multi-step agent with checkpoint capability
- Pre-saved checkpoint file mid-execution
- Way to trigger resume

**Demo Steps:**
1. Show checkpoint file structure (30 sec)
2. Show how checkpoint was created (1 min)
3. Demonstrate resume from checkpoint (2 min)
4. Show continuation to completion (30 sec)

**Backup Plan:**
If demo fails:
1. Show pre-captured screenshots
2. Walk through the process conceptually
3. Emphasize testing in homework

---

### Segment 4: Long-Running Task Patterns + Closing (6 minutes)

**Learning Objective:** Understand long-running task management and homework preview

**Slides:** 21-25

#### Content Delivery

**Key Point 1: Handling Extended Tasks**
- Main message: Break into session-sized chunks, clear handoffs, human check-in points
- Framework: Think in sessions, not continuous execution

**Key Point 2: Progress Reporting**
- Main message: Keep stakeholders informed during long tasks
- Pattern: "[Step 2/7] Action... Complete" format

**Key Point 3: Timeout Management**
- Main message: Set maximum time per step, save and resume on timeout

#### Homework Preview

**Script:**
> "Your homework includes three exercises totaling about 75 minutes.
>
> Exercise 4.1 is Task Planning System - 30 minutes. Create the planning prompt that breaks down complex tasks.
>
> Exercise 4.2 is State Management Implementation - 25 minutes. Build the state tracking system for your agent.
>
> Exercise 4.3 is Checkpoint System - 20 minutes. Implement and test checkpoint/resume.
>
> By end of week, your agent should handle multi-step tasks with state tracking and recovery. Everything is in your participant guide."

#### Next Week Preview

> "Next week is Agent Specialization and Orchestration - coordinating multiple specialized agents. Your multi-step foundation is essential for that."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: When should I use planning vs. just letting the agent figure it out?**
A: Use planning for tasks with 5+ steps, multiple decision points, or where getting lost is costly. Simple tasks don't need it.

**Q: How big should my checkpoint files be?**
A: Only store what's needed to resume. A few KB is typical. If you're storing MB, you're probably storing too much.

**Q: What's the difference between state object and checkpoint?**
A: State object is in-memory during execution. Checkpoint is the persisted snapshot of that state. Checkpoints are state objects saved to files.

### Technical Questions

**Q: How do I know if a step is safe to re-run?**
A: If running it twice produces the same result without side effects, it's idempotent. File reads are idempotent. Sending emails is not.

**Q: Where should I store checkpoint files?**
A: Local filesystem for development. For production, consider versioned storage (S3, etc.) with retention policies.

### Scope Questions

**Q: My capstone task doesn't seem to need checkpoints - is that okay?**
A: If your task completes in one session reliably, checkpoints may be overkill. But implementing them demonstrates the pattern and protects against future complexity.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Demo checkpoint won't load | Check JSON syntax | Show pre-captured screenshots |
| State file corruption | Show error handling | Explain validation importance |
| Resume starts wrong step | Debug state.current_step | "This is why testing matters" |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| State management confusion | "What goes where?" | Simplify to basic state object first |
| Over-complicating state | Massive JSON schemas | "Start minimal, add as needed" |
| Checkpoint anxiety | "What if I lose data?" | Emphasize multiple checkpoints, testing |
| No multi-tool agent | Can't implement exercises | Provide starter agent, catch-up support |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save common state questions | For FAQ |
| Note checkpoint issues | For troubleshooting guide |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | |
| Answer state management questions | |
| Share state schema templates | |
| Document common issues | |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions | |
| Check checkpoint implementations | |
| Verify resume functionality works | |
| Identify participants needing support | |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 4.1 | Planning prompt + generated plan | `/agents/[name]/prompts/` |
| 4.2 | State management design + implementation | `/agents/[name]/` |
| 4.3 | Checkpoint system + resume test | `/agents/[name]/checkpoints/` |

### Progress Check Approach

**How to Verify Completion:**
- Check for planning prompt in prompts folder
- Verify state schema exists and is complete
- Look for checkpoint files and resume test documentation

**Intervention Thresholds:**
- No state management: Immediate support needed
- Checkpoint not tested: May fail in production
- Planning prompt generic: May not help with their specific agent

---

## Week-Specific Notes

### What Makes This Week Unique

- **Halfway point of Block 3** - Critical capabilities complete after this week
- **Foundation for orchestration** - Week 5 builds directly on this
- **Production-readiness milestone** - Checkpoint/resume is essential for real use
- **Complexity peak** - State management is the hardest concept for many

### Dependencies

**Builds On:**
- Week 3: Multi-tool agent required
- Week 2: Error handling used in checkpoints
- Week 1: Design document informs planning

**Sets Up:**
- Week 5: Multi-agent orchestration needs reliable individual agents
- Week 6-7: Optimization and documentation assume working multi-step
- Week 8: Capstone requires all capabilities

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| JSON serialization edge cases | Provide validated schema | Active |
| Checkpoint file permissions | Document OS-specific fixes | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- "What's in Tier 1 context vs. Tier 3?" (current step vs. persistent memory)
- "When does checkpoint save happen?" (after each step completes)
- Observable behavior indicating understanding: Questions about their specific state needs
- Observable behavior indicating confusion: Generic questions, mixing up tiers

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 4.1: Planning prompt produces actionable plans, not vague outlines
- Exercise 4.2: State schema is complete and used in execution
- Exercise 4.3: Resume actually works (tested), not just implemented

**Common Issues to Flag:**
- Planning too detailed (won't generalize)
- State includes everything (context overload)
- Checkpoint not tested (will fail when needed)

### Connecting to Capstone

**Capstone Relevance:**
This week's work contributes to the capstone by:
- Planning system enables complex task handling
- State management required for production reliability
- Checkpoint/resume is capstone requirement

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Plan before execute - complex tasks need explicit planning"
2. "Not everything belongs in context - use the four tiers"
3. "Checkpoints enable recovery - test resume before you need it"

### If You Only Have Time For One Thing

State management: Explicit state object tracking task_id, current_step, and step_results. Load what you need for each step, save after each step.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Four Tiers | Library card catalog vs. reading every book | Explaining context tiers |
| Checkpoint | Video game save point | Explaining why/when to checkpoint |
| Planning phase | Architect drawing blueprints before building | Explaining plan/execute split |

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial guide created | Training Team |
