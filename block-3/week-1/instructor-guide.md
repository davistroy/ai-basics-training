# **INSTRUCTOR GUIDE: BLOCK 3 WEEK 1**
## **Agent Fundamentals**

**Block:** 3: AI Automation Architecture
**Week:** 1 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Understanding agent fundamentals and the Two-Agent Architecture Pattern |
| **Difficulty Level** | Medium |
| **Prep Time Required** | 45 minutes |
| **Demo Required** | Yes - RFP Response Agent walkthrough |
| **Tech Setup Needed** | Presentation slides, MCP configured, example agent design document |
| **Common Challenges** | Confusion between agents and workflows; complexity of Two-Agent Pattern |

---

## Navigation

**Block Navigation:** [Block 2 Week 8](../../block-2/week-8/instructor-guide.md) | **Week 1** | [Week 2 Instructor Guide](../week-2/instructor-guide.md)

**Related Materials:**
- [Week 1 Presentation Slides](presentation.md)
- [Week 1 Participant Guide](participant-guide.md)
- [Block 3 Main Document](../block-3.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 1 materials and Block 3 overview | |
| Review pre-work | Ensure Agent Memory Meta-Framework presentation is accessible | |
| Prepare examples | Have RFP Response Agent example ready to explain | |
| Check prerequisites | Verify participants completed Block 2 capstone | |
| Review Block 2 | Check Block 2 Week 8 feedback and questions | |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | |
| Load presentation | Have slides ready and tested | |
| Review timing | Practice transitions and key points | |
| Prepare materials | Have agent design template ready to show | |
| Check participant progress | Review who completed Block 2 capstone | |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, agent design template, MCP documentation | |
| Test share | Verify screen sharing works | |
| Welcome early arrivals | Brief chat, gauge excitement for Block 3 | |
| Start recording | If session is recorded | |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome to Block 3, preview | Build excitement |
| 0:03 | 10 min | Segment 1 | Block 3 Overview + Agent Mindset | Connect to pre-work |
| 0:13 | 12 min | Segment 2 | Agents vs. Workflows Distinction | Critical foundation |
| 0:25 | 15 min | Segment 3 | Two-Agent Architecture Pattern | Core concept |
| 0:40 | 5 min | Segment 4 | Planning Capstone Agent | Live brainstorm |
| 0:45 | - | Closing | Homework preview | Don't skip |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Shorten the RFP Response Agent example (keep high-level)
- Reference detailed diagrams in participant guide rather than explaining fully
- Move capstone brainstorm to homework

**If Running Ahead:**
- Deeper discussion on when agents vs. workflows
- More examples of Two-Agent Pattern in different domains
- Extended Q&A on pre-work concepts

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:13 | Compress maturity progression explanation |
| End Segment 2 | 0:25 | Skip detailed agent loop diagram |
| Start Closing | 0:42 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants warmly to Block 3
2. Acknowledge the milestone - they've completed Blocks 1 and 2
3. Set context for automation architecture
4. Preview today's session

**Opening Script:**
> "Welcome to Block 3: AI Automation Architecture! This is a major milestone - you've completed AI Prompting Mastery and AI Workflow Engineering. Now we're taking everything to the next level. Today we're focusing on Agent Fundamentals - the critical concepts that separate workflows that execute steps from agents that make decisions. By the end of our 45 minutes together, you'll understand the key distinction and have started planning your capstone agent."

**Engagement Opportunity:**
> "Quick check-in: Who reviewed the Agent Memory Meta-Framework presentation as pre-work? What concept stood out most to you?"

[Wait for 1-2 responses - this should take 30 seconds max]

---

### Segment 1: Welcome to Block 3 + The Agent Mindset (10 minutes)

**Learning Objective:** Understand the maturity progression and connect pre-work to Block 3 goals

**Slides:** 3-6

#### Content Delivery

**Key Point 1: Maturity Progression Completion**
- Main message: You've climbed the ladder - Level 1 (templated workflows), Level 2 (workflow engineering), now Level 3 (automation architecture)
- Example to use: "Think of it like learning to cook - first you follow recipes exactly, then you learn to adapt them, now you're designing your own restaurant kitchen"
- Common misconception: That Level 3 replaces Levels 1-2 (they build on each other)

**Key Point 2: The Key Shift**
- Main message: From workflows that execute steps to agents that make decisions
- Demonstration: Show simple workflow vs. agent decision tree
- Participant relevance: "This is how you'll handle the variable, judgment-requiring tasks in your work"

**Key Point 3: Connection to Pre-Work**
- Main message: The presentation explained WHY agents fail; Block 3 teaches HOW to build agents that succeed
- Practice preview: The Three Pillars (Goals, Progress, Procedures) become your design framework

#### Facilitation Notes

**Watch For:**
- Participants who didn't complete pre-work (they may look confused at references)
- Over-excitement leading to scope creep thinking

**If Asked About the Capstone:**
> "The capstone is an end-to-end autonomous agent demonstration. We'll plan it throughout the block. Don't worry about the details yet - focus on today's fundamentals."

**Transition to Segment 2:**
> "Now let's get concrete about the critical distinction between agents and workflows - this is foundational for everything that follows."

---

### Segment 2: Agents vs. Workflows - The Critical Distinction (12 minutes)

**Learning Objective:** Clearly distinguish when to use agents vs. workflows

**Slides:** 7-11

#### Content Delivery

**Key Point 1: Workflow Characteristics**
- Main message: Predetermined paths, human-designed logic, fails on unexpected input
- Visual to emphasize: Flowchart with fixed paths
- Example: "Your Block 2 workflows - powerful but predictable"

**Key Point 2: Agent Characteristics**
- Main message: Dynamic decision-making, AI determines next steps, adapts to context, uses tools
- Visual: The agent loop diagram (Observe -> Think -> Act -> Observe...)
- Real-world application: "When the RFP has unusual requirements, the agent adapts rather than failing"

**Key Point 3: When to Use Each**
- Main message: Workflow for predictable/repeatable; Agent for variable inputs and judgment required
- Framework: "If you can draw every possible path, use a workflow. If you can't, consider an agent."

#### Interactive Element

**Activity Type:** Quick poll

**Activity Duration:** 2 minutes

**Instructions:**
1. "I'm going to describe three scenarios. For each, call out 'Workflow' or 'Agent'"
2. Scenario 1: "Processing expense reports with standard categories" (Workflow)
3. Scenario 2: "Researching competitors with varying data availability" (Agent)
4. Scenario 3: "Generating weekly status emails from template" (Workflow)

**Debrief Points:**
> "Notice the pattern - when the path is predictable, workflow. When judgment and adaptation are needed, agent. But here's the key insight: agents are expensive. Use them only when the variability justifies the complexity."

#### Facilitation Notes

**Energy Check:**
At this point in the session, participants may be:
- Eager to jump to building (hold them back - design first)
- Confused about boundary cases (that's okay - we'll clarify)

**Transition to Segment 3:**
> "Now for the most important concept of today - the Two-Agent Architecture Pattern. This is what makes agents reliable instead of chaotic."

---

### Segment 3: The Two-Agent Architecture Pattern (15 minutes)

**Learning Objective:** Understand and apply the Two-Agent Pattern for reliable agent systems

**Slides:** 12-18

#### Content Delivery

**Key Point 1: The Fundamental Insight**
- Main message: Stop trying to give agents memory. Build systems where amnesiacs can work effectively.
- Framework: The Daily Contractor Analogy
- Why single agents fail: No memory between sessions, different interpretations of "done", context pollution

**Key Point 2: The Two-Agent Pattern**
- Main message: Setup Agent (runs once) + Worker Agent (runs repeatedly, stateless)
- Structure to present:
  - Setup Agent: Takes request, creates structured records, defines goals/procedures, then STOPS
  - Worker Agent: Reads state, picks ONE task, does work, updates records, STOPS
- Key insight: "The PROJECT has memory, not the agent"

**Key Point 3: Core Agent Components**
- Main message: Every agent has Goal, Context/Memory, Tools, Reasoning, Output
- Example walkthrough: RFP Response Agent with each component identified

#### Demo: RFP Response Agent Example

**Demo Duration:** 5 minutes

**Setup Required:**
- RFP Response Agent diagram ready
- response_plan.json example ready to show

**Demo Steps:**
1. Show the problem: "RFP with 47 requirements, 20-40 hours manual, variable quality"
2. Walk through Setup Agent: "Parses requirements, creates response_plan.json, then STOPS"
3. Walk through Worker Agent: "Reads plan, finds pending section, generates draft, updates plan, STOPS"
4. Show response_plan.json structure
5. Highlight: "Each worker is stateless but the PROJECT has memory"

**Demo Talking Points:**
> "Notice the Setup Agent runs ONCE. It doesn't try to do everything - it creates the structure."
> "The Worker Agent doesn't need to remember anything. It reads the current state, does one thing, updates state, stops."

**Backup Plan:**
If demo fails:
1. Switch to pre-prepared diagrams
2. Walk through conceptually using whiteboard
3. Offer to demonstrate in office hours

#### Facilitation Notes

**Common Confusion Point:**
"Why not just use one agent that remembers everything?"

**Clarification Approach:**
> "The key insight is that LLMs are unreliable amnesiacs. Fighting their nature fails. Instead, we design systems where amnesia doesn't matter - the memory is in the structured records, not the agent."

---

### Segment 4: Planning Your Capstone Agent (5 minutes)

**Learning Objective:** Begin planning a capstone agent with clear criteria

**Slides:** 19-21

#### Content Delivery

**Key Point 1: Agent Selection Criteria**
- Main message: Complex enough to benefit, clear success criteria, measurable value, builds on Block 2
- Framework: What goal? What tools? What decisions? How will you know it succeeded? What could go wrong?

**Key Point 2: Planning Framework Preview**
- Main message: Exercise 1.2 will guide you through comprehensive agent design
- Connection to Homework: "Your agent design document becomes the Setup Agent output"

#### Practical Application

**Live Exercise:**
> "Take 60 seconds right now. Think about your Block 2 workflows. Which one has the most variable inputs? Which requires the most human judgment? That's your agent candidate. Drop your initial idea in the chat."

[Wait 60 seconds, acknowledge 2-3 responses]

---

### Closing (3 minutes)

**Slides:** 22-24

**Do Not Skip This Section** - even if running behind

#### Homework Preview

**Key Actions:**
1. Overview all three exercises briefly
2. Highlight which exercise practices which concept
3. Note estimated times
4. Point to resources and where to get help

**Script:**
> "Your homework includes three exercises totaling about 75 minutes.
>
> Exercise 1.1 is Agent vs. Workflow Analysis - takes about 20 minutes. You'll review your Block 2 workflows and identify the best agent candidate.
>
> Exercise 1.2 is the Agent Design Document - about 35 minutes. This is where you create the comprehensive plan for your capstone agent. This becomes your 'Setup Agent output.'
>
> Exercise 1.3 is Agent Skeleton Setup - 20 minutes. You'll create the folder structure and initial system prompt.
>
> Everything you need is in your participant guide, including templates and the design document structure."

#### Resources and Support

> "If you get stuck, post in the support channel. Also check the Anthropic Agent Documentation and MCP Server Registry - links in your participant guide."

#### Next Week Preview

> "Next week we cover Building Reliable Agents - the Domain Memory pillars, the execution loop, and error handling. Complete your exercises before then because we'll be building on your agent design."

#### Session Close

> "Questions before we wrap? ... Welcome to Block 3! This is where AI gets truly powerful. See you next week!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: What's the difference between an agent and just a complex prompt?**
A: A prompt produces one output. An agent iterates - it observes, thinks, acts, and loops until the goal is achieved. It's the loop and tool usage that makes it an agent.

**Q: Do I need to use the Two-Agent Pattern for my capstone?**
A: Not necessarily for simple agents, but for anything multi-step or requiring persistence, yes. It's the pattern that enables reliability.

**Q: How do I know if my task is complex enough for an agent?**
A: Ask: Does it require multiple tools? Does it need to make decisions based on intermediate results? Could a workflow handle all the variations? If yes to first two and no to last, consider an agent.

### Technical Questions

**Q: What MCP servers will I need?**
A: Depends on your agent's purpose. Common ones: filesystem, GitHub. We'll cover MCP in depth in Week 3.

**Q: Can I use Make/n8n for my agent?**
A: Yes, as the orchestration layer that calls the agent. The agent itself runs via Claude API with MCP tools.

### Scope Questions

**Q: How complex should my capstone agent be?**
A: "Complex enough to demonstrate the patterns we're learning, simple enough to complete in 8 weeks. Think one significant task, not a whole system. We'll refine scope throughout the block."

**Q: What if I want to do something different from my Block 2 workflows?**
A: You can, but building on Block 2 gives you a head start. New domains mean more setup time. Consider what maximizes your learning vs. scope risk.

### Pushback/Objections

**Q: This seems more complicated than just using a good prompt. Why bother?**
A: "For simple tasks, you're right - use a prompt. But when you need to handle variable inputs, use multiple tools, and recover from failures, the agent architecture pays off. It's about matching tool to task."

**Q: Won't this be expensive with all the API calls?**
A: "Yes, agents cost more than single prompts. That's why we only use them when the value justifies it. Week 6 covers cost optimization."

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Screen share fails | Restart share, switch to application share | Have participant share their screen |
| Diagrams not showing | Switch to whiteboard explanation | Reference participant guide |
| Audio issues | Ask participants to type questions | Continue with video only |
| Slides won't advance | Use keyboard shortcuts | Open backup copy |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Confusion about agents vs. workflows | "I don't see the difference" | Use more concrete examples from their domain |
| Overwhelmed by Two-Agent Pattern | Glazed looks, silence | Break down with simpler analogy |
| Pre-work not completed | Lost at Domain Memory references | Provide quick summary, suggest they review after |
| Over-eager to build | "Can we skip to coding?" | Emphasize design-first, show failed agent examples |
| Scope anxiety | "My capstone seems too big/small" | Reassure - we refine scope throughout block |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Content too easy | "We know this from Block 2" | Emphasize what's NEW - the agent loop, memory patterns |
| Content too hard | Many questions about basics | Slow down, reference Block 2 concepts |
| Off-topic tangent | Discussion drifting to specific tools | "Great topic for office hours, let's stay on patterns today" |
| Time pressure | Running behind | Skip detailed RFP example, reference in guide |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save any chat questions | For follow-up |
| Note what worked/didn't | Quick mental notes |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | |
| Answer pending questions in support channel | |
| Send follow-up message with key reminders | |
| Document issues encountered for curriculum improvement | |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions (spot check agent designs) | |
| Identify participants needing support | |
| Prepare any clarifications for Week 2 | |
| Update this instructor guide with lessons learned | |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 1.1 | `agent-opportunity-analysis.md` | Participant's GitHub repo |
| 1.2 | `agent-design-document.md` | Participant's GitHub repo |
| 1.3 | Agent folder structure + system prompt | `/agents/[name]/` in repo |

### Progress Check Approach

**How to Verify Completion:**
- Check GitHub commits for the three deliverables
- Look for completeness of agent design document sections
- Verify system prompt addresses all required elements

**Intervention Thresholds:**
- 1 exercise incomplete: Monitor, may be time constraints
- 2+ exercises incomplete: Reach out privately
- Agent design document superficial: Schedule 1:1 to deepen before Week 2

---

## Week-Specific Notes

### What Makes This Week Unique

- **First week of Block 3** - Sets the tone for the entire block
- **Major conceptual shift** - From workflows to agents requires new mental model
- **Pre-work dependency** - Content builds on Agent Memory Meta-Framework presentation
- **Capstone planning begins** - Decisions made this week carry through the block

### Dependencies

**Builds On:**
- Block 2: Workflow engineering skills, MCP basics, quality gates
- Pre-work: Agent Memory Meta-Framework concepts

**Sets Up:**
- Week 2: Agent design document becomes basis for implementation
- Weeks 3-7: All build on this week's agent plan
- Week 8: Capstone submission based on design started here

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Pre-work not completed by all | Provide 5-min summary at start | Active |
| Scope anxiety for capstone | Emphasize iterative refinement | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- "What distinguishes an agent from a workflow?" (expect: decision-making, tool use, iteration)
- "Why do we use two agents instead of one?" (expect: memory/state management, reliability)
- Observable behavior indicating understanding: Asking good questions about their specific agent idea
- Observable behavior indicating confusion: Generic questions, silence at Two-Agent Pattern

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 1.1: Look for thoughtful analysis of agent potential, not just listing workflows
- Exercise 1.2: Look for complete sections, realistic success criteria, identified risks
- Exercise 1.3: Look for well-structured system prompt with clear role, goals, constraints

**Common Issues to Flag:**
- Overly ambitious scope (agent tries to do too much)
- Missing failure criteria (only thinks about success)
- Vague success criteria ("make it work" vs. measurable)

### Connecting to Capstone

**Capstone Relevance:**
This week's work contributes to the capstone by:
- Exercise 1.2 becomes the foundation of the capstone agent design
- Early scope decisions determine capstone complexity
- System prompt from 1.3 evolves throughout the block

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Quick pulse check: "On a scale of 1-5, how clear is the agent vs. workflow distinction?"
- Open question: "What's still fuzzy?"

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

1. "Agents decide, workflows execute - know when each is appropriate"
2. "The project has memory, not the agent - that's the key insight"
3. "Design before building - your agent design document is your foundation"

### If You Only Have Time For One Thing

The Two-Agent Pattern: Setup Agent creates structure once, Worker Agent executes stateless steps repeatedly. The memory is in the records, not the agent.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Two-Agent Pattern | Daily contractor who reads the job board each morning | Explaining stateless workers |
| Agent vs. Workflow | Recipes vs. cooking show improvisation | When distinction is unclear |
| Domain Memory | Project documentation that any new team member can read | Explaining persistent state |
