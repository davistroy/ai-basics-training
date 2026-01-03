# **POWERPOINT PRESENTATION: MODULE 3 SESSION 2**
## **Validation in Practice**

**Module:** Advanced Module 3: JSON Schema & Data Validation
**Session Number:** 2 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 2+ graduates who completed Session 1 and have created a schema library

**Key Thesis:** Runtime validation transforms JSON Schema from static documentation into active quality control—catching AI output errors at generation time, enabling intelligent retry strategies, and generating developer-friendly error messages that prevent malformed data from propagating through workflows while maintaining comprehensive documentation through schema-driven generation.

**Session Learning Objectives:** By the end of this session, participants will:
1. Implement runtime validation at key workflow points
2. Validate AI outputs with retry and recovery strategies
3. Create actionable error messages from validation failures
4. Generate documentation from schemas for team reference

**Entry Criteria:** (What participants should have before this session)
- [ ] 5+ schemas created in Session 1
- [ ] Schema library organized
- [ ] Understanding of schema syntax
- [ ] Validation tools identified

**Exit Criteria:** (What participants should be able to do after this session)
- [ ] Runtime validation implemented in workflows
- [ ] AI output validation working
- [ ] Error handling for validation failures
- [ ] Schema documentation generated
- [ ] Module capstone completed

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Validation in Workflows (12 min) - Slides 4-7
3. Segment 2: Validating AI Outputs (12 min) - Slides 8-11
4. Segment 3: Error Messages and Debugging (12 min) - Slides 12-15
5. Segment 4: Schema Documentation (9 min) - Slides 16-18
6. Homework Preview & Close (3 min) - Slides 19-21

**Total Slides:** 21

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Module 3 Session 2: Validation in Practice

**Subtitle:** Implementing Robust Validation in Production Workflows

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program
- Advanced Module 3

**Graphic:** Clean title slide with program branding. Orange tones (Block 2-level, building/engineering theme)

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Session 2 of Advanced Module 3: JSON Schema and Data Validation. Today we're taking the schemas you created last session and putting them into production.

Last session you learned JSON Schema syntax - how to write schemas for your data. Who can share one schema they created?

[Wait for 1-2 responses]

Great. Today we're going beyond syntax. We're implementing actual validation in real workflows. You'll learn where to validate, how to handle AI outputs that don't match your schema, how to create useful error messages, and how to build a complete validated workflow system.

By the end of our 45 minutes together, you'll have a roadmap for implementing validation across all your workflow touch points."

[Transition: Click to next slide]

---

### SLIDE 2: SESSION OVERVIEW

**Title:** This Session's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Recap & Preview |
| 3-15 min | Segment 1 | Validation in Workflows |
| 15-27 min | Segment 2 | Validating AI Outputs |
| 27-39 min | Segment 3 | Error Messages & Debugging |
| 39-48 min | Segment 4 | Schema Documentation |
| 48-51 min | Close | Capstone & Resources |

**Graphic:** Simple timeline or agenda visual showing the session flow

**SPEAKER NOTES:**

"Here's what we'll cover today:

First, we'll identify where to validate in your workflows - input validation, AI output validation, and inter-step validation.

Then, we'll tackle the AI output challenge - how to handle the fact that AI is non-deterministic and doesn't always follow your schema perfectly. You'll learn retry strategies and recovery patterns.

In our third segment, we'll look at error handling - turning validation failures into actionable error messages that help you fix issues quickly.

And we'll close with schema documentation - using your schemas as living documentation for your team.

[Pause]

Any questions before we dive in?"

[Transition]

---

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Implement runtime validation at key workflow points**
   - Know where to validate and how to integrate validation steps

2. **Validate AI outputs with retry and recovery strategies**
   - Handle non-deterministic AI responses gracefully

3. **Create actionable error messages from validation failures**
   - Turn schema errors into useful debugging information

4. **Generate documentation from schemas for team reference**
   - Make schemas serve double duty as code and documentation

**Graphic:** Checklist or milestone visual - objectives as checkboxes participants will "complete"

**SPEAKER NOTES:**

"These are our four objectives for today. By the time you leave this session, you'll be able to:

[Read each objective, pausing briefly after each]

Notice that today is all about implementation. Last session was syntax. This session is applying that syntax in production workflows.

[Point to second objective]

This one is particularly important because AI outputs are the trickiest validation point. We'll spend significant time on handling validation failures gracefully.

Let's get started with where to validate."

[Transition: Click to Segment 1]

---

## SEGMENT 1: VALIDATION IN WORKFLOWS
### Duration: 12 minutes | Slides 4-7

---

### SLIDE 4: SEGMENT 1 - VALIDATION POINTS

**Title:** Where to Validate in Your Workflow

**Content:**

**Four Critical Validation Points:**

1. **Input Validation** - Before processing starts
   - Workflow triggers (forms, APIs, webhooks)
   - Catch bad data immediately

2. **AI Output Validation** - After generation
   - Validate format before using output
   - Most critical for reliability

3. **Inter-Step Validation** - Between workflow steps
   - Ensure data contracts between components
   - Prevent cascading failures

4. **Final Validation** - Before delivery
   - Last quality gate
   - Ensure complete, correct deliverable

**Graphic:** Flow diagram showing validation gates in a workflow pipeline

**GRAPHICS:**

**Graphic 1: Four Validation Gates**
- Purpose: Show the four critical validation points in a workflow
- Type: Workflow diagram with numbered validation gates
- Elements: Linear workflow with four validation checkpoints highlighted
- Labels:
  - Gate 1: "Input Validation" (Form → Validate → Process)
  - Gate 2: "AI Output Validation" (AI Generate → Validate → Use)
  - Gate 3: "Inter-Step Validation" (Step 1 → Validate → Step 2)
  - Gate 4: "Final Validation" (Result → Validate → Deliver)
- Relationships: Each gate has error path branching to error handler
- Visual Style: Validation gates shown as shield icons in green; error paths in red

**SPEAKER NOTES:**

"[Hook - Multiple validation points]"

"Let me show you the four places where you should validate data in every workflow.

First, input validation. When your workflow is triggered - whether by a form submission, API call, or webhook - validate that data immediately. Don't start processing until you know the input is valid.

Second, AI output validation. After the AI generates a response, validate it against your schema before you use it. This is your most important validation point because AI is non-deterministic.

Third, inter-step validation. If your workflow has multiple steps passing data between them, validate at each handoff. This prevents one step's bad output from cascading through the rest of your workflow.

