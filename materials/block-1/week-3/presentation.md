# **POWERPOINT PRESENTATION: BLOCK 1 WEEK 3**
## **JSON Fundamentals + GitHub Basics**

**Block:** 1: AI Prompting Mastery
**Week Number:** 3
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Participants who completed Weeks 1-2 and have working prompt templates

**Key Thesis:** JSON configuration files transform scattered preferences into reusable infrastructure, while version control preserves the evolution of your prompting expertise—together they create a foundation that scales from personal use to team collaboration.

**Week Learning Objectives:** By the end of this session, participants will:
1. Read and write valid JSON structures with multiple data types
2. Create a personal `style.json` file defining writing preferences
3. Perform basic GitHub operations (commit, push, view history)
4. Understand how configuration files enable consistent AI outputs

**Entry Criteria:**
- [ ] Week 2 exercises completed
- [ ] Few-shot template created and tested
- [ ] GitHub repository active

**Exit Criteria:**
- [ ] Understands JSON syntax (objects, arrays, types)
- [ ] Knows how to validate JSON with JSONLint
- [ ] Has plan to create personal `style.json`
- [ ] Understands GitHub commit workflow

**Presentation Structure:**
1. Opening & Recap (5 min) - Slides 1-3
2. Segment 1: Why JSON? (8 min) - Slides 4-5
3. Segment 2: JSON Syntax Essentials (15 min) - Slides 6-10
4. Segment 3: Creating `style.json` (10 min) - Slides 11-13
5. Segment 4: GitHub Basics (7 min) - Slides 14-17

**Total Slides:** 17

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Block 1 Week 3: JSON Fundamentals + GitHub Basics

**Subtitle:** Infrastructure for Consistent AI Outputs

**Content:**
- AI Practitioner Training Program
- Block 1: AI Prompting Mastery
- Week 3 of 8

**Graphic:** Clean title slide with blue color scheme (Block 1 theme).

**GRAPHICS:**

**Graphic 1: Week 3 Title Slide**
- Purpose: Position JSON and GitHub as infrastructure supporting prompting techniques
- Type: Title slide with technical/infrastructure theme
- Elements: Blue gradient background (Block 1 theme), subtle code/structure patterns (JSON braces, version control tree), professional layout
- Labels: "AI Practitioner Training Program" (top), "Block 1: AI Prompting Mastery" (center), "Week 3 of 8" (subtitle), "JSON Fundamentals + GitHub Basics" title with "Infrastructure for Consistent AI Outputs"
- Relationships: Visual elements suggesting structure and organization (foundation theme)

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Week 3! We're at the midpoint of Block 1's content now.

Last two weeks were about prompting techniques - structure, roles, few-shot learning. This week, we're adding infrastructure.

JSON for configuration. GitHub for version control. These might feel more technical, but they're the foundation that makes everything else work better.

By the end of today, you'll understand how to store your preferences in a file and reference them in every prompt for consistent output."

[Transition: Click to next slide]

---

### SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-5 min | Opening | Week 2 Recap |
| 5-13 min | Segment 1 | Why JSON? |
| 13-28 min | Segment 2 | JSON Syntax Essentials |
| 28-38 min | Segment 3 | Creating `style.json` |
| 38-45 min | Segment 4 | GitHub Basics |

**Graphic:** Timeline with JSON and GitHub icons

**GRAPHICS:**

**Graphic 1: Week 3 Session Timeline**
- Purpose: Show balance between JSON (majority) and GitHub (foundation) content
- Type: Horizontal timeline with technology icons
- Elements: Five time segments, JSON icon (curly braces) prominent in segments 1-3, GitHub octocat icon in segment 4, arrows connecting segments
- Labels: Time markers, topic names, "Technical Foundation" theme, JSON and GitHub icons clearly visible
- Relationships: Left-to-right progression, visual emphasis on JSON syntax segment (longest duration)

**SPEAKER NOTES:**

"Here's our agenda:

First, a quick recap of Week 2. Then we'll cover why JSON matters for AI work.

The bulk of our time is on JSON syntax - this is the technical foundation. Then we'll apply it by looking at `style.json` - your personal voice configuration.

We'll close with GitHub basics - version control concepts you'll use going forward.

Let's start with a quick recap."

[Transition]

---

### SLIDE 3: WEEK 2 RECAP

**Title:** Quick Recap: Your Power Tools

**Content:**

**Role Prompting:**
```markdown
You are a [role] with expertise in [domain]...
```

**Few-Shot Learning:**
```markdown
# Examples
Input: [sample]
Output: [your ideal result]
```

**Platform Optimization:**
- Claude: XML tags, reasoning requests
- ChatGPT: Custom instructions, iteration

