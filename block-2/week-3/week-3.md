# Week 3: Quality Systems + Template Workflows

**Block:** 2 - AI Workflow Engineering
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] First workflow built and tested
- [ ] Error handling implemented
- [ ] Logging active
- [ ] 5+ successful workflow executions

## Exit Criteria

- [ ] Quality check module integrated into workflow
- [ ] JSON data structures used for workflow data
- [ ] Second workflow built using template pattern
- [ ] Rubric-based quality gate implemented
- [ ] Template versioning strategy established

---

## Workshop Content (45 minutes)

### Segment 1: Quality in Automated Workflows (12 min)

**Framing: Quality as Domain Memory**

**The Three Pillars (preview of Block 3):**
1. **Explicit Goals** → Your success criteria
2. **Progress Records** → Your execution logs
3. **Operating Procedures** → Your quality system!

**Quality systems ARE operating procedures:**
- Pre-generation checks = input validation procedures
- Post-generation evaluation = output verification procedures
- Human review triggers = escalation procedures

**Why this matters:**
- Consistent behavior across all executions
- Predictable quality without human variance
- Foundation for autonomous agents (Block 3)

**The automation quality challenge:**
- Manual review doesn't scale
- Inconsistent quality undermines trust
- Need systematic quality assurance

**Block 1 foundations applied:**
- Quality rubrics become automated checks
- Comparison gates verify style matching
- LLM-as-judge pattern for self-evaluation

**Quality gate implementation:**
- Pre-generation: Input validation
- Post-generation: Output evaluation
- Human review: When automated checks fail

### Segment 2: Automated Quality Checks (10 min)

**Using AI to check AI:**

```
Step 1: Generate deliverable
Step 2: Run evaluation prompt
Step 3: Parse scores
Step 4: Route based on scores
```

**Evaluation prompt pattern:**

```markdown
Evaluate this [deliverable] against these criteria.
For each criterion, score 1-5 and provide a brief justification.

Criteria:
1. [From your rubric]
2. [From your rubric]
3. [From your rubric]

Output your evaluation as JSON:
{
  "scores": {
    "criterion_1": {"score": X, "reason": "..."},
    "criterion_2": {"score": X, "reason": "..."}
  },
  "overall_score": X,
  "pass": true/false,
  "improvement_suggestions": ["...", "..."]
}
```

**Routing logic:**
- Score ≥ 4: Proceed to output
- Score 3: Flag for human review
- Score < 3: Regenerate with improvements

### Segment 3: JSON Data Structures in Workflows (13 min)

**Why JSON for workflows:**
- Structured data between steps
- Easy parsing and manipulation
- Standard format across platforms
- AI generates JSON reliably

**Common workflow data patterns:**

```json
{
  "workflow_id": "wf-001",
  "execution_timestamp": "2024-12-30T10:30:00Z",
  "input": {
    "client_name": "Acme Corp",
    "project_type": "proposal"
  },
  "processing": {
    "template_used": "proposal-tech-v2",
    "ai_model": "claude-3-opus",
    "tokens_used": 2500
  },
  "output": {
    "status": "success",
    "quality_score": 4.2,
    "deliverable_url": "..."
  }
}
```

**JSON in AI prompts:**
- Request JSON output explicitly
- Provide schema/example
- Parse and validate in workflow

### Segment 4: Template Workflow Pattern (10 min)

**The reusable workflow template:**
- Generic structure
- Variables for customization
- Swap components (different prompts, outputs)

**Template versioning:**
- v1.0, v1.1, v2.0 naming
- Changelog documentation
- A/B testing workflows

**Building your second workflow:**
- Clone workflow 1
- Replace prompt template
- Adjust data mappings
- Same quality/logging infrastructure

---

## Self-Paced Exercises (60 minutes total)

### Exercise 3.1: Add Quality Check Module (25 minutes)

*Implement automated quality assurance*

1. Create quality evaluation prompt based on your Block 1 rubric:

```markdown
# Quality Evaluation Prompt

You are evaluating a [deliverable type] for quality.

## Criteria (score each 1-5)

1. **[Criterion 1 from rubric]**
   - 5: [Excellent description]
   - 3: [Adequate description]
   - 1: [Poor/Missing description]

2. **[Criterion 2]**
   - 5: [Description]
   - 3: [Description]
   - 1: [Description]

[Repeat for 3-5 criteria]

## Content to Evaluate

\`\`\`
{deliverable_content}
\`\`\`

## Output Format

Respond ONLY with valid JSON:
\`\`\`json
{
  "scores": {
    "criterion_1_name": {"score": X, "reason": "brief explanation"},
    "criterion_2_name": {"score": X, "reason": "brief explanation"}
  },
  "overall_score": X.X,
  "pass": true/false,
  "suggestions": ["improvement 1", "improvement 2"]
}
\`\`\`

Pass threshold: overall_score >= 3.5
```

2. Add evaluation step to your workflow:
   - After AI generation, before output
   - Parse JSON response
   - Create routing based on pass/fail

3. Add routing logic:
   - Pass → Continue to output
   - Fail → Log failure, send for review OR regenerate

4. Test with good and bad inputs to verify routing works

**Deliverable:** Quality check module added to workflow + evaluation prompt saved

---

### Exercise 3.2: Build Second Workflow (Using Template) (25 minutes)

*Create reusable workflow pattern*

1. Clone your first workflow in the platform

2. Identify what changes for different use case:
   - Different trigger? → Update trigger
   - Different prompt? → Swap prompt template
   - Different output? → Adjust output step
   - Same quality/logging? → Keep as-is

3. Modify for new deliverable type:
   - Use second Block 1 template
   - Adjust data mappings
   - Update quality criteria in evaluation prompt

4. Test with 3+ executions

5. Document both workflows as a "family":

```markdown
# Workflow Template Family: [Name]

## Base Pattern
- Trigger → Data Prep → AI Generation → Quality Check → Output/Route

## Workflow Variants

### Variant 1: [Original Workflow Name]
- **Deliverable:** [What it produces]
- **Template:** [Which Block 1 template]
- **Unique config:** [What's specific to this one]

### Variant 2: [New Workflow Name]
- **Deliverable:** [What it produces]
- **Template:** [Which Block 1 template]
- **Unique config:** [What's specific to this one]

## Shared Components
- Quality evaluation prompt: [Link]
- Logging destination: [Link]
- Error handling pattern: [Description]

## Versioning
- v1.0: Initial implementation
- [Date]: [Changes]
```

**Deliverable:** Second workflow + template family documentation

---

### Exercise 3.3: JSON Data Structure Design (10 minutes)

*Standardize workflow data*

1. Design standard data structure for your workflows:

```json
{
  "$schema": "workflow-execution-v1",

  "execution": {
    "id": "unique-execution-id",
    "workflow_name": "string",
    "workflow_version": "1.0",
    "timestamp": "ISO-8601",
    "duration_seconds": 0
  },

  "input": {
    "trigger_type": "manual|webhook|schedule",
    "source": "string",
    "data": {
      // workflow-specific input fields
    }
  },

  "processing": {
    "template_name": "string",
    "template_version": "string",
    "model": "string",
    "tokens_used": 0,
    "cost_estimate": 0.00
  },

  "quality": {
    "evaluation_run": true,
    "overall_score": 0.0,
    "passed": true,
    "criteria_scores": {}
  },

  "output": {
    "status": "success|failed|review_required",
    "destination": "string",
    "deliverable_id": "string"
  },

  "errors": []
}
```

2. Update your logging to use this structure

3. Validate JSON output from your workflows

**Deliverable:** `workflow-data-schema.json`

---

## Key Takeaways

1. **Quality gates automate evaluation** - LLM-as-judge at scale
2. **JSON structures workflow data** - Consistent, parseable, standard
3. **Template workflows enable reuse** - Build once, customize many times
4. **Routing based on quality** - Automatic pass/fail/review decisions
5. **Quality systems ARE operating procedures** - Foundation for Block 3 agents

---

## Preparation for Week 4

- Run both workflows 5+ times each
- Review quality check results - are thresholds right?
- Log all executions with full JSON data
- Next week: Workflow optimization

---

## Resources

- [JSON Schema Reference](https://json-schema.org/)
- [Make JSON Parsing](https://www.make.com/en/help/tools/json)
- [n8n Working with JSON](https://docs.n8n.io/data/data-structure/)
