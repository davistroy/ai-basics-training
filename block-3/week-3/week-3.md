# Week 3: MCP Deep Dive

**Block:** 3 - AI Automation Architecture
**Duration:** 45 min live workshop + 75 min self-paced exercises

---

## Entry Criteria

- [ ] Functional agent with error handling
- [ ] 5+ successful agent executions
- [ ] MCP basics from Block 2 understood
- [ ] GitHub MCP working

## Exit Criteria

- [ ] Multiple MCP servers configured for agent
- [ ] Custom tool prompts created
- [ ] Agent uses 3+ MCP tools effectively
- [ ] Tool chaining implemented
- [ ] MCP security best practices applied

---

## Workshop Content (45 minutes)

### Segment 1: Advanced MCP Architecture (10 min)

**MCP in the agent context:**
```
Agent (Claude) ← MCP Protocol → Server 1 (Files)
                              → Server 2 (GitHub)
                              → Server 3 (Database)
                              → Server 4 (API)
```

**Server types for agents:**
- **Data servers:** Filesystem, databases, APIs
- **Action servers:** Email, Slack, document creation
- **Integration servers:** GitHub, Google Drive, Notion

**Tool discovery:**
- Agents can list available tools
- Dynamic tool selection based on need
- Tool descriptions guide agent decisions

**Resource exposure:**
- Static resources (files, configs)
- Dynamic resources (search results, API data)
- Context injection patterns

### Segment 2: Configuring Multi-Server Environments (12 min)

**Configuration architecture:**

```json
{
  "mcpServers": {
    "filesystem": { /* file access */ },
    "github": { /* repository operations */ },
    "postgres": { /* database queries */ },
    "slack": { /* notifications */ }
  }
}
```

**Server selection strategy:**
- What data does your agent need?
- What actions must it take?
- What systems does it integrate with?

**Dependency management:**
- Some servers require others
- Order of operations matters
- Credential coordination

### Segment 3: Tool Chaining Patterns (12 min)

**Sequential chaining:**
```
Search files → Read file → Extract data → Write to database
```
- Each tool output feeds next input
- Clear data transformation path

**Conditional chaining:**
```
Check condition → IF true: Tool A → Tool B
                → IF false: Tool C → Tool D
```
- Agent decides path based on results
- Dynamic flow control

**Parallel tool use:**
```
Start →┬→ Search Web ──────┬→ Combine → Output
       ├→ Search Files ────┤
       └→ Query Database ──┘
```
- Multiple tools simultaneously
- Results aggregation

**Implementation tips:**
- Clear handoff prompts between tools
- Validate outputs before chaining
- Handle partial failures gracefully

### Segment 4: Production Principles + Security (11 min)

**The 12-Factor Agent Principles (Key Highlights):**

Production agents follow operational principles:

1. **Own Your Prompts** - Treat prompts as first-class code, not framework magic
2. **Own Your Context Window** - Curate ruthlessly; context is your competitive advantage
3. **Tools Are Structured Outputs** - LLM emits JSON; YOUR code decides what to do
4. **Small, Focused Agents** - 3-20 step workflows; smaller = better performance
5. **Stateless Reducer** - Think `(state, event) → state`; enables testing and replay

**What this means for your agent:**
- You control the prompts (not hidden in a framework)
- You decide what goes in context (not automatic accumulation)
- You handle tool results (not black-box execution)
- You keep scope bounded (not "do everything")
- You can replay any decision (not mystery behavior)

**Security principles:**
- Least privilege: Only enable needed servers
- Token management: Rotate regularly, use env vars
- Data boundaries: Know what's exposed
- Audit logging: Track all tool usage

**Best practices:**
- Test each server independently
- Document all configurations
- Version control your config files
- Monitor for unusual patterns

---

## Self-Paced Exercises (75 minutes total)

### Exercise 3.1: Multi-Server Configuration (25 minutes)

*Expand your MCP capabilities*

1. **Identify needed servers for your agent:**

```markdown
# MCP Server Requirements

## Agent: [Name]

### Required Capabilities

| Capability | Server | Priority | Status |
|------------|--------|----------|--------|
| Read local files | filesystem | Required | ✓ |
| Access GitHub | github | Required | ✓ |
| [Capability 3] | [server] | [R/Nice] | |
| [Capability 4] | [server] | [R/Nice] | |

### Server Configurations

#### Server 1: [Name]
\`\`\`json
{
  "command": "...",
  "args": [...],
  "env": {...}
}
\`\`\`
- **Purpose:** [What it provides]
- **Test command:** [How to verify]

#### Server 2: [Name]
[Repeat structure]
```

2. **Update Claude Desktop configuration:**
   - Add all required servers
   - Restart and verify each works
   - Test tool availability in Claude

3. **Document working configuration:**

```markdown
# MCP Configuration - [Agent Name]

## Active Servers

| Server | Status | Last Tested | Notes |
|--------|--------|-------------|-------|
| filesystem | ✓ Active | [Date] | |
| github | ✓ Active | [Date] | |
| [other] | | | |

## Full Configuration File
[Include complete claude_desktop_config.json]
```

**Deliverable:** Multi-server configuration + verification documentation

---

### Exercise 3.2: Tool Prompts Development (25 minutes)

*Guide your agent's tool usage*

1. **Create tool-specific prompts:**

```markdown
# Tool Usage Guide for [Agent Name]

## Tool: [Filesystem - Read File]

### When to Use
- Need to read content from a local file
- Accessing templates, configs, or reference data
- Reading previous outputs for comparison

### How to Use
1. Confirm file path is within allowed directories
2. Check if file exists before reading
3. Handle large files by reading sections

### Example Usage
"I need to read the proposal template. Let me use the filesystem tool to access /prompts/proposal-template.md"

### Common Errors
- File not found: Verify path, check permissions
- Too large: Read in chunks or summarize

---

## Tool: [GitHub - Read Repository]

### When to Use
- Accessing version-controlled templates
- Reading latest version of resources
- Checking repository status

### How to Use
1. Specify repository and file path
2. Use for reading, not frequent writes
3. Respect rate limits

### Example Usage
[Provide example]

### Common Errors
[List common issues]

---

## Tool: [Custom Tool]
[Repeat structure for each tool]
```

2. **Integrate into system prompt:**
   - Add tool usage guidelines to system prompt
   - Include examples of correct usage
   - Add error handling instructions

**Deliverable:** Tool prompts document + updated system prompt

---

### Exercise 3.3: Tool Chaining Implementation (25 minutes)

*Build connected tool workflows*

1. **Design tool chain for common agent task:**

```markdown
# Tool Chain: [Task Name]

## Purpose
[What this chain accomplishes]

## Chain Diagram
\`\`\`
[Tool 1: Describe] → [Transform: How] → [Tool 2: Describe] → [Output]
\`\`\`

## Step-by-Step Flow

### Step 1: [Tool 1 Name]
- **Action:** [What to do]
- **Input:** [What it receives]
- **Output:** [What it produces]
- **Pass to next:** [What data flows forward]

### Step 2: [Tool 2 Name]
- **Action:** [What to do]
- **Input:** [From Step 1]
- **Output:** [What it produces]
- **Pass to next:** [What data flows forward]

### Step 3: [Tool 3 Name]
[Repeat structure]

## Error Handling

| Step | Possible Error | Recovery Action |
|------|----------------|-----------------|
| 1 | [Error] | [Action] |
| 2 | [Error] | [Action] |

## Validation Points
- After Step 1: [What to check]
- After Step 2: [What to check]
- Final: [What to verify]
```

2. **Implement and test the chain:**
   - Execute complete chain 3+ times
   - Test with variations
   - Document results

3. **Optimize chain:**
   - Identify bottlenecks
   - Add caching where possible
   - Reduce unnecessary calls

**Deliverable:** Tool chain documentation + test results

---

## Key Takeaways

1. **Multi-server MCP expands capabilities** - Connect to everything your agent needs
2. **Tool prompts guide behavior** - Explicit instructions improve tool usage
3. **Tool chaining creates power** - Combine simple tools for complex tasks
4. **Security is non-negotiable** - Least privilege, audit logging, token management
5. **The 12-Factor Agent principles** - Own your prompts, context, and tool handling

---

## Preparation for Week 4

- Ensure all MCP servers are working reliably
- Test tool chains multiple times
- Document any issues for discussion
- Next week: Multi-step agents

---

## Resources

- [MCP Server Registry](https://github.com/modelcontextprotocol/servers)
- [MCP Documentation](https://modelcontextprotocol.io/)
- [12-Factor Agent Principles](https://github.com/humanlayer/12-factor-agents)
