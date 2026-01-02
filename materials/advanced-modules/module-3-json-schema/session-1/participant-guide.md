# **MODULE 3 SESSION 1: JSON Schema Fundamentals**

**Module:** Advanced Module 3: JSON Schema & Data Validation
**Session:** 1 of 2
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Module Navigation:** Session 1 | [Session 2 →](../session-2/participant-guide.md)

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
| 1 | Explain why JSON Schema is essential for AI workflow reliability | Workshop + All Exercises |
| 2 | Write basic JSON schemas with primitive types and constraints | Exercise 1.1 |
| 3 | Create schemas for objects and arrays with nested structures | Exercise 1.2 |
| 4 | Apply advanced constraints including enums and conditional validation | Exercise 1.3 |

---

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Block 2 Certification: AI Workflow Engineer (minimum)
- [ ] Comfortable reading and writing JSON
- [ ] Experience with `style.json` and data structures
- [ ] Working workflows using JSON data

**Not ready?** Review Block 1 JSON fundamentals or reach out in [support channel] for help.

---

## Key Concepts

### Concept 1: JSON Schema Purpose

**Definition:**
JSON Schema is a vocabulary that allows you to annotate and validate JSON documents. It defines the expected structure, types, and constraints for your data.

**Why It Matters:**
AI outputs are non-deterministic. Even with perfect prompts, AI may return data in unexpected formats. JSON Schema lets you validate data automatically, catching errors before they break your workflow.

**Core Principle:**
> Define expected structure once, validate everywhere. Fail fast with clear errors, not slow with mysterious bugs.

**Example:**
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "type": "object",
  "properties": {
    "name": { "type": "string" },
    "score": { "type": "number", "minimum": 0, "maximum": 100 }
  },
  "required": ["name", "score"]
}
```

This schema requires an object with a name (string) and score (number 0-100), both mandatory.

**Common Mistake:**
Assuming AI will always follow your requested format. Without validation, format variations cause silent failures or broken workflows.

---

### Concept 2: Schema Structure

**Definition:**
Every JSON Schema has standard metadata fields plus type-specific validation rules.

**Why It Matters:**
Understanding schema structure lets you read existing schemas and write new ones correctly.

**The Pattern:**
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "unique-identifier.json",
  "title": "Human-Readable Name",
  "description": "What this schema validates",
  "type": "object|array|string|number|...",
  [type-specific validation rules]
}
```

**When to Use:**
Every schema you write should follow this structure. The metadata makes schemas self-documenting.

**When NOT to Use:**
Don't skip metadata fields to save space - they're your documentation.

---

### Concept 3: Validation Constraints

**Definition:**
Constraints restrict what values are valid for each data type.

**Key Components:**

| Type | Common Constraints | Example |
|------|-------------------|---------|
| string | minLength, maxLength, pattern, format | `"format": "email"` |
| number | minimum, maximum, multipleOf | `"minimum": 0` |
| object | properties, required, additionalProperties | `"required": ["name"]` |
| array | items, minItems, maxItems, uniqueItems | `"minItems": 1` |

**Visual Reference:**
```
Schema Definition          Validation Result
      ↓                           ↓
┌──────────────────┐        ┌──────────────┐
│ type: "string"   │   →    │ "hello" ✓    │
│ format: "email"  │        │ "not-email" ✗│
└──────────────────┘        └──────────────┘
```

---

### Quick Reference: JSON Schema Essentials

**Primitive Types:**

| Type | Description | Example Value |
|------|-------------|---------------|
| string | Text | `"hello"` |
| number | Any number | `42`, `3.14` |
| integer | Whole numbers | `42` |
| boolean | True/false | `true` |
| null | Null | `null` |
| array | List | `[1, 2, 3]` |
| object | Key-value | `{"a": 1}` |

**Common Constraints:**

| Constraint | Applies To | Purpose |
|------------|-----------|---------|
| minLength / maxLength | string | Length limits |
| pattern | string | Regex match |
| format | string | Built-in formats (email, date, uri) |
| minimum / maximum | number | Range limits |
| multipleOf | number | Divisibility |
| required | object | Mandatory fields |
| additionalProperties | object | Allow/deny extra fields |
| items | array | Element schema |
| minItems / maxItems | array | Length limits |
| uniqueItems | array | No duplicates |
| enum | any | Allowed values |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Learning JSON Schema syntax to define and validate data structures for AI workflows

**Key Points from Each Segment:**

**Segment 1: Why JSON Schema?**
- AI outputs are non-deterministic - validation catches format variations
- Schemas define expected structure explicitly
- Validate at multiple points: inputs, AI outputs, inter-step data
- Fail fast with clear errors instead of silent corruption

**Segment 2: Schema Basics**
- Every schema has metadata: $schema, $id, title, description
- Seven primitive types: string, number, integer, boolean, null, array, object
- Strings constrained by length, pattern, or format
- Numbers constrained by range and precision

**Segment 3: Objects and Arrays**
- Objects use properties, required, and additionalProperties
- Set additionalProperties: false for strict validation
- Arrays use items to define element schemas
- Nest schemas to match data structure

**Segment 4: Advanced Constraints**
- Enums restrict to specific allowed values
- Conditional schemas (if/then) apply rules based on data
- Combining schemas (allOf, anyOf, oneOf) for complex logic

### Demo Recap

**What Was Demonstrated:**
Live validation using jsonschemavalidator.net showing how schemas catch invalid data

**Key Steps:**
1. Created simple email validation schema
2. Tested valid email - validation passed
3. Tested invalid email - validation failed with clear error message
4. Added length constraint - showed how multiple constraints work together

**Result:**
Demonstrated that validation gives immediate, actionable feedback when data doesn't match schema

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 1.1 | 20 min | 2 schema files + validation test results | Basic schemas, primitive types |
| 1.2 | 20 min | style-guide.schema.json + validated style.json | Nested objects, complex constraints |
| 1.3 | 20 min | Organized schema library with 5+ schemas | Reusable patterns, references |

---

### Exercise 1.1: Schema Basics Practice

**Duration:** 20 minutes

**Purpose:**
Practice writing basic schemas for common AI workflow data structures. You'll create schemas for workflow inputs and quality evaluation results, then validate them.

**You Will Create:**
- `workflow-input.schema.json` - Validates workflow trigger data
- `quality-result.schema.json` - Validates AI quality evaluation output
- Validation test results showing pass/fail for sample data

---

#### Instructions

**Step 1: Create workflow input schema**

Create a new file called `workflow-input.schema.json` with this content:

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

**Step 2: Create quality evaluation result schema**

Create `quality-result.schema.json`:

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

**Step 3: Test validation with online tool**

1. Go to https://www.jsonschemavalidator.net/
2. Paste your workflow-input schema in the Schema section
3. Test with valid data:
   ```json
   {
     "task_type": "proposal",
     "client_name": "Acme Corporation"
   }
   ```
4. Test with invalid data (missing required field):
   ```json
   {
     "client_name": "Acme Corporation"
   }
   ```
5. Test with invalid data (wrong enum value):
   ```json
   {
     "task_type": "invalid",
     "client_name": "Acme Corporation"
   }
   ```
6. Repeat for quality-result schema

**Step 4: Document test results**

Create a file called `validation-tests.md` documenting what you tested and the results.

**Step 5: Review Your Work**

Check that your deliverables include:
- [ ] `workflow-input.schema.json` with all required fields
- [ ] `quality-result.schema.json` with nested structure
- [ ] Validation test results for both schemas
- [ ] Test cases for valid and invalid data

---

#### Deliverable Specification

**File Names:**
- `workflow-input.schema.json`
- `quality-result.schema.json`
- `validation-tests.md`

**Location:** Create a `/schemas` folder in your project directory

**Format Requirements:**
- Valid JSON (use validator to verify)
- Includes $schema, $id, title, description
- Appropriate constraints for each field
- Required fields specified

**Quality Criteria:**
- [ ] Schemas validate successfully in online tool
- [ ] Test cases cover valid and invalid data
- [ ] Appropriate constraints for each data type
- [ ] Clear descriptions for documentation

---

#### Example

**Scenario:** Validating a workflow input

**Input - Valid:**
```json
{
  "task_type": "proposal",
  "client_name": "Acme Corporation",
  "priority": "high",
  "deadline": "2026-02-15"
}
```
**Result:** ✓ Validation passes