Fourth, final validation. Before you deliver output to a client or user, validate one last time. This is your final quality gate.

[Point to graphic]

Notice the pattern: validate early, validate often. Each validation gate catches errors before they propagate further.

Let me show you what this looks like in practice..."

[Transition]

**BACKGROUND:**

**Rationale:**
- Multiple validation points create defense in depth
- Earlier validation = easier debugging
- Each point serves a specific purpose

**Q&A Preparation:**
- *"Isn't this validation overkill?"*: Each point serves a purpose. You can start with input + AI output and add others as needed.
- *"What if validation slows down my workflow?"*: Validation is fast (milliseconds). The time saved debugging failures far exceeds validation overhead.

---

### SLIDE 5: SEGMENT 1 - VALIDATION PATTERN

**Title:** The Validation Pattern

**Content:**

**Standard Validation Flow:**

```
[Data Source]
     ↓
[Parse JSON]
     ↓
[Validate Against Schema]
     ↓
  ┌──┴──┐
  ✓     ✗
  │     │
[Continue] [Error Handler]
  │          ↓
  │     [Log Error]
  │          ↓
  │     [Format Message]
  │          ↓
  │     [Return/Retry/Escalate]
```

**Key Steps:**
1. Parse data (catch JSON syntax errors)
2. Validate against schema
3. Branch on validation result
4. Handle errors gracefully

**Graphic:** Flowchart showing the pattern with decision points

**GRAPHICS:**

**Graphic 1: Standard Validation Flow Pattern**
- Purpose: Show the universal pattern for validation at any point
- Type: Detailed flowchart with branching logic
- Elements: Sequential steps with decision diamond
- Labels:
  - Step 1: "Data Source"
  - Step 2: "Parse JSON" (with TRY/CATCH indicator)
  - Step 3: "Validate Against Schema" (diamond decision)
  - Branch A (✓): "Continue Workflow"
  - Branch B (✗): "Error Handler" → "Log Error" → "Format Message" → "Return/Retry/Escalate"
- Relationships: Show both success and failure paths clearly
- Visual Style: Green path for success, red path for errors; use flowchart standard shapes

**SPEAKER NOTES:**

"[INSIGHT - Standard pattern]"

"Here's the standard pattern you'll use at every validation point:

First, parse the JSON. This catches basic syntax errors - missing commas, malformed structure. If parsing fails, the data isn't even valid JSON.

Second, validate the parsed data against your schema. This checks types, constraints, required fields.

Third, branch based on the result. If validation passes, continue the workflow. If it fails, route to your error handler.

Fourth, in your error handler, log the error with details, format a useful message, and decide whether to return an error, retry, or escalate to a human.

[Point to flowchart]

This pattern is the same whether you're validating input, AI output, or inter-step data. The only difference is what you do when validation fails.

Let's look at platform-specific implementation..."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide establishes the universal validation pattern that works across all platforms and validation points
- Creates the mental model that validation is a structured decision process, not ad-hoc error checking
- Provides the template participants will apply repeatedly throughout their workflows

**Key Research & Citations:**
- **Defensive Programming Principles**: Parse-validate-branch pattern is a fundamental defensive programming technique that prevents cascading failures
- **Error Handling Best Practices**: Explicit error handling paths reduce production incidents by 40-60% compared to implicit try-catch blocks

**Q&A Preparation:**
- *"Can I skip the parse step if I trust the data source?"*: Never skip parsing - even trusted sources can have transient network errors, encoding issues, or upstream bugs that produce malformed JSON
- *"Should I validate before or after parsing?"*: Always parse first - you can't validate structure of malformed JSON. Parsing validates syntax, schema validates semantics
- *"What if my platform doesn't support branching?"*: All automation platforms support conditional logic - Make.com has Filters/Routers, n8n has IF nodes, code has if-statements

---

### SLIDE 6: SEGMENT 1 - PLATFORM IMPLEMENTATION

**Title:** Implementing Validation by Platform

**Content:**

**Make.com:**
- JSON module with schema validation
- Filter module for branching
- Error handler route

**n8n:**
- Function node with ajv library
- IF node for branching
- Error workflow

**Custom Code (JavaScript):**
```javascript
const Ajv = require('ajv');
const ajv = new Ajv();

const schema = { /* your schema */ };
const validate = ajv.compile(schema);

const data = JSON.parse(input);
const valid = validate(data);

if (!valid) {
  throw new Error(JSON.stringify(validate.errors));
}
```

**Python:**
```python
import jsonschema

jsonschema.validate(data, schema)
# Raises ValidationError if invalid
```

**Graphic:** Platform logos with code snippets

**SPEAKER NOTES:**

"Let me show you how to implement validation on different platforms.

In Make.com, use the JSON module which has built-in schema validation. Follow it with a Filter module to branch on the result, and set up an error handler route.

In n8n, use a Function node with the ajv library to validate. Follow it with an IF node to branch, and create an error workflow for failures.

If you're writing custom code in JavaScript, use the ajv library. It's the fastest and most popular JSON Schema validator. Compile your schema once, then use it to validate data.

In Python, use the jsonschema library. It's the reference implementation and very straightforward.

[Pause]

The key is: whichever platform you're using, the pattern is the same. Parse, validate, branch, handle errors.

In Exercise 2.1, you'll implement validation in your actual workflow using whichever platform you use."

[Transition]

---

### SLIDE 7: SEGMENT 1 - KEY TAKEAWAY

**Title:** Segment 1 Summary

**Content:**

**Key Takeaway:** Validate at four points - input, AI output, inter-step, and final - using the same pattern everywhere

**Remember:**
- Each validation point serves a specific purpose
- Use the same pattern: parse, validate, branch, handle
- Platform doesn't matter - pattern is universal
- Error handlers are not optional

**You'll Practice:**
Exercise 2.1 - Add validation to your workflow at input and AI output points

**Graphic:** Simple diagram showing validation gates in sequence

**SPEAKER NOTES:**

"Before we move on, let me summarize validation points:

Validate at four places in your workflow: input, AI output, inter-step, and final. Each catches errors at a different stage.

Use the same pattern everywhere: parse JSON, validate against schema, branch on result, handle errors gracefully.

The platform you use doesn't matter - Make, n8n, custom code - the pattern is the same.

And error handlers are not optional. Every validation point needs an error handler. We'll cover error handling in detail in Segment 3.

