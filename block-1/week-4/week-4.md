# Week 4: Quality Rubrics + Workflow Design

**Block:** 1 - AI Prompting Mastery
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Week 3 exercises completed
- [ ] style.json created and tested
- [ ] GitHub basics understood
- [ ] Comfortable with JSON syntax

## Exit Criteria

- [ ] Quality rubric created for one deliverable type
- [ ] LLM-as-judge pattern understood
- [ ] Comparison gate technique learned
- [ ] Workflow improvement process documented
- [ ] First quality-checked prompt template created

---

## Workshop Content (45 minutes)

### Segment 1: The Quality Problem (8 min)

**Without quality systems:**
- AI output quality varies unpredictably
- Manual review every time is exhausting
- "Good enough" becomes the standard
- No improvement over time

**With quality systems:**
- Consistent, measurable quality
- Clear pass/fail criteria
- Systematic improvement
- AI can self-evaluate

**The insight:** You can use AI to check AI output

### Segment 2: Creating Quality Rubrics (12 min)

**What is a rubric?**
- Scoring guide with specific criteria
- Clear descriptions for each quality level
- Removes subjectivity from evaluation

**Rubric structure:**
```markdown
# Quality Rubric: [Deliverable Type]

## Criterion 1: [Name]
**Weight:** [X%]

| Score | Description |
|-------|-------------|
| 5 | Excellent: [Specific description] |
| 4 | Good: [Specific description] |
| 3 | Acceptable: [Specific description] |
| 2 | Needs improvement: [Specific description] |
| 1 | Unacceptable: [Specific description] |

## Criterion 2: [Name]
[Repeat structure]
```

**Example: Email rubric:**
```markdown
# Quality Rubric: Professional Email

## Criterion 1: Clarity
| Score | Description |
|-------|-------------|
| 5 | Purpose clear in first sentence, no ambiguity |
| 4 | Purpose clear by first paragraph |
| 3 | Purpose eventually clear, some re-reading needed |
| 2 | Purpose unclear, requires inference |
| 1 | Reader cannot determine email purpose |

## Criterion 2: Tone
| Score | Description |
|-------|-------------|
| 5 | Perfect match to context and relationship |
| 4 | Appropriate with minor adjustments needed |
| 3 | Generally appropriate, some inconsistency |
| 2 | Noticeably off for context |
| 1 | Inappropriate tone for situation |

## Criterion 3: Actionability
| Score | Description |
|-------|-------------|
| 5 | Next steps crystal clear, deadlines explicit |
| 4 | Next steps clear, timing understood |
| 3 | Action implied but not explicit |
| 2 | Unclear what reader should do |
| 1 | No call to action when one is needed |
```

**Creating effective criteria:**
- Be specific (avoid "good" or "nice")
- Use observable behaviors
- Include examples where helpful
- Weight by importance

### Segment 3: LLM-as-Judge Pattern (12 min)

**The concept:**
Use a second AI call to evaluate the first AI's output

**The pattern:**
```markdown
# Evaluation Request

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

## Output Format
Provide your evaluation as:
- Criterion scores with justification
- Overall score
- Pass/Fail (passing = average ≥ 3.5)
- Top 3 improvements needed
```

**When to use:**
- High-stakes deliverables
- When you want systematic feedback
- To identify patterns in AI outputs
- Before sending to clients/stakeholders

**Tips:**
- Use a different AI instance for evaluation
- Be specific in rubric criteria
- Trust but verify (spot-check evaluations)

### Segment 4: Comparison Gates (8 min)

**The concept:**
Give AI an example of "perfect" output and ask it to match

**The pattern:**
```markdown
# Reference Document
[Paste example of ideal output - your own past work or approved sample]

# Task
Create [deliverable] that matches the style, structure, and quality of the reference document.

# Specific Requirements
- Match the tone exactly
- Use similar sentence structures
- Follow the same organizational pattern
- Apply formatting consistently

# Input
[Your specific request details]
```

**Why this works:**
- AI excels at pattern matching
- Removes ambiguity about expectations
- Produces more consistent results
- Your best work becomes the standard

**Caution:**
- Reference must be high quality
- Update references as standards evolve
- Don't share confidential references

### Segment 5: Quality Workflow Overview (5 min)

**The quality improvement cycle:**
```
Generate → Evaluate → Refine → Generate (improved) → Evaluate → ...
```

