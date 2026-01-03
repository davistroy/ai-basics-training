# **POWERPOINT PRESENTATION: BLOCK 2 WEEK 4**
## **Workflow Optimization**

**Block:** 2: AI Workflow Engineering
**Week Number:** 4
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Consultants with two working workflows and logged execution data

**Key Thesis:** Optimization requires data-driven analysis, and counterintuitively, reducing context improves both performance and cost - less context means better AI focus and output quality.

**Week Learning Objectives:** By the end of this session, participants will:
1. Analyze workflow execution data to identify optimization opportunities
2. Understand and apply context window optimization strategies
3. Calibrate quality thresholds based on actual execution results
4. Implement speed optimizations for improved workflow performance

**Entry Criteria:**
- [ ] Two working workflows with quality checks
- [ ] 10+ logged executions across workflows
- [ ] JSON data structures implemented
- [ ] Quality routing functional

**Exit Criteria:**
- [ ] Cost optimization applied to workflows
- [ ] Quality gates refined based on data
- [ ] Performance bottlenecks identified and addressed
- [ ] Workflow efficiency improved by 20%+

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Analyzing Performance (9 min) - Slides 4-6
3. Segment 2: Cost Optimization + Context Window (16 min) - Slides 7-13
4. Segment 3: Quality Gate Refinement (10 min) - Slides 14-17
5. Segment 4: Speed Optimization (4 min) - Slides 18-19
6. Homework Preview & Close (3 min) - Slides 20-22

**Total Slides:** 22

---

## SLIDE 1: TITLE SLIDE

**Title:** Block 2 Week 4: Workflow Optimization

**Subtitle:** Using Data to Make Your Workflows Faster, Cheaper, and Better

**Content:**
- AI Practitioner Training Program
- Block 2: AI Workflow Engineering
- [Instructor Name]
- [Date]

**Graphic:** Clean title slide with Block 2 orange color theme. Optimization icons (speed, cost, quality gauges).

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Week 4 - we're at the midpoint of Block 2! You've built workflows, added quality checks, and logged executions. Today we use that data to optimize.

Quick show of hands: who has at least 10 logged executions across their workflows? [Count]

Those logs are your optimization goldmine. They tell you what to improve.

Here's what we're solving today: Your workflows work. But are they as fast, cheap, and reliable as they could be? Let's find out."

[Transition: Click to next slide]

---

## SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Status check, data readiness |
| 3-12 min | Segment 1 | Analyzing Workflow Performance |
| 12-28 min | Segment 2 | Cost Optimization + Context Window Trap |
| 28-38 min | Segment 3 | Quality Gate Refinement |
| 38-42 min | Segment 4 | Speed Optimization |
| 42-45 min | Close | Homework & Week 5 Preview |

**Graphic:** Visual timeline with optimization focus markers

**SPEAKER NOTES:**

"Here's our agenda:

First, we'll look at how to analyze your execution data - what patterns to look for.

Then the big topic: cost optimization. I'll share a counterintuitive insight about context windows that will change how you think about prompts.

Next, quality gate refinement - using real data to calibrate your thresholds.

And we'll close with speed optimizations.

By the end, you'll have a clear plan for making your workflows 20% or more efficient."

[Transition]

---

## SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Analyze workflow execution data**
   - Extract insights from your logs

2. **Apply the context window optimization principle**
   - Less context = better performance

3. **Calibrate quality thresholds**
   - Data-driven threshold adjustment

4. **Implement speed optimizations**
   - Parallel processing, caching, model selection

**Graphic:** Checklist with optimization icons

**SPEAKER NOTES:**

"Four objectives for today.

First, you'll know how to read your execution logs for optimization insights.

Second - and this is the big one - you'll understand why MORE context often means WORSE results. This is counterintuitive but critical.

Third, you'll calibrate your quality thresholds using actual data instead of guesses.

Fourth, you'll know how to speed up your workflows.

Let's start with the data."

[Transition: Click to Segment 1]

---

## SEGMENT 1: ANALYZING WORKFLOW PERFORMANCE
### Duration: 9 minutes | Slides 4-6

---

## SLIDE 4: YOUR EXECUTION LOGS ARE GOLD

**Title:** Data Tells You What to Optimize

**Content:**

**Key Metrics to Calculate:**

| Metric | What It Tells You |
|--------|-------------------|
| Average Execution Time | Baseline speed |
| Success Rate | Reliability |
| Quality Score Distribution | Output consistency |
| Cost Per Execution | Baseline cost |
| Human Review Rate | Quality gate efficiency |

