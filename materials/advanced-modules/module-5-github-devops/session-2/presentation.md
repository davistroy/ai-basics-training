# **POWERPOINT PRESENTATION: ADVANCED MODULE 5 SESSION 2**
## **Advanced DevOps Patterns**

**Module:** Advanced Module 5: Advanced GitHub & DevOps for AI Systems
**Session:** 2 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 graduates with Session 1 completed, implementing production deployment strategies

**Key Thesis:** Production AI systems require enterprise deployment patterns—blue-green and canary deployments enable zero-downtime releases, secrets management protects API keys and credentials, and monitoring pipelines provide real-time visibility into system health—completing the CI/CD journey from local development through automated testing to production deployment with confidence and control.

**Session Learning Objectives:** By the end of this session, participants will:
1. Design and implement deployment strategies (blue-green or canary) for AI systems
2. Configure secrets management and environment-specific configurations
3. Build monitoring and alerting workflows for production AI systems
4. Assemble a complete CI/CD pipeline from validation through deployment

**Entry Criteria:**
- [ ] Session 1 exercises completed
- [ ] GitHub Actions workflow running successfully
- [ ] Version control structure implemented
- [ ] Basic test suite passing

**Exit Criteria:**
- [ ] Deployment strategy implemented (blue-green or canary)
- [ ] Secrets management configured
- [ ] Monitoring and alerting operational
- [ ] Complete CI/CD pipeline functional
- [ ] Production deployment documented

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Deployment Strategies for AI Systems (12 min) - Slides 4-8
3. Segment 2: Secrets & Configuration Management (12 min) - Slides 9-13
4. Segment 3: Monitoring & Observability (12 min) - Slides 14-18
5. Segment 4: Complete CI/CD Pipeline Assembly (9 min) - Slides 19-22
6. Homework Preview & Close (3 min) - Slides 23-25

**Total Slides:** 25

-----

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Advanced Module 5 Session 2: Advanced DevOps Patterns

**Subtitle:** Production Deployment Strategies for AI Systems

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program - Advanced Module 5

**Graphic:** Clean title slide with green tones (Advanced module theme)

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Session 2 - the final session of Advanced Module 5. Last session you built the foundation: GitHub Actions workflows, version control, and automated testing. Today we're going production-ready.

We'll cover deployment strategies so you can deploy with zero downtime. Secrets management so API keys stay secure. Monitoring so you know when things break. And we'll assemble everything into a complete CI/CD pipeline.

By the end of today, you'll have a production-grade DevOps system for your AI workflows."

[Transition: Click to next slide]

-----

### SLIDE 2: SESSION OVERVIEW

**Title:** Today's Journey: Foundation to Production

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Session 1 recap, production readiness |
| 3-15 min | Segment 1 | Deployment Strategies (Blue-Green, Canary) |
| 15-27 min | Segment 2 | Secrets & Configuration Management |
| 27-39 min | Segment 3 | Monitoring & Observability |
| 39-42 min | Segment 4 | Complete CI/CD Pipeline |
| 42-45 min | Close | Capstone Exercise & Module Completion |

**Graphic:** Pipeline visualization showing complete flow from validation to production

**SPEAKER NOTES:**

"Here's our journey today:

First, deployment strategies. How do you deploy AI systems with zero downtime? Blue-green and canary deployments give you safe, reversible deployments.

Then secrets management. Your API keys and tokens need protection. We'll configure GitHub Secrets properly.

Third, monitoring and observability. How do you know when your AI system breaks? Automated health checks and alerting.

Finally, we'll assemble everything into a complete CI/CD pipeline - validation, testing, deployment, monitoring, all automated.

[Pause]

Questions before we dive in?"

[Transition]

-----

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Design and implement deployment strategies for AI systems**
   - Choose between blue-green, canary, and rolling deployments

2. **Configure secrets management and environment-specific configurations**
   - Secure API keys and manage staging vs. production configs

3. **Build monitoring and alerting workflows**
   - Detect failures and alert teams automatically

4. **Assemble a complete CI/CD pipeline**
   - From validation through production deployment

**Graphic:** Production pipeline diagram with all components

**SPEAKER NOTES:**

"These are our four objectives for today.

[Read each objective, pausing briefly after each]

Notice we're moving from 'can you build it?' to 'can you deploy it safely and monitor it in production?' This is production-grade DevOps.

[Point to fourth objective]

The capstone exercise brings everything together - a complete pipeline ready for real-world use.

Let's get started with deployment strategies."

[Transition: Click to Segment 1]

-----

## SEGMENT 1: Deployment Strategies for AI Systems
### Duration: 12 minutes | Slides 4-8

-----

### SLIDE 4: SEGMENT 1 - DEPLOYMENT CHALLENGE

**Title:** How Do You Deploy AI Changes Without Breaking Production?

**Content:**

**The Challenge:**
You've updated a critical prompt. It passed all tests. You're ready to deploy. But if it breaks, 10,000 customers see errors.

**Traditional Deploy Problems:**
- All-or-nothing: Everyone gets new version immediately
- No gradual rollout: Can't test with small user group first
- Risky rollbacks: Downtime while reverting
- No safety net: Errors affect all users

**Graphic:** Diagram showing risky all-or-nothing deployment vs. safe gradual deployment

**GRAPHICS:**

**Graphic 1: All-or-Nothing vs. Gradual Deployment Risk Comparison**
- Purpose: Contrast traditional risky deployment with safe gradual rollout strategies
- Type: Side-by-side comparison with risk indicators
- Elements:
  - Left side (All-or-Nothing): Single large arrow pointing from "Old Version" to "New Version" affecting all users at once
  - Right side (Gradual): Multiple smaller arrows showing phased rollout (10% → 25% → 50% → 100%)
  - User icons showing impact (all users affected vs. subset affected)
- Labels:
  - All-or-nothing: "All 10,000 users", "No testing with real traffic", "Risky rollback with downtime"
  - Gradual: "10% initially", "Validate with real users", "Easy rollback", "Incremental risk"
- Relationships: Impact radius visualization (large blast radius vs. controlled exposure)
- Visual cues: Red/warning colors for all-or-nothing, green/safe colors for gradual, danger icons vs. checkmarks

**SPEAKER NOTES:**

"[Hook - Create tension]"

"You've built the perfect prompt. It passed all your tests. Your team approved the PR. You're ready to deploy.

But here's the reality: If this prompt breaks in production, 10,000 customers see errors. Your client's chatbot stops working. Support tickets flood in.

[Pause]

Traditional deployment is all-or-nothing. You push the new version, everyone gets it instantly. If it breaks, everyone sees the breakage.

What you need is a deployment strategy that:
- Deploys with zero downtime
- Tests in production with real traffic
- Rolls back instantly if something breaks

That's what blue-green and canary deployments solve."

[Transition]

**BACKGROUND:**

**Rationale:**
- Creates urgency around safe deployment practices
- Connects to real production risk
- Sets up value proposition for deployment strategies

**Q&A Preparation:**
- *"Can't we just deploy off-hours?"*: That reduces user impact but doesn't eliminate risk. Plus AI systems often serve global users - there are no off-hours.

-----

### SLIDE 5: BLUE-GREEN DEPLOYMENT PATTERN

**Title:** Blue-Green Deployments: Instant Rollback

**Content:**

**How It Works:**
1. **Deploy to inactive slot** (Green while Blue is live)
2. **Run smoke tests** on Green slot
3. **Switch traffic** if tests pass
4. **Rollback** by switching back if issues arise

**Benefits:**
- Zero downtime deployment
- Instant rollback (just switch back)
- Full testing before traffic switch

**Workflow Pattern:**
```yaml
- name: Deploy to green slot
  run: ./deploy-prompts.sh --slot green

- name: Smoke test green slot
  run: ./smoke-test.sh --slot green

- name: Switch to green
  if: success()
  run: ./switch-traffic.sh green
```

**Graphic:** Diagram showing Blue (active) and Green (deploying) slots, then traffic switch

**GRAPHICS:**

**Graphic 1: Blue-Green Deployment Architecture**
- Purpose: Visualize the two-environment deployment pattern with instant rollback capability
- Type: Multi-stage diagram showing deployment flow
- Elements:
  - Stage 1: Blue environment (active, receiving 100% traffic), Green environment (idle)
  - Stage 2: New version deployed to Green environment, Blue still active
  - Stage 3: Smoke tests running on Green (test icon)
  - Stage 4: Traffic switch - load balancer redirects 100% traffic from Blue to Green
  - Stage 5: Green now active, Blue becomes standby for instant rollback
- Labels:
  - Load balancer at top routing traffic
  - "Blue" and "Green" environment labels
  - Traffic percentage indicators (100% → 0% on Blue, 0% → 100% on Green)
  - "Deploy", "Test", "Switch", "Rollback Ready" stage labels
- Relationships: Sequential stages showing deployment progression, bidirectional arrow showing rollback capability
- Visual cues: Blue and green color coding for environments, arrows showing traffic flow, lightning bolt for instant switch

**SPEAKER NOTES:**

"Blue-Green deployment uses two identical environments: Blue and Green.

[Point to diagram]

Blue is currently serving production traffic. You deploy the new version to Green.

Before switching traffic, you run smoke tests on Green. Does it respond? Are prompts working? If yes, switch traffic from Blue to Green.

Now Green is serving production. Blue is idle.

If something breaks after the switch? Switch back to Blue. Instant rollback. No downtime.

This is perfect when you need fast rollback capability. The tradeoff is you need two complete environments."

[Transition]

**BACKGROUND:**

**Rationale:**
- Blue-Green deployment eliminates deployment downtime through environment switching
- Two-environment pattern provides instant rollback capability (just switch back)
- Smoke tests in inactive slot catch issues before user impact
- Proven pattern used by major platforms (AWS, Azure, Heroku)

**Key Research & Citations:**
- Martin Fowler's BlueGreenDeployment pattern (2010) established industry standard
- Netflix uses Blue-Green for zero-downtime deployments at massive scale
- AWS Elastic Beanstalk and Azure App Service provide native Blue-Green support
- Cloud-native architecture patterns emphasize immutable deployments

**Q&A Preparation:**
- *"How much does running two environments cost?"*: Only during deployment window. Most cloud providers charge per-minute. Cost is minimal compared to downtime risk.
- *"Can we do this without cloud infrastructure?"*: Yes - use deployment slots on single server, or containerized environments (Docker). Pattern applies regardless of infrastructure.
- *"What if smoke tests pass but production traffic reveals issues?"*: That's why we combine Blue-Green with monitoring. Detect issues quickly and switch back. Consider adding Canary pattern for gradual validation.

**Sources:**
- Martin Fowler - BlueGreenDeployment: https://martinfowler.com/bliki/BlueGreenDeployment.html
- AWS Blue/Green Deployments: https://docs.aws.amazon.com/whitepapers/latest/blue-green-deployments/
- Continuous Delivery (Humble & Farley): Chapter 10 on deployment strategies

-----

### SLIDE 6: CANARY DEPLOYMENT PATTERN

**Title:** Canary Deployments: Gradual Validation

**Content:**

**How It Works:**
1. **Deploy to 10%** of traffic
2. **Monitor metrics** (errors, latency, satisfaction)
3. **Progressive rollout** if metrics healthy (10% → 25% → 50% → 100%)
4. **Auto-rollback** if metrics degrade

**Benefits:**
- Real production validation with minimal risk
- Progressive rollout catches issues early
- Automatic rollback on metric degradation

**Key Metrics:**
- Error rate < 5%
- Latency p95 < 2000ms
- Success rate > 95%

**Graphic:** Progressive rollout visualization (10% → 25% → 50% → 100%)

**GRAPHICS:**

**Graphic 1: Canary Deployment Progressive Rollout**
- Purpose: Illustrate gradual traffic increase with metric monitoring at each stage
- Type: Horizontal timeline with monitoring gates
- Elements:
  - Timeline bar showing four stages: 10% → 25% → 50% → 100%
  - Each stage has a monitoring checkpoint (dashboard icon)
  - User population icons showing percentage allocation (small group → full population)
  - Metric gauges at each checkpoint: Error rate, Latency, Success rate
  - Decision diamond at each stage: "Metrics healthy?" → Continue or Rollback
- Labels:
  - Stage percentages: "10% canary", "25%", "50%", "100% (full rollout)"
  - Metric thresholds: "Error rate < 5%", "Latency P95 < 2s", "Success > 95%"
  - Decision points: "Continue" (green) or "Auto-rollback" (red)
- Relationships: Progressive flow with validation gates, rollback arrows from any stage back to previous version
- Visual cues: Color-coded traffic bars (growing from small to full width), green checkmarks for healthy metrics, red warning for rollback triggers

**SPEAKER NOTES:**

"Canary deployment is gradual rollout.

You deploy the new version to just 10% of users. Monitor closely. Is error rate higher? Latency worse? If metrics look good, increase to 25%.

Keep monitoring. Still good? 50%. Then 75%. Finally 100%.

If metrics degrade at any point? Auto-rollback. Stop the deployment, revert that traffic.

The name comes from 'canary in a coal mine' - the canary detects danger before everyone is affected.

This is perfect when you want gradual validation with real production traffic. The tradeoff is complexity - you need metric tracking and automated rollback logic."

[Transition]

**BACKGROUND:**

**Rationale:**
- Canary deployment reduces risk by limiting initial exposure to new version
- Real production traffic provides validation that staging environments can't simulate
- Progressive rollout (10% → 25% → 50% → 100%) catches issues with minimal user impact
- Automated metric-based rollback prevents human delay in incident response

**Key Research & Citations:**
- "Canary in a coal mine" metaphor - small percentage detects danger before widespread impact
- Facebook's "dark launches" use Canary pattern for feature rollouts
- Google's "1% experiments" validate changes with real user data before full rollout
- SRE principles emphasize gradual rollout with automated monitoring

**Q&A Preparation:**
- *"How do you decide the rollout percentages?"*: Start small (5-10%), increase gradually. Adjust based on risk tolerance and user base size. High-risk changes stay at each percentage longer.
- *"What metrics determine rollback?"*: Error rate, latency (P95/P99), success rate, user complaints. Define thresholds before deployment - not during incident.
- *"Can we do Canary without sophisticated infrastructure?"*: Yes - use feature flags to control which users see new version. Simple percentage-based routing works without complex load balancers.

**Sources:**
- Site Reliability Engineering (Google): https://sre.google/sre-book/release-engineering/
- Canary Deployments at Scale (Facebook Engineering): https://engineering.fb.com/
- Progressive Delivery patterns: https://launchdarkly.com/blog/what-is-progressive-delivery/

-----

### SLIDE 7: CHOOSING A DEPLOYMENT STRATEGY

**Title:** Which Deployment Strategy?

**Content:**

| Strategy | Best For | Risk Level | Complexity | Rollback Speed |
|----------|----------|------------|------------|----------------|
| **Blue-Green** | Fast rollback needed | Low | Medium | Instant |
| **Canary** | Gradual validation | Low | High | Automatic |
| **Rolling** | Resource constrained | Medium | Low | Slower |

**Decision Framework:**
- **Need instant rollback?** → Blue-Green
- **Need gradual validation with real users?** → Canary
- **Limited infrastructure?** → Rolling
- **Just getting started?** → Blue-Green (simpler)

**Graphic:** Decision tree for choosing deployment strategy

**GRAPHICS:**

**Graphic 1: Deployment Strategy Decision Tree**
- Purpose: Guide users through selecting the appropriate deployment strategy based on requirements
- Type: Flowchart decision tree
- Elements:
  - Start: "Choose Deployment Strategy"
  - Decision 1: "Need instant rollback?" → Yes: Blue-Green, No: Continue
  - Decision 2: "Need gradual validation with real users?" → Yes: Canary, No: Continue
  - Decision 3: "Limited infrastructure resources?" → Yes: Rolling, No: Blue-Green (default)
  - Decision 4: "Just getting started?" → Yes: Blue-Green (simpler), No: Evaluate based on needs
- Labels:
  - Each decision box clearly states the question
  - Each outcome path labeled with recommendation
  - Key characteristics in boxes: "Simple", "Safe", "Resource-efficient"
- Relationships: Tree structure with yes/no branches, multiple paths leading to recommendations
- Visual cues: Color-coded outcomes (Blue-Green=blue, Canary=yellow, Rolling=green), icons representing each strategy

**SPEAKER NOTES:**

"So which strategy should you use?

Blue-Green if you need instant rollback and have infrastructure for two environments. It's simpler to implement than Canary.

Canary if you want to validate with real production traffic gradually. Requires metric tracking and automated rollback.

Rolling if you're resource-constrained - updates happen in place. But rollback is slower.

For most AI systems, I recommend starting with Blue-Green. It's proven, straightforward, and gives you the safety net of instant rollback.

As your system matures and you add metric tracking, consider Canary for even safer rollouts."

[Transition]

-----

### SLIDE 8: SEGMENT 1 - KEY TAKEAWAY

**Title:** Segment 1 Summary

**Content:**

**Key Takeaway:** Deployment strategies enable zero-downtime deployments with fast, safe rollbacks.

**Remember:**
- Blue-Green: Two environments, instant rollback
- Canary: Gradual rollout, metric-based validation
- Choose based on your rollback needs and infrastructure

**You'll Practice:**
Exercise 2.1 - Implement a deployment strategy for your AI system

**Graphic:** Blue-Green and Canary patterns side-by-side

**SPEAKER NOTES:**

"Key points on deployment strategies:

Production deployments don't have to be risky. Blue-Green and Canary give you safety nets.

Blue-Green is simpler - two slots, smoke test, switch. Perfect for fast rollback.

Canary is more sophisticated - gradual rollout with metric monitoring. Perfect for validation with real traffic.

Choose based on your needs. Starting out? Blue-Green. Want gradual validation? Canary.

Exercise 2.1 will have you implement one of these for your AI system.

Questions before we move to secrets management?"

[Transition: Click to Segment 2]

-----

## SEGMENT 2: Secrets & Configuration Management
### Duration: 12 minutes | Slides 9-13

-----

### SLIDE 9: SECRETS MANAGEMENT CHALLENGE

**Title:** How Do You Keep API Keys Secure in Automated Deployments?

**Content:**

**The Problem:**
- Workflows need API keys to deploy
- Keys can't be in code (security risk)
- Different environments need different keys
- Secrets need rotation without code changes

**What Goes Wrong:**
- API keys committed to GitHub (exposed)
- Same key for staging and production (risky)
- Hard-coded secrets (can't rotate easily)
- Overly permissive access (anyone can see keys)

**Graphic:** Crossed-out bad practice (keys in code) vs. correct practice (GitHub Secrets)

**GRAPHICS:**

**Graphic 1: Secrets Management - Wrong vs. Right**
- Purpose: Clearly show the danger of committing secrets vs. proper secrets management
- Type: Before/after comparison with strong visual warnings
- Elements:
  - Left side (WRONG): Code file with API key visible in plain text, red X overlay
  - Right side (RIGHT): GitHub Secrets vault icon, encrypted key icon, workflow accessing secret securely
  - Danger symbols on wrong side (skull, warning signs)
  - Security shields on right side (lock, checkmark)
- Labels:
  - Wrong: "API key in code", "Committed to git", "EXPOSED", "Cannot rotate easily"
  - Right: "GitHub Secrets", "Encrypted storage", "SECURE", "Easy rotation", "Audited access"
- Relationships: Arrows showing wrong practice leading to compromised security, right practice leading to protected system
- Visual cues: Red danger zone for wrong practice, green security zone for right practice, "DO NOT" symbol prominently on left

**SPEAKER NOTES:**

"Your deployment workflow needs API keys. OpenAI keys, deployment tokens, monitoring webhooks.

How do you provide these keys without putting them in code?

[Point to bad practice]

If you commit keys to your repository, they're compromised. GitHub scans for this and alerts you, but damage may be done.

Hard-coding keys means you can't rotate them without changing code. And you definitely don't want the same production API key in your staging environment.

The solution is GitHub Secrets - encrypted secrets that workflows can access but humans can't easily view."

[Transition]

**BACKGROUND:**

**Rationale:**
- Secrets in code are immediately compromised when pushed to GitHub (public or private)
- GitHub's secret scanning detects and alerts on exposed credentials but prevention is better
- Encrypted secrets storage separates configuration (versioned) from credentials (secured)
- Environment-scoped secrets prevent production credentials from being used in development

**Key Research & Citations:**
- GitHub Secret Scanning has detected over 1 million exposed credentials since 2018
- 2021 security study: 6% of GitHub commits contained at least one exposed secret
- OWASP Top 10 includes "Sensitive Data Exposure" as critical security risk
- Zero-trust security model requires secrets rotation - hard-coded secrets prevent this

**Q&A Preparation:**
- *"What if someone with repo access views the secret in GitHub UI?"*: GitHub Secrets are write-only by default. You can add but not retrieve. Some cloud providers offer additional secret management (AWS Secrets Manager, Azure Key Vault).
- *"Can workflows accidentally log secrets?"*: GitHub automatically masks secret values in logs. But still practice never echo/print secrets.
- *"How often should we rotate secrets?"*: Depends on risk. Production API keys: quarterly minimum. After personnel changes: immediately. Use secret expiration where possible.

**Sources:**
- GitHub Secret Scanning: https://docs.github.com/en/code-security/secret-scanning/about-secret-scanning
- OWASP Sensitive Data Exposure: https://owasp.org/www-project-top-ten/
- Secrets Management Best Practices: https://www.hashicorp.com/resources/what-is-secrets-management

-----

### SLIDE 10: GITHUB SECRETS HIERARCHY

**Title:** Organizing Secrets: Repository vs. Environment

**Content:**

**Two Levels:**

**Repository Secrets:** Available to all workflows
```
Repository Settings → Secrets
├── AI_API_KEY
├── DEPLOYMENT_TOKEN
└── MONITORING_WEBHOOK
```

**Environment Secrets:** Specific to environments
```
Environments:
├── staging/
│   └── AI_API_KEY (staging key)
└── production/
    └── AI_API_KEY (production key)
```

**Best Practice:**
- Development/shared secrets: Repository level
- Environment-specific keys: Environment level
- Production secrets: Always environment-scoped

**Graphic:** Hierarchy diagram showing repository and environment secrets

**GRAPHICS:**

**Graphic 1: GitHub Secrets Hierarchy**
- Purpose: Show the two-level organization of secrets (repository vs. environment-specific)
- Type: Hierarchical tree diagram with scope visualization
- Elements:
  - Top level: Repository icon
  - Level 2a: "Repository Secrets" box containing: AI_API_KEY, DEPLOYMENT_TOKEN, MONITORING_WEBHOOK
  - Level 2b: "Environments" box branching to two environments
  - Level 3: "staging/" environment with AI_API_KEY (staging)
  - Level 3: "production/" environment with AI_API_KEY (production)
  - Scope indicators showing which secrets are available to which workflows
- Labels:
  - "Repository Secrets: Available to all workflows"
  - "Environment Secrets: Specific to environment"
  - "Production secrets require approval" badge on production environment
- Relationships: Tree structure showing containment and inheritance, arrows from workflows to accessible secrets
- Visual cues: Color coding (repository=blue, staging=yellow, production=red), lock icons on environment-specific secrets, shield icon on production

**SPEAKER NOTES:**

"GitHub Secrets has two levels.

Repository secrets are available to any workflow. Use these for shared secrets like monitoring webhooks or deployment tokens.

Environment secrets are scoped to specific environments. Your production AI_API_KEY is different from staging. Environment secrets enforce this.

[Point to environment structure]

When a workflow targets the production environment, it gets production secrets. Staging workflows get staging secrets. This prevents accidentally using production keys in staging.

Best practice: All production secrets should be environment-scoped. This adds protection rules - you can require approval before workflows access production secrets."

[Transition]

-----

### SLIDE 11: USING SECRETS IN WORKFLOWS

**Title:** Accessing Secrets in GitHub Actions

**Content:**

**Workflow Syntax:**
```yaml
jobs:
  deploy:
    environment: production  # Accesses production secrets
    steps:
      - name: Deploy with API key
        env:
          API_KEY: ${{ secrets.AI_API_KEY }}
          WEBHOOK: ${{ secrets.MONITORING_WEBHOOK }}
        run: |
          ./deploy.sh --api-key "$API_KEY"
```

**Key Points:**
- Reference with `${{ secrets.SECRET_NAME }}`
- Never echo secrets in logs
- Secrets are masked in workflow output
- Use environment-specific secrets for production

**Graphic:** Code snippet with annotations showing secret references

**SPEAKER NOTES:**

"Here's how you use secrets in workflows.

[Point to environment line]
Specify which environment this job uses. This determines which secrets are available.

[Point to env section]
Reference secrets with the secrets context: secrets.AI_API_KEY.

GitHub automatically masks secret values in logs. If you accidentally echo them, GitHub replaces the value with asterisks.

But still - never echo secrets. Never log them. Use them only where needed, as environment variables passed to scripts.

This keeps your keys secure while letting automated workflows use them."

[Transition]

-----

### SLIDE 12: CONFIGURATION AS CODE

**Title:** Managing Environment Configurations

**Content:**

**Configuration Files (NOT Secrets):**
```yaml
# configs/production.yml
ai:
  provider: openai
  model: gpt-4
  temperature: 0.7
  max_tokens: 2000

rate_limits:
  requests_per_minute: 100

monitoring:
  error_threshold: 0.02
```

**Commit configs to code, reference secrets:**
```yaml
ai:
  api_key: ${AI_API_KEY}  # From GitHub Secrets
  model: gpt-4            # Safe to commit
```

**Graphic:** Configuration files in version control, secrets in GitHub Secrets

**SPEAKER NOTES:**

"Configuration as code means your environment configs are versioned and tracked.

[Point to example]

Model selection, temperature settings, rate limits - these aren't secrets. They're configuration. Commit them to your repository.

But API keys? Those are secrets. Reference them as variables, keep actual values in GitHub Secrets.

This gives you the best of both worlds: tracked configuration history and secure secret management.

When you deploy, the workflow combines the config file with GitHub Secrets to build the complete configuration."

[Transition]

-----

### SLIDE 13: SEGMENT 2 - KEY TAKEAWAY

**Title:** Segment 2 Summary

**Content:**

**Key Takeaway:** GitHub Secrets keeps API keys secure while configuration as code tracks environment settings.

**Remember:**
- Use environment-specific secrets for production
- Never commit secrets to code
- Configuration (non-secret) should be versioned
- Reference secrets in workflows with `${{ secrets.NAME }}`

**You'll Practice:**
Exercise 2.2 configures secrets and environment-specific configurations

**Graphic:** Shield icon protecting secrets

**SPEAKER NOTES:**

"Key points on secrets management:

GitHub Secrets is your secret storage. Environment-scoped secrets add extra protection for production.

Never commit secrets to code. Never. GitHub scans for this, but prevention is better.

Configuration that isn't secret should be versioned - model settings, thresholds, etc.

And reference secrets in workflows using the secrets context.

Your capstone exercise will configure this properly for staging and production.

Questions on secrets before we move to monitoring?"

[Transition: Click to Segment 3]

-----

## SEGMENT 3: Monitoring & Observability
### Duration: 12 minutes | Slides 14-18

-----

### SLIDE 14: MONITORING CHALLENGE

**Title:** How Do You Know When Your AI System Breaks?

**Content:**

**The Problem:**
- AI systems fail silently (prompts return empty, errors ignored)
- Users experience problems before you know
- No visibility into performance degradation
- Manual checking doesn't scale

**What You Need to Know:**
- Is the system responding?
- Are error rates elevated?
- Is latency degrading?
- Are we hitting rate limits?

**Graphic:** Alert system visualization - system health → monitoring → alerts

**GRAPHICS:**

**Graphic 1: Monitoring and Alerting Flow**
- Purpose: Show how system health is continuously monitored and alerts are triggered
- Type: Flow diagram with feedback loop
- Elements:
  - AI System (server/cloud icon) at center
  - Health metrics emanating: Response time, Error rate, Token usage, Success rate
  - Monitoring service (eye/dashboard icon) collecting metrics
  - Threshold evaluation (decision diamond): "Metrics within thresholds?"
  - Alert channels: Slack (icon), Email (icon), PagerDuty (icon)
  - Response loop: Team → Investigate → Fix → System
- Labels:
  - "Continuous monitoring (every 15 min)"
  - "Threshold checks" with example values
  - "Alert routing" based on severity
  - "Incident response"
- Relationships: Circular flow showing continuous monitoring, conditional alerts, response actions
- Visual cues: Green for healthy metrics, yellow for warnings, red for critical alerts, arrows showing data flow

**SPEAKER NOTES:**

"Your AI system is deployed. How do you know if it's working?

AI systems often fail silently. A prompt might return empty results. An API call might timeout. Users see errors, but you don't know until support tickets arrive.

[Pause]

That's reactive. You want to be proactive.

You need monitoring: automated health checks that run continuously and alert you when things break.

Today we'll build health check workflows that run every 15 minutes, track key metrics, and alert via Slack/Discord/email when problems arise."

[Transition]

**BACKGROUND:**

**Rationale:**
- AI systems fail silently more often than traditional software (timeout, empty response, degraded quality)
- User-reported issues mean customers experienced problems before you knew
- Proactive monitoring shifts from reactive firefighting to preventive maintenance
- Automated health checks provide 24/7 coverage without human monitoring cost

**Key Research & Citations:**
- Google's "Four Golden Signals" of monitoring: Latency, Traffic, Errors, Saturation
- Observability vs Monitoring: Observability reveals "unknown unknowns" through instrumentation
- Mean Time To Detect (MTTD) critical for incident response - automated monitoring reduces MTTD from hours to minutes
- GitHub Actions scheduled workflows provide free monitoring infrastructure (no additional service needed)

**Q&A Preparation:**
- *"Why not use external monitoring service like Datadog or New Relic?"*: Those are excellent for production systems. GitHub Actions provides free tier for basic health checks. Use both - external for comprehensive monitoring, GitHub Actions for lightweight checks.
- *"What if health check itself fails due to network issue?"*: Implement retry logic and alert only on sustained failures. Single failure might be transient network issue.
- *"How do we avoid alert fatigue?"*: Tune alert thresholds carefully. Critical alerts should require action. Use warning vs critical severity levels. Provide actionable context in alerts.

**Sources:**
- Google SRE - The Four Golden Signals: https://sre.google/sre-book/monitoring-distributed-systems/
- Observability Engineering (O'Reilly): https://www.oreilly.com/library/view/observability-engineering/9781492076438/
- GitHub Actions Scheduled Events: https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#schedule

-----

### SLIDE 15: HEALTH CHECK WORKFLOWS

**Title:** Automated Health Checks with GitHub Actions

**Content:**

**Schedule-Triggered Workflow:**
```yaml
on:
  schedule:
    - cron: '*/15 * * * *'  # Every 15 minutes

jobs:
  health-check:
    steps:
      - name: Check AI endpoint
        run: |
          RESPONSE=$(curl -s $AI_ENDPOINT/health)
          if [ "$RESPONSE" != "OK" ]; then
            echo "Health check failed: $RESPONSE"
            exit 1
          fi

      - name: Alert on failure
        if: failure()
        run: |
          curl -X POST $SLACK_WEBHOOK \
            -d '{"text":"AI system health check FAILED"}'
```

**Benefits:**
- Runs automatically every 15 minutes
- Alerts immediately on failure
- No infrastructure needed (GitHub Actions)

**Graphic:** Timeline showing health checks running every 15 minutes

**GRAPHICS:**

**Graphic 1: Automated Health Check Timeline**
- Purpose: Visualize the continuous nature of scheduled health checks
- Type: Horizontal timeline with recurring events
- Elements:
  - Timeline bar spanning 2 hours
  - Health check events (heartbeat icon) at 15-minute intervals (00:00, 00:15, 00:30, 00:45, etc.)
  - Each check shows: Request sent → Response received → Status evaluated
  - One failed check shown with alert notification
  - Most checks showing green success status
- Labels:
  - "Every 15 minutes (cron: */15 * * * *)"
  - Success checks: "✓ Health OK"
  - Failed check: "✗ Health check failed → Alert sent to Slack"
  - Timeline markers showing times
- Relationships: Recurring pattern, failed check triggering immediate alert
- Visual cues: Green checkmarks for successful checks, red X for failure, alert icon (bell) on failure, GitHub Actions logo indicating automated execution

**SPEAKER NOTES:**

"Health check workflows use schedule triggers.

[Point to cron]
This cron expression means 'every 15 minutes'. GitHub Actions runs this workflow automatically.

[Point to steps]
First step: call your AI system health endpoint. Check if it responds correctly.

Second step: if the first step failed, send an alert. This uses Slack webhook, but you could use Discord, email, PagerDuty, whatever your team monitors.

The beauty is this runs continuously, automatically. Your AI system is monitored 24/7 with zero manual effort."

[Transition]

-----

### SLIDE 16: KEY METRICS TO TRACK

**Title:** What to Monitor in AI Systems

**Content:**

**Critical Metrics:**

| Metric | Threshold | Action |
|--------|-----------|--------|
| **Error Rate** | > 5% for 5 min | Critical alert |
| **Latency (p95)** | > 2000ms for 10 min | Warning |
| **Token Usage** | > 90% of limit | Warning |
| **Success Rate** | < 95% for 5 min | Critical alert |
| **Health Endpoint** | Any failure | Immediate alert |

**What to Track:**
- Request volume and success rate
- Response latency (p50, p95, p99)
- Token consumption vs. limits
- Error types and frequencies

**Graphic:** Dashboard visualization showing these metrics

**GRAPHICS:**

**Graphic 1: AI System Monitoring Dashboard**
- Purpose: Show the key metrics and thresholds for monitoring AI systems
- Type: Dashboard mockup with gauges and graphs
- Elements:
  - Metric panel 1: Error Rate gauge (current: 2.3%, threshold: 5%, status: green)
  - Metric panel 2: Latency graph showing P50/P95/P99 lines (P95 current: 1.8s, threshold: 2s, status: green)
  - Metric panel 3: Token Usage progress bar (current: 65%, warning: 90%, status: green)
  - Metric panel 4: Success Rate gauge (current: 97.5%, threshold: 95%, status: green)
  - Metric panel 5: Health Endpoint status (current: OK, any failure = critical)
  - Alert indicator panel showing current alert status
- Labels:
  - Each metric clearly labeled with current value and threshold
  - Status indicators: "Healthy", "Warning", "Critical"
  - Time range selector (Last 1 hour / 24 hours / 7 days)
- Relationships: All metrics feeding into overall system health status
- Visual cues: Color-coded status (green=healthy, yellow=warning, red=critical), trend arrows showing direction, threshold lines on graphs

**SPEAKER NOTES:**

"What should you monitor?

Error rate is critical. If more than 5% of requests fail for 5 minutes, something is broken. Critical alert.

Latency tells you about performance degradation. If p95 latency exceeds 2 seconds, users are experiencing slowness. Warning alert.

Token usage matters for AI systems. If you're at 90% of your token limit, you need to know before hitting the wall.

Success rate combines several signals. Below 95% means something is wrong.

And health endpoints should never fail. Any failure is immediate alert.

[Point to graphic]

You don't need fancy dashboards to start. Log these metrics, alert on thresholds. That's 80% of the value."

[Transition]

-----

### SLIDE 17: ALERTING PATTERNS

**Title:** Effective Alerting for AI Systems

**Content:**

**Alert Levels:**

**Critical** (Immediate action required)
- Health check failure
- Error rate > 5% for 5 minutes
- Success rate < 95%

**Warning** (Investigate soon)
- Latency p95 > 2000ms
- Token usage > 90%
- Error rate 2-5%

**Info** (Awareness)
- Deployment completed
- Version rollout milestone
- Daily summary

**Best Practices:**
- Alert where your team looks (Slack, Discord, email)
- Include context in alerts (what failed, current metrics)
- Actionable: Each alert should have clear next steps

**Graphic:** Alert severity levels pyramid

**GRAPHICS:**

**Graphic 1: Alert Severity Pyramid**
- Purpose: Show the hierarchy and volume of different alert types
- Type: Inverted pyramid with three tiers
- Elements:
  - Top tier (smallest, red): "Critical" - Immediate action required
  - Middle tier (medium, yellow): "Warning" - Investigate soon
  - Bottom tier (largest, blue): "Info" - Awareness only
  - Volume indicators showing relative frequency
- Labels:
  - Critical examples: "Health check failure", "Error rate > 5%", "Success rate < 95%"
  - Warning examples: "Latency P95 > 2s", "Token usage > 90%", "Error rate 2-5%"
  - Info examples: "Deployment completed", "Daily summary", "Version rollout milestone"
  - Response times: Critical (immediate), Warning (within 1 hour), Info (no action needed)
- Relationships: Inverse pyramid showing fewer critical alerts, more info alerts
- Visual cues: Color coding (red/yellow/blue), alert icons (bell, flag, info icon), urgency indicators

**SPEAKER NOTES:**

"Not all alerts are equal.

Critical alerts mean 'wake someone up'. Health check failed? Production is down. Critical.

Warning alerts mean 'investigate soon'. Latency is elevated. Not an emergency, but trending wrong. Warning.

Info alerts are FYI. Deployment succeeded. Daily summary of metrics. No action needed.

[Point to best practices]

Alert where your team actually looks. If nobody checks email, don't alert via email. Use Slack or Discord.

Include context. Don't just say 'error rate high'. Say 'Error rate: 7.2% (threshold: 5%) in last 5 minutes. Check logs: [link]'.

And make alerts actionable. What should the on-call person do? Include runbook links."

[Transition]

-----

### SLIDE 18: SEGMENT 3 - KEY TAKEAWAY

**Title:** Segment 3 Summary

**Content:**

**Key Takeaway:** Automated monitoring detects failures before users report them.

**Remember:**
- Health check workflows run on schedule (every 15 min)
- Track error rate, latency, token usage, success rate
- Alert at appropriate severity levels (critical, warning, info)
- Alert where your team actually looks

**You'll Practice:**
Exercise 2.2 - Build monitoring workflow with health checks and alerting

**Graphic:** Monitoring workflow protecting production

**SPEAKER NOTES:**

"Key points on monitoring:

Automated monitoring is proactive. You find problems before users do.

Health check workflows use GitHub Actions schedule triggers - no additional infrastructure needed.

Track the metrics that matter: error rate, latency, token usage, success rate.

Alert appropriately. Critical for production-down. Warning for degradation. Info for awareness.

Exercise 2.2 will have you build a complete monitoring workflow.

Questions on monitoring before we assemble the complete pipeline?"

[Transition: Click to Segment 4]

-----

## SEGMENT 4: Complete CI/CD Pipeline Assembly
### Duration: 9 minutes | Slides 19-22

-----

### SLIDE 19: THE COMPLETE PIPELINE

**Title:** From Commit to Production: Complete CI/CD

**Content:**

**Pipeline Stages:**
```
Developer commits
    ↓
Validate (syntax, schema, security)
    ↓
Test (unit, integration, coverage)
    ↓
Deploy to Staging (automatic)
    ↓
Staging Tests (smoke tests)
    ↓
Deploy to Production (manual approval)
    ↓
Production Deployment (blue-green/canary)
    ↓
Monitor (health checks, alerts)
```

**Workflow Files:**
- `validate.yml` - Validation checks
- `test.yml` - Automated tests
- `deploy-staging.yml` - Staging deployment
- `deploy-production.yml` - Production deployment
- `monitoring.yml` - Health checks

**Graphic:** Complete pipeline flow diagram

**GRAPHICS:**

**Graphic 1: Complete CI/CD Pipeline Stages**
- Purpose: Show the end-to-end pipeline from commit to production monitoring
- Type: Vertical flowchart with stage gates
- Elements:
  - Stage 1: "Developer commits" (developer icon)
  - Stage 2: "Validate" (syntax, schema, security) - automated
  - Stage 3: "Test" (unit, integration, coverage) - automated
  - Stage 4: "Deploy to Staging" - automated on success
  - Stage 5: "Staging Tests" (smoke tests) - automated
  - Stage 6: "Deploy to Production" - MANUAL APPROVAL required
  - Stage 7: "Production Deployment" (blue-green/canary) - automated after approval
  - Stage 8: "Monitor" (health checks, alerts) - continuous
- Labels:
  - Each stage clearly labeled with actions
  - Automation indicators: "Auto" vs. "Manual approval required"
  - Success criteria at each gate
  - "STOP" indicators on failure paths
- Relationships: Sequential flow with gates, failures stop progression, monitoring as continuous loop
- Visual cues: Green arrows for automated progression, orange for manual approval, red for failure paths, continuous monitoring loop around production

**SPEAKER NOTES:**

"Let's bring everything together into a complete CI/CD pipeline.

[Walk through each stage]

Developer commits code. Validation runs automatically - syntax checks, security scans.

If validation passes, tests run - unit tests, integration tests, coverage checks.

If tests pass, code deploys automatically to staging. No human intervention needed.

Staging deployment triggers smoke tests. Does staging work?

If staging is healthy, production deployment becomes available. But this requires manual approval - a human clicks 'deploy'.

Once approved, production deployment executes - using blue-green or canary strategy.

After deployment, monitoring watches continuously. Health checks every 15 minutes.

This entire pipeline is automated. Humans only intervene for production approval."

[Transition]

**BACKGROUND:**

**Rationale:**
- Complete CI/CD pipeline automates everything except human judgment for production deployment
- Each stage adds a protection layer: validation catches syntax, tests catch logic, staging catches integration issues
- Manual approval for production preserves human oversight while automating mechanics
- Pipeline provides audit trail of what was deployed, when, by whom, and what checks passed

**Key Research & Citations:**
- DevOps Research & Assessment (DORA): Elite performers deploy on-demand with lead times < 1 hour
- Continuous Delivery book (Humble & Farley): Deployment pipeline is the manifestation of your process for getting software from version control to users
- Google's "Release Engineering" emphasizes automation with human checkpoints for critical decisions
- GitHub's State of the Octoverse: Organizations using CI/CD have 2x faster incident resolution

**Q&A Preparation:**
- *"Should production deployment always require manual approval?"*: For most organizations, yes. Very mature teams with comprehensive monitoring might auto-deploy to production using Canary with automated rollback. Start with manual approval, earn full automation.
- *"What if we need emergency hotfix and approver is unavailable?"*: Configure multiple approved reviewers. For true emergencies, repository admins can override (but it's logged and should be reviewed).
- *"How do we handle database migrations in pipeline?"*: Run migrations as separate stage before deployment. Use backward-compatible migrations. Consider blue-green for databases or separate migration pipeline.

**Sources:**
- DORA State of DevOps Reports: https://dora.dev/research/
- Continuous Delivery (Jez Humble): https://continuousdelivery.com/
- GitHub State of the Octoverse: https://octoverse.github.com/

-----

### SLIDE 20: ENVIRONMENT PROTECTION RULES

**Title:** Protecting Production with GitHub Environments

**Content:**

**Environment Settings (Production):**

**Required Reviewers:**
- At least 1 reviewer before deployment
- Specific teams/individuals can approve

**Wait Timer:**
- Optional delay between approval and deployment
- Prevents rushed deployments

**Deployment Branches:**
- Only main branch can deploy to production
- Prevents deploying from feature branches

**Benefits:**
- Human oversight for production changes
- Audit trail of who approved what
- Prevents accidental deployments

**Graphic:** GitHub environment protection settings screenshot

**SPEAKER NOTES:**

"GitHub Environments let you protect production.

Required reviewers mean production deployments need approval. Someone other than the developer must review and approve.

Wait timer adds a cooling-off period. Approved a deployment but want to think twice? Wait timer gives you that window.

Deployment branch restrictions ensure only main branch deploys to production. Feature branches can't accidentally push to production.

[Point to benefits]

This adds human judgment to automated processes. Automation handles the mechanics. Humans make the 'yes deploy to production' decision.

And you get a complete audit trail. Who approved this production deployment? When? Why? It's all logged."

[Transition]

-----

### SLIDE 21: WORKFLOW DEPENDENCIES

**Title:** Orchestrating Workflow Jobs with Dependencies

**Content:**

**Job Dependencies:**
```yaml
jobs:
  validate:
    runs-on: ubuntu-latest
    steps: [...]

  test:
    needs: validate  # Only runs if validate succeeds
    steps: [...]

  deploy-staging:
    needs: test
    environment: staging
    steps: [...]

  deploy-production:
    needs: deploy-staging
    environment: production  # Requires approval
    steps: [...]
```

**Benefits:**
- Failed validation blocks testing
- Failed tests block deployment
- Clear dependency chain
- Fail fast (stop at first failure)

**Graphic:** Dependency graph showing job relationships

**GRAPHICS:**

**Graphic 1: Workflow Job Dependencies**
- Purpose: Visualize how jobs depend on each other and execute in sequence
- Type: Directed acyclic graph (DAG)
- Elements:
  - Job node 1: "validate" (no dependencies)
  - Job node 2: "test" (depends on validate)
  - Job node 3: "deploy-staging" (depends on test, has environment: staging)
  - Job node 4: "deploy-production" (depends on deploy-staging, has environment: production, requires approval)
  - Dependency arrows with "needs:" labels
  - Environment shields on deployment jobs
  - Approval gate icon on production deployment
- Labels:
  - Each job labeled with name and key attributes
  - "needs: validate", "needs: test", "needs: deploy-staging" on arrows
  - "Manual approval required" on production job
  - Environment names clearly marked
- Relationships: Directed arrows showing execution order, no job runs until dependencies complete
- Visual cues: Color coding by stage (validate=blue, test=green, deploy=orange), approval icon (hand/checkmark), environment badges

**SPEAKER NOTES:**

"Workflow jobs use dependencies to create ordered execution.

[Point to needs: validate]
Test job only runs if validate succeeds. If validation fails, we don't waste time running tests.

[Point to needs: test]
Staging deployment only runs if tests pass.

[Point to needs: deploy-staging]
Production deployment requires staging success plus manual approval.

This creates a safety net. Each stage must pass before the next stage runs.

And it fails fast. Syntax error? Validation fails, pipeline stops. No point running tests if code doesn't validate."

[Transition]

-----

### SLIDE 22: SEGMENT 4 - KEY TAKEAWAY

**Title:** Segment 4 Summary

**Content:**

**Key Takeaway:** Complete CI/CD pipeline automates validation through deployment with human oversight for production.

**Pipeline Stages:**
1. Validate → 2. Test → 3. Stage → 4. Approve → 5. Deploy → 6. Monitor

**Remember:**
- Automation handles mechanics, humans approve production
- Dependencies create fail-fast pipeline
- Environment protection adds safety gates
- Monitoring completes the feedback loop

**You'll Practice:**
Exercise 2.3 (Capstone) - Assemble your complete CI/CD pipeline

**Graphic:** Complete pipeline with all components

**SPEAKER NOTES:**

"The complete CI/CD pipeline brings everything together.

Validation catches errors early. Tests verify behavior. Staging provides pre-production testing. Approval adds human judgment. Deployment uses safe strategies. Monitoring provides feedback.

Each stage builds on the previous. Each stage adds a layer of protection.

And it's automated end-to-end. Push a commit, the pipeline executes. The only human touchpoint is production approval.

Your capstone exercise - Exercise 2.3 - assembles your complete pipeline. All the pieces you've built over two sessions come together.

This is production-ready DevOps for AI systems."

[Transition: Click to Closing]

-----

## CLOSING SECTION
### Duration: 3 minutes | Slides 23-25

-----

### SLIDE 23: HOMEWORK OVERVIEW

**Title:** Module Capstone: Complete CI/CD Pipeline

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 2.1: Deployment Strategy | 30 min | Design doc + deployment workflow | Blue-green or canary deployment |
| Exercise 2.2: Monitoring & Alerting | 25 min | Health check workflow + alerts | Monitoring, alerting |
| Exercise 2.3: Complete Pipeline (Capstone) | 20 min | Full CI/CD pipeline | All module skills |
| **Total** | **75 min** | | |

**Capstone Deliverables:**
- `validate.yml`, `test.yml`, `deploy-staging.yml`, `deploy-production.yml`, `monitoring.yml`
- Environment configurations (staging, production)
- Complete documentation

**Graphic:** Pipeline diagram showing all workflow files

**GRAPHICS:**

**Graphic 1: Complete CI/CD Workflow Files Architecture**
- Purpose: Show all the workflow files and how they interconnect in the complete system
- Type: Architecture diagram with file references
- Elements:
  - File stack showing `.github/workflows/` directory
  - Workflow file 1: `validate.yml` - Validation checks
  - Workflow file 2: `test.yml` - Automated tests
  - Workflow file 3: `deploy-staging.yml` - Staging deployment
  - Workflow file 4: `deploy-production.yml` - Production deployment with approval
  - Workflow file 5: `monitoring.yml` - Health checks and alerting
  - Environment configurations: staging/, production/ (with secrets)
  - Documentation: README, deployment procedures
- Labels:
  - Each file labeled with purpose and trigger conditions
  - Arrows showing execution flow and dependencies
  - Environment associations clearly marked
- Relationships: Files triggering each other, dependencies between workflows, environments linked to deployment workflows
- Visual cues: File icons, workflow connections with arrows, environment badges, color coding by workflow type

**SPEAKER NOTES:**

"Your homework completes the module with three exercises totaling 75 minutes.

Exercise 2.1, 30 minutes. Implement a deployment strategy - blue-green or canary. You'll design it, document it, and build the workflow.

Exercise 2.2, 25 minutes. Configure monitoring and alerting. Health checks every 15 minutes, alerts on failures.

Exercise 2.3 is the capstone - 20 minutes. Assemble everything into a complete pipeline. This brings together all the workflows, environment configs, and protection rules.

When you're done, you'll have a production-ready CI/CD system for AI workflows.

All instructions are in your participant guide."

[Transition]

-----

### SLIDE 24: RESOURCES

**Title:** Resources for Completion

**Content:**

**Module Appendices:**
- Appendix A: GitHub Actions Reference
- Appendix B: Troubleshooting Guide
- Appendix C: Security Checklist

**Templates:**
- Deployment workflow templates
- Monitoring workflow examples
- Environment configuration templates

**External Resources:**
- GitHub Environments documentation
- GitHub Secrets best practices
- Blue-Green and Canary deployment patterns

**Support:**
- Questions: [Async channel]
- Review module materials

**Graphic:** Resource icons

**SPEAKER NOTES:**

"Resources to support your work:

Module appendices have reference material and troubleshooting. Appendix C's security checklist is especially important for production deployments.

Templates for all workflows are in the participant guide.

External docs cover GitHub-specific features like Environments and Secrets.

If you get stuck, review the module materials first, then post in the support channel."

[Transition]

-----

### SLIDE 25: MODULE COMPLETION

**Title:** Congratulations - Module 5 Complete!

**Content:**

**What You've Built:**
- ✓ GitHub Actions automation
- ✓ Version control for AI artifacts
- ✓ Automated testing with coverage
- ✓ Deployment strategies (blue-green/canary)
- ✓ Secrets management
- ✓ Monitoring and alerting
- ✓ Complete CI/CD pipeline

**Next Steps:**
1. Complete capstone exercise
2. Deploy your pipeline to production
3. Apply to your Block 3 autonomous agents
4. Consider other advanced modules

**You're now equipped for production-grade AI DevOps!**

**Graphic:** Completion badge or achievement visual

**SPEAKER NOTES:**

"Congratulations! You've completed Advanced Module 5.

[Read through checklist]

You've built a complete DevOps system. GitHub Actions automation. Version control. Testing. Deployment strategies. Monitoring. The works.

Next steps: Complete the capstone exercise. Get your pipeline running. Then apply it to your Block 3 autonomous agents - they're ready for production now.

This module gave you production-grade DevOps skills. You can confidently deploy AI systems knowing they're validated, tested, and monitored.

[Pause]

Final questions? ... Excellent work everyone. You've leveled up your AI DevOps capabilities significantly. Now go build production systems!"

---

## APPENDICES

### Appendix A: Slide Type Definitions

**TITLE SLIDE**, **PROBLEM STATEMENT**, **INSIGHT / REVELATION**, **CONCEPT INTRODUCTION**, **FRAMEWORK / MODEL**, **COMPARISON**, **DEEP DIVE**, **CASE STUDY**, **PATTERN / BEST PRACTICE**, **METRICS / DATA**, **ARCHITECTURE / DIAGRAM**, **OBJECTION HANDLING**, **ACTION / NEXT STEPS**, **SUMMARY / RECAP**, **CLOSING / CALL TO ACTION**, **Q&A / CONTACT**, **APPENDIX**

### Appendix B: BACKGROUND & Implementation Guidance

See template for full BACKGROUND section structure (Rationale, Key Research & Citations, Q&A Preparation) and Implementation Guidance structure (Getting Started, Best Practices, Common Pitfalls, Tools & Technologies).

### Appendix C: Deployment Strategy Implementation Guide

**Blue-Green Deployment Implementation:**

**Directory Structure:**
```
.github/workflows/
├── deploy-blue-green.yml
└── switch-traffic.yml

scripts/
├── deploy-to-slot.sh
├── smoke-test.sh
└── switch-traffic.sh

deployments/
├── blue/
│   ├── prompts/
│   └── configs/
└── green/
    ├── prompts/
    └── configs/
```

**Complete Blue-Green Workflow:**
```yaml
name: Blue-Green Deployment

on:
  workflow_dispatch:
    inputs:
      target_slot:
        description: 'Target deployment slot (blue or green)'
        required: true
        type: choice
        options:
          - blue
          - green

jobs:
  deploy-to-inactive-slot:
    runs-on: ubuntu-latest
    environment: production
    steps:
      - uses: actions/checkout@v4

      - name: Determine inactive slot
        id: slot
        run: |
          # Get currently active slot
          ACTIVE_SLOT=$(curl -s ${{ secrets.PROD_ENDPOINT }}/active-slot)
          if [ "$ACTIVE_SLOT" = "blue" ]; then
            echo "inactive=green" >> $GITHUB_OUTPUT
            echo "active=blue" >> $GITHUB_OUTPUT
          else
            echo "inactive=blue" >> $GITHUB_OUTPUT
            echo "active=green" >> $GITHUB_OUTPUT
          fi

      - name: Deploy to inactive slot
        run: |
          ./scripts/deploy-to-slot.sh \
            --slot ${{ steps.slot.outputs.inactive }} \
            --version ${{ github.sha }}
        env:
          API_KEY: ${{ secrets.AI_API_KEY }}

      - name: Wait for deployment
        run: sleep 30

      - name: Smoke test inactive slot
        run: |
          ./scripts/smoke-test.sh \
            --slot ${{ steps.slot.outputs.inactive }} \
            --endpoint ${{ secrets.PROD_ENDPOINT }}

      - name: Health check inactive slot
        run: |
          RESPONSE=$(curl -s -o /dev/null -w "%{http_code}" \
            ${{ secrets.PROD_ENDPOINT }}/${{ steps.slot.outputs.inactive }}/health)
          if [ "$RESPONSE" != "200" ]; then
            echo "Health check failed: $RESPONSE"
            exit 1
          fi

  switch-traffic:
    needs: deploy-to-inactive-slot
    runs-on: ubuntu-latest
    environment: production
    steps:
      - name: Switch traffic to new slot
        run: |
          ./scripts/switch-traffic.sh \
            --from ${{ needs.deploy-to-inactive-slot.steps.slot.outputs.active }} \
            --to ${{ needs.deploy-to-inactive-slot.steps.slot.outputs.inactive }}

      - name: Monitor for 5 minutes
        run: |
          for i in {1..5}; do
            echo "Monitoring minute $i/5..."
            ERROR_RATE=$(curl -s ${{ secrets.PROD_ENDPOINT }}/metrics/error-rate)
            if (( $(echo "$ERROR_RATE > 0.05" | bc -l) )); then
              echo "Error rate elevated: $ERROR_RATE"
              echo "Initiating rollback..."
              ./scripts/switch-traffic.sh \
                --from ${{ needs.deploy-to-inactive-slot.steps.slot.outputs.inactive }} \
                --to ${{ needs.deploy-to-inactive-slot.steps.slot.outputs.active }}
              exit 1
            fi
            sleep 60
          done

      - name: Deployment success notification
        if: success()
        run: |
          curl -X POST ${{ secrets.SLACK_WEBHOOK }} \
            -H 'Content-Type: application/json' \
            -d '{
              "text": "✅ Blue-Green deployment successful",
              "blocks": [{
                "type": "section",
                "text": {
                  "type": "mrkdwn",
                  "text": "*Deployment Complete*\nSlot: ${{ needs.deploy-to-inactive-slot.steps.slot.outputs.inactive }}\nVersion: ${{ github.sha }}"
                }
              }]
            }'
```

**Canary Deployment Implementation:**

**Progressive Rollout Workflow:**
```yaml
name: Canary Deployment

on:
  workflow_dispatch:
    inputs:
      version:
        description: 'Version to deploy'
        required: true
        type: string

jobs:
  deploy-canary-10:
    runs-on: ubuntu-latest
    environment: production
    steps:
      - uses: actions/checkout@v4

      - name: Deploy to 10% canary
        run: |
          ./scripts/deploy-canary.sh \
            --version ${{ inputs.version }} \
            --percentage 10

      - name: Monitor metrics for 10 minutes
        id: monitor_10
        run: |
          ./scripts/monitor-metrics.sh \
            --duration 600 \
            --error-threshold 0.05 \
            --latency-threshold 2000

  deploy-canary-25:
    needs: deploy-canary-10
    runs-on: ubuntu-latest
    environment: production
    steps:
      - name: Increase to 25%
        run: |
          ./scripts/deploy-canary.sh \
            --version ${{ inputs.version }} \
            --percentage 25

      - name: Monitor metrics for 10 minutes
        run: |
          ./scripts/monitor-metrics.sh \
            --duration 600 \
            --error-threshold 0.05 \
            --latency-threshold 2000

  deploy-canary-50:
    needs: deploy-canary-25
    runs-on: ubuntu-latest
    environment: production
    steps:
      - name: Increase to 50%
        run: |
          ./scripts/deploy-canary.sh \
            --version ${{ inputs.version }} \
            --percentage 50

      - name: Monitor metrics for 15 minutes
        run: |
          ./scripts/monitor-metrics.sh \
            --duration 900 \
            --error-threshold 0.05 \
            --latency-threshold 2000

  deploy-canary-100:
    needs: deploy-canary-50
    runs-on: ubuntu-latest
    environment: production
    steps:
      - name: Complete rollout to 100%
        run: |
          ./scripts/deploy-canary.sh \
            --version ${{ inputs.version }} \
            --percentage 100

      - name: Final monitoring
        run: |
          ./scripts/monitor-metrics.sh \
            --duration 900 \
            --error-threshold 0.05 \
            --latency-threshold 2000

      - name: Deployment complete notification
        if: success()
        run: |
          curl -X POST ${{ secrets.SLACK_WEBHOOK }} \
            -H 'Content-Type: application/json' \
            -d '{
              "text": "🎉 Canary deployment complete: ${{ inputs.version }} at 100%"
            }'

  rollback:
    if: failure()
    needs: [deploy-canary-10, deploy-canary-25, deploy-canary-50, deploy-canary-100]
    runs-on: ubuntu-latest
    environment: production
    steps:
      - name: Automatic rollback
        run: |
          ./scripts/rollback-canary.sh \
            --to-previous-version

      - name: Rollback notification
        run: |
          curl -X POST ${{ secrets.SLACK_WEBHOOK }} \
            -H 'Content-Type: application/json' \
            -d '{
              "text": "⚠️ Canary deployment rolled back due to metric degradation"
            }'
```

**Monitoring Script (monitor-metrics.sh):**
```bash
#!/bin/bash

DURATION=${1:-600}  # Default 10 minutes
ERROR_THRESHOLD=${2:-0.05}  # Default 5%
LATENCY_THRESHOLD=${3:-2000}  # Default 2000ms

START_TIME=$(date +%s)
END_TIME=$((START_TIME + DURATION))

while [ $(date +%s) -lt $END_TIME ]; do
  # Fetch metrics
  ERROR_RATE=$(curl -s "$METRICS_ENDPOINT/error-rate")
  LATENCY_P95=$(curl -s "$METRICS_ENDPOINT/latency-p95")
  SUCCESS_RATE=$(curl -s "$METRICS_ENDPOINT/success-rate")

  echo "$(date): Error Rate: $ERROR_RATE, Latency P95: $LATENCY_P95ms, Success: $SUCCESS_RATE%"

  # Check thresholds
  if (( $(echo "$ERROR_RATE > $ERROR_THRESHOLD" | bc -l) )); then
    echo "❌ Error rate exceeded threshold: $ERROR_RATE > $ERROR_THRESHOLD"
    exit 1
  fi

  if (( $(echo "$LATENCY_P95 > $LATENCY_THRESHOLD" | bc -l) )); then
    echo "❌ Latency exceeded threshold: $LATENCY_P95ms > $LATENCY_THRESHOLD ms"
    exit 1
  fi

  if (( $(echo "$SUCCESS_RATE < 0.95" | bc -l) )); then
    echo "❌ Success rate below threshold: $SUCCESS_RATE < 95%"
    exit 1
  fi

  sleep 30  # Check every 30 seconds
done

echo "✅ Metrics healthy for $DURATION seconds"
exit 0
```

### Appendix D: Secrets Management Configuration Guide

**GitHub Secrets Setup (via UI):**

1. **Repository Secrets:**
   - Navigate to: Repository → Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Add:
     - `SLACK_WEBHOOK` - Slack webhook URL for notifications
     - `MONITORING_ENDPOINT` - Monitoring service endpoint

2. **Environment Secrets:**
   - Navigate to: Repository → Settings → Environments
   - Create "staging" environment:
     - Add secret: `AI_API_KEY` (staging API key)
     - Add secret: `DEPLOYMENT_TOKEN` (staging deployment token)
   - Create "production" environment:
     - Add secret: `AI_API_KEY` (production API key)
     - Add secret: `DEPLOYMENT_TOKEN` (production deployment token)
     - Configure protection rules:
       - ✅ Required reviewers: Add team members
       - ✅ Wait timer: 5 minutes (optional)
       - ✅ Deployment branches: Only `main`

**Using Secrets in Workflows:**
```yaml
jobs:
  deploy-staging:
    environment: staging
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to staging
        env:
          API_KEY: ${{ secrets.AI_API_KEY }}  # Uses staging key
        run: ./deploy.sh

  deploy-production:
    environment: production  # Requires approval
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to production
        env:
          API_KEY: ${{ secrets.AI_API_KEY }}  # Uses production key
        run: ./deploy.sh
```

**Secret Rotation Procedure:**

1. **Generate New Secret:**
   ```bash
   # Example: Generate new API key from provider
   NEW_API_KEY=$(openai api keys create --name "prod-key-2026-01")
   ```

2. **Update GitHub Secret:**
   - Repository Settings → Secrets → Edit `AI_API_KEY`
   - Paste new value
   - Save

3. **Test Deployment:**
   - Run deployment to staging first
   - Verify new key works
   - Deploy to production

4. **Revoke Old Secret:**
   - Delete old API key from provider
   - Document rotation in audit log

**Secrets Security Checklist:**
- [ ] All secrets stored in GitHub Secrets (never in code)
- [ ] Production secrets use environment scope
- [ ] Secret names are descriptive (not generic like `KEY1`)
- [ ] Secrets are never logged or echoed
- [ ] Rotation schedule documented
- [ ] Access to secrets repository settings limited to admins
- [ ] Secret scanning enabled on repository

### Appendix E: Configuration Management Patterns

**Environment Configuration Structure:**

```yaml
# configs/base.yml - Shared configuration
ai:
  provider: openai
  temperature: 0.7
  max_tokens: 2000

rate_limits:
  burst_size: 10

monitoring:
  health_check_interval: 900  # 15 minutes

# configs/staging.yml - Staging overrides
ai:
  model: gpt-4o-mini  # Cheaper model for staging
  api_key: ${AI_API_KEY}  # From GitHub Secrets

deployment:
  endpoint: https://staging.example.com

rate_limits:
  requests_per_minute: 50

# configs/production.yml - Production overrides
ai:
  model: gpt-4
  api_key: ${AI_API_KEY}  # From GitHub Secrets

deployment:
  endpoint: https://api.example.com

rate_limits:
  requests_per_minute: 100

monitoring:
  error_threshold: 0.02  # 2% in production
```

**Configuration Loading Script:**
```javascript
// scripts/load-config.js
const fs = require('fs');
const yaml = require('js-yaml');
const deepmerge = require('deepmerge');

function loadConfig(environment) {
  // Load base config
  const baseConfig = yaml.load(
    fs.readFileSync('configs/base.yml', 'utf8')
  );

  // Load environment-specific config
  const envConfig = yaml.load(
    fs.readFileSync(`configs/${environment}.yml`, 'utf8')
  );

  // Merge configs (env overrides base)
  const merged = deepmerge(baseConfig, envConfig);

  // Substitute environment variables
  return substituteEnvVars(merged);
}

function substituteEnvVars(config) {
  const configString = JSON.stringify(config);
  const substituted = configString.replace(
    /\$\{([^}]+)\}/g,
    (match, envVar) => process.env[envVar] || match
  );
  return JSON.parse(substituted);
}

// Usage
const environment = process.env.ENVIRONMENT || 'development';
const config = loadConfig(environment);
console.log(JSON.stringify(config, null, 2));
```

**Workflow Integration:**
```yaml
jobs:
  deploy:
    environment: production
    steps:
      - uses: actions/checkout@v4

      - name: Load configuration
        env:
          ENVIRONMENT: production
          AI_API_KEY: ${{ secrets.AI_API_KEY }}
        run: |
          node scripts/load-config.js > runtime-config.json

      - name: Deploy with config
        run: |
          ./deploy.sh --config runtime-config.json
```

### Appendix F: Monitoring & Alerting Configuration

**Health Check Endpoints (Express.js example):**

```javascript
// server.js - Health check endpoints
const express = require('express');
const app = express();

// Basic health check
app.get('/health', (req, res) => {
  res.status(200).json({ status: 'OK' });
});

// Detailed health check
app.get('/health/detailed', async (req, res) => {
  const health = {
    status: 'OK',
    timestamp: new Date().toISOString(),
    checks: {
      ai_api: await checkAIAPI(),
      database: await checkDatabase(),
      memory: checkMemory(),
      disk: checkDisk()
    }
  };

  const allHealthy = Object.values(health.checks)
    .every(check => check.status === 'OK');

  res.status(allHealthy ? 200 : 503).json(health);
});

// Metrics endpoint
app.get('/metrics', (req, res) => {
  const metrics = {
    error_rate: calculateErrorRate(),
    latency_p50: calculateLatencyPercentile(50),
    latency_p95: calculateLatencyPercentile(95),
    latency_p99: calculateLatencyPercentile(99),
    success_rate: calculateSuccessRate(),
    token_usage: getTokenUsage(),
    request_count: getRequestCount()
  };

  res.json(metrics);
});

async function checkAIAPI() {
  try {
    // Make test API call
    const response = await fetch(process.env.AI_ENDPOINT + '/health');
    return {
      status: response.ok ? 'OK' : 'DEGRADED',
      latency: response.headers.get('x-response-time')
    };
  } catch (error) {
    return { status: 'DOWN', error: error.message };
  }
}
```

**Comprehensive Monitoring Workflow:**

```yaml
name: Production Monitoring

on:
  schedule:
    - cron: '*/15 * * * *'  # Every 15 minutes
  workflow_dispatch:

jobs:
  health-checks:
    runs-on: ubuntu-latest
    steps:
      - name: Check production health
        id: health
        run: |
          RESPONSE=$(curl -s -w "\n%{http_code}" ${{ secrets.PROD_ENDPOINT }}/health/detailed)
          STATUS_CODE=$(echo "$RESPONSE" | tail -n1)
          BODY=$(echo "$RESPONSE" | head -n-1)

          echo "status_code=$STATUS_CODE" >> $GITHUB_OUTPUT
          echo "response=$BODY" >> $GITHUB_OUTPUT

          if [ "$STATUS_CODE" != "200" ]; then
            echo "Health check failed: $STATUS_CODE"
            echo "$BODY"
            exit 1
          fi

      - name: Alert on health check failure
        if: failure()
        run: |
          curl -X POST ${{ secrets.SLACK_WEBHOOK }} \
            -H 'Content-Type: application/json' \
            -d '{
              "text": "🚨 Production Health Check FAILED",
              "blocks": [{
                "type": "section",
                "text": {
                  "type": "mrkdwn",
                  "text": "*Health Check Failed*\nStatus: ${{ steps.health.outputs.status_code }}\nEndpoint: ${{ secrets.PROD_ENDPOINT }}\n\nResponse:\n```${{ steps.health.outputs.response }}```"
                }
              }, {
                "type": "actions",
                "elements": [{
                  "type": "button",
                  "text": {"type": "plain_text", "text": "View Logs"},
                  "url": "${{ secrets.LOGS_URL }}"
                }]
              }]
            }'

  metrics-checks:
    runs-on: ubuntu-latest
    steps:
      - name: Fetch and check metrics
        run: |
          METRICS=$(curl -s ${{ secrets.PROD_ENDPOINT }}/metrics)

          ERROR_RATE=$(echo "$METRICS" | jq -r '.error_rate')
          LATENCY_P95=$(echo "$METRICS" | jq -r '.latency_p95')
          SUCCESS_RATE=$(echo "$METRICS" | jq -r '.success_rate')

          echo "Error Rate: $ERROR_RATE"
          echo "Latency P95: $LATENCY_P95ms"
          echo "Success Rate: $SUCCESS_RATE"

          # Check thresholds
          ALERT=""
          if (( $(echo "$ERROR_RATE > 0.05" | bc -l) )); then
            ALERT="⚠️ Error rate elevated: $ERROR_RATE (threshold: 5%)\n"
          fi

          if (( $(echo "$LATENCY_P95 > 2000" | bc -l) )); then
            ALERT="${ALERT}⚠️ Latency high: ${LATENCY_P95}ms (threshold: 2000ms)\n"
          fi

          if (( $(echo "$SUCCESS_RATE < 0.95" | bc -l) )); then
            ALERT="${ALERT}⚠️ Success rate low: ${SUCCESS_RATE} (threshold: 95%)\n"
          fi

          if [ -n "$ALERT" ]; then
            echo "Metrics degraded:"
            echo -e "$ALERT"

            curl -X POST ${{ secrets.SLACK_WEBHOOK }} \
              -H 'Content-Type: application/json' \
              -d "{\"text\": \"⚠️ Metrics Alert\n$ALERT\"}"
          fi

  token-usage-tracking:
    runs-on: ubuntu-latest
    steps:
      - name: Check token usage
        run: |
          METRICS=$(curl -s ${{ secrets.PROD_ENDPOINT }}/metrics)
          TOKEN_USAGE=$(echo "$METRICS" | jq -r '.token_usage.percentage')

          echo "Token Usage: $TOKEN_USAGE%"

          if (( $(echo "$TOKEN_USAGE > 90" | bc -l) )); then
            curl -X POST ${{ secrets.SLACK_WEBHOOK }} \
              -H 'Content-Type: application/json' \
              -d "{
                \"text\": \"⚠️ Token usage at ${TOKEN_USAGE}% - approaching limit\"
              }"
          fi
```

**Slack Alert Templates:**

```json
{
  "text": "Alert Summary",
  "blocks": [
    {
      "type": "header",
      "text": {
        "type": "plain_text",
        "text": "🚨 Production Alert"
      }
    },
    {
      "type": "section",
      "fields": [
        {
          "type": "mrkdwn",
          "text": "*Type:*\nHealth Check Failure"
        },
        {
          "type": "mrkdwn",
          "text": "*Severity:*\nCritical"
        },
        {
          "type": "mrkdwn",
          "text": "*Environment:*\nProduction"
        },
        {
          "type": "mrkdwn",
          "text": "*Time:*\n2026-01-03 10:30 UTC"
        }
      ]
    },
    {
      "type": "section",
      "text": {
        "type": "mrkdwn",
        "text": "*Details:*\nHealth check endpoint returned 503. AI API check failed with timeout."
      }
    },
    {
      "type": "actions",
      "elements": [
        {
          "type": "button",
          "text": {
            "type": "plain_text",
            "text": "View Logs"
          },
          "url": "https://logs.example.com",
          "style": "danger"
        },
        {
          "type": "button",
          "text": {
            "type": "plain_text",
            "text": "Runbook"
          },
          "url": "https://wiki.example.com/runbooks/health-check-failure"
        }
      ]
    }
  ]
}
```

### Appendix G: Complete CI/CD Pipeline Template

**Multi-Stage Pipeline Workflow:**

```yaml
name: Complete CI/CD Pipeline

on:
  push:
    branches: [develop, main]
  pull_request:
    branches: [main]

jobs:
  # Stage 1: Validation
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Install dependencies
        run: npm ci

      - name: Validate prompts
        run: npm run validate:prompts

      - name: Security scan
        run: npm audit --audit-level=moderate

  # Stage 2: Testing
  unit-tests:
    needs: validate
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Install dependencies
        run: npm ci

      - name: Run unit tests
        run: npm run test:unit

      - name: Upload coverage
        uses: actions/upload-artifact@v4
        with:
          name: unit-coverage
          path: coverage/

  integration-tests:
    needs: validate
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Install dependencies
        run: npm ci

      - name: Run integration tests
        run: npm run test:integration

  # Stage 3: Quality Gate
  quality-gate:
    needs: [unit-tests, integration-tests]
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Download coverage
        uses: actions/download-artifact@v4
        with:
          name: unit-coverage
          path: coverage/

      - name: Check coverage threshold
        run: |
          COVERAGE=$(cat coverage/coverage-summary.json | jq '.total.lines.pct')
          if (( $(echo "$COVERAGE < 80" | bc -l) )); then
            echo "Coverage $COVERAGE% below 80% threshold"
            exit 1
          fi
          echo "Coverage: $COVERAGE% ✅"

  # Stage 4: Deploy to Staging
  deploy-staging:
    needs: quality-gate
    if: github.ref == 'refs/heads/develop' || github.ref == 'refs/heads/main'
    runs-on: ubuntu-latest
    environment: staging
    steps:
      - uses: actions/checkout@v4

      - name: Deploy to staging
        env:
          API_KEY: ${{ secrets.AI_API_KEY }}
          ENVIRONMENT: staging
        run: ./scripts/deploy.sh

      - name: Staging smoke tests
        run: ./scripts/smoke-test.sh --endpoint ${{ secrets.STAGING_ENDPOINT }}

  # Stage 5: Deploy to Production (manual approval)
  deploy-production:
    needs: deploy-staging
    if: github.ref == 'refs/heads/main'
    runs-on: ubuntu-latest
    environment: production  # Requires manual approval
    steps:
      - uses: actions/checkout@v4

      - name: Blue-Green deployment
        env:
          API_KEY: ${{ secrets.AI_API_KEY }}
          ENVIRONMENT: production
        run: ./scripts/deploy-blue-green.sh

      - name: Production smoke tests
        run: ./scripts/smoke-test.sh --endpoint ${{ secrets.PROD_ENDPOINT }}

      - name: Monitor for 10 minutes
        run: ./scripts/monitor-metrics.sh --duration 600

      - name: Deployment success notification
        if: success()
        run: |
          curl -X POST ${{ secrets.SLACK_WEBHOOK }} \
            -d '{"text":"✅ Production deployment successful: ${{ github.sha }}"}'

      - name: Deployment failure notification
        if: failure()
        run: |
          curl -X POST ${{ secrets.SLACK_WEBHOOK }} \
            -d '{"text":"❌ Production deployment failed: ${{ github.sha }}"}'
```

### Appendix H: Incident Response Runbook

**Health Check Failure Response:**

**1. Triage (0-5 minutes)**
- [ ] Acknowledge alert
- [ ] Check incident channel for similar reports
- [ ] Verify issue with manual health check: `curl https://api.example.com/health/detailed`
- [ ] Determine severity: Critical (all users affected) vs Warning (degraded)

**2. Investigation (5-15 minutes)**
- [ ] Check recent deployments: Any changes in last 2 hours?
- [ ] Review application logs: `https://logs.example.com`
- [ ] Check AI provider status: OpenAI, Anthropic status pages
- [ ] Monitor metrics: Error rate, latency, success rate
- [ ] Check dependencies: Database, cache, external APIs

**3. Mitigation (15-30 minutes)**

**If recent deployment:**
```bash
# Option 1: Blue-Green rollback (instant)
./scripts/switch-traffic.sh --to blue

# Option 2: Rollback via GitHub
gh workflow run deploy-production.yml -f action=rollback -f version=<previous-sha>
```

**If external dependency:**
- Enable fallback mode if available
- Implement rate limiting to protect system
- Communicate outage to users

**If unknown cause:**
- Restart affected services
- Scale up resources if capacity issue
- Enable debug logging for investigation

**4. Communication**
- [ ] Update status page
- [ ] Post in incident channel
- [ ] Notify stakeholders if SLA breach
- [ ] Create incident ticket

**5. Recovery Verification (30-45 minutes)**
- [ ] Health checks passing
- [ ] Metrics returned to normal
- [ ] Sample user requests succeeding
- [ ] No error spike in logs

**6. Post-Incident (24 hours)**
- [ ] Write postmortem
- [ ] Identify root cause
- [ ] Document action items
- [ ] Update runbook based on learnings

**Rollback Procedures:**

**Blue-Green Rollback:**
```bash
# scripts/rollback-blue-green.sh
#!/bin/bash

CURRENT_SLOT=$(curl -s https://api.example.com/active-slot)
if [ "$CURRENT_SLOT" = "blue" ]; then
  TARGET_SLOT="green"
else
  TARGET_SLOT="blue"
fi

echo "Rolling back from $CURRENT_SLOT to $TARGET_SLOT..."

./scripts/switch-traffic.sh --from $CURRENT_SLOT --to $TARGET_SLOT

echo "Verifying rollback..."
sleep 10

HEALTH=$(curl -s -o /dev/null -w "%{http_code}" https://api.example.com/health)
if [ "$HEALTH" = "200" ]; then
  echo "✅ Rollback successful"

  # Notify team
  curl -X POST $SLACK_WEBHOOK \
    -d '{"text":"✅ Rollback completed successfully to '$TARGET_SLOT'"}'
else
  echo "❌ Rollback failed - health check returned $HEALTH"
  exit 1
fi
```

**Canary Rollback:**
```bash
# scripts/rollback-canary.sh
#!/bin/bash

echo "Rolling back canary deployment..."

# Set traffic to 100% previous version
./scripts/deploy-canary.sh --version previous --percentage 100

# Verify
sleep 10

ERROR_RATE=$(curl -s https://api.example.com/metrics | jq -r '.error_rate')
if (( $(echo "$ERROR_RATE < 0.05" | bc -l) )); then
  echo "✅ Canary rollback successful"
else
  echo "⚠️ Error rate still elevated: $ERROR_RATE"
fi
```

### Appendix I: Performance Benchmarks & SLOs

**Service Level Objectives (SLOs):**

**Availability SLO: 99.9% ("three nines")**
- Allows: 43.2 minutes downtime per month
- Measurement: Health check endpoint availability
- Target: No single incident > 30 minutes

**Latency SLO: P95 < 2000ms**
- 95% of requests complete in < 2 seconds
- Measurement: Response time from request to completion
- Target: Sustained, not just burst performance

**Error Rate SLO: < 1%**
- Less than 1% of requests return errors
- Measurement: HTTP 5xx responses / total requests
- Excludes: Client errors (4xx), rate limiting

**Success Rate SLO: > 99%**
- More than 99% of AI workflows complete successfully
- Measurement: Successful completions / total workflows
- Target: Across all prompt types

**SLO Tracking Dashboard:**

```javascript
// scripts/calculate-slo.js
const axios = require('axios');

async function calculateSLOs(startDate, endDate) {
  const metrics = await fetchMetrics(startDate, endDate);

  // Availability SLO
  const totalMinutes = (endDate - startDate) / 60000;
  const downtimeMinutes = metrics.downtime_events.reduce(
    (sum, event) => sum + event.duration_minutes,
    0
  );
  const availabilityPct = ((totalMinutes - downtimeMinutes) / totalMinutes) * 100;

  // Latency SLO
  const latencyP95 = calculatePercentile(metrics.latencies, 95);

  // Error Rate SLO
  const errorRate = (metrics.error_count / metrics.total_requests) * 100;

  // Success Rate SLO
  const successRate = (metrics.successful_workflows / metrics.total_workflows) * 100;

  return {
    availability: {
      value: availabilityPct,
      target: 99.9,
      status: availabilityPct >= 99.9 ? 'PASS' : 'FAIL',
      downtime_minutes: downtimeMinutes,
      budget_remaining: (totalMinutes * 0.001) - downtimeMinutes
    },
    latency: {
      value: latencyP95,
      target: 2000,
      status: latencyP95 <= 2000 ? 'PASS' : 'FAIL'
    },
    error_rate: {
      value: errorRate,
      target: 1.0,
      status: errorRate <= 1.0 ? 'PASS' : 'FAIL'
    },
    success_rate: {
      value: successRate,
      target: 99.0,
      status: successRate >= 99.0 ? 'PASS' : 'FAIL'
    }
  };
}
```

**Error Budget Policy:**

```markdown
# Error Budget Policy

## Monthly Error Budget: 43.2 minutes (99.9% SLO)

### Budget Consumption Rules:
- Critical incidents: Consume actual downtime
- Degraded performance (P95 > 2s for 15+ min): Count as 50% downtime
- Planned maintenance: Does NOT consume budget

### Budget Status Actions:

**100-75% Budget Remaining (Green):**
- Normal deployment cadence (daily if needed)
- Standard change review process
- Experimentation permitted

**75-25% Budget Remaining (Yellow):**
- Reduce deployment frequency (2-3x per week)
- Enhanced change review required
- Focus on reliability improvements
- Pause non-critical features

**< 25% Budget Remaining (Red):**
- Deployment freeze except critical fixes
- All changes require VP approval
- Dedicate sprint to reliability work
- Postmortem all recent incidents

**Budget Exhausted:**
- Complete deployment freeze
- Emergency reliability sprint
- Executive review of all processes
- May impact team performance reviews
```

**Performance Optimization Targets:**

| Metric | Current | Target | Stretch |
|--------|---------|--------|---------|
| Health Check Response | 150ms | < 100ms | < 50ms |
| Prompt Validation | 500ms | < 200ms | < 100ms |
| Deployment Time | 8 min | < 5 min | < 3 min |
| Test Suite Runtime | 4 min | < 3 min | < 2 min |
| CI/CD Pipeline Total | 12 min | < 8 min | < 5 min |

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | AI Practitioner Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |
