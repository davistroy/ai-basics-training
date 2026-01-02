# **INSTRUCTOR GUIDE: ADVANCED MODULE 4 SESSION 1**
## **Mermaid Fundamentals**

**Module:** Advanced Module 4: Visual Documentation with Mermaid
**Session:** 1 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Teaching text-based diagram creation with Mermaid for AI workflows |
| **Difficulty Level** | Low - Syntax is straightforward, immediate visual feedback |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Yes - Live Mermaid creation and GitHub rendering |
| **Tech Setup Needed** | VS Code with Mermaid Preview extension, GitHub repo, screen share |
| **Common Challenges** | Syntax errors in code blocks, rendering issues, participants unfamiliar with markdown |

---

## Navigation

**Session Navigation:** | **Session 1** | [Session 2 Instructor Guide →](../session-2/instructor-guide.md)

**Related Materials:**
- [Session 1 Presentation Slides](presentation.md)
- [Session 1 Participant Guide](participant-guide.md)
- [Module 4 Main Document](../module-4-visual-documentation.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Session 1 materials and practice demos | ☐ |
| Test demo | Create sample Mermaid diagrams in VS Code and GitHub | ☐ |
| Check resources | Verify Mermaid docs links work, extension installs properly | ☐ |
| Prepare backup | Create screenshots of all demo steps in case live fails | ☐ |
| Review previous | Check module prerequisites - ensure participants are Block 2+ | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, VS Code preview, GitHub rendering | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice transitions - this session is demo-heavy | ☐ |
| Prepare materials | Have VS Code open with blank .md file, GitHub repo ready | ☐ |
| Install extension | Verify Mermaid Preview extension works in VS Code | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, VS Code, GitHub, Mermaid docs | ☐ |
| Test share | Verify screen sharing shows VS Code preview pane clearly | ☐ |
| Welcome early arrivals | Ask if they've seen Mermaid before | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, session preview, learning objectives | Set context |
| 0:03 | 10 min | Segment 1 | Introduction to Mermaid + Basic Demo | Include live demo |
| 0:13 | 15 min | Segment 2 | Flowcharts for workflows | Most important segment |
| 0:28 | 12 min | Segment 3 | Sequence diagrams for agents | Live example |
| 0:40 | 8 min | Segment 4 | Styling and best practices | Can compress if needed |
| 0:48 | 3 min | Closing | Homework preview, resources, next session | Don't skip |
| **Total** | **51 min** | | | 6-min buffer included |

### Timing Flexibility

**If Running Behind:**
- Segment 1: Shorten "where Mermaid renders" to 1 minute bullet list
- Segment 2: Skip advanced flowchart features (subgraphs) - reference in participant guide
- Segment 4: Show one styling example instead of multiple

**If Running Ahead:**
- Segment 2: Add additional workflow example (error handling pattern)
- Segment 3: Show activate/deactivate and loop examples
- Q&A: Extended discussion on real use cases

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:13 | Skip detailed platform list, focus on GitHub |
| End Segment 2 | 0:28 | Must complete - core content. Skip Segment 4 if needed. |
| Start Closing | 0:48 | Must start by here regardless of prior content |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants warmly
2. Set context: "Visual documentation makes AI systems understandable"
3. Quick poll: "Who has built AI workflows that are hard to explain?"
4. Preview: "By end of today, you'll create professional diagrams using just text"

**Opening Script:**
> "Welcome to Advanced Module 4, Session 1: Mermaid Fundamentals. How many of you have built AI workflows or multi-agent systems that you struggle to document clearly?"

[Wait for show of hands - should see most hands up]

> "That's exactly what we're solving today. By the end of this session, you'll be able to create professional flowcharts, sequence diagrams, and architecture views using simple text syntax that renders automatically in GitHub. Let's dive in."

**Engagement Opportunity:**
> "Quick question: What's your current method for documenting workflows? Whiteboard? PowerPoint? Just text?"

[Wait for 1-2 responses - this primes them to see Mermaid as a solution]

---

### Segment 1: Introduction to Mermaid (10 min)

**Learning Objective:** Understand what Mermaid is and create first basic diagram

**Slides:** 4-7

#### Content Delivery

**Key Point 1: The Documentation Problem (Slide 4)**
- Main message: Traditional diagram tools are disconnected from code
- Example to use: "Whiteboard sketches that disappear, PowerPoint diagrams that become outdated"
- Common misconception: "Visual documentation requires specialized tools like Visio"

**Key Point 2: What is Mermaid? (Slide 5)**
- Main message: Text-based diagrams that version-control with your code
- Demonstration: Side-by-side text syntax and rendered output
- Participant relevance: Documentation that evolves with their AI systems

**Key Point 3: Basic Demo (Slide 6)**
- Main message: Creating and rendering is simple and immediate
- Practice preview: Exercise 1.1 uses this exact pattern

#### Demo Instructions

**Demo Duration:** 5 minutes

**Setup Required:**
- VS Code with Mermaid Preview extension installed
- Blank markdown file open
- Preview pane visible (split screen)
- GitHub repository ready in browser tab

**Demo Steps:**
1. **Create basic diagram:**
   - Type opening code fence with mermaid language identifier
   - Create simple 3-node flowchart: Start → Process → End
   - Show preview rendering in real-time
   - **Say:** "Notice how the preview updates instantly as I type"

2. **Add complexity:**
   - Add a decision node (diamond shape)
   - Add branching with labels
   - Add a loop back
   - **Say:** "Watch how easy it is to add decision points and loops"

3. **Show GitHub rendering:**
   - Commit the file to GitHub
   - Open README in browser
   - Show that it renders automatically
   - **Say:** "No special setup needed - GitHub just renders it"

**Demo Talking Points:**
> "I'm in VS Code with the Mermaid Preview extension. As I type the syntax, watch the preview pane on the right..."
> "The syntax is intuitive - I'm just describing the flow in text. Square brackets for nodes, arrows for connections..."
> "Now let me commit this to GitHub and show you the magic - it renders automatically in the README. No external tools needed."

**Backup Plan:**
If demo fails:
1. Switch to pre-captured screenshots showing each step
2. Walk through the syntax conceptually using slides
3. Offer to demonstrate 1:1 in office hours

#### Facilitation Notes

**Watch For:**
- Confused expressions during syntax explanation - slow down and break it down more
- Questions about where to get the extension - have link ready

**If Asked About "Do I need special software?":**
> "Just a text editor - any markdown editor works. VS Code with Mermaid Preview is nice for live preview, but you can write Mermaid in any editor and it'll render in GitHub."

**Transition to Segment 2:**
> "Now that you understand the basics, let's apply this to real AI workflows. Starting with flowcharts..."

---

### Segment 2: Flowcharts (15 min)

**Learning Objective:** Create flowcharts to document AI workflow logic

**Slides:** 8-13

#### Content Delivery

**Key Point 1: Why Flowcharts for AI Workflows (Slide 8)**
- Main message: AI workflows have decision logic, loops, and branching that flowcharts excel at showing
- Visual to emphasize: Complex workflow with quality gate example

**Key Point 2: Flowchart Syntax (Slide 9)**
- Main message: Simple syntax for nodes and connections
- Visual: Node shapes reference (rectangle, diamond, database, circle)

**Key Point 3: Real Example (Slide 10)**
- Main message: Quality check pattern with three paths (pass, fail, human review)
- Hands-on reference: This is the pattern they'll use in Exercise 1.1

**Key Point 4: Best Practices (Slide 11)**
- Main message: Clear labels and focused diagrams
- Real-world application: "One workflow per diagram - split if it gets too complex"

**Key Point 5: Advanced - Subgraphs (Slide 12)**
- Main message: Group related steps for complex workflows
- Note: Can skip if running behind - reference participant guide

#### Interactive Element

**Activity Type:** Quick exercise

**Activity Duration:** 2 minutes (only if time allows)

**Instructions:**
1. Ask participants: "In chat, describe a workflow you've built that has a quality check or decision point"
2. Pick one example and sketch it verbally using Mermaid syntax
3. Show how the flowchart pattern applies

**Debrief Points:**
> "Notice how many of your workflows follow this pattern: process → check → branch based on quality. This is the core pattern you'll diagram in Exercise 1.1."

#### Facilitation Notes

**Energy Check:**
At this point in the session, participants may be:
- Information loaded from syntax details
- Eager to try it themselves

Recommended adjustment: Keep examples concrete and show visuals, less abstract syntax explanation

**Transition to Segment 3:**
> "Flowcharts show WHAT happens in your workflow. But what about showing WHO does WHAT and WHEN? That's where sequence diagrams come in..."

---

### Segment 3: Sequence Diagrams (12 min)

**Learning Objective:** Build sequence diagrams to show agent interactions over time

**Slides:** 14-17

#### Content Delivery

**Key Point 1: Sequence vs. Flow (Slide 14)**
- Main message: Sequence diagrams show interactions between participants over time
- Framework/Pattern: Time flows top to bottom, messages flow left/right between participants

**Key Point 2: Sequence Syntax (Slide 15)**
- Main message: Participants and messages with different arrow types
- Example walkthrough: Solid for calls, dashed for responses

**Key Point 3: Multi-Agent Example (Slide 16)**
- Main message: Orchestrator pattern with research, writing, and quality agents
- Live walkthrough: Point out activate/deactivate, alt/else conditional logic

#### Practical Application

**Consulting Connection:**
> "If you've built a multi-agent system with an orchestrator, this diagram type is perfect for explaining how agents collaborate. Instead of pages of text describing the flow, one sequence diagram makes it immediately clear."

**Example Scenario:**
> "Imagine you're presenting your AI workflow to a client. They ask 'How do the agents work together?' You show them a sequence diagram. They immediately see: Orchestrator asks Researcher for data, then hands to Writer, then Quality checks it. If quality is low, it loops back. Clear and visual."

#### Facilitation Notes

**Common Confusion Point:**
Participants often confuse solid vs. dashed arrows

**Clarification Approach:**
> "Think of solid arrows as questions or commands: 'Do this task.' Dashed arrows are answers or responses: 'Here's the result.' Solid is outbound, dashed is return."

---

### Segment 4: Styling and Best Practices (8 min)

**Learning Objective:** Apply styling and follow best practices for professional diagrams

**Slides:** 18-20

#### Content Delivery

**Key Point 1: Adding Styles (Slide 18)**
- Main message: Simple styling adds visual hierarchy
- Example: Start nodes in green, end nodes in red, processes in default

**Key Point 2: Best Practices Checklist (Slide 19)**
- Main message: One concept per diagram, test rendering, clear labels
- Key principle: "Diagrams should be maintainable - plan for updates"

**Key Point 3: Summary (Slide 20)**
- Main message: Professional diagrams are focused and well-labeled

#### Closing This Segment

**Key Takeaway:**
> "Professional Mermaid diagrams aren't about fancy styling - they're about clarity and maintainability. Keep them focused, label everything, and test rendering."

**Connection to Homework:**
> "In Exercise 1.3, you'll create integrated documentation that combines flowcharts, sequence diagrams, and architecture views using these best practices."

---

### Closing (3 minutes)

**Slides:** 21-23

**Do Not Skip This Section** - even if running behind

#### Homework Preview

**Key Actions:**
1. Overview all three exercises briefly
2. Highlight which exercise practices which concept
3. Note estimated times (60 total)
4. Point to resources and where to get help

**Script:**
> "Your homework includes three exercises totaling 60 minutes.
>
> Exercise 1.1 practices flowcharts - takes about 20 minutes. You'll create diagrams for three of your actual workflows.
> Exercise 1.2 focuses on sequence diagrams - 20 minutes. You'll document agent interactions and error handling.
> Exercise 1.3 brings it together - 20 minutes to create integrated documentation with multiple diagram types.
>
> Everything you need is in your participant guide, including templates and examples you can copy and adapt."

#### Resources and Support

> "If you get stuck, post your Mermaid code in [support channel] along with what you're trying to achieve. The syntax errors are usually simple - missing backtick, wrong bracket type - and easy to fix."

#### Next Week Preview

> "Next session we'll cover advanced diagram types: state diagrams for agent states, architecture diagrams for systems, and GitHub integration best practices. We'll also complete the module capstone where you create a comprehensive visual documentation suite."

#### Session Close

> "Questions before we wrap? ... Great session today. Remember: Mermaid makes documentation maintainable. Use that to your advantage. See you next session!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Why Mermaid instead of PowerPoint or Visio?**
A: Three reasons: (1) Version control - diagrams live with your code in git, (2) Easy updates - change text instead of dragging boxes, (3) Automatic rendering - GitHub, GitLab, Notion all support it natively. PowerPoint diagrams become outdated the moment you create them.

**Q: Is Mermaid only for technical documentation?**
A: No - it's great for any documentation that needs diagrams. Workflows, org charts, timelines, architecture. The text-based approach means anyone can update it, not just people with Visio licenses.

**Q: Can I customize the styling more than what you showed?**
A: Yes - Mermaid supports custom themes, colors, and layouts. But start simple. Most professional diagrams use minimal styling for clarity.

### Technical Questions

**Q: What if my diagram doesn't render in GitHub?**
A: Most common issues: (1) Missing opening or closing backticks in the code fence, (2) Wrong language identifier - must be exactly "mermaid" lowercase, (3) Syntax error in the diagram code. Test locally in VS Code first.

**Q: Can I export Mermaid diagrams as images?**
A: Yes - VS Code extensions can export to PNG/SVG. But the power of Mermaid is that it stays as text in your repo. If you need images for presentations, export when needed but keep the source as Mermaid.

**Q: Does this work offline?**
A: Rendering requires either a local preview tool (VS Code extension) or a platform (GitHub). The text syntax works offline, but you need a renderer to see the diagram.

### Scope Questions

**Q: Can Mermaid create org charts, timelines, and other diagram types?**
A: Yes - that's actually covered in Session 2. Today we focused on flowcharts and sequence diagrams because they're most relevant for AI workflows. Session 2 covers state diagrams, class diagrams, and more.

**Q: What about really complex diagrams with 50+ nodes?**
A: Split them. Better to have multiple focused diagrams than one overwhelming one. Create "Main Workflow" and "Error Handling" as separate diagrams. Use links between docs if needed.

### Pushback/Objections

**Q: This seems harder than just drawing in PowerPoint.**
A: It feels that way at first because you're learning syntax. But after creating 2-3 diagrams, the syntax becomes natural. And the payoff is huge - your diagrams stay up-to-date because they're easy to edit. PowerPoint diagrams rot the moment they're created.

**Q: My stakeholders won't understand text-based diagrams.**
A: They don't see the text - they see the rendered diagram. When you share a GitHub README, they see the visual diagram, not the Mermaid code. It looks just as professional as any diagram tool, but you maintain it more easily.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Mermaid Preview not working | Restart VS Code, verify extension installed | Use Mermaid Live Editor (mermaid.live) in browser |
| GitHub not rendering | Check syntax in VS Code first, verify code fence | Show screenshots of working examples |
| Screen share shows wrong window | Re-share, select specific VS Code window | Use backup screenshots |
| Demo syntax error | Check brackets, verify code fence format | Have working example ready to paste |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Markdown unfamiliarity | "What's a code fence?" | Quick 1-minute markdown primer, show backticks |
| Syntax confusion | "My diagram won't render" | Check: code fence format, mermaid language tag, bracket types |
| Overwhelmed by options | "So many node shapes and arrow types!" | Reassure: "Start with basics - rectangles and arrows. Advanced features come later." |
| Can't see use case | "When would I actually use this?" | Ask about their workflows, show how diagram would help |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Content too easy | "We already know diagrams" | Emphasize unique value: version control, text-based, automatic rendering |
| Content too hard | Many questions on syntax | Slow down, show more examples, focus on patterns not memorization |
| Off-topic tangent | Discussion about other diagram tools | "Great question - let's focus on Mermaid for now and compare tools in [support channel]" |
| Time pressure | Running 10+ minutes behind | Skip Segment 4 (styling), reference participant guide |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save chat questions | For follow-up and FAQ updates |
| Note what worked/didn't | Especially demo issues or timing problems |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | ☐ |
| Answer pending questions in support channel | ☐ |
| Send follow-up with key resources (Mermaid docs, VS Code extension link) | ☐ |
| Document any syntax issues encountered for curriculum improvement | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions (spot check) | ☐ |
| Identify participants needing syntax help | ☐ |
| Prepare clarifications for Session 2 if common issues emerged | ☐ |
| Update instructor guide with lessons learned | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 1.1 | 3 workflow flowchart .md files | Participant's GitHub repo /docs or /workflows folder |
| 1.2 | 2 sequence diagram .md files | Participant's GitHub repo |
| 1.3 | 1 integrated documentation file | Participant's GitHub repo (likely README or docs/visual-documentation.md) |

### Progress Check Approach

**How to Verify Completion:**
- Check for GitHub commits with .md files containing mermaid code blocks
- Look for properly formatted code fences with "mermaid" language tag
- Verify diagrams render correctly in GitHub (not just syntax present)

**Red Flags Indicating Struggle:**
- Mermaid code not in proper code fences (won't render)
- Very simple diagrams (suggests participant didn't engage with real workflows)
- No commits at all (struggling with GitHub or markdown basics)

**Intervention Thresholds:**
- 1 exercise incomplete: Monitor, may be time constraints
- 2+ exercises incomplete: Reach out privately - likely syntax confusion
- Diagrams present but not rendering: Quick fix - code fence format issue

---

## Week-Specific Notes

### What Makes This Session Unique

**Session 1 is the foundation** - participants must grasp syntax here to succeed in Session 2

**Special challenges:**
- Syntax learning curve - participants unfamiliar with markdown may struggle
- Preview tool setup - some may not have VS Code or extension installed
- Immediate gratification is key - live demos that render instantly keep engagement high

**Critical concepts that need extra emphasis:**
- Code fence format (triple backticks with "mermaid" language tag)
- Node syntax (brackets define shape)
- The value proposition: text-based diagrams that version-control

**Common failure points:**
- Missing or incorrect code fence markers
- Wrong bracket types ([ vs { vs ( - each creates different shape)
- Trying to create overly complex diagrams on first attempt

**Connections to other content:**
- Builds on Block 2's markdown and GitHub knowledge
- Session 2 builds directly on flowchart and sequence syntax learned here

### Dependencies

**Builds On:**
- Block 2: GitHub repository management
- General: Markdown syntax knowledge
- Prerequisites: Having workflows/agents to document

**Sets Up:**
- Session 2: Advanced diagram types and GitHub integration
- Module capstone: Complete visual documentation suite

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Some Mermaid features don't render in all platforms | Stick to core syntax (flowcharts, sequence) for Session 1 | Active |
| VS Code extension occasionally needs restart | Mention this proactively, have backup browser option | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- After demo: "What's the language tag in the code fence?" (Answer: "mermaid")
- After flowcharts: "What shape represents a decision point?" (Answer: Diamond/curly braces)
- After sequence: "What's the difference between solid and dashed arrows?" (Answer: Call vs. response)

**Observable Behavior Indicating Understanding:**
- Nodding during demos
- Questions about how to apply to their specific workflows
- Chat messages sharing examples

**Observable Behavior Indicating Confusion:**
- Silence after questions
- Questions about basic markdown syntax (indicates prerequisite gap)
- Facial expressions of being overwhelmed

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 1.1: Look for (1) Proper code fences, (2) Decision diamonds used appropriately, (3) Workflows reflect real logic (not just linear)
- Exercise 1.2: Look for (1) Multiple participants in sequence, (2) Solid vs. dashed arrows used correctly, (3) Alt/else or loop features attempted
- Exercise 1.3: Look for (1) Multiple diagram types combined, (2) Diagrams render correctly, (3) Documentation is coherent

**Common Issues to Flag:**
- Code not rendering: Usually code fence format error
- Overly simple diagrams: Participant may not have engaged with real workflows - encourage authenticity
- Syntax errors: Usually bracket types - provide specific correction

### Connecting to Capstone

**Capstone Relevance:**
Session 2 includes the module capstone where participants create a complete visual documentation suite.

This week's work contributes by:
- Exercise 1.1 flowcharts become part of "Workflows" section
- Exercise 1.2 sequence diagrams become "Agent Interactions" section
- Exercise 1.3 integrated doc is the starting template for the capstone

Encourage participants to choose workflows/agents they'll want in their final portfolio.

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Quick poll: "On a scale of 1-5, how comfortable are you creating Mermaid diagrams now?"
- Open question: "What's still unclear about Mermaid syntax?"

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

1. "Mermaid diagrams are text that renders automatically - version-controllable documentation"
2. "Flowcharts show workflow logic, sequence diagrams show agent interactions over time"
3. "Start simple - rectangles and arrows. Advanced features come with practice"

### If You Only Have Time For One Thing

The flowchart syntax and quality gate pattern (Slide 10) - this is what 80% of participants will use most often for documenting AI workflows.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Text-based diagrams | "Like markdown is to Word docs - lightweight, version-controllable, portable" | When explaining Mermaid's value prop |
| Code fences | "The container that tells GitHub 'this is a Mermaid diagram, please render it'" | When troubleshooting rendering issues |
| Flowcharts vs. Sequence | "Flowcharts are WHAT happens, sequence diagrams are WHO does WHAT and WHEN" | When helping participants choose diagram type |

---
