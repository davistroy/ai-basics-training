# Block 2 Quick Reference Card
## AI Workflow Engineering

---

## Workflow Design Pattern

```
[Trigger] → [Data Gather] → [AI Process] → [Quality Check] → [Route] → [Output]
                                                 ↓
                                          [Human Review]
```

---

## When to Automate vs. Keep Manual

| Automate | Keep Manual |
|----------|-------------|
| >10x/month frequency | <5x/month |
| Low-medium stakes | High-stakes client |
| Recoverable errors | Zero-tolerance |
| Predictable patterns | Highly variable |
| Transactional | Relationship-critical |

---

## Quality Gate Logic

```
IF score >= 4.0 THEN
    → Proceed to output
ELSE IF score >= 3.0 THEN
    → Flag for human review
ELSE
    → Regenerate OR escalate
END IF
```

---

## MCP Configuration Template

**File Location:**
- Mac: `~/Library/Application Support/Claude/claude_desktop_config.json`
- Windows: `%APPDATA%\Claude\claude_desktop_config.json`

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
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_xxxxx"
      }
    }
  }
}
```

**After editing:** Fully quit and restart Claude Desktop

---

## Quality Evaluation Prompt

```markdown
Evaluate this [deliverable] against these criteria.
Score each 1-5 with brief justification.

Criteria:
1. [Criterion from rubric]
2. [Criterion from rubric]
3. [Criterion from rubric]

Output as JSON:
{
  "scores": {...},
  "overall_score": X.X,
  "pass": true/false,
  "suggestions": [...]
}

Pass threshold: 3.5
```

---

## Workflow Documentation Checklist

- [ ] Architecture diagram
- [ ] Trigger configuration
- [ ] Step-by-step flow
- [ ] AI prompt/template used
- [ ] Quality criteria
- [ ] Error handling
- [ ] Output destinations
- [ ] Test results

---

## Cost Optimization Tactics

| Tactic | Impact |
|--------|--------|
| Shorter prompts | Fewer tokens = lower cost |
| Summarize before passing | Reduce context size |
| Use smaller models for simple tasks | 10-50x cheaper |
| Cache repeated lookups | Avoid redundant calls |
| Skip unnecessary steps | Faster + cheaper |

---

## Performance Metrics to Track

| Category | Metrics |
|----------|---------|
| Volume | Executions/day |
| Speed | Avg duration, P95 |
| Quality | Success rate, scores |
| Cost | $/execution, total |
| Reliability | Error rate, retries |

---

## MCP Troubleshooting Quick Check

1. ✓ JSON valid? (jsonlint.com)
2. ✓ File in right location?
3. ✓ Claude fully restarted?
4. ✓ Node.js installed?
5. ✓ Paths exist?
6. ✓ No trailing commas?

---

## Key Reminders

✓ Micro-agents: 3-20 steps, bounded scope
✓ More context often = worse performance
✓ Log everything from day one
✓ Test error handling deliberately
✓ MCP runs locally—your data stays yours
