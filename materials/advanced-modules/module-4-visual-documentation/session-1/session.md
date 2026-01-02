# **Advanced Module 4: Visual Documentation with Mermaid**
## **Session 1: Mermaid Fundamentals**

**Duration:** 45 min live + 60 min homework

---

## **Entry Criteria**

- [ ] Markdown proficiency
- [ ] Workflows or agents to document
- [ ] GitHub repository access
- [ ] Text editor with Mermaid preview (VS Code, etc.)

---

## **Exit Criteria**

- [ ] Mermaid syntax understood
- [ ] Flowcharts created for workflows
- [ ] Sequence diagrams for interactions
- [ ] 5+ diagrams created and rendered

---

## **Workshop Content (45 minutes)**

### **Segment 1: Introduction to Mermaid (10 min)**

- **What is Mermaid?**
  - Text-based diagramming language
  - Renders in Markdown (GitHub, GitLab, etc.)
  - No external tools needed
  - Version-controllable diagrams

- **Why Mermaid for AI documentation?**
  - Describe workflows visually
  - Show agent interactions
  - Document system architecture
  - Easy to update as systems evolve

- **Where Mermaid renders:**
  - GitHub README files
  - GitLab documentation
  - Notion, Obsidian, many others
  - VS Code with extensions

- **Basic syntax:**
  ```
  ```mermaid
  graph TD
    A[Start] --> B[Process]
    B --> C[End]
  ```
  ```

### **Segment 2: Flowcharts (15 min)**

- **Basic flowchart:**
  ```mermaid
  graph TD
      A[Start] --> B{Decision?}
      B -->|Yes| C[Action 1]
      B -->|No| D[Action 2]
      C --> E[End]
      D --> E
  ```

- **Direction options:**
  - `TD` or `TB` - Top to Bottom
  - `BT` - Bottom to Top
  - `LR` - Left to Right
  - `RL` - Right to Left

- **Node shapes:**
  ```
  A[Rectangle]
  B(Rounded)
  C([Stadium])
  D[[Subroutine]]
  E[(Database)]
  F((Circle))
  G{Diamond/Decision}
  H{{Hexagon}}
  I[/Parallelogram/]
  ```

- **Link styles:**
  ```
  A --> B        (Arrow)
  A --- B        (Line)
  A -.-> B       (Dotted arrow)
  A ==> B        (Thick arrow)
  A --text--> B  (Arrow with text)
  A -->|text| B  (Arrow with text)
  ```

- **Workflow example:**
  ```mermaid
  graph LR
      A[Trigger] --> B[Gather Data]
      B --> C[AI Generate]
      C --> D{Quality Check}
      D -->|Pass| E[Output]
      D -->|Fail| F[Retry]
      F --> C
  ```

### **Segment 3: Sequence Diagrams (12 min)**

- **Basic sequence diagram:**
  ```mermaid
  sequenceDiagram
      participant U as User
      participant O as Orchestrator
      participant A as Agent

      U->>O: Submit request
      O->>A: Delegate task
      A->>A: Process
      A-->>O: Return result
      O-->>U: Deliver output
  ```

- **Arrow types:**
  ```
  ->>   Solid line with arrow
  -->>  Dotted line with arrow
  -x    Solid line with cross
  --x   Dotted line with cross
  -)    Solid line with open arrow
  --)   Dotted line with open arrow
  ```

- **Advanced features:**
  ```mermaid
  sequenceDiagram
      participant U as User
      participant S as System

      U->>S: Request

      alt Success
          S-->>U: Response
      else Failure
          S-->>U: Error
      end

      loop Retry
          S->>S: Attempt
      end

      Note over U,S: Important note
  ```

- **Agent interaction example:**
  ```mermaid
  sequenceDiagram
      participant O as Orchestrator
      participant R as Researcher
      participant W as Writer
      participant E as Editor

      O->>R: Gather information
      R-->>O: Research results
      O->>W: Generate draft
      W-->>O: Draft content
      O->>E: Review and edit
      E-->>O: Edited content
      O->>O: Final assembly
  ```

### **Segment 4: Styling and Best Practices (8 min)**

- **Adding styles:**
  ```mermaid
  graph TD
      A[Start]:::startStyle --> B[Process]
      B --> C[End]:::endStyle

      classDef startStyle fill:#9f9,stroke:#333
      classDef endStyle fill:#f99,stroke:#333
  ```

- **Subgraphs (grouping):**
  ```mermaid
  graph TD
      subgraph Phase1[Research Phase]
          A[Gather] --> B[Analyze]
      end
      subgraph Phase2[Creation Phase]
          C[Draft] --> D[Edit]
      end
      B --> C
  ```

- **Best practices:**
  - Keep diagrams focused (one concept per diagram)
  - Use consistent naming
  - Add labels to arrows
  - Use subgraphs for complex systems
  - Test rendering before committing

