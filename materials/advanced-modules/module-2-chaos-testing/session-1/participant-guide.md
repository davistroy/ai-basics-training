# **ADVANCED MODULE 2 SESSION 1: CHAOS ENGINEERING FUNDAMENTALS**

**Module:** Advanced Module 2: Chaos Testing & Reliability Engineering
**Session:** 1 of 2
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Module Navigation:** Session 1 | [Session 2 →](/home/user/ai-basics-training/materials/advanced-modules/module-2-chaos-testing/session-2/participant-guide.md)

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

By the end of this session, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Understand chaos engineering principles and the experiment cycle | Workshop + Exercise 1.2 |
| 2 | Identify and categorize AI agent failure modes systematically | Exercise 1.1 |
| 3 | Design structured chaos experiments with clear hypotheses | Exercise 1.2 |
| 4 | Set up safe testing environments and execute chaos tests | Exercise 1.3 |

---

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Block 3 certification completed
- [ ] Working agent system deployed (from Block 3)
- [ ] Basic monitoring and logging in place
- [ ] Ability to observe your agent system's behavior

**Not ready?** Ensure your Block 3 agent system is operational before beginning chaos testing.

---

## Key Concepts

### Concept 1: Chaos Engineering

**Definition:**
A discipline of experimenting on a system to build confidence in its capability to withstand turbulent production conditions

**Why It Matters:**
AI agents interact with external services, MCP servers, and APIs - all of which can fail. Chaos engineering helps you find and fix failure modes before your clients discover them.

**Core Principle:**
> "Break it in testing so it doesn't break in production"

**The Chaos Engineering Cycle:**
```
1. Define steady state (what "working" looks like)
2. Hypothesize what will happen during failure
3. Inject failure in controlled environment
4. Observe actual behavior
5. Fix weaknesses found
6. Repeat
```

**Common Mistake:**
Testing randomly without hypotheses - chaos engineering is systematic and hypothesis-driven, not random breaking

---

### Concept 2: AI Agent Failure Modes

**Definition:**
The specific ways an AI agent system can fail, categorized by type and severity

**Why It Matters:**
AI agents have unique failure modes compared to traditional systems - non-deterministic outputs, complex orchestration, and external dependencies create failure scenarios you must plan for.

**The Five Categories:**

| Category | Examples | Key Characteristic |
|----------|----------|-------------------|
| **Tool Failures** | MCP server down, API timeout | External tool unavailable |
| **AI Failures** | Hallucination, context loss, infinite loop | LLM behavior issues |
| **Orchestration Failures** | Handoff fails, state corruption | Multi-agent coordination |
| **Resource Failures** | Token limit, budget exceeded | Resource constraints |
| **External Failures** | Network, auth, service outage | Infrastructure issues |

**When to Use:**
Use this categorization when creating your failure mode catalog to ensure comprehensive coverage

**When NOT to Use:**
Don't get stuck on categorization - if you're unsure which category, just document the failure

---

### Concept 3: Chaos Experiment Structure

**Definition:**
A rigorous framework for testing system resilience through controlled failure injection

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| **Hypothesis** | What you expect to happen | "Agent will retry 3x with backoff" |
| **Steady State** | Metrics defining "working" | "Success rate >95%, latency <30s" |
| **Injection** | How to cause the failure | "Disable MCP server for 60s" |
| **Observation** | What to monitor | "Logs, metrics, error messages" |
| **Rollback** | How to stop and recover | "Restore config, restart server" |
| **Success Criteria** | Checklist of expected behaviors | "☐ Detects failure ☐ Retries ☐ Fails gracefully" |

**Visual Reference:**
```
Hypothesis → Steady State → Inject Failure
                                    ↓
Success Criteria ← Observe ← (System Response)
       ↓
   Fix Issues → Rollback
```

---

### Concept 4: Safe Testing Environment

**Definition:**
An isolated, monitored environment where failures can be injected without production impact

**Key Requirements:**
- **Isolated**: Separate from production - no shared resources
- **Monitored**: Real-time logs and metrics visible
- **Labeled**: Clear "CHAOS TEST" marking in all outputs
- **Test data only**: No real customer data
- **Rollback ready**: Can stop and restore immediately

**Kill Switch Pattern:**
```
IF chaos_test_running AND
   (error_rate > 50% OR
    system_unresponsive OR
    user_triggered):
  STOP chaos injection
  RESTORE normal operation
  ALERT operator
```

**Common Mistake:**
Testing in production without safeguards - always start in isolated environments

---

### Quick Reference: Failure Mode Analysis

**Template for documenting each failure:**

| Element | Purpose | Format |
|---------|---------|--------|
| **What** | Describe the failure | "MCP server becomes unavailable" |
| **Likelihood** | How often it occurs | Common / Occasional / Rare |
| **Impact** | Severity if it happens | Critical / High / Medium / Low |
| **Detection** | How to identify it | "Connection timeout error" |
| **Current handling** | What happens now | "Agent crashes" |
| **Desired handling** | What should happen | "Retry 3x, fail gracefully" |

**Priority = Likelihood × Impact** - Test high-priority failures first

---

## Workshop Recap

### Session Summary

**Today's Focus:** Introduction to chaos engineering principles, failure mode analysis, experiment design, and safe testing practices for AI agent systems

**Key Points from Each Segment:**

**Segment 1: Introduction to Chaos Engineering**
- Chaos engineering is systematic, hypothesis-driven resilience testing
- The six-step cycle: define, hypothesize, inject, observe, fix, repeat
- AI agents have unique failure modes requiring specialized testing
- Safety principles: start small, have rollback, monitor closely

**Segment 2: AI Agent Failure Modes**
- Five categories: Tool, AI, Orchestration, Resource, External
- Each failure mode needs six attributes documented
- Prioritize testing by likelihood × impact
- Create comprehensive failure catalog before testing

**Segment 3: Designing Chaos Experiments**
- Six required elements: hypothesis, steady state, injection, observation, rollback, success criteria
- All elements are mandatory for rigorous testing
- Specific hypotheses lead to actionable findings
- Document expected vs actual results

**Segment 4: Safe Testing Environment**
- Never test without isolation and monitoring
- Real-time observability is required, not optional
- Implement kill switch for immediate stop capability
- Use Chaos Testing Safety Checklist (Appendix A)

### Demo Recap

**What Was Demonstrated:**
Example chaos experiment design for MCP server failure scenario

**Key Steps:**
1. Defined hypothesis with specific behaviors
2. Established steady state metrics
3. Chose safe injection method (rename config)
4. Planned observation approach
5. Documented rollback procedure
6. Created checklist of success criteria

**Result:**
Complete experiment template ready for execution with all safety measures

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 1.1 | 25 min | `failure-mode-catalog.md` | Systematic failure analysis |
| 1.2 | 25 min | `chaos-experiment-suite.md` | Experiment design |
| 1.3 | 25 min | Test results documentation | Hands-on chaos testing |

---

### Exercise 1.1: Failure Mode Catalog (25 minutes)

**Purpose:**
Create a comprehensive catalog of all ways your agent system can fail, categorized and prioritized for testing

**You Will Create:**
A complete failure mode catalog with categorized failures and priority matrix

---

#### Instructions

**Step 1: Set up your catalog document**

Create a new file: `failure-mode-catalog.md`

Use this structure:
```markdown
# Failure Mode Catalog

## System: [Your Agent System Name]
## Date: [Today's date]

### Tool Failures
[Document all tool-related failures]

### AI Failures
[Document all AI/LLM-related failures]

### Orchestration Failures
[Document all multi-agent coordination failures]

### Resource Failures
[Document all resource constraint failures]

### External Failures
[Document all infrastructure/service failures]

### Failure Priority Matrix
[Prioritized list for testing]
```

**Step 2: Document Tool Failures**

For each way your agent's tools can fail, create an entry:

```markdown
#### TF-001: [Failure Name]
- **Description:** [What fails and how]
- **Likelihood:** [Common/Occasional/Rare]
- **Impact:** [Critical/High/Medium/Low]
- **Detection:** [How you know it happened]
- **Current handling:** [What happens now]
- **Symptoms:** [What user/system sees]
```

Examples to consider:
- MCP server unavailable (filesystem, GitHub, etc.)
- API rate limiting (429 errors)
- API timeout (no response)
- Malformed API response
- Tool returns error

**Step 3: Document AI Failures**

Catalog LLM-specific failures:

```markdown
#### AF-001: [Failure Name]
- **Description:** [What fails and how]
- **Likelihood:** [Common/Occasional/Rare]
- **Impact:** [Critical/High/Medium/Low]
- **Detection:** [How you know it happened]
- **Current handling:** [What happens now]
```

