# **BLOCK 2 WEEK 4: Workflow Optimization**

**Block:** 2: AI Workflow Engineering
**Week:** 4 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** [← Week 3](../week-3/participant-guide.md) | **Week 4** | [Week 5 →](../week-5/participant-guide.md)

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
| 1 | Analyze workflow execution data to identify optimization opportunities | Exercise 4.1 |
| 2 | Apply cost optimization techniques including context window management | Exercise 4.2 |
| 3 | Calibrate quality thresholds based on actual execution results | Exercise 4.2 |
| 4 | Measure and document before/after optimization impact | Exercise 4.3 |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Two working workflows with quality checks
- [ ] 10+ logged executions across workflows
- [ ] JSON data structures implemented
- [ ] Quality routing functional

**Not ready?** Complete Week 3 exercises or reach out in the support channel for help.

---

## Key Concepts

### Concept 1: The Context Window Trap

**Definition:**
The counterintuitive reality that adding more context to AI prompts often DECREASES performance rather than improving it.

**Why It Matters:**
This is the single most important optimization insight. Most people assume "more information = better results." Research shows the opposite is often true.

**Core Principle:**
> More context makes things WORSE, not better. Every token competes for attention.

**The Research:**
- "Lost in the Middle" study: AI models pay attention to the beginning and end of prompts, but often ignore or de-prioritize content in the middle
- Performance degrades as input length increases
- Complete conversation histories often perform WORSE than curated excerpts

**Common Mistake:**
```
Wrong approach:
"I'll include the entire conversation history, all the reference documents,
and every piece of context just in case the AI needs it."

Right approach:
"What is the minimum context needed for THIS specific step to succeed?
Only include that."
```

**The Dual Benefit:**
Token reduction improves BOTH:
- Performance (AI focuses on what matters)
- Cost (fewer tokens = lower cost)

---

### Concept 2: Cost Optimization Strategies

**Definition:**
Techniques for reducing the cost of AI workflow executions while maintaining or improving output quality.

**Why It Matters:**
While AI costs are often modest compared to time savings, unnecessary spending adds up. Smart optimization means paying for what you need, not what you don't.

**Token Reduction Techniques:**

| Technique | How It Works | Typical Savings |
|-----------|--------------|-----------------|
| Shorter prompts | Remove unnecessary context | 20-50% |
| Summarize first | Compress long inputs | 40-70% |
| Model selection | Right-size for task | 50-90% |
| Caching | Don't re-fetch static content | Variable |

**Current Pricing Reference (Early 2025):**

| Model | Input (per 1M tokens) | Output (per 1M tokens) | Best For |
|-------|----------------------|------------------------|----------|
| Claude 3.5 Sonnet | ~$3.00 | ~$15.00 | Complex generation |
| Claude 3 Haiku | ~$0.25 | ~$1.25 | Simple tasks |
| GPT-4o | ~$2.50 | ~$10.00 | General purpose |
| GPT-4o-mini | ~$0.15 | ~$0.60 | High-volume simple |

*Prices change frequently - verify current rates at provider websites*

**Typical Workflow Costs:**
- Simple email: ~500 tokens = $0.001-0.01
- Proposal section: ~3,500 tokens = $0.01-0.05
- Complex analysis: ~8,000 tokens = $0.05-0.15
- 100 executions/month: $1-15 typical

**Key Insight:**
> Token costs are rarely the bottleneck. Time savings dwarf AI costs. A $0.05 workflow that saves 30 minutes is extremely valuable.

---

### Concept 3: Quality Gate Calibration

**Definition:**
The process of adjusting quality evaluation thresholds based on actual execution results to achieve the right balance between accepting good output and rejecting bad output.

**Why It Matters:**
Thresholds set arbitrarily often don't match reality. Too strict means rejecting usable output. Too lenient means passing bad output.

**Calibration Process:**

1. **Collect data:** Run 20+ executions with quality scoring
2. **Review distribution:** What scores are you getting?
3. **Spot check:** Manually review outputs at each score level
4. **Adjust thresholds:** Move pass/fail line based on findings

