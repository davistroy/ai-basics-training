# Week 3: JSON Fundamentals + GitHub Basics

**Block:** 1 - AI Prompting Mastery
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Week 2 exercises completed
- [ ] Role prompting and few-shot learning practiced
- [ ] Platform comparison document created
- [ ] GitHub repository active

## Exit Criteria

- [ ] Can read and write basic JSON structures
- [ ] Understands JSON for AI configuration (`style.json` concept)
- [ ] Can perform basic GitHub operations (commit, push, pull)
- [ ] First `style.json` file created

---

## Workshop Content (45 minutes)

### Segment 1: Why JSON? (8 min)

**The problem:**
- AI outputs vary based on mood, context, time
- Hard to ensure consistent style, tone, format
- Manual checking doesn't scale

**The solution: Configuration files**
- Store your preferences in structured format
- Reference them in every prompt
- AI follows documented standards

**Why JSON specifically:**
- Human-readable and writable
- Supported by all AI platforms
- Standard data format (used everywhere)
- Easy to version control

**Preview: `style.json`**
```json
{
  "voice": "professional but approachable",
  "sentence_length": "medium (15-25 words)",
  "avoid": ["jargon", "passive voice", "clichés"]
}
```

### Segment 2: JSON Syntax Essentials (15 min)

**Basic structure:**
```json
{
  "key": "value"
}
```

**Data types:**
```json
{
  "string": "text in quotes",
  "number": 42,
  "decimal": 3.14,
  "boolean": true,
  "null_value": null,
  "array": ["item1", "item2", "item3"],
  "object": {
    "nested_key": "nested_value"
  }
}
```

**Common mistakes:**
```json
// WRONG - trailing comma
{
  "name": "John",
  "age": 30,  // <- This comma breaks JSON
}

// WRONG - single quotes
{
  'name': 'John'  // Must use double quotes
}

// CORRECT
{
  "name": "John",
  "age": 30
}
```