**The Question:**
How do we maintain consistency across ALL prompts?

**Graphic:** Three technique icons from Week 2

**GRAPHICS:**

**Graphic 1: Week 2 Techniques Recap**
- Purpose: Quick visual refresher of previous week's techniques
- Type: Icon summary with consistency question
- Elements: Three technique icons from Week 2 (role mask, example cards, platform logos), arranged horizontally, question mark or connecting lines suggesting need for unifying approach
- Labels: "Role Prompting", "Few-Shot Learning", "Platform Optimization" with minimal descriptors, "How do we maintain consistency?" question prominently displayed
- Relationships: Three separate techniques pointing to central challenge of consistency across all prompts

**SPEAKER NOTES:**

"Quick recap of your power tools from Week 2.

Role prompting - activate specific expertise. Few-shot learning - teach through examples. Platform optimization - get the most from each tool.

These are great techniques. But here's the question:

[Point to question]

How do we maintain consistency across ALL our prompts? If you have 10 different templates, how do you ensure they all sound like you?

That's what we're solving this week."

[Transition: Click to Segment 1]

---

## SEGMENT 1: WHY JSON?
### Duration: 8 minutes | Slides 4-5

---

### SLIDE 4: THE CONSISTENCY PROBLEM

**Title:** The Problem: Variable Outputs

**Content:**

**Even with good prompts:**
- Same prompt, different runs, different tone
- "Professional" means different things each time
- Preferences forgotten or inconsistently applied
- No single source of truth for your style

**What We Need:**
- Store preferences once
- Reference them every time
- Consistent voice across all outputs
- Easy to update as preferences evolve

**Graphic:** Multiple outputs with inconsistent styles vs. unified style

**GRAPHICS:**

**Graphic 1: Variable Outputs Problem**
- Purpose: Show frustration of inconsistent AI outputs despite good prompts
- Type: Problem visualization with variation emphasis
- Elements: Single "good prompt" box at center, multiple output samples around it showing different tones/styles (formal, casual, technical, etc.), visual indicators of variation (different fonts, colors, styles), confused user icon
- Labels: "Same prompt, different times", output samples labeled "Formal", "Casual", "Too technical", etc., "No consistent voice" problem statement
- Relationships: One prompt producing scattered inconsistent outputs, visual chaos emphasizing the problem

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Here's a problem you've probably noticed: even with good prompts, outputs vary.

You say 'professional tone' and sometimes you get formal, sometimes conversational. You remember to say 'avoid jargon' in one prompt but forget in the next.

Your preferences are scattered across individual prompts. There's no single source of truth for your style.

What we need is a way to store preferences once and reference them every time."

[Transition]

---

### SLIDE 5: THE SOLUTION - CONFIGURATION FILES

**Title:** The Solution: Configuration Files

**Content:**

**The Concept:**
Store your preferences in a file. Reference that file in every prompt.

**`style.json` Preview:**
```json
{
  "voice": {
    "tone": "professional but approachable",
    "formality": "business casual"
  },
  "preferences": {
    "use": ["active voice", "concrete examples"],
    "avoid": ["jargon", "passive voice"]
  }
}
```

**Why JSON Specifically:**
- Human-readable (you can understand it)
- Machine-readable (AI can parse it)
- Industry standard (used everywhere)
- Easy to version control

**Graphic:** Configuration file connecting to multiple prompts

**GRAPHICS:**

**Graphic 1: Configuration File Solution**
- Purpose: Show how single config file ensures consistency across all prompts
- Type: Hub-and-spoke diagram showing centralized configuration
- Elements: Central `style.json` file icon, multiple prompt templates radiating outward like spokes, consistency indicators showing uniform output, "reference" arrows from prompts to config file
- Labels: "style.json" (center, highlighted), "Email Template", "Report Template", "Analysis Template" (spokes), "Consistent Voice Every Time" outcome banner
- Relationships: Single source (config file) influencing multiple destinations (prompts), unity and consistency theme

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"The solution is a configuration file. Store your preferences once, reference them everywhere.

[Point to JSON example]

This is what it looks like. Your voice settings. Your preferences. Things to use. Things to avoid. All in one structured file.

Why JSON specifically?

It's human-readable - you can understand what it says. It's machine-readable - AI can parse the structure. It's the industry standard - used in every programming language, every platform.

Now let's learn the syntax so you can write your own."

[Transition: Click to Segment 2]

**BACKGROUND:**

**Rationale:**
- Positions configuration files as infrastructure, not just convenience—this mental shift is critical for adoption
- The preview JSON example makes the abstract concept concrete immediately
- By showing the problem (scattered preferences) and solution (centralized config) together, creates clear value proposition
- The "single source of truth" pattern is familiar from data engineering, making it accessible