**Score Distribution Example:**
```
5.0     : ████ (15%)     - Excellent, definitely pass
4.0-4.9 : ████████ (40%) - Good, should pass
3.0-3.9 : ████████ (35%) - Acceptable, review recommended
< 3.0   : ██ (10%)       - Poor, should fail
```

**Threshold Adjustment:**
- If good outputs are failing: Lower threshold
- If bad outputs are passing: Raise threshold
- If borderline is large: Consider adding criteria

**Calibration Tips:**
- Start conservative (reject more), loosen based on data
- Review outputs at threshold boundary
- Different deliverable types may need different thresholds

---

### Concept 4: Speed Optimization

**Definition:**
Techniques for reducing workflow execution time without sacrificing quality.

**Why It Matters:**
Faster workflows provide quicker feedback and enable higher throughput. Some optimizations also improve cost and quality.

**Speed Optimization Techniques:**

| Technique | Description | Impact |
|-----------|-------------|--------|
| **Parallel processing** | Run independent steps simultaneously | 2-5x faster |
| **Caching** | Store and reuse static content | Variable |
| **Step elimination** | Remove unnecessary steps | Proportional |
| **Model selection** | Use faster models for simple tasks | 2-10x faster |

**Parallel Processing Example:**
```
Sequential:  Fetch A (2s) → Fetch B (2s) → Process (5s) = 9s total
Parallel:    Fetch A + B (2s) → Process (5s) = 7s total
```

**Caching Candidates:**
- style.json and reference documents
- Static templates
- Frequently accessed data
- Previous execution results (where appropriate)

---

### Quick Reference: Optimization Priorities

| Priority | Focus | Typical Impact |
|----------|-------|----------------|
| 1st | Context reduction | Improves cost AND quality |
| 2nd | Model selection | Major cost savings |
| 3rd | Quality calibration | Reduces false positives/negatives |
| 4th | Speed optimization | Improves throughput |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Using execution data to optimize workflows for cost, speed, and quality.

**Key Points from Each Segment:**

**Segment 1: Analyzing Workflow Performance**
- Review execution logs for patterns
- Key metrics: execution time, success rate, quality distribution, cost
- Identify bottlenecks and failure points
- "Measure before improving"

**Segment 2: Cost Optimization + Context Window Trap**
- More context makes things WORSE, not better
- "Lost in the Middle" research shows models ignore mid-prompt content
- Token reduction improves both performance and cost
- Current pricing: modest costs, massive time savings

**Segment 3: Quality Gate Refinement**
- Calibrate thresholds based on actual data
- Adjust criteria weights for importance
- Create fast-paths for simple cases
- Learn from human review feedback

**Segment 4: Speed Optimization**
- Parallel processing for independent steps
- Cache static content
- Eliminate unnecessary steps
- Match model to task complexity

### Demo Recap

**What Was Demonstrated:**
Analysis of sample execution data with optimization recommendations.

**Key Steps:**
1. Reviewed execution log metrics
2. Calculated cost per execution
3. Identified context reduction opportunity
4. Compared before/after token counts

**Result:**
Same output quality with 60% fewer tokens (cost and quality improvement).

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 4.1 | 20 min | `performance-analysis.md` | Data analysis |
| 4.2 | 25 min | Optimized workflows + docs | Implement optimizations |
| 4.3 | 15 min | `optimization-results.md` | Measure improvement |

---

### Exercise 4.1: Performance Analysis

**Duration:** 20 minutes

**Purpose:**
Analyze your workflow execution data to identify optimization opportunities. Data-driven improvement is more effective than guessing.

**You Will Create:**
A documented analysis of your workflow performance with specific optimization recommendations.

---

#### Instructions

**Step 1: Export Your Execution Data (3 min)**

Collect your execution logs (minimum 10 executions, ideally 20+):
- From Google Sheets/Airtable logging
- Or from platform execution history
- Include both workflows if possible

**Step 2: Calculate Key Metrics (8 min)**

For each workflow, calculate:

| Metric | Workflow 1 | Workflow 2 |
|--------|------------|------------|
| Total Executions | | |
| Average Execution Time | | |
| Success Rate (%) | | |
| Average Quality Score | | |
| Human Review Rate (%) | | |
| Average Cost/Execution | | |

