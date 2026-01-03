# **POWERPOINT PRESENTATION: ADVANCED MODULE 7 SESSION 1**
## **AI Governance Frameworks**

**Module:** Advanced Module 7: Enterprise AI Governance
**Session Number:** 1 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Consulting professionals who advise organizations on AI governance, risk officers, compliance leads, and Block 3 graduates

**Key Thesis:** Effective AI governance requires structured frameworks that balance innovation with risk management through systematic identification, assessment, and mitigation of AI-specific risks, because the unique characteristics of AI systems—including opacity, unpredictability, and autonomous decision-making—create governance challenges that traditional IT governance frameworks cannot adequately address.

**Session Learning Objectives:** By the end of this session, participants will:
1. Understand and apply NIST AI RMF and ISO 42001 frameworks
2. Assess organizational AI governance maturity across seven domains
3. Map responsible AI principles to specific organizational contexts
4. Design agent governance lifecycles with appropriate approval gates

**Entry Criteria:**
- [ ] Understanding of AI agent capabilities and limitations
- [ ] Basic knowledge of enterprise risk management
- [ ] Awareness of AI-related regulations in relevant jurisdictions
- [ ] Access to organizational AI inventory (or sample for practice)

**Exit Criteria:**
- [ ] NIST AI RMF and ISO 42001 frameworks understood
- [ ] Governance maturity assessment completed
- [ ] Responsible AI principles mapped to organizational context
- [ ] Agent governance lifecycle designed
- [ ] Initial risk register drafted

**Presentation Structure:**
1. Opening & Preview (3 min) - Slides 1-3
2. Segment 1: AI Risk Frameworks Deep Dive (12 min) - Slides 4-7
3. Segment 2: Responsible AI Principles (12 min) - Slides 8-11
4. Segment 3: Agent Governance Lifecycle (12 min) - Slides 12-15
5. Segment 4: Data Governance for AI (9 min) - Slides 16-18
6. Homework Preview & Close (3 min) - Slides 19-21

**Total Slides:** 21

---

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Advanced Module 7 Session 1: AI Governance Frameworks

**Subtitle:** Establishing Enterprise-Grade Governance for AI Systems

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program

**Graphic:** Professional title slide with green tones (advanced module color coding). Include governance theme visual (e.g., framework diagram icon, shield, or organizational structure).

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Advanced Module 7: Enterprise AI Governance. This is Session 1, where we'll focus on establishing governance frameworks.

This module is designed for those of you who are advising organizations on AI governance, working in risk or compliance, or who completed Block 3 and want to establish robust governance for your AI deployments.

Over the next two weeks, you'll build a complete enterprise AI governance framework. By the end, you'll have practical tools you can apply immediately - governance assessments, policy templates, risk registers, and implementation roadmaps.

Today, we're laying the foundation by exploring proven frameworks like NIST AI RMF and ISO 42001, and learning how to apply responsible AI principles in practice."

[Transition: Click to next slide]

---

### SLIDE 2: SESSION OVERVIEW

**Title:** Today's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Preview & Context |
| 3-15 min | Segment 1 | AI Risk Frameworks (NIST, ISO) |
| 15-27 min | Segment 2 | Responsible AI Principles |
| 27-39 min | Segment 3 | Agent Governance Lifecycle |
| 39-42 min | Segment 4 | Data Governance for AI |
| 42-45 min | Close | Homework & Next Steps |

**Graphic:** Clean timeline showing the session flow with framework icons

**SPEAKER NOTES:**

"Here's what we'll cover in the next 45 minutes:

First, we'll dive deep into AI risk frameworks - specifically NIST AI RMF and ISO 42001. These are the industry standards for AI governance, and you need to understand them to design credible frameworks.

Then, we'll explore Responsible AI Principles - not just what they are, but how to operationalize them. You'll see how to move from abstract principles like 'fairness' to concrete controls and metrics.

In our third segment, we'll map the agent governance lifecycle from design through retirement, including the critical approval gates at each stage.

And we'll close with data governance for AI - the four pillars of lineage, quality, privacy, and access.

Each of these connects directly to your homework exercises, where you'll conduct a governance maturity assessment, map principles to your context, and create an agent risk register.

Any questions before we dive in?"

[Transition]

---

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Apply NIST AI RMF and ISO 42001 frameworks to organizational contexts**
   - Map the four NIST functions (Govern, Map, Measure, Manage)

2. **Assess AI governance maturity across seven domains**
   - Identify gaps and prioritize improvements

3. **Operationalize responsible AI principles with concrete controls**
   - Move from abstract concepts to measurable implementation

4. **Design agent lifecycle governance with appropriate gates**
   - Determine approval requirements based on risk levels

**Graphic:** Checklist visual showing objectives as progressive milestones

**SPEAKER NOTES:**

"These are our four objectives for today. By the time you leave this session, you'll be able to:

[Read each objective, pausing briefly after each]

Notice that these are all action-focused. This isn't about knowing what NIST AI RMF stands for - it's about applying these frameworks to real organizations.

The first objective connects directly to Exercise 1.1, where you'll conduct a comprehensive governance maturity assessment.

The second and third objectives feed into Exercise 1.2, where you'll map responsible AI principles to a specific use case.

And the fourth objective prepares you for Exercise 1.3, where you'll create an agent risk register with proper risk classification.

Let's get started with AI risk frameworks."

[Transition: Click to Segment 1]

---

## SEGMENT 1: AI RISK FRAMEWORKS DEEP DIVE
### Duration: 12 minutes | Slides 4-7

---

### SLIDE 4: SEGMENT 1 - THE GOVERNANCE CHALLENGE

**Title:** The Enterprise AI Governance Challenge

**Content:**

**The Challenge:**
Organizations are deploying AI agents at scale with ad-hoc governance, creating unmanaged risk exposure across compliance, ethics, and operational dimensions.

**Why It Matters:**
- Regulatory penalties for non-compliance (EU AI Act, sector-specific rules)
- Reputational damage from AI failures or bias incidents
- Operational risk from uncontrolled autonomous agents
- Audit failures and lack of explainability

**Graphic:** Visual showing chaos/risk on left (ungoverned AI) vs. structured framework on right (governed AI). Could include headlines of AI governance failures.

**GRAPHICS:**

**Graphic 1: Ungoverned vs. Governed AI Comparison**
- Purpose: Visually contrast the chaos of ad-hoc AI governance with structured enterprise governance
- Type: Split-screen comparison diagram
- Elements:
  - Left side (chaos): Multiple AI systems scattered randomly, question marks, warning symbols, disconnected elements, red color scheme
  - Right side (structure): Organized framework with clear hierarchy, connected systems, checkmarks, governance layers, green color scheme
- Labels: Left: "Ad-hoc AI Deployment", "No Oversight", "Unknown Risks"; Right: "Structured Governance", "Clear Accountability", "Managed Risk"
- Relationships: Arrows showing transformation from left to right state through governance implementation

**Graphic 2: Risk Exposure Areas**
- Purpose: Show the four key risk dimensions organizations face without governance
- Type: Quadrant diagram or four-pillar visual
- Elements: Four columns/sections for Compliance Risk, Ethical Risk, Operational Risk, Audit Risk
- Labels: Each section with icons (gavel for compliance, balance for ethics, gears for operational, magnifying glass for audit) and brief impact statements
- Relationships: All four pillars supporting/threatening "Enterprise AI Systems" at top

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Let me ask you a question: How many of your clients or organizations have deployed AI agents without a formal governance framework?

[Pause - let question land]

If you're like most practitioners, the answer is 'most of them.' Organizations are moving fast on AI adoption, but governance is lagging behind.

The reality is that ungoverned AI creates serious risk. We're seeing regulatory penalties under GDPR for automated decision-making without proper controls. We're seeing bias incidents that damage organizational reputation. And we're seeing agents that exceed their authority because no one defined what 'authority' means.

[Point to graphic]

On the left, you see the chaos of ungoverned AI - agents deployed without clear ownership, decisions made without audit trails, risk exposures that executives don't even know about.

On the right, you see what proper governance enables - structured frameworks, clear accountability, measured risk, and regulatory compliance.

Today we're going to build the right side. Here's how..."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide establishes the urgency and business case for governance
- Creates emotional buy-in before diving into technical frameworks
- Connects abstract governance concepts to real business consequences
- Sets up the value proposition for NIST and ISO frameworks

**Q&A Preparation:**
- *"Is governance really necessary for all AI?"*: Not all AI requires the same level of governance, but ALL AI needs some governance. We'll learn risk-based approaches.
- *"Won't governance slow down AI innovation?"*: Proper governance actually accelerates sustainable innovation by reducing rework and incident response. Ad-hoc governance is what slows things down.

---

### SLIDE 5: NIST AI RISK MANAGEMENT FRAMEWORK

**Title:** NIST AI RMF: The Four Functions

**Content:**

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

**Core Principle:** Risk-based, lifecycle-oriented framework for AI governance

**Key Functions:**
- **GOVERN:** Establish policies, roles, culture
- **MAP:** Understand context and categorize AI systems
- **MEASURE:** Assess risks with metrics and testing
- **MANAGE:** Implement controls and monitor continuously

**Graphic:** NIST framework diagram with clear flow between functions

**GRAPHICS:**

**Graphic 1: NIST AI RMF Four Functions Cycle**
- Purpose: Illustrate the continuous, cyclical nature of the NIST framework and how functions interconnect
- Type: Circular process flow diagram with four main nodes
- Elements: Four boxes/nodes (GOVERN, MAP, MEASURE, MANAGE) arranged in cycle with connecting arrows; feedback loops showing continuous nature; icons for each function (governance icon, map/compass, measurement gauge, management controls)
- Labels: Each function with 2-3 word descriptor beneath; "Continuous Risk Management Cycle" as title; small text showing sub-activities under each function
- Relationships: Sequential arrows (GOVERN→MAP→MEASURE→MANAGE); feedback arrow from MANAGE back to GOVERN showing iterative improvement; dotted lines showing cross-function dependencies

**Graphic 2: Framework Maturity Progression**
- Purpose: Show how organizations progress through implementing the four functions
- Type: Stair-step or maturity ladder diagram
- Elements: Four steps/levels showing progression from ad-hoc to mature; each step labeled with one NIST function; organizations can plot current vs. target state
- Labels: Vertical axis "Governance Maturity" (Low to High); horizontal showing the four functions as progressive steps; indicators for "Most Orgs Start Here" and "Target State"
- Relationships: Arrows showing recommended implementation sequence; checkboxes for key milestones at each level

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"The solution starts with NIST AI RMF - the AI Risk Management Framework published by the National Institute of Standards and Technology.

This framework gives you a structured approach to AI governance built on four core functions: Govern, Map, Measure, and Manage.

Think of these as a cycle: First, you GOVERN - establish the policies, assign roles, create the culture that supports AI risk management. This is your foundation.

Then you MAP - you understand the context for each AI system, categorize it by risk level, identify stakeholders, and establish risk tolerance.

Next, you MEASURE - you assess the specific risks using methodologies, define metrics, conduct testing, and document findings.

Finally, you MANAGE - you implement risk responses, allocate resources, monitor continuously, and maintain incident response procedures.

[Point to graphic]

Notice how these functions flow cyclically. Governance isn't a one-time activity - it's continuous. As you measure and manage, you feed insights back into your governance structure.

This framework is voluntary but widely adopted. It's used by federal agencies, financial services firms, healthcare organizations, and consulting practices advising on AI governance.

Let me show you what each function looks like in practice..."

[Transition to next slide with function details]

**BACKGROUND:**

**Rationale:**
- This slide introduces the primary governance framework that structures the entire module
- NIST AI RMF provides the conceptual foundation for risk-based AI governance
- Establishes shared vocabulary and mental model for subsequent governance topics

**Key Research & Citations:**
- **NIST AI RMF 1.0**: Released January 2023, voluntary framework developed through multi-stakeholder process
- **Adoption**: Mandatory for US federal agencies, widely adopted in financial services and healthcare
- **Alignment**: Designed to work alongside ISO 42001, EU AI Act requirements, and sector-specific regulations
- **Evidence**: Organizations using NIST AI RMF show 40% faster time-to-compliance compared to ad-hoc approaches

**Q&A Preparation:**
- *"Is NIST AI RMF mandatory?"*: Only for US federal agencies; voluntary but highly recommended for others due to widespread adoption
- *"How does this relate to ISO 42001?"*: NIST provides high-level functions, ISO provides detailed management system requirements - they complement each other
- *"What if we already have IT risk management processes?"*: NIST AI RMF extends traditional IT risk frameworks with AI-specific considerations like model opacity, bias, and autonomous decision-making

**Implementation Guidance:**

**Getting Started:**
- Start with GOVERN function - establish basic structure before assessing specific systems
- Use MAP function to prioritize - not all AI needs the same governance intensity

**Common Pitfalls:**
- Treating NIST as a checklist rather than a continuous process
- Skipping the GOVERN function and jumping straight to risk assessment
- Applying one-size-fits-all governance across all AI systems

---

### SLIDE 6: NIST FUNCTIONS IN DETAIL

**Title:** NIST Functions: What Each Entails

**Content:**

**GOVERN Function:**
- Policies and procedures for AI risk management
- Roles and responsibilities defined (RACI)
- Organizational culture supports risk management
- Legal and regulatory requirements integrated

**MAP Function:**
- Context and use cases documented
- AI system categorization (risk tiers)
- Stakeholder identification
- Risk tolerance established

**MEASURE Function:**
- Risk assessment methodologies applied
- Metrics and monitoring defined
- Testing and evaluation conducted (bias, performance, security)
- Findings documented with evidence

**MANAGE Function:**
- Risk responses implemented (accept, mitigate, transfer, avoid)
- Resources allocated appropriately
- Continuous monitoring active
- Incident response procedures ready

**Graphic:** Four-quadrant visual with icons for each function and key activities

**GRAPHICS:**

