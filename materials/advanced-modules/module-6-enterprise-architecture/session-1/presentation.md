# **POWERPOINT PRESENTATION: ADVANCED MODULE 6, SESSION 1**
## **Cloud AI Architecture Patterns**

**Module:** Advanced Module 6: Enterprise AI Architecture
**Session Number:** 1 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 graduates who advise clients on AI platform selection, deployment architecture, and enterprise-scale AI agent implementations.

**Key Thesis:** Cloud AI platform selection requires structured evaluation across multiple weighted factors rather than seeking a universal "best" choice, because the right platform depends entirely on client context including existing infrastructure, specific model requirements, compliance needs, and operational constraints.

**Session Learning Objectives:** By the end of this session, participants will:
1. Evaluate and compare major cloud AI platforms (AWS Bedrock, Azure OpenAI, Google Vertex AI)
2. Design appropriate deployment architecture patterns for different enterprise scenarios
3. Apply defense-in-depth security principles to AI systems
4. Create platform selection decision frameworks using weighted scoring models

**Entry Criteria:**
- [ ] Block 3 completed with working agent system
- [ ] Access to at least one cloud platform (trial acceptable)
- [ ] Understanding of basic networking concepts
- [ ] Familiarity with API authentication patterns

**Exit Criteria:**
- [ ] Major cloud AI platforms compared and understood
- [ ] Platform selection framework created
- [ ] Security architecture patterns documented
- [ ] First architecture diagram completed
- [ ] Cost model template populated

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: Cloud AI Platform Landscape (12 min) - Slides 4-8
3. Segment 2: Deployment Architecture Patterns (12 min) - Slides 9-13
4. Segment 3: Security Architecture Fundamentals (12 min) - Slides 14-18
5. Segment 4: Platform Selection Decision Framework (9 min) - Slides 19-22
6. Homework Preview & Close (3 min) - Slides 23-25

**Total Slides:** 25

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Advanced Module 6, Session 1: Cloud AI Architecture Patterns

**Subtitle:** Platform Selection, Deployment Patterns, and Security for Enterprise AI

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program

**Graphic:** Clean title slide with program branding. Advanced module color scheme (purple/silver tones for enterprise/advanced topics).

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Advanced Module 6: Enterprise AI Architecture. Over the next two sessions, we'll be moving from building AI agents to deploying them at enterprise scale.

This is an advanced module, so you've all completed Block 3 and have working agent systems. Now we're addressing the question: how do you take that agent from your laptop and deploy it for an organization with hundreds or thousands of users?

Today's session focuses on Cloud AI Architecture Patterns - we'll compare the major platforms, explore deployment architectures, and build the frameworks you need to advise clients on platform selection and architecture design.

Let's get started."

[Transition: Click to next slide]

---

### SLIDE 2: SESSION OVERVIEW

**Title:** This Session's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Preview & Setup |
| 3-15 min | Segment 1 | Cloud AI Platform Landscape |
| 15-27 min | Segment 2 | Deployment Architecture Patterns |
| 27-39 min | Segment 3 | Security Architecture Fundamentals |
| 39-48 min | Segment 4 | Platform Selection Framework |
| 48-51 min | Close | Homework & Resources |

**Graphic:** Simple timeline showing the session flow

**SPEAKER NOTES:**

"Here's what we'll cover in the next 45 minutes:

First, we'll compare the Big Three cloud AI platforms - AWS Bedrock, Azure OpenAI, and Google Vertex AI. You need to understand their strengths, limitations, and when to recommend each.

Then we'll explore three core deployment architecture patterns - serverless, containerized, and queue-based. Each has specific use cases and trade-offs.

In our third segment, we'll design security architectures using defense-in-depth principles. Enterprise AI has unique security considerations beyond traditional applications.

Finally, we'll build a platform selection decision framework you can use in client engagements.

[Pause]

This is a lot to cover, so we're moving quickly. All details are in your participant guide for deeper study."

[Transition]

---

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Evaluate and compare major cloud AI platforms**
   - AWS Bedrock, Azure OpenAI, Google Vertex AI feature analysis

2. **Design deployment architecture patterns**
   - Serverless, containerized, and queue-based patterns for different scenarios

3. **Apply defense-in-depth security principles**
   - Network, identity, application, data, and monitoring layers

4. **Create platform selection frameworks**
   - Weighted scoring models and decision trees for client recommendations

**Graphic:** Checklist visual with the four objectives

**SPEAKER NOTES:**

"These are our four objectives for today. Notice they're all action-focused:

You'll EVALUATE platforms using specific comparison criteria.
You'll DESIGN architectures that match client requirements.
You'll APPLY security principles to real scenarios.
You'll CREATE decision frameworks you can use in your next client engagement.

[Point to first objective]

This first one is critical - your clients will ask 'Which platform should we use?' You need a structured way to answer that question.

In your homework, you'll practice all four of these skills with realistic client scenarios."

[Transition: Click to Segment 1]

---

## SEGMENT 1: CLOUD AI PLATFORM LANDSCAPE
### Duration: 12 minutes | Slides 4-8

---

### SLIDE 4: THE BIG THREE - OVERVIEW

**Title:** Cloud AI Platform Landscape

**Content:**

**The Challenge:**
Your client asks: "Which cloud AI platform should we use?" They have existing cloud infrastructure, specific model needs, compliance requirements, and budget constraints.

**Why It Matters:**
- Platform choice impacts costs, capabilities, and vendor lock-in
- Wrong choice creates technical debt and migration headaches
- Decision affects team productivity and feature velocity

**Graphic:** Logos of AWS Bedrock, Azure OpenAI, Google Vertex AI with question marks between them

**GRAPHICS:**

**Graphic 1: Platform Selection Challenge**
- Purpose: Visualize the complexity of choosing between major cloud AI platforms
- Type: Decision diagram with platform logos
- Elements:
  - Center: Large question mark with "Which Platform?" text
  - Three branches radiating out to platform logos:
    - AWS Bedrock (orange logo)
    - Azure OpenAI (blue logo)
    - Google Vertex AI (multi-color logo)
  - Decision factors floating around: "Cost?", "Models?", "Integration?", "Compliance?"
- Labels:
  - Platform names clearly labeled
  - Key decision criteria as question bubbles
  - "No universal 'best' choice" caption
- Relationships: Equal distance from center indicating no inherent preference, arrows pointing both ways showing comparison needed
- Visual cues: Question mark emphasizing uncertainty, balanced layout showing need for structured evaluation

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Let me start with a question: How many of you have been asked by a client or your organization which cloud AI platform to use?

[Pause - show of hands]

This is one of the most common questions in enterprise AI right now. And the stakes are high - this decision impacts everything from monthly costs to team productivity to long-term vendor lock-in.

The reality is there's no universal 'best' platform. The right choice depends on your client's specific context.

Today we're going to build the framework you need to make this recommendation confidently."

[Transition]

**BACKGROUND:**

**Rationale:**
- Establishes the real-world consulting problem that practitioners immediately face
- Creates urgency around getting this decision right before implementation
- Sets up the need for a structured evaluation approach rather than vendor marketing

**Key Research & Citations:**
- **AWS Bedrock (2023)**: Widest model selection including Claude, Llama, Titan families - enables multi-model strategies
- **Azure OpenAI (2023)**: Exclusive access to OpenAI GPT-4 models in enterprise contexts with Microsoft infrastructure integration
- **Google Vertex AI (2023)**: Gemini and PaLM models with strong GCP integration but varying regional availability

**Q&A Preparation:**
- *"Can't we just use whatever we already have?"*: Existing infrastructure is one of six factors, weighted at typically 20%. Integration benefits are real but shouldn't override model requirements or compliance needs.
- *"What about smaller providers like Cohere or Anthropic direct?"*: We're focusing on the Big Three for enterprise scale and feature completeness, but the weighted scoring framework applies to any platform comparison.
- *"What if requirements change after selection?"*: Multi-cloud strategies exist but add operational complexity - better to build abstraction layers that enable platform portability if this is a concern.

---

### SLIDE 5: PLATFORM COMPARISON - CAPABILITIES

**Title:** The Big Three - Capability Comparison

**Content:**

| Capability | AWS Bedrock | Azure OpenAI | Google Vertex AI |
|------------|-------------|--------------|------------------|
| **Model Access** | Claude, Llama, Titan | GPT-4, GPT-3.5 | Gemini, PaLM, Claude |
| **Fine-tuning** | Select models | GPT-3.5-turbo | Most models |
| **Agents** | Bedrock Agents | Assistants API | Vertex AI Agents |
| **RAG Support** | Knowledge Bases | Azure AI Search | Vertex AI Search |
| **Enterprise SSO** | IAM, SAML | Entra ID native | Cloud IAM |
| **Compliance** | FedRAMP, HIPAA | FedRAMP, HIPAA | FedRAMP, HIPAA |

**Graphic:** Comparison table with color coding for strengths

**GRAPHICS:**

**Graphic 1: Cloud AI Platform Capabilities Matrix**
- Purpose: Provide side-by-side comparison of key capabilities across the Big Three platforms
- Type: Comparison matrix/table
- Elements:
  - Row headers: Model Access, Fine-tuning, Agents, RAG Support, Enterprise SSO, Compliance
  - Column headers: AWS Bedrock, Azure OpenAI, Google Vertex AI
  - Each cell filled with capability details from the table
- Labels:
  - Platform logos in column headers
  - Capability categories in row headers
  - Checkmarks for full support, partial for limited support
- Relationships: Side-by-side comparison enabling quick evaluation
- Visual cues:
  - Green highlighting for strongest capabilities
  - Yellow for moderate capabilities
  - Icons: checkmark (supported), star (best-in-class), tilde (limited)
  - Model names in bold (GPT-4, Claude, Gemini)
  - Color coding: AWS=orange accents, Azure=blue accents, Google=multi-color accents

**SPEAKER NOTES:**

"[INSIGHT - Deliver comparison framework]"

"Here's the high-level comparison. Let me highlight the key differentiators:

Model Access: If your client specifically needs GPT-4, Azure OpenAI is the only option. If they want Claude, Bedrock or Vertex. If they need flexibility across multiple models, Bedrock has the widest selection.

Fine-tuning: Azure and Vertex offer more fine-tuning options. Bedrock is more limited here.

Agent capabilities: All three have built agent frameworks, but they're implemented differently. Bedrock Agents, Azure Assistants API, and Vertex AI Agents each have different strengths.

[Point to compliance row]

Notice all three meet major compliance standards - this levels the playing field for regulated industries.

The key insight: model availability is often the first decision filter."

[Transition]

**BACKGROUND:**

**Key Research & Citations:**
- Platform documentation as of 2026-01
- All platforms continuously adding models and features
- Regional availability varies

**Implementation Guidance:**

**Getting Started:**
- Always check current regional availability for specific models
- Trial accounts available for all three platforms

**Common Pitfalls:**
- Assuming model availability is static - it changes frequently
- Overlooking regional restrictions for specific models

---

### SLIDE 6: PLATFORM SELECTION FACTORS

**Title:** Platform Selection Framework

**Content:**

**Six Key Factors:**

1. **Existing cloud footprint** - Integration ease, team skills
2. **Model requirements** - Specific models vs flexibility
3. **Compliance needs** - Data residency, certifications
4. **Team expertise** - Learning curve, training investment
5. **Integration points** - Existing services, data sources
6. **Pricing structure** - Cost model alignment with usage patterns

**Multi-cloud considerations:**
- When multiple platforms make sense
- Abstraction layers for portability
- Complexity vs flexibility trade-offs

**Graphic:** Six-pointed star diagram with factors, or decision matrix

**GRAPHICS:**

**Graphic 1: Platform Selection Six-Factor Framework**
- Purpose: Show the six key factors that should drive platform selection decisions
- Type: Hexagonal radar/star diagram
- Elements:
  - Center point representing the platform decision
  - Six axes radiating outward:
    1. Existing Cloud Footprint
    2. Model Requirements
    3. Compliance Needs
    4. Team Expertise
    5. Integration Points
    6. Pricing Structure
  - Each axis can be scored/weighted
- Labels:
  - Each factor clearly labeled on its axis
  - Brief descriptor for each (e.g., "Model Requirements: Specific models vs. flexibility")
  - Weight percentages can be shown
- Relationships: Interconnected factors all contributing to central decision
- Visual cues: Star/hexagon shape showing balanced consideration, could overlay different platform scores for comparison

**SPEAKER NOTES:**

"When evaluating platforms, you need to consider six key factors:

[Walk through each factor]

Existing cloud footprint is huge - if your client is already on Azure with Entra ID, Active Directory, and Azure SQL, the integration story for Azure OpenAI is compelling.

Model requirements often narrow the field immediately. Need GPT-4? Azure. Want Claude with the widest model selection? Bedrock.

[Point to multi-cloud section]

Should you use multiple platforms? Sometimes yes - for example, using Bedrock for Claude and Azure for GPT-4. But this adds operational complexity. You need abstraction layers and solid reasons to justify multi-cloud AI.

The key is weighting these factors based on client priorities."

[Transition to next slide]

**BACKGROUND:**

**Implementation Guidance:**

**When Multi-Cloud Makes Sense:**
- Need specific models from different providers
- Geographic redundancy requirements
- Strategic vendor diversification

**When to Avoid Multi-Cloud:**
- Small team without multi-cloud expertise
- Limited operational capacity
- Cost optimization is primary goal

---

### SLIDE 7: LIVE DEMO - PLATFORM COMPARISON

**Title:** Demo: Weighted Scoring Model