---

## **Self-Paced Exercises (60 minutes total)**

### **Exercise 1.1: Workflow Flowcharts (20 minutes)**

*Create flowcharts for your workflows*

1. **Document your main workflow:**

```markdown
# Workflow Diagram: [Your Workflow Name]

## Overview
[Brief description of what this workflow does]

## Flowchart

```mermaid
graph TD
    A[Trigger: Form Submission] --> B[Validate Input]
    B --> C{Valid?}
    C -->|Yes| D[Load Template]
    C -->|No| E[Return Error]
    D --> F[AI Generation]
    F --> G{Quality Check}
    G -->|Pass ≥4| H[Format Output]
    G -->|Score 3-4| I[Human Review]
    G -->|Fail <3| J[Regenerate]
    J --> F
    I --> K{Approved?}
    K -->|Yes| H
    K -->|No| J
    H --> L[Deliver to Client]
    L --> M[Log Execution]
    M --> N[End]
    E --> N
```

## Step Descriptions

| Step | Description |
|------|-------------|
| A | Workflow triggered by form submission |
| B | Validate required fields present |
| ... | ... |
```

2. **Create flowcharts for 2 more workflows**

3. **Add to your documentation**

**Deliverable:** 3 workflow flowcharts in markdown files

---

### **Exercise 1.2: Sequence Diagrams (20 minutes)**

*Document agent interactions*

1. **Create agent sequence diagram:**

```markdown
# Agent Interaction: [Scenario Name]

## Scenario
[What interaction this documents]

## Sequence Diagram

```mermaid
sequenceDiagram
    participant U as User
    participant O as Orchestrator
    participant R as Research Agent
    participant W as Writing Agent
    participant Q as Quality Agent

    U->>O: Request: Create proposal

    O->>R: Gather client information
    activate R
    R->>R: Search files
    R->>R: Fetch templates
    R-->>O: Research package
    deactivate R

    O->>W: Generate proposal
    activate W
    Note over W: Using template + research
    W-->>O: Draft proposal
    deactivate W

    O->>Q: Evaluate quality
    activate Q
    Q->>Q: Score against rubric

    alt Score ≥ 4
        Q-->>O: Pass
        O-->>U: Deliver proposal
    else Score < 4
        Q-->>O: Fail + suggestions
        O->>W: Revise with feedback
        W-->>O: Revised draft
        O->>Q: Re-evaluate
    end
    deactivate Q
```

## Interaction Notes

1. **Research Phase:** Agent gathers all necessary context
2. **Generation Phase:** Writing agent produces draft
3. **Quality Phase:** Evaluation with potential iteration
```

2. **Create sequence diagram for error handling:**

```markdown
# Error Handling Flow

```mermaid
sequenceDiagram
    participant O as Orchestrator
    participant A as Agent
    participant T as Tool (Model Context Protocol)
    participant E as Error Handler

    O->>A: Execute task
    A->>T: Use tool

    alt Tool Success
        T-->>A: Result
        A-->>O: Complete
    else Tool Failure
        T--xA: Error
        A->>E: Report failure
        E->>E: Log error

        loop Retry (max 3)
            E->>T: Retry with backoff
            alt Success
                T-->>E: Result
                E-->>A: Recovered
            else Fail
                T--xE: Error
            end
        end

        alt Recovered
            A-->>O: Complete
        else Max retries
            E->>O: Escalate
            O->>O: Human alert
        end
    end
```
```

**Deliverable:** 2 sequence diagrams in documentation

---

### **Exercise 1.3: Combined Documentation (20 minutes)**

*Create integrated visual documentation*

```markdown
# [System Name] - Visual Documentation

## System Overview

This document provides visual documentation for [system description].

## High-Level Architecture

```mermaid
graph TB
    subgraph Input
        A[Triggers]
        B[Data Sources]
    end

    subgraph Processing
        C[Orchestrator]
        D[Agent Pool]
        E[Quality System]
    end

    subgraph Output
        F[Deliverables]
        G[Notifications]
    end

    A --> C
    B --> C
    C --> D
    D --> E
    E --> F
    E --> G
```

## Workflow Details

### Main Workflow

```mermaid
graph LR
    [Your flowchart here]
```

### Quality Workflow

```mermaid
graph TD
    [Quality process flowchart]
```

## Agent Interactions

### Standard Execution

```mermaid
sequenceDiagram
    [Standard flow sequence]
```

### Error Recovery

```mermaid
sequenceDiagram
    [Error handling sequence]
```

## Legend

| Symbol | Meaning |
|--------|---------|
| Rectangle | Process step |
| Diamond | Decision point |
| Database shape | Data storage |
| Dotted line | Optional/async |
```

**Deliverable:** Integrated visual documentation file

---
