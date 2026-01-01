# **INSTRUCTOR GUIDE: BLOCK 1 WEEK 5**
## **GitHub Collaboration & Documentation**

**Block:** 1: AI Prompting Mastery
**Week:** 5 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Pull request workflow, AI-assisted documentation, repository structure |
| **Difficulty Level** | Medium |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Yes - Pull request creation and AI documentation generation |
| **Tech Setup Needed** | GitHub account, AI platform for documentation demo |
| **Common Challenges** | PR workflow confusion, AI documentation requiring significant editing |

---

## Navigation

**Block Navigation:** [← Week 4 Instructor Guide](../week-4/instructor-guide.md) | **Week 5** | [Week 6 Instructor Guide →](../week-6/instructor-guide.md)

**Related Materials:**
- [Week 5 Presentation](presentation.md)
- [Week 5 Participant Guide](participant-guide.md)
- [Block 1 Main Document](../block-1.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 5 materials | ☐ |
| Test demo | Create a test PR in your own repo | ☐ |
| Prepare doc prompt | Have AI documentation prompt ready | ☐ |
| Check resources | Verify GitHub documentation links work | ☐ |
| Review previous | Check Week 4 rubric submissions | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice PR workflow demo | ☐ |
| Prepare materials | GitHub test repo ready, AI platform open | ☐ |
| Check participant progress | Review who completed Week 4 rubrics | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, GitHub, AI platform | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Ask about LLM-as-judge experience | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 5 min | Opening | Recap Week 4, preview collaboration | Set context |
| 0:05 | 7 min | Segment 1 | Why Collaboration Matters | Motivation |
| 0:12 | 13 min | Segment 2 | Pull Request Workflow | Core technique |
| 0:25 | 15 min | Segment 3 | AI-Assisted Documentation | Practical skill |
| 0:40 | 5 min | Segment 4 | Repo Structure + Close | Best practices + homework |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Shorten PR workflow to concept + quick demo
- Reference GitHub docs for detailed steps
- Minimize repo structure section

**If Running Ahead:**
- Spend more time on documentation prompts
- Show multiple documentation examples
- Take deeper questions about collaboration

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Why Collaboration | 0:12 | Keep brief, motivation clear |
| End PR Workflow | 0:25 | Must allow time for documentation |
| Start Closing | 0:40 | Can integrate repo structure into close |

---

## Session Delivery Guide

### Opening (5 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants back
2. Quick recap of Week 4: quality rubrics, LLM-as-judge
3. Preview today's shift to collaboration and documentation
4. Set expectations: practical GitHub and documentation skills

**Opening Script:**
> "Welcome to Week 5. Last week we built quality systems - rubrics and LLM-as-judge. Today we're shifting to collaboration and documentation. How do you work with others on prompts? How do you document templates so others can use them? These are the skills that take you from individual contributor to team enabler."

**Engagement Opportunity:**
> "Quick question: How many of you have collaborated with someone else on a document or project using GitHub or similar tools?"

[Wait for responses - gauge experience level]

---

### Segment 1: Why Collaboration Matters (7 minutes)

**Learning Objective:** Understand the value of structured collaboration on prompt development

**Slides:** 4-5

#### Content Delivery

**Key Point 1: The Evolution**
- Main message: We've moved from personal development to shareable work
- Visual progression: Weeks 1-4 personal → Week 5+ team-ready
- Participant relevance: Templates are only valuable if others can use them

**Key Point 2: Benefits of Proper Documentation**
- Main message: Future you and others need to understand your work
- Example to use: Coming back to a template 3 months later
- Institutional knowledge preservation

**Key Point 3: GitHub as Collaboration Platform**
- Main message: Not just storage - it's a workflow for safe changes
- Key insight: Review before merge prevents mistakes

#### Facilitation Notes

**Transition to Segment 2:**
> "GitHub isn't just for storing files. It has a whole workflow for collaborating safely. Let's learn the pull request pattern."

---

### Segment 2: Pull Request Workflow (13 minutes)

**Learning Objective:** Create and manage pull requests for safe collaboration

**Slides:** 6-9

#### Content Delivery

**Key Point 1: What Is a Pull Request**
- Main message: A proposed change that can be reviewed before merging
- Analogy: "Like sending a draft for approval before publishing"
- Why it matters: Safe way to make changes

**Key Point 2: The Workflow**
- Main message: Branch → Changes → PR → Review → Merge
- Step by step through the process
- Emphasis on review step

**Key Point 3: PR Description Best Practices**
- Main message: Good descriptions make review easier
- Show the template
- Connect to Exercise 5.1

#### Demo Instructions

**Demo Duration:** 5 minutes

**Setup Required:**
- Test repository with some content
- GitHub web interface ready

**Demo Steps:**
1. Create a new branch from main
2. Make a small change (edit a file)
3. Start a pull request
4. Write description using template
5. Show the diff view
6. Merge the PR

**Demo Talking Points:**
> "Watch - I'm creating a branch first. This is a copy of main where I can make changes safely..."
> "Now I'll open a pull request. This is asking to merge my changes..."
> "See the diff view? Red is removed, green is added. This is what reviewers look at."

---

### Segment 3: AI-Assisted Documentation (15 minutes)

**Learning Objective:** Use AI to create and improve documentation for templates

**Slides:** 10-13

#### Content Delivery

**Key Point 1: Documentation Types**
- Main message: Different docs for different purposes
- README, usage guides, examples, changelog
- Key insight: Good documentation enables reuse

**Key Point 2: AI Documentation Prompts**
- Main message: AI can accelerate documentation writing
- Show README generation prompt
- Show template documentation prompt
- Caution: Human review essential

**Key Point 3: Self-Documenting Prompts**
- Main message: Include documentation in the template itself
- Headers explain purpose
- Comments clarify complex sections

#### Demo Instructions

**Demo Duration:** 5 minutes

**Setup Required:**
- A template file ready to document
- AI platform open

**Demo Steps:**
1. Show a template without documentation
2. Use AI documentation prompt
3. Show generated documentation
4. Point out what needs human editing

**Demo Talking Points:**
> "Here's a template with no documentation. Let me ask AI to document it..."
> "Look at what it generated - structure, usage, variables. Good start."
> "But see here? This needs editing. AI guessed at the purpose. You need to verify and refine."

---

### Segment 4: Repository Structure + Close (5 minutes)

**Learning Objective:** Understand best practices for repository organization

**Slides:** 14-17

#### Content Delivery

**Key Point 1: Recommended Structure**
- Main message: Consistent structure scales
- Show recommended folder organization
- Naming conventions

**Key Point 2: Documentation in Folders**
- Main message: Each folder needs a README
- Explain what's in the folder
- Help discovery

#### Closing

**Homework Preview:**

**Script:**
> "Three exercises this week totaling 60 minutes.
>
> Exercise 5.1 is creating a pull request - 20 minutes. You'll create a branch, make changes, open and merge a PR.
> Exercise 5.2 is AI-generated README - 25 minutes. Create comprehensive documentation for your repository.
> Exercise 5.3 is documenting one template - 15 minutes. Full documentation for your best template.
>
> These exercises prepare your repository for the capstone. Good documentation makes everything easier."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Why use branches instead of just editing directly?**
A: Branches let you make changes without affecting the main version. If your changes have problems, main is unaffected. It's like drafting in a separate document before replacing the original.

**Q: Do I need to use PRs if I'm working alone?**
A: Not strictly, but it's good practice. PRs create a record of what changed and why. Even for solo work, they help you review your own changes.

**Q: How much documentation is enough?**
A: Enough that someone else (or future you) can use the template without asking questions. If they need to contact you to understand it, add more documentation.

### Technical Questions

**Q: What if I make a mistake in a PR?**
A: You can update a PR by making more commits to the branch. You can also close a PR without merging if you want to start over.

**Q: Can AI documentation be wrong?**
A: Yes - AI guesses at purpose, usage, and context. Always review and edit AI-generated documentation. Use it as a starting point, not the final product.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| GitHub not loading | Use prepared screenshots | Walk through conceptually |
| PR creation fails | Check branch settings | Demo on different repo |
| AI doc generation poor | Have backup example ready | Show editing process |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| GitHub workflow confusion | Mixing branch/PR/merge | Use filing analogy |
| PR anxiety | "What if I break something?" | Reassure - PRs are safe |
| Documentation seems tedious | "This is a lot of work" | Emphasize future time savings |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 5.1 | Merged pull request | GitHub PR history |
| 5.2 | Updated `README.md` | Repository root |
| 5.3 | Documented template | Templates folder |

### Progress Check Approach

**How to Verify Completion:**
- Check for merged PR in participant's repo
- Verify README is comprehensive
- Confirm template documentation has all sections

---

## Week-Specific Notes

### What Makes This Week Unique

- **Collaboration focus**: First time addressing team/sharing aspects
- **GitHub deepening**: Beyond basics to workflow
- **Documentation emphasis**: Often neglected, highly valuable
- **Capstone preparation**: Repository organization matters

### Dependencies

**Builds On:**
- Week 1: Initial GitHub setup
- Week 3: Basic commits and structure
- Week 4: Quality rubrics (referenced in documentation)

**Sets Up:**
- Week 6: Organization and taxonomy
- Week 7-8: Capstone requires documented templates

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Pull requests are drafts for review - safe way to make changes"
2. "Documentation is a gift to future you - invest now, save later"
3. "AI accelerates documentation - but human review is essential"

### If You Only Have Time For One Thing

AI-assisted documentation. PR workflow can be learned from GitHub docs, but understanding how to use AI for documentation is the unique skill.

---

**Navigation:** [← Week 4 Instructor Guide](../week-4/instructor-guide.md) | **Week 5** | [Week 6 Instructor Guide →](../week-6/instructor-guide.md)
