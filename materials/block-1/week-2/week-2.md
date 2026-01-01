# Week 2: Advanced Prompting + Platform Optimization

**Block:** 1 - AI Prompting Mastery
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Week 1 exercises completed
- [ ] GitHub repository created with initial structure
- [ ] Markdown basics understood
- [ ] First structured prompt tested

## Exit Criteria

- [ ] Understands role prompting and few-shot learning
- [ ] Can optimize prompts for specific AI platforms
- [ ] Has tested prompts on multiple platforms
- [ ] Platform comparison document created

---

## Workshop Content (45 minutes)

### Segment 1: Recap & Common Issues (5 min)

- Quick review of Week 1 concepts
- Address common Markdown mistakes
- Answer questions from exercises

### Segment 2: Role Prompting (12 min)

**What is role prompting?**
- Telling AI to adopt a specific persona or expertise
- Activates relevant "knowledge patterns" in the model

**The pattern:**
```markdown
You are a [ROLE] with expertise in [DOMAIN].
Your communication style is [STYLE].
```

**Examples:**
```markdown
You are a senior software engineer who specializes in Python.
Review this code for bugs, security issues, and best practices.
```

```markdown
You are a business analyst with 15 years of consulting experience.
Analyze this market data and provide strategic recommendations.
```

**When to use roles:**
- Technical tasks → Technical expert roles
- Creative tasks → Creative professional roles
- Communication → Role matching the audience
- Analysis → Domain expert roles

**Caution:**
- Don't over-specify (too many constraints confuse the model)
- Match role to task complexity
- Test different roles to find what works

### Segment 3: Few-Shot Learning (12 min)

**What is few-shot learning?**
- Providing examples of desired input→output pairs
- "Teaching" the AI through demonstration

**The pattern:**
```markdown
# Task
[Describe what you want]

# Examples

## Example 1
Input: [sample input]
Output: [desired output]

## Example 2
Input: [sample input]
Output: [desired output]

# Your Turn
Input: [actual input]
Output:
```

**Why it works:**
- Shows exact format expectations
- Demonstrates edge cases
- Reduces ambiguity dramatically

**Best practices:**
- Use 2-3 examples (more isn't always better)
- Examples should cover different scenarios
- Keep examples realistic and relevant
- Order matters: put most relevant example last

**Live demo:** Creating a few-shot prompt for data extraction

### Segment 4: Platform-Specific Optimization (12 min)

**Key platform differences:**

| Feature | Claude | ChatGPT | Gemini |
|---------|--------|---------|--------|
| Context window | 200K tokens | 128K (GPT-4) | 1M tokens |
| Best for | Analysis, writing, code | General, creative, plugins | Long documents, research |
| Formatting | Excellent Markdown | Good Markdown | Good Markdown |
| System prompts | Yes (in API) | Yes | Limited |

**Claude-specific tips:**
- Excels at following complex instructions
- Use clear section headers
- Provide XML-style tags for structured output:
  ```markdown
  <context>
  [Background information]
  </context>

  <task>
  [What to do]
  </task>
  ```
- Works well with thinking/reasoning requests

**ChatGPT-specific tips:**
- Good at conversational refinement
- Can use Custom Instructions for persistent context
- Works well with iterative prompting
- Strong at code generation and explanation

**General optimization:**
- Start with clear, direct instructions
- Break complex tasks into steps
- Use formatting to organize long prompts
- Test same prompt on multiple platforms

### Segment 5: Thinking/Reasoning Prompts (4 min)

**When to ask AI to "think":**
```markdown
Think through this step-by-step before providing your answer.
```

```markdown
Before writing, outline your approach.
```

**Benefits:**
- Improves accuracy on complex tasks
- Makes reasoning visible and debuggable
- Reduces errors in multi-step problems

---

## Self-Paced Exercises (60 minutes total)

### Exercise 2.1: Role Prompting Experiments (20 minutes)

*Test how roles change AI output*

1. Choose a task (writing, analysis, or technical)
2. Create 3 versions with different roles:

```markdown
# Version 1: No role
[Just the task]

# Version 2: Basic role
You are a [professional]. [Task]

# Version 3: Detailed role
You are a [professional] with [specific experience] who [communication style]. [Task]
```

3. Run all three versions
4. Document the differences

**Deliverable:** `role-prompting-experiments.md` containing:
- Your task
- All 3 prompts
- All 3 responses (or summaries)
- Analysis: How did the role affect output?

---

### Exercise 2.2: Few-Shot Prompt Creation (25 minutes)

*Build a reusable few-shot prompt*

1. Choose a repeatable task you do often:
   - Email responses
   - Data formatting
   - Content summarization
   - Code documentation

2. Create a few-shot prompt:

```markdown
# Task
[Clear description of what you need]

# Format
[Describe the exact output format]

# Examples

## Example 1
**Input:**
[Sample input]

**Output:**
[Ideal output - write this yourself!]

## Example 2
**Input:**
[Different sample input]

**Output:**
[Ideal output]

# Now process this:
**Input:**
[Your actual input]

**Output:**
```

3. Test with 3 different inputs
4. Refine based on results

**Deliverable:** `few-shot-template.md` with:
- Your template
- 3 test results
- Notes on what worked/didn't

---

### Exercise 2.3: Platform Comparison (15 minutes)

*Understand platform strengths*

1. Take your best prompt from this week
2. Test it on at least 2 platforms:
   - Claude (claude.ai)
   - ChatGPT (chat.openai.com)
   - Gemini (gemini.google.com)
   - Or others you have access to

3. Compare results:

```markdown
# Platform Comparison

## Prompt Used
[Your prompt]

## Results

### [Platform 1]
- Quality: [1-5]
- Speed: [Fast/Medium/Slow]
- Following instructions: [1-5]
- Notes: [Observations]

### [Platform 2]
- Quality: [1-5]
- Speed: [Fast/Medium/Slow]
- Following instructions: [1-5]
- Notes: [Observations]

## Conclusions
- Best for this task: [Platform]
- Key differences noticed: [List]
```

**Deliverable:** `platform-comparison.md`

---

## Key Takeaways

1. **Role prompting** activates domain-specific patterns in AI models
2. **Few-shot learning** is the most powerful technique for consistent outputs
3. **Different platforms have different strengths** - match platform to task
4. **Thinking prompts** improve accuracy on complex, multi-step tasks
5. **Testing and iteration** are essential - no prompt is perfect on first try

---

## Preparation for Week 3

- Complete all Week 2 exercises
- Identify 2-3 tasks you'd like to create templates for
- Think about: What AI outputs do you need to be consistent every time?
- We'll introduce JSON and GitHub collaboration next week

---

## Resources

- [Anthropic Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
- [Google AI Prompting Guide](https://ai.google.dev/docs/prompt_best_practices)
- [Prompt Engineering Guide (Community)](https://www.promptingguide.ai/)
