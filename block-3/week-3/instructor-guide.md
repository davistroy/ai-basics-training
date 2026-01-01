# **INSTRUCTOR GUIDE: BLOCK 3 WEEK 3**
## **MCP Deep Dive**

**Block:** 3: AI Automation Architecture
**Week:** 3 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Advanced MCP architecture, multi-server configuration, and tool chaining |
| **Difficulty Level** | High |
| **Prep Time Required** | 60 minutes |
| **Demo Required** | Yes - Multi-server MCP configuration and tool chaining |
| **Tech Setup Needed** | Claude Desktop with multiple MCP servers, tool chain examples |
| **Common Challenges** | MCP configuration errors; understanding server dependencies |

---

## Navigation

**Block Navigation:** [Week 2 Instructor Guide](../week-2/instructor-guide.md) | **Week 3** | [Week 4 Instructor Guide](../week-4/instructor-guide.md)

**Related Materials:**
- [Week 3 Presentation Slides](presentation.md)
- [Week 3 Participant Guide](participant-guide.md)
- [Block 3 Main Document](../block-3.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 3 materials | |
| Test MCP setup | Verify multiple servers work together | |
| Prepare tool chain | Build working example of tool chaining | |
| Check participant progress | Review who has functional agents | |
| Review Week 2 | Check execution logs and error handling | |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test all MCP servers individually | |
| Load presentation | Have slides ready and tested | |
| Test tool chain demo | Run complete chain 3+ times | |
| Prepare config examples | Have sanitized config.json ready to show | |
| Check common errors | Have fixes ready for typical MCP issues | |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, Claude Desktop, config files | |
| Test share | Verify screen sharing works | |
| Load MCP configs | Have servers running and verified | |
| Start recording | If session is recorded | |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Week 2 recap | Check agent status |
| 0:03 | 10 min | Segment 1 | Advanced MCP Architecture | Foundation |
| 0:13 | 12 min | Segment 2 | Multi-Server Configuration | Hands-on |
| 0:25 | 12 min | Segment 3 | Tool Chaining Patterns | Core patterns |
| 0:37 | 8 min | Segment 4 | Production + Security | Best practices |
| 0:45 | - | Closing | Homework preview | |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Reference 12-Factor Principles in guide rather than explaining all 5
- Show one chaining pattern instead of three
- Skip parallel tool use (reference in guide)

**If Running Ahead:**
- More Q&A on specific MCP server configurations
- Extended security discussion
- Discuss participant-specific tool needs

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:13 | Compress server types to key examples |
| End Segment 2 | 0:25 | Skip dependency management details |
| Start Closing | 0:42 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants
2. Quick status check on functional agents
3. Connect Week 2 error handling to tool usage
4. Preview today's session

**Opening Script:**
> "Welcome to Week 3: MCP Deep Dive. This is where we expand your agent's capabilities significantly. Before we dive in - quick check: Who has a functional agent running from Week 2 exercises? Raise your hand or type 'yes' in chat."

[Gauge response]

> "Good. Today we're going to give those agents more tools to work with. We'll cover advanced MCP architecture, how to configure multiple servers, and critical tool chaining patterns. By the end, your agent will have access to a much richer toolkit."

---

### Segment 1: Advanced MCP Architecture (10 minutes)

**Learning Objective:** Understand MCP architecture in the agent context

**Slides:** 3-7

#### Content Delivery

**Key Point 1: MCP in Agent Context**
- Main message: Agent connects to multiple servers, each providing different capabilities
- Visual to emphasize: Architecture diagram showing agent connected to multiple servers
- Key insight: "One agent, many tools - MCP is the protocol that makes this possible"

**Key Point 2: Server Types**
- Main message: Data servers, Action servers, Integration servers
- Framework: Match server type to capability needed
- Examples: Filesystem (data), Email (action), GitHub (integration)

**Key Point 3: Tool Discovery and Resources**
- Main message: Agents can discover available tools and access resources dynamically
- Demonstration: Show how agent sees available tools
- Participant relevance: "Your agent will select tools based on their descriptions"

#### Facilitation Notes

**Watch For:**
- Confusion about what MCP actually does (it's a protocol, not the tools themselves)
- Participants who haven't configured MCP yet

**If Asked About Specific Servers:**
> "Check the MCP Server Registry - there are servers for most common integrations. If you don't see what you need, we can discuss custom approaches in office hours."

**Transition to Segment 2:**
> "Now that we understand the architecture, let's get practical with multi-server configuration."

---

### Segment 2: Configuring Multi-Server Environments (12 minutes)

**Learning Objective:** Configure multiple MCP servers for an agent

**Slides:** 8-12

#### Content Delivery

**Key Point 1: Configuration Architecture**
- Main message: All servers defined in one config file, each with command, args, and environment
- Code example: Show multi-server config.json
- Common mistake: "Don't forget environment variables - tokens and paths must be correct"

**Key Point 2: Server Selection Strategy**
- Main message: Ask three questions - What data? What actions? What integrations?
- Framework: Map agent capabilities to servers needed
- Practice preview: Exercise 3.1 walks through this analysis

**Key Point 3: Dependency Management**
- Main message: Some servers depend on others; order and credentials matter
- Example: "GitHub server needs auth before it can access repos"
- Key insight: "Test each server independently before combining"

#### Demo Instructions

**Demo Duration:** 4 minutes (within segment)

**Setup Required:**
- Claude Desktop config.json ready to show
- 3+ MCP servers configured and working
- Simple test prompts for each server

**Demo Steps:**
1. Show config.json structure (30 sec)
2. Highlight each server configuration (1 min)
3. Restart Claude Desktop to load config (30 sec)
4. Show available tools in Claude (1 min)
5. Quick test of one tool (1 min)

**Backup Plan:**
If config fails:
1. Show pre-captured screenshots
2. Walk through config structure conceptually
3. Offer troubleshooting in support channel

#### Facilitation Notes

**Watch For:**
- OS-specific configuration questions (Windows vs Mac paths)
- Token/credential security concerns

**Transition to Segment 3:**
> "Now we have multiple tools. The power comes from chaining them together."

---

### Segment 3: Tool Chaining Patterns (12 minutes)

**Learning Objective:** Implement tool chaining for complex agent tasks

**Slides:** 13-18

#### Content Delivery

**Key Point 1: Sequential Chaining**
- Main message: Output of one tool feeds input of next
- Pattern: Search → Read → Extract → Write
- Key insight: "Clear data transformation path at each step"

**Key Point 2: Conditional Chaining**
- Main message: Agent decides path based on tool results
- Pattern: Check → IF true: Path A → IF false: Path B
- Real-world application: "If file exists, read it. If not, create it."

**Key Point 3: Parallel Tool Use**
- Main message: Multiple tools simultaneously, results aggregated
- Pattern: Start →┬→ Tool A ─┬→ Combine → Output
- When to use: "When you need multiple independent data sources"

**Key Point 4: Implementation Tips**
- Main message: Validate between steps, handle partial failures
- Framework: "Handoff prompts tell agent what to do with each tool result"
- Common mistake: "Don't assume tool output format - validate first"

#### Facilitation Notes

**Energy Check:**
At this point, participants may be:
- Excited about possibilities (channel into practical application)
- Overwhelmed by options (focus on sequential chaining first)

**Transition to Segment 4:**
> "Tool chaining is powerful. But with power comes responsibility - let's talk about production principles and security."

---

### Segment 4: Production Principles + Security (8 minutes)

**Learning Objective:** Apply production best practices and security principles

**Slides:** 19-23

#### Content Delivery

**Key Point 1: 12-Factor Agent Principles (Highlights)**
- Main message: Five key principles for production agents
- Structure:
  1. Own Your Prompts - not hidden in framework
  2. Own Your Context Window - curate ruthlessly
  3. Tools Are Structured Outputs - you handle results
  4. Small, Focused Agents - 3-20 steps
  5. Stateless Reducer - enables testing and replay

**Key Point 2: Security Principles**
- Main message: Least privilege, token management, data boundaries, audit logging
- Framework: "Only enable what you need, rotate tokens, know what's exposed"
- Key insight: "MCP gives agents real power - power requires responsibility"

**Key Point 3: Best Practices**
- Main message: Test independently, document everything, version control configs
- Framework: "Treat MCP config like code - versioned, tested, documented"

---

### Closing (3 minutes)

**Slides:** 24-25

**Do Not Skip This Section**

#### Homework Preview

**Script:**
> "Your homework includes three exercises totaling about 75 minutes.
>
> Exercise 3.1 is Multi-Server Configuration - 25 minutes. Identify and configure all MCP servers your agent needs.
>
> Exercise 3.2 is Tool Prompts Development - 25 minutes. Create explicit guidance for how your agent should use each tool.
>
> Exercise 3.3 is Tool Chaining Implementation - 25 minutes. Design and implement at least one tool chain.
>
> By end of week, your agent should be using 3+ MCP tools effectively. Everything is in your participant guide."

#### Next Week Preview

> "Next week is Multi-Step Agents - complex task decomposition, state management across steps, and checkpoint/resume. Your agent needs multiple working tools before then."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: What's the difference between MCP and just calling APIs directly?**
A: MCP provides a standardized protocol that agents understand natively. It handles tool discovery, input/output formatting, and error responses consistently. Direct API calls would require custom integration for each service.

**Q: How many servers is too many?**
A: There's no hard limit, but more servers mean more complexity. Start with what you need, add as required. 3-5 servers is typical for most agents.

**Q: Can I create my own MCP server?**
A: Yes, you can create custom servers. That's beyond Block 3 scope, but the MCP documentation has guides. For most use cases, existing servers plus configuration handles it.

### Technical Questions

**Q: My server won't connect - what do I check?**
A: In order: 1) Config syntax (JSON is valid), 2) Path to server (correct location), 3) Environment variables (tokens set), 4) Restart Claude Desktop. Post full error if stuck.

**Q: How do I handle rate limits across multiple tools?**
A: Add backoff in your error handling (from Week 2). For known rate-limited APIs, add explicit delays between calls in your system prompt.

### Scope Questions

**Q: Should I learn all the servers now?**
A: No - learn what you need for your agent. The registry is a reference, not a curriculum. Start with filesystem and one integration (GitHub, Google Drive, etc.).

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| MCP server won't load | Check config syntax | Show pre-captured working setup |
| Claude Desktop crash | Restart, load minimal config | Demonstrate conceptually |
| Tool returns errors | Show error handling from Week 2 | "This is why error handling matters!" |
| Screen share fails | Restart share | Have participant share their config |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Config not working | Error messages, frustration | Offer post-session troubleshooting |
| No functional agent from Week 2 | Can't test tools | Provide simple starter agent |
| Overwhelmed by options | "Which servers do I need?" | Focus on their specific use case |
| Security concerns | Questions about data exposure | Validate concern, show least privilege |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save common config questions | For troubleshooting guide |
| Note MCP issues encountered | For curriculum improvement |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | |
| Answer config questions in support channel | |
| Share working config examples (sanitized) | |
| Document OS-specific issues | |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions | |
| Check tool chain implementations | |
| Identify participants with config issues | |
| Update guide with lessons learned | |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 3.1 | Multi-server configuration + verification | `/agents/[name]/config/` |
| 3.2 | Tool prompts document + updated system prompt | `/agents/[name]/prompts/` |
| 3.3 | Tool chain documentation + test results | `/agents/[name]/` |

### Progress Check Approach

**How to Verify Completion:**
- Check for MCP configuration documentation
- Verify 3+ tools working (from execution logs)
- Look for tool chain test results

**Intervention Thresholds:**
- MCP not configured: Immediate support needed
- Fewer than 3 tools: May need help with config
- No tool chaining attempted: May not understand patterns

---

## Week-Specific Notes

### What Makes This Week Unique

- **Technical configuration heavy** - More setup than previous weeks
- **Platform dependencies** - OS-specific issues common
- **Expansion week** - Agent capabilities grow significantly
- **Foundation for remaining weeks** - Multi-tool agents essential going forward

### Dependencies

**Builds On:**
- Week 2: Functional agent with error handling
- Week 2: Tool usage from execution logs

**Sets Up:**
- Week 4: Multi-step agents need multiple tools
- Week 5: Agent orchestration uses tool chains
- All remaining weeks: Multi-tool capability assumed

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Windows path escaping | Use forward slashes or escape backslashes | Active |
| Token exposure in logs | Remind about .env usage | Active |
| Server version conflicts | Specify versions in docs | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- "What's the difference between data servers and action servers?" (data reads, action writes/sends)
- "When would you use conditional vs. sequential chaining?" (conditional when path depends on results)
- Observable behavior indicating understanding: Questions about their specific server needs
- Observable behavior indicating confusion: Generic questions, no mention of their agent

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**
- Exercise 3.1: Config actually works (tested), not just documented
- Exercise 3.2: Tool prompts are specific to their tools, not generic
- Exercise 3.3: Chain accomplishes a real task, not just connects tools

**Common Issues to Flag:**
- Credentials in config (should use env vars)
- No verification that servers work
- Tool prompts copied from template without customization

### Connecting to Capstone

**Capstone Relevance:**
This week's work contributes to the capstone by:
- MCP configuration becomes part of deployment documentation
- Tool chains demonstrate automation capability
- Security practices required for production readiness

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "One agent, many tools - MCP makes this possible"
2. "Test each server independently before combining"
3. "Tool chaining creates power - sequential is the starting point"

### If You Only Have Time For One Thing

Multi-server configuration: Know what data/actions/integrations you need, configure each server, test independently, then combine.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| MCP Protocol | Universal translator for tools | Explaining what MCP does |
| Tool Chaining | Assembly line - each station does one thing | Explaining sequential chaining |
| Server Types | Librarian (data), Assistant (action), Bridge (integration) | Categorizing server purposes |

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial guide created | Training Team |
