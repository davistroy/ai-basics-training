# **BLOCK 2 WEEK 5: MCP Integration Basics**

**Block:** 2: AI Workflow Engineering
**Week:** 5 of 8
**Estimated Self-Paced Time:** 60 minutes

---

## Navigation

**Block Navigation:** [← Week 4](../week-4/participant-guide.md) | **Week 5** | [Week 6 →](../week-6/participant-guide.md)

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
| 1 | Configure MCP in Claude Desktop with filesystem server | Exercise 5.1 |
| 2 | Set up GitHub MCP server for repository access | Exercise 5.2 |
| 3 | Use MCP to enable Claude to read files and templates directly | Exercise 5.3 |
| 4 | Understand MCP security model and best practices | All exercises |

---

## Entry Criteria

Before starting this week, confirm you have completed:

- [ ] Two optimized workflows running
- [ ] Claude Desktop installed
- [ ] MCP servers identified (from Week 1 analysis)
- [ ] Understanding of workflow data flow

**Not ready?** Install Claude Desktop from claude.ai/download and complete Week 4 exercises.

---

## Key Concepts

### Concept 1: MCP Architecture

**Definition:**
The Model Context Protocol (MCP) is a standardized protocol that allows Claude Desktop to connect to external tools and data sources through configured "servers."

**Why It Matters:**
MCP eliminates copy-paste workflows. Claude can directly read your files, access repositories, and interact with tools.

**Architecture:**
```
┌─────────────────────┐
│   Claude Desktop    │  ← HOST (your AI interface)
│       (Host)        │
└──────────┬──────────┘
           │ MCP Protocol
           ▼
┌─────────────────────┐
│     MCP Server      │  ← SERVER (bridge to capabilities)
│      (Bridge)       │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│   External Tool     │  ← CAPABILITY (files, APIs, data)
│    (Capability)     │
└─────────────────────┘
```

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| Host | Claude Desktop application | Where you chat with Claude |
| Server | Pre-built connector | Filesystem server, GitHub server |
| Tools | Actions a server provides | Read file, list directory |
| Resources | Data sources exposed | File contents, repository data |

---

### Concept 2: MCP Security Model

**Definition:**
MCP's security approach where servers run locally on your machine and you control which servers are active.

**Why It Matters:**
Understanding security lets you use MCP confidently with sensitive data.

**Security Principles:**

| Principle | Description |
|-----------|-------------|
| Local execution | Servers run on YOUR machine |
| No third-party data | Data doesn't leave your machine (unless server specifically sends it) |
| Explicit activation | You control which servers are configured |
| Permission prompts | Sensitive operations require approval |
| Scoped access | Each server has limited, defined capabilities |

**Best Practices:**
- Only configure servers you need
- Use minimal token scopes for GitHub
- Review server documentation before adding
- Keep config file secure (contains tokens)

---

### Concept 3: Claude Desktop Configuration

**Definition:**
The JSON configuration file that tells Claude Desktop which MCP servers to activate.

**Why It Matters:**
Correct configuration is required for MCP to work. One syntax error breaks everything.

**Config File Locations:**
- **Mac:** `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows:** `%APPDATA%\Claude\claude_desktop_config.json`

**Basic Structure:**
```json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-name", "optional-args"],
      "env": {
        "OPTIONAL_VAR": "value"
      }
    }
  }
}
```

**Key Rules:**
- JSON must be perfectly valid (no trailing commas)
- All strings in double quotes
- Restart Claude Desktop after every change
- Path separators: Use forward slashes or escape backslashes on Windows

---

### Concept 4: Filesystem Server

**Definition:**
The MCP server that allows Claude to read and write files in specified directories.

**Why It Matters:**
This is the foundation for Claude accessing your templates, style guides, and other local files.

**Configuration:**
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

**Capabilities:**
- List files in directory
- Read file contents
- Write new files (if permitted)
- Navigate directory structure

**Security:** Claude can only access the specific directory you configure.

---

### Concept 5: GitHub Server

**Definition:**
The MCP server that allows Claude to access your GitHub repositories.

**Why It Matters:**
Direct access to your prompt library without copy-paste. Claude can read templates directly from GitHub.

**Configuration:**
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

**Token Requirements:**
- Generate at: GitHub → Settings → Developer Settings → Personal Access Tokens
- Required scopes: `repo`, `read:user`
- Copy immediately (won't be shown again)

**Capabilities:**
- List repositories
- Read file contents from repos
- List directory contents
- Access repository metadata

---

## Workshop Recap

### Session Summary

**Today's Focus:** Configuring MCP in Claude Desktop to connect to files and GitHub.

**Key Points from Each Segment:**

**Segment 1: MCP Architecture Deep Dive**
- MCP connects Claude to external tools via protocol
- Host (Claude Desktop) ↔ Server (bridge) ↔ Tool (capability)
- Security is local-first - servers run on your machine
- You control what's active

**Segment 2: Setting Up First MCP Server**
- Config file location differs by OS
- JSON configuration for each server
- Filesystem server grants access to specific directory
- Must restart Claude Desktop after config changes

**Segment 3: GitHub MCP Server Setup**
- Requires GitHub Personal Access Token
- Token scopes: repo, read:user
- Direct access to prompt library
- No more copy-paste from GitHub

**Segment 4: MCP in Workflows Preview**
- Claude+MCP can access templates directly
- Workflows can leverage MCP context
- Week 6 covers full integration

### Demo Recap

**What Was Demonstrated:**
Configuring filesystem MCP server and testing file access.

**Key Steps:**
1. Located Claude Desktop config file
2. Added filesystem server configuration
3. Restarted Claude Desktop
4. Tested with "read my file" request

**Result:**
Claude successfully reading local files via MCP.

---

## Self-Paced Exercises

**Total Time:** 60 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 5.1 | 25 min | Working MCP + `mcp-setup.md` | Filesystem server |
| 5.2 | 20 min | GitHub MCP + test results | GitHub server |
| 5.3 | 15 min | MCP generation test + sample | Practical application |

---

### Exercise 5.1: Configure Claude Desktop MCP

**Duration:** 25 minutes

**Purpose:**
Set up MCP foundation by configuring Claude Desktop with filesystem server access to your prompt files.

**You Will Create:**
Working MCP configuration and documentation of setup.

---

#### Instructions

**Step 1: Verify Prerequisites (3 min)**

- [ ] Claude Desktop is installed
- [ ] Node.js is installed (required for npx command)
- [ ] You have a folder with your Block 1 prompt files

**To check Node.js:** Open terminal/command prompt, type `node --version`. If not installed, download from nodejs.org.

**Step 2: Locate Config File (5 min)**

**Mac:**
1. Open Finder
2. Press Cmd+Shift+G
3. Enter: `~/Library/Application Support/Claude/`
4. Look for `claude_desktop_config.json`
5. If file doesn't exist, you'll create it

**Windows:**
1. Open File Explorer
2. Type `%APPDATA%\Claude\` in address bar
3. Look for `claude_desktop_config.json`
4. If file doesn't exist, you'll create it

**Step 3: Create/Edit Configuration (8 min)**

Open the config file in a text editor (or create new file if needed).

Add this configuration (replace path with YOUR path):

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/your/actual/path/to/prompts"]
    }
  }
}
```

**Path Examples:**
- Mac: `/Users/yourname/Documents/prompt-library`
- Windows: `C:/Users/yourname/Documents/prompt-library` (use forward slashes!)

**Step 4: Restart Claude Desktop (2 min)**

1. Quit Claude Desktop completely (Cmd+Q on Mac, close all windows on Windows)
2. Relaunch Claude Desktop
3. Wait for it to fully load

**Step 5: Test Filesystem Access (5 min)**

In Claude Desktop, try these prompts:

1. "What files are in my prompts directory?"
2. "Read my style.json file" (or any file you know exists)
3. "List all markdown files in my prompt library"

**Step 6: Document Configuration (2 min)**

Create `mcp-setup.md` with your configuration details.

---

#### Deliverable Specification

**File Name:** `mcp-setup.md`

**Location:** Your Block 2 folder in GitHub repository

**Quality Criteria:**
- [ ] Filesystem server configured correctly
- [ ] Claude can list files in directory
- [ ] Claude can read file contents
- [ ] Configuration documented

---

#### Template

```markdown
# MCP Configuration

**Date:** [YYYY-MM-DD]
**Claude Desktop Version:** [Version number]

## Filesystem Server

**Status:** [Working / Not Working]

**Configuration:**
```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "[your-path]"]
    }
  }
}
```

**Allowed Directory:** [Full path]

**Test Results:**

| Test | Result | Notes |
|------|--------|-------|
| List files in directory | Pass/Fail | |
| Read file contents | Pass/Fail | |
| Navigate subdirectories | Pass/Fail | |

## Capabilities Confirmed

- [ ] Can list files in directory
- [ ] Can read file contents
- [ ] Can navigate subdirectories
- [ ] Can read style.json
- [ ] Can read prompt templates

## Issues Encountered

[Document any issues and how you resolved them]

## Notes

[Any additional observations]
```

---

#### Tips & Troubleshooting

**Tips:**
- Use a JSON validator (jsonlint.com) before saving config
- Always restart Claude Desktop after config changes
- Use absolute paths, not relative paths

**Common Issues:**

| Problem | Solution |
|---------|----------|
| JSON syntax error | Check for trailing commas, missing quotes |
| "Server not found" | Verify Node.js is installed, check npx works |
| Can't find files | Check path is correct, use forward slashes |
| Claude shows no MCP tools | Full restart of Claude Desktop |

---

### Exercise 5.2: Configure GitHub MCP Server

**Duration:** 20 minutes

**Purpose:**
Connect Claude to your GitHub repositories for direct access to your prompt library.

**You Will Create:**
Working GitHub MCP configuration with tested repository access.

---

#### Instructions

**Step 1: Create GitHub Personal Access Token (7 min)**

1. Go to GitHub.com and sign in
2. Click your profile picture → Settings
3. Scroll down to "Developer settings" (bottom left)
4. Click "Personal access tokens" → "Tokens (classic)"
5. Click "Generate new token" → "Generate new token (classic)"
6. Give it a name: "MCP Access"
7. Set expiration (recommend 90 days for security)
8. Select scopes:
   - [x] repo (Full control of private repositories)
   - [x] read:user (Read user profile data)
9. Click "Generate token"
10. **COPY THE TOKEN IMMEDIATELY** - you won't see it again!

**Step 2: Add GitHub Server to Config (5 min)**

Open your `claude_desktop_config.json` and update:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/your/path"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_your_actual_token_here"
      }
    }
  }
}
```

**Step 3: Restart and Test (5 min)**

1. Restart Claude Desktop completely
2. Test with these prompts:
   - "List the repositories I have access to"
   - "Show me the README from my [repo-name] repository"
   - "Read my proposal template from [repo]/templates/proposal.md"

**Step 4: Document Results (3 min)**

Update your `mcp-setup.md` with GitHub configuration.

---

#### Deliverable Specification

**Update:** `mcp-setup.md` with GitHub server section

**Quality Criteria:**
- [ ] GitHub token created with correct scopes
- [ ] Claude can list repositories
- [ ] Claude can read file from repository
- [ ] Configuration documented

---

#### Template Addition

```markdown
## GitHub Server

**Status:** [Working / Not Working]

**Token Created:** [Date]
**Token Expiration:** [Date]
**Token Scopes:** repo, read:user

**Configuration:**
```json
"github": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-github"],
  "env": {
    "GITHUB_PERSONAL_ACCESS_TOKEN": "[token-hidden]"
  }
}
```

**Test Results:**

| Test | Result | Notes |
|------|--------|-------|
| List repositories | Pass/Fail | |
| Read README | Pass/Fail | |
| Read template file | Pass/Fail | |

## Security Notes

- Token stored in local config file only
- Token expires: [Date]
- Minimum required scopes used
```

---

### Exercise 5.3: MCP-Powered Generation Test

**Duration:** 15 minutes

**Purpose:**
Use MCP to have Claude read your templates directly and generate output, demonstrating the practical value of MCP integration.

**You Will Create:**
Documentation of MCP-powered generation including output sample.

---

#### Instructions

**Step 1: Create MCP-Powered Prompt (5 min)**

In Claude Desktop, send this prompt (customize with your repo name):

```
First, read my style.json from my GitHub repository at [your-repo-name]/resources/style.json.

Then, read my proposal template from [your-repo-name]/templates/proposal-template.md.

Using the style guide and template structure, create a proposal for:
- Client: Test Company Inc.
- Project: Digital Transformation Assessment
- Timeline: 3 months
- Budget: $150,000

Follow the template structure exactly and apply the style guide throughout.
```

**Step 2: Verify MCP Usage (3 min)**

Watch Claude's response:
- Does it confirm reading the files via MCP?
- Does the output match your style.json guidelines?
- Does it follow your template structure?

**Step 3: Compare to Manual Approach (3 min)**

Think about the manual alternative:
- How long would it take to copy style.json and paste it?
- How long to copy the template?
- What's the time difference?

**Step 4: Document Results (4 min)**

Create documentation of the test.

---

#### Deliverable Specification

**File Name:** `mcp-generation-test.md`

**Location:** Your Block 2 folder in GitHub repository

**Also save:** Sample output from the MCP-powered generation

**Quality Criteria:**
- [ ] MCP successfully read files
- [ ] Output reflects style guide
- [ ] Output follows template structure
- [ ] Time comparison documented

---

#### Template

```markdown
# MCP-Powered Generation Test

**Date:** [YYYY-MM-DD]

## Process

1. Sent prompt to Claude Desktop with MCP active
2. Claude read style.json via GitHub MCP
3. Claude read template via GitHub MCP
4. Generated proposal using both

## Files Read via MCP

| File | Source | Success |
|------|--------|---------|
| style.json | [repo]/resources/style.json | Yes/No |
| proposal-template.md | [repo]/templates/proposal-template.md | Yes/No |

## Results

**Time to Complete:** [X] minutes

**Quality Assessment:**
- Style adherence: [How well did it follow style.json?]
- Template structure: [Did it follow the template?]
- Overall quality: [Assessment]

## Comparison to Manual Approach

| Aspect | Manual | MCP-Powered |
|--------|--------|-------------|
| Time to gather context | [X] min | 0 min |
| Copy-paste errors | Possible | None |
| Style guide included | Sometimes forgotten | Always included |
| Total time | [X] min | [Y] min |
| Time saved | - | [Z] min |

## Sample Output

[Paste first section of generated output here as evidence]

## Observations

- [What worked well]
- [What could be improved]
- [How this changes your workflow]
```

---

## Templates & Resources

### Templates Provided This Week

| Template | Purpose | Location |
|----------|---------|----------|
| MCP Setup Documentation | Track configuration | Exercise 5.1 |
| Generation Test Documentation | Document MCP value | Exercise 5.3 |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| MCP Server Registry | Reference | [github.com/modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) | Finding servers |
| Claude Desktop Download | Tool | [claude.ai/download](https://claude.ai/download) | Installation |
| MCP Documentation | Reference | [modelcontextprotocol.io](https://modelcontextprotocol.io/) | Understanding protocol |
| GitHub Token Creation | Guide | [docs.github.com](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) | Token setup |
| Node.js Download | Tool | [nodejs.org](https://nodejs.org/) | If npx fails |
| JSON Validator | Tool | [jsonlint.com](https://jsonlint.com/) | Config debugging |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next week, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Configure MCP in Claude Desktop | Config file working | ☐ |
| 2 | Use filesystem MCP server | Can list and read local files | ☐ |
| 3 | Use GitHub MCP server | Can read from repositories | ☐ |
| 4 | Apply MCP to real task | Generation test successful | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| MCP Configuration | `mcp-setup.md` | GitHub | ☐ |
| Working filesystem server | N/A | Claude Desktop | ☐ |
| Working GitHub server | N/A | Claude Desktop | ☐ |
| Generation test | `mcp-generation-test.md` | GitHub | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** How does MCP change your interaction with Claude?

2. **What's still fuzzy?** Any configuration or security aspects unclear?

3. **How much time will MCP save?** Based on your test, what's the actual time difference?

4. **What else could you connect?** What other MCP servers from Week 1 analysis look useful now?

---

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, usually answered within 24 hours
- **Peer Discussion** - Share config tips with cohort

### Common Questions This Week

**Q: My config file changes don't take effect.**
A: Did you fully restart Claude Desktop? Quit completely (check no processes running), then relaunch.

**Q: I get "command not found: npx"**
A: Node.js isn't installed. Download from nodejs.org and install it.

**Q: JSON syntax error but I can't see what's wrong.**
A: Paste your config into jsonlint.com - it will show exactly where the error is.

---

## Looking Ahead

### Next Week Preview: Week 6 - Integration Patterns

**Focus:**
Building fully integrated workflows that combine MCP, automation platforms, and quality systems.

**How It Builds on This Week:**
Your working MCP configuration enables Claude to pull templates directly into workflows.

**To Prepare:**
- [ ] Complete all Week 5 exercises
- [ ] Ensure MCP is working reliably
- [ ] Test with multiple file types
- [ ] Review your workflow architecture

---

## Glossary

| Term | Definition |
|------|------------|
| MCP | Model Context Protocol - standard for AI-tool connections |
| Host | The application running AI (Claude Desktop) |
| Server | Pre-built connector providing capabilities to AI |
| Personal Access Token | GitHub authentication credential for API access |
| npx | Node.js command to run packages without installing |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-01-01 | Initial guide created |

---

**Navigation:** [← Week 4](../week-4/participant-guide.md) | **Week 5** | [Week 6 →](../week-6/participant-guide.md)
