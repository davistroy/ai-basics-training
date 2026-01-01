# **INSTRUCTOR GUIDE: BLOCK 1 WEEK 3**
## **JSON Fundamentals + GitHub Basics**

**Block:** 1: AI Prompting Mastery
**Week:** 3 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | JSON syntax for configuration files and GitHub version control basics |
| **Difficulty Level** | Medium |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Yes - Building JSON step-by-step and GitHub commit workflow |
| **Tech Setup Needed** | Text editor, JSONLint.com open, GitHub account, sample style.json |
| **Common Challenges** | JSON syntax errors (trailing commas, single quotes), GitHub terminology confusion |

---

## Navigation

**Block Navigation:** [← Week 2 Instructor Guide](../week-2/instructor-guide.md) | **Week 3** | [Week 4 Instructor Guide →](../week-4/instructor-guide.md)

**Related Materials:**
- [Week 3 Presentation](presentation.md)
- [Week 3 Participant Guide](participant-guide.md)
- [Block 1 Main Document](../block-1.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 3 materials | ☐ |
| Test demo | Practice building style.json live, common errors to show | ☐ |
| Check resources | Verify JSONLint.com, JSON.org links work | ☐ |
| Prepare backup | Create screenshots of JSON validation and GitHub workflow | ☐ |
| Review previous | Check Week 2 exercise submissions and note common issues | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice JSON demo - most time-sensitive segment | ☐ |
| Prepare materials | Have JSONLint open, sample JSON with errors prepared | ☐ |
| Check participant progress | Review who completed Week 2 exercises | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, JSONLint, GitHub, text editor | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Ask about role prompting and few-shot experiences | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 5 min | Opening | Recap Week 2, preview JSON journey | Quick context |
| 0:05 | 8 min | Segment 1 | Why JSON? Configuration concept | Motivation |
| 0:13 | 15 min | Segment 2 | JSON Syntax Essentials | Core technical content |
| 0:28 | 10 min | Segment 3 | Creating style.json | Practical application |
| 0:38 | 7 min | Segment 4 | GitHub Basics | Version control intro |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Shorten JSON syntax to just objects, arrays, and strings
- Reference JSONLint and tutorials for self-study on edge cases
- Skip GitHub workflow demo, cover conceptually

**If Running Ahead:**
- Show more JSON validation error examples
- Walk through more GitHub operations
- Take deeper questions about JSON structure design

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Why JSON | 0:13 | Keep motivation brief, more time for syntax |
| End JSON Syntax | 0:28 | Critical section - don't rush |
| Start GitHub | 0:38 | Must cover at least conceptually |

---

## Session Delivery Guide

### Opening (5 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants back
2. Quick recap of Week 2: role prompting, few-shot, platforms
3. Preview today's shift to configuration and version control
4. Set expectations: more technical, but foundational

**Opening Script:**
> "Welcome to Week 3. Last week we added power tools - role prompting and few-shot learning. Today we're adding infrastructure. JSON for configuration and GitHub for version control. These might feel more technical, but they're essential foundations that make everything else work better."

**Engagement Opportunity:**
> "Quick question: Who created a few-shot template that you're actually planning to reuse?"

[Wait for responses - validates Week 2 learning]

---

### Segment 1: Why JSON? (8 minutes)

**Learning Objective:** Understand why JSON configuration files improve AI output consistency

**Slides:** 4-5

#### Content Delivery

**Key Point 1: The Consistency Problem**
- Main message: AI outputs vary even with identical prompts
- Example to use: "Write a professional email" produces different tones each time
- Common misconception: Just adding "professional" is enough for consistency

**Key Point 2: Configuration Files as Solution**
- Main message: Store preferences in a file, reference every time
- Demonstration: Preview what style.json enables
- Participant relevance: "Your voice" captured and applied consistently

**Key Point 3: Why JSON Specifically**
- Main message: Human-readable, AI-parseable, industry standard
- Practice preview: Exercise 3.2 creates personal style.json

#### Facilitation Notes

**Watch For:**
- Intimidation at "JSON" terminology - reassure it's simpler than it sounds
- Questions about other formats (YAML, etc.) - acknowledge but stay focused

**If Asked About "Why not just write preferences in Markdown?"**
> "You can, and we did in Week 1 with constraints. JSON adds structure that's more precise and reusable. We'll see why as we learn the syntax."

**Transition to Segment 2:**
> "Let's learn the syntax. JSON looks intimidating at first, but there are only a few patterns to master."

---

### Segment 2: JSON Syntax Essentials (15 minutes)

**Learning Objective:** Read and write valid JSON structures

**Slides:** 6-10

#### Content Delivery

**Key Point 1: Basic Structure**
- Main message: Key-value pairs in curly braces
- Visual to emphasize: `{ "key": "value" }`
- Build up complexity gradually

**Key Point 2: Data Types**
- Main message: Strings, numbers, booleans, null, arrays, objects
- Hands-on reference: Connect to Exercise 3.1
- Show each type with simple examples

**Key Point 3: Common Mistakes**
- Main message: Trailing commas and single quotes are the top errors
- Real-world application: Show error, then fix, use JSONLint
- Critical emphasis: Always validate before using

#### Demo Instructions

**Demo Duration:** 5 minutes

**Setup Required:**
- Text editor (VS Code or similar)
- JSONLint.com open
- Prepared JSON with intentional errors

**Demo Steps:**
1. Start with empty `{}`, add a simple key-value pair
2. Add different data types one by one
3. Intentionally add a trailing comma - show error in JSONLint
4. Fix the error, show validation passing

**Demo Talking Points:**
> "Let me build this step by step so you see how it comes together..."
> "Now watch what happens when I add this trailing comma... JSONLint catches it immediately."
> "This is why we always validate. One extra comma breaks everything."

**Backup Plan:**
If demo fails:
1. Use prepared screenshots showing error states and fixes
2. Walk through the syntax conceptually with slide examples
3. Emphasize JSONLint for self-checking

#### Facilitation Notes

**Energy Check:**
This is dense technical content. Keep it practical and moving.

**Transition to Segment 3:**
> "Now you know the syntax. Let's apply it to something immediately useful - your personal style.json file."

---

### Segment 3: Creating style.json (10 minutes)

**Learning Objective:** Create a style.json file capturing personal preferences

**Slides:** 11-13

#### Content Delivery

**Key Point 1: What Goes in style.json**
- Main message: Voice, writing preferences, things to avoid
- Framework/Pattern: Show the template structure
- Customization: This is personal - no single right answer

**Key Point 2: Using style.json in Prompts**
- Main message: Reference the file, AI follows the configuration
- Example walkthrough: Show a prompt that incorporates style.json
- Practical benefit: Consistent voice across all outputs

**Key Point 3: Evolving Your Style**
- Main message: This isn't fixed - refine as you learn what works
- Connection to homework: Exercise 3.2 creates first version

#### Demo Instructions

**Demo Duration:** 3 minutes

**Setup Required:**
- Empty JSON file ready to populate
- style.json template on screen

**Demo Steps:**
1. Start with the template structure
2. Fill in personal preferences as examples
3. Show how to reference in a prompt

**Demo Talking Points:**
> "I'll show you how I'd fill this out. Tone: professional but approachable. Things to avoid: jargon, passive voice..."
> "Now in my prompts, I can say 'Follow this style guide:' and paste the JSON."

---

### Segment 4: GitHub Basics (7 minutes)

**Learning Objective:** Understand version control concepts and basic GitHub workflow

**Slides:** 14-17

#### Content Delivery

**Key Point 1: Why Version Control**
- Main message: Track changes, collaborate, never lose work
- Analogy: "Like track changes in Word, but for everything"
- Practical benefit: See what changed, when, why

**Key Point 2: Key Concepts**
- Main message: Repository, commit, push, pull
- Keep simple: Don't overwhelm with advanced concepts
- Reference Week 1: They've already used GitHub, now understanding it

**Key Point 3: Basic Workflow**
- Main message: Edit → Stage → Commit → Push
- Practical demo if time: Show one commit with meaningful message

#### Facilitation Notes

**Watch For:**
- Git/GitHub confusion - clarify Git is the tool, GitHub is the service
- Intimidation from "version control" - keep it simple and practical

**Common Confusion Point:**
Commit messages - why they matter

**Clarification Approach:**
> "Good commit messages are like notes to your future self. 'Updated stuff' tells you nothing. 'Add email response few-shot template' tells you exactly what changed."

---

### Closing (embedded in Segment 4)

**Do Not Skip This Section** - even if running behind

#### Homework Preview

**Key Actions:**
1. Overview all three exercises briefly
2. Highlight that JSONLint validation is required
3. Note GitHub upload for Exercise 3.3

**Script:**
> "Your homework includes three exercises totaling about 60 minutes.
>
> Exercise 3.1 is JSON practice - 15 minutes. Get comfortable with the syntax.
> Exercise 3.2 is creating your style.json - 25 minutes. This is your personal voice configuration.
> Exercise 3.3 is GitHub practice - 20 minutes. Uploading files, making commits, using version control.
>
> Important: Validate all JSON with JSONLint before submitting. Invalid JSON breaks everything."

#### Next Week Preview

> "Next week we're tackling quality - how to evaluate AI outputs systematically. You'll create quality rubrics and learn the LLM-as-judge pattern. Your style.json from this week becomes part of how we evaluate outputs."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Why JSON instead of just writing preferences in my prompts?**
A: JSON is structured data that can be parsed precisely. It also becomes reusable - you reference the same file in every prompt instead of rewriting preferences each time.

**Q: Does the AI actually read JSON, or do I need to convert it?**
A: AI can read JSON directly. You paste it into your prompt and the AI parses the structure. That's one reason we use it - human-readable AND machine-readable.

**Q: How detailed should my style.json be?**
A: Start simple. Add detail only when outputs aren't matching your preferences. You can always expand it. Better to start minimal and grow.

### Technical Questions

**Q: My JSON keeps failing validation - how do I debug?**
A: JSONLint highlights the line with the error. Common issues: trailing comma after last item, single quotes instead of double, missing comma between items.

**Q: Do I need to learn Git commands?**
A: Not for Block 1. The GitHub web interface handles everything you need. Block 2 introduces more Git if you want it.

**Q: Can I use a different JSON validator?**
A: Yes - VS Code has built-in JSON validation, and there are many online validators. JSONLint is recommended because it gives clear error messages.

### Scope Questions

**Q: What about YAML or other configuration formats?**
A: JSON is the most universally supported. YAML is also good but has indentation-based syntax that causes more errors. Stick with JSON for now.

**Q: Will we use GitHub for team collaboration?**
A: Week 5 introduces collaboration features. For now, focus on your personal repository and version control basics.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| JSONLint not loading | Use VS Code JSON validation | Show validation conceptually |
| GitHub not loading | Continue with JSON content | Cover GitHub in office hours |
| JSON demo errors not showing | Have screenshot backup ready | Walk through error examples verbally |
| Text editor issues | Use online editor like dillinger | Any text editor works |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| JSON syntax intimidation | "This looks like coding" | Reassure: "Just key-value pairs, like a form" |
| Trailing comma confusion | Repeated validation errors | Show pattern: last item has no comma |
| GitHub terminology confusion | Mixing up push/pull/commit | Use analogies: commit = save, push = upload |
| Overwhelmed by both topics | Disengagement | Focus on JSON first, GitHub can wait |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Too technical for some | Many basic questions | Slow down, use more analogies |
| Too basic for others | "I already know JSON" | Ask them to help peers, add advanced tips |
| JSON syntax tedious | Restlessness during examples | Move faster, emphasize practical use |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save any chat questions | Especially JSON syntax questions |
| Note what worked/didn't | Especially demo flow |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | ☐ |
| Answer pending questions about JSON syntax | ☐ |
| Send follow-up with JSONLint link and common errors | ☐ |
| Document issues encountered for curriculum improvement | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions (validate JSON files) | ☐ |
| Identify participants with invalid JSON | ☐ |
| Prepare any clarifications for Week 4 opening | ☐ |
| Update this instructor guide with lessons learned | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 3.1 | `json-practice.json` | Participant's GitHub repo |
| 3.2 | `style.json` + test results | Participant's GitHub repo |
| 3.3 | GitHub activity (commits, README update) | GitHub commit history |

### Progress Check Approach

**How to Verify Completion:**
- Validate JSON files with JSONLint
- Check GitHub commit history for meaningful messages
- Verify style.json has personalized content (not just template)

**Red flags indicating struggle:**
- Invalid JSON (validation errors)
- style.json that's just the template without customization
- No new GitHub commits

**Intervention Thresholds:**
- Invalid JSON: Must fix before Week 4
- No style.json: Core requirement for Block 1
- GitHub issues: Offer 1:1 support

---

## Week-Specific Notes

### What Makes This Week Unique

- **Technical pivot**: More structured data, less creative prompting
- **Foundation setting**: style.json becomes capstone component
- **GitHub deepening**: From storage to version control
- **Two distinct topics**: JSON and GitHub - different skill sets

### Dependencies

**Builds On:**
- Week 1: Markdown formatting (JSON is structured data like Markdown is structured text)
- Week 2: Preferences from role prompting inform style.json content
- Previous GitHub setup from Week 1

**Sets Up:**
- Week 4: Quality rubrics reference style.json for evaluation
- Week 5: GitHub collaboration builds on basics
- Capstone: style.json is required deliverable

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Trailing comma errors are extremely common | Emphasize heavily, provide validation checklist | Active |
| GitHub web interface varies by browser | Recommend Chrome, test alternatives | Active |
| JSON syntax highlighting varies by editor | Recommend VS Code or use JSONLint | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- Can participants identify valid vs. invalid JSON?
- Do they understand why style.json helps with consistency?
- Are they comfortable with basic GitHub terminology?

**Observable behavior indicating understanding:**
- Nodding during JSON syntax explanations
- Questions about their specific use cases
- Recognizing errors in demo

**Observable behavior indicating confusion:**
- Blank looks during JSON structure building
- Questions that mix up JSON terms
- No questions at all (overwhelm)

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 3.1: Valid JSON with all required data types
- Exercise 3.2: Personalized style.json (not just template)
- Exercise 3.3: Meaningful commit messages

**Common Issues to Flag:**
- JSON validation errors (must fix)
- style.json that doesn't reflect actual preferences
- Single commit with "updates" message

### Connecting to Capstone

**Capstone Relevance:**
This week's work contributes to the capstone by:
- style.json is required capstone component
- GitHub practices establish repository quality
- JSON skills used for any structured data

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Note which JSON concepts needed most clarification
- Track common validation errors for better examples

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

1. "JSON is structured data - like a digital form with questions and answers"
2. "Always validate JSON before using - one error breaks everything"
3. "style.json is your voice captured in code - reference it every time for consistency"

### If You Only Have Time For One Thing

JSON syntax and validation. style.json creation can be homework-driven, but understanding the syntax is essential.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| JSON structure | "A form with questions (keys) and answers (values)" | When introducing JSON |
| Trailing commas | "Like having an extra 'and' at the end of a list" | When showing common errors |
| Git commits | "Like saving a video game - you can go back to any save point" | When explaining version control |
| style.json | "Your personal brand guide in code" | When explaining the purpose |

---

**Navigation:** [← Week 2 Instructor Guide](../week-2/instructor-guide.md) | **Week 3** | [Week 4 Instructor Guide →](../week-4/instructor-guide.md)
