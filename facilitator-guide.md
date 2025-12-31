# AI Practitioner Training - Facilitator Guide

## Overview

This guide supports facilitators delivering the AI Practitioner Training curriculum. It includes session preparation notes, common questions, troubleshooting tips, and timing guidance.

---

## General Facilitation Principles

### Adult Learning Approach
- Participants are professionals with existing expertise
- Connect new concepts to their consulting experience
- Respect their time—stay on schedule
- Encourage questions but manage tangents
- Focus on practical application, not theory

### Session Structure
- **Start:** Brief recap of previous week + preview of today
- **Middle:** Segment-by-segment delivery with demos
- **End:** Clear homework instructions + preview of next week
- **Buffer:** Keep 2-3 minutes for questions/overflow

### Technical Demonstrations
- Test all demos before the session
- Have backup screenshots if live demo fails
- Narrate what you're doing and why
- Pause for questions at natural breakpoints

---

## Block 1 Facilitation Notes

### Week 1: Markdown Fundamentals

**Common Questions:**
- "Why Markdown instead of just typing?" → Show before/after quality comparison
- "Do I need to memorize all syntax?" → No, reference the quick card; muscle memory builds over time

**Demo Tips:**
- Use a side-by-side view: Markdown source + rendered output
- Show the prompt injection prevention demo clearly—this is a "wow" moment

**Timing Watch:**
- Segment 3 (Markdown syntax) can run long—keep examples brief

### Week 3: JSON + GitHub

**Common Struggles:**
- JSON trailing commas cause frustration
- GitHub terminology is confusing (repo, commit, branch)

**Tips:**
- Emphasize JSONLint validation before saving
- Use GitHub's web interface for Week 3—no command line yet
- "Repository = project folder, Commit = save with a note"

### Week 5: Peer Review

**Facilitation Required:**
- Pair participants before the session
- Provide clear pairing instructions in advance
- Check that pairs have exchanged PR links

---

## Block 2 Facilitation Notes

### Week 1: Automation Platforms

**Decision Point:**
- Participants choose their platform this week
- Don't let analysis paralysis stall them
- Recommendation: Make.com for most, n8n for technical comfort

**Common Question:**
- "Which platform is best?" → There's no universal best; the matrix helps you decide based on YOUR priorities

### Weeks 5-6: MCP Integration

**Critical Sessions:**
- These weeks have the highest failure rate
- Budget extra support time
- Have troubleshooting appendix ready

**Before Week 5:**
- Remind participants to install Node.js
- Remind participants to install Claude Desktop
- Send the config file location reminder

**During Week 5:**
- Live demo should show the FULL process including restart
- Have a participant share screen and troubleshoot live (builds confidence)
- Emphasize: "One server working reliably > three servers half-working"

**Common Issues:**
- JSON syntax errors (commas!)
- Wrong config file location
- Didn't fully restart Claude
- Node.js not installed

---

## Block 3 Facilitation Notes

### Week 1: Agent Fundamentals

**Mindset Shift:**
- This is where participants transition from "building tools" to "building systems"
- The Two-Agent Pattern is the key concept—spend time on it
- Use the RFP Response Agent example extensively

**Pre-Work Check:**
- Verify participants reviewed presentation.md
- Quick poll: "What's the Daily Contractor analogy about?"

### Week 2: Building Reliable Agents

**Expectations Management:**
- First agents WILL fail
- This is expected and instructive
- "Failure is data about what to improve"

**The 3-Failure Rule:**
- This is a practical heuristic, not a rigid rule
- The point: Know when to stop and escalate

### Week 5: Orchestration

**Complexity Warning:**
- This is the densest content in the curriculum
- Focus on Sequential and Master-Worker
- Explicitly tell participants: "Parallel and Team-Based are advanced—we're covering concepts, not requiring implementation"

---

## Troubleshooting Common Issues

### GitHub Access Blocked
- Some corporate networks block GitHub
- Solution: Use personal network for exercises, or request IT exception

### AI Tool Rate Limits
- Free tiers may hit usage limits
- Solution: Spread exercises across days, or upgrade to paid tier

### MCP Won't Work
- See Appendix O in Block 2
- Common fix: Fully quit Claude Desktop (not just close window)

### Participant Falling Behind
- Check in privately after session
- Identify specific blocker
- Offer 1:1 support or paired work
- Don't let them skip to next week without core skills

---

## Assessment and Certification

### Capstone Evaluation
- Use the provided rubrics (Appendices H, J, N)
- Score each criterion independently
- Provide written feedback on strengths and improvements
- Certification threshold: 22/40 (55%)

### Borderline Cases
- If 20-21 points: Offer conditional pass with specific improvement requirements
- Document what needs to be addressed
- Re-evaluate after improvements

### Outstanding Work
- Scores of 36+ should be recognized
- Consider showcasing exceptional capstones (with permission)
- These participants may help facilitate future cohorts

---

## Session Timing Templates

### Standard 45-Minute Session
```
0:00-0:03  Welcome, recap previous week
0:03-0:13  Segment 1
0:13-0:23  Segment 2
0:23-0:33  Segment 3
0:33-0:42  Segment 4
0:42-0:45  Homework preview, questions
```

### Adjust for Demos
```
If live demo planned:
- Reduce other segments by 2-3 min each
- Demo should be 8-10 min max
- Have backup plan if demo fails
```

---

## Resources

- [Prerequisites Self-Assessment](prerequisites.md)
- [Quick Reference Cards](quick-reference/)
- [Checkpoint Assessments](checkpoints/)
- [Feedback Template](feedback/cohort-feedback-template.md)
