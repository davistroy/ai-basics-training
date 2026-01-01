# **BLOCK 2: AI Workflow Engineering**

**Version:** 3.1
**Last Updated:** 2026-01-01
**Status:** Active

---

**Navigation:** [← README](README.md) | [← Block 1](block-1.md) | **Block 2** | [Block 3 →](block-3.md)

---

## **8 Weeks | 45 min live + 60-75 min homework per week**

> **Pacing Note:** Weeks 5-6 (MCP integration) often require additional time for initial setup and troubleshooting. Budget extra time your first time configuring MCP servers.

-----

## **Prerequisites**

- Block 1 Certification: AI Prompting Practitioner
- Personal Prompt Library with 3+ documented templates
- GitHub repository with organized structure
- `style.json` and quality rubrics created
- Familiarity with ASK-CONTEXT-CONSTRAINTS-EXAMPLE framework

-----

## **Block 2 Overview**

**Target Audience:** Block 1 graduates creating recurring deliverables who want to move from manual prompting to automated workflows.

**Learning Objectives:**
- Build reusable workflow templates that execute multi-step AI processes
- Configure and use MCP (Model Context Protocol) for tool integration
- Create quality assurance systems for automated outputs
- Design performance monitoring for AI workflows
- Develop an AI Workflow Toolkit for team use

**Capstone:** AI Workflow Toolkit
- 3 workflow templates with rubrics
- MCP demonstration (functional integration)
- Performance metrics documentation
- Impact measurement with actual data

-----

## **Week 1: Automation Platforms Introduction**

### **Entry Criteria**

- [ ] Block 1 Capstone completed and approved
- [ ] GitHub prompt library accessible and organized
- [ ] Understanding of quality rubrics and gates
- [ ] One workflow candidate identified from Block 1 task priority matrix

### **Exit Criteria**

- [ ] Understands automation platform landscape
- [ ] Decision matrix completed for platform selection
- [ ] MCP Server Registry explored and relevant servers identified
- [ ] Performance monitoring metrics defined
- [ ] Platform selected for Block 2 work

-----

### **Workshop Content (45 minutes)**

**Segment 1: Welcome to Block 2 + Recap (8 min)**

- Welcome back and Block 2 overview
- **Maturity progression reminder:**
  - Level 1: Templated workflows (Block 1 - completed)
  - Level 2: Workflow engineering (Block 2 - starting now)
  - Level 3: Automation architecture (Block 3 - future)
- **Key shift:** From manual prompting to automated execution
- Preview of capstone deliverables

**Segment 2: Automation Platform Landscape (12 min)**

- **The evolution:** Manual → Templates → Workflows → Agents
- **Platform categories:**
  - **No-code platforms:** Zapier, Make (Integromat), Power Automate
  - **Low-code platforms:** n8n, Retool, Pipedream
  - **AI-native platforms:** Claude MCP, OpenAI Assistants API, LangChain
  - **Enterprise platforms:** UiPath, Automation Anywhere (heavier lift)
- **Key considerations:**
  - Learning curve vs. capability
  - Cost structure (per execution vs. flat fee)
  - AI integration depth
  - Team collaboration features
  - Data security requirements
- **Recommendation:** Start with Make or n8n for most consultants

> **🔒 AI Data Handling Awareness**
>
> When automating workflows that process client or sensitive data:
> - **Know your data flows:** Understand what data passes through each platform and AI service
> - **Check data retention policies:** Most AI providers retain data temporarily; know the specifics
> - **Client obligations first:** Review client contracts for data handling requirements before automating
> - **When in doubt, anonymize:** Use placeholder data for testing; sanitize sensitive fields
> - **Document your choices:** Record which platforms handle which data types for compliance
>
> This isn't legal advice—consult your organization's policies. The goal is awareness, not fear.

**Segment 3: Decision Matrix for Platform Selection (12 min)**

- **The framework:**

  | Criterion | Weight | Platform A | Platform B | Platform C |
  |-----------|--------|------------|------------|------------|
  | Learning Curve | 20% | | | |
  | AI Integration | 25% | | | |
  | Cost | 15% | | | |
  | Collaboration | 15% | | | |
  | Security | 15% | | | |
  | Scalability | 10% | | | |

- **Scoring guide:** 1-5 for each criterion
- **Live exercise:** Group rates one platform together
- **Your decision:** Use matrix to select YOUR platform

**Segment 4: MCP Introduction + Registry Preview (13 min)**

- **MCP Deep Dive:** Remember "USB-C for AI"?
  - Universal protocol for AI tool connections
  - Servers provide capabilities (file access, database, APIs)
  - Claude and other AI tools connect via MCP
- **MCP Server Registry:**
  - Official servers: filesystem, GitHub, Slack, databases
  - Community servers: Google Drive, Notion, custom tools
  - How to find what you need
- **Live demo:** Browse MCP registry, show popular servers
- **Performance monitoring preview:**
  - Why track from the start
  - Core metrics: execution time, success rate, quality, cost
  - Simple logging approach (Week 2 deep dive)

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 1.1: Platform Research & Decision Matrix (25 minutes)**

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

-----

**Exercise 1.2: MCP Server Registry Exploration (20 minutes)**

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

-----

**Exercise 1.3: Define Performance Metrics (15 minutes)**

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

-----

## **Week 2: Building Your First Workflow**

### **Entry Criteria**

- [ ] Automation platform selected and account created
- [ ] Platform getting started tutorial completed
- [ ] MCP servers identified
- [ ] Performance metrics defined
- [ ] Workflow candidate selected

### **Exit Criteria**

- [ ] First workflow built and functional
- [ ] Basic error handling implemented
- [ ] Performance tracking active from first execution
- [ ] Workflow documented in standard format
- [ ] Successfully processed 3+ test executions

-----

### **Workshop Content (45 minutes)**

**Segment 1: Workflow Design Principles (12 min)**

- **The workflow mindset:**
  - Think in steps, not single prompts
  - Each step should do ONE thing well
  - Plan for failure (what if a step breaks?)
- **Core workflow components:**
  1. **Trigger:** What starts the workflow?
  2. **Data gathering:** What information is needed?
  3. **AI processing:** The prompt/generation step
  4. **Quality check:** Does output meet standards?
  5. **Output:** Where does the result go?
- **Visual mapping:** Flowchart your workflow before building

- **The Micro-Agent Pattern:**
  - **What's actually working in production:**
    - NOT autonomous agents running indefinitely
    - Small, focused agents: 3-20 steps
    - Embedded within larger deterministic workflows
  - **The pattern:**
    ```
    Traditional DAG:     Step A → Step B → Step C → Step D
                         (all deterministic, all predefined)

    Micro-Agent Pattern: [Deterministic] → [AI: 5-10 steps] → [Deterministic]
                         (flexibility where needed, predictability elsewhere)
    ```
  - **Why 3-20 steps?**
    - Bounds the context window
    - Limits scope of failures
    - Easier to debug
    - Research shows agents degrade after 10-20 turns
  - **The 90% reality check:**
    - A 90% success rate sounds good
    - But would you use a web app that crashed 10% of the time?
    - Production means reliability, not impressive demos
  - **For your workflow:** Think "one thing done well"

**Segment 2: Your First Workflow - Live Build (18 min)**

- **Demonstration workflow:** Email → AI Summary → Slack notification
- **Step-by-step construction:**

  1. **Trigger configuration:**
     - Email webhook, scheduled, or manual trigger
     - Understanding trigger data structure

  2. **Data extraction:**
     - Parsing incoming data
     - Variable mapping
     - Handling missing fields

  3. **AI module setup:**
     - Connecting to Claude/OpenAI
     - Passing context and prompt
     - Receiving and parsing response

  4. **Output configuration:**
     - Formatting the response
     - Sending to destination
     - Confirmation handling

- **Live demo:** Build each step in real-time on Make/n8n

**Segment 3: Error Handling Fundamentals (8 min)**

- **What can go wrong:**
  - API rate limits
  - Invalid input data
  - AI generation failures
  - Connection timeouts
- **Basic error handling:**
  - Try/catch patterns in workflows
  - Fallback routes
  - Alert on failure (email/Slack notification)
  - Logging errors for review
- **The 80/20 rule:** Handle the common failures first

**Segment 4: Logging and Monitoring Setup (7 min)**

- **Start logging immediately:**
  - Every execution should be tracked
  - Include: timestamp, input summary, output summary, duration, status
- **Simple logging approaches:**
  - Google Sheets (easiest)
  - Airtable (more structured)
  - Platform built-in logs (varies by platform)
- **Quick setup:** Add logging step to workflow

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 2.1: Build Your First Workflow (35 minutes)**

*Create a functional workflow end-to-end*

1. **Map your workflow visually:**

   ```
   [Trigger] → [Gather Data] → [AI Process] → [Quality Check] → [Output]
   ```

   Document each step:
   - What triggers it?
   - What data is needed?
   - What prompt template to use?
   - What quality criteria to check?
   - Where does output go?

2. **Build in your platform:**

   Step 1: Configure trigger
   - Manual/webhook for testing

   Step 2: Set up AI module
   - Connect your AI provider
   - Insert your Block 1 prompt template
   - Configure response handling

   Step 3: Add output
   - Start simple: send to email or create document

   Step 4: Test with sample data
   - Run 3+ test executions
   - Document results

3. **Document the workflow:**

```markdown
# Workflow: [Name]

## Purpose
[What this workflow does]

## Trigger
- Type: [Manual/Webhook/Schedule/etc.]
- Input: [What data it expects]

## Steps
1. [Step name] - [What it does]
2. [Step name] - [What it does]
3. [Step name] - [What it does]

## AI Processing
- Template: [Link to prompt template from Block 1]
- Model: [Claude/GPT-4/etc.]
- Expected output: [Format description]

## Output
- Destination: [Where results go]
- Format: [How it's delivered]

## Test Results
| Test # | Input Summary | Output Quality | Duration | Notes |
|--------|---------------|----------------|----------|-------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
```

