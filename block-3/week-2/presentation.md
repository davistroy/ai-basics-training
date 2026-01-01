# **POWERPOINT PRESENTATION: BLOCK 3 WEEK 2**
## **Building Reliable Agents**

**Block:** 3: AI Automation Architecture
**Week Number:** 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 participants with completed agent design documents

**Week Learning Objectives:** By the end of this session, participants will:
1. Apply the Three Pillars of Domain Memory to make agents reliable
2. Implement the agent execution loop with proper bounds
3. Add comprehensive error handling for all failure types
4. Understand testing categories for agent reliability

**Entry Criteria:** (What participants should have before this session)
- [ ] Agent design document completed (Week 1)
- [ ] Agent skeleton created in GitHub
- [ ] System prompt drafted
- [ ] Tools identified and MCP servers noted

**Exit Criteria:** (What participants should be able to do after this session)
- [ ] Explain the Three Pillars of Domain Memory
- [ ] Describe the agent execution loop
- [ ] Implement error handling for tool and reasoning failures
- [ ] Apply the 3-Failure Rule and Circuit Breaker pattern

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Domain Memory (8 min) - Slides 4-7
3. Segment 2: Agent Execution Loop (8 min) - Slides 8-11
4. Segment 3: Error Handling (13 min) - Slides 12-18
5. Segment 4: Live Demo (9 min) - Slides 19-20
6. Segment 5: Testing + Homework (4 min) - Slides 21-24

**Total Slides:** 24

---

## SLIDE 1: TITLE SLIDE

**Title:** Block 3 Week 2: Building Reliable Agents

**Subtitle:** From Design to Implementation

**Content:**
- AI Practitioner Training Program
- Block 3: AI Automation Architecture

**Graphic:** Clean title slide with green theme (Block 3 color). Visual of agent construction.

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Week 2: Building Reliable Agents. Last week we covered the fundamental distinction between agents and workflows and the Two-Agent Architecture Pattern. You all created agent design documents.

Today we take those designs and start building. We're focusing on what makes agents reliable - Domain Memory, the execution loop, and error handling.

Quick check-in: What was the hardest part of your agent design document? Any sections that were unclear?

[Wait for 1-2 responses]

Good questions. Let's dig into implementation."

[Transition: Click to next slide]

---

## SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Week 1 Recap |
| 3-11 min | Segment 1 | Domain Memory |
| 11-19 min | Segment 2 | Agent Execution Loop |
| 19-32 min | Segment 3 | Error Handling |
| 32-41 min | Segment 4 | Live Demo |
| 41-45 min | Close | Testing + Homework |

**Graphic:** Timeline showing session flow with green accent colors

**SPEAKER NOTES:**

"Here's our roadmap:

First, Domain Memory - the three pillars that make agents reliable. This connects directly to your design documents.

Then, the agent execution loop - how agents actually run. This is the core pattern you'll implement.

Error handling is our big topic - 13 minutes on making agents resilient. This is what separates fragile agents from reliable ones.

We'll see it all in action with a live demo, then preview your homework.

Ready?"

[Transition]

---

## SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Apply the Three Pillars of Domain Memory**
   - Goals, Progress, Procedures make agents reliable

2. **Implement the agent execution loop**
   - Observe-Think-Act with proper bounds

3. **Add comprehensive error handling**
   - Tool, reasoning, context, and quality failures

4. **Apply the 3-Failure Rule**
   - Know when to escalate instead of retry

**Graphic:** Checklist visual with green checkboxes

**SPEAKER NOTES:**

"Four objectives for today.

[Read each]

Notice we're moving from theory to practice. Your homework this week is building a functional agent. By end of week, you should have 5+ successful executions.

Let's start with what makes agents reliable."

[Transition: Click to Segment 1]

---

## SEGMENT 1: DOMAIN MEMORY
### Duration: 8 minutes | Slides 4-7

---

## SLIDE 4: THE RELIABILITY PROBLEM

**Title:** Why Agents Fail

**Content:**

**The Problem with Naive Agents:**
- No memory between sessions
- Different interpretations of "done"
- Repeated failed attempts (Groundhog Day)
- Context window pollution

**The Insight (From Week 1):**
> "Stop trying to give agents memory. Build systems where amnesiacs can work effectively."

**Graphic:** Visual of agent losing memory between sessions