**Pattern Questions:**
- Which steps take longest?
- Where do failures occur?
- What triggers low quality scores?

**Graphic:** Dashboard mockup showing key metrics

**GRAPHICS:**

**Graphic 1: Workflow Metrics Dashboard**
- Purpose: Show comprehensive view of workflow performance across all three dimensions
- Type: Dashboard mockup with metric tiles
- Elements: Three metric sections (Speed: avg execution time, p95 time; Cost: per-execution cost, monthly total; Quality: avg score, pass rate), trend indicators, target thresholds marked
- Labels: Metric names, current values, targets, trends
- Relationships: Three pillars of optimization shown as interconnected metrics

**SPEAKER NOTES:**

"[Hook - The data you've collected]"

"Those logs you've been keeping? They're your optimization roadmap.

[Point to metrics]

Average execution time tells you your baseline. Success rate shows reliability. Quality distribution reveals consistency. Cost per execution establishes your baseline spend.

But the real insights come from patterns:

Which step takes longest? That's your bottleneck.

Where do failures occur? That's your reliability problem.

What triggers low scores? That's your quality issue.

The data tells you what to fix. Let's look at how to analyze it."

[Transition]

---

## SLIDE 5: STEP-BY-STEP TIMING ANALYSIS

**Title:** Find the Bottleneck

**Content:**

**Example Breakdown:**

| Step | Avg Duration | % of Total | Issue? |
|------|--------------|------------|--------|
| Trigger | 0.5s | 4% | - |
| Data Fetch | 3s | 25% | Possible |
| AI Generation | 6s | 50% | Main cost |
| Quality Check | 2s | 17% | Acceptable |
| Output | 0.5s | 4% | - |
| **Total** | **12s** | 100% | |

**Insights from This Example:**
- AI generation is 50% of time (expected)
- Data fetch at 25% is high - investigate
- Could parallel fetch with quality model load

**Graphic:** Bar chart showing step timing distribution

**SPEAKER NOTES:**

"Here's what step-by-step analysis looks like.

[Point to table]

In this example, AI generation is 50% of time. That's expected - it's the core work.

But data fetch is 25%. That's high for just gathering input. Is it fetching too much? Can we cache it?

[Point to insights]

The analysis reveals: we could run data fetch in parallel with loading the quality model. Save 2 seconds.

This is what your analysis should produce: specific, actionable insights."

[Transition]

---

## SLIDE 6: SEGMENT 1 SUMMARY

**Title:** Analysis Principles

**Content:**

**Key Takeaways:**
- Calculate key metrics from your logs
- Look for patterns, not just averages
- Identify bottlenecks by step
- "Measure before improving"

**You'll Practice:**
Exercise 4.1 - Complete performance analysis

**Graphic:** Simple analysis flow icon

**SPEAKER NOTES:**

"Before we move on:

Calculate your key metrics. Look beyond averages to patterns.

Identify which step is your bottleneck.

And remember: measure before improving. Guessing wastes effort.

Now let's talk about the biggest optimization opportunity for most people: context windows."

[Transition: Click to Segment 2]

---

## SEGMENT 2: COST OPTIMIZATION + CONTEXT WINDOW TRAP
### Duration: 16 minutes | Slides 7-13

---

## SLIDE 7: THE COUNTERINTUITIVE TRUTH

**Title:** More Context Makes Things WORSE

**Content:**

**Common Assumption:**
> "I'll include more context so the AI has all the information it might need."

**Research Reality:**
> Models ignore the middle of long inputs. Performance DEGRADES as input length increases.

**The "Lost in the Middle" Finding:**
- AI pays attention to beginning and end
- Middle content is de-prioritized or ignored
- Complete histories often perform WORSE than curated excerpts

**Graphic:** Attention distribution curve showing high attention at start/end, low in middle

**GRAPHICS:**

**Graphic 1: LLM Attention Distribution Curve**
- Purpose: Illustrate how LLMs pay more attention to beginning and end of prompts
- Type: U-shaped attention curve graph
- Elements: Curve with peaks at start/end, valley in middle, shaded high-attention zones, "Lost in the Middle" phenomenon annotation
- Labels: "Position in Prompt" (X-axis), "Attention Weight" (Y-axis), optimal placement annotations
- Relationships: U-shaped distribution showing strategic placement guidance for prompt optimization

