# Advanced Module 5: Advanced GitHub & DevOps for AI Systems

## Module Overview

| Attribute | Details |
|-----------|---------|
| **Duration** | 2 weeks |
| **Prerequisites** | Block 3 completion, basic Git/GitHub familiarity |
| **Difficulty** | Advanced |
| **Focus** | CI/CD pipelines, GitHub Actions, version control for AI workflows |

### Learning Objectives

By the end of this module, participants will be able to:

1. Design and implement GitHub Actions workflows for AI system automation
2. Apply version control best practices for prompts, configurations, and AI artifacts
3. Build CI/CD pipelines that validate and deploy AI workflows
4. Implement branch strategies suitable for AI development teams
5. Create automated testing and quality gates for AI systems

---

## Week 1: GitHub Actions & CI/CD Fundamentals

### Workshop 1.1: GitHub Actions Architecture (45 minutes)

#### Understanding GitHub Actions Components

```yaml
# .github/workflows/ai-workflow-validation.yml
name: AI Workflow Validation Pipeline

on:
  push:
    branches: [main, develop]
    paths:
      - 'prompts/**'
      - 'workflows/**'
      - 'configs/**'
  pull_request:
    branches: [main]
  workflow_dispatch:
    inputs:
      environment:
        description: 'Target environment'
        required: true
        default: 'staging'
        type: choice
        options:
          - staging
          - production

env:
  AI_MODEL_VERSION: "gpt-4"
  VALIDATION_THRESHOLD: "0.85"

jobs:
  validate-prompts:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'
          cache: 'npm'

      - name: Install dependencies
        run: npm ci

      - name: Validate prompt syntax
        run: npm run validate:prompts

      - name: Run prompt linting
        run: npm run lint:prompts
```

#### Workflow Triggers Deep Dive

| Trigger | Use Case | Example |
|---------|----------|---------|
| `push` | Validate on code changes | Prompt syntax checks |
| `pull_request` | Gate merges with validation | Quality reviews |
| `schedule` | Regular maintenance tasks | Daily prompt testing |
| `workflow_dispatch` | Manual deployments | Production releases |
| `repository_dispatch` | External system triggers | Webhook integrations |

#### Exercise 1.1: Create Your First AI Validation Workflow

**Objective**: Build a workflow that validates prompt files on every push

**Steps**:
1. Create `.github/workflows/` directory in your repository
2. Add a validation workflow file
3. Configure triggers for your prompt directories
4. Add validation steps

**Starter Template**:

```yaml
name: Prompt Validation

on:
  push:
    paths:
      - 'prompts/**/*.md'
      - 'prompts/**/*.txt'

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Check prompt file structure
        run: |
          echo "Validating prompt files..."
          # Add your validation logic here
          find prompts -name "*.md" -exec echo "Checking: {}" \;

      - name: Verify required sections
        run: |
          # Check that each prompt has required sections
          for file in prompts/**/*.md; do
            if [ -f "$file" ]; then
              echo "Validating: $file"
              # Add section validation
            fi
          done
```

---

### Workshop 1.2: Version Control for AI Artifacts (45 minutes)

#### Prompt Versioning Strategies

**Strategy 1: Semantic Versioning for Prompts**

```
prompts/
├── customer-support/
│   ├── v1.0.0/
│   │   └── ticket-response.md
│   ├── v1.1.0/
│   │   └── ticket-response.md
│   └── v2.0.0/
│       └── ticket-response.md
├── content-generation/
│   ├── v1.0.0/
│   │   └── blog-writer.md
│   └── v1.2.0/
│       └── blog-writer.md
└── VERSION_MANIFEST.json
```

**VERSION_MANIFEST.json**:

```json
{
  "prompts": {
    "customer-support/ticket-response": {
      "current": "2.0.0",
      "deprecated": ["1.0.0"],
      "supported": ["1.1.0", "2.0.0"]
    },
    "content-generation/blog-writer": {
      "current": "1.2.0",
      "deprecated": [],
      "supported": ["1.0.0", "1.2.0"]
    }
  },
  "lastUpdated": "2024-01-15T10:30:00Z"
}
```

**Strategy 2: Git Tags for Release Management**

```bash
# Tag a prompt release
git tag -a prompts-v1.2.0 -m "Release: Updated customer support prompts"

# Tag with metadata
git tag -a prompts-v1.2.0 -m "
Release: Customer Support Prompts v1.2.0

Changes:
- Improved tone for escalation scenarios
- Added multi-language support templates
- Fixed formatting in response templates

Testing:
- Passed 95% satisfaction threshold
- A/B tested against v1.1.0 (12% improvement)
"

# Push tags
git push origin prompts-v1.2.0
```

#### Branch Strategy for AI Development

```
main (production prompts)
│
├── develop (integration branch)
│   │
│   ├── feature/new-customer-prompt
│   │   └── Experimental prompt development
│   │
│   ├── feature/multilingual-support
│   │   └── Adding language variants
│   │
│   └── experiment/gpt4-optimization
│       └── Testing with new model
│
├── release/v2.0
│   └── Release candidate preparation
│
└── hotfix/urgent-prompt-fix
    └── Emergency production fixes
```

#### Exercise 1.2: Implement Prompt Versioning

**Objective**: Set up a versioned prompt structure with manifest tracking

**Deliverables**:
1. Create versioned directory structure
2. Implement VERSION_MANIFEST.json
3. Add a script to validate manifest consistency
4. Create git hooks for version validation

---

### Workshop 1.3: Automated Testing for AI Workflows (45 minutes)

#### Testing Pyramid for AI Systems

```
                    ┌─────────────────┐
                    │   E2E Tests     │  ← Full workflow execution
                    │   (Few, Slow)   │     with real AI calls
                   ─┼─────────────────┼─
                  / │ Integration     │ \  ← Workflow component
                 /  │ Tests           │  \    interaction tests
                /   │ (Some, Medium)  │   \
               ─────┼─────────────────┼─────
              /     │   Unit Tests    │     \  ← Prompt validation,
             /      │   (Many, Fast)  │      \   config checks
            /       │                 │       \
           ─────────┴─────────────────┴─────────
```

#### Unit Tests for Prompts

```javascript
// tests/prompts/customer-support.test.js
const { validatePrompt, checkTokenCount } = require('../utils/prompt-validator');
const fs = require('fs');

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
    const tokenCount = checkTokenCount(promptContent);
    expect(tokenCount).toBeLessThan(4000);
  });

  test('should not contain placeholder text', () => {
    expect(promptContent).not.toMatch(/\[INSERT.*\]/i);
    expect(promptContent).not.toMatch(/TODO:/i);
    expect(promptContent).not.toMatch(/FIXME:/i);
  });

  test('should have valid variable placeholders', () => {
    const variables = promptContent.match(/\{\{(\w+)\}\}/g) || [];
    const validVariables = ['customer_name', 'ticket_id', 'issue_summary', 'priority'];

    variables.forEach(variable => {
      const varName = variable.replace(/\{\{|\}\}/g, '');
      expect(validVariables).toContain(varName);
    });
  });
});
```

#### Integration Tests for Workflows

```javascript
// tests/workflows/support-workflow.integration.test.js
const { WorkflowRunner } = require('../utils/workflow-runner');
const { MockAIProvider } = require('../mocks/ai-provider');

describe('Customer Support Workflow Integration', () => {
  let workflow;
  let mockAI;

  beforeEach(() => {
    mockAI = new MockAIProvider();
    workflow = new WorkflowRunner({
      aiProvider: mockAI,
      configPath: 'workflows/customer-support/config.json'
    });
  });

  test('should process ticket through complete workflow', async () => {
    const ticket = {
      id: 'TEST-001',
      customer: 'John Doe',
      issue: 'Cannot login to account',
      priority: 'high'
    };

    mockAI.setResponse('classify', { category: 'authentication', confidence: 0.95 });
    mockAI.setResponse('respond', { message: 'Password reset instructions...', tone: 'helpful' });

    const result = await workflow.process(ticket);

    expect(result.status).toBe('completed');
    expect(result.classification.category).toBe('authentication');
    expect(result.response.tone).toBe('helpful');
    expect(mockAI.callCount).toBe(2);
  });

  test('should handle AI provider errors gracefully', async () => {
    mockAI.simulateError('classify', new Error('Rate limit exceeded'));

    const ticket = { id: 'TEST-002', issue: 'Test issue' };
    const result = await workflow.process(ticket);

    expect(result.status).toBe('error');
    expect(result.fallback).toBe(true);
    expect(result.errorType).toBe('rate_limit');
  });
});
```

#### GitHub Actions Test Workflow

```yaml
# .github/workflows/test-ai-workflows.yml
name: AI Workflow Tests

on:
  pull_request:
    branches: [main, develop]

jobs:
  unit-tests:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Install dependencies
        run: npm ci

      - name: Run prompt unit tests
        run: npm run test:prompts

      - name: Run config validation tests
        run: npm run test:configs

  integration-tests:
    runs-on: ubuntu-latest
    needs: unit-tests
    steps:
      - uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Install dependencies
        run: npm ci

      - name: Run integration tests
        run: npm run test:integration
        env:
          AI_PROVIDER: mock

      - name: Upload test results
        uses: actions/upload-artifact@v4
        if: always()
        with:
          name: test-results
          path: coverage/

  quality-gate:
    runs-on: ubuntu-latest
    needs: [unit-tests, integration-tests]
    steps:
      - name: Check test coverage threshold
        run: |
          COVERAGE=$(cat coverage/coverage-summary.json | jq '.total.lines.pct')
          if (( $(echo "$COVERAGE < 80" | bc -l) )); then
            echo "Coverage $COVERAGE% is below 80% threshold"
            exit 1
          fi
          echo "Coverage $COVERAGE% meets threshold"
```

---

### Week 1 Homework (60-75 minutes)

#### Assignment 1: Build a Complete CI Pipeline

Create a GitHub Actions workflow that:

1. **Validates** all prompt files for required structure
2. **Tests** prompt token counts stay within limits
3. **Checks** for deprecated prompt versions
4. **Reports** validation results as PR comments

**Acceptance Criteria**:
- Workflow triggers on PRs to main branch
- All validation steps must pass for merge
- Failed checks provide actionable error messages
- Results posted as PR comment

#### Assignment 2: Implement Git Hooks

Set up local git hooks for:

1. **Pre-commit**: Validate prompt syntax
2. **Pre-push**: Run unit tests
3. **Commit-msg**: Enforce conventional commits

**Deliverable**: `.githooks/` directory with working hooks

---

## Week 2: Advanced DevOps Patterns

### Workshop 2.1: Deployment Strategies for AI Systems (45 minutes)

#### Blue-Green Deployments for Prompts

```yaml
# .github/workflows/blue-green-deploy.yml
name: Blue-Green Prompt Deployment

on:
  workflow_dispatch:
    inputs:
      version:
        description: 'Prompt version to deploy'
        required: true
      environment:
        description: 'Target environment'
        required: true
        type: choice
        options:
          - staging
          - production

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: ${{ inputs.environment }}

    steps:
      - uses: actions/checkout@v4
        with:
          ref: prompts-v${{ inputs.version }}

      - name: Determine current slot
        id: current
        run: |
          CURRENT=$(curl -s ${{ secrets.CONFIG_API }}/active-slot)
          echo "slot=$CURRENT" >> $GITHUB_OUTPUT
          echo "Current active slot: $CURRENT"

      - name: Deploy to inactive slot
        id: deploy
        run: |
          if [ "${{ steps.current.outputs.slot }}" == "blue" ]; then
            TARGET="green"
          else
            TARGET="blue"
          fi
          echo "target=$TARGET" >> $GITHUB_OUTPUT

          # Deploy prompts to target slot
          ./scripts/deploy-prompts.sh \
            --slot $TARGET \
            --version ${{ inputs.version }} \
            --environment ${{ inputs.environment }}

      - name: Run smoke tests
        run: |
          ./scripts/smoke-test.sh \
            --slot ${{ steps.deploy.outputs.target }} \
            --environment ${{ inputs.environment }}

      - name: Switch traffic
        if: success()
        run: |
          curl -X POST ${{ secrets.CONFIG_API }}/switch-slot \
            -H "Authorization: Bearer ${{ secrets.DEPLOY_TOKEN }}" \
            -d '{"slot": "${{ steps.deploy.outputs.target }}"}'

      - name: Rollback on failure
        if: failure()
        run: |
          echo "Deployment failed, keeping traffic on ${{ steps.current.outputs.slot }}"
          # Cleanup failed deployment
          ./scripts/cleanup-slot.sh --slot ${{ steps.deploy.outputs.target }}
```

