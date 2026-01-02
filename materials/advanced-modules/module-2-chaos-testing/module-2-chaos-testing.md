# **Advanced Module 2: Chaos Testing & Reliability Engineering**

## **2 Weeks | 45 min live + 75 min homework per week**

-----

## **Prerequisites**

- Block 3 Certification: AI Automation Architect
- Production-ready agent system deployed
- Performance monitoring and logging in place
- Understanding of error handling patterns
- 50+ agent executions completed

-----

## **Module Overview**

**Target Audience:** Block 3 graduates who want to build highly reliable, production-grade AI agent systems that can withstand failures and operate with minimal human intervention.

**Learning Objectives:**
- Understand chaos engineering principles for AI systems
- Design and execute systematic failure injection tests
- Implement advanced reliability patterns (circuit breakers, bulkheads)
- Build self-healing agent systems
- Create comprehensive reliability documentation

**Capstone:** Reliability Engineering Report
- Chaos test suite with documented results
- Implemented reliability patterns
- Self-healing mechanisms demonstration
- Production hardening checklist completed

-----

## **Week 1: Chaos Engineering Fundamentals**

### **Entry Criteria**

- [ ] Working agent system from Block 3
- [ ] Monitoring dashboard operational
- [ ] Error handling in place (basic)
- [ ] Ability to observe system behavior in real-time

### **Exit Criteria**

- [ ] Chaos engineering principles understood
- [ ] Failure mode catalog created
- [ ] First chaos experiments designed
- [ ] Safe testing environment established
- [ ] 5+ chaos experiments executed

-----

### **Workshop Content (45 minutes)**

**Segment 1: Introduction to Chaos Engineering (12 min)**

- **What is Chaos Engineering?**
  - Discipline of experimenting on a system to build confidence
  - Deliberately inject failures to find weaknesses
  - "Break it in testing so it doesn't break in production"

- **Why for AI Agents?**
  - AI systems have unique failure modes
  - External dependencies (APIs, tools, Model Context Protocol (MCP) servers)
  - Non-deterministic outputs
  - Complex orchestration paths

- **The Chaos Engineering cycle:**
  ```
  1. Define steady state (what "working" looks like)
  2. Hypothesize what will happen during failure
  3. Inject failure
  4. Observe actual behavior
  5. Fix weaknesses found
  6. Repeat
  ```

- **Safety principles:**
  - Start small, controlled experiments
  - Have rollback capability
  - Monitor closely during experiments
  - Never chaos test in production without safeguards

**Segment 2: AI Agent Failure Modes (12 min)**

- **Categories of failures:**

  | Category | Examples |
  |----------|----------|
  | **Tool Failures** | API down, timeout, rate limited, wrong response |
  | **AI Failures** | Hallucination, context lost, infinite loop, wrong tool choice |
  | **Orchestration Failures** | Agent handoff fails, state corruption, deadlock |
  | **Resource Failures** | Token limit, memory, cost budget exceeded |
  | **External Failures** | Network, authentication, third-party service down |

- **Failure mode analysis:**
  ```markdown
  ## Failure Mode: [Name]

  - **What:** [Description of failure]
  - **Likelihood:** [Common/Occasional/Rare]
  - **Impact:** [Critical/High/Medium/Low]
  - **Detection:** [How do we know it happened?]
  - **Current handling:** [What happens now?]
  - **Desired handling:** [What should happen?]
  ```

- **Prioritizing what to test:**
  - High likelihood × High impact = Test first
  - Create failure mode matrix

**Segment 3: Designing Chaos Experiments (12 min)**

- **Experiment structure:**
  ```markdown
  # Chaos Experiment: [Name]

  ## Hypothesis
  When [failure condition], the system will [expected behavior].

  ## Steady State Definition
  - Success rate: >95%
  - Response time: <30s
  - Error rate: <5%

  ## Failure Injection
  - **Method:** [How to cause failure]
  - **Duration:** [How long]
  - **Scope:** [What's affected]

  ## Observation Plan
  - Metrics to watch: [List]
  - Logs to monitor: [List]
  - Expected indicators: [List]

  ## Rollback Plan
  - How to stop: [Steps]
  - How to recover: [Steps]

  ## Success Criteria
  System should:
  - [ ] Detect the failure
  - [ ] Handle gracefully (no crash)
  - [ ] Recover when failure ends
  - [ ] Not corrupt data
  ```

- **Injection methods:**
  - Disable MCP server
  - Return error from tool
  - Delay responses (latency injection)
  - Return malformed data
  - Exhaust token budget
  - Kill agent mid-execution

**Segment 4: Safe Testing Environment (9 min)**

- **Setting up chaos testing:**
  - Clone production setup
  - Use test data only
  - Separate from real workflows
  - Clear "CHAOS TEST" labeling

- **Observability requirements:**
  - Real-time log streaming
  - Metrics dashboard visible
  - Alert notifications active
  - Recording of all events

- **Kill switch implementation:**
  ```
  IF chaos_test_running AND
     (error_rate > 50% OR
      system_unresponsive OR
      user_triggered):
    STOP chaos injection
    RESTORE normal operation
    ALERT operator
  ```

-----

### **Self-Paced Exercises (75 minutes total)**

**Exercise 1.1: Failure Mode Catalog (25 minutes)**

*Document all ways your system can fail*

```markdown
# Failure Mode Catalog

## System: [Your Agent System Name]

### Tool Failures

#### TF-001: MCP Server Unavailable
- **Description:** MCP server (filesystem/GitHub/etc.) not responding
- **Likelihood:** Occasional
- **Impact:** High - agent cannot access tools
- **Detection:** Connection timeout, error response
- **Current handling:** [What happens now]
- **Symptoms:** [What user sees]

#### TF-002: API Rate Limit
- **Description:** External API returns 429
- **Likelihood:** Common (during heavy use)
- **Impact:** Medium - delays execution
- **Detection:** 429 response code
- **Current handling:** [What happens now]

#### TF-003: [Name]
[Continue for all tool failures]

### AI Failures

#### AF-001: Context Window Exceeded
- **Description:** Input too large for model
- **Likelihood:** Occasional
- **Impact:** High - cannot process
- **Detection:** Token count error
- **Current handling:** [What happens now]

#### AF-002: Infinite Loop
- **Description:** Agent repeats same action
- **Likelihood:** Rare
- **Impact:** Critical - resource drain
- **Detection:** Iteration count > max
- **Current handling:** [What happens now]

#### AF-003: [Name]
[Continue]

### Orchestration Failures

#### OF-001: Agent Handoff Failure
[Document]

#### OF-002: State Corruption
[Document]

### Resource Failures

#### RF-001: Cost Budget Exceeded
[Document]

### External Failures

#### EF-001: Network Timeout
[Document]

---

## Failure Priority Matrix

| ID | Failure | Likelihood | Impact | Priority |
|----|---------|------------|--------|----------|
| TF-001 | MCP unavailable | Medium | High | **1** |
| AF-002 | Infinite loop | Low | Critical | **2** |
| [Continue sorted by priority]
```

**Deliverable:** `failure-mode-catalog.md`

-----

**Exercise 1.2: Design Chaos Experiments (25 minutes)**

*Create your first chaos test suite*

```markdown
# Chaos Experiment Suite

## Experiment 1: MCP Server Failure

### Hypothesis
When the filesystem MCP server becomes unavailable, the agent will:
1. Detect the failure within 10 seconds
2. Log the error with context
3. Attempt 3 retries with backoff
4. Fail gracefully with clear error message
5. Not crash or corrupt state

### Steady State
- Agent successfully reads files: Yes
- Response time: <10s
- Success rate: 100%

### Injection Method
- Rename MCP config temporarily
- OR: Block MCP server port
- OR: Return error from mock server

### Duration
- 60 seconds

### Observation
- [ ] Watch agent logs
- [ ] Monitor dashboard metrics
- [ ] Track error messages
- [ ] Verify no state corruption

### Rollback
1. Restore MCP config
2. Restart Claude Desktop if needed
3. Verify connectivity restored

### Expected vs Actual
| Behavior | Expected | Actual |
|----------|----------|--------|
| Detection time | <10s | |
| Retries attempted | 3 | |
| Graceful failure | Yes | |
| Error message clear | Yes | |
| State corrupted | No | |

---

## Experiment 2: AI Response Timeout

### Hypothesis
When AI API response takes >60 seconds, the system will:
[Design experiment]

---

## Experiment 3: Agent Infinite Loop

### Hypothesis
When agent enters a loop (>10 same actions), the system will:
[Design experiment]

---

## Experiment 4: Partial Orchestration Failure

### Hypothesis
When one agent in chain fails but others succeed, the system will:
[Design experiment]

---

## Experiment 5: Resource Exhaustion

### Hypothesis
When token budget is exceeded mid-execution, the system will:
[Design experiment]
```

