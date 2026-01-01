# **BLOCK 2 WEEK 2: Building Your First Workflow**

**Block:** 2: AI Workflow Engineering
**Week:** 2 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** [← Week 1](../week-1/participant-guide.md) | **Week 2** | [Week 3 →](../week-3/participant-guide.md)

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
| 1 | Build an end-to-end AI workflow with trigger, AI processing, and output | Exercise 2.1 |
| 2 | Implement basic error handling for common failure scenarios | Exercise 2.2 |
| 3 | Configure performance logging to track workflow executions | Exercise 2.3 |
| 4 | Apply the micro-agent pattern for reliable AI steps | All exercises |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Automation platform account created (Make, n8n, or your choice)
- [ ] Platform getting started tutorial completed
- [ ] Block 1 prompt template selected for automation
- [ ] Performance metrics defined (from Week 1 Exercise 1.3)

**Not ready?** Complete Week 1 exercises or reach out in the support channel for help.

---

## Key Concepts

### Concept 1: The Workflow Mindset

**Definition:**
Thinking in sequential steps rather than single prompts, where each step does one thing well and passes its output to the next step.

**Why It Matters:**
Breaking complex processes into steps makes workflows more reliable, debuggable, and maintainable. When something fails, you know exactly where.

**Core Principle:**
> Think in steps, not single prompts. Each step should do ONE thing well.

**Example:**
```
Instead of one complex prompt:
"Summarize this email, check for action items, format as bullet points, and send to Slack"

Break into steps:
1. Trigger: Receive email
2. Extract: Pull email content
3. Process: AI summarizes content
4. Format: Structure output as bullets
5. Deliver: Send to Slack
```

**Common Mistake:**
Trying to do too much in a single AI call. This makes debugging hard and increases failure points.

---

### Concept 2: Core Workflow Components

**Definition:**
Every workflow consists of five fundamental components that work together to process data automatically.

**Why It Matters:**
Understanding these components helps you design workflows systematically rather than improvising.

**The Five Components:**

| Component | Purpose | Example |
|-----------|---------|---------|
| **Trigger** | What starts the workflow | Manual button, email received, webhook, schedule |
| **Data Gathering** | Collect needed information | Read email content, fetch from API, pull from database |
| **AI Processing** | Transform data using AI | Summarize, generate, analyze, extract |
| **Quality Check** | Verify output meets standards | Score against rubric, check formatting |
| **Output** | Deliver the result | Send email, post to Slack, create document |

**Visual Reference:**
```
┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
│ Trigger  │───▶│  Gather  │───▶│    AI    │───▶│  Check   │───▶│  Output  │
│          │    │   Data   │    │ Process  │    │ Quality  │    │          │
└──────────┘    └──────────┘    └──────────┘    └──────────┘    └──────────┘
```

---

### Concept 3: The Micro-Agent Pattern

**Definition:**
A design pattern where AI operates within bounded steps (3-20 actions) embedded in larger deterministic workflows, rather than running autonomously.

**Why It Matters:**
Unbounded AI agents are unreliable in production. The micro-agent pattern gives you AI flexibility where needed with predictability elsewhere.

**The Pattern:**
```
Traditional DAG:     Step A → Step B → Step C → Step D
                     (all deterministic, all predefined)

Micro-Agent Pattern: [Deterministic] → [AI: 5-10 steps] → [Deterministic]
                     (flexibility where needed, predictability elsewhere)
```

**Why 3-20 Steps?**
- Bounds the context window (AI doesn't lose track)
- Limits scope of failures (contained blast radius)
- Easier to debug (clear start and end)
- Research shows agents degrade after 10-20 turns

**The 90% Reality Check:**
A 90% success rate sounds good, but would you use a web app that crashed 10% of the time? Production means reliability, not impressive demos.

---

### Concept 4: Error Handling Patterns

**Definition:**
Strategies for gracefully handling failures in workflow execution without crashing the entire process.

**Why It Matters:**
Things will go wrong - API limits, bad data, timeouts. Error handling determines whether your workflow fails gracefully or catastrophically.

**Common Failure Points:**

| Failure | Cause | Impact |
|---------|-------|--------|
| API rate limits | Too many requests | Workflow pauses or fails |
| Invalid input | Missing or malformed data | AI produces garbage |
| AI refusal | Content policy or confusion | No output generated |
| Timeout | Slow response | Step times out |

**Basic Error Handling Patterns:**
1. **Try/Catch:** Wrap risky steps, route failures separately
2. **Fallback Routes:** If primary fails, try alternative
3. **Alerts:** Notify yourself on failure
4. **Logging:** Record errors for later review

**The 80/20 Rule:**
> Handle the common failures first. Don't try to handle every edge case - focus on the 3-4 things that actually break.

---

### Quick Reference: Workflow Building Checklist

| Step | Question | Action |
|------|----------|--------|
| 1. Trigger | What starts this workflow? | Configure trigger module |
| 2. Data | What information is needed? | Set up data gathering |
| 3. AI | What should AI do? | Insert prompt template |
| 4. Quality | How do we verify output? | Add check (Week 3 focus) |
| 5. Output | Where does result go? | Configure destination |
| 6. Errors | What can fail? | Add error handlers |
| 7. Logging | How do we track? | Add logging step |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Building an end-to-end AI workflow with error handling and logging fundamentals.

**Key Points from Each Segment:**

**Segment 1: Workflow Design Principles**
- Think in steps, not single prompts
- Five core components: Trigger, Data, AI, Quality, Output
- Micro-agent pattern: bounded AI within deterministic workflows
- 3-20 steps keeps AI reliable
- Production means reliability, not impressive demos

**Segment 2: Live Workflow Build**
- Created new scenario/workflow
- Configured manual trigger with sample data
- Added AI module with prompt template
- Connected output module (email/Slack)
- Ran successful test execution

**Segment 3: Error Handling Fundamentals**
- Common failures: API limits, invalid input, timeouts
- Try/catch pattern for risky steps
- Fallback routes for alternatives
- Alerts to know when things break
- 80/20 rule: handle common failures first

**Segment 4: Logging and Monitoring**
- Log every execution from day one
- Track: timestamp, input, output, duration, status
- Simple options: Google Sheets, Airtable, platform logs
- "You can't improve what you don't measure"

### Demo Recap

**What Was Demonstrated:**
Building a complete workflow from scratch: Manual Trigger → AI Summary → Email Output

**Key Steps:**
1. Created new scenario with trigger
2. Added AI module with Claude/OpenAI
3. Configured output destination
4. Ran successful test execution

**Result:**
A working workflow that processes input through AI and delivers output.

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 2.1 | 35 min | Working workflow + `workflow-1-documentation.md` | Build end-to-end |
| 2.2 | 15 min | Error handling added | Make workflow resilient |
| 2.3 | 10 min | Logging configured | Track executions |

---

### Exercise 2.1: Build Your First Workflow

**Duration:** 35 minutes

**Purpose:**
Create a functional end-to-end workflow that automates a task from your Block 1 work. This is your first capstone component.

**You Will Create:**
A working workflow in your automation platform plus documentation of its structure and test results.

---

#### Instructions

**Step 1: Map Your Workflow Visually (5 min)**

Before building, plan your workflow:

```
[Trigger] → [Gather Data] → [AI Process] → [Quality Check] → [Output]
```

Document each step:
- What triggers it? (Manual for testing)
- What data is needed? (What input does AI need?)
- What prompt template to use? (From Block 1)
- What quality criteria to check? (From Block 1 rubric - detailed in Week 3)
- Where does output go? (Email, Google Doc, etc.)

**Step 2: Create New Workflow (3 min)**

In your platform:
1. Create a new scenario/workflow
2. Name it descriptively: "[Deliverable Type] Generator v1"
3. Save it

**Step 3: Configure Trigger (5 min)**

For testing, use a manual trigger:

**In Make:**
- Add "Custom webhook" or "Scenario start" module
- Configure with sample input data structure

**In n8n:**
- Add "Manual Trigger" node
- Configure with sample JSON data

**Sample Data Structure:**
```json
{
  "client_name": "Acme Corp",
  "project_type": "Digital Transformation",
  "key_details": "3-month assessment project, budget $150k"
}
```

**Step 4: Add AI Module (10 min)**

Add your AI processing step:

**For Claude (via HTTP):**
1. Add HTTP module
2. URL: `https://api.anthropic.com/v1/messages`
3. Method: POST
4. Headers:
   - `x-api-key: [your-key]`
   - `anthropic-version: 2023-06-01`
   - `content-type: application/json`
5. Body: Your prompt with variables inserted

**For OpenAI (native in Make):**
1. Add OpenAI module
2. Select "Create a completion" or "Create a chat completion"
3. Configure model and prompt

**Prompt Template Example:**
```
You are a professional consultant creating a [deliverable type].

Client: {{client_name}}
Project: {{project_type}}
Details: {{key_details}}

[Insert your Block 1 template instructions here]

Respond with the complete [deliverable type].
```

**Step 5: Add Output (5 min)**

Configure where results go:

**Simple option - Email:**
1. Add Email module
2. Configure recipient (yourself for testing)
3. Map AI response to email body

**Alternative - Google Doc:**
1. Add Google Docs module
2. Create new document
3. Map AI response to content

**Step 6: Test with Sample Data (5 min)**

Run your workflow:
1. Click "Run once" / "Execute workflow"
2. Watch each step execute
3. Verify output arrived at destination
4. Note execution time

Repeat 3+ times with different sample data.

**Step 7: Document Your Workflow (2 min)**

Use the template below to document.

---

#### Deliverable Specification

**File Name:** `workflow-1-documentation.md`

**Location:** Your Block 2 folder in GitHub repository

**Also Required:** Working workflow in your platform

**Quality Criteria:**
- [ ] Workflow runs successfully end-to-end
- [ ] AI produces expected output format
- [ ] Output arrives at designated destination
- [ ] 3+ successful test executions completed
- [ ] Documentation captures all steps

---

#### Template

```markdown
# Workflow: [Name]

**Version:** 1.0
**Created:** [Date]
**Platform:** [Make / n8n / Other]
**Status:** Testing

---

## Purpose

[What this workflow does - 2-3 sentences]

---

## Trigger

- **Type:** [Manual/Webhook/Schedule/etc.]
- **Input Data:**
  ```json
  {
    "field1": "description",
    "field2": "description"
  }
  ```

---

## Steps

### Step 1: [Trigger Name]
- **What it does:** Receives input data and starts workflow
- **Output:** Input variables available for downstream steps

### Step 2: [AI Module Name]
- **What it does:** Processes input using AI
- **Template used:** [Link to Block 1 template]
- **Model:** [Claude/GPT-4/etc.]

### Step 3: [Output Module Name]
- **What it does:** Delivers AI response to destination
- **Destination:** [Email/Google Doc/Slack/etc.]

---

## AI Processing

- **Prompt Template:** [Paste or link to your prompt]
- **Model:** [Claude 3.5 Sonnet / GPT-4 / etc.]
- **Expected output format:** [Description of expected output]

---

## Output

- **Destination:** [Where results go]
- **Format:** [How it's delivered - email body, document, etc.]

---

## Test Results

| Test # | Input Summary | Output Quality | Duration | Notes |
|--------|---------------|----------------|----------|-------|
| 1 | [Brief description] | [Good/Acceptable/Poor] | [X sec] | [Any notes] |
| 2 | | | | |
| 3 | | | | |

---

## Known Limitations

- [Limitation 1]
- [Limitation 2]

---

## Next Steps

- Add error handling (Exercise 2.2)
- Add logging (Exercise 2.3)
- Add quality check (Week 3)
```

---

#### Tips & Troubleshooting

**Tips:**
- Start with manual trigger - easier to test
- Use simple output (email) before complex (Google Doc)
- Keep your first workflow simple - you'll add complexity later

**Common Issues:**

| Problem | Solution |
|---------|----------|
| API key rejected | Check key is copied correctly, has no extra spaces |
| AI returns error | Verify prompt format matches API requirements |
| Output not arriving | Check output module configuration, test email separately |
| Variables not inserting | Verify variable names match exactly between steps |

---

### Exercise 2.2: Add Error Handling

**Duration:** 15 minutes

**Purpose:**
Make your workflow resilient to common failures. A workflow that handles errors gracefully is production-ready; one that crashes is just a demo.

**You Will Create:**
Error handlers for critical steps in your workflow.

---

#### Instructions

**Step 1: Identify Failure Points (3 min)**

List what could go wrong:

| Step | Potential Failure | Likelihood |
|------|-------------------|------------|
| AI Module | API unavailable | Medium |
| AI Module | Rate limit exceeded | Medium |
| AI Module | Invalid response | Low |
| Output | Email/destination fails | Low |
| Input | Missing required fields | Medium |

**Step 2: Add Error Handler to AI Step (7 min)**

**In Make:**
1. Right-click AI module
2. Add error handler → "Resume" or "Ignore"
3. Configure fallback behavior
4. Optional: Add alert (email on error)

**In n8n:**
1. Add "Error Trigger" node
2. Connect to notification node
3. Configure error handling workflow

**Error Handler Configuration:**
- Log the error (what failed, when, with what input)
- Send alert notification to yourself
- Graceful failure (don't crash entire workflow)

**Step 3: Test Error Handling (3 min)**

Deliberately trigger a failure:
- Use invalid API key temporarily
- Send malformed input data
- Verify error is caught, logged, and alert sent

**Step 4: Document Error Handling (2 min)**

Add to your workflow documentation.

---

#### Deliverable Specification

**Update:** `workflow-1-documentation.md` with error handling section

**Quality Criteria:**
- [ ] At least one error handler added
- [ ] Error logging configured
- [ ] Alert notification set up
- [ ] Error handling tested

---

#### Template Addition

```markdown
## Error Handling

### Step: AI Module
- **Potential failure:** API unavailable, rate limit, invalid response
- **Handler:** Resume with logged error
- **Alert:** Email notification to [address]
- **Tested:** [Yes/No]

### Step: Output Module
- **Potential failure:** Destination unavailable
- **Handler:** Retry once, then log failure
- **Alert:** Email notification to [address]
- **Tested:** [Yes/No]

### Error Log Location
[Where errors are logged - platform logs, spreadsheet, etc.]
```

---

### Exercise 2.3: Set Up Performance Logging

**Duration:** 10 minutes

**Purpose:**
Track every workflow execution from day one. This data enables Week 4 optimization and capstone impact measurement.

**You Will Create:**
A logging step that records execution details to a destination you can analyze.

---

#### Instructions

**Step 1: Choose Logging Destination (2 min)**

Options:
- **Google Sheets** (easiest) - One row per execution
- **Airtable** (more structured) - Better for complex analysis
- **Platform logs** (simplest) - Built-in but less flexible

For this exercise, we recommend Google Sheets.

**Step 2: Create Logging Destination (3 min)**

**For Google Sheets:**
1. Create new spreadsheet: "Workflow Execution Log"
2. Create headers:
   - Timestamp
   - Workflow Name
   - Trigger Type
   - Input Summary
   - Output Summary
   - Duration (seconds)
   - Status (Success/Partial/Failed)
   - Quality Score (for later)
   - Cost Estimate (for later)
   - Notes

**Step 3: Add Logging Step to Workflow (4 min)**

At the END of your workflow:

**In Make:**
1. Add Google Sheets module
2. "Add a row" action
3. Map workflow data to columns

**In n8n:**
1. Add Google Sheets node
2. Configure append row
3. Map execution data

**Data Mapping:**
```
Timestamp: {{now}}
Workflow: [workflow name]
Trigger: [trigger type]
Input: {{input.summary or first 100 chars}}
Output: {{output.summary or first 100 chars}}
Duration: {{execution_time}}
Status: Success
Quality Score: [blank for now]
Cost: [blank for now]
Notes: [blank for now]
```

**Step 4: Test Logging (1 min)**

1. Run your workflow
2. Check logging destination
3. Verify row was added with correct data
4. Run 2 more times to confirm consistency

---

#### Deliverable Specification

**Deliverables:**
- Logging configured in workflow
- 3 logged executions visible in destination
- Update `workflow-1-documentation.md` with logging section

**Quality Criteria:**
- [ ] Logging step added to workflow
- [ ] At least 3 executions logged
- [ ] All specified fields captured
- [ ] Log destination accessible for future analysis

---

#### Template Addition

```markdown
## Logging

### Log Destination
- **Type:** [Google Sheets / Airtable / Platform]
- **Location:** [URL or description]

### Fields Logged
| Field | Source | Purpose |
|-------|--------|---------|
| Timestamp | System | When executed |
| Workflow Name | Static | Which workflow |
| Trigger Type | Trigger module | What started it |
| Input Summary | Trigger data | What was processed |
| Output Summary | AI response | What was produced |
| Duration | System | How long it took |
| Status | Workflow result | Success/Failure |
| Quality Score | [Week 3] | Output quality |
| Cost Estimate | [Week 4] | Execution cost |
| Notes | Manual | Any issues |

### Logged Executions
| # | Timestamp | Status | Duration | Notes |
|---|-----------|--------|----------|-------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
```

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| Workflow Documentation | Document workflow structure | Exercise 2.1 |
| Error Handling Section | Document error handlers | Exercise 2.2 |
| Logging Section | Document logging setup | Exercise 2.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Make Getting Started | Tutorial | [make.com/en/help/getting-started-with-make](https://www.make.com/en/help/getting-started-with-make) | Platform basics |
| n8n Workflow Tutorial | Tutorial | [docs.n8n.io/courses/level-one](https://docs.n8n.io/courses/level-one/) | Platform basics |
| Make Error Handling | Documentation | [make.com/en/help/errors/error-handling](https://www.make.com/en/help/errors/error-handling) | Error setup |
| n8n Error Handling | Documentation | [docs.n8n.io/flow-logic/error-handling](https://docs.n8n.io/flow-logic/error-handling/) | Error setup |
| Claude API Reference | Documentation | [docs.anthropic.com/claude/reference](https://docs.anthropic.com/claude/reference) | API setup |
| OpenAI API Reference | Documentation | [platform.openai.com/docs/api-reference](https://platform.openai.com/docs/api-reference) | API setup |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Build end-to-end AI workflow | Working workflow with successful executions | ☐ |
| 2 | Configure trigger, AI, and output modules | All three present in workflow | ☐ |
| 3 | Implement basic error handling | At least one handler configured and tested | ☐ |
| 4 | Set up execution logging | 3+ executions logged to destination | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Working workflow | N/A | Platform | ☐ |
| Workflow documentation | `workflow-1-documentation.md` | GitHub Block 2 folder | ☐ |
| Error handling | Added to workflow + documentation | Platform + GitHub | ☐ |
| Logging | Configured + 3 executions | Platform + Log destination | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** Which part of workflow building felt intuitive?

2. **What's still fuzzy?** Where did you struggle or need extra help?

3. **How does it compare to manual?** How long did your 3 test executions take vs. doing them manually?

4. **What would you automate next?** Now that you've built one workflow, what else could use this pattern?

---

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Tag cohort members for platform-specific tips

### Common Questions This Week

**Q: My API connection keeps failing. What should I check?**
A: Verify API key is correct with no extra spaces. Check you haven't exceeded rate limits. Try the API directly (Postman or curl) to isolate if it's a platform issue.

**Q: The AI output isn't formatted the way I expected.**
A: Check your prompt explicitly requests the format you want. Include an example of expected output in your prompt. Verify you're parsing the response correctly in the workflow.

**Q: How do I know if my workflow is "good enough"?**
A: If it runs successfully 3+ times and produces usable output, it's good enough for now. We'll add quality checks in Week 3 and optimize in Week 4.

### When to Ask for Help

- **Before asking:** Check platform documentation for your specific error
- **Good to ask:** "I tried [X] but got [Y] error. Here's a screenshot..."
- **Include:** Platform, specific error message, what you've already tried

---

## Looking Ahead

### Next Week Preview: Week 3 - Quality Systems + Template Workflows

**Focus:**
Adding automated quality checks using the LLM-as-judge pattern, and building your second workflow.

**How It Builds on This Week:**
Your workflow from this week gets quality gates added. You'll also clone it to create your second workflow.

**To Prepare:**
- [ ] Complete all Week 2 exercises
- [ ] Have 5+ successful workflow executions logged
- [ ] Review your Block 1 quality rubric
- [ ] Note any quality issues in your current output

---

## Glossary

| Term | Definition |
|------|------------|
| Trigger | The event that starts a workflow (manual click, webhook, schedule, etc.) |
| Module | A single step in a workflow that performs one action |
| Scenario | Make's term for a complete workflow |
| Workflow | A connected series of steps that process data automatically |
| Error Handler | Logic that catches failures and routes them appropriately |
| Logging | Recording execution details for later analysis |
| Micro-Agent Pattern | AI operating in bounded steps within deterministic workflows |
| Fallback Route | Alternative path when primary step fails |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [← Week 1](../week-1/participant-guide.md) | **Week 2** | [Week 3 →](../week-3/participant-guide.md)