**Input - Invalid:**
```json
{
  "task_type": "invalid_type",
  "client_name": "Acme Corporation"
}
```
**Result:** ✗ Validation fails - task_type must be one of: proposal, assessment, report

**Why This Works:**
The enum constraint catches the invalid task_type value and provides a clear error message listing allowed values.

---

#### Tips & Troubleshooting

**Tips:**
- Use the online validator constantly while building schemas
- Test with both valid and invalid data
- Read error messages carefully - they tell you exactly what's wrong
- Start simple, add constraints incrementally

**Common Issues:**

| Problem | Solution |
|---------|----------|
| "Invalid JSON" error | Check for missing commas, quotes, or brackets |
| Schema accepts invalid data | Add more specific constraints (enum, format, minimum) |
| Schema rejects valid data | Check if constraints are too strict |
| patternProperties confusing | This validates object properties with dynamic names |

---

### Exercise 1.2: Complex Schema Design

**Duration:** 20 minutes

**Purpose:**
Practice creating schemas for complex nested structures. You'll schema-validate your `style.json` file, handling nested objects and arrays.

**You Will Create:**
- `style-guide.schema.json` - Complete schema for style configuration
- Validated `style.json` file

---

#### Instructions

**Step 1: Create the style guide schema**

Create `style-guide.schema.json`:

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

**Step 2: Validate your existing style.json**

If you have an existing `style.json` from Block 2:
1. Use the online validator to test it against this schema
2. Note any validation errors
3. Fix your style.json to match the schema

If you don't have a `style.json`, create one that matches this schema.

**Step 3: Extend schema for your needs**

Add properties specific to your workflow:
- Additional brand fields you use
- Custom tone settings
- Workflow-specific standards

**Step 4: Review Your Work**

Check that your deliverable includes:
- [ ] `style-guide.schema.json` with complete structure
- [ ] Validated `style.json` file
- [ ] Any extensions you added documented

---

#### Deliverable Specification

**File Names:**
- `style-guide.schema.json`
- `style.json` (validated)

**Location:** `/schemas/config/` folder

**Format Requirements:**
- Nested object structure properly defined
- Array constraints specified
- Pattern validation for colors
- Enum for formality and date format

**Quality Criteria:**
- [ ] Schema validates your style.json successfully
- [ ] All nested objects properly structured
- [ ] Constraints appropriate for each field
- [ ] Extensions documented if added

---

#### Example

**Valid style.json:**
```json
{
  "brand": {
    "name": "Acme Consulting",
    "tagline": "Excellence in Action",
    "primary_color": "#0066CC",
    "fonts": {
      "primary": "Arial"
    }
  },
  "tone": {
    "descriptors": ["professional", "clear", "confident"],
    "formality": "professional"
  }
}
```
**Result:** ✓ Validation passes - all required fields present and valid

---

### Exercise 1.3: Schema Library Setup

**Duration:** 20 minutes

**Purpose:**
Organize your schemas into a reusable library with base types and proper structure. This sets you up for Session 2 where you'll use these schemas in workflows.

**You Will Create:**
- Organized schema library folder structure
- `base-types.schema.json` with reusable definitions
- Example schema using references
- `README.md` documenting the library

---

#### Instructions

**Step 1: Create schema library structure**

Create this folder structure:

```
/schemas
  /common
    base-types.schema.json
  /inputs
    workflow-input.schema.json
    (move from Exercise 1.1)
  /outputs
    quality-result.schema.json
    (move from Exercise 1.1)
  /config
    style-guide.schema.json
    (move from Exercise 1.2)
  README.md
```

**Step 2: Create base types schema**

Create `/schemas/common/base-types.schema.json`:

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "base-types.schema.json",
  "title": "Common Type Definitions",
  "description": "Reusable type definitions for AI workflow schemas",

  "$defs": {
    "uuid": {
      "type": "string",
      "pattern": "^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$",
      "description": "UUID v4 format"
    },
    "timestamp": {
      "type": "string",
      "format": "date-time",
      "description": "ISO 8601 timestamp"
    },
    "score": {
      "type": "number",
      "minimum": 0,
      "maximum": 5,
      "description": "Quality score 0-5"
    },
    "status": {
      "type": "string",
      "enum": ["pending", "in_progress", "completed", "failed"],
      "description": "Workflow execution status"
    },
    "priority": {
      "type": "string",
      "enum": ["low", "normal", "high", "critical"],
      "description": "Task priority level"
    }
  }
}
```

**Step 3: Create schema using references**

Create `/schemas/inputs/workflow-execution.schema.json`:

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "workflow-execution.schema.json",
  "title": "Workflow Execution Record",
  "description": "Tracks a single workflow execution",

  "type": "object",
  "properties": {
    "id": {
      "$ref": "../common/base-types.schema.json#/$defs/uuid",
      "description": "Unique execution ID"
    },
    "started_at": {
      "$ref": "../common/base-types.schema.json#/$defs/timestamp",
      "description": "When execution started"
    },
    "status": {
      "$ref": "../common/base-types.schema.json#/$defs/status",
      "description": "Current execution status"
    },
    "quality_score": {
      "$ref": "../common/base-types.schema.json#/$defs/score",
      "description": "Final quality score"
    }
  },
  "required": ["id", "started_at", "status"]
}
```

**Step 4: Create README**

Create `/schemas/README.md`:

```markdown
# Schema Library

## Overview
This library contains JSON schemas that define data contracts for AI workflows.

## Organization

### Common Types (common/)
- `base-types.schema.json` - Reusable type definitions (UUID, timestamp, score, status, priority)

### Input Schemas (inputs/)
- `workflow-input.schema.json` - Workflow trigger data validation
- `workflow-execution.schema.json` - Execution tracking data

### Output Schemas (outputs/)
- `quality-result.schema.json` - Quality evaluation output format

### Config Schemas (config/)
- `style-guide.schema.json` - Brand and style configuration

## Usage

### Validating Data
Use any JSON Schema validator that supports Draft 2020-12:
- Online: https://www.jsonschemavalidator.net/
- JavaScript: ajv library
- Python: jsonschema library

### Referencing Base Types
Use `$ref` to reference common types:
```json
{
  "properties": {
    "id": { "$ref": "../common/base-types.schema.json#/$defs/uuid" }
  }
}
```

## Validation
All schemas validated with Draft 2020-12 specification.

## Version
1.0 - Initial library
```

**Step 5: Review Your Work**

Check that your deliverable includes:
- [ ] Organized folder structure
- [ ] Base types schema with reusable definitions
- [ ] At least 5 total schemas in the library
- [ ] Example schema using $ref
- [ ] README documenting the library

---

#### Deliverable Specification

**Folder Structure:** `/schemas` with organized subfolders

**Format Requirements:**
- Consistent $schema version across all schemas
- Base types in $defs for reuse
- Proper use of $ref for references
- README with usage instructions

**Quality Criteria:**
- [ ] Library well-organized by category
- [ ] Base types cover common workflow needs
- [ ] References work correctly
- [ ] README clear and complete

---

#### Tips & Troubleshooting

**Tips:**
- Start with base types - identify patterns you use repeatedly
- Use relative paths in $ref for portability
- Keep README updated as you add schemas
- Validate schemas with references using online tools that support $ref

**Common Issues:**

| Problem | Solution |
|---------|----------|
| $ref not resolving | Check relative path, ensure base schema is valid |
| Duplicate definitions | Move to base-types.schema.json |
| Library getting messy | Reorganize by input/output/config categories |
| Can't decide what's "common" | If used 2+ times, make it a base type |

---

## Templates & Resources

### Templates Provided This Session

| Template | Purpose | Location |
|----------|---------|----------|
| workflow-input.schema.json | Workflow trigger validation | Exercise 1.1 |
| quality-result.schema.json | AI output validation | Exercise 1.1 |
| style-guide.schema.json | Style configuration | Exercise 1.2 |
| base-types.schema.json | Reusable type library | Exercise 1.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| JSON Schema Official Docs | Documentation | https://json-schema.org/ | Reference for all schema syntax |
| JSON Schema Validator | Online Tool | https://www.jsonschemavalidator.net/ | Test schemas during development |
| JSON Schema Lint | Online Tool | https://jsonschemalint.com/ | Alternative validator |
| Understanding JSON Schema | Tutorial | https://json-schema.org/understanding-json-schema/ | Learning resource |

---

### Module Appendix References

For this session's exercises, reference:

- **Appendix A:** JSON Schema Quick Reference - All constraint types on one page
- **Appendix B:** Validation Tools - Tools for different platforms and languages

See the main module document ([Module 3](../module-3-json-schema.md)) for full appendix content.

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next session, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Explain why JSON Schema is essential | Understanding of validation benefits | ☐ |
| 2 | Write basic schemas with constraints | Exercise 1.1 completed | ☐ |
| 3 | Create schemas for nested structures | Exercise 1.2 completed | ☐ |
| 4 | Apply advanced constraints | Exercise 1.3 completed | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Workflow input schema | `workflow-input.schema.json` | `/schemas/inputs/` | ☐ |
| Quality result schema | `quality-result.schema.json` | `/schemas/outputs/` | ☐ |
| Style guide schema | `style-guide.schema.json` | `/schemas/config/` | ☐ |
| Base types schema | `base-types.schema.json` | `/schemas/common/` | ☐ |
| Schema library README | `README.md` | `/schemas/` | ☐ |
| Validation tests | `validation-tests.md` | `/schemas/` | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** What concept or technique suddenly made sense?

2. **What's still fuzzy?** What do you need more practice or clarification on?

3. **How will you apply this?** Name one real workflow where you'll add validation.

4. **What surprised you?** Was anything harder or easier than expected?

[Optional: Share insights in [support channel] to help your peers]

---

## Getting Help

### Quick Answers
- **[Support Channel]** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Tag your cohort for quick tips

### Common Questions This Session

**Q: My schema validates successfully but seems too permissive - it accepts data I didn't expect.**
A: Check your constraints. Common issues: missing `additionalProperties: false`, missing `required` fields, or constraints that are too loose. Test with intentionally invalid data.

**Q: I'm getting "Invalid JSON" errors but my JSON looks correct.**
A: Common culprits: trailing commas (not allowed in JSON), single quotes instead of double quotes, or missing quotes around property names. Use a JSON formatter to find the issue.

**Q: What's the difference between `minimum: 0` and `exclusiveMinimum: 0`?**
A: `minimum: 0` allows 0 or greater. `exclusiveMinimum: 0` requires greater than 0 (not equal to). Use `minimum` for "at least" and `exclusiveMinimum` for "more than".

**Q: Should I validate my style.json with a schema?**
A: Yes! Even configuration files benefit from validation. It catches typos and ensures your style.json has all required fields before workflows try to use it.

**Q: How do I know if my constraints are too strict or too loose?**
A: Test with real data. If valid data is rejected, constraints are too strict. If invalid data passes, they're too loose. Start loose and tighten based on actual validation failures.

### When to Ask for Help

- **Before asking:** Check the JSON Schema official docs and this guide's troubleshooting sections
- **Good to ask:** "I tried [X] but got [Y] result. Here's my schema..."
- **Include:** Your schema, test data, and the validation error message

### Office Hours

[If applicable]
- **When:** [Day/Time]
- **Where:** [Platform/Link]
- **For:** Live troubleshooting and deeper questions

---

## Looking Ahead

### Next Session Preview: Session 2 - Validation in Practice

**Focus:**
Session 2 covers implementing validation in real workflows - runtime validation, error handling, and the module capstone.

**How It Builds on This Session:**
You'll take the schema library you created this session and integrate it into actual workflows. You'll learn where to validate, how to handle errors, and build a complete validated workflow system.

**To Prepare:**
- [ ] Complete all Session 1 exercises
- [ ] Have your schema library organized and tested
- [ ] Identify one workflow where you'll implement validation

---

## Glossary

| Term | Definition |
|------|------------|
| JSON Schema | A vocabulary for annotating and validating JSON documents |
| $schema | Property specifying which JSON Schema version to use |
| $id | Unique identifier for a schema |
| $ref | Reference to another schema or definition |
| $defs | Section containing reusable schema definitions |
| additionalProperties | Controls whether extra properties are allowed in objects |
| enum | Constraint restricting values to a specific set |
| format | Built-in string format validators (email, date, uri, etc.) |
| patternProperties | Validates object properties with dynamic names using regex patterns |
| allOf / anyOf / oneOf | Schema combination operators for complex validation logic |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial guide created |

---

**Navigation:** Session 1 | [Session 2 →](../session-2/participant-guide.md)

---

**END OF PARTICIPANT GUIDE - SESSION 1**
