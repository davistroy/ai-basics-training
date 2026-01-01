# **BLOCK 1 WEEK 6: Prompt Library Organization**

**Block:** 1: AI Prompting Mastery
**Week:** 6 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** [← Previous Week](../week-5/participant-guide.md) | **Week 6** | [Next Week →](../week-7/participant-guide.md)

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
| 1 | Design a taxonomy that matches how you think about work | Exercise 6.1 |
| 2 | Apply consistent naming conventions across templates | Exercise 6.2 |
| 3 | Create metadata headers for searchability | Exercise 6.2 |
| 4 | Build a template index for discovery | Exercise 6.3 |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Week 5 exercises (PR, README, template documentation)
- [ ] At least 5 templates in your repository
- [ ] Repository documentation (README) updated
- [ ] Comfortable with GitHub file management

---

## Key Concepts

### Concept 1: The Organization Challenge

**Definition:**
As prompt libraries grow, finding and managing templates becomes increasingly difficult without systematic organization.

**The Scale Problem:**
- 5 templates: Easy to remember
- 20 templates: Starting to forget what exists
- 50+ templates: Can't find anything
- Team library: Complete chaos

**Symptoms of Poor Organization:**
- Recreating prompts you already have
- Can't find the "good" version
- Similar templates with slight differences
- No one knows what exists

**The Goal:**
> Find any template in under 30 seconds. Know immediately if a template exists.

---

### Concept 2: Taxonomy Design

**Definition:**
A classification system for organizing your prompts into hierarchical categories.

**Three Approaches:**

| Approach | Structure | Best For |
|----------|-----------|----------|
| By Deliverable | emails/, reports/, proposals/ | When you think in output types |
| By Use Case | client-communication/, research/, content/ | When you think in workflows |
| By Audience | executive/, technical/, client-facing/ | When audience determines format |

**Hybrid Approach (Recommended):**
```
templates/
├── communication/
│   ├── client/
│   │   ├── formal-email.md
│   │   └── proposal-response.md
│   └── internal/
│       └── status-update.md
├── content/
│   └── blog-post.md
└── analysis/
    └── data-summary.md
```

**Choosing Your Taxonomy:**
1. List all your current templates
2. Group them naturally by how you think of them
3. Look for patterns in the groupings
4. Create max 3 levels of hierarchy
5. Document the structure

---

### Concept 3: Naming Conventions

**Definition:**
Consistent rules for naming files that make discovery predictable.

**The Pattern:**
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

**Rules:**
1. **Lowercase always** - Avoids OS conflicts
2. **Hyphens for spaces** - No spaces or underscores
3. **General → Specific** - Aids sorting and scanning
4. **No abbreviations** - Unless universally understood
5. **Action-oriented** - Shows what template does

**Anti-patterns:**
```
WRONG: finalFINAL_v3_REAL.md
WRONG: New Template (2).md
WRONG: email template.md
RIGHT: email-client-proposal-v2.md
```

---

### Concept 4: Template Metadata

**Definition:**
Structured information in template headers that enables searching and organization.

**The Pattern:**
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
```

**Why Metadata Matters:**
- Enables tag-based searching
- Shows currency (last updated)
- Links to quality systems
- Supports automated indexing

---

### Concept 5: Template Index

**Definition:**
A central document listing all templates with descriptions, enabling quick discovery.

**The Pattern:**
```markdown
# Template Index

## Quick Navigation
- [Communication](#communication)
- [Content](#content)
- [Analysis](#analysis)

## Communication

### Client
| Template | Purpose | Tags |
|----------|---------|------|
| [formal-email](path) | Formal correspondence | formal, client |
| [proposal-response](path) | Responding to RFPs | proposal, sales |

### Internal
| Template | Purpose | Tags |
|----------|---------|------|
| [status-update](path) | Weekly updates | status, internal |
```

**Discovery Methods:**
1. Browse by category
2. Search by name
3. Search by tag
4. Index lookup

---

## Workshop Recap

### Session Summary

**Today's Focus:** Organizing your prompt library for scale - taxonomy, naming, metadata, and indexing.

**Key Points from Each Segment:**

**Segment 1: The Organization Challenge**
- Scale creates findability problems
- Poor organization leads to duplicate work
- Goal: Find anything in 30 seconds
- Key takeaway: Organize before you need to

**Segment 2: Taxonomy Design**
- Three approaches: deliverable, use case, audience
- Hybrid approach recommended
- Match your mental model
- Key takeaway: Best taxonomy is one that matches how YOU think

**Segment 3: Naming Conventions**
- Consistent patterns enable prediction
- Lowercase, hyphens, no spaces
- General to specific
- Key takeaway: A few rules applied everywhere compound

**Segment 4: Metadata & Index**
- Headers enable searching
- Index is single source of truth
- Regular maintenance required
- Key takeaway: The index helps you and others find things

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 6.1 | 20 min | `taxonomy-design.md` | Taxonomy planning |
| 6.2 | 25 min | Reorganized repository | Implementation |
| 6.3 | 15 min | `template-index.md` | Discovery tool |

---

### Exercise 6.1: Design Your Taxonomy

**Duration:** 20 minutes

**Purpose:**
Create a sustainable organization system that matches how you think about your work.

---

#### Instructions

**Step 1: Inventory current templates**
List every template you have:
- Name
- Current location
- What it's for

**Step 2: Group naturally**
Without thinking too hard, group templates by how you'd look for them:
- "When I need X, I'd look for..."
- "These templates go together because..."

**Step 3: Design taxonomy**

```markdown
# My Prompt Library Taxonomy

## Design Principles
- [Principle 1: e.g., "Organize by deliverable type"]
- [Principle 2: e.g., "Max 3 levels deep"]
- [Principle 3: e.g., "Categories match how I think"]

## Top-Level Categories
1. **[Category 1]** - [What goes here]
2. **[Category 2]** - [What goes here]
3. **[Category 3]** - [What goes here]

## Full Structure
```
templates/
├── [category-1]/
│   ├── [subcategory-a]/
│   │   ├── [template-1.md]
│   │   └── [template-2.md]
│   └── [subcategory-b]/
├── [category-2]/
└── [category-3]/
```

## Naming Convention
Pattern: [type]-[specificity]-[variant].md

Rules:
- [Rule 1]
- [Rule 2]
- [Rule 3]

## When to Create New Categories
- [Criterion 1]
- [Criterion 2]
```

---

#### Deliverable Specification

**File Name:** `taxonomy-design.md`

**Location:** Repository root or `/resources`

**Quality Criteria:**
- [ ] Design principles documented
- [ ] Categories match your mental model
- [ ] Naming convention clearly defined
- [ ] Full structure mapped out

---

### Exercise 6.2: Reorganize Your Repository

**Duration:** 25 minutes

**Purpose:**
Implement your taxonomy design by reorganizing your actual repository.

---

#### Instructions

**Step 1: Create folder structure**
Make all directories according to your taxonomy.

**Step 2: Add folder READMEs**
Each folder should have a README explaining:
- What belongs in this folder
- Naming expectations
- Examples

**Step 3: Move and rename templates**
Apply your naming convention to all templates.

**Step 4: Add metadata headers**
Add to each template:
```markdown
---
title: [Descriptive title]
category: [path/to/category]
tags: [tag1, tag2, tag3]
version: 1.0
last_updated: [date]
---
```

**Step 5: Commit changes**
Use meaningful commit messages describing the reorganization.

---

#### Deliverable Specification

**Deliverable:** Reorganized repository

**Quality Criteria:**
- [ ] Folder structure matches taxonomy design
- [ ] All templates renamed consistently
- [ ] Metadata headers on all templates
- [ ] Folder READMEs present
- [ ] Meaningful commit messages

---

### Exercise 6.3: Create Template Index

**Duration:** 15 minutes

**Purpose:**
Build a discovery tool - a central document listing all templates.

---

#### Instructions

Create `template-index.md`:

```markdown
# Template Index

*Last updated: [Date]*
*Total templates: [Number]*

## Quick Navigation
- [Category 1](#category-1)
- [Category 2](#category-2)
- [Category 3](#category-3)

---

## Category 1

### Subcategory A

| Template | Purpose | Best For | Tags |
|----------|---------|----------|------|
| [template-name](path) | Brief description | Scenario | tags |

### Subcategory B

| Template | Purpose | Best For | Tags |
|----------|---------|----------|------|
| [template-name](path) | Brief description | Scenario | tags |

---

## How to Use This Index

### Finding Templates
1. Browse by category above
2. Search page (Ctrl+F) for keywords
3. Look at tags for related templates

### Adding New Templates
1. Place in appropriate category folder
2. Follow naming convention
3. Add metadata header
4. Update this index

### Template Not Found?
If no template exists for your need:
1. Check similar templates
2. Create new using appropriate base
3. Add to index after creation
```

---

#### Deliverable Specification

**File Name:** `template-index.md`

**Location:** Repository root or `/templates`

**Quality Criteria:**
- [ ] All templates listed
- [ ] Links work correctly
- [ ] Descriptions are helpful
- [ ] Usage instructions included

---

## Templates & Resources

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Information Architecture | Article | [usability.gov](https://www.usability.gov/what-and-why/information-architecture.html) | IA concepts |
| File Naming Best Practices | Guide | [Stanford Library](https://library.stanford.edu/research/data-management-services/data-best-practices/best-practices-file-naming) | Naming conventions |
| GitHub Search | Documentation | [docs.github.com](https://docs.github.com/en/search-github/searching-on-github/searching-code) | Search syntax |

---

## Self-Assessment

### Exit Criteria Checklist

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Design appropriate taxonomy | Exercise 6.1 completed | ☐ |
| 2 | Apply naming conventions | Exercise 6.2 templates renamed | ☐ |
| 3 | Add metadata headers | All templates have headers | ☐ |
| 4 | Create template index | Exercise 6.3 completed | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 6.1 | `taxonomy-design.md` | Repository | ☐ |
| Exercise 6.2 | Reorganized structure | Repository | ☐ |
| Exercise 6.3 | `template-index.md` | Repository | ☐ |

---

## Looking Ahead

### Next Week Preview: Week 7 - Block 1 Capstone Preparation

**Focus:**
Completing all capstone components, finalizing `style.json`, task priority matrix.

**How It Builds on This Week:**
Your organized repository IS a capstone requirement. The structure you create this week is evaluated.

**To Prepare:**
- [ ] Complete all Week 6 exercises
- [ ] Ensure all templates have metadata
- [ ] Review capstone requirements
- [ ] Identify any gaps in your library

---

## Glossary

| Term | Definition |
|------|------------|
| **Taxonomy** | Classification system for organizing content |
| **Metadata** | Structured information about a template (title, tags, etc.) |
| **Template Index** | Central document listing all templates |
| **Naming Convention** | Consistent rules for file names |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [← Previous Week](../week-5/participant-guide.md) | **Week 6** | [Next Week →](../week-7/participant-guide.md)
