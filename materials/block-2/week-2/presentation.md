# **POWERPOINT PRESENTATION: BLOCK 2 WEEK 2**
## **Building Your First Workflow**

**Block:** 2: AI Workflow Engineering
**Week Number:** 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Consultants with platform accounts created and Block 1 templates ready

**Week Learning Objectives:** By the end of this session, participants will:
1. Understand workflow design principles and the micro-agent pattern
2. Build an end-to-end AI workflow with trigger, AI processing, and output
3. Implement basic error handling for common failure scenarios
4. Configure performance logging to track workflow executions

**Entry Criteria:**
- [ ] Automation platform selected and account created
- [ ] Platform getting started tutorial completed
- [ ] MCP servers identified
- [ ] Performance metrics defined
- [ ] Workflow candidate selected

**Exit Criteria:**
- [ ] First workflow built and functional
- [ ] Basic error handling implemented
- [ ] Performance tracking active from first execution
- [ ] Workflow documented in standard format
- [ ] Successfully processed 3+ test executions

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Workflow Design Principles (12 min) - Slides 4-8
3. Segment 2: Live Workflow Build (18 min) - Slides 9-13
4. Segment 3: Error Handling (5 min) - Slides 14-16
5. Segment 4: Logging Setup (4 min) - Slides 17-19
6. Homework Preview & Close (3 min) - Slides 20-22

**Total Slides:** 22

---

## SLIDE 1: TITLE SLIDE

**Title:** Block 2 Week 2: Building Your First Workflow

**Subtitle:** From Concept to Working Automation in 45 Minutes

**Content:**
- AI Practitioner Training Program
- Block 2: AI Workflow Engineering
- [Instructor Name]
- [Date]

**Graphic:** Clean title slide with Block 2 orange color theme. Workflow builder visual or gear/flow icon.

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome back to Block 2, Week 2! Today is hands-on day - we're building actual workflows.

Quick readiness check: Who has their platform account set up and completed the getting started tutorial?

[Count hands]

Great. For those who didn't quite finish - you'll still follow along, and we'll catch you up in the support channel after.

By the end of today, you'll have a working AI workflow - not just concepts, but something you can run and see results from.

What platform did everyone choose? Quick poll: Make? n8n? Something else?

[Note distribution]

Let's get building."

[Transition: Click to next slide]

---

## SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Week 1 recap, readiness check |
| 3-15 min | Segment 1 | Workflow Design Principles |
| 15-33 min | Segment 2 | Live Workflow Build (DEMO) |
| 33-38 min | Segment 3 | Error Handling Fundamentals |
| 38-42 min | Segment 4 | Logging and Monitoring |
| 42-45 min | Close | Homework & Week 3 Preview |

**Graphic:** Visual timeline with orange markers, emphasizing the live build segment

**SPEAKER NOTES:**

"Here's our agenda:

We'll start with workflow design principles - the mental models you need before building.

Then - the main event - I'll build a complete workflow live, from scratch. Watch what I do, because you'll replicate this in homework.

After that, we cover error handling - because things WILL break - and logging, because you need to track from day one.

This is the most hands-on session of Block 2. Ready to build?"

[Transition]

---

## SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Apply workflow design principles**
   - Think in steps, not single prompts
   - Use the micro-agent pattern

2. **Build an end-to-end AI workflow**
   - Configure trigger, AI processing, output

3. **Implement basic error handling**
   - Handle common failures gracefully

4. **Set up execution logging**
   - Track from day one

**Graphic:** Checklist with workflow icon, orange checkmarks

**SPEAKER NOTES:**

"Four objectives for today.

First, you'll learn how to think about workflows - in steps, not single prompts.

Second, you'll see a complete workflow built from scratch and know how to build your own.

Third, you'll understand error handling - what breaks and how to handle it.

Fourth, you'll know how to log every execution for later optimization.

Let's start with the principles."

[Transition: Click to Segment 1]

---

## SEGMENT 1: WORKFLOW DESIGN PRINCIPLES
### Duration: 12 minutes | Slides 4-8

---

## SLIDE 4: THE WORKFLOW MINDSET

**Title:** Think in Steps, Not Single Prompts

**Content:**

**Block 1 Approach:**
```
One prompt → One output
(You run it manually each time)
```

**Block 2 Approach:**
```
Trigger → Step 1 → Step 2 → Step 3 → Output
(System runs automatically)
```

**Key Principle:** Each step should do ONE thing well

**Graphic:** Visual comparing single prompt vs. multi-step workflow

**SPEAKER NOTES:**

"[Hook - The mindset shift]"

"In Block 1, you worked with single prompts. You crafted a great template, ran it, got output.

In Block 2, we think differently. Instead of one big prompt, we break the process into steps.

[Point to workflow]

Each step does one thing. The trigger starts it. Step 1 might gather data. Step 2 runs AI. Step 3 checks quality. Step 4 delivers output.

Why break it up? Three reasons:

First, reliability. If something breaks, you know exactly which step failed.

Second, debuggability. You can see the input and output of each step.

Third, reusability. You can swap individual steps without rebuilding everything.

This is the workflow mindset: think in steps, not single prompts."

[Transition]

---

## SLIDE 5: CORE WORKFLOW COMPONENTS

**Title:** Five Building Blocks of Every Workflow

**Content:**

| Component | Purpose | Example |
|-----------|---------|---------|
| **1. Trigger** | What starts it? | Manual button, email received, schedule |
| **2. Data Gathering** | What info is needed? | Read email, fetch from API |
| **3. AI Processing** | What does AI do? | Summarize, generate, analyze |
| **4. Quality Check** | Does output pass? | Score against rubric |
| **5. Output** | Where does result go? | Email, Slack, Google Doc |

**Graphic:** Flow diagram showing five connected boxes with arrows

**SPEAKER NOTES:**

"Every workflow has five components.

[Point to each]

First, the Trigger - what starts the workflow? Could be a button click, an incoming email, a schedule, or a webhook.

Second, Data Gathering - what information does the workflow need? Maybe reading an email body, fetching from a database, or pulling from an API.

Third, AI Processing - this is where your Block 1 templates live. The AI step that transforms input into output.

Fourth, Quality Check - does the output meet your standards? We'll build this in Week 3 using your rubrics.

Fifth, Output - where does the result go? Email, Slack message, Google Doc, wherever it needs to be.

This week we'll build trigger, AI, and output. Next week we add quality checks."

[Transition]

---

## SLIDE 6: THE MICRO-AGENT PATTERN

**Title:** Bounded AI Within Deterministic Workflows

**Content:**

**Traditional DAG:**
```
Step A → Step B → Step C → Step D
(all deterministic, all predefined)
```

**Micro-Agent Pattern:**
```
[Deterministic] → [AI: 5-10 steps] → [Deterministic]
(flexibility where needed, predictability elsewhere)
```

**Why 3-20 AI steps?**
- Bounds the context window
- Limits scope of failures
- Easier to debug
- Research: agents degrade after 10-20 turns

**Graphic:** Side-by-side comparison with AI section highlighted

**SPEAKER NOTES:**

"Here's a key concept: the micro-agent pattern.

[Point to traditional DAG]

Traditional automation is fully deterministic. Step A always goes to Step B. Predictable but rigid.

[Point to micro-agent pattern]

The micro-agent pattern embeds AI within deterministic boundaries. The workflow is predictable, but the AI step has flexibility.

Why limit AI to 3-20 steps? Several reasons:

It bounds the context window - AI doesn't lose track of what it's doing.

It limits failure scope - if AI goes wrong, it's contained.

It's easier to debug - clear start and end.

And research shows AI agents degrade after 10-20 turns anyway.

For your workflows, think 'one AI step doing one thing well' - that's the sweet spot."

[Transition]

---

## SLIDE 7: THE 90% REALITY CHECK

**Title:** Production Means Reliability

**Content:**

**The Question:**
> A 90% success rate sounds good, right?

**The Reality Check:**
> Would you use a web app that crashed 10% of the time?

**What This Means:**
- Demo ≠ Production
- Impressive one-off ≠ Reliable daily use
- "Usually works" ≠ "Can trust to run"

**Our Goal:**
Build workflows you can trust to run unattended.

**Graphic:** Comparison of demo vs. production expectations

**SPEAKER NOTES:**

"Let me give you a reality check.

A 90% success rate sounds pretty good. Most AI demos hit around that mark.

But think about it differently: Would you use a web app that crashed 10% of the time? Would you trust a banking app that failed one out of ten transactions?

No. You wouldn't.

That's the difference between a demo and production. Demos can be impressive occasionally. Production needs to be reliable constantly.

Our goal in Block 2 is building workflows you can trust to run without you watching. That means error handling, logging, quality checks - all the 'boring' stuff that makes things actually work.

This is why we handle errors and log everything."

[Transition]

---

## SLIDE 8: SEGMENT 1 SUMMARY

**Title:** Design Principles Recap

**Content:**

**Key Takeaways:**
- Think in steps, not single prompts
- Five components: Trigger, Data, AI, Quality, Output
- Micro-agent pattern: bounded AI steps
- 90% isn't good enough for production

**Coming Up:**
Live build of a complete workflow

**Graphic:** Simple recap icons for each principle

**SPEAKER NOTES:**

"Before we build, let me summarize:

Think in steps. Each step does one thing.

Every workflow has five components - we're building three today, adding quality checks next week.

The micro-agent pattern keeps AI bounded and reliable.

And remember: we're building for production reliability, not demo impressiveness.

Now let's build."

[Transition: Click to Segment 2]

---

## SEGMENT 2: LIVE WORKFLOW BUILD
### Duration: 18 minutes | Slides 9-13

---

## SLIDE 9: WHAT WE'RE BUILDING

**Title:** Live Demo: Content Summarizer Workflow

**Content:**

**Workflow:**
```
[Manual Trigger] → [AI: Summarize] → [Email Output]
```

**What You'll See:**
1. Creating a new scenario/workflow
2. Configuring the trigger with sample data
3. Adding AI module with prompt
4. Setting up output destination
5. Running a successful test

**Watch For:**
- How data flows between steps
- How variables are mapped
- What happens when you run

**Graphic:** Simple 3-step workflow diagram

**SPEAKER NOTES:**

"[DEMO - Start]"

"Let me show you exactly how to build a workflow.

We're building a simple but complete workflow: Manual trigger, AI summarization, Email output.

I'll walk through every click. Watch how data flows between steps - that's the key to understanding workflows.

Ready? Let's do this."

[Switch to screen share]

---

## SLIDE 10: STEP 1 - CREATE SCENARIO

**Title:** Creating Your Workflow

**Content:**

**Steps:**
1. Click "Create new scenario" / "New workflow"
2. Name it descriptively
3. Save

**Naming Convention:**
`[Deliverable Type] - [Action] - v[Version]`

Example: `Email Summary - Summarize - v1`

**Graphic:** Screenshot of new scenario creation

**SPEAKER NOTES:**

"First, we create a new scenario.

[Navigate to platform, click create]

I'm naming this 'Content Summarizer v1'. Good naming helps when you have multiple workflows.

[Save it]

Now we have a blank canvas. Time to add our first step."

[Transition]

---

## SLIDE 11: STEP 2 - CONFIGURE TRIGGER

**Title:** Adding the Trigger

**Content:**

**What Triggers Do:**
- Start the workflow
- Provide initial data
- Make variables available downstream

**For Testing:**
- Use manual trigger
- Define sample input data

**Sample Data:**
```json
{
  "content": "Long text to summarize...",
  "format": "bullet points",
  "length": "brief"
}
```

**Graphic:** Trigger configuration screenshot

**SPEAKER NOTES:**

"The trigger is what starts your workflow.

For testing, we use a manual trigger. In production, you might use a webhook, schedule, or email trigger.

[Add trigger module]

Now I need to define what data this trigger provides.

[Configure sample data]

See these variables? They'll be available in all downstream steps. This is how data flows through the workflow.

[Show variable panel]

'Content', 'format', 'length' - I can use these anywhere in my workflow now."

[Transition]

---

## SLIDE 12: STEP 3 - ADD AI MODULE

**Title:** The AI Processing Step

**Content:**

**Configuration:**
1. Add HTTP module (for Claude) or OpenAI module
2. Configure API connection
3. Build prompt with variables
4. Parse response

**Key Point:**
This is where your Block 1 templates go!

**Prompt Structure:**
```
[Instructions from Block 1 template]
Content: {{trigger.content}}
Format: {{trigger.format}}
Length: {{trigger.length}}
```

**Graphic:** AI module configuration screenshot

**SPEAKER NOTES:**

"Now the AI step - the heart of the workflow.

[Add AI module]

I'm using [Claude/OpenAI]. First, I configure the API connection.

[Show API setup - briefly]

Now the prompt. This is where your Block 1 templates come in.

[Build prompt]

See how I'm inserting variables? The double curly braces pull in data from the trigger.

[Show variable insertion]

'Content' comes from the trigger. 'Format' comes from the trigger. The workflow connects it all.

[Configure response parsing]

And we tell the platform how to read the AI's response.

Let's add the output and test it."

[Transition]

---

## SLIDE 13: STEP 4 - OUTPUT AND TEST

**Title:** Delivering Results and Testing

**Content:**

**Output Configuration:**
1. Add output module (Email/Slack/Doc)
2. Map AI response to output
3. Configure destination

**Testing:**
1. Click "Run once" / "Execute"
2. Watch each step execute
3. Check output arrived
4. Note execution time

**Success:**
Each step shows green checkmark
Output received at destination

**Graphic:** Execution view with success indicators

**SPEAKER NOTES:**

"Final step - the output.

[Add email module]

I'm mapping the AI response to the email body.

[Configure mapping]

Recipient is me, for testing. Subject includes a variable so I know what was processed.

Now the moment of truth.

[Click Run]

Watch the execution...

[Narrate as it runs]

Trigger fired... data passed to AI... AI is processing... response received... email sending... sent!

[Show success indicators]

Every step green. That's a successful execution.

[Check email]

And there's my email with the AI-generated summary.

That's a complete workflow, built in about 10 minutes. You'll do this in your homework.

Questions before we move on?"

[Take 1-2 questions, then transition]

---

## SEGMENT 3: ERROR HANDLING FUNDAMENTALS
### Duration: 5 minutes | Slides 14-16

---

## SLIDE 14: WHAT CAN GO WRONG

**Title:** Common Workflow Failures

**Content:**

| Failure | Cause | Frequency |
|---------|-------|-----------|
| **API Rate Limits** | Too many requests | Common |
| **Invalid Input** | Missing or malformed data | Common |
| **AI Generation Failure** | Timeout, refusal, bad response | Occasional |
| **Connection Timeout** | Network/service issues | Occasional |
| **Output Destination Fails** | Service down, auth expired | Rare |

**Key Insight:**
It's not IF something will fail, it's WHEN.

**Graphic:** Warning icons next to each failure type

**SPEAKER NOTES:**

"Now let's talk about what goes wrong.

[Point to list]

API rate limits - especially on free tiers, you hit limits quickly.

Invalid input - someone sends data missing a required field.

AI failures - timeout, refusal, response that doesn't parse.

Connection issues - services go down.

Output problems - email server hiccup, expired credentials.

[Pause]

Notice I said 'when' not 'if'. Things WILL break. The question is whether your workflow handles it gracefully or crashes."

[Transition]

---

## SLIDE 15: BASIC ERROR HANDLING

**Title:** Handling Failures Gracefully

**Content:**

**The Pattern:**

```
┌─────────┐     Success     ┌─────────┐
│ AI Step │───────────────▶│ Output  │
└─────────┘                 └─────────┘
     │
     │ Failure
     ▼
┌─────────┐     ┌─────────┐
│  Log    │────▶│  Alert  │
│  Error  │     │   Me    │
└─────────┘     └─────────┘
```

**Error Handling Actions:**
1. **Log** the error (what, when, with what input)
2. **Alert** yourself (email/Slack notification)
3. **Graceful failure** (don't crash entire workflow)

**Graphic:** Error handling flow diagram

**SPEAKER NOTES:**

"Here's the basic error handling pattern.

[Point to diagram]

Normal flow: AI step succeeds, goes to output.

Error flow: AI step fails, we catch it, log what happened, alert ourselves.

Three actions for every error:

Log it - what failed, when, with what input. You need this for debugging.

Alert yourself - you should know when things break.

Graceful failure - don't let one error crash everything.

In Make, you add error handlers to modules. In n8n, you use error trigger nodes. The concepts are the same."

[Transition]

---

## SLIDE 16: THE 80/20 RULE

**Title:** Handle Common Failures First

**Content:**

**Don't Try to Handle Everything**

Focus on:
1. API unavailable (retry once, then fail)
2. Rate limits (wait and retry)
3. Invalid input (validate, skip if bad)
4. Timeouts (set reasonable limits)

**Skip (for now):**
- Exotic edge cases
- Unlikely scenarios
- "What if the sun explodes?"

**Principle:**
> Handle the 3-4 things that actually break.

**Graphic:** 80/20 visual with common issues highlighted

**SPEAKER NOTES:**

"Last point on errors: the 80/20 rule.

Don't try to handle every possible failure. You'll never ship.

Focus on the 3-4 things that actually break:
- API unavailable
- Rate limits
- Invalid input
- Timeouts

These cover 80% of failures.

Skip the exotic edge cases for now. Handle what breaks in practice.

In your homework, you'll add error handling to at least one step."

[Transition: Click to Segment 4]

---

## SEGMENT 4: LOGGING AND MONITORING
### Duration: 4 minutes | Slides 17-19

---

## SLIDE 17: WHY LOG FROM DAY ONE

**Title:** Track Everything from the Start

**Content:**

**Without Logging:**
- "It was working yesterday..."
- "I think it ran successfully?"
- "Not sure what went wrong"

**With Logging:**
- "Execution #47 at 3pm failed with error X"
- "Average execution time is 12 seconds"
- "Success rate is 94% over last week"

**The Principle:**
> You can't improve what you don't measure.

**Graphic:** Comparison of with/without logging scenarios

**SPEAKER NOTES:**

"Before we close, logging.

[Point to without logging]

Without logging, you're flying blind. 'I think it worked?' is not professional.

[Point to with logging]

With logging, you know exactly what happened, when, and what went wrong.

By Week 4, we'll optimize your workflows. Without logs, you're guessing what to optimize. With logs, you have data.

Start logging from day one."

[Transition]

---

## SLIDE 18: WHAT TO LOG

**Title:** Simple Logging Setup

**Content:**

**Log These Fields:**

| Field | Example | Purpose |
|-------|---------|---------|
| Timestamp | 2025-01-15 14:30:22 | When |
| Workflow Name | Content Summarizer | Which |
| Trigger Type | Manual | What started it |
| Input Summary | "500 word article about..." | What was processed |
| Output Summary | "3 bullet points..." | What was produced |
| Duration | 8 seconds | How long |
| Status | Success | Did it work |
| Notes | (blank) | Any issues |

**Simple Destination:**
Google Sheets - one row per execution

**Graphic:** Sample log spreadsheet

**SPEAKER NOTES:**

"What should you log?

[Point to table]

Timestamp - when it ran.
Workflow name - which workflow.
Trigger type - what started it.
Input summary - brief description of what was processed.
Output summary - brief description of what was produced.
Duration - how long it took.
Status - success, failure, partial.
Notes - any issues.

For destination, start simple. Google Sheets works great. One row per execution.

Add a logging step at the end of your workflow that writes a row."

[Transition]

---

## SLIDE 19: SEGMENT 4 SUMMARY

**Title:** Logging Takeaways

**Content:**

**Key Points:**
- Log every execution from day one
- Simple logging: Google Sheets row per execution
- Track: timestamp, input, output, duration, status
- You need this data for Week 4 optimization

**In Your Homework:**
Exercise 2.3 - Set up logging, capture 3 executions

**Graphic:** Logging icon with checkmark

**SPEAKER NOTES:**

"Summary on logging:

Log everything from day one. A Google Sheet is fine to start.

Track the basics: when, what, how long, success/fail.

In Exercise 2.3, you'll add logging to your workflow and capture at least 3 executions.

This data becomes crucial in Week 4 when we optimize.

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
| 2.1: Build First Workflow | 35 min | Working workflow + docs | End-to-end build |
| 2.2: Add Error Handling | 15 min | Error handlers added | Resilience |
| 2.3: Set Up Logging | 10 min | 3 logged executions | Tracking |
| **Total** | **60 min** | | |

**Critical:** You need a working workflow for Week 3

**Graphic:** Progress bar showing the three exercises

**SPEAKER NOTES:**

"Your homework is hands-on building.

Exercise 2.1 - 35 minutes - build your first workflow. Use what I demonstrated, adapted to your Block 1 template.

Exercise 2.2 - 15 minutes - add error handling. At least one error handler configured and tested.

Exercise 2.3 - 10 minutes - set up logging. Capture 3 executions in your log.

[Emphasize]

You need a working workflow for Week 3. We'll be adding quality checks to it. If you don't have a workflow, you can't continue."

[Transition]

---

## SLIDE 21: RESOURCES

**Title:** Resources for This Week

**Content:**

**Platform Documentation:**
- Make: make.com/en/help/getting-started-with-make
- n8n: docs.n8n.io/courses/level-one

**Error Handling:**
- Make: make.com/en/help/errors/error-handling
- n8n: docs.n8n.io/flow-logic/error-handling

**API Reference:**
- Claude: docs.anthropic.com
- OpenAI: platform.openai.com/docs

**Support:**
- Questions: [Support channel]
- Screenshots help us help you faster

**Graphic:** QR codes or icons for quick access

**SPEAKER NOTES:**

"Resources:

Platform documentation for your specific platform.

Error handling guides for Make and n8n.

API documentation if you're having connection issues.

If you get stuck, post in support with screenshots. The more context you provide, the faster we can help."

[Transition]

---

## SLIDE 22: NEXT WEEK PREVIEW

**Title:** Next Week: Quality Systems + Template Workflows

**Content:**

**Week 3 Focus:**
- Add automated quality checks
- LLM-as-judge pattern
- Build second workflow
- Template versioning

**Preparation Required:**
- [ ] Working workflow from this week
- [ ] 5+ successful executions logged
- [ ] Block 1 quality rubric ready
- [ ] Note any quality issues in current output

**The Goal:**
Your workflow will evaluate its own output before delivering.

**Graphic:** Preview of quality check flow

**SPEAKER NOTES:**

"Next week: quality systems.

We'll add automated quality checks using your Block 1 rubrics. The AI will evaluate its own output before delivering it.

You'll also build your second workflow by cloning the first and adapting it.

To be ready, you need:
- A working workflow from this week
- At least 5 logged executions
- Your Block 1 rubric ready to convert to evaluation criteria

[Final close]

Questions before we wrap?

[Take questions]

Great session today. You've seen how to build a complete workflow. Now go build your own.

See you next week!"

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |

---

**Template Usage:**
1. Use Block 2 orange color theme throughout
2. Prepare demo workflow before session
3. Have backup screenshots for demo failure
4. Test API connections day before
5. Cross-reference with instructor and participant guides
