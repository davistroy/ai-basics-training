# **POWERPOINT PRESENTATION: BLOCK 1 WEEK 4**
## **Quality Rubrics + Workflow Design**

**Block:** 1: AI Prompting Mastery
**Week Number:** 4
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Participants who completed Weeks 1-3 with style.json and multiple templates

**Week Learning Objectives:** By the end of this session, participants will:
1. Create quality rubrics with specific, measurable criteria
2. Apply the LLM-as-judge pattern to evaluate AI outputs
3. Design comparison gates using reference documents
4. Understand the quality improvement cycle

**Entry Criteria:**
- [ ] Week 3 exercises completed
- [ ] style.json created and tested
- [ ] GitHub basics understood

**Exit Criteria:**
- [ ] Understands rubric structure (criteria + score levels)
- [ ] Knows LLM-as-judge pattern
- [ ] Can identify when to use quality systems
- [ ] Has plan to create first quality rubric

**Presentation Structure:**
1. Opening & Recap (5 min) - Slides 1-3
2. Segment 1: The Quality Problem (8 min) - Slides 4-5
3. Segment 2: Creating Quality Rubrics (12 min) - Slides 6-9
4. Segment 3: LLM-as-Judge Pattern (12 min) - Slides 10-13
5. Segment 4: Comparison Gates + Close (8 min) - Slides 14-17

**Total Slides:** 17

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Block 1 Week 4: Quality Rubrics + Workflow Design

**Subtitle:** Systematic Quality for AI Outputs

**Content:**
- AI Practitioner Training Program
- Block 1: AI Prompting Mastery
- Week 4 of 8

**Graphic:** Clean title slide with blue color scheme (Block 1 theme).

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Week 4! We're at the halfway point of Block 1.

Over the past three weeks, you've built prompts, templates, and configuration files. Today we're adding quality systems - how to evaluate AI outputs systematically.

Here's the key insight: you can use AI to evaluate AI. And when you give it the right structure, it works remarkably well.

By the end of today, you'll know how to build quality rubrics and use the LLM-as-judge pattern."

[Transition: Click to next slide]

---

### SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-5 min | Opening | Week 3 Recap |
| 5-13 min | Segment 1 | The Quality Problem |
| 13-25 min | Segment 2 | Creating Quality Rubrics |
| 25-37 min | Segment 3 | LLM-as-Judge Pattern |
| 37-45 min | Segment 4 | Comparison Gates + Homework |

**Graphic:** Timeline with quality system icons

**SPEAKER NOTES:**

"Here's our agenda:

First, we'll look at the quality problem - why ad-hoc evaluation doesn't work.

Then we'll build quality rubrics - scoring guides that make evaluation consistent.

The big technique today is LLM-as-judge - using AI to evaluate AI outputs.

We'll close with comparison gates and your homework.

Let's start with a quick recap of Week 3."

[Transition]

---

### SLIDE 3: WEEK 3 RECAP

**Title:** Quick Recap: Your Infrastructure

**Content:**

**JSON Configuration:**
```json
{
  "tone": "professional but approachable",
  "preferences": {
    "use": ["active voice", "examples"],
    "avoid": ["jargon", "passive voice"]
  }
}
```

**GitHub Version Control:**
- Commits = saved snapshots
- History = change log
- Meaningful messages

**The Question:**
Your style.json defines how you want to sound. But how do you know if AI actually followed it?

**Graphic:** style.json flowing into question mark

**SPEAKER NOTES:**

"Last week you built infrastructure. JSON for configuration - your style.json captures preferences. GitHub for version control - tracking changes over time.

[Point to question]

But here's the question: Your style.json says 'professional but approachable.' After AI generates content, how do you know if it actually matched that?

Right now, it's subjective. 'This feels right' or 'This seems off.' That's the problem we're solving today."

[Transition: Click to Segment 1]

---

## SEGMENT 1: THE QUALITY PROBLEM
### Duration: 8 minutes | Slides 4-5

---

### SLIDE 4: THE CURRENT STATE

**Title:** The Problem: Subjective Quality

**Content:**

**Current Reality:**
- "This email looks good" - But what makes it good?
- "The tone seems off" - How do we define "right"?
- Different people, different judgments
- No consistent standard