**Step 3: Analyze Step-by-Step Timing (4 min)**

Break down where time goes:

| Step | Avg Duration | % of Total | Bottleneck? |
|------|--------------|------------|-------------|
| Trigger | | | |
| AI Generation | | | |
| Quality Check | | | |
| Output | | | |

**Step 4: Review Quality Distribution (3 min)**

| Score Range | Count | % | Current Outcome |
|-------------|-------|---|-----------------|
| 4.5-5.0 | | | Pass |
| 4.0-4.4 | | | Pass |
| 3.5-3.9 | | | ? |
| 3.0-3.4 | | | Review |
| < 3.0 | | | Fail |

**Step 5: Identify Optimization Opportunities (2 min)**

Based on your analysis, list:
1. Top time sink
2. Top cost driver
3. Quality threshold issue (if any)
4. Potential quick wins

---

#### Deliverable Specification

**File Name:** `performance-analysis.md`

**Location:** Your Block 2 folder in GitHub repository

**Quality Criteria:**
- [ ] All key metrics calculated
- [ ] Step-by-step timing analyzed
- [ ] Quality distribution reviewed
- [ ] At least 3 optimization opportunities identified

---

#### Template

```markdown
# Workflow Performance Analysis

**Date:** [YYYY-MM-DD]
**Analysis Period:** [Start date] to [End date]
**Total Executions Analyzed:** [Number]

---

## Execution Metrics

| Metric | Workflow 1 | Workflow 2 | Target |
|--------|------------|------------|--------|
| Total Executions | | | - |
| Avg Execution Time | | | < ___s |
| Success Rate | | | > ___% |
| Avg Quality Score | | | > ___/5 |
| Human Review Rate | | | < ___% |
| Avg Cost/Execution | | | < $___ |

---

## Step-by-Step Timing

### Workflow 1: [Name]

| Step | Avg Duration | % of Total | Bottleneck? |
|------|--------------|------------|-------------|
| | | | |
| **Total** | | 100% | |

### Workflow 2: [Name]

| Step | Avg Duration | % of Total | Bottleneck? |
|------|--------------|------------|-------------|
| | | | |
| **Total** | | 100% | |

---

## Quality Score Distribution

### Workflow 1

| Score Range | Count | % | Outcome |
|-------------|-------|---|---------|
| 4.5 - 5.0 | | | |
| 4.0 - 4.4 | | | |
| 3.5 - 3.9 | | | |
| 3.0 - 3.4 | | | |
| < 3.0 | | | |

### Observations
- [Observation about quality distribution]
- [Threshold adjustment needed?]

---

## Cost Analysis

- Total cost for [X] executions: $___
- Average cost per execution: $___
- Primary cost driver: [Identify]
- Projected monthly cost at current rate: $___

---

## Issues Identified

1. **[Issue 1]:** [Description and impact]
2. **[Issue 2]:** [Description and impact]
3. **[Issue 3]:** [Description and impact]

---

## Optimization Opportunities

| Opportunity | Type | Expected Impact | Priority |
|-------------|------|-----------------|----------|
| [Opportunity 1] | Cost/Speed/Quality | [X%] improvement | High/Med/Low |
| [Opportunity 2] | | | |
| [Opportunity 3] | | | |

---

## Next Steps

1. [ ] [Specific optimization to implement]
2. [ ] [Specific optimization to implement]
3. [ ] [Specific optimization to implement]
```

---

### Exercise 4.2: Implement Optimizations

**Duration:** 25 minutes

**Purpose:**
Apply optimizations based on your analysis. Implement at least one from each category where applicable.

**You Will Create:**
Optimized versions of your workflows with documented changes.

---

#### Instructions

**Step 1: Cost Optimization (10 min)**

Pick 2 optimizations from this list:

**Option A: Reduce Prompt Length**
1. Review your generation prompt
2. Identify unnecessary context
3. Remove or summarize verbose sections
4. Target: 20%+ token reduction

**Option B: Smaller Model for Quality Check**
1. Change quality evaluation step to use cheaper model
2. Update API configuration
3. Test that evaluation quality is maintained

