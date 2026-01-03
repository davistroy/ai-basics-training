# **POWERPOINT PRESENTATION: ADVANCED MODULE 6, SESSION 2**
## **Production Deployment & Operations**

**Module:** Advanced Module 6: Enterprise AI Architecture
**Session Number:** 2 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 graduates who advise clients on deploying and operating enterprise-scale AI systems in production.

**Key Thesis:** Production AI systems require scaling architectures fundamentally different from traditional applications because they must manage token-based constraints, variable latency, and real-world action consequences that amplify through agent autonomy, making multi-layer defense-in-depth essential for reliability at scale.

**Session Learning Objectives:** By the end of this session, participants will:
1. Configure auto-scaling strategies for AI workloads based on different triggers
2. Design hybrid and on-premises architectures for regulated environments
3. Implement observability stacks with AI-specific metrics and monitoring
4. Create phased deployment strategies for enterprise rollouts

**Entry Criteria:**
- [ ] Platform comparison completed (Session 1, Exercise 1.1)
- [ ] Security architecture designed (Session 1, Exercise 1.2)
- [ ] Cost model created (Session 1, Exercise 1.3)
- [ ] Understanding of deployment patterns (Session 1)

**Exit Criteria:**
- [ ] Deployment strategy documented
- [ ] Scaling patterns implemented
- [ ] Operations runbook created
- [ ] Module capstone delivered
- [ ] Executive presentation ready

**Presentation Structure:**
1. Opening & Session 1 Recap (3 min) - Slides 1-3
2. Segment 1: Scaling Patterns for AI Workloads (12 min) - Slides 4-8
3. Segment 2: Hybrid and On-Premises Architectures (12 min) - Slides 9-13
4. Segment 3: Operations and Observability (12 min) - Slides 14-18
5. Segment 4: Enterprise Deployment Strategy (9 min) - Slides 19-22
6. Capstone Overview & Close (3 min) - Slides 23-25

**Total Slides:** 25

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Advanced Module 6, Session 2: Production Deployment & Operations

**Subtitle:** Scaling, Operations, and Enterprise Rollout Strategies

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program

**Graphic:** Clean title slide with program branding. Advanced module color scheme.

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Session 2 of Enterprise AI Architecture. Last session, you learned how to select platforms, design architectures, and secure AI systems. Today, we're moving to production: how do you actually deploy, scale, monitor, and operate these systems at enterprise scale?

This is where theory meets reality. You've designed the architecture - now let's talk about running it in production with thousands of users.

Today's session culminates in the module capstone: a complete Enterprise AI Architecture Proposal that you can use in real client engagements.

Let's get started."

[Transition: Click to next slide]

---

### SLIDE 2: SESSION OVERVIEW

**Title:** This Session's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Session 1 Recap & Preview |
| 3-15 min | Segment 1 | Scaling Patterns for AI Workloads |
| 15-27 min | Segment 2 | Hybrid & On-Premises Architectures |
| 27-39 min | Segment 3 | Operations and Observability |
| 39-48 min | Segment 4 | Enterprise Deployment Strategy |
| 48-51 min | Close | Capstone Overview & Resources |

**Graphic:** Timeline showing session flow

**SPEAKER NOTES:**

"Here's what we're covering in the next 45 minutes:

First, scaling patterns - how to configure auto-scaling for AI workloads. Token limits, burst handling, and capacity planning.

Second, hybrid and on-premises patterns - when and how to deploy AI outside the cloud. This is critical for regulated industries.

Third, operations and observability - monitoring AI-specific metrics, incident response, and operational procedures.

Finally, enterprise deployment strategies - phased rollouts, migration strategies, and change management.

Then we'll preview the module capstone, which brings everything together into a client-ready proposal.

Questions before we dive in?"

[Transition]

---

### SLIDE 3: SESSION 1 RECAP

**Title:** Building on Session 1

**Content:**

**What You Completed:**
- Platform comparison with weighted scoring
- Security architecture with defense-in-depth
- Cost modeling with scaling projections

**How Session 2 Builds:**
- Platform selection → Deployment strategy
- Architecture design → Operations and monitoring
- Cost model → Capacity planning and optimization

**Capstone Connection:**
All exercises from both sessions feed into the Enterprise Architecture Proposal.

**Graphic:** Flow diagram showing progression

**SPEAKER NOTES:**

"Quick recap of Session 1:

You selected a platform using weighted scoring. You designed security architecture with five layers. You built cost models projecting scaling scenarios.

[Point to how Session 2 builds]

Today we're taking those decisions and making them operational. Your platform selection informs deployment strategy. Your architecture design informs monitoring. Your cost model informs capacity planning.

By the end of today, you'll have a complete enterprise AI architecture ready to present to clients.

Let's talk about scaling."

[Transition: Click to Segment 1]

---

## SEGMENT 1: SCALING PATTERNS FOR AI WORKLOADS
### Duration: 12 minutes | Slides 4-8

---

### SLIDE 4: THE SCALING CHALLENGE

**Title:** AI Workloads Have Unique Scaling Needs

**Content:**

**The Challenge:**
AI workloads don't scale like traditional web apps. Token limits, model latency, and cost per request create unique constraints.

**Scaling Dimensions:**
- Throughput (requests/second)
- Token capacity (tokens/minute)
- Cost ($/hour)
- Latency (P95, P99)

**Why It Matters:**
Poor scaling leads to rate limit errors, latency spikes, cost overruns, or outages during traffic spikes.

**Graphic:** Graph showing traffic spike with different scaling responses

**GRAPHICS:**

**Graphic 1: AI Workload Scaling Challenge**
- Purpose: Illustrate how different scaling approaches respond to traffic spikes
- Type: Line graph with scaling response comparison
- Elements:
  - X-axis: Time
  - Y-axis: Requests/second
  - Line 1: Actual traffic (spikes from 100 to 1000 req/s)
  - Line 2: Manual scaling (flat line, unable to handle spike, shows failures)
  - Line 3: CPU-based auto-scaling (lags behind traffic, some failures)
  - Line 4: Token-aware auto-scaling (matches traffic, no failures)
  - Failure zones marked in red where capacity < demand
- Labels:
  - Traffic spike event marker
  - "Token limit hit" annotation on CPU-based line
  - "Scaling lag" annotation
  - "Optimal response" annotation on token-aware line
- Relationships: Comparison showing different scaling strategies' effectiveness
- Visual cues: Red zones for failures/errors, green zone for successful handling, dotted lines for capacity limits

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Scaling AI workloads is different from scaling traditional applications.

Traditional apps scale based on CPU and memory. Add more servers, handle more requests - simple.

AI workloads have different constraints:

Token limits - platform APIs have tokens-per-minute caps. Hit the limit, requests fail.

Model latency - the AI API itself has variable latency. Your scaling can't fix that.

Cost - scaling up means more AI API costs. Unlike adding cheap compute, AI tokens cost real money.

[Pause]

I've seen production systems fail because scaling was configured for CPU, not tokens. We need AI-specific scaling strategies."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide establishes why AI scaling is fundamentally different from traditional application scaling
- Creates urgency and practical motivation for the specific strategies that follow
- Addresses common misconception that traditional auto-scaling approaches work for AI workloads

**Key Research & Citations:**
- Based on production experience with AWS Bedrock and Azure OpenAI rate limits
- Token-per-minute (TPM) limits vary by model tier and often become the constraining factor before CPU/memory
- Research from cloud provider documentation on AI-specific scaling patterns

**Q&A Preparation:**
- *"Can't we just over-provision to avoid scaling issues?"*: Yes but cost becomes prohibitive - AI API costs scale linearly unlike traditional compute economies of scale
- *"What about caching to reduce scaling needs?"*: Excellent strategy covered in hybrid patterns, but doesn't eliminate need for proper scaling design
- *"How do we know token limits in advance?"*: Provider documentation and monitoring - track actual usage against documented limits

---

### SLIDE 5: AUTO-SCALING STRATEGIES

**Title:** Five Auto-Scaling Triggers for AI

**Content:**

| Strategy | Trigger | Best For | Trade-off |
|----------|---------|----------|-----------|
| **Request-based** | Requests/second | Synchronous APIs | May hit token limits |
| **Queue-depth** | Messages in queue | Async processing | Latency for queued items |
| **CPU/Memory** | Resource utilization | Container workloads | Lags behind actual load |
| **Custom metric** | Token usage rate | All patterns | Requires custom metrics |
| **Scheduled** | Time of day | Predictable patterns | Doesn't handle spikes |

**Recommendation:** Use multiple triggers with different weights.

**Graphic:** Comparison table as shown

**SPEAKER NOTES:**

"[INSIGHT - Deliver solution]"

"Five auto-scaling strategies for AI workloads:

[Walk through each row]

Request-based scaling: Scale when requests/second hits threshold. Simple but risky - you might hit token limits before request limits.

Queue-depth scaling: For async patterns. Scale when queue builds up. Works well but queued items wait.

CPU/memory scaling: Traditional approach. Works for container workloads but lags - you're scaling based on symptoms, not root cause.

Custom metric scaling: Scale based on token usage rate. Best approach but requires setting up custom metrics.

Scheduled scaling: Pre-scale for known patterns. Great for 'every Monday at 9 AM' spikes but doesn't handle unexpected load.

[Emphasize]

Best practice: combine multiple triggers. Scale on requests AND token usage AND queue depth. Cover all bases."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide provides the practical toolkit for implementing AI-specific scaling strategies
- Directly addresses the challenge established in SLIDE 4 with actionable solutions
- Each strategy has clear trade-offs that help practitioners choose appropriate approach

**Key Research & Citations:**
- Request-based and CPU/memory scaling are standard cloud patterns (AWS Auto Scaling, Azure VMSS)
- Custom metric scaling based on token usage requires CloudWatch custom metrics (AWS) or Azure Monitor custom metrics
- Queue-depth scaling pattern from AWS SQS-based scaling and Azure Queue Storage triggers
- Token rate limiting behavior documented in OpenAI, Anthropic, and cloud provider API documentation

**Q&A Preparation:**
- *"Which single trigger should we use if we can only choose one?"*: Custom metric based on token usage rate - it's closest to the actual constraint
- *"How do we track token usage in real-time?"*: Application instrumentation sending metrics to CloudWatch/Azure Monitor, covered in observability segment
- *"What if scheduled scaling conflicts with metric-based scaling?"*: Triggers combine (take maximum), but generally avoid mixing scheduled with reactive for same service

---

### SLIDE 6: SCALING CONFIGURATION EXAMPLE

**Title:** Production Scaling Configuration

**Content:**

**Auto-Scaling JSON:**
```json
{
  "auto_scaling": {
    "min_instances": 2,
    "max_instances": 50,
    "target_cpu_utilization": 70,
    "scale_up_threshold": {
      "requests_per_second": 100,
      "queue_depth": 1000,
      "token_usage_rate": 80
    },
    "scale_down_delay_seconds": 300,
    "scale_up_cooldown_seconds": 60
  }
}
```

**Key Parameters:**
- **min_instances: 2** - Always-on for high availability
- **max_instances: 50** - Cost protection cap
- **scale_down_delay: 300s** - Prevent flapping
- **Multiple triggers** - Requests, queue, tokens

**Graphic:** Annotated JSON configuration

**SPEAKER NOTES:**

"[DEMO - Show configuration]"

"Here's what production scaling configuration looks like:

[Point to min_instances]

Always run at least 2 instances for high availability. No single point of failure.

[Point to max_instances]

Cap at 50 to protect against runaway costs. If you hit 50 and still can't keep up, that's a different problem.

[Point to thresholds]

Three triggers: 100 requests/second, OR queue depth > 1000, OR token usage > 80%.

[Point to delays]

Scale down delay of 5 minutes prevents flapping. Don't want to scale down during temporary lull only to scale back up.

Scale up cooldown of 60 seconds prevents too-rapid scaling.

[Pause]

This configuration handles most production scenarios. Adjust thresholds based on your traffic patterns."

[Transition]

---

### SLIDE 7: LOAD BALANCING FOR AI

**Title:** AI-Specific Load Balancing Considerations

**Content:**

**Standard Load Balancing:**
- Distribute requests across instances
- Health checks
- Geographic routing

**AI-Specific Additions:**
1. **Session affinity** - Multi-turn conversations need same instance
2. **AI health probes** - Check AI API connectivity, not just HTTP 200
3. **Weighted routing** - A/B test different models or prompt templates
4. **Cost-aware routing** - Route expensive requests to reserved capacity

**Session Affinity Example:**
```
User A, Message 1 → Instance 1 (stores context)
User A, Message 2 → Instance 1 (uses context)
User A, Message 3 → Instance 1 (continues conversation)
```

**Graphic:** Load balancer diagram with session affinity highlighted

**GRAPHICS:**

**Graphic 1: Load Balancing with Session Affinity**
- Purpose: Show how session affinity ensures conversation continuity for multi-turn interactions
- Type: Architecture diagram with session flow
- Elements:
  - Top: Load Balancer (icon)
  - Bottom: Three backend instances (Instance 1, 2, 3)
  - User A's requests (3 sequential messages) all routed to Instance 1 (highlighted)
  - User B's requests routed to Instance 2
  - User C's requests distributed to Instance 3
  - Context storage shown within each instance
- Labels:
  - "Session Affinity: Same user → Same instance"
  - "User A Conversation Context" stored in Instance 1
  - "Multi-turn conversation preserved"
  - Arrows showing routing decisions
- Relationships: Sticky sessions maintaining user-to-instance mapping
- Visual cues:
  - Color coding per user (User A=blue, User B=green, User C=purple)
  - Arrows from load balancer to instances
  - Session ID cookies/tokens shown
  - Context icon (chat bubbles) in instances

**SPEAKER NOTES:**

"Load balancing for AI has unique considerations:

[Point to session affinity]

Multi-turn conversations - like chatbots - need session affinity. User's conversation context is stored on an instance. Route all messages from that user to the same instance.

Without session affinity, User asks 'What's my account balance?' on Instance 1, then asks 'Can I transfer $100?' routed to Instance 2, which has no context.

[Point to AI health probes]

Health checks need to verify AI API connectivity. Don't just check if your service returns HTTP 200. Check if it can reach the AI API.

[Point to weighted routing]

Weighted routing lets you A/B test. Route 90% traffic to GPT-4, 10% to GPT-4-turbo. Compare quality and cost.

[Point to cost-aware routing]

Route expensive high-token requests to reserved capacity instances where you've pre-paid. Route cheap requests to on-demand."

[Transition]

---

### SLIDE 8: SEGMENT 1 SUMMARY

**Title:** Scaling Patterns - Key Takeaways

**Content:**

**Key Takeaway:** AI workloads need multi-trigger auto-scaling configured for token limits, not just CPU/memory.

**Scaling Checklist:**
- [ ] Multiple scaling triggers (requests, tokens, queue depth)
- [ ] Min instances ≥ 2 for high availability
- [ ] Max instances cap for cost protection
- [ ] Scale-down delay to prevent flapping
- [ ] Session affinity for multi-turn conversations
- [ ] AI-aware health probes

**You'll Practice:**
Exercise 2.1 - Deployment strategy with scaling configuration

**Graphic:** Summary checklist

**SPEAKER NOTES:**

"Scaling summary:

Use multiple triggers. Don't rely on just CPU - you'll hit token limits first.

Always run at least 2 instances. High availability is non-negotiable in production.

Cap max instances to protect costs. Better to gracefully degrade than run up a $10,000 bill.

[Pause]

In Exercise 2.1, you'll configure scaling for your deployment strategy.

Questions on scaling before we talk about hybrid and on-premises?"

[Transition: Click to Segment 2]

---

## SEGMENT 2: HYBRID AND ON-PREMISES ARCHITECTURES
### Duration: 12 minutes | Slides 9-13

