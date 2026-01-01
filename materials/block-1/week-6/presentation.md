# **POWERPOINT PRESENTATION: BLOCK 1 WEEK 6**
## **Prompt Library Organization**

**Block:** 1: AI Prompting Mastery
**Week Number:** 6
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Participants who completed Weeks 1-5 with documented templates

**Week Learning Objectives:** By the end of this session, participants will:
1. Design a taxonomy that matches their mental model
2. Apply consistent naming conventions
3. Create metadata headers for searchability
4. Build a template index for discovery

**Entry Criteria:**
- [ ] Week 5 exercises completed
- [ ] At least 5 templates in repository
- [ ] Documentation created

**Exit Criteria:**
- [ ] Understands taxonomy approaches
- [ ] Knows naming convention rules
- [ ] Has plan to organize repository
- [ ] Understands template index purpose

**Presentation Structure:**
1. Opening & Recap (5 min) - Slides 1-3
2. Segment 1: The Organization Challenge (8 min) - Slides 4-5
3. Segment 2: Taxonomy Design (12 min) - Slides 6-8
4. Segment 3: Naming Conventions (10 min) - Slides 9-11
5. Segment 4: Metadata & Index + Close (10 min) - Slides 12-15

**Total Slides:** 15

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Block 1 Week 6: Prompt Library Organization

**Subtitle:** Finding Anything in 30 Seconds

**Content:**
- AI Practitioner Training Program
- Block 1: AI Prompting Mastery
- Week 6 of 8

**Graphic:** Clean title slide with blue color scheme (Block 1 theme).

**SPEAKER NOTES:**

"Welcome to Week 6! We're in the final stretch of Block 1 now.

You've built prompts, templates, quality rubrics, and documentation. Today we're making sure you can actually find all of that.

The goal: find any template in 30 seconds or less. If you can't find it, it might as well not exist.

Let's build an organization system that scales."

[Transition]

---

### SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-5 min | Opening | Week 5 Recap |
| 5-13 min | Segment 1 | The Organization Challenge |
| 13-25 min | Segment 2 | Taxonomy Design |
| 25-35 min | Segment 3 | Naming Conventions |
| 35-45 min | Segment 4 | Metadata & Index |

**Graphic:** Timeline with organization icons

**SPEAKER NOTES:**

"Here's our agenda:

First, why organization matters - the scale problem.

Then taxonomy design - how to categorize your templates.

Naming conventions - consistent rules that make finding things predictable.

Finally, metadata and indexing - tools for discovery.

Let's start with why this matters."

[Transition]

---

### SLIDE 3: WEEK 5 RECAP

**Title:** Quick Recap: Collaboration & Documentation

**Content:**

**Pull Requests:**
- Safe way to make changes
- Review before merge

**AI Documentation:**
- README generation
- Template documentation
- Human review essential

**Repository Structure:**
- Folders for organization
- READMEs explain contents

**The Question:**
What happens when you have 50+ templates?

**Graphic:** Week 5 icons

**SPEAKER NOTES:**

"Last week you learned collaboration - pull requests for safe changes, AI for documentation, repository structure basics.

[Point to question]

But here's the question: What happens when you have not 5 templates, but 50?

Right now you can probably remember what you have. In six months? On a team? With dozens of templates?

That's what we're solving today."

[Transition]

---

## SEGMENT 1: THE ORGANIZATION CHALLENGE
### Duration: 8 minutes | Slides 4-5

---

### SLIDE 4: THE SCALE PROBLEM

**Title:** The Organization Challenge

**Content:**

**Scale Changes Everything:**

| Scale | Experience |
|-------|------------|
| 5 templates | Easy to remember |
| 20 templates | Starting to forget what exists |
| 50+ templates | Can't find anything |
| Team library | Complete chaos |

**Symptoms of Poor Organization:**
- Recreating prompts you already have
- Can't find the "good" version
- Similar templates with slight differences
- No one knows what exists

**Graphic:** Progression showing increasing chaos

**SPEAKER NOTES:**

"Scale changes everything.

[Walk through table]

