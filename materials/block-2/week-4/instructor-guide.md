# **INSTRUCTOR GUIDE: BLOCK 2 WEEK 4**
## **Workflow Optimization**

**Block:** 2: AI Workflow Engineering
**Week:** 4 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Analyzing performance data and optimizing workflows for cost, speed, and quality |
| **Difficulty Level** | Medium |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Yes - Performance analysis walkthrough |
| **Tech Setup Needed** | Sample execution log data, pricing reference |
| **Common Challenges** | Lack of logged data, unrealistic optimization expectations |

---

## Navigation

**Block Navigation:** [← Week 3 Instructor Guide](../week-3/instructor-guide.md) | **Week 4** | [Week 5 Instructor Guide →](../week-5/instructor-guide.md)

**Related Materials:**
- [Week 4 Presentation](presentation.md)
- [Week 4 Participant Guide](participant-guide.md)
- [Block 2 Main Document](../block-2.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 4 materials | ☐ |
| Prepare sample data | Create example execution log for analysis | ☐ |
| Update pricing | Verify current AI model pricing is accurate | ☐ |
| Check resources | Verify optimization documentation links | ☐ |
| Review Week 3 submissions | Check who has two working workflows | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load analysis demo | Have sample data ready for walkthrough | ☐ |
| Prepare calculations | Have cost/time calculations ready | ☐ |
| Review participant progress | Identify who has sufficient logged data | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, sample data, pricing pages | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Load spreadsheet | Sample execution log visible | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Week 3 recap, data check | Quick status |
| 0:03 | 9 min | Segment 1 | Analyzing Workflow Performance | Data review |
| 0:12 | 16 min | Segment 2 | Cost Optimization + Context Window Trap | Critical concept |
| 0:28 | 10 min | Segment 3 | Quality Gate Refinement | Calibration |
| 0:38 | 4 min | Segment 4 | Speed Optimization | Quick wins |
| 0:42 | 3 min | Closing | Homework, Week 5 preview | Don't skip |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Segment 1: Reference analysis framework, don't demo fully
- Segment 4: Brief overview, detailed content in participant guide

**If Running Ahead:**
- Segment 2: More discussion on pricing and cost calculations
- Segment 3: Walk through threshold calibration example

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:12 | Shorten analysis walkthrough |
| End Segment 2 | 0:28 | Context window trap is critical - don't skip |
| Start Closing | 0:42 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants to the midpoint of Block 2
2. Quick check on workflow status and logged data
3. Frame optimization as data-driven improvement

**Opening Script:**
> "Welcome to Week 4 - we're at the midpoint of Block 2! Today is about optimization. You've built workflows, added quality checks, and logged executions. Now we use that data to make everything better. Quick check: who has at least 10 logged executions across their workflows? [Count] Good. Those logs are your optimization goldmine."

**Engagement Opportunity:**
> "What's the one thing about your workflows that you'd most like to improve? Speed? Cost? Quality?"

---

### Segment 1: Analyzing Workflow Performance (9 minutes)

**Learning Objective:** Extract insights from execution log data

**Slides:** 4-6

#### Content Delivery

**Key Point 1: Review Your Execution Logs**
- Main message: Data tells you what to optimize
- Key metrics: Average execution time, success rate, quality score distribution, cost per execution
- Example: "If 80% of your executions take 8 seconds but 20% take 30 seconds, investigate why"

**Key Point 2: Identify Patterns**
- Which steps take longest?
- Where do failures occur?
- What triggers low quality scores?
- Pattern recognition drives targeted optimization

**Key Point 3: Analysis Framework**
- Present the performance analysis template
- Show how to calculate key metrics from raw data
- Emphasize: "Measure before improving"

#### Facilitation Notes

**Watch For:**
- Participants who didn't log enough data
- Confusion about what metrics mean

**If Limited Data:**
> "Even 5-10 executions give you a starting point. Look for obvious patterns first. More data enables more nuanced optimization."

**Transition to Segment 2:**
> "The biggest optimization opportunity for most people is cost. But it's not what you think..."

---

### Segment 2: Cost Optimization + The Context Window Trap (16 minutes)

**Learning Objective:** Understand context window dynamics and cost optimization strategies

**Slides:** 7-13

#### Content Delivery

**Key Point 1: The Context Window Trap (CRITICAL)**
- Main message: More context makes things WORSE, not better
- Research: "Lost in the Middle" - models ignore middle of long inputs
- Common mistake: "I'll just include everything so the AI has all the information"
- Reality: Complete histories often perform WORSE than curated excerpts

**Key Point 2: Why This Matters**
- Every token competes for attention
- Performance degrades as input length increases
- Token reduction = better performance AND lower cost
- This is counterintuitive but well-documented

**Key Point 3: Token Reduction Techniques**
- Shorter context windows (pass only what's needed for THIS step)
- Summarize large inputs before AI processing
- Use smaller models for simple tasks
- Cache repeated operations

**Key Point 4: Current Pricing Reference**
- Walk through current pricing table
- Show cost calculation example
- Typical consulting workflow costs
- The insight: Token costs are rarely the bottleneck - time savings dwarf AI costs

#### Demo/Walkthrough

**Demo Duration:** 5 minutes

**Content:**
1. Show sample prompt with excessive context
2. Calculate token count and cost
3. Show reduced prompt with same output quality
4. Compare costs
5. Emphasize: "We got the same quality with 60% fewer tokens"

**Demo Talking Points:**
> "Look at this prompt - it includes the entire conversation history. That's 3,000 tokens. But the AI only needs the last exchange and the style guide. That's 800 tokens."
> "Same output quality. 70% cost reduction. And actually BETTER performance because the AI focuses on what matters."

#### Facilitation Notes

**This is the most counterintuitive concept in the session:**
Many participants assume more context = better results. The research says otherwise. Emphasize this multiple times.

**Transition to Segment 3:**
> "Cost is one lever. Quality is another. Let's refine your quality thresholds."

---

### Segment 3: Quality Gate Refinement (10 minutes)

**Learning Objective:** Use data to calibrate quality thresholds

**Slides:** 14-17

#### Content Delivery

**Key Point 1: Using Data to Improve Thresholds**
- What score actually predicts usable output?
- Are you over-rejecting good content?
- Are bad outputs slipping through?
- Look at your actual score distribution

**Key Point 2: Adjusting Evaluation Criteria**
- Weight criteria by importance
- Add specific checks for common issues
- Create fast-path for simple cases (if input is X, use simpler evaluation)

**Key Point 3: Human-in-the-Loop Optimization**
- When to require human review
- Reducing review burden over time
- Learning from corrections

#### Facilitation Notes

**Watch For:**
- Participants frustrated that thresholds don't match intuition
- Over-engineering of evaluation criteria

**If Asked About Threshold Frustration:**
> "Calibration is iterative. Start conservative (reject more), then loosen based on data. It's easier to loosen than to tighten."

---

### Segment 4: Speed Optimization (4 minutes)

**Learning Objective:** Identify quick wins for execution speed

**Slides:** 18-19

#### Content Delivery

**Key Point 1: Parallel Processing**
- Run independent steps simultaneously
- Example: If you're fetching from two sources, fetch both at once
- Platform-specific implementation

**Key Point 2: Caching Strategies**
- Cache `style.json` and reference data
- Don't re-fetch static content every execution
- Platform-specific caching options

**Key Point 3: Model Selection for Speed**
- Faster models for simpler tasks
- Reserve powerful models for complex generation
- Quality check can use cheaper/faster model

---

### Closing (3 minutes)

**Slides:** 20-22

**Script:**
> "Your homework this week is analysis-focused - about 60 minutes total.
>
> Exercise 4.1 - 20 minutes - analyze your execution data and document findings.
>
> Exercise 4.2 - 25 minutes - implement at least 3 optimizations based on your analysis.
>
> Exercise 4.3 - 15 minutes - measure the before/after impact.
>
> By end of week, you should see measurable improvement in at least one area: cost, speed, or quality."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: How much improvement should I expect from optimization?**
A: Varies widely. 20-50% improvement in one metric is typical. Sometimes more. The goal is measurable improvement, not a specific percentage.

**Q: Should I optimize for cost or speed first?**
A: Usually cost, because context window reduction improves BOTH cost and quality. Speed optimizations are secondary.

**Q: What if my optimization makes quality worse?**
A: Roll back. Optimization should improve or maintain quality, not sacrifice it. If quality drops, the optimization isn't worth it.

### Technical Questions

**Q: How do I measure token counts in my workflow?**
A: Most AI APIs return token usage in the response. Log it. Or use a token counter tool for estimation.

**Q: Can I use different models for different steps?**
A: Absolutely. Quality checks can use cheaper models. Simple transformations can use fast models. Match model to task.

### Scope Questions

**Q: When do we get to MCP?**
A: Next week! Week 5 introduces MCP configuration. This week we optimize what we have before adding new capabilities.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Pricing data outdated | Note it's approximate | Reference provider websites |
| Demo calculation wrong | Recalculate live | Show concept, fix numbers later |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Insufficient logged data | "I only have 3 executions" | Use what you have, note need for more data |
| Overwhelmed by metrics | "Too many things to track" | Focus on one metric (cost or time) first |
| Optimization not improving | "Numbers aren't better" | Check measurement method, ensure apples-to-apples |

---

## Post-Session Tasks

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording | ☐ |
| Share updated pricing reference if needed | ☐ |
| Answer optimization strategy questions | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review optimization results submitted | ☐ |
| Identify participants showing good improvement | ☐ |
| Note common optimization challenges for future | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 4.1 | `performance-analysis.md` | GitHub |
| 4.2 | Optimized workflows + documentation | Platform + GitHub |
| 4.3 | `optimization-results.md` | GitHub |

### Progress Check Approach

**How to Verify Completion:**
- Check for analysis document in repo
- Look for before/after comparison in results
- Verify at least one measurable improvement

**Intervention Thresholds:**
- No analysis: Needs support extracting insights from data
- No improvement: May need different optimization strategy
- Missing comparison: Follow up on measurement approach

---

## Week-Specific Notes

### What Makes This Week Unique

- Midpoint of Block 2 - good checkpoint for progress
- Data-driven rather than building new features
- Context window trap is counterintuitive - needs emphasis
- Sets up optimized foundation for MCP integration

### Dependencies

**Builds On:**
- Week 2-3: Working workflows with logging
- Quality check data from Week 3

**Sets Up:**
- Week 5-6: MCP integration on optimized workflows
- Capstone: Performance documentation requirement

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "More context makes things WORSE, not better"
2. "Token costs are rarely the bottleneck - time savings dwarf AI costs"
3. "Measure before improving, measure after to verify"

### If You Only Have Time For One Thing

The context window trap - this counterintuitive concept changes how participants think about prompt design.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Context window trap | "A packed suitcase where you can't find anything" | Explaining why more isn't better |
| Cost optimization | "Paying for express shipping on a letter" | Explaining proportionality of AI costs |
| Threshold calibration | "Adjusting the thermostat" | Explaining iterative refinement |

---

**Navigation:** [← Week 3 Instructor Guide](../week-3/instructor-guide.md) | **Week 4** | [Week 5 Instructor Guide →](../week-5/instructor-guide.md)
