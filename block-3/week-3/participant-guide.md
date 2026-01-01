# **BLOCK 3 WEEK 3: MCP Deep Dive**

**Block:** 3: AI Automation Architecture
**Week:** 3 of 8
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Block Navigation:** [Week 2 Participant Guide](../week-2/participant-guide.md) | **Week 3** | [Week 4 Participant Guide](../week-4/participant-guide.md)

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
| 1 | Configure multiple MCP servers for expanded agent capabilities | Exercise 3.1 |
| 2 | Create tool-specific prompts that guide agent behavior | Exercise 3.2 |
| 3 | Implement tool chaining patterns for complex tasks | Exercise 3.3 |
| 4 | Apply security best practices for production MCP configurations | All Exercises |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Functional agent with error handling (Week 2)
- [ ] 5+ successful agent executions
- [ ] MCP basics from Block 2 understood
- [ ] GitHub MCP working (or at least one MCP server)

**Not ready?** You must have a functional agent before proceeding. MCP expansion builds on a working foundation.

---

## Key Concepts

### Concept 1: MCP in the Agent Context

**Definition:**
Model Context Protocol (MCP) is the protocol that connects Claude to external tools and data sources. In agent context, MCP enables agents to interact with the world through multiple specialized servers.

**Why It Matters:**
Without MCP, your agent can only process text. With MCP, it can read files, search the web, interact with GitHub, send emails, query databases - the capabilities become vastly expanded.

**Architecture:**
```
Agent (Claude) ← MCP Protocol → Server 1 (Files)
                              → Server 2 (GitHub)
                              → Server 3 (Database)
                              → Server 4 (API)
```

**Core Principle:**
> "One agent, many tools - MCP is the protocol that makes this possible."

---

### Concept 2: MCP Server Types

**Definition:**
MCP servers are categorized by their primary purpose: Data servers provide read access, Action servers perform operations, Integration servers connect to external platforms.

**Server Type Matrix:**

| Type | Purpose | Examples | When to Use |
|------|---------|----------|-------------|
| **Data Servers** | Read information | Filesystem, Database queries | Agent needs to read files, configs, data |
| **Action Servers** | Perform operations | Email, Slack, Document creation | Agent needs to create, send, or modify |
| **Integration Servers** | Connect platforms | GitHub, Google Drive, Notion | Agent works with external services |

**Selection Strategy:**
1. What data does my agent need to read?
2. What actions must my agent take?
3. What external systems must my agent integrate with?

---

### Concept 3: Tool Chaining Patterns

**Definition:**
Tool chaining is connecting multiple tools so the output of one becomes the input of the next, enabling complex multi-step operations.

**Pattern 1: Sequential Chaining**
```
Search files → Read file → Extract data → Write to database
```
- Each tool output feeds the next tool's input
- Clear data transformation path
- Best for: Linear processes with dependencies

**Pattern 2: Conditional Chaining**
```
Check condition → IF true: Tool A → Tool B
                → IF false: Tool C → Tool D
```
- Agent decides path based on results
- Dynamic flow control
- Best for: Processes with branches

**Pattern 3: Parallel Tool Use**
```
Start →┬→ Search Web ──────┬→ Combine → Output
       ├→ Search Files ────┤
       └→ Query Database ──┘
```
- Multiple tools simultaneously
- Results aggregation
- Best for: Gathering from multiple sources

**Implementation Tips:**
- Clear handoff prompts between tools
- Validate outputs before chaining
- Handle partial failures gracefully

---

### Concept 4: The 12-Factor Agent Principles (Key Highlights)

**Definition:**
Operational principles that production agents should follow for reliability, maintainability, and scalability.

**Five Key Principles:**

| Principle | Meaning | Application |
|-----------|---------|-------------|
| **Own Your Prompts** | Treat prompts as code, not framework magic | Write explicit prompts, version control them |
| **Own Your Context Window** | Curate ruthlessly | Only include necessary information |
| **Tools Are Structured Outputs** | LLM emits JSON, you handle results | Validate and process tool responses |
| **Small, Focused Agents** | 3-20 step workflows | Smaller = better performance |
| **Stateless Reducer** | `(state, event) → state` | Enables testing and replay |

**Why It Matters:**
Following these principles means your agent is debuggable, testable, and maintainable - not a black box.

---

### Concept 5: MCP Security Principles

**Definition:**
Security practices specific to MCP configurations that protect credentials, limit exposure, and maintain audit trails.

**Core Principles:**

| Principle | Implementation | Example |
|-----------|----------------|---------|
| **Least Privilege** | Only enable needed servers | Don't add email server if agent doesn't send email |
| **Token Management** | Use env vars, rotate regularly | `GITHUB_TOKEN` in .env, not in config |
| **Data Boundaries** | Know what's exposed | Restrict filesystem to specific directories |
| **Audit Logging** | Track all tool usage | Log every tool call with timestamp |

**Security Checklist:**
- [ ] Credentials in environment variables, not config files
- [ ] Servers limited to required directories/repos
- [ ] Token rotation schedule defined
- [ ] Tool usage logging enabled

---

### Quick Reference: MCP Configuration Structure

```json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-name", "argument"],
      "env": {
        "API_TOKEN": "${ENVIRONMENT_VARIABLE}"
      }
    }
  }
}
```

| Field | Purpose | Notes |
|-------|---------|-------|
| `server-name` | Identifier for this server | Use descriptive names |
| `command` | Executable to run | Usually `npx` or `node` |
| `args` | Command line arguments | Server package and options |
| `env` | Environment variables | Use `${VAR}` for secrets |

---

## Workshop Recap

### Session Summary

**Today's Focus:** Advanced MCP architecture, multi-server configuration, tool chaining patterns, and production security.

**Key Points from Each Segment:**

**Segment 1: Advanced MCP Architecture**
- Agent connects to multiple servers via MCP protocol
- Server types: Data (read), Action (write/send), Integration (platforms)
- Tool discovery allows agents to see available capabilities

**Segment 2: Configuring Multi-Server Environments**
- All servers defined in one config file
- Strategy: What data? What actions? What integrations?
- Test each server independently before combining

**Segment 3: Tool Chaining Patterns**
- Sequential: Output feeds input
- Conditional: Path depends on results
- Parallel: Multiple simultaneous, aggregate results
- Validate between steps, handle partial failures

**Segment 4: Production Principles + Security**
- 12-Factor Agent: Own prompts, context, tool handling
- Security: Least privilege, token management, audit logging

### Demo Recap

**What Was Demonstrated:**
Multi-server MCP configuration with tool chaining

**Key Steps:**
1. Config.json with filesystem, GitHub, and web search servers
2. Restart Claude Desktop to load configuration
3. Verified all tools available in Claude interface
4. Demonstrated sequential chain: Search → Read → Summarize
5. Showed tool selection based on task requirements

**Result:**
Agent with access to multiple tools, able to chain them for complex tasks.

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 3.1 | 25 min | Multi-server config + verification | Expand capabilities |
| 3.2 | 25 min | Tool prompts + updated system prompt | Guide tool usage |
| 3.3 | 25 min | Tool chain documentation + tests | Connect tools |

---

### Exercise 3.1: Multi-Server Configuration

**Duration:** 25 minutes

**Purpose:**
Expand your agent's capabilities by configuring multiple MCP servers. This exercise ensures your agent has all the tools it needs for complex tasks.

**You Will Create:**
A working multi-server configuration with verification documentation.

---

#### Instructions

**Step 1: Identify Required Servers**

Create a requirements analysis:

```markdown
# MCP Server Requirements

## Agent: [Name]

### Required Capabilities

| Capability | Server | Priority | Status |
|------------|--------|----------|--------|
| Read local files | filesystem | Required | |
| Access GitHub | github | Required | |
| [Your capability 3] | [server] | [Required/Nice-to-have] | |
| [Your capability 4] | [server] | [Required/Nice-to-have] | |

### Analysis Questions
1. What data does my agent need to read?
   - [Answer]

2. What actions must my agent take?
   - [Answer]

3. What external systems must my agent integrate with?
   - [Answer]
```

**Step 2: Configure Each Server**

For each required server, add to your config:

```markdown
### Server Configurations

#### Server 1: Filesystem
\`\`\`json
{
  "filesystem": {
    "command": "npx",
    "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/allowed/directory"],
    "env": {}
  }
}
\`\`\`
- **Purpose:** Read templates, configs, and reference data
- **Test command:** "Read the file at [specific path]"
- **Security note:** Limited to [specific directory]

#### Server 2: GitHub
\`\`\`json
{
  "github": {
    "command": "npx",
    "args": ["-y", "@modelcontextprotocol/server-github"],
    "env": {
      "GITHUB_PERSONAL_ACCESS_TOKEN": "${GITHUB_TOKEN}"
    }
  }
}
\`\`\`
- **Purpose:** Access version-controlled templates and resources
- **Test command:** "List files in repository [repo-name]"
- **Security note:** Token in .env file, not config

#### Server 3: [Your Additional Server]
[Repeat structure]
```

