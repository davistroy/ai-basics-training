# **POWERPOINT PRESENTATION: BLOCK 3 WEEK 6**
## **Optimization & Monitoring**

**Block:** 3: AI Automation Architecture
**Week Number:** 6
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 participants with multi-agent orchestration from Week 5

**Week Learning Objectives:** By the end of this session, participants will:
1. Assess production readiness using a systematic checklist
2. Design and implement performance dashboards with key metrics
3. Analyze costs and implement optimization strategies
4. Implement reliability patterns for production agents

**Entry Criteria:**
- [ ] Multi-agent orchestration working (Week 5)
- [ ] 20+ orchestrated executions
- [ ] All agents specialized and functional
- [ ] Basic logging in place

**Exit Criteria:**
- [ ] Understand production readiness requirements
- [ ] Design dashboard with key metrics
- [ ] Identify cost optimization opportunities
- [ ] Know four reliability patterns

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Production Readiness (10 min) - Slides 4-8
3. Segment 2: Performance Dashboards (13 min) - Slides 9-14
4. Segment 3: Cost Optimization (11 min) - Slides 15-19
5. Segment 4: Reliability Patterns + Close (8 min) - Slides 20-25

**Total Slides:** 25

---

## SLIDE 1: TITLE SLIDE

**Title:** Block 3 Week 6: Optimization & Monitoring

**Subtitle:** Production-Ready Agent Systems

**Content:**
- AI Practitioner Training Program
- Block 3: AI Automation Architecture

**Graphic:** Clean title slide with green theme. Visual of dashboard/monitoring.

**SPEAKER NOTES:**

"Welcome to Week 6: Optimization & Monitoring.

You've built multi-agent systems with orchestration. Today we make them production-ready.

By the end, you'll know how to measure, optimize, and monitor your agents for real-world deployment. This is the week where your prototype becomes something you can actually trust."

[Transition]

---

## SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Week 5 Recap |
| 3-13 min | Segment 1 | Production Readiness |
| 13-26 min | Segment 2 | Performance Dashboards |
| 26-37 min | Segment 3 | Cost Optimization |
| 37-45 min | Segment 4 | Reliability Patterns |

**Graphic:** Timeline with green accents

**SPEAKER NOTES:**

"Here's our roadmap:

First, production readiness - what does it mean for agents to be ready for real use?

Then dashboards - creating visibility into your system.

Cost optimization - making it efficient.

Reliability patterns - making it resilient.

After today, your system should be ready for the capstone evaluation."

[Transition]

---

## SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Assess production readiness**
   - Systematic checklist for deployment

2. **Design performance dashboards**
   - Track what matters

3. **Optimize costs**
   - Reduce spend without sacrificing quality

4. **Implement reliability patterns**
   - Handle failures gracefully

**Graphic:** Checklist with green checkboxes

**SPEAKER NOTES:**

"Four objectives.

[Read each]

Your homework implements all of these. By end of week, you'll have a monitored, optimized, resilient system."

[Transition: Click to Segment 1]

---

## SEGMENT 1: PRODUCTION READINESS
### Duration: 10 minutes | Slides 4-8

---

## SLIDE 4: WHAT IS PRODUCTION READY?

**Title:** Five Qualities of Production-Ready

**Content:**

| Quality | Meaning |
|---------|---------|
| **Reliable** | Works consistently without failures |
| **Observable** | You can see what's happening |
| **Recoverable** | Failures don't cause data loss |
| **Efficient** | Reasonable cost and time |
| **Secure** | Doesn't expose sensitive data |

**Production ready = All five qualities present**

**Graphic:** Five pillars or pentagon diagram

**SPEAKER NOTES:**

"What does production-ready mean?

[Walk through each]

Reliable - it works, consistently. Not 'usually works.'

Observable - you can see what's happening. Not a black box.

Recoverable - when things fail, you don't lose data. Checkpoints help here.

Efficient - reasonable cost and time. Not burning money.

Secure - not leaking sensitive information.

Production ready means ALL FIVE. Not just 'it runs.'"

[Transition]

---

## SLIDE 5: PRODUCTION CHECKLIST

**Title:** Before You Deploy

**Content:**

**Production Readiness Checklist:**
- [ ] Error handling for all failure modes
- [ ] Logging of all executions
- [ ] Alerting on failures
- [ ] Checkpoint/resume capability
- [ ] Performance within acceptable range
- [ ] Cost within budget
- [ ] Security review completed

**If you can't check all boxes → not ready**

