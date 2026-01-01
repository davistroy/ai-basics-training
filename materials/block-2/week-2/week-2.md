# Week 2: Building Your First Workflow

**Block:** 2 - AI Workflow Engineering
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Automation platform selected and account created
- [ ] Platform getting started tutorial completed
- [ ] MCP servers identified
- [ ] Performance metrics defined
- [ ] Workflow candidate selected

## Exit Criteria

- [ ] First workflow built and functional
- [ ] Basic error handling implemented
- [ ] Performance tracking active from first execution
- [ ] Workflow documented in standard format
- [ ] Successfully processed 3+ test executions

---

## Workshop Content (45 minutes)

### Segment 1: Workflow Design Principles (12 min)

**The workflow mindset:**
- Think in steps, not single prompts
- Each step should do ONE thing well
- Plan for failure (what if a step breaks?)

**Core workflow components:**
1. **Trigger:** What starts the workflow?
2. **Data gathering:** What information is needed?
3. **AI processing:** The prompt/generation step
4. **Quality check:** Does output meet standards?
5. **Output:** Where does the result go?

**Visual mapping:** Flowchart your workflow before building

**The Micro-Agent Pattern:**
- **What's actually working in production:**
  - NOT autonomous agents running indefinitely
  - Small, focused agents: 3-20 steps
  - Embedded within larger deterministic workflows

- **The pattern:**
  ```
  Traditional DAG:     Step A → Step B → Step C → Step D
                       (all deterministic, all predefined)

  Micro-Agent Pattern: [Deterministic] → [AI: 5-10 steps] → [Deterministic]
                       (flexibility where needed, predictability elsewhere)
  ```

- **Why 3-20 steps?**
  - Bounds the context window
  - Limits scope of failures
  - Easier to debug
  - Research shows agents degrade after 10-20 turns

- **The 90% reality check:**
  - A 90% success rate sounds good
  - But would you use a web app that crashed 10% of the time?
  - Production means reliability, not impressive demos

### Segment 2: Your First Workflow - Live Build (18 min)

**Demonstration workflow:** Email → AI Summary → Slack notification

**Step-by-step construction:**

1. **Trigger configuration:**
   - Email webhook, scheduled, or manual trigger
   - Understanding trigger data structure

2. **Data extraction:**
   - Parsing incoming data
   - Variable mapping
   - Handling missing fields

3. **AI module setup:**
   - Connecting to Claude/OpenAI
   - Passing context and prompt
   - Receiving and parsing response

4. **Output configuration:**
   - Formatting the response
   - Sending to destination
   - Confirmation handling

**Live demo:** Build each step in real-time on Make/n8n

### Segment 3: Error Handling Fundamentals (8 min)

**What can go wrong:**
- API rate limits
- Invalid input data
- AI generation failures
- Connection timeouts

**Basic error handling:**
- Try/catch patterns in workflows
- Fallback routes
- Alert on failure (email/Slack notification)
- Logging errors for review

**The 80/20 rule:** Handle the common failures first

### Segment 4: Logging and Monitoring Setup (7 min)

**Start logging immediately:**
- Every execution should be tracked
- Include: timestamp, input summary, output summary, duration, status

**Simple logging approaches:**
- Google Sheets (easiest)
- Airtable (more structured)
- Platform built-in logs (varies by platform)

**Quick setup:** Add logging step to workflow

---

## Self-Paced Exercises (60 minutes total)

### Exercise 2.1: Build Your First Workflow (35 minutes)

*Create a functional workflow end-to-end*

1. **Map your workflow visually:**

   ```
   [Trigger] → [Gather Data] → [AI Process] → [Quality Check] → [Output]
   ```

   Document each step:
   - What triggers it?
   - What data is needed?
   - What prompt template to use?
   - What quality criteria to check?
   - Where does output go?

