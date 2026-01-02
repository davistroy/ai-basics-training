# **Advanced Module 6: Enterprise AI Architecture**
# **Session 1: Cloud AI Architecture Patterns**

## **45 min live + 75 min homework**

-----

## **Entry Criteria**

- [ ] Block 3 completed with working agent system
- [ ] Access to at least one cloud platform (trial acceptable)
- [ ] Understanding of basic networking concepts
- [ ] Familiarity with API authentication patterns

## **Exit Criteria**

- [ ] Major cloud AI platforms compared and understood
- [ ] Platform selection framework created
- [ ] Security architecture patterns documented
- [ ] First architecture diagram completed
- [ ] Cost model template populated

-----

## **Workshop Content (45 minutes)**

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

## **Self-Paced Exercises (75 minutes total)**

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
