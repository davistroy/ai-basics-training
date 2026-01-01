# **BLOCK 3 WEEK 2: Building Reliable Agents**

**Block:** 3: AI Automation Architecture
**Week:** 2 of 8
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Block Navigation:** [Week 1 Participant Guide](../week-1/participant-guide.md) | **Week 2** | [Week 3 Participant Guide](../week-3/participant-guide.md)

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
| 1 | Apply the Three Pillars of Domain Memory to make agents reliable | Exercise 2.1 |
| 2 | Implement the agent execution loop with proper bounds | Exercise 2.1 |
| 3 | Add comprehensive error handling for tool, reasoning, context, and quality failures | Exercise 2.2 |
| 4 | Document failure modes with detection and recovery strategies | Exercise 2.3 |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Agent design document completed (Exercise 1.2)
- [ ] Agent skeleton created in GitHub (Exercise 1.3)
- [ ] System prompt drafted
- [ ] Tools identified and MCP servers noted
- [ ] Success criteria defined

**Not ready?** Complete Week 1 exercises before proceeding. You need the design document as your implementation foundation.

---

## Key Concepts

### Concept 1: Domain Memory - The Three Pillars

**Definition:**
Domain Memory is the external state system that enables stateless agents to work reliably. It consists of three pillars that must be explicitly implemented.

**Why It Matters:**
Without Domain Memory, agents forget between sessions, interpret "done" differently each time, and repeat the same failures. The Three Pillars solve each of these problems.

**The Three Pillars:**

| Pillar | Purpose | Implementation |
|--------|---------|----------------|
| **Explicit Goals** | Testable success criteria | Define in design doc, check in execution |
| **Progress Records** | What's been completed, attempted, failed | Log after each action |
| **Operating Procedures** | How to validate, when to escalate | Encode in system prompt and error handling |

**Core Principle:**
> "If you can't test it, it's not a goal - it's a wish."

**Application to Your Agent:**
- Your Week 1 design document IS the Setup Agent output
- Your execution logs become Progress Records
- Your error handling becomes Operating Procedures

**Common Mistake:**
Defining vague goals like "help the user" instead of testable criteria like "generate response for all sections with quality score >= 4.0"

---

### Concept 2: The Agent Execution Loop

**Definition:**
The agent execution loop is the core pattern that drives agent behavior: Receive task, analyze, decide, execute, observe, check goal, loop or complete.

**Why It Matters:**
Understanding the loop is essential for implementing agents. Each step must be explicit, and the loop must have bounds to prevent infinite execution.

**The Loop:**
```
START
  |
[Receive task/context]
  |
[Analyze situation] <--------------+
  |                                |
[Decide next action]               |
  |                                |
[Execute action using tool]        |
  |                                |
[Observe result]                   |
  |                                |
[Goal achieved?] --No--------------+
  | Yes
[Generate final output]
  |
END
```

**Key Implementation Concepts:**

| Concept | Purpose | Example |
|---------|---------|---------|
| **Max iterations** | Prevent infinite loops | `if iteration > 100: stop()` |
| **State management** | Track progress between iterations | Update state object after each action |
| **Tool result parsing** | Extract useful information from tools | Validate format, handle missing fields |
| **Completion detection** | Know when goal is achieved | Check success criteria after each iteration |

**When to Stop:**
- Goal achieved (success criteria met)
- Maximum iterations reached
- Timeout exceeded
- Unrecoverable error encountered
- Escalation triggered

---

### Concept 3: Error Handling for Agents

**Definition:**
Systematic approaches to detecting, categorizing, and responding to failures during agent execution.

**Why It Matters:**
Agents interact with external tools and make decisions based on uncertain information. Errors are inevitable. Good error handling makes the difference between fragile and reliable agents.

**Types of Agent Failures:**

| Type | Description | Examples |
|------|-------------|----------|
| **Tool Failures** | External system issues | API down, permission denied, timeout |
| **Reasoning Failures** | Agent logic issues | Gets confused, loops, wrong decisions |
| **Context Failures** | State management issues | Loses track of goal, forgets state |
| **Quality Failures** | Output issues | Wrong answer, poor formatting, incomplete |

**Error Handling Strategy:**
```
For each action:
  TRY:
    Execute tool
    Validate result
  CATCH tool_error:
    Log error
    IF retryable: retry with backoff
    ELSE: use fallback OR escalate
  CATCH validation_error:
    Request clarification OR try alternative
```

---

### Concept 4: The Circuit Breaker Pattern

**Definition:**
A safety mechanism that automatically stops agent execution when certain thresholds are exceeded, preventing runaway costs or infinite loops.

**Why It Matters:**
Without bounds, agents can loop forever, drain API budgets, or produce mountains of garbage. The circuit breaker is your safety net.

**Implementation:**
```python
class CircuitBreaker:
    max_iterations = 100
    timeout_seconds = 1800  # 30 minutes
    max_consecutive_errors = 3

    def check(self):
        if self.iteration > self.max_iterations:
            raise CircuitBreakerTripped("Iteration limit")
        if elapsed > self.timeout:
            raise CircuitBreakerTripped("Timeout")
        if self.consecutive_errors >= self.max_consecutive_errors:
            raise CircuitBreakerTripped("Error limit - escalate to human")
```

**Key Thresholds:**

| Threshold | Typical Value | Purpose |
|-----------|---------------|---------|
| Max iterations | 50-100 | Prevent infinite loops |
| Timeout | 15-30 minutes | Prevent hung processes |
| Consecutive errors | 3 | Detect stuck agent |

---

### Concept 5: The 3-Failure Rule

**Definition:**
After 3 consecutive failures at the same task, escalate to a human rather than continuing to retry.

**Why It Matters:**
LLMs CAN recover from errors - they read error messages and adapt. But after 3 tries, if the agent is still failing, it's stuck. More attempts won't help; they'll just waste resources.

**Core Principle:**
> "After 3 failures, escalate - don't thrash indefinitely."

**Application:**
```
attempt = 0
while attempt < 3:
    result = try_action()
    if result.success:
        break
    attempt += 1

if attempt >= 3:
    escalate_to_human(context, last_error)
```

**When to Adjust:**
- Critical operations: Lower threshold (2 failures)
- Low-risk operations: Higher threshold (5 failures)
- But never unlimited retries

---

### Quick Reference: Error Handling Matrix

| Failure Type | Detection | Auto-Recover? | Action |
|--------------|-----------|---------------|--------|
| Tool timeout | No response in 30s | Yes | Retry 3x with backoff |
| Invalid output | Validation fails | Yes | Regenerate with guidance |
| Loop detected | >10 same actions | No | Stop and alert |
| Goal lost | Off-topic response | Yes | Reset context |
| Complete failure | All retries failed | No | Escalate to human |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Building the first functional agent with Domain Memory and comprehensive error handling.

**Key Points from Each Segment:**

**Segment 1: Domain Memory - What Makes Agents Reliable**
- Three Pillars: Explicit Goals, Progress Records, Operating Procedures
- Your design document IS Domain Memory - the Setup Agent output
- "If you can't test it, it's not a goal - it's a wish"

**Segment 2: The Agent Execution Loop**
- Core pattern: Receive → Analyze → Decide → Execute → Observe → Loop
- Every loop needs bounds: max iterations, timeout, error limits
- Completion detection from success criteria

**Segment 3: Error Handling for Agents**
- Four failure types: Tool, Reasoning, Context, Quality
- Error handling strategy: Try → Catch → Decide (retry/fallback/escalate)
- Circuit Breaker pattern prevents runaway execution

**Segment 4: Live Demo - Building First Agent**
- System prompt with role and tools
- Initial context and tool configuration
- Execution loop with error handling

**Segment 5: Testing Agent Reliability**
- Test categories: Happy path, Edge cases, Error cases, Stress cases
- Start simple, systematically break things

### Demo Recap

**What Was Demonstrated:**
Research Assistant agent that answers questions using multiple sources

**Key Steps:**
1. System prompt defined role (researcher) and tools (web search, file reader, note taker)
2. Initial context setup with the research question
3. MCP configuration for all tools
4. Agent executed the observe-think-act loop
5. Error handling caught a timeout and recovered
6. Agent completed when answer quality threshold met

**Result:**
A working agent that demonstrates the execution loop with proper error handling.

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 2.1 | 40 min | Working agent + execution docs | Build functional agent |
| 2.2 | 20 min | Error handling + test results | Make agent resilient |
| 2.3 | 15 min | `failure-modes.md` | Document what can go wrong |

---

### Exercise 2.1: Build Functional Agent

**Duration:** 40 minutes

**Purpose:**
Create your first working agent based on your Week 1 design document. This exercise moves you from design to implementation.

**You Will Create:**
A functional agent that executes the observe-think-act loop and produces output.

---

#### Instructions

**Step 1: Prepare Your System Prompt**
Refine your Week 1 system prompt with specific tool instructions:

```markdown
# System Prompt: [Agent Name]

## Role
You are an AI agent that [description of role].

## Goal
Your objective is to [primary goal from design document].

## Available Tools
You have access to the following tools:
1. [Tool 1]: [Description and when to use]
2. [Tool 2]: [Description and when to use]
3. [Tool 3]: [Description and when to use]

## Decision Guidelines
When deciding what to do:
- First, [initial action]
- If [condition], then [action]
- When [situation], prefer [approach]

## Constraints
- Maximum [X] iterations before stopping
- Must validate output against [criteria]
- Cannot [prohibited action]

## Output Format
[Exact format specification]

## When to Stop
Stop and report completion when:
- [Success criterion 1 is met]
- [Success criterion 2 is met]

Stop and request help when:
- [Escalation trigger 1]
- [Escalation trigger 2]
```

**Step 2: Configure MCP Tools**
Verify your Claude Desktop MCP configuration includes all required tools:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/allowed/directory"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "your-token"
      }
    }
  }
}
```

**Step 3: Create Agent Runner**
In your automation platform (Make/n8n), create a runner workflow:

```
Trigger → [Prepare Context] → [Call Agent API] → [Parse Response]
                                    ↓
                              [Agent uses tools]
                                    ↓
                              [Loop until done]
                                    ↓
                      [Extract final output] → [Deliver result]
```

**Step 4: Run Initial Tests**
Execute your agent with these test scenarios:
- Simple request (should complete in 2-3 iterations)
- Moderate complexity (may need 5-7 iterations)

**Step 5: Document Execution**
Create an execution log:

```markdown
# Agent Execution Log

## Test 1: [Simple Request]
- **Input:** [Exact request]
- **Tools used:** [List in order]
- **Iterations:** [Count]
- **Duration:** [Time in seconds]
- **Output quality:** [Assessment 1-5]
- **Issues:** [Any problems encountered]

## Test 2: [Moderate Request]
- **Input:** [Exact request]
- **Tools used:** [List in order]
- **Iterations:** [Count]
- **Duration:** [Time in seconds]
- **Output quality:** [Assessment 1-5]
- **Issues:** [Any problems encountered]
```

**Step 6: Review Your Work**
Check that your agent:
- [ ] Executes and produces output
- [ ] Uses at least one tool
- [ ] Stops when goal is achieved
- [ ] Has documented 2+ test executions

---

#### Deliverable Specification

**File Name:** Working agent + `execution-log.md`

**Location:** `/agents/[agent-name]/` in your GitHub repo

**Format Requirements:**
- System prompt in `/prompts/system-prompt.md`
- Execution log with all test results
- MCP configuration documented

**Quality Criteria:**
- [ ] Agent successfully executes at least 2 different requests
- [ ] Execution log includes all required fields
- [ ] Tool usage is appropriate for the task
- [ ] Agent stops appropriately (not infinite loop)

---

#### Example

**Execution Log Entry:**
```markdown
## Test 1: Simple Research Query
- **Input:** "What are the top 3 benefits of using TypeScript over JavaScript?"
- **Tools used:** web_search (2x), note_taker (1x)
- **Iterations:** 4
- **Duration:** 45 seconds
- **Output quality:** 4/5 (accurate, but could be more detailed)
- **Issues:** First web search returned irrelevant results, agent correctly tried again with refined query

## Test 2: Multi-Source Analysis
- **Input:** "Compare the latest features of React 18 vs Vue 3, with examples"
- **Tools used:** web_search (4x), file_reader (1x), note_taker (2x)
- **Iterations:** 7
- **Duration:** 95 seconds
- **Output quality:** 5/5 (comprehensive comparison with code examples)
- **Issues:** None - agent effectively combined multiple sources
```

---

#### Tips & Troubleshooting

**Tips:**
- Start with your simplest tool first
- Test each tool individually before combining
- Watch the Claude interface to see agent reasoning

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Agent loops forever | Add max iteration check in system prompt |
| Tools not available | Verify MCP config, restart Claude Desktop |
| Output format wrong | Add explicit format instructions in prompt |
| Agent stops too early | Adjust completion criteria |

---

### Exercise 2.2: Implement Error Handling

**Duration:** 20 minutes

**Purpose:**
Make your agent resilient by adding systematic error handling for all failure types.

**You Will Create:**
Error handling configuration and test documentation.

---

#### Instructions

**Step 1: Create Error Handling Configuration**

```markdown
# Error Handling Configuration

## Tool Errors

### [Tool 1: e.g., Filesystem] Failures
- **Possible errors:** File not found, permission denied, file too large
- **Retry strategy:** 2 attempts with 1-second delay
- **Fallback:** Skip file and note as unavailable
- **Escalation:** After 2 failures on critical file, stop and report

### [Tool 2: e.g., Web Search] Failures
- **Possible errors:** Timeout, rate limit, no results
- **Retry strategy:** 3 attempts with exponential backoff (1s, 2s, 4s)
- **Fallback:** Use cached results or alternative search
- **Escalation:** After 3 failures, continue with available data

## Agent Logic Errors

### Loop Detection
- **Max iterations:** [Number, e.g., 50]
- **Detection method:** Count iterations, detect repeated actions
- **Response:** Stop, save progress, alert

### Goal Confusion
- **Detection:** Agent output doesn't relate to original goal
- **Response:** Reset context with goal reminder, try once more

## Quality Errors

### Output Validation
- **Checks:**
  - Output format matches specification
  - All required sections present
  - Quality score meets threshold
- **Response:** Regenerate with specific guidance, max 2 retries
```

**Step 2: Add to System Prompt**
Update your system prompt with error handling instructions:

```markdown
## Error Handling

If a tool fails:
1. Log the error with context
2. If retryable, wait [X] seconds and retry (max 3 times)
3. If not retryable, use fallback approach
4. If all retries fail, escalate to human

If you're confused about the goal:
1. Re-read the original request
2. Summarize what you've accomplished
3. Identify what remains
4. If still unclear, stop and request clarification

If output quality is low:
1. Identify specific weaknesses
2. Attempt to improve with targeted action
3. If quality still insufficient after 2 attempts, deliver best effort with quality note
```

**Step 3: Test Error Handling**
Deliberately trigger failures:
- Force a tool error (e.g., request non-existent file)
- Provide ambiguous input that might confuse the agent
- Test iteration limits

**Step 4: Document Test Results**

```markdown
# Error Handling Test Results

## Test 1: Tool Failure Recovery
- **Trigger:** Requested read of non-existent file
- **Expected:** Agent retries, then falls back
- **Actual:** [What happened]
- **Pass/Fail:** [Result]

## Test 2: Invalid Input Handling
- **Trigger:** Ambiguous request with unclear goal
- **Expected:** Agent asks for clarification or makes reasonable assumption
- **Actual:** [What happened]
- **Pass/Fail:** [Result]

## Test 3: Iteration Limit
- **Trigger:** Complex request likely to need many iterations
- **Expected:** Agent stops at max iterations with partial result
- **Actual:** [What happened]
- **Pass/Fail:** [Result]
```

---

#### Deliverable Specification

**File Name:** `error-handling-config.md` + test documentation

**Location:** `/agents/[agent-name]/config/`

**Quality Criteria:**
- [ ] All tool error scenarios covered
- [ ] Retry strategies include backoff
- [ ] Escalation triggers are specific
- [ ] At least 3 error scenarios tested

---

### Exercise 2.3: Failure Mode Documentation

**Duration:** 15 minutes

**Purpose:**
Create a comprehensive catalog of what can go wrong with your agent and how to handle each failure.

**You Will Create:**
A failure mode document specific to your agent.

---

#### Instructions

**Step 1: Identify Failure Modes**
Based on your tests and analysis, list all ways your agent can fail.

**Step 2: Create Failure Mode Catalog**

```markdown
# Agent Failure Modes

## Agent: [Name]

### Failure Mode 1: [Name, e.g., "Tool Timeout"]
- **Description:** Web search tool doesn't respond within expected time
- **Trigger:** Network issues, API rate limiting, overloaded servers
- **Frequency:** Common (1 in 10 executions)
- **Impact:** Medium - delays completion
- **Detection:** No response after 30 seconds
- **Prevention:** Implement timeout with retry
- **Recovery:** Retry with backoff, fall back to cached data

### Failure Mode 2: [Name, e.g., "Loop Trap"]
- **Description:** Agent repeats the same action without progress
- **Trigger:** Ambiguous success criteria, unclear goal
- **Frequency:** Rare (1 in 50 executions)
- **Impact:** High - wastes resources, produces no output
- **Detection:** Same action repeated 3+ times
- **Prevention:** Clear success criteria, explicit stop conditions
- **Recovery:** Force stop, log context, escalate

### Failure Mode 3: [Name, e.g., "Quality Below Threshold"]
- **Description:** Agent produces output that fails quality checks
- **Trigger:** Insufficient source data, misunderstanding of requirements
- **Frequency:** Occasional (1 in 20 executions)
- **Impact:** Medium - requires human review
- **Detection:** Quality score < 4.0
- **Prevention:** Better prompts, more source data
- **Recovery:** Regenerate with feedback, max 2 retries

---

## Failure Response Matrix

| Failure Type | Detection | Auto-Recover? | Action |
|--------------|-----------|---------------|--------|
| Tool timeout | No response 30s | Yes | Retry 3x with backoff |
| Invalid output | Validation fail | Yes | Regenerate with guidance |
| Loop detected | >5 repeated actions | No | Stop, alert |
| Goal confusion | Off-topic response | Yes | Reset context |
| Complete failure | All retries failed | No | Escalate to human |
| [Add your specific failures] | | | |

---

## Monitoring Triggers

Set alerts for:
- [ ] Error rate > 20%
- [ ] Avg iterations > [your threshold]
- [ ] Completion rate < 80%
- [ ] Duration > [your max acceptable time]
```

---

#### Deliverable Specification

**File Name:** `failure-modes.md`

**Location:** `/agents/[agent-name]/`

**Quality Criteria:**
- [ ] At least 3 specific failure modes documented
- [ ] Each failure mode has all required fields
- [ ] Response matrix matches your actual error handling
- [ ] Monitoring triggers are realistic for your agent

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| System Prompt Enhancement | Add error handling instructions | Exercise 2.1 |
| Error Handling Config | Document tool and logic errors | Exercise 2.2 |
| Failure Mode Catalog | Comprehensive failure documentation | Exercise 2.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Anthropic Agent Documentation | Documentation | [docs.anthropic.com](https://docs.anthropic.com/en/docs/agents) | Agent patterns and best practices |
| Circuit Breaker Pattern | Reference | [Martin Fowler](https://martinfowler.com/bliki/CircuitBreaker.html) | Understanding pattern deeply |
| MCP Documentation | Documentation | [modelcontextprotocol.io](https://modelcontextprotocol.io/) | Tool configuration |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Apply Domain Memory pillars | Design doc as Setup Agent output | |
| 2 | Implement agent execution loop | Working agent with iterations | |
| 3 | Add comprehensive error handling | Error config + test results | |
| 4 | Document failure modes | Specific failure-modes.md | |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 2.1 output | Working agent + `execution-log.md` | `/agents/[name]/` | |
| Exercise 2.2 output | `error-handling-config.md` + tests | `/agents/[name]/config/` | |
| Exercise 2.3 output | `failure-modes.md` | `/agents/[name]/` | |

**Execution Target:** 5+ successful agent executions this week

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** What concept or technique suddenly made sense?

2. **What's still fuzzy?** What do you need more practice or clarification on?

3. **How did your agent surprise you?** What did it do that you didn't expect?

4. **What failure modes did you discover?** Were any unexpected?

---

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Tag your cohort for quick tips

### Common Questions This Week

**Q: My agent loops forever - what do I do?**
A: Add explicit iteration limits in your system prompt AND in your runner workflow. The agent should count iterations and stop at max (e.g., 50).

**Q: How do I test error handling without waiting for real failures?**
A: Deliberately trigger failures - request non-existent files, use invalid inputs, set artificially low timeouts.

**Q: My agent keeps using the wrong tool - how do I fix this?**
A: Make tool selection criteria more explicit in your system prompt. Add "When to use" and "When NOT to use" for each tool.

### When to Ask for Help

- **Before asking:** Check this guide's troubleshooting sections
- **Good to ask:** "My agent failed with this error: [specific error]. I tried [approach]. What am I missing?"
- **Include:** Your system prompt, the error, and what you've already tried

---

## Looking Ahead

### Next Week Preview: Week 3 - MCP Deep Dive

**Focus:**
Advanced MCP architecture, multi-server configuration, tool chaining patterns, and security best practices.

**How It Builds on This Week:**
Your functional agent will gain access to multiple MCP servers and learn to chain tools together for complex tasks.

**To Prepare:**
- [ ] Complete all Week 2 exercises
- [ ] Ensure agent is functional with at least one tool
- [ ] Review MCP servers available for your use case
- [ ] Run your agent 5+ times to build confidence

---

## Glossary

| Term | Definition |
|------|------------|
| Domain Memory | External state (goals, progress, procedures) that enables stateless agents to work reliably |
| Agent Loop | The observe-think-act cycle that drives agent behavior |
| Circuit Breaker | Safety mechanism that stops execution when thresholds are exceeded |
| Tool Failure | Error from external tools (APIs, file systems, etc.) |
| Reasoning Failure | Agent logic errors (confusion, loops, wrong decisions) |
| Context Failure | State management errors (lost goal, forgotten state) |
| Quality Failure | Output errors (wrong answer, poor format, incomplete) |
| 3-Failure Rule | Escalate to human after 3 consecutive failures at the same task |
| Backoff | Increasing delay between retry attempts |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [Week 1 Participant Guide](../week-1/participant-guide.md) | **Week 2** | [Week 3 Participant Guide](../week-3/participant-guide.md)