**Deliverable:** `chaos-experiment-suite.md`

-----

**Exercise 1.3: Execute First Chaos Tests (25 minutes)**

*Run experiments and document results*

1. **Set up safe environment:**
   - Create test copy of agent system
   - Verify monitoring is active
   - Prepare rollback procedures

2. **Execute Experiment 1:**
   - Inject failure per design
   - Observe system behavior
   - Document actual results
   - Compare to hypothesis

3. **Document findings:**

```markdown
# Chaos Test Results: Experiment 1

## Execution Details
- **Date:** [Date]
- **Experimenter:** [Name]
- **Duration:** [Time]
- **Environment:** [Test/Staging]

## Results

### Expected vs Actual

| Behavior | Expected | Actual | Pass/Fail |
|----------|----------|--------|-----------|
| Detection time | <10s | Xs | |
| Retries attempted | 3 | N | |
| Graceful failure | Yes | | |
| Error message clear | Yes | | |
| State corrupted | No | | |

### Observations
- [What happened]
- [Unexpected behaviors]
- [System responses]

### Logs Captured
```
[Relevant log entries]
```

### Issues Found
1. **Issue:** [Description]
   - **Severity:** [Critical/High/Medium/Low]
   - **Fix needed:** [What to do]

2. **Issue:** [Description]
   [Continue]

### Recommendations
1. [Recommendation]
2. [Recommendation]

## Hypothesis Confirmed?
[Yes/No/Partially - explain]
```

4. **Execute remaining experiments** (at least 3 total)

**Deliverable:** Completed chaos test results for 3+ experiments

-----

## **Week 2: Advanced Reliability Patterns**

### **Entry Criteria**

- [ ] Chaos experiment suite created
- [ ] 5+ chaos tests executed
- [ ] Weaknesses identified in system
- [ ] Understanding of failure modes

### **Exit Criteria**

- [ ] Circuit breaker pattern implemented
- [ ] Bulkhead isolation in place
- [ ] Self-healing mechanisms functional
- [ ] Reliability documentation complete
- [ ] Module capstone delivered

-----

### **Workshop Content (45 minutes)**

**Segment 1: Circuit Breaker Pattern (12 min)**

- **What is a circuit breaker?**
  - Prevents repeated calls to failing service
  - "Trips" after threshold failures
  - Allows recovery time
  - Automatically resets

- **States:**
  ```
  CLOSED ──(failures > threshold)──→ OPEN
     ↑                                  │
     │                                  ↓
     └──(success)── HALF-OPEN ←──(timeout)
  ```

- **Implementation:**
  ```
  class CircuitBreaker:
    state = CLOSED
    failure_count = 0
    last_failure_time = null

    function call(operation):
      IF state == OPEN:
        IF time_since(last_failure) > reset_timeout:
          state = HALF_OPEN
        ELSE:
          return CIRCUIT_OPEN_ERROR

      TRY:
        result = operation()
        IF state == HALF_OPEN:
          state = CLOSED
          failure_count = 0
        return result
      CATCH:
        failure_count++
        last_failure_time = now()
        IF failure_count >= threshold:
          state = OPEN
        RAISE
  ```

- **Configuration:**
  - Failure threshold: 5 failures
  - Reset timeout: 60 seconds
  - Half-open test calls: 1

**Segment 2: Bulkhead Pattern (10 min)**

- **What is bulkhead isolation?**
  - Separate resources for different operations
  - Failure in one doesn't affect others
  - Like compartments in a ship

