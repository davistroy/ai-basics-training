# Block 1 Quick Reference Card
## AI Prompting Mastery

---

## ASK-CONTEXT-CONSTRAINTS-EXAMPLE Framework

```markdown
## ASK
[What you want the AI to do - be specific]

## CONTEXT
[Background information needed]
- Who is involved
- What situation/project
- Key facts and data

## CONSTRAINTS
[Requirements and limitations]
- Length/format requirements
- Tone specifications
- Things to avoid
- Deadlines

## EXAMPLE
[Sample of desired output]
```

---

## Quality Rubric Format

| Criterion | 5-Excellent | 4-Good | 3-Adequate | 2-Poor | 1-Missing |
|-----------|-------------|--------|------------|--------|-----------|
| [Name] | [Specific description] | [Description] | [Description] | [Description] | [Description] |

**Scoring:** Weight × Score = Weighted Score
**Thresholds:** ≥4 = Ship it | 3-4 = Review | <3 = Redo

---

## LLM-as-Judge Pattern

```markdown
Evaluate the [deliverable] against these criteria:

1. [Criterion 1] - Score 1-5 and explain
2. [Criterion 2] - Score 1-5 and explain
3. [Criterion 3] - Score 1-5 and explain

Based on your evaluation:
- Suggest 3 specific improvements
- Provide a revised version
```

---

## Essential Markdown

| Element | Syntax | Use For |
|---------|--------|---------|
| Header | `# ## ###` | Structure, hierarchy |
| Bold | `**text**` | Emphasis, key terms |
| List | `- item` | Requirements, options |
| Numbered | `1. item` | Steps, sequences |
| Code block | ` ``` ` | Data isolation, examples |
| Table | `\| col \|` | Comparisons, matrices |

**Critical:** Always wrap external data in code blocks to prevent prompt injection

---

## `style.json` Essential Fields

```json
{
  "brand": {
    "name": "Company Name",
    "colors": ["#hex1", "#hex2"]
  },
  "tone": {
    "descriptors": ["Professional", "Concise"],
    "avoid": ["Jargon", "Passive voice"]
  },
  "document_standards": {
    "date_format": "YYYY-MM-DD"
  }
}
```

---

## GitHub Essentials

| Action | How |
|--------|-----|
| Create repo | GitHub.com → New Repository |
| Add file | Upload or create in browser |
| Commit | Save with descriptive message |
| Branch | Create for experiments |
| Pull Request | Propose changes for review |

**Commit Message Format:** `[Type] Brief description`
- Types: `Add`, `Update`, `Fix`, `Remove`

---

## Task Priority Formula

```
Priority = (Frequency × Time × Repetitiveness) + (Value × AI-Suitable)
```

Scale: 1-5 for each factor
Higher score = Better automation candidate

---

## Key Reminders

✓ Structure = Clarity for AI = Better outputs
✓ Always include examples in prompts
✓ Test prompts with real work, not toy examples
✓ Version control your prompts like code
✓ Document for your future self and teammates
