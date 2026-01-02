# **Advanced Module 1: Advanced Orchestration Patterns**
## **Session 2: Team-Based Orchestration Pattern**

**Module:** Advanced Module 1 - Advanced Orchestration Patterns
**Session:** 2 of 2
**Duration:** 45 min live + 75 min homework

-----

## **Entry Criteria**

- [ ] Parallel pattern implemented and tested
- [ ] Result aggregation working
- [ ] Understanding of agent specialization
- [ ] Familiar with agent communication concepts

## **Exit Criteria**

- [ ] Team-Based pattern architecture understood
- [ ] Agent roles and interactions designed
- [ ] Collaborative workflow implemented
- [ ] Inter-agent communication functional
- [ ] Hybrid orchestration approach designed
- [ ] Module capstone completed

-----

## **Workshop Content (45 minutes)**

### **Segment 1: Team-Based Pattern Fundamentals (12 min)**

- **Pattern overview:**
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

- **Key characteristics:**
  - Agents have distinct roles (like a real team)
  - Agents can interact with each other
  - Shared workspace/context
  - Iterative refinement possible
  - More complex coordination

- **When to use Team-Based:**
  - Complex problems requiring multiple perspectives
  - Iterative refinement needed
  - Quality through collaboration
  - Simulating expert panels or review boards

- **When NOT to use:**
  - Simple, linear tasks
  - Speed is critical
  - Limited resources/budget
  - Overkill for the problem

### **Segment 2: Designing Agent Teams (12 min)**

- **Role archetypes:**

  | Role | Responsibility | Example |
  |------|----------------|---------|
  | Researcher | Gather information | Web search, file lookup |
  | Analyst | Process and interpret | Data analysis, pattern finding |
  | Creator | Generate content | Writing, designing |
  | Critic | Evaluate quality | Review, scoring |
  | Editor | Refine and polish | Revision, formatting |
  | Coordinator | Manage workflow | Task assignment, tracking |

- **Team composition examples:**

  **Content Creation Team:**
  ```
  Researcher → Writer → Editor → Reviewer
  ```

  **Analysis Team:**
  ```
  Data Gatherer → Analyst → Summarizer → Fact Checker
  ```

  **Decision Support Team:**
  ```
  Researcher ──┬── Pro Analyst ──┬── Synthesizer → Recommender
               └── Con Analyst ──┘
  ```

- **Defining agent personalities:**
  - Each agent has focused expertise
  - Clear boundaries of responsibility
  - Defined interaction protocols

### **Segment 3: Inter-Agent Communication (12 min)**

- **Communication patterns:**

  1. **Direct Handoff:**
     ```
     Agent A completes → passes to Agent B
     ```
     - Simple, clear ownership
     - No back-and-forth

  2. **Request-Response:**
     ```
     Agent A: "I need information about X"
     Agent B: "Here is information about X"
     Agent A: continues with information
     ```
     - Agents can ask each other for help
     - More flexible

  3. **Shared Workspace:**
     ```
     All agents read/write to shared context
     Coordinator manages turn-taking
     ```
     - Most collaborative
     - Requires coordination

- **Implementing communication:**

  ```json
  {
    "message_type": "request",
    "from": "writer_agent",
    "to": "researcher_agent",
    "content": "Need statistics on market size for 2024",
    "priority": "high",
    "timeout": 30
  }
  ```

- **Shared context structure:**

  ```json
  {
    "workspace": {
      "task_id": "xyz",
      "goal": "Create market analysis report",
      "current_phase": "research",
      "artifacts": {
        "research_notes": "...",
        "draft_v1": "...",
        "review_comments": "..."
      },
      "decisions_made": [],
      "open_questions": []
    }
  }
  ```

### **Segment 4: Hybrid Orchestration (9 min)**

- **Combining patterns:**
  ```
  Sequential: [Input] → [Planner]
                           ↓
  Parallel:   ┌── [Researcher A] ──┐
              └── [Researcher B] ──┘
                           ↓
  Team-Based: [Analyst] ←→ [Writer] ←→ [Reviewer]
                           ↓
  Sequential: [Finalizer] → [Output]
  ```

- **Pattern selection by phase:**
  | Phase | Best Pattern | Rationale |
  |-------|--------------|-----------|
  | Planning | Sequential | Single coherent plan |
  | Research | Parallel | Independent gathering |
  | Analysis | Team-Based | Collaborative refinement |
  | Finalization | Sequential | Single output |

- **Designing hybrid systems:**
  - Identify natural phase boundaries
  - Match pattern to phase requirements
  - Define handoffs between patterns

-----

## **Self-Paced Exercises (75 minutes total)**

### **Exercise 2.1: Design Agent Team (25 minutes)**

*Create your collaborative agent team*

```markdown
# Agent Team Design

## Team Purpose
[What problem does this team solve?]

## Team Composition

### Agent 1: [Role Name]
- **Expertise:** [Specialization]
- **Responsibilities:**
  - [Responsibility 1]
  - [Responsibility 2]
- **Interacts with:** [Other agents]
- **Inputs:** [What it needs]
- **Outputs:** [What it produces]
- **Tools:** [MCP servers/tools]

### Agent 2: [Role Name]
[Repeat structure]

### Agent 3: [Role Name]
[Repeat structure]

### Agent 4: [Role Name]
[Repeat structure]

## Interaction Map
```
[Agent 1] ──request──→ [Agent 2]
    ↑                      ↓
    └───feedback───← [Agent 3]
                          ↓
                    [Agent 4] → Output
```

## Shared Workspace Schema
```json
{
  "task": {},
  "artifacts": {},
  "status": {},
  "communication_log": []
}
```

## Workflow Phases
1. [Phase 1]: [Which agents, what happens]
2. [Phase 2]: [Which agents, what happens]
3. [Phase 3]: [Which agents, what happens]

## Coordination Rules
- Turn-taking: [How managed]
- Conflict resolution: [How handled]
- Completion criteria: [When done]
```

**Deliverable:** `team-design.md`

-----

### **Exercise 2.2: Implement Team Collaboration (30 minutes)**

*Build working agent team*

1. **Create agent prompts with team awareness:**

```markdown
# Team Agent System Prompt: [Role]

## Your Role
You are the [Role] on a team working to [goal].

## Your Teammates
- [Role 1]: [What they do, when to ask them]
- [Role 2]: [What they do, when to ask them]

## Your Responsibilities
- [Responsibility 1]
- [Responsibility 2]

## Collaboration Guidelines
- When you need [X], ask [Role]
- When you complete [Y], pass to [Role]
- Check shared workspace for [Z]

## Communication Format
When communicating with teammates:
```json
{
  "to": "[role]",
  "type": "request|response|handoff",
  "content": "...",
  "artifacts": []
}
```

## Shared Workspace Access
You can read and write to the shared workspace.
Current artifacts available: [list]
```

2. **Implement coordination layer:**
   - Track agent states
   - Route messages between agents
   - Manage shared workspace
   - Enforce turn-taking if needed

3. **Test team execution:**
   - Run 3+ complete team workflows
   - Observe agent interactions
   - Verify artifact passing
   - Check final output quality

**Deliverable:** Working team implementation + interaction logs

-----

### **Exercise 2.3: Module Capstone - Hybrid Orchestration (20 minutes)**

*Combine all patterns into sophisticated system*

```markdown
# Hybrid Orchestration Capstone

## System Overview
[Description of your multi-pattern system]

## Architecture
```
[Phase 1 - Sequential]
Input → Planner
           ↓
[Phase 2 - Parallel]
    ┌── Agent A ──┐
    └── Agent B ──┘
           ↓
[Phase 3 - Team-Based]
  Analyst ←→ Writer
           ↓
[Phase 4 - Sequential]
  Finalizer → Output
```

## Pattern Usage Justification

| Phase | Pattern | Why This Pattern |
|-------|---------|------------------|
| Planning | Sequential | [Reason] |
| Research | Parallel | [Reason] |
| Creation | Team-Based | [Reason] |
| Output | Sequential | [Reason] |

## Implementation Summary
- Total agents: [N]
- Parallel groups: [N]
- Team interactions: [Description]

## Performance Results

| Metric | Value |
|--------|-------|
| Total execution time | |
| Quality score | |
| Cost per execution | |
| Success rate | |

## Comparison to Single-Pattern

| Approach | Time | Quality | Complexity |
|----------|------|---------|------------|
| Sequential only | | | Low |
| Hybrid | | | High |
| Improvement | | | |

## Lessons Learned
1. [Lesson]
2. [Lesson]
3. [Lesson]
```

**Deliverable:** `hybrid-orchestration-capstone.md` + working implementation

-----
