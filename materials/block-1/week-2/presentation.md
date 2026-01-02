# **POWERPOINT PRESENTATION: BLOCK 1 WEEK 2**
## **Advanced Prompting + Platform Optimization**

**Block:** 1: AI Prompting Mastery
**Week Number:** 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Participants who completed Week 1 Markdown and ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework training

**Week Learning Objectives:** By the end of this session, participants will:
1. Use role prompting to activate domain-specific expertise in AI responses
2. Create few-shot prompts that produce consistent, formatted outputs
3. Apply platform-specific optimization techniques for Claude and ChatGPT
4. Use thinking prompts to improve accuracy on complex tasks

**Entry Criteria:**
- [ ] Week 1 exercises completed
- [ ] GitHub repository created with initial structure
- [ ] Comfortable with ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework

**Exit Criteria:**
- [ ] Understands when to use role prompting vs. few-shot
- [ ] Can structure a few-shot prompt with examples
- [ ] Knows key differences between Claude and ChatGPT
- [ ] Has plan to complete Week 2 exercises

**Presentation Structure:**
1. Opening & Recap (5 min) - Slides 1-3
2. Segment 1: Role Prompting (12 min) - Slides 4-7
3. Segment 2: Few-Shot Learning (12 min) - Slides 8-11
4. Segment 3: Platform Optimization (12 min) - Slides 12-15
5. Thinking Prompts & Close (4 min) - Slides 16-19

**Total Slides:** 19

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Block 1 Week 2: Advanced Prompting + Platform Optimization

**Subtitle:** Power Tools for Your AI Toolkit

**Content:**
- AI Practitioner Training Program
- Block 1: AI Prompting Mastery
- Week 2 of 8

**Graphic:** Clean title slide with blue color scheme (Block 1 theme).

**GRAPHICS:**

**Graphic 1: Week 2 Title Slide**
- Purpose: Establish continuity with Week 1 while introducing advanced techniques
- Type: Title slide with progressive theme
- Elements: Blue gradient background (Block 1 consistent theme), "power tools" iconography suggesting enhanced capabilities, subtle progression indicator from Week 1
- Labels: "AI Practitioner Training Program" (top), "Block 1: AI Prompting Mastery" (center), "Week 2 of 8" (subtitle), "Advanced Prompting + Platform Optimization"
- Relationships: Visual connection to Week 1 style, progression markers showing advancement in curriculum

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome back to Week 2! Last week you built the foundation - Markdown structure and the ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework.

This week, we're adding power tools. By the end of today, you'll have three new techniques that dramatically improve your prompt effectiveness.

Quick check-in: Who used the ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework on a real task this week?

[Wait for 1-2 responses]

Great to hear. Today we're building on that foundation."

[Transition: Click to next slide]

---

### SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-5 min | Opening | Week 1 Recap |
| 5-17 min | Segment 1 | Role Prompting |
| 17-29 min | Segment 2 | Few-Shot Learning |
| 29-41 min | Segment 3 | Platform Optimization |
| 41-45 min | Close | Thinking Prompts & Homework |

**Graphic:** Timeline with three main technique icons

**GRAPHICS:**

**Graphic 1: Week 2 Session Timeline**
- Purpose: Show progression through three advanced techniques
- Type: Horizontal timeline with technique icons
- Elements: Five time segments, three central segments highlighted with icons (role mask/persona for role prompting, example cards for few-shot, platform logos for optimization), arrows connecting segments
- Labels: Time markers for each segment, technique names with brief descriptors, "Thinking Prompts" bonus callout
- Relationships: Left-to-right flow showing technique sequence, visual emphasis on three main techniques

**SPEAKER NOTES:**

"Here's our agenda:

Three main techniques today. First, role prompting - telling AI what expertise to bring. Second, few-shot learning - teaching through examples. Third, platform optimization - getting the most from Claude and ChatGPT.

We'll close with a quick look at thinking prompts and your homework.

Let's start with a quick recap of where we left off."

[Transition]

---

### SLIDE 3: WEEK 1 RECAP

**Title:** Quick Recap: Your Foundation

**Content:**

**What You Learned:**
- Markdown provides structure AI understands
- The ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework ensures completeness

