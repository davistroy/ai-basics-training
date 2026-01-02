# **ADVANCED MODULE 7 SESSION 1: AI Governance Frameworks**

**Module:** Advanced Module 7: Enterprise AI Governance
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
| 1 | Apply NIST AI RMF and ISO 42001 frameworks to organizational contexts | Exercise 1.1 |
| 2 | Assess AI governance maturity across seven domains and identify gaps | Exercise 1.1 |
| 3 | Operationalize responsible AI principles with concrete controls and metrics | Exercise 1.2 |
| 4 | Design agent lifecycle governance with appropriate approval gates | Exercise 1.3 |

---

## Entry Criteria

Before starting this session, confirm you have:

- [ ] Understanding of AI agent capabilities and limitations (from Block 3 or equivalent experience)
- [ ] Basic knowledge of enterprise risk management concepts
- [ ] Awareness of AI-related regulations in your relevant jurisdictions
- [ ] Access to an organizational context (your organization, a client, or a case study) for exercises

**Not ready?** Review Block 3 materials or reach out in [support channel] for help.

---

## Key Concepts

### Concept 1: NIST AI Risk Management Framework (AI RMF)

**Definition:**
A voluntary framework published by the US National Institute of Standards and Technology that provides a structured approach to identifying, assessing, and managing AI-related risks through four core functions.

**Why It Matters:**
NIST AI RMF is the de facto standard for AI governance in the US and increasingly referenced globally. Federal contractors, regulated industries, and organizations in procurement processes often must demonstrate NIST alignment. Understanding NIST AI RMF enables you to design credible governance frameworks.

**Core Principle:**
> AI governance should be risk-based, lifecycle-oriented, and structured around four functions: Govern (establish accountability), Map (understand context), Measure (assess risks), and Manage (implement controls).

**The Four Functions:**
```
┌─────────────────────────────────────────────────────────┐
│                    NIST AI RMF                          │
│                                                         │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌─────────┐ │
│  │  GOVERN  │──│   MAP    │──│ MEASURE  │──│ MANAGE  │ │
│  └──────────┘  └──────────┘  └──────────┘  └─────────┘ │
│       │             │             │             │       │
│  Establish     Understand    Assess &       Prioritize │
│  accountability context &    analyze        & address  │
│  & culture     risks         risks          risks      │
└─────────────────────────────────────────────────────────┘
```

**When to Use:**
- Designing governance frameworks from scratch
- Assessing current governance maturity
- Demonstrating governance to regulators or procurement teams
- Structuring AI risk assessments

**Common Mistake:**
Treating NIST as a compliance checklist rather than a continuous risk management process. NIST is cyclical - you continuously govern, map, measure, and manage as AI systems and contexts evolve.

---

### Concept 2: Responsible AI Principles

**Definition:**
Six core principles that guide ethical and safe AI development and deployment: Fairness, Transparency, Accountability, Privacy, Safety, and Human Oversight.

**Why It Matters:**
Regulatory frameworks (EU AI Act, sector-specific regulations) increasingly require demonstrable implementation of responsible AI principles. Adopting principles without operationalizing them creates "governance theater" - good PR but no actual protection.

**The Six Principles:**

| Principle | Definition | Implementation Example |
|-----------|------------|----------------------|
| **Fairness** | AI treats all individuals equitably | Conduct bias testing using demographic parity ratio (target: 0.8-1.2) before deployment |
| **Transparency** | Decisions are explainable | Enable decision logging and create model cards documenting system capabilities and limitations |
| **Accountability** | Clear ownership of outcomes | Create RACI matrix showing who's Responsible, Accountable, Consulted, Informed for each AI system |
| **Privacy** | Personal data protected | Implement data minimization, consent management, and data subject rights (access, deletion) |
| **Safety** | AI operates within safe boundaries | Deploy kill switches, set automatic escalation triggers, conduct regular safety testing |
| **Human Oversight** | Humans maintain control | Define approval workflows for high-risk decisions and intervention points for human review |

**Principle Trade-offs:**
Principles sometimes conflict. Document all trade-off decisions with rationale and approval.

Example: Transparency vs. Intellectual Property
- Conflict: Full model explainability might expose proprietary algorithms
- Resolution: Provide high-level logic documentation and outcome explanations without revealing IP
- Documentation: "Chose partial transparency approach to protect IP while meeting user explanation needs. Approved by Legal and Ethics Board on [date]."

**When NOT to Use:**
Don't apply principles at identical intensity to all AI systems. Use risk-based approach - high-risk AI needs rigorous principle implementation; low-risk AI needs proportional implementation.

---

### Concept 3: Agent Governance Lifecycle

**Definition:**
A six-stage framework for governing AI agents across their complete lifecycle: Design → Develop → Test → Deploy → Monitor → Retire.

**The Pattern:**
```
[Design] → [Develop] → [Test] → [Deploy] → [Monitor] → [Retire]
    │          │          │         │          │          │
    ↓          ↓          ↓         ↓          ↓          ↓
 Purpose    Controls   Validation  Approval   Ongoing    Secure
 Definition  Built In  & Bias     Gates      Oversight  Disposal
```

**Stage-Specific Governance:**

**Design:** Define purpose, assign risk classification, conduct stakeholder review
**Develop:** Follow secure development practices, ensure data governance compliance, require peer review
**Test:** Conduct functional, bias, security, and user acceptance testing
**Deploy:** Obtain risk-appropriate approvals, prepare rollback procedures, communicate to stakeholders
**Monitor:** Track performance metrics, detect drift, log incidents, conduct periodic reviews
**Retire:** Execute data retention/disposal, transfer knowledge, assess impact, follow decommissioning procedures

**Risk-Based Approval Gates:**

| Risk Level | Required Approvals | Review Frequency |
|------------|-------------------|------------------|
| Low | Team Lead | Biennial |
| Medium | Department Head + Risk Review | Annual |
| High | Executive + Legal + Ethics Board | Semi-annual |
| Critical | Board-level approval | Quarterly |

**Risk Classification Criteria:**
- **Impact:** What's the consequence if the AI fails?
- **Reversibility:** Can decisions be easily undone?
- **Scope:** How many people/transactions affected?
- **Regulatory Context:** Is this a regulated use case?

**Common Mistake:**
Treating deployment approval as the end of governance. Monitor and Retire stages are where most governance failures happen - agents drift, become outdated, or get abandoned without proper decommissioning.

---

### Concept 4: Data Governance for AI

**Definition:**
The management of data used in AI systems across four pillars: Lineage (provenance), Quality (fitness for use), Privacy (protection), and Access (control).

**The Four Pillars:**

```
┌─────────────────────────────────────────────────┐
│           DATA GOVERNANCE FOR AI                │
│                                                 │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌───────┐ │
│  │ LINEAGE │ │ QUALITY │ │ PRIVACY │ │ ACCESS│ │
│  └─────────┘ └─────────┘ └─────────┘ └───────┘ │
│                                                 │
│  Where did    Is it fit   Is it       Who can  │
│  data come    for AI      protected?  use it?  │
│  from?        use?                             │
└─────────────────────────────────────────────────┘
```

**Pillar Details:**

**LINEAGE:**
- Source identification: Where did data come from?
- Transformation tracking: How was it processed?
- Usage documentation: How is it being used in AI?
- Consent chain verification: Do we have rights to use it this way?

**QUALITY:**
- Accuracy and completeness metrics
- Timeliness and relevance validation
- Consistency across sources
- Bias assessment in training data (critical for AI)

**PRIVACY:**
- Personal data identification (PII, sensitive attributes)
- Purpose limitation (use only for specified purposes)
- Consent management (track and honor user consent)
- Data subject rights (access, deletion, correction, portability)

**ACCESS:**
- Role-based access controls
- Purpose-based restrictions
- Data classification (public, internal, confidential, restricted)
- Access logging and audit

**Critical Teaching:**
> "AI governance fails without data governance. You can have perfect governance processes, but if your data is biased, improperly sourced, or privacy-violating, your AI will fail."

---

### Quick Reference: NIST Functions vs. ISO 42001

| Aspect | NIST AI RMF | ISO 42001 |
|--------|-------------|-----------|
| **Type** | Risk management framework | Management system standard |
| **Structure** | Four functions (Govern, Map, Measure, Manage) | Plan-Do-Check-Act cycle |
| **Certification** | No certification pathway | Certification available from accredited bodies |
| **Focus** | Risk-centric | Broader AI management |
| **Best For** | Risk assessment, ongoing risk management | Overall governance structure, third-party validation |
| **Compliance** | Voluntary (but increasingly referenced) | Voluntary (required by some procurement processes) |
| **Relationship** | Complementary - many organizations use both | Complementary - NIST can map to ISO 42001 |

**When to Use:**
- Use NIST for risk framework and assessment methodology
- Use ISO 42001 if you need certification or broader management system
- Use both - NIST for risk processes, ISO 42001 for certification

---

## Workshop Recap

### Session Summary

**Today's Focus:** Established foundational frameworks for AI governance including NIST AI RMF, ISO 42001, Responsible AI Principles, Agent Lifecycle Governance, and Data Governance for AI.

**Key Points from Each Segment:**

**Segment 1: AI Risk Frameworks Deep Dive**
- NIST AI RMF provides four-function structure: Govern (policies/roles), Map (context/categorization), Measure (risk assessment), Manage (controls/monitoring)
- ISO 42001 offers certifiable management system based on Plan-Do-Check-Act cycle
- Both frameworks are voluntary but increasingly referenced in regulations and procurement
- NIST is risk-focused; ISO 42001 is broader management system; they complement each other

**Segment 2: Responsible AI Principles**
- Six core principles: Fairness, Transparency, Accountability, Privacy, Safety, Human Oversight
- Principles must be operationalized through metrics and controls (not just aspirational statements)
- Example: "Fairness" becomes actionable through demographic parity ratio, bias testing, and regular audits
- Principles sometimes conflict - document trade-off decisions with rationale and approval
- Regulators expect demonstrable controls, not just principle adoption

**Segment 3: Agent Governance Lifecycle**
- Governance spans six stages: Design → Develop → Test → Deploy → Monitor → Retire
- Each stage has specific governance requirements based on risk classification
- Risk-based approval gates: Low (Team Lead) → Medium (Dept Head + Risk) → High (Executive + Legal + Ethics) → Critical (Board)
- Risk classification uses four criteria: Impact, Reversibility, Scope, Regulatory Context
- Monitoring and retirement often neglected but critical for sustainable governance

**Segment 4: Data Governance for AI**
- AI governance fails without data governance - four pillars: Lineage, Quality, Privacy, Access
- Lineage: Can you trace data from source to AI output and verify rights to use?
- Quality: Is data accurate, complete, timely, unbiased? Test training data, not just outputs
- Privacy: Personal data protection, consent management, data subject rights (GDPR/CCPA)
- Access: Role-based controls, data classification, purpose restrictions

---

## Self-Paced Exercises

**Total Time:** 75 minutes

| Exercise | Duration | Deliverable | Focus |
|----------|----------|-------------|-------|
| 1.1 | 25 min | `governance-maturity-assessment.md` | NIST/ISO framework application, gap analysis |
| 1.2 | 25 min | `responsible-ai-mapping.md` | Principle operationalization, controls design |
| 1.3 | 25 min | `agent-risk-register.md` | Lifecycle risk assessment, treatment planning |

---

### Exercise 1.1: Governance Maturity Assessment

**Duration:** 25 minutes

**Purpose:**
Assess the current state of AI governance in an organization (yours, a client's, or a case study) across seven domains. This produces a maturity score, identifies gaps, and creates prioritized recommendations.

**You Will Create:**
A complete governance maturity assessment document that can be presented to executives or used in consulting engagements.

---

#### Instructions

**Step 1: Select Your Organization**
Choose the organization you'll assess:
- Your current organization
- A client organization
- A public case study (if you don't have organizational access)
- A hypothetical organization (but make it realistic)

Note the organization name, assessment date, and your name as assessor.

**Step 2: Understand Maturity Levels**
Review the five maturity levels you'll use for scoring:
1. **Initial:** Ad-hoc, reactive, no formal processes
2. **Developing:** Basic processes exist, inconsistent application
3. **Defined:** Documented processes, consistent application
4. **Managed:** Measured and controlled, metrics-driven
5. **Optimizing:** Continuous improvement, industry-leading

**Step 3: Assess Seven Domains**
For each domain, score 4 questions on a 1-5 scale and provide evidence/notes:

**Domain 1: Strategy & Leadership**
- AI strategy aligned with business objectives?
- Executive sponsorship for AI governance?
- AI governance roles defined?
- Budget allocated for governance activities?

**Domain 2: Policies & Standards**
- AI-specific policies documented?
- Responsible AI principles adopted?
- Development standards exist?
- Deployment approval processes defined?

**Domain 3: Risk Management**
- AI risk framework adopted (NIST/ISO)?
- Risk classification system for AI?
- Risk assessments conducted regularly?
- Incident response procedures exist?

**Domain 4: Data Governance**
- Data lineage tracked for AI systems?
- Data quality standards defined?
- Privacy controls implemented?
- Data access controls appropriate?

**Domain 5: Model/Agent Lifecycle**
- AI inventory maintained?
- Development lifecycle documented?
- Testing requirements defined?
- Monitoring and review processes exist?

**Domain 6: Compliance & Audit**
- Regulatory requirements mapped?
- Audit trail capabilities exist?
- Internal audits conducted?
- External audit readiness?

**Domain 7: People & Culture**
- AI governance training provided?
- Awareness of responsible AI principles?
- Clear accountability for AI outcomes?
- Ethics reporting channels exist?

Calculate the average score for each domain (sum of 4 questions ÷ 4).

**Step 4: Calculate Overall Maturity**
Sum all domain averages and divide by 7 to get overall maturity score.

**Step 5: Identify Strengths and Gaps**
- List 3 strengths (highest-scoring domains or practices)
- List 3 critical gaps (lowest-scoring areas with business impact)

**Step 6: Create Priority Recommendations**
Identify 3 priority recommendations with:
- Which domain they address
- Effort level (High/Medium/Low)
- Impact level (High/Medium/Low)
- Brief description of the recommendation

**Step 7: Identify Quick Wins**
List 3 quick wins - improvements achievable in 30 days that will demonstrate progress.

**Step 8: Review Your Work**
Check that your deliverable includes:
- [ ] All seven domains assessed with scores
- [ ] Evidence/notes provided for scores (not just numbers)
- [ ] Overall maturity score calculated
- [ ] Strengths and gaps identified
- [ ] Priority recommendations with effort/impact ratings
- [ ] Quick wins that are actually achievable in 30 days

---

#### Deliverable Specification

**File Name:** `governance-maturity-assessment.md`

**Location:** Your working directory (or as specified by instructor)

**Format Requirements:**
- Markdown format using the template provided
- All scoring fields completed
- Evidence/notes column filled in (not blank)
- Recommendations specific to the organization (not generic)

**Quality Criteria:**
- [ ] Scores are realistic based on evidence
- [ ] Gap analysis connects to business impact
- [ ] Recommendations are actionable and prioritized
- [ ] Quick wins are actually quick (not 6-month projects)
- [ ] Overall assessment is professional quality (could be presented to executives)

---

#### Example (Excerpt)

**Scenario:** Mid-size financial services firm starting AI adoption

**Domain 3: Risk Management**

| Question | Score (1-5) | Evidence/Notes |
|----------|-------------|----------------|
| AI risk framework adopted (NIST/ISO)? | 2 | Aware of NIST but not formally adopted. No documented risk framework. |
| Risk classification system for AI? | 1 | No risk classification system. All AI treated the same regardless of risk. |
| Risk assessments conducted regularly? | 2 | Ad-hoc assessments for high-profile projects only. No regular schedule. |
| Incident response procedures exist? | 3 | General IT incident response exists but no AI-specific procedures. |
| **Domain Average** | **2.0** | Risk management is developing but not formalized. |

**Key Finding:**
Risk management gap creates exposure, especially as organization deploys customer-facing AI. Without risk classification, treating low-risk chatbot same as high-risk credit decisioning AI.

**Priority Recommendation:**
Adopt NIST AI RMF as risk framework and implement risk classification system (High Impact, Medium Effort, targets Domain 3)

---

#### Tips & Troubleshooting

**Tips:**
- Be honest in scoring - this is a diagnostic, not a performance review
- Evidence is critical - scores without evidence aren't credible
- If you don't have information for a question, score it 1 and note "insufficient information"
- Target scores should be realistic - don't aim for 5 (optimizing) on everything
- Prioritize recommendations by impact, not ease - high impact should come first even if high effort

**Common Issues:**

| Problem | Solution |
|---------|----------|
| "I don't have access to enough information" | Focus on what you can observe or learn through conversation; note information gaps explicitly |
| "All my scores are 1s or 2s" | That's OK - many organizations are at Initial/Developing maturity; this identifies opportunity |
| "Recommendations seem overwhelming" | That's why you prioritize - you won't fix everything at once; focus on high-impact items |
| "Quick wins aren't coming to mind" | Think small: create AI inventory spreadsheet, document one policy, conduct bias test on one model |

---

### Exercise 1.2: Responsible AI Mapping

**Duration:** 25 minutes

**Purpose:**
Operationalize responsible AI principles for a specific AI system. This moves from abstract principles to concrete controls, metrics, and implementation requirements.

**You Will Create:**
A complete responsible AI principles mapping that defines exactly how each principle applies to your AI system, with measurable metrics and documented trade-offs.

---

#### Instructions

**Step 1: Select Your AI System**
Choose a specific AI system/use case:
- An AI system your organization uses or is developing
- A client's AI system
- A well-known public AI system (e.g., resume screening AI, loan approval AI, customer service chatbot)

Document the organization name and AI system/use case description.

**Step 2: Map Principle 1 - Fairness**

**Define fairness for your context:**
What does "fairness" mean for this specific AI system? (Example: "Equal opportunity for qualified candidates regardless of demographic attributes")

**Identify risks:**
List 3 fairness-related risks with likelihood (H/M/L) and impact (H/M/L):
- Example: Training data bias (Likelihood: High, Impact: High, Current Controls: None)

**Define implementation requirements:**
Create 4 requirements with status, owner, and due date:
- Example: "Bias testing before deployment" (Status: Planned, Owner: Data Science Lead, Due: Q2)

**Define metrics:**
Specify 2-3 measurable fairness metrics:
- Example: Demographic parity ratio: approval rate for protected class / approval rate for reference class (target: 0.8-1.2)

**Step 3: Map Principle 2 - Transparency**

**Define transparency for your context:**
What does transparency mean? (Example: "Users understand why recommendations were made")

**Identify stakeholder communication needs:**
Create table with stakeholder, information needed, format, frequency:
- Example: End users → How decision was made → Plain language explanation → At each interaction

**Define implementation requirements:**
Create 4 requirements (model cards, decision logging, explanations, documentation)

**Step 4: Map Principle 3 - Accountability**

**Create RACI matrix:**
For 5 activities, specify who's Responsible, Accountable, Consulted, Informed:
- AI system performance
- Risk decisions
- Incident response
- Policy compliance
- Stakeholder communication

**Define escalation path:**
Document escalation chain with timeframes:
Example: Issue Detected → Team Lead (15 min) → Dept Head (1 hour) → Risk Officer (4 hours) → Executive (24 hours)

**Step 5: Map Principle 4 - Privacy**

**Create data inventory:**
For each data element used by AI, document:
- Data element name
- Personal data? (Y/N)
- Sensitive? (Y/N)
- Legal basis for processing
- Retention period

**Checklist privacy controls:**
- [ ] Data minimization applied
- [ ] Purpose limitation documented
- [ ] Consent obtained where required
- [ ] Data subject rights process exists
- [ ] Cross-border transfer compliance

**Step 6: Map Principle 5 - Safety**

**Document safety controls:**
Create table with control, description, status:
- Example: Kill switch capability → Emergency stop for all AI actions → Implemented

**Define risk boundaries:**
- Maximum autonomous decisions per hour
- Escalation triggers
- Automatic shutdown conditions

**Step 7: Map Principle 6 - Human Oversight**

**Select oversight model:**
- [ ] Human-in-the-loop (approval required for each action)
- [ ] Human-on-the-loop (monitoring with intervention capability)
- [ ] Human-in-command (strategic oversight, operational autonomy)

**Define intervention points:**
Create table with decision type, oversight level, response time:
- Example: High risk decision → Human approval required → Before action

**Step 8: Document Trade-offs**

**Identify principle conflicts:**
For each pair of principles in tension, document:
- Principles in tension
- Decision made
- Rationale
- Who approved

Example: Transparency vs. IP → Partial transparency approach → Protects IP while meeting explanation needs → Legal & Ethics Board

**Step 9: Review Your Work**
Check that your deliverable includes:
- [ ] All six principles mapped
- [ ] Specific metrics defined (not vague "measure fairness")
- [ ] RACI matrix has actual roles (not "TBD")
- [ ] Privacy controls checklist completed
- [ ] Trade-offs documented with approval

---

#### Deliverable Specification

**File Name:** `responsible-ai-mapping.md`

**Location:** Your working directory

**Format Requirements:**
- Markdown format using template
- All six principles addressed
- Metrics are quantitative and measurable
- RACI matrix populated with real roles or realistic role descriptions
- Trade-offs documented with rationale

**Quality Criteria:**
- [ ] Principles are context-specific (not generic definitions)
- [ ] Metrics are measurable (numbers, percentages, thresholds)
- [ ] Implementation requirements have owners and dates
- [ ] Trade-off decisions show real thinking about tensions
- [ ] Document is actionable (could guide actual implementation)

---

#### Example (Excerpt)

**Scenario:** Resume screening AI for hiring process

**Principle 1: Fairness**

**Definition Applied:** Equal opportunity for qualified candidates regardless of race, gender, age, or other protected attributes

**Risks Identified:**
| Risk | Likelihood | Impact | Current Controls |
|------|------------|--------|------------------|
| Training data reflects historical hiring biases | High | High | None - using 5 years historical data |
| Resume format advantages certain demographics | Medium | Medium | None |
| Lack of diverse test population for validation | High | High | Small test set, not demographically balanced |

**Implementation Requirements:**
| Requirement | Status | Owner | Due Date |
|-------------|--------|-------|----------|
| Bias testing before deployment | Planned | ML Engineering Lead | 2025-03-15 |
| Diverse test population recruited | In Progress | Recruiting Team | 2025-02-28 |
| Fairness metrics defined and measured | Planned | Data Science Lead | 2025-03-01 |
| Regular fairness audits scheduled | Not Started | Compliance Officer | 2025-04-01 |

**Metrics:**
- [x] Demographic parity ratio: 0.85 (target: 0.8-1.2) - within acceptable range
- [ ] Equal opportunity difference: Not yet measured (target: <0.05)
- [ ] Disparate impact ratio: 0.76 (target: >0.80) - **FAILS legal threshold, requires mitigation**

**Why This Works:**
Shows specific risks grounded in the use case, concrete owners and dates, and measurable metrics with actual thresholds. Identifies specific problem (disparate impact ratio failing legal threshold).

---

### Exercise 1.3: Agent Risk Register

**Duration:** 25 minutes

**Purpose:**
Create a comprehensive risk register for AI agents that identifies risks across the lifecycle, scores them by likelihood and impact, documents current controls, and creates treatment plans.

**You Will Create:**
An agent risk register that serves as your governance roadmap - prioritized risks with clear ownership and mitigation plans.

---

#### Instructions

**Step 1: Define Scope**
Document:
- Organization name
- Scope: Which AI agents are covered (specific agent, class of agents, all agents)
- Last updated date
- Register owner (who maintains this register)

**Step 2: Understand Risk Methodology**

**Likelihood Scale (1-5):**
- 5: Almost Certain (>90% probability)
- 4: Likely (60-90%)
- 3: Possible (30-60%)
- 2: Unlikely (10-30%)
- 1: Rare (<10%)

**Impact Scale (1-5):**
- 5: Severe (existential threat, major regulatory action)
- 4: Major (significant financial loss, reputation damage)
- 3: Moderate (operational disruption, contained damage)
- 2: Minor (limited impact, easily remediated)
- 1: Negligible (minimal consequence)

**Risk Score:** Likelihood × Impact (1-25)

**Step 3: Document Risk AGR-001 - Autonomous Agent Exceeds Authority**

Use the template to document:
- Description: Agent takes actions beyond approved scope without human approval
- Category: Autonomy/Control
- Likelihood: [Your assessment 1-5]
- Impact: [Your assessment 1-5]
- Risk Score: [L × I]
- Risk Owner: [Name/Role]

**Current Controls Checklist:**
- [ ] Action scope limits defined
- [ ] Approval workflows configured
- [ ] Audit logging enabled
- [ ] Monitoring alerts active

**Residual Risk:** [Score after controls, 1-25]

**Treatment Plan:** Create table with actions, owners, due dates, status

**Step 4: Document Risk AGR-002 - Biased Agent Outputs**
- Description: Agent produces systematically unfair or discriminatory outputs
- Category: Fairness/Ethics
- Follow same structure as AGR-001

**Step 5: Document Risk AGR-003 - Data Privacy Violation**
- Description: Agent accesses, processes, or exposes personal data improperly
- Category: Privacy/Compliance

**Step 6: Document Risk AGR-004 - Model/Agent Drift**
- Description: Agent behavior degrades over time due to data or environment changes
- Category: Performance/Quality

**Step 7: Document Risk AGR-005 - Regulatory Non-Compliance**
- Description: Agent deployment violates applicable AI regulations
- Category: Compliance/Legal

**Step 8: Document Risk AGR-006 - Lack of Audit Trail**
- Description: Unable to explain or reconstruct agent decisions when required
- Category: Transparency/Accountability

**Step 9: Create Risk Heat Map**
Plot your six risks on the heat map by likelihood (x-axis) and impact (y-axis).

**Step 10: Complete Risk Summary**
Count risks by score band:
- 20-25 (Critical): Immediate escalation required
- 12-19 (High): Treatment plan required
- 6-11 (Medium): Monitor and review
- 1-5 (Low): Accept with monitoring

**Step 11: Define Review Schedule**
Document when the register will be reviewed:
- Monthly: Risk owner review
- Quarterly: Full register review with stakeholders
- Annually: Comprehensive reassessment
- Ad-hoc: After incidents or significant changes

**Step 12: Review Your Work**
Check that your deliverable includes:
- [ ] All six risks documented with scores
- [ ] Likelihood and impact assessments are realistic
- [ ] Current controls identified (may be none - that's OK)
- [ ] Treatment plans specify actions, owners, dates
- [ ] Heat map accurately reflects risk scores
- [ ] Risk summary counts are correct

---

#### Deliverable Specification

**File Name:** `agent-risk-register.md`

**Location:** Your working directory

**Format Requirements:**
- Markdown format using template
- All six base risks documented (you may add more)
- Risk scores calculated correctly (Likelihood × Impact)
- Treatment plans have specific actions, not vague statements

**Quality Criteria:**
- [ ] Risk scores are differentiated (not all the same score)
- [ ] Current controls are realistic for your organizational context
- [ ] Treatment plans are specific and actionable
- [ ] Risk owners are specific roles (not "TBD" or "someone")
- [ ] Register could actually guide risk mitigation efforts

---

#### Example (Excerpt)

**Risk ID: AGR-002**
**Risk Name:** Biased Agent Outputs

| Field | Value |
|-------|-------|
| **Description** | Customer service AI provides different quality responses based on customer demographics, potentially violating discrimination laws |
| **Category** | Fairness/Ethics |
| **Likelihood** | 4 (Likely - training data from historical interactions likely contains bias) |
| **Impact** | 4 (Major - regulatory penalties, reputation damage, class action risk) |
| **Risk Score** | 16 (High) |
| **Risk Owner** | Chief AI Officer |

**Current Controls:**
- [ ] Bias testing conducted - NOT DONE
- [x] Diverse training data verified - PARTIAL (reviewed but not tested for statistical bias)
- [ ] Output sampling and review - NOT DONE
- [ ] Fairness metrics monitored - NOT DONE

**Residual Risk After Controls:** 16 (High - controls insufficient)

**Treatment Plan:**
| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| Conduct bias testing using Fairlearn on training data | Data Science Lead | 2025-02-15 | Not Started |
| Implement ongoing output sampling (100 interactions/week) | Customer Service Manager | 2025-02-28 | Not Started |
| Define and monitor fairness metrics (response quality by demographic) | Analytics Lead | 2025-03-15 | Not Started |
| Quarterly bias audits scheduled | Compliance Officer | 2025-04-01 | Not Started |

**Why This Works:**
Realistic likelihood and impact based on actual risk (training data likely biased, impact includes legal exposure). Identifies specific control gaps. Treatment plan has concrete actions with real owners and dates.

---

#### Tips & Troubleshooting

**Tips:**
- Not all risks will be present in your context - adjust to your reality
- If current controls don't exist, note that honestly (don't invent controls)
- Treatment plans should be specific actions, not aspirations ("Conduct bias testing" not "Improve fairness")
- Risk owners should be actual roles/people who can address the risk
- Residual risk reflects risk AFTER controls - if you have no controls, residual risk = inherent risk

**Common Issues:**

| Problem | Solution |
|---------|----------|
| "All my risks score the same" | Differentiate by context - not all risks are equal likelihood or impact |
| "We have no current controls" | That's valuable information - shows where to focus; don't make up controls |
| "Treatment plans seem generic" | Get specific - "Implement bias testing" → "Conduct bias testing using Fairlearn, testing demographic parity and equal opportunity, by March 15" |
| "Risk owners are all the same person" | Risk ownership should distribute - different risks need different expertise |

---

## Templates & Resources

### Templates Provided This Session

| Template | Purpose | Location |
|----------|---------|----------|
| Governance Maturity Assessment | Assess current governance state across 7 domains | Exercise 1.1 instructions above |
| Responsible AI Principles Mapping | Operationalize 6 principles with metrics and controls | Exercise 1.2 instructions above |
| Agent Risk Register | Document and score AI agent risks | Exercise 1.3 instructions above |

All templates are embedded in the exercise instructions. Copy the markdown structure and fill in with your organization's information.

---

### External Resources

| Resource | Type | Link | When to Use |
|----------|------|------|-------------|
| NIST AI Risk Management Framework | Official Framework Doc | https://www.nist.gov/itl/ai-risk-management-framework | Deep dive on NIST functions and sub-functions |
| ISO 42001 Overview | Standard Information | https://www.iso.org/standard/81230.html | Understanding ISO certification requirements |
| EU AI Act Summary | Regulatory Summary | https://artificialintelligenceact.eu/ | Understanding EU regulatory landscape |
| Fairlearn | Bias Testing Tool | https://fairlearn.org/ | Implementing fairness metrics in practice |
| Model Cards | Documentation Standard | https://modelcards.withgoogle.com/ | Creating transparency documentation |

---

## Self-Assessment

### Exit Criteria Checklist

Before moving to Session 2, confirm you can:

| # | Skill | Demonstrated By | Done? |
|---|-------|-----------------|-------|
| 1 | Apply NIST AI RMF four functions to organizational governance | Exercise 1.1 completed with NIST-aligned assessment | ☐ |
| 2 | Assess governance maturity and identify gaps | Exercise 1.1 produces actionable recommendations | ☐ |
| 3 | Operationalize responsible AI principles with metrics | Exercise 1.2 defines measurable controls for all 6 principles | ☐ |
| 4 | Design lifecycle governance with approval gates | Exercise 1.3 identifies risks across lifecycle stages | ☐ |

---

### Deliverables Checklist

| Deliverable | File Name | Content Complete? | Quality Check? |
|-------------|-----------|-------------------|----------------|
| Maturity Assessment | `governance-maturity-assessment.md` | All 7 domains scored, gaps identified | ☐ |
| Principles Mapping | `responsible-ai-mapping.md` | All 6 principles mapped with metrics | ☐ |
| Risk Register | `agent-risk-register.md` | At least 6 risks documented and scored | ☐ |

**Quality Check Questions:**
- Are scores and metrics quantitative (not vague)?
- Are recommendations specific to your organizational context?
- Could you present these to executives or clients?
- Are owners and dates realistic?

---

### Reflection Questions

Take 5 minutes to consider:

1. **What clicked this week?**
   - Which framework (NIST, ISO, lifecycle, data governance) made the most sense for your context?

2. **What's still fuzzy?**
   - Which concepts need more practice or clarification? (Bring to Session 2 or post in support channel)

3. **How will you apply this?**
   - Name one real AI system where you'll apply governance framework thinking.

4. **What surprised you?**
   - Was anything about enterprise AI governance harder or easier than expected?

[Optional: Share insights in [support channel] to help your peers]

---

## Getting Help

### Quick Answers
- **[Support Channel Name]** - Post questions, usually answered within 24 hours
- **Peer Discussion** - Tag your cohort for quick tips on exercises

### Common Questions This Week

**Q: I don't have access to organizational information for the assessment. What should I do?**
A: Three options: (1) Use publicly available information about a well-known company's AI practices, (2) Create a realistic hypothetical organization based on an industry you know, (3) Focus on one domain you can assess and note information gaps for others.

**Q: My organization has almost no governance - my scores are all 1s and 2s. Is that OK?**
A: Yes - this is very common and valuable information. The assessment identifies the opportunity. Low scores with good gap analysis and recommendations are more valuable than inflated scores.

**Q: How do I define fairness metrics if I'm not a data scientist?**
A: Use the examples provided (demographic parity ratio, equal opportunity, disparate impact). You don't need to implement the metrics yourself - you need to specify that they should be measured and what the targets are. Data scientists can implement.

**Q: The risk register feels generic. How do I make it specific?**
A: Ground each risk in your actual AI system. Instead of "Agent exceeds authority," write "Customer service agent approves refunds beyond $500 limit without manager review." Instead of "Data privacy violation," write "Agent accesses customer financial data without valid purpose for the interaction."

**Q: I'm stuck on the RACI matrix - who should be accountable vs. responsible?**
A: Remember: Responsible = does the work, Accountable = owns the outcome (only one per activity), Consulted = provides input, Informed = kept updated. For "AI system performance," Responsible might be "Data Science Team," Accountable is "Product Owner," Consulted includes "Legal, Ethics Board," Informed includes "Executive Sponsor."

### When to Ask for Help

- **Before asking:** Review the exercise instructions and examples
- **Good to ask:** "I completed the maturity assessment but my scores don't differentiate between domains - am I missing something?"
- **Include:** What you tried, what result you got, what you expected

### Office Hours

[If applicable]
- **When:** [Day/Time]
- **Where:** [Platform/Link]
- **For:** Live troubleshooting and deeper questions about governance frameworks

---

## Looking Ahead

### Next Session Preview: Session 2 - Implementation & Compliance

**Focus:**
Session 2 shifts from frameworks to implementation - regulatory compliance, organizational structures, agent autonomy classification, and audit trails.

**How It Builds on This Session:**
- Your maturity assessment becomes Part 1 of the capstone governance framework
- Your principles mapping informs policy design
- Your risk register drives compliance roadmap

**To Prepare:**
- [ ] Complete all Session 1 exercises (they feed into capstone)
- [ ] Review EU AI Act basics (link in resources) if unfamiliar
- [ ] Think about organizational structure questions (centralized vs. federated governance)

**Session 2 Capstone:**
The Session 2 capstone integrates everything - you'll create a complete Enterprise AI Governance Framework that's client-ready. Quality Session 1 deliverables are essential.

---

## Glossary

| Term | Definition |
|------|------------|
| **AI RMF** | AI Risk Management Framework (NIST) - four-function framework for AI governance |
| **ISO 42001** | International standard for AI Management Systems providing certification pathway |
| **Demographic Parity** | Fairness metric requiring equal selection rates across demographic groups |
| **Disparate Impact** | Legal concept where seemingly neutral practice has discriminatory effect (80% rule) |
| **RACI Matrix** | Responsibility assignment matrix showing who's Responsible, Accountable, Consulted, Informed |
| **Data Lineage** | Documentation of data's origin, transformations, and usage chain |
| **Model Drift** | Degradation of AI model performance over time due to data or environment changes |
| **Kill Switch** | Emergency capability to immediately halt AI agent operation |
| **Human-in-the-loop** | Oversight model requiring human approval for each AI action |
| **Human-on-the-loop** | Oversight model with human monitoring and intervention capability |
| **Risk Appetite** | Amount and type of risk an organization is willing to accept |
| **Residual Risk** | Risk remaining after controls are applied |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-01-02 | Initial participant guide created |

---

**Navigation:** Session 1 | [Session 2 →](../session-2/participant-guide.md)
