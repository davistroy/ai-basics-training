# **BLOCK 1: AI Prompting Mastery**

**Version:** 1.0
**Last Updated:** 2025-01-01
**Status:** Active

---

**Navigation:** [← README](README.md) | **Block 1** | [Block 2 →](block-2.md) | [Block 3 →](block-3.md)

---

## **8 Weeks | 45 min live + 60 min homework per week**

-----

## **Week 1: Markdown Fundamentals & Structured Prompting**

### **Entry Criteria**

- [ ] Access to AI tool (Claude, ChatGPT, or Copilot)
- [ ] Ability to create/edit text files
- [ ] One real work deliverable in mind to improve

### **Exit Criteria**

- [ ] Can write prompts using Markdown structure (headers, lists, code blocks, tables)
- [ ] Can use ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework
- [ ] Understands prompt injection prevention with code blocks
- [ ] Identified top 3 high-value automation candidates

-----

### **Workshop Content (45 minutes)**

**Segment 1: Program Introduction & Framing (10 min)**

- Welcome and objectives
- **“Engineer-Consultant Hybrid” framing:** “You’re becoming hybrid professionals who combine strategy with systematic thinking”
- **Maturity progression explicit:** Show journey from Level 0 → Level 3
  - Level 0: Ad-hoc AI usage (where you are)
  - Level 1: Templated workflows (end of Block 1)
  - Level 2: Workflow engineering (end of Block 2)
  - Level 3: Automation architecture (end of Block 3)
- Overview of three blocks, time commitment, certification points

**Segment 2: Why Markdown Matters for AI (10 min)**

- **Problem:** “Wall of text” prompts produce inconsistent results
- **Solution:** Markdown provides structure AI understands better
- Demo: Same prompt with/without Markdown structure - show quality difference
- **Core principle:** “Structure = clarity for AI = better outputs”

**Segment 3: Essential Markdown Syntax (15 min)**

