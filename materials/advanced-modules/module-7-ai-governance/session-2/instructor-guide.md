# **INSTRUCTOR GUIDE: ADVANCED MODULE 7 SESSION 2**
## **Implementation & Compliance**

**Module:** Advanced Module 7: Enterprise AI Governance
**Session:** 2 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes (includes 25-min capstone)

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Regulatory compliance, organizational structures, agent autonomy classification, audit trails, and capstone integration |
| **Difficulty Level** | High - Implementation-focused with regulatory complexity |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | No - Concept and policy-focused session |
| **Tech Setup Needed** | Presentation slides, screen share, access to example policies (optional) |
| **Common Challenges** | Regulatory landscape complexity, organizational design requires context, capstone integration requires Session 1 completion |

---

## Navigation

**Module Navigation:** [← Session 1 Instructor Guide](../session-1/instructor-guide.md) | Session 2

**Related Materials:**
- [Session 2 Presentation Slides](presentation.md)
- [Session 2 Participant Guide](participant-guide.md)
- [Module 7 Main Document](../module-7-ai-governance.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review Session 1 completion | Check how many participants completed all 3 exercises | ☐ |
| Review EU AI Act basics | Refresh on risk tiers and requirements | ☐ |
| Prepare regulatory examples | Identify 1-2 recent AI compliance cases (enforcement or incidents) | ☐ |
| Check resources | Verify links to EU AI Act, SR 11-7, NYC Law 144 work | ☐ |
| Review capstone template | Familiarize with expected deliverable structure | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and practice regulatory segment | ☐ |
| Review timing | This session has capstone preview - ensure time for it | ☐ |
| Prepare organizational examples | Have 1-2 examples of governance structures (centralized vs. federated) | ☐ |
| Check participant progress | Identify who needs Session 1 deliverables for capstone | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all materials | Presentation, EU AI Act reference, example policies | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Ask about Session 1 exercise completion | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, Session 1 recap, preview | Connect to prior week |
| 0:03 | 12 min | Segment 1 | Regulatory Compliance (EU AI Act, sector regs) | Dense regulatory content |
| 0:15 | 10 min | Segment 2 | Organizational Structures | Shorter segment |
| 0:25 | 12 min | Segment 3 | Agent Autonomy Classification | Core implementation content |
| 0:37 | 11 min | Segment 4 | Audit Trails & Accountability | Technical but critical |
| 0:48 | 3 min | Closing | Capstone preview, resources, final message | Must emphasize capstone |
| **Total** | **51 min** | | **(includes 6-min buffer)** | Aim for 45-48 min |

### Timing Flexibility

**If Running Behind:**
- Segment 1: Condense sector-specific regulations to high-level only
- Segment 2: Shorten organizational roles discussion, reference participant guide
- Segment 3: Skip autonomy boundaries detail slide
- Segment 4: Condense retention requirements discussion

**If Running Ahead:**
- Add real-world compliance failure example
- Expand organizational structure discussion with participant poll
- Include additional autonomy classification example
- Take extended Q&A on capstone requirements

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | Condense sector regulations if behind |
| End Segment 3 | 0:37 | Autonomy boundaries optional; keep classification system complete |
| Start Closing | 0:45 | Must start by 0:45 to ensure capstone preview completes |

---

## Session Delivery Guide

### Opening (3 minutes)

**Key Actions:**
1. Welcome and connect to Session 1
2. Quick recap of Session 1 frameworks and deliverables
3. Preview Session 2 as implementation focus
4. Set expectation for capstone

**Opening Script:**
> "Welcome to Session 2. Last week we built the governance foundation - NIST frameworks, responsible AI principles, lifecycle thinking, data governance. You created three deliverables: maturity assessment, principles mapping, and risk register.
>
> Today we make it operational. You'll learn regulatory compliance requirements from EU AI Act to sector-specific regulations. You'll design governance structures. You'll classify agent autonomy levels. And you'll understand audit trail requirements.
>
> Most importantly, you'll complete the capstone - a complete Enterprise AI Governance Framework that integrates everything from both sessions. This is a client-ready deliverable.
>
> Let's start by connecting to last week."

---

### Segment 1: Regulatory Compliance Landscape (12 minutes)

**Learning Objective:** Map regulatory compliance requirements to AI systems

**Key Teaching Points:**
- EU AI Act is most comprehensive AI regulation currently (4 risk tiers)
- High-risk systems have 7 core requirements (risk mgmt, data gov, documentation, etc.)
- Sector regulations often stricter than general AI law
- Compliance is ongoing, not one-time

**Delivery Tips:**
- Use recent enforcement example if available (GDPR penalties for automated decisions, bias lawsuits)
- Emphasize that compliance is cross-functional (not just legal)
- Connect to Exercise 2.1 compliance mapping template

**Common Question:** "Does EU AI Act apply to US companies?"
**Answer:** "Yes, if you offer products/services in EU or if outputs are used in EU. Similar to GDPR extraterritorial reach. US companies with EU customers need to comply."

---

### Segment 2: Organizational Structures (10 minutes)

**Learning Objective:** Design governance organizational structures

**Key Teaching Points:**
- Centralized vs. federated models (no one-size-fits-all)
- Key roles: Chief AI Officer, AI Ethics Officer, AI Risk Manager, Governance Lead, Model Validators
- Governance committees: Steering, Ethics Board, Risk Committee, Data Council
- Start lean, evolve as maturity grows

**Delivery Tips:**
- Poll participants: "How many work in centralized vs. federated organizations generally?" (helps them self-identify)
- Emphasize matching structure to organizational culture
- Connect to capstone where they recommend structure

---

### Segment 3: Agent Autonomy Classification (12 minutes)

**Learning Objective:** Classify agent autonomy and define oversight

**Key Teaching Points:**
- Five levels: 0 (Tool) through 4 (Autonomous)
- Classification uses 3 factors: Impact, Reversibility, Compliance context
- Define boundaries (financial limits, stakeholder scope, data sensitivity)
- Escalation triggers (confidence, novel situations, error spikes)

**Delivery Tips:**
- Use concrete examples for each autonomy level
- Interactive: Ask participants to classify a specific AI (e.g., medical diagnosis AI)
- Emphasize: Autonomy should match risk, not technical capability

**Common Confusion:** "Can we change autonomy level over time?"
**Clarification:** "Yes - review periodically. As AI improves or risk changes, autonomy classification can be adjusted. But require governance approval for changes."

---

### Segment 4: Audit Trails & Accountability (11 minutes)

**Learning Objective:** Implement audit trail requirements and accountability

**Key Teaching Points:**
- Comprehensive audit record has 10+ fields (timestamp, agent ID, action, input/output, reasoning, data accessed, human oversight, confidence, model version, outcome)
- Retention driven by regulatory (5-7 years), legal, operational needs
- Accountability has 3 levels: Operator, Developer, Executive
- Accountable role must always be human

**Delivery Tips:**
- Walk through audit record structure field by field
- Emphasize "accountable must be human" - critical governance principle
- Connect to Exercise 2.2 policy on audit requirements

---

### Closing (3 minutes)

**Critical Section - DO NOT SKIP**

**Key Actions:**
1. Preview capstone structure (7 parts)
2. Emphasize it integrates all prior deliverables
3. Set expectation: 25 minutes using templates
4. Provide resources
5. Close module

**Script:**
> "Your capstone integrates everything. Part 1 uses your maturity assessment. Part 2 is framework design with organizational structure and policies. Part 3 is autonomy classification. Part 4 is compliance roadmap. Part 5 is implementation plan with quick wins.
>
> This is what you'd present to executives. It's comprehensive, actionable, client-ready.
>
> Estimated time: 25 minutes using your prior work and the template provided.
>
> This has been an intensive module - lots of frameworks, regulations, implementation details. But you now have capability that's in high demand. Organizations need enterprise AI governance. You can build it."

---

## Anticipated Questions & Answers

**Q: Our organization operates globally - how do we handle multiple regulatory regimes?**
A: Map all applicable regulations in Exercise 2.1. Design governance that meets the strictest requirements (usually satisfies less strict ones). For region-specific rules, add regional supplements to core policies.

**Q: We don't have a Chief AI Officer - can we still do governance?**
A: Absolutely. Start with AI Governance Lead (can be part-time). Add roles as AI maturity grows. Don't wait for perfect structure to start governance.

**Q: What autonomy level should generative AI chatbots have?**
A: Depends on use case. Customer service chatbot with human monitoring: Level 2 (Supervised). Internal FAQ bot: Level 3 (Managed). Legal advice chatbot: Level 0-1 (Tool/Assistant with human approval).

**Q: How do we audit AI decisions when the model is a black box?**
A: You can't fully explain neural network internals, but you CAN log: what inputs were used, what output was generated, what confidence score, what data sources, whether human approved. Explainability doesn't require complete transparency into weights.

---

## Post-Session Tasks

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post capstone expectations/clarifications in support channel | ☐ |
| Share example governance framework (redacted/anonymized) if available | ☐ |
| Answer pending questions | ☐ |
| Review any completed capstones submitted early | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review submitted capstones (spot check) | ☐ |
| Provide feedback on capstone quality | ☐ |
| Document lessons learned for curriculum improvement | ☐ |
| Celebrate module completion with cohort | ☐ |

---

## Capstone Assessment Notes

**Quality Indicators:**
- Integration of Session 1 deliverables (not starting from scratch)
- Organizational structure justified for context
- Compliance roadmap specific to organization's regulatory environment
- Implementation roadmap has realistic timelines and resources
- Professional quality (could be presented to executives)

**Red Flags:**
- Generic recommendations not tailored to organization
- Missing parts (incomplete framework)
- No integration of prior exercises
- Unrealistic implementation timeline (e.g., "implement full governance in 2 weeks")

---

## Key Messages to Emphasize

1. "Compliance is cross-functional - requires technical, operational, legal, and governance coordination"
2. "Autonomy should match risk, not technical capability"
3. "Accountable role must always be human - you can't make an AI accountable"

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial instructor guide for Session 2 | [Instructor Name] |
