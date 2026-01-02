# **ADVANCED MODULE 5 SESSION 1: GitHub Actions & Version Control Fundamentals**

**Module:** Advanced Module 5: Advanced GitHub & DevOps for AI Systems
**Session:** 1 of 2
**Estimated Self-Paced Time:** 75 minutes

-----

## Navigation

**Module Navigation:** **Session 1** | [Session 2 →](../session-2/participant-guide.md)

**In This Guide:**
- [Learning Objectives](#learning-objectives)
- [Key Concepts](#key-concepts)
- [Workshop Recap](#workshop-recap)
- [Self-Paced Exercises](#self-paced-exercises)
- [Templates & Resources](#templates--resources)
- [Self-Assessment](#self-assessment)
- [Getting Help](#getting-help)

-----

## Learning Objectives

By the end of this session, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Design and implement GitHub Actions workflows for AI system validation | Exercise 1.1 |
| 2 | Apply version control strategies for prompts and AI configurations | Exercise 1.2 |
| 3 | Create automated test suites for AI workflows | Exercise 1.3 |
| 4 | Configure quality gates and branch protection rules | All Exercises |

-----

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Block 3 certification with working autonomous agent system
- [ ] GitHub account created with repository access
- [ ] Basic understanding of YAML syntax (or willingness to learn)
- [ ] At least 3 prompt templates in your repository

**Not ready?** Review Block 3 materials or reach out in the support channel for help.

-----

## Key Concepts

### Concept 1: GitHub Actions Workflows

**Definition:**
GitHub Actions is GitHub's built-in automation platform. Workflows are automated processes defined in YAML files that run validation, testing, and deployment tasks.

**Why It Matters:**
Automated validation catches errors before they reach production. Instead of manually testing every change, workflows run automatically on every commit, pull request, or schedule.

**Core Principle:**
> Automate everything that's checkable. Humans focus on creativity, automation handles consistency.

**Example:**
```yaml
name: AI Workflow Validation Pipeline

on:
  push:
    paths:
      - 'prompts/**'

jobs:
  validate-prompts:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Validate prompt syntax
        run: npm run validate:prompts
```

**Common Mistake:**
Creating workflows in the wrong directory. Workflows MUST be in `.github/workflows/` or GitHub won't recognize them.

-----

### Concept 2: Semantic Versioning for AI Artifacts

**Definition:**
Semantic versioning (semver) uses MAJOR.MINOR.PATCH format to give meaning to version numbers. For AI artifacts like prompts and configurations, this communicates the type and scope of changes.

**Why It Matters:**
Version numbers with semantic meaning enable safe deployments, clear deprecation tracking, and coordination across environments (staging vs. production).

**The Pattern:**
```
v1.0.0 → v1.1.0 → v2.0.0

MAJOR: Breaking changes (v1 → v2)
MINOR: New features, backward compatible (v1.0 → v1.1)
PATCH: Bug fixes, no new functionality (v1.0.0 → v1.0.1)
```

**When to Use:**
- Use semantic versioning for all production AI artifacts
- Track versions in directory structure and manifest files
- Apply git tags to mark release versions

**When NOT to Use:**
- Don't use for experimental prompts that won't be deployed
- Don't version internal development iterations (use branches instead)

-----

### Concept 3: Automated Testing for AI Systems

**Definition:**
Automated tests validate AI workflows programmatically - checking structure, constraints, and behavior without human intervention.

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| **Unit Tests** | Fast, focused checks on individual components | Prompt has required sections |
| **Integration Tests** | Validate component interaction | Workflow components work together |
| **E2E Tests** | Complete workflow execution validation | Full system test with mock AI |

**Visual Reference:**
```
    ┌─────────────────────────┐
    │   E2E Tests (Fewest)    │  Slow, complete validation
    └───────────┬─────────────┘
                │
    ┌───────────▼─────────────┐
    │  Integration Tests      │  Component interaction
    └───────────┬─────────────┘
                │
    ┌───────────▼─────────────┐
    │   Unit Tests (Most)     │  Fast, focused checks
    └─────────────────────────┘

    Testing Pyramid for AI Systems
```

-----

### Quick Reference: GitHub Actions Triggers

**When to run workflows:**

| Trigger | Purpose | Example Use Case |
|---------|---------|------------------|
| `on: push` | Validate every code change | Prompt syntax checks |
| `on: pull_request` | Gate merges with validation | Quality review before production |
| `on: schedule` | Regular maintenance | Daily prompt testing |
| `on: workflow_dispatch` | Manual execution | Production deployments |

-----

## Workshop Recap

### Session Summary

**Today's Focus:** Building automated validation pipelines and version control for AI artifacts using GitHub Actions.

**Key Points from Each Segment:**

**Segment 1: GitHub Actions Architecture**
- GitHub Actions automates quality checks with workflows, jobs, and steps
- Triggers determine when workflows run (push, pull_request, schedule, manual)
- Workflows run in clean environments (runners) with full GitHub integration
- Key takeaway: Automation catches errors humans miss

**Segment 2: Version Control for AI Artifacts**
- Semantic versioning (MAJOR.MINOR.PATCH) gives meaning to version numbers
- Directory-based versioning keeps multiple versions accessible
- VERSION_MANIFEST.json tracks current, deprecated, and supported versions
- Key takeaway: Version numbers should communicate what changed

**Segment 3: Automated Testing for AI Workflows**
- Testing pyramid: Most unit tests, some integration tests, few E2E tests
- Unit tests validate structure and constraints (fast, reliable)
- GitHub Actions runs tests automatically on every commit
- Key takeaway: Build strong foundation of fast unit tests

**Segment 4: Quality Gates and Branch Protection**
- Required status checks block merges if validation fails
- Branch protection prevents direct pushes to main
- Multiple layers of protection catch different error types
- Key takeaway: If it doesn't pass all checks, it doesn't merge

### Demo Recap

**What Was Demonstrated:**
Creating a GitHub Actions workflow that validates prompt files on every push.

**Key Steps:**
1. Created `.github/workflows/` directory in repository
2. Added `prompt-validation.yml` workflow file with push trigger
3. Defined validation job with checkout and validation steps
4. Committed and pushed to trigger workflow
5. Verified execution in GitHub Actions tab

**Result:**
Automated validation that runs on every commit, catching errors before code review.

-----

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 1.1 | 25 min | Working GitHub Actions workflow | Workflow creation, triggers, validation |
| 1.2 | 25 min | Versioned directory + manifest | Semantic versioning, version tracking |
| 1.3 | 25 min | Test suite with 80%+ coverage | Unit testing, automated validation |

-----

### Exercise 1.1: Create Your First AI Validation Workflow

**Duration:** 25 minutes

**Purpose:**
Build a GitHub Actions workflow that automatically validates prompt files on every push. This establishes the foundation for continuous integration.

**You Will Create:**
- `.github/workflows/prompt-validation.yml` file
- Validation steps that check prompt structure and constraints
- Automated workflow that runs on every push

-----

#### Instructions

**Step 1: Create Workflow Directory**

In your GitHub repository, create the workflows directory:
```bash
mkdir -p .github/workflows
```

This directory MUST be exactly `.github/workflows/` for GitHub to recognize your workflows.

**Step 2: Create Validation Workflow File**

Create `.github/workflows/prompt-validation.yml` with this starter content:

```yaml
name: Prompt Validation

on:
  push:
    paths:
      - 'prompts/**/*.md'

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Check prompt file structure
        run: |
          echo "Validating prompt files..."
          find prompts -name "*.md" -exec echo "Checking: {}" \;

      - name: Verify required sections
        run: |
          for file in prompts/**/*.md; do
            if [ -f "$file" ]; then
              echo "Validating: $file"
              # Check for required sections
              if ! grep -q "## System Context" "$file"; then
                echo "ERROR: Missing 'System Context' section in $file"
                exit 1
              fi
              if ! grep -q "## Instructions" "$file"; then
                echo "ERROR: Missing 'Instructions' section in $file"
                exit 1
              fi
            fi
          done
```

**Step 3: Customize Validation Checks**

Add validation for your specific requirements:
- Token count validation (if you have a token counting tool)
- Check for placeholder text like `[TODO]` or `[REPLACE]`
- Validate variable placeholders format (e.g., `{{variable_name}}`)

Example token count check:
```yaml
      - name: Check token limits
        run: |
          # This is a placeholder - implement with your token counting tool
          echo "Token count validation would run here"
```

**Step 4: Commit and Push**

```bash
git add .github/workflows/prompt-validation.yml
git commit -m "Add prompt validation workflow"
git push origin main
```

**Step 5: Verify Workflow Execution**

1. Go to your GitHub repository
2. Click the "Actions" tab
3. You should see "Prompt Validation" workflow running
4. Click on the workflow run to see step-by-step execution
5. Verify all steps pass (green checkmarks)

**Step 6: Review Your Work**

Check that your deliverable includes:
- [ ] `.github/workflows/prompt-validation.yml` exists
- [ ] Workflow has correct YAML syntax (no syntax errors in Actions tab)
- [ ] Workflow triggers on push to prompts directory
- [ ] At least 2 validation steps are defined
- [ ] Workflow runs successfully in Actions tab

-----

#### Deliverable Specification

**File Name:** `.github/workflows/prompt-validation.yml`

**Location:** Must be in `.github/workflows/` directory at repository root

**Format Requirements:**
- Valid YAML syntax (indentation with spaces, not tabs)
- `name:` field defines workflow name
- `on:` field defines trigger(s)
- `jobs:` field defines at least one job with validation steps

**Quality Criteria:**
- [ ] Workflow appears in GitHub Actions tab
- [ ] Workflow runs on push to prompts directory
- [ ] Validation steps execute successfully
- [ ] Clear error messages if validation fails

-----

#### Example

**Scenario:** Validating customer support prompts

**Input:**
Prompts directory with multiple markdown files:
```
prompts/
├── customer-support/
│   ├── ticket-response.md
│   └── escalation.md
```

**Output:**
Workflow file that validates structure:

```yaml
name: Customer Support Prompt Validation

on:
  push:
    paths:
      - 'prompts/customer-support/**/*.md'

jobs:
  validate-prompts:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Validate required sections
        run: |
          for file in prompts/customer-support/*.md; do
            echo "Checking $file"
            grep -q "## System Context" "$file" || (echo "Missing System Context in $file" && exit 1)
            grep -q "## Instructions" "$file" || (echo "Missing Instructions in $file" && exit 1)
            grep -q "## Output Format" "$file" || (echo "Missing Output Format in $file" && exit 1)
          done

      - name: Check for placeholders
        run: |
          if grep -r "\[TODO\]\|\[REPLACE\]" prompts/customer-support/; then
            echo "ERROR: Found placeholder text in prompts"
            exit 1
          fi
          echo "No placeholders found"
```

**Why This Works:**
- Trigger is specific to customer-support directory
- Each validation step does one thing
- Exit codes (exit 1) fail the workflow if checks don't pass
- Clear echo messages show what's being validated

-----

#### Tips & Troubleshooting

**Tips:**
- Start simple - get one validation step working before adding complexity
- Test locally with bash before adding to workflow
- Use `echo` statements liberally for debugging
- Check Actions tab for detailed error messages

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Workflow doesn't appear in Actions | Check file is in `.github/workflows/` (exact path) |
| YAML syntax error | Validate indentation (use spaces, not tabs), check https://yamlchecker.com |
| Workflow doesn't trigger | Verify trigger paths match your directory structure |
| Steps fail but shouldn't | Check file paths are correct, bash syntax is valid |

-----

### Exercise 1.2: Implement Prompt Versioning System

**Duration:** 25 minutes

**Purpose:**
Set up a versioned prompt structure with semantic versioning and manifest tracking. This enables safe deployments and rollbacks.

**You Will Create:**
- Directory structure with versioned prompts
- VERSION_MANIFEST.json tracking version status
- Documentation explaining versioning strategy

-----

#### Instructions

**Step 1: Create Versioned Directory Structure**

Organize your prompts with semantic versioning:

```bash
mkdir -p prompts/customer-support/v1.0.0
mkdir -p prompts/customer-support/v2.0.0
```

Move existing prompts into versioned directories:
```bash
cp prompts/customer-support/ticket-response.md prompts/customer-support/v1.0.0/
```

**Step 2: Create VERSION_MANIFEST.json**

Create `prompts/VERSION_MANIFEST.json`:

```json
{
  "prompts": {
    "customer-support/ticket-response": {
      "current": "2.0.0",
      "deprecated": ["1.0.0"],
      "supported": ["2.0.0"],
      "changelog": {
        "2.0.0": "Added multilingual support and improved error handling",
        "1.0.0": "Initial version"
      }
    }
  },
  "lastUpdated": "2026-01-02T10:00:00Z",
  "schema": "1.0"
}
```

**Step 3: Document Your Versioning Strategy**

Create `prompts/VERSIONING.md`:

```markdown
# Prompt Versioning Strategy

## Semantic Versioning

We use MAJOR.MINOR.PATCH format:

- **MAJOR**: Breaking changes, incompatible with previous version
- **MINOR**: New features, backward compatible
- **PATCH**: Bug fixes, no functionality changes

## Directory Structure

Each prompt version has its own directory:
```
prompts/
└── <category>/
    ├── v1.0.0/
    ├── v1.1.0/
    └── v2.0.0/
```

## Version Manifest

VERSION_MANIFEST.json tracks:
- **current**: Recommended version for new deployments
- **deprecated**: Versions no longer supported
- **supported**: Actively maintained versions

## Deployment Guidelines

- Production may lag behind current (gradual rollout)
- Deprecated versions generate warnings but still work
- Unsupported versions fail validation
```

**Step 4: Create Validation Script**

Create `scripts/validate-versions.js` (or `.py` if you prefer Python):

```javascript
// Example validation script
const fs = require('fs');
const path = require('path');

const manifestPath = 'prompts/VERSION_MANIFEST.json';
const manifest = JSON.parse(fs.readFileSync(manifestPath, 'utf8'));

console.log('Validating version manifest...');

for (const [promptPath, versions] of Object.entries(manifest.prompts)) {
  console.log(`Checking ${promptPath}`);

  // Verify current version exists
  const currentPath = path.join('prompts', promptPath, `v${versions.current}`);
  if (!fs.existsSync(currentPath)) {
    console.error(`ERROR: Current version ${versions.current} not found at ${currentPath}`);
    process.exit(1);
  }

  // Verify supported versions exist
  for (const version of versions.supported) {
    const versionPath = path.join('prompts', promptPath, `v${version}`);
    if (!fs.existsSync(versionPath)) {
      console.error(`ERROR: Supported version ${version} not found at ${versionPath}`);
      process.exit(1);
    }
  }
}

console.log('Version manifest validation passed!');
```

**Step 5: Review Your Work**

Check that your deliverable includes:
- [ ] Versioned directory structure (v1.0.0, v2.0.0, etc.)
- [ ] VERSION_MANIFEST.json with current/deprecated/supported fields
- [ ] VERSIONING.md documenting your strategy
- [ ] Validation script that checks manifest consistency
- [ ] All referenced versions actually exist in directories

-----

#### Deliverable Specification

**Files:**
- `prompts/VERSION_MANIFEST.json` - Version tracking manifest
- `prompts/VERSIONING.md` - Documentation
- `scripts/validate-versions.js` (or `.py`) - Validation script
- Versioned prompt directories

**Location:**
- Manifest and docs in `prompts/` directory
- Validation script in `scripts/` directory

**Format Requirements:**
- VERSION_MANIFEST.json must be valid JSON
- Directory names must follow vMAJOR.MINOR.PATCH format
- Validation script must exit with code 1 on errors

**Quality Criteria:**
- [ ] Manifest JSON is valid (use JSON validator)
- [ ] All referenced versions exist as directories
- [ ] Validation script runs without errors
- [ ] Documentation clearly explains versioning rules

-----

#### Example

**Complete Version Structure:**

```
prompts/
├── VERSION_MANIFEST.json
├── VERSIONING.md
├── customer-support/
│   ├── v1.0.0/
│   │   └── ticket-response.md
│   └── v2.0.0/
│       └── ticket-response.md
└── sales/
    └── v1.0.0/
        └── lead-qualification.md

scripts/
└── validate-versions.js
```

**VERSION_MANIFEST.json example:**
```json
{
  "prompts": {
    "customer-support/ticket-response": {
      "current": "2.0.0",
      "deprecated": [],
      "supported": ["1.0.0", "2.0.0"]
    },
    "sales/lead-qualification": {
      "current": "1.0.0",
      "deprecated": [],
      "supported": ["1.0.0"]
    }
  },
  "lastUpdated": "2026-01-02T10:00:00Z"
}
```

-----

#### Tips & Troubleshooting

**Tips:**
- Start with one prompt category, then expand
- Keep changelog in manifest for traceability
- Use git tags to mark version releases (e.g., `git tag v2.0.0`)
- Run validation script in GitHub Actions workflow

**Common Issues:**

| Problem | Solution |
|---------|----------|
| JSON validation fails | Use https://jsonlint.com to check syntax |
| Version mismatch | Ensure manifest references match directory names exactly |
| Script can't find files | Check paths are relative to repository root |
| Unclear when to increment MAJOR vs MINOR | MAJOR = breaking changes, MINOR = new features (backward compatible) |

-----

### Exercise 1.3: Build Automated Test Suite

**Duration:** 25 minutes

**Purpose:**
Create a comprehensive test suite for your prompt library with unit tests, integration tests, and automated coverage reporting.

**You Will Create:**
- Test files validating prompt structure and constraints
- Test configuration with coverage reporting
- GitHub Actions workflow running tests automatically

-----

#### Instructions

**Step 1: Set Up Testing Framework**

Install a testing framework (choose one):

**For JavaScript/Node.js:**
```bash
npm init -y  # If no package.json exists
npm install --save-dev jest
```

**For Python:**
```bash
pip install pytest pytest-cov
```

**Step 2: Create Unit Tests**

Create `tests/prompts.test.js` (or `test_prompts.py` for Python):

**JavaScript example:**
```javascript
const fs = require('fs');
const path = require('path');

describe('Customer Support Prompts', () => {
  const promptPath = 'prompts/customer-support/v2.0.0/ticket-response.md';
  let promptContent;

  beforeAll(() => {
    promptContent = fs.readFileSync(promptPath, 'utf8');
  });

  test('should have required sections', () => {
    expect(promptContent).toContain('## System Context');
    expect(promptContent).toContain('## Instructions');
    expect(promptContent).toContain('## Output Format');
  });

  test('should be within token limits', () => {
    // Rough estimate: 1 token ≈ 4 characters
    const estimatedTokens = promptContent.length / 4;
    expect(estimatedTokens).toBeLessThan(4000);
  });

  test('should not contain placeholder text', () => {
    expect(promptContent).not.toContain('[TODO]');
    expect(promptContent).not.toContain('[REPLACE]');
    expect(promptContent).not.toContain('[PLACEHOLDER]');
  });

  test('should have valid variable placeholders', () => {
    // Find all {{variable}} patterns
    const variablePattern = /\{\{([^}]+)\}\}/g;
    const matches = promptContent.match(variablePattern) || [];

    matches.forEach(match => {
      // Variables should be lowercase with underscores
      const variable = match.slice(2, -2);
      expect(variable).toMatch(/^[a-z_]+$/);
    });
  });
});
```

**Python example:**
```python
import os
import re
import pytest

PROMPT_PATH = 'prompts/customer-support/v2.0.0/ticket-response.md'

@pytest.fixture
def prompt_content():
    with open(PROMPT_PATH, 'r') as f:
        return f.read()

def test_required_sections(prompt_content):
    assert '## System Context' in prompt_content
    assert '## Instructions' in prompt_content
    assert '## Output Format' in prompt_content

def test_token_limits(prompt_content):
    # Rough estimate: 1 token ≈ 4 characters
    estimated_tokens = len(prompt_content) / 4
    assert estimated_tokens < 4000

def test_no_placeholders(prompt_content):
    assert '[TODO]' not in prompt_content
    assert '[REPLACE]' not in prompt_content
    assert '[PLACEHOLDER]' not in prompt_content

def test_valid_variable_placeholders(prompt_content):
    # Find all {{variable}} patterns
    variables = re.findall(r'\{\{([^}]+)\}\}', prompt_content)

    for var in variables:
        # Variables should be lowercase with underscores
        assert re.match(r'^[a-z_]+$', var), f"Invalid variable name: {var}"
```

**Step 3: Configure Coverage Reporting**

**For Jest** - Add to `package.json`:
```json
{
  "scripts": {
    "test": "jest",
    "test:coverage": "jest --coverage"
  },
  "jest": {
    "coverageThreshold": {
      "global": {
        "lines": 80,
        "statements": 80
      }
    }
  }
}
```

**For pytest** - Create `pytest.ini`:
```ini
[pytest]
addopts = --cov=. --cov-report=html --cov-report=term
```

**Step 4: Add Tests to GitHub Actions**

Update `.github/workflows/prompt-validation.yml`:

```yaml
jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      # ... existing validation steps ...

  test:
    needs: validate
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Setup Node.js  # Or Python
        uses: actions/setup-node@v4
        with:
          node-version: '18'

      - name: Install dependencies
        run: npm install

      - name: Run tests with coverage
        run: npm run test:coverage

      - name: Check coverage threshold
        run: |
          COVERAGE=$(cat coverage/coverage-summary.json | jq '.total.lines.pct')
          echo "Coverage: $COVERAGE%"
          if (( $(echo "$COVERAGE < 80" | bc -l) )); then
            echo "Coverage $COVERAGE% is below 80% threshold"
            exit 1
          fi
```

**Step 5: Review Your Work**

Check that your deliverable includes:
- [ ] Test files in `tests/` directory
- [ ] Tests cover required sections, token limits, placeholders
- [ ] Coverage reporting configured
- [ ] Tests run in GitHub Actions
- [ ] Coverage threshold >= 80%

-----

#### Deliverable Specification

**Files:**
- `tests/prompts.test.js` (or `test_prompts.py`)
- Test configuration (`package.json` or `pytest.ini`)
- Updated GitHub Actions workflow

**Location:**
- Tests in `tests/` directory
- Configuration at repository root

**Format Requirements:**
- Tests use standard testing framework (Jest, pytest, etc.)
- Coverage reports generated automatically
- Tests exit with code 0 on pass, non-zero on fail

**Quality Criteria:**
- [ ] At least 4 unit tests implemented
- [ ] Tests run successfully locally
- [ ] Tests run in GitHub Actions
- [ ] Coverage >= 80%
- [ ] Clear test names describing what's being tested

-----

#### Example

**Complete test structure:**

```
tests/
├── prompts.test.js
└── version-manifest.test.js

coverage/
├── coverage-summary.json
└── lcov-report/

package.json (with test scripts and coverage config)
.github/workflows/prompt-validation.yml (with test job)
```

**Sample test output:**
```
PASS tests/prompts.test.js
  Customer Support Prompts
    ✓ should have required sections (5ms)
    ✓ should be within token limits (2ms)
    ✓ should not contain placeholder text (3ms)
    ✓ should have valid variable placeholders (4ms)

Test Suites: 1 passed, 1 total
Tests:       4 passed, 4 total
Coverage:    85.7%
```

-----

#### Tips & Troubleshooting

**Tips:**
- Write tests for what breaks most often (missing sections, placeholders)
- Test one thing per test function (easier to debug)
- Use descriptive test names: `test_should_have_required_sections`
- Run tests locally before committing

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Tests can't find prompt files | Check file paths are correct relative to repository root |
| Coverage below 80% | Add more tests or adjust threshold temporarily |
| Tests fail in GitHub Actions but pass locally | Check Node/Python versions match, dependencies installed |
| YAML syntax error in workflow | Validate indentation, check Actions tab for error details |

-----

## Templates & Resources

### Templates Provided This Session

| Template | Purpose | Location |
|----------|---------|----------|
| Workflow Template | GitHub Actions validation workflow | Exercise 1.1 instructions |
| VERSION_MANIFEST Template | Version tracking manifest | Exercise 1.2 instructions |
| Test Suite Template | Unit tests for prompts | Exercise 1.3 instructions |

-----

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| GitHub Actions Docs | Official Documentation | https://docs.github.com/actions | Workflow syntax, triggers, debugging |
| Semantic Versioning Spec | Specification | https://semver.org | Understanding version numbering |
| YAML Validator | Tool | https://yamlchecker.com | Checking workflow YAML syntax |
| JSON Validator | Tool | https://jsonlint.com | Validating VERSION_MANIFEST.json |
| Jest Documentation | Testing Framework | https://jestjs.io | JavaScript testing reference |
| Pytest Documentation | Testing Framework | https://pytest.org | Python testing reference |

-----

### Module Appendix References

For this session's exercises, you may need:

- **Appendix A:** GitHub Actions Reference - Commonly used actions, workflow syntax
- **Appendix B:** Troubleshooting Guide - Common issues and solutions
- **Appendix C:** Security Checklist - Best practices for workflows

See the main module document ([Module 5](../module-5-github-devops.md)) for full appendix content.

-----

## Self-Assessment

### Exit Criteria Checklist

Before moving to next session, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Create GitHub Actions workflows | Exercise 1.1 workflow running in Actions tab | ☐ |
| 2 | Apply semantic versioning to AI artifacts | Exercise 1.2 versioned structure + manifest | ☐ |
| 3 | Build automated test suites | Exercise 1.3 tests passing with 80%+ coverage | ☐ |
| 4 | Configure quality gates | All exercises integrated into CI pipeline | ☐ |

-----

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Exercise 1.1 output | `prompt-validation.yml` | `.github/workflows/` | ☐ |
| Exercise 1.2 output | `VERSION_MANIFEST.json` | `prompts/` | ☐ |
| Exercise 1.3 output | `prompts.test.js` | `tests/` | ☐ |

-----

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?** Which concept or technique suddenly made sense?

2. **What's still fuzzy?** What do you need more practice or clarification on?

3. **How will you apply this?** Name one real work deliverable where you'll use this session's learning.

4. **What surprised you?** Was anything harder or easier than expected?

[Optional: Share insights in support channel to help your peers]

-----

## Getting Help

### Quick Answers
- **Support Channel** - Async questions, check module appendices first
- **Peer Discussion** - Tag your cohort for quick tips

### Common Questions This Session

**Q: My workflow isn't triggering. What's wrong?**
A: Check three things: 1) File is in `.github/workflows/` directory exactly, 2) YAML syntax is valid, 3) Trigger paths match your changes. View Actions tab for error messages.

**Q: How do I know if my YAML syntax is correct?**
A: Use https://yamlchecker.com to validate syntax. Common issues: tabs instead of spaces, incorrect indentation, missing colons.

**Q: What's the difference between deprecated and unsupported versions?**
A: Deprecated versions still work but generate warnings. Unsupported versions fail validation and shouldn't be deployed.

**Q: My tests pass locally but fail in GitHub Actions. Why?**
A: Usually environment differences. Check Node/Python versions match, dependencies are installed, file paths are correct.

**Q: Is 80% coverage too strict?**
A: 80% is a good target for production systems. You can start lower (60-70%) and increase over time.

### When to Ask for Help

- **Before asking:** Check this guide's troubleshooting sections and module appendices
- **Good to ask:** "I tried [X] but got [Y] result. Here's my workflow file..."
- **Include:** Your specific scenario, what you tried, error messages, and expected result

-----

## Looking Ahead

### Next Session Preview: Session 2 - Advanced DevOps Patterns

**Focus:**
Deployment strategies (blue-green, canary), secrets management, monitoring, and building a complete CI/CD pipeline.

**How It Builds on This Session:**
Session 2 extends your validation workflows into production deployment pipelines. You'll add deployment stages, environment management, and monitoring.

**To Prepare:**
- [ ] Complete all Session 1 exercises
- [ ] Ensure GitHub Actions workflows are running successfully
- [ ] Have at least one prompt ready for deployment testing

-----

## Glossary

| Term | Definition |
|------|------------|
| **GitHub Actions** | GitHub's built-in CI/CD automation platform |
| **Workflow** | Automated process defined in YAML file |
| **Job** | Set of steps that execute on same runner |
| **Step** | Individual task in a job |
| **Trigger** | Event that starts a workflow (push, PR, schedule) |
| **Runner** | Virtual machine that executes workflow jobs |
| **Semantic Versioning** | MAJOR.MINOR.PATCH version numbering system |
| **Version Manifest** | JSON file tracking version status |
| **Unit Test** | Fast, focused test of individual component |
| **Coverage** | Percentage of code/logic tested |
| **Quality Gate** | Required check that blocks merge if failed |

-----

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial participant guide created |

-----

**Navigation:** **Session 1** | [Session 2 →](../session-2/participant-guide.md)
