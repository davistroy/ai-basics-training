# **INSTRUCTOR GUIDE: ADVANCED MODULE 6, SESSION 1**
## **Cloud AI Architecture Patterns**

**Module:** Advanced Module 6: Enterprise AI Architecture
**Session:** 1 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

---

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Cloud platform comparison, deployment patterns, security architecture, and platform selection frameworks |
| **Difficulty Level** | High - Advanced module requiring Block 3 completion |
| **Prep Time Required** | 45 minutes |
| **Demo Required** | Yes - Weighted scoring model walkthrough |
| **Tech Setup Needed** | Spreadsheet/template for weighted scoring demo, screen sharing capability |
| **Common Challenges** | Participants may lack cloud platform experience; abstract architecture concepts need concrete examples |

---

## Navigation

**Module Navigation:** Session 1 | [Session 2 Instructor Guide →](../session-2/instructor-guide.md)

**Related Materials:**
- [Session 1 Presentation Slides](presentation.md)
- [Session 1 Participant Guide](participant-guide.md)
- [Module 6 Main Document](../module-6-enterprise-architecture.md)

---

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Session 1 materials and appendices | ☐ |
| Test demo | Run through weighted scoring demo with sample scenario | ☐ |
| Check resources | Verify platform documentation links are current | ☐ |
| Prepare backup | Create screenshots of weighted scoring in case live demo fails | ☐ |
| Review prerequisites | Confirm participants have Block 3 certification and cloud platform access | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice transitions and key points | ☐ |
| Prepare materials | Have weighted scoring template ready to share | ☐ |
| Check participant readiness | Verify who has completed Block 3 | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, scoring template, platform documentation | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Brief chat, answer quick questions | ☐ |
| Start recording | If session is recorded | ☐ |

---

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, preview, objectives | Keep brisk, no long introductions |
| 0:03 | 12 min | Segment 1 | Cloud AI Platform Landscape | Include 4-5 min weighted scoring demo |
| 0:15 | 12 min | Segment 2 | Deployment Architecture Patterns | Show all three patterns clearly |
| 0:27 | 12 min | Segment 3 | Security Architecture Fundamentals | Emphasize AI-specific controls |
| 0:39 | 9 min | Segment 4 | Platform Selection Framework | Connect back to Segment 1 demo |
| 0:48 | 3 min | Closing | Homework, resources, preview | Don't skip - critical for exercise setup |
| **Total** | **51 min** | | | Includes 6 min buffer |

### Timing Flexibility

**If Running Behind:**
- Segment 2: Skip deep dive into one architecture pattern, reference in participant guide
- Segment 3: Abbreviate secrets management section
- Segment 4: Shorten red flags discussion

**If Running Ahead:**
- Segment 1: Add discussion of regional availability nuances
- Segment 2: Discuss hybrid architecture patterns combining multiple patterns
- Segment 3: Add compliance mapping examples (SOC 2, HIPAA)
- More Q&A time

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | If behind, abbreviate multi-cloud discussion |
| End Segment 2 | 0:27 | If behind, simplify Pattern 3 explanation |
| Start Closing | 0:48 | Must start by here - homework overview is essential |

---

## Session Delivery Guide

### Opening (3 minutes)

**Slides 1-3: Title, Overview, Learning Objectives**

**Key Actions:**
1. Welcome participants to Advanced Module 6
2. Set context: from building agents to deploying at enterprise scale
3. Preview today's four objectives
4. Create energy around real-world consulting relevance

**Opening Script:**
> "Welcome to Advanced Module 6: Enterprise AI Architecture. You've all completed Block 3, which means you can build working AI agents. Now we're tackling the next challenge: how do you take that agent from prototype to production, serving thousands of users in an enterprise environment?
>
> Over the next 45 minutes, we're covering four critical skills: comparing cloud platforms, designing deployment architectures, securing AI systems, and building platform selection frameworks. These are the questions your clients are asking right now.
>
> Let's dive in."

**Engagement Opportunity:**
> "Quick show of hands: How many have been asked by a client or your organization which cloud AI platform to use?"

[Expect most hands - this validates the topic's relevance]

---

### Segment 1: Cloud AI Platform Landscape (12 minutes)

**Learning Objective:** Evaluate and compare major cloud AI platforms

**Slides:** 4-8

#### Content Delivery

**Key Point 1: Platform Comparison Table (Slide 5)**
- Main message: Model availability is often the first decision filter
- Example to use: "If client needs GPT-4, Azure OpenAI is the only option - decision made"
- Common misconception: "All platforms offer the same models" - they don't

**Key Point 2: Platform Selection Factors (Slide 6)**
- Main message: Six factors must be weighted based on client priorities
- Demonstration: Show how existing infrastructure changes the math
- Participant relevance: They'll use this framework in client engagements

**Key Point 3: Weighted Scoring Demo (Slide 7)**
- Main message: Structured scoring removes bias and documents rationale
- Practice preview: Exercise 1.1 applies this exact framework

#### Demo Instructions

**Demo Duration:** 4-5 minutes

**Setup Required:**
- Weighted scoring template (spreadsheet or slide)
- Sample client scenario: Healthcare org, Azure shop, needs GPT-4, HIPAA-compliant
- Pre-calculated scores ready if live calculation fails

**Demo Steps:**
1. Present client scenario - read requirements aloud
2. Show empty scoring template
3. Fill in scores for each platform on each factor (AWS Bedrock, Azure OpenAI, Vertex AI)
4. Apply weights and calculate weighted totals
5. Show final recommendation with Azure scoring highest

**Demo Talking Points:**
> "Let's score model availability. Azure gets 10/10 because our client specifically needs GPT-4. Bedrock and Vertex don't have GPT-4, so they score 2/10.
>
> Existing integration - client is already on Azure. Azure scores 10/10. AWS and GCP score 3/10 because migration is expensive.
>
> Watch how the weights amplify differences. Model availability is 25% weight, so Azure's advantage here is significant..."

**Backup Plan:**
If demo fails:
1. Switch to pre-filled screenshot showing completed scoring
2. Walk through the logic conceptually without live filling
3. Reference complete template in participant guide

#### Facilitation Notes

**Watch For:**
- Participants getting hung up on specific scores ("Why 7 and not 8?")
  - Response: "The exact number matters less than documenting your rationale"
- Questions about pricing - this comes in Exercise 1.3
  - Response: "We'll get detailed on cost modeling in Exercise 1.3"

**If Asked About "What if they need both GPT-4 and Claude?":**
> "Great question - that's where multi-cloud comes in. But you pay with operational complexity. Need strong justification for multi-cloud AI."

**Transition to Segment 2:**
> "We've selected a platform. Now: how do we actually deploy the agent?"

---

### Segment 2: Deployment Architecture Patterns (12 minutes)

**Learning Objective:** Design deployment architecture patterns

**Slides:** 9-13

#### Content Delivery

**Key Point 1: Serverless Pattern (Slide 10)**
- Main message: Best for variable workloads, but watch for cold starts
- Visual to emphasize: Architecture diagram showing Lambda → AI API flow
- Real-world application: "Client has 100 users at 9 AM, 10,000 at 2 PM - serverless scales automatically"

**Key Point 2: Containerized Pattern (Slide 11)**
- Main message: Consistent performance, no cold starts, higher baseline cost
- Visual to emphasize: Kubernetes cluster with multiple agent pods
- Trade-off highlight: "You're paying for pods 24/7 vs. serverless pay-per-use"

**Key Point 3: Queue-Based Pattern (Slide 12)**
- Main message: Perfect for async batch processing, not for real-time
- Hands-on reference: "You'll design security for one of these patterns in Exercise 1.2"
- Use case example: "Document processing - user uploads 1000 PDFs, gets results in 30 minutes"

#### Interactive Element

**Activity Type:** Quick poll or show of hands

**Activity Duration:** 1 minute

**Instructions:**
1. Ask: "Which pattern would you use for a customer service chatbot that needs sub-2-second response times?"
2. Wait for responses
3. Answer: "Containerized - consistent low latency, no cold starts"

**Debrief Points:**
> "Exactly - chatbot users won't tolerate 5-second cold start delays. That rules out serverless for this use case. Latency requirements often decide your pattern."

#### Facilitation Notes

**Energy Check:**
At this point in the session (15-27 min), participants may be:
- Information overload from architectural detail
- Recommended adjustment: Use concrete examples, less abstract theory

**Common Confusion Point:**
"Can I combine patterns?" (e.g., serverless + queue-based)

**Clarification Approach:**
> "Yes, absolutely. Many production systems use hybrid approaches. Serverless API layer that queues work for containerized agent workers. Start simple, add complexity as needed."

**Transition to Segment 3:**
> "We've designed the architecture. Now we need to secure it - and AI security has unique challenges."

---

### Segment 3: Security Architecture Fundamentals (12 minutes)

**Learning Objective:** Apply defense-in-depth security principles

**Slides:** 14-18

#### Content Delivery

**Key Point 1: Defense-in-Depth (Slide 15)**
- Main message: Five layers of security, compromise of one doesn't compromise system
- Framework/Pattern: Network → Identity → Application → Data → Monitoring
- Emphasis: "Layer 3 - Application - is where AI-specific controls live"

**Key Point 2: Secrets Management (Slide 16)**
- Main message: Never hard-code API keys, use vault-based or managed identity
- Example walkthrough: "Lambda assumes IAM role, no secrets to manage - best pattern"
- Common mistake: "I still see production systems with API keys in config files committed to git"

**Key Point 3: API Gateway Security (Slide 17)**
- Main message: Rate limiting prevents cost abuse and system overload
- AI-specific focus: Prompt size limits, content filtering, PII redaction
- Real-world impact: "Without rate limits, one user pasted a 100,000-token document and cost the client $500 in an hour"

#### Practical Application

**Consulting Connection:**
> "When you're designing security for a client, security teams will ask about each layer. Defense-in-depth is their language - use it. Show you've thought through network isolation, identity management, application controls, data encryption, and monitoring."

**Example Scenario:**
> "Imagine you're advising a healthcare client on AI for clinical documentation. HIPAA requires encryption at rest and in transit (Layer 4), audit logging (Layer 5), and PII redaction (Layer 3). Your architecture must show all of this."

#### Facilitation Notes

**Common Confusion Point:**
Difference between authentication (who are you?) and authorization (what can you do?)

**Clarification Approach:**
> "Authentication: API key proves you are client X. Authorization: Client X is allowed to call endpoint /analyze but not /admin."

**If Asked About "How do I prevent prompt injection?":**
> "Input validation in Layer 3. Block known injection patterns, limit special characters, sanitize inputs. There's no perfect solution yet, but defense-in-depth helps."

**Transition to Segment 4:**
> "Security architecture is complex. Platform selection is complex. You need frameworks to make these decisions systematically. That's what we're covering next."

---

### Segment 4: Platform Selection Decision Framework (9 minutes)

**Learning Objective:** Create platform selection frameworks

**Slides:** 19-22

#### Content Delivery

**Key Point 1: Why Frameworks Matter (Slide 19)**
- Main message: Clients need data-driven recommendations, not gut feel
- Value: Documents decision for CTO, security team, procurement
- Reduces political pressure and bias

**Key Point 2: Decision Tree (Slide 20)**
- Main message: Use binary filters to narrow from 3 platforms to 1-2 finalists
- Process: Existing infra → Model needs → Compliance → Team expertise
- Example: "Need GPT-4? Azure. That's a hard filter."

**Key Point 3: Weighted Scoring (Slide 21)**
- Main message: Score finalists quantitatively, document rationale for each score
- Connect back: This is what we demoed in Segment 1
- Critical emphasis: "Document WHY you scored each item. 'Azure 9/10 on integration because client has 50+ Azure resources' - that's defendable."

#### Closing This Segment

**Key Takeaway:**
> "Decision tree filters, weighted scoring compares, documentation justifies. With this three-part framework, you can walk into a client meeting and recommend a platform with data backing it up."

**Connection to Homework:**
> "Exercise 1.1 is exactly this process. You'll take a client scenario, apply the decision tree, fill in weighted scoring, and make a recommendation. This is what you'll do in real client engagements."

---

### Closing (3 minutes)

**Slides:** 23-25

**Do Not Skip This Section** - even if running behind

#### Homework Preview

**Key Actions:**
1. Overview all three exercises briefly
2. Highlight that they build on each other
3. Note total time is 75 minutes
4. Point to participant guide for detailed instructions

**Script:**
> "Your homework includes three exercises totaling about 75 minutes.
>
> Exercise 1.1 - Platform Comparison Analysis - you'll apply the decision framework we covered today to a realistic client scenario. 25 minutes.
>
> Exercise 1.2 - Security Architecture Design - you'll design a complete five-layer security architecture for an AI deployment. 30 minutes.
>
> Exercise 1.3 - Cost Modeling - you'll build a cost projection showing costs at scale and optimization strategies. 20 minutes.
>
> These build on each other. Platform selection informs architecture choice, architecture informs cost.
>
> Everything you need is in your participant guide, including complete templates."

#### Resources and Support

> "All templates are in the participant guide. Platform documentation links are current as of today - pricing and features change frequently, so verify details.
>
> If you get stuck, post in the async channel. I'll respond within 24 hours, and your peers often have good answers too."

#### Next Session Preview

> "Next session we move from architecture to operations - scaling patterns, monitoring, deployment strategies, and the module capstone project.
>
> Make sure to complete all three exercises before next session. We'll be building on the platform and architecture decisions you make today."

#### Session Close

> "Questions before we wrap up?
>
> [Wait for questions - answer 1-2 if time allows]
>
> Great session today. See you next time!"

---

## Anticipated Questions & Answers

### Conceptual Questions

**Q: "What if my client needs models from multiple providers, like GPT-4 AND Claude?"**
A: "That's when multi-cloud makes sense. But you pay with operational complexity - managing multiple platforms, different APIs, unified monitoring. You need strong justification. Usually the answer is: pick the platform with the most important model and accept limitations on others."

**Q: "How do I actually prevent prompt injection attacks?"**
A: "There's no perfect solution yet - it's an active research area. Best practices: input validation to block known patterns, output filtering to catch harmful responses, rate limiting to prevent abuse, and monitoring for anomalies. Defense-in-depth helps - if one control fails, others catch it."

**Q: "Is serverless always cheaper than containerized?"**
A: "Not always. Serverless is cheaper at low volumes and variable workloads. But at very high consistent volume, the per-request cost of serverless can exceed the fixed cost of always-on containers. Usually the break-even is somewhere around 24/7 utilization - if you're always busy, containers may be cheaper."

### Technical Questions

**Q: "What about on-premises AI? Can we run models on our own infrastructure?"**
A: "Yes - we cover hybrid and on-premises patterns in Session 2. Options include self-hosted open source models like Llama, private cloud deployments, or AI appliances. Common in regulated industries with data sovereignty requirements."

**Q: "How do I handle session state in serverless architectures?"**
A: "External state store like DynamoDB, Redis, or similar. Each Lambda invocation is stateless, so state goes in a database keyed by session ID. Multi-turn conversations load state from DB, process, save state back."

### Scope Questions

**Q: "How do I optimize costs for AI at scale?"**
A: "That's Exercise 1.3 today and we go deeper in Session 2. Preview: caching, model selection optimization, reserved capacity, prompt engineering to reduce tokens."

**Q: "What monitoring tools should I use?"**
A: "Session 2 covers observability in detail. Preview: CloudWatch/Azure Monitor/Cloud Logging for basics, Datadog/Grafana for advanced. AI-specific: track token usage, cost per request, latency P95/P99, error rates."

### Pushback/Objections

**Q: "This seems like a lot of complexity. Do we really need all this for AI?"**
A: "I understand - it is complex. But enterprise AI without proper architecture, security, and cost controls fails. I've seen projects blocked by security teams, surprise cost overruns, and systems that can't scale. The complexity is managing real risks. Start simple - serverless pattern, basic security - then add as you learn."

**Q: "Our team doesn't have Kubernetes expertise. Can we still do containerized deployments?"**
A: "Yes, using managed Kubernetes services like EKS, AKS, or GKE reduces operational burden. But Kubernetes has a learning curve. If your team isn't ready, start with serverless - it's simpler operationally. You can always migrate to containers later as you scale."

---

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| Screen share fails | Restart share, switch to application share | Have participant share their screen with questions |
| Weighted scoring demo breaks | Switch to pre-filled screenshot | Walk through conceptually, reference template |
| Audio issues | Ask participants to type questions in chat | Continue with video only, post transcript |
| Slides won't advance | Use keyboard shortcuts (arrow keys) | Open backup copy in new window |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Lack of cloud experience | Questions about basic cloud concepts | Acknowledge gap, point to cloud fundamentals resources, focus on patterns not platform specifics |
| Confusion about architecture patterns | "I don't understand when to use each pattern" | Use decision heuristic: variable load→serverless, consistent latency→container, batch→queue |
| Overwhelmed by security layers | Silence, looks of confusion | Simplify to "security at every layer - if one fails, others protect you" |
| Falling behind prerequisites | "I haven't completed Block 3" | Offer to catch up async, encourage completion before Session 2 |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Content too technical | Many basic questions, confusion | Add more concrete examples, reduce jargon |
| Content too basic | "We know this already" | Add advanced examples, discuss edge cases |
| Off-topic tangent | Discussion drifting to specific platform features | "Great discussion - let's stay focused on selection frameworks. Platform details in exercises." |
| Time pressure | Running 5+ min behind | Skip multi-cloud discussion, abbreviate red flags section |

---

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save chat questions | For follow-up or FAQ updates |
| Note what worked/didn't | Quick mental notes or voice memo |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | ☐ |
| Answer pending questions in async channel | ☐ |
| Send follow-up message with exercise reminders | ☐ |
| Update platform comparison table if any pricing/features changed | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions (spot check 3-5 participants) | ☐ |
| Identify participants needing support | ☐ |
| Prepare clarifications for common issues in Session 2 | ☐ |
| Update this instructor guide with lessons learned | ☐ |

---

## Participant Progress Tracking

### Expected Deliverables This Session

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 1.1 | `platform-comparison-analysis.md` | Participant's working directory |
| 1.2 | `security-architecture-design.md` | Participant's working directory |
| 1.3 | `cost-model.md` | Participant's working directory |

### Progress Check Approach

**How to Verify Completion:**
- Check for file creation and substantive content (not just templates)
- Look for specific weighted scores in 1.1, security controls in 1.2, cost projections in 1.3
- Red flags: Empty templates, placeholder text not replaced, missing sections

**Quality Indicators:**
- Exercise 1.1: Weighted scoring shows clear winner with documented rationale
- Exercise 1.2: All five security layers addressed with specific controls
- Exercise 1.3: Cost projections include scaling scenarios and optimization strategies

**Intervention Thresholds:**
- 1 exercise incomplete: Monitor, may be time constraints
- 2+ exercises incomplete: Reach out privately, offer support
- Exercises completed but low quality: Provide specific feedback before Session 2

---

## Session-Specific Notes

### What Makes This Session Unique

This is an advanced module focused on enterprise architecture - different from Block 1-3's hands-on prompting and agent building:

- Participants need enterprise context - not all have worked with large-scale systems
- Abstract architecture concepts need concrete grounding
- Platform comparison requires current knowledge - pricing and features change frequently
- Security discussion can get overwhelming - keep it practical

### Dependencies

**Builds On:**
- Block 3: Working knowledge of AI agents and their components
- General understanding of cloud concepts (VPC, API Gateway, etc.)
- Familiarity with authentication/authorization concepts

**Sets Up:**
- Session 2: Operations, scaling, monitoring, deployment strategy
- Module capstone: Enterprise Architecture Proposal builds on platform selection and security design from this session

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Platform pricing changes frequently | Verify current pricing before session, note that examples may be outdated | Active - ongoing |
| Participants may lack cloud platform hands-on experience | Focus on patterns and frameworks, not platform specifics | Active - by design |
| Weighted scoring can feel subjective | Emphasize that process is objective, documentation is key | Active - address in demo |

---

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- "Which platform would you recommend for a client that specifically needs GPT-4?" (Answer: Azure OpenAI)
- "What deployment pattern for variable workload and cost focus?" (Answer: Serverless)
- Observable behavior indicating understanding: Participants asking clarifying questions about specific scenarios

**Observable Behavior Indicating Confusion:**
- Silence when asked questions
- Questions about basic concepts (e.g., "What's a VPC?")
- Confused expressions during architecture diagrams

### Summative Assessment (End of Session)

**Exercise Quality Indicators:**
- Exercise 1.1: Look for complete weighted scoring with documented rationale for each score
- Exercise 1.2: Look for all five security layers addressed with specific implementation details
- Exercise 1.3: Look for realistic cost projections with scaling scenarios and optimization strategies

**Common Issues to Flag:**
- Exercise 1.1: Scores without rationale, missing platforms, incomplete comparison
- Exercise 1.2: Missing security layers, generic controls without AI-specific considerations
- Exercise 1.3: Unrealistic cost projections, missing scaling scenarios

### Connecting to Capstone

**Capstone Relevance:**
The module capstone is an Enterprise AI Architecture Proposal. This session's work feeds directly into capstone sections:

- Exercise 1.1 → Platform Recommendation section
- Exercise 1.2 → Security Architecture section
- Exercise 1.3 → Cost Analysis section

Participants can reuse and expand their session exercises for the capstone.

---

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Quick pulse check in async channel: "What was most valuable? What was confusing?"
- Monitor exercise completion rates and quality
- Note questions that come up repeatedly

### Improvement Log

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| | | | |

---

## Quick Reference Cards

### Key Messages to Emphasize

1. "Platform selection requires structured evaluation using multiple weighted factors"
2. "Choose deployment pattern based on workload characteristics, not on what's 'best'"
3. "AI systems need defense-in-depth with AI-specific controls at the application layer"
4. "Document your rationale - that's what makes recommendations defendable"

### If You Only Have Time For One Thing

The weighted scoring framework for platform selection. This is the most immediately applicable skill participants can use in client engagements.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| Defense-in-depth | "Like a castle: moat, walls, guards, vaults - if attackers breach the walls, guards still protect you" | Explaining security layers |
| Platform selection | "Like choosing a phone: Android vs iPhone depends on your ecosystem, needs, and preferences - no universal 'best'" | Explaining why there's no single right answer |
| Serverless vs containers | "Serverless: pay for what you use, like renting a car. Containers: fixed cost, like owning a car" | Explaining cost trade-offs |

---

**Version History:**

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial instructor guide created | [Instructor] |