- **For AI agents:**
  ```
  ┌─────────────────┐  ┌─────────────────┐
  │ Research Agent  │  │ Writing Agent   │
  │ ┌─────────────┐ │  │ ┌─────────────┐ │
  │ │ Own context │ │  │ │ Own context │ │
  │ │ Own timeout │ │  │ │ Own timeout │ │
  │ │ Own retry   │ │  │ │ Own retry   │ │
  │ └─────────────┘ │  │ └─────────────┘ │
  └─────────────────┘  └─────────────────┘
         │                     │
         └──────────┬──────────┘
                    ↓
              [Orchestrator]
  ```

- **Benefits:**
  - Research agent failure doesn't crash writer
  - Resource limits per agent
  - Easier debugging

**Segment 3: Self-Healing Mechanisms (12 min)**

- **Types of self-healing:**

  1. **Automatic Retry:**
     - Retry with exponential backoff
     - Different strategies for different errors
     ```
     retry_config = {
       "network_error": {retries: 5, backoff: "exponential"},
       "rate_limit": {retries: 3, backoff: "fixed", delay: 60},
       "validation": {retries: 2, backoff: "none"}
     }
     ```

  2. **Automatic Fallback:**
     - Use alternative when primary fails
     ```
     IF primary_tool.fails():
       result = fallback_tool.execute()
     ```

  3. **Automatic Recovery:**
     - Detect degraded state
     - Trigger recovery procedure
     ```
     IF success_rate < 80%:
       trigger_recovery()
       # Clear caches
       # Restart connections
       # Reset state
     ```

  4. **Checkpoint Recovery:**
     - Resume from last good state
     - Don't restart from beginning
     ```
     IF execution_fails:
       last_checkpoint = load_checkpoint()
       resume_from(last_checkpoint)
     ```

- **Self-healing dashboard:**
  - Healing events logged
  - Success rate tracked
  - Escalation when healing fails

**Segment 4: Production Hardening (11 min)**

- **Hardening checklist:**
  - [ ] All failure modes have handling
  - [ ] Circuit breakers on external calls
  - [ ] Bulkhead isolation for agents
  - [ ] Self-healing for common failures
  - [ ] Graceful degradation defined
  - [ ] Monitoring for all components
  - [ ] Alerts for critical failures
  - [ ] Runbook for manual intervention

- **Testing hardened system:**
  - Re-run chaos experiments
  - Verify improvements
  - Document remaining gaps

- **Reliability metrics:**
  - MTBF: Mean Time Between Failures
  - MTTR: Mean Time To Recovery
  - Availability: Uptime percentage
  - Error budget: Acceptable failure rate

-----

### **Self-Paced Exercises (75 minutes total)**

**Exercise 2.1: Implement Circuit Breakers (25 minutes)**

*Add circuit breakers to your system*

```markdown
# Circuit Breaker Implementation

## Circuit Breaker 1: MCP Tool Calls

### Configuration
```json
{
  "circuit_breaker": {
    "name": "mcp_tools",
    "failure_threshold": 5,
    "reset_timeout_seconds": 60,
    "half_open_max_calls": 1
  }
}
```

### Implementation Location
[Where in your system this is added]

### Protected Operations
- Filesystem read/write
- GitHub API calls
- [Other MCP operations]

### State Tracking
```json
{
  "current_state": "CLOSED",
  "failure_count": 0,
  "last_failure": null,
  "trip_count": 0,
  "last_trip": null
}
```

### Testing
- [ ] Trigger 5 failures - verify circuit opens
- [ ] Wait 60s - verify half-open state
- [ ] Successful call - verify circuit closes
- [ ] Log circuit state changes

---

## Circuit Breaker 2: AI API Calls

### Configuration
```json
{
  "circuit_breaker": {
    "name": "ai_api",
    "failure_threshold": 3,
    "reset_timeout_seconds": 120,
    "half_open_max_calls": 1
  }
}
```

[Continue documentation]

---

## Verification Results

| Circuit Breaker | Opens Correctly | Resets Correctly | Logging Works |
|-----------------|-----------------|------------------|---------------|
| MCP Tools | ✓/✗ | ✓/✗ | ✓/✗ |
| AI API | ✓/✗ | ✓/✗ | ✓/✗ |
```

**Deliverable:** Circuit breaker implementation + verification

-----

**Exercise 2.2: Implement Self-Healing (25 minutes)**

*Add automatic recovery mechanisms*

```markdown
# Self-Healing Implementation

## Healing Mechanism 1: Automatic Retry with Backoff

### Configuration
```json
{
  "retry_policy": {
    "tool_failures": {
      "max_retries": 3,
      "backoff_type": "exponential",
      "initial_delay_ms": 1000,
      "max_delay_ms": 30000
    },
    "ai_failures": {
      "max_retries": 2,
      "backoff_type": "fixed",
      "delay_ms": 5000
    }
  }
}
```

### Implementation
[How and where implemented]

### Logging
Each retry logs:
- Attempt number
- Error that triggered retry
- Delay before next attempt
- Final outcome

---

## Healing Mechanism 2: Fallback Strategies

### Tool Fallbacks
| Primary Tool | Fallback | Trigger |
|--------------|----------|---------|
| GitHub MCP | Local filesystem | GitHub unavailable |
| Web search | Cached results | Search API down |
| [Tool] | [Fallback] | [Trigger] |

### Implementation
```
function read_template(path):
  TRY:
    return github_mcp.read(path)
  CATCH GitHubError:
    log("GitHub unavailable, using local fallback")
    return filesystem.read(local_path)
```

---

## Healing Mechanism 3: State Recovery

### Checkpoint Triggers
- After each successful agent completion
- Before risky operations
- Every 5 minutes during long tasks

### Recovery Process
1. Detect failure
2. Load last checkpoint
3. Verify checkpoint integrity
4. Resume from checkpoint
5. Log recovery event

### Testing
- [ ] Force failure mid-execution
- [ ] Verify checkpoint loaded
- [ ] Confirm correct resumption
- [ ] Check no duplicate work

---

## Self-Healing Dashboard Metrics

| Metric | Current Value | Target |
|--------|---------------|--------|
| Auto-healed failures | /week | |
| Healing success rate | % | >90% |
| Avg recovery time | seconds | <30s |
| Escalations to human | /week | <5 |
```

**Deliverable:** Self-healing implementation + test results

-----

**Exercise 2.3: Module Capstone - Reliability Report (25 minutes)**

*Complete reliability engineering documentation*

```markdown
# Reliability Engineering Report

## System: [Your Agent System]
## Report Date: [Date]
## Author: [Name]

---

## Executive Summary

[2-3 paragraphs summarizing reliability work done, key findings, and current state]

---

## Chaos Testing Summary

### Tests Conducted
| Experiment | Hypothesis Confirmed | Issues Found | Fixed |
|------------|---------------------|--------------|-------|
| MCP Failure | Yes/No/Partial | N | Y/N |
| API Timeout | | | |
| Infinite Loop | | | |
| [Others] | | | |

### Key Findings
1. [Finding]
2. [Finding]
3. [Finding]

### Critical Issues Resolved
1. **Issue:** [Description]
   - **Impact:** [What could have happened]
   - **Fix:** [What was done]

---

## Reliability Patterns Implemented

### Circuit Breakers
| Name | Threshold | Timeout | Status |
|------|-----------|---------|--------|
| MCP Tools | 5 | 60s | Active |
| AI API | 3 | 120s | Active |

### Self-Healing
| Mechanism | Coverage | Success Rate |
|-----------|----------|--------------|
| Auto-retry | All tools | X% |
| Fallbacks | N tools | X% |
| Checkpoint recovery | Agents | X% |

### Bulkhead Isolation
[Describe isolation implemented]

---

## Reliability Metrics

### Current State
| Metric | Value | Target | Status |
|--------|-------|--------|--------|
| Success rate | X% | >95% | ✓/✗ |
| MTBF | X hours | >24h | ✓/✗ |
| MTTR | X min | <5min | ✓/✗ |
| Error rate | X% | <5% | ✓/✗ |

### Before vs After Chaos Testing
| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| Success rate | X% | X% | +X% |
| Graceful failures | X% | X% | +X% |
| Auto-healed | X% | X% | +X% |

---

## Production Hardening Checklist

- [x] Failure mode catalog complete
- [x] Chaos tests executed (X experiments)
- [x] Circuit breakers implemented
- [x] Self-healing mechanisms active
- [ ] All critical paths protected
- [ ] Monitoring covers all components
- [ ] Alerts configured
- [ ] Runbook created
- [ ] Team trained on incident response

---

## Remaining Risks

| Risk | Likelihood | Impact | Mitigation Plan |
|------|------------|--------|-----------------|
| [Risk] | H/M/L | H/M/L | [Plan] |

---

## Recommendations

1. [Recommendation for further improvement]
2. [Recommendation]
3. [Recommendation]

---

## Appendix: Runbook

### Incident: System-Wide Failure
1. Check dashboard for error pattern
2. Identify failing component
3. Check circuit breaker states
4. [Continue steps]

### Incident: Single Agent Failure
[Steps]

### Incident: External Service Outage
[Steps]
```

**Deliverable:** `reliability-engineering-report.md`

-----

# **APPENDICES**

## **Appendix A: Chaos Testing Checklist**

```markdown
# Chaos Testing Safety Checklist

## Before Testing
- [ ] Test environment isolated from production
- [ ] Monitoring dashboard open and visible
- [ ] Rollback procedure documented
- [ ] Team notified of testing
- [ ] Kill switch ready

## During Testing
- [ ] Recording all observations
- [ ] Monitoring key metrics
- [ ] Ready to abort if needed
- [ ] Timing each experiment

## After Testing
- [ ] All injected failures removed
- [ ] System returned to normal state
- [ ] Results documented
- [ ] Issues logged for fixing
- [ ] Lessons learned captured
```

-----

## **Appendix B: Circuit Breaker Configuration Templates**

```json
{
  "circuit_breakers": {
    "default": {
      "failure_threshold": 5,
      "success_threshold": 2,
      "timeout_seconds": 60,
      "half_open_max_calls": 3
    },
    "critical_services": {
      "failure_threshold": 3,
      "success_threshold": 3,
      "timeout_seconds": 120,
      "half_open_max_calls": 1
    },
    "non_critical": {
      "failure_threshold": 10,
      "success_threshold": 1,
      "timeout_seconds": 30,
      "half_open_max_calls": 5
    }
  }
}
```

-----

## **Appendix C: Module Evaluation Rubric**

```markdown
# Chaos Testing & Reliability - Evaluation Rubric

**Total Points: 20 (4 criteria × 5 points each)**

## Criterion 1: Chaos Testing (5 points)

| Score | Description |
|-------|-------------|
| 5 | Comprehensive failure catalog. 5+ well-designed experiments. Thorough documentation. Clear findings and fixes. |
| 4 | Good catalog and experiments. Most failure modes covered. Good documentation. |
| 3 | Basic testing done. Some experiments. Adequate documentation. |
| 2 | Limited testing. Few experiments. Poor documentation. |
| 1 | No meaningful chaos testing. |

## Criterion 2: Reliability Patterns (5 points)

| Score | Description |
|-------|-------------|
| 5 | Circuit breakers, bulkheads, and self-healing all implemented. Well-configured. Tested and verified. |
| 4 | Multiple patterns implemented. Working correctly. |
| 3 | At least one pattern implemented. Basically working. |
| 2 | Patterns attempted but not working correctly. |
| 1 | No reliability patterns implemented. |

## Criterion 3: Self-Healing (5 points)

| Score | Description |
|-------|-------------|
| 5 | Comprehensive self-healing. Multiple mechanisms. High auto-recovery rate. Well-tested. |
| 4 | Good self-healing coverage. Works for common failures. |
| 3 | Basic self-healing. Works for some cases. |
| 2 | Minimal self-healing. Limited effectiveness. |
| 1 | No self-healing implemented. |

## Criterion 4: Documentation & Metrics (5 points)

| Score | Description |
|-------|-------------|
| 5 | Complete reliability report. Clear metrics. Before/after comparison. Runbook created. |
| 4 | Good documentation. Most metrics tracked. |
| 3 | Basic documentation. Some metrics. |
| 2 | Limited documentation. Few metrics. |
| 1 | No documentation. |
```

-----

**END OF ADVANCED MODULE 2**
