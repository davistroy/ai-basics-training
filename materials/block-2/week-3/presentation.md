# **POWERPOINT PRESENTATION: BLOCK 2 WEEK 3**
## **Quality Systems + Template Workflows**

**Block:** 2: AI Workflow Engineering
**Week Number:** 3
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Consultants with working workflows from Week 2

**Key Thesis:** Quality systems are operating procedures for AI - automating evaluation through LLM-as-judge patterns and structured JSON data transforms ad-hoc review into systematic, scalable quality control.

**Week Learning Objectives:** By the end of this session, participants will:
1. Understand quality systems as operating procedures for AI
2. Implement the LLM-as-judge pattern for automated quality evaluation
3. Use JSON data structures for workflow data flow
4. Apply the template pattern to build a second workflow

**Entry Criteria:**
- [ ] First workflow built and tested
- [ ] Error handling implemented
- [ ] Logging active
- [ ] 5+ successful workflow executions

**Exit Criteria:**
- [ ] Quality check module integrated into workflow
- [ ] JSON data structures used for workflow data
- [ ] Second workflow built using template pattern
- [ ] Rubric-based quality gate implemented
- [ ] Template versioning strategy established

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Quality in Automated Workflows (12 min) - Slides 4-8
3. Segment 2: Automated Quality Checks (10 min) - Slides 9-12
4. Segment 3: JSON Data Structures (13 min) - Slides 13-17
5. Segment 4: Template Workflow Pattern (4 min) - Slides 18-19
6. Homework Preview & Close (3 min) - Slides 20-22

**Total Slides:** 22

---

## SLIDE 1: TITLE SLIDE

**Title:** Block 2 Week 3: Quality Systems + Template Workflows

**Subtitle:** Teaching Your Workflows to Check Their Own Work

**Content:**
- AI Practitioner Training Program
- Block 2: AI Workflow Engineering
- [Instructor Name]
- [Date]

**Graphic:** Clean title slide with Block 2 orange color theme. Quality check or verification icon.

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Week 3! Last week you built working workflows. This week we make them smart - they'll evaluate their own output quality before delivering.

Quick status check: Who has a working workflow with at least 5 logged executions? [Count hands]

Great. For those who are catching up, follow along today - you'll apply this as soon as your workflow is ready.

Here's what we're solving: Your workflow produces output, but how do you know if it's good? Today, we automate that judgment."

[Transition: Click to next slide]

---

## SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Week 2 recap, readiness check |
| 3-15 min | Segment 1 | Quality in Automated Workflows |
| 15-25 min | Segment 2 | Automated Quality Checks (LLM-as-Judge) |
| 25-38 min | Segment 3 | JSON Data Structures |
| 38-42 min | Segment 4 | Template Workflow Pattern |
| 42-45 min | Close | Homework & Week 4 Preview |

**Graphic:** Visual timeline with orange markers

**GRAPHICS:**

**Graphic 1: Week 3 Session Timeline**
- Purpose: Show session flow emphasizing quality and JSON segments
- Type: Horizontal timeline with segment markers
- Elements: Timeline bar 0-45 minutes, five segments with varying durations, orange highlights on Segments 2-3 (quality and JSON focus areas)
- Labels: Time markers, segment names, key topics
- Relationships: Sequential flow building from quality concepts to practical JSON implementation

**SPEAKER NOTES:**

"Here's our agenda:

First, we'll understand quality systems conceptually - why they matter for automation.

Then, the core technique: using AI to evaluate AI. This is the LLM-as-judge pattern.

We'll spend time on JSON data structures - the format that makes quality scoring reliable.

And we'll close with the template pattern for building your second workflow efficiently.

By the end, you'll know how to make your workflows self-checking."

[Transition]

---

## SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Understand quality as operating procedures**
   - Your rubrics become automated checks

2. **Implement the LLM-as-judge pattern**
   - AI evaluating AI output

3. **Use JSON for structured data flow**
   - Reliable scoring and routing

4. **Apply the template workflow pattern**
   - Clone, adapt, maintain

**Graphic:** Checklist visual with quality/verification icons

**SPEAKER NOTES:**

"Four objectives for today.

First, you'll understand how quality systems work in automation - they're operating procedures for AI.

Second, you'll learn the LLM-as-judge pattern - the key technique for automated quality.

Third, JSON - the data format that makes it all work reliably.

Fourth, the template pattern - so you can efficiently build your second workflow.

Let's start with why quality matters."

[Transition: Click to Segment 1]

---

## SEGMENT 1: QUALITY IN AUTOMATED WORKFLOWS
### Duration: 12 minutes | Slides 4-8

---

## SLIDE 4: THE AUTOMATION QUALITY CHALLENGE

**Title:** Manual Review Doesn't Scale

**Content:**

**The Problem:**

| Scale | Review Feasibility |
|-------|-------------------|
| 10 outputs/day | Easy - review everything |
| 50 outputs/day | Manageable - spot check |
| 100 outputs/day | Exhausting - miss issues |
| 500 outputs/day | Impossible - give up |

**Current Reality:**
Without automated quality, you either:
- Review everything (doesn't scale)
- Trust blindly (risky)
- Give up on automation (waste potential)

**Graphic:** Graph showing review effort vs. output volume

**GRAPHICS:**

**Graphic 1: Manual Review Scalability Challenge**
- Purpose: Demonstrate exponential growth of review effort as output volume increases
- Type: Line graph with threshold zones
- Elements: X-axis showing outputs/day (10, 50, 100, 500), Y-axis showing review effort/time, exponential curve showing effort, color zones (green "Easy", yellow "Manageable", orange "Exhausting", red "Impossible"), breaking point annotation at 100-500 range
- Labels: Axis titles, zone labels, "Scale Problem" annotation showing gap between effort available and effort required
- Relationships: Exponential relationship showing manual review becomes unsustainable, visual justification for automation need

**SPEAKER NOTES:**

"[Hook - The scale problem]"

"Let's be honest about the challenge.

If your workflow produces 10 outputs a day, you can review every one. Quality is easy.

At 50, it's manageable. You spot check.

At 100, you're exhausted. Issues slip through.

At 500, it's impossible. You're either blindly trusting or you've given up on automation entirely.

This is why we need automated quality checks. Not because we don't trust AI, but because scale demands it."

[Transition]

---

## SLIDE 5: QUALITY AS OPERATING PROCEDURES

**Title:** Quality Systems = Operating Procedures for AI

**Content:**

**The Three Pillars (Preview of Block 3):**

| Pillar | Purpose | Your Implementation |
|--------|---------|---------------------|
| Explicit Goals | What success looks like | Quality thresholds |
| Progress Records | What happened | Your logging system |
| Operating Procedures | How to behave | Quality evaluation prompts |

**Key Insight:**
> Quality systems ARE operating procedures. Your Block 1 rubrics become automated checks.

**Graphic:** Three pillars visual with Block 2 components mapped

**GRAPHICS:**

**Graphic 1: Three Pillars of Quality Systems**
- Purpose: Connect Block 3 framework preview to current Block 2 implementations
- Type: Three-column pillar diagram with mappings
- Elements: Three architectural pillars (Explicit Goals, Progress Records, Operating Procedures), Block 2 component mapped under each pillar (quality thresholds, logging system, evaluation prompts), foundation showing connection to Block 1 rubrics
- Labels: Pillar names, purposes, Block 2 implementations, "Foundation: Block 1 Rubrics" annotation
- Relationships: Pillars as structural framework, Block 2 work as practical implementation of each pillar, preview of Block 3 depth

**SPEAKER NOTES:**

"Here's a conceptual framework that will become important in Block 3.

Quality systems have three pillars:

Explicit goals - what does 'good' look like? Your quality thresholds define this.

Progress records - what happened? Your logging system captures this.

Operating procedures - how should AI behave? Your evaluation prompts encode this.

[Point to key insight]

Your Block 1 rubrics - the criteria you defined for good output - become the operating procedures for your automated quality checks.

This is the connection between Block 1 and Block 2. Everything you learned about quality criteria now becomes automation."

[Transition]

---

## SLIDE 6: QUALITY GATE IMPLEMENTATION

**Title:** Three Layers of Quality Checking

**Content:**

```
Input → [PRE-GENERATION] → AI → [POST-GENERATION] → Output
             Check                    Check
               │                        │
               ▼                        ▼
        Validate input           Evaluate output
        Complete? Valid?         Score against rubric
               │                        │
        If fail: Stop            If fail: Route
               │                        │
               ▼                        ▼
                    [HUMAN REVIEW]
                    When automated fails
```

**Three Gate Types:**
1. **Pre-generation:** Input validation
2. **Post-generation:** Output evaluation
3. **Human review:** Escalation when needed

**Graphic:** Flow diagram with three gates highlighted

**GRAPHICS:**

**Graphic 1: Three-Layer Quality Gate Architecture**
- Purpose: Show the complete quality checking flow with three intervention points
- Type: Process flow with decision gates
- Elements: Linear workflow (Input → Pre-Gen Check → AI → Post-Gen Check → Output) with two decision diamonds, failure paths leading down to Human Review layer, success paths continuing right, gate type labels (Validate, Evaluate, Escalate)
- Labels: Gate names, check descriptions ("Complete? Valid?" at pre-gen, "Score against rubric" at post-gen), "Today's Focus" callout on post-generation gate
- Relationships: Sequential gates as quality filters, failure escalation to human review, post-generation as primary focus point

**SPEAKER NOTES:**

"Quality checking happens at three points.

[Point to pre-generation]

Pre-generation - before AI even runs. Is the input complete? Valid? If required fields are missing, we stop here.

[Point to post-generation]

Post-generation - after AI generates. Does the output meet our standards? This is where we score against our rubrics.

[Point to human review]

Human review - when automated checks fail or flag something uncertain. This is the escalation path.

Today we focus on post-generation - the quality evaluation after AI generates output."

[Transition]

---

## SLIDE 7: BLOCK 1 FOUNDATIONS APPLIED

**Title:** Your Rubrics Become Automated Checks

**Content:**

**Block 1:** Manual Quality Rubric
```
Criterion: Clarity
- 5: Crystal clear, no ambiguity
- 3: Mostly clear, minor issues
- 1: Confusing, needs rewrite
```

**Block 2:** Automated Evaluation Prompt
```
Score this output for Clarity (1-5):
- 5: Crystal clear, no ambiguity
- 3: Mostly clear, minor issues
- 1: Confusing, needs rewrite

Output JSON: {"clarity": {"score": X, "reason": "..."}}
```

**Same criteria, different format**

**Graphic:** Side-by-side comparison of manual rubric and evaluation prompt

**SPEAKER NOTES:**

"Here's the key connection.

[Point to Block 1]

In Block 1, you created quality rubrics. You had criteria like clarity, completeness, style. You defined what 5 means, what 3 means, what 1 means.

[Point to Block 2]

In Block 2, that exact same rubric becomes an evaluation prompt. We give it to a second AI call and ask it to score the output.

Same criteria. Same scoring. Just automated.

This is why Block 1 mattered. Those rubrics you created are now the operating instructions for your quality system."

[Transition]

---

## SLIDE 8: SEGMENT 1 SUMMARY

**Title:** Quality System Foundations

**Content:**

**Key Takeaways:**
- Manual review doesn't scale
- Quality systems = operating procedures for AI
- Three layers: pre-generation, post-generation, human review
- Block 1 rubrics become evaluation prompts

**Coming Up:**
How to implement automated quality checks

**Graphic:** Simple summary icons

**SPEAKER NOTES:**

"Before we implement, let me summarize:

Manual review doesn't scale. At some point, you need automation.

Quality systems are essentially operating procedures - rules for how AI should behave.

We have three checkpoints: validate input, evaluate output, escalate when needed.

And your Block 1 rubrics are the foundation - they become your automated checks.

Now let's see how to actually implement this."

[Transition: Click to Segment 2]

---

## SEGMENT 2: AUTOMATED QUALITY CHECKS
### Duration: 10 minutes | Slides 9-12

---

## SLIDE 9: THE LLM-AS-JUDGE PATTERN

**Title:** Using AI to Check AI

**Content:**

**The Pattern:**
```
┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
│ Generate │───▶│ Evaluate │───▶│  Parse   │───▶│  Route   │
│ Content  │    │ Quality  │    │  Score   │    │ Based On │
└──────────┘    └──────────┘    └──────────┘    │  Score   │
                                                └──────────┘
```

**How It Works:**
1. First AI call generates content
2. Second AI call evaluates the content
3. Parse the evaluation score
4. Route based on score

**Key Insight:**
The evaluator AI follows your criteria, not its own.

**Graphic:** Flow diagram with four connected steps

**GRAPHICS:**

**Graphic 1: LLM-as-Judge Pattern Flow**
- Purpose: Illustrate the four-step pattern for automated quality evaluation
- Type: Horizontal process flow with data annotations
- Elements: Four sequential boxes (Generate Content, Evaluate Quality, Parse Score, Route Based On Score), connecting arrows with data labels ("generated content", "evaluation result", "parsed score", "routing decision"), AI icon on Generate and Evaluate steps showing two separate AI calls
- Labels: Step names, data passing between steps, "1st AI Call" and "2nd AI Call" annotations, "Your Criteria Applied Here" callout on Evaluate step
- Relationships: Two-AI-call pattern showing separation of generation and evaluation, structured data flow from text to score to decision

**SPEAKER NOTES:**

"[INSIGHT - The core pattern]"

"This is the LLM-as-judge pattern. It's elegantly simple.

Step 1: Your first AI call generates the content - just like you've been doing.

Step 2: A SECOND AI call evaluates that content. This is the quality check.

Step 3: Parse the evaluation - we need a structured score.

Step 4: Route based on the score - high scores pass, low scores fail.

[Point to key insight]

Critical point: the evaluator follows YOUR criteria. You define what 'good' means. The AI applies your rubric, not its own judgment.

This is why the evaluation prompt is so important."

[Transition]

---

## SLIDE 10: THE EVALUATION PROMPT PATTERN

**Title:** Structuring the Quality Check

**Content:**

```markdown
You are evaluating a [deliverable type] for quality.

## Criteria (score each 1-5)

### 1. Clarity
- 5: Crystal clear, no ambiguity
- 3: Mostly clear, minor issues
- 1: Confusing, needs rewrite

### 2. Completeness
- 5: All required elements present
- 3: Most elements present
- 1: Missing critical elements

[Additional criteria...]

## Content to Evaluate
```
{{generated_content}}
```

## Output Format (JSON only)
{"scores": {...}, "overall_score": X.X, "pass": true/false}
```

**Graphic:** Highlighted sections of the prompt

**SPEAKER NOTES:**

"Here's the structure of an evaluation prompt.

[Walk through sections]

First, you state what's being evaluated.

Then, your criteria - directly from Block 1 rubrics. Each criterion has clear scoring definitions.

Next, the content to evaluate - this is the variable that holds the AI's generated output.

Finally, the output format - we request JSON so we can parse it reliably.

The key is explicit criteria with clear scoring levels. The AI applies YOUR rubric."

[Transition]

---

## SLIDE 11: ROUTING LOGIC

**Title:** What to Do with the Score

**Content:**

**Standard Routing:**

| Score Range | Action | Destination |
|-------------|--------|-------------|
| >= 4.0 | ✓ Proceed | Output to client |
| 3.0 - 3.9 | ⚠ Flag | Human review queue |
| < 3.0 | ✗ Fail | Regenerate or stop |

**In Your Workflow:**
```
IF overall_score >= 4:
    → Output module
ELSE IF overall_score >= 3:
    → Review notification + Output
ELSE:
    → Error handler / Retry
```

**Graphic:** Decision tree showing three paths

**SPEAKER NOTES:**

"Once you have a score, you route based on it.

[Point to table]

Score 4 or above: High quality. Proceed directly to output.

Score 3 to 3.9: Acceptable but flagged. Send to human review or output with a warning.

Score below 3: Below standards. Either retry generation or fail gracefully.

[Point to workflow logic]

In your workflow, this is conditional routing. If score >= 4, go to output. Else if >= 3, go to review. Else, handle as error.

The thresholds aren't fixed - calibrate them based on your actual results."

[Transition]

---

## SLIDE 12: SEGMENT 2 SUMMARY

**Title:** Automated Quality Checks

**Content:**

**Key Takeaways:**
- LLM-as-judge: AI evaluates AI output
- Evaluation prompt mirrors your Block 1 rubrics
- JSON output enables reliable parsing
- Route based on score thresholds

**You'll Practice:**
Exercise 3.1 - Add quality check module to your workflow

**Graphic:** Simple recap of the pattern

**SPEAKER NOTES:**

"Let me summarize the quality check pattern:

LLM-as-judge means using AI to evaluate AI. It's a second call that scores the first call's output.

Your evaluation prompt is your Block 1 rubric in a different format.

We use JSON because it's reliable to parse.

And we route based on scores - pass, review, or fail.

In Exercise 3.1, you'll add this to your workflow.

Now let's talk about JSON - the format that makes this reliable."

[Transition: Click to Segment 3]

---

## SEGMENT 3: JSON DATA STRUCTURES
### Duration: 13 minutes | Slides 13-17

---

## SLIDE 13: WHY JSON FOR WORKFLOWS

**Title:** Structured Data for Reliable Automation

**Content:**

**The Problem with Unstructured Responses:**
```
"The quality score is about 4 out of 5. It's pretty good
but could use some improvement in clarity..."
```
→ How do you parse "about 4"? What's the exact score?

**The Solution with JSON:**
```json
{"overall_score": 4.0, "pass": true, "clarity": 3.8}
```
→ Exact values. Easy to parse. Reliable routing.

**Why JSON Works:**
- Structured: defined keys and values
- Parseable: workflow platforms handle it natively
- Standard: same format everywhere
- AI-friendly: Claude/GPT generate it reliably

**Graphic:** Side-by-side comparison of unstructured vs. JSON

**GRAPHICS:**

**Graphic 1: Unstructured vs JSON Comparison**
- Purpose: Show why JSON is necessary for reliable workflow automation
- Type: Before-and-after comparison with problems highlighted
- Elements: Left side showing unstructured text response with parsing challenges highlighted (variable format, ambiguous values, hard to extract), right side showing JSON with clear structure and easy parsing, parsing code snippets showing difficulty vs ease
- Labels: "Unstructured Text (Problems)" header, "JSON (Reliable)" header, problem annotations on left, benefits annotations on right
- Relationships: Contrast showing JSON as solution to unstructured text parsing unreliability

**SPEAKER NOTES:**

"Why do we insist on JSON for quality scores?

[Point to unstructured]

Look at this response: 'The score is about 4 out of 5.' How do you parse 'about 4'? Is it 4.0? 3.8? What happens when it says 'pretty good'?

[Point to JSON]

With JSON: exact value 4.0. Boolean pass/fail. Clear structure.

This is the difference between 'mostly works' and 'actually reliable.'

JSON is structured, parseable, standard, and AI generates it well when you ask correctly."

[Transition]

---

## SLIDE 14: BASIC JSON STRUCTURE

**Title:** JSON Fundamentals

**Content:**

```json
{
  "string": "text value",
  "number": 42,
  "decimal": 3.14,
  "boolean": true,
  "null_value": null,
  "array": ["item1", "item2", "item3"],
  "object": {
    "nested_key": "nested value"
  }
}
```

**Key Rules:**
- Keys in double quotes
- Strings in double quotes
- No trailing commas
- Brackets must match

**Graphic:** Color-coded JSON with element types labeled

**GRAPHICS:**

**Graphic 1: JSON Anatomy with Syntax Highlighting**
- Purpose: Teach JSON structure through visual syntax highlighting
- Type: Annotated code example
- Elements: JSON example with color coding (keys in blue, strings in green, numbers in orange, booleans in purple), element type labels (object, array, string, number, boolean), bracket/brace matching indicators
- Labels: Data type annotations, structural element names (root object, nested object, array), syntax markers
- Relationships: Hierarchical nesting shown through indentation and bracket matching, type system illustrated through color coding

**SPEAKER NOTES:**

"Quick JSON refresher if you need it.

[Walk through types]

Strings go in double quotes.

Numbers don't need quotes.

Booleans are true or false, lowercase.

Arrays use square brackets with comma-separated items.

Objects use curly braces with key-value pairs.

[Point to rules]

Common errors: missing quotes around keys, trailing commas, mismatched brackets. Use a JSON validator if you're having issues."

[Transition]

---

## SLIDE 15: QUALITY EVALUATION JSON

**Title:** JSON Structure for Quality Scores

**Content:**

```json
{
  "scores": {
    "clarity": {"score": 4, "reason": "Well-structured"},
    "completeness": {"score": 5, "reason": "All elements present"},
    "style": {"score": 4, "reason": "Matches tone guide"}
  },
  "overall_score": 4.3,
  "pass": true,
  "suggestions": [
    "Consider more specific examples",
    "Add executive summary"
  ]
}
```

**What Each Field Provides:**
- `scores`: Individual criterion breakdown
- `overall_score`: Single number for routing
- `pass`: Boolean for simple logic
- `suggestions`: Improvement hints

**Graphic:** JSON with callouts explaining each section

**SPEAKER NOTES:**

"Here's the JSON structure for quality evaluation.

[Point to scores]

The scores object has each criterion with its score and reasoning.

[Point to overall_score]

Overall_score is the single number we use for routing. Calculate as average or weighted average.

[Point to pass]

Pass is a boolean - true or false. Simplest routing logic.

[Point to suggestions]

Suggestions are helpful if you want to include improvement hints in review notifications.

This structure gives you flexibility. Route on overall_score, but you have detailed breakdowns available."

[Transition]

---

## SLIDE 16: WORKFLOW EXECUTION DATA

**Title:** Full Execution Record Structure

**Content:**

```json
{
  "execution": {
    "id": "exec-12345",
    "workflow_name": "Proposal Generator",
    "timestamp": "2025-01-15T14:30:00Z"
  },
  "input": {
    "client_name": "Acme Corp",
    "project_type": "Digital Transformation"
  },
  "quality": {
    "overall_score": 4.3,
    "passed": true
  },
  "output": {
    "status": "success",
    "destination": "email"
  }
}
```

**Why This Matters:**
Complete records enable Week 4 optimization analysis

**Graphic:** Execution data structure with sections labeled

**SPEAKER NOTES:**

"Beyond quality scores, here's a complete execution record.

[Point to sections]

Execution metadata: when, which workflow, unique ID.

Input: what was processed.

Quality: how it scored.

Output: where it went, what happened.

This is what your logging captures. Each execution is one of these records.

In Week 4, we'll analyze these records to find optimization opportunities. The structure you set up now enables that analysis."

[Transition]

---

## SLIDE 17: GETTING AI TO RETURN VALID JSON

**Title:** Prompting for Reliable JSON Output

**Content:**

**Key Instructions:**
```
Respond with ONLY valid JSON.
No markdown formatting.
No text before or after the JSON.
No code blocks or backticks.
```

**Provide Example:**
```
Your response should look exactly like:
{"overall_score": 4.2, "pass": true, "scores": {...}}
```

**Handle Failures:**
- Wrap parsing in error handling
- If parse fails, retry once
- If still fails, flag for human review

**Graphic:** Prompt with JSON instructions highlighted

**SPEAKER NOTES:**

"Getting AI to return valid JSON requires explicit instructions.

[Point to key instructions]

Be very explicit: ONLY valid JSON. No markdown. No text before or after. No code blocks.

[Point to example]

Provide an example of the exact format you want. AI follows examples well.

[Point to failure handling]

Even with good instructions, sometimes JSON is malformed. Always wrap parsing in error handling. Retry once, then flag for review.

In Exercise 3.1, you'll implement this in your quality check module."

[Transition: Click to Segment 4]

---

## SEGMENT 4: TEMPLATE WORKFLOW PATTERN
### Duration: 4 minutes | Slides 18-19

---

## SLIDE 18: BUILDING YOUR SECOND WORKFLOW

**Title:** Clone, Adapt, Maintain

**Content:**

**The Template Pattern:**
```
Base Template:
Trigger → Data → AI → Quality → Output

Variant 1: Proposal Generator
[Same structure, different prompt]

Variant 2: Email Summarizer
[Same structure, different prompt]
```

**What to Clone:**
- Trigger structure
- Error handling
- Quality evaluation
- Logging

**What to Adapt:**
- AI prompt template (from Block 1)
- Quality criteria (if different)
- Input/output mappings

**Graphic:** Template branching into variants

**GRAPHICS:**

**Graphic 1: Template Workflow Branching Pattern**
- Purpose: Show how one base workflow spawns multiple variants
- Type: Tree diagram showing template and variants
- Elements: Base workflow at top (Workflow Template v1), three variant branches below (Content Summarizer v1, Email Responder v1, Report Generator v1), arrows showing clone/adapt relationship, percentage indicators showing what percentage of template remains unchanged
- Labels: "Base Template" header, variant names, "Clone & Adapt" arrows, commonality percentages (85% shared, 15% customized per variant)
- Relationships: One-to-many relationship from template to variants, visual emphasis on reuse efficiency

**SPEAKER NOTES:**

"For your second workflow, we use the template pattern.

You've built one workflow with error handling, quality checks, and logging. That infrastructure is reusable.

Clone the workflow, then swap:
- The AI prompt (different Block 1 template)
- Quality criteria (if the deliverable type is different)
- Input/output mappings (as needed)

Keep the structure, change the content.

This is efficient: you're not rebuilding logging and error handling. Just adapting."

[Transition]

---

## SLIDE 19: VERSIONING YOUR WORKFLOWS

**Title:** Template Versioning Strategy

**Content:**

**Naming Convention:**
```
[Deliverable Type] [Action] v[Major].[Minor]

Examples:
- Proposal Generator v1.0
- Proposal Generator v1.1 (threshold adjusted)
- Proposal Generator v2.0 (new structure)
```

**When to Increment:**
| Change Type | Version Bump | Example |
|-------------|-------------|---------|
| Prompt tweaks | v1.0 → v1.1 | Adjust wording |
| Threshold changes | v1.0 → v1.1 | Raise pass threshold |
| New structure | v1.0 → v2.0 | Add new step |
| New deliverable | v1.0 | New workflow |

**Document Everything:**
Changelog in workflow documentation

**Graphic:** Version timeline showing progression

**SPEAKER NOTES:**

"Version your workflows so you can track changes.

[Point to naming]

Include deliverable type, action, and version number.

[Point to table]

Minor version for tweaks and adjustments. Major version for structural changes.

[Point to documentation]

Keep a changelog. When you adjust a threshold, note it. When you change the prompt, document why.

This becomes important when you have multiple variants and need to know which version produced which results.

In Exercise 3.2, you'll build your second workflow and document your workflow family."

[Transition: Click to Closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 20-22

---

## SLIDE 20: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| 3.1: Quality Check | 25 min | Evaluation module + prompt | LLM-as-judge |
| 3.2: Second Workflow | 25 min | Variant workflow + docs | Template pattern |
| 3.3: JSON Schema | 10 min | `workflow-data-schema.json` | Data structure |
| **Total** | **60 min** | | |

**Critical:** Two working workflows with quality checks by end of week

**Graphic:** Exercise progress bar

**SPEAKER NOTES:**

"Three exercises this week, about 60 minutes total.

Exercise 3.1 - 25 minutes - add quality check to your existing workflow. Create the evaluation prompt, add the module, configure routing.

Exercise 3.2 - 25 minutes - build your second workflow by cloning the first. Swap the prompt, adjust as needed, test.

Exercise 3.3 - 10 minutes - design your JSON schema for execution data.

[Emphasize]

By end of week, you need TWO working workflows with quality checks. This is capstone progress."

[Transition]

---

## SLIDE 21: RESOURCES

**Title:** Resources for This Week

**Content:**

**JSON Tools:**
- JSON Validator: jsonlint.com
- JSON Schema: json-schema.org

**Platform Documentation:**
- Make JSON: make.com/en/help/tools/json
- n8n JSON: docs.n8n.io/data/data-structure

**Support:**
- Questions: [Support channel]
- JSON issues: Paste your JSON and error for fastest help

**Graphic:** Resource icons with links

**SPEAKER NOTES:**

"Resources for this week:

JSONLint for validating JSON syntax - paste your JSON, it tells you what's wrong.

Platform docs for JSON parsing in your specific platform.

If you're stuck on JSON issues, paste your JSON and the error message in the support channel. We can usually spot the issue quickly."

[Transition]

---

## SLIDE 22: NEXT WEEK PREVIEW

**Title:** Next Week: Workflow Optimization

**Content:**

**Week 4 Focus:**
- Analyze performance data
- Optimize for cost, speed, quality
- Context window management
- A/B testing concepts

**Preparation Required:**
- [ ] Two working workflows with quality checks
- [ ] 10+ logged executions total
- [ ] Quality score distribution noted
- [ ] Identify slowest steps

**The Goal:**
Make your workflows faster, cheaper, and better.

**Graphic:** Optimization icons - speed, cost, quality

**SPEAKER NOTES:**

"Next week: optimization.

We'll analyze your execution data and find ways to make workflows faster, cheaper, and better quality.

To be ready:
- Two working workflows with quality checks
- At least 10 logged executions
- Know your quality score distribution
- Notice which steps are slowest

[Final close]

Questions before we wrap?

[Take questions]

Great session. You now know how to make your workflows self-checking. That's a major capability.

Build those quality checks, create your second workflow, and see you next week!"

---

## Appendices

**Slide Type Definitions:** TITLE SLIDE | PROBLEM STATEMENT | INSIGHT / REVELATION | CONCEPT INTRODUCTION | FRAMEWORK / MODEL | COMPARISON | DEEP DIVE | CASE STUDY | PATTERN / BEST PRACTICE | METRICS / DATA | ARCHITECTURE / DIAGRAM | OBJECTION HANDLING | ACTION / NEXT STEPS | SUMMARY / RECAP | SECTION DIVIDER | CLOSING / CALL TO ACTION | Q&A / CONTACT

**Content Guidelines:** Use parallel structure in bullets | Clear tables with headers | Bad/Good example contrasts | Key principle callouts | Stage directions in speaker notes `[Pause]` `[Point to X]` `[Emphasize]`

**Block 2 Orange Theme:** Primary Orange (#FF6B35) for branding | Accent blues/grays | Orange highlights for emphasis | Consistent color across all Block 2 presentations

**Quality Checklist:** Learning objectives align | Key Thesis clear | Complete speaker notes | Technical accuracy | Relevant examples | Research citations specific | Q&A addresses objections | Orange theme consistent | Progressive building | Realistic timing

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |

---

**Template Usage:**
1. Use Block 2 orange color theme throughout
2. Prepare quality evaluation demo with routing
3. Have JSON examples ready
4. Test JSON parsing in demo platform
5. Cross-reference with instructor and participant guides
