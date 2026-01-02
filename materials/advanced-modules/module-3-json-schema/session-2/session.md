# **Session 2: Validation in Practice**

**Advanced Module 3: JSON Schema & Data Validation**
**Session:** 2 of 2
**Duration:** 45 min live + 60 min homework

---

## **Entry Criteria**

- [ ] 5+ schemas created
- [ ] Schema library organized
- [ ] Understanding of schema syntax
- [ ] Validation tools identified

## **Exit Criteria**

- [ ] Runtime validation implemented in workflows
- [ ] AI output validation working
- [ ] Error handling for validation failures
- [ ] Schema documentation generated
- [ ] Module capstone completed

-----

## **Workshop Content (45 minutes)**

**Segment 1: Validation in Workflows (12 min)**

- **Where to validate:**
  1. **Input validation:** Before processing starts
  2. **AI output validation:** After generation
  3. **Inter-step validation:** Between workflow steps
  4. **Final validation:** Before delivery

- **Validation workflow pattern:**
  ```
  [Input] → [Validate] → [Process] → [Validate] → [Output]
              ↓                          ↓
           [Error]                    [Error]
  ```

- **Platform implementation:**
  - Make: JSON module + filter
  - n8n: Function node with ajv library
  - Custom: ajv, zod, or similar library

**Segment 2: Validating AI Outputs (12 min)**

- **The challenge:**
  - AI outputs are non-deterministic
  - May not follow requested format exactly
  - Need graceful handling

- **Validation prompt pattern:**
  ```markdown
  Generate your response as JSON matching this schema:

  ```json
  {
    "analysis": { "type": "string" },
    "confidence": { "type": "number", "minimum": 0, "maximum": 1 },
    "recommendations": { "type": "array", "items": { "type": "string" } }
  }
  ```

  Respond with ONLY valid JSON, no other text.
  ```

- **Post-generation validation:**
  ```
  response = ai_generate(prompt)

  TRY:
    parsed = JSON.parse(response)
    validate(parsed, schema)
    return parsed
  CATCH ParseError:
    # Response wasn't valid JSON
    retry_with_stricter_prompt()
  CATCH ValidationError as e:
    # JSON valid but wrong structure
    fix_or_retry(e.details)
  ```

- **Handling validation failures:**
  1. Retry with more explicit prompt
  2. Attempt to fix/coerce data
  3. Use partial data if valid subset
  4. Escalate to human

**Segment 3: Error Messages and Debugging (12 min)**

- **Useful error information:**
  ```json
  {
    "valid": false,
    "errors": [
      {
        "path": "/client/name",
        "message": "Required property missing",
        "keyword": "required"
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

- **Human-readable error formatting:**
  ```
  Validation failed:
  - client.name: Required field is missing
  - priority: "urgent" is not allowed (use: low, normal, high)
  ```

- **Logging validation results:**
  - Log all validation attempts
  - Track failure patterns
  - Identify common issues
  - Improve prompts/schemas based on data

**Segment 4: Schema Documentation (9 min)**

- **Self-documenting schemas:**
  - Use `title` and `description` fields
  - Document each property
  - Include examples
  - Note constraints clearly

- **Generating documentation:**
  - Tools like json-schema-to-markdown
  - API documentation from schemas
  - Example generators

- **Schema-driven development:**
  - Define schema first
  - Generate examples from schema
  - Use schema in AI prompts
  - Validate against schema

-----

## **Self-Paced Exercises (60 minutes total)**

### **Exercise 2.1: Workflow Validation (20 minutes)**

*Add validation to your workflow*

1. **Add input validation step:**

```markdown
# Input Validation Implementation

## Validation Point: Workflow Input

### Schema Used
`workflow-input.schema.json`

### Implementation (Make/n8n)

1. Receive input data
2. Parse JSON
3. Validate against schema
4. IF valid: continue workflow
5. IF invalid: route to error handler

### Validation Module Configuration
```json
{
  "schema": "[your schema here]",
  "strict": true,
  "coerce": false
}
```

### Error Handler
On validation failure:
1. Log error with details
2. Format user-friendly message
3. Return error response
4. Alert if critical

### Test Cases

| Input | Expected | Actual |
|-------|----------|--------|
| Valid complete | Pass | |
| Missing required | Fail - list missing | |
| Wrong type | Fail - type error | |
| Extra fields | Fail (strict) | |
```

2. **Add AI output validation:**

```markdown
## Validation Point: AI Response

### Schema Used
`quality-result.schema.json`

### Prompt Addition
[Add schema to generation prompt]

### Post-Generation Validation
```
response = generate(prompt)
try:
  data = json.parse(response)
  validation = validate(data, schema)
  if validation.valid:
    continue_workflow(data)
  else:
    retry_generation(validation.errors)
except:
  retry_with_stricter_format()
```

### Retry Strategy
- Max retries: 2
- On retry: Add "IMPORTANT: Respond with ONLY valid JSON"
- After max retries: Escalate to human
```

**Deliverable:** Validation implemented in workflow + test results

-----

### **Exercise 2.2: Validation Error Handling (20 minutes)**

*Build robust error handling*

```markdown
# Validation Error Handler

## Error Response Schema

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "validation-error.schema.json",
  "type": "object",
  "properties": {
    "success": { "const": false },
    "error_type": {
      "type": "string",
      "enum": ["validation_error", "parse_error", "unknown"]
    },
    "message": { "type": "string" },
    "details": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "field": { "type": "string" },
          "issue": { "type": "string" },
          "expected": { "type": "string" },
          "received": {}
        }
      }
    },
    "recoverable": { "type": "boolean" },
    "suggested_fix": { "type": "string" }
  }
}
```

## Error Formatting Function

```
function format_validation_error(schema_errors):
  details = []
  for error in schema_errors:
    details.append({
      "field": error.path,
      "issue": error.message,
      "expected": get_expected(error),
      "received": error.actual_value
    })

  return {
    "success": false,
    "error_type": "validation_error",
    "message": f"Validation failed: {len(details)} issue(s)",
    "details": details,
    "recoverable": is_recoverable(details),
    "suggested_fix": generate_fix_suggestion(details)
  }
```

## Recovery Strategies

### Strategy 1: Auto-Fix
For minor issues, attempt automatic correction:
- Missing optional field → use default
- Wrong type but convertible → coerce
- Extra fields → remove

### Strategy 2: Retry with Feedback
Include validation errors in retry prompt:
```
Your response had validation errors:
- score: Expected integer, got string "4"
- suggestions: Array required, got null

Please regenerate following the exact schema.
```

### Strategy 3: Partial Success
If some parts valid:
- Use valid portions
- Flag invalid portions for review
- Continue with degraded output

### Strategy 4: Human Escalation
When not recoverable:
- Queue for human review
- Include original input
- Include validation errors
- Include attempted fixes
```

**Deliverable:** Error handler implementation + recovery logic

-----

### **Exercise 2.3: Module Capstone - Validated System (20 minutes)**

*Complete validated workflow system*

```markdown
# Validated Workflow System

## System Overview
[Description of your validated workflow]

## Schema Library

| Schema | Purpose | Location |
|--------|---------|----------|
| workflow-input | Validate trigger data | /schemas/inputs/ |
| quality-result | Validate AI evaluation | /schemas/outputs/ |
| style-guide | Validate style config | /schemas/config/ |
| [others] | | |

## Validation Points

```
[Input] ─── validate(input-schema) ───→ [Process]
                     ↓                       │
               [Error Handler]               │
                                            ↓
[Output] ←── validate(output-schema) ←── [AI Generate]
                     ↓
               [Error Handler]
```

## Validation Statistics

### Past 50 Executions
| Validation Point | Pass Rate | Common Errors |
|------------------|-----------|---------------|
| Input validation | X% | [List] |
| AI output validation | X% | [List] |
| Final validation | X% | [List] |

### Error Recovery
| Recovery Type | Count | Success Rate |
|---------------|-------|--------------|
| Auto-fix | | % |
| Retry | | % |
| Human escalation | | % |

## Documentation Generated

### Schema Documentation
[Link to generated docs]

### API Contract
[If applicable - API documentation from schemas]

## Key Learnings

1. **[Learning]:** [Details]
2. **[Learning]:** [Details]
3. **[Learning]:** [Details]

## Recommendations

1. [Recommendation for using schemas in AI prompts]
2. [Recommendation for validation coverage]
3. [Recommendation for error handling]
```

**Deliverable:** Complete validated system + documentation

-----
