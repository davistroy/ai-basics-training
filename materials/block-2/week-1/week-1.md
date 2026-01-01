# Week 1: Automation Platforms Introduction

**Block:** 2 - AI Workflow Engineering
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Block 1 Capstone completed and approved
- [ ] GitHub prompt library accessible and organized
- [ ] Understanding of quality rubrics and gates
- [ ] One workflow candidate identified from Block 1 task priority matrix

## Exit Criteria

- [ ] Understands automation platform landscape
- [ ] Decision matrix completed for platform selection
- [ ] MCP Server Registry explored and relevant servers identified
- [ ] Performance monitoring metrics defined
- [ ] Platform selected for Block 2 work

---

## Workshop Content (45 minutes)

### Segment 1: Welcome to Block 2 + Recap (8 min)

- Welcome back and Block 2 overview
- **Maturity progression reminder:**
  - Level 1: Templated workflows (Block 1 - completed)
  - Level 2: Workflow engineering (Block 2 - starting now)
  - Level 3: Automation architecture (Block 3 - future)
- **Key shift:** From manual prompting to automated execution
- Preview of capstone deliverables

### Segment 2: Automation Platform Landscape (12 min)

**The evolution:**
```
Manual → Templates → Workflows → Agents
```

**Platform categories:**

| Category | Platforms | Best For |
|----------|-----------|----------|
| **No-code** | Zapier, Make (Integromat), Power Automate | Business users, quick setup |
| **Low-code** | n8n, Retool, Pipedream | Technical comfort, more control |
| **AI-native** | Claude MCP, OpenAI Assistants API, LangChain | Deep AI integration |
| **Enterprise** | UiPath, Automation Anywhere | Large scale, governance |

**Key considerations:**
- Learning curve vs. capability
- Cost structure (per execution vs. flat fee)
- AI integration depth
- Team collaboration features
- Data security requirements

**Recommendation:** Start with Make or n8n for most consultants

> **AI Data Handling Awareness**
>
> When automating workflows that process client or sensitive data:
> - **Know your data flows:** Understand what data passes through each platform and AI service
> - **Check data retention policies:** Most AI providers retain data temporarily; know the specifics
> - **Client obligations first:** Review client contracts for data handling requirements before automating
> - **When in doubt, anonymize:** Use placeholder data for testing; sanitize sensitive fields
> - **Document your choices:** Record which platforms handle which data types for compliance

### Segment 3: Decision Matrix for Platform Selection (12 min)

**The framework:**

| Criterion | Weight | Platform A | Platform B | Platform C |
|-----------|--------|------------|------------|------------|
| Learning Curve | 20% | | | |
| AI Integration | 25% | | | |
| Cost | 15% | | | |
| Collaboration | 15% | | | |
| Security | 15% | | | |
| Scalability | 10% | | | |

**Scoring guide:** 1-5 for each criterion

**Live exercise:** Group rates one platform together

### Segment 4: MCP Introduction + Registry Preview (13 min)

**Model Context Protocol (MCP) Deep Dive - "USB-C for AI":**
- Universal protocol for AI tool connections
- Servers provide capabilities (file access, database, APIs)
- Claude and other AI tools connect via MCP

**MCP Server Registry:**
- Official servers: filesystem, GitHub, Slack, databases
- Community servers: Google Drive, Notion, custom tools
- How to find what you need

**Live demo:** Browse MCP registry, show popular servers

**Performance monitoring preview:**
- Why track from the start
- Core metrics: execution time, success rate, quality, cost
- Simple logging approach (Week 2 deep dive)

---

## Self-Paced Exercises (60 minutes total)

### Exercise 1.1: Platform Research & Decision Matrix (25 minutes)

*Select your automation platform*

1. Research 2-3 platforms from your category:

**For No-Code Preference:**
- Make (Integromat)
- Zapier
- Power Automate

**For Technical Comfort:**
- n8n (self-hosted or cloud)
- Pipedream

2. Complete decision matrix for your top 3 choices:

```markdown
# Platform Decision Matrix

| Criterion | Weight | [Platform 1] | [Platform 2] | [Platform 3] |
|-----------|--------|--------------|--------------|--------------|
| Learning Curve (1=hard, 5=easy) | 20% | | | |
| AI Integration Depth | 25% | | | |
| Cost (for your usage) | 15% | | | |
| Team Collaboration | 15% | | | |
| Security Features | 15% | | | |
| Scalability | 10% | | | |
| **Weighted Total** | | | | |

## Decision
Selected Platform: [Name]
Rationale: [2-3 sentences explaining choice]
```

3. Create account on selected platform (free tier)
4. Complete platform's getting started tutorial

**Deliverable:** `platform-decision-matrix.md` + platform account created

**Resources:**
- [Make Documentation](https://www.make.com/en/help)
- [n8n Documentation](https://docs.n8n.io/)
- [Zapier Learning Center](https://zapier.com/learn)
- [Power Automate Documentation](https://learn.microsoft.com/en-us/power-automate/)

---

### Exercise 1.2: MCP Server Registry Exploration (20 minutes)

*Discover available integrations*

1. Browse the MCP Server Registry
2. Identify 5-10 servers relevant to your work:

```markdown
# MCP Server Analysis

## Highly Relevant Servers

| Server Name | Capability | My Use Case | Priority |
|-------------|------------|-------------|----------|
| filesystem | Read/write local files | Access prompt templates | High |
| github | Repository operations | Pull templates, push outputs | High |
| | | | |

## Potentially Useful Servers

| Server Name | Capability | Possible Use Case | Explore Later? |
|-------------|------------|-------------------|----------------|
| | | | |
```

3. For your top 3 servers, note:
   - What it does
   - How you'd use it
   - Any prerequisites (API keys, etc.)

4. Install Claude Desktop if not already (MCP requires desktop client)

**Deliverable:** `mcp-server-analysis.md`

**Resources:**
- [MCP Server Registry](https://github.com/modelcontextprotocol/servers)
- [Claude Desktop Download](https://claude.ai/download)
- [MCP Introduction](https://modelcontextprotocol.io/introduction)

---

### Exercise 1.3: Define Performance Metrics (15 minutes)

*Establish measurement framework*

1. For your highest-priority workflow (from Block 1), define:

```markdown
# Workflow Performance Metrics

## Workflow: [Name]
**Purpose:** [What this workflow does]
**Current State:** Manual prompting with template

## Metrics to Track

### Execution Metrics
- **Execution Time:** How long from start to finish?
  - Baseline (manual): ___ minutes
  - Target (automated): ___ minutes

- **Success Rate:** % of executions producing usable output
  - Target: ___%

### Quality Metrics
- **Rubric Score:** Average score against quality rubric
  - Minimum acceptable: ___/5
  - Target: ___/5

- **Revision Rate:** % requiring human revision
  - Target: < ___%

### Cost Metrics
- **Cost Per Execution:** AI API costs + platform costs
  - Acceptable range: $___-$___

- **Time Investment:** Human time per execution
  - Baseline: ___ minutes
  - Target: ___ minutes

## Tracking Method
[How will you record these? Spreadsheet, database, platform analytics?]
```

2. Create simple tracking spreadsheet or document

**Deliverable:** `workflow-metrics-definition.md` + tracking template

---

## Key Takeaways

1. **Automation platforms vary in complexity** - Match platform to your skills and needs
2. **MCP enables deep AI integration** - Understand the protocol for Block 2 work
3. **Performance metrics from day one** - What you measure, you can improve
4. **Decision matrices reduce bias** - Systematic evaluation over gut feeling
5. **Block 2 builds on Block 1** - Your templates become automation inputs

---

## Preparation for Week 2

- Complete platform account setup and tutorials
- Install Claude Desktop for MCP
- Review your Block 1 templates - which is best for automation?
- Have your workflow candidate ready for Week 2

---

## Resources

- [Make Documentation](https://www.make.com/en/help)
- [n8n Documentation](https://docs.n8n.io/)
- [MCP Server Registry](https://github.com/modelcontextprotocol/servers)
- [Claude Desktop](https://claude.ai/download)
- [MCP Introduction](https://modelcontextprotocol.io/introduction)
