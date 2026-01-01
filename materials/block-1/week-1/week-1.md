# Week 1: Markdown Fundamentals & Structured Prompting

**Block:** 1 - AI Prompting Mastery
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Self-assessment completed (prerequisites.md)
- [ ] GitHub account created
- [ ] AI platform access confirmed (Claude or ChatGPT)
- [ ] Understand basic text formatting concepts

## Exit Criteria

- [ ] Can write valid Markdown documents
- [ ] Understands structured prompting basics
- [ ] First structured prompt created and tested
- [ ] GitHub repository created for prompt library

---

## Workshop Content (45 minutes)

### Segment 1: Welcome & Program Overview (5 min)

- Welcome to AI Prompting Mastery
- Block 1 overview: 8 weeks to AI Prompting Practitioner certification
- Maturity model introduction:
  - Level 0: Ad-hoc prompting (where most start)
  - Level 1: Templated workflows (Block 1 goal)
  - Level 2: Workflow engineering (Block 2)
  - Level 3: Automation architecture (Block 3)
- What success looks like: Consistent, high-quality AI outputs

### Segment 2: Why Markdown Matters (8 min)

- **The problem:** Unstructured prompts produce inconsistent results
- **The solution:** Markdown provides structure that AI models understand
- **Key insight:** AI models are trained on millions of Markdown documents
- **Benefits:**
  - Clear visual hierarchy
  - Consistent formatting
  - Portable across platforms
  - Version control friendly

### Segment 3: Markdown Essentials (15 min)

**Headers (document structure):**
```markdown
# Main Title (H1)
## Section (H2)
### Subsection (H3)
```

**Lists (organizing information):**
```markdown
- Bullet point
- Another point
  - Nested point

1. First item
2. Second item
```

**Emphasis and formatting:**
```markdown
**Bold text** for emphasis
*Italic text* for terms
`Code` for technical items
```

**Code blocks:**
```markdown
\`\`\`python
def example():
    return "Hello"
\`\`\`
```

**Links and references:**
```markdown
[Link text](URL)
![Image alt](image-url)
```

**Live demo:** Converting unstructured notes to Markdown

### Segment 4: Structured Prompting Fundamentals (12 min)

- **Why structure prompts?**
  - Reduces ambiguity
  - Improves consistency
  - Makes prompts reusable
  - Easier to iterate and improve

- **The ASK-CONTEXT-CONSTRAINTS-EXAMPLE Framework:**

  ```markdown
  # ASK
  [What you want the AI to do - be specific]

  # CONTEXT
  [Background information the AI needs]

  # CONSTRAINTS
  [Limitations, format requirements, what to avoid]

  # EXAMPLE (optional but powerful)
  [Show what good output looks like]
  ```

- **Quick demonstration:** Transform a vague request into a structured prompt

### Segment 5: Preview of Week 1 Exercises (5 min)

- Exercise overview
- How to submit work
- Questions and setup help

---

## Self-Paced Exercises (60 minutes total)

### Exercise 1.1: Markdown Practice Document (20 minutes)

*Build muscle memory with Markdown syntax*

1. Create a new file called `markdown-practice.md`
2. Write a document that includes:
   - A title (H1) and at least two sections (H2)
   - A numbered list of 3+ items
   - A bulleted list with nested items
   - Bold and italic text
   - A code block (any language)
   - A link to any website

3. Preview your Markdown in:
   - VS Code with preview pane
   - GitHub (paste into any repository README)
   - Online: [Dillinger](https://dillinger.io/) or [StackEdit](https://stackedit.io/)

**Deliverable:** `markdown-practice.md` file

**Tips:**
- If preview looks wrong, check for missing blank lines
- Headers need a space after the #
- Code blocks need matching backticks

---

### Exercise 1.2: First Structured Prompt (25 minutes)

*Apply the ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework*

1. Choose a simple task you've asked AI to help with before
2. Rewrite it using the framework:

```markdown
# ASK
[Clear, specific request]

# CONTEXT
[Relevant background - who you are, what this is for]

# CONSTRAINTS
- [Constraint 1]
- [Constraint 2]
- [Format requirements]

# EXAMPLE
[Optional: Show what good output looks like]
```

3. Test your prompt in Claude or ChatGPT
4. Save the prompt AND the response

**Deliverable:** `first-structured-prompt.md` with:
- Your structured prompt
- The AI's response
- 2-3 sentences: Did structure improve the output? How?

**Sample task ideas:**
- Write a professional email
- Explain a concept
- Create a meeting agenda
- Draft social media content

---

### Exercise 1.3: GitHub Repository Setup (15 minutes)

*Create your prompt library home*

1. Go to [github.com](https://github.com) and sign in
2. Click "New repository"
3. Configure:
   - Name: `ai-prompt-library` (or similar)
   - Description: "My personal AI prompt library"
   - Visibility: Private (recommended) or Public
   - Check "Add a README file"
4. Create the repository
5. Add a basic structure:

```
ai-prompt-library/
├── README.md          # Overview of your library
├── templates/         # Reusable prompt templates
├── examples/          # Prompt + response examples
└── resources/         # Reference materials
```

6. Upload your files from exercises 1.1 and 1.2

**Deliverable:** Link to your GitHub repository

**If you're new to GitHub:**
- You can create folders by typing `templates/README.md` in "Add file"
- Use the web interface for now; we'll cover Git basics in Week 3

---

## Key Takeaways

1. **Markdown provides structure** that AI models understand and respect
2. **The ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework** transforms vague requests into clear instructions
3. **Version control (GitHub)** enables iteration and improvement of prompts over time
4. **Practice is essential** - the more you write structured prompts, the more natural it becomes

---

## Preparation for Week 2

- Complete all Week 1 exercises
- Test at least 3 more prompts using the structured framework
- Note which prompts work well and which don't
- Bring questions about prompt structure to Week 2

---

## Resources

- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub Markdown Documentation](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Dillinger Online Markdown Editor](https://dillinger.io/)
- [Claude Prompting Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
