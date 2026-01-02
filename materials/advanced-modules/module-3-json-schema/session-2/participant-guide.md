# **MODULE 3 SESSION 2: Validation in Practice**

**Module:** Advanced Module 3: JSON Schema & Data Validation
**Session:** 2 of 2
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Module Navigation:** [← Session 1](../session-1/participant-guide.md) | Session 2

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

By the end of this session, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Implement runtime validation at key workflow points | Exercise 2.1 |
| 2 | Validate AI outputs with retry and recovery strategies | Exercise 2.1 |
| 3 | Create actionable error messages from validation failures | Exercise 2.2 |
| 4 | Generate documentation from schemas for team reference | Exercise 2.3 (Capstone) |

---

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Session 1 exercises - 5+ schemas created
- [ ] Schema library organized
- [ ] Understanding of JSON Schema syntax
- [ ] Validation tools identified for your platform

**Not ready?** Complete Session 1 exercises before proceeding.

---

## Key Concepts

### Concept 1: Validation Points

**Definition:**
Strategic locations in your workflow where data is validated against schemas to catch errors early.

**Why It Matters:**
Multiple validation points create defense in depth. Errors are caught before they propagate, making debugging faster and preventing cascading failures.

**Core Principle:**
> Validate early, validate often. Each validation point serves a specific purpose in protecting your workflow.

**The Four Critical Points:**

1. **Input Validation** - Before processing starts
   - Catches bad trigger data immediately
   - Prevents processing with invalid input

2. **AI Output Validation** - After generation
   - Most critical for reliability
   - Handles non-deterministic AI behavior

3. **Inter-Step Validation** - Between workflow steps
   - Ensures data contracts between components
   - Prevents cascading failures

4. **Final Validation** - Before delivery
   - Last quality gate
   - Ensures complete, correct deliverable

**When to Use:**
Start with input + AI output validation (most critical). Add inter-step and final as complexity grows.

**When NOT to Use:**
Don't skip validation thinking "the AI will get it right" - it won't, 100% of the time.

---

### Concept 2: Validation Pattern

**Definition:**
A standard four-step process for validating data: Parse → Validate → Branch → Handle.

**Why It Matters:**
This pattern works universally across all platforms and validation points. Learn it once, use it everywhere.

**The Pattern:**
```
1. Parse JSON (catch syntax errors)
2. Validate against schema (catch structure errors)
3. Branch on result (pass or fail)
4. Handle errors (log, retry, escalate)
```

**Universal Implementation:**
```javascript
// JavaScript example
try {
  const data = JSON.parse(input);  // Step 1: Parse
  const valid = validate(data, schema);  // Step 2: Validate

  if (valid) {  // Step 3: Branch
    continueWorkflow(data);
  } else {
    handleError(validate.errors);  // Step 4: Handle
  }
} catch (parseError) {
  handleParseError(parseError);
}
```

**Platform Variations:**
- Make.com: JSON module → Filter → Router with error handler
- n8n: Function node → IF node → Error workflow
- Custom code: Parser → Validator library → Conditional → Error handler

**Common Mistake:**
Skipping the parse step and going straight to validation. Always parse first to catch JSON syntax errors.

---

### Concept 3: AI Output Recovery

**Definition:**
Strategies for handling AI outputs that fail validation, ranging from automatic fixes to human escalation.

**Why It Matters:**
AI is non-deterministic. Even perfect prompts yield 1-5% format variation. Recovery strategies handle failures automatically without manual intervention.

**Recovery Ladder:**

| Strategy | When to Use | Example |
|----------|-------------|---------|
| **Retry with stricter prompt** | Parse errors, structural issues | Add "IMPORTANT: ONLY valid JSON" to prompt |
| **Auto-fix minor issues** | Type coercion, missing optionals | "4" string → 4 number, use default value |
| **Use partial data** | Some fields valid, others not | Use valid fields, flag invalid for review |
| **Escalate to human** | Complex failures, max retries reached | Queue for review with full context |

**Decision Flow:**
```
Validation Fails
     ↓
Parse error? → Retry with stricter prompt (max 2-3)
     ↓
Type mismatch? → Auto-fix if safe
     ↓
Structural issue? → Partial data if possible
     ↓
Max retries? → Escalate to human
```

