# **BLOCK 2 WEEK 3: Quality Systems + Template Workflows**

**Block:** 2: AI Workflow Engineering
**Week:** 3 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** [← Week 2](../week-2/participant-guide.md) | **Week 3** | [Week 4 →](../week-4/participant-guide.md)

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
| 1 | Implement automated quality checks using the LLM-as-judge pattern | Exercise 3.1 |
| 2 | Configure quality-based routing in workflows | Exercise 3.1 |
| 3 | Build a second workflow using the template pattern | Exercise 3.2 |
| 4 | Design JSON data structures for workflow data | Exercise 3.3 |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] First workflow built and tested (from Week 2)
- [ ] Error handling implemented
- [ ] Logging active with 5+ executions logged
- [ ] Block 1 quality rubric accessible

**Not ready?** Complete Week 2 exercises or reach out in the support channel for help.

---

## Key Concepts

### Concept 1: Quality as Operating Procedures

**Definition:**
Quality systems are the operating procedures that ensure consistent AI output across all executions, without human variance.

**Why It Matters:**
Manual review doesn't scale. At 10 outputs a day, you can review everything. At 100, it's exhausting. At 1000, it's impossible. Automated quality systems let you scale while maintaining standards.

**Core Principle:**
> Quality systems ARE operating procedures for AI. Your Block 1 rubrics become automated checks.

**The Three Pillars (Preview of Block 3):**

| Pillar | Purpose | Block 2 Application |
|--------|---------|---------------------|
| Explicit Goals | Success criteria | Quality thresholds |
| Progress Records | Execution logs | Your logging system |
| Operating Procedures | How to behave | Quality evaluation prompts |

---

### Concept 2: The LLM-as-Judge Pattern

**Definition:**
Using a second AI call to evaluate the output of a first AI call against defined criteria, producing structured scores that enable automated routing.

**Why It Matters:**
This pattern lets AI check AI's work, catching quality issues before they reach clients and enabling systematic improvement.

**The Pattern:**
```
┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
│ Generate │───▶│ Evaluate │───▶│  Parse   │───▶│  Route   │
│ Content  │    │ Quality  │    │  Score   │    │ Based On │
└──────────┘    └──────────┘    └──────────┘    │  Score   │
                                                └──────────┘
                                                     │
                     ┌───────────────────────────────┼───────────────────────────────┐
                     │                               │                               │
                     ▼                               ▼                               ▼
              ┌──────────┐                    ┌──────────┐                    ┌──────────┐
              │ Score≥4  │                    │ Score 3  │                    │ Score<3  │
              │ → Output │                    │ → Review │                    │ → Retry  │
              └──────────┘                    └──────────┘                    └──────────┘
```

**Key Insight:**
The evaluation prompt mirrors your Block 1 rubrics - same criteria, different format.

---

### Concept 3: Quality Gate Implementation

**Definition:**
Checkpoints in a workflow that validate inputs or outputs before proceeding to the next step.

**Why It Matters:**
Quality gates catch problems early, prevent bad outputs from reaching clients, and provide data for improvement.

**Three Types of Quality Gates:**

| Gate Type | When | Purpose | Example |
|-----------|------|---------|---------|
| **Pre-generation** | Before AI | Validate input | Check required fields present |
| **Post-generation** | After AI | Evaluate output | Score against rubric |
| **Human review** | When automated fails | Escalation | Flag for manual check |

**Routing Logic:**
```
Score ≥ 4.0  →  Proceed to output (high quality)
Score 3.0-3.9  →  Flag for human review (acceptable but needs checking)
Score < 3.0  →  Regenerate or fail (below standards)
```

---

### Concept 4: JSON Data Structures

**Definition:**
Structured data format using key-value pairs that enables consistent data flow between workflow steps.

**Why It Matters:**
JSON provides structured data that can be reliably parsed, manipulated, and analyzed. AI generates JSON consistently when properly prompted.

**Basic JSON Syntax:**
```json
{
  "string_field": "text value",
  "number_field": 42,
  "boolean_field": true,
  "array_field": ["item1", "item2"],
  "nested_object": {
    "inner_field": "value"
  }
}
```

**Common Workflow Data Pattern:**
```json
{
  "execution": {
    "id": "exec-12345",
    "workflow_name": "Proposal Generator",
    "timestamp": "2025-01-15T14:30:00Z",
    "duration_seconds": 12
  },
  "input": {
    "client_name": "Acme Corp",
    "project_type": "Digital Transformation"
  },
  "quality": {
    "overall_score": 4.2,
    "passed": true,
    "criteria_scores": {
      "clarity": 4,
      "completeness": 5,
      "style": 4
    }
  },
  "output": {
    "status": "success",
    "destination": "email"
  }
}
```

---

### Concept 5: Template Workflow Pattern

**Definition:**
Creating reusable workflow structures that can be cloned and adapted for different deliverable types while sharing common infrastructure.

**Why It Matters:**
Template patterns reduce duplication, ensure consistency, and make maintenance easier. Change one shared component, all variants benefit.

**The Pattern:**
```
Base Workflow Template:
Trigger → Data Prep → AI Generation → Quality Check → Output/Route

Variant 1: Proposal Generator
- Same structure
- Different prompt template
- Same quality/logging

Variant 2: Email Summarizer
- Same structure
- Different prompt template
- Same quality/logging
```

**Versioning Convention:**
- v1.0 - Initial release
- v1.1 - Minor changes (prompt tweaks, threshold adjustments)
- v2.0 - Major changes (structure changes, new features)

---

## Workshop Recap

### Session Summary

**Today's Focus:** Adding automated quality checks to workflows and building template patterns.

**Key Points from Each Segment:**

**Segment 1: Quality in Automated Workflows**
- Quality systems ARE operating procedures for AI
- Manual review doesn't scale
- Three layers: pre-generation, post-generation, human review
- Block 1 rubrics become automated evaluation criteria

**Segment 2: Automated Quality Checks**
- LLM-as-judge pattern: AI evaluates AI output
- Evaluation prompt based on your rubrics
- JSON output for reliable parsing
- Routing based on scores: pass/review/fail

**Segment 3: JSON Data Structures**
- JSON enables structured data between steps
- Standard execution data structure
- Request JSON output explicitly from AI
- Parse and validate in workflow

**Segment 4: Template Workflow Pattern**
- Clone workflow to create variants
- Replace prompt, keep infrastructure
- Version naming: v1.0, v1.1, v2.0
- Document as workflow family

### Demo Recap

**What Was Demonstrated:**
Adding a quality evaluation step to a workflow with routing based on scores.

**Key Steps:**
1. Added evaluation step after AI generation
2. Created evaluation prompt with criteria from rubric
3. Configured JSON parsing for scores
4. Set up routing logic based on score thresholds

**Result:**
Workflow that automatically evaluates output quality and routes accordingly.

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 3.1 | 25 min | Quality check module + evaluation prompt | LLM-as-judge implementation |
| 3.2 | 25 min | Second workflow + template family docs | Template pattern |
| 3.3 | 10 min | `workflow-data-schema.json` | JSON structure design |

---

### Exercise 3.1: Add Quality Check Module

**Duration:** 25 minutes

**Purpose:**
Implement automated quality assurance in your workflow using the LLM-as-judge pattern. This transforms your workflow from "hope it's good" to "verified quality."

**You Will Create:**
A quality evaluation step that scores output against criteria and routes based on scores.

---

#### Instructions

**Step 1: Create Quality Evaluation Prompt (10 min)**

Based on your Block 1 rubric, create an evaluation prompt:

```markdown
# Quality Evaluation Prompt

You are evaluating a [deliverable type] for quality.

## Criteria (score each 1-5)

### 1. [Criterion 1 from your rubric]
- 5 (Excellent): [Description of excellent]
- 3 (Adequate): [Description of adequate]
- 1 (Poor): [Description of poor]

### 2. [Criterion 2 from your rubric]
- 5 (Excellent): [Description]
- 3 (Adequate): [Description]
- 1 (Poor): [Description]

### 3. [Criterion 3 from your rubric]
- 5 (Excellent): [Description]
- 3 (Adequate): [Description]
- 1 (Poor): [Description]

[Add 2-4 more criteria as appropriate]

## Content to Evaluate

```
{{generated_content}}
```

## Output Format

Respond ONLY with valid JSON. No other text before or after.

```json
{
  "scores": {
    "criterion_1_name": {"score": X, "reason": "Brief explanation"},
    "criterion_2_name": {"score": X, "reason": "Brief explanation"},
    "criterion_3_name": {"score": X, "reason": "Brief explanation"}
  },
  "overall_score": X.X,
  "pass": true/false,
  "suggestions": ["Improvement 1", "Improvement 2"]
}
```

Pass threshold: overall_score >= 3.5
```