**Key Research & Citations:**
- **Configuration Management Patterns (Twelve-Factor App Methodology)**: Industry standard for application development recommends storing configuration separate from code. The same principle applies to AI prompting—preferences should be configuration, not hardcoded in each prompt.
- **Don't Repeat Yourself (DRY) Principle (Hunt & Thomas, The Pragmatic Programmer)**: When the same preference appears in multiple prompts, changing it requires updating all instances. Configuration files provide single-source-of-truth that eliminates repetition.
- **JSON as Universal Data Format**: JSON is the most widely supported data format across programming languages and platforms. Learning JSON for AI prompting provides transferable knowledge applicable to APIs, configuration files, and data processing.

**Q&A Preparation:**
- *"Can't I just copy-paste my preferences into each prompt?"*: You can, but that becomes unmaintainable at scale. When you refine your tone preference, you'd need to update 50+ prompts individually. Configuration files update all prompts at once.
- *"Why JSON instead of plain text?"*: Plain text lacks structure. JSON's key-value pairs enable selective referencing—you can use just the tone settings in one prompt, both tone and formatting in another. Structure enables flexibility.
- *"What if I have different styles for different contexts?"*: Create multiple configuration files: `style-formal.json`, `style-casual.json`. Reference the appropriate one for each use case.

---

## SEGMENT 2: JSON SYNTAX ESSENTIALS
### Duration: 15 minutes | Slides 6-10

---

### SLIDE 6: JSON BASIC STRUCTURE

**Title:** JSON Basics: Keys and Values

**Content:**

**The Fundamental Pattern:**
```json
{
  "key": "value"
}
```

**Rules:**
- Everything wrapped in curly braces `{ }`
- Keys are always in **double quotes**
- Colon separates key from value
- Comma separates items (except the last one!)

**Multiple Items:**
```json
{
  "name": "Alice",
  "role": "Consultant",
  "years": 5
}
```

**Graphic:** Diagram showing key → value relationship

**GRAPHICS:**

**Graphic 1: JSON Key-Value Basics**
- Purpose: Explain fundamental JSON structure pattern
- Type: Annotated syntax diagram
- Elements: Large clear code example showing JSON syntax, labeled arrows pointing to key structural elements (curly braces, double quotes, colon, comma), color coding for different parts (keys in one color, values in another)
- Labels: "Curly braces wrap everything", "Keys in double quotes", "Colon separates", "Comma between items (not after last!)", example showing multiple items
- Relationships: Visual breakdown of syntax structure, annotations explaining each component's role

**SPEAKER NOTES:**

"Let's start simple.

JSON is just key-value pairs. The key is a name - like 'name' or 'role'. The value is the data.

[Point to rules]

Everything goes in curly braces. Keys are always in double quotes. Colon separates key from value. Comma separates items.

[Point to multiple items]

Here's a JSON object with three items. Notice the last item - 'years' - has no comma after it. That's important. Trailing commas break JSON.

Let's look at what types of values you can use."

[Transition]

---

### SLIDE 7: JSON DATA TYPES

**Title:** JSON Data Types

**Content:**