#### Canary Deployments

```yaml
# .github/workflows/canary-deploy.yml
name: Canary Prompt Deployment

jobs:
  canary-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Deploy canary (10% traffic)
        run: |
          ./scripts/deploy-canary.sh \
            --version ${{ inputs.version }} \
            --traffic-percentage 10

      - name: Monitor canary metrics
        id: monitor
        run: |
          # Wait and collect metrics
          sleep 300  # 5 minutes

          METRICS=$(./scripts/collect-metrics.sh --deployment canary)
          ERROR_RATE=$(echo $METRICS | jq '.errorRate')
          LATENCY=$(echo $METRICS | jq '.p95Latency')
          SATISFACTION=$(echo $METRICS | jq '.satisfactionScore')

          echo "error_rate=$ERROR_RATE" >> $GITHUB_OUTPUT
          echo "latency=$LATENCY" >> $GITHUB_OUTPUT
          echo "satisfaction=$SATISFACTION" >> $GITHUB_OUTPUT

      - name: Evaluate canary health
        id: evaluate
        run: |
          if (( $(echo "${{ steps.monitor.outputs.error_rate }} > 0.05" | bc -l) )); then
            echo "healthy=false" >> $GITHUB_OUTPUT
            echo "reason=Error rate too high" >> $GITHUB_OUTPUT
          elif (( $(echo "${{ steps.monitor.outputs.satisfaction }} < 0.80" | bc -l) )); then
            echo "healthy=false" >> $GITHUB_OUTPUT
            echo "reason=Satisfaction score too low" >> $GITHUB_OUTPUT
          else
            echo "healthy=true" >> $GITHUB_OUTPUT
          fi

      - name: Progressive rollout
        if: steps.evaluate.outputs.healthy == 'true'
        run: |
          for percentage in 25 50 75 100; do
            ./scripts/update-traffic.sh --percentage $percentage
            sleep 180  # Wait 3 minutes between increases

            # Verify health at each stage
            ./scripts/health-check.sh || exit 1
          done

      - name: Rollback canary
        if: steps.evaluate.outputs.healthy == 'false'
        run: |
          echo "Canary unhealthy: ${{ steps.evaluate.outputs.reason }}"
          ./scripts/rollback-canary.sh
          exit 1
```

#### Exercise 2.1: Design a Deployment Strategy

**Scenario**: Your team manages prompts for a customer-facing chatbot. You need to:
- Deploy prompt updates with zero downtime
- Quickly rollback if issues arise
- Validate changes before full rollout

**Deliverable**: Design document with:
1. Chosen deployment strategy (with justification)
2. Workflow diagram
3. Rollback procedure
4. Monitoring requirements

---

### Workshop 2.2: Secrets & Configuration Management (45 minutes)

#### GitHub Secrets Management

```yaml
# Secrets hierarchy for AI workflows
Repository Secrets:
├── AI_API_KEY                 # AI provider authentication
├── DEPLOYMENT_TOKEN           # Deployment automation
└── MONITORING_WEBHOOK         # Alerting integration

Environment Secrets:
├── staging/
│   ├── AI_API_KEY            # Staging AI credentials
│   └── DATABASE_URL          # Staging database
└── production/
    ├── AI_API_KEY            # Production AI credentials
    └── DATABASE_URL          # Production database
```

