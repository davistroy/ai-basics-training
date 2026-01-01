# **BLOCK 3 WEEK 5: Agent Specialization & Orchestration**

**Block:** 3: AI Automation Architecture
**Week:** 5 of 8
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Block Navigation:** [Week 4 Participant Guide](../week-4/participant-guide.md) | **Week 5** | [Week 6 Participant Guide](../week-6/participant-guide.md)

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
| 1 | Apply the specialization principle to decompose agents into focused roles | Exercise 5.1 |
| 2 | Implement sequential orchestration for pipeline workflows | Exercise 5.2 |
| 3 | Implement master-worker orchestration for decomposable tasks | Exercise 5.2 |
| 4 | Verify multi-agent coordination through integration testing | Exercise 5.3 |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Multi-step agent working (Week 4)
- [ ] State management implemented
- [ ] Checkpoint system functional
- [ ] 15+ successful agent executions

**Not ready?** You must have a working multi-step agent before proceeding. Orchestration builds on reliable individual agents.

---

## Key Concepts

### Concept 1: The Specialization Principle

**Definition:**
The principle that each agent should focus on one specific responsibility, doing that one thing exceptionally well.

**Why It Matters:**
- Focused prompts produce better results
- Easier to test and debug
- Simpler error handling
- Reusable components
- Prevents "bloated agent syndrome"

**Core Principle:**
> "One agent = One thing done well"

**Signs of a Bloated Agent:**
- System prompt > 2000 words
- Agent gets confused about its role
- Too many tools to choose from
- Inconsistent output quality
- Hard to debug failures

**Specialization Examples:**

| Agent Type | Focus | Does NOT Do |
|------------|-------|-------------|
| Research Agent | Gather information | Analyze or write |
| Analysis Agent | Analyze data | Gather or produce content |
| Writer Agent | Produce content | Research or evaluate |
| Reviewer Agent | Evaluate quality | Create or modify |

---

### Concept 2: Sequential Orchestration Pattern

**Definition:**
An orchestration pattern where agents execute in sequence, with each agent's output becoming the next agent's input.

**Pattern Diagram:**
```
Agent A → Agent B → Agent C → Final Output
(Research)  (Analyze)  (Write)
```

**How It Works:**
1. Orchestrator receives task
2. Calls Agent A with initial input
3. Validates Agent A output
4. Passes to Agent B
5. Validates Agent B output
6. Passes to Agent C
7. Returns final output

**Implementation:**
```
ORCHESTRATOR:
  input = user_request

  # Stage 1: Research
  research_result = call_agent("research", input)
  validate(research_result)

  # Stage 2: Analyze
  analysis_result = call_agent("analyze", research_result)
  validate(analysis_result)

  # Stage 3: Write
  final_output = call_agent("write", analysis_result)
  validate(final_output)

  return final_output
```

