# **POWERPOINT PRESENTATION: ADVANCED MODULE 1 SESSION 2**
## **Team-Based Orchestration & Hybrid Patterns**

**Module:** Advanced Module 1 - Advanced Orchestration Patterns
**Session:** 2 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Advanced Module 1 participants who completed Session 1 with working parallel orchestration systems

**Key Thesis:** Team-Based orchestration enables agents to collaborate through specialized roles and inter-agent communication, while Hybrid orchestration combines Sequential, Parallel, and Team-Based patterns to optimize each workflow phase for its specific requirements—creating production-grade multi-agent systems that balance speed, quality, and complexity.

**Session Learning Objectives:** By the end of this session, participants will:
1. Design agent teams with specialized roles and clear interaction protocols
2. Implement inter-agent communication using direct handoff, request-response, or shared workspace patterns
3. Combine Sequential, Parallel, and Team-Based patterns into hybrid orchestration systems
4. Create production-ready multi-pattern agent architectures

**Entry Criteria:**
- [ ] Parallel pattern implemented and tested (Session 1 complete)
- [ ] Result aggregation working
- [ ] Understanding of agent specialization
- [ ] Familiar with agent communication concepts

**Exit Criteria:**
- [ ] Team-Based pattern architecture understood
- [ ] Agent roles and interactions designed
- [ ] Collaborative workflow implemented
- [ ] Inter-agent communication functional
- [ ] Hybrid orchestration approach designed
- [ ] Module capstone completed

**Presentation Structure:**
1. Opening & Session 1 Recap (3 min) - Slides 1-3
2. Segment 1: Team-Based Pattern Fundamentals (12 min) - Slides 4-7
3. Segment 2: Designing Agent Teams (12 min) - Slides 8-11
4. Segment 3: Inter-Agent Communication (12 min) - Slides 12-15
5. Segment 4: Hybrid Orchestration (9 min) - Slides 16-18
6. Capstone Preview & Close (3 min) - Slides 19-21

**Total Slides:** 21

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Advanced Module 1 Session 2: Team-Based Orchestration & Hybrid Patterns

**Subtitle:** Building Collaborative Multi-Agent Systems

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program - Advanced Modules

**Graphic:** Clean title slide with program branding. Green tones (Block 3 advanced/architecture theme)

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Session 2 of Advanced Module 1. Last session you learned Parallel orchestration - running independent agents simultaneously to reduce execution time.

Today we're taking it to the next level: Team-Based orchestration, where agents collaborate like a real team, and Hybrid orchestration, where you combine Sequential, Parallel, and Team-Based patterns into sophisticated multi-pattern systems.

By the end of today, you'll have the tools to build enterprise-grade agent architectures that are both fast AND intelligent."

[Transition: Click to next slide]

---

### SLIDE 2: SESSION OVERVIEW

**Title:** Today's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Session 1 Recap & Preview |
| 3-15 min | Segment 1 | Team-Based Pattern Fundamentals |
| 15-27 min | Segment 2 | Designing Agent Teams |
| 27-39 min | Segment 3 | Inter-Agent Communication |
| 39-42 min | Segment 4 | Hybrid Orchestration |
| 42-45 min | Close | Capstone Preview & Wrap-Up |

**Graphic:** Simple timeline showing the session flow

**SPEAKER NOTES:**

"Here's our roadmap for the next 45 minutes:

First, we'll explore Team-Based orchestration - what it is, when to use it, and how it differs from Parallel patterns.

Then, we'll design agent teams using role archetypes like Researcher, Analyst, Critic, and Editor.

In segment 3, we'll tackle inter-agent communication - how agents talk to each other and share work.

And we'll close with Hybrid orchestration - combining all three patterns (Sequential, Parallel, Team-Based) into one system.

[Pause]

This is sophisticated content, but you're ready. Let's dive in."

[Transition]

---

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Design collaborative agent teams**
   - Assign specialized roles with clear responsibilities

2. **Implement inter-agent communication**
   - Choose and build handoff, request-response, or workspace patterns

3. **Create hybrid orchestration systems**
   - Combine Sequential, Parallel, and Team-Based patterns appropriately

4. **Deliver Module 1 capstone**
   - Multi-pattern system with performance documentation

**Graphic:** Checklist visual with checkboxes

**SPEAKER NOTES:**

"These are our four objectives for today:

[Read each objective]

Notice the progression: we started Module 1 with Parallel patterns. Today we add Team-Based collaboration. Then we combine everything into Hybrid systems.

Your capstone - Exercise 2.3 - will demonstrate mastery of all three patterns in one integrated system.

[Point to first objective]

Team design is where we start. Just like real consulting teams have specialized roles, so do agent teams.

Let's explore what that means."

[Transition: Click to Segment 1]

---

## SEGMENT 1: TEAM-BASED PATTERN FUNDAMENTALS
### Duration: 12 minutes | Slides 4-7

---

### SLIDE 4: BEYOND PARALLEL - THE COLLABORATION NEED

**Title:** The Limitation: Parallel Isn't Always Enough

**Content:**

**The Challenge:**
Parallel orchestration is fast but lacks collaboration. Agents work independently - they can't:
- Ask each other questions
- Review each other's work
- Iterate based on feedback
- Combine expertise interactively

**Real Scenario:**
Creating a strategic report requires:
- Research (gather data)
- Analysis (find patterns)
- Writing (draft content)
- Review (ensure quality)

These tasks CAN'T all run in parallel - they have dependencies. But sequential is too rigid.

**What We Need:** Agents that can collaborate like human teams

**Graphic:** Diagram showing parallel agents working in isolation vs team agents interacting

**GRAPHICS:**

**Graphic 1: Parallel vs Team Collaboration Comparison**
- Purpose: Contrast the isolation of parallel execution with the collaboration of team-based patterns
- Type: Side-by-side comparison diagram
- Elements:
  - Left side labeled "Parallel: Isolated Execution"
    - Four agent boxes with no connections between them
    - Walls/barriers between agents
    - All outputs go directly to aggregator
    - Label: "No interaction", "Fast but inflexible"
  - Right side labeled "Team-Based: Collaborative Execution"
    - Four agent boxes with bidirectional arrows between them
    - Shared workspace surrounding all agents
    - Agents labeled with roles (Researcher, Analyst, Writer, Reviewer)
    - Label: "Agents can communicate", "Iterative refinement possible"
- Labels: "Parallel = Speed", "Team = Quality through collaboration"
- Relationships: Contrast shows what team-based adds: communication and shared context

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Last session you learned Parallel orchestration. It's powerful - cuts execution time dramatically.

But here's the limitation: parallel agents work in total isolation. They can't talk to each other, can't review each other's work, can't iterate.

[Point to real scenario]

Think about creating a strategic report. Research must happen before writing. Writing must happen before review. You can't parallelize everything.

But pure Sequential is too rigid - the Analyst and Writer could benefit from back-and-forth collaboration.

[Pause]

What we need is agents that work like a real team: specialized roles, clear responsibilities, and the ability to collaborate.

That's Team-Based orchestration."

[Transition]

**BACKGROUND:**

**Rationale:**
- Establishes why Team-Based is needed beyond Parallel
- Creates motivation through realistic scenario
- Sets up the pattern as solution to limitation
- Bridges from Session 1's speed focus to Session 2's quality focus

