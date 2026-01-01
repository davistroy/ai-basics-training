# **PARTICIPANT GUIDE: BLOCK 2 WEEK 6**
## **Integration Patterns**

**Block:** 2: AI Workflow Engineering
**Week:** 6 of 8
**Self-Study Time:** 60 minutes
**Theme Color:** Orange (Block 2)

---

## Navigation

**Block Navigation:** [<- Week 5 Participant Guide](../week-5/participant-guide.md) | **Week 6** | [Week 7 Participant Guide ->](../week-7/participant-guide.md)

**Related Materials:**
- [Week 6 Presentation](presentation.md)
- [Week 6 Instructor Guide](instructor-guide.md)
- [Block 2 Main Document](../block-2.md)

---

## Introduction

### What You'll Learn This Week

This week brings together everything you've built in Block 2. You'll learn integration patterns that connect your automation platform, AI processing, MCP tools, and quality systems into cohesive workflows. By the end, you'll have a third fully integrated workflow ready for your capstone portfolio.

### Prerequisites Checklist

Before starting this week's exercises, ensure you have:

- [ ] MCP configured and working in Claude Desktop
- [ ] GitHub MCP connected to your prompt library
- [ ] Two optimized workflows from Weeks 2-4
- [ ] Understanding of quality gates and LLM-as-judge pattern
- [ ] Access to output destinations (Google Docs, Slack, etc.)

### Materials Needed

| Item | Purpose | Where to Get |
|------|---------|--------------|
| Working MCP setup | Access templates directly | Configured in Week 5 |
| Automation platform | Build integrated workflow | Make.com or n8n |
| Review queue tool | Human review system | Airtable, Trello, or Google Sheets |
| Output destinations | Workflow outputs | Google Docs, Slack, email |

---

## Session Content Summary

### Key Concepts Covered

#### 1. Integration Architecture

The complete integration landscape connects five layers:

```
Triggers -> Workflow Platform -> AI + MCP -> Quality System -> Outputs
   ^                              |
External    <---- Feedback <--- Human Review
Systems
```

**The Five Integration Layers:**

| Layer | Purpose | Examples |
|-------|---------|----------|
| Data Layer | Where information originates | Forms, emails, webhooks, schedules |
| Processing Layer | How AI transforms data | Claude API, prompt templates |
| Quality Layer | How we verify outputs | LLM-as-judge, score thresholds |
| Output Layer | Where results are delivered | Docs, Sheets, Slack, email |
| Feedback Layer | How we learn and improve | Human review, error tracking |

#### 2. Four Integration Patterns

**Pattern 1: Sequential Pipeline**
```
Trigger -> Gather -> Generate -> Evaluate -> Route -> Output
```
- Each step depends on previous
- Clear data flow, easy to debug
- Best for: Straightforward transformations

**Pattern 2: Parallel Processing**
```
Trigger -> [Generate A] --+
       -> [Generate B] --+--> Merge -> Evaluate -> Output
       -> [Generate C] --+
```
- Multiple generations simultaneously
- Compare or combine outputs
- Best for: Multi-part content, A/B testing

**Pattern 3: Iterative Refinement**
```
Generate -> Evaluate -> (Pass?) -> Output
               | (Fail)
            Refine -> Re-generate -> Evaluate...
```
- Auto-improvement with safety limits
- Always set max iterations (3-5 typical)
- Best for: Quality-critical content

**Pattern 4: Human-in-the-Loop**
```
Generate -> Evaluate -> (Review Needed?) -> Queue for Human
                              | (Pass)
                           Output
Human Review -> Approve/Edit -> Learn from Feedback
```
- Systematic oversight, not ad-hoc
- Captures feedback for improvement
- Best for: High-stakes content, building trust

#### 3. MCP-Workflow Connection

Three approaches to connecting MCP with automation platforms:

1. **Claude API with MCP context** - MCP gathers context, API generates
2. **Pre-fetch via MCP** - Get templates first, pass to workflow
3. **Hybrid approach** - Some context via MCP, some via workflow

#### 4. Documentation Requirements

Essential documentation for team handoff:
- Architecture diagram
- Data flow description
- Component dependencies
- Configuration details
- Troubleshooting guide

---

## Self-Paced Exercises

### Exercise 6.1: Build Integrated Workflow (30 minutes)

**Objective:** Create a fully integrated workflow using one of the four patterns

**Part 1: Design Your Integration (10 min)**

Choose a pattern and design your third workflow:

```markdown
# Integrated Workflow: [Your Workflow Name]

## Pattern Selected
[ ] Sequential Pipeline
[ ] Parallel Processing
[ ] Iterative Refinement
[ ] Human-in-the-Loop (with Sequential base)

## Architecture
```
[Draw your workflow flow here]
```

## Components

### Trigger
- Type: [Form/Email/Webhook/Schedule]
- Source: [Where it comes from]
- Data provided: [What information arrives]

### Data Sources
- Input data: [From trigger]
- Template: [Via MCP from GitHub - specify path]
- Style guide: [Via MCP from GitHub - specify path]

### AI Processing
- Model: Claude 3.5 Sonnet
- Template: [Which template from your library]
- MCP integration: [How MCP provides context]

### Quality System
- Evaluation rubric: [Link to your rubric]
- Pass threshold: [Score, e.g., 4.0/5.0]
- Review trigger: [Conditions that trigger human review]

### Routing Logic
- Pass (>= threshold): [Where output goes]
- Review (< threshold but > minimum): [Review queue destination]
- Fail (< minimum): [What happens - retry? alert?]

### Outputs
- Primary: [Where main output goes]
- Notification: [How stakeholders are alerted]
- Logging: [Where execution is logged]
```

**Part 2: Build in Your Platform (15 min)**

Using your design:

1. **Create the workflow structure:**
   - Add trigger module
   - Add data gathering steps
   - Add AI processing module with Claude API
   - Add evaluation module (LLM-as-judge)
   - Add router based on quality scores
   - Add output modules

2. **Configure MCP integration:**
   - Set up template fetching (if using MCP approach)
   - Or prepare template context for API call

3. **Set up quality routing:**
   - Configure score threshold
   - Create pass path to output
   - Create review path to queue

4. **Configure outputs:**
   - Primary output destination
   - Notification channel
   - Logging/tracking

**Part 3: Test End-to-End (5 min)**

Run at least 3 complete tests:

| Test | Input | Expected Path | Actual Path | Result |
|------|-------|---------------|-------------|--------|
| 1 | [Good input] | Pass -> Output | | |
| 2 | [Edge case] | May need review | | |
| 3 | [Challenging input] | Likely review | | |

**Deliverables:**
- [ ] Third working workflow in your automation platform
- [ ] Workflow architecture documentation (above template filled in)
- [ ] At least 3 successful test executions

---

### Exercise 6.2: Human Review System (20 minutes)

**Objective:** Design and implement systematic human oversight

**Part 1: Create Review Queue (10 min)**

Choose your review queue tool:
- [ ] Airtable (structured, queryable)
- [ ] Trello (kanban visual)
- [ ] Google Sheets (simple, accessible)
- [ ] Email folder (basic)
- [ ] Other: ___________

Set up your review queue with this structure:

```markdown
# Review Queue Configuration

## Tool Selected: [Your choice]

## Queue Structure

### Fields/Columns Required:
1. ID - Unique identifier
2. Workflow - Which workflow generated this
3. Timestamp - When it was created
4. Trigger Source - What initiated the workflow
5. Generated Content - The output needing review
6. Quality Score - Overall score from evaluation
7. Score Breakdown - Individual criterion scores
8. Review Reason - Why it was flagged
9. Priority - High/Medium/Low
10. Status - Pending/In Review/Approved/Rejected
11. Reviewer - Who is reviewing
12. Reviewer Notes - Feedback and edits
13. Disposition - Final decision

### Views/Filters:
- Pending Reviews (Status = Pending, sorted by Priority)
- My Reviews (Reviewer = Me)
- Completed Today (Status in [Approved, Rejected] AND Date = Today)
```

**Part 2: Design Review Interface (5 min)**

Create a template for how reviews are presented:

```markdown
# Review Queue Item Template

## Execution Details
- **Workflow:** [Name]
- **Executed:** [Timestamp]
- **Trigger:** [Source]
- **ID:** [Unique identifier]

---

## Generated Content

[Content that needs review - displayed in readable format]

---

## Quality Evaluation

| Criterion | Score | Reason |
|-----------|-------|--------|
| Criterion 1 | X.X/5 | [Evaluator's reasoning] |
| Criterion 2 | X.X/5 | [Evaluator's reasoning] |
| Criterion 3 | X.X/5 | [Evaluator's reasoning] |
| Criterion 4 | X.X/5 | [Evaluator's reasoning] |
| Criterion 5 | X.X/5 | [Evaluator's reasoning] |

**Overall Score:** X.X/5

**Review Triggered Because:** [Specific reason - e.g., "Score 3.8 below threshold 4.0"]

---

## Reviewer Actions

- [ ] **Approve as-is** - Output meets quality standards
- [ ] **Approve with edits** - Minor changes needed (document below)
- [ ] **Reject - Regenerate** - Retry with modified prompt/input
- [ ] **Reject - Manual creation** - Automation not suitable for this case

### Edits Made:
[Space for documenting any changes]

### Feedback for Improvement:
[Notes on how to improve future automation - prompt tweaks, additional context, etc.]

---

## Disposition
- **Decision:** [Approved/Rejected]
- **Reviewer:** [Name]
- **Date:** [Timestamp]
- **Time Spent:** [Minutes]
```

**Part 3: Implement Feedback Loop (5 min)**

Document how feedback improves the system:

```markdown
# Feedback Loop Process

## How Edits Get Incorporated

1. **Document the pattern:** When I make the same edit 3+ times, I note it
2. **Update the prompt:** Modify my prompt template to prevent the issue
3. **Update the rubric:** Adjust evaluation criteria if needed
4. **Test the change:** Run through quality gate to verify improvement

## How Rejections Inform Improvements

1. **Categorize rejection reasons:**
   - [ ] Missing context - Need more input data
   - [ ] Wrong tone - Prompt needs adjustment
   - [ ] Factual errors - Need validation step
   - [ ] Format issues - Template needs updating
   - [ ] Edge case - May not be suitable for automation

2. **Track patterns:** If same rejection reason appears 3+ times, take action
3. **Escalate if needed:** Some content types may not be automatable

## Metrics to Track

| Metric | Current | Target |
|--------|---------|--------|
| Auto-approve rate | ___% | >80% |
| Average review time | ___ min | <5 min |
| Rejection rate | ___% | <10% |
| Common edit patterns | [List] | Addressed in prompts |
```

**Deliverables:**
- [ ] Review queue set up in your chosen tool
- [ ] Review item template documented
- [ ] Feedback loop process documented

---

### Exercise 6.3: Integration Architecture Document (10 minutes)

**Objective:** Create comprehensive documentation for your integrated system

Create `integration-architecture.md` in your prompt library repository:

```markdown
# AI Workflow Integration Architecture

## Overview

This document describes my integrated AI workflow system built during Block 2 of the AI Practitioner Training program.

## System Diagram

```
[Draw your complete system architecture]

Example:
                    +------------------+
                    |    Triggers      |
                    | (Forms, Email,   |
                    |  Webhook, Sched) |
                    +--------+---------+
                             |
                             v
                    +------------------+
                    |   Automation     |
                    |   Platform       |
                    |   (Make/n8n)     |
                    +--------+---------+
                             |
              +--------------+---------------+
              |              |               |
              v              v               v
        +---------+    +---------+    +-----------+
        |Workflow1|    |Workflow2|    |Workflow 3 |
        +---------+    +---------+    +-----------+
              |              |               |
              +--------------+---------------+
                             |
                             v
                    +------------------+
                    |   Claude API     |
                    |   + MCP Context  |
                    +--------+---------+
                             |
                             v
                    +------------------+
                    |  Quality System  |
                    |  (LLM-as-judge)  |
                    +--------+---------+
                             |
              +--------------+---------------+
              |                              |
              v                              v
        +---------+                  +--------------+
        | Outputs |                  | Review Queue |
        |(Docs,   |                  | (Human-in-   |
        | Slack)  |                  |  the-Loop)   |
        +---------+                  +--------------+
```

## Components

### Automation Platform
- **Platform:** [Make.com / n8n / other]
- **Account type:** [Free / Paid tier]
- **Workflows:**
  1. [Workflow 1 name] - [Purpose]
  2. [Workflow 2 name] - [Purpose]
  3. [Workflow 3 name] - [Purpose]
- **External connections:** [List all connected apps/services]

### AI Layer
- **Provider:** Anthropic (Claude)
- **Model:** Claude 3.5 Sonnet
- **MCP servers configured:**
  - filesystem: [Path(s) accessible]
  - GitHub: [Repository connected]

### Data Sources
- **GitHub repository:** [URL]
  - Prompt templates: `/templates/`
  - Evaluation rubrics: `/rubrics/`
  - Style guides: `/style-guides/`
- **Other sources:** [List any additional data sources]

### Outputs
- **Google Docs:** [Folder/location]
- **Slack:** [Channel(s)]
- **Email:** [If used]
- **Other:** [Any additional outputs]

### Quality System
- **Evaluation approach:** LLM-as-judge with structured rubric
- **Pass threshold:** [Score]
- **Review threshold:** [Score range]
- **Fail threshold:** [Score]

### Human Review
- **Queue tool:** [Airtable/Trello/Sheets/etc.]
- **Queue location:** [URL or path]
- **Review SLA:** [Target turnaround time]

## Data Flows

### Flow 1: [Workflow 1 Name]
```
[Input source] -> [Step 1] -> [Step 2] -> ... -> [Output]
```
- **Trigger:** [What initiates]
- **Processing:** [What AI does]
- **Output:** [Where results go]

### Flow 2: [Workflow 2 Name]
```
[Input source] -> [Step 1] -> [Step 2] -> ... -> [Output]
```
- **Trigger:** [What initiates]
- **Processing:** [What AI does]
- **Output:** [Where results go]

### Flow 3: [Workflow 3 Name]
```
[Input source] -> [Step 1] -> [Step 2] -> ... -> [Output]
```
- **Trigger:** [What initiates]
- **Processing:** [What AI does]
- **Output:** [Where results go]

## Configuration Requirements

### API Keys and Tokens
| Service | Key Type | Where Stored | Rotation Schedule |
|---------|----------|--------------|-------------------|
| Claude API | API Key | Automation platform secrets | Quarterly |
| GitHub | Personal Access Token | MCP config | Quarterly |
| [Other] | | | |

### MCP Configuration
- **Config file location:** [Path]
- **Servers configured:** filesystem, GitHub
- **Access paths:** [What directories/repos are accessible]

### Platform Connections
| Connection | Purpose | Credentials Location |
|------------|---------|---------------------|
| Google | Docs, Sheets output | OAuth in platform |
| Slack | Notifications | OAuth in platform |
| [Other] | | |

## Security Considerations

### Data Handling
- All data processed through [platform] which is [SOC2/GDPR/etc. compliant]
- Sensitive data [is/is not] processed through AI
- PII handling: [Describe approach]

### Access Controls
- API keys: Stored in platform secrets, not in code
- MCP tokens: Stored locally, not in git
- Platform access: [Who has access]

### Token Management
- Regular rotation: [Quarterly/etc.]
- Revocation process: [How to revoke if compromised]

## Monitoring

### Logs
- **Workflow logs:** [Platform] execution history
- **AI logs:** [If applicable]
- **Error logs:** [Where errors are tracked]

### Alerts
- Workflow failure: [Notification method]
- Quality drops: [If monitored]
- Review queue backup: [If monitored]

### Metrics Tracked
| Metric | Current Value | Target |
|--------|---------------|--------|
| Workflow success rate | ___% | >95% |
| Auto-approve rate | ___% | >80% |
| Average execution time | ___ sec | <60 sec |
| Cost per execution | $___ | <$0.10 |

## Troubleshooting Guide

### Common Issues

| Issue | Symptoms | Solution |
|-------|----------|----------|
| API rate limit | 429 errors | Add delay between calls |
| MCP not connecting | Tools unavailable | Restart Claude Desktop |
| Quality scores low | High review rate | Review prompt templates |
| Output not appearing | Missing deliverables | Check destination permissions |

### Escalation Path
1. **Self-troubleshoot:** Use this guide
2. **Documentation:** Check official docs
3. **Support:** [Contact information]
```

**Deliverables:**
- [ ] `integration-architecture.md` committed to your prompt library repository
- [ ] All sections completed with your actual configuration

---

## Reflection Questions

After completing this week's exercises, consider:

1. **Pattern Selection:** Which integration pattern did you choose and why? Would a different pattern have worked better?

2. **MCP Integration:** How does MCP change your workflow capabilities compared to manual template copying?

3. **Human Review:** How will systematic human review help build trust in your AI workflows?

4. **Documentation Value:** Who else could use your integration architecture document to understand or maintain your system?

5. **Capstone Readiness:** Do you have three working workflows ready for Week 7 preparation?

---

## Key Takeaways

1. **Integration patterns provide structure** - Choose the right pattern for your use case, start with Sequential
2. **MCP connects AI to external tools** - Templates, repos, and more accessible directly
3. **Human review is systematic** - Designed process, not ad-hoc checking
4. **Documentation enables handoff** - Others can understand and maintain your work
5. **Feedback loops improve quality** - Every review is a learning opportunity

---

## Checklist Before Next Week

Before Week 7 (Capstone Preparation), ensure:

- [ ] Three working workflows completed
- [ ] Each workflow tested 5+ times
- [ ] Human review queue operational
- [ ] Integration architecture document complete
- [ ] Execution data being collected
- [ ] All prompt templates in GitHub repository
- [ ] Quality evaluation rubrics documented

---

## Resources

### Documentation
- [Make Integration Patterns](https://www.make.com/en/help/scenarios)
- [n8n Workflow Patterns](https://docs.n8n.io/courses/)
- [MCP Documentation](https://modelcontextprotocol.io/)

### Templates
- Integration architecture template (above)
- Review queue item template (above)
- Feedback loop documentation template (above)

### Tools
- Airtable: [airtable.com](https://airtable.com) - Structured review queues
- Trello: [trello.com](https://trello.com) - Kanban-style review
- Diagrams: [draw.io](https://draw.io) - Architecture diagrams

---

**Navigation:** [<- Week 5 Participant Guide](../week-5/participant-guide.md) | **Week 6** | [Week 7 Participant Guide ->](../week-7/participant-guide.md)