**Best Practice:**
Always limit retries (2-3 maximum). After that, escalate rather than loop indefinitely.

---

### Quick Reference: Validation Implementation

**By Platform:**

| Platform | Parse | Validate | Branch | Handle Errors |
|----------|-------|----------|--------|---------------|
| Make.com | JSON module | JSON module (schema) | Filter | Error handler route |
| n8n | Function node | Function node (ajv) | IF node | Error workflow |
| JavaScript | JSON.parse() | ajv.validate() | if/else | try/catch + handler |
| Python | json.loads() | jsonschema.validate() | if/else | try/except + handler |

**Validation Libraries:**

| Language | Library | Installation | Usage |
|----------|---------|--------------|-------|
| JavaScript | ajv | `npm install ajv` | Fast, most popular |
| JavaScript | zod | `npm install zod` | TypeScript-first |
| Python | jsonschema | `pip install jsonschema` | Reference implementation |
| Python | pydantic | `pip install pydantic` | Popular, Python-native |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Implementing validation in production workflows with error handling and recovery

**Key Points from Each Segment:**

**Segment 1: Validation in Workflows**
- Four critical validation points: input, AI output, inter-step, final
- Universal pattern: Parse → Validate → Branch → Handle
- Platform doesn't matter - pattern is the same
- Each validation point prevents different failure types

**Segment 2: Validating AI Outputs**
- AI is non-deterministic - validation is mandatory
- Include schema in prompt as prevention
- Always validate after generation as backup
- Recovery ladder: Retry → Auto-fix → Partial → Escalate
- Limit retries to 2-3 maximum

**Segment 3: Error Messages and Debugging**
- Transform raw validator errors into actionable messages
- Include full path, clear message, expected vs received
- Log all validation attempts with full context
- Analyze patterns to improve prompts and schemas
- Validation failures are learning opportunities

**Segment 4: Schema Documentation**
- Schemas with good titles/descriptions are self-documenting
- Tools can generate documentation automatically
- Schema-driven development: schema first, everything else follows
- Schemas serve double duty: validation and documentation

### Demo Recap

**What Was Demonstrated:**
Validation implemented in a real workflow (Make/n8n/code) showing parse, validate, branch, and error handling

**Key Steps:**
1. Valid data sent through workflow - validation passes, continues
2. Invalid data sent - validation catches error, routes to handler
3. Error handler receives detailed error information
4. Retry logic attempts recovery with stricter prompt

**Result:**
Demonstrated that validation creates defense in depth, catching errors before they break workflow or reach clients

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 2.1 | 20 min | Validation implemented + test results | Runtime validation, error handling |
| 2.2 | 20 min | Error formatter + recovery logic | Error messages, recovery strategies |
| 2.3 | 20 min | Complete validated system + docs | Full integration, documentation, capstone |

---

### Exercise 2.1: Workflow Validation

**Duration:** 20 minutes

**Purpose:**
Implement validation in your actual workflow at input and AI output points. You'll add validation steps, configure error handlers, and test with valid and invalid data.

**You Will Create:**
- Validation at workflow input point
- Validation at AI output point
- Error handlers for both
- Test results showing pass/fail cases

---

#### Instructions

**Step 1: Add input validation**

In your workflow, add a validation step after the trigger/input:

**For Make.com:**
1. Add JSON module set to "Parse JSON"
2. Configure with your workflow-input schema
3. Add Filter module after: "Only continue if JSON is valid"
4. Add error handler route for validation failures

**For n8n:**
1. Add Function node with this code:
```javascript
const Ajv = require('ajv');
const ajv = new Ajv();

const schema = { /* paste your workflow-input schema */ };
const validate = ajv.compile(schema);

const valid = validate($input.all()[0].json);

if (!valid) {
  throw new Error(JSON.stringify(validate.errors));
}

return $input.all();
```
2. Add IF node checking for errors
3. Connect to error workflow

**For Custom Code (JavaScript):**
```javascript
const Ajv = require('ajv');
const ajv = new Ajv();

const schema = require('./schemas/inputs/workflow-input.schema.json');
const validate = ajv.compile(schema);

try {
  const input = JSON.parse(requestBody);
  const valid = validate(input);

  if (!valid) {
    return {
      success: false,
      errors: validate.errors
    };
  }

  // Continue workflow
  processWorkflow(input);

} catch (e) {
  return {
    success: false,
    error: 'Invalid JSON: ' + e.message
  };
}
```