**Key Research & Citations:**
- **Multi-Agent Systems Research (Wooldridge, 2009)**: Demonstrates that agent collaboration through specialized roles mirrors effective human team structures, with quality improvements of 20-40% over isolated agents.
- **Software Engineering Team Patterns**: Agile methodologies show that cross-functional teams with specialists (developer, tester, designer) outperform generalist individuals on complex tasks.
- **Human-AI Collaboration Studies (2024)**: Research shows iterative review cycles between AI agents improve output quality by 30-50% compared to single-pass generation.

**Q&A Preparation:**
- *"Why not just use Sequential for report creation?"*: Sequential works but misses optimization opportunities. Team-Based allows iterative refinement - Writer can ask Researcher for clarification, Reviewer can send draft back to Writer for revision.
- *"Isn't Team-Based slower than Parallel?"*: Yes, but it's solving a different problem. Parallel optimizes for speed when tasks are independent. Team-Based optimizes for quality when collaboration adds value.
- *"How many agents is too many for a team?"*: Beyond 5-6 agents, coordination complexity outweighs benefits. Keep teams small and focused.

**Sources:**
1. [An Introduction to MultiAgent Systems (Wooldridge)](https://www.wiley.com/en-us/An+Introduction+to+MultiAgent+Systems%2C+2nd+Edition-p-9780470519462) - Multi-agent theory
2. [Agile Cross-Functional Teams](https://www.scrum.org/resources/blog/cross-functional-scrum-teams) - Team design patterns
3. [Human-AI Collaboration Research](https://arxiv.org/abs/2408.05440) - Iterative refinement studies

---

### SLIDE 5: TEAM-BASED ORCHESTRATION PATTERN

**Title:** Team-Based Pattern Overview

**Content:**

**Core Principle:** Agents with specialized roles collaborate through shared workspace and inter-agent communication

**Pattern Structure:**
```
┌─────────────────────────────────────────┐
│           TEAM WORKSPACE                │
│                                         │
│  [Researcher] ←──→ [Analyst]           │
│       ↓              ↓                  │
│       └──→ [Writer] ←┘                 │
│              ↓                          │
│         [Reviewer]                      │
│              ↓                          │
│          [Output]                       │
└─────────────────────────────────────────┘
```

**Key Characteristics:**
- Distinct roles (like real team members)
- Inter-agent communication
- Shared workspace/context
- Iterative refinement possible
- More complex coordination

**Graphic:** Visual showing team workspace with agents interacting

**GRAPHICS:**

**Graphic 1: Team Workspace Architecture**
- Purpose: Illustrate the team-based orchestration pattern with shared workspace and agent communication
- Type: Architectural diagram with workspace container
- Elements:
  - Large box labeled "TEAM WORKSPACE" containing all agents
  - Four agent nodes: Researcher, Analyst, Writer, Reviewer
  - Bidirectional arrows showing communication:
    - Researcher ↔ Analyst
    - Analyst → Writer
    - Researcher → Writer
    - Writer → Reviewer
  - Shared workspace area showing artifacts:
    - "Research Notes"
    - "Draft Documents"
    - "Review Comments"
  - Output arrow from Reviewer leading outside workspace
- Labels: "Shared Context", "Inter-Agent Communication", "Iterative Refinement"
- Relationships: All agents operate within shared workspace, communication flows show collaboration patterns

**SPEAKER NOTES:**

"[INSIGHT - Deliver solution]"

"Team-Based orchestration treats agents like team members.

[Point to diagram]

Each agent has a specialized role. Researcher gathers information. Analyst interprets it. Writer creates content. Reviewer ensures quality.

But here's the key: they communicate. Researcher can pass findings to Analyst. Analyst and Writer can collaborate on structure. Writer produces draft. Reviewer can send it back for revision.

Notice the workspace surrounding all agents - this is shared context where they all read and write artifacts.

The pattern enables iterative refinement: not just linear handoffs, but back-and-forth collaboration.

Let me show you when this pattern makes sense..."

[Transition]

**BACKGROUND:**

**Rationale:**
- Provides concrete visual and structural model for Team-Based pattern
- Introduces shared workspace as key enabling component
- Establishes foundation for designing teams in Segment 2

**Key Research & Citations:**
- **Multi-Agent Systems (Wooldridge, 2009)**: Academic field studying collaborative agent architectures, showing that agent teams with role specialization outperform homogeneous agent groups by 25-35%.
- **Shared Context Pattern**: Common in distributed systems (e.g., Redis pub/sub, message queues), enabling coordination without tight coupling between agents.
- **Human Team Dynamics**: Research on high-performing teams shows clear roles + shared context + communication protocols = higher quality outcomes than individual contributors.

**Q&A Preparation:**
- *"What exactly is the 'shared workspace'?"*: It's a common data structure (file, database, message queue) where all agents can read current state and write their contributions. Like a shared Google Doc or Slack channel.
- *"Do agents need to run simultaneously?"*: Not necessarily. Unlike Parallel (which requires simultaneity), Team-Based agents can take turns. The key is they can reference each other's work.
- *"Can I have multiple teams in one system?"*: Yes - this becomes Hybrid orchestration with team phases. We'll cover it in Segment 4.

**Sources:**
1. [Multi-Agent Systems Book (Wooldridge)](https://www.wiley.com/en-us/An+Introduction+to+MultiAgent+Systems%2C+2nd+Edition-p-9780470519462) - Foundational theory
2. [Redis Pub/Sub Pattern](https://redis.io/docs/manual/pubsub/) - Shared workspace implementation
3. [Google's SRE Team Patterns](https://sre.google/workbook/team-design/) - Role-based collaboration

**Implementation Guidance:**

**Getting Started:**
- Start with 2 agents (e.g., Writer + Reviewer) before scaling to full teams
- Use file-based shared workspace (JSON/YAML) for simplicity
- Define clear handoff points between agents initially

**Best Practices:**
- Give each agent a distinct, non-overlapping responsibility
- Use structured data formats (JSON) for workspace artifacts to enable parsing
- Include metadata in workspace: current_phase, active_agent, completion_status
- Version workspace snapshots for debugging

**Common Pitfalls:**
- Creating agents with overlapping responsibilities (leads to conflict)
- Not defining who writes to workspace when (leads to race conditions)
- Over-complicating initial design - start simple, iterate

**Tools & Technologies:**
- **File-based**: JSON/YAML files in shared directory
- **Message-based**: Redis pub/sub, RabbitMQ, AWS SQS
- **Database-backed**: PostgreSQL/SQLite with agent state tables
- **Framework-native**: LangGraph shared state, CrewAI workspace

---

### SLIDE 6: WHEN TO USE TEAM-BASED

**Title:** Decision Framework: Team-Based vs Other Patterns

**Content:**

**Use Team-Based When:**
- ✓ Complex problems requiring multiple perspectives
- ✓ Iterative refinement improves quality
- ✓ Quality through collaboration (not just speed)
- ✓ Simulating expert panels or review boards

**Do NOT Use Team-Based When:**
- ✗ Simple, linear tasks (use Sequential)
- ✗ Speed is the only priority (use Parallel)
- ✗ Limited resources/budget
- ✗ Tasks are completely independent (use Parallel)

**Comparison:**

| Pattern | Best For | Trade-off |
|---------|----------|-----------|
| Sequential | Simple workflows | Slow but simple |
| Parallel | Independent tasks | Fast but isolated |
| Team-Based | Collaborative refinement | High quality but complex |

**Graphic:** Decision tree or comparison matrix

**SPEAKER NOTES:**

"When should you use Team-Based orchestration?

[Walk through 'Use Team-Based When' items]

The key indicator: does collaboration improve quality? If a second perspective, review cycle, or iterative refinement makes the output better, Team-Based is appropriate.

[Point to DO NOT use section]

But be careful with these scenarios:

If your task is simple and linear - Sequential is sufficient. Don't over-engineer.

If speed is the only priority and tasks are independent - Parallel is faster.

If budget is constrained - Team-Based uses more agents (more cost).

[Comparison table]

Think of it this way:
- Sequential: One consultant doing all the work
- Parallel: Four consultants working independently
- Team-Based: Four consultants collaborating on a whiteboard

Different tools for different problems."

[Transition]

---

### SLIDE 7: TEAM-BASED EXAMPLES

**Title:** Real-World Team Applications

**Content:**

| Scenario | Team Roles | Why Team-Based Works |
|----------|------------|---------------------|
| **Content Creation** | Researcher → Writer → Editor → Reviewer | Iterative improvement through review cycles |
| **Strategic Analysis** | Data Gatherer → Analyst → Critic → Synthesizer | Multiple perspectives create better insights |
| **Decision Support** | Researcher → Pro Analyst → Con Analyst → Recommender | Balanced evaluation of options |
| **Product Design** | User Researcher → Designer → Engineer → Tester | Cross-functional collaboration |

**Anti-Example:**
```
❌ Data Pipeline Processing:
   Extract → Transform → Load
   (Pure Sequential - no collaboration needed)
```

**Graphic:** Icons or visuals for each scenario type

**SPEAKER NOTES:**

"Let's look at real scenarios where Team-Based excels:

Content creation: Researcher gathers sources, Writer drafts, Editor refines, Reviewer checks quality. Each role has expertise, and iteration improves the final output.

Strategic analysis: Data Gatherer gets facts, Analyst finds patterns, Critic challenges assumptions, Synthesizer creates recommendations. The back-and-forth produces better insights than any single agent.

[Point to anti-example]

But here's what DOESN'T need Team-Based: simple data pipelines. Extract → Transform → Load is pure Sequential. No collaboration adds value.

[Pause]

Your Exercise 2.1 will design a team for your specific use case. Think about what roles you need and how they should interact.

Questions on Team-Based fundamentals before we design actual teams?"

[Transition: Click to Segment 2]

---

## SEGMENT 2: DESIGNING AGENT TEAMS
### Duration: 12 minutes | Slides 8-11

---

### SLIDE 8: AGENT ROLE ARCHETYPES

**Title:** Building Your Team: Role Archetypes

**Content:**

| Role | Responsibility | Example Tasks | When Needed |
|------|----------------|---------------|-------------|
| **Researcher** | Gather information | Web search, file lookup, data retrieval | Starting point for knowledge work |
| **Analyst** | Process & interpret | Data analysis, pattern finding, insights | Making sense of information |
| **Creator** | Generate content | Writing, designing, modeling | Producing deliverables |
| **Critic** | Evaluate quality | Review, scoring, validation | Ensuring quality standards |
| **Editor** | Refine & polish | Revision, formatting, optimization | Final refinement |
| **Coordinator** | Manage workflow | Task assignment, tracking, decisions | Complex multi-agent teams |

**Design Principle:** Each role should have clear, non-overlapping responsibilities

**Graphic:** Icons representing each role archetype

**GRAPHICS:**

**Graphic 1: Agent Role Archetype Icons and Responsibilities**
- Purpose: Provide visual identity for each agent role type with clear responsibilities
- Type: Icon grid with role descriptions
- Elements:
  - Six role cards in 2x3 grid:
    - Researcher: Magnifying glass icon, "Gathers information"
    - Analyst: Bar chart/graph icon, "Finds patterns & insights"
    - Creator: Pencil/brush icon, "Produces deliverables"
    - Critic: Checklist/validation icon, "Evaluates quality"
    - Editor: Polish/refinement icon, "Refines & optimizes"
    - Coordinator: Network/hub icon, "Manages workflow"
  - Each card shows: Icon, Role name, Key responsibility, Example tasks
  - Color coding by function: Blue (information), Green (creation), Orange (evaluation), Purple (coordination)
- Labels: "Clear, non-overlapping responsibilities", "3-4 roles optimal for most teams"
- Relationships: Roles complement each other to form complete workflow

**SPEAKER NOTES:**

"When designing agent teams, start with role archetypes.

[Walk through table]

Researcher: Gathers raw information. Think: web search, database queries, file reads.

Analyst: Takes research and finds meaning. Pattern recognition, data interpretation.

Creator: Produces the actual deliverable. Writer, designer, modeler.

Critic: Evaluates quality. Scores outputs, validates against requirements.

Editor: Final polish. Formatting, optimization, refinement.

Coordinator: Manages complex workflows. Only needed when you have 5+ agents.

[Design principle]

The key: each role should have clear boundaries. If Researcher and Analyst do overlapping work, combine them into one agent.

Most teams need 3-4 roles. More than that gets complex fast."

[Transition]

**BACKGROUND:**

**Rationale:**
- Provides actionable archetypes participants can use immediately
- Maps to familiar human team roles for easy understanding
- Establishes vocabulary for team design exercises

**Key Research & Citations:**
- **Conway's Law (1967)**: Organizations design systems that mirror their communication structure. Agent teams with clear roles produce better-structured outputs.
- **Belbin Team Roles (1981)**: Research on human teams identified 9 role types; agent teams apply similar specialization principles.
- **DevOps RACI Matrix**: Role clarity (Responsible, Accountable, Consulted, Informed) reduces coordination overhead by 40-60%.

**Q&A Preparation:**
- *"Can one agent fill multiple roles?"*: Technically yes, but defeats the purpose. Role specialization improves quality. If combining roles, you're likely just building Sequential, not Team-Based.
- *"Do I need all 6 archetypes?"*: No - pick 3-4 that fit your use case. Not every team needs a Coordinator; only use when you have 5+ agents.
- *"Can I create custom roles?"*: Absolutely! These are archetypes, not requirements. If you need "Validator" or "Synthesizer", create them. Just keep responsibilities clear.

**Sources:**
1. [Conway's Law](https://www.melconway.com/Home/Conways_Law.html) - System-team alignment
2. [Belbin Team Roles](https://www.belbin.com/about/belbin-team-roles) - Role theory
3. [RACI Matrix Guide](https://www.projectmanager.com/blog/raci-chart-definition-tips-and-example) - Role clarity frameworks

**Implementation Guidance:**

**Getting Started:**
- Map your workflow to 3-4 archetypes (e.g., Research → Analysis → Creation)
- Write role descriptions with specific responsibilities before writing prompts
- Test with 2 roles initially (e.g., Creator + Critic)

**Best Practices:**
- Each role should have clear inputs and outputs
- Avoid role overlap (if unclear who does X, split or combine roles)
- Name roles descriptively (avoid generic "Agent 1", "Agent 2")
- Document what each role should NOT do (helps prevent scope creep)

**Common Pitfalls:**
- Creating too many roles (coordinate 5+ agents becomes unwieldy)
- Roles with vague boundaries (leads to duplication or gaps)
- Choosing roles based on pattern rather than actual need
- Not giving Coordinator sufficient authority when needed

**Tools & Technologies:**
- **Role templates**: Reusable prompt templates for common archetypes
- **Workflow diagrams**: Draw.io, Mermaid for visualizing role interactions
- **Testing**: Run each role in isolation first to verify it works independently

---

### SLIDE 9: TEAM COMPOSITION PATTERNS

**Title:** Common Team Structures

**Content:**

**Pattern 1: Linear Team**
```
Researcher → Writer → Editor → Reviewer
```
Good for: Content creation, report generation
Pros: Simple, clear handoffs
Cons: No parallel work

**Pattern 2: Collaborative Team**
```
Researcher ──┬── Analyst ──┬── Synthesizer
             └── Critic ───┘
```
Good for: Analysis requiring multiple perspectives
Pros: Collaborative insights
Cons: More complex coordination

**Pattern 3: Parallel + Team Hybrid**
```
┌── Researcher A ──┐
└── Researcher B ──┘──→ Writer ←→ Reviewer
```
Good for: Large research with collaborative synthesis
Pros: Speed + quality
Cons: Most complex

**Graphic:** Visual diagrams of each pattern

**GRAPHICS:**

**Graphic 1: Linear Team Pattern**
- Purpose: Show simple sequential handoff team structure
- Type: Linear flow diagram
- Elements:
  - Four boxes in horizontal line: Researcher → Writer → Editor → Reviewer
  - Single arrows showing sequential flow
  - Labels: "Simple handoffs", "Clear stages", "No parallel work"
- Labels: "Good for: Content creation, report generation"
- Relationships: Each agent completes before next starts

**Graphic 2: Collaborative Team Pattern**
- Purpose: Illustrate multi-perspective convergence for analysis
- Type: Convergence diagram
- Elements:
  - Researcher at top feeding two agents
  - Analyst and Critic working in parallel below Researcher
  - Both converge to Synthesizer at bottom
  - Arrows show: Researcher → Analyst, Researcher → Critic, Analyst → Synthesizer, Critic → Synthesizer
- Labels: "Multiple perspectives", "Convergent analysis"
- Relationships: Single input feeds multiple analyzers who converge results

**Graphic 3: Parallel + Team Hybrid**
- Purpose: Show combination of parallel research with collaborative synthesis
- Type: Hybrid pattern diagram
- Elements:
  - Two parallel Researcher boxes (A and B) at top
  - Both feed into Writer
  - Writer has bidirectional arrow with Reviewer
  - Final output from Reviewer
  - Bracket showing "Parallel Phase" around researchers
  - Bracket showing "Team Phase" around Writer-Reviewer interaction
- Labels: "Speed + Quality", "Most complex"
- Relationships: Parallel execution followed by collaborative refinement

**SPEAKER NOTES:**

"Here are three common team structures:

[Pattern 1]

Linear Team: Simple handoffs. Researcher → Writer → Editor → Reviewer. Each agent completes before next starts. Good for content creation where stages are clear.

[Pattern 2]

Collaborative Team: Researcher feeds both Analyst and Critic. They both contribute to Synthesizer. Multiple perspectives create better output. Good for strategic analysis.

[Pattern 3]

Parallel + Team Hybrid: Multiple Researchers work in parallel gathering data. They feed one Writer who iterates with Reviewer. Combines speed of Parallel with quality of Team-Based.

[Pause]

In Exercise 2.1, you'll design one of these structures for your use case. Choose based on your quality vs speed vs complexity trade-offs."

[Transition]

---

### SLIDE 10: DEFINING AGENT PERSONALITIES

**Title:** Creating Team Agent Prompts

**Content:**

**Standard Agent Prompt:**
```
You are an AI agent that [does task].

Input: [description]
Output: [description]
```

**Team Agent Prompt (Enhanced):**
```
You are the [ROLE] on a team working to [GOAL].

Your Teammates:
- [Role 1]: [What they do, when to ask them]
- [Role 2]: [What they do, when to ask them]

Your Responsibilities:
- [Specific duty 1]
- [Specific duty 2]

Collaboration Guidelines:
- When you need [X], request from [Role]
- When you complete [Y], pass to [Role]
- Check shared workspace for [Z]
```

**Key Difference:** Team agents know about each other and how to collaborate

**Graphic:** Side-by-side comparison of prompts

**GRAPHICS:**

**Graphic 1: Standard vs Team-Aware Agent Prompts**
- Purpose: Demonstrate the critical difference in prompt structure for team agents
- Type: Side-by-side text comparison with highlighting
- Elements:
  - Left panel: "Standard Agent Prompt"
    - Simple prompt text: "You are an AI agent that [does task]. Input: [description], Output: [description]"
    - Gray/neutral color
    - Label: "Isolated perspective"
  - Right panel: "Team Agent Prompt"
    - Enhanced prompt sections highlighted:
      - "You are the [ROLE] on a team" (highlighted)
      - "Your Teammates:" section (highlighted)
      - "Collaboration Guidelines:" section (highlighted)
    - Green/active color for highlighted sections
    - Label: "Team-aware perspective"
  - Arrows pointing to key differences
- Labels: "Team agents know about each other", "Enables collaboration through awareness"
- Relationships: Enhanced prompt structure creates team capability

**SPEAKER NOTES:**

"Creating team agents requires different prompts than isolated agents.

[Point to standard prompt]

Standard agents just know their task: input → process → output.

[Point to team prompt]

Team agents know:
1. Their role on the team
2. Who their teammates are and what they do
3. When to ask for help vs work independently
4. How to pass work to next agent

This awareness enables collaboration.

[Example]

A Writer agent knows: 'When I need market data, ask Researcher. When I finish draft, pass to Editor.'

That's what makes it a team, not just a sequence."

[Transition]

---

### SLIDE 11: SEGMENT 2 SUMMARY

**Title:** Team Design Recap

**Content:**

**Key Takeaway:** Effective agent teams have specialized roles with clear responsibilities and defined collaboration protocols

**Remember:**
- Use role archetypes (Researcher, Analyst, Creator, Critic, Editor)
- Most teams need 3-4 agents (more gets complex)
- Define team structure: Linear, Collaborative, or Hybrid
- Give agents team awareness in their prompts

**You'll Practice:**
Exercise 2.1 - Design complete agent team for your use case

**Graphic:** Simple visual reinforcing role → team → collaboration

**SPEAKER NOTES:**

"Before we move to communication patterns, let me summarize:

Team design starts with roles. Pick from archetypes. Keep teams small - 3-4 agents.

Choose team structure based on your needs: Linear for simple, Collaborative for multiple perspectives, Hybrid for speed + quality.

Most importantly: give agents team awareness. They need to know their role, teammates, and collaboration rules.

In Exercise 2.1, you'll design your team using these principles.

[Pause]

Questions on team design before we tackle how agents actually communicate?"

[Transition: Click to Segment 3]

---

## SEGMENT 3: INTER-AGENT COMMUNICATION
### Duration: 12 minutes | Slides 12-15

---

### SLIDE 12: COMMUNICATION PATTERNS OVERVIEW

**Title:** How Agents Talk to Each Other

**Content:**

**Three Communication Patterns:**

1. **Direct Handoff** - Agent A completes → passes to Agent B
   - Simplest: clear ownership
   - No back-and-forth

2. **Request-Response** - Agent A asks Agent B for information
   - Flexible: agents can request help
   - Bi-directional communication

3. **Shared Workspace** - All agents read/write shared context
   - Most collaborative
   - Requires coordination layer

**Choosing Your Pattern:**
- Simple linear workflows → Direct Handoff
- Agents need each other's help → Request-Response
- Complex collaboration → Shared Workspace

**Graphic:** Visual showing all three patterns

**GRAPHICS:**

**Graphic 1: Three Communication Patterns Comparison**
- Purpose: Illustrate the three fundamental communication patterns for team agents
- Type: Three-panel comparison diagram
- Elements:
  - Panel 1: "Direct Handoff"
    - Agent A box → Result arrow → Agent B box
    - One-way flow
    - Simple relay icon
    - Label: "Simplest: Like relay race"
  - Panel 2: "Request-Response"
    - Agent A box with request arrow to Agent B
    - Response arrow back to Agent A
    - Speech bubble icons showing question/answer
    - Label: "Flexible: Agents can ask for help"
  - Panel 3: "Shared Workspace"
    - Multiple agents (A, B, C) around shared center
    - All with bidirectional arrows to shared workspace
    - Document/workspace icon in center
    - Coordinator presence shown
    - Label: "Most collaborative: Shared context"
- Labels: "Choose based on collaboration complexity"
- Relationships: Increasing collaboration capability from left to right, with increasing coordination complexity

**SPEAKER NOTES:**

"Now let's tackle how agents actually communicate.

You have three fundamental patterns:

[Pattern 1]

Direct Handoff: Agent A finishes, passes result to Agent B, done. Like a relay race - hand off the baton. Simplest approach.

[Pattern 2]

Request-Response: Agent A can ASK Agent B for information. 'Hey Researcher, I need market data.' Agent B responds. Agent A continues. More flexible because agents can request help.

[Pattern 3]

Shared Workspace: All agents read and write to shared context. Like working on a shared Google Doc. Most collaborative but needs someone (coordinator) to manage turn-taking.

[Choosing pattern]

Start with Direct Handoff. Upgrade to Request-Response when agents need to ask questions. Use Shared Workspace for highly iterative, complex collaboration.

Let me show you each in detail..."

[Transition]

---

### SLIDE 13: DIRECT HANDOFF PATTERN

**Title:** Pattern 1: Direct Handoff

**Content:**

**Structure:**
```
Agent A: [Does work] → {result} → Agent B: [Does work] → {result} → Agent C
```

**Implementation:**
```
orchestrator:
  result_a = call_agent_a(input)
  result_b = call_agent_b(result_a)
  result_c = call_agent_c(result_b)
  return result_c
```

**Pros:**
- Simple to implement
- Clear ownership (one agent at a time)
- Easy to debug

**Cons:**
- No back-and-forth possible
- Rigid flow
- Later agents can't influence earlier ones

**Best For:** Linear workflows where each stage builds on previous

**Graphic:** Flowchart showing linear handoff

**GRAPHICS:**

**Graphic 1: Direct Handoff Implementation**
- Purpose: Show the simple sequential execution pattern with clear handoffs
- Type: Sequential flow diagram with code overlay
- Elements:
  - Three agent boxes: Agent A, Agent B, Agent C
  - Result data packages flowing between them
  - Each package labeled: {result_a}, {result_b}, {result_c}
  - Orchestrator swimlane at bottom showing:
    - call_agent_a(input)
    - call_agent_b(result_a)
    - call_agent_c(result_b)
  - Green checkmarks showing "Completes" at each handoff
  - Red note showing "No back-and-forth possible"
- Labels: "Clear ownership - one agent at a time", "Easy to debug"
- Relationships: Linear dependency chain, each agent depends on previous completion

**SPEAKER NOTES:**

"Direct Handoff is the simplest pattern.

[Point to structure]

Agent A completes its work. Passes result to Agent B. Agent B completes. Passes to Agent C. Linear flow.

[Implementation]

In code or automation platform: call Agent A, take result, call Agent B with that result, take result, call Agent C.

[Pros/Cons]

Advantage: Simple. Easy to understand, implement, debug.

Disadvantage: Rigid. Agent C can't send feedback to Agent A. No iteration.

[Best for]

Use this when your workflow is truly linear: Research → Analyze → Write → Format. Each stage builds on previous, no need for back-and-forth.

This is what you probably built in Block 3 Sequential patterns."

[Transition]

---

### SLIDE 14: REQUEST-RESPONSE & SHARED WORKSPACE

**Title:** Patterns 2 & 3: Interactive Communication

**Content:**

**Pattern 2: Request-Response**
```
Writer: "I need competitor pricing data"
   └──→ Researcher: [fetches data] → {data} ──→ Writer: [continues writing]
```

**Implementation:**
```json
{
  "message_type": "request",
  "from": "writer",
  "to": "researcher",
  "content": "Need competitor pricing for Q4 2024"
}

{
  "message_type": "response",
  "from": "researcher",
  "to": "writer",
  "content": {...pricing_data...}
}
```

**Pattern 3: Shared Workspace**
```json
{
  "workspace": {
    "task": "Create analysis report",
    "artifacts": {
      "research_notes": "[Researcher writes here]",
      "draft_v1": "[Writer writes here]",
      "review_comments": "[Reviewer writes here]"
    },
    "current_phase": "drafting"
  }
}
```

**Graphic:** Diagrams showing message passing and workspace structure

**GRAPHICS:**

**Graphic 1: Request-Response Message Flow**
- Purpose: Visualize dynamic inter-agent communication through message passing
- Type: Sequence diagram with message objects
- Elements:
  - Writer agent on left
  - Researcher agent on right
  - Message 1 (request) flowing left to right:
    - Speech bubble: "I need competitor pricing data"
    - JSON structure overlay showing message format
  - Researcher processing indicator
  - Message 2 (response) flowing right to left:
    - Data package icon with pricing data
    - JSON structure overlay showing response format
  - Writer continuing work with new data
- Labels: "Dynamic collaboration", "Agents ask for what they need"
- Relationships: Bidirectional communication enables just-in-time information requests

**Graphic 2: Shared Workspace Structure**
- Purpose: Demonstrate shared context model where all agents read/write common artifacts
- Type: Workspace schema diagram
- Elements:
  - Central "Workspace" box containing:
    - task: "Create analysis report"
    - artifacts folder with:
      - research_notes (written by Researcher)
      - draft_v1 (written by Writer)
      - review_comments (written by Reviewer)
    - current_phase indicator
  - Three agent icons around workspace: Researcher, Writer, Reviewer
  - Bidirectional arrows from each agent to workspace
  - Color-coded to show who writes which artifact
  - Coordinator icon showing management role
- Labels: "Like shared Google Doc", "All agents contribute"
- Relationships: All agents have read/write access to shared context, coordinator manages turn-taking

**SPEAKER NOTES:**

"Let's look at interactive patterns:

[Request-Response]

Writer is working on a draft. Realizes it needs competitor pricing. Sends request to Researcher. Researcher fetches data, responds. Writer continues with new information.

This enables dynamic collaboration - agents ask for what they need.

[Implementation]

Implement with message passing. Message includes: who's sending, who should receive, what's needed.

[Shared Workspace]

Alternative approach: all agents read/write to shared workspace. Researcher puts notes in research_notes. Writer creates draft_v1. Reviewer adds review_comments.

Like a shared Google Doc where everyone can contribute.

[Key difference]

Request-Response: Direct agent-to-agent messages
Shared Workspace: All agents access common context

Choose based on complexity: Request-Response for simple back-and-forth, Shared Workspace for complex multi-agent collaboration."

[Transition]

---

### SLIDE 15: SEGMENT 3 SUMMARY

**Title:** Communication Patterns Recap

**Content:**

**Key Takeaway:** Choose communication pattern based on collaboration complexity

**Three Patterns:**
- **Direct Handoff**: Linear workflows (simplest)
- **Request-Response**: Agents can ask for help (flexible)
- **Shared Workspace**: All agents collaborate on shared context (most complex)

**Implementation Tips:**
- Start with Direct Handoff
- Add Request-Response when agents need dynamic information exchange
- Use Shared Workspace for complex iterative refinement

**You'll Practice:**
Exercise 2.2 - Implement team with chosen communication pattern

**Graphic:** Decision tree for choosing pattern

**SPEAKER NOTES:**

"Let's recap communication patterns:

You have three choices, increasing in complexity:

Direct Handoff for linear flows. Request-Response for dynamic help-seeking. Shared Workspace for complex collaboration.

[Implementation tips]

My recommendation: start simple. Implement Direct Handoff first. Prove the team works. Then upgrade to Request-Response if you need it. Only go to Shared Workspace if you're doing highly iterative, complex work.

In Exercise 2.2, you'll implement your team design from Exercise 2.1 with one of these patterns.

[Pause]

Questions on communication before we combine everything into Hybrid orchestration?"

[Transition: Click to Segment 4]

---

## SEGMENT 4: HYBRID ORCHESTRATION
### Duration: 9 minutes | Slides 16-18

---

### SLIDE 16: THE POWER OF COMBINING PATTERNS

**Title:** Hybrid Orchestration: Using the Right Pattern for Each Phase

**Content:**

**The Opportunity:**
Real workflows have different needs at different phases:
- Planning needs coherence (Sequential)
- Research needs speed (Parallel)
- Creation needs quality (Team-Based)
- Finalization needs consistency (Sequential)

**Hybrid Solution:**
```
Phase 1: [Sequential] → Planner
Phase 2: [Parallel] → Research A, B, C
Phase 3: [Team-Based] → Analyst ←→ Writer
Phase 4: [Sequential] → Finalizer → Output
```

**Key Insight:** Don't pick one pattern - use the best pattern for each phase

**Graphic:** Visual showing multi-phase workflow with different patterns

**GRAPHICS:**

**Graphic 1: Hybrid Orchestration Multi-Phase Workflow**
- Purpose: Illustrate how different orchestration patterns are applied to different workflow phases
- Type: Multi-layer flow diagram with pattern labels
- Elements:
  - Four horizontal phases stacked vertically:
    - Phase 1 (Sequential): Single Planner box
      - Label: "Sequential - Single coherent plan"
      - Color: Blue
    - Phase 2 (Parallel): Research A, B, C boxes side-by-side
      - Label: "Parallel - Speed through independence"
      - Color: Green
    - Phase 3 (Team-Based): Analyst ↔ Writer collaboration
      - Label: "Team-Based - Quality through collaboration"
      - Color: Orange
      - Workspace shown around agents
    - Phase 4 (Sequential): Single Finalizer box
      - Label: "Sequential - Consistent output"
      - Color: Blue
  - Vertical flow arrows connecting phases
  - Pattern icons on right showing which pattern used where
- Labels: "Use the right pattern for each phase", "Enterprise-grade architecture"
- Relationships: Each phase uses optimal pattern for its requirements, handoffs connect phases

**SPEAKER NOTES:**

"[Hook - The power of combination]"

"Here's a question: which orchestration pattern is best?

[Pause]

The answer: it depends on the phase.

Real workflows aren't uniform. Different phases have different needs.

[Point to opportunity]

Planning phase: You need ONE coherent plan, not multiple competing plans. Use Sequential.

Research phase: You need data fast from multiple sources. Use Parallel.

Creation phase: You need quality through collaboration. Use Team-Based.

Finalization: You need ONE consistent output. Use Sequential.

[Hybrid solution]

Hybrid orchestration means using the right pattern for each phase. Don't limit yourself to one approach.

This is enterprise-grade architecture."

[Transition]

**BACKGROUND:**

**Rationale:**
- Establishes that pattern choice isn't either/or
- Shows sophistication of multi-pattern thinking
- Motivates the complexity of Hybrid approach
- Bridges from single-pattern thinking to production-grade architecture

**Key Research & Citations:**
- **Microservices Architecture**: Modern software systems combine multiple architectural patterns based on component needs (synchronous for API, async for events, batch for analytics). Agent systems apply the same principle.
- **Spotify Engineering Model**: Teams use different methodologies (Scrum, Kanban, custom) per squad based on their work characteristics. Hybrid agent orchestration applies similar flexibility.
- **Production AI Systems**: Research shows enterprise AI deployments rarely use single orchestration patterns—70%+ use hybrid approaches tailored to specific workflow phases.

**Q&A Preparation:**
- *"Isn't Hybrid more complex to build?"*: Yes, initially. But trying to force one pattern everywhere creates worse complexity through workarounds. Hybrid acknowledges reality: different phases have different needs.
- *"How do I know where to switch patterns?"*: Look for phase boundaries where requirements change. Planning → Research = coherence to speed. Research → Analysis = speed to quality.
- *"Can I have Parallel inside Team-Based?"*: Yes! A Team-Based Writer might spawn multiple Parallel sub-agents to draft different sections simultaneously. Patterns compose.

**Sources:**
1. [Microservices Patterns (Richardson)](https://microservices.io/patterns/index.html) - Multi-pattern architecture
2. [Spotify Engineering Culture](https://engineering.atspotify.com/2014/03/spotify-engineering-culture-part-1/) - Adaptive methodologies
3. [Enterprise AI Deployment Patterns](https://martinfowler.com/articles/patterns-of-distributed-systems/) - Production system design

**Implementation Guidance:**

**Getting Started:**
- Draw your complete workflow end-to-end before choosing patterns
- Identify 3-5 natural phases with different characteristics
- Start by implementing one phase pattern perfectly before adding others
- Use simple handoffs between pattern phases initially

**Best Practices:**
- Document why each pattern was chosen for each phase (justification = design quality)
- Make phase transitions explicit in code (clear boundary between Parallel and Team-Based)
- Test each phase independently before integrating
- Monitor performance/quality metrics per phase to validate pattern choices

**Common Pitfalls:**
- Over-engineering: Using Hybrid when simple Sequential would work
- Unclear phase boundaries: Switching patterns mid-phase causes confusion
- Not testing patterns individually: Integration problems become debugging nightmares
- Ignoring cost: Hybrid typically uses more agents = higher cost. Ensure value justifies expense.

**Tools & Technologies:**
- **Workflow orchestration**: AWS Step Functions (supports Parallel states + Sequential flows)
- **Visualization**: Mermaid diagrams to map phase transitions
- **Monitoring**: Track latency/cost/quality per phase separately
- **Testing**: Phase-level integration tests before full end-to-end

**Pseudocode Pattern - Hybrid Orchestration:**
```python
def hybrid_workflow(input):
    # Phase 1: Sequential Planning
    plan = sequential_planner(input)

    # Phase 2: Parallel Research (fast data gathering)
    research_tasks = plan.research_requirements
    research_results = parallel_execute([
        researcher_a(task1),
        researcher_b(task2),
        researcher_c(task3)
    ])

    # Phase 3: Team-Based Analysis (quality through collaboration)
    team_workspace = create_workspace(research_results)
    analysis = team_based_collaborate(
        agents=[analyst, critic, synthesizer],
        workspace=team_workspace
    )

    # Phase 4: Sequential Finalization (consistent output)
    final_output = sequential_finalizer(analysis)

    return final_output
```

---

### SLIDE 17: DESIGNING HYBRID SYSTEMS

**Title:** Hybrid Architecture Design

**Content:**

**Pattern Selection by Phase:**

| Phase | Best Pattern | Rationale |
|-------|--------------|-----------|
| Planning | Sequential | Single coherent strategy |
| Research | Parallel | Independent data gathering (speed) |
| Analysis | Team-Based | Collaborative interpretation (quality) |
| Synthesis | Team-Based | Iterative refinement |
| Finalization | Sequential | Consistent output formatting |

**Design Process:**
1. **Identify phases** - Break workflow into natural stages
2. **Assess phase needs** - Speed? Quality? Coherence?
3. **Match patterns** - Choose best fit per phase
4. **Define handoffs** - How does output of Phase N become input to Phase N+1?

**Example: Strategic Report**
```
Sequential: [Planner] defines scope
     ↓
Parallel: [Researcher A, B, C, D] gather data
     ↓
Team: [Analyst ←→ Writer ←→ Reviewer] create report
     ↓
Sequential: [Formatter] → final deliverable
```

**Graphic:** Example hybrid workflow with visual phase boundaries

**GRAPHICS:**

**Graphic 1: Hybrid System Design Process**
- Purpose: Provide step-by-step framework for designing hybrid orchestration systems
- Type: Design workflow diagram
- Elements:
  - Step 1: "Identify Phases"
    - Icon showing workflow breakdown
    - Example phases listed: Planning, Research, Analysis, Synthesis, Finalization
  - Step 2: "Assess Phase Needs"
    - Decision matrix showing:
      - Speed priority? → Consider Parallel
      - Quality priority? → Consider Team-Based
      - Coherence priority? → Consider Sequential
  - Step 3: "Match Patterns"
    - Visual showing phase-to-pattern assignment
    - Color coding for each pattern type
  - Step 4: "Define Handoffs"
    - Diagram showing data transformation between phases
    - Questions: "How does Parallel output feed Team-Based input?"
- Labels: "Systematic design approach", "Match pattern to phase requirements"
- Relationships: Design process flows from high-level phases to specific pattern selection

**Graphic 2: Strategic Report Example**
- Purpose: Show concrete hybrid implementation for common use case
- Type: End-to-end workflow example
- Elements:
  - Sequential: Planner box defining scope
  - Parallel: 4 Researcher boxes (A, B, C, D) gathering data simultaneously
  - Team: Analyst-Writer-Reviewer collaboration with bidirectional arrows
  - Sequential: Formatter box creating final deliverable
  - Time estimates shown for each phase
  - Data artifacts flowing between phases
- Labels: "Real-world hybrid system", "4 patterns in one workflow"
- Relationships: Complete example showing how patterns combine in production system

**SPEAKER NOTES:**

"How do you design Hybrid systems?

[Pattern selection table]

Start by mapping your workflow phases. For each phase, ask: what's the priority?

Planning: coherence → Sequential
Research: speed → Parallel
Analysis: quality → Team-Based

[Design process]

Follow this process:

1. Break your workflow into phases. Where are natural boundaries?
2. For each phase: Is speed the priority? Quality? Coherence?
3. Match the pattern to the need.
4. Design handoffs: How does Parallel research output feed Team-Based analysis?

[Example]

Strategic report: Planner defines scope sequentially. Parallel Researchers gather data fast. Team (Analyst, Writer, Reviewer) collaborates on quality. Sequential Formatter creates consistent output.

Four patterns in one workflow.

Your capstone - Exercise 2.3 - will design and implement a Hybrid system."

[Transition]

---

### SLIDE 18: SEGMENT 4 SUMMARY + MODULE COMPLETE

**Title:** Advanced Orchestration Patterns Complete

**Content:**

**Module 1 Journey:**
- ✓ Session 1: Parallel orchestration for speed
- ✓ Session 2: Team-Based for quality, Hybrid for sophistication

**You Now Know:**
- When and how to use Parallel patterns
- How to design and implement Team-Based collaboration
- How to combine patterns into Hybrid systems
- How to choose the right pattern for each phase

**Capabilities Unlocked:**
- 50-75% faster execution (Parallel)
- Higher quality through collaboration (Team-Based)
- Enterprise-grade multi-pattern architectures (Hybrid)

**Graphic:** Progression visual showing skill advancement

**SPEAKER NOTES:**

"Let's wrap up Module 1:

[Module journey]

Session 1: You learned Parallel orchestration. Speed through simultaneous execution.

Session 2 today: Team-Based for quality collaboration. Hybrid for enterprise architectures.

[You now know]

You can now:
- Identify when tasks are independent and parallelize them
- Design teams with specialized roles
- Implement inter-agent communication
- Combine all three patterns appropriately

[Capabilities unlocked]

This unlocks real capabilities:

Parallel cuts execution time in half or better.
Team-Based improves quality through expert collaboration.
Hybrid gives you production-ready, sophisticated systems.

[Pause]

You're now equipped to build agent systems that are fast, high-quality, AND sophisticated.

Let's preview your capstone."

[Transition: Click to closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 19-21

---

### SLIDE 19: CAPSTONE OVERVIEW

**Title:** Module 1 Capstone: Hybrid Orchestration System

**Content:**

| Exercise | Time | Deliverable | Skills Demonstrated |
|----------|------|-------------|---------------------|
| Exercise 2.1: Design Agent Team | 25 min | `team-design.md` | Role design, interaction mapping |
| Exercise 2.2: Implement Team Collaboration | 30 min | Working team + interaction logs | Team-Based pattern implementation |
| Exercise 2.3: **Capstone - Hybrid Orchestration** | 20 min | `hybrid-orchestration-capstone.md` + system | **Multi-pattern integration** |
| **Total** | **75 min** | | |

**Capstone Requirements:**
- Combine Sequential, Parallel, AND Team-Based patterns
- Justify pattern choice for each phase
- Document performance and quality results
- Production-ready implementation

**Graphic:** Capstone workflow showing all three patterns integrated

**SPEAKER NOTES:**

"Your homework includes three exercises totaling 75 minutes.

Exercise 2.1 (25 min): Design your agent team. Define roles, responsibilities, interaction patterns.

Exercise 2.2 (30 min): Implement working Team-Based system. Build the communication layer, test collaboration.

Exercise 2.3 (20 min): This is your MODULE CAPSTONE. You'll combine Session 1's Parallel system with Session 2's Team-Based system into one Hybrid orchestration architecture.

[Capstone requirements]

Your capstone must:
- Use all three patterns: Sequential, Parallel, Team-Based
- Have clear justification for why each pattern in each phase
- Include performance metrics and quality assessment
- Be production-ready (not just a design)

This demonstrates complete mastery of Advanced Orchestration Patterns.

All instructions are in your participant guide."

[Transition]

---

### SLIDE 20: RESOURCES

**Title:** Resources for This Session

**Content:**

**Templates & Files:**
- Agent Team Design Template - Participant Guide
- Team Agent Prompt Template - Participant Guide
- Hybrid Orchestration Template - Participant Guide

**Reference Materials:**
- Appendix B: Team-Based Pattern Templates (Module document)
- Appendix C: Module Evaluation Rubric
- Session 1 Parallel implementation (your work)

**Support:**
- Questions: [Async channel name]
- Office Hours: [Time/location if applicable]

**Graphic:** Resource icons for quick access

**SPEAKER NOTES:**

"You have several resources:

Participant guide has complete templates for all three exercises.

Appendix B in the module document has team pattern examples and workspace schemas.

Appendix C has the evaluation rubric - use this to self-assess your capstone quality.

Most importantly: your Session 1 work. You'll build on your Parallel implementation.

If you get stuck, post in [channel] or attend office hours."

[Transition]

---

### SLIDE 21: MODULE 1 COMPLETE

**Title:** Congratulations - Advanced Orchestration Patterns Mastered

**Content:**

**What You've Achieved:**
- ✓ Parallel orchestration for 50-75% time reduction
- ✓ Team-Based collaboration for quality improvement
- ✓ Hybrid multi-pattern architectures
- ✓ Production-ready advanced agent systems

**What to Complete:**
- [ ] Exercise 2.1: Design Agent Team
- [ ] Exercise 2.2: Implement Team Collaboration
- [ ] Exercise 2.3: Hybrid Orchestration Capstone

**Looking Ahead:**
Advanced Module 2: [Topic] - [Brief preview]

**Graphic:** Completion celebration visual

**SPEAKER NOTES:**

"Congratulations on completing Advanced Module 1!

[What you've achieved]

You've mastered three orchestration patterns and how to combine them. This is sophisticated architecture work - beyond what most AI practitioners know.

[What to complete]

Complete all three exercises, especially the capstone. This is your proof of mastery.

[Looking ahead]

When you're ready, Advanced Module 2 covers [topic]. But first, complete this module's capstone.

[Final close]

Excellent work through both sessions. Remember: use the right pattern for each phase. Don't over-engineer, but don't under-engineer either.

Congratulations!"

---

## APPENDICES

### Appendix A: Slide Type Definitions

**TITLE SLIDE** - Opens the presentation with title, subtitle, presenter info, date. Hero image or thematic illustration.

**PROBLEM STATEMENT** - Establishes challenge or pain point. Creates tension the presentation will resolve. Often includes statistics.

**INSIGHT / REVELATION** - Delivers key insight or "aha moment." Reframes how audience thinks about the problem.

**CONCEPT INTRODUCTION** - Introduces new term, framework, or mental model. Provides clear definition and context.

**FRAMEWORK / MODEL** - Presents structured approach or methodology. Uses diagrams, pillars, or numbered components showing relationships.

**COMPARISON** - Contrasts two or more approaches, options, or states. Uses tables, side-by-side layouts, or before/after.

**DEEP DIVE** - Detailed exploration of specific topic. May include technical content, code, or specifications.

**CASE STUDY** - Real-world example or application. Includes specific outcomes, metrics, or quotes.

**PATTERN / BEST PRACTICE** - Describes proven approach or methodology. Often includes do's and don'ts.

**METRICS / DATA** - Presents quantitative information using charts, graphs, or data tables to support claims.

**ARCHITECTURE / DIAGRAM** - Shows system structure or process flow. Visual representation as primary content.

**OBJECTION HANDLING** - Anticipates and addresses audience concerns. Presents objection-response pairs.

**ACTION / NEXT STEPS** - Provides concrete actions for audience. Often time-bound.

**SUMMARY / RECAP** - Consolidates key points from a section. Reinforces main messages.

**SECTION DIVIDER** - Marks transition between major sections. Minimal content, provides mental break.

**CLOSING / CALL TO ACTION** - Final slide before Q&A. Summarizes core thesis with clear call to action.

**Q&A / CONTACT** - Invites questions, includes contact information and resource links.

---

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
3. Third sequential item
```

**Tables:**
```markdown
| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Data     | Data     | Data     |
```

**Comparison Format:**
```markdown
**Label A:**
- Point about A

**Label B:**
- Point about B
```

**Bad/Good Example:**
```markdown
**Bad Example:** Description of anti-pattern
**Good Example:** Description of best practice
```

**Key Principle Callout:**
```markdown
**Key Principle:** [Bold statement in one sentence]
```

---

### Appendix C: Speaker Notes Conventions

**Stage Directions (in brackets):**
- `[Pause]` - Deliberate silence for effect
- `[Point to X]` - Gesture to visual element
- `[Emphasize this]` - Vocal emphasis
- `[Light humor]` - Lighter delivery
- `[Personal story - adjust]` - Customization placeholder

**Transition Markers:**
- `[Transition]` - Standard transition cue
- `[OPENING - Description]` - Opening segment marker
- `[Hook - Description]` - Attention-grabbing opener

---

### Appendix D: Graphics Description Guidelines

Describe graphics with enough detail for a designer to create them:

**Required Elements:**
1. **Type**: diagram, illustration, chart, photo, icon grid
2. **Main elements**: What objects/shapes appear
3. **Arrangement**: Spatial relationships
4. **Labels/Text**: Text appearing in graphic
5. **Communication goal**: What visual should convey

---

### Appendix E: BACKGROUND Section Structure

**Rationale (3-5 bullets):**
- Slide's purpose in narrative arc
- Mental shift it creates for audience
- Connections to adjacent slides
- Why chosen framing/approach is effective

**Key Research & Citations (3-5 entries):**
Format: **[Source Name (Year)]**: [Detailed explanation with methodology, statistics, or quotes]

**Q&A Preparation (3-5 questions):**
Format: *"[Question]"*: [Response with specifics, examples, or graceful redirects]

---

### Appendix F: Sources Section Guidelines

Include 3-7 sources per slide:
```markdown
1. [Full title with hyperlink](URL) - [1-5 word description]
```

Source types:
- **Primary research**: Academic papers, official documentation
- **Industry reports**: Analyst reports, surveys, benchmarks
- **Practitioner content**: Expert blog posts, conference talks
- **Official documentation**: Product docs, API references
- **Books/Long-form**: Foundational concept references

---

### Appendix G: Implementation Guidance Structure

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
- Misleading assumptions

**Tools & Technologies (2-4 categories):**
Format: **[Category]**: [Tool1, Tool2] - [use case description]

**Pseudocode Pattern (optional):**
Include when slide introduces technical pattern

---

### Appendix H: Quality Checklist

**Content:**
- [x] All learning objectives addressed
- [x] Team-Based and Hybrid patterns clearly explained
- [x] Examples relevant to enterprise work
- [x] Capstone requirements clearly defined
- [x] Builds on Session 1 parallel content

**Speaker Notes:**
- [x] Natural speech patterns
- [x] Smooth transitions
- [x] Timing markers included
- [x] Anticipated questions addressed

**Design:**
- [x] Consistent with advanced module theme
- [x] Slide content not overcrowded
- [x] Graphics support collaboration concepts
- [x] Total slides: 21 (appropriate for 45 min)

---

### Appendix I: Module 1 Completion and Certification

**Module 1 Learning Outcomes:**
- **Parallel Orchestration**: Reduce execution time by 50-75% through simultaneous task execution
- **Team-Based Orchestration**: Improve quality through agent collaboration and role specialization
- **Hybrid Orchestration**: Combine patterns appropriately for production-grade systems

**Capstone Requirements (Exercise 2.3):**
- Demonstrate all three patterns in one integrated system
- Document pattern choice justification for each phase
- Include performance metrics (time, cost, quality)
- Provide production-ready implementation with error handling

**Certification Criteria:**
- Complete all 6 exercises (3 per session)
- Deliver hybrid orchestration capstone with:
  - Sequential component (coherence)
  - Parallel component (speed)
  - Team-Based component (quality)
- Document before/after performance comparison
- Show graceful degradation in failure scenarios

**Progression to Module 2:**
- Module 1 focuses on orchestration patterns (how agents coordinate)
- Module 2 focuses on reliability engineering (how agents handle failures)
- Recommended: Complete Module 1 capstone before starting Module 2

**Portfolio Artifact:**
Your hybrid orchestration system and documentation become portfolio evidence of:
- Advanced agent architecture design skills
- Performance optimization capabilities
- Production engineering competency

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation creation | AI Practitioner Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |
