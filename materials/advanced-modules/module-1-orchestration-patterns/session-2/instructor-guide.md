# **INSTRUCTOR GUIDE: ADVANCED MODULE 1 SESSION 2**
## **Team-Based Orchestration & Hybrid Patterns**

**Module:** Advanced Module 1 - Advanced Orchestration Patterns
**Session:** 2 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Team-Based orchestration with agent collaboration + Hybrid patterns combining Sequential, Parallel, and Team-Based |
| **Difficulty Level** | High (builds on Session 1, adds collaboration complexity) |
| **Prep Time Required** | 45 minutes |
| **Demo Required** | Yes - Team-Based collaboration with inter-agent communication |
| **Tech Setup Needed** | Automation platform with message passing or shared workspace capability, team scenario ready, backup interaction logs prepared |
| **Common Challenges** | Participants struggle with inter-agent communication implementation; confusion about when to use which pattern in Hybrid systems |

---

## Navigation

**Session Navigation:** [← Session 1 Instructor Guide](../session-1/instructor-guide.md) | **Session 2** | Advanced Module 1 Complete

**Related Materials:**
- [Session 2 Presentation Slides](presentation.md)
- [Session 2 Participant Guide](participant-guide.md)
- [Module 1 Main Document](../module-1-orchestration-patterns.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Session 2 materials including Appendices B & C | ☐ |
| Review Session 1 submissions | Check participant parallel implementations to understand starting point | ☐ |
| Test demo | Run through Team-Based demo showing agent-to-agent communication | ☐ |
| Check resources | Verify Appendix B team templates and Appendix C rubric are accessible | ☐ |
| Prepare backup | Create screenshots/logs showing team interactions in case demo fails | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video in MS Teams | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice transitions especially for complex Hybrid pattern explanation | ☐ |
| Prepare materials | Have team demo environment ready with 3+ agents configured | ☐ |
| Check participant readiness | Verify participants completed Session 1 exercises (parallel system working) | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, team demo platform, interaction logs, Hybrid architecture diagram | ☐ |
| Test share | Verify screen sharing works and demo is visible | ☐ |
| Welcome early arrivals | Ask about their Session 1 parallel implementations and learnings | ☐ |
| Start recording | If session is recorded for later review | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Session 1 recap, Session 2 preview | Acknowledge Session 1 work |
| 0:03 | 12 min | Segment 1 | Team-Based pattern fundamentals | Emphasize collaboration vs isolation |
| 0:15 | 12 min | Segment 2 | Designing agent teams | Role archetypes, team structures |
| 0:27 | 12 min | Segment 3 | Inter-agent communication | DEMO here - show message passing |
| 0:39 | 3 min | Segment 4 | Hybrid orchestration | Quick but powerful synthesis |
| 0:42 | 3 min | Closing | Capstone preview, resources, module complete | Emphasize capstone importance |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Segment 1: Reduce to single Team-Based example (content creation only)
- Segment 2: Show only Linear and Collaborative team structures, skip Hybrid example
- Segment 3: Demo one communication pattern only (Request-Response recommended)
- Segment 4: Show Hybrid concept without deep dive into design process

**If Running Ahead:**
- Segment 2: Deeper dive into team personality prompts with live co-creation
- Segment 3: Show both Request-Response AND Shared Workspace demos
- Add Q&A break between Segments 2 and 3 to address design questions

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | Skip anti-example on Slide 7, reference verbally |
| End Segment 2 | 0:27 | Condense Slide 10 prompts, show template only |
| Start Closing | 0:42 | Must start here - capstone preview cannot be compressed |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants to Session 2
2. Acknowledge Session 1 completion and parallel implementations
3. Preview Session 2 value: collaboration and sophistication
4. Set tone: this is advanced, high-value content

**Opening Script:**
> "Welcome to Session 2 of Advanced Module 1. Great work completing Session 1 - I saw several impressive parallel implementations in the exercises.
>
> Today we're elevating your orchestration skills. Session 1 gave you speed through Parallel execution. Today we add quality through Team-Based collaboration, and sophistication through Hybrid multi-pattern systems.
>
> By the end of today's session, you'll design agent teams that collaborate like expert consultants, and you'll know how to combine Sequential, Parallel, and Team-Based patterns into production-grade architectures."

**Engagement Opportunity:**
> "Quick show of hands: How many of you achieved 50%+ time reduction with your parallel implementation from Session 1?"

[Wait for hands - should see most participants]

> "Excellent. Today we optimize for quality, not just speed."

---

### Segment 1: Team-Based Pattern Fundamentals (12 minutes)

**Learning Objective:** Understand when and why Team-Based orchestration enables collaboration that Parallel cannot

**Slides:** 4-7

#### Content Delivery

**Key Point 1: Limitation of Parallel (Slide 4)**
- Main message: Parallel is fast but isolated - agents can't collaborate
- Example to use: Strategic report requiring Research → Analysis → Writing → Review
- Common misconception: "Can't we just make everything parallel?" - No, these have dependencies BUT benefit from collaboration

**Key Point 2: Team-Based Structure (Slide 5)**
- Main message: Agents with roles that communicate through shared workspace
- Demonstration: Draw or annotate the team workspace diagram
- Participant relevance: Mirrors how they work in consulting teams

**Key Point 3: When to Use Team-Based (Slide 6)**
- Main message: Use when collaboration improves quality, not when speed is only goal
- Practice preview: Exercise 2.1 requires choosing appropriate team structure
- **CRITICAL**: Emphasize trade-off - Team-Based is more complex and slower than Parallel

**Key Point 4: Real-World Examples (Slide 7)**
- Main message: Team-Based excels at iterative quality work (content, analysis, design)
- Example walkthrough: Content creation with Researcher → Writer → Editor → Reviewer
- Anti-pattern emphasis: Simple data pipelines don't need team collaboration

#### Facilitation Notes

**Watch For:**
- Participants assuming Team-Based is "better" than Parallel (it's just different - trade-offs)
- Confusion between Team-Based and Sequential with multiple agents

**If Asked About "Is Team-Based always higher quality?":**
> "Not automatically. Team-Based enables collaboration, which CAN improve quality if designed well. But a poorly designed team is worse than a good single agent. The key is: does collaboration add value for your specific use case?"

**Transition to Segment 2:**
> "Now that you understand WHY Team-Based patterns matter, let's design actual teams using role archetypes."

---

### Segment 2: Designing Agent Teams (12 minutes)

**Learning Objective:** Design agent teams using role archetypes and appropriate team structures

**Slides:** 8-11

#### Content Delivery

**Key Point 1: Role Archetypes (Slide 8)**
- Main message: Use standard roles (Researcher, Analyst, Creator, Critic, Editor, Coordinator)
- Visual to emphasize: Role responsibilities table
- Participant application: Most teams need 3-4 roles, not all 6

**Key Point 2: Team Composition Patterns (Slide 9)**
- Main message: Three common structures - Linear, Collaborative, Parallel+Team Hybrid
- Hands-on reference: Exercise 2.1 uses one of these patterns
- **IMPORTANT**: Start simple (Linear), prove it works, then add complexity

**Key Point 3: Team Agent Prompts (Slide 10)**
- Main message: Team agents need awareness of teammates and collaboration protocols
- Example: Show how Writer agent prompt includes "when to ask Researcher" guidance
- Code walkthrough: Compare standard vs team-aware prompts

#### Facilitation Notes

**Watch For:**
- Participants trying to create too many roles (>5 agents gets very complex)
- Confusion about Coordinator role (only needed for 5+ agent teams)

**If Asked About "How do I know which team structure to use?":**
> "Ask yourself: Do tasks happen in sequence with clear handoffs? Use Linear. Do multiple perspectives need to converge? Use Collaborative. Do you need both speed AND collaboration? Use Parallel+Team Hybrid. Exercise 2.1 will walk you through this decision."

**Transition to Segment 3:**
> "You know what roles you need. Now let's tackle HOW they actually communicate."

---

### Segment 3: Inter-Agent Communication (12 minutes)

**Learning Objective:** Implement inter-agent communication using appropriate pattern (handoff, request-response, or workspace)

**Slides:** 12-15

#### Content Delivery

**Key Point 1: Three Communication Patterns (Slide 12)**
- Main message: Direct Handoff (simplest), Request-Response (flexible), Shared Workspace (most collaborative)
- Framework: Choose based on collaboration complexity needs
- Decision guide: Start with Handoff, upgrade only if needed

**Key Point 2: Direct Handoff (Slide 13)**
- Main message: Linear passing of results, no back-and-forth
- When to use: Simple sequential workflows where iteration isn't valuable
- This is likely what participants built in Block 3

**Key Point 3: Request-Response & Shared Workspace (Slide 14)**
- Main message: Enable dynamic interaction between agents
- Demonstration: Show message format and workspace schema
- **Show both patterns** with clear differentiation

#### Demo Instructions

**Demo Duration:** 5-6 minutes (within Segment 3)

**Setup Required:**
- Team scenario with 3 agents: Researcher, Writer, Reviewer
- Request-Response communication between Writer and Researcher
- Shared workspace showing artifacts from all agents
- Pre-tested and working

**Demo Steps:**

1. **Show the team structure** - Point out agent roles
   > "We have three agents: Researcher gathers data, Writer creates content, Reviewer ensures quality."

2. **Demonstrate Request-Response** - Trigger Writer requesting data
   > "Watch: Writer starts drafting, realizes it needs market statistics, sends request to Researcher. Researcher receives request, fetches data, responds. Writer continues with the data."

3. **Show the message flow** - Display actual messages
   > "Here's the request message: 'from: writer, to: researcher, content: Need Q4 2024 pricing data.' And here's the response with the data."

4. **Show shared workspace** - Display workspace with artifacts
   > "Alternatively, all agents can use a shared workspace. Researcher writes to research_notes. Writer creates draft_v1. Reviewer adds review_comments. Everyone reads from the same context."

**Demo Talking Points:**
> "The key difference: Request-Response is direct agent-to-agent messages. Shared Workspace is all agents accessing common context. Both work - choose based on your platform capabilities and complexity needs."

**Backup Plan:**
If demo fails:
1. Switch to pre-captured interaction logs showing message flow
2. Walk through message format using slide content
3. Show workspace schema as static example
4. Offer to demonstrate 1:1 in office hours

#### Facilitation Notes

**Watch For:**
- Participants asking very platform-specific implementation questions
- Confusion about how to route messages in their specific tools

**If Asked About "How do I implement message passing in Make/n8n?":**
> "Platform-specific approaches vary. Make: use webhooks or data stores. n8n: use HTTP requests or database nodes. Custom code: function calls or message queue. Focus on the pattern concept now - Exercise 2.2 has platform guidance for implementation."

**Transition to Segment 4:**
> "You now know how to design teams and enable communication. The final piece: combining patterns into Hybrid systems."

---

### Segment 4: Hybrid Orchestration (3 minutes)

**Learning Objective:** Combine Sequential, Parallel, and Team-Based patterns appropriately

**Slides:** 16-18

#### Content Delivery

**Key Point 1: Pattern Combination Opportunity (Slide 16)**
- Main message: Real workflows have phases with different needs - use best pattern per phase
- Don't pick ONE pattern - use the RIGHT pattern for each phase
- This is sophisticated, enterprise-grade thinking

**Key Point 2: Hybrid Design Process (Slide 17)**
- Main message: Map phases → assess needs → match patterns → define handoffs
- Example walkthrough: Strategic report with Sequential planning, Parallel research, Team-Based creation
- Pattern selection matrix is decision tool

**Key Point 3: Module Complete (Slide 18)**
- Summary of entire Module 1 journey
- Capabilities unlocked: speed (Parallel), quality (Team-Based), sophistication (Hybrid)
- Transition to capstone

#### Facilitation Notes

**Watch For:**
- Participants feeling overwhelmed by Hybrid complexity
- Questions about "how many patterns should I use?"

**If Time Is Short:**
Focus on key principle:
> "Hybrid means using the right pattern for each phase. Don't overcomplicate - if your whole workflow needs speed, just use Parallel. If it needs quality, just use Team-Based. Use Hybrid only when different phases have different priorities."

**Closing This Segment:**
> "Hybrid orchestration is advanced architecture. Your capstone will demonstrate this mastery by combining all three patterns."

---

### Closing (3 minutes)

**Slides:** 19-21

**Do Not Skip This Section** - capstone is critical

#### Capstone Preview

**Key Actions:**
1. Overview all three exercises with emphasis on Exercise 2.3 capstone
2. Explain capstone requirements clearly
3. Note that capstone demonstrates MODULE completion, not just session
4. Point to evaluation rubric in Appendix C

**Script:**
> "Your homework includes three exercises totaling 75 minutes.
>
> Exercise 2.1: Design your agent team - 25 minutes. Define roles, interactions, workflow.
>
> Exercise 2.2: Implement Team-Based system - 30 minutes. Build working team with communication.
>
> Exercise 2.3: MODULE CAPSTONE - 20 minutes. This is critical. You'll combine your Session 1 Parallel system with Session 2 Team-Based system into one Hybrid orchestration architecture.
>
> Your capstone must demonstrate all three patterns: Sequential, Parallel, AND Team-Based, with clear justification for each phase.
>
> This is your proof of mastery for Advanced Module 1."

#### Resources and Support

> "Use the templates in your participant guide. Review Appendix B for team pattern examples and Appendix C for evaluation rubric - that's how you'll self-assess quality.
>
> If you get stuck, post in [channel] with specifics. This is advanced work - asking for help is expected."

#### Module Completion

> "When you complete Exercise 2.3, you've mastered Advanced Orchestration Patterns. This is sophisticated architecture work that sets you apart from typical AI practitioners.
>
> Congratulations on completing Module 1!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: When should I use Team-Based vs Parallel?**
A: "Different optimization goals. Parallel optimizes for speed when tasks are independent. Team-Based optimizes for quality when collaboration adds value. Not either/or - you can use both in Hybrid systems. Ask: Is my priority speed or quality for this phase?"

**Q: How is Team-Based different from just Sequential with multiple agents?**
A: "Great question. Sequential with multiple agents is still one-directional: A→B→C. Team-Based allows back-and-forth: A can ask B for help, C can send feedback to B. It's about bidirectional communication and iteration, not just passing results forward."

**Q: Do I need all 6 role archetypes in my team?**
A: "Definitely not. Most teams need 3-4 agents. Only use roles that add value for your use case. Don't use Coordinator unless you have 5+ agents. Don't use Critic if quality review isn't needed. Pick roles that serve your goal."

### Technical Questions

**Q: How do I implement inter-agent communication in my platform?**
A: "Depends on platform. Make: data stores or webhooks for message passing. n8n: database nodes or HTTP requests. Custom code: function parameters or message queues. The key is: one agent's output becomes input to another agent's call. Implementation details in Exercise 2.2 guidance."

**Q: What if my agents can't actually communicate - can I still do Team-Based?**
A: "Yes, with orchestrator-mediated communication. Instead of Agent A calling Agent B directly, orchestrator calls Agent A, takes output, calls Agent B with it. It's simulated Team-Based but achieves similar results. True peer-to-peer is ideal but not required."

**Q: How do I implement a shared workspace?**
A: "Use a data store all agents can access. Make: Data store module. n8n: Database or file storage. Custom: Database table or shared memory object. Schema should include task metadata, artifacts from each agent, and status tracking."

### Scope Questions

**Q: Should every workflow be Hybrid?**
A: "No! Hybrid adds complexity. Only use it when different phases have different optimization needs. If your entire workflow is independent tasks, just use Parallel. If it's collaborative quality work throughout, just use Team-Based. Hybrid is for workflows with distinct phases."

**Q: Can I have multiple Team-Based phases in one Hybrid system?**
A: "Absolutely. Example: Phase 1 Sequential planning, Phase 2 Parallel research, Phase 3 Team-Based analysis, Phase 4 Team-Based content creation, Phase 5 Sequential formatting. Use what fits each phase."

### Pushback/Objections

**Q: This seems overly complex - why not just use Claude or ChatGPT directly?**
A: "Fair point for simple tasks. Direct use is fine for one-off requests. But for repeatable business processes requiring multiple expertise areas, orchestrated teams provide: (1) specialization - each agent optimized for its role, (2) consistency - same team structure every time, (3) scalability - run hundreds of requests reliably. It's process automation, not just ad-hoc queries."

**Q: Won't Team-Based be much more expensive with all the agent calls?**
A: "Yes, Team-Based uses more agents than Sequential. But the ROI question isn't just cost - it's value. If team collaboration produces 2x better client deliverables, it may be worth 1.5x cost. Measure quality improvement vs cost increase. For critical deliverables, quality often justifies cost."

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Team demo breaks | Switch to pre-captured interaction logs | Walk through message flow using slide diagrams |
| Can't show message passing | Describe conceptually with visual diagram | Use participant's earlier question about their platform as discussion example |
| Workspace demo inaccessible | Show workspace schema on slide | Explain structure verbally with concrete example |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Overwhelmed by complexity | "This is too complicated for my use case" | "Start simple. Exercise 2.1 asks you to design a 3-agent Linear team. Prove that works. Then add complexity in future projects." |
| Can't see difference between patterns | "When would I use Team vs Parallel?" | Return to optimization goal: "Parallel = speed. Team = quality. Sequential = coherence. What's your priority?" |
| Struggling with communication implementation | Platform-specific questions dominating | "Focus on the pattern concept now. Exercise 2.2 has platform-specific guidance. Post screenshots in [channel] for implementation help." |
| Unsure about Hybrid design | "How do I know which pattern for which phase?" | Use decision matrix from Slide 17. "Planning needs coherence → Sequential. Research needs speed → Parallel. Creation needs quality → Team." |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Content too easy | "We already do Team-Based workflows" | "Excellent! Exercise 2.3 challenges you to formalize architecture and measure quality improvement. Can you quantify team collaboration value?" |
| Content too hard | Many questions, confusion | Simplify to core principles: "Three patterns exist. Use right one per phase. That's Hybrid. Start with one pattern, add others incrementally." |
| Hybrid section too abstract | "Can you show a real example?" | Use strategic report example in depth: "Planning (1 planner) → Research (4 parallel researchers) → Analysis (Analyst ↔ Writer team) → Finalization (1 formatter)." |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | Verify recording saved properly |
| Save chat questions | Copy any unanswered questions for follow-up |
| Note what worked/didn't | Especially note demo effectiveness and Hybrid segment clarity |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording | If applicable, share link in course channel | ☐ |
| Answer pending questions | Especially any Hybrid design questions | ☐ |
| Send capstone reminder | Emphasize Exercise 2.3 importance for module completion | ☐ |
| Document issues encountered | Note any confusion patterns for curriculum improvement | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review capstone submissions | Assess Exercise 2.3 using Appendix C rubric | ☐ |
| Identify exceptional work | Note participants who demonstrated mastery for recognition | ☐ |
| Identify struggling participants | Reach out to those with incomplete/weak capstone | ☐ |
| Prepare Module 1 completion summary | Cohort-level analysis of capstone quality | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Session

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 2.1 | `team-design.md` | Participant's GitHub repo or shared folder |
| 2.2 | Working team implementation + interaction logs | Platform workspace + documentation |
| 2.3 (CAPSTONE) | `hybrid-orchestration-capstone.md` + working system | Documentation + platform |

### Capstone Assessment (Using Appendix C Rubric)

**Criterion 1: Parallel Implementation (5 points)** - From Session 1
- Look for: Working parallel execution with proper aggregation
- Red flag: Still showing sequential timing

**Criterion 2: Team-Based Implementation (5 points)** - From Exercise 2.2
- Look for: Clear roles, working communication, iterative refinement
- Red flag: Agents don't actually interact (just Sequential mislabeled)

**Criterion 3: Hybrid Orchestration (5 points)** - From Exercise 2.3
- Look for: Multiple patterns used appropriately with clear justification
- Red flag: Only using one pattern, or patterns chosen without rationale

**Criterion 4: Performance & Documentation (5 points)** - From Exercise 2.3
- Look for: Metrics comparing approaches, clear documentation, production quality
- Red flag: No performance analysis or missing documentation

### Intervention Thresholds:
- Capstone score <15/20 (75%): Reach out for revision before approving module completion
- Capstone missing Team-Based or Hybrid: Critical gap - requires completion
- Capstone excellent (18-20/20): Recognize publicly as exemplar

---

## Session-Specific Notes

### What Makes This Session Unique

This is the final session of Module 1, culminating in a capstone that integrates both sessions.

**Critical Concepts Needing Extra Emphasis:**
- Inter-agent communication distinction (Slide 13-14) - participants often confuse the three patterns
- Pattern selection by phase (Slide 17) - this is the key to Hybrid thinking
- Capstone requirements (Slide 19) - must emphasize this demonstrates MODULE mastery, not just session

**Common Failure Points:**
- Demo of inter-agent communication is technically fragile (have backup logs ready)
- Segment 4 Hybrid content can feel abstract (use concrete example repeatedly)
- Participants may underestimate capstone complexity (emphasize 20 min is for documentation, implementation may take longer)

### Dependencies

**Builds On:**
- Session 1: Parallel orchestration patterns (participants must have working parallel system)
- Block 3: Multi-agent orchestration fundamentals
- Block 2: Workflow engineering principles

**Sets Up:**
- Future advanced modules building on orchestration patterns
- Participants' own production implementations
- Consulting engagements requiring sophisticated agent architectures

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Shared Workspace implementation varies significantly by platform | Focus on concept, accept diverse implementations | Active - acknowledged in exercises |
| Request-Response can be confused with function calling | Clarify: message-based vs direct function invocation are both valid | Active - clarify in Slide 14 |
| Capstone may require more than 20 min | 20 min is for design/documentation; implementation may extend beyond | Active - note in instructions |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- After Slide 6: "Quick poll - which pattern for: create 50 blog posts, all independent topics. Parallel or Team-Based?" [Answer: Parallel - speed, independent]
- After Slide 9: "How many agents in most teams?" [Answer: 3-4, not all 6 archetypes]
- After Slide 17: "Which pattern for planning phase in most workflows?" [Answer: Sequential - need coherence]

**Observable Behavior Indicating Understanding:**
- Participants asking how to apply patterns to their specific use cases
- Recognition of trade-offs (not "Team is better" but "Team vs Parallel serve different goals")
- Engagement during Hybrid design discussion

**Observable Behavior Indicating Confusion:**
- Questions about "making everything Team-Based"
- Conflating Team-Based with just having multiple Sequential agents
- Asking "which pattern is best" without context

### Summative Assessment (End of Session - Capstone)

**Using Appendix C Module Evaluation Rubric (20 points total):**

**Exercise Quality Indicators:**

**Exercise 2.1 (Team Design):** Look for:
- 3-4 agents with clear, non-overlapping roles
- Appropriate team structure (Linear, Collaborative, or Hybrid)
- Interaction map showing communication flows
- Shared workspace schema appropriate for use case

**Exercise 2.2 (Team Implementation):** Look for:
- Actually implemented (not just designed)
- Evidence of inter-agent communication (logs, messages, workspace artifacts)
- 3+ test executions showing team collaboration
- Quality improvement through iteration visible

**Exercise 2.3 (CAPSTONE - Hybrid Orchestration):** Look for:
- Uses at least 2 patterns (ideally all 3: Sequential, Parallel, Team-Based)
- Clear justification for pattern choice per phase (not arbitrary)
- Performance metrics (time, cost, quality) comparing approaches
- Production-ready quality (error handling, documentation, etc.)

**Common Issues to Flag:**
- **Issue 1**: Capstone only uses one pattern (e.g., just Parallel or just Team-Based)
  - **Why it matters**: Demonstrates misunderstanding of Hybrid concept
  - **Intervention**: Require revision showing at least 2 patterns with phase justification

- **Issue 2**: Team agents don't actually communicate (just Sequential)
  - **Why it matters**: Missing Team-Based pattern core concept
  - **Intervention**: Review interaction logs, require evidence of collaboration

### Module Completion Criteria

Participant must achieve:
- **15/20 points minimum** (75%) on Appendix C rubric
- **All three exercises submitted** (2.1, 2.2, 2.3)
- **Working implementations** (not just design documents)

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Slack poll: "On scale 1-5, how clear was the difference between Team-Based and Parallel patterns?"
- Monitor capstone submissions for common architecture patterns or gaps

**Improvement Log:**

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| YYYY-MM-DD | Participants unclear when to use Hybrid vs single pattern | Added decision guide emphasizing "use Hybrid only when phases have different needs" | Improved clarity |
| | | | |

### Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial Session 2 instructor guide created | AI Practitioner Training Team |

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Team-Based enables collaboration that Parallel cannot - use when quality through iteration matters"
2. "Start with 3-4 agents and Direct Handoff communication - prove it works before adding complexity"
3. "Hybrid means using the RIGHT pattern per phase - not using all patterns everywhere"

### If You Only Have Time For One Thing

**The single most important concept:** Understanding that different orchestration patterns serve different goals (speed vs quality vs coherence), and Hybrid systems apply the right pattern to each phase based on that phase's priority.

**How to convey it:** Use the strategic report example repeatedly showing Sequential planning → Parallel research → Team-Based creation → Sequential finalization. Make the "why this pattern here" reasoning explicit.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Team-Based orchestration | "Like a consulting team collaborating on a whiteboard, not just four people working in isolation" | Explaining Team vs Parallel difference |
| Inter-agent communication | "Request-Response is like email. Shared Workspace is like Google Docs. Both enable collaboration, different mechanisms." | Explaining communication patterns |
| Hybrid orchestration | "Like using running for cardio, lifting for strength, yoga for flexibility - right tool for each training goal" | Explaining pattern selection per phase |

---

**Instructor Preparation Complete:** Use this guide alongside presentation slides and participant guide to deliver effective Session 2 and support capstone completion.
