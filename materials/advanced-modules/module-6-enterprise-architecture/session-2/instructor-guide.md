# **INSTRUCTOR GUIDE: ADVANCED MODULE 6, SESSION 2**
## **Production Deployment & Operations**

**Module:** Advanced Module 6: Enterprise AI Architecture
**Session:** 2 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Scaling patterns, hybrid architectures, operations/observability, deployment strategies, and module capstone |
| **Difficulty Level** | High - Culminates in enterprise architecture proposal |
| **Prep Time Required** | 45 minutes |
| **Demo Required** | Optional - Scaling configuration walkthrough |
| **Tech Setup Needed** | Screen sharing for configuration examples |
| **Common Challenges** | Participants may lack ops experience; capstone synthesis requires pulling together all prior work |

---

## Navigation

**Module Navigation:** [← Session 1 Instructor Guide](../session-1/instructor-guide.md) | Session 2

**Related Materials:**
- [Session 2 Presentation Slides](presentation.md)
- [Session 2 Participant Guide](participant-guide.md)
- [Module 6 Main Document](../module-6-enterprise-architecture.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Session 2 materials | ☐ |
| Check Session 1 completion | Verify participants completed exercises 1.1-1.3 | ☐ |
| Prepare scaling example | Have auto-scaling JSON config ready to share | ☐ |
| Review capstone requirements | Understand how exercises feed into capstone | ☐ |
| Update any stale examples | Verify cloud platform features haven't changed | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready | ☐ |
| Prepare capstone template | Have proposal template ready to share | ☐ |
| Check participant readiness | Review Session 1 exercise completion rates | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, config examples, templates | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Answer quick questions about Session 1 work | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Session 1 recap, preview | Connect to prior work |
| 0:03 | 12 min | Segment 1 | Scaling Patterns | Show config example |
| 0:15 | 12 min | Segment 2 | Hybrid/On-Prem | Focus on when, not how to implement |
| 0:27 | 12 min | Segment 3 | Operations/Observability | AI-specific metrics emphasis |
| 0:39 | 9 min | Segment 4 | Deployment Strategy | Connect to real rollout challenges |
| 0:48 | 3 min | Closing | Capstone overview, resources | Critical - capstone is main deliverable |
| **Total** | **51 min** | | | Includes 6 min buffer |

### Timing Flexibility

**If Running Behind:**
- Segment 2: Abbreviate on-premises options discussion
- Segment 3: Skip incident response workflow detail
- Segment 4: Shorten migration strategies discussion

**If Running Ahead:**
- Segment 1: Discuss capacity planning in more depth
- Segment 2: Add hybrid architecture case studies
- Segment 3: Deep dive on AI-specific monitoring challenges
- More Q&A time before capstone overview

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | If behind, skip capacity planning details |
| End Segment 2 | 0:27 | If behind, simplify connectivity discussion |
| Start Closing | 0:48 | Must start by here - capstone overview is essential |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slides 1-3: Title, Overview, Session 1 Recap**

**Key Actions:**
1. Welcome participants to final session
2. Recap Session 1 deliverables
3. Preview how Session 2 builds to capstone
4. Create energy around completing the module

**Opening Script:**
> "Welcome to Session 2 - our final session of Enterprise AI Architecture. Last time, you selected platforms, designed security architecture, and built cost models. Today we're making those designs operational: scaling, monitoring, deploying, and running AI systems in production.
>
> This session culminates in the module capstone: a complete Enterprise Architecture Proposal. The good news - you've already done most of the work. Today we synthesize it into a client-ready artifact.
>
> Let's get started with scaling patterns."

**Engagement Opportunity:**
> "Quick check: How many completed all three exercises from Session 1?"

[Expect most hands - if not, note who needs catch-up support]

---

### Segment 1: Scaling Patterns for AI Workloads (12 minutes)

**Learning Objective:** Configure auto-scaling strategies for AI workloads

**Slides:** 4-8

#### Content Delivery

**Key Point 1: Scaling Challenge (Slide 4)**
- Main message: AI workloads scale differently due to token limits and cost per request
- Example: "Traditional app: add CPU, handle more load. AI app: hit token limit, requests fail regardless of CPU"
- Common misconception: "Scaling AI is just like scaling any app" - it's not

**Key Point 2: Auto-Scaling Strategies (Slide 5)**
- Main message: Use multiple triggers - requests, tokens, queue depth
- Demonstration: Show how request-based alone fails when token limits hit first
- Participant relevance: "You'll configure this in Exercise 2.1"

**Key Point 3: Configuration Example (Slide 6)**
- Main message: Production config uses multiple triggers, min instances for HA, max for cost protection
- Walk through JSON config line by line
- Emphasize delays to prevent flapping

**Key Point 4: Load Balancing (Slide 7)**
- Main message: Session affinity critical for multi-turn conversations
- Example: Chatbot without session affinity loses context between messages
- AI-specific: Health probes must check AI API connectivity

#### Facilitation Notes

**Watch For:**
- Participants asking "What numbers should I use?" - answer depends on traffic patterns
- Confusion about token limits vs request limits - clarify these are different caps

**If Asked About "How do I determine the right max_instances?":**
> "Start with cost budget. If your max budget is $100/hour and each instance costs $2/hour in AI API calls, max = 50. Test and adjust."

**Transition to Segment 2:**
> "We've covered cloud scaling. But many enterprises can't use cloud AI due to compliance or data sovereignty. Let's talk hybrid and on-premises."

---

### Segment 2: Hybrid and On-Premises Architectures (12 minutes)

**Learning Objective:** Design hybrid and on-premises architectures

**Slides:** 9-13

#### Content Delivery

**Key Point 1: When On-Prem Makes Sense (Slide 9)**
- Main message: Not just compliance - cost at extreme scale favors self-hosted
- Visual to emphasize: Decision tree for cloud vs hybrid vs on-prem
- Break-even rough estimate: < 1M requests/day → cloud, > 10M → consider self-hosted

**Key Point 2: Hybrid Patterns (Slides 10-11)**
- Main message: Two common patterns - data on-prem with cloud AI, or edge processing
- Pattern A: Keep sensitive data on-premises, send to cloud AI for processing, return results
- Pattern B: Edge filtering/caching, regional processing, central cloud AI for complex tasks

**Key Point 3: On-Prem Options (Slide 12)**
- Main message: Self-hosted LLMs, private cloud, or appliances - each with trade-offs
- Self-hosted: Max control, max complexity
- Private cloud: Vendor-managed but dedicated infrastructure
- Appliance: Pre-configured hardware/software, simplest deployment

#### Facilitation Notes

**Energy Check:**
At this point (15-27 min), participants may be:
- Overwhelmed by operational complexity
- Recommended adjustment: Keep it high-level, focus on when not how

**Common Confusion Point:**
"Do I need to run my own data center for on-prem?"

**Clarification Approach:**
> "Not necessarily. On-premises can mean your data center, a colo facility, or even a dedicated region in cloud provider's infrastructure. The key is data doesn't leave your control perimeter."

**Transition to Segment 3:**
> "Whether cloud, hybrid, or on-prem - you need observability. Let's talk about monitoring AI systems in production."

---

### Segment 3: Operations and Observability (12 minutes)

**Learning Objective:** Implement observability stacks with AI-specific metrics

**Slides:** 14-18

#### Content Delivery

**Key Point 1: Observability Stack (Slide 14-15)**
- Main message: Three pillars - metrics, logs, traces - plus dashboards and alerts
- Framework/Pattern: Metrics (Prometheus), Logs (ELK/CloudWatch), Traces (Jaeger)
- All feed into centralized dashboards (Grafana, Datadog, CloudWatch)

**Key Point 2: AI-Specific Metrics (Slide 16)**
- Main message: Track token usage rate, not just requests/second
- Example walkthrough: "P95 latency >10s alerts. Cost per request >target alerts. Token usage >80% of limit alerts."
- Critical: "These are AI-specific - traditional app monitoring misses them"

**Key Point 3: Logging Best Practices (Slide 17)**
- Main message: Log request/response (sanitized), token counts, model versions, trace IDs
- Sanitization emphasis: "Never log raw PII - redact before logging"
- Compliance need: Audit logs for regulated industries

**Key Point 4: Incident Response (Slide 18)**
- Main message: Six-step workflow - Detect, Triage, Contain, Investigate, Resolve, Review
- AI-specific triage: Is this AI API issue or infrastructure issue?
- Containment options: Circuit breaker, fallback to simpler model, disable feature

#### Practical Application

**Consulting Connection:**
> "When advising clients on operations, they'll ask 'How do we know if it's working?' Observability is your answer. Show them dashboards with AI-specific metrics, alert thresholds, and incident procedures."

**Example Scenario:**
> "Client reports 'AI is slow.' Without observability, you're guessing. With it, you check: Token usage at 95% → hitting rate limits. P95 latency from AI API is 15s → provider issue, not yours. Error rate 0% → not failing, just slow. Now you can recommend: request rate limit increase from provider or implement caching to reduce token usage."

#### Facilitation Notes

**Common Confusion Point:**
Difference between metrics, logs, and traces

**Clarification Approach:**
> "Metrics: time series numbers (latency, token count). Logs: text events (request received, error occurred). Traces: path through distributed system (API Gateway → Lambda → Bedrock)."

**Transition to Segment 4:**
> "We've designed architecture, configured scaling, set up monitoring. Final piece: how do you actually roll this out to thousands of users? That's deployment strategy."

---

### Segment 4: Enterprise Deployment Strategy (9 minutes)

**Learning Objective:** Create phased deployment strategies for enterprise rollouts

**Slides:** 19-22

#### Content Delivery

**Key Point 1: Deployment Phases (Slide 19-20)**
- Main message: Three phases - Pilot (10 users, 4-6 weeks), Limited (100 users, 8-12 weeks), General (all users, ongoing)
- Each phase has go/no-go decision point based on success criteria
- Value: De-risks rollout, allows learning and iteration

**Key Point 2: Migration Strategies (Slide 21)**
- Main message: Four approaches - big bang, parallel run, phased, feature flags
- Trade-offs: Big bang (fast but risky) vs Parallel (safe but expensive) vs Phased (balanced) vs Feature flags (most flexible)
- Recommendation: Phased with feature flags for maximum control

**Key Point 3: Rollback Planning (Slide 22)**
- Main message: Define rollback triggers, document procedure, test in staging
- Critical: "Hope for the best, plan for the worst. Every deployment needs rollback plan."
- Test rollback: "If you've never tested rollback, it won't work when you need it"

#### Closing This Segment

**Key Takeaway:**
> "Deployment strategy is risk management. Phased rollout with clear go/no-go criteria lets you catch issues early with small blast radius."

**Connection to Homework:**
> "Exercise 2.1 is creating a complete deployment strategy. You'll define phases, success criteria, rollback procedures - everything needed for real enterprise rollout."

---

### Closing (3 minutes)

**Slides:** 23-25

**Do Not Skip This Section** - capstone overview is critical

#### Capstone Overview

**Key Actions:**
1. Explain capstone structure and deliverables
2. Show how all exercises feed into capstone sections
3. Emphasize this is reuse/synthesis, not starting from scratch
4. Point to templates and support resources

**Script:**
> "The module capstone brings everything together into an Enterprise AI Architecture Proposal.
>
> Two deliverables: written proposal and executive presentation deck.
>
> [Show how exercises map to sections]
>
> Your Session 1 platform comparison goes directly into the Platform Recommendation section. Security architecture from Ex 1.2 becomes the Security Architecture section. Cost model from Ex 1.3 is your Cost Analysis.
>
> Today's deployment strategy and ops runbook complete it.
>
> You're not starting from scratch - you're synthesizing existing work into a cohesive client-ready proposal.
>
> This is what you'd present to a CTO. Make it professional quality.
>
> Templates are in your participant guide."

#### Resources and Support

> "Complete templates in participant guide. Reuse all your exercise work - copy sections, polish, integrate.
>
> Questions in async channel. This is your final deliverable - make it great."

#### Module Completion

> "Complete the capstone proposal to earn Module 6 certification.
>
> [Pause]
>
> Congratulations on reaching this point. Advanced Module 6 is challenging material. You're now equipped to design and deploy enterprise AI architecture at scale.
>
> Questions before you start the capstone?"

[Answer 1-2 questions if time]

> "Excellent work. Good luck with your proposals!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: "What if my client doesn't have predictable traffic patterns for scheduled scaling?"**
A: "Then don't use scheduled scaling as primary strategy. Use request-based or custom metric scaling. Scheduled scaling is only for known patterns like 'Monday 9 AM spike.' If traffic is unpredictable, rely on reactive triggers."

**Q: "How do I know if on-premises makes sense for my client?"**
A: "Three questions: (1) Do regulations prohibit cloud? If yes, on-prem. (2) Is usage >10M requests/day? If yes, do cost analysis. (3) Do they have ops expertise for self-hosted infrastructure? If no, probably stay cloud despite cost."

**Q: "What's the difference between observability and monitoring?"**
A: "Monitoring: tracking known problems (CPU >80% alert). Observability: ability to investigate unknown problems. Monitoring tells you 'system is slow.' Observability lets you investigate why - trace requests, analyze logs, correlate metrics. You need both."

### Technical Questions

**Q: "What monitoring tools should I recommend?"**
A: "Depends on platform and budget. AWS → CloudWatch (built-in, cheap, basic). Multi-cloud or advanced needs → Datadog (expensive, powerful). Self-hosted preference → Prometheus + Grafana. Start simple, add capabilities as needed."

**Q: "How do I handle session state in serverless if I need session affinity?"**
A: "Two options: (1) Sticky sessions in load balancer - routes same user to same Lambda instance while it's warm. (2) External state store like DynamoDB keyed by session ID. Option 2 is more reliable since Lambda instances are ephemeral."

### Capstone Questions

**Q: "How long should the capstone proposal be?"**
A: "Focus on completeness, not length. All required sections with real content. Typically 15-25 pages including diagrams. Executive presentation is 10-15 slides."

**Q: "Can I use a real client scenario or should I make one up?"**
A: "Real is better if you can. Sanitize client name and sensitive details, but real scenarios are more authentic. If you don't have one, create realistic scenario based on common client patterns."

**Q: "Do I need to create all new diagrams?"**
A: "No - reuse your Session 1 architecture diagrams. Refine them, add deployment details, make them presentation-ready. Don't start from scratch."

### Pushback/Objections

**Q: "This seems like overkill for small deployments."**
A: "You're right - scale the approach. 10-user pilot doesn't need 3-phase rollout. But the module prepares you for enterprise scale. Apply principles proportionally. Even small deployments need basic monitoring and rollback plans."

**Q: "Our team won't have time for all this operational complexity."**
A: "That's a real constraint. Options: (1) Use managed services that handle ops for you. (2) Start simple - basic scaling, basic monitoring - add sophistication as you grow. (3) Partner with managed service provider. Don't over-engineer early, but plan for operational needs."

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save chat questions | For FAQ updates |
| Note capstone common questions | Update guidance for future cohorts |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording | ☐ |
| Answer pending questions in async channel | ☐ |
| Send capstone reminder with template links | ☐ |
| Check Session 1 completion status for stragglers | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review capstone submissions (spot check 3-5) | ☐ |
| Provide feedback on capstone quality | ☐ |
| Identify participants needing additional support | ☐ |
| Update instructor guide with lessons learned | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Session

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 2.1 | `deployment-strategy.md` | Participant's working directory |
| 2.2 | `operations-runbook.md` | Participant's working directory |
| 2.3 | `enterprise-architecture-proposal.md` + Executive presentation | Participant's working directory |

### Capstone Quality Indicators

**Look For:**
- All required sections present and complete
- Clear platform recommendation with data from Ex 1.1
- Security architecture covering all five layers from Ex 1.2
- Cost projections with scaling scenarios from Ex 1.3
- Deployment strategy with phased approach from Ex 2.1
- Professional quality suitable for client presentation

**Red Flags:**
- Copy-paste of exercises without synthesis
- Missing sections or placeholder text
- Generic content not tied to specific client scenario
- No architecture diagrams
- Unrealistic cost projections or timelines

### Intervention Thresholds

- Exercises 2.1 or 2.2 incomplete: Reach out, offer support
- Capstone missing key sections: Provide specific feedback before certification
- Low quality across all deliverables: 1:1 conversation about module objectives

---

## Module-Specific Notes

### What Makes This Session Unique

Final session of advanced module:
- Synthesizes all prior learning into capstone
- More operational focus than architectural
- Capstone requires pulling together disparate pieces into cohesive whole
- Participants may struggle with synthesis vs just completing exercises

### Module Capstone Emphasis

The capstone is the primary assessment for Module 6:
- Worth more than individual exercises
- Tests ability to create client-ready artifacts
- Requires synthesis, not just execution
- Should be professional quality suitable for real client presentations

### Dependencies

**Builds On:**
- Session 1: Platform selection, security architecture, cost modeling
- Block 3: Agent architecture and deployment knowledge
- Real or realistic client scenarios for authentic proposals

**Completes:**
- Module 6: Enterprise AI Architecture
- Advanced modules track (optional post-Block 3)

---

## Assessment Notes

### Capstone Evaluation Criteria

From Module Appendix C:

**Criterion 1: Platform Analysis (5 points)**
- Comprehensive comparison with weighted scoring
- Clear recommendation with rationale
- Client-specific factors addressed

**Criterion 2: Security Architecture (5 points)**
- Defense-in-depth with all layers
- AI-specific controls
- Compliance mapping

**Criterion 3: Cost & Operations (5 points)**
- Detailed cost model with projections
- Operational procedures documented
- Realistic scaling plan

**Criterion 4: Proposal Quality (5 points)**
- Client-ready presentation quality
- All components integrated
- Realistic roadmap and next steps

**Certification Requirement:** 14/20 minimum (70%)

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Auto-scaling for AI needs multiple triggers - requests AND tokens AND queue depth"
2. "On-premises makes sense for compliance AND cost at extreme scale"
3. "AI-specific metrics matter: token usage, cost per request, quality scores"
4. "Phased deployment de-risks rollout: pilot → limited → general availability"
5. "Capstone synthesis what you've learned - reuse your exercise work"

### If You Only Have Time For One Thing

The capstone overview. Participants must understand how to synthesize their work into the final proposal - this is the main module deliverable.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Phased deployment | "Like airplane testing: ground tests, then taxi tests, then short flights, then commercial service - catch issues early" | Explaining deployment strategy |
| Observability vs monitoring | "Monitoring: dashboard in your car. Observability: ability to diagnose why car is making that weird noise" | Explaining observability stack |
| Multi-trigger scaling | "Like home security: motion sensors AND door sensors AND window sensors - catch all threats" | Explaining auto-scaling strategies |

---

**Version History:**

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial instructor guide created | [Instructor] |
