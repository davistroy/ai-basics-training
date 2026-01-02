# **Advanced Module 5: Advanced GitHub & DevOps for AI Systems**

## **2 Weeks | 45 min live + 75 min homework per week**

-----

## **Prerequisites**

- Block 3 Certification: AI Automation Architect
- Basic Git/GitHub familiarity (commits, branches, pull requests)
- Understanding of CI/CD concepts
- Working AI workflows to version and deploy
- GitHub account with repository access

-----

## **Module Overview**

**Target Audience:** Block 3 graduates who want to implement professional DevOps practices for AI systems, including CI/CD pipelines, version control strategies, and production deployment workflows.

**Learning Objectives:**
- Design and implement GitHub Actions workflows for AI system automation
- Apply version control best practices for prompts, configurations, and AI artifacts
- Build CI/CD pipelines that validate and deploy AI workflows
- Implement branch strategies suitable for AI development teams
- Create automated testing and quality gates for AI systems

**Capstone:** Production-Ready AI DevOps System
- Complete CI/CD pipeline implementation
- Versioned prompt/configuration repository
- Automated testing and deployment workflows
- Monitoring and alerting integration

-----

## **Week 1: GitHub Actions & Version Control Fundamentals**

### **Entry Criteria**

- [ ] Block 3 completed with working autonomous agent system
- [ ] GitHub repository created for AI workflows
- [ ] Basic understanding of YAML syntax
- [ ] At least 3 prompt templates ready for version control

### **Exit Criteria**

- [ ] GitHub Actions workflow created and running
- [ ] Prompt validation automation implemented
- [ ] Version control strategy defined and documented
- [ ] First automated test suite passing
- [ ] Branch protection rules configured

-----

### **Workshop Content (45 minutes)**

**Segment 1: GitHub Actions Architecture (12 min)**

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

**Segment 2: Version Control for AI Artifacts (12 min)**

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

**Segment 3: Automated Testing for AI Workflows (12 min)**

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

**Segment 4: Quality Gates and Branch Protection (9 min)**

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

### **Self-Paced Exercises (75 minutes total)**

**Exercise 1.1: Create Your First AI Validation Workflow (25 minutes)**

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

**Exercise 1.2: Implement Prompt Versioning System (25 minutes)**

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

**Exercise 1.3: Build Automated Test Suite (25 minutes)**

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

## **Week 2: Advanced DevOps Patterns**

### **Entry Criteria**

- [ ] Week 1 exercises completed
- [ ] GitHub Actions workflow running successfully
- [ ] Version control structure implemented
- [ ] Basic test suite passing

### **Exit Criteria**

- [ ] Deployment strategy implemented (blue-green or canary)
- [ ] Secrets management configured
- [ ] Monitoring and alerting operational
- [ ] Complete CI/CD pipeline functional
- [ ] Production deployment documented

-----

### **Workshop Content (45 minutes)**

**Segment 1: Deployment Strategies for AI Systems (12 min)**

- **Blue-Green deployments:**
  - Deploy to inactive slot
  - Run smoke tests
  - Switch traffic on success
  - Rollback by switching back

  ```yaml
  steps:
    - name: Deploy to inactive slot
      run: ./scripts/deploy-prompts.sh --slot $TARGET

    - name: Run smoke tests
      run: ./scripts/smoke-test.sh --slot $TARGET

    - name: Switch traffic
      if: success()
      run: curl -X POST $CONFIG_API/switch-slot
  ```

- **Canary deployments:**
  - Deploy to small percentage (10%)
  - Monitor metrics (error rate, latency, satisfaction)
  - Progressive rollout (25%, 50%, 75%, 100%)
  - Automatic rollback on failure

- **Choosing a strategy:**
  | Strategy | Best For | Risk Level | Complexity |
  |----------|----------|------------|------------|
  | Blue-Green | Fast rollback needed | Low | Medium |
  | Canary | Gradual validation | Low | High |
  | Rolling | Resource constrained | Medium | Low |

**Segment 2: Secrets & Configuration Management (12 min)**

- **GitHub Secrets hierarchy:**
  ```
  Repository Secrets:
  ├── AI_API_KEY
  ├── DEPLOYMENT_TOKEN
  └── MONITORING_WEBHOOK

  Environment Secrets:
  ├── staging/
  │   └── AI_API_KEY (staging)
  └── production/
      └── AI_API_KEY (production)
  ```

- **Configuration as code:**
  ```yaml
  # configs/environments/production.yml
  ai:
    provider: openai
    model: gpt-4
    settings:
      temperature: 0.7
      max_tokens: 2000

  rate_limits:
    requests_per_minute: 100

  monitoring:
    error_threshold: 0.02
  ```

- **Security best practices:**
  - Never commit secrets to code
  - Use environment-specific secrets
  - Pin actions to SHA for security
  - Limit workflow permissions

**Segment 3: Monitoring & Observability (12 min)**

- **Health check workflows:**
  ```yaml
  on:
    schedule:
      - cron: '*/15 * * * *'  # Every 15 minutes

  jobs:
    health-check:
      steps:
        - name: Check AI endpoint health
          run: |
            RESPONSE=$(curl -s $AI_HEALTH_ENDPOINT)
            # Parse and validate response

        - name: Alert on failure
          if: failure()
          run: curl -X POST $SLACK_WEBHOOK -d '...'
  ```

- **Key metrics to track:**
  - Request volume and success rate
  - Response latency (p50, p95, p99)
  - Token usage vs. limits
  - Error rate by type

- **Alerting patterns:**
  - Error rate > 5% for 5 minutes → Critical
  - Latency p95 > 2000ms for 10 minutes → Warning
  - Health check failure → Immediate alert

**Segment 4: Complete CI/CD Pipeline Assembly (9 min)**

- **Full pipeline stages:**
  ```
  Push → Validate → Test → Build → Stage → Approve → Deploy → Monitor
  ```

- **Pipeline workflow structure:**
  ```yaml
  jobs:
    validate:
      # Syntax, schema, security checks

    test:
      needs: validate
      # Unit and integration tests

    staging:
      needs: test
      environment: staging
      # Auto-deploy to staging

    production:
      needs: staging
      environment: production
      # Manual approval + canary deployment
  ```

- **Environment protection rules:**
  - Required reviewers for production
  - Wait timer between deployments
  - Deployment branch restrictions

-----

### **Self-Paced Exercises (75 minutes total)**

**Exercise 2.1: Implement Deployment Strategy (30 minutes)**

*Design and implement a deployment workflow for your AI system*

**Scenario:** Your team manages prompts for a customer-facing chatbot. You need to:
- Deploy prompt updates with zero downtime
- Quickly rollback if issues arise
- Validate changes before full rollout

**Deliverables:**
1. Design document with:
   - Chosen deployment strategy (with justification)
   - Workflow diagram
   - Rollback procedure
2. Implemented deployment workflow in `.github/workflows/`

-----

**Exercise 2.2: Configure Monitoring and Alerting (25 minutes)**

*Create a monitoring solution for your AI workflows*

**Requirements:**
1. Health check workflow running every 15 minutes
2. Alert on failures via Slack, Discord, or email
3. Track key metrics over time
4. Generate weekly summary (optional)

**Deliverable:** Monitoring workflow + alert configuration

-----

**Exercise 2.3: Module Capstone - Complete CI/CD Pipeline (20 minutes)**

*Assemble all components into a production-ready pipeline*

**Requirements:**
1. **Validation Stage:** Syntax, schema, security checks
2. **Test Stage:** Unit and integration tests with coverage
3. **Staging Deployment:** Auto-deploy on merge to develop
4. **Production Deployment:** Manual approval + canary/blue-green

**Deliverable:** Complete `.github/workflows/` directory with:
- `validate.yml` - Validation workflow
- `test.yml` - Test workflow
- `deploy-staging.yml` - Staging deployment
- `deploy-production.yml` - Production deployment with approval
- `monitoring.yml` - Health checks and alerting

-----

## **Assessment Rubric**

### Practical Assessment (70%)

| Component | Points | Criteria |
|-----------|--------|----------|
| CI Pipeline | 20 | Complete validation, testing, quality gates |
| Deployment Workflow | 20 | Blue-green or canary with rollback |
| Version Control | 15 | Proper branching, versioning, tagging |
| Monitoring | 15 | Health checks, alerting, dashboards |

### Written Assessment (30%)

| Component | Points | Criteria |
|-----------|--------|----------|
| Architecture Design | 15 | Clear diagrams, justified decisions |
| Documentation | 15 | Complete, accurate, maintainable |

### Grading Scale

| Grade | Score | Description |
|-------|-------|-------------|
| Exceptional | 90-100% | Production-ready implementation |
| Proficient | 80-89% | Solid implementation, minor gaps |
| Developing | 70-79% | Core concepts, needs refinement |
| Beginning | Below 70% | Significant gaps, needs review |

-----

## **APPENDICES**

### **Appendix A: GitHub Actions Reference**

#### Commonly Used Actions

| Action | Purpose | Example |
|--------|---------|---------|
| `actions/checkout@v4` | Clone repository | Required for most workflows |
| `actions/setup-node@v4` | Setup Node.js | JavaScript/TypeScript projects |
| `actions/setup-python@v5` | Setup Python | Python-based tooling |
| `actions/cache@v4` | Cache dependencies | Speed up builds |
| `actions/upload-artifact@v4` | Store build outputs | Test results, coverage |
| `actions/github-script@v7` | Run GitHub API calls | PR comments, issues |

#### Workflow Syntax Quick Reference

```yaml
# Conditional execution
jobs:
  deploy:
    if: github.ref == 'refs/heads/main'

# Matrix builds
jobs:
  test:
    strategy:
      matrix:
        node: [18, 20, 22]
        os: [ubuntu-latest, macos-latest]
    runs-on: ${{ matrix.os }}

# Job dependencies
jobs:
  build:
    runs-on: ubuntu-latest
  test:
    needs: build
  deploy:
    needs: [build, test]

# Environment protection
jobs:
  deploy:
    environment:
      name: production
      url: https://app.example.com
```

-----

### **Appendix B: Troubleshooting Guide**

#### Common Issues and Solutions

| Issue | Cause | Solution |
|-------|-------|----------|
| Workflow not triggering | Path filters not matching | Check `paths` configuration |
| Secrets not available | Wrong environment scope | Verify secret environment |
| Cache not restoring | Key mismatch | Review cache key generation |
| Deployment failing | Permission denied | Check environment protection rules |
| Tests timing out | Resource constraints | Increase timeout or optimize tests |

#### Debug Mode

```yaml
# Enable debug logging
env:
  ACTIONS_STEP_DEBUG: true
  ACTIONS_RUNNER_DEBUG: true

# Add debug outputs
- name: Debug context
  run: |
    echo "Event: ${{ github.event_name }}"
    echo "Ref: ${{ github.ref }}"
    echo "SHA: ${{ github.sha }}"
```

-----

### **Appendix C: Security Checklist**

#### Pre-Deployment Security Review

- [ ] No secrets in code or config files
- [ ] All sensitive values use GitHub Secrets
- [ ] Environment protection rules configured
- [ ] Branch protection enabled
- [ ] Required reviews for production changes
- [ ] Audit logging enabled
- [ ] Dependency scanning active
- [ ] Secret scanning enabled

#### Secure Workflow Patterns

```yaml
# Pin actions to SHA for security
- uses: actions/checkout@8ade135a41bc03ea155e62e844d188df1ea18608  # v4.1.1

# Limit permissions
permissions:
  contents: read
  pull-requests: write

# Use OIDC for cloud authentication
- uses: aws-actions/configure-aws-credentials@v4
  with:
    role-to-assume: arn:aws:iam::123456789:role/GitHubActions
    aws-region: us-east-1
```