**The Framework:**
```markdown
# ASK - What you want
# CONTEXT - Background info
# CONSTRAINTS - Rules and limits
# EXAMPLE - Show the format
```

**Common Issues from Week 1:**
- Missing spaces after # in headers
- Code blocks for data isolation
- Being specific enough in ASK section

**Graphic:** ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework visual from Week 1

**GRAPHICS:**

**Graphic 1: Framework Recap**
- Purpose: Quick visual reminder of Week 1 foundation
- Type: Four-box framework diagram (simplified version from Week 1)
- Elements: Four connected boxes showing ASK, CONTEXT, CONSTRAINTS, EXAMPLE with icons, simplified compared to Week 1 full version
- Labels: Four section names with one-line descriptors, "Your Foundation" header, common issues callout boxes
- Relationships: Same visual style as Week 1 to trigger recognition, annotations pointing to common mistakes

**SPEAKER NOTES:**

"Quick recap: Markdown gives structure, the framework gives completeness.

[Point to framework]

ASK - what you want. CONTEXT - background. CONSTRAINTS - rules. EXAMPLE - show it.

Common issues I saw in exercises: forgetting the space after the hash for headers, not using code blocks for data, and ASK sections that were too vague.

Today's techniques build directly on this foundation. You'll still use the framework - but now with more sophisticated approaches.

Let's start with role prompting."

[Transition: Click to Segment 1]

---

## SEGMENT 1: ROLE PROMPTING
### Duration: 12 minutes | Slides 4-7

---

### SLIDE 4: THE EXPERTISE PROBLEM

**Title:** The Problem: Generic Expertise

**Content:**

**Without a Role:**
```markdown
Review this code for issues.
```

**AI Response:**
- Generic observations
- Surface-level analysis
- Missing domain expertise
- No particular perspective

**The Question:**
Would you ask a generalist or a specialist to review critical code?

**Graphic:** Generic figure vs. expert figure with credentials

**GRAPHICS:**

**Graphic 1: Generic vs Expert Perspective**
- Purpose: Illustrate the difference between asking anyone vs asking a specialist
- Type: Comparison diagram with personas
- Elements: Left side shows generic stick figure with question mark and generic/shallow response bubble, right side shows professional figure with expertise badges/credentials and detailed response bubble
- Labels: "Generic AI" (left with surface-level comments), "Expert AI" (right with domain-specific insights), "Who would you trust?" question prompt
- Relationships: Side-by-side contrast showing output quality difference, visual weight emphasizing expert advantage

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Let me ask you something: If you had critical code that needed review, would you ask a random person or a senior engineer?

The answer is obvious. But when we prompt AI, we often forget to specify what expertise we want.

[Point to example]

'Review this code' - what perspective should the AI take? Security? Performance? Readability? It doesn't know.

The result: generic, surface-level feedback. Not what you need."

[Transition]

---

### SLIDE 5: THE SOLUTION - ROLE PROMPTING

**Title:** Role Prompting: Activating Expertise

**Content:**

**The Pattern:**
```markdown
You are a [ROLE] with expertise in [DOMAIN].
Your communication style is [STYLE].
```

**Example:**
```markdown
You are a senior software engineer with 10 years of experience
in Python and system design. Your communication style is direct
and technically precise.

Review this code for potential issues...
```

**Why It Works:**
- AI trained on text by experts in various fields
- Role specification activates relevant patterns
- Different roles = different perspectives, vocabulary, depth

**Graphic:** Key unlocking different expertise areas

**GRAPHICS:**

**Graphic 1: Role as Key to Expertise**
- Purpose: Show how role specification activates different knowledge domains
- Type: Metaphor diagram with key/lock concept
- Elements: Central key labeled "Role Prompting", multiple doors/locks around it representing different expertise domains (engineering, analysis, writing, consulting), each door opening to reveal domain-specific knowledge patterns
- Labels: "Role Prompting" (key), expertise domains on each door, "Activates relevant patterns" subtitle
- Relationships: One key (technique) unlocking multiple domains (expertise areas), radial arrangement showing versatility

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"Role prompting solves this. You tell the AI what expertise to bring.

[Walk through pattern]

Role - who they are. Domain - what they know. Style - how they communicate.

Why does this work? AI models were trained on text written by experts in every field. When you specify a role, you're activating those patterns.

A 'senior software engineer' reviews code differently than a 'junior developer' or a 'technical writer'. Different vocabulary, different focus, different depth.

Let me show you."

[Transition]

---

### SLIDE 6: ROLE EXAMPLES IN ACTION

**Title:** Same Task, Different Roles

**Content:**

**Task:** Analyze declining customer satisfaction scores

| Role | Focus Area | Output Style |
|------|------------|--------------|
| Data Analyst | Statistical trends, correlations | Numbers, charts, patterns |
| Customer Success Manager | Relationship factors, churn risk | Narrative, recommendations |
| Operations Manager | Process breakdowns, efficiency | Root cause, action items |
| Executive | Business impact, strategic options | Summary, decisions needed |

**Key Insight:**
The role determines what gets emphasized and how it's communicated.

**Graphic:** Four quadrant showing different outputs from same data

**GRAPHICS:**

**Graphic 1: Same Data, Different Roles**
- Purpose: Demonstrate how roles change perspective and output
- Type: Four-quadrant grid comparison
- Elements: Central hub showing "Customer Satisfaction Data", four quadrants radiating out, each showing different role icon and sample output style (charts for analyst, relationship diagram for CSM, process flow for operations, executive summary for executive)
- Labels: Role names in each quadrant, output type descriptors, focus area for each role, "Same Input, Different Perspectives" title
- Relationships: Single data source branching to four distinct perspectives, visual differentiation of output types

**SPEAKER NOTES:**

"Same data, different roles, completely different outputs.

[Walk through table]

Data Analyst focuses on the numbers - what's the trend, what correlates.
Customer Success Manager thinks about relationships - who's at risk, what do they need.
Operations Manager looks at processes - what's broken, how do we fix it.
Executive wants the business view - what does this mean, what are our options.

The role determines emphasis and communication style.

Which role you choose depends on what you actually need. Don't default to 'expert' - choose the role that matches your need."

[Transition]

---

### SLIDE 7: ROLE PROMPTING BEST PRACTICES

**Title:** Role Prompting: Do's and Don'ts

**Content:**

**Do:**
- Start simple, add detail if needed
- Match role to task complexity
- Include communication style when tone matters
- Test different roles to find what works

**Don't:**
- Over-specify (too many details confuse)
- Use roles for simple tasks
- Assume more detail = better results
- Forget to actually state the task

**The Sweet Spot:**
```markdown
You are a [role] with expertise in [relevant domain].
```

Add more only if output needs adjustment.

**Graphic:** Slider showing "Too Simple" → "Sweet Spot" → "Too Complex"

**GRAPHICS:**

**Graphic 1: Role Specification Spectrum**
- Purpose: Show the balance between under- and over-specification
- Type: Horizontal spectrum/slider diagram
- Elements: Horizontal bar with three zones marked, left zone in red ("Too Simple"), center zone in green ("Sweet Spot"), right zone in red ("Too Complex"), slider indicator positioned at sweet spot
- Labels: Left: "You are an expert" (too vague), Center: "You are a senior consultant with expertise in X" (optimal), Right: "You are a 45-year-old consultant with PhD who worked at..." (overspecified), effectiveness curve shown below
- Relationships: Bell curve or inverted U showing effectiveness peaking at sweet spot, declining on either side

**SPEAKER NOTES:**

"A few best practices before we move on.

