# **INSTRUCTOR GUIDE: MODULE 3 SESSION 2**
## **Validation in Practice**

**Module:** Advanced Module 3: JSON Schema & Data Validation
**Session:** 2 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Implementing runtime validation in production workflows with error handling |
| **Difficulty Level** | Medium-High - requires integration with existing workflows |
| **Prep Time Required** | 45 minutes |
| **Demo Required** | Yes - Validation in a real workflow (Make/n8n/code) |
| **Tech Setup Needed** | Workflow platform ready, validation library installed, example workflow prepared |
| **Common Challenges** | Platform-specific implementation details, retry logic complexity |

---

## Navigation

**Module Navigation:** [← Session 1 Instructor Guide](../session-1/instructor-guide.md) | Session 2

**Related Materials:**
- [Session 2 Presentation Slides](presentation.md)
- [Session 2 Participant Guide](participant-guide.md)
- [Module 3 Main Document](../module-3-json-schema.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Session 2 materials | ☐ |
| Test demo | Run validation demo in your workflow platform | ☐ |
| Check resources | Verify ajv/validation libraries are accessible | ☐ |
| Prepare backup | Create screenshots of validation working | ☐ |
| Review Session 1 | Check what participants completed | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice transitions and demo | ☐ |
| Prepare materials | Have workflow with validation ready | ☐ |
| Check participant schemas | Review submissions from Session 1 | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, workflow platform, code examples | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Brief chat, answer questions about Session 1 | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Session 1 recap, preview | Quick engagement check |
| 0:03 | 12 min | Segment 1 | Validation in Workflows | Validation points, pattern, platforms |
| 0:15 | 12 min | Segment 2 | Validating AI Outputs | AI challenges, retry strategies, demo |
| 0:27 | 12 min | Segment 3 | Error Handling | Error formatting, logging, improvement |
| 0:39 | 9 min | Segment 4 | Schema Documentation | Self-documenting, tools, schema-driven dev |
| 0:48 | 3 min | Closing | Capstone overview, resources | Emphasize module completion |
| **Total** | **51 min** | | | 6-min buffer included |

### Timing Flexibility

**If Running Behind:**
- Segment 4: Skip documentation generation tools, focus on self-documenting schemas
- Segment 3: Shorten logging discussion
- Segment 2: Reduce number of retry strategy examples
- Keep Segment 1 and AI output demo intact - critical for practical implementation

**If Running Ahead:**
- Segment 2: Show more error recovery examples
- Segment 3: Demonstrate log analysis
- Extended Q&A on platform-specific implementation

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | If behind, shorten Segment 2 examples |
| End Segment 2 | 0:27 | Critical - must complete AI validation demo |
| End Segment 3 | 0:39 | If behind, abbreviate Segment 4 |
| Start Closing | 0:48 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants
2. Quick recap of Session 1
3. Engagement check on Session 1 exercises
4. Preview Session 2 focus

**Opening Script:**
> "Welcome to Session 2 - our final session for this module. Last session you learned JSON Schema syntax and created your schema library.
>
> Quick check-in: Who completed all three exercises from Session 1? [Show of hands]
>
> Great! Today we're taking those schemas and putting them into production workflows. You'll learn where to validate, how to handle AI outputs that don't match your schema, and how to build robust error handling.
>
> By the end, you'll have a complete validated workflow system - the module capstone."

**Engagement Opportunity:**
> "Who saw a validation error when testing their schemas? What did you learn from it?"

[Wait for 1-2 responses - validates that they actually tested their schemas]

---

### Segment 1: Validation in Workflows (12 minutes)

**Learning Objective:** Implement runtime validation at key workflow points

**Slides:** 4-7

#### Content Delivery

**Key Point 1: Four Validation Points (Slide 4)**
- Main message: Validate at input, AI output, inter-step, and final points
- Example to use: Show workflow diagram with validation gates
- Common misconception: "One validation point is enough" - need defense in depth

**Key Point 2: Validation Pattern (Slide 5)**
- Main message: Parse → Validate → Branch → Handle is universal pattern
- Demonstration: Walk through flowchart
- Participant relevance: Same pattern works everywhere

**Key Point 3: Platform Implementation (Slide 6)**
- Main message: Platform doesn't matter - pattern is the same
- Show code examples for Make, n8n, JavaScript, Python
- This is where participants see how to do it in their platform

#### Demo Instructions (Critical)

**Demo Duration:** 6 minutes

**Setup Required:**
- Working workflow in Make/n8n or code
- Schema file ready
- Test data (valid and invalid)
- Error handler configured

**Demo Steps:**
1. Show workflow with validation step
2. Run with valid data - show it passes through
3. Run with invalid data - show validation catches it
4. Show error handler receiving the failure
5. Point out error message with details

**Demo Talking Points:**
> "Watch what happens when I send valid data... validation passes, workflow continues.
>
> Now I'll send data missing a required field... see how validation catches it? The error handler receives the validation error with full details about what's wrong.
>
> This is defense in depth. Bad data never makes it past this validation gate."

**Backup Plan:**
If demo fails:
1. Use prepared screenshots showing validation pass/fail
2. Walk through the configuration conceptually
3. Emphasize the pattern even without live demo

#### Facilitation Notes

**Watch For:**
- Platform-specific confusion - participants on different platforms may need different guidance
- Questions about where to add validation - emphasize starting with input + AI output

**If Asked About Platform X:**
> "The pattern is the same on all platforms. For [Platform X] specifically, see the participant guide which has detailed instructions. The key is: parse, validate, branch, handle errors."

**Transition to Segment 2:**
> "Now you know WHERE to validate and the pattern to use. Let's tackle the trickiest validation point: AI outputs..."

---

### Segment 2: Validating AI Outputs (12 minutes)

**Learning Objective:** Validate AI outputs with retry and recovery strategies

**Slides:** 8-11

#### Content Delivery

**Key Point 1: AI Challenge (Slide 8)**
- Main message: AI is non-deterministic - validation is mandatory
- Visual to emphasize: Examples of AI output variations
- Real impact: 1-5% failure rate without validation

**Key Point 2: Schema in Prompt (Slide 9)**
- Main message: Include schema in prompt as prevention
- Example: Show prompt with embedded schema
- Critical note: Still must validate afterward

**Key Point 3: Post-Generation Validation (Slide 10)**
- Main message: Validate and recover with multiple strategies
- Framework: Try/catch with parse and schema validation
- Recovery ladder: Retry → Auto-fix → Partial → Escalate

#### Demo Instructions

**Demo Duration:** 5 minutes

**Setup Required:**
- AI generation step in workflow
- Prompt with schema included
- Validation after generation
- Retry logic configured

**Demo Steps:**
1. Show prompt with schema embedded
2. Generate AI output
3. Validate the output
4. If fails (or use prepared failure), show retry logic
5. Show error with recovery strategy

**Demo Talking Points:**
> "Notice the prompt includes the complete schema. I'm showing the AI exactly what I want.
>
> AI generates... now we validate. If this fails, we don't just give up. We retry with a stricter prompt, or attempt to auto-fix minor issues.
>
> This graceful degradation is what makes the system production-ready."

**Backup Plan:**
If AI doesn't fail:
1. Have prepared example of validation failure
2. Walk through what would happen
3. Show retry prompt logic

#### Facilitation Notes

**Watch For:**
- Concern about retry complexity - reassure that starting simple is fine
- Questions about when to escalate - provide clear decision criteria

**If Asked About Retry Limits:**
> "Start with 2-3 retries max. More than that and you're wasting time. Escalate to human review if automatic recovery fails."

**Transition to Segment 3:**
> "You've seen how to validate and retry. But what about when validation fails? Let's make those errors useful..."

---

### Segment 3: Error Messages and Debugging (12 minutes)

**Learning Objective:** Create actionable error messages from validation failures

**Slides:** 12-15

#### Content Delivery

**Key Point 1: Error Information (Slide 12)**
- Main message: Raw validator errors need transformation
- Comparison: Show raw vs useful error side-by-side
- Key difference: Path, message, expected vs actual

**Key Point 2: Human-Readable Format (Slide 13)**
- Main message: Format errors for humans with clear structure
- Code example: Error formatting function
- Output: Numbered errors with full context

**Key Point 3: Logging and Patterns (Slide 14)**
- Main message: Log everything, analyze patterns, improve
- Framework: Continuous improvement loop
- Data-driven: Use logs to identify issues

#### Practical Application

**Consulting Connection:**
> "When a client workflow breaks, you need to debug fast. Clear error messages and good logs mean you can identify and fix issues in minutes instead of hours. That's the difference between a minor hiccup and a client emergency."

**Example Scenario:**
> "Imagine you notice AI output validation failing 10% of the time. Your logs show it's always the same field - 'recommendations' array is coming back as null. Now you know exactly what to fix in your prompt: explicitly require the recommendations array with at least one item."

#### Facilitation Notes

**Common Confusion Point:**
Participants may not see value in detailed logging initially

**Clarification Approach:**
> "You might think logging is overhead, but the first time you need to debug a production failure, you'll be grateful. Logs give you the forensic data to understand what went wrong and prevent it from happening again."

**Transition to Segment 4:**
> "We've covered validation, recovery, and error handling. Let's close with how schemas serve double duty as documentation..."

---

### Segment 4: Schema Documentation (9 minutes)

**Learning Objective:** Generate documentation from schemas for team reference

**Slides:** 16-18

#### Content Delivery

**Key Point 1: Self-Documenting (Slide 16)**
- Main message: Schemas with good titles and descriptions are documentation
- Example: Show well-documented schema
- Benefit: Always accurate because it IS the validation

**Key Point 2: Documentation Tools (Slide 17)**
- Main message: Tools generate docs automatically from schemas
- Quick overview: json-schema-to-markdown, docson, redoc
- Generated example: Show markdown output

**Key Point 3: Schema-Driven Development (Slide 18)**
- Main message: Put schemas first in workflow design
- Pattern: Define schema → Generate examples → Include in prompts → Validate → Document
- Benefits: Clear contracts, better compliance, automatic docs

#### Closing This Segment

**Key Takeaway:**
> "Your schemas are working double duty: validation at runtime and documentation for your team. Invest time in good titles, descriptions, and structure. It pays off immediately."

**Connection to Homework:**
> "In the capstone exercise, you'll document your complete validated workflow system, including your schema library as team reference."

---

### Closing (3 minutes)

**Slides:** 19-21

**Do Not Skip This Section**

#### Homework Preview

**Key Actions:**
1. Overview all three exercises
2. Emphasize that Exercise 2.3 is the module capstone
3. Note estimated times (60 minutes total)
4. Point to evaluation rubric in Appendix C

**Script:**
> "Your homework completes the module with the capstone project.
>
> Exercise 2.1 - 20 minutes - add validation to your actual workflow at input and AI output points.
>
> Exercise 2.2 - 20 minutes - build a complete error handler with formatting and recovery.
>
> Exercise 2.3 - 20 minutes - the capstone: document your complete validated workflow system with statistics and lessons learned.
>
> Appendix C has the evaluation rubric showing what makes a strong capstone submission.
>
> Everything you need is in your participant guide."

#### Resources and Support

> "If you get stuck, post in [support channel]. For platform-specific questions, check the participant guide which has detailed instructions for Make, n8n, and custom code.
>
> Appendix B lists all validation tools by platform."

#### Module Completion

> "When you finish the capstone, you'll have completed Advanced Module 3. You'll have a production-ready validated workflow system that's robust, debuggable, and well-documented.
>
> Congratulations on making it this far. This is advanced stuff and you've handled it well."

#### Session Close

> "Questions before we wrap? ... Great work throughout this module. See you in your next training!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Do I really need validation at all four points? Isn't that overkill?**
A: You can start with input + AI output validation - those are the most critical. Add inter-step and final validation as your workflow complexity grows. But having multiple validation points is defense in depth that prevents cascading failures.

**Q: What if validation slows down my workflow?**
A: Validation is fast - typically adds only milliseconds. The time you save on debugging failures far exceeds any validation overhead. Plus, catching errors early prevents wasted processing on bad data.

**Q: How many retries should I allow for AI output validation?**
A: 2-3 retries maximum. More than that and you're wasting time. If automatic recovery fails after 3 attempts, escalate to human review.

### Technical Questions

**Q: Which validation library should I use?**
A: For JavaScript, use ajv - it's the fastest and most popular. For Python, use jsonschema - it's the reference implementation. For Make.com, use the built-in JSON module. For n8n, use ajv in a Function node.

**Q: How do I implement retry logic in Make/n8n?**
A: In Make, use Router with filters based on validation result. In n8n, use IF node to branch on validation, with loop-back for retries (limit iterations). Detailed instructions are in the participant guide.

**Q: Can I auto-fix validation errors?**
A: For minor issues, yes. Coercing "4" string to 4 number is safe. Using default for missing optional field is safe. But don't try to fix structural issues - those need human review.

### Scope Questions

**Q: What about validating data from third-party APIs?**
A: "Absolutely - create schemas for third-party data too. You can't control what they send, but you can validate it immediately and handle unexpected changes. Same pattern applies."

**Q: Should I validate configuration files like style.json?**
A: "Yes! Configuration validation is just as important. Your workflow assumes style.json has certain fields - validate on load to catch issues early."

### Pushback/Objections

**Q: This seems like a lot of extra work for uncertain benefit.**
A: I understand the concern. Here's the reality: implementing validation at one critical point takes 30 minutes. The first time it catches a bad AI output before it reaches a client, it's paid for itself. The ROI is immediate and ongoing. Start small - add validation to your most critical workflow and measure the impact.

**Q: Can't I just handle errors as they come up?**
A: Reactive error handling means you're firefighting. Every failure is a surprise, debugging is slow, and clients see errors. Proactive validation means errors are caught automatically, you have full context for debugging, and clients never see the failures. Which approach protects your reputation better?

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Screen share fails | Restart share, switch to window share | Have participant share to show their implementation |
| Workflow demo breaks | Acknowledge, debug briefly | Use prepared screenshots, continue conceptually |
| Validation library not working | Check installation, version | Show code conceptually, fix in office hours |
| AI doesn't fail validation | Use prepared failure example | Show what would happen with failure |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Platform confusion | Questions about "how do I do this in [platform]?" | Point to participant guide platform-specific sections |
| Retry logic complexity | "This is getting complicated" | Start simple - one retry max, then expand |
| Don't see value in logging | "Why log if validation passed?" | Explain pattern analysis and continuous improvement |
| Overwhelmed by options | "Too many recovery strategies" | Start with retry only, add others as needed |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Content too platform-specific | Questions only about one platform | Keep discussion pattern-focused, point to guides for specifics |
| Want deep-dive on error handling | Many detailed questions | "Great topic - let's discuss in [channel] to not lose the group" |
| Confused about when to use which recovery strategy | "How do I decide?" | Decision tree: Retry for parse errors, auto-fix for minor issues, partial for structural, escalate for complex |
| Time pressure | Running behind | Skip documentation tools (Segment 4), focus on self-documenting schemas |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save chat questions | For follow-up or FAQ updates |
| Note what worked/didn't | Demo success, timing, examples that landed |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | ☐ |
| Answer pending questions in support channel | ☐ |
| Send capstone reminder with rubric link | ☐ |
| Document issues encountered for curriculum improvement | ☐ |

### Within 2 Weeks

| Task | Done? |
|------|-------|
| Review capstone submissions | ☐ |
| Provide feedback on submissions | ☐ |
| Identify participants who struggled | ☐ |
| Update this instructor guide with lessons learned | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Session

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 2.1 | Workflow with validation implemented + test results | Participant's workflow platform or code repo |
| 2.2 | Error handler with formatting + recovery logic | Code or workflow documentation |
| 2.3 | Complete validated system documentation | Written documentation with statistics |

### Progress Check Approach

**How to Verify Completion:**
- Check for validation steps in workflow
- Look for error handling implementation
- Review capstone documentation for completeness
- Red flags: No validation testing, missing error handler, incomplete capstone

**Intervention Thresholds:**
- Validation not implemented: Help with platform-specific setup
- Error handler missing: Point to examples in participant guide
- Capstone incomplete: Clarify requirements, extend deadline if needed
- Not understanding value: 1:1 conversation about production reliability

---

## Session-Specific Notes

### What Makes This Session Unique

This session bridges theory (Session 1) and practice. The challenge is:
- Platform diversity - participants use different tools
- Implementation complexity - more moving parts than Session 1
- Capstone pressure - need to complete module successfully

**Critical Success Factors:**
- Strong demo showing validation in real workflow
- Clear pattern that works across platforms
- Practical, implementable retry and error handling strategies
- Enthusiasm for production readiness

### Dependencies

**Builds On:**
- Session 1: Schema library created
- Session 1: Understanding of schema syntax
- Block 2: Working workflows to add validation to

**Sets Up:**
- Production workflow implementation
- Team schema library and documentation
- Ongoing validation practice

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Platform diversity makes demos challenging | Focus on pattern, point to platform-specific guides | Documented in delivery guide |
| Retry logic can get complex | Start simple, one retry max | Noted in facilitation |
| Capstone in 20 min is tight | Can be completed incrementally | Acceptable |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- "Where would you validate in your workflow?" (Answer: At least input and AI output)
- "What's the first recovery strategy to try?" (Answer: Retry with stricter prompt)
- Watch for: Participants correctly identifying validation points in their workflows

### Summative Assessment (End of Session)

**Capstone Quality Indicators:**
- Exercise 2.1: Validation working at 2+ points with tests
- Exercise 2.2: Error handler formats messages clearly, implements 2+ recovery strategies
- Exercise 2.3: Complete system documented with validation statistics and learnings

**Common Issues to Flag:**
- Validation implemented but not tested
- Error handler that just logs without recovery
- Capstone documentation incomplete or generic

### Module Evaluation Rubric

**Total Points: 20 (from Appendix C)**

Key evaluation criteria:
1. Schema Quality (5 points) - Well-organized, documented schemas
2. Validation Implementation (5 points) - Multiple points, working correctly
3. Error Handling (5 points) - Clear messages, recovery strategies
4. Documentation (5 points) - Complete capstone with statistics

**Certification threshold: Not specified (module optional)**

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Quick poll: "How confident are you implementing validation in your workflow? 1-5"
- Open question: "What's the biggest challenge you anticipate with the capstone?"
- Observe: Which examples resonated, platform split

**Improvement Log:**

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| | | | |

### Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial guide created | [Instructor] |

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Validate early, validate often - multiple validation points prevent cascading failures"
2. "AI is non-deterministic - validation with recovery is mandatory for production"
3. "Your schemas are documentation - invest time in clear, complete schemas"

### If You Only Have Time For One Thing

The single most important concept: Implement validation at input and AI output points with basic error handling. Everything else builds on this foundation.

Participants must understand: Where to validate (input + AI output minimum) and basic retry logic for AI failures.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Multiple validation points | Airport security - multiple checkpoints | When explaining defense in depth |
| AI validation with retry | Quality control with rework option | When explaining recovery strategies |
| Schemas as documentation | Blueprint that's also the construction spec | When explaining self-documenting schemas |

---

**END OF INSTRUCTOR GUIDE - SESSION 2**