[Pause]

Now let's tackle the trickiest validation point: AI outputs."

[Transition: Click to Segment 2]

---

## SEGMENT 2: VALIDATING AI OUTPUTS
### Duration: 12 minutes | Slides 8-11

---

### SLIDE 8: SEGMENT 2 - THE AI CHALLENGE

**Title:** Why AI Output Validation is Different

**Content:**

**The Challenge:**
- AI outputs are non-deterministic
- Perfect prompts still get 1-5% variation
- May add/omit fields unexpectedly
- May return wrong types or formats

**Why This Matters:**
- Can't assume AI follows instructions
- Need graceful degradation
- Must handle failures automatically
- Can't manually fix every instance

**Real Example:**
```
Prompt: "Return JSON with 'score' (number 0-5) and 'reason' (string)"

AI might return:
{ "score": "4", "reason": "Good work" }  // score is string, not number
{ "rating": 4, "reason": "Good work" }   // wrong field name
{ "score": 4 }                           // missing reason
```

**Graphic:** Examples of AI output variations

**GRAPHICS:**

**Graphic 1: AI Output Format Variations**
- Purpose: Show real examples of how AI output can deviate from schema
- Type: Comparison table with validation results
- Elements: Three columns showing prompt request, expected schema, and actual AI outputs
- Labels:
  - Column 1: "Requested Format" → {score: number, reason: string}
  - Column 2-4: "Actual AI Outputs" with validation results
    - Output 1: {score: "4", reason: "Good"} → ✗ "score is string, not number"
    - Output 2: {rating: 4, reason: "Good"} → ✗ "wrong field name (rating vs score)"
    - Output 3: {score: 4} → ✗ "missing required field (reason)"
    - Output 4: {score: 4, reason: "Good"} → ✓ "Valid!"
- Relationships: Shows that even with clear prompts, AI can vary output structure
- Visual Style: Red X for invalid, green checkmark for valid

**SPEAKER NOTES:**

"[Hook - AI is unpredictable]"

"Let me ask: who has seen AI return data in a format different from what you asked for?

[Show of hands - should see many]

This is the core challenge with AI output validation. AI is non-deterministic. Even with perfect prompts, you'll see format variations 1-5% of the time.

[Point to examples]

You ask for a field called 'score' as a number. AI might give you a string instead. Or use 'rating' instead of 'score'. Or omit a required field entirely.

The problem is scale. If you're running 100 workflow executions per day, that's 1-5 failures daily. You can't manually fix each one.

You need automatic validation and recovery. Let me show you how..."

[Transition]

**BACKGROUND:**

**Rationale:**
- Sets up why AI validation needs special handling
- Creates urgency for robust validation
- Prepares for retry strategies in next slides

---

### SLIDE 9: SEGMENT 2 - VALIDATION PROMPT PATTERN

**Title:** Including Schema in AI Prompts

**Content:**

**The Pattern: Schema in Prompt**

```markdown
Generate your response as JSON matching this exact schema:

```json
{
  "analysis": { "type": "string", "minLength": 10 },
  "confidence": { "type": "number", "minimum": 0, "maximum": 1 },
  "recommendations": {
    "type": "array",
    "items": { "type": "string" },
    "minItems": 1
  }
}
```

Respond with ONLY valid JSON matching this schema.
Do not include any text before or after the JSON.
```

**Why This Works:**
- Shows AI the exact structure
- Specifies types and constraints
- Reduces (but doesn't eliminate) format errors

**Critical:** Still validate after generation!

**Graphic:** Prompt template with schema embedded

**SPEAKER NOTES:**

"The first strategy is prevention: include your schema in the AI prompt.

[Point to example]

Show the AI exactly what structure you expect. Include the schema right in the prompt, and explicitly tell the AI to respond with only valid JSON.

This reduces format errors significantly. Instead of hoping the AI understands 'return JSON with analysis, confidence, and recommendations', you show the exact structure.

[Emphasize]

But - and this is critical - you still must validate after generation. Including the schema helps, but doesn't guarantee compliance. AI is still probabilistic.

Think of it like this: the schema in the prompt is your first defense. Validation after generation is your backup.

Now let's look at what to do when validation fails..."

[Transition]

---

### SLIDE 10: SEGMENT 2 - POST-GENERATION VALIDATION

**Title:** Validate and Recover

**Content:**

**Validation Flow:**

```
response = ai_generate(prompt)

TRY:
  parsed = JSON.parse(response)
  validation = validate(parsed, schema)

  IF valid:
    return parsed
  ELSE:
    // JSON valid but wrong structure
    handle_schema_error(validation.errors)

CATCH ParseError:
  // Response wasn't even valid JSON
  handle_parse_error(response)
```

**Recovery Strategies:**

1. **Retry with stricter prompt** (max 2-3 times)
2. **Auto-fix minor issues** (coerce types, use defaults)
3. **Use partial data** (if some fields valid)
4. **Escalate to human** (when automatic recovery fails)

**Graphic:** Decision tree for handling validation failures

**GRAPHICS:**

**Graphic 1: Post-Generation Validation Flow**
- Purpose: Show the complete validation and recovery process
- Type: Detailed flowchart with error handling branches
- Elements: Multi-step process with decision points
- Labels:
  - Start: "AI Generate Response"
  - Step 1: "Parse JSON" → ParseError? → "Handle Parse Error (retry with stricter prompt)"
  - Step 2: "Validate Schema" → Valid? → "Use Data"
  - If Invalid: "Handle Schema Error" → Decision tree:
    - Option 1: "Auto-Fix Minor Issues" (coerce types, defaults)
    - Option 2: "Retry with Stricter Prompt" (max 2-3)
    - Option 3: "Use Partial Data" (if some fields valid)
    - Option 4: "Escalate to Human"
- Relationships: Show decision logic for each recovery strategy
- Visual Style: Color-code strategies (green=auto-fix, yellow=retry, orange=partial, red=escalate)

**SPEAKER NOTES:**

"Here's what post-generation validation looks like:

First, try to parse the response as JSON. If this fails, the AI didn't even return valid JSON - you'll need to retry with an even more explicit prompt.

If parsing succeeds, validate against your schema. If validation passes, great - use the data. If it fails, you have options.

[Point to recovery strategies]

Option 1: Retry with a stricter prompt. Add emphasis like 'IMPORTANT: Respond with ONLY valid JSON'. Limit to 2-3 retries.

Option 2: Auto-fix minor issues. If the AI returned '4' as a string but you need a number, coerce it. If an optional field is missing, use a default value.

Option 3: Use partial data. If some fields are valid, use those and flag the invalid parts for review.

Option 4: Escalate to human. When automatic recovery fails, queue for human review with all the context.

[Pause]

The key is graceful degradation. Don't just fail silently or crash. Have a strategy for each failure type."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide provides the critical playbook for handling AI non-determinism in production workflows
- Shifts mindset from "AI should always work" to "AI failures are expected, plan for graceful recovery"
- Establishes the multi-tiered recovery strategy that prevents workflow abandonment while maintaining quality

**Key Research & Citations:**
- **LLM Output Reliability Research**: Even with schema-in-prompt, GPT-4 class models show 1-5% format non-compliance depending on complexity
- **Retry Strategy Analysis**: Exponential backoff with maximum retry limits prevents infinite loops while recovering 85-95% of transient failures
- **Type Coercion Trade-offs**: Automatic coercion recovers 60-70% of format errors but requires careful logging to detect systematic prompt issues

**Q&A Preparation:**
- *"How do I know when to auto-fix vs. retry vs. escalate?"*: Auto-fix for simple type mismatches (string→number), retry for structure issues (missing fields), escalate after max retries or for semantic errors (wrong values)
- *"Won't retrying the same prompt just fail again?"*: Add randomness or stricter instructions in retry prompts. For persistent failures, the issue is usually prompt clarity, not AI randomness
- *"Is partial data safe to use?"*: Only if you can clearly identify which parts are valid and mark missing/invalid parts for review. Never silently use partial data in production outputs

---

### SLIDE 11: SEGMENT 2 - KEY TAKEAWAY

**Title:** Segment 2 Summary

**Content:**

**Key Takeaway:** Include schema in prompts to reduce errors, but always validate and have recovery strategies

**Remember:**
- AI is non-deterministic - validation is mandatory
- Include schema in prompt as prevention
- Validate after generation as backup
- Have 3-4 recovery strategies ready
- Limit retries (2-3 max)

**You'll Practice:**
Exercise 2.1 - Add AI output validation with retry logic to your workflow

**Graphic:** Prevention + Validation + Recovery = Robust AI integration

**SPEAKER NOTES:**

"Let me summarize AI output validation:

First, prevention: include your schema in the AI prompt. Show the AI exactly what you expect.

Second, validation: always validate the response, even with schema in prompt.

Third, recovery: have multiple strategies ready. Retry with stricter prompt, auto-fix minor issues, use partial data, or escalate to human.

Fourth, limit retries. Don't get stuck in infinite loops. 2-3 retries max, then escalate.

In Exercise 2.1, you'll implement this full pattern in your workflow.

[Pause]

Questions on AI output validation before we move to error handling?"

[Transition: Click to Segment 3]

---

## SEGMENT 3: ERROR MESSAGES AND DEBUGGING
### Duration: 12 minutes | Slides 12-15

---

### SLIDE 12: SEGMENT 3 - ERROR INFORMATION

**Title:** What Makes a Good Validation Error?

**Content:**

**Raw Schema Error (Not Helpful):**
```json
{
  "valid": false,
  "errors": [{"keyword": "required", "dataPath": "/client"}]
}
```

**Useful Error (Helpful):**
```json
{
  "valid": false,
  "errors": [
    {
      "path": "/client/name",
      "message": "Required property missing",
      "keyword": "required",
      "expected": "string",
      "received": undefined
    },
    {
      "path": "/priority",
      "message": "Value must be one of: low, normal, high",
      "keyword": "enum",
      "allowedValues": ["low", "normal", "high"],
      "actualValue": "urgent"
    }
  ]
}
```

**Key Elements:**
- Full path to error
- Clear message
- Expected vs actual values
- Actionable information

**Graphic:** Side-by-side comparison of raw vs formatted errors

**GRAPHICS:**

**Graphic 1: Raw vs Useful Error Messages**
- Purpose: Contrast machine-readable errors with human-readable ones
- Type: Side-by-side comparison with before/after
- Elements: Two error message formats
- Labels:
  - LEFT (Raw): `{"valid": false, "errors": [{"keyword": "required", "dataPath": "/client"}]}`
    - Annotation: "Cryptic", "Hard to debug", "Machine-focused"
  - RIGHT (Useful):
    ```
    Field: client.name
    Problem: Required property missing
    Expected: string
    Received: undefined
    ```
    - Annotation: "Clear", "Actionable", "Human-focused"
- Relationships: Show transformation from raw to useful
- Visual Style: Raw in gray/technical font, useful in clear readable format with highlighting

**SPEAKER NOTES:**

"[INSIGHT - Error quality matters]"

"Not all validation errors are created equal. Let me show you the difference between useless and useful errors.

[Point to raw error]

This is what many validators give you by default. It says validation failed, there's a required field missing at /client, keyword 'required'. What does that mean? Which field? What should it be?

[Point to useful error]

Now look at this. It tells you exactly what's wrong: client.name is missing and it should be a string. Priority has value 'urgent' but allowed values are low, normal, high.

This is actionable. You can immediately fix the issue or update your prompt to prevent it.

The difference is formatting. Raw validator output needs to be transformed into useful error messages.

Let me show you how to format errors for humans..."

[Transition]

---

### SLIDE 13: SEGMENT 3 - HUMAN-READABLE ERRORS

**Title:** Formatting Errors for Humans

**Content:**

**Machine Format:**
```json
{"path": "/client/name", "keyword": "required"}
{"path": "/score", "keyword": "minimum", "limit": 0, "value": -5}
```

**Human Format:**
```
Validation failed with 2 errors:

1. client.name: Required field is missing
   Expected: string
   Received: undefined

2. score: Value below minimum
   Expected: >= 0
   Received: -5
```

**Format Function:**
```javascript
function formatErrors(schemaErrors) {
  return schemaErrors.map((error, index) => {
    return `${index+1}. ${error.path}: ${error.message}
   Expected: ${error.expected}
   Received: ${error.received}`;
  }).join('\n\n');
}
```

**Graphic:** Transformation from machine format to human format

**GRAPHICS:**

**Graphic 1: Error Formatting Transformation**
- Purpose: Show the process of transforming error data
- Type: Data transformation pipeline
- Elements: Three-stage transformation
- Labels:
  - Stage 1 (Input): Raw validator errors → `[{path: "/score", keyword: "minimum", limit: 0, value: -5}]`
  - Stage 2 (Transform): Format function → "Extract path, create message, show expected vs received"
  - Stage 3 (Output): Human-readable →
    ```
    1. score: Value below minimum
       Expected: >= 0
       Received: -5
    ```
- Relationships: Show data flowing through transformation stages
- Visual Style: Use pipeline/arrow visual to show progression

**SPEAKER NOTES:**

"You need to transform machine-format errors into human-readable messages.

[Point to machine format]

Validators give you path, keyword, and maybe some parameters. This is for machines.

[Point to human format]

Transform this into clear, numbered errors with context. Show the field path in dot notation, describe what's wrong, show expected vs received values.

[Point to function]

This is simple code. Map over the errors, format each one with path, message, expected, and received. Join with blank lines for readability.

[Pause]

In Exercise 2.2, you'll build an error formatter that turns schema errors into useful messages you can log or show to users.

Now let's talk about what to do with these errors..."

[Transition]

---

### SLIDE 14: SEGMENT 3 - LOGGING AND DEBUGGING

**Title:** Using Validation Errors for Improvement

**Content:**

**Log Validation Results:**
```javascript
{
  "timestamp": "2026-01-02T10:30:00Z",
  "workflow_id": "wf-12345",
  "validation_point": "ai_output",
  "schema": "quality-result.schema.json",
  "valid": false,
  "errors": [...],
  "data": {...}
}
```

**Track Patterns:**
- Which validation points fail most?
- Which schema fields cause issues?
- Which AI prompts need improvement?
- Which recovery strategies work best?

**Improvement Loop:**
```
Validation Failures
       ↓
   Analyze Patterns
       ↓
   Improve Prompts/Schemas
       ↓
   Fewer Failures
```

**Graphic:** Continuous improvement cycle

**GRAPHICS:**

**Graphic 1: Validation Improvement Loop**
- Purpose: Show how validation failures drive continuous improvement
- Type: Circular improvement cycle diagram
- Elements: 4-stage cycle with feedback arrows
- Labels:
  - Stage 1: "Validation Failures Occur" (log all attempts with full context)
  - Stage 2: "Analyze Patterns" (which fields fail? which prompts need work?)
  - Stage 3: "Improve Prompts/Schemas" (tighten prompts, adjust constraints)
  - Stage 4: "Fewer Failures" (measure improvement)
  - Cycle back to Stage 1
- Relationships: Circular arrows showing continuous loop; include metrics annotation "Track failure rate over time"
- Visual Style: Use cycle diagram with arrows; include data icons (charts/graphs)

**SPEAKER NOTES:**

"Don't just handle errors - learn from them.

[Point to log structure]

Log every validation attempt with full context: timestamp, which workflow, which validation point, which schema, whether it passed, and if not, the errors and data.

[Point to patterns]

Then analyze the logs. Which validation points fail most often? Input validation failures might mean your form needs better validation. AI output failures might mean your prompt needs improvement.

Which schema fields cause the most issues? Maybe your constraints are too strict, or your prompt isn't clear about that field.

[Point to improvement loop]

This creates a continuous improvement loop. Validation failures tell you where to improve. Better prompts and schemas mean fewer failures.

After a month of logging, you'll have data-driven insights into your workflow reliability.

In the capstone exercise, you'll document validation statistics and use them to improve your workflow."

[Transition]

---

### SLIDE 15: SEGMENT 3 - KEY TAKEAWAY

**Title:** Segment 3 Summary

**Content:**

**Key Takeaway:** Transform raw validation errors into actionable messages, log everything, and use patterns to improve

**Remember:**
- Raw validator output needs formatting for humans
- Include full path, message, expected vs received
- Log all validation attempts with full context
- Analyze patterns to improve prompts and schemas
- Validation failures are learning opportunities

**You'll Practice:**
Exercise 2.2 - Build error formatter with recovery strategies

**Graphic:** Error → Format → Log → Analyze → Improve

**SPEAKER NOTES:**

"Let me summarize error handling:

Raw validation errors are machine-readable. Transform them into human-readable messages with full context.

Log every validation attempt, not just failures. You need the full picture.

Analyze patterns over time. Which validation points, schemas, or prompts cause the most issues?

Use that data to improve. Better prompts, better schemas, fewer failures.

Validation failures are not just errors - they're signals telling you where to improve.

In Exercise 2.2, you'll build a complete error handler with formatting and recovery strategies.

[Pause]

Now let's look at using schemas as documentation."

[Transition: Click to Segment 4]

---

## SEGMENT 4: SCHEMA DOCUMENTATION
### Duration: 9 minutes | Slides 16-18

---

### SLIDE 16: SEGMENT 4 - SELF-DOCUMENTING SCHEMAS

**Title:** Schemas as Documentation

**Content:**

**Good Schema Documentation:**
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "workflow-result.schema.json",
  "title": "Workflow Execution Result",
  "description": "Output from a completed workflow execution",

  "type": "object",
  "properties": {
    "deliverable": {
      "type": "string",
      "description": "Generated deliverable content in markdown format"
    },
    "quality_score": {
      "type": "number",
      "minimum": 0,
      "maximum": 5,
      "description": "Quality evaluation score (0=poor, 5=excellent)"
    },
    "execution_time_seconds": {
      "type": "number",
      "minimum": 0,
      "description": "Total execution time in seconds"
    }
  }
}
```

**Benefits:**
- Schema IS the documentation
- Always accurate (it's what validates)
- Human and machine readable
- Single source of truth

**Graphic:** Schema with documentation annotations highlighted

**GRAPHICS:**

**Graphic 1: Self-Documenting Schema Elements**
- Purpose: Highlight the documentation fields within a schema
- Type: Annotated schema code with highlighting
- Elements: Schema code with documentation fields emphasized
- Labels:
  - Highlight `"title"` field → "Describes what this schema validates"
  - Highlight `"description"` field → "Explains purpose and context"
  - Highlight each property's `"description"` → "Documents field meaning and usage"
  - Highlight constraints (minimum, maximum) → "Documents allowed values"
  - Annotation: "These fields serve dual purpose: validation AND documentation"
- Relationships: Show how schema fields map to documentation needs
- Visual Style: Use color highlighting or callout boxes for documentation fields

**SPEAKER NOTES:**

"One of the best benefits of JSON Schema is that it serves double duty: validation and documentation.

[Point to example]

Look at how this schema documents itself. The title and description explain what it validates. Each property has its own description. Constraints like minimum and maximum document allowed values.

Anyone can read this schema and understand:
- What fields are in the result
- What type each field is
- What constraints apply
- What the purpose is

[Point to benefits]

And here's the key: this documentation is always accurate. It can't get out of date like a separate document can, because this IS what validates the data.

It's both human-readable and machine-readable. Humans can read it to understand the format. Tools can use it to validate.

It's your single source of truth for data format.

Let's look at generating documentation from schemas..."

[Transition]

---

### SLIDE 17: SEGMENT 4 - GENERATING DOCUMENTATION

**Title:** Tools for Schema Documentation

**Content:**

**Documentation Generators:**

1. **json-schema-to-markdown**
   - Generates markdown docs from schemas
   - Perfect for GitHub wikis

2. **docson**
   - Interactive HTML documentation
   - Great for internal reference

3. **redoc / swagger-ui**
   - API documentation from OpenAPI (which uses JSON Schema)
   - Professional API docs

**Example Generated Doc:**
```markdown
# Workflow Execution Result

