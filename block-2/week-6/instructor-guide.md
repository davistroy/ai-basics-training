# **INSTRUCTOR GUIDE: BLOCK 2 WEEK 6**
## **Integration Patterns**

**Block:** 2: AI Workflow Engineering
**Week:** 6 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Advanced integration patterns and building fully integrated workflows |
| **Difficulty Level** | High |
| **Prep Time Required** | 60 minutes |
| **Demo Required** | Yes - Live integrated workflow building |
| **Tech Setup Needed** | Working MCP, automation platform, Claude API, output destinations |
| **Common Challenges** | MCP-workflow connection, human review queue design, pattern selection |

---

## Navigation

**Block Navigation:** [<- Week 5 Instructor Guide](../week-5/instructor-guide.md) | **Week 6** | [Week 7 Instructor Guide ->](../week-7/instructor-guide.md)

**Related Materials:**
- [Week 6 Presentation](presentation.md)
- [Week 6 Participant Guide](participant-guide.md)
- [Block 2 Main Document](../block-2.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 6 materials | |
| Prepare integrated workflow demo | Build a complete integrated workflow to demonstrate | |
| Set up human review queue | Create example review queue (Airtable/Trello) | |
| Test MCP-workflow integration | Verify MCP works with your automation platform | |
| Review Week 5 submissions | Check MCP setup status for all participants | |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | |
| Verify demo workflow | Run end-to-end test of integrated workflow | |
| Prepare architecture diagrams | Have visual examples ready | |
| Check all API connections | Verify Claude API, MCP, outputs all working | |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, automation platform, MCP, output destinations | |
| Test share | Verify screen sharing works | |
| Load demo scenario | Have test data ready for live demo | |
| Start recording | If session is recorded | |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Week 5 MCP recap, integration preview | Check MCP status |
| 0:03 | 10 min | Segment 1 | Integration Architecture Overview | 5 layers concept |
| 0:13 | 15 min | Segment 2 | Advanced Integration Patterns | 4 patterns deep dive |
| 0:28 | 12 min | Segment 3 | Building Integrated Workflows | Live demo |
| 0:40 | 5 min | Segment 4 | Documentation and Handoff | Quick but critical |
| 0:45 | - | Closing | Homework, capstone prep preview | Emphasize Week 7 |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Segment 2: Cover Sequential and Human-in-the-Loop patterns only (most common)
- Segment 4: Assign documentation as extended homework reading

**If Running Ahead:**
- Segment 2: Add discussion of when to use each pattern
- Segment 3: Extend demo with additional routing scenarios

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:13 | Architecture overview must be complete |
| End Pattern 2 | 0:20 | Prioritize remaining patterns |
| Demo working | 0:35 | This is the key demonstration moment |
| Start Closing | 0:42 | Must emphasize capstone prep |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants
2. Quick MCP status check
3. Bridge from configuration to integration
4. Preview the integration focus

**Opening Script:**
> "Welcome to Week 6! Last week we configured MCP - Claude can now access your files and GitHub directly. Today we put it all together. We're building fully integrated workflows that combine triggers, AI processing, quality checks, and human review. By the end of today, you'll understand the patterns that make enterprise-grade AI workflows possible."

**Engagement Opportunity:**
> "Quick check - who has MCP working? [Count] Excellent. If you're still troubleshooting, that's your first priority after this session."

---

### Segment 1: Integration Architecture Overview (10 minutes)

**Learning Objective:** Understand the five layers of integration architecture

**Slides:** 4-7

#### Content Delivery

**Key Point 1: The Integration Landscape**
- Show the complete flow diagram:
```
Triggers -> Workflow Platform -> AI + MCP -> Quality System -> Outputs
   ^                              |
External    <---- Feedback <--- Human Review
Systems
```
- Emphasize this is the full picture of what we're building

**Key Point 2: Five Integration Layers**
- Data layer: Where information originates
- Processing layer: How AI transforms data
- Quality layer: How we verify outputs
- Output layer: Where results are delivered
- Feedback layer: How we learn and improve

> "Think of these as the five floors of your workflow building. Each needs to be solid for the whole structure to work."

**Key Point 3: Tool Ecosystem**
- Automation platforms: Make, n8n (what they've been using)
- AI providers: Claude API, OpenAI API
- MCP servers: filesystem, GitHub (what they configured)
- Output destinations: Google Docs, Sheets, Slack, email

#### Facilitation Notes

**Watch For:**
- Participants feeling overwhelmed by complexity
- Confusion about where MCP fits in the architecture

**If Asked About Complexity:**
> "We're building this systematically. You've already mastered individual pieces - workflows, prompts, quality checks, MCP. Now we're connecting them."

**Transition to Segment 2:**
> "Now let's look at the specific patterns for connecting these components."

---

### Segment 2: Advanced Integration Patterns (15 minutes)

**Learning Objective:** Master four integration patterns and know when to use each

**Slides:** 8-13

#### Content Delivery

**Pattern 1: Sequential Pipeline (3 min)**
```
Trigger -> Gather -> Generate -> Evaluate -> Route -> Output
```
- Main message: Linear, predictable, easy to debug
- Best for: Straightforward transformations
- Example: Email summary workflow

**Pattern 2: Parallel Processing (4 min)**
```
Trigger -> [Generate A] --+
       -> [Generate B] --+--> Merge -> Evaluate -> Output
       -> [Generate C] --+
```
- Main message: Speed through concurrent processing
- Best for: Multi-part content, A/B testing approaches
- Example: Generate 3 versions, pick best

**Pattern 3: Iterative Refinement (4 min)**
```
Generate -> Evaluate -> (Pass?) -> Output
               | (Fail)
            Refine -> Re-generate -> Evaluate...
```
- Main message: Auto-improvement with safety limits
- Best for: Quality-critical content
- Critical: Always set max iterations (3-5 typical)
- Example: Report generation with revision loop

**Pattern 4: Human-in-the-Loop (4 min)**
```
Generate -> Evaluate -> (Review Needed?) -> Queue for Human
                              | (Pass)
                           Output
Human Review -> Approve/Edit -> Learn from Feedback
```
- Main message: Systematic oversight, not ad-hoc
- Best for: High-stakes content, building trust
- Key insight: Feedback captured for continuous improvement
- Example: Client communications, legal documents

#### Facilitation Notes

**Common Question:**
> "Which pattern should I use?"

**Response:**
> "Start with Sequential - it's simplest. Add complexity only when needed. Human-in-the-Loop is essential when building organizational trust in AI."

**Transition to Segment 3:**
> "Let's build one of these live. I'll show an integrated workflow using the Sequential pattern with Human-in-the-Loop routing."

---

### Segment 3: Building Integrated Workflows (12 minutes)

**Learning Objective:** See how to build a fully integrated workflow with MCP

**Slides:** 14-17

#### Demo Instructions

**Demo Duration:** 10-11 minutes

**Setup Required:**
- Automation platform (Make or n8n) with working scenario
- Claude API connection configured
- MCP with GitHub access (for templates)
- Output destination (Google Docs)
- Notification channel (Slack or email)

**Demo Scenario:**
Build a workflow that:
1. Triggers from form submission (or webhook for demo)
2. Fetches template from GitHub via MCP context
3. Generates content with Claude API
4. Evaluates quality with LLM-as-judge
5. Routes: pass -> output, fail -> review queue
6. Outputs to Google Doc
7. Notifies via Slack

**Demo Steps:**

**Step 1: Show Complete Flow (2 min)**
> "Here's the complete workflow we're building. Notice how each component connects."

- Walk through the visual workflow in your platform
- Highlight the decision points

**Step 2: MCP-Workflow Connection (3 min)**
> "The key integration point is getting MCP context into your workflow."

- Show how template content is fetched via MCP
- Demonstrate passing template to Claude API call
- Explain: "MCP gathers context, API does generation"

**Step 3: Quality Routing (3 min)**
> "This is where quality scores determine next steps."

- Show the router module
- Configure: score >= 4.0 goes to output, below goes to review
- Show both paths in the workflow

**Step 4: Live Test (3 min)**
> "Let's run this end-to-end."

- Trigger the workflow with test data
- Show execution flow
- Display generated output in destination
- Show Slack notification

**Backup Plan:**
If demo fails:
1. Show prepared screenshots of successful execution
2. Walk through conceptually with workflow screenshots
3. Debug visible issues as teaching moment

---

### Segment 4: Documentation and Handoff (5 minutes)

**Learning Objective:** Understand documentation requirements for team handoff

**Slides:** 18-19

**Key Points:**

**Documentation Requirements (3 min)**
- Architecture diagram (visual overview)
- Data flow description (what goes where)
- Component dependencies (what needs what)
- Configuration details (API keys, tokens, settings)
- Troubleshooting guide (common issues and fixes)

**Team Handoff Considerations (2 min)**
- Access requirements: Who needs which API keys?
- Training needed: What skills are required?
- Support plan: Who handles issues?

**Key Message:**
> "Documentation isn't optional - it's what makes your workflow sustainable. If you can't hand it off, you own it forever."

---

### Closing (3 minutes)

**Slides:** 20-21

**Script:**
> "Your homework builds your third fully integrated workflow. About 60 minutes total.
>
> Exercise 6.1 - 30 minutes - build an integrated workflow using one of today's patterns. This is your third workflow.
>
> Exercise 6.2 - 20 minutes - design and implement a human review system. Where do flagged items go? What information is included?
>
> Exercise 6.3 - 10 minutes - create your integration architecture document. This becomes part of your capstone portfolio.
>
> Critical: Next week is Capstone Preparation. You need ALL THREE workflows working. Start collecting execution data now - run each workflow at least 5 times. We're calculating real impact metrics."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: How do I choose between patterns?**
A: Start with Sequential for simplicity. Use Parallel when you need speed or multiple versions. Use Iterative when quality is critical and auto-improvement is feasible. Use Human-in-the-Loop when building trust or for high-stakes content.

**Q: Can I combine patterns?**
A: Absolutely. Most production workflows combine patterns. For example, Sequential with Human-in-the-Loop routing is very common.

### Technical Questions

**Q: How do I get MCP context into my automation platform?**
A: Two approaches: (1) Use Claude Desktop with MCP to gather context, then pass to your workflow. (2) Use Claude API in your workflow with context you've prepared. Week 6 focuses on the architecture; exact implementation varies by platform.

**Q: How do I implement the review queue?**
A: Common options: Airtable (structured data + views), Trello (kanban style), Google Sheet (simple), or email (basic). Choose based on your team's existing tools.

**Q: What if my MCP isn't working yet?**
A: That's your first priority. You can still design the workflow architecture conceptually, but you need MCP for full integration. Reach out for support.

### Scope Questions

**Q: How much should I document?**
A: Enough that someone else can understand and maintain your workflow. If you're hit by a bus (or go on vacation), could a colleague take over?

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Demo workflow fails | Show prepared screenshots | Walk through conceptually |
| MCP not connecting | Acknowledge and troubleshoot briefly | Use static template for demo |
| API rate limit | Switch to pre-recorded demo | Explain concept without live execution |
| Output destination fails | Show mock output | Focus on workflow logic |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| MCP still not working | "I couldn't get MCP configured" | Prioritize 1:1 support |
| Pattern confusion | "Which one do I use?" | Start with Sequential, add complexity later |
| Overwhelmed by integration | "This is too complex" | Break into smaller pieces |
| Unclear on human review | "Where do flagged items go?" | Provide specific tool recommendations |

---

## Post-Session Tasks

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording | |
| Share architecture diagram template | |
| Send review queue examples | |
| Follow up on MCP issues | |

### Within 1 Week

| Task | Done? |
|------|-------|
| Check workflow completion status | |
| Verify all participants have 3 workflows | |
| Prepare capstone timeline for Week 7 | |
| Review integration documentation submissions | |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 6.1 | Third integrated workflow + architecture doc | Automation platform + GitHub |
| 6.2 | Human review queue + feedback process | Tool of choice + GitHub documentation |
| 6.3 | Integration architecture document | GitHub: `integration-architecture.md` |

### Progress Check Approach

**How to Verify Completion:**
- Check for third workflow in automation platform
- Look for integration-architecture.md in repos
- Verify review queue exists somewhere

**Intervention Thresholds:**
- No third workflow: Critical - need 1:1 support
- Missing documentation: Important - affects capstone
- Review queue not set up: Can catch up during Week 7

---

## Week-Specific Notes

### What Makes This Week Unique

- Synthesizes all previous weeks
- Highest complexity session in Block 2
- Direct preparation for capstone
- Documentation becomes deliverable

### Dependencies

**Builds On:**
- Week 2-4: Workflows 1 and 2
- Week 5: MCP configuration
- All of Block 1: Prompt engineering foundation

**Sets Up:**
- Week 7: Capstone preparation
- Week 8: Capstone evaluation
- Block 3: Advanced patterns and scale

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| MCP-workflow integration complex | Focus on concepts, implementation varies | Active |
| Review queue tools vary | Provide examples for Airtable, Trello, Sheets | Active |
| Pattern selection overwhelming | Default to Sequential + Human-in-the-Loop | Active |

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Integration patterns provide structure for complex workflows"
2. "Human-in-the-Loop is systematic, not ad-hoc"
3. "Documentation enables handoff - don't skip it"

### If You Only Have Time For One Thing

Sequential pipeline with Human-in-the-Loop routing - this covers most real-world needs.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Five Layers | "Floors of a building" | Explaining architecture |
| Integration Patterns | "Recipes with variations" | Explaining pattern choice |
| Human Review | "Quality control checkpoint" | Explaining oversight |
| Documentation | "User manual for your workflow" | Explaining why document |

---

**Navigation:** [<- Week 5 Instructor Guide](../week-5/instructor-guide.md) | **Week 6** | [Week 7 Instructor Guide ->](../week-7/instructor-guide.md)