**Deliverable:** Working workflow + `workflow-1-documentation.md`

-----

**Exercise 2.2: Add Error Handling (15 minutes)**

*Make your workflow resilient*

1. Identify failure points in your workflow:
   - What if input data is missing key fields?
   - What if AI API is unavailable?
   - What if output destination fails?

2. Add error handling:

   **For each critical step:**
   - Add error route/exception handler
   - Log the error with context
   - Send alert notification (email/Slack)
   - Graceful failure (don't crash entire workflow)

3. Test error handling:
   - Deliberately trigger a failure
   - Verify error is caught and logged
   - Confirm alert was sent

4. Document error handling:

```markdown
## Error Handling

### Step: [Step Name]
- **Potential failure:** [What could go wrong]
- **Handler:** [What happens on failure]
- **Alert:** [Yes/No - where sent]

### Step: [Step Name]
- **Potential failure:** [What could go wrong]
- **Handler:** [What happens on failure]
- **Alert:** [Yes/No - where sent]
```

**Deliverable:** Error handling added + documentation updated

-----

**Exercise 2.3: Set Up Performance Logging (10 minutes)**

*Track from day one*

1. Add logging step to workflow end:

```
Log Entry:
- Timestamp: [execution time]
- Workflow: [name]
- Trigger: [what started it]
- Input Summary: [brief description]
- Output Summary: [brief description]
- Duration: [seconds/minutes]
- Status: [Success/Partial/Failed]
- Quality Score: [if applicable]
- Cost Estimate: [if known]
- Notes: [any issues]
```

2. Create logging destination:
   - Google Sheet with columns matching log entry
   - Or Airtable base
   - Or platform's built-in logging

3. Run 3 test executions and verify logging works

**Deliverable:** Logging configured + 3 logged executions

**Resources:**
- [Make Error Handling](https://www.make.com/en/help/errors/error-handling)
- [n8n Error Handling](https://docs.n8n.io/flow-logic/error-handling/)
- [Google Sheets API Integration](https://developers.google.com/sheets/api)

-----

## **Week 3: Quality Systems + Template Workflows**

### **Entry Criteria**

- [ ] First workflow built and tested
- [ ] Error handling implemented
- [ ] Logging active
- [ ] 5+ successful workflow executions

### **Exit Criteria**

- [ ] Quality check module integrated into workflow
- [ ] JSON data structures used for workflow data
- [ ] Second workflow built using template pattern
- [ ] Rubric-based quality gate implemented
- [ ] Template versioning strategy established

-----

### **Workshop Content (45 minutes)**

**Segment 1: Quality in Automated Workflows (12 min)**

- **Framing: Quality as Domain Memory**
  - **The Three Pillars (preview of Block 3):**
    1. **Explicit Goals** → Your success criteria
    2. **Progress Records** → Your execution logs
    3. **Operating Procedures** → Your quality system!
  - **Quality systems ARE operating procedures:**
    - Pre-generation checks = input validation procedures
    - Post-generation evaluation = output verification procedures
    - Human review triggers = escalation procedures
  - **Why this matters:**
    - Consistent behavior across all executions
    - Predictable quality without human variance
    - Foundation for autonomous agents (Block 3)

- **The automation quality challenge:**
  - Manual review doesn't scale
  - Inconsistent quality undermines trust
  - Need systematic quality assurance
- **Block 1 foundations applied:**
  - Quality rubrics become automated checks
  - Comparison gates verify style matching
  - LLM-as-judge pattern for self-evaluation
- **Quality gate implementation:**
  - Pre-generation: Input validation
  - Post-generation: Output evaluation
  - Human review: When automated checks fail

**Segment 2: Automated Quality Checks (10 min)**

- **Using AI to check AI:**

  ```
  Step 1: Generate deliverable
  Step 2: Run evaluation prompt
  Step 3: Parse scores
  Step 4: Route based on scores
  ```

- **Evaluation prompt pattern:**

  ```markdown
  Evaluate this [deliverable] against these criteria.
  For each criterion, score 1-5 and provide a brief justification.

  Criteria:
  1. [From your rubric]
  2. [From your rubric]
  3. [From your rubric]

  Output your evaluation as JSON:
  {
    "scores": {
      "criterion_1": {"score": X, "reason": "..."},
      "criterion_2": {"score": X, "reason": "..."}
    },
    "overall_score": X,
    "pass": true/false,
    "improvement_suggestions": ["...", "..."]
  }
  ```

- **Routing logic:**
  - Score ≥ 4: Proceed to output
  - Score 3: Flag for human review
  - Score < 3: Regenerate with improvements

**Segment 3: JSON Data Structures in Workflows (13 min)**

- **Why JSON for workflows:**
  - Structured data between steps
  - Easy parsing and manipulation
  - Standard format across platforms
  - AI generates JSON reliably
- **Common workflow data patterns:**

  ```json
  {
    "workflow_id": "wf-001",
    "execution_timestamp": "2024-12-30T10:30:00Z",
    "input": {
      "client_name": "Acme Corp",
      "project_type": "proposal"
    },
    "processing": {
      "template_used": "proposal-tech-v2",
      "ai_model": "claude-3-opus",
      "tokens_used": 2500
    },
    "output": {
      "status": "success",
      "quality_score": 4.2,
      "deliverable_url": "..."
    }
  }
  ```

- **JSON in AI prompts:**
  - Request JSON output explicitly
  - Provide schema/example
  - Parse and validate in workflow

**Segment 4: Template Workflow Pattern (10 min)**

- **The reusable workflow template:**
  - Generic structure
  - Variables for customization
  - Swap components (different prompts, outputs)
- **Template versioning:**
  - v1.0, v1.1, v2.0 naming
  - Changelog documentation
  - A/B testing workflows
- **Building your second workflow:**
  - Clone workflow 1
  - Replace prompt template
  - Adjust data mappings
  - Same quality/logging infrastructure

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 3.1: Add Quality Check Module (25 minutes)**

*Implement automated quality assurance*

1. Create quality evaluation prompt based on your Block 1 rubric:

```markdown
# Quality Evaluation Prompt

You are evaluating a [deliverable type] for quality.

## Criteria (score each 1-5)

1. **[Criterion 1 from rubric]**
   - 5: [Excellent description]
   - 3: [Adequate description]
   - 1: [Poor/Missing description]

2. **[Criterion 2]**
   - 5: [Description]
   - 3: [Description]
   - 1: [Description]

[Repeat for 3-5 criteria]

## Content to Evaluate

```
{deliverable_content}
```

## Output Format

Respond ONLY with valid JSON:
```json
{
  "scores": {
    "criterion_1_name": {"score": X, "reason": "brief explanation"},
    "criterion_2_name": {"score": X, "reason": "brief explanation"}
  },
  "overall_score": X.X,
  "pass": true/false,
  "suggestions": ["improvement 1", "improvement 2"]
}
```

Pass threshold: overall_score >= 3.5
```

2. Add evaluation step to your workflow:
   - After AI generation, before output
   - Parse JSON response
   - Create routing based on pass/fail

3. Add routing logic:
   - Pass → Continue to output
   - Fail → Log failure, send for review OR regenerate

4. Test with good and bad inputs to verify routing works

**Deliverable:** Quality check module added to workflow + evaluation prompt saved

-----

**Exercise 3.2: Build Second Workflow (Using Template) (25 minutes)**

*Create reusable workflow pattern*

1. Clone your first workflow in the platform

2. Identify what changes for different use case:
   - Different trigger? → Update trigger
   - Different prompt? → Swap prompt template
   - Different output? → Adjust output step
   - Same quality/logging? → Keep as-is

3. Modify for new deliverable type:
   - Use second Block 1 template
   - Adjust data mappings
   - Update quality criteria in evaluation prompt

4. Test with 3+ executions

5. Document both workflows as a "family":

```markdown
# Workflow Template Family: [Name]

## Base Pattern
- Trigger → Data Prep → AI Generation → Quality Check → Output/Route

## Workflow Variants

### Variant 1: [Original Workflow Name]
- **Deliverable:** [What it produces]
- **Template:** [Which Block 1 template]
- **Unique config:** [What's specific to this one]

### Variant 2: [New Workflow Name]
- **Deliverable:** [What it produces]
- **Template:** [Which Block 1 template]
- **Unique config:** [What's specific to this one]

## Shared Components
- Quality evaluation prompt: [Link]
- Logging destination: [Link]
- Error handling pattern: [Description]

## Versioning
- v1.0: Initial implementation
- [Date]: [Changes]
```

**Deliverable:** Second workflow + template family documentation

-----

**Exercise 3.3: JSON Data Structure Design (10 minutes)**

*Standardize workflow data*

1. Design standard data structure for your workflows:

```json
{
  "$schema": "workflow-execution-v1",

  "execution": {
    "id": "unique-execution-id",
    "workflow_name": "string",
    "workflow_version": "1.0",
    "timestamp": "ISO-8601",
    "duration_seconds": 0
  },

  "input": {
    "trigger_type": "manual|webhook|schedule",
    "source": "string",
    "data": {
      // workflow-specific input fields
    }
  },

  "processing": {
    "template_name": "string",
    "template_version": "string",
    "model": "string",
    "tokens_used": 0,
    "cost_estimate": 0.00
  },

  "quality": {
    "evaluation_run": true,
    "overall_score": 0.0,
    "passed": true,
    "criteria_scores": {}
  },

  "output": {
    "status": "success|failed|review_required",
    "destination": "string",
    "deliverable_id": "string"
  },

  "errors": []
}
```

2. Update your logging to use this structure

3. Validate JSON output from your workflows

**Deliverable:** `workflow-data-schema.json`

-----

## **Week 4: Workflow Optimization**

### **Entry Criteria**

- [ ] Two working workflows with quality checks
- [ ] 10+ logged executions across workflows
- [ ] JSON data structures implemented
- [ ] Quality routing functional

### **Exit Criteria**

- [ ] Cost optimization applied to workflows
- [ ] Quality gates refined based on data
- [ ] Performance bottlenecks identified and addressed
- [ ] A/B testing concept understood
- [ ] Workflow efficiency improved by 20%+

-----

### **Workshop Content (45 minutes)**

**Segment 1: Analyzing Workflow Performance (9 min)**

- **Review your execution logs:**
  - Average execution time
  - Success rate
  - Quality score distribution
  - Cost per execution
- **Identify patterns:**
  - Which steps take longest?
  - Where do failures occur?
  - What triggers low quality scores?
- **Live analysis:** Walk through sample execution data

**Segment 2: Cost Optimization Strategies (16 min)**

- **The Context Window Trap:**
  - **Common assumption:** "Bigger context windows = better performance"
  - **The research reality:**
    - "Lost in the Middle" study: Models ignore middle of long inputs
    - Performance degrades as input length increases
    - Complete histories often perform WORSE than curated excerpts
  - **The counterintuitive principle:** More context makes things WORSE, not better.
  - **Why this matters for workflow optimization:**
    - Don't dump entire conversation histories
    - Summarize large inputs before AI processing
    - Pass only what's needed for THIS step
    - Every token competes for attention
  - **Token Reduction = Better Performance AND Lower Cost**

- **Token reduction techniques:**
  - Shorter context windows (pass only what's needed)
  - Summarize large inputs before AI processing
  - Use smaller models for simple tasks
  - Cache repeated operations
- **Platform cost optimization:**
  - Batch executions where possible
  - Avoid unnecessary steps
  - Use conditional logic to skip irrelevant paths
- **Cost tracking implementation:**

  ```json
  {
    "cost_breakdown": {
      "ai_tokens": {"input": 1000, "output": 500, "cost": 0.03},
      "platform_operations": 5,
      "platform_cost": 0.01,
      "total": 0.04
    }
  }
  ```

- **Current Token Pricing Reference (Early 2025):**

  | Model | Input (per 1M tokens) | Output (per 1M tokens) | Best For |
  |-------|----------------------|------------------------|----------|
  | Claude 3.5 Sonnet | ~$3.00 | ~$15.00 | Complex generation, analysis |
  | Claude 3 Haiku | ~$0.25 | ~$1.25 | Simple tasks, classification |
  | GPT-4o | ~$2.50 | ~$10.00 | General purpose |
  | GPT-4o-mini | ~$0.15 | ~$0.60 | High-volume, simple tasks |

  *Prices change frequently—verify current rates at provider websites*

  **Typical consulting workflow costs:**
  - Simple email generation: ~500 tokens → $0.001-0.01
  - Proposal section: ~2,000 input + 1,500 output → $0.01-0.05
  - Complex analysis: ~5,000 input + 3,000 output → $0.05-0.15
  - 100 executions/month: $1-15/month (varies by complexity)

  **The insight:** Token costs are rarely the bottleneck—time savings dwarf AI costs

- **Example:** Reduce 40% token usage with prompt optimization

**Segment 3: Quality Gate Refinement (12 min)**

- **Using data to improve thresholds:**
  - What score actually predicts usable output?
  - Are you over-rejecting good content?
  - Are bad outputs slipping through?
- **Adjusting evaluation criteria:**
  - Weight criteria by importance
  - Add specific checks for common issues
  - Create fast-path for simple cases
- **Human-in-the-loop optimization:**
  - When to require human review
  - Reducing review burden over time
  - Learning from corrections

**Segment 4: Speed Optimization (8 min)**

- **Parallel processing:**
  - Run independent steps simultaneously
  - Reduce total execution time
- **Caching strategies:**
  - Cache `style.json` and reference data
  - Don't re-fetch static content
- **Step elimination:**
  - Are all steps necessary?
  - Can steps be combined?
- **Model selection:**
  - Faster models for simpler tasks
  - Reserve powerful models for complex generation

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 4.1: Performance Analysis (20 minutes)**

*Understand your workflow efficiency*

1. Export your execution logs (10+ executions minimum)

2. Calculate key metrics:

```markdown
# Workflow Performance Analysis

## Execution Metrics

| Metric | Workflow 1 | Workflow 2 | Target |
|--------|------------|------------|--------|
| Avg Execution Time | | | |
| Success Rate | | | |
| Avg Quality Score | | | |
| Human Review Rate | | | |
| Avg Cost/Execution | | | |

## Step-by-Step Timing

### Workflow 1
| Step | Avg Duration | % of Total | Bottleneck? |
|------|--------------|------------|-------------|
| | | | |

## Quality Analysis

| Score Range | Count | % | Outcome |
|-------------|-------|---|---------|
| 4.5-5.0 | | | Direct output |
| 3.5-4.4 | | | Passed with minor issues |
| 2.5-3.4 | | | Required review |
| < 2.5 | | | Regenerated/Failed |

## Cost Analysis
- Total cost for [X] executions: $___
- Average cost per execution: $___
- Projected monthly cost (at current rate): $___

## Issues Identified
1. [Issue description]
2. [Issue description]
```

**Deliverable:** `performance-analysis.md`

-----

**Exercise 4.2: Implement Optimizations (25 minutes)**

*Improve efficiency based on analysis*

1. **Cost optimization (pick 2):**
   - Reduce prompt length by 20%+
   - Use smaller model for quality check step
   - Add caching for repeated data
   - Eliminate unnecessary steps

2. **Speed optimization (pick 1):**
   - Add parallel processing
   - Optimize data fetching
   - Remove bottleneck step

3. **Quality optimization (pick 1):**
   - Refine evaluation thresholds
   - Add specific quality checks
   - Improve regeneration prompt

4. Document changes:

```markdown
# Optimization Changes

## Cost Optimizations
- **Change:** [What you changed]
- **Expected impact:** [X% reduction]
- **Actual result:** [Measure after 5 executions]

## Speed Optimizations
- **Change:** [What you changed]
- **Expected impact:** [X seconds/minutes faster]
- **Actual result:** [Measure after 5 executions]

## Quality Optimizations
- **Change:** [What you changed]
- **Expected impact:** [Better accuracy, fewer reviews]
- **Actual result:** [Measure after 5 executions]
```

5. Run 5+ test executions to measure improvement

**Deliverable:** Optimized workflows + optimization documentation

-----

**Exercise 4.3: Before/After Comparison (15 minutes)**

*Quantify improvement*

1. Compare pre and post optimization metrics:

```markdown
# Optimization Results

## Before vs. After

| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| Avg Execution Time | | | X% faster |
| Avg Cost/Execution | | | X% cheaper |
| Success Rate | | | X% better |
| Quality Score | | | X points |
| Human Review Rate | | | X% reduction |

## ROI Calculation

### Time Savings
- Per execution: ___ minutes saved
- Monthly (X executions): ___ hours saved
- Annual projection: ___ hours saved

### Cost Savings
- Per execution: $___ saved
- Monthly: $___ saved
- Annual projection: $___ saved

### Quality Improvement
- [Describe quality gains]

## Lessons Learned
1. [Key learning]
2. [Key learning]
```

**Deliverable:** `optimization-results.md`

-----

**Exercise 4.4: Workflow Exchange (Optional - 20 minutes)**

*Learn from peers by testing each other's workflows*

**If you have a learning partner:**

1. Exchange workflow documentation with partner
2. Each person attempts to run the other's workflow:
   - Follow their documentation
   - Note any gaps or confusion
   - Document results

3. Provide feedback:
   - What was clear
   - What was confusing
   - Suggestions for improvement

4. Discuss findings together

**Deliverable:** Peer feedback notes (shared with partner)

**Benefits:**
- Reveals documentation gaps
- Exposes assumptions
- Builds team knowledge
- Prepares for team rollout

-----

## **Week 5: MCP Integration Basics**

### **Entry Criteria**

- [ ] Two optimized workflows running
- [ ] Claude Desktop installed
- [ ] MCP servers identified (from Week 1)
- [ ] Understanding of workflow data flow

### **Exit Criteria**

- [ ] MCP configured in Claude Desktop
- [ ] At least one MCP server connected and functional
- [ ] Workflow integrated with MCP capability
- [ ] MCP security considerations understood
- [ ] GitHub MCP server working

-----

### **Workshop Content (45 minutes)**

**Segment 1: MCP Architecture Deep Dive (12 min)**

- **How MCP works:**

  ```
  Claude Desktop ← MCP Protocol → MCP Server → External Tool
       ↓                                            ↓
    Your Prompts                              Files, APIs, Data
  ```

- **Key concepts:**
  - **Host:** Claude Desktop (the AI interface)
  - **Server:** Bridge to external capabilities
  - **Tools:** Specific actions a server provides
  - **Resources:** Data sources a server exposes
- **Security model:**
  - Servers run locally (your machine)
  - No data sent to third parties (unless server does)
  - You control which servers are active
  - Permission prompts for sensitive operations

**Segment 2: Setting Up Your First MCP Server (15 min)**

- **Claude Desktop configuration:**
  - Location: `~/Library/Application Support/Claude/claude_desktop_config.json` (Mac)
  - Or: `%APPDATA%\Claude\claude_desktop_config.json` (Windows)

  ```json
  {
    "mcpServers": {
      "filesystem": {
        "command": "npx",
        "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/allowed/directory"]
      }
    }
  }
  ```

- **Live demo:** Configure filesystem server
- **Testing the connection:**
  - Restart Claude Desktop
  - Verify server appears in tools
  - Test a simple operation

**Segment 3: GitHub MCP Server Setup (10 min)**

- **Why GitHub MCP:**
  - Direct access to your prompt library
  - Read templates without copy/paste
  - Create/update files automatically
  - Version control awareness
- **Configuration:**

  ```json
  {
    "mcpServers": {
      "github": {
        "command": "npx",
        "args": ["-y", "@modelcontextprotocol/server-github"],
        "env": {
          "GITHUB_PERSONAL_ACCESS_TOKEN": "your-token-here"
        }
      }
    }
  }
  ```

- **Token creation:** GitHub → Settings → Developer Settings → Personal Access Tokens
- **Required scopes:** repo, read:user

**Segment 4: MCP in Workflows (8 min)**

- **Connecting the dots:**
  - Claude with MCP can access your templates
  - Workflow can trigger Claude operations
  - End-to-end: Trigger → Claude+MCP → Quality Check → Output
- **Integration patterns:**
  - Claude generates using GitHub templates directly
  - Output saved back to repository
  - Automatic version tracking
- **Next week:** Full integration patterns

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 5.1: Configure Claude Desktop MCP (25 minutes)**

*Set up MCP foundation*

1. **Locate Claude Desktop config file:**
   - Mac: `~/Library/Application Support/Claude/claude_desktop_config.json`
   - Windows: `%APPDATA%\Claude\claude_desktop_config.json`
   - Create file if it doesn't exist

2. **Configure filesystem server:**

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/prompts/folder"]
    }
  }
}
```

3. **Restart Claude Desktop**

4. **Test filesystem access:**
   - Ask Claude: "What files are in my prompts directory?"
   - Ask Claude: "Read my `style.json` file"
   - Verify it can access your Block 1 content

5. **Document configuration:**

```markdown
# MCP Configuration

## Filesystem Server
- **Status:** Working/Not Working
- **Allowed Directory:** [path]
- **Test Result:** [What worked/didn't]

## Capabilities Confirmed
- [ ] Can list files in directory
- [ ] Can read file contents
- [ ] Can create new files (if enabled)
```

**Deliverable:** Working MCP config + `mcp-setup.md` documentation

-----

**Exercise 5.2: Configure GitHub MCP Server (20 minutes)**

*Connect your prompt library*

1. **Create GitHub Personal Access Token:**
   - Go to GitHub → Settings → Developer Settings → Personal Access Tokens → Tokens (classic)
   - Generate new token with scopes: `repo`, `read:user`
   - Copy token immediately (won't be shown again)

2. **Add GitHub server to config:**

```json
{
  "mcpServers": {
    "filesystem": {
      // ... existing config
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_your_token_here"
      }
    }
  }
}
```

3. **Restart Claude Desktop**

4. **Test GitHub access:**
   - Ask Claude: "List the repositories I have access to"
   - Ask Claude: "Show me the README from my [repo-name] repository"
   - Ask Claude: "Read my proposal template from [repo]/templates/proposal.md"

5. **Security considerations:**
   - Token stored locally only
   - Consider using environment variable for token
   - Review repository access scope

**Deliverable:** GitHub MCP working + test results documented

-----

**Exercise 5.3: MCP-Powered Generation Test (15 minutes)**

*Use MCP to enhance AI generation*

1. **Create a prompt that uses MCP:**

```markdown
# Test: MCP-Powered Proposal Generation

## Prompt to Claude (with MCP active)

First, read my style.json from my GitHub repository at [repo-name]/resources/style.json.

Then, read my proposal template from [repo-name]/templates/proposal-template.md.

Using the style guide and template structure, create a proposal for:
- Client: Test Company Inc.
- Project: Digital Transformation Assessment
- Timeline: 3 months
- Budget: $150,000

Follow the template structure exactly and apply the style guide throughout.
```

2. **Execute in Claude Desktop:**
   - Verify Claude reads files via MCP
   - Check output matches `style.json` guidelines
   - Verify template structure is followed

3. **Compare with manual approach:**
   - Time to produce output
   - Quality of result
   - Ease of process

4. **Document results:**

```markdown
# MCP-Powered Generation Test

## Process
1. Claude read style.json via GitHub MCP
2. Claude read template via GitHub MCP
3. Generated proposal using both

## Results
- **Time:** [How long]
- **Quality:** [Assessment]
- **Style Adherence:** [Did it follow style.json?]
- **Template Structure:** [Did it follow template?]

## Comparison to Manual
- Manual copy/paste approach: ___ minutes
- MCP approach: ___ minutes
- Time saved: ___ minutes

## Observations
- [What worked well]
- [What could be better]
```

**Deliverable:** MCP test documentation + sample output

-----

## **Week 6: Integration Patterns**

### **Entry Criteria**

- [ ] MCP configured and working
- [ ] GitHub MCP connected to prompt library
- [ ] Two optimized workflows
- [ ] Understanding of quality gates

### **Exit Criteria**

- [ ] Workflow integrated with MCP capabilities
- [ ] Multi-step integration pattern implemented
- [ ] Human-in-the-loop integration designed
- [ ] Third workflow created with full integration
- [ ] Integration architecture documented

-----

### **Workshop Content (45 minutes)**

**Segment 1: Integration Architecture Overview (10 min)**

- **The integration landscape:**

  ```
  Triggers → Workflow Platform → AI + MCP → Quality System → Outputs
     ↑                              ↓
  External    ←──── Feedback ←─── Human Review
  Systems
  ```

- **Integration layers:**
  1. **Data layer:** Where information comes from
  2. **Processing layer:** How AI transforms it
  3. **Quality layer:** How we verify quality
  4. **Output layer:** Where results go
  5. **Feedback layer:** How we learn and improve

- **Tool ecosystem:**
  - Automation platforms (Make, n8n)
  - AI providers (Claude, OpenAI)
  - MCP servers (filesystem, GitHub, custom)
  - Output destinations (Docs, Sheets, Slack, email)

**Segment 2: Advanced Integration Patterns (15 min)**

- **Pattern 1: Sequential Pipeline**
  ```
  Trigger → Gather → Generate → Evaluate → Route → Output
  ```
  - Each step depends on previous
  - Clear data flow
  - Easy to debug

- **Pattern 2: Parallel Processing**
  ```
  Trigger → [Generate A] ──┐
         → [Generate B] ──┼→ Merge → Evaluate → Output
         → [Generate C] ──┘
  ```
  - Multiple generations simultaneously
  - Compare/combine outputs
  - Faster for complex deliverables

- **Pattern 3: Iterative Refinement**
  ```
  Generate → Evaluate → (Pass?) → Output
                ↓ (Fail)
             Refine → Re-generate → Evaluate...
  ```
  - Auto-improvement loop
  - Max iteration limit
  - Escalation on repeated failure

- **Pattern 4: Human-in-the-Loop**
  ```
  Generate → Evaluate → (Review Needed?) → Queue for Human
                              ↓ (Pass)
                           Output
  Human Review → Approve/Edit → Learn from Feedback
  ```
  - Systematic review process
  - Feedback captured for improvement
  - Gradual automation increase

**Segment 3: Building Integrated Workflows (12 min)**

- **Connecting MCP to automation platforms:**
  - Approach 1: Claude API with MCP context
  - Approach 2: Pre-fetch via MCP, pass to workflow
  - Approach 3: Hybrid (some MCP, some workflow)

- **Live demo:** Build integrated workflow
  - Trigger from form submission
  - Gather data + fetch template via MCP
  - Generate with AI
  - Quality check
  - Route based on score
  - Output to Google Doc + notify via Slack

**Segment 4: Documentation and Handoff (8 min)**

- **Integration documentation requirements:**
  - Architecture diagram
  - Data flow description
  - Component dependencies
  - Configuration details
  - Troubleshooting guide

- **Team handoff considerations:**
  - Access requirements (API keys, permissions)
  - Training needed
  - Support plan

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 6.1: Build Integrated Workflow (30 minutes)**

*Create a fully integrated workflow*

1. **Design integrated workflow:**

```markdown
# Integrated Workflow: [Name]

## Architecture
```
[Trigger] → [Data Gather] → [MCP: Fetch Template] → [AI: Generate]
                                                          ↓
[Output: Doc] ← [Route] ← [Quality Check] ← [Evaluate]
      ↓              ↓
  [Notify]     [Human Review Queue]
```

## Components

### Trigger
- Type: [Form/Email/Webhook/Schedule]
- Source: [Where it comes from]

### Data Sources
- Input data: [From trigger]
- Template: [Via MCP from GitHub]
- Style guide: [Via MCP from GitHub]

### AI Processing
- Model: [Claude/GPT]
- Template: [Which template]
- MCP servers: [Which MCP servers are used]

### Quality System
- Evaluation criteria: [Link to rubric]
- Pass threshold: [Score]
- Review trigger: [Conditions]

### Outputs
- Primary: [Where main output goes]
- Notification: [How stakeholders are alerted]
- Logging: [Where execution is logged]
```

2. **Build in your platform:**
   - Configure all components
   - Connect MCP-fetched templates
   - Set up quality routing
   - Configure outputs

3. **Test end-to-end:**
   - Run 3+ complete executions
   - Test pass scenario
   - Test review scenario
   - Verify all outputs work

**Deliverable:** Third working workflow + architecture documentation

-----

**Exercise 6.2: Human Review System (20 minutes)**

*Design systematic human oversight*

1. **Create review queue:**
   - Where flagged items go (Airtable, Trello, email)
   - What information is included
   - Priority/urgency indication

2. **Design review interface:**

```markdown
# Review Queue Item Template

## Execution Details
- Workflow: [Name]
- Executed: [Timestamp]
- Trigger: [Source]

## Generated Content
[Content that needs review]

## Quality Scores
| Criterion | Score | Reason |
|-----------|-------|--------|
| | | |

## Overall: [X.X/5] - REVIEW NEEDED because [reason]

## Reviewer Actions
- [ ] Approve as-is
- [ ] Approve with edits
- [ ] Reject - Regenerate
- [ ] Reject - Manual creation needed

## Feedback for Improvement
[Space for notes on how to improve automation]
```

3. **Implement feedback loop:**
   - How do edits get incorporated?
   - How do rejections inform prompt improvements?
   - Track patterns in reviews

**Deliverable:** Review queue setup + feedback process documentation

-----

**Exercise 6.3: Integration Architecture Document (10 minutes)**

*Create comprehensive documentation*

1. **Create architecture overview:**

```markdown
# AI Workflow Integration Architecture

## System Diagram

```
[Visual representation of your integrated system]
```

## Components

### Automation Platform
- Platform: [Name]
- Workflows: [List]
- Connections: [External systems]

### AI Layer
- Provider: [Claude/OpenAI]
- Models used: [List]
- MCP servers: [List]

### Data Sources
- GitHub: [Repository for templates]
- [Other sources]

### Outputs
- [List all output destinations]

## Data Flows

### Flow 1: [Workflow Name]
Input → [Step] → [Step] → Output

### Flow 2: [Workflow Name]
Input → [Step] → [Step] → Output

## Configuration Requirements
- API keys needed: [List]
- MCP servers to configure: [List]
- Platform connections: [List]

## Security Considerations
- [Data handling]
- [Access controls]
- [Token management]

## Monitoring
- Logs location: [Where]
- Alerts: [When triggered]
- Dashboard: [If applicable]
```

**Deliverable:** `integration-architecture.md`

-----

## **Week 7: Block 2 Capstone Preparation**

### **Entry Criteria**

- [ ] 3 working, integrated workflows
- [ ] MCP configured and functional
- [ ] Quality systems implemented
- [ ] 20+ logged workflow executions
- [ ] Performance metrics tracked

### **Exit Criteria**

- [ ] All capstone components complete
- [ ] Impact measurement documented with real data
- [ ] Workflows polished and documented
- [ ] Ready for Block 2 evaluation
- [ ] Block 3 preview understood

-----

### **Workshop Content (45 minutes)**

**Segment 1: Capstone Requirements Review (10 min)**

- **Block 2 Capstone: AI Workflow Toolkit**

  Required components:
  1. **3 Workflow Templates** - Documented, tested, integrated
  2. **Quality System** - Evaluation prompts, rubrics, gates
  3. **MCP Demonstration** - Functional integration
  4. **Performance Documentation** - Metrics, logs, analysis
  5. **Impact Measurement** - Real data, ROI calculation

- **Evaluation criteria (8 dimensions):**
  1. Workflow Design
  2. Integration Quality
  3. MCP Implementation
  4. Quality Systems
  5. Performance Monitoring
  6. Documentation Completeness
  7. Practical Application
  8. Overall Toolkit Value

**Segment 2: Impact Measurement with Real Data (15 min)**

- **Collecting actual metrics:**
  - Pull from execution logs
  - Compare to Block 1 baseline
  - Calculate real time savings

- **Impact calculation framework:**

  ```markdown
  ## Time Savings (Actual)
  - Manual process (Block 1): X minutes/execution
  - Automated (Block 2): Y minutes/execution
  - Savings per execution: X - Y = Z minutes
  - Total executions (Block 2): N
  - Total time saved: Z × N = hours

  ## Quality Improvement (Actual)
  - Average quality score: X.X/5
  - % requiring revision: X%
  - Comparison to manual baseline

  ## Cost Analysis (Actual)
  - AI costs (Block 2): $X
  - Platform costs: $X
  - Total automation cost: $X
  - Value of time saved: hours × rate = $X
  - Net ROI: Value - Costs = $X
  ```

- **Projecting annual impact:**
  - Based on actual usage rates
  - Accounting for team scale potential

**Segment 3: Portfolio Preparation (12 min)**

- **Workflow documentation checklist:**
  - [ ] Architecture diagram
  - [ ] Step-by-step configuration guide
  - [ ] Integration dependencies
  - [ ] Troubleshooting guide
  - [ ] Performance benchmarks
  - [ ] Example executions

- **Quality system documentation:**
  - [ ] Evaluation prompts (all)
  - [ ] Rubrics for each workflow
  - [ ] Quality routing logic
  - [ ] Human review process

- **MCP documentation:**
  - [ ] Configuration file
  - [ ] Server setup instructions
  - [ ] Usage examples
  - [ ] Security notes

**Segment 4: Block 3 Preview (8 min)**

- **Block 3: AI Automation Architecture**
  - Building reliable AI agents
  - Multi-agent orchestration
  - Production deployment
  - Team scaling

- **Prerequisites for Block 3:**
  - Block 2 completion
  - Strong workflow foundation
  - MCP proficiency
  - Quality system thinking

- **Enrollment and scheduling info**

-----

### **Self-Paced Exercises (60 minutes total)**

**Exercise 7.1: Finalize All Workflows (Variable - as needed)**

*Complete and polish your workflow toolkit*

1. **Review each workflow against requirements:**
   - [ ] Fully functional end-to-end
   - [ ] Error handling implemented
   - [ ] Quality check integrated
   - [ ] Logging active
   - [ ] MCP server (at least one)
   - [ ] Documentation complete

2. **Final testing:**
   - Run 3+ executions per workflow
   - Test error scenarios
   - Verify quality routing
   - Check all outputs

3. **Polish documentation:**
   - Clear architecture diagrams
   - Step-by-step setup guides
   - Troubleshooting tips
   - Version history

**Deliverable:** 3 finalized workflows with complete documentation

-----

**Exercise 7.2: Calculate Real Impact (25 minutes)**

*Document actual business value*

1. **Export all execution data:**
   - Timestamps, durations, costs, quality scores
   - Success/failure rates
   - Human review rates

2. **Calculate actual metrics:**

```markdown
# Block 2 Impact Report

## Execution Summary
- Total workflow executions: [N]
- Date range: [Start] to [End]
- Workflows in production: [3]

## Time Savings (Actual Data)

| Workflow | Manual Time | Automated Time | Savings/Exec | Executions | Total Saved |
|----------|-------------|----------------|--------------|------------|-------------|
| WF1 | X min | Y min | Z min | N | hours |
| WF2 | | | | | |
| WF3 | | | | | |
| **Total** | | | | | **X hours** |

## Quality Metrics (Actual Data)

| Workflow | Avg Quality Score | Pass Rate | Review Rate | Revision Rate |
|----------|-------------------|-----------|-------------|---------------|
| WF1 | X.X/5 | X% | X% | X% |
| WF2 | | | | |
| WF3 | | | | |

## Cost Analysis (Actual Data)

| Category | Amount |
|----------|--------|
| AI API costs (total) | $X |
| Platform costs | $X |
| **Total Automation Cost** | $X |
| | |
| Time saved (hours) | X |
| Value @ $150/hr | $X |
| **Net Value** | $X |
| **ROI** | X% |

## Annual Projection

Based on actual usage rate of [X] executions/week:
- Annual executions: [N]
- Annual time saved: [X] hours
- Annual value: $[X]
- Annual cost: $[X]
- **Annual Net ROI: $[X]**

## Team Scale Potential

If [X] team members used these workflows:
- Team time saved: [X] hours/year
- Team value: $[X]/year
```

**Deliverable:** `block-2-impact-report.md` with real data

-----

**Exercise 7.3: Create Capstone Summary (10 minutes)**

*Prepare submission package*

1. **Create capstone summary:**

```markdown
# Block 2 Capstone Summary
## AI Workflow Toolkit

### Participant
- Name: [Your name]
- Completed: [Date]

### Toolkit Contents

#### Workflows (3)
1. **[Workflow 1 Name]**
   - Purpose: [Description]
   - Integration: [What it connects]
   - Location: [Link to documentation]

2. **[Workflow 2 Name]**
   - Purpose: [Description]
   - Integration: [What it connects]
   - Location: [Link to documentation]

3. **[Workflow 3 Name]**
   - Purpose: [Description]
   - Integration: [What it connects]
   - Location: [Link to documentation]

#### Quality System
- Evaluation prompts: [Count]
- Quality rubrics: [Count]
- Quality gate logic: [Description]
- Location: [Link]

#### MCP Implementation
- Servers configured: [List]
- Integration points: [Description]
- Documentation: [Link]

#### Performance Monitoring
- Logging system: [Description]
- Metrics tracked: [List]
- Dashboard/Reports: [Link]

### Impact Summary
- **Time saved (actual):** [X] hours over Block 2
- **Quality improvement:** [Description]
- **ROI achieved:** [X%]
- **Annual projection:** $[X] value

### Key Achievements
1. [Achievement 1]
2. [Achievement 2]
3. [Achievement 3]

### Lessons Learned
1. [Learning 1]
2. [Learning 2]

### Block 3 Readiness
- [How this prepares you for Block 3]
- [What you want to build in Block 3]

### Repository
[Link to GitHub repository with all materials]
```

**Deliverable:** `block-2-capstone-summary.md`

-----

## **Week 8: Block 2 Capstone Evaluation**

### **Format**

This week is **self-paced** - no live workshop. Complete final submissions and self-evaluation.

### **Requirements**

**Submit by end of week:**

1. GitHub repository with all workflow documentation
2. Capstone summary document
3. Impact report with actual data
4. Self-evaluation (optional but encouraged)

### **Self-Evaluation Process (Optional - 30 minutes)**

1. Review the Block 2 Capstone Rubric (see Appendix I)
2. Score yourself on each of 8 criteria (1-5 points each):

   - Workflow Design
   - Integration Quality
   - MCP Implementation
   - Quality Systems
   - Performance Monitoring
   - Documentation Completeness
   - Practical Application
   - Overall Toolkit Value

3. Calculate total score (out of 40)
4. Identify strengths, areas for improvement, key learnings

**Deliverable:** Self-evaluation document

-----

### **Transition to Block 3**

**Preview of Block 3: AI Automation Architecture**

- Building reliable, production-ready AI agents
- Multi-agent orchestration patterns
- Performance optimization at scale
- Team deployment and governance
- Enterprise integration patterns

**Block 3 takes you from:**
Workflow → Agent → Orchestrated System

**Enrollment:** Opens upon Block 2 certification
**Block 3 starts:** 1-2 weeks after Block 2 evaluation

-----

# **APPENDICES**

## **Appendix J: Block 2 Capstone Rubric**

```markdown
# Block 2 Capstone Evaluation Rubric
## AI Workflow Engineering - AI Workflow Toolkit

**Total Points: 40 (8 criteria × 5 points each)**

---

## Criterion 1: Workflow Design (5 points)

**Evaluates:** Architecture, efficiency, reliability, error handling

| Score | Description |
|-------|-------------|
| **5 - Excellent** | 3+ workflows with elegant architecture. Efficient step design. Comprehensive error handling. Parallel processing where appropriate. Clear triggering logic. Production-ready design. |
| **4 - Good** | 3 well-designed workflows. Good architecture. Solid error handling. Efficient in most areas. Minor design improvements possible. |
| **3 - Adequate** | 3 functional workflows. Basic architecture. Some error handling. Room for efficiency improvements. Mostly reliable. |
| **2 - Poor** | Fewer than 3 workflows or poorly designed. Limited error handling. Inefficient execution. Unreliable in places. |
| **1 - Missing** | Incomplete workflows or non-functional. No error handling. Poor design. |

**Weight:** 12.5%

---

## Criterion 2: Integration Quality (5 points)

**Evaluates:** Tool connections, data flow, seamless operation

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Seamless integration across multiple tools. Clean data transformations. No manual intervention needed. Robust connections. Handles edge cases gracefully. |
| **4 - Good** | Good integration with most tools working smoothly. Minor data handling issues. Occasional manual steps. Generally reliable connections. |
| **3 - Adequate** | Basic integrations working. Some data transformation issues. Manual intervention sometimes needed. Connections work but fragile. |
| **2 - Poor** | Limited integration. Frequent data issues. Regular manual intervention. Unreliable connections. |
| **1 - Missing** | No meaningful integration. Disconnected components. Constant failures. |

**Weight:** 12.5%

---

## Criterion 3: MCP Implementation (5 points)

**Evaluates:** MCP configuration, server usage, practical application

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Multiple MCP servers configured and actively used. GitHub integration with templates. Demonstrated practical value. Clear documentation. Security best practices followed. |
| **4 - Good** | MCP properly configured with 1-2 servers. Good practical use. Documentation present. Reasonable security. |
| **3 - Adequate** | Basic MCP configuration. At least one server working. Limited practical application. Basic documentation. |
| **2 - Poor** | MCP attempted but limited success. Configuration issues. Minimal practical use. Poor documentation. |
| **1 - Missing** | No MCP implementation or non-functional. |

**Weight:** 12.5%

---

## Criterion 4: Quality Systems (5 points)

**Evaluates:** Automated evaluation, quality gates, routing logic, human review

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Comprehensive quality system. Automated evaluation with rubric-based scoring. Intelligent routing logic. Effective human review process. Feedback loop for improvement. Demonstrable quality gains. |
| **4 - Good** | Good quality system. Automated evaluation working. Clear routing logic. Human review when needed. Quality improvements visible. |
| **3 - Adequate** | Basic quality checks implemented. Some routing logic. Human review process exists. Limited quality measurement. |
| **2 - Poor** | Minimal quality checking. Poor or missing routing. No systematic review process. Quality inconsistent. |
| **1 - Missing** | No quality system implemented. No evaluation. No routing. |

**Weight:** 12.5%

---

## Criterion 5: Performance Monitoring (5 points)

**Evaluates:** Logging, metrics tracking, analysis, optimization

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Comprehensive logging of all executions. Key metrics tracked (time, cost, quality, success rate). Regular analysis performed. Evidence of optimization based on data. Clear performance trends. |
| **4 - Good** | Good logging coverage. Most key metrics tracked. Some analysis done. Optimization attempted based on data. |
| **3 - Adequate** | Basic logging in place. Some metrics tracked. Limited analysis. Some awareness of performance. |
| **2 - Poor** | Minimal logging. Few metrics. No analysis. No optimization. |
| **1 - Missing** | No logging or performance tracking. |

**Weight:** 12.5%

---

## Criterion 6: Documentation Completeness (5 points)

**Evaluates:** Architecture docs, setup guides, troubleshooting, examples

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Comprehensive documentation for all workflows. Clear architecture diagrams. Detailed setup guides. Troubleshooting tips. Working examples. Someone else could set up from docs alone. |
| **4 - Good** | Good documentation coverage. Architecture documented. Setup instructions present. Some troubleshooting info. Examples included. |
| **3 - Adequate** | Basic documentation. Architecture partially documented. Setup instructions exist but incomplete. Limited troubleshooting. Few examples. |
| **2 - Poor** | Minimal documentation. Missing architecture info. Incomplete setup. No troubleshooting. No examples. |
| **1 - Missing** | No documentation or unusable. |

**Weight:** 12.5%

---

## Criterion 7: Practical Application (5 points)

**Evaluates:** Real-world relevance, actual usage, business value

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Workflows address real consulting needs. Evidence of actual use (20+ executions). Measurable time savings. Clear business value demonstrated. Team adoption potential high. |
| **4 - Good** | Workflows relevant to real work. Good usage evidence. Some time savings. Business value present. Could be adopted by team. |
| **3 - Adequate** | Workflows somewhat relevant. Limited actual usage. Theoretical value present. Adoption would require work. |
| **2 - Poor** | Workflows not clearly relevant. Minimal usage. Questionable value. Not ready for team use. |
| **1 - Missing** | No practical application demonstrated. |

**Weight:** 12.5%

---

## Criterion 8: Overall Toolkit Value (5 points)

**Evaluates:** Completeness, coherence, impact, professionalism

| Score | Description |
|-------|-------------|
| **5 - Excellent** | Complete toolkit with all components. Coherent system that works together. Significant demonstrated impact. Professional presentation. Exceeds Block 2 requirements. Ready for Block 3. |
| **4 - Good** | All requirements met. Components work together. Good impact shown. Professional quality. Block 3 ready. |
| **3 - Adequate** | Most requirements met. Components function. Some impact shown. Acceptable quality. Can proceed to Block 3 with review. |
| **2 - Poor** | Requirements partially met. Components don't integrate well. Limited impact. Quality issues. Block 3 readiness questionable. |
| **1 - Missing** | Major requirements missing. Non-functional system. No impact. Not ready for Block 3. |

**Weight:** 12.5%

---

## Scoring Summary

| Criterion | Raw Score (1-5) | Weighted Score (12.5%) |
|-----------|-----------------|------------------------|
| 1. Workflow Design | | |
| 2. Integration Quality | | |
| 3. MCP Implementation | | |
| 4. Quality Systems | | |
| 5. Performance Monitoring | | |
| 6. Documentation Completeness | | |
| 7. Practical Application | | |
| 8. Overall Toolkit Value | | |
| **TOTAL** | **/40** | **/100%** |

---

## Performance Levels

| Score Range | Percentage | Level | Description |
|-------------|------------|-------|-------------|
| 34-40 points | 85-100% | **Excellent** | Exceptional work. Fully prepared for Block 3. Toolkit ready for team use. |
| 28-33 points | 70-84% | **Good** | Strong work. Ready for Block 3. Minor enhancements would elevate to excellent. |
| 22-27 points | 55-69% | **Adequate** | Acceptable work. Can proceed to Block 3 with commitment to address gaps. |
| 16-21 points | 40-54% | **Needs Improvement** | Significant gaps. Additional work needed before Block 3. |
| 0-15 points | 0-39% | **Incomplete** | Major elements missing. Not ready for Block 3. |

---

## Self-Evaluation Questions

1. **Are my workflows production-ready?**
   - Would I trust them to run without supervision?
   - Have I tested edge cases and errors?
   - Is monitoring in place?

2. **Does my quality system actually improve output?**
   - Can I show before/after quality metrics?
   - Is human review systematic and efficient?
   - Do I learn from failures?

3. **Is MCP adding real value?**
   - Am I using it for practical purposes?
   - Is it integrated into workflows?
   - Could I demonstrate it to my team?

4. **What's my actual impact?**
   - Real time saved (not theoretical)
   - Real quality improvement
   - Real cost analysis

5. **What would I do differently?**
   - In workflow design?
   - In tool selection?
   - In quality systems?
   - What lessons will I carry to Block 3?
```

-----

## **Appendix K: Platform Decision Matrix Template**

```markdown
# Automation Platform Decision Matrix

## Candidates
1. [Platform 1]
2. [Platform 2]
3. [Platform 3]

## Scoring (1-5 scale, 5 = best)

| Criterion | Weight | [Platform 1] | [Platform 2] | [Platform 3] |
|-----------|--------|--------------|--------------|--------------|
| **Learning Curve** | 20% | | | |
| 5 = Very easy to learn | | | | |
| 1 = Very difficult | | | | |
| | | | | |
| **AI Integration** | 25% | | | |
| 5 = Native AI, multiple models | | | | |
| 1 = No AI integration | | | | |
| | | | | |
| **Cost** | 15% | | | |
| 5 = Free/very cheap for my needs | | | | |
| 1 = Expensive | | | | |
| | | | | |
| **Collaboration** | 15% | | | |
| 5 = Great team features | | | | |
| 1 = Single user only | | | | |
| | | | | |
| **Security** | 15% | | | |
| 5 = Enterprise-grade | | | | |
| 1 = Minimal security | | | | |
| | | | | |
| **Scalability** | 10% | | | |
| 5 = Unlimited scale | | | | |
| 1 = Very limited | | | | |

## Weighted Calculation

Platform 1: (LC × 0.20) + (AI × 0.25) + (C × 0.15) + (Col × 0.15) + (S × 0.15) + (Sc × 0.10) = ___

Platform 2: = ___

Platform 3: = ___

## Additional Considerations

| Factor | [Platform 1] | [Platform 2] | [Platform 3] |
|--------|--------------|--------------|--------------|
| Free tier limitations | | | |
| Community/support | | | |
| MCP compatibility | | | |
| Existing tool integrations | | | |

## Decision

**Selected Platform:** [Name]

**Rationale:**
[2-3 sentences explaining why this is the best choice for your needs]

**Next Steps:**
1. Create account
2. Complete getting started tutorial
3. Build first test workflow
```

-----

## **Appendix L: Workflow Documentation Template**

```markdown
# Workflow: [Name]

## Metadata
- **Version:** 1.0
- **Created:** YYYY-MM-DD
- **Last Updated:** YYYY-MM-DD
- **Author:** [Name]
- **Status:** [Development/Testing/Production]

---

## Overview

**Purpose:** [What this workflow does - 2-3 sentences]

**Business Value:** [Why this matters - time saved, quality improved, etc.]

**Prerequisites:**
- [Required access/accounts]
- [Required configurations]
- [Required data]

---

## Architecture

```
[ASCII or Mermaid diagram of workflow]

Example:
Trigger → Data Prep → AI Generate → Quality Check → Route
                                           ↓           ↓
                                        Output    Human Review
```

---

## Trigger Configuration

**Trigger Type:** [Manual/Webhook/Schedule/Email/etc.]

**Trigger Details:**
- [Configuration specifics]
- [Expected input format]

**Input Schema:**
```json
{
  "field1": "description",
  "field2": "description"
}
```

---

## Steps

### Step 1: [Name]
- **Purpose:** [What this step does]
- **Module:** [Platform module used]
- **Configuration:**
  - [Key setting 1]
  - [Key setting 2]
- **Input:** [What it receives]
- **Output:** [What it produces]

### Step 2: [Name]
[Repeat structure]

### Step 3: [Name]
[Repeat structure]

---

## AI Processing

**Model:** [Claude/GPT-4/etc.]

**Prompt Template:** [Link to template file or include inline]

**MCP Integration:** [If applicable - which servers, how used]

**Expected Output Format:**
```json
{
  // Expected JSON structure
}
```

---

## Quality System

**Evaluation Prompt:** [Link or inline]

**Scoring Criteria:**
| Criterion | Weight | Threshold |
|-----------|--------|-----------|
| | | |

**Routing Logic:**
- Score ≥ X.X → [Action]
- Score X.X - Y.Y → [Action]
- Score < Y.Y → [Action]

---

## Error Handling

| Error Type | Detection | Response | Alert |
|------------|-----------|----------|-------|
| [Type] | [How detected] | [What happens] | [Yes/No] |

**Retry Policy:** [Number of retries, backoff strategy]

**Escalation:** [What happens after max retries]

---

## Outputs

**Primary Output:**
- Destination: [Where]
- Format: [How]

**Notifications:**
- [Who gets notified]
- [When]
- [How]

**Logging:**
- Location: [Where logs go]
- Fields: [What's logged]

---

## Performance Metrics

| Metric | Current Average | Target |
|--------|-----------------|--------|
| Execution Time | | |
| Success Rate | | |
| Quality Score | | |
| Cost/Execution | | |

---

## Setup Instructions

### Prerequisites
1. [Account/access requirement]
2. [Configuration requirement]

### Step-by-Step Setup
1. [First step]
2. [Second step]
3. [Third step]
...

### Testing
1. [How to test]
2. [What to verify]
3. [Expected results]

---

## Troubleshooting

### Common Issue 1: [Description]
- **Symptom:** [What you see]
- **Cause:** [Why it happens]
- **Solution:** [How to fix]

### Common Issue 2: [Description]
- **Symptom:** [What you see]
- **Cause:** [Why it happens]
- **Solution:** [How to fix]

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | YYYY-MM-DD | Initial version | [Name] |

---

## Related Resources

- [Link to prompt templates]
- [Link to quality rubrics]
- [Link to architecture docs]
- [Link to related workflows]
```

-----

## **Appendix M: MCP Configuration Reference**

```markdown
# MCP Configuration Guide

## Configuration File Location

**Mac:** `~/Library/Application Support/Claude/claude_desktop_config.json`

**Windows:** `%APPDATA%\Claude\claude_desktop_config.json`

---

## Basic Configuration Structure

```json
{
  "mcpServers": {
    "server-name": {
      "command": "executable",
      "args": ["arg1", "arg2"],
      "env": {
        "ENV_VAR": "value"
      }
    }
  }
}
```

---

## Common Server Configurations

### Filesystem Server
Access local files and directories.

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/Users/yourname/Documents/prompts",
        "/Users/yourname/Projects"
      ]
    }
  }
}
```

**Notes:**
- List all directories you want Claude to access
- Use absolute paths
- Restart Claude Desktop after changes

### GitHub Server
Access GitHub repositories.

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_xxxxxxxxxxxx"
      }
    }
  }
}
```