**Option C: Add Context Caching**
1. Identify static content fetched each execution
2. Move to cached variable
3. Reference cache instead of re-fetching

**Option D: Eliminate Unnecessary Steps**
1. Review workflow for redundant steps
2. Combine steps where possible
3. Remove steps that don't add value

**Step 2: Quality Optimization (8 min)**

Pick 1 optimization:

**Option A: Refine Thresholds**
1. Based on your quality distribution, adjust pass/fail threshold
2. Update routing logic
3. Test with known good/bad examples

**Option B: Add Specific Checks**
1. Identify common quality issues from reviews
2. Add specific criteria to evaluation prompt
3. Weight appropriately

**Option C: Improve Regeneration**
1. For failed quality checks, improve retry prompt
2. Include specific feedback from quality evaluation
3. Test regeneration success rate

**Step 3: Speed Optimization (5 min)**

Pick 1 optimization:

**Option A: Parallelize Steps**
1. Identify independent steps
2. Configure for parallel execution
3. Measure time improvement

**Option B: Use Faster Model**
1. For simple steps, switch to faster model
2. Verify quality maintained
3. Measure speed improvement

**Step 4: Document Changes (2 min)**

Update your workflow documentation with changes made.

---

#### Deliverable Specification

**Deliverables:**
1. Optimized workflows in platform
2. Updated documentation reflecting changes

**Quality Criteria:**
- [ ] At least 2 cost optimizations implemented
- [ ] At least 1 quality optimization implemented
- [ ] At least 1 speed optimization implemented
- [ ] All changes documented

---

#### Template Addition (to workflow documentation)

```markdown
## Optimization History

### [Date] - Optimization Round 1

**Cost Optimizations:**
- **Change 1:** [What you changed]
  - Before: [Old value/approach]
  - After: [New value/approach]
  - Expected impact: [X%] token reduction

- **Change 2:** [What you changed]
  - Before: [Old value/approach]
  - After: [New value/approach]
  - Expected impact: [Description]

**Quality Optimizations:**
- **Change:** [What you changed]
  - Before: Threshold at [X]
  - After: Threshold at [Y]
  - Reason: [Why this adjustment]

**Speed Optimizations:**
- **Change:** [What you changed]
  - Before: [Sequential/other]
  - After: [Parallel/other]
  - Expected impact: [X seconds saved]
```

---

### Exercise 4.3: Measure Improvement

**Duration:** 15 minutes

**Purpose:**
Quantify the impact of your optimizations. Without measurement, you can't know if optimizations actually worked.

**You Will Create:**
Before/after comparison documenting actual improvement achieved.

---

#### Instructions

**Step 1: Run Post-Optimization Tests (10 min)**

Run 5+ executions of each optimized workflow:
- Use similar inputs to pre-optimization
- Log all execution metrics
- Note any quality differences

**Step 2: Calculate Before/After Comparison (3 min)**

| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| Avg Execution Time | | | X% faster |
| Avg Cost/Execution | | | X% cheaper |
| Success Rate | | | X% better |
| Avg Quality Score | | | +/- X points |
| Human Review Rate | | | X% reduction |

**Step 3: Calculate ROI (2 min)**

```
Time Savings:
- Per execution: ___ minutes saved
- Monthly (at X executions): ___ hours saved
- Value of time (@ $___/hr): $___/month

Cost Savings:
- Per execution: $___ saved
- Monthly: $___/month

Quality Improvement:
- [Qualitative assessment]
```

---

#### Deliverable Specification

**File Name:** `optimization-results.md`

**Location:** Your Block 2 folder in GitHub repository

**Quality Criteria:**
- [ ] Before/after comparison for all key metrics
- [ ] Measurable improvement in at least one area
- [ ] ROI calculation completed
- [ ] Lessons learned documented

---

#### Template

```markdown
# Optimization Results

**Date:** [YYYY-MM-DD]
**Workflows Optimized:** [Names]
**Post-Optimization Executions:** [Number]

---

## Before vs. After Comparison

| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| Avg Execution Time | ___ s | ___ s | ___% faster |
| Avg Cost/Execution | $___ | $___ | ___% cheaper |
| Success Rate | ___% | ___% | +___% |
| Avg Quality Score | ___/5 | ___/5 | +___ points |
| Human Review Rate | ___% | ___% | -___% |

---

## ROI Calculation

### Time Savings
- Per execution: ___ minutes saved
- Monthly (at ___ executions): ___ hours saved
- Annual projection: ___ hours saved
- Value of time saved (@ $___/hr): $___/year

### Cost Savings
- Per execution: $___ saved
- Monthly: $___ saved
- Annual projection: $___ saved

### Quality Improvement
- [Description of quality improvement]
- [Impact on downstream work]

### Total Annual Value
- Time savings value: $___
- Cost savings: $___
- **Total: $___/year**

---

## Lessons Learned

1. **[Lesson 1]:** [What you learned]
2. **[Lesson 2]:** [What you learned]
3. **[Lesson 3]:** [What you learned]

---

## Further Optimization Opportunities

| Opportunity | Expected Impact | Priority for Future |
|-------------|-----------------|---------------------|
| [Opportunity] | [Impact] | [High/Med/Low] |
| | | |

---

## Notes

[Any additional observations or comments]
```

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| Performance Analysis | Document workflow metrics | Exercise 4.1 |
| Optimization History | Track changes made | Exercise 4.2 |
| Optimization Results | Measure improvement | Exercise 4.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Anthropic Pricing | Reference | [anthropic.com/pricing](https://www.anthropic.com/pricing) | Cost calculations |
| OpenAI Pricing | Reference | [openai.com/pricing](https://openai.com/pricing) | Cost calculations |
| Lost in the Middle Paper | Research | [arxiv.org/abs/2307.03172](https://arxiv.org/abs/2307.03172) | Understanding context limits |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Analyze workflow execution data | Performance analysis document complete | ☐ |
| 2 | Apply context window optimization | Prompt length reduced | ☐ |
| 3 | Calibrate quality thresholds | Threshold adjusted based on data | ☐ |
| 4 | Measure optimization impact | Before/after comparison complete | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Performance analysis | `performance-analysis.md` | GitHub | ☐ |
| Optimized workflows | N/A | Platform | ☐ |
| Optimization results | `optimization-results.md` | GitHub | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What surprised you?** Did the data show something you didn't expect about your workflows?

2. **What was your biggest win?** Which optimization had the most impact?

3. **What did the context window insight change?** How does "less is more" affect your thinking about prompts?

4. **What would you optimize next?** If you had more time, what else would you improve?

---

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Compare optimization strategies with cohort

### Common Questions This Week

**Q: I don't have enough logged data. What should I do?**
A: Run more executions now, then analyze. Even 10 executions give useful patterns. Focus on obvious issues first.

**Q: My optimization didn't improve anything. What went wrong?**
A: Check your measurement. Are you comparing apples to apples? Also, not all optimizations work for all workflows. Try a different approach.

**Q: The context window research contradicts what I thought. Is it really true?**
A: Yes. "Lost in the Middle" is well-documented. It's counterintuitive but consistent across models. Pass only what's needed for the specific step.

---

## Looking Ahead

### Next Week Preview: Week 5 - MCP Integration Basics

**Focus:**
Configuring Model Context Protocol to connect your workflows to files, GitHub, and other tools.

**How It Builds on This Week:**
You'll integrate MCP with your optimized, quality-checked workflows.

**To Prepare:**
- [ ] Complete all Week 4 exercises
- [ ] Have optimized workflows running
- [ ] Review MCP server analysis from Week 1
- [ ] Ensure Claude Desktop is installed

---

## Glossary

| Term | Definition |
|------|------------|
| Context Window | The maximum amount of text/tokens an AI model can process at once |
| Token | A unit of text (~4 characters or 0.75 words) used for pricing and limits |
| Calibration | Adjusting thresholds based on actual results |
| Parallel Processing | Running multiple operations simultaneously |
| Caching | Storing data for reuse instead of fetching repeatedly |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [← Week 3](../week-3/participant-guide.md) | **Week 4** | [Week 5 →](../week-5/participant-guide.md)