**SPEAKER NOTES:**

"[Hook - The counterintuitive truth]"

"I need to share something that might contradict what you've been doing.

[Pause for effect]

More context makes things WORSE, not better.

[Point to assumption]

The assumption: 'I'll include everything so the AI has all the information.'

[Point to reality]

The research: AI models actually IGNORE the middle of long inputs. It's called the 'Lost in the Middle' phenomenon. Documented across models.

[Point to graphic]

AI pays attention to the start and end. The middle? Often ignored.

This means complete conversation histories often perform WORSE than short, curated excerpts.

Let that sink in."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide delivers the week's most important insight and must overcome strong intuitive resistance
- Participants naturally assume "more information = better results" from general knowledge work experience
- The counterintuitive nature requires strong evidence and clear explanation to shift mental models
- This insight directly impacts both cost optimization and quality improvement

**Key Research & Citations:**
- **"Lost in the Middle" (Liu et al., 2023)**: Empirical study showing LLM performance degrades on information placed in the middle of long contexts, with attention concentrated at beginning and end positions across multiple model architectures
- **Attention Mechanisms in Transformers (Vaswani et al., 2017)**: The foundational architecture research that explains WHY context dilution occurs - attention is distributed across all tokens with positional bias
- **Context Window Studies (2024)**: Recent research on Claude and GPT-4 shows that even with 100K+ token windows, performance on retrieval tasks drops significantly for middle-positioned information

**Q&A Preparation:**
- *"But Claude has a 200K token context window - why not use it?"*: Having capacity doesn't mean you should fill it. Larger windows enable flexibility for when you NEED them, but optimal performance still comes from focused, curated context. Think of it like RAM in a computer - having 64GB doesn't mean every program should use all of it.
- *"How do I know what's the 'minimum needed'?"*: Start with what you think is essential, run tests, then try removing 30-40% of context and compare outputs. Most people find they can cut significantly without quality loss - often improving it.
- *"Doesn't this contradict RAG systems that retrieve lots of context?"*: Good RAG systems RANK and LIMIT retrieved context. They don't dump everything - they prioritize the most relevant chunks. Same principle applies.

---

## SLIDE 8: WHY THIS HAPPENS

**Title:** Every Token Competes for Attention

**Content:**

**The Attention Economy Inside AI:**
```
Token 1: ████████████ (gets attention)
Token 2: ██████████ (gets attention)
...
Token 500: ███ (less attention)
...
Token 2000: █ (minimal attention)
...
Token 4000: (effectively ignored)
```

**Key Insight:**
> When you add more tokens, each token gets LESS attention. The important information gets diluted.

**The Counterintuitive Optimization:**
Remove context → Better focus → Better output

**Graphic:** Dilution visual showing attention spread thinner with more tokens

**SPEAKER NOTES:**

"Why does this happen?

[Point to diagram]

AI has a fixed 'attention budget.' When you have 100 tokens, each one gets substantial attention.

When you have 4,000 tokens, that same attention is spread across 40x more content. Each token gets 1/40th the focus.

[Point to key insight]

Your critical instruction - the one that really matters - is now competing with 4,000 other tokens. It's diluted.

[Point to counterintuitive]

The optimization: REMOVE context. Less competition for attention. Better focus on what matters. Better output.

This is why reducing context improves both cost AND quality."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide provides the mechanistic explanation that makes the counterintuitive insight credible
- Understanding WHY context dilution happens enables participants to make informed optimization decisions
- The attention budget metaphor makes an abstract technical concept accessible to non-technical audiences

**Key Research & Citations:**
- **Attention Mechanism Fundamentals**: Transformer models use softmax attention which distributes a normalized probability across all tokens - mathematically, adding more tokens MUST reduce attention weight on any individual token
- **Cognitive Load Theory Applied to AI**: Just as human working memory has limits, AI attention has computational limits. The parallel to human cognition helps participants understand the principle intuitively.
- **Production System Optimization**: Real-world case studies show that token reduction of 50-70% often maintains or improves output quality while dramatically reducing costs and latency

**Q&A Preparation:**
- *"Is this true for all models or just some?"*: The attention dilution effect is fundamental to transformer architecture, which underpins Claude, GPT, and most modern LLMs. Some models handle longer contexts better than others, but the principle applies universally.
- *"What about models specifically trained on long contexts?"*: Long-context training improves the ability to maintain coherence across distance, but doesn't eliminate the attention competition effect. They're better at long contexts, not immune to dilution.
- *"How do I know if I've removed too much context?"*: Test. Compare outputs with fuller vs. minimal context. The quality metrics you built in Week 3 give you objective measures. Most people are surprised how little context is actually needed.

