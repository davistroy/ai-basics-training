# **POWERPOINT PRESENTATION: MODULE 3 SESSION 1**
## **JSON Schema Fundamentals**

**Module:** Advanced Module 3: JSON Schema & Data Validation
**Session Number:** 1 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 2+ graduates who want to implement robust data validation in their AI workflows

**Key Thesis:** JSON Schema transforms unpredictable AI outputs into reliable, validated data structures by defining precise contracts for JSON data—enabling workflows to fail fast with clear errors rather than propagating malformed data, while giving AI models explicit specifications that improve output quality and consistency.

**Session Learning Objectives:** By the end of this session, participants will:
1. Explain why JSON Schema is essential for AI workflow reliability
2. Write basic JSON schemas with primitive types and constraints
3. Create schemas for objects and arrays with nested structures
4. Apply advanced constraints including enums and conditional validation

**Entry Criteria:** (What participants should have before this session)
- [ ] Comfortable reading and writing JSON
- [ ] `style.json` created and used
- [ ] Workflows handling JSON data
- [ ] Understanding of data types

**Exit Criteria:** (What participants should be able to do after this session)
- [ ] JSON Schema syntax mastered
- [ ] Schemas created for core data types
- [ ] Validation tools configured
- [ ] 5+ schemas written and tested

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Why JSON Schema? (10 min) - Slides 4-6
3. Segment 2: Schema Basics (15 min) - Slides 7-11
4. Segment 3: Objects and Arrays (12 min) - Slides 12-15
5. Segment 4: Advanced Constraints (8 min) - Slides 16-18
6. Homework Preview & Close (3 min) - Slides 19-21

**Total Slides:** 21

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Module 3 Session 1: JSON Schema Fundamentals

**Subtitle:** Building Reliable AI Workflows with Data Validation

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program
- Advanced Module 3

**Graphic:** Clean title slide with program branding. Orange tones (Block 2-level, building/engineering theme)

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Session 1 of Advanced Module 3: JSON Schema and Data Validation. Today we're focusing on JSON Schema fundamentals - the foundation for building reliable, robust AI workflows.

This is an advanced module designed for those of you who have completed Block 2 and are already working with AI workflows. You've experienced the pain of AI outputs that don't match what you expected, workflows that break because of missing fields, and debugging sessions where you can't figure out what went wrong.

Today we're going to solve those problems with JSON Schema - a powerful tool that lets you define exactly what your data should look like and validate it automatically.

By the end of our 45 minutes together, you'll be able to write schemas for your workflow data and validate both inputs and AI outputs."

[Transition: Click to next slide]

---

### SLIDE 2: WEEK OVERVIEW

**Title:** This Session's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Welcome & Preview |
| 3-13 min | Segment 1 | Why JSON Schema? |
| 13-28 min | Segment 2 | Schema Basics |
| 28-40 min | Segment 3 | Objects and Arrays |
| 40-48 min | Segment 4 | Advanced Constraints |
| 48-51 min | Close | Homework & Resources |

**Graphic:** Simple timeline or agenda visual showing the session flow

**SPEAKER NOTES:**

"Here's what we'll cover today:

First, we'll explore why JSON Schema matters - what problems it solves and how it makes your AI workflows more reliable.

Then, we'll dive into schema basics - the fundamental syntax and how to define primitive types with constraints.

In our third segment, we'll tackle objects and arrays, including nested structures - this is where schemas become really powerful for complex workflow data.

And we'll close with advanced constraints - enums, conditionals, and schema combinations that handle sophisticated validation rules.

[Pause]

Any questions before we dive in?"

[Transition]

---

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Explain why JSON Schema is essential for AI workflow reliability**
   - Understand the problems validation solves

2. **Write basic JSON schemas with primitive types and constraints**
   - Define strings, numbers, booleans with validation rules

3. **Create schemas for objects and arrays with nested structures**
   - Handle complex workflow data structures

4. **Apply advanced constraints including enums and conditional validation**
   - Implement sophisticated validation logic

**Graphic:** Checklist or milestone visual - objectives as checkboxes participants will "complete"

**SPEAKER NOTES:**

"These are our four objectives for today. By the time you leave this session, you'll be able to:

[Read each objective, pausing briefly after each]

Notice that these are all ACTION-focused. This isn't about knowing what JSON Schema is - it's about WRITING schemas and USING them in your workflows. You'll practice each of these in your homework exercises.

[Point to first objective]

This one is critical because if you don't understand WHY you need validation, you won't use it consistently. We'll see real examples of what goes wrong without schemas.

Let's get started."

[Transition: Click to Segment 1]

---

## SEGMENT 1: WHY JSON SCHEMA?
### Duration: 10 minutes | Slides 4-6

---

### SLIDE 4: SEGMENT 1 - THE PROBLEM

**Title:** What Goes Wrong Without Validation?

**Content:**

**The Pain Points:**
- AI returns unexpected formats - your parser breaks
- Workflows fail on missing required fields
- Silent data corruption - wrong types accepted
- Hours of debugging to find data issues

**Real Impact:**
- Workflows that worked yesterday fail today
- Client deliverables delayed
- Lost trust in automation

**Graphic:** Visual showing a workflow breaking - perhaps a flow diagram with an X or error symbol where validation should be

**GRAPHICS:**

**Graphic 1: Workflow Failure Cascade**
- Purpose: Show how missing validation causes workflow failures
- Type: Annotated flowchart with error indicators
- Elements: Workflow steps (Input → AI Generate → Parse → Use Data → Output) with an X or explosion icon at the "Parse" step
- Labels: "Expected: {name, score}", "Got: {rating, confidence}", "Parser Crash"
- Relationships: Red arrows showing failure propagating downstream; include annotation "Without validation, failures happen late in the process"

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Let me ask you a question: How many of you have had an AI workflow break because the AI's response was in a different format than you expected?

[Pause - let question land - show of hands]

[Personal story or common scenario]

The reality is that AI outputs are non-deterministic. You ask for JSON with specific fields, and the AI might give you those fields... or it might not. Or it might give you a string where you expected a number. Or add extra fields you didn't ask for.

[Point to graphic]

This is what happens: your workflow expects field A, the AI gives you field B instead, and everything breaks. And the worst part? You often don't find out until you're reviewing the final output - or worse, after it's been delivered to a client.

