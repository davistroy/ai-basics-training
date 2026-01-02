# **ADVANCED MODULE 6, SESSION 1: Cloud AI Architecture Patterns**

**Module:** Advanced Module 6: Enterprise AI Architecture
**Session:** 1 of 2
**Estimated Self-Paced Time:** 75 minutes

---

## Navigation

**Module Navigation:** Session 1 | [Session 2 →](../session-2/participant-guide.md)

**In This Guide:**
- [Learning Objectives](#learning-objectives)
- [Key Concepts](#key-concepts)
- [Workshop Recap](#workshop-recap)
- [Self-Paced Exercises](#self-paced-exercises)
- [Templates & Resources](#templates--resources)
- [Self-Assessment](#self-assessment)
- [Getting Help](#getting-help)

---

## Learning Objectives

By the end of this session, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Evaluate and compare major cloud AI platforms using weighted scoring | Exercise 1.1 |
| 2 | Design deployment architecture patterns for different enterprise scenarios | Exercise 1.2 |
| 3 | Apply defense-in-depth security principles to AI systems | Exercise 1.2 |
| 4 | Create platform selection decision frameworks for client engagements | Exercise 1.1 |

---

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Block 3: AI Automation Architecture with working agent system
- [ ] Access to at least one cloud platform (trial account acceptable)
- [ ] Understanding of basic networking concepts (VPC, API Gateway, etc.)
- [ ] Familiarity with API authentication patterns (OAuth, API keys)

**Not ready?** Review Block 3 materials or reach out in the support channel for help.

---

## Key Concepts

### Concept 1: Cloud AI Platform Comparison

**Definition:**
Systematic evaluation of major cloud AI platforms (AWS Bedrock, Azure OpenAI, Google Vertex AI) based on capabilities, integration, compliance, and cost.

**Why It Matters:**
Platform selection impacts long-term costs, technical capabilities, vendor lock-in, and team productivity. Wrong choice creates technical debt and expensive migrations.

**Core Principle:**
> There is no universal "best" platform. The right choice depends on client-specific requirements: model needs, existing infrastructure, compliance requirements, and team expertise.

**Comparison Framework:**

| Capability | AWS Bedrock | Azure OpenAI | Google Vertex AI |
|------------|-------------|--------------|------------------|
| **Model Access** | Claude, Llama, Titan | GPT-4, GPT-3.5 | Gemini, PaLM, Claude |
| **Fine-tuning** | Select models | GPT-3.5-turbo | Most models |
| **Agents** | Bedrock Agents | Assistants API | Vertex AI Agents |
| **RAG Support** | Knowledge Bases | Azure AI Search | Vertex AI Search |
| **Enterprise SSO** | IAM, SAML | Entra ID native | Cloud IAM |
| **Compliance** | FedRAMP, HIPAA | FedRAMP, HIPAA | FedRAMP, HIPAA |

**Common Mistake:**
Choosing a platform based on general reputation instead of specific client requirements. "Everyone uses AWS" is not a valid rationale.

---

### Concept 2: Deployment Architecture Patterns

**Definition:**
Standard architectural patterns for deploying AI agents at enterprise scale: serverless, containerized, and queue-based.

**Why It Matters:**
Deployment pattern affects cost, latency, scalability, and operational complexity. Mismatch between pattern and workload leads to poor performance or excessive costs.

**The Three Patterns:**

```
Pattern 1: Serverless
- Best for: Variable workloads, cost optimization
- Limitations: Cold starts, execution time limits

Pattern 2: Containerized
- Best for: Consistent performance, complex orchestration
- Limitations: Higher baseline cost, operational complexity

Pattern 3: Queue-Based
- Best for: Batch processing, rate limiting
- Limitations: Not suitable for real-time needs
```

**When to Use:**
- **Serverless:** Request volume varies significantly throughout day, cost optimization is priority
- **Containerized:** Consistent low latency required, complex multi-agent workflows, long-running tasks
- **Queue-Based:** Batch processing acceptable, need natural rate limiting, async workflows

**When NOT to Use:**
- **Serverless:** Cannot tolerate cold start latency, tasks exceed execution time limits
- **Containerized:** Low budget, limited operational expertise, variable workload
- **Queue-Based:** Users need immediate real-time responses

---

### Concept 3: Defense-in-Depth Security

**Definition:**
Layered security approach where multiple independent security controls protect AI systems. Compromise of one layer doesn't compromise the entire system.

**Key Components:**

| Layer | Purpose | Example Controls |
|-----------|-------------|---------|
| **Layer 1: Network** | Isolate and protect network traffic | VPC, private endpoints, firewalls |
| **Layer 2: Identity** | Authenticate and authorize access | OAuth, API keys, IAM roles |
| **Layer 3: Application** | Validate inputs and outputs | Prompt injection prevention, PII redaction |
| **Layer 4: Data** | Protect data at rest and in transit | Encryption (AES-256, TLS 1.3) |
| **Layer 5: Monitoring** | Detect and respond to threats | Logging, anomaly detection, alerts |

**Visual Reference:**
```
┌─────────────────────────────────────┐
│    Layer 5: Monitoring              │
│  (Logging, Anomaly Detection)       │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│    Layer 4: Data Protection         │
│  (Encryption at rest/transit)       │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│    Layer 3: Application Security    │
│  (Input validation, Output filter)  │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│    Layer 2: Identity & Access       │
│  (OAuth, API Keys, IAM)             │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│    Layer 1: Network Security        │
│  (VPC, Private Endpoints)           │
└─────────────────────────────────────┘
```

**AI-Specific Security Considerations:**
- **Prompt injection prevention** - Input validation at Layer 3
- **PII detection and redaction** - Output filtering at Layer 3
- **API key management** - Secrets vault at Layer 2
- **Audit logging** - Request/response logging at Layer 5

---

### Concept 4: Platform Selection Framework

**Definition:**
Structured decision-making process using decision trees and weighted scoring to select cloud AI platforms based on client requirements.

**Why It Matters:**
Clients need data-driven recommendations with documented rationale. Framework removes bias, manages political pressure, and creates repeatable evaluation process.

**Two-Part Process:**

**Part 1: Decision Tree (Filters)**
```
1. Existing cloud infrastructure?
   → Strong preference for that platform

2. Specific model requirements?
   → GPT-4 only = Azure
   → Claude preferred = Bedrock or Vertex
   → Flexibility = Bedrock

3. Compliance requirements?
   → Verify certifications and regional availability

4. Team expertise?
   → Weight by existing skills
```

**Part 2: Weighted Scoring (Comparison)**

| Factor | Weight | Platform A | Platform B | Platform C |
|--------|--------|------------|------------|------------|
| Model availability | 25% | /10 | /10 | /10 |
| Existing integration | 20% | /10 | /10 | /10 |
| Security/Compliance | 20% | /10 | /10 | /10 |
| Cost structure | 15% | /10 | /10 | /10 |
| Team expertise | 10% | /10 | /10 | /10 |
| Support/SLAs | 10% | /10 | /10 | /10 |
| **Weighted Total** | 100% | X.X | X.X | X.X |

**Critical Success Factor:**
Document rationale for each score. "Azure scores 9/10 on existing integration because client has 50+ Azure resources and Entra ID" is defendable. A score without rationale is not.

---

## Workshop Recap

### Session Summary

**Today's Focus:** Cloud platform comparison, deployment architecture patterns, security architecture, and platform selection frameworks for enterprise AI.

**Key Points from Each Segment:**

**Segment 1: Cloud AI Platform Landscape**
- AWS Bedrock, Azure OpenAI, and Google Vertex AI have different model access and capabilities
- Model availability is often the first decision filter
- Existing cloud infrastructure significantly impacts TCO
- Six selection factors: models, integration, compliance, cost, team, support

**Segment 2: Deployment Architecture Patterns**
- Serverless pattern: best for variable workloads, watch for cold starts
- Containerized pattern: consistent performance, higher baseline cost
- Queue-based pattern: perfect for async batch processing
- Choose pattern based on workload characteristics, not "what's best"

**Segment 3: Security Architecture Fundamentals**
- Defense-in-depth uses five layers: network, identity, application, data, monitoring
- AI has unique security challenges: prompt injection, PII leakage, model manipulation
- Application layer (Layer 3) is where AI-specific controls live
- Never hard-code secrets - use vaults or managed identities

**Segment 4: Platform Selection Decision Framework**
- Decision tree filters options based on hard requirements
- Weighted scoring compares finalists quantitatively
- Document rationale for every score
- Framework removes bias and creates defendable recommendations

### Demo Recap

**What Was Demonstrated:**
Weighted scoring model applied to healthcare client scenario

**Key Steps:**
1. Defined client requirements (healthcare, Azure shop, needs GPT-4, HIPAA)
2. Scored each platform (AWS Bedrock, Azure OpenAI, Vertex AI) on six factors
3. Applied weights to each factor score
4. Calculated weighted totals
5. Recommended Azure OpenAI based on highest score with documented rationale

**Result:**
Azure scored highest (8.7/10) due to GPT-4 availability and existing Azure infrastructure. Bedrock and Vertex scored lower primarily on model availability for GPT-4.

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 1.1 | 25 min | `platform-comparison-analysis.md` | Platform selection framework |
| 1.2 | 30 min | `security-architecture-design.md` | Defense-in-depth security |
| 1.3 | 20 min | `cost-model.md` | Cost projection and optimization |

---

### Exercise 1.1: Platform Comparison Analysis

**Duration:** 25 minutes

**Purpose:**
Apply the platform selection framework (decision tree + weighted scoring) to a realistic client scenario. This practices the core skill of making data-driven platform recommendations.

**You Will Create:**
Complete platform comparison analysis with weighted scoring and documented recommendation

---

#### Instructions

**Step 1: Define Client Scenario**

Choose a client scenario (or create your own):

**Option A: Financial Services**
- Industry: Banking/Financial Services
- Use Case: Customer service automation for account inquiries
- Scale: 500,000 customers, ~50,000 requests/day
- Existing Infrastructure: AWS (extensive use of AWS services, but no AI yet)
- Key Constraints: PCI DSS compliance, data residency in US, strict security requirements

**Option B: Healthcare**
- Industry: Healthcare provider
- Use Case: Clinical documentation assistance for physicians
- Scale: 500 physicians, ~5,000 patient notes/day
- Existing Infrastructure: Azure (using Entra ID, Azure SQL, etc.)
- Key Constraints: HIPAA compliance, needs GPT-4 specifically, budget-conscious

**Option C: Retail**
- Industry: E-commerce retail
- Use Case: Product recommendation and customer support
- Scale: 1M customers, highly variable traffic (10x spikes during sales)
- Existing Infrastructure: Google Cloud (GKE, BigQuery, etc.)
- Key Constraints: Cost optimization priority, need for multiple models, global deployment

Fill in your chosen scenario in the template.

**Step 2: Apply Decision Tree**

Work through the four-level decision tree:

1. **Existing infrastructure?** → Document platform and level of investment
2. **Specific model requirements?** → Identify must-have models
3. **Compliance requirements?** → List required certifications
4. **Team expertise?** → Note cloud platform experience

This should narrow to 1-2 finalist platforms.

**Step 3: Complete Weighted Scoring**

For each finalist platform:
1. Score 1-10 on each factor (Model fit, Integration ease, Compliance, Cost, Team, Support)
2. **Document rationale for each score** in 1-2 sentences
3. Multiply score × weight
4. Sum weighted scores

**Step 4: Make Recommendation**

Based on weighted scores:
1. State primary recommendation
2. Explain rationale (why this platform won)
3. Identify risks and mitigation strategies

**Step 5: Review Your Work**

Check that your deliverable includes:
- [ ] Complete client scenario definition
- [ ] Decision tree application showing filtering logic
- [ ] Weighted scoring for all finalist platforms
- [ ] **Documented rationale for every score**
- [ ] Clear recommendation with supporting data
- [ ] Risk mitigation strategies

---

#### Deliverable Specification

**File Name:** `platform-comparison-analysis.md`

**Location:** Your working directory for Module 6

**Format Requirements:**
- Use the template provided in Templates section below
- Complete all sections (no placeholder text remaining)
- Document score rationale in each platform evaluation
- Show weighted score calculations

**Quality Criteria:**
- [ ] Client scenario is realistic and complete
- [ ] Decision tree logic is sound and documented
- [ ] Weighted scoring shows clear mathematical winner
- [ ] Every score has documented justification
- [ ] Recommendation is data-driven and defendable
- [ ] Risks are identified with mitigation strategies

---

#### Example

**Scenario:** Healthcare client (Option B above)

**Decision Tree Application:**
1. Existing infrastructure: Azure (heavy investment - 50+ resources)
2. Model requirements: GPT-4 specifically required → Filters to Azure OpenAI only
3. Compliance: HIPAA required → Azure meets requirement
4. Team expertise: Strong Azure skills

**Weighted Scoring:**

Azure OpenAI:
- Model availability: 10/10 (has GPT-4, which is required) × 25% = 2.5
- Integration: 10/10 (existing Azure footprint) × 20% = 2.0
- Compliance: 10/10 (HIPAA certified) × 20% = 2.0
- Cost: 7/10 (competitive but not cheapest) × 15% = 1.05
- Team: 9/10 (strong Azure expertise) × 10% = 0.9
- Support: 8/10 (good enterprise support) × 10% = 0.8
- **Total: 9.25/10**

**Recommendation:** Azure OpenAI

**Rationale:** Azure is the only platform with GPT-4, which is a hard requirement. Additionally, strong existing Azure infrastructure and team expertise make integration faster and cheaper.

**Why This Works:**
- Decision tree eliminated other options (GPT-4 requirement)
- Scoring shows quantitative advantage on key factors
- Every score has documented justification
- Recommendation is data-driven and defendable to stakeholders

---

#### Tips & Troubleshooting

**Tips:**
- Don't overthink the scores - documenting your rationale matters more than perfect numbers
- If decision tree narrows to one platform, still complete scoring to show why it's strong
- Consider total cost of ownership, not just API costs - integration and training matter
- Multi-cloud is an option, but you need strong justification for the added complexity

**Common Issues:**

| Problem | Solution |
|---------|----------|
| "All platforms seem equally good" | Look deeper at model requirements and existing infrastructure - these usually create differentiation |
| "I don't know what score to give" | Research that factor (pricing, features) or make educated estimate with documented assumptions |
| "Weights don't seem right" | Adjust weights based on client priorities - no universal "right" weighting |
| "My math doesn't add up" | Check that weights total 100%, and scores are being multiplied (not added) to weights |

---

### Exercise 1.2: Security Architecture Design

**Duration:** 30 minutes

**Purpose:**
Design a complete defense-in-depth security architecture for an enterprise AI deployment. This practices applying the five-layer security model with AI-specific controls.

**You Will Create:**
Comprehensive security architecture document covering all five layers with specific implementation details

---

#### Instructions

**Step 1: Define System Overview**

Choose your deployment from Exercise 1.1 (or use the scenario below):
- Platform: [AWS Bedrock / Azure OpenAI / Vertex AI - from Exercise 1.1]
- Deployment pattern: [Serverless / Containerized / Queue-based - choose one]
- Data sensitivity: [Public / Internal / Confidential / Restricted]

**Default Scenario if needed:**
- Platform: Azure OpenAI
- Pattern: Containerized (AKS cluster)
- Data sensitivity: Confidential (healthcare data, HIPAA)

**Step 2: Design Network Security (Layer 1)**

Create architecture diagram showing:
- VPC/VNet boundaries
- Public vs Private subnets
- Private endpoints for AI API
- Firewall rules
- Load balancer configuration

Document network controls in table format (see template).

**Step 3: Design Identity & Access Management (Layer 2)**

Define:
- **Service authentication**: How services authenticate (IAM roles, API keys, managed identities)
- **User authentication**: How end users authenticate (OAuth, SAML, API keys)
- **Authorization model**: RBAC or ABAC with defined roles and permissions
- **Secrets management**: Where and how API keys and credentials are stored

**Step 4: Design Application Security (Layer 3)**

This is where AI-specific controls live:
- **Input validation**: Prompt injection prevention, size limits, content filtering
- **Output filtering**: PII detection in responses, harmful content filtering
- **Rate limiting**: Per-user, per-tenant limits
- **Audit logging**: What to log for compliance

**Step 5: Design Data Protection (Layer 4)**

Define:
- **Encryption at rest**: Method (AES-256), key management (KMS, customer-managed)
- **Encryption in transit**: TLS 1.3, certificate management
- **PII handling**: Detection, redaction, retention policies

**Step 6: Design Monitoring & Audit (Layer 5)**

Define:
- **Logging strategy**: What to log, retention periods, storage location
- **Alerting**: What conditions trigger alerts, who responds
- **Compliance mapping**: How controls map to requirements (HIPAA, SOC 2, etc.)

**Step 7: Review Your Work**

Check that your deliverable includes:
- [ ] All five security layers addressed
- [ ] AI-specific controls in application layer
- [ ] Secrets management approach defined
- [ ] Monitoring and alerting configured
- [ ] Compliance requirements mapped to controls

---

#### Deliverable Specification

**File Name:** `security-architecture-design.md`

**Location:** Your working directory for Module 6

**Format Requirements:**
- Use the template provided in Templates section
- Include network architecture diagram (ASCII art or description)
- Complete all five security layers
- Document specific controls, not generic statements

**Quality Criteria:**
- [ ] Defense-in-depth with all five layers
- [ ] AI-specific controls clearly identified
- [ ] Secrets never hard-coded or stored in code
- [ ] Encryption at rest and in transit specified
- [ ] Monitoring covers security events and anomalies
- [ ] Compliance mapping shows how controls meet requirements

---

#### Example

**System:** Healthcare AI clinical documentation (HIPAA-compliant)

**Network Security (Layer 1):**
```
VNet: 10.0.0.0/16
├── Public Subnet (10.0.1.0/24)
│   └── Load Balancer (TLS termination)
└── Private Subnet (10.0.2.0/24)
    ├── AKS Cluster (agent pods)
    ├── Azure OpenAI (private endpoint)
    └── Azure SQL (private endpoint)

Firewall: Allow only HTTPS (443) from public internet to LB
          Allow only internal traffic between private subnet resources
```

**Controls:**
- VPC isolation: Separate VNet for AI system
- Private endpoints: Azure OpenAI and SQL only accessible from VNet
- Firewall: NSG rules block all except HTTPS to LB
- DDoS: Azure DDoS Protection Standard

**Why This Works:**
All AI processing happens in private subnet. Azure OpenAI API is never exposed to public internet. Even if LB is compromised, attacker can't reach AI services directly.

---

### Exercise 1.3: Cost Modeling

**Duration:** 20 minutes

**Purpose:**
Build a cost projection model showing costs at enterprise scale with optimization strategies. This practices the financial analysis skills needed for enterprise AI proposals.

**You Will Create:**
Complete cost model with scaling projections and optimization roadmap

---

#### Instructions

**Step 1: Define Baseline Assumptions**

Document your usage profile:
- **Daily active users**: Estimate for Month 1
- **Requests per user per day**: Typical usage
- **Average tokens per request**: Input and output token estimates
- **Peak hours**: When is usage highest? What's the multiplier?

Use your Exercise 1.1 scenario or create realistic assumptions.

**Step 2: Project Growth**

Create growth projections for:
- Month 1 (initial deployment)
- Month 6 (mid-year)
- Month 12 (end of first year)
- Month 24 (end of second year)

For each period, estimate: users, requests/day, monthly tokens

**Step 3: Calculate AI API Costs**

Get current pricing for your selected platform and models:
- Input tokens: $ per 1M tokens
- Output tokens: $ per 1M tokens

Calculate monthly AI costs for each growth period.

**Step 4: Calculate Infrastructure Costs**

Estimate monthly costs for:
- **Compute**: API Gateway, Lambda/containers, etc.
- **Storage**: Object storage, database storage
- **Data transfer**: Network egress
- **Additional**: Monitoring, security tools, support tiers

**Step 5: Identify Optimization Strategies**

List 3-5 cost optimization strategies:
- Caching frequently requested responses
- Model selection optimization (use smaller models when appropriate)
- Reserved capacity vs on-demand
- Prompt engineering to reduce tokens
- Batch processing for non-urgent requests

For each, estimate implementation effort and potential savings.

**Step 6: Calculate Cost per Transaction**

For different transaction types, break down:
- Tokens used
- AI API cost
- Infrastructure cost
- Total cost per transaction
- Target cost (if you have a budget constraint)

**Step 7: Review Your Work**

Check that your deliverable includes:
- [ ] Realistic usage and growth assumptions
- [ ] AI API cost projections for multiple time periods
- [ ] Infrastructure cost breakdowns
- [ ] Total cost summary
- [ ] Cost optimization strategies with estimated savings
- [ ] Cost per transaction analysis

---

#### Deliverable Specification

**File Name:** `cost-model.md`

**Location:** Your working directory for Module 6

**Format Requirements:**
- Use the template provided in Templates section
- Show calculations and assumptions
- Include scaling scenarios (not just single point-in-time)
- Document optimization strategies

**Quality Criteria:**
- [ ] Usage assumptions are realistic
- [ ] Growth projections show scaling over time
- [ ] Costs include both AI API and infrastructure
- [ ] Optimization strategies are specific and quantified
- [ ] Cost per transaction broken down by component
- [ ] Total year 1 cost calculated

---

#### Tips & Troubleshooting

**Tips:**
- Use current pricing from platform documentation - pricing changes frequently
- Don't forget infrastructure costs - API Gateway, load balancers, databases, monitoring
- Reserved capacity can save 15-30% if usage is consistent
- Caching is often the biggest cost optimization opportunity

**Common Issues:**

| Problem | Solution |
|---------|----------|
| "I don't know current pricing" | Check platform documentation or use placeholder values with note to verify |
| "Token estimates seem arbitrary" | Test with sample prompts to get realistic token counts |
| "Infrastructure costs are complex" | Start with major components (compute, storage), add details as you learn |
| "Optimization savings are guesses" | That's OK - document assumptions, industry benchmarks are 20-30% from caching |

---

## Templates & Resources

### Template 1: Platform Comparison Analysis

```markdown
# Platform Comparison Analysis

## Client Scenario
- **Industry:** [e.g., Financial Services, Healthcare, Retail]
- **Use Case:** [e.g., Customer service automation, document processing]
- **Scale:** [Expected volume, users, transactions]
- **Existing Infrastructure:** [Current cloud provider, tools]
- **Key Constraints:** [Compliance, budget, timeline]

## Platform Evaluation

### AWS Bedrock

#### Strengths for This Scenario
1. [Strength with rationale]
2. [Strength with rationale]
3. [Strength with rationale]

#### Limitations for This Scenario
1. [Limitation with impact]
2. [Limitation with impact]

#### Relevant Features
- Model options: [List applicable models]
- Integration points: [Existing AWS services to leverage]
- Compliance: [Relevant certifications]

#### Cost Estimate
- Per-request pricing: $X.XX per 1M tokens (input), $X.XX per 1M tokens (output)
- Monthly estimate at scale: $X,XXX
- Hidden costs: [Training, data transfer, support, etc.]

---

### Azure OpenAI

[Same structure as AWS Bedrock]

---

### Google Vertex AI

[Same structure as AWS Bedrock]

---

## Weighted Scoring

| Factor | Weight | AWS Bedrock | Azure OpenAI | Vertex AI |
|--------|--------|-------------|--------------|-----------|
| Model fit | 25% | X/10 (rationale) | X/10 (rationale) | X/10 (rationale) |
| Integration ease | 20% | X/10 (rationale) | X/10 (rationale) | X/10 (rationale) |
| Compliance match | 20% | X/10 (rationale) | X/10 (rationale) | X/10 (rationale) |
| Cost efficiency | 15% | X/10 (rationale) | X/10 (rationale) | X/10 (rationale) |
| Team readiness | 10% | X/10 (rationale) | X/10 (rationale) | X/10 (rationale) |
| Support quality | 10% | X/10 (rationale) | X/10 (rationale) | X/10 (rationale) |
| **Weighted Score** | 100% | X.XX | X.XX | X.XX |

## Recommendation
[Primary recommendation with clear rationale based on weighted scores and decision tree]

## Risk Mitigation
[Specific strategies to address limitations of recommended platform]
```

---

### Template 2: Security Architecture Design

```markdown
# Security Architecture Design

## System Overview
- **Platform:** [AWS Bedrock / Azure OpenAI / Vertex AI]
- **Deployment pattern:** [Serverless / Containerized / Queue-based]
- **Data sensitivity:** [Public / Internal / Confidential / Restricted]

## Layer 1: Network Security

### Architecture Diagram
```
[ASCII diagram showing VPC/VNet, subnets, private endpoints, firewalls, load balancers]
```

### Network Controls
| Control | Implementation | Status |
|---------|----------------|--------|
| VPC isolation | [Details] | [ ] Planned |
| Private endpoints | [Details] | [ ] Planned |
| Firewall rules | [Details] | [ ] Planned |
| DDoS protection | [Details] | [ ] Planned |

## Layer 2: Identity & Access Management

### Service Authentication
| Service | Auth Method | Secret Storage |
|---------|-------------|----------------|
| AI API | [API Key / IAM Role / Managed Identity] | [Secrets Manager / Vault] |
| Database | [IAM / Password] | [Location] |
| External APIs | [OAuth / API Key] | [Location] |

### User Authentication
- **Method:** [OAuth 2.0 / SAML / API Keys]
- **Provider:** [Okta / Entra ID / Cognito]
- **MFA:** [Required / Optional]

### Authorization Model
- **Pattern:** [RBAC / ABAC / Custom]
- **Roles:**
  - Admin: [Permissions]
  - Developer: [Permissions]
  - Operator: [Permissions]
  - Auditor: [Permissions]

## Layer 3: Application Security

### Input Validation
- **Prompt injection prevention:** [Method]
- **Input size limits:** [Values]
- **Content filtering:** [Approach]

### Output Filtering
- **PII detection:** [Tool/method for detecting PII in responses]
- **Harmful content filtering:** [Approach]
- **Confidence thresholds:** [Values]

### Rate Limiting
- **Per-user limits:** [Requests per minute]
- **Per-tenant limits:** [Requests per minute]
- **Cost protection:** [Max $ per hour]

## Layer 4: Data Protection

### Encryption
| Data State | Method | Key Management |
|------------|--------|----------------|
| At rest | [AES-256] | [AWS KMS / Azure Key Vault / Customer-managed] |
| In transit | [TLS 1.3] | [Certificate source] |
| In processing | [Details] | [Details] |

### PII Handling
- **Detection:** [Tool/method]
- **Redaction:** [Before/after AI processing]
- **Retention:** [Duration, deletion process]

## Layer 5: Monitoring & Audit

### Logging Strategy
| Log Type | Retention | Storage |
|----------|-----------|---------|
| Access logs | [Days] | [S3/Blob/Cloud Storage] |
| AI request/response | [Days] | [Location] |
| Security events | [Days] | [Location] |
| Audit trail | [Days] | [Location] |

### Alerting
| Alert | Condition | Response |
|-------|-----------|----------|
| Unusual volume | >X requests/min | [Action] |
| Auth failures | >N in Y minutes | [Action] |
| Cost anomaly | >X% above baseline | [Action] |

## Compliance Mapping

| Requirement | Control | Evidence |
|-------------|---------|----------|
| [SOC 2 - Access Control] | [Specific implementation] | [Audit logs, IAM policies] |
| [HIPAA - Encryption] | [Implementation] | [Encryption configuration] |
| [GDPR - Data handling] | [Implementation] | [Retention policies] |
```

---

### Template 3: Cost Model

```markdown
# Enterprise AI Cost Model

## Baseline Assumptions

### Usage Profile
- **Daily active users:** [Number]
- **Requests per user per day:** [Number]
- **Average tokens per request:** [Input] / [Output]
- **Peak hours:** [Time range], [X]x multiplier

### Growth Projections
| Period | Users | Requests/Day | Monthly Tokens |
|--------|-------|--------------|----------------|
| Month 1 | | | |
| Month 6 | | | |
| Month 12 | | | |
| Month 24 | | | |

## AI API Costs

### Model Pricing (as of [date])
| Model | Input (per 1M tokens) | Output (per 1M tokens) |
|-------|----------------------|------------------------|
| [Model 1] | $X.XX | $X.XX |
| [Model 2] | $X.XX | $X.XX |

### Monthly Projections
| Period | Input Tokens | Output Tokens | AI Cost |
|--------|--------------|---------------|---------|
| Month 1 | | | $X,XXX |
| Month 6 | | | $X,XXX |
| Month 12 | | | $X,XXX |

## Infrastructure Costs

### Compute
| Component | Type | Monthly Cost |
|-----------|------|--------------|
| API Gateway | [Requests-based] | $XXX |
| Functions/Containers | [Details] | $XXX |
| Database | [Type, size] | $XXX |
| Cache | [Type, size] | $XXX |

### Storage & Transfer
| Component | Volume | Monthly Cost |
|-----------|--------|--------------|
| Object storage | X GB | $XXX |
| Database storage | X GB | $XXX |
| Data transfer | X GB | $XXX |

## Operational Costs

| Category | Monthly Cost | Notes |
|----------|--------------|-------|
| Monitoring tools | $XXX | [Datadog/CloudWatch/etc.] |
| Security tools | $XXX | [WAF, SIEM, etc.] |
| Support tier | $XXX | [Enterprise support] |
| Backup/DR | $XXX | [Details] |

## Total Cost Summary

| Period | AI API | Infrastructure | Operations | Total |
|--------|--------|----------------|------------|-------|
| Month 1 | $X,XXX | $XXX | $XXX | $X,XXX |
| Month 6 | $XX,XXX | $X,XXX | $XXX | $XX,XXX |
| Month 12 | $XX,XXX | $X,XXX | $X,XXX | $XX,XXX |
| **Year 1 Total** | | | | **$XXX,XXX** |

## Cost Optimization Strategies

### Identified Opportunities
1. **[Strategy]:** [Description and potential savings]
2. **[Strategy]:** [Description and potential savings]
3. **[Strategy]:** [Description and potential savings]

### Optimization Roadmap
| Strategy | Implementation Effort | Savings | Timeline |
|----------|----------------------|---------|----------|
| Response caching | Medium | 20-30% | Month 2 |
| Model selection optimization | Low | 10-15% | Month 1 |
| Reserved capacity | Low | 15-25% | Month 3 |

## Cost per Transaction Analysis

| Scenario | Tokens | AI Cost | Infra Cost | Total | Target |
|----------|--------|---------|------------|-------|--------|
| Simple query | 500 | $0.XX | $0.XX | $0.XX | <$0.XX |
| Complex task | 5,000 | $0.XX | $0.XX | $0.XX | <$0.XX |
| Document processing | 20,000 | $0.XX | $0.XX | $0.XX | <$0.XX |
```

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| AWS Bedrock Pricing | Documentation | [AWS Bedrock Pricing](https://aws.amazon.com/bedrock/pricing/) | Platform comparison, cost modeling |
| Azure OpenAI Pricing | Documentation | [Azure OpenAI Pricing](https://azure.microsoft.com/en-us/pricing/details/cognitive-services/openai-service/) | Platform comparison, cost modeling |
| Google Vertex AI Pricing | Documentation | [Vertex AI Pricing](https://cloud.google.com/vertex-ai/pricing) | Platform comparison, cost modeling |
| OWASP AI Security | Guide | [OWASP AI Security](https://owasp.org/www-project-ai-security-and-privacy-guide/) | Security architecture design |
| Cloud Security Alliance | Resources | [CSA Cloud Controls](https://cloudsecurityalliance.org/) | Compliance mapping |

---

### Module Appendix References

For this session's exercises, you may need:

- **Appendix A:** Platform Comparison Matrix - Complete feature comparison tables
- **Appendix B:** Deployment Checklist - Security and compliance requirements
- **Appendix C:** Evaluation Rubric - Criteria for assessing exercise quality

See the main module document for full appendix content.

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to next session, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Evaluate cloud AI platforms using weighted scoring | Exercise 1.1 completed with documented scores | ☐ |
| 2 | Design deployment architectures for different scenarios | Exercise 1.2 architecture matches workload requirements | ☐ |
| 3 | Apply defense-in-depth security to AI systems | Exercise 1.2 addresses all five security layers | ☐ |
| 4 | Create platform selection frameworks | Exercise 1.1 recommendation is data-driven and defendable | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Location | Complete? |
|-------------|-----------|----------|-----------|
| Platform comparison | `platform-comparison-analysis.md` | Working directory | ☐ |
| Security architecture | `security-architecture-design.md` | Working directory | ☐ |
| Cost model | `cost-model.md` | Working directory | ☐ |

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this session?** Which concept or framework suddenly made sense for you?

2. **What's still fuzzy?** What do you need more practice or clarification on?

3. **How will you apply this?** Name one real client engagement where you'll use platform selection framework.

4. **What surprised you?** Was anything harder or easier than expected?

---

## Getting Help

### Quick Answers
- **Async Support Channel** - Post questions, usually answered within 24 hours
- **Peer Discussion** - Tag your cohort for quick tips on exercises

### Common Questions This Session

**Q: What if all platforms score similarly in my weighted scoring?**
A: Look more closely at model requirements and existing infrastructure - these usually create clear differentiation. If truly tied, document pros/cons of each and let client priorities decide.

**Q: How detailed should my security architecture be?**
A: Specific enough to implement. "Use encryption" is too vague. "AES-256 encryption at rest using AWS KMS with customer-managed keys" is specific.

**Q: Where do I find current pricing for cost modeling?**
A: Platform documentation links in External Resources section. Pricing changes frequently - note the date you checked pricing.

**Q: Can I use hybrid deployment patterns (combining serverless + containerized)?**
A: Yes, many production systems use hybrid approaches. For exercises, start with one primary pattern to keep scope manageable.

**Q: What if I don't have experience with cloud platforms?**
A: Focus on the frameworks and patterns - these apply regardless of specific platform. Use documentation links to research platform-specific details as needed.

### When to Ask for Help

- **Before asking:** Check this guide's troubleshooting sections and Common Questions
- **Good to ask:** "I applied weighted scoring but all platforms tied at 7/10. Here's my scenario and scores..."
- **Include:** Your specific scenario, what you tried, and the result

---

## Looking Ahead

### Next Session Preview: Session 2 - Production Deployment & Operations

**Focus:**
Scaling patterns, hybrid/on-premises architectures, operations and observability, deployment strategies, and the module capstone project.

**How It Builds on This Session:**
Session 2 takes the platform and architecture decisions you make today and covers how to deploy, scale, monitor, and maintain those systems in production.

**To Prepare:**
- [ ] Complete all Session 1 exercises (platform comparison, security architecture, cost model)
- [ ] Review your platform selection - Session 2 builds on this choice
- [ ] Think about operational challenges: how do you monitor AI systems? How do you handle scaling?

---

## Glossary

| Term | Definition |
|------|------------|
| **Defense-in-depth** | Layered security approach where multiple independent controls protect systems |
| **Deployment pattern** | Standard architectural approach for deploying applications (serverless, containerized, queue-based) |
| **IAM** | Identity and Access Management - authentication and authorization services |
| **PII** | Personally Identifiable Information - data that can identify specific individuals |
| **Platform selection framework** | Structured decision-making process using decision trees and weighted scoring |
| **Prompt injection** | Attack where user manipulates AI behavior through carefully crafted prompts |
| **Rate limiting** | Controlling the number of requests a user/client can make in a time period |
| **Serverless** | Cloud computing model where provider manages servers and scales automatically |
| **Weighted scoring** | Evaluation method where factors are scored and multiplied by importance weights |
| **VPC/VNet** | Virtual Private Cloud/Network - isolated network environment in cloud |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial participant guide created |

---

**Navigation:** Session 1 | [Session 2 →](../session-2/participant-guide.md)
