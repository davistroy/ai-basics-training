# **ADVANCED MODULE 6, SESSION 2: Production Deployment & Operations**

**Module:** Advanced Module 6: Enterprise AI Architecture
**Session:** 2 of 2
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Module Navigation:** [← Session 1](../session-1/participant-guide.md) | Session 2

**In This Guide:**
- [Learning Objectives](#learning-objectives)
- [Key Concepts](#key-concepts)
- [Workshop Recap](#workshop-recap)
- [Self-Paced Exercises](#self-paced-exercises)
- [Templates & Resources](#templates--resources)
- [Self-Assessment](#self-assessment)
- [Module Completion](#module-completion)

---

## Learning Objectives

By the end of this session, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Configure auto-scaling strategies for AI workloads based on multiple triggers | Exercise 2.1 |
| 2 | Design hybrid and on-premises architectures for regulated environments | Exercise 2.1 |
| 3 | Implement observability stacks with AI-specific metrics and monitoring | Exercise 2.2 |
| 4 | Create phased deployment strategies for enterprise rollouts | Exercise 2.1, 2.3 |
| 5 | Synthesize complete enterprise architecture proposals | Exercise 2.3 (Capstone) |

---

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Session 1, Exercise 1.1: Platform Comparison Analysis
- [ ] Session 1, Exercise 1.2: Security Architecture Design
- [ ] Session 1, Exercise 1.3: Cost Modeling
- [ ] Understanding of deployment architecture patterns (serverless, containerized, queue-based)

**Not ready?** Complete Session 1 exercises before proceeding - Session 2 builds directly on that work.

---

## Key Concepts

### Concept 1: Auto-Scaling for AI Workloads

**Definition:**
Automated adjustment of compute resources based on workload demand, configured specifically for AI system constraints like token limits and cost per request.

**Why It Matters:**
AI workloads don't scale like traditional web apps. Token limits, model latency, and per-request costs create unique constraints that traditional CPU/memory-based scaling doesn't address.

**Core Principle:**
> Use multiple scaling triggers (requests, tokens, queue depth) with proper delays and caps to handle AI-specific constraints while controlling costs.

**Five Scaling Strategies:**

| Strategy | Trigger | Best For | Limitation |
|----------|---------|----------|------------|
| Request-based | Requests/second | Synchronous APIs | May hit token limits before request limits |
| Queue-depth | Messages in queue | Async processing | Latency for queued items |
| CPU/Memory | Resource utilization | Container workloads | Lags behind actual demand |
| Custom metric | Token usage rate | All patterns | Requires custom metrics setup |
| Scheduled | Time of day | Predictable patterns | Doesn't handle unexpected spikes |

**Production Configuration Example:**
```json
{
  "auto_scaling": {
    "min_instances": 2,          // High availability
    "max_instances": 50,         // Cost protection
    "target_cpu_utilization": 70,
    "scale_up_threshold": {
      "requests_per_second": 100,
      "queue_depth": 1000,
      "token_usage_rate": 80     // % of platform limit
    },
    "scale_down_delay_seconds": 300,   // Prevent flapping
    "scale_up_cooldown_seconds": 60
  }
}
```

**Common Mistakes:**
- Scaling on CPU alone without considering token limits
- No max_instances cap, leading to runaway costs
- Scale-down delay too short, causing flapping (scale up, down, up, down)
- Single instance minimum (no high availability)

---

### Concept 2: Hybrid and On-Premises AI Architecture

**Definition:**
Deployment patterns that combine cloud and on-premises infrastructure, or run AI entirely on-premises, typically for data sovereignty, compliance, or cost optimization.

**Why It Matters:**
Many enterprises cannot use public cloud AI due to regulatory requirements, data sovereignty laws, or air-gapped environments. Understanding hybrid patterns is essential for these clients.

**When to Consider On-Premises:**

| Driver | Explanation | Example |
|--------|-------------|---------|
| **Data sovereignty** | Legal requirement to keep data in specific geographic location | EU GDPR restrictions |
| **Air-gapped** | No internet connectivity allowed | Defense, critical infrastructure |
| **Compliance** | Industry regulations prohibit cloud | Some financial, healthcare scenarios |
| **Cost at scale** | Very high volume makes self-hosting cheaper | >10M requests/day break-even point |
| **Latency** | Ultra-low latency requirements | Real-time manufacturing, trading |

**Two Common Hybrid Patterns:**

**Pattern A: Data On-Prem, AI in Cloud**
```
┌─────────────────┐     ┌─────────────────┐
│  On-Premises    │     │     Cloud       │
│  ┌───────────┐  │     │  ┌───────────┐  │
│  │   Data    │──┼─────┼─▶│   AI API  │  │
│  │  Sources  │  │     │  └───────────┘  │
│  └───────────┘  │     │                 │
│  ┌───────────┐  │     │                 │
│  │  Results  │◀─┼─────┼─────────────────│
│  │  Storage  │  │     │                 │
│  └───────────┘  │     │                 │
└─────────────────┘     └─────────────────┘
```
- Sensitive data stays on-premises
- Only necessary data sent to cloud for processing
- Results returned to on-premises storage

**Pattern B: Edge Processing with Cloud AI**
```
┌─────────────┐   ┌─────────────┐   ┌─────────────┐
│   Edge      │   │   Regional  │   │   Central   │
│ ┌─────────┐ │   │ ┌─────────┐ │   │ ┌─────────┐ │
│ │ Filter  │─┼──▶│ │ Process │─┼──▶│ │Cloud AI │ │
│ │ & Cache │ │   │ │ & Route │ │   │ │   API   │ │
│ └─────────┘ │   │ └─────────┘ │   │ └─────────┘ │
└─────────────┘   └─────────────┘   └─────────────┘
```
- Edge layer filters and caches common requests
- Regional layer processes and routes
- Only complex requests go to central cloud AI

**On-Premises Options:**

| Option | Models | Hardware | Best For |
|--------|--------|----------|----------|
| Self-hosted LLM | Llama, Mistral (open-source) | Your GPU servers | Maximum control, high expertise |
| Private cloud | Vendor models in dedicated region | Vendor-managed | Compliance with less ops burden |
| AI Appliance | Pre-configured | Vendor hardware | Simplicity, fast deployment |

---

### Concept 3: Observability for AI Systems

**Definition:**
The ability to understand internal system state from external outputs using metrics, logs, and traces. For AI systems, includes AI-specific metrics like token usage, cost per request, and quality scores.

**Why It Matters:**
Traditional application monitoring (CPU, memory, request rate) misses AI-specific issues like token limit throttling, model quality degradation, or unexpected cost spikes.

**Three Pillars of Observability:**

```
┌─────────────────────────────────────────┐
│      Dashboards & Alerts                │
│   (Grafana, Datadog, CloudWatch)        │
└──────────────┬──────────────────────────┘
               │
    ┌──────────┼──────────┐
    ▼          ▼          ▼
┌─────────┐ ┌─────────┐ ┌─────────┐
│ Metrics │ │  Logs   │ │ Traces  │
│(Counters│ │ (Events)│ │ (Flows) │
└─────────┘ └─────────┘ └─────────┘
```

**1. Metrics (Time-Series Numbers)**
- Response latency (P50, P95, P99)
- Error rate (%)
- Token usage rate (tokens/min)
- Cost per request ($)
- Quality scores (if measured)

**2. Logs (Discrete Events)**
- Request received with trace ID
- AI API call made with token count
- Response returned with latency
- Errors with stack traces
- Audit events for compliance

**3. Traces (Distributed Request Flow)**
- Request path through system
- API Gateway → Lambda → Bedrock → Response
- Identify bottlenecks and failures

**AI-Specific Metrics:**

| Metric | Description | Alert Threshold |
|--------|-------------|-----------------|
| **Token usage rate** | Tokens/minute vs platform limit | >80% of limit (WARNING), >95% (CRITICAL) |
| **Response latency** | Time from request to response | P95 > 10s |
| **Error rate** | % of requests failing | >5% |
| **Cost per request** | Average $ per request | >target cost |
| **Quality score** | Output quality if measured | <threshold (e.g., <0.7) |

**Logging Best Practices:**
- **Sanitize PII** - Never log raw user data
- **Include trace IDs** - Correlate logs across services
- **Log token counts** - Essential for cost analysis
- **Record model versions** - Track which model served request
- **Capture prompt templates** - For debugging and optimization

**Incident Response Workflow:**
```
1. Detect     → Automated alerts fire
2. Triage     → Classify as AI vs infrastructure issue
3. Contain    → Circuit breaker, fallback, or disable
4. Investigate → Logs, traces, recent changes
5. Resolve    → Fix root cause
6. Review     → Post-incident analysis, prevent recurrence
```

---

### Concept 4: Phased Enterprise Deployment

**Definition:**
Staged rollout strategy where system is deployed to progressively larger user groups (pilot → limited → general availability) with go/no-go decision points between phases.

**Why It Matters:**
Deploying enterprise AI to thousands of users simultaneously is high-risk. Issues that affect 10 pilot users are manageable. Same issues affecting 10,000 users is a crisis.

**Three-Phase Deployment:**

| Phase | Duration | Users | Goals | Success Criteria |
|-------|----------|-------|-------|------------------|
| **Pilot** | 4-6 weeks | 10-20 | Validate approach, gather feedback | Positive user feedback, core functionality working, no critical issues |
| **Limited Availability** | 8-12 weeks | 100-500 | Validate scale, refine operations | SLAs met, scaling works, support processes functional |
| **General Availability** | Ongoing | All users | Full production rollout | All users onboarded, optimizations applied, metrics green |

**Go/No-Go Decision Points:**
- After Pilot: Decide whether to proceed to Limited based on success criteria
- After Limited: Decide whether to proceed to General Availability
- Each phase has defined success criteria that must be met

**Four Migration Strategies:**

1. **Big Bang** - One-time cutover
   - Pros: Fast, simple
   - Cons: High risk, difficult rollback
   - Use when: Small user base, low criticality

2. **Parallel Run** - Both old and new systems active
   - Pros: Very safe, easy rollback
   - Cons: Expensive (running two systems), complex data sync
   - Use when: Mission-critical system, budget available

3. **Phased** - Gradual user migration
   - Pros: Balanced risk/speed, manageable rollback
   - Cons: Moderate complexity
   - Use when: Most enterprise scenarios (recommended default)

4. **Feature Flags** - Toggle features per user/group
   - Pros: Maximum flexibility, instant rollback
   - Cons: Requires feature flag infrastructure
   - Use when: Complex system with multiple new features

**Rollback Planning:**
- **Define triggers**: What conditions require rollback? (e.g., error rate >10%, cost >2x expected)
- **Document procedure**: Step-by-step rollback steps
- **Test in staging**: Practice rollback before production
- **Maintain previous version**: Keep old version deployable for 30 days post-launch

---

## Workshop Recap

### Session Summary

**Today's Focus:** Scaling patterns, hybrid/on-prem architectures, operations/observability, deployment strategies, and module capstone.

**Key Points from Each Segment:**

**Segment 1: Scaling Patterns for AI Workloads**
- AI workloads scale differently due to token limits and per-request costs
- Use multiple scaling triggers: requests/second AND token usage AND queue depth
- Min instances ≥ 2 for HA, max instances for cost protection
- Session affinity critical for multi-turn conversations
- Scale-down delay prevents flapping

**Segment 2: Hybrid and On-Premises Architectures**
- On-prem makes sense for compliance, data sovereignty, air-gapped, or cost at extreme scale
- Two common patterns: data on-prem with cloud AI, or edge processing
- On-prem options: self-hosted LLMs, private cloud, or appliances
- Break-even rough estimate: <1M requests/day → cloud, >10M → consider self-hosted

**Segment 3: Operations and Observability**
- Three pillars: metrics, logs, traces feeding into dashboards and alerts
- AI-specific metrics: token usage rate, cost per request, quality scores
- Log sanitized request/response, token counts, model versions, trace IDs
- Incident response: Detect, Triage, Contain, Investigate, Resolve, Review

**Segment 4: Enterprise Deployment Strategy**
- Three phases: Pilot (10 users, 4-6 weeks), Limited (100 users, 8-12 weeks), General (all users)
- Go/no-go decision points between phases based on success criteria
- Four migration strategies: big bang, parallel run, phased, feature flags
- Always have rollback plan: define triggers, document procedure, test in staging

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 2.1 | 25 min | `deployment-strategy.md` | Phased deployment plan |
| 2.2 | 25 min | `operations-runbook.md` | Operational procedures and monitoring |
| 2.3 | 25 min | `enterprise-architecture-proposal.md` | Complete capstone proposal |

---

### Exercise 2.1: Deployment Strategy Document

**Duration:** 25 minutes

**Purpose:**
Create a complete phased deployment plan for enterprise AI rollout. This practices the skill of de-risking large deployments through staged rollout.

**You Will Create:**
Deployment strategy document with phased approach, infrastructure pipeline, scaling configuration, risk mitigation, and timeline.

---

#### Instructions

**Step 1: Choose Deployment Approach**

Select migration strategy:
- **Phased** (recommended for most scenarios)
- **Big Bang** (if small user base, low risk)
- **Parallel Run** (if mission-critical, budget available)
- **Feature Flags** (if complex feature set)

Document rationale for your choice.

**Step 2: Define Deployment Phases**

For each phase (Pilot, Limited, General), define:

**Phase 1: Pilot**
- Scope: Which features, use cases
- Users: How many, selection criteria (e.g., "10 power users from IT department")
- Success criteria: 3-5 specific, measurable criteria (e.g., "Average user satisfaction >4/5", "Error rate <1%", "No data security incidents")
- Duration: Typically 4-6 weeks
- Go/No-Go decision point: When and what triggers proceeding or stopping

**Phase 2: Limited Availability**
- Scope: Expanded features
- Users: Target 100-500 users, which departments
- Success criteria: Including SLA targets, scaling validation
- Duration: 8-12 weeks
- Go/No-Go decision point

**Phase 3: General Availability**
- Scope: Full feature set
- Users: All target users
- Ongoing metrics to track

**Step 3: Design Infrastructure Deployment**

Define environments:
- Development: For feature development
- Staging: For integration testing
- Pre-prod: For performance/security testing
- Production: Live system

Document deployment pipeline:
```
Code Commit → Build → Unit Tests → Security Scan
     ↓
Deploy to Staging → Integration Tests → Performance Tests
     ↓
Manual Approval → Deploy to Pre-prod → Validation
     ↓
Change Request → Deploy to Production → Smoke Tests → Monitor
```

**Step 4: Configure Scaling**

Using Session 1 architecture choice and Exercise 1.3 usage projections:

Define auto-scaling rules in JSON format (see template):
- min_replicas
- max_replicas
- scaling metrics and thresholds
- scale-up and scale-down delays

Define capacity reservations for different time periods:
- Business hours
- Off-hours
- Peak events (if applicable)

**Step 5: Identify Risks and Mitigations**

List 4-6 major risks:
- API rate limits
- Model degradation
- Cost overrun
- Security incident
- Performance degradation
- User adoption challenges

For each risk:
- Likelihood (Low/Medium/High)
- Impact (Low/Medium/High/Critical)
- Mitigation strategy

**Step 6: Create Timeline**

Week-by-week timeline for first 12-16 weeks:
- Key milestones
- Deliverables
- Decision points

**Step 7: Document Rollback Procedure**

4-6 step rollback procedure:
1. Detect rollback condition
2. Stop new deployments
3. Revert to previous version
4. Verify rollback success
5. Communicate to stakeholders
6. Investigate root cause

**Step 8: Review Your Work**

Check that your deliverable includes:
- [ ] Deployment approach selected with rationale
- [ ] All three phases defined with success criteria
- [ ] Infrastructure deployment pipeline documented
- [ ] Auto-scaling configuration specified
- [ ] Risks identified with mitigations
- [ ] Timeline with milestones
- [ ] Rollback procedure documented

---

#### Deliverable Specification

**File Name:** `deployment-strategy.md`

**Location:** Your working directory for Module 6

**Quality Criteria:**
- [ ] Phased approach with clear go/no-go decision points
- [ ] Success criteria are specific and measurable
- [ ] Scaling configuration is realistic and complete
- [ ] Risk mitigations are specific and actionable
- [ ] Timeline is realistic with dependencies noted
- [ ] Rollback procedure is testable

---

### Exercise 2.2: Operations Runbook

**Duration:** 25 minutes

**Purpose:**
Document operational procedures for running AI system in production. This creates the "how to operate" guide for operations teams.

**You Will Create:**
Operations runbook with monitoring dashboards, key metrics, alert thresholds, common procedures, and incident response workflows.

---

#### Instructions

**Step 1: Document System Overview**

Brief architecture summary referencing Session 1 design:
- Platform (AWS Bedrock/Azure OpenAI/Vertex AI)
- Deployment pattern (serverless/containerized/queue-based)
- Key components and owners

List external dependencies:
- AI platform API (SLA, fallback)
- Other critical services

**Step 2: Define Monitoring**

Specify dashboard links (even if placeholder URLs):
- Production dashboard
- Staging dashboard
- Cost tracking dashboard

Define key metrics and thresholds:

| Metric | Warning Threshold | Critical Threshold | Dashboard Link |
|--------|------------------|-------------------|----------------|
| Response latency P95 | >5s | >10s | [URL] |
| Error rate | >2% | >5% | [URL] |
| Token usage | >70% of limit | >90% of limit | [URL] |
| Cost per hour | >$X | >$Y | [URL] |
| Queue depth (if applicable) | >1000 | >5000 | [URL] |

Define alert routing:
- Critical alerts → PagerDuty + Slack, 15 min response time
- Warning alerts → Slack, 1 hour response time
- Info → Email, next business day

**Step 3: Document Common Procedures**

Create 4-6 common operational procedures:

**Procedure 1: Scaling Up Manually**
- When: Anticipated high load event (product launch, marketing campaign)
- Steps: [Specific commands or actions]
- Verification: [How to confirm it worked]

**Procedure 2: Rotating API Keys**
- When: Scheduled rotation or suspected compromise
- Steps: Generate new key, update secrets manager, deploy, verify, deactivate old key
- Verification: Requests succeeding with new key

**Procedure 3: Updating Model Version**
- When: New model version available
- Steps: Test in staging, deploy to prod, monitor metrics, rollback if needed
- Verification: Model version logging shows new version

**Procedure 4: Emergency Disable**
- When: Critical security incident or runaway costs
- Steps: Disable feature flag, stop traffic, verify shutdown
- Verification: No new requests processing

(Add 2-3 more procedures specific to your architecture)

**Step 4: Define Incident Response**

Severity levels:
- SEV1: Complete outage (all requests failing)
- SEV2: Partial outage (>20% errors)
- SEV3: Degraded performance (high latency, some errors)
- SEV4: Minor issues (cosmetic, low impact)

Incident workflow:
```
Detection → Acknowledge → Assess Severity
     ↓
Communicate → Investigate → Resolve
     ↓
Post-Incident Review → Document → Close
```

Common issues with resolutions:

**Issue: High Error Rate**
- Symptoms: Error rate >5%, alerts firing
- Potential causes: AI API issues, rate limiting, bad deployment
- Resolution steps: Check provider status, check token usage, check recent deployments

**Issue: High Latency**
- Symptoms: P95 latency >10s
- Potential causes: Model congestion, database slow, network issues
- Resolution steps: Check AI provider status, check database performance, check connectivity

**Issue: Cost Spike**
- Symptoms: Hourly cost >2x normal
- Potential causes: Traffic spike, prompt bloat, infinite loop
- Resolution steps: Check request volume, check token counts, check for loops

**Step 5: Define Maintenance Windows**

| Activity | Frequency | Duration | Impact |
|----------|-----------|----------|--------|
| Security patches | Weekly | 30 min | None (rolling update) |
| Model updates | Monthly | 1 hour | Degraded performance |
| Infrastructure updates | Quarterly | 2 hours | Possible brief outage |

**Step 6: Document Escalation Path**

L1, L2, L3 escalation with contact methods
Vendor support contacts with SLAs

**Step 7: Review Your Work**

Check that your deliverable includes:
- [ ] System overview with components and dependencies
- [ ] Monitoring dashboards and metrics defined
- [ ] Alert thresholds and routing specified
- [ ] Common procedures documented step-by-step
- [ ] Incident response workflow and common issues
- [ ] Maintenance windows defined
- [ ] Escalation path documented

---

#### Deliverable Specification

**File Name:** `operations-runbook.md`

**Location:** Your working directory for Module 6

**Quality Criteria:**
- [ ] All key AI-specific metrics covered (tokens, cost, quality)
- [ ] Procedures are specific with actual commands/steps
- [ ] Incident response addresses AI-specific issues
- [ ] Alert thresholds are realistic and actionable
- [ ] Escalation path is clear

---

### Exercise 2.3: Module Capstone - Enterprise Architecture Proposal

**Duration:** 25 minutes

**Purpose:**
Synthesize all module work into a client-ready Enterprise AI Architecture Proposal. This is the primary deliverable for Module 6 certification.

**You Will Create:**
1. Complete written proposal (`enterprise-architecture-proposal.md`)
2. Executive presentation outline (10-15 slides)

---

#### Instructions

**This is Synthesis, Not New Work:**

You've already completed the hard work in Exercises 1.1-2.2. This exercise is about pulling those pieces together into a cohesive, client-ready proposal.

**Step 1: Define Client Scenario**

Use a real client (sanitized) or create realistic scenario:
- Client name and industry
- Business challenge and AI initiative goals
- Primary use cases (3-5)
- Success metrics
- Constraints (budget, timeline, compliance)

**Can reuse scenario from Exercise 1.1** - this provides continuity.

**Step 2: Write Executive Summary**

3-4 paragraphs covering:
- Business context and goals
- Recommended platform and architecture approach
- Key benefits and expected outcomes
- Investment summary (from Ex 1.3) and timeline (from Ex 2.1)

This is what executives read first - make it compelling.

**Step 3: Document Business Requirements**

From your scenario:
- Primary use cases with volumes and priorities
- Success criteria table (metric, current state, target, timeline)
- Constraints (budget, compliance, integration needs)

**Step 4: Present Platform Recommendation**

**Copy from Exercise 1.1:**
- Selected platform with rationale
- Comparison summary (weighted scoring results)
- Risks and mitigations

Polish and integrate into proposal narrative.

**Step 5: Describe Reference Architecture**

**Copy from Exercise 1.2:**
- Architecture diagram showing components
- Component details table (service, purpose, sizing)
- Data flow overview

Add deployment details from Exercise 2.1 if relevant.

**Step 6: Present Security Architecture**

**Copy from Exercise 1.2:**
- Security controls summary (all five layers)
- Compliance mapping showing how controls meet requirements

Ensure it's client-ready quality - clear diagrams, professional formatting.

**Step 7: Present Cost Analysis**

**Copy from Exercise 1.3:**
- 12-month projection table
- Cost optimization roadmap
- ROI analysis (investment, benefits, payback period)

Add any insights from scaling configuration in Ex 2.1.

**Step 8: Present Implementation Roadmap**

**Copy from Exercise 2.1:**
- Phase timeline (Pilot, Limited, GA)
- Key milestones with target dates and dependencies

Visual timeline format works well (see template).

**Step 9: Define Next Steps**

Immediate actions (next 2 weeks):
- 3-5 specific actions

Decision points:
- Platform approval - who decides, by when
- Budget approval - who decides, by when
- Security sign-off - who decides, by when

**Step 10: Create Executive Presentation**

10-15 slide outline:
1. Title
2. Executive Summary (one slide)
3. Business Challenge
4. Proposed Solution (high-level architecture visual)
5. Why [Platform Name] (3-4 key criteria)
6. Reference Architecture (detailed diagram)
7. Security & Compliance (key controls)
8. Cost Overview (year 1 investment, ROI)
9. Implementation Timeline (phases and milestones)
10. Risks & Mitigations (top 3-4)
11. Success Metrics (KPIs and targets)
12. Next Steps (actions and decisions)

**Step 11: Review for Client-Ready Quality**

Check:
- [ ] Professional formatting and diagrams
- [ ] No placeholder text or TODOs
- [ ] Consistent terminology throughout
- [ ] All sections complete
- [ ] Executive summary compelling
- [ ] Recommendations data-driven and defendable
- [ ] Timeline realistic
- [ ] Next steps clear and actionable

---

#### Deliverable Specification

**File Names:**
- `enterprise-architecture-proposal.md` (written proposal)
- `executive-presentation-outline.md` or slides (presentation)

**Location:** Your working directory for Module 6

**Quality Criteria (Evaluation Rubric):**

**Criterion 1: Platform Analysis (5 points)**
- Comprehensive platform comparison with detailed scoring
- Clear rationale for recommendation
- Client-specific factors addressed
- Risk analysis included

**Criterion 2: Security Architecture (5 points)**
- Defense-in-depth architecture with all layers
- AI-specific security controls clearly identified
- Compliance mapped to specific controls
- Practical implementation details

**Criterion 3: Cost & Operations (5 points)**
- Detailed cost model with scaling projections
- Complete operations runbook
- Realistic scaling and deployment plan
- Optimization strategies identified

**Criterion 4: Enterprise Proposal Quality (5 points)**
- Client-ready professional quality
- Executive summary compelling
- Clear, data-driven recommendations
- Realistic roadmap with next steps
- All components integrated cohesively

**Certification Requirement:** 14/20 points minimum (70%)

---

#### Tips

- **Reuse aggressively** - Copy sections from exercises 1.1-2.2, don't rewrite
- **Professional polish** - This goes to executives, not just technical teams
- **Be specific** - "Implement encryption" is vague; "AES-256 encryption at rest using AWS KMS" is specific
- **Show your work** - Include weighted scoring, cost calculations, architectural diagrams
- **Make it defendable** - Every recommendation should have data supporting it

---

## Templates & Resources

All templates for exercises 2.1-2.3 are provided in the session.md file and can be copied directly.

### Additional Resources

| Resource | Link | Purpose |
|----------|------|---------|
| AWS Auto Scaling | [AWS Docs](https://docs.aws.amazon.com/autoscaling/) | Scaling configuration reference |
| Azure Monitor | [Azure Docs](https://docs.microsoft.com/en-us/azure/azure-monitor/) | Observability setup |
| Google Cloud Monitoring | [GCP Docs](https://cloud.google.com/monitoring/docs) | Metrics and alerting |

---

## Self-Assessment

### Exit Criteria Checklist

Before considering module complete, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Configure auto-scaling for AI workloads | Ex 2.1 includes multi-trigger scaling config | ☐ |
| 2 | Design hybrid/on-prem architectures | Ex 2.1 addresses deployment environment | ☐ |
| 3 | Implement observability with AI metrics | Ex 2.2 includes token usage, cost metrics | ☐ |
| 4 | Create phased deployment strategies | Ex 2.1 has pilot/limited/GA phases | ☐ |
| 5 | Synthesize enterprise architecture proposals | Ex 2.3 capstone is complete and client-ready | ☐ |

---

### Module Deliverables Checklist

| Deliverable | File Name | Complete? |
|-------------|-----------|-----------|
| Session 1, Ex 1.1 | `platform-comparison-analysis.md` | ☐ |
| Session 1, Ex 1.2 | `security-architecture-design.md` | ☐ |
| Session 1, Ex 1.3 | `cost-model.md` | ☐ |
| Session 2, Ex 2.1 | `deployment-strategy.md` | ☐ |
| Session 2, Ex 2.2 | `operations-runbook.md` | ☐ |
| **Session 2, Ex 2.3** | **`enterprise-architecture-proposal.md`** | **☐** |
| **Session 2, Ex 2.3** | **Executive presentation** | **☐** |

---

## Module Completion

### Certification

**To earn Module 6 certification:**
- Complete capstone proposal (Exercise 2.3) with all required sections
- Achieve minimum 14/20 points on evaluation rubric
- All sections demonstrate client-ready quality

### What You've Achieved

Congratulations on completing Advanced Module 6: Enterprise AI Architecture!

You can now:
- Compare and select cloud AI platforms using structured frameworks
- Design deployment and security architectures for enterprise AI
- Build cost models with scaling projections and optimization strategies
- Configure auto-scaling and observability for production AI systems
- Create phased deployment strategies de-risking enterprise rollouts
- Deliver client-ready enterprise architecture proposals

**This is advanced material.** You're equipped to advise enterprises on AI architecture at scale.

### Next Steps

- Submit capstone for Module 6 certification
- Apply these skills in real client engagements
- Explore other advanced modules (Modules 7-10 available)
- Share your proposals and learnings with cohort

---

## Getting Help

### Support Channels

- **Async Support** - Post questions in support channel
- **Peer Discussion** - Share work and get feedback from cohort
- **Office Hours** - If available for this cohort

### Common Questions

**Q: How do I know if my capstone is good enough?**
A: Check against the rubric. Does it have all required sections? Is it client-ready quality? Are recommendations data-driven? If yes to all, you're ready to submit.

**Q: Can I use the same client scenario across all exercises?**
A: Yes, strongly recommended. Using one consistent scenario creates a cohesive capstone.

**Q: My deployment strategy seems too simple. Is that OK?**
A: Simple is often better. Phased rollout with clear success criteria is better than over-engineered complexity. Focus on being realistic and actionable.

---

## Glossary

| Term | Definition |
|------|------------|
| **Auto-scaling** | Automated adjustment of compute resources based on demand |
| **Capstone** | Final comprehensive project synthesizing all module learning |
| **Go/No-Go** | Decision point to proceed or stop based on defined criteria |
| **Hybrid architecture** | Deployment combining cloud and on-premises infrastructure |
| **Observability** | Ability to understand system state from external outputs |
| **On-premises** | Infrastructure hosted in client's own data centers |
| **Phased deployment** | Staged rollout to progressively larger user groups |
| **Runbook** | Operational documentation for running system in production |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial participant guide created |

---

**Navigation:** [← Session 1](../session-1/participant-guide.md) | Session 2

---

**Congratulations on completing Module 6!**