**For Python:**
```python
import json
import jsonschema

with open('schemas/inputs/workflow-input.schema.json') as f:
    schema = json.load(f)

try:
    data = json.loads(request_body)
    jsonschema.validate(data, schema)

    # Continue workflow
    process_workflow(data)

except json.JSONDecodeError as e:
    return {'success': False, 'error': f'Invalid JSON: {e}'}
except jsonschema.ValidationError as e:
    return {'success': False, 'error': e.message}
```

**Step 2: Add AI output validation**

After your AI generation step, add validation:

1. Parse AI response as JSON
2. Validate against quality-result schema (or whichever output schema you use)
3. If validation fails, retry with stricter prompt (max 2 times)
4. After 2 failed retries, escalate to error handler

**Retry Logic Example (JavaScript):**
```javascript
let attempts = 0;
const maxAttempts = 3;
let validResponse = null;

while (attempts < maxAttempts && !validResponse) {
  const prompt = attempts === 0
    ? basePrompt
    : basePrompt + "\n\nIMPORTANT: Respond with ONLY valid JSON matching the schema.";

  const response = await generateAI(prompt);

  try {
    const parsed = JSON.parse(response);
    const valid = validate(parsed, schema);

    if (valid) {
      validResponse = parsed;
    } else {
      attempts++;
      console.log(`Validation failed, attempt ${attempts}:`, validate.errors);
    }
  } catch (e) {
    attempts++;
    console.log(`Parse failed, attempt ${attempts}:`, e.message);
  }
}

if (!validResponse) {
  // Escalate to human review
  queueForReview({
    input: basePrompt,
    attempts: attempts,
    lastError: validate.errors
  });
}
```

**Step 3: Configure error handlers**

For both validation points, create error handlers that:
1. Log error with full context (timestamp, validation point, schema, errors, data)
2. Format user-friendly message
3. Return error response or route to review queue
4. Alert if critical

**Step 4: Test with valid and invalid data**

Create test cases:

| Test Case | Input | Expected Result | Actual Result |
|-----------|-------|-----------------|---------------|
| Valid complete | All required fields, correct types | Pass | |
| Missing required field | Omit client_name | Fail - "client_name required" | |
| Wrong type | task_type: 123 instead of string | Fail - "must be string" | |
| Invalid enum | priority: "critical" not in enum | Fail - "must be low/normal/high/urgent" | |
| Extra fields (strict mode) | Add unexpected field | Fail - "additional properties not allowed" | |

Document test results in `validation-tests.md`.

**Step 5: Review Your Work**

Check that your deliverables include:
- [ ] Input validation implemented
- [ ] AI output validation implemented
- [ ] Error handlers configured for both
- [ ] Retry logic for AI output (max 2-3 retries)
- [ ] Test results for 5+ cases
- [ ] Validation working correctly

---

#### Deliverable Specification

**File Names/Locations:**
- Validation in workflow (Make/n8n scenario, code in repo)
- `validation-tests.md` - Test results documentation

**Format Requirements:**
- Parse before validate
- Branch on validation result
- Error handlers for both validation points
- Retry logic limits attempts

**Quality Criteria:**
- [ ] Validation catches all test failure cases
- [ ] Error messages are clear and actionable
- [ ] Retry logic works and limits attempts
- [ ] Successful test cases pass through
- [ ] Error handlers log with full context

---

#### Example

**Scenario:** Validating workflow input

**Configuration (Make.com):**
1. JSON module: Parse incoming webhook data
2. JSON module: Validate against workflow-input.schema.json
3. Filter: Continue only if valid
4. Error handler: Log error + return 400 response

**Test - Valid:**
```json
{
  "task_type": "proposal",
  "client_name": "Acme Corporation",
  "priority": "high"
}
```
Result: ✓ Passes validation, workflow continues

**Test - Invalid:**
```json
{
  "task_type": "proposal"
}
```
Result: ✗ Validation fails with error:
```
Required property missing: client_name
```
Error handler logs and returns error response.

**Why This Works:**
The validation step acts as a gate. Only valid data passes through. Invalid data is caught immediately with clear error messages.

---

#### Tips & Troubleshooting

**Tips:**
- Test with intentionally invalid data to verify error handling works
- Start with one validation point, then add others
- Log everything - you'll need it for debugging
- Keep retry logic simple at first

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Validation not catching errors | Check schema is correct, ensure strict mode |
| Infinite retry loop | Add max attempts limit (2-3) |
| Parse errors not handled | Add try/catch around JSON.parse |
| Error messages unclear | Transform raw validator output to human-readable format |

---

### Exercise 2.2: Validation Error Handling

**Duration:** 20 minutes

**Purpose:**
Build a robust error handler that transforms validation errors into actionable messages and implements recovery strategies.

**You Will Create:**
- Error response schema
- Error formatting function
- Recovery strategy implementation
- Documentation of error handling approach

---

#### Instructions

**Step 1: Create error response schema**

Create `/schemas/outputs/validation-error.schema.json`:

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "validation-error.schema.json",
  "title": "Validation Error Response",
  "description": "Standardized error response for validation failures",

  "type": "object",
  "properties": {
    "success": {
      "const": false
    },
    "error_type": {
      "type": "string",
      "enum": ["validation_error", "parse_error", "unknown"]
    },
    "message": {
      "type": "string",
      "description": "Human-readable error summary"
    },
    "details": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "field": {
            "type": "string",
            "description": "Path to field with error"
          },
          "issue": {
            "type": "string",
            "description": "What's wrong"
          },
          "expected": {
            "type": "string",
            "description": "What was expected"
          },
          "received": {
            "description": "What was actually received"
          }
        },
        "required": ["field", "issue"]
      }
    },
    "recoverable": {
      "type": "boolean",
      "description": "Whether automatic recovery is possible"
    },
    "suggested_fix": {
      "type": "string",
      "description": "Suggestion for fixing the issue"
    }
  },
  "required": ["success", "error_type", "message"]
}
```

**Step 2: Create error formatting function**

Create a function that transforms raw validator errors:

**JavaScript:**
```javascript
function formatValidationError(schemaErrors) {
  const details = schemaErrors.map(error => ({
    field: error.instancePath || error.dataPath || 'unknown',
    issue: error.message,
    expected: getExpectedValue(error),
    received: error.data
  }));

  const recoverable = isRecoverable(details);
  const suggestedFix = generateFixSuggestion(details);

  return {
    success: false,
    error_type: 'validation_error',
    message: `Validation failed: ${details.length} issue(s)`,
    details: details,
    recoverable: recoverable,
    suggested_fix: suggestedFix
  };
}

function getExpectedValue(error) {
  if (error.params?.type) return `type: ${error.params.type}`;
  if (error.params?.allowedValues) return `one of: ${error.params.allowedValues.join(', ')}`;
  if (error.keyword === 'required') return 'required field';
  return error.keyword;
}

function isRecoverable(details) {
  // Simple type coercion issues are recoverable
  const recoverableIssues = details.filter(d =>
    d.issue.includes('type') && canCoerce(d)
  );
  return recoverableIssues.length === details.length;
}

function generateFixSuggestion(details) {
  if (details.length === 1) {
    const d = details[0];
    if (d.issue.includes('required')) {
      return `Add required field: ${d.field}`;
    }
    if (d.issue.includes('type')) {
      return `Convert ${d.field} to ${d.expected}`;
    }
  }
  return `Fix ${details.length} validation issues`;
}
```

**Python:**
```python
def format_validation_error(schema_errors):
    details = []
    for error in schema_errors:
        details.append({
            'field': error.path[0] if error.path else 'unknown',
            'issue': error.message,
            'expected': get_expected_value(error),
            'received': error.instance
        })

    return {
        'success': False,
        'error_type': 'validation_error',
        'message': f'Validation failed: {len(details)} issue(s)',
        'details': details,
        'recoverable': is_recoverable(details),
        'suggested_fix': generate_fix_suggestion(details)
    }