**Content:**

**Demo Scenario:**
Healthcare client needs HIPAA-compliant AI for clinical documentation. Current Azure shop, needs GPT-4, budget-conscious.

**Watch For:**
- How existing infrastructure weights the decision
- Model requirement as a filter
- Compliance as table stakes
- Final weighted score calculation

**Graphic:** Screenshot of weighted scoring spreadsheet or template

**SPEAKER NOTES:**

"[DEMO - Show, don't tell]"

"Let me show you how to apply a weighted scoring model to a real scenario.

[Share screen with scoring template]

Our client is a healthcare organization. They need HIPAA compliance - that's table stakes. They're already on Azure with significant investment in Entra ID and Azure infrastructure. They specifically need GPT-4 for clinical documentation.

[Fill in scoring template]

Model availability: Azure scores 10/10 because they need GPT-4. Bedrock and Vertex score lower.

Existing integration: Azure scores 10/10 - they're already there. AWS and GCP score 3/10.

[Continue scoring]

Notice how we're applying weights. Model availability is 25% - critical but not everything. Existing integration is 20%.

[Show final calculation]

Azure wins with a weighted score of 8.7. But look - if they didn't specifically need GPT-4, this would be different.

The key is documenting WHY you scored each platform the way you did."

[Pause]

"Questions about the scoring approach?"

**BACKGROUND:**

**Demo Backup Plan:**
If live demo fails:
1. Use prepared screenshot showing completed scoring
2. Walk through the logic conceptually
3. Reference template in participant guide

**Timing Note:**
- Demo should take 4-5 minutes maximum
- Focus on the weighting and calculation logic
- Don't get stuck on specific scores - it's the process that matters

---

### SLIDE 8: SEGMENT 1 SUMMARY

**Title:** Cloud Platform Landscape - Key Takeaways

**Content:**

**Key Takeaway:** Platform selection requires structured evaluation using multiple weighted factors, not just "which is best?"

**Remember:**
- Model availability often narrows the field first
- Existing infrastructure significantly impacts total cost of ownership
- All three platforms meet major compliance requirements
- Document your scoring rationale for client buy-in

**You'll Practice:**
Exercise 1.1 - Platform Comparison Analysis for specific client scenario

**Graphic:** Simple checklist or summary icon

**SPEAKER NOTES:**

"Before we move on, key points:

There is no universal 'best' platform. The right choice depends on client context.

Model availability is often your first filter - if they need GPT-4, you're looking at Azure.

[Emphasize this point]

Existing infrastructure matters more than many people realize. Integration costs, team training, and operational complexity can dwarf the per-token API costs.

In Exercise 1.1 today, you'll apply this framework to a realistic client scenario and produce a complete platform comparison with weighted scoring.

[Pause]

Questions before we move to deployment architectures?"

[Transition: Click to Segment 2]

---

## SEGMENT 2: DEPLOYMENT ARCHITECTURE PATTERNS
### Duration: 12 minutes | Slides 9-13

---

### SLIDE 9: DEPLOYMENT PATTERNS - THE CHALLENGE

**Title:** How Do We Actually Deploy This?

**Content:**

**The Challenge:**
You've selected a platform. Now your client asks: "What's the actual architecture? How do we deploy this for 10,000 users?"

**Architecture Requirements:**
- Scale from 100 to 100,000 users
- Handle variable workload patterns
- Maintain acceptable latency
- Control costs as usage grows
- Ensure reliability and fault tolerance

**Graphic:** Simple diagram showing user load increasing over time with architecture question mark

**GRAPHICS:**

**Graphic 1: Scaling Challenge Visualization**
- Purpose: Illustrate the problem of scaling from prototype to enterprise production
- Type: Growth chart with architecture question
- Elements:
  - X-axis: Time (Prototype → Production)
  - Y-axis: Users (100 → 100,000)
  - Growth curve showing exponential increase
  - Laptop icon at start (prototype)
  - Large question mark at end: "How to deploy?"
  - Requirements bubbles: "Scale", "Reliability", "Cost Control", "Low Latency"
- Labels:
  - "100 users" at start
  - "100,000 users" at end
  - "Architecture decision point" at inflection
  - Key requirements listed
- Relationships: User growth creating pressure for architectural decision
- Visual cues: Steep growth curve, concern/challenge indicators, scaling arrows

**SPEAKER NOTES:**

"Selecting a platform was step one. Now you need to design the actual deployment architecture.

[Rhetorical question]

How do you take an AI agent from a prototype on your laptop to a production system serving thousands of users?

This is where many enterprise AI projects struggle. They have a working agent, but no clear path to production deployment.

[Point to requirements]

Your architecture needs to handle all of these requirements. And the trade-offs are real - the best architecture for cost optimization may not be the best for latency.

We're going to look at three proven deployment patterns. Each solves different problems."

[Transition]

**BACKGROUND:**

**Rationale:**
- Connects platform selection to practical deployment
- Establishes that architecture choice has significant business impact
- Sets up the need for pattern-based thinking

---

### SLIDE 10: PATTERN 1 - SERVERLESS ARCHITECTURE

**Title:** Serverless Agent Architecture

**Content:**

**Architecture Diagram:**
```
┌─────────────────────────────────────┐
│         API Gateway                 │
│    (Rate limiting, Auth)            │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│     Lambda/Cloud Function           │
│  (Agent Orchestration Logic)        │
└──────────────┬──────────────────────┘
               │
   ┌───────────┼───────────┐
   ▼           ▼           ▼
┌──────┐  ┌─────────┐  ┌─────┐
│ AI   │  │DynamoDB │  │ S3  │
│ API  │  │ (State) │  │Files│
└──────┘  └─────────┘  └─────┘
```

**Best For:**
- Variable workloads
- Cost optimization
- Rapid scaling

**Limitations:**
- Cold starts (latency spikes)
- Execution time limits
- Stateless complexity

**Graphic:** Architecture diagram as shown

**GRAPHICS:**

**Graphic 1: Serverless Agent Architecture Diagram**
- Purpose: Show the complete serverless deployment pattern with all components and data flow
- Type: Technical architecture diagram
- Elements:
  - Top layer: API Gateway (icon) - entry point for requests
  - Middle layer: Lambda/Cloud Function (icon) - execution environment
  - Bottom layer: Three parallel services:
    - AI API (Bedrock/OpenAI/Vertex icon)
    - DynamoDB/NoSQL (database icon) for state
    - S3/Object Storage (storage icon) for files
  - Request/response flow arrows
- Labels:
  - "API Gateway: Rate limiting, Auth"
  - "Lambda/Cloud Function: Agent Orchestration Logic"
  - "AI API: Model inference"
  - "DynamoDB: State persistence"
  - "S3: File storage"
  - "Best for: Variable workloads, cost optimization"
  - "Limitations: Cold starts, execution time limits"
- Relationships: Request flow from top to bottom, parallel access to three backend services
- Visual cues: Cloud icons, serverless lightning bolts, arrows showing data flow, color coding (API Gateway=orange, compute=blue, storage=green)

**SPEAKER NOTES:**

"Pattern 1 is serverless architecture. Here's how it works:

[Walk through diagram]

Requests come through API Gateway - this gives you rate limiting, authentication, and request validation.

Lambda or Cloud Functions handle the agent orchestration. They spin up on demand, run your agent logic, and shut down.

State goes to DynamoDB or similar. Files to S3. AI API calls to Bedrock, Azure OpenAI, or Vertex.

[Point to Best For section]

This pattern excels when your workload is variable. If you have 100 requests at 9 AM and 10,000 at 2 PM, serverless scales automatically and you only pay for what you use.

[Point to Limitations]

But watch out for cold starts. The first request after idle time can take 2-5 seconds while Lambda spins up. For some use cases, that's unacceptable.

Also, Lambda has execution time limits - typically 15 minutes max. If your agent workflow takes longer, this won't work."

[Transition]

---

### SLIDE 11: PATTERN 2 - CONTAINERIZED ARCHITECTURE

**Title:** Containerized Agent Architecture

**Content:**

**Architecture Diagram:**
```
┌─────────────────────────────────────┐
│        Load Balancer                │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│      Kubernetes Cluster             │
│  ┌──────┐  ┌──────┐  ┌──────┐      │
│  │Agent │  │Agent │  │Agent │      │
│  │Pod 1 │  │Pod 2 │  │Pod 3 │      │
│  └──────┘  └──────┘  └──────┘      │
└──────────────┬──────────────────────┘
               │
   ┌───────────┼───────────┐
   ▼           ▼           ▼
┌──────┐  ┌─────────┐  ┌──────────┐
│ AI   │  │ Redis   │  │Postgres  │
│ API  │  │(Cache)  │  │ (State)  │
└──────┘  └─────────┘  └──────────┘
```

**Best For:**
- Consistent performance
- Complex orchestration
- Long-running tasks

**Limitations:**
- Higher baseline cost
- Operational complexity

**Graphic:** Architecture diagram as shown

**GRAPHICS:**

**Graphic 1: Containerized Agent Architecture Diagram**
- Purpose: Show the Kubernetes-based deployment pattern with container orchestration
- Type: Technical architecture diagram
- Elements:
  - Top layer: Load Balancer (icon) distributing traffic
  - Middle layer: Kubernetes Cluster (large box containing):
    - Agent Pod 1 (container icon)
    - Agent Pod 2 (container icon)
    - Agent Pod 3 (container icon)
  - Bottom layer: Three parallel services:
    - AI API (cloud icon)
    - Redis (cache icon)
    - Postgres (database icon)
  - Traffic distribution arrows from load balancer to pods
  - Data access arrows from pods to backend services
- Labels:
  - "Load Balancer: Traffic distribution"
  - "Kubernetes Cluster: Container orchestration"
  - "Agent Pods: Always-on, consistent performance"
  - "AI API: Model inference"
  - "Redis: Response caching"
  - "Postgres: State persistence"
  - "Best for: Consistent performance, complex orchestration"
  - "Limitations: Higher baseline cost, operational complexity"
- Relationships: Load balancer distributes to multiple pods, pods access shared backend services
- Visual cues: Container/pod icons, K8s logo, arrows showing load distribution and data flow

**SPEAKER NOTES:**

"Pattern 2 is containerized architecture using Kubernetes.

[Walk through diagram]

Load balancer distributes traffic across agent pods. Each pod is a running container with your agent code.

This gives you consistent performance - no cold starts. Pods are always running and ready to handle requests.

You can run complex multi-agent orchestration. State goes to Postgres for transactional data, Redis for caching.

[Point to Best For]

Use this when you need consistent low latency, when you're running complex multi-agent workflows, or when agent tasks take longer than serverless allows.

[Point to Limitations]

Trade-off: you're paying for those pods 24/7, even when idle. Minimum 3 pods for high availability means higher baseline cost than serverless.

Plus Kubernetes operational complexity - you need someone who knows how to run a K8s cluster."

[Transition]

---

### SLIDE 12: PATTERN 3 - QUEUE-BASED ARCHITECTURE

**Title:** Queue-Based Processing Architecture

**Content:**

**Architecture Diagram:**
```
┌─────────┐   ┌─────────────┐   ┌─────────────┐
│  API    │──▶│   Queue     │──▶│Worker Pool  │
│ Gateway │   │ (SQS/Pub)   │   │(Agent Fleet)│
└─────────┘   └─────────────┘   └─────────────┘
     │                                  │
     │         ┌─────────────┐          │
     └────────▶│  Status DB  │◀─────────┘
               └─────────────┘
```

**Best For:**
- Batch processing
- Rate limiting
- Async workflows

**Limitations:**
- Not suitable for real-time needs
- Status tracking complexity

**Graphic:** Architecture diagram as shown

**GRAPHICS:**

**Graphic 1: Queue-Based Processing Architecture Diagram**
- Purpose: Show the asynchronous queue-based pattern for batch processing
- Type: Technical architecture diagram
- Elements:
  - Left: API Gateway (icon) - request entry point
  - Middle: Queue/Message Broker (SQS/Pub/Sub icon)
  - Right: Worker Pool/Agent Fleet (multiple worker icons)
  - Bottom center: Status Database (database icon)
  - Bidirectional arrows showing workflow
- Labels:
  - "API Gateway: Immediate response with request ID"
  - "Queue (SQS/Pub/Sub): Work buffer"
  - "Worker Pool: Agent fleet processing tasks"
  - "Status DB: Job status tracking"
  - "Client polls status or receives webhook"
  - "Best for: Batch processing, rate limiting, async workflows"
  - "Limitations: Not suitable for real-time, status tracking complexity"
- Relationships:
  - Request → Queue → Workers (asynchronous flow)
  - Workers update Status DB
  - API Gateway reads Status DB for status queries
- Visual cues: Queue icon (stacked items), worker icons (gears/processors), async arrows (dashed), status indicators

**SPEAKER NOTES:**

"Pattern 3 is queue-based processing.

[Walk through diagram]

Requests go to API Gateway, which immediately returns a request ID and queues the work.

Worker agents pull from the queue, process tasks, and update status in the database.

Client polls status DB or receives webhook when complete.

[Point to Best For]

This is perfect for batch processing - document analysis, bulk data processing, anything that doesn't need immediate response.

It also gives you natural rate limiting. If you get 10,000 requests at once, they queue up and process at the rate your worker pool can handle.

[Point to Limitations]

But this is async - if users need immediate responses, this doesn't work. And status tracking adds complexity - you need polling or webhooks."

[Transition]

---

### SLIDE 13: SEGMENT 2 SUMMARY

**Title:** Deployment Patterns - Key Takeaways

**Content:**

**Key Takeaway:** Choose deployment pattern based on workload characteristics, latency requirements, and operational constraints - not on what's "best."

**Pattern Selection Guide:**
- Variable workload + cost focus → Serverless
- Consistent latency + complex workflows → Containerized
- Batch processing + rate limiting → Queue-based

**Remember:**
- Hybrid approaches are common
- Start simple, add complexity as needed
- Operational expertise matters as much as technical fit

**You'll Practice:**
Exercise 1.2 - Security Architecture Design using selected pattern

**Graphic:** Decision tree or comparison matrix

**GRAPHICS:**

**Graphic 1: Deployment Pattern Selection Guide**
- Purpose: Help users quickly choose the right deployment pattern for their needs
- Type: Decision matrix with visual quick-reference
- Elements:
  - Three columns for Serverless, Containerized, Queue-based
  - Rows for: Workload Type, Latency Needs, Cost Model, Complexity, Best Use Case
  - Visual indicators (thumbs up/down, stars) for each combination
- Labels:
  - Serverless: "Variable workload ⭐", "Cost-conscious ⭐", "Cold starts OK"
  - Containerized: "Consistent latency ⭐", "Complex workflows ⭐", "Higher baseline cost"
  - Queue-based: "Batch processing ⭐", "Async OK ⭐", "Real-time ✗"
- Relationships: Side-by-side comparison enabling quick pattern selection
- Visual cues: Green checkmarks for ideal fits, yellow for acceptable, red X for poor fits, star ratings for strength in category

**SPEAKER NOTES:**

"Key takeaways on deployment patterns:

[Emphasize this]

There's no universal 'best' pattern. The right choice depends on your specific requirements.

[Point to selection guide]

Use this as a starting heuristic. Variable workload and cost-conscious? Start with serverless. Need consistent low latency? Containerized. Batch processing? Queue-based.

In reality, many production systems use hybrid approaches. Maybe serverless for the API layer with queue-based processing for heavy workloads.

[Pause]

The most common mistake is over-engineering too early. Start with the simplest pattern that meets requirements.

Questions before we talk about security?"

[Transition: Click to Segment 3]

---

## SEGMENT 3: SECURITY ARCHITECTURE FUNDAMENTALS
### Duration: 12 minutes | Slides 14-18

---

### SLIDE 14: SECURITY - THE STAKES

**Title:** AI Security is Different

**Content:**

**Unique AI Security Challenges:**
- Prompt injection attacks
- Training data exposure
- Model output manipulation
- PII leakage in prompts and responses
- Compliance logging requirements

**Why Traditional Security Isn't Enough:**
Enterprise AI systems need AI-specific security controls beyond traditional application security.

**Graphic:** Comparison showing traditional app vs AI app attack vectors

**GRAPHICS:**

**Graphic 1: Traditional vs. AI Security Threats**
- Purpose: Highlight the unique security challenges specific to AI systems
- Type: Side-by-side comparison diagram
- Elements:
  - Left side: Traditional App attack vectors (SQL injection, XSS, CSRF, etc.)
  - Right side: AI-specific attack vectors (Prompt injection, Training data exposure, Model manipulation, PII leakage, etc.)
  - Overlap area showing shared concerns (Authentication, Authorization, Network security)
- Labels:
  - Traditional: "Standard web app threats"
  - AI-specific: "New AI system threats"
  - Shared: "Common security concerns"
  - Each threat type with icon (lock, shield, warning symbol)
- Relationships: Venn diagram or side-by-side showing AI systems face both traditional AND new threats
- Visual cues: Red/warning colors for threat categories, shield icons for defenses needed, arrows pointing to specific vulnerabilities

**SPEAKER NOTES:**

"Security for AI systems has unique challenges beyond traditional applications.

[Point to challenges list]

Prompt injection - attackers can manipulate AI behavior through carefully crafted prompts.

Training data exposure - if your client fine-tuned models, that data needs protection.

PII leakage - users might paste sensitive data into prompts, and AI might include PII in responses.

[Pause for effect]

I've seen enterprise AI projects blocked by security teams because these risks weren't addressed.

We need defense-in-depth specifically designed for AI systems."

[Transition]

**BACKGROUND:**

**Rationale:**
- Establishes that AI security is not just "add authentication"
- Creates awareness of AI-specific attack vectors
- Sets up need for comprehensive security architecture

---

### SLIDE 15: DEFENSE IN DEPTH

**Title:** Five-Layer Security Architecture

**Content:**

**Defense-in-Depth Layers:**
```
Layer 1: Network (VPC, Private Endpoints, Firewalls)
    │
Layer 2: Identity (OAuth, API Keys, Service Accounts)
    │
Layer 3: Application (Input validation, Output filtering)
    │
Layer 4: Data (Encryption at rest/transit, Tokenization)
    │
Layer 5: Monitoring (Logging, Anomaly detection, Alerts)
```

**Principle:** Security at every layer. Compromise of one layer doesn't compromise the system.

**Graphic:** Layered diagram showing the five layers

**GRAPHICS:**

**Graphic 1: Defense-in-Depth Five-Layer Security Architecture**
- Purpose: Visualize the layered security approach with each layer protecting the core
- Type: Layered/concentric diagram (like an onion or castle walls)
- Elements:
  - Outermost Layer 1: Network Security (VPC, Private Endpoints, Firewalls)
  - Layer 2: Identity & Access Management (OAuth, API Keys, Service Accounts)
  - Layer 3: Application Security (Input validation, Output filtering, WAF)
  - Layer 4: Data Protection (Encryption at rest/transit, Tokenization, DLP)
  - Layer 5 (innermost): Monitoring & Audit (Logging, Anomaly detection, Alerts)
  - Center: "Protected AI System"
- Labels:
  - Each layer clearly labeled with name and key controls
  - "Defense-in-Depth: Security at every layer"
  - Brief description of what each layer protects against
- Relationships: Concentric layers showing multiple barriers, attacker must breach all layers
- Visual cues:
  - Shield/wall imagery for each layer
  - Color gradient from outer (blue) to inner (red) showing increasing sensitivity
  - Arrows showing attack vectors blocked at each layer
  - Checkmarks showing protection mechanisms

**SPEAKER NOTES:**

"We apply defense-in-depth using five layers:

[Walk through each layer]

Layer 1 - Network: VPC isolation, private endpoints, firewalls. AI APIs should not be accessible from the public internet.

Layer 2 - Identity: OAuth for users, IAM roles for services. Every request must be authenticated.

Layer 3 - Application: This is where AI-specific controls live. Input validation to prevent prompt injection. Output filtering to catch PII in responses.

Layer 4 - Data: Encryption at rest and in transit. If you're storing prompts and responses for audit, that data must be encrypted.

Layer 5 - Monitoring: Log everything. Detect anomalies. Alert on unusual patterns.

[Point to principle]

The key: if an attacker bypasses one layer, the others still protect you."

[Transition]

---

### SLIDE 16: SECRETS MANAGEMENT

**Title:** Managing Secrets in AI Systems

**Content:**

**Secrets You Need to Protect:**
- AI platform API keys
- Database credentials
- OAuth client secrets
- Encryption keys
- Service account credentials

**Secrets Management Patterns:**

| Pattern | Implementation | Use Case |
|---------|----------------|----------|
| **Vault-based** | HashiCorp Vault, AWS Secrets Manager | Dynamic secrets, rotation |
| **Environment** | Kubernetes Secrets, Parameter Store | Simple deployments |
| **Managed Identity** | AWS IAM Roles, Azure MSI | Cloud-native apps |

**Never:** Hard-code secrets, commit to git, store in config files

**Graphic:** Comparison table of patterns

**GRAPHICS:**

**Graphic 1: Secrets Management Patterns Comparison**
- Purpose: Compare three approaches to managing secrets in AI deployments
- Type: Comparison table with use case guidance
- Elements:
  - Three columns: Vault-based, Environment Variables, Managed Identity
  - Rows: Implementation, Use Case, Complexity, Security Level, Rotation Capability
  - Implementation details for each pattern
- Labels:
  - Vault-based: "HashiCorp Vault, AWS Secrets Manager" | "Dynamic secrets, rotation" | "High complexity, High security"
  - Environment: "Kubernetes Secrets, Parameter Store" | "Simple deployments" | "Medium complexity, Medium security"
  - Managed Identity: "AWS IAM Roles, Azure MSI" | "Cloud-native apps" | "Low complexity, High security"
- Relationships: Trade-offs between complexity and capabilities
- Visual cues:
  - Security rating (stars or locks)
  - Complexity indicator (1-3 gears)
  - Checkmarks for capabilities
  - Color coding: Green for recommended, yellow for acceptable, red for limitations

**SPEAKER NOTES:**

"Let's talk about secrets management.

[Point to secrets list]

Your AI system has multiple secrets to protect. API keys for Bedrock, Azure OpenAI, or Vertex. Database credentials. OAuth secrets.

[Point to patterns table]

Three patterns:

Vault-based - Use AWS Secrets Manager, HashiCorp Vault, or equivalent. Secrets are centralized, can be rotated automatically, access is audited.

Environment variables - Kubernetes Secrets or Parameter Store. Simpler but less dynamic.

Managed Identity - Best when possible. Your Lambda or container assumes an IAM role, no secrets to manage.

[Emphasize this]

What you NEVER do: hard-code API keys in your code, commit them to git, or store them in config files. I still see this in production systems. Don't do it."

[Transition]

---

### SLIDE 17: API GATEWAY SECURITY

**Title:** Securing the Entry Point

**Content:**

**API Gateway Security Controls:**

1. **Rate Limiting** - Per client/tenant limits prevent abuse
2. **Request Validation** - Schema validation, size limits
3. **Authentication** - JWT/OAuth token validation
4. **Authorization** - RBAC/ABAC policy enforcement
5. **IP Allowlisting** - For B2B/partner integrations
6. **DDoS Protection** - CloudFront, Azure Front Door, Cloud Armor

**AI-Specific Controls:**
- Prompt size limits (prevent token abuse)
- Content filtering (block harmful requests)
- Output sanitization (PII redaction)

**Graphic:** API Gateway with controls illustrated

**GRAPHICS:**

**Graphic 1: API Gateway Security Controls Stack**
- Purpose: Show all the security layers enforced at the API Gateway level
- Type: Layered architecture diagram with control annotations
- Elements:
  - Center: API Gateway icon/box
  - Top (incoming): Request flow with threats (malicious requests, DDoS, etc.)
  - Security control layers within gateway:
    1. Rate Limiting (speedometer icon)
    2. Request Validation (checkmark/clipboard icon)
    3. Authentication (key icon)
    4. Authorization (shield icon)
    5. IP Allowlisting (network icon)
    6. DDoS Protection (armor icon)
  - Bottom (outgoing): Clean, validated requests to backend
  - Side annotations for AI-specific controls: Prompt size limits, Content filtering, Output sanitization
- Labels:
  - Each control labeled with purpose
  - "Rate Limiting: Per client/tenant"
  - "Authentication: JWT/OAuth validation"
  - "Authorization: RBAC/ABAC policies"
  - AI-specific labels highlighted
- Relationships: Sequential filtering showing each control as a gate
- Visual cues:
  - Red threats blocked at each layer
  - Green validated requests passing through
  - Shield/protection icons
  - Traffic flow arrows

**SPEAKER NOTES:**

"Your API Gateway is the front line of defense.

[Walk through controls]

Rate limiting - Essential. Without it, a single user can drive up costs or abuse the system. Limit per API key, per user, per tenant.

Request validation - Validate request format and size. Prevent malformed requests from reaching your agent.

Authentication and authorization - Every request must be authenticated, then authorized against policies.

[Point to AI-specific controls]

For AI specifically: limit prompt size. I've seen users paste entire books into prompts, running up massive token costs.

Content filtering - block known harmful prompt patterns.

Output sanitization - scan responses for PII before returning to users.

In Exercise 1.2, you'll design all these controls for a specific architecture."

[Transition]

---

### SLIDE 18: SEGMENT 3 SUMMARY

**Title:** Security Architecture - Key Takeaways

**Content:**

**Key Takeaway:** AI systems need defense-in-depth with AI-specific controls at the application layer.

**Five Layers:**
1. Network isolation
2. Identity & access management
3. Application-level validation and filtering
4. Data encryption and protection
5. Monitoring and anomaly detection

**AI-Specific Focus:**
- Prompt injection prevention
- PII detection and redaction
- Secrets management for API keys
- Audit logging for compliance

**You'll Practice:**
Exercise 1.2 - Complete security architecture design

**Graphic:** Summary checklist

**SPEAKER NOTES:**

"Security summary:

Defense-in-depth with five layers. Security at the network, identity, application, data, and monitoring levels.

[Emphasize AI-specific controls]

The application layer is where AI-specific controls live. Prompt injection prevention, PII detection, output filtering.

This isn't optional. I've seen enterprise deals blocked because security architecture wasn't addressed.

In Exercise 1.2, you'll design a complete security architecture for an AI system.

Questions on security before we talk about decision frameworks?"

[Transition: Click to Segment 4]

---

## SEGMENT 4: PLATFORM SELECTION DECISION FRAMEWORK
### Duration: 9 minutes | Slides 19-22

---

### SLIDE 19: DECISION FRAMEWORKS

**Title:** Structured Platform Selection

**Content:**

**Why You Need a Framework:**
- Clients expect data-driven recommendations
- Documents decision rationale for stakeholders
- Reduces bias and political pressure
- Creates repeatable evaluation process

**Two Complementary Approaches:**
1. **Decision Tree** - Binary filters to narrow options
2. **Weighted Scoring** - Quantitative comparison of finalists

**Graphic:** Icons representing decision tree and scoring matrix

**GRAPHICS:**

**Graphic 1: Two-Part Decision Framework Overview**
- Purpose: Introduce the two complementary approaches for platform selection
- Type: Process flow with method icons
- Elements:
  - Left side: Decision Tree (tree/flowchart icon)
    - "Narrow the field"
    - "Binary filters"
    - "Hard requirements"
  - Arrow pointing right labeled "THEN"
  - Right side: Weighted Scoring (spreadsheet/calculator icon)
    - "Compare finalists"
    - "Quantitative analysis"
    - "Data-driven choice"
  - Bottom: Final output "Platform Recommendation with Justification"
- Labels:
  - "Step 1: Filter" on decision tree
  - "Step 2: Score" on weighted matrix
  - "Documented, defensible decision" at output
- Relationships: Sequential process showing both methods working together
- Visual cues: Funnel imagery (many options → few options → one choice), numbered steps, arrows showing progression

**SPEAKER NOTES:**

"You can't just say 'use Azure' without justification.

Your client needs to defend this decision to their CTO, their security team, their procurement team.

You need a framework that:
- Filters options based on hard requirements
- Scores remaining options quantitatively
- Documents why you scored the way you did

[Point to two approaches]

Decision tree narrows the field. Weighted scoring compares what remains.

Let me show you how."

[Transition]

---

### SLIDE 20: DECISION TREE APPROACH

**Title:** Decision Tree for Platform Selection

**Content:**

**Four-Level Decision Tree:**

```
1. Do you have existing cloud infrastructure?
   ├── Yes: Prefer that platform for integration
   └── No: Evaluate based on model and feature needs

2. Do you need specific models?
   ├── OpenAI GPT-4 only: Azure OpenAI
   ├── Claude only: AWS Bedrock or Google Vertex
   └── Flexibility needed: AWS Bedrock (most models)

3. What are your compliance requirements?
   ├── Government/FedRAMP: All three support
   ├── Data residency: Check regional availability
   └── Industry-specific: Verify certifications

4. What is your team's expertise?
   └── Weight platform by existing skills
```

**Graphic:** Flowchart visualization

**GRAPHICS:**

**Graphic 1: Platform Selection Decision Tree**
- Purpose: Provide a clear decision path for narrowing platform choices
- Type: Flowchart decision tree
- Elements:
  - Start node: "Platform Selection"
  - Level 1: "Existing cloud infrastructure?" → Yes/No branches
    - Yes → "Prefer that platform for integration" → (AWS/Azure/GCP logo)
    - No → Continue to Level 2
  - Level 2: "Specific models required?"
    - "OpenAI GPT-4 only?" → Yes → Azure OpenAI (decision end)
    - "Claude only?" → Yes → AWS Bedrock or Google Vertex
    - "Flexibility needed?" → Yes → AWS Bedrock (most models)
  - Level 3: "Compliance requirements?"
    - Government/FedRAMP → All three support (continue)
    - Data residency → Check regional availability
    - Industry-specific → Verify certifications
  - Level 4: "Team expertise?"
    - Existing skills → Weight platform by familiarity
- Labels:
  - Each decision clearly stated as question
  - Outcomes labeled with platform names and logos
  - "Decision point" markers
- Relationships: Tree structure with yes/no branches, multiple paths to recommendations
- Visual cues: Decision diamonds, outcome boxes, platform logos at endpoints, green highlighting for recommended paths

**SPEAKER NOTES:**

"The decision tree works like this:

[Walk through each level]

Level 1: Existing infrastructure. If they're deep into AWS with tons of services, the integration case for Bedrock is strong. Not decisive, but weighted heavily.

Level 2: Model requirements. This often decides it. Need GPT-4? Azure is your answer. That's a binary filter.

Level 3: Compliance. Usually all three qualify, but check regional availability. Some models only available in certain regions.

Level 4: Team expertise. Retraining a team on a new cloud platform is expensive and time-consuming.

[Pause]

This tree gets you to one or two finalists. Then you score them."

[Transition]

---

### SLIDE 21: WEIGHTED SCORING MODEL

**Title:** Quantitative Platform Scoring

**Content:**

**Scoring Template:**

| Factor | Weight | Platform A | Platform B | Platform C |
|--------|--------|------------|------------|------------|
| Model availability | 25% | | | |
| Existing integration | 20% | | | |
| Security/Compliance | 20% | | | |
| Cost structure | 15% | | | |
| Team expertise | 10% | | | |
| Support/SLAs | 10% | | | |
| **Weighted Total** | 100% | | | |

**Scoring Scale:** 1-10 for each factor
**Calculation:** (Score × Weight) summed across factors

**Document:** Rationale for each score

**Graphic:** Scoring table with example scores

**GRAPHICS:**

**Graphic 1: Weighted Scoring Model Template**
- Purpose: Show the scoring methodology with example values filled in
- Type: Scoring matrix/table
- Elements:
  - Column headers: Factor, Weight, Platform A (AWS), Platform B (Azure), Platform C (GCP)
  - Rows:
    - Model availability: 25% | 7/10 | 10/10 | 8/10
    - Existing integration: 20% | 3/10 | 10/10 | 4/10
    - Security/Compliance: 20% | 9/10 | 9/10 | 9/10
    - Cost structure: 15% | 7/10 | 6/10 | 8/10
    - Team expertise: 10% | 4/10 | 9/10 | 3/10
    - Support/SLAs: 10% | 8/10 | 9/10 | 7/10
  - Bottom row: Weighted Total | 6.5 | 9.0 | 7.1
  - Winner highlight on Platform B
- Labels:
  - Each factor clearly labeled
  - Weights shown as percentages (total 100%)
  - Scores shown as X/10
  - Calculated weighted totals
  - "RECOMMENDED" badge on winner
- Relationships: Weighted calculation showing how scores combine to final decision
- Visual cues:
  - Color gradient on scores (green=high, yellow=medium, red=low)
  - Bold/highlight on winning platform
  - Weight percentages in separate column
  - Calculation arrows showing weight × score

**SPEAKER NOTES:**

"Here's the weighted scoring model.

[Explain the table]

Six factors, each with a weight totaling 100%.

For each platform, score 1-10 on each factor. Then multiply score by weight and sum.

[Point to weights]

These weights are suggestions. Adjust based on client priorities. If cost is the primary concern, increase that weight. If compliance is critical, weight it higher.

[Emphasize this]

Critical: document WHY you scored each platform the way you did. 'Azure scores 9/10 on existing integration because client has 50+ Azure resources and Entra ID.' That's defendable.

The scoring is somewhat subjective. The process is objective."

[Transition]

---

### SLIDE 22: SEGMENT 4 SUMMARY

**Title:** Decision Framework - Key Takeaways

**Content:**

**Key Takeaway:** Use decision trees to filter, weighted scoring to compare, and documentation to justify.

**Process:**
1. Apply decision tree to narrow to 1-2 finalists
2. Score finalists using weighted criteria
3. Document rationale for each score
4. Present recommendation with data

**Red Flags to Watch For:**
- Vendor lock-in with proprietary features
- Missing compliance certifications
- Unclear pricing at scale
- Limited regional availability

**You'll Practice:**
Exercise 1.1 - Complete platform comparison with weighted scoring

**Graphic:** Process flow diagram

**SPEAKER NOTES:**

"Decision framework summary:

Decision tree first - filter based on hard requirements.

Weighted scoring second - quantify the comparison.

Documentation throughout - justify every score.

[Point to red flags]

Watch for these red flags. Vendor lock-in is real - proprietary features that make migration painful.

Unclear pricing is common. Get clarity on costs at your expected scale.

[Pause]

With this framework, you can walk into a client meeting and confidently recommend a platform with data to back it up.

That's what we're practicing in Exercise 1.1."

[Transition: Click to Closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 23-25

---

### SLIDE 23: HOMEWORK OVERVIEW

**Title:** This Session's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 1.1: Platform Comparison | 25 min | `platform-comparison-analysis.md` | Platform evaluation, weighted scoring |
| Exercise 1.2: Security Architecture | 30 min | `security-architecture-design.md` | Defense-in-depth, security controls |
| Exercise 1.3: Cost Modeling | 20 min | `cost-model.md` | Cost projection, optimization |
| **Total** | **75 min** | | |

**Graphic:** Exercise icons showing progression

**SPEAKER NOTES:**

"Here's your homework for this session. You have 75 minutes of exercises.

Exercise 1.1 - Platform Comparison Analysis. You'll take a client scenario and apply the decision tree and weighted scoring framework we just covered. This practices the core skill of platform recommendation.

Exercise 1.2 - Security Architecture Design. You'll design a complete five-layer security architecture for an enterprise AI deployment. This is where you apply defense-in-depth principles.

Exercise 1.3 - Cost Modeling. You'll build a cost projection model showing costs at scale and optimization strategies.

These build on each other - platform selection informs architecture, architecture informs cost.

All templates and detailed instructions are in your participant guide."

[Transition]

---

### SLIDE 24: RESOURCES

**Title:** Resources for This Session

**Content:**

**Templates & Files:**
- Platform Comparison Template - Exercise 1.1
- Security Architecture Template - Exercise 1.2
- Cost Model Template - Exercise 1.3

**Reference Materials:**
- AWS Bedrock Documentation
- Azure OpenAI Documentation
- Google Vertex AI Documentation
- Module 6 Appendices A-C

**Support:**
- Questions: [Async channel]
- All materials in participant guide

**Graphic:** Resource icons or links

**SPEAKER NOTES:**

"Resources to support your work:

All three exercises have complete templates in your participant guide. Don't start from scratch.

Reference links to current platform documentation - pricing and features change frequently, so verify current details.

Appendices A-C in the module document have additional comparison matrices and checklists.

If you get stuck, post questions in the async channel. Common questions and answers are in your participant guide FAQ section."

[Transition]

---

### SLIDE 25: NEXT SESSION PREVIEW

**Title:** Next Session: Production Deployment & Operations

**Content:**

**Preview:**
Session 2 covers scaling patterns, hybrid/on-premises architectures, operations, and deployment strategy.

**What to Complete Before Then:**
- [ ] Exercise 1.1: Platform Comparison Analysis
- [ ] Exercise 1.2: Security Architecture Design
- [ ] Exercise 1.3: Cost Modeling

**Key Preparation:**
Session 2 builds directly on platform and architecture decisions from today.

**Graphic:** Preview image showing deployment and operations theme

**SPEAKER NOTES:**

"Next session we move from architecture design to operations. How do you actually deploy, scale, monitor, and maintain enterprise AI systems in production?

We'll cover auto-scaling strategies, hybrid and on-premises patterns, observability stacks, and deployment methodologies.

[Point to checklist]

Before next session, complete all three exercises. We'll be building on the platform selection and architecture designs you create today.

[Final close]

Great session today. Remember - the goal is to build repeatable frameworks you can apply in real client engagements.

See you next session!"

---

## Appendix A: Slide Type Definitions (Condensed)

**CONCEPT**: Introduces new idea or framework - focus on clarity and single concept
**DEMO**: Live demonstration or walkthrough - have backup plan if tech fails
**INSIGHT**: Delivers key learning or aha moment - emphasize and pause after
**TRANSITION**: Bridges sections - keep brief, preview what's coming
**SUMMARY**: Reinforces key points - use repetition intentionally

---

## Appendix B: Visual Design Guidelines

**Color Palette - Advanced Green Theme:**
- Primary: Advanced Green #00CC99
- Secondary: Deep Blue #003D5C
- Accent: Bright Orange #FF6B35
- Neutral: Cool Gray #708090
- Warning/Alert: Amber #FFA500

**Typography Standards:**
- Titles: 44pt bold
- Subtitles: 32pt regular
- Body text: 24pt (minimum)
- Code blocks: 18pt monospace
- Never go below 18pt for any text

**Graphic Requirements:**
- Every GRAPHICS block must be implemented
- Diagrams should use consistent iconography
- Color-code by meaning (green=good, red=bad, blue=information)
- Include alt text descriptions for accessibility

---

## Appendix C: Quality Checklist

**Content Quality:**
- [ ] All learning objectives explicitly addressed in slides
- [ ] Real-world examples included (not just theory)
- [ ] Key messages repeated in summary slides
- [ ] Transitions between segments are smooth

**Speaker Notes Quality:**
- [ ] Written as natural speech (not bullet points)
- [ ] Include specific timing guidance (pauses, emphasis)
- [ ] Anticipated questions addressed in BACKGROUND sections
- [ ] Clear instructions for demos/activities

**Technical Quality:**
- [ ] All GRAPHICS blocks have detailed specifications
- [ ] Code examples are tested and work
- [ ] All links and references are valid
- [ ] Version history is current

---

## Appendix: Presentation Design Notes

**Color Scheme:**
- Advanced module color: Purple/silver tones
- Accent colors for platform comparison: AWS orange, Azure blue, GCP colors

**Key Visuals Needed:**
- Platform comparison tables
- Architecture diagrams for all three patterns
- Security layer diagram
- Decision tree flowchart
- Weighted scoring template

**Animation Suggestions:**
- Architecture diagrams build step-by-step
- Decision tree reveals level by level
- Scoring table fills in during demo

---

**Version History:**

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | [Instructor] |
| 2.0 | 2026-01-03 | Enhanced with BACKGROUND sections, Key Thesis, and expanded appendices | Claude |
