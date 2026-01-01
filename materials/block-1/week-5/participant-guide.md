# **BLOCK 1 WEEK 5: GitHub Collaboration & Documentation**

**Block:** 1: AI Prompting Mastery
**Week:** 5 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** [← Previous Week](../week-4/participant-guide.md) | **Week 5** | [Next Week →](../week-6/participant-guide.md)

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
| 1 | Create and merge pull requests for safe collaboration | Exercise 5.1 |
| 2 | Use AI to generate comprehensive documentation | Exercise 5.2 |
| 3 | Document templates with all required sections | Exercise 5.3 |
| 4 | Organize repositories for team discovery and reuse | All Exercises |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Week 4 exercises (quality rubric, LLM-as-judge test, comparison gate)
- [ ] At least one quality rubric created
- [ ] Multiple templates in your GitHub repository
- [ ] Comfortable with basic GitHub operations (commit, push)

**Not ready?** Complete the [Week 4 exercises](../week-4/participant-guide.md) first - your quality rubrics will be referenced in documentation.

---

## Key Concepts

### Concept 1: Why Collaboration Matters

**Definition:**
Structured collaboration enables safe, reviewable changes to shared resources.

**Why It Matters:**
Your prompts and templates are valuable. Collaboration practices ensure changes don't break things, knowledge is preserved, and others can contribute.

**The Evolution:**
- Weeks 1-4: Personal prompt development
- Week 5+: Shareable, collaborative work
- Block 2-3: Team deployment and automation

**Core Principle:**
> Documentation is a gift to future you - invest time now, save time later.

---

### Concept 2: Pull Request Workflow

**Definition:**
A pull request (PR) is a proposed change that can be reviewed before being merged into the main version.

**Why It Matters:**
PRs enable safe collaboration. Changes are reviewed before they affect the main branch, preventing mistakes and enabling feedback.

**The Workflow:**
```
1. Create branch (copy of main)
       ↓
2. Make changes on branch
       ↓
3. Open Pull Request
       ↓
4. Review and discuss
       ↓
5. Merge into main
       ↓
6. Delete branch (cleanup)
```

**Key Vocabulary:**

| Term | Definition |
|------|------------|
| **Branch** | A parallel copy of the repository for making changes |
| **Pull Request** | A request to merge changes from one branch to another |
| **Merge** | Combining changes from one branch into another |
| **Diff** | The comparison showing what changed (red=removed, green=added) |

---

### Concept 3: AI-Assisted Documentation

**Definition:**
Using AI to generate documentation drafts that you then review and refine.

**Why It Matters:**
Documentation is often skipped because it's tedious. AI makes it faster, reducing the barrier to good documentation.

**Types of Documentation:**

| Type | Purpose | Contents |
|------|---------|----------|
| **README** | Overview and quick start | Purpose, setup, usage |
| **Usage guides** | Detailed instructions | Step-by-step, examples |
| **Template docs** | How to use a specific template | Variables, examples, tips |
| **Changelog** | What changed when | Version history |

**Key Insight:**
> AI accelerates documentation - but human review is essential. AI guesses at context; you verify accuracy.

---

### Concept 4: Repository Structure Best Practices

**Definition:**
Consistent organization that makes templates discoverable and maintainable.

**Recommended Structure:**
```
ai-prompt-library/
├── README.md              # Overview and quick start
├── CHANGELOG.md           # Version history
├── style.json             # Style configuration
│
├── templates/             # Reusable prompt templates
│   ├── README.md          # Templates overview
│   ├── email/
│   │   ├── formal-response.md
│   │   └── meeting-request.md
│   └── analysis/
│       └── data-summary.md
│
├── rubrics/               # Quality evaluation rubrics
│   ├── email-quality.md
│   └── report-quality.md
│
├── examples/              # Sample inputs and outputs
│   └── email-examples.md
│
└── resources/             # Reference materials
    └── style.json
```

**Naming Conventions:**
- Lowercase with hyphens: `email-template.md`
- Descriptive names: `client-proposal-formal.md`
- Version if needed: `proposal-v2.md`

---

### Quick Reference: PR Description Template

```markdown
## Summary
[What this PR adds/changes in 1-2 sentences]

## Changes
- [Change 1]
- [Change 2]
- [Change 3]

## Testing
- [ ] Tested prompt with [scenario]
- [ ] Validated JSON syntax
- [ ] Checked formatting

## Notes
[Any additional context reviewers need]
```

---

## Workshop Recap

### Session Summary

**Today's Focus:** Collaboration through pull requests and creating documentation that enables others to use your templates.

**Key Points from Each Segment:**

**Segment 1: Why Collaboration Matters**
- Weeks 1-4 were personal; Week 5+ is shareable
- Good documentation enables reuse
- GitHub is a workflow, not just storage
- Key takeaway: Documentation is investment in future time savings

**Segment 2: Pull Request Workflow**
- PRs are proposed changes with review
- Branch → Changes → PR → Review → Merge
- Good descriptions make review easier
- Key takeaway: PRs are safe drafts that can be reviewed

