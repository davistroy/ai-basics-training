# **INSTRUCTOR GUIDE: ADVANCED MODULE 2 SESSION 1**
## **Chaos Engineering Fundamentals**

**Module:** Advanced Module 2: Chaos Testing & Reliability Engineering
**Session:** 1 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Introduction to chaos engineering principles and failure mode analysis for AI agent systems |
| **Difficulty Level** | Medium |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Optional - Can show failure mode example or experiment design |
| **Tech Setup Needed** | None (conceptual session, hands-on in exercises) |
| **Common Challenges** | Participants may want to test in production immediately; emphasize safety protocols |

---

## Navigation

**Module Navigation:** Session 1 | [Session 2 Instructor Guide →](/home/user/ai-basics-training/materials/advanced-modules/module-2-chaos-testing/session-2/instructor-guide.md)

**Related Materials:**
- [Session 1 Presentation Slides](/home/user/ai-basics-training/materials/advanced-modules/module-2-chaos-testing/session-1/presentation.md)
- [Session 1 Participant Guide](/home/user/ai-basics-training/materials/advanced-modules/module-2-chaos-testing/session-1/participant-guide.md)
- [Module 2 Main Document](/home/user/ai-basics-training/materials/advanced-modules/module-2-chaos-testing/module-2-chaos-testing.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Session 1 materials | ☐ |
| Prepare examples | Identify 2-3 real failure scenarios from your experience | ☐ |
| Check resources | Verify Appendix A (Chaos Testing Checklist) is accessible | ☐ |
| Prepare backup | Optional: Create failure mode or experiment design example | ☐ |
| Review prerequisites | Confirm participants completed Block 3 | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice key segments if needed | ☐ |
| Prepare materials | Have templates ready to reference | ☐ |
| Check participant readiness | Verify who has operational agent systems | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, templates, resources | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Brief chat, answer quick questions | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, context, preview | Keep brisk |
| 0:03 | 12 min | Segment 1 | Introduction to Chaos Engineering | Core concepts |
| 0:15 | 12 min | Segment 2 | AI Agent Failure Modes | Critical categorization |
| 0:27 | 12 min | Segment 3 | Designing Chaos Experiments | Detailed template |
| 0:39 | 3 min | Segment 4 | Safe Testing Environment | Safety emphasis |
| 0:42 | 3 min | Closing | Homework, resources, preview | Don't skip |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Segment 2: Show failure categories table, but don't walk through each example - "See participant guide for details"
- Segment 3: Show complete experiment template but don't explain every field - focus on hypothesis and success criteria
- Segment 4: Reference safety checklist, don't read through it

**If Running Ahead:**
- Add more real-world failure stories
- Deeper dive on prioritization matrix in Segment 2
- Show an actual experiment document example in Segment 3
- Extra Q&A time

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | If behind, reduce examples; if ahead, add stories |
| End Segment 2 | 0:27 | If behind, reference templates without full explanation |
| Start Closing | 0:42 | Must start here regardless - closing is not optional |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slides 1-3**

**Key Actions:**
1. Welcome participants warmly - this is advanced content for Block 3 graduates
2. Acknowledge their agent systems are already working
3. Position chaos testing as "making good systems bulletproof"
4. Preview the session structure

**Opening Script:**
> "Welcome to Advanced Module 2, Session 1. You've all completed Block 3, so you've built sophisticated agent systems. Today we're learning how to make them production-grade through chaos engineering. The philosophy is simple: break it in testing so it doesn't break in production. By the end of our 45 minutes together, you'll know how to systematically find and fix failure modes before your clients discover them."

**Engagement Opportunity:**
> "Quick check-in: How many of you have had an agent work perfectly in testing, then fail unexpectedly in a real scenario?"

[Show of hands - this should take 20 seconds max]

---

### Segment 1: Introduction to Chaos Engineering (12 minutes)

**Learning Objective:** Understand chaos engineering principles and the experiment cycle

**Slides:** 4-7

#### Content Delivery

**Key Point 1: What is Chaos Engineering?**
- Main message: Proactive discipline of testing system resilience through controlled failure injection
- Example to use: Netflix Chaos Monkey - randomly terminates production instances to ensure systems can handle failures
- Common misconception: "This is just error handling" - NO, it's systematic discovery of unknown failure modes

**Key Point 2: The Chaos Engineering Cycle**
- Main message: Six-step repeatable process from hypothesis to fix
- Demonstration: Walk through the cycle with a simple example (MCP server failure)
- Participant relevance: They'll use this exact cycle in Exercise 1.3

**Key Point 3: Why AI Agents Need It**
- Main message: Non-determinism, complex dependencies, and orchestration create unique failure modes
- Practice preview: Exercise 1.1 will help them identify all the unique failure modes in their systems

#### Facilitation Notes

**Watch For:**
- Participants assuming this is "just testing" - emphasize the systematic, hypothesis-driven approach
- Questions about production testing - reinforce safety-first approach

**If Asked About "Can't we just handle errors normally?":**
> "Error handling is reactive - you handle errors you expect. Chaos engineering is proactive - it finds the errors you didn't think of. You're not just testing if your error handler works; you're discovering what can actually go wrong."

**Transition to Segment 2:**
> "Now that you understand the chaos engineering approach, let's explore the specific ways AI agents fail. This categorization will guide your testing strategy."

---

### Segment 2: AI Agent Failure Modes (12 minutes)

**Learning Objective:** Identify and categorize AI agent failure modes

**Slides:** 8-11

#### Content Delivery

**Key Point 1: Five Failure Categories**
- Main message: Tool, AI, Orchestration, Resource, External - each needs different handling
- Visual to emphasize: The failure categories table on Slide 8

**Key Point 2: Systematic Analysis**
- Main message: Each failure mode gets documented with 6 attributes (what, likelihood, impact, detection, current, desired)
- Hands-on reference: This exact template is used in Exercise 1.1

**Key Point 3: Prioritization Matrix**
- Main message: Test high likelihood × high impact failures first
- Real-world application: A common failure (API rate limits) might be lower priority than a rare but critical failure (infinite loop draining budget)

#### Interactive Element

**Activity Type:** Quick poll

**Activity Duration:** 2 minutes

**Instructions:**
1. Ask: "What's the failure you're most concerned about in your agent system?"
2. Have 2-3 participants share briefly in chat or verbally
3. Debrief by mapping their concerns to the five categories

**Debrief Points:**
> "Notice how these map to our categories. [Name]'s concern about API timeouts is a Tool Failure. [Name]'s worry about context loss is an AI Failure. The categorization helps you organize your thinking and ensures you don't miss entire classes of failures."

#### Facilitation Notes

**Energy Check:**
At this point in the session, participants may be:
- Information-saturated - lots of new concepts
- Use concrete examples rather than abstract theory

**Common Confusion Point:**
Distinguishing between Tool Failures and External Failures

**Clarification Approach:**
> "Tool Failures are when your agent's tools (MCP servers, APIs you call directly) fail. External Failures are when services your tools depend on fail. If your agent calls a GitHub MCP server that works, but GitHub's API is down, that's External. If the MCP server itself crashes, that's Tool."

**Transition to Segment 3:**
> "You now know what can fail. Next, let's learn how to design rigorous experiments to test each failure mode."

---

### Segment 3: Designing Chaos Experiments (12 minutes)

**Learning Objective:** Design structured chaos experiments with clear hypotheses

**Slides:** 12-15

#### Content Delivery

**Key Point 1: Six Required Elements**
- Main message: Hypothesis, steady state, injection, observation, rollback, success criteria - all are mandatory
- Framework/Pattern: The complete experiment template structure

**Key Point 2: Example Walkthrough**
- Main message: Show how a complete experiment looks with all elements filled in
- Example walkthrough: MCP Server Failure experiment (Slide 13)

**Key Point 3: Injection Methods**
- Main message: Six common techniques from safe (config changes) to risky (process killing)
- Practical application: Always start with safer methods, progress to riskier ones as you gain confidence

#### Facilitation Notes

**Watch For:**
- Participants jumping to "let's just break stuff" mentality
- Missing the importance of clear hypotheses and success criteria

**If Asked About "How detailed should the hypothesis be?":**
> "Specific enough that someone else could validate whether it's true. 'System handles failure' is too vague. 'Agent retries 3 times with exponential backoff, then fails with error code X' is specific enough."

**Common Mistake to Address:**
Not defining steady state first - emphasize you can't test "broken" if you don't know what "working" looks like

**Transition to Segment 4:**
> "You can now design rigorous experiments. But before you start breaking things, let's talk about how to do this safely."

---

### Segment 4: Safe Testing Environment (3 minutes)

**Learning Objective:** Set up safe testing environments with proper safeguards

**Slides:** 16-18

#### Content Delivery

**Key Point 1: Five Safety Requirements**
- Main message: Isolated, monitored, labeled, test-data-only, rollback-ready
- Framework: The safety checklist

**Key Point 2: Observability and Kill Switch**
- Main message: Real-time monitoring is mandatory, not optional
- Demonstration: Explain what a kill switch implementation looks like

#### Closing This Segment

**Key Takeaway:**
> "Safety is not optional. Never inject failures without full monitoring and a way to stop immediately. In Exercise 1.3, you'll set up your safe environment before running any tests."

**Connection to Homework:**
> "In your exercises, you'll create a failure catalog, design experiments, and execute them safely. The safety checklist in Appendix A guides your setup."

---

### Closing (3 minutes)

**Slides:** 19-21

**Do Not Skip This Section** - even if running behind

#### Homework Preview

**Key Actions:**
1. Overview all three exercises briefly (catalog, design, execute)
2. Emphasize the progression: analysis → design → hands-on testing
3. Note total time: 75 minutes
4. Point to participant guide for detailed instructions

**Script:**
> "Your homework includes three exercises totaling about 75 minutes.
>
> Exercise 1.1 - 25 minutes - Create a complete failure mode catalog for your agent system. Document everything that can fail.
>
> Exercise 1.2 - 25 minutes - Design 5 chaos experiments with all six required elements.
>
> Exercise 1.3 - 25 minutes - Execute at least 3 experiments and document results.
>
> Everything you need is in your participant guide, including templates."

#### Resources and Support

> "If you get stuck, post in [support channel]. Common questions: check the troubleshooting sections in your participant guide first."

#### Next Week Preview

> "Next session we'll implement advanced reliability patterns - circuit breakers, bulkheads, and self-healing. These patterns address the weaknesses you'll find in your chaos testing this week. Make sure to complete all exercises - we'll build on them."

#### Session Close

> "Questions before we wrap? ... Great session today. Remember: every failure you find in testing is one you won't see in production. Happy chaos testing!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Isn't chaos engineering just fancy testing?**
A: No - traditional testing verifies known behaviors work correctly. Chaos engineering discovers unknown failure modes. You're not testing if your error handler works; you're finding errors you didn't know could happen.

**Q: Why can't we just write better error handlers?**
A: You can only handle errors you know about. Chaos engineering finds the errors you didn't anticipate. It's discovery, not just validation.

**Q: Do we really need to document everything in a catalog?**
A: Yes - without documentation, chaos testing is just random breaking. The catalog provides prioritized structure and ensures comprehensive coverage.

### Technical Questions

**Q: How do I inject failures in Claude Desktop agent systems?**
A: For MCP servers: rename config files or stop servers. For API calls: use proxy tools or mocks. For resources: set strict token limits. Details in Exercise instructions.

**Q: What monitoring do I need?**
A: At minimum: real-time log viewing, success/failure metrics, and error message tracking. Claude Desktop has built-in logging; use that as starting point.

**Q: How do I know if my kill switch works?**
A: Test it! Before running real chaos experiments, trigger the kill switch manually to verify it stops everything and restores state.

### Scope Questions

**Q: Should we chaos test in production?**
A: Not initially. Start in test environments. Only test in production after extensive test-environment validation AND with comprehensive safeguards (canary testing, feature flags, immediate rollback).

**Q: How many experiments do we need?**
A: Start with your top 5 priority failures. Cover all five categories (Tool, AI, Orchestration, Resource, External). Expand from there.

**Q: What if we find failures we can't fix?**
A: Document them as known limitations. Implement monitoring and alerting. Consider graceful degradation. Not all failures need to be prevented - some need to be handled gracefully.

### Pushback/Objections

**Q: This seems like a lot of overhead for small systems**
A: Start small - even 3 experiments will find critical issues. The cost of one production failure usually exceeds the cost of chaos testing. Think of it as insurance.

**Q: Our agents are simple, do we really need this?**
A: If your agents interact with external services, use MCP servers, or handle customer work, yes. Even simple agents have failure modes. Better to find them in testing.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Screen share fails | Restart share, switch to window share | Ask participant to share, or describe slides verbally |
| Slides won't load | Use backup PDF or browser version | Deliver from speaker notes without slides |
| Audio issues | Ask participants to type questions | Continue with video only, monitor chat |
| Internet drops | Rejoin immediately | Extend session time if needed |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Confusion about chaos vs testing | "Isn't this just error handling?" | Emphasize discovery vs validation distinction |
| Safety concerns | "What if this breaks production?" | Reinforce isolated environments and safety protocols |
| Overwhelm | "Too many failure modes to track" | Start with top 5 priorities, expand later |
| Resistance | "Seems like overkill" | Share production failure story, emphasize prevention cost vs fix cost |
| Overconfidence | "Our system handles failures fine" | Challenge: "Have you tested every scenario?" Chaos will find gaps |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Content too theoretical | "Can you show an example?" | Use Slide 13 MCP failure experiment, or share real scenario |
| Confusion on prioritization | "How do I rank these?" | Use simple formula: Likelihood × Impact, walk through example |
| Missing context | "We don't have monitoring" | Basic logging is sufficient to start, reference setup in Exercise 1.3 |
| Time pressure | Running behind | Skip detailed template walkthroughs, reference participant guide |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save chat questions | For follow-up or FAQ updates |
| Note what worked/didn't | Mental notes for improvement |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | ☐ |
| Answer pending questions in support channel | ☐ |
| Send follow-up message: "Remember to complete Exercise 1.3 - execute chaos tests" | ☐ |
| Document any confusion points for curriculum improvement | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions (spot check 3-5) | ☐ |
| Identify participants who haven't completed exercises | ☐ |
| Prepare clarifications for Session 2 based on findings | ☐ |
| Update this instructor guide with lessons learned | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Session

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 1.1 | `failure-mode-catalog.md` | Participant's project repository |
| 1.2 | `chaos-experiment-suite.md` | Participant's project repository |
| 1.3 | Chaos test results (3+ experiments) | Participant's project repository or shared document |

### Progress Check Approach

**How to Verify Completion:**
- Check for file creation in repositories
- Look for documented results with expected vs actual columns filled
- Red flags: Missing priority matrix, experiments without all 6 elements, no actual test execution

**Intervention Thresholds:**
- 1 exercise incomplete: Monitor, may be time constraints
- Missing Exercise 1.3 (execution): Reach out - hands-on practice is critical
- No deliverables: 1:1 conversation - may need system setup help

---

## Session-Specific Notes

### What Makes This Session Unique

This is the foundational session for chaos engineering - participants may never have heard of this discipline. Key challenges:

- **Conceptual shift**: Moving from "testing features" to "testing resilience"
- **Safety emphasis**: Must establish safety-first mindset before hands-on
- **Systematic approach**: Fighting urge to "just try breaking stuff" without structure
- **Application to AI**: Unique failure modes (non-determinism, orchestration) require new thinking

### Dependencies

**Builds On:**
- Block 3: Multi-agent systems, orchestration patterns, error handling basics
- Assumes participants have working agent systems to test

**Sets Up:**
- Session 2: Reliability patterns (circuit breakers, self-healing) address failures found in chaos testing
- Capstone: Reliability report includes chaos test results

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Participants want to test in production immediately | Strongly emphasize safety section, share cautionary tales | Active - needs constant reinforcement |
| Confusion between failure types (Tool vs External) | Use clear examples, reference categorization table | Active - address in Q&A |
| Overwhelming number of potential failures | Focus on top 5 priorities first, expand later | Active - emphasize in Segment 2 |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- Ask: "Who can name the six elements of a chaos experiment?" (after Segment 3)
- Observable behavior indicating understanding: Participants asking about specific failure scenarios in their systems
- Observable behavior indicating confusion: Generic questions about "testing" rather than specific failure modes

### Summative Assessment (End of Session)

**Exercise Quality Indicators:**
- Exercise 1.1: Look for categorized failures, likelihood/impact ratings, priority matrix
- Exercise 1.2: Look for all 6 experiment elements, specific hypotheses, clear success criteria
- Exercise 1.3: Look for actual results documented, expected vs actual comparison, issues identified

**Common Issues to Flag:**
- Vague hypotheses ("system will handle failure") - needs specificity
- Missing rollback plans - safety concern
- No actual test execution in 1.3 - hands-on practice is essential

### Connecting to Capstone

**Capstone Relevance:**
The module capstone is a Reliability Engineering Report. This session's work contributes:
- Failure mode catalog becomes "Chaos Testing Summary" section
- Chaos experiments become "Tests Conducted" table
- Test results become "Key Findings" and "Critical Issues Resolved"

Session 2 will add reliability patterns and self-healing implementation to complete the report.

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Quick poll: "Which segment was most valuable?" (helps identify what resonates)
- Monitor support channel questions to identify confusion points

**Improvement Log:**

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| | | | |

### Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial guide created for Module 2 Session 1 | |

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Break it in testing so it doesn't break in production"
2. "All six experiment elements are required - hypothesis, steady state, injection, observation, rollback, success criteria"
3. "Safety is not optional - always have rollback ready before injecting failures"

### If You Only Have Time For One Thing

Emphasize the chaos engineering cycle (define steady state → hypothesize → inject → observe → fix → repeat). This is the core methodology that everything else builds on.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Chaos Engineering | Fire drill - practice failure scenarios before real emergency | Opening hook |
| Kill Switch | Emergency stop button - immediate safety control | Safety segment |
| Failure Mode Catalog | Threat model / risk register | When explaining systematic approach |
| Chaos Testing | Stress-testing a bridge before opening to traffic | When addressing "seems like overkill" objection |

---

**End of Instructor Guide - Session 1**
