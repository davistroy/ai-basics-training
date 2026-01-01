# **BLOCK 2 WEEK 1: Automation Platforms Introduction**

**Block:** 2: AI Workflow Engineering
**Week:** 1 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** [Block 1 Week 8](../../block-1/week-8/participant-guide.md) | **Week 1** | [Week 2 →](../week-2/participant-guide.md)

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

By the end of this week, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Compare automation platform categories and select one for Block 2 work | Exercise 1.1 |
| 2 | Apply a weighted decision matrix for systematic platform evaluation | Exercise 1.1 |
| 3 | Identify relevant MCP servers for your workflow integration needs | Exercise 1.2 |
| 4 | Define performance metrics for workflow monitoring | Exercise 1.3 |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Block 1 Capstone completed and approved
- [ ] GitHub prompt library accessible and organized
- [ ] Understanding of quality rubrics and gates from Block 1
- [ ] One workflow candidate identified from Block 1 task priority matrix

**Not ready?** Complete Block 1 requirements or reach out in the support channel for help.

---

## Key Concepts

### Concept 1: The Automation Maturity Progression

**Definition:**
The path from manual AI use to fully automated systems, progressing through four levels of increasing sophistication and reliability.

**Why It Matters:**
Understanding where you are and where you're going helps you make appropriate tool and technique choices. Skipping levels leads to fragile systems.

**Core Principle:**
> Block 2 takes you from Level 1 (templated workflows) to Level 2 (workflow engineering). Block 3 continues to Level 3 (automation architecture).

**The Progression:**
```
Level 1: Templates       → You created prompt templates in Block 1
Level 2: Workflows       → You'll build automated workflows in Block 2
Level 3: Agents          → You'll design agent systems in Block 3
Level 4: Orchestration   → Multi-agent systems (advanced)
```

**Common Mistake:**
Trying to jump straight to "agents" without solid workflow foundations. Workflows are the building blocks of reliable agents.

---

### Concept 2: Automation Platform Categories

**Definition:**
Automation platforms can be grouped into four categories based on technical requirements and capabilities.

**Why It Matters:**
Choosing the right category of platform matches your skills to capabilities, reducing learning curve while meeting your needs.

**The Categories:**

| Category | Platforms | Best For | Learning Curve |
|----------|-----------|----------|----------------|
| **No-Code** | Zapier, Make, Power Automate | Business users, quick setup | Lowest |
| **Low-Code** | n8n, Retool, Pipedream | Technical comfort, more control | Medium |
| **AI-Native** | Claude MCP, OpenAI Assistants, LangChain | Deep AI integration | Higher |
| **Enterprise** | UiPath, Automation Anywhere | Large scale, governance | Highest |

**When to Use:**
- No-code: You want to get started quickly without technical complexity
- Low-code: You want more control and are comfortable with some technical concepts
- AI-native: Your primary focus is AI integration depth
- Enterprise: You need governance, audit trails, and massive scale

**Recommendation for Most Consultants:**
Start with **Make** or **n8n**. Both offer excellent AI integration with manageable learning curves.

---

### Concept 3: Model Context Protocol (MCP)

**Definition:**
MCP is a universal protocol that allows AI systems (like Claude) to connect to external tools, files, and data sources through standardized "servers."

**Why It Matters:**
MCP eliminates the need to build custom integrations. Instead of coding connections, you configure pre-built servers that handle the communication.

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| **Host** | The AI interface (Claude Desktop) | Claude Desktop application |
| **Server** | Bridge to external capabilities | Filesystem server, GitHub server |
| **Tools** | Specific actions a server provides | Read file, create repository |
| **Resources** | Data sources a server exposes | File contents, repo metadata |

**Visual Reference:**
```
┌─────────────────┐
│  Claude Desktop │  ← Host (your AI interface)
│    (Host)       │
└────────┬────────┘
         │ MCP Protocol
         ▼
┌─────────────────┐
│   MCP Server    │  ← Bridge (pre-built connector)
│   (Bridge)      │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ External Tool   │  ← Your files, APIs, databases
│ (Capability)    │
└─────────────────┘
```

**The USB-C Analogy:**
Just like USB-C lets you connect any device to any computer without special adapters, MCP lets Claude connect to any tool that has an MCP server.

---

### Concept 4: Decision Matrix for Platform Selection

**Definition:**
A weighted scoring system that evaluates options against defined criteria, producing a numerical comparison for decision-making.

**Why It Matters:**
Decision matrices reduce bias and "analysis paralysis" by making evaluation systematic and comparable.

**The Framework:**

| Criterion | Weight | Why This Weight |
|-----------|--------|-----------------|
| Learning Curve | 20% | You need to be productive quickly |
| AI Integration | 25% | Highest priority - this is an AI workflow course |
| Cost | 15% | Budget matters but isn't the primary driver |
| Collaboration | 15% | Team rollout potential |
| Security | 15% | Client data handling requirements |
| Scalability | 10% | Growth potential (less urgent for learning) |

**Scoring Guide:**
- 5 = Excellent / Very Easy / Best in class
- 4 = Good / Easy / Above average
- 3 = Adequate / Moderate / Average
- 2 = Poor / Difficult / Below average
- 1 = Missing / Very Difficult / Inadequate

---

### Quick Reference: Platform Selection Criteria

| Criterion | What to Evaluate | Where to Find Info |
|-----------|-----------------|-------------------|
| Learning Curve | Time to first workflow, documentation quality | Platform tutorials, reviews |
| AI Integration | Native AI modules, API flexibility, model support | Platform documentation |
| Cost | Free tier limits, execution pricing, scaling costs | Pricing pages |
| Collaboration | Team features, sharing, permissions | Feature lists |
| Security | Data handling, compliance certifications | Security documentation |
| Scalability | Execution limits, enterprise options | Pricing/enterprise pages |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Introduction to automation platforms and MCP as the foundation for Block 2 workflow engineering.

**Key Points from Each Segment:**

**Segment 1: Welcome to Block 2 + Recap**
- Block 2 shifts from manual prompting to automated workflows
- Maturity progression: Templates → Workflows → Agents
- Your Block 1 work becomes input to Block 2 workflows
- Capstone: AI Workflow Toolkit with 3 workflows and MCP integration

**Segment 2: Automation Platform Landscape**
- Four platform categories: No-code, Low-code, AI-native, Enterprise
- Key considerations: Learning curve, AI integration, cost, collaboration, security, scalability
- Recommendation: Make or n8n for most consultants
- Data handling awareness: Know your data flows before automating

**Segment 3: Decision Matrix for Platform Selection**
- Six weighted criteria for systematic evaluation
- Scoring 1-5 for each criterion
- Calculate weighted totals for comparison
- Document your rationale

**Segment 4: MCP Introduction + Registry Preview**
- MCP is "USB-C for AI" - universal protocol for tool connections
- MCP servers provide capabilities (filesystem, GitHub, Slack, etc.)
- Official and community servers available
- Performance monitoring: Track from day one

### Demo Recap

**What Was Demonstrated:**
Browsing the MCP Server Registry to identify available integrations

**Key Steps:**
1. Navigated to MCP Server Registry on GitHub
2. Explored official servers (filesystem, GitHub)
3. Reviewed server capabilities and use cases

**Result:**
Understanding of available MCP servers for workflow enhancement

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 1.1 | 25 min | `platform-decision-matrix.md` | Platform selection |
| 1.2 | 20 min | `mcp-server-analysis.md` | MCP server selection |
| 1.3 | 15 min | `workflow-metrics-definition.md` | Performance monitoring |

---

### Exercise 1.1: Platform Research & Decision Matrix

**Duration:** 25 minutes

**Purpose:**
Select your automation platform for Block 2 using systematic evaluation. This platform will be your foundation for all workflow exercises.

**You Will Create:**
A completed decision matrix with platform selection and rationale, plus an active platform account.

---

#### Instructions

**Step 1: Identify Your Category**

Based on your technical comfort level, focus your research on one category:

**For No-Code Preference (recommended for most):**
- Make (Integromat) - [www.make.com](https://www.make.com)
- Zapier - [www.zapier.com](https://www.zapier.com)
- Power Automate - [powerautomate.microsoft.com](https://powerautomate.microsoft.com)

**For Technical Comfort:**
- n8n - [www.n8n.io](https://www.n8n.io)
- Pipedream - [www.pipedream.com](https://www.pipedream.com)

**Step 2: Research 2-3 Platforms**

For each platform, investigate:
- Getting started tutorials (how long to first workflow?)
- AI/API integration capabilities
- Pricing structure (free tier limits)
- Team features
- Security documentation

Spend about 5-7 minutes per platform.

**Step 3: Complete Decision Matrix**

Use the template below to score each platform.

**Step 4: Calculate Weighted Scores**

For each platform:
```
Weighted Score = (Learning × 0.20) + (AI × 0.25) + (Cost × 0.15) +
                 (Collaboration × 0.15) + (Security × 0.15) + (Scalability × 0.10)
```

**Step 5: Make Your Decision**

Select the platform with the highest weighted score (or close to it if you have a strong preference).

**Step 6: Create Your Account**

- Go to your selected platform
- Create a free account
- Complete the "getting started" or onboarding tutorial

**Step 7: Review Your Work**

Check that your deliverable includes:
- [ ] Scores for all 6 criteria across 2-3 platforms
- [ ] Weighted totals calculated
- [ ] Clear selection with rationale
- [ ] Account created confirmation

---

#### Deliverable Specification

**File Name:** `platform-decision-matrix.md`

**Location:** Your Block 2 folder in GitHub repository

**Format Requirements:**
- Markdown format
- All criteria scored
- Weighted totals calculated
- Selection rationale included

**Quality Criteria:**
- [ ] At least 2 platforms compared (3 preferred)
- [ ] Scores are realistic and based on research (not guessed)
- [ ] Rationale explains why selected platform fits YOUR needs
- [ ] Account creation noted

---

#### Template

```markdown
# Platform Decision Matrix

**Date:** [YYYY-MM-DD]
**Prepared By:** [Your Name]

## Platforms Evaluated

1. [Platform 1 Name]
2. [Platform 2 Name]
3. [Platform 3 Name] (optional)

## Scoring Matrix

| Criterion | Weight | [Platform 1] | [Platform 2] | [Platform 3] |
|-----------|--------|--------------|--------------|--------------|
| Learning Curve (1=hard, 5=easy) | 20% | | | |
| AI Integration Depth | 25% | | | |
| Cost (for your usage) | 15% | | | |
| Team Collaboration | 15% | | | |
| Security Features | 15% | | | |
| Scalability | 10% | | | |
| **Weighted Total** | 100% | | | |

## Calculation Notes

**[Platform 1]:**
(___ × 0.20) + (___ × 0.25) + (___ × 0.15) + (___ × 0.15) + (___ × 0.15) + (___ × 0.10) = ___

**[Platform 2]:**
(___ × 0.20) + (___ × 0.25) + (___ × 0.15) + (___ × 0.15) + (___ × 0.15) + (___ × 0.10) = ___

**[Platform 3]:**
(___ × 0.20) + (___ × 0.25) + (___ × 0.15) + (___ × 0.15) + (___ × 0.15) + (___ × 0.10) = ___

## Decision

**Selected Platform:** [Name]

**Rationale:**
[2-3 sentences explaining why this platform is the best choice for your specific needs. Reference your scores and any personal factors like existing experience or team requirements.]

## Account Status

- [ ] Free account created
- [ ] Getting started tutorial completed
- [ ] Ready for Week 2 workflow building

## Notes

[Any additional observations, concerns, or things to explore later]
```

---

#### Tips & Troubleshooting

**Tips:**
- Don't over-research. 5-7 minutes per platform is enough
- If truly stuck between two, pick Make - it has the gentlest learning curve
- The skills transfer between platforms, so you're not locked in forever

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Can't decide between two platforms | Check AI integration specifically - that's the highest weight for a reason |
| Platform requires credit card | Try a different platform, or use virtual card with low limit |
| Getting started tutorial is very long | Complete the first 2-3 steps minimum, finish rest before Week 2 |

---

### Exercise 1.2: MCP Server Registry Exploration

**Duration:** 20 minutes

**Purpose:**
Discover MCP servers that can enhance your workflows. This exploration prepares you for Week 5-6 MCP integration.

**You Will Create:**
An analysis of MCP servers relevant to your work, prioritized by usefulness.

---

#### Instructions

**Step 1: Access the MCP Server Registry**

Go to: [https://github.com/modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers)

**Step 2: Browse Available Servers**

Explore the registry and identify:
- Official servers (maintained by Anthropic)
- Community servers (third-party contributions)
- Categories that relate to your work

**Step 3: Identify 5-10 Relevant Servers**

For each server you identify as potentially useful:
- What capability does it provide?
- How would you use it in your work?
- What priority would you assign? (High/Medium/Low)

**Step 4: Deep Dive on Top 3**

For your top 3 highest-priority servers, document:
- Detailed capabilities
- Prerequisites (API keys, accounts needed)
- Setup complexity

**Step 5: Install Claude Desktop (if not already)**

MCP requires Claude Desktop. Download from: [https://claude.ai/download](https://claude.ai/download)

**Step 6: Review Your Work**

Check that your deliverable includes:
- [ ] At least 5 servers identified
- [ ] Use cases specific to YOUR work
- [ ] Top 3 servers with detailed notes
- [ ] Claude Desktop installed

---

#### Deliverable Specification

**File Name:** `mcp-server-analysis.md`

**Location:** Your Block 2 folder in GitHub repository

**Quality Criteria:**
- [ ] Minimum 5 servers identified
- [ ] Use cases are specific, not generic
- [ ] Priority rankings reflect actual relevance to your work
- [ ] Top 3 servers have prerequisites documented

---

#### Template

```markdown
# MCP Server Analysis

**Date:** [YYYY-MM-DD]
**Prepared By:** [Your Name]

## Overview

This analysis identifies MCP servers relevant to my consulting workflow automation needs.

## Highly Relevant Servers

| Server Name | Capability | My Use Case | Priority |
|-------------|------------|-------------|----------|
| filesystem | Read/write local files | Access prompt templates from local directory | High |
| github | Repository operations | Pull templates from prompt library, push outputs | High |
| | | | |
| | | | |
| | | | |

## Potentially Useful Servers

| Server Name | Capability | Possible Use Case | Explore Later? |
|-------------|------------|-------------------|----------------|
| | | | |
| | | | |
| | | | |

## Top 3 Server Deep Dive

### Server 1: [Name]

**What It Does:**
[Detailed description of capabilities]

**How I'll Use It:**
[Specific use cases in your workflows]

**Prerequisites:**
- [ ] [Requirement 1 - e.g., API key needed]
- [ ] [Requirement 2 - e.g., account setup]
- [ ] [Requirement 3]

**Setup Complexity:** [Low / Medium / High]

### Server 2: [Name]

**What It Does:**
[Detailed description]

**How I'll Use It:**
[Specific use cases]

**Prerequisites:**
- [ ] [Requirements]

**Setup Complexity:** [Low / Medium / High]

### Server 3: [Name]

**What It Does:**
[Detailed description]

**How I'll Use It:**
[Specific use cases]

**Prerequisites:**
- [ ] [Requirements]

**Setup Complexity:** [Low / Medium / High]

## Claude Desktop Status

- [ ] Claude Desktop installed
- [ ] Verified working
- [ ] Ready for MCP configuration (Week 5)

## Notes

[Any observations, questions, or things to investigate further]
```

---

#### Tips & Troubleshooting

**Tips:**
- Start with filesystem and GitHub servers - they're useful for almost everyone
- Look for servers that match tools you already use (Slack, Google Drive, Notion)
- Don't worry about understanding everything now - we'll configure in Week 5

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Registry seems overwhelming | Start with the "Official" section only |
| Not sure what servers do | Click into each for README with details |
| Claude Desktop won't install | Check system requirements, try different browser for download |

---

### Exercise 1.3: Define Performance Metrics

**Duration:** 15 minutes

**Purpose:**
Establish a measurement framework for your workflows before you build them. What you measure from the start, you can improve.

**You Will Create:**
A metrics definition document for your priority workflow, with baseline and target values.

---

#### Instructions

**Step 1: Select Your Priority Workflow**

From your Block 1 task priority matrix, identify the workflow you most want to automate.

**Step 2: Define Execution Metrics**

- How long does it currently take manually?
- What's your target for automated execution?
- What success rate do you expect?

**Step 3: Define Quality Metrics**

- What rubric will you use? (From Block 1)
- What's the minimum acceptable score?
- What percentage can require human revision?

**Step 4: Define Cost Metrics**

- What's acceptable cost per execution?
- How much human time per execution currently?
- What's your target human time?

**Step 5: Choose Tracking Method**

How will you record metrics?
- Google Sheets (simplest)
- Airtable (more structured)
- Platform built-in logging

**Step 6: Review Your Work**

Check that your deliverable includes:
- [ ] All three metric categories addressed
- [ ] Baseline (current) values estimated
- [ ] Target values set
- [ ] Tracking method chosen

---

#### Deliverable Specification

**File Name:** `workflow-metrics-definition.md`

**Location:** Your Block 2 folder in GitHub repository

**Quality Criteria:**
- [ ] Specific workflow identified
- [ ] Realistic baseline estimates
- [ ] Achievable but ambitious targets
- [ ] Tracking method is practical

---

#### Template

```markdown
# Workflow Performance Metrics

**Date:** [YYYY-MM-DD]
**Prepared By:** [Your Name]

## Workflow Identification

**Workflow Name:** [Name]

**Purpose:** [What this workflow does - 1-2 sentences]

**Current State:** Manual prompting with Block 1 template

**Selected for automation because:** [Brief rationale]

## Execution Metrics

### Execution Time
How long from start to finish?

| Measure | Value |
|---------|-------|
| Baseline (manual) | ___ minutes |
| Target (automated) | ___ minutes |
| Expected improvement | ___% reduction |

### Success Rate
Percentage of executions producing usable output

| Measure | Value |
|---------|-------|
| Current estimate | ___% |
| Target | ___% |

## Quality Metrics

### Rubric Score
Average score against quality rubric

| Measure | Value |
|---------|-------|
| Rubric used | [Link to Block 1 rubric] |
| Minimum acceptable | ___/5 |
| Target average | ___/5 |

### Revision Rate
Percentage requiring human revision after automated output

| Measure | Value |
|---------|-------|
| Acceptable maximum | < ___% |
| Target | < ___% |

## Cost Metrics

### Cost Per Execution
AI API costs + platform costs

| Measure | Value |
|---------|-------|
| Acceptable range | $___-$___ |
| Target | < $___ |

### Human Time Investment
Time you spend per execution

| Measure | Value |
|---------|-------|
| Baseline (manual) | ___ minutes |
| Target (automated) | ___ minutes |
| Expected savings | ___ minutes/execution |

## Tracking Method

**Selected Method:** [Google Sheets / Airtable / Platform Logs / Other]

**Why This Method:**
[Brief rationale for your choice]

**Tracking Frequency:**
[Every execution / Daily summary / Weekly review]

## Monthly Projection

Based on estimated usage of ___ executions per month:

| Metric | Monthly Impact |
|--------|----------------|
| Time saved | ___ hours |
| Value of time saved (@ $___/hr) | $___ |
| Estimated automation cost | $___ |
| Net value | $___ |

## Notes

[Any assumptions, uncertainties, or things to validate during Week 2-3]
```

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| Platform Decision Matrix | Systematic platform evaluation | Exercise 1.1 |
| MCP Server Analysis | Integration planning | Exercise 1.2 |
| Workflow Metrics Definition | Performance tracking setup | Exercise 1.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| Make Documentation | Tutorial | [make.com/en/help](https://www.make.com/en/help) | Platform setup |
| n8n Documentation | Tutorial | [docs.n8n.io](https://docs.n8n.io/) | Platform setup |
| Zapier Learning Center | Tutorial | [zapier.com/learn](https://zapier.com/learn) | Platform setup |
| Power Automate Docs | Tutorial | [learn.microsoft.com/power-automate](https://learn.microsoft.com/en-us/power-automate/) | Platform setup |
| MCP Server Registry | Reference | [github.com/modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) | Server exploration |
| Claude Desktop Download | Tool | [claude.ai/download](https://claude.ai/download) | MCP prerequisite |
| MCP Introduction | Documentation | [modelcontextprotocol.io/introduction](https://modelcontextprotocol.io/introduction) | Understanding MCP |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Compare automation platforms systematically | Completed decision matrix with scores | ☐ |
| 2 | Select appropriate platform for your needs | Platform account created and ready | ☐ |
| 3 | Identify relevant MCP servers | 5+ servers documented with use cases | ☐ |
| 4 | Define workflow performance metrics | Metrics document with baselines and targets | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Platform Decision Matrix | `platform-decision-matrix.md` | Block 2 folder | ☐ |
| MCP Server Analysis | `mcp-server-analysis.md` | Block 2 folder | ☐ |
| Workflow Metrics | `workflow-metrics-definition.md` | Block 2 folder | ☐ |
| Platform Account | N/A | Platform website | ☐ |
| Claude Desktop | N/A | Installed locally | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** What concept or technique suddenly made sense?

2. **What's still fuzzy?** What do you need more practice or clarification on?

3. **How will you apply this?** Which workflow from your Block 1 priority matrix are you most excited to automate?

4. **What surprised you?** Was anything about the platforms or MCP easier or harder than expected?

---

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Tag your cohort for quick tips

### Common Questions This Week

**Q: Which platform should I choose if I'm completely undecided?**
A: Start with Make. It has the gentlest learning curve and strong AI integration. You can always switch later - the concepts transfer.

**Q: Do I really need Claude Desktop for MCP?**
A: Yes, for now. MCP integration requires the desktop client. We'll configure it in Week 5.

**Q: What if my organization already uses a different automation tool?**
A: If your organization uses a tool with AI integration capabilities, you can use that. Just ensure it can connect to AI APIs and handle the workflow patterns we'll cover.

### When to Ask for Help

- **Before asking:** Check this guide's troubleshooting sections
- **Good to ask:** "I tried [X] but got [Y] result. Here's what I expected..."
- **Include:** Your specific scenario, what you tried, and the result

---

## Looking Ahead

### Next Week Preview: Week 2 - Building Your First Workflow

**Focus:**
Building and testing your first end-to-end AI workflow with error handling and logging.

**How It Builds on This Week:**
You'll use the platform you selected to build an actual workflow automating the process you defined metrics for.

**To Prepare:**
- [ ] Complete all Week 1 exercises
- [ ] Finish platform getting started tutorial
- [ ] Have Claude Desktop installed
- [ ] Know which Block 1 template you'll automate first

---

## Glossary

| Term | Definition |
|------|------------|
| Automation Platform | Software that connects different tools and services to create automated workflows |
| MCP (Model Context Protocol) | A standardized protocol for connecting AI systems to external tools and data sources |
| MCP Server | A pre-built connector that provides specific capabilities (file access, API integration) to AI systems via MCP |
| Decision Matrix | A weighted scoring system for comparing options against defined criteria |
| No-Code Platform | Automation tool that requires no programming, using visual drag-and-drop interfaces |
| Low-Code Platform | Automation tool that minimizes coding but allows technical customization when needed |
| Workflow | A series of connected steps that automatically process data or complete tasks |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [Block 1 Week 8](../../block-1/week-8/participant-guide.md) | **Week 1** | [Week 2 →](../week-2/participant-guide.md)