**Integrating quality into workflow:**
1. Create initial output
2. Run through quality rubric
3. If fails: Feed evaluation back for revision
4. If passes: Proceed to use

**Preview of automation (Block 2):**
- This manual process can be automated
- Workflows can include automatic quality gates
- Low-quality outputs get flagged/regenerated

---

## Self-Paced Exercises (60 minutes total)

### Exercise 4.1: Create a Quality Rubric (25 minutes)

*Build your first quality evaluation tool*

1. Choose a deliverable type you create regularly:
   - Emails
   - Reports
   - Meeting summaries
   - Social media posts
   - Technical documentation
   - Proposals

2. Create a rubric with 3-5 criteria:

```markdown
# Quality Rubric: [Your Deliverable Type]

## Overview
- **Purpose:** [What this rubric evaluates]
- **Passing score:** [Minimum average score, e.g., 3.5/5]
- **When to use:** [Context for this rubric]

## Criteria

### Criterion 1: [Name]
**Weight:** [X%]
**What it measures:** [Brief description]

| Score | Description | Example |
|-------|-------------|---------|
| 5 | [Excellent] | [Concrete example] |
| 4 | [Good] | [Concrete example] |
| 3 | [Acceptable] | [Concrete example] |
| 2 | [Needs work] | [Concrete example] |
| 1 | [Unacceptable] | [Concrete example] |

### Criterion 2: [Name]
[Repeat structure]

### Criterion 3: [Name]
[Repeat structure]

## Scoring
- Calculate weighted average
- Pass: ≥ [threshold]
- Fail: < [threshold]
```

**Deliverable:** `quality-rubric-[type].md`

---

### Exercise 4.2: LLM-as-Judge Test (20 minutes)

*Test the AI self-evaluation pattern*

1. Generate a deliverable using AI (use your templates from previous weeks)

2. Create an evaluation prompt:

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
2. Quote specific text supporting your score
3. Suggest one specific improvement

Then provide:
- Overall score (weighted average)
- Pass/Fail determination
- Top 3 actionable improvements

Format your response clearly with headers for each section.
```

3. Run the evaluation
4. Compare to your own assessment - does the AI evaluation match your judgment?

**Deliverable:** `llm-judge-test.md` containing:
- Original content
- AI evaluation
- Your own evaluation
- Comparison notes (where did AI agree/disagree?)

---

### Exercise 4.3: Comparison Gate Prompt (15 minutes)

*Create a reference-based quality prompt*

1. Find or create a "gold standard" example of work you've done
   - An email you're proud of
   - A report that got great feedback
   - Any deliverable that represents your best work

2. Create a comparison gate prompt:

```markdown
# Style Reference
The following is an example of excellent [deliverable type] that represents my preferred style:

---
[Paste your gold standard example]
---

# Style Analysis
Key characteristics of this reference:
- Tone: [Describe]
- Structure: [Describe]
- Length: [Describe]
- Notable patterns: [List 3-5]

# Task
Create a new [deliverable type] that matches this style exactly.

# Requirements
[Your specific request]

# Quality Check
After generating, verify:
- [ ] Tone matches reference
- [ ] Structure follows same pattern
- [ ] Length is comparable
- [ ] Key stylistic elements present
```

3. Test with a real request
4. Evaluate: Did the comparison improve output quality?

**Deliverable:** `comparison-gate-template.md` with test results

---

## Key Takeaways

1. **Quality rubrics remove subjectivity** from evaluating AI outputs
2. **LLM-as-judge enables systematic evaluation** at scale
3. **Comparison gates leverage your best work** as the quality standard
4. **Quality systems compound** - each improvement raises the baseline
5. **Manual quality checking now becomes automated checking later** (Block 2)

---

## Preparation for Week 5

- Complete all Week 4 exercises
- Use your rubric to evaluate 3-5 AI outputs this week
- Identify: Where does AI consistently score low?
- Prepare questions about quality systems
- Next week: GitHub collaboration and documentation patterns

---

## Resources

- [Rubric Examples](https://www.cultofpedagogy.com/rubric-design/) - General rubric design principles
- [LLM-as-Judge Research](https://arxiv.org/abs/2306.05685) - Academic paper on the technique
- [Anthropic's Constitutional AI](https://www.anthropic.com/research/constitutional-ai) - How AI self-evaluation works at scale