**Segment 3: AI-Assisted Documentation**
- AI can generate README, template docs, usage guides
- Always review and edit AI documentation
- Key takeaway: AI accelerates but doesn't replace human judgment

**Segment 4: Repository Structure**
- Consistent structure scales
- Every folder needs a README
- Naming conventions matter
- Key takeaway: Organization enables discovery

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 5.1 | 20 min | Merged pull request | PR workflow |
| 5.2 | 25 min | Updated README.md | AI documentation |
| 5.3 | 15 min | Documented template | Template docs |

---

### Exercise 5.1: Create a Branch and Pull Request

**Duration:** 20 minutes

**Purpose:**
Practice the pull request workflow by making a real change through the proper process.

**You Will Create:**
A branch, make changes, open a PR, and merge it.

---

#### Instructions

**Step 1: Create a new branch**
1. Go to your repository on GitHub
2. Click the branch dropdown (shows "main")
3. Type a new branch name: `add-week5-docs`
4. Click "Create branch: add-week5-docs"

**Step 2: Make changes on your branch**
1. Ensure you're on your new branch (check dropdown)
2. Add or edit a file (suggestions below)
3. Commit the change with a descriptive message
4. Make at least 2 separate commits

**Suggested changes:**
- Add a new template
- Update an existing file
- Add a new rubric
- Improve documentation

**Step 3: Open a Pull Request**
1. Click the "Pull requests" tab
2. Click "New pull request"
3. Set: Base: `main` ← Compare: `add-week5-docs`
4. Click "Create pull request"
5. Add title and description using this template:

```markdown
## Summary
Adding Week 5 documentation updates and improvements.

## Changes
- [List specific changes]
- [What files were added/modified]

## Testing
- [ ] Verified Markdown renders correctly
- [ ] Checked all links work

## Notes
Part of Week 5 exercises for AI Prompting Mastery.
```

**Step 4: Review and merge**
1. Look at the "Files changed" tab
2. Notice the diff view (red/green)
3. Click "Merge pull request"
4. Click "Confirm merge"
5. Click "Delete branch" (cleanup)

---

#### Deliverable Specification

**Deliverable:** Merged pull request visible in repository

**How to Verify:**
- Go to Pull requests → Closed
- Your PR should show as merged

**Quality Criteria:**
- [ ] Branch created with meaningful name
- [ ] At least 2 commits made
- [ ] PR has descriptive title and description
- [ ] PR successfully merged
- [ ] Branch deleted after merge

---

### Exercise 5.2: AI-Generated README

**Duration:** 25 minutes

**Purpose:**
Create comprehensive repository documentation using AI assistance, then refine with your knowledge.

**You Will Create:**
A complete README.md that explains your prompt library.

---

#### Instructions

**Step 1: Inventory your repository**
List everything in your repo:
- Templates (names and purposes)
- Rubrics (what they evaluate)
- Configuration files (style.json)
- Other resources

**Step 2: Generate README with AI**
Use this prompt, customized with your actual content:

```markdown
Create a professional README.md for my AI prompt library repository.

## Repository Contents
- templates/: [List your templates with brief descriptions]
- rubrics/: [List your rubrics]
- resources/: [List resources including style.json]
- [Any other folders/files]

## My Details
- Repository name: [your repo name]
- Primary use: [what you use prompts for]
- Audience: [just you / team / public]

## Requirements
1. Engaging introduction explaining the purpose
2. Clear "Getting Started" section with numbered steps
3. Repository structure with file descriptions
4. At least one usage example
5. Prerequisites section
6. Section on how to customize templates
7. Professional tone

Use clear Markdown formatting with headers and lists.
```

**Step 3: Review and refine**
Check the AI output for:
- [ ] Accuracy of file descriptions
- [ ] Correct paths and names
- [ ] Appropriate tone for your audience
- [ ] Missing information that should be added
- [ ] Information that's wrong or guessed incorrectly

**Step 4: Commit to repository**
Replace your current README.md with the refined version.

---

#### Deliverable Specification

**File Name:** `README.md`

**Location:** Repository root

**Required Sections:**
- Introduction/purpose
- Getting started
- Repository structure
- Usage example
- Prerequisites
- Customization guidance

**Quality Criteria:**
- [ ] All file references are accurate
- [ ] Provides value to someone new to the repo
- [ ] Professional and clear
- [ ] Reflects YOUR actual content

---

### Exercise 5.3: Document One Template

**Duration:** 15 minutes

**Purpose:**
Create complete documentation for one template that would allow someone else to use it without your help.

**You Will Create:**
Full documentation for your best template.

---

#### Instructions

**Step 1: Choose your best template**
Select a template that:
- You've used successfully
- Has clear variables/placeholders
- Would be valuable for others

**Step 2: Create documentation**
Use this structure:

```markdown
# [Template Name]

## Purpose
[2-3 sentences explaining what this template does and when to use it]

## When to Use
- [Scenario 1]
- [Scenario 2]
- [Scenario 3]

## Template

```markdown
[Your actual template with [VARIABLE] placeholders clearly marked]
```

## Variables

| Variable | Description | Example |
|----------|-------------|---------|
| [VAR1] | What to put here | Example value |
| [VAR2] | What to put here | Example value |

## Example Usage

### Input
[Show the template filled in with real values]

### Output
[Show actual AI response - real example]

## Tips for Best Results
1. [Tip based on your experience]
2. [Another tip]
3. [Third tip]

## Common Issues

| Issue | Solution |
|-------|----------|
| [Problem 1] | [How to fix] |
| [Problem 2] | [How to fix] |

## Quality Rubric
[Link to associated rubric if you have one, or embed criteria]

## Version History
- v1.0 ([Date]): Initial version
```

**Step 3: Add to repository**
Place in appropriate location (e.g., `templates/` folder)

---

#### Deliverable Specification

**File Name:** `[template-name].md` with documentation

**Location:** Appropriate templates folder

**Required Sections:**
- Purpose
- When to use
- Template with marked variables
- Variable descriptions
- Example with real output
- Tips
- Common issues

**Quality Criteria:**
- [ ] Someone else could use this without asking questions
- [ ] Real example included (not placeholder)
- [ ] Tips based on actual experience
- [ ] Variables clearly explained

---

## Templates & Resources

### Template: README Generator Prompt

```markdown
Create a README.md for an AI prompt template repository.

## Context
Repository name: [NAME]
Purpose: [DESCRIPTION]
Primary audience: [WHO]
Key contents:
- [Folder/file 1]: [Description]
- [Folder/file 2]: [Description]

## README Should Include
1. Clear title and tagline
2. Brief introduction (2-3 sentences)
3. Quick start (numbered steps)
4. Repository structure (tree format)
5. Usage examples
6. Prerequisites
7. How to customize
8. Contributing (if public)

## Tone
Professional but accessible. Assume reader is [EXPERIENCE LEVEL].
```

### Template: Template Documentation Prompt

```markdown
Write documentation for this prompt template:

## Template
---
[PASTE YOUR TEMPLATE]
---

## Documentation Needed
1. **Purpose:** What this template does (2-3 sentences)
2. **When to use:** 3+ specific scenarios
3. **Variables:** List each [BRACKET] item with description
4. **Example:** Complete filled-in example
5. **Tips:** 3 best practices
6. **Issues:** 2 common problems with solutions

Format as Markdown with clear headers.
```

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| GitHub PR Documentation | Tutorial | [docs.github.com](https://docs.github.com/en/pull-requests) | PR help |
| How to Write a README | Guide | [makeareadme.com](https://www.makeareadme.com/) | README best practices |
| Documentation Best Practices | Article | [writethedocs.org](https://www.writethedocs.org/guide/writing/beginners-guide-to-docs/) | General documentation |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Create and merge pull requests | Exercise 5.1 merged PR | ☐ |
| 2 | Generate documentation with AI | Exercise 5.2 README | ☐ |
| 3 | Document templates thoroughly | Exercise 5.3 template docs | ☐ |
| 4 | Organize repository for discovery | Updated structure | ☐ |

---

### Deliverables Checklist

| Deliverable | Evidence | Location | Complete? |
|-------------|----------|----------|-----------|
| Exercise 5.1 | Merged pull request | GitHub PR history | ☐ |
| Exercise 5.2 | Comprehensive README | Repository root | ☐ |
| Exercise 5.3 | Documented template | Templates folder | ☐ |

---

### Reflection Questions

1. **What clicked this week?** Did the PR workflow make sense?

2. **What's still fuzzy?** Any Git/GitHub concepts unclear?

3. **How will you apply this?** How will documentation help your future work?

4. **What surprised you?** How good (or not) was AI at documenting your work?

---

## Getting Help

### Common Questions This Week

**Q: Do I need to use PRs for every change?**
A: For solo work, not strictly necessary. But PRs create a record and help you review your own changes. It's good practice.

**Q: The AI documentation was mostly wrong. What should I do?**
A: Use it as a starting point, not final output. AI guesses at context - you provide the accurate details. Edit heavily.

**Q: How detailed should template documentation be?**
A: Detailed enough that someone else can use it without asking you questions. If they'd need to contact you, add more.

---

## Looking Ahead

### Next Week Preview: Week 6 - Prompt Library Organization

**Focus:**
Taxonomy design, naming conventions, metadata, and template index creation.

**How It Builds on This Week:**
The documentation you created this week becomes part of a larger organizational system.

**To Prepare:**
- [ ] Complete all Week 5 exercises
- [ ] Think about: How would you organize 50+ templates?
- [ ] Consider: What categories make sense for your work?
- [ ] Review your current folder structure

---

## Glossary

| Term | Definition |
|------|------------|
| **Pull Request (PR)** | A proposed change for review before merging |
| **Branch** | A parallel copy for making changes safely |
| **Merge** | Combining changes from one branch to another |
| **Diff** | Comparison showing changes (red=removed, green=added) |
| **README** | Main documentation file in a repository |
| **Changelog** | Record of what changed in each version |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [← Previous Week](../week-4/participant-guide.md) | **Week 5** | [Next Week →](../week-6/participant-guide.md)
