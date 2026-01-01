# Week 2: Building Reliable Agents

**Block:** 3 - AI Automation Architecture
**Duration:** 45 min live workshop + 75 min self-paced exercises

---

## Entry Criteria

- [ ] Agent design document completed
- [ ] Agent skeleton created in GitHub
- [ ] System prompt drafted
- [ ] Tools identified and MCP servers noted
- [ ] Success criteria defined

## Exit Criteria

- [ ] First functional agent running
- [ ] Basic error handling implemented
- [ ] Agent loop pattern understood
- [ ] 5+ successful agent executions
- [ ] Failure modes identified and documented

---

## Workshop Content (45 minutes)

### Segment 1: Domain Memory - What Makes Agents Reliable (8 min)

**Recall from presentation:** The fundamental insight is that agents are "unreliable amnesiacs"

**Today's application:** We make amnesiacs effective by building systems with memory

**The Three Pillars of Domain Memory:**

1. **EXPLICIT GOALS**
   - What "done" means with testable criteria
   - "Run login_test.py, all assertions pass" vs "Build login"
   - If you can't test it, it's not a goal—it's a wish

2. **PROGRESS RECORDS**
   - What's been completed, attempted, failed
   - "Tuesday: Tried approach A → timeout failure"
   - Prevents Groundhog Day loops

3. **OPERATING PROCEDURES**
   - How to validate, when to escalate
   - "After any change, run test suite"
   - "After 3 failures, escalate to human"

**Why this matters for your agent:**
- Your agent design document (from Week 1) becomes the Setup Agent output
- Your execution logs become Progress Records
- Your error handling becomes Operating Procedures

### Segment 2: The Agent Execution Loop (8 min)

**Understanding the loop:**
```
START
  ↓
[Receive task/context]
  ↓
[Analyze situation] ←──────────────┐
  ↓                                │
[Decide next action]               │
  ↓                                │
[Execute action using tool]        │
  ↓                                │
[Observe result]                   │
  ↓                                │
[Goal achieved?] ──No──────────────┘
  ↓ Yes
[Generate final output]
  ↓
END
```

**Key implementation concepts:**
- Maximum iterations (prevent infinite loops)
- State management between iterations
- Tool result parsing
- Completion detection

### Segment 3: Error Handling for Agents (13 min)

**Types of agent failures:**
1. **Tool failures:** API down, permission denied, timeout
2. **Reasoning failures:** Agent gets confused, loops
3. **Context failures:** Loses track of goal, forgets state
4. **Quality failures:** Produces wrong/poor output

**Error handling strategies:**

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

**The Circuit Breaker Pattern:**

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

**The 3-Failure Rule:**
- LLMs CAN recover from errors (they read error messages and adapt)
- BUT after 3 consecutive failures, the agent is probably stuck
- It's tried its best approaches; more attempts won't help
- ESCALATE to human rather than thrashing indefinitely

**Multi-Agent Error Propagation:**
When a sub-agent fails:
- Return structured failure info (not a crash)
- Include: success flag, partial work completed, can_retry boolean
- Let parent agent decide: retry, work around, or escalate

### Segment 4: Building Your First Agent - Live Demo (9 min)

**Demo agent:** Research Assistant
- Goal: Answer questions using multiple sources
- Tools: Web search, file reader, note taker

**Live build:**
1. System prompt with role and tools
2. Initial context setup
3. Tool configuration via MCP
4. Execution loop implementation
5. Error handling addition
6. Test execution

### Segment 5: Testing Agent Reliability (7 min)

**Test categories:**
1. **Happy path:** Normal inputs, everything works
2. **Edge cases:** Unusual but valid inputs
3. **Error cases:** Invalid inputs, tool failures
4. **Stress cases:** Large inputs, many iterations

**Testing approach:**
- Start with happy path
- Systematically break things
- Document all failure modes
- Build handling for each

---

## Self-Paced Exercises (75 minutes total)

### Exercise 2.1: Build Functional Agent (40 minutes)

*Create your first working agent*

1. **Implement agent in your automation platform:**

   Using Claude with MCP (recommended approach):

   ```markdown
   # Agent Execution Framework

   ## System Prompt
   [Your system prompt from Week 1]

   ## Execution Process

   1. Initialize with user request
   2. Agent analyzes and plans
   3. Agent uses tools via MCP
   4. Agent evaluates progress
   5. Agent continues or completes

   ## Tool Integration
   - Configure MCP servers for all required tools
   - Test each tool individually first
   - Combine in agent context
   ```

2. **Create agent runner (in Make/n8n):**
   ```
   Trigger → [Prepare Context] → [Call Agent API] → [Parse Response]
                                       ↓
                                 [Agent uses tools]
                                       ↓
                                 [Loop until done]
                                       ↓
                           [Extract final output] → [Deliver result]
   ```

3. **Run initial tests:**
   - Test with simple request
   - Test with moderate complexity
   - Document behavior

4. **Document execution:**

```markdown
# Agent Execution Log

## Test 1: [Simple Request]
- **Input:** [Request]
- **Tools used:** [List]
- **Iterations:** [Count]
- **Duration:** [Time]
- **Output quality:** [Assessment]
- **Issues:** [Any problems]

## Test 2: [Moderate Request]
[Repeat structure]
```

**Deliverable:** Working agent + execution documentation

---

### Exercise 2.2: Implement Error Handling (20 minutes)

*Make your agent resilient*

1. **Add error handling layer:**

```markdown
# Error Handling Configuration

## Tool Errors

### [Tool 1] Failures
- **Possible errors:** [List]
- **Retry strategy:** [Attempts, backoff]
- **Fallback:** [Alternative action]
- **Escalation:** [When to stop]

### [Tool 2] Failures
[Repeat structure]

## Agent Logic Errors

### Loop Detection
- **Max iterations:** [Number]
- **Detection method:** [How to detect]
- **Response:** [What to do]

### Goal Confusion
- **Detection:** [Symptoms]
- **Response:** [Reset, clarify, escalate]

## Quality Errors

### Output Validation
- **Checks:** [What to verify]
- **Response:** [Retry, adjust, escalate]
```

2. **Implement in your agent:**
   - Add try/catch patterns around tool calls
   - Add iteration counter with maximum
   - Add output validation step
   - Add logging for all errors

3. **Test error handling:**
   - Deliberately trigger a tool failure
   - Force an invalid input
   - Verify graceful handling

**Deliverable:** Error handling added + test results documented

---

### Exercise 2.3: Failure Mode Documentation (15 minutes)

*Know what can go wrong*

1. **Create failure mode catalog:**

```markdown
# Agent Failure Modes

## Agent: [Name]

### Failure Mode 1: [Name]
- **Description:** [What happens]
- **Trigger:** [What causes it]
- **Frequency:** [Common/Rare]
- **Impact:** [Severity]
- **Detection:** [How you know]
- **Prevention:** [How to avoid]
- **Recovery:** [How to fix]

### Failure Mode 2: [Name]
[Repeat structure]

---

## Failure Response Matrix

| Failure Type | Detection | Auto-Recover? | Action |
|--------------|-----------|---------------|--------|
| Tool timeout | No response 30s | Yes | Retry 3x |
| Invalid output | Validation fail | Yes | Regenerate |
| Loop detected | >10 iterations | No | Stop, alert |
| Goal lost | Off-topic response | Yes | Reset context |
| Complete failure | All retries failed | No | Escalate human |

---

## Monitoring Triggers

Set alerts for:
- [ ] Error rate > 20%
- [ ] Avg iterations > [threshold]
- [ ] Completion rate < 80%
- [ ] Duration > [max acceptable]
```

**Deliverable:** `failure-modes.md`

---

## Key Takeaways

1. **Domain Memory enables reliability** - Goals, Progress, Procedures
2. **The agent loop is bounded** - Max iterations, timeout, error limits
3. **The 3-Failure Rule** - Escalate rather than thrash
4. **Error handling is not optional** - Plan for every failure mode
5. **Test systematically** - Happy path, edge cases, errors, stress

---

## Preparation for Week 3

- Run your agent 5+ more times with varied inputs
- Document all failures and successes
- Review MCP servers for your agent's needs
- Next week: MCP deep dive

---

## Resources

- [Anthropic Agent Documentation](https://docs.anthropic.com/en/docs/agents)
- [Error Handling Patterns](https://docs.anthropic.com/en/docs/agents)
- [Circuit Breaker Pattern](https://martinfowler.com/bliki/CircuitBreaker.html)
