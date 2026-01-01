# **BLOCK 1 WEEK 3: JSON Fundamentals + GitHub Basics**

**Block:** 1: AI Prompting Mastery
**Week:** 3 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** [← Previous Week](../week-2/participant-guide.md) | **Week 3** | [Next Week →](../week-4/participant-guide.md)

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
| 1 | Read and write valid JSON structures with multiple data types | Exercise 3.1 |
| 2 | Create a personal style.json file defining your writing preferences | Exercise 3.2 |
| 3 | Perform basic GitHub operations (commit, push, version history) | Exercise 3.3 |
| 4 | Reference configuration files in prompts for consistent output | Exercise 3.2 + All future work |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Week 2 exercises (role prompting, few-shot template, platform comparison)
- [ ] At least one few-shot template created and tested
- [ ] GitHub repository active with Week 1-2 files uploaded
- [ ] Comfortable with basic Markdown formatting

**Not ready?** Complete the [Week 2 exercises](../week-2/participant-guide.md) first - the style preferences you've developed inform this week's work.

---

## Key Concepts

### Concept 1: Why JSON for AI Configuration

**Definition:**
JSON (JavaScript Object Notation) is a text-based format for storing structured data using key-value pairs.

**Why It Matters:**
AI outputs vary even with identical prompts. A configuration file stores your preferences once and applies them consistently every time.

**Core Principle:**
> Configuration files turn variable outputs into consistent, predictable results.

**Example:**
```json
{
  "voice": {
    "tone": "professional but approachable",
    "formality": "business casual"
  },
  "avoid": ["jargon", "passive voice", "cliches"]
}
```

**Common Mistake:**
Trying to remember and type preferences each time instead of storing them once and referencing consistently.

---

### Concept 2: JSON Syntax Essentials

**Definition:**
JSON uses a simple structure of keys (names) and values (data) enclosed in curly braces.

**Why It Matters:**
Invalid JSON breaks everything. Understanding the rules prevents frustrating errors.

**The Pattern:**
```json
{
  "key": "value",
  "another_key": "another value"
}
```

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| **Object** | Container with key-value pairs | `{ }` |
| **Key** | Name in double quotes | `"name"` |
| **String** | Text in double quotes | `"hello"` |
| **Number** | Numeric value (no quotes) | `42`, `3.14` |
| **Boolean** | True or false (no quotes) | `true`, `false` |
| **Array** | List in square brackets | `["a", "b", "c"]` |
| **Null** | Empty/no value | `null` |

**Visual Reference:**
```
JSON Structure:
{
  "string": "text in quotes",          ← String
  "number": 42,                         ← Number (no quotes)
  "boolean": true,                      ← Boolean (no quotes)
  "array": ["item1", "item2"],          ← Array with brackets
  "object": {                           ← Nested object
    "nested_key": "nested_value"
  }
}
```

---

### Concept 3: Common JSON Errors

**Definition:**
JSON has strict syntax rules. Small mistakes cause complete failure.

**Why It Matters:**
Unlike Markdown where errors just look wrong, JSON errors break parsing entirely.

**Top Errors to Avoid:**

| Error | Wrong | Right |
|-------|-------|-------|
| Trailing comma | `"name": "value",` (at end) | `"name": "value"` |
| Single quotes | `'name': 'value'` | `"name": "value"` |
| Unquoted keys | `name: "value"` | `"name": "value"` |
| Missing comma | `"a": 1 "b": 2` | `"a": 1, "b": 2` |

**The Rule:**
> Always validate with JSONLint before using. Always.

---

### Concept 4: The style.json Concept

**Definition:**
A configuration file that captures your personal writing preferences for consistent AI outputs.

**Why It Matters:**
Your "voice" becomes reproducible. Every prompt references the same style guide.

**What to Include:**
- Voice and tone preferences
- Writing style (sentence length, structure)
- Things to always do
- Things to always avoid
- Domain-specific preferences

**Example Usage in Prompts:**
```markdown
Follow this style guide for all writing:

<style>
{
  "tone": "professional but approachable",
  "preferences": {
    "use": ["active voice", "concrete examples"],
    "avoid": ["jargon", "passive voice"]
  }
}
</style>

Now write: [Your request]
```

---

### Concept 5: GitHub Version Control

**Definition:**
Version control tracks changes to files over time, allowing you to see history and collaborate safely.

**Why It Matters:**
You can see what changed, when, and why. You can revert mistakes. You can collaborate without overwriting each other's work.

**Key Concepts:**

| Term | Definition | Analogy |
|------|------------|---------|
| **Repository** | Project folder containing all files | A filing cabinet |
| **Commit** | Saved snapshot with description | Saving a video game |
| **Push** | Upload commits to GitHub | Syncing to cloud |
| **Pull** | Download latest changes | Getting updates |
| **History** | Record of all commits | Change log |

**The Workflow:**
```
1. Make changes to files
2. Stage changes (select what to save)
3. Commit with message (save snapshot)
4. Push to GitHub (upload)
```

---

### Quick Reference: JSON Data Types

| Type | Syntax | Example | When to Use |
|------|--------|---------|-------------|
| String | Double quotes | `"hello"` | Text, labels |
| Number | No quotes | `42` or `3.14` | Quantities, scores |
| Boolean | `true` / `false` | `true` | Yes/no settings |
| Null | `null` | `null` | Empty/unknown values |
| Array | `[]` brackets | `["a", "b"]` | Lists of items |
| Object | `{}` braces | `{"key": "value"}` | Grouped settings |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Learning JSON for configuration files and GitHub for version control - the infrastructure that makes your prompts consistent and trackable.

**Key Points from Each Segment:**

**Segment 1: Why JSON?**
- AI outputs vary even with identical prompts
- Configuration files store preferences for consistent application
- JSON is human-readable AND machine-readable
- Key takeaway: Store once, reference always

**Segment 2: JSON Syntax Essentials**
- Key-value pairs in curly braces
- Multiple data types: strings, numbers, booleans, arrays, objects
- Strict syntax - always validate
- Key takeaway: Trailing commas are the #1 error

**Segment 3: Creating style.json**
- Captures voice, preferences, things to avoid
- Reference in prompts for consistent output
- Personal - customize to your actual preferences
- Key takeaway: This becomes your voice in code

**Segment 4: GitHub Basics**
- Version control tracks all changes
- Commits are snapshots with descriptions
- Good commit messages explain what and why
- Key takeaway: Commit messages are notes to future you

### Demo Recap

**What Was Demonstrated:**
Building a style.json file step-by-step, showing validation with JSONLint, and fixing common errors.

**Key Steps:**
1. Started with empty JSON object `{}`
2. Added voice configuration
3. Added preferences arrays
4. Showed trailing comma error in JSONLint
5. Fixed error, showed successful validation

**Result:**
A valid style.json that can be referenced in any prompt for consistent output.

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 3.1 | 15 min | `json-practice.json` | JSON syntax |
| 3.2 | 25 min | `style.json` + test | Personal configuration |
| 3.3 | 20 min | GitHub activity | Version control |

---

### Exercise 3.1: JSON Practice

**Duration:** 15 minutes

**Purpose:**
Build familiarity with JSON syntax by creating a file that uses all the major data types.

**You Will Create:**
A valid JSON file demonstrating strings, numbers, booleans, arrays, and nested objects.

---

#### Instructions

**Step 1: Create a new file**
Create a file called `json-practice.json` in your text editor.

**Step 2: Build the structure**
Create valid JSON that includes:
- At least 5 different keys
- A string value
- A number value
- A boolean value
- An array (list) with 3+ items
- A nested object (object inside object)

**Step 3: Use this template as a starting point**

```json
{
  "project_name": "My AI Library",
  "version": 1.0,
  "active": true,
  "tags": ["prompts", "templates", "ai"],
  "metadata": {
    "created": "2025-01-01",
    "author": "Your Name"
  }
}
```

**Step 4: Customize with your own content**
Change the values to something relevant to you or your work.

**Step 5: Validate**
Go to [JSONLint.com](https://jsonlint.com/), paste your JSON, click "Validate JSON."

**Step 6: Fix any errors**
If validation fails:
- Check for trailing commas (comma after last item)
- Ensure all strings use double quotes
- Verify all keys are in double quotes
- Check for missing commas between items

---

#### Deliverable Specification

**File Name:** `json-practice.json`

**Location:** Upload to your GitHub repository

**Format Requirements:**
- Valid JSON (passes JSONLint validation)
- Contains all required data types

**Quality Criteria:**
- [ ] Contains string, number, boolean, array, and nested object
- [ ] Passes JSONLint validation
- [ ] Contains meaningful content (not just template values)

---

#### Example

**Scenario:** Creating a project configuration

**Output:**
```json
{
  "project_name": "Client Proposal Templates",
  "version": 2.1,
  "is_production": true,
  "priority": 1,
  "categories": [
    "proposals",
    "client-facing",
    "sales"
  ],
  "settings": {
    "auto_validate": true,
    "default_tone": "professional",
    "max_length": 2000
  },
  "team": [
    "Alice",
    "Bob",
    "Charlie"
  ]
}
```

**Why This Works:**
Uses all required data types in a realistic structure. Each value serves a purpose.

---

#### Tips & Troubleshooting

**Tips:**
- Start simple, add complexity gradually
- Validate after each major addition
- Use indentation for readability (2 spaces is standard)

**Common Issues:**

| Problem | Solution |
|---------|----------|
| "Expecting string" error | Make sure keys are in double quotes |
| "Trailing comma" error | Remove comma after the last item in objects/arrays |
| "Invalid syntax" | Check for single quotes - must use double quotes |

---

### Exercise 3.2: Create Your style.json

**Duration:** 25 minutes

**Purpose:**
Define your personal writing style in a configuration file that you'll reference in prompts for consistent output.

**You Will Create:**
A style.json file capturing your voice, plus test results showing it works.

---

#### Instructions

**Step 1: Reflect on your preferences**
Before writing JSON, consider:
- How do you want your writing to sound? (tone)
- What's your preferred level of formality?
- What do you always try to include?
- What do you always try to avoid?
- Any domain-specific preferences?

**Step 2: Create style.json using this template**

```json
{
  "voice": {
    "tone": "[Your preferred tone]",
    "formality": "[casual/business casual/formal]",
    "personality": "[Descriptive words for your voice]"
  },
  "writing": {
    "sentence_length": "[short/medium/long - with word counts]",
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
  "formatting": {
    "headers": "[sentence case/title case]",
    "lists": "[parallel structure requirements]",
    "emphasis": "[how you use bold/italic]"
  }
}
```

**Step 3: Fill in with YOUR actual preferences**
Don't just copy the template - make it reflect your real style.

**Step 4: Validate with JSONLint**
Paste into [JSONLint.com](https://jsonlint.com/) and fix any errors.

**Step 5: Test your style.json**
Create a prompt that references your style:

```markdown
Follow this style guide for all writing:

<style>
[Paste your style.json content here]
</style>

Write a 2-paragraph overview of [any topic you know well].
```

**Step 6: Evaluate the result**
- Did the AI follow your tone preferences?
- Did it use the structure you specified?
- Did it avoid the things you listed?

**Step 7: Refine if needed**
If the AI didn't follow something, make that preference more explicit.

---

#### Deliverable Specification

**File Name:** `style.json`

**Location:** Upload to your GitHub repository (in `/resources` folder)

**Also Include:** A test document showing:
- Your test prompt (with style.json included)
- The AI's response
- Brief evaluation of how well style was followed

**Quality Criteria:**
- [ ] Valid JSON (passes validation)
- [ ] Personalized content (not just template)
- [ ] Test results included
- [ ] Evaluation of style adherence

---

#### Example

**Scenario:** A consultant creating their style guide

**style.json:**
```json
{
  "voice": {
    "tone": "professional but approachable",
    "formality": "business casual",
    "personality": "helpful, direct, thoughtful"
  },
  "writing": {
    "sentence_length": "medium (15-25 words average)",
    "paragraph_length": "3-5 sentences",
    "structure_preference": "clear headers, bulleted lists for complex info"
  },
  "preferences": {
    "always_use": [
      "active voice",
      "concrete examples",
      "clear transitions",
      "specific numbers over vague quantities"
    ],
    "always_avoid": [
      "jargon without explanation",
      "cliches and buzzwords",
      "passive voice",
      "hedge words (might, perhaps, maybe)"
    ]
  },
  "formatting": {
    "headers": "sentence case",
    "lists": "parallel structure required",
    "emphasis": "bold for key terms, italics for definitions"
  }
}
```

---

### Exercise 3.3: GitHub Practice

**Duration:** 20 minutes

**Purpose:**
Build familiarity with GitHub version control through practical use.

**You Will Create:**
A series of meaningful commits to your repository.

---

#### Instructions

**Step 1: Add your new files**
Using the GitHub web interface:
1. Go to your repository
2. Click "Add file" → "Upload files"
3. Upload `json-practice.json` and `style.json`
4. Write a meaningful commit message: "Add Week 3 JSON practice and style configuration"
5. Click "Commit changes"

**Step 2: Edit an existing file**
1. Click on your main README.md
2. Click the pencil icon to edit
3. Add a section about your style configuration:
```markdown
## Style Configuration

This repository includes a `style.json` file in `/resources` that defines
my personal writing preferences. Reference this file in prompts for
consistent output.
```
4. Write commit message: "Add style configuration section to README"
5. Click "Commit changes"

**Step 3: View your history**
1. Go to your repository main page
2. Click on "Commits" (or the commit count number)
3. Browse the list of all your commits
4. Click on one commit to see the "diff" (what changed)

**Step 4: Update your repository README**
Add information about Week 3 deliverables:
```markdown
## Week 3 Files
- `json-practice.json` - JSON syntax practice
- `resources/style.json` - Personal style configuration
```

**Step 5: Commit with descriptive message**
"Update README with Week 3 deliverables list"

---

#### Deliverable Specification

**Deliverable:** GitHub activity showing:
- Files uploaded (json-practice.json, style.json)
- At least 3 commits with meaningful messages
- Updated README.md

**Quality Criteria:**
- [ ] New files added to repository
- [ ] At least 3 commits
- [ ] Commit messages describe what changed (not "updates")
- [ ] README updated with Week 3 information

---

#### Tips & Troubleshooting

**Tips:**
- Make commits as you work, not all at the end
- Write commit messages as if explaining to a colleague
- Check the diff view to understand what changed

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Can't find where to edit | Click the file name, then the pencil icon |
| Commit button grayed out | You need to write a commit message first |
| Don't see file changes | Check if you're on the right branch (main) |

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| style.json Template | Personal style configuration | Below |
| JSON Quick Reference | Syntax reminder | Key Concepts section |

---

### Template: Complete style.json

```json
{
  "metadata": {
    "version": "1.0",
    "last_updated": "YYYY-MM-DD",
    "author": "Your Name"
  },
  "voice": {
    "tone": "professional but approachable",
    "formality": "business casual",
    "personality_traits": ["helpful", "direct", "thoughtful"]
  },
  "writing": {
    "sentence_length": "medium (15-25 words average)",
    "paragraph_length": "3-5 sentences",
    "structure": "clear headers, bulleted lists for complex information"
  },
  "preferences": {
    "always_use": [
      "active voice",
      "concrete examples",
      "clear transitions",
      "specific numbers over vague quantities"
    ],
    "always_avoid": [
      "jargon without explanation",
      "cliches",
      "passive voice",
      "hedge words (might, perhaps, maybe)"
    ]
  },
  "formatting": {
    "headers": "sentence case",
    "lists": "parallel structure required",
    "emphasis": "bold for key terms, italics for definitions",
    "code": "include language identifier"
  },
  "domain_specific": {
    "your_field": {
      "terminology": "preferred terms",
      "conventions": "field-specific rules"
    }
  }
}
```

**Usage Instructions:**
1. Copy this template
2. Customize ALL values to reflect YOUR preferences
3. Validate with JSONLint
4. Save in your `/resources` folder
5. Reference in prompts by pasting the content

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| JSONLint | Validator | [jsonlint.com](https://jsonlint.com/) | Validate JSON (required!) |
| JSON.org | Documentation | [json.org](https://www.json.org/json-en.html) | Understand specification |
| GitHub Docs | Tutorial | [docs.github.com](https://docs.github.com/en/get-started) | GitHub help |
| GitHub Desktop | Tool | [desktop.github.com](https://desktop.github.com/) | GUI for Git operations |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Write valid JSON with multiple data types | Exercise 3.1 passes JSONLint | ☐ |
| 2 | Create personalized style.json | Exercise 3.2 with custom content | ☐ |
| 3 | Reference configuration in prompts | Test results in Exercise 3.2 | ☐ |
| 4 | Make meaningful GitHub commits | Exercise 3.3 with good messages | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 3.1 output | `json-practice.json` | GitHub repo | ☐ |
| Exercise 3.2 output | `style.json` + test | GitHub repo `/resources` | ☐ |
| Exercise 3.3 output | Commit history | GitHub | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** Did the JSON syntax make sense, or did it take practice?

2. **What's still fuzzy?** Are there JSON concepts you need to review?

3. **How will you apply this?** What other preferences could you capture in JSON configuration?

4. **What surprised you?** Was JSON easier or harder than expected? How about version control?

---

## Getting Help

### Quick Answers
- **JSON Validation Errors:** Use JSONLint - it shows exactly where the error is
- **GitHub Confusion:** Use the web interface for everything in Block 1

### Common Questions This Week

**Q: My JSON won't validate but I can't find the error.**
A: Most likely a trailing comma. Look at the last item before each closing brace `}` or bracket `]`. If there's a comma, remove it.

**Q: How detailed should my style.json be?**
A: Start with the basics (tone, preferences, avoid). Add more detail only if AI outputs aren't matching your expectations.

**Q: Do I need to memorize JSON syntax?**
A: No - you just need to recognize valid structure and use JSONLint to catch errors. The templates give you patterns to follow.

### When to Ask for Help

- **Before asking:** Validate with JSONLint and read the error message
- **Good to ask:** "My JSON validates but the AI isn't following my style for [specific preference]"
- **Include:** Your actual JSON and the prompt you used

---

## Looking Ahead

### Next Week Preview: Week 4 - Quality Rubrics + Workflow Design

**Focus:**
Creating quality evaluation rubrics and learning the LLM-as-judge pattern.

**How It Builds on This Week:**
Your style.json becomes part of how you evaluate outputs. Does the AI match your documented style?

**To Prepare:**
- [ ] Complete all Week 3 exercises
- [ ] Use your style.json in at least 5 prompts this week
- [ ] Note: Where does AI follow your style? Where does it deviate?
- [ ] Think about: How would you rate AI output quality?

---

## Glossary

| Term | Definition |
|------|------------|
| **JSON** | JavaScript Object Notation - text format for structured data |
| **Key** | The name part of a key-value pair (always in double quotes) |
| **Value** | The data part of a key-value pair (type varies) |
| **Object** | Container for key-value pairs using `{ }` |
| **Array** | Ordered list of values using `[ ]` |
| **Repository** | Project folder on GitHub containing all files |
| **Commit** | Saved snapshot of changes with description |
| **Push** | Upload commits to GitHub |
| **Diff** | Comparison showing what changed between versions |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [← Previous Week](../week-2/participant-guide.md) | **Week 3** | [Next Week →](../week-4/participant-guide.md)