**Token Setup:**
1. GitHub → Settings → Developer Settings
2. Personal Access Tokens → Tokens (classic)
3. Generate new token
4. Select scopes: `repo`, `read:user`
5. Copy token (shown only once)

### Slack Server
Access Slack workspaces.

```json
{
  "mcpServers": {
    "slack": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-slack"],
      "env": {
        "SLACK_BOT_TOKEN": "xoxb-xxxxxxxxxxxx",
        "SLACK_TEAM_ID": "T0XXXXXXX"
      }
    }
  }
}
```

### Google Drive Server
Access Google Drive files.

```json
{
  "mcpServers": {
    "gdrive": {
      "command": "npx",
      "args": ["-y", "@anthropics/mcp-server-gdrive"],
      "env": {
        "GOOGLE_CLIENT_ID": "xxx.apps.googleusercontent.com",
        "GOOGLE_CLIENT_SECRET": "xxx"
      }
    }
  }
}
```

---

## Multiple Servers Example

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/Users/me/prompts"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_xxx"
      }
    }
  }
}
```

---

## Troubleshooting

### Server Not Appearing
1. Check JSON syntax (use validator)
2. Verify file location is correct
3. Restart Claude Desktop completely
4. Check server logs in Claude

### Permission Errors
1. Verify paths are accessible
2. Check token permissions/scopes
3. Ensure environment variables are set

### Connection Failures
1. Check internet connection
2. Verify API tokens are valid
3. Try running server command manually in terminal

---

## Security Best Practices

1. **Token Management:**
   - Use environment variables instead of hardcoding
   - Rotate tokens regularly
   - Use minimum required scopes

2. **File Access:**
   - Only allow necessary directories
   - Avoid giving access to sensitive areas

3. **Monitoring:**
   - Review what Claude accesses
   - Check server logs periodically

---

## Environment Variables Alternative

Instead of tokens in config:

**Mac/Linux (.zshrc or .bashrc):**
```bash
export GITHUB_PERSONAL_ACCESS_TOKEN="ghp_xxx"
```

**Then in config:**
```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"]
    }
  }
}
```
The server will read from environment automatically.
```

-----

## **Appendix N: Quality Evaluation Prompt Template**

```markdown
# Quality Evaluation Prompt Template

## Purpose
Use this template to create automated quality checks for your workflows.

---

## Template Structure

```
You are a quality evaluator assessing a [DELIVERABLE_TYPE] for a consulting firm.

## Evaluation Criteria

For each criterion below, provide:
- A score from 1-5
- A brief (1-2 sentence) justification

### Criterion 1: [NAME]
**Description:** [What this measures]
- 5 (Excellent): [Specific description]
- 4 (Good): [Specific description]
- 3 (Adequate): [Specific description]
- 2 (Poor): [Specific description]
- 1 (Missing): [Specific description]

### Criterion 2: [NAME]
[Repeat structure]

### Criterion 3: [NAME]
[Repeat structure]

[Add 2-4 more criteria as needed]

---

## Content to Evaluate

```
{content_to_evaluate}
```

---

## Output Format

You MUST respond with valid JSON only. No other text.

```json
{
  "evaluation": {
    "criterion_1": {
      "score": [1-5],
      "justification": "Brief explanation"
    },
    "criterion_2": {
      "score": [1-5],
      "justification": "Brief explanation"
    }
  },
  "overall_score": [calculated average],
  "pass": [true if overall_score >= threshold, else false],
  "summary": "One sentence overall assessment",
  "improvement_suggestions": [
    "Suggestion 1",
    "Suggestion 2"
  ]
}
```

Pass threshold: [X.X]
```

---

## Example: Proposal Evaluation Prompt

```
You are a quality evaluator assessing a client proposal for a consulting firm.

## Evaluation Criteria

### Criterion 1: Problem Clarity
**Description:** How clearly the client's problem is stated
- 5: Problem is specific, quantified, and directly tied to business impact
- 4: Problem is clear with most specifics present
- 3: Problem is mentioned but somewhat vague
- 2: Problem is unclear or generic
- 1: No clear problem statement

### Criterion 2: Solution Fit
**Description:** How well the proposed solution addresses the stated problem
- 5: Solution directly addresses all aspects of the problem with clear methodology
- 4: Solution addresses problem well with minor gaps
- 3: Solution partially addresses problem
- 2: Weak connection between problem and solution
- 1: Solution doesn't address stated problem

### Criterion 3: Value Proposition
**Description:** Clarity and strength of the business case
- 5: Clear, quantified benefits with compelling ROI
- 4: Good benefits stated, mostly quantified
- 3: Benefits mentioned but not well quantified
- 2: Vague or generic value claims
- 1: No clear value proposition

### Criterion 4: Professional Quality
**Description:** Writing quality, formatting, and professionalism
- 5: Flawless writing, perfect formatting, highly professional
- 4: Minor issues, good overall quality
- 3: Some quality issues but acceptable
- 2: Multiple quality problems
- 1: Unprofessional quality

