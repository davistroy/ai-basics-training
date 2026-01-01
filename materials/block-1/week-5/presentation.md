# **POWERPOINT PRESENTATION: BLOCK 1 WEEK 5**
## **GitHub Collaboration & Documentation**

**Block:** 1: AI Prompting Mastery
**Week Number:** 5
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Participants who completed Weeks 1-4 with quality rubrics and templates

**Week Learning Objectives:** By the end of this session, participants will:
1. Create and merge pull requests for safe collaboration
2. Use AI to generate comprehensive documentation
3. Document templates with all required sections
4. Organize repositories for team discovery

**Entry Criteria:**
- [ ] Week 4 exercises completed
- [ ] Quality rubric created
- [ ] Multiple templates in repository

**Exit Criteria:**
- [ ] Understands PR workflow
- [ ] Knows how to use AI for documentation
- [ ] Has plan to document templates
- [ ] Understands repository organization

**Presentation Structure:**
1. Opening & Recap (5 min) - Slides 1-3
2. Segment 1: Why Collaboration Matters (7 min) - Slides 4-5
3. Segment 2: Pull Request Workflow (13 min) - Slides 6-9
4. Segment 3: AI-Assisted Documentation (15 min) - Slides 10-13
5. Segment 4: Repository Structure + Close (5 min) - Slides 14-16

**Total Slides:** 16

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Block 1 Week 5: GitHub Collaboration & Documentation

**Subtitle:** Sharing Your Work Safely and Clearly

**Content:**
- AI Practitioner Training Program
- Block 1: AI Prompting Mastery
- Week 5 of 8

**Graphic:** Clean title slide with blue color scheme (Block 1 theme).

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Week 5! We're in the home stretch of Block 1 now.

Over the past four weeks, you've built prompts, templates, quality rubrics, and configuration files. Today we're making all of that shareable.

How do you collaborate safely on prompts? How do you document templates so others can actually use them? These skills take you from individual contributor to team enabler.

Let's dive in."

[Transition]

---

### SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-5 min | Opening | Week 4 Recap |
| 5-12 min | Segment 1 | Why Collaboration Matters |
| 12-25 min | Segment 2 | Pull Request Workflow |
| 25-40 min | Segment 3 | AI-Assisted Documentation |
| 40-45 min | Segment 4 | Repository Structure + Close |

**Graphic:** Timeline with collaboration and documentation icons

**SPEAKER NOTES:**

"Here's our agenda:

We'll start with why collaboration matters - the shift from personal to shareable work.

Then pull requests - the workflow for making safe, reviewable changes.

The bulk of our time is on AI-assisted documentation - using AI to speed up the documentation process.

We'll close with repository structure best practices."

[Transition]

---

### SLIDE 3: WEEK 4 RECAP

**Title:** Quick Recap: Quality Systems

**Content:**

**Quality Rubrics:**
- Specific criteria with score descriptions
- Makes quality measurable

**LLM-as-Judge:**
- AI evaluating AI with your rubric
- Scalable quality checking

**Comparison Gates:**
- Your best work as the standard
- Pattern matching for consistency

**The Question:**
How do others use your templates? How do they know if output is good enough?

**Graphic:** Quality system icons from Week 4

**SPEAKER NOTES:**

"Quick recap from Week 4.

You built quality rubrics with specific criteria. You tested LLM-as-judge for scalable evaluation. You created comparison gates using your best work.

[Point to question]

But here's the question: How do others use your templates? If you share a template, how does the other person know how to use it? How do they know if their output is good enough?

That's what documentation solves. Let's talk about why collaboration matters first."

[Transition]

---

## SEGMENT 1: WHY COLLABORATION MATTERS
### Duration: 7 minutes | Slides 4-5

---

### SLIDE 4: THE EVOLUTION

**Title:** From Personal to Shareable

**Content:**

**Your Journey So Far:**

| Phase | Focus | Outcome |
|-------|-------|---------|
| Weeks 1-2 | Prompting techniques | Skills |
| Weeks 3-4 | Configuration & quality | Systems |
| Week 5+ | Collaboration & sharing | Team value |
| Block 2-3 | Automation & deployment | Scale |