**Graphic:** Checklist visualization

**SPEAKER NOTES:**

"Here's your checklist.

[Read through items]

Error handling - we covered this in Week 2. Do you handle all failure modes?

Logging - can you see what happened after the fact?

Alerting - do you know when things fail?

Checkpoint/resume - Week 4. Can you recover?

Performance - is it fast enough?

Cost - can you afford to run it?

Security - have you checked?

If any box is unchecked, you're not ready for production."

[Transition]

---

## SLIDE 6: THE LAW OF OBSERVABILITY

**Title:** If You Can't See It...

**Content:**

**The Law of Observability:**
> "If you can't see it, you can't fix it. If you can't fix it, you can't trust it."

**Observability Litmus Test:**

Can you answer these questions?
- What's in the context right now?
- Where did each piece come from?
- Why was this included?
- What was available but excluded?
- Can you replay any decision with exact context state?

**Graphic:** Question marks → Lightbulbs flow

**SPEAKER NOTES:**

"This is critical.

[Read the law]

If you can't see it, you can't fix it. If you can't fix it, you can't trust it.

[Litmus test]

Can you answer these five questions about your agent right now? What's in context? Where did it come from? Why included? What excluded? Can you replay?

If no, you don't have observability. And without observability, you can't trust the system."

[Transition]

---

## SLIDE 7: THE PRODUCTION MINDSET

**Title:** From "It Works" to "It's Ready"

**Content:**

**Prototype Mindset:**
- "It worked this time"
- "I can fix it if it breaks"
- "I understand what happened"

**Production Mindset:**
- "It works every time"
- "It fixes itself or alerts me"
- "Anyone can understand what happened"

**The Shift:**
Personal understanding → Systematic observability

**Graphic:** Before/after mindset comparison

**SPEAKER NOTES:**

"There's a mindset shift needed.

[Prototype]

'It worked this time' - but will it work next time?
'I can fix it' - but will you be available?
'I understand' - but will someone else?

[Production]

'It works every time' - reliable.
'It fixes itself or alerts' - recoverable, observable.
'Anyone can understand' - documentation, logging.

The shift is from personal understanding to systematic observability."

[Transition]

---

## SLIDE 8: YOUR ASSESSMENT

**Title:** Assess Your System

**Content:**

**This Week:**
Run through the checklist for your multi-agent system.

**Questions to Answer:**
1. What's working well?
2. What gaps exist?
3. What's the biggest risk?
4. What would fail first under stress?

**Exercise 6.3 implements reliability patterns for gaps you find.**

**Graphic:** Assessment framework

**SPEAKER NOTES:**

"Your assignment is to assess your own system.

[Questions]

What's working? What are the gaps? Biggest risk? What fails first?

Be honest with yourself. You're two weeks from capstone submission. Better to find gaps now than during evaluation.

Exercise 6.3 helps you fill gaps with reliability patterns."

[Transition: Click to Segment 2]

---

## SEGMENT 2: PERFORMANCE DASHBOARDS
### Duration: 13 minutes | Slides 9-14

---

## SLIDE 9: WHY DASHBOARDS?

**Title:** What You Measure, You Can Improve

**Content:**

**Without Measurement:**
- "I think it's working okay"
- "It seems faster lately"
- "Costs are probably fine"

**With Measurement:**
- "94% success rate this week"
- "Average execution: 45 seconds"
- "Cost: $0.08 per execution"

**Dashboards transform opinions into facts.**

**Graphic:** Vague vs. Precise comparison

**SPEAKER NOTES:**

"Why bother with dashboards?

[Without]

'I think it's working' - you think? 'Seems faster' - seems? 'Probably fine' - probably?

[With]

'94% success rate' - fact. '45 seconds' - measurable. '$0.08' - trackable.

Dashboards turn vague feelings into concrete facts. You can't improve what you can't measure."

[Transition]

---

## SLIDE 10: KEY METRICS

**Title:** What to Track

**Content:**

| Category | Metrics |
|----------|---------|
| **Volume** | Executions/day, Tasks/agent |
| **Performance** | Avg duration, P95 duration |
| **Quality** | Success rate, Quality scores |
| **Cost** | Cost/execution, Total cost |
| **Reliability** | Error rate, Retry rate |

**Start here. Add more as needed.**

**Graphic:** Five-category metric table

**SPEAKER NOTES:**

"Here are the five categories to track.

[Walk through each]

Volume - how much is running? Executions per day, tasks per agent.

Performance - how fast? Average duration and P95 (95th percentile - where most fall under).

Quality - how good? Success rate and quality scores if you have them.

Cost - how expensive? Per execution and total.

Reliability - how stable? Error rate, retry rate.

Start with one metric per category. Add more as you have questions."

[Transition]

---

## SLIDE 11: DASHBOARD DESIGN

**Title:** What It Looks Like

**Content:**

```
┌─────────────────────────────────────────────┐
│ AGENT DASHBOARD                             │
├─────────────────────────────────────────────┤
│ Today: 47 executions | 94% success | $12.40 │
├─────────────────────────────────────────────┤
│ [Chart: Executions over time]               │
│ [Chart: Success rate trend]                 │
│ [Chart: Avg duration by agent]              │
├─────────────────────────────────────────────┤
│ Recent Failures:                            │
│ - 10:32 AM: Agent B timeout                 │
│ - 09:15 AM: Tool API error                  │
└─────────────────────────────────────────────┘
```

**Graphic:** Dashboard mockup

**SPEAKER NOTES:**

"Here's an example layout.

[Walk through]

Header with today's summary - quick glance at health. Executions, success rate, cost.

Charts showing trends over time. Are things getting better or worse?

Recent failures - what went wrong? Quick reference for debugging.

You don't need fancy tools. This could be Google Sheets."

[Transition]

---

## SLIDE 12: IMPLEMENTATION OPTIONS

**Title:** Tools for Dashboards

**Content:**

| Tool | Complexity | Best For |
|------|------------|----------|
| **Google Sheets** | Low | Starting out |
| **Airtable** | Medium | Structured data |
| **Grafana** | High | Real-time, advanced |
| **Custom Web** | Variable | Specific needs |

**Start simple. Upgrade when you outgrow it.**

**Graphic:** Tool comparison chart

**SPEAKER NOTES:**

"What tool should you use?

[Walk through options]

Google Sheets - easiest. Good for starting. Manual or automated updates.

Airtable - more structure. Good for tracking many things.

Grafana - real-time dashboards. More setup, more power.

Custom - build your own if you have specific needs.

[Advice]

Start with Google Sheets. Seriously. You can always upgrade. Don't let tool selection block progress."

[Transition]

---

## SLIDE 13: ALERTING

**Title:** Know When Things Break

**Content:**

**Critical Alerts (Immediate):**
- Error rate > 20%
- Cost > $X/day
- No executions in 24 hours

**Warning Alerts (Daily):**
- Success rate < 80%
- Duration trending up
- Cost trending up

**Don't Alert on Everything**
Alert fatigue kills responsiveness.

**Graphic:** Alert priority pyramid

**SPEAKER NOTES:**

"Dashboards show you what happened. Alerts tell you when to act.

[Critical]

Error rate spiking? Know immediately. Costs exploding? Know immediately. System completely down? Know immediately.

[Warning]

Success rate declining? Daily summary is fine. Trends changing? Daily.

[Key point]

Don't alert on everything. If everything is an alert, nothing is. Reserve immediate alerts for things that need immediate action."

[Transition]

---

## SLIDE 14: EXERCISE PREVIEW

**Title:** Build Your Dashboard

**Content:**

**Exercise 6.1:**
1. Define metrics for each category
2. Choose your tool
3. Implement data collection
4. Create visualizations
5. Configure alerts

**Deliverable:**
Working dashboard with actual data from your executions.

**Graphic:** Exercise steps

**SPEAKER NOTES:**

"Exercise 6.1 has you build this.

Define your metrics. Choose your tool - Google Sheets is fine. Implement data collection. Create some charts. Configure alerts.

The deliverable is a working dashboard with your actual data. Not a plan - a working dashboard."

[Transition: Click to Segment 3]

---

## SEGMENT 3: COST OPTIMIZATION
### Duration: 11 minutes | Slides 15-19

---

## SLIDE 15: COST COMPONENTS

**Title:** Where Money Goes

**Content:**

**Cost Components:**
- **AI API calls** - Tokens in and out
- **Platform fees** - Make/n8n/etc. execution costs
- **External APIs** - Tool calls, data sources
- **Storage/Logging** - Keeping records

**First: Know Your Costs**

Before optimizing, measure what you're actually spending.

**Graphic:** Cost breakdown pie chart

**SPEAKER NOTES:**

"Before optimizing, know where money goes.

[Components]

AI API calls - usually the biggest. Input and output tokens.

Platform fees - whatever automation platform you use.

External APIs - tools that call other services.

Storage and logging - keeping records.

[First step]

Measure first. You can't optimize what you don't measure. Exercise 6.2 starts with cost analysis."

[Transition]

---

## SLIDE 16: FOUR OPTIMIZATION STRATEGIES

**Title:** How to Reduce Costs

**Content:**

| Strategy | How |
|----------|-----|
| **Token Reduction** | Shorter prompts, summarized context |
| **Model Selection** | Smaller models for simple tasks |
| **Execution Efficiency** | Skip unnecessary steps, batch ops |
| **Smart Caching** | Cache tool results that don't change |

**Goal: Reduce cost WITHOUT sacrificing quality**

**Graphic:** Four strategy icons

**SPEAKER NOTES:**

"Four strategies to reduce costs.

[Walk through each]

Token reduction - shorter prompts, summarize instead of full context. Less in = less cost.

Model selection - not everything needs the biggest model. Simple tasks can use smaller, cheaper models.

Execution efficiency - skip steps you don't need. Batch operations when possible.

Smart caching - if a tool call returns the same thing every time, cache it.

[Goal]

The goal is reducing cost WITHOUT reducing quality. Validate after optimizing."

[Transition]

---

## SLIDE 17: TOKEN REDUCTION

**Title:** Write Less, Say More

**Content:**

**Before:**
```
You are a highly skilled research assistant with expertise in
finding and analyzing information from various sources. Your
job is to help users by searching the web, reading documents,
and synthesizing findings into clear, comprehensive reports...
[500 more words]
```

**After:**
```
You are a research assistant. Search, read, and summarize
information into clear reports.
Tools: web_search, file_read
Format: Bullet summary with sources.
```

**Same capability, fewer tokens**

**Graphic:** Before/after comparison

**SPEAKER NOTES:**

"Token reduction example.

[Before]

Verbose prompt. Every word costs tokens. Does the agent need all that?

[After]

Same capability. Much shorter. Clear and direct.

[Key point]

Every token costs money. Be concise. Say what you mean in fewer words. The agent doesn't need flowery language."

[Transition]

---

## SLIDE 18: MODEL SELECTION

**Title:** Right Model for Right Task

**Content:**

| Task Type | Recommended | Cost |
|-----------|-------------|------|
| **Classification** | Haiku | Lowest |
| **Simple generation** | Haiku/Sonnet | Low-Medium |
| **Complex reasoning** | Sonnet | Medium |
| **Expert analysis** | Opus | Highest |

**Not every task needs the most powerful model.**

**Example:** Use Haiku for validation, Sonnet for generation.

**Graphic:** Model tier diagram

**SPEAKER NOTES:**

"Match model to task.

[Walk through tiers]

Classification - is this A or B? Haiku is fine.

Simple generation - write a sentence. Haiku or Sonnet.

Complex reasoning - analyze this situation. Sonnet.

Expert analysis - nuanced judgment. Opus.

[Key insight]

Not every task needs the most powerful model. Your orchestration can use different models for different agents."

[Transition]

---

## SLIDE 19: COST TRACKING

**Title:** Track Every Execution

**Content:**

```json
{
  "execution_id": "xxx",
  "costs": {
    "agent_1": { "tokens": 1500, "cost": 0.02 },
    "agent_2": { "tokens": 2000, "cost": 0.03 },
    "tools": { "api_calls": 3, "cost": 0.01 }
  },
  "total_cost": 0.06
}
```

**Track per-execution to find patterns.**

**Exercise 6.2 analyzes your costs and implements optimizations.**

**Graphic:** Cost tracking format

**SPEAKER NOTES:**

"Track costs per execution.

[Show format]

Each execution gets a cost breakdown. Which agents used how many tokens, what did tools cost, total.

[Why]

This lets you find patterns. Is one agent costing way more? Is there a spike on certain requests?

Exercise 6.2 has you analyze this data and implement optimizations."

[Transition: Click to Segment 4]

---

## SEGMENT 4: RELIABILITY PATTERNS + CLOSE
### Duration: 8 minutes | Slides 20-25

---

## SLIDE 20: RELIABILITY PATTERNS

**Title:** Building Resilience

**Content:**

**Four Key Patterns:**

| Pattern | Purpose |
|---------|---------|
| **Circuit Breaker** | Stop calling failing services |
| **Bulkhead** | Isolate component failures |
| **Timeout + Retry** | Don't wait forever |
| **Graceful Degradation** | Partial service on failure |

**Prevent cascade failures.**

**Graphic:** Four pattern icons

**SPEAKER NOTES:**