```

**Step 3: Implement recovery strategies**

**Strategy 1: Auto-Fix**
```javascript
function tryAutoFix(data, errors) {
  const fixedData = { ...data };

  for (const error of errors) {
    if (error.keyword === 'type') {
      // Try type coercion
      const field = error.instancePath.split('/').filter(p => p);
      const value = getNestedValue(data, field);

      if (error.params.type === 'number' && typeof value === 'string') {
        const num = parseFloat(value);
        if (!isNaN(num)) {
          setNestedValue(fixedData, field, num);
        }
      }
    }

    if (error.keyword === 'required' && error.params.missingProperty) {
      // Use default if available
      const schema = error.parentSchema;
      const propSchema = schema.properties[error.params.missingProperty];
      if (propSchema && 'default' in propSchema) {
        fixedData[error.params.missingProperty] = propSchema.default;
      }
    }
  }

  // Validate again
  const valid = validate(fixedData, schema);
  return valid ? fixedData : null;
}
```

**Strategy 2: Retry with Feedback**
```javascript
function retryWithFeedback(originalPrompt, validationErrors) {
  const errorSummary = validationErrors.map(e =>
    `- ${e.field}: ${e.issue} (expected: ${e.expected})`
  ).join('\n');

  const retryPrompt = `${originalPrompt}

VALIDATION ERRORS FROM PREVIOUS ATTEMPT:
${errorSummary}

Please regenerate following the exact schema. Respond with ONLY valid JSON.`;

  return retryPrompt;
}
```

**Strategy 3: Partial Success**
```javascript
function extractPartialData(data, errors) {
  // Identify which top-level fields are valid
  const errorFields = new Set(errors.map(e =>
    e.instancePath.split('/')[1]
  ));

  const partialData = {};
  for (const [key, value] of Object.entries(data)) {
    if (!errorFields.has(key)) {
      partialData[key] = value;
    }
  }

  return {
    data: partialData,
    invalidFields: Array.from(errorFields),
    complete: false
  };
}
```

**Strategy 4: Human Escalation**
```javascript
function escalateToHuman(context) {
  const review = {
    timestamp: new Date().toISOString(),
    workflow_id: context.workflowId,
    validation_point: context.validationPoint,
    original_input: context.input,
    ai_output: context.output,
    validation_errors: context.errors,
    attempted_fixes: context.attemptedFixes,
    retry_count: context.retryCount
  };

  // Queue for human review
  queueForReview(review);

  // Send alert if critical
  if (context.priority === 'high') {
    sendAlert('Validation failure requires human review', review);
  }
}
```

**Step 4: Document error handling approach**

Create `error-handling.md`:

```markdown
# Validation Error Handling

## Error Response Format

All validation errors follow the validation-error.schema.json format.

## Recovery Strategies

### 1. Auto-Fix (Applied First)
**When:** Type coercion possible, optional fields with defaults
**Examples:**
- "4" string → 4 number
- Missing optional field → use default value
**Success Rate:** ~30%

### 2. Retry with Feedback (Applied Second)
**When:** Parse errors, structural issues
**Max Attempts:** 2
**Prompt Enhancement:** Include previous validation errors
**Success Rate:** ~50%

### 3. Partial Success (Applied Third)
**When:** Some fields valid, others invalid
**Action:** Use valid fields, flag invalid for review
**Use Cases:** Non-critical fields invalid
**Success Rate:** ~15%

### 4. Human Escalation (Final Fallback)
**When:** Max retries exceeded, complex failures
**Action:** Queue for review with full context
**SLA:** Review within 24 hours
**Success Rate:** 100% (human fixes)

## Decision Flow

```
Validation Fails
     ↓
Try Auto-Fix → Success? → Continue
     ↓ No
Retry (2x) → Success? → Continue
     ↓ No
Partial Data? → Use Partial + Flag
     ↓ No
Escalate to Human
```

## Logging