**The Shift:**
Templates are only valuable if others can use them.

**Graphic:** Progression arrow from individual to team to organization

**SPEAKER NOTES:**

"Let's look at where you've been and where you're going.

[Walk through table]

Weeks 1-2 were about skills - prompting techniques.
Weeks 3-4 were about systems - configuration and quality.
Week 5 onwards is about sharing - making your work usable by others.
Blocks 2 and 3 are about scale - automation and deployment.

[Point to shift]

Here's the key insight: Templates are only valuable if others can use them. A brilliant template that no one else can understand is wasted potential."

[Transition]

---

### SLIDE 5: BENEFITS OF DOCUMENTATION

**Title:** Why Documentation Matters

**Content:**

**Benefits:**

| Benefit | Without Documentation | With Documentation |
|---------|----------------------|-------------------|
| Future you | "What was this for?" | Quick understanding |
| Teammates | "How do I use this?" | Self-service |
| Quality | Inconsistent use | Consistent application |
| Knowledge | Lost when you leave | Preserved |

**Key Insight:**
> Documentation is a gift to future you. Invest time now, save time later.

**Graphic:** Before/after comparison

**SPEAKER NOTES:**

"Why bother with documentation?

[Walk through table]

Without it, future you forgets what things are for. Teammates have to ask you questions. Usage is inconsistent. Knowledge is lost when people leave.

With it, understanding is instant. Others can self-serve. Templates are used consistently. Knowledge is preserved.

[Point to key insight]

Documentation is a gift to future you. The time you spend documenting now saves multiples of that time later.

Now let's learn the workflow for collaborating safely."

[Transition]

---

## SEGMENT 2: PULL REQUEST WORKFLOW
### Duration: 13 minutes | Slides 6-9

---

### SLIDE 6: WHAT IS A PULL REQUEST

**Title:** Pull Requests: Safe Collaboration

**Content:**

**Definition:**
A pull request (PR) is a proposed change that can be reviewed before merging.

**Analogy:**
Like sending a draft for approval before publishing.

**Why It Matters:**
- Changes reviewed before affecting main
- Discussion happens on the change
- History shows what changed and why
- Can be rejected or revised

**Graphic:** Document with "draft" stamp becoming "published"

**SPEAKER NOTES:**

"What is a pull request?

It's a proposed change. You're saying 'I want to make these changes - please review them before we merge.'

[Point to analogy]

Think of it like sending a draft for approval. The editor reviews, suggests changes, and only then does it get published.

[Point to 'Why It Matters']

PRs make collaboration safe. Changes don't affect main until reviewed. Discussion happens right on the change. History is preserved. And if something's wrong, it can be rejected or revised before any damage is done."

[Transition]

---

### SLIDE 7: THE PR WORKFLOW

**Title:** The Pull Request Workflow

**Content:**

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
- **Branch:** Parallel copy for changes
- **Merge:** Combine branch into main
- **Diff:** What changed (red=removed, green=added)

**Graphic:** Workflow diagram with icons

**SPEAKER NOTES:**

"Here's the workflow, step by step.

[Walk through steps]

First, create a branch. This is a copy of main where you can make changes safely.

Make your changes on the branch. Commit them.

Open a pull request. This starts the review process.

Review and discuss. Look at the diff, add comments, suggest changes.

When approved, merge into main.

Delete the branch to clean up.

[Point to vocabulary]

Key terms: Branch is your working copy. Merge combines it back. Diff shows what changed."

[Transition]

---

### SLIDE 8: LIVE DEMO - CREATING A PR

**Title:** Live Demo: Pull Request Workflow

**Content:**

**We'll Do:**
1. Create a branch
2. Make a change
3. Open a PR
4. Look at the diff
5. Merge

**Watch For:**
- How branches work
- What the diff looks like
- PR description importance

**Graphic:** Demo placeholder

**SPEAKER NOTES:**

"[DEMO - Show, don't tell]"

"Let me walk through this live.

[Create branch]

I'm creating a branch called 'demo-update'...

[Make change]

Now I'll edit a file on this branch...

[Open PR]

Opening a pull request. Notice I'm setting base as main, compare as my branch...

[Show diff]

