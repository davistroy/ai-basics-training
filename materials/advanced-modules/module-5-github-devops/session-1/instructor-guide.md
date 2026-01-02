# **INSTRUCTOR GUIDE: ADVANCED MODULE 5 SESSION 1**
## **GitHub Actions & Version Control Fundamentals**

**Module:** Advanced Module 5: Advanced GitHub & DevOps for AI Systems
**Session:** 1 of 2
**Session Duration:** 45 minutes
**Homework Duration:** 75 minutes

-----

## Quick Reference

| Element | Details |
|---------|---------|
| **Session Focus** | Building GitHub Actions workflows and version control for AI artifacts |
| **Difficulty Level** | Medium |
| **Prep Time Required** | 30 minutes |
| **Demo Required** | Yes - GitHub Actions workflow creation |
| **Tech Setup Needed** | GitHub repository, YAML editor, example prompts |
| **Common Challenges** | YAML syntax errors, understanding triggers, version manifest structure |

-----

## Navigation

**Module Navigation:** **Session 1** | [Session 2 Instructor Guide →](../session-2/instructor-guide.md)

**Related Materials:**
- [Session 1 Presentation Slides](presentation.md)
- [Session 1 Participant Guide](participant-guide.md)
- [Module 5 Main Document](../module-5-github-devops.md)

-----

## Pre-Session Preparation

### 1 Week Before

| Task | Details | Done? |
|------|---------|-------|
| Review content | Read through all Session 1 materials | ☐ |
| Test demo | Create a GitHub Actions workflow yourself | ☐ |
| Check resources | Verify GitHub repository access | ☐ |
| Prepare backup | Create screenshots of working workflow | ☐ |
| Review prerequisites | Confirm participants have Block 3 certification | ☐ |

### 1 Day Before

| Task | Details | Done? |
|------|---------|-------|
| Tech check | Test screen share, audio, video | ☐ |
| Load presentation | Have slides ready and tested | ☐ |
| Review timing | Practice transitions and key points | ☐ |
| Prepare materials | Have demo repository ready with sample prompts | ☐ |
| Check participant readiness | Verify participants have GitHub accounts | ☐ |

### 15 Minutes Before

| Task | Details | Done? |
|------|---------|-------|
| Open all tabs | Presentation, GitHub repository, Actions page | ☐ |
| Test share | Verify screen sharing works | ☐ |
| Welcome early arrivals | Brief chat, answer quick questions | ☐ |
| Start recording | If session is recorded | ☐ |

-----

## Session Timing Plan

### Detailed Timing

| Time | Duration | Section | Content | Notes |
|------|----------|---------|---------|-------|
| 0:00 | 3 min | Opening | Welcome, module intro, objectives | Set advanced tone |
| 0:03 | 12 min | Segment 1 | GitHub Actions Architecture | Include workflow demo |
| 0:15 | 12 min | Segment 2 | Version Control for AI Artifacts | Show manifest examples |
| 0:27 | 12 min | Segment 3 | Automated Testing | Show unit test examples |
| 0:39 | 3 min | Segment 4 | Quality Gates & Branch Protection | Fast-paced summary |
| 0:42 | 3 min | Closing | Homework, resources, preview | Don't skip |
| **Total** | **45 min** | | | |

### Timing Flexibility

**If Running Behind:**
- Segment 4 can be condensed to 6 minutes (reduce examples)
- Skip branch protection UI demo - reference in documentation
- Reduce Q&A time within segments

**If Running Ahead:**
- Add more GitHub Actions trigger examples
- Show real-world version manifest from production system
- Demonstrate branch protection setup in GitHub UI
- Extended Q&A on testing strategies

### Critical Timing Points

| Checkpoint | Target Time | Action If Off Track |
|------------|-------------|---------------------|
| End Segment 1 | 0:15 | Skip trigger table details, reference in guide |
| End Segment 2 | 0:27 | Shorten branch strategy discussion |
| Start Closing | 0:42 | Must start by here regardless |

-----

## Session Delivery Guide

### Opening (3 minutes)

**Slide 1: Title**

**Key Actions:**
1. Welcome participants warmly
2. Set context for advanced module (Block 3 graduates)
3. Preview the journey from basic workflows to production DevOps
4. Establish that this is hands-on, practical content

**Opening Script:**
> "Welcome to Advanced Module 5 - GitHub & DevOps for AI Systems. As Block 3 graduates, you've built autonomous agent systems. Now we're taking them production-ready. Today we're building the foundation: GitHub Actions automation and version control specifically designed for AI artifacts. By the end of our 45 minutes together, you'll be able to build automated validation pipelines that run on every commit."

**Engagement Opportunity:**
> "Quick check-in: Who's currently using any CI/CD automation for their AI workflows?"

[Wait for 1-2 hands/responses - gauge baseline knowledge]

-----

### Segment 1: GitHub Actions Architecture (12 minutes)

**Learning Objective:** Design and implement GitHub Actions workflows for AI system validation

**Slides:** 4-8

#### Content Delivery

**Key Point 1: The Problem - Manual Validation Doesn't Scale**
- Main message: Manual testing is slow, error-prone, and misses edge cases
- Example to use: "You update a customer support prompt. How do you know it won't break production?"
- Common misconception: "We can just test manually before deploying"

**Key Point 2: GitHub Actions Components**
- Main message: Workflows automate validation with triggers, jobs, and steps
- Demonstration: Show actual .github/workflows/ YAML file
- Participant relevance: Eliminates manual quality checks

**Key Point 3: Trigger Types**
- Main message: Different triggers serve different validation needs
- Practice preview: Exercise 1.1 builds a workflow with push triggers

#### Demo Instructions

**Demo Duration:** 5 minutes

**Setup Required:**
- GitHub repository with prompts/ directory
- At least one prompt markdown file
- Empty .github/workflows/ directory ready to populate

**Demo Steps:**
1. **Create workflow directory**
   - Navigate to repository root
   - Create .github/workflows/ directory
   - Say: "GitHub automatically recognizes workflows in this directory"

2. **Create validation workflow file**
   - Create prompt-validation.yml
   - Add basic YAML structure with on: push trigger
   - Say: "This trigger means the workflow runs on every push"

3. **Add validation job**
   - Define ubuntu-latest runner
   - Add checkout action
   - Add validation step (simple file check)
   - Say: "Notice how each step does one specific thing"

4. **Commit and push**
   - Commit the workflow file
   - Push to GitHub
   - Navigate to Actions tab
   - Say: "Watch it trigger automatically"

5. **Show running workflow**
   - Point out job execution
   - Show step-by-step progress
   - Highlight success/failure visibility

**Demo Talking Points:**
> "See how this workflow file defines exactly what happens on every push. GitHub reads this YAML and executes it automatically. No human intervention needed."

> "The Actions tab gives you complete visibility. You can see every workflow run, every job, every step. When something fails, you know exactly where."

**Backup Plan:**
If demo fails:
1. Switch to pre-captured screenshots showing workflow creation
2. Walk through the YAML structure conceptually
3. Show a successful workflow run from backup images
4. Offer to demonstrate 1:1 in async channel

#### Facilitation Notes

**Watch For:**
- Confusion about YAML indentation (very common)
- Questions about costs (GitHub Actions has free tier)
- Uncertainty about what to validate first

**If Asked About "What should we validate?":**
> "Start simple. File structure checks, required sections, token counts. You'll add complexity as you learn what breaks. Exercise 1.1 walks you through building your first validation."

**Transition to Segment 2:**
> "Now you know how to automate validation. But how do you track versions of your prompts and configs? That's next."

-----

### Segment 2: Version Control for AI Artifacts (12 minutes)

**Learning Objective:** Apply version control strategies for prompts and AI configurations

**Slides:** 9-12

#### Content Delivery

**Key Point 1: The Version Control Challenge**
- Main message: AI artifacts need semantic versioning beyond git commits
- Visual to emphasize: Messy git history vs. clean versioned structure slide

**Key Point 2: Semantic Versioning for Prompts**
- Main message: MAJOR.MINOR.PATCH gives meaning to version changes
- Hands-on reference: Exercise 1.2 implements this structure

**Key Point 3: Version Manifest Pattern**
- Main message: Single source of truth for version status
- Real-world application: Prevents deploying deprecated prompts

#### Interactive Element

**Activity Type:** Quick discussion

**Activity Duration:** 2 minutes

**Instructions:**
1. Ask: "What happens when you have v1.0 in production but v2.0 in staging?"
2. Collect 1-2 responses
3. Highlight the coordination challenge

**Debrief Points:**
> "Exactly - you need to know which version is deployed where. That's what the version manifest solves. It's your deployment coordination center."

#### Facilitation Notes

**Energy Check:**
At this point in the session, participants may be:
- Information-dense - lots of new concepts
- Use concrete examples to ground abstract version control ideas

**Common Confusion Point:**
"Why not just use git tags?"

**Clarification Approach:**
> "Git tags are great for marking commits, but they don't give you the semantic meaning AI artifacts need. MAJOR.MINOR.PATCH tells you immediately if it's a breaking change or a patch. Plus the manifest tracks supported vs. deprecated - git tags can't do that."

**Transition to Segment 3:**
> "Version control tracks changes over time. But how do you validate those changes automatically? Testing."

-----

### Segment 3: Automated Testing for AI Workflows (12 minutes)

**Learning Objective:** Create automated test suites for AI workflows

**Slides:** 13-17

#### Content Delivery

**Key Point 1: AI Testing Is Different**
- Main message: Can't test LLM outputs like traditional code
- Framework/Pattern: Testing pyramid adapted for AI (unit/integration/E2E)

**Key Point 2: Unit Tests for Prompts**
- Main message: Fast, focused tests for structure and constraints
- Example walkthrough: Required sections test, token count test

**Key Point 3: Integration with GitHub Actions**
- Main message: Tests run automatically on every commit
- Example: Show test job with needs: dependencies

#### Practical Application

**Consulting Connection:**
> "In consulting, your prompts are client-facing. A broken prompt means lost revenue or damaged reputation. Automated tests are insurance - they catch problems before clients see them."

**Example Scenario:**
> "Imagine you're managing customer support prompts for a major client. Someone updates a prompt and accidentally removes the 'Output Format' section. Without tests, this goes to production and the chatbot starts returning unstructured responses. With tests, the PR is blocked immediately. The developer fixes it before anyone notices."

#### Facilitation Notes

**Watch For:**
- Questions about testing non-deterministic LLM outputs
- Confusion about what's testable vs. what requires manual review

**If Asked About "How do we test actual LLM quality?":**
> "Great question. Unit and integration tests validate structure and consistency. Actual output quality requires LLM-as-Judge patterns or human review. We're not testing the LLM itself - we're testing that our prompts are well-formed and our workflows execute correctly."

**Transition to Segment 4:**
> "Tests catch errors. But how do you enforce that nothing broken reaches production? Quality gates."

-----

### Segment 4: Quality Gates and Branch Protection (3 minutes)

**Learning Objective:** Configure quality gates and branch protection rules

**Slides:** 18-21

**NOTE:** This segment is condensed to 3 minutes instead of 9 to fit timing. Move quickly but hit key points.

#### Content Delivery

**Key Message:** Quality gates + branch protection = nothing broken reaches production

**Coverage:**
- Required status checks block merges if tests fail
- Branch protection prevents direct pushes to main
- Multiple layers catch different error types

**Visual:** Show complete pipeline flow (Slide 20)

#### Closing This Segment

**Key Takeaway:**
> "If it doesn't pass all checks, it doesn't merge. No exceptions. That's how you maintain production stability."

**Connection to Homework:**
> "All three exercises build toward this complete pipeline - validation, versioning, testing, quality gates."

-----

### Closing (3 minutes)

**Slides:** 22-24

**Do Not Skip This Section** - even if running behind

#### Homework Preview

**Key Actions:**
1. Overview all three exercises briefly (use slide 22)
2. Highlight progression: workflow → versioning → testing
3. Note total time: 75 minutes
4. Point to participant guide for detailed instructions

**Script:**
> "Your homework includes three exercises totaling 75 minutes.
>
> Exercise 1.1 - create your first GitHub Actions validation workflow. 25 minutes.
> Exercise 1.2 - implement prompt versioning with manifest tracking. 25 minutes.
> Exercise 1.3 - build automated test suite with 80%+ coverage. 25 minutes.
>
> Everything you need is in your participant guide, including starter templates."

#### Resources and Support

> "Module Appendix A has GitHub Actions reference. Appendix B is troubleshooting. Appendix C is security best practices. If you get stuck, check the appendices first, then post in [support channel]."

#### Next Session Preview

> "Next session we'll cover deployment strategies - blue-green, canary releases - plus secrets management and monitoring. We'll build a complete CI/CD pipeline. Make sure your workflows from this week are running before then - we'll extend them."

#### Session Close

> "Questions before we wrap? ... Excellent session today. Remember: automation is your friend. The time you invest in pipelines pays off every time they catch a bug. See you next week!"

-----

## Anticipated Questions & Answers

### Conceptual Questions

**Q: Why do we need all this automation? Can't we just be careful?**
A: Humans make mistakes, especially under pressure. Automation is consistent - it checks the same things the same way every time. Plus it scales. You can't manually test every prompt on every change. Automation can.

**Q: How is this different from regular software CI/CD?**
A: The principles are the same, but AI artifacts have unique challenges. Prompts aren't code. LLM outputs are non-deterministic. Token limits matter. We adapt CI/CD patterns to AI-specific constraints.

**Q: What if GitHub Actions is too expensive?**
A: GitHub provides 2,000 free minutes per month for private repos, unlimited for public repos. For most AI projects, that's plenty. If you exceed it, you can optimize workflows or consider self-hosted runners.

### Technical Questions

**Q: What testing framework should we use?**
A: Any testing framework works - Jest, Mocha, pytest, etc. Choose what matches your stack. The key is having automated tests, not which tool runs them.

**Q: How do we handle secrets in GitHub Actions?**
A: GitHub Secrets (covered in Session 2). Never put API keys in code. Use repository or environment secrets. We'll cover this in depth next week.

**Q: Can workflows trigger other workflows?**
A: Yes, using workflow_dispatch or repository_dispatch events. Useful for complex pipelines. We'll touch on this in Session 2.

### Scope Questions

**Q: What about deploying to production? Is that this session?**
A: Great question - that's Session 2. Today is foundation: validation, versioning, testing. Next week we'll cover deployment strategies and monitoring.

**Q: How do we test with actual LLMs if they're non-deterministic?**
A: For unit/integration tests, we validate structure not content. For E2E tests with actual LLMs, use mock responses or LLM-as-Judge patterns. Full LLM testing is complex - start with structural validation.

### Pushback/Objections

**Q: This seems like a lot of overhead for small projects.**
A: It feels like overhead until it saves you from a production incident. Even small AI systems can have big impacts. Start simple - one validation workflow. Add complexity as you see value.

**Q: Our team doesn't know YAML. Is this worth learning?**
A: YAML is widely used in DevOps (Docker, Kubernetes, Ansible). Learning it for GitHub Actions pays dividends elsewhere. And it's straightforward - indentation-based configuration. The participant guide has examples to copy.

-----

## Troubleshooting Guide

### Technical Issues During Session

| Issue | Immediate Action | Backup Plan |
|-------|------------------|-------------|
| GitHub Actions demo fails | Check workflow syntax, view error logs | Switch to pre-captured screenshots |
| Screen share fails | Restart share, switch to application share | Have participant volunteer to share |
| YAML syntax error in demo | Copy from backup file | Explain error and show corrected version |
| Workflow doesn't trigger | Check triggers match push paths | Show previously successful run |

### Participant Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| YAML confusion | Questions about indentation, syntax errors | Show side-by-side correct vs. incorrect. Emphasize indentation matters. |
| Overwhelmed by options | "What should I validate first?" | Start simple: file structure, required sections. Add complexity incrementally. |
| GitHub Actions not triggering | Workflow not running on push | Check file location (.github/workflows/), YAML syntax, trigger paths |
| Version manifest confusion | "Why not just use git tags?" | Explain semantic meaning + deprecation tracking that tags can't provide |

### Content Challenges

| Challenge | Signs | Response |
|-----------|-------|----------|
| Too theoretical | Glazed looks, disengagement | Add more concrete examples, show real workflow files |
| Too much detail | Information overload | Speed up, reference participant guide for details |
| Questions about LLM testing | "How do we test actual outputs?" | Clarify: we test structure/consistency, not LLM quality. That requires different approaches. |

-----

## Post-Session Tasks

### Immediately After (5 minutes)

| Task | Notes |
|------|-------|
| Stop recording | If applicable |
| Save chat questions | For follow-up |
| Note timing issues | What ran long, what could be shortened |

### Within 24 Hours

| Task | Done? |
|------|-------|
| Post session recording (if applicable) | ☐ |
| Answer pending questions in support channel | ☐ |
| Share workflow template files | ☐ |
| Document demo issues for curriculum improvement | ☐ |

### Within 1 Week

| Task | Done? |
|------|-------|
| Review exercise submissions (spot check) | ☐ |
| Identify participants struggling with GitHub Actions | ☐ |
| Prepare clarifications for Session 2 | ☐ |
| Update instructor guide with lessons learned | ☐ |

-----

## Participant Progress Tracking

### Expected Deliverables This Session

| Exercise | Deliverable | Where to Find |
|----------|-------------|---------------|
| 1.1 | `.github/workflows/prompt-validation.yml` | Participant's GitHub repository |
| 1.2 | Versioned directory structure + VERSION_MANIFEST.json | `prompts/` directory in repo |
| 1.3 | Test suite files + coverage report | Tests directory, coverage/ folder |

### Progress Check Approach

**How to Verify Completion:**
- Check GitHub repositories for .github/workflows/ directory
- Look for VERSION_MANIFEST.json in prompts directory
- Verify GitHub Actions tab shows workflow runs
- Check for test files and passing status

**Red Flags:**
- Workflow files exist but have syntax errors (no runs in Actions tab)
- VERSION_MANIFEST.json missing or incorrectly structured
- Tests exist but coverage below 80%

**Intervention Thresholds:**
- 1 exercise incomplete: Normal variance, monitor
- 2+ exercises incomplete: Reach out with offer to help
- GitHub Actions not running: Priority intervention - foundation for Session 2

-----

## Session-Specific Notes

### What Makes This Session Unique

**Critical Foundation:**
- This session builds the foundation for Session 2's deployment pipeline
- If participants don't get GitHub Actions working, Session 2 will be difficult
- Prioritize getting workflows running over perfect understanding

**Key Challenges:**
- YAML syntax is unfamiliar to many - indentation errors are very common
- Conceptual leap from "manual testing" to "automated validation"
- Version control for non-code artifacts feels abstract

**Success Indicators:**
- Participants successfully create and run a GitHub Actions workflow
- Understanding of semantic versioning purpose
- Comfort with automated testing concept

### Dependencies

**Builds On:**
- Block 3: Autonomous agent systems (provides artifacts to version/test)
- Basic Git/GitHub knowledge (commits, branches, pull requests)
- Understanding of YAML basics (or willingness to learn)

**Sets Up:**
- Session 2: Deployment strategies build directly on these workflows
- Complete CI/CD pipeline extends validation workflows
- Monitoring uses GitHub Actions scheduled triggers

### Known Issues

| Issue | Workaround | Status |
|-------|------------|--------|
| Participants forget to create .github/workflows/ directory | Emphasize exact path in demo | Active |
| YAML indentation errors very common | Provide working template to copy | Active |
| Free GitHub Actions minutes concerns | Clarify 2,000 free minutes/month | Active |

-----

## Assessment Notes

### Formative Assessment (During Session)

**Check for Understanding:**
- Ask: "What trigger would you use for validating PRs before merge?" (Expected: pull_request)
- Observable understanding: Participants ask questions about their specific use cases
- Observable confusion: Silence when asked about trigger types

### Summative Assessment (End of Session)

**Exercise Quality Indicators:**
- Exercise 1.1: Workflow file exists, has correct YAML syntax, runs successfully in Actions tab
- Exercise 1.2: Directory structure follows semantic versioning, VERSION_MANIFEST.json is valid JSON
- Exercise 1.3: Tests exist, run in GitHub Actions, coverage >= 80%

**Common Issues to Flag:**
- Workflow syntax errors (check Actions tab for error messages)
- VERSION_MANIFEST.json not valid JSON (use JSON validator)
- Tests exist but don't run or fail (check test framework setup)

### Connecting to Module Capstone

**Module Capstone Relevance:**
This session's work is essential for the module capstone:
- Validation workflows become part of complete CI/CD pipeline
- Version control structure supports deployment strategies
- Test suites ensure production stability

**How Exercises Build Toward Capstone:**
- Exercise 1.1 workflow becomes validate.yml in capstone
- Exercise 1.2 version structure enables blue-green deployments
- Exercise 1.3 test suite becomes automated quality gate

-----

## Continuous Improvement

### Feedback Collection

**After This Session:**
- Monitor support channel for common questions (indicates unclear content)
- Note which segment ran long (adjust timing)
- Track exercise completion rates

**Improvement Log:**

| Date | Issue Observed | Change Made | Result |
|------|----------------|-------------|--------|
| | | | |

-----

## Quick Reference Cards

### Key Messages to Emphasize

1. "Automate everything that's checkable. Humans focus on creativity, automation handles consistency."
2. "If it doesn't pass all checks, it doesn't merge. No exceptions."
3. "Version numbers should have semantic meaning. MAJOR.MINOR.PATCH tells you what changed."

### If You Only Have Time For One Thing

**Core Concept:** GitHub Actions automates validation so every change is checked before it can affect users. This prevents production incidents and scales testing beyond human capacity.

### Memorable Analogies

| Concept | Analogy | When to Use |
|---------|---------|-------------|
| GitHub Actions | Airport security checkpoint | When explaining quality gates - nothing gets through without passing checks |
| Version Manifest | Product catalog | When explaining version tracking - shows current, discontinued, supported items |
| Automated Testing | Spell-checker | When explaining continuous validation - catches errors as you work |

-----

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial instructor guide created | Claude |