All validation attempts logged with:
- Timestamp
- Workflow ID
- Validation point (input/output/inter-step/final)
- Schema used
- Validation result (pass/fail)
- Errors (if any)
- Recovery strategy applied
- Recovery result
```

**Step 5: Review Your Work**

Check that your deliverables include:
- [ ] Error response schema
- [ ] Error formatting function
- [ ] 4 recovery strategies implemented
- [ ] Documentation of approach
- [ ] Decision flow clear

---

#### Deliverable Specification

**File Names:**
- `/schemas/outputs/validation-error.schema.json`
- `error-formatter.js` (or .py)
- `error-handling.md`

**Quality Criteria:**
- [ ] Error format is consistent and schema-validated
- [ ] Formatting function produces clear, actionable messages
- [ ] Recovery strategies have clear success criteria
- [ ] Documentation explains when to use each strategy
- [ ] Retry limits are enforced

---

### Exercise 2.3: Module Capstone - Validated System

**Duration:** 20 minutes

**Purpose:**
Document your complete validated workflow system, including validation points, error handling, statistics (simulated if not yet deployed), and key learnings. This is the module capstone.

**You Will Create:**
- Complete system documentation
- Validation statistics (from tests or production)
- Error recovery analysis
- Lessons learned and recommendations

---

#### Instructions

**Step 1: Document system overview**

Create `validated-workflow-system.md`:

```markdown
# Validated Workflow System

## System Overview

**Workflow Name:** [Your workflow name]

**Description:** [What this workflow does]

**Validation Coverage:**
- Input validation: ✓
- AI output validation: ✓
- Inter-step validation: [✓ or planned]
- Final validation: [✓ or planned]

## Schema Library

| Schema | Purpose | Location | Version |
|--------|---------|----------|---------|
| workflow-input | Validate trigger data | /schemas/inputs/ | 1.0 |
| quality-result | Validate AI evaluation | /schemas/outputs/ | 1.0 |
| style-guide | Validate style config | /schemas/config/ | 1.0 |
| validation-error | Error response format | /schemas/outputs/ | 1.0 |
| base-types | Reusable type definitions | /schemas/common/ | 1.0 |

**Total Schemas:** 5+

## Validation Points

```
[Workflow Trigger]
        ↓
[Input Validation] ─── validate(workflow-input.schema.json)
        ↓ valid              ↓ invalid
[Process Input]         [Error Handler]
        ↓
[Generate AI Output]
        ↓
[Output Validation] ── validate(quality-result.schema.json)
        ↓ valid              ↓ invalid
[Use Output]            [Retry Logic] ─→ [Error Handler]
        ↓
[Final Output]
```

### Validation Configuration

**Input Validation:**
- Schema: workflow-input.schema.json
- Strict mode: Yes (additionalProperties: false)
- Required fields: task_type, client_name
- Error handling: Log + return 400 response

**AI Output Validation:**
- Schema: quality-result.schema.json
- Retry logic: Max 2 retries with stricter prompt
- Auto-fix: Type coercion for score field
- Error handling: Log + escalate after max retries

## Validation Statistics

### Test Results (or Production Data)

**Test Period:** [Date range or "Pre-deployment tests"]
**Total Executions:** [Number of test runs]

| Validation Point | Pass Rate | Fail Count | Common Errors |
|------------------|-----------|------------|---------------|
| Input validation | 90% | 5 | Missing client_name (3), Invalid task_type (2) |
| AI output validation | 85% | 8 | Score wrong type (4), Missing suggestions (4) |
| Overall system | 82% | 9 | [Combined] |

### Error Recovery Statistics

| Recovery Strategy | Attempts | Success Count | Success Rate |
|-------------------|----------|---------------|--------------|
| Auto-fix (type coercion) | 4 | 3 | 75% |
| Retry with feedback | 8 | 5 | 62% |
| Partial data | 2 | 1 | 50% |
| Human escalation | 3 | 3 | 100% |

**Key Insight:** Auto-fix and retry handle most failures. Only 3/50 tests required human intervention.

## Error Handling

### Error Response Format
All errors follow validation-error.schema.json

### Recovery Strategies

1. **Auto-Fix:** Type coercion, default values
2. **Retry:** Max 2 attempts with enhanced prompts
3. **Partial:** Use valid fields, flag invalid
4. **Escalate:** Queue for human review

### Error Logging
- All validation attempts logged
- Includes: timestamp, validation point, schema, result, errors
- Log location: [Platform logging system or file path]
- Retention: 90 days

## Documentation

### Schema Documentation
- Location: /schemas/README.md
- Format: Markdown with examples
- Coverage: All schemas documented with usage instructions

### API Contract (if applicable)
[Link to generated API docs or N/A]

## Key Learnings

1. **Schema Strictness:** Setting additionalProperties: false caught 2 errors where AI added unexpected fields. This strictness is valuable.

2. **Prompt Improvement:** After seeing "score" returned as string 4 times, I modified the AI prompt to explicitly state "score must be a NUMBER between 0-5". Failure rate dropped to near zero.

3. **Error Messages:** Transforming raw validator errors to human-readable format reduced debugging time significantly. Clear messages like "client.name: Required field missing" vs "required keyword failed" make a huge difference.

## Recommendations

1. **Schema in Prompts:** Always include the exact schema in AI generation prompts. This reduced format errors by ~30% in testing.

2. **Validation Coverage:** Start with input + AI output validation. These catch 90% of issues. Add inter-step and final validation as complexity grows.

3. **Error Logging:** Log everything, even successes. Pattern analysis over time identifies prompt improvements and schema issues.

4. **Retry Limits:** Never exceed 3 retries. After that, human review is more efficient than automatic recovery.

5. **Team Schema Library:** Maintain schemas in a central location with clear README. This enables reuse across workflows and maintains consistency.

## Next Steps

1. Deploy validation to production workflow
2. Collect real usage statistics
3. Analyze error patterns monthly
4. Update prompts and schemas based on data
5. Extend validation to other workflows

## Appendix: Sample Validation Errors

### Example 1: Missing Required Field
```json
{
  "success": false,
  "error_type": "validation_error",
  "message": "Validation failed: 1 issue(s)",
  "details": [
    {
      "field": "client_name",
      "issue": "must have required property 'client_name'",
      "expected": "required field",
      "received": undefined
    }
  ],
  "recoverable": false,
  "suggested_fix": "Add required field: client_name"
}
```

