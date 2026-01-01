# **BLOCK 1 WEEK 4: Quality Rubrics + Workflow Design**

**Block:** 1: AI Prompting Mastery
**Week:** 4 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** [← Previous Week](../week-3/participant-guide.md) | **Week 4** | [Next Week →](../week-5/participant-guide.md)

**In This Guide:**
- [Learning Objectives](#learning-objectives)
- [Key Concepts](#key-concepts)
- [Workshop Recap](#workshop-recap)
- [Self-Paced Exercises](#self-paced-exercises)
- [Templates & Resources](#templates--resources)
- [Self-Assessment](#self-assessment)
- [Getting Help](#getting-help)

---

## Learning Objectives

By the end of this week, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Create quality rubrics with specific, measurable criteria | Exercise 4.1 |
| 2 | Apply the LLM-as-judge pattern to evaluate AI outputs | Exercise 4.2 |
| 3 | Design comparison gates using reference documents | Exercise 4.3 |
| 4 | Understand how quality systems enable systematic improvement | Workshop + All Exercises |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Week 3 exercises (json-practice.json, `style.json`, GitHub activity)
- [ ] `style.json` created and tested with at least one prompt
- [ ] Comfortable with JSON syntax and validation
- [ ] At least 3-4 templates or prompts in your library

**Not ready?** Complete the [Week 3 exercises](../week-3/participant-guide.md) first - your `style.json` becomes part of quality evaluation.

---

## Key Concepts

### Concept 1: The Quality Problem

**Definition:**
Without systematic evaluation, AI output quality is subjective, inconsistent, and doesn't improve over time.

**Why It Matters:**
"Good enough" becomes the standard. Manual review is exhausting. There's no way to identify patterns or systematically improve.

**Core Principle:**
> What gets measured gets improved.

**Example of the Problem:**
- "This email looks good" - But what makes it good?
- "The tone seems off" - How do we define "right" tone?
- Different people, different judgments, inconsistent quality

**The Solution:**
Quality rubrics with specific criteria that remove subjectivity.

---

### Concept 2: Quality Rubrics

**Definition:**
A scoring guide with specific criteria and descriptions for each quality level, enabling consistent evaluation.

**Why It Matters:**
Rubrics make quality measurable. Instead of "good" vs. "bad," you have specific scores with clear justification.

**The Pattern:**
```markdown
# Quality Rubric: [Deliverable Type]

## Criterion 1: [Name]
**Weight:** [X%]

| Score | Description |
|-------|-------------|
| 5 | Excellent: [Specific observable behavior] |
| 4 | Good: [Specific observable behavior] |
| 3 | Acceptable: [Specific observable behavior] |
| 2 | Needs improvement: [Specific observable behavior] |
| 1 | Unacceptable: [Specific observable behavior] |
```

**Key Insight:**
The descriptions at each level make it measurable. "Purpose clear in first sentence" (5) is specific. "Good quality" (5) is useless.

---

### Concept 3: LLM-as-Judge Pattern

**Definition:**
Using a second AI call to evaluate the first AI's output against a rubric.

**Why It Matters:**
Manual evaluation doesn't scale. AI can apply rubrics consistently across many outputs.

**The Pattern:**
```markdown
You are a quality evaluator. Assess this [deliverable type] against the rubric below.

## Rubric
[Paste your rubric]

## Content to Evaluate
[Paste the AI-generated content]

## Instructions
1. Score each criterion (1-5)
2. Provide brief justification for each score
3. Calculate overall score
4. List specific improvements needed
```

**When to Use:**
- High-stakes deliverables
- Template development and refinement
- Systematic improvement efforts
- Before sending to clients/stakeholders

**When NOT to Use:**
- Quick, low-stakes outputs
- Conversational exchanges
- When manual review is faster

---

### Concept 4: Comparison Gates

**Definition:**
Providing AI with an example of "perfect" output and asking it to match that quality and style.

**Why It Matters:**
Your best work becomes the standard. AI excels at pattern matching.

**The Pattern:**
```markdown
# Reference Document
[Paste example of ideal output]

# Task
Create [deliverable] that matches the style, structure, and quality of the reference document.

# Specific Requirements
- Match the tone exactly
- Use similar sentence structures
- Follow the same organizational pattern
```

**Key Insight:**
The reference must be high quality. Your best past work is your quality standard.

---

### Concept 5: The Quality Improvement Cycle

**Definition:**
A systematic process for improving AI outputs over time.

**Visual Reference:**
```
    ┌─────────────────┐
    │    Generate     │
    │    (Create)     │
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
    ├─► YES → Use     │
    │                 │
    └─► NO ↓          │
    ┌─────────────────┐
    │     Refine      │
    │   (Improve)     │
    └────────┬────────┘
             │
             └─→ Back to Generate
```

**Key Insight:**
This manual process becomes automated in Block 2. Learning it manually first helps you understand what's being automated.

---

### Quick Reference: Rubric Design Principles

| Principle | Good Example | Bad Example |
|-----------|--------------|-------------|
| Specific | "Purpose stated in first sentence" | "Clear" |
| Observable | "Contains 3+ concrete examples" | "Well-supported" |
| Measurable | "Under 200 words" | "Appropriate length" |
| Relevant | Matches actual quality needs | Generic criteria |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Building quality systems - rubrics for evaluation, LLM-as-judge for scaling, and comparison gates for consistency.

**Key Points from Each Segment:**

**Segment 1: The Quality Problem**
- Without systems, quality is subjective and inconsistent
- Manual review doesn't scale
- "Good enough" becomes the standard
- Key takeaway: What gets measured gets improved

**Segment 2: Creating Quality Rubrics**
- Rubrics have criteria with specific score descriptions
- Specific means observable, not vague
- Transform "good quality" to "purpose clear in first sentence"
- Key takeaway: Descriptions at each level make quality measurable

**Segment 3: LLM-as-Judge Pattern**
- AI can evaluate AI when given a structured rubric
- Pattern: Evaluator role + Rubric + Content + Instructions
- Use for high-stakes deliverables, template development
- Key takeaway: The rubric makes this reliable, not the AI alone

**Segment 4: Comparison Gates**
- Provide a "perfect" example as reference
- AI matches the style and structure
- Your best work becomes the standard
- Key takeaway: Pattern matching is an AI strength

### Demo Recap

**What Was Demonstrated:**
LLM-as-judge evaluation of a sample email against a quality rubric.

**Key Steps:**
1. Showed the content to evaluate
2. Showed the rubric being applied
3. Constructed the evaluation prompt
4. Ran the evaluation
5. Walked through scores and justifications

**Result:**
The AI provided specific scores for each criterion with justification and improvement suggestions.

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 4.1 | 25 min | `quality-rubric-[type].md` | Rubric creation |
| 4.2 | 20 min | `llm-judge-test.md` | LLM-as-judge pattern |
| 4.3 | 15 min | `comparison-gate-template.md` | Comparison gates |

---

### Exercise 4.1: Create a Quality Rubric

**Duration:** 25 minutes

**Purpose:**
Build your first quality evaluation tool - a rubric with specific, measurable criteria for a deliverable type you create often.

**You Will Create:**
A complete quality rubric with 3-5 criteria, each with descriptions for all five score levels.

---

#### Instructions

**Step 1: Choose a deliverable type**
Pick something you create regularly:
- Emails (client, internal, follow-up)
- Reports (status, analysis, summary)
- Meeting summaries or notes
- Social media posts
- Technical documentation
- Proposals or pitches

**Step 2: Identify what matters**
Think about:
- When this deliverable fails, why does it fail?
- What feedback do you typically receive?
- What makes your best work different from average work?

**Step 3: Define 3-5 criteria**
For each criterion:
- Name it clearly (Clarity, Tone, Completeness, etc.)
- Decide its weight (how important is it?)
- Write descriptions for each score level (1-5)

**Step 4: Use this template**

```markdown
# Quality Rubric: [Deliverable Type]

## Overview
- **Purpose:** [What this rubric evaluates]
- **Passing score:** [Minimum average score, e.g., 3.5/5]
- **When to use:** [Context for using this rubric]

## Criteria

### Criterion 1: [Name]
**Weight:** [X%]
**What it measures:** [Brief description]

| Score | Description | Example |
|-------|-------------|---------|
| 5 | Excellent: [Specific, observable behavior] | [Concrete example] |
| 4 | Good: [Specific behavior] | [Example] |
| 3 | Acceptable: [Specific behavior] | [Example] |
| 2 | Needs improvement: [Specific behavior] | [Example] |
| 1 | Unacceptable: [Specific behavior] | [Example] |

### Criterion 2: [Name]
**Weight:** [X%]
**What it measures:** [Brief description]

| Score | Description | Example |
|-------|-------------|---------|
| 5 | [Description] | [Example] |
| 4 | [Description] | [Example] |
| 3 | [Description] | [Example] |
| 2 | [Description] | [Example] |
| 1 | [Description] | [Example] |

[Repeat for 3-5 total criteria]

## Scoring

### Calculation
- Calculate weighted average of all criteria
- Pass threshold: [X or higher]

### Score Interpretation
- 4.5-5.0: Excellent - ready for use
- 3.5-4.4: Good - minor refinements recommended
- 2.5-3.4: Needs work - significant improvements required
- Below 2.5: Unacceptable - regenerate

```

**Step 5: Review Your Criteria**
For each criterion, ask:
- [ ] Is this specific? (Not vague like "good" or "appropriate")
- [ ] Is this observable? (Can you point to evidence?)
- [ ] Does the 5-level scale make sense? (Clear progression)

---

#### Deliverable Specification

**File Name:** `quality-rubric-[type].md` (e.g., `quality-rubric-email.md`)

**Location:** Upload to your GitHub repository (suggest `/rubrics` folder)

**Format Requirements:**
- Markdown with tables
- 3-5 criteria minimum
- All five score levels described for each criterion

**Quality Criteria:**
- [ ] All criteria are specific (no vague terms)
- [ ] Each score level has a distinct description
- [ ] Examples provided where helpful
- [ ] Passing threshold defined

---

#### Example

**Scenario:** Quality rubric for professional emails

```markdown
# Quality Rubric: Professional Email

## Overview
- **Purpose:** Evaluate AI-generated professional emails
- **Passing score:** 3.5/5 average
- **When to use:** Before sending client or stakeholder emails

## Criteria

### Criterion 1: Clarity
**Weight:** 30%
**What it measures:** How quickly the reader understands the email's purpose

| Score | Description | Example |
|-------|-------------|---------|
| 5 | Purpose clear in first sentence, no ambiguity | "I'm writing to confirm our meeting on Tuesday at 2pm." |
| 4 | Purpose clear by end of first paragraph | Purpose emerges within first 2-3 sentences |
| 3 | Purpose eventually clear, some re-reading needed | Reader understands after full read |
| 2 | Purpose unclear, requires inference | Reader must guess the intent |
| 1 | Reader cannot determine email purpose | Completely ambiguous or contradictory |

### Criterion 2: Tone Appropriateness
**Weight:** 25%
**What it measures:** Match between tone and context/relationship

| Score | Description | Example |
|-------|-------------|---------|
| 5 | Perfect match to context and relationship | Formal for new client, warm for long-term partner |
| 4 | Appropriate with minor adjustments possible | Slightly more/less formal than ideal |
| 3 | Generally appropriate, some inconsistency | Mix of formal and casual that feels awkward |
| 2 | Noticeably off for context | Too casual for formal situation or vice versa |
| 1 | Inappropriate tone for situation | Offensive, dismissive, or wildly mismatched |

### Criterion 3: Actionability
**Weight:** 25%
**What it measures:** Clarity of next steps and calls to action

| Score | Description | Example |
|-------|-------------|---------|
| 5 | Next steps crystal clear, deadlines explicit | "Please confirm by Friday 5pm" |
| 4 | Next steps clear, timing understood | "Let me know your thoughts this week" |
| 3 | Action implied but not explicit | Reader can infer what's expected |
| 2 | Unclear what reader should do | Vague or multiple possible interpretations |
| 1 | No call to action when one is needed | Email ends without direction |

### Criterion 4: Conciseness
**Weight:** 20%
**What it measures:** Efficiency of communication

| Score | Description | Example |
|-------|-------------|---------|
| 5 | Every sentence adds value, no filler | Tight, purposeful writing |
| 4 | Mostly efficient, minor trimming possible | One or two unnecessary phrases |
| 3 | Some redundancy or padding | Repeats points, unnecessary context |
| 2 | Significant bloat | Could be half the length |
| 1 | Extremely wordy, buries key points | Wall of text, hard to parse |
```

---

### Exercise 4.2: LLM-as-Judge Test

**Duration:** 20 minutes

**Purpose:**
Test the LLM-as-judge pattern by evaluating AI-generated content against your rubric.

**You Will Create:**
A document showing the content, the evaluation, and your comparison to manual assessment.

---

#### Instructions

**Step 1: Generate content to evaluate**
Use one of your templates or prompts to generate a deliverable matching your rubric type.

**Step 2: Create the evaluation prompt**

```markdown
You are a quality evaluator assessing a [deliverable type].

## Quality Rubric
[Paste your rubric from Exercise 4.1]

## Content to Evaluate
---
[Paste the AI-generated content]
---

## Evaluation Instructions
For each criterion:
1. Assign a score (1-5)
2. Quote specific text from the content supporting your score
3. Suggest one specific improvement

Then provide:
- Overall score (weighted average)
- Pass/Fail determination
- Top 3 actionable improvements

Format your response with clear headers for each section.
```

**Step 3: Run the evaluation**
Submit the evaluation prompt to your AI platform.

**Step 4: Compare to your judgment**
Manually evaluate the same content. Do you agree with the AI's scores?

**Step 5: Document everything**

---

#### Deliverable Specification

**File Name:** `llm-judge-test.md`

**Location:** Upload to your GitHub repository

**Format:**
```markdown
# LLM-as-Judge Test

## Content Evaluated
[Type of content and brief description]

### The Content
```
[Paste the actual content that was evaluated]
```

## Evaluation Prompt Used
```
[Paste your complete evaluation prompt]
```

## AI Evaluation Results
[Paste the AI's evaluation output]

## My Manual Evaluation

| Criterion | AI Score | My Score | Agreement? |
|-----------|----------|----------|------------|
| [Criterion 1] | [X] | [X] | Yes/No |
| [Criterion 2] | [X] | [X] | Yes/No |
| [Criterion 3] | [X] | [X] | Yes/No |

## Analysis
- **Where AI agreed with me:** [Notes]
- **Where AI disagreed:** [Notes and why]
- **Was the AI evaluation useful?** [Assessment]
- **What would I change about the rubric?** [Refinements]
```

**Quality Criteria:**
- [ ] Complete evaluation output included
- [ ] Manual evaluation comparison
- [ ] Thoughtful analysis of agreement/disagreement
- [ ] Rubric refinement ideas if applicable

---

### Exercise 4.3: Comparison Gate Prompt

**Duration:** 15 minutes

**Purpose:**
Create a reference-based quality prompt using your own best work as the standard.

**You Will Create:**
A comparison gate template with real reference content.

---

#### Instructions

**Step 1: Find or create a "gold standard"**
Identify a piece of your best work:
- An email you're proud of
- A report that got great feedback
- Any deliverable that represents your best

If you don't have one, create one now - write your ideal version of a common deliverable.

**Step 2: Analyze the reference**
Identify what makes it good:
- Tone characteristics
- Structure pattern
- Length and pacing
- Notable stylistic elements

**Step 3: Create the comparison gate prompt**

```markdown
# Style Reference
The following is an example of excellent [deliverable type] that represents my preferred style:

---
[Paste your gold standard example]
---

# Style Analysis
Key characteristics of this reference:
- **Tone:** [Describe]
- **Structure:** [Describe]
- **Length:** [Describe]
- **Notable patterns:** [List 3-5]

# Task
Create a new [deliverable type] that matches this style exactly.

# Requirements
[Your specific request details]

# Quality Check
After generating, verify:
- [ ] Tone matches reference
- [ ] Structure follows same pattern
- [ ] Length is comparable
- [ ] Key stylistic elements present
```

**Step 4: Test the prompt**
Use the comparison gate with a real request. Evaluate: did the output match your reference style?

---

#### Deliverable Specification

**File Name:** `comparison-gate-template.md`

**Location:** Upload to your GitHub repository

**Format Requirements:**
- Real reference content (not placeholder)
- Style analysis completed
- Prompt structure ready to use
- Test results included

**Quality Criteria:**
- [ ] Reference is actual quality content
- [ ] Style analysis is specific
- [ ] Template is ready for reuse
- [ ] Test results document effectiveness

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| Quality Rubric Template | Create evaluation rubrics | Below |
| LLM-as-Judge Prompt | Evaluate content | Below |
| Comparison Gate Template | Reference-based quality | Below |

---

### Template: LLM-as-Judge Prompt

```markdown
You are a quality evaluator. Assess the following [deliverable type] against the rubric below.

## Quality Rubric

### Criterion 1: [Name] (Weight: [X]%)
| Score | Description |
|-------|-------------|
| 5 | [Description] |
| 4 | [Description] |
| 3 | [Description] |
| 2 | [Description] |
| 1 | [Description] |

[Repeat for each criterion]

## Content to Evaluate

---
[Paste content here]
---

## Evaluation Instructions

For each criterion:
1. Assign a score (1-5)
2. Quote specific evidence from the content
3. Provide one actionable improvement suggestion

Then provide:
- **Overall Score:** Weighted average
- **Pass/Fail:** Pass if average >= 3.5
- **Top 3 Improvements:** Most impactful changes needed

Format with clear headers. Be specific and cite evidence.
```

---

### Template: Comparison Gate

```markdown
# Reference Document

The following is an example of excellent [deliverable type] that represents my preferred style and quality standard:

---
[Your gold standard content here]
---

# Style Elements to Match

From the reference above, match these specific elements:

| Element | Characteristic | Evidence from Reference |
|---------|---------------|------------------------|
| Tone | [Describe] | [Quote or describe] |
| Structure | [Pattern] | [How it's organized] |
| Length | [Approximate] | [Word/paragraph count] |
| Opening | [How it starts] | [Quote opening] |
| Closing | [How it ends] | [Quote closing] |

# Your Task

Create a [deliverable type] about [topic/context] that:
- Matches the tone exactly
- Follows the same structural pattern
- Uses similar sentence lengths and rhythm
- Applies the same formatting conventions

# Context for This Request

[Your specific requirements]

# Self-Check

Before finalizing, verify:
- [ ] Tone matches reference
- [ ] Structure follows same pattern
- [ ] Opening uses similar approach
- [ ] Length is comparable
- [ ] Formatting is consistent
```

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Rubric Design Principles | Article | [cultofpedagogy.com](https://www.cultofpedagogy.com/rubric-design/) | Rubric best practices |
| LLM-as-Judge Research | Paper | [arxiv.org](https://arxiv.org/abs/2306.05685) | Deep dive on technique |
| Anthropic Constitutional AI | Research | [anthropic.com](https://www.anthropic.com/research/constitutional-ai) | How AI self-evaluation works |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Create rubrics with specific criteria | Exercise 4.1 has measurable descriptions | ☐ |
| 2 | Apply LLM-as-judge pattern | Exercise 4.2 shows working evaluation | ☐ |
| 3 | Design comparison gates | Exercise 4.3 uses real reference content | ☐ |
| 4 | Understand quality improvement cycle | Can explain when to use each technique | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 4.1 output | `quality-rubric-[type].md` | GitHub repo | ☐ |
| Exercise 4.2 output | `llm-judge-test.md` | GitHub repo | ☐ |
| Exercise 4.3 output | `comparison-gate-template.md` | GitHub repo | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** Did the LLM-as-judge concept make sense immediately, or did it take practice?

2. **What's still fuzzy?** Are you unclear about when to use rubrics vs. comparison gates?

3. **How will you apply this?** Which deliverables in your work would benefit from systematic quality evaluation?

4. **What surprised you?** How did the AI's evaluation compare to your manual assessment?

---

## Getting Help

### Quick Answers
- **Rubric criteria too vague?** Ask "Can I point to specific evidence for this score?"
- **LLM evaluation unreliable?** Check that criteria descriptions are specific

### Common Questions This Week

**Q: My rubric criteria feel vague. How do I make them specific?**
A: Replace adjectives with observable behaviors. Instead of "clear," use "purpose stated in first sentence." Instead of "appropriate tone," use "matches formal/informal context as specified."

**Q: The AI gave different scores than I would. Which is right?**
A: Neither is objectively "right" - this is about calibration. If you consistently disagree with AI scores, refine your criteria to better capture what you're looking for.

**Q: When should I use a rubric vs. a comparison gate?**
A: Use rubrics for systematic evaluation against criteria. Use comparison gates when you have a perfect example and want to match its style. They can be combined.

### When to Ask for Help

- **Before asking:** Review your criteria for specificity
- **Good to ask:** "My rubric has [criterion]. Here's the description: [description]. Does this seem specific enough?"
- **Include:** Your actual rubric text

---

## Looking Ahead

### Next Week Preview: Week 5 - GitHub Collaboration & Documentation

**Focus:**
Pull request workflow, AI-assisted documentation, repository organization.

**How It Builds on This Week:**
Your quality rubrics become part of your documentation. You'll document templates with their associated quality criteria.

**To Prepare:**
- [ ] Complete all Week 4 exercises
- [ ] Use your rubric to evaluate 3-5 AI outputs this week
- [ ] Note: Where does AI consistently score low? (This reveals areas to improve)
- [ ] Think about: How would you document a template for someone else to use?

---

## Glossary

| Term | Definition |
|------|------------|
| **Quality Rubric** | Scoring guide with specific criteria and descriptions for each quality level |
| **Criterion** | A specific aspect of quality being evaluated (clarity, tone, etc.) |
| **LLM-as-Judge** | Pattern where AI evaluates content against a structured rubric |
| **Comparison Gate** | Quality technique using a reference document as the standard |
| **Weighted Average** | Score calculation where some criteria count more than others |
| **Passing Threshold** | Minimum score required for content to be considered acceptable |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [← Previous Week](../week-3/participant-guide.md) | **Week 4** | [Next Week →](../week-5/participant-guide.md)
