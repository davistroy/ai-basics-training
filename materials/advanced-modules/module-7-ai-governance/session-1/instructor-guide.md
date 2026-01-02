# **INSTRUCTOR GUIDE: ADVANCED MODULE 7 SESSION 1**
## **AI Governance Frameworks**

**Module:** Advanced Module 7: Enterprise AI Governance
**Session:** 1 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | AI governance frameworks (NIST, ISO), responsible AI principles, agent lifecycle governance, data governance pillars |
| **Difficulty Level** | High - Enterprise governance concepts requiring maturity |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | No - Concept and framework-focused session |
| **Tech Setup Needed** | Presentation slides, screen share capability, optional: sample governance documents to reference |
| **Common Challenges** | Participants may lack enterprise governance context; concepts can seem abstract without real-world grounding |

---

## Navigation

**Module Navigation:** Session 1 | [Session 2 Instructor Guide →](../session-2/instructor-guide.md)

**Related Materials:**
- [Session 1 Presentation Slides](presentation.md)
- [Session 1 Participant Guide](participant-guide.md)
- [Module 7 Main Document](../module-7-ai-governance.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Session 1 materials including main module doc | ☐ |
| Review frameworks | Refresh on NIST AI RMF and ISO 42001 from official sources | ☐ |
| Prepare examples | Identify 2-3 real-world governance examples from news/experience | ☐ |
| Check resources | Verify all links to NIST, ISO, EU AI Act resources work | ☐ |
| Review participant background | Understand if participants have Block 3 background or compliance roles | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and practice key transitions | ☐ |
| Review timing | Practice segment transitions - this session is framework-dense | ☐ |
| Prepare real examples | Have 1-2 governance failure examples ready (bias incidents, compliance failures) | ☐ |
| Review exercise templates | Familiarize yourself with the three exercise templates participants will use | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all materials | Presentation, NIST framework diagram, ISO reference | ☐ |
| Test share | Verify screen sharing works clearly | ☐ |
| Welcome early arrivals | Gauge participant background - consulting vs. internal roles | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, module context, preview | Set enterprise tone |
| 0:03 | 12 min | Segment 1 | AI Risk Frameworks (NIST, ISO) | Most framework-dense segment |
| 0:15 | 12 min | Segment 2 | Responsible AI Principles | Move from theory to practice |
| 0:27 | 12 min | Segment 3 | Agent Lifecycle Governance | Connect to Block 3 experience |
| 0:39 | 9 min | Segment 4 | Data Governance for AI | Shorter but critical segment |
| 0:48 | 3 min | Closing | Homework overview, resources, preview | Must complete by 0:51 |
| **Total** | **51 min** | | **(includes 6-min buffer)** | Aim for 45-48 min |

### Timing Flexibility

**If Running Behind:**
- Segment 1: Condense ISO 42001 slide to 2 minutes instead of 4 (reference in participant guide)
- Segment 2: Skip principle trade-offs slide detail, just emphasize documentation point
- Segment 3: Shorten stage-specific governance detail slide to high-level overview
- Segment 4: Condense data governance requirements detail slide

**If Running Ahead:**
- Add real-world governance failure example in Segment 1 opening
- Expand principle trade-offs discussion with participant poll
- Include additional lifecycle governance example (e.g., agent retirement case study)
- Take additional Q&A time

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | Skip ISO 42001 detail if behind; keep NIST complete |
| End Segment 2 | 0:27 | Principles trade-offs optional; keep core 6 principles complete |
| Start Closing | 0:45 | Must start by 0:45 to ensure homework preview completes |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slides 1-3: Title, Overview, Learning Objectives**

**Key Actions:**
1. Welcome participants with enterprise-appropriate tone
2. Establish credibility - this is advanced governance content
3. Connect to Block 3 for those who completed it
4. Preview the practical deliverables they'll create

**Opening Script:**
> "Welcome to Advanced Module 7: Enterprise AI Governance, Session 1. Over the next two sessions, you're going to build something very practical - a complete enterprise AI governance framework that you can use with clients or in your own organization.
>
> This module assumes you understand AI agents - their capabilities, limitations, and risks. If you completed Block 3, you've built multi-agent systems. Now we're governing them at enterprise scale.
>
> By the end of today's session, you'll have three framework-based deliverables: a governance maturity assessment, a responsible AI principles mapping, and an agent risk register. These aren't academic exercises - they're client-ready documents."

**Engagement Opportunity:**
> "Quick poll: How many of you work with organizations that have formal AI governance frameworks in place? [pause for responses] And how many work with organizations that need governance but don't have it yet? [usually more hands]
>
> That second group is why you're here. You're going to build what they need."

**Facilitation Notes:**
- Participants may have varied backgrounds - some compliance professionals, some consulting generalists
- Establish that this is practical, not theoretical
- Reference real governance challenges if participants share in opening poll

---

### Segment 1: AI Risk Frameworks Deep Dive (12 minutes)

**Learning Objective:** Apply NIST AI RMF and ISO 42001 frameworks to organizational contexts

**Slides:** 4-7

#### Content Delivery

**Slide 4: The Governance Challenge**

**Main message:** Organizations deploy AI without governance, creating unmanaged risk
**Example to use:** Recent AI bias incident or compliance failure (e.g., hiring AI bias lawsuit, GDPR penalties)
**Common misconception:** "We don't need formal governance for internal AI tools" - FALSE, risk exists regardless of user type

**Slide 5: NIST AI RMF**

**Main message:** NIST provides the standard risk framework for AI governance - four functions: Govern, Map, Measure, Manage
**Demonstration:** Walk through the four functions with concrete examples:
- GOVERN: "You create an AI Acceptable Use Policy and assign a Chief AI Officer"
- MAP: "You categorize your loan approval AI as High Risk"
- MEASURE: "You conduct bias testing and find 15% approval rate disparity"
- MANAGE: "You implement human review for borderline cases and monitor weekly"
**Participant relevance:** This framework is referenced in procurement RFPs, regulatory guidance, and audit requirements

**Slide 6: NIST Functions in Detail**

**Main message:** Each function has specific activities that translate to governance work products
**Key point:** Risk classification (in MAP function) drives everything else - spend time here
**Practice preview:** Exercise 1.1 assesses maturity across all four functions

**Slide 7: ISO 42001**

**Main message:** ISO 42001 provides certification pathway for AI management systems
**Demonstration:** Explain when certification matters - procurement requirements, regulatory demonstration
**Comparison with NIST:** ISO is broader management system; NIST is more risk-focused. Many use both.

#### Facilitation Notes

**Watch For:**
- Glazed looks during framework detail - this is dense content
- Questions about "do we really need this" - address with regulatory/risk examples
- Participants trying to take detailed notes - remind them it's all in participant guide

**If Asked "Which framework should we use - NIST or ISO?":**
> "Great question. They're complementary, not competing. Use NIST for risk assessment and ongoing risk management. Use ISO 42001 if you need third-party certification or want a broader management system approach. Many organizations use NIST as their risk framework and map it to ISO 42001 for certification purposes. Your capstone next week will help you decide what fits your context."

**Transition to Segment 2:**
> "NIST and ISO give you governance structure. But structure without values is just bureaucracy. That's where Responsible AI Principles come in - they're the values that shape what you govern toward."

---

### Segment 2: Responsible AI Principles (12 minutes)

**Learning Objective:** Operationalize responsible AI principles with concrete controls

**Slides:** 8-11

#### Content Delivery

**Slide 8: From Principles to Practice**

**Main message:** Organizations adopt principles but fail to implement them - this creates the "governance theater" problem
**Example:** "Company website says 'We're committed to AI fairness' but they have no fairness testing process"
**Emotional hook:** Regulatory enforcement is moving beyond principles to requiring demonstrable controls

**Slide 9: Six Core Principles**

**Main message:** Six principles form the foundation - Fairness, Transparency, Accountability, Privacy, Safety, Human Oversight
**Visual to emphasize:** The table with Implementation Focus column - this is the shift from aspiration to operation
**Key teaching point:** Notice every principle has concrete implementation focus - bias testing, RACI matrices, kill switches

**Slide 10: Operationalizing Principles - Fairness Example**

**Main message:** "Fairness" becomes actionable through metrics like demographic parity ratio and disparate impact
**Hands-on reference:** This is exactly what participants do in Exercise 1.2 - for ALL six principles
**Real-world application:** NYC Local Law 144 requires these specific fairness metrics for employment AI

**Interactive opportunity:**
> "Show of hands - how many have heard of 'disparate impact ratio'? [usually few] This is the 80% rule in employment law. If your AI selects candidates at a rate less than 80% of the rate for another group, that's potential discrimination. This isn't academic - it's legally required testing."

**Slide 11: Principle Trade-offs**

**Main message:** Principles sometimes conflict - document trade-off decisions with rationale
**Example:** "Your IP lawyer says 'don't explain the algorithm.' Your ethics board says 'be transparent.' You can't do both perfectly. So you document the trade-off."
**Critical point:** Regulators expect trade-offs - they don't expect undocumented, unconscious ones

#### Facilitation Notes

**Energy Check:**
At this point (25-30 minutes in), participants may be experiencing information overload.
**Recommended adjustment:** Use more concrete examples, fewer abstract concepts. Ground each principle in a real scenario.

**Common Confusion Point:**
"How do you measure fairness objectively when fairness is subjective?"
**Clarification Approach:**
> "Excellent question. You're right that fairness has subjective elements - different stakeholders may disagree on what's fair. That's why you define fairness *for your specific context* at the start. For a loan AI, you might define fairness as 'equal opportunity for qualified applicants.' Then you measure that with objective metrics. The subjective decision is which definition of fairness applies. The measurement is objective."

**Transition to Segment 3:**
> "We've covered the principles that guide governance. Now let's look at *when* governance happens - across the entire AI agent lifecycle."

---

### Segment 3: Agent Governance Lifecycle (12 minutes)

**Learning Objective:** Design agent lifecycle governance with appropriate approval gates

**Slides:** 12-15

#### Content Delivery

**Slide 12: Agent Lifecycle Governance**

**Main message:** Governance spans six stages from Design through Retire - not just deployment approval
**Framework/Pattern:** The lifecycle circle showing Design → Develop → Test → Deploy → Monitor → Retire
**Key teaching point:** Most organizations do deployment approval well but fail at ongoing monitoring and retirement

**Slide 13: Stage-Specific Governance Requirements**

**Main message:** Each lifecycle stage has specific governance controls - risk classification drives control intensity
**Hands-on reference:** Risk classification (Low/Medium/High/Critical) appears in Exercise 1.3
**Important detail:** "Bias and fairness testing required for people-impacting decisions" - emphasize this is non-negotiable for hiring, lending, insurance, healthcare AI

**Slide 14: Governance Gates and Approval Matrix**

**Main message:** Approval requirements scale with risk - not all AI needs board approval, but critical-risk AI does
**Example walkthrough:**
- "Internal FAQ chatbot? Team Lead approval, 2-day timeline."
- "Loan approval AI? Executive + Legal + Ethics Board, 4-week timeline."
**Critical concept:** Risk classification based on four criteria: Impact, Reversibility, Scope, Regulatory Context

**Interactive element:**
> "Let's classify a real example together. Medical diagnosis AI that recommends treatment plans to doctors. What's the risk level? [Take responses]
>
> Impact - if it's wrong, patient harm. HIGH.
> Reversibility - doctors review, so somewhat reversible. MEDIUM.
> Scope - could affect thousands of patients. HIGH.
> Regulatory context - healthcare AI is heavily regulated. HIGH.
>
> This is Critical risk. Board approval, quarterly review, extensive testing. Agreement?"

**Slide 15: Lifecycle Governance Summary**

**Key takeaway:** Governance is continuous, risk-based, documented, and includes retirement planning
**Connection to homework:** Exercise 1.3 risk register identifies risks at each lifecycle stage

#### Facilitation Notes

**Common Pitfall:**
Participants want simple rules: "Just tell us what risk level each type of AI is."
**Response:**
> "I understand the desire for a lookup table, but risk classification requires judgment. The same type of AI can be different risk levels in different contexts. A chatbot for customer service is low risk. A chatbot providing medical advice is high risk. Your governance board sets the classification criteria, and product teams apply them with governance review."

**For Block 3 Graduates:**
> "Those of you who completed Block 3 built autonomous agents. Think about the agents you built - where would they fall in the approval matrix? What lifecycle governance did you *actually* implement vs. what you *should have* implemented? That gap is what we're addressing."

**Transition to Segment 4:**
> "Lifecycle governance gives you the 'when' and 'who' of governance. But AI is fundamentally data-driven. Without data governance, everything else falls apart. Let's look at the four data governance pillars."

---

### Segment 4: Data Governance for AI (9 minutes)

**Learning Objective:** Understand data governance pillars (lineage, quality, privacy, access)

**Slides:** 16-18

#### Content Delivery

**Slide 16: Data Governance Pillars**

**Main message:** AI governance fails without data governance - four pillars: Lineage, Quality, Privacy, Access
**Critical teaching point:** "Bias in AI almost always traces to bias in training data"
**Real-world relevance:** GDPR Article 22 on automated decision-making requires data governance documentation

**Slide 17: Data Governance Requirements Detail**

**Main message:** Each pillar has specific requirements that translate to controls and documentation
**Key details:**
- Lineage: "Can you prove you have rights to use this data for AI training?"
- Quality: "Bias assessment in training data using statistical tests for protected attributes"
- Privacy: "Data subject rights - access, deletion, correction, portability"
- Access: "Role-based controls - data scientists vs. production users have different access"

**Slide 18: Data Governance Summary**

**Key takeaway:** Quality over quantity for data; privacy by design; document lineage
**Connection to exercises:** All three exercises touch data governance - assessment, privacy principle mapping, data-related risks

#### Facilitation Notes

**Watch For:**
This segment is short (9 min) but critical. Don't rush through it.
**Timing strategy:** If running long overall, this segment can absorb 2-3 minutes from buffer time

**Common Question:**
"What if our organization doesn't have good data governance yet?"
**Response:**
> "That's very common, and it's actually the biggest barrier to good AI governance. You have two paths: First, advocate for enterprise data governance improvement - this benefits all data use, not just AI. Second, implement AI-specific data governance in parallel - you can't wait for perfect enterprise data governance. Exercise 1.1 helps you assess the gap and Exercise 1.3 identifies data-related risks."

**Emphasis Point:**
> "Remember: You can have perfect AI governance processes and still fail if your data is biased, improperly sourced, or privacy-violating. Data governance is foundational."

#### Closing This Segment

**Key Takeaway:**
> "If you only remember one thing from Segment 4: Test your training data for bias, not just your model outputs. By the time bias shows up in outputs, it's baked in. Catch it at the data stage."

**Connection to Homework:**
> "Exercise 1.2 asks you to map the Privacy principle, which is fundamentally about data governance. Exercise 1.3 includes data privacy violation as one of the risk scenarios. You'll practice data governance thinking in both."

---

### Closing (3 minutes)

**Slides:** 19-21

**Do Not Skip This Section** - even if running behind

#### Homework Preview

**Key Actions:**
1. Overview all three exercises with time estimates
2. Emphasize that deliverables are client-ready documents
3. Point to templates in each exercise
4. Note that exercises build on each other

**Script:**
> "Your homework includes three exercises totaling 75 minutes.
>
> Exercise 1.1 - Governance Maturity Assessment - 25 minutes. You'll assess an organization across seven domains, score maturity levels, identify gaps, and create prioritized recommendations. This is a complete assessment you can use with clients.
>
> Exercise 1.2 - Responsible AI Mapping - 25 minutes. You'll take the six principles and map them to a specific AI system, defining controls, metrics, and trade-offs. This operationalizes abstract principles.
>
> Exercise 1.3 - Agent Risk Register - 25 minutes. You'll create a risk register with likelihood and impact scoring, current controls, and treatment plans. This is your governance roadmap.
>
> Everything you need is in your participant guide, including complete templates you can copy and adapt. These aren't toy templates - they're based on real governance frameworks used in consulting."

#### Resources and Support

> "All the templates are in the participant guide. Reference materials include links to NIST AI RMF, ISO 42001, and EU AI Act resources.
>
> If you get stuck, post in [support channel]. I check it daily. Your peers are also active there and often have great insights."

#### Next Week Preview

> "Next week, Session 2, we cover implementation and compliance. You'll learn regulatory requirements like EU AI Act, organizational structures for governance, agent autonomy classification, and audit trails.
>
> The Session 2 capstone brings everything together - you'll create a complete Enterprise AI Governance Framework that combines your Session 1 deliverables with Session 2 material into a comprehensive, client-ready framework.
>
> To be ready for that capstone, complete all three of this week's exercises. They're the foundation."

#### Session Close

> "Questions before we wrap? [Pause for questions]
>
> This was a framework-heavy session - NIST, ISO, principles, lifecycle, data governance. But these frameworks aren't academic - they're what regulators reference, what procurement requires, and what protects organizations from AI incidents.
>
> Your exercises make it practical. See you next week!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Is NIST AI RMF mandatory or voluntary?**
A: Voluntary for most organizations, but increasingly referenced in regulations and procurement. Federal contractors may face NIST requirements. Even if not mandatory, it's the de facto standard - easier to adopt than create your own framework.

**Q: How do we decide which responsible AI principles to adopt - are these six universal?**
A: These six appear in most frameworks, but some organizations add others like Reliability, Security, or Sustainability. Start with these six - they cover the core regulatory and ethical concerns. You can always add more.

**Q: What if our organization has zero governance today - where do we start?**
A: Start with Exercise 1.1 - the maturity assessment. That tells you where you are and identifies quick wins. Then focus on three things: (1) AI inventory - know what AI you have, (2) Risk classification - categorize AI by risk level, (3) Basic policies - document minimum requirements. You can build from there.

### Technical Questions

**Q: What tools exist for bias testing and fairness metrics?**
A: Several options: Fairlearn (Microsoft), AI Fairness 360 (IBM), What-If Tool (Google), Aequitas. These provide statistical tests for common fairness metrics. But remember - tools measure, humans decide what's fair.

**Q: How do you monitor agent drift in production?**
A: Two types of drift to monitor: (1) Data drift - your input data distribution changes, (2) Concept drift - the relationship between inputs and outputs changes. Tools like Evidently AI, NannyML, or custom monitoring can detect drift. Set baseline metrics at deployment and alert when deviation exceeds thresholds.

### Scope Questions

**Q: Do these governance frameworks apply to simple AI like spam filters or recommendation systems?**
A: Yes, but with proportional governance. A spam filter is low-risk, so governance is light - basic documentation, periodic review. A recommendation system that influences purchasing might be medium-risk - more testing, closer monitoring. Risk-based approach means governance intensity matches actual risk.

**Q: What about AI we procure from vendors vs. build ourselves - same governance?**
A: Same governance outcomes required, different implementation. For vendor AI, your governance focuses on: (1) Vendor due diligence - do they have governance? (2) Contractual requirements - SLAs, audit rights, (3) Output monitoring - is their AI performing as expected? You may not control their development process, but you control deployment and ongoing oversight.

### Pushback/Objections

**Q: This seems like a lot of overhead that will slow down AI innovation.**
A: I hear that concern often. Here's the reality: ungoverned AI creates incidents, which create emergency responses, which stop innovation completely. Proper governance prevents incidents, which allows sustainable innovation. The organizations that move fastest long-term are those with strong governance. Short-term, yes, there's setup cost. Long-term, governance accelerates innovation by reducing rework and incident response.

**Q: Can't we just add governance later, after we prove the AI works?**
A: That's like saying "build the building first, add the foundation later." Some governance must be built in from the start - data provenance, bias testing, privacy controls. Retrofitting is expensive and often incomplete. You don't need perfect governance from day one, but you need minimum viable governance: risk classification, basic testing, and approval gates.

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Screen share fails | Restart share, switch to application share | Describe slides verbally, share presentation file in chat |
| Slides won't advance | Use keyboard shortcuts, restart presentation | Open backup PDF version |
| Audio issues | Ask participants to type questions | Continue with video only, post recording after |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Framework overload | "This is too theoretical" | Ground in concrete examples; reference real governance failures; emphasize practical deliverables |
| Lack of enterprise context | Confused questions about roles like Chief AI Officer | Explain organizational structures; provide smaller-scale alternatives |
| Skepticism about necessity | "Do we really need all this for our simple AI?" | Use regulatory examples; emphasize risk-based approach allows proportional governance |
| Paralysis about where to start | "This seems overwhelming" | Point to maturity assessment as starting point; emphasize incremental improvement |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Content too abstract | Many questions seeking concrete examples | Add real-world governance failure stories; reference specific regulations |
| Content too basic | "We already do this" | Good - then the maturity assessment will show high scores; focus on gaps and advanced topics |
| Off-topic tangent | Discussion drifting to AI ethics philosophy | "Great discussion for async channel - let's stay practical for session time" |
| Time pressure | Running 5+ minutes behind | Skip ISO 42001 detail, principle trade-offs detail; reference participant guide |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save chat questions | Copy unanswered questions for follow-up |
| Note timing issues | Did you run long/short on specific segments? |
| Document good examples | Any participant examples worth keeping for future sessions |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording | If applicable, with timestamps for key segments |
| Answer pending questions in support channel | Especially framework clarifications |
| Send follow-up with key resources | NIST link, ISO link, exercise templates |
| Document any confusion points for curriculum improvement | Were there repeated questions indicating content gaps? |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions (spot check 3-5) | Are participants interpreting exercises correctly? |
| Identify participants needing support | Who hasn't started or submitted exercises? |
| Prepare clarifications for Session 2 | Any concepts from Session 1 that need reinforcement |
| Update this instructor guide with lessons learned | What worked/didn't work in delivery? |

---

## Participant Progress Tracking

### Expected Deliverables This Week

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 1.1 | `governance-maturity-assessment.md` | Participant's working directory or shared location |
| 1.2 | `responsible-ai-mapping.md` | Participant's working directory |
| 1.3 | `agent-risk-register.md` | Participant's working directory |

### Progress Check Approach

**How to Verify Completion:**
- Check submission timestamps in shared folder or LMS
- Look for complete templates (not just partially filled)
- Verify assessment scores are calculated (Exercise 1.1)
- Check that all six principles are mapped (Exercise 1.2)
- Ensure risk register has at least 6 risks scored (Exercise 1.3)

**Red Flags Indicating Struggle:**
- Generic responses that don't reflect real organizational context
- Skipped sections (e.g., only 3 of 7 domains assessed)
- No quantitative scores or metrics (just narrative)
- Templates copied without customization

**Intervention Thresholds:**
- 1 exercise incomplete: Normal - may be time constraints
- 2+ exercises incomplete: Reach out to offer support
- All exercises incomplete 3+ days before Session 2: Required 1:1 conversation

---

## Week-Specific Notes

### What Makes This Week Unique

This is a frameworks and foundations week - heavy on conceptual frameworks (NIST, ISO) and principles. The challenge is making abstract governance concepts concrete and actionable.

**Critical concepts that need extra emphasis:**
- Risk-based governance (not one-size-fits-all)
- Operationalizing principles through metrics and controls
- Lifecycle governance (not just deployment approval)
- Data governance as foundation for AI governance

**Common failure points:**
- Participants treat frameworks as checklists rather than guidance
- Confusing principle adoption with principle operationalization
- Underestimating data governance complexity
- Trying to apply maximum governance to all AI equally

**Connections to other content:**
- Block 3 graduates built agents - now they're governing them
- Session 2 builds directly on Session 1 - maturity assessment, principles mapping, and risk register feed into the capstone
- The frameworks taught here (NIST, ISO) appear in Session 2 regulatory compliance discussion

### Dependencies

**Builds On:**
- Block 3 (or equivalent): Understanding of AI agent capabilities, limitations, and architectures
- Basic risk management concepts
- Awareness of AI regulations (at least high-level)

**Sets Up:**
- Session 2: Regulatory compliance, organizational structures, autonomy classification, audit requirements
- Module Capstone: Enterprise AI Governance Framework integrates all Session 1 and 2 content

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| NIST AI RMF is complex for those without risk management background | Provide simplified overview; emphasize practical application over framework details | Active |
| Participants may not have organizational access to complete assessments | Encourage use of hypothetical organization or public case study | Active |
| Exercise 1.2 requires understanding of AI system - some may not have one in mind | Provide example AI systems to use (chatbot, recommendation engine, approval agent) | Active |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- "Can someone explain the difference between the MAP and MEASURE functions in NIST?" (Tests comprehension)
- "What risk level would you assign to [specific AI example]?" (Tests application)
- Look for participants taking notes during framework explanations

**Observable Behavior Indicating Understanding:**
- Questions about "how do I apply this?" rather than "what is this?"
- References to their own organizational context
- Comparisons between NIST and ISO showing comprehension

**Observable Behavior Indicating Confusion:**
- Silence when asked for examples
- Questions about basic definitions covered earlier
- Note-taking everything (may indicate lack of grasp of what's important)

### Summative Assessment (End of Week)

**Exercise Quality Indicators:**

**Exercise 1.1 (Maturity Assessment):**
- Look for: Numerical scores calculated, evidence/notes provided, gap analysis specific to organization
- Red flag: All scores identical, no evidence, generic recommendations

**Exercise 1.2 (Principles Mapping):**
- Look for: Specific metrics defined (not just "measure fairness"), RACI matrix with real roles, trade-off decisions documented
- Red flag: Vague metrics, no actual stakeholder names, missing principles

**Exercise 1.3 (Risk Register):**
- Look for: Risk scores calculated (Likelihood x Impact), current controls identified, treatment plans with owners and dates
- Red flag: All risks same score, no current controls identified, vague mitigation plans

**Common Issues to Flag:**
- Treating exercises as theoretical rather than applied to real context
- Copying templates without customization
- Missing quantitative elements (scores, metrics)
- Incomplete documentation (skipped sections)

### Connecting to Capstone

**Capstone Relevance:**
The Session 2 capstone integrates all Session 1 deliverables:
- Maturity assessment becomes Part 1 of governance framework
- Principles mapping informs policy framework design
- Risk register drives risk framework and compliance roadmap
- All three feed into implementation roadmap and quick wins

**Quality Check:**
If Session 1 exercises are incomplete or low-quality, the capstone will be weak. Encourage quality completion this week.

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Optional quick pulse: "On a scale of 1-5, how well do you understand NIST AI RMF after today's session?"
- Note common questions in chat/discussion for FAQ development

**Improvement Log:**

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| | | | |
| | | | |

### Key Messages to Emphasize

1. "Governance is risk-based - match intensity to actual risk, not fear or compliance theater"
2. "Principles without operationalization are PR, not governance - define metrics and controls"
3. "AI governance fails without data governance - they're inseparable"

### If You Only Have Time For One Thing

The single most important concept: **Risk-based governance approach**

If participants understand that AI governance should match risk level (not one-size-fits-all), they can figure out the rest. Without this, they'll either under-govern high-risk AI or over-govern everything and create governance gridlock.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Governance without data governance | "Foundation without ground underneath" | When discussing data governance importance |
| Principles without metrics | "Saying 'be healthy' without defining exercise or diet" | When explaining principle operationalization |
| Lifecycle governance | "Parenting doesn't end at birth - it's continuous through childhood, adolescence, adulthood" | When explaining why monitoring matters |

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial instructor guide created for Module 7 Session 1 | [Instructor Name] |

---

**Quick Reference Card**

**Session 1 in One Page:**
- **Core frameworks:** NIST AI RMF (Govern, Map, Measure, Manage) + ISO 42001
- **Key principles:** Fairness, Transparency, Accountability, Privacy, Safety, Human Oversight
- **Critical teaching:** Operationalize principles with metrics, not just aspirations
- **Lifecycle stages:** Design → Develop → Test → Deploy → Monitor → Retire
- **Data pillars:** Lineage, Quality, Privacy, Access
- **Exercises:** Maturity assessment + Principles mapping + Risk register
- **Common pitfall:** Treating governance as one-time approval vs. continuous lifecycle
- **Next session:** Implementation, compliance, autonomy classification, audit trails
