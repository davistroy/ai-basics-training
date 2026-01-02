# **Session 2: Advanced DevOps Patterns**

**Advanced Module 5: Advanced GitHub & DevOps for AI Systems**
**Session Duration:** 45 min workshop + 75 min self-paced exercises

-----

## **Entry Criteria**

- [ ] Session 1 exercises completed
- [ ] GitHub Actions workflow running successfully
- [ ] Version control structure implemented
- [ ] Basic test suite passing

## **Exit Criteria**

- [ ] Deployment strategy implemented (blue-green or canary)
- [ ] Secrets management configured
- [ ] Monitoring and alerting operational
- [ ] Complete CI/CD pipeline functional
- [ ] Production deployment documented

-----

## **Workshop Content (45 minutes)**

### **Segment 1: Deployment Strategies for AI Systems (12 min)**

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

### **Segment 2: Secrets & Configuration Management (12 min)**

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

### **Segment 3: Monitoring & Observability (12 min)**

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

### **Segment 4: Complete CI/CD Pipeline Assembly (9 min)**

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

## **Self-Paced Exercises (75 minutes total)**

### **Exercise 2.1: Implement Deployment Strategy (30 minutes)**

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

### **Exercise 2.2: Configure Monitoring and Alerting (25 minutes)**

*Create a monitoring solution for your AI workflows*

**Requirements:**
1. Health check workflow running every 15 minutes
2. Alert on failures via Slack, Discord, or email
3. Track key metrics over time
4. Generate weekly summary (optional)

**Deliverable:** Monitoring workflow + alert configuration

-----

### **Exercise 2.3: Module Capstone - Complete CI/CD Pipeline (20 minutes)**

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
