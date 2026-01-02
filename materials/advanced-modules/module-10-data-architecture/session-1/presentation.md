# **POWERPOINT PRESENTATION: ADVANCED MODULE 10 SESSION 1**
## **Information Architecture for AI**

**Module:** Advanced Module 10: Data Architecture for AI Systems
**Session Number:** 1 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 graduates who need to design, structure, and transform data for optimal AI agent consumption

**Session Learning Objectives:** By the end of this session, participants will:
1. Understand information architecture principles for AI agents
2. Apply semantic structuring patterns to make meaning explicit
3. Select appropriate data formats for different AI use cases
4. Design metadata strategies that enhance agent understanding

**Entry Criteria:**
- [ ] Block 3 completed with working agent system
- [ ] Sample dataset identified for exercises
- [ ] Understanding of how agents consume context
- [ ] Familiarity with at least 2 data formats (JSON, Markdown, YAML, CSV)

**Exit Criteria:**
- [ ] Information architecture principles for AI understood
- [ ] Semantic structuring patterns applied
- [ ] Format selection framework mastered
- [ ] Metadata strategy designed
- [ ] First AI-optimized data structure created

**Presentation Structure:**
1. Opening & Overview (3 min) - Slides 1-3
2. Segment 1: Why Data Structure Matters for AI (10 min) - Slides 4-6
3. Segment 2: Semantic Structuring Patterns (12 min) - Slides 7-10
4. Segment 3: Document Design for AI Consumption (12 min) - Slides 11-14
5. Segment 4: Format Selection Framework (11 min) - Slides 15-18
6. Homework Preview & Close (3 min) - Slides 19-21

**Total Slides:** 21

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Advanced Module 10 Session 1: Information Architecture for AI

**Subtitle:** Designing Data Structures That AI Agents Can Actually Use

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program - Advanced Modules

**Graphic:** Clean title slide with Advanced Module branding (purple/teal tones - advanced learning)

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Advanced Module 10, Data Architecture for AI Systems. This is our first session, focusing on Information Architecture for AI.

You've built agent systems in Block 3. You know how to create workflows, handle context, and orchestrate multi-agent systems. But there's one thing that makes or breaks agent effectiveness: the quality and structure of the data they consume.

Today we're diving into how to design, structure, and optimize data so that AI agents can find it, understand it, and use it effectively."

[Transition: Click to next slide]

---

### SLIDE 2: SESSION OVERVIEW

**Title:** Today's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Overview & Preview |
| 3-13 min | Segment 1 | Why Data Structure Matters for AI |
| 13-25 min | Segment 2 | Semantic Structuring Patterns |
| 25-37 min | Segment 3 | Document Design for AI Consumption |
| 37-48 min | Segment 4 | Format Selection Framework |
| 42-45 min | Close | Homework & Resources |

**Graphic:** Simple timeline showing the session flow

**SPEAKER NOTES:**

"Here's what we'll cover today:

First, we'll establish why data structure matters for AI agents - what's different about how agents consume data compared to humans.

Then, we'll dive into semantic structuring patterns - how to make implicit meaning explicit so agents can understand your data.

In our third segment, we'll look at document design patterns specifically optimized for AI consumption.

And we'll close with a format selection framework - how to choose between JSON, YAML, Markdown, CSV, and other formats for different use cases.

[Pause]

Any questions before we dive in?"

[Transition]

---

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Understand information architecture principles for AI agents**
   - Know what agents need from data (discoverability, context, actionability, reliability)

2. **Apply semantic structuring patterns to make meaning explicit**
   - Transform implicit information into explicit, parseable structures

3. **Select appropriate data formats for different AI use cases**
   - Use decision framework to choose JSON, YAML, Markdown, CSV, or hybrid approaches

4. **Design metadata strategies that enhance agent understanding**
   - Create comprehensive metadata schemas for AI discoverability

**Graphic:** Checklist visual with the four objectives

**SPEAKER NOTES:**

"These are our four objectives for today. By the time you leave this session, you'll be able to:

[Read each objective, pausing briefly after each]

Notice that these are all ACTION-focused. This isn't about knowing concepts - it's about DOING things with data. You'll practice each of these in your homework exercises.

[Point to first objective]

This one is foundational - understanding what makes AI-ready data different from human-friendly data.

Let's get started."

[Transition: Click to Segment 1]

---

## SEGMENT 1: Why Data Structure Matters for AI
### Duration: 10 minutes | Slides 4-6

---

### SLIDE 4: THE FUNDAMENTAL CHALLENGE

**Title:** Humans vs. AI Agents: The Data Gap

**Content:**

```
HUMANS                           AI AGENTS
─────────────────────────────    ─────────────────────────────
Infer context from experience    Need context made explicit
Navigate ambiguity naturally     Require clear structure
Understand implicit meaning      Process explicit patterns
Fill gaps from memory            Limited to provided context
```

**Graphic:** Split-screen visual contrasting human and AI approaches to data consumption

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Let me ask you a question: When you read meeting notes that say 'John thinks we should wait,' what do you understand?

[Pause - let question land]

You probably infer who John is from context. You understand 'wait' means defer a decision. You know approximately when based on the meeting date.

The reality is AI agents can't make those inferences. They process what's explicitly stated. And this costs us in hallucinations, misinterpretations, and failed automations.

[Point to graphic]

The fundamental challenge is this gap between how humans and agents consume data. Humans bring context and experience. Agents work with what's in front of them.

Today we're going to bridge this gap. Here's how..."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide establishes the core problem that the entire module addresses
- Creates emotional buy-in for the techniques that follow
- Makes abstract data architecture concrete and relatable

**Q&A Preparation:**
- *"But agents are getting smarter - won't they figure this out?"*: Yes, but explicit structure is always more reliable and efficient than inference
- *"Isn't this just over-documenting?"*: No - it's making existing information explicit rather than implicit

---

### SLIDE 5: WHAT AGENTS NEED FROM DATA

**Title:** The Four Requirements for AI-Ready Data

**Content:**

**1. Discoverability**
- Can the agent find what it needs?
- Is content indexed, tagged, searchable?

**2. Context**
- Does the agent understand what it found?
- Are relationships, definitions, scope explicit?

**3. Actionability**
- Can the agent use what it found?
- Is data in parseable, structured formats?

**4. Reliability**
- Is the data consistent and trustworthy?
- Are status, freshness, authority clear?

**Graphic:** Four-quadrant diagram showing each requirement with icons

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"AI-ready data must satisfy four requirements:

First, DISCOVERABILITY. If an agent can't find the information, it doesn't exist. This means proper metadata, tagging, and indexing.

Second, CONTEXT. Finding information isn't enough - the agent must understand it. This means explicit relationships, clear definitions, and stated scope.

Third, ACTIONABILITY. The agent needs to USE the information. This means parseable formats, consistent structure, and clear schemas.

Fourth, RELIABILITY. The agent must trust what it finds. This means tracking status, freshness, ownership, and authority.

[Point to graphic]

Every data architecture decision we make today comes back to these four requirements.

Let me show you what happens when we ignore them..."

[Transition to next slide]

**BACKGROUND:**

**Key Research & Citations:**
- Based on Block 3 MCP server patterns and agent context limitations
- Builds on Domain Memory Meta-Framework principles

---

### SLIDE 6: THE COST OF POOR DATA STRUCTURE

**Title:** What Happens When Data Structure Fails

**Content:**

| Problem | Agent Symptom | Business Impact |
|---------|---------------|-----------------|
| Missing context | Hallucination, wrong assumptions | Incorrect outputs |
| Ambiguous structure | Misinterpretation | Unreliable results |
| Inconsistent format | Parsing failures | System errors |
| Implicit meaning | Missed information | Incomplete work |

**Design Principle:**
> "Structure your data as if the reader has no background knowledge, unlimited attention to detail, and zero tolerance for ambiguity."

**Graphic:** Table with real examples of each failure mode

**SPEAKER NOTES:**

"Here are the failure modes:

[Walk through each row]

Missing context leads to hallucinations - the agent fills in gaps with plausible but wrong information.

Ambiguous structure causes misinterpretation - 'wait for approval' could mean many things.

Inconsistent formats break parsing - sometimes dates are MM/DD, sometimes DD/MM.

Implicit meaning gets missed entirely - pronouns, abbreviations, assumed knowledge.

[Point to design principle]

This gives us our guiding principle: Structure data as if the reader has no background knowledge, unlimited attention to detail, and zero tolerance for ambiguity.

That's the mindset shift. Now let's see how to do it."

[Transition: Click to Segment 2]

---

## SEGMENT 2: Semantic Structuring Patterns
### Duration: 12 minutes | Slides 7-10

---

### SLIDE 7: MAKING MEANING EXPLICIT

**Title:** From Implicit to Explicit: A Transformation

**Content:**

**Bad (implicit meaning):**
```
Meeting Notes - Q4 Planning

Discussed budget. John thinks we need more.
Sarah disagrees. Decision: revisit next week.
```

**Good (explicit meaning):**
```markdown
# Meeting Notes: Q4 Planning
**Date:** 2024-10-15
**Attendees:** John Smith (Finance), Sarah Chen (Operations)
**Status:** Pending Decision

## Topic: Q4 Budget Allocation
### Positions
- **John Smith (Finance):** Recommends 15% budget increase
  - Rationale: Market expansion opportunity
- **Sarah Chen (Operations):** Recommends maintaining current budget
  - Rationale: Uncertain economic conditions

### Decision
- **Status:** Deferred
- **Next Step:** Revisit at Oct 22 meeting
- **Owner:** John Smith
```

**Graphic:** Before/after comparison

**SPEAKER NOTES:**

"[DEMO - Show transformation]"

"Let me show you the difference between implicit and explicit data.

[Point to top example]

Here's typical meeting notes. 'John thinks we need more.' An agent reading this has no idea who John is, what 'more' means, or what the decision was.

[Point to bottom example]

Here's the same information made explicit. John becomes 'John Smith (Finance)' with his full position stated. 'More' becomes '15% budget increase with market expansion rationale.' 'Next week' becomes 'Oct 22 meeting.'

Notice we didn't add much text - we clarified what was already there.

This is semantic structuring: making the implicit explicit.

Let me break down the patterns..."

[Transition]

---

### SLIDE 8: SEMANTIC PATTERNS

**Title:** Four Core Semantic Patterns

**Content:**

**1. Explicit Labels**
- Replace pronouns with names
- Replace "this" and "that" with specific references
- State relationships explicitly

**2. Consistent Taxonomy**
```
Status: Draft | Review | Approved | Archived
Priority: Critical | High | Medium | Low
Type: [Defined list for your domain]
```

**3. Context Headers**
- Every section states its purpose
- Relationships to other sections explicit
- Scope and limitations stated

**4. Actionable Structure**
```markdown
## Decision Required
**Question:** [Specific question]
**Options:** [Numbered with costs/timelines]
**Deadline:** [Absolute date]
**Decision Maker:** [Named individual]
```

**Graphic:** Four-quadrant layout with examples of each pattern

**SPEAKER NOTES:**

"Here are the four core patterns:

Pattern 1: Explicit Labels. No pronouns, no 'this/that,' no ambiguous references. Everything named.

Pattern 2: Consistent Taxonomy. Define your controlled vocabularies upfront. Status isn't 'done-ish' or 'mostly ready' - it's one of four defined values.

Pattern 3: Context Headers. Every section declares what it contains, how it relates to other sections, and what it doesn't cover.

Pattern 4: Actionable Structure. Decisions, tasks, and actions have standardized formats that agents can parse reliably.

[Pause]

Let me show you how to apply these..."

[Transition]

---

### SLIDE 9: THE SEMANTIC CHECKLIST

**Title:** Five Questions for Every Data Structure

**Content:**

Before finalizing any document or data structure, ask:

- [ ] **Who/what is being discussed?** (Named, not implied)
- [ ] **When?** (Dates explicit, not relative)
- [ ] **What's the status?** (From defined taxonomy)
- [ ] **What action is needed?** (Clear next steps)
- [ ] **Who owns it?** (Named individual)

**Example Application:**
```
❌ "We should review this next quarter"
✓ "John Smith (Project Lead) will review this requirements document
   (status: draft) by 2024-10-01 to approve Phase 2 initiation"
```

**Graphic:** Checklist format with red X / green checkmark examples

**SPEAKER NOTES:**

"Use this five-question checklist on everything:

Who/what - no pronouns, everything named
When - absolute dates, no 'next week' or 'soon'
Status - from your defined taxonomy
Action - what specifically needs to happen
Owner - who is responsible

[Point to example]

See the transformation? Same intent, but the second version answers all five questions explicitly.

This is what makes data AI-ready."

[Transition]

---

### SLIDE 10: SEGMENT 2 SUMMARY

**Title:** Semantic Structuring: Key Takeaways

**Content:**

**Key Takeaway:** Agents process what's explicit, not what's implied. Make every piece of information stand alone.

**Remember:**
- Replace all pronouns and ambiguous references with specific names
- Define taxonomies for status, priority, type - then use them consistently
- Structure decisions and actions with complete context
- Use the five-question checklist on everything

**You'll Practice:**
Exercise 1.1 - Semantic Structure Analysis

**Graphic:** Simple visual reinforcing explicit vs implicit

**SPEAKER NOTES:**

"Before we move on, key points:

Agents process what's explicit. If it's implied, assumed, or contextual - it doesn't exist for the agent.

Use the patterns: explicit labels, consistent taxonomy, context headers, actionable structure.

Run everything through the five-question checklist.

In your homework, Exercise 1.1 gives you hands-on practice transforming implicit data into explicit structures.

[Pause]

Any questions on semantic structuring before we move to document design?"

[Transition: Click to Segment 3]

---

## SEGMENT 3: Document Design for AI Consumption
### Duration: 12 minutes | Slides 11-14

---

### SLIDE 11: HIERARCHICAL CONTEXT PATTERN

**Title:** Building Context Layers for AI

**Content:**

```
Level 1: DOMAIN CONTEXT
└── What area of knowledge is this?
    └── Level 2: DOCUMENT PURPOSE
        └── Why does this document exist?
            └── Level 3: SECTION CONTENT
                └── What specific information?
                    └── Level 4: DETAILS
                        └── Supporting specifics
```

**Key Principle:** Each level provides context for the level below

**Graphic:** Tree diagram showing hierarchical context layers

**SPEAKER NOTES:**

"Document structure needs to build context hierarchically.

Level 1 establishes the domain - what area of knowledge.
Level 2 states the document's purpose - why it exists.
Level 3 contains section-specific content.
Level 4 provides supporting details.

Each level gives context for what follows. An agent reading Level 4 details has already absorbed Levels 1-3 context.

This prevents the 'lost in details' problem where agents miss the forest for the trees.

Let me show you the template..."

[Transition]

---

### SLIDE 12: AI-OPTIMIZED DOCUMENT TEMPLATE

**Title:** Standard Document Structure for AI Consumption

**Content:**

```markdown
# [Document Title]

> **Purpose:** [One sentence: why this document exists]
> **Audience:** [Who should read this]
> **Last Updated:** [Date]
> **Owner:** [Name/Role]

## Overview
[2-3 sentence summary - agent uses this to assess relevance]

## Context
[Background needed to understand this document]
- Related documents: [Links]
- Prerequisites: [What reader should know]
- Scope: [What this covers and doesn't cover]

## [Main Content Sections]
[Structured content with consistent patterns]

## Summary
[Key takeaways in structured format]

## Metadata
- Tags: [Searchable keywords]
- Category: [From taxonomy]
- Status: [From status taxonomy]
```

**Graphic:** Document structure diagram

**SPEAKER NOTES:**

"Here's your standard template for AI-ready documents.

[Walk through each section]

The header block gives critical metadata upfront - purpose, audience, freshness, ownership.

Overview provides a decision point - should the agent read further?

Context section explicitly states prerequisites, relationships, and scope.

Main content follows your domain patterns.

Summary section at the end reinforces key points.

Metadata makes the document discoverable.

Every section serves a purpose for the agent. Nothing is decorative.

Notice what this enables..."

[Transition]

---

### SLIDE 13: NAVIGATION AIDS FOR AGENTS

**Title:** Helping Agents Find Their Way

**Content:**

**1. Tables of Contents** with descriptive entries
- ❌ "Section 3"
- ✓ "Section 3: Authentication Requirements"

**2. Cross-References** with context
- ❌ "See Section 3"
- ✓ "See Section 3: Authentication Requirements for API security details"

**3. Summary Sections** at both start and end
- Top: Decision point for relevance
- Bottom: Reinforcement of key points

**4. Consistent Heading Patterns** agents can parse
- Use semantic heading levels (H1 = document, H2 = major sections, etc.)

**Graphic:** Examples of good vs bad navigation patterns

**SPEAKER NOTES:**

"Agents need navigation aids just like humans - but more explicit.

[Walk through each]

Tables of contents should be descriptive, not just section numbers.

Cross-references must include context - what will the agent find there and why it matters.

Summaries at top and bottom serve different purposes - filtering and reinforcement.

Consistent heading hierarchy lets agents understand document structure programmatically.

These aren't optional niceties - they're requirements for AI consumption.

One more critical piece: chunking..."

[Transition]

---

### SLIDE 14: CHUNKING FOR AI

**Title:** Right-Sizing Content for Agent Context Windows

**Content:**

| Content Type | Recommended Chunk Size | Why |
|--------------|------------------------|-----|
| Reference docs | 500-1000 tokens | Self-contained lookups |
| Procedures | Full procedure | Need complete steps |
| Policies | Full section | Context-dependent |
| Meeting notes | Per topic/decision | Discrete units |
| Code docs | Per function/class | Logical units |

**Key Insight:** Chunk at semantic boundaries, not arbitrary lengths

**Graphic:** Visual showing different chunking strategies

**SPEAKER NOTES:**

"AI agents have context window limits. How you chunk matters.

[Walk through table]

Reference docs should be bite-sized - 500-1000 tokens per concept.

Procedures need to stay together - splitting steps loses coherence.

Policies chunk at section level - each section is context-dependent.

Meeting notes chunk per decision or topic - natural semantic units.

Code documentation chunks per function or class.

The key: chunk at semantic boundaries. Don't split in the middle of a thought just to hit a token count.

This is document design. Now let's talk formats..."

[Transition: Click to Segment 4]

---

## SEGMENT 4: Format Selection Framework
### Duration: 11 minutes | Slides 15-18

---

### SLIDE 15: FORMAT COMPARISON FOR AI USE CASES

**Title:** Choosing the Right Format for AI Agents

**Content:**

| Format | Best For | Agent Strengths | Agent Weaknesses |
|--------|----------|-----------------|------------------|
| **JSON** | Structured data, APIs, configs | Precise parsing, type safety | Verbose, hard to read in prompts |
| **YAML** | Configuration, human-edited | Readable, comments allowed | Whitespace-sensitive, edge cases |
| **Markdown** | Documents, mixed content | Natural in prompts, flexible | Less parseable structure |
| **CSV** | Tabular data, simple records | Compact, universal | No nesting, type ambiguity |
| **XML** | Complex hierarchies, schemas | Strong validation | Verbose, complex to process |

**Graphic:** Format comparison matrix

**SPEAKER NOTES:**

"Different formats serve different purposes. Let's compare:

JSON: Great for structured data - precise, type-safe. But verbose and hard to read in large prompts.

YAML: Human-friendly configuration. Comments, readable. But whitespace-sensitive and has parsing edge cases.

Markdown: Natural for documents and mixed content. Works beautifully in prompts. But less structured for pure data.

CSV: Perfect for simple tabular data. Compact, universal. But can't handle nesting or complex types.

XML: Powerful for complex hierarchies with validation. But verbose and complex.

No single winner - it depends on your use case. Here's the decision framework..."

[Transition]

---

### SLIDE 16: FORMAT SELECTION DECISION TREE

**Title:** Which Format Should You Use?

**Content:**

```
START
  │
  ├─ Is data primarily tabular with flat structure?
  │   └─ YES → CSV (or JSON Lines for streaming)
  │
  ├─ Does data need strict typing and validation?
  │   └─ YES → JSON with schema
  │
  ├─ Is data human-edited configuration?
  │   └─ YES → YAML
  │
  ├─ Is content primarily narrative/documents?
  │   └─ YES → Markdown with frontmatter
  │
  ├─ Does data have complex nested relationships?
  │   └─ YES → JSON (or XML if validation critical)
  │
  └─ Mixed content with structure + narrative?
      └─ Markdown with embedded JSON/YAML blocks
```

**Graphic:** Decision tree flowchart

**SPEAKER NOTES:**

"Use this decision tree:

Start with the nature of your data.

Tabular and flat? CSV is your friend.

Need strict typing and validation? JSON with a schema.

Human-edited configuration? YAML for readability.

Narrative documents? Markdown, potentially with YAML frontmatter.

Complex nested relationships? JSON for most cases, XML if you need heavy validation.

Mixed content - both structure and narrative? Hybrid approach with Markdown and embedded structured blocks.

Let me show you that hybrid pattern - it's powerful..."

[Transition]

---

### SLIDE 17: HYBRID PATTERNS

**Title:** The Best of Both Worlds: Markdown + Structured Data

**Content:**

```markdown
---
# YAML frontmatter for metadata
title: Project Requirements
status: approved
owner: jane.smith
tags: [requirements, phase-1, approved]
---

# Project Requirements

## Overview
[Narrative content in Markdown]

## Requirements

```json
{
  "requirements": [
    {
      "id": "REQ-001",
      "priority": "high",
      "description": "System shall support SSO",
      "status": "approved"
    }
  ]
}
```

## Discussion
[More narrative content]
```

**Graphic:** Annotated example showing three layers: YAML metadata, Markdown narrative, embedded JSON data

**SPEAKER NOTES:**

"This is a hybrid pattern - combining formats for maximum effectiveness.

[Point to YAML section]
YAML frontmatter provides machine-readable metadata.

[Point to Markdown sections]
Markdown handles narrative content beautifully.

[Point to JSON block]
Embedded JSON gives you structured data with full type safety.

Agents can parse all three layers. You get discoverability from YAML, readability from Markdown, and structure from JSON.

This is increasingly the pattern for AI-ready documentation.

One critical rule..."

[Transition]

---

### SLIDE 18: CONSISTENCY RULES

**Title:** Format Consistency Across Your System

**Content:**

**The Three Consistency Rules:**

1. **Pick ONE format per data type across your system**
   - All meeting notes: Same format
   - All API configs: Same format
   - All requirements: Same format

2. **Document format decisions**
   - Create format selection record
   - Explain rationale for each choice
   - Make it findable for team members

3. **Provide conversion utilities when needed**
   - JSON ↔ CSV for reporting
   - Markdown ↔ JSON for data extraction
   - Document conversion approaches

**Why It Matters:** Agents learn patterns. Consistency = reliability.

**Graphic:** Consistency diagram showing format decisions

**SPEAKER NOTES:**

"Three consistency rules:

Rule 1: Pick one format per data type. If meeting notes are Markdown with YAML frontmatter, ALL meeting notes use that format. No mixing.

Rule 2: Document why you chose each format. Future you will forget. New team members need to know.

Rule 3: Provide conversions when you need different views of the same data. But the source of truth stays in ONE format.

[Pause]

Why does this matter? Agents learn patterns. When every meeting note has the same structure, the agent can reliably extract decisions, action items, attendees. Inconsistency breaks that.

Consistency is a feature, not a constraint."

[Transition to closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 19-21

---

### SLIDE 19: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 1.1: Semantic Structure Analysis | 25 min | `semantic-structure-analysis.md` | Making implicit meaning explicit |
| Exercise 1.2: Format Selection Design | 25 min | `format-selection-design.md` | Applying format decision framework |
| Exercise 1.3: Metadata Strategy | 25 min | `metadata-strategy.md` | Designing metadata schema |
| **Total** | **75 min** | | |

**Graphic:** Exercise icons showing the progression

**SPEAKER NOTES:**

"Here's your homework for this week. You have 75 minutes of exercises.

Exercise 1.1 takes about 25 minutes. You'll take a real document and transform it using semantic structuring patterns. You'll see exactly how much implicit information exists in typical documents.

Exercise 1.2 is format selection. You'll design a format strategy for a data domain, applying the decision framework from today.

Exercise 1.3 is metadata strategy. You'll create a comprehensive metadata schema for AI discoverability.

These build on each other, so complete them in order.

All detailed instructions are in your participant guide, including templates."

[Transition]

---

### SLIDE 20: RESOURCES

**Title:** Resources for This Session

**Content:**

**Templates & Files:**
- Semantic Structure Analysis Template - Appendix A
- Format Selection Template - Appendix B
- Document Structure Template - Session materials

**Reference Materials:**
- Block 3 MCP Server Documentation
- JSON Schema specification
- YAML specification

**Support:**
- Questions: [Async channel name]
- Office Hours: [Time/location if applicable]

**Graphic:** QR codes or links for quick access

**SPEAKER NOTES:**

"You have several resources:

Templates for each exercise are in the appendices and session materials.

Reference materials include links to format specifications and Block 3 MCP documentation.

If you get stuck, post in the async channel. Response time is usually within 24 hours.

[If office hours exist]: We also have office hours [time] for live support."

[Transition]

---

### SLIDE 21: NEXT SESSION PREVIEW

**Title:** Next Session: Data Transformation & Agent Interfaces

**Content:**

**Preview:**
Building transformation pipelines and designing agent-to-agent data interfaces

**What to Complete Before Then:**
- [ ] Exercise 1.1: Semantic Structure Analysis
- [ ] Exercise 1.2: Format Selection Design
- [ ] Exercise 1.3: Metadata Strategy

**Key Preparation:**
Bring your format selection design - we'll build transformation pipelines for it

**What's Coming:**
- Data transformation architecture
- Enterprise data challenges
- Agent-to-agent interface patterns
- AI readiness assessment
- Module capstone project

**Graphic:** Preview image showing transformation pipeline

**SPEAKER NOTES:**

"Next session we'll cover data transformation and agent interfaces. This is where we take real enterprise data and transform it into AI-ready formats.

[Brief preview]

You'll learn transformation patterns, how to handle messy real-world data, and how to design interfaces between agents.

Make sure you've completed all three exercises before next session - we'll build on them directly.

The format selection design you create this week will become the foundation for your transformation pipeline next week.

[Final close]

Great session today. Remember: the goal is making implicit information explicit. Start seeing your data through an agent's eyes.

See you next week!"

---

## Appendix: Presentation Notes

### Total Timing Breakdown
- Opening: 3 min (Slides 1-3)
- Segment 1: 10 min (Slides 4-6)
- Segment 2: 12 min (Slides 7-10)
- Segment 3: 12 min (Slides 11-14)
- Segment 4: 11 min (Slides 15-18)
- Closing: 3 min (Slides 19-21)
- **Total: 45 minutes**

### Key Messages to Repeat
1. "Agents process what's explicit, not what's implied"
2. "Structure data for zero background knowledge and zero ambiguity"
3. "Consistency is a feature, not a constraint"

### Backup Plans
- If demos fail: Use screenshots from materials
- If running long: Slides 13-14 can be shortened to 5 min total
- If running short: Add Q&A time at end of Segment 2

### Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | [Your name] |
