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

**GRAPHICS:**

**Graphic 1: Session Timeline with Demo Emphasis**
- Purpose: Show session flow with visual emphasis on the hands-on live build segment
- Type: Horizontal timeline with emphasis marker
- Elements: Timeline bar 0-45 minutes, six time blocks, extra-large orange highlight box around Segment 2 (Live Build), "DEMO" badge on the build segment
- Labels: Time markers, segment names, focus descriptions, "HANDS-ON" label on Segment 2
- Relationships: Sequential flow with Segment 2 visually emphasized as the centerpiece activity

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

**GRAPHICS:**

**Graphic 1: Learning Objectives Checklist**
- Purpose: Present four hands-on learning objectives
- Type: Checklist with workflow iconography
- Elements: Four numbered items with orange checkmarks, workflow gear icon beside each, connecting arrows showing progression from principles to practice
- Labels: Objective titles in bold, sub-descriptions for each
- Relationships: Progression from conceptual (principles, micro-agent) to practical (build, error handling, logging)

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

**GRAPHICS:**

**Graphic 1: Single Prompt vs Multi-Step Workflow Comparison**
- Purpose: Illustrate the fundamental mindset shift from Block 1 to Block 2
- Type: Before-and-after comparison diagram
- Elements: Left side showing single prompt box with manual "You run it" notation, right side showing 5-step flow (Trigger → Step 1 → Step 2 → Step 3 → Output) with "System runs automatically" notation, transformation arrow between them
- Labels: "Block 1 Approach" header on left, "Block 2 Approach" header on right, "Manual Execution" vs "Automated Execution" tags
- Relationships: Contrast between monolithic manual approach and decomposed automated approach

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

**GRAPHICS:**

**Graphic 1: Five Core Workflow Components**
- Purpose: Visualize the universal structure of AI workflows
- Type: Horizontal process flow diagram
- Elements: Five sequential boxes connected by arrows (Trigger, Data Gathering, AI Processing, Quality Check, Output), icons representing each component (play button for trigger, database for data, brain for AI, checkmark for quality, target for output), examples listed under each box
- Labels: Component names as headers, purpose questions (What starts it?, What info needed?, etc.), concrete examples for each
- Relationships: Left-to-right sequential flow, AI Processing as the central transformation step, Quality Check as gate before Output

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

**GRAPHICS:**

**Graphic 1: Micro-Agent Pattern Diagram**
- Purpose: Illustrate how bounded AI steps embed within deterministic workflows
- Type: Comparative architecture diagram
- Elements: Top row showing traditional DAG (4 identical boxes in sequence), bottom row showing micro-agent pattern (deterministic box, highlighted AI section with 5-10 sub-steps, deterministic box), visual boundary box around AI section with "Bounded AI: 3-20 steps" label, flexibility icon in AI section, predictability icons in deterministic sections
- Labels: "Traditional DAG: All Deterministic" header, "Micro-Agent Pattern: Bounded AI" header, step annotations, "Why 3-20 steps?" callout with bullet points
- Relationships: Contrast between fully rigid vs strategically flexible approaches, AI section as contained exception to determinism

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

**GRAPHICS:**

**Graphic 1: Demo vs Production Reality Check**
- Purpose: Visually emphasize the difference between impressive demos and reliable production systems
- Type: Split comparison with emotional impact
- Elements: Left side "DEMO" with 90% success gauge (green), happy emoji, "Impressive!" tag; Right side "PRODUCTION" with 10% failure gauge (red), worried emoji, "Unacceptable!" tag, comparison to web app that crashes 10% of time with broken browser icon
- Labels: "90% Success Rate" on left, "10% Failure Rate" on right (same thing, different framing), "Would you use this?" question
- Relationships: Reframing the same metric to show how demo-thinking vs production-thinking evaluates reliability differently

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

**GRAPHICS:**

**Graphic 1: Design Principles Icon Summary**
- Purpose: Reinforce the four key design principles with memorable icons
- Type: Icon grid with labels
- Elements: Four quadrants each with icon and text (steps icon for "Think in Steps," five-box diagram for "Five Components," bounded box for "Micro-Agent Pattern," warning icon with "90% isn't enough")
- Labels: Principle titles, brief one-liner for each
- Relationships: Equal-weight presentation of four foundational concepts participants need before building

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

