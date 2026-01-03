# **POWERPOINT PRESENTATION: ADVANCED MODULE 4 SESSION 2**
## **Advanced Diagrams & Integration**

**Module:** Advanced Module 4: Visual Documentation with Mermaid
**Session Number:** 2 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 2+ certified consultants who completed Session 1 and have created basic Mermaid diagrams

**Key Thesis:** State diagrams and architecture patterns complete the visual documentation toolkit, enabling teams to document complex agent state machines, multi-component system architectures, and workflow integration points—while GitHub integration ensures diagrams render automatically in README files and documentation, creating living documentation that evolves with the codebase and serves as both design artifact and implementation reference.

**Session Learning Objectives:** By the end of this session, participants will:
1. Create state diagrams to document agent and workflow states
2. Build architecture diagrams using flowchart patterns
3. Integrate diagrams into GitHub documentation effectively
4. Complete a comprehensive visual documentation suite (capstone)

**Entry Criteria:** (What participants should have before this session)
- [ ] 5+ basic diagrams created (from Session 1)
- [ ] Flowcharts and sequence diagrams working
- [ ] Diagrams rendering in GitHub

**Exit Criteria:** (What participants should be able to do after this session)
- [ ] State diagrams for agent states
- [ ] Architecture diagrams for systems
- [ ] Diagrams integrated into README files
- [ ] Module capstone completed

**Presentation Structure:**
1. Opening & Session 1 Recap (3 min) - Slides 1-3
2. Segment 1: State Diagrams (12 min) - Slides 4-8
3. Segment 2: Class & Entity Diagrams (10 min) - Slides 9-11
4. Segment 3: Architecture Diagrams (12 min) - Slides 12-16
5. Segment 4: GitHub Integration (11 min) - Slides 17-20
6. Capstone Preview & Close (3 min) - Slides 21-23

**Total Slides:** 23

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Advanced Module 4 Session 2: Advanced Diagrams & Integration

**Subtitle:** State diagrams, architecture views, and production-ready documentation

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program

**Graphic:** Clean title slide with program branding. Use Block 2 orange tones.

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome back to Module 4, Session 2. Last session you learned flowcharts and sequence diagrams. Today we're adding advanced diagram types and integrating everything into production-ready documentation.

How many of you completed the three exercises from Session 1?

[Wait for show of hands]

Excellent. Today we're building on those fundamentals with state diagrams - perfect for documenting how agents move through different states - and architecture diagrams to show system context and components.

And your capstone today is to create a complete visual documentation suite that you can actually use for your AI systems."

[Transition: Click to next slide]

---

### SLIDE 2: SESSION OVERVIEW

**Title:** This Session's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Session 1 Recap & Preview |
| 3-15 min | State Diagrams | Agent & Workflow States |
| 15-25 min | Class & Entity Diagrams | System Components & Data |
| 25-37 min | Architecture Diagrams | Context, Containers, Deployment |
| 37-48 min | GitHub Integration | Documentation Structure |
| 48-51 min | Close | Capstone & Resources |

**Graphic:** Timeline showing the session flow

**SPEAKER NOTES:**

"Here's what we'll cover today:

First, state diagrams. These are perfect for documenting how your agents move through different states - idle, processing, completed, error handling.

Then class and entity diagrams for showing system components and data models.

In segment 3, we'll tackle architecture diagrams - how to show your system's context, major components, and deployment.

And we'll close with GitHub integration best practices - how to structure your documentation so it's actually useful.

Your capstone exercise brings all of this together into a comprehensive visual documentation suite.

[Pause]

Questions before we dive in?"

[Transition]

---

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Create state diagrams to document agent and workflow states**
   - Show state transitions and error handling

2. **Build architecture diagrams using flowchart patterns**
   - Context, container, and deployment views

3. **Integrate diagrams into GitHub documentation effectively**
   - Structure, maintenance, and discoverability

4. **Complete a comprehensive visual documentation suite**
   - Module capstone: production-ready documentation

**Graphic:** Checklist with advanced diagram icons

**SPEAKER NOTES:**

"These are our four objectives for today. By the time you leave this session, you'll be able to:

[Read each objective, pausing briefly after each]

Notice that today is about completion and integration. Session 1 was foundations - flowcharts and sequences. Today we're adding the final pieces and putting it all together into documentation you can actually ship.

[Point to fourth objective]

Your capstone project creates a complete visual documentation suite - architecture diagrams, workflow diagrams, agent interactions, and state diagrams all integrated into a coherent documentation package.

Let's get started with state diagrams..."

[Transition: Click to Segment 1]

---

## SEGMENT 1: STATE DIAGRAMS
### Duration: 12 minutes | Slides 4-8

---

### SLIDE 4: WHY STATE DIAGRAMS?

**Title:** State Diagrams: Document How Things Change

**Content:**

**The Challenge:**
Your agents don't just process tasks linearly - they move through states: idle, analyzing, executing, observing, responding. How do you document these state transitions?

**Flowcharts vs. State Diagrams:**
- Flowcharts: Show process flow (what steps happen)
- State Diagrams: Show state transitions (what states exist and how you move between them)

**Perfect For:**
- Agent execution states
- Workflow lifecycle states
- Circuit breaker patterns
- Connection/session states

**Graphic:** Side-by-side flowchart vs. state diagram showing the difference

**GRAPHICS:**

**Graphic 1: Flowchart vs State Diagram Comparison**
- Purpose: Clarify the distinction between flowcharts and state diagrams
- Type: Side-by-side comparison with annotations
- Elements: Two diagrams representing the same agent system
- Labels:
  - LEFT: "Flowchart - Shows PROCESS STEPS"
    - Linear flow: Receive Task → Analyze → Execute → Observe → Respond
    - Annotation: "Shows WHAT steps happen in sequence"
  - RIGHT: "State Diagram - Shows STATES & TRANSITIONS"
    - States: Idle, Analyzing, Executing, Observing, Responding
    - Arrows labeled with events: "task received", "plan ready", "action complete"
    - Annotation: "Shows WHAT STATES exist and HOW to move between them"
- Relationships: Same system, different perspectives
- Visual Style: Flowchart uses rectangles, state diagram uses rounded rectangles with transition labels

**SPEAKER NOTES:**

"[Hook - Create distinction]"

"Session 1 we focused on flowcharts and sequences. Those show WHAT happens and WHO does WHAT. But what about documenting the STATES your system can be in?

Think about an agent. It's not just 'processing' - it's idle, then analyzing a task, then executing an action, then observing the result, then responding. These are distinct states with transitions between them.

[Point to graphic]

Flowcharts show steps in a process. State diagrams show the states a component can be in and how it transitions between them.

This is perfect for:
- Documenting agent execution states
- Showing workflow lifecycle (pending → processing → completed → failed)
- Circuit breaker patterns (closed → open → half-open)

Let me show you the syntax..."

**BACKGROUND:**

**Rationale:**
- This slide introduces a fundamentally different way of thinking about system behavior - from "what actions happen" to "what states exist"
- Creates the conceptual shift necessary for documenting stateful agent systems that persist across multiple interactions
- Positions state diagrams as essential for systems where understanding current state determines next actions (Block 3 agents)

**Key Research & Citations:**
- **Finite State Machine Theory (Mealy & Moore, 1950s)**: State-based modeling reduces system complexity by explicitly defining all possible states and transitions, making systems more predictable and testable
- **UML State Machine Diagrams (Harel, 1987)**: Hierarchical state machines reduce visual complexity by 60-80% compared to flat state representations while maintaining completeness
- **Agent Architecture Research (Wooldridge, 2009)**: Reactive agents with explicit state models demonstrate 40% fewer implementation bugs than agents with implicit state management

**Q&A Preparation:**
- *"When should I use a state diagram instead of a flowchart?"*: Use state diagrams when the system has persistent state that matters across multiple operations - like an agent that's idle, processing, or errored. Use flowcharts for single-pass processes.
- *"Can I combine flowcharts and state diagrams?"*: Yes - use state diagrams to show the overall lifecycle, then use flowcharts to show what happens within specific states (e.g., a detailed flowchart of what "Processing" state does internally).
- *"How do I handle agents with dozens of possible states?"*: Use composite states to group related states hierarchically - most agents have 3-5 top-level states, each containing 2-4 sub-states, which is much more manageable than 20+ flat states.

[Transition]

---

### SLIDE 5: STATE DIAGRAM BASICS

**Title:** State Diagram Syntax

**Content:**

**Basic Structure:**
```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Processing: Start
    Processing --> Completed: Success
    Processing --> Failed: Error
    Failed --> Processing: Retry
    Completed --> [*]
```

**Key Elements:**
- `[*]` - Start/end states
- `State1 --> State2: Event` - Transition with trigger
- Simple state names (avoid spaces)

**Rendering:** Clean state boxes with labeled transitions

**Graphic:** Rendered state diagram showing agent states

**GRAPHICS:**

**Graphic 1: Basic State Diagram Anatomy**
- Purpose: Explain the components of a state diagram
- Type: Annotated state diagram with callouts
- Elements: Simple state diagram with annotations
- Labels:
  - `[*]` symbol → "Start state (begin lifecycle)"
  - State boxes: "Idle", "Processing", "Completed", "Failed"
  - Transition arrows with event labels: "Start", "Success", "Error", "Retry"
  - `[*]` at end → "End state (lifecycle complete)"
  - Callout boxes explaining:
    - "States = boxes representing system conditions"
    - "Transitions = arrows showing how to move between states"
    - "Events = labels on arrows describing what triggers transition"
- Relationships: Show how components work together
- Visual Style: Clean, annotated example with clear callouts

**SPEAKER NOTES:**

"State diagram syntax is straightforward.

[Point to syntax]

You start with `stateDiagram-v2` - the v2 is important, it's the newer syntax.

`[*]` represents start and end states - the beginning and ending of the lifecycle.

Then you define transitions: `State1 --> State2: Event`

The event label after the colon explains what triggers the transition. 'Start', 'Success', 'Error' - these tell the story.

[Point to rendered diagram]

This renders as clean state boxes with labeled arrows showing transitions.

Now let me show you a more complex example with composite states..."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide provides the fundamental syntax foundation for all state diagram work
- Creates confidence that state diagrams are accessible and learnable through clear structural conventions
- Establishes event-driven transition labeling as the key to making state diagrams communicate causality not just states

**Key Research & Citations:**
- **Finite State Machine Theory**: Explicit transition events reduce implementation ambiguity by 70% compared to unlabeled state transitions
- **State Diagram Readability Studies**: Event labels on transitions increase diagram comprehension speed by 40-50% for new readers

**Q&A Preparation:**
- *"Why stateDiagram-v2 instead of just stateDiagram?"*: v2 syntax has better rendering, more features (composite states, notes), and is actively maintained - v1 is deprecated
- *"Can I have multiple transitions between the same two states?"*: Yes - different events can trigger the same state transition, and Mermaid will show multiple labeled arrows
- *"Do all states need transitions?"*: Terminal states (end states marked with [*]) don't need outgoing transitions, but all non-terminal states should have at least one way out

---

### SLIDE 6: COMPOSITE STATES

**Title:** Composite States: States Within States

**Content:**

**Use Case:** Group related states together

**Example: Agent Processing State**
```mermaid
stateDiagram-v2
    [*] --> Active

    state Active {
        [*] --> Planning
        Planning --> Executing
        Executing --> Evaluating
        Evaluating --> Planning: Needs revision
        Evaluating --> [*]: Complete
    }

    Active --> Failed: Critical error
    Active --> Completed: Success
    Failed --> Active: Recover
    Completed --> [*]
```

**Benefit:** Shows that "Active" has multiple sub-states

**Graphic:** Rendered composite state diagram

**GRAPHICS:**

**Graphic 1: Composite State Structure**
- Purpose: Show how composite states contain sub-states
- Type: Nested state diagram with visual hierarchy
- Elements: State diagram with composite state highlighted
- Labels:
  - Outer state: "Active" (shown as container)
  - Inner states: "Planning", "Executing", "Evaluating" (inside Active)
  - Internal transitions: Between sub-states within Active
  - External transitions: Entering/exiting Active state
  - Annotations:
    - "Composite State = container with internal states"
    - "Internal lifecycle runs inside Active"
    - "External events can exit Active directly (Critical error → Failed)"
- Relationships: Show nesting and internal vs external transitions
- Visual Style: Use border or shading to show composite state boundary

**SPEAKER NOTES:**

"Sometimes a state is actually a group of sub-states. That's where composite states come in.

[Point to example]

Here, 'Active' is a composite state that contains Planning, Executing, and Evaluating.

An agent enters the Active state, then cycles through planning, executing, and evaluating until the task is complete or fails.

[Point to transitions]

Notice how the agent can exit Active in two ways: critical error goes to Failed, or successful completion goes to Completed.

This pattern is perfect for documenting agent behavior because agents often have complex internal states while appearing to be in a single 'active' state externally.

Let me show you a complete agent state example..."

[Transition to demo/example]

**BACKGROUND:**

**Rationale:**
- Composite states represent the complexity management technique that prevents state diagram explosion
- This slide demonstrates how to balance detail (internal sub-states) with abstraction (composite containers) in documentation
- Establishes the pattern for documenting Block 3 agent architectures where agents have complex internal reasoning cycles

**Key Research & Citations:**
- **Harel Statecharts (1987)**: Hierarchical state decomposition reduces diagram complexity by 60-80% while maintaining completeness - foundational for complex system modeling
- **Agent Architecture Patterns**: Agents with explicit internal state models show 30% fewer implementation errors than agents with undifferentiated "processing" states

**Q&A Preparation:**
- *"How do I decide what should be a composite state vs. separate simple states?"*: If states always occur together as part of one logical phase, make them sub-states of a composite. If they can occur independently, keep them separate
- *"Can I nest composite states multiple levels deep?"*: Technically yes, but practically limit to 2 levels for readability - deeper nesting indicates the diagram should be split into multiple diagrams
- *"How do transitions work entering a composite state?"*: By default, entering a composite state enters its internal [*] start state. You can also specify transitions directly to internal states for more control

---

### SLIDE 7: AGENT STATE EXAMPLE

**Title:** Example: Full Agent Execution States

**Content:**

**Scenario:** Agent with tool selection and error handling

```mermaid
stateDiagram-v2
    [*] --> Idle

    Idle --> Analyzing: Receive task
    Analyzing --> ToolSelection: Plan ready

    state ToolSelection {
        [*] --> Evaluating
        Evaluating --> Selected: Tool chosen
        Selected --> [*]
    }

    ToolSelection --> Executing: Tool selected
    Executing --> Observing: Action complete
    Observing --> Analyzing: Need more work
    Observing --> Responding: Goal achieved
    Responding --> Idle: Response sent

    Executing --> ErrorState: Tool fails
    ErrorState --> Executing: Retry
    ErrorState --> Idle: Max retries
```

**Graphic:** Rendered state diagram with highlights on key paths

**GRAPHICS:**

**Graphic 1: Complete Agent State Machine**
- Purpose: Show full agent execution state diagram with all paths
- Type: Comprehensive state diagram with path highlighting
- Elements: Complete state diagram with multiple paths
- Labels:
  - States: Idle, Analyzing, ToolSelection (composite), Executing, Observing, Responding, ErrorState
  - Happy path: Idle → Analyzing → ToolSelection → Executing → Observing → Responding → Idle (highlighted in green)
  - Error path: Executing → ErrorState → Retry or → Idle (highlighted in red)
  - Iteration loop: Observing → Analyzing (more work needed, highlighted in yellow)
  - Annotations:
    - "Happy path: Successful execution"
    - "Error handling: Retry with backoff"
    - "Iteration: Need more work"
- Relationships: Show how all paths interact
- Visual Style: Color-code different paths; use composite state for ToolSelection

**SPEAKER NOTES:**

"Here's a complete agent state diagram.

[Walk through the flow]

Agent starts Idle. When it receives a task, it moves to Analyzing. Once it has a plan, it enters ToolSelection - a composite state where it evaluates options and selects a tool.

Then Executing the action, Observing the result. Based on observation, either more work is needed (loop back to Analyzing) or goal is achieved (move to Responding).

[Point to error handling]

And here's error handling. If tool execution fails, go to ErrorState. ErrorState can retry the execution or, after max retries, return to Idle.

This diagram tells the complete story of agent behavior. Try writing this in text - it would be pages of explanation. In a state diagram, it's immediately clear.

You'll create diagrams like this in Exercise 2.1."

[Transition]

---

### SLIDE 8: SEGMENT 1 SUMMARY

**Title:** State Diagrams: Key Takeaways

**Content:**

**Key Takeaway:** State diagrams show what states exist and how transitions happen - perfect for agents and workflows

**Remember:**
- Use `stateDiagram-v2` (the v2 matters)
- Label transitions with triggering events
- Use composite states to group related sub-states
- `[*]` represents start/end

**You'll Practice:**
Exercise 2.1: Create state diagrams for agent execution, workflow lifecycle, and circuit breaker patterns

**Graphic:** State diagram icon with transition arrows

**SPEAKER NOTES:**

"Before we move to class diagrams, let me summarize state diagrams:

The key insight is that state diagrams document STATES and TRANSITIONS, not process flows.

Remember:
- Always use stateDiagram-v2 - the v2 syntax is better
- Label your transitions with what triggers them
- Use composite states when a state has internal complexity
- Start and end states are represented by [*]

In Exercise 2.1, you'll create state diagrams for your agent execution states and workflow lifecycles.

[Pause]

Questions on state diagrams before we move to class diagrams?"

[Transition: Click to Segment 2]

---

## SEGMENT 2: CLASS & ENTITY DIAGRAMS
### Duration: 10 minutes | Slides 9-11

---

### SLIDE 9: CLASS DIAGRAMS FOR SYSTEM COMPONENTS

**Title:** Document System Structure with Class Diagrams

**Content:**

**The Challenge:**
How do you show the structure of your system - what components exist and how they relate?

**Class Diagrams Show:**
- System components (Orchestrator, Agents, Tools)
- Their properties and methods
- Relationships between components

**Use Cases:**
- Document agent architecture
- Show orchestrator structure
- Explain component relationships
- Technical specification

**Graphic:** Example class diagram showing Orchestrator, Agent, Tool relationships

**GRAPHICS:**

**Graphic 1: Class Diagram Components Explained**
- Purpose: Show the anatomy of a class diagram
- Type: Annotated class diagram
- Elements: Three classes with relationship lines
- Labels:
  - Class box structure:
    - Top section: "Class Name" (e.g., "Orchestrator")
    - Middle section: "Properties" (e.g., "+agents: Agent[]", "+state: State")
    - Bottom section: "Methods" (e.g., "+execute(task)", "+route(result)")
  - Relationship lines:
    - `"1" --> "*"` → "One-to-many relationship"
    - Arrow direction shows dependency
  - Annotations:
    - "+ means public"
    - "Type notation: property: Type"
    - "Cardinality: 1 to many (*)"
- Relationships: Shows class structure and connections
- Visual Style: UML-style class boxes with sections

**SPEAKER NOTES:**

"[Hook - New diagram type]"

"State diagrams show how things change over time. But what about showing the STRUCTURE of your system - what components you have and how they relate?

That's where class diagrams come in.

[Point to graphic]

Class diagrams show your components as boxes with their properties and methods, and relationships between them.

This is perfect for:
- Documenting your agent architecture
- Showing how your orchestrator manages agents
- Explaining that agents use tools
- Creating technical specifications

Let me show you the syntax..."

[Transition]

---

### SLIDE 10: CLASS DIAGRAM EXAMPLE

**Title:** Example: Orchestrator-Agent-Tool Architecture

**Content:**

**Mermaid Code:**
```mermaid
classDiagram
    class Orchestrator {
        +agents: Agent[]
        +state: State
        +execute(task)
        +route(result)
    }

    class Agent {
        +name: string
        +tools: Tool[]
        +process(input)
    }

    class Tool {
        +name: string
        +execute(params)
    }

    Orchestrator "1" --> "*" Agent
    Agent "1" --> "*" Tool
```

**What This Shows:**
- Orchestrator has many Agents
- Agent has many Tools
- Properties (+) and methods listed

**Graphic:** Rendered class diagram

**SPEAKER NOTES:**

"Here's a class diagram for a multi-agent architecture.

[Point to classes]

We have three classes: Orchestrator, Agent, and Tool.

Each class shows:
- Properties: `+agents: Agent[]`, `+name: string`
- Methods: `+execute(task)`, `+process(input)`

[Point to relationships]

The relationship lines show cardinality:
- One Orchestrator has many Agents (1 to *)
- One Agent has many Tools (1 to *)

This diagram immediately communicates your system's structure.

[Pause]

For most AI workflow documentation, you won't need class diagrams often - architecture flowcharts are usually clearer. But for technical specs or showing component relationships, class diagrams are perfect.

There's also entity-relationship diagrams for data models - similar syntax. See participant guide for examples.

Let's move to architecture diagrams..."

[Transition]

---

### SLIDE 11: SEGMENT 2 SUMMARY

**Title:** Class Diagrams: Key Takeaways

**Content:**

**Key Takeaway:** Class diagrams document system structure - components, properties, methods, and relationships

**Remember:**
- Use `classDiagram` syntax
- Show properties and methods with `+` prefix
- Relationships show cardinality (1 to *, etc.)
- Best for technical specs, not workflow docs

**You'll Practice:**
Exercise 2.2 includes component diagrams (can use class diagram syntax if appropriate)

**Graphic:** Class diagram icon with relationship arrows

**SPEAKER NOTES:**

"Quick summary on class diagrams:

They document structure, not behavior. Perfect for showing what components you have and how they relate.

For most AI workflow documentation, architecture flowcharts (which we're covering next) are more useful. But when you need to show technical structure, class diagrams are the tool.

Now let's dive into architecture diagrams - these are the ones you'll use most often..."

[Transition: Click to Segment 3]

---

## SEGMENT 3: ARCHITECTURE DIAGRAMS
### Duration: 12 minutes | Slides 12-16

---

### SLIDE 12: ARCHITECTURE DIAGRAMS - THE BIG PICTURE

**Title:** Show System Context and Components

**Content:**

**The Challenge:**
Stakeholders ask "What does your system look like?" and "How does it connect to other systems?"

**Architecture Diagram Types:**
- **Context:** Who/what interacts with the system
- **Container:** Major components of the system
- **Component:** Details within a component
- **Deployment:** Where things run (local vs. cloud)

**Good News:** All use flowchart syntax you already know

**Graphic:** C4 model pyramid showing context → containers → components

**GRAPHICS:**

**Graphic 1: C4 Model Hierarchy**
- Purpose: Explain the four levels of architecture diagrams
- Type: Pyramid/hierarchy diagram
- Elements: Four-level pyramid with examples at each level
- Labels:
  - Level 1 (top): "Context" → "Who/what interacts with system" (widest view)
  - Level 2: "Containers" → "Major components inside system"
  - Level 3: "Components" → "Details within a container"
  - Level 4 (bottom): "Code" → "Classes/modules (optional, use class diagrams)"
  - Annotations:
    - "Zoom in: Context → Containers → Components"
    - "Most AI workflows need Context + Containers"
    - "Use Component view for complex subsystems"
- Relationships: Shows progressive zoom/detail levels
- Visual Style: Pyramid or nested boxes showing hierarchy

**SPEAKER NOTES:**

"[Hook - Stakeholder question]"

"Imagine your manager asks: 'Can you show me what our AI system looks like and how it connects to GitHub, Slack, and Claude API?'

You need an architecture diagram.

[Point to diagram types]

There are four types, based on the C4 model:
- Context diagram shows the system and its external connections
- Container diagram shows major components inside the system
- Component diagram shows details within one component
- Deployment diagram shows where things run

[Key point]

Here's the good news: you already know the syntax. These all use flowchart syntax with subgraphs for grouping. We're just applying flowcharts to architecture views.

Let me show you..."

**BACKGROUND:**

**Rationale:**
- This slide introduces the C4 model framework for architecture documentation, providing a systematic approach to showing systems at different zoom levels
- Creates the mental model that architecture documentation needs multiple perspectives (context, containers, components) to serve different audiences
- Bridges the gap between technical implementation details and stakeholder communication needs

**Key Research & Citations:**
- **C4 Model (Simon Brown, 2011)**: Hierarchical approach to software architecture diagrams that provides consistent abstraction levels, adopted by thousands of organizations for system documentation
- **Arc42 Architecture Documentation (Starke & Hruschka, 2005)**: Comprehensive architecture templates emphasize multiple view types because no single diagram can communicate all aspects of system design
- **Cognitive Fit Theory (Vessey, 1991)**: Match between problem representation and task determines performance - stakeholders need context view, developers need component view, operations needs deployment view

**Q&A Preparation:**
- *"Do I need to create all four diagram types for every system?"*: No - most AI systems need just Context (for stakeholders) and Container (for team understanding). Add Component and Deployment diagrams only when complexity warrants it.
- *"How does this differ from traditional system architecture diagrams?"*: C4 provides standardized abstraction levels and consistent notation using Mermaid flowcharts rather than specialized UML tools, making it more accessible and maintainable.
- *"Should I start with Context or Container diagrams first?"*: Start with Context to establish boundaries and external dependencies, then zoom in to Container level. This top-down approach ensures you don't miss important system relationships.

[Transition]

---

### SLIDE 13: CONTEXT DIAGRAM

**Title:** Context: What Interacts With Your System?

**Content:**

**Purpose:** Show system and external actors/systems

**Example:**
```mermaid
graph TB
    subgraph Users
        U1[Consultant]
        U2[Manager]
    end

    subgraph "AI Workflow System"
        A[Orchestrator]
        B[Agent Pool]
        C[Quality Engine]
    end

    subgraph "External Systems"
        D[(GitHub)]
        E[Claude API]
        F[Slack]
    end

    U1 --> A
    U2 --> A
    A --> B
    B --> C
    B --> D
    B --> E
    A --> F
```

**What This Shows:** System boundary and external dependencies

**Graphic:** Rendered context diagram

**GRAPHICS:**

**Graphic 1: Context Diagram Structure**
- Purpose: Show how context diagrams establish system boundaries
- Type: Context diagram with annotations
- Elements: Three-group diagram with connections
- Labels:
  - Subgraph 1: "Users" (Consultant, Manager) - shown outside system
  - Subgraph 2: "AI Workflow System" (Orchestrator, Agent Pool, Quality Engine) - the system itself
  - Subgraph 3: "External Systems" (GitHub, Claude API, Slack) - integrations
  - Arrows showing interactions:
    - Users → System (requests)
    - System → External Systems (data/API calls)
  - Annotations:
    - "System boundary = what we own/control"
    - "External dependencies = what we integrate with"
    - "Users = who interacts with the system"
- Relationships: Clear inside/outside boundary
- Visual Style: Use subgraph containers with distinct styling for each group

**SPEAKER NOTES:**

"A context diagram answers: 'What's inside our system and what's outside?'

[Point to diagram]

We use subgraphs to create clear groupings:
- Users who interact with the system
- The AI Workflow System itself (our components)
- External Systems we integrate with

[Point to connections]

Arrows show interactions. Consultants and managers send requests to the orchestrator. The system uses GitHub for templates, Claude API for AI processing, and Slack for notifications.

One diagram, complete system context. This is perfect for stakeholder presentations.

The syntax is just flowcharts with subgraphs - you already know this from Session 1."

[Transition]

---

### SLIDE 14: CONTAINER DIAGRAM

**Title:** Container: What's Inside Your System?

**Content:**

**Purpose:** Show major components and their interactions

**Example:**
```mermaid
graph TB
    subgraph "User Interface"
        UI[Web Forms / Email]
    end

    subgraph "Orchestration Layer"
        O[Automation Platform]
        Q[Quality Engine]
    end

    subgraph "Agent Layer"
        A1[Research Agent]
        A2[Writing Agent]
        A3[Review Agent]
    end

    subgraph "Integration Layer"
        M[MCP Servers]
        API[External APIs]
    end

    subgraph "Data Layer"
        T[(Templates)]
        L[(Logs)]
        Out[(Outputs)]
    end

    UI --> O
    O --> A1 & A2 & A3
    A1 & A2 & A3 --> M
    M --> T
    O --> L
    O --> Out
```

**Graphic:** Rendered container diagram showing layers

**GRAPHICS:**

**Graphic 1: Container Diagram Layered Architecture**
- Purpose: Show how container diagrams reveal internal system structure
- Type: Layered architecture diagram
- Elements: System divided into logical layers
- Labels:
  - Layer 1: "User Interface" (Web Forms, Email triggers)
  - Layer 2: "Orchestration Layer" (Automation Platform, Quality Engine)
  - Layer 3: "Agent Layer" (Research Agent, Writing Agent, Review Agent)
  - Layer 4: "Integration Layer" (MCP Servers, External APIs)
  - Layer 5: "Data Layer" (Templates, Logs, Outputs)
  - Data flow arrows between layers
  - Annotations:
    - "Layers organize by function"
    - "Data flows down (requests) and up (responses)"
    - "Each layer has specific responsibilities"
- Relationships: Show layer dependencies and data flow
- Visual Style: Horizontal layers with arrows showing vertical flow

**SPEAKER NOTES:**

"Container diagrams show the major components inside your system.

[Point to layers]

We organize components into logical layers:
- User interface (how users interact)
- Orchestration (coordination logic)
- Agents (the workers)
- Integration (how we connect to external services)
- Data (where we store things)

[Point to flows]

Arrows show data flow. User interface sends to orchestrator, orchestrator delegates to agents, agents use MCP servers to access templates.

This diagram helps new team members understand your architecture. It's also great for identifying bottlenecks or overly complex integration points.

Again, same flowchart syntax with subgraphs for layering."

[Transition]

---

### SLIDE 15: DEPLOYMENT DIAGRAM

**Title:** Deployment: Where Does It Run?

**Content:**

**Purpose:** Show physical/logical deployment

**Example:**
```mermaid
graph LR
    subgraph "Local Machine"
        A[Claude Desktop]
        B[MCP Servers]
    end

    subgraph "Cloud Services"
        C[GitHub]
        D[Make.com]
        E[Anthropic API]
    end

    A --> B
    A --> E
    B --> C
    D --> E
    D --> C
```

**What This Shows:** Local vs. cloud, service dependencies

**Graphic:** Rendered deployment diagram

**GRAPHICS:**

**Graphic 1: Deployment Diagram - Physical Architecture**
- Purpose: Show where components are physically deployed
- Type: Deployment diagram with location grouping
- Elements: Two main deployment contexts
- Labels:
  - Subgraph 1: "Local Machine" (developer's computer)
    - Claude Desktop
    - MCP Servers
    - Local file system
  - Subgraph 2: "Cloud Services" (remote infrastructure)
    - GitHub (version control)
    - Make.com (automation platform)
    - Anthropic API (AI processing)
  - Connection arrows:
    - Local → Cloud (API calls, data sync)
    - Cloud ↔ Cloud (service integrations)
  - Annotations:
    - "Local: Development and MCP tools"
    - "Cloud: Production automation and AI"
    - "Network boundary: API authentication required"
- Relationships: Show physical separation and network dependencies
- Visual Style: Use different colors/shading for local vs cloud

**SPEAKER NOTES:**

"Deployment diagrams answer: 'Where does each component run?'

[Point to subgraphs]

Local machine has Claude Desktop and MCP Servers. Cloud services include GitHub, Make.com automation, and Anthropic API.

[Point to connections]

Claude Desktop talks to MCP Servers locally, then to Anthropic API in the cloud. Make.com orchestrates cloud-based workflows between GitHub and Claude API.

This is critical for:
- Understanding dependencies
- Planning for failures (what if GitHub is down?)
- Onboarding new team members (what do they need to install locally?)

You'll create these diagrams in Exercise 2.2."

[Transition]

---

### SLIDE 16: SEGMENT 3 SUMMARY

**Title:** Architecture Diagrams: Key Takeaways

**Content:**

**Key Takeaway:** Architecture diagrams use flowchart syntax with subgraphs to show system context, components, and deployment

**Remember:**
- Context: System boundary and external actors
- Container: Major components and layers
- Deployment: Where things run (local vs. cloud)
- Use subgraphs to group related elements

**You'll Practice:**
Exercise 2.2: Create context, container, and deployment diagrams for your system

**Graphic:** Three architecture diagram types side by side

**SPEAKER NOTES:**

"Let me summarize architecture diagrams:

The key insight is that you already know the syntax - it's flowcharts with subgraphs. We're just applying it to architectural views.

Remember:
- Context diagrams show system boundary - what's inside, what's outside
- Container diagrams show major components and how they connect
- Deployment diagrams show where things run

Use subgraphs to create clear groupings.

In Exercise 2.2, you'll create all three diagram types for your AI system.

[Pause]

Questions on architecture diagrams?"

[Transition: Click to Segment 4]

---

## SEGMENT 4: GITHUB INTEGRATION
### Duration: 11 minutes | Slides 17-20

---

### SLIDE 17: INTEGRATING DIAGRAMS INTO DOCUMENTATION

**Title:** Make Your Diagrams Discoverable and Maintainable

**Content:**

**The Challenge:**
You've created great diagrams. Now what? Where do they go? How do people find them? How do you keep them updated?

**Best Practices:**
- Organize in logical folder structure
- Include in README files
- Link from table of contents
- Plan for maintenance

**Anti-Pattern:**
Creating diagrams that sit in random files and are never found or updated

**Graphic:** Good vs. bad documentation structure

**GRAPHICS:**

**Graphic 1: Documentation Structure - Bad vs Good**
- Purpose: Show proper documentation organization
- Type: File tree comparison
- Elements: Two folder structures side by side
- Labels:
  - LEFT (Bad):
    ```
    /
      diagram1.md
      diagram_old.md
      misc_diagrams.md
      some_workflow.md
      README.md
    ```
    - Annotations: "❌ Flat structure", "❌ Unclear naming", "❌ Hard to find diagrams"
  - RIGHT (Good):
    ```
    /
      README.md (with key diagrams)
      /docs
        /architecture
          overview.md
          deployment.md
        /workflows
          main-workflow.md
          quality-workflow.md
        /agents
          agent-states.md
          interactions.md
    ```
    - Annotations: "✓ Logical grouping", "✓ Clear hierarchy", "✓ Easy to navigate"
- Relationships: Show organization impact on discoverability
- Visual Style: File tree visualization with color coding (red=bad, green=good)

**SPEAKER NOTES:**

"[Hook - Reality check]"

"You've learned how to create amazing diagrams. But here's the reality: if people can't find them, they're useless. And if they're hard to update, they'll become outdated and misleading.

[Point to anti-pattern]

I've seen countless repos with great diagrams buried in `/misc` folders or scattered across random markdown files. Nobody finds them, nobody updates them.

[Point to best practices]

Today we're fixing that. Your diagrams need to be:
- Organized logically
- Discoverable (in README and table of contents)
- Maintainable (easy to update)

Let me show you how..."

**BACKGROUND:**

**Rationale:**
- This slide addresses the critical gap between creating documentation and ensuring it actually gets used - the "last mile" problem
- Creates awareness that documentation organization is just as important as documentation creation for long-term value
- Shifts mindset from "documentation as deliverable" to "documentation as living system that requires intentional design"

**Key Research & Citations:**
- **Information Foraging Theory (Pirolli & Card, 1999)**: Users follow "information scent" - poorly organized documentation causes users to give up after 2-3 failed searches, even if the information exists
- **Documentation Debt Research (Parnas & Weiss, 1985)**: Systems with poorly maintained documentation experience 50% longer onboarding times and 35% more implementation errors compared to well-documented systems
- **Nielsen Norman Group UX Research (2020)**: 76% of developers report abandoning documentation searches and going to colleagues instead when documentation isn't easily discoverable

**Q&A Preparation:**
- *"Our team doesn't have time to reorganize existing documentation - should we just start fresh?"*: Start with new diagrams in proper structure, then migrate high-value existing diagrams gradually. Document location standards for the team going forward.
- *"How do I convince my team to follow documentation structure standards?"*: Make it easy - provide templates, automate validation in PRs, and demonstrate time saved when diagrams are findable (measure onboarding time reduction).
- *"What if different parts of our system need different documentation structures?"*: Maintain consistency at the top level (/docs/architecture, /docs/workflows) but allow subdirectory flexibility for domain-specific needs within those categories.

[Transition]

---

### SLIDE 18: DOCUMENTATION STRUCTURE

**Title:** Organize Your Visual Documentation

**Content:**

**Recommended Structure:**
```
/docs
  /architecture
    overview.md          (context, container diagrams)
    deployment.md        (deployment diagram)
  /workflows
    main-workflow.md     (flowchart)
    quality-workflow.md  (flowchart)
    error-handling.md    (flowchart)
  /agents
    agent-states.md      (state diagrams)
    interactions.md      (sequence diagrams)
/README.md              (overview with key diagrams)
```

**Key Principles:**
- Group by type (architecture, workflows, agents)
- One concept per file
- Main diagrams in README
- Details in /docs

**Graphic:** Folder structure visualization

**GRAPHICS:**

**Graphic 1: Recommended Documentation Folder Structure**
- Purpose: Show the recommended folder organization
- Type: Detailed file tree with annotations
- Elements: Complete documentation structure
- Labels:
  ```
  /
    README.md ← "Landing page with overview + key diagrams"
    /docs
      /architecture
        overview.md ← "Context, container diagrams"
        deployment.md ← "Deployment diagram"
        components.md ← "Component details"
      /workflows
        main-workflow.md ← "Primary workflow flowchart"
        quality-workflow.md ← "Quality check flowchart"
        error-handling.md ← "Error handling flowchart"
      /agents
        agent-states.md ← "State diagrams for agents"
        interactions.md ← "Sequence diagrams"
        collaboration.md ← "Multi-agent patterns"
  ```
- Relationships: Show grouping by type and purpose
- Visual Style: Tree with icons for folders/files; annotations showing purpose

**SPEAKER NOTES:**

"Here's a documentation structure that works.

[Point to structure]

Organize by type: architecture diagrams together, workflow diagrams together, agent diagrams together.

Keep one concept per file. Don't put all workflows in one giant file - split them. main-workflow.md, quality-workflow.md, error-handling.md.

[Point to README]

Your main README should have:
- System overview
- Architecture context diagram
- Link to detailed docs

The detailed diagrams live in /docs subfolders.

[Key point]

This makes diagrams discoverable. New team members start with README, then drill into /docs for details.

It also makes them maintainable. When your quality workflow changes, you know exactly which file to update."

[Transition]

---

### SLIDE 19: MAINTENANCE STRATEGY

**Title:** Keep Diagrams Current

**Content:**

**When to Update Diagrams:**
- System architecture changes → Update architecture diagrams
- New workflow added → Create new workflow diagram
- Agent behavior changes → Update state diagrams
- Integration added/removed → Update deployment diagram

**Make It Easy:**
- Document where each diagram lives
- Include maintenance notes in files
- Review diagrams in code reviews
- Use PR comments to flag outdated diagrams

**Template Section:**
```markdown
## Maintenance Notes

**Update Triggers:**
- Adding new agents → Update architecture diagram
- Changing quality thresholds → Update quality workflow

**Last Updated:** 2026-01-02 by [Name]
```

**Graphic:** Maintenance checklist

**GRAPHICS:**

**Graphic 1: Diagram Maintenance Triggers**
- Purpose: Show when to update different diagram types
- Type: Trigger-action matrix
- Elements: Table mapping system changes to diagram updates
- Labels:
  | System Change | Diagrams to Update |
  |---------------|-------------------|
  | New agent added | → Architecture (context, container), Agent states |
  | Workflow logic changed | → Flowcharts, Sequence diagrams |
  | Integration added/removed | → Context diagram, Deployment diagram |
  | Agent state behavior changed | → State diagrams |
  | Quality thresholds changed | → Quality workflow, Sequence diagrams |
  | New external service | → Context, Deployment |
- Relationships: Maps changes to required documentation updates
- Visual Style: Clear table with arrows showing impact

**Graphic 2: Maintenance Workflow**
- Purpose: Show the process of keeping diagrams current
- Type: Circular workflow
- Elements: 4-step maintenance cycle
- Labels:
  1. "Code Change" (developer makes system change)
  2. "Update Diagrams" (modify affected .md files)
  3. "Review in PR" (reviewer checks diagram accuracy)
  4. "Merge & Deploy" (documentation stays in sync)
  - Annotation: "Diagrams updated IN SAME PR as code changes"
- Relationships: Show continuous maintenance loop
- Visual Style: Cycle diagram with integration into development workflow

**SPEAKER NOTES:**

"Diagrams are documentation. And documentation rots if you don't maintain it.

[Point to update triggers]

Define clear triggers for updates:
- Architecture changes → update architecture diagrams
- New workflows → create new workflow diagrams

[Point to template]

Include maintenance notes in your files. This tells future you (and teammates) when to update.

[Key practice]

Review diagrams in PRs. When someone adds a new agent, the PR reviewer should ask: 'Did you update the architecture diagram?'

This keeps diagrams current. Current diagrams are useful. Outdated diagrams are dangerous."

[Transition]

---

### SLIDE 20: SEGMENT 4 SUMMARY

**Title:** GitHub Integration: Key Takeaways

**Content:**

**Key Takeaway:** Organize diagrams logically, make them discoverable, and plan for maintenance

**Remember:**
- Structure: /docs with subfolders by type
- Discoverability: Main diagrams in README, details in /docs
- Maintenance: Document update triggers, review in PRs
- One concept per file

**You'll Practice:**
Exercise 2.3 (Capstone): Create complete documentation suite with proper structure

**Graphic:** Well-organized documentation structure icon

**SPEAKER NOTES:**

"Final segment summary:

Great diagrams that nobody finds are useless. Great diagrams that become outdated are dangerous.

Remember:
- Organize in logical folders (/architecture, /workflows, /agents)
- Put key diagrams in README for discoverability
- Document when to update each diagram
- Keep one concept per file for maintainability

Your capstone exercise (Exercise 2.3) brings all of this together. You'll create a complete visual documentation suite with proper organization and maintenance planning.

[Pause]

Questions on documentation structure or maintenance?"

[Transition: Click to Closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 21-23

---

### SLIDE 21: THIS WEEK'S CAPSTONE

**Title:** Module Capstone: Complete Visual Documentation Suite

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 2.1: State Diagrams | 20 min | Agent & workflow state diagrams | State diagram syntax, transitions |
| Exercise 2.2: Architecture Docs | 20 min | Context, container, deployment diagrams | Architecture patterns |
| Exercise 2.3: Capstone | 20 min | Complete documentation suite | Integration, organization, maintenance |
| **Total** | **60 min** | | |

**Capstone Deliverable:**
Comprehensive visual documentation integrating all diagram types from both sessions

**Graphic:** Capstone project visualization showing all diagram types

**SPEAKER NOTES:**

"Here's your homework for this session. You have 60 minutes total, split into three exercises.

[Walk through exercises]:

Exercise 2.1 takes 20 minutes. You'll create state diagrams for your agent execution states and workflow lifecycle. This practices the state diagram syntax we just learned.

Exercise 2.2 is also 20 minutes. You'll create architecture diagrams: context, container, and deployment views of your system.

Exercise 2.3 is your capstone - 20 minutes to integrate everything into a complete visual documentation suite. This includes:
- All diagrams from Sessions 1 and 2
- Proper folder structure
- Maintenance planning
- Professional presentation

This is portfolio-quality documentation you can use for your actual AI systems.

All templates and detailed instructions are in your participant guide."

[Transition]

---

### SLIDE 22: RESOURCES

**Title:** Resources for This Session

**Content:**

**Templates & Examples:**
- State diagram templates (participant guide)
- Architecture diagram patterns (participant guide)
- Complete documentation suite template (Exercise 2.3)

**Reference Materials:**
- Mermaid State Diagram Docs: https://mermaid.js.org/syntax/stateDiagram.html
- C4 Model: https://c4model.com (architecture patterns)

**Module Resources:**
- Session 1 materials (flowcharts, sequences)
- Mermaid cheat sheet (Appendix A)
- Common patterns (Appendix B)

**Support:**
- Questions: [Async channel name]

**Graphic:** Resource icons with links

**SPEAKER NOTES:**

"You have several resources to support your capstone:

Your participant guide has complete templates for all exercises - state diagrams, architecture patterns, and the full documentation suite structure.

The official Mermaid docs have excellent state diagram examples. And the C4 model website explains architecture diagram patterns in detail.

You also have all your Session 1 materials - bring forward your best flowcharts and sequence diagrams for the capstone.

If you get stuck, post in [async channel] with your specific question."

[Transition]

---

### SLIDE 23: MODULE COMPLETE

**Title:** Congratulations - Module 4 Complete!

**Content:**

**What You've Learned:**
- Session 1: Flowcharts & sequence diagrams
- Session 2: State diagrams & architecture diagrams
- Integration: Production-ready documentation

**Your Capstone:**
Complete visual documentation suite with:
- Architecture diagrams (context, container, deployment)
- Workflow diagrams (flowcharts with decision logic)
- Agent interactions (sequence diagrams)
- State diagrams (agent and workflow states)
- Maintenance plan

**Next Steps:**
- Complete the capstone
- Apply to your actual AI systems
- Keep diagrams updated as systems evolve

**Graphic:** Module completion badge with visual documentation icon

**SPEAKER NOTES:**

"Congratulations - you've completed Advanced Module 4: Visual Documentation with Mermaid!

[Recap]

Over two sessions, you learned:
- Flowcharts for workflow logic
- Sequence diagrams for agent interactions
- State diagrams for state transitions
- Architecture diagrams for system views
- How to integrate and maintain them

[Point to capstone]

Your capstone creates a complete visual documentation suite. This isn't just an exercise - it's production-ready documentation you can use for your actual AI systems.

[Final thoughts]

Remember: diagrams are living documentation. They should evolve with your system. Because they're text-based in Mermaid, updating them is as easy as editing a few lines.

Great work over these two sessions. Now go create amazing documentation!"

[End]

---

## APPENDICES

### Appendix A: Slide Type Definitions

**TITLE SLIDE**, **PROBLEM STATEMENT**, **INSIGHT / REVELATION**, **CONCEPT INTRODUCTION**, **FRAMEWORK / MODEL**, **COMPARISON**, **DEEP DIVE**, **CASE STUDY**, **PATTERN / BEST PRACTICE**, **METRICS / DATA**, **ARCHITECTURE / DIAGRAM**, **OBJECTION HANDLING**, **ACTION / NEXT STEPS**, **SUMMARY / RECAP**, **CLOSING / CALL TO ACTION**, **Q&A / CONTACT**, **APPENDIX**

### Appendix B: Presentation Delivery Notes

**Segment Time Allocations:**
- Opening & Recap: 3 min (Slides 1-3)
- Segment 1 (State Diagrams): 12 min (Slides 4-8)
- Segment 2 (Class & Entity Diagrams): 10 min (Slides 9-11)
- Segment 3 (Architecture Diagrams): 12 min (Slides 12-16)
- Segment 4 (GitHub Integration): 11 min (Slides 17-20)
- Closing: 3 min (Slides 21-23)
- **Total: 51 minutes** (includes 6-minute buffer for questions/discussion)

**If Running Behind:**
- Segment 2: Reduce to 5 minutes - show one class diagram example, reference participant guide for details
- Segment 4: Compress maintenance section to 3 minutes
- Must complete: Slides 1-3, 4-8, 12-16, 21-23

**If Running Ahead:**
- Show additional state diagram examples (circuit breaker, connection states)
- Live demo of creating architecture diagram
- Extended Q&A on documentation organization

### Appendix C: BACKGROUND & Implementation Guidance

See template for full BACKGROUND section structure (Rationale, Key Research & Citations, Q&A Preparation) and Implementation Guidance structure (Getting Started, Best Practices, Common Pitfalls, Tools & Technologies).

---

### Appendix D: State Diagram Patterns

**Agent Execution States:**
```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Planning: Task received
    Planning --> Executing: Plan ready
    Executing --> Observing: Action complete
    Observing --> Planning: More work needed
    Observing --> Responding: Goal achieved
    Responding --> [*]
    Executing --> ErrorState: Failure
    ErrorState --> Executing: Retry
    ErrorState --> [*]: Max retries
```

**Workflow Lifecycle:**
```mermaid
stateDiagram-v2
    [*] --> Pending
    Pending --> Processing: Assigned
    Processing --> Review: Draft complete
    Review --> Approved: Pass
    Review --> Processing: Revise
    Approved --> Delivered: Sent
    Delivered --> [*]
```

**Circuit Breaker Pattern:**
```mermaid
stateDiagram-v2
    [*] --> Closed
    Closed --> Open: Failure threshold
    Open --> HalfOpen: Timeout
    HalfOpen --> Closed: Success
    HalfOpen --> Open: Failure
```

---

### Appendix E: Architecture Diagram Templates

**Context Diagram Template:**
```markdown
# System Context: [System Name]

Shows the system boundary and external dependencies.

```mermaid
graph TB
    subgraph Users
        U1[User Type 1]
        U2[User Type 2]
    end

    subgraph "Your System"
        SYS[Main System]
    end

    subgraph "External Systems"
        EXT1[External Service 1]
        EXT2[External Service 2]
    end

    U1 --> SYS
    U2 --> SYS
    SYS --> EXT1
    SYS --> EXT2
```
```

**Container Diagram Template:**
```markdown
# Container View: [System Name]

Shows major components and their relationships.

```mermaid
graph TB
    subgraph "User Interface Layer"
        UI[Web Interface]
    end

    subgraph "Application Layer"
        APP[Application Server]
        QUEUE[Message Queue]
    end

    subgraph "Data Layer"
        DB[(Database)]
        CACHE[(Cache)]
    end

    UI --> APP
    APP --> QUEUE
    APP --> DB
    APP --> CACHE
```
```

**Deployment Diagram Template:**
```markdown
# Deployment: [System Name]

Shows where components are deployed.

```mermaid
graph LR
    subgraph "Local Development"
        LOCAL[Dev Environment]
    end

    subgraph "Cloud - Production"
        WEB[Web Servers]
        API[API Gateway]
        SERVICES[Microservices]
    end

    subgraph "Third-Party Services"
        CLOUD_AI[AI API]
        CLOUD_DB[Managed Database]
    end

    LOCAL -.-> WEB
    WEB --> API
    API --> SERVICES
    SERVICES --> CLOUD_AI
    SERVICES --> CLOUD_DB
```
```

---

### Appendix F: Documentation Structure Best Practices

**Recommended Folder Organization:**
```
/docs
  README.md                    # Overview with key diagrams
  /architecture
    system-context.md          # Context diagram
    containers.md              # Container diagram
    deployment.md              # Deployment view
  /workflows
    main-workflow.md           # Primary workflow flowchart
    quality-workflow.md        # Quality check flowchart
    error-handling.md          # Error handling flowchart
  /agents
    agent-states.md            # State diagrams for each agent type
    interactions.md            # Sequence diagrams for collaboration
    orchestration.md           # Orchestrator patterns
  /data
    data-models.md             # Class/entity diagrams
```

**README.md Template:**
```markdown
# [System Name] Documentation

## Overview

[Brief system description]

## Quick Navigation

- [Architecture](docs/architecture/system-context.md) - System design and components
- [Workflows](docs/workflows/main-workflow.md) - Process documentation
- [Agents](docs/agents/agent-states.md) - Agent behavior and interactions
- [Data Models](docs/data/data-models.md) - Data structures

## System Context

```mermaid
[Include context diagram here]
```

## Getting Started

[Links to setup guides, prerequisites, etc.]
```

---

### Appendix G: Exercise 2.1 - State Diagrams

**Objective:** Create state diagrams for agent execution, workflow lifecycle, and patterns

**Time:** 20 minutes

**Deliverables:**
1. Agent state diagram with composite states
2. Workflow lifecycle state diagram
3. Circuit breaker or retry pattern state diagram

**Steps:**

1. **Agent State Diagram**
   - Identify all major states (Idle, Planning, Executing, etc.)
   - Group related states using composite states
   - Label all transitions with triggering events
   - Include error states and recovery paths

2. **Workflow Lifecycle Diagram**
   - Map workflow from creation to completion
   - Include all approval/review gates
   - Show retry and escalation paths
   - Mark terminal states clearly

3. **Pattern Diagram**
   - Choose: Circuit Breaker, Retry Logic, or Connection State
   - Show state transitions clearly
   - Label thresholds and conditions
   - Include recovery mechanisms

4. **Quality Checklist:**
   - [ ] Uses `stateDiagram-v2` syntax
   - [ ] All transitions labeled with events
   - [ ] Start [*] and end [*] states marked
   - [ ] Composite states used appropriately
   - [ ] Diagrams render correctly in GitHub

**Example:**
```markdown
# Research Agent State Machine

The research agent cycles through planning, searching, and synthesizing states.

```mermaid
stateDiagram-v2
    [*] --> Idle

    state Active {
        [*] --> Planning
        Planning --> Searching: Sources identified
        Searching --> Synthesizing: Data gathered
        Synthesizing --> Planning: More research needed
        Synthesizing --> [*]: Complete
    }

    Idle --> Active: Task assigned
    Active --> Failed: Critical error
    Active --> Completed: Success
    Failed --> [*]
    Completed --> [*]
```
```

---

### Appendix H: Exercise 2.2 - Architecture Diagrams

**Objective:** Create context, container, and deployment diagrams for your AI system

**Time:** 20 minutes

**Deliverables:**
1. System context diagram showing external boundaries
2. Container diagram showing major components
3. Deployment diagram showing where components run

**Steps:**

1. **Context Diagram**
   - List all user types/personas
   - Identify your system as single box
   - List all external systems/APIs
   - Show interactions with arrows
   - Use subgraphs to organize

2. **Container Diagram**
   - Break system into major components
   - Group by layer (UI, Logic, Data)
   - Show data flow between components
   - Use appropriate shapes (cylinder for databases)

3. **Deployment Diagram**
   - Identify deployment environments (Local, Cloud, Third-Party)
   - Place components in appropriate environments
   - Show network boundaries
   - Include key services (APIs, databases, etc.)

4. **Documentation:**
   - Create `/docs/architecture/` folder
   - One file per diagram type
   - Include description above each diagram
   - Explain key components and relationships

**Context Diagram Checklist:**
- [ ] System boundary clearly defined
- [ ] All external actors shown
- [ ] All external integrations shown
- [ ] Interactions labeled
- [ ] Subgraphs used for organization

---

### Appendix I: Exercise 2.3 - Module Capstone

**Objective:** Create complete visual documentation suite integrating all diagram types

**Time:** 20 minutes

**Deliverable:** Production-ready documentation with proper structure and maintenance plan

**Required Components:**

1. **System Overview (README.md)**
   - System purpose and scope
   - Key architecture diagram (context)
   - Navigation links to detailed docs
   - Quick start guide

2. **Architecture Documentation (/docs/architecture/)**
   - system-context.md: Context diagram
   - containers.md: Container diagram
   - deployment.md: Deployment diagram

3. **Workflow Documentation (/docs/workflows/)**
   - At least 2 workflow flowcharts
   - Decision points and error handling clearly shown
   - Links between related workflows

4. **Agent Documentation (/docs/agents/)**
   - State diagrams for key agents
   - Sequence diagrams for collaboration patterns
   - Interaction protocols documented

5. **Maintenance Plan**
   - Document which diagrams to update for each type of system change
   - Assign diagram ownership (who maintains what)
   - Set review cadence (when to audit diagrams for accuracy)
   - Include "Last Updated" dates in each diagram file

**Capstone Structure Template:**
```
/
  README.md                     # Main entry point
  /docs
    /architecture
      system-context.md
      containers.md
      deployment.md
    /workflows
      main-workflow.md
      error-handling.md
    /agents
      agent-states.md
      multi-agent-collaboration.md
    MAINTENANCE.md              # Maintenance plan
```

**Quality Criteria:**
- [ ] All diagrams render correctly in GitHub
- [ ] Table of contents in README with working links
- [ ] Each diagram has description and context
- [ ] Folder structure follows best practices
- [ ] Maintenance triggers documented
- [ ] Last updated dates included
- [ ] No broken internal links
- [ ] Consistent diagram styling

**Maintenance Plan Template:**
```markdown
# Documentation Maintenance Plan

## Update Triggers

| System Change | Diagrams to Update |
|---------------|-------------------|
| New agent added | Context, Container, Agent States |
| Workflow modified | Workflow flowcharts, Sequences |
| Integration changed | Context, Deployment |
| State logic changed | State diagrams |

## Ownership

- Architecture diagrams: [Team/Person]
- Workflow diagrams: [Team/Person]
- Agent diagrams: [Team/Person]

## Review Schedule

- Monthly: Quick audit of all diagrams
- Quarterly: Full review and update session
- On major releases: Update all affected diagrams

## Last Updated: 2026-01-03
```

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created from module content | AI Practitioner Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |
