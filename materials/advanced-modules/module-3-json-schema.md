# **Advanced Module 3: JSON Schema & Data Validation**

## **2 Weeks | 45 min live + 60 min homework per week**

-----

## **Prerequisites**

- Block 2 Certification: AI Workflow Engineer (minimum)
- Understanding of JSON fundamentals from Block 1
- Experience with style.json and data structures
- Working workflows using JSON data

-----

## **Module Overview**

**Target Audience:** Block 2+ graduates who want to implement robust data validation in their AI workflows using JSON Schema, ensuring consistent, reliable data handling.

**Learning Objectives:**
- Master JSON Schema specification and syntax
- Create schemas for AI workflow data structures
- Implement validation in automation workflows
- Design self-documenting API contracts
- Build reusable schema libraries

**Capstone:** Validated Workflow System
- Schema library for all workflow data types
- Runtime validation implementation
- Schema-based documentation
- Error handling for validation failures

-----

## **Week 1: JSON Schema Fundamentals**

### **Entry Criteria**

- [ ] Comfortable reading and writing JSON
- [ ] style.json created and used
- [ ] Workflows handling JSON data
- [ ] Understanding of data types

### **Exit Criteria**

- [ ] JSON Schema syntax mastered
- [ ] Schemas created for core data types
- [ ] Validation tools configured
- [ ] 5+ schemas written and tested

-----

### **Workshop Content (45 minutes)**

**Segment 1: Why JSON Schema? (10 min)**

- **The problem without validation:**
  - AI returns unexpected formats
  - Workflows break on missing fields
  - Silent data corruption
  - Difficult debugging

- **JSON Schema benefits:**
  - Define expected structure explicitly
  - Validate data at runtime
  - Self-documenting formats
  - Catch errors early
  - Consistent across team

- **Use cases in AI workflows:**
  - Validate AI output format
  - Validate workflow inputs
  - Document data contracts
  - Generate example data

**Segment 2: Schema Basics (15 min)**

- **Basic schema structure:**
  ```json
  {
    "$schema": "https://json-schema.org/draft/2020-12/schema",
    "$id": "https://example.com/my-schema.json",
    "title": "My Data Type",
    "description": "Description of what this represents",
    "type": "object",
    "properties": {
      "field1": { "type": "string" },
      "field2": { "type": "number" }
    },
    "required": ["field1"]
  }
  ```

- **Primitive types:**
  - `string` - text values
  - `number` - any number (integer or float)
  - `integer` - whole numbers only
  - `boolean` - true/false
  - `null` - null value
  - `array` - ordered list
  - `object` - key-value structure

- **String constraints:**
  ```json
  {
    "type": "string",
    "minLength": 1,
    "maxLength": 100,
    "pattern": "^[A-Z][a-z]+$",
    "format": "email"
  }
  ```

- **Number constraints:**
  ```json
  {
    "type": "number",
    "minimum": 0,
    "maximum": 100,
    "multipleOf": 0.5
  }
  ```

**Segment 3: Objects and Arrays (12 min)**

- **Object schemas:**
  ```json
  {
    "type": "object",
    "properties": {
      "name": { "type": "string" },
      "age": { "type": "integer", "minimum": 0 }
    },
    "required": ["name"],
    "additionalProperties": false
  }
  ```

- **Array schemas:**
  ```json
  {
    "type": "array",
    "items": { "type": "string" },
    "minItems": 1,
    "maxItems": 10,
    "uniqueItems": true
  }
  ```

- **Nested structures:**
  ```json
  {
    "type": "object",
    "properties": {
      "client": {
        "type": "object",
        "properties": {
          "name": { "type": "string" },
          "contacts": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "email": { "type": "string", "format": "email" }
              }
            }
          }
        }
      }
    }
  }
  ```

**Segment 4: Advanced Constraints (8 min)**

- **Enums (allowed values):**
  ```json
  {
    "type": "string",
    "enum": ["draft", "review", "published"]
  }
  ```

- **Conditional schemas:**
  ```json
  {
    "if": {
      "properties": { "type": { "const": "business" } }
    },
    "then": {
      "required": ["company_name"]
    }
  }
  ```

- **Combining schemas:**
  - `allOf` - must match all
  - `anyOf` - must match at least one
  - `oneOf` - must match exactly one
  - `not` - must not match

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 1.1: Schema Basics Practice (20 minutes)**

*Create schemas for simple data types*

1. **Create schema for workflow input:**

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "workflow-input.schema.json",
  "title": "Workflow Input",
  "description": "Input data for AI workflow execution",
  "type": "object",
  "properties": {
    "task_type": {
      "type": "string",
      "enum": ["proposal", "assessment", "report"],
      "description": "Type of deliverable to generate"
    },
    "client_name": {
      "type": "string",
      "minLength": 1,
      "maxLength": 200,
      "description": "Client's full legal name"
    },
    "priority": {
      "type": "string",
      "enum": ["low", "normal", "high", "urgent"],
      "default": "normal"
    },
    "deadline": {
      "type": "string",
      "format": "date",
      "description": "Due date in YYYY-MM-DD format"
    },
    "context": {
      "type": "string",
      "maxLength": 5000,
      "description": "Additional context for the task"
    }
  },
  "required": ["task_type", "client_name"],
  "additionalProperties": false
}
```

2. **Create schema for quality evaluation result:**

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "quality-result.schema.json",
  "title": "Quality Evaluation Result",
  "description": "Output from quality evaluation prompt",
  "type": "object",
  "properties": {
    "scores": {
      "type": "object",
      "patternProperties": {
        "^[a-z_]+$": {
          "type": "object",
          "properties": {
            "score": {
              "type": "integer",
              "minimum": 1,
              "maximum": 5
            },
            "reason": {
              "type": "string",
              "minLength": 10
            }
          },
          "required": ["score", "reason"]
        }
      }
    },
    "overall_score": {
      "type": "number",
      "minimum": 1,
      "maximum": 5
    },
    "pass": {
      "type": "boolean"
    },
    "suggestions": {
      "type": "array",
      "items": { "type": "string" },
      "maxItems": 5
    }
  },
  "required": ["scores", "overall_score", "pass"]
}
```

3. **Validate with online tool:**
   - Use https://www.jsonschemavalidator.net/
   - Test valid and invalid examples

**Deliverable:** 2 schema files + validation test results

-----

**Exercise 1.2: Complex Schema Design (20 minutes)**

*Create schema for your style.json*

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "style-guide.schema.json",
  "title": "Style Guide Configuration",
  "description": "Brand and style configuration for AI-generated content",

  "type": "object",
  "properties": {
    "brand": {
      "type": "object",
      "properties": {
        "name": {
          "type": "string",
          "minLength": 1
        },
        "tagline": { "type": "string" },
        "primary_color": {
          "type": "string",
          "pattern": "^#[0-9A-Fa-f]{6}$"
        },
        "secondary_color": {
          "type": "string",
          "pattern": "^#[0-9A-Fa-f]{6}$"
        },
        "fonts": {
          "type": "object",
          "properties": {
            "primary": { "type": "string" },
            "secondary": { "type": "string" }
          },
          "required": ["primary"]
        }
      },
      "required": ["name"]
    },

    "tone": {
      "type": "object",
      "properties": {
        "descriptors": {
          "type": "array",
          "items": { "type": "string" },
          "minItems": 1,
          "maxItems": 7
        },
        "avoid": {
          "type": "array",
          "items": { "type": "string" }
        },
        "formality": {
          "type": "string",
          "enum": ["casual", "professional", "formal", "academic"]
        }
      },
      "required": ["descriptors"]
    },

    "document_standards": {
      "type": "object",
      "properties": {
        "page_numbers": { "type": "boolean" },
        "date_format": {
          "type": "string",
          "enum": ["YYYY-MM-DD", "MM/DD/YYYY", "DD/MM/YYYY"]
        },
        "currency": { "type": "string" }
      }
    },

    "metadata": {
      "type": "object",
      "properties": {
        "version": { "type": "string" },
        "last_updated": {
          "type": "string",
          "format": "date"
        },
        "owner": { "type": "string" }
      }
    }
  },

  "required": ["brand", "tone"]
}
```

**Tasks:**
1. Validate your existing style.json against this schema
2. Fix any validation errors
3. Extend schema for your specific needs

**Deliverable:** `style-guide.schema.json` + validated `style.json`

-----

**Exercise 1.3: Schema Library Setup (20 minutes)**

*Organize schemas for reuse*

1. **Create schema library structure:**

```
/schemas
  /common
    base-types.schema.json     # Reusable type definitions
  /inputs
    workflow-input.schema.json
    task-request.schema.json
  /outputs
    quality-result.schema.json
    agent-response.schema.json
  /config
    style-guide.schema.json
    workflow-config.schema.json
  README.md
```

2. **Create base types schema:**

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "base-types.schema.json",
  "title": "Common Type Definitions",

  "$defs": {
    "uuid": {
      "type": "string",
      "pattern": "^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$"
    },
    "timestamp": {
      "type": "string",
      "format": "date-time"
    },
    "score": {
      "type": "number",
      "minimum": 0,
      "maximum": 5
    },
    "status": {
      "type": "string",
      "enum": ["pending", "in_progress", "completed", "failed"]
    },
    "priority": {
      "type": "string",
      "enum": ["low", "normal", "high", "critical"]
    }
  }
}
```

3. **Reference in other schemas:**

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "workflow-execution.schema.json",

  "type": "object",
  "properties": {
    "id": { "$ref": "base-types.schema.json#/$defs/uuid" },
    "started_at": { "$ref": "base-types.schema.json#/$defs/timestamp" },
    "status": { "$ref": "base-types.schema.json#/$defs/status" },
    "quality_score": { "$ref": "base-types.schema.json#/$defs/score" }
  }
}
```

4. **Create README:**

```markdown
# Schema Library

## Usage
These schemas define data contracts for AI workflows.

## Schemas

### Common Types (common/)
- `base-types.schema.json` - Reusable primitives

### Input Schemas (inputs/)
- `workflow-input.schema.json` - Workflow trigger data

### Output Schemas (outputs/)
- `quality-result.schema.json` - Quality evaluation format

### Config Schemas (config/)
- `style-guide.schema.json` - Brand/style configuration

## Validation
Use any JSON Schema validator (Draft 2020-12).
```

**Deliverable:** Organized schema library with 5+ schemas

-----

## **Week 2: Validation in Practice**

### **Entry Criteria**

- [ ] 5+ schemas created
- [ ] Schema library organized
- [ ] Understanding of schema syntax
- [ ] Validation tools identified

### **Exit Criteria**

- [ ] Runtime validation implemented in workflows
- [ ] AI output validation working
- [ ] Error handling for validation failures
- [ ] Schema documentation generated
- [ ] Module capstone completed

-----

### **Workshop Content (45 minutes)**

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

### **Self-Paced Exercises (60 minutes total)**

**Exercise 2.1: Workflow Validation (20 minutes)**

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

**Exercise 2.2: Validation Error Handling (20 minutes)**

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

**Exercise 2.3: Module Capstone - Validated System (20 minutes)**

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

# **APPENDICES**

## **Appendix A: JSON Schema Quick Reference**

```markdown
# JSON Schema Cheat Sheet

## Types
- string, number, integer, boolean, null, array, object

## String Constraints
- minLength, maxLength
- pattern (regex)
- format: date, time, date-time, email, uri, uuid

## Number Constraints
- minimum, maximum
- exclusiveMinimum, exclusiveMaximum
- multipleOf

## Array Constraints
- items (schema for all items)
- minItems, maxItems
- uniqueItems

## Object Constraints
- properties
- required (array of required property names)
- additionalProperties (true/false/schema)
- patternProperties

## Combining
- allOf, anyOf, oneOf, not

## Conditionals
- if/then/else

## References
- $ref: "other.schema.json#/$defs/typeName"
- $defs: { "typeName": { schema } }
```

-----

## **Appendix B: Validation Tools**

```markdown
# Recommended Validation Tools

## Online Validators
- https://www.jsonschemavalidator.net/
- https://jsonschemalint.com/

## JavaScript/Node.js
- ajv (Fastest, most popular)
- zod (TypeScript-first)
- joi (Expressive, Hapi ecosystem)

## Python
- jsonschema (Reference implementation)
- pydantic (Popular, Python-native)

## Make.com
- JSON module with schema validation
- Filter after JSON parse

## n8n
- Function node with ajv
- Custom validation node

## CLI Tools
- ajv-cli
- jsonschema (Python CLI)
```

-----

## **Appendix C: Module Evaluation Rubric**

```markdown
# JSON Schema & Data Validation - Evaluation Rubric

**Total Points: 20 (4 criteria × 5 points each)**

## Criterion 1: Schema Quality (5 points)

| Score | Description |
|-------|-------------|
| 5 | Comprehensive schemas with proper constraints, documentation, and reusable patterns. Well-organized library. |
| 4 | Good schemas with most constraints. Organized. |
| 3 | Basic schemas working. Some organization. |
| 2 | Minimal schemas. Poor organization. |
| 1 | No usable schemas. |

## Criterion 2: Validation Implementation (5 points)

| Score | Description |
|-------|-------------|
| 5 | Validation at all key points. Working correctly. Integrated into workflow. |
| 4 | Good validation coverage. Working well. |
| 3 | Basic validation at some points. |
| 2 | Limited validation. Not working consistently. |
| 1 | No validation implemented. |

## Criterion 3: Error Handling (5 points)

| Score | Description |
|-------|-------------|
| 5 | Comprehensive error handling. Recovery strategies. Clear messages. Good logging. |
| 4 | Good error handling. Some recovery. |
| 3 | Basic error handling. |
| 2 | Poor error handling. |
| 1 | No error handling. |

## Criterion 4: Documentation (5 points)

| Score | Description |
|-------|-------------|
| 5 | Well-documented schemas. Generated documentation. Clear usage guide. |
| 4 | Good documentation. |
| 3 | Basic documentation. |
| 2 | Limited documentation. |
| 1 | No documentation. |
```

-----

**END OF ADVANCED MODULE 3**