Here's the diff. Red is what I removed. Green is what I added. This is what reviewers look at.

[Merge]

If this looks good, I merge. And now main has my changes.

[Delete branch]

Finally, cleanup - delete the branch."

[Transition]

---

### SLIDE 9: PR DESCRIPTION TEMPLATE

**Title:** Writing Good PR Descriptions

**Content:**

**Template:**
```markdown
## Summary
[What this PR adds/changes - 1-2 sentences]

## Changes
- [Change 1]
- [Change 2]
- [Change 3]

## Testing
- [ ] Tested prompt with [scenario]
- [ ] Validated JSON syntax
- [ ] Checked formatting

## Notes
[Additional context]
```

**Why It Matters:**
Good descriptions make review faster and create useful history.

**Graphic:** PR description example

**SPEAKER NOTES:**

"When you open a PR, write a good description.

[Walk through template]

Summary - what does this PR do? One or two sentences.

Changes - bullet list of specific changes.

Testing - what did you check? Use checkboxes.

Notes - anything else reviewers need to know.

Good descriptions make review faster. They also create useful history - six months from now, you can see what this PR was about.

In Exercise 5.1, you'll create a real PR with a proper description."

[Transition]

---

## SEGMENT 3: AI-ASSISTED DOCUMENTATION
### Duration: 15 minutes | Slides 10-13

---

### SLIDE 10: DOCUMENTATION TYPES

**Title:** Types of Documentation You Need

**Content:**

| Type | Purpose | Key Contents |
|------|---------|--------------|
| **README** | Overview & quick start | Purpose, setup, usage |
| **Usage guides** | Detailed how-to | Steps, examples, tips |
| **Template docs** | Per-template guide | Variables, examples |
| **Changelog** | Version history | What changed, when |

**The Problem:**
Documentation is often skipped because it's tedious.

**The Solution:**
AI can accelerate the process.

**Graphic:** Four document types with icons

**SPEAKER NOTES:**

"You need several types of documentation.

[Walk through table]

README - the overview. What is this? How do I start?

Usage guides - detailed instructions for specific tasks.

Template docs - how to use each individual template.

Changelog - what changed in each version.

[Point to problem]

The problem? Documentation is tedious. It often gets skipped.

[Point to solution]

AI can help. It won't replace your judgment, but it can generate drafts quickly."

[Transition]

---

### SLIDE 11: AI README PROMPT

**Title:** Generating READMEs with AI

**Content:**

**The Prompt:**
```markdown
Create a README.md for my AI prompt template repository.

## Context
Repository name: [name]
Purpose: [what it contains]
Primary audience: [who will use it]
Key contents: [list of main files/folders]

## README Should Include
1. Clear title and description
2. Quick start (3-5 steps)
3. Repository structure overview
4. Prerequisites
5. Usage examples
6. How to customize

## Tone
Professional but accessible.
```

**Graphic:** Prompt with callouts

**SPEAKER NOTES:**

"Here's a prompt for generating README files.

[Walk through sections]

Context - tell AI about your repository. Name, purpose, audience, contents.

Requirements - what sections the README needs.

Tone - how it should sound.

The more specific you are about your content, the better the output. Don't expect AI to guess what's in your repo - tell it.

Let me show you what this produces."

[Transition]

---

### SLIDE 12: LIVE DEMO - AI DOCUMENTATION

**Title:** Live Demo: AI-Generated Documentation

**Content:**

**We'll Generate:**
Documentation for a sample template

**Watch For:**
- What AI gets right
- What AI guesses (needs editing)
- How to refine the output

**Graphic:** Demo placeholder

**SPEAKER NOTES:**

"[DEMO - Show, don't tell]"

"Let me show you AI documentation in action.

[Set up]

I have this template with minimal documentation. Let me ask AI to document it.

[Run prompt]

[Review output]

Look at what it generated. Structure is good. Purpose section - decent guess, but I need to refine.

[Point out issues]

See here? AI guessed this is for 'weekly reports.' Actually, it's for client proposals. I need to fix that.

And here - it made up variables that don't exist in my template.

[Key point]

AI gives you a starting point, not a finished product. Always review and edit."

[Transition]

---

### SLIDE 13: TEMPLATE DOCUMENTATION STRUCTURE