---

## SLIDE 9: PRACTICAL TOKEN REDUCTION

**Title:** What to Cut, What to Keep

**Content:**

**Remove:**
- Complete conversation histories (use summary instead)
- Verbose explanations (shorten)
- Repeated instructions (say once)
- "Just in case" context (cut it)
- Formatting fluff (minimize)

**Keep:**
- Direct instructions for THIS step
- Necessary context for THIS task
- Examples (1-2, not 10)
- `style.json` reference (summarized)

**The Question to Ask:**
> "What is the MINIMUM context needed for this specific step?"

**Graphic:** Before/after prompt comparison showing reduction

**SPEAKER NOTES:**

"Here's what to cut and what to keep.

[Point to Remove]

Remove: Complete histories, verbose explanations, repeated instructions, 'just in case' content. All of this dilutes attention.

[Point to Keep]

Keep: Direct instructions for THIS step. Necessary context for THIS task. One or two examples. Summarized style reference.

[Point to question]

Before adding anything, ask: 'Is this the minimum needed for this step?'

If it's 'nice to have' instead of 'need to have' - cut it."

[Transition]

---

## SLIDE 10: TOKEN REDUCTION EXAMPLE

**Title:** Same Quality, 70% Fewer Tokens

**Content:**

**Before (3,000 tokens):**
```
[Full conversation history from last 5 exchanges]
[Complete style guide - 2 pages]
[All project background]
[Detailed instructions with examples]
[Full deliverable context]
```

**After (900 tokens):**
```
[Last exchange only - summarized]
[Style guide key points - 5 bullets]
[Relevant project detail only]
[Concise instruction]
[Specific context for this task]
```

**Result:**
- 70% token reduction
- Same output quality (tested)
- Better focus on task

**Graphic:** Side-by-side token count comparison

**SPEAKER NOTES:**

"Let me show you a real example.

[Point to before]

Before: Full history, complete style guide, all background. 3,000 tokens.

[Point to after]

After: Last exchange summarized, key style points, only relevant context. 900 tokens.

[Point to result]

Result: 70% reduction. And here's the key - SAME output quality. Actually, often BETTER because the AI focuses on what matters.

This is what you're doing in Exercise 4.2 - finding these reductions in your own prompts."

[Transition]

---

## SLIDE 11: CURRENT PRICING REFERENCE

**Title:** What Tokens Actually Cost

**Content:**

**Model Pricing (Early 2025):**

| Model | Input/1M tokens | Output/1M tokens | Best For |
|-------|-----------------|------------------|----------|
| Claude 3.5 Sonnet | ~$3.00 | ~$15.00 | Complex generation |
| Claude 3 Haiku | ~$0.25 | ~$1.25 | Simple tasks |
| GPT-4o | ~$2.50 | ~$10.00 | General purpose |
| GPT-4o-mini | ~$0.15 | ~$0.60 | High volume |

**Typical Workflow Costs:**
- Simple task: $0.001 - $0.01
- Standard generation: $0.01 - $0.05
- Complex analysis: $0.05 - $0.15

*Prices change - verify at provider websites*

**Graphic:** Pricing comparison visualization

**SPEAKER NOTES:**

"Let's talk actual costs.

[Point to table]

These are approximate current prices. Claude Sonnet is about $3 per million input tokens. Haiku is a fraction of that.

[Point to typical costs]

For most consulting workflows: simple tasks are fractions of a cent. Standard generation is 1-5 cents. Even complex work is 5-15 cents.

[Pause]

At these prices, 100 executions per month costs $1-15. The TIME you save dwarfs the AI cost."

[Transition]

---

## SLIDE 12: THE REAL COST INSIGHT

**Title:** Time Savings Dwarf Token Costs

**Content:**

**Example Calculation:**

| Metric | Value |
|--------|-------|
| AI cost per execution | $0.05 |
| Time saved per execution | 30 minutes |
| Your hourly rate | $100/hour |
| Value of time saved | $50 |

**ROI per execution: 1000:1**

**The Insight:**
> Optimize tokens for PERFORMANCE, not cost savings. The cost savings are a bonus.