Today we're going to solve this. Here's how..."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide establishes the "why" before the "how"
- Creates emotional buy-in for the solution that follows
- Connects abstract concepts to real consulting pain points
- Sets up the value proposition for JSON Schema

**Q&A Preparation:**
- *"Is this really that big of a problem?"*: Yes - even a 5% failure rate means 1 in 20 workflow executions breaks, which is unacceptable for professional deliverables
- *"I've never experienced this issue"*: You may not have noticed it yet, but check your workflow logs - you'll likely find AI outputs that don't match your expected format

---

### SLIDE 5: SEGMENT 1 - THE SOLUTION

**Title:** The Solution: JSON Schema

**Content:**

**Core Principle:** Define expected data structure once, validate everywhere

**JSON Schema Benefits:**
1. Define structure explicitly - no ambiguity
2. Validate at runtime - catch errors early
3. Self-documenting - schema IS the documentation
4. Consistent across team - everyone uses same contracts

**Key Benefit:** Workflows fail fast with clear error messages, not silently with bad data

**Graphic:** Before/after comparison:
- Before: AI → Process → ??? → Maybe works
- After: AI → Validate → Pass/Fail → Process (only valid data)

**GRAPHICS:**

**Graphic 1: Before/After Validation Comparison**
- Purpose: Contrast workflows with and without validation
- Type: Side-by-side flowcharts
- Elements:
  - LEFT (Before): AI → Process → Output with question marks and uncertainty clouds
  - RIGHT (After): AI → Schema Validation (diamond decision) → [Pass] Process → Output OR [Fail] Error Handler
- Labels: "Before: Hope it works", "After: Know it works", "Fail Fast", "Clear Errors"
- Relationships: Show uncertainty vs. confidence; highlight validation as a quality gate

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"The solution is JSON Schema - a standard way to define what your JSON data should look like.

Think of it like a contract. You write down exactly what fields you expect, what types they should be, which ones are required, and what constraints they must meet. Then you validate your data against that contract.

Let me break down how this works:

First, you define the structure explicitly in a schema file. No more assuming the AI will give you what you want - you write it down.

Second, you validate at runtime. Before your workflow processes data, you check it against the schema. If it doesn't match, you catch the error immediately.

Third, your schema becomes your documentation. Anyone can look at the schema and know exactly what the data should look like.

And fourth, when you share schemas across your team, everyone validates against the same contracts. Consistency everywhere.

[Point to graphic]

Notice the difference: without validation, you cross your fingers and hope it works. With validation, you KNOW it's correct before processing.

The key insight here is: fail fast with clear errors, not slow with mysterious bugs.

Let me show you what a schema looks like..."

[Transition to basics]

**BACKGROUND:**

**Key Research & Citations:**
- **JSON Schema Specification**: Official standard from json-schema.org, draft 2020-12
- **Industry Adoption**: Used by major APIs (OpenAPI), cloud providers, and enterprise systems

**Implementation Guidance:**

**Getting Started:**
- Start with simple schemas for critical data points
- Add validation to one workflow as proof of concept
- Expand to all workflow touch points

**Common Pitfalls:**
- Making schemas too strict (allow flexibility where needed)
- Not validating AI outputs (only validating inputs)
- Writing schemas manually without testing

---

### SLIDE 6: SEGMENT 1 - USE CASES

**Title:** JSON Schema in AI Workflows

**Content:**

**Where to Use Validation:**

1. **Validate workflow inputs**
   - Trigger data from forms, APIs, webhooks
   - Catch bad data before processing starts

2. **Validate AI outputs**
   - Ensure AI follows requested format
   - Retry or fix if validation fails

3. **Document data contracts**
   - Schema defines what data looks like
   - Team knows what to expect

4. **Generate example data**
   - Tools can create valid examples from schemas
   - Useful for testing

**Graphic:** Flow diagram showing validation points in a workflow

**GRAPHICS:**

**Graphic 1: Validation Points in AI Workflow**
- Purpose: Show where to apply validation in a complete workflow
- Type: Annotated flowchart with validation gates highlighted
- Elements: Form Input → [Validate 1] → AI Prompt → AI Generate → [Validate 2] → Process Result → [Validate 3] → Output
- Labels: "Validate 1: Input Data", "Validate 2: AI Output", "Validate 3: Final Result", each validation point as a shield icon
- Relationships: Validation points as quality gates; error paths branching from each validation to an error handler
- Visual Style: Validation points in different color (green shields) to stand out from process steps

**SPEAKER NOTES:**

"Let's look at specific places where you'll use JSON Schema in your AI workflows:

First, validate workflow inputs. When someone submits a form, or an API call triggers your workflow, validate that data immediately. If required fields are missing or types are wrong, reject it before you waste time processing.

Second - and this is critical - validate AI outputs. After the AI generates a response, validate it against your schema. If it doesn't match, you can retry with a more explicit prompt, attempt to fix the data, or escalate to human review.

Third, use schemas as documentation. Instead of a separate document describing your data format, the schema IS the documentation. It's always accurate because it's what you actually validate against.

Fourth, generate example data for testing. Many tools can create valid example data from schemas, which is incredibly useful for testing workflows without running AI generation.

[Pause]

Now let's get into the syntax. How do you actually write a schema?"

[Transition: Click to Segment 2]

---

## SEGMENT 2: SCHEMA BASICS
### Duration: 15 minutes | Slides 7-11

---

### SLIDE 7: SEGMENT 2 - BASIC STRUCTURE

**Title:** Anatomy of a JSON Schema

**Content:**

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

**Key Elements:**
- `$schema` - Which JSON Schema version
- `$id` - Unique identifier for this schema
- `title` & `description` - Documentation
- `type` - What kind of data (object, array, string, etc.)
- `properties` - For objects: what fields exist
- `required` - Which fields are mandatory

**Graphic:** Annotated schema with arrows pointing to each element

**GRAPHICS:**

**Graphic 1: Anatomy of JSON Schema**
- Purpose: Explain the key components of a schema structure
- Type: Annotated code diagram with callout boxes
- Elements: The schema code block with colored boxes/arrows pointing to each major section
- Labels:
  - "$schema" → "Specifies JSON Schema version"
  - "$id" → "Unique identifier (URL format)"
  - "title/description" → "Human-readable documentation"
  - "type" → "Data type being validated"
  - "properties" → "Field definitions"
  - "required" → "Mandatory fields array"
- Relationships: Group related elements (metadata at top, validation rules below)
- Visual Style: Use different colors for metadata vs. validation sections

**SPEAKER NOTES:**

"[INSIGHT - Core structure]"

"Here's what every JSON Schema looks like. Let me walk through each part:

At the top, `$schema` tells validators which version of the JSON Schema specification to use. Always use the latest: 2020-12.

`$id` is a unique identifier - usually a URL. Even if the URL doesn't point to a real file, it uniquely identifies this schema.

`title` and `description` are for humans. Make these clear because they become your documentation.

`type` defines what kind of data you're validating. In this case, it's an object - a key-value structure.

`properties` lists the fields in your object. Each property has its own mini-schema.

`required` is an array of field names that must be present. In this example, field1 is required but field2 is optional.

[Point to example]

This schema would accept:
```
{ "field1": "hello", "field2": 42 }
```

But reject:
```
{ "field2": 42 }  // missing required field1
```

Let's look at the different types you can validate..."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide provides the foundational mental model for all JSON Schema work - understanding schema structure is prerequisite to writing schemas
- Creates confidence that schemas are readable and understandable, not cryptic technical artifacts
- Establishes the core vocabulary ($schema, $id, type, properties, required) that will be used throughout the rest of the session

**Key Research & Citations:**
- **JSON Schema Specification (2020-12)**: Official standard from json-schema.org, widely adopted across industries
- **Schema Design Principles**: Schemas serve dual purpose as validation rules and documentation, reducing documentation drift

**Q&A Preparation:**
- *"Do I need to include $schema and $id in every schema?"*: $schema is best practice but not required. $id is optional but useful for referencing schemas and debugging validation errors
- *"Can I use comments in JSON Schema?"*: No, JSON doesn't support comments, but use "title" and "description" fields liberally for documentation
- *"What happens if I don't mark any fields as required?"*: The schema will validate objects with any combination of the properties, including empty objects {}

---

### SLIDE 8: SEGMENT 2 - PRIMITIVE TYPES

**Title:** Primitive Data Types

**Content:**

**Available Types:**

| Type | Description | Example |
|------|-------------|---------|
| `string` | Text values | `"hello"` |
| `number` | Any number | `42` or `3.14` |
| `integer` | Whole numbers only | `42` |
| `boolean` | True/false | `true` |
| `null` | Null value | `null` |
| `array` | Ordered list | `[1, 2, 3]` |
| `object` | Key-value structure | `{"a": 1}` |

**Graphic:** Visual showing each type with examples

**GRAPHICS:**

**Graphic 1: JSON Primitive Types Reference**
- Purpose: Quick visual reference for all JSON data types
- Type: Icon grid with examples
- Elements: 7 boxes, one per type (string, number, integer, boolean, null, array, object)
- Labels:
  - Each box contains: Type name, icon, example value, use case
  - string → "abc" icon, "hello", "Text values"
  - number → 123.45 icon, "3.14", "Any numeric"
  - integer → 42 icon, "42", "Whole numbers"
  - boolean → true/false toggle, "true", "Yes/no flags"
  - null → empty symbol, "null", "No value"
  - array → [] bracket icon, "[1,2,3]", "Lists"
  - object → {} brace icon, '{"a":1}', "Key-value pairs"
- Relationships: Organized in logical order (simple → complex)

**SPEAKER NOTES:**

"JSON Schema supports seven primitive types:

String is for text - any text value.

Number accepts any numeric value, including decimals. If you specifically need whole numbers, use integer instead.

Boolean is true or false.

Null is... null. This is rarely the type itself, but often appears in combinations.

Array is an ordered list of values.

Object is a key-value structure - what we usually think of as JSON.

[Pause]

But types alone aren't enough. You need constraints. Let me show you..."

[Transition]

---

### SLIDE 9: SEGMENT 2 - STRING CONSTRAINTS

**Title:** Constraining Strings

**Content:**

```json
{
  "type": "string",
  "minLength": 1,
  "maxLength": 100,
  "pattern": "^[A-Z][a-z]+$",
  "format": "email"
}
```

**Available Constraints:**

- `minLength` / `maxLength` - Length limits
- `pattern` - Regular expression match
- `format` - Built-in formats:
  - `email`, `uri`, `uuid`
  - `date`, `time`, `date-time`
  - `ipv4`, `ipv6`, `hostname`

**Example:** Email validation
```json
{
  "type": "string",
  "format": "email",
  "description": "Contact email address"
}
```

**Graphic:** Examples of valid vs invalid strings for each constraint

**GRAPHICS:**

**Graphic 1: String Constraint Validation Examples**
- Purpose: Show how different string constraints validate data
- Type: Validation matrix with pass/fail indicators
- Elements: Table with constraints as rows, test values as columns
- Labels:
  - Row headers: "minLength: 1", "maxLength: 100", "pattern: ^[A-Z][a-z]+$", "format: email"
  - Test values: "", "Hi", "ValidName", "invalid", "user@example.com", "not-an-email"
  - Cells: ✓ (green checkmark) or ✗ (red X)
- Relationships: Show that one value can pass some constraints but fail others
- Examples:
  - "" fails minLength, passes maxLength
  - "ValidName" passes pattern (capital + lowercase)
  - "user@example.com" passes format: email

**SPEAKER NOTES:**

"Now we get to the power of schemas: constraints.

For strings, you can set minimum and maximum length. This prevents empty strings or excessively long input.

You can use regular expressions with `pattern`. This example requires strings that start with a capital letter followed by lowercase letters.

And you can use built-in formats. `format: email` validates email addresses. `format: date` ensures dates are in YYYY-MM-DD format.

[Point to example]

This schema would accept: `user@example.com`

But reject: `not-an-email` or `user@` or `@example.com`

Let's look at number constraints..."

[Transition]

---

### SLIDE 10: SEGMENT 2 - NUMBER CONSTRAINTS

**Title:** Constraining Numbers

**Content:**

```json
{
  "type": "number",
  "minimum": 0,
  "maximum": 100,
  "multipleOf": 0.5
}
```

**Available Constraints:**

- `minimum` / `maximum` - Range limits (inclusive)
- `exclusiveMinimum` / `exclusiveMaximum` - Range limits (exclusive)
- `multipleOf` - Must be a multiple of this value

**Examples:**

Percentage score:
```json
{ "type": "number", "minimum": 0, "maximum": 100 }
```

Price in dollars and cents:
```json
{ "type": "number", "minimum": 0, "multipleOf": 0.01 }
```

Positive integers only:
```json
{ "type": "integer", "minimum": 1 }
```

**Graphic:** Number line showing valid/invalid ranges

**GRAPHICS:**

**Graphic 1: Number Constraint Ranges**
- Purpose: Visualize how number constraints work on a number line
- Type: Annotated number line diagram
- Elements: Horizontal number line from -10 to 110 with highlighted valid range
- Labels:
  - Range marker showing "minimum: 0" and "maximum: 100"
  - Green shaded area between 0 and 100 labeled "Valid Range"
  - Red areas outside this range labeled "Invalid"
  - Example values plotted: -5 (✗), 0 (✓), 50 (✓), 100 (✓), 105 (✗)
- Relationships: Visual representation of inclusive minimum/maximum
- Additional: Small callout showing "multipleOf: 0.5" with examples 50, 50.5, 51 valid; 50.3 invalid

**SPEAKER NOTES:**

"For numbers, you have range and precision constraints.

Minimum and maximum set the allowed range. Use `exclusiveMinimum` if you want 'greater than' instead of 'greater than or equal to'.

MultipleOf ensures the number is a multiple of the specified value. This is perfect for prices - use 0.01 to ensure two decimal places.

[Point to examples]

For a percentage score, you'd use minimum 0, maximum 100.

For a price in dollars and cents, minimum 0 and multipleOf 0.01.

For positive integers only, use type integer with minimum 1.

[Pause]

Now let's see how to combine these into objects and arrays..."

[Transition: Click to Segment 3]

---

### SLIDE 11: SEGMENT 2 - KEY TAKEAWAY

**Title:** Schema Basics Summary

**Content:**

**Key Takeaway:** Every data element has a type and constraints that define valid values

**Remember:**
- Start with `$schema` and `$id` at the top
- Use `type` to define the data type
- Add constraints specific to that type
- Document with `title` and `description`

**You'll Practice:**
Exercise 1.1 - Create schemas for workflow input and quality evaluation results

**Graphic:** Simple visual showing schema → validation → pass/fail

**SPEAKER NOTES:**

"Before we move on, let me summarize the key points:

Every piece of data has a type and constraints. That's the foundation of JSON Schema.

Always start with `$schema` and `$id` at the top of your schema file.

Use the `type` field to define what kind of data you're validating.

Add constraints specific to that type - length for strings, range for numbers, etc.

And always include `title` and `description` so your schema is self-documenting.

In your homework this week, Exercise 1.1 will give you hands-on practice creating schemas for real workflow data.

[Pause]

Any final questions on basic types and constraints before we move to objects and arrays?"

[Transition: Click to Segment 3]

---

## SEGMENT 3: OBJECTS AND ARRAYS
### Duration: 12 minutes | Slides 12-15

---

### SLIDE 12: SEGMENT 3 - OBJECT SCHEMAS

**Title:** Validating Objects

**Content:**

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

**Key Elements:**
- `properties` - Define each field with its schema
- `required` - Array of mandatory field names
- `additionalProperties` - Allow/deny extra fields
  - `false` - Strict, no extra fields
  - `true` - Allow any extra fields
  - Schema object - Extra fields must match schema

**Graphic:** Object visualization showing required vs optional fields

**GRAPHICS:**

**Graphic 1: Object Schema Structure**
- Purpose: Show how object schemas define and validate structure
- Type: Layered diagram with visual hierarchy
- Elements: Object box containing field definitions
- Labels:
  - Object container labeled "User Object"
  - Inside: "name: string" with red asterisk (*) labeled "Required"
  - Inside: "age: integer (≥0)" with gray text labeled "Optional"
  - Outside: "additionalProperties: false" with lock icon
- Relationships:
  - Required fields marked distinctly (red asterisk or border)
  - Optional fields in lighter color
  - additionalProperties setting shown as boundary control
- Visual Style: Use solid border for required, dashed for optional

**Graphic 2: Valid vs Invalid Object Examples**
- Purpose: Show what passes or fails object validation
- Type: Side-by-side comparison with pass/fail indicators
- Elements: Three example JSON objects with validation results
- Labels:
  - Example 1: {"name": "Alice"} → ✓ "Valid (required field present)"
  - Example 2: {"age": 30} → ✗ "Invalid (missing required name)"
  - Example 3: {"name": "Bob", "email": "..."} → ✗ "Invalid (additionalProperties:false)"
- Relationships: Shows how schema rules are applied

**SPEAKER NOTES:**

"[INSIGHT - Objects are where schemas get powerful]"

"Objects are the most common data structure you'll validate. Here's how object schemas work:

`properties` defines each field. Each property name maps to a schema for that field. In this example, name is a string and age is a non-negative integer.

`required` is an array of field names that must be present. Here, name is required but age is optional.

[Point to additionalProperties]

This is critical: `additionalProperties` controls whether extra fields are allowed.

Set it to `false` for strict validation - only the fields you defined are allowed. This catches typos and unexpected AI additions.

Set it to `true` if you want to allow extra fields you didn't define.

Or provide a schema that extra fields must match.

[Example]

This schema accepts:
```
{ "name": "Alice" }
{ "name": "Bob", "age": 30 }
```

But rejects:
```
{ "age": 30 }  // missing required name
{ "name": "Alice", "email": "alice@example.com" }  // extra field not allowed
```

Let's look at arrays..."

[Transition]

---

### SLIDE 13: SEGMENT 3 - ARRAY SCHEMAS

**Title:** Validating Arrays

**Content:**

```json
{
  "type": "array",
  "items": { "type": "string" },
  "minItems": 1,
  "maxItems": 10,
  "uniqueItems": true
}
```

**Key Elements:**
- `items` - Schema for array elements
  - Same schema for all items
  - Or tuple validation (different schema per position)
- `minItems` / `maxItems` - Length constraints
- `uniqueItems` - Prevent duplicates

**Examples:**

List of email addresses:
```json
{
  "type": "array",
  "items": { "type": "string", "format": "email" },
  "minItems": 1
}
```

**Graphic:** Array visualization showing validation of elements

**GRAPHICS:**

**Graphic 1: Array Schema Validation**
- Purpose: Show how array constraints validate lists
- Type: Diagram showing array with validation annotations
- Elements: Visual array representation with brackets and elements
- Labels:
  - Array: ["alice@ex.com", "bob@ex.com", "carol@ex.com"]
  - Top annotation: "items: {type: string, format: email}" with arrows pointing to each element
  - Left annotation: "minItems: 1 ✓ (has 3 items)"
  - Right annotation: "maxItems: 10 ✓ (has 3 items)"
  - Bottom annotation: "uniqueItems: true ✓ (all unique)"
- Relationships: Show how each constraint checks a different aspect of the array
- Visual Style: Green checkmarks for passing constraints

**Graphic 2: Array Validation Failures**
- Purpose: Show common array validation errors
- Type: Examples with failure indicators
- Elements: Three failing examples
- Labels:
  - Example 1: [] → ✗ "Fails minItems: 1 (empty array)"
  - Example 2: [15 emails...] → ✗ "Fails maxItems: 10 (too many)"
  - Example 3: ["a@ex.com", "b@ex.com", "a@ex.com"] → ✗ "Fails uniqueItems (duplicate)"
- Relationships: Each example demonstrates one validation failure

**SPEAKER NOTES:**

"Arrays are lists of values. Array schemas define what's in the list and how long it can be.

`items` is the schema for array elements. Usually, this is a single schema that applies to every element.

[Point to example]

This schema says: array of strings, minimum 1 item, maximum 10 items, all items must be unique.

`minItems` and `maxItems` control the array length. Use `minItems: 1` to prevent empty arrays.

`uniqueItems: true` prevents duplicates. Perfect for lists that shouldn't have repeats.

[Point to email example]

For a list of email addresses, you'd use type array with items that are email-format strings, with a minimum of 1 to require at least one email.

Now let's combine objects and arrays for complex structures..."

[Transition]

---

### SLIDE 14: SEGMENT 3 - NESTED STRUCTURES

**Title:** Complex Nested Schemas

**Content:**

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

**What This Validates:**
```json
{
  "client": {
    "name": "Acme Corp",
    "contacts": [
      { "email": "john@acme.com" },
      { "email": "jane@acme.com" }
    ]
  }
}
```

**Graphic:** Tree diagram showing nested structure

**GRAPHICS:**

**Graphic 1: Nested Schema Structure Tree**
- Purpose: Visualize the hierarchy of nested objects and arrays
- Type: Tree diagram with expandable levels
- Elements: Root node expanding to show full nesting
- Labels:
  - Level 1: Root object
  - Level 2: "client" (object property)
  - Level 3: "name" (string), "contacts" (array)
  - Level 4: Array items (objects)
  - Level 5: "email" (string with format constraint)
- Relationships: Parent-child connections showing nesting
- Visual Style: Different shapes for different types (rectangles for objects, brackets for arrays, ovals for primitives)
- Annotations: Type indicators at each level

**Graphic 2: Schema-to-Data Mapping**
- Purpose: Show how schema structure maps to actual data
- Type: Side-by-side comparison
- Elements: Schema code on left, valid data example on right, with connecting lines
- Labels:
  - Left: Schema defining structure
  - Right: Actual JSON data
  - Lines: Connect schema definitions to corresponding data elements
- Relationships: Visual mapping between schema rules and data structure

**SPEAKER NOTES:**

"[DEMO - Complex structure]"

"Real workflow data is often nested - objects inside objects, arrays of objects, objects with arrays.

Let me walk through this example:

At the top level, we have an object with a client property.

Client is itself an object with two properties: name and contacts.

Contacts is an array of objects, where each object has an email property.

[Point to data example]

This is what valid data looks like: A client with a name and an array of contact objects, each with an email.

[Pause]

The key is to build from the inside out. Start with the innermost structure, then work your way up.

In Exercise 1.2, you'll create a schema for your style.json file, which has this kind of nested structure.

[Transition]

**BACKGROUND:**

**Rationale:**
- Nested structures represent the complexity inflection point where schemas become truly valuable vs. optional
- This slide demonstrates that schema complexity mirrors data complexity naturally, making complex validation manageable
- Establishes the inside-out building pattern that prevents overwhelming cognitive load when creating complex schemas

**Key Research & Citations:**
- **Cognitive Load Theory**: Breaking complex structures into composable pieces (nested schemas) reduces working memory demands
- **Real-world AI Workflows**: 80%+ of production workflow data involves nested objects or arrays, making this pattern essential not optional

**Q&A Preparation:**
- *"How deep can nesting go?"*: Technically unlimited, but practically keep it under 4-5 levels for maintainability. If deeper, consider if your data model can be simplified
- *"Can I reference the same schema multiple times?"*: Yes, use $ref to reference shared schema definitions, reducing duplication
- *"What if array items need different schemas based on position?"*: Use "prefixItems" for tuple validation where position determines schema

---

### SLIDE 15: SEGMENT 3 - KEY TAKEAWAY

**Title:** Objects and Arrays Summary

**Content:**

**Key Takeaway:** Nest schemas to match your data structure - objects contain properties, arrays contain items

**Remember:**
- Use `properties` and `required` for objects
- Use `items` for arrays
- Set `additionalProperties: false` for strict validation
- Build complex schemas from inside out

**You'll Practice:**
Exercise 1.2 - Create schema for style.json with nested structures

**Graphic:** Simple nested structure diagram

**SPEAKER NOTES:**

"Let me summarize objects and arrays:

Nest schemas to match your data structure. If your data has objects inside objects, your schema does too.

For objects, define properties and mark which are required.

For arrays, define what the items look like.

Set additionalProperties to false when you want strict validation - only the fields you defined are allowed.

When building complex schemas, start with the innermost structures and work outward.

Exercise 1.2 will have you create a schema for your style.json file, which typically has nested objects and arrays.

[Pause]

Questions on objects and arrays before we look at advanced constraints?"

[Transition: Click to Segment 4]

---

## SEGMENT 4: ADVANCED CONSTRAINTS
### Duration: 8 minutes | Slides 16-18

---

### SLIDE 16: SEGMENT 4 - ENUMS

**Title:** Enums: Allowed Values

**Content:**

**Enum Constraint:**
```json
{
  "type": "string",
  "enum": ["draft", "review", "published"]
}
```

