# **BLOCK 1 WEEK 1: Markdown Fundamentals & Structured Prompting**

**Block:** 1: AI Prompting Mastery
**Week:** 1 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** **Week 1** | [Next Week →](../week-2/participant-guide.md)

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
| 1 | Write valid Markdown documents with headers, lists, emphasis, and code blocks | Exercise 1.1 |
| 2 | Apply the ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework to create structured prompts | Exercise 1.2 |
| 3 | Set up a GitHub repository for your personal prompt library | Exercise 1.3 |
| 4 | Understand why structured prompts produce better AI outputs | Workshop + All Exercises |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Access to an AI platform (Claude at claude.ai or ChatGPT at chat.openai.com)
- [ ] GitHub account created (free tier at github.com)
- [ ] Ability to create and edit text files on your computer
- [ ] Basic understanding of text formatting concepts

**Not ready?** Create your accounts now - both are free and take about 5 minutes each.

---

## Key Concepts

### Concept 1: Why Markdown Matters for AI

**Definition:**
Markdown is a lightweight text formatting language that uses simple symbols (like # and *) to create structure in documents.

**Why It Matters:**
AI models were trained on millions of Markdown documents - websites, documentation, README files. When you use Markdown in prompts, you're speaking the AI's native language.

**Core Principle:**
> Structure = clarity for AI = better outputs

**Example:**
```markdown
# Project Proposal

## Overview
This project aims to improve customer satisfaction.

## Key Goals
- Reduce response time by 50%
- Increase satisfaction scores to 4.5/5
- Implement feedback loop

## Timeline
| Phase | Duration |
|-------|----------|
| Discovery | 2 weeks |
| Implementation | 4 weeks |
```

**Common Mistake:**
Writing prompts as a "wall of text" without structure. This forces the AI to guess what's important and often produces inconsistent results.

---

### Concept 2: Essential Markdown Syntax

**Definition:**
The core formatting elements you'll use in every prompt.

**Why It Matters:**
Consistent formatting creates consistent outputs. Master these elements and your prompts become predictable and reliable.

**The Pattern:**
```markdown
# Headers use hash symbols
## More hashes = smaller headers
### Up to six levels

- Bullet points use dashes
- Or asterisks *
  - Indent for nesting

1. Numbered lists
2. Use numbers and periods
3. For sequential items

**Bold text** for emphasis
*Italic text* for terms

`Inline code` for technical items

​```
Code blocks for multi-line code or data
Use three backticks to start and end
​```

[Link text](https://url.com)
```

**When to Use:**
- Headers: Separate sections of your prompt
- Lists: Present options or requirements
- Bold: Highlight key constraints
- Code blocks: Wrap any data, examples, or code

**When NOT to Use:**
- Don't over-format simple questions
- Avoid deep nesting (3+ levels) - it gets confusing

---

### Concept 3: The ASK-CONTEXT-CONSTRAINTS-EXAMPLE Framework

**Definition:**
A four-section structure for creating complete, clear prompts that produce consistent results.

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| **ASK** | What you want the AI to do | "Write a follow-up email" |
| **CONTEXT** | Background information needed | Client name, meeting details, relationship |
| **CONSTRAINTS** | Requirements and limitations | Tone, length, what to include/exclude |
| **EXAMPLE** | Sample of desired output | A paragraph showing the style you want |

**Visual Reference:**
```
    ┌─────────────────┐
    │      ASK        │  What you want
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │    CONTEXT      │  Background info
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │  CONSTRAINTS    │  Rules & limits
    └────────┬────────┘
             │
             ▼
    ┌─────────────────┐
    │    EXAMPLE      │  Show the format
    └─────────────────┘
```

---

### Quick Reference: ASK-CONTEXT-CONSTRAINTS-EXAMPLE Template

| Element | Purpose | Format |
|---------|---------|--------|
| ASK | States what you want clearly | 1-2 sentences, specific action |
| CONTEXT | Provides background | Bullet points or paragraph with key details |
| CONSTRAINTS | Sets boundaries | Bulleted list of requirements |
| EXAMPLE | Shows desired output | Sample text in the format you want |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Introduction to Markdown formatting and the structured prompting framework that will be the foundation for all your AI work.

**Key Points from Each Segment:**

**Segment 1: Welcome & Program Overview**
- Block 1 is an 8-week journey to AI Prompting Practitioner certification
- The maturity model: Level 0 (ad-hoc) → Level 1 (templated) → Level 2 (workflows) → Level 3 (automation)
- Key takeaway: You're building skills that compound over time

**Segment 2: Why Markdown Matters**
- Unstructured prompts produce inconsistent results
- AI models understand Markdown because they were trained on it
- Key takeaway: Structure = clarity for AI = better outputs

**Segment 3: Markdown Essentials**
- Headers (#), lists (- and 1.), emphasis (**bold**, *italic*)
- Code blocks (```) are critical for isolating data
- Key takeaway: Master these basics and every prompt improves

**Segment 4: ASK-CONTEXT-CONSTRAINTS-EXAMPLE Framework**
- Every prompt needs these four sections
- Forces completeness and prevents vague requests
- Key takeaway: Use this framework until it becomes automatic

### Demo Recap

**What Was Demonstrated:**
Live transformation of a vague request into a structured prompt using the framework.

**Key Steps:**
1. Started with vague: "Write an email"
2. Added ASK: Specific type of email and purpose
3. Added CONTEXT: Who, what, when details
4. Added CONSTRAINTS: Tone, length, requirements
5. Added EXAMPLE: Sample style

**Result:**
The structured version produced a much more relevant, usable output than the vague original.

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 1.1 | 20 min | `markdown-practice.md` | Markdown syntax |
| 1.2 | 25 min | `first-structured-prompt.md` | ASK-CONTEXT-CONSTRAINTS-EXAMPLE |
| 1.3 | 15 min | GitHub repository | Prompt library setup |

---

### Exercise 1.1: Markdown Practice Document

**Duration:** 20 minutes

**Purpose:**
Build muscle memory with Markdown syntax by creating a document that uses all the essential formatting elements.

**You Will Create:**
A Markdown document that demonstrates your understanding of headers, lists, emphasis, and code blocks.

---

#### Instructions

**Step 1: Create a new file**
Create a file called `markdown-practice.md` on your computer. Use any text editor (VS Code, Notepad++, TextEdit, or even basic Notepad).

**Step 2: Add headers**
Create a document structure with:
- One H1 header (main title using #)
- At least two H2 headers (sections using ##)
- At least one H3 header (subsection using ###)

Example:
```markdown
# My First Markdown Document

## About This Document

### Purpose
```

**Step 3: Add lists**
Include both types of lists:
- A numbered list with at least 3 items
- A bulleted list with at least 3 items, including one nested item

Example:
```markdown
## My Favorite Things

1. First item
2. Second item
3. Third item

- Bullet point
- Another point
  - Nested point
- Final point
```

**Step 4: Add emphasis and a code block**
- Use **bold** and *italic* text somewhere in your document
- Add a code block with any content (could be example code, a quote, or data)

Example:
```markdown
The most **important** concept is *structure*.

​```
This is a code block.
It preserves formatting exactly.
​```
```

**Step 5: Add a link**
Include at least one link to any website.

Example:
```markdown
Learn more at [Markdown Guide](https://www.markdownguide.org/)
```

**Step 6: Preview your work**
Verify your Markdown renders correctly using one of these:
- VS Code preview (Ctrl+Shift+V or Cmd+Shift+V)
- [Dillinger](https://dillinger.io/) - paste your content
- GitHub - paste into any README

**Step 7: Review Your Work**
Check that your deliverable includes:
- [ ] Title (H1) and at least two sections (H2)
- [ ] Both numbered and bulleted lists
- [ ] Bold and italic text
- [ ] A code block
- [ ] A link

---

#### Deliverable Specification

**File Name:** `markdown-practice.md`

**Location:** Save locally for now, will upload to GitHub in Exercise 1.3

**Format Requirements:**
- Plain text file with .md extension
- Valid Markdown that renders correctly

**Quality Criteria:**
- [ ] All required elements present
- [ ] Renders correctly in preview
- [ ] Content makes sense (not just random text)

---

#### Example

**Scenario:** Creating a personal introduction document

**Output:**
```markdown
# About Me

## Professional Background

I work as a **consultant** with a focus on *technology strategy*.

### Key Skills
1. Strategic planning
2. Technology assessment
3. Stakeholder management

## Interests

- Learning new tools
- Process improvement
  - Automation
  - Efficiency
- Teaching others

## Resources I Recommend

Check out [Claude](https://claude.ai) for AI assistance.

​```
My productivity motto:
"Work smarter, not harder"
​```
```

**Why This Works:**
Uses all required elements in a natural, readable way. The content flows logically and demonstrates understanding of when to use each formatting type.

---

#### Tips & Troubleshooting

**Tips:**
- Leave a blank line before and after headers and lists
- Put a space after # in headers

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Headers not rendering | Add a space after the # symbol |
| Lists running together | Add a blank line before the first list item |
| Code block not working | Make sure you have exactly three backticks |

---

### Exercise 1.2: First Structured Prompt

**Duration:** 25 minutes

**Purpose:**
Apply the ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework to a real task, experiencing the difference structured prompting makes.

**You Will Create:**
A structured prompt for a task you actually do, plus the AI response and your analysis.

---

#### Instructions

**Step 1: Choose a task**
Pick something you've asked AI to help with before (or would want help with):
- Writing an email
- Explaining a concept
- Creating a meeting agenda
- Drafting social media content
- Summarizing information
- Any other text-based task

**Step 2: Create your structured prompt**
Use the framework template:

```markdown
# ASK
[What you want the AI to do - be specific about the deliverable]

# CONTEXT
[Background information the AI needs to do this well]
- [Relevant detail 1]
- [Relevant detail 2]
- [Relevant detail 3]

# CONSTRAINTS
- [Requirement 1: e.g., tone, length]
- [Requirement 2: e.g., what to include]
- [Requirement 3: e.g., what to avoid]
- [Format requirement: e.g., structure, style]

# EXAMPLE
[Optional but powerful: Show what good output looks like]
```

**Step 3: Test your prompt**
Copy your complete prompt into Claude or ChatGPT and run it.

**Step 4: Save everything**
Create a file with:
- Your structured prompt
- The AI's response
- Your analysis (2-3 sentences on how structure affected the output)

**Step 5: Review Your Work**
Check that your deliverable includes:
- [ ] Clear, specific ASK section
- [ ] At least 3 details in CONTEXT
- [ ] At least 3 items in CONSTRAINTS
- [ ] The AI's actual response
- [ ] Your reflection on the results

---

#### Deliverable Specification

**File Name:** `first-structured-prompt.md`

**Location:** Save locally for now, will upload to GitHub in Exercise 1.3

**Format Requirements:**
- Markdown format with clear sections
- Include both prompt and response
- Include your brief analysis

**Quality Criteria:**
- [ ] Framework used correctly
- [ ] Prompt is specific, not vague
- [ ] Analysis reflects on what worked

---

#### Example

**Scenario:** Creating a meeting follow-up email

**Input:**
```markdown
# ASK
Write a professional follow-up email to send after an initial client meeting.

# CONTEXT
- Client: Sarah Chen, VP of Operations at Meridian Manufacturing
- Meeting date: Yesterday (Tuesday)
- Topics discussed: Their current inventory management challenges,
  potential for automation, and timeline for decision
- Relationship: First meeting, referred by mutual contact
- Next step agreed: I'll send a proposal outline by Friday

# CONSTRAINTS
- Tone: Professional but warm, not stiff or overly formal
- Length: 150-200 words
- Must include: Thank you, summary of key points, confirmation of next step
- Avoid: Jargon, pushy sales language, excessive exclamation marks
- Format: Standard email with greeting and signature

# EXAMPLE
The opening should feel like:
"Thank you for taking the time to meet yesterday. I enjoyed learning about
Meridian's operations and the challenges you're facing with inventory visibility."
```

**Output:**
[AI generates a relevant, well-structured email following the constraints]

**Analysis:**
"The structured prompt produced an email that matched my intended tone exactly. The context about it being a first meeting from a referral helped the AI strike the right balance - professional but not cold. The example of the opening paragraph was especially helpful for setting the voice."

**Why This Works:**
Each section adds clarity. The AI isn't guessing about relationship, tone, or expectations.

---

### Exercise 1.3: GitHub Repository Setup

**Duration:** 15 minutes

**Purpose:**
Create your prompt library home - a GitHub repository that will hold all your templates, prompts, and resources throughout this program.

**You Will Create:**
A GitHub repository with a basic folder structure and your first files.

---

#### Instructions

**Step 1: Go to GitHub**
Navigate to [github.com](https://github.com) and sign in (or create an account if you haven't).

**Step 2: Create a new repository**
1. Click the "+" icon in the top right
2. Select "New repository"
3. Configure:
   - **Name:** `ai-prompt-library` (or similar)
   - **Description:** "My personal AI prompt library and templates"
   - **Visibility:** Private (recommended) or Public
   - **Check:** "Add a README file"
4. Click "Create repository"

**Step 3: Create folder structure**
Using the GitHub web interface:
1. Click "Add file" → "Create new file"
2. Type `templates/README.md` (this creates the folder and file together)
3. Add some placeholder content: `# Templates\n\nReusable prompt templates will go here.`
4. Click "Commit new file"

Repeat for:
- `examples/README.md` - "Prompt and response examples"
- `resources/README.md` - "Reference materials and guides"

**Step 4: Upload your exercises**
1. Click "Add file" → "Upload files"
2. Upload `markdown-practice.md` and `first-structured-prompt.md` from exercises 1.1 and 1.2
3. Add commit message: "Add Week 1 exercises"
4. Click "Commit changes"

**Step 5: Update the main README**
Edit the `README.md` file to describe your library:

```markdown
# My AI Prompt Library

## Purpose
Personal library of AI prompts, templates, and resources developed
during the AI Prompting Mastery training program.

## Contents
- `/templates` - Reusable prompt templates
- `/examples` - Prompt + response examples
- `/resources` - Reference materials

## Week 1 Files
- `markdown-practice.md` - Markdown syntax practice
- `first-structured-prompt.md` - First structured prompt using ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework

## How to Use
[Will be developed as library grows]
```

---

#### Deliverable Specification

**Deliverable:** GitHub repository URL

**Quality Criteria:**
- [ ] Repository created with README
- [ ] Three folders created (templates, examples, resources)
- [ ] Week 1 exercise files uploaded
- [ ] README describes the purpose

---

#### Tips & Troubleshooting

**Tips:**
- You can create folders by including "/" in the filename when adding a new file
- Commit messages should describe what changed (not "update" or "changes")

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Can't create folder | Type `foldername/filename.md` when adding new file |
| File won't upload | Check file size (max 25MB), refresh and try again |
| Made a mistake | Edit the file (pencil icon) or delete and re-upload |

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| ASK-CONTEXT-CONSTRAINTS-EXAMPLE Template | Structure any prompt | Below |
| Markdown Quick Reference | Syntax reminder | Below |

---

### Template 1: ASK-CONTEXT-CONSTRAINTS-EXAMPLE Template

```markdown
# ASK
[State clearly what you want the AI to create, analyze, or do]
- Be specific about the deliverable type
- Include the action you want (write, analyze, summarize, etc.)

# CONTEXT
[Provide background information the AI needs]
- Who is involved (names, roles, relationships)
- What situation this relates to
- Any relevant history or constraints
- Key facts or data points

# CONSTRAINTS
- [Tone requirement: e.g., professional, casual, technical]
- [Length requirement: e.g., 200 words, 3 paragraphs]
- [Format requirement: e.g., bullet points, email format]
- [What to include: e.g., specific sections or elements]
- [What to avoid: e.g., jargon, specific topics]

# EXAMPLE (optional but powerful)
[Show a sample of the output format or style you want]
This could be:
- A few sentences showing your preferred tone
- A template structure to follow
- An excerpt from similar past work
```

**Usage Instructions:**
1. Copy this template for each new prompt
2. Fill in all sections with specific details
3. Remove the instructional text in brackets
4. Test and refine based on results

---

### Template 2: Markdown Quick Reference

```markdown
# Headers
# H1 - Main title
## H2 - Section
### H3 - Subsection

# Lists
- Bullet point
- Another point
  - Nested point

1. Numbered item
2. Another numbered item

# Emphasis
**bold text**
*italic text*
`inline code`

# Code Blocks
​```
Multi-line code or data
goes here
​```

# Links
[Link text](https://url.com)

# Tables
| Column 1 | Column 2 |
|----------|----------|
| Data 1   | Data 2   |
```

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Markdown Tutorial | Interactive Tutorial | [markdowntutorial.com](https://www.markdowntutorial.com/) | Practice syntax |
| Markdown Guide | Documentation | [markdownguide.org](https://www.markdownguide.org/) | Reference |
| Dillinger | Online Editor | [dillinger.io](https://dillinger.io/) | Preview Markdown |
| GitHub Docs | Tutorial | [docs.github.com](https://docs.github.com/en/get-started) | GitHub help |
| Claude | AI Platform | [claude.ai](https://claude.ai) | Test prompts |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Write valid Markdown with all essential elements | Exercise 1.1 file renders correctly | ☐ |
| 2 | Structure prompts using ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework | Exercise 1.2 uses all four sections | ☐ |
| 3 | Use GitHub for file storage and version control | Repository exists with files uploaded | ☐ |
| 4 | Explain why structure improves AI outputs | Your analysis in Exercise 1.2 | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 1.1 output | `markdown-practice.md` | GitHub repo | ☐ |
| Exercise 1.2 output | `first-structured-prompt.md` | GitHub repo | ☐ |
| Exercise 1.3 output | Repository URL | GitHub | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** What concept or technique suddenly made sense?

2. **What's still fuzzy?** What do you need more practice or clarification on?

3. **How will you apply this?** Name one real work deliverable where you'll use structured prompting.

4. **What surprised you?** Was anything harder or easier than expected?

---

## Getting Help

### Quick Answers
- **Participant Resources:** Check the resources section above
- **Peer Discussion:** Connect with your cohort for quick tips

### Common Questions This Week

**Q: Do I have to use this exact framework for every prompt?**
A: The framework is a starting point. For simple questions, you don't need all four sections. For complex, repeatable tasks, the full framework ensures consistency.

**Q: My Markdown isn't rendering correctly - what's wrong?**
A: Most common issues: missing space after # in headers, missing blank lines before lists, or unmatched backticks for code blocks.

**Q: How do I know if my GitHub repo is set up correctly?**
A: If you can navigate to your repo URL and see your files, you're set. The folder structure should match what's described in Exercise 1.3.

### When to Ask for Help

- **Before asking:** Check this guide's troubleshooting sections
- **Good to ask:** "I tried [X] but got [Y] result. Here's what I expected..."
- **Include:** Your specific scenario, what you tried, and the result

---

## Looking Ahead

### Next Week Preview: Week 2 - Advanced Prompting + Platform Optimization

**Focus:**
Role prompting, few-shot learning, and optimizing prompts for different AI platforms.

**How It Builds on This Week:**
The structured prompts you create this week become the foundation for adding advanced techniques next week.

**To Prepare:**
- [ ] Complete all Week 1 exercises
- [ ] Test at least 2-3 more prompts using the framework
- [ ] Note which prompts work well and which don't
- [ ] Bring questions about prompt structure to Week 2

---

## Glossary

| Term | Definition |
|------|------------|
| **Markdown** | A lightweight text formatting language using symbols like # and * |
| **ASK** | The section of a prompt that states what you want the AI to do |
| **CONTEXT** | Background information the AI needs to complete the task |
| **CONSTRAINTS** | Rules, requirements, and limitations for the output |
| **EXAMPLE** | A sample showing the desired format or style |
| **Repository (repo)** | A project folder on GitHub for storing and tracking files |
| **Commit** | A saved version of changes to files in a repository |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** **Week 1** | [Next Week →](../week-2/participant-guide.md)