**Title:** Documenting Individual Templates

**Content:**

**Required Sections:**

```markdown
# [Template Name]

## Purpose
[What it does, when to use]

## Template
[The actual template with [VARIABLES] marked]

## Variables
| Variable | Description | Example |

## Example
### Input: [Filled template]
### Output: [Actual AI response]

## Tips
[Best practices from experience]

## Common Issues
[Problems and solutions]
```

**Key Insight:**
Someone should be able to use this without asking you questions.

**Graphic:** Documentation structure diagram

**SPEAKER NOTES:**

"For individual templates, here's what documentation needs.

[Walk through sections]

Purpose - what does it do, when would you use it?

Template - the actual template with variables clearly marked.

Variables - table explaining each placeholder.

Example - real input and real output. Not hypothetical.

Tips - what you've learned from using it.

Common issues - problems and how to solve them.

[Point to key insight]

The test: Could someone else use this template without asking you questions? If not, add more detail."

[Transition]

---

## SEGMENT 4: REPOSITORY STRUCTURE + CLOSE
### Duration: 5 minutes | Slides 14-16

---

### SLIDE 14: REPOSITORY STRUCTURE

**Title:** Organizing for Discovery

**Content:**

**Recommended Structure:**
```
ai-prompt-library/
├── README.md
├── style.json
├── templates/
│   ├── README.md
│   ├── email/
│   └── analysis/
├── rubrics/
└── resources/
```

**Best Practices:**
- Every folder has a README
- Consistent naming (lowercase, hyphens)
- Group by type or use case
- Max 3 levels deep

**Graphic:** Folder structure diagram

**SPEAKER NOTES:**

"Quick best practices for structure.

[Walk through structure]

Root has your main README and style.json.

Templates folder contains subfolders by type.

Rubrics folder for quality rubrics.

Resources for other materials.

[Point to best practices]

Every folder should have a README explaining what's in it.

Consistent naming - lowercase, hyphens.

Group by type or use case, whichever makes more sense for your work.

Don't go more than 3 levels deep - gets confusing."

[Transition]

---

### SLIDE 15: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Focus |
|----------|------|-------------|-------|
| Exercise 5.1: Create a PR | 20 min | Merged PR | PR workflow |
| Exercise 5.2: AI README | 25 min | Updated README | AI documentation |
| Exercise 5.3: Document Template | 15 min | Template docs | Template documentation |
| **Total** | **60 min** | | |

**Key Requirements:**
- PR must have proper description
- README must reflect YOUR actual content
- Template docs must include real examples

**Graphic:** Three exercise cards

**SPEAKER NOTES:**

"Three exercises this week.

Exercise 5.1 - create a real PR. Branch, changes, PR with description, merge.

Exercise 5.2 - generate README with AI, then refine it to be accurate.

Exercise 5.3 - full documentation for one template. All required sections.

[Point to requirements]

Key: Make it real. Your PR should have meaningful changes. Your README should describe YOUR actual repository. Your template docs should have real examples, not placeholders."

[Transition]

---

### SLIDE 16: NEXT WEEK PREVIEW

**Title:** Next Week: Prompt Library Organization

**Content:**

**Preview:**
Taxonomy design, naming conventions, metadata, template index.

**What to Complete:**
- [ ] Exercise 5.1: Pull Request
- [ ] Exercise 5.2: AI-Generated README
- [ ] Exercise 5.3: Documented Template

**Key Preparation:**
- Think about: How would you organize 50+ templates?
- Consider: What categories make sense for YOUR work?

**Connection:**
Good documentation + good organization = usable library.

**Graphic:** Organization preview

**SPEAKER NOTES:**

"Next week we're focusing on organization.

When you have 5 templates, you can remember what you have. When you have 50, you need systems.

We'll cover taxonomy - how to categorize. Naming conventions. Metadata for search. Creating a template index.

[Point to preparation]

Start thinking: How would you organize a large library? What categories make sense for your work? There's no single right answer - it depends on how you think about your tasks.

Questions before we wrap?

[Take questions]

Great session. You now have collaboration tools - PRs for safe changes, AI for documentation, structure for organization.

See you next week!"

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
