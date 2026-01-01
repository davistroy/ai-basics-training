# **BLOCK 1 WEEK 2: Advanced Prompting + Platform Optimization**

**Block:** 1: AI Prompting Mastery
**Week:** 2 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** [← Previous Week](../week-1/participant-guide.md) | **Week 2** | [Next Week →](../week-3/participant-guide.md)

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
| 1 | Use role prompting to activate domain-specific expertise in AI responses | Exercise 2.1 |
| 2 | Create few-shot prompts that produce consistent, formatted outputs | Exercise 2.2 |
| 3 | Apply platform-specific optimization techniques for Claude and ChatGPT | Exercise 2.3 |
| 4 | Use thinking prompts to improve accuracy on complex tasks | Workshop + All Exercises |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Week 1 exercises (markdown-practice.md, first-structured-prompt.md)
- [ ] GitHub repository created with initial structure
- [ ] At least one structured prompt tested using ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework
- [ ] Familiar with basic Markdown syntax

**Not ready?** Complete the [Week 1 exercises](../week-1/participant-guide.md) first - they're the foundation for this week.

---

## Key Concepts

### Concept 1: Role Prompting

**Definition:**
Role prompting is telling the AI to adopt a specific persona or expertise before completing a task. This activates relevant knowledge patterns in the model.

**Why It Matters:**
Different roles bring different perspectives, vocabulary, and approaches. A "senior software engineer" reviews code differently than a "technical writer" would.

**Core Principle:**
> Role + Domain + Style = Effective Role Prompt

**Example:**
```markdown
You are a senior management consultant with 15 years of experience
in organizational transformation. Your communication style is direct
but diplomatic.

Analyze this org chart and identify potential bottlenecks...
```

**Common Mistake:**
Over-specifying the role with too many details. "You are a senior software engineer who graduated from MIT in 2005, worked at Google, then Amazon, and now specializes in distributed systems with a focus on microservices architecture..." - this is too much. Start simple, add detail only if needed.

---

### Concept 2: Few-Shot Learning

**Definition:**
Few-shot learning provides examples of desired input→output pairs to "teach" the AI through demonstration rather than description.

**Why It Matters:**
Showing examples is more precise than describing what you want. Examples eliminate ambiguity about format, style, and structure.

**The Pattern:**
```markdown
# Task
[Describe what you want]

# Format
[Describe the exact output format]

# Examples

## Example 1
**Input:**
[Sample input]

**Output:**
[Your ideal output - write this yourself!]

## Example 2
**Input:**
[Different sample input]

**Output:**
[Another ideal output]

# Now process this:
**Input:**
[Your actual input]

**Output:**
```

**When to Use:**
- Data extraction or formatting tasks
- Consistent email or message responses
- Any task where exact format matters
- When description alone isn't working

**When NOT to Use:**
- One-off creative tasks where variation is wanted
- Very simple requests that don't need format guidance
- When you don't have good examples to provide

---

### Concept 3: Platform-Specific Optimization

**Definition:**
Different AI platforms (Claude, ChatGPT, Gemini) have different strengths and respond better to certain formatting techniques.

**Key Components:**

| Platform | Strengths | Optimization Tips |
|----------|-----------|-------------------|
| **Claude** | Analysis, following complex instructions | Use XML tags, clear headers, reasoning requests |
| **ChatGPT** | Conversational refinement, code | Use system messages, iterative prompting, JSON mode |
| **Both** | Structure recognition | Code blocks, explicit constraints, examples |

**Visual Reference:**
```
    ┌─────────────────────────────┐
    │   Universal Techniques      │
    │  (Code blocks, headers,     │
    │   constraints, examples)    │
    └──────────────┬──────────────┘
                   │
        ┌──────────┴──────────┐
        ▼                     ▼
┌───────────────┐     ┌───────────────┐
│    Claude     │     │   ChatGPT     │
│  - XML tags   │     │ - Custom Inst │
│  - Reasoning  │     │ - JSON mode   │
│  - Long docs  │     │ - Iteration   │
└───────────────┘     └───────────────┘
```

---

### Concept 4: Thinking Prompts

**Definition:**
Asking AI to "think through" or "reason step-by-step" before providing an answer improves accuracy on complex tasks.

**Why It Matters:**
Forces the AI to show its work, making reasoning visible and errors easier to catch.

**The Pattern:**
```markdown
Before providing your answer, think through this step-by-step.
```

or

```markdown
Before writing your response, outline your approach.
```

**When to Use:**
- Complex multi-step problems
- Analysis tasks requiring accuracy
- Debugging or troubleshooting
- When you need to verify reasoning

---

### Quick Reference: Advanced Prompting Techniques

| Technique | Purpose | Key Format |
|-----------|---------|------------|
| Role Prompting | Activate specific expertise | "You are a [role] with [experience]..." |
| Few-Shot | Consistent formatted outputs | Examples with Input: / Output: pairs |
| Platform Optimization | Maximize effectiveness | Claude: XML tags; ChatGPT: Custom Instructions |
| Thinking Prompts | Improve accuracy | "Think through this step-by-step" |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Adding power tools to your prompting toolkit - role prompting, few-shot learning, and platform-specific optimizations.

**Key Points from Each Segment:**

**Segment 1: Role Prompting**
- Roles activate domain-specific knowledge patterns
- Pattern: Role + Domain + Style
- Start simple, add detail only if needed
- Key takeaway: Different roles produce genuinely different outputs

**Segment 2: Few-Shot Learning**
- Show examples instead of just describing what you want
- 2-3 examples is usually optimal
- Put your most relevant example last
- Key takeaway: Few-shot is the most powerful technique for consistent outputs

**Segment 3: Platform Optimization**
- Claude excels at following complex instructions, use XML tags
- ChatGPT excels at conversational refinement, use iteration
- Universal: code blocks, headers, explicit constraints
- Key takeaway: Match your technique to your platform

**Segment 4: Thinking Prompts**
- "Think step-by-step" improves accuracy on complex tasks
- Makes reasoning visible and debuggable
- Key takeaway: Use when accuracy matters more than speed

### Demo Recap

**What Was Demonstrated:**
Few-shot prompt creation for data extraction, showing how examples produce precise, consistent formatting.

**Key Steps:**
1. Defined the task and format
2. Provided 2-3 examples with input/output pairs
3. Added the actual input
4. Showed how output matched the example format

**Result:**
The AI followed the example format exactly, producing consistent, usable output.

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 2.1 | 20 min | `role-prompting-experiments.md` | Role prompting |
| 2.2 | 25 min | `few-shot-template.md` | Few-shot learning |
| 2.3 | 15 min | `platform-comparison.md` | Platform optimization |

---

### Exercise 2.1: Role Prompting Experiments

**Duration:** 20 minutes

**Purpose:**
Test how different role specifications change AI output, discovering the impact of expertise framing on response quality.

**You Will Create:**
A document comparing the same task with three different role specifications.

---

#### Instructions

**Step 1: Choose a task**
Select a task you actually do in your work:
- Reviewing a document or proposal
- Analyzing data or information
- Writing communication (email, report section)
- Providing recommendations

**Step 2: Create three role versions**

```markdown
# Version 1: No role (baseline)
[Just your task, no role specified]

# Version 2: Basic role
You are a [professional type].
[Your task]

# Version 3: Detailed role
You are a [professional type] with [X years] of experience in [domain].
Your communication style is [style descriptors].
[Your task]
```

**Step 3: Run all three versions**
Test each prompt in your AI platform (Claude or ChatGPT). Save the responses.

**Step 4: Analyze the differences**
Document how the role affected:
- Depth of response
- Terminology used
- Perspective taken
- Practical usefulness

**Step 5: Review Your Work**
Check that your deliverable includes:
- [ ] The task you chose
- [ ] All 3 prompt versions
- [ ] Responses (or summaries) from all 3
- [ ] Analysis of how role affected output

---

#### Deliverable Specification

**File Name:** `role-prompting-experiments.md`

**Location:** Upload to your GitHub repository

**Format Requirements:**
- Clear headers for each version
- Actual prompts shown (not just described)
- Specific observations about differences

**Quality Criteria:**
- [ ] Three distinct role variations
- [ ] Meaningful task (not trivial)
- [ ] Thoughtful analysis of differences

---

#### Example

**Scenario:** Analyzing a project delay

**Version 1 (No role):**
```markdown
Our project is 3 weeks behind schedule due to API integration issues.
What should we do?
```

**Version 2 (Basic role):**
```markdown
You are a project manager.

Our project is 3 weeks behind schedule due to API integration issues.
What should we do?
```

**Version 3 (Detailed role):**
```markdown
You are a senior project manager with 12 years of experience in software
development projects. You specialize in recovery planning and stakeholder
communication. Your style is direct and solution-focused.

Our project is 3 weeks behind schedule due to API integration issues.
What should we do?
```

**Analysis example:**
"The no-role version gave generic advice. The basic role added project management terminology. The detailed role provided specific recovery techniques and emphasized stakeholder communication - exactly what was mentioned in the role specification."

---

#### Tips & Troubleshooting

**Tips:**
- Choose a task where expertise actually matters
- Make the detailed role match the expertise you actually need
- Don't over-specify - if basic role works, you don't need more

**Common Issues:**

| Problem | Solution |
|---------|----------|
| All versions seem similar | Choose a more complex task where expertise matters |
| Detailed role makes response worse | You may have over-specified - simplify |
| Can't think of a role | Use roles from your industry: consultant, analyst, engineer, etc. |

---

### Exercise 2.2: Few-Shot Prompt Creation

**Duration:** 25 minutes

**Purpose:**
Build a reusable few-shot prompt for a task you do repeatedly, creating a template that produces consistent outputs.

**You Will Create:**
A few-shot template with 2-3 examples, tested with real inputs.

---

#### Instructions

**Step 1: Choose a repeatable task**
Pick something you do often:
- Email responses to common questions
- Data extraction from text
- Meeting notes summarization
- Content formatting
- Documentation updates

**Step 2: Create your few-shot prompt**

```markdown
# Task
[Clear description of what you need done]

# Format
[Describe the exact output format you want]

# Examples

## Example 1
**Input:**
[Sample input - use real or realistic data]

**Output:**
[Write your ideal output - this is the key step!]

## Example 2
**Input:**
[Different sample input - vary the scenario]

**Output:**
[Another ideal output]

## Example 3 (optional)
**Input:**
[Edge case or complex scenario]

**Output:**
[How you want the edge case handled]

# Now process this:
**Input:**
[Your actual input goes here]

**Output:**
```

**Step 3: Write your examples carefully**
- Create realistic inputs
- Write the outputs yourself (don't have AI generate them)
- Make examples different enough to show variation
- Put your most complex or representative example last

**Step 4: Test with 3 different inputs**
Run your template three times with different real inputs. Save the results.

**Step 5: Refine based on results**
If outputs aren't matching your examples:
- Add more detail to your examples
- Make format section more explicit
- Add a third example if using only two

---

#### Deliverable Specification

**File Name:** `few-shot-template.md`

**Location:** Upload to your GitHub repository

**Format Requirements:**
- Complete template with all sections
- At least 2 examples (3 is better)
- Test results included

**Quality Criteria:**
- [ ] Template is for a real, repeatable task
- [ ] Examples written by you (not AI-generated)
- [ ] Tested with 3 different inputs
- [ ] Notes on what worked and adjustments made

---

#### Example

**Scenario:** Extracting action items from meeting notes

**Template:**
```markdown
# Task
Extract action items from meeting notes. Create a formatted list of tasks
with owner and due date (if mentioned).

# Format
Return as a Markdown list with this structure:
- [ ] [Task description] - **Owner:** [Name] - **Due:** [Date or "Not specified"]

# Examples

## Example 1
**Input:**
Meeting notes: John said he would update the project plan by Friday.
Sarah will review the budget and get back to us next week.
We need to schedule the client call but no one was assigned.

**Output:**
- [ ] Update the project plan - **Owner:** John - **Due:** Friday
- [ ] Review the budget - **Owner:** Sarah - **Due:** Next week
- [ ] Schedule the client call - **Owner:** Not assigned - **Due:** Not specified

## Example 2
**Input:**
Team sync: Marketing team to deliver campaign assets by March 15.
Dev team working on API - Mike owns this, targeting end of sprint.
Open question: who's handling the user testing?

**Output:**
- [ ] Deliver campaign assets - **Owner:** Marketing team - **Due:** March 15
- [ ] Complete API work - **Owner:** Mike - **Due:** End of sprint
- [ ] Handle user testing - **Owner:** Not assigned - **Due:** Not specified

# Now process this:
**Input:**
[Paste actual meeting notes here]

**Output:**
```

---

### Exercise 2.3: Platform Comparison

**Duration:** 15 minutes

**Purpose:**
Understand platform strengths by testing the same prompt on different AI tools.

**You Will Create:**
A comparison document with observations about platform differences.

---

#### Instructions

**Step 1: Select your best prompt**
Choose your most refined prompt from this week or last week.

**Step 2: Test on two platforms**
Run the identical prompt on at least two platforms:
- [Claude](https://claude.ai)
- [ChatGPT](https://chat.openai.com)
- [Gemini](https://gemini.google.com) (optional third)

**Step 3: Compare results**
For each platform, evaluate:
- Quality of output (1-5 scale)
- Speed of response (Fast/Medium/Slow)
- How well it followed instructions (1-5 scale)
- Any notable differences

**Step 4: Document conclusions**
What did you learn about when to use each platform?

---

#### Deliverable Specification

**File Name:** `platform-comparison.md`

**Location:** Upload to your GitHub repository

**Format:**
```markdown
# Platform Comparison

## Prompt Used
```
[Your complete prompt]
```

## Results

### Claude
- **Quality:** [1-5]
- **Speed:** [Fast/Medium/Slow]
- **Instruction Following:** [1-5]
- **Response length:** [approximate]
- **Notes:** [Specific observations]

### ChatGPT
- **Quality:** [1-5]
- **Speed:** [Fast/Medium/Slow]
- **Instruction Following:** [1-5]
- **Response length:** [approximate]
- **Notes:** [Specific observations]

## Key Differences Observed
- [Difference 1]
- [Difference 2]
- [Difference 3]

## Conclusions
- Best platform for this type of task: [Choice and why]
- When I would use Claude: [Scenarios]
- When I would use ChatGPT: [Scenarios]
```

**Quality Criteria:**
- [ ] Same prompt tested on both platforms
- [ ] Specific observations (not just "they were similar")
- [ ] Thoughtful conclusions about when to use each

---

#### Tips & Troubleshooting

**Tips:**
- Use a prompt complex enough to show differences
- Test at similar times (AI load varies)
- Note if you're using free vs. paid tier

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Only have access to one platform | Use free tier of second platform, or document what you'd test |
| Outputs look identical | Try a more complex prompt or one with specific format requirements |
| Can't decide which is "better" | That's okay - document that they have different strengths |

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| Role Prompt Template | Structure role specifications | Below |
| Few-Shot Template | Create example-based prompts | Below |
| Platform Comparison Template | Document platform differences | Exercise 2.3 |

---

### Template 1: Role Prompt Template

```markdown
# Role Definition
You are a [role/title] with [X years] of experience in [domain/industry].

## Expertise
- [Key skill 1]
- [Key skill 2]
- [Key skill 3]

## Communication Style
[Describe how they communicate: direct, diplomatic, technical, accessible, etc.]

---

# Task
[Your request using the ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework]

## ASK
[What you want]

## CONTEXT
[Background]

## CONSTRAINTS
[Requirements]

## EXAMPLE
[Sample if helpful]
```

**Usage Instructions:**
1. Start with just the basic role (first line)
2. Add expertise section only if output needs more specificity
3. Communication style helps with tone matching
4. Combine with ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework for best results

---

### Template 2: Few-Shot Prompt Template

```markdown
# Task
[Clear description of what you want done]

# Format
[Explicit description of output format]
- Structure: [Describe structure]
- Length: [Expected length]
- Style: [Any style requirements]

# Examples

## Example 1: [Basic case]
**Input:**
[Sample input]

**Output:**
[Your ideal output]

## Example 2: [Different scenario]
**Input:**
[Different sample]

**Output:**
[Your ideal output]

## Example 3: [Edge case] (optional)
**Input:**
[Complex or unusual scenario]

**Output:**
[How to handle the edge case]

---

# Your Turn
**Input:**
[Actual input to process]

**Output:**
```

**Usage Instructions:**
1. Write examples yourself - don't have AI generate them
2. Use realistic inputs, not toy examples
3. Make examples different enough to show range
4. 2-3 examples is optimal; more isn't always better
5. Put most complex/representative example last

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Anthropic Prompt Engineering | Documentation | [docs.anthropic.com](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) | Claude optimization |
| OpenAI Prompt Engineering | Documentation | [platform.openai.com](https://platform.openai.com/docs/guides/prompt-engineering) | ChatGPT optimization |
| Prompting Guide | Community Resource | [promptingguide.ai](https://www.promptingguide.ai/) | General techniques |
| Google AI Prompting | Documentation | [ai.google.dev](https://ai.google.dev/docs/prompt_best_practices) | Gemini optimization |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Write effective role prompts | Exercise 2.1 shows meaningful differences across roles | ☐ |
| 2 | Create few-shot prompts | Exercise 2.2 template produces consistent outputs | ☐ |
| 3 | Identify platform strengths | Exercise 2.3 has specific observations | ☐ |
| 4 | Combine techniques appropriately | Exercises use role + ASK-CONTEXT-CONSTRAINTS-EXAMPLE or few-shot as appropriate | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 2.1 output | `role-prompting-experiments.md` | GitHub repo | ☐ |
| Exercise 2.2 output | `few-shot-template.md` | GitHub repo | ☐ |
| Exercise 2.3 output | `platform-comparison.md` | GitHub repo | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** Which technique - role prompting or few-shot - feels more immediately useful for your work?

2. **What's still fuzzy?** Are you unclear about when to use which technique?

3. **How will you apply this?** Identify one specific task you'll use few-shot prompting for this week.

4. **What surprised you?** Did the platform comparison reveal unexpected differences?

---

## Getting Help

### Quick Answers
- **Participant Resources:** Check the templates and resources above
- **Peer Discussion:** Connect with your cohort for quick tips

### Common Questions This Week

**Q: Should I always use role prompting?**
A: No - for simple tasks, roles add unnecessary complexity. Use roles when expertise or perspective genuinely matters for the output.

**Q: My few-shot examples aren't being followed exactly. Why?**
A: Make your examples more consistent with each other. If they have different formats, the AI may mix them. Also, make the "Format" section more explicit.

**Q: Which platform should I use for most tasks?**
A: Use what you have access to. For complex, structured tasks, Claude often excels. For conversational refinement and iteration, ChatGPT is strong. Test both for important tasks.

### When to Ask for Help

- **Before asking:** Check templates and resources sections
- **Good to ask:** "I tried [technique] but got [result]. Here's my prompt: [prompt]. What am I missing?"
- **Include:** Your actual prompt, what you expected, what you got

---

## Looking Ahead

### Next Week Preview: Week 3 - JSON Fundamentals + GitHub Basics

**Focus:**
Creating structured configuration files (`style.json`) and mastering GitHub version control.

**How It Builds on This Week:**
The prompting techniques you've learned will be captured in JSON configuration files for consistent application.

**To Prepare:**
- [ ] Complete all Week 2 exercises
- [ ] Think about your preferred writing style (tone, format, preferences)
- [ ] Review your GitHub repository - we'll be using it more extensively
- [ ] Consider: What makes your best outputs "yours"? What's your voice?

---

## Glossary

| Term | Definition |
|------|------------|
| **Role Prompting** | Telling AI to adopt a specific persona or expertise |
| **Few-Shot Learning** | Teaching AI through examples of desired input→output pairs |
| **Platform Optimization** | Adapting prompts for specific AI tools (Claude, ChatGPT) |
| **Thinking Prompts** | Asking AI to reason step-by-step before answering |
| **XML Tags** | Claude-specific formatting like `<instructions>` for structure |
| **Custom Instructions** | ChatGPT feature for persistent context across conversations |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [← Previous Week](../week-1/participant-guide.md) | **Week 2** | [Next Week →](../week-3/participant-guide.md)