**When to Use:**
- Clear sequential dependency (B needs A's output)
- Each stage has a distinct skill
- Quality gates between stages are valuable

---

### Concept 3: Master-Worker Pattern

**Definition:**
An orchestration pattern where a master agent decomposes tasks and coordinates workers who execute subtasks independently.

**Pattern Diagram:**
```
                  ┌→ Worker A ─┐
Master (Planner) ─┼→ Worker B ─┼→ Master (Aggregator) → Output
                  └→ Worker C ─┘
```

**How It Works:**
1. Master decomposes task into subtasks
2. Master assigns subtasks to workers
3. Workers execute independently (can be parallel)
4. Master collects results
5. Master aggregates into final output

**Implementation:**
```
MASTER:
  subtasks = decompose(user_request)
  results = []

  FOR each subtask:
    worker_result = call_worker(subtask)
    results.append(worker_result)

  final_output = aggregate(results)
  return final_output
```

**When to Use:**
- Task can be parallelized
- Workers are interchangeable
- Results need synthesis

---

### Concept 4: Other Orchestration Patterns

**Parallel Pattern:**
- Multiple agents work simultaneously
- No dependency between them
- Results merged at end
- Good for: Multiple independent analyses

**Team-Based Pattern:**
- Agents with distinct roles collaborate
- Can interact with each other
- Complex coordination
- Good for: Simulated expert panels

**Pattern Selection Guide:**

| Pattern | Use When | Complexity |
|---------|----------|------------|
| Sequential | Clear stages, dependencies | Low |
| Master-Worker | Decomposable, aggregatable | Medium |
| Parallel | Independent analyses | Medium |
| Team-Based | Complex collaboration | High |

**For Your Capstone:**
- Recommend: Sequential or Master-Worker
- Keep it simple - can expand later
- Master-Worker only if task naturally decomposes

---

### Quick Reference: Orchestration Components

| Component | Sequential | Master-Worker |
|-----------|------------|---------------|
| **Coordinator** | Orchestrator | Master Agent |
| **Workers** | Stage agents | Worker agents |
| **Data Flow** | Linear | Fan-out/Fan-in |
| **Parallelism** | No | Yes (optional) |
| **Aggregation** | Final agent | Master Agent |
| **Error Handling** | Per-stage | Per-worker + Master |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Agent specialization, sequential orchestration, and master-worker patterns for multi-agent systems.

**Key Points from Each Segment:**

**Segment 1: The Specialization Principle**
- One agent = One thing done well
- Bloated agents show confusion, inconsistent quality, hard debugging
- Specialization examples: Research, Analysis, Writer, Reviewer agents

**Segment 2: Sequential Orchestration Pattern**
- Agent A → Agent B → Agent C with validation between
- Orchestrator coordinates, agents execute
- Use when: Clear dependencies, distinct skills per stage

**Segment 3: Master-Worker Pattern**
- Master decomposes and aggregates, Workers execute subtasks
- Can parallelize worker execution
- Use when: Task can be split into similar subtasks

**Segment 4: Other Patterns + Planning**
- Parallel for independent analyses
- Team-Based for complex collaboration (not for capstone)
- Choose Sequential or Master-Worker for capstone

### Demo Recap

**What Was Demonstrated:**
Multi-agent orchestration with three specialized agents

**Key Steps:**
1. Showed bloated agent vs. specialized agents comparison
2. Demonstrated sequential orchestration flow
3. Showed validation between agent calls
4. Demonstrated data transformation at handoffs
5. Showed error handling when one agent fails

**Result:**
Three specialized agents coordinated by orchestrator, producing higher quality output than single bloated agent.

---

## Self-Paced Exercises

**Total Time:** 75 minutes (plus optional peer review)

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 5.1 | 25 min | Agent decomposition document | Identify specialists |
| 5.2 | 30 min | Orchestration design + implementation | Build coordination |
| 5.3 | 20 min | Integration test results | Verify system |
| 5.4 (Optional) | 30 min | Peer review feedback | Design review |

---

### Exercise 5.1: Agent Decomposition

**Duration:** 25 minutes

**Purpose:**
Analyze your current agent and identify how to split it into specialized agents with clear responsibilities.

**You Will Create:**
An agent decomposition document identifying specialist agents.

---

#### Instructions

**Step 1: Analyze Current Agent**

```markdown
# Agent Decomposition Analysis

## Current Agent: [Name]
**Current scope:** [What it does - probably too much]

**System prompt length:** [Word count]

**Tools used:** [List all tools]

**Quality issues observed:**
- [Issue 1]
- [Issue 2]
```

**Step 2: Identify Responsibilities**

List everything your agent currently does:

```markdown
## Identified Responsibilities

1. [Responsibility 1 - e.g., "Searches for relevant information"]
2. [Responsibility 2 - e.g., "Analyzes data for patterns"]
3. [Responsibility 3 - e.g., "Generates written content"]
4. [Responsibility 4 - e.g., "Evaluates quality of output"]
...
```

**Step 3: Design Specialist Agents**

For each responsibility, consider if it warrants its own agent:

```markdown
## Candidate Specialists

### Specialist 1: [Name] Agent
**Focus:** [Single responsibility]
**Inputs:** [What it receives]
**Outputs:** [What it produces]
**Tools needed:** [Subset of tools]
**Why separate:** [Benefit of specialization]

### Specialist 2: [Name] Agent
**Focus:** [Single responsibility]
**Inputs:** [What it receives]
**Outputs:** [What it produces]
**Tools needed:** [Subset of tools]
**Why separate:** [Benefit of specialization]

### Specialist 3: [Name] Agent
**Focus:** [Single responsibility]
**Inputs:** [What it receives]
**Outputs:** [What it produces]
**Tools needed:** [Subset of tools]
**Why separate:** [Benefit of specialization]
```

**Step 4: Map Dependencies**

```markdown
## Dependency Map

\`\`\`
[Specialist 1] → [Specialist 2] → [Specialist 3]
                       ↓
               [Depends on external data]
\`\`\`

## Recommended Architecture
- **Pattern:** [Sequential / Master-Worker]
- **Orchestration flow:** [Description]
- **Benefits over single agent:** [List]
```

---

#### Deliverable Specification

**File Name:** `agent-decomposition.md`

**Location:** `/agents/[agent-name]/`

**Quality Criteria:**
- [ ] Current agent analyzed with specific issues
- [ ] All responsibilities identified
- [ ] 2-4 specialist agents defined
- [ ] Dependencies mapped
- [ ] Pattern recommendation with rationale

---

### Exercise 5.2: Orchestration Implementation

**Duration:** 30 minutes

**Purpose:**
Implement your chosen orchestration pattern (Sequential or Master-Worker) to coordinate your specialized agents.

**You Will Create:**
Orchestration design and working implementation.

---

#### Instructions

**Choose Your Pattern:**

**For Sequential Pattern:**

```markdown
# Sequential Orchestration Design

## Pipeline Flow
\`\`\`
[Input] → [Agent 1] → [Agent 2] → [Agent 3] → [Output]
\`\`\`

## Agent Definitions

### Agent 1: [Name]
- **System prompt:** [Brief summary or link]
- **Input format:**
  \`\`\`json
  { "field": "description" }
  \`\`\`
- **Output format:**
  \`\`\`json
  { "field": "description" }
  \`\`\`
- **Validation:** [How to verify output]

### Agent 2: [Name]
[Repeat structure]

### Agent 3: [Name]
[Repeat structure]

## Orchestrator Logic

\`\`\`
def orchestrate(user_input):
    # Stage 1
    result_1 = agent_1.run(user_input)
    if not validate(result_1): handle_error()

    # Stage 2
    result_2 = agent_2.run(result_1)
    if not validate(result_2): handle_error()

    # Stage 3
    final = agent_3.run(result_2)
    if not validate(final): handle_error()

    return final
\`\`\`

## Data Transformations
- Between Agent 1→2: [Transform description]
- Between Agent 2→3: [Transform description]
```

**For Master-Worker Pattern:**

```markdown
# Master-Worker Orchestration Design

## Architecture
\`\`\`
                  ┌→ [Worker A] ─┐
[Master: Plan] ───┼→ [Worker B] ─┼→ [Master: Aggregate] → [Output]
                  └→ [Worker C] ─┘
\`\`\`

## Master Agent

### Planning Phase
- **Input:** User request
- **Output:** List of subtasks with assignments
- **Logic:** How to decompose task

### Aggregation Phase
- **Input:** Worker results
- **Output:** Synthesized final result
- **Logic:** How to combine results

## Worker Definition
(All workers share same structure, different inputs)

- **System prompt:** [Worker prompt]
- **Input format:** Subtask from master
- **Output format:** Subtask result
- **Validation:** [How master validates]

## Orchestrator Logic

\`\`\`
def orchestrate(user_input):
    # Planning
    subtasks = master.plan(user_input)

    # Execution
    results = []
    for task in subtasks:
        result = worker.run(task)
        results.append(result)

    # Aggregation
    final = master.aggregate(results)
    return final
\`\`\`
```

**Step 2: Implement in Your Platform**

Build the orchestration in Make/n8n or your chosen platform.

**Step 3: Test with Sample Task**

Run a complete orchestration end-to-end.

---

#### Deliverable Specification

**File Name:** `orchestration-design.md`

**Location:** `/agents/[agent-name]/`

**Quality Criteria:**
- [ ] Pattern choice documented with rationale
- [ ] All agents defined with input/output formats
- [ ] Orchestration logic clear
- [ ] Data transformations specified
- [ ] Working implementation tested

---

### Exercise 5.3: Integration Testing

**Duration:** 20 minutes

**Purpose:**
Verify that your multi-agent system works correctly end-to-end through systematic testing.

**You Will Create:**
Integration test suite with results.

---

#### Instructions

```markdown
# Multi-Agent Integration Tests

## Test 1: Happy Path - Complete Flow
- **Input:** [Standard valid input]
- **Expected flow:** Agent1 → Agent2 → Agent3
- **Expected output:** [What success looks like]
- **Actual result:** [Pass/Fail]
- **Notes:** [Observations]

## Test 2: Handoff Validation
- **Focus:** Data passes correctly between agents
- **Check:** Agent 2 receives correct input from Agent 1
- **Check:** Agent 3 receives correct input from Agent 2
- **Actual result:** [Pass/Fail]
- **Notes:** [Observations]

## Test 3: Single Agent Failure
- **Scenario:** Agent 2 fails (trigger intentionally)
- **Expected behavior:** [Retry/escalate]
- **Actual result:** [Pass/Fail]
- **Notes:** [Observations]

## Test 4: Quality Gate Rejection
- **Scenario:** Agent 1 output fails validation
- **Expected behavior:** [Retry/escalate]
- **Actual result:** [Pass/Fail]
- **Notes:** [Observations]

## Test 5: End-to-End Performance
- **Measure:** Total execution time
- **Measure:** Per-agent time
- **Baseline target:** [X minutes]
- **Actual result:** [Y minutes]

## Test Summary

| Test | Status | Notes |
|------|--------|-------|
| 1. Happy Path | Pass/Fail | |
| 2. Handoff | Pass/Fail | |
| 3. Failure | Pass/Fail | |
| 4. Quality Gate | Pass/Fail | |
| 5. Performance | Pass/Fail | |

## Issues Found
- [Issue 1]: [Description] - [Resolution]
- [Issue 2]: [Description] - [Resolution]
```

---

#### Deliverable Specification

**File Name:** `integration-tests.md`

**Location:** `/agents/[agent-name]/tests/`

**Quality Criteria:**
- [ ] All 5 test categories executed
- [ ] Results clearly documented
- [ ] Issues identified and resolved
- [ ] Performance within acceptable range

---

### Exercise 5.4: Agent Architecture Review (Optional)

**Duration:** 30 minutes

**Purpose:**
Get peer feedback on your agent architecture design.

**If You Have a Learning Partner:**

1. Exchange agent design documents
2. Review partner's design for:
   - Clear specialization (is scope bounded?)
   - Appropriate orchestration pattern
   - Complete error handling
   - Realistic success criteria

3. Provide structured feedback:

```markdown
## Agent Design Review

### Strengths
- [What's well-designed]

### Questions
- [Clarifications needed]

### Concerns
- [Potential issues]

### Suggestions
- [Improvements to consider]
```

4. Discuss feedback together
5. Revise designs based on input

**Deliverable:** Design review feedback + revised design

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| Agent Decomposition | Identify specialists | Exercise 5.1 |
| Sequential Design | Pipeline orchestration | Exercise 5.2 |
| Master-Worker Design | Decomposition orchestration | Exercise 5.2 |
| Integration Tests | System verification | Exercise 5.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Multi-Agent Systems | Documentation | [docs.anthropic.com](https://docs.anthropic.com/en/docs/agents) | Agent patterns |
| Orchestration Patterns | Reference | [microservices.io](https://microservices.io/patterns/data/saga.html) | Pattern details |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Apply specialization principle | Agent decomposition document | |
| 2 | Implement sequential orchestration | Working pipeline | |
| 3 | Implement master-worker pattern | Or understand when to use | |
| 4 | Verify multi-agent coordination | Integration tests pass | |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 5.1 output | `agent-decomposition.md` | `/agents/[name]/` | |
| Exercise 5.2 output | `orchestration-design.md` | `/agents/[name]/` | |
| Exercise 5.3 output | `integration-tests.md` | `/agents/[name]/tests/` | |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** Which orchestration pattern made most sense for your use case?

2. **What's still fuzzy?** What do you need more practice or clarification on?

3. **How did specialization change your agents?** Quality improvement observed?

4. **What orchestration challenges did you encounter?** How did you solve them?

---

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Share orchestration approaches

### Common Questions This Week

**Q: How do I know if I've specialized enough?**
A: Each agent should have a single clear responsibility. If you can't describe what an agent does in one sentence, it might need splitting.

**Q: Can I have agents call each other directly?**
A: Keep it simple - use the orchestrator for all inter-agent communication. Direct calls add complexity.

**Q: What if my agents need to share context?**
A: Pass context through the orchestrator. Use the state management from Week 4.

### When to Ask for Help

- **Before asking:** Try running integration tests, check agent outputs
- **Good to ask:** "My handoff from Agent A to Agent B fails with [error]. Input is [X], expected output is [Y]."
- **Include:** Agent definitions, input/output formats, error details

---

## Looking Ahead

### Next Week Preview: Week 6 - Optimization & Monitoring

**Focus:**
Production readiness, performance dashboards, cost optimization, and reliability patterns.

**How It Builds on This Week:**
Your multi-agent system will be optimized for cost and performance, with monitoring to track health.

**To Prepare:**
- [ ] Complete all Week 5 exercises
- [ ] Ensure orchestration is working reliably
- [ ] Run multi-agent system 5+ times
- [ ] Document any performance issues

---

## Glossary

| Term | Definition |
|------|------------|
| Specialization | Each agent focuses on one specific responsibility |
| Orchestrator | Component that coordinates agent execution |
| Sequential Orchestration | Agents execute in order, output → input chain |
| Master-Worker | Master decomposes tasks, workers execute, master aggregates |
| Parallel Pattern | Multiple agents execute simultaneously, results merged |
| Team-Based Pattern | Agents with distinct roles that collaborate |
| Integration Testing | Verifying multi-agent coordination works correctly |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [Week 4 Participant Guide](../week-4/participant-guide.md) | **Week 5** | [Week 6 Participant Guide](../week-6/participant-guide.md)
