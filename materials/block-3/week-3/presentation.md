# **POWERPOINT PRESENTATION: BLOCK 3 WEEK 3**
## **MCP Deep Dive**

**Block:** 3: AI Automation Architecture
**Week Number:** 3
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 participants with functional agents from Week 2

**Week Learning Objectives:** By the end of this session, participants will:
1. Configure multiple MCP servers for expanded agent capabilities
2. Understand server types and selection strategies
3. Implement tool chaining patterns for complex tasks
4. Apply security best practices for production configurations

**Entry Criteria:** (What participants should have before this session)
- [ ] Functional agent with error handling (Week 2)
- [ ] 5+ successful agent executions
- [ ] MCP basics from Block 2 understood
- [ ] At least one MCP server working

**Exit Criteria:** (What participants should be able to do after this session)
- [ ] Explain MCP architecture in agent context
- [ ] Configure multiple servers in one config
- [ ] Describe three tool chaining patterns
- [ ] Apply security principles to MCP configurations

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Advanced MCP Architecture (10 min) - Slides 4-8
3. Segment 2: Multi-Server Configuration (12 min) - Slides 9-13
4. Segment 3: Tool Chaining Patterns (12 min) - Slides 14-19
5. Segment 4: Production + Security (8 min) - Slides 20-23
6. Homework Preview & Close (3 min) - Slides 24-25

**Total Slides:** 25

---

## SLIDE 1: TITLE SLIDE

**Title:** Block 3 Week 3: MCP Deep Dive

**Subtitle:** Expanding Agent Capabilities Through Multi-Server Architecture

**Content:**
- AI Practitioner Training Program
- Block 3: AI Automation Architecture

**Graphic:** Clean title slide with green theme (Block 3 color). Visual of connected servers.

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Week 3: MCP Deep Dive. This is where your agent's capabilities expand significantly.

Last week you built functional agents with error handling. Today we're giving those agents more tools to work with.

Quick status check: Who has a functional agent running from Week 2? Raise your hand or type 'yes' in chat.

[Gauge response]

Good. We need that foundation because today we're building on it. By the end of this session, your agent will have access to a much richer toolkit."

[Transition: Click to next slide]

---

## SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Week 2 Recap |
| 3-13 min | Segment 1 | Advanced MCP Architecture |
| 13-25 min | Segment 2 | Multi-Server Configuration |
| 25-37 min | Segment 3 | Tool Chaining Patterns |
| 37-45 min | Segment 4 | Production + Security |

**Graphic:** Timeline showing session flow with green accent colors

**SPEAKER NOTES:**

"Here's our roadmap for today:

First, MCP architecture in the agent context - understanding how agents connect to multiple servers.

Then, practical configuration - how to set up multiple servers and test them.

Tool chaining patterns - this is where power comes from. Connecting tools together.

We close with production principles and security - essential for real-world deployment.

Let's dive in."

[Transition]

---

## SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Configure multiple MCP servers**
   - Expand your agent's capabilities

2. **Understand server types**
   - Data, Action, Integration servers

3. **Implement tool chaining patterns**
   - Sequential, conditional, parallel

4. **Apply security best practices**
   - Least privilege, token management

**Graphic:** Checklist visual with green checkboxes

**SPEAKER NOTES:**

"Four objectives for today.

[Read each]

By the end, your agent will be able to use multiple tools, chain them together for complex tasks, and do so securely.

Your homework this week is configuring 3+ tools and implementing at least one tool chain.

Let's start with the architecture."

[Transition: Click to Segment 1]

---

## SEGMENT 1: ADVANCED MCP ARCHITECTURE
### Duration: 10 minutes | Slides 4-8

---

## SLIDE 4: MCP IN AGENT CONTEXT

**Title:** One Agent, Many Tools

**Content:**

```
Agent (Claude) ← MCP Protocol → Server 1 (Files)
                              → Server 2 (GitHub)
                              → Server 3 (Database)
                              → Server 4 (API)
```

**What MCP Enables:**
- Read files, search web, query databases
- Send emails, create documents, post to Slack
- Interact with GitHub, Google Drive, Notion

**Key Insight:**
> "Without MCP, your agent only processes text. With MCP, it can interact with the world."

**Graphic:** Hub-and-spoke diagram with agent at center, servers around it

**GRAPHICS:**

**Graphic 1: Agent-Centric MCP Architecture**
- Purpose: Visualize how a single agent connects to multiple MCP servers simultaneously
- Type: Hub-and-spoke network diagram
- Elements: Central agent node; multiple server nodes in orbit; connection lines representing MCP protocol
- Labels:
  - Center hub: "AGENT (Claude)" with brain/processor icon
  - Spoke 1: "Filesystem Server" - folder icon - "Read/write local files"
  - Spoke 2: "GitHub Server" - git icon - "Repository operations"
  - Spoke 3: "Database Server" - database icon - "SQL queries"
  - Spoke 4: "API Server" - cloud icon - "External service integration"
  - Connection lines: "MCP Protocol" label on each connection
  - Bottom callout: "Without MCP: text only | With MCP: world interaction"
- Relationships: All connections bidirectional; agent as central orchestrator; servers as capability providers; equal distance from center showing peer relationship

**SPEAKER NOTES:**

"[Hook - The power of MCP]"

"Here's the architecture we're working with.

[Point to diagram]

Your agent at the center, connected to multiple servers via MCP protocol. Each server provides different capabilities.

Filesystem server lets you read and write files. GitHub server accesses repositories. Database server runs queries. API server connects to external services.

[Key point]

Without MCP, your agent can only process the text you give it. With MCP, it can interact with the world - read files, search the web, send emails, update databases.

That's a massive capability expansion."

[Transition]

---

## SLIDE 5: SERVER TYPES

**Title:** Three Types of MCP Servers

**Content:**

| Type | Purpose | Examples |
|------|---------|----------|
| **Data Servers** | Read information | Filesystem, Database, Memory |
| **Action Servers** | Perform operations | Email, Slack, Puppeteer |
| **Integration Servers** | Connect platforms | GitHub, Google Drive, Notion |

**Selection Strategy:**
1. What data does my agent need to READ?
2. What actions must my agent TAKE?
3. What systems must my agent INTEGRATE with?

**Graphic:** Three-column visual with icons for each server type

**GRAPHICS:**

**Graphic 1: Three Types of MCP Servers**
- Purpose: Categorize MCP servers by primary function to guide server selection
- Type: Three-column comparison chart
- Elements: Three distinct columns with headers, icons, examples, and use cases
- Labels:
  - Column 1 - DATA SERVERS (blue icon: database/folder):
    - "Purpose: Read information"
    - Examples: "Filesystem, PostgreSQL, SQLite, Memory"
    - Use case: "When agent needs to READ data"
  - Column 2 - ACTION SERVERS (green icon: lightning bolt/action):
    - "Purpose: Perform operations"
    - Examples: "Email, Slack, Puppeteer, Document creation"
    - Use case: "When agent needs to TAKE ACTION"
  - Column 3 - INTEGRATION SERVERS (orange icon: link/connector):
    - "Purpose: Connect platforms"
    - Examples: "GitHub, Google Drive, Notion, Jira"
    - Use case: "When agent needs PLATFORM INTEGRATION"
  - Bottom section: "Selection Questions"
    - "What data to READ? → Data servers"
    - "What actions to TAKE? → Action servers"
    - "What systems to INTEGRATE? → Integration servers"
- Relationships: Three mutually exclusive categories; clear functional separation; selection strategy maps to categories

**SPEAKER NOTES:**

"Servers fall into three categories.

[Point to each]

Data servers read information. Filesystem reads local files. Database runs queries. Memory stores and retrieves data.

Action servers perform operations. Email sends messages. Slack posts to channels. Puppeteer controls a browser.

Integration servers connect to platforms. GitHub for repositories. Google Drive for documents. Notion for workspaces.

[Point to selection strategy]

When choosing servers, ask these three questions: What does my agent need to read? What actions must it take? What systems must it integrate with?

Answer those, and you know which servers you need."

[Transition]

---

## SLIDE 6: TOOL DISCOVERY

**Title:** How Agents Find Tools

**Content:**

**Tool Discovery:**
- Agents can list available tools automatically
- Tool descriptions guide agent decisions
- Dynamic selection based on task needs

**What Agents See:**
```
Available tools:
- filesystem_read: Read content from a file
- filesystem_write: Write content to a file
- github_list_repos: List repositories
- github_read_file: Read file from repository
```

**Graphic:** Agent interface showing tool list

**SPEAKER NOTES:**

"Once servers are configured, agents discover their tools automatically.

[Point to tool list]

The agent sees what's available. Each tool has a description. When the agent needs to do something, it reads these descriptions and picks the right tool.

This is why tool descriptions matter. If the description is vague, the agent might pick wrong. If it's clear, the agent selects appropriately.

[Key insight]

You don't need to tell the agent which tool to use every time. It selects based on the task and tool descriptions."

[Transition]

---

## SLIDE 7: RESOURCE EXPOSURE

**Title:** Beyond Tools: Resources

**Content:**

**MCP Also Provides Resources:**

| Resource Type | What It Is | Example |
|---------------|------------|---------|
| **Static** | Files, configs | Templates, style guides |
| **Dynamic** | Search results, API data | Query results, live data |

**Context Injection:**
- Resources can be injected into agent context
- Provides background without explicit tool calls
- Reduces token usage for common data

**Graphic:** Resource flowing into agent context

**SPEAKER NOTES:**

"MCP isn't just tools - it also provides resources.

[Explain types]

Static resources are fixed content - templates, configuration files, style guides. Dynamic resources change - search results, API responses, live data.

[Context injection]

Resources can be injected into agent context automatically. Instead of the agent calling a tool to read your company style guide every time, it's just... there.

This reduces tool calls and token usage for commonly needed information."

[Transition]

---

## SLIDE 8: ARCHITECTURE SUMMARY

**Title:** Putting It Together

**Content:**

**Your Agent Architecture:**

```
┌─────────────────────────────────────────┐
│                 AGENT                   │
│  (System Prompt + Context + Reasoning)  │
└─────────────────┬───────────────────────┘
                  │ MCP Protocol
    ┌─────────────┼─────────────┐
    ↓             ↓             ↓
┌───────┐   ┌───────┐   ┌───────┐
│ Data  │   │Action │   │Integr.│
│Server │   │Server │   │Server │
└───────┘   └───────┘   └───────┘
```

**Key Takeaway:**
One agent can leverage many specialized servers through a single protocol.

**Graphic:** Layered architecture diagram

**GRAPHICS:**

**Graphic 1: Complete Agent-MCP Stack**
- Purpose: Show the layered architecture from agent through protocol to specialized servers
- Type: Layered architecture diagram (vertical stack)
- Elements: Three distinct layers with clear separation and connection points
- Labels:
  - Top layer: "AGENT LAYER"
    - Box containing: "Agent (System Prompt + Context + Reasoning)"
    - Capabilities: "Decision-making, Tool selection, Task planning"
  - Middle layer: "PROTOCOL LAYER"
    - Box containing: "MCP (Model Context Protocol)"
    - Functions: "Standardized communication, Tool discovery, Resource management"
  - Bottom layer: "SERVER LAYER"
    - Three boxes side-by-side:
      - "Data Servers" (Filesystem, DB)
      - "Action Servers" (Email, Slack)
      - "Integration Servers" (GitHub, Drive)
  - Connections: Bidirectional arrows between layers
- Relationships: Top-down architecture; single agent, single protocol, multiple servers; MCP abstracts server diversity; one-to-many relationship

**SPEAKER NOTES:**

"Here's the complete picture.

[Walk through]

Your agent at the top - system prompt, context, reasoning capability. MCP protocol connects it to multiple servers. Each server provides specialized capabilities.

[Key takeaway]

One agent, many servers, one protocol. MCP standardizes how all these connections work. You don't need custom integration for each tool - MCP handles it.

Now let's get practical with configuration."

[Transition: Click to Segment 2]

---

## SEGMENT 2: MULTI-SERVER CONFIGURATION
### Duration: 12 minutes | Slides 9-13

---

## SLIDE 9: CONFIGURATION STRUCTURE

**Title:** The Config File

**Content:**

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path"],
      "env": {}
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "${GITHUB_TOKEN}"
      }
    },
    "slack": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-slack"],
      "env": {
        "SLACK_BOT_TOKEN": "${SLACK_TOKEN}"
      }
    }
  }
}
```

**Graphic:** Config file with annotations

**GRAPHICS:**

**Graphic 1: Annotated Multi-Server Configuration**
- Purpose: Explain the structure and key elements of a production MCP configuration file
- Type: Annotated code block
- Elements: JSON configuration with callout annotations pointing to key sections
- Labels:
  - Main structure: `mcpServers` object
  - Annotation 1 pointing to "filesystem": "Server name (your choice)"
  - Annotation 2 pointing to "command": "Always 'npx' for npm packages"
  - Annotation 3 pointing to "args": "Server package + optional parameters"
  - Annotation 4 pointing to filesystem path: "Restricts access to this directory only"
  - Annotation 5 pointing to "env": "Environment variables for this server"
  - Annotation 6 pointing to "${GITHUB_TOKEN}": "Pulls from environment - NEVER hardcode tokens"
  - Security callout: "Credentials use ${VAR} syntax - resolved at runtime"
- Relationships: Hierarchical JSON structure; each server independently configured; environment variable pattern prevents credential leaks

**SPEAKER NOTES:**

"Here's what a multi-server config looks like.

[Walk through structure]

mcpServers object contains all your servers. Each server has a name - filesystem, github, slack.

Each server has command (usually npx), args (the server package and options), and env (environment variables).

[Point to env vars]

Notice tokens use ${VAR_NAME} syntax. That pulls from your environment - don't put actual tokens in the config file!"

[Transition]

---

## SLIDE 10: SERVER SELECTION STRATEGY

**Title:** Which Servers Do You Need?

**Content:**

**Three Questions:**

1. **What DATA does my agent need to read?**
   → Filesystem, Database, Memory servers

2. **What ACTIONS must my agent take?**
   → Email, Slack, Puppeteer servers

3. **What SYSTEMS must my agent integrate with?**
   → GitHub, Google Drive, Notion servers

**Start Small:**
- Begin with 2-3 essential servers
- Add as needs become clear
- Test each independently

**Graphic:** Decision tree for server selection

**GRAPHICS:**

**Graphic 1: Server Selection Decision Tree**
- Purpose: Guide practitioners through systematic server selection based on agent needs
- Type: Decision tree flowchart
- Elements: Root question branching into three main categories, then specific server recommendations
- Labels:
  - Root: "What does my agent need to do?"
  - Branch 1: "READ DATA?"
    - "Local files?" → "Filesystem server"
    - "Database queries?" → "PostgreSQL/SQLite server"
    - "Store/retrieve info?" → "Memory server"
  - Branch 2: "TAKE ACTIONS?"
    - "Send notifications?" → "Email/Slack server"
    - "Automate browser?" → "Puppeteer server"
    - "Create documents?" → "Document server"
  - Branch 3: "INTEGRATE SYSTEMS?"
    - "Code repositories?" → "GitHub server"
    - "Cloud storage?" → "Google Drive server"
    - "Project management?" → "Notion/Jira server"
  - Bottom advice: "Start with 2-3 essential servers, add more as needs emerge"
- Relationships: Top-down decision flow; questions lead to specific recommendations; emphasis on starting small

**SPEAKER NOTES:**

"Don't configure every server in the registry. Start with what you need.

[Walk through questions]

What data? If you need local files, add filesystem. If database queries, add postgres or sqlite.

What actions? If sending emails, add email server. If posting to Slack, add slack server.

What integrations? If working with GitHub repos, add github server. If Google Docs, add drive server.

[Key advice]

Start with 2-3 essential servers. Add more as needs become clear. Test each one independently before combining."

[Transition]

---

## SLIDE 11: DEPENDENCY MANAGEMENT

**Title:** Server Dependencies

**Content:**

**Some Servers Need Others:**
```
GitHub Server → Requires valid token
Database Server → Requires running database
Custom API Server → May require auth server
```

**Order Matters:**
- Configure dependencies first
- Verify credentials before use
- Test in isolation

**Credential Coordination:**
- Use environment variables
- Never hardcode tokens
- Rotate regularly

**Graphic:** Dependency diagram showing connections

**GRAPHICS:**

**Graphic 1: Server Dependency Chain**
- Purpose: Illustrate dependencies between servers and their prerequisites
- Type: Dependency graph with prerequisites
- Elements: Server nodes with arrows showing dependencies and prerequisites
- Labels:
  - Foundation layer: "Prerequisites"
    - "Valid GitHub token" node
    - "Running PostgreSQL instance" node
    - "Environment variables configured" node
  - Server layer: "MCP Servers"
    - "GitHub Server" (depends on token)
    - "PostgreSQL Server" (depends on running instance)
    - "Custom API Server" (depends on env vars)
  - Dependency arrows labeled: "requires", "needs", "depends on"
  - Testing order annotation: "1. Verify prerequisites → 2. Test individual servers → 3. Combine"
- Relationships: Prerequisites must exist before servers; upward dependencies showing what each server needs; testing sequence follows dependency chain

**SPEAKER NOTES:**

"Not all servers are independent.

[Explain dependencies]

GitHub server needs a valid token. Database server needs a running database to connect to. Custom API servers might need authentication configured first.

[Order matters]

When testing, verify the foundations first. Is your token valid? Is the database running? Then test the servers that depend on them.

[Credentials]

Always use environment variables. Never hardcode tokens in your config. Rotate credentials regularly.

This prevents embarrassing security incidents."

[Transition]

---

## SLIDE 12: CONFIG FILE LOCATIONS

**Title:** Where to Configure

**Content:**

**Claude Desktop Config Location:**

| OS | Path |
|----|------|
| **Mac** | `~/Library/Application Support/Claude/claude_desktop_config.json` |
| **Windows** | `%APPDATA%\Claude\claude_desktop_config.json` |

**After Editing:**
1. Save the config file
2. Restart Claude Desktop completely
3. Verify tools appear in interface

**Troubleshooting:**
- Check JSON syntax (missing comma is common)
- Verify paths exist
- Confirm env variables are set

**Graphic:** File path icons for each OS

**SPEAKER NOTES:**

"Here's where to put your config.

[Point to paths]

Mac users: Library/Application Support/Claude folder. Windows: APPDATA/Claude folder.

[After editing]

After you save the config, you MUST restart Claude Desktop. It doesn't hot-reload. Close it completely and reopen.

[Troubleshooting]

If things don't work: Check JSON syntax - missing commas break everything. Verify paths actually exist. Make sure environment variables are set in your shell."

[Transition]

---

## SLIDE 13: VERIFICATION PROCESS

**Title:** Test Before You Trust

**Content:**

**Verification Steps:**

1. **Configure one server**
2. **Restart Claude Desktop**
3. **Test with simple prompt**
   - "List the tools you have available"
   - "Read the file at [path]"
4. **Verify expected result**
5. **Add next server, repeat**

**Common Issues:**

| Issue | Solution |
|-------|----------|
| "Tool not found" | Restart Claude Desktop |
| "Permission denied" | Check token/path permissions |
| "Invalid JSON" | Validate syntax |

**Graphic:** Verification checklist flowchart

**GRAPHICS:**

**Graphic 1: MCP Server Verification Flow**
- Purpose: Provide step-by-step verification process to ensure servers are working correctly
- Type: Sequential flowchart with decision points
- Elements: Process boxes, decision diamonds, success/failure paths
- Labels:
  - Step 1: "Configure ONE server in config file"
  - Step 2: "Restart Claude Desktop completely"
  - Step 3: "Test with simple prompt" (Example: "List your available tools")
  - Decision: "Tool appears?"
    - YES path: "Test functionality" → "Works correctly?"
      - YES → "Server verified ✓" → "Add next server, repeat"
      - NO → "Check permissions/credentials" → Loop back to Step 1
    - NO path: "Common issues?"
      - "Restart again" → Loop to Step 2
      - "Check JSON syntax" → Loop to Step 1
      - "Verify paths exist" → Loop to Step 1
  - Side panel: "Common Issues → Solutions"
    - "Tool not found → Restart Claude"
    - "Permission denied → Check token/paths"
    - "Invalid JSON → Validate syntax"
- Relationships: Iterative testing process; one server at a time; decision points for troubleshooting; emphasis on systematic approach

**SPEAKER NOTES:**

"Don't configure everything at once and hope it works.

[Walk through process]

Configure one server. Restart Claude. Test with a simple prompt - 'list your tools' or 'read this file.' Verify it works. Then add the next server.

[Common issues]

Tool not found usually means you didn't restart. Permission denied is usually wrong token or path restrictions. Invalid JSON means check your syntax - online JSON validators help.

[Key point]

Test each server independently before combining. Debugging multiple broken servers at once is painful."

[Transition: Click to Segment 3]

---

## SEGMENT 3: TOOL CHAINING PATTERNS
### Duration: 12 minutes | Slides 14-19

---

## SLIDE 14: WHY CHAIN TOOLS?

**Title:** The Power of Combination

**Content:**

**Single Tool:**
- Read a file
- Search the web
- Send an email

**Chained Tools:**
- Search web → Read file → Write summary → Email result

**The Difference:**
- Single tools do one thing
- Chained tools accomplish complex tasks
- Agent decides what to chain based on goal

**Graphic:** Single tool vs. chain comparison

**GRAPHICS:**

**Graphic 1: Single Tool vs. Tool Chain Comparison**
- Purpose: Illustrate the power multiplication that comes from chaining tools together
- Type: Side-by-side before/after comparison
- Elements: Left side shows isolated tools; right side shows connected chain
- Labels:
  - Left side: "SINGLE TOOLS (Limited)"
    - Individual boxes: "Read file", "Search web", "Send email" (disconnected)
    - Capability: "Each does one thing"
    - Example outcome: "File contents" OR "Search results" OR "Email sent"
  - Right side: "CHAINED TOOLS (Powerful)"
    - Connected sequence: "Search web" → "Read file" → "Write summary" → "Email result"
    - Capability: "Combined to accomplish complex task"
    - Example outcome: "Researched, synthesized, delivered report"
  - Center divider: "→ CHAINING CREATES VALUE →"
  - Bottom emphasis: "Agent decides what to chain based on goal"
- Relationships: Contrast isolated vs. integrated; show data flowing through chain; emphasize emergent capabilities from combination

**SPEAKER NOTES:**

"[Hook - Why chaining matters]"

"Single tools are useful but limited. Read a file - great. Search the web - useful. Send an email - helpful.

Chaining creates power.

[Point to chain]

Search the web for information. Read a local file for context. Write a summary combining both. Email the result to stakeholders.

That's four tools working together to accomplish something none could do alone.

[Key point]

Your agent decides what to chain based on the goal. You define the patterns; the agent applies them."

[Transition]

---

## SLIDE 15: SEQUENTIAL CHAINING

**Title:** Pattern 1: Sequential

**Content:**

```
Search files → Read file → Extract data → Write to database
```

**Characteristics:**
- Each output feeds the next input
- Clear data transformation path
- Failure stops the chain (or triggers recovery)

**Example:**
```
"Find all .md files" → [list of files]
"Read each file" → [file contents]
"Extract headings" → [heading list]
"Write to index.json" → [done]
```

**Graphic:** Linear flow diagram with arrows

**GRAPHICS:**

**Graphic 1: Sequential Tool Chaining Pattern**
- Purpose: Show how output from one tool becomes input to the next in a linear chain
- Type: Linear flow diagram with data transformation
- Elements: Sequential tool boxes with data flow arrows and transformation labels
- Labels:
  - Tool 1: "Search files"
    - Output: [list of .md files]
  - Arrow: "List becomes input →"
  - Tool 2: "Read each file"
    - Output: [file contents]
  - Arrow: "Contents become input →"
  - Tool 3: "Extract headings"
    - Output: [heading list]
  - Arrow: "Headings become input →"
  - Tool 4: "Write to index.json"
    - Output: [index file created]
  - Characteristics box:
    - "Each output feeds next input"
    - "Clear data transformation path"
    - "Failure stops chain (or triggers recovery)"
  - Bottom note: "Execute in ORDER - sequence matters"
- Relationships: Strict sequential dependency; data transformation at each step; linear progression; failure propagation shown

**SPEAKER NOTES:**

"Sequential chaining is the most common pattern.

[Walk through]

Step 1 output becomes step 2 input. Step 2 output becomes step 3 input. Linear progression.

[Point to example]

Find markdown files - get a list. Read each one - get contents. Extract headings - get a summary. Write to index - create the deliverable.

[Key point]

Each step transforms data. The chain only makes sense in order. Failure at any step needs handling - retry, skip, or stop."

[Transition]

---

## SLIDE 16: CONDITIONAL CHAINING

**Title:** Pattern 2: Conditional

**Content:**

```
Check condition → IF true: Tool A → Tool B
                → IF false: Tool C → Tool D
```

**Characteristics:**
- Agent decides path based on results
- Dynamic flow control
- Handles variations gracefully

**Example:**
```
"Does config.json exist?"
  → IF yes: Read it → Use settings
  → IF no: Create it → Use defaults
```

**Graphic:** Branching flow diagram

**GRAPHICS:**

**Graphic 1: Conditional Tool Chaining Pattern**
- Purpose: Illustrate how agents make dynamic decisions to choose different tool paths
- Type: Branching flow diagram with decision logic
- Elements: Decision diamond with two distinct paths; tools on each branch
- Labels:
  - Start: "Agent receives task"
  - Decision diamond: "Does config.json exist?"
  - TRUE branch (green):
    - Tool: "Read config.json"
    - Tool: "Use settings from file"
    - Outcome: "Configured with user preferences"
  - FALSE branch (orange):
    - Tool: "Create config.json with defaults"
    - Tool: "Use default settings"
    - Outcome: "Configured with defaults"
  - Both paths converge: "Continue with task"
  - Characteristics box:
    - "Agent decides path based on results"
    - "Dynamic flow control"
    - "Handles variations gracefully"
- Relationships: Branching based on condition; agent makes intelligent choice; different paths achieve same goal; paths reconverge

**SPEAKER NOTES:**

"Conditional chaining adds intelligence.

[Explain pattern]

Agent checks something, then chooses a path based on the result. Different conditions lead to different tool sequences.

[Point to example]

Does the config file exist? If yes, read it and use those settings. If no, create one with defaults.

[Key point]

This is where agent reasoning shines. It's not following a fixed script - it's adapting to what it finds."

[Transition]

---

## SLIDE 17: PARALLEL TOOL USE

**Title:** Pattern 3: Parallel

**Content:**

```
Start →┬→ Search Web ──────┬→ Combine → Output
       ├→ Search Files ────┤
       └→ Query Database ──┘
```

**Characteristics:**
- Multiple tools simultaneously
- Results aggregated
- Faster than sequential for independent data

**When to Use:**
- Gathering from multiple sources
- Comparing alternatives
- Building comprehensive views

**Graphic:** Parallel flow diagram with merge point

**GRAPHICS:**

**Graphic 1: Parallel Tool Use Pattern**
- Purpose: Show how multiple tools can execute simultaneously and results combined
- Type: Parallel flow diagram with merge/aggregation point
- Elements: Start point splitting into parallel paths; merge point combining results
- Labels:
  - Start: "Research task begins"
  - Split point: "Query multiple sources simultaneously"
  - Parallel path 1: "Search Web" → [web results]
  - Parallel path 2: "Search Files" → [local results]
  - Parallel path 3: "Query Database" → [DB results]
  - Merge point: "Combine & Synthesize"
    - Aggregation logic: "Merge results, deduplicate, rank relevance"
  - Output: "Comprehensive answer from all sources"
  - Characteristics box:
    - "Multiple tools simultaneously"
    - "Results aggregated"
    - "Faster than sequential for independent data"
  - Side note: "Use when data sources are independent"
- Relationships: Parallel execution (no dependencies between paths); convergence at merge point; aggregation logic required; handle partial results if one path fails

**SPEAKER NOTES:**

"Parallel chaining is for when you need multiple independent things.

[Explain pattern]

Start multiple tools at once. They run in parallel. Results come back, get combined into final output.

[When to use]

Gathering information from web AND files AND database. Comparing options from different sources. Building a comprehensive view from multiple inputs.

[Key point]

This is faster than sequential when data sources are independent. But it's more complex to implement - you need to handle partial results if one source fails."

[Transition]

---

## SLIDE 18: IMPLEMENTATION TIPS

**Title:** Making Chains Work

**Content:**

**Key Practices:**

1. **Clear handoff prompts**
   - Tell agent what to do with each result
   - "Use this list to..."

2. **Validate between steps**
   - Check output format before next step
   - Handle missing or malformed data

3. **Handle partial failures**
   - One tool failing shouldn't crash the chain
   - Graceful degradation

**System Prompt Pattern:**
```markdown
When [task], follow this sequence:
1. First, [tool A] to get [data]
2. Then, [tool B] using that [data]
3. Finally, [tool C] to produce [output]
Report progress at each step.
```

**Graphic:** Chain with validation checkpoints

**GRAPHICS:**

**Graphic 1: Tool Chain with Validation Checkpoints**
- Purpose: Show best practices for robust tool chaining with validation between steps
- Type: Flow diagram with validation gates
- Elements: Tool sequence with checkpoint diamonds between each step
- Labels:
  - Tool 1: "Tool A - Get data"
  - Checkpoint 1: "Validate output format" (diamond)
    - PASS → Continue
    - FAIL → "Handle error (retry/fallback/escalate)"
  - Tool 2: "Tool B - Transform data"
  - Checkpoint 2: "Validate transformation" (diamond)
    - PASS → Continue
    - FAIL → "Handle error"
  - Tool 3: "Tool C - Deliver result"
  - Final validation: "Verify complete"
  - Best practices box:
    - "✓ Clear handoff prompts between tools"
    - "✓ Validate output before next step"
    - "✓ Handle partial failures gracefully"
    - "✓ Report progress at each step"
- Relationships: Validation gates prevent error propagation; early detection of issues; graceful degradation on partial failures; progress tracking throughout chain

**SPEAKER NOTES:**

"Chains don't work automatically. You need to design them.

[Walk through practices]

Clear handoff prompts. Don't assume the agent knows what to do with each result. Tell it: 'Use this list to...'

Validate between steps. Tool A returned something - is it what you expected? Check before passing to Tool B.

Handle partial failures. If Tool B fails, don't crash. Maybe Tool A's result is still useful. Degrade gracefully.

[Point to pattern]

Include chain instructions in your system prompt. Make the sequence explicit."

[Transition]

---

## SLIDE 19: CHAIN EXAMPLE

**Title:** Real Example: Research Chain

**Content:**

**Task:** Research and summarize a topic

**Chain:**
```
[Web Search] → search results
     ↓
[Read Context File] → background info
     ↓
[Combine & Analyze] → synthesis
     ↓
[Write Summary] → output file
```

**System Prompt:**
```markdown
When asked to research a topic:
1. Search the web for current information
2. Read /context/background.md for context
3. Combine sources into coherent analysis
4. Save summary to /output/summary.md
```

**Graphic:** Complete chain with data flow

**GRAPHICS:**

**Graphic 1: Complete Research Chain Example**
- Purpose: Provide concrete end-to-end example of tool chaining for a research task
- Type: Detailed flow diagram with data annotations
- Elements: Four-step chain with data flowing through each stage
- Labels:
  - Input: "User asks: 'Research AI agents and summarize'"
  - Step 1: "Web Search Tool"
    - Action: "Search for 'AI agents 2025 best practices'"
    - Output data: [5 relevant articles with URLs]
  - Step 2: "Filesystem Read Tool"
    - Action: "Read /context/background.md"
    - Output data: [Company standards, writing style, focus areas]
  - Step 3: "Analysis (Agent Reasoning)"
    - Action: "Combine web sources + internal context"
    - Output data: [Synthesized analysis matching company style]
  - Step 4: "Filesystem Write Tool"
    - Action: "Write to /output/ai-agents-summary.md"
    - Output data: [Saved file with comprehensive summary]
  - Final result: "Deliverable: Research summary in company format"
  - System prompt snippet shown: "When researching: 1. Search web, 2. Read context, 3. Synthesize, 4. Save output"
- Relationships: Sequential with clear data transformation; external + internal data combined; reasoning step synthesizes; output matches specifications

**SPEAKER NOTES:**

"Here's a concrete example.

[Walk through]

User asks to research a topic. Agent searches the web - gets current information. Reads background file - gets context. Combines both into analysis. Writes the summary.

[Point to system prompt]

This is in the system prompt. The agent knows the pattern. When asked to research, it follows this sequence.

[Key point]

You design the chain. The agent executes it. Each step uses the appropriate tool."

[Transition: Click to Segment 4]

---

## SEGMENT 4: PRODUCTION + SECURITY
### Duration: 8 minutes | Slides 20-23

---

## SLIDE 20: 12-FACTOR AGENT PRINCIPLES

**Title:** Production Agent Principles

**Content:**

**Five Key Principles:**

| # | Principle | Meaning |
|---|-----------|---------|
| 1 | **Own Your Prompts** | Treat prompts as code, not framework magic |
| 2 | **Own Your Context Window** | Curate ruthlessly - less is often more |
| 3 | **Tools Are Structured Outputs** | LLM emits JSON; you decide what to do |
| 4 | **Small, Focused Agents** | 3-20 step workflows; smaller = better |
| 5 | **Stateless Reducer** | `(state, event) → state` for testing |

**Graphic:** Numbered list with icons

**SPEAKER NOTES:**

"Production agents follow these principles.

[Walk through key ones]

Own your prompts - you write them, you version them, you control them. Not hidden in some framework.

Own your context window - more context isn't better. Curate ruthlessly. Include only what's needed.

Tools are structured outputs - the LLM emits JSON describing what to do. YOUR code decides whether to actually do it.

Small, focused agents - 3 to 20 steps is the sweet spot. Smaller agents perform better.

[Key insight]

These principles make agents debuggable and maintainable. Not black boxes."

[Transition]

---

## SLIDE 21: SECURITY PRINCIPLES

**Title:** MCP Security Essentials

**Content:**

| Principle | Implementation |
|-----------|----------------|
| **Least Privilege** | Only enable servers you need |
| **Token Management** | Env vars, never hardcode, rotate |
| **Data Boundaries** | Restrict filesystem to specific dirs |
| **Audit Logging** | Log every tool call |

**Example - Filesystem Restriction:**
```json
"args": ["-y", "@modelcontextprotocol/server-filesystem", "/projects/agent"]
```
Only `/projects/agent` is accessible - not entire filesystem.

**Graphic:** Security shield with principles

**GRAPHICS:**

**Graphic 1: MCP Security Principles Shield**
- Purpose: Visualize the four critical security principles for production MCP deployments
- Type: Shield diagram with four quadrants
- Elements: Shield shape divided into four sections; each section represents a principle
- Labels:
  - Top-left quadrant: "LEAST PRIVILEGE" (lock icon)
    - "Only enable servers you need"
    - "Minimize attack surface"
    - Example: "Don't add email if agent doesn't send mail"
  - Top-right quadrant: "TOKEN MANAGEMENT" (key icon)
    - "Environment variables only"
    - "Never hardcode credentials"
    - "Rotate tokens regularly"
  - Bottom-left quadrant: "DATA BOUNDARIES" (fence icon)
    - "Restrict filesystem to specific directories"
    - "Limit database access scopes"
    - Example: `/projects/agent` only, not entire filesystem
  - Bottom-right quadrant: "AUDIT LOGGING" (clipboard icon)
    - "Log every tool call"
    - "Track who, what, when"
    - "Monitor for unusual patterns"
  - Shield center: "PRODUCTION-READY MCP"
  - Bottom banner: "All four required for secure deployment"
- Relationships: Four equal pillars of security; all must be implemented; defensive layers; production requirement not optional

**SPEAKER NOTES:**

"MCP gives agents real power. Power requires security.

[Walk through principles]

Least privilege - don't add email server if your agent doesn't need to send email. Each server is attack surface.

Token management - environment variables, never in config. Rotate tokens regularly.

Data boundaries - restrict filesystem access. That path in the args? The agent can ONLY see that directory.

Audit logging - log every tool call. Know what your agent did.

[Point to example]

This filesystem config only allows access to /projects/agent. The agent can't read /etc/passwd or your SSH keys."

[Transition]

---

## SLIDE 22: BEST PRACTICES

**Title:** MCP Best Practices

**Content:**

**Configuration:**
- [ ] Test each server independently
- [ ] Document all configurations
- [ ] Version control your config files
- [ ] Use environment variables for secrets

**Operation:**
- [ ] Monitor for unusual patterns
- [ ] Set up alerts for high error rates
- [ ] Review tool usage logs regularly
- [ ] Rotate tokens on schedule

**Treat MCP config like code:**
- Versioned
- Tested
- Documented
- Reviewed

**Graphic:** Checklist with categories

**SPEAKER NOTES:**

"Best practices for MCP in production.

[Configuration]

Test independently. Document everything. Version control - your config should be in git. Environment variables for all secrets.

[Operation]

Monitor patterns - is your agent making unusual tool calls? Alert on high error rates. Review logs regularly. Rotate tokens on a schedule.

[Key insight]

Treat your MCP config like code. It should be versioned, tested, documented, and reviewed. Not thrown together and forgotten."

[Transition]

---

## SLIDE 23: SECURITY CHECKLIST

**Title:** Before You Deploy

**Content:**

**Security Checklist:**

- [ ] All credentials in environment variables
- [ ] Filesystem access restricted to needed directories
- [ ] GitHub token has minimum required scopes
- [ ] Token rotation schedule defined
- [ ] Tool usage logging enabled
- [ ] No sensitive data in prompts
- [ ] Error messages don't leak credentials

**If You Can Answer "Yes" to All:**
You're ready for production use.

**Graphic:** Security checklist with lock icon

**SPEAKER NOTES:**

"Before you deploy, run through this checklist.

[Read through items]

Credentials in env vars - check. Filesystem restricted - check. Minimum token scopes - check. Rotation schedule - check. Logging - check. No sensitive data in prompts - check. Safe error messages - check.

[Key point]

If you can't answer yes to all of these, fix that before deploying. Security isn't optional for production agents."

[Transition: Click to Closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 24-25

---

## SLIDE 24: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| 3.1: Multi-Server Config | 25 min | Working config + verification | Server setup |
| 3.2: Tool Prompts | 25 min | Tool guide + updated prompt | Tool guidance |
| 3.3: Tool Chaining | 25 min | Chain design + test results | Combining tools |
| **Total** | **75 min** | | |

**Target:** Agent using 3+ MCP tools effectively

**Graphic:** Exercise progression diagram

**SPEAKER NOTES:**

"Your homework for this week.

[Walk through exercises]

Exercise 3.1 - configure multiple servers. 25 minutes. Identify what you need, configure it, verify it works.

Exercise 3.2 - tool prompts. 25 minutes. Document when to use each tool, update your system prompt.

Exercise 3.3 - tool chaining. 25 minutes. Design and test at least one tool chain.

[Target]

By end of week, your agent should be using 3+ tools effectively. That's the foundation for multi-step agents next week."

[Transition]

---

## SLIDE 25: NEXT WEEK PREVIEW

**Title:** Next Week: Multi-Step Agents

**Content:**

**Preview:**
Week 4 covers complex task decomposition, state management across steps, and checkpoint/resume capabilities.

**What to Complete Before Then:**
- [ ] Exercise 3.1: Multi-Server Configuration
- [ ] Exercise 3.2: Tool Prompts Development
- [ ] Exercise 3.3: Tool Chaining Implementation
- [ ] Agent using 3+ tools successfully

**Key Preparation:**
Multi-tool agent must be working - we'll be adding planning and state management.

**Graphic:** Preview showing multi-step agent diagram

**SPEAKER NOTES:**

"Next week is Multi-Step Agents.

We'll cover complex task decomposition - breaking big tasks into steps. State management - tracking progress across steps. Checkpoint and resume - recovering from failures mid-task.

[Requirements]

Your multi-tool agent needs to work before Week 4. We'll be building planning and state management on top of it.

[Final close]

Great session today. MCP opens up what your agent can do. Tool chaining creates real power.

Questions before we wrap?

[Handle questions]

Good work. See you next week!"

---

## Appendix: Slide Design Notes

### Block 3 Color Scheme

| Element | Color | Hex Code |
|---------|-------|----------|
| Primary | Green | #00CC99 |
| Accent | Teal | #008B8B |
| Background | White | #FFFFFF |
| Text | Dark Gray | #333333 |

### Graphic Suggestions by Slide

| Slide | Graphic Type | Description |
|-------|-------------|-------------|
| 1 | Title | Connected servers visual |
| 4 | Architecture | Hub-and-spoke diagram |
| 5 | Categories | Three-column server types |
| 9 | Code | Annotated config file |
| 15-17 | Flow | Chain pattern diagrams |
| 21 | Security | Shield with principles |

### Animation Notes

- Code blocks: Highlight key sections
- Flow diagrams: Animate step by step
- Checklists: Reveal item by item
- Keep animations subtle - content is technical

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |
