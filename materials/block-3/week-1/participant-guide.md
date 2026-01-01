# **BLOCK 3 WEEK 1: Agent Fundamentals**

**Block:** 3: AI Automation Architecture
**Week:** 1 of 8
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Block Navigation:** [Block 2 Week 8](../../block-2/week-8/participant-guide.md) | **Week 1** | [Week 2 Participant Guide](../week-2/participant-guide.md)

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

By the end of this week, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Distinguish between agents and workflows and know when to use each | Exercise 1.1 |
| 2 | Apply the Two-Agent Architecture Pattern to design reliable agent systems | Exercise 1.2 |
| 3 | Create a comprehensive agent design document with goals, tools, and success criteria | Exercise 1.2 |
| 4 | Set up an agent project structure with system prompt foundations | Exercise 1.3 |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Block 2 Capstone completed and approved
- [ ] 3 working workflows from Block 2
- [ ] MCP configuration functional
- [ ] Understanding of quality gates and routing
- [ ] One complex workflow candidate identified for agent conversion
- [ ] Pre-work: Reviewed Agent Memory Meta-Framework Presentation (slides 1-30)

**Not ready?** Complete Block 2 requirements or reach out in the support channel for help.

---

## Key Concepts

### Concept 1: Agents vs. Workflows

**Definition:**
A **workflow** is a predetermined sequence of steps that executes what you specify. An **agent** is a system that makes dynamic decisions, adapts to context, and uses tools to achieve goals.

**Why It Matters:**
Knowing when to use each determines whether your automation succeeds or fails. Agents are powerful but expensive; workflows are efficient but rigid.

**Core Principle:**
> "If you can draw every possible path, use a workflow. If you can't, consider an agent."

**The Agent Loop:**
```
Observe → Think → Act → Observe → Think → Act → ...
```

**Comparison:**

| Aspect | Workflow | Agent |
|--------|----------|-------|
| Path | Predetermined | Dynamic |
| Logic | Human designs | AI determines |
| Input variation | Limited | Handles variety |
| Failure mode | Fails on unexpected | Adapts to unexpected |
| Cost | Lower | Higher |
| Best for | Predictable, repeatable | Variable, judgment-required |

**Common Mistake:**
Using agents for simple, predictable tasks wastes resources. Use workflows when the path is clear.

---

### Concept 2: The Two-Agent Architecture Pattern

**Definition:**
A design pattern where a **Setup Agent** runs once to create structure and records, then **Worker Agents** run repeatedly in a stateless manner, reading from and updating those records.

**Why It Matters:**
LLMs are "unreliable amnesiacs" - they have no memory between sessions. This pattern makes that limitation irrelevant by putting memory in the PROJECT, not the agent.

**The Pattern:**
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

**The Daily Contractor Analogy:**
> Imagine hiring a contractor who forgets everything each day. You wouldn't rely on their memory - you'd create a detailed job board, progress logs, and clear procedures. Each morning, any contractor can read the board, see what's done and what's next, and continue the work. That's exactly what the Two-Agent Pattern does.

**When to Use:**
- Multi-step tasks that span multiple sessions
- Tasks requiring persistent state
- Complex projects with multiple subtasks

**When NOT to Use:**
- Simple, single-response tasks
- Tasks that complete in one session
- Highly predictable, fixed workflows

---

### Concept 3: Core Agent Components

**Definition:**
Every agent consists of five core components that define its behavior and capabilities.

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| **Goal/Objective** | What the agent is trying to achieve | "Generate complete RFP response" |
| **Context/Memory** | Information the agent has access to | Structured records, progress logs |
| **Tools** | Actions the agent can take | File read/write, API calls, MCP servers |
| **Reasoning** | How the agent decides what to do | Decision criteria, priorities |
| **Output** | What the agent produces | Documents, updates, notifications |

**Visual Reference:**
```
    ┌─────────────────────────────────────┐
    │              AGENT                  │
    ├─────────────────────────────────────┤
    │  GOAL: What to achieve              │
    │                                     │
    │  CONTEXT: What it knows             │
    │     ↓                               │
    │  REASONING: How it decides          │
    │     ↓                               │
    │  TOOLS: What it can do              │
    │     ↓                               │
    │  OUTPUT: What it produces           │
    └─────────────────────────────────────┘
```

---

### Concept 4: Domain Memory - The Three Pillars

**Definition:**
Domain Memory is the external state that enables stateless agents to work reliably. It consists of three pillars.

**The Three Pillars:**

| Pillar | Purpose | Example |
|--------|---------|---------|
| **Explicit Goals** | Testable success criteria | "Run login_test.py, all assertions pass" |
| **Progress Records** | What's been completed, attempted, failed | "Tuesday: Tried approach A → timeout" |
| **Operating Procedures** | How to validate, when to escalate | "After 3 failures, escalate to human" |

**Why It Matters:**
- Goals prevent "different interpretations of done"
- Progress prevents "Groundhog Day loops" (repeating failures)
- Procedures ensure consistent quality and safety

**Core Principle:**
> "If you can't test it, it's not a goal - it's a wish."

---

### Quick Reference: Agent Design Checklist

| Element | Question to Answer | Format |
|---------|-------------------|--------|
| Purpose | What does this agent do? | 2-3 sentences |
| Business Value | Why does it matter? | Time saved, capability gained |
| Autonomy Level | When does it need human input? | Full/Partial with triggers |
| Primary Goal | What is the single clear objective? | One statement |
| Success Criteria | How do you know it succeeded? | Measurable criteria |
| Failure Criteria | When should it stop and escalate? | Specific triggers |
| Tools | What can it do? | List with MCP servers |
| Key Decisions | What choices must it make? | Decision with options/criteria |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Understanding agent fundamentals and the Two-Agent Architecture Pattern that makes agents reliable.

**Key Points from Each Segment:**

**Segment 1: Welcome to Block 3 + The Agent Mindset**
- Completed the maturity progression: Level 1 (templates) → Level 2 (workflows) → Level 3 (agents)
- Key shift: From workflows that execute steps to agents that make decisions
- Pre-work connection: The Three Pillars become your design framework

**Segment 2: Agents vs. Workflows - The Critical Distinction**
- Workflows: Predetermined paths, human-designed logic
- Agents: Dynamic decisions, AI determines next steps
- Decision guide: Workflow for predictable; Agent for variable inputs and judgment

**Segment 3: The Two-Agent Architecture Pattern**
- Fundamental insight: Build systems where amnesiacs can work effectively
- Setup Agent runs once to create structure
- Worker Agents run repeatedly, stateless, reading from shared records
- "The project has memory, not the agent"

**Segment 4: Planning Your Capstone Agent**
- Selection criteria: Complex enough to benefit, clear success criteria, measurable value
- Planning framework introduced for homework exercises

### Demo Recap

**What Was Demonstrated:**
RFP Response Agent using the Two-Agent Pattern

**Key Steps:**
1. Setup Agent parses RFP requirements into structured checklist
2. Setup Agent creates response_plan.json with goals, procedures, sections
3. Worker Agent reads plan, finds first "pending" section
4. Worker Agent generates draft, self-evaluates, updates plan status
5. Next Worker Agent continues from updated state

**Result:**
A system where any worker can continue the work because progress is tracked externally, not in agent memory.

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 1.1 | 20 min | `agent-opportunity-analysis.md` | Identify agent candidates |
| 1.2 | 35 min | `agent-design-document.md` | Plan your capstone agent |
| 1.3 | 20 min | Agent folder structure + system prompt | Create foundation |

---

### Exercise 1.1: Agent vs. Workflow Analysis

**Duration:** 20 minutes

**Purpose:**
Understand when agents add value by analyzing your Block 2 workflows for agent potential. This exercise helps you identify the best candidate for your capstone agent.

**You Will Create:**
A document analyzing your workflows and selecting the best agent candidate.

---

#### Instructions

**Step 1: List Your Block 2 Workflows**
Open your Block 2 repository and list the 3+ workflows you created.

**Step 2: Analyze Each Workflow**
For each workflow, answer these questions:
- Where does human judgment currently happen?
- How much do inputs/situations vary?
- What fails when unexpected input arrives?

**Step 3: Rate Agent Potential**
Rate each workflow as High/Medium/Low for agent potential based on:
- High: Variable inputs, requires judgment, current workflow is brittle
- Medium: Some variation, occasional judgment needed
- Low: Predictable inputs, fixed logic sufficient

**Step 4: Select Your Candidate**
Choose the best candidate for agent conversion and explain why.

**Step 5: Review Your Work**
Check that your analysis includes:
- [ ] All 3+ Block 2 workflows analyzed
- [ ] Decision points identified for each
- [ ] Variability assessed for each
- [ ] Clear rationale for your selection
- [ ] Expected benefits articulated

---

#### Deliverable Specification

**File Name:** `agent-opportunity-analysis.md`

**Location:** Save in your GitHub repository `/agents/` folder

**Format Requirements:**
- Use the template structure provided below
- Be specific about decision points and variability
- Provide clear rationale, not just ratings

**Quality Criteria:**
- [ ] Analysis is specific to your actual workflows
- [ ] Agent potential ratings are justified with reasons
- [ ] Selected candidate has clear explanation
- [ ] Expected benefits are concrete and realistic

---

#### Template

```markdown
# Agent Opportunity Analysis

## Workflow 1: [Name]
- **Current state:** Workflow with fixed steps
- **Decision points:** [Where does human judgment currently happen?]
- **Variability:** [How much do inputs/situations vary?]
- **Agent potential:** [High/Medium/Low]
- **Rationale:** [Why this rating?]

## Workflow 2: [Name]
- **Current state:** Workflow with fixed steps
- **Decision points:** [Where does human judgment currently happen?]
- **Variability:** [How much do inputs/situations vary?]
- **Agent potential:** [High/Medium/Low]
- **Rationale:** [Why this rating?]

## Workflow 3: [Name]
- **Current state:** Workflow with fixed steps
- **Decision points:** [Where does human judgment currently happen?]
- **Variability:** [How much do inputs/situations vary?]
- **Agent potential:** [High/Medium/Low]
- **Rationale:** [Why this rating?]

## Best Agent Candidate
- **Selected workflow:** [Name]
- **Why this one:** [Detailed explanation]
- **Expected benefits:** [What autonomy enables - be specific]
```

---

#### Example

**Scenario:** Analyzing a proposal generation workflow

**Example Analysis:**
```markdown
## Workflow 2: Client Proposal Generator
- **Current state:** Workflow that assembles proposals from templates
- **Decision points:**
  - Selecting which case studies to include
  - Adjusting scope based on client size
  - Choosing pricing tier
- **Variability:** High - each client has different needs, industries, sizes
- **Agent potential:** High
- **Rationale:** Currently requires manual review of every proposal because
  the template selection is context-dependent. An agent could analyze client
  details and make appropriate selections.
```

**Why This Works:**
The analysis is specific about WHERE decisions happen and WHY variability matters.

---

#### Tips & Troubleshooting

**Tips:**
- Think about where you currently intervene manually in workflows
- Consider what would break if you got unusual input

**Common Issues:**

| Problem | Solution |
|---------|----------|
| All workflows seem low potential | Look for hidden decision points you're making manually |
| Can't decide between candidates | Choose the one with clearest success criteria |

---

### Exercise 1.2: Agent Design Document

**Duration:** 35 minutes

**Purpose:**
Plan your capstone agent comprehensively. This document becomes the foundation for everything you build in Block 3 - essentially the output of your "Setup Agent" for the project.

**You Will Create:**
A detailed design document covering all aspects of your agent.

---

#### Instructions

**Step 1: Define Overview**
Write the purpose, business value, and autonomy level for your agent.

**Step 2: Define Goals**
Create a primary goal statement and 3+ measurable success criteria. Also define failure criteria.

**Step 3: Design Context & Memory**
Specify what information the agent needs initially, during runtime, and across sessions.

**Step 4: Identify Tools**
List each tool the agent needs with its MCP server and usage criteria.

**Step 5: Create Decision Framework**
Document the key decisions the agent must make and how it should choose.

**Step 6: Design Domain Memory**
Apply the Three Pillars: testable goals, progress records structure, operating procedures.

**Step 7: Assess Risks**
Identify 3+ risks with likelihood, impact, and mitigation strategies.

**Step 8: Define Success Metrics**
Create a table with baseline (current) and target metrics.

**Step 9: Review Your Work**
Check that your document includes:
- [ ] Clear, single primary goal
- [ ] Measurable success criteria (not vague)
- [ ] Defined failure criteria with escalation triggers
- [ ] All required tools identified
- [ ] Realistic risk assessment

---

#### Deliverable Specification

**File Name:** `agent-design-document.md`

**Location:** Save in your GitHub repository `/agents/[agent-name]/design.md`

**Format Requirements:**
- Use the complete template structure
- Fill in ALL sections (no placeholders)
- Be specific - avoid vague language

**Quality Criteria:**
- [ ] Primary goal is a single, clear statement
- [ ] Success criteria are testable (not "make it good")
- [ ] Tools have specific MCP servers identified
- [ ] Risks are realistic, not generic
- [ ] Metrics have actual baseline numbers where possible

---

#### Template

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
- **Purpose:** [What it does]
- **MCP Server:** [Which server provides this]
- **When to use:** [Decision criteria]
- **Expected output:** [What it returns]

### Tool 3: [Name]
- **Purpose:** [What it does]
- **MCP Server:** [Which server provides this]
- **When to use:** [Decision criteria]
- **Expected output:** [What it returns]

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
| [Risk 3] | H/M/L | H/M/L | [Strategy] |

---

## Success Metrics

| Metric | Baseline (Current) | Target (With Agent) |
|--------|-------------------|---------------------|
| Time per task | [X minutes] | [Y minutes] |
| Human intervention rate | [X%] | [Y%] |
| Quality score | [X/5] | [Y/5] |
| Cost per execution | [$X] | [$Y] |
```

---

#### Example

**Scenario:** RFP Response Agent

```markdown
## Goal Definition

**Primary Goal:**
Generate complete, requirement-compliant RFP response drafts for all sections, ready for human review and refinement.

**Success Criteria:**
1. Every RFP requirement has a corresponding response
2. Each section scores >= 4.0 on quality rubric
3. Response follows client-specific tone from style.json
4. Total generation time < 4 hours (vs 20-40 hours manual)

**Failure Criteria:**
- Any section fails quality check 3+ times → escalate to human
- Missing requirement detected → stop and flag
- Template not found for section type → stop and flag
```

**Why This Works:**
The goal is specific, success criteria are measurable, and failure criteria include specific escalation triggers.

---

### Exercise 1.3: Agent Skeleton Setup

**Duration:** 20 minutes

**Purpose:**
Create the foundational structure for your agent project. This includes folder organization and an initial system prompt that you'll refine throughout Block 3.

**You Will Create:**
A complete agent folder structure and initial system prompt.

---

#### Instructions

**Step 1: Create Folder Structure**
In your GitHub repository, create this structure:
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

**Step 2: Create README.md**
Write a brief README for your agent with:
- Agent name and purpose
- Quick start instructions (placeholder for now)
- Link to design document

**Step 3: Create System Prompt**
Using the template below, create your agent's system prompt.

**Step 4: Commit to GitHub**
Commit all files with a meaningful commit message.

**Step 5: Review Your Work**
Check that your setup includes:
- [ ] Complete folder structure
- [ ] README with purpose and links
- [ ] System prompt with all required sections
- [ ] Committed to GitHub

---

#### Deliverable Specification

**File Name:** Multiple files in `/agents/[agent-name]/`

**Location:** Your GitHub repository

**Format Requirements:**
- Follow the exact folder structure
- System prompt must include all template sections
- README should be brief but complete

**Quality Criteria:**
- [ ] Folder structure matches template exactly
- [ ] System prompt role is clear and specific
- [ ] Goals align with design document
- [ ] Constraints are realistic and enforceable
- [ ] Stop criteria are specific

---

#### System Prompt Template

```markdown
# System Prompt: [Agent Name]

## Role
You are an AI agent that [description of role].

## Goal
Your objective is to [primary goal from design document].

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

---

#### Example

**System Prompt for RFP Response Agent:**

```markdown
# System Prompt: RFP Response Agent

## Role
You are an AI agent that generates high-quality RFP response sections based on structured requirements and templates.

## Goal
Your objective is to generate a complete, requirement-compliant draft for ONE pending section of an RFP response.

## Available Tools
You have access to the following tools:
1. Filesystem (Read): Access templates and reference materials
2. Filesystem (Write): Save generated drafts and update progress
3. GitHub: Read version-controlled templates and style guides

## Decision Guidelines
When deciding what to do:
- Always read response_plan.json first to find the next pending section
- Select the template that best matches the section type
- Prioritize requirement coverage over elegant prose
- Self-evaluate against the quality rubric before saving

## Constraints
- Only work on ONE section per execution
- Do not modify sections marked as "complete"
- Always update response_plan.json with your status
- Maximum 3 attempts per section before escalating

## Output Format
Save drafts as markdown files in /outputs/[section-id].md
Update response_plan.json with status and quality score

## When to Stop
Stop and report completion when:
- Section draft passes quality threshold (>= 4.0)
- response_plan.json updated with "complete" status

Stop and request help when:
- Quality threshold not met after 3 attempts
- Required template not found
- Ambiguous requirement that needs human clarification
```

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| Agent Opportunity Analysis | Identify best agent candidate | Exercise 1.1 |
| Agent Design Document | Comprehensive agent planning | Exercise 1.2 |
| System Prompt | Initial agent instructions | Exercise 1.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Anthropic Agent Documentation | Documentation | [docs.anthropic.com](https://docs.anthropic.com/en/docs/agents) | Understanding agent concepts |
| MCP Server Registry | Registry | [GitHub](https://github.com/modelcontextprotocol/servers) | Finding MCP servers for tools |
| Agent Memory Meta-Framework | Presentation | Archive folder | Review pre-work concepts |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Distinguish agents from workflows | Exercise 1.1 analysis | |
| 2 | Apply Two-Agent Architecture Pattern | Exercise 1.2 domain memory design | |
| 3 | Create comprehensive agent design | Exercise 1.2 complete document | |
| 4 | Set up agent project structure | Exercise 1.3 folder + system prompt | |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 1.1 output | `agent-opportunity-analysis.md` | `/agents/` | |
| Exercise 1.2 output | `agent-design-document.md` | `/agents/[name]/design.md` | |
| Exercise 1.3 output | Folder structure + `system-prompt.md` | `/agents/[name]/` | |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** What concept or technique suddenly made sense?

2. **What's still fuzzy?** What do you need more practice or clarification on?

3. **How will you apply this?** Name one real work deliverable where you'll use agent architecture.

4. **What surprised you?** Was anything harder or easier than expected?

---

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Tag your cohort for quick tips

### Common Questions This Week

**Q: How complex should my capstone agent be?**
A: Complex enough to demonstrate the patterns (multi-step, tool usage, error handling) but simple enough to complete. Think one significant task, not a whole system.

**Q: What if I want to change my agent idea later?**
A: You can refine scope throughout Block 3. Major pivots after Week 3 are risky. Get feedback early if uncertain.

**Q: Do I need all the MCP servers configured now?**
A: No. Just identify what you'll need. Week 3 covers MCP configuration in depth.

### When to Ask for Help

- **Before asking:** Check this guide's troubleshooting sections
- **Good to ask:** "I tried analyzing my workflow but can't identify decision points. Here's what I have..."
- **Include:** Your specific situation, what you tried, and the result

---

## Looking Ahead

### Next Week Preview: Week 2 - Building Reliable Agents

**Focus:**
Building your first functional agent with error handling and the agent execution loop.

**How It Builds on This Week:**
Your agent design document becomes the foundation for implementation. Your system prompt gets its first real test.

**To Prepare:**
- [ ] Complete all Week 1 exercises
- [ ] Refine agent design based on any feedback
- [ ] Review MCP servers you'll need for your agent

---

## Glossary

| Term | Definition |
|------|------------|
| Agent | A system that makes dynamic decisions, adapts to context, and uses tools to achieve goals |
| Workflow | A predetermined sequence of steps that executes what you specify |
| Two-Agent Pattern | Architecture with Setup Agent (runs once) and Worker Agents (run repeatedly, stateless) |
| Domain Memory | External state (goals, progress, procedures) that enables stateless agents to work reliably |
| Setup Agent | Agent that runs once to create structure, records, and goals |
| Worker Agent | Stateless agent that reads state, executes one task, updates state, and stops |
| System Prompt | The instructions that define an agent's role, goals, tools, and constraints |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [Block 2 Week 8](../../block-2/week-8/participant-guide.md) | **Week 1** | [Week 2 Participant Guide](../week-2/participant-guide.md)
