# **POWERPOINT PRESENTATION: BLOCK 3 WEEK 1**
## **Agent Fundamentals**

**Block:** 3: AI Automation Architecture
**Week Number:** 1
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 2 graduates with functional workflows who want to build autonomous AI agents

**Key Thesis:** Autonomous agents require architectural separation between planning and execution, with memory residing in external structured state rather than the agent itself.

**Week Learning Objectives:** By the end of this session, participants will:
1. Distinguish between agents and workflows and know when to use each
2. Apply the Two-Agent Architecture Pattern to design reliable agent systems
3. Identify the five core components of any agent
4. Begin planning their capstone agent with clear criteria

**Entry Criteria:** (What participants should have before this session)
- [ ] Block 2 Capstone completed and approved
- [ ] 3 working workflows from Block 2
- [ ] MCP configuration functional
- [ ] Pre-work: Reviewed Agent Memory Meta-Framework Presentation (slides 1-30)

**Exit Criteria:** (What participants should be able to do after this session)
- [ ] Explain the difference between agents and workflows
- [ ] Describe the Two-Agent Architecture Pattern
- [ ] List the five core components of an agent
- [ ] Identify a candidate workflow for agent conversion

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Block 3 Overview + Agent Mindset (10 min) - Slides 4-7
3. Segment 2: Agents vs. Workflows (12 min) - Slides 8-12
4. Segment 3: Two-Agent Architecture Pattern (15 min) - Slides 13-19
5. Segment 4: Planning Your Capstone (5 min) - Slides 20-21
6. Homework Preview & Close (3 min) - Slides 22-24

**Total Slides:** 24

---

## SLIDE 1: TITLE SLIDE

**Title:** Block 3 Week 1: Agent Fundamentals

**Subtitle:** From Workflows to Agents - The Automation Architecture Journey

**Content:**
- AI Practitioner Training Program
- Block 3: AI Automation Architecture

**Graphic:** Clean title slide with green theme (Block 3 color). Include program branding and visual of agent concept.

**GRAPHICS:**