**Step 2: Add Evaluation Step to Workflow (8 min)**

In your automation platform:

1. Add a new AI module AFTER your generation step
2. Configure it to call Claude/OpenAI with your evaluation prompt
3. Insert the generated content from the previous step into `{{generated_content}}`
4. Use a faster/cheaper model if available (this is simpler than generation)

**Step 3: Add JSON Parsing (3 min)**

Parse the evaluation response:

**In Make:**
1. Add JSON Parse module after evaluation
2. Map the evaluation response to it
3. Access individual fields: `overall_score`, `pass`, etc.

**In n8n:**
1. Add JSON Parse node
2. Connect to evaluation output
3. Reference fields in subsequent nodes

**Step 4: Add Routing Logic (3 min)**

Create conditional routing based on score:

**In Make:**
1. Add Router module
2. Create routes:
   - Route 1: If `overall_score >= 4` → Output (high quality)
   - Route 2: If `overall_score >= 3.0 AND < 4` → Review queue
   - Route 3: If `overall_score < 3.0` → Fail/Retry

**In n8n:**
1. Add IF node
2. Configure conditions:
   - If score >= 4 → Success path
   - Else if score >= 3 → Review path
   - Else → Fail path

**Step 5: Test Quality Routing (1 min)**

Test with both good and intentionally poor inputs to verify routing works.

---

#### Deliverable Specification

**Deliverables:**
1. Evaluation prompt saved as `quality-evaluation-prompt.md`
2. Quality check module added to workflow
3. Routing logic configured
4. Documentation updated

**Quality Criteria:**
- [ ] Evaluation prompt includes 3-5 criteria from Block 1 rubric
- [ ] JSON output format is valid and parseable
- [ ] Routing logic correctly routes based on scores
- [ ] Both pass and fail paths tested

---

#### Template

```markdown
# Quality Evaluation Prompt: [Deliverable Type]

**Version:** 1.0
**Created:** [Date]
**Pass Threshold:** 3.5

## Criteria

### 1. [Criterion Name]
- **Weight:** [X%]
- 5 (Excellent): [Description]
- 3 (Adequate): [Description]
- 1 (Poor): [Description]

### 2. [Criterion Name]
- **Weight:** [X%]
- 5 (Excellent): [Description]
- 3 (Adequate): [Description]
- 1 (Poor): [Description]

### 3. [Criterion Name]
- **Weight:** [X%]
- 5 (Excellent): [Description]
- 3 (Adequate): [Description]
- 1 (Poor): [Description]

## Full Prompt

[Paste your complete evaluation prompt here]

## Routing Configuration

| Score Range | Action | Destination |
|-------------|--------|-------------|
| >= 4.0 | Output | [Destination] |
| 3.0 - 3.9 | Review | [Review queue] |
| < 3.0 | Fail | [Error handler] |

## Test Results

| Test | Input Type | Score | Correct Route? |
|------|------------|-------|----------------|
| 1 | Good input | | |
| 2 | Poor input | | |
| 3 | Edge case | | |
```

---

### Exercise 3.2: Build Second Workflow (Using Template)

**Duration:** 25 minutes

**Purpose:**
Create a reusable workflow pattern by cloning your first workflow and adapting it for a different deliverable type.

**You Will Create:**
A second workflow variant and documentation of your workflow "family."

---

#### Instructions

**Step 1: Clone Your First Workflow (3 min)**

**In Make:**
1. Open your first workflow
2. Click "Clone scenario"
3. Name it: "[Deliverable Type 2] Generator v1"

**In n8n:**
1. Open your first workflow
2. Click "Duplicate"
3. Rename appropriately

**Step 2: Identify What Changes (5 min)**

Document what needs to change:

| Component | Changes Needed? | What to Change |
|-----------|-----------------|----------------|
| Trigger | No/Yes | [If yes, what] |
| Data gathering | No/Yes | [If yes, what] |
| AI prompt | Yes | Swap to different Block 1 template |
| Quality criteria | Maybe | Adjust for new deliverable type |
| Output | Maybe | [If yes, what] |
| Logging | No | Keep as-is |
| Error handling | No | Keep as-is |

**Step 3: Swap Prompt Template (8 min)**

1. Select a different Block 1 template (different deliverable type)
2. Update the AI module prompt with new template
3. Adjust any input variable mappings if needed

**Step 4: Update Quality Criteria (5 min)**

1. Review your quality evaluation prompt
2. Adjust criteria for the new deliverable type if needed
3. Keep the same scoring structure and JSON format

**Step 5: Test New Workflow (3 min)**

1. Run 3+ test executions with appropriate sample data
2. Verify quality routing works
3. Check logs capture executions

**Step 6: Document as Workflow Family (1 min)**

Use the template below to document both workflows as related variants.

---

#### Deliverable Specification

**Deliverables:**
1. Second working workflow in platform
2. `workflow-template-family.md` documenting both workflows

**Quality Criteria:**
- [ ] Second workflow runs successfully
- [ ] Quality check integrated
- [ ] 3+ successful test executions
- [ ] Family documentation complete

---

#### Template

```markdown
# Workflow Template Family: [Family Name]

**Version:** 1.0
**Created:** [Date]

## Base Pattern

```
Trigger → Data Prep → AI Generation → Quality Check → Output/Route
              ↓                            ↓
           Logging                    Human Review (if needed)
```

## Workflow Variants

### Variant 1: [Original Workflow Name]

**Purpose:** [What it produces]
**Block 1 Template:** [Which template]
**Trigger:** [What starts it]
**Output Destination:** [Where results go]
**Unique Configuration:**
- [Specific detail 1]
- [Specific detail 2]

### Variant 2: [New Workflow Name]

**Purpose:** [What it produces]
**Block 1 Template:** [Which template]
**Trigger:** [What starts it]
**Output Destination:** [Where results go]
**Unique Configuration:**
- [Specific detail 1]
- [Specific detail 2]

## Shared Components

| Component | Description | Location |
|-----------|-------------|----------|
| Quality Evaluation | LLM-as-judge scoring | [Link] |
| Logging | Execution tracking | [Spreadsheet/Airtable link] |
| Error Handling | Fallback and alerts | [Description] |

## Versioning History

| Version | Date | Changes | Variant |
|---------|------|---------|---------|
| 1.0 | [Date] | Initial implementation | Both |
| | | | |

## Notes

[Any observations, planned improvements, or issues to address]
```

---

### Exercise 3.3: JSON Data Structure Design

**Duration:** 10 minutes

**Purpose:**
Design a standardized JSON schema for your workflow execution data to enable consistent logging and future analysis.

**You Will Create:**
A JSON schema document that defines the structure for your workflow data.

---

#### Instructions

**Step 1: Review Standard Structure (3 min)**

Review this standard workflow execution data structure:

```json
{
  "$schema": "workflow-execution-v1",

  "execution": {
    "id": "unique-execution-id",
    "workflow_name": "string",
    "workflow_version": "1.0",
    "timestamp": "ISO-8601 format",
    "duration_seconds": 0
  },

  "input": {
    "trigger_type": "manual|webhook|schedule",
    "source": "description of source",
    "data": {
      // Your workflow-specific input fields
    }
  },

  "processing": {
    "template_name": "string",
    "template_version": "string",
    "model": "claude-3.5-sonnet|gpt-4|etc",
    "tokens_used": 0,
    "cost_estimate": 0.00
  },

  "quality": {
    "evaluation_run": true,
    "overall_score": 0.0,
    "passed": true,
    "criteria_scores": {
      "criterion_1": 0,
      "criterion_2": 0
    }
  },

  "output": {
    "status": "success|failed|review_required",
    "destination": "email|slack|gdoc|etc",
    "deliverable_id": "optional reference id"
  },

  "errors": []
}
```

**Step 2: Customize for Your Workflows (5 min)**

Adapt the structure for your specific workflows:
- Add your workflow-specific input fields
- Add your quality criteria names
- Include any custom tracking fields you need

**Step 3: Document Your Schema (2 min)**

Save as `workflow-data-schema.json` with comments explaining fields.

---

#### Deliverable Specification

**File Name:** `workflow-data-schema.json`

**Location:** Your Block 2 folder in GitHub repository

**Quality Criteria:**
- [ ] All standard fields included
- [ ] Workflow-specific fields added
- [ ] Quality criteria match your evaluation prompt
- [ ] Comments explain purpose of fields

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| Quality Evaluation Prompt | Automated quality scoring | Exercise 3.1 |
| Workflow Family Documentation | Template pattern docs | Exercise 3.2 |
| Workflow Data Schema | JSON structure | Exercise 3.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| JSON Validator | Tool | [jsonlint.com](https://jsonlint.com) | Validate JSON syntax |
| Make JSON Parsing | Documentation | [make.com/en/help/tools/json](https://www.make.com/en/help/tools/json) | Platform-specific JSON |
| n8n Working with JSON | Documentation | [docs.n8n.io/data/data-structure](https://docs.n8n.io/data/data-structure/) | Platform-specific JSON |
| JSON Schema Reference | Documentation | [json-schema.org](https://json-schema.org/) | Advanced schema design |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Implement LLM-as-judge quality checks | Quality evaluation module working | ☐ |
| 2 | Configure quality-based routing | Pass/fail/review paths tested | ☐ |
| 3 | Build workflow variants from templates | Second workflow running | ☐ |
| 4 | Design JSON data structures | Schema document created | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Quality evaluation prompt | `quality-evaluation-prompt.md` | GitHub | ☐ |
| Quality module in workflow | N/A | Platform | ☐ |
| Second workflow | N/A | Platform | ☐ |
| Template family docs | `workflow-template-family.md` | GitHub | ☐ |
| JSON schema | `workflow-data-schema.json` | GitHub | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** How does using AI to evaluate AI change your thinking about quality?

2. **What's still fuzzy?** Where do you need more practice with JSON or routing?

3. **How accurate is your quality check?** Does it pass/fail outputs the way you would manually?

4. **What threshold feels right?** Based on your test results, should you adjust your pass threshold?

---

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Tag cohort members for JSON/routing tips

### Common Questions This Week

**Q: My JSON parsing keeps failing. What should I check?**
A: Common issues: AI includes text before/after JSON, invalid syntax, different key names. Add explicit instruction "Respond with ONLY valid JSON." Use [jsonlint.com](https://jsonlint.com) to validate. Add error handling for parse failures.

**Q: My quality threshold seems too strict/lenient. How do I adjust?**
A: Calibrate using 10-20 executions. If good outputs fail, lower threshold. If bad outputs pass, raise it. Document your calibration in your evaluation prompt file.

**Q: Can I use a different model for quality checks?**
A: Yes! Quality evaluation is often simpler than generation. A smaller/cheaper model (GPT-4o-mini, Claude Haiku) works well and reduces costs.

---

## Looking Ahead

### Next Week Preview: Week 4 - Workflow Optimization

**Focus:**
Analyzing performance data and optimizing workflows for cost, speed, and quality.

**How It Builds on This Week:**
You'll use your logged execution data and quality scores to identify optimization opportunities.

**To Prepare:**
- [ ] Complete all Week 3 exercises
- [ ] Have 10+ logged executions across both workflows
- [ ] Note which steps take longest
- [ ] Review your quality score distribution

---

## Glossary

| Term | Definition |
|------|------------|
| LLM-as-Judge | Pattern where AI evaluates another AI's output against criteria |
| Quality Gate | Checkpoint that validates inputs or outputs before proceeding |
| Routing | Directing workflow execution down different paths based on conditions |
| JSON | JavaScript Object Notation - structured data format |
| Schema | Definition of data structure including field names and types |
| Template Pattern | Reusable workflow structure adapted for different use cases |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [← Week 2](../week-2/participant-guide.md) | **Week 3** | [Week 4 →](../week-4/participant-guide.md)
