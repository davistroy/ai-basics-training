# **INSTRUCTOR GUIDE: ADVANCED MODULE 4 SESSION 2**
## **Advanced Diagrams & Integration**

**Module:** Advanced Module 4: Visual Documentation with Mermaid
**Session:** 2 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes (capstone included)

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Advanced diagram types (state, architecture) and integration into production docs |
| **Difficulty Level** | Medium - Builds on Session 1, adds new diagram types |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Optional - Can show state diagram or architecture diagram creation |
| **Tech Setup Needed** | VS Code with Mermaid Preview, GitHub repo, screen share |
| **Common Challenges** | State diagram syntax differences, organizing documentation structure |

---

## Navigation

**Session Navigation:** [← Session 1 Instructor Guide](../session-1/instructor-guide.md) | **Session 2**

**Related Materials:**
- [Session 2 Presentation Slides](presentation.md)
- [Session 2 Participant Guide](participant-guide.md)
- [Module 4 Main Document](../module-4-visual-documentation.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Session 2 materials | ☐ |
| Test diagrams | Create sample state and architecture diagrams | ☐ |
| Check examples | Verify all diagram examples render correctly | ☐ |
| Prepare backup | Screenshots of all diagram types | ☐ |
| Review Session 1 | Check participant submissions to gauge progress | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, VS Code preview | ☐ |
| Load presentation | Have slides ready | ☐ |
| Review timing | This session covers 4 diagram types - pace accordingly | ☐ |
| Prepare examples | Have state diagram and architecture diagram ready to show | ☐ |
| Check Session 1 completion | Know who completed exercises | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, VS Code, GitHub | ☐ |
| Test share | Verify screen sharing | ☐ |
| Welcome early arrivals | Ask about Session 1 - which diagrams they created | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Session 1 recap, preview | Quick pace |
| 0:03 | 12 min | Segment 1 | State diagrams | Most important new type |
| 0:15 | 10 min | Segment 2 | Class & entity diagrams | Can compress |
| 0:25 | 12 min | Segment 3 | Architecture diagrams | Critical for stakeholders |
| 0:37 | 11 min | Segment 4 | GitHub integration | Practical guidance |
| 0:48 | 3 min | Closing | Capstone preview, wrap-up | Must complete |
| **Total** | **51 min** | | | 6-min buffer |

### Timing Flexibility

**If Running Behind:**
- Segment 2: Compress to 5 minutes - show one class diagram example, reference participant guide
- Segment 4: Reduce maintenance discussion to 3 minutes
- Skip detailed folder structure walk-through, show one example

**If Running Ahead:**
- Segment 1: Show additional state diagram examples (circuit breaker, connection pool)
- Segment 3: Live demo creating architecture diagram
- Extended Q&A on real-world documentation challenges

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | Must complete - state diagrams are core. Skip Segment 2 if needed. |
| End Segment 3 | 0:37 | Must complete - architecture diagrams are most useful. Compress Segment 4. |
| Start Closing | 0:48 | Must start here to properly preview capstone |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants back
2. Quick recap of Session 1 (flowcharts, sequences)
3. Preview Session 2 (state, architecture, integration)
4. Set expectation: "Today we complete the toolkit"

**Opening Script:**
> "Welcome back to Module 4, Session 2. Last session you learned flowcharts and sequence diagrams. Quick poll - who completed all three exercises from Session 1?"

[Wait for show of hands - gauge completion rate]

> "Great. Today we're adding the final pieces: state diagrams for documenting how agents move through states, architecture diagrams for showing system structure, and integration practices to make your documentation actually useful. By the end, you'll have a complete visual documentation toolkit."

**Engagement Opportunity:**
> "Quick share: What's one diagram you created in Session 1 that made something clearer?"

[Wait for 1-2 responses - this reinforces value and primes them for today]

---

### Segment 1: State Diagrams (12 min)

**Learning Objective:** Create state diagrams to document agent and workflow states

**Slides:** 4-8

#### Content Delivery

**Key Point 1: Why State Diagrams (Slide 4)**
- Main message: Flowcharts show process flow, state diagrams show state transitions
- Example to use: Agent states (idle, analyzing, executing, observing)
- Common misconception: "Can't I just use a flowchart for this?" - No, different purposes

**Key Point 2: Basic Syntax (Slide 5)**
- Main message: `stateDiagram-v2` with `[*]` for start/end, transitions labeled with events
- Demonstration: Show simple 5-state diagram
- Participant relevance: Perfect for documenting agent behavior

**Key Point 3: Composite States (Slide 6)**
- Main message: States can contain sub-states
- Example walkthrough: Active state containing Planning → Executing → Evaluating
- Real-world application: Agent "active" state has internal complexity

**Key Point 4: Complete Example (Slide 7)**
- Main message: Full agent lifecycle with tool selection and error handling
- Practice preview: Exercise 2.1 creates diagrams like this

#### Demo Instructions (if time allows)

**Demo Duration:** 4 minutes (optional)

**Setup Required:**
- VS Code with blank .md file
- Preview pane open

**Demo Steps:**
1. **Create basic state diagram:**
   - Type `stateDiagram-v2`
   - Add start state: `[*] --> Idle`
   - Add transitions: `Idle --> Processing: Start`
   - Show preview
   - **Say:** "Notice the v2 - that's important, it's the newer syntax"

2. **Add composite state:**
   - Create state block with sub-states
   - Show how it renders as nested diagram
   - **Say:** "Composite states show that 'Active' has internal complexity"

**Demo Talking Points:**
> "The syntax is similar to flowcharts but the semantics are different. We're documenting STATES not STEPS..."

**Backup Plan:**
Use slides with screenshots if demo skipped due to time

#### Facilitation Notes

**Watch For:**
- Confusion between flowcharts and state diagrams - emphasize the distinction
- Forgetting "v2" in syntax - common mistake

**If Asked About "When do I use state vs. flow?":**
> "State diagrams document what states exist and how you transition between them. Flowcharts document what steps happen in a process. If you're asking 'what states can this be in?', use state. If you're asking 'what steps does this go through?', use flowchart."

**Transition to Segment 2:**
> "State diagrams document behavior. Now let's look at class diagrams which document structure..."

---

### Segment 2: Class & Entity Diagrams (10 min)

**Learning Objective:** Understand class diagrams for system components (brief - not heavily used)

**Slides:** 9-11

#### Content Delivery

**Key Point 1: Class Diagrams for Structure (Slide 9)**
- Main message: Class diagrams show components, properties, methods, relationships
- Visual to emphasize: Orchestrator-Agent-Tool example

**Key Point 2: Example (Slide 10)**
- Main message: Syntax shows classes with properties/methods and relationship cardinality
- Hands-on reference: See participant guide for more details

**Key Point 3: When to Use (Slide 11)**
- Main message: Best for technical specs, not workflow docs
- Real-world application: Most participants will use architecture flowcharts more often

#### Facilitation Notes

**Energy Check:**
This segment is shorter and less critical - keep pace brisk

**Recommended approach:** Show one clear example, acknowledge it's less commonly used than other types, reference participant guide for details

**Transition to Segment 3:**
> "Class diagrams are for structure. But for most AI documentation, you'll use architecture flowcharts - which we're covering next - much more often. These are the diagrams stakeholders ask for..."

---

### Segment 3: Architecture Diagrams (12 min)

**Learning Objective:** Create architecture diagrams showing system context and components

**Slides:** 12-16

#### Content Delivery

**Key Point 1: Architecture Overview (Slide 12)**
- Main message: Four diagram types (context, container, component, deployment) using flowchart syntax
- Framework/Pattern: C4 model adapted to Mermaid

**Key Point 2: Context Diagram (Slide 13)**
- Main message: System boundary and external actors/systems
- Example walkthrough: Users, AI System, External Systems as subgraphs

**Key Point 3: Container Diagram (Slide 14)**
- Main message: Major components inside the system organized in layers
- Demonstration: UI layer, Orchestration layer, Agent layer, etc.

**Key Point 4: Deployment Diagram (Slide 15)**
- Main message: Where components run (local vs. cloud)
- Real-world application: Critical for understanding dependencies

#### Practical Application

**Consulting Connection:**
> "When a client or manager asks 'show me the system', they're asking for a context or container diagram. These diagrams answer stakeholder questions in a way that flowcharts don't."

**Example Scenario:**
> "Imagine presenting your AI workflow to senior leadership. They don't need to see decision diamonds and retry loops. They need to see: what's our system, what external services do we depend on, what are the major components. That's what architecture diagrams do."

#### Facilitation Notes

**Common Confusion Point:**
Participants may not see the difference from flowcharts

**Clarification Approach:**
> "These ARE flowcharts syntactically. But we're applying flowchart syntax to architectural views. The difference is purpose and audience. Workflow flowcharts are for understanding logic. Architecture diagrams are for understanding system structure."

---

### Segment 4: GitHub Integration (11 min)

**Learning Objective:** Integrate diagrams into production-ready documentation

**Slides:** 17-20

#### Content Delivery

**Key Point 1: The Documentation Challenge (Slide 17)**
- Main message: Great diagrams that nobody finds are useless
- Example: Anti-pattern of diagrams scattered in random files

**Key Point 2: Documentation Structure (Slide 18)**
- Main message: Organize in /docs with subfolders by type
- Demonstration: Show folder structure example

**Key Point 3: Maintenance Strategy (Slide 19)**
- Main message: Document update triggers, review diagrams in PRs
- Practical application: Template section for maintenance notes

**Key Point 4: Summary (Slide 20)**
- Main message: Organization, discoverability, maintenance
- Capstone preview: Exercise 2.3 applies all of this

#### Closing This Segment

**Key Takeaway:**
> "Diagrams are only useful if people can find them and they stay current. Structure and maintenance planning make that happen."

**Connection to Homework:**
> "Your capstone (Exercise 2.3) creates a complete documentation suite with proper organization. This is production-ready documentation you can actually use."

---

### Closing (3 minutes)

**Slides:** 21-23

**Do Not Skip This Section**

#### Homework Preview

**Key Actions:**
1. Overview three exercises (state diagrams, architecture diagrams, capstone)
2. Emphasize capstone brings everything together
3. Note this is portfolio-quality deliverable
4. Point to resources

**Script:**
> "Your homework has three exercises totaling 60 minutes.
>
> Exercise 2.1: State diagrams for your agent and workflow states - 20 minutes.
> Exercise 2.2: Architecture diagrams (context, container, deployment) - 20 minutes.
> Exercise 2.3: Capstone - integrate everything into a complete documentation suite - 20 minutes.
>
> The capstone is your portfolio piece. It includes all diagram types from both sessions, proper organization, and maintenance planning. This is documentation you can actually ship.
>
> All templates are in your participant guide."

#### Resources and Support

> "You have templates for all diagram types. Your Session 1 materials are also resources - bring your best flowcharts and sequences into the capstone."

#### Module Close

> "Congratulations on completing Advanced Module 4. You now have a complete toolkit for visual documentation: flowcharts, sequences, state diagrams, and architecture diagrams. Use them to make your AI systems understandable."

#### Session Close

> "Questions? ... Excellent work over these two sessions. Now go document your systems!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: When should I use state diagrams vs. flowcharts?**
A: State diagrams show what states exist and how you transition between them (agent idle → analyzing → executing). Flowcharts show what steps happen in a process (input → validate → generate → check). Different purposes. If the question is "what states can this be in?", use state. If it's "what steps does this go through?", use flowchart.

**Q: Are architecture diagrams necessary if I have flowcharts?**
A: Yes - different audiences and purposes. Flowcharts show workflow logic (how the system processes tasks). Architecture diagrams show system structure (what components exist, how they connect). Stakeholders and new team members need architecture views. Daily workflow understanding needs flowcharts.

**Q: How detailed should my architecture diagrams be?**
A: Start high-level. Context diagram: major components only. Container diagram: one box per significant component. Don't show every function or micro-service. If your container diagram has >12 boxes, it's too detailed - create a separate component diagram for the complex parts.

### Technical Questions

**Q: Why stateDiagram-v2 and not just stateDiagram?**
A: v2 is the newer, better syntax with more features (composite states, notes, etc.). Always use v2. The old syntax still works but is deprecated.

**Q: Can I mix diagram types in one file?**
A: Technically yes - you can have multiple Mermaid code blocks in one file. But organizationally, keep one concept per file. Don't put workflow flowchart, agent sequence, and state diagram all in one file - split them.

**Q: How do I control layout in architecture diagrams?**
A: Limited control in Mermaid - it auto-layouts. Best approach: order your node definitions logically (inputs first, then processing, then outputs), use subgraphs for grouping, and choose direction (TD vs. LR) that works best. Don't try to pixel-perfect it.

### Scope Questions

**Q: Should I create all four architecture diagram types (context, container, component, deployment)?**
A: Depends on your needs. At minimum: context (system boundary) and container (major components). Deployment is critical if you have local + cloud complexity. Component diagrams are optional deep-dives into specific components.

**Q: How often should I update diagrams?**
A: Whenever the system changes in a way that makes the diagram inaccurate. New agent added? Update architecture. Workflow logic changed? Update workflow flowchart. Include diagram review in your PR checklist.

### Pushback/Objections

**Q: This seems like a lot of overhead to maintain.**
A: It's less than you think. Because diagrams are text, updating is editing a few lines, not dragging boxes in Visio. And because they're in PRs, reviewers catch outdated diagrams. The payoff is huge - new team members understand the system faster, stakeholders get clear pictures, bugs are easier to find with visual documentation.

**Q: Our stakeholders won't look at technical diagrams.**
A: That's why you create different diagrams for different audiences. Architecture context diagram for stakeholders (high-level, no jargon). Container diagram for team (moderate detail). Component diagram for developers (deep detail). Flowcharts for workflow understanding. Tailor to audience.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| State diagram syntax error | Check for "v2", verify [*] syntax | Use screenshot examples |
| Architecture diagram layout weird | Try different direction (TD vs. LR) | Reference participant guide examples |
| Screen share fails | Restart share | Use slide screenshots only |
| Participant confusion on diagram types | Use comparison table (flow vs. state vs. architecture) | Show concrete examples side-by-side |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Overwhelmed by diagram types | "Too many types to remember" | Reassure: "You learned flow/sequence in Session 1. State and architecture are just additions. Start with flow/sequence, add others as needed." |
| Can't see use cases | "When would I use state diagrams?" | Ask about their agents: "Does your agent have different states? Idle, processing, error? That's a state diagram." |
| Documentation structure confusing | "Where do I put all these files?" | Show concrete example, provide template structure in participant guide |
| Capstone seems overwhelming | "20 minutes isn't enough" | Clarify: "You're integrating existing diagrams, not creating from scratch. Templates provided." |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Session moving too fast | Many confused faces, few questions | Slow down Segment 3 (architecture), it's most important. Compress Segment 2 (class). |
| Session moving too slow | Ahead of schedule by 10+ min | Add live demo of architecture diagram, extended Q&A |
| Confused on state vs. flow | Repeated questions | Draw comparison table on slide, show both diagrams for same scenario |
| Too theoretical | "How does this apply to my work?" | Ask for specific examples from their systems, apply diagram types to them |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save chat questions | For FAQ updates |
| Note diagram types that confused people | For curriculum refinement |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording | ☐ |
| Answer pending questions in support channel | ☐ |
| Send capstone reminder with template links | ☐ |
| Document any common syntax errors encountered | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review capstone submissions | ☐ |
| Identify participants with excellent documentation suites (for showcase) | ☐ |
| Collect feedback on module usefulness | ☐ |
| Update instructor guide with lessons learned | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 2.1 | State diagram .md files | Participant's GitHub repo /docs/agents or /docs/states |
| 2.2 | Architecture diagram .md files | /docs/architecture |
| 2.3 | Complete visual documentation suite | README or /docs/visual-documentation.md |

### Progress Check Approach

**How to Verify Completion:**
- Check for state diagrams with `stateDiagram-v2` syntax
- Verify architecture diagrams use subgraphs for organization
- Capstone should integrate diagrams from Sessions 1 and 2
- Look for maintenance notes and documentation structure

**Red Flags Indicating Struggle:**
- State diagrams missing "v2" (will render incorrectly)
- Architecture diagrams too detailed (20+ nodes)
- Capstone missing integration (just individual diagrams, no structure)
- No maintenance planning

**Intervention Thresholds:**
- 1 exercise incomplete: Monitor
- Capstone not attempted: Reach out - may be overwhelmed
- Diagrams don't render: Syntax issue - quick fix available

---

## Week-Specific Notes

### What Makes This Session Unique

**Session 2 is the completion** - participants get full toolkit and create portfolio piece

**Special challenges:**
- More diagram types in less time than Session 1
- Integration concepts (documentation structure) are less concrete than syntax
- Capstone requires bringing together 2 weeks of work

**Critical concepts that need extra emphasis:**
- State vs. flow distinction (most common confusion)
- Architecture diagrams use flowchart syntax (reassure them they know this)
- Documentation organization (practical, not theoretical)

**Common failure points:**
- Forgetting "v2" in state diagram syntax
- Architecture diagrams becoming too detailed
- Capstone being a list of diagrams without integration or structure

**Connections to other content:**
- Builds on Session 1 flowcharts and sequences
- Capstone integrates all Module 4 learning
- Applicable to Block 2 and 3 systems (workflows and agents)

### Dependencies

**Builds On:**
- Session 1: Flowcharts, sequences, basic Mermaid syntax
- Block 2: GitHub documentation practices
- Block 3 (if applicable): Multi-agent architectures to document

**Sets Up:**
- Participants can now create comprehensive documentation for any AI system
- Portfolio-quality capstone can be shown to stakeholders

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| State diagram v1 syntax still in some docs online | Emphasize v2 is correct | Active |
| Architecture diagrams auto-layout can be unpredictable | Recommend trying TD vs. LR direction | Active |
| Class diagrams less useful than expected | De-emphasize, show briefly, reference guide | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- After state diagrams: "What's the difference between a state diagram and a flowchart?" (Answer: States vs. steps)
- After architecture: "Which diagram shows system boundary - context or container?" (Answer: Context)
- After integration: "Where should your main diagrams go?" (Answer: README, with details in /docs)

**Observable Behavior Indicating Understanding:**
- Head nodding during state diagram distinction
- Questions about applying to their specific systems
- Taking notes on documentation structure

**Observable Behavior Indicating Confusion:**
- Silence when asked about state vs. flow
- Questions about basic flowchart syntax (indicates Session 1 gaps)
- Overwhelmed expressions during architecture segment

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 2.1: Look for (1) stateDiagram-v2 syntax, (2) Composite states if applicable, (3) Transitions labeled with events
- Exercise 2.2: Look for (1) Subgraphs for organization, (2) Context diagram shows boundary clearly, (3) Deployment shows local vs. cloud
- Exercise 2.3: Look for (1) Integration of diagrams from both sessions, (2) Logical folder structure, (3) Maintenance notes present

**Common Issues to Flag:**
- Missing "v2" in state diagrams → Quick syntax fix
- Architecture diagrams overly complex → Guidance on abstraction levels
- Capstone lacks integration → Needs to understand documentation structure

### Capstone Quality Standards

**Portfolio-Quality Capstone Includes:**
- ✓ Architecture diagrams (context, container, deployment)
- ✓ Workflow flowcharts from Session 1
- ✓ Agent interaction sequences from Session 1
- ✓ State diagrams for agents/workflows
- ✓ Organized folder structure (/architecture, /workflows, /agents)
- ✓ README with overview and key diagrams
- ✓ Maintenance notes documenting update triggers
- ✓ All diagrams render correctly

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Quick poll: "On a scale of 1-5, how useful is visual documentation for your work?"
- Open question: "Which diagram type will you use most?"

**Improvement Log:**

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| | | | |

### Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial instructor guide created | AI Training Team |

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "State diagrams show states and transitions, flowcharts show process steps - different purposes"
2. "Architecture diagrams use flowchart syntax you already know - just applied to architectural views"
3. "Documentation structure determines whether diagrams are useful or ignored"

### If You Only Have Time For One Thing

State diagram basics and architecture context/container patterns (Slides 4-5, 12-14) - these are the new diagram types participants will use most.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| State vs. Flow | "State diagram is like a status board (what states exist), flowchart is like a recipe (what steps to follow)" | When explaining the distinction |
| Architecture layers | "Like a map - zooming out shows context, zooming in shows components" | When explaining context vs. container diagrams |
| Documentation structure | "Like organizing a library - books (diagrams) need shelves (/docs folders) and a catalog (README)" | When explaining why structure matters |

---
