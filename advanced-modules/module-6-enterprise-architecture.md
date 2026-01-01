# **Advanced Module 6: Enterprise AI Architecture**

## **2 Weeks | 45 min live + 75 min homework per week**

-----

## **Prerequisites**

- Block 3 Certification: AI Automation Architect
- Experience with cloud platforms (AWS, Azure, or GCP)
- Understanding of enterprise security principles
- Familiarity with containerization concepts (Docker)
- 50+ agent executions completed
- Participation in at least one enterprise technology decision

-----

## **Module Overview**

**Target Audience:** Block 3 graduates who advise clients on AI platform selection, deployment architecture, and enterprise-scale AI agent implementations.

**Learning Objectives:**
- Evaluate and compare major cloud AI platforms (AWS Bedrock, Google Vertex AI, Azure OpenAI)
- Design hybrid and on-premises AI architectures for regulated industries
- Architect secure, scalable agent deployment patterns
- Create cost models and optimization strategies for AI at scale
- Build platform selection decision frameworks for client engagements
- Document enterprise architecture recommendations

**Capstone:** Enterprise AI Architecture Proposal
- Platform comparison analysis for specific client scenario
- Reference architecture diagram with security controls
- Cost projection model with scaling scenarios
- Deployment strategy and migration roadmap
- Executive presentation deck

-----

## **Week 1: Cloud AI Architecture Patterns**

### **Entry Criteria**

- [ ] Block 3 completed with working agent system
- [ ] Access to at least one cloud platform (trial acceptable)
- [ ] Understanding of basic networking concepts
- [ ] Familiarity with API authentication patterns

### **Exit Criteria**

- [ ] Major cloud AI platforms compared and understood
- [ ] Platform selection framework created
- [ ] Security architecture patterns documented
- [ ] First architecture diagram completed
- [ ] Cost model template populated

-----

### **Workshop Content (45 minutes)**

**Segment 1: Cloud AI Platform Landscape (12 min)**

- **The Big Three comparison:**

  | Capability | AWS Bedrock | Azure OpenAI | Google Vertex AI |
  |------------|-------------|--------------|------------------|
  | **Model Access** | Claude, Llama, Titan | GPT-4, GPT-3.5 | Gemini, PaLM, Claude |
  | **Fine-tuning** | Select models | GPT-3.5-turbo | Most models |
  | **Agents** | Bedrock Agents | Assistants API | Vertex AI Agents |
  | **RAG Support** | Knowledge Bases | Azure AI Search | Vertex AI Search |
  | **Enterprise SSO** | IAM, SAML | Entra ID native | Cloud IAM |
  | **Compliance** | FedRAMP, HIPAA | FedRAMP, HIPAA | FedRAMP, HIPAA |

- **Platform selection factors:**
  - Existing cloud footprint
  - Model requirements (specific models vs flexibility)
  - Compliance and data residency needs
  - Team expertise and training investment
  - Integration with existing services
  - Pricing structure alignment

- **Multi-cloud considerations:**
  - When to use multiple platforms
  - Abstraction layers and portability
  - Complexity vs flexibility trade-offs

**Segment 2: Deployment Architecture Patterns (12 min)**

- **Pattern 1: Serverless Agent Architecture**
  ```
  ┌─────────────────────────────────────────────────────────┐
  │                    API Gateway                          │
  │              (Rate limiting, Auth)                      │
  └─────────────────────┬───────────────────────────────────┘
                        │
  ┌─────────────────────▼───────────────────────────────────┐
  │              Lambda/Cloud Function                       │
  │         (Agent Orchestration Logic)                      │
  └─────────────────────┬───────────────────────────────────┘
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
  ┌───────────┐ ┌───────────┐ ┌───────────┐
  │  Bedrock  │ │ DynamoDB  │ │    S3     │
  │   API     │ │  (State)  │ │  (Files)  │
  └───────────┘ └───────────┘ └───────────┘
  ```

  - **Best for:** Variable workloads, cost optimization, rapid scaling
  - **Limitations:** Cold starts, execution time limits, stateless complexity

- **Pattern 2: Containerized Agent Architecture**
  ```
  ┌─────────────────────────────────────────────────────────┐
  │                 Load Balancer                            │
  └─────────────────────┬───────────────────────────────────┘
                        │
  ┌─────────────────────▼───────────────────────────────────┐
  │              Kubernetes Cluster                          │
  │  ┌─────────┐  ┌─────────┐  ┌─────────┐                 │
  │  │ Agent   │  │ Agent   │  │ Agent   │                 │
  │  │ Pod 1   │  │ Pod 2   │  │ Pod 3   │                 │
  │  └─────────┘  └─────────┘  └─────────┘                 │
  └─────────────────────────────────────────────────────────┘
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
  ┌───────────┐ ┌───────────┐ ┌───────────┐
  │  AI API   │ │  Redis    │ │ Postgres  │
  │           │ │  (Cache)  │ │  (State)  │
  └───────────┘ └───────────┘ └───────────┘
  ```

  - **Best for:** Consistent performance, complex orchestration, long-running tasks
  - **Limitations:** Higher baseline cost, operational complexity

- **Pattern 3: Queue-Based Processing Architecture**
  ```
  ┌─────────┐     ┌─────────────┐     ┌─────────────────┐
  │  API    │────▶│   Queue     │────▶│  Worker Pool    │
  │ Gateway │     │ (SQS/Pub)   │     │ (Agent Fleet)   │
  └─────────┘     └─────────────┘     └─────────────────┘
       │                                      │
       │         ┌─────────────┐              │
       └────────▶│  Status DB  │◀─────────────┘
                 └─────────────┘
  ```

  - **Best for:** Batch processing, rate limiting, async workflows
  - **Limitations:** Latency for real-time needs, complexity in status tracking

**Segment 3: Security Architecture Fundamentals (12 min)**

- **Defense in depth for AI systems:**
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

- **Secrets management patterns:**

  | Pattern | Implementation | Use Case |
  |---------|----------------|----------|
  | **Vault-based** | HashiCorp Vault, AWS Secrets Manager | Dynamic secrets, rotation |
  | **Environment** | Kubernetes Secrets, Parameter Store | Simple deployments |
  | **Managed Identity** | AWS IAM Roles, Azure MSI | Cloud-native apps |

- **API Gateway security:**
  - Rate limiting per client/tenant
  - Request validation and sanitization
  - JWT/OAuth token validation
  - IP allowlisting for B2B
  - DDoS protection

- **Data protection considerations:**
  - PII detection and redaction before AI processing
  - Prompt injection prevention
  - Output filtering for sensitive data
  - Audit logging for compliance

**Segment 4: Platform Selection Decision Framework (9 min)**

- **Decision tree approach:**
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

- **Weighted scoring model:**

  | Factor | Weight | Platform A | Platform B | Platform C |
  |--------|--------|------------|------------|------------|
  | Model availability | 25% | | | |
  | Existing integration | 20% | | | |
  | Security/Compliance | 20% | | | |
  | Cost structure | 15% | | | |
  | Team expertise | 10% | | | |
  | Support/SLAs | 10% | | | |
  | **Weighted Total** | 100% | | | |

- **Red flags in platform selection:**
  - Vendor lock-in with proprietary features
  - Missing compliance certifications
  - Unclear pricing for scale
  - Limited regional availability
  - Poor documentation or support

-----

### **Self-Paced Exercises (75 minutes total)**

**Exercise 1.1: Platform Comparison Analysis (25 minutes)**

*Compare platforms for a specific use case*

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
1. [Strength]
2. [Strength]
3. [Strength]

#### Limitations for This Scenario
1. [Limitation]
2. [Limitation]

#### Relevant Features
- Model options: [List applicable models]
- Integration points: [Existing AWS services to leverage]
- Compliance: [Relevant certifications]

#### Cost Estimate
- Per-request pricing: $X
- Monthly estimate at scale: $X
- Hidden costs: [Training, data transfer, etc.]

---

### Azure OpenAI

#### Strengths for This Scenario
1. [Strength]
2. [Strength]
3. [Strength]

#### Limitations for This Scenario
1. [Limitation]
2. [Limitation]

#### Relevant Features
- Model options: [List applicable models]
- Integration points: [Existing Azure services]
- Compliance: [Relevant certifications]

#### Cost Estimate
- Per-request pricing: $X
- Monthly estimate at scale: $X
- Hidden costs: [List]

---

### Google Vertex AI

#### Strengths for This Scenario
1. [Strength]
2. [Strength]
3. [Strength]

#### Limitations for This Scenario
1. [Limitation]
2. [Limitation]

#### Relevant Features
- Model options: [List applicable models]
- Integration points: [Existing GCP services]
- Compliance: [Relevant certifications]

#### Cost Estimate
- Per-request pricing: $X
- Monthly estimate at scale: $X
- Hidden costs: [List]

---

## Weighted Scoring

| Factor | Weight | AWS Bedrock | Azure OpenAI | Vertex AI |
|--------|--------|-------------|--------------|-----------|
| Model fit | 25% | /10 | /10 | /10 |
| Integration ease | 20% | /10 | /10 | /10 |
| Compliance match | 20% | /10 | /10 | /10 |
| Cost efficiency | 15% | /10 | /10 | /10 |
| Team readiness | 10% | /10 | /10 | /10 |
| Support quality | 10% | /10 | /10 | /10 |
| **Weighted Score** | 100% | X.X | X.X | X.X |

## Recommendation
[Primary recommendation with rationale]

## Risk Mitigation
[How to address limitations of recommended platform]
```

**Deliverable:** `platform-comparison-analysis.md`

-----

**Exercise 1.2: Security Architecture Design (30 minutes)**

*Design security controls for enterprise AI deployment*

```markdown
# Security Architecture Design

## System Overview
- **Platform:** [Selected platform]
- **Deployment pattern:** [Serverless/Container/Queue-based]
- **Data sensitivity:** [Public/Internal/Confidential/Restricted]

## Network Security

### Architecture Diagram
```
[Draw your network architecture showing:]
- VPC/VNet boundaries
- Public/Private subnets
- Firewall rules
- Private endpoints
- Load balancers
```

### Network Controls
| Control | Implementation | Status |
|---------|----------------|--------|
| VPC isolation | [Details] | [ ] Planned |
| Private endpoints | [Details] | [ ] Planned |
| Firewall rules | [Details] | [ ] Planned |
| DDoS protection | [Details] | [ ] Planned |

---

## Identity & Access Management

### Service Authentication
| Service | Auth Method | Secret Storage |
|---------|-------------|----------------|
| AI API | [API Key/IAM Role] | [Secrets Manager] |
| Database | [IAM/Password] | [Location] |
| External APIs | [OAuth/API Key] | [Location] |

### User Authentication
- **Method:** [OAuth 2.0 / SAML / API Keys]
- **Provider:** [Okta / Entra ID / Cognito]
- **MFA:** [Required/Optional]

### Authorization Model
- **Pattern:** [RBAC / ABAC / Custom]
- **Roles defined:**
  - Admin: [Permissions]
  - Developer: [Permissions]
  - Operator: [Permissions]
  - Auditor: [Permissions]

---

## Data Protection

### Encryption
| Data State | Method | Key Management |
|------------|--------|----------------|
| At rest | [AES-256] | [KMS/Customer-managed] |
| In transit | [TLS 1.3] | [Certificate source] |
| In processing | [Details] | [Details] |

### Data Handling
- **PII Detection:** [Tool/Method]
- **Redaction strategy:** [Before/After AI processing]
- **Retention policy:** [Duration, deletion process]

---

## Application Security

### Input Validation
- Prompt injection prevention: [Method]
- Input size limits: [Values]
- Content filtering: [Approach]

### Output Filtering
- PII detection in responses: [Method]
- Harmful content filtering: [Approach]
- Confidence thresholds: [Values]

---

## Monitoring & Audit

### Logging Strategy
| Log Type | Retention | Storage |
|----------|-----------|---------|
| Access logs | [Days] | [Location] |
| AI request/response | [Days] | [Location] |
| Security events | [Days] | [Location] |
| Audit trail | [Days] | [Location] |

### Alerting
| Alert | Condition | Response |
|-------|-----------|----------|
| Unusual volume | >X requests/min | [Action] |
| Auth failures | >N in Y minutes | [Action] |
| Cost anomaly | >X% above baseline | [Action] |

---

## Compliance Mapping

| Requirement | Control | Evidence |
|-------------|---------|----------|
| [SOC 2 - Access Control] | [Implementation] | [Documentation] |
| [HIPAA - Encryption] | [Implementation] | [Documentation] |
| [GDPR - Data handling] | [Implementation] | [Documentation] |
```

**Deliverable:** `security-architecture-design.md`

-----

**Exercise 1.3: Cost Modeling (20 minutes)**

*Build a cost projection for enterprise scale*

```markdown
# Enterprise AI Cost Model

## Baseline Assumptions

### Usage Profile
- **Daily active users:** [Number]
- **Requests per user per day:** [Number]
- **Average tokens per request:** [Input/Output]
- **Peak hours:** [Time range, multiplier]

### Growth Projections
| Period | Users | Requests/Day | Monthly Tokens |
|--------|-------|--------------|----------------|
| Month 1 | | | |
| Month 6 | | | |
| Month 12 | | | |
| Month 24 | | | |

---

## AI API Costs

### Model Pricing
| Model | Input (per 1M tokens) | Output (per 1M tokens) |
|-------|----------------------|------------------------|
| [Model 1] | $X.XX | $X.XX |
| [Model 2] | $X.XX | $X.XX |
| [Model 3] | $X.XX | $X.XX |

### Monthly Projections
| Period | Input Tokens | Output Tokens | AI Cost |
|--------|--------------|---------------|---------|
| Month 1 | | | $X,XXX |
| Month 6 | | | $X,XXX |
| Month 12 | | | $X,XXX |

---

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

---

## Operational Costs

| Category | Monthly Cost | Notes |
|----------|--------------|-------|
| Monitoring tools | $XXX | [Details] |
| Security tools | $XXX | [Details] |
| Support tier | $XXX | [Details] |
| Backup/DR | $XXX | [Details] |

---

## Total Cost Summary

| Period | AI API | Infrastructure | Operations | Total |
|--------|--------|----------------|------------|-------|
| Month 1 | | | | $X,XXX |
| Month 6 | | | | $X,XXX |
| Month 12 | | | | $X,XXX |
| Year 1 Total | | | | $XX,XXX |

---

## Cost Optimization Strategies

### Identified Opportunities
1. **[Strategy]:** [Potential savings]
2. **[Strategy]:** [Potential savings]
3. **[Strategy]:** [Potential savings]

### Optimization Roadmap
| Strategy | Implementation Effort | Savings | Timeline |
|----------|----------------------|---------|----------|
| Caching responses | Medium | 20-30% | Month 2 |
| Model selection optimization | Low | 10-15% | Month 1 |
| Reserved capacity | Low | 15-25% | Month 3 |

---

## Cost per Transaction Analysis

| Scenario | Tokens | AI Cost | Infra Cost | Total | Target |
|----------|--------|---------|------------|-------|--------|
| Simple query | 500 | $0.XX | $0.XX | $0.XX | <$0.XX |
| Complex task | 5000 | $0.XX | $0.XX | $0.XX | <$0.XX |
| Document processing | 20000 | $0.XX | $0.XX | $0.XX | <$0.XX |
```

**Deliverable:** `cost-model.md`

-----

## **Week 2: Production Deployment & Operations**

### **Entry Criteria**

- [ ] Platform comparison completed
- [ ] Security architecture designed
- [ ] Cost model created
- [ ] Understanding of deployment patterns

### **Exit Criteria**

- [ ] Deployment strategy documented
- [ ] Scaling patterns implemented
- [ ] Operations runbook created
- [ ] Module capstone delivered
- [ ] Executive presentation ready

-----

### **Workshop Content (45 minutes)**

**Segment 1: Scaling Patterns for AI Workloads (12 min)**

- **Auto-scaling strategies:**

  | Strategy | Trigger | Best For |
  |----------|---------|----------|
  | **Request-based** | Requests/second | Synchronous APIs |
  | **Queue-depth** | Messages in queue | Async processing |
  | **CPU/Memory** | Resource utilization | Container workloads |
  | **Custom metric** | Business KPIs | Complex workflows |
  | **Scheduled** | Time of day | Predictable patterns |

- **Scaling configuration example:**
  ```json
  {
    "auto_scaling": {
      "min_instances": 2,
      "max_instances": 50,
      "target_cpu_utilization": 70,
      "scale_up_threshold": {
        "requests_per_second": 100,
        "queue_depth": 1000
      },
      "scale_down_delay_seconds": 300,
      "scale_up_cooldown_seconds": 60
    }
  }
  ```

- **Load balancing for AI:**
  - Session affinity for multi-turn conversations
  - Health checks with AI-specific probes
  - Weighted routing for A/B testing
  - Geographic routing for latency

- **Capacity planning:**
  - Token throughput limits
  - Concurrent request limits
  - Burst handling strategies
  - Reserved capacity vs on-demand

**Segment 2: Hybrid and On-Premises Architectures (12 min)**

- **When to consider on-premises:**
  - Data sovereignty requirements
  - Air-gapped environments
  - Ultra-low latency needs
  - Cost optimization at extreme scale
  - Regulatory mandates

- **Hybrid architecture patterns:**

  ```
  Pattern A: Data On-Prem, AI in Cloud
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

  Pattern B: Edge Processing with Cloud AI
  ┌─────────────┐   ┌─────────────┐   ┌─────────────┐
  │   Edge      │   │   Regional  │   │   Central   │
  │ ┌─────────┐ │   │ ┌─────────┐ │   │ ┌─────────┐ │
  │ │ Filter  │─┼──▶│ │ Process │─┼──▶│ │Cloud AI │ │
  │ │ & Cache │ │   │ │ & Route │ │   │ │   API   │ │
  │ └─────────┘ │   │ └─────────┘ │   │ └─────────┘ │
  └─────────────┘   └─────────────┘   └─────────────┘
  ```

- **On-premises AI options:**

  | Option | Models | Hardware | Use Case |
  |--------|--------|----------|----------|
  | **Self-hosted LLM** | Llama, Mistral | GPU servers | Full control |
  | **Private cloud** | Vendor models | Dedicated region | Compliance |
  | **Appliance** | Pre-configured | Vendor hardware | Simplicity |

- **Connectivity considerations:**
  - VPN vs Direct Connect vs ExpressRoute
  - Latency requirements
  - Bandwidth for token streaming
  - Failover strategies

**Segment 3: Operations and Observability (12 min)**

- **Observability stack for AI:**
  ```
  ┌─────────────────────────────────────────────────────────┐
  │                   Dashboards & Alerts                    │
  │              (Grafana, Datadog, CloudWatch)             │
  └─────────────────────────┬───────────────────────────────┘
                            │
  ┌─────────────┬───────────┴───────────┬─────────────┐
  │   Metrics   │        Logs           │   Traces    │
  │ (Prometheus)│    (ELK, CloudWatch)  │   (Jaeger)  │
  └─────────────┴───────────────────────┴─────────────┘
                            │
  ┌─────────────────────────┴───────────────────────────────┐
  │                  AI Agent System                         │
  │  ┌──────────┐  ┌──────────┐  ┌──────────┐              │
  │  │Orchestrator│ │  Agents  │  │  Tools   │              │
  │  └──────────┘  └──────────┘  └──────────┘              │
  └─────────────────────────────────────────────────────────┘
  ```

- **AI-specific metrics:**

  | Metric | Description | Alert Threshold |
  |--------|-------------|-----------------|
  | Token usage rate | Tokens/minute | >80% of limit |
  | Response latency | P50, P95, P99 | P95 > 10s |
  | Error rate | Failed requests % | >5% |
  | Cost per request | $/request | >target |
  | Quality score | Output quality | <threshold |

- **Logging best practices:**
  - Log request/response (sanitized)
  - Include trace IDs across services
  - Capture token counts
  - Record model versions
  - Track prompt templates used

- **Incident response for AI systems:**
  ```
  1. Detect: Automated alerting on metrics
  2. Triage: Classify as AI vs infrastructure issue
  3. Contain: Circuit breaker, fallback, or disable
  4. Investigate: Logs, traces, recent changes
  5. Resolve: Fix root cause
  6. Review: Post-incident analysis
  ```

**Segment 4: Enterprise Deployment Strategy (9 min)**

- **Deployment phases:**

  | Phase | Duration | Goals | Success Criteria |
  |-------|----------|-------|------------------|
  | **Pilot** | 4-6 weeks | Validate approach | 10 users, positive feedback |
  | **Limited** | 8-12 weeks | Scale validation | 100 users, SLAs met |
  | **General** | Ongoing | Full rollout | All users, optimized |

- **Migration strategies:**
  - **Big bang:** One-time cutover (high risk, fast)
  - **Parallel run:** Both systems active (safe, expensive)
  - **Phased:** Gradual user migration (balanced)
  - **Feature flags:** Toggle per feature/user (flexible)

- **Rollback planning:**
  - Define rollback triggers
  - Document rollback procedure
  - Test rollback in staging
  - Maintain previous version

- **Change management:**
  - Stakeholder communication plan
  - Training program
  - Support escalation path
  - Feedback collection mechanism

-----

### **Self-Paced Exercises (75 minutes total)**

**Exercise 2.1: Deployment Strategy Document (25 minutes)**

*Create deployment plan for enterprise rollout*

```markdown
# Enterprise AI Deployment Strategy

## Executive Summary
[2-3 paragraphs summarizing deployment approach, timeline, and key decisions]

---

## Deployment Approach

### Strategy Selection
- **Chosen approach:** [Phased/Parallel/Big Bang]
- **Rationale:** [Why this approach]
- **Risk level:** [Low/Medium/High]

### Phase Plan

#### Phase 1: Pilot (Weeks 1-4)
- **Scope:** [Specific use cases, features]
- **Users:** [Number, criteria for selection]
- **Success criteria:**
  - [ ] [Criterion 1]
  - [ ] [Criterion 2]
  - [ ] [Criterion 3]
- **Go/No-Go decision point:** Week 4

#### Phase 2: Limited Availability (Weeks 5-12)
- **Scope:** [Expanded use cases]
- **Users:** [Target number, departments]
- **Success criteria:**
  - [ ] [Criterion 1]
  - [ ] [Criterion 2]
- **Go/No-Go decision point:** Week 12

#### Phase 3: General Availability (Week 13+)
- **Scope:** [Full functionality]
- **Users:** [All target users]
- **Ongoing metrics:** [What to track]

---

## Infrastructure Deployment

### Environment Strategy
| Environment | Purpose | Refresh Frequency |
|-------------|---------|-------------------|
| Development | Feature development | Continuous |
| Staging | Integration testing | Weekly |
| Pre-prod | Performance/Security | Bi-weekly |
| Production | Live system | Controlled releases |

### Deployment Pipeline
```
Code Commit → Build → Unit Tests → Security Scan
     ↓
Deploy to Staging → Integration Tests → Performance Tests
     ↓
Manual Approval → Deploy to Pre-prod → Validation
     ↓
Change Request → Deploy to Production → Smoke Tests → Monitor
```

### Rollback Procedure
1. [Step 1]
2. [Step 2]
3. [Step 3]
4. [Step 4]

---

## Scaling Configuration

### Auto-scaling Rules
```json
{
  "scaling_policy": {
    "min_replicas": X,
    "max_replicas": X,
    "metrics": [
      {
        "type": "cpu",
        "target_utilization": X
      },
      {
        "type": "custom",
        "name": "requests_per_second",
        "target": X
      }
    ]
  }
}
```

### Capacity Reservations
| Time Period | Reserved Capacity | On-Demand Buffer |
|-------------|-------------------|------------------|
| Business hours | X units | X% |
| Off-hours | X units | X% |
| Peak events | X units | X% |

---

## Risk Mitigation

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| API rate limits | Medium | High | Reserved capacity, caching |
| Model degradation | Low | High | Quality monitoring, rollback |
| Cost overrun | Medium | Medium | Budget alerts, usage caps |
| Security incident | Low | Critical | Defense in depth, response plan |

---

## Timeline

| Week | Milestone | Deliverable |
|------|-----------|-------------|
| 1 | Infrastructure ready | Environments provisioned |
| 2 | Security approved | Penetration test passed |
| 3 | Pilot users onboarded | Training complete |
| 4 | Pilot review | Go/No-Go decision |
| [Continue...]
```

**Deliverable:** `deployment-strategy.md`

-----

**Exercise 2.2: Operations Runbook (25 minutes)**

*Document operational procedures*

```markdown
# AI System Operations Runbook

## System Overview

### Architecture Summary
[Brief description with reference to architecture diagram]

### Key Components
| Component | Technology | Owner | Support |
|-----------|------------|-------|---------|
| API Gateway | [Service] | [Team] | [Contact] |
| Orchestrator | [Service] | [Team] | [Contact] |
| AI Backend | [Service] | [Team] | [Contact] |
| Database | [Service] | [Team] | [Contact] |

### Dependencies
| External Service | Purpose | SLA | Fallback |
|-----------------|---------|-----|----------|
| [AI Provider] | Model inference | 99.9% | [Alternative] |
| [Service 2] | [Purpose] | X% | [Alternative] |

---

## Monitoring

### Dashboard Links
- Production: [URL]
- Staging: [URL]
- Cost tracking: [URL]

### Key Metrics & Thresholds

| Metric | Warning | Critical | Dashboard |
|--------|---------|----------|-----------|
| Response latency P95 | >5s | >10s | [Link] |
| Error rate | >2% | >5% | [Link] |
| Token usage | >70% | >90% | [Link] |
| Cost/hour | >$X | >$X | [Link] |
| Queue depth | >1000 | >5000 | [Link] |

### Alert Routing
| Severity | Channel | Response Time |
|----------|---------|---------------|
| Critical | PagerDuty + Slack | 15 min |
| Warning | Slack #ai-alerts | 1 hour |
| Info | Email | Next business day |

---

## Common Procedures

### Procedure 1: Scaling Up Manually
**When:** Anticipated high load event
**Steps:**
1. [Step with command/action]
2. [Step with command/action]
3. [Step with command/action]
**Verification:** [How to confirm success]

### Procedure 2: Rotating API Keys
**When:** Scheduled or after suspected compromise
**Steps:**
1. [Step]
2. [Step]
3. [Step]
**Verification:** [How to confirm success]

### Procedure 3: Updating Model Version
**When:** New model version available
**Steps:**
1. [Step]
2. [Step]
3. [Step]
**Verification:** [How to confirm success]

### Procedure 4: Emergency Disable
**When:** Critical incident requiring immediate shutdown
**Steps:**
1. [Step]
2. [Step]
3. [Step]
**Verification:** [How to confirm success]

---

## Incident Response

### Severity Levels
| Level | Definition | Examples |
|-------|------------|----------|
| SEV1 | Complete outage | All requests failing |
| SEV2 | Partial outage | >20% errors |
| SEV3 | Degraded | High latency |
| SEV4 | Minor | Cosmetic issues |

### Incident Workflow
```
Detection → Acknowledge → Assess Severity
     ↓
Communicate → Investigate → Resolve
     ↓
Post-Incident Review → Document → Close
```

### Common Issues & Resolutions

#### Issue: High Error Rate
**Symptoms:** Error rate >5%, alerts firing
**Potential Causes:**
1. AI API issues - Check provider status page
2. Rate limiting - Check token usage
3. Bad deployment - Check recent changes

**Resolution Steps:**
1. [Step]
2. [Step]
3. [Step]

#### Issue: High Latency
**Symptoms:** P95 >10s
**Potential Causes:**
1. Model congestion - Check AI provider
2. Database slow - Check query performance
3. Network issues - Check connectivity

**Resolution Steps:**
1. [Step]
2. [Step]
3. [Step]

#### Issue: Cost Spike
**Symptoms:** Hourly cost >2x normal
**Potential Causes:**
1. Traffic spike - Check request volume
2. Prompt bloat - Check token counts
3. Loop detection - Check for repeated requests

**Resolution Steps:**
1. [Step]
2. [Step]
3. [Step]

---

## Maintenance Windows

| Activity | Frequency | Duration | Impact |
|----------|-----------|----------|--------|
| Security patches | Weekly | 30 min | None (rolling) |
| Model updates | Monthly | 1 hour | Degraded |
| Infrastructure updates | Quarterly | 2 hours | Possible outage |

---

## Contacts

### Escalation Path
1. **L1:** On-call engineer - [Contact method]
2. **L2:** Senior engineer - [Contact method]
3. **L3:** Architecture team - [Contact method]
4. **Management:** [Name] - [Contact method]

### Vendor Support
| Vendor | Support Portal | SLA |
|--------|---------------|-----|
| [AI Provider] | [URL] | [Response time] |
| [Cloud Provider] | [URL] | [Response time] |
```

**Deliverable:** `operations-runbook.md`

-----

**Exercise 2.3: Module Capstone - Enterprise Architecture Proposal (25 minutes)**

*Create client-ready architecture recommendation*

```markdown
# Enterprise AI Architecture Proposal

## Client: [Client Name]
## Prepared by: [Your Name]
## Date: [Date]

---

## Executive Summary

[3-4 paragraphs covering:]
- Business context and AI initiative goals
- Recommended platform and architecture
- Key benefits and expected outcomes
- Investment summary and timeline

---

## Business Requirements

### Primary Use Cases
1. **[Use Case 1]:** [Description, volume, priority]
2. **[Use Case 2]:** [Description, volume, priority]
3. **[Use Case 3]:** [Description, volume, priority]

### Success Criteria
| Metric | Current State | Target | Timeline |
|--------|---------------|--------|----------|
| [Metric 1] | | | |
| [Metric 2] | | | |
| [Metric 3] | | | |

### Constraints
- **Budget:** [Range]
- **Timeline:** [Deadline]
- **Compliance:** [Requirements]
- **Integration:** [Existing systems]

---

## Platform Recommendation

### Selected Platform: [Platform Name]

#### Rationale
1. [Reason 1 - tied to requirement]
2. [Reason 2 - tied to requirement]
3. [Reason 3 - tied to requirement]

#### Comparison Summary
| Factor | Recommended | Alternative 1 | Alternative 2 |
|--------|-------------|---------------|---------------|
| Model fit | [Score] | [Score] | [Score] |
| Integration | [Score] | [Score] | [Score] |
| Cost | [Score] | [Score] | [Score] |
| **Overall** | **Best** | Viable | Not recommended |

#### Risks and Mitigations
| Risk | Mitigation |
|------|------------|
| [Risk 1] | [Mitigation] |
| [Risk 2] | [Mitigation] |

---

## Reference Architecture

### Architecture Diagram
```
[Insert detailed architecture diagram showing:]
- User entry points
- API Gateway / Load Balancer
- Compute layer (serverless/containers)
- AI services integration
- Data stores
- Security controls
- Monitoring stack
```

### Component Details

| Component | Service | Purpose | Sizing |
|-----------|---------|---------|--------|
| API Gateway | [Service] | Auth, rate limiting | [Config] |
| Compute | [Service] | Agent orchestration | [Config] |
| AI Backend | [Service] | Model inference | [Config] |
| Vector DB | [Service] | RAG storage | [Config] |
| Cache | [Service] | Response caching | [Config] |
| Logging | [Service] | Observability | [Config] |

---

## Security Architecture

### Security Controls Summary
| Layer | Controls | Implementation |
|-------|----------|----------------|
| Network | VPC, Private endpoints | [Details] |
| Identity | OAuth 2.0, MFA | [Details] |
| Data | Encryption, DLP | [Details] |
| Application | Input validation, WAF | [Details] |
| Monitoring | SIEM, audit logs | [Details] |

### Compliance Mapping
| Requirement | Status | Evidence |
|-------------|--------|----------|
| [Requirement 1] | Addressed | [Control reference] |
| [Requirement 2] | Addressed | [Control reference] |

---

## Cost Analysis

### 12-Month Projection
| Category | Year 1 | Notes |
|----------|--------|-------|
| AI API costs | $XXX,XXX | [Assumptions] |
| Infrastructure | $XX,XXX | [Assumptions] |
| Operations | $XX,XXX | [Assumptions] |
| **Total** | **$XXX,XXX** | |

### Cost Optimization Roadmap
| Initiative | Savings | Timeline |
|------------|---------|----------|
| [Initiative 1] | $XX,XXX | Month X |
| [Initiative 2] | $XX,XXX | Month X |

### ROI Analysis
- **Investment:** $XXX,XXX (Year 1)
- **Expected benefits:** [Quantified benefits]
- **Payback period:** [Months]

---

## Implementation Roadmap

### Phase Timeline
```
Month 1-2: Foundation
├── Infrastructure provisioning
├── Security implementation
└── Development environment ready

Month 3-4: Pilot
├── Core features deployed
├── Pilot users onboarded
└── Initial feedback incorporated

Month 5-6: Scale
├── Full feature deployment
├── Broader user rollout
└── Performance optimization

Month 7+: Optimize
├── Cost optimization
├── Feature expansion
└── Continuous improvement
```

### Key Milestones
| Milestone | Target Date | Dependencies |
|-----------|-------------|--------------|
| Infrastructure ready | Month 1 | [Deps] |
| Security approved | Month 2 | [Deps] |
| Pilot launch | Month 3 | [Deps] |
| GA launch | Month 5 | [Deps] |

---

## Next Steps

### Immediate Actions (Next 2 Weeks)
1. [ ] [Action 1]
2. [ ] [Action 2]
3. [ ] [Action 3]

### Decision Points
| Decision | Owner | Deadline |
|----------|-------|----------|
| Platform approval | [Role] | [Date] |
| Budget approval | [Role] | [Date] |
| Security sign-off | [Role] | [Date] |

---

## Appendices

### Appendix A: Detailed Cost Model
[Reference to cost-model.md]

### Appendix B: Security Architecture Details
[Reference to security-architecture-design.md]

### Appendix C: Platform Comparison Details
[Reference to platform-comparison-analysis.md]
```

**Deliverable:** `enterprise-architecture-proposal.md` + Executive presentation

-----

# **APPENDICES**

## **Appendix A: Platform Comparison Template**

```markdown
# Cloud AI Platform Comparison Matrix

## Quick Reference

| Feature | AWS Bedrock | Azure OpenAI | Google Vertex AI |
|---------|-------------|--------------|------------------|
| **Models** | | | |
| Claude | Yes | No | Yes |
| GPT-4 | No | Yes | No |
| Gemini | No | No | Yes |
| Llama | Yes | No | Yes |
| **Capabilities** | | | |
| Fine-tuning | Limited | Yes | Yes |
| Agents/Assistants | Bedrock Agents | Assistants API | Vertex Agents |
| RAG | Knowledge Bases | AI Search | Vertex Search |
| Batch processing | Yes | Yes | Yes |
| **Enterprise** | | | |
| Private endpoints | Yes | Yes | Yes |
| Customer-managed keys | Yes | Yes | Yes |
| SLA | 99.9% | 99.9% | 99.9% |
| **Compliance** | | | |
| SOC 2 | Yes | Yes | Yes |
| HIPAA | Yes | Yes | Yes |
| FedRAMP | High | High | High |
| **Pricing Model** | | | |
| On-demand | $/token | $/token | $/token |
| Provisioned | Yes | Yes | Yes |
| Committed use | No | No | Yes |

## Detailed Pricing Comparison

### On-Demand Pricing (per 1M tokens)

| Model Tier | AWS Bedrock | Azure OpenAI | Google Vertex |
|------------|-------------|--------------|---------------|
| **Input tokens** | | | |
| Small model | $X.XX | $X.XX | $X.XX |
| Medium model | $X.XX | $X.XX | $X.XX |
| Large model | $X.XX | $X.XX | $X.XX |
| **Output tokens** | | | |
| Small model | $X.XX | $X.XX | $X.XX |
| Medium model | $X.XX | $X.XX | $X.XX |
| Large model | $X.XX | $X.XX | $X.XX |

## Regional Availability

| Region | AWS Bedrock | Azure OpenAI | Google Vertex |
|--------|-------------|--------------|---------------|
| US East | Yes | Yes | Yes |
| US West | Yes | Yes | Yes |
| EU West | Yes | Yes | Yes |
| EU Central | Yes | Yes | Yes |
| Asia Pacific | Limited | Limited | Yes |
```

-----

## **Appendix B: Deployment Checklist**

```markdown
# Enterprise AI Deployment Checklist

## Pre-Deployment

### Infrastructure
- [ ] Cloud accounts and subscriptions created
- [ ] Resource groups/projects organized
- [ ] Networking configured (VPC, subnets, peering)
- [ ] Private endpoints established
- [ ] DNS configured
- [ ] SSL certificates provisioned

### Security
- [ ] IAM roles and policies defined
- [ ] Service accounts created with least privilege
- [ ] Secrets management configured
- [ ] Encryption keys provisioned (KMS)
- [ ] Network security groups configured
- [ ] WAF rules implemented
- [ ] DDoS protection enabled

### Compliance
- [ ] Data classification completed
- [ ] Privacy impact assessment done
- [ ] Security review approved
- [ ] Compliance controls mapped
- [ ] Audit logging enabled

### Monitoring
- [ ] Logging infrastructure ready
- [ ] Metrics collection configured
- [ ] Dashboards created
- [ ] Alerts defined and tested
- [ ] On-call rotation established

## Deployment

### Application
- [ ] Container images built and scanned
- [ ] Configurations externalized
- [ ] Environment variables set
- [ ] Health checks configured
- [ ] Deployment manifests validated

### Testing
- [ ] Unit tests passing
- [ ] Integration tests passing
- [ ] Security scan clean
- [ ] Performance baseline established
- [ ] Load testing completed

### Rollout
- [ ] Deployment window scheduled
- [ ] Stakeholders notified
- [ ] Rollback procedure documented
- [ ] Support team briefed

## Post-Deployment

### Validation
- [ ] Health checks passing
- [ ] Smoke tests successful
- [ ] Metrics flowing
- [ ] Logs accessible
- [ ] User acceptance verified

### Documentation
- [ ] Runbook updated
- [ ] Architecture diagrams current
- [ ] API documentation published
- [ ] User guides available

### Handover
- [ ] Operations team trained
- [ ] Support procedures documented
- [ ] Escalation path confirmed
- [ ] Post-deployment review scheduled
```

-----

## **Appendix C: Module Evaluation Rubric**

```markdown
# Enterprise AI Architecture - Evaluation Rubric

**Total Points: 20 (4 criteria x 5 points each)**

## Criterion 1: Platform Analysis (5 points)

| Score | Description |
|-------|-------------|
| 5 | Comprehensive platform comparison with detailed scoring. Clear rationale for recommendation. Risk analysis included. Client-specific factors addressed. |
| 4 | Good comparison with scoring. Solid recommendation. Most factors considered. |
| 3 | Basic comparison. Recommendation provided. Some gaps in analysis. |
| 2 | Limited comparison. Weak rationale. Missing key factors. |
| 1 | No meaningful platform analysis. |

## Criterion 2: Security Architecture (5 points)

| Score | Description |
|-------|-------------|
| 5 | Defense-in-depth architecture. All layers addressed. Compliance mapped. Practical implementation details. AI-specific security considered. |
| 4 | Good security design. Most layers covered. Compliance addressed. |
| 3 | Basic security architecture. Core controls identified. |
| 2 | Incomplete security design. Major gaps. |
| 1 | No security architecture. |

## Criterion 3: Cost & Operations (5 points)

| Score | Description |
|-------|-------------|
| 5 | Detailed cost model with projections. Optimization strategies identified. Complete operations runbook. Realistic scaling plan. |
| 4 | Good cost analysis. Runbook covers key procedures. Reasonable scaling approach. |
| 3 | Basic cost estimate. Some operational procedures. |
| 2 | Limited financial analysis. Incomplete runbook. |
| 1 | No cost model or operations documentation. |

## Criterion 4: Enterprise Proposal Quality (5 points)

| Score | Description |
|-------|-------------|
| 5 | Client-ready proposal. Executive summary compelling. Clear recommendations. Realistic roadmap. Professional presentation. All components integrated. |
| 4 | Good proposal structure. Clear recommendations. Reasonable timeline. |
| 3 | Basic proposal. Recommendations present but could be clearer. |
| 2 | Draft quality. Missing key sections. Unclear recommendations. |
| 1 | No coherent proposal. |

## Certification Requirement
- **Minimum passing score:** 14/20
- **Distinction:** 18/20
```

-----

**END OF ADVANCED MODULE 6**