Examples to consider:
- Context window exceeded
- Infinite loop (repeated actions)
- Hallucination (incorrect information)
- Wrong tool choice
- Prompt injection vulnerability

**Step 4: Document Orchestration, Resource, and External Failures**

Continue with remaining categories following the same template.

**Orchestration examples:**
- Agent handoff failure
- State corruption
- Deadlock between agents

**Resource examples:**
- Token limit exceeded
- Cost budget exceeded
- Memory constraints

**External examples:**
- Network timeout
- Authentication expiration
- Third-party service outage

**Step 5: Create Priority Matrix**

Build a table prioritizing all failures:

```markdown
## Failure Priority Matrix

| ID | Failure | Likelihood | Impact | Priority |
|----|---------|------------|--------|----------|
| TF-001 | MCP unavailable | Medium | High | **1** |
| AF-002 | Infinite loop | Low | Critical | **2** |
| [Continue sorted by priority...]
```

**Priority calculation:**
- High likelihood × High impact = Priority 1
- Low likelihood × Critical impact = Priority 2
- High likelihood × Medium impact = Priority 3
- Medium × Medium = Priority 4
- And so on...

**Step 6: Review Your Work**

Check that your deliverable includes:
- [ ] At least 10 documented failure modes
- [ ] All five categories covered
- [ ] Each failure has all six attributes
- [ ] Priority matrix sorted by priority
- [ ] Specific to your actual agent system

---

#### Deliverable Specification

**File Name:** `failure-mode-catalog.md`

**Location:** Your project repository (recommend `/chaos-testing` folder)

**Format Requirements:**
- Markdown format
- Clear categorization by failure type
- Consistent ID numbering (TF-001, AF-001, etc.)
- Priority matrix sorted highest to lowest

**Quality Criteria:**
- [ ] Comprehensive coverage (10+ failures minimum)
- [ ] Specific to your system (not generic)
- [ ] Likelihood and impact assessments realistic
- [ ] Current handling honestly documented
- [ ] Priority matrix guides testing order

---

#### Example

**Scenario:** Block 3 multi-agent research system using filesystem and GitHub MCP servers

**Input:** Agent system with Research Agent, Writing Agent, MCP servers

**Output:**
```markdown
# Failure Mode Catalog

## System: Research & Writing Multi-Agent System

### Tool Failures

#### TF-001: Filesystem MCP Server Unavailable
- **Description:** Filesystem MCP server stops responding or connection fails
- **Likelihood:** Occasional (happens during restarts or config changes)
- **Impact:** High - Research agent cannot read source documents
- **Detection:** Connection timeout after 10s
- **Current handling:** Agent crashes with "Cannot connect to server" error
- **Symptoms:** User sees error, no research results produced

#### TF-002: GitHub API Rate Limit
- **Description:** GitHub API returns 429 Too Many Requests
- **Likelihood:** Common during heavy usage
- **Impact:** Medium - Delays but doesn't stop execution
- **Detection:** 429 response code in logs
- **Current handling:** Request fails, no retry
- **Symptoms:** Missing repository information

### AI Failures

#### AF-001: Research Agent Context Window Exceeded
- **Description:** Source documents too large for context window
- **Likelihood:** Occasional (large codebases)
- **Impact:** High - Cannot complete research
- **Detection:** Token count error from API
- **Current handling:** Agent fails with token error
- **Symptoms:** No research output, cryptic error message

### Priority Matrix

| ID | Failure | Likelihood | Impact | Priority |
|----|---------|------------|--------|----------|
| TF-001 | Filesystem MCP unavailable | Medium | High | **1** |
| AF-001 | Context window exceeded | Medium | High | **2** |
| TF-002 | GitHub rate limit | High | Medium | **3** |
```

**Why This Works:**
- Specific to actual system (Research & Writing agents)
- Realistic likelihood/impact based on experience
- Honest about current handling (mostly crashes)
- Prioritized for testing MCP failure first

---

#### Tips & Troubleshooting

**Tips:**
- Review your agent's error logs for real failures you've encountered
- Ask: "What external service does my agent depend on?" - each is a potential failure
- Consider both common failures (API timeouts) and rare but critical ones (infinite loops)
- Be honest about current handling - most agents crash on failures, that's okay and normal

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Can't think of 10 failures | Review the five categories, ensure each has at least 2 entries |
| Unsure about likelihood | Base on experience: seen it weekly=Common, monthly=Occasional, never but possible=Rare |
| Difficult to prioritize | Start with failures that would most embarrass you in front of a client |
| Generic descriptions | Add specifics: which API? which MCP server? which agent? |

---

### Exercise 1.2: Design Chaos Experiments (25 minutes)

**Purpose:**
Design rigorous chaos experiments for your top priority failures with complete structure and safety measures

**You Will Create:**
A suite of 5 chaos experiments with all six required elements

---

#### Instructions

**Step 1: Create experiment suite document**

Create file: `chaos-experiment-suite.md`

```markdown
# Chaos Experiment Suite

## System: [Your Agent System Name]
## Date: [Today's date]

## Experiment 1: [Failure Name]
[Full experiment structure]

## Experiment 2: [Failure Name]
[Full experiment structure]

[Continue for 5 experiments]
```

**Step 2: Choose your top 5 priority failures**

From your failure mode catalog priority matrix, select the top 5 failures to test.

**Step 3: Design Experiment 1 (your #1 priority failure)**

Use this complete template for each experiment:

```markdown
## Experiment 1: [Failure Name]

### Hypothesis
When [failure condition], the system will:
1. [Expected behavior 1]
2. [Expected behavior 2]
3. [Expected behavior 3]
4. [Expected behavior 4]

### Steady State Definition
- [Metric 1]: [Normal value]
- [Metric 2]: [Normal value]
- [Metric 3]: [Normal value]

### Failure Injection
- **Method:** [How you will cause the failure]
- **Duration:** [How long - start with 60 seconds]
- **Scope:** [What's affected]

### Observation Plan
- [ ] [What to watch #1]
- [ ] [What to watch #2]
- [ ] [What to watch #3]
- [ ] [What to watch #4]

### Rollback Plan
1. [Step to stop injection]
2. [Step to restore normal]
3. [Step to verify recovery]

### Success Criteria
System should:
- [ ] [Expected behavior 1 - make it checkable]
- [ ] [Expected behavior 2]
- [ ] [Expected behavior 3]
- [ ] [Expected behavior 4]

### Expected vs Actual Results
| Behavior | Expected | Actual | Pass/Fail |
|----------|----------|--------|-----------|
| [Behavior 1] | [Value] | | |
| [Behavior 2] | [Value] | | |
| [Behavior 3] | [Value] | | |
```

**Step 4: Complete all six elements**

For each element, make it specific:

**Hypothesis example:**
- ❌ Bad: "System handles MCP failure"
- ✅ Good: "Agent detects MCP failure within 10s, retries 3x with exponential backoff, fails gracefully with clear error message, does not corrupt state"

**Injection example:**
- ❌ Bad: "Break MCP server"
- ✅ Good: "Rename ~/.config/claude/mcp.json to mcp.json.disabled, duration 60 seconds"

**Success criteria example:**
- ❌ Bad: "Works correctly"
- ✅ Good: "☐ Logs show 'MCP connection failed' within 10s ☐ 3 retry attempts logged ☐ Final error message includes helpful instructions"

**Step 5: Design experiments 2-5**

Repeat the template for your remaining 4 priority failures. Cover different categories if possible:
- At least one Tool Failure
- At least one AI or Orchestration Failure
- Remaining can be highest priority regardless of category

**Step 6: Review your experiment suite**

Check that each experiment has:
- [ ] Specific hypothesis with measurable behaviors
- [ ] Defined steady state metrics
- [ ] Clear injection method you can actually execute
- [ ] Observation plan listing what to monitor
- [ ] Safe rollback procedure
- [ ] Checkable success criteria

---

#### Deliverable Specification

**File Name:** `chaos-experiment-suite.md`

**Location:** Your project repository `/chaos-testing` folder

**Format Requirements:**
- Markdown format
- 5 complete experiments
- All six elements present in each
- Experiments address different failure modes

**Quality Criteria:**
- [ ] All 5 experiments complete (not placeholders)
- [ ] Hypotheses are specific and testable
- [ ] Injection methods are safe and reversible
- [ ] Rollback plans are documented
- [ ] Success criteria are checkboxes
- [ ] Expected vs Actual table included

---

#### Example

See Session 1 workshop content for complete MCP Server Failure example. Additional experiment examples:

**Experiment 2: AI Response Timeout**

```markdown
## Experiment 2: AI API Response Timeout

### Hypothesis
When AI API response exceeds 60 seconds, the system will:
1. Detect timeout after 60s
2. Log timeout error with context
3. Not retry (timeouts indicate overload, retries worsen it)
4. Return clear error to user

### Steady State
- AI API response time: <5s average
- Success rate: >95%
- Timeout rate: <1%

### Failure Injection
- **Method:** Use proxy to delay AI API responses by 65 seconds
- **Duration:** 3 requests (simulate multiple timeouts)
- **Scope:** All AI API calls during test window

### Observation Plan
- [ ] Watch agent execution logs
- [ ] Monitor API call timing
- [ ] Track timeout error messages
- [ ] Verify user receives error notification

### Rollback Plan
1. Remove proxy configuration
2. Verify normal API response times (<5s)
3. Test successful AI call completion

### Success Criteria
- [ ] Timeout detected after 60s (not waiting forever)
- [ ] Error logged with "AI API timeout" message
- [ ] No retry attempts (confirms timeout-specific handling)
- [ ] User error message clear and actionable

### Expected vs Actual Results
| Behavior | Expected | Actual | Pass/Fail |
|----------|----------|--------|-----------|
| Timeout detection | 60s | | |
| Retry attempts | 0 | | |
| Error message quality | Clear | | |
| User notified | Yes | | |
```

---

#### Tips & Troubleshooting

**Tips:**
- Start with safer injection methods (config changes) before riskier ones (process killing)
- 60 seconds is a good default injection duration for first tests
- Write rollback steps BEFORE you design injection - ensures you can recover
- Make success criteria binary (yes/no) so you can clearly mark pass/fail

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Hypothesis too vague | Add numbers: "retry 3 times", "within 10 seconds", "error code 500" |
| Don't know injection method | Start simple: config rename, environment variable change, localhost port blocking |
| Unsure what to observe | At minimum: logs, error messages, agent completion status |
| Missing rollback plan | Reverse your injection method: renamed file? Rename back. Blocked port? Unblock. |

---

### Exercise 1.3: Execute First Chaos Tests (25 minutes)

**Purpose:**
Execute at least 3 chaos experiments in a safe environment and document actual results compared to hypotheses

**You Will Create:**
Test execution results documenting expected vs actual behavior and issues found

---

#### Instructions

**Step 1: Set up safe testing environment**

Before running ANY chaos experiments:

- [ ] Create test copy of agent system (separate from production)
- [ ] Verify you can see logs in real-time (tail logs, monitoring dashboard, etc.)
- [ ] Test your rollback procedure (ensure you can undo changes)
- [ ] Add "CHAOS_TEST=true" or similar flag to environment
- [ ] Notify anyone who might be affected by testing

**Safety checklist** (from Appendix A - complete this first):
- [ ] Test environment isolated from production
- [ ] Monitoring dashboard open and visible
- [ ] Rollback procedure documented and tested
- [ ] Team notified of testing window
- [ ] Kill switch ready (can stop immediately)

**Step 2: Execute Experiment 1**

Choose your highest priority experiment from Exercise 1.2.

1. **Before injection - verify steady state:**
   - Run agent normally
   - Confirm it works as expected
   - Note baseline metrics

2. **Inject failure:**
   - Follow injection method from experiment design
   - Start timer for duration
   - Monitor continuously

3. **Observe behavior:**
   - Watch logs stream in real-time
   - Check each item in observation plan
   - Note anything unexpected
   - Take screenshots of key moments

4. **Rollback:**
   - Follow rollback procedure
   - Verify system returns to normal
   - Test agent works again

5. **Document results:**

Create file: `chaos-test-results.md`

```markdown
# Chaos Test Results

## Experiment 1: [Name]

### Execution Details
- **Date:** [Date and time]
- **Experimenter:** [Your name]
- **Duration:** [How long test ran]
- **Environment:** [Test/Staging/Local]

### Results

#### Expected vs Actual

| Behavior | Expected | Actual | Pass/Fail |
|----------|----------|--------|-----------|
| [Behavior 1] | [Expected] | [What actually happened] | Pass/Fail |
| [Behavior 2] | [Expected] | [Actual] | Pass/Fail |
| [Behavior 3] | [Expected] | [Actual] | Pass/Fail |
| [Behavior 4] | [Expected] | [Actual] | Pass/Fail |

#### Observations
- [What happened - be specific]
- [Unexpected behaviors - anything surprising]
- [System responses - how did it react]

#### Logs Captured
```
[Paste relevant log entries showing failure detection, retries, errors]
```

#### Issues Found
1. **Issue:** [Specific problem discovered]
   - **Severity:** [Critical/High/Medium/Low]
   - **Fix needed:** [What should be done]

2. **Issue:** [Next issue if any]

#### Recommendations
1. [Actionable recommendation based on findings]
2. [Next steps]

### Hypothesis Confirmed?
[Yes/No/Partially]

**Explanation:** [Why hypothesis was or wasn't confirmed, what you learned]
```

**Step 3: Execute Experiments 2 and 3**

Repeat the process for at least 2 more experiments.

Tips:
- Start with safest/easiest experiments first
- Allow time between experiments for system to stabilize
- If an experiment finds critical issues, you may want to fix them before continuing

**Step 4: Summarize findings across all tests**

Add a summary section to your results file:

```markdown
## Summary Across All Tests

### Tests Conducted
| Experiment | Hypothesis Confirmed | Critical Issues | Fixed |
|------------|---------------------|-----------------|-------|
| 1: [Name] | Yes/No/Partial | [Number] | Y/N |
| 2: [Name] | Yes/No/Partial | [Number] | Y/N |
| 3: [Name] | Yes/No/Partial | [Number] | Y/N |

### Key Learnings
1. [Major insight from testing]
2. [Pattern observed across tests]
3. [Biggest surprise or gap found]

### Next Steps
1. [What to fix first based on findings]
2. [Additional experiments to run]
3. [Improvements to test process itself]
```

**Step 5: Review your work**

Check that your deliverable includes:
- [ ] At least 3 experiments executed
- [ ] Each has expected vs actual comparison
- [ ] Actual results documented (not left blank)
- [ ] Issues identified with severity ratings
- [ ] Log excerpts showing key moments
- [ ] Honest assessment of hypothesis confirmation

---

#### Deliverable Specification

**File Name:** `chaos-test-results.md`

**Location:** Your project repository `/chaos-testing` folder

**Format Requirements:**
- Markdown format
- Results for 3+ experiments
- Expected vs actual tables completed
- Log excerpts included
- Issues and recommendations documented

**Quality Criteria:**
- [ ] Actually executed (not simulated)
- [ ] Specific results documented
- [ ] Pass/fail clearly indicated
- [ ] Issues have severity and fix recommendations
- [ ] Learnings captured for future improvements

---

#### Example

**Scenario:** Testing MCP filesystem server failure

```markdown
# Chaos Test Results

## Experiment 1: Filesystem MCP Server Unavailable

### Execution Details
- **Date:** 2026-01-02 14:30
- **Experimenter:** [Name]
- **Duration:** 90 seconds (60s injection + 30s recovery observation)
- **Environment:** Local test environment

### Results

#### Expected vs Actual

| Behavior | Expected | Actual | Pass/Fail |
|----------|----------|--------|-----------|
| Detection time | <10s | 3s | **Pass** |
| Retries attempted | 3 | 0 | **Fail** |
| Graceful failure | Yes | No - crashed | **Fail** |
| Error message clear | Yes | Generic "Error" | **Fail** |
| State corrupted | No | Partial output saved | **Pass** |

#### Observations
- System detected MCP failure very quickly (3s)
- **CRITICAL**: No retry logic implemented at all - fails immediately
- Agent crashed with generic error instead of handling gracefully
- Error message was "Error executing tool" - not helpful for debugging
- Partial research results were saved before crash (good - no work lost)

#### Logs Captured
```
14:30:05 [Research Agent] Starting research task...
14:30:08 [MCP] Connection failed: Cannot connect to filesystem server
14:30:08 [Error] Error executing tool: filesystem.read
14:30:08 [Agent] Task failed
[CRASH]
```

#### Issues Found
1. **Issue:** No retry logic for MCP failures
   - **Severity:** High
   - **Fix needed:** Implement retry with exponential backoff (3 attempts)

2. **Issue:** Generic error messages
   - **Severity:** Medium
   - **Fix needed:** Wrap MCP errors with context and user-friendly explanation

3. **Issue:** Agent crashes instead of graceful failure
   - **Severity:** High
   - **Fix needed:** Add error handling to continue with degraded functionality or fail gracefully

#### Recommendations
1. Add retry logic ASAP - many MCP failures are transient
2. Improve error messaging - current errors don't help user understand what happened
3. Implement graceful degradation - can research proceed with cached data?

### Hypothesis Confirmed?
**No - Partially**

**Explanation:** Detection was faster than expected (3s vs <10s), which is good. However, the system failed all other criteria - no retries, crashes instead of graceful failure, poor error messaging. This test revealed significant gaps in error handling that must be addressed before production.
```

**Why This Works:**
- Specific measurements (3s detection time)
- Clear pass/fail on each criterion
- Actual log excerpts as evidence
- Honest about failures found
- Actionable recommendations with priority

---

#### Tips & Troubleshooting

**Tips:**
- Do a "dry run" first - verify you can inject and rollback without running full test
- Keep a terminal window open with live logs - don't rely on reviewing logs after
- Take screenshots during critical moments
- If something goes very wrong, use your kill switch immediately - safety first
- Document failures honestly - finding problems is the whole point!

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Can't inject failure safely | Start with simplest method: rename a config file temporarily |
| Not sure what to observe | At minimum watch: agent logs, completion status, error messages |
| System behaves unpredictably | This is a finding! Document the unpredictability as an issue |
| Test reveals critical bug | Excellent! Document it, stop testing, fix it, then continue |
| Can't complete in 25 min | Execute 3 experiments - you can run more after completing module |

---

## Templates & Resources

### Templates Provided This Session

| Template | Purpose | Location |
|----------|---------|----------|
| Failure Mode Analysis | Document each failure systematically | Below |
| Chaos Experiment Structure | Design rigorous experiments | Below |
| Test Results Documentation | Record experiment outcomes | Below |
| Safety Checklist | Ensure safe testing | Appendix A |

---

### Template 1: Failure Mode Analysis

```markdown
## Failure Mode: [Name]

**Category:** [Tool/AI/Orchestration/Resource/External]

- **What:** [Description of failure]
- **Likelihood:** [Common/Occasional/Rare]
- **Impact:** [Critical/High/Medium/Low]
- **Detection:** [How do we know it happened?]
- **Current handling:** [What happens now?]
- **Desired handling:** [What should happen?]
- **Priority:** [Calculated: Likelihood × Impact]
```

**Usage Instructions:**
1. Copy this template for each failure you identify
2. Fill in all fields based on your system's behavior
3. Be honest about current handling (most likely crashes)
4. Calculate priority to guide testing order

---

### Template 2: Chaos Experiment Structure

```markdown
## Experiment [N]: [Failure Name]

### Hypothesis
When [failure condition], the system will:
1. [Expected behavior 1]
2. [Expected behavior 2]
3. [Expected behavior 3]

### Steady State Definition
- [Metric 1]: [Normal value]
- [Metric 2]: [Normal value]

### Failure Injection
- **Method:** [How to cause failure]
- **Duration:** [How long]
- **Scope:** [What's affected]

### Observation Plan
- [ ] [What to monitor]
- [ ] [What to monitor]
- [ ] [What to monitor]

### Rollback Plan
1. [Step to stop]
2. [Step to restore]
3. [Step to verify]

### Success Criteria
System should:
- [ ] [Checkable behavior 1]
- [ ] [Checkable behavior 2]
- [ ] [Checkable behavior 3]

### Expected vs Actual Results
| Behavior | Expected | Actual | Pass/Fail |
|----------|----------|--------|-----------|
| | | | |
```

**Usage Instructions:**
1. Use this template for each experiment
2. Complete ALL six elements before executing
3. Test rollback procedure before injection
4. Make success criteria binary (yes/no checkboxes)

---

### Template 3: Test Results Documentation

```markdown
# Chaos Test Results: Experiment [N]

## Execution Details
- **Date:** [Date]
- **Experimenter:** [Name]
- **Duration:** [Time]
- **Environment:** [Test/Staging]

## Results

### Expected vs Actual
| Behavior | Expected | Actual | Pass/Fail |
|----------|----------|--------|-----------|
| | | | |

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

### Recommendations
1. [Recommendation]
2. [Recommendation]

## Hypothesis Confirmed?
[Yes/No/Partially - explain]
```

**Usage Instructions:**
1. Create one results document per experiment (or combine all in one file with sections)
2. Fill in expected vs actual while test is running
3. Paste actual log excerpts as evidence
4. Document ALL issues found, even minor ones

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Principles of Chaos Engineering | Documentation | https://principlesofchaos.org | Foundational reading |
| Chaos Engineering Book (O'Reilly) | Book | Search online | Deeper dive into practices |
| Advanced Failure Injection Tools | Tools | Research: Toxiproxy, Chaos Mesh | When ready for automated testing |

---

### Module Appendix References

For this session's exercises, you may need:

- **Appendix A:** Chaos Testing Safety Checklist - Complete before executing any experiments

See the main module document for full appendix content.

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next session, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Understand chaos engineering principles and cycle | Completed Exercise 1.2 with proper experiment structure | ☐ |
| 2 | Identify and categorize failure modes | Created comprehensive failure catalog (Ex 1.1) | ☐ |
| 3 | Design chaos experiments | Designed 5 experiments with all 6 elements (Ex 1.2) | ☐ |
| 4 | Execute chaos tests safely | Ran 3+ experiments and documented results (Ex 1.3) | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 1.1 output | `failure-mode-catalog.md` | Project repo /chaos-testing | ☐ |
| Exercise 1.2 output | `chaos-experiment-suite.md` | Project repo /chaos-testing | ☐ |
| Exercise 1.3 output | `chaos-test-results.md` | Project repo /chaos-testing | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** Did the systematic approach to failure analysis change how you think about reliability?

2. **What's still fuzzy?** Are you unsure about any part of experiment design or execution?

3. **How will you apply this?** Which failures you found need fixing before production deployment?

4. **What surprised you?** Were your agent's failure modes better or worse than expected?

---

## Getting Help

### Quick Answers
- **[Support Channel Name]** - Post questions, usually answered within 24 hours
- **Peer Discussion** - Tag your cohort for quick tips

### Common Questions This Session

**Q: My agent has dozens of potential failures - do I need to catalog all of them?**
A: Start with 10-15 covering all five categories. You can expand later. Focus on highest priority failures first.

**Q: What if I don't know how to inject a failure safely?**
A: Start with the safest method: temporarily renaming config files. You can progress to more advanced injection methods later.

**Q: My chaos test revealed my agent handles nothing gracefully - is that normal?**
A: Very normal! Most Block 3 agents focused on functionality, not resilience. That's exactly what chaos testing finds - you'll fix it in Session 2.

**Q: How do I know if my test environment is truly isolated?**
A: Verify: (1) separate config files, (2) different data directory, (3) can't affect production users. When in doubt, add more separation.

**Q: Can I test in production with safeguards?**
A: Not recommended for first chaos tests. Master the approach in test environments first. Production chaos testing requires extensive additional safeguards beyond this session.

### When to Ask for Help

- **Before asking:** Check the troubleshooting sections in each exercise
- **Good to ask:** "I tried [X injection method] but got [Y unexpected result]. Here's my setup..."
- **Include:** Your specific scenario, what you tried, actual results, and relevant logs

### Office Hours

[If applicable]
- **When:** [Day/Time]
- **Where:** [Platform/Link]
- **For:** Live troubleshooting and deeper questions

---

## Looking Ahead

### Next Session Preview: Session 2 - Advanced Reliability Patterns

**Focus:**
Implement circuit breakers, bulkhead isolation, and self-healing mechanisms based on your chaos testing findings

**How It Builds on This Session:**
The failures you discovered in chaos testing tell you where to implement reliability patterns. Circuit breakers prevent cascading failures. Self-healing handles transient issues automatically.

**To Prepare:**
- [ ] Complete all Session 1 exercises
- [ ] Review your chaos test findings - which failures need circuit breakers?
- [ ] Identify good candidates for self-healing (transient vs permanent failures)

---

## Glossary

| Term | Definition |
|------|------------|
| **Chaos Engineering** | Discipline of experimenting on systems to build confidence in resilience |
| **Steady State** | Metrics that define "normal working" system behavior |
| **Failure Injection** | Deliberately causing a specific failure in controlled way |
| **Hypothesis** | Specific prediction of system behavior during failure |
| **Kill Switch** | Mechanism to immediately stop chaos injection and restore normal operation |
| **Rollback** | Process of undoing failure injection and returning to steady state |
| **Graceful Failure** | System failing in controlled way with clear messaging vs crashing |
| **Transient Failure** | Temporary failure that resolves itself (worth retrying) |
| **Permanent Failure** | Failure that won't resolve without intervention (retries won't help) |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial participant guide created for Module 2 Session 1 |

---

**Navigation:** Session 1 | [Session 2 →](/home/user/ai-basics-training/materials/advanced-modules/module-2-chaos-testing/session-2/participant-guide.md)