2. **Build in your platform:**

   Step 1: Configure trigger
   - Manual/webhook for testing

   Step 2: Set up AI module
   - Connect your AI provider
   - Insert your Block 1 prompt template
   - Configure response handling

   Step 3: Add output
   - Start simple: send to email or create document

   Step 4: Test with sample data
   - Run 3+ test executions
   - Document results

3. **Document the workflow:**

```markdown
# Workflow: [Name]

## Purpose
[What this workflow does]

## Trigger
- Type: [Manual/Webhook/Schedule/etc.]
- Input: [What data it expects]

## Steps
1. [Step name] - [What it does]
2. [Step name] - [What it does]
3. [Step name] - [What it does]

## AI Processing
- Template: [Link to prompt template from Block 1]
- Model: [Claude/GPT-4/etc.]
- Expected output: [Format description]

## Output
- Destination: [Where results go]
- Format: [How it's delivered]

## Test Results
| Test # | Input Summary | Output Quality | Duration | Notes |
|--------|---------------|----------------|----------|-------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
```

**Deliverable:** Working workflow + `workflow-1-documentation.md`

---

### Exercise 2.2: Add Error Handling (15 minutes)

*Make your workflow resilient*

1. Identify failure points in your workflow:
   - What if input data is missing key fields?
   - What if AI API is unavailable?
   - What if output destination fails?

2. Add error handling:

   **For each critical step:**
   - Add error route/exception handler
   - Log the error with context
   - Send alert notification (email/Slack)
   - Graceful failure (don't crash entire workflow)

3. Test error handling:
   - Deliberately trigger a failure
   - Verify error is caught and logged
   - Confirm alert was sent

4. Document error handling:

```markdown
## Error Handling

### Step: [Step Name]
- **Potential failure:** [What could go wrong]
- **Handler:** [What happens on failure]
- **Alert:** [Yes/No - where sent]

### Step: [Step Name]
- **Potential failure:** [What could go wrong]
- **Handler:** [What happens on failure]
- **Alert:** [Yes/No - where sent]
```

**Deliverable:** Error handling added + documentation updated

---

### Exercise 2.3: Set Up Performance Logging (10 minutes)

*Track from day one*

1. Add logging step to workflow end:

```
Log Entry:
- Timestamp: [execution time]
- Workflow: [name]
- Trigger: [what started it]
- Input Summary: [brief description]
- Output Summary: [brief description]
- Duration: [seconds/minutes]
- Status: [Success/Partial/Failed]
- Quality Score: [if applicable]
- Cost Estimate: [if known]
- Notes: [any issues]
```

2. Create logging destination:
   - Google Sheet with columns matching log entry
   - Or Airtable base
   - Or platform's built-in logging

3. Run 3 test executions and verify logging works

**Deliverable:** Logging configured + 3 logged executions

**Resources:**
- [Make Error Handling](https://www.make.com/en/help/errors/error-handling)
- [n8n Error Handling](https://docs.n8n.io/flow-logic/error-handling/)
- [Google Sheets API Integration](https://developers.google.com/sheets/api)

---

## Key Takeaways

1. **Workflow thinking is different** - Steps, not single prompts
2. **Plan for failure from the start** - Error handling isn't optional
3. **Logging enables improvement** - Track everything from day one
4. **Start simple, iterate** - Get something working before adding complexity
5. **The micro-agent pattern** - Bounded AI within deterministic workflows

---

## Preparation for Week 3

- Run your workflow 5+ more times with real inputs
- Log all executions
- Note: Where does quality vary? Where do errors occur?
- Next week: Quality systems and template workflows

---

## Resources

- [Make Getting Started](https://www.make.com/en/help/getting-started-with-make)
- [n8n Workflow Tutorial](https://docs.n8n.io/courses/level-one/)
- [Make Error Handling](https://www.make.com/en/help/errors/error-handling)
- [n8n Error Handling](https://docs.n8n.io/flow-logic/error-handling/)