```json
{
  "string": "text in double quotes",
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

**Type Reference:**

| Type | Syntax | Example |
|------|--------|---------|
| String | Double quotes | `"hello"` |
| Number | No quotes | `42`, `3.14` |
| Boolean | `true` / `false` | `true` |
| Null | `null` | `null` |
| Array | Square brackets | `["a", "b"]` |
| Object | Curly braces | `{"key": "value"}` |

**Graphic:** Type icons with visual examples

**GRAPHICS:**

**Graphic 1: JSON Data Types Visual Reference**
- Purpose: Provide clear visual guide to all JSON data types
- Type: Icon grid with type examples
- Elements: Six rows, each showing type icon, name, syntax example, and visual representation (string with quotes, number without quotes, boolean as switch, null as empty, array as list, object as nested structure)
- Labels: Type names, syntax examples clearly formatted, usage notes for each type, quick reference table
- Relationships: Organized by type, visual hierarchy showing most common types (string, number, array, object) prominently

**SPEAKER NOTES:**

"JSON supports several data types.

[Walk through example]

Strings - text in double quotes. Numbers - no quotes needed. Booleans - true or false, no quotes. Null - represents empty or unknown.

Arrays - lists of items in square brackets. Objects - nested groups in curly braces.

For `style.json`, you'll mostly use strings, arrays, and nested objects.

[Point to table]

Here's your quick reference. Strings always have quotes. Numbers and booleans don't."

[Transition]

---

### SLIDE 8: COMMON JSON ERRORS

**Title:** Common Errors (And How to Fix Them)

**Content:**

**Error 1: Trailing Comma**
```json
{
  "name": "Alice",
  "role": "Consultant",  ← WRONG: comma here
}
```

**Error 2: Single Quotes**
```json
{
  'name': 'Alice'  ← WRONG: must use double quotes
}
```

**Error 3: Unquoted Keys**
```json
{
  name: "Alice"  ← WRONG: key needs quotes
}
```

**The Fix:**
Always validate with [JSONLint.com](https://jsonlint.com/) before using.

**Graphic:** Red X marks on errors, green checkmark on JSONLint

**GRAPHICS:**

**Graphic 1: Common JSON Errors**
- Purpose: Highlight the three most common JSON mistakes
- Type: Error comparison with solution
- Elements: Three error example boxes each showing wrong code with red X, annotations pointing to specific errors, fourth box showing correct version with green checkmark, JSONLint logo as solution
- Labels: "Error 1: Trailing Comma", "Error 2: Single Quotes", "Error 3: Unquoted Keys", "Correct Version", "Always Validate with JSONLint.com"
- Relationships: Wrong examples leading to correct example, validation as mandatory step

**SPEAKER NOTES:**

"These three errors cause 90% of JSON problems.

[Point to Error 1]

Trailing comma - the most common error. The last item in an object or array should NOT have a comma after it.

[Point to Error 2]

Single quotes - JSON requires double quotes. Not single. Always double.

[Point to Error 3]

Unquoted keys - unlike some programming languages, JSON needs quotes around keys.

[Point to fix]

The fix: always validate. JSONLint.com will tell you exactly where the error is. I validate every JSON file I write. No exceptions."

[Transition]

**BACKGROUND:**

**Rationale:**
- Prevents the #1 frustration source for JSON beginners—syntax errors that break the entire file
- By showing the three most common errors upfront, saves participants hours of debugging
- Establishes validation as mandatory workflow step, not optional nice-to-have
- The "90% of errors" statistic gives participants confidence that mastering these three prevents most problems

**Key Research & Citations:**
- **JSON Syntax Error Research (Stack Overflow Data)**: Analysis of JSON-related questions shows trailing commas account for 40%+ of beginner errors, quote issues for 30%, and unquoted keys for 15%. These three categories represent 85% of all syntax errors.
- **JSON Specification (ECMA-404)**: JSON is intentionally strict compared to JavaScript object notation. Trailing commas are explicitly forbidden, only double quotes are valid, and all keys must be quoted. This strictness enables reliable parsing across all platforms.
- **Developer Tool Studies**: Validation tools catch 100% of syntax errors before runtime, versus 60-70% error detection rate for manual review. Mandatory validation workflows reduce debugging time by 80%.

**Q&A Preparation:**
- *"Why is JSON so strict about syntax?"*: Strictness enables universal compatibility. Because JSON has one unambiguous syntax, parsers in every programming language interpret it identically. JavaScript Object Notation is more lenient but not universal.
- *"Can I use a code editor that validates automatically?"*: Yes! VS Code, Sublime Text, and most modern editors have JSON validation built-in. But learning JSONLint.com as the validation workflow ensures you can validate anywhere, even in browser.
- *"What if JSONLint says my JSON is valid but it still doesn't work?"*: Valid syntax doesn't guarantee correct logic. Your JSON might be syntactically correct but semantically wrong (wrong values, wrong structure for your use case). Validation catches syntax only.

---

### SLIDE 9: LIVE DEMO - BUILDING JSON

**Title:** Live Demo: Building JSON Step by Step

**Content:**

**We'll Build:**
A simple style configuration from scratch

**Watch For:**
1. Starting with empty braces `{}`
2. Adding key-value pairs
3. Creating nested objects
4. Intentional error → validation → fix

**Graphic:** Demo placeholder

**GRAPHICS:**

**Graphic 1: JSON Building Demo Sequence**
- Purpose: Show progressive construction of JSON from scratch
- Type: Step-by-step sequence visualization
- Elements: Four panels showing progressive building (1: empty braces, 2: first key-value pair, 3: additional pairs, 4: nested object), arrows between steps, editor window mockup
- Labels: Step numbers, "Start here", "Add key-value", "Add more", "Create nested structure", intentional error example with validation failure
- Relationships: Linear progression showing JSON construction, validation checkpoint emphasized

**SPEAKER NOTES:**

"[DEMO - Show, don't tell]"

"Let me show you how to build JSON step by step.

[Open text editor]

Start with empty braces.

[Type { }]

Now I'll add a key-value pair. 'tone' - my preferred tone.

[Type 'tone': 'professional']

Let me add another - my formality preference.

[Continue building]

Now I want to group these under 'voice'. I'll create a nested object.

[Create nested structure]

Let me validate this in JSONLint...

[Paste into JSONLint - should pass]

Now watch what happens if I add a trailing comma...

[Add comma after last item]

Error! See how JSONLint shows exactly where the problem is.

[Fix and validate]

Clean again. Always validate."

[Transition]

---

### SLIDE 10: JSON VALIDATION WORKFLOW

**Title:** The Validation Workflow

**Content:**

**Every Time You Write JSON:**

```
1. Write or edit JSON
       ↓