**Focus On:**
- Reducing tokens improves quality (less dilution)
- Reducing tokens improves speed (less to process)
- Cost savings happen automatically

**Graphic:** ROI comparison showing time value vs. token cost

**SPEAKER NOTES:**

"Here's the insight that changes how you think about optimization.

[Point to calculation]

AI cost: 5 cents. Time saved: 30 minutes. At $100/hour, that's $50 of time saved.

ROI per execution: 1000 to 1.

[Point to insight]

The point isn't to save money on tokens. Token costs are trivial compared to time value.

[Point to focus]

Optimize tokens for PERFORMANCE. Less dilution = better quality. Less to process = faster response.

The cost savings are just a bonus. The real win is better, faster output."

[Transition]

---

## SLIDE 13: SEGMENT 2 SUMMARY

**Title:** Cost Optimization Takeaways

**Content:**

**Key Points:**
- More context = WORSE performance (counterintuitive but true)
- Every token competes for attention
- Ask: "What's the minimum for this step?"
- Token reduction improves quality AND cost
- Time savings dwarf AI costs

**You'll Practice:**
Exercise 4.2 - Implement cost optimizations

**Graphic:** Summary with cost optimization icon

**SPEAKER NOTES:**

"Let me summarize cost optimization:

More context makes things worse. This is the big insight.

Every token competes for attention. Adding more dilutes what matters.

Always ask: what's the minimum needed?

Token reduction improves both quality and cost.

And remember: your time savings are worth far more than the token costs.

In Exercise 4.2, you'll find and implement these reductions in your own workflows.

Now let's refine your quality thresholds."

[Transition: Click to Segment 3]

---

## SEGMENT 3: QUALITY GATE REFINEMENT
### Duration: 10 minutes | Slides 14-17

---

## SLIDE 14: THRESHOLDS FROM DATA, NOT GUESSES

**Title:** Calibrating Quality Gates

**Content:**

**The Problem with Arbitrary Thresholds:**
- "Pass at 4.0" - why 4.0? Because it sounds good?
- Too strict: reject usable output
- Too lenient: pass bad output

**Data-Driven Calibration:**
1. Collect 20+ scored executions
2. Review the distribution
3. Spot-check outputs at each level
4. Adjust thresholds based on reality

**Graphic:** Distribution curve with threshold line

**SPEAKER NOTES:**

"Let's refine your quality thresholds.

[Point to problem]

Setting 'pass at 4.0' - why 4.0? Often it's arbitrary. And arbitrary thresholds cause problems.

Too strict: you reject perfectly usable output. Too lenient: bad output slips through.

[Point to calibration]

Data-driven approach: Collect 20+ scored executions. Review how scores distribute. Spot-check outputs at each level. THEN adjust thresholds based on what you actually see.

Let the data tell you where the line should be."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide transitions participants from intuition-based to evidence-based decision making
- It addresses a common failure mode: setting thresholds based on what "sounds right" rather than empirical validation
- The data-driven approach demonstrates professional engineering practice applicable beyond AI

**Key Research & Citations:**
- **Statistical Process Control**: Industrial quality management principle that thresholds should be set based on actual process capability data, not desired targets. Applying manufacturing quality principles to AI workflows.
- **Machine Learning Model Calibration**: The practice of threshold tuning based on validation data is standard in ML deployment - precision/recall tradeoffs are calibrated empirically, never guessed
- **A/B Testing Methodology**: The iterative refinement process mirrors how successful product teams optimize features - measure, analyze, adjust, repeat

**Q&A Preparation:**
- *"What if my initial threshold was way off?"*: That's completely normal and expected. Initial thresholds are educated guesses. The point of data collection is to discover reality. Big adjustments are a sign you're learning, not failing.
- *"How many executions do I need before I can trust the data?"*: 20+ gives you a distribution pattern. 50+ gives you confidence. 100+ lets you segment by workflow type. Start adjusting at 20, keep refining as data accumulates.
- *"What if the distribution is bimodal - two peaks?"*: That usually indicates you have two different types of inputs or use cases. Consider separate thresholds for each type, or split into two different workflows.

---

## SLIDE 15: READING YOUR SCORE DISTRIBUTION

**Title:** What Your Quality Scores Tell You

**Content:**

**Example Distribution:**