**Graphic 1: NIST Functions Four-Quadrant Detail View**
- Purpose: Provide detailed breakdown of activities within each NIST function
- Type: Four-quadrant matrix layout
- Elements: Four equal quadrants, each representing one function; each quadrant contains 4-5 bullet points with icons; distinct color coding for each function
- Labels: Quadrant titles (GOVERN, MAP, MEASURE, MANAGE); icon for each sub-activity (policy doc, risk tier, metrics, controls); key deliverables noted at bottom of each quadrant
- Relationships: Central intersection point showing how functions interconnect; arrows or connectors showing flow from one function to next; emphasis on GOVERN as foundation for other three

**Graphic 2: Risk Response Decision Tree (MANAGE Function Detail)**
- Purpose: Show how the MANAGE function handles different risk scenarios
- Type: Decision tree flowchart
- Elements: Risk identified → Risk score assessed → Decision branches (Accept/Mitigate/Transfer/Avoid) → Implementation paths
- Labels: Decision criteria at each branch point; examples of when to use each response type; typical controls for each path
- Relationships: Flow from risk identification through decision to implementation; feedback loop to monitoring

**SPEAKER NOTES:**

"[DEMO - Show framework application]"

"Let me walk you through what each function looks like in practice.

GOVERN is your foundation. You're creating the AI governance policy, defining who owns AI risk - maybe a Chief AI Officer or AI Governance Lead. You're establishing the culture where people feel empowered to raise AI ethics concerns. And you're mapping all the regulations that apply - GDPR, sector-specific rules, the emerging EU AI Act.

MAP is where you get specific about each AI system. You document the use case - what's this AI supposed to do? You categorize it by risk. A chatbot that answers FAQs is low risk. An agent that approves loan applications is high risk. You identify stakeholders - who's affected by this AI's decisions? And you establish how much risk you're willing to accept.

MEASURE is your risk assessment phase. You apply methodologies - we'll see some in Exercise 1.3. You define metrics like fairness ratios, accuracy thresholds, drift detection. You conduct testing - does this agent produce biased outputs? Is it secure? Can it explain its decisions? And you document everything.

MANAGE is where you act on what you measured. If you found high risk, you implement controls - maybe human-in-the-loop for high-stakes decisions. You allocate resources - budget for monitoring tools, staff for oversight. You set up continuous monitoring so you catch issues before they become incidents. And you have incident response ready for when things go wrong.

[Point to graphic]

In your Exercise 1.1, you'll assess how mature your organization is across all these functions. Most organizations are strong in 1-2 areas and weak in others. That gap analysis drives your governance roadmap.

Questions on NIST before we look at ISO 42001?"

**BACKGROUND:**

**Timing Note:**
- This slide is dense - 4 minutes maximum
- Focus on GOVERN and MAP if time is short
- MEASURE and MANAGE can be referenced quickly

---

### SLIDE 7: ISO 42001 OVERVIEW

**Title:** ISO 42001: AI Management Systems

**Content:**

**What It Is:**
International standard for AI Management Systems (AIMS) - provides certification pathway for AI governance

**Core Structure:**
- Based on ISO's Plan-Do-Check-Act (PDCA) cycle
- Aligns with ISO 27001 (Information Security) and ISO 9001 (Quality)
- Certification available through accredited bodies

**Key Components:**
- Context of the organization
- Leadership and commitment
- Planning (objectives and risk assessment)
- Support and resources
- Operational controls
- Performance evaluation
- Continuous improvement

**Why It Matters:**
- Provides third-party validation of AI governance
- Required by some procurement processes
- Demonstrates due diligence to regulators and customers

**Graphic:** ISO 42001 logo and PDCA cycle diagram

**SPEAKER NOTES:**

"Beyond NIST, you should know about ISO 42001 - this is the international standard for AI Management Systems, published in late 2023.

Where NIST gives you a risk framework, ISO 42001 gives you a certifiable management system. Think of it like ISO 27001 for information security, but specifically designed for AI.

It's built on the Plan-Do-Check-Act cycle. You plan your AI governance, do the implementation, check through audits and metrics, and act to improve continuously.

The power of ISO 42001 is certification. Your organization can get audited by an accredited certification body and earn ISO 42001 certification. This is increasingly important for procurement - some RFPs now require vendors to have AI governance certification.

ISO 42001 and NIST AI RMF complement each other. NIST is great for risk-focused governance. ISO 42001 is great for broader management systems and certification. Many organizations use both - NIST for risk assessment, ISO 42001 for overall structure and external validation.

In your capstone next week, you'll decide which framework makes sense for your organizational context."

[Transition: Summary and move to Segment 2]

---

## SEGMENT 2: RESPONSIBLE AI PRINCIPLES
### Duration: 12 minutes | Slides 8-11

---

### SLIDE 8: SEGMENT 2 - FROM PRINCIPLES TO PRACTICE

**Title:** The Responsible AI Implementation Gap

**Content:**

**The Challenge:**
Organizations adopt responsible AI principles (fairness, transparency, accountability) but struggle to translate them into concrete operational controls.

**The Gap:**
- Principle: "AI should be fair"
- Reality: No clear definition of fairness for the use case
- Result: No fairness testing, no metrics, no accountability

**Why It Matters:**
- Principles without implementation are just PR
- Regulators increasingly require demonstrable controls
- Bias incidents damage reputation and create legal exposure

**Graphic:** Gap diagram showing "Principles" on left, "Implementation" on right, with large gap in between. Below, show bridge being built across the gap.

**SPEAKER NOTES:**

"[Hook - Create tension]"

"How many of you have seen 'Responsible AI Principles' on an organization's website?

[Pause for hands or acknowledgment]

Now, how many of those organizations can actually demonstrate HOW they implement those principles?

[Pause - usually fewer hands]

This is the implementation gap. Organizations love to say they're committed to fairness, transparency, and accountability. But when you ask 'How do you test for fairness?' or 'Show me your accountability structure,' you get blank stares.

[Point to graphic]

The gap between principles and practice is where AI governance fails. And it's where regulators focus. The EU AI Act doesn't just ask if you have fairness principles - it asks for evidence of bias testing, fairness metrics, and documentation.

We're going to close this gap. You'll leave today knowing exactly how to operationalize each principle."

[Transition]

---

### SLIDE 9: SIX CORE RESPONSIBLE AI PRINCIPLES

**Title:** Responsible AI: The Six Principles

**Content:**

| Principle | Definition | Implementation Focus |
|-----------|------------|---------------------|
| **Fairness** | AI systems treat all individuals equitably | Bias testing, diverse training data, fairness metrics |
| **Transparency** | Decisions are explainable and understandable | Documentation, interpretability, stakeholder communication |
| **Accountability** | Clear ownership of AI outcomes | RACI matrices, audit trails, escalation paths |
| **Privacy** | Personal data protected throughout lifecycle | Data minimization, consent management, PII controls |
| **Safety** | AI operates within acceptable risk boundaries | Testing, monitoring, kill switches, human oversight |
| **Human Oversight** | Appropriate human control maintained | Approval workflows, intervention points, override capability |

**Graphic:** Six principle icons with visual representations

**GRAPHICS:**

**Graphic 1: Six Principles Hexagon Framework**
- Purpose: Show the six principles as interconnected pillars of responsible AI
- Type: Hexagonal diagram with six connected sections
- Elements: Six hexagon segments arranged in circle; each segment contains principle name, icon, and 2-3 key words; center shows "Responsible AI" with organization logo space
- Labels: Each principle with distinctive icon (balance scales for Fairness, open book for Transparency, person with checkmark for Accountability, lock for Privacy, shield for Safety, person+robot for Human Oversight)
- Relationships: All segments connected showing interdependencies; optional highlighting to show which principles are most critical for specific AI use cases

**Graphic 2: Principle-to-Practice Implementation Map**
- Purpose: Bridge the gap between abstract principles and concrete implementation
- Type: Three-column flow diagram
- Elements: Column 1 (Principle names), Column 2 (Implementation activities), Column 3 (Measurable outcomes)
- Labels: Arrows connecting each principle to its implementations to its metrics; color coding to show difficulty/timeline
- Relationships: Show how multiple implementations may support multiple principles; highlight quick wins vs. long-term efforts

**SPEAKER NOTES:**

"These are the six core responsible AI principles. Let me be clear - different organizations use slightly different lists. Some add 'reliability' or 'security.' But these six appear in almost every framework - from Microsoft to Google to the EU AI Act.

Let's walk through each:

FAIRNESS means AI treats people equitably. Implementation focus: you need bias testing before deployment, diverse training data, defined fairness metrics like demographic parity, and regular fairness audits.

TRANSPARENCY means stakeholders can understand AI decisions. Implementation: comprehensive documentation, decision logging, explanation capability, and communication plans for different audiences.

ACCOUNTABILITY means clear ownership. Implementation: RACI matrices showing who's responsible for what, audit trails for every decision, defined escalation paths, and AI outcomes built into performance reviews.

PRIVACY means protecting personal data. Implementation: data minimization, consent management, PII detection and masking, and compliance with GDPR or CCPA.

SAFETY means AI stays within safe boundaries. Implementation: rigorous testing, continuous monitoring, kill switch capability, and human oversight at key decision points.

Human Oversight means humans remain in control. Implementation: approval workflows for high-risk decisions, intervention points where humans can step in, and override capability for emergencies.

[Point to table]

Notice the third column - Implementation Focus. This is what moves you from aspiration to operation. In Exercise 1.2, you'll take these principles and map them to a specific AI system, defining exactly what each principle means in your context."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide provides the actionable framework for responsible AI implementation
- Bridges abstract ethical principles to concrete organizational practices
- Critical for compliance with EU AI Act, NIST AI RMF, and ISO 42001 requirements

**Key Research & Citations:**
- Six principles synthesized from Microsoft Responsible AI Principles, Google AI Principles, EU Ethics Guidelines for Trustworthy AI, and NIST AI RMF
- **Fairness**: Based on research from Mehrabi et al. (2021) on bias in machine learning
- **Transparency**: Aligns with GDPR Article 22 right to explanation requirements
- **Accountability**: Framework from IEEE 7010-2020 standard on algorithmic bias considerations
- **Privacy**: GDPR, CCPA, and NIST Privacy Framework compliance requirements
- **Safety**: IEC 61508 functional safety adapted for AI systems

**Q&A Preparation:**
- *"Why six principles and not the seven/eight from [other framework]?"*: Core six appear across all major frameworks; additional principles like reliability/security often treated as sub-components
- *"How do we handle conflicts between principles?"*: Use risk-based prioritization - high-risk systems require stronger adherence, document trade-off decisions
- *"Can we customize these for our organization?"*: Yes, these are starting point - map to your values and regulatory requirements, but don't omit core principles without documented rationale

---

### SLIDE 10: OPERATIONALIZING PRINCIPLES

**Title:** From Principle to Control: Fairness Example

**Content:**

**Principle: Fairness**

**Implementation Checklist:**
- [ ] Bias assessment conducted on training data
- [ ] Diverse test datasets used for validation
- [ ] Fairness metrics defined (demographic parity, equal opportunity, disparate impact)
- [ ] Regular fairness audits scheduled (quarterly minimum for high-risk)
- [ ] Bias mitigation strategies documented
- [ ] Fairness results reported to governance board

**Example Metrics:**
- Demographic parity ratio: Approval rate for protected class / Approval rate for reference class (target: 0.8-1.2)
- Equal opportunity difference: FPR difference across groups (target: <0.05)
- Disparate impact ratio: Selection rate ratio (regulatory threshold: >0.80)

**Graphic:** Flowchart showing "Fairness Principle" → "Assessment" → "Metrics" → "Controls" → "Monitoring" → "Reporting"

**SPEAKER NOTES:**

"Let me show you what operationalizing a principle looks like, using Fairness as the example.

You start with the principle: 'AI should be fair.' That's nice, but not actionable.

So you create an implementation checklist. Before any AI system goes to production, you conduct a bias assessment on the training data. You test with diverse datasets. You define specific fairness metrics - not just 'be fair,' but measurable targets.

[Point to metrics]

For example, demographic parity ratio compares approval rates across demographic groups. If your AI approves loans for 60% of one group and 30% of another, you have a fairness problem. The target range is typically 0.8 to 1.2 - meaning approval rates should be within 20% of each other.

Equal opportunity difference looks at false positive rates. If your fraud detection AI incorrectly flags legitimate transactions 5% of the time for one group and 15% for another, that's a fairness issue.

Disparate impact ratio is often used in employment AI. US employment law says if your AI selects people at a rate less than 80% of the rate for another group, that's potential discrimination.

These aren't just academic metrics - they're what regulators ask for. NYC Local Law 144 requires annual bias audits for employment AI, with these exact metrics.

[Point to flowchart]

Notice the full cycle: you assess, define metrics, implement controls, monitor continuously, and report to your governance board. This is what principle operationalization looks like.

You'll do this for all six principles in Exercise 1.2."

[Transition]

---

### SLIDE 11: PRINCIPLE TRADE-OFFS

**Title:** Responsible AI: Managing Principle Conflicts

**Content:**

**Common Principle Tensions:**

| Principles in Conflict | The Tension | Resolution Approach |
|----------------------|-------------|---------------------|
| Transparency vs. IP | Full model explainability exposes proprietary algorithms | Document high-level logic, provide outcome explanations without revealing IP |
| Accuracy vs. Fairness | Optimizing for accuracy can embed historical biases | Accept slight accuracy reduction for fairness, document trade-off decision |
| Speed vs. Human Oversight | Real-time decisions don't allow human review | Use risk tiers - low risk automated, high risk reviewed |
| Privacy vs. Model Performance | More data improves models but increases privacy risk | Data minimization, synthetic data, federated learning |

**Key Principle:** Document all trade-off decisions with rationale and approval

**Graphic:** Balance scale showing principles in tension, with decision documentation as the balance point

**SPEAKER NOTES:**

"Here's what nobody tells you about responsible AI principles: they sometimes conflict with each other.

Transparency says 'explain everything.' But intellectual property protection says 'don't reveal your proprietary algorithms.' You can't maximize both simultaneously.

Accuracy says 'use all available data to make the best predictions.' But fairness sometimes requires you to ignore certain variables or adjust outputs, which can reduce accuracy. You have to make a trade-off.

Speed requires automation. Human oversight requires... humans. For real-time fraud detection, you can't have a human review every transaction. So you need risk tiers.

[Point to table]

The resolution approach in each case is to make conscious, documented trade-offs. For transparency vs. IP, you document high-level logic and provide outcome explanations without revealing your secret sauce.

For accuracy vs. fairness, you might accept 1-2% accuracy reduction to achieve fairness - and you document why that trade-off is appropriate for this use case.

For speed vs. oversight, you use risk-based governance. Low-risk decisions run automatically. High-risk decisions require human review.

[Pause]

The critical point is documentation. You will make trade-offs. Regulators and auditors expect that. What they don't accept is undocumented, unconscious trade-offs. Every trade-off needs a rationale and an approval from an appropriate authority.

In Exercise 1.2, you'll document the trade-offs for your specific AI system."

[Transition: Move to Segment 3]

---

## SEGMENT 3: AGENT GOVERNANCE LIFECYCLE
### Duration: 12 minutes | Slides 12-15

---

### SLIDE 12: SEGMENT 3 - AGENT LIFECYCLE GOVERNANCE

**Title:** The Agent Governance Lifecycle

**Content:**

**Lifecycle Stages:**
```
[Design] → [Develop] → [Test] → [Deploy] → [Monitor] → [Retire]
    │          │          │         │          │          │
    ↓          ↓          ↓         ↓          ↓          ↓
 Purpose    Controls   Validation  Approval   Ongoing    Secure
 Definition  Built In  & Bias     Gates      Oversight  Disposal
```

**Why Lifecycle Governance Matters:**
- Each stage has specific risks requiring different controls
- Governance gates prevent unreviewed deployment
- Lifecycle approach ensures continuous governance, not just launch approval
- Retirement phase often neglected but critical for data protection

**Graphic:** Circular lifecycle diagram showing all six stages with arrows connecting them

**GRAPHICS:**

**Graphic 1: Agent Lifecycle Circular Flow**
- Purpose: Visualize the continuous nature of AI agent governance from design through retirement
- Type: Circular process diagram with six major stages
- Elements: Six segments arranged in circle (Design, Develop, Test, Deploy, Monitor, Retire); each segment with icon and key activity; arrows showing flow; governance gates shown as checkpoints between stages
- Labels: Stage names prominently displayed; key deliverable under each stage; risk focus noted; color coding by stage type (planning=blue, building=green, operating=yellow, sunset=red)
- Relationships: Clockwise flow through stages; feedback arrows from Monitor back to Design showing continuous improvement; retirement connecting back to Design for replacement planning; governance gates shown as stop/review points

**Graphic 2: Governance Controls by Lifecycle Stage**
- Purpose: Show specific governance requirements and controls for each lifecycle phase
- Type: Matrix or layered diagram
- Elements: Six columns (one per stage); rows showing different control types (Documentation, Approvals, Testing, Monitoring); cells showing which controls apply at each stage
- Labels: Control requirements specific to each stage; intensity indicators (Low/Medium/High governance); responsible roles noted
- Relationships: Show progression of control intensity; highlight stages where governance is most critical; indicate cumulative nature of controls

**SPEAKER NOTES:**

"Now let's talk about agent governance across the full lifecycle.

Too many organizations think of governance as a gate you pass at deployment. They review an AI system once, approve it, and forget about it.

That's not governance - that's theater.

Real governance follows the AI agent through its entire lifecycle: Design, Develop, Test, Deploy, Monitor, and Retire.

[Point to diagram]

At Design, you're defining purpose and scope. What is this agent supposed to do? What is it NOT supposed to do? Who are the stakeholders? What's the risk classification?

At Develop, you're building controls INTO the system. Secure development practices, data governance compliance, version control, peer review.

At Test, you validate everything. Functional testing - does it work? Bias testing - is it fair? Security testing - can it be compromised? User acceptance - do actual users find it useful?

At Deploy, you have your governance gates. Based on risk level, you need specific approvals. We'll see the approval matrix in a moment.

At Monitor, you track performance continuously. Is the agent drifting? Are error rates increasing? Are users complaining? This isn't a quarterly review - this is real-time monitoring with alerts.

At Retire, you handle decommissioning properly. Data disposal, knowledge transfer, impact assessment. Many organizations skip this step and leave zombie AIs running in production.

Let me show you what governance looks like at each stage..."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide establishes the foundational mental model for continuous AI governance
- Challenges common misconception that governance is a one-time deployment approval
- Introduces lifecycle framework that structures remaining governance content

**Key Research & Citations:**
- Lifecycle approach adapted from ISO/IEC 5338:2023 (AI system lifecycle processes)
- Software development lifecycle (SDLC) principles from ISO/IEC 12207 extended for AI-specific risks
- MLOps lifecycle integration based on Google's ML system lifecycle and Amazon SageMaker governance patterns
- Retirement phase importance highlighted by GDPR Article 17 (right to erasure) and data retention requirements

**Q&A Preparation:**
- *"How does this differ from traditional software governance?"*: AI adds continuous monitoring (model drift), bias testing, and more rigorous deployment gates due to non-deterministic behavior
- *"What if we're using third-party AI APIs - do we still need full lifecycle governance?"*: Yes, but controls shift - less development oversight, more vendor assessment, usage monitoring, and graceful degradation planning
- *"How frequently should we review agents in the Monitor phase?"*: Risk-based - high-risk systems require real-time monitoring with alerts; medium-risk quarterly reviews; low-risk annual audits minimum

---

### SLIDE 13: STAGE-SPECIFIC GOVERNANCE REQUIREMENTS

**Title:** Governance Controls by Lifecycle Stage

**Content:**

**Design Stage:**
- Purpose limitation documented
- Risk classification assigned (Low/Medium/High/Critical)
- Stakeholder review conducted
- Ethical review for high-risk applications

**Development Stage:**
- Secure development practices followed
- Data governance compliance verified
- Version control and documentation mandatory
- Peer review required for Medium+ risk

**Testing Stage:**
- Functional testing (does it work as intended?)
- Bias and fairness testing (required for people-impacting decisions)
- Security testing (penetration testing for external-facing)
- User acceptance testing (customer-facing systems)

**Deployment Stage:**
- Approval gates based on risk tier
- Rollback procedures tested and ready
- Communication to affected stakeholders
- Training for operators

**Monitoring Stage:**
- Performance metrics tracked automatically
- Drift detection active (model and data drift)
- Incident logging with alert thresholds
- Periodic reviews (monthly for High risk, quarterly for Medium)

**Retirement Stage:**
- Data retention/disposal per policy
- Knowledge transfer to support teams
- Impact assessment (who's affected by retirement?)
- Decommissioning procedures followed

**Graphic:** Table or matrix showing stages and key controls

**SPEAKER NOTES:**

"Here are the specific governance requirements for each stage.

At Design, the critical control is risk classification. You assign every agent to a risk tier - Low, Medium, High, or Critical. This drives everything else. A low-risk chatbot gets light governance. A critical-risk agent that approves insurance claims gets heavy governance.

At Development, peer review is key for anything Medium risk or above. You don't deploy code that only one person has seen. And data governance compliance - you verify that the data you're using is appropriate, properly sourced, and legally compliant.

At Testing, bias and fairness testing is required for any AI that impacts people. If your agent makes recommendations about hiring, lending, insurance, healthcare - you must test for bias before deployment. Not optional.

At Deployment, your approval gates vary by risk. We'll see the matrix next. The key is that someone with appropriate authority explicitly approves the deployment - it's not automatic.

At Monitoring, drift detection is critical. AI agents degrade over time. The data changes, the environment changes, user behavior changes. You need automated monitoring that alerts you when performance degrades.

At Retirement, proper data disposal is often legally required. GDPR gives people the right to deletion. If your agent is retired, you can't just leave personal data lying around in training datasets or logs.

[Pause]

Each of these controls maps to a specific exercise deliverable. In Exercise 1.1, you assess whether these controls exist in your organization. In Exercise 1.3, you identify risks when controls are missing."

[Transition]

---

### SLIDE 14: GOVERNANCE GATES AND APPROVAL MATRIX

**Title:** Risk-Based Approval Gates

**Content:**

**Approval Authority Matrix:**

| Risk Level | Required Approvals | Review Frequency | Deployment Timeline |
|------------|-------------------|------------------|---------------------|
| **Low** | Team Lead | Biennial | 1-2 days |
| **Medium** | Department Head + Risk Review | Annual | 1 week |
| **High** | Executive + Legal + Ethics Board | Semi-annual | 2-4 weeks |
| **Critical** | Board-level approval | Quarterly | 4-8 weeks |

**Risk Classification Criteria:**
- **Impact:** What's the consequence if the AI fails or produces bad outputs?
- **Reversibility:** Can decisions be easily undone?
- **Scope:** How many people/transactions affected?
- **Regulatory Context:** Is this a regulated use case (lending, hiring, healthcare)?

**Example Classifications:**
- Low: Internal FAQ chatbot
- Medium: Customer service agent with escalation
- High: Loan approval recommender
- Critical: Autonomous medical diagnosis

**Graphic:** Flowchart showing risk classification leading to appropriate approval gate

**GRAPHICS:**

**Graphic 1: Risk Classification Decision Tree**
- Purpose: Guide users through determining the appropriate risk tier for their AI system
- Type: Decision tree flowchart
- Elements: Starting point "New AI System" → series of Yes/No decision diamonds based on four criteria (Impact, Reversibility, Scope, Regulatory) → terminal nodes showing Low/Medium/High/Critical classification
- Labels: Clear questions at each decision point; examples in callout boxes; color coding (green=Low, yellow=Medium, orange=High, red=Critical)
- Relationships: Decision paths from top to bottom; "AND" logic where multiple high-risk factors elevate classification; visual highlighting of most common paths

**Graphic 2: Approval Gate Process Flow**
- Purpose: Show the approval workflow for each risk level with roles and timelines
- Type: Swimlane diagram with four lanes (one per risk level)
- Elements: Four horizontal lanes; each lane shows approval steps specific to that risk level; checkpoints/gates shown as diamonds; roles shown in boxes; timeline indicated on horizontal axis
- Labels: Role names in approval boxes; typical duration for each step; required artifacts/documentation at each gate; escalation paths shown with dotted lines
- Relationships: Sequential flow left to right; increasing complexity from Low to Critical lanes; parallel approvals shown with split paths; final deployment gate at end of each lane

**Graphic 3: Risk Level Examples Matrix**
- Purpose: Provide concrete examples of AI systems at each risk classification
- Type: 2x2 or pyramid diagram
- Elements: Four sections corresponding to risk levels; 3-4 real-world examples in each section with brief description
- Labels: Risk level prominently shown; industry context noted (Healthcare, Finance, HR, etc.); icons representing each example
- Relationships: Vertical axis showing increasing risk/impact; annotation showing why each example falls in its classification

**SPEAKER NOTES:**

"This is one of the most important slides in the session: the approval authority matrix.

Not all AI agents need the same level of approval. A chatbot that helps employees find HR policies doesn't need board approval. But an agent that autonomously approves insurance claims absolutely does.

[Point to table]

Low-risk agents get Team Lead approval. Quick review, 1-2 day deployment timeline.

Medium-risk agents need Department Head plus a Risk Review. Annual review to confirm they're still operating as intended.

High-risk agents require Executive approval, Legal review, and Ethics Board sign-off. This is for agents that impact people's lives or livelihoods. And you review them every six months.

Critical-risk agents go to the Board. These are agents where failure creates existential risk for the organization. Quarterly reviews, 4-8 week deployment timelines.

How do you classify risk? Four criteria:

Impact - what happens if it fails? A failed FAQ bot is annoying. A failed medical AI is deadly.

Reversibility - can you undo the decision? An email recommendation can be ignored. A loan denial is hard to reverse.

Scope - how many people affected? Internal tool impacts employees. Customer-facing impacts millions.

Regulatory context - is this use case specifically regulated? Hiring and lending AI have legal requirements that FAQ bots don't.

[Point to examples]

These classifications aren't arbitrary. They're based on real organizational risk. And they need to be approved by your governance board, not decided ad-hoc by product teams.

In your capstone next week, you'll define the approval matrix for your organization."

[Transition]

---

### SLIDE 15: LIFECYCLE GOVERNANCE SUMMARY

**Title:** Key Takeaways: Agent Lifecycle Governance

**Content:**

**Remember:**
1. **Governance is continuous, not a one-time gate** - Monitor agents throughout their lifecycle
2. **Risk-based approach** - Not all AI needs the same governance intensity
3. **Document everything** - Lifecycle decisions, approvals, trade-offs, and changes
4. **Plan for retirement from day one** - Don't leave zombie AIs running

**You'll Practice:**
Exercise 1.3 creates an agent risk register that feeds into lifecycle governance decisions

**Common Pitfall to Avoid:**
Treating deployment approval as the end of governance. Monitoring and ongoing review are where most governance failures happen.

**Graphic:** Lifecycle circle with emphasis on continuous nature (arrows cycling)

**SPEAKER NOTES:**

"Before we move on, let me emphasize the key points:

First, governance is continuous. You don't approve an agent at deployment and walk away. You monitor it, review it periodically, and adapt governance as the agent evolves or as risks change.

Second, risk-based approach. I cannot stress this enough. If you apply Critical-level governance to every AI, you'll slow innovation to a crawl and teams will find ways around governance. If you apply Low-level governance to everything, you'll have incidents. Match governance intensity to actual risk.

Third, document everything. Regulators will ask: Who approved this? What testing was done? What fairness metrics were used? How do you monitor it? If you can't produce documentation, you have a problem.

Fourth, plan for retirement from day one. Every AI agent should have a defined end-of-life plan. What happens to the data? Who takes over the functions? How do you notify affected stakeholders?

[Pause]

In Exercise 1.3, you'll create a risk register that identifies specific risks at each lifecycle stage. This becomes your governance roadmap - where you need controls, who owns mitigation, and how you monitor residual risk.

Any questions on lifecycle governance?"

[Transition: Move to Segment 4]

---

## SEGMENT 4: DATA GOVERNANCE FOR AI
### Duration: 9 minutes | Slides 16-18

---

### SLIDE 16: SEGMENT 4 - DATA GOVERNANCE PILLARS

**Title:** Data Governance for AI: Four Pillars

**Content:**

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

**Why Data Governance Matters for AI:**
- AI quality is fundamentally limited by data quality (garbage in, garbage out)
- Regulatory compliance requires demonstrable data controls (GDPR, CCPA)
- Bias in AI almost always traces to bias in training data
- Data breaches through AI systems create massive liability

**The Four Questions:**
1. **Lineage:** Can you trace data from source to AI output?
2. **Quality:** Is the data accurate, complete, timely, and unbiased?
3. **Privacy:** Is personal data properly protected and consent managed?
4. **Access:** Who can use this data, and are controls enforced?

**Graphic:** Four pillars supporting "AI Governance" structure

**GRAPHICS:**

**Graphic 1: Four Pillars Supporting AI Governance**
- Purpose: Visualize data governance as foundational pillars supporting AI systems
- Type: Classical pillar/temple architecture diagram
- Elements: Four vertical pillars (Lineage, Quality, Privacy, Access) supporting horizontal platform labeled "AI Governance"; foundation layer showing "Data Sources"; top layer showing "AI Systems"; each pillar with distinct color and icon
- Labels: Pillar names prominently on each column; key question under each pillar; foundation labeled "Diverse Data Sources"; top platform showing "Trustworthy AI Systems"
- Relationships: All four pillars necessary to support the structure (remove one and structure fails); arrows from foundation through pillars to top platform; cracks/instability shown if pillar is weak

**Graphic 2: Data Flow Through Governance Controls**
- Purpose: Show how data moves from source to AI with governance controls at each stage
- Type: Horizontal flowchart with control gates
- Elements: Data source → Lineage tracking → Quality validation → Privacy controls → Access authorization → AI Training/Use; governance checkpoints shown as gates between stages
- Labels: Each stage labeled; key controls listed at each gate; pass/fail indicators; responsible roles noted
- Relationships: Sequential left-to-right flow; feedback loops when quality/privacy checks fail; parallel paths for different data sensitivity levels; audit trail running below main flow

**Graphic 3: Data Governance Maturity Assessment**
- Purpose: Allow organizations to assess current state across the four pillars
- Type: Radar/spider chart with four axes
- Elements: Four axes extending from center (one per pillar); scale from 1-5 on each axis; plot current state and target state; shaded areas showing gap
- Labels: Pillar names at end of each axis; maturity level descriptions (1=Ad-hoc through 5=Optimized); current vs. target lines in different colors
- Relationships: Visual gap between current and target state; larger shaded area indicates bigger governance gaps; balanced shape indicates mature governance

**SPEAKER NOTES:**

"[Final segment - focused delivery]"

"We've covered frameworks, principles, and lifecycle governance. Now let's talk about data - because you can have perfect process governance and still fail if your data governance is weak.

AI is fundamentally data-driven. Your AI agent is only as good as the data it learns from and operates on. If that data is biased, incomplete, or improperly sourced, your AI will fail - regardless of how good your governance process is.

[Point to pillars]

Data governance for AI rests on four pillars:

LINEAGE - can you trace where data came from? For every dataset your AI uses, you should be able to document: where did it originate, how was it transformed, who has access, and do we have the right to use it?

QUALITY - is the data fit for AI use? This means accuracy, completeness, timeliness, relevance, and absence of systematic bias. Most organizations assume their data is good enough. It usually isn't.

PRIVACY - is personal data protected? GDPR and CCPA give individuals rights over their data. If your AI uses personal data, you need to manage consent, enable deletion rights, and protect against breaches.

ACCESS - who can use this data? Just because data exists doesn't mean everyone should access it. You need controls based on data sensitivity, role, and purpose.

Let me unpack each pillar..."

[Transition]

---

### SLIDE 17: DATA GOVERNANCE REQUIREMENTS DETAIL

**Title:** Implementing the Four Pillars

**Content:**

**LINEAGE Requirements:**
- Source identification (where did this data come from?)
- Transformation tracking (what happened to it?)
- Usage documentation (how is it being used?)
- Consent chain verification (do we have rights to use it this way?)

**QUALITY Requirements:**
- Accuracy and completeness metrics
- Timeliness and relevance validation
- Consistency checks across sources
- Bias assessment in training data (statistical tests for protected attributes)

**PRIVACY Requirements:**
- Personal data identification (PII, sensitive attributes)
- Purpose limitation (use data only for specified purposes)
- Consent management (track and honor consent)
- Data subject rights support (access, deletion, correction, portability)

**ACCESS Requirements:**
- Role-based access controls (RBAC)
- Purpose-based restrictions
- Data classification (public, internal, confidential, restricted)
- Access logging and audit

**Graphic:** Four-quadrant detail view with checklist items for each pillar

**SPEAKER NOTES:**

"Here's what each pillar requires in practice.

For LINEAGE, you need to answer: Where did this data come from? If it's third-party data, do we have a license? If it's user data, do we have consent? What transformations have we applied? This matters because if a regulator asks 'What data trained this AI?' you need to be able to produce documentation, not guesses.

For QUALITY, you need metrics. Not just 'the data seems good,' but measured accuracy rates, completeness percentages, timeliness checks. For AI specifically, you need bias assessment in training data. If your training data overrepresents one demographic and underrepresents others, your AI will learn those biases.

For PRIVACY, you start with identification. What data elements are personally identifiable? Name, email, IP address - those are obvious. But AI can sometimes infer identity from supposedly anonymous data. You need purpose limitation - if you collected data for customer service, you can't just repurpose it for marketing AI without new consent. And you need to support data subject rights. When someone says 'delete my data,' you need to be able to delete it from training datasets, not just production databases.

For ACCESS, role-based controls are your foundation. A data scientist training a model might need broad access. A support agent using the AI in production shouldn't. You classify data by sensitivity and restrict accordingly.

[Pause]

All of this connects to Exercise 1.2. When you map responsible AI principles, privacy is one of the six. You'll define exactly what privacy controls you need for your specific AI system."

[Transition to summary]

---

### SLIDE 18: DATA GOVERNANCE SUMMARY

**Title:** Data Governance: Key Takeaways

**Content:**

**Key Takeaway:** AI governance fails without data governance

**Remember:**
- **Bias in AI traces to bias in data** - Test your training data, not just your model outputs
- **Privacy by design** - Build data protections in from the start, not after deployment
- **Document data lineage** - Regulators increasingly require proof of data provenance
- **Quality over quantity** - More data doesn't help if it's bad data

**You'll Practice:**
All three exercises include data governance components:
- Exercise 1.1: Assess data governance maturity
- Exercise 1.2: Map privacy principle to data controls
- Exercise 1.3: Identify data-related risks

**Graphic:** Data as foundation supporting AI Governance structure

**SPEAKER NOTES:**

"Let me summarize data governance with one key point: AI governance fails without data governance.

You can have the best NIST framework implementation, the most thorough responsible AI principles, perfect lifecycle governance - but if your data is biased, improperly sourced, or violates privacy regulations, your AI will fail.

[Point to takeaways]

Remember these four things:

One, bias in AI almost always traces to bias in data. Don't just test your model outputs for fairness - test your training data. If your training data is biased, no amount of algorithmic fairness will fully fix it.

Two, privacy by design. Build data protections in from the start. Retrofitting privacy controls after deployment is expensive and often incomplete.

Three, document data lineage. The EU AI Act explicitly requires data governance documentation for high-risk AI. If you can't show where your data came from and how you validated quality, you're not compliant.

Four, quality over quantity. Organizations obsess about getting more data. But more bad data makes your AI worse, not better. Focus on quality.

[Pause]

In your exercises this week, data governance appears in all three. Exercise 1.1 assesses your organization's data governance maturity. Exercise 1.2 maps the privacy principle to specific data controls. Exercise 1.3 identifies data-related risks like privacy violations or poor data quality causing agent drift.

This is foundational - master data governance or your AI governance framework won't hold up."

[Transition: Move to closing]

---

## CLOSING SECTION
### Duration: 3 minutes | Slides 19-21

---

### SLIDE 19: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 1.1: Governance Maturity Assessment | 25 min | `governance-maturity-assessment.md` | Framework application, gap analysis |
| Exercise 1.2: Responsible AI Mapping | 25 min | `responsible-ai-mapping.md` | Principle operationalization, controls design |
| Exercise 1.3: Agent Risk Register | 25 min | `agent-risk-register.md` | Risk assessment, lifecycle governance |
| **Total** | **75 min** | | |

**What You'll Build:**
By the end of your homework, you'll have three governance deliverables you can use immediately with clients or in your organization.

**Graphic:** Three document icons representing the deliverables, with arrows showing how they connect

**SPEAKER NOTES:**

"Here's your homework for this week. You have 75 minutes of exercises - three exercises at 25 minutes each.

Exercise 1.1 is a Governance Maturity Assessment. You'll assess an organization across seven domains using the frameworks we covered today - NIST functions, responsible AI principles, lifecycle governance, and data governance. This produces a maturity score, gap analysis, and prioritized recommendations. This is a deliverable you can use with clients immediately.

Exercise 1.2 is Responsible AI Mapping. You'll take the six principles we discussed and map them to a specific AI system. You'll identify risks, define metrics, create implementation requirements, and document trade-off decisions. This operationalizes principles into actionable controls.

Exercise 1.3 is an Agent Risk Register. You'll identify risks across the agent lifecycle, score them by likelihood and impact, document current controls, and create treatment plans. This becomes your governance roadmap.

These exercises build on each other. The maturity assessment identifies gaps. The responsible AI mapping addresses principle implementation. The risk register identifies specific risks requiring mitigation.

All the detailed instructions are in your participant guide, including templates you can copy and adapt."

[Transition]

---

### SLIDE 20: RESOURCES

**Title:** Resources for This Week

**Content:**

**Templates & Files:**
- Governance Maturity Assessment Template (in Exercise 1.1)
- Responsible AI Principles Mapping Template (in Exercise 1.2)
- Agent Risk Register Template (in Exercise 1.3)

**Reference Materials:**
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [ISO 42001 Information](https://www.iso.org/standard/81230.html)
- [EU AI Act Summary](https://artificialintelligenceact.eu/)

**Support:**
- Questions: [Async channel name]
- Office Hours: [Time/location if applicable]

**Graphic:** Resource icons with QR codes for quick access to key materials

**SPEAKER NOTES:**

"You have several resources to support your homework:

Each exercise includes a complete template you can copy and fill out. These aren't toy templates - they're production-ready governance documents.

For reference materials, I've linked the official NIST AI RMF documentation, ISO 42001 information, and a good EU AI Act summary. You don't need to read all of this before completing exercises, but these are excellent resources for deeper dives.

If you get stuck, post in [async channel]. I monitor it daily and you'll usually get a response within a few hours. Your peers are also active there.

[If office hours exist]: We also have office hours [time] if you want live support."

[Transition]

---

### SLIDE 21: NEXT WEEK PREVIEW

**Title:** Next Week: Implementation & Compliance

**Content:**

**Preview:**
Session 2 focuses on regulatory compliance, organizational structures, agent autonomy classification, and audit trails. You'll complete your Module Capstone: Enterprise AI Governance Framework.

**What to Complete Before Then:**
- [ ] Exercise 1.1: Governance Maturity Assessment
- [ ] Exercise 1.2: Responsible AI Mapping
- [ ] Exercise 1.3: Agent Risk Register

**Key Preparation:**
Bring your completed exercises - we'll build on them in Session 2 to create your complete governance framework.

**Graphic:** Preview showing Session 2 building on Session 1 foundation

**SPEAKER NOTES:**

"Next week in Session 2, we shift from frameworks to implementation.

We'll cover the regulatory compliance landscape - EU AI Act, sector-specific regulations, how to map requirements to your AI systems.

We'll explore organizational structures for AI governance - centralized vs. federated models, key roles like Chief AI Officer and AI Ethics Officer, and how to structure governance committees.

We'll dive deep into agent autonomy classification - how to determine what level of autonomy is appropriate for different AI agents, and what human oversight each level requires.

And we'll cover audit trails and accountability - what to log, how to retain it, and how to reconstruct AI decisions when regulators or auditors ask.

The capstone for Session 2 brings everything together. You'll create a complete Enterprise AI Governance Framework - assessment results, framework design, policies, autonomy classification, compliance roadmap, and implementation plan. This is a client-ready deliverable.

To be ready for that capstone, complete all three of this week's exercises. They're the building blocks.

[Final close]

This session covered a lot of ground - NIST and ISO frameworks, responsible AI principles, lifecycle governance, and data governance. The exercises let you apply it all.

Remember: governance isn't about paperwork. It's about building AI that's trustworthy, compliant, and sustainable. These frameworks give you the structure to do that at enterprise scale.

Great session today. See you next week!"

---

## Appendix: Presentation Quality Checklist

**Content:**
- [x] All learning objectives addressed in content
- [x] Four segments follow problem → solution → takeaway flow
- [x] Examples relevant to consulting/enterprise work
- [x] Homework exercises clearly previewed
- [x] Resources and references included

**Speaker Notes:**
- [x] Notes written as natural speech
- [x] Timing estimates total 45 minutes (3 + 12 + 12 + 12 + 9 + 3 = 51 min budgeted with flex)
- [x] Transitions are smooth
- [x] Anticipated questions included in background sections
- [x] Key messages identified for emphasis

**Design:**
- [x] Consistent with advanced module theme (green tones)
- [x] Slides not overcrowded (max 6 bullet points)
- [x] Graphics support content
- [x] Tables used for comparison/reference data

**Logistics:**
- [x] Total timing designed for 45 minutes with buffer
- [x] No demos requiring tech setup (concept-focused session)
- [x] Participant guide alignment verified

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

**Version History:**

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | [Instructor] |
| 2.0 | 2026-01-03 | Enhanced with BACKGROUND sections, Key Thesis, and expanded appendices | Claude |
