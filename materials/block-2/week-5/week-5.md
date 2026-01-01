# Week 5: MCP Integration Basics

**Block:** 2 - AI Workflow Engineering
**Duration:** 45 min live workshop + 60 min self-paced exercises

---

## Entry Criteria

- [ ] Two optimized workflows running
- [ ] Claude Desktop installed
- [ ] MCP servers identified (from Week 1)
- [ ] Understanding of workflow data flow

## Exit Criteria

- [ ] MCP configured in Claude Desktop
- [ ] At least one MCP server connected and functional
- [ ] Workflow integrated with MCP capability
- [ ] MCP security considerations understood
- [ ] GitHub MCP server working

---

## Workshop Content (45 minutes)

### Segment 1: MCP Architecture Deep Dive (12 min)

**How MCP works:**

```
Claude Desktop ← MCP Protocol → MCP Server → External Tool
     ↓                                            ↓
  Your Prompts                              Files, APIs, Data
```

**Key concepts:**
- **Host:** Claude Desktop (the AI interface)
- **Server:** Bridge to external capabilities
- **Tools:** Specific actions a server provides
- **Resources:** Data sources a server exposes

**Security model:**
- Servers run locally (your machine)
- No data sent to third parties (unless server does)
- You control which servers are active
- Permission prompts for sensitive operations

### Segment 2: Setting Up Your First MCP Server (15 min)

**Claude Desktop configuration:**

- Location (Mac): `~/Library/Application Support/Claude/claude_desktop_config.json`
- Location (Windows): `%APPDATA%\Claude\claude_desktop_config.json`

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

**Live demo:** Configure filesystem server

**Testing the connection:**
- Restart Claude Desktop
- Verify server appears in tools
- Test a simple operation

### Segment 3: GitHub MCP Server Setup (10 min)

**Why GitHub MCP:**
- Direct access to your prompt library
- Read templates without copy/paste
- Create/update files automatically
- Version control awareness

**Configuration:**

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

**Token creation:**
- GitHub → Settings → Developer Settings → Personal Access Tokens
- Required scopes: repo, read:user

### Segment 4: MCP in Workflows (8 min)

**Connecting the dots:**
- Claude with MCP can access your templates
- Workflow can trigger Claude operations
- End-to-end: Trigger → Claude+MCP → Quality Check → Output

**Integration patterns:**
- Claude generates using GitHub templates directly
- Output saved back to repository
- Automatic version tracking

**Next week:** Full integration patterns

---

## Self-Paced Exercises (60 minutes total)

### Exercise 5.1: Configure Claude Desktop MCP (25 minutes)

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

---

### Exercise 5.2: Configure GitHub MCP Server (20 minutes)

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
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/prompts"]
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

---

### Exercise 5.3: MCP-Powered Generation Test (15 minutes)

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

---

## Key Takeaways

1. **MCP connects AI to tools** - Direct access to files, repos, APIs
2. **Configuration is JSON-based** - Easy to set up and version control
3. **Security is local-first** - Servers run on your machine
4. **GitHub integration is powerful** - Direct access to prompt library
5. **MCP enables true automation** - No more copy/paste

---

## Preparation for Week 6

- Ensure MCP is working reliably
- Test with multiple file types
- Consider: What other MCP servers would be useful?
- Next week: Full integration patterns

---

## Resources

- [MCP Server Registry](https://github.com/modelcontextprotocol/servers)
- [Claude Desktop Download](https://claude.ai/download)
- [MCP Documentation](https://modelcontextprotocol.io/)
- [GitHub Personal Access Tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
