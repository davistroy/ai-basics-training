# Week 1: Agent Fundamentals

**Block:** 3 - AI Automation Architecture
**Duration:** 45 min live workshop + 75 min self-paced exercises

---

## Entry Criteria

- [ ] Block 2 Capstone completed and approved
- [ ] 3 working workflows from Block 2
- [ ] MCP configuration functional
- [ ] Understanding of quality gates and routing
- [ ] One complex workflow candidate identified for agent conversion

## Exit Criteria

- [ ] Understands agent vs. workflow distinction
- [ ] Agent design principles internalized
- [ ] First agent skeleton created
- [ ] Agent planning document completed
- [ ] Success criteria defined for capstone agent

---

## Pre-Work (Complete Before Week 1)

- Review [Agent Memory Meta-Framework Presentation](../../archive/presentation.md), slides 1-30
- Focus on: The Three Pillars of Domain Memory, Why Agents Fail, The Daily Contractor Analogy
- Time required: ~30 minutes

---

## Workshop Content (45 minutes)

### Segment 1: Welcome to Block 3 + The Agent Mindset (10 min)

- Welcome back and Block 3 overview
- **Maturity progression completion:**
  - Level 1: Templated workflows (Block 1 - completed)
  - Level 2: Workflow engineering (Block 2 - completed)
  - Level 3: Automation architecture (Block 3 - starting now)
- **The key shift:** From workflows that execute steps → Agents that make decisions
- Preview of capstone: End-to-end autonomous solution
- **Connection to pre-work:**
  - The presentation introduced WHY agents fail (memory, reliability, complexity)
  - Block 3 teaches HOW to build agents that succeed
  - The Three Pillars become your design framework
  - The Daily Contractor analogy guides your architecture

### Segment 2: Agents vs. Workflows - The Critical Distinction (12 min)

**Workflows:**
- Predetermined paths
- Human designs the logic
- Executes what you specify
- Fails when unexpected input arrives

**Agents:**
- Dynamic decision-making
- AI determines next steps
- Adapts to context
- Handles unexpected situations
- Can use tools and take actions

**The agent loop:**
```
Observe → Think → Act → Observe → Think → Act → ...
```

**When to use each:**
- Workflow: Predictable, repeatable processes
- Agent: Variable inputs, judgment required, tool selection needed

### Segment 3: The Two-Agent Architecture Pattern (15 min)

**The fundamental insight:**
- Stop trying to give agents memory
- Build systems where amnesiacs can work effectively

**Why single agents fail on multi-session tasks:**
- No memory between sessions
- Different interpretations of "done"
- Repeated failed attempts
- Context window pollution

**The Two-Agent Pattern:**
```
SETUP AGENT (runs once)
- Takes human request
- Creates structured records
- Defines goals, procedures, success criteria
- Then stops

WORKER AGENT (runs repeatedly, stateless)
- Reads current state from records
- Picks ONE incomplete task
- Does work, validates, updates records
- Stops

→ Next worker starts fresh, reads updated state, continues
```

**The Daily Contractor Analogy:**
- Each contractor is still an amnesiac
- But the PROJECT has memory
- The system has memory through structured records

**Core components of an agent:**
1. **Goal/Objective:** What the agent is trying to achieve
2. **Context/Memory:** Information the agent has access to (structured records!)
3. **Tools:** Actions the agent can take
4. **Reasoning:** How the agent decides what to do
5. **Output:** What the agent produces

**Consulting Domain Example: RFP Response Agent**

*The Problem:*
- RFP arrives with 47 requirements across 8 sections
- Manual response takes 20-40 hours
- Quality varies based on who writes it
- Easy to miss requirements

*Setup Agent (runs once when RFP arrives):*
- Parse all requirements into structured checklist
- Map each requirement to existing proposal sections
- Identify which templates apply
- Create response_plan.json with goals and procedures
- Then: STOP

*Worker Agent (runs repeatedly, stateless):*
- Read response_plan.json
- Find first section with status: "pending"
- Load the mapped template
- Generate section draft
- Self-evaluate against requirements
- Update response_plan.json
- STOP

### Segment 4: Planning Your Capstone Agent (8 min)

**Agent selection criteria:**
- Complex enough to benefit from autonomy
- Clear success criteria
- Measurable business value
- Builds on Block 2 workflows

**Planning framework:**
- What goal should the agent achieve?
- What tools does it need?
- What decisions must it make?
- How will you know it succeeded?
- What could go wrong?

**Live exercise:** Brainstorm potential agent projects

---

## Self-Paced Exercises (75 minutes total)

### Exercise 1.1: Agent vs. Workflow Analysis (20 minutes)

*Understand when agents add value*

1. Review your Block 2 workflows and categorize:

```markdown
# Agent Opportunity Analysis

## Workflow 1: [Name]
- **Current state:** Workflow with fixed steps
- **Decision points:** [Where does human judgment currently happen?]
- **Variability:** [How much do inputs/situations vary?]
- **Agent potential:** [High/Medium/Low]
- **Rationale:** [Why?]

## Workflow 2: [Name]
[Repeat analysis]

## Workflow 3: [Name]
[Repeat analysis]

## Best Agent Candidate
- **Selected workflow:** [Name]
- **Why this one:** [Explanation]
- **Expected benefits:** [What autonomy enables]
```

2. Identify the top candidate for agent conversion

**Deliverable:** `agent-opportunity-analysis.md`

---

### Exercise 1.2: Agent Design Document (35 minutes)

*Plan your capstone agent*

1. Create comprehensive agent design:

```markdown
# Agent Design Document

## Agent Name: [Descriptive name]

## Overview
**Purpose:** [What this agent does - 2-3 sentences]
**Business Value:** [Why this matters - time saved, capability gained]
**Autonomy Level:** [Full/Partial - when does it need human input?]

---

## Goal Definition

**Primary Goal:**
[Single, clear statement of what the agent should achieve]

**Success Criteria:**
1. [Measurable criterion 1]
2. [Measurable criterion 2]
3. [Measurable criterion 3]

**Failure Criteria:**
- [What constitutes failure]
- [When to stop and escalate]

---

## Context & Memory

**Initial Context Needed:**
- [What information the agent starts with]
- [Where this comes from]

**Runtime Context:**
- [What the agent learns during execution]
- [How it maintains state]

**Persistent Memory:**
- [What should be remembered across sessions]
- [How to store/retrieve]

---

## Tools & Capabilities

### Tool 1: [Name]
- **Purpose:** [What it does]
- **MCP Server:** [Which server provides this]
- **When to use:** [Decision criteria]
- **Expected output:** [What it returns]

### Tool 2: [Name]
[Repeat structure]

---

## Decision Framework

**Key Decisions the Agent Makes:**

1. **Decision:** [Description]
   - **Options:** [A, B, C]
   - **Criteria:** [How to choose]

2. **Decision:** [Description]
   - **Options:** [A, B, C]
   - **Criteria:** [How to choose]

---

## Domain Memory Design

### Goals (Testable Success Criteria)
1. [Criterion with specific test]
2. [Criterion with specific test]
3. [Criterion with specific test]

### Progress Records Structure
- What will be logged after each execution?
- How will failures be recorded?
- What state persists between sessions?

### Operating Procedures
- Validation process: [How to verify success]
- Escalation triggers: [When to stop and get help]
- Quality standards: [What "good" looks like]

---

## Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| [Risk 1] | H/M/L | H/M/L | [Strategy] |
| [Risk 2] | H/M/L | H/M/L | [Strategy] |

---

## Success Metrics

| Metric | Baseline (Current) | Target (With Agent) |
|--------|-------------------|---------------------|
| Time per task | | |
| Human intervention rate | | |
| Quality score | | |
| Cost per execution | | |
```

**Deliverable:** `agent-design-document.md`

---

### Exercise 1.3: Agent Skeleton Setup (20 minutes)

*Create the foundation*

1. Set up agent project structure:

```
/agents
  /[agent-name]
    /README.md           # Agent documentation
    /design.md           # Design document (from 1.2)
    /prompts/            # Agent prompts
      /system-prompt.md  # Main agent instructions
      /tool-prompts/     # Tool-specific prompts
    /config/             # Configuration files
    /tests/              # Test cases
    /logs/               # Execution logs
```

2. Create initial system prompt:

```markdown
# System Prompt: [Agent Name]

## Role
You are an AI agent that [description of role].

## Goal
Your objective is to [primary goal].

## Available Tools
You have access to the following tools:
1. [Tool 1]: [Description]
2. [Tool 2]: [Description]
3. [Tool 3]: [Description]

## Decision Guidelines
When deciding what to do:
- [Guideline 1]
- [Guideline 2]
- [Guideline 3]

## Constraints
- [Constraint 1]
- [Constraint 2]
- [Constraint 3]

## Output Format
[How the agent should structure its responses]

## When to Stop
Stop and report completion when:
- [Completion criterion 1]
- [Completion criterion 2]

Stop and request help when:
- [Escalation criterion 1]
- [Escalation criterion 2]
```

3. Commit to GitHub repository

**Deliverable:** Agent folder structure + initial system prompt

---

## Key Takeaways

1. **Agents decide, workflows execute** - Know when each is appropriate
2. **The Two-Agent Pattern solves memory** - Setup once, workers repeatedly
3. **The project has memory, not the agent** - External state is the key
4. **Domain Memory = Goals + Progress + Procedures** - The three pillars
5. **Design before building** - Clear goals and success criteria first

---

## Preparation for Week 2

- Complete all Week 1 exercises
- Refine agent design based on feedback
- Review MCP servers you'll need for your agent
- Next week: Building reliable agents

---

## Resources

- [Anthropic Agent Documentation](https://docs.anthropic.com/en/docs/agents)
- [MCP Server Registry](https://github.com/modelcontextprotocol/servers)
- [Agent Memory Meta-Framework Presentation](../../archive/presentation.md)