**The Costs:**
- Manual review for everything (exhausting)
- Inconsistent quality across outputs
- No systematic improvement
- "Good enough" becomes the standard

**Graphic:** Multiple reviewers with different judgments on same content

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Let me ask you: How do you currently evaluate AI output quality?

If you're like most people, it's gut feel. 'This looks good.' 'This seems right.' 'I don't love the tone.'

[Point to current reality]

That's subjective evaluation. It varies by person, by mood, by day. Different people look at the same email and have different judgments.

[Point to costs]

The costs are real. You manually review everything - that's exhausting. Quality varies. There's no way to systematically improve. And 'good enough' becomes your standard.

We can do better."

[Transition]

---

### SLIDE 5: THE SOLUTION - QUALITY SYSTEMS

**Title:** The Solution: Measurable Quality

**Content:**

**The Insight:**
> What gets measured gets improved.

**Quality System Components:**

| Component | Purpose | We'll Cover |
|-----------|---------|-------------|
| **Rubrics** | Define what "good" means | Today |
| **LLM-as-Judge** | Automate evaluation | Today |
| **Comparison Gates** | Reference-based quality | Today |
| **Automated Workflows** | Quality at scale | Block 2 |

**Key Insight:**
AI can evaluate AI - when you give it the right structure.

**Graphic:** Quality system workflow diagram

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"The solution is quality systems. Structured, measurable evaluation.

[Point to insight]

What gets measured gets improved. If you can measure clarity, you can improve clarity. If you can measure tone match, you can improve tone match.

[Walk through components]

Today we're covering three components. Rubrics define what 'good' means with specific criteria. LLM-as-judge automates evaluation using those rubrics. Comparison gates use your best work as the standard.

In Block 2, this all gets automated. Learn it manually first so you understand what's being automated."

[Transition: Click to Segment 2]

---

## SEGMENT 2: CREATING QUALITY RUBRICS
### Duration: 12 minutes | Slides 6-9

---

### SLIDE 6: WHAT IS A RUBRIC

**Title:** Quality Rubrics: Making Quality Measurable

**Content:**

**Definition:**
A scoring guide with specific criteria and descriptions for each quality level.

**Structure:**
```markdown
# Criterion: Clarity

| Score | Description |
|-------|-------------|
| 5 | Purpose clear in first sentence |
| 4 | Purpose clear by end of first paragraph |
| 3 | Purpose eventually clear |
| 2 | Purpose unclear, requires inference |
| 1 | Reader cannot determine purpose |
```

**Key Insight:**
The descriptions at each level make it measurable. Not "good" or "bad" - specific behaviors.

**Graphic:** 5-point scale with specific descriptions

**SPEAKER NOTES:**

"A rubric is a scoring guide. Teachers use them, peer reviewers use them, and now you'll use them for AI.

[Walk through structure]

Each criterion gets a 5-point scale. But here's what matters - specific descriptions at each level.

Look at this clarity criterion. '5' isn't 'very clear.' It's 'Purpose clear in first sentence.' That's measurable. You can look at an email and check: is the purpose in the first sentence?

[Point to key insight]

The descriptions make it work. Without them, you're back to subjective judgment."

[Transition]

---

### SLIDE 7: RUBRIC STRUCTURE

**Title:** Building a Complete Rubric

**Content:**

**Full Rubric Template:**
```markdown
# Quality Rubric: [Deliverable Type]

## Overview
- Purpose: What this evaluates
- Passing score: 3.5/5 average

## Criterion 1: Clarity (30%)
| Score | Description |
|-------|-------------|
| 5 | [Specific observable behavior] |
...

## Criterion 2: Tone (25%)
| Score | Description |
|-------|-------------|
| 5 | [Specific observable behavior] |
...

## Scoring
- Calculate weighted average
- Pass if >= 3.5
```

**Graphic:** Rubric structure diagram with sections highlighted

**SPEAKER NOTES:**

"Here's the full structure.

[Walk through sections]

Overview - what does this rubric evaluate? What's the passing threshold?

Then your criteria - each with a weight. Clarity might be 30% of the score, tone 25%, and so on.

Each criterion has the 5-level scale with specific descriptions.

At the bottom, scoring instructions. Usually a weighted average with a pass/fail threshold.

You'll build one of these in Exercise 4.1."

[Transition]

---

### SLIDE 8: GOOD VS. BAD CRITERIA

**Title:** Specific vs. Vague Criteria

**Content:**

**Bad Criterion (Vague):**
```markdown
## Quality
| Score | Description |
|-------|-------------|
| 5 | High quality |
| 3 | Medium quality |
| 1 | Low quality |
```
**Problem:** What does "high quality" mean? Useless.

**Good Criterion (Specific):**
```markdown
## Clarity
| Score | Description |
|-------|-------------|
| 5 | Purpose stated in first sentence |
| 3 | Purpose clear by end of email |
| 1 | Reader cannot determine purpose |
```
**Why it works:** Observable. Measurable. Consistent.

**Graphic:** Side-by-side comparison with X and checkmark

**SPEAKER NOTES:**

"This is the most important slide in today's session.

[Point to bad criterion]

This is useless. 'High quality' tells you nothing. How would you score? It's completely subjective.

[Point to good criterion]

This works. 'Purpose stated in first sentence' - I can check that. 'Reader cannot determine purpose' - I can evaluate that.

The transformation is from adjectives to behaviors. Not 'clear' - 'purpose stated in first sentence.' Not 'appropriate' - 'matches formal/informal context specified.'

When you write criteria, ask: Can I point to specific evidence for this score?"

[Transition]

---

### SLIDE 9: COMMON CRITERIA EXAMPLES

**Title:** Criteria Ideas by Deliverable Type

**Content:**

**For Emails:**
- Clarity (purpose evident)
- Tone (matches relationship/context)
- Actionability (clear next steps)
- Conciseness (no unnecessary words)

**For Reports:**
- Structure (logical organization)
- Evidence (claims supported)
- Executive summary (captures key points)
- Recommendations (specific, actionable)

**For Documentation:**
- Completeness (all topics covered)
- Accuracy (technically correct)
- Readability (appropriate for audience)
- Examples (concepts illustrated)

**Graphic:** Three columns with icons for each deliverable type

**SPEAKER NOTES:**

"Here are criteria ideas organized by deliverable type.

[Walk through examples]

For emails - clarity, tone, actionability, conciseness. These are the things that make emails succeed or fail.

For reports - structure, evidence, executive summary quality, recommendations. These are what executives actually evaluate.

For documentation - completeness, accuracy, readability, examples.

In Exercise 4.1, you'll choose a deliverable type and pick 3-5 criteria that matter for YOUR work.

Now, let's talk about how to automate this evaluation."

[Transition: Click to Segment 3]

---

## SEGMENT 3: LLM-AS-JUDGE PATTERN
### Duration: 12 minutes | Slides 10-13

---

### SLIDE 10: THE LLM-AS-JUDGE CONCEPT

**Title:** LLM-as-Judge: AI Evaluating AI

**Content:**

**The Pattern:**
Use a second AI call to evaluate the first AI's output.

```
┌──────────────────┐
│  AI generates    │
│  content         │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  AI evaluates    │
│  using rubric    │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│  Scores +        │
│  improvements    │
└──────────────────┘
```

**Why It Works:**
The rubric provides structure. AI isn't giving subjective opinions - it's applying your criteria consistently.

**Graphic:** Two AI icons with arrow between, rubric as the bridge

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"Here's the key technique: LLM-as-judge.

[Walk through pattern]

First AI call generates content. Second AI call evaluates it using your rubric.

[Point to 'Why It Works']

I know what you're thinking - 'How can AI judge AI? Isn't that just garbage in, garbage out?'

The rubric makes it work. You're not asking for subjective opinion. You're giving AI specific criteria with score descriptions and asking it to apply them.

It's like giving a colleague your evaluation checklist. They apply your criteria, not their own judgment.

Let me show you the prompt pattern."

[Transition]

---

### SLIDE 11: THE EVALUATION PROMPT

**Title:** The LLM-as-Judge Prompt Pattern

**Content:**

```markdown
You are a quality evaluator. Assess this [type] against the rubric below.

## Rubric
[Paste your rubric - criteria + score descriptions]

## Content to Evaluate
---
[Paste the AI-generated content]
---

## Instructions
1. Score each criterion (1-5)
2. Quote specific evidence for each score
3. Calculate overall score
4. List specific improvements needed

Output format: Clear headers for each section.
```

