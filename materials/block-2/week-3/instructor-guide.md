# **INSTRUCTOR GUIDE: BLOCK 2 WEEK 3**
## **Quality Systems + Template Workflows**

**Block:** 2: AI Workflow Engineering
**Week:** 3 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Adding automated quality checks using LLM-as-judge pattern and building second workflow |
| **Difficulty Level** | Medium-High |
| **Prep Time Required** | 35 minutes |
| **Demo Required** | Yes - Quality evaluation module demo |
| **Tech Setup Needed** | Working workflow from Week 2, JSON parsing demo ready |
| **Common Challenges** | JSON parsing issues, quality threshold calibration, routing logic |

---

## Navigation

**Block Navigation:** [← Week 2 Instructor Guide](../week-2/instructor-guide.md) | **Week 3** | [Week 4 Instructor Guide →](../week-4/instructor-guide.md)

**Related Materials:**
- [Week 3 Presentation](presentation.md)
- [Week 3 Participant Guide](participant-guide.md)
- [Block 2 Main Document](../block-2.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 3 materials | ☐ |
| Build quality demo | Create evaluation module with routing | ☐ |
| Test JSON parsing | Verify JSON response handling works | ☐ |
| Prepare backup | Create screenshots of quality routing | ☐ |
| Review Week 2 submissions | Check who has working workflows | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load demo environment | Have workflow with quality module ready | ☐ |
| Prepare sample outputs | Good and bad outputs for evaluation demo | ☐ |
| Review participant progress | Identify who may need catch-up support | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, platform, sample outputs | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Load demo scenario | Have quality evaluation ready to show | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Week 2 recap, workflow status check | Quick troubleshooting |
| 0:03 | 12 min | Segment 1 | Quality in Automated Workflows | Foundation concepts |
| 0:15 | 10 min | Segment 2 | Automated Quality Checks | LLM-as-judge pattern |
| 0:25 | 13 min | Segment 3 | JSON Data Structures | Practical patterns |
| 0:38 | 4 min | Segment 4 | Template Workflow Pattern | Quick overview |
| 0:42 | 3 min | Closing | Homework, Week 4 preview | Don't skip |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Segment 3: Focus on essential JSON patterns, skip advanced examples
- Segment 4: Briefly introduce, detailed content in participant guide

**If Running Ahead:**
- Segment 2: Show full routing logic in demo
- Segment 3: Cover more JSON examples

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | Shorten quality gate details |
| End Segment 2 | 0:25 | Must cover evaluation prompt pattern |
| Start Closing | 0:42 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants back
2. Quick status check on Week 2 workflows
3. Address any critical issues briefly
4. Preview quality focus for today

**Opening Script:**
> "Welcome to Week 3! Today we add intelligence to your workflows - automated quality checks. Quick show of hands: who has a working workflow with at least 3 successful executions? [Count] Great. For those who didn't quite finish, let's talk after - but follow along today because you'll apply this immediately."

**Engagement Opportunity:**
> "How consistent was the output quality from your workflow? Did every execution produce usable output, or were some better than others?"

---

### Segment 1: Quality in Automated Workflows (12 minutes)

**Learning Objective:** Understand quality as operating procedures and the automation quality challenge

**Slides:** 4-8

#### Content Delivery

**Key Point 1: Quality as Domain Memory**
- Main message: Quality systems ARE operating procedures for AI
- Connect to Block 3 preview: Three Pillars (Explicit Goals, Progress Records, Operating Procedures)
- Your quality rubrics from Block 1 become automated checks

**Key Point 2: The Automation Quality Challenge**
- Main message: Manual review doesn't scale
- Example: "Reviewing 10 outputs a day is manageable. 100 is exhausting. 1000 is impossible."
- Inconsistent quality undermines trust in the system

**Key Point 3: Quality Gate Implementation**
- Main message: Three layers of quality checking
- Pre-generation: Input validation (is the input complete and valid?)
- Post-generation: Output evaluation (does output meet standards?)
- Human review: Escalation when automated checks fail

#### Facilitation Notes

**Watch For:**
- Participants who think quality checks slow things down
- Questions about "why can't we just trust the AI?"

**If Asked About Trust:**
> "We're building trustworthy systems, not trusting AI blindly. The quality check is what makes the system trustworthy. It catches the 10-20% of outputs that need work."

**Transition to Segment 2:**
> "Now let's see how to implement these quality checks using AI itself."

---

### Segment 2: Automated Quality Checks (10 minutes)

**Learning Objective:** Understand and apply the LLM-as-judge pattern

**Slides:** 9-12

#### Content Delivery

**Key Point 1: Using AI to Check AI**
- Main message: A second AI call evaluates the first AI's output
- Pattern: Generate → Evaluate → Route
- This is the LLM-as-judge pattern

**Key Point 2: The Evaluation Prompt Pattern**
- Show the evaluation prompt structure
- Criteria come from Block 1 rubrics
- JSON output for reliable parsing
- Clear pass/fail threshold

**Key Point 3: Routing Logic**
- Score >= 4: Proceed to output (high quality)
- Score 3-3.9: Flag for human review (acceptable but needs checking)
- Score < 3: Regenerate or fail (below standards)

#### Demo Instructions

**Demo Duration:** 4-5 minutes

**Setup Required:**
- Workflow with AI generation step
- Evaluation step added
- Routing configured

**Demo Steps:**
1. Show the evaluation prompt in the workflow
2. Run with a good input → show it passes
3. Explain JSON response parsing
4. Show routing logic configuration
5. Optional: Run with intentionally poor input to show fail path

**Demo Talking Points:**
> "See how the evaluation prompt mirrors your Block 1 rubric? Same criteria, just formatted for automation."
> "The JSON output is critical - we need structured data to make routing decisions."

---

### Segment 3: JSON Data Structures in Workflows (13 minutes)

**Learning Objective:** Use JSON for structured data flow between workflow steps

**Slides:** 13-17

#### Content Delivery

**Key Point 1: Why JSON for Workflows**
- Structured data between steps
- Easy parsing and manipulation
- Standard format across platforms
- AI generates JSON reliably (with proper prompting)

**Key Point 2: Common Workflow Data Patterns**
- Show the standard execution data structure
- Walk through each section: execution, input, processing, quality, output
- Explain how this enables analysis and optimization

**Key Point 3: JSON in AI Prompts**
- Request JSON output explicitly
- Provide schema or example
- Parse and validate in workflow
- Handle malformed JSON gracefully

#### Facilitation Notes

**Watch For:**
- Participants unfamiliar with JSON syntax
- Confusion about parsing in their specific platform

**If Asked About JSON Errors:**
> "Malformed JSON is a common issue. Always wrap JSON parsing in error handling. If the AI doesn't return valid JSON, catch it and either retry or flag for review."

---

### Segment 4: Template Workflow Pattern (4 minutes)

**Learning Objective:** Understand workflow cloning and template versioning

**Slides:** 18-19

#### Content Delivery

**Key Point 1: The Reusable Workflow Template**
- Clone workflow 1 to create workflow 2
- Replace prompt template (different deliverable type)
- Keep quality and logging infrastructure
- Adjust data mappings as needed

**Key Point 2: Template Versioning**
- v1.0, v1.1, v2.0 naming convention
- Track changes in documentation
- A/B testing concept (preview for Week 4)

---

### Closing (3 minutes)

**Slides:** 20-22

**Script:**
> "Your homework this week is substantial - about 60 minutes.
>
> Exercise 3.1 - 25 minutes - add quality check module to your workflow. Create the evaluation prompt, add the step, configure routing.
>
> Exercise 3.2 - 25 minutes - build your second workflow by cloning the first. Swap templates, adjust mappings, test with new use case.
>
> Exercise 3.3 - 10 minutes - design your JSON data structure for logging.
>
> By end of week, you should have two working workflows with quality checks."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Doesn't the quality check slow down the workflow?**
A: It adds a few seconds per execution. But catching a bad output before it reaches a client is worth far more than the time cost. Think of it as insurance, not overhead.

**Q: What if the quality checker disagrees with my judgment?**
A: Calibrate your thresholds based on actual results. If outputs you consider good are failing, lower the threshold. If bad outputs pass, raise it. Use your first 10-20 executions to tune.

**Q: Can I use a cheaper/faster model for quality checks?**
A: Absolutely. Quality checks are often simpler than generation. A smaller model (GPT-4o-mini, Claude Haiku) can handle evaluation at lower cost.

### Technical Questions

**Q: My JSON parsing keeps failing. What's wrong?**
A: Common issues: AI includes extra text before/after JSON, uses invalid JSON syntax, or has different key names than expected. Add explicit instruction: "Respond with ONLY valid JSON, nothing else." Also add error handling for parse failures.

**Q: How do I configure routing in Make/n8n?**
A: In Make, use Router module after parsing. In n8n, use IF node. Route based on the parsed quality score value.

### Scope Questions

**Q: When do we connect this to MCP?**
A: Weeks 5-6. This week focus on quality systems. MCP integration layers on top of working, quality-checked workflows.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| JSON parsing fails in demo | Show the raw response, explain the issue | Use prepared screenshots |
| Quality score unexpected | Walk through evaluation criteria | Educational moment about calibration |
| Routing not working | Check condition logic | Explain conceptually |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| No working workflow from Week 2 | Can't apply quality checks | Offer 1:1 catch-up, provide sample workflow |
| Confused by JSON | Lost expression, syntax questions | Slow down, provide JSON validator resource |
| Threshold calibration frustration | "It keeps failing good output" | Explain calibration process, suggest lowering threshold temporarily |

---

## Post-Session Tasks

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording | ☐ |
| Answer JSON/routing questions | ☐ |
| Share JSON validator resource | ☐ |
| Check on participants without Week 2 workflow | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review quality evaluation prompts | ☐ |
| Check that participants have 2 workflows | ☐ |
| Identify calibration issues for Week 4 discussion | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 3.1 | Quality check module + evaluation prompt | Platform + GitHub |
| 3.2 | Second workflow + template family docs | Platform + GitHub |
| 3.3 | `workflow-data-schema.json` | GitHub |

### Progress Check Approach

**How to Verify Completion:**
- Check for quality evaluation prompt in repos
- Verify two workflows exist in platform
- Look for template family documentation

**Intervention Thresholds:**
- No quality check added: Critical for capstone quality
- Only one workflow: Need second for capstone requirement
- No JSON schema: Less critical but important for Week 4

---

## Week-Specific Notes

### What Makes This Week Unique

- Conceptual shift: AI evaluating AI
- JSON skills become critical
- Second workflow means template thinking
- Foundation for optimization in Week 4

### Dependencies

**Builds On:**
- Week 2: Working workflow to add quality checks to
- Block 1: Quality rubrics become evaluation criteria

**Sets Up:**
- Week 4: Optimization uses quality data
- Week 5-6: MCP integrates with quality-checked workflows
- Capstone: Quality systems are evaluation criterion

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Quality systems ARE operating procedures for AI"
2. "Use AI to check AI - the LLM-as-judge pattern"
3. "JSON is how data flows between steps"

### If You Only Have Time For One Thing

The evaluation prompt pattern with JSON output and routing logic.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Quality check | "Editor before publishing" | When explaining quality gates |
| LLM-as-judge | "Peer review for AI" | When introducing the pattern |
| JSON structure | "Standard shipping container" | When explaining data consistency |

---

**Navigation:** [← Week 2 Instructor Guide](../week-2/instructor-guide.md) | **Week 3** | [Week 4 Instructor Guide →](../week-4/instructor-guide.md)