2. Paste into JSONLint.com
       ↓
3. Click "Validate JSON"
       ↓
   If error → Read error message → Fix → Return to step 2
       ↓
   If valid → Use in your work
```

**Common Error Messages:**
- "Expecting 'STRING'" → Missing double quotes
- "Unexpected token" → Trailing comma or missing comma
- "Expected ',' or '}'" → Missing comma between items

**Graphic:** Flowchart of validation process

**GRAPHICS:**

**Graphic 1: JSON Validation Workflow**
- Purpose: Establish mandatory validation habit
- Type: Process flowchart with decision points
- Elements: Flowchart boxes showing steps (Write/Edit → Paste into JSONLint → Validate → Decision diamond "Valid?"), error path looping back to fix, success path leading to use, common error messages in sidebar
- Labels: Process steps clearly labeled, "Yes/No" at decision point, "Fix error" in loop, "Use in work" at end, error messages reference box
- Relationships: Cyclical flow for errors (iterate until valid), linear flow for success, validation as gate before use

**SPEAKER NOTES:**

"Here's the workflow you should follow every time.

Write JSON. Paste into JSONLint. Validate. If there's an error, read the message, fix it, validate again. Only use JSON that validates clean.

[Point to error messages]

These are the messages you'll see most often. 'Expecting STRING' usually means missing quotes. 'Unexpected token' usually means comma issues.

JSONLint highlights the line with the problem. Look there first.

Now let's apply this to something practical - your `style.json`."

[Transition: Click to Segment 3]

---

## SEGMENT 3: CREATING STYLE.JSON
### Duration: 10 minutes | Slides 11-13

---

### SLIDE 11: WHAT GOES IN STYLE.JSON

**Title:** Your `style.json`: Personal Voice Configuration

**Content:**

**What to Include:**

| Section | Purpose | Examples |
|---------|---------|----------|
| `voice` | How you want to sound | tone, formality, personality |
| `writing` | Structure preferences | sentence length, paragraph length |
| `preferences` | What to do/avoid | use: [...], avoid: [...] |
| `formatting` | Visual style | headers, lists, emphasis |

**Key Insight:**
This isn't abstract - it's YOUR actual preferences. What do YOU want your writing to sound like?

**Graphic:** `style.json` sections mapped to output characteristics

**GRAPHICS:**

**Graphic 1: Style.json Sections Mapped to Output**
- Purpose: Connect configuration sections to their effects on output
- Type: Mapping diagram showing input-output relationships
- Elements: Four boxes showing style.json sections (voice, writing, preferences, formatting), arrows pointing to sample output text showing each section's effect
- Labels: Section names with examples, output samples with annotations ("sounds professional", "medium sentences", "no jargon", "clear headers"), "Your Preferences → Your Voice" theme
- Relationships: Configuration choices directly influencing output characteristics, personal customization emphasis

**SPEAKER NOTES:**

"Your `style.json` captures your personal voice.

[Walk through sections]

Voice - how do you want to sound? Tone, formality, personality.

Writing - structure preferences. Do you like short sentences or longer ones? How many sentences per paragraph?

Preferences - explicit lists of what to use and what to avoid. This is powerful.

Formatting - visual style. How do you use headers? Lists? Emphasis?

[Point to key insight]

This isn't abstract. Think about your actual preferences. How do YOU want to write? What makes your best work yours?"

[Transition]

---

### SLIDE 12: STYLE.JSON TEMPLATE

**Title:** `style.json` Template

**Content:**

```json
{
  "voice": {
    "tone": "professional but approachable",
    "formality": "business casual",
    "personality": "helpful, direct, thoughtful"
  },
  "writing": {
    "sentence_length": "medium (15-25 words)",
    "paragraph_length": "3-5 sentences"
  },
  "preferences": {
    "use": [
      "active voice",
      "concrete examples",
      "clear transitions"
    ],
    "avoid": [
      "jargon without explanation",
      "passive voice",
      "hedge words (might, perhaps)"
    ]
  }
}
```

**Graphic:** Template with "customize these" callouts

**GRAPHICS:**

**Graphic 1: Style.json Template with Customization Callouts**
- Purpose: Guide participants to personalize the template
- Type: Annotated code template
- Elements: Complete style.json template in code format, callout boxes pointing to customizable values with prompting questions ("What's YOUR tone?", "YOUR sentence preference?", "What do YOU avoid?")
- Labels: Section names, example values, customization prompts, "Start here, make it yours" instruction
- Relationships: Template as starting point, emphasis on personal customization rather than copying

**SPEAKER NOTES:**

"Here's a template to start from.

[Walk through sections]

Voice section - I've put 'professional but approachable' as the tone. Business casual formality. Helpful, direct, thoughtful personality.

Writing section - medium sentence length with a word count range. 3-5 sentences per paragraph.

Preferences - arrays of things to use and avoid. Active voice, concrete examples, clear transitions. Avoid jargon, passive voice, hedge words.

This is MY style. Yours will be different.

In Exercise 3.2, you'll customize every value to match YOUR preferences."

[Transition]

---

### SLIDE 13: USING STYLE.JSON IN PROMPTS

**Title:** Using `style.json` in Prompts

**Content:**

**The Pattern:**
```markdown
Follow this style guide for all writing:

<style>
{
  "tone": "professional but approachable",
  "preferences": {
    "use": ["active voice", "examples"],
    "avoid": ["jargon", "passive voice"]
  }
}
</style>

Now write: [Your request here]
```

**Benefits:**
- Same voice every time
- Easy to update (change file, all prompts updated)
- Shareable (team can use same style)
- Evolves with you (refine as you learn)

**Graphic:** `style.json` connecting to multiple prompts with consistent output

**GRAPHICS:**

**Graphic 1: Style.json Integration Pattern**
- Purpose: Show how to reference config file in actual prompts
- Type: Usage pattern diagram with benefits callout
- Elements: Prompt template showing style.json integration (follow style guide → paste JSON → actual request), multiple prompt examples all referencing same config, consistent output samples, benefits list with icons
- Labels: "The Pattern" with template code, prompt examples, benefits (same voice, easy updates, shareable, evolves), consistency indicator
- Relationships: One config file referenced by many prompts, consistency multiplier effect, benefits radiating from central config

**SPEAKER NOTES:**

"Here's how you use it in prompts.

[Walk through pattern]

'Follow this style guide' - tells the AI to apply these preferences. Then paste your JSON in style tags or code blocks. Then your actual request.

[Point to benefits]

Same voice every time - no more inconsistent outputs.

Easy to update - change the file once, every prompt that references it benefits.

Shareable - your team can use the same style for brand consistency.

Evolves - as you learn what works, refine the file. Your prompts automatically improve.

Now let's talk about version control - how we track these changes over time."

[Transition: Click to Segment 4]

**BACKGROUND:**

**Rationale:**
- Demonstrates the practical application pattern participants will use immediately
- The benefits list converts abstract configuration concept into concrete value propositions
- By showing style.json integration in actual prompt structure, removes ambiguity about usage
- The "one change, all prompts updated" benefit is the key scalability insight

**Key Research & Citations:**
- **Separation of Concerns (Software Design Principle)**: Separating configuration (style.json) from logic (prompt templates) enables independent modification. You can refine your writing style without touching template logic, or vice versa.
- **Template Pattern (Design Patterns, Gang of Four)**: The style.json integration follows the template method pattern—prompts define structure, configuration provides variable content. This enables reusable prompt templates with customizable behavior.
- **Version Control Benefits for Configuration**: When style.json is version-controlled, every change is traceable. You can experiment with style changes, then revert if they don't improve outputs. Without version control, experiments are risky.

**Q&A Preparation:**
- *"Do I paste the entire JSON every time?"*: For manual prompting, yes—paste the relevant sections. In Block 2 workflows, you'll reference the file programmatically without manual pasting. Learn the manual pattern first.
- *"Can I override style.json settings in individual prompts?"*: Yes. Add prompt-specific constraints after the style.json inclusion. AI applies both, with prompt-specific constraints taking precedence. This gives flexibility when needed.
- *"What if my style.json becomes huge?"*: Split into multiple files: `voice.json`, `formatting.json`, `domain-specific.json`. Include only relevant files for each prompt type.

---

## SEGMENT 4: GITHUB BASICS
### Duration: 7 minutes | Slides 14-17

---

### SLIDE 14: WHY VERSION CONTROL

**Title:** Why Version Control Matters

**Content:**

**Without Version Control:**
- Multiple files: "style_v2_final_REAL.json"
- No history of what changed when
- Can't undo mistakes
- Collaboration is chaos

**With Version Control:**
- One file that evolves
- Complete history of all changes
- Roll back to any previous version
- Safe collaboration

**Analogy:**
Version control is like "track changes" for your entire project.

**Graphic:** Messy file versions vs. clean version history

**GRAPHICS:**

**Graphic 1: Version Control Before/After**
- Purpose: Contrast chaos of manual versioning with clean version control
- Type: Side-by-side comparison showing disorder vs. order
- Elements: Left side shows cluttered folder with multiple file versions (style_v2_final_REAL.json, etc.), confusion indicators; right side shows single file with clean version history timeline, organized commits
- Labels: "Without Version Control" (chaos, confusion, can't undo), "With Version Control" (clean history, rollback capability, collaboration), "Track changes for your entire project" analogy
- Relationships: Chaotic multiple files vs. single file with history, visual relief on "after" side

**SPEAKER NOTES:**

"Let's talk about why version control matters.

[Point to 'without']

Without it, you end up with files like 'style_final_v2_REAL.json'. No history of what changed. Can't undo mistakes. Collaborating with others is a nightmare.

[Point to 'with']

With version control - one file that evolves. Complete history of every change. You can roll back to any previous version. Collaboration works.

[Point to analogy]

Think of it like track changes in Word, but for your entire project."

[Transition]

---

### SLIDE 15: KEY GITHUB CONCEPTS

**Title:** GitHub Vocabulary

**Content:**

| Term | What It Is | Analogy |
|------|------------|---------|
| **Repository** | Project folder | Filing cabinet |
| **Commit** | Saved snapshot | Video game save |
| **Push** | Upload to GitHub | Sync to cloud |
| **Pull** | Download changes | Get updates |
| **History** | Record of commits | Change log |

**You Already Have:**
A repository from Week 1!

**Today's Focus:**
Understanding commits and history.

**Graphic:** Icons for each concept

**GRAPHICS:**

**Graphic 1: GitHub Vocabulary with Analogies**
- Purpose: Make version control concepts accessible through analogies
- Type: Definition table with visual analogies
- Elements: Five rows showing term, definition, and analogy icon (filing cabinet for repository, save icon for commit, cloud upload for push, download for pull, timeline for history)
- Labels: Terms in bold, clear definitions, relatable analogies, "You already have a repository!" reminder
- Relationships: Technical terms made accessible through familiar concepts, building on Week 1 setup

**SPEAKER NOTES:**

"Let's get the vocabulary down.

[Walk through table]

Repository - your project folder on GitHub. You created this in Week 1.

Commit - a saved snapshot with a description. Like saving a video game - you can go back to any save point.

Push - uploading commits to GitHub. Syncing to the cloud.

Pull - downloading changes others made. Getting updates.

History - the record of all commits. Your change log.

Today we're focusing on commits and history. These are the core of version control."

[Transition]

---

### SLIDE 16: THE COMMIT WORKFLOW

**Title:** The Basic Workflow

**Content:**

**Step 1: Make Changes**
Edit files, add new files

**Step 2: Stage Changes**
Select what to include in this commit

**Step 3: Write Commit Message**
Describe what changed and why

**Step 4: Commit**
Save the snapshot

**Step 5: Push**
Upload to GitHub

**Commit Message Examples:**
```
Good: "Add style.json with voice and formatting preferences"
Good: "Fix typo in email template"
Bad:  "updates"
Bad:  "stuff"
```

**Graphic:** Flowchart showing the 5 steps

**GRAPHICS:**

**Graphic 1: Git Commit Workflow**
- Purpose: Teach the five-step commit process
- Type: Linear process flowchart
- Elements: Five sequential boxes with icons (1: edit icon, 2: selection icon, 3: message icon, 4: save icon, 5: upload icon), arrows connecting steps, good vs bad commit message examples in sidebar
- Labels: Step names and descriptions, "Make Changes → Stage → Write Message → Commit → Push", commit message quality examples with green/red indicators
- Relationships: Linear sequence of steps, emphasis on meaningful commit messages as critical step

**SPEAKER NOTES:**

"Here's the basic workflow.

Make changes to your files. Stage the changes - select what to include. Write a commit message describing what changed. Commit - save the snapshot. Push - upload to GitHub.

[Point to commit message examples]

Commit messages matter. They're notes to your future self.

'Add `style.json` with voice and formatting preferences' - tells you exactly what that commit contains.

'updates' - tells you nothing. Three months from now, you won't remember what you changed.

In Exercise 3.3, you'll practice making meaningful commits."

[Transition]

---

### SLIDE 17: HOMEWORK & CLOSE

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 3.1: JSON Practice | 15 min | `json-practice.json` | All data types |
| Exercise 3.2: Create `style.json` | 25 min | `style.json` + test | Personal config |
| Exercise 3.3: GitHub Practice | 20 min | Commit history | Version control |
| **Total** | **60 min** | | |

**Key Reminders:**
- **Always validate JSON with JSONLint**
- Customize `style.json` to YOUR preferences
- Write meaningful commit messages

**Next Week:** Quality Rubrics + LLM-as-Judge

**Graphic:** Three exercise cards with icons

**GRAPHICS:**

**Graphic 1: Week 3 Exercise Cards**
- Purpose: Present homework as progressive skill building
- Type: Card-based layout consistent with previous weeks
- Elements: Three cards arranged horizontally, each with icon (JSON braces, style file icon, GitHub logo), time estimate, deliverable, skills practiced
- Labels: Exercise numbers and names, time allocations (15-25-20 min), deliverables (json-practice.json, style.json, commit history), key reminders ("validate", "customize", "meaningful messages")
- Relationships: Progressive flow from JSON basics to personal config to version control, building complete infrastructure

**SPEAKER NOTES:**

"Three exercises this week.

Exercise 3.1 is JSON practice - 15 minutes. Create a valid JSON file using all the data types we covered. Validate with JSONLint.

Exercise 3.2 is your `style.json` - 25 minutes. This is personal. Customize every value to YOUR preferences. Test it in a prompt.

Exercise 3.3 is GitHub practice - 20 minutes. Upload your files, make multiple commits, practice meaningful commit messages.

[Point to reminders]

Always validate JSON. Customize your `style.json` - don't just copy the template. Write commit messages that explain what you changed.

[Point to next week]

Next week we tackle quality - how to evaluate AI outputs systematically. You'll create quality rubrics and learn the LLM-as-judge pattern. Your `style.json` becomes part of how we evaluate outputs.

Questions before we wrap?

[Take questions]

Great session. You've got the infrastructure now - JSON for configuration, GitHub for version control. These compound over time.

See you next week!"

---

## APPENDICES

### APPENDIX A: Slide Type Definitions

(See Week 1 presentation for complete slide type reference - consistent across all weeks)

Key slide types used in Week 3:
- **PROBLEM STATEMENT**: Creates tension around inconsistent AI outputs (Slide 4)
- **INSIGHT / REVELATION**: Introduces configuration files as solution (Slide 5)
- **SYNTAX / TECHNICAL**: Teaches JSON structure and data types (Slides 6-8)
- **LIVE DEMO**: Demonstrates JSON building and validation (Slide 9)
- **APPLICATION**: Shows style.json in actual prompts (Slide 13)

---

### APPENDIX B: Content Element Formats

(Standard formatting conventions apply - see Week 1 for complete reference)

---

### APPENDIX C: Speaker Notes Conventions

(Standard stage directions and transitions - see Week 1 for complete reference)

---

### APPENDIX D: Background Section Guidelines

**Rationale (3-5 bullets)**
- Explain the slide's purpose in the narrative arc
- Describe the mental shift it creates
- Note connections to adjacent slides
- Justify the chosen framing or approach

**Key Research & Citations (3-5 entries)**
Format: **[Source Name (Year)]**: [Detailed explanation]
- Include methodology when relevant
- Cite specific statistics or findings
- Explain how the research supports the slide's claims
- Note any caveats or limitations

**Q&A Preparation (3-5 questions)**
Format: *"[Question]"*: [Response]
- Anticipate skeptical questions
- Prepare for "what about..." objections
- Have specific examples ready
- Include graceful redirects for off-topic questions

---

### APPENDIX E: Visual Design Guidelines

**Block 1 Color Coding**
- **Primary color**: Blue (represents foundational skills, structure, clarity)
- **Accent color**: Lighter blue for highlights and callouts
- **Success indicators**: Green checkmarks for correct examples
- **Warning indicators**: Red X marks for incorrect examples
- **Neutral**: Gray for supporting/background elements

(See Week 1 for complete visual design guidelines)

---

### APPENDIX F: Quality Checklist

**Content Quality**
- [ ] Slide type clearly identified
- [ ] Key Thesis established in metadata
- [ ] Learning objectives are action-oriented
- [ ] Content supports thesis and objectives
- [ ] Examples are specific and relevant
- [ ] Technical accuracy verified

**Documentation Quality**
- [ ] All slides have complete GRAPHICS descriptions
- [ ] Speaker notes provide full script
- [ ] BACKGROUND sections on key slides (3 in Week 3)
- [ ] JSON syntax examples validated
- [ ] JSONLint workflow emphasized

**Week 3 Specific**
- [ ] JSON examples are syntactically valid
- [ ] style.json template is complete and functional
- [ ] GitHub workflow steps are sequential and clear
- [ ] Validation emphasis repeated throughout
- [ ] Configuration vs. logic separation explained

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 2.0 | 2026-01-03 | Enhanced with BACKGROUND sections, Key Thesis, and expanded appendices | Claude |
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