| Score | Count | % | Your Judgment |
|-------|-------|---|---------------|
| 4.5-5.0 | 8 | 20% | Excellent - definitely pass |
| 4.0-4.4 | 15 | 37% | Good - should pass |
| 3.5-3.9 | 12 | 30% | Acceptable - review? |
| 3.0-3.4 | 4 | 10% | Questionable |
| < 3.0 | 1 | 3% | Fail |

**Questions to Answer:**
- Where does "usable" actually start?
- Are 3.5-3.9 outputs actually good enough?
- Is the 3.0 threshold right?

**Graphic:** Bar chart of score distribution

**SPEAKER NOTES:**

"Here's how to read your distribution.

[Point to table]

This example shows most outputs score 4.0-4.4. About 30% are in the 3.5-3.9 zone.

[Point to questions]

The question: are those 3.5-3.9 outputs actually usable? Look at them. If they're fine, maybe your pass threshold is too high.

Or maybe the 3.0-3.4 outputs are worse than you thought. Raise the fail threshold.

Your data + your judgment = correct thresholds."

[Transition]

---

## SLIDE 16: THRESHOLD ADJUSTMENT

**Title:** Fine-Tuning Your Quality Gates

**Content:**

**If Good Outputs Are Failing:**
- Lower pass threshold (4.0 → 3.7)
- Check if criteria are too strict
- Review scoring prompt for harshness

**If Bad Outputs Are Passing:**
- Raise pass threshold (3.5 → 4.0)
- Add specific checks for the issues
- Weight problem criteria higher

**If Borderline Is Large:**
- Add more specific criteria
- Create tiered routing (pass/review/fail)
- Consider different thresholds by type

**Calibration Tip:**
> Start conservative (reject more). Loosen based on data.

**Graphic:** Threshold adjustment arrows

**SPEAKER NOTES:**

"How to adjust based on what you find:

[Point to good failing]

If good outputs are failing, lower your pass threshold. Also check if your evaluation criteria are too harsh.

[Point to bad passing]

If bad outputs are passing, raise your threshold. Add specific checks for the issues you're seeing.

[Point to borderline]

If you have a large 'borderline' category, add more criteria or create tiered routing.

[Point to tip]

Start conservative - it's easier to loosen than to tighten. You want to catch problems, then refine."

[Transition]

---

## SLIDE 17: SEGMENT 3 SUMMARY

**Title:** Quality Calibration Takeaways

**Content:**

**Key Points:**
- Use data to set thresholds, not guesses
- Review outputs at each score level
- Adjust based on actual usability
- Start conservative, loosen with data

**You'll Practice:**
Exercise 4.2 - Refine quality thresholds

**Graphic:** Calibration summary icon

**SPEAKER NOTES:**

"Quality calibration summary:

Use data, not guesses. Review actual outputs. Adjust based on what's really usable.

Start strict. You can always loosen later.

In your homework, you'll do this calibration for your own workflows."

[Transition: Click to Segment 4]

---

## SEGMENT 4: SPEED OPTIMIZATION
### Duration: 4 minutes | Slides 18-19

---

## SLIDE 18: QUICK SPEED WINS

**Title:** Making Workflows Faster

**Content:**

**Parallel Processing:**
```
Sequential: Step A (2s) → Step B (2s) → Step C (5s) = 9s
Parallel:   Step A + B (2s) → Step C (5s) = 7s
```
If steps are independent, run them simultaneously.

**Caching:**
- Cache static content (`style.json`, templates)
- Don't re-fetch what doesn't change
- Most platforms support caching

**Model Selection:**
| Task Complexity | Model Choice | Speed |
|-----------------|--------------|-------|
| Simple (classify, extract) | Fast model | 1-2s |
| Standard (generate short) | Standard model | 3-5s |
| Complex (long generation) | Powerful model | 5-10s |

**Graphic:** Speed comparison visualization

**SPEAKER NOTES:**

"Quick speed wins:

[Point to parallel]

Parallel processing: if two steps don't depend on each other, run them at the same time. Instant time savings.

[Point to caching]

Caching: your `style.json` doesn't change. Why fetch it every execution? Cache static content.

[Point to model selection]

Model selection: quality checks don't need your most powerful model. Use a faster model for simple tasks."

[Transition]

---

## SLIDE 19: SEGMENT 4 SUMMARY

**Title:** Speed Optimization Takeaways

**Content:**

**Quick Wins:**
- Parallel processing for independent steps
- Cache static content
- Right-size model to task
- Remove unnecessary steps

**Priority:**
Speed is usually third priority after context reduction and quality calibration.

**You'll Practice:**
Exercise 4.2 - Implement speed optimization

**Graphic:** Speed priority list

**SPEAKER NOTES:**

"Speed optimization summary:

Parallelize independent steps. Cache static content. Right-size your models.

Note: speed is usually third priority. Context reduction and quality calibration often have bigger impact.

But speed wins are easy and add up.

Let's wrap up."

[Transition: Click to Closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 20-22

---

## SLIDE 20: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| 4.1: Performance Analysis | 20 min | `performance-analysis.md` | Data analysis |
| 4.2: Implement Optimizations | 25 min | Optimized workflows | Apply improvements |
| 4.3: Measure Results | 15 min | `optimization-results.md` | Before/after |
| **Total** | **60 min** | | |

**Goal:** Measurable improvement in at least one area

**Graphic:** Exercise breakdown visual

**SPEAKER NOTES:**

"Three exercises this week:

Exercise 4.1 - 20 minutes - analyze your execution data. Calculate metrics, find patterns.

Exercise 4.2 - 25 minutes - implement optimizations. At least one from each category.

Exercise 4.3 - 15 minutes - measure the before/after. Quantify your improvement.

Goal: measurable improvement in cost, speed, or quality. Ideally all three."

[Transition]

---

## SLIDE 21: RESOURCES

**Title:** Resources for This Week

**Content:**

**Pricing Reference:**
- Anthropic: anthropic.com/pricing
- OpenAI: openai.com/pricing

**Research:**
- "Lost in the Middle" paper: arxiv.org/abs/2307.03172

**Support:**
- Questions: [Support channel]
- Share your optimization wins with the cohort!

**Graphic:** Resource icons

**SPEAKER NOTES:**

"Resources:

Current pricing at the provider websites - verify before calculating.

If you want to read the research on context windows, the 'Lost in the Middle' paper is linked.

Share your optimization wins in the support channel. Good to learn from each other."

[Transition]

---

## SLIDE 22: NEXT WEEK PREVIEW

**Title:** Next Week: MCP Integration Basics

**Content:**

**Week 5 Focus:**
- Configure Model Context Protocol
- Connect Claude to your files and tools
- Build first MCP-powered workflow

**Preparation Required:**
- [ ] All Week 4 exercises complete
- [ ] Optimized workflows running
- [ ] MCP server analysis from Week 1 ready
- [ ] Claude Desktop installed

**The Goal:**
Claude reading your files, accessing your GitHub, connected to your tools.

**Graphic:** MCP server diagram

**SPEAKER NOTES:**

"Next week: MCP integration!

We finally connect Claude to your files, GitHub, and other tools using the Model Context Protocol.

To be ready:
- Complete this week's optimization exercises
- Have your optimized workflows running
- Pull up your MCP server analysis from Week 1
- Make sure Claude Desktop is installed

[Final close]

Questions before we wrap?

[Take questions]

You're at the midpoint of Block 2 with optimized, quality-checked workflows. Next week we add powerful integrations.

Complete your analysis, implement those optimizations, and see you next week!"

---

## Appendices

**Slide Type Definitions:** TITLE SLIDE | PROBLEM STATEMENT | INSIGHT / REVELATION | CONCEPT INTRODUCTION | FRAMEWORK / MODEL | COMPARISON | DEEP DIVE | CASE STUDY | PATTERN / BEST PRACTICE | METRICS / DATA | ARCHITECTURE / DIAGRAM | OBJECTION HANDLING | ACTION / NEXT STEPS | SUMMARY / RECAP | SECTION DIVIDER | CLOSING / CALL TO ACTION | Q&A / CONTACT

**Content Guidelines:** Use parallel structure in bullets | Clear tables with headers | Bad/Good example contrasts | Key principle callouts | Stage directions in speaker notes `[Pause]` `[Point to X]` `[Emphasize]`

**Block 2 Orange Theme:** Primary Orange (#FF6B35) for branding | Accent blues/grays | Orange highlights for emphasis | Consistent color across all Block 2 presentations

**Quality Checklist:** Learning objectives align | Key Thesis clear | Complete speaker notes | Technical accuracy | Relevant examples | Research citations specific | Q&A addresses objections | Orange theme consistent | Progressive building | Realistic timing

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |

---

**Template Usage:**
1. Use Block 2 orange color theme throughout
2. Have current pricing reference verified
3. Prepare sample execution data for analysis examples
4. Cross-reference with instructor and participant guides
