# **INSTRUCTOR GUIDE: BLOCK 2 WEEK 2**
## **Building Your First Workflow**

**Block:** 2: AI Workflow Engineering
**Week:** 2 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Building first end-to-end AI workflow with error handling and logging |
| **Difficulty Level** | Medium-High |
| **Prep Time Required** | 45 minutes |
| **Demo Required** | Yes - Live workflow build in Make/n8n |
| **Tech Setup Needed** | Make or n8n account ready, Claude/OpenAI API access for demo |
| **Common Challenges** | API connection issues, platform unfamiliarity, error handling concepts |

---

## Navigation

**Block Navigation:** [← Week 1 Instructor Guide](../week-1/instructor-guide.md) | **Week 2** | [Week 3 Instructor Guide →](../week-3/instructor-guide.md)

**Related Materials:**
- [Week 2 Presentation](presentation.md)
- [Week 2 Participant Guide](participant-guide.md)
- [Block 2 Main Document](../block-2.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 2 materials | ☐ |
| Build demo workflow | Create the Email → AI Summary → Slack demo workflow | ☐ |
| Test demo | Run through live build at least twice | ☐ |
| Check resources | Verify platform documentation links | ☐ |
| Review Week 1 submissions | Check who has platform accounts ready | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load demo environment | Have Make/n8n open and ready | ☐ |
| Verify API connections | Test Claude/OpenAI API in platform | ☐ |
| Prepare backup | Have screenshots of each build step | ☐ |
| Check participant readiness | Identify who may need extra support | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, Make/n8n, API settings | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Clean up platform | Remove any test scenarios from demo account | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Week 1 recap, Week 2 preview | Quick readiness check |
| 0:03 | 12 min | Segment 1 | Workflow Design Principles + Micro-Agent Pattern | Foundation concepts |
| 0:15 | 18 min | Segment 2 | Live Workflow Build | Longest segment - the demo |
| 0:33 | 5 min | Segment 3 | Error Handling Fundamentals | Keep concise |
| 0:38 | 4 min | Segment 4 | Logging and Monitoring Setup | Brief but critical |
| 0:42 | 3 min | Closing | Homework, resources, Week 3 preview | Don't skip |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Segment 1: Skip micro-agent pattern details, reference in participant guide
- Segment 2: Complete trigger + AI step, reference remaining steps as homework
- Segment 3: Reduce to 3 minutes, cover only key error handling concepts

**If Running Ahead:**
- Segment 2: Show error path configuration in detail
- Segment 3: Walk through specific error scenarios
- Segment 4: Actually add logging step to demo workflow

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | Skip micro-agent deep dive |
| Demo AI step working | 0:25 | This is critical - prioritize over other content |
| Start Closing | 0:42 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants back
2. Quick check: "Who has their platform account ready?"
3. Address any Week 1 homework challenges briefly
4. Preview today's hands-on session

**Opening Script:**
> "Welcome back to Block 2, Week 2! Today is a hands-on session - we're building actual workflows. Quick show of hands: who has their platform account set up and completed the getting started tutorial? [Count hands] Great. For those who didn't quite finish - you'll still follow along, and we'll catch you up in the support channel."

**Engagement Opportunity:**
> "What platform did everyone choose? Quick poll: Make? n8n? Something else?"

[Note the distribution for demo relevance]

---

### Segment 1: Workflow Design Principles (12 minutes)

**Learning Objective:** Understand workflow component structure and the micro-agent pattern

**Slides:** 4-8

#### Content Delivery

**Key Point 1: The Workflow Mindset**
- Main message: Think in steps, not single prompts
- Example: "Instead of one complex prompt, break it into: gather data, process with AI, check quality, deliver output"
- Common misconception: "More steps = slower" - Actually, smaller steps are more reliable and debuggable

**Key Point 2: Core Workflow Components**
- Main message: Every workflow has five components
- Walk through each:
  1. Trigger: What starts it?
  2. Data gathering: What information is needed?
  3. AI processing: The prompt/generation step
  4. Quality check: Does output meet standards?
  5. Output: Where does the result go?

**Key Point 3: The Micro-Agent Pattern**
- Main message: Small, focused AI steps within deterministic workflows
- Framework:
  ```
  [Deterministic] → [AI: 5-10 steps] → [Deterministic]
  ```
- Why 3-20 steps: Bounded context, limited failure scope, easier to debug
- The 90% reality check: Production means reliability, not impressive demos

#### Facilitation Notes

**Watch For:**
- Participants who seem confused about "steps" vs. "prompts"
- Questions about whether they need to code

**If Asked About Coding:**
> "No coding required. We use visual workflow builders. If you can drag and drop, you can build workflows."

**If Asked About Complex Workflows:**
> "We start simple. Week 3 adds quality systems, Week 4 adds optimization. Build the foundation first."

**Transition to Segment 2:**
> "Now let's see these principles in action. I'm going to build a workflow live, from scratch."

---

### Segment 2: Your First Workflow - Live Build (18 minutes)

**Learning Objective:** See end-to-end workflow construction and understand each step

**Slides:** 9-13

#### Demo Instructions

**Demo Duration:** 15-16 minutes (allow 2-3 min for questions)

**Demo Workflow:** Manual Trigger → AI Summary → Email Output (simplified from Email→AI→Slack)

**Setup Required:**
- Make or n8n account open
- Claude or OpenAI API key connected
- Fresh scenario/workflow ready
- Sample input data prepared

**Demo Steps:**

**Step 1: Create New Scenario (2 min)**
> "I'm creating a new scenario. This is our blank canvas. Every workflow starts here."

1. Click "Create new scenario" (Make) or "New Workflow" (n8n)
2. Name it: "Block 2 Demo - Content Summarizer"

**Step 2: Add Trigger (3 min)**
> "First, the trigger - what starts our workflow? For testing, we use a manual trigger. In production, this could be a webhook, email, or schedule."

1. Add manual trigger module
2. Configure with sample data structure
3. Show how variables become available downstream

**Demo Talking Points:**
> "Notice how the platform shows us what data is available. Every module makes its output available to subsequent modules."

**Step 3: Add AI Module (5 min)**
> "Now the AI step. This is where your Block 1 templates come in."

1. Add HTTP/AI module (Claude or OpenAI)
2. Configure API connection (show briefly - don't dwell on API keys)
3. Build the prompt using incoming data
4. Show variable insertion from trigger data

**Demo Talking Points:**
> "See how I'm inserting the trigger data into my prompt? This is how we make it dynamic. The same workflow can process different inputs."

**Step 4: Configure Output (3 min)**
> "Finally, where does the result go? For this demo, email. Could be Slack, Google Doc, or any destination."

1. Add email module
2. Map AI response to email body
3. Configure recipient (use test email)

**Step 5: Test Run (3 min)**
> "Let's run it. Watch each step execute."

1. Click "Run once" / "Execute workflow"
2. Walk through execution as it happens
3. Show the output

**Demo Talking Points:**
> "Each step shows its input and output. This is crucial for debugging. If something breaks, you can see exactly where."

**Backup Plan:**
If demo fails:
1. Show prepared screenshots of each step
2. Walk through conceptually: "Here's what you would see..."
3. Acknowledge the issue: "This is actually a perfect example of why we need error handling - next segment!"

#### Facilitation Notes

**Critical Success:**
The demo MUST show a successful AI response. If API fails, have a backup scenario with cached response.

**Participant Questions During Demo:**
- "Can we ask questions?" - Yes, brief questions. "Let me finish this step, then I'll take questions."
- Keep demo moving but don't ignore confusion

---

### Segment 3: Error Handling Fundamentals (5 minutes)

**Learning Objective:** Understand what can go wrong and basic error handling patterns

**Slides:** 14-16

#### Content Delivery

**Key Point 1: What Can Go Wrong**
- API rate limits (especially on free tiers)
- Invalid input data (missing fields, wrong format)
- AI generation failures (timeout, refusal, malformed response)
- Connection timeouts

**Key Point 2: Basic Error Handling**
- Try/catch pattern in visual workflows
- Fallback routes
- Alert on failure (notify yourself)
- Logging errors for later review

**Key Point 3: The 80/20 Rule**
- Main message: Handle the common failures first
- "Don't try to handle every edge case. Handle the 3-4 things that actually break."

#### Facilitation Notes

**Keep It Brief:**
Error handling is important but don't over-elaborate. Participants will implement in homework.

**Transition to Segment 4:**
> "Error handling catches problems. Logging lets you learn from them."

---

### Segment 4: Logging and Monitoring Setup (4 minutes)

**Learning Objective:** Understand why and how to log from day one

**Slides:** 17-19

#### Content Delivery

**Key Point 1: Start Logging Immediately**
- Every execution should be tracked
- What to log: timestamp, input summary, output summary, duration, status

**Key Point 2: Simple Logging Approaches**
- Google Sheets (easiest - add a row for each execution)
- Airtable (more structured)
- Platform built-in logs (varies)

**Key Point 3: Quick Setup**
- Add logging as final workflow step
- Even simple logging is valuable
- "You can't improve what you don't measure"

#### Closing This Segment

**Key Takeaway:**
> "Log from day one. By Week 4 when we optimize, you'll have data to work with."

---

### Closing (3 minutes)

**Slides:** 20-22

**Do Not Skip This Section**

#### Homework Preview

**Script:**
> "Your homework is building, not just watching. Three exercises, about 60 minutes total.
>
> Exercise 2.1 is the big one - 35 minutes to build your first workflow. Use the template I demonstrated, adapted to your Block 1 template.
>
> Exercise 2.2 adds error handling - 15 minutes to make your workflow resilient.
>
> Exercise 2.3 sets up logging - 10 minutes. Simple but critical.
>
> You need 3+ test executions documented. Don't skip the testing."

#### Resources and Support

> "If you get stuck on API connections, check the platform documentation first. Common issues are covered there. If still stuck, post in support with screenshots."

#### Next Week Preview

> "Next week: Quality systems. We'll add automated quality checks using the LLM-as-judge pattern. Your workflow will evaluate its own output before delivering."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Do I need a paid API account for Claude/OpenAI?**
A: For Block 2 exercises, free tier credits are usually sufficient. Monitor your usage. If you exhaust free credits, we can discuss alternatives.

**Q: What if my workflow is different from the demo?**
A: Adapt the pattern. Every workflow has trigger → process → output. The specific modules vary but the structure is the same.

**Q: How long should each step take to execute?**
A: AI steps take 2-15 seconds typically. Total workflow under 30 seconds for simple workflows. Longer is fine but watch for timeouts.

### Technical Questions

**Q: The AI module isn't showing my expected output format.**
A: Check your prompt is requesting specific format. In the API settings, verify you're parsing the response correctly. JSON format helps.

**Q: My API connection keeps failing.**
A: Check API key is correct, has proper permissions, and hasn't expired. Verify you're within rate limits. Try the API directly in a tool like Postman to isolate the issue.

**Q: Which module do I use for Claude in Make?**
A: Use the HTTP module and configure it for Claude's API. Make has OpenAI native support; Claude requires HTTP configuration.

### Scope Questions

**Q: When do we add quality checks?**
A: Week 3. This week focus on getting the basic flow working. Quality systems layer on top.

**Q: Can I build a more complex workflow?**
A: Start simple. Get one workflow working well before adding complexity. The foundation matters.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| API connection fails | Check API key, try again | Use cached response or screenshots |
| Demo workflow errors | Debug briefly, narrate what's happening | "This is debugging in action" - make it educational |
| Platform is slow | Wait, narrate delay | Switch to screenshots |
| Screen share breaks | Restart share | Have participant share if needed |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Platform not set up | "I don't have an account" | Have them follow along, catch up in homework |
| Confused by interface | Lost expression, clicking randomly | Slow down, point to specific UI elements |
| API key issues | Can't connect to Claude/OpenAI | Offer 1:1 support after session |
| Overwhelmed | "This is a lot" | Reassure: "We'll practice in homework. Start simple." |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Demo fails repeatedly | Multiple errors | Switch to conceptual walkthrough with screenshots |
| Running behind | Past time checkpoints | Skip to critical steps, reference guide for details |
| Too easy for some | "I already know this" | Invite them to build alongside, add complexity |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save demo workflow | Keep for reference |
| Note any platform issues | For FAQ updates |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording | ☐ |
| Answer platform-specific questions | ☐ |
| Send API connection troubleshooting if needed | ☐ |
| Share demo workflow link (if possible) | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review submitted workflows (spot check) | ☐ |
| Identify participants struggling with builds | ☐ |
| Prepare Week 3 based on common issues | ☐ |
| Note any documentation gaps | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 2.1 | Working workflow + `workflow-1-documentation.md` | Platform + GitHub |
| 2.2 | Error handling added + documentation updated | Platform + GitHub |
| 2.3 | Logging configured + 3 logged executions | Logging destination + GitHub |

### Progress Check Approach

**How to Verify Completion:**
- Check for workflow documentation in repo
- Ask about test execution count in Week 3 opening
- Look for logging destination link

**Intervention Thresholds:**
- No working workflow: Critical - need 1:1 support before Week 3
- No error handling: Can add in Week 3 prep
- No logging: Important for Week 4, follow up

---

## Week-Specific Notes

### What Makes This Week Unique

- First hands-on building week
- Demo is critical - plan backup thoroughly
- API connection issues are common - have troubleshooting ready
- Participants vary widely in platform familiarity

### Dependencies

**Builds On:**
- Week 1: Platform selection and account creation
- Block 1: Prompt templates to use in AI step

**Sets Up:**
- Week 3: Quality systems layer on working workflows
- Week 4: Optimization requires logged execution data
- Capstone: First of three workflow templates

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Make HTTP module complex for Claude | Provide detailed configuration steps | Active |
| Free API tiers have low limits | Monitor usage, have backup plan | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- "What's the first thing we configure?" (Trigger)
- "Where does our Block 1 template go?" (AI processing step)
- Watch for following along during demo

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 2.1: Workflow runs successfully, produces expected output
- Exercise 2.2: At least one error handler configured
- Exercise 2.3: Logging captures all specified fields

**Common Issues to Flag:**
- Workflow runs but output is wrong (prompt issue)
- No error handling at all
- Test count less than 3

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Think in steps, not single prompts"
2. "Plan for failure from the start"
3. "Log everything from day one"

### If You Only Have Time For One Thing

A working demo of trigger → AI → output with successful execution.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Workflow steps | "Recipe steps, not a single instruction" | When explaining step breakdown |
| Error handling | "Seatbelts - you hope you don't need them" | When motivating error handling |
| Logging | "Flight recorder - know what happened" | When explaining logging value |

---

**Navigation:** [← Week 1 Instructor Guide](../week-1/instructor-guide.md) | **Week 2** | [Week 3 Instructor Guide →](../week-3/instructor-guide.md)
