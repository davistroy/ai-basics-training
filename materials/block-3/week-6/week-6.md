# Week 6: Optimization & Monitoring

**Block:** 3 - AI Automation Architecture
**Duration:** 45 min live workshop + 75 min self-paced exercises

---

## Entry Criteria

- [ ] Multi-agent orchestration working
- [ ] 20+ orchestrated executions
- [ ] All agents specialized and functional
- [ ] Basic logging in place

## Exit Criteria

- [ ] Performance dashboard created
- [ ] Cost optimization applied
- [ ] Reliability patterns implemented
- [ ] Production monitoring configured
- [ ] (Optional) Chaos testing explored

---

## Workshop Content (45 minutes)

### Segment 1: Production Readiness Assessment (10 min)

**What "production ready" means:**
- Reliable: Works consistently without failures
- Observable: You can see what's happening
- Recoverable: Failures don't cause data loss
- Efficient: Reasonable cost and time
- Secure: Doesn't expose sensitive data

**Production checklist:**
- [ ] Error handling for all failure modes
- [ ] Logging of all executions
- [ ] Alerting on failures
- [ ] Checkpoint/resume capability
- [ ] Performance within acceptable range
- [ ] Cost within budget
- [ ] Security review completed

### Segment 2: Performance Dashboards (13 min)

**Key metrics to track:**

| Category | Metrics |
|----------|---------|
| Volume | Executions/day, Tasks/agent |
| Performance | Avg duration, P95 duration |
| Quality | Success rate, Quality scores |
| Cost | Cost/execution, Total cost |
| Reliability | Error rate, Retry rate |

**Dashboard design:**
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

**Observability Litmus Test:**

Can you answer these questions about your agent system?

- ✓ What's in the context right now?
- ✓ Where did each piece come from?
- ✓ Why was this included?
- ✓ What was available but excluded?
- ✓ Can you replay any decision with exact context state?

**The Law of Observability:**
If you can't see it, you can't fix it. If you can't fix it, you can't trust it.

**Implementation options:**
- Google Sheets (simple)
- Airtable (structured)
- Grafana (advanced)
- Custom web dashboard

### Segment 3: Cost Optimization Deep Dive (11 min)

**Cost components:**
- AI API calls (tokens)
- Platform execution fees
- External API costs
- Storage/logging costs

**Optimization strategies:**

1. **Token reduction:**
   - Shorter prompts (without losing clarity)
   - Summarize context instead of full history
   - Cache repeated lookups

2. **Model selection:**
   - Use smaller models for simple tasks
   - Reserve powerful models for complex reasoning
   - Example: Haiku for classification, Opus for generation

3. **Execution efficiency:**
   - Skip unnecessary steps
   - Parallel where possible
   - Batch operations

4. **Smart caching:**
   - Cache tool results that don't change
   - Reuse common outputs
   - Invalidate strategically

**Cost tracking:**
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

### Segment 4: Reliability Patterns + Chaos Testing (11 min)

**Reliability patterns:**

1. **Circuit breaker:**
   - Stop calling failing service
   - Prevent cascade failures
   - Auto-reset after cooldown

2. **Bulkhead:**
   - Isolate components
   - Failure in one doesn't affect others

3. **Timeout + retry:**
   - Don't wait forever
   - Retry with exponential backoff

4. **Graceful degradation:**
   - Provide partial service on failure
   - Better than complete failure

**Chaos testing (optional/advanced):**
- Deliberately inject failures
- Verify system handles them
- Build confidence in reliability

```markdown
Chaos Tests:
1. Kill Tool A mid-execution → Agent should recover
2. Inject timeout on Agent B → Orchestrator should retry
3. Return malformed data → Validation should catch
```

---

## Self-Paced Exercises (75 minutes total)

### Exercise 6.1: Build Performance Dashboard (30 minutes)

*Create visibility into your agents*

1. **Design dashboard metrics:**

```markdown
# Agent Performance Dashboard Design

## Key Metrics

### Volume Metrics
- Total executions (daily/weekly/monthly)
- Executions by agent type
- Executions by trigger source

### Performance Metrics
- Average execution time
- P95 execution time (95th percentile)
- Time by stage/agent

### Quality Metrics
- Overall success rate
- Quality scores (from rubric evaluation)
- Human review rate
- Revision rate

### Cost Metrics
- Cost per execution
- Cost by agent
- Daily/monthly total cost
- Cost trend

### Reliability Metrics
- Error rate
- Error types distribution
- Retry rate
- Recovery rate

## Dashboard Layout

[Sketch or describe the layout]

## Data Sources
- Execution logs: [Location]
- Quality evaluations: [Location]
- Cost tracking: [Location]

## Update Frequency
- Real-time: [Which metrics]
- Daily: [Which metrics]
- Weekly: [Which metrics]
```

2. **Implement dashboard:**
   - Create in Google Sheets, Airtable, or tool of choice
   - Connect to your execution logs
   - Add charts/visualizations
   - Test with real data

3. **Set up alerts:**
   - Error rate > 20%: Alert immediately
   - Success rate < 80%: Daily summary
   - Cost > $X/day: Alert immediately

**Deliverable:** Working dashboard + alert configuration

---

### Exercise 6.2: Cost Optimization (25 minutes)

*Reduce costs without sacrificing quality*

1. **Analyze current costs:**

```markdown
# Cost Analysis & Optimization

## Current State

### Cost Breakdown (last 20 executions)
| Component | Tokens/Calls | Cost | % of Total |
|-----------|--------------|------|------------|
| Agent 1 | | $ | % |
| Agent 2 | | $ | % |
| Agent 3 | | $ | % |
| Tool calls | | $ | % |
| **Total** | | $ | 100% |

### Cost per Execution
- Average: $
- Minimum: $
- Maximum: $

### Monthly Projection
- At current rate: $/month

## Optimization Opportunities

### Opportunity 1: [Description]
- **Current:** [State]
- **Change:** [What to do]
- **Expected savings:** [%]
- **Risk:** [Any quality impact]

### Opportunity 2: [Description]
[Repeat structure]

## Implementation Plan

1. [ ] [Change 1]
2. [ ] [Change 2]
3. [ ] [Change 3]

## Validation
- Run 10 executions with optimizations
- Compare quality scores (before vs after)
- Calculate actual savings
```

2. **Implement top optimizations:**
   - Apply 2-3 changes
   - Test thoroughly
   - Verify quality maintained

3. **Measure results:**

```markdown
## Optimization Results

| Metric | Before | After | Change |
|--------|--------|-------|--------|
| Avg cost/execution | $ | $ | -X% |
| Avg quality score | X.X | X.X | |
| Avg execution time | Xm | Xm | |

## Conclusion
[Summary of optimization impact]
```

**Deliverable:** Cost analysis + optimization results

---

### Exercise 6.3: Reliability Implementation (20 minutes)

*Harden your agents for production*

1. **Implement reliability patterns:**

```markdown
# Reliability Implementation

## Circuit Breaker

### Configuration
- Failure threshold: [X failures in Y minutes]
- Open duration: [Z minutes]
- Half-open test: [How to check if recovered]

### Implementation
[Where and how implemented]

### Testing
- [ ] Triggered circuit breaker manually
- [ ] Verified requests blocked when open
- [ ] Verified auto-recovery after cooldown

## Timeout & Retry

### Configuration
| Operation | Timeout | Max Retries | Backoff |
|-----------|---------|-------------|---------|
| Tool A | Xs | 3 | 1s, 2s, 4s |
| Tool B | Xs | 3 | 1s, 2s, 4s |
| Agent call | Xs | 2 | 2s, 4s |

### Testing
- [ ] Timeout triggers correctly
- [ ] Retries execute with backoff
- [ ] Gives up after max retries

## Graceful Degradation

### Fallback Strategies
| Failure | Fallback Behavior |
|---------|------------------|
| Tool A fails | [What happens instead] |
| Agent B fails | [What happens instead] |
| Quality check fails | [What happens instead] |
```

2. **Optional: Chaos Testing**

```markdown
# Chaos Testing Log

## Test 1: Tool Failure
- **Action:** Disabled Tool A access
- **Expected:** Agent detects, uses fallback
- **Actual:** [What happened]
- **Fix needed:** [If any]

## Test 2: Agent Timeout
- **Action:** Forced Agent B to timeout
- **Expected:** Orchestrator retries, then escalates
- **Actual:** [What happened]
- **Fix needed:** [If any]
```

**Deliverable:** Reliability implementation + test results

---

## Key Takeaways

1. **Production readiness is a checklist** - Reliable, observable, recoverable
2. **Dashboards enable improvement** - What you measure, you can optimize
3. **Cost optimization compounds** - Small savings add up at scale
4. **Reliability patterns prevent cascades** - Circuit breakers, retries, fallbacks
5. **Chaos testing builds confidence** - Know your system handles failure

---

## Preparation for Week 7

- Complete all monitoring setup
- Run optimized system for multiple days
- Collect data for capstone metrics
- Next week: Capstone preparation

---

## Resources

- [Grafana](https://grafana.com/)
- [Circuit Breaker Pattern](https://martinfowler.com/bliki/CircuitBreaker.html)
- [Chaos Engineering](https://principlesofchaos.org/)
