# **ADVANCED MODULE 1 SESSION 2: TEAM-BASED ORCHESTRATION & HYBRID PATTERNS**

**Module:** Advanced Module 1 - Advanced Orchestration Patterns
**Session:** 2 of 2
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Session Navigation:** [← Session 1](../session-1/participant-guide.md) | **Session 2** | Advanced Module 1 Complete

**In This Guide:**
- [Learning Objectives](#learning-objectives)
- [Key Concepts](#key-concepts)
- [Workshop Recap](#workshop-recap)
- [Self-Paced Exercises](#self-paced-exercises)
- [Templates & Resources](#templates--resources)
- [Self-Assessment](#self-assessment)
- [Getting Help](#getting-help)

---

## Learning Objectives

By the end of this session, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Design agent teams with specialized roles and clear interaction protocols | Exercise 2.1 |
| 2 | Implement inter-agent communication using handoff, request-response, or workspace patterns | Exercise 2.2 |
| 3 | Combine Sequential, Parallel, and Team-Based patterns into hybrid orchestration systems | Exercise 2.3 (Capstone) |
| 4 | Justify pattern selection based on phase requirements and optimization goals | Exercise 2.3 (Capstone) |

---

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Session 1 exercises (parallel architecture design and implementation)
- [ ] Working parallel orchestration system with result aggregation
- [ ] Performance analysis showing time reduction from parallel execution
- [ ] Understanding of agent specialization principles from Block 3

**Not ready?** Complete Session 1 exercises before proceeding - Session 2 builds directly on that work.

---

## Key Concepts

### Concept 1: Team-Based Orchestration Pattern

**Definition:**
An orchestration pattern where agents with specialized roles collaborate through inter-agent communication and shared workspace, enabling iterative refinement and quality improvement through expertise combination.

**Why It Matters:**
Parallel orchestration optimizes for speed but agents work in isolation. Team-Based enables collaboration like human teams - agents can ask each other questions, review work, iterate on feedback. This improves quality for complex tasks requiring multiple perspectives.

**Core Principle:**
> "When collaboration adds value, use Team-Based orchestration. Agents with distinct expertise working together produce better results than isolated agents or single multi-purpose agents."

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
- Agents have specialized roles (like real team members)
- Inter-agent communication (not just sequential handoffs)
- Shared workspace for artifacts
- Iterative refinement possible
- More complex than Sequential or Parallel

**Common Mistake:**
Treating Team-Based as just "Sequential with multiple agents." The key difference is bidirectional communication and iteration, not just passing results forward.

---

### Concept 2: Agent Role Archetypes

**Definition:**
Standard specialized roles that agents can fulfill in collaborative teams, each with clear responsibilities and boundaries.

**Why It Matters:**
Starting with proven archetypes accelerates team design and ensures clear role boundaries. Better to use standard roles than invent custom ones that overlap.

**Standard Archetypes:**

| Role | Responsibility | Example Tasks | When Needed |
|------|----------------|---------------|-------------|
| **Researcher** | Gather information | Web search, database queries, file reads | Starting point for knowledge work |
| **Analyst** | Process and interpret | Data analysis, pattern finding, insights | Making sense of raw information |
| **Creator** | Generate content | Writing, designing, modeling | Producing deliverables |
| **Critic** | Evaluate quality | Review, scoring, validation | Quality assurance |
| **Editor** | Refine and polish | Revision, formatting, optimization | Final refinement |
| **Coordinator** | Manage workflow | Task assignment, tracking, decisions | Only for 5+ agent teams |

**Design Principle:**
> "Each role should have clear, non-overlapping responsibilities. If two roles do similar work, combine them into one agent."

**Common Mistake:**
Creating too many roles. Most effective teams have 3-4 agents. Beyond 5, coordination complexity outweighs collaboration benefits.

---

### Concept 3: Inter-Agent Communication Patterns

**Definition:**
Mechanisms by which agents exchange information and coordinate work in Team-Based orchestration.

**Three Communication Patterns:**

**1. Direct Handoff (Simplest)**
```
Agent A completes work → passes result → Agent B begins work
```
- Good for: Linear workflows with clear stages
- Pros: Simple, easy to debug
- Cons: No back-and-forth, rigid flow

**2. Request-Response (Flexible)**
```
Agent A: "I need data about X"
  └──→ Agent B: [fetches data] → {data}
       └──→ Agent A: [continues with data]
```
- Good for: Agents need to ask for specific information
- Pros: Dynamic, flexible collaboration
- Cons: More complex coordination

**3. Shared Workspace (Most Collaborative)**
```json
{
  "workspace": {
    "task_id": "report-123",
    "artifacts": {
      "research_notes": "[Researcher writes here]",
      "draft_v1": "[Writer writes here]",
      "review_comments": "[Reviewer writes here]"
    }
  }
}
```
- Good for: Complex iterative collaboration
- Pros: All agents access common context
- Cons: Requires coordination layer for turn-taking

**Choosing Your Pattern:**
- Simple linear workflow → Direct Handoff
- Agents need to request help → Request-Response
- Complex back-and-forth collaboration → Shared Workspace

---

### Concept 4: Hybrid Orchestration

**Definition:**
Architecture pattern that combines Sequential, Parallel, and Team-Based orchestration, applying the most appropriate pattern to each phase based on that phase's optimization goals.

**Why It Matters:**
Real workflows aren't uniform. Different phases have different priorities. Planning needs coherence (Sequential). Research needs speed (Parallel). Creation needs quality (Team-Based). Hybrid applies the right pattern where it fits.

**Core Principle:**
> "Don't ask 'which pattern is best?' Ask 'which pattern is best for THIS phase?' Use Sequential when coherence matters, Parallel when speed matters, Team-Based when quality through collaboration matters."

**Example Architecture:**
```
Phase 1 - Sequential:
  [Input] → [Planner] creates strategy
              ↓
Phase 2 - Parallel:
       ┌── [Researcher A] ──┐
       ├── [Researcher B] ──┤ Gather data fast
       └── [Researcher C] ──┘
              ↓
Phase 3 - Team-Based:
  [Analyst] ←→ [Writer] ←→ [Reviewer] Collaborate on quality
              ↓
Phase 4 - Sequential:
       [Finalizer] → [Output] Single consistent format
```

**Pattern Selection Matrix:**

| Phase Type | Best Pattern | Rationale |
|------------|--------------|-----------|
| Planning | Sequential | Need single coherent strategy |
| Research | Parallel | Independent data gathering (speed) |
| Analysis | Team-Based | Multiple perspectives improve insights |
| Synthesis | Team-Based | Iterative refinement improves quality |
| Finalization | Sequential | Need consistent output format |

**Common Mistake:**
Using Hybrid everywhere. If your entire workflow prioritizes speed, just use Parallel. If it all requires collaboration, just use Team-Based. Use Hybrid only when different phases have different optimization goals.

---

### Quick Reference: Pattern Selection Guide

| Goal | Best Pattern | When to Use |
|------|--------------|-------------|
| **Speed** | Parallel | Tasks are independent, time reduction critical |
| **Quality through collaboration** | Team-Based | Multiple perspectives or iteration improves output |
| **Coherence** | Sequential | Need single voice, consistent approach |
| **Different goals per phase** | Hybrid | Planning needs coherence, research needs speed, etc. |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Team-Based orchestration for collaborative quality improvement + Hybrid patterns combining all orchestration types

**Key Points from Each Segment:**

**Segment 1: Team-Based Pattern Fundamentals**
- Parallel is fast but isolated - agents can't collaborate
- Team-Based enables back-and-forth communication and iteration
- Use Team-Based when collaboration improves quality (not just when tasks have dependencies)
- More complex than Parallel - trade-off is complexity vs quality

**Segment 2: Designing Agent Teams**
- Six role archetypes: Researcher, Analyst, Creator, Critic, Editor, Coordinator
- Most teams need 3-4 agents (not all 6 roles)
- Three team structures: Linear (simple handoffs), Collaborative (multiple perspectives), Parallel+Team Hybrid
- Team agent prompts include teammate awareness and collaboration guidelines

**Segment 3: Inter-Agent Communication**
- Three communication patterns increasing in complexity:
  - Direct Handoff: Simple sequential passing
  - Request-Response: Agents can ask each other for information
  - Shared Workspace: All agents read/write common context
- Choose based on collaboration complexity needs
- Start simple (Handoff), upgrade only if needed

**Segment 4: Hybrid Orchestration**
- Real workflows have phases with different priorities
- Apply appropriate pattern per phase: Sequential for coherence, Parallel for speed, Team-Based for quality
- Design process: Identify phases → Assess needs → Match patterns → Define handoffs
- Use Hybrid only when phases have different optimization goals (not everywhere)

### Demo Recap

**What Was Demonstrated:**
Team-Based orchestration showing Writer agent requesting data from Researcher agent via Request-Response pattern, plus Shared Workspace with artifacts from multiple agents

**Key Steps:**
1. Writer agent begins drafting content
2. Writer realizes it needs market statistics, sends request message to Researcher
3. Researcher receives request, fetches data, sends response
4. Writer continues with received data
5. Alternative shown: Shared workspace where Researcher writes research_notes, Writer creates draft_v1, Reviewer adds review_comments

**Result:**
Agents collaborating dynamically (not just sequential handoffs) - Writer gets data when needed, enabling quality improvement through specialized expertise

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 2.1 | 25 min | `team-design.md` | Team architecture, role design |
| 2.2 | 30 min | Working team + interaction logs | Team-Based implementation |
| 2.3 (CAPSTONE) | 20 min | `hybrid-orchestration-capstone.md` | **Module completion** |

**Important:** Exercise 2.3 is your MODULE 1 CAPSTONE. It demonstrates mastery of all orchestration patterns and completes Advanced Module 1.

---

### Exercise 2.1: Design Agent Team

**Duration:** 25 minutes

**Purpose:**
Design a collaborative agent team for your use case, defining specialized roles, interaction patterns, and workflow phases using Team-Based orchestration principles.

**You Will Create:**
`team-design.md` - Complete team architecture design document

---

#### Instructions

**Step 1: Define Team Purpose**

Identify the problem your team will solve:

```markdown
# Agent Team Design

## Team Purpose

**Problem to Solve:** [What complex task requires team collaboration?]

**Why Team-Based:** [Why does this need collaboration vs Parallel or Sequential?]

**Expected Outcome:** [What should the team produce?]

**Quality Improvement Through Collaboration:** [How does team interaction improve quality?]
```

**Step 2: Choose Team Roles**

Select 3-4 roles from archetypes (Researcher, Analyst, Creator, Critic, Editor, Coordinator):

```markdown
## Team Composition

### Agent 1: [Role Name]
- **Role Archetype:** [Which of the 6 archetypes]
- **Expertise:** [Specific specialization]
- **Responsibilities:**
  - [Specific duty 1]
  - [Specific duty 2]
  - [Specific duty 3]
- **Interacts with:** [Which other agents]
- **Inputs:** [What this agent needs to start work]
- **Outputs:** [What this agent produces]
- **Tools/MCP:** [Any tools or MCP servers this agent uses]

### Agent 2: [Role Name]
[Repeat structure]

### Agent 3: [Role Name]
[Repeat structure]

### Agent 4: [Role Name] (if needed)
[Repeat structure]
```

**Step 3: Map Interactions**

Create interaction map showing communication flows:

```markdown
## Interaction Map

```
[Agent 1: Researcher] ──request data──→ [Agent 2: Analyst]
         ↓                                      ↓
         └────────→ [Agent 3: Writer] ←────────┘
                            ↓
                   [Agent 4: Reviewer]
                            ↓
                        [Output]
```

**Key:**
- `──→` Direct handoff
- `←──→` Bidirectional communication
- Arrows show information flow direction
```

**Step 4: Design Shared Workspace**

Define workspace schema for team artifacts:

```markdown
## Shared Workspace Schema

```json
{
  "workspace_id": "team-workspace-001",
  "task": {
    "goal": "[What team is working on]",
    "requirements": ["requirement 1", "requirement 2"],
    "constraints": ["constraint 1"]
  },
  "artifacts": {
    "research_data": null,      // Agent 1 writes here
    "analysis_results": null,   // Agent 2 writes here
    "draft_content": null,      // Agent 3 writes here
    "review_feedback": null     // Agent 4 writes here
  },
  "status": {
    "current_phase": "research",
    "current_agent": "researcher",
    "iteration": 1
  },
  "communication_log": []
}
```
```

**Step 5: Define Workflow Phases**

Break team workflow into phases:

```markdown
## Workflow Phases

### Phase 1: [Phase Name - e.g., Research]
- **Active Agents:** [Which agents work in this phase]
- **Activities:** [What happens]
- **Output:** [What this phase produces]
- **Duration:** [Expected time]

### Phase 2: [Phase Name - e.g., Analysis]
- **Active Agents:** [Which agents]
- **Activities:** [What happens]
- **Interactions:** [How agents collaborate]
- **Output:** [What this phase produces]
- **Duration:** [Expected time]

### Phase 3: [Phase Name - e.g., Creation]
[Repeat structure]

### Phase 4: [Phase Name - e.g., Review]
[Repeat structure]

## Coordination Rules

**Turn-Taking:** [How is it determined which agent acts when?]
- Example: "Sequential phases - Researcher completes before Analyst starts"
- Example: "Coordinator assigns tasks based on agent availability"

**Conflict Resolution:** [What happens if agents disagree?]
- Example: "Reviewer feedback sent back to Writer for revision"
- Example: "Coordinator makes final decision if Analyst and Critic disagree"

**Completion Criteria:** [When is team done?]
- Example: "Reviewer approves draft with score ≥8/10"
- Example: "All required artifacts present in workspace"
```

**Step 6: Choose Communication Pattern**

Select and document communication approach:

```markdown
## Communication Pattern

**Chosen Pattern:** [Direct Handoff / Request-Response / Shared Workspace]

**Rationale:** [Why this pattern fits team needs]

**Implementation:**
[Brief description of how agents will communicate]

**Example Interaction:**
```json
// Example message or workspace update
{
  "from": "writer",
  "to": "researcher",
  "type": "request",
  "content": "Need competitor pricing data for Q4 2024"
}
```
```

**Step 7: Review Your Work**

Verify design completeness:
- [ ] Team has 3-4 agents with clear roles
- [ ] Each role has specific, non-overlapping responsibilities
- [ ] Interaction map shows communication flows
- [ ] Shared workspace schema appropriate for use case
- [ ] Workflow phases defined with clear activities
- [ ] Communication pattern chosen with justification

---

#### Deliverable Specification

**File Name:** `team-design.md`

**Location:** Your project documentation folder or GitHub repository

**Format Requirements:**
- Markdown format
- All sections from template completed
- Interaction map drawn in ASCII or described clearly
- Specific to YOUR use case (not generic example)

**Quality Criteria:**
- [ ] Roles are specialized (no overlapping responsibilities)
- [ ] Team size is reasonable (3-4 agents, not 6+)
- [ ] Communication pattern matches team complexity
- [ ] Workspace schema includes all necessary artifacts
- [ ] Collaboration adds clear value (not just Sequential rebranded)

---

#### Example

**Scenario:** Strategic report creation requiring research, analysis, and quality review

**Output:**
```markdown
# Agent Team Design

## Team Purpose

**Problem to Solve:** Create strategic market reports requiring expert research, analytical insights, compelling writing, and quality validation

**Why Team-Based:** Collaboration improves quality - Researcher provides data, Analyst finds patterns, Writer creates narrative, Reviewer ensures standards. Iteration between Writer and Reviewer improves final product.

**Expected Outcome:** High-quality strategic report with research-backed insights and professional presentation

## Team Composition

### Agent 1: Market Researcher
- **Role Archetype:** Researcher
- **Expertise:** Market data gathering, competitor intelligence
- **Responsibilities:**
  - Search web for market trends
  - Gather competitor information
  - Compile industry statistics
- **Interacts with:** Analyst, Writer (provides data on request)
- **Inputs:** Report topic, key competitors list
- **Outputs:** Research summary with sources
- **Tools:** Web search MCP, database access

### Agent 2: Data Analyst
- **Role Archetype:** Analyst
- **Expertise:** Pattern recognition, data interpretation
- **Responsibilities:**
  - Analyze research data for patterns
  - Identify key insights
  - Create data visualizations
- **Interacts with:** Researcher (requests clarification), Writer (provides insights)
- **Inputs:** Research summary from Researcher
- **Outputs:** Analysis findings, key insights
- **Tools:** Data analysis tools

### Agent 3: Content Writer
- **Role Archetype:** Creator
- **Expertise:** Strategic narrative, business writing
- **Responsibilities:**
  - Draft report structure
  - Write compelling narrative
  - Incorporate research and analysis
- **Interacts with:** Analyst (gets insights), Reviewer (receives feedback)
- **Inputs:** Research summary, analysis findings
- **Outputs:** Report draft
- **Tools:** Writing templates

### Agent 4: Quality Reviewer
- **Role Archetype:** Critic
- **Expertise:** Quality assessment, standards validation
- **Responsibilities:**
  - Review draft for quality
  - Score against rubric
  - Provide revision feedback
- **Interacts with:** Writer (sends feedback)
- **Inputs:** Report draft from Writer
- **Outputs:** Quality score, feedback for revision
- **Tools:** Quality rubric

## Interaction Map

```
[Researcher] ──research data──→ [Analyst]
      ↓                             ↓
      └────data on request─────→ [Writer] ←──feedback──┐
                                    ↓                   │
                               [Reviewer] ──────────────┘
                                    ↓
                               [Final Report]
```

## Shared Workspace Schema

```json
{
  "workspace_id": "strategic-report-workspace",
  "task": {
    "goal": "Create Q1 2026 market analysis report",
    "requirements": [
      "5-10 pages",
      "3+ data sources",
      "Competitor comparison",
      "Quality score ≥8/10"
    ]
  },
  "artifacts": {
    "research_summary": null,
    "analysis_findings": null,
    "report_draft_v1": null,
    "review_feedback": null,
    "report_draft_v2": null,
    "final_report": null
  },
  "status": {
    "current_phase": "research",
    "iteration": 1
  }
}
```

## Workflow Phases

### Phase 1: Research
- **Active Agents:** Researcher
- **Activities:** Gather market data, competitor info, industry statistics
- **Output:** Research summary in workspace
- **Duration:** ~5 minutes

### Phase 2: Analysis
- **Active Agents:** Analyst
- **Activities:** Analyze research, identify patterns, create insights
- **Interactions:** May request clarification from Researcher
- **Output:** Analysis findings in workspace
- **Duration:** ~3 minutes

### Phase 3: Drafting
- **Active Agents:** Writer
- **Activities:** Create report structure, write narrative using research and analysis
- **Interactions:** Accesses research and analysis from workspace
- **Output:** Report draft_v1 in workspace
- **Duration:** ~4 minutes

### Phase 4: Review & Iteration
- **Active Agents:** Reviewer, Writer
- **Activities:** Reviewer scores draft, provides feedback. If score <8, Writer revises.
- **Interactions:** Reviewer → Writer feedback, Writer → Reviewer revised draft
- **Output:** Final report when score ≥8/10
- **Duration:** ~3 minutes (may iterate)

## Coordination Rules

**Turn-Taking:** Sequential phases - each agent completes before next starts, EXCEPT review phase allows iteration

**Conflict Resolution:** Reviewer's quality score determines if iteration needed. Writer must address feedback until score ≥8.

**Completion Criteria:** Final report in workspace with Reviewer score ≥8/10

## Communication Pattern

**Chosen Pattern:** Shared Workspace with selective Request-Response

**Rationale:** Shared workspace allows all agents to access artifacts. Request-Response used when Writer needs Researcher clarification during drafting.

**Implementation:** All agents read/write to workspace artifacts. Workspace status tracks current phase and iteration count.
```

**Why This Works:**
- Four distinct, non-overlapping roles
- Clear interaction flows showing collaboration
- Workspace schema captures all artifacts
- Iteration between Writer and Reviewer improves quality
- Communication pattern appropriate for team complexity

---

#### Tips & Troubleshooting

**Tips:**
- Start with 3 agents - prove team works before adding 4th
- Choose Direct Handoff communication first - upgrade to Request-Response only if needed
- Define completion criteria clearly (prevents endless iteration)
- Keep workspace schema simple initially

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Roles overlap (e.g., Researcher and Analyst doing similar work) | Combine into one agent or clearly separate: Researcher = gather, Analyst = interpret |
| Can't identify collaborative value | Ask: Does Agent B's review improve Agent A's work? If no, don't use Team-Based |
| Too many agents (5+) | Reduce to core 3-4 - additional agents add more complexity than value |
| Unclear when team is done | Define specific completion criteria: quality score threshold, checklist, time limit |

---

### Exercise 2.2: Implement Team Collaboration

**Duration:** 30 minutes

**Purpose:**
Build working Team-Based orchestration system implementing your Exercise 2.1 design, with functional inter-agent communication and shared workspace.

**You Will Create:**
- Working team implementation in your automation platform
- Agent prompts with team awareness
- Communication/workspace infrastructure
- Test execution logs showing team collaboration

---

#### Instructions

**Step 1: Create Team-Aware Agent Prompts**

For each agent in your team design, create enhanced prompt with team awareness:

```markdown
# Team Agent System Prompts

## Agent 1: [Role Name]

### System Prompt

```
You are the [ROLE NAME] on a team working to [TEAM GOAL].

## Your Role
[Description of this agent's expertise and focus]

## Your Teammates
- **[Teammate 1 Role]**: [What they do, when to rely on them]
  - Ask them when you need: [specific information]
- **[Teammate 2 Role]**: [What they do, when you pass work to them]
  - Hand off to them when: [completion condition]

## Your Responsibilities
1. [Primary responsibility]
2. [Secondary responsibility]
3. [Tertiary responsibility]

## Collaboration Guidelines
- **When you need [X]**: Request from [Role]
- **When you complete [Y]**: Pass result to [Role] by writing to workspace artifact: [artifact_name]
- **Before starting**: Check workspace for [prerequisite artifact]

## Communication Format

When requesting information from teammate:
```json
{
  "to": "[role]",
  "type": "request",
  "content": "[what you need]"
}
```

When passing work to next teammate:
```json
{
  "to": "[role]",
  "type": "handoff",
  "artifact": "[workspace artifact name]",
  "content": "[your output]"
}
```

## Shared Workspace Access

Read from: `workspace.artifacts.[input_artifact]`
Write to: `workspace.artifacts.[output_artifact]`

## Quality Standards
[Any quality criteria this agent must meet]

## Example Input/Output
[One concrete example of input and expected output]
```
```

Repeat for each agent (2.1 design had 3-4 agents).

**Step 2: Implement Communication Infrastructure**

Choose and implement your communication pattern from Exercise 2.1:

**Option A: Direct Handoff**
```markdown
# Direct Handoff Implementation

## Orchestrator Logic
```python
# Pseudocode for Direct Handoff
workspace = initialize_workspace(task_details)

# Phase 1
result_1 = call_agent_1(input, workspace)
workspace.artifacts.agent_1_output = result_1

# Phase 2
result_2 = call_agent_2(result_1, workspace)
workspace.artifacts.agent_2_output = result_2

# Phase 3
result_3 = call_agent_3(result_2, workspace)
workspace.artifacts.agent_3_output = result_3

return result_3
```

**Platform-Specific:**
- **Make**: Sequential modules, each calls one agent
- **n8n**: Sequential nodes with workspace data passed through
- **Custom**: Function calls with results passed as parameters
```

**Option B: Request-Response**
```markdown
# Request-Response Implementation

## Message Router

```python
# Pseudocode for Request-Response
def route_message(message, agents):
    target_agent = message.to
    response = call_agent(target_agent, message.content)
    return response

# Main orchestration
workspace = initialize_workspace(task_details)

# Agents can request help
result = call_agent_with_router(
    "agent_3",
    input,
    workspace,
    router=route_message
)
```

**Implementation:**
- Set up message passing mechanism (webhooks, API calls, function parameters)
- Agent prompts include how to format requests
- Router directs messages to appropriate agents
```

**Option C: Shared Workspace**
```markdown
# Shared Workspace Implementation

## Workspace Data Structure

```json
{
  "workspace_id": "unique-id",
  "task": {...},
  "artifacts": {
    "artifact_1": null,
    "artifact_2": null,
    "artifact_3": null
  },
  "status": {
    "current_agent": null,
    "phase": null
  }
}
```

## Access Pattern

All agents receive workspace reference.
Each agent:
1. Reads prerequisite artifacts
2. Performs work
3. Writes output to designated artifact
4. Updates status
```

**Platform-Specific:**
- **Make**: Data Store module
- **n8n**: Database or Google Sheets
- **Custom**: Dictionary object or database table
```

**Step 3: Implement Team Workflow**

Build orchestration logic executing your Exercise 2.1 workflow phases:

```markdown
# Team Workflow Implementation

## Platform: [Make/n8n/Python/JavaScript]

## Setup

[Description of how scenario/workflow is configured]

## Execution Flow

1. **Initialize**: Create workspace with task details
2. **Phase 1**: Call [Agent 1]
   - Input: [from task]
   - Output: [to workspace.artifact_1]
3. **Phase 2**: Call [Agent 2]
   - Input: [from workspace.artifact_1]
   - Output: [to workspace.artifact_2]
4. **Phase 3**: Call [Agent 3] + [Agent 4] (if iterative)
   - Interaction: [description of collaboration]
   - Output: [to workspace.final_artifact]
5. **Finalize**: Return workspace.final_artifact

## Code/Configuration

[Platform-specific implementation details or code snippet]
```

**Step 4: Test Team Execution**

Run at least 3 complete team workflows:

```markdown
# Team Execution Test Results

## Test 1: Full Success

**Input:** [Test case description]

**Execution Log:**
```
[Timestamp] Agent 1 (Researcher) started
[Timestamp] Agent 1 completed - wrote to workspace.research_data
[Timestamp] Agent 2 (Analyst) started - read workspace.research_data
[Timestamp] Agent 2 completed - wrote to workspace.analysis
[Timestamp] Agent 3 (Writer) started - read analysis
[Timestamp] Agent 3 completed - wrote to workspace.draft_v1
[Timestamp] Agent 4 (Reviewer) started - read draft_v1
[Timestamp] Agent 4 completed - score: 9/10
[Timestamp] Team workflow complete
```

**Total Duration:** X seconds

**Output Quality:** [Assessment of final output]

**Collaboration Evidence:**
- Agent 2 successfully used Agent 1's research
- Agent 3 incorporated analysis from Agent 2
- Agent 4 provided quality validation

## Test 2: Iteration Required

[Similar format showing Reviewer feedback → Writer revision cycle]

## Test 3: [Another scenario]

[Similar format]

## Summary

**Total Tests:** 3
**Successful Completions:** 3
**Average Duration:** X seconds
**Collaboration Functioning:** Yes/No
**Quality Improvement Visible:** [Evidence that team collaboration improved quality]
```

**Step 5: Document Implementation**

Create comprehensive documentation:

```markdown
# Team-Based Implementation Documentation

## Team Architecture Implemented

**Agents:** [List with roles]
**Communication Pattern:** [Which pattern used]
**Platform:** [Make/n8n/Python/etc]

## Agent Prompts

[Include actual prompts for each agent - see Step 1]

## Infrastructure

**Workspace Storage:** [How workspace is stored - data store, database, memory]
**Message Passing:** [How agents communicate - if applicable]
**Coordination Logic:** [How turn-taking is managed]

## Workflow Phases

[Actual implementation of phases from Exercise 2.1]

## Test Results

[From Step 4]

## Lessons Learned

1. [What worked well]
2. [What was challenging]
3. [What would you change]

## Collaboration Value

**Quality with Team vs Single Agent:**
[Evidence that team collaboration improved output quality]
```

**Step 6: Review Your Work**

Verify implementation completeness:
- [ ] 3+ test executions completed successfully
- [ ] Agents actually communicate (not just sequential)
- [ ] Evidence of collaboration improving quality
- [ ] All agents use team-aware prompts
- [ ] Workspace or communication infrastructure functioning
- [ ] Documentation complete with implementation details

---

#### Deliverable Specification

**File Name:** `team-implementation.md` + platform workspace/code

**Location:** Documentation folder + link to platform scenario or code repository

**Format Requirements:**
- Implementation documentation in markdown
- Agent prompts included
- Test execution logs
- Platform workspace accessible (screenshot or share link)
- Code committed to repository if custom implementation

**Quality Criteria:**
- [ ] Team actually collaborates (evidence of inter-agent communication)
- [ ] Quality improvement through team interaction visible
- [ ] 3+ successful test executions
- [ ] Clear documentation of how team was implemented
- [ ] Agent prompts show team awareness

---

### Exercise 2.3: Module Capstone - Hybrid Orchestration

**Duration:** 20 minutes (design/documentation - implementation may extend)

**Purpose:**
**This is your Advanced Module 1 Capstone.** Design and document a Hybrid orchestration system combining Sequential, Parallel (from Session 1), and Team-Based (from Exercise 2.2) patterns into one sophisticated multi-pattern architecture.

**You Will Create:**
`hybrid-orchestration-capstone.md` - Complete hybrid system design with implementation summary and performance analysis

**This exercise demonstrates MODULE COMPLETION - not just session completion.**

---

#### Instructions

**Step 1: Design Hybrid Architecture**

Identify phases in your workflow and select appropriate pattern per phase:

```markdown
# Hybrid Orchestration Capstone

## System Overview

**Business Problem:** [What real problem does this system solve?]

**Why Hybrid:** [Why does this workflow need multiple patterns?]

**Patterns Used:**
- [ ] Sequential (for [phases])
- [ ] Parallel (for [phases])
- [ ] Team-Based (for [phases])

## Architecture

### Visual Workflow

```
[Phase 1 - Sequential]
Input → [Planner Agent] Creates strategy
           ↓
[Phase 2 - Parallel]  (Session 1 work)
    ┌── [Agent A: Topic 1] ──┐
    ├── [Agent B: Topic 2] ──┤  Gather data fast
    └── [Agent C: Topic 3] ──┘
           ↓
    [Aggregator: Merge All]
           ↓
[Phase 3 - Team-Based]  (Session 2 work)
  [Analyst] ←→ [Writer] ←→ [Reviewer]  Collaborate on quality
           ↓
[Phase 4 - Sequential]
    [Formatter] → [Output]
```

### Phase Breakdown

**Phase 1: [Name] - Sequential**
- **Duration:** X min
- **Agents:** [List]
- **Why Sequential:** [Rationale - e.g., "Need single coherent strategy"]
- **Input:** [What triggers this phase]
- **Output:** [What this phase produces]

**Phase 2: [Name] - Parallel**
- **Duration:** Y min (slowest agent, not sum)
- **Agents:** [List - from Session 1 parallel implementation]
- **Why Parallel:** [Rationale - e.g., "Independent data gathering, speed critical"]
- **Aggregation:** [Strategy used]
- **Input:** [From Phase 1]
- **Output:** [Aggregated results]

**Phase 3: [Name] - Team-Based**
- **Duration:** Z min
- **Agents:** [List - from Exercise 2.2 team]
- **Why Team-Based:** [Rationale - e.g., "Collaboration improves quality"]
- **Interaction:** [How agents collaborate]
- **Input:** [From Phase 2]
- **Output:** [High-quality deliverable]

**Phase 4: [Name] - Sequential**
- **Duration:** A min
- **Agents:** [List]
- **Why Sequential:** [Rationale - e.g., "Need consistent output format"]
- **Input:** [From Phase 3]
- **Output:** [Final system output]
```

**Step 2: Justify Pattern Selection**

For each phase, explain why that pattern is optimal:

```markdown
## Pattern Usage Justification

| Phase | Pattern | Optimization Goal | Why This Pattern | Alternative Considered |
|-------|---------|-------------------|------------------|------------------------|
| Planning | Sequential | Coherence | Need single unified strategy, not multiple competing plans | N/A - no alternative makes sense |
| Research | Parallel | Speed | 3 independent data sources, reduce 9 min to 3 min (67% faster) | Sequential too slow, Team-Based unnecessary for independent tasks |
| Creation | Team-Based | Quality | Writer + Reviewer iteration improves quality score from 6/10 to 9/10 | Sequential = no review, Parallel = isolated creation (lower quality) |
| Finalization | Sequential | Consistency | Need single consistent output format | N/A - formatting is inherently sequential |

### Key Trade-Offs

**Speed vs Quality:**
- Parallel Phase 2 prioritizes speed (3 min vs 9 min)
- Team-Based Phase 3 prioritizes quality over speed (slower but higher quality)

**Complexity vs Value:**
- Hybrid adds coordination complexity between phases
- Justified by: [specific value - e.g., "67% faster + 50% quality improvement"]
```

**Step 3: Implementation Summary**

Document how you implemented the hybrid system:

```markdown
## Implementation Summary

### Platform
[Make/n8n/Python/JavaScript/Mixed]

### Total Agents
- **Sequential Agents:** [N]
- **Parallel Agents:** [M]
- **Team Agents:** [P]
- **Total:** [N+M+P]

### Parallel Groups
[From Session 1 - reference your parallel implementation]

### Team Interactions
[From Exercise 2.2 - reference your team implementation]

### Phase Handoffs

**Phase 1 → Phase 2:**
[How Sequential output becomes Parallel input]

**Phase 2 → Phase 3:**
[How Parallel aggregated results become Team-Based input]

**Phase 3 → Phase 4:**
[How Team-Based output becomes Sequential input]

### Technical Implementation

**Infrastructure:**
- Workspace: [Where shared data is stored]
- Message Passing: [How agents communicate]
- Orchestration: [How phases are triggered and coordinated]

**Code/Configuration:**
[High-level description or link to implementation]
```

**Step 4: Performance Analysis**

Compare hybrid system to single-pattern approaches:

```markdown
## Performance Results

### Test Conditions
- **Test Cases:** [Number executed]
- **Input Type:** [Description]
- **Success Rate:** X%

### Timing Analysis

| Metric | Sequential Only | Parallel Only | Team Only | Hybrid | Best |
|--------|----------------|---------------|-----------|--------|------|
| Total Duration | 15 min | 5 min | 12 min | 8 min | Hybrid |
| Quality Score | 6/10 | 5/10 | 9/10 | 9/10 | Team/Hybrid |
| Cost | $0.50 | $0.50 | $0.75 | $0.65 | Parallel |
| Complexity | Low | Medium | High | Very High | Sequential |

### Hybrid Performance Details

**By Phase:**
| Phase | Pattern | Duration | Cost | Notes |
|-------|---------|----------|------|-------|
| 1 - Planning | Sequential | 1 min | $0.05 | Single planner agent |
| 2 - Research | Parallel | 3 min | $0.30 | 3 agents simultaneously (vs 9 min sequential) |
| 3 - Creation | Team-Based | 3 min | $0.25 | Analyst + Writer + Reviewer iteration |
| 4 - Finalization | Sequential | 1 min | $0.05 | Single formatter agent |
| **Total** | **Hybrid** | **8 min** | **$0.65** | |

### Quality Analysis

**Quality Improvement Evidence:**
- Team-Based Phase 3 (Analyst + Writer + Reviewer) produces score: 9/10
- Comparable Sequential approach produces score: 6/10
- **Quality improvement: +50%**

**Quality vs Speed Trade-off:**
- Hybrid takes 8 min (vs 5 min pure Parallel)
- But achieves 9/10 quality (vs 5/10 pure Parallel)
- **Trade-off accepted:** Slightly slower, much higher quality
```

**Step 5: Comparison & Conclusion**

Synthesize findings:

```markdown
## Comparison to Single-Pattern Approaches

| Approach | Time | Quality | Cost | Complexity | Use When |
|----------|------|---------|------|------------|----------|
| Sequential only | 15 min | 6/10 | $0.50 | Low | Simple workflows, learning/prototyping |
| Parallel only | 5 min | 5/10 | $0.50 | Medium | Speed critical, quality secondary |
| Team-Based only | 12 min | 9/10 | $0.75 | High | Quality critical, time flexible |
| **Hybrid** | **8 min** | **9/10** | **$0.65** | **Very High** | **Production workflows needing both speed AND quality** |

### Improvement Metrics

**vs Sequential:**
- Time: 47% faster (15 min → 8 min)
- Quality: 50% better (6/10 → 9/10)
- Cost: 30% higher ($0.50 → $0.65)

**vs Parallel:**
- Time: 60% slower (5 min → 8 min)
- Quality: 80% better (5/10 → 9/10)
- Cost: 30% higher ($0.50 → $0.65)

**vs Team-Based:**
- Time: 33% faster (12 min → 8 min)
- Quality: Same (9/10 → 9/10)
- Cost: 13% lower ($0.75 → $0.65)

### Conclusion

**Best Single-Pattern Alternative:** [Team-Based or Parallel, with rationale]

**Why Hybrid Wins:**
[Specific justification for your use case]

**Hybrid Value Proposition:**
[Clear statement of when to use Hybrid vs single patterns]

## Lessons Learned

### What Worked Well
1. [Lesson about successful aspect]
2. [Lesson about pattern combination]
3. [Lesson about implementation]

### Challenges Encountered
1. [Challenge and how solved]
2. [Challenge and workaround]

### Recommendations for Future Implementations
1. [Advice for next hybrid system]
2. [Pattern selection guidance]
3. [Implementation best practice]

### Module 1 Synthesis

**Key Takeaway from Session 1 (Parallel):**
[Your main learning about parallel orchestration]

**Key Takeaway from Session 2 (Team-Based):**
[Your main learning about team collaboration]

**Key Takeaway from Hybrid Integration:**
[Your main learning about combining patterns]

**Overall Module Mastery:**
[Reflection on advancement from Block 3 sequential to advanced multi-pattern architectures]
```

**Step 6: Review Your Work**

Verify capstone completeness (this is MODULE completion criteria):
- [ ] Uses at least 2 patterns (ideally all 3: Sequential, Parallel, Team-Based)
- [ ] Clear justification for each pattern per phase
- [ ] Performance analysis comparing approaches
- [ ] Implementation summary documenting how system was built
- [ ] Lessons learned capturing insights
- [ ] Professional quality documentation suitable for portfolio

---

#### Deliverable Specification

**File Name:** `hybrid-orchestration-capstone.md`

**Location:** Documentation folder or GitHub repository (alongside implementation)

**Format Requirements:**
- Comprehensive markdown document
- Visual architecture diagram (ASCII or described)
- Performance data from actual implementation
- All comparison tables completed
- Lessons learned section included

**Quality Criteria (Appendix C Rubric - 20 points total):**

**Criterion 1: Parallel Implementation (5 points)**
- From Session 1 - working parallel execution with aggregation

**Criterion 2: Team-Based Implementation (5 points)**
- From Exercise 2.2 - agents collaborating with communication

**Criterion 3: Hybrid Orchestration (5 points)**
- Uses multiple patterns appropriately
- Clear justification for pattern selection
- Seamless phase transitions

**Criterion 4: Performance & Documentation (5 points)**
- Comprehensive analysis comparing approaches
- Clear metrics (time, cost, quality)
- Professional documentation
- Production-ready quality

**Module Completion Threshold:** 15/20 points (75%)

---

#### Tips & Troubleshooting

**Tips:**
- Don't build from scratch - combine Session 1 parallel + Exercise 2.2 team implementations
- Focus 20 min on design/documentation, implementation can extend beyond
- Use real performance data from your implementations
- Be honest in lessons learned - challenges are valuable insights

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Only using one pattern | Review your workflow - different phases likely have different needs. Planning = Sequential, Research = Parallel, Creation = Team |
| Can't justify pattern choices | Ask: What's optimized in this phase? Speed → Parallel. Quality → Team. Coherence → Sequential |
| Hybrid seems unnecessarily complex | Valid concern - if single pattern serves all phases well, use it. Hybrid only when phases have different optimization goals |
| Implementation incomplete | Capstone focuses on design/documentation. Working implementations from Sessions 1-2 count. Integration can be conceptual. |

---

## Templates & Resources

### Templates Provided This Session

| Template | Purpose | Location |
|----------|---------|----------|
| Agent Team Design | Design team roles and interactions | Exercise 2.1 instructions |
| Team Agent Prompt | Create team-aware agent prompts | Exercise 2.2 instructions |
| Hybrid Architecture | Design multi-pattern system | Exercise 2.3 instructions |

---

### Template: Team-Based Pattern (Appendix B)

```markdown
# Team Configuration Template

## Team Definition
```json
{
  "team": {
    "id": "content-creation-team",
    "goal": "Create high-quality content through collaboration",
    "agents": [
      {
        "role": "researcher",
        "capabilities": ["web_search", "file_read"],
        "interacts_with": ["writer"]
      },
      {
        "role": "writer",
        "capabilities": ["content_generation"],
        "interacts_with": ["researcher", "editor"]
      },
      {
        "role": "editor",
        "capabilities": ["content_revision"],
        "interacts_with": ["writer", "reviewer"]
      },
      {
        "role": "reviewer",
        "capabilities": ["quality_evaluation"],
        "interacts_with": ["editor"]
      }
    ],
    "workflow": {
      "phases": ["research", "draft", "edit", "review"],
      "max_iterations": 3
    }
  }
}
```

## Shared Workspace Template
```json
{
  "workspace": {
    "id": "ws-001",
    "created": "ISO-8601",
    "task": {
      "goal": "",
      "requirements": [],
      "constraints": []
    },
    "artifacts": {
      "research": null,
      "draft_v1": null,
      "draft_v2": null,
      "final": null
    },
    "communication_log": [],
    "current_phase": "research",
    "iteration": 1
  }
}
```

## Inter-Agent Message Format
```json
{
  "message": {
    "id": "msg-001",
    "timestamp": "ISO-8601",
    "from": "writer",
    "to": "researcher",
    "type": "request",
    "content": "Need additional data on competitor pricing",
    "priority": "normal",
    "requires_response": true,
    "timeout_seconds": 60
  }
}
```
```

**Usage Instructions:**
1. Copy JSON structures for your team configuration
2. Adapt roles and capabilities to your use case
3. Customize workspace artifacts to match your workflow

---

### External Resources

| Resource | Type | Link/Location | When to Use |
|----------|------|---------------|-------------|
| Appendix B: Team Patterns | Module Document | Module main doc | Team configuration examples |
| Appendix C: Evaluation Rubric | Module Document | Module main doc | Self-assess capstone quality |
| Session 1 Materials | Previous Session | Session 1 folder | Reference parallel implementation |

---

### Module Appendix References

For this session's exercises, you need:

- **Appendix B: Team-Based Pattern Templates** - Team configuration, workspace schemas, message formats
- **Appendix C: Module Evaluation Rubric** - 20-point rubric for capstone assessment (use this to self-assess Exercise 2.3)

See the main module document ([Module 1](../module-1-orchestration-patterns.md)) for full appendix content.

---

## Self-Assessment

### Exit Criteria Checklist

Before completing Module 1, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Design agent teams with specialized roles | Exercise 2.1 - clear role definitions | ☐ |
| 2 | Implement inter-agent communication | Exercise 2.2 - working team collaboration | ☐ |
| 3 | Combine orchestration patterns into hybrid system | Exercise 2.3 - multi-pattern architecture | ☐ |
| 4 | Justify pattern selection based on phase needs | Exercise 2.3 - clear rationale per phase | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 2.1 output | `team-design.md` | Documentation folder | ☐ |
| Exercise 2.2 output | `team-implementation.md` + platform workspace | Documentation + platform | ☐ |
| **Exercise 2.3 CAPSTONE** | `hybrid-orchestration-capstone.md` | Documentation folder | ☐ |

---

### Module Completion Self-Assessment

Use Appendix C rubric to score your capstone (Exercise 2.3):

| Criterion | Points (0-5) | Self-Score |
|-----------|--------------|------------|
| 1. Parallel Implementation | 5 | ___ |
| 2. Team-Based Implementation | 5 | ___ |
| 3. Hybrid Orchestration | 5 | ___ |
| 4. Performance & Documentation | 5 | ___ |
| **Total** | **20** | **___** |

**Module Completion Threshold:** 15/20 (75%)

**Your Score:** ___/20

**Module Status:** [ ] Complete (≥15) | [ ] Needs Revision (<15)

---

### Reflection Questions

Take 10 minutes to consider:

1. **What was your biggest insight from Module 1?**
   - About parallel patterns? Team-Based collaboration? Hybrid thinking?

2. **Which pattern do you see applying most in your work?**
   - Parallel for speed? Team-Based for quality? Hybrid for production systems?

3. **How has your agent architecture thinking evolved?**
   - From Block 3 Sequential patterns to advanced multi-pattern architectures

4. **What will you build next?**
   - How will you apply these patterns to real consulting deliverables?

---

## Getting Help

### Quick Answers
- **Support Channel:** Post questions with [Module1-Session2] tag
- **Response Time:** Usually within 12 hours
- **Capstone Support:** Tag instructor for capstone review/feedback

### Common Questions This Session

**Q: How is Team-Based different from just Sequential with multiple agents?**
A: Sequential is one-directional: A→B→C. Team-Based allows bidirectional communication: A can ask B for help, C can send feedback to B for revision. It's about iteration and collaboration, not just passing results forward.

**Q: My entire workflow needs both speed AND quality - which pattern?**
A: That's exactly when to use Hybrid! Use Parallel for phases needing speed (independent data gathering), Team-Based for phases needing quality (collaborative creation), Sequential for phases needing coherence (planning, finalization).

**Q: Can I complete the capstone with just 2 patterns instead of all 3?**
A: Yes - minimum is 2 patterns to qualify as Hybrid. But try to identify where all 3 fit - most production workflows have planning (Sequential), research (Parallel), and creation (Team-Based) phases.

**Q: How do I implement Request-Response in my platform?**
A: Platform-specific. Make: use webhooks or data stores. n8n: HTTP requests or database. Custom code: function calls with message objects. The pattern concept is universal - implementation varies.

### Capstone Support

**Capstone-Specific Help:**
- **Design Review:** Post your Exercise 2.3 design before implementation for feedback
- **Rubric Clarification:** Ask about Appendix C scoring criteria if unclear
- **Implementation Challenges:** Share specific technical blockers

**Before Submitting Capstone:**
- [ ] Self-scored using Appendix C rubric
- [ ] Achieved ≥15/20 points
- [ ] All comparison tables completed
- [ ] Performance data from real implementations

---

## Module 1 Completion

### Congratulations!

When you complete Exercise 2.3 capstone with ≥15/20 points, you have mastered **Advanced Orchestration Patterns**:

**You Can Now:**
- ✓ Design and implement Parallel orchestration for 50-75% time reduction
- ✓ Build Team-Based systems with collaborative agent teams
- ✓ Create Hybrid architectures combining patterns appropriately
- ✓ Justify pattern selection based on optimization goals
- ✓ Build production-ready multi-pattern agent systems

**This Distinguishes You:**
Most AI practitioners know Sequential patterns. You now architect sophisticated multi-pattern systems appropriate for enterprise-scale automation.

**Portfolio Piece:**
Your Exercise 2.3 capstone demonstrates advanced architecture skills. Include it in your professional portfolio.

---

## Glossary

| Term | Definition |
|------|------------|
| **Team-Based Orchestration** | Pattern where agents with specialized roles collaborate through communication and shared workspace |
| **Role Archetype** | Standard agent specialization (Researcher, Analyst, Creator, Critic, Editor, Coordinator) |
| **Inter-Agent Communication** | Mechanisms enabling agents to exchange information (handoff, request-response, workspace) |
| **Direct Handoff** | Communication pattern where Agent A passes results to Agent B sequentially |
| **Request-Response** | Communication pattern enabling agents to request information from each other |
| **Shared Workspace** | Common context where all agents read/write artifacts |
| **Hybrid Orchestration** | Architecture combining Sequential, Parallel, and Team-Based patterns per phase |
| **Pattern Selection** | Choosing orchestration pattern based on phase optimization goal |
| **Collaboration Value** | Quality improvement achieved through agent team interaction |
| **Phase Handoff** | Transition between workflow phases using different orchestration patterns |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial Session 2 participant guide created |

---

**Navigation:** [← Session 1](../session-1/participant-guide.md) | **Session 2** | Advanced Module 1 Complete

---

**Congratulations on completing Advanced Module 1!**
