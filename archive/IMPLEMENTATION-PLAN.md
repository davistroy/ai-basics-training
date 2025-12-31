# Implementation Plan: Presentation Content Integration

**Date:** December 31, 2024
**Status:** DRAFT - Awaiting Review
**Scope:** Integrate 8 priority items from presentation.md into curriculum

---

## Executive Summary

This plan details how to integrate high and medium priority concepts from the Agent Memory Meta-Framework presentation into Blocks 2 and 3 of the AI training curriculum. The existing 3-block × 8-week structure remains intact; changes occur within individual week content.

**Total estimated edits:** 12 targeted insertions across 6 weeks

---

## Items to Integrate

### High Priority (4 items)
| # | Item | Source Slides | Target Block/Week |
|---|------|---------------|-------------------|
| 1 | Two-Agent Pattern (Setup + Worker) | Slides 13-14 | Block 3, Weeks 1-2 |
| 2 | Micro-Agent Pattern | Slides 6, 10 | Block 2, Week 2 |
| 3 | Three Pillars of Domain Memory | Slides 9-12 | Block 2, Week 3 |
| 4 | 12-Factor Agent Principles | Slide 15 | Block 3, Week 3 |

### Medium Priority (4 items)
| # | Item | Source Slides | Target Block/Week |
|---|------|---------------|-------------------|
| 5 | Context Architecture - Four Tiers | Slide 18 | Block 3, Week 4 |
| 6 | Observability Requirements | Slide 25 | Block 3, Week 6 |
| 7 | Context Window Trap | Slide 5 | Block 2, Week 4 |
| 8 | Error Handling Patterns (Enhanced) | Slide 24 | Block 2, Week 5 or Block 3, Week 2 |

---

## Detailed Implementation Plan

---

### ITEM 1: Two-Agent Pattern (Setup + Worker)

**Priority:** HIGH
**Target:** Block 3, Weeks 1-2 (Building Reliable Agents)
**Files to modify:** `block-3.md`

#### Rationale
This is THE core architectural pattern for reliable agents. It should be introduced early in Block 3 as the foundational architecture, not just one pattern among many.

#### Current State (Block 3, Week 1)
- Segment 2: "Agents vs. Workflows - The Critical Distinction" (12 min)
- Segment 3: "Agent Architecture Components" (13 min)

#### Proposed Changes

**Week 1, Segment 3 - RESTRUCTURE (13 min → 15 min)**

Replace generic "Agent Architecture Components" with:

```markdown
**Segment 3: The Two-Agent Architecture Pattern (15 min)**

- **The fundamental insight:**
  - Stop trying to give agents memory
  - Build systems where amnesiacs can work effectively

- **Why single agents fail on multi-session tasks:**
  - No memory between sessions
  - Different interpretations of "done"
  - Repeated failed attempts
  - Context window pollution

- **The Two-Agent Pattern:**
  ```
  SETUP AGENT (runs once)
  - Takes human request
  - Creates structured records
  - Defines goals, procedures, success criteria
  - Then stops

  WORKER AGENT (runs repeatedly, stateless)
  - Reads current state from records
  - Picks ONE incomplete task
  - Does work, validates, updates records
  - Stops

  → Next worker starts fresh, reads updated state, continues
  ```

- **The Daily Contractor Analogy:**
  - Each contractor is still an amnesiac
  - But the PROJECT has memory
  - The system has memory through structured records

- **For your capstone:** Consider this pattern for complex multi-step tasks
```

**Week 2, Segment 1 - ADD (new 8-min segment, adjust others)**

Add new segment before "The Agent Execution Loop":

```markdown
**Segment 1: Domain Memory - What Makes Agents Reliable (8 min)**

- **The Three Pillars of Domain Memory:**

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

- **Why this matters for your agent:**
  - Your agent design document (from Week 1) becomes the Setup Agent output
  - Your execution logs become Progress Records
  - Your error handling becomes Operating Procedures
```

**Adjust time allocation:**
- Week 2 Segment 1 (new): 8 min
- Week 2 Segment 2 (was Segment 1): 10 min → 8 min (minor trim)
- Total still 45 min

#### Exercise Updates

**Week 1, Exercise 1.2 - ENHANCE**

Add to Agent Design Document template:

```markdown
## Domain Memory Design

### Goals (Testable Success Criteria)
1. [Criterion with specific test]
2. [Criterion with specific test]
3. [Criterion with specific test]

### Progress Records Structure
- What will be logged after each execution?
- How will failures be recorded?
- What state persists between sessions?

### Operating Procedures
- Validation process: [How to verify success]
- Escalation triggers: [When to stop and get help]
- Quality standards: [What "good" looks like]
```