### Example 2: Type Mismatch (Auto-Fixed)
```json
{
  "success": false,
  "error_type": "validation_error",
  "message": "Validation failed: 1 issue(s)",
  "details": [
    {
      "field": "score",
      "issue": "must be number",
      "expected": "type: number",
      "received": "4"
    }
  ],
  "recoverable": true,
  "suggested_fix": "Convert score to type: number"
}
```
**Recovery:** Auto-coerced "4" to 4, re-validated successfully.
```

**Step 2: Complete the documentation sections**

Fill in:
- Actual test results or production statistics
- Specific errors you encountered
- Recovery success rates from your testing
- Real learnings from implementation

**Step 3: Review and refine**

Check that your capstone includes:
- [ ] Complete system overview
- [ ] Schema library documented
- [ ] Validation points clearly mapped
- [ ] Statistics from testing
- [ ] Error recovery analysis
- [ ] Meaningful learnings (not generic)
- [ ] Actionable recommendations

---

#### Deliverable Specification

**File Name:** `validated-workflow-system.md`

**Format Requirements:**
- Complete system overview
- All validation points documented
- Real statistics (from tests or production)
- Specific learnings (not generic statements)
- Actionable recommendations

**Quality Criteria:**
- [ ] Documentation is comprehensive
- [ ] Statistics show real data (not just template)
- [ ] Learnings are specific to your implementation
- [ ] Recommendations are actionable
- [ ] System is production-ready or has clear path to production

---

## Templates & Resources

### Templates Provided This Session

| Template | Purpose | Location |
|----------|---------|----------|
| validation-error.schema.json | Error response format | Exercise 2.2 |
| error-formatter function | Transform validator errors | Exercise 2.2 |
| Recovery strategies | Handle validation failures | Exercise 2.2 |

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| AJV Documentation | Library Docs | https://ajv.js.org/ | JavaScript validation |
| jsonschema Python | Library Docs | https://python-jsonschema.readthedocs.io/ | Python validation |
| Make.com JSON Module | Platform Docs | [Make docs] | Make.com validation |
| n8n Function Node | Platform Docs | [n8n docs] | n8n validation |

### Module Appendix References

For this session's exercises, reference:

- **Appendix B:** Validation Tools - Platform-specific implementation guides
- **Appendix C:** Module Evaluation Rubric - Capstone assessment criteria

See the main module document ([Module 3](../module-3-json-schema.md)) for full appendix content.

---

## Self-Assessment

### Exit Criteria Checklist

Before completing the module, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Implement runtime validation at workflow points | Exercise 2.1 completed | ☐ |
| 2 | Validate AI outputs with retry strategies | Exercise 2.1 AI validation working | ☐ |
| 3 | Create actionable error messages | Exercise 2.2 error formatter | ☐ |
| 4 | Generate documentation from schemas | Exercise 2.3 capstone | ☐ |

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Workflow with validation | [Platform scenario/code] | Workflow platform or repo | ☐ |
| Validation test results | `validation-tests.md` | Project folder | ☐ |
| Error response schema | `validation-error.schema.json` | `/schemas/outputs/` | ☐ |
| Error formatter | `error-formatter.js/.py` | Project folder | ☐ |
| Error handling docs | `error-handling.md` | Project folder | ☐ |
| Capstone documentation | `validated-workflow-system.md` | Project folder | ☐ |

### Reflection Questions

Take 5 minutes to consider:

1. **What worked well?** What aspect of validation was easier than expected?

2. **What was challenging?** What took longer or was more complex than anticipated?

3. **How will you use this?** Which workflows will you add validation to first?

4. **What surprised you?** What did you learn that you didn't expect?

[Optional: Share insights in [support channel] to help your peers]

---

## Getting Help

### Quick Answers
- **[Support Channel]** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Tag your cohort for implementation tips

### Common Questions This Session

**Q: My workflow platform doesn't support the validation library. What should I do?**
A: Most platforms support custom code via function nodes or HTTP modules. Call an external validation service, or use platform-native JSON parsing with manual field checking as a starting point.

**Q: How do I handle validation in Make.com specifically?**
A: Use the JSON module with schema validation enabled. Add a Filter after it to branch on validation result. Set up error handler routes for failures. See Appendix B for detailed Make.com instructions.

**Q: Should I validate configuration files every time the workflow runs?**
A: Validate on load/initialization, not on every execution. Cache the validated configuration and reuse it. Re-validate only when configuration changes.

**Q: My AI output fails validation 20% of the time. Is that normal?**
A: That's higher than expected. Check: (1) Is your schema in the AI prompt? (2) Is the schema too strict? (3) Does the prompt explicitly request the format? With optimization, you should see <5% failure rate.

**Q: How do I decide between retry and escalation?**
A: Retry for: parse errors (AI didn't return JSON), easily fixable structural issues. Escalate for: max retries exceeded (2-3), complex validation failures, or when retry has low success rate for that error type.

### When to Ask for Help

- **Before asking:** Check Appendix B for platform-specific guidance, test with simple valid/invalid data
- **Good to ask:** "I implemented validation but it's not catching [specific error]. Here's my code/configuration..."
- **Include:** Your schema, test data, validation code/configuration, and the actual vs expected result

### Office Hours

[If applicable]
- **When:** [Day/Time]
- **Where:** [Platform/Link]
- **For:** Platform-specific implementation help, capstone feedback

---

## Looking Ahead

### Module Complete!

You've completed Advanced Module 3: JSON Schema & Data Validation. You now have:
- ✓ JSON Schema expertise
- ✓ Production-ready validation implementation
- ✓ Robust error handling
- ✓ Schema-driven development practices

### Next Steps

1. **Deploy your validated system**
2. **Apply validation to all workflows**
3. **Share schema library with your team**
4. **Monitor validation statistics**
5. **Iterate based on error patterns**

### Continuing Your Learning

Consider these advanced topics:
- **Block 3**: AI Automation Architecture (if not yet completed)
- **Other Advanced Modules**: Additional specialized topics
- **Community**: Share your validated workflow patterns with peers

---

## Glossary

| Term | Definition |
|------|------------|
| Validation Point | Location in workflow where data is validated against schema |
| Defense in Depth | Multiple validation points preventing cascading failures |
| Recovery Strategy | Approach for handling validation failures (retry, auto-fix, escalate) |
| Auto-Fix | Automatic correction of minor validation errors (type coercion, defaults) |
| Retry with Feedback | Regenerating AI output with validation errors included in prompt |
| Partial Success | Using valid portions of data when some fields fail validation |
| Human Escalation | Queuing failed validation for manual review |
| Self-Documenting Schema | Schema with clear titles and descriptions that serve as documentation |
| Schema-Driven Development | Design pattern where schema is defined first, everything else follows |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial guide created |

---

**Navigation:** [← Session 1](../session-1/participant-guide.md) | Session 2

---

**CONGRATULATIONS ON COMPLETING ADVANCED MODULE 3!**
