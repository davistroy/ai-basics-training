# **INSTRUCTOR GUIDE: ADVANCED MODULE 5 SESSION 2**
## **Advanced DevOps Patterns**

**Module:** Advanced Module 5: Advanced GitHub & DevOps for AI Systems
**Session:** 2 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

-----

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Production deployment strategies, secrets management, monitoring, complete CI/CD pipeline |
| **Difficulty Level** | Medium-High |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Yes - Blue-green deployment or environment setup |
| **Tech Setup Needed** | GitHub repository with environments configured, webhook for alerts (Slack/Discord) |
| **Common Challenges** | Understanding deployment strategies, configuring GitHub Environments, setting up webhooks |

-----

## Navigation

**Module Navigation:** [← Session 1 Instructor Guide](../session-1/instructor-guide.md) | **Session 2**

**Related Materials:**
- [Session 2 Presentation Slides](presentation.md)
- [Session 2 Participant Guide](participant-guide.md)
- [Module 5 Main Document](../module-5-github-devops.md)

-----

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Session 2 materials | ☐ |
| Test demo | Set up GitHub Environments and test deployment | ☐ |
| Check resources | Verify webhook URLs for alerting demos | ☐ |
| Prepare backup | Screenshots of environment setup, deployment workflow | ☐ |
| Review Session 1 | Check participant completion of Session 1 exercises | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice deployment strategy explanations | ☐ |
| Prepare materials | Have repository with staging/production environments ready | ☐ |
| Configure webhook | Test Slack/Discord webhook for alert demo | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, GitHub repo, Environments page, Secrets page | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Check completion of Session 1 exercises | ☐ |
| Start recording | If session is recorded | ☐ |

-----

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Session 1 recap, production focus | Emphasize progression |
| 0:03 | 12 min | Segment 1 | Deployment Strategies | Blue-green and canary patterns |
| 0:15 | 12 min | Segment 2 | Secrets & Configuration Management | Demo environment setup |
| 0:27 | 12 min | Segment 3 | Monitoring & Observability | Show health check workflow |
| 0:39 | 3 min | Segment 4 | Complete CI/CD Pipeline | Fast-paced assembly overview |
| 0:42 | 3 min | Closing | Capstone exercise, module completion | Celebrate achievement |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Segment 4 can be condensed to 6 minutes (reference pipeline diagram, skip detailed explanation)
- Reduce examples in deployment strategies (focus on one: blue-green)
- Skip secrets demo - reference screenshots instead

**If Running Ahead:**
- Show actual GitHub Environment protection rules setup
- Demonstrate creating a Slack/Discord webhook
- Live deployment workflow run
- Extended Q&A on production deployment concerns

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | Reduce canary deployment details, focus on blue-green |
| End Segment 2 | 0:27 | Skip secrets creation demo, show pre-configured |
| Start Closing | 0:42 | Must start by here regardless - capstone is critical |

-----

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants warmly
2. Acknowledge Session 1 completion
3. Frame Session 2 as "going production"
4. Set expectation for capstone exercise

**Opening Script:**
> "Welcome to Session 2 - our final session of Advanced Module 5. Last week you built the foundation: GitHub Actions, version control, testing. Today we're going production-ready. Deployment strategies for zero-downtime deployments. Secrets management for security. Monitoring for reliability. And you'll assemble everything into a complete CI/CD pipeline in the capstone exercise."

**Engagement Opportunity:**
> "Quick check: Who has their Session 1 workflows running successfully?"

[Wait for hands - gauge readiness]

-----

### Segment 1: Deployment Strategies (12 minutes)

**Learning Objective:** Design and implement deployment strategies for AI systems

**Slides:** 4-8

#### Content Delivery

**Key Point 1: The Deployment Challenge**
- Main message: Traditional all-or-nothing deployment is too risky for production AI systems
- Example to use: "10,000 customers see errors if deployment breaks"
- Common misconception: "We'll just deploy during off-hours" (AI systems often serve global users - no off-hours)

**Key Point 2: Blue-Green Deployment**
- Main message: Two environments (blue/green), deploy to inactive, switch traffic after validation
- Demonstration: Show workflow that deploys to green slot, runs smoke tests, switches
- Participant relevance: Instant rollback if anything goes wrong

**Key Point 3: Canary Deployment**
- Main message: Gradual rollout (10% → 25% → 50% → 100%) with metric monitoring
- Practice preview: Exercise 2.1 implements one of these strategies

#### Demo Instructions (if time permits)

**Demo Duration:** 5 minutes (optional - can skip if running behind)

**Setup Required:**
- GitHub repository with two deployment slots/environments
- Simple deployment script
- Smoke test script

**Demo Steps:**
1. **Show current production** (blue slot serving traffic)
2. **Deploy to green slot** (new version)
3. **Run smoke test on green** (verify it works)
4. **Switch traffic to green** (now production)
5. **Show instant rollback capability** (switch back to blue)

**Demo Talking Points:**
> "Notice we deployed without any downtime. Blue continued serving traffic while green was being prepared. Only after validation did we switch."

**Backup Plan:**
If demo fails or time is short:
1. Use diagram from slides to explain the flow
2. Show deployment workflow YAML conceptually
3. Reference exercise instructions for implementation details

#### Facilitation Notes

**Watch For:**
- Confusion about "slots" vs "environments" (clarify terminology)
- Questions about infrastructure costs (two environments = more resources)
- Uncertainty about which strategy to choose

**If Asked About "Which strategy should I use?":**
> "Start with Blue-Green. It's simpler, proven, and gives you the instant rollback safety net. As you add metric tracking, you can evolve to Canary for even safer gradual rollouts."

**Transition to Segment 2:**
> "Now you know how to deploy safely. But your workflows need API keys and secrets. How do you manage those securely?"

-----

### Segment 2: Secrets & Configuration Management (12 minutes)

**Learning Objective:** Configure secrets management and environment-specific configurations

**Slides:** 9-13

#### Content Delivery

**Key Point 1: Secrets Management Challenge**
- Main message: API keys can't be in code, must be securely stored and accessed by workflows
- Visual to emphasize: Crossed-out keys in code vs. GitHub Secrets

**Key Point 2: GitHub Secrets Hierarchy**
- Main message: Repository secrets for shared values, environment secrets for production
- Hands-on reference: Exercise 2.3 configures staging and production environments

**Key Point 3: Configuration as Code**
- Main message: Non-secret configuration should be versioned, secrets referenced
- Real-world application: Model settings in code, API keys in GitHub Secrets

#### Interactive Element

**Activity Type:** Show GitHub Secrets UI

**Activity Duration:** 3 minutes

**Instructions:**
1. Navigate to repository Settings → Secrets and variables → Actions
2. Show repository secrets (if any exist)
3. Navigate to Environments
4. Show staging and production with environment-specific secrets
5. Point out protection rules

**Debrief Points:**
> "See how production environment has protection rules? Required reviewers, branch restrictions. This adds safety gates beyond just secret management."

#### Facilitation Notes

**Energy Check:**
At this point in the session, participants may be:
- Conceptually loaded - lots of new GitHub features
- Ground with concrete examples: "Your OpenAI API key goes here"

**Common Confusion Point:**
"When do I use repository secrets vs. environment secrets?"

**Clarification Approach:**
> "If all environments can use the same value - repository secret. If staging needs different value than production - environment secrets. Production API keys should ALWAYS be environment secrets for extra protection."

**Transition to Segment 3:**
> "Secrets keep your credentials safe. But how do you know when your system breaks? Monitoring."

-----

### Segment 3: Monitoring & Observability (12 minutes)

**Learning Objective:** Build monitoring and alerting workflows

**Slides:** 14-18

#### Content Delivery

**Key Point 1: Monitoring Challenge**
- Main message: AI systems fail silently; proactive monitoring beats reactive support tickets
- Framework/Pattern: Health checks + metrics + alerts

**Key Point 2: Health Check Workflows**
- Main message: Schedule-triggered workflows check system health every 15 minutes
- Example walkthrough: Cron schedule → health check → alert on failure

**Key Point 3: Alerting Patterns**
- Main message: Critical/Warning/Info severity levels, alert where team looks
- Example: Error rate > 5% for 5 min → Critical Slack alert

#### Practical Application

**Consulting Connection:**
> "In consulting, downtime is lost revenue. If your client's AI chatbot goes down for 2 hours before you notice, that's customers lost. Automated monitoring detects issues in minutes, not hours."

**Example Scenario:**
> "Your AI system starts timing out. Health checks fail. Within 15 minutes, Slack alert pings the on-call engineer. They investigate logs, find rate limit hit, scale up. Total downtime: 20 minutes instead of 2 hours. That's the value of monitoring."

#### Facilitation Notes

**Watch For:**
- Questions about alert fatigue (too many alerts)
- Confusion about webhook setup
- Uncertainty about what metrics to track

**If Asked About "How do I avoid too many alerts?":**
> "Start with critical alerts only - health check failures, error rate spikes. Add warnings as you learn what matters. Better to start conservative than drown in noise."

**Transition to Segment 4:**
> "You have deployment strategies, secrets management, monitoring. Now let's bring it all together into a complete pipeline."

-----

### Segment 4: Complete CI/CD Pipeline (3 minutes)

**Learning Objective:** Assemble complete CI/CD pipeline

**Slides:** 19-22

**NOTE:** This segment is condensed to 3 minutes to fit timing and save energy for capstone exercise explanation.

#### Content Delivery

**Key Message:** All the pieces you've built over two sessions come together into an automated, end-to-end pipeline.

**Coverage:**
- Show complete pipeline diagram (Slide 19)
- Explain job dependencies (needs:)
- Highlight human approval gate for production
- Point to capstone exercise

**Visual:** Walk through pipeline diagram pointing to each stage

#### Closing This Segment

**Key Takeaway:**
> "This is production-grade DevOps. Validation, testing, deployment, monitoring - all automated. The only human touchpoint is approving production deployments. Everything else runs automatically."

**Connection to Capstone:**
> "Exercise 2.3 - the capstone - has you assemble this complete pipeline. All the workflows, environment configs, protection rules. When you're done, you have a production-ready system."

-----

### Closing (3 minutes)

**Slides:** 23-25

**Do Not Skip This Section** - module completion and capstone are critical

#### Homework Preview

**Key Actions:**
1. Overview three exercises with time estimates
2. Emphasize Exercise 2.3 is the capstone - brings everything together
3. Point out this completes the module
4. Reference participant guide for detailed instructions

**Script:**
> "Three exercises, 75 minutes total.
>
> Exercise 2.1 - implement a deployment strategy. Blue-green or canary, your choice. 30 minutes.
> Exercise 2.2 - configure monitoring and alerting. Health checks, webhooks. 25 minutes.
> Exercise 2.3 - the capstone. Assemble your complete CI/CD pipeline. All workflows, all environments. 20 minutes.
>
> When you complete Exercise 2.3, you'll have a production-ready DevOps system. Everything you need to deploy AI workflows safely and monitor them reliably."

#### Resources and Support

> "Module appendices have reference materials, troubleshooting, security checklists. Use them. If you get stuck, check the troubleshooting guide first, then ask in the support channel."

#### Module Completion Celebration

> "Completing Exercise 2.3 completes Advanced Module 5. You've built production-grade DevOps capabilities for AI systems. That's a significant achievement. Take a moment to appreciate how far you've come from Session 1."

#### Session Close

> "Final questions? ... Excellent work everyone. You now have the skills to deploy AI systems with confidence. Production-grade automation, testing, deployment, monitoring. Go build amazing things. Congratulations on completing Advanced Module 5!"

-----

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Blue-green vs. canary - which is better?**
A: Neither is universally better. Blue-green is simpler and gives instant rollback. Canary provides gradual validation with real traffic. Start with blue-green, evolve to canary as your monitoring matures.

**Q: How much does GitHub Actions cost for all this?**
A: GitHub provides 2,000 free minutes/month for private repos. For most AI projects, that's sufficient. Public repos get unlimited minutes. If you exceed limits, optimize workflows or consider self-hosted runners.

**Q: What if we don't use GitHub?**
A: These patterns apply to any CI/CD platform. GitLab CI, Jenkins, CircleCI - they all support similar workflows. The principles are universal, even if the syntax differs.

### Technical Questions

**Q: How do we set up a webhook for Slack/Discord?**
A: Slack: Create an incoming webhook in your workspace settings. Discord: Server settings → Integrations → Webhooks. Both give you a URL to POST messages to. Participant guide has links to official docs.

**Q: Can we deploy to AWS/Azure/GCP?**
A: Absolutely. Your deployment workflow can use cloud CLI tools or SDKs. For AWS, use aws-actions/configure-aws-credentials action with OIDC for secure authentication.

**Q: What about database migrations in deployments?**
A: Add a migration step before traffic switch in blue-green. For canary, migrations are trickier - you need backward-compatible schemas. Consider this an advanced topic beyond this module's scope.

### Scope Questions

**Q: What about rollback testing? How do we verify rollback works?**
A: Great question - test rollbacks in staging regularly. Include rollback drills in your process. This is an operational maturity topic. Start by documenting rollback procedures.

**Q: How do we handle secrets rotation?**
A: Update the secret in GitHub Secrets, redeploy workflows that use it. For zero-downtime rotation, some systems support dual secrets (old and new both valid during transition).

### Pushback/Objections

**Q: This seems over-engineered for our small project.**
A: Start simple. Even a small project benefits from automated validation and testing. Add deployment strategies when you go to production. Add monitoring when you have users. Build incrementally.

**Q: Our team isn't ready for this level of automation.**
A: That's okay. Start with what adds immediate value - automated testing catches bugs. Add deployment automation when manual deployments become painful. Incremental adoption works.

-----

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Environment demo fails | Check environment exists, protection rules correct | Show screenshots of pre-configured environment |
| Webhook alert fails | Verify webhook URL, check payload format | Show successful alert from previous test |
| Deployment workflow errors | Check YAML syntax, secrets configured | Walk through conceptually using slides |
| Screen share issues | Restart share, switch to application window | Describe what you'd show, use slides |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Unclear on deployment strategies | "Which should I use?" | Recommend blue-green to start, explain tradeoffs |
| Overwhelmed by pipeline complexity | Silence, confusion | Emphasize incremental build - each piece adds value |
| Webhook setup confusion | "How do I get the webhook URL?" | Provide direct links to Slack/Discord webhook docs |
| Environment protection unclear | Questions about required reviewers | Show GitHub UI, demonstrate adding protection rules |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Too much information | Glazed looks | Slow down, use more concrete examples |
| Want more technical depth | Questions about advanced scenarios | Acknowledge, provide resources for deeper learning |
| Conceptual vs. implementation gap | "I understand but don't know how to build it" | Emphasize exercises provide step-by-step implementation |

-----

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save chat questions | For follow-up |
| Note what worked/struggled | Timing, examples, demos |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording | ☐ |
| Answer pending questions in support channel | ☐ |
| Share example webhook setup instructions | ☐ |
| Document any issues for curriculum improvement | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review capstone submissions (spot check) | ☐ |
| Identify participants needing pipeline support | ☐ |
| Gather feedback on module overall | ☐ |
| Update instructor guide with lessons learned | ☐ |

-----

## Participant Progress Tracking

### Expected Deliverables This Session

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 2.1 | `deploy-production.yml` + design doc | `.github/workflows/` + docs folder |
| 2.2 | `monitoring.yml` + webhook config | `.github/workflows/` |
| 2.3 (Capstone) | Complete `.github/workflows/` directory with all pipelines | Repository root |

### Progress Check Approach

**How to Verify Completion:**
- Check repository for complete `.github/workflows/` directory
- Verify staging and production environments exist
- Look for secrets configured (at least environment-level AI_API_KEY)
- Check Actions tab for workflow runs

**Red Flags:**
- No environments configured (capstone incomplete)
- Workflows exist but fail due to missing secrets
- No monitoring workflow (incomplete Exercise 2.2)

**Intervention Thresholds:**
- Capstone incomplete: Priority support - this validates module completion
- Workflows not running: Check secrets configuration
- No progress after 48 hours: Individual outreach

-----

## Session-Specific Notes

### What Makes This Session Unique

**Module Capstone:**
- Session 2 culminates in capstone exercise that integrates all learning
- Success here validates entire module completion
- More complex than typical exercises - expect some struggles

**Production Focus:**
- This session is about production-readiness, not just learning concepts
- Emphasize real-world implications (downtime, security, monitoring)
- Participants should leave confident to deploy to production

**Key Challenges:**
- Overwhelming number of components (environments, secrets, workflows, protection rules)
- Conceptual understanding of deployment strategies
- Webhook setup for monitoring (external to GitHub)

**Success Indicators:**
- Participants understand blue-green or canary deployment
- Comfortable with GitHub Environments and Secrets
- Excited about complete pipeline they're building

### Dependencies

**Builds On:**
- Session 1: Validation workflows, testing, version control (foundation)
- Block 3: Autonomous agents to deploy
- Git/GitHub fundamentals

**Sets Up:**
- Production deployments of Block 3 projects
- Real-world AI system operations
- Other advanced modules that assume DevOps capability

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| GitHub Environments require pro/org account | Free accounts can still use repository secrets, skip environment protection | Active |
| Webhook setup varies by platform | Provide links to official docs for Slack, Discord, etc. | Active |
| Deployment complexity varies by target | Focus on principles, let participants adapt to their infrastructure | Active |

-----

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- Ask: "What's the key benefit of blue-green deployment?" (Expected: Instant rollback)
- Observable understanding: Questions about adapting strategies to their use cases
- Observable confusion: Silence when asked about environment protection

### Summative Assessment (End of Session)

**Exercise Quality Indicators:**
- Exercise 2.1: Deployment workflow exists, strategy clearly documented, rollback procedure defined
- Exercise 2.2: Monitoring workflow runs on schedule, alerts configured, health checks functional
- Exercise 2.3 (Capstone): Complete pipeline with all workflows, environments configured, protection rules set

**Common Issues to Flag:**
- Deployment workflow exists but missing critical steps (smoke tests, rollback)
- Monitoring workflow doesn't actually send alerts (webhook misconfigured)
- Capstone missing components (no environment protection, incomplete pipeline)

### Connecting to Module Capstone

**Module Capstone IS Exercise 2.3:**
The capstone exercise assembles everything from both sessions into a production-ready pipeline.

**Capstone Success Criteria:**
- All five workflow files present and functional
- Staging and production environments configured
- Secrets properly scoped
- Environment protection rules on production
- Monitoring running on schedule

-----

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Monitor support channel for repeated questions (indicates unclear content)
- Track capstone completion rate
- Note which deployment strategy participants choose (informs future recommendations)

**Improvement Log:**

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| | | | |

-----

## Quick Reference Cards

### Key Messages to Emphasize

1. "Deploy with confidence: Blue-green and canary strategies give you safety nets."
2. "Never commit secrets. GitHub Secrets keeps credentials secure."
3. "Automated monitoring detects problems before users do."

### If You Only Have Time For One Thing

**Core Concept:** A complete CI/CD pipeline automates validation, testing, and deployment while adding human approval gates for production. This enables safe, frequent deployments with fast rollback.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Blue-Green Deployment | Two stages with spotlight | When explaining traffic switching |
| Canary Deployment | Canary in coal mine | When explaining early warning with small user group |
| Monitoring | Smoke detector | When explaining proactive vs. reactive detection |

-----

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial instructor guide created | Claude |
