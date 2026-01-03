# **POWERPOINT PRESENTATION: BLOCK 2 WEEK 5**
## **MCP Integration Basics**

**Block:** 2: AI Workflow Engineering
**Week Number:** 5
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Consultants with optimized workflows ready for MCP enhancement

**Key Thesis:** Model Context Protocol (MCP) is the universal connector that transforms Claude from an isolated AI into an integrated tool with direct access to files, repositories, and enterprise systems through locally-run, secure servers.

**Week Learning Objectives:** By the end of this session, participants will:
1. Understand MCP architecture and security model
2. Configure Claude Desktop with filesystem MCP server
3. Set up GitHub MCP server for repository access
4. Test MCP-powered file access and generation

**Entry Criteria:**
- [ ] Two optimized workflows running
- [ ] Claude Desktop installed
- [ ] MCP servers identified (from Week 1)
- [ ] Understanding of workflow data flow

**Exit Criteria:**
- [ ] MCP configured in Claude Desktop
- [ ] At least one MCP server connected and functional
- [ ] Workflow integrated with MCP capability
- [ ] MCP security considerations understood
- [ ] GitHub MCP server working

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: MCP Architecture (12 min) - Slides 4-7
3. Segment 2: First MCP Server Setup (15 min) - Slides 8-11
4. Segment 3: GitHub MCP Setup (10 min) - Slides 12-15
5. Segment 4: MCP in Workflows (2 min) - Slides 16-17
6. Homework Preview & Close (3 min) - Slides 18-20

**Total Slides:** 20

---

## SLIDE 1: TITLE SLIDE

**Title:** Block 2 Week 5: MCP Integration Basics

**Subtitle:** Connecting Claude to Your Files and Repositories

**Content:**
- AI Practitioner Training Program
- Block 2: AI Workflow Engineering
- [Instructor Name]
- [Date]

**Graphic:** Clean title slide with Block 2 orange theme. MCP server icon.

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Week 5! You've optimized your workflows for cost and quality. Now we give them superpowers.

Today we configure MCP - the Model Context Protocol - so Claude can directly access your files and GitHub repositories.

No more copy-paste. No more manually gathering context. Claude reads your templates directly.

Who has Claude Desktop installed and ready? [Count]

Let's connect."

[Transition: Click to next slide]

---

## SLIDE 2: WEEK OVERVIEW

**Title:** This Week's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Week 4 recap, MCP excitement |
| 3-15 min | Segment 1 | MCP Architecture Deep Dive |
| 15-30 min | Segment 2 | Setting Up First MCP Server (Demo) |
| 30-40 min | Segment 3 | GitHub MCP Server Setup |
| 40-42 min | Segment 4 | MCP in Workflows Preview |
| 42-45 min | Close | Homework & Week 6 Preview |

**Graphic:** Visual timeline with MCP integration icons

**SPEAKER NOTES:**

"Our agenda:

First, we understand MCP architecture - how it works, what it connects.

Then the main event: live demo of configuring your first MCP server. You'll do this in homework.

We'll add GitHub server for repository access.

And preview how MCP connects to your workflows.

By the end, you'll understand exactly how to set this up on your own machine."

[Transition]

---

## SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Understand MCP architecture**
   - Host, Server, Tools, Resources

2. **Configure filesystem MCP server**
   - Claude reads your local files

3. **Set up GitHub MCP server**
   - Direct access to your prompt library

4. **Apply MCP to real generation**
   - No more copy-paste

**Graphic:** Checklist with MCP server icons

**SPEAKER NOTES:**

"Four objectives.

First, understand the architecture - how MCP components fit together.

Second, configure filesystem access - Claude reading your local files.

Third, GitHub access - Claude reading directly from your repositories.

Fourth, apply it - use MCP for actual content generation.

Let's start with architecture."

[Transition: Click to Segment 1]

---

## SEGMENT 1: MCP ARCHITECTURE DEEP DIVE
### Duration: 12 minutes | Slides 4-7

---

## SLIDE 4: HOW MCP WORKS

**Title:** The MCP Architecture

**Content:**

```
┌─────────────────────┐
│   Claude Desktop    │  ← HOST
│       (Host)        │
└──────────┬──────────┘
           │ MCP Protocol
           ▼
┌─────────────────────┐
│     MCP Server      │  ← SERVER
│      (Bridge)       │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│   External Tool     │  ← CAPABILITY
│  (Files, GitHub...)  │
└─────────────────────┘
```

**The Components:**
- **Host:** Claude Desktop (your AI interface)
- **Server:** Bridge to external capabilities
- **Capabilities:** Files, APIs, databases...

**Graphic:** Architecture diagram with labeled components

**GRAPHICS:**

**Graphic 1: Complete MCP Architecture**
- Purpose: Show how all MCP components connect in complete system
- Type: Layered system architecture diagram
- Elements: Claude Desktop (Host layer), MCP Server layer (filesystem, github, slack servers), External Resources layer (files, repos, APIs), bidirectional arrows showing MCP protocol, workflow platform connection
- Labels: Component names, layer labels, communication paths, "Your Workflow" integration point
- Relationships: Layered architecture with multiple servers providing different capabilities, workflow automation leveraging MCP

**SPEAKER NOTES:**

"[Hook - The architecture]"

"Let me show you how MCP is structured.

[Point to Host]

At the top: Claude Desktop. This is the Host - where you interact with Claude.

[Point to Server]

In the middle: MCP Servers. These are bridges that connect Claude to external capabilities. They're pre-built - you configure, not code.

[Point to Capabilities]

At the bottom: the actual tools - your files, GitHub repos, databases, APIs.

MCP is the protocol - the language they speak to each other.

You configure which servers are active. Claude Desktop handles the communication."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide establishes the foundational mental model for understanding MCP as a three-layer architecture
- It addresses the "how does this actually work" question that blocks adoption for technical audiences
- The layered diagram makes an abstract protocol concrete and understandable

**Key Research & Citations:**
- **Model Context Protocol Specification (Anthropic, 2024)**: Open protocol enabling AI applications to connect with external data sources and tools through a standardized interface, designed for security and extensibility
- **Client-Server Architecture Patterns**: MCP follows established architectural patterns (host-bridge-resource) familiar from web services, making it conceptually accessible to anyone with API experience
- **Tool Use in LLMs Research**: Studies show that LLMs with structured tool access significantly outperform context-only approaches for tasks requiring external data or actions

**Q&A Preparation:**
- *"Is this an Anthropic-only technology?"*: No. MCP is an open protocol. While Anthropic developed it, any AI application can implement it. Think of it like HTTP - one company created it, but it's now a universal standard.
- *"Do I need to be a programmer to use MCP?"*: No programming required for standard servers (filesystem, GitHub, etc.). You edit a JSON config file. Custom servers require coding, but that's optional and advanced.
- *"What's the difference between MCP and API calls in my workflow?"*: MCP is for Claude accessing tools/data. Workflow APIs orchestrate AI calls. They work together: MCP gives Claude context, your workflow controls when/how AI runs.

---

## SLIDE 5: KEY MCP CONCEPTS

**Title:** Understanding the Components

**Content:**

| Component | What It Is | Example |
|-----------|------------|---------|
| **Host** | AI application | Claude Desktop |
| **Server** | Pre-built connector | filesystem, github |
| **Tools** | Actions server provides | Read file, list repos |
| **Resources** | Data server exposes | File contents, repo data |

**How They Connect:**
1. You configure servers in config file
2. Claude Desktop activates configured servers
3. Servers provide tools and resources to Claude
4. You use natural language - Claude uses the tools

**Graphic:** Visual showing the relationship between components

**SPEAKER NOTES:**

"Let's define each component clearly.

[Point to table]

Host is Claude Desktop - the application.

Servers are pre-built connectors - filesystem, GitHub, Slack, and many more.

Tools are what servers DO - read a file, list repositories, send a message.

Resources are what servers PROVIDE - file contents, repository data.

[Point to connection]

You configure it once. Then you just chat naturally. 'Read my `style.json`' - Claude uses the filesystem tool automatically."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide clarifies the critical distinction between Tools (actions) and Resources (data) that confuses many first-time MCP users
- Understanding the component taxonomy enables participants to troubleshoot issues and select appropriate servers for their needs
- The "configure once, use naturally" principle demonstrates the usability advantage of MCP over manual context management

**Key Research & Citations:**
- **Model Context Protocol Specification**: MCP defines a clear separation between Tools (executable functions) and Resources (readable data) to enable both action-taking and context-gathering capabilities
- **Abstraction Patterns in API Design**: The host-server-tool/resource architecture follows established API design patterns where abstraction layers (servers) translate between generic interfaces (hosts) and specific implementations (tools/resources)
- **Natural Language Interface Research**: Studies show that users prefer natural language commands ("read my file") over explicit function calls when both achieve the same outcome - MCP enables this through automatic tool selection

**Q&A Preparation:**
- *"What's the difference between Tools and Resources?"*: Tools are actions (read file, create issue, send message). Resources are data (file contents, repository info, channel history). Some servers provide both - filesystem has read_file (tool) and file contents (resource).
- *"How does Claude know which tool to use?"*: When you make a request, Claude analyzes what you need, sees available tools from active servers, and automatically selects the appropriate one. You see this in the UI when tools are invoked.
- *"Can I create custom servers?"*: Yes, but that's advanced. The official server registry has 50+ pre-built servers covering most needs. Start with those before building custom ones.

**Sources:**
- Model Context Protocol Specification - Anthropic, 2024
- MCP Server Registry - github.com/modelcontextprotocol/servers

---

## SLIDE 6: MCP SECURITY MODEL

**Title:** Your Data Stays With You

**Content:**

**Security Principles:**

| Principle | What It Means |
|-----------|---------------|
| **Local Execution** | Servers run on YOUR machine |
| **No Third Parties** | Data doesn't leave unless server explicitly sends it |
| **Explicit Activation** | YOU control which servers are configured |
| **Permission Prompts** | Sensitive operations ask for approval |
| **Scoped Access** | Each server has defined, limited capabilities |

**The Key Insight:**
> MCP servers run locally. Your files, your machine, your control.

**Graphic:** Security shield with local execution emphasis

**GRAPHICS:**

**Graphic 1: MCP Local Execution Security Model**
- Purpose: Illustrate security advantage of local MCP execution
- Type: Comparison diagram with security emphasis
- Elements: Cloud approach showing data leaving machine, MCP local approach showing data containment, security shield on local side, data flow arrows showing boundaries
- Labels: "Cloud: Data Leaves Machine" vs "MCP: Data Stays Local," security indicators, data protection callout
- Relationships: Contrast showing security advantage of local execution, client data protection

**SPEAKER NOTES:**

"Security is a reasonable concern. Let me address it directly.

[Point to principles]

Local execution: servers run on YOUR machine. Not in the cloud. Not on Anthropic's servers.

No third parties: data doesn't leave your machine unless a server is specifically designed to send it somewhere.

Explicit activation: YOU decide which servers are active. Nothing runs unless you configure it.

Permission prompts: for sensitive operations, you'll be asked to confirm.

Scoped access: the filesystem server can only access the directory you specify. Not your whole computer.

[Point to key insight]

Bottom line: your files, your machine, your control. MCP doesn't phone home."

[Transition]

**BACKGROUND:**

**Rationale:**
- Security concerns are the #1 barrier to MCP adoption in enterprise contexts - this slide must directly address them
- The local execution model is MCP's key security differentiator but counterintuitive to cloud-first thinking
- Explicit permission and scoped access align with enterprise security principles (least privilege, defense in depth)

**Key Research & Citations:**
- **Local-First Software Principles**: The "local execution" model follows local-first architecture patterns where data remains on user devices, reducing attack surface and privacy risks
- **Zero Trust Security**: MCP's explicit configuration and permission prompts align with zero trust principles - nothing is trusted by default, everything must be explicitly authorized
- **Enterprise AI Security Research**: Studies of AI deployment blockers show that data exfiltration concerns are the top barrier. MCP's architecture directly addresses this concern.

**Q&A Preparation:**
- *"What if a malicious MCP server steals my data?"*: You control which servers are configured. Use only official servers from the MCP registry or vetted sources. Think of it like browser extensions - use reputable ones, avoid random unknowns.
- *"Can Claude send my files to Anthropic?"*: Only the conversation content (what you type and Claude's responses) go to Anthropic's API. MCP server data stays local unless explicitly configured otherwise. Filesystem server reads files locally, includes relevant portions in prompts.
- *"What about GitHub tokens in the config?"*: Tokens are stored locally in your config file. Use read-only tokens with minimal scopes. You can revoke and regenerate tokens anytime. Consider them like API keys - protect them, but they're revocable if compromised.

---

## SLIDE 7: SEGMENT 1 SUMMARY

**Title:** MCP Architecture Recap

**Content:**

**Remember:**
- Host (Claude Desktop) ↔ Server (Bridge) ↔ Capability (Tool)
- Servers run locally on your machine
- You configure which servers are active
- Each server provides specific tools and resources

**Available Servers:**
- Filesystem: Local file access
- GitHub: Repository access
- Slack, databases, and many more

**Coming Up:**
Live demo - configuring your first MCP server

**Graphic:** Simple architecture recap

**SPEAKER NOTES:**

"Quick recap:

Three-layer architecture: Claude Desktop talks to servers, servers talk to tools.

Everything runs locally. You control what's active.

We'll use filesystem and GitHub servers - both are official, well-tested.

Now let's set it up live."

[Transition: Click to Segment 2]

---

## SEGMENT 2: SETTING UP YOUR FIRST MCP SERVER
### Duration: 15 minutes | Slides 8-11

---

## SLIDE 8: CONFIG FILE LOCATION

**Title:** Where Claude Stores MCP Settings

**Content:**

**Config File Locations:**

**Mac:**
```
~/Library/Application Support/Claude/claude_desktop_config.json
```

**Windows:**
```
%APPDATA%\Claude\claude_desktop_config.json
```

**If File Doesn't Exist:**
Create it - we'll show you exactly what to put in it

**Graphic:** File path visualization for both OS

**SPEAKER NOTES:**

"[DEMO - Starting]"

"First, we find where Claude stores its configuration.

[Show Mac path]

On Mac: Home folder, Library, Application Support, Claude folder, claude_desktop_config.json.

[Show Windows path]

On Windows: %APPDATA%\Claude\claude_desktop_config.json. You can type %APPDATA% directly in File Explorer.

If the file doesn't exist, we create it. If it exists, we add to it.

Let me show you on my machine..."

[Navigate to file location]

---

## SLIDE 9: FILESYSTEM SERVER CONFIGURATION

**Title:** Adding Your First MCP Server

**Content:**

**Configuration Structure:**
```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/path/to/your/prompts"
      ]
    }
  }
}
```

**Key Elements:**
- `mcpServers`: Contains all server configs
- `filesystem`: Server name (can be anything)
- `command`: How to run the server
- `args`: Server package and path to allow

**Graphic:** Config file with annotated sections

**SPEAKER NOTES:**

"Here's what goes in the config file.

[Point to mcpServers]

The mcpServers object holds all your server configurations.

[Point to filesystem]

'filesystem' is the name we're giving this server.

[Point to command and args]

We use npx to run the server - this fetches and runs the package automatically.

[Point to path]

The path is critical - this is the ONLY directory Claude can access. Your whole disk isn't exposed - just this folder.

Let me add this to my config..."

[Show editing config file]

---

## SLIDE 10: TESTING YOUR CONFIGURATION

**Title:** Restart and Verify

**Content:**

**After Saving Config:**
1. **Quit Claude Desktop completely**
   - Mac: Cmd+Q
   - Windows: Close all windows, check Task Manager

2. **Relaunch Claude Desktop**

3. **Look for MCP indicator**
   - Tools should appear available

4. **Test with prompts:**
   - "What files are in my prompts directory?"
   - "Read my `style.json` file"

**Graphic:** Test workflow diagram

**SPEAKER NOTES:**

"After saving the config, we must restart.

[Emphasize]

COMPLETELY restart. Not just close the window - fully quit the application.

[Restart Claude Desktop in demo]

Now we wait for it to load...

[When loaded]

Look - there's an indicator showing MCP tools are available.

Let me test: 'What files are in my prompts directory?'

[Show Claude accessing files]

It's reading my local files via MCP. No copy-paste. No manual browsing."

---

## SLIDE 11: SEGMENT 2 SUMMARY

**Title:** Filesystem Server Configured

**Content:**

**What We Did:**
1. Located config file
2. Added filesystem server configuration
3. Restarted Claude Desktop
4. Tested file access

**Key Points:**
- JSON must be perfectly valid
- Restart required after every change
- Only configured directory is accessible

**You'll Practice:**
Exercise 5.1 - Configure this on your machine

**Graphic:** Checkmarks for completed steps

**SPEAKER NOTES:**

"We've got filesystem MCP working.

What we did: located config, added configuration, restarted, tested.

Remember: JSON must be valid - use a validator if needed. Always restart after changes.

In Exercise 5.1, you'll do exactly this on your own machine.

Now let's add GitHub access."

[Transition: Click to Segment 3]

---

## SEGMENT 3: GITHUB MCP SERVER SETUP
### Duration: 10 minutes | Slides 12-15

---

## SLIDE 12: WHY GITHUB MCP

**Title:** Direct Access to Your Prompt Library

**Content:**

**What GitHub MCP Enables:**
- Read templates directly from your repo
- No copy-paste from GitHub
- Access any file in any repo you own
- Version-aware (can specify branches)

**Use Cases:**
- "Read my proposal template from [repo]/templates/"
- "Get my `style.json` from the resources folder"
- "List what templates I have available"

**Graphic:** GitHub logo with MCP server arrows

**SPEAKER NOTES:**

"Why add GitHub MCP?

Your prompt library is in GitHub. Right now, to use a template, you open GitHub, find the file, copy it, paste it into Claude.

With GitHub MCP: 'Read my proposal template from my-repo/templates/proposal.md'

That's it. Claude reads it directly. No copy-paste. No context switching.

This is where the time savings become real."

[Transition]

**BACKGROUND:**

**Rationale:**
- GitHub MCP demonstrates the practical value of MCP beyond local filesystem access - it connects to external version-controlled resources
- The copy-paste elimination use case is immediately relatable and quantifiable for time savings calculations
- Version-awareness capability (branch specification) enables sophisticated use cases like testing prompts before merging

**Key Research & Citations:**
- **Context Switching Cost Research**: Studies show that context switching (e.g., switching from Claude to GitHub and back) creates 15-30% productivity loss. Each switch requires 5-15 minutes to regain focus. MCP eliminates this overhead.
- **Version Control in AI Workflows**: GitHub's version control combined with MCP access enables prompt engineering best practices - testing changes in branches, rolling back failures, collaborative prompt development
- **Template Reuse Patterns**: Research on knowledge work efficiency shows that template reuse reduces time-to-output by 40-60% compared to starting from scratch. MCP makes template access frictionless.

**Q&A Preparation:**
- *"Why use GitHub instead of just filesystem MCP?"*: GitHub provides version control, collaboration, backup, and access from anywhere. Filesystem is for local-only files. Both serve different needs - many users configure both servers.
- *"Can I access private repos?"*: Yes - that's what the Personal Access Token enables. Your token authenticates you to GitHub, so MCP can access any repo you have permissions for.
- *"What if my team uses GitLab or Bitbucket?"*: Check the MCP server registry - there may be community-built servers for those platforms. If not, filesystem MCP with local git clones is a workaround until specific servers are available.

**Sources:**
- Context Switching and Productivity - Gloria Mark, UC Irvine, 2023
- GitHub MCP Server Documentation - github.com/modelcontextprotocol/servers

---

## SLIDE 13: CREATING GITHUB TOKEN

**Title:** GitHub Personal Access Token

**Content:**

**Steps:**
1. GitHub.com → Your Profile → Settings
2. Scroll to "Developer settings" (bottom left)
3. Personal access tokens → Tokens (classic)
4. Generate new token (classic)
5. Select scopes:
   - [x] **repo** - Repository access
   - [x] **read:user** - Read user profile
6. Generate and **COPY IMMEDIATELY**

**Security Note:**
Token is shown once. Store it securely.

**Graphic:** GitHub settings navigation path

**SPEAKER NOTES:**

"To connect GitHub, we need a Personal Access Token.

[Walk through steps]

Go to GitHub Settings, find Developer settings at the bottom, Personal access tokens, Tokens classic.

Generate new token. Give it a name like 'MCP Access.'

[Point to scopes]

Select 'repo' for repository access and 'read:user' for profile access. These are the minimum needed.

[Emphasize]

When you generate, COPY IT IMMEDIATELY. GitHub shows it once. If you lose it, generate a new one.

I'll show this process, but use a test account..."

[Brief demo if time]

---

## SLIDE 14: GITHUB SERVER CONFIGURATION

**Title:** Adding GitHub to Your Config

**Content:**

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path"]
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

**Key Difference:**
- `env` object for environment variables
- Token goes in GITHUB_PERSONAL_ACCESS_TOKEN

**Graphic:** Config file with GitHub section highlighted

**SPEAKER NOTES:**

"Here's the GitHub configuration.

[Point to github section]

We add it alongside filesystem - both servers can be active.

[Point to env]

The 'env' object passes environment variables. Your token goes in GITHUB_PERSONAL_ACCESS_TOKEN.

[Point to token]

Replace 'ghp_your_token_here' with your actual token.

After saving, restart Claude Desktop, and test with: 'List my repositories' or 'Read the README from my-repo.'"

[Transition]

---

## SLIDE 15: SEGMENT 3 SUMMARY

**Title:** GitHub MCP Ready

**Content:**

**Configuration Complete:**
- Token created with repo + read:user scopes
- GitHub server added to config
- Token stored in env section

**Test Prompts:**
- "List my repositories"
- "Read [repo]/`README.md`"
- "Show my templates folder from [repo]"

**Security Reminder:**
- Token stored locally only
- Revoke if compromised
- Use minimal scopes

**Graphic:** GitHub + MCP connected visual

**SPEAKER NOTES:**

"GitHub MCP is configured.

You'll test with prompts like 'list my repositories' or 'read file from repo.'

Security reminder: token is stored only in your local config. If somehow compromised, revoke it on GitHub and generate a new one.

In Exercise 5.2, you'll set this up on your machine."

[Transition: Click to Segment 4]

---

## SEGMENT 4: MCP IN WORKFLOWS PREVIEW
### Duration: 2 minutes | Slides 16-17

---

## SLIDE 16: CONNECTING TO YOUR WORKFLOWS

**Title:** How MCP Fits the Picture

**Content:**

**The Integration Pattern:**
```
Trigger → [Gather Data] → [Claude + MCP] → Quality Check → Output
                              ↓
                    Reads templates directly
                    Applies style.json
                    No copy-paste needed
```

**What This Enables:**
- Claude reads your templates via MCP
- Workflow orchestrates the process
- Quality check on output
- Full automation

**Coming in Week 6:**
Full integration patterns and third workflow

**Graphic:** Workflow with MCP-enabled Claude step

**SPEAKER NOTES:**

"Quick preview of where this goes.

[Point to diagram]

Your workflow triggers. Data is gathered. Claude runs with MCP active - it reads templates directly from GitHub.

No copy-paste. No manual context gathering.

Quality check on output. Deliver to destination.

This is the integration pattern we'll build in Week 6.

Today: get MCP working. Next week: integrate it into workflows."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide bridges Week 5 (MCP setup) to Week 6 (integration patterns) by previewing the connection
- It resolves the "what's the point of MCP" question by showing concrete workflow integration
- The preview builds anticipation for Week 6 and motivates completion of Week 5 exercises

**Key Research & Citations:**
- **Separation of Concerns Principle**: Software architecture best practice - MCP handles context/tools, workflow platforms handle orchestration. Clear boundaries prevent confusion and enable modular design.
- **Orchestration vs. Execution Pattern**: Workflow platforms orchestrate (when to run, what data to pass), MCP executes (what tools AI can access). This mirrors microservices architecture patterns.
- **Integration Architecture Literature**: Successful AI systems combine context providers (like MCP), processing engines (like Claude API), and orchestrators (like Make/n8n). Each layer serves a distinct purpose.

**Q&A Preparation:**
- *"Can I replace my workflow platform with MCP?"*: No - they serve different functions. MCP gives Claude access to data/tools. Workflow platforms orchestrate multi-step processes, route based on conditions, connect to output destinations. You need both.
- *"Which approach should I use for my use case?"*: If context is stable (templates, style guides), pre-fetch via MCP and pass to API is simplest. If context varies by execution, Claude Desktop + MCP to gather context on-demand works better. Hybrid is common - some via MCP, some via workflow.
- *"Does this mean I need Claude Desktop running for workflows?"*: Depends on approach. If you pre-fetch templates via MCP once and store them, no. If workflows call Claude Desktop directly, yes. Most production workflows use Claude API with pre-fetched or workflow-provided context.

---

## SLIDE 17: SEGMENT 4 SUMMARY

**Title:** MCP Enables Full Automation

**Content:**

**This Week:**
- Configure MCP on your machine
- Test filesystem access
- Test GitHub access

**Next Week:**
- Full integration patterns
- Build third workflow with MCP
- End-to-end automation

**The Goal:**
No more copy-paste. Claude accesses your templates directly.

**Graphic:** Automation goal visual

**SPEAKER NOTES:**

"This week: get MCP working on your machine.

Next week: full integration with your workflows.

The goal is simple: no more copy-paste. Claude reads your templates directly.

Let's close out with homework."

[Transition: Click to Closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 18-20

---

## SLIDE 18: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Focus |
|----------|------|-------------|-------|
| 5.1: Filesystem MCP | 25 min | Config + `mcp-setup.md` | Local file access |
| 5.2: GitHub MCP | 20 min | GitHub config + tests | Repo access |
| 5.3: Generation Test | 15 min | `mcp-generation-test.md` | Practical value |
| **Total** | **60 min** | | |

**Critical:** MCP must be working for Week 6

**Graphic:** Exercise breakdown

**SPEAKER NOTES:**

"Three exercises, about 60 minutes.

Exercise 5.1 - configure filesystem MCP. Get Claude reading your local files.

Exercise 5.2 - add GitHub MCP. Get Claude accessing your repositories.

Exercise 5.3 - test real generation. Have Claude read templates via MCP and produce output.

[Emphasize]

MCP must be working for Week 6. We'll build integrated workflows that depend on it."

[Transition]

---

## SLIDE 19: RESOURCES

**Title:** Resources for This Week

**Content:**

**MCP Resources:**
- Server Registry: github.com/modelcontextprotocol/servers
- Documentation: modelcontextprotocol.io
- Claude Desktop: claude.ai/download

**Setup Help:**
- JSON Validator: jsonlint.com
- Node.js (if needed): nodejs.org
- GitHub Tokens: docs.github.com

**Support:**
- Config issues: Post with error message
- Screenshots help!

**Graphic:** Resource icons

**SPEAKER NOTES:**

"Resources:

MCP server registry for documentation on each server.

JSON validator if you're having syntax issues.

Node.js download if npx doesn't work.

If you get stuck, post in support with your error message and a screenshot of your config (hide your token!)."

[Transition]

---

## SLIDE 20: NEXT WEEK PREVIEW

**Title:** Next Week: Integration Patterns

**Content:**

**Week 6 Focus:**
- Advanced integration patterns
- Build third workflow with MCP
- Human-in-the-loop systems
- Full integration documentation

**Preparation Required:**
- [ ] MCP filesystem working
- [ ] MCP GitHub working
- [ ] Both tested successfully
- [ ] Two existing workflows ready

**The Goal:**
Three fully integrated workflows ready for capstone.

**Graphic:** Integration pattern preview

**SPEAKER NOTES:**

"Next week: full integration patterns.

We'll build your third workflow with MCP integrated. We'll design human-in-the-loop systems. We'll document the full architecture.

To be ready:
- Both MCP servers must be working
- Your two existing workflows ready to enhance

[Final close]

Questions before we wrap?

[Take questions]

This is exciting week - you're connecting Claude to your actual tools. No more copy-paste.

Get MCP working, test it thoroughly, and see you next week!"

---

## Appendices

### Appendix D: MCP Configuration Templates

**Filesystem Server Template:**
```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/absolute/path/to/allowed/directory"
      ]
    }
  }
}
```

**GitHub Server Template:**
```json
{
  "mcpServers": {
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

**Combined Configuration:**
```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path"]
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

### Appendix E: MCP Troubleshooting Guide

**Common Issues and Solutions:**

| Issue | Cause | Solution |
|-------|-------|----------|
| Servers not appearing | Config syntax error | Validate JSON at jsonlint.com |
| npx not found | Node.js not installed | Install from nodejs.org |
| Permission errors | Incorrect path permissions | Check directory permissions |
| Token errors | Invalid or expired token | Regenerate GitHub token |
| Restart didn't work | Claude still running | Check Task Manager/Activity Monitor |

**Validation Steps:**
1. Validate JSON syntax
2. Check file paths are absolute
3. Verify Node.js installation: `node --version`
4. Confirm Claude fully restarted
5. Check error logs in Claude Desktop

### Appendix F: MCP Security Best Practices

**Configuration Security:**
- Use read-only tokens when possible
- Limit filesystem access to specific directories
- Never commit tokens to version control
- Rotate tokens periodically (every 90 days)
- Use minimal scopes for GitHub tokens

**Safe Token Management:**
1. Store tokens only in local config files
2. Use environment variables for sensitive values
3. Document token permissions in setup guide
4. Revoke tokens immediately if compromised
5. Use separate tokens for different environments

### Appendix G: MCP Use Case Examples

**Template Access:**
- "Read my proposal template from [repo]/templates/proposal.md"
- "Show me my style.json file"
- "List all markdown files in my prompts directory"

**Version Control Integration:**
- "Read the README from the main branch"
- "Compare my template with the version in develop branch"
- "Show recent commits to my prompts folder"

**Workflow Integration:**
- Pre-fetch templates via MCP for workflow use
- Reference style guides automatically
- Access brand assets from GitHub

### Appendix H: MCP Server Registry

**Official MCP Servers:**

| Server | Purpose | Documentation |
|--------|---------|---------------|
| filesystem | Local file access | github.com/modelcontextprotocol/servers |
| github | GitHub repository access | github.com/modelcontextprotocol/servers |
| gitlab | GitLab repository access | github.com/modelcontextprotocol/servers |
| slack | Slack integration | github.com/modelcontextprotocol/servers |
| postgres | Database access | github.com/modelcontextprotocol/servers |
| google-drive | Google Drive access | github.com/modelcontextprotocol/servers |

**Finding Servers:**
- Official registry: github.com/modelcontextprotocol/servers
- Community servers: Search "MCP server" + your tool
- Documentation: modelcontextprotocol.io

### Appendix I: Platform-Specific Instructions

**macOS Configuration:**
- Config location: `~/Library/Application Support/Claude/claude_desktop_config.json`
- Access Library folder: Finder → Go menu → Hold Option → Library
- Use absolute paths: `/Users/[username]/path/to/directory`

**Windows Configuration:**
- Config location: `%APPDATA%\Claude\claude_desktop_config.json`
- Access APPDATA: Type `%APPDATA%` in File Explorer address bar
- Use absolute paths: `C:\Users\[username]\path\to\directory`

**Linux Configuration:**
- Config location: `~/.config/Claude/claude_desktop_config.json`
- Standard XDG config directory
- Use absolute paths: `/home/[username]/path/to/directory`

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

**Template Usage:**
1. Use Block 2 orange color theme throughout
2. Have MCP demo prepared and tested
3. Know config file paths for both OS
4. Have backup screenshots for demo failure
5. Cross-reference with instructor and participant guides
