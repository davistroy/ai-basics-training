# Week 5: GitHub Collaboration & Documentation

**Block:** 1 - AI Prompting Mastery
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Week 4 exercises completed
- [ ] Quality rubric created
- [ ] LLM-as-judge pattern tested
- [ ] Active GitHub repository

## Exit Criteria

- [ ] GitHub collaboration workflow understood
- [ ] Can create and merge pull requests
- [ ] AI-assisted documentation created
- [ ] Repository documentation complete
- [ ] README with usage instructions

---

## Workshop Content (45 minutes)

### Segment 1: Why Collaboration Matters (7 min)

**The evolution:**
- Week 1-4: Personal prompt development
- Week 5+: Sharing and collaborating
- Block 2-3: Team deployment

**Benefits of proper documentation:**
- Future you understands past work
- Others can use your prompts
- Institutional knowledge preserved
- Quality maintained at scale

**GitHub as collaboration platform:**
- Not just storage - it's a workflow
- Built for team coordination
- Industry standard for code and content

### Segment 2: Pull Request Workflow (13 min)

**What is a Pull Request (PR)?**
- A proposed change to the repository
- Request to "pull" your changes into the main version
- Enables review before merging

**The workflow:**
```
1. Create branch (copy of main)
2. Make changes on branch
3. Open Pull Request
4. Review and discuss
5. Merge into main
```

**Creating a branch (web interface):**
1. Go to repository
2. Click branch dropdown (shows "main")
3. Type new branch name (e.g., "add-email-template")
4. Click "Create branch"

**Opening a Pull Request:**
1. Make changes on your branch
2. Click "Pull requests" tab
3. Click "New pull request"
4. Select your branch → main
5. Add title and description
6. Click "Create pull request"

**PR description template:**
```markdown
## Summary
[What this PR adds/changes]

## Changes
- [Change 1]
- [Change 2]

## Testing
- [ ] Tested prompt with [scenario]
- [ ] Validated JSON syntax
- [ ] Checked formatting

## Notes
[Any additional context]
```

**Merging:**
1. Review changes in "Files changed" tab
2. If approved, click "Merge pull request"
3. Delete branch (cleanup)

### Segment 3: AI-Assisted Documentation (15 min)

**Documentation types for prompts:**
1. **README** - Overview and quick start
2. **Usage guides** - Detailed instructions
3. **Examples** - Sample inputs and outputs
4. **Changelog** - What changed and when

**Using AI to write documentation:**

**README generation prompt:**
```markdown
Create a README.md for an AI prompt template repository.

## Context
Repository name: [name]
Purpose: [what it contains]
Primary audience: [who will use it]
Key contents: [list of main files/folders]

## README Should Include
1. Clear title and description
2. Quick start (3-5 steps to use)
3. Repository structure overview
4. Prerequisites
5. Usage examples
6. Contributing guidelines (optional)
7. License (if applicable)

## Tone
Professional but accessible, assuming reader is [experience level]
```

**Template documentation prompt:**
```markdown
Write documentation for this prompt template:

## Template
---
[Paste the template]
---

## Documentation Needed
1. **Purpose:** What this template does
2. **When to use:** Specific scenarios
3. **Variables:** What needs to be filled in (mark with [brackets])
4. **Example:** Complete example with filled variables
5. **Tips:** Best practices for use
6. **Common issues:** Problems and solutions

Format as clear Markdown with headers.
```

**Self-documenting prompts:**
- Include purpose in prompt header
- Comment complex sections
- Version number in filename or header

### Segment 4: Repository Structure Best Practices (10 min)

**Recommended structure:**
```
ai-prompt-library/
├── README.md              # Overview and quick start
├── CHANGELOG.md           # Version history
├── style.json             # Your style configuration
│
├── templates/             # Reusable prompt templates
│   ├── README.md          # Templates overview
│   ├── email/
│   │   ├── formal-response.md
│   │   └── meeting-request.md
│   ├── analysis/
│   │   └── data-summary.md
│   └── writing/
│       └── blog-post.md
│
├── rubrics/               # Quality evaluation rubrics
│   ├── email-quality.md
│   └── report-quality.md
│
├── examples/              # Sample inputs and outputs
│   └── email-examples.md
│
└── resources/             # Reference materials
    └── platform-tips.md
```

**File naming conventions:**
- Use lowercase with hyphens: `email-template.md`
- Be descriptive: `client-proposal-formal.md`
- Include version if needed: `proposal-v2.md`

**Documentation in folders:**
- Each folder should have a README
- Explain what's in the folder
- List contents with brief descriptions

---

## Self-Paced Exercises (60 minutes total)

### Exercise 5.1: Create a Branch and Pull Request (20 minutes)

*Practice the collaboration workflow*

1. **Create a new branch:**
   - Go to your repository on GitHub
   - Click the branch dropdown (shows "main")
   - Type: `add-week5-docs`
   - Click "Create branch: add-week5-docs"

2. **Make changes on your branch:**
   - Add a new file or edit an existing one
   - Could be: new template, updated README, new rubric
   - Make at least 2 separate commits

3. **Open a Pull Request:**
   - Click "Pull requests" tab
   - Click "New pull request"
   - Base: main ← Compare: add-week5-docs
   - Add title: "Add Week 5 documentation updates"
   - Add description using the template from the workshop
   - Create the pull request

4. **Review and merge:**
   - Look at the "Files changed" tab
   - Add a comment on one of the changes
   - Merge the pull request
   - Delete the branch

**Deliverable:** Screenshot or link showing merged pull request

---

### Exercise 5.2: AI-Generated README (25 minutes)

*Create comprehensive repository documentation*

1. **Inventory your repository:**
   - List all files and folders
   - Note the purpose of each
   - Identify your most important templates

2. **Generate README with AI:**

```markdown
Create a professional README.md for my AI prompt library repository.

## Repository Contents
[List your actual files and folders with descriptions]

## My Details
- Repository name: [your name]
- Primary use: [what you use prompts for]
- Audience: [just you, team, public]

## Requirements
1. Engaging introduction explaining the purpose
2. Clear "Getting Started" section (numbered steps)
3. Repository structure with file descriptions
4. At least one usage example
5. Prerequisites section (what users need)
6. Section on how to customize templates
7. Professional tone but not overly formal

## Additional
- Use emojis sparingly for visual interest
- Include badges if relevant (optional)
- Add "About" section with your context
```

3. **Refine the output:**
   - Check all file references are accurate
   - Add/remove sections as needed
   - Ensure examples work

4. **Commit to repository:**
   - Replace your current README (or create if missing)
   - Write meaningful commit message

**Deliverable:** Updated `README.md` in your repository

---

### Exercise 5.3: Document One Template (15 minutes)

*Create thorough documentation for a single template*

1. Choose your best prompt template from previous weeks

2. Create comprehensive documentation:

```markdown
# [Template Name]

## Purpose
[2-3 sentences on what this template does]

## When to Use
- [Scenario 1]
- [Scenario 2]
- [Scenario 3]

## Template
\`\`\`markdown
[Your actual template with [VARIABLE] placeholders marked]
\`\`\`

## Variables

| Variable | Description | Example |
|----------|-------------|---------|
| [VAR1] | [What to put here] | [Example value] |
| [VAR2] | [What to put here] | [Example value] |

## Example Usage

### Input
[Show template filled in with real values]

### Output
[Show actual AI response]

## Tips for Best Results
1. [Tip 1]
2. [Tip 2]
3. [Tip 3]

## Common Issues

| Issue | Solution |
|-------|----------|
| [Problem 1] | [How to fix] |
| [Problem 2] | [How to fix] |

## Related Templates
- [Link to related template 1]
- [Link to related template 2]

## Version History
- v1.0 (Date): Initial version
- v1.1 (Date): [What changed]
```

3. Add to your repository in the appropriate location

**Deliverable:** Fully documented template in repository

---

## Key Takeaways

1. **Pull requests enable safe collaboration** - changes reviewed before merging
2. **AI can accelerate documentation** - but human review is essential
3. **Good structure scales** - organized repos are easier to maintain
4. **Documentation is a gift to future you** - invest time now, save time later
5. **Consistent naming and organization** reduce cognitive load

---

## Preparation for Week 6

- Complete all Week 5 exercises
- Think about: How would you organize 50+ templates?
- Consider: What categories make sense for your work?
- Next week: Prompt library organization and advanced patterns

---

## Resources

- [GitHub Pull Request Documentation](https://docs.github.com/en/pull-requests)
- [How to Write a Good README](https://www.makeareadme.com/)
- [Documentation Best Practices](https://www.writethedocs.org/guide/writing/beginners-guide-to-docs/)
- [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)