- **Headers (#, ##, ###):** Hierarchy and importance signaling
- **Lists (- and 1.):** When to use unordered vs. ordered
- **Emphasis (**bold**, *italic*):** Highlighting constraints
- **Code blocks (```):** THE CRITICAL TECHNIQUE
  - **Prompt injection prevention:** Isolating data from instructions
  - Demo: Show prompt injection attack failing with code blocks
  - Rule: “Always wrap external data in code blocks”
- **Tables:** For comparisons, pricing, timelines (show syntax)

**Segment 4: ASK-CONTEXT-CONSTRAINTS-EXAMPLE Framework (10 min)**

- **The four-section structure every prompt needs:**
  
  ```markdown
  ## ASK
  What you want the AI to do
  
  ## CONTEXT
  Background information needed
  
  ## CONSTRAINTS
  Requirements, format, tone, limits
  
  ## EXAMPLE
  Sample showing what you want
  ```
- **Live demo:** Build a proposal prompt using this framework
- **Why it works:** Forces completeness, prevents vague requests
- Participants take notes on framework

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 1.1: Recurring Task Identification (20 minutes)**

*Identify your highest-value automation candidates*

**Step 1:** List 10-15 tasks you do regularly

**Step 2:** Rate each task (1-5 scale):

- Frequency: How often? (1=rarely, 5=daily)
- Time: How long? (1=<15min, 5=>2hrs)
- Repetitiveness: How similar each time? (1=always different, 5=exactly same)
- Value: How important? (1=low, 5=critical)
- AI-Suitable: Could AI help? (1=no, 5=definitely)

**Step 3:** Calculate priority score:

```
Priority = (Frequency × Time × Repetitiveness) + (Value × AI-Suitable)
```

**Step 4:** Identify your top 3 highest-scoring tasks

**Step 5:** Quick Impact Estimate

For each of your top 3 tasks, estimate the potential time savings:

```markdown
# Quick Impact Estimate

| Task | Current Time | Frequency | Hours/Month | With AI (est.) | Monthly Savings |
|------|--------------|-----------|-------------|----------------|-----------------|
| [Task 1] | __ min | __x/week | __ hrs | __ min | __ hrs |
| [Task 2] | __ min | __x/week | __ hrs | __ min | __ hrs |
| [Task 3] | __ min | __x/week | __ hrs | __ min | __ hrs |
| **Total** | | | __ hrs | | __ hrs |

Projected annual time savings: __ hours
```

> **Why estimate now?** Tracking your "before" state helps you measure real impact later. By Block 3, you'll calculate actual ROI with measured data. This baseline makes that possible.

**Deliverable:** Completed task priority matrix with impact estimates (use provided template)

**Resources:**

- Task Priority Matrix Template (see Appendix A)

-----

**Exercise 1.2: Markdown Practice (20 minutes)**

*Build muscle memory with Markdown syntax*

1. Complete interactive tutorial: [Markdown Tutorial](https://www.markdowntutorial.com/) (10 min)
1. Create `markdown-practice.md` file with examples of:

- Three header levels (H1, H2, H3)
- Unordered and ordered lists
- Bold and italic emphasis
- Code block (fenced with ```)
- A table with 3 columns and 4 rows
- A combination: List with bold items

1. Use online previewer to verify: [Dillinger](https://dillinger.io/)

**Deliverable:** `markdown-practice.md` file

**Resources:**

- [Markdown Tutorial](https://www.markdowntutorial.com/)
- [Markdown Guide - Basic Syntax](https://www.markdownguide.org/basic-syntax/)
- [Dillinger - Online Markdown Editor](https://dillinger.io/)

-----

**Exercise 1.3: First Structured Prompt (20 minutes)**

*Apply ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework*

1. Choose one of your top 3 tasks from Exercise 1.1
1. Write a prompt using the framework:
   
   ```markdown
   ## ASK
   [What you want AI to create/analyze]
   
   ## CONTEXT
   [At least 3 specific details]
   
   ## CONSTRAINTS
   - [Requirement 1]
   - [Requirement 2]
   - [Format specification]
   
   ## EXAMPLE
   [Short sample of desired output style]
   ```
1. Test the prompt in your AI tool
1. Note what worked and what needs adjustment

**Deliverable:** Your first structured prompt (saved as `first-prompt.md`)

**Resources:**

- ASK-CONTEXT-CONSTRAINTS-EXAMPLE Template (see Appendix B)

-----

## **Week 2: Advanced Prompting + Platform Optimization**

### **Entry Criteria**

- [ ] Completed Week 1 exercises
- [ ] Can write basic Markdown-formatted prompts
- [ ] Familiar with ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework

### **Exit Criteria**

- [ ] Can use LLM-as-judge pattern for iteration
- [ ] Knows platform-specific optimizations for primary tool
- [ ] Understands cost optimization basics
- [ ] Created 2-3 working prompts for real deliverables

-----

### **Workshop Content (45 minutes)**

**Segment 1: The Iteration Problem (5 min)**

- **Common mistake:** Getting mediocre output and starting over
- **Better approach:** Using AI to improve its own output
- **Preview:** LLM-as-judge pattern

**Segment 2: LLM-as-Judge Pattern (15 min)**

- **The two-step workflow:**

1. Generate initial output
1. Prompt: “Evaluate your output against these criteria… score each 1-5… suggest 3 improvements… then revise”

- **Live demo:**
  - Generate a proposal section
  - Use LLM-as-judge to critique and improve
  - Show before/after quality
- **Why it works:**
  - AI can spot its own weaknesses if prompted
  - Faster than rewriting prompts
  - Teaches what “good” looks like

**Segment 3: Platform-Specific Optimization (15 min)**

- **Core principle:** Each AI platform has formatting preferences
- **Universal techniques (work everywhere):**
  - Code blocks for data isolation
  - Clear section headers
  - Examples showing desired format
  - Explicit constraints
- **Platform-specific techniques:**
  - **Claude:** XML tags (`<instructions>`, `<examples>`), prefilling responses
  - **ChatGPT:** System messages, JSON mode
  - **Copilot:** @mentions (`@workspace`), file references (`#file:`)
- **Your assignment:** Research YOUR platform’s optimizations

**Segment 4: Cost Optimization Basics (10 min)**

- **Why it matters:** AI costs scale with usage
- **Key techniques:**
  - Shorter, focused prompts (fewer tokens = lower cost)
  - Strategic use of examples (when needed, not always)
  - Avoid repetitive context
  - Choose right model for task (not always most expensive)
- **Example:** Show 40% cost reduction with no quality loss

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 2.1: Platform Optimization Research (20 minutes)**

*Discover techniques specific to your AI tool*

1. Identify your primary AI platform (Claude, ChatGPT, Copilot, or other)
1. Research 2-3 optimization techniques specific to that platform:

- Official documentation
- User forums/communities
- Prompt engineering guides

1. Document each technique:

- What it is
- How to use it
- When to use it
- Example

1. Test at least one technique with a prompt

**Deliverable:** `platform-optimizations.md` with your findings

**Resources:**

- [Anthropic Prompt Engineering Guide](https://docs.anthropic.com/claude/docs/prompt-engineering)
- [OpenAI Prompt Engineering Best Practices](https://platform.openai.com/docs/guides/prompt-engineering)
- [Microsoft Copilot Documentation](https://learn.microsoft.com/en-us/copilot/)

-----

**Exercise 2.2: LLM-as-Judge Practice (25 minutes)**

*Master the iteration workflow*

1. Using your prompt from Week 1 Exercise 1.3, generate an initial output
1. Create a self-evaluation prompt:
   
   ```markdown
   Evaluate the [deliverable] you just created against these criteria:
   1. [Criterion 1] - Score 1-5 and explain
   2. [Criterion 2] - Score 1-5 and explain
   3. [Criterion 3] - Score 1-5 and explain
   
   Based on your evaluation:
   - Suggest 3 specific improvements
   - Provide a revised version implementing those improvements
   ```
1. Run the evaluation prompt
1. Compare initial vs. revised output
1. Document:

- Initial quality scores
- Improvements identified
- Revised quality scores
- Your assessment of the technique

**Deliverable:** `llm-as-judge-results.md` with before/after comparison

-----

**Exercise 2.3: Cost-Efficient Prompting (15 minutes)**

*Learn to reduce costs without sacrificing quality*

1. Take one of your prompts
1. Count approximate words/tokens
1. Identify opportunities to shorten:

- Remove redundant context
- Consolidate similar instructions
- Use more concise language
- Remove unnecessary examples

1. Create shortened version
1. Test both versions - compare:

- Output quality (same? better? worse?)
- Estimated cost difference
- Time to generate

**Deliverable:** Cost comparison document showing original vs. optimized

-----

## **Week 3: JSON Fundamentals + GitHub Basics**

### **Entry Criteria**

- [ ] Completed Weeks 1-2
- [ ] 2-3 working prompts created
- [ ] GitHub account created (free tier)

### **Exit Criteria**

- [ ] Can read and create basic JSON structures
- [ ] Created personal `style.json` file
- [ ] GitHub repository initialized with folder structure
- [ ] Understands "promptware" concept (prompts as assets)
- [ ] Basic understanding of how templates will be automated in Block 2

-----

### **Workshop Content (45 minutes)**

**Segment 1: Why JSON for Consultants (8 min)**

- **Analogy:** JSON is a “digital form” - keys are questions, values are answers
- **Use cases:**
  - `style.json`: Brand consistency across outputs
  - Data structures: Organizing deliverable components
  - AI output format: Structured responses
- **Not coding:** You’re defining structure, not programming

**Segment 2: JSON Syntax Essentials (12 min)**

- **Keys and values:** `"key": "value"`
- **Data types:** Strings, numbers, booleans, arrays, objects
- **Structure:** Curly braces `{}`, brackets `[]`, quotes `""`
- **The comma pain:** Trailing commas break everything
- **Example:**
  
  ```json
  {
    "client_name": "Acme Corp",
    "budget": 150000,
    "timeline": "6 months",
    "deliverables": ["BRD", "Implementation Plan", "Training"]
  }
  ```

**Segment 3: Creating style.json (10 min)**

- **Purpose:** Single source of truth for brand/style
- **What to include:**
  
  ```json
  {
    "brand": {
      "primary_color": "#0066CC",
      "secondary_color": "#FF6B35",
      "fonts": ["Calibri", "Arial"],
      "logo_placement": "top-right"
    },
    "tone": {
      "descriptors": ["Professional", "Concise", "Data-driven"],
      "avoid": ["Jargon", "Overly casual", "Buzzwords"]
    },
    "document_standards": {
      "page_numbers": true,
      "footer_content": "Company Name | Confidential"
    }
  }
  ```
- **Using it:** “Apply my style.json to this output…”

**Segment 4: GitHub as Asset Repository + Looking Ahead (15 min)**

- **"Promptware" framing:** Prompts are company assets, not personal notes
- **Why GitHub:**
  - Version control (track changes)
  - Collaboration (team access)
  - Documentation (README files)
  - Professional standard
- **Basic workflow:**
  - Repository = project folder
  - Commit = save version
  - README = documentation
- **Quick demo:** Create repo, add file, commit, view history
- **Looking Ahead (2 min):**
  - "In Block 2, you'll connect these templates to automated workflows"
  - "Your organized GitHub library becomes the foundation for automation"
  - "The structure you build now pays dividends later"

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 3.1: Create Your style.json (25 minutes)**

*Define your brand/style standards*

1. Create a `style.json` file including:

- Brand colors (hex codes or names)
- Font preferences
- Tone descriptors (3-5 adjectives)
- Document formatting standards
- Things to avoid

1. Validate using JSONLint: [jsonlint.com](https://jsonlint.com/)
1. Test by prompting AI: “Using this style guide [paste JSON], write a one-paragraph company overview”
1. Document results: Did AI follow the style?

**Deliverable:** Valid `style.json` file + test results

**Resources:**

- style.json Template (see Appendix C)
- [JSONLint Validator](https://jsonlint.com/)
- [JSON.org - Introduction](https://www.json.org/)

-----

**Exercise 3.2: Initialize GitHub Repository (20 minutes)**

*Set up your prompt library foundation*

1. Sign up for GitHub (if not already): [github.com](https://github.com)
1. Create new repository:

- Name: `[YourName]-ai-prompts`
- Public or Private (your choice)
- Initialize with README

1. Create folder structure:
   
   ```
   /prompts
   /templates
   /workflows
   /resources
   ```
1. Add initial README.md:
   
   ```markdown
   # [Your Name]'s AI Prompt Library
   
   ## Purpose
   This repository contains reusable prompts, templates, and workflows
   for AI-assisted consulting work.
   
   ## Contents
   - `/prompts` - Individual prompt files
   - `/templates` - Deliverable templates
   - `/workflows` - Multi-step processes
   - `/resources` - Reference materials
   
   ## How to Use
   [To be documented as library grows]
   ```
1. Upload your `style.json` to `/resources` folder
1. Commit changes with message: “Initial repository setup”

**Deliverable:** GitHub repository URL

**Resources:**

- [GitHub Hello World Guide](https://docs.github.com/en/get-started/quickstart/hello-world)
- [GitHub Basic Writing and Formatting](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

-----

**Exercise 3.3: JSON Data Structure Design (15 minutes)**

*Structure a deliverable for AI generation*

1. Choose one deliverable type (proposal, SOW, assessment, etc.)
1. Design JSON structure capturing key components:
   
   ```json
   {
     "deliverable_type": "Proposal",
     "client_info": {
       "name": "",
       "industry": "",
       "size": ""
     },
     "project": {
       "scope": "",
       "timeline": "",
       "budget": 0
     },
     "sections": []
   }
   ```
1. Create example with sample data
1. Validate with JSONLint

**Deliverable:** `[deliverable]-structure.json` file

-----

## **Week 4: Quality Rubrics + Workflow Design**

### **Entry Criteria**

- [ ] Completed Weeks 1-3
- [ ] style.json created
- [ ] GitHub repository initialized
- [ ] 3+ working prompts developed (these will become templates)

### **Exit Criteria**

- [ ] Can create 5-point rubrics with explicit descriptions
- [ ] Rubrics created as deliverables for templates
- [ ] Understands quality gates in workflows
- [ ] Can write pseudocode for workflow logic
- [ ] Knows comparison gates (style.json matching)

-----

### **Workshop Content (45 minutes)**

**Segment 1: Defining Quality (8 min)**

- **The problem:** “Quality” is subjective without standards
- **The solution:** Explicit, measurable criteria
- **Quality dimensions:**
  - Accuracy (facts correct?)
  - Completeness (all sections present?)
  - Tone/style (matches brand?)
  - Client-specificity (tailored, not generic?)
  - Formatting (follows template?)

**Segment 2: 5-Point Rubric Structure (15 min)**

- **The format:**
  
  |Criterion|Excellent (5)|Good (4)     |Adequate (3) |Poor (2)     |Missing (1)  |
  |---------|-------------|-------------|-------------|-------------|-------------|
  |[Name]   |[Description]|[Description]|[Description]|[Description]|[Description]|
- **Example - Proposal Clarity:**
  - **Excellent (5):** Problem statement is specific, quantified, and directly tied to client pain points
  - **Good (4):** Problem stated clearly with most specifics present
  - **Adequate (3):** Problem mentioned but somewhat vague or generic
  - **Poor (2):** Problem unclear or not client-specific
  - **Missing (1):** No problem statement present
- **Live exercise:** Group creates one rubric criterion together

**Segment 3: Quality Gates + Pseudocode Thinking (12 min)**

- **Quality gates:** Checkpoints where you verify before proceeding
- **Types:**
  - Input validation: “Is data complete?”
  - Process gate: “Is AI generating correctly?”
  - Output validation: “Does output meet rubric?”
  - Human review: “Does expert approve?”
- **Pseudocode thinking:** Writing logic in plain English
  
  ```
  IF rubric_score >= 4 THEN
      Send to client
  ELSE IF rubric_score >= 3 THEN
      Flag for human review
  ELSE
      Regenerate with revised prompt
  END IF
  ```
- **Why it matters:** Foundation for automation in Blocks 2-3

**Segment 4: Comparison Gates (10 min)**

- **Concept:** Comparing output against standards
- **style.json matching:**
  - Does tone match descriptors?
  - Are brand colors referenced correctly?
  - Is formatting consistent?
- **Example matching:**
  - Does this look like our previous proposals?
  - Is structure similar to template?
- **Implementation:** Manual now, automated later

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 4.1: Create Quality Rubric (30 minutes)**

*Build evaluation framework for your key deliverable*

1. Choose your highest-priority deliverable
1. Identify 5-7 quality criteria specific to that deliverable
1. For each criterion, write descriptions for all 5 levels:

- Excellent (5 points)
- Good (4 points)
- Adequate (3 points)
- Poor (2 points)
- Missing (1 point)

1. Estimate weighting (which criteria matter most?)
1. Create in Markdown table format

**Deliverable:** `[deliverable]-quality-rubric.md` in GitHub

**Resources:**

- Quality Rubric Template (see Appendix D)
- Example rubrics (see Appendix E)

-----

**Exercise 4.2: Test Rubric Application (20 minutes)**

*Validate your rubric with real outputs*

1. Generate 2 versions of your deliverable using AI (different prompts or iterations)
1. Score each version against your rubric:

- Rate each criterion (1-5)
- Calculate total score
- Calculate weighted score if applicable

1. Document:

- Which criteria did AI excel at?
- Which fell short?
- What patterns did you notice?
- How would you adjust prompts to improve scores?

**Deliverable:** Rubric evaluation analysis document

-----

**Exercise 4.3: Workflow Logic Design (10 minutes)**

*Practice pseudocode thinking*

1. Choose a workflow you execute regularly
1. Map it with pseudocode including quality gates:
   
   ```
   START
   
   Gather client data
   IF data_complete = TRUE THEN
       Proceed to generation
   ELSE
       Request missing information
       STOP
   END IF
   
   Generate deliverable using prompt template
   
   Score output against rubric
   IF score >= 4 THEN
       Deliver to client
   ELSE IF score >= 3 THEN
       Human review required
   ELSE
       Regenerate with adjustments
   END IF
   
   END
   ```
1. Identify decision points and quality gates

**Deliverable:** Workflow pseudocode document

-----

## **Week 5: GitHub Collaboration & Documentation**

### **Entry Criteria**

- [ ] GitHub repository with content
- [ ] Created templates and rubrics
- [ ] Understanding of version control concept

### **Exit Criteria**

- [ ] Can create branches for improvements
- [ ] Can create and review pull requests
- [ ] Completed peer review exercise
- [ ] Documentation standard template applied
- [ ] CONTRIBUTING.md file created

-----

### **Workshop Content (45 minutes)**

**Segment 1: Why Branching Matters (8 min)**

- **The problem:** Editing directly can break working templates
- **The solution:** Branch strategy
- **Branches explained:**
  - `main` = production (approved, tested templates)
  - Feature branches = experimentation
  - Merge when ready
- **Analogy:** Main branch is your published work. Branches are drafts.

**Segment 2: Branch Workflow (12 min)**

- **The process:**

1. Create branch from main
1. Make improvements
1. Test changes
1. Create pull request (PR)
1. Review (self or peer)
1. Merge to main

- **Live demo:** Create branch, edit file, create PR, merge
- **Naming conventions:**
  - `feature/add-budget-section`
  - `fix/rubric-scoring-unclear`
  - `docs/improve-readme`

**Segment 3: Pull Requests & Peer Review (15 min)**

- **PR best practices:**
  - Clear title describing change
  - Description explaining:
    - What changed
    - Why
    - How to test
- **Peer review process:**

1. Partner creates PR
1. You review changes
1. Leave constructive comments
1. Discuss if needed
1. Approve or request changes
1. Partner merges when approved

- **Feedback template:**
  - ✅ What’s working well
  - 💡 Suggestions for improvement
  - ❓ Questions or clarifications needed

**Segment 4: Documentation Standards (10 min)**

- **Why document:** Makes templates reusable by others
- **Documentation template structure:**
  - Purpose
  - When to use / When NOT to use
  - How to use (step-by-step)
  - Input requirements
  - Output format
  - Customization tips
  - Known limitations
  - Version history
- **README hierarchy:**
  - Level 1: Repository overview
  - Level 2: Folder/section overviews
  - Level 3: Individual file documentation
- **CONTRIBUTING.md:** Guidelines for team contributions

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 5.1: Branch and Improve (20 minutes)**

*Practice safe experimentation*

1. Create new branch: `improve-[template-name]`
1. Make improvements to one template:

- Refine prompt wording
- Add new example
- Update rubric
- Improve documentation

1. Test changes (generate output, verify quality)
1. Commit with clear message describing change
1. Create pull request with description:

- What changed
- Why you made the change
- How to test it

**Deliverable:** Pull request created (don’t merge yet - for peer review)

-----

**Exercise 5.2: Peer Review Practice (25 minutes)**

*Give and receive constructive feedback*

**Part A: Review Partner’s PR (15 min)**

1. You’ll be paired with another participant
1. Review their pull request:

- Read the changes carefully
- Check documentation completeness
- Test the template if possible
- Leave 2-3 constructive comments

1. Use feedback template:

- What’s working well
- Suggestions for improvement
- Questions

**Part B: Respond to Feedback (10 min)**

1. Read feedback on your own PR
1. Respond to comments
1. Make adjustments if needed
1. Merge your PR to main

**Deliverable:** Completed peer review (comments given and received)

**Note:** Pairing will be coordinated via async channel

-----

**Exercise 5.3: Apply Documentation Standard (15 minutes)**

*Make templates professionally documented*

1. Choose one of your templates
1. Create comprehensive documentation using template:
   
   ```markdown
   # [Template Name]
   
   ## Purpose
   [What this template is for]
   
   ## When to Use
   - Use case 1
   - Use case 2
   
   ## When NOT to Use
   - Situation where this isn't appropriate
   
   ## How to Use
   1. Step 1
   2. Step 2...
   
   ## Input Requirements
   | Variable | Description | Example | Required? |
   |----------|-------------|---------|-----------|
   | CLIENT_NAME | Full legal name | "Acme Corp" | Yes |
   
   ## Output Format
   [Description of output]
   
   ## Customization Tips
   - Tip 1
   - Tip 2
   
   ## Known Limitations
   - Limitation 1
   
   ## Version History
   - v1.0 (YYYY-MM-DD): Initial version
   ```
1. Create CONTRIBUTING.md in repository root:

- How to contribute
- Quality standards
- Pull request process
- Who to contact

**Deliverable:** Documented template + CONTRIBUTING.md file

**Resources:**

- Documentation Standard Template (see Appendix F)
- CONTRIBUTING.md Template (see Appendix G)

-----

## **Week 6: Prompt Library Organization**

### **Entry Criteria**

- [ ] 3+ documented templates in repository
- [ ] Style.json and rubrics created
- [ ] Familiarity with README files

### **Exit Criteria**

- [ ] Complete README hierarchy (3 levels)
- [ ] Library organized by categories
- [ ] Client-facing vs. internal templates distinguished
- [ ] Quick-start guide created
- [ ] Understanding of how Block 1 work enables Block 2 automation

-----

### **Workshop Content (45 minutes)**

**Segment 1: Repository Organization Strategy (10 min)**

- **The challenge:** As library grows, findability becomes critical
- **Folder taxonomy options:**
  - By deliverable type: `/proposals`, `/assessments`, `/sows`
  - By function: `/generation`, `/analysis`, `/editing`
  - By client type: `/enterprise`, `/mid-market`, `/startup`
  - **Recommendation:** By deliverable type (most intuitive)
- **Naming conventions:**
  - Descriptive, consistent
  - No spaces (use hyphens)
  - Include version if needed
  - Example: `proposal-tech-consulting-v2.md`

**Segment 2: README Hierarchy (15 min)**

- **Three-level structure:**

**Level 1 - Repository README:**

```markdown
# AI Prompt Library

## Overview
Complete library of AI prompts, templates, and workflows for consulting work.

## Contents
- [Prompts](/prompts) - Individual reusable prompts
- [Templates](/templates) - Complete deliverable templates
- [Workflows](/workflows) - Multi-step processes
- [Resources](/resources) - Reference materials

## Quick Start
1. Browse templates by deliverable type
2. Copy template to use
3. Follow documentation in each template folder

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md)
```

**Level 2 - Folder READMEs:**

```markdown
# Templates

## Available Templates
- [Proposal](/templates/proposal) - Client proposals and RFP responses
- [SOW](/templates/sow) - Statements of Work
- [Assessment](/templates/assessment) - Client assessments

## Template Structure
Each template includes:
- Prompt file (.md)
- Data structure (.json)
- Quality rubric (.md)
- Documentation (README.md)
- Examples
```

**Level 3 - Template README:**

- Follows documentation standard from Week 5

**Segment 3: Client-Facing vs. Internal (10 min)**

- **Different quality standards:**
  - **Client-facing:** High polish, brand consistency critical, zero tolerance for errors
  - **Internal:** Functional first, speed prioritized, higher error tolerance
- **Different workflows:**
  - Client-facing: More quality gates, human review required
  - Internal: Fewer gates, faster iteration
- **Labeling strategy:** Tag templates as “client” or “internal”

**Segment 4: Block 2 Preview - Looking Ahead (10 min)**

- **What you've built:**
  - Organized template library with version control
  - Quality rubrics for consistent evaluation
  - Documentation standards for reusability
- **What's next in Block 2:**
  - Automating your templates into multi-step workflows
  - Adding quality gates that run automatically
  - Connecting workflows to external tools and data sources
  - Building systems that execute without manual prompting
- **Why your Block 1 work matters:**
  - Well-documented templates become workflow components
  - Quality rubrics become automated quality checks
  - GitHub organization enables team collaboration
- **The progression:** "You've learned to write excellent prompts. Next, you'll learn to orchestrate them."

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 6.1: Complete README Hierarchy (30 minutes)**

*Create all three levels of documentation*

1. **Update repository README** (Level 1):

- Overview of library
- Contents listing
- Navigation guide
- Quick start instructions
- Link to CONTRIBUTING.md
- Version history

1. **Create folder READMEs** (Level 2):

- One for `/prompts`
- One for `/templates`
- One for `/workflows`
- List contents, explain structure

1. **Verify Level 3** (individual templates):

- Ensure each template has documentation
- Check for completeness
- Update any missing sections

**Deliverable:** Complete 3-level README hierarchy

-----

**Exercise 6.2: Categorize and Label Templates (20 minutes)**

*Organize for discoverability*

1. Review all your templates
1. Categorize each as:

- **Client-facing** or **Internal**
- **Deliverable type** (proposal, assessment, etc.)
- **Maturity level** (draft, tested, production)

1. Add metadata to each template README:
   
   ```markdown
   **Type:** Client-facing
   **Category:** Proposal
   **Status:** Production-ready
   ```
1. Create index table in main README:
   
   |Template     |Type  |Category|Status|Link                       |
   |-------------|------|--------|------|---------------------------|
   |Tech Proposal|Client|Proposal|Prod  |[View](/templates/proposal)|

**Deliverable:** Categorized and labeled library with index

-----

**Exercise 6.3: Quick Start Guide (10 minutes)**

*Make library immediately usable by others*

1. Create `QUICK-START.md` in repository root
1. Include:

- “I need to create a [deliverable]” → Link to that template
- “I want to browse all templates” → Link to index
- “I want to contribute” → Link to CONTRIBUTING.md
- “I have a question” → Contact info / async channel

1. Add to main README as first section

**Deliverable:** QUICK-START.md file

-----

## **Week 7: Block 1 Capstone Preparation**

### **Entry Criteria**

- [ ] Completed Weeks 1-6
- [ ] Repository with organized templates, rubrics, documentation
- [ ] Style.json configured
- [ ] 3+ working templates with documentation

### **Exit Criteria**

- [ ] Capstone deliverables complete and ready to present
- [ ] Impact estimation documented
- [ ] All templates meet quality standards
- [ ] Repository professionally organized
- [ ] Ready for Block 1 evaluation

-----

### **Workshop Content (45 minutes)**

**Segment 1: Capstone Requirements Review (10 min)**

- **What’s required:**

1. Personal Prompt Library (GitHub repository)
1. 3+ fully documented templates
1. Quality rubrics for each template
1. style.json file
1. Complete README hierarchy
1. Impact estimation document

- **Evaluation criteria (8 dimensions):**

1. Repository Organization
1. Template Quality
1. Prompt Engineering
1. GitHub Usage
1. Workflow Documentation
1. Style Consistency
1. Practical Application
1. Overall Completeness

- **Point breakdown:** 40 points total (8 × 5)
  - 34-40: Excellent
  - 28-33: Good
  - 22-27: Adequate

**Segment 2: Impact Estimation Framework (15 min)**

- **The formula:**
  
  ```
  Time Saved Per Use × Frequency = Total Time Saved
  Total Time Saved × Hourly Rate = Dollar Value
  Dollar Value - AI Costs = Net ROI
  ```
- **Example calculation:**
  
  ```
  Proposal Template:
  - Time saved: 2 hrs (manual) → 20 min (AI) = 1.67 hrs saved
  - Frequency: 8 proposals/month
  - Monthly savings: 1.67 × 8 = 13.3 hrs/month
  - Annual savings: 13.3 × 12 = 160 hrs/year
  - Dollar value: 160 × $150/hr = $24,000/year
  - AI costs: ~$30/month = $360/year
  - Net ROI: $23,640/year
  ```
- **What to measure:**
  - Time savings
  - Quality improvement (rubric scores before/after)
  - Potential team impact (if others use templates)
  - Cost analysis

**Segment 3: Final Polish Checklist (10 min)**

- **Repository organization:**
  - [ ] Clear folder structure
  - [ ] All READMEs complete
  - [ ] CONTRIBUTING.md present
  - [ ] Quick start guide
  - [ ] Consistent naming
- **Template quality:**
  - [ ] Follow documentation standard
  - [ ] Include rubrics
  - [ ] Tested and working
  - [ ] Examples provided
  - [ ] Limitations noted
- **Professional touches:**
  - [ ] Proper Markdown formatting
  - [ ] Links work correctly
  - [ ] No typos/errors
  - [ ] Version history included

**Segment 4: Q&A and Individual Support (10 min)**

- Open floor for questions
- Quick 1-on-1 check-ins if needed
- Clarify any confusion on requirements

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 7.1: Complete All Templates (Variable time - as needed)**

*Finalize your template library*

1. Review each template against documentation standard
1. Ensure all have:

- Complete documentation
- Quality rubrics (5-point scale)
- Examples
- Clear instructions
- Limitations noted
- Version history

1. Test each template one more time:

- Generate sample output
- Score against rubric
- Verify quality

1. Make final adjustments based on testing

**Deliverable:** All templates finalized and committed to GitHub

-----

**Exercise 7.2: Calculate Impact Estimation (30 minutes)**

*Document business value of your work*

1. For each template, estimate:

- Baseline time (manual process)
- AI-assisted time (with template)
- Time saved per use
- Frequency of use (per week/month)
- Total time saved (annual)

1. Calculate dollar value:

- Time saved × your hourly rate
- Or time saved × average consultant rate ($150-200/hr)

1. Estimate costs:

- AI API costs (if using paid tier)
- Time investment to create templates

1. Calculate ROI:

- Value - Costs = Net ROI
- ROI % = (Net ROI / Costs) × 100

1. Create impact summary document:
   
   ```markdown
   # Impact Estimation
   
   ## Templates Created
   - Template 1: [Name]
   - Template 2: [Name]
   - Template 3: [Name]
   
   ## Time Savings
   | Template | Time Saved/Use | Frequency | Annual Savings |
   |----------|----------------|-----------|----------------|
   | Template 1 | 1.5 hrs | 10/month | 180 hrs |
   
   ## Financial Impact
   - Total time saved: XXX hours/year
   - Dollar value: $XXX,XXX
   - Costs: $XXX
   - Net ROI: $XXX,XXX
   - ROI %: XXX%
   
   ## Quality Improvements
   [Describe quality gains, consistency, reduced errors]
   
   ## Team Potential
   [If 5 consultants use these templates...]
   ```

**Deliverable:** `impact-estimation.md` in repository

-----

**Exercise 7.3: Final Repository Polish (30 minutes)**

*Ensure professional presentation*

1. **Check all links:**

- Click every link in READMEs
- Fix any broken links
- Ensure proper formatting

1. **Verify consistency:**

- File naming conventions followed
- Markdown formatting consistent
- Header capitalization consistent

1. **Add finishing touches:**

- Update main README with final stats (# templates, # rubrics, etc.)
- Add license if appropriate (MIT, Apache, etc.)
- Consider adding visual elements (badges, screenshots if helpful)

1. **Create capstone summary document:**
   
   ```markdown
   # Block 1 Capstone Summary
   
   ## Repository
   [Link to GitHub repository]
   
   ## Contents
   - X templates created
   - X quality rubrics
   - style.json configured
   - Complete documentation
   
   ## Key Achievements
   - [Achievement 1]
   - [Achievement 2]
   - [Achievement 3]
   
   ## Impact
   - Estimated XXX hours/year saved
   - $XXX,XXX annual value
   - [Other benefits]
   
   ## Next Steps
   - Plans for Block 2
   - Additional templates to create
   - Team rollout considerations
   ```

**Deliverable:** Polished repository + capstone summary

-----

## **Week 8: Block 1 Capstone Evaluation**

### **Format**

This week is **self-paced** - no live workshop. Participants complete final deliverables and self-evaluate using the rubric.

### **Requirements**

**Submit by end of week:**

1. GitHub repository URL
1. Capstone summary document
1. Impact estimation document
1. Self-evaluation against rubric (optional but encouraged)

### **Self-Evaluation Process (Optional - 30 minutes)**

1. Review the Block 1 Capstone Rubric (see Appendix H)
1. Score yourself on each of 8 criteria (1-5 points each):

- Repository Organization
- Template Quality
- Prompt Engineering
- GitHub Usage
- Workflow Documentation
- Style Consistency
- Practical Application
- Overall Completeness

1. Calculate total score (out of 40)
1. Identify:

- Your strongest areas
- Areas for improvement
- What you learned most
- What you’ll apply immediately

1. Create brief self-reflection (1-2 paragraphs)

**Deliverable:** Self-evaluation document (optional)

-----

### **Transition to Block 2**

**Preview of Block 2: AI Workflow Engineering**

- Building on your templates to create automated workflows
- Introduction to no-code automation platforms
- Connecting AI to external tools and data sources
- Creating your first AI-powered agent
- Takes your prompts from manual to automated

**Enrollment:** Opens upon Block 1 certification
**Block 2 starts:** 1-2 weeks after Block 1 evaluation

-----

# **APPENDICES**

## **Appendix A: Task Priority Matrix Template**

```markdown
# Task Priority Analysis

| Task | Frequency (1-5) | Time (1-5) | Repetitiveness (1-5) | Value (1-5) | AI-Suitable (1-5) | Priority Score | Rank |
|------|----------------|------------|---------------------|-------------|------------------|----------------|------|
| [Task name] | | | | | | | |
| | | | | | | | |

## Scoring Guide

**Frequency:**
- 1 = Rarely (few times per year)
- 2 = Occasionally (monthly)
- 3 = Regularly (weekly)
- 4 = Often (few times per week)
- 5 = Daily or more

**Time:**
- 1 = < 15 minutes
- 2 = 15-30 minutes
- 3 = 30-60 minutes
- 4 = 1-2 hours
- 5 = > 2 hours

**Repetitiveness:**
- 1 = Always completely different
- 2 = Mostly different, some patterns
- 3 = Mix of standard and custom
- 4 = Mostly same, minor variations
- 5 = Exactly the same every time

**Value:**
- 1 = Low impact, nice-to-have
- 2 = Moderate impact
- 3 = Important, regular impact
- 4 = High impact, significant value
- 5 = Critical, major business impact

**AI-Suitable:**
- 1 = AI cannot help at all
- 2 = AI could help minimally
- 3 = AI could handle parts of it
- 4 = AI could handle most of it
- 5 = AI perfect fit for this task

## Priority Calculation
Priority Score = (Frequency × Time × Repetitiveness) + (Value × AI-Suitable)

## Top 3 Priorities
1. [Highest scoring task]
2. [Second highest]
3. [Third highest]
```

-----

## **Appendix B: ASK-CONTEXT-CONSTRAINTS-EXAMPLE Template**

```markdown
# Prompt Template: [Deliverable Name]

## ASK
[State clearly what you want the AI to create, analyze, or do]

Example:
- Create a project proposal executive summary
- Analyze meeting notes and extract action items
- Draft a client assessment report

## CONTEXT
[Provide background information the AI needs]

Include:
- Who is involved (client name, team, stakeholders)
- What situation/project this relates to
- Any relevant history or background
- Key facts or data points

Example:
- Client: Acme Manufacturing (500 employees, $50M revenue)
- Project: Cloud ERP migration
- Current state: Using 15-year-old on-premise system
- Timeline: 12-month implementation
- Budget: $500K approved

## CONSTRAINTS
[Specify requirements, limitations, format, tone]

Include:
- Length requirements (word count, page count)
- Tone and voice (formal, conversational, technical)
- Required sections or structure
- Things to avoid
- Formatting specifications
- Deadline or urgency considerations

Example:
- Length: 2-3 paragraphs maximum
- Tone: Professional but approachable, executive-level
- Must include: Business case, approach summary, timeline, value proposition
- Avoid: Technical jargon, implementation details
- Format: Markdown with bold headers

## EXAMPLE
[Show a sample of desired output style or format]

Provide:
- Short excerpt from similar deliverable
- Sample paragraph showing tone
- Format template
- Structure to follow

Example:

    ## Executive Summary

    Acme Manufacturing's legacy ERP system has become a critical bottleneck,
    limiting growth and creating operational inefficiencies…

    **Proposed Approach:** [Brief description]
    **Timeline:** [Key milestones]
    **Expected Value:** [Quantified benefits]

---

## Usage Instructions

1. Fill in all four sections before prompting
2. Be specific in each section
3. Test and iterate based on output
4. Save successful prompts for reuse
5. Document what works best

## Customization Tips
- Add more context for complex deliverables
- Include multiple examples for consistency
- Adjust constraint specificity based on need
- Version and track improvements
```

-----

## **Appendix C: style.json Template**

```json
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "Personal/Brand Style Guide",
  "description": "Configuration file for consistent AI-generated content",
  
  "brand": {
    "name": "Your Company Name",
    "tagline": "Your tagline or mission",
    "primary_color": "#0066CC",
    "secondary_color": "#FF6B35",
    "accent_colors": ["#00CC99", "#FFD700"],
    "fonts": {
      "primary": "Calibri",
      "secondary": "Arial",
      "headings": "Helvetica Neue"
    },
    "logo_placement": "top-right",
    "logo_description": "Blue and white modern design with company initials"
  },
  
  "tone": {
    "descriptors": [
      "Professional",
      "Concise",
      "Data-driven",
      "Approachable",
      "Confident"
    ],
    "avoid": [
      "Overly casual",
      "Buzzwords and jargon",
      "Passive voice",
      "Vague generalities",
      "Excessive exclamation points"
    ],
    "voice_characteristics": {
      "formality": "Business professional",
      "perspective": "First person plural (we/our) for company, second person (you/your) for client",
      "sentence_structure": "Mix of short and medium sentences, avoid run-ons"
    }
  },
  
  "document_standards": {
    "page_numbers": true,
    "footer_content": "Company Name | Confidential | Page {page} of {total}",
    "header_content": "Client Name | Project Name | {Date}",
    "date_format": "YYYY-MM-DD",
    "number_format": "US (commas for thousands)",
    "currency": "USD"
  },
  
  "content_preferences": {
    "bullet_style": "Sentence fragments with action verbs",
    "list_length": "3-5 items ideal, max 7",
    "paragraph_length": "3-5 sentences",
    "section_transitions": "Use transitional phrases",
    "data_presentation": "Tables for comparisons, charts for trends",
    "call_to_action_style": "Clear, specific, action-oriented"
  },
  
  "ai_generation_preferences": {
    "image_style": "Modern corporate photography, bright natural lighting",
    "image_subjects": "Diverse business professionals, collaborative settings",
    "image_colors": "Cool blues and warm oranges, minimal saturation",
    "avoid_in_images": "Stock photo clichés, fake handshakes, clipart"
  },
  
  "deliverable_specific": {
    "proposals": {
      "required_sections": ["Executive Summary", "Approach", "Timeline", "Investment", "Why Us"],
      "max_pages": 15,
      "include_case_studies": true
    },
    "presentations": {
      "slide_design": "Minimal text, strong visuals",
      "max_bullets_per_slide": 5,
      "include_slide_numbers": true
    }
  },
  
  "quality_standards": {
    "grammar_checker": "Required before delivery",
    "client_name_verification": "Must appear correctly in all documents",
    "brand_color_accuracy": "Must use exact hex codes",
    "template_adherence": "All deliverables must follow approved templates"
  },
  
  "metadata": {
    "version": "1.0",
    "last_updated": "YYYY-MM-DD",
    "owner": "Your Name",
    "department": "Consulting",
    "approved_by": "Leadership Team"
  }
}
```

-----

## **Appendix D: Quality Rubric Template**

```markdown
# Quality Rubric: [Deliverable Name]

## Purpose
This rubric evaluates [deliverable type] for consistency, quality, and alignment with standards.

## Scoring Scale
- **5 - Excellent:** Exceeds all standards
- **4 - Good:** Meets all standards with minor room for improvement
- **3 - Adequate:** Meets minimum standards, needs refinement
- **2 - Poor:** Below standards, significant issues
- **1 - Missing:** Critical elements absent

---

## Criterion 1: [Name]
**Description:** [What this criterion measures]

| Score | Description |
|-------|-------------|
| **5 - Excellent** | [Specific, detailed description of excellent work] |
| **4 - Good** | [Specific description of good work] |
| **3 - Adequate** | [Specific description of adequate work] |
| **2 - Poor** | [Specific description of poor work] |
| **1 - Missing** | [What constitutes missing/absent] |

**Weight:** [X%] of total score

---

## Criterion 2: [Name]
**Description:** [What this criterion measures]

| Score | Description |
|-------|-------------|
| **5 - Excellent** | [Description] |
| **4 - Good** | [Description] |
| **3 - Adequate** | [Description] |
| **2 - Poor** | [Description] |
| **1 - Missing** | [Description] |

**Weight:** [X%] of total score

---

[Repeat for Criteria 3-7]

---

## Scoring Summary

| Criterion | Weight | Raw Score (1-5) | Weighted Score |
|-----------|--------|-----------------|----------------|
| Criterion 1 | 20% | | |
| Criterion 2 | 20% | | |
| Criterion 3 | 15% | | |
| Criterion 4 | 15% | | |
| Criterion 5 | 15% | | |
| Criterion 6 | 10% | | |
| Criterion 7 | 5% | | |
| **TOTAL** | **100%** | | |

## Quality Thresholds
- **90-100%:** Excellent - Ready for delivery
- **80-89%:** Good - Minor revisions recommended
- **70-79%:** Adequate - Significant revisions needed
- **60-69%:** Poor - Major rework required
- **<60%:** Unacceptable - Start over or fundamentally revise

## Notes and Observations
[Document specific observations, patterns, or recommendations]

---

## Version History
- v1.0 (YYYY-MM-DD): Initial rubric created
```

-----

## **Appendix E: Example Rubrics**

### **Example 1: Proposal Quality Rubric**

```markdown
# Quality Rubric: Client Proposal

## Criterion 1: Problem Statement Clarity

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Client challenges stated clearly with specific, quantified impacts. Directly tied to business objectives. |
| **4 - Good** | Challenges stated clearly with most specifics present. Good connection to business impact. |
| **3 - Adequate** | Challenges mentioned but somewhat general. Business impact implied but not explicit. |
| **2 - Poor** | Challenges vague or generic. Minimal connection to specific client situation. |
| **1 - Missing** | No clear problem statement or completely disconnected from client needs. |

**Weight:** 20%

---

## Criterion 2: Solution Appropriateness

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Proposed approach directly addresses stated problems. Methodology clearly explained. Tailored to client's specific situation and constraints. |
| **4 - Good** | Approach addresses problems well. Methodology explained. Mostly client-specific with minor generic elements. |
| **3 - Adequate** | Approach addresses problems adequately. Basic methodology outlined. Mix of specific and generic content. |
| **2 - Poor** | Approach weakly connected to problems. Methodology unclear. Largely generic, not customized. |
| **1 - Missing** | No clear solution proposed or completely inappropriate for stated problems. |

**Weight:** 25%

---

## Criterion 3: Value Proposition

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Clear, quantified benefits. ROI or impact metrics provided. Compelling differentiation from alternatives. |
| **4 - Good** | Benefits clearly stated, mostly quantified. Good value case. Some differentiation shown. |
| **3 - Adequate** | Benefits mentioned, partially quantified. Basic value case. Limited differentiation. |
| **2 - Poor** | Benefits vague or generic. No quantification. No clear differentiation. |
| **1 - Missing** | No value proposition or benefits stated. |

**Weight:** 20%

---

## Criterion 4: Timeline Realism

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Detailed timeline with milestones, dependencies, and realistic durations. Aligned with client constraints. |
| **4 - Good** | Clear timeline with major milestones. Realistic durations. Mostly aligned with constraints. |
| **3 - Adequate** | Basic timeline present. Generally realistic. Some alignment with constraints. |
| **2 - Poor** | Vague timeline. Questionable realism. Poor constraint alignment. |
| **1 - Missing** | No timeline or completely unrealistic. |

**Weight:** 10%

---

## Criterion 5: Professional Tone & Style

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Consistently professional tone. Perfect grammar. Matches style.json precisely. Client-centric language throughout. |
| **4 - Good** | Professional tone maintained. Minor grammar issues. Good style.json alignment. Mostly client-centric. |
| **3 - Adequate** | Generally professional. Some grammar issues. Partial style.json alignment. Mix of client-centric and generic language. |
| **2 - Poor** | Inconsistent professionalism. Multiple grammar errors. Poor style alignment. Generic language dominates. |
| **1 - Missing** | Unprofessional tone or severe grammar issues. No style adherence. |

**Weight:** 15%

---

## Criterion 6: Completeness

| Score | Description |
|-------|-------------|
| **5 - Excellent** | All required sections present and well-developed. No gaps. Thorough coverage of all aspects. |
| **4 - Good** | All required sections present. Minor gaps in detail. Good coverage overall. |
| **3 - Adequate** | Most sections present. Some gaps. Adequate coverage of key points. |
| **2 - Poor** | Missing sections. Significant gaps. Incomplete coverage. |
| **1 - Missing** | Critical sections absent. Major information gaps. |

**Weight:** 5%

---

## Criterion 7: Client-Specificity

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Heavily customized to client. Uses client's terminology and references specific situations. Industry-specific insights throughout. |
| **4 - Good** | Good customization. References client situations. Some industry-specific content. |
| **3 - Adequate** | Basic customization. Client mentioned but limited specifics. Generic industry content. |
| **2 - Poor** | Minimal customization. Mostly template language. Could apply to any client. |
| **1 - Missing** | No customization. Pure template. Wrong client name or details. |

**Weight:** 5%
```

-----

## **Appendix F: Documentation Standard Template**

```markdown
# [Template/Prompt Name]

## Metadata
- **Type:** [Client-facing / Internal]
- **Category:** [Proposal / SOW / Assessment / etc.]
- **Status:** [Draft / Tested / Production]
- **Version:** 1.0
- **Last Updated:** YYYY-MM-DD
- **Owner:** [Your Name]

---

## Purpose
[2-3 sentences explaining what this template is for and what problem it solves]

Example:
"This template generates executive summaries for technical proposals. It ensures consistent structure, appropriate detail level for executives, and alignment with our brand voice."

---

## When to Use
[Bullet list of specific scenarios where this template applies]

- Use case scenario 1
- Use case scenario 2
- Use case scenario 3

Example:
- When responding to RFPs requiring executive summary
- When creating unsolicited proposals for C-level prospects
- When executive asks for high-level project overview

---

## When NOT to Use
[Bullet list of scenarios where this template is inappropriate]

- Inappropriate scenario 1
- Inappropriate scenario 2

Example:
- For technical deep-dives (use Technical Specification template instead)
- For internal project updates (use Status Report template)
- When client explicitly requests different format

---

## How to Use

### Step 1: Gather Required Inputs
[What information you need before using this template]

### Step 2: Prepare Your Prompt
[How to fill in the template variables]

### Step 3: Generate Content
[Run the prompt in your AI tool]

### Step 4: Review and Refine
[Use the rubric to evaluate quality, apply LLM-as-judge if needed]

### Step 5: Finalize
[Final checks before delivery]

---

## Input Requirements

| Variable | Description | Example | Required? | Default |
|----------|-------------|---------|-----------|---------|
| CLIENT_NAME | Full legal client name | "Acme Manufacturing Inc." | Yes | - |
| INDUSTRY | Client's industry sector | "Manufacturing - Automotive Parts" | Yes | - |
| PROJECT_SCOPE | Brief project description | "ERP cloud migration" | Yes | - |
| TIMELINE | Project duration | "12 months" | No | "6 months" |
| BUDGET | Approved budget amount | "$500,000" | No | "TBD" |

---

## Output Format

**Expected output:**
[Describe what the AI will generate]

**Structure:**
```markdown
[Show the typical structure/format of the output]
```

**Typical length:** [word count / page count / character count]

-----

## Quality Rubric

[Link to or include the quality rubric for this deliverable]

See: [Link to rubric file]

**Quick quality checks:**

- [ ] Client name appears correctly (3+ times)
- [ ] Industry-specific terminology used
- [ ] All required sections present
- [ ] Matches style.json tone
- [ ] No placeholder text remaining
- [ ] Grammar and spelling perfect

-----

## Customization Tips

**Common Adjustments:**

- [Tip for customizing to specific situations]
- [Another customization tip]

**Advanced Usage:**

- [Optional advanced techniques]
- [Platform-specific optimizations]

**Cost Optimization:**

- [How to reduce token usage without losing quality]

-----

## Known Limitations

**What this template does NOT do:**

- [Limitation 1]
- [Limitation 2]

**Common Issues:**

- **Issue:** [Description of problem]
  - **Solution:** [How to fix or work around]

-----

## Examples

### Example 1: [Scenario Name]

**Input:**

```
[Show sample input data]
```

**Output:**

```
[Show portion of generated output]
```

**Notes:** [What worked well, what was adjusted]

### Example 2: [Different Scenario]

[Repeat structure]

-----

## Version History

|Version|Date      |Changes                        |Author|
|-------|----------|-------------------------------|------|
|1.0    |YYYY-MM-DD|Initial template created       |[Name]|
|1.1    |YYYY-MM-DD|Added cost optimization tips   |[Name]|
|2.0    |YYYY-MM-DD|Restructured for better quality|[Name]|

-----

## Related Resources

- **Similar Templates:** [Links to related templates]
- **Quality Rubric:** [Link to rubric]
- **Style Guide:** [Link to style.json]
- **Best Practices:** [Link to relevant documentation]

-----

## Feedback and Contributions

**Found an issue?** [How to report problems]
**Want to improve this?** [How to contribute changes]

See [CONTRIBUTING.md](../CONTRIBUTING.md) for details.

-----

## License

[If applicable, specify license for reuse]

```
---

## **Appendix G: CONTRIBUTING.md Template**

```markdown
# Contributing to [Your Name]'s AI Prompt Library

Thank you for your interest in improving our shared AI resources! This document provides guidelines for contributing to this prompt library.

---

## How to Contribute

### 1. Fork or Branch the Repository
- **If you have write access:** Create a feature branch
```

git checkout -b feature/your-improvement-name

```
- **If you don't have access:** Fork the repository

### 2. Make Your Improvements
Focus on one of these areas:
- **New Templates:** Add prompts for new deliverable types
- **Improvements:** Enhance existing templates
- **Documentation:** Improve clarity, add examples
- **Bug Fixes:** Fix errors in prompts or documentation
- **Quality:** Add or improve rubrics

### 3. Test Thoroughly
Before submitting, verify:
- [ ] Template generates quality output (test with 3+ examples)
- [ ] Documentation is complete and clear
- [ ] Rubric is included (if applicable)
- [ ] Examples are provided
- [ ] No sensitive/client information included
- [ ] Follows our documentation standard

### 4. Submit a Pull Request
- Write clear PR title: `[Category] Brief description`
- In PR description, explain:
- **What changed:** Specific modifications made
- **Why:** Problem solved or improvement achieved
- **How to test:** Steps to verify the change works

### 5. Wait for Review
- Reviewer will provide feedback
- Address comments and make adjustments
- Once approved, changes will be merged

---

## Contribution Standards

### Quality Requirements

**All contributions must:**
- Follow our [Documentation Standard Template](docs/documentation-standard-template.md)
- Include quality rubrics for new templates
- Provide at least 2 working examples
- Use proper Markdown formatting
- Have no typos or grammatical errors

**Templates must:**
- Use ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework
- Include clear variable definitions
- Specify when to use and when NOT to use
- List known limitations
- Include version history

### What We're Looking For

**High Priority:**
- Templates for common consulting deliverables
- Quality improvements to existing templates
- Better rubrics and evaluation criteria
- Clear, helpful documentation
- Real-world examples that worked well

**Medium Priority:**
- Platform-specific optimizations
- Cost optimization techniques
- Advanced prompting patterns
- Integration with other tools

**Lower Priority:**
- Experimental or unproven techniques
- Highly specialized niche templates
- Theoretical improvements without testing

---

## What to Avoid

**Do NOT contribute:**
- Untested prompts (must validate with real outputs)
- Templates without documentation
- Content with client-specific/sensitive information
- Breaking changes to existing templates without discussion
- Plagiarized content from other sources

**Do NOT:**
- Make multiple unrelated changes in one PR
- Change file/folder structure without approval
- Remove existing content without justification
- Ignore existing conventions and standards

---

## Code of Conduct

### Be Professional
- Constructive feedback only
- Respect different approaches and styles
- Assume good intentions
- Focus on improving the library, not criticizing contributors

### Be Collaborative
- Discuss major changes before implementing
- Seek feedback early
- Help other contributors
- Share knowledge and insights

### Be Responsible
- Test your contributions thoroughly
- Document clearly
- Respond to feedback promptly
- Fix issues you introduced

---

## Review Process

### Timeline
- **Initial Review:** Within 3 business days
- **Follow-up:** Within 2 business days of updates
- **Merge:** Once approved and all feedback addressed

### Review Criteria
Reviewers will evaluate:
1. **Functionality:** Does it work as described?
2. **Quality:** Does it produce good outputs?
3. **Documentation:** Is it clear and complete?
4. **Standards:** Does it follow our conventions?
5. **Value:** Does it add meaningful value to the library?

### Approval Requirements
- At least 1 reviewer approval
- All automated checks passing
- No unresolved comments
- Documentation complete

---

## Getting Help

### Questions?
- **General questions:** Post in [async support channel]
- **Technical issues:** Create a GitHub Issue
- **Major changes:** Discuss in [forum/channel] before implementing

### Resources
- [Documentation Standard Template](docs/documentation-standard-template.md)
- [Quality Rubric Template](docs/rubric-template.md)
- [Example Templates](examples/)
- [Style Guide](resources/style.json)

---

## Recognition

### Contributors
All contributors will be recognized in:
- Repository README (Contributors section)
- Version history of modified templates
- Quarterly newsletter (if applicable)

### Top Contributors
Outstanding contributors may receive:
- "Power User" badge in repository
- Featured template showcase
- Invitation to contribute to advanced features

---

## License and Ownership

### Your Contributions
By contributing, you agree that:
- Your contributions are your original work
- You grant [organization/owner] permission to use and distribute your contributions
- Contributions become part of this repository under [License Type]

### Attribution
- You will be credited in version history
- Major contributions will be noted in README
- You retain rights to your original work

---

## Questions or Issues?

**Contact:**
- **Repository Owner:** [Your Name] - [email/contact]
- **Technical Questions:** [GitHub Issues](link)
- **General Questions:** [Async channel/forum]

---

## Thank You!

Your contributions help make our AI work more effective and our team more productive. Every improvement, no matter how small, is valued and appreciated.

**Happy contributing!** 🚀
```

-----

## **Appendix H: Block 1 Capstone Rubric**

```markdown
# Block 1 Capstone Evaluation Rubric
## AI Prompting Mastery - Personal Prompt Library

**Total Points: 40 (8 criteria × 5 points each)**

---

## Criterion 1: Repository Organization (5 points)

**Evaluates:** Logical structure, navigation ease, folder organization

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Logical folder structure with clear hierarchy. All content properly categorized. README files at all levels (repository, folders, templates). Easy to find anything. Professional presentation. |
| **4 - Good** | Well-organized structure. Most content properly categorized. README files present at key levels. Generally easy to navigate. Minor organizational gaps. |
| **3 - Adequate** | Basic organization present. Content mostly categorized. Some README files missing. Navigation requires some effort. Structure could be clearer. |
| **2 - Poor** | Disorganized structure. Content poorly categorized. Few or no README files. Difficult to find content. Confusing layout. |
| **1 - Missing** | No clear organization. Random file placement. No documentation structure. Impossible to navigate. |

**Weight:** 12.5% of total score

---

## Criterion 2: Template Quality (5 points)

**Evaluates:** Prompt effectiveness, ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework, reusability

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Templates produce consistently high-quality outputs. Perfect adherence to ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework. Clear variable definitions. Highly reusable across situations. Tested and validated. |
| **4 - Good** | Templates produce good outputs with minor iterations. Good framework adherence. Clear variables. Reusable with some adjustments. Adequately tested. |
| **3 - Adequate** | Templates produce acceptable outputs. Basic framework usage. Variables present but could be clearer. Limited reusability. Some testing evident. |
| **2 - Poor** | Templates produce inconsistent outputs. Weak framework adherence. Unclear variables. Not clearly reusable. Minimal testing. |
| **1 - Missing** | Templates don't work or produce poor outputs. No framework structure. No clear variables. Not reusable. |

**Weight:** 12.5% of total score

---

## Criterion 3: Prompt Engineering (5 points)

**Evaluates:** Use of Markdown, code blocks, platform optimizations, cost efficiency

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Sophisticated Markdown structure (headers, lists, tables, code blocks). Proper data isolation with code blocks. Platform-specific optimizations applied. Cost-efficient prompt design. Examples of LLM-as-judge usage. |
| **4 - Good** | Good Markdown usage. Code blocks for data isolation. Some platform optimizations. Reasonable cost efficiency. Aware of iteration techniques. |
| **3 - Adequate** | Basic Markdown usage. Some code blocks used. Limited platform optimizations. Basic prompts without clear optimization. Minimal iteration. |
| **2 - Poor** | Minimal Markdown structure. Code blocks rarely used. No platform optimizations. Inefficient prompts. No iteration techniques. |
| **1 - Missing** | No Markdown structure. No code blocks. Generic prompts. No optimization or iteration. |

**Weight:** 12.5% of total score

---

## Criterion 4: GitHub Usage (5 points)

**Evaluates:** Version control practices, commit history, branching, pull requests

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Active use of branches for improvements. Multiple meaningful commits with clear messages. Pull request(s) completed with good descriptions. Version history shows iterative improvement. Professional Git practices. |
| **4 - Good** | Some branch usage. Good commit history with clear messages. At least one pull request completed. Version history present. Solid Git practices. |
| **3 - Adequate** | Basic commits present. Commit messages somewhat clear. Branch strategy attempted. Some version history. Adequate Git usage. |
| **2 - Poor** | Few commits. Unclear commit messages. No branching strategy. Limited version history. Poor Git practices. |
| **1 - Missing** | No meaningful commit history. Random or unclear commits. No versioning strategy. No evidence of Git usage beyond initial upload. |

**Weight:** 12.5% of total score

---

## Criterion 5: Workflow Documentation (5 points)

**Evaluates:** Template documentation, README completeness, usage instructions, examples

| Score | Description |
|-------|-------------|
| **5 - Excellent** | All templates follow documentation standard completely. Comprehensive instructions for each template. Multiple working examples provided. Known limitations documented. Clear version history. Perfect README hierarchy (3 levels). |
| **4 - Good** | Templates well-documented with minor gaps. Good instructions for most templates. Examples provided. Limitations noted. Good README structure. |
| **3 - Adequate** | Basic documentation present for templates. Instructions somewhat clear. Some examples. Limitations mentioned. README structure adequate. |
| **2 - Poor** | Minimal documentation. Unclear or incomplete instructions. Few examples. Limitations not documented. README structure weak. |
| **1 - Missing** | No documentation or incomprehensible. No usage instructions. No examples. No README structure. |

**Weight:** 12.5% of total score

---

## Criterion 6: Style Consistency (5 points)

**Evaluates:** style.json creation and usage, brand alignment, tone consistency

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Comprehensive style.json created with brand colors, fonts, tone, standards. Actively used in prompts and verified in outputs. Perfect consistency across all templates. Evidence of comparison gates usage. |
| **4 - Good** | Good style.json created with key elements. Used in most templates. Good consistency. Some comparison validation. |
| **3 - Adequate** | Basic style.json created. Used in some templates. Adequate consistency. Limited validation. |
| **2 - Poor** | Minimal style.json or poorly defined. Rarely used. Inconsistent outputs. No validation. |
| **1 - Missing** | No style.json or not used. No consistency across outputs. No style awareness. |

**Weight:** 12.5% of total score

---

## Criterion 7: Practical Application (5 points)

**Evaluates:** Real-world relevance, immediate usability, value demonstration

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Templates address actual consulting deliverables. Immediately usable in real work. Clear distinction between client-facing and internal templates. Demonstrated impact with specific examples. Ready for team sharing. |
| **4 - Good** | Templates address real needs. Usable with minor adjustments. Template categorization present. Good potential impact. Could be shared with preparation. |
| **3 - Adequate** | Templates somewhat relevant to work. Requires significant adaptation. Basic categorization. Some potential value. Not immediately shareable. |
| **2 - Poor** | Templates tangentially relevant. Limited practical use. Poor categorization. Unclear value. Not suitable for sharing. |
| **1 - Missing** | Templates not relevant to actual work. No practical application. No categorization. No demonstrated value. |

**Weight:** 12.5% of total score

---

## Criterion 8: Overall Completeness (5 points)

**Evaluates:** Capstone requirements met, impact estimation, polish and professionalism

| Score | Description |
|-------|-------------|
| **5 - Excellent** | All capstone requirements exceeded. 3+ exceptional templates with rubrics. Comprehensive impact estimation with ROI calculations. CONTRIBUTING.md present. Professional polish throughout. Self-evaluation completed thoughtfully. |
| **4 - Good** | All requirements met. 3+ good templates with rubrics. Good impact estimation. CONTRIBUTING.md present. Good overall quality. Self-evaluation completed. |
| **3 - Adequate** | Most requirements met. 3 templates present with rubrics. Basic impact estimation. CONTRIBUTING.md attempted. Adequate quality. Self-evaluation basic. |
| **2 - Poor** | Some requirements missing. Fewer than 3 templates or incomplete rubrics. Weak impact estimation. No CONTRIBUTING.md. Poor quality. No self-evaluation. |
| **1 - Missing** | Major requirements missing. Incomplete deliverables. No impact estimation. Unprofessional presentation. |

**Weight:** 12.5% of total score

---

## Scoring Summary

| Criterion | Raw Score (1-5) | Weighted Score (12.5%) |
|-----------|-----------------|------------------------|
| 1. Repository Organization | | |
| 2. Template Quality | | |
| 3. Prompt Engineering | | |
| 4. GitHub Usage | | |
| 5. Workflow Documentation | | |
| 6. Style Consistency | | |
| 7. Practical Application | | |
| 8. Overall Completeness | | |
| **TOTAL** | **/40** | **/100%** |

---

## Performance Levels

| Score Range | Percentage | Level | Description |
|-------------|------------|-------|-------------|
| 34-40 points | 85-100% | **Excellent** | Exceptional work. Ready for Block 2. Could serve as example for others. |
| 28-33 points | 70-84% | **Good** | Strong work. Ready for Block 2. Minor refinements would elevate to excellent. |
| 22-27 points | 55-69% | **Adequate** | Acceptable work. Can proceed to Block 2 but should address gaps during Block 2. |
| 16-21 points | 40-54% | **Needs Improvement** | Significant gaps. Should complete additional work before Block 2. |
| 0-15 points | 0-39% | **Incomplete** | Major elements missing. Not ready for Block 2. Needs substantial rework. |

---

## Feedback Template

**Strengths:**
- [What this capstone does exceptionally well]
- [Another strength]

**Areas for Improvement:**
- [Specific suggestion for improvement]
- [Another suggestion]

**Standout Elements:**
- [Something particularly impressive or creative]

**Recommended Next Steps:**
- [Specific action to take before or during Block 2]
- [Another recommendation]

**Overall Assessment:**
[Paragraph summarizing overall quality and readiness for Block 2]

---

## Self-Evaluation Questions

Use these to assess your own work before submission:

1. **Can someone else use my templates successfully?**
   - Are instructions clear enough?
   - Are examples helpful?
   - Is documentation complete?

2. **Do my templates actually save time?**
   - Have I tested them on real work?
   - What's the time savings?
   - Would I actually use these?

3. **Is my repository professional?**
   - Would I be proud to show this to my team?
   - Is navigation easy?
   - Are there any embarrassing gaps?

4. **Have I demonstrated growth?**
   - How has my prompting improved?
   - What new techniques did I learn?
   - What will I continue using?

5. **What surprised me?**
   - What worked better than expected?
   - What was harder than expected?
   - What would I do differently?
```

-----

## **Appendix I: QUICK-START.md Template**

```markdown
# Quick Start Guide: [Repository/Library Name]

## 5-Minute Setup

### Step 1: Clone or Download

    git clone [repository-url]

Or download ZIP from GitHub and extract.

### Step 2: Review Structure

    your-prompt-library/
    ├── README.md          # You are here
    ├── QUICK-START.md     # This file
    ├── CONTRIBUTING.md    # How to contribute
    ├── resources/
    │   └── style.json     # Your brand configuration
    ├── templates/
    │   ├── client-facing/ # External deliverables
    │   └── internal/      # Internal documents
    └── rubrics/           # Quality evaluation criteria

### Step 3: Configure Your Style
1. Open `resources/style.json`
2. Update brand colors, fonts, and tone to match your preferences
3. Save the file

### Step 4: Use Your First Template
1. Navigate to `templates/client-facing/` or `templates/internal/`
2. Open any template file
3. Copy the prompt section
4. Paste into your AI tool (Claude, ChatGPT, Copilot)
5. Fill in the variables (marked with [BRACKETS])
6. Run and review output
7. Use the associated rubric to evaluate quality

---

## Common Tasks

### Creating a New Deliverable
1. Identify the closest matching template
2. Copy the prompt
3. Fill in all required variables
4. Generate content
5. Evaluate with rubric
6. Iterate if needed (use LLM-as-judge pattern)

### Adding a New Template
1. Create a new branch: `git checkout -b feature/new-template-name`
2. Copy `templates/_template-template.md` to your category folder
3. Fill in all sections following the documentation standard
4. Create accompanying rubric in `rubrics/`
5. Test with at least 3 examples
6. Submit pull request

### Updating an Existing Template
1. Create a feature branch
2. Make your improvements
3. Update version history
4. Test thoroughly
5. Submit pull request with clear description

---

## Key Files Reference

| File | Purpose |
|------|---------|
| `resources/style.json` | Brand voice, colors, formatting preferences |
| `templates/client-facing/proposal.md` | Proposal generation template |
| `templates/internal/status-report.md` | Internal status updates |
| `rubrics/proposal-rubric.md` | Proposal quality evaluation |
| `CONTRIBUTING.md` | Guidelines for improvements |

---

## Getting Help

- **Documentation Issues:** Check the full README for detailed explanations
- **Template Problems:** Review the "Known Limitations" section in each template
- **General Questions:** [Your support channel]
- **Contributions:** See CONTRIBUTING.md

---

## Quick Reference: ASK-CONTEXT-CONSTRAINTS-EXAMPLE

Every template follows this structure:

    # ASK
    [What you want the AI to do]

    # CONTEXT
    [Background information and inputs]

    # CONSTRAINTS
    [Rules, requirements, limitations]

    # EXAMPLE
    [Sample of desired output format]

---

**Ready to go?** Start with a template from `/templates/` that matches your current task!
```

-----

## **Certification: AI Prompting Practitioner**

Upon successful completion of Block 1 Capstone with a score of 22+ points (55%+):

**You have demonstrated:**
- Proficiency in structured prompting using Markdown
- Ability to create reusable, documented templates
- Understanding of quality evaluation through rubrics
- Professional use of GitHub for version control
- Application of the ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework
- Creation of a personal prompt library with measurable impact

**You are certified as:** AI Prompting Practitioner

**Next Steps:**
- Continue to [Block 2: AI Workflow Engineering](block-2.md)
- Enrollment opens upon Block 1 certification
- Block 2 starts 1-2 weeks after Block 1 evaluation

-----

**END OF BLOCK 1 CURRICULUM**

---

**Navigation:** [← README](README.md) | **Block 1** | [Block 2 →](block-2.md) | [Block 3 →](block-3.md)