#### Configuration as Code

```yaml
# configs/environments/production.yml
ai:
  provider: openai
  model: gpt-4
  settings:
    temperature: 0.7
    max_tokens: 2000
    timeout_seconds: 30

prompts:
  version: "2.1.0"
  cache_ttl: 3600

rate_limits:
  requests_per_minute: 100
  tokens_per_minute: 40000

monitoring:
  error_threshold: 0.02
  latency_p95_threshold_ms: 2000

feature_flags:
  new_classification_prompt: false
  enhanced_response_format: true
```

#### Secure Configuration Workflow

```yaml
# .github/workflows/config-deployment.yml
name: Deploy Configuration

on:
  push:
    paths:
      - 'configs/**'
    branches: [main]

jobs:
  validate-config:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Validate YAML syntax
        run: |
          pip install yamllint
          yamllint configs/

      - name: Validate against schema
        run: |
          pip install jsonschema pyyaml
          python scripts/validate-config-schema.py

      - name: Check for secrets in config
        run: |
          # Ensure no secrets are committed in config files
          if grep -rE "(api_key|password|secret|token):\s*['\"]?[a-zA-Z0-9]+" configs/; then
            echo "ERROR: Potential secrets found in config files!"
            exit 1
          fi

  deploy-config:
    needs: validate-config
    runs-on: ubuntu-latest
    environment: production
    steps:
      - uses: actions/checkout@v4

      - name: Deploy configuration
        run: |
          ./scripts/deploy-config.sh \
            --env production \
            --config configs/environments/production.yml
        env:
          DEPLOY_TOKEN: ${{ secrets.DEPLOY_TOKEN }}
```

---

### Workshop 2.3: Monitoring & Observability (45 minutes)

#### GitHub Actions for Monitoring

```yaml
# .github/workflows/ai-health-check.yml
name: AI System Health Check

on:
  schedule:
    - cron: '*/15 * * * *'  # Every 15 minutes
  workflow_dispatch:

jobs:
  health-check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Check AI endpoint health
        id: health
        run: |
          RESPONSE=$(curl -s -w "\n%{http_code}" ${{ secrets.AI_HEALTH_ENDPOINT }})
          HTTP_CODE=$(echo "$RESPONSE" | tail -1)
          BODY=$(echo "$RESPONSE" | head -n -1)

          echo "status_code=$HTTP_CODE" >> $GITHUB_OUTPUT
          echo "response=$BODY" >> $GITHUB_OUTPUT

          if [ "$HTTP_CODE" != "200" ]; then
            echo "healthy=false" >> $GITHUB_OUTPUT
          else
            echo "healthy=true" >> $GITHUB_OUTPUT
          fi

      - name: Check response quality
        id: quality
        run: |
          # Test with sample prompt
          RESULT=$(./scripts/test-prompt.sh --prompt "test-health-check")
          QUALITY_SCORE=$(echo $RESULT | jq '.qualityScore')

          echo "quality_score=$QUALITY_SCORE" >> $GITHUB_OUTPUT

          if (( $(echo "$QUALITY_SCORE < 0.8" | bc -l) )); then
            echo "quality_ok=false" >> $GITHUB_OUTPUT
          else
            echo "quality_ok=true" >> $GITHUB_OUTPUT
          fi

      - name: Alert on failure
        if: steps.health.outputs.healthy == 'false' || steps.quality.outputs.quality_ok == 'false'
        run: |
          curl -X POST ${{ secrets.SLACK_WEBHOOK }} \
            -H "Content-Type: application/json" \
            -d '{
              "text": "🚨 AI System Health Check Failed",
              "blocks": [
                {
                  "type": "section",
                  "text": {
                    "type": "mrkdwn",
                    "text": "*Health Check Results*\n• Endpoint Status: ${{ steps.health.outputs.status_code }}\n• Quality Score: ${{ steps.quality.outputs.quality_score }}"
                  }
                }
              ]
            }'

      - name: Update status page
        run: |
          curl -X POST ${{ secrets.STATUS_API }}/update \
            -H "Authorization: Bearer ${{ secrets.STATUS_TOKEN }}" \
            -d '{
              "component": "ai-service",
              "status": "${{ steps.health.outputs.healthy == 'true' && 'operational' || 'degraded' }}",
              "metrics": {
                "healthScore": ${{ steps.health.outputs.status_code == '200' && 1 || 0 }},
                "qualityScore": ${{ steps.quality.outputs.quality_score }}
              }
            }'
```

#### Metrics Dashboard Configuration

```yaml
# monitoring/dashboard-config.yml
dashboards:
  ai-operations:
    title: "AI Workflow Operations"
    refresh: 30s

    panels:
      - title: "Request Volume"
        type: graph
        metrics:
          - ai_requests_total
          - ai_requests_success
          - ai_requests_failed

      - title: "Response Latency"
        type: graph
        metrics:
          - ai_response_latency_p50
          - ai_response_latency_p95
          - ai_response_latency_p99
        thresholds:
          warning: 1000
          critical: 2000

      - title: "Token Usage"
        type: gauge
        metrics:
          - ai_tokens_used
          - ai_tokens_limit

      - title: "Error Rate"
        type: stat
        metrics:
          - ai_error_rate
        thresholds:
          warning: 0.01
          critical: 0.05

alerts:
  - name: "High Error Rate"
    condition: ai_error_rate > 0.05
    duration: 5m
    severity: critical
    notify:
      - slack: "#ai-alerts"
      - pagerduty: "ai-oncall"

  - name: "Elevated Latency"
    condition: ai_response_latency_p95 > 2000
    duration: 10m
    severity: warning
    notify:
      - slack: "#ai-alerts"
```

---

### Week 2 Homework (60-75 minutes)

#### Assignment 1: Complete CI/CD Pipeline

Build a production-ready CI/CD pipeline that includes:

1. **Validation Stage**: Syntax, schema, security checks
2. **Test Stage**: Unit and integration tests
3. **Staging Deployment**: Auto-deploy to staging
4. **Production Deployment**: Manual approval + canary

**Deliverable**: Complete `.github/workflows/` directory with all workflows

#### Assignment 2: Monitoring Implementation

Create a monitoring solution that:

1. Runs health checks every 15 minutes
2. Alerts on failures via Slack/Discord
3. Tracks key metrics over time
4. Generates weekly summary reports

**Deliverable**: Monitoring workflow + documentation

---

## Assessment Rubric

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

---

## Appendix A: GitHub Actions Reference

### Commonly Used Actions

| Action | Purpose | Example |
|--------|---------|---------|
| `actions/checkout@v4` | Clone repository | Required for most workflows |
| `actions/setup-node@v4` | Setup Node.js | JavaScript/TypeScript projects |
| `actions/setup-python@v5` | Setup Python | Python-based tooling |
| `actions/cache@v4` | Cache dependencies | Speed up builds |
| `actions/upload-artifact@v4` | Store build outputs | Test results, coverage |
| `actions/github-script@v7` | Run GitHub API calls | PR comments, issues |

### Workflow Syntax Quick Reference

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

---

## Appendix B: Troubleshooting Guide

### Common Issues and Solutions

| Issue | Cause | Solution |
|-------|-------|----------|
| Workflow not triggering | Path filters not matching | Check `paths` configuration |
| Secrets not available | Wrong environment scope | Verify secret environment |
| Cache not restoring | Key mismatch | Review cache key generation |
| Deployment failing | Permission denied | Check environment protection rules |
| Tests timing out | Resource constraints | Increase timeout or optimize tests |

### Debug Mode

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
    echo "Actor: ${{ github.actor }}"
```

---

## Appendix C: Security Checklist

### Pre-Deployment Security Review

- [ ] No secrets in code or config files
- [ ] All sensitive values use GitHub Secrets
- [ ] Environment protection rules configured
- [ ] Branch protection enabled
- [ ] Required reviews for production changes
- [ ] Audit logging enabled
- [ ] Dependency scanning active
- [ ] Secret scanning enabled

### Secure Workflow Patterns

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