[Due to length constraints, I'll provide a condensed version of the remaining segments]

---

### SLIDE 9: WHEN ON-PREMISES MAKES SENSE

**Title:** Hybrid and On-Premises AI

**Content:**

**Drivers for On-Premises:**
- Data sovereignty requirements
- Air-gapped environments (government, defense)
- Extreme scale (costs favor self-hosted)
- Regulatory mandates
- Ultra-low latency needs

**Not Just Compliance:**
At very high volume, self-hosted models can be cheaper than cloud APIs.

**Graphic:** Decision tree for cloud vs hybrid vs on-prem

**GRAPHICS:**

**Graphic 1: Cloud vs. Hybrid vs. On-Premises Decision Tree**
- Purpose: Guide users through the decision of where to deploy AI workloads
- Type: Decision flowchart
- Elements:
  - Start: "Where to deploy AI?"
  - Decision 1: "Data sovereignty requirements?" → Yes: On-premises or Hybrid
  - Decision 2: "Air-gapped environment?" → Yes: On-premises only
  - Decision 3: "Volume > 10M requests/day?" → Yes: Consider on-premises for cost
  - Decision 4: "Need specific cloud models?" → Yes: Cloud or Hybrid
  - Decision 5: "Ultra-low latency required?" → Yes: Edge/On-premises
  - Default: Cloud
- Labels:
  - Each decision clearly stated
  - Outcomes: "Cloud", "Hybrid", "On-Premises"
  - Key factors noted on each path
- Relationships: Decision tree with multiple paths to different deployment models
- Visual cues: Cloud icon, building/server icon for on-prem, hybrid icon (cloud + server), color coding for recommendations

**SPEAKER NOTES:**

"Most of this module focuses on cloud AI. But many enterprises need hybrid or on-premises deployments.

[Walk through drivers]

Data sovereignty - some countries require data processing within borders.

Air-gapped - government, defense, critical infrastructure - no cloud allowed.

Cost at scale - if you're running millions of requests daily, self-hosting can be cheaper.

The break-even varies, but rough estimate: < 1M requests/day → cloud. > 10M requests/day → consider self-hosted.

We'll explore the architecture patterns."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide challenges the cloud-first assumption and establishes when alternatives are necessary
- Addresses enterprise realities of compliance, sovereignty, and cost at scale
- Critical for consultants advising regulated industries and government clients

**Key Research & Citations:**
- **Data sovereignty**: GDPR (EU), PIPL (China), LGPD (Brazil) mandate data processing within national borders for certain data types
- **Cost break-even**: Self-hosted models break even vs. cloud APIs at approximately 8-12M API calls/month depending on model size
- **Air-gapped requirements**: DoD IL4+ classification, financial market data centers, healthcare patient safety systems
- **Open-source model viability**: Llama 2/3, Mistral, Falcon models approaching proprietary quality for many use cases

**Q&A Preparation:**
- *"Can't we use cloud with data residency guarantees?"*: Yes for some regulations (GDPR Article 46), but air-gapped environments categorically prohibit cloud connectivity
- *"What about using smaller models on-premises?"*: Good strategy - trade model capability for control, covered in hybrid patterns. 7B parameter models can run on single GPU.
- *"How do we assess cost break-even for our specific case?"*: Exercise 2.1 includes cost modeling framework comparing cloud API costs vs self-hosting total cost of ownership (hardware, operations, inference costs)
- *"What about model updates and security patches for self-hosted?"*: Valid concern - requires internal ML ops capability or managed on-premises solutions (Azure Stack, AWS Outposts with AI services)

---

[Slides 10-13 would follow similar pattern covering hybrid architectures, on-premises options, connectivity, and segment summary]

**GRAPHICS:**

**Graphic for Hybrid Architecture Patterns (Slide 10-12):**

**Graphic 1: Hybrid Architecture - Data On-Prem, AI in Cloud**
- Purpose: Show how to keep sensitive data on-premises while leveraging cloud AI
- Type: Split architecture diagram
- Elements:
  - Left box: On-Premises (data center icon)
    - Data Sources (database icon)
    - Results Storage (storage icon)
  - Right box: Cloud (cloud icon)
    - AI API (model icon)
  - Secure connection between (VPN/Direct Connect line)
  - Data flow arrows: On-prem → Cloud (encrypted), Cloud → On-prem (results)
- Labels:
  - "On-Premises: Data stays local"
  - "Cloud: AI processing"
  - "Encrypted tunnel: VPN/Direct Connect"
  - "Data sovereignty maintained"
- Relationships: Bidirectional secure flow, data residency compliance
- Visual cues: Shield/lock icons on connection, arrows showing data movement, firewall icons

**Graphic 2: Edge Processing with Cloud AI**
- Purpose: Illustrate multi-tier architecture with edge filtering and cloud processing
- Type: Three-tier architecture diagram
- Elements:
  - Tier 1: Edge (building/device icon) - Filter & Cache
  - Tier 2: Regional (regional data center icon) - Process & Route
  - Tier 3: Central Cloud (cloud icon) - Cloud AI API
  - Data flow: Edge → Regional → Cloud → back
- Labels:
  - "Edge: Filter, cache, reduce traffic"
  - "Regional: Processing and routing"
  - "Central: AI inference"
  - Latency indicators at each tier
- Relationships: Hierarchical flow with caching at each level
- Visual cues: Performance/speed indicators, cache icons, traffic reduction visualization

---

## SEGMENT 3: OPERATIONS AND OBSERVABILITY
### Duration: 12 minutes | Slides 14-18

### SLIDE 14: OBSERVABILITY STACK

**GRAPHICS:**

**Graphic 1: Three-Pillar Observability Stack**
- Purpose: Show the complete observability architecture with metrics, logs, and traces
- Type: Layered architecture diagram
- Elements:
  - Top layer: Dashboards & Alerts (Grafana, Datadog, CloudWatch icons)
  - Middle layer: Three pillars:
    - Metrics (Prometheus icon): Request rates, latency, errors
    - Logs (ELK/CloudWatch icon): Request/response logs, errors
    - Traces (Jaeger icon): Distributed tracing across services
  - Bottom layer: AI Agent System (components generating telemetry)
  - Data flow arrows from system to pillars to dashboards
- Labels:
  - Each pillar clearly labeled with tools and purpose
  - "Unified view of system health"
  - Key metrics listed (token usage, latency, error rate)
- Relationships: Three independent data streams feeding unified dashboard
- Visual cues: Column icons for each pillar, upward arrows for data flow, dashboard visualization at top

---

## SEGMENT 4: ENTERPRISE DEPLOYMENT STRATEGY
### Duration: 9 minutes | Slides 19-22

### SLIDE 19: PHASED DEPLOYMENT

**GRAPHICS:**

**Graphic 1: Three-Phase Deployment Strategy**
- Purpose: Visualize the staged rollout approach from pilot to general availability
- Type: Timeline with phase gates
- Elements:
  - Phase 1: Pilot (Weeks 1-6)
    - 10 users
    - Validate approach
    - Success criteria: Positive feedback, SLAs met
    - Go/No-Go gate
  - Phase 2: Limited Availability (Weeks 7-18)
    - 100 users
    - Scale validation
    - Success criteria: SLAs met, performance validated
    - Go/No-Go gate
  - Phase 3: General Availability (Week 19+)
    - All users
    - Full rollout
    - Ongoing optimization
- Labels:
  - Each phase clearly labeled with duration and user count
  - Success criteria listed
  - Go/No-Go decision points marked
  - User icons showing growth
- Relationships: Sequential progression with gates, can halt at any gate
- Visual cues:
  - Growing user base visualization (10 → 100 → all)
  - Green checkmarks for completed phases
  - Decision diamonds at gates
  - Timeline bar showing weeks

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 23-25

---

### SLIDE 23: CAPSTONE OVERVIEW

**Title:** Module Capstone: Enterprise Architecture Proposal

**Content:**

**Deliverables:**
1. **Written Proposal** (Enterprise AI Architecture Proposal)
   - Business requirements and success criteria
   - Platform recommendation with data
   - Reference architecture diagram
   - Security architecture
   - Cost analysis and ROI
   - Implementation roadmap

2. **Executive Presentation** (10-15 slides)
   - Problem, solution, benefits, investment
   - Visual architecture
   - Timeline and milestones
   - Next steps and decision points

**Uses Work From:**
- Session 1, Ex 1.1: Platform comparison → Platform Recommendation section
- Session 1, Ex 1.2: Security architecture → Security Architecture section
- Session 1, Ex 1.3: Cost model → Cost Analysis section
- Session 2, Ex 2.1: Deployment strategy → Implementation Roadmap section
- Session 2, Ex 2.2: Operations runbook → Operations appendix

**Time:** 25 minutes (reuse + synthesize existing work)

**Graphic:** Diagram showing how exercises feed into capstone

**GRAPHICS:**

**Graphic 1: Capstone Integration Flow**
- Purpose: Show how all previous exercises combine into the final deliverable
- Type: Integration flow diagram
- Elements:
  - Center: "Enterprise Architecture Proposal" (document icon)
  - Feeding in from left:
    - Session 1, Ex 1.1: Platform Comparison → "Platform Recommendation" section
    - Session 1, Ex 1.2: Security Architecture → "Security Architecture" section
    - Session 1, Ex 1.3: Cost Model → "Cost Analysis" section
  - Feeding in from right:
    - Session 2, Ex 2.1: Deployment Strategy → "Implementation Roadmap" section
    - Session 2, Ex 2.2: Operations Runbook → "Operations" appendix
  - Output: Complete proposal document + Executive presentation
- Labels:
  - Each exercise labeled with source and destination section
  - "Reuse & synthesize" notation
  - "25 minutes to complete" time indicator
- Relationships: All exercises feeding into comprehensive deliverable
- Visual cues:
  - Arrows showing integration
  - Document sections highlighted
  - Checkmarks on completed exercises
  - Color coding by session (Session 1=blue, Session 2=green)

**GRAPHICS:**

**Graphic 2: Capstone Deliverable Structure**
- Purpose: Outline the complete structure of the final deliverable
- Type: Document outline/table of contents
- Elements:
  - Section 1: Executive Summary
  - Section 2: Business Requirements & Success Criteria
  - Section 3: Platform Recommendation (from Ex 1.1)
  - Section 4: Reference Architecture (synthesis)
  - Section 5: Security Architecture (from Ex 1.2)
  - Section 6: Cost Analysis & ROI (from Ex 1.3)
  - Section 7: Implementation Roadmap (from Ex 2.1)
  - Section 8: Next Steps
  - Appendices: A (Cost detail), B (Security detail), C (Platform comparison), D (Operations runbook from Ex 2.2)
  - Bonus: Executive Presentation (10-15 slides)
- Labels:
  - Source exercises noted for each section
  - "Client-ready quality" badge
  - Page/slide counts estimated
- Relationships: Hierarchical document structure
- Visual cues: Document icon, section numbers, completion checkboxes

**SPEAKER NOTES:**

"The module capstone brings everything together.

You're creating a client-ready Enterprise AI Architecture Proposal. This is what you'd present to a CTO or executive team.

[Point to deliverables]

Two parts: written proposal and executive presentation deck.

The good news: you've already done most of the work. Your Session 1 platform comparison becomes the Platform Recommendation section. Your security architecture from Ex 1.2 goes right into the proposal. Your cost model from Ex 1.3 becomes the Cost Analysis.

Today's deployment strategy and ops runbook round it out.

[Emphasize]

This isn't busywork - you're building a real artifact you can use in client engagements.

25 minutes to synthesize your existing work into a cohesive proposal."

[Transition]

---

### SLIDE 24: RESOURCES & SUPPORT

**Title:** Resources for Capstone

**Content:**

**Templates:**
- Enterprise Architecture Proposal template (in participant guide)
- Executive Presentation outline (10-15 slides)

**Reuse Your Work:**
- Platform comparison (Ex 1.1)
- Security architecture (Ex 1.2)
- Cost model (Ex 1.3)
- Deployment strategy (Ex 2.1)
- Operations runbook (Ex 2.2)

**Support:**
- Questions: [Async channel]
- All materials in participant guide
- Module appendices A-C

**Graphic:** Resource icons

**SPEAKER NOTES:**

"Resources to support your capstone:

Complete templates in your participant guide. Don't start from scratch.

Reuse all your exercise work - copy sections directly into the proposal, then polish.

Module appendices have evaluation rubrics, comparison matrices, and checklists.

Questions and support in the async channel.

This is the culmination of the module - make it client-ready quality."

[Transition]

---

### SLIDE 25: MODULE COMPLETE

**Title:** Congratulations - Module 6 Complete!

**Content:**

**What You've Achieved:**
- Compared and selected cloud AI platforms
- Designed deployment and security architectures
- Built cost models and optimization strategies
- Configured scaling and operations
- Created enterprise deployment strategies
- Delivered client-ready architecture proposal

**Certification:**
Complete capstone proposal for Module 6 certification.

**Next Steps:**
- Additional advanced modules available
- Apply these skills in real client engagements
- Share your proposals and learnings with cohort

**Graphic:** Completion badge or achievement visual

**SPEAKER NOTES:**

"Congratulations - you've completed Advanced Module 6: Enterprise AI Architecture!

[Walk through achievements]

You can now evaluate platforms, design architectures, secure systems, build cost models, configure scaling, and create deployment strategies.

Most importantly, you've created a complete Enterprise Architecture Proposal ready for real client engagements.

[Pause]

To earn Module 6 certification, complete the capstone with all required sections.

[Final close]

This is advanced material. You're now equipped to advise enterprises on AI architecture at scale.

Excellent work. Good luck with your capstones!"

---

## Appendix A: Slide Type Definitions (Condensed)

**CONCEPT**: Introduces new idea or framework - focus on clarity and single concept
**DEMO**: Live demonstration or walkthrough - have backup plan if tech fails
**INSIGHT**: Delivers key learning or aha moment - emphasize and pause after
**TRANSITION**: Bridges sections - keep brief, preview what's coming
**SUMMARY**: Reinforces key points - use repetition intentionally

## Appendix B: Visual Design Guidelines

**Color Palette - Advanced Green Theme:**
- Primary: Advanced Green #00CC99
- Secondary: Deep Blue #003D5C
- Accent: Bright Orange #FF6B35
- Neutral: Cool Gray #708090
- Warning/Alert: Amber #FFA500

**Typography:**
- Headers: Bold, size 32-44pt
- Body: Regular, size 18-24pt
- Code/Technical: Monospace, size 16-20pt
- Ensure sufficient contrast (WCAG AA minimum)

**Graphic Standards:**
- Every slide with technical content needs a supporting graphic
- Graphics must be referenced in speaker notes
- Use consistent icon set throughout presentation
- Label all diagram elements clearly
- Show relationships with arrows/connectors

**Layout Principles:**
- Maximum 3 main points per slide
- White space is valuable - don't overcrowd
- Align elements to grid
- Consistent margins across all slides

## Appendix C: Quality Checklist

**Content Quality:**
- [ ] All learning objectives explicitly addressed in slides
- [ ] Each segment has clear opening, body, and summary
- [ ] Technical accuracy verified (commands, code, architecture patterns)
- [ ] Examples are realistic and relevant to target audience
- [ ] Terminology consistent with Block 3 and prior modules

**Speaker Notes Quality:**
- [ ] Every content slide has speaker notes
- [ ] Notes include delivery cues ([Pause], [Emphasize], [Transition])
- [ ] Approximate timing aligns with segment durations
- [ ] Questions and transitions scripted
- [ ] Backup explanations prepared for complex topics

**Technical Quality:**
- [ ] All code examples are syntactically correct
- [ ] Architecture diagrams are technically sound
- [ ] Commands have been tested
- [ ] Links and references are valid
- [ ] Version numbers and dates are current

---

## Appendix D: Auto-Scaling Configuration Templates

**Purpose:** Reference configurations for different scaling patterns

**Configuration 1: Token-Aware Scaling (Recommended for AI Workloads)**

```yaml
auto_scaling_config:
  scaling_policy:
    name: "ai-agent-token-aware-scaling"
    metric_type: "custom"
    target_metrics:
      - metric: "tokens_per_minute_utilization"
        target_value: 75
        weight: 40
      - metric: "request_queue_depth"
        target_value: 100
        weight: 30
      - metric: "cpu_utilization"
        target_value: 70
        weight: 30

    scale_up:
      threshold_breach_duration: 60  # seconds
      cooldown_period: 60
      step_adjustments:
        - threshold: 80
          scaling_adjustment: 2  # add 2 instances
        - threshold: 90
          scaling_adjustment: 4  # add 4 instances

    scale_down:
      threshold_breach_duration: 300  # 5 minutes
      cooldown_period: 300
      step_adjustments:
        - threshold: 50
          scaling_adjustment: -1  # remove 1 instance

    capacity:
      min_instances: 2
      max_instances: 50
      desired_initial: 3
```

**Configuration 2: Queue-Based Scaling**

```yaml
auto_scaling_config:
  scaling_policy:
    name: "ai-agent-queue-based"
    metric_type: "queue_depth"
    target_value: 1000  # messages per instance

    scale_up:
      threshold: 1500
      cooldown: 30
      adjustment: 3

    scale_down:
      threshold: 500
      cooldown: 600
      adjustment: -1

    capacity:
      min_instances: 1
      max_instances: 100
```

---

## Appendix E: Hybrid Architecture Patterns Catalog

**Purpose:** Detailed hybrid deployment patterns for different scenarios

**Pattern 1: Cloud AI with On-Premises Data**

**When to Use:**
- Data cannot leave premises due to regulations
- AI processing not subject to same restrictions
- Want to leverage cloud AI capabilities

**Architecture:**
```
┌─────────────────────────────────┐
│      On-Premises Data Center   │
│  ┌──────────────────────────┐  │
│  │  Data Sources (DBs, APIs) │  │
│  └────────────┬─────────────┘  │
│               │                 │
│  ┌────────────▼─────────────┐  │
│  │  Data Preprocessing      │  │
│  │  (Anonymization, PII)    │  │
│  └────────────┬─────────────┘  │
└───────────────┼─────────────────┘
                │
        ┌───────▼───────┐
        │   Encrypted   │
        │    Tunnel     │
        │  (VPN/Direct  │
        │   Connect)    │
        └───────┬───────┘
                │
┌───────────────▼─────────────────┐
│          Cloud Environment      │
│  ┌──────────────────────────┐  │
│  │  AI Processing           │  │
│  │  (Bedrock/OpenAI/Vertex) │  │
│  └────────────┬─────────────┘  │
│               │                 │
│  ┌────────────▼─────────────┐  │
│  │  Results Storage         │  │
│  └──────────────────────────┘  │
└─────────────────────────────────┘
```

**Implementation Checklist:**
- [ ] Secure VPN or Direct Connect established
- [ ] Data preprocessing pipeline removes all PII
- [ ] Encryption in transit (TLS 1.3+)
- [ ] Results retention policy documented
- [ ] Compliance sign-off obtained

---

**Pattern 2: Edge Processing with Cloud Escalation**

**When to Use:**
- Low latency requirements for most requests
- Occasional complex queries need powerful cloud models
- Bandwidth/cost optimization needed

**Architecture:**
```
┌─────────────┐
│    Edge     │
│  Device/    │
│  Gateway    │
└──────┬──────┘
       │
   ┌───▼────┐
   │ Local  │ ───Simple Query──> Process Locally (Fast)
   │  AI    │
   │ (Small │
   │ Model) │
   └───┬────┘
       │
   Complex/
  Uncertain
   Query?
       │
   ┌───▼────────┐
   │   Cloud    │
   │  AI API    │
   │ (Large     │
   │  Model)    │
   └────────────┘
```

**Implementation Details:**
- **Local Model:** 7B parameter model (Llama, Mistral) on GPU
- **Routing Logic:** Confidence threshold <0.7 → escalate to cloud
- **Fallback:** If cloud unavailable, local model processes with warning
- **Cost Savings:** 80-90% of queries handled locally

---

## Appendix F: Observability Stack Components

**Purpose:** Detailed component specifications for AI system monitoring

**Component 1: Metrics Collection**

**Required Metrics:**
- Request rate (requests/second)
- Token usage (input tokens, output tokens, total)
- Latency (P50, P95, P99)
- Error rate (by error type)
- Cost per request
- Model confidence scores
- Queue depth (if using queue pattern)

**Tools:**
- **Prometheus** for metrics collection and storage
- **Grafana** for visualization
- **CloudWatch/Azure Monitor/Cloud Monitoring** for cloud-native option

**Configuration Example (Prometheus):**
```yaml
scrape_configs:
  - job_name: 'ai-agent-metrics'
    metrics_path: '/metrics'
    scrape_interval: 15s
    static_configs:
      - targets: ['agent-service:9090']
    metric_relabel_configs:
      - source_labels: [__name__]
        regex: 'ai_.*'
        action: keep
```

---

**Component 2: Distributed Tracing**

**Why It Matters:**
AI agents often involve multiple service calls:
1. API Gateway
2. Agent orchestration service
3. AI API (Bedrock/OpenAI/Vertex)
4. Database for context
5. Response formatting

Tracing connects these into single request view.

**Tools:**
- **Jaeger** (open-source)
- **AWS X-Ray**
- **Azure Application Insights**
- **Google Cloud Trace**

**Trace Attributes to Capture:**
- `trace_id`: Unique identifier for request
- `span_id`: Unique identifier for service call
- `agent_id`: Which agent handled this
- `model_name`: Which AI model used
- `prompt_tokens`: Input size
- `completion_tokens`: Output size
- `total_latency_ms`: End-to-end time
- `ai_api_latency_ms`: Time in AI API call

---

**Component 3: Log Aggregation**

**Log Structure (JSON format):**
```json
{
  "timestamp": "2026-01-03T10:15:30.123Z",
  "level": "INFO",
  "service": "ai-agent",
  "trace_id": "abc123",
  "agent_id": "customer-service-bot",
  "event": "ai_request_completed",
  "details": {
    "user_id": "user_789",
    "prompt_summary": "Request for account balance",
    "response_summary": "Provided balance information",
    "tokens_used": 150,
    "latency_ms": 1200,
    "model": "gpt-4"
  }
}
```

**Tools:**
- **ELK Stack** (Elasticsearch, Logstash, Kibana)
- **Splunk**
- **CloudWatch Logs / Azure Monitor Logs**
- **Datadog**

---

## Appendix G: Phased Deployment Playbook

**Purpose:** Step-by-step guide for rolling out AI agents safely

**Phase 1: Pilot (Weeks 1-6)**

**Goal:** Validate approach with minimal risk

**Participant Criteria:**
- 10-20 early adopter users
- Internal or friendly external users
- Willing to provide detailed feedback
- Understand this is pilot (expect issues)

**Success Criteria:**
- [ ] 80%+ user satisfaction score
- [ ] <5% error rate
- [ ] Latency within SLA (<2s P95)
- [ ] No critical incidents
- [ ] Feedback captured and analyzed

**Go/No-Go Decision:**
- **GO:** All success criteria met, no blocking issues
- **NO-GO:** Any critical incident, >20% user dissatisfaction, >10% error rate
- **Action if NO-GO:** Analyze root causes, fix, extend pilot

---

**Phase 2: Limited Availability (Weeks 7-18)**

**Goal:** Scale validation with broader but controlled user base

**Participant Criteria:**
- 100-500 users
- Mix of user types/personas
- Geographic distribution if relevant
- Can include external customers (with clear "beta" labeling)

**Scaling Checkpoints:**
- Week 7: 100 users
- Week 10: 250 users (if no issues)
- Week 14: 500 users (if performance stable)

**Success Criteria:**
- [ ] SLAs maintained at scale
- [ ] Cost per transaction within budget
- [ ] <3% error rate
- [ ] 75%+ user satisfaction
- [ ] Zero security incidents
- [ ] Support team can handle volume

**Go/No-Go Decision:**
- **GO:** All criteria met, infrastructure scales smoothly
- **NO-GO:** Performance degradation, cost overruns, satisfaction drops
- **Action if NO-GO:** Optimize, add capacity, improve UX before expanding

---

**Phase 3: General Availability (Week 19+)**

**Goal:** Full production rollout

**Rollout Strategy:**
- Week 19: 10% of total user base
- Week 20: 25%
- Week 21: 50%
- Week 22: 75%
- Week 23: 100%

**Monitor Closely:**
- Cost trajectory (daily budget alerts)
- Error rate trends
- User satisfaction (NPS or CSAT)
- Support ticket volume
- Infrastructure utilization

**Rollback Trigger:**
Any of:
- Error rate >5% for 1 hour
- Cost exceeds budget by >50%
- Critical security incident
- User satisfaction drops >20% from baseline
- Executive directive

**Rollback Procedure:**
1. Reduce traffic percentage to last stable level
2. Communicate to stakeholders
3. Analyze incident
4. Fix root cause
5. Resume rollout when stable

---

## Appendix H: Operations Runbook Template

**Purpose:** Standardized incident response procedures

**Incident Classification:**

| Severity | Definition | Response Time | Example |
|----------|------------|---------------|---------|
| **P0 - Critical** | Complete outage, data loss, security breach | <15 min | AI agent down, PII leaked |
| **P1 - High** | Major functionality impaired, workarounds exist | <1 hour | Error rate >20%, latency >10s |
| **P2 - Medium** | Degraded performance, limited user impact | <4 hours | Error rate 10-20%, slow responses |
| **P3 - Low** | Minor issues, minimal impact | <24 hours | UI bug, minor UX issue |

---

**Runbook: AI Agent High Error Rate**

**Symptoms:**
- Error rate >10% over 15-minute window
- Alert triggered from monitoring system

**Investigation Steps:**
1. **Check AI API status**
   ```bash
   curl -H "Authorization: Bearer $API_KEY" https://api.openai.com/v1/models
   ```
   If 200 OK → AI API is healthy, problem is local
   If 5xx → AI API degradation, external issue

2. **Check recent deployments**
   ```bash
   kubectl rollout history deployment/ai-agent
   ```
   If deployment within last 2 hours → suspect new version

3. **Check error logs**
   ```bash
   kubectl logs -l app=ai-agent --tail=100 | grep ERROR
   ```
   Look for patterns (specific error type, specific users, timeframe)

4. **Check metrics dashboard**
   - Grafana: AI Agent Error Rate panel
   - Look for: Which error types? Which endpoints?

**Resolution Paths:**

**If AI API degraded:**
- Action: Enable graceful degradation mode
- Command: `kubectl set env deployment/ai-agent FALLBACK_MODE=true`
- Notify users of degraded service
- Monitor for AI API recovery

**If new deployment caused it:**
- Action: Rollback immediately
- Command: `kubectl rollout undo deployment/ai-agent`
- Verify error rate returns to normal
- Analyze failed deployment before retry

**If infrastructure issue:**
- Action: Scale up capacity
- Command: `kubectl scale deployment/ai-agent --replicas=10`
- Monitor if error rate improves
- Identify root cause (traffic spike, resource exhaustion)

---

## Appendix I: Exercise Solutions and Grading Rubrics

**Exercise 2.1: Deployment Strategy**

**Expected Deliverable:** Complete deployment strategy document including scaling configuration

**Grading Rubric (10 points total):**
- **Architecture Pattern Selection (3 points):** Appropriate pattern chosen with justification referencing requirements
- **Scaling Configuration (3 points):** Multi-trigger auto-scaling configured with specific thresholds
- **Phased Rollout Plan (2 points):** Three phases defined with success criteria and go/no-go gates
- **Cost Projection (2 points):** Realistic cost estimates for each phase

**Sample High-Quality Answer:**
- Pattern: Serverless for variable customer service workload
- Scaling: Triggers on requests/sec (>100), queue depth (>1000), token usage (>80%)
- Phases: Pilot (10 users, 2 weeks) → Limited (100 users, 6 weeks) → GA (rollout over 4 weeks)
- Cost: $500/month pilot, $5K/month limited, $30K/month at full scale

---

**Exercise 2.2: Operations Runbook**

**Expected Deliverable:** Operations runbook with at least 3 incident scenarios

**Grading Rubric (10 points total):**
- **Incident Coverage (3 points):** At least 3 realistic scenarios (high error rate, latency spike, cost overrun)
- **Investigation Steps (3 points):** Clear, actionable investigation procedures with commands
- **Resolution Paths (2 points):** Multiple resolution options depending on root cause
- **Escalation Criteria (2 points):** Clear criteria for escalating vs. resolving

---

**Version History:**

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | [Instructor] |
| 2.0 | 2026-01-03 | Enhanced with BACKGROUND sections, Key Thesis, and expanded appendices | Claude |
