# Week 5: Agent Specialization & Orchestration

**Block:** 3 - AI Automation Architecture
**Duration:** 45 min live workshop + 75 min self-paced exercises

---

## Entry Criteria

- [ ] Multi-step agent working
- [ ] State management implemented
- [ ] Checkpoint system functional
- [ ] 15+ successful agent executions

## Exit Criteria

- [ ] Agent specialization concept applied
- [ ] Sequential orchestration pattern implemented
- [ ] Master-Worker pattern understood
- [ ] Multi-agent coordination designed
- [ ] Orchestration for capstone planned

---

## Workshop Content (45 minutes)

### Segment 1: The Specialization Principle (10 min)

**Core concept:** One agent = One thing done well

**Why specialization matters:**
- Focused prompts = better results
- Easier to test and debug
- Simpler error handling
- Reusable components
- Prevents "bloated agent syndrome"

**Signs of a bloated agent:**
- System prompt > 2000 words
- Agent gets confused about role
- Too many tools to choose from
- Inconsistent quality
- Hard to debug failures

**Specialization examples:**
- Research Agent: Only gathers information
- Analysis Agent: Only analyzes data
- Writer Agent: Only produces content
- Reviewer Agent: Only evaluates quality

### Segment 2: Sequential Orchestration Pattern (12 min)

**Pattern overview:**
```
Agent A → Agent B → Agent C → Final Output
(Research)  (Analyze)  (Write)
```

**How it works:**
1. Orchestrator receives task
2. Calls Agent A with initial input
3. Takes Agent A output, passes to Agent B
4. Takes Agent B output, passes to Agent C
5. Collects final output

**Implementation:**
```
ORCHESTRATOR:
  input = user_request

  # Step 1: Research
  research_result = call_agent("research", input)
  validate(research_result)

  # Step 2: Analyze
  analysis_result = call_agent("analyze", research_result)
  validate(analysis_result)

  # Step 3: Write
  final_output = call_agent("write", analysis_result)
  validate(final_output)

  return final_output
```

**When to use:**
- Clear sequential dependency
- Each stage has distinct skill
- Quality gates between stages

### Segment 3: Master-Worker Pattern (12 min)

**Pattern overview:**
```
                  ┌→ Worker A ─┐
Master (Planner) ─┼→ Worker B ─┼→ Master (Aggregator) → Output
                  └→ Worker C ─┘
```

**How it works:**
1. Master decomposes task into subtasks
2. Master assigns subtasks to workers
3. Workers execute independently (can be parallel)
4. Master collects and aggregates results
5. Master produces final output

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

**When to use:**
- Task can be parallelized
- Workers are interchangeable
- Results need synthesis

### Segment 4: Other Patterns + Planning (11 min)

**Parallel Pattern (mention only):**
- Multiple agents work simultaneously
- No dependency between them
- Results merged at end
- Good for: Multiple independent analyses

**Team-Based Pattern (mention only):**
- Agents with distinct roles collaborate
- Can interact with each other
- Complex coordination
- Good for: Simulated expert panels

**Choosing your pattern:**

| Pattern | Use When | Complexity |
|---------|----------|------------|
| Sequential | Clear stages, dependencies | Low |
| Master-Worker | Decomposable, aggregatable | Medium |
| Parallel | Independent analyses | Medium |
| Team-Based | Complex collaboration | High |

**For your capstone:**
- Recommend: Sequential or Master-Worker
- Design which pattern fits your task
- Keep it simple - can expand later

---

## Self-Paced Exercises (75 minutes total)

### Exercise 5.1: Agent Decomposition (25 minutes)

*Break your agent into specialists*

1. **Analyze your current agent:**

```markdown
# Agent Decomposition Analysis

## Current Agent: [Name]
**Current scope:** [What it does - probably too much]

## Identified Responsibilities
List everything your agent currently does:
1. [Responsibility 1]
2. [Responsibility 2]
3. [Responsibility 3]
...

## Candidate Specialists

### Specialist 1: [Name] Agent
**Focus:** [Single responsibility]
**Inputs:** [What it receives]
**Outputs:** [What it produces]
**Tools needed:** [Subset of tools]
**Why separate:** [Benefit of specialization]

### Specialist 2: [Name] Agent
[Repeat structure]

### Specialist 3: [Name] Agent
[Repeat structure]

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

**Deliverable:** Agent decomposition document

---

### Exercise 5.2: Orchestration Implementation (30 minutes)

*Build your orchestration layer*

1. **Choose and implement pattern:**

**For Sequential Pattern:**

```markdown
# Sequential Orchestration Design

## Pipeline Flow
\`\`\`
[Input] → [Agent 1] → [Agent 2] → [Agent 3] → [Output]
\`\`\`

## Agent Definitions

### Agent 1: [Name]
- **System prompt:** [Link or summary]
- **Input format:** [Schema]
- **Output format:** [Schema]
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

    # Execution (can parallelize)
    results = []
    for task in subtasks:
        result = worker.run(task)
        results.append(result)

    # Aggregation
    final = master.aggregate(results)
    return final
\`\`\`
```

2. **Implement in your platform**

3. **Test with sample task**

**Deliverable:** Orchestration design + working implementation

---

### Exercise 5.3: Integration Testing (20 minutes)

*Verify multi-agent coordination*

1. **Create integration test suite:**

```markdown
# Multi-Agent Integration Tests

## Test 1: Happy Path - Complete Flow
- **Input:** [Standard valid input]
- **Expected flow:** Agent1 → Agent2 → Agent3
- **Expected output:** [What success looks like]
- **Result:** [Pass/Fail + notes]

## Test 2: Handoff Validation
- **Focus:** Data passes correctly between agents
- **Check:** Agent 2 receives correct input from Agent 1
- **Check:** Agent 3 receives correct input from Agent 2
- **Result:** [Pass/Fail + notes]

## Test 3: Single Agent Failure
- **Scenario:** Agent 2 fails
- **Expected behavior:** [How system handles]
- **Result:** [Pass/Fail + notes]

## Test 4: Quality Gate Rejection
- **Scenario:** Agent 1 output fails validation
- **Expected behavior:** [Retry/escalate]
- **Result:** [Pass/Fail + notes]

## Test 5: End-to-End Performance
- **Measure:** Total execution time
- **Measure:** Per-agent time
- **Baseline:** [Target time]
- **Result:** [Actual time]

## Test Summary
| Test | Status | Notes |
|------|--------|-------|
| 1. Happy Path | | |
| 2. Handoff | | |
| 3. Failure | | |
| 4. Quality Gate | | |
| 5. Performance | | |
```

**Deliverable:** Integration test results

---

### Exercise 5.4: Agent Architecture Review (Optional - 30 minutes)

*Peer review of agent designs*

**If you have a learning partner:**

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

## Key Takeaways

1. **Specialization improves quality** - One agent, one job
2. **Sequential for pipelines** - Clear stages with dependencies
3. **Master-Worker for decomposition** - Divide and conquer
4. **Orchestration adds reliability** - Validation between agents
5. **Test the whole system** - Integration testing is essential

---

## Preparation for Week 6

- Complete orchestration implementation
- Run multi-agent system 5+ times
- Document performance and issues
- Next week: Optimization and monitoring

---

## Resources

- [Multi-Agent Systems](https://docs.anthropic.com/en/docs/agents)
- [Orchestration Patterns](https://microservices.io/patterns/data/saga.html)