---

## Content to Evaluate

```
{proposal_content}
```

---

## Output Format

Respond with valid JSON only:

```json
{
  "evaluation": {
    "problem_clarity": {"score": X, "justification": "..."},
    "solution_fit": {"score": X, "justification": "..."},
    "value_proposition": {"score": X, "justification": "..."},
    "professional_quality": {"score": X, "justification": "..."}
  },
  "overall_score": X.X,
  "pass": true/false,
  "summary": "One sentence assessment",
  "improvement_suggestions": ["...", "..."]
}
```

Pass threshold: 3.5
```

---

## Usage Notes

1. **Customize criteria** for each deliverable type
2. **Be specific** in score descriptions to get consistent results
3. **Test thoroughly** with good and bad examples
4. **Adjust threshold** based on your quality requirements
5. **Parse JSON** in workflow to route based on pass/fail
```

-----

## **Appendix O: MCP Troubleshooting Guide**

# MCP Troubleshooting Guide

## Quick Diagnostic Checklist

When MCP isn't working, check these in order:

- [ ] JSON syntax is valid (test at jsonlint.com)
- [ ] Config file is in correct location for your OS
- [ ] Claude Desktop was fully quit and relaunched
- [ ] Node.js is installed (`node --version` in terminal)
- [ ] File paths in config actually exist
- [ ] No trailing commas in JSON

---

## Common Issues and Solutions

### Issue: "Server Not Appearing in Claude"

**Symptoms:**
- Asked Claude about MCP tools, says it has none
- No server-related options visible

**Solutions:**

1. **Verify config file location:**
   - Mac: `~/Library/Application Support/Claude/claude_desktop_config.json`
   - Windows: `%APPDATA%\Claude\claude_desktop_config.json`
   - File must be named exactly `claude_desktop_config.json`

2. **Validate JSON syntax:**
   ```json
   // WRONG - trailing comma
   {
     "mcpServers": {
       "filesystem": { ... },  // ← comma here causes failure if last item
     }
   }

   // CORRECT - no trailing comma
   {
     "mcpServers": {
       "filesystem": { ... }
     }
   }
   ```

3. **Fully restart Claude Desktop:**
   - Mac: Menu bar → Claude → Quit Claude (not just close window)
   - Windows: System tray → Right-click Claude icon → Exit
   - Then relaunch

4. **Check Claude Desktop version:**
   - MCP requires recent Claude Desktop versions
   - Update if available: Help → Check for Updates

---

### Issue: "npx Command Not Found"

**Symptoms:**
- Server fails to start
- Error mentions npx or npm not found

**Solutions:**

1. **Install Node.js:**
   - Download from https://nodejs.org/ (LTS version)
   - Run installer with default options
   - Restart terminal/command prompt after install

