# **INSTRUCTOR GUIDE: BLOCK 3 WEEK 5**
## **Agent Specialization & Orchestration**

**Block:** 3: AI Automation Architecture
**Week:** 5 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Agent specialization, sequential orchestration, and master-worker patterns |
| **Difficulty Level** | High |
| **Prep Time Required** | 60 minutes |
| **Demo Required** | Yes - Multi-agent orchestration demo |
| **Tech Setup Needed** | Multiple specialized agents ready, orchestration flow working |
| **Common Challenges** | Understanding when to specialize; orchestration complexity |

---

## Navigation

**Block Navigation:** [Week 4 Instructor Guide](../week-4/instructor-guide.md) | **Week 5** | [Week 6 Instructor Guide](../week-6/instructor-guide.md)

**Related Materials:**
- [Week 5 Presentation Slides](presentation.md)
- [Week 5 Participant Guide](participant-guide.md)
- [Block 3 Main Document](../block-3.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 5 materials | |
| Prepare multi-agent demo | Build working orchestration example | |
| Review participant progress | Check multi-step agent status | |
| Prepare specialization examples | Have bloated vs. specialized comparison | |
| Review Week 4 | Check state management and checkpoint implementations | |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test orchestration demo end-to-end | |
| Load presentation | Have slides ready and tested | |
| Test agent handoffs | Verify data passes correctly between agents | |
| Prepare pattern diagrams | Have Sequential and Master-Worker ready | |
| Check common issues | Prepare fixes for orchestration problems | |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, orchestration demo, agent configs | |
| Test share | Verify screen sharing works | |
| Load demo agents | Have all specialized agents ready | |
| Start recording | If session is recorded | |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Week 4 recap | Check multi-step status |
| 0:03 | 10 min | Segment 1 | The Specialization Principle | Core concept |
| 0:13 | 12 min | Segment 2 | Sequential Orchestration Pattern | First pattern |
| 0:25 | 12 min | Segment 3 | Master-Worker Pattern | Second pattern |
| 0:37 | 8 min | Segment 4 | Other Patterns + Planning | Brief overview + capstone |
| 0:45 | - | Closing | Homework preview | |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Skip parallel and team-based patterns (reference in guide)
- Shorten Master-Worker to key concepts only
- Move pattern selection to homework

**If Running Ahead:**
- More discussion on participant-specific specialization
- Extended Q&A on orchestration patterns
- Discuss capstone architecture in detail

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:13 | Compress bloated agent signs |
| End Segment 2 | 0:25 | Skip orchestrator pseudocode |
| Start Closing | 0:42 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants
2. Quick status check on multi-step agents with checkpoints
3. Preview today's shift to multiple agents
4. Set context for orchestration

**Opening Script:**
> "Welcome to Week 5: Agent Specialization & Orchestration. You've built sophisticated single agents with state management and checkpoints. Today we're going bigger - coordinating multiple specialized agents that work together. By the end, you'll understand how to break complex work into specialized roles and orchestrate them effectively."

**Engagement Opportunity:**
> "Quick check: How many of you found your Week 4 agent doing too many different things? That's what we're solving today."

---

### Segment 1: The Specialization Principle (10 minutes)

**Learning Objective:** Understand why and when to specialize agents

**Slides:** 3-7

#### Content Delivery

**Key Point 1: One Agent = One Thing Done Well**
- Main message: Focused prompts produce better results
- Framework: Single responsibility principle for agents
- Key insight: "The more an agent does, the worse it does each thing"

**Key Point 2: Signs of a Bloated Agent**
- Main message: Recognize when an agent needs splitting
- Symptoms: System prompt > 2000 words, agent confusion, too many tools, inconsistent quality
- Practice preview: Exercise 5.1 analyzes your current agent

**Key Point 3: Specialization Examples**
- Main message: Clear role boundaries make better agents
- Examples: Research Agent (gathers), Analysis Agent (analyzes), Writer Agent (produces), Reviewer Agent (evaluates)

#### Facilitation Notes

**Watch For:**
- Resistance to splitting ("but it works as one agent")
- Over-specialization anxiety ("how many agents is too many?")

**If Asked About Agent Count:**
> "Start with 2-3 agents that have clear roles. You can always combine if too many, but it's harder to split a bloated agent later."

**Transition to Segment 2:**
> "Once we have specialized agents, we need to coordinate them. Let's start with the simplest pattern: Sequential Orchestration."

---

### Segment 2: Sequential Orchestration Pattern (12 minutes)

**Learning Objective:** Implement sequential orchestration for pipeline workflows

**Slides:** 8-12

#### Content Delivery

**Key Point 1: Pattern Overview**
- Main message: Agent A → Agent B → Agent C → Final Output
- Visual: Pipeline diagram with clear stages
- When to use: Clear sequential dependency, distinct skills per stage

**Key Point 2: How It Works**
- Main message: Orchestrator calls agents in sequence, passing outputs forward
- Process walkthrough: Receive task → Call Agent A → Validate → Call Agent B → Validate → ...
- Key insight: "Quality gates between stages catch problems early"

**Key Point 3: Implementation**
- Main message: Simple orchestrator logic with validation between calls
- Code example: Show pseudocode for orchestrate() function
- Connection to homework: Exercise 5.2 implements this for your capstone

#### Facilitation Notes

**Common Confusion:**
"How is this different from a multi-step agent?"

**Clarification:**
> "A multi-step agent does everything itself. Sequential orchestration has DIFFERENT agents for different stages. Each agent is specialized and focused. The orchestrator coordinates, but doesn't do the work."

**Transition to Segment 3:**
> "Sequential is great for pipelines. But what if you can parallelize the work? Enter Master-Worker."

---

### Segment 3: Master-Worker Pattern (12 minutes)

**Learning Objective:** Implement master-worker orchestration for decomposable tasks

**Slides:** 13-18

#### Content Delivery

**Key Point 1: Pattern Overview**
- Main message: Master decomposes, Workers execute, Master aggregates
- Visual: Master with multiple workers fanning out and returning
- When to use: Task can be parallelized, workers are interchangeable

**Key Point 2: How It Works**
- Main message: Master plans subtasks, assigns to workers, collects and synthesizes
- Process walkthrough: Decompose → Assign → Execute (parallel) → Collect → Aggregate
- Key insight: "Workers are stateless and interchangeable - any can do any subtask"

**Key Point 3: Implementation**
- Main message: Master has planning and aggregation roles, workers share one definition
- Code example: Show master.plan() and master.aggregate() pseudocode
- Connection to capstone: "Choose this if your task decomposes into similar subtasks"

#### Facilitation Notes

**Energy Check:**
At this point, participants may be:
- Excited about parallelization (channel into realistic implementation)
- Confused about master vs. workers (emphasize role distinction)

**Transition to Segment 4:**
> "Those are the two patterns we recommend for your capstone. Let me briefly mention two others, then we'll discuss planning."

---

### Segment 4: Other Patterns + Planning (8 minutes)

**Learning Objective:** Know other patterns exist; plan capstone architecture

**Slides:** 19-23

#### Content Delivery

**Key Point 1: Parallel Pattern (Brief)**
- Main message: Multiple independent agents, results merged
- When to use: Multiple independent analyses needed
- Note: "Similar to Master-Worker but no planning phase - all predetermined"

**Key Point 2: Team-Based Pattern (Brief)**
- Main message: Agents with distinct roles that interact
- When to use: Complex collaboration, simulated expert panels
- Note: "Most complex - not recommended for capstone"

**Key Point 3: Choosing Your Pattern**
- Main message: Match pattern to task characteristics
- Framework: Sequential for dependencies, Master-Worker for parallelizable, keep it simple
- Capstone guidance: "Start with Sequential or Master-Worker - you can always expand"

---

### Closing (3 minutes)

**Slides:** 24-25

**Do Not Skip This Section**

#### Homework Preview

**Script:**
> "Your homework includes three main exercises plus an optional peer review.
>
> Exercise 5.1 is Agent Decomposition - 25 minutes. Analyze your current agent and identify how to split it into specialists.
>
> Exercise 5.2 is Orchestration Implementation - 30 minutes. Implement either Sequential or Master-Worker for your capstone.
>
> Exercise 5.3 is Integration Testing - 20 minutes. Verify the multi-agent system works end-to-end.
>
> By end of week, you should have a working multi-agent orchestration. Everything is in your participant guide."

#### Next Week Preview

> "Next week is Optimization & Monitoring - making your system production-ready. Your orchestration needs to be working before then."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: How many agents is too many?**
A: There's no hard rule, but 3-5 is typical for most tasks. If you're managing more than 7, consider whether some can be combined or if the task is too complex.

**Q: Can an agent call another agent directly?**
A: In these patterns, the orchestrator handles all inter-agent communication. Direct agent-to-agent calls add complexity and make debugging harder.

**Q: What if my agents need to share state?**
A: Use the state management from Week 4. The orchestrator maintains state; agents receive and return structured data.

### Technical Questions

**Q: How do I handle errors in multi-agent systems?**
A: Each agent has its own error handling. The orchestrator checks validation after each call and decides: retry, skip, or escalate.

**Q: Can I mix patterns?**
A: Yes, you can have a Sequential pipeline where one stage is a Master-Worker. But keep it simple for now.

### Scope Questions

**Q: Should I use Master-Worker even if I don't need parallelization?**
A: Only if your task naturally decomposes into subtasks. Sequential is simpler and often sufficient.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Orchestration demo fails | Check agent connections | Show pre-recorded version |
| Agent handoff fails | Debug validation | Show expected behavior |
| Data doesn't pass correctly | Check format transformation | Walk through conceptually |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Resistance to specialization | "My agent works fine as is" | Show quality comparison |
| Over-specialization | Planning 10+ agents | "Start with 2-3, expand as needed" |
| Pattern confusion | "Which pattern do I use?" | Walk through decision guide |
| Integration anxiety | "How do I connect them?" | Show orchestrator as coordinator |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save pattern questions | For FAQ |
| Note orchestration issues | For troubleshooting guide |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | |
| Answer orchestration questions | |
| Share pattern examples | |
| Check participant decomposition plans | |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions | |
| Check integration test results | |
| Verify orchestration implementations | |
| Identify participants needing support | |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 5.1 | Agent decomposition document | `/agents/[name]/` |
| 5.2 | Orchestration design + implementation | `/agents/[name]/` |
| 5.3 | Integration test results | `/agents/[name]/tests/` |

---

## Week-Specific Notes

### What Makes This Week Unique

- **Architecture shift** - From single agent to multi-agent system
- **Orchestration introduction** - New coordination concepts
- **Capstone architecture decision** - Pattern choice carries forward
- **Integration complexity** - More moving parts to test

### Dependencies

**Builds On:**
- Week 4: Multi-step agents become components
- Week 4: State management for orchestrator
- Week 3: MCP tools for each agent

**Sets Up:**
- Week 6: Optimization of multi-agent system
- Week 7: Documentation of architecture
- Week 8: Capstone submission

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "One agent, one job - specialization improves quality"
2. "Sequential for pipelines, Master-Worker for parallel decomposition"
3. "The orchestrator coordinates; agents execute"

### If You Only Have Time For One Thing

Sequential Orchestration: Agent A → Agent B → Agent C with validation between each. Simple, reliable, sufficient for most capstones.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Specialization | Assembly line vs. single craftsman | Explaining why to specialize |
| Sequential | Relay race - pass the baton | Explaining handoffs |
| Master-Worker | Manager with team members | Explaining decomposition |

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial guide created | Training Team |