Output from a completed workflow execution

## Properties

### deliverable
- **Type:** string
- **Required:** Yes
- **Description:** Generated deliverable content in markdown format

### quality_score
- **Type:** number
- **Required:** Yes
- **Range:** 0-5
- **Description:** Quality evaluation score (0=poor, 5=excellent)
```

**Graphic:** Schema → Tool → Documentation

**GRAPHICS:**

**Graphic 1: Documentation Generation Pipeline**
- Purpose: Show how tools convert schemas to documentation
- Type: Linear process flow
- Elements: Three-stage pipeline with tool in middle
- Labels:
  - Input: "JSON Schema File" (schema.json icon)
  - Process: "Documentation Generator" (json-schema-to-markdown, docson, or redoc logo/icon)
  - Output: Split to multiple formats:
    - "Markdown Docs" (GitHub icon)
    - "HTML Interactive Docs" (browser icon)
    - "API Reference" (API doc icon)
- Relationships: One schema → multiple documentation outputs
- Visual Style: Pipeline with branching outputs; emphasize "one source, many formats"

**SPEAKER NOTES:**

"You don't have to manually write documentation from schemas. Tools can generate it automatically.

[Point to tools]

json-schema-to-markdown creates markdown documentation. Perfect for GitHub wikis or internal docs.

docson creates interactive HTML documentation with expandable sections. Great for reference.

If you're building APIs, redoc and swagger-ui generate professional API documentation from OpenAPI specs, which use JSON Schema.

[Point to example]

Here's what generated documentation looks like. Clear, structured, accurate. And it's automatically generated from your schema, so it's always in sync with your validation.

[Pause]

The workflow is: write schemas for validation, generate documentation automatically, publish to your team wiki. One source, multiple uses."

[Transition]

---

### SLIDE 18: SEGMENT 4 - SCHEMA-DRIVEN DEVELOPMENT

**Title:** Schema-Driven Workflow Design

**Content:**

**The Pattern:**

1. **Define Schema First**
   - Before writing prompts or code
   - Defines data contract

2. **Generate Examples from Schema**
   - Tools create valid sample data
   - Use for testing

3. **Include Schema in AI Prompts**
   - AI knows exact format
   - Reduces validation failures

4. **Validate Against Schema**
   - Runtime validation
   - Ensures compliance

5. **Generate Documentation**
   - Schema becomes team reference
   - Always accurate

**Benefits:**
- Clear contracts between components
- Fewer integration issues
- Better AI output compliance
- Automatic documentation

**Graphic:** Schema-driven development cycle

**GRAPHICS:**

**Graphic 1: Schema-Driven Development Workflow**
- Purpose: Show the schema-first development pattern
- Type: Sequential workflow diagram with feedback loops
- Elements: 5-step workflow with schemas at center
- Labels:
  - Step 1: "Define Schema First" (before writing code or prompts)
  - Step 2: "Generate Examples" (tools create valid sample data from schema)
  - Step 3: "Include in AI Prompts" (schema embedded in prompt)
  - Step 4: "Validate Runtime" (all data validated against schema)
  - Step 5: "Generate Docs" (documentation auto-generated from schema)
  - Center: "Schema = Single Source of Truth"
- Relationships: Schema at center connecting to all steps; show how schema drives all activities
- Visual Style: Star/hub pattern with schema in center, or linear flow with schema referenced at each step

**SPEAKER NOTES:**

"Let me show you schema-driven development - a pattern that puts schemas at the center of your workflow design.

[Point to steps]

First, define your schema before you write anything else. This establishes the data contract.

Second, generate example data from your schema. Many tools can do this - you get valid sample data for testing.

Third, include the schema in your AI prompts. The AI sees exactly what format you need.

Fourth, validate at runtime. The schema ensures everything stays compliant.

Fifth, generate documentation from the schema. Your team always has accurate reference material.

[Point to benefits]

This pattern creates clear contracts between workflow components. Integration is easier because everyone knows the exact format. AI compliance improves because you're showing the schema. Documentation is automatic.

[Pause]

In the capstone exercise, you'll apply this pattern to your complete workflow."

[Transition: Click to closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 19-21

---

### SLIDE 19: HOMEWORK OVERVIEW

**Title:** This Session's Practice - Module Capstone

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 2.1: Workflow Validation | 20 min | Validation implemented + tests | Runtime validation, error handling |
| Exercise 2.2: Error Handling | 20 min | Error formatter + recovery logic | Error messages, recovery strategies |
| Exercise 2.3: Module Capstone | 20 min | Complete validated system + docs | Full integration, documentation |
| **Total** | **60 min** | | |

**Graphic:** Exercise icons showing progression to complete system

**SPEAKER NOTES:**

"Here's your homework - this completes the module with the capstone project.

[Walk through each exercise]:

Exercise 2.1 takes about 20 minutes. You'll add validation to your actual workflow at input and AI output points, with test cases.

Exercise 2.2 is 20 minutes. You'll build a complete error handler that formats validation errors and implements recovery strategies.

Exercise 2.3 is the module capstone - 20 minutes. You'll document your complete validated workflow system, including validation statistics, recovery success rates, and lessons learned.

When you finish Exercise 2.3, you'll have a production-ready validated workflow system that's robust, debuggable, and well-documented.

All instructions are in your participant guide."

[Transition]

---

### SLIDE 20: RESOURCES

**Title:** Resources for This Session

**Content:**

**Validation Libraries:**
- JavaScript: ajv (fastest), zod (TypeScript-first)
- Python: jsonschema, pydantic
- Make.com: JSON module
- n8n: Function node with ajv

**Documentation Tools:**
- json-schema-to-markdown
- docson
- redoc / swagger-ui

**Reference:**
- Module Appendix B: Validation Tools
- Module Appendix C: Evaluation Rubric

**Support:**
- Questions: [Async channel]
- Office Hours: [If applicable]

**Graphic:** Tool icons and links

**SPEAKER NOTES:**

"You have several resources to support your capstone:

For validation libraries, use ajv for JavaScript, jsonschema for Python. Platform-specific guidance is in your participant guide.

For documentation generation, try json-schema-to-markdown for markdown docs.

Module Appendix B lists all validation tools by platform. Appendix C has the evaluation rubric so you know what makes a strong capstone submission.

If you get stuck, post in [channel] with your specific issue.

[Transition]

---

### SLIDE 21: MODULE COMPLETE

**Title:** Module 3 Complete - What You've Achieved

**Content:**

**You Now Can:**
- ✓ Write JSON schemas for any data structure
- ✓ Validate workflow inputs automatically
- ✓ Handle AI output validation with retry strategies
- ✓ Create actionable error messages
- ✓ Generate documentation from schemas
- ✓ Build production-ready validated workflows

**Next Steps:**
1. Complete the capstone (Exercise 2.3)
2. Implement validation in all your workflows
3. Share your schema library with your team

**Impact:**
Fewer workflow failures, faster debugging, better documentation, more reliable client deliverables

**Graphic:** Achievement graphic showing progression from Module 3 start to completion

**SPEAKER NOTES:**

"Congratulations! You've completed Advanced Module 3: JSON Schema and Data Validation.

[Point to accomplishments]

You now have the skills to write schemas for any data structure, validate at multiple workflow points, handle validation failures gracefully, and use schemas as living documentation.

[Point to next steps]

Your next step is completing the capstone - documenting your complete validated workflow system.

Then, apply these techniques to all your workflows. Start with your most critical workflow and add validation at input and AI output points. Expand from there.

[Point to impact]

The impact will be immediate: fewer mysterious failures, faster debugging when issues occur, better documentation for your team, and more reliable client deliverables.

[Final]

Great work in this module. You've taken a major step toward production-ready, enterprise-grade AI workflows.

Questions before we wrap?"

---

## APPENDICES

### Appendix A: Slide Type Definitions

**TITLE SLIDE**, **PROBLEM STATEMENT**, **INSIGHT / REVELATION**, **CONCEPT INTRODUCTION**, **FRAMEWORK / MODEL**, **COMPARISON**, **DEEP DIVE**, **CASE STUDY**, **PATTERN / BEST PRACTICE**, **METRICS / DATA**, **ARCHITECTURE / DIAGRAM**, **OBJECTION HANDLING**, **ACTION / NEXT STEPS**, **SUMMARY / RECAP**, **CLOSING / CALL TO ACTION**, **Q&A / CONTACT**, **APPENDIX**

### Appendix B: Presentation Delivery Notes

**Timing Checkpoints:**

| Checkpoint | Target Time |
|------------|-------------|
| End Segment 1 | 15 min |
| End Segment 2 | 27 min |
| End Segment 3 | 39 min |
| End Segment 4 | 48 min |
| Session End | 51 min |

**Demo Preparation:**
- Workflow platform (Make/n8n) or code editor
- Example workflow with validation
- Schema files from Session 1
- Backup: Screenshots and prepared error examples

**Key Messages to Emphasize:**
1. "Validate early, validate often - multiple validation points prevent cascading failures"
2. "AI is non-deterministic - validation with recovery is mandatory, not optional"
3. "Your schemas are documentation - keep them clear and complete"

### Appendix C: BACKGROUND & Implementation Guidance

See template for full BACKGROUND section structure (Rationale, Key Research & Citations, Q&A Preparation) and Implementation Guidance structure (Getting Started, Best Practices, Common Pitfalls, Tools & Technologies).

---

### Appendix D: Runtime Validation Implementation Examples

**Make.com Implementation:**

1. **Add JSON Module After AI Generation**
   - Module: "Parse JSON"
   - Input: AI response text
   - Schema: Paste your JSON Schema

2. **Add Router for Branching**
   - Route 1 (Valid): Continue workflow
   - Route 2 (Invalid): Error handler
   - Filter: Check validation status

3. **Error Handler Route**
   - Format error message
   - Log to data store
   - Send notification or retry

**n8n Implementation:**

```javascript
// Function node: Validate with AJV
const Ajv = require('ajv');
const ajv = new Ajv();

const schema = { /* your schema */ };
const validate = ajv.compile(schema);

const data = JSON.parse($input.item.json.aiResponse);
const valid = validate(data);

if (!valid) {
  return {
    json: {
      valid: false,
      errors: validate.errors,
      originalData: data
    }
  };
}

return { json: { valid: true, data: data } };
```

Follow with IF node to branch on `valid` field.

**Python (Custom Script):**

```python
import jsonschema
import json

def validate_ai_output(response_text, schema):
    """
    Validate AI response against schema with error handling.

    Returns: (is_valid: bool, data: dict, errors: list)
    """
    try:
        # Parse JSON
        data = json.loads(response_text)
    except json.JSONDecodeError as e:
        return False, None, [f"JSON parse error: {str(e)}"]

    try:
        # Validate against schema
        jsonschema.validate(data, schema)
        return True, data, []
    except jsonschema.ValidationError as e:
        return False, data, [e.message]

# Usage
is_valid, data, errors = validate_ai_output(ai_response, my_schema)

if not is_valid:
    # Handle validation failure
    log_errors(errors)
    retry_or_escalate()
else:
    # Use validated data
    process(data)
```

---

### Appendix E: Error Recovery Strategies

**Type Coercion (Auto-Fix Minor Issues):**

```javascript
function autoFixCommonIssues(data, schema) {
  // Clone to avoid mutating original
  const fixed = JSON.parse(JSON.stringify(data));

  // String to number coercion
  if (schema.properties.score?.type === 'number' && typeof fixed.score === 'string') {
    const num = parseFloat(fixed.score);
    if (!isNaN(num)) {
      fixed.score = num;
      console.log('Auto-fixed: score string → number');
    }
  }

  // Default values for missing optional fields
  if (!fixed.priority && schema.properties.priority?.default) {
    fixed.priority = schema.properties.priority.default;
    console.log('Auto-fixed: added default priority');
  }

  // Remove additional properties if schema disallows them
  if (schema.additionalProperties === false) {
    const allowedProps = Object.keys(schema.properties);
    Object.keys(fixed).forEach(key => {
      if (!allowedProps.includes(key)) {
        delete fixed[key];
        console.log(`Auto-fixed: removed additional property ${key}`);
      }
    });
  }

  return fixed;
}
```

**Retry with Stricter Prompt:**

```javascript
function buildRetryPrompt(originalPrompt, validationErrors, attemptNumber) {
  const errorSummary = validationErrors.map(e =>
    `- ${e.path}: ${e.message}`
  ).join('\n');

  return `${originalPrompt}

IMPORTANT: Your previous response failed validation with these errors:
${errorSummary}

Attempt ${attemptNumber} of 3. Please provide response in EXACT JSON format matching the schema.
Return ONLY valid JSON with no additional text.`;
}
```

**Partial Data Usage Pattern:**

```javascript
function extractValidFields(data, schema, validationErrors) {
  const valid = {};
  const invalid = {};

  // Identify which fields failed validation
  const failedPaths = validationErrors.map(e => e.path);

  Object.keys(schema.properties).forEach(field => {
    const fieldPath = `/${field}`;
    if (!failedPaths.some(p => p.startsWith(fieldPath))) {
      valid[field] = data[field];
    } else {
      invalid[field] = data[field];
    }
  });

  return {
    validFields: valid,
    invalidFields: invalid,
    isPartial: Object.keys(invalid).length > 0
  };
}
```

---

### Appendix F: Error Message Templates

**Validation Error Email Template:**

```markdown
Subject: Workflow Validation Failure - [Workflow Name]

Workflow: [Workflow Name]
Execution ID: [ID]
Timestamp: [ISO timestamp]
Validation Point: [Input/AI Output/Inter-step]

VALIDATION ERRORS:

1. Field: client.name
   Problem: Required field is missing
   Expected: string
   Received: undefined

2. Field: score
   Problem: Value below minimum
   Expected: >= 0
   Received: -5

RAW DATA:
```json
[data dump]
```

RECOVERY ACTION: [Manual review required / Auto-retry scheduled / Partial data used]

View full details: [Link to workflow execution log]
```

**Slack Notification Template:**

```json
{
  "blocks": [
    {
      "type": "header",
      "text": {
        "type": "plain_text",
        "text": "⚠️ Validation Failure"
      }
    },
    {
      "type": "section",
      "fields": [
        {
          "type": "mrkdwn",
          "text": "*Workflow:*\n[Workflow Name]"
        },
        {
          "type": "mrkdwn",
          "text": "*Validation Point:*\nAI Output"
        }
      ]
    },
    {
      "type": "section",
      "text": {
        "type": "mrkdwn",
        "text": "*Errors:*\n• client.name: Required field missing\n• score: Value -5 below minimum 0"
      }
    },
    {
      "type": "actions",
      "elements": [
        {
          "type": "button",
          "text": {
            "type": "plain_text",
            "text": "View Details"
          },
          "url": "[execution log URL]"
        }
      ]
    }
  ]
}
```

---

### Appendix G: Exercise 2.1 - Workflow Validation Implementation

**Objective:** Add validation to your workflow at input and AI output points

**Time:** 20 minutes

**Deliverables:**
1. Validation implemented at 2+ points in workflow
2. Error handling configured
3. Test results showing validation catches errors

**Steps:**

1. **Choose Validation Points**
   - Identify workflow trigger (input validation)
   - Identify AI generation step (output validation)

2. **Implement Input Validation**
   - Add validation step after trigger
   - Use schema from Exercise 1.1 (workflow-input)
   - Configure error branch (reject invalid triggers)

3. **Implement AI Output Validation**
   - Add validation step after AI generation
   - Use appropriate schema for AI output
   - Configure retry logic (max 2 attempts)

4. **Test Both Validation Points**
   - Test 1: Send invalid input (should reject)
   - Test 2: Force AI validation failure (modify schema to fail current output)
   - Test 3: Send valid input (should complete successfully)

5. **Document Results**
   - Screenshot validation step configuration
   - Screenshot error handling branch
   - Note validation failure rate

---

### Appendix H: Exercise 2.2 - Error Handler Implementation

**Objective:** Build error formatter with recovery strategies

**Time:** 20 minutes

**Deliverables:**
1. Error formatting function
2. Recovery logic implementation
3. Test cases showing different recovery paths

**Steps:**

1. **Create Error Formatter**
   - Build function to transform schema errors to human-readable format
   - Include field path, message, expected vs received
   - Format for logging and notifications

2. **Implement Recovery Strategies**
   - Auto-fix: Type coercion for string→number
   - Retry: Enhanced prompt for missing fields
   - Escalate: Queue for review after max retries

3. **Test Recovery Paths**
   - Test auto-fix with type mismatch
   - Test retry with missing field
   - Test escalation after 3 failures

4. **Log All Attempts**
   - Record validation results
   - Track which recovery strategies work
   - Measure success rates

---

### Appendix I: Exercise 2.3 - Module Capstone

**Objective:** Document complete validated workflow system

**Time:** 20 minutes

**Deliverable:** Validation documentation report

**Required Sections:**

1. **System Overview**
   - Which workflows have validation
   - Validation points per workflow
   - Schemas used

2. **Validation Statistics (Last Week)**
   - Total validation attempts: [number]
   - Success rate: [percentage]
   - Most common failures: [list top 3]
   - Recovery success rate: [percentage]

3. **Schema Library**
   - List all schemas created
   - Reference relationships ($ref usage)
   - Maintenance notes

4. **Error Handling Strategy**
   - Auto-fix rules defined
   - Retry logic configuration
   - Escalation procedures

5. **Lessons Learned**
   - What validation caught that you didn't expect
   - Prompts improved based on validation failures
   - Schema adjustments made during testing

6. **Next Steps**
   - Additional workflows to add validation
   - Schema improvements planned
   - Monitoring/alerting enhancements

**Format:** Markdown document with diagrams (flowcharts showing validation points)

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | AI Practitioner Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |
