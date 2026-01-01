# **INSTRUCTOR GUIDE: BLOCK 1 WEEK 4**
## **Quality Rubrics + Workflow Design**

**Block:** 1: AI Prompting Mastery
**Week:** 4 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Creating quality rubrics, LLM-as-judge pattern, comparison gates |
| **Difficulty Level** | Medium |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Yes - LLM-as-judge evaluation of sample content |
| **Tech Setup Needed** | AI platform for live evaluation demo, sample content to evaluate |
| **Common Challenges** | Rubric criteria too vague, understanding when to use quality gates |

---

## Navigation

**Block Navigation:** [← Week 3 Instructor Guide](../week-3/instructor-guide.md) | **Week 4** | [Week 5 Instructor Guide →](../week-5/instructor-guide.md)

**Related Materials:**
- [Week 4 Presentation](presentation.md)
- [Week 4 Participant Guide](participant-guide.md)
- [Block 1 Main Document](../block-1.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 4 materials | ☐ |
| Test demo | Prepare sample content and run LLM-as-judge evaluation | ☐ |
| Create rubric | Have a sample quality rubric ready for demonstration | ☐ |
| Prepare backup | Create screenshots of evaluation output | ☐ |
| Review previous | Check Week 3 exercise submissions, especially `style.json` files | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice LLM-as-judge demo - ensure it fits in time | ☐ |
| Prepare materials | Sample content ready, evaluation prompt prepared | ☐ |
| Check participant progress | Review who completed Week 3, especially `style.json` | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, AI platform, sample rubric | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Ask how `style.json` testing went | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 5 min | Opening | Recap Week 3, preview quality focus | Set context |
| 0:05 | 8 min | Segment 1 | The Quality Problem | Why we need systems |
| 0:13 | 12 min | Segment 2 | Creating Quality Rubrics | Core technique |
| 0:25 | 12 min | Segment 3 | LLM-as-Judge Pattern | Advanced technique |
| 0:37 | 8 min | Segment 4 | Comparison Gates + Close | Additional technique + homework |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Shorten rubric creation to just the concept and one criterion
- Reference participant guide for full rubric examples
- Skip comparison gates, cover conceptually in homework preview

**If Running Ahead:**
- Spend more time on LLM-as-judge demo
- Show multiple evaluation examples
- Discuss quality workflow integration

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Quality Problem | 0:13 | Keep motivation concise |
| End Rubric Creation | 0:25 | Must allow time for LLM-as-judge |
| End LLM-as-Judge | 0:37 | Can shorten comparison gates |

---

## Session Delivery Guide

### Opening (5 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants back
2. Quick recap of Week 3: JSON configuration, `style.json`, GitHub
3. Preview today's shift to quality evaluation
4. Set expectations: systematic quality improvement

**Opening Script:**
> "Welcome to Week 4. Last week we built infrastructure - JSON for configuration and GitHub for version control. Now we're adding quality systems. Today you'll learn how to evaluate AI outputs systematically and, here's the key insight, use AI itself to do the evaluation."

**Engagement Opportunity:**
> "Quick question: When you tested your `style.json` this week, how did you know if the AI actually followed your preferences? How did you evaluate the output?"

[Wait for responses - leads into the quality problem]

---

### Segment 1: The Quality Problem (8 minutes)

**Learning Objective:** Understand why systematic quality evaluation is necessary

**Slides:** 4-5

#### Content Delivery

**Key Point 1: The Current State**
- Main message: Without systems, quality is subjective and inconsistent
- Example to use: "This email looks good" - but what makes it good?
- Common misconception: Quality is obvious and doesn't need measurement

**Key Point 2: The Cost of Ad-Hoc Quality**
- Main message: Manual review is exhausting and doesn't scale
- Demonstration: Preview what happens as prompt usage grows
- Participant relevance: They'll have dozens of templates by capstone

**Key Point 3: The Solution Preview**
- Main message: Systematic evaluation with clear criteria
- Practice preview: This week's exercises create quality tools

#### Facilitation Notes

**Watch For:**
- Skepticism about needing quality systems for "just prompts"
- Questions about when this becomes overkill

**If Asked About "Isn't this too much for simple prompts?"**
> "For a one-time question, you're right - you don't need this. But for templates you use repeatedly, for high-stakes deliverables, for team-shared prompts - quality systems are essential. Start simple, scale up as needed."

**Transition to Segment 2:**
> "Let's build your first quality tool - a rubric that removes subjectivity from evaluation."

---

### Segment 2: Creating Quality Rubrics (12 minutes)

**Learning Objective:** Create specific, measurable quality rubrics for AI outputs

**Slides:** 6-9

#### Content Delivery

**Key Point 1: What Is a Rubric**
- Main message: Scoring guide with specific criteria and descriptions
- Visual to emphasize: The 1-5 scale with descriptions for each level
- Key insight: Descriptions make it measurable, not subjective

**Key Point 2: Rubric Structure**
- Main message: Criterion + Weight + Score Levels
- Hands-on reference: Connect to Exercise 4.1
- Show the Markdown table format

**Key Point 3: Writing Good Criteria**
- Main message: Specific, observable, relevant
- Common mistakes: Vague criteria like "good quality" or "appropriate"
- Example walkthrough: Transform vague criterion to specific

#### Demo Instructions

**Demo Duration:** 4 minutes

**Setup Required:**
- Blank document ready
- Sample vague criterion to improve

**Demo Steps:**
1. Show a vague criterion: "Quality: Is the email high quality?"
2. Ask: "How would you score this? What does '3' look like vs '5'?"
3. Transform to specific: Clarity - "Purpose clear in first sentence" (5) vs. "Purpose unclear" (1)
4. Show the full table format

**Demo Talking Points:**
> "This criterion is useless as written. Let me show you how to make it measurable..."
> "Now I can score this consistently. I don't have to guess what 'high quality' means."

#### Facilitation Notes

**Common Confusion Point:**
Choosing the right criteria - what should be measured?

**Clarification Approach:**
> "Think about why outputs fail. If emails get rejected because they're too long, 'length' is a criterion. If reports get edited for tone, 'tone appropriateness' is a criterion. Criteria come from real quality issues."

**Transition to Segment 3:**
> "You now have a rubric. But manually evaluating every output is tedious. What if AI could do the evaluation for you?"

---

### Segment 3: LLM-as-Judge Pattern (12 minutes)

**Learning Objective:** Use AI to evaluate AI outputs systematically

**Slides:** 10-13

#### Content Delivery

**Key Point 1: The Concept**
- Main message: Use a second AI call to evaluate the first AI's output
- Why it works: AI can apply rubrics consistently
- Key insight: The rubric makes this reliable

**Key Point 2: The Pattern**
- Main message: Evaluator role + Rubric + Content + Instructions
- Framework/Pattern: Show the complete prompt structure
- Practical application: High-stakes deliverables, systematic improvement

**Key Point 3: When to Use**
- Main message: Not every output - reserve for important deliverables
- Examples: Client-facing work, published content, templates in development

#### Demo Instructions

**Demo Duration:** 5 minutes

**Setup Required:**
- Sample AI-generated content (email or short document)
- Prepared quality rubric
- AI platform ready

**Demo Steps:**
1. Show the content to evaluate
2. Show the rubric being used
3. Construct the LLM-as-judge prompt
4. Run the evaluation
5. Walk through the scores and justifications

**Demo Talking Points:**
> "Watch - I'm going to have the AI evaluate this email against my rubric..."
> "See how it scores each criterion and provides specific justification? That's the power of structured evaluation."
> "Notice it even suggests specific improvements. This is actionable feedback."

#### Interactive Element

**Activity Type:** Quick reflection

**Activity Duration:** 1 minute

**Instructions:**
1. Ask: "What's one deliverable type where you'd use this? Something you create regularly that needs to be high quality?"
2. Take 2-3 answers

**Debrief Points:**
> "Great examples. Those are exactly where LLM-as-judge pays off."

---

### Segment 4: Comparison Gates + Close (8 minutes)

**Learning Objective:** Understand comparison gates technique and homework

**Slides:** 14-17

#### Content Delivery

**Key Point 1: Comparison Gates Concept**
- Main message: Give AI an example of "perfect" output and ask it to match
- Why it works: AI excels at pattern matching
- When to use: When you have a gold standard to reference

**Key Point 2: The Pattern**
- Main message: Reference document + Task + Match instructions
- Quick example: Show the prompt structure
- Caution: Reference must be high quality

#### Closing

**Homework Preview:**

**Key Actions:**
1. Overview all three exercises
2. Emphasize that rubric criteria must be specific
3. Note that Exercise 4.2 requires AI-generated content first

**Script:**
> "Your homework includes three exercises totaling about 60 minutes.
>
> Exercise 4.1 is creating a quality rubric - 25 minutes. Pick a deliverable you create often and build a full rubric.
> Exercise 4.2 is testing LLM-as-judge - 20 minutes. Generate content, then run it through your rubric.
> Exercise 4.3 is creating a comparison gate - 15 minutes. Find your best past work and build a reference-based prompt.
>
> Key requirement: Your rubric criteria must be specific. Not 'good quality' - specific descriptions of what each score looks like."

#### Next Week Preview

> "Next week we're covering GitHub collaboration and AI-assisted documentation. Your rubrics from this week become part of your documentation strategy. We're building toward the capstone where you'll need quality systems in place."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Isn't having AI evaluate AI just garbage in, garbage out?**
A: The rubric makes it work. Without a rubric, yes - the evaluation would be vague. With specific criteria and score descriptions, AI can apply them consistently. You're giving it a scoring guide, not asking for subjective judgment.

**Q: How often should I use LLM-as-judge?**
A: Reserve it for important deliverables. Not every chat message, but definitely for client-facing work, templates you're developing, anything that needs to be right. The cost is one extra AI call - use it when accuracy matters.

**Q: What if the AI gives itself a good score when the content is actually bad?**
A: This is why specific criteria matter. Vague criteria produce unreliable evaluation. Also, spot-check evaluations - run a few manually to calibrate trust.

### Technical Questions

**Q: Should I use the same AI for generating and evaluating?**
A: Using a different model or instance can provide a second perspective. But even the same AI with a clear evaluator role can work well. The key is the structured rubric, not the model difference.

**Q: How do I weight criteria in the score?**
A: Assign percentage weights based on importance. Calculate weighted average. Or keep it simple: unweighted average with a passing threshold (like 3.5 out of 5).

### Scope Questions

**Q: Will we automate this in Block 2?**
A: Yes - Block 2 introduces workflow automation. Quality gates can be built into automated pipelines. This manual practice prepares you to understand what's being automated.

**Q: How does this connect to the capstone?**
A: Quality rubrics are required capstone deliverables. You'll need at least 2 rubrics for different deliverable types. Start building them now.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| AI platform slow/down | Have backup screenshots of evaluation | Walk through conceptually |
| Evaluation too long | Stop generation early, summarize | Pre-prepared evaluation output |
| Unexpected scores | Use as teaching moment about calibration | Adjust rubric live |
| Demo content poor | Have backup content ready | Use participant suggestion |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Criteria too vague | "Quality" or "Good" without specifics | Show transformation to specific |
| Over-complicated rubrics | 10+ criteria, complex weighting | Simplify - start with 3-4 criteria |
| Skeptical of AI evaluation | "How can AI judge AI?" | Emphasize rubric makes it work |
| Missing connection to work | "When would I use this?" | Ask about their high-stakes deliverables |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Quality feels abstract | Struggling to define criteria | Use concrete examples from their work |
| Too much content | Running behind | Focus on LLM-as-judge, minimize comparison gates |
| Mixed understanding | Some get it, some don't | Pair discussion, peer explanation |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save any chat questions | For follow-up |
| Note demo effectiveness | Did evaluation produce good results? |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | ☐ |
| Answer pending questions about rubric design | ☐ |
| Send follow-up with rubric resources | ☐ |
| Document issues encountered for curriculum improvement | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions | ☐ |
| Check rubric quality (specific criteria?) | ☐ |
| Identify participants who need support | ☐ |
| Prepare any clarifications for Week 5 opening | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 4.1 | `quality-rubric-[type].md` | Participant's GitHub repo |
| 4.2 | `llm-judge-test.md` | Participant's GitHub repo |
| 4.3 | `comparison-gate-template.md` | Participant's GitHub repo |

### Progress Check Approach

**How to Verify Completion:**
- Check rubric has specific criteria (not vague terms)
- Verify LLM-as-judge test includes actual evaluation output
- Confirm comparison gate has real reference content

**Red flags indicating struggle:**
- Vague criteria like "good," "appropriate," "high quality"
- Missing evaluation output in Exercise 4.2
- Comparison gate without actual reference document

**Intervention Thresholds:**
- Vague rubric criteria: Provide specific feedback before Week 5
- Missing exercises: Reach out, these are capstone prerequisites
- Confusion about concepts: Offer office hours support

---

## Week-Specific Notes

### What Makes This Week Unique

- **Quality focus**: Shift from creation to evaluation
- **Meta-skill**: Using AI to evaluate AI
- **Capstone connection**: Rubrics are required deliverables
- **Scalability preview**: Manual now, automated in Block 2

### Dependencies

**Builds On:**
- Week 1-2: Prompting techniques (what we're evaluating)
- Week 3: `style.json` (can be referenced in rubrics)
- All previous: Content to evaluate

**Sets Up:**
- Week 5: Documentation uses rubrics for quality standards
- Week 6: Organization includes quality artifacts
- Week 7-8: Capstone requires quality rubrics

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Rubric criteria tend to be too vague initially | Emphasize specific descriptions, show transformations | Active |
| LLM-as-judge can be verbose | Include instruction for concise output | Active |
| Some don't have "gold standard" for comparison gate | Suggest creating one or using best recent work | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- Can participants distinguish vague vs. specific criteria?
- Do they understand when to use LLM-as-judge?
- Are they connecting quality systems to their real work?

**Observable behavior indicating understanding:**
- Nodding during transformation of vague to specific criteria
- Questions about their specific use cases
- Notes on rubric structure

**Observable behavior indicating confusion:**
- Difficulty articulating what makes criteria specific
- Questions about why this is necessary
- No connection to their deliverables

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 4.1: 3-5 criteria, all specific with score descriptions
- Exercise 4.2: Complete evaluation with scores and justification
- Exercise 4.3: Real reference content, not hypothetical

**Common Issues to Flag:**
- Criteria without score-level descriptions
- Evaluation that doesn't match rubric criteria
- Comparison gate without actual comparison

### Connecting to Capstone

**Capstone Relevance:**
This week's work contributes to the capstone by:
- Quality rubrics are required deliverables (2+ rubrics)
- LLM-as-judge pattern used in capstone evaluation
- Quality mindset applies to all capstone components

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Specific criteria make quality measurable - 'clear purpose in first sentence' not 'good quality'"
2. "LLM-as-judge works because the rubric provides structure - you're not asking for subjective opinion"
3. "Quality systems compound - every improvement raises the baseline"

### If You Only Have Time For One Thing

LLM-as-judge pattern. Rubrics can be learned from the guide, but the insight that AI can evaluate AI reliably with proper structure is the key breakthrough.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Quality rubric | "A grading guide teachers use - but for AI output" | When introducing rubrics |
| LLM-as-judge | "Having a colleague review your work using your criteria" | When explaining the pattern |
| Comparison gate | "A style guide with a perfect example attached" | When explaining the concept |
| Vague vs. specific | "Saying 'write well' vs. 'use active voice, 15-20 word sentences'" | When transforming criteria |

---

**Navigation:** [← Week 3 Instructor Guide](../week-3/instructor-guide.md) | **Week 4** | [Week 5 Instructor Guide →](../week-5/instructor-guide.md)
