# **Advanced Module 10: Data Architecture for AI Systems**
## **Session 2 - Data Transformation & Agent Interfaces**

**Module:** Advanced Module 10
**Session:** 2 of 2
**Duration:** 45 min live + 75 min homework

-----

## **Entry Criteria**

- [ ] Information architecture principles understood
- [ ] Format selection framework applied
- [ ] Metadata strategy designed
- [ ] Sample data prepared for transformation exercises

## **Exit Criteria**

- [ ] Data transformation pipeline implemented
- [ ] Agent-to-agent data interface designed
- [ ] AI readiness assessment methodology applied
- [ ] Module capstone completed

-----

## **Workshop Content (45 minutes)**

### **Segment 1: Data Transformation Pipelines (12 min)**

- **The transformation challenge:**

  ```
  ENTERPRISE REALITY              AI REQUIREMENTS
  ─────────────────────────────   ─────────────────────────────
  Multiple formats                Consistent structure
  Inconsistent naming             Standardized taxonomy
  Missing metadata                Rich metadata
  Implicit relationships          Explicit connections
  Scattered across systems        Unified access patterns
  Historical conventions          AI-optimized patterns
  ```

- **Pipeline architecture:**

  ```
  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
  │   SOURCE    │───▶│   EXTRACT   │───▶│  TRANSFORM  │───▶│    LOAD     │
  │    DATA     │    │  & VALIDATE │    │ & ENRICH    │    │  & INDEX    │
  └─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘
        │                  │                  │                  │
        ▼                  ▼                  ▼                  ▼
   Raw formats        Valid data         Structured         AI-ready
   No metadata        Basic checks       + Metadata         + Searchable
   Inconsistent       Type coercion      + Normalized       + Versioned
  ```

- **Transformation operations:**

  | Operation | Purpose | Example |
  |-----------|---------|---------|
  | **Normalize** | Consistent formats | Dates to ISO-8601, names to standard form |
  | **Enrich** | Add metadata | Auto-generate summaries, extract entities |
  | **Restructure** | Optimize layout | Flatten nested, chunk documents |
  | **Link** | Connect related | Add cross-references, build relationships |
  | **Validate** | Ensure quality | Schema validation, completeness checks |
  | **Version** | Track changes | Add version metadata, maintain history |

- **AI-assisted transformation:**

  ```markdown
  # Transformation Prompt Pattern

  You are transforming legacy data into AI-optimized format.

  ## Input
  ```
  [Raw data]
  ```

  ## Target Schema
  ```json
  {
    "required_fields": [...],
    "taxonomies": {...},
    "format_rules": {...}
  }
  ```

  ## Instructions
  1. Extract all entities and relationships
  2. Map to target taxonomy
  3. Generate missing metadata
  4. Flag ambiguities for human review

  ## Output Format
  [Structured output template]
  ```

### **Segment 2: Enterprise Data Patterns (10 min)**

- **Common enterprise data challenges:**

  | Source | Typical Issues | Transformation Strategy |
  |--------|----------------|------------------------|
  | **Wiki/Confluence** | Inconsistent structure, stale content | Template enforcement, freshness metadata |
  | **SharePoint** | Poor taxonomy, buried in folders | Re-categorize, extract to flat structure |
  | **Email/Slack** | Unstructured, context-dependent | Extract decisions/actions, summarize |
  | **Databases** | Technical schemas, no semantics | Add business context, readable names |
  | **PDFs/Docs** | Layout-dependent, no structure | Extract, restructure, validate |
  | **Spreadsheets** | Implicit headers, merged cells | Normalize, explicit column meanings |

- **Dealing with messy reality:**

  ```
  STRATEGY 1: Parallel Structures
  ─────────────────────────────────
  Keep original → Create AI-optimized copy → Sync mechanism
  (Preserves existing workflows while enabling AI)

  STRATEGY 2: Progressive Enhancement
  ─────────────────────────────────────
  Add metadata layer → Gradually restructure → Full migration
  (Lower risk, longer timeline)

  STRATEGY 3: New System, Old Bridge
  ────────────────────────────────────
  New AI-native system → Import/transform on read → Deprecate old
  (Clean slate with backward compatibility)
  ```

- **Handling uncertainty:**

  ```json
  {
    "extracted_data": {
      "client_name": "Acme Corp",
      "contract_value": 50000,
      "start_date": "2024-01-15"
    },
    "confidence": {
      "client_name": "high",
      "contract_value": "medium",
      "start_date": "low"
    },
    "flags": [
      {
        "field": "contract_value",
        "issue": "Multiple values found: 50000, 55000",
        "source_locations": ["page 2", "page 5"]
      },
      {
        "field": "start_date",
        "issue": "Relative date 'next quarter' - interpreted as Q1 2024",
        "requires_review": true
      }
    ]
  }
  ```

### **Segment 3: Agent-to-Agent Data Interfaces (12 min)**

- **The interface challenge:**

  ```
  Agent A                    Agent B
  ─────────────────────────  ─────────────────────────
  Produces output     ───▶   Needs input
  Own context/goals          Different context/goals
  Makes assumptions          May not share assumptions
  ```

- **Interface design principles:**

  1. **Self-describing:** Output includes schema/structure info
  2. **Complete context:** No assumed background knowledge
  3. **Explicit status:** Clear success/failure/partial
  4. **Actionable:** Receiving agent knows what to do

- **Standard output envelope:**

  ```json
  {
    "interface_version": "1.0",
    "producer": {
      "agent_id": "research-agent",
      "task_id": "task-123",
      "timestamp": "2024-10-15T10:30:00Z"
    },
    "status": {
      "code": "complete",
      "confidence": "high",
      "flags": []
    },
    "output": {
      "type": "research_results",
      "schema_version": "2.0",
      "data": {
        // Actual output data
      }
    },
    "context": {
      "original_request": "Find competitor pricing",
      "sources_consulted": ["source1", "source2"],
      "limitations": ["Only public data available"],
      "assumptions": ["Prices in USD unless noted"]
    },
    "handoff": {
      "suggested_next": "analysis-agent",
      "required_actions": ["Verify pricing accuracy", "Compare to internal costs"],
      "deadline": "2024-10-16T10:00:00Z"
    }
  }
  ```

- **Interface patterns:**

  | Pattern | Use Case | Structure |
  |---------|----------|-----------|
  | **Request-Response** | Synchronous calls | Request schema → Response schema |
  | **Event** | Async notifications | Event type + payload + metadata |
  | **Document** | Content handoff | Full document + processing instructions |
  | **Delta** | Updates only | Change set + base reference |
  | **Stream** | Continuous data | Chunk format + sequence + termination |

- **Versioning interfaces:**

  ```yaml
  interface: research-to-analysis
  version: 2.0
  breaking_changes_from: 1.0

  changes:
    - field: competitor_data
      change: renamed from 'competitors'
    - field: pricing.currency
      change: now required (was optional)

  migration:
    from_v1: |
      1. Rename 'competitors' to 'competitor_data'
      2. Add currency field (default: USD)
  ```

### **Segment 4: AI Readiness Assessment (11 min)**

- **The AI readiness framework:**

  ```
  ┌─────────────────────────────────────────────────────────────┐
  │                    AI READINESS SCORE                        │
  ├─────────────────────────────────────────────────────────────┤
  │  STRUCTURE  │  SEMANTICS  │  METADATA  │  FRESHNESS  │  ACCESS │
  │    /20      │     /20     │    /20     │     /20     │   /20   │
  └─────────────────────────────────────────────────────────────┘
  ```

- **Assessment dimensions:**

  | Dimension | What It Measures | Score Criteria |
  |-----------|------------------|----------------|
  | **Structure** | Organization and consistency | Format consistency, hierarchy, chunking |
  | **Semantics** | Meaning explicitness | Labels, relationships, context |
  | **Metadata** | Discoverability info | Completeness, accuracy, taxonomy |
  | **Freshness** | Currency and validity | Update tracking, staleness indicators |
  | **Access** | Retrievability | Indexing, search, permissions |

- **Quick assessment checklist:**

  ```markdown
  ## Structure (0-20 points)
  - [ ] (5) Consistent format within data type
  - [ ] (5) Clear hierarchical organization
  - [ ] (5) Appropriate chunking for AI context
  - [ ] (5) Machine-parseable structure

  ## Semantics (0-20 points)
  - [ ] (5) No ambiguous references (pronouns, "this/that")
  - [ ] (5) Explicit relationships stated
  - [ ] (5) Defined taxonomies used consistently
  - [ ] (5) Context provided, not assumed

  ## Metadata (0-20 points)
  - [ ] (5) Core fields present (title, type, status, date)
  - [ ] (5) Ownership clearly identified
  - [ ] (5) Tags/categories for discoverability
  - [ ] (5) Relationships to other content explicit

  ## Freshness (0-20 points)
  - [ ] (5) Last updated date tracked
  - [ ] (5) Version history available
  - [ ] (5) Staleness/expiry indicators
  - [ ] (5) Review cycle defined

  ## Access (0-20 points)
  - [ ] (5) Content is indexed/searchable
  - [ ] (5) Consistent access patterns
  - [ ] (5) Appropriate for AI context windows
  - [ ] (5) Security/permissions defined
  ```

- **Readiness levels:**

  | Score | Level | Recommendation |
  |-------|-------|----------------|
  | 0-40 | Not Ready | Major restructuring needed before AI use |
  | 41-60 | Basic | Can use with significant prompt engineering |
  | 61-80 | Good | Suitable for most AI use cases |
  | 81-100 | Excellent | Optimized for AI consumption |

- **Prioritization matrix:**

  ```
                    HIGH IMPACT
                         │
          ┌──────────────┼──────────────┐
          │              │              │
          │   QUICK      │   MAJOR      │
          │   WINS       │   PROJECTS   │
          │              │              │
   LOW ───┼──────────────┼──────────────┼─── HIGH
   EFFORT │              │              │   EFFORT
          │              │              │
          │   SKIP       │   CONSIDER   │
          │   (for now)  │   LATER      │
          │              │              │
          └──────────────┼──────────────┘
                         │
                    LOW IMPACT
  ```

-----

## **Self-Paced Exercises (75 minutes total)**

### **Exercise 2.1: Build Transformation Pipeline (25 minutes)**

*Create a working data transformation process*

1. **Select source data:**
   - Use real data from your organization, OR
   - Use the provided sample messy data (below)

**Sample Messy Data (if needed):**
```
Meeting Notes 10/5

Talked to John about the project. He said maybe 2 weeks.
Budget TBD but probably around $50k. Need to check with Sarah.

Action items:
- follow up w/ John
- get Sarah's sign off
- update the doc

Next mtg scheduled
```

2. **Design transformation:**

```markdown
# Transformation Pipeline Design

## Source Analysis
- **Format:** [Current format]
- **Issues identified:**
  1. [Issue]
  2. [Issue]
  3. [Issue]

## Target Format
```[format]
[Target structure]
```

## Transformation Steps

### Step 1: Extract Entities
| Entity Type | Raw Value | Normalized Value |
|-------------|-----------|------------------|
| Person | "John" | "John [Last Name TBD]" |
| Date | "10/5" | "2024-10-05" |
| Amount | "around $50k" | {"value": 50000, "confidence": "approximate"} |

### Step 2: Normalize Structure
[Show structure transformation]

### Step 3: Add Metadata
```yaml
[Metadata to add]
```

### Step 4: Flag Uncertainties
| Field | Issue | Needs Human Review |
|-------|-------|-------------------|
| [Field] | [Issue] | Yes/No |

## Implementation

### Using AI to Transform
```markdown
[Prompt you would use]
```

### Validation Rules
- [ ] [Validation check 1]
- [ ] [Validation check 2]
```

3. **Execute transformation:**
   - Transform the sample data
   - Document the output
   - Note any ambiguities encountered

**Deliverable:** `transformation-pipeline.md` with design and executed example

-----

### **Exercise 2.2: Agent Interface Design (25 minutes)**

*Design data interface between two agents in your system*

```markdown
# Agent-to-Agent Interface Design

## Interface Overview

**Producer Agent:** [Name/Role]
**Consumer Agent:** [Name/Role]
**Purpose:** [What data is exchanged and why]

## Interface Contract

### Request Format (Consumer → Producer)

```json
{
  "$schema": "request-schema-v1",
  "request_id": "string (UUID)",
  "timestamp": "ISO-8601",
  "request_type": "[type from enum]",
  "parameters": {
    // Request-specific parameters
  },
  "context": {
    "caller": "string (agent ID)",
    "priority": "enum: low|normal|high|critical",
    "timeout_seconds": "integer"
  }
}
```

### Response Format (Producer → Consumer)

```json
{
  "$schema": "response-schema-v1",
  "response_id": "string (UUID)",
  "request_id": "string (matching request)",
  "timestamp": "ISO-8601",
  "status": {
    "code": "enum: success|partial|error",
    "message": "string",
    "confidence": "enum: low|medium|high"
  },
  "data": {
    // Response payload
  },
  "metadata": {
    "processing_time_ms": "integer",
    "sources_used": ["array of source identifiers"],
    "limitations": ["array of limitation notes"],
    "assumptions": ["array of assumption notes"]
  },
  "next_steps": {
    "suggested_actions": ["array of recommended actions"],
    "required_validation": ["array of validation needs"]
  }
}
```

## Enumeration Definitions

### Request Types
```yaml
request_types:
  - research: "Gather information on a topic"
  - analyze: "Analyze provided data"
  - generate: "Create new content"
  - validate: "Check/verify information"
  - transform: "Convert data format"
