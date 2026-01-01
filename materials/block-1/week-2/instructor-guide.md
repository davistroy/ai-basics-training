# **INSTRUCTOR GUIDE: BLOCK 1 WEEK 2**
## **Advanced Prompting + Platform Optimization**

**Block:** 1: AI Prompting Mastery
**Week:** 2 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Role prompting, few-shot learning, and platform-specific optimizations |
| **Difficulty Level** | Low-Medium |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Yes - Few-shot prompt creation and platform comparison |
| **Tech Setup Needed** | Access to Claude AND ChatGPT for comparison demo |
| **Common Challenges** | Over-specifying roles, choosing number of examples for few-shot |

---

## Navigation

**Block Navigation:** [← Week 1 Instructor Guide](../week-1/instructor-guide.md) | **Week 2** | [Week 3 Instructor Guide →](../week-3/instructor-guide.md)

**Related Materials:**
- [Week 2 Presentation](presentation.md)
- [Week 2 Participant Guide](participant-guide.md)
- [Block 1 Main Document](../block-1.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 2 materials | ☐ |
| Test demo | Create and test a few-shot prompt with real data | ☐ |
| Check resources | Verify platform documentation links work | ☐ |
| Prepare backup | Create screenshots of platform comparison | ☐ |
| Review previous | Check Week 1 exercise submissions and questions | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice transitions, especially for platform demo | ☐ |
| Prepare materials | Have both Claude and ChatGPT ready and logged in | ☐ |
| Check participant progress | Review who completed Week 1 exercises | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, Claude, ChatGPT, resources | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Ask how Week 1 exercises went | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 5 min | Opening | Recap Week 1, address common issues | Quick and focused |
| 0:05 | 12 min | Segment 1 | Role Prompting | Core technique |
| 0:17 | 12 min | Segment 2 | Few-Shot Learning | Most powerful technique |
| 0:29 | 12 min | Segment 3 | Platform Optimization | Claude vs ChatGPT tips |
| 0:41 | 4 min | Closing | Thinking prompts, homework preview | Don't skip |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Shorten platform optimization to just top 2 tips for each platform
- Reference the documentation links for detailed platform guides
- Skip the thinking prompts segment

**If Running Ahead:**
- Spend more time on few-shot examples
- Take additional questions about role specificity
- Live demo a thinking prompt

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Role Prompting | 0:17 | Cut to just the core pattern |
| End Few-Shot | 0:29 | Must start platforms by here |
| Start Closing | 0:41 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (5 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants back
2. Quick recap of Week 1: Markdown and ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework
3. Address common issues from Week 1 exercises
4. Preview today's advanced techniques

**Opening Script:**
> "Welcome back to Week 2. Last week we covered the foundation - Markdown structure and the ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework. Today we're adding power tools to your toolkit: role prompting, few-shot learning, and platform-specific optimizations."

**Engagement Opportunity:**
> "Quick check-in: Who used the ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework this week for a real task? What was your experience?"

[Wait for 1-2 responses - this helps gauge if Week 1 concepts are sticking]

---

### Segment 1: Role Prompting (12 minutes)

**Learning Objective:** Use role prompting to activate domain-specific patterns in AI responses

**Slides:** 4-7

#### Content Delivery

**Key Point 1: What Is Role Prompting**
- Main message: Telling AI to adopt a specific persona activates relevant "knowledge patterns"
- Example to use: "You are a senior software engineer" vs. just asking for code review
- Common misconception: More detailed roles always work better (actually, over-specification can confuse)

**Key Point 2: The Pattern**
- Main message: Role + Domain + Style = Effective role prompt
- Demonstration: Show the three-part structure
- Participant relevance: Match roles to their actual work tasks

**Key Point 3: When to Use Roles**
- Main message: Different tasks need different expertise levels
- Practice preview: Exercise 2.1 tests different role specifications

#### Demo Instructions

**Demo Duration:** 4 minutes

**Setup Required:**
- AI platform ready (Claude or ChatGPT)
- Prepared task to analyze with three different role prompts

**Demo Steps:**
1. Show same task with no role - note the generic response
2. Show with basic role "You are a consultant" - note improvement
3. Show with specific role "You are a senior management consultant with 15 years experience" - show best results

**Demo Talking Points:**
> "Watch how the same question gets different treatment with different roles..."
> "Notice how the specific expertise changes not just what's said, but how it's framed."

**Backup Plan:**
If demo fails:
1. Use prepared screenshots showing all three responses
2. Walk through the pattern conceptually
3. Participants will test this themselves in Exercise 2.1

#### Facilitation Notes

**Watch For:**
- Questions about what level of detail is right for roles
- Confusion about when roles help vs. when they overcomplicate

**If Asked About "How specific should roles be?"**
> "Start simple and add detail only if the output needs more expertise. A 'senior software engineer' is usually enough - you don't need their entire career history."

**Transition to Segment 2:**
> "Role prompting activates the right expertise. But what if you need a very specific output format or style? That's where few-shot learning comes in."

---

### Segment 2: Few-Shot Learning (12 minutes)

**Learning Objective:** Create few-shot prompts that produce consistent, formatted outputs

**Slides:** 8-11

#### Content Delivery

**Key Point 1: What Is Few-Shot Learning**
- Main message: Providing examples teaches the AI through demonstration
- Visual to emphasize: The input→output pattern
- Why it works: Shows exact format expectations, reduces ambiguity dramatically

**Key Point 2: The Two-Step Workflow**
- Main message: Examples first, then your actual input
- Hands-on reference: Connect to Exercise 2.2
- Best practices: 2-3 examples is usually optimal, order matters

**Key Point 3: Real-World Application**
- Main message: Any repeatable task can use few-shot
- Real-world application: Email responses, data formatting, content summarization

#### Demo Instructions

**Demo Duration:** 5 minutes

**Setup Required:**
- Prepared few-shot prompt for data extraction or formatting
- AI platform ready

**Demo Steps:**
1. Show the structure: Task description, Format specification, Examples, Actual input
2. Run the prompt
3. Show how the output matches the example format exactly

**Demo Talking Points:**
> "I'm giving the AI three examples of what I want. Watch how precisely it follows this pattern..."
> "Notice I put my most complex example last - order matters."

#### Interactive Element

**Activity Type:** Quick poll

**Activity Duration:** 1 minute

**Instructions:**
1. Ask: "What task do you do repeatedly that could benefit from few-shot prompting?"
2. Collect 3-4 answers verbally
3. Briefly note how few-shot would help each

**Debrief Points:**
> "Great examples - data formatting, email responses, documentation. All perfect for few-shot."

#### Facilitation Notes

**Energy Check:**
At 20 minutes in, this is the meaty content. Keep examples practical and relatable.

**Transition to Segment 3:**
> "Now you have role prompting and few-shot learning. But different AI platforms respond differently to these techniques. Let's talk optimization."

---

### Segment 3: Platform Optimization (12 minutes)

**Learning Objective:** Apply platform-specific techniques to improve prompt effectiveness

**Slides:** 12-15

#### Content Delivery

**Key Point 1: Platform Differences**
- Main message: Each AI platform has formatting preferences
- Framework/Pattern: Universal techniques vs. platform-specific
- Example walkthrough: What works on Claude vs. ChatGPT

**Key Point 2: Claude-Specific Tips**
- Main message: XML tags, clear headers, reasoning requests
- Real-world application: When to use `<instructions>` tags

**Key Point 3: ChatGPT-Specific Tips**
- Main message: System messages, JSON mode, iterative refinement
- Example walkthrough: Custom Instructions feature

**Key Point 4: Universal Techniques**
- Main message: Code blocks, clear headers, explicit constraints work everywhere
- Connection to homework: Platform comparison exercise

#### Demo Instructions

**Demo Duration:** 4 minutes

**Setup Required:**
- Same prompt ready in both Claude and ChatGPT
- Both platforms open in separate tabs

**Demo Steps:**
1. Run identical prompt on both platforms
2. Point out differences in responses
3. Show a platform-specific optimization (e.g., XML tags on Claude)

**Demo Talking Points:**
> "Same prompt, watch the differences..."
> "On Claude, if I add these XML tags, notice how it handles the structure..."

#### Facilitation Notes

**Common Confusion Point:**
Participants may think one platform is "better" - emphasize that each has strengths

**Clarification Approach:**
> "It's not about which is better - it's about knowing when to use which, and how to optimize for each."

---

### Segment 4: Thinking Prompts (Brief - within closing)

**Learning Objective:** Understand when to ask AI to reason step-by-step

**Slide:** 16

**Key Point:**
- Main message: "Think through this step-by-step" improves accuracy on complex tasks
- When to use: Multi-step problems, analysis, debugging
- Quick tip: Add to prompts when accuracy matters more than speed

---

### Closing (4 minutes)

**Slides:** 17-19

**Do Not Skip This Section** - even if running behind

#### Homework Preview

**Key Actions:**
1. Overview all three exercises briefly
2. Highlight that Exercise 2.3 requires access to two platforms
3. Note estimated times
4. Point to resources and platform documentation

**Script:**
> "Your homework includes three exercises totaling about 60 minutes.
>
> Exercise 2.1 is role prompting experiments - 20 minutes. You'll test the same task with different role specifications.
> Exercise 2.2 is few-shot prompt creation - 25 minutes. You'll build a reusable few-shot template for a real task.
> Exercise 2.3 is platform comparison - 15 minutes. Test one prompt on two different platforms.
>
> For Exercise 2.3, you'll need access to at least two platforms. Claude and ChatGPT both have free tiers."

#### Resources and Support

> "The participant guide has links to official platform documentation. Anthropic's prompt engineering guide and OpenAI's guide are both excellent resources."

#### Next Week Preview

> "Next week we're introducing JSON - structured data for AI configuration. We'll create your `style.json` file that defines your personal brand voice. And we'll do more with GitHub."

#### Session Close

> "Questions before we wrap? ... Great session. You've got three powerful techniques now - roles, few-shot, and platform optimization. See you next week!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: How do I know if I should use role prompting or few-shot?**
A: Use roles for expertise and perspective. Use few-shot for format and style consistency. You can combine them - give a role AND show examples.

**Q: How many examples is too many for few-shot?**
A: 2-3 is usually optimal. More examples take up context window and can confuse if they're inconsistent. Quality over quantity.

**Q: Do thinking prompts slow down the response?**
A: Yes, slightly. The AI generates more text. Use them when accuracy matters more than speed - complex analysis, debugging, multi-step reasoning.

### Technical Questions

**Q: Can I use platform-specific techniques if I don't know which platform my prompt will run on?**
A: Stick to universal techniques (code blocks, headers, explicit constraints) when portability matters. Add platform-specific optimizations when you know the target.

**Q: Do I need paid accounts for the exercises?**
A: No, free tiers work for all Block 1 exercises. You might hit rate limits if you test a lot in one day - spread it out.

### Scope Questions

**Q: What about other platforms like Gemini or Copilot?**
A: We focus on Claude and ChatGPT as they're most common. The principles transfer - test to find what works on your platform.

**Q: Will we cover system prompts and API usage?**
A: Block 2 gets more technical with automation. Block 1 focuses on the prompts themselves, which work in chat interfaces.

### Pushback/Objections

**Q: Isn't role prompting just pretending? Does the AI actually have expertise?**
A: The AI doesn't have real expertise, but it was trained on text by experts. The role activates relevant patterns from that training. It's about pulling the right knowledge, not creating new knowledge.

**Q: Few-shot seems like a lot of setup for one prompt.**
A: The setup time pays off when you use the prompt repeatedly. Build once, use many times. That's why we save them in your GitHub library.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| AI platform down | Switch to other platform for demo | Use prepared screenshots |
| Rate limit hit | Have backup account or screenshots ready | Walk through conceptually |
| Response too long | Stop generation, summarize what was shown | Pre-save shorter examples |
| Comparison demo fails | Show one platform only | Reference the screenshots |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Week 1 concepts shaky | Questions about ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework | Quickly review, point to Week 1 guide |
| Over-complicating roles | Very long role descriptions | Encourage simpler, test and refine |
| No access to second platform | "I only have ChatGPT" | Offer to demo comparison, accept one-platform exercise |
| Feature confusion | Mixing up role vs. few-shot | Clarify: role = who, few-shot = how |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Too basic for some | "I already use roles" | Add advanced tips, emphasize platform optimization |
| Too fast for others | Many clarifying questions | Slow down, add examples |
| Platform preference debates | "But ChatGPT is better" | Redirect to "different strengths for different tasks" |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save any chat questions | For follow-up |
| Note what worked/didn't | Especially for demos |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | ☐ |
| Answer pending questions in support channel | ☐ |
| Send follow-up with platform documentation links | ☐ |
| Document issues encountered for curriculum improvement | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions (spot check) | ☐ |
| Identify participants needing support | ☐ |
| Prepare any clarifications for Week 3 opening | ☐ |
| Update this instructor guide with lessons learned | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 2.1 | `role-prompting-experiments.md` | Participant's GitHub repo |
| 2.2 | `few-shot-template.md` | Participant's GitHub repo |
| 2.3 | `platform-comparison.md` | Participant's GitHub repo |

### Progress Check Approach

**How to Verify Completion:**
- Check GitHub repos for new files
- Look for actual test results, not just templates
- Verify they used different role specifications in 2.1
- Check that 2.3 compares two platforms

**Red flags indicating struggle:**
- Only one role variation in 2.1 (should have 3)
- Few-shot prompt without actual examples
- Platform comparison with only one platform

**Intervention Thresholds:**
- 1 exercise incomplete: Monitor
- 2+ exercises incomplete: Reach out privately
- Still missing Week 1 exercises: 1:1 conversation

---

## Week-Specific Notes

### What Makes This Week Unique

- **Technique intensity**: Three new techniques in one session
- **Platform differences**: First time discussing tool-specific optimizations
- **Demo heavy**: Multiple live demonstrations needed
- **Combination potential**: Techniques can be combined, adding complexity

### Dependencies

**Builds On:**
- Week 1: Markdown structure for formatting
- Week 1: ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework for organizing prompts
- Assumes participants have working AI platform access

**Sets Up:**
- Week 3: JSON structures will capture style preferences
- Week 4: Quality rubrics will evaluate prompt outputs
- Capstone: Templates use these techniques

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Free tier rate limits | Encourage spreading exercises across days | Active |
| Platform UI changes | Screenshots may not match exactly | Monitor |
| Some participants only have one platform | Accept modified Exercise 2.3 | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- Can participants distinguish when to use role vs. few-shot?
- Do they understand that platform optimization is about strengths, not superiority?
- Are they asking practical application questions?

**Observable behavior indicating understanding:**
- Nodding during technique explanations
- Questions about their specific use cases
- Notes being taken on patterns

**Observable behavior indicating confusion:**
- Questions that confuse role with few-shot
- Blank looks during platform comparison
- No questions at all (may indicate overwhelm)

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 2.1: Three distinct role variations with analysis
- Exercise 2.2: Working few-shot template with real examples
- Exercise 2.3: Thoughtful comparison with specific observations

**Common Issues to Flag:**
- Role prompts that are too long or complicated
- Few-shot examples that are inconsistent with each other
- Platform comparison that just says "they're the same"

### Connecting to Capstone

**Capstone Relevance:**
This week's work contributes to the capstone by:
- Role prompting becomes part of prompt templates
- Few-shot templates become capstone deliverables
- Platform optimization knowledge informs template design

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Note which demos worked best
- Capture questions about technique combinations

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

1. "Role prompting activates the right expertise - like consulting the right specialist"
2. "Few-shot is showing, not telling - examples beat descriptions"
3. "Different platforms, different strengths - optimize for where you're working"

### If You Only Have Time For One Thing

Few-shot learning. It's the most powerful technique for consistent outputs and directly applicable to real work.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Role prompting | "Consulting a specialist vs. asking a generalist" | When explaining why roles improve output |
| Few-shot learning | "Training by showing, like teaching a recipe" | When explaining the example pattern |
| Platform optimization | "Different tools for different jobs - hammer vs. screwdriver" | When discussing Claude vs. ChatGPT |

---

**Navigation:** [← Week 1 Instructor Guide](../week-1/instructor-guide.md) | **Week 2** | [Week 3 Instructor Guide →](../week-3/instructor-guide.md)