---

### ITEM 2: Micro-Agent Pattern

**Priority:** HIGH
**Target:** Block 2, Week 2 (Building Your First Workflow)
**Files to modify:** `block-2.md`

#### Rationale
Critical framing for workflow scope. Prevents participants from building overly ambitious workflows that fail.

#### Current State (Block 2, Week 2)
- Segment 1: "Workflow Design Principles" (10 min)

#### Proposed Changes

**Week 2, Segment 1 - EXPAND (10 min → 12 min)**

Add to "Workflow Design Principles" segment:

```markdown
**The Micro-Agent Pattern:**

- **What's actually working in production:**
  - NOT autonomous agents running indefinitely
  - Small, focused agents: 3-20 steps
  - Embedded within larger deterministic workflows

- **The pattern:**
  ```
  Traditional DAG:     Step A → Step B → Step C → Step D
                       (all deterministic, all predefined)

  Micro-Agent Pattern: [Deterministic] → [AI: 5-10 steps] → [Deterministic]
                       (flexibility where needed, predictability elsewhere)
  ```

- **Why 3-20 steps?**
  - Bounds the context window
  - Limits scope of failures
  - Easier to debug
  - Research shows agents degrade after 10-20 turns

- **The 90% reality check:**
  - A 90% success rate sounds good
  - But would you use a web app that crashed 10% of the time?
  - Production means reliability, not impressive demos

- **For your workflow:** Think "one thing done well"
```

**Reduce Segment 2 from 20 min to 18 min** (slight trim) to maintain 45 min total.

---

### ITEM 3: Three Pillars of Domain Memory

**Priority:** HIGH
**Target:** Block 2, Week 3 (Quality Systems + Template Workflows)
**Files to modify:** `block-2.md`

#### Rationale
Frames quality systems as "Operating Procedures" - one of the three pillars. Creates conceptual bridge to Block 3.

#### Current State (Block 2, Week 3)
- Segment 1: "Quality in Automated Workflows" (10 min)

#### Proposed Changes

**Week 3, Segment 1 - ENHANCE (10 min → 12 min)**

Add to beginning of "Quality in Automated Workflows":

```markdown
**Framing: Quality as Domain Memory**

- **The Three Pillars (preview of Block 3):**
  1. **Explicit Goals** → Your success criteria
  2. **Progress Records** → Your execution logs
  3. **Operating Procedures** → Your quality system!

- **Quality systems ARE operating procedures:**
  - Pre-generation checks = input validation procedures
  - Post-generation evaluation = output verification procedures
  - Human review triggers = escalation procedures

- **Why this matters:**
  - Consistent behavior across all executions
  - Predictable quality without human variance
  - Foundation for autonomous agents (Block 3)
```

**Reduce Segment 2 from 12 min to 10 min** to maintain 45 min total.

---

### ITEM 4: 12-Factor Agent Principles

**Priority:** HIGH
**Target:** Block 3, Week 3 (MCP Deep Dive)
**Files to modify:** `block-3.md`

#### Rationale
Provides operational principles that distinguish production agents from demos. Natural fit with MCP deep dive (tools integration).

#### Current State (Block 3, Week 3)
- Segment 4: "Security and Best Practices" (9 min)

#### Proposed Changes

**Week 3, Segment 4 - RESTRUCTURE (9 min → 11 min)**

Rename to "Production Principles + Security" and add:

```markdown
**Segment 4: Production Principles + Security (11 min)**

**The 12-Factor Agent Principles (Key Highlights):**

Production agents follow operational principles:

1. **Own Your Prompts** - Treat prompts as first-class code, not framework magic
2. **Own Your Context Window** - Curate ruthlessly; context is your competitive advantage
3. **Tools Are Structured Outputs** - LLM emits JSON; YOUR code decides what to do
4. **Small, Focused Agents** - 3-20 step workflows; smaller = better performance
5. **Stateless Reducer** - Think `(state, event) → state`; enables testing and replay

**What this means for your agent:**
- You control the prompts (not hidden in a framework)
- You decide what goes in context (not automatic accumulation)
- You handle tool results (not black-box execution)
- You keep scope bounded (not "do everything")
- You can replay any decision (not mystery behavior)

**Security Principles:**
[Keep existing security content]
```

**Reduce Segment 1 from 12 min to 10 min** to maintain 45 min total.

