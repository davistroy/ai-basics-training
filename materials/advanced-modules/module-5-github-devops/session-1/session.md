# **Session 1: GitHub Actions & Version Control Fundamentals**

**Advanced Module 5: Advanced GitHub & DevOps for AI Systems**
**Session Duration:** 45 min workshop + 75 min self-paced exercises

-----

## **Entry Criteria**

- [ ] Block 3 completed with working autonomous agent system
- [ ] GitHub repository created for AI workflows
- [ ] Basic understanding of YAML syntax
- [ ] At least 3 prompt templates ready for version control

## **Exit Criteria**

- [ ] GitHub Actions workflow created and running
- [ ] Prompt validation automation implemented
- [ ] Version control strategy defined and documented
- [ ] First automated test suite passing
- [ ] Branch protection rules configured

-----

## **Workshop Content (45 minutes)**

### **Segment 1: GitHub Actions Architecture (12 min)**

- **GitHub Actions components:**
  - Workflows, jobs, steps, and actions
  - Triggers: push, pull_request, schedule, workflow_dispatch
  - Runners and execution environments
  - Secrets and environment variables

- **AI-specific workflow pattern:**
  ```yaml
  name: AI Workflow Validation Pipeline

  on:
    push:
      paths:
        - 'prompts/**'
        - 'workflows/**'
        - 'configs/**'
    pull_request:
      branches: [main]

  jobs:
    validate-prompts:
      runs-on: ubuntu-latest
      steps:
        - uses: actions/checkout@v4
        - name: Validate prompt syntax
          run: npm run validate:prompts
  ```

- **When to use different triggers:**
  | Trigger | Use Case | Example |
  |---------|----------|---------|
  | `push` | Validate on code changes | Prompt syntax checks |
  | `pull_request` | Gate merges with validation | Quality reviews |
  | `schedule` | Regular maintenance tasks | Daily prompt testing |
  | `workflow_dispatch` | Manual deployments | Production releases |

### **Segment 2: Version Control for AI Artifacts (12 min)**

- **Prompt versioning strategies:**
  - Semantic versioning (v1.0.0, v1.1.0, v2.0.0)
  - Directory-based versioning
  - Git tags for release management

- **Version manifest pattern:**
  ```json
  {
    "prompts": {
      "customer-support/ticket-response": {
        "current": "2.0.0",
        "deprecated": ["1.0.0"],
        "supported": ["1.1.0", "2.0.0"]
      }
    },
    "lastUpdated": "2024-01-15T10:30:00Z"
  }
  ```

- **Branch strategy for AI development:**
  ```
  main (production prompts)
  ├── develop (integration branch)
  │   ├── feature/new-customer-prompt
  │   ├── feature/multilingual-support
  │   └── experiment/gpt4-optimization
  ├── release/v2.0
  └── hotfix/urgent-prompt-fix
  ```

### **Segment 3: Automated Testing for AI Workflows (12 min)**

- **Testing pyramid for AI systems:**
  - Unit tests: Prompt validation, syntax checks, token limits
  - Integration tests: Workflow component interaction
  - E2E tests: Full workflow execution with mock AI

- **Unit test example:**
  ```javascript
  describe('Customer Support Prompts', () => {
    test('should have required sections', () => {
      expect(promptContent).toContain('## System Context');
      expect(promptContent).toContain('## Instructions');
      expect(promptContent).toContain('## Output Format');
    });

    test('should be within token limits', () => {
      const tokenCount = checkTokenCount(promptContent);
      expect(tokenCount).toBeLessThan(4000);
    });
  });
  ```

- **GitHub Actions test workflow pattern:**
  ```yaml
  jobs:
    unit-tests:
      runs-on: ubuntu-latest
      steps:
        - uses: actions/checkout@v4
        - name: Run prompt unit tests
          run: npm run test:prompts

    integration-tests:
      needs: unit-tests
      runs-on: ubuntu-latest
      steps:
        - name: Run integration tests
          run: npm run test:integration
  ```

### **Segment 4: Quality Gates and Branch Protection (9 min)**

- **Required status checks:**
  - Prompt validation must pass
  - Tests must succeed
  - Coverage thresholds met

- **Branch protection rules:**
  - Require pull request reviews
  - Require status checks before merge
  - Restrict push access to main

- **Quality gate workflow pattern:**
  ```yaml
  quality-gate:
    needs: [unit-tests, integration-tests]
    steps:
      - name: Check test coverage threshold
        run: |
          COVERAGE=$(cat coverage/coverage-summary.json | jq '.total.lines.pct')
          if (( $(echo "$COVERAGE < 80" | bc -l) )); then
            echo "Coverage $COVERAGE% is below 80% threshold"
            exit 1
          fi
  ```

-----

## **Self-Paced Exercises (75 minutes total)**

### **Exercise 1.1: Create Your First AI Validation Workflow (25 minutes)**

*Build a workflow that validates prompt files on every push*

**Steps:**
1. Create `.github/workflows/` directory in your repository
2. Add a validation workflow file (`prompt-validation.yml`)
3. Configure triggers for your prompt directories
4. Add validation steps for:
   - File structure check
   - Required sections verification
   - Token count validation

**Starter Template:**
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
              # Add section validation
            fi
          done
```

**Deliverable:** Working GitHub Actions workflow that runs on push

-----

### **Exercise 1.2: Implement Prompt Versioning System (25 minutes)**

*Set up a versioned prompt structure with manifest tracking*

**Steps:**
1. Create versioned directory structure:
   ```
   prompts/
   ├── customer-support/
   │   ├── v1.0.0/
   │   └── v2.0.0/
   └── VERSION_MANIFEST.json
   ```
2. Implement VERSION_MANIFEST.json with current/deprecated/supported versions
3. Create a validation script that checks manifest consistency
4. Add git hooks for version validation

**Deliverable:** Versioned prompt structure with working manifest

-----

### **Exercise 1.3: Build Automated Test Suite (25 minutes)**

*Create tests for your prompt library*

**Steps:**
1. Set up testing framework (Jest, Mocha, or similar)
2. Create unit tests for:
   - Required section presence
   - Token count limits
   - No placeholder text remaining
   - Valid variable placeholders
3. Add tests to your GitHub Actions workflow
4. Configure coverage reporting

**Deliverable:** Test suite with 80%+ coverage on prompt validation

-----