**Key Elements:**
- Evaluator role
- Complete rubric
- Content clearly marked
- Specific instructions

**Graphic:** Prompt structure with callouts

**SPEAKER NOTES:**

"Here's the prompt pattern.

[Walk through elements]

Start with an evaluator role - 'You are a quality evaluator.'

Include your complete rubric - criteria and score descriptions. The more specific your rubric, the better the evaluation.

Mark the content clearly - I use code blocks or horizontal rules.

Give specific instructions. Score each criterion. Quote evidence. Calculate overall score. List improvements.

The output format instruction helps you get consistent, parseable results."

[Transition]

---

### SLIDE 12: LIVE DEMO - LLM-AS-JUDGE

**Title:** Live Demo: LLM-as-Judge in Action

**Content:**

**We'll Evaluate:**
An AI-generated email against an email quality rubric

**Watch For:**
1. How scores are justified
2. Specific evidence cited
3. Actionable improvements suggested
4. Overall pass/fail determination

**Graphic:** Demo placeholder

**SPEAKER NOTES:**

"[DEMO - Show, don't tell]"

"Let me show you this in action.

[Set up demo]

I have an AI-generated email here, and I'm going to evaluate it against my email rubric.

[Construct prompt]

'You are a quality evaluator...' - adding my rubric, my content, my instructions.

[Run evaluation]

[Walk through output]

See the scores? Each criterion gets a number. And look - specific evidence. 'The purpose is stated in sentence two, not sentence one, so 4 not 5.'

[Point out improvements]

And here are the improvements. Not vague - specific. 'Move the meeting request to the first sentence.'

This is actionable feedback. You can use this to refine the content."

[Transition]

---

### SLIDE 13: WHEN TO USE LLM-AS-JUDGE

**Title:** When to Use LLM-as-Judge

**Content:**

**Use For:**
- High-stakes deliverables (client work)
- Template development and refinement
- Systematic quality improvement
- Before publishing or sending externally

**Don't Use For:**
- Quick, low-stakes messages
- Conversational exchanges
- When manual review is faster
- Every single output (overkill)

**The Balance:**
The cost is one extra AI call. Use it when accuracy matters.

**Graphic:** Balance scale showing when to use vs. when not to

**SPEAKER NOTES:**

"LLM-as-judge isn't for everything.

[Point to 'Use For']

Use it for high-stakes deliverables. Client emails. Published reports. Templates you're developing - test them against your rubric.

[Point to 'Don't Use For']

Don't use it for quick messages, casual conversations, low-stakes outputs. The extra step isn't worth it.

[Point to balance]

The cost is one additional AI call. Use it when getting it right matters. Not for everything, but for the important things.

In Exercise 4.2, you'll test this with your own rubric."

[Transition: Click to Segment 4]

---

## SEGMENT 4: COMPARISON GATES + CLOSE
### Duration: 8 minutes | Slides 14-17

---

### SLIDE 14: COMPARISON GATES

**Title:** Comparison Gates: Your Best Work as Standard

**Content:**

**The Concept:**
Give AI an example of "perfect" output and ask it to match.

**The Pattern:**
```markdown
# Reference Document
[Your gold standard example]

# Task
Create [deliverable] that matches the style, structure,
and quality of the reference document.

# Requirements
- Match tone exactly
- Use similar structure
- Follow same patterns
```

**Why It Works:**
AI excels at pattern matching. Your best work becomes reproducible.

**Graphic:** Reference document connecting to new output with "match" arrows

**SPEAKER NOTES:**

"One more technique: comparison gates.

Instead of a rubric with criteria, you provide a perfect example. 'Here's my best email ever. Match this.'

[Walk through pattern]

Give the reference document. State the task. List what must match - tone, structure, patterns.

Why does this work? AI is excellent at pattern matching. It can identify style, structure, pacing, and replicate them.

The catch: your reference must be high quality. If you provide a mediocre example, you get mediocre matches.

In Exercise 4.3, you'll find your best past work and build a comparison gate around it."

[Transition]

---

### SLIDE 15: QUALITY IMPROVEMENT CYCLE

**Title:** The Quality Improvement Cycle

**Content:**

```
    ┌─────────────────┐
    │    Generate     │
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │    Evaluate     │
    │   (LLM-judge)   │
    └────────┬────────┘
             │
    ┌────────┴────────┐
    │   Pass?         │
    ├─► YES → Use it  │
    │                 │
    └─► NO → Refine   │
              │
              └─→ Generate again
```

**The Insight:**
This manual cycle becomes automated in Block 2. Learn it now, automate it later.

**Graphic:** Cycle diagram with icons

**SPEAKER NOTES:**

"Here's how it all comes together.

[Walk through cycle]

Generate content. Evaluate against your rubric. If it passes, use it. If it doesn't, refine and regenerate.

This is manual right now. You're running the evaluation, reading the results, making decisions.

In Block 2, this becomes automated. Workflows that generate, evaluate, and route - all without manual intervention.

Learning the manual process first helps you understand what's being automated."

[Transition]

---

### SLIDE 16: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 4.1: Quality Rubric | 25 min | `quality-rubric-[type].md` | Rubric creation |
| Exercise 4.2: LLM-as-Judge Test | 20 min | `llm-judge-test.md` | Evaluation pattern |
| Exercise 4.3: Comparison Gate | 15 min | `comparison-gate-template.md` | Reference-based quality |
| **Total** | **60 min** | | |

**Key Requirements:**
- Rubric criteria must be specific (not vague)
- Exercise 4.2 requires AI-generated content first
- Exercise 4.3 needs real reference content (your best work)

**Graphic:** Three exercise cards with icons

**SPEAKER NOTES:**

"Three exercises this week.

Exercise 4.1 is creating a quality rubric - 25 minutes. Choose a deliverable type you create often. Build a rubric with 3-5 specific criteria.

Exercise 4.2 is testing LLM-as-judge - 20 minutes. Generate content, then run it through your rubric. Compare AI evaluation to your own judgment.

Exercise 4.3 is creating a comparison gate - 15 minutes. Find your best past work. Build a reference-based prompt around it.

[Point to key requirements]

Important: Your rubric criteria must be specific. Not 'good quality' - 'purpose clear in first sentence.' That's the key to making this work."

[Transition]

---

### SLIDE 17: NEXT WEEK PREVIEW

**Title:** Next Week: GitHub Collaboration & Documentation

**Content:**

**Preview:**
Pull request workflow, AI-assisted documentation, repository organization.

**What to Complete Before Then:**
- [ ] Exercise 4.1: Quality Rubric (with specific criteria!)
- [ ] Exercise 4.2: LLM-as-Judge Test
- [ ] Exercise 4.3: Comparison Gate Template

**Key Preparation:**
- Use your rubric to evaluate 3-5 AI outputs this week
- Note where AI consistently scores low

**Connection:**
Your quality rubrics become part of your template documentation.

**Graphic:** Preview of Week 5 topics

**SPEAKER NOTES:**

"Next week we're covering GitHub collaboration and documentation.

You'll learn the pull request workflow for collaborating safely. AI-assisted documentation for your templates. Repository organization for scaling your library.

[Point to key preparation]

Key preparation: actually use your rubric this week. Evaluate 3-5 AI outputs. Notice patterns. Where does AI consistently score low? Those are your improvement opportunities.

[Point to connection]

Your quality rubrics become part of your template documentation. When you document a template for someone else to use, you include how to evaluate quality.

Questions before we wrap?

[Take questions]

Great session. You now have quality systems - rubrics for definition, LLM-as-judge for automation, comparison gates for consistency.

See you next week!"

---

## Appendix: Slide Type Reference

| Slide Type | Purpose | Used In |
|------------|---------|---------|
| Title | Opens presentation | Slide 1 |
| Overview | Sets expectations | Slide 2 |
| Recap | Reviews prior learning | Slide 3 |
| Problem/Hook | Creates tension | Slide 4 |
| Solution | Introduces approach | Slide 5 |
| Concept | Teaches structure | Slides 6-7 |
| Comparison | Good vs. bad | Slide 8 |
| Examples | Ideas/options | Slide 9 |
| Pattern | Shows technique | Slides 10-11 |
| Live Demo | Shows in action | Slide 12 |
| When to Use | Application guidance | Slide 13 |
| Concept | Additional technique | Slide 14 |
| Cycle | Process overview | Slide 15 |
| Homework | Assignments | Slide 16 |
| Next Week | Creates continuity | Slide 17 |

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
