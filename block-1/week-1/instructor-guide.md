# **INSTRUCTOR GUIDE: BLOCK 1 WEEK 1**
## **Markdown Fundamentals & Structured Prompting**

**Block:** 1: AI Prompting Mastery
**Week:** 1 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Introduction to Markdown syntax and the ASK-CONTEXT-CONSTRAINTS-EXAMPLE prompting framework |
| **Difficulty Level** | Low |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Yes - Converting unstructured text to Markdown and building a structured prompt |
| **Tech Setup Needed** | AI platform access (Claude/ChatGPT), Markdown previewer, screen sharing |
| **Common Challenges** | Markdown syntax errors (missing spaces after #), understanding why structure matters |

---

## Navigation

**Block Navigation:** **Week 1** | [Week 2 Instructor Guide →](../week-2/instructor-guide.md)

**Related Materials:**
- [Week 1 Presentation](presentation.md)
- [Week 1 Participant Guide](participant-guide.md)
- [Block 1 Main Document](../block-1.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 1 materials including block-1.md | ☐ |
| Test demo | Practice converting unstructured notes to Markdown live | ☐ |
| Check resources | Verify Dillinger.io, Markdown Tutorial links work | ☐ |
| Prepare backup | Create screenshots of Markdown preview in case demo fails | ☐ |
| Setup example | Prepare a "wall of text" prompt and its structured version | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice transitions, especially for the 15-min Markdown segment | ☐ |
| Prepare materials | Have AI platform open, Markdown editor ready | ☐ |
| Test AI access | Verify Claude or ChatGPT is working for demo | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, AI platform, Markdown previewer | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Ask about their AI experience level | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 5 min | Opening | Welcome, program overview, maturity model | Set the stage for 8 weeks |
| 0:05 | 8 min | Segment 1 | Why Markdown Matters | Problem/solution framing |
| 0:13 | 15 min | Segment 2 | Markdown Essentials | Core syntax with live demo |
| 0:28 | 12 min | Segment 3 | ASK-CONTEXT-CONSTRAINTS-EXAMPLE Framework | The key framework |
| 0:40 | 5 min | Closing | Exercise preview and setup help | Don't skip |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Shorten Markdown syntax to just headers, lists, and code blocks
- Reference the Markdown Tutorial link for self-study on emphasis and tables
- Skip the live demo and use prepared screenshots

**If Running Ahead:**
- Spend more time on the structured prompt transformation demo
- Take additional questions about AI platform access
- Discuss real examples from participants' work

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Welcome/Overview | 0:05 | Cut program overview shorter |
| End Markdown Essentials | 0:28 | Must start framework by here |
| Start Closing | 0:40 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (5 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants warmly to Block 1
2. Set context for the 8-week journey to AI Prompting Practitioner certification
3. Introduce the maturity model (Level 0-3)
4. Preview today's focus on foundations

**Opening Script:**
> "Welcome to Block 1: AI Prompting Mastery. Over the next 8 weeks, you'll transform from ad-hoc AI users to skilled practitioners with your own prompt library and quality systems. Today we're starting with the fundamentals - Markdown formatting and structured prompting - because these are the building blocks for everything else we'll do."

**Engagement Opportunity:**
> "Quick show of hands: How many of you have used Markdown before, even if just in a README file or Slack message?"

[Acknowledge responses - this helps gauge the room's starting point]

---

### Segment 1: Why Markdown Matters (8 minutes)

**Learning Objective:** Understand why structured prompts produce better AI outputs

**Slides:** 4-5

#### Content Delivery

**Key Point 1: The Problem**
- Main message: Unstructured "wall of text" prompts produce inconsistent results
- Example to use: Show a vague prompt like "Write something about marketing"
- Common misconception: More words = better prompts (actually the opposite)

**Key Point 2: The Solution**
- Main message: Markdown provides structure that AI models understand and respect
- Demonstration: AI models were trained on millions of Markdown documents
- Participant relevance: Consistent formatting = consistent quality outputs

**Key Point 3: The Core Principle**
- Main message: "Structure = clarity for AI = better outputs"
- Practice preview: All exercises will use Markdown formatting

#### Demo Instructions

**Demo Duration:** 3 minutes

**Setup Required:**
- Two versions of the same prompt prepared (unstructured vs. structured)
- AI platform ready to run both

**Demo Steps:**
1. Show the unstructured prompt, run it, show mediocre output
2. Show the same request with Markdown headers and structure
3. Run the structured version, show improved output

**Demo Talking Points:**
> "Watch how the AI responds to this wall of text... now compare when I add clear headers and structure."
> "Notice how the structured version follows our format exactly - that's the power of Markdown."

**Backup Plan:**
If demo fails:
1. Use prepared screenshots showing both outputs
2. Walk through the structure conceptually
3. Participants will test this themselves in Exercise 1.2

#### Facilitation Notes

**Watch For:**
- Confusion about what Markdown actually is
- Questions about specific AI platforms

**If Asked About "What AI platform should I use?"**
> "For this program, Claude or ChatGPT both work well. Use whichever you have access to. The techniques we teach work across platforms."

**Transition to Segment 2:**
> "Now that you understand WHY structure matters, let's learn the specific Markdown syntax you'll use."

---

### Segment 2: Markdown Essentials (15 minutes)

**Learning Objective:** Write valid Markdown including headers, lists, emphasis, and code blocks

**Slides:** 6-10

#### Content Delivery

**Key Point 1: Headers (Document Structure)**
- Main message: Headers create hierarchy that AI respects
- Visual to emphasize: Show the # ## ### progression
- Practical tip: Always put a space after the #

**Key Point 2: Lists (Organizing Information)**
- Main message: Use ordered lists for sequences, unordered for options
- Hands-on reference: Exercise 1.1 requires both types
- Common mistake: Forgetting blank lines before lists

**Key Point 3: Code Blocks (THE Critical Technique)**
- Main message: Triple backticks isolate data from instructions
- Real-world application: Prevents prompt injection, keeps examples clear
- Rule to emphasize: "Always wrap external data in code blocks"

**Key Point 4: Emphasis and Links**
- Main message: Bold for emphasis, italics for terms, links for references
- Keep brief: Participants can practice these in exercises

#### Demo Instructions

**Demo Duration:** 5 minutes

**Setup Required:**
- Notepad or text editor ready
- Dillinger.io open for preview

**Demo Steps:**
1. Start with unformatted notes
2. Add headers to create structure
3. Convert run-on sentences to bullet list
4. Add code block around example code or data
5. Show preview side-by-side

**Demo Talking Points:**
> "I'm starting with these messy notes... First, let me add structure with headers."
> "Now watch what happens when I preview this - the hierarchy becomes visual."

#### Facilitation Notes

**Watch For:**
- Participants trying to take notes on all syntax (reassure them it's in the participant guide)
- Confusion about when to use code blocks

**Energy Check:**
At 15 minutes in, participants may be getting restless with syntax. Keep this segment practical and moving.

**Transition to Segment 3:**
> "Now that you know the building blocks, let's put them together into a framework for writing effective prompts every time."

---

### Segment 3: ASK-CONTEXT-CONSTRAINTS-EXAMPLE Framework (12 minutes)

**Learning Objective:** Apply the four-section framework to create structured prompts

**Slides:** 11-14

#### Content Delivery

**Key Point 1: The Framework Introduction**
- Main message: Every prompt needs these four sections
- Framework/Pattern: ASK, CONTEXT, CONSTRAINTS, EXAMPLE
- Why it works: Forces completeness, prevents vague requests

**Key Point 2: Each Section Explained**
- ASK: What you want the AI to do - be specific
- CONTEXT: Background information the AI needs
- CONSTRAINTS: Limitations, format requirements, what to avoid
- EXAMPLE: Show what good output looks like (optional but powerful)

**Key Point 3: Live Transformation**
- Main message: Transform a vague request into a structured prompt
- Example walkthrough: Take "write an email" and add all four sections

#### Demo Instructions

**Demo Duration:** 5 minutes

**Demo Steps:**
1. Start with vague request: "Write an email to a client"
2. Add ASK: "Write a professional follow-up email to a client after our initial meeting"
3. Add CONTEXT: Client name, meeting date, what was discussed
4. Add CONSTRAINTS: Tone, length, include next steps
5. Add EXAMPLE: Show a sample paragraph style

**Demo Talking Points:**
> "Let's transform this vague request step by step..."
> "Notice how each section adds clarity. The AI now knows exactly what we want."

#### Practical Application

**Consulting Connection:**
> "Think about the emails, reports, and proposals you write regularly. Every one of these can be templated using this framework."

**Example Scenario:**
> "Imagine you need to write a project status update. With the framework: ASK is 'write a status update', CONTEXT is project name and current status, CONSTRAINTS are format and audience, EXAMPLE shows your preferred structure."

#### Facilitation Notes

**Common Confusion Point:**
Participants often confuse CONTEXT and CONSTRAINTS

**Clarification Approach:**
> "Think of CONTEXT as the background story - who, what, when. CONSTRAINTS are the rules - format, tone, length, what NOT to include."

---

### Closing (5 minutes)

**Slides:** 15-16

**Do Not Skip This Section** - even if running behind

#### Homework Preview

**Key Actions:**
1. Overview all three exercises briefly
2. Highlight that Exercise 1.3 sets up their prompt library home
3. Note estimated times
4. Point to resources and where to get help

**Script:**
> "Your homework includes three exercises totaling about 60 minutes.
>
> Exercise 1.1 is Markdown practice - about 20 minutes. You'll create a document with all the syntax we covered.
> Exercise 1.2 is your first structured prompt - 25 minutes. You'll use the framework on a real task.
> Exercise 1.3 is GitHub setup - 15 minutes. This creates your prompt library home.
>
> Everything you need is in your participant guide, including the templates and links to Markdown resources."

#### Resources and Support

> "If you get stuck, check the resources section in your participant guide first. The Markdown Tutorial at markdowntutorial.com is excellent for practice."

#### Next Week Preview

> "Next week we'll cover advanced prompting techniques - role prompting and few-shot learning - plus platform-specific optimizations. Make sure to complete your exercises so you have examples to build on."

#### Session Close

> "Questions before we wrap? ... Great first session. You've got the foundations now. See you next week!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Why Markdown specifically? Why not just write normally?**
A: AI models were trained on millions of Markdown documents - websites, documentation, code repos. They recognize and respect this structure. It's like speaking their native language.

**Q: Do I have to use this exact framework?**
A: The ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework is a proven pattern, but the principles matter more than rigid adherence. Use it as a starting point and adapt as you learn what works for your use cases.

**Q: How much context is too much?**
A: Include what's relevant to the task. If the AI is giving generic outputs, add more context. If it's including irrelevant details, you may have added too much. We'll refine this skill over the coming weeks.

### Technical Questions

**Q: Which AI platform should I use?**
A: Claude or ChatGPT both work well for this program. Use whichever you have access to. The techniques we teach are platform-agnostic.

**Q: Do I need a paid AI account?**
A: Free tiers work for all exercises in Block 1. Paid tiers give you more messages and sometimes better models, but aren't required.

**Q: What text editor should I use for Markdown?**
A: Any text editor works - VS Code, Notepad++, even basic Notepad. VS Code has a nice Markdown preview built in. For quick testing, use Dillinger.io in your browser.

### Scope Questions

**Q: Will we learn about images and AI art?**
A: This program focuses on text-based AI for professional work. Image generation uses some similar principles but isn't covered in depth.

**Q: What about coding with AI?**
A: Block 2 includes technical workflows. For Block 1, focus on getting comfortable with prompting regardless of the task type.

### Pushback/Objections

**Q: I've been using AI fine without all this structure. Is this really necessary?**
A: You can get occasional good results without structure, but consistency is the goal. When you need the same quality every time - for client work, for team processes - structure makes that possible.

**Q: This seems like a lot of overhead for a simple question.**
A: For simple questions, simple prompts work. This framework is for complex, repeatable tasks. By Week 3-4, you'll have templates that make this feel natural.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Screen share fails | Restart share, switch to application share | Ask a participant to share their screen |
| AI platform down | Switch to screenshots of prepared examples | Focus on Markdown demo only |
| Markdown preview not working | Use Dillinger.io as fallback | Walk through conceptually with text editor |
| Audio issues | Ask participants to type questions | Continue with video/text only |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| No AI access | "I can't log in" or "Account not working" | Help troubleshoot after session, exercises can wait |
| Markdown confusion | Frustration with syntax | Emphasize the tutorials in resources, it takes practice |
| Skepticism | "Why do I need this?" | Acknowledge valid concern, promise to show value through practice |
| Over-participation | One person dominating | "Great point, let's hear from someone else" |
| GitHub anxiety | "I've never used GitHub" | Reassure them Exercise 1.3 is gentle, we'll cover more in Week 3 |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Content too easy | "We know Markdown already" | Skip syntax details, spend more time on the framework |
| Content too hard | Many syntax questions | Slow down, show more examples, reference the tutorials |
| Off-topic tangent | Discussion of AI ethics, other tools | "Great topic for discussion in the community channel" |
| Time pressure | Running behind | Skip live demo, use prepared screenshots |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save any chat questions | For follow-up |
| Note what worked/didn't | Quick mental notes |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | ☐ |
| Answer pending questions in support channel | ☐ |
| Send follow-up message with key reminders about exercises | ☐ |
| Document issues encountered for curriculum improvement | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions (spot check GitHub repos) | ☐ |
| Identify participants needing support (no repo created, etc.) | ☐ |
| Prepare any clarifications for Week 2 opening | ☐ |
| Update this instructor guide with lessons learned | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 1.1 | `markdown-practice.md` | Participant's GitHub repo |
| 1.2 | `first-structured-prompt.md` | Participant's GitHub repo |
| 1.3 | GitHub repository with folder structure | GitHub URL |

### Progress Check Approach

**How to Verify Completion:**
- Check GitHub repos for the three deliverables
- Look for meaningful content, not just placeholder files
- Verify Markdown renders correctly

**Red flags indicating struggle:**
- No GitHub repo created
- Empty or template-only files
- Multiple syntax errors in Markdown

**Intervention Thresholds:**
- 1 exercise incomplete: Monitor, may be time constraints
- 2+ exercises incomplete: Reach out privately
- No GitHub repo: Offer 1:1 setup help

---

## Week-Specific Notes

### What Makes This Week Unique

- **First session**: Set tone and expectations for all 8 weeks
- **Foundation setting**: Everything builds on Markdown and the framework
- **GitHub introduction**: First exposure for some participants
- **Excitement vs. overwhelm**: Balance enthusiasm with realistic expectations

### Dependencies

**Builds On:**
- No prerequisites - this is Week 1
- Assumes basic text editing ability
- Assumes AI platform access (Claude or ChatGPT)

**Sets Up:**
- Week 2: Platform optimization builds on this framework
- Week 3: JSON structure uses similar Markdown concepts
- Week 4: Quality rubrics use Markdown tables
- Capstone: Everything starts with these fundamentals

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Some corporate firewalls block GitHub | Use GitHub web interface, not desktop app | Active |
| Free AI tiers have rate limits | Encourage participants to spread exercises across days | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- Can participants explain why structure matters?
- Do they understand the four sections of the framework?
- Are they asking practical "how would I use this for X" questions?

**Observable behavior indicating understanding:**
- Taking notes on the framework
- Nodding during the demo
- Asking clarifying questions

**Observable behavior indicating confusion:**
- Blank looks during syntax explanation
- No questions at all
- Frustration with terminology

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 1.1: Valid Markdown with all required elements
- Exercise 1.2: Clear use of ASK-CONTEXT-CONSTRAINTS-EXAMPLE
- Exercise 1.3: Functional GitHub repo with folder structure

**Common Issues to Flag:**
- Markdown syntax errors that break rendering
- Framework sections that are too vague or empty
- GitHub repos that are empty or missing structure

### Connecting to Capstone

**Capstone Relevance:**
This week's work contributes to the capstone by:
- GitHub repo becomes the capstone submission location
- Markdown skills used in all template documentation
- Framework becomes the basis for all prompt templates

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Quick pulse check: "On a scale of 1-5, how clear was today's content?"
- Note specific questions asked for FAQ development

**Improvement Log:**

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| | | | |

### Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial guide created | Training Team |

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Structure = clarity for AI = better outputs"
2. "Every prompt needs ASK, CONTEXT, CONSTRAINTS, and ideally EXAMPLE"
3. "Your GitHub repo is your prompt library - it grows with you over 8 weeks"

### If You Only Have Time For One Thing

The ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework. Participants can learn Markdown syntax from tutorials, but understanding WHY to structure prompts is the critical insight.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Why Markdown works | "Like speaking AI's native language" | When explaining why this format |
| The framework | "A recipe with ingredients (context) and instructions (ask/constraints)" | When someone is confused about the sections |
| Code blocks | "A quarantine zone for data - keeps it separate from instructions" | When explaining prompt injection prevention |

---

**Navigation:** **Week 1** | [Week 2 Instructor Guide →](../week-2/instructor-guide.md)