**SPEAKER NOTES:**

"[Hook - Recall the problem]"

"Recall from last week why single agents fail. No memory between sessions. Every run, they start fresh. They interpret 'done' differently each time. They repeat the same failures.

[Point to insight]

The insight: Don't fight the amnesia. Design around it. Build systems where memory is in the PROJECT, not the agent.

Today we make this practical."

[Transition]

---

## SLIDE 5: THE THREE PILLARS OF DOMAIN MEMORY

**Title:** Domain Memory: Three Pillars

**Content:**

| Pillar | Purpose | Your Implementation |
|--------|---------|---------------------|
| **Explicit Goals** | Testable success criteria | Design doc → Success Criteria |
| **Progress Records** | What's done, tried, failed | Execution logs |
| **Operating Procedures** | How to validate, when to escalate | Error handling code |

**Key Principle:**
> "If you can't test it, it's not a goal - it's a wish."

**Graphic:** Three pillars supporting "Reliable Agents" structure

**SPEAKER NOTES:**

"Domain Memory has three pillars.

[Point to each]

Explicit Goals - testable success criteria. Not 'help the user' but 'generate response for all sections with quality score >= 4.0.' If you can't test it, it's a wish.

Progress Records - what's been completed, attempted, failed. This prevents Groundhog Day loops.

Operating Procedures - how to validate success, when to escalate. This is your error handling.

[Key connection]

Your Week 1 design document maps to these pillars. It's the Setup Agent output!"

[Transition]

---

## SLIDE 6: YOUR DESIGN DOC IS DOMAIN MEMORY

**Title:** Connecting Design to Implementation

**Content:**

**Your Design Document:**
- Goal Definition → **Explicit Goals**
- Domain Memory Design → **Progress Records**
- Risk Assessment + Success Metrics → **Operating Procedures**

**Your Implementation:**
- Design document = Setup Agent output
- Execution logs = Progress Records
- Error handling = Operating Procedures

**Graphic:** Arrows connecting design document sections to Domain Memory pillars

**SPEAKER NOTES:**

"Let's connect this to YOUR work.

[Walk through mappings]

Your Goal Definition section? That's Explicit Goals. Those success criteria become completion checks.

Your Domain Memory Design section? That's Progress Records. What you log after each action.

Your Risk Assessment and Success Metrics? That's Operating Procedures. Error handling and quality checks.

Your design document IS the Setup Agent output. Now we implement it."

[Transition]

---

## SLIDE 7: GOALS MUST BE TESTABLE

**Title:** Goals vs. Wishes

**Content:**

**A Wish:**
> "Build a good login system"

**A Goal:**
> "Run login_test.py - all 15 assertions pass"

| Element | Wish | Goal |
|---------|------|------|
| Specific | ❌ | ✅ |
| Measurable | ❌ | ✅ |
| Testable | ❌ | ✅ |

**Check Your Design Document:**
Are your success criteria testable?

**Graphic:** Side-by-side comparison with checkmarks and X marks

**SPEAKER NOTES:**

"This distinction is critical.

[Point to examples]

'Build a good login' - that's a wish. What's 'good'? How do you know you're done?

'Run login_test.py, all assertions pass' - that's a goal. Specific file, specific result, testable.

[Pause]

Check your design document. Are your success criteria testable? If not, refine them this week."

[Transition: Click to Segment 2]

---

## SEGMENT 2: AGENT EXECUTION LOOP
### Duration: 8 minutes | Slides 8-11

---

## SLIDE 8: THE AGENT LOOP

**Title:** How Agents Actually Execute

**Content:**

```
START
  ↓
[Receive task/context]
  ↓
[Analyze situation] ←────────────┐
  ↓                              │
[Decide next action]             │
  ↓                              │
[Execute action using tool]      │
  ↓                              │
[Observe result]                 │
  ↓                              │
[Goal achieved?] ──No────────────┘
  ↓ Yes
[Generate final output]
  ↓
END
```

**Graphic:** Loop diagram with clear flow arrows

**SPEAKER NOTES:**

"This is the agent execution loop.

[Walk through]

Start with task and context. Analyze the situation. Decide what to do. Execute using a tool. Observe the result.

Then the key question: Is the goal achieved? If no, loop back. Analyze again with new information. Decide next action.

If yes, generate final output and end.

[Key point]

The agent decides when to stop. That's what makes it an agent, not a workflow."

[Transition]

---

## SLIDE 9: KEY IMPLEMENTATION CONCEPTS

**Title:** Making the Loop Work

**Content:**

| Concept | Purpose | Implementation |
|---------|---------|----------------|
| **Max iterations** | Prevent infinite loops | `if iteration > 50: stop()` |
| **State management** | Track between iterations | Update state object after each action |
| **Tool result parsing** | Extract useful info | Validate format, handle missing |
| **Completion detection** | Know when done | Check success criteria each iteration |

**Every Loop Needs Bounds**

**Graphic:** Loop with safety rails illustrated

**SPEAKER NOTES:**

"Four concepts make the loop work.

[Walk through table]

Max iterations - without this, agents can loop forever. Set a limit. 50, 100, whatever makes sense.

State management - track what's happened. Update after each action.

Tool result parsing - tools return data. Validate it, handle missing fields.

Completion detection - check success criteria each iteration. Know when you're done.

[Emphasize]

Every loop needs bounds. This is non-negotiable."

[Transition]

---

## SLIDE 10: THE LOOP IN PSEUDOCODE

**Title:** Implementation Pattern

**Content:**

```python
def run_agent(task, context):
    state = initialize_state(task, context)
    iteration = 0

    while iteration < MAX_ITERATIONS:
        # Analyze and decide
        action = agent.decide_action(state)

        # Check for completion
        if action.type == "COMPLETE":
            return state.final_output

        # Execute
        result = execute_tool(action)

        # Update state
        state = update_state(state, action, result)
        iteration += 1

    # Max iterations reached
    return partial_result_with_warning(state)
```

**Graphic:** Code block with annotations pointing to key sections

**SPEAKER NOTES:**

"Here's the pattern in code.

[Walk through]

Initialize state with task and context. Set iteration counter.

While loop with max iterations check. First thing in the loop - agent decides action.

Check if action is COMPLETE - if so, return final output.

Otherwise, execute the tool, update state, increment iteration.

If we exit the loop, max iterations reached. Return partial result with warning.

[Key point]

Notice the agent decides 'COMPLETE' - that's the completion detection. Your success criteria go there."

[Transition]

---

## SLIDE 11: WHEN TO STOP

**Title:** Stop Conditions

**Content:**

**Stop Successfully When:**
- Goal achieved (success criteria met)
- All tasks complete
- Quality threshold met

**Stop Gracefully When:**
- Maximum iterations reached
- Timeout exceeded
- Escalation triggered

**Stop Immediately When:**
- Unrecoverable error
- Safety constraint violated
- Circuit breaker tripped

**Graphic:** Traffic light visual - green (success), yellow (graceful), red (immediate)

**SPEAKER NOTES:**

"Agents need multiple stop conditions.

[Green - success]

Stop successfully when goal is achieved. Your success criteria from the design document.

[Yellow - graceful]

Stop gracefully when limits hit. Max iterations, timeout, escalation needed. Save progress, report status.

[Red - immediate]

Stop immediately on unrecoverable errors or safety violations. Circuit breaker catches these.

Your system prompt should specify all three types."

[Transition: Click to Segment 3]

---

## SEGMENT 3: ERROR HANDLING
### Duration: 13 minutes | Slides 12-18

---

## SLIDE 12: TYPES OF AGENT FAILURES

**Title:** What Can Go Wrong

**Content:**

| Type | Description | Examples |
|------|-------------|----------|
| **Tool Failures** | External system issues | API down, timeout, rate limit |
| **Reasoning Failures** | Agent logic issues | Confused, loops, wrong decisions |
| **Context Failures** | State issues | Lost goal, forgot state |
| **Quality Failures** | Output issues | Wrong answer, incomplete |

**All Four Types Will Happen**

**Graphic:** Four quadrant diagram with failure types

**SPEAKER NOTES:**

"[Hook - Reality check]"

"Four types of failures. All of them will happen.

[Walk through]

Tool failures - external things break. APIs go down. Rate limits hit. Timeouts happen.

Reasoning failures - the agent gets confused. It loops. It makes wrong decisions.

Context failures - the agent loses track. Forgets the goal. Loses state.

Quality failures - output is wrong. Incomplete. Poor format.

[Key point]

You can't prevent all failures. You can handle them systematically."

[Transition]

---

## SLIDE 13: ERROR HANDLING STRATEGY

**Title:** The Strategy: Try-Catch-Decide

**Content:**

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

**Three Options After Catching:**
1. **Retry** - Try again (with backoff)
2. **Fallback** - Use alternative approach
3. **Escalate** - Stop and get help

**Graphic:** Flow diagram showing try-catch-decide pattern

**SPEAKER NOTES:**

"The strategy is systematic.

[Walk through pattern]

Try to execute and validate. If tool error, log it, then decide: is it retryable? If yes, retry with backoff. If no, fallback or escalate.

[Point to three options]

After catching, you have three choices:

Retry - try again. But not immediately - use backoff to avoid hammering a failing service.

Fallback - alternative approach. If search fails, use cached data.

Escalate - stop and get human help. When you're truly stuck.

The key is deciding systematically, not randomly."

[Transition]

---

## SLIDE 14: THE CIRCUIT BREAKER PATTERN

**Title:** The Safety Net

**Content:**

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
            raise CircuitBreakerTripped("Error limit")
```

**Three Breaker Conditions:**
- Too many iterations
- Too much time
- Too many consecutive errors

**Graphic:** Electrical circuit breaker illustration

**SPEAKER NOTES:**

"The Circuit Breaker is your safety net.

[Walk through code]

Three conditions that trip the breaker:

Iteration limit - 100 is reasonable for most tasks. Adjust based on your use case.

Timeout - 30 minutes here. Prevents hung processes.

Consecutive errors - 3 in a row suggests the agent is stuck.

[Key insight]

Without a circuit breaker, agents can loop forever, drain your API budget, or produce garbage for hours. This is non-negotiable for production agents."

[Transition]

---

## SLIDE 15: THE 3-FAILURE RULE

**Title:** When to Escalate

**Content:**

**The Rule:**
> After 3 consecutive failures at the same task, escalate to human.

**Why 3?**
- LLMs CAN recover from errors
- 1 failure = might be a fluke
- 2 failures = concerning pattern
- 3 failures = agent is stuck
- More attempts won't help

**Implementation:**
```python
if consecutive_failures >= 3:
    escalate_to_human(context, last_error)
```

**Graphic:** Strike counter showing "Strike 1, Strike 2, Strike 3 - Escalate!"

**SPEAKER NOTES:**

"The 3-Failure Rule is simple but important.

[Explain rationale]

LLMs can recover from errors. They read error messages and adapt. One failure might be a fluke - network hiccup, temporary issue.

Two failures is a pattern. Worth noting.

Three failures? The agent is stuck. It's tried its best approaches. More attempts won't help - they'll just waste time and money.

[Key point]

Escalate rather than thrash. It's an Operating Procedure in your Domain Memory."

[Transition]

---

## SLIDE 16: RETRY WITH BACKOFF

**Title:** How to Retry Correctly

**Content:**

**Exponential Backoff:**
```
Attempt 1: Wait 1 second
Attempt 2: Wait 2 seconds
Attempt 3: Wait 4 seconds
(Then escalate)
```

**Why Backoff?**
- Immediate retry often fails again
- Services need time to recover
- Rate limits need cooldown
- Prevents hammering failing services

**Configuration Example:**
```json
{
  "retry_policy": {
    "max_attempts": 3,
    "initial_delay_seconds": 1,
    "backoff_multiplier": 2
  }
}
```

**Graphic:** Timeline showing increasing delays between retries

**SPEAKER NOTES:**

"When you retry, don't retry immediately.

[Explain backoff]

Exponential backoff: first retry after 1 second, second after 2, third after 4.

Why? Immediate retry often hits the same problem. Services need time to recover. Rate limits need cooldown.

[Key point]

Backoff is courtesy to the service and improves your success rate."

[Transition]

---

## SLIDE 17: MULTI-AGENT ERROR PROPAGATION

**Title:** When Sub-Agents Fail

**Content:**

**The Pattern:**
Sub-agents should return structured failure info, not crash.

**Failure Response Structure:**
```json
{
  "success": false,
  "partial_work": { ... },
  "error": "Timeout on step 3",
  "can_retry": true,
  "context": { ... }
}
```

**Parent Agent Decides:**
- Retry the sub-agent
- Work around the failure
- Escalate to human

**Graphic:** Parent agent receiving failure info from child agent

**SPEAKER NOTES:**

"When you have multiple agents, failures propagate.

[Explain pattern]

Sub-agents shouldn't crash on failure. They should return structured info: success flag, any partial work completed, the error, whether retry might help.

[Point to parent decisions]

The parent agent then decides: Retry? Work around? Escalate?

This keeps failures contained and recoverable. One sub-agent failing doesn't crash the whole system."

[Transition]

---

## SLIDE 18: ERROR HANDLING CHECKLIST

**Title:** Your Error Handling Checklist

**Content:**

**For Each Tool:**
- [ ] What errors can it throw?
- [ ] Which are retryable?
- [ ] What's the fallback?
- [ ] When to escalate?

**For the Agent:**
- [ ] Max iterations set?
- [ ] Timeout configured?
- [ ] Circuit breaker in place?
- [ ] 3-Failure Rule implemented?

**For Logging:**
- [ ] Errors logged with context?
- [ ] Retries counted?
- [ ] Escalations recorded?

**Graphic:** Checklist with checkboxes

**SPEAKER NOTES:**

"Use this checklist when implementing.

[Walk through sections]

For each tool - know its failure modes. Which are retryable, what's the fallback, when to escalate.

For the agent itself - bounds in place. Max iterations, timeout, circuit breaker.

For logging - can you debug failures? Errors with context, retry counts, escalation records.

Exercise 2.2 has you fill this out for your agent."

[Transition: Click to Segment 4]

---

## SEGMENT 4: LIVE DEMO
### Duration: 9 minutes | Slides 19-20

---

## SLIDE 19: LIVE DEMO SETUP

**Title:** Live Demo: Research Assistant Agent

**Content:**

**Agent Overview:**
- **Goal:** Answer questions using multiple sources
- **Tools:** Web search, file reader, note taker
- **Pattern:** Observe-Think-Act loop with error handling

**What to Watch For:**
- How agent decides which tool to use
- How the loop progresses
- What happens when something fails

**Graphic:** Demo setup diagram showing agent components

**SPEAKER NOTES:**

"Let me show you this in action.

I'm going to run a Research Assistant agent. Goal is answering questions using multiple sources.

[Point to tools]

Three tools: web search, file reader, note taker. All configured via MCP.

[Point to watch for]

Watch how the agent decides which tool to use first. Watch the loop progress. And I'll trigger an error so you can see recovery.

Let me share my screen..."

[Start demo]

---

## SLIDE 20: DEMO OBSERVATIONS

**Title:** What We Saw

**Content:**

**Key Observations:**
1. Agent chose tools based on task requirements
2. Loop continued until quality threshold met
3. Error was caught and handled (retry succeeded)
4. Final output included sources and reasoning

**Patterns in Action:**
- Observe-Think-Act loop
- Tool result validation
- Error retry with backoff
- Completion detection

**Graphic:** Summary of demo with screenshots or key moments

**SPEAKER NOTES:**

"[Post-demo discussion]"

"Let's recap what we saw.

[Walk through observations]

The agent chose web search first because the question needed current information. That's tool selection based on task.

It looped 4 times - search, analyze, search again for more detail, synthesize. Loop continued until quality was good enough.

When the first search timed out, the agent caught the error, waited, retried, and succeeded. That's error handling in action.

Final output included sources - the agent tracked where information came from.

Questions about what you saw?"

[Handle questions briefly]

[Transition: Click to Segment 5]

---

## SEGMENT 5: TESTING + CLOSING
### Duration: 4 minutes | Slides 21-24

---

## SLIDE 21: TESTING AGENT RELIABILITY

**Title:** Test Categories

**Content:**

| Category | What to Test | Example |
|----------|--------------|---------|
| **Happy Path** | Normal inputs, everything works | Standard query, all tools available |
| **Edge Cases** | Unusual but valid inputs | Very long query, special characters |
| **Error Cases** | Invalid inputs, tool failures | Missing file, API timeout |
| **Stress Cases** | Large inputs, many iterations | Complex multi-part query |

**Approach:**
Start with happy path → Systematically break things → Document all failures → Build handling for each

**Graphic:** Testing funnel from happy path to stress cases

**SPEAKER NOTES:**

"Your testing approach matters.

[Walk through categories]

Happy path first - normal inputs, everything working. Build confidence.

Edge cases - unusual inputs that should still work. Long queries, special characters.

Error cases - deliberately break things. Force tool failures. See what happens.

Stress cases - push the limits. Complex queries, many iterations.

[Key approach]

Start simple, systematically break things, document what fails, build handling."

[Transition]

---

## SLIDE 22: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| 2.1: Build Functional Agent | 40 min | Working agent + logs | Execution loop |
| 2.2: Implement Error Handling | 20 min | Error config + tests | Resilience |
| 2.3: Failure Mode Documentation | 15 min | `failure-modes.md` | Planning |
| **Total** | **75 min** | | |

**Target:** 5+ successful agent executions this week

**Graphic:** Exercise progression showing build → harden → document

**SPEAKER NOTES:**

"Your homework for this week.

[Walk through exercises]

Exercise 2.1 - build your functional agent. 40 minutes. Use your design document, implement the loop, test it.

Exercise 2.2 - implement error handling. 20 minutes. Add try/catch, circuit breaker, logging.

Exercise 2.3 - document failure modes. 15 minutes. What can go wrong, how do you handle it.

[Emphasize target]

Target is 5+ successful executions. Run your agent multiple times. Find the bugs. Fix them."

[Transition]

---

## SLIDE 23: RESOURCES

**Title:** Resources for This Week

**Content:**

**Templates & Files:**
- System prompt enhancement - Participant Guide
- Error handling configuration - Participant Guide
- Failure mode catalog - Participant Guide

**Reference Materials:**
- [Anthropic Agent Documentation](https://docs.anthropic.com/en/docs/agents)
- [Circuit Breaker Pattern](https://martinfowler.com/bliki/CircuitBreaker.html)

**Support:**
- Questions: Support channel
- If agent won't run: Post error + system prompt for help

**Graphic:** Resource icons with links

**SPEAKER NOTES:**

"Resources for this week.

All templates are in your participant guide. The failure mode catalog is especially useful for Exercise 2.3.

[Point to references]

Anthropic docs for agent patterns. Martin Fowler's article on Circuit Breaker if you want to go deep.

If your agent won't run, post in the support channel with the error AND your system prompt. Can't debug without seeing both."

[Transition]

---

## SLIDE 24: NEXT WEEK PREVIEW

**Title:** Next Week: MCP Deep Dive

**Content:**

**Preview:**
Week 3 covers advanced MCP architecture, multi-server configuration, tool chaining, and security best practices.

**What to Complete Before Then:**
- [ ] Exercise 2.1: Build Functional Agent
- [ ] Exercise 2.2: Implement Error Handling
- [ ] Exercise 2.3: Failure Mode Documentation
- [ ] Run agent 5+ times

**Key Preparation:**
Your agent must be functional before Week 3 - we'll be expanding its capabilities.

**Graphic:** Preview showing MCP multi-server diagram

**SPEAKER NOTES:**

"Next week is MCP Deep Dive.

We'll cover advanced MCP architecture, connecting multiple servers, chaining tools together. Security best practices for production.

[Point to requirements]

Your agent needs to be functional before then. We're going to expand its capabilities, which means it needs to work first.

[Final close]

Great session today. You now understand what makes agents reliable - Domain Memory, the execution loop, error handling.

The homework is where learning happens. Build your agent, break it, fix it. 5+ executions minimum.

Questions before we wrap?

[Handle questions]

See you next week!"

---

## Appendix: Slide Design Notes

### Block 3 Color Scheme

| Element | Color | Hex Code |
|---------|-------|----------|
| Primary | Green | #00CC99 |
| Accent | Teal | #008B8B |
| Background | White | #FFFFFF |
| Text | Dark Gray | #333333 |

### Graphic Suggestions by Slide

| Slide | Graphic Type | Description |
|-------|-------------|-------------|
| 1 | Title | Green theme, construction visual |
| 5 | Architecture | Three pillars supporting structure |
| 8 | Loop | Clear flow diagram with arrows |
| 12 | Quadrant | Four failure types |
| 14 | Illustration | Electrical circuit breaker |
| 15 | Counter | Strike 1, 2, 3 visual |
| 21 | Funnel | Testing categories |

### Animation Notes

- Code blocks: Reveal line by line for complex examples
- Tables: Build row by row
- Loop diagrams: Animate the flow
- Avoid: Excessive animation that distracts from technical content

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