---

### ITEM 5: Context Architecture - Four Tiers

**Priority:** MEDIUM
**Target:** Block 3, Week 4 (Multi-Step Agents)
**Files to modify:** `block-3.md`

#### Rationale
Critical for understanding state management in multi-step agents. Directly relevant to Week 4's focus on state.

#### Current State (Block 3, Week 4)
- Segment 2: "State Management Across Steps" (12 min)

#### Proposed Changes

**Week 4, Segment 2 - ENHANCE (12 min → 14 min)**

Add to "State Management Across Steps":

```markdown
**Context Architecture - The Four Tiers:**

Not everything belongs in active context:

| Tier | What | Example | Loading |
|------|------|---------|---------|
| **Tier 1: Working Context** | Active now | Current prompt, immediate task | Always loaded |
| **Tier 2: Session State** | This conversation | Structured event stream | Filtered as needed |
| **Tier 3: Persistent Memory** | Across sessions | Progress records, learnings | Retrieved on-demand |
| **Tier 4: Artifacts** | Large data | Files, databases | Referenced, not pasted |

**The Attention Budget:**
- Context is a finite resource
- Find the SMALLEST set of HIGH-SIGNAL tokens
- More context often makes performance WORSE (research-backed)
- Progressive disclosure over pre-loading

**For your multi-step agent:**
- Tier 1: Current step instructions only
- Tier 2: Step results and running summary
- Tier 3: Checkpoint files
- Tier 4: Full documents referenced by path
```

**Reduce Segment 1 from 12 min to 10 min** to maintain 45 min total.

---

### ITEM 6: Observability Requirements

**Priority:** MEDIUM
**Target:** Block 3, Week 6 (Optimization & Monitoring)
**Files to modify:** `block-3.md`

#### Rationale
Strengthens the existing monitoring content with specific production-readiness questions.

#### Current State (Block 3, Week 6)
- Segment 2: "Performance Dashboards" (12 min)

#### Proposed Changes

**Week 6, Segment 2 - ENHANCE (12 min → 13 min)**

Add to "Performance Dashboards" after dashboard design:

```markdown
**Observability Litmus Test:**

Can you answer these questions about your agent system?

- ✓ What's in the context right now?
- ✓ Where did each piece come from?
- ✓ Why was this included?
- ✓ What was available but excluded?
- ✓ Can you replay any decision with exact context state?

**Without observability:**
- Debugging is guesswork
- Failures are mysterious
- Trust is impossible

**The Law of Observability:**
If you can't see it, you can't fix it. If you can't fix it, you can't trust it.

**Your dashboard must enable:**
- Context inspection at any step
- Decision tracing (what did agent see when it decided X?)
- Replay capability for debugging
```

**Reduce Segment 3 from 12 min to 11 min** to maintain 45 min total.

---

### ITEM 7: Context Window Trap

**Priority:** MEDIUM
**Target:** Block 2, Week 4 (Workflow Optimization)
**Files to modify:** `block-2.md`

#### Rationale
Explains WHY optimization matters. Sets up the principle before teaching techniques.

#### Current State (Block 2, Week 4)
- Segment 2: "Cost Optimization Strategies" (15 min)

#### Proposed Changes

**Week 4, Segment 2 - ADD FRAMING (15 min → 16 min)**

Add to beginning of "Cost Optimization Strategies":

```markdown
**The Context Window Trap:**

**Common assumption:** "Bigger context windows = better performance"

**The research reality:**
- "Lost in the Middle" study: Models ignore middle of long inputs
- Performance degrades as input length increases
- Complete histories often perform WORSE than curated excerpts

**The counterintuitive principle:**
More context makes things WORSE, not better.

**Why this matters for workflow optimization:**
- Don't dump entire conversation histories
- Summarize large inputs before AI processing
- Pass only what's needed for THIS step
- Every token competes for attention

**Token Reduction = Better Performance AND Lower Cost**
```

**Reduce Segment 1 from 10 min to 9 min** to maintain 45 min total.

---

### ITEM 8: Error Handling Patterns (Enhanced)

**Priority:** MEDIUM
**Target:** Block 3, Week 2 (Building Reliable Agents)
**Files to modify:** `block-3.md`

#### Rationale
Enhances existing error handling with circuit breaker pattern and the "3 failures, escalate" principle.

#### Current State (Block 3, Week 2)
- Segment 2: "Error Handling for Agents" (12 min)

#### Proposed Changes

**Week 2, Segment 2 - ENHANCE (12 min → 13 min)**

Add to "Error Handling for Agents":

```markdown
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
```

**Reduce Segment 4 from 8 min to 7 min** to maintain 45 min total.

---

## Implementation Sequence

### Phase 1: Block 2 Updates (Files: `block-2.md`)

| Order | Item | Week | Estimated Edit Time |
|-------|------|------|---------------------|
| 1 | Micro-Agent Pattern | Week 2 | 20 min |
| 2 | Three Pillars | Week 3 | 15 min |
| 3 | Context Window Trap | Week 4 | 15 min |

### Phase 2: Block 3 Updates (Files: `block-3.md`)

| Order | Item | Week | Estimated Edit Time |
|-------|------|------|---------------------|
| 4 | Two-Agent Pattern | Week 1 | 30 min |
| 5 | Domain Memory + Enhanced Error Handling | Week 2 | 25 min |
| 6 | 12-Factor Principles | Week 3 | 20 min |
| 7 | Four Tiers Context | Week 4 | 15 min |
| 8 | Observability | Week 6 | 15 min |

**Total estimated implementation time:** ~2.5 hours

---

## Time Budget Impact

### Block 2 Workshop Adjustments

| Week | Segment | Current | After | Change |
|------|---------|---------|-------|--------|
| Week 2 | Seg 1 | 10 min | 12 min | +2 min |
| Week 2 | Seg 2 | 20 min | 18 min | -2 min |
| Week 3 | Seg 1 | 10 min | 12 min | +2 min |
| Week 3 | Seg 2 | 12 min | 10 min | -2 min |
| Week 4 | Seg 1 | 10 min | 9 min | -1 min |
| Week 4 | Seg 2 | 15 min | 16 min | +1 min |

**Net change:** 0 min (all weeks still 45 min)

### Block 3 Workshop Adjustments

| Week | Segment | Current | After | Change |
|------|---------|---------|-------|--------|
| Week 1 | Seg 3 | 13 min | 15 min | +2 min |
| Week 1 | Seg 4 | 10 min | 8 min | -2 min |
| Week 2 | Seg 1 (new) | - | 8 min | +8 min |
| Week 2 | Seg 2 (was 1) | 10 min | 8 min | -2 min |
| Week 2 | Seg 3 (was 2) | 12 min | 13 min | +1 min |
| Week 2 | Seg 4 (was 3) | 15 min | 9 min | -6 min |
| Week 2 | Seg 5 (was 4) | 8 min | 7 min | -1 min |
| Week 3 | Seg 1 | 12 min | 10 min | -2 min |
| Week 3 | Seg 4 | 9 min | 11 min | +2 min |
| Week 4 | Seg 1 | 12 min | 10 min | -2 min |
| Week 4 | Seg 2 | 12 min | 14 min | +2 min |
| Week 6 | Seg 2 | 12 min | 13 min | +1 min |
| Week 6 | Seg 3 | 12 min | 11 min | -1 min |

**Net change:** 0 min (all weeks still 45 min)

---

## Exercise Updates Summary

| Block | Week | Exercise | Change |
|-------|------|----------|--------|
| Block 3 | Week 1 | 1.2 Agent Design | Add Domain Memory section to template |
| Block 3 | Week 2 | 2.2 Error Handling | Add circuit breaker pattern |

**Note:** Most conceptual additions go into workshop content, not exercises, to avoid increasing homework load.

---

## Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Segment timing runs over | Medium | Low | Built-in flex via minor trims; practice timing |
| Concepts too advanced for stage | Low | Medium | Framing as "preview" in Block 2; full depth in Block 3 |
| Too much new terminology | Low | Medium | Reuse existing curriculum terminology where possible |

---

## Quality Assurance

### Before Implementation
- [ ] User approves this plan
- [ ] Confirm all source slide numbers are correct

### During Implementation
- [ ] Maintain consistent terminology across blocks
- [ ] Preserve existing appendix references
- [ ] Keep all entry/exit criteria valid

### After Implementation
- [ ] Read through each modified week for flow
- [ ] Verify all time segments sum to 45 min
- [ ] Check no orphaned cross-references

---

## Approval Checklist

**Please confirm:**
- [ ] High priority items (1-4) approved for implementation
- [ ] Medium priority items (5-8) approved for implementation
- [ ] Time rebalancing approach acceptable
- [ ] Exercise update scope acceptable
- [ ] Ready to proceed with implementation

---

**END OF IMPLEMENTATION PLAN**
