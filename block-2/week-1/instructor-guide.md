# **INSTRUCTOR GUIDE: BLOCK 2 WEEK 1**
## **Automation Platforms Introduction**

**Block:** 2: AI Workflow Engineering
**Week:** 1 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Introduction to automation platforms and MCP for workflow engineering |
| **Difficulty Level** | Medium |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Yes - Browse MCP Server Registry |
| **Tech Setup Needed** | Claude Desktop installed, MCP registry access, platform comparison open |
| **Common Challenges** | Platform selection paralysis, MCP concept confusion |

---

## Navigation

**Block Navigation:** [Block 1 Week 8](../../block-1/week-8/instructor-guide.md) | **Week 1** | [Week 2 Instructor Guide →](../week-2/instructor-guide.md)

**Related Materials:**
- [Week 1 Presentation](presentation.md)
- [Week 1 Participant Guide](participant-guide.md)
- [Block 2 Main Document](../block-2.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 1 materials and Block 2 overview | ☐ |
| Test demo | Browse MCP Server Registry, test filtering and searching | ☐ |
| Check resources | Verify all platform documentation links work | ☐ |
| Prepare backup | Create screenshots of MCP registry and platform comparisons | ☐ |
| Review previous | Check Block 1 capstone feedback and common issues | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice transitions between segments | ☐ |
| Prepare materials | Have MCP registry open, platform comparison ready | ☐ |
| Check participant progress | Review who completed Block 1 capstone | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, MCP registry, Make/n8n sites | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Brief chat about Block 1 experience | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome to Block 2, Block 1 recap | Celebrate capstone completions |
| 0:03 | 8 min | Segment 1 | Welcome to Block 2 + Maturity Progression | Set context for the block |
| 0:11 | 12 min | Segment 2 | Automation Platform Landscape | Include data handling awareness |
| 0:23 | 12 min | Segment 3 | Decision Matrix for Platform Selection | Live exercise with group |
| 0:35 | 7 min | Segment 4 | MCP Introduction + Registry Preview | Live demo of registry |
| 0:42 | 3 min | Closing | Homework, resources, Week 2 preview | Don't skip |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Segment 2: Reference data handling awareness slide but don't elaborate
- Segment 3: Skip group exercise, do quick walkthrough instead
- Segment 4: Show 2 MCP servers instead of browsing extensively

**If Running Ahead:**
- Segment 2: More detailed platform comparison discussion
- Segment 3: Do full group scoring exercise
- Segment 4: Show more MCP servers and discuss community options

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:11 | Shorten Block 1 recap |
| End Segment 2 | 0:23 | Reference data handling, don't elaborate |
| Start Closing | 0:42 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants to Block 2
2. Acknowledge Block 1 capstone completions
3. Set expectations for the engineering mindset shift
4. Preview today's session

**Opening Script:**
> "Welcome to Block 2: AI Workflow Engineering! You've all completed Block 1 and created your Prompt Libraries. Today marks a significant shift - we're moving from crafting individual prompts to building automated workflows. By the end of today, you'll have selected your automation platform and understand how MCP enables powerful AI integrations."

**Engagement Opportunity:**
> "Quick show of hands: Who found themselves wishing they could automate repetitive prompting tasks during Block 1?"

[Wait for responses - this validates the need for Block 2]

---

### Segment 1: Welcome to Block 2 + Recap (8 minutes)

**Learning Objective:** Understand the maturity progression from templates to workflows to automation

**Slides:** 4-7

#### Content Delivery

**Key Point 1: Maturity Progression**
- Main message: You're leveling up from template user to workflow engineer
- Example: "In Block 1, you created a proposal template. In Block 2, you'll build a workflow that triggers when a client request arrives, pulls the template, generates the proposal, checks quality, and delivers it."
- Common misconception: "Automation is just running prompts faster" - No, it's about reliable, quality-controlled processes

**Key Point 2: The Key Shift**
- Main message: From manual prompting to automated execution
- Demonstration: Show simple before/after flow diagram
- Participant relevance: "Think about the task you identified in your Block 1 priority matrix - that's what we'll automate"

**Key Point 3: Capstone Preview**
- Main message: You'll build an AI Workflow Toolkit with 3 workflows, MCP integration, and impact measurement
- Practice preview: Each exercise builds toward capstone components

#### Facilitation Notes

**Watch For:**
- Participants who seem overwhelmed by the scope
- Questions about "do we need to code?"

**If Asked About Coding:**
> "Block 2 uses no-code and low-code platforms. We focus on visual workflow builders. If you can drag and drop, you can build workflows."

**Transition to Segment 2:**
> "Now that you know where we're headed, let's explore the platforms that will get us there."

---

### Segment 2: Automation Platform Landscape (12 minutes)

**Learning Objective:** Understand platform categories and key selection criteria

**Slides:** 8-12

#### Content Delivery

**Key Point 1: The Evolution**
- Main message: Manual → Templates → Workflows → Agents is a natural progression
- Visual to emphasize: Evolution diagram showing increasing automation
- Show the progression participants are on

**Key Point 2: Platform Categories**
- Main message: Match platform to your skills and needs
- Present the four categories with clear use cases:
  - No-code (Zapier, Make): Business users, quick setup
  - Low-code (n8n, Pipedream): More control, technical comfort needed
  - AI-native (Claude MCP, LangChain): Deep AI integration focus
  - Enterprise (UiPath): Large scale, heavy governance

**Key Point 3: Key Considerations**
- Main message: Six criteria for platform selection
- Walk through: Learning curve, AI integration, cost, collaboration, security, scalability
- Real-world application: "For most consultants, Make or n8n hits the sweet spot"

**Key Point 4: Data Handling Awareness**
- Main message: Know your data flows before automating
- Critical points: Data retention, client obligations, anonymization
- Emphasize: "This isn't about fear - it's about awareness and documentation"

#### Demo Instructions (if applicable)

**Demo Duration:** 3 minutes

**Setup Required:**
- Platform comparison chart visible
- Make and n8n homepages open in tabs

**Demo Steps:**
1. Show Make interface briefly (visual workflow builder)
2. Show n8n interface (more technical but powerful)
3. Point out AI integration options in each

**Backup Plan:**
If demo fails:
1. Use prepared screenshots
2. Reference documentation links
3. Focus on conceptual comparison

#### Facilitation Notes

**Energy Check:**
At this point, participants may be experiencing information overload from platform options. Use the decision matrix in the next segment to give structure.

**Transition to Segment 3:**
> "With all these options, how do you decide? That's where our decision matrix comes in."

---

### Segment 3: Decision Matrix for Platform Selection (12 minutes)

**Learning Objective:** Apply systematic evaluation to platform selection

**Slides:** 13-16

#### Content Delivery

**Key Point 1: The Decision Matrix Framework**
- Main message: Systematic evaluation over gut feeling
- Present the six criteria with weights
- Explain scoring guide (1-5)

**Key Point 2: Criterion Deep Dive**
- Walk through each criterion briefly:
  - Learning Curve (20%): How fast can you be productive?
  - AI Integration (25%): Highest weight - this is an AI workflow course!
  - Cost (15%): Free tiers vs. execution costs
  - Collaboration (15%): Team features for eventual rollout
  - Security (15%): Data handling capabilities
  - Scalability (10%): Growth potential

#### Interactive Element

**Activity Type:** Live Group Scoring

**Activity Duration:** 5 minutes

**Instructions:**
1. "Let's score Make together as a group on one criterion: Learning Curve"
2. "Who has tried Make? What would you give it for ease of learning?"
3. Collect 2-3 responses
4. "Now you'll do this for your top 3 platforms in homework"

**Debrief Points:**
> "Notice how having specific criteria reduces the 'which one feels right?' guesswork. This same approach works for many decisions."

#### Facilitation Notes

**Common Confusion Point:**
Participants may worry about making the "wrong" choice.

**Clarification Approach:**
> "There's no wrong answer here. We're looking for 'good enough to learn with.' You can always switch platforms later. The skills transfer."

---

### Segment 4: MCP Introduction + Registry Preview (7 minutes)

**Learning Objective:** Understand MCP as the integration layer for AI workflows

**Slides:** 17-21

#### Content Delivery

**Key Point 1: MCP Concept - "USB-C for AI"**
- Main message: MCP is a universal protocol for connecting AI to tools
- Analogy: "Just like USB-C lets you connect any device to any computer, MCP lets Claude connect to any tool that speaks the protocol"
- Components: Host (Claude), Server (the bridge), Tools/Resources (capabilities)

**Key Point 2: MCP Server Registry**
- Main message: There's an ecosystem of ready-to-use servers
- Official servers: filesystem, GitHub, Slack, databases
- Community servers: Google Drive, Notion, custom tools

#### Demo Instructions

**Demo Duration:** 3 minutes

**Setup Required:**
- MCP Server Registry open (https://github.com/modelcontextprotocol/servers)
- Claude Desktop installed

**Demo Steps:**
1. Navigate to MCP Server Registry
2. Show the categories of servers
3. Click into filesystem server - show what it does
4. Click into GitHub server - show capabilities
5. "In homework, you'll identify which servers are relevant to YOUR work"

**Demo Talking Points:**
> "This is where you'll find pre-built integrations. Instead of coding connections, you configure these servers."
> "Notice the filesystem server - this lets Claude read and write files directly. The GitHub server lets Claude access your repositories."

**Backup Plan:**
If demo fails:
1. Show prepared screenshots of registry
2. List the main servers verbally
3. Point to resources for self-exploration

**Key Point 3: Performance Monitoring Preview**
- Main message: Track from the start
- Core metrics: Execution time, success rate, quality, cost
- Preview: "Week 2 we'll set up logging. Today we define what to track."

#### Closing This Segment

**Key Takeaway:**
> "MCP is the secret weapon that makes AI workflows powerful. You don't need to be a developer to use it - you configure, not code."

**Connection to Homework:**
> "In Exercise 1.2, you'll explore the registry and identify servers for your work."

---

### Closing (3 minutes)

**Slides:** 22-24

**Do Not Skip This Section** - even if running behind

#### Homework Preview

**Key Actions:**
1. Overview all three exercises
2. Highlight platform decision as primary focus
3. Note Claude Desktop installation requirement

**Script:**
> "Your homework includes three exercises totaling about 60 minutes.
>
> Exercise 1.1 is the big one - 25 minutes to research platforms, complete your decision matrix, and create your account. This is critical - you need a working platform for Week 2.
>
> Exercise 1.2 takes 20 minutes to explore the MCP registry and identify relevant servers.
>
> Exercise 1.3 is 15 minutes to define performance metrics for your first workflow.
>
> Make sure Claude Desktop is installed - MCP requires it."

#### Resources and Support

> "Platform documentation links are in your participant guide. If you get stuck on platform selection, post in the support channel with your top 2-3 options and your specific concerns."

#### Next Week Preview

> "Next week we build your first workflow. Come with your platform account ready and tutorials completed. We'll go from zero to functional workflow in 45 minutes."

#### Session Close

> "Questions before we wrap? ... Great to have you all starting Block 2. The engineering mindset is a significant step up - you're moving from prompt user to workflow builder. See you next week!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Do I really need to pick a platform now? Can I wait and see?**
A: You need a working platform for Week 2 when we build workflows. The decision matrix helps you decide quickly. If still stuck, start with Make - it's the most beginner-friendly with strong AI integration.

**Q: What if I'm already using a different automation platform?**
A: If you have existing platform experience, you can use that platform. The concepts transfer. Just ensure it has AI/API integration capabilities.

**Q: How is MCP different from regular API integration?**
A: MCP is a standardized protocol specifically designed for AI interactions. Instead of building custom integrations, you use pre-built MCP servers that handle the connection. It's like the difference between writing custom drivers and using USB.

### Technical Questions

**Q: Do I need to install anything besides Claude Desktop?**
A: For MCP, Claude Desktop is the main requirement. For your automation platform, most are web-based (Make, Zapier). N8n can be self-hosted but also has a cloud option.

**Q: Is there a cost to the platforms?**
A: All recommended platforms have free tiers sufficient for learning. Make, n8n, and Zapier all offer free accounts. You may hit limits with heavy usage, but for Block 2 exercises, free tiers work fine.

### Scope Questions

**Q: Will we build actual agents in this block?**
A: Block 2 focuses on workflows with AI components. Block 3 covers agent architecture. By the end of Block 2, you'll have the foundation to build reliable agents in Block 3.

**Q: How does this connect to my Block 1 work?**
A: Your Block 1 prompt templates become inputs to your workflows. Your quality rubrics become automated quality checks. Everything you built transfers directly.

### Pushback/Objections

**Q: My organization has strict data policies. Can I still do this?**
A: Yes - that's why we emphasized data handling awareness. Document your data flows, use anonymized test data, and check with your compliance team if needed. Many platforms offer enterprise tiers with enhanced security.

**Q: This seems like a lot of new tools to learn. Is it worth it?**
A: The time investment in learning pays off quickly. Once you have one workflow running, you can replicate the pattern. Most participants save hours per week within a few weeks of Block 2.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| MCP registry not loading | Refresh, try different browser | Use prepared screenshots |
| Screen share fails | Restart share, switch to window share | Have participant share if needed |
| Platform demo breaks | Switch to screenshots | Walk through conceptually |
| Audio issues | Ask participants to type questions | Continue with video only |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Platform choice paralysis | "There are too many options" | Focus on Make as default recommendation |
| MCP confusion | "I don't understand how it connects" | Use USB-C analogy, show concrete example |
| Overwhelmed by scope | Silence, worried expressions | Remind them it's step-by-step over 8 weeks |
| Block 1 gaps | Missing capstone components | Suggest 1:1 follow-up, don't hold up group |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Content too easy | "We know this" | Add more technical depth, discuss edge cases |
| Content too hard | Many basic questions | Slow down, more analogies |
| Off-topic tangent | Discussion drifting to unrelated tools | "Great point - let's discuss in support channel" |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save any chat questions | For follow-up |
| Note which platforms generated most interest | For future cohorts |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | ☐ |
| Answer pending questions in support channel | ☐ |
| Send reminder about Claude Desktop installation | ☐ |
| Share additional platform resources if requested | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review platform decision submissions | ☐ |
| Check who has created platform accounts | ☐ |
| Identify participants needing platform support | ☐ |
| Prepare Week 2 demo based on most popular platform | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 1.1 | `platform-decision-matrix.md` | Participant's GitHub repo |
| 1.2 | `mcp-server-analysis.md` | Participant's GitHub repo |
| 1.3 | `workflow-metrics-definition.md` | Participant's GitHub repo |

### Progress Check Approach

**How to Verify Completion:**
- Check for platform-decision-matrix.md in repos
- Verify platform account created (ask in Week 2 opening)
- Look for Claude Desktop installation confirmation

**Intervention Thresholds:**
- No platform account by Week 2: Critical - need 1:1 support
- Missing MCP analysis: Can catch up, but follow up
- Missing metrics definition: Important for Week 2, prompt completion

---

## Week-Specific Notes

### What Makes This Week Unique

- First week of Block 2 - sets tone for the block
- Critical decision point (platform selection) affects all future weeks
- Introduction to MCP - new concept for most participants
- Bridge from Block 1 work to new capabilities

### Dependencies

**Builds On:**
- Block 1 Capstone: Prompt library, templates, quality rubrics
- Block 1 Task Priority Matrix: Workflow candidate identification
- GitHub repository skills from Block 1

**Sets Up:**
- Week 2: First workflow build (requires platform account)
- Week 5: MCP integration (requires MCP understanding from this week)
- Capstone: All three workflows use chosen platform

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| MCP registry occasionally slow | Have screenshots ready | Active |
| Some platforms require credit card for free tier | Recommend Make (no card needed) | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- "What's the main difference between no-code and AI-native platforms?"
- Watch for nodding during MCP explanation
- Observe participation in group scoring exercise

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 1.1: Clear rationale in platform decision, weighted scores calculated
- Exercise 1.2: Minimum 5 servers identified with use cases
- Exercise 1.3: All metric categories addressed with realistic targets

**Common Issues to Flag:**
- Platform decision without completed matrix (gut feeling choice)
- MCP servers listed without clear use cases
- Metrics too vague ("good quality" vs. "score >= 4/5")

### Connecting to Capstone

**Capstone Relevance:**
This week's work contributes to the capstone by:
- Platform becomes the foundation for all 3 workflow templates
- MCP servers identified now become Week 5-6 integrations
- Metrics defined now become the basis for impact measurement

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Quick pulse check: "On a scale of 1-5, how confident are you in selecting a platform?"
- Note common questions for FAQ updates

**Improvement Log:**

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| | | | |

### Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial guide created | Training Team |

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Block 2 is about building systems, not just prompts"
2. "MCP is USB-C for AI - universal connections without custom code"
3. "Measure from day one - what you track, you can improve"

### If You Only Have Time For One Thing

Platform selection with decision matrix - participants must have accounts for Week 2.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| MCP Protocol | "USB-C for AI" | When explaining how MCP works |
| Platform Selection | "Choosing a car - match to your driving needs" | When participants are paralyzed by options |
| Workflow vs. Prompt | "Recipe vs. single ingredient" | When distinguishing Block 2 from Block 1 |

---

**Navigation:** [Block 1 Week 8](../../block-1/week-8/instructor-guide.md) | **Week 1** | [Week 2 Instructor Guide →](../week-2/instructor-guide.md)