**GRAPHICS:**

**Graphic 1: Demo Workflow Architecture**
- Purpose: Show the structure of the workflow about to be built in demo
- Type: Linear process flow with annotations
- Elements: Three connected boxes (Manual Trigger, AI: Summarize, Email Output), connecting arrows, data flow annotations showing what passes between steps, "Watch For:" callout box listing key observation points
- Labels: Component names, data labels (sample data, AI request, AI response, formatted email), observation checklist
- Relationships: Sequential three-step flow, data transformation at each stage

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

**GRAPHICS:**

**Graphic 1: Platform Scenario Creation Screenshot**
- Purpose: Provide visual reference for first step of workflow building
- Type: Annotated screenshot
- Elements: Platform interface showing "Create New Scenario" button, naming field with example name "Email Summary - Summarize - v1", save button, naming convention callout box
- Labels: UI element labels, naming convention formula, step numbers (1, 2, 3)
- Relationships: Step-by-step visual guide matching the demo flow

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

**GRAPHICS:**

**Graphic 1: Trigger Configuration Interface**
- Purpose: Show how to configure trigger with sample data
- Type: Annotated screenshot with data flow visualization
- Elements: Trigger module configuration panel, sample JSON data input area, variable panel showing created variables (content, format, length), data flow arrows showing how trigger data becomes available downstream
- Labels: "Sample Data" header, variable names, "Available Downstream" annotation, JSON field names
- Relationships: Input data structure creates variables accessible in subsequent workflow steps

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

**GRAPHICS:**

**Graphic 1: AI Module Configuration with Variable Mapping**
- Purpose: Show how Block 1 templates integrate with workflow variable system
- Type: Annotated screenshot showing prompt construction
- Elements: AI module configuration panel, prompt text area showing template with variable placeholders ({{trigger.content}}, {{trigger.format}}), variable insertion dropdown/panel, API connection settings (collapsed), response parsing configuration
- Labels: "Your Block 1 Template Goes Here" callout, variable placeholder syntax, "Data from Trigger" arrows pointing to variables
- Relationships: Block 1 static template + workflow dynamic variables = personalized AI processing

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

**GRAPHICS:**

**Graphic 1: Successful Workflow Execution View**
- Purpose: Show what successful execution looks like with all success indicators
- Type: Annotated workflow execution screenshot
- Elements: Three workflow modules in sequence, green checkmarks on each module, execution time stamps, data preview bubbles showing what passed between steps, "Run Once" button, execution time counter
- Labels: Success indicators (green checks), execution times, "Output Received" confirmation, step-by-step data previews
- Relationships: Sequential execution visualization showing data transformation through each successful step

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

**GRAPHICS:**

**Graphic 1: Common Failure Types Matrix**
- Purpose: Categorize failures by type and frequency to prioritize error handling
- Type: Table with visual severity indicators
- Elements: Five-row table with failure types, warning icons (⚠️) with color coding by frequency (red for common, yellow for occasional, gray for rare), cause descriptions, frequency badges
- Labels: Failure names, causes, frequency labels, "It's not IF, it's WHEN" callout
- Relationships: Frequency-based prioritization showing which failures need immediate handling vs eventual handling

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

**GRAPHICS:**

**Graphic 1: Error Handling Flow Pattern**
- Purpose: Illustrate the standard error handling pattern for workflow steps
- Type: Branching flow diagram
- Elements: Central AI step box with two exit paths (Success path going right to Output box, Failure path going down to Log Error box then to Alert Me box), green arrow for success path, red arrow for failure path, action labels on each box (Log: "what, when, with what input", Alert: "email/Slack notification")
- Labels: "Success" and "Failure" path labels, action descriptions, "Graceful Failure" annotation
- Relationships: Binary branching from each critical step, error path as contained and logged rather than crashing

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

**GRAPHICS:**

**Graphic 1: 80/20 Error Handling Priority**
- Purpose: Show which errors to handle first using 80/20 principle
- Type: Pareto chart / priority matrix
- Elements: Large orange box containing 4 common failures (API unavailable, Rate limits, Invalid input, Timeouts) labeled "80% of failures - HANDLE THESE," small gray box containing edge cases labeled "20% of failures - SKIP FOR NOW," visual sizing showing 80/20 proportion
- Labels: "Focus On" header for main box, "Skip (for now)" header for small box, examples of exotic edge cases with humorous "What if sun explodes?" reference
- Relationships: Proportional sizing reinforcing 80/20 focus, clear delineation between actionable and theoretical concerns

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

**GRAPHICS:**

**Graphic 1: With vs Without Logging Comparison**
- Purpose: Demonstrate the value of logging through contrasting scenarios
- Type: Before-and-after comparison with dialogue
- Elements: Left side "Without Logging" with confused person icon and vague quotes in speech bubbles ("It was working yesterday..."), right side "With Logging" with confident person icon and specific quotes with data ("Execution #47 at 3pm failed with error X"), visual contrast in certainty/professionalism
- Labels: "Flying Blind" vs "Data-Driven" headers, sample quotes, "You can't improve what you don't measure" principle at bottom
- Relationships: Contrast between guesswork and precision, emotional/professional difference logging provides

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

**GRAPHICS:**

**Graphic 1: Workflow Execution Log Template**
- Purpose: Provide concrete example of simple logging structure
- Type: Spreadsheet screenshot/mockup
- Elements: Google Sheets layout with 8 columns (Timestamp, Workflow Name, Trigger Type, Input Summary, Output Summary, Duration, Status, Notes), 3-4 sample execution rows with realistic data, header row highlighted, status column using color coding (green for Success)
- Labels: Column headers from table, sample data entries, "One Row Per Execution" annotation
- Relationships: Columnar data structure showing how each execution is tracked, chronological ordering by timestamp

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

**GRAPHICS:**

**Graphic 1: Logging Summary Icon**
- Purpose: Simple visual reinforcement of logging takeaways
- Type: Icon with key points
- Elements: Logging/clipboard icon with checkmark, four key points listed below (log every execution, Google Sheets, track basics, needed for Week 4), Exercise 2.3 reference badge
- Labels: Key points, homework reference
- Relationships: Summary icon connecting logging practice to upcoming optimization needs

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

**GRAPHICS:**

**Graphic 1: Homework Exercise Breakdown**
- Purpose: Clearly present homework structure and time allocation
- Type: Table with progress visualization
- Elements: Three-row table showing exercises with time estimates (35/15/10 min), deliverables, skills practiced, cumulative progress bar showing 60-minute total, "CRITICAL" badge on first exercise
- Labels: Exercise names, time allocations, deliverable descriptions, skills practiced, total time
- Relationships: Sequential exercise structure, cumulative time building to 60 minutes, dependency on Exercise 2.1 for Week 3

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

**GRAPHICS:**

**Graphic 1: Categorized Resource Directory**
- Purpose: Organize resources by category for easy reference
- Type: Three-column categorized list with icons
- Elements: Three sections (Platform Documentation, Error Handling, API Reference), icons for each platform/service, URLs or QR codes for quick access, support channel callout box with "Screenshots help!" tip
- Labels: Category headers, platform/service names, URL references, support information
- Relationships: Categorical organization matching the three technical areas covered in homework

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

**GRAPHICS:**

**Graphic 1: Week 3 Quality Check Flow Preview**
- Purpose: Build excitement for next week by previewing quality automation
- Type: Enhanced workflow diagram
- Elements: Expanded workflow showing Trigger → AI Processing → Quality Check (new, highlighted) → Output, quality check step with rubric icon and pass/fail branches, "NEW IN WEEK 3" badge on quality check, preparation checklist on side
- Labels: Workflow step names, "LLM-as-Judge Pattern" annotation on quality check, preparation requirements
- Relationships: Quality check as new gate between AI processing and output, builds on Week 2 workflow foundation

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
