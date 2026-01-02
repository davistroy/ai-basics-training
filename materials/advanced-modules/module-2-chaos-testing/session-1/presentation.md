# **POWERPOINT PRESENTATION: ADVANCED MODULE 2 SESSION 1**
## **Chaos Engineering Fundamentals**

**Module:** Advanced Module 2: Chaos Testing & Reliability Engineering
**Session Number:** 1 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 graduates with production-ready agent systems deployed

**Session Learning Objectives:** By the end of this session, participants will:
1. Understand chaos engineering principles and the experiment cycle
2. Identify and categorize AI agent failure modes
3. Design structured chaos experiments with clear hypotheses
4. Set up safe testing environments with proper safeguards

**Entry Criteria:**
- [ ] Working agent system from Block 3
- [ ] Monitoring dashboard operational
- [ ] Error handling in place (basic)
- [ ] Ability to observe system behavior in real-time

**Exit Criteria:**
- [ ] Chaos engineering principles understood
- [ ] Failure mode catalog created
- [ ] First chaos experiments designed
- [ ] Safe testing environment established
- [ ] 5+ chaos experiments executed

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Introduction to Chaos Engineering (12 min) - Slides 4-7
3. Segment 2: AI Agent Failure Modes (12 min) - Slides 8-11
4. Segment 3: Designing Chaos Experiments (12 min) - Slides 12-15
5. Segment 4: Safe Testing Environment (9 min) - Slides 16-18
6. Homework Preview & Close (3 min) - Slides 19-21

**Total Slides:** 21

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Advanced Module 2 Session 1: Chaos Engineering Fundamentals

**Subtitle:** Breaking Your AI Agents Before Production Does

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program - Advanced Module 2

**Graphic:** Title slide with green tones (advanced module color). Include visual of controlled chaos/testing icon.

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Advanced Module 2: Chaos Testing & Reliability Engineering. Today we're starting with Session 1, focusing on chaos engineering fundamentals.

This is a post-Block 3 module, so you've already built sophisticated agent systems. Now we're going to learn how to make them bulletproof by intentionally breaking them in controlled ways.

The philosophy is simple: break it in testing so it doesn't break in production.

Today we'll learn how to systematically test your agent's resilience through chaos engineering."

[Transition: Click to next slide]

---

### SLIDE 2: WEEK OVERVIEW

**Title:** This Session's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Recap & Preview |
| 3-15 min | Segment 1 | Introduction to Chaos Engineering |
| 15-27 min | Segment 2 | AI Agent Failure Modes |
| 27-39 min | Segment 3 | Designing Chaos Experiments |
| 39-42 min | Segment 4 | Safe Testing Environment |
| 42-45 min | Close | Homework & Preview |

**Graphic:** Simple timeline showing the session flow with chaos engineering cycle visual

**SPEAKER NOTES:**

"Here's what we'll cover today:

First, we'll introduce chaos engineering - what it is, why it matters for AI agents, and the basic experiment cycle.

Then, we'll explore the unique failure modes of AI agent systems - everything from tool failures to orchestration issues.

In our third segment, we'll learn how to design rigorous chaos experiments with clear hypotheses and success criteria.

And we'll close with how to set up a safe testing environment so you can break things without consequences.

[Pause]

Any questions before we dive in?"

[Transition]

---

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Understand chaos engineering principles**
   - Learn the discipline of experimenting on systems to build confidence

2. **Identify and categorize AI agent failure modes**
   - Catalog tool, AI, orchestration, resource, and external failures

3. **Design structured chaos experiments**
   - Create hypothesis-driven tests with clear success criteria

4. **Set up safe testing environments**
   - Implement safeguards, monitoring, and kill switches

**Graphic:** Checklist visual with chaos engineering icons

**SPEAKER NOTES:**

"These are our four objectives for today. By the time you leave this session, you'll be able to:

[Read each objective, pausing briefly after each]

Notice that these are all ACTION-focused. This isn't about theory - it's about systematically testing your agent systems.

[Point to first objective]

This one is crucial: chaos engineering is a discipline with specific principles and practices. It's not just randomly breaking things.

Let's get started."

[Transition: Click to Segment 1]

---

## SEGMENT 1: Introduction to Chaos Engineering
### Duration: 12 minutes | Slides 4-7

---

### SLIDE 4: SEGMENT 1 - PROBLEM/HOOK

**Title:** What Happens When Your Agent Hits Production?

**Content:**

**The Challenge:**
Your agent works perfectly in testing. Then it hits production and:
- External API goes down
- MCP server becomes unavailable
- Network latency spikes
- Token limits hit unexpectedly

**Why It Matters:**
- Production failures damage client trust
- Manual intervention is expensive and slow
- Hidden failure modes emerge under real conditions
- Agents must handle failures gracefully

**Graphic:** Before/after comparison - agent working smoothly vs. agent failing in production with error cascades

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Let me ask you a question: How confident are you that your agent system will handle every failure scenario in production?

[Pause - let question land]

Here's what typically happens: You test your agent. It works great. You deploy to production. Then the filesystem MCP server goes down, and your agent crashes instead of handling it gracefully.

Or an API you depend on starts rate-limiting you, and your agent enters an infinite retry loop.

The reality is that AI agents have complex dependencies. And in production, things fail. APIs go down. Networks timeout. Services get rate-limited.

[Point to graphic]

The difference between the left and right side of this diagram is chaos engineering.

Today we're going to solve this. Here's how..."

[Transition]

**BACKGROUND:**

**Rationale:**
- Establishes real production pain points
- Creates urgency for systematic testing
- Connects to their Block 3 experience with agents
- Sets up chaos engineering as the solution

**Q&A Preparation:**
- *"Isn't this just normal testing?"*: No - chaos engineering specifically injects failures to test resilience, not just functionality
- *"Can't we just handle errors?"*: Yes, but chaos engineering helps you find the error cases you didn't think of

---

### SLIDE 5: SEGMENT 1 - SOLUTION INTRODUCTION

**Title:** The Solution: Chaos Engineering

**Content:**

**Core Principle:** Deliberately inject failures in controlled environments to build confidence in system resilience

**How It Works:**
1. Define steady state (what "working" looks like)
2. Hypothesize what will happen during failure
3. Inject failure in controlled way
4. Observe actual behavior
5. Fix weaknesses found
6. Repeat

**Key Benefit:** Find and fix failure modes before production does

**Graphic:** Chaos engineering cycle diagram showing the 6 steps as a continuous loop

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"The solution is chaos engineering.

Chaos engineering is a discipline of experimenting on a system to build confidence in its capability to withstand turbulent conditions.

The idea: break it in testing so it doesn't break in production.

Let me break down how this works:

First, you define steady state - what does 'working' look like? Success rate above 95%? Response time under 30 seconds?

Then you hypothesize what will happen when something fails. 'When the MCP server is unavailable, the agent will retry 3 times and fail gracefully.'

Next, you inject that failure in a controlled environment. You actually make the MCP server unavailable.

You observe what really happens. Does it match your hypothesis?

You fix any weaknesses you found. Maybe it didn't retry, or it crashed.

Then you repeat with the next failure scenario.

[Point to graphic]

Notice how this is a continuous cycle. You're constantly finding and fixing weaknesses.

The key insight here is that chaos engineering is proactive. You're not waiting for production to find your bugs.

Let me show you this in action..."

[Transition to demo or example]

**BACKGROUND:**

**Key Research & Citations:**
- **Netflix Chaos Monkey**: Pioneered chaos engineering at scale
- **Principles of Chaos Engineering**: chaos.org

**Implementation Guidance:**

**Getting Started:**
- Start with one failure scenario
- Use non-production environment first

**Common Pitfalls:**
- Testing in production without safeguards
- Not having clear hypotheses
- Forgetting to document findings

---

### SLIDE 6: SEGMENT 1 - WHY FOR AI AGENTS?

**Title:** AI Agents Have Unique Failure Modes

**Content:**

**AI-Specific Challenges:**
- **Non-deterministic outputs** - Same input ≠ same output
- **Complex dependencies** - MCP servers, APIs, external tools
- **Token/context limits** - Resource constraints mid-execution
- **Orchestration complexity** - Multi-agent handoffs and state

**Traditional Systems vs AI Agents:**

| Traditional | AI Agents |
|-------------|-----------|
| Predictable failures | Non-deterministic failures |
| Single responsibility | Complex orchestration |
| Clear error states | Ambiguous partial states |
| Stateless or simple state | Rich contextual state |

**Graphic:** Diagram showing AI agent dependencies: AI API, MCP servers, tools, orchestration layer, external services

**SPEAKER NOTES:**

"Why do we need chaos engineering specifically for AI agents?

AI agents have unique failure characteristics that traditional systems don't have.

First, non-determinism. The same prompt can give different responses. This makes testing harder because you can't just replay scenarios.

Second, complex dependencies. Your agent might depend on Claude's API, multiple MCP servers, GitHub, search APIs, and custom tools. Each is a potential failure point.

Third, resource constraints. Token limits, context windows, cost budgets - these can be exceeded mid-execution in ways that are hard to predict.

Fourth, orchestration complexity. If you have multi-agent systems, handoffs can fail. State can corrupt. Deadlocks can occur.

[Point to comparison table]

Traditional systems fail predictably. AI agents can fail in subtle, partial ways. An agent might partially complete a task, or hallucinate instead of failing cleanly.

This is why chaos engineering is essential for production AI agents."

[Transition]

---

### SLIDE 7: SEGMENT 1 - KEY TAKEAWAY

**Title:** Segment 1 Summary

**Content:**

**Key Takeaway:** Chaos engineering finds failure modes before production does by systematically injecting failures in controlled environments

**Remember:**
- Define steady state first
- Have clear hypotheses
- Start small and controlled
- Document everything

**You'll Practice:**
Exercise 1.1: Create failure mode catalog
Exercise 1.2: Design chaos experiments
Exercise 1.3: Execute first tests

**Graphic:** Simple visual showing controlled chaos → findings → fixes → confidence

**SPEAKER NOTES:**

"Before we move on, let me summarize the key points:

Chaos engineering is about proactively finding weaknesses. You systematically inject failures, observe what happens, and fix what breaks.

Remember: Always define steady state first. You need to know what 'working' looks like before you can test breaking.

Have clear hypotheses. 'I think X will happen when Y fails.' Then test it.

Start small. Don't inject ten failures at once. One at a time, controlled.

And document everything. Your findings become your roadmap for hardening.

In your homework this week, you'll create a complete failure catalog for your system, design chaos experiments, and execute your first tests.

[Pause]

Any final questions on chaos engineering basics before we move to failure modes?"

[Transition: Click to Segment 2]

---

## SEGMENT 2: AI Agent Failure Modes
### Duration: 12 minutes | Slides 8-11

---

### SLIDE 8: SEGMENT 2 - FAILURE CATEGORIES

**Title:** Five Categories of AI Agent Failures

**Content:**

| Category | Examples |
|----------|----------|
| **Tool Failures** | API down, timeout, rate limited, wrong response |
| **AI Failures** | Hallucination, context lost, infinite loop, wrong tool choice |
| **Orchestration Failures** | Agent handoff fails, state corruption, deadlock |
| **Resource Failures** | Token limit, memory, cost budget exceeded |
| **External Failures** | Network, authentication, third-party service down |

**Key Point:** Each category requires different detection and handling strategies

**Graphic:** Visual taxonomy showing the five categories with icons

**SPEAKER NOTES:**

"Now let's dive into the specific ways AI agents fail.

I've organized failures into five categories. Let me walk through each:

Tool failures: Your agent calls a tool - a filesystem MCP server, GitHub API, search - and it's down, times out, or rate limits you. Or worse, returns malformed data.

AI failures: The LLM itself has issues. It hallucinates. It loses context. It enters an infinite loop, calling the same tool repeatedly. Or it chooses the wrong tool entirely.

Orchestration failures: In multi-agent systems, handoffs fail. State gets corrupted. Agents deadlock waiting for each other.

Resource failures: You hit token limits mid-execution. Memory runs out. Your cost budget is exceeded.

External failures: Network issues. Authentication expires. A third-party service you depend on goes down.

[Point to table]

The key insight is that each category needs different handling. You can retry tool failures. But you can't retry a hallucination - you need different prompting."

[Transition]

---

### SLIDE 9: SEGMENT 2 - FAILURE MODE ANALYSIS

**Title:** Analyzing Each Failure Mode

**Content:**

**Failure Mode Template:**
```markdown
## Failure Mode: [Name]

- What: [Description]
- Likelihood: [Common/Occasional/Rare]
- Impact: [Critical/High/Medium/Low]
- Detection: [How to detect]
- Current handling: [What happens now]
- Desired handling: [What should happen]
```

**Example:**
```markdown
## Failure Mode: MCP Server Unavailable

- What: Filesystem MCP server not responding
- Likelihood: Occasional
- Impact: High - agent cannot access files
- Detection: Connection timeout
- Current handling: Agent crashes
- Desired handling: Retry 3x, then fail gracefully
```

**Graphic:** Template structure with arrows showing the analysis flow

**SPEAKER NOTES:**

"For each failure mode, we analyze it systematically using this template.

First, What: Describe exactly what fails and how.

Likelihood: Is this common, occasional, or rare? This helps you prioritize.

Impact: If it happens, how bad is it? Critical means system down. High means major functionality lost. Medium and Low are degraded but functional.

Detection: How do you know it happened? What's the signal?

Current handling: Be honest - what happens now? Maybe it crashes. Maybe it silently fails.

Desired handling: What should happen? Retry? Failover? Graceful degradation?

[Point to example]

Here's a real example: MCP server unavailable. It's occasional - happens during updates or network issues. Impact is high because without file access, many agents can't function.

We detect it via connection timeout. Currently, most agents crash. But we want retry with backoff, then graceful failure with clear messaging.

This analysis becomes your chaos testing roadmap."

[Transition]

---

### SLIDE 10: SEGMENT 2 - PRIORITY MATRIX

**Title:** Prioritizing What to Test

**Content:**

**Priority Formula:**
Priority = Likelihood × Impact

**Failure Priority Matrix:**

| ID | Failure | Likelihood | Impact | Priority |
|----|---------|------------|--------|----------|
| TF-001 | MCP unavailable | Medium | High | **1** |
| AF-002 | Infinite loop | Low | Critical | **2** |
| EF-001 | Network timeout | High | Medium | **3** |
| RF-001 | Token limit | Medium | Medium | **4** |

**Test high-priority items first**

**Graphic:** 2x2 matrix showing likelihood vs impact quadrants with failures plotted

**SPEAKER NOTES:**

"You can't test everything at once. So how do you prioritize?

Simple formula: Priority equals likelihood times impact.

High likelihood and high impact? Test first.

Low likelihood but critical impact? Also test early - these are your rare but catastrophic failures.

[Point to table]

Here's an example priority list:

MCP unavailable: Medium likelihood, high impact. This is priority 1.

Infinite loop: Low likelihood, but critical impact. Priority 2.

Network timeout: High likelihood but medium impact. Priority 3.

Token limit: Medium and medium. Priority 4.

Notice that we're not ignoring low-likelihood failures if they're critical. A rare infinite loop can drain your entire budget.

Start with your top 5 priority failures. Those become your first chaos experiments."

[Transition]

---

### SLIDE 11: SEGMENT 2 - KEY TAKEAWAY

**Title:** Segment 2 Summary

**Content:**

**Key Takeaway:** Systematically catalog all failure modes, analyze each one, and prioritize testing based on likelihood × impact

**Remember:**
- Five categories: Tool, AI, Orchestration, Resource, External
- Each failure needs: description, likelihood, impact, detection, handling
- Test high-priority failures first
- Document everything in your catalog

**You'll Practice:**
Exercise 1.1 guides you through creating a complete failure mode catalog for your agent system

**Graphic:** Catalog → Analysis → Priority → Testing workflow

**SPEAKER NOTES:**

"Let me summarize this segment:

First, categorize your failures: Tool, AI, Orchestration, Resource, External.

Second, analyze each one systematically. What is it? How likely? How bad? How to detect? How to handle?

Third, prioritize by likelihood times impact. Test the worst ones first.

And document it all. Your failure mode catalog is a living document.

In Exercise 1.1, you'll create a complete catalog for your specific agent system. This becomes your chaos testing roadmap.

[Pause]

Questions on failure modes before we move to experiment design?"

[Transition: Click to Segment 3]

---

## SEGMENT 3: Designing Chaos Experiments
### Duration: 12 minutes | Slides 12-15

---

### SLIDE 12: SEGMENT 3 - EXPERIMENT STRUCTURE

**Title:** Anatomy of a Chaos Experiment

**Content:**

**Required Elements:**
1. **Hypothesis** - What you expect to happen
2. **Steady State** - Metrics defining "working"
3. **Failure Injection** - How to cause the failure
4. **Observation Plan** - What to monitor
5. **Rollback Plan** - How to stop and recover
6. **Success Criteria** - What validates the hypothesis

**Graphic:** Experiment template structure with all six elements connected

**SPEAKER NOTES:**

"Now let's learn how to design rigorous chaos experiments.

Every experiment needs six elements:

First, a hypothesis. 'When the MCP server fails, the agent will retry 3 times and fail gracefully.' Be specific.

Second, steady state definition. Define what 'working' looks like in metrics. Success rate above 95%. Response time under 30 seconds.

Third, failure injection method. How exactly will you cause this failure? Disable the MCP server? Block the port? Return errors?

Fourth, observation plan. What will you watch? Logs? Metrics dashboard? Specific error messages?

Fifth, rollback plan. How do you stop the experiment and recover? This is critical for safety.

Sixth, success criteria. How do you know if your hypothesis was right? Checklist of expected behaviors.

All six elements are required. Missing any one, and your experiment isn't rigorous."

[Transition]

---

### SLIDE 13: SEGMENT 3 - EXAMPLE EXPERIMENT

**Title:** Example: MCP Server Failure Test

**Content:**

```markdown
## Hypothesis
When filesystem MCP server fails, agent will:
- Detect within 10s
- Retry 3x with backoff
- Fail gracefully with clear message
- Not corrupt state

## Steady State
- Success rate: 100%
- Response time: <10s

## Injection
- Rename MCP config file
- Duration: 60 seconds

## Observe
- Agent logs
- Error messages
- Dashboard metrics

## Rollback
1. Restore config
2. Restart Claude Desktop
3. Verify recovery

## Success Criteria
- [x] Detects failure
- [x] Attempts retries
- [x] Fails gracefully
- [x] State intact
```

**Graphic:** Experiment workflow from hypothesis to validation

**SPEAKER NOTES:**

"Here's a complete example experiment.

Hypothesis: When the MCP server fails, the agent will detect it within 10 seconds, retry 3 times with backoff, fail gracefully, and not corrupt state.

Steady state: Normally, success is 100% and response time is under 10 seconds.

Injection method: We'll rename the MCP config file to make the server unavailable. Duration: 60 seconds.

Observation: We'll watch the agent logs, error messages, and dashboard metrics in real-time.

Rollback: To stop, we restore the config, restart Claude Desktop, and verify recovery.

Success criteria: Four checkboxes. Did it detect? Did it retry? Did it fail gracefully? Is state intact?

[Point to template]

This structure ensures rigorous, repeatable testing. You can hand this experiment to another engineer and they can reproduce it exactly.

In your homework, you'll design 5 experiments like this."

[Transition]

---

### SLIDE 14: SEGMENT 3 - INJECTION METHODS

**Title:** Ways to Inject Failures

**Content:**

**Common Injection Techniques:**

| Method | Use Case | Example |
|--------|----------|---------|
| **Disable service** | Test unavailability | Rename MCP config |
| **Return errors** | Test error handling | Mock API returning 500 |
| **Add latency** | Test timeout handling | Network delay injection |
| **Malformed data** | Test validation | Return invalid JSON |
| **Resource limits** | Test constraints | Set low token budget |
| **Kill process** | Test recovery | Terminate agent mid-execution |

**Safety:** Always have rollback ready before injection

**Graphic:** Visual showing different injection techniques with safety warnings

**SPEAKER NOTES:**

"How do you actually inject failures? Here are six common methods:

Disable service: Make something unavailable. Rename a config file. Stop a server. Block a port.

Return errors: Use mocks or proxies to return error codes. 500 server error. 429 rate limit. 401 auth failure.

Add latency: Inject network delays to test timeout handling. Does your agent wait forever or fail gracefully?

Malformed data: Return invalid responses. Corrupted JSON. Missing required fields. Wrong data types.

Resource limits: Constrain resources. Set a tiny token budget. Limit memory. Restrict API calls.

Kill process: Terminate the agent mid-execution. Does it recover? Corrupt state? Leave partial work?

[Point to safety note]

Critical: Always have your rollback plan ready BEFORE you inject. Know how to stop and recover.

Start with the safest methods - config changes - before you move to process killing."

[Transition]

---

### SLIDE 15: SEGMENT 3 - KEY TAKEAWAY

**Title:** Segment 3 Summary

**Content:**

**Key Takeaway:** Well-designed chaos experiments have clear hypotheses, defined steady state, specific injection methods, observation plans, rollback procedures, and success criteria

**Remember:**
- All six elements are required
- Be specific in your hypothesis
- Define success criteria as checkboxes
- Have rollback ready before injecting
- Document expected vs actual results

**You'll Practice:**
Exercise 1.2: Design 5 complete chaos experiments with all elements

**Graphic:** Experiment checklist visual

**SPEAKER NOTES:**

"Let me summarize experiment design:

Six required elements: hypothesis, steady state, injection, observation, rollback, success criteria.

Be specific. 'Test MCP failure' is not a hypothesis. 'Agent will retry 3 times with exponential backoff' is.

Define success as checkboxes you can verify. Did it detect? Did it retry? Did it recover?

Always have rollback ready. Never inject a failure you can't stop.

And document everything. Expected vs actual results. What worked, what didn't.

In Exercise 1.2, you'll design 5 complete experiments. These become your chaos test suite.

Questions on experiment design?"

[Transition: Click to Segment 4]

---

## SEGMENT 4: Safe Testing Environment
### Duration: 9 minutes | Slides 16-18

---

### SLIDE 16: SEGMENT 4 - SAFE ENVIRONMENT

**Title:** Setting Up Safe Chaos Testing

**Content:**

**Environment Requirements:**
- **Isolated** - Separate from production
- **Monitored** - Full observability
- **Labeled** - Clear "CHAOS TEST" marking
- **Test data only** - No real customer data
- **Rollback ready** - Can stop instantly

**Setup Checklist:**
- [ ] Clone production configuration
- [ ] Use test/staging environment
- [ ] Enable all monitoring
- [ ] Prepare rollback procedures
- [ ] Notify team of testing

**Graphic:** Safe testing environment diagram showing isolation, monitoring, kill switch

**SPEAKER NOTES:**

"Before you start breaking things, you need a safe environment.

Five requirements:

Isolated: Completely separate from production. No shared resources. No risk to real users.

Monitored: Full observability. Real-time logs streaming. Metrics dashboard visible. Alerts active.

Labeled: Clear marking that this is chaos testing. 'CHAOS_TEST=true' environment variable. Obvious labeling in logs.

Test data only: Never use real customer data. Mock data. Synthetic data. No PII.

Rollback ready: You can stop the experiment instantly and restore normal operation.

[Point to checklist]

Before your first experiment, complete this checklist. Clone your production setup to test environment. Enable all monitoring. Prepare your rollback procedures. And notify your team so they're not surprised by alerts.

Never chaos test in production without extensive safeguards. Start in test environments first."

[Transition]

---

### SLIDE 17: SEGMENT 4 - OBSERVABILITY & KILL SWITCH

**Title:** Monitoring and Safety Controls

**Content:**

**Observability Requirements:**
- Real-time log streaming (visible during test)
- Metrics dashboard (success rate, latency, errors)
- Alert notifications (active and monitored)
- Recording of all events (for post-analysis)

**Kill Switch Implementation:**
```
IF chaos_test_running AND
   (error_rate > 50% OR
    system_unresponsive OR
    user_triggered):
  STOP chaos injection
  RESTORE normal operation
  ALERT operator
```

**Graphic:** Dashboard mockup showing logs, metrics, and kill switch button

**SPEAKER NOTES:**

"Two critical safety mechanisms: observability and kill switch.

Observability: You must be able to see what's happening in real-time.

Logs streaming live. Not querying logs after - watching them as they flow.

Metrics dashboard visible. Success rate. Latency. Error counts. Updating in real-time.

Alerts active. If something goes really wrong, you get notified.

Recording everything. You'll analyze the full trace after.

[Point to kill switch code]

Kill switch: Automatic and manual stop capability.

If error rate exceeds 50%, stop automatically.

If system becomes unresponsive, stop automatically.

And you can trigger it manually anytime.

When triggered: stop injection immediately, restore normal operation, alert the operator.

Think of it like a circuit breaker for chaos testing.

Never run chaos tests without both full observability and a kill switch."

[Transition]

---

### SLIDE 18: SEGMENT 4 - KEY TAKEAWAY

**Title:** Segment 4 Summary

**Content:**

**Key Takeaway:** Safe chaos testing requires isolated environments, full observability, clear labeling, and kill switch capabilities

**Remember:**
- Never test in production without safeguards
- Start in test/staging environments
- Monitor in real-time, not after
- Have rollback ready before injection
- Document all safety procedures

**You'll Practice:**
Exercise 1.3: Set up safe environment and execute first chaos tests with full monitoring

**Graphic:** Safety checklist with all elements checked

**SPEAKER NOTES:**

"Final summary on safety:

Safe chaos testing is not optional. It's required.

Isolated environment. Full monitoring. Clear labeling. Kill switch ready.

Never test in production until you've validated in test environments first.

Monitor in real-time. Watching logs stream is not optional - it's how you catch problems.

Have your rollback procedure documented and tested before you inject any failures.

In Exercise 1.3, you'll set up your safe environment and execute your first chaos tests. You'll practice the full cycle with proper safeguards.

[Pause]

Questions on safe testing?"

[Transition: Click to Closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 19-21

---

### SLIDE 19: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 1.1: Failure Mode Catalog | 25 min | `failure-mode-catalog.md` | Systematic failure analysis |
| Exercise 1.2: Design Chaos Experiments | 25 min | `chaos-experiment-suite.md` | Experiment design |
| Exercise 1.3: Execute First Chaos Tests | 25 min | Test results documentation | Hands-on chaos testing |
| **Total** | **75 min** | | |

**Graphic:** Exercise workflow showing progression from catalog → design → execution

**SPEAKER NOTES:**

"Here's your homework for this week. You have 75 minutes of exercises to complete before our next session.

Exercise 1.1 takes about 25 minutes. You'll create a complete failure mode catalog for your agent system. Document every way it can fail, categorize them, and prioritize.

Exercise 1.2 is also 25 minutes. You'll design 5 complete chaos experiments with hypotheses, injection methods, observation plans, and success criteria.

Exercise 1.3 is the hands-on part - 25 minutes. You'll actually execute at least 3 of your chaos experiments and document the results.

These exercises build on each other, so complete them in order.

All the detailed instructions are in your participant guide, along with templates."

[Transition]

---

### SLIDE 20: RESOURCES

**Title:** Resources for This Session

**Content:**

**Templates & Files:**
- Failure Mode Analysis Template - Appendix A
- Chaos Experiment Template - Session 1 materials
- Test Results Template - Session 1 materials

**Reference Materials:**
- Principles of Chaos Engineering - chaos.org
- Chaos Testing Safety Checklist - Appendix A

**Support:**
- Questions: [Async channel name]
- Office Hours: [Time/location if applicable]

**Graphic:** Resource icons with links

**SPEAKER NOTES:**

"You have several resources to support your homework:

Templates for failure mode analysis, chaos experiments, and test results documentation. All included in your materials.

Reference materials including the official Principles of Chaos Engineering from chaos.org.

Safety checklist in Appendix A - use this before your first experiment.

If you get stuck, post in [async channel]. I monitor it and you'll usually get a response within [timeframe].

[If office hours exist]: We also have office hours [time] if you want live support."

[Transition]

---

### SLIDE 21: NEXT SESSION PREVIEW

**Title:** Next Session: Advanced Reliability Patterns

**Content:**

**Preview:**
We'll implement circuit breakers, bulkhead isolation, and self-healing mechanisms to make your agents production-grade

**What to Complete Before Then:**
- [ ] Exercise 1.1: Failure mode catalog
- [ ] Exercise 1.2: Chaos experiment designs
- [ ] Exercise 1.3: First chaos test results

**Key Preparation:**
Bring your chaos test findings - we'll use them to implement reliability patterns

**Graphic:** Preview showing circuit breaker and self-healing patterns

**SPEAKER NOTES:**

"Next session we'll cover advanced reliability patterns. We'll implement circuit breakers, bulkhead isolation, and self-healing mechanisms.

This builds directly on what you're practicing this week. Your chaos test findings will tell you where to add circuit breakers and what to make self-healing.

Make sure you've completed all three exercises before next session - especially Exercise 1.3. We'll be building on those test results.

[Final close]

Great session today. Remember: the goal is to find weaknesses before production does. The more failures you find in testing, the more reliable your system will be.

See you next session!"

---

## Appendix: Presentation Notes

### Timing Checkpoints
- End Segment 1: 15 min
- End Segment 2: 27 min
- End Segment 3: 39 min
- Start Closing: 42 min

### If Running Behind
- Shorten Slide 9 (failure mode analysis) - reference template, don't walk through
- Reduce live Q&A, direct to async channel
- Skip detailed injection method examples on Slide 14

### If Running Ahead
- Add more examples on Slide 13 (experiment design)
- Deeper Q&A on prioritization
- Show live dashboard/monitoring setup

### Key Messages to Repeat
1. "Break it in testing so it doesn't break in production"
2. "All six experiment elements are required"
3. "Safety is not optional - always have rollback ready"
