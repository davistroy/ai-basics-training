# Week 4: Workflow Optimization

**Block:** 2 - AI Workflow Engineering
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Two working workflows with quality checks
- [ ] 10+ logged executions across workflows
- [ ] JSON data structures implemented
- [ ] Quality routing functional

## Exit Criteria

- [ ] Cost optimization applied to workflows
- [ ] Quality gates refined based on data
- [ ] Performance bottlenecks identified and addressed
- [ ] A/B testing concept understood
- [ ] Workflow efficiency improved by 20%+

---

## Workshop Content (45 minutes)

### Segment 1: Analyzing Workflow Performance (9 min)

**Review your execution logs:**
- Average execution time
- Success rate
- Quality score distribution
- Cost per execution

**Identify patterns:**
- Which steps take longest?
- Where do failures occur?
- What triggers low quality scores?

**Live analysis:** Walk through sample execution data

### Segment 2: Cost Optimization Strategies (16 min)

**The Context Window Trap:**

- **Common assumption:** "Bigger context windows = better performance"
- **The research reality:**
  - "Lost in the Middle" study: Models ignore middle of long inputs
  - Performance degrades as input length increases
  - Complete histories often perform WORSE than curated excerpts
- **The counterintuitive principle:** More context makes things WORSE, not better
- **Why this matters for workflow optimization:**
  - Don't dump entire conversation histories
  - Summarize large inputs before AI processing
  - Pass only what's needed for THIS step
  - Every token competes for attention
- **Token Reduction = Better Performance AND Lower Cost**

