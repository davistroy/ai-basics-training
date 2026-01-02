# **Session 1: JSON Schema Fundamentals**

**Advanced Module 3: JSON Schema & Data Validation**
**Session:** 1 of 2
**Duration:** 45 min live + 60 min homework

---

## **Entry Criteria**

- [ ] Comfortable reading and writing JSON
- [ ] `style.json` created and used
- [ ] Workflows handling JSON data
- [ ] Understanding of data types

## **Exit Criteria**

- [ ] JSON Schema syntax mastered
- [ ] Schemas created for core data types
- [ ] Validation tools configured
- [ ] 5+ schemas written and tested

-----

## **Workshop Content (45 minutes)**

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

## **Self-Paced Exercises (60 minutes total)**

### **Exercise 1.1: Schema Basics Practice (20 minutes)**

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

### **Exercise 1.2: Complex Schema Design (20 minutes)**

*Create schema for your `style.json`*

> **Note:** If you don't have an existing `style.json` from Block 2, you can use the schema provided below to create one from scratch, or use the Block 1 appendix example as a starting point.

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
1. Validate your existing `style.json` against this schema
2. Fix any validation errors
3. Extend schema for your specific needs

**Deliverable:** `style-guide.schema.json` + validated `style.json`

-----

### **Exercise 1.3: Schema Library Setup (20 minutes)**

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
