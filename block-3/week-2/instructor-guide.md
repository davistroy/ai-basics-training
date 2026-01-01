# **INSTRUCTOR GUIDE: BLOCK 3 WEEK 2**
## **Building Reliable Agents**

**Block:** 3: AI Automation Architecture
**Week:** 2 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Building first functional agent with Domain Memory and error handling |
| **Difficulty Level** | High |
| **Prep Time Required** | 60 minutes |
| **Demo Required** | Yes - Research Assistant agent live build |
| **Tech Setup Needed** | MCP configured, Claude Desktop ready, sample agent code |
| **Common Challenges** | Error handling complexity; understanding the agent loop |

---

## Navigation

**Block Navigation:** [Week 1 Instructor Guide](../week-1/instructor-guide.md) | **Week 2** | [Week 3 Instructor Guide](../week-3/instructor-guide.md)

**Related Materials:**
- [Week 2 Presentation Slides](presentation.md)
- [Week 2 Participant Guide](participant-guide.md)
- [Block 3 Main Document](../block-3.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 2 materials | |
| Prepare demo | Build and test Research Assistant agent | |
| Check agent designs | Review participant agent design documents | |
| Test error scenarios | Prepare examples of each failure type | |
| Review Week 1 | Check Week 1 feedback and questions | |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, Claude Desktop, MCP | |
| Load presentation | Have slides ready and tested | |
| Test demo agent | Run Research Assistant through all scenarios | |
| Prepare error triggers | Have ways to force each error type | |
| Check participant progress | Review who completed Week 1 exercises | |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, Claude Desktop, demo environment | |
| Test share | Verify screen sharing works | |
| Load demo agent | Have Research Assistant ready to run | |
| Start recording | If session is recorded | |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Week 1 recap | Connect to designs |
| 0:03 | 8 min | Segment 1 | Domain Memory - What Makes Agents Reliable | Theory foundation |
| 0:11 | 8 min | Segment 2 | The Agent Execution Loop | Core concept |
| 0:19 | 13 min | Segment 3 | Error Handling for Agents | Critical for reliability |
| 0:32 | 9 min | Segment 4 | Live Demo - Building First Agent | Hands-on demonstration |
| 0:41 | 4 min | Segment 5 | Testing Agent Reliability + Close | Homework preview |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Shorten Circuit Breaker code example (reference in guide)
- Reduce demo to 6 minutes focusing on core loop only
- Skip multi-agent error propagation (reference in guide)

**If Running Ahead:**
- More Q&A on error handling strategies
- Extended demo showing error recovery
- Discuss specific participant agent designs

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:11 | Compress Three Pillars to key points |
| End Segment 3 | 0:32 | Must start demo by 0:32 |
| Start Closing | 0:41 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants
2. Quick recap of Week 1: agents vs. workflows, Two-Agent Pattern
3. Connect to their design documents
4. Preview today's session

**Opening Script:**
> "Welcome to Week 2: Building Reliable Agents. Last week we covered the fundamental distinction between agents and workflows, and the Two-Agent Architecture Pattern. You all created agent design documents. Today we take those designs and start building. By the end of our 45 minutes, you'll understand the Domain Memory pillars, the agent execution loop, and error handling patterns that make agents reliable."

**Engagement Opportunity:**
> "Quick check-in: What was the hardest part of your agent design document? Any sections that were unclear?"

[Wait for 1-2 responses - this should take 30 seconds max]

---

### Segment 1: Domain Memory - What Makes Agents Reliable (8 minutes)

**Learning Objective:** Understand and apply the Three Pillars of Domain Memory

**Slides:** 3-6

#### Content Delivery

**Key Point 1: Recall the Fundamental Insight**
- Main message: Agents are "unreliable amnesiacs" - we build systems with memory
- Example to use: "Your agent design document IS Domain Memory - it's the Setup Agent output"
- Common misconception: That we're giving the agent memory (we're not - memory is in the records)

**Key Point 2: The Three Pillars**
- Main message: Explicit Goals, Progress Records, Operating Procedures
- Demonstration: Show how each pillar appears in their design documents
- Participant relevance: "Your design document maps to these pillars"

**Key Point 3: Why Each Pillar Matters**
- Main message: Goals prevent different interpretations; Progress prevents Groundhog Day; Procedures ensure quality
- Practice preview: Exercise 2.3 documents failure modes as part of Operating Procedures

#### Facilitation Notes

**Watch For:**
- Confusion about how design document relates to Domain Memory
- Participants who didn't complete agent design

**If Asked About Design Document Gaps:**
> "If your design document is incomplete, that's okay - today's content will help you fill it in. Focus on defining testable success criteria and failure triggers."

**Transition to Segment 2:**
> "Now that we understand what makes agents reliable, let's look at how agents actually execute - the agent loop."

---

### Segment 2: The Agent Execution Loop (8 minutes)

**Learning Objective:** Understand the observe-think-act loop and key implementation concepts

**Slides:** 7-10

#### Content Delivery

**Key Point 1: The Loop Structure**
- Main message: Receive task → Analyze → Decide → Execute → Observe → Check goal → Loop or Complete
- Visual to emphasize: Loop diagram with all states
- Key insight: "The agent decides when to stop - that's what makes it an agent, not a workflow"

**Key Point 2: Key Implementation Concepts**
- Main message: Maximum iterations, state management, tool result parsing, completion detection
- Framework: "Every loop needs bounds - max iterations, timeout, error limits"
- Real-world application: "Without bounds, agents can loop forever or drain your API budget"

**Key Point 3: Completion Detection**
- Main message: Agent must recognize when goal is achieved
- Example: "Success criteria from your design document become completion checks"
- Connection to homework: "Exercise 2.1 implements this loop for your agent"

#### Facilitation Notes

**Energy Check:**
At this point in the session, participants may be:
- Eager to see code (demo coming next segment)
- Worried about implementation complexity (reassure - we'll build step by step)

**Transition to Segment 3:**
> "The loop is the core. But what happens when things go wrong? Error handling is what separates fragile agents from reliable ones."

---

### Segment 3: Error Handling for Agents (13 minutes)

**Learning Objective:** Implement robust error handling for all failure types

**Slides:** 11-17

#### Content Delivery

**Key Point 1: Types of Agent Failures**
- Main message: Four types - Tool failures, Reasoning failures, Context failures, Quality failures
- Structure to present:
  - Tool: API down, permission denied, timeout
  - Reasoning: Agent gets confused, loops
  - Context: Loses track of goal, forgets state
  - Quality: Produces wrong/poor output

**Key Point 2: Error Handling Strategy**
- Main message: Try-Catch pattern with retry, fallback, or escalate
- Framework: "For each action: Try → Catch → Decide (retry/fallback/escalate)"
- Code example: Show the error handling pseudocode

**Key Point 3: The Circuit Breaker Pattern**
- Main message: Prevent infinite loops with iteration limits, timeouts, consecutive error limits
- Code example: CircuitBreaker class with three checks
- Key insight: "The circuit breaker is your safety net"

**Key Point 4: The 3-Failure Rule**
- Main message: LLMs can recover from errors, but after 3 consecutive failures, escalate
- Rationale: "It's tried its best approaches; more attempts won't help"
- Connection to design: "This is an Operating Procedure in your Domain Memory"

**Key Point 5: Multi-Agent Error Propagation**
- Main message: Sub-agents should return structured failure info, not crash
- Framework: success flag, partial work, can_retry boolean
- Key insight: "Let parent agent decide: retry, work around, or escalate"

#### Demo Instructions (if applicable)

**Demo Duration:** Not in this segment - demo is Segment 4

#### Facilitation Notes

**Watch For:**
- Overwhelm at the number of error types
- Questions about specific error scenarios

**If Asked About Specific Errors:**
> "That's a great specific scenario. Let's think through it: What type of failure is it? What's the recovery strategy? Exercise 2.2 will have you map this out for your agent."

**Transition to Segment 4:**
> "Now let's see all of this in action. I'm going to build a simple agent live so you can see the loop and error handling work together."

---

### Segment 4: Building Your First Agent - Live Demo (9 minutes)

**Learning Objective:** See agent construction and execution in practice

**Slides:** 18-19

#### Demo Instructions

**Demo Duration:** 9 minutes

**Setup Required:**
- Claude Desktop with MCP configured
- Web search, file reader, note taker tools available
- Pre-written system prompt ready to paste
- Simple research question prepared

**Demo Steps:**
1. Show system prompt with role and tools (1 min)
2. Show initial context setup (1 min)
3. Show tool configuration via MCP (1 min)
4. Execute agent with simple query (3 min)
5. Show error handling in action - trigger a timeout (2 min)
6. Wrap up with key observations (1 min)

**Demo Talking Points:**
> "Watch how the agent decides which tool to use first. It's not following a script - it's making a decision."
> "Notice the loop - it observes the tool result, thinks about what to do next, then acts again."
> "Here's where error handling kicks in. The tool timed out, but the agent recovers and tries an alternative."

**Backup Plan:**
If demo fails:
1. Use pre-recorded video of agent execution
2. Walk through the code and expected behavior
3. Show screenshots of each step

#### Facilitation Notes

**Watch For:**
- Questions during demo that derail the timing
- Technical issues with Claude Desktop or MCP

**If Demo Runs Into Problems:**
> "This is actually a great example of why error handling matters! Let me show you what's happening..."

---

### Segment 5: Testing Agent Reliability + Closing (4 minutes)

**Learning Objective:** Understand testing categories and homework preview

**Slides:** 20-24

#### Content Delivery

**Key Point 1: Test Categories**
- Main message: Happy path, Edge cases, Error cases, Stress cases
- Framework: "Start with happy path, then systematically break things"

#### Homework Preview

**Key Actions:**
1. Overview all three exercises briefly
2. Highlight the importance of Exercise 2.1 (building functional agent)
3. Note that 5+ executions are expected this week

**Script:**
> "Your homework includes three exercises totaling about 75 minutes.
>
> Exercise 2.1 is Build Functional Agent - takes about 40 minutes. You'll implement the agent from your design document with the execution loop.
>
> Exercise 2.2 is Implement Error Handling - about 20 minutes. Add try/catch, iteration limits, and logging.
>
> Exercise 2.3 is Failure Mode Documentation - 15 minutes. Create a catalog of what can go wrong and how to handle it.
>
> By end of week, you should have 5+ successful agent executions. Everything is in your participant guide."

#### Resources and Support

> "If you get stuck on error handling, check the Anthropic Agent Documentation. Circuit Breaker pattern reference is also in your guide."

#### Next Week Preview

> "Next week is MCP Deep Dive - advanced tool integration. Your agent needs to be functional before then because we'll be expanding its capabilities."

#### Session Close

> "Questions before we wrap? ... Great progress today. Building reliable agents is the foundation for everything that follows. See you next week!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: How is Domain Memory different from just good documentation?**
A: Domain Memory is live, structured state that agents read and write. Documentation is static. The three pillars are specifically designed to enable stateless agents to function reliably.

**Q: Why 3 consecutive failures before escalating? Why not 2 or 5?**
A: Three is a pragmatic threshold. One failure could be a fluke. Two suggests a pattern. Three confirms the agent is stuck. More than three wastes time and resources. But adjust based on your specific use case.

**Q: What if my agent needs more than one tool at once?**
A: That's parallel tool use - covered in Week 3. For now, focus on sequential tool use with proper loop handling.

### Technical Questions

**Q: How do I implement the Circuit Breaker in Make/n8n?**
A: Use counters and conditional branches. Add a counter node that increments on each iteration, check against max before continuing. For errors, maintain an error counter that resets on success.

**Q: How do I parse tool results if they're inconsistent?**
A: Add a validation step after each tool call. Check for expected format, handle missing fields gracefully. Log unexpected formats for debugging.

### Scope Questions

**Q: My agent seems too complex for Week 2 - what should I do?**
A: Focus on the core loop with your highest-priority tool. Add complexity in later weeks. It's better to have a simple working agent than a complex broken one.

**Q: Can I use a different error handling approach?**
A: Yes, the patterns shown are guidelines. The key is having SOME systematic approach. Document your approach so you can improve it.

### Pushback/Objections

**Q: This seems like a lot of overhead for a simple task.**
A: For simple tasks, you're right - use workflows. Error handling pays off when tasks are complex or when reliability matters. The patterns we're learning apply to production systems.

**Q: Won't all this error handling slow things down?**
A: Slightly, yes. But the alternative is agents that fail unpredictably or loop forever. The overhead is worth the reliability. Optimize later.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Claude Desktop not responding | Restart application | Use pre-recorded demo |
| MCP tools not loading | Check config, restart | Demonstrate conceptually |
| Demo agent loops infinitely | Show circuit breaker kicking in | "This is why we need error handling!" |
| Screen share fails | Restart share | Have participant share |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Confusion about loop | "When does it stop?" | Emphasize completion detection |
| Overwhelmed by error types | Glazed looks | "Start with tool errors only, add others later" |
| Design document incomplete | Can't discuss their agent | "Focus on one path first, expand later" |
| Afraid to try | "What if it breaks?" | "Breaking is learning. Failures teach us." |
| Over-engineering | Adding too many error cases | "Start simple, add based on actual failures" |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Content too easy | "We know try/catch" | Emphasize agent-specific patterns |
| Content too hard | Many questions about basics | Slow down, more examples |
| Off-topic tangent | Discussion of specific tools | "Let's focus on patterns, tools in Week 3" |
| Time pressure | Running behind | Cut multi-agent error propagation |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save any chat questions | For follow-up |
| Note demo issues | For improvement |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | |
| Answer pending questions in support channel | |
| Send follow-up message about 5+ execution target | |
| Document issues encountered for curriculum improvement | |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions (check for functional agents) | |
| Identify participants with non-functional agents | |
| Prepare MCP server recommendations for next week | |
| Update this instructor guide with lessons learned | |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 2.1 | Working agent + execution documentation | GitHub repo `/agents/[name]/` |
| 2.2 | Error handling configuration + test results | GitHub repo |
| 2.3 | `failure-modes.md` | GitHub repo `/agents/[name]/` |

### Progress Check Approach

**How to Verify Completion:**
- Check GitHub commits for agent code and documentation
- Look for 5+ execution logs
- Verify failure modes document exists

**Intervention Thresholds:**
- Agent not functional: Reach out immediately
- Fewer than 3 executions: Encourage more testing
- No failure mode documentation: May not understand error handling

---

## Week-Specific Notes

### What Makes This Week Unique

- **First implementation week** - Moving from design to building
- **High failure potential** - Expect participants to struggle with agent reliability
- **Critical foundation** - If agents don't work this week, later weeks suffer
- **Demo is essential** - Participants need to see a working agent

### Dependencies

**Builds On:**
- Week 1: Agent design document becomes implementation foundation
- Week 1: System prompt gets implemented

**Sets Up:**
- Week 3: Functional agent ready for MCP expansion
- Week 4: Agent with error handling ready for multi-step
- All remaining weeks: Agent must work before we can optimize/orchestrate

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| MCP configuration varies by OS | Provide OS-specific guidance | Active |
| Claude Desktop version differences | Specify minimum version | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- "What are the three pillars of Domain Memory?" (Goals, Progress, Procedures)
- "When should an agent escalate rather than retry?" (After 3 consecutive failures)
- Observable behavior indicating understanding: Asking specific questions about their agent
- Observable behavior indicating confusion: Generic questions, not connecting to their design

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 2.1: Agent actually executes and produces output
- Exercise 2.2: Error handling catches at least one error type
- Exercise 2.3: Failure modes are specific to their agent, not generic

**Common Issues to Flag:**
- Agent has no iteration limit (dangerous)
- No error logging (can't debug)
- Failure modes copied from template without customization

### Connecting to Capstone

**Capstone Relevance:**
This week's work contributes to the capstone by:
- Agent execution forms the core of capstone system
- Error handling patterns used throughout remaining weeks
- Failure mode documentation becomes part of capstone documentation

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Quick pulse check: "How confident are you in building your agent after today?"
- Open question: "What would help you most with implementation?"

**Improvement Log:**

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| | | | |

### Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial guide created | Training Team |

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Domain Memory enables reliability - Goals, Progress, Procedures"
2. "The agent loop is bounded - max iterations, timeout, error limits"
3. "After 3 failures, escalate - don't thrash indefinitely"

### If You Only Have Time For One Thing

The Circuit Breaker Pattern: Every agent needs bounds - max iterations, timeout, and consecutive error limits. Without these, agents can loop forever or drain resources.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Circuit Breaker | Electrical circuit breaker in your home | Explaining why agents need automatic shutoff |
| 3-Failure Rule | "Three strikes and you're out" | Explaining escalation threshold |
| Error handling | Safety net for acrobats | Explaining why overhead is worth it |
