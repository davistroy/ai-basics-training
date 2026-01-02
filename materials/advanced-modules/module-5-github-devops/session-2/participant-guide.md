# **ADVANCED MODULE 5 SESSION 2: Advanced DevOps Patterns**

**Module:** Advanced Module 5: Advanced GitHub & DevOps for AI Systems
**Session:** 2 of 2
**Estimated Self-Paced Time:** 75 minutes

-----

## Navigation

**Module Navigation:** [← Session 1](../session-1/participant-guide.md) | **Session 2**

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
| 1 | Design and implement deployment strategies (blue-green or canary) for AI systems | Exercise 2.1 |
| 2 | Configure secrets management and environment-specific configurations | Exercise 2.3 |
| 3 | Build monitoring and alerting workflows for production AI systems | Exercise 2.2 |
| 4 | Assemble a complete CI/CD pipeline from validation through deployment | Exercise 2.3 (Capstone) |

-----

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Session 1 exercises (validation workflow, versioning, testing)
- [ ] GitHub Actions workflow running successfully
- [ ] Version control structure implemented
- [ ] Basic test suite passing

**Not ready?** Review Session 1 materials or reach out in the support channel for help.

-----

## Key Concepts

### Concept 1: Blue-Green Deployment

**Definition:**
Blue-Green deployment uses two identical production environments. One (Blue) serves live traffic while the other (Green) is idle. Deploy new versions to the idle environment, validate, then switch traffic.

**Why It Matters:**
Zero-downtime deployments with instant rollback capability. If the new version breaks, switch traffic back to the old version immediately.

**Core Principle:**
> Always have a safe fallback. Deploy to inactive, validate, switch traffic.

**The Pattern:**
```
1. Blue is live, Green is idle
2. Deploy new version to Green
3. Run smoke tests on Green
4. If tests pass: Switch traffic to Green
5. If issues arise: Switch back to Blue (instant rollback)
```

**When to Use:**
- Need fast rollback capability
- Have infrastructure for two environments
- Want simple, proven deployment strategy

**When NOT to Use:**
- Very resource-constrained (need two full environments)
- Need gradual rollout validation (use canary instead)

-----

### Concept 2: Canary Deployment

**Definition:**
Canary deployment gradually rolls out new versions by routing a small percentage of traffic to the new version, monitoring metrics, then progressively increasing the percentage if metrics remain healthy.

**Why It Matters:**
Validates new versions with real production traffic while limiting blast radius. Problems affect only a small percentage of users.

**The Pattern:**
```
1. Deploy new version alongside old version
2. Route 10% of traffic to new version
3. Monitor error rate, latency, success metrics
4. If healthy: Increase to 25%, then 50%, then 75%, then 100%
5. If metrics degrade: Auto-rollback to 0%
```

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| **Deployment** | New version deployed to separate instances | v2.0 pods alongside v1.0 pods |
| **Traffic Routing** | Load balancer splits traffic by percentage | 10% to v2.0, 90% to v1.0 |
| **Metrics Monitoring** | Real-time tracking of health signals | Error rate, latency, success rate |
| **Automated Rollback** | Revert if metrics degrade | Error rate > 5% → route 0% to new version |

**Visual Reference:**
```
Traffic Distribution Over Time:

    v1.0    v2.0
T1:  100%    0%    (Initial: Deploy v2.0)
T2:   90%   10%    (Start: 10% canary)
T3:   75%   25%    (Healthy: Increase to 25%)
T4:   50%   50%    (Healthy: Increase to 50%)
T5:   25%   75%    (Healthy: Increase to 75%)
T6:    0%  100%    (Complete: Full rollout)
```

-----

### Concept 3: GitHub Environments and Secrets

**Definition:**
GitHub Environments provide deployment targets (staging, production) with environment-specific secrets and protection rules. Secrets are encrypted values that workflows can access but humans cannot easily view.

**Why It Matters:**
Keeps API keys secure, prevents accidental production deployments, provides audit trails for who deployed what.

**Key Components:**

| Component | Description | Example |
|-----------|-------------|---------|
| **Repository Secrets** | Available to all workflows | Shared monitoring webhook |
| **Environment Secrets** | Scoped to specific environments | Production API key |
| **Environment Protection** | Rules before deployment | Required reviewer approval |
| **Deployment Branches** | Which branches can deploy | Only main → production |

**Best Practices:**
- Production secrets: Always environment-scoped
- Never commit secrets to code
- Use different API keys for staging vs. production
- Require approval for production deployments

-----

### Concept 4: Health Check Workflows

**Definition:**
Scheduled GitHub Actions workflows that periodically check system health and alert on failures.

**The Pattern:**
```yaml
on:
  schedule:
    - cron: '*/15 * * * *'  # Every 15 minutes

jobs:
  health-check:
    steps:
      - name: Check endpoint health
        run: curl -f $HEALTH_ENDPOINT || exit 1

      - name: Alert on failure
        if: failure()
        run: curl -X POST $SLACK_WEBHOOK -d '{"text":"Health check failed"}'
```

**Key Metrics to Track:**
- Error rate (threshold: < 5%)
- Latency p95 (threshold: < 2000ms)
- Success rate (threshold: > 95%)
- Token usage (threshold: < 90% of limit)

-----

### Quick Reference: Deployment Strategy Selection

**Which strategy should you use?**

| Need | Strategy | Why |
|------|----------|-----|
| Instant rollback | Blue-Green | Traffic switch is immediate |
| Gradual validation | Canary | Test with small % of real traffic |
| Simple implementation | Blue-Green | Fewer moving parts |
| Metric-driven deployment | Canary | Automated rollback on metric degradation |
| Limited infrastructure | Rolling | Updates in-place, no duplicate environments |

**Recommendation:** Start with Blue-Green (simpler), evolve to Canary as monitoring matures.

-----

## Workshop Recap

### Session Summary

**Today's Focus:** Production deployment strategies, secrets management, monitoring, and assembling a complete CI/CD pipeline.

**Key Points from Each Segment:**

**Segment 1: Deployment Strategies for AI Systems**
- Blue-Green: Two environments, deploy to inactive, switch traffic, instant rollback
- Canary: Gradual rollout (10% → 100%), metric monitoring, auto-rollback
- Choose based on rollback speed needs and infrastructure availability
- Key takeaway: Safe deployments with zero downtime

**Segment 2: Secrets & Configuration Management**
- GitHub Secrets stores API keys and tokens securely
- Repository secrets for shared values, environment secrets for production
- Configuration as code: commit settings, reference secrets
- Key takeaway: Never commit secrets, use environment-scoped secrets for production

**Segment 3: Monitoring & Observability**
- Health check workflows run on schedule (every 15 minutes)
- Track error rate, latency, token usage, success rate
- Alert at appropriate severity (Critical, Warning, Info)
- Key takeaway: Proactive monitoring detects failures before users report them

**Segment 4: Complete CI/CD Pipeline Assembly**
- Validate → Test → Stage → Approve → Deploy → Monitor
- Job dependencies create fail-fast pipeline
- Environment protection adds human oversight for production
- Key takeaway: Automation handles mechanics, humans approve production

### Demo Recap

**What Was Demonstrated:**
Blue-green deployment strategy or GitHub Environments setup with protection rules.

**Key Steps:**
1. Two deployment slots/environments (Blue and Green)
2. Deploy to inactive slot (Green)
3. Run smoke tests on Green
4. Switch traffic if tests pass
5. Instant rollback by switching back to Blue

**Result:**
Zero-downtime deployment with safety net for quick rollback if issues arise.

-----

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 2.1 | 30 min | Design doc + deployment workflow | Deployment strategy |
| 2.2 | 25 min | Monitoring workflow + alerts | Health checks, alerting |
| 2.3 | 20 min | Complete CI/CD pipeline | Module capstone |

**Note:** Exercise 2.3 is the module capstone - it brings together all learning from Sessions 1 and 2.

-----

### Exercise 2.1: Implement Deployment Strategy

**Duration:** 30 minutes

**Purpose:**
Design and implement a deployment strategy (blue-green or canary) for your AI system. This enables zero-downtime deployments with safe rollback.

**You Will Create:**
- Design document explaining your chosen strategy
- Deployment workflow implementing the strategy
- Rollback procedure documentation

-----

#### Instructions

**Step 1: Choose Your Deployment Strategy**

Consider your requirements:
- **Need instant rollback?** → Blue-Green
- **Need gradual validation with real users?** → Canary
- **Getting started / want simplicity?** → Blue-Green
- **Have mature monitoring / want metric-driven rollout?** → Canary

**Recommendation for this exercise:** Blue-Green (simpler to implement)

**Step 2: Create Design Document**

Create `docs/deployment-strategy.md`:

```markdown
# Deployment Strategy

## Strategy: Blue-Green Deployment

### Justification
We chose Blue-Green deployment because:
- Provides instant rollback capability
- Simpler to implement than Canary
- Our monitoring is still maturing
- Infrastructure can support two environments

### How It Works

1. **Blue (Active) and Green (Inactive) slots**
   - Blue serves production traffic
   - Green is idle, ready for new deployment

2. **Deployment Process:**
   - Deploy new version to Green slot
   - Run smoke tests on Green
   - If tests pass: Switch traffic to Green
   - Blue becomes idle (ready for rollback)

3. **Rollback Procedure:**
   - If issues detected after switch: Switch traffic back to Blue
   - Rollback time: < 30 seconds
   - No code changes needed for rollback

### Smoke Tests
- Health endpoint responds with 200 OK
- Key prompt returns valid response
- Configuration loads correctly

### Monitoring During Deployment
- Error rate (expect < 5%)
- Latency p95 (expect < 2000ms)
- First 5 minutes post-deployment: Extra vigilance

## Architecture Diagram

```
┌─────────────────────┐
│  Load Balancer      │  ← Traffic routing
│  (Switch: Blue/Green)│
└──────────┬──────────┘
           │
      ┌────┴────┐
      │         │
   ┌──▼──┐   ┌──▼──┐
   │Blue │   │Green│
   │(v1) │   │(v2) │
   └─────┘   └─────┘
```
```

**Step 3: Create Deployment Workflow**

Create `.github/workflows/deploy-production.yml`:

```yaml
name: Deploy to Production (Blue-Green)

on:
  workflow_dispatch:  # Manual trigger for production
    inputs:
      target_slot:
        description: 'Target slot (blue or green)'
        required: true
        type: choice
        options:
          - blue
          - green

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: production  # Requires approval
    steps:
      - uses: actions/checkout@v4

      - name: Deploy to ${{ inputs.target_slot }} slot
        env:
          API_KEY: ${{ secrets.AI_API_KEY }}
          SLOT: ${{ inputs.target_slot }}
        run: |
          echo "Deploying to $SLOT slot"
          # Replace with your deployment script
          ./scripts/deploy.sh --slot $SLOT --api-key "$API_KEY"

      - name: Run smoke tests on ${{ inputs.target_slot }}
        run: |
          echo "Running smoke tests on ${{ inputs.target_slot }}"
          # Replace with your smoke test script
          ./scripts/smoke-test.sh --slot ${{ inputs.target_slot }}

      - name: Health check
        run: |
          HEALTH_URL="https://your-app-${{ inputs.target_slot }}.example.com/health"
          RESPONSE=$(curl -s -o /dev/null -w "%{http_code}" $HEALTH_URL)
          if [ "$RESPONSE" != "200" ]; then
            echo "Health check failed: HTTP $RESPONSE"
            exit 1
          fi
          echo "Health check passed"

  switch-traffic:
    needs: deploy
    runs-on: ubuntu-latest
    environment: production
    if: success()
    steps:
      - name: Switch traffic to ${{ inputs.target_slot }}
        run: |
          echo "Switching traffic to ${{ inputs.target_slot }}"
          # Replace with your traffic switching script
          # This could be updating load balancer config,
          # updating DNS, or cloud provider traffic routing
          ./scripts/switch-traffic.sh --to ${{ inputs.target_slot }}

      - name: Verify traffic switch
        run: |
          sleep 10  # Wait for traffic switch to propagate
          echo "Verifying traffic is routing to ${{ inputs.target_slot }}"
          # Check that production URL serves new version
```

**Step 4: Create Deployment Scripts**

Create `scripts/deploy.sh`:

```bash
#!/bin/bash
set -e

SLOT=""
API_KEY=""

while [[ $# -gt 0 ]]; do
  case $1 in
    --slot) SLOT="$2"; shift 2 ;;
    --api-key) API_KEY="$2"; shift 2 ;;
    *) echo "Unknown parameter: $1"; exit 1 ;;
  esac
done

echo "Deploying to $SLOT slot..."

# Example: Copy prompts to deployment directory
mkdir -p "deployments/$SLOT/prompts"
cp -r prompts/* "deployments/$SLOT/prompts/"

# Example: Update configuration
cat > "deployments/$SLOT/config.json" <<EOF
{
  "slot": "$SLOT",
  "apiKey": "$API_KEY",
  "deployed": "$(date -u +%Y-%m-%dT%H:%M:%SZ)"
}
EOF

echo "Deployment to $SLOT complete"
```

Make it executable:
```bash
chmod +x scripts/deploy.sh
```

Create `scripts/smoke-test.sh`:

```bash
#!/bin/bash
set -e

SLOT="$1"

echo "Running smoke tests on $SLOT..."

# Test 1: Health endpoint
echo "Test 1: Health endpoint"
curl -f "http://localhost:8080/$SLOT/health" || (echo "Health check failed"; exit 1)

# Test 2: Key prompt renders
echo "Test 2: Prompt rendering"
if [ ! -f "deployments/$SLOT/prompts/customer-support/v2.0.0/ticket-response.md" ]; then
  echo "Prompt file missing"
  exit 1
fi

echo "All smoke tests passed"
```

Make it executable:
```bash
chmod +x scripts/smoke-test.sh
```

**Step 5: Document Rollback Procedure**

Add to `docs/deployment-strategy.md`:

```markdown
## Rollback Procedure

### When to Rollback
- Error rate > 5% for 5 minutes
- Health checks failing
- Critical functionality broken
- User-reported production issues

### How to Rollback

1. **Identify current active slot:**
   ```bash
   ./scripts/get-active-slot.sh
   ```
   Output: "green" (means green is active)

2. **Switch traffic to other slot:**
   ```bash
   ./scripts/switch-traffic.sh --to blue
   ```

3. **Verify rollback:**
   ```bash
   curl https://your-app.example.com/health
   # Should respond from blue slot
   ```

4. **Monitor metrics:**
   - Error rate should return to baseline
   - Latency should normalize
   - User reports should stop

### Rollback Time
- **Target:** < 30 seconds
- **Traffic switch:** ~10 seconds
- **Verification:** ~20 seconds

### Post-Rollback
1. Investigate what caused the issue
2. Fix in Green slot (now inactive)
3. Re-test thoroughly
4. Re-deploy when ready
```

**Step 6: Review Your Work**

Check that your deliverable includes:
- [ ] `docs/deployment-strategy.md` with strategy explanation
- [ ] `docs/deployment-strategy.md` includes rollback procedure
- [ ] `.github/workflows/deploy-production.yml` exists
- [ ] Deployment scripts exist and are executable
- [ ] Workflow uses manual trigger (workflow_dispatch)
- [ ] Workflow uses production environment (requires approval)

-----

#### Deliverable Specification

**Files:**
- `docs/deployment-strategy.md` - Strategy documentation
- `.github/workflows/deploy-production.yml` - Deployment workflow
- `scripts/deploy.sh` - Deployment script
- `scripts/smoke-test.sh` - Smoke test script

**Quality Criteria:**
- [ ] Strategy choice is clearly justified
- [ ] Workflow includes deploy, smoke test, and traffic switch jobs
- [ ] Rollback procedure is documented with time estimates
- [ ] Scripts are executable and have error handling

-----

#### Tips & Troubleshooting

**Tips:**
- Start with workflow_dispatch (manual trigger) for production safety
- Test deployment scripts locally before using in workflow
- Document your specific smoke tests (what validates "working"?)
- Include health check endpoints in deployment

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Scripts not executable | Run `chmod +x scripts/*.sh` |
| Workflow doesn't appear | Check file is in `.github/workflows/` with .yml extension |
| Can't trigger manually | Ensure `on: workflow_dispatch:` is in workflow |
| Environment approval not required | Configure environment protection in Settings → Environments |

-----

### Exercise 2.2: Configure Monitoring and Alerting

**Duration:** 25 minutes

**Purpose:**
Create a monitoring solution that continuously checks your AI system health and alerts on failures. This provides proactive detection of issues.

**You Will Create:**
- Health check workflow that runs every 15 minutes
- Alert configuration for Slack, Discord, or email
- Monitoring documentation

-----

#### Instructions

**Step 1: Set Up Alert Webhook**

**For Slack:**
1. Go to https://api.slack.com/messaging/webhooks
2. Create an Incoming Webhook for your workspace
3. Choose a channel (e.g., #ai-alerts)
4. Copy the webhook URL (looks like https://hooks.slack.com/services/...)

**For Discord:**
1. Server Settings → Integrations → Webhooks
2. Create webhook, choose channel
3. Copy webhook URL (looks like https://discord.com/api/webhooks/...)

**For email (using GitHub API):**
No webhook needed - workflow can use `gh api` commands

**Step 2: Add Webhook to GitHub Secrets**

1. Go to your repository Settings
2. Secrets and variables → Actions
3. New repository secret
4. Name: `ALERT_WEBHOOK`
5. Value: Your webhook URL
6. Save

**Step 3: Create Monitoring Workflow**

Create `.github/workflows/monitoring.yml`:

```yaml
name: Health Check Monitoring

on:
  schedule:
    - cron: '*/15 * * * *'  # Every 15 minutes
  workflow_dispatch:  # Allow manual triggering for testing

jobs:
  health-check:
    runs-on: ubuntu-latest
    steps:
      - name: Check system health endpoint
        id: health
        continue-on-error: true
        run: |
          # Replace with your actual health endpoint
          HEALTH_URL="${{ secrets.HEALTH_ENDPOINT_URL || 'https://your-app.example.com/health' }}"

          echo "Checking $HEALTH_URL"
          RESPONSE=$(curl -s -o /dev/null -w "%{http_code}" "$HEALTH_URL")

          if [ "$RESPONSE" = "200" ]; then
            echo "status=healthy" >> $GITHUB_OUTPUT
            echo "Health check passed: HTTP $RESPONSE"
          else
            echo "status=unhealthy" >> $GITHUB_OUTPUT
            echo "Health check failed: HTTP $RESPONSE"
            exit 1
          fi

      - name: Check error rate
        id: errors
        continue-on-error: true
        run: |
          # This is a placeholder - integrate with your actual metrics
          # Example: Query your logging/metrics system for error rate
          ERROR_RATE=3.2  # Placeholder value

          echo "Current error rate: $ERROR_RATE%"

          if (( $(echo "$ERROR_RATE > 5.0" | bc -l) )); then
            echo "status=high" >> $GITHUB_OUTPUT
            exit 1
          else
            echo "status=normal" >> $GITHUB_OUTPUT
          fi

      - name: Check latency
        id: latency
        continue-on-error: true
        run: |
          # Placeholder - integrate with your actual metrics
          LATENCY_P95=1200  # milliseconds

          echo "Current p95 latency: ${LATENCY_P95}ms"

          if [ "$LATENCY_P95" -gt 2000 ]; then
            echo "status=high" >> $GITHUB_OUTPUT
            exit 1
          else
            echo "status=normal" >> $GITHUB_OUTPUT
          fi

      - name: Send success notification
        if: steps.health.outputs.status == 'healthy' && steps.errors.outputs.status == 'normal' && steps.latency.outputs.status == 'normal'
        env:
          WEBHOOK: ${{ secrets.ALERT_WEBHOOK }}
        run: |
          # Only send periodic "all good" messages (once per hour)
          # Check if current minute is 00
          if [ "$(date +%M)" = "00" ]; then
            curl -X POST "$WEBHOOK" \
              -H "Content-Type: application/json" \
              -d '{
                "text": "✅ AI System Health: All checks passing",
                "attachments": [{
                  "color": "good",
                  "fields": [
                    {"title": "Status", "value": "Healthy", "short": true},
                    {"title": "Time", "value": "'"$(date -u +%Y-%m-%dT%H:%M:%SZ)"'", "short": true}
                  ]
                }]
              }'
          fi

      - name: Alert on health check failure
        if: steps.health.outputs.status == 'unhealthy'
        env:
          WEBHOOK: ${{ secrets.ALERT_WEBHOOK }}
        run: |
          curl -X POST "$WEBHOOK" \
            -H "Content-Type: application/json" \
            -d '{
              "text": "🚨 CRITICAL: AI System Health Check FAILED",
              "attachments": [{
                "color": "danger",
                "fields": [
                  {"title": "Issue", "value": "Health endpoint not responding", "short": false},
                  {"title": "Severity", "value": "CRITICAL", "short": true},
                  {"title": "Time", "value": "'"$(date -u +%Y-%m-%dT%H:%M:%SZ)"'", "short": true},
                  {"title": "Action", "value": "Investigate immediately", "short": false}
                ]
              }]
            }'

      - name: Alert on high error rate
        if: steps.errors.outputs.status == 'high'
        env:
          WEBHOOK: ${{ secrets.ALERT_WEBHOOK }}
        run: |
          curl -X POST "$WEBHOOK" \
            -H "Content-Type: application/json" \
            -d '{
              "text": "⚠️ WARNING: Elevated Error Rate Detected",
              "attachments": [{
                "color": "warning",
                "fields": [
                  {"title": "Issue", "value": "Error rate > 5%", "short": false},
                  {"title": "Severity", "value": "WARNING", "short": true},
                  {"title": "Time", "value": "'"$(date -u +%Y-%m-%dT%H:%M:%SZ)"'", "short": true}
                ]
              }]
            }'

      - name: Alert on high latency
        if: steps.latency.outputs.status == 'high'
        env:
          WEBHOOK: ${{ secrets.ALERT_WEBHOOK }}
        run: |
          curl -X POST "$WEBHOOK" \
            -H "Content-Type: application/json" \
            -d '{
              "text": "⚠️ WARNING: High Latency Detected",
              "attachments": [{
                "color": "warning",
                "fields": [
                  {"title": "Issue", "value": "p95 latency > 2000ms", "short": false},
                  {"title": "Severity", "value": "WARNING", "short": true},
                  {"title": "Time", "value": "'"$(date -u +%Y-%m-%dT%H:%M:%SZ)"'", "short": true}
                ]
              }]
            }'
```

**Step 4: Test Monitoring Workflow**

1. Commit and push the monitoring workflow
2. Go to Actions tab → Health Check Monitoring
3. Click "Run workflow" (uses workflow_dispatch to test)
4. Check your alert channel for test message
5. Verify workflow runs successfully

**Step 5: Document Monitoring**

Create `docs/monitoring.md`:

```markdown
# Monitoring and Alerting

## Health Checks

### Schedule
- Runs every 15 minutes via GitHub Actions
- Workflow: `.github/workflows/monitoring.yml`

### Checks Performed
1. **Health Endpoint:** System responds with HTTP 200
2. **Error Rate:** < 5% threshold
3. **Latency (p95):** < 2000ms threshold

## Alerts

### Channel
- Alerts sent to: [Slack #ai-alerts / Discord #alerts / Email]
- Webhook configured in GitHub Secrets: `ALERT_WEBHOOK`

### Alert Levels

**CRITICAL** (Red)
- Health check failure
- Requires immediate investigation

**WARNING** (Yellow)
- Error rate 5-10%
- Latency 2000-3000ms
- Investigate soon

**INFO** (Green)
- Hourly "all good" confirmation
- Deployment notifications

### Response Procedures

**On Critical Alert:**
1. Check GitHub Actions run for specific failure
2. Check application logs
3. Verify deployment status
4. Consider rollback if recent deployment

**On Warning Alert:**
5. Monitor trend - is it getting worse?
6. Check resource usage
7. Review recent changes
8. Plan investigation

## Metrics Dashboard

[Link to metrics dashboard if you have one]

## Escalation

- First alert: On-call engineer
- Not resolved in 30 min: Escalate to team lead
- Still not resolved: Escalate to management
```

**Step 6: Review Your Work**

Check that your deliverable includes:
- [ ] Webhook created and added to GitHub Secrets
- [ ] `.github/workflows/monitoring.yml` exists and runs on schedule
- [ ] Workflow checks health, error rate, and latency
- [ ] Alerts send to configured webhook
- [ ] `docs/monitoring.md` documents monitoring approach

-----

#### Deliverable Specification

**Files:**
- `.github/workflows/monitoring.yml` - Monitoring workflow
- `docs/monitoring.md` - Documentation
- GitHub Secret: `ALERT_WEBHOOK` configured

**Quality Criteria:**
- [ ] Workflow runs on schedule (cron: */15 * * * *)
- [ ] At least 2 health checks implemented
- [ ] Alerts actually send (test with workflow_dispatch)
- [ ] Documentation explains alert levels and response

-----

#### Tips & Troubleshooting

**Tips:**
- Test webhook manually: `curl -X POST $WEBHOOK_URL -d '{"text":"test"}'`
- Use workflow_dispatch to test without waiting 15 minutes
- Start with simple health check, add complexity incrementally
- Document what each metric means and thresholds

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Alerts don't send | Verify webhook URL is correct, test with curl |
| Webhook secret not found | Check secret name matches exactly: ALERT_WEBHOOK |
| Cron not triggering | Verify cron syntax, may take up to first run to activate |
| Too many alerts | Increase thresholds or add rate limiting |

-----

### Exercise 2.3: Module Capstone - Complete CI/CD Pipeline

**Duration:** 20 minutes

**Purpose:**
Assemble all components from Sessions 1 and 2 into a production-ready CI/CD pipeline. This is the module capstone that demonstrates your complete DevOps capabilities.

**You Will Create:**
- Complete `.github/workflows/` directory with all pipeline stages
- Staging and production environments configured
- Documentation of complete pipeline

-----

#### Instructions

**Step 1: Organize Workflow Files**

Your `.github/workflows/` directory should contain:

```
.github/workflows/
├── validate.yml           (From Session 1, Exercise 1.1)
├── test.yml               (From Session 1, Exercise 1.3)
├── deploy-staging.yml     (Create new)
├── deploy-production.yml  (From Exercise 2.1)
└── monitoring.yml         (From Exercise 2.2)
```

**Step 2: Create/Update Validation Workflow**

Ensure `.github/workflows/validate.yml` exists (from Session 1):

```yaml
name: Validate

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  validate-prompts:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Check prompt structure
        run: |
          echo "Validating prompt files..."
          find prompts -name "*.md" -type f | while read file; do
            echo "Checking: $file"
            grep -q "## System Context" "$file" || (echo "Missing System Context in $file"; exit 1)
            grep -q "## Instructions" "$file" || (echo "Missing Instructions in $file"; exit 1)
          done

  validate-versions:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Validate version manifest
        run: |
          # Check VERSION_MANIFEST.json is valid JSON
          cat prompts/VERSION_MANIFEST.json | python -m json.tool > /dev/null
          echo "Version manifest is valid JSON"
```

**Step 3: Create/Update Test Workflow**

Ensure `.github/workflows/test.yml` exists (from Session 1):

```yaml
name: Test

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  unit-tests:
    needs: []  # Can run independently
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '18'

      - name: Install dependencies
        run: npm install

      - name: Run unit tests
        run: npm test

      - name: Check coverage
        run: |
          npm run test:coverage
          # Enforce 80% coverage threshold
          COVERAGE=$(cat coverage/coverage-summary.json | jq '.total.lines.pct')
          echo "Coverage: $COVERAGE%"
          if (( $(echo "$COVERAGE < 80" | bc -l) )); then
            echo "Coverage below 80% threshold"
            exit 1
          fi
```

**Step 4: Create Staging Deployment Workflow**

Create `.github/workflows/deploy-staging.yml`:

```yaml
name: Deploy to Staging

on:
  push:
    branches: [develop]  # Auto-deploy on merge to develop
  workflow_dispatch:  # Allow manual trigger

jobs:
  validate:
    uses: ./.github/workflows/validate.yml

  test:
    needs: validate
    uses: ./.github/workflows/test.yml

  deploy:
    needs: test
    runs-on: ubuntu-latest
    environment: staging
    steps:
      - uses: actions/checkout@v4

      - name: Deploy to staging
        env:
          API_KEY: ${{ secrets.AI_API_KEY }}
        run: |
          echo "Deploying to staging environment"
          ./scripts/deploy.sh --env staging --api-key "$API_KEY"

      - name: Run smoke tests
        run: |
          echo "Running staging smoke tests"
          ./scripts/smoke-test.sh staging

      - name: Notify deployment
        env:
          WEBHOOK: ${{ secrets.ALERT_WEBHOOK }}
        run: |
          curl -X POST "$WEBHOOK" \
            -H "Content-Type: application/json" \
            -d '{
              "text": "✅ Deployed to staging",
              "attachments": [{
                "color": "good",
                "fields": [
                  {"title": "Environment", "value": "Staging", "short": true},
                  {"title": "Commit", "value": "'"${{ github.sha }}"'", "short": true}
                ]
              }]
            }'
```

**Step 5: Ensure Production Deployment Workflow**

Your `.github/workflows/deploy-production.yml` from Exercise 2.1 should be updated to require staging success:

```yaml
name: Deploy to Production

on:
  workflow_dispatch:
    inputs:
      target_slot:
        description: 'Target slot (blue or green)'
        required: true
        type: choice
        options:
          - blue
          - green

jobs:
  # Require validation and tests before production
  validate:
    uses: ./.github/workflows/validate.yml

  test:
    needs: validate
    uses: ./.github/workflows/test.yml

  deploy:
    needs: test
    runs-on: ubuntu-latest
    environment: production  # Requires approval
    steps:
      - uses: actions/checkout@v4

      - name: Deploy to ${{ inputs.target_slot }} slot
        env:
          API_KEY: ${{ secrets.AI_API_KEY }}
          SLOT: ${{ inputs.target_slot }}
        run: |
          echo "Deploying to production $SLOT slot"
          ./scripts/deploy.sh --env production --slot $SLOT --api-key "$API_KEY"

      - name: Run smoke tests
        run: ./scripts/smoke-test.sh production-${{ inputs.target_slot }}

      - name: Health check
        run: |
          HEALTH_URL="https://your-app-${{ inputs.target_slot }}.example.com/health"
          curl -f "$HEALTH_URL" || exit 1

  switch-traffic:
    needs: deploy
    runs-on: ubuntu-latest
    environment: production
    if: success()
    steps:
      - name: Switch traffic to ${{ inputs.target_slot }}
        run: ./scripts/switch-traffic.sh --to ${{ inputs.target_slot }}

      - name: Notify production deployment
        env:
          WEBHOOK: ${{ secrets.ALERT_WEBHOOK }}
        run: |
          curl -X POST "$WEBHOOK" \
            -H "Content-Type: application/json" \
            -d '{
              "text": "🚀 PRODUCTION DEPLOYMENT COMPLETE",
              "attachments": [{
                "color": "good",
                "fields": [
                  {"title": "Environment", "value": "Production", "short": true},
                  {"title": "Slot", "value": "'"${{ inputs.target_slot }}"'", "short": true},
                  {"title": "Deployed by", "value": "'"${{ github.actor }}"'", "short": true}
                ]
              }]
            }'
```

**Step 6: Configure GitHub Environments**

1. **Create Staging Environment:**
   - Go to Settings → Environments
   - Click "New environment"
   - Name: `staging`
   - Add environment secret: `AI_API_KEY` (staging API key)
   - Save

2. **Create Production Environment:**
   - Click "New environment"
   - Name: `production`
   - Add environment secret: `AI_API_KEY` (production API key)
   - Configure environment protection rules:
     - ✓ Required reviewers (add yourself or team)
     - ✓ Wait timer: 0 minutes (optional)
     - ✓ Deployment branches: Only `main` branch
   - Save

**Step 7: Create Pipeline Documentation**

Create `docs/ci-cd-pipeline.md`:

```markdown
# CI/CD Pipeline Documentation

## Pipeline Overview

Complete automated pipeline from commit to production deployment with monitoring.

## Pipeline Stages

```
Developer Commit
      ↓
   Validate (validate.yml)
      ↓
    Test (test.yml)
      ↓
Deploy to Staging (deploy-staging.yml)
      ↓
   Manual Approval
      ↓
Deploy to Production (deploy-production.yml)
      ↓
  Monitor (monitoring.yml)
```

## Workflow Files

| Workflow | Trigger | Purpose | Environment |
|----------|---------|---------|-------------|
| `validate.yml` | Push, PR | Syntax, schema checks | None |
| `test.yml` | Push, PR | Unit tests, coverage | None |
| `deploy-staging.yml` | Push to develop | Auto-deploy staging | Staging |
| `deploy-production.yml` | Manual | Deploy production | Production |
| `monitoring.yml` | Schedule (15 min) | Health checks | None |

## Environments

### Staging
- **Purpose:** Pre-production testing
- **Deployment:** Automatic on merge to `develop`
- **Secrets:** Staging-specific AI_API_KEY
- **URL:** https://staging.your-app.example.com

### Production
- **Purpose:** Live user traffic
- **Deployment:** Manual trigger with approval
- **Secrets:** Production AI_API_KEY
- **Protection:** Required reviewer, main branch only
- **URL:** https://your-app.example.com

## Deployment Process

### To Staging
1. Merge PR to `develop` branch
2. Pipeline runs automatically:
   - Validates code
   - Runs tests
   - Deploys to staging
   - Runs smoke tests
3. Verify in staging environment

### To Production
1. Ensure code is in `main` branch
2. Go to Actions → Deploy to Production
3. Click "Run workflow"
4. Select target slot (blue or green)
5. Wait for approval notification
6. Reviewer approves deployment
7. Pipeline executes:
   - Validates and tests
   - Deploys to selected slot
   - Runs smoke tests and health checks
   - Switches traffic if successful
8. Monitor for issues

## Rollback Procedure

See [deployment-strategy.md](deployment-strategy.md) for detailed rollback instructions.

Quick rollback:
```bash
./scripts/switch-traffic.sh --to [other-slot]
```

## Monitoring

- Health checks run every 15 minutes
- Alerts sent to [Slack/Discord channel]
- See [monitoring.md](monitoring.md) for details

## Secrets Management

### Repository Secrets
- `ALERT_WEBHOOK` - Slack/Discord webhook for alerts

### Environment Secrets
- Staging: `AI_API_KEY` (staging API key)
- Production: `AI_API_KEY` (production API key)

**Never commit secrets to code.**

## Branch Strategy

- `main` - Production-ready code
- `develop` - Integration branch, auto-deploys to staging
- `feature/*` - Feature development
- `hotfix/*` - Emergency production fixes

## Quality Gates

### Pre-Merge
- All validation checks pass
- All tests pass with 80%+ coverage
- Code review approved

### Pre-Production
- Deployed successfully to staging
- Staging smoke tests pass
- Manual approval obtained
- All production checks pass

## Maintenance

- Review failed workflows weekly
- Update dependencies monthly
- Test rollback procedures quarterly
- Review and update documentation as needed
```

**Step 8: Review Your Complete Pipeline**

Check that your capstone includes:
- [ ] All 5 workflow files present and functional
- [ ] Staging environment configured with secrets
- [ ] Production environment configured with protection rules
- [ ] `docs/ci-cd-pipeline.md` documenting complete pipeline
- [ ] `docs/deployment-strategy.md` from Exercise 2.1
- [ ] `docs/monitoring.md` from Exercise 2.2

**Step 9: Test Complete Pipeline**

1. **Test validation:** Push a change to develop, verify validate.yml runs
2. **Test staging deployment:** Merge to develop, verify deploy-staging.yml runs
3. **Test monitoring:** Wait for monitoring.yml to run, verify alerts
4. **Test production (optional):** Run deploy-production.yml manually

-----

#### Deliverable Specification

**Complete `.github/workflows/` directory:**
- `validate.yml`
- `test.yml`
- `deploy-staging.yml`
- `deploy-production.yml`
- `monitoring.yml`

**Environments configured:**
- Staging (with AI_API_KEY secret)
- Production (with AI_API_KEY secret + protection rules)

**Documentation:**
- `docs/ci-cd-pipeline.md`
- `docs/deployment-strategy.md`
- `docs/monitoring.md`

**Quality Criteria:**
- [ ] All workflows run successfully
- [ ] Production requires approval
- [ ] Monitoring sends alerts
- [ ] Documentation is complete and accurate
- [ ] Pipeline follows validate → test → stage → approve → deploy → monitor flow

-----

#### Tips & Troubleshooting

**Tips:**
- Test each workflow individually before testing the complete pipeline
- Use workflow_dispatch for manual testing
- Check Actions tab for workflow run history and logs
- Document your specific infrastructure details

**Common Issues:**

| Problem | Solution |
|---------|----------|
| Workflows don't trigger | Check trigger conditions (branches, paths) |
| Secrets not available | Verify secret names match exactly, environment is specified |
| Reusable workflow errors | Check uses: syntax, ensure validate/test workflows are callable |
| Environment protection not enforced | Verify environment name in workflow matches Settings → Environments |
| Approval not required | Check production environment has required reviewers configured |

-----

## Templates & Resources

### Templates Provided This Session

| Template | Purpose | Location |
|----------|---------|----------|
| Blue-Green Deployment Workflow | Production deployment | Exercise 2.1 |
| Monitoring Workflow | Health checks and alerts | Exercise 2.2 |
| Complete Pipeline | All workflow files | Exercise 2.3 |

-----

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| GitHub Environments | Documentation | https://docs.github.com/actions/deployment/targeting-different-environments | Setting up staging/production |
| GitHub Secrets | Documentation | https://docs.github.com/actions/security-guides/encrypted-secrets | Configuring secrets |
| Slack Incoming Webhooks | Guide | https://api.slack.com/messaging/webhooks | Setting up Slack alerts |
| Discord Webhooks | Guide | https://support.discord.com/hc/en-us/articles/228383668 | Setting up Discord alerts |
| Workflow Syntax | Reference | https://docs.github.com/actions/using-workflows/workflow-syntax-for-github-actions | Writing workflows |
| Cron Schedule | Tool | https://crontab.guru | Building cron expressions |

-----

### Module Appendix References

Review these appendices from the main module:

- **Appendix A:** GitHub Actions Reference - Actions, syntax, patterns
- **Appendix B:** Troubleshooting Guide - Common issues and solutions
- **Appendix C:** Security Checklist - Pre-deployment security review

See the main module document ([Module 5](../module-5-github-devops.md)) for full appendix content.

-----

## Self-Assessment

### Exit Criteria Checklist

Before considering the module complete, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Implement deployment strategy | Exercise 2.1 workflow + documentation | ☐ |
| 2 | Configure monitoring and alerting | Exercise 2.2 workflow sending alerts | ☐ |
| 3 | Manage secrets securely | Environments with environment-scoped secrets | ☐ |
| 4 | Assemble complete CI/CD pipeline | Exercise 2.3 all workflows functional | ☐ |

-----

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Deployment strategy | `deployment-strategy.md` | `docs/` | ☐ |
| Deployment workflow | `deploy-production.yml` | `.github/workflows/` | ☐ |
| Monitoring workflow | `monitoring.yml` | `.github/workflows/` | ☐ |
| Staging deployment | `deploy-staging.yml` | `.github/workflows/` | ☐ |
| Complete pipeline docs | `ci-cd-pipeline.md` | `docs/` | ☐ |
| All workflows | 5 workflow files | `.github/workflows/` | ☐ |

-----

### Reflection Questions

Take 5 minutes to consider:

1. **What was your biggest win?** What part of the pipeline are you most proud of?

2. **What would you do differently?** If you built this again, what would you change?

3. **How will you use this?** What AI system will you deploy with this pipeline?

4. **What's next?** What additional DevOps capabilities do you want to add?

-----

## Getting Help

### Common Questions This Session

**Q: My production deployment doesn't require approval. Why?**
A: Check that your production environment in Settings → Environments has "Required reviewers" configured. Ensure the workflow specifies `environment: production`.

**Q: How do I create a webhook for Slack/Discord?**
A: Slack: https://api.slack.com/messaging/webhooks. Discord: Server Settings → Integrations → Webhooks. Both provide a URL to add as GitHub Secret.

**Q: Workflows fail with "secret not found". What's wrong?**
A: Verify secret name matches exactly (case-sensitive). If using environment secrets, ensure workflow specifies the environment. Check secret is in correct scope (repository vs. environment).

**Q: Should I use blue-green or canary deployment?**
A: For this module, blue-green is recommended (simpler). Use canary if you have robust metrics and want gradual rollout.

**Q: How do I test my complete pipeline without affecting production?**
A: Use staging environment. Deploy to staging automatically. Test production workflow with workflow_dispatch but don't approve the production deployment.

### When to Ask for Help

- **Before asking:** Check module appendices (A, B, C) and this guide's troubleshooting
- **Good to ask:** "My monitoring workflow runs but doesn't send alerts. Here's my webhook configuration..."
- **Include:** Workflow file, error messages, what you've tried, expected vs. actual behavior

-----

## Module Completion

### Congratulations!

Completing Exercise 2.3 completes Advanced Module 5. You've built:

✅ GitHub Actions automation for AI workflows
✅ Version control for AI artifacts
✅ Automated testing with coverage
✅ Deployment strategies (blue-green or canary)
✅ Secrets management
✅ Monitoring and alerting
✅ Complete CI/CD pipeline from validation to production

### Next Steps

1. **Deploy to production:** Use your pipeline to deploy a real AI system
2. **Apply to Block 3 projects:** Add CI/CD to your autonomous agents
3. **Iterate and improve:** Add more tests, refine monitoring, optimize workflows
4. **Explore other modules:** Consider other advanced modules that interest you

### Share Your Achievement

You've developed production-grade DevOps skills for AI systems. This is a significant accomplishment. Share your pipeline with your team, apply it to real projects, and continue building!

-----

## Glossary

| Term | Definition |
|------|------------|
| **Blue-Green Deployment** | Deployment strategy using two identical environments, switching traffic between them |
| **Canary Deployment** | Gradual rollout strategy routing increasing percentages of traffic to new version |
| **Environment** | Deployment target (staging, production) with specific secrets and protection rules |
| **Environment Secret** | Secret scoped to a specific environment (staging vs. production) |
| **Health Check** | Automated check verifying system is responding correctly |
| **Rollback** | Reverting to previous version after problematic deployment |
| **Smoke Test** | Quick validation that critical functionality works |
| **Webhook** | URL that receives HTTP POST notifications (for alerts) |

-----

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial participant guide created |

-----

**Navigation:** [← Session 1](../session-1/participant-guide.md) | **Session 2**
