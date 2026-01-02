# **POWERPOINT PRESENTATION: MODULE 3 SESSION 1**
## **JSON Schema Fundamentals**

**Module:** Advanced Module 3: JSON Schema & Data Validation
**Session Number:** 1 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 2+ graduates who want to implement robust data validation in their AI workflows

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

## Appendix: Presentation Notes

### Timing Checkpoints

| Checkpoint | Target Time | Actual Time |
|------------|-------------|-------------|
| End Segment 1 | 13 min | |
| End Segment 2 | 28 min | |
| End Segment 3 | 40 min | |
| End Segment 4 | 48 min | |
| Session End | 51 min | |

### Demo Preparation

**Tools Needed:**
- Online validator: https://www.jsonschemavalidator.net/
- Example schema files ready
- Valid and invalid JSON examples prepared

**Backup Plan:**
- Screenshots of validation passing and failing
- Prepared examples if live demo fails

### Key Messages to Emphasize

1. "Schemas are contracts - define them once, validate everywhere"
2. "Fail fast with clear errors, not slow with mysterious bugs"
3. "Your schema IS your documentation"

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | [Instructor] |
