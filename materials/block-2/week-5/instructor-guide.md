# **INSTRUCTOR GUIDE: BLOCK 2 WEEK 5**
## **MCP Integration Basics**

**Block:** 2: AI Workflow Engineering
**Week:** 5 of 8
**Session Duration:** 45 minutes
**Homework Duration:** 60 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Configuring MCP in Claude Desktop and connecting to filesystem and GitHub |
| **Difficulty Level** | Medium-High |
| **Prep Time Required** | 45 minutes |
| **Demo Required** | Yes - Live MCP configuration and filesystem server setup |
| **Tech Setup Needed** | Claude Desktop installed, GitHub token ready, sample directory structure |
| **Common Challenges** | Config file location, JSON syntax errors, GitHub token permissions |

---

## Navigation

**Block Navigation:** [← Week 4 Instructor Guide](../week-4/instructor-guide.md) | **Week 5** | [Week 6 Instructor Guide →](../week-6/instructor-guide.md)

**Related Materials:**
- [Week 5 Presentation](presentation.md)
- [Week 5 Participant Guide](participant-guide.md)
- [Block 2 Main Document](../block-2.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Week 5 materials | ☐ |
| Test MCP setup | Configure MCP on your own machine | ☐ |
| Create demo directory | Set up sample files for filesystem demo | ☐ |
| Generate GitHub token | Have token ready for demo | ☐ |
| Review Week 4 submissions | Check optimization results | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Verify MCP working | Test filesystem and GitHub servers | ☐ |
| Prepare config file | Have example config ready to show | ☐ |
| Check Claude Desktop version | Ensure latest version for MCP support | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, Claude Desktop, config file | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Have config paths ready | Know exact paths for Mac and Windows | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Week 4 recap, MCP excitement | Build anticipation |
| 0:03 | 12 min | Segment 1 | MCP Architecture Deep Dive | Concepts first |
| 0:15 | 15 min | Segment 2 | Setting Up First MCP Server | Live demo |
| 0:30 | 10 min | Segment 3 | GitHub MCP Server Setup | Token and config |
| 0:40 | 2 min | Segment 4 | MCP in Workflows Preview | Quick bridge |
| 0:42 | 3 min | Closing | Homework, Week 6 preview | Don't skip |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Segment 1: Focus on essential architecture, skip advanced security discussion
- Segment 3: Show config but defer token creation to homework

**If Running Ahead:**
- Segment 2: Test additional MCP operations
- Segment 3: Walk through token creation live

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | Must cover core architecture |
| Filesystem working | 0:25 | This is critical demo moment |
| Start Closing | 0:42 | Must start by here regardless |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants
2. Acknowledge optimization wins from Week 4
3. Build excitement for MCP
4. Preview the hands-on nature of today

**Opening Script:**
> "Welcome to Week 5! We've optimized your workflows for cost and quality. Now we give them superpowers. Today we configure MCP - the Model Context Protocol - so Claude can directly access your files and GitHub repositories. No more copy-paste. Let's connect."

**Engagement Opportunity:**
> "Who has Claude Desktop installed and ready? [Count] Great - you'll be setting this up during homework."

---

### Segment 1: MCP Architecture Deep Dive (12 minutes)

**Learning Objective:** Understand MCP components, security model, and how it enables AI-tool connections

**Slides:** 4-7

#### Content Delivery

**Key Point 1: How MCP Works**
- Main message: MCP is a protocol connecting AI to external capabilities
- Architecture: Claude Desktop (Host) ↔ MCP Protocol ↔ MCP Server ↔ External Tool
- Key concepts: Host, Server, Tools, Resources

**Key Point 2: Security Model**
- Main message: Security is local-first
- Servers run on YOUR machine
- No data sent to third parties (unless server specifically does)
- You control which servers are active
- Permission prompts for sensitive operations

**Key Point 3: Available Servers**
- Official: filesystem, GitHub, Slack, databases
- Community: Google Drive, Notion, many more
- Reference Week 1 MCP analysis

#### Facilitation Notes

**Watch For:**
- Confusion about where servers run
- Security concerns about data exposure

**If Asked About Security:**
> "MCP servers run locally on your machine. Data stays with you unless you explicitly configure a server that sends data elsewhere. You control what's active."

**Transition to Segment 2:**
> "Let's actually set this up. Live demo - configuring your first MCP server."

---

### Segment 2: Setting Up Your First MCP Server (15 minutes)

**Learning Objective:** Configure Claude Desktop for MCP with filesystem server

**Slides:** 8-11

#### Demo Instructions

**Demo Duration:** 12-13 minutes

**Setup Required:**
- Claude Desktop installed
- Sample directory with prompt files
- Config file path known

**Demo Steps:**

**Step 1: Locate Config File (3 min)**
> "First, we find where Claude Desktop stores its configuration."

1. Show Mac path: `~/Library/Application Support/Claude/claude_desktop_config.json`
2. Show Windows path: `%APPDATA%\Claude\claude_desktop_config.json`
3. Navigate to the file (create if doesn't exist)

**Step 2: Configure Filesystem Server (4 min)**
> "Now we add our first MCP server - filesystem access."

1. Open config file
2. Add configuration:
```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/prompts"]
    }
  }
}
```
3. Explain each part:
   - mcpServers object contains all servers
   - "filesystem" is the server name
   - command and args specify how to run it
   - The path is what Claude can access

**Step 3: Restart and Test (5 min)**
> "Restart Claude Desktop for changes to take effect."

1. Quit Claude Desktop completely
2. Relaunch
3. Check for MCP indicator (usually shows available tools)
4. Test: "What files are in my prompts directory?"
5. Test: "Read my style.json file"
6. Show successful read

**Demo Talking Points:**
> "Notice Claude now has tools available - these are the MCP capabilities."
> "When I ask to read a file, it uses the filesystem server we configured."

**Backup Plan:**
If demo fails:
1. Show prepared screenshots of each step
2. Debug common issues (path typo, JSON syntax)
3. Walk through conceptually

#### Facilitation Notes

**Common Issues:**
- Config file doesn't exist: Create it
- JSON syntax errors: Use JSON validator
- Path incorrect: Double-check path, use absolute path
- Need to install Node.js for npx: Mention this requirement

---

### Segment 3: GitHub MCP Server Setup (10 minutes)

**Learning Objective:** Configure GitHub MCP for repository access

**Slides:** 12-15

#### Content Delivery

**Key Point 1: Why GitHub MCP**
- Direct access to your prompt library
- Read templates without copy/paste
- Create/update files automatically
- Version control awareness

**Key Point 2: Token Creation**
- Navigate to GitHub Settings → Developer Settings → Personal Access Tokens
- Generate classic token
- Required scopes: repo, read:user
- Copy immediately (won't be shown again)

**Key Point 3: Configuration**
Show the config addition:
```json
{
  "mcpServers": {
    "filesystem": { ... },
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

**Key Point 4: Security Considerations**
- Token stored locally
- Consider using environment variable instead of hardcoding
- Review token scope carefully
- Token can be revoked if compromised

---

### Segment 4: MCP in Workflows Preview (2 minutes)

**Learning Objective:** Understand how MCP connects to workflow automation

**Slides:** 16-17

**Quick Points:**
- Claude with MCP can access templates directly
- Workflows can trigger Claude operations with MCP context
- Week 6 covers full integration patterns
- End-to-end: Trigger → Claude+MCP → Quality Check → Output

---

### Closing (3 minutes)

**Slides:** 18-20

**Script:**
> "Your homework is getting MCP running on YOUR machine. About 60 minutes total.
>
> Exercise 5.1 - 25 minutes - configure Claude Desktop with filesystem server. Get it reading your Block 1 files.
>
> Exercise 5.2 - 20 minutes - add GitHub server. Connect to your prompt library repository.
>
> Exercise 5.3 - 15 minutes - test MCP-powered generation. Have Claude read your templates via MCP and generate output.
>
> By next week, you need working MCP - we're building integrated workflows with it."

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Is MCP only for Claude Desktop? What about the API?**
A: MCP is currently focused on Claude Desktop. API integration patterns exist but are different. For workflow integration, we typically use Claude API with context that MCP helps gather.

**Q: Can I create my own MCP server?**
A: Yes, though it requires development work. The MCP SDK is available. For Block 2, we use existing servers. Block 3 may touch on custom servers.

### Technical Questions

**Q: I get a JSON syntax error. What's wrong?**
A: Common issues: trailing commas, missing quotes, mismatched braces. Use a JSON validator. Every string needs quotes, including keys.

**Q: The filesystem server doesn't show my files.**
A: Check: Is the path correct? Is it an absolute path? Did you restart Claude Desktop after config change? Is the path accessible to your user?

**Q: My GitHub token doesn't work.**
A: Verify: Did you copy the full token? Are the scopes correct (repo, read:user)? Has the token expired? Try generating a new one.

### Scope Questions

**Q: How does this connect to my automation platform (Make/n8n)?**
A: Week 6 covers integration patterns. Short answer: Claude with MCP gathers context, your workflow orchestrates the process.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Config file not found | Show how to create it | Use screenshots |
| MCP server fails to start | Check Node.js installed | Note as prereq for homework |
| Claude doesn't show MCP tools | Full restart, check config | Debug in support channel |
| Path permissions issue | Show permission check | Use different directory |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| No Claude Desktop | "I use the web version" | Emphasize desktop is required for MCP |
| Windows path confusion | Lost with %APPDATA% | Show how to navigate |
| JSON syntax struggles | Multiple errors | Share JSON validator link |
| Node.js not installed | npx fails | Provide Node.js install instructions |

---

## Post-Session Tasks

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording | ☐ |
| Share troubleshooting guide | ☐ |
| Answer config questions | ☐ |
| Provide JSON validator link | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Check MCP setup status | ☐ |
| Help stuck participants | ☐ |
| Prepare Week 6 integration demo | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 5.1 | Working MCP config + `mcp-setup.md` | Claude Desktop + GitHub |
| 5.2 | GitHub MCP working + test results | Claude Desktop + GitHub |
| 5.3 | MCP generation test + sample output | GitHub |

### Progress Check Approach

**How to Verify Completion:**
- Ask about MCP status in Week 6 opening
- Check for mcp-setup.md in repos
- Look for test output documentation

**Intervention Thresholds:**
- MCP not working: Critical - need 1:1 support before Week 6
- Only filesystem working: Acceptable, GitHub can catch up
- No test output: Important to complete before Week 6

---

## Week-Specific Notes

### What Makes This Week Unique

- Configuration-focused rather than building
- Node.js requirement may be new for some
- Direct Claude Desktop interaction
- Sets up transformative capability for Week 6

### Dependencies

**Builds On:**
- Week 1: MCP server analysis
- Weeks 2-4: Workflows ready for MCP enhancement

**Sets Up:**
- Week 6: Full integration patterns
- Capstone: MCP demonstration requirement

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Node.js not installed | Provide install instructions | Active |
| Windows path navigation confusing | Provide explicit steps | Active |
| GitHub token scope confusion | Clear documentation with screenshots | Active |

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "MCP runs locally - your data stays with you"
2. "Restart Claude Desktop after every config change"
3. "JSON must be perfectly formatted - use a validator"

### If You Only Have Time For One Thing

Filesystem server working - this is the foundation for all MCP work.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| MCP Server | "A bridge between Claude and your tools" | Explaining architecture |
| Config file | "Claude's address book for tools" | Explaining where config goes |
| Token | "Your GitHub key - don't share it" | Security context |

---

**Navigation:** [← Week 4 Instructor Guide](../week-4/instructor-guide.md) | **Week 5** | [Week 6 Instructor Guide →](../week-6/instructor-guide.md)