"Four patterns make systems resilient.

[Walk through]

Circuit breaker - if something keeps failing, stop calling it for a while.

Bulkhead - isolate components so one failure doesn't take down everything.

Timeout and retry - don't wait forever; retry with backoff.

Graceful degradation - if you can't do everything, do something.

These prevent cascade failures - one problem becoming many."

[Transition]

---

## SLIDE 21: CIRCUIT BREAKER

**Title:** Stop Calling What's Broken

**Content:**

```
CLOSED (normal) → OPEN (failing) → HALF-OPEN (testing)
```

**Implementation:**
- After N failures, stop calling (OPEN)
- Wait X minutes
- Try one request (HALF-OPEN)
- If success, resume (CLOSED)
- If failure, stay OPEN

**Prevents: Hammering a failing service**

**Graphic:** Circuit breaker state diagram

**SPEAKER NOTES:**

"Circuit breaker in detail.

[States]

Normal operation is CLOSED - requests flow through.

After N failures, it opens. No more requests go through. You're not hammering a failing service.

After cooldown, it goes half-open. Try one request. If it works, close the circuit. If not, stay open.

This prevents you from making a bad situation worse by flooding a failing service."

[Transition]

---

## SLIDE 22: GRACEFUL DEGRADATION

**Title:** Something is Better Than Nothing

**Content:**

**Instead of:**
Complete failure, error message, no value

**Provide:**
- Partial results with explanation
- Cached data with staleness note
- Reduced functionality that still helps

**Example:**
If analysis agent fails → Return research results only
"Analysis unavailable. Here's what I found: [research]"

**Graphic:** Degradation example

**SPEAKER NOTES:**

"Graceful degradation is key.

[Instead of]

Complete failure - 'Error: Agent B failed' - user gets nothing.

[Provide]

Partial results - 'Here's what I have so far.'
Cached data - 'Latest data is from 2 hours ago.'
Reduced functionality - 'Full analysis unavailable, but research is complete.'

[Example]

Analysis agent fails? Don't fail completely. Return the research. Something is better than nothing."

[Transition]

---

## SLIDE 23: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Focus |
|----------|------|-------------|-------|
| 6.1: Dashboard | 30 min | Working dashboard | Visibility |
| 6.2: Cost Optimization | 25 min | Analysis + results | Efficiency |
| 6.3: Reliability | 20 min | Patterns implemented | Resilience |
| **Total** | **75 min** | | |

**Target:** Production-ready system

**Graphic:** Exercise flow

**SPEAKER NOTES:**

"Your homework.

Exercise 6.1 - build your dashboard. 30 minutes.

Exercise 6.2 - cost optimization. 25 minutes. Analyze and improve.

Exercise 6.3 - reliability patterns. 20 minutes. Implement and test.

By end of week, your system should be production-ready. Next week is capstone preparation."

[Transition]

---

## SLIDE 24: RESOURCES

**Title:** Resources for This Week

**Content:**

**Templates:**
- Dashboard design template - Participant Guide
- Cost analysis template - Participant Guide
- Reliability implementation template - Participant Guide

**Reference:**
- [Grafana](https://grafana.com/) - Advanced dashboards
- [Circuit Breaker Pattern](https://martinfowler.com/bliki/CircuitBreaker.html)
- [Chaos Engineering](https://principlesofchaos.org/)

**Graphic:** Resource icons

**SPEAKER NOTES:**

"Resources in your participant guide. Templates for all three exercises.

Reference links for deeper reading. Circuit breaker pattern if you want more detail. Chaos engineering if you want to go advanced."

[Transition]

---

## SLIDE 25: NEXT WEEK PREVIEW

**Title:** Next Week: Capstone Preparation

**Content:**

**Preview:**
Week 7 completes all capstone components - documentation, team rollout plan, ROI with real data.

**What to Complete:**
- [ ] Exercise 6.1: Performance Dashboard
- [ ] Exercise 6.2: Cost Optimization
- [ ] Exercise 6.3: Reliability Implementation
- [ ] Run optimized system multiple days

**Key Preparation:**
Collect metrics for ROI calculation next week.

**Graphic:** Week 7 preview

**SPEAKER NOTES:**

"Next week is Capstone Preparation.

You'll complete all the components - documentation, rollout plan, ROI calculation.

[Requirements]

Complete this week's exercises. Run your optimized system for several days. Collect the metrics - you'll need them for ROI.

[Final close]

Good session. Your system is almost production-ready. Two more weeks to capstone.

Questions?

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

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
