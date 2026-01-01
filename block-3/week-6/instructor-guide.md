# **INSTRUCTOR GUIDE: BLOCK 3 WEEK 6**
## **Optimization & Monitoring**

**Block:** 3: AI Automation Architecture
**Week:** 6 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Production readiness, dashboards, cost optimization, reliability patterns |
| **Difficulty Level** | Medium-High |
| **Prep Time Required** | 45 minutes |
| **Demo Required** | Yes - Dashboard demo, cost analysis example |
| **Tech Setup Needed** | Sample dashboard, cost data, reliability pattern examples |
| **Common Challenges** | Metric selection; balancing cost vs. quality |

---

## Navigation

**Block Navigation:** [Week 5 Instructor Guide](../week-5/instructor-guide.md) | **Week 6** | [Week 7 Instructor Guide](../week-7/instructor-guide.md)

**Related Materials:**
- [Week 6 Presentation Slides](presentation.md)
- [Week 6 Participant Guide](participant-guide.md)
- [Block 3 Main Document](../block-3.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 6 materials | |
| Prepare dashboard demo | Build sample dashboard with real-looking data | |
| Create cost analysis example | Calculate sample optimization results | |
| Review participant progress | Check multi-agent orchestration status | |
| Review Week 5 | Check integration test results | |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test dashboard demo | |
| Load presentation | Have slides ready | |
| Prepare cost examples | Have before/after optimization data | |
| Check reliability examples | Have circuit breaker, retry examples ready | |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, dashboard demo, cost spreadsheet | |
| Test share | Verify screen sharing works | |
| Load demo data | Have metrics ready to show | |
| Start recording | If session is recorded | |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Week 5 recap | Check orchestration status |
| 0:03 | 10 min | Segment 1 | Production Readiness Assessment | Checklist |
| 0:13 | 13 min | Segment 2 | Performance Dashboards | Metrics & observability |
| 0:26 | 11 min | Segment 3 | Cost Optimization | Token reduction, efficiency |
| 0:37 | 8 min | Segment 4 | Reliability Patterns + Close | Patterns & homework |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Skip chaos testing mention (reference in guide)
- Reduce reliability patterns to circuit breaker only
- Reference dashboard implementation details in guide

**If Running Ahead:**
- More discussion on participant-specific metrics
- Extended cost optimization examples
- Discuss chaos testing in more depth

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants
2. Quick status check on multi-agent orchestration
3. Preview today's production focus
4. Set context for capstone preparation

**Opening Script:**
> "Welcome to Week 6: Optimization & Monitoring. You've built multi-agent systems with orchestration. Today we make them production-ready. By the end, you'll know how to measure, optimize, and monitor your agents for real-world deployment."

---

### Segment 1: Production Readiness Assessment (10 minutes)

**Learning Objective:** Understand what production-ready means for agent systems

**Slides:** 3-7

#### Content Delivery

**Key Point 1: What "Production Ready" Means**
- Main message: Five qualities - Reliable, Observable, Recoverable, Efficient, Secure
- Framework: Checklist approach to production readiness
- Key insight: "If you can't see it, you can't fix it. If you can't fix it, you can't trust it."

**Key Point 2: Production Checklist**
- Main message: Systematic verification before deployment
- Checklist items: Error handling, logging, alerting, checkpoint/resume, performance, cost, security
- Practice preview: "Exercise 6.3 implements reliability patterns"

---

### Segment 2: Performance Dashboards (13 minutes)

**Learning Objective:** Design and implement agent monitoring dashboards

**Slides:** 8-13

#### Content Delivery

**Key Point 1: Key Metrics to Track**
- Main message: Volume, Performance, Quality, Cost, Reliability categories
- Framework: What to measure in each category
- Key insight: "What you measure, you can improve"

**Key Point 2: Dashboard Design**
- Main message: Clear visualization of agent health
- Example: Show dashboard layout with charts, alerts, recent failures
- Implementation options: Google Sheets, Airtable, Grafana

**Key Point 3: Observability Litmus Test**
- Main message: Five questions to verify observability
- Questions: What's in context? Where did it come from? Why included? What excluded? Can you replay?
- Key insight: "The Law of Observability: If you can't see it, you can't fix it."

---

### Segment 3: Cost Optimization (11 minutes)

**Learning Objective:** Implement cost reduction without sacrificing quality

**Slides:** 14-19

#### Content Delivery

**Key Point 1: Cost Components**
- Main message: AI API calls, platform fees, external APIs, storage/logging
- Framework: Understand where money goes before optimizing

**Key Point 2: Optimization Strategies**
- Main message: Four strategies - Token reduction, Model selection, Execution efficiency, Smart caching
- Examples: Shorter prompts, smaller models for simple tasks, skip unnecessary steps, cache tool results

**Key Point 3: Cost Tracking**
- Main message: Track costs per execution, per agent
- Format: JSON structure for cost logging
- Connection to homework: Exercise 6.2 analyzes and optimizes costs

---

### Segment 4: Reliability Patterns + Closing (8 minutes)

**Learning Objective:** Implement reliability patterns for production agents

**Slides:** 20-25

#### Content Delivery

**Key Point 1: Reliability Patterns**
- Main message: Four patterns - Circuit breaker, Bulkhead, Timeout+retry, Graceful degradation
- Quick overview of each
- Key insight: "Prevent cascade failures"

**Key Point 2: Chaos Testing (Brief)**
- Main message: Deliberately inject failures to verify handling
- Examples: Kill tool mid-execution, inject timeout, return malformed data
- Note: "Optional but builds confidence"

#### Homework Preview

**Script:**
> "Your homework includes three exercises totaling about 75 minutes.
>
> Exercise 6.1 is Build Performance Dashboard - 30 minutes. Create visibility into your agents with metrics and alerts.
>
> Exercise 6.2 is Cost Optimization - 25 minutes. Analyze costs and implement reductions without sacrificing quality.
>
> Exercise 6.3 is Reliability Implementation - 20 minutes. Add circuit breaker, retry, and graceful degradation.
>
> By end of week, your system should be production-ready. Next week is capstone preparation."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: How much monitoring is enough?**
A: At minimum: success rate, error rate, cost per execution. Add more as specific questions arise. Don't monitor everything - monitor what matters.

**Q: What's an acceptable error rate?**
A: Depends on use case. 95% success is good for most applications. Critical processes might need 99%+.

### Technical Questions

**Q: What tool should I use for dashboards?**
A: Start simple - Google Sheets works fine. Move to Airtable for more structure, Grafana for real-time. Don't over-engineer.

**Q: How do I measure token usage?**
A: API responses include token counts. Log them with each execution. Most platforms provide usage dashboards too.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Dashboard demo fails | Show pre-captured screenshots | Walk through conceptually |
| Cost data incomplete | Use example numbers | Focus on methodology |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| No metrics yet | "I haven't tracked anything" | Start with basic logging |
| Over-monitoring | Too many metrics | "Focus on actionable metrics" |
| Cost anxiety | Worried about API costs | Show optimization strategies |

---

## Post-Session Tasks

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | |
| Answer monitoring questions | |
| Share dashboard templates | |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review dashboard implementations | |
| Check cost optimization results | |
| Verify reliability patterns implemented | |

---

## Week-Specific Notes

### What Makes This Week Unique

- **Production focus** - Shifting from "does it work" to "is it ready for real use"
- **Measurement emphasis** - Quantifying agent performance
- **Optimization introduction** - Balancing cost and quality
- **Pre-capstone preparation** - Getting systems ready for final evaluation

### Dependencies

**Builds On:**
- Week 5: Multi-agent orchestration to monitor
- Week 2: Error handling expanded to reliability patterns

**Sets Up:**
- Week 7: Capstone preparation with optimized system
- Week 8: Capstone submission with metrics

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "If you can't see it, you can't fix it"
2. "What you measure, you can improve"
3. "Optimize cost without sacrificing quality"

### If You Only Have Time For One Thing

Dashboard with three metrics: Success rate, Average cost, Error types. These tell you if your system is healthy.

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial guide created | Training Team |