With 5 templates, you remember what you have. Easy.

With 20, you start forgetting. 'Did I make that template or not?'

With 50 or more, you can't find anything. You end up recreating things you already built.

On a team? It's chaos. Everyone builds their own version because they can't find what exists.

[Point to symptoms]

These are the symptoms. Recreating work. Can't find the good version. Similar templates everywhere. No one knows what exists."

[Transition]

---

### SLIDE 5: THE GOAL

**Title:** What Good Organization Looks Like

**Content:**

**The Goal:**
- Find any template in **under 30 seconds**
- Know immediately if a template exists
- Understand purpose without opening it
- Enable others to discover and reuse

**The Solution:**

| Component | Purpose |
|-----------|---------|
| Taxonomy | Categories that match your thinking |
| Naming | Predictable, searchable names |
| Metadata | Tags and info for discovery |
| Index | Central list of everything |

**Graphic:** Clean, organized structure

**SPEAKER NOTES:**

"Here's what we're aiming for.

[Point to goal]

Find anything in 30 seconds. Know immediately if something exists. Understand what a template does from its name. Enable others to find things without your help.

[Point to solution]

Four components make this work.

Taxonomy - categories that match how you think.
Naming - consistent, predictable names.
Metadata - tags and information for searching.
Index - one document listing everything.

Let's start with taxonomy."

[Transition]

---

## SEGMENT 2: TAXONOMY DESIGN
### Duration: 12 minutes | Slides 6-8

---

### SLIDE 6: TAXONOMY APPROACHES

**Title:** How to Categorize Your Templates

**Content:**

**Approach 1: By Deliverable Type**
```
templates/
├── emails/
├── reports/
├── proposals/
└── documentation/
```

**Approach 2: By Use Case**
```
templates/
├── client-communication/
├── internal-updates/
├── research/
└── content-creation/
```

**Approach 3: By Audience**
```
templates/
├── executive/
├── technical/
├── client-facing/
└── internal-team/
```

**Graphic:** Three folder structures side by side

**SPEAKER NOTES:**

"Three common approaches to categorizing templates.

[Point to Approach 1]

By deliverable type. Emails in one folder, reports in another. Good if you think 'I need an email template.'

[Point to Approach 2]

By use case or workflow. Client communication, internal updates, research. Good if you think 'I'm working on this project type.'

[Point to Approach 3]

By audience. Executive-level, technical, client-facing. Good if audience determines the format.

Which is right? Whichever matches how YOU think. There's no universal answer."

[Transition]

---

### SLIDE 7: HYBRID APPROACH

**Title:** Recommended: Hybrid Approach

**Content:**

**Combine approaches for best results:**
```
templates/
├── communication/          ← Use case
│   ├── client/             ← Audience
│   │   ├── formal-email.md
│   │   └── proposal-response.md
│   └── internal/
│       ├── status-update.md
│       └── meeting-summary.md
├── content/
│   ├── blog-post.md
│   └── social-media.md
└── analysis/
    ├── data-summary.md
    └── research-synthesis.md
```

**Key Insight:**
> The best taxonomy matches how you naturally think about your work.

**Graphic:** Hybrid structure with callouts

**SPEAKER NOTES:**

"I recommend a hybrid approach.

[Walk through structure]

Top level by use case - communication, content, analysis. Within communication, split by audience - client vs. internal.

This gives you the benefits of multiple approaches. Find by use case, then narrow by audience.

[Point to key insight]

The key insight: The best taxonomy matches how you naturally think.

Don't force yourself into someone else's structure. If you think 'I need something for the weekly report,' your structure should support that."

[Transition]

---

### SLIDE 8: DESIGN PRINCIPLES

**Title:** Taxonomy Design Principles

**Content:**

**Steps to Design:**
1. List all your current templates
2. Group naturally by how you'd look for them
3. Look for patterns in the groupings
4. Create max 3 levels of hierarchy
5. Document the structure

**Rules:**
- Categories should be mutually exclusive (mostly)
- Names should be intuitive
- 3 levels max (more gets confusing)
- When in doubt, go broader

**Example Questions:**
- "When I need X, where would I look?"
- "These templates go together because..."

**Graphic:** Process flowchart

**SPEAKER NOTES:**

"Here's how to design your taxonomy.

[Walk through steps]

Start by listing everything you have. Don't overthink - just list.

Group them naturally. Ask 'Where would I look for this?'

Look for patterns. Do you have lots of client communication? That's a category.

Keep it to 3 levels max. More than that gets confusing.

Document it so you remember the logic.

[Point to rules]

Categories should mostly not overlap. Names should be intuitive. When in doubt, make it broader - you can always subdivide later."

[Transition]

---

## SEGMENT 3: NAMING CONVENTIONS
### Duration: 10 minutes | Slides 9-11

---

### SLIDE 9: WHY NAMING MATTERS

**Title:** Naming: Your Primary Discovery Tool

**Content:**

**Why Names Matter:**
- Names are how you find things
- Good names are predictable
- Consistent naming enables scanning
- Names survive reorganization

**The Problem:**
```
finalFINAL_v3_REAL.md
New Template (2).md
email template.md
TempV2Final.md
```

**The Solution:**
```
email-client-proposal-v2.md
report-weekly-executive.md
analysis-competitive-deep.md
```

**Graphic:** Bad vs good file names

**SPEAKER NOTES:**

"Naming is critical. It's how you actually find things.

[Point to 'Why Names Matter']

Good names are predictable. If I know the convention, I can guess the name. Consistent naming lets me scan a folder quickly. And names survive reorganization - even if you move files, the name still tells you what it is.

[Point to problem]

We've all seen these. 'finalFINAL_v3_REAL.' 'New Template (2).' Useless.

[Point to solution]

This is what we want. Type, specificity, variant. Predictable, scannable, meaningful."

[Transition]

---

### SLIDE 10: THE NAMING PATTERN

**Title:** The Naming Pattern

**Content:**

**Pattern:**
```
[type]-[specificity]-[variant].md
```

**Examples:**
```
email-client-formal.md
email-client-followup.md
email-internal-status.md
report-weekly-technical.md
report-monthly-executive.md
analysis-data-summary.md
analysis-competitive-deep.md
```

**Structure:**
- **Type:** What kind of deliverable (email, report)
- **Specificity:** Who/what/context (client, weekly)
- **Variant:** Style or version (formal, v2)

**Graphic:** Pattern with color-coded parts

**SPEAKER NOTES:**

"Here's the pattern: type, specificity, variant.

[Walk through examples]

email-client-formal - type is email, specificity is client, variant is formal.

report-weekly-technical - type is report, specificity is weekly, variant is technical.

This pattern is scannable. All emails sort together. Within emails, client emails sort together. You can find things quickly.

[Point to structure]

Type is the deliverable kind. Specificity is context. Variant is style or version."

[Transition]

---

### SLIDE 11: NAMING RULES

**Title:** Naming Rules

**Content:**

**The Rules:**
1. **Lowercase always** - Avoids OS conflicts
2. **Hyphens for spaces** - No spaces, no underscores
3. **General → Specific** - Aids sorting
4. **No abbreviations** - Unless universally known
5. **Action-oriented** - Show what it does

**Version Handling:**
- Active iteration: `template-name-v2.md`
- Archive old versions: `archive/template-name-v1.md`
- Dated: `template-name-2024-01.md`

**Test:** Can someone guess what's in this file from the name alone?

**Graphic:** Rules with examples

**SPEAKER NOTES:**

"Five rules for naming.

[Walk through rules]

Lowercase always - some operating systems treat 'File.md' and 'file.md' as different, others as same. Lowercase avoids the problem.

Hyphens for spaces - no actual spaces, no underscores. Hyphens are readable and URL-safe.

General to specific - email-client-formal, not formal-client-email. This helps with sorting.

No abbreviations unless universal. 'email' is fine. 'em-cl-frm' is not.

Action-oriented when possible. 'data-analysis' tells you more than 'data.'

[Point to test]

The test: Can someone guess what's in this file from just the name? If yes, good name."

[Transition]

---

## SEGMENT 4: METADATA & INDEX + CLOSE
### Duration: 10 minutes | Slides 12-15

---

### SLIDE 12: TEMPLATE METADATA

**Title:** Metadata Headers

**Content:**

**Add to every template:**
```markdown
---
title: Client Proposal Email
category: communication/client
tags: [email, proposal, formal, sales]
version: 2.1
last_updated: 2024-12-15
author: Your Name
quality_rubric: email-quality.md
---

# Template content below...
```

**Why Metadata:**
- Search by tags
- Know currency (last updated)
- Link to quality systems
- Track authorship

**Graphic:** Metadata header with callouts

**SPEAKER NOTES:**

"Metadata headers add searchable information to every template.

[Walk through header]

Title - human-readable name.
Category - where it lives.
Tags - keywords for searching.
Version - track iterations.
Last updated - know if it's current.
Quality rubric - link to evaluation criteria.

[Point to 'Why Metadata']

This enables searching by tags. You can see at a glance if something's current. It connects to your quality systems."

[Transition]

---

### SLIDE 13: TEMPLATE INDEX

**Title:** The Template Index

**Content:**

**Your single source of truth:**
```markdown
# Template Index

## Communication

### Client
| Template | Purpose | Tags |
|----------|---------|------|
| [formal-email](link) | Formal correspondence | formal |
| [proposal-response](link) | RFP responses | proposal |

### Internal
| Template | Purpose | Tags |
|----------|---------|------|
| [status-update](link) | Weekly updates | status |

## How to Find Templates
1. Browse by category
2. Search (Ctrl+F) for keywords
3. Check tags
```

**Graphic:** Index structure

**SPEAKER NOTES:**

"The template index is your single source of truth for what exists.

[Walk through structure]

Organized by your taxonomy. Each template has a link, purpose, and tags.

At the bottom, instructions for how to find things.

When someone asks 'do we have a template for X?' - point them to the index. If it's not there, it doesn't exist."

[Transition]

---

### SLIDE 14: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Focus |
|----------|------|-------------|-------|
| Exercise 6.1: Design Taxonomy | 20 min | `taxonomy-design.md` | Planning |
| Exercise 6.2: Reorganize Repo | 25 min | Updated structure | Implementation |
| Exercise 6.3: Create Index | 15 min | `template-index.md` | Discovery |
| **Total** | **60 min** | | |

**Key Requirements:**
- Taxonomy must match YOUR mental model
- All templates renamed consistently
- All templates have metadata headers
- Index includes all templates

**Graphic:** Three exercise cards

**SPEAKER NOTES:**

"Three exercises this week.

Exercise 6.1 - design your taxonomy. 20 minutes of planning before implementation.

Exercise 6.2 - actually reorganize your repository. Rename, move, add metadata.

Exercise 6.3 - create your template index.

[Point to requirements]

Key: This must work for YOU. Don't copy someone else's taxonomy. Rename consistently. Add metadata to everything. Index everything."

[Transition]

---

### SLIDE 15: NEXT WEEK PREVIEW

**Title:** Next Week: Capstone Preparation

**Content:**

**Preview:**
Completing all capstone components, finalizing `style.json`, task priority matrix.

**What to Complete:**
- [ ] Exercise 6.1: Taxonomy Design
- [ ] Exercise 6.2: Repository Reorganization
- [ ] Exercise 6.3: Template Index

**Key Preparation:**
- Review capstone requirements
- Ensure all templates have metadata
- Your organized repository IS a capstone requirement

**Graphic:** Capstone preview

**SPEAKER NOTES:**

"Next week is capstone preparation. We're getting everything ready for your Block 1 certification.

Your organized repository IS a capstone requirement. The work you do this week directly impacts your evaluation.

[Point to key preparation]

Review the capstone requirements. Make sure everything has metadata. The structure you build this week is what gets evaluated.

Questions before we wrap?

[Take questions]

Good session. You now have the tools for scalable organization. Use them.

See you next week!"

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
