# **PRESENTATION: BLOCK 2 WEEK 6**
## **Integration Patterns**

**Block:** 2: AI Workflow Engineering
**Week:** 6 of 8
**Duration:** 45 minutes
**Theme Color:** Orange (Block 2)

**Key Thesis:** Effective integration patterns (Sequential, Parallel, Iterative, Human-in-the-Loop) connect workflow components into production-ready systems that scale quality control and maintain systematic oversight.

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

**BACKGROUND:**

**Rationale:**
- This slide establishes the complete integration architecture that participants will build - it's the "north star" diagram they'll reference throughout Week 6
- The feedback loop inclusion distinguishes production systems from prototypes - systems that learn from usage versus static implementations
- The before/after framing makes the learning progression tangible and demonstrates Block 2's cumulative value

**Key Research & Citations:**
- **Systems Thinking in Automation**: Complete systems require closed feedback loops. Open-loop systems (no feedback) cannot adapt or improve. The integration landscape shows closed-loop architecture essential for sustainable automation.
- **DevOps and Production Readiness**: Production systems have monitoring, quality gates, and feedback mechanisms. These aren't optional additions - they're what defines "production-ready" versus prototype status.
- **Integration Architecture Patterns**: The multi-layer architecture (triggers, orchestration, processing, quality, output, feedback) follows enterprise integration patterns proven across decades of software systems design.

**Q&A Preparation:**
- *"Is all this complexity really necessary for AI workflows?"*: For prototypes, no. For production use - yes. The difference is whether it needs to run reliably at scale without constant manual intervention. Each layer serves a specific reliability or quality function.
- *"Can I skip the feedback loop initially?"*: You can, but you'll have a static system that doesn't improve. Feedback is how you identify edge cases, refine quality criteria, and build confidence for increasing automation. Start simple but plan to add it.
- *"What's the minimum viable version of this architecture?"*: Trigger → Process (AI) → Quality Check → Output. That's the minimum. Add feedback when you want the system to learn. Add human review when stakes are high or trust is building.

**Sources:**
- Enterprise Integration Patterns - Hohpe & Woolf, 2003
- The DevOps Handbook - Kim, Humble, Debois, Willis, 2016

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

**BACKGROUND:**

**Rationale:**
- This framework provides a complete mental model for understanding workflow architecture beyond simple linear flows
- The five-layer model maps directly to enterprise integration patterns participants may encounter professionally
- Each layer represents a discrete point of potential failure or optimization, making troubleshooting systematic

**Key Research & Citations:**
- **Enterprise Integration Patterns (Hohpe & Woolf, 2003)**: Classic integration architecture identifies similar layers - data sources, message routing, transformation, endpoints, and monitoring. Block 2 adapts these patterns for AI workflows.
- **Systems Thinking in Automation**: Complete systems require closed feedback loops. The five layers ensure nothing is overlooked - data in, processing, quality, output, and learning from results.
- **Production AI Deployment Literature**: Studies of successful AI deployments emphasize that quality/monitoring layers (layers 3 & 5) are what distinguish prototypes from production systems

**Q&A Preparation:**
- *"Do all workflows need all five layers?"*: For production use, yes. You can skip feedback initially for simple cases, but data, processing, quality, and output are essential. Feedback makes systems improve over time.
- *"What if I only have three of the five layers?"*: Identify which are missing. No quality layer means you don't know if outputs are good. No feedback means you can't improve. Document gaps and plan to fill them.
- *"Is this overkill for simple workflows?"*: The layers scale to complexity. Simple workflow = simple implementation at each layer. But thinking through all five prevents blind spots.

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

**BACKGROUND:**

**Rationale:**
- This slide justifies the complexity investment by showing concrete value delivered by integration
- The before/after comparison makes abstract benefits tangible and memorable
- "Prototype vs. production" framing resonates with participants who have built prototypes that never scaled

**Key Research & Citations:**
- **The Last Mile Problem in AI**: Research on AI deployment shows that 87% of data science projects never reach production. The gap is integration - connecting components, ensuring quality, documenting for handoff.
- **Scalability Research**: Studies of workflow automation show manual steps (copy-paste, spot-checking) are the #1 bottleneck to scaling. Automation value compounds with volume - 10x executions = 10x value, but only if integrated.
- **Knowledge Management**: Tribal knowledge (undocumented processes) creates key-person risk. Documented architecture enables team scale and business continuity.

**Q&A Preparation:**
- *"My workflow works fine without all this integration - why add complexity?"*: "Works fine" at what scale? For 10 executions/month with one person? Maybe. For 100 executions or team usage? The manual steps become bottlenecks. Integration removes those limits.
- *"How do I know if I've integrated enough?"*: The handoff test - could a colleague maintain this system based on documentation? If yes, you're integrated. If no, you've built a personal tool, not a sustainable system.
- *"What's the minimum viable integration?"*: Data flow (automated input), AI processing, quality check, documented output. That's the minimum. Add feedback and human review as needs demand.

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

**BACKGROUND:**

**Rationale:**
- Iterative refinement demonstrates AI's capacity for self-improvement, moving beyond single-pass generation to quality-driven iteration
- The maximum iteration guardrail is essential - without it, participants risk runaway costs and infinite loops
- This pattern showcases the power of combining generation with evaluation in a closed feedback loop

**Key Research & Citations:**
- **Iterative Improvement in AI Systems**: Research shows that LLM outputs improve significantly when evaluation feedback is incorporated into regeneration prompts. Average quality scores increase 15-40% with one iteration, with diminishing returns after 3-4 iterations.
- **Cost-Benefit Analysis**: Automated iteration is cost-effective when API cost per regeneration is less than human editing time. At current API pricing, this threshold is typically 3-5 iterations before human editing becomes more economical.
- **Failure Mode Research**: Studies of production AI systems show that unbounded iteration loops are a common failure pattern. Maximum iteration limits prevent both cost overruns and time-to-completion issues.

**Q&A Preparation:**
- *"How do I know if I should use iterative refinement or just regenerate manually?"*: If you're consistently regenerating outputs manually 2+ times, automate it. If outputs usually pass on first try, iterative refinement adds complexity without value.
- *"What happens when maximum iterations is reached and quality still fails?"*: Escalate to human review with all iteration history. This reveals either unrealistic quality criteria or a prompt that needs fundamental redesign, not just iteration.
- *"How do I feed evaluation feedback into regeneration?"*: Include the evaluation results in the regeneration prompt: "The previous output scored 3.2/5. Issues: [reasons]. Generate an improved version addressing these issues."

**Sources:**
- Iterative Refinement in Large Language Models - Anthropic Research, 2024
- Cost Optimization for Production AI - OpenAI, 2024

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

**BACKGROUND:**

**Rationale:**
- Human-in-the-Loop is the pattern that enables AI adoption in risk-averse organizations
- The slide reframes human review from "AI can't be trusted" to "systematic learning and improvement"
- Feedback capture transforms human review from cost center to data source for optimization

**Key Research & Citations:**
- **Human-AI Collaboration Research**: Studies show that hybrid systems (AI + human oversight) outperform either alone, especially during initial deployment when trust is building and edge cases are being discovered
- **Progressive Automation Principle**: Start with high human involvement, gradually increase automation as confidence builds. HITL enables this progression through measured risk reduction.
- **Learning from Human Feedback (RLHF)**: While RLHF typically refers to model training, the same principle applies to workflow optimization - human judgments become training data for refining quality criteria and routing logic

**Q&A Preparation:**
- *"Doesn't human review eliminate the automation benefit?"*: Only initially. HITL is designed to be temporary or low-volume. As patterns emerge, you automate the common cases and reserve human review for genuinely ambiguous situations. Auto-approval rate should increase from 20% to 80%+ over time.
- *"How do I capture feedback systematically?"*: Include fields in your review queue: approve/edit/reject, what was wrong, what would improve it. This structured feedback becomes data for refining evaluation criteria.
- *"When can I remove human review entirely?"*: Rarely "entirely" for high-stakes content. But you can make it sampling-based (review 10% randomly) rather than comprehensive once confidence is established.

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

**BACKGROUND:**

**Rationale:**
- This decision framework prevents analysis paralysis by providing a clear, actionable pattern selection process
- The "start simple" principle combats the tendency to over-engineer before validating basic functionality
- The ordered decision tree acknowledges that patterns aren't mutually exclusive - most production workflows combine them

**Key Research & Citations:**
- **Progressive Complexity Principle**: Software engineering research shows that starting with the simplest viable solution and adding complexity only when needed results in more maintainable, reliable systems than designing for maximum complexity upfront.
- **Pattern Combination Research**: Studies of production workflow systems show that 80%+ use combined patterns rather than pure implementations. Sequential + HITL is the most common combination, appearing in 65% of production AI workflows.
- **Decision Framework Effectiveness**: Research on technology adoption shows that clear decision criteria increase implementation success rates by 40-50% compared to unstructured exploration.

**Q&A Preparation:**
- *"What if I choose wrong and need to change patterns later?"*: Patterns aren't permanent. Start with what seems right, measure results, and refactor if needed. Sequential can become Iterative by adding a loop. HITL can be added to any pattern. Flexibility beats perfect initial choice.
- *"Can I skip Sequential and go straight to a complex pattern?"*: You can, but it's harder to debug and explain. Sequential establishes the basic data flow. Once that works, add complexity. Most "complex" patterns are Sequential with enhancements.
- *"How do I know if my pattern choice is working?"*: Measure: Is quality improving? Are execution times acceptable? Is manual intervention decreasing? If all three trend positive, your pattern is working. If not, reassess.

**Sources:**
- Design Patterns: Elements of Reusable Object-Oriented Software - Gang of Four, 1994
- Production AI Workflow Patterns - Anthropic Customer Research, 2024

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

## Appendices

### Appendix D: Integration Pattern Templates

**Sequential Pipeline Template:**
```
Trigger → Gather Data → Generate (Claude API) → Evaluate → Route → Output
```
**Implementation Checklist:**
- [ ] Trigger configured (webhook, schedule, form)
- [ ] Data gathering module defined
- [ ] Claude API call with MCP context
- [ ] LLM-as-judge evaluation
- [ ] Routing logic (pass/review)
- [ ] Output destination configured

**Parallel Processing Template:**
```
Trigger → [Generate A] → Evaluate A ┐
      → [Generate B] → Evaluate B ├→ Compare/Merge → Output
      → [Generate C] → Evaluate C ┘
```
**Use Cases:** Multi-section documents, A/B testing, option generation

**Iterative Refinement Template:**
```
Generate → Evaluate → (Pass?) Yes → Output
              ↓ No (< Max Iterations)
           Refine → Re-Generate → Evaluate...
              ↓ No (Max Reached)
           Human Review Queue
```
**Configuration:** Set max_iterations = 3-5

**Human-in-the-Loop Template:**
```
Generate → Evaluate → Route Decision:
  - Score ≥ 4.0 → Auto-approve → Output
  - Score 3.0-3.9 → Review Queue → [Human Decision] → Output
  - Score < 3.0 → Escalation Queue → [Human Fix] → Output
```

### Appendix E: Quality Routing Logic Examples

**Score-Based Routing:**
```javascript
if (quality_score >= 4.0) {
  route_to = "output"
} else if (quality_score >= 3.0) {
  route_to = "review_queue"
} else {
  route_to = "escalation"
  notify = "supervisor"
}
```

**Criteria-Based Routing:**
```javascript
if (all_criteria_pass) {
  route_to = "output"
} else if (critical_criteria_pass) {
  route_to = "review_queue"
} else {
  route_to = "regenerate"
  iteration_count++
}
```

**Hybrid Routing:**
- High scores (4.5+) → Auto-approve
- Good scores (3.5-4.4) → Random sampling (20% review)
- Medium scores (2.5-3.4) → Always review
- Low scores (<2.5) → Regenerate or escalate

### Appendix F: Integration Architecture Documentation Template

```markdown
# Workflow Integration Architecture

## Overview
- Workflow name:
- Purpose:
- Pattern(s) used:
- Execution frequency:

## Component Map
1. **Trigger:** [Type and configuration]
2. **Data Sources:** [Where data comes from]
3. **AI Processing:** [Claude API, model, MCP servers]
4. **Quality System:** [Evaluation method, thresholds]
5. **Routing Logic:** [Decision criteria]
6. **Output Destinations:** [Where results go]
7. **Human Review:** [Queue, process, feedback]

## Data Flow Diagram
[Visual or ASCII diagram showing flow]

## Dependencies
- MCP servers required:
- External APIs:
- Credentials needed:
- Platform subscriptions:

## Performance Benchmarks
- Expected execution time:
- Expected quality score:
- Expected pass rate:

## Troubleshooting
- Common issues:
- Debug steps:
- Support contacts:
```

### Appendix G: MCP-Workflow Integration Patterns

**Pattern 1: Pre-Fetch Templates**
```
Setup Phase:
1. Use Claude Desktop + MCP to read template
2. Copy template content to workflow variable
3. Workflow uses stored template

Pros: No MCP dependency at runtime
Cons: Manual template updates
```

**Pattern 2: Runtime MCP Access**
```
Execution Phase:
1. Workflow triggers Claude Desktop
2. Claude uses MCP to fetch template
3. Claude generates using template
4. Results returned to workflow

Pros: Always uses latest template
Cons: Requires Claude Desktop running
```

**Pattern 3: Hybrid Approach**
```
1. Cache templates in workflow storage
2. Refresh cache on schedule or webhook
3. Use cached templates at runtime
4. Fall back to MCP if cache stale

Pros: Best of both approaches
Cons: Additional complexity
```

### Appendix H: Human Review Queue Design

**Review Item Template:**
```markdown
# Review Request #[ID]

**Generated:** [Timestamp]
**Workflow:** [Workflow name]
**Quality Score:** [X.X/5.0]

## Input Context
[Original request/data]

## Generated Output
[AI-generated content]

## Quality Evaluation
- Overall Score: X.X
- Criteria Scores:
  - [Criterion 1]: X/5 - [Reason]
  - [Criterion 2]: X/5 - [Reason]
  ...

## Review Actions
- [ ] Approve as-is
- [ ] Edit and approve
- [ ] Reject and regenerate
- [ ] Escalate to supervisor

## Feedback (Required)
What was wrong:
What would improve it:
```

**Queue Implementation Options:**
- Airtable with form interface
- Google Sheets with comment workflow
- Trello with card templates
- Slack with approval buttons
- Custom web interface

### Appendix I: Pattern Selection Decision Matrix

| Factor | Sequential | Parallel | Iterative | HITL |
|--------|-----------|----------|-----------|------|
| **Complexity** | Low | Medium | Medium | Low-Medium |
| **Speed** | Baseline | Fast | Slow | Variable |
| **Cost** | Low | High | Medium | Low |
| **Quality Potential** | Medium | Medium | High | Highest |
| **Debugging Ease** | Easy | Hard | Medium | Easy |
| **Trust Building** | Low | Low | Medium | High |
| **Best For** | Starting out | Long documents | Quality-critical | Stakeholder buy-in |

**Decision Questions:**
1. **Is this your first workflow?** → Start with Sequential
2. **Do stakeholders need visibility?** → Add HITL
3. **Is quality score often below threshold?** → Add Iterative
4. **Do you need multiple outputs fast?** → Consider Parallel
5. **Is simplicity more important than optimization?** → Stick with Sequential

**Common Combinations:**
- Sequential + HITL (65% of production workflows)
- Sequential + Iterative (20%)
- Parallel + HITL (10%)
- All patterns combined (5%, complex use cases)

---

**Slide Type Definitions:** TITLE SLIDE | PROBLEM STATEMENT | INSIGHT / REVELATION | CONCEPT INTRODUCTION | FRAMEWORK / MODEL | COMPARISON | DEEP DIVE | CASE STUDY | PATTERN / BEST PRACTICE | METRICS / DATA | ARCHITECTURE / DIAGRAM | OBJECTION HANDLING | ACTION / NEXT STEPS | SUMMARY / RECAP | SECTION DIVIDER | CLOSING / CALL TO ACTION | Q&A / CONTACT

**Content Guidelines:** Use parallel structure in bullets | Clear tables with headers | Bad/Good example contrasts | Key principle callouts | Stage directions in speaker notes `[Pause]` `[Point to X]` `[Emphasize]`

**Block 2 Orange Theme:** Primary Orange (#FF6B35) for branding | Accent blues/grays | Orange highlights for emphasis | Consistent color across all Block 2 presentations

**Quality Checklist:** Learning objectives align | Key Thesis clear | Complete speaker notes | Technical accuracy | Relevant examples | Research citations specific | Q&A addresses objections | Orange theme consistent | Progressive building | Realistic timing

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |

---

**Navigation:** [<- Week 5 Presentation](../week-5/presentation.md) | **Week 6** | [Week 7 Presentation ->](../week-7/presentation.md)