**Use Cases:**
- Status fields with specific allowed values
- Categories or types from a fixed list
- Priority levels, stages, states

**Examples:**

Priority levels:
```json
{
  "type": "string",
  "enum": ["low", "normal", "high", "urgent"],
  "default": "normal"
}
```

Task type:
```json
{
  "type": "string",
  "enum": ["proposal", "assessment", "report"]
}
```

**Graphic:** Dropdown menu visual showing allowed values

**GRAPHICS:**

**Graphic 1: Enum Constraint Visualization**
- Purpose: Show how enums restrict values to a specific set
- Type: Dropdown/selection visualization
- Elements: Dropdown menu style graphic with allowed values
- Labels:
  - Dropdown header: "status: string"
  - Options list: "draft", "review", "published" (all valid, shown in green)
  - Below: Attempted values with results:
    - "draft" → ✓ "Allowed"
    - "Draft" → ✗ "Rejected (case-sensitive)"
    - "pending" → ✗ "Rejected (not in enum)"
- Relationships: Shows that only exact matches from enum list are accepted
- Visual Style: Green for allowed values, red for rejected values

**SPEAKER NOTES:**

"Enums restrict a field to a specific set of allowed values.

[Point to example]

This schema says: the value must be a string, and it must be exactly one of: draft, review, or published. Nothing else is allowed.

Enums are perfect for:
- Status fields where you have specific states
- Categories from a fixed list
- Priority levels, workflow stages, any field with a known set of values

[Point to priority example]

Notice you can also include a default value. If the field is omitted, it defaults to 'normal'.

Enums prevent typos and ensure consistency. Instead of accepting 'Draft', 'draft', 'DRAFT', you force exactly 'draft'.

Let's look at conditional validation..."

[Transition]

---

### SLIDE 17: SEGMENT 4 - CONDITIONALS

**Title:** Conditional Schemas

**Content:**

**If-Then Pattern:**
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

**What This Means:**
IF the type field equals "business",
THEN company_name is required

**Use Cases:**
- Different required fields based on type
- Additional constraints based on context
- Validation rules that depend on other fields

**Example:** Contact validation
```json
{
  "if": {
    "properties": { "contact_method": { "const": "email" } }
  },
  "then": {
    "required": ["email_address"],
    "properties": {
      "email_address": { "type": "string", "format": "email" }
    }
  }
}
```

**Graphic:** Decision tree showing if-then logic

**GRAPHICS:**

**Graphic 1: Conditional Schema Flow**
- Purpose: Show how if-then conditional validation works
- Type: Decision tree / flowchart
- Elements: Diamond decision node with branching paths
- Labels:
  - Decision diamond: "type === 'business'?"
  - Left branch (Yes): "THEN company_name is required" → Shows object with company_name field
  - Right branch (No): "No additional requirements" → Shows object without company_name
- Relationships: Conditional logic determining which validation rules apply
- Visual Style: Use flowchart conventions (diamond for decision, rectangles for outcomes)

**Graphic 2: Conditional Validation Example**
- Purpose: Show concrete example of conditional validation in action
- Type: Side-by-side comparison
- Elements: Two data objects with validation results
- Labels:
  - Example 1: {type: "business", company_name: "Acme"} → ✓ "Valid"
  - Example 2: {type: "business"} → ✗ "Invalid (company_name required when type=business)"
  - Example 3: {type: "personal"} → ✓ "Valid (company_name not required)"
- Relationships: Shows how the same schema validates differently based on field values

**SPEAKER NOTES:**

"Sometimes validation rules depend on other fields. That's where conditionals come in.

[Point to example]

This says: IF the type field equals 'business', THEN company_name is required.

For other types, company_name might be optional or not exist at all.

[Point to contact example]

Here's a practical use case: If the contact method is email, then email_address is required and must be a valid email format.

You can also use `else` for what happens when the condition isn't met.

Conditionals let you express complex business rules in your schemas.

[Pause]

Let's look at one more advanced feature..."

[Transition]

---

### SLIDE 18: SEGMENT 4 - COMBINING SCHEMAS

**Title:** Schema Combinations

**Content:**

**Combining Operators:**

- `allOf` - Must match ALL schemas
- `anyOf` - Must match AT LEAST ONE schema
- `oneOf` - Must match EXACTLY ONE schema
- `not` - Must NOT match schema

**Example: allOf**
```json
{
  "allOf": [
    { "type": "object", "required": ["name"] },
    { "type": "object", "required": ["email"] }
  ]
}
```
Result: Both name AND email required

**Example: anyOf**
```json
{
  "anyOf": [
    { "properties": { "email": { "type": "string" } } },
    { "properties": { "phone": { "type": "string" } } }
  ]
}
```
Result: Must have email OR phone (or both)

**Graphic:** Venn diagram showing set operations

**GRAPHICS:**

**Graphic 1: Schema Combination Operators**
- Purpose: Visualize how allOf, anyOf, oneOf, and not work using set theory
- Type: Venn diagram grid (2x2 layout)
- Elements: Four separate diagrams showing each operator
- Labels:
  - **allOf**: Two overlapping circles A and B, only intersection highlighted → "Must match ALL schemas"
  - **anyOf**: Two overlapping circles, entire area (A + B + intersection) highlighted → "Must match AT LEAST ONE"
  - **oneOf**: Two overlapping circles, A-only and B-only highlighted (NOT intersection) → "Must match EXACTLY ONE"
  - **not**: Single circle with shaded area outside → "Must NOT match schema"
- Relationships: Visual representation of Boolean logic
- Visual Style: Use consistent colors (green for valid regions, gray for invalid)

**Graphic 2: Practical Combination Example**
- Purpose: Show real-world use of schema combinations
- Type: Annotated example
- Elements: Contact validation scenario
- Labels:
  - "anyOf: [email schema, phone schema]"
  - Valid examples: {email: "..."}, {phone: "..."}, {email: "...", phone: "..."}
  - Invalid example: {} (neither email nor phone)
- Relationships: Shows "at least one contact method required" pattern

**SPEAKER NOTES:**

"[INSIGHT - Schema combinations]"

"Finally, you can combine multiple schemas with logical operators.

`allOf` means the data must match all of the listed schemas. Use this to compose complex schemas from simpler pieces.

`anyOf` means the data must match at least one schema. Perfect for 'email OR phone required' scenarios.

`oneOf` means exactly one schema must match - not zero, not two, exactly one.

`not` means the data must not match the schema - useful for exclusions.

[Point to examples]

The allOf example requires both name AND email.

The anyOf example requires email OR phone - at least one must be present.

These operators let you express complex validation logic without repeating yourself.

[Pause]

That's a quick tour of advanced constraints. You'll use these in Exercise 1.3 when building your schema library."

[Transition: Click to closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 19-21

---

### SLIDE 19: HOMEWORK OVERVIEW

**Title:** This Session's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 1.1: Schema Basics Practice | 20 min | 2 schema files + test results | Basic schemas, primitive types, validation |
| Exercise 1.2: Complex Schema Design | 20 min | style-guide.schema.json | Nested objects, complex constraints |
| Exercise 1.3: Schema Library Setup | 20 min | Organized schema library | Reusable patterns, references |
| **Total** | **60 min** | | |

**Graphic:** Exercise icons or visual workflow showing the progression

**SPEAKER NOTES:**

"Here's your homework for this session. You have 60 minutes of exercises to complete before our next session.

[Walk through each exercise briefly]:

Exercise 1.1 takes about 20 minutes. You'll create schemas for workflow input and quality evaluation results, then validate them with an online tool. This practices basic schema syntax and primitive types.

Exercise 1.2 is 20 minutes. You'll create a schema for your style.json file. This practices nested objects and complex constraints.

Exercise 1.3 is 20 minutes. You'll organize your schemas into a reusable library with base types and references. This sets you up for Session 2 where we'll use these schemas in real workflows.

These exercises build on each other, so I recommend completing them in order.

All the detailed instructions are in your participant guide, along with templates and examples."

[Transition]

---

### SLIDE 20: RESOURCES

**Title:** Resources for This Session

**Content:**

**Templates & Files:**
- Exercise schemas provided in session materials
- Base types template included

**Reference Materials:**
- JSON Schema Official Docs: https://json-schema.org/
- Online Validator: https://www.jsonschemavalidator.net/
- JSON Schema Cheat Sheet (Appendix A in module)

**Validation Tools:**
- Online: jsonschemavalidator.net, jsonschemalint.com
- JavaScript: ajv, zod
- Python: jsonschema, pydantic

**Support:**
- Questions: [Async channel name]
- Office Hours: [Time/location if applicable]

**Graphic:** QR codes or simple icons for quick access to key resources

**SPEAKER NOTES:**

"You have several resources to support your homework:

The session materials include all the example schemas we discussed today, plus templates for the base types schema.

For reference, bookmark json-schema.org - it's the official documentation. The validator at jsonschemavalidator.net is perfect for testing your schemas.

Appendix A in the module document is a JSON Schema cheat sheet - all the constraints on one page.

If you're ready to implement validation in code, the resources section lists popular validation libraries for JavaScript and Python.

If you get stuck, post in [async channel]. [Instructor] monitors it and you'll usually get a response within [timeframe].

[Transition]

---

### SLIDE 21: NEXT SESSION PREVIEW

**Title:** Next Session: Validation in Practice

**Content:**

**Preview:**
Session 2 will cover implementing validation in your actual workflows - runtime validation, error handling, and the module capstone.

**What to Complete Before Then:**
- [ ] Exercise 1.1: Schema Basics Practice
- [ ] Exercise 1.2: Complex Schema Design
- [ ] Exercise 1.3: Schema Library Setup

**Key Preparation:**
Have your schema library ready - we'll be integrating it into workflows next session.

**Graphic:** Preview image showing validation in a workflow context

**SPEAKER NOTES:**

"Next session we'll cover validation in practice. We'll take the schemas you create this week and integrate them into real workflows.

You'll learn how to validate inputs before processing, validate AI outputs after generation, handle validation errors gracefully, and build robust error recovery.

The capstone for this module is a fully validated workflow system, so Session 2 brings it all together.

Make sure you've completed all three exercises before next session - we'll be building directly on your schema library.

[Final close]

Great session today. Remember: schemas are contracts. Write them clearly, validate consistently, and your workflows become dramatically more reliable.

You now have the syntax knowledge. This week's exercises will give you the practice. Next session, we'll put it into production.

See you next time!"

---

## APPENDICES

### Appendix A: Slide Type Definitions

**TITLE SLIDE**, **PROBLEM STATEMENT**, **INSIGHT / REVELATION**, **CONCEPT INTRODUCTION**, **FRAMEWORK / MODEL**, **COMPARISON**, **DEEP DIVE**, **CASE STUDY**, **PATTERN / BEST PRACTICE**, **METRICS / DATA**, **ARCHITECTURE / DIAGRAM**, **OBJECTION HANDLING**, **ACTION / NEXT STEPS**, **SUMMARY / RECAP**, **CLOSING / CALL TO ACTION**, **Q&A / CONTACT**, **APPENDIX**

### Appendix B: Presentation Delivery Notes

**Timing Checkpoints:**

| Checkpoint | Target Time |
|------------|-------------|
| End Segment 1 | 13 min |
| End Segment 2 | 28 min |
| End Segment 3 | 40 min |
| End Segment 4 | 48 min |
| Session End | 51 min |

**Demo Preparation:**
- Online validator: https://www.jsonschemavalidator.net/
- Example schema files ready
- Valid and invalid JSON examples prepared
- Backup: Screenshots if live demo fails

**Key Messages to Emphasize:**
1. "Schemas are contracts - define them once, validate everywhere"
2. "Fail fast with clear errors, not slow with mysterious bugs"
3. "Your schema IS your documentation"

### Appendix C: BACKGROUND & Implementation Guidance

See template for full BACKGROUND section structure (Rationale, Key Research & Citations, Q&A Preparation) and Implementation Guidance structure (Getting Started, Best Practices, Common Pitfalls, Tools & Technologies).

---

### Appendix D: JSON Schema Quick Reference

**Primitive Types:**
- `string`, `number`, `integer`, `boolean`, `null`, `array`, `object`

**String Constraints:**
- `minLength`, `maxLength`, `pattern` (regex), `format` (email, uri, date, etc.)

**Number Constraints:**
- `minimum`, `maximum`, `exclusiveMinimum`, `exclusiveMaximum`, `multipleOf`

**Array Constraints:**
- `items` (schema for elements), `minItems`, `maxItems`, `uniqueItems`

**Object Constraints:**
- `properties` (field definitions), `required` (array of field names), `additionalProperties` (true/false/schema)

**Combining Schemas:**
- `allOf`, `anyOf`, `oneOf`, `not`

**Conditionals:**
- `if`, `then`, `else`

---

### Appendix E: Common Schema Patterns

**Email Address:**
```json
{
  "type": "string",
  "format": "email",
  "description": "User email address"
}
```

**Percentage (0-100):**
```json
{
  "type": "number",
  "minimum": 0,
  "maximum": 100,
  "description": "Percentage value"
}
```

**Required Object with Optional Fields:**
```json
{
  "type": "object",
  "properties": {
    "id": { "type": "string" },
    "name": { "type": "string" },
    "email": { "type": "string", "format": "email" }
  },
  "required": ["id", "name"],
  "additionalProperties": false
}
```

**Array of Strings (at least one):**
```json
{
  "type": "array",
  "items": { "type": "string" },
  "minItems": 1
}
```

**Enum (Status Field):**
```json
{
  "type": "string",
  "enum": ["pending", "in_progress", "completed", "failed"],
  "default": "pending"
}
```

---

### Appendix F: Validation Tools by Platform

**JavaScript/Node.js:**
- **ajv**: Fastest validator, supports all JSON Schema features
  - Install: `npm install ajv`
  - Usage: `const ajv = new Ajv(); const validate = ajv.compile(schema);`
- **zod**: TypeScript-first with type inference
  - Great for TS projects, different syntax from JSON Schema

**Python:**
- **jsonschema**: Reference implementation
  - Install: `pip install jsonschema`
  - Usage: `jsonschema.validate(instance, schema)`
- **pydantic**: Popular for FastAPI, uses Python type hints

**No-Code Platforms:**
- **Make.com**: Built-in JSON module with schema validation
- **n8n**: Use Function node with ajv library
- **Zapier**: Limited native support, use Code by Zapier with ajv

**Online Validators:**
- https://www.jsonschemavalidator.net/ (best for learning)
- https://jsonschemalint.com/ (detailed error messages)

---

### Appendix G: Exercise 1.1 - Schema Basics Practice

**Objective:** Create basic schemas for workflow input and quality evaluation results

**Time:** 20 minutes

**Deliverables:**
1. `workflow-input.schema.json` - Schema for workflow trigger data
2. `quality-result.schema.json` - Schema for quality evaluation output
3. Test results screenshot showing validation

**Steps:**

1. **Create workflow-input.schema.json**
   - Required fields: `task_id` (string), `task_type` (enum: proposal, assessment, report), `client_name` (string)
   - Optional fields: `deadline` (date string), `special_instructions` (string)
   - No additional properties allowed

2. **Create quality-result.schema.json**
   - Required fields: `score` (number 0-5), `feedback` (string min 10 chars), `approved` (boolean)
   - Optional fields: `improvements` (array of strings), `reviewer` (string)

3. **Test Your Schemas**
   - Visit https://www.jsonschemavalidator.net/
   - Paste schema in left panel
   - Test with valid and invalid data
   - Screenshot results

**Example Test Data for workflow-input:**

Valid:
```json
{
  "task_id": "T-12345",
  "task_type": "proposal",
  "client_name": "Acme Corp"
}
```

Invalid (missing required field):
```json
{
  "task_id": "T-12345",
  "task_type": "proposal"
}
```

---

### Appendix H: Exercise 1.2 - Complex Schema Design

**Objective:** Create a schema for your style.json file with nested structures

**Time:** 20 minutes

**Deliverable:** `style-guide.schema.json`

**Steps:**

1. **Analyze Your style.json Structure**
   - Identify all top-level properties
   - Note nested objects and arrays
   - Determine which fields are required vs optional

2. **Build Schema from Inside Out**
   - Start with innermost nested objects
   - Define array item schemas
   - Work outward to top level

3. **Add Constraints**
   - String lengths where appropriate
   - Number ranges for scores/ratings
   - Enums for categorical fields
   - Format validation for emails, URLs, dates

4. **Test Thoroughly**
   - Validate your actual style.json
   - Test with missing required fields
   - Test with wrong types
   - Test with additional properties

**Typical style.json Schema Structure:**
```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "style-guide.schema.json",
  "title": "Style Guide Configuration",
  "type": "object",
  "properties": {
    "tone": {
      "type": "object",
      "properties": {
        "formality": { "type": "string", "enum": ["casual", "professional", "formal"] },
        "voice": { "type": "string", "enum": ["active", "passive"] }
      },
      "required": ["formality"]
    },
    "formatting": {
      "type": "object",
      "properties": {
        "headings": { "type": "boolean" },
        "bullet_points": { "type": "boolean" }
      }
    }
  },
  "required": ["tone"],
  "additionalProperties": false
}
```

---

### Appendix I: Exercise 1.3 - Schema Library Setup

**Objective:** Organize schemas into a reusable library with base types and references

**Time:** 20 minutes

**Deliverables:**
1. `/schemas` folder with organized schema files
2. `base-types.schema.json` with common definitions
3. Updated schemas using $ref to reference base types

**Steps:**

1. **Create Folder Structure**
   ```
   /schemas
     /base
       base-types.schema.json
     /workflows
       workflow-input.schema.json
       workflow-output.schema.json
     /quality
       quality-result.schema.json
   ```

2. **Define Base Types** (base-types.schema.json)
   ```json
   {
     "$schema": "https://json-schema.org/draft/2020-12/schema",
     "$id": "base-types.schema.json",
     "$defs": {
       "email": {
         "type": "string",
         "format": "email"
       },
       "score_0_5": {
         "type": "number",
         "minimum": 0,
         "maximum": 5
       },
       "non_empty_string": {
         "type": "string",
         "minLength": 1
       }
     }
   }
   ```

3. **Use References in Other Schemas**
   ```json
   {
     "properties": {
       "email": { "$ref": "base-types.schema.json#/$defs/email" },
       "score": { "$ref": "base-types.schema.json#/$defs/score_0_5" }
     }
   }
   ```

4. **Document Your Library**
   - Create `schemas/README.md` explaining structure
   - List all schemas and their purposes
   - Include usage examples

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | AI Practitioner Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |
