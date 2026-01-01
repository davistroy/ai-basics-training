# **PRESENTATION: BLOCK 2 WEEK 6**
## **Integration Patterns**

**Block:** 2: AI Workflow Engineering
**Week:** 6 of 8
**Duration:** 45 minutes
**Theme Color:** Orange (Block 2)

---

## Slide Overview

| Slide # | Title | Duration | Type |
|---------|-------|----------|------|
| 1 | Title Slide | 0:30 | Title |
| 2 | Week 6 Learning Objectives | 1:00 | Overview |
| 3 | Where We Are in Block 2 | 1:30 | Context |
| 4 | The Integration Landscape | 2:00 | Concept |
| 5 | Five Integration Layers | 2:30 | Concept |
| 6 | Tool Ecosystem | 2:00 | Concept |
| 7 | Why Integration Matters | 2:30 | Context |
| 8 | Pattern 1: Sequential Pipeline | 3:00 | Pattern |
| 9 | Pattern 2: Parallel Processing | 3:00 | Pattern |
| 10 | Pattern 3: Iterative Refinement | 3:00 | Pattern |
| 11 | Pattern 4: Human-in-the-Loop | 4:00 | Pattern |
| 12 | Choosing the Right Pattern | 2:00 | Guidance |
| 13 | Combining Patterns | 2:00 | Advanced |
| 14 | MCP-Workflow Connection | 3:00 | Technical |
| 15 | Live Demo: Integrated Workflow | 8:00 | Demo |
| 16 | Quality Routing in Action | 2:00 | Concept |
| 17 | Documentation Requirements | 2:30 | Practice |
| 18 | Team Handoff Considerations | 2:00 | Practice |
| 19 | This Week's Exercises | 2:00 | Assignment |
| 20 | Preparing for Capstone | 1:30 | Preview |
| 21 | Q&A | - | Interactive |

---

## Slide 1: Title Slide

### Integration Patterns
#### Building End-to-End AI Workflows

**Block 2: AI Workflow Engineering**
Week 6 of 8

*[Company/Training Logo]*

**Speaker Notes:**
Welcome to Week 6 - Integration Patterns. This is where everything comes together. You've built individual components - workflows, prompts, quality systems, MCP. Today we connect them into cohesive, production-ready systems. This is arguably the most important session in Block 2 because it synthesizes everything you've learned.

---

## Slide 2: Week 6 Learning Objectives

### By the End of This Session, You Will:

1. **Understand** the five-layer integration architecture
2. **Master** four integration patterns (Sequential, Parallel, Iterative, Human-in-the-Loop)
3. **See** how to build fully integrated workflows with MCP
4. **Know** documentation requirements for team handoff
5. **Be Ready** to build your third integrated workflow

**Speaker Notes:**
These objectives move you from having separate pieces to having a complete system. By the end of homework, you'll have three working workflows, documentation, and a human review process - everything needed for your capstone.

---

## Slide 3: Where We Are in Block 2

### Block 2 Journey

| Week | Focus | Status |
|------|-------|--------|
| Week 1 | Automation Platforms | Complete |
| Week 2 | First Workflow | Complete |
| Week 3 | Quality Systems | Complete |
| Week 4 | Optimization | Complete |
| Week 5 | MCP Integration | Complete |
| **Week 6** | **Integration Patterns** | **TODAY** |
| Week 7 | Capstone Prep | Next Week |
| Week 8 | Capstone Evaluation | Final |

**Speaker Notes:**
Quick status check - who has MCP working? [Count hands] Excellent. If you're still troubleshooting MCP, that's your first priority after this session - you need it for today's exercises. We're entering the final stretch. Week 6 synthesizes everything, Week 7 prepares your capstone, Week 8 is evaluation.

---

## Slide 4: The Integration Landscape

### The Complete Picture

```
Triggers -> Workflow Platform -> AI + MCP -> Quality System -> Outputs
   ^                              |
External    <---- Feedback <--- Human Review
Systems
```

### From Components to System

- **Before Block 2:** Individual AI interactions
- **After Block 2:** Connected, automated, quality-controlled workflows
- **This Week:** Connecting all the pieces

**Speaker Notes:**
This diagram shows everything we're building. Triggers initiate workflows, your automation platform orchestrates, AI with MCP generates content, quality systems evaluate, outputs are delivered, and human review provides feedback that improves the system. This is production-grade AI automation.

---

## Slide 5: Five Integration Layers

### Layer Architecture

| Layer | Purpose | Your Components |
|-------|---------|-----------------|
| **Data** | Where information originates | Forms, emails, webhooks |
| **Processing** | How AI transforms data | Claude + prompts + MCP |
| **Quality** | How we verify outputs | LLM-as-judge, rubrics |
| **Output** | Where results are delivered | Docs, Slack, email |
| **Feedback** | How we learn and improve | Human review, metrics |

### Think of it as a building with five floors
Each floor must be solid for the whole structure to work.

**Speaker Notes:**
Think of these as the five floors of your workflow building. Data comes in at ground level. Processing happens in the middle. Quality checks everything. Outputs go out to the world. Feedback flows back to improve the system. Miss any floor and the building is incomplete.

---

## Slide 6: Tool Ecosystem

### Your Integration Toolkit

**Automation Platforms**
- Make.com, n8n (what you're using)
- Zapier, Power Automate (alternatives)

**AI Providers**
- Claude API (primary)
- OpenAI API (alternative)

**MCP Servers**
- Filesystem (local files)
- GitHub (templates, version control)
- Custom servers (advanced)

**Output Destinations**
- Google Docs, Sheets
- Slack, Microsoft Teams
- Email, webhooks

**Speaker Notes:**
You're not starting from scratch - you have all these tools available. Your automation platform is the orchestrator. Claude is the brain. MCP provides context. Your outputs go to tools people already use. The skill is connecting them effectively.

---

## Slide 7: Why Integration Matters

### The Difference Integration Makes

| Without Integration | With Integration |
|---------------------|------------------|
| Manual template copying | MCP fetches automatically |
| Copy-paste between tools | Data flows automatically |
| Spot-check quality | Every output evaluated |
| Hope it's good enough | Know exactly how good it is |
| Ad-hoc human review | Systematic oversight |
| Tribal knowledge | Documented architecture |

### Integration = Scalability + Quality + Sustainability

**Speaker Notes:**
This comparison shows why we spent four weeks building components. Without integration, you have smart tools used in dumb ways. With integration, you have a system that scales, maintains quality, and can be handed off to others. This is the difference between a prototype and production.

---

## Slide 8: Pattern 1 - Sequential Pipeline

### The Foundation Pattern

```
Trigger -> Gather -> Generate -> Evaluate -> Route -> Output
```

### Characteristics
- Each step depends on the previous
- Clear, linear data flow
- Easy to debug and understand
- Most common starting pattern

### Best For
- Straightforward transformations
- Single-output workflows
- When simplicity is valued

### Example
Email arrives -> Extract key info -> Generate response -> Check quality -> Send or queue for review

**Speaker Notes:**
Sequential is your default pattern. Start here. It's the easiest to build, debug, and explain. Most workflows work perfectly fine as sequential pipelines. Only add complexity when you have a specific reason.

---

## Slide 9: Pattern 2 - Parallel Processing

### Speed Through Concurrency

```
Trigger -> [Generate A] --+
       -> [Generate B] --+--> Merge -> Evaluate -> Output
       -> [Generate C] --+
```

### Characteristics
- Multiple generations run simultaneously
- Outputs are compared or combined
- Faster for complex deliverables
- Higher API costs

### Best For
- Multi-section documents
- A/B testing different approaches
- When you want to pick the best of several

### Example
Brief arrives -> Generate intro, body, conclusion in parallel -> Combine -> Evaluate -> Output

**Speaker Notes:**
Parallel is for speed or variety. If you're generating a long document, generate sections in parallel. If you want options, generate three versions and pick the best. Watch your costs - you're making multiple API calls simultaneously.

---

## Slide 10: Pattern 3 - Iterative Refinement

### Self-Improving Loops

```
Generate -> Evaluate -> (Pass?) -> Output
               | (Fail)
            Refine -> Re-generate -> Evaluate...
```

### Characteristics
- Auto-improvement when quality fails
- CRITICAL: Set maximum iterations (3-5)
- Escalation on repeated failure
- Higher quality potential

### Best For
- Quality-critical content
- When regeneration is cheaper than human editing
- Outputs with clear quality criteria

### Example
Generate report -> Evaluate -> Score 3.2 -> Refine prompt with feedback -> Regenerate -> Score 4.1 -> Output

**Speaker Notes:**
Iterative refinement is powerful but needs guardrails. Always set a maximum iteration count - 3 to 5 is typical. Without limits, you can get stuck in loops or burn through your API budget. The key is feeding evaluation feedback into the regeneration prompt.

---

## Slide 11: Pattern 4 - Human-in-the-Loop

### Systematic Oversight

```
Generate -> Evaluate -> (Review Needed?) -> Queue for Human
                              | (Pass)
                           Output

Human Review -> Approve/Edit -> Learn from Feedback
```

### Characteristics
- Systematic, not ad-hoc
- Review decisions are tracked
- Feedback captured for improvement
- Trust builds over time

### Best For
- High-stakes content
- Building organizational trust
- Regulatory requirements
- Learning what works

### The Secret Sauce
Every human review teaches you something. Capture that feedback.

**Speaker Notes:**
Human-in-the-Loop is essential, especially when you're building trust. It's not about not trusting AI - it's about learning and improving systematically. Every review is data. Over time, your auto-approve rate should increase as you learn what works.

---

## Slide 12: Choosing the Right Pattern

### Pattern Selection Guide

| If You Need... | Use This Pattern |
|----------------|------------------|
| Simplicity | Sequential |
| Speed | Parallel |
| Highest quality | Iterative |
| Trust/oversight | Human-in-the-Loop |

### Decision Tree

1. **Start with Sequential** - Can this work as a simple pipeline?
2. **Add Human-in-the-Loop** - Do stakeholders need visibility/control?
3. **Consider Iterative** - Is quality critical and auto-improvement feasible?
4. **Try Parallel** - Do you need speed or multiple outputs?

**Speaker Notes:**
When in doubt, start simple. Sequential with Human-in-the-Loop covers most real-world needs. Add complexity only when you have a specific problem to solve. Premature complexity is the enemy of getting things done.

---

## Slide 13: Combining Patterns

### Real Workflows Combine Patterns

```
Trigger -> Gather -> [Sequential base]
                         |
                         v
               Generate -> Evaluate
                              |
              +---------------+---------------+
              |                               |
        (Pass)                          (Review Needed)
              v                               v
      Iterative                        Human-in-the-Loop
    (if score 3.5-4.0)                  (if score < 3.5)
              |                               |
              +--------------+----------------+
                             |
                             v
                          Output
```

### Common Combinations
- Sequential + Human-in-the-Loop (most common)
- Sequential + Iterative (quality-focused)
- Parallel + Human-in-the-Loop (options with oversight)

**Speaker Notes:**
Don't think of patterns as mutually exclusive. Most production workflows combine patterns. The most common is Sequential with Human-in-the-Loop routing - simple flow, but with systematic oversight for edge cases.

---

## Slide 14: MCP-Workflow Connection

### Three Approaches

**Approach 1: Claude API with MCP Context**
- Use Claude Desktop + MCP to gather context
- Pass context to API call in workflow
- Best for: Complex context gathering

**Approach 2: Pre-fetch via MCP**
- Fetch templates/context before workflow runs
- Templates stored/passed to workflow
- Best for: Stable, reusable templates

**Approach 3: Hybrid**
- Some context via MCP, some via workflow
- Flexible based on what's needed
- Best for: Complex, varied requirements

### Key Insight
MCP gathers context. API generates content.
Your workflow orchestrates the process.

**Speaker Notes:**
The relationship between MCP and your automation platform can be confusing. Think of it this way: MCP is Claude's way to access tools and data. Your workflow orchestrates when and how AI is called. They work together, not instead of each other.

---

## Slide 15: Live Demo - Integrated Workflow

### What We're Building

**Workflow: Content Generation with Quality Routing**

1. **Trigger:** Webhook (simulating form submission)
2. **Gather:** Collect input data
3. **Fetch:** Get template via MCP context
4. **Generate:** Claude API call
5. **Evaluate:** LLM-as-judge quality check
6. **Route:** Pass -> Output, Review -> Queue
7. **Output:** Google Doc creation
8. **Notify:** Slack message

### Let's Build It Live

*[Live demonstration]*

**Speaker Notes:**
[This is the main demo - about 8 minutes. Walk through each component of your pre-built workflow. Show the trigger, data flow, AI processing, quality routing, and outputs. Run it live with test data. Show both the pass path and the review path if possible.]

---

## Slide 16: Quality Routing in Action

### The Router Decision Point

```
Quality Score >= 4.0  ->  Direct to Output
Quality Score 3.0-3.9 ->  Queue for Human Review
Quality Score < 3.0   ->  Retry or Escalate
```

### What Gets Routed to Review

- Scores below threshold
- Specific criteria failures
- Novel/unusual inputs
- Flagged content types

### Review Queue Contains
- Generated content
- All quality scores with reasoning
- Original input context
- Reviewer action options

**Speaker Notes:**
The router is your traffic controller. It makes decisions based on objective quality scores. This isn't about AI being untrustworthy - it's about knowing when outputs need a second look. Well-designed routing means humans focus only where they add value.

---

## Slide 17: Documentation Requirements

### Essential Documentation

| Document | Purpose | Audience |
|----------|---------|----------|
| Architecture Diagram | Visual overview | Everyone |
| Data Flow Description | What goes where | Maintainers |
| Component Dependencies | What needs what | Troubleshooters |
| Configuration Details | How to set up | Implementers |
| Troubleshooting Guide | How to fix issues | Support |

### The Documentation Test

> "If I go on vacation, could a colleague maintain this?"

If no, your documentation is incomplete.

**Speaker Notes:**
Documentation isn't optional - it's what makes your workflow sustainable. If you can't hand it off, you own it forever. Your integration architecture document becomes part of your capstone portfolio and a real deliverable for your organization.

---

## Slide 18: Team Handoff Considerations

### Access Requirements

| Access Needed | Who Has It | How to Get |
|---------------|------------|------------|
| Automation platform | You | Share access or transfer |
| Claude API key | Organization | Request from admin |
| MCP configuration | Individual | Document setup steps |
| Output destinations | Varies | Check permissions |

### Training Needed
- How to trigger workflows
- How to monitor execution
- How to review queued items
- How to troubleshoot common issues

### Support Plan
- Who handles issues?
- What's the escalation path?
- Where are logs?

**Speaker Notes:**
Think about handoff now, not later. Who else needs to understand this system? What happens when you're unavailable? These aren't hypothetical questions - they affect whether your work has lasting impact.

---

## Slide 19: This Week's Exercises

### Homework (60 minutes)

**Exercise 6.1: Build Integrated Workflow (30 min)**
- Design your third workflow using one of today's patterns
- Build it in your automation platform
- Test end-to-end with 3+ executions
- Document the architecture

**Exercise 6.2: Human Review System (20 min)**
- Create review queue (Airtable, Trello, or Sheets)
- Design review item template
- Document feedback loop process

**Exercise 6.3: Integration Architecture Document (10 min)**
- Create `integration-architecture.md`
- Document complete system
- Include all components, flows, and configuration

**Speaker Notes:**
This homework is substantial but critical. Exercise 6.1 gives you your third workflow. Exercise 6.2 gives you systematic oversight. Exercise 6.3 documents everything. All three become part of your capstone portfolio.

---

## Slide 20: Preparing for Capstone

### Week 7: Capstone Preparation

**What You Need Ready:**
- 3 working workflows (all tested 5+ times)
- Complete prompt library in GitHub
- Integration architecture documented
- Execution data for impact metrics

**What We'll Do:**
- Calculate real cost savings
- Measure quality improvements
- Prepare demonstration
- Build portfolio document

### Start Now
- Run each workflow 5+ times this week
- Track execution times
- Note any issues
- Collect output samples

**Speaker Notes:**
Capstone preparation starts now. Run your workflows. Collect data. You need real numbers for impact calculation - time saved, cost per execution, quality scores. The more data you have, the stronger your capstone.

---

## Slide 21: Q&A

### Questions?

**Common Questions:**
- "Which pattern should I use?" - Start with Sequential + Human-in-the-Loop
- "How do I connect MCP to my workflow?" - MCP gathers context, API generates
- "How much documentation is enough?" - Enough for someone else to maintain it

**Resources:**
- [Make Integration Patterns](https://www.make.com/en/help/scenarios)
- [n8n Workflow Patterns](https://docs.n8n.io/courses/)
- [MCP Documentation](https://modelcontextprotocol.io/)

**Next Week:** Capstone Preparation

**Speaker Notes:**
Take questions. Common concerns are pattern selection (start simple), MCP integration (varies by approach), and documentation scope (handoff test). Remind everyone that Week 7 is capstone prep - they need three working workflows by then.

---

## Appendix: Supporting Materials

### Demo Script Details

**Pre-Demo Setup:**
1. Have workflow pre-built in automation platform
2. Test data ready in trigger
3. Output destinations verified
4. Slack channel ready for notification

**Demo Execution:**
1. Show complete workflow overview
2. Walk through each module
3. Highlight MCP context integration
4. Show quality evaluation logic
5. Demonstrate routing paths
6. Execute with test data
7. Show output in destination
8. Show Slack notification

**If Demo Fails:**
1. Show prepared screenshots
2. Explain what should happen
3. Debug as teaching moment
4. Move on after 2-3 minutes troubleshooting

### Pattern Selection Quick Reference

| Situation | Recommended Pattern |
|-----------|-------------------|
| First workflow | Sequential |
| Stakeholder skepticism | Human-in-the-Loop |
| Quality is critical | Iterative |
| Long document | Parallel |
| Regulatory environment | Human-in-the-Loop |
| Building trust | Human-in-the-Loop |
| Speed matters | Parallel |
| Debugging needed | Sequential |

---

**Navigation:** [<- Week 5 Presentation](../week-5/presentation.md) | **Week 6** | [Week 7 Presentation ->](../week-7/presentation.md)