**Graphic 1: Agent Concept Visualization**
- Purpose: Establish visual identity for Block 3 and introduce the concept of autonomous agents
- Type: Abstract conceptual illustration
- Elements: Circular agent icon with interconnected nodes representing observe-think-act loops; subtle background pattern suggesting automation/architecture
- Labels: "Block 3: AI Automation Architecture" with green accent (#00CC99)
- Relationships: Agent icon positioned as centerpiece with subtle connections radiating outward suggesting autonomous decision-making

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Block 3: AI Automation Architecture! This is a major milestone. You've completed AI Prompting Mastery and AI Workflow Engineering. Now we're entering the final frontier - building autonomous AI agents.

Today we're focusing on Agent Fundamentals - the critical concepts that will guide everything you build in this block.

Quick check-in: Who reviewed the Agent Memory Meta-Framework presentation as pre-work? What concept stood out most to you?

[Wait for 1-2 responses]

Great. Let's build on those concepts today."

[Transition: Click to next slide]

---

## SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Welcome to Block 3 |
| 3-13 min | Segment 1 | Block 3 Overview + Agent Mindset |
| 13-25 min | Segment 2 | Agents vs. Workflows |
| 25-40 min | Segment 3 | Two-Agent Architecture Pattern |
| 40-45 min | Segment 4 | Planning Your Capstone |

**Graphic:** Timeline showing session flow with green accent colors

**SPEAKER NOTES:**

"Here's what we'll cover today:

First, we'll set the context for Block 3 - where you are in the maturity progression and what makes agent architecture different.

Then, the critical distinction between agents and workflows. This is foundational - knowing when to use each.

Our main topic is the Two-Agent Architecture Pattern - this is what makes agents reliable instead of chaotic.

We'll close by starting to plan your capstone agent.

[Pause]

Any questions before we dive in?"

[Transition]

---

## SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Distinguish between agents and workflows**
   - Know when each is appropriate for your tasks

2. **Apply the Two-Agent Architecture Pattern**
   - Design systems where "amnesiacs" can work effectively

3. **Identify the five core components of any agent**
   - Goal, Context, Tools, Reasoning, Output

4. **Begin planning your capstone agent**
   - Select a candidate and define initial scope

**Graphic:** Checklist visual with green checkboxes

**SPEAKER NOTES:**

"These are our four objectives for today. By the time you leave this session, you'll be able to:

[Read each objective, pausing briefly after each]

Notice these are all ACTION-focused. This isn't just theory - you'll apply each of these in your homework exercises.

[Point to first objective]

This first one connects directly to your Block 2 work. You'll analyze your existing workflows to find agent candidates.

Let's get started."

[Transition: Click to Segment 1]

---

## SEGMENT 1: BLOCK 3 OVERVIEW + AGENT MINDSET
### Duration: 10 minutes | Slides 4-7

---

## SLIDE 4: THE MATURITY PROGRESSION

**Title:** Your AI Practitioner Journey

**Content:**

```
Level 1: AI Prompting Mastery (Block 1) ✓
         → Templated workflows, consistent prompts

Level 2: AI Workflow Engineering (Block 2) ✓
         → Complex workflows, quality gates, MCP integration

Level 3: AI Automation Architecture (Block 3) ← YOU ARE HERE
         → Autonomous agents, dynamic decisions, production systems
```

**Graphic:** Ascending staircase or pyramid showing three levels, with Level 3 highlighted in green

**GRAPHICS:**

**Graphic 1: Three-Level Maturity Progression**
- Purpose: Show the learning journey from Block 1 through Block 3 and current position
- Type: Ascending staircase diagram or stepped pyramid
- Elements: Three distinct levels/steps, each progressively higher; checkmarks on Levels 1 and 2; "YOU ARE HERE" indicator on Level 3 with green highlight
- Labels:
  - Level 1: "AI Prompting Mastery" with "Templated workflows" subtitle
  - Level 2: "AI Workflow Engineering" with "Quality gates, MCP" subtitle
  - Level 3: "AI Automation Architecture" (highlighted in green #00CC99) with "Autonomous agents" subtitle
- Relationships: Each level builds upon the previous (visual foundation/support relationship); arrow or pathway showing progression upward

**SPEAKER NOTES:**

"[Hook - Create context]"

"Look at where you are. Level 1 - you learned to write effective prompts and create templated workflows. Level 2 - you engineered complex workflows with quality gates and MCP integration.

Now Level 3 - automation architecture. This is where AI becomes truly autonomous.

[Point to graphic]

Each level builds on the previous. Everything you learned still applies. But now we're adding a crucial capability: agents that make decisions, not just execute steps."

[Transition]

**BACKGROUND:**

**Rationale:**
- Establishes Block 3 context by anchoring it within the complete learning progression
- Creates motivation through achievement recognition (checkmarks on completed blocks)
- Positions agents as natural evolution, not disconnected new topic
- The "YOU ARE HERE" marker creates present-moment engagement and readiness

**Key Research & Citations:**
- **Bloom's Taxonomy Progression**: Learning objectives should scaffold from knowledge (Block 1) through application (Block 2) to synthesis and creation (Block 3) - this slide visually demonstrates that progression
- **AI Maturity Models**: Industry frameworks (Gartner, McKinsey) show organizations progress from ad-hoc AI use through systematized workflows to autonomous operations - mirrors individual skill development
- **Adult Learning Theory (Knowles)**: Adults learn best when they understand the context and can see how new learning builds on existing knowledge

**Q&A Preparation:**
- *"Can I skip ahead if I already know some of this?"*: Each block builds essential foundations - Block 3 assumes you've internalized Block 2 patterns like MCP and quality gates. Skipping creates gaps that show up in agent reliability.
- *"How is Level 3 different from just making my workflows more complex?"*: Workflows execute predetermined logic you design. Agents make dynamic decisions - fundamentally different capability requiring different architecture patterns.
- *"What comes after Level 3?"*: Advanced modules cover specialized topics (RAG, fine-tuning, domain-specific agents), but Level 3 gives you the architecture foundation to explore any direction.

**Sources:**
- [Bloom's Taxonomy](https://cft.vanderbilt.edu/guides-sub-pages/blooms-taxonomy/) - Cognitive skill progression
- [Gartner AI Maturity Model](https://www.gartner.com/en/newsroom/press-releases/2021-11-22-gartner-identifies-four-key-factors-to-successfully-adopt-ai) - Organizational AI evolution
- [Adult Learning Theory](https://educationaltechnology.net/knowles-theory-of-andragogy/) - Context-based learning principles

---

## SLIDE 5: THE KEY SHIFT

**Title:** The Key Shift in Block 3

**Content:**

**From:** Workflows that execute steps
**To:** Agents that make decisions

| Workflows | Agents |
|-----------|--------|
| You design the logic | AI determines next steps |
| Predetermined paths | Dynamic decisions |
| Fails on unexpected | Adapts to context |
| Executes what you specify | Achieves goals you define |

**Graphic:** Visual showing a linear workflow transforming into an adaptive decision tree

**GRAPHICS:**

**Graphic 1: Workflow to Agent Transformation**
- Purpose: Illustrate the fundamental difference between rigid workflow execution and adaptive agent decision-making
- Type: Before/after transformation diagram
- Elements:
  - Left side: Linear flowchart with fixed sequential steps (boxes connected by straight arrows)
  - Center: Transformation arrow or divider
  - Right side: Dynamic decision tree with multiple branches, decision nodes, and adaptive pathways
- Labels:
  - Left: "WORKFLOW - Executes Steps" with "Predetermined, rigid" annotation
  - Right: "AGENT - Makes Decisions" with "Dynamic, adaptive" annotation
  - Decision nodes on right marked with "AI decides" indicators
- Relationships: Show contrast between fixed path (left) vs. multiple possible paths based on context (right)

**SPEAKER NOTES:**

"This is the fundamental shift.

[Point to Workflows column]

Workflows execute what you specify. You design every path, every decision point, every outcome. They're powerful but rigid.

[Point to Agents column]

Agents achieve goals you define. They decide HOW to get there. They adapt when things don't go as expected.

Think of it like giving directions. A workflow is turn-by-turn navigation - 'turn left, go 100 meters, turn right.' An agent is 'get to the restaurant' - it figures out the path.

[Pause]

But here's the catch: agents are expensive and complex. That's why Block 3 exists - to teach you WHEN agents make sense and HOW to build them reliably."

[Transition]

---

## SLIDE 6: CONNECTION TO PRE-WORK

**Title:** Building on the Foundation

**Content:**

**The presentation introduced:**
- WHY agents fail (memory, reliability, complexity)
- The Three Pillars of Domain Memory
- The Daily Contractor Analogy

**Block 3 teaches:**
- HOW to build agents that succeed
- The Three Pillars become your design framework
- The analogy guides your architecture

**Graphic:** Bridge visual connecting "Why Agents Fail" to "How Agents Succeed"

**GRAPHICS:**

**Graphic 1: Pre-Work to Block 3 Connection Bridge**
- Purpose: Show the progression from understanding problems (pre-work) to implementing solutions (Block 3)
- Type: Bridge/connection diagram
- Elements:
  - Left side: "Pre-Work Concepts" platform with key concepts listed
  - Right side: "Block 3 Skills" platform with implementation skills listed
  - Bridge connecting the two platforms
- Labels:
  - Left platform: "WHY Agents Fail" with bullets "Memory problems, Unreliable amnesiacs, Three Pillars theory, Daily Contractor concept"
  - Right platform: "HOW to Build Reliable Agents" with bullets "Architecture patterns, Domain Memory implementation, Production systems"
  - Bridge: "Block 3 = Theory → Practice"
- Relationships: Arrow flow from left to right showing progression; bridge as transformation mechanism

**SPEAKER NOTES:**

"Your pre-work laid the groundwork.

The Agent Memory Meta-Framework presentation explained WHY most agents fail. Remember the key insight? Agents are 'unreliable amnesiacs.' They have no memory between sessions. They interpret 'done' differently each time.

[Pause]

Block 3 is the solution. We'll take those concepts - the Three Pillars of Domain Memory, the Daily Contractor Analogy - and turn them into practical architectures you can build.

If you haven't reviewed the pre-work, I strongly recommend doing so before next week. Everything we build assumes that foundation."

[Transition]

---

## SLIDE 7: CAPSTONE PREVIEW

**Title:** Your Block 3 Capstone

**Content:**

**Automated Workflow Solution**
- End-to-end autonomous agent demonstration
- Production deployment documentation
- Team rollout plan
- ROI calculation with actual measured data

**What you'll build over 8 weeks:**
Weeks 1-4: Agent fundamentals and construction
Weeks 5-6: Orchestration and optimization
Week 7: Documentation and planning
Week 8: Final submission

**Graphic:** Roadmap showing the 8-week journey with milestones

**GRAPHICS:**

**Graphic 1: Block 3 Eight-Week Roadmap**
- Purpose: Provide clear visual timeline of capstone development progression
- Type: Horizontal timeline/roadmap
- Elements: Eight week markers with milestone indicators; three phase groupings
- Labels:
  - Phase 1 (Weeks 1-4): "AGENT FUNDAMENTALS & CONSTRUCTION" with milestones:
    - Week 1: "Design & Planning"
    - Week 2: "Build Reliable Agent"
    - Week 3: "MCP Integration"
    - Week 4: "Testing & Refinement"
  - Phase 2 (Weeks 5-6): "ORCHESTRATION & OPTIMIZATION" with milestones:
    - Week 5: "Multi-Agent Orchestration"
    - Week 6: "Performance Optimization"
  - Phase 3 (Weeks 7-8): "DEPLOYMENT & SUBMISSION" with milestones:
    - Week 7: "Documentation & Rollout Plan"
    - Week 8: "Final Submission & Presentation"
- Relationships: Progressive flow left to right; phase groupings with distinct visual separation; "YOU ARE HERE" indicator at Week 1

**SPEAKER NOTES:**

"Here's where we're headed.

Your Block 3 capstone is an Automated Workflow Solution - a real, working agent system that solves a meaningful problem.

[Point to requirements]

It's not just code. You'll document it for production, plan how to roll it out to a team, and calculate actual ROI from your data.

[Point to timeline]

Weeks 1-4 are construction - building the agent. Weeks 5-6 add sophistication - orchestration and optimization. Week 7 is documentation. Week 8 is submission.

Today we start planning. By the end of this session, you'll know which workflow you're converting and have started your design document."

[Transition: Click to Segment 2]

---

## SEGMENT 2: AGENTS VS. WORKFLOWS
### Duration: 12 minutes | Slides 8-12

---

## SLIDE 8: THE CRITICAL DISTINCTION

**Title:** When to Use What?

**Content:**

**The Question:**
"Should this be a workflow or an agent?"

**The Answer Depends On:**
- How predictable is the path?
- How much judgment is required?
- What happens with unexpected input?

**Graphic:** Fork in the road visual with "Workflow" and "Agent" paths

**SPEAKER NOTES:**

"[Hook - Create tension]"

"You're going to face this question constantly: Should this be a workflow or an agent?

Get it wrong, and you either:
- Build a rigid workflow that breaks on real-world variation, OR
- Build an expensive agent for something a simple workflow could handle

[Pause]

The answer isn't about what's cooler or more advanced. It's about matching the tool to the task.

Let's break down how to decide."

[Transition]

---

## SLIDE 9: WORKFLOW CHARACTERISTICS

**Title:** Workflows: Powerful But Predictable

**Content:**

**Characteristics:**
- Predetermined paths
- Human designs the logic
- Executes what you specify
- Fails when unexpected input arrives

**Best For:**
- Predictable, repeatable processes
- Fixed decision trees
- Consistent input formats
- High-volume, low-variation tasks

**Graphic:** Flowchart with fixed paths, all branches clearly defined

**GRAPHICS:**

**Graphic 1: Workflow Fixed-Path Flowchart**
- Purpose: Demonstrate the predictable, predetermined nature of workflow automation
- Type: Traditional flowchart diagram
- Elements: Start node, decision diamonds, process rectangles, end node; all paths clearly mapped
- Labels:
  - Example flow: "Receive input" → "Check format" (diamond) → "Process Type A" / "Process Type B" → "Output result"
  - All decision paths explicitly defined
  - "ALL PATHS PRE-DEFINED" annotation
- Relationships: Every branch has a defined outcome; no ambiguity or dynamic decision-making; closed system

**SPEAKER NOTES:**

"Workflows are what you built in Block 2. Let's be clear about their strengths.

[Point to characteristics]

You design every path. That means you KNOW what will happen. Predictability is valuable - you can test every branch, guarantee outcomes.

[Point to Best For]

Expense report processing. Email routing. Report generation from templates. These are workflow territory.

[Pause]

The weakness? When input varies beyond what you designed for, workflows fail. They don't adapt - they break."

[Transition]

---

## SLIDE 10: AGENT CHARACTERISTICS

**Title:** Agents: Adaptive But Complex

**Content:**

**Characteristics:**
- Dynamic decision-making
- AI determines next steps
- Adapts to context
- Handles unexpected situations
- Uses tools and takes actions

**The Agent Loop:**
```
Observe → Think → Act → Observe → Think → Act → ...
```

**Best For:**
- Variable inputs requiring judgment
- Tool selection based on situation
- Multi-step tasks with dependencies
- Situations where all paths can't be pre-defined

**Graphic:** Circular loop diagram showing Observe-Think-Act cycle

**GRAPHICS:**

**Graphic 1: Agent Execution Loop**
- Purpose: Illustrate the continuous, iterative decision-making process that defines agent behavior
- Type: Circular process flow diagram
- Elements: Three connected nodes forming a continuous cycle with directional arrows; cycle repeats until goal achieved
- Labels:
  - "OBSERVE" node: "Take in information, read state"
  - "THINK" node: "Decide next action, evaluate options"
  - "ACT" node: "Use tool, update state, produce output"
  - "REPEAT" arrow cycling back to Observe
  - "Until goal achieved or escalation needed" condition
- Relationships: Continuous circular flow; arrows showing direction; emphasis on repetition; exit condition noted outside loop

**SPEAKER NOTES:**

"Agents operate differently.

[Point to loop]

This is the agent loop. Observe - take in information. Think - decide what to do. Act - use a tool or produce output. Then loop.

The agent keeps going until the goal is achieved or it determines it can't proceed.

[Point to Best For]

Research tasks where sources vary. Content generation requiring analysis. Troubleshooting problems. These benefit from agents.

[Pause]

But agents cost more - more tokens, more complexity, more things that can go wrong. That's why the next slide matters."

[Transition]

---

## SLIDE 11: DECISION FRAMEWORK

**Title:** Workflow or Agent? A Decision Guide

**Content:**

| Question | If Yes → Workflow | If Yes → Agent |
|----------|-------------------|----------------|
| Can you draw every path? | ✓ | |
| Is input format consistent? | ✓ | |
| Does it require judgment? | | ✓ |
| Must it select between tools? | | ✓ |
| Do inputs vary significantly? | | ✓ |
| Is the process well-defined? | ✓ | |

**Rule of Thumb:**
> "If you can draw every possible path, use a workflow. If you can't, consider an agent."

**Graphic:** Decision matrix with green (agent) and blue (workflow) coding

**GRAPHICS:**

**Graphic 1: Workflow vs Agent Decision Matrix**
- Purpose: Provide quick reference framework for choosing between workflows and agents
- Type: Decision matrix/table with color coding
- Elements: Two-column comparison table with checkmarks; color-coded recommendations
- Labels:
  - Column headers: "Workflow" (blue #4A90E2) | "Agent" (green #00CC99)
  - Rows with decision criteria and checkmarks indicating which approach fits
  - Bottom: "Rule of Thumb" callout box
- Relationships:
  - Mutually exclusive checkmarks per row (either workflow OR agent)
  - Visual clustering of similar criteria
  - Rule of thumb as summary decision aid
- Color coding: Blue checkmarks for workflow criteria, green checkmarks for agent criteria

**SPEAKER NOTES:**

"Use this framework when deciding.

[Walk through table]

Can you draw every path? That's the key question. If yes, workflow. If there are too many variations to enumerate, agent.

[Point to Rule of Thumb]

Here's the simple version. Every possible path = workflow. Too many paths to draw = agent.

[Pause]

Now let's test your understanding."

[Transition]

---

## SLIDE 12: QUICK EXERCISE

**Title:** Test Yourself

**Content:**

**Scenario 1:** Processing expense reports with standard categories
→ [Workflow / Agent]

**Scenario 2:** Researching competitors with varying data availability
→ [Workflow / Agent]

**Scenario 3:** Generating weekly status emails from template
→ [Workflow / Agent]

**Scenario 4:** Responding to customer inquiries with different intents
→ [Workflow / Agent]

**Graphic:** Quiz-style layout with answer spaces

**SPEAKER NOTES:**

"Quick exercise. I'll read each scenario, call out your answer.

[Read Scenario 1]

Expense reports with standard categories. Workflow or Agent?

[Wait for responses]

Workflow. Fixed categories, predictable processing.

[Read Scenario 2]

Competitor research with varying data availability.

[Wait]

Agent. Data sources vary, requires judgment on what's relevant.

[Read Scenario 3]

Weekly status emails from template.

[Wait]

Workflow. Template-based, predictable format.

[Read Scenario 4]

Customer inquiries with different intents.

[Wait]

This one's interesting - could be either. Simple FAQ? Workflow. Complex, varied inquiries needing context? Agent.

The boundary isn't always clear. When in doubt, start simpler."

[Transition: Click to Segment 3]

---

## SEGMENT 3: TWO-AGENT ARCHITECTURE PATTERN
### Duration: 15 minutes | Slides 13-19

---

## SLIDE 13: THE FUNDAMENTAL INSIGHT

**Title:** Why Single Agents Fail

**Content:**

**The Problem with Single Agents:**
- No memory between sessions
- Different interpretations of "done"
- Repeated failed attempts (Groundhog Day)
- Context window pollution

**The Fundamental Insight:**
> "Stop trying to give agents memory. Build systems where amnesiacs can work effectively."

**Graphic:** Illustration of an agent losing memory between sessions (thought bubbles disappearing)

**GRAPHICS:**

**Graphic 1: Agent Memory Loss Between Sessions**
- Purpose: Visualize the critical problem of agent amnesia between execution sessions
- Type: Sequential time-based illustration
- Elements:
  - Three time periods shown horizontally: Session 1, Session 2, Session 3
  - Agent icon (consistent across sessions)
  - Thought bubbles above agent containing information/context
  - Bubbles progressively fade/disappear between sessions
- Labels:
  - "Session 1": Full thought bubble with "Task A complete, working on B, tried approach X"
  - "Session 2": Empty thought bubble with "?" - agent has no memory of Session 1
  - "Session 3": Empty thought bubble with "?" - repeating same failures
  - "AMNESIA BETWEEN SESSIONS" annotation with warning indicator
- Relationships: Show disconnection between sessions; emphasize that context is lost completely; no persistence

**SPEAKER NOTES:**

"[INSIGHT - The breakthrough]"

"Here's why most agent projects fail.

[Point to problems]

Single agents have no memory between sessions. Each time they start fresh. They interpret 'done' differently. They repeat the same failed approaches. Their context window fills with garbage.

[Pause - let it sink in]

The insight from your pre-work: Stop fighting the amnesia. Design AROUND it.

If you had a team of contractors who forgot everything each day, would you rely on their memory? No. You'd create systems - job boards, progress logs, clear procedures.

That's exactly what we do with agents."

[Transition]

---

## SLIDE 14: THE TWO-AGENT PATTERN

**Title:** The Two-Agent Architecture Pattern

**Content:**

```
SETUP AGENT (runs once)
├─ Takes human request
├─ Creates structured records
├─ Defines goals, procedures, success criteria
└─ Then STOPS

WORKER AGENT (runs repeatedly, stateless)
├─ Reads current state from records
├─ Picks ONE incomplete task
├─ Does work, validates, updates records
└─ STOPS

→ Next worker starts fresh, reads updated state, continues
```

**Graphic:** Two-agent diagram with Setup Agent on left, multiple Worker Agents on right, connected by "Structured Records" in the middle

**GRAPHICS:**

**Graphic 1: Two-Agent Architecture Pattern**
- Purpose: Illustrate the core architectural pattern that solves agent memory problems through external state
- Type: System architecture diagram
- Elements:
  - Left box: Setup Agent (runs once)
  - Center: Structured Records (persistent state file/database)
  - Right: Multiple Worker Agent instances (3-4 shown, each identical)
  - Human icon providing initial request to Setup Agent
  - Bidirectional arrows between Workers and Structured Records
- Labels:
  - Setup Agent: "Runs ONCE" with sub-tasks "Parse request, Create structure, Define goals, STOP"
  - Structured Records: "goals.json, progress.json, procedures.md" (persistent external memory)
  - Worker Agent: "Runs REPEATEDLY (stateless)" with sub-tasks "Read state, Pick ONE task, Do work, Update records, STOP"
  - Each worker numbered (Worker 1, Worker 2, Worker 3...) showing sequential execution
- Relationships:
  - Setup Agent writes to Structured Records (one-way arrow)
  - Each Worker reads from and writes to Structured Records (bidirectional arrows)
  - Workers do NOT connect to each other (emphasizing stateless nature)
  - Time arrow showing sequential worker execution

**Graphic 2: Memory Location Emphasis**
- Purpose: Highlight that memory lives in the project, not the agents
- Type: Annotation overlay on architecture
- Elements: Large callout box pointing to Structured Records
- Labels: "MEMORY LIVES HERE" with "Not in agents - in the PROJECT" subtitle
- Relationships: Visual emphasis (highlight, glow, or border) around Structured Records to show it as the critical component

**SPEAKER NOTES:**

"This is the Two-Agent Architecture Pattern.

[Point to Setup Agent]

The Setup Agent runs ONCE. It takes the human request and creates structure - structured records, goals, procedures. Then it STOPS. It doesn't try to do the whole task.

[Point to Worker Agent]

Worker Agents run repeatedly. Each one is stateless - no memory of previous runs. It reads the current state from records, picks ONE incomplete task, does work, updates records, STOPS.

[Point to connection]

The key is 'structured records.' That's where memory lives. Not in the agents - in the PROJECT.

Any worker can pick up where the last one left off because all the state is external."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide introduces the foundational Two-Agent Architecture Pattern that becomes the design template for all Block 3 work
- The pattern solves the core reliability problem identified in pre-work (agent amnesia) through external state management
- Setup-once/Execute-repeatedly pattern aligns with production engineering principles of separation of concerns
- This architecture enables the Domain Memory framework introduced later in the block

**Key Research & Citations:**
- **Anthropic Building Effective Agents (2025)**: Explicitly recommends separating planning agents from execution agents, with structured handoff protocols between them to maintain context across sessions
- **12-Factor Agents - Factor 6 (Launch/Pause/Resume) and Factor 12 (Stateless Reducer)**: Both factors advocate for agents that can restart from externalized state without context loss, mirroring the Setup/Worker pattern
- **Software Engineering Microservices Pattern**: Stateless services with external data stores have proven more reliable and scalable than stateful monoliths - same principle applies to agents

**Q&A Preparation:**
- *"Why not just one smart agent that remembers?"*: LLM conversation memory is unreliable for production work - it's optimized for chat coherence, not workflow state. External structured state is queryable, versionable, and agent-independent.
- *"Isn't this more complex?"*: Initial setup is more work, but it pays dividends in debuggability and reliability. You can inspect state files, replay from checkpoints, and multiple agents can collaborate.
- *"How is this different from just writing to files?"*: It's the discipline and structure that matters - specific schemas for goals, progress, and procedures that agents can reliably parse and act on.

**Sources:**
1. [Anthropic: Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) - Official architectural guidance
2. [12-Factor Agents Methodology](https://github.com/humanlayer/12-factor-agents) - Production agent principles
3. [The Twelve-Factor App](https://12factor.net/) - Original stateless service patterns
4. [Google ADK Multi-Agent Framework](https://google.github.io/adk-docs/) - Tiered memory implementation

---

## SLIDE 15: THE DAILY CONTRACTOR ANALOGY

**Title:** Think: Daily Contractors

**Content:**

**Imagine:** You hire contractors who forget everything each day.

**Bad Approach:**
- Rely on their memory
- Hope they remember what's done
- Repeat the same instructions daily

**Good Approach:**
- Create a detailed job board
- Maintain progress logs
- Write clear procedures
- Any contractor can read the board and continue

**The PROJECT has memory, not the contractors.**

**Graphic:** Construction site with job board, showing different contractors checking the board

**GRAPHICS:**

**Graphic 1: Daily Contractor Analogy**
- Purpose: Make the Two-Agent Pattern concrete through relatable real-world analogy
- Type: Illustrated analogy diagram
- Elements:
  - Construction site scene
  - Large job board/task board on wall (central element)
  - Three different contractor figures at different times checking the board
  - Task cards on board with status indicators
  - Progress log clipboard hanging on board
  - Procedures/standards document posted on board
- Labels:
  - Job Board sections: "TO DO", "IN PROGRESS", "DONE"
  - Sample tasks: "Install windows - Floor 2", "Paint lobby - Pending", "Electrical - Complete"
  - Contractors labeled "Monday Contractor", "Tuesday Contractor", "Wednesday Contractor" (different people, same role)
  - "PROJECT MEMORY" banner above job board
  - "Contractors = Amnesiac" caption with "Board = Persistent State" caption
- Relationships:
  - Each contractor independently checking board (no direct interaction between contractors)
  - Board is single source of truth
  - Any contractor can pick up where others left off by reading board

**SPEAKER NOTES:**

"The Daily Contractor Analogy makes this concrete.

[Present the scenario]

Imagine hiring contractors who forget everything overnight. Sounds terrible, right?

[Point to Bad Approach]

If you rely on their memory, you're doomed. They'll redo work, miss context, give up.

[Point to Good Approach]

Instead, you create systems. A job board showing what's done and what's next. Progress logs tracking attempts. Clear procedures for each task.

Any contractor - any day - can check the board, see the state, and continue.

[Point to key insight]

The PROJECT has memory. Not the contractors. That's how we build reliable agents."

[Transition]

---

## SLIDE 16: CORE AGENT COMPONENTS

**Title:** The Five Core Components

**Content:**

Every agent has:

| Component | Purpose | Example |
|-----------|---------|---------|
| **Goal** | What to achieve | "Generate complete RFP response" |
| **Context** | What it knows | Structured records, progress logs |
| **Tools** | What it can do | File read/write, APIs, MCP servers |
| **Reasoning** | How it decides | Decision criteria, priorities |
| **Output** | What it produces | Documents, updates, notifications |

**Graphic:** Pentagon or star diagram with five components

**GRAPHICS:**

**Graphic 1: Five Core Agent Components**
- Purpose: Show the essential building blocks present in every agent system
- Type: Pentagon diagram with interconnected components
- Elements: Pentagon shape with each point representing one component; agent icon in center
- Labels (at each pentagon point):
  - Top: "GOAL" with "What to achieve" subtitle and example "Generate RFP response"
  - Upper right: "CONTEXT" with "What it knows" subtitle and example "Structured records, progress"
  - Lower right: "TOOLS" with "What it can do" subtitle and example "File ops, APIs, MCP"
  - Lower left: "REASONING" with "How it decides" subtitle and example "Decision criteria, priorities"
  - Upper left: "OUTPUT" with "What it produces" subtitle and example "Documents, updates, logs"
- Relationships: Lines connecting each component to center agent icon; subtle connections between adjacent points showing interdependencies

**SPEAKER NOTES:**

"Every agent - regardless of complexity - has these five components.

[Walk through each]

Goal - clear objective. Not vague 'help the user' but specific 'generate RFP response for all sections.'

Context - information available. In Two-Agent Pattern, this is the structured records.

Tools - actions it can take. MCP servers, file operations, API calls.

Reasoning - decision logic. How it chooses what to do next.

Output - what it produces. Not just final deliverable but also state updates.

Your design document in Exercise 1.2 will define each of these."

[Transition]

---

## SLIDE 17: DOMAIN MEMORY - THREE PILLARS

**Title:** Domain Memory: The Three Pillars

**Content:**

| Pillar | Purpose | Example |
|--------|---------|---------|
| **Explicit Goals** | Testable success criteria | "Run login_test.py, all pass" |
| **Progress Records** | What's been done/tried | "Tuesday: Tried A → timeout" |
| **Operating Procedures** | How to validate, when to escalate | "After 3 failures, escalate" |

**Key Principle:**
> "If you can't test it, it's not a goal - it's a wish."

**Graphic:** Three pillars holding up "Reliable Agents" structure

**GRAPHICS:**

**Graphic 1: Three Pillars of Domain Memory**
- Purpose: Visualize the foundational framework that enables reliable agent operation
- Type: Architectural pillars diagram
- Elements:
  - Three classical columns/pillars on foundation
  - Roof structure labeled "Reliable Agents" supported by pillars
  - Foundation labeled "External Persistent State"
- Labels:
  - Left Pillar: "EXPLICIT GOALS" with "Testable success criteria" subtitle and example "Run login_test.py - all pass"
  - Center Pillar: "PROGRESS RECORDS" with "What's done/tried" subtitle and example "Tuesday: Tried A → timeout"
  - Right Pillar: "OPERATING PROCEDURES" with "How to validate, escalate" subtitle and example "After 3 failures → escalate"
  - Roof beam: "RELIABLE AGENTS"
  - Foundation: "Structured External State (JSON, Markdown, Database)"
- Relationships: Pillars support roof equally; all three required for stability; foundation supports all pillars; each pillar is distinct but complementary

**SPEAKER NOTES:**

"Domain Memory has three pillars. This is from your pre-work, now applied practically.

[Point to Explicit Goals]

Goals must be testable. 'Build login' is a wish. 'Run login_test.py, all assertions pass' is a goal. If you can't test it, it's not a goal.

[Point to Progress Records]

What's been completed, what's been tried, what failed. Prevents Groundhog Day - repeating the same failures.

[Point to Operating Procedures]

How to validate success. When to escalate. Quality standards. The rules workers follow.

Your agent design document will define all three."

[Transition]

---

## SLIDE 18: RFP RESPONSE AGENT EXAMPLE

**Title:** Example: RFP Response Agent

**Content:**

**The Problem:**
- RFP with 47 requirements across 8 sections
- Manual response: 20-40 hours
- Quality varies by author
- Easy to miss requirements

**Setup Agent (runs once):**
- Parse requirements into checklist
- Map to templates
- Create response_plan.json
- STOP

**Worker Agent (runs repeatedly):**
- Read response_plan.json
- Find pending section
- Generate draft
- Self-evaluate
- Update plan
- STOP

**Graphic:** Flow diagram showing Setup Agent creating plan, then multiple Worker Agents processing sections

**GRAPHICS:**

**Graphic 1: RFP Response Agent Workflow**
- Purpose: Demonstrate Two-Agent Pattern with concrete consulting domain example
- Type: Process flow diagram with two phases
- Elements:
  - Phase 1 (left): Setup Agent flow
  - Phase 2 (right): Worker Agent loop
  - Center: response_plan.json file
  - RFP document as input
- Labels:
  - Input: "RFP Document - 47 requirements, 8 sections"
  - Setup Agent box: "Parse requirements → Map to templates → Create response_plan.json → STOP"
  - response_plan.json: Visual representation showing sections with status fields
  - Worker Agent loop (repeated 3 times):
    - "Worker 1: Read plan → Exec Summary → Update plan → STOP"
    - "Worker 2: Read plan → Technical Approach → Update plan → STOP"
    - "Worker 3: Read plan → Pricing → Update plan → STOP"
  - Time arrow showing sequential execution
- Relationships:
  - Setup runs once (emphasized with "1x" badge)
  - Workers run repeatedly (emphasized with "Nx" badge)
  - All workers interact only with response_plan.json (no worker-to-worker connections)
  - Each worker updates status in plan before stopping

**GRAPHIC 2: Section Status Progression**
- Purpose: Show how state changes as workers complete sections
- Type: State transition table
- Elements: response_plan.json shown at three time points
- Labels:
  - "After Setup": All sections status="pending"
  - "After Worker 1": Exec summary status="complete", quality_score=4.2
  - "After Worker 2": Technical approach status="complete", quality_score=4.5
- Relationships: Visual progression showing state evolution; highlight changing status fields

**SPEAKER NOTES:**

"Let's see this pattern in action with a consulting example.

[Present the problem]

RFP arrives with 47 requirements. Manual response takes 20-40 hours. Quality varies. Requirements get missed.

[Point to Setup Agent]

Setup Agent runs once when RFP arrives. Parses all requirements, maps them to templates, creates response_plan.json with the structure. Then STOPS.

[Point to Worker Agent]

Worker Agent runs for each section. Reads the plan, finds first pending section, generates draft, self-evaluates against quality rubric, updates the plan status. STOPS.

Next worker starts fresh, reads updated plan, continues with next pending section.

[Key point]

Each worker is stateless. But the project progresses because response_plan.json tracks everything."

[Transition]

---

## SLIDE 19: THE STATE FILE

**Title:** The Structured Record

**Content:**

```json
{
  "rfp_id": "acme-2024-q4",
  "client": "Acme Manufacturing",
  "due_date": "2025-01-15",
  "sections": [
    {
      "id": "exec-summary",
      "requirements": ["ES-1", "ES-2", "ES-3"],
      "template": "executive-summary-v2.md",
      "status": "complete",
      "quality_score": 4.2
    },
    {
      "id": "technical-approach",
      "requirements": ["TA-1", "TA-2"],
      "template": "technical-approach-v3.md",
      "status": "pending"
    }
  ]
}
```

**Graphic:** JSON structure with annotations pointing to key fields

**SPEAKER NOTES:**

"This is what the structured record looks like.

[Walk through structure]

The plan has RFP metadata - ID, client, due date.

Each section tracks requirements, template mapping, status, and quality score.

[Point to status fields]

See how status changes? 'complete' with quality score, 'pending' awaiting work.

Any worker can read this, see exec-summary is done, technical-approach is next, and continue.

This is the PROJECT memory. The workers are stateless, but the project isn't."

[Transition: Click to Segment 4]

---

## SEGMENT 4: PLANNING YOUR CAPSTONE
### Duration: 5 minutes | Slides 20-21

---

## SLIDE 20: AGENT SELECTION CRITERIA

**Title:** Choosing Your Capstone Agent

**Content:**

**Selection Criteria:**
- Complex enough to benefit from autonomy
- Clear success criteria
- Measurable business value
- Builds on your Block 2 workflows

**Planning Questions:**
1. What goal should the agent achieve?
2. What tools does it need?
3. What decisions must it make?
4. How will you know it succeeded?
5. What could go wrong?

**Graphic:** Checklist with evaluation criteria

**SPEAKER NOTES:**

"Now let's apply this to YOUR capstone.

[Point to criteria]

Your agent should be complex enough to benefit from agent architecture - simple tasks don't need it. Clear success criteria - you need to know when it's working. Measurable value - time saved, quality improved. Builds on Block 2 - leverage your existing work.

[Point to questions]

These five questions guide your design. Exercise 1.2 walks you through each in detail.

Let's do a quick brainstorm."

[Transition]

---

## SLIDE 21: LIVE BRAINSTORM

**Title:** Your Agent Candidate

**Content:**

**Quick Exercise (60 seconds):**

Think about your Block 2 workflows:
- Which has the most variable inputs?
- Which requires the most human judgment?
- Which breaks most often on unexpected input?

**That's your agent candidate.**

Drop your initial idea in the chat.

**Graphic:** Thought bubble with question marks transforming into lightbulb

**SPEAKER NOTES:**

"Take 60 seconds right now.

[Read the prompts slowly]

Which Block 2 workflow has the most variable inputs?
Which requires the most human judgment?
Which breaks most often when something unexpected arrives?

[Pause 30 seconds]

The intersection of those answers is your agent candidate.

Drop your initial idea in the chat - just a phrase or sentence.

[Wait for responses, acknowledge 2-3]

Great ideas. These will become your Exercise 1.2 focus. Now let's preview your homework."

[Transition: Click to Closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 22-24

---

## SLIDE 22: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| 1.1: Agent vs. Workflow Analysis | 20 min | `agent-opportunity-analysis.md` | Identify candidates |
| 1.2: Agent Design Document | 35 min | `agent-design-document.md` | Comprehensive planning |
| 1.3: Agent Skeleton Setup | 20 min | Folder structure + system prompt | Foundation building |
| **Total** | **75 min** | | |

**Graphic:** Exercise flow showing progression from analysis to design to setup

**GRAPHICS:**

**Graphic 1: Homework Exercise Flow**
- Purpose: Show the logical progression and dependencies between the three exercises
- Type: Process flow diagram with time allocation
- Elements: Three connected boxes representing exercises; arrows showing dependencies; time indicators
- Labels:
  - Exercise 1.1 box: "Agent vs. Workflow Analysis" with "20 min" badge and "Identify best candidate" outcome
  - Exercise 1.2 box: "Agent Design Document" with "35 min" badge and "Complete planning" outcome
  - Exercise 1.3 box: "Agent Skeleton Setup" with "20 min" badge and "Create structure" outcome
  - Arrow labels: "Candidate selected" → "Design complete" →
  - Total time: "75 minutes" prominently displayed
- Relationships: Sequential flow left to right; each exercise builds on previous; outputs become inputs to next step

**SPEAKER NOTES:**

"Here's your homework for this week. You have 75 minutes of exercises.

[Walk through each]

Exercise 1.1 - analyze your Block 2 workflows for agent potential. 20 minutes. This helps you pick the right candidate.

Exercise 1.2 - create your agent design document. 35 minutes. This is the big one - it becomes your 'Setup Agent output' for the project.

Exercise 1.3 - set up your agent skeleton in GitHub. 20 minutes. Folder structure and initial system prompt.

Complete them in order. Your participant guide has detailed instructions and templates."

[Transition]

---

## SLIDE 23: RESOURCES

**Title:** Resources for This Week

**Content:**

**Templates & Files:**
- Agent Opportunity Analysis template - Participant Guide
- Agent Design Document template - Participant Guide
- System Prompt template - Participant Guide

**Reference Materials:**
- [Anthropic Agent Documentation](https://docs.anthropic.com/en/docs/agents)
- [MCP Server Registry](https://github.com/modelcontextprotocol/servers)

**Support:**
- Questions: Support channel
- Pre-work review: Archive folder - Agent Memory Meta-Framework

**Graphic:** Resource icons with links

**SPEAKER NOTES:**

"Resources for this week.

All templates are in your participant guide. The design document template is comprehensive - follow it section by section.

[Point to references]

The Anthropic docs are excellent for agent concepts. MCP Server Registry for finding tools.

If you didn't complete the pre-work, prioritize reviewing it - we build on those concepts throughout Block 3."

[Transition]

---

## SLIDE 24: NEXT WEEK PREVIEW

**Title:** Next Week: Building Reliable Agents

**Content:**

**Preview:**
Week 2 covers the Domain Memory pillars, the agent execution loop, and error handling.

**What to Complete Before Then:**
- [ ] Exercise 1.1: Agent vs. Workflow Analysis
- [ ] Exercise 1.2: Agent Design Document
- [ ] Exercise 1.3: Agent Skeleton Setup

**Key Preparation:**
Review MCP servers you'll need for your agent

**Graphic:** Preview image showing execution loop diagram

**SPEAKER NOTES:**

"Next week we cover Building Reliable Agents.

We'll go deep on Domain Memory - the three pillars in practice. The agent execution loop - how agents actually run. And error handling - what to do when things go wrong.

[Point to checklist]

Complete all three exercises. Week 2 builds directly on your design document.

[Point to preparation]

Also review what MCP servers your agent will need. Week 3 is MCP deep dive, but start thinking about it now.

[Final close]

Welcome to Block 3! This is where AI becomes truly powerful. You've learned to prompt. You've learned to engineer workflows. Now you're learning to architect autonomous systems.

Questions before we wrap?

[Handle any questions]

Great session today. Remember: design before building. Your agent design document is your foundation.

See you next week!"

---

## APPENDICES

### Appendix A: Slide Type Definitions

Use these type classifications in slide headers to indicate the slide's role:

**TITLE SLIDE** - Opens presentation; contains title, subtitle, presenter info
**PROBLEM STATEMENT** - Establishes challenge/pain point; creates tension
**INSIGHT / REVELATION** - Delivers key insight or "aha moment"
**CONCEPT INTRODUCTION** - Introduces new term, framework, or mental model
**FRAMEWORK / MODEL** - Presents structured approach with diagrams/pillars
**COMPARISON** - Contrasts approaches using tables or side-by-side layouts
**DEEP DIVE** - Detailed exploration of specific topic
**CASE STUDY** - Real-world example with outcomes and metrics
**PATTERN / BEST PRACTICE** - Describes proven approach with do's/don'ts
**METRICS / DATA** - Presents quantitative information with charts
**ARCHITECTURE / DIAGRAM** - Shows system structure or process flow
**OBJECTION HANDLING** - Anticipates and addresses audience concerns
**ACTION / NEXT STEPS** - Provides concrete actions for audience
**SUMMARY / RECAP** - Consolidates key points from section
**SECTION DIVIDER** - Marks transition between major sections
**CLOSING / CALL TO ACTION** - Final slide before Q&A with core thesis
**Q&A / CONTACT** - Invites questions and includes contact information

### Appendix B: Content Element Formats

**Bullet Points:**
```markdown
- First level bullet point
  - Second level for supporting detail
- Use parallel structure across bullets
```

**Numbered Lists:**
```markdown
1. First sequential item
2. Second sequential item
```

**Tables:**
```markdown
| Column Header 1 | Column Header 2 |
|-----------------|-----------------|
| Row 1 data | Row 1 data |
```

**Bad/Good Example Format:**
```markdown
**Bad Example:**
"[Description of anti-pattern]"
- [Why it's problematic]

**Good Example:**
"[Description of best practice]"
- [Why it works]
```

### Appendix C: Speaker Notes Conventions

**Stage Directions (in brackets):**
- `[Pause]` - Deliberate silence for effect
- `[Point to X]` - Gesture to specific visual element
- `[Emphasize this]` - Vocal emphasis
- `[Personal story - adjust to your context]` - Customization placeholder
- `[Show of hands]` - Audience participation cue

**Transition Markers:**
- `[Transition]` - Standard transition cue
- `[OPENING - Description]` - Opening segment marker
- `[Hook - Description]` - Attention-grabbing opener

### Appendix D: Background Section Guidelines

**Rationale (3-5 bullets):**
- Explain slide's purpose in narrative arc
- Describe mental shift it creates
- Note connections to adjacent slides
- Justify chosen framing/approach

**Key Research & Citations (3-5 entries):**
Format: **[Source Name (Year)]**: [Detailed explanation]
- Include methodology when relevant
- Cite specific statistics or findings
- Explain how research supports claims

**Q&A Preparation (3-5 questions):**
Format: *"[Question]"*: [Response]
- Anticipate skeptical questions
- Prepare for "what about..." objections
- Have specific examples ready

### Appendix E: Sources Section Guidelines

Include 3-7 sources per slide, formatted as:
```markdown
1. [Full title with hyperlink](URL) - [Brief description]
```

Source types:
- **Primary research**: Academic papers, official documentation
- **Industry reports**: Analyst reports, surveys, benchmarks
- **Practitioner content**: Blog posts, conference talks
- **Official documentation**: Product docs, API references

### Appendix F: Implementation Guidance Structure

**Getting Started (2-4 items):**
- Immediate actions (can do today)
- Low-barrier entry points
- Foundation-building steps

**Best Practices (3-5 items):**
- Proven approaches with specific criteria
- Patterns that scale
- Measurable success indicators

**Common Pitfalls (2-4 items):**
- Mistakes that seem logical but fail
- Anti-patterns to avoid
- Assumptions that mislead

**Tools & Technologies (2-4 categories):**
Format: **[Category]**: [Tool names] - [use case description]

### Appendix G: Visual/Graphic Description Guidelines

Describe graphics with enough detail for a designer:

1. **Type**: diagram, illustration, chart, photo, etc.
2. **Main elements**: What objects/shapes appear
3. **Arrangement**: Spatial relationships
4. **Labels/Text**: Any text in the graphic
5. **Communication goal**: What the visual conveys

### Appendix H: Visual Design Guidelines

**Block 3 Color Scheme:**
| Element | Color | Hex Code |
|---------|-------|----------|
| Primary | Green | #00CC99 |
| Accent | Teal | #008B8B |
| Background | White | #FFFFFF |
| Text | Dark Gray | #333333 |

**Block 3 Theme:**
- Green represents growth, automation, and intelligent systems
- Use green highlights for agent-related concepts
- Teal accents for orchestration and coordination
- Clean, modern aesthetic reflecting production engineering

**Graphic Suggestions:**
- Title slides: Agent/architecture visuals with green theme
- Architecture diagrams: Clear component separation
- Flow diagrams: Directional arrows showing data/control flow
- Comparison slides: Side-by-side or table formats

### Appendix I: Quality Checklist

**Content Quality:**
- [ ] Key Thesis clearly stated in metadata
- [ ] Learning objectives are actionable
- [ ] Each slide has clear purpose in narrative
- [ ] Transitions connect ideas smoothly
- [ ] Examples are Block 3-relevant (automation architecture)

**Background Sections:**
- [ ] Rationale explains slide's role in presentation
- [ ] Research citations support claims with specifics
- [ ] Q&A preparation addresses likely objections
- [ ] Sources are credible and linked

**Implementation Guidance:**
- [ ] Getting Started provides immediate actions
- [ ] Best Practices are specific and proven
- [ ] Common Pitfalls warn against real mistakes
- [ ] Tools recommended are current and relevant

**Technical Accuracy:**
- [ ] Code examples are syntactically correct
- [ ] Architectural patterns follow industry standards
- [ ] Metrics and calculations are accurate
- [ ] Links to external resources work

**Audience Engagement:**
- [ ] Speaker notes include engagement cues
- [ ] Questions prompt reflection
- [ ] Examples relate to consulting work
- [ ] Exercises connect to real capstone needs

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |
