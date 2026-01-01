# Week 6: Prompt Library Organization

**Block:** 1 - AI Prompting Mastery
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Week 5 exercises completed
- [ ] Pull request workflow understood
- [ ] Repository documentation created
- [ ] At least 5 templates in library

## Exit Criteria

- [ ] Prompt library organized with clear taxonomy
- [ ] Naming conventions established and documented
- [ ] Search and retrieval patterns understood
- [ ] Template metadata system created
- [ ] Library structure ready for scaling

---

## Workshop Content (45 minutes)

### Segment 1: The Organization Challenge (8 min)

**The problem at scale:**
- 5 templates: Easy to remember
- 20 templates: Starting to forget what you have
- 50+ templates: Can't find anything
- Team library: Complete chaos

**Symptoms of poor organization:**
- Recreating prompts you already have
- Can't find the "good" version
- Similar templates with slight differences
- No one knows what exists

**The goal:**
- Find any template in under 30 seconds
- Know immediately if a template exists
- Understand template purpose without opening it
- Enable team discovery and reuse

### Segment 2: Taxonomy Design (12 min)

**What is taxonomy?**
- Classification system for your prompts
- Hierarchical categories
- Consistent structure

**Approach 1: By deliverable type**
```
templates/
├── emails/
├── reports/
├── proposals/
├── documentation/
├── social-media/
└── analysis/
```

**Approach 2: By use case/workflow**
```
templates/
├── client-communication/
├── internal-updates/
├── research/
├── content-creation/
├── code-assistance/
└── data-processing/
```

**Approach 3: By audience**
```
templates/
├── executive/
├── technical/
├── client-facing/
├── internal-team/
└── public/
```

**Hybrid approach (recommended):**
```
templates/
├── communication/
│   ├── client/
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

**Choosing your taxonomy:**
1. List all your current templates
2. Group naturally by how you think of them
3. Look for patterns in groupings
4. Create max 3 levels of hierarchy
5. Document the structure

### Segment 3: Naming Conventions (10 min)

**Why naming matters:**
- Names are primary discovery method
- Consistent naming = predictable finding
- Names survive moves and reorganization

**Naming pattern:**
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

**Naming rules:**
1. **Lowercase always** - Avoids OS conflicts
2. **Hyphens for spaces** - No spaces or underscores
3. **Most general → most specific** - Aids sorting
4. **No abbreviations** - Unless universally understood
5. **Action-oriented when possible** - Shows what it does

**Versioning in names:**
- For active iteration: `template-name-v2.md`
- For archival: Move to `archive/` folder
- For dated versions: `template-name-2024-01.md`

**Anti-patterns:**
```
❌ finalFINAL_v3_REAL.md
❌ New Template (2).md
❌ email template.md
❌ TempV2Final.md
✓ email-client-proposal-v2.md
```

### Segment 4: Metadata and Discovery (10 min)

**Template header metadata:**
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

# Client Proposal Email Template
...
```

**Creating a template index:**
```markdown
# Template Index

## Communication

### Client
| Template | Purpose | Tags | Last Updated |
|----------|---------|------|--------------|
| [formal-email](path) | Formal client correspondence | formal, client | 2024-12-15 |
| [proposal-response](path) | Responding to proposals | proposal, sales | 2024-12-10 |

### Internal
| Template | Purpose | Tags | Last Updated |
|----------|---------|------|--------------|
| [status-update](path) | Weekly status updates | status, internal | 2024-12-01 |
```

**Discovery methods:**
1. **Browse structure** - Navigate folders
2. **Search by name** - Use GitHub search or local find
3. **Search by tag** - Grep for tags in headers
4. **Index lookup** - Consult template index

**AI-assisted discovery:**
```markdown
I'm looking for a template to [task description].

Here's my template index:
[Paste index]

Which template(s) would be most appropriate?
Suggest modifications if no exact match exists.
```

### Segment 5: Maintenance Workflows (5 min)

**Regular maintenance:**
- Weekly: Add new templates with proper naming
- Monthly: Review and update index
- Quarterly: Audit for duplicates and outdated templates

**Template lifecycle:**
```
Draft → Active → Deprecated → Archived
```

**Deprecation process:**
1. Mark as deprecated in metadata
2. Link to replacement template
3. Keep available for reference
4. Archive after transition period

**Deduplication:**
- Regularly search for similar templates
- Merge variations into parameterized single version
- Use examples rather than separate templates

---

## Self-Paced Exercises (60 minutes total)

### Exercise 6.1: Design Your Taxonomy (20 minutes)

*Create a sustainable organization system*

1. **Inventory current templates:**
   - List every template you have
   - Note what each is used for
   - Identify natural groupings

2. **Design your taxonomy:**

```markdown
# My Prompt Library Taxonomy

## Design Principles
- [Principle 1: e.g., "Organize by use case, not format"]
- [Principle 2: e.g., "Max 3 levels deep"]
- [Principle 3: e.g., "Category names match my mental model"]

## Structure

### Top-Level Categories
1. **[Category 1]** - [Description of what goes here]
2. **[Category 2]** - [Description of what goes here]
3. **[Category 3]** - [Description of what goes here]

### Full Structure
\`\`\`
templates/
├── [category-1]/
│   ├── [subcategory-a]/
│   │   ├── [template-example-1.md]
│   │   └── [template-example-2.md]
│   └── [subcategory-b]/
├── [category-2]/
│   └── ...
└── [category-3]/
    └── ...
\`\`\`

## Naming Convention
[Document your naming rules]

## When to Create New Categories
- [Criteria 1]
- [Criteria 2]
```

**Deliverable:** `taxonomy-design.md`

---

### Exercise 6.2: Reorganize Your Repository (25 minutes)

*Implement your new structure*

1. **Create the folder structure:**
   - Make all directories according to your taxonomy
   - Add `README.md` to each folder explaining contents

2. **Move and rename templates:**
   - Apply your naming convention
   - Move to appropriate categories
   - Update any internal links

3. **Add metadata headers:**
   To each template, add:
   ```markdown
   ---
   title: [Descriptive title]
   category: [path/to/category]
   tags: [tag1, tag2, tag3]
   version: 1.0
   last_updated: [date]
   related: [related-template.md]
   ---
   ```

4. **Commit changes:**
   - Use meaningful commit message
   - Consider one commit per major change

**Deliverable:** Reorganized repository with consistent structure

---

### Exercise 6.3: Create Template Index (15 minutes)

*Build a discovery tool*

1. **Create template-index.md:**

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
| [template-name](link) | Brief description | Specific scenario | tag1, tag2 |

### Subcategory B

| Template | Purpose | Best For | Tags |
|----------|---------|----------|------|
| [template-name](link) | Brief description | Specific scenario | tag1, tag2 |

---

## Category 2
[Repeat structure]

---

## How to Use This Index

### Finding Templates
1. Browse by category above
2. Search this page (Ctrl/Cmd+F) for keywords
3. Look at tags for related templates

### Adding New Templates
1. Place in appropriate category folder
2. Follow naming convention: [pattern]
3. Add metadata header
4. Update this index

### Template Not Found?
If you need a template that doesn't exist:
1. Check similar templates for adaptation
2. Create new using [base-template.md]
3. Add to index after creation
```

2. **Populate with all your templates**

3. **Add to repository root or templates folder**

**Deliverable:** `template-index.md` in repository

---

## Key Takeaways

1. **Good taxonomy enables discovery** - Find templates in seconds
2. **Naming conventions prevent chaos** - Consistency compounds
3. **Metadata powers advanced search** - Tags and categories together
4. **Index serves as single source of truth** - One place to find everything
5. **Maintenance is ongoing** - Schedule regular review

---

## Preparation for Week 7

- Complete all Week 6 exercises
- Ensure all templates have metadata headers
- Review your library: anything missing for your capstone?
- Next week: Capstone preparation and integration

---

## Resources

- [Information Architecture Basics](https://www.usability.gov/what-and-why/information-architecture.html)
- [File Naming Best Practices](https://library.stanford.edu/research/data-management-services/data-best-practices/best-practices-file-naming)
- [GitHub Search Syntax](https://docs.github.com/en/search-github/searching-on-github/searching-code)
