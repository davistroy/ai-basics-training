# **ADVANCED MODULE 7 SESSION 2: Implementation & Compliance**

**Module:** Advanced Module 7: Enterprise AI Governance
**Session:** 2 of 2
**Estimated Self-Paced Time:** 75 minutes (includes 25-minute capstone)

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
- [Getting Help](#getting-help)

---

## Learning Objectives

By the end of this session, you will be able to:

| # | Objective | Practiced In |
|---|-----------|--------------|
| 1 | Map regulatory compliance requirements (EU AI Act, sector-specific) to AI systems | Exercise 2.1 |
| 2 | Design organizational governance structures (centralized vs. federated models) | Exercise 2.2, Capstone |
| 3 | Classify agent autonomy levels and define appropriate human oversight | Exercise 2.2, Capstone |
| 4 | Implement audit trail requirements and accountability frameworks | Exercise 2.2, Capstone |

---

## Entry Criteria

Before starting this session, confirm you have completed:

- [ ] Exercise 1.1: Governance Maturity Assessment from Session 1
- [ ] Exercise 1.2: Responsible AI Principles Mapping from Session 1
- [ ] Exercise 1.3: Agent Risk Register from Session 1
- [ ] Understanding of organizational context for your capstone

**Not ready?** Complete Session 1 exercises first - they feed directly into this week's capstone.

---

## Key Concepts

### Concept 1: EU AI Act Risk Tiers

**Definition:**
The EU AI Act is comprehensive legislation regulating AI systems using a four-tier risk-based approach: Unacceptable Risk (prohibited), High Risk (strict requirements), Limited Risk (transparency obligations), and Minimal Risk (no specific requirements).

**Why It Matters:**
The EU AI Act sets the global standard for AI regulation. Even non-EU organizations must comply if they offer products/services in the EU or if AI outputs are used in the EU. Understanding risk tiers determines compliance obligations.

**The Four Tiers:**

**Unacceptable Risk - PROHIBITED:**
- Social scoring by governments
- Real-time biometric identification in public spaces
- Manipulative AI exploiting vulnerabilities
- Cannot be deployed in EU

**High Risk - STRICT REQUIREMENTS:**
- AI used in: Employment (hiring, promotion), Credit scoring, Education, Law enforcement, Critical infrastructure, Medical devices
- Requirements: Risk management system, data governance, technical documentation, record-keeping, transparency, human oversight, accuracy/robustness/cybersecurity

**Limited Risk - TRANSPARENCY OBLIGATIONS:**
- Chatbots (must disclose they're AI)
- Emotion recognition systems
- Biometric categorization
- Deep fakes
- Must inform users AI is being used

**Minimal Risk - NO SPECIFIC REQUIREMENTS:**
- AI-enabled games
- Spam filters
- Recommendation systems (in most contexts)
- No mandatory compliance

**Common Mistake:**
Assuming US companies aren't subject to EU AI Act. The Act has extraterritorial reach similar to GDPR - if you have EU customers or your AI outputs affect EU residents, you must comply.

---

### Concept 2: Agent Autonomy Classification

**Definition:**
A five-level framework (0-4) for classifying how much autonomy an AI agent should have, ranging from Tool (human initiates every action) to Autonomous (AI operates independently with periodic audit).

**The Five Levels:**

| Level | Name | Description | Oversight | Example |
|-------|------|-------------|-----------|---------|
| 0 | Tool | Human initiates, AI assists | Full human control | Grammar checker with manual accept/reject |
| 1 | Assistant | AI suggests, human decides | Approval per action | Email draft AI (human reviews before sending) |
| 2 | Supervised | AI acts, human monitors | Real-time monitoring, veto capability | Customer service bot with live agent monitoring |
| 3 | Managed | AI operates, human oversight | Exception-based review | Fraud detection AI (human reviews flagged cases) |
| 4 | Autonomous | Independent operation | Periodic audit only | Automated trading within preset limits |

**Classification Decision Criteria:**

**Three Factors:**
1. **Impact:** What's the consequence if AI makes a mistake?
2. **Reversibility:** Can the decision be easily undone?
3. **Compliance Context:** Is this regulated, requiring human oversight?

**Decision Matrix:**
- Low impact + Reversible + Low compliance = Level 3-4 autonomy appropriate
- High impact + Not reversible + Any compliance = Level 0-1 autonomy only

**Example:** Medical diagnosis AI
- Impact: HIGH (wrong diagnosis harms patients)
- Reversibility: LOW (diagnosis influences treatment, hard to undo)
- Compliance: HIGH (FDA regulates medical AI, HIPAA applies)
- → Classification: Level 0-1 (Tool/Assistant requiring human approval)

**Autonomy Boundaries:**
Beyond classification, define operational boundaries:
- Financial limits (e.g., Level 3 can make decisions <$1,000)
- Stakeholder scope (e.g., Level 2 internal users only, Level 3 can serve customers)
- Data sensitivity (e.g., Level 2 non-PII only, Level 3 can access PII with controls)

**Escalation Triggers:**
Even autonomous agents must escalate to humans when:
- Confidence score below threshold (e.g., <0.7)
- Novel situation encountered (outside training distribution)
- Error rate spikes (exceeds baseline by >20%)
- User explicitly requests human review
- High-value or high-sensitivity scenario detected

**When NOT to Use:**
Don't classify based solely on technical capability. An AI might be capable of Level 4 autonomy, but governance may require Level 1 or 2 based on risk.

---

### Concept 3: Organizational Governance Structures

**Definition:**
The organizational model for AI governance, typically either Centralized (strong central authority), Federated (business unit autonomy with central guidance), or Hybrid (combination).

**Centralized Model:**
```
                  ┌─────────────────┐
                  │ AI Governance   │
                  │    Council      │
                  └────────┬────────┘
                           │
          ┌────────────────┼────────────────┐
          │                │                │
     ┌────┴────┐     ┌─────┴─────┐    ┌────┴────┐
     │ BU 1    │     │   BU 2    │    │  BU 3   │
     │ AI Team │     │  AI Team  │    │ AI Team │
     └─────────┘     └───────────┘    └─────────┘
```

**Characteristics:**
- Central governance council has strong authority
- Consistent policies and standards across organization
- All AI deployments approved centrally

**Best For:**
- Regulated industries (financial services, healthcare)
- High-risk AI systems
- Organizations with compliance-focused culture
- Smaller organizations (easier to coordinate centrally)

**Federated Model:**
```
     ┌─────────────────────────────────────────────┐
     │        AI Center of Excellence              │
     │     (Standards, Best Practices)             │
     └─────────────────────────────────────────────┘
                          ↕
     ┌─────────┐    ┌─────────┐    ┌─────────┐
     │ BU 1    │    │  BU 2   │    │  BU 3   │
     │ AI Gov  │    │ AI Gov  │    │ AI Gov  │
     │ (Local) │    │ (Local) │    │ (Local) │
     └─────────┘    └─────────┘    └─────────┘
```

**Characteristics:**
- Center of Excellence provides guidance, not control
- Business units have autonomy to adapt governance to local context
- Flexible implementation

**Best For:**
- Diverse organizations with different business models
- Lower-risk AI use cases
- Organizations with decentralized culture
- Large enterprises with distinct business units

**Key Governance Roles:**

| Role | Responsibility | When Needed |
|------|----------------|-------------|
| Chief AI Officer | Enterprise AI strategy, governance oversight | Medium+ AI maturity |
| AI Ethics Officer | Responsible AI principles, ethical escalations | High-risk AI deployments |
| AI Risk Manager | Risk framework implementation, monitoring | Regulated industries |
| AI Governance Lead | Policy implementation, process management | All organizations with AI |
| Model Validators | Independent technical review | High-risk AI systems |

**Governance Committees:**
- AI Steering Committee: Strategic direction
- AI Ethics Board: Principle conflicts, ethical decisions
- Model Risk Committee: Technical validation
- Data Governance Council: Data quality, privacy, lineage

---

### Concept 4: Audit Trails and Accountability

**Definition:**
Comprehensive logging of AI decisions and clear mapping of accountability from AI actions to responsible humans.

**Audit Record Structure:**
```json
{
  "timestamp": "2026-01-02T14:30:00Z",
  "agent_id": "loan-approval-agent-v2.1",
  "action_type": "decision",
  "input_summary": "Loan application #12345, amount $50K",
  "output_summary": "Application approved, rate 5.2%",
  "reasoning_trace": "Credit score 750, income sufficient, DTI 28%",
  "data_accessed": ["credit_bureau", "income_verification", "bank_statements"],
  "human_oversight": {
    "type": "none",
    "approver": null,
    "timestamp": null
  },
  "confidence_score": 0.89,
  "model_version": "v2.1.3",
  "outcome": "success"
}
```

**Why Each Field Matters:**
- **Timestamp:** Regulatory compliance, chronological reconstruction
- **Agent ID:** Accountability, debugging, version tracking
- **Action type:** Classification for review and analysis
- **Input/Output:** Decision reconstruction, dispute resolution
- **Reasoning trace:** Explainability, regulatory requirement
- **Data accessed:** Privacy compliance, data lineage
- **Human oversight:** Compliance demonstration, accountability
- **Confidence:** Quality control, escalation verification
- **Model version:** Rollback capability, change tracking
- **Outcome:** Performance monitoring, bias detection

**Retention Requirements:**
- **Regulatory:** Often 5-7 years (e.g., SR 11-7 in financial services)
- **Legal:** Statute of limitations + buffer
- **Operational:** Duration of AI deployment + 1 year post-retirement
- **Litigation hold:** Indefinite if litigation pending

**Accountability Mapping:**

**Three Levels:**
1. **Operator Level (Immediate):** Person who deployed agent or approved action
2. **Developer Level (System):** Team who built/configured the agent
3. **Executive Level (Policy):** Leadership who approved deployment and set governance

**Critical Principle:** Accountable role must always be human. You cannot make an AI accountable - accountability flows to the human operator, developer, or executive.

---

## Workshop Recap

### Session Summary

**Today's Focus:** Implementation and compliance - regulatory requirements, organizational structures, autonomy classification, and audit trails.

**Key Points from Each Segment:**

**Segment 1: Regulatory Compliance Landscape**
- EU AI Act uses 4 risk tiers: Unacceptable (prohibited), High (strict requirements), Limited (transparency), Minimal (no specific requirements)
- High-risk AI requires: risk management, data governance, documentation, record-keeping, transparency, human oversight, accuracy/robustness/security
- Sector-specific regulations often stricter than general AI law (SR 11-7, HIPAA, NYC Local Law 144, etc.)
- Compliance is cross-functional and ongoing

**Segment 2: Organizational Structures**
- Centralized governance (strong central authority) vs. Federated (BU autonomy with central guidance)
- No one-size-fits-all - match structure to organizational culture, risk, and regulatory environment
- Key roles: Chief AI Officer, AI Ethics Officer, AI Risk Manager, AI Governance Lead, Model Validators
- Start lean, evolve as maturity grows

**Segment 3: Agent Autonomy Classification**
- Five levels: 0 (Tool) → 1 (Assistant) → 2 (Supervised) → 3 (Managed) → 4 (Autonomous)
- Classification uses 3 factors: Impact, Reversibility, Compliance context
- Define boundaries: financial limits, stakeholder scope, data sensitivity, regulatory context
- Escalation triggers: low confidence, novel situations, error spikes, user request

**Segment 4: Audit Trails & Accountability**
- Comprehensive audit record includes 10+ fields (timestamp, agent ID, action, input/output, reasoning, data, human oversight, confidence, version, outcome)
- Retention driven by regulatory (5-7 years), legal, operational needs
- Accountability has 3 levels: Operator (immediate), Developer (system), Executive (policy)
- Accountable role must always be human

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 2.1 | 25 min | `regulatory-compliance-mapping.md` | Mapping regulations to AI systems |
| 2.2 | 25 min | `ai-governance-policies.md` | Drafting core governance policies |
| 2.3 (Capstone) | 25 min | `enterprise-ai-governance-framework.md` | Complete integrated framework |

---

### Exercise 2.1: Regulatory Compliance Mapping

**Duration:** 25 minutes

**Purpose:**
Map applicable regulations to your AI systems, identify compliance requirements, assess gaps, and create remediation roadmap.

**You Will Create:**
A regulatory compliance mapping document showing which regulations apply to your organization, compliance status, and action plans.

**Instructions:**

**Step 1: Identify Applicable Regulations**
For your organization (or case study), identify which regulations apply:
- EU AI Act (if serving EU market or EU residents)
- Sector-specific (financial: SR 11-7, Basel; healthcare: HIPAA, FDA; employment: EEOC, NYC Law 144, etc.)
- Data protection (GDPR, CCPA, etc.)

**Step 2: Map EU AI Act**
If applicable, identify AI systems by risk tier:
- List systems that are High Risk (employment, credit, medical, etc.)
- List systems that are Limited Risk (chatbots, emotion recognition, etc.)
- List systems that are Minimal Risk

For High-Risk systems, document compliance with 7 requirements:
- Risk management system
- Data governance
- Technical documentation
- Record-keeping
- Transparency
- Human oversight
- Accuracy/robustness/cybersecurity

Use Red/Yellow/Green to indicate compliance status.

**Step 3: Map Sector-Specific Regulations**
For applicable sector regulations, document:
- Which AI systems are in scope
- Key requirements specific to AI
- Current state of compliance
- Gaps identified

**Step 4: Map Data Protection Requirements**
Document AI-specific implications of GDPR/CCPA:
- Automated decision-making (Article 22 - right to human review)
- Profiling transparency requirements
- Data minimization for training data
- Purpose limitation for AI use cases

**Step 5: Create Compliance Status Summary**
For each applicable regulation, assign overall status:
- Green: Compliant
- Yellow: Partial compliance, gaps being addressed
- Red: Non-compliant, significant gaps

**Step 6: Build Remediation Roadmap**
List priority gaps with:
- Which regulation they relate to
- Priority (High/Medium/Low)
- Owner (who will address)
- Effort estimate
- Target completion date

**Step 7: Define Ongoing Monitoring**
Document how you'll monitor for regulatory changes:
- Regulatory update review (monthly recommended)
- Compliance self-assessment (quarterly)
- Internal audit (annual)
- External audit if required

**Deliverable:** `regulatory-compliance-mapping.md`

**Quality Criteria:**
- [ ] All applicable regulations identified (not just EU AI Act)
- [ ] AI systems mapped to specific regulatory requirements
- [ ] Compliance gaps are honest (not aspirational)
- [ ] Remediation roadmap has realistic owners and dates
- [ ] Ongoing monitoring process defined

---

### Exercise 2.2: Governance Policy Drafting

**Duration:** 25 minutes

**Purpose:**
Draft core AI governance policies covering development & deployment, agent autonomy, and data governance.

**You Will Create:**
An AI Governance Policy Suite with three foundational policies tailored to your organizational context.

**Instructions:**

**Step 1: Customize Policy Headers**
For each of the three policies, update:
- Organization name
- Version number (start with 1.0)
- Effective date
- Policy owner (specific role)
- Approval authority

**Step 2: Draft Policy 1 - AI Development and Deployment**

Customize these sections:
- **AI Inventory:** How will you track AI systems?
- **Risk Classification:** Define your risk levels (adapt Low/Medium/High/Critical to context)
- **Development Standards:** Reference your development lifecycle
- **Testing Requirements:** Specify what testing is required for which risk levels
- **Approval Gates:** Document approval authority matrix
- **Monitoring:** Define monitoring requirements

**Step 3: Draft Policy 2 - AI Agent Autonomy**

Customize:
- **Autonomy Classification:** Document your 5-level system (0-4)
- **Level-Specific Requirements:** Define oversight for each level
- **Boundaries:** Set financial limits, stakeholder scope, data access limits
- **Escalation:** Define escalation triggers and paths
- **Emergency Override:** Specify override capability and testing frequency

**Step 4: Draft Policy 3 - AI Data Governance**

Customize:
- **Data Sourcing:** Requirements for data provenance and licensing
- **Data Quality:** Standards for AI training/operational data
- **Data Lineage:** Documentation requirements
- **Privacy:** Compliance with privacy policy, PII handling
- **Bias Mitigation:** Training data bias assessment requirements

**Step 5: Complete Policy Appendices**

**Appendix A - Approval Authority Matrix:**
Define who approves at each risk level

**Appendix B - Documentation Requirements:**
Specify documentation by risk level (business case, risk assessment, model docs, testing, approvals)

**Appendix C - Review Schedule:**
Define periodic review frequency by risk level

**Deliverable:** `ai-governance-policies.md`

**Quality Criteria:**
- [ ] Policies are specific to organizational context (not generic)
- [ ] Approval authorities are realistic roles
- [ ] Requirements are implementable (not aspirational)
- [ ] Appendices provide operational clarity
- [ ] Policies could actually guide decisions

---

### Exercise 2.3: Module Capstone - Enterprise Governance Framework

**Duration:** 25 minutes

**Purpose:**
Integrate all your work from Session 1 and Session 2 into a complete, client-ready Enterprise AI Governance Framework.

**You Will Create:**
A comprehensive governance framework document that could be presented to executives or clients, covering assessment, framework design, autonomy classification, compliance, and implementation.

**Instructions:**

**Step 1: Write Executive Summary**
In 2-3 paragraphs, summarize:
- Current state findings from your maturity assessment
- Key governance gaps identified
- Your recommended framework approach
- Expected outcomes and timeline

**Step 2: Part 1 - Assessment Summary**
Pull from Exercise 1.1 (Maturity Assessment):
- Governance maturity scores table (7 domains with current/target/gap)
- Key strengths (top 2-3)
- Critical gaps (top 2-3 with business impact)

**Step 3: Part 2 - Framework Design**

**Organizational Structure:**
- Recommend centralized, federated, or hybrid model
- Justify why this fits the organization
- Diagram the structure (text diagram acceptable)
- List key roles to establish with FTE requirements and priority

**Policy Framework:**
- List core policies required (from Exercise 2.2)
- Document status (Draft, To Develop, etc.)
- Assign priority and owner

**Risk Framework:**
- Specify which framework to adopt (NIST AI RMF, ISO 42001, custom)
- List risk categories
- State organization's risk appetite for AI

**Step 4: Part 3 - Agent Autonomy Classification**
- Document your 5-level classification system
- Classify current agents in organizational inventory by level
- Note any recommended level changes (e.g., currently operating at Level 3, should be Level 2 based on risk)

**Step 5: Part 4 - Compliance Roadmap**
Pull from Exercise 2.1:
- List applicable regulations with applicability and compliance status (R/Y/G)
- Identify priority compliance actions with regulation, owner, due date

**Step 6: Part 5 - Implementation Roadmap**

**Phase 1: Foundation (Months 1-3)**
- Objectives
- 3-5 key activities with owner, timeline, success criteria
- 3 Quick Wins (achievable in 30 days)

**Phase 2: Build (Months 4-6)**
- Objectives
- Key activities

**Phase 3: Operate (Months 7-12)**
- Objectives
- Key activities

**Step 7: Part 6 - Success Metrics**
Define 5-7 Governance KPIs with baseline, 6-month target, 12-month target:
- AI inventory completeness
- Policy compliance rate
- Risk assessments completed
- Open audit findings
- Training completion

Document expected maturity progression (overall score at current, 6-month, 12-month)

**Step 8: Part 7 - Investment Summary**
Estimate resource requirements:
- Personnel (one-time and annual)
- Technology (tools for monitoring, bias testing, audit)
- Training
- External support (consultants, auditors)

Provide ROI considerations (risk mitigation, compliance penalty avoidance, efficiency, competitive advantage)

**Step 9: Appendices**
Reference your other deliverables:
- Appendix A: Detailed Assessment (link to Exercise 1.1)
- Appendix B: Risk Register (link to Exercise 1.3)
- Appendix C: Policy Drafts (link to Exercise 2.2)
- Appendix D: Regulatory Mapping (link to Exercise 2.1)

**Step 10: Sign-Off**
Include signature table for:
- Executive Sponsor
- AI Governance Lead
- Risk Officer
- Legal/Compliance

**Deliverable:** `enterprise-ai-governance-framework.md`

**Quality Criteria:**
- [ ] Integrates all Session 1 and 2 deliverables (not starting from scratch)
- [ ] Executive summary is concise and compelling
- [ ] Organizational structure is justified for context
- [ ] Implementation roadmap has realistic timelines
- [ ] Quick wins are actually achievable in 30 days
- [ ] Success metrics are measurable
- [ ] Professional quality (could be presented to executives)
- [ ] Comprehensive yet focused (15-20 pages expected)

---

## Templates & Resources

### Templates Provided This Session

| Template | Purpose | Location |
|----------|---------|----------|
| Regulatory Compliance Mapping | Map regulations to AI systems | Exercise 2.1 instructions |
| AI Governance Policy Suite | Draft core policies | Exercise 2.2 instructions |
| Enterprise AI Governance Framework | Complete integrated framework | Exercise 2.3 instructions |

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| EU AI Act Official Text | Regulation | https://artificialintelligenceact.eu/ | Understanding requirements and risk tiers |
| SR 11-7 Model Risk Management | Guidance | https://www.federalreserve.gov/supervisionreg/srletters/sr1107.htm | Financial services compliance |
| NYC Local Law 144 | Regulation | https://www.nyc.gov/site/dca/about/automated-employment-decision-tools.page | Employment AI compliance |
| FDA AI/ML as Medical Device | Guidance | https://www.fda.gov/medical-devices/software-medical-device-samd | Healthcare AI compliance |

---

## Self-Assessment

### Exit Criteria Checklist

Before completing this module, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Map regulatory requirements to AI systems | Exercise 2.1 completed with compliance gaps identified | ☐ |
| 2 | Design organizational governance structures | Capstone includes justified structure recommendation | ☐ |
| 3 | Classify agent autonomy appropriately | Capstone includes autonomy classification system | ☐ |
| 4 | Implement audit and accountability frameworks | Policies include audit trail requirements | ☐ |

### Deliverables Checklist

| Deliverable | File Name | Content Complete? | Integration Check? |
|-------------|-----------|-------------------|-------------------|
| Compliance Mapping | `regulatory-compliance-mapping.md` | All applicable regulations mapped | Referenced in capstone Part 4 |
| Policy Suite | `ai-governance-policies.md` | 3 policies drafted | Referenced in capstone Part 2 |
| Capstone Framework | `enterprise-ai-governance-framework.md` | 7 parts complete, all appendices linked | Integrates all prior work |

### Module Completion Reflection

1. **What capability have you gained?**
   - Can you now design a complete AI governance framework for an organization?

2. **How will you apply this?**
   - Name one organization where you'll implement this governance framework.

3. **What's your next step?**
   - Will you pursue ISO 42001 certification? Implement NIST AI RMF? Focus on compliance?

---

## Getting Help

### Common Questions

**Q: My capstone seems too generic - how do I make it specific?**
A: Ground every recommendation in your organization's actual context. Instead of "implement NIST AI RMF," write "Adopt NIST AI RMF because we're in financial services and SR 11-7 references it." Instead of "create AI Governance Lead role," write "Assign AI Governance Lead to current Chief Data Officer (part-time initially) because we have 15 AI systems and growing."

**Q: I don't have enough information about my organization to complete the capstone.**
A: Three options: (1) Use publicly available information about a well-known company, (2) Create a realistic hypothetical organization in an industry you know, (3) Focus on the framework design and note where organizational data would inform the assessment.

**Q: My implementation timeline seems too aggressive/conservative - how do I know?**
A: Compare to your maturity assessment. If you scored 1-2 (Initial/Developing), 12-month timeline to reach 3 (Defined) is realistic. If you're already at 3, reaching 4 (Managed) in 6 months is possible. Quick wins should genuinely be achievable in 30 days with available resources.

---

## Looking Ahead

### Module Complete!

Congratulations on completing Advanced Module 7: Enterprise AI Governance. You now have:

**Frameworks:** NIST AI RMF, ISO 42001 knowledge
**Principles:** Six responsible AI principles operationalized
**Lifecycle:** Agent governance from design through retirement
**Data:** Four pillars of AI data governance
**Compliance:** EU AI Act and sector-specific regulation mapping
**Structure:** Organizational governance models and roles
**Autonomy:** Five-level classification system
**Accountability:** Audit trail and accountability frameworks
**Deliverable:** Complete enterprise AI governance framework

**Next Steps:**
- Implement your governance framework in your organization
- Consider ISO 42001 certification pathway
- Stay current on regulatory developments (EU AI Act implementation, emerging US regulations)
- Apply governance thinking to every AI project

---

## Glossary

| Term | Definition |
|------|------------|
| **EU AI Act** | Comprehensive EU regulation for AI systems using risk-based approach (4 tiers) |
| **High-Risk AI** | EU AI Act category requiring strict compliance (employment, credit, medical, etc.) |
| **Autonomy Level** | Classification 0-4 indicating how much independence an AI agent has |
| **Human-in-the-loop** | Level 1 autonomy - human approval required for each action |
| **Human-on-the-loop** | Level 2 autonomy - human monitoring with veto capability |
| **Human-in-command** | Level 3-4 autonomy - strategic oversight, operational autonomy |
| **Audit Trail** | Comprehensive log of AI decisions with reasoning and data sources |
| **Accountability** | Clear assignment of responsibility for AI outcomes to humans |
| **Centralized Governance** | Model where central authority controls all AI governance |
| **Federated Governance** | Model where business units have autonomy with central guidance |
| **Escalation Trigger** | Condition forcing AI agent to escalate to human review |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial participant guide created |

---

**Navigation:** [← Session 1](../session-1/participant-guide.md) | Session 2