**Validation:**
- Use [JSONLint](https://jsonlint.com/) to check syntax
- Most code editors highlight JSON errors
- Invalid JSON = prompt failure

**Live demo:** Building a JSON configuration step by step

### Segment 3: Creating Your `style.json` (10 min)

**The `style.json` concept:**
- Central file defining your writing preferences
- Reference in prompts for consistency
- Evolves as you refine your style

**Template:**
```json
{
  "voice": {
    "tone": "professional but approachable",
    "formality": "business casual",
    "personality": "helpful and direct"
  },
  "writing": {
    "sentence_length": "medium (15-25 words average)",
    "paragraph_length": "3-5 sentences",
    "structure": "clear headers, bulleted lists for complex info"
  },
  "preferences": {
    "use": ["active voice", "concrete examples", "clear transitions"],
    "avoid": ["jargon", "clichés", "passive voice", "hedge words"]
  },
  "formatting": {
    "headers": "sentence case",
    "lists": "parallel structure",
    "emphasis": "bold for key terms, italics for new concepts"
  }
}
```

**How to use in prompts:**
```markdown
Follow this style guide for all writing:

<style>
[Paste your style.json content]
</style>

Now write: [Your request]
```

### Segment 4: GitHub Basics (12 min)

**Why GitHub for prompts:**
- Version history (see what changed, when)
- Backup (never lose your work)
- Collaboration (share with team)
- Professional practice

**Key concepts:**
- **Repository:** Your project folder
- **Commit:** A saved snapshot with description
- **Push:** Upload commits to GitHub
- **Pull:** Download latest changes
- **Branch:** Parallel version for experiments

**Basic workflow (web interface):**
1. Edit file on GitHub
2. Write commit message describing change
3. Click "Commit changes"

**Basic workflow (desktop):**
1. Make changes locally
2. Stage changes: `git add .`
3. Commit: `git commit -m "Description of change"`
4. Push: `git push`

**Commit message best practices:**
```
Good: "Add email response template with formal tone option"
Bad: "Updated stuff"
Bad: "Changes"
```

---

## Self-Paced Exercises (60 minutes total)

### Exercise 3.1: JSON Practice (15 minutes)

*Build comfort with JSON syntax*

1. Create a file called `json-practice.json`
2. Write valid JSON that includes:
   - At least 5 different keys
   - A string, number, boolean, and array
   - A nested object (object inside object)

3. Validate at [JSONLint.com](https://jsonlint.com/)
4. Fix any errors until valid

**Example structure:**
```json
{
  "project_name": "My AI Library",
  "version": 1.0,
  "active": true,
  "tags": ["prompts", "templates", "ai"],
  "metadata": {
    "created": "2024-01-01",
    "author": "Your Name"
  }
}
```

**Deliverable:** Valid `json-practice.json` file

---

### Exercise 3.2: Create Your `style.json` (25 minutes)

*Define your personal writing style*

1. Reflect on your preferred writing style:
   - How do you want to sound?
   - What do you always include?
   - What do you avoid?

2. Create `style.json` using this template:

```json
{
  "voice": {
    "tone": "[Your preferred tone]",
    "formality": "[casual/business casual/formal]",
    "personality": "[Descriptive words]"
  },
  "writing": {
    "sentence_length": "[short/medium/long with example word counts]",
    "paragraph_length": "[number of sentences]",
    "structure_preference": "[How you like content organized]"
  },
  "preferences": {
    "always_use": [
      "[Thing 1]",
      "[Thing 2]",
      "[Thing 3]"
    ],
    "always_avoid": [
      "[Thing 1]",
      "[Thing 2]",
      "[Thing 3]"
    ]
  },
  "domain_specific": {
    "[Your field]": {
      "terminology": "[preferred terms]",
      "conventions": "[field-specific rules]"
    }
  }
}
```

3. Validate your JSON
4. Test it: Create a prompt that references your `style.json` and generate content
5. Refine based on results

**Deliverable:** `style.json` + test prompt + AI response showing style application

---

### Exercise 3.3: GitHub Practice (20 minutes)

*Learn version control basics*

1. **Using GitHub web interface:**
   - Go to your repository
   - Click "Add file" → "Create new file"
   - Add your `style.json` from Exercise 3.2
   - Write a meaningful commit message
   - Commit the file

2. **Make an edit:**
   - Click on `style.json`
   - Click the pencil icon to edit
   - Make a small change (add a preference)
   - Write commit message describing the change
   - Commit

3. **View history:**
   - Go to your repository main page
   - Click on "Commits" or the commit count
   - Click on a commit to see what changed
   - Notice the "diff" view (red = removed, green = added)

4. **Document your repository:**
   - Edit your `README.md`
   - Add a description of your prompt library
   - List what files are included
   - Commit the change

**Deliverable:**
- `style.json` in your GitHub repository
- At least 3 commits with meaningful messages
- Updated `README.md`

**Optional (if comfortable with command line):**
- Install [GitHub Desktop](https://desktop.github.com/) or Git
- Clone your repository locally
- Make changes and push from your computer

---

## Key Takeaways

1. **JSON provides structured configuration** that AI can parse and follow
2. **`style.json` creates consistency** across all your AI-generated content
3. **Version control (GitHub) tracks evolution** of your prompts and configurations
4. **Meaningful commit messages** make it easy to understand changes over time
5. **Validation is essential** - always check JSON syntax before using

---

## Preparation for Week 4

- Complete all Week 3 exercises
- Use your `style.json` in at least 5 prompts this week
- Note: Does the AI follow your style guide? Where does it deviate?
- Next week: Quality rubrics and workflow design

---

## Resources

- [JSON.org](https://www.json.org/json-en.html) - Official JSON specification
- [JSONLint](https://jsonlint.com/) - JSON validator
- [GitHub Docs](https://docs.github.com/en/get-started) - Getting started guide
- [GitHub Desktop](https://desktop.github.com/) - GUI for Git operations
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf) - Command reference