**Step 3: Update Claude Desktop Configuration**

1. Locate your config file:
   - Mac: `~/Library/Application Support/Claude/claude_desktop_config.json`
   - Windows: `%APPDATA%\Claude\claude_desktop_config.json`

2. Add all server configurations

3. Restart Claude Desktop

**Step 4: Verify Each Server**

Test each server individually:

```markdown
# MCP Configuration - [Agent Name]

## Verification Log

### Filesystem Server
- **Test performed:** Read file at /prompts/test.md
- **Result:** Success / Failure
- **Notes:** [Any issues or observations]
- **Verified:** [Date]

### GitHub Server
- **Test performed:** List files in [repo-name]
- **Result:** Success / Failure
- **Notes:** [Any issues or observations]
- **Verified:** [Date]

### [Server 3]
[Repeat structure]

## Active Servers Summary

| Server | Status | Last Tested | Notes |
|--------|--------|-------------|-------|
| filesystem | ✓ Active | [Date] | Limited to /projects |
| github | ✓ Active | [Date] | Read-only access |
| [other] | | | |
```

**Step 5: Document Final Configuration**

Include your complete (sanitized) configuration:

```markdown
## Full Configuration File

Note: Tokens replaced with placeholders

\`\`\`json
{
  "mcpServers": {
    // Your complete configuration here
    // Replace actual tokens with ${VAR_NAME}
  }
}
\`\`\`
```

---

#### Deliverable Specification

**File Name:** `mcp-configuration.md`

**Location:** `/agents/[agent-name]/config/`

**Quality Criteria:**
- [ ] At least 3 servers configured
- [ ] Each server tested and verified
- [ ] Credentials use environment variables
- [ ] Security notes included

---

### Exercise 3.2: Tool Prompts Development

**Duration:** 25 minutes

**Purpose:**
Create explicit guidance for how your agent should use each tool. Good tool prompts improve tool selection and reduce errors.

**You Will Create:**
A tool usage guide and updated system prompt.

---

#### Instructions

**Step 1: Create Tool Usage Guide**

```markdown
# Tool Usage Guide for [Agent Name]

## Tool: Filesystem - Read File

### When to Use
- Need to read content from a local file
- Accessing templates, configs, or reference data
- Reading previous outputs for comparison

### When NOT to Use
- File is outside allowed directory
- Content is binary (images, PDFs)
- File is extremely large (>1MB)

### How to Use
1. Confirm file path is within allowed directories
2. Check if file exists before reading
3. Handle large files by reading sections

### Example Usage
"I need to read the proposal template. Let me use the filesystem tool to access /prompts/proposal-template.md"

### Expected Output
- File contents as text
- Error if file not found

### Common Errors
| Error | Cause | Solution |
|-------|-------|----------|
| File not found | Wrong path or file deleted | Verify path, check permissions |
| Too large | File exceeds size limit | Read in chunks or summarize |
| Permission denied | Outside allowed directory | Check allowed paths |

---

## Tool: GitHub - Read Repository

### When to Use
- Accessing version-controlled templates
- Reading latest version of resources
- Checking repository status

### When NOT to Use
- Frequent writes (use sparingly)
- Large file downloads
- Binary files

### How to Use
1. Specify repository and file path
2. Use for reading, not frequent writes
3. Respect rate limits

### Example Usage
"I need to check the latest template version. Let me read from the templates repository."

### Expected Output
- File contents from specified path
- Repository information

### Common Errors
| Error | Cause | Solution |
|-------|-------|----------|
| Not found | Wrong repo or path | Verify repository name and path |
| Rate limited | Too many requests | Wait and retry with backoff |
| Auth failed | Token expired or invalid | Check GITHUB_TOKEN |

---

## Tool: [Your Third Tool]

### When to Use
[Specific scenarios]

### When NOT to Use
[Anti-patterns]

### How to Use
[Step-by-step]

### Example Usage
[Concrete example]

### Expected Output
[What to expect]

### Common Errors
| Error | Cause | Solution |
|-------|-------|----------|
| | | |
```

**Step 2: Update System Prompt**

Add tool guidance to your system prompt:

```markdown
## Tool Usage Guidelines

### Tool Selection
When deciding which tool to use:
- For reading local files: Use filesystem
- For GitHub resources: Use github server
- For [capability]: Use [tool]

### Tool Usage Patterns

#### Filesystem
- Always verify path is within allowed directories
- Read file before attempting to modify
- Use for: templates, configs, reference data

#### GitHub
- Use for version-controlled content
- Prefer reading over writing
- Check for latest version when templates matter

#### [Third Tool]
- [Specific guidance]

### Error Recovery
If a tool fails:
1. Check the error message
2. Verify inputs are correct
3. Try alternative approach if available
4. Log failure and continue if non-critical
```

**Step 3: Integrate and Test**

1. Add tool guidance to your system prompt
2. Test agent with prompts that require tool selection
3. Verify agent chooses appropriate tools

---

#### Deliverable Specification

**File Name:** `tool-prompts.md` + updated `system-prompt.md`

**Location:** `/agents/[agent-name]/prompts/`

**Quality Criteria:**
- [ ] Each configured tool has a usage guide
- [ ] When to use AND when NOT to use specified
- [ ] Common errors documented with solutions
- [ ] System prompt includes tool guidance

---

### Exercise 3.3: Tool Chaining Implementation

**Duration:** 25 minutes

**Purpose:**
Design and implement tool chains that accomplish complex tasks by connecting multiple tools together.

**You Will Create:**
Tool chain documentation and test results.

---

#### Instructions

**Step 1: Design Your Tool Chain**

Choose a common task for your agent that requires multiple tools:

```markdown
# Tool Chain: [Task Name]

## Purpose
[What this chain accomplishes]

## Chain Diagram
\`\`\`
[Tool 1: Action] → [Transform: How] → [Tool 2: Action] → [Output]
\`\`\`

## Step-by-Step Flow

### Step 1: [Tool 1 Name]
- **Action:** [What the tool does]
- **Input:** [What it receives]
- **Output:** [What it produces]
- **Validation:** [How to verify success]
- **Pass to next:** [What data flows forward]

### Step 2: [Tool 2 Name]
- **Action:** [What the tool does]
- **Input:** [From Step 1]
- **Output:** [What it produces]
- **Validation:** [How to verify success]
- **Pass to next:** [What data flows forward]

### Step 3: [Tool 3 Name]
- **Action:** [What the tool does]
- **Input:** [From Step 2]
- **Output:** [Final deliverable]
- **Validation:** [How to verify success]

## Error Handling

| Step | Possible Error | Recovery Action |
|------|----------------|-----------------|
| 1 | [Error type] | [What to do] |
| 2 | [Error type] | [What to do] |
| 3 | [Error type] | [What to do] |

## Validation Points
- After Step 1: [What to check]
- After Step 2: [What to check]
- Final: [What to verify]
```

**Step 2: Add Chain Instructions to System Prompt**

```markdown
## Tool Chain: [Task Name]

When asked to [trigger phrase], follow this sequence:

1. First, use [Tool 1] to [action]
   - Verify: [check]
   - If fails: [recovery]

2. Then, use [Tool 2] with the result to [action]
   - Verify: [check]
   - If fails: [recovery]

3. Finally, use [Tool 3] to [complete action]
   - Verify: [check]
   - If fails: [recovery]

Report progress at each step.
```

**Step 3: Test the Chain**

Execute the chain 3+ times with variations:

```markdown
# Tool Chain Test Results

## Test 1: [Standard Case]
- **Input:** [What you asked]
- **Step 1 result:** [Success/Fail] - [Notes]
- **Step 2 result:** [Success/Fail] - [Notes]
- **Step 3 result:** [Success/Fail] - [Notes]
- **Final output:** [Quality assessment]
- **Total time:** [Duration]

## Test 2: [Variation]
[Repeat structure]

## Test 3: [Edge Case]
[Repeat structure]

## Summary
- Success rate: [X/3]
- Average time: [Duration]
- Issues found: [List]
- Improvements needed: [List]
```

**Step 4: Optimize Chain**

Based on test results:
- Identify bottlenecks
- Add caching where possible
- Reduce unnecessary calls

---

#### Deliverable Specification

**File Name:** `tool-chain-[name].md`

**Location:** `/agents/[agent-name]/`

**Quality Criteria:**
- [ ] At least one complete tool chain designed
- [ ] Chain uses 2+ tools
- [ ] Error handling specified for each step
- [ ] 3+ test executions documented
- [ ] Optimizations identified

---

#### Example Tool Chain

**Research and Summarize Chain:**

```markdown
# Tool Chain: Research and Summarize

## Purpose
Gather information from multiple sources and create a summary document

## Chain Diagram
\`\`\`
[Web Search: Query] → [Filesystem: Read context] → [Combine & Summarize] → [Filesystem: Write output]
\`\`\`

## Step-by-Step Flow

### Step 1: Web Search
- **Action:** Search for current information on topic
- **Input:** Search query from user request
- **Output:** List of relevant results with snippets
- **Validation:** At least 3 relevant results returned
- **Pass to next:** Top 5 results with URLs and summaries

### Step 2: Filesystem Read
- **Action:** Read context file with background information
- **Input:** Path to context file (e.g., /context/topic-background.md)
- **Output:** Background information text
- **Validation:** File successfully read
- **Pass to next:** Combined web results + background context

### Step 3: Synthesize
- **Action:** Combine sources into coherent summary
- **Input:** Web results + background context
- **Output:** Structured summary document
- **Validation:** Summary addresses original query
- **Pass to next:** Final summary text

### Step 4: Filesystem Write
- **Action:** Save summary to output file
- **Input:** Summary text
- **Output:** Confirmation of file saved
- **Validation:** File exists and contains summary

## Error Handling

| Step | Possible Error | Recovery Action |
|------|----------------|-----------------|
| 1 | No search results | Broaden query, try alternative terms |
| 2 | File not found | Continue with web results only |
| 3 | Poor synthesis | Retry with explicit structure |
| 4 | Write failed | Return summary in response instead |
```

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| MCP Server Requirements | Identify needed capabilities | Exercise 3.1 |
| Tool Usage Guide | Document tool behavior | Exercise 3.2 |
| Tool Chain Design | Plan multi-tool operations | Exercise 3.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| MCP Server Registry | Registry | [GitHub](https://github.com/modelcontextprotocol/servers) | Finding available servers |
| MCP Documentation | Documentation | [modelcontextprotocol.io](https://modelcontextprotocol.io/) | Understanding protocol |
| 12-Factor Agents | Reference | [GitHub](https://github.com/humanlayer/12-factor-agents) | Production principles |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Configure multiple MCP servers | 3+ servers working | |
| 2 | Create tool-specific prompts | Tool usage guide complete | |
| 3 | Implement tool chaining | Chain tested 3+ times | |
| 4 | Apply security best practices | Credentials in env vars | |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 3.1 output | `mcp-configuration.md` | `/agents/[name]/config/` | |
| Exercise 3.2 output | `tool-prompts.md` + updated prompt | `/agents/[name]/prompts/` | |
| Exercise 3.3 output | `tool-chain-[name].md` | `/agents/[name]/` | |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** Which MCP concept or pattern was most useful?

2. **What's still fuzzy?** What do you need more practice or clarification on?

3. **How did tool chaining change your agent?** What can it do now that it couldn't before?

4. **What security considerations did you address?** Any concerns remaining?

---

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, usually answered within 24 hours
- **MCP Registry** - Check for server-specific documentation

### Common Questions This Week

**Q: My server won't load - what do I check?**
A: In order: 1) JSON syntax valid, 2) Path to server correct, 3) Environment variables set, 4) Restart Claude Desktop. Post full error if stuck.

**Q: How do I know which servers I need?**
A: Answer three questions: What data does my agent read? What actions does it take? What systems does it integrate with?

**Q: Can I create my own MCP server?**
A: Yes, but it's beyond Block 3 scope. For most use cases, existing servers plus configuration is sufficient.

### When to Ask for Help

- **Before asking:** Check config syntax, restart Claude, verify env vars
- **Good to ask:** "My [server] fails with [specific error]. Config is [sanitized config]. What am I missing?"
- **Include:** Error message, relevant config (tokens removed), what you've tried

---

## Looking Ahead

### Next Week Preview: Week 4 - Multi-Step Agents

**Focus:**
Complex task decomposition, state management across steps, checkpoint and resume capabilities.

**How It Builds on This Week:**
Your multi-tool agent will learn to plan and execute complex tasks that span multiple steps, with state tracked throughout.

**To Prepare:**
- [ ] Complete all Week 3 exercises
- [ ] Ensure 3+ tools working reliably
- [ ] Test your tool chain multiple times
- [ ] Review state management concepts from Week 2

---

## Glossary

| Term | Definition |
|------|------------|
| MCP | Model Context Protocol - standard for connecting Claude to external tools |
| Server | An MCP server that provides specific tool capabilities |
| Tool | A specific action or capability provided by an MCP server |
| Tool Chaining | Connecting multiple tools so output of one feeds input of another |
| Sequential Chaining | Tools executed in order, each dependent on previous |
| Conditional Chaining | Tool path depends on results of previous tools |
| Parallel Tool Use | Multiple tools executed simultaneously, results combined |
| Least Privilege | Only enable capabilities that are actually needed |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [Week 2 Participant Guide](../week-2/participant-guide.md) | **Week 3** | [Week 4 Participant Guide](../week-4/participant-guide.md)
