# Week 7: Block 1 Capstone Preparation

**Block:** 1 - AI Prompting Mastery
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Week 6 exercises completed
- [ ] Prompt library organized with taxonomy
- [ ] Template index created
- [ ] At least 5 documented templates
- [ ] `style.json` created and tested

## Exit Criteria

- [ ] All capstone components identified
- [ ] Personal Prompt Library complete
- [ ] Task priority matrix created
- [ ] `style.json` finalized
- [ ] Ready for Block 1 evaluation

---

## Workshop Content (45 minutes)

### Segment 1: Capstone Requirements Review (10 min)

**Block 1 Capstone: Personal Prompt Library**

Required components:
1. **Organized GitHub Repository** - Clear structure, documentation
2. **5+ Prompt Templates** - Documented, tested, quality-checked
3. **`style.json`** - Your personal style configuration
4. **Quality Rubrics** - At least 2 rubrics for different deliverable types
5. **Task Priority Matrix** - Analysis of AI-automation opportunities

**Evaluation criteria (6 dimensions):**
1. Template Quality & Documentation
2. Variety & Coverage
3. `style.json` Sophistication
4. Quality System Implementation
5. Repository Organization
6. Practical Application

**Passing score:** 18/30 (60%) minimum

### Segment 2: Template Completion Checklist (10 min)

**Each template must have:**

```markdown
---
title: [Clear, descriptive title]
category: [category/subcategory]
tags: [relevant, searchable, tags]
version: [semantic version]
last_updated: [YYYY-MM-DD]
quality_rubric: [link to rubric]
---

# [Template Title]

## Purpose
[2-3 sentences explaining what this template does]

## When to Use
- [Scenario 1]
- [Scenario 2]
- [Scenario 3]

## Template

\`\`\`markdown
[The actual prompt template with [VARIABLE] placeholders]
\`\`\`

## Variables

| Variable | Description | Example |
|----------|-------------|---------|
| [VAR1] | What goes here | Example value |

## Example

### Input
[Complete example with filled variables]

### Output
[Actual AI response]

## Quality Criteria
[Link to or embed quality rubric]

## Tips
- [Best practice 1]
- [Best practice 2]

## Version History
- v1.0: Initial creation
```

**Quality check each template:**
- [ ] Clear, specific purpose
- [ ] Variables clearly marked and explained
- [ ] Real example included
- [ ] Tested with actual AI platform
- [ ] Quality rubric connected

### Segment 3: Task Priority Matrix (12 min)

**Purpose:** Identify your highest-value AI automation opportunities

**The Matrix:**
```markdown
# Task Priority Matrix

## Instructions
Rate each task you perform regularly on two dimensions:
- **Frequency:** How often do you do this? (1=Rarely, 5=Daily)
- **Time:** How long does it take? (1=Minutes, 5=Hours)

Score = Frequency × Time

## My Tasks

| Task | Frequency (1-5) | Time (1-5) | Score | Has Template? |
|------|-----------------|------------|-------|---------------|
| [Task 1] | | | | Yes/No |
| [Task 2] | | | | Yes/No |
| [Task 3] | | | | Yes/No |
...

## Priority Quadrants

### High Frequency + High Time (Automate First)
- [Task]
- [Task]

### High Frequency + Low Time (Quick Wins)
- [Task]
- [Task]

### Low Frequency + High Time (Worth Automating)
- [Task]
- [Task]

### Low Frequency + Low Time (Optional)
- [Task]
- [Task]

## Action Plan
1. **Template to create next:** [Task from High/High quadrant]
2. **Quick win to tackle:** [Task from High/Low quadrant]
3. **Block 2 candidate:** [Complex workflow from matrix]
```

**This becomes your roadmap:**
- Block 1 templates from high-priority items
- Block 2 workflows from complex tasks
- Block 3 agents from multi-step processes

### Segment 4: Style.json Finalization (8 min)

**Review and refine:**
- Test with multiple prompts
- Add domain-specific settings
- Include format preferences

**Complete `style.json` template:**
```json
{
  "metadata": {
    "version": "1.0",
    "last_updated": "2024-12-15",
    "author": "Your Name"
  },
  "voice": {
    "tone": "professional but approachable",
    "formality": "business casual",
    "personality_traits": ["helpful", "direct", "thoughtful"]
  },
  "writing": {
    "sentence_length": "medium (15-25 words average)",
    "paragraph_length": "3-5 sentences",
    "structure": "clear headers, bulleted lists for complex information"
  },
  "preferences": {
    "always_use": [
      "active voice",
      "concrete examples",
      "clear transitions",
      "specific numbers over vague quantities"
    ],
    "always_avoid": [
      "jargon without explanation",
      "clichés",
      "passive voice",
      "hedge words (might, perhaps, maybe)"
    ]
  },
  "formatting": {
    "headers": "sentence case",
    "lists": "parallel structure required",
    "emphasis": "bold for key terms, italics for definitions",
    "code": "include language identifier"
  },
  "domain_specific": {
    "consulting": {
      "framework_references": "explain briefly when mentioned",
      "data_presentation": "lead with insight, support with data",
      "recommendations": "clear, actionable, numbered"
    }
  }
}
```

### Segment 5: Final Preparation (5 min)

**This week's focus:**
- Complete all template documentation
- Test every template with real tasks
- Finalize `style.json`
- Create task priority matrix
- Review repository organization

**Week 8 (Evaluation Week):**
- Self-evaluation
- Final submission
- Certification determination

**Questions and concerns**

---

## Self-Paced Exercises (60 minutes total)

### Exercise 7.1: Complete Template Documentation (Variable Time)

*Ensure all templates meet requirements*

1. **Audit current templates:**

```markdown
# Template Audit

| Template | Has Purpose? | Has Variables? | Has Example? | Has Rubric? | Complete? |
|----------|--------------|----------------|--------------|-------------|-----------|
| [Name] | ✓/✗ | ✓/✗ | ✓/✗ | ✓/✗ | ✓/✗ |
```

2. **Complete any incomplete templates:**
   - Add missing sections
   - Include real examples
   - Link to quality rubrics

3. **Ensure minimum of 5 complete templates**

4. **Add any high-priority templates from your matrix**

**Deliverable:** All templates complete and documented

---

### Exercise 7.2: Create Task Priority Matrix (20 minutes)

*Map your AI automation opportunities*

1. **List all regular tasks:**
   - Think through a typical week
   - Include communication, analysis, creation tasks
   - Consider tasks you avoid because they're tedious

2. **Create and populate the matrix:**

```markdown
# Task Priority Matrix

## Analysis Date: [Date]

## All Tasks

| Task | Description | Frequency (1-5) | Time Impact (1-5) | Priority Score | Template Status |
|------|-------------|-----------------|-------------------|----------------|-----------------|
| Email responses | Responding to client inquiries | 5 | 2 | 10 | Have template |
| Weekly reports | Status updates for management | 4 | 3 | 12 | Need template |
| [Your task] | [Description] | | | | |
| [Your task] | [Description] | | | | |
[Continue for 10-15 tasks]

## Priority Analysis

### Quadrant 1: High Frequency + High Time (Priority: Highest)
*These are your biggest automation opportunities*

| Task | Score | Action |
|------|-------|--------|
| [Task] | [X] | [Create template / Exists / Block 2 candidate] |

### Quadrant 2: High Frequency + Low Time (Priority: High)
*Quick wins - easy to automate, high cumulative value*

| Task | Score | Action |
|------|-------|--------|
| [Task] | [X] | [Action] |

### Quadrant 3: Low Frequency + High Time (Priority: Medium)
*Worth automating when they occur*

| Task | Score | Action |
|------|-------|--------|
| [Task] | [X] | [Action] |

### Quadrant 4: Low Frequency + Low Time (Priority: Low)
*Automate only if easy*

| Task | Score | Action |
|------|-------|--------|
| [Task] | [X] | [Action] |

## Block 1 Actions (This Week)
1. [ ] Complete template for: [Task from Q1]
2. [ ] Create quick template for: [Task from Q2]

## Block 2 Candidates
*Tasks that need workflow automation, not just prompts*
- [Complex task 1]
- [Complex task 2]

## Block 3 Candidates
*Tasks that need AI agents with decision-making*
- [Multi-step task 1]
- [Multi-step task 2]
```

**Deliverable:** `task-priority-matrix.md`

---

### Exercise 7.3: Finalize `style.json` (15 minutes)

*Complete your style configuration*

1. **Review current `style.json`:**
   - Test with 3-5 different prompt types
   - Note where style isn't being followed

2. **Enhance based on testing:**
   - Add specific guidance for problem areas
   - Include domain-specific rules
   - Add formatting preferences

3. **Validate JSON syntax:**
   - Use [JSONLint](https://jsonlint.com/)
   - Fix any errors

4. **Create usage documentation:**

```markdown
# style.json Usage Guide

## Purpose
This file defines my personal writing style for all AI-generated content.

## How to Use
Include in prompts as:
\`\`\`markdown
Follow this style guide for all output:

<style>
[Paste style.json content]
</style>
\`\`\`

## Key Style Points
1. [Most important style rule]
2. [Second most important]
3. [Third most important]

## When to Override
- [Scenario where style should differ]
- [Another exception]

## Version History
- v1.0: Initial creation
- v1.1: Added [what]
```

**Deliverable:** Finalized `style.json` + usage guide

---

### Exercise 7.4: Repository Final Review (15 minutes)

*Prepare for evaluation*

1. **Structure check:**
   - [ ] `README.md` is comprehensive
   - [ ] Template index is complete and accurate
   - [ ] All folders have README files
   - [ ] Naming conventions are consistent

2. **Content check:**
   - [ ] 5+ complete templates with all required sections
   - [ ] `style.json` is valid and documented
   - [ ] 2+ quality rubrics created
   - [ ] Task priority matrix complete

3. **Quality check:**
   - [ ] All templates tested with AI
   - [ ] Examples include actual AI responses
   - [ ] Rubrics are specific and usable

4. **Create capstone summary:**

```markdown
# Block 1 Capstone Summary

## Repository
[Link to GitHub repository]

## Contents

### Templates ([Number])
| Template | Category | Purpose |
|----------|----------|---------|
| [Name] | [Cat] | [Purpose] |

### Style Configuration
- style.json: [Brief description of key choices]

### Quality Rubrics
| Rubric | For | Criteria Count |
|--------|-----|----------------|
| [Name] | [Deliverable type] | [Number] |

### Task Priority Matrix
- Total tasks analyzed: [Number]
- High priority templates created: [Number]
- Block 2 candidates identified: [Number]

## Key Achievements
1. [Achievement 1]
2. [Achievement 2]
3. [Achievement 3]

## Lessons Learned
1. [Learning 1]
2. [Learning 2]
```

**Deliverable:** Complete repository ready for evaluation

---

## Key Takeaways

1. **Capstone is a practical demonstration** - Show real work, not theoretical
2. **Quality over quantity** - 5 excellent templates beat 20 mediocre ones
3. **Task priority matrix guides future work** - Know where to focus
4. **Documentation matters** - Others (and future you) need to understand
5. **`style.json` creates consistency** - The foundation for all output

---

## Preparation for Week 8

- Complete all outstanding exercises
- Perform self-evaluation using the rubric
- Prepare questions for final session
- Week 8 is evaluation and certification week

---

## Resources

- [Block 1 Capstone Rubric](#) - See evaluation criteria
- [Example Capstone Repository](#) - Reference example
- [JSON Validator](https://jsonlint.com/)
