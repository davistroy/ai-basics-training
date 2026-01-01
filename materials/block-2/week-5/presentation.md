# **POWERPOINT PRESENTATION: BLOCK 2 WEEK 5**
## **MCP Integration Basics**

**Block:** 2: AI Workflow Engineering
**Week Number:** 5
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Consultants with optimized workflows ready for MCP enhancement

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

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2025-01-01 | Initial presentation created | Training Team |

---

**Template Usage:**
1. Use Block 2 orange color theme throughout
2. Have MCP demo prepared and tested
3. Know config file paths for both OS
4. Have backup screenshots for demo failure
5. Cross-reference with instructor and participant guides
