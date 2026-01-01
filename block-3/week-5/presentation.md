# **POWERPOINT PRESENTATION: BLOCK 3 WEEK 5**
## **Agent Specialization & Orchestration**

**Block:** 3: AI Automation Architecture
**Week Number:** 5
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 participants with multi-step agents from Week 4

**Week Learning Objectives:** By the end of this session, participants will:
1. Apply the specialization principle to decompose agents into focused roles
2. Implement sequential orchestration for pipeline workflows
3. Implement master-worker orchestration for decomposable tasks
4. Choose the appropriate pattern for their capstone

**Entry Criteria:**
- [ ] Multi-step agent working (Week 4)
- [ ] State management implemented
- [ ] Checkpoint system functional
- [ ] 15+ successful agent executions

**Exit Criteria:**
- [ ] Understand specialization benefits
- [ ] Describe sequential orchestration pattern
- [ ] Describe master-worker pattern
- [ ] Choose pattern for capstone

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: The Specialization Principle (10 min) - Slides 4-8
3. Segment 2: Sequential Orchestration (12 min) - Slides 9-13
4. Segment 3: Master-Worker Pattern (12 min) - Slides 14-19
5. Segment 4: Other Patterns + Close (8 min) - Slides 20-25

**Total Slides:** 25

---

## SLIDE 1: TITLE SLIDE

**Title:** Block 3 Week 5: Agent Specialization & Orchestration

**Subtitle:** From One Agent to Many - Coordinated Intelligence

**Content:**
- AI Practitioner Training Program
- Block 3: AI Automation Architecture

**Graphic:** Clean title slide with green theme. Visual of multiple connected agents.

**SPEAKER NOTES:**

"Welcome to Week 5: Agent Specialization & Orchestration.

You've built sophisticated single agents with state management and checkpoints. Today we're going bigger - coordinating multiple specialized agents that work together.

Quick check: How many of you found your Week 4 agent doing too many different things? Getting confused about what it should focus on?

[Wait for responses]

That's exactly what we're solving today. By the end, you'll understand how to break complex work into specialized roles and orchestrate them effectively."

[Transition]

---

## SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Week 4 Recap |
| 3-13 min | Segment 1 | Specialization Principle |
| 13-25 min | Segment 2 | Sequential Orchestration |
| 25-37 min | Segment 3 | Master-Worker Pattern |
| 37-45 min | Segment 4 | Other Patterns + Close |

**Graphic:** Timeline with green accents

**SPEAKER NOTES:**

"Here's our roadmap:

First, the specialization principle - why one agent should do one thing well.

Then two orchestration patterns. Sequential - for pipeline workflows. Master-Worker - for decomposable tasks.

We'll close with a brief look at other patterns and planning for your capstone."

[Transition]

---

## SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Apply the specialization principle**
   - One agent = One thing done well

2. **Implement sequential orchestration**
   - Agent A → Agent B → Agent C

3. **Implement master-worker orchestration**
   - Master decomposes, Workers execute, Master aggregates

4. **Choose your capstone pattern**
   - Match pattern to task characteristics

**Graphic:** Checklist with green checkboxes

**SPEAKER NOTES:**

"Four objectives.

[Read each]

By the end, you'll have a multi-agent architecture designed for your capstone.

Let's start with why we specialize in the first place."

[Transition: Click to Segment 1]

---

## SEGMENT 1: THE SPECIALIZATION PRINCIPLE
### Duration: 10 minutes | Slides 4-8

---

## SLIDE 4: THE CORE PRINCIPLE

**Title:** One Agent = One Thing Done Well

**Content:**

**Why Specialization Matters:**
- Focused prompts produce better results
- Easier to test and debug
- Simpler error handling
- Reusable components
- Prevents "bloated agent syndrome"

**The More An Agent Does, The Worse It Does Each Thing**

**Graphic:** Quality vs. Scope graph showing decline

**SPEAKER NOTES:**

"[Hook - The principle]"

"Here's the core principle: One agent, one thing done well.

[Walk through benefits]

Focused prompts produce better results - less confusion. Easier to test - you know what to expect. Simpler error handling - failures are isolated. Reusable - you can use that agent elsewhere.

[Key insight]

The more an agent does, the worse it does each thing. Scope and quality are inversely related."

[Transition]

---

## SLIDE 5: SIGNS OF A BLOATED AGENT

**Title:** Is Your Agent Bloated?

**Content:**

**Warning Signs:**
- System prompt > 2000 words
- Agent gets confused about its role
- Too many tools to choose from
- Inconsistent output quality
- Hard to debug failures

**The Test:**
> "Can you describe what this agent does in one sentence?"

If not → it's probably doing too much.

**Graphic:** Bloated agent illustration with warning signs

**SPEAKER NOTES:**

"How do you know if your agent is bloated?

[Walk through signs]

System prompt over 2000 words? That's a lot. Agent confusion about role? Bad sign. Too many tools, inconsistent quality, hard to debug - all symptoms.

[The test]

Here's a simple test: Can you describe what the agent does in ONE sentence? If you need five sentences, it's doing too much."

[Transition]

---

## SLIDE 6: SPECIALIZATION EXAMPLES

**Title:** Focused Agent Roles

**Content:**

| Agent Type | Focus | Does NOT Do |
|------------|-------|-------------|
| **Research Agent** | Gather information | Analyze or write |
| **Analysis Agent** | Analyze data | Gather or produce |
| **Writer Agent** | Produce content | Research or evaluate |
| **Reviewer Agent** | Evaluate quality | Create or modify |

**Clear boundaries = better results**

**Graphic:** Four agent icons with clear role labels

**SPEAKER NOTES:**

"Here are examples of specialized agents.

[Walk through each]

Research Agent gathers information. That's it. Doesn't analyze, doesn't write.

Analysis Agent analyzes data. Doesn't gather, doesn't produce.

Writer Agent produces content. Doesn't research, doesn't evaluate.

Reviewer Agent evaluates quality. Doesn't create, doesn't modify.

[Key point]

Clear boundaries. Each knows exactly what it does and doesn't do."

[Transition]

---

## SLIDE 7: DECOMPOSITION EXAMPLE

**Title:** From One to Many

**Content:**

**Before: Bloated Agent**
```
"You are a comprehensive research and analysis and writing assistant..."
[2500 word system prompt]
[12 tools configured]
```

**After: Specialized Agents**
```
Research Agent: 400 words, 3 tools
Analysis Agent: 300 words, 2 tools
Writer Agent: 350 words, 2 tools
Reviewer Agent: 250 words, 1 tool
```

**Total: 4 focused agents, clearer roles, better results**

**Graphic:** Before/after comparison

**SPEAKER NOTES:**

"Let's see decomposition in action.

[Before]

One bloated agent. 2500 word prompt. 12 tools. Does everything.

[After]

Four specialized agents. Each under 500 words. 2-3 tools each. Clear roles.

[Result]

Same work gets done, but each agent is focused. Quality improves. Debugging is easier."

[Transition]

---

## SLIDE 8: YOUR DECOMPOSITION

**Title:** Analyze Your Agent

**Content:**

**Exercise 5.1 will have you:**

1. List everything your current agent does
2. Identify distinct responsibilities
3. Design 2-4 specialist agents
4. Map dependencies between them
5. Choose an orchestration pattern

**Questions to Ask:**
- What are the natural stages of this work?
- Which tools go together?
- Where are the quality gates?

**Graphic:** Decomposition worksheet preview

**SPEAKER NOTES:**

"In Exercise 5.1, you'll analyze your own agent.

[Walk through steps]

List everything it does. Identify responsibilities. Design specialists. Map how they connect.

[Questions]

What are the natural stages? Which tools go together? Where should you check quality?

Now let's talk about how to coordinate these specialized agents."

[Transition: Click to Segment 2]

---

## SEGMENT 2: SEQUENTIAL ORCHESTRATION
### Duration: 12 minutes | Slides 9-13

---

## SLIDE 9: SEQUENTIAL PATTERN

**Title:** Pattern 1: Sequential Orchestration

**Content:**

```
Agent A → Agent B → Agent C → Final Output
(Research)  (Analyze)  (Write)
```

**Characteristics:**
- Output of one becomes input of next
- Clear sequential dependency
- Quality gates between stages

**Like a relay race - pass the baton**

**Graphic:** Pipeline flow diagram

**SPEAKER NOTES:**

"Sequential orchestration is the first pattern.

[Explain diagram]

Agent A runs first, produces output. That output goes to Agent B. Agent B produces output, goes to Agent C. Final result.

[Analogy]

Like a relay race. Each runner does their leg, passes the baton to the next.

This works when there's clear sequential dependency - B needs A's output before it can work."

[Transition]

---

## SLIDE 10: HOW IT WORKS

**Title:** Sequential Flow

**Content:**

1. **Orchestrator receives task**
2. **Call Agent A** with initial input
3. **Validate** Agent A output
4. **Call Agent B** with Agent A's output
5. **Validate** Agent B output
6. **Call Agent C** with Agent B's output
7. **Return** final output

**Key: Validation between every step**

**Graphic:** Numbered flow with validation checkpoints

**SPEAKER NOTES:**

"Here's the step-by-step flow.

[Walk through]

Orchestrator gets the task. Calls Agent A. Validates the output - did it produce what we expected? If yes, pass to Agent B. Validate again. Pass to Agent C. Validate. Return.

[Key point]

Validation between every step. This is your quality gate. Problems caught early, not at the end."

[Transition]

---

## SLIDE 11: IMPLEMENTATION

**Title:** Sequential Implementation

**Content:**

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

**Graphic:** Code block with annotations

**SPEAKER NOTES:**

"Here's what it looks like in code.

[Walk through]

Start with user request. Call research agent, get result, validate. Call analyze agent with that result, validate. Call write agent, validate, return.

[Key point]

The orchestrator is simple. It just calls agents in order and validates between. Each agent is focused on its job."

[Transition]

---

## SLIDE 12: WHEN TO USE SEQUENTIAL

**Title:** When Sequential Fits

**Content:**

**Use Sequential When:**
- Clear sequential dependency (B needs A's output)
- Each stage has a distinct skill
- Quality gates between stages are valuable
- Order matters

**Examples:**
- Research → Analyze → Report
- Gather → Transform → Publish
- Draft → Review → Finalize

**Graphic:** Examples with pipeline arrows

**SPEAKER NOTES:**

"When does sequential fit?

[Criteria]

When there's clear dependency - Agent B can't start until Agent A finishes. When each stage has a distinct skill. When you want quality gates between stages. When order matters.

[Examples]

Research-Analyze-Report is a natural pipeline. Gather-Transform-Publish. Draft-Review-Finalize.

For your capstone, if the work flows naturally through stages, sequential is your pattern."

[Transition]

---

## SLIDE 13: SEQUENTIAL VS. MULTI-STEP

**Title:** Not the Same as Multi-Step

**Content:**

**Multi-Step Agent (Week 4):**
- One agent, multiple steps
- Same agent throughout
- Steps defined in plan

**Sequential Orchestration (Today):**
- Multiple specialized agents
- Different agents at each stage
- Orchestrator coordinates

**Key Difference:**
Specialization creates different agents for different work.

**Graphic:** Side-by-side comparison

**SPEAKER NOTES:**

"Quick clarification.

[Multi-step]

Multi-step from Week 4 is one agent doing multiple steps. Same agent throughout, following its plan.

[Sequential]

Sequential orchestration is MULTIPLE agents. Different agents at each stage. Each specialized for their role. Orchestrator coordinates.

[Key difference]

Sequential has specialization. Each stage is a different expert, not one agent trying to do everything."

[Transition: Click to Segment 3]

---

## SEGMENT 3: MASTER-WORKER PATTERN
### Duration: 12 minutes | Slides 14-19

---

## SLIDE 14: MASTER-WORKER PATTERN

**Title:** Pattern 2: Master-Worker

**Content:**

```
                  ┌→ Worker A ─┐
Master (Planner) ─┼→ Worker B ─┼→ Master (Aggregator) → Output
                  └→ Worker C ─┘
```

**Characteristics:**
- Master decomposes and aggregates
- Workers execute subtasks
- Can run in parallel

**Like a manager with team members**

**Graphic:** Fan-out/fan-in diagram

**SPEAKER NOTES:**

"Master-Worker is the second pattern.

[Explain diagram]

Master receives the task, decomposes it into subtasks. Workers execute those subtasks - can be in parallel. Master collects results, aggregates into final output.

[Analogy]

Like a manager with team members. Manager assigns work, team does it, manager combines the results."

[Transition]

---

## SLIDE 15: HOW IT WORKS

**Title:** Master-Worker Flow

**Content:**

1. **Master decomposes** task into subtasks
2. **Master assigns** subtasks to workers
3. **Workers execute** independently (can be parallel)
4. **Master collects** results
5. **Master aggregates** into final output

**Two Master Phases:**
- Planning (decompose, assign)
- Aggregation (collect, synthesize)

**Graphic:** Two-phase master diagram

**SPEAKER NOTES:**

"Here's the flow.

[Walk through]

Master receives task, breaks it into subtasks. Assigns to workers. Workers execute - they can work in parallel since they're independent. Master collects all results. Master synthesizes into final output.

[Key insight]

Master has two phases. First, planning - decompose and assign. Last, aggregation - collect and synthesize. Workers do the middle."

[Transition]

---

## SLIDE 16: IMPLEMENTATION

**Title:** Master-Worker Implementation

**Content:**

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

**Note:** Workers share the same definition, just get different inputs.

**Graphic:** Code block with annotations

**SPEAKER NOTES:**

"Here's the implementation.

[Walk through]

Master decomposes request into subtasks. Loops through each, calls a worker, collects result. After all done, aggregates into final output.

[Key point]

Workers share the same definition. Same system prompt, same capabilities. They just get different inputs. Interchangeable."

[Transition]

---

## SLIDE 17: WHEN TO USE MASTER-WORKER

**Title:** When Master-Worker Fits

**Content:**

**Use Master-Worker When:**
- Task can be parallelized
- Workers are interchangeable
- Results need synthesis
- Divide and conquer makes sense

**Examples:**
- Analyze multiple documents → Synthesize findings
- Research multiple topics → Create unified report
- Process multiple data sources → Aggregate insights

**Graphic:** Examples with decomposition arrows

**SPEAKER NOTES:**

"When does Master-Worker fit?

[Criteria]

When the task can be parallelized - subtasks don't depend on each other. When workers are interchangeable - any can do any subtask. When results need synthesis at the end.

[Examples]

Analyze multiple documents, synthesize. Research multiple topics, unify. Process multiple sources, aggregate.

If your task naturally decomposes into similar subtasks, Master-Worker is your pattern."

[Transition]

---

## SLIDE 18: MASTER AGENT ROLES

**Title:** The Master's Two Hats

**Content:**

**Planning Phase:**
```
INPUT: "Research competitors in the fitness app market"
OUTPUT: [
  { "subtask": "Research competitor A", "worker": "any" },
  { "subtask": "Research competitor B", "worker": "any" },
  { "subtask": "Research competitor C", "worker": "any" }
]
```

**Aggregation Phase:**
```
INPUT: [result_A, result_B, result_C]
OUTPUT: "Synthesized competitive analysis..."
```

**Graphic:** Two-phase diagram with examples

**SPEAKER NOTES:**

"The master has two distinct roles.

[Planning]

Takes the request, breaks it into subtasks. Each subtask is self-contained. Any worker can do any of them.

[Aggregation]

Takes all the results, synthesizes into coherent final output. This is where the pieces come together.

You might even use different prompts for each phase - planning prompt and aggregation prompt."

[Transition]

---

## SLIDE 19: SEQUENTIAL VS. MASTER-WORKER

**Title:** Pattern Comparison

**Content:**

| Aspect | Sequential | Master-Worker |
|--------|------------|---------------|
| **Flow** | Linear | Fan-out/Fan-in |
| **Parallelism** | No | Yes |
| **Agents** | Different at each stage | Same workers |
| **Dependencies** | Stage-to-stage | None between workers |
| **Best for** | Pipelines | Decomposition |

**Both are valid for capstone - choose what fits your task.**

**Graphic:** Side-by-side pattern diagrams

**SPEAKER NOTES:**

"Let's compare.

[Walk through table]

Sequential is linear, no parallelism, different agents at stages. Master-Worker is fan-out, can parallelize, same workers.

[Key point]

Both are valid for your capstone. Sequential for pipelines. Master-Worker for decomposition. Choose what fits your task characteristics."

[Transition: Click to Segment 4]

---

## SEGMENT 4: OTHER PATTERNS + CLOSE
### Duration: 8 minutes | Slides 20-25

---

## SLIDE 20: OTHER PATTERNS (BRIEF)

**Title:** Other Patterns to Know

**Content:**

**Parallel Pattern:**
- Multiple agents simultaneously
- No dependency between them
- Results merged at end
- Good for: Multiple independent analyses

**Team-Based Pattern:**
- Agents with distinct roles that collaborate
- Can interact with each other
- Complex coordination
- Good for: Simulated expert panels

**Not recommended for capstone - too complex.**

**Graphic:** Brief diagrams of each

**SPEAKER NOTES:**

"Two more patterns to know about, briefly.

[Parallel]

Multiple agents run at once, no dependencies, merge results. Good for independent analyses.

[Team-Based]

Agents with roles that interact with each other. Complex coordination.

[Recommendation]

These are more complex. For your capstone, stick with Sequential or Master-Worker. You can explore these later."

[Transition]

---

## SLIDE 21: PATTERN SELECTION GUIDE

**Title:** Choosing Your Pattern

**Content:**

| Pattern | Use When | Complexity |
|---------|----------|------------|
| **Sequential** | Clear stages, dependencies | Low |
| **Master-Worker** | Decomposable, aggregatable | Medium |
| **Parallel** | Independent analyses | Medium |
| **Team-Based** | Complex collaboration | High |

**For Capstone:**
- Recommend: Sequential or Master-Worker
- Start simple, can expand later

**Graphic:** Decision guide with recommendations

**SPEAKER NOTES:**

"Here's your selection guide.

[Walk through table]

Sequential is lowest complexity. Clear stages, dependencies.

Master-Worker is medium. Decomposable tasks.

[Capstone advice]

For your capstone, use Sequential or Master-Worker. Parallel and Team-Based add complexity you don't need yet. Start simple - you can always expand later."

[Transition]

---

## SLIDE 22: PLANNING YOUR CAPSTONE

**Title:** Choose Your Architecture

**Content:**

**This Week:**
- Decompose your agent into specialists
- Choose Sequential or Master-Worker
- Design the orchestration
- Test end-to-end

**Questions to Answer:**
1. How many specialists do I need?
2. What's the natural flow?
3. Can I parallelize anything?
4. Where are the quality gates?

**Graphic:** Architecture planning checklist

**SPEAKER NOTES:**

"This week you're making architecture decisions for your capstone.

[Tasks]

Decompose into specialists. Choose your pattern. Design the orchestration. Test it.

[Questions]

How many specialists? What's the natural flow? Can you parallelize? Where are quality gates?

Your homework walks you through this systematically."

[Transition]

---

## SLIDE 23: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Focus |
|----------|------|-------------|-------|
| 5.1: Agent Decomposition | 25 min | Decomposition doc | Identify specialists |
| 5.2: Orchestration Implementation | 30 min | Working orchestration | Build coordination |
| 5.3: Integration Testing | 20 min | Test results | Verify system |
| **Total** | **75 min** | | |

**Optional: 5.4 Peer Review (30 min)**

**Graphic:** Exercise flow

**SPEAKER NOTES:**

"Your homework.

[Walk through]

Exercise 5.1 - decompose your agent. 25 minutes. Identify specialists.

Exercise 5.2 - implement orchestration. 30 minutes. Build the coordination layer.

Exercise 5.3 - integration testing. 20 minutes. Verify it all works together.

Optional 5.4 - peer review if you have a partner.

By end of week, multi-agent orchestration should be working."

[Transition]

---

## SLIDE 24: RESOURCES

**Title:** Resources for This Week

**Content:**

**Templates:**
- Agent decomposition template - Participant Guide
- Sequential design template - Participant Guide
- Master-Worker design template - Participant Guide
- Integration test template - Participant Guide

**Reference:**
- [Multi-Agent Systems](https://docs.anthropic.com/en/docs/agents)
- [Orchestration Patterns](https://microservices.io/patterns/data/saga.html)

**Graphic:** Resource icons

**SPEAKER NOTES:**

"Resources for this week.

All templates in your participant guide. Choose Sequential or Master-Worker template based on your pattern choice.

Reference links for deeper reading on multi-agent and orchestration patterns."

[Transition]

---

## SLIDE 25: NEXT WEEK PREVIEW

**Title:** Next Week: Optimization & Monitoring

**Content:**

**Preview:**
Week 6 covers production readiness, performance dashboards, cost optimization, and reliability patterns.

**What to Complete:**
- [ ] Exercise 5.1: Agent Decomposition
- [ ] Exercise 5.2: Orchestration Implementation
- [ ] Exercise 5.3: Integration Testing
- [ ] Run multi-agent system 5+ times

**Key Preparation:**
Orchestration must be working - we'll be optimizing it.

**Graphic:** Preview showing dashboard

**SPEAKER NOTES:**

"Next week is Optimization & Monitoring.

Production readiness. Performance dashboards. Cost optimization. Reliability patterns.

[Requirements]

Your orchestration needs to be working. We'll be measuring and optimizing.

[Final close]

Good session today. You've learned how to break work into specialized agents and coordinate them. That's a major capability.

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

### Graphic Suggestions

| Slide | Graphic Type | Description |
|-------|-------------|-------------|
| 1 | Title | Connected agents visual |
| 4 | Graph | Quality vs. Scope curve |
| 9 | Pipeline | Sequential flow arrows |
| 14 | Fan-out | Master-Worker diagram |
| 19 | Comparison | Side-by-side patterns |

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