[Point to Do's]

Start simple. 'You are a senior consultant' is often enough. Add expertise only if the output needs more specificity.

[Point to Don'ts]

Don't over-specify. I've seen people write entire biographies for their roles. That's too much - it can actually confuse the AI.

[Point to sweet spot]

The sweet spot: role plus relevant domain. 'You are a senior consultant with expertise in organizational change.' That's usually enough.

In your Exercise 2.1, you'll test three levels of role specification to see this for yourself.

Questions on role prompting before we move to few-shot learning?"

[Transition: Click to Segment 2]

---

## SEGMENT 2: FEW-SHOT LEARNING
### Duration: 12 minutes | Slides 8-11

---

### SLIDE 8: THE CONSISTENCY PROBLEM

**Title:** The Problem: Inconsistent Outputs

**Content:**

**The Challenge:**
- Describing format in words is imprecise
- "Make it professional" means different things
- Same prompt, different runs, different formats
- No way to guarantee structure

**What We Want:**
- Exact format every time
- Consistent style and structure
- Reliable, predictable outputs
- Template-like consistency

**Graphic:** Multiple different outputs from same prompt, with question marks

**GRAPHICS:**

**Graphic 1: Inconsistent Output Problem**
- Purpose: Visualize the frustration of unpredictable formats
- Type: Problem diagram showing variation
- Elements: Single prompt box at center, three different output boxes around it showing varying formats (different lengths, structures, styles), question marks between outputs indicating unpredictability, frustrated user icon
- Labels: "Same Prompt" (center), "Run 1", "Run 2", "Run 3" (outputs), "Why the variation?" question, inconsistency indicators highlighting differences
- Relationships: One input producing multiple inconsistent outputs, visual emphasis on undesirable variation

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Here's a problem you've probably experienced: You describe exactly what you want, but the format keeps varying.

You say 'professional email' and sometimes you get formal, sometimes conversational. You say 'bullet points' and sometimes you get three, sometimes ten.

Describing format in words is imprecise. We need a better way.

What if instead of describing what you want, you could show it?"

[Transition]

---

### SLIDE 9: THE SOLUTION - FEW-SHOT LEARNING

**Title:** Few-Shot Learning: Show, Don't Tell

**Content:**

**The Pattern:**
```markdown
# Task
[What you want done]

# Examples

## Example 1
Input: [Sample input]
Output: [Your ideal output]

## Example 2
Input: [Different sample]
Output: [Your ideal output]

# Your Turn
Input: [Actual input]
Output:
```

**Why It Works:**
- Examples eliminate ambiguity
- AI matches the pattern exactly
- Format, length, style all demonstrated
- "Teaching" through demonstration

**Graphic:** Input→Output pattern with arrows showing repetition

**GRAPHICS:**

**Graphic 1: Few-Shot Pattern Structure**
- Purpose: Show the input→output pattern that AI learns to replicate
- Type: Pattern flow diagram
- Elements: Sequence of input→output pairs (Example 1, Example 2) shown with arrows, followed by new input with blank output, pattern learning visualization showing AI recognizing the format
- Labels: "Example 1: Input → Output", "Example 2: Input → Output", "Your Turn: Input → Output", "AI learns the pattern" annotation
- Relationships: Vertical flow showing examples stacking to teach pattern, final arrow showing pattern application

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"Few-shot learning solves this. Instead of describing what you want, you show it.

[Walk through pattern]

You give 2-3 examples of input and your ideal output. Then you provide your actual input and ask for output.

The AI reads your examples and thinks 'Ah, this is the pattern they want.' And it follows that pattern precisely.

This is the single most powerful technique for consistent outputs. If you only learn one thing today, make it this."

[Transition]

---

### SLIDE 10: FEW-SHOT IN ACTION

**Title:** Live Demo: Few-Shot Prompt

**Content:**

**Task:** Extract action items from meeting notes

**The Prompt:**
```markdown
# Task
Extract action items from meeting notes as a checklist.

# Format
- [ ] [Task] - Owner: [Name] - Due: [Date]

# Examples

## Example 1
Input: John will send the proposal by Friday.
Output: - [ ] Send the proposal - Owner: John - Due: Friday

## Example 2
Input: Marketing team to review assets next week.
Output: - [ ] Review assets - Owner: Marketing team - Due: Next week

# Your Turn
Input: [Meeting notes here]
Output:
```

**Graphic:** Demo placeholder

**GRAPHICS:**

**Graphic 1: Few-Shot Demo Structure**
- Purpose: Visualize the complete few-shot prompt structure
- Type: Annotated prompt structure diagram
- Elements: Multi-section layout showing Task section, Format specification, two Example boxes with input/output pairs clearly formatted, and "Your Turn" section, annotations pointing to key elements
- Labels: Section headers (Task, Format, Examples, Your Turn), callout boxes explaining each section's purpose, example content visible within structure
- Relationships: Top-to-bottom flow through prompt sections, examples establishing pattern for final input

**SPEAKER NOTES:**

"[DEMO - Show, don't tell]"

"Let me show you this in action.

[Walk through the prompt structure]

Task - extract action items. Format - specific checkbox structure. Two examples showing input to output.

Notice I'm being very specific in my examples. The format is exact. Owner is labeled. Due date is labeled.

[Run the demo]

Watch how precisely it follows my format...

[Show result]

See? Exact match to my example structure. That's the power of few-shot."

[Transition]

---

### SLIDE 11: FEW-SHOT BEST PRACTICES

**Title:** Few-Shot: Making It Work

**Content:**

**How Many Examples?**
- 2-3 is usually optimal
- More examples = more context used
- Quality > quantity

**Example Selection:**
- Cover different scenarios
- Include edge cases if relevant
- Put most important example last
- Write examples yourself (don't have AI generate them)

**Common Mistakes:**
- Examples that contradict each other
- Too many examples (wastes context)
- AI-generated examples (defeats purpose)
- Forgetting to include "Your Turn" section

**Graphic:** Balance scale showing quality vs. quantity

**GRAPHICS:**

**Graphic 1: Example Quality vs Quantity**
- Purpose: Emphasize that 2-3 quality examples beat many mediocre ones
- Type: Balance scale comparison
- Elements: Traditional balance scale, left side showing 2-3 high-quality examples (glowing/highlighted), right side showing 10+ examples (dimmed/cluttered), scale tipped toward quality side
- Labels: Left: "2-3 Quality Examples" (weighted heavy), Right: "Too Many Examples" (weighted light), "Quality > Quantity" principle statement
- Relationships: Visual weight showing quality examples outweighing quantity, clutter on quantity side suggesting diminishing returns

**SPEAKER NOTES:**

"A few critical points for making few-shot work.

[Point to 'How Many']

Two to three examples is optimal. More isn't necessarily better - you're using context window and potentially adding inconsistency.

[Point to 'Example Selection']

Cover different scenarios. If you're doing email responses, have one quick reply and one detailed reply. Order matters - put your most representative example last.

[Point to 'Common Mistakes']

Most important: write examples yourself. Don't have AI generate them. The whole point is to teach the AI what YOU want, in YOUR style. AI-generated examples defeat that purpose.

In Exercise 2.2, you'll build a few-shot template for a task you actually do. This becomes a reusable tool in your library."

[Transition: Click to Segment 3]

---

## SEGMENT 3: PLATFORM OPTIMIZATION
### Duration: 12 minutes | Slides 12-15

---

### SLIDE 12: PLATFORM DIFFERENCES OVERVIEW

**Title:** Different Platforms, Different Strengths

**Content:**

**Key Insight:**
Each AI platform has formatting preferences and capabilities.

**Universal Techniques (Work Everywhere):**
- Code blocks for data isolation
- Clear section headers
- Explicit constraints
- Examples showing format

**Platform-Specific:**
| Platform | Strength | Special Features |
|----------|----------|------------------|
| Claude | Complex instructions | XML tags, long context |
| ChatGPT | Conversational refinement | Custom Instructions, iteration |
| Gemini | Long documents | Extended context window |

**Graphic:** Three platform logos with strength indicators

**GRAPHICS:**

**Graphic 1: Platform Strengths Overview**
- Purpose: Compare key capabilities across major AI platforms
- Type: Comparison chart with platform icons
- Elements: Three columns for Claude, ChatGPT, and Gemini, each with platform logo, strength bars showing relative capabilities (complex instructions, conversational refinement, long documents), special feature icons
- Labels: Platform names, capability categories with strength indicators, "Universal Techniques" section listing common approaches
- Relationships: Side-by-side comparison showing differentiated strengths, universal techniques bar spanning all platforms

**SPEAKER NOTES:**

"Now that you have role prompting and few-shot, let's talk about where to use them.

Different platforms have different strengths.

[Point to universal]

Some techniques work everywhere: code blocks, headers, explicit constraints, examples. You learned these in Week 1.

[Point to platform table]

Claude excels at following complex, multi-part instructions. ChatGPT is great at conversational refinement - iterating through multiple turns. Gemini can handle very long documents.

Let's look at specific optimizations for each."

[Transition]

---

### SLIDE 13: CLAUDE OPTIMIZATION

**Title:** Optimizing for Claude

**Content:**

**Claude Strengths:**
- Following complex instructions
- Analysis and reasoning
- Long documents (200K context)
- Structured output

**Claude-Specific Techniques:**

**XML Tags:**
```markdown
<instructions>
[Your instructions here]
</instructions>

<context>
[Background information]
</context>

<task>
[The actual request]
</task>
```

**Thinking Requests:**
```markdown
Before answering, think through your reasoning step by step.
```

**Graphic:** Claude logo with technique icons

**GRAPHICS:**

**Graphic 1: Claude Optimization Techniques**
- Purpose: Highlight Claude-specific optimization strategies
- Type: Feature diagram with examples
- Elements: Claude logo as anchor, three technique boxes radiating out (XML tags with code snippet, thinking requests with brain icon, long context with document stack icon), capability indicators
- Labels: "Claude Strengths" header, technique names with code examples, "200K context" specification, "Complex instructions" emphasis
- Relationships: Central logo with technique spokes, visual hierarchy showing primary strengths

**SPEAKER NOTES:**

"If you're using Claude, here are optimizations that work well.

[Point to strengths]

Claude excels at complex instructions and analysis. It handles long documents - up to 200K tokens.

[Point to XML tags]

XML tags are a Claude-specific feature. These tags help Claude understand structure. Wrap your instructions, context, and task in tags.

[Point to thinking]

Claude responds well to 'think through this step by step.' This improves accuracy on complex analysis.

You don't have to use these - standard Markdown works fine. But if you want to optimize for Claude, these help."

[Transition]

---

### SLIDE 14: CHATGPT OPTIMIZATION

**Title:** Optimizing for ChatGPT

**Content:**

**ChatGPT Strengths:**
- Conversational refinement
- Code generation
- Creative writing
- Plugin/tool integration

**ChatGPT-Specific Techniques:**

**Custom Instructions:**
- Persistent context across conversations
- Set once, applies to all chats
- Great for style preferences

**Iterative Refinement:**
```markdown
[First prompt gets you 70%]
"Make it more concise"
"Add a section about X"
"Change the tone to be more formal"
```

**JSON Mode:**
- Request structured data output
- More reliable parsing

**Graphic:** ChatGPT logo with technique icons

**GRAPHICS:**

**Graphic 1: ChatGPT Optimization Techniques**
- Purpose: Highlight ChatGPT-specific optimization strategies
- Type: Feature diagram with examples
- Elements: ChatGPT logo as anchor, three technique boxes (Custom Instructions with settings icon, Iterative Refinement with conversation bubbles showing progressive improvement, JSON Mode with structured data icon)
- Labels: "ChatGPT Strengths" header, technique names, iterative conversation flow example, "Conversational refinement" emphasis
- Relationships: Central logo with technique spokes, conversation flow showing iteration pattern

**SPEAKER NOTES:**

"ChatGPT has different strengths.

[Point to strengths]

It's great at conversational back-and-forth. If your first response isn't quite right, you refine through iteration.

[Point to Custom Instructions]

Custom Instructions is a powerful feature - you set preferences once and they apply to every conversation. Great for 'always respond in my preferred style.'

[Point to iteration]

ChatGPT excels at iteration. Get a 70% response, then refine: 'make it shorter,' 'add more detail here,' 'change the tone.' Three or four refinements often beats one perfect prompt."

[Transition]

---

### SLIDE 15: PLATFORM COMPARISON DEMO

**Title:** Same Prompt, Different Platforms

**Content:**

**The Test:**
Run identical prompt on Claude and ChatGPT

**Compare:**
- Response quality (1-5)
- Instruction following (1-5)
- Response length
- Notable differences

**What to Look For:**
- How each handles structure
- Interpretation of ambiguous instructions
- Default tone and style
- Handling of constraints

**Graphic:** Side-by-side comparison placeholder

**GRAPHICS:**

**Graphic 1: Platform Comparison Demo Layout**
- Purpose: Show evaluation framework for comparing platform outputs
- Type: Side-by-side comparison template
- Elements: Two columns (Claude vs ChatGPT), prompt text box at top spanning both, response boxes below each platform, rating indicators (1-5 scales) for quality and instruction following, observation notes sections
- Labels: Platform names, "Same Prompt" header, rating categories, "Notable Differences" section, comparison criteria listed
- Relationships: Identical prompt input branching to two platform responses, parallel evaluation structure enabling direct comparison

**SPEAKER NOTES:**

"[DEMO - Show, don't tell]"

"Let me show you the difference directly.

I'm going to run the same prompt on both Claude and ChatGPT. Watch for differences.

[Run on both platforms]

[Compare results]

Notice:
- [Point out specific difference in structure]
- [Point out difference in interpretation]
- [Point out difference in length or detail]

Neither is 'better' - they're different. In Exercise 2.3, you'll do this comparison yourself.

The goal isn't to pick a winner. It's to understand when to use which platform for what task."

[Transition: Click to Closing]

---

## CLOSING SECTION
### Duration: 4 minutes | Slides 16-19

---

### SLIDE 16: BONUS TECHNIQUE - THINKING PROMPTS

**Title:** Bonus: Thinking Prompts

**Content:**

**The Technique:**
```markdown
Before providing your answer, think through this step-by-step.
```

or

```markdown
Before writing your response, outline your approach.
```

**When to Use:**
- Complex multi-step problems
- Analysis requiring accuracy
- Debugging or troubleshooting
- When you need to verify reasoning

**Trade-off:**
Slower response, but more accurate and debuggable.

**Graphic:** Brain icon with step indicators

**GRAPHICS:**

**Graphic 1: Thinking Prompts Visualization**
- Purpose: Show how thinking prompts improve accuracy through visible reasoning
- Type: Process diagram with cognitive emphasis
- Elements: Brain icon at center, step-by-step progression showing: 1) receive prompt, 2) think through reasoning, 3) show work, 4) provide answer, accuracy improvement indicator
- Labels: "Think Step-by-Step" prompt example, reasoning chain visualization, "Higher Accuracy" outcome indicator, trade-off note "Slower but more accurate"
- Relationships: Linear flow showing reasoning process, before/after accuracy comparison

**SPEAKER NOTES:**

"One more quick technique before homework.

Thinking prompts. Adding 'think through this step-by-step' or 'outline your approach first' improves accuracy on complex tasks.

[Point to when to use]

Use this for analysis, debugging, multi-step problems. Anywhere accuracy matters more than speed.

The trade-off: longer response (AI shows its work), but more accurate and you can see where reasoning went wrong if it did.

You can combine this with role prompting and few-shot. They all work together."

[Transition]

---

### SLIDE 17: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 2.1: Role Prompting | 20 min | `role-prompting-experiments.md` | Three role variations |
| Exercise 2.2: Few-Shot Template | 25 min | `few-shot-template.md` | Example-based prompting |
| Exercise 2.3: Platform Comparison | 15 min | `platform-comparison.md` | Platform optimization |
| **Total** | **60 min** | | |

**Graphic:** Three exercise cards with technique icons

**GRAPHICS:**

**Graphic 1: Week 2 Exercise Cards**
- Purpose: Present three homework exercises as distinct practice opportunities
- Type: Card-based layout matching Week 1 style
- Elements: Three cards arranged horizontally, each with technique icon (role mask for 2.1, example cards for 2.2, platform logos for 2.3), time estimate, deliverable filename, skills practiced
- Labels: Exercise numbers and names, time allocations (20-25-15 min), deliverable filenames, technique focus for each
- Relationships: Left-to-right sequence showing technique progression from role to few-shot to platform comparison

**SPEAKER NOTES:**

"Three exercises this week.

Exercise 2.1 - role prompting. You'll test the same task with no role, basic role, and detailed role. Compare the differences.

Exercise 2.2 - few-shot. You'll build a reusable template for a task you actually do. This goes in your library.

Exercise 2.3 - platform comparison. Test one prompt on two different platforms. Document the differences.

For 2.3, you need access to two platforms. Both Claude and ChatGPT have free tiers if you need to create an account."

[Transition]

---

### SLIDE 18: RESOURCES

**Title:** Resources for This Week

**Content:**

**Templates & Guides:**
- Role Prompt Template - Participant Guide
- Few-Shot Template - Participant Guide
- Platform Comparison Template - Exercise 2.3

**Platform Documentation:**
- [Anthropic Prompt Engineering](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- [OpenAI Prompt Engineering](https://platform.openai.com/docs/guides/prompt-engineering)
- [Prompting Guide (Community)](https://www.promptingguide.ai/)

**Support:**
- Questions: Cohort support channel
- Office Hours: See schedule

**Graphic:** Resource icons and QR codes

**GRAPHICS:**

**Graphic 1: Week 2 Resource Access**
- Purpose: Organize resources by type for easy reference
- Type: Icon grid with categorized resources
- Elements: Three sections (Templates & Guides, Platform Documentation, Support), each with appropriate icons, optional QR codes for quick mobile access to documentation links
- Labels: Resource category headers, specific resource names (Role Template, Few-Shot Template, Platform docs), access methods
- Relationships: Organized by resource type, visual hierarchy showing templates first (immediate use), then documentation (reference), then support (help)

**SPEAKER NOTES:**

"Resources for this week.

Templates are in your participant guide - role prompting template and few-shot template.

Platform documentation - Anthropic and OpenAI both have excellent prompt engineering guides. I've linked them in your materials.

If you get stuck, post in the cohort channel. Happy to help troubleshoot."

[Transition]

---

### SLIDE 19: NEXT WEEK PREVIEW

**Title:** Next Week: JSON Fundamentals + GitHub Basics

**Content:**

**Preview:**
Creating structured configuration files (`style.json`) and mastering GitHub version control.

**What to Complete Before Then:**
- [ ] Exercise 2.1: Role Prompting Experiments
- [ ] Exercise 2.2: Few-Shot Template
- [ ] Exercise 2.3: Platform Comparison

**Key Preparation:**
- Think about your preferred writing style
- What tone, format, preferences define "your voice"?
- We'll capture this in JSON

**Graphic:** JSON code snippet preview

**GRAPHICS:**

**Graphic 1: Week 3 JSON Preview**
- Purpose: Tease next week's JSON configuration concept
- Type: Preview graphic with code snippet
- Elements: Sample JSON structure showing style preferences (tone, format, constraints), "style.json" filename prominently displayed, connection arrow from "Your Preferences" to structured configuration
- Labels: "Next Week: JSON Fundamentals", "style.json file", "Capture your voice in code" tagline, preview of structure elements
- Relationships: Progression from this week's techniques to next week's structured configuration, building on foundation visual theme

**SPEAKER NOTES:**

"Next week we're introducing JSON - structured data for AI configuration.

You'll create a `style.json` file that captures your personal preferences. Tone, format, things to include, things to avoid. Then you reference this in every prompt for consistent style.

We'll also do more with GitHub - version control, collaboration basics.

To prepare: start thinking about what defines your writing style. What makes your best work yours? We'll formalize that next week.

[Final close]

Great session today. Three power tools in your toolkit now: role prompting for expertise, few-shot for consistency, platform optimization for effectiveness.

Questions before we wrap?

[Take questions]

Excellent. See you next week!"

---

## Appendix: Slide Type Reference

| Slide Type | Purpose | Used In |
|------------|---------|---------|
| Title | Opens presentation | Slide 1 |
| Overview | Sets expectations | Slide 2 |
| Recap | Reviews prior learning | Slide 3 |
| Problem/Hook | Creates tension | Slides 4, 8 |
| Solution | Introduces technique | Slides 5, 9 |
| Examples | Shows technique in use | Slides 6, 10 |
| Best Practices | Do's and don'ts | Slides 7, 11 |
| Platform Overview | Introduces differences | Slide 12 |
| Platform Specific | Claude/ChatGPT tips | Slides 13, 14 |
| Comparison Demo | Shows differences | Slide 15 |
| Bonus Technique | Additional tool | Slide 16 |
| Homework Preview | Sets up exercises | Slide 17 |
| Resources | Provides support | Slide 18 |
| Next Week Preview | Creates continuity | Slide 19 |

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