```

### Error Codes
```yaml
error_codes:
  - invalid_request: "Request format invalid"
  - not_found: "Requested information not found"
  - timeout: "Processing time exceeded"
  - partial_failure: "Some but not all operations succeeded"
  - dependency_error: "Required external resource unavailable"
```

## Example Exchange

### Example Request
```json
[Complete example]
```

### Example Response (Success)
```json
[Complete example]
```

### Example Response (Partial)
```json
[Complete example with partial status]
```

## Versioning Strategy

- **Current version:** 1.0
- **Deprecation policy:** [How old versions are handled]
- **Breaking change process:** [How changes are communicated]

## Validation

Consumer should validate:
- [ ] Schema compliance
- [ ] Required fields present
- [ ] Enums match expected values
- [ ] Timestamps are valid
- [ ] IDs are properly formatted
```

**Deliverable:** `agent-interface-design.md`

-----

### **Exercise 2.3: Module Capstone - AI Readiness Assessment (25 minutes)**

*Complete assessment and transformation plan for a data domain*

```markdown
# AI Readiness Assessment Report

## Executive Summary

**Data Domain:** [What was assessed]
**Assessment Date:** [Date]
**Assessor:** [Name]
**Overall Score:** [X/100]
**Readiness Level:** [Not Ready / Basic / Good / Excellent]

**Key Finding:** [One sentence summary]

**Top Recommendation:** [Single most important action]

---

## Assessment Scores

| Dimension | Score | Key Issues |
|-----------|-------|------------|
| Structure | /20 | [Brief summary] |
| Semantics | /20 | [Brief summary] |
| Metadata | /20 | [Brief summary] |
| Freshness | /20 | [Brief summary] |
| Access | /20 | [Brief summary] |
| **Total** | **/100** | |

---

## Detailed Findings

### Structure Assessment

**Score: [X]/20**

| Criterion | Score | Evidence |
|-----------|-------|----------|
| Format consistency | /5 | [What was found] |
| Hierarchical organization | /5 | [What was found] |
| AI-appropriate chunking | /5 | [What was found] |
| Machine parseability | /5 | [What was found] |

**Issues:**
1. [Specific issue with example]
2. [Specific issue with example]

### Semantics Assessment

**Score: [X]/20**

[Same structure as above]

### Metadata Assessment

**Score: [X]/20**

[Same structure as above]

### Freshness Assessment

**Score: [X]/20**

[Same structure as above]

### Access Assessment

**Score: [X]/20**

[Same structure as above]

---

## Transformation Plan

### Quick Wins (< 1 week effort)

| Action | Impact | Effort | Priority |
|--------|--------|--------|----------|
| [Action 1] | +[X] points | [Hours] | 1 |
| [Action 2] | +[X] points | [Hours] | 2 |

### Medium-Term Improvements (1-4 weeks)

| Action | Impact | Effort | Dependencies |
|--------|--------|--------|--------------|
| [Action 1] | +[X] points | [Days] | [What's needed first] |
| [Action 2] | +[X] points | [Days] | |

### Major Initiatives (> 1 month)

| Initiative | Impact | Effort | Considerations |
|------------|--------|--------|----------------|
| [Initiative 1] | +[X] points | [Weeks] | [Key considerations] |

---

## Implementation Roadmap

```
Week 1-2: Quick Wins
├── [Action 1]
├── [Action 2]
└── Score improvement: [X] → [Y]

Week 3-6: Medium-Term
├── [Action 3]
├── [Action 4]
└── Score improvement: [Y] → [Z]

Month 2-3: Major Initiatives
├── [Initiative 1]
└── Target score: [Final]
```

---

## Sample Transformations

### Before (Current State)
```
[Example of current data]
```

### After (Target State)
```
[Example of transformed data]
```

### Transformation Applied
1. [What was changed]
2. [What was added]
3. [What was restructured]

---

## Appendix: Complete Checklist Scores

[Full checklist with all items marked]
```

**Deliverable:** `ai-readiness-assessment.md`

-----