2. **Verify installation:**
   ```bash
   node --version    # Should show version number
   npm --version     # Should show version number
   npx --version     # Should show version number
   ```

3. **If still not working (Mac):**
   ```bash
   # May need to add to PATH - add to ~/.zshrc:
   export PATH="/usr/local/bin:$PATH"
   ```

4. **If still not working (Windows):**
   - Restart computer after Node.js install
   - Or manually add Node.js to system PATH

---

### Issue: "Permission Denied" Errors

**Symptoms:**
- Server starts but can't access files
- Error mentions permissions

**Solutions:**

1. **Filesystem server - verify path access:**
   - Path in config must be readable by your user
   - Try a simple path first: your Documents folder
   - Avoid system directories

2. **GitHub server - verify token:**
   - Token may have expired
   - Token may lack required scopes
   - Generate new token with `repo` and `read:user` scopes

3. **Mac-specific:**
   - Claude Desktop may need Full Disk Access
   - System Preferences → Security & Privacy → Privacy → Full Disk Access
   - Add Claude if prompted

---

### Issue: "GitHub Server Can't Access Repository"

**Symptoms:**
- GitHub MCP configured but can't read repos
- Authentication errors

**Solutions:**

1. **Verify token is correct:**
   - No extra spaces when copying
   - Token starts with `ghp_`
   - Token hasn't expired

2. **Check token scopes:**
   - Go to GitHub → Settings → Developer Settings → Personal Access Tokens
   - Verify token has `repo` scope (for private repos)
   - Verify token has `read:user` scope

3. **Token in config correctly:**
   ```json
   {
     "mcpServers": {
       "github": {
         "command": "npx",
         "args": ["-y", "@modelcontextprotocol/server-github"],
         "env": {
           "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_xxxxxxxxxxxx"
         }
       }
     }
   }
   ```
   - Note: Token is in `env` object, not `args`

4. **Alternative - use environment variable:**

   Instead of putting token in config file:

   **Mac (~/.zshrc):**
   ```bash
   export GITHUB_PERSONAL_ACCESS_TOKEN="ghp_xxxxxxxxxxxx"
   ```

   **Windows (System Environment Variables):**
   - Search "Environment Variables" in Start menu
   - Add new User variable: GITHUB_PERSONAL_ACCESS_TOKEN

   Then config can omit the env section:
   ```json
   {
     "mcpServers": {
       "github": {
         "command": "npx",
         "args": ["-y", "@modelcontextprotocol/server-github"]
       }
     }
   }
   ```

---

### Issue: "Server Starts Then Immediately Stops"

**Symptoms:**
- Brief activity then nothing
- Server shows then disappears

**Solutions:**

1. **Check for conflicting servers:**
   - Two servers can't use same name
   - Each server needs unique key in mcpServers object

2. **Test server manually in terminal:**
   ```bash
   npx -y @modelcontextprotocol/server-filesystem /your/path
   ```
   - Watch for error messages
   - Ctrl+C to stop when done testing

3. **Check Claude Desktop logs:**
   - Mac: `~/Library/Logs/Claude/`
   - Windows: `%APPDATA%\Claude\logs\`
   - Look for recent error messages

---

### Issue: "Everything Was Working, Now It's Not"

**Symptoms:**
- MCP worked before, stopped working
- No config changes made

**Solutions:**

1. **Node.js/npm update broke things:**
   ```bash
   # Clear npm cache
   npm cache clean --force

   # Try running server manually to see errors
   npx -y @modelcontextprotocol/server-filesystem /your/path
   ```

2. **Claude Desktop update:**
   - Config format may have changed
   - Check Anthropic's MCP documentation for updates

3. **Token expired:**
   - GitHub tokens can expire
   - Generate new token and update config

4. **Simple restart:**
   - Fully quit Claude Desktop
   - Close all terminal windows
   - Restart computer if needed
   - Relaunch Claude Desktop

---

## Validation Commands

Run these to verify your setup:

```bash
# Check Node.js installation
node --version

# Check npm installation
npm --version

# Test filesystem server manually
npx -y @modelcontextprotocol/server-filesystem ~/Documents

# Test GitHub server manually (needs token in environment)
export GITHUB_PERSONAL_ACCESS_TOKEN="ghp_xxx"
npx -y @modelcontextprotocol/server-github

# Validate JSON config
# Copy your config and paste at: https://jsonlint.com/
```

---

## Getting Help

If these solutions don't work:

1. **Check MCP documentation:** https://modelcontextprotocol.io/
2. **Search GitHub issues:** https://github.com/modelcontextprotocol/servers/issues
3. **Ask in training support channel** with:
   - Your operating system
   - Node.js version (`node --version`)
   - Your config file (remove any tokens first!)
   - Exact error message
   - Steps you've already tried

-----

## **Certification: AI Workflow Engineer**

Upon successful completion of Block 2 Capstone with a score of 22+ points (55%+):

**You have demonstrated:**
- Ability to design and build multi-step AI workflows
- Proficiency in MCP configuration and tool integration
- Understanding of quality systems and automated evaluation
- Skill in performance monitoring and optimization
- Creation of reusable workflow templates for team use
- Measured business impact with actual data

**You are certified as:** AI Workflow Engineer

**Next Steps:**
- Continue to [Block 3: AI Automation Architecture](block-3.md)
- Enrollment opens upon Block 2 certification
- Block 3 starts 1-2 weeks after Block 2 evaluation

-----

**END OF BLOCK 2 CURRICULUM**

---

**Navigation:** [← README](README.md) | [← Block 1](block-1.md) | **Block 2** | [Block 3 →](block-3.md)