**Token reduction techniques:**
- Shorter context windows (pass only what's needed)
- Summarize large inputs before AI processing
- Use smaller models for simple tasks
- Cache repeated operations

**Platform cost optimization:**
- Batch executions where possible
- Avoid unnecessary steps
- Use conditional logic to skip irrelevant paths

**Cost tracking implementation:**

```json
{
  "cost_breakdown": {
    "ai_tokens": {"input": 1000, "output": 500, "cost": 0.03},
    "platform_operations": 5,
    "platform_cost": 0.01,
    "total": 0.04
  }
}
```

**Current Token Pricing Reference (Early 2025):**

| Model | Input (per 1M tokens) | Output (per 1M tokens) | Best For |
|-------|----------------------|------------------------|----------|
| Claude 3.5 Sonnet | ~$3.00 | ~$15.00 | Complex generation, analysis |
| Claude 3 Haiku | ~$0.25 | ~$1.25 | Simple tasks, classification |
| GPT-4o | ~$2.50 | ~$10.00 | General purpose |
| GPT-4o-mini | ~$0.15 | ~$0.60 | High-volume, simple tasks |

*Prices change frequently—verify current rates at provider websites*

**Typical consulting workflow costs:**
- Simple email generation: ~500 tokens → $0.001-0.01
- Proposal section: ~2,000 input + 1,500 output → $0.01-0.05
- Complex analysis: ~5,000 input + 3,000 output → $0.05-0.15
- 100 executions/month: $1-15/month (varies by complexity)

**The insight:** Token costs are rarely the bottleneck—time savings dwarf AI costs

### Segment 3: Quality Gate Refinement (12 min)

**Using data to improve thresholds:**
- What score actually predicts usable output?
- Are you over-rejecting good content?
- Are bad outputs slipping through?

**Adjusting evaluation criteria:**
- Weight criteria by importance
- Add specific checks for common issues
- Create fast-path for simple cases

**Human-in-the-loop optimization:**
- When to require human review
- Reducing review burden over time
- Learning from corrections

### Segment 4: Speed Optimization (8 min)

**Parallel processing:**
- Run independent steps simultaneously
- Reduce total execution time

**Caching strategies:**
- Cache style.json and reference data
- Don't re-fetch static content

**Step elimination:**
- Are all steps necessary?
- Can steps be combined?

**Model selection:**
- Faster models for simpler tasks
- Reserve powerful models for complex generation

---

## Self-Paced Exercises (60 minutes total)

### Exercise 4.1: Performance Analysis (20 minutes)

*Understand your workflow efficiency*

1. Export your execution logs (10+ executions minimum)

2. Calculate key metrics:

```markdown
# Workflow Performance Analysis

## Execution Metrics

| Metric | Workflow 1 | Workflow 2 | Target |
|--------|------------|------------|--------|
| Avg Execution Time | | | |
| Success Rate | | | |
| Avg Quality Score | | | |
| Human Review Rate | | | |
| Avg Cost/Execution | | | |

## Step-by-Step Timing

### Workflow 1
| Step | Avg Duration | % of Total | Bottleneck? |
|------|--------------|------------|-------------|
| | | | |

## Quality Analysis

| Score Range | Count | % | Outcome |
|-------------|-------|---|---------|
| 4.5-5.0 | | | Direct output |
| 3.5-4.4 | | | Passed with minor issues |
| 2.5-3.4 | | | Required review |
| < 2.5 | | | Regenerated/Failed |

## Cost Analysis
- Total cost for [X] executions: $___
- Average cost per execution: $___
- Projected monthly cost (at current rate): $___

## Issues Identified
1. [Issue description]
2. [Issue description]
```

**Deliverable:** `performance-analysis.md`

---

### Exercise 4.2: Implement Optimizations (25 minutes)

*Improve efficiency based on analysis*

1. **Cost optimization (pick 2):**
   - Reduce prompt length by 20%+
   - Use smaller model for quality check step
   - Add caching for repeated data
   - Eliminate unnecessary steps

2. **Speed optimization (pick 1):**
   - Add parallel processing
   - Optimize data fetching
   - Remove bottleneck step

3. **Quality optimization (pick 1):**
   - Refine evaluation thresholds
   - Add specific quality checks
   - Improve regeneration prompt

4. Document changes:

```markdown
# Optimization Changes

## Cost Optimizations
- **Change:** [What you changed]
- **Expected impact:** [X% reduction]
- **Actual result:** [Measure after 5 executions]

## Speed Optimizations
- **Change:** [What you changed]
- **Expected impact:** [X seconds/minutes faster]
- **Actual result:** [Measure after 5 executions]

## Quality Optimizations
- **Change:** [What you changed]
- **Expected impact:** [Better accuracy, fewer reviews]
- **Actual result:** [Measure after 5 executions]
```

5. Run 5+ test executions to measure improvement

**Deliverable:** Optimized workflows + optimization documentation

---

### Exercise 4.3: Before/After Comparison (15 minutes)

*Quantify improvement*

1. Compare pre and post optimization metrics:

```markdown
# Optimization Results

## Before vs. After

| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| Avg Execution Time | | | X% faster |
| Avg Cost/Execution | | | X% cheaper |
| Success Rate | | | X% better |
| Quality Score | | | X points |
| Human Review Rate | | | X% reduction |

## ROI Calculation

### Time Savings
- Per execution: ___ minutes saved
- Monthly (X executions): ___ hours saved
- Annual projection: ___ hours saved

### Cost Savings
- Per execution: $___ saved
- Monthly: $___ saved
- Annual projection: $___ saved

### Quality Improvement
- [Describe quality gains]

## Lessons Learned
1. [Key learning]
2. [Key learning]
```

**Deliverable:** `optimization-results.md`

---

### Exercise 4.4: Workflow Exchange (Optional - 20 minutes)

*Learn from peers by testing each other's workflows*

**If you have a learning partner:**

1. Exchange workflow documentation with partner
2. Each person attempts to run the other's workflow:
   - Follow their documentation
   - Note any gaps or confusion
   - Document results

3. Provide feedback:
   - What was clear
   - What was confusing
   - Suggestions for improvement

4. Discuss findings together

**Deliverable:** Peer feedback notes (shared with partner)

**Benefits:**
- Reveals documentation gaps
- Exposes assumptions
- Builds team knowledge
- Prepares for team rollout

---

## Key Takeaways

1. **Data drives optimization** - Measure before improving
2. **Context reduction improves performance** - Less is often more
3. **Model selection matters** - Right model for right task
4. **Quality thresholds need tuning** - Use real results to calibrate
5. **Document everything** - Optimizations are only valuable if repeatable

---

## Preparation for Week 5

- Complete optimization implementation
- Have optimized workflows running
- Review MCP server analysis from Week 1
- Next week: MCP integration basics

---

## Resources

- [Anthropic Pricing](https://www.anthropic.com/pricing)
- [OpenAI Pricing](https://openai.com/pricing)
- [Lost in the Middle: How Language Models Use Long Contexts](https://arxiv.org/abs/2307.03172)
