# **POWERPOINT PRESENTATION: ADVANCED MODULE 5 SESSION 1**
## **GitHub Actions & Version Control Fundamentals**

**Module:** Advanced Module 5: Advanced GitHub & DevOps for AI Systems
**Session:** 1 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 graduates implementing professional DevOps practices for AI systems

**Session Learning Objectives:** By the end of this session, participants will:
1. Design and implement GitHub Actions workflows for AI system validation
2. Apply version control strategies for prompts and AI configurations
3. Create automated test suites for AI workflows
4. Configure quality gates and branch protection rules

**Entry Criteria:**
- [ ] Block 3 completed with working autonomous agent system
- [ ] GitHub repository created for AI workflows
- [ ] Basic understanding of YAML syntax
- [ ] At least 3 prompt templates ready for version control

**Exit Criteria:**
- [ ] GitHub Actions workflow created and running
- [ ] Prompt validation automation implemented
- [ ] Version control strategy defined and documented
- [ ] First automated test suite passing
- [ ] Branch protection rules configured

**Presentation Structure:**
1. Opening & Recap (3 min) - Slides 1-3
2. Segment 1: GitHub Actions Architecture (12 min) - Slides 4-8
3. Segment 2: Version Control for AI Artifacts (12 min) - Slides 9-12
4. Segment 3: Automated Testing for AI Workflows (12 min) - Slides 13-17
5. Segment 4: Quality Gates and Branch Protection (9 min) - Slides 18-21
6. Homework Preview & Close (3 min) - Slides 22-24

**Total Slides:** 24

-----

## Slide Definitions

### SLIDE 1: TITLE SLIDE

**Title:** Advanced Module 5 Session 1: GitHub Actions & Version Control Fundamentals

**Subtitle:** Professional DevOps Practices for AI Systems

**Content:**
- [Instructor Name]
- [Date/Cohort identifier]
- AI Practitioner Training Program - Advanced Module 5

**Graphic:** Clean title slide with program branding using green tones (Advanced module/architecture theme)

**SPEAKER NOTES:**

"[OPENING - Welcome]"

"Welcome to Advanced Module 5 on GitHub & DevOps for AI Systems. Today we're focusing on GitHub Actions and version control fundamentals for AI artifacts.

This is our first session of this advanced module. As Block 3 graduates, you've built autonomous agent systems. Now we're taking them to the next level with professional DevOps practices - CI/CD pipelines, automated testing, and production deployment strategies.

Today we're building the foundation with GitHub Actions and version control specifically designed for AI systems."

[Transition: Click to next slide]

-----

### SLIDE 2: WEEK OVERVIEW

**Title:** This Session's Journey

**Content:**

| Time | Topic | Focus |
|------|-------|-------|
| 0-3 min | Opening | Recap & Preview |
| 3-15 min | Segment 1 | GitHub Actions Architecture |
| 15-27 min | Segment 2 | Version Control for AI Artifacts |
| 27-39 min | Segment 3 | Automated Testing for AI Workflows |
| 39-42 min | Segment 4 | Quality Gates & Branch Protection |
| 42-45 min | Close | Homework & Preview |

**Graphic:** Simple timeline showing the session flow

**SPEAKER NOTES:**

"Here's what we'll cover today:

First, we'll dive into GitHub Actions architecture - the components, triggers, and execution environments. You'll learn how to build AI-specific validation pipelines.

Then, we'll move into version control strategies for AI artifacts. This is where we'll explore how to version prompts, configurations, and maintain manifest files.

In our third segment, we'll build automated testing for AI workflows - unit tests, integration tests, and quality validation.

And we'll close with quality gates and branch protection rules to ensure nothing broken reaches production.

[Pause]

Any questions before we dive in?"

[Transition]

-----

### SLIDE 3: LEARNING OBJECTIVES

**Title:** By the End of Today...

**Content:**

You will be able to:

1. **Design and implement GitHub Actions workflows for AI system validation**
   - Build workflows with appropriate triggers and execution steps

2. **Apply version control strategies for prompts and AI configurations**
   - Implement semantic versioning and manifest tracking

3. **Create automated test suites for AI workflows**
   - Develop unit and integration tests for prompt validation

4. **Configure quality gates and branch protection rules**
   - Set up guardrails that prevent broken code from reaching production

**Graphic:** Checklist visual - objectives as checkboxes participants will "complete"

**SPEAKER NOTES:**

"These are our four objectives for today. By the time you leave this session, you'll be able to:

[Read each objective, pausing briefly after each]

Notice that these are all ACTION-focused. This isn't about knowing DevOps theory - it's about implementing production-grade automation for your AI systems. You'll practice each of these in your homework exercises.

[Point to first objective]

This one is critical because GitHub Actions will become your automation backbone - validating every change before it reaches users.

Let's get started."

[Transition: Click to Segment 1]

-----

## SEGMENT 1: GitHub Actions Architecture
### Duration: 12 minutes | Slides 4-8

-----

### SLIDE 4: SEGMENT 1 - PROBLEM/HOOK

**Title:** How Do You Know Your AI Changes Won't Break Production?

**Content:**

**The Challenge:**
You've updated a prompt template, tweaked a configuration, or modified a workflow. How do you verify it works before deploying? Manual testing is slow, error-prone, and doesn't scale.

**Why It Matters:**
- A broken prompt can crash customer-facing chatbots
- Configuration errors can exceed API rate limits
- Untested workflows can fail silently in production
- Manual validation doesn't catch edge cases

**Graphic:** Visual showing manual testing chaos vs. automated pipeline - developer manually testing vs. GitHub Actions running automatically

**SPEAKER NOTES:**

"[Hook - Create tension]"

"Let me ask you a question: You've just updated a critical customer support prompt. It looks good to you. How confident are you that it won't break when it hits production?

[Pause - let question land]

The reality is that AI systems have unique failure modes. A prompt might work perfectly with one input but fail catastrophically with another. A configuration change might look innocent but exceed your token limits. And if you're relying on manual testing before every deployment, you're both slow AND unreliable.

[Point to graphic]

On the left, manual testing - slow, inconsistent, human error. On the right, GitHub Actions - automatic validation on every commit.

Today we're going to eliminate that uncertainty with automated validation pipelines."

[Transition]

**BACKGROUND:**

**Rationale:**
- This slide establishes why automation is critical for AI systems
- Creates emotional buy-in for learning GitHub Actions
- Connects abstract CI/CD concepts to real production risks
- Sets up the value proposition for automated validation

**Q&A Preparation:**
- *"Is this really necessary for smaller projects?"*: Yes - even small AI systems can have big impacts when they fail. Automation prevents preventable outages.
- *"Can't we just test manually before deploying?"*: Manual testing doesn't scale and misses edge cases. Automated tests run consistently on every change.

-----

### SLIDE 5: SEGMENT 1 - SOLUTION INTRODUCTION

**Title:** The Solution: GitHub Actions for AI Validation

**Content:**

**Core Principle:** Automate every quality check so humans can focus on creating value, not catching errors.

**How It Works:**
1. **Triggers** - Workflows run automatically on push, PR, schedule
2. **Jobs & Steps** - Define what validation to run
3. **Quality Gates** - Block merges if checks fail

**Key Benefit:** Every change is validated automatically before it can affect users.

**Graphic:** Flow diagram showing: Code Push → GitHub Actions Triggers → Validation Steps → Pass/Fail Gate → Merge or Block

**SPEAKER NOTES:**

"[INSIGHT - Deliver the solution]"

"The solution is GitHub Actions - GitHub's built-in automation platform.

The core principle is simple: automate every quality check that matters. Prompt syntax? Automated. Token limits? Automated. Required sections? Automated. If it's checkable, it should be automated.

Let me break down how this works:

First, you define triggers - when should validation run? On every push? On pull requests? On a schedule? You decide.

Second, you specify jobs and steps - what exactly should be validated? Check file structure, verify required content, count tokens, run tests.

Third, you set quality gates - if any check fails, the code cannot be merged. No exceptions.

[Point to graphic]

Notice how this creates a safety net. Nothing reaches your main branch without passing all checks.

The key insight here is that this happens automatically. You write the validation rules once, and they protect you forever.

Let me show you this in action..."

[Transition to demo]

**BACKGROUND:**

**Key Research & Citations:**
- **GitHub Actions**: Official automation platform integrated with GitHub repositories
- **CI/CD Best Practices**: Industry-standard pattern for continuous integration

**Implementation Guidance:**

**Getting Started:**
- Start with one simple validation workflow
- Add complexity incrementally

**Common Pitfalls:**
- Over-complicating initial workflows - start simple
- Not testing workflows before relying on them

-----

### SLIDE 6: SEGMENT 1 - AI-SPECIFIC WORKFLOW PATTERN

**Title:** GitHub Actions Workflow for AI Validation

**Content:**

**Example Workflow:**
```yaml
name: AI Workflow Validation Pipeline

on:
  push:
    paths:
      - 'prompts/**'
      - 'workflows/**'
      - 'configs/**'
  pull_request:
    branches: [main]

jobs:
  validate-prompts:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Validate prompt syntax
        run: npm run validate:prompts
```

**Key Components:**
- `on:` - Triggers (when to run)
- `jobs:` - What to execute
- `steps:` - Individual validation steps

**Graphic:** Annotated YAML showing each component's purpose

**SPEAKER NOTES:**

"Here's what an actual AI validation workflow looks like.

[Point to `on:` section]
This defines our triggers. We're saying: run this workflow whenever code is pushed that changes anything in prompts, workflows, or configs directories. Also run on pull requests to main.

[Point to `jobs:` section]
This is our validation job. We're using an Ubuntu runner - a clean Linux environment where our tests execute.

[Point to `steps:` section]
These are the actual validation steps. First, check out the code. Then run our prompt validation script.

The beauty is this runs automatically. Push a commit? Validation runs. Open a PR? Validation runs. No human intervention needed.

Questions about this structure?"

**BACKGROUND:**

**Demo Backup Plan:**
Use this slide as reference if live demo isn't possible.

**Timing Note:**
- Spend 3-4 minutes on this slide
- Allow questions but stay on track

-----

### SLIDE 7: SEGMENT 1 - TRIGGER TYPES

**Title:** When to Run Validation: GitHub Actions Triggers

**Content:**

| Trigger | Use Case | Example |
|---------|----------|---------|
| `push` | Validate on code changes | Prompt syntax checks |
| `pull_request` | Gate merges with validation | Quality reviews |
| `schedule` | Regular maintenance tasks | Daily prompt testing |
| `workflow_dispatch` | Manual deployments | Production releases |

**When to Use Each:**
- **push**: Immediate feedback on every commit
- **pull_request**: Quality gate before merging
- **schedule**: Proactive health checks
- **workflow_dispatch**: Human-initiated processes

**Graphic:** Table with icons for each trigger type

**SPEAKER NOTES:**

"Let's talk about when to run your validations.

Push triggers give you immediate feedback. Every time code is pushed, validation runs. Use this for quick syntax checks and basic validation.

Pull request triggers are your quality gates. Before any code can be merged to main, it must pass all checks. This is your production safety net.

Schedule triggers let you run maintenance tasks. Maybe you want to test all prompts against the latest AI models every night. Schedule it.

Workflow dispatch is for manual triggers. When you're ready to deploy to production, you click the button, and the workflow runs.

The key is matching the trigger to the purpose. Fast feedback? Push. Production safety? Pull request. Maintenance? Schedule."

[Transition]

-----

### SLIDE 8: SEGMENT 1 - KEY TAKEAWAY

**Title:** Segment 1 Summary

**Content:**

**Key Takeaway:** GitHub Actions automates quality checks so every change is validated before it can affect users.

**Remember:**
- Define triggers that match your validation needs
- Build workflows with clear, testable steps
- Let automation catch errors humans miss

**You'll Practice:**
Exercise 1.1 - Building your first AI validation workflow

**Graphic:** Simple visual showing automated pipeline protecting production

**SPEAKER NOTES:**

"Before we move on, let me summarize the key points:

GitHub Actions automates quality validation. You define the rules once, and they protect you forever.

Remember: Choose triggers that match your needs. Push for fast feedback, pull requests for production gates, schedules for maintenance.

Build workflows with clear steps - each step should do one thing well.

And let automation catch the errors humans miss. We're not perfect. Our automated tests are consistent.

In your homework this week, Exercise 1.1 will give you hands-on practice building your first validation workflow.

[Pause]

Any final questions on GitHub Actions architecture before we move to version control?"

[Transition: Click to Segment 2]

-----

## SEGMENT 2: Version Control for AI Artifacts
### Duration: 12 minutes | Slides 9-12

-----

### SLIDE 9: SEGMENT 2 - THE VERSION CONTROL CHALLENGE

**Title:** How Do You Track Changes to Prompts and AI Configurations?

**Content:**

**The Challenge:**
- Prompts evolve over time (v1.0 → v1.1 → v2.0)
- Multiple versions may be in use simultaneously
- Need to rollback to previous versions quickly
- Must track which version is deployed where

**Why Standard Git Isn't Enough:**
- No semantic meaning for AI artifact versions
- Hard to know which prompts are current vs. deprecated
- Difficult to coordinate version deployments

**Graphic:** Messy git history vs. clean versioned structure

**SPEAKER NOTES:**

"Now let's talk about a challenge specific to AI systems: version control for prompts and configurations.

Here's the problem: Your customer support prompt evolves. Version 1.0 works. Then you improve it to 1.1. Then you make major changes for 2.0.

But here's the catch - you might have different versions deployed to different environments. Staging is on 2.0, but production is still on 1.1 because you're doing a gradual rollout.

Standard git version control doesn't give you the semantic meaning you need. A git commit SHA doesn't tell you which prompt version it contains.

We need a versioning strategy designed for AI artifacts."

[Transition]

-----

### SLIDE 10: SEGMENT 2 - SEMANTIC VERSIONING FOR PROMPTS

**Title:** Semantic Versioning for AI Artifacts

**Content:**

**Version Structure:** MAJOR.MINOR.PATCH (e.g., 2.1.0)

**When to Increment:**
- **MAJOR**: Breaking changes, incompatible with previous version
- **MINOR**: New features, backward compatible
- **PATCH**: Bug fixes, no functionality changes

**Directory Structure:**
```
prompts/
├── customer-support/
│   ├── v1.0.0/
│   ├── v1.1.0/
│   └── v2.0.0/
└── VERSION_MANIFEST.json
```

**Graphic:** Directory tree visualization

**SPEAKER NOTES:**

"The solution is semantic versioning adapted for AI artifacts.

Version numbers follow MAJOR.MINOR.PATCH format.

Increment MAJOR when you make breaking changes - like completely rewriting the prompt structure. Previous integrations won't work without modification.

Increment MINOR when you add new features but maintain compatibility - like adding multilingual support while keeping the original functionality.

Increment PATCH for bug fixes - fixing typos, correcting edge cases.

[Point to directory structure]

Each version lives in its own directory. This makes it easy to deploy specific versions and rollback if needed.

The VERSION_MANIFEST.json tracks which versions are current, deprecated, or supported."

[Transition]

-----

### SLIDE 11: SEGMENT 2 - VERSION MANIFEST PATTERN

**Title:** Tracking Version Status with Manifests

**Content:**

**Version Manifest Example:**
```json
{
  "prompts": {
    "customer-support/ticket-response": {
      "current": "2.0.0",
      "deprecated": ["1.0.0"],
      "supported": ["1.1.0", "2.0.0"]
    }
  },
  "lastUpdated": "2024-01-15T10:30:00Z"
}
```

**Purpose:**
- Single source of truth for version status
- Clear deprecation tracking
- Automated version validation
- Deployment coordination

**Graphic:** Manifest file with annotations showing each field's purpose

**SPEAKER NOTES:**

"The version manifest is your single source of truth.

[Point to 'current']
This tells you which version is recommended for new deployments.

[Point to 'deprecated']
These versions should no longer be used. They're documented but not supported.

[Point to 'supported']
These are the versions you're actively supporting. They might both be in production in different environments.

This manifest becomes part of your automated validation. When someone tries to deploy a deprecated version, the pipeline catches it."

[Transition]

-----

### SLIDE 12: SEGMENT 2 - BRANCH STRATEGY

**Title:** Branch Strategy for AI Development

**Content:**

**Branching Model:**
```
main (production prompts)
├── develop (integration branch)
│   ├── feature/new-customer-prompt
│   ├── feature/multilingual-support
│   └── experiment/gpt4-optimization
├── release/v2.0
└── hotfix/urgent-prompt-fix
```

**Branch Purposes:**
- **main**: Production-ready, always deployable
- **develop**: Integration, pre-production testing
- **feature/**: New capabilities under development
- **experiment/**: Testing new approaches (may not be merged)
- **release/**: Preparing version releases
- **hotfix/**: Emergency production fixes

**Graphic:** Git branch diagram

**SPEAKER NOTES:**

"Let's talk about branching strategy for AI development.

Main branch is sacred - production-ready at all times. Nothing gets merged here without passing all quality gates.

Develop is your integration branch. Features merge here first for testing.

Feature branches are for new capabilities. Notice we have both regular features and experiments.

Experiments are important in AI - sometimes you're testing an approach that might not work. Experiment branches let you try things without cluttering your main workflow.

Release branches prepare specific versions for deployment. This is where final validation happens.

Hotfix branches let you fix production emergencies fast while keeping your main workflow clean.

Exercise 1.2 will have you implement this versioning system."

[Transition: Click to Segment 3]

-----

## SEGMENT 3: Automated Testing for AI Workflows
### Duration: 12 minutes | Slides 13-17

-----

### SLIDE 13: SEGMENT 3 - TESTING CHALLENGE

**Title:** How Do You Test AI Workflows Automatically?

**Content:**

**The Challenge:**
AI systems have unique testing requirements:
- Prompts aren't traditional code
- LLM outputs are non-deterministic
- Token limits are critical constraints
- Structure matters as much as content

**What to Test:**
- Prompt syntax and structure
- Token count limits
- Required sections present
- Variable placeholders valid
- Configuration consistency

**Graphic:** Traditional testing pyramid adapted for AI systems

**SPEAKER NOTES:**

"Now let's tackle automated testing for AI workflows.

Testing AI systems is different from testing traditional software. You can't just check if a function returns the right value.

Prompts are structured text, not code. LLM outputs are non-deterministic - you can't assert an exact output. And constraints like token limits are critical.

So what do we test?

We test structure - does the prompt have all required sections?

We test constraints - is it within token limits?

We test syntax - are all variable placeholders valid?

We test configuration - are settings consistent across environments?

These are all deterministic checks we can automate."

[Transition]

-----

### SLIDE 14: SEGMENT 3 - TESTING PYRAMID FOR AI

**Title:** The AI Testing Pyramid

**Content:**

**Three Layers:**

**Unit Tests (Base - Most tests here):**
- Prompt validation
- Syntax checks
- Token count limits
- Required sections present

**Integration Tests (Middle):**
- Workflow component interaction
- Configuration consistency
- End-to-end structure validation

**E2E Tests (Top - Fewest tests):**
- Full workflow execution with mock AI
- Output format validation
- Error handling verification

**Graphic:** Pyramid diagram showing the three layers

**SPEAKER NOTES:**

"The testing pyramid for AI systems looks like this.

Most of your tests are unit tests - fast, focused checks. Does this prompt have required sections? Is it within token limits? These run in milliseconds.

The middle layer is integration tests - do components work together? Is configuration consistent? These take longer but catch coordination issues.

The top is E2E tests with mock AI responses. These are slow and brittle, so you have fewer of them. But they validate the complete workflow.

The key is having many fast unit tests and few slow E2E tests. This keeps your pipeline fast while maintaining coverage."

[Transition]

-----

### SLIDE 15: SEGMENT 3 - UNIT TEST EXAMPLE

**Title:** Unit Testing Prompts

**Content:**

**Example Unit Test:**
```javascript
describe('Customer Support Prompts', () => {
  test('should have required sections', () => {
    expect(promptContent).toContain('## System Context');
    expect(promptContent).toContain('## Instructions');
    expect(promptContent).toContain('## Output Format');
  });

  test('should be within token limits', () => {
    const tokenCount = checkTokenCount(promptContent);
    expect(tokenCount).toBeLessThan(4000);
  });
});
```

**What This Tests:**
- Required sections are present
- Token limits not exceeded
- Structure is valid

**Graphic:** Code snippet with annotations

**SPEAKER NOTES:**

"Here's what a prompt unit test looks like.

[Point to first test]
This checks for required sections. Every customer support prompt must have System Context, Instructions, and Output Format. If any are missing, the test fails.

[Point to second test]
This validates token count. We're using a 4000 token limit. If the prompt exceeds it, the test fails before deployment.

These tests run in milliseconds. You can have hundreds of them and your pipeline still completes in seconds.

This is the foundation of automated quality."

[Transition]

-----

### SLIDE 16: SEGMENT 3 - GITHUB ACTIONS TEST WORKFLOW

**Title:** Integrating Tests into GitHub Actions

**Content:**

**Test Workflow Pattern:**
```yaml
jobs:
  unit-tests:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run prompt unit tests
        run: npm run test:prompts

  integration-tests:
    needs: unit-tests
    runs-on: ubuntu-latest
    steps:
      - name: Run integration tests
        run: npm run test:integration
```

**Key Features:**
- `needs:` ensures unit tests pass before integration tests run
- Separate jobs for test isolation
- Clear failure visibility

**Graphic:** Workflow diagram showing job dependencies

**SPEAKER NOTES:**

"Here's how we integrate tests into GitHub Actions.

[Point to unit-tests job]
First job runs unit tests - fast, focused validation.

[Point to integration-tests job]
Second job runs integration tests, but notice the 'needs' keyword. Integration tests only run if unit tests pass.

This saves time. If unit tests fail, we don't waste time running integration tests.

Each job runs in isolation. If integration tests fail, you know unit tests passed, so the problem is in component interaction.

This structure gives you clear, fast feedback on exactly what's broken."

[Transition]

-----

### SLIDE 17: SEGMENT 3 - KEY TAKEAWAY

**Title:** Segment 3 Summary

**Content:**

**Key Takeaway:** Automated tests validate AI workflows consistently - catching errors before they reach users.

**Remember:**
- Unit tests are fast and focused - most tests should be unit tests
- Integration tests validate component interaction
- E2E tests with mock AI cover complete workflows
- GitHub Actions runs all tests automatically

**You'll Practice:**
Exercise 1.3 - Building an automated test suite with 80%+ coverage

**Graphic:** Testing pyramid with checkmarks

**SPEAKER NOTES:**

"Key points on testing:

Automated tests catch errors humans miss. They run consistently on every change.

Build a strong foundation of unit tests - fast, focused, reliable.

Add integration tests to catch coordination issues.

Use E2E tests sparingly - they're slow but valuable.

And let GitHub Actions run everything automatically. You focus on building features. Tests catch the bugs.

Exercise 1.3 will have you build a complete test suite with 80%+ coverage.

Questions on testing before we move to quality gates?"

[Transition: Click to Segment 4]

-----

## SEGMENT 4: Quality Gates and Branch Protection
### Duration: 9 minutes | Slides 18-21

-----

### SLIDE 18: SEGMENT 4 - QUALITY GATES

**Title:** Enforcing Quality: Nothing Broken Reaches Production

**Content:**

**The Principle:** If it doesn't pass all checks, it doesn't merge.

**Required Status Checks:**
- Prompt validation must pass
- All tests must succeed
- Coverage thresholds must be met

**Quality Gate Example:**
```yaml
quality-gate:
  needs: [unit-tests, integration-tests]
  steps:
    - name: Check test coverage threshold
      run: |
        COVERAGE=$(cat coverage/coverage-summary.json | jq '.total.lines.pct')
        if (( $(echo "$COVERAGE < 80" | bc -l) )); then
          echo "Coverage $COVERAGE% is below 80% threshold"
          exit 1
        fi
```

**Graphic:** Quality gate blocking failed code

**SPEAKER NOTES:**

"Quality gates enforce one simple rule: if it doesn't pass all checks, it doesn't merge.

No exceptions. No 'we'll fix it later.' No 'it's just a small change.'

[Point to required checks]
Prompt validation must pass. Tests must succeed. Coverage must meet threshold.

[Point to code]
This quality gate checks test coverage. If coverage is below 80%, the build fails. The code cannot be merged.

This might feel strict. It is. That's the point.

Quality gates prevent 'just this once' decisions that lead to production outages."

[Transition]

-----

### SLIDE 19: SEGMENT 4 - BRANCH PROTECTION

**Title:** Branch Protection Rules

**Content:**

**Protection Settings for Main Branch:**

**Require:**
- Pull request reviews (at least 1)
- Status checks to pass before merging
- Up-to-date branches
- Conversation resolution before merging

**Restrict:**
- Direct pushes to main (nobody can push directly)
- Force pushes
- Deletion

**Result:** Main branch is always stable and deployable

**Graphic:** GitHub branch protection settings interface

**SPEAKER NOTES:**

"Branch protection rules enforce your quality gates.

[Point to require section]
Main branch requires pull request reviews - no one commits directly. It requires status checks to pass - all tests must be green. Branches must be up-to-date before merging.

[Point to restrict section]
No direct pushes to main. No force pushes that rewrite history. No deletion.

The result? Main branch is sacred. It's always stable, always deployable, always tested.

This is how you prevent 2am emergencies caused by untested code reaching production."

[Transition]

-----

### SLIDE 20: SEGMENT 4 - PUTTING IT ALL TOGETHER

**Title:** The Complete Validation Pipeline

**Content:**

**Flow:**
```
Developer pushes code
    ↓
GitHub Actions triggers
    ↓
Unit tests run → Pass/Fail
    ↓
Integration tests run → Pass/Fail
    ↓
Quality gate checks coverage → Pass/Fail
    ↓
All checks pass → PR can be merged
    ↓
Branch protection enforces review
    ↓
Code merges to main
```

**Protection at Every Step**

**Graphic:** Complete pipeline flow diagram

**SPEAKER NOTES:**

"Let's see how all these pieces work together.

Developer pushes code. GitHub Actions triggers automatically.

Unit tests run. If they fail, the process stops.

If unit tests pass, integration tests run. If they fail, the process stops.

If integration tests pass, quality gates check coverage and other metrics.

Only if everything passes can the PR be merged.

And even then, branch protection requires human review.

Multiple layers of protection. Each one catches different classes of errors.

This is production-grade DevOps for AI systems."

[Transition]

-----

### SLIDE 21: SEGMENT 4 - KEY TAKEAWAY

**Title:** Segment 4 Summary

**Content:**

**Key Takeaway:** Quality gates and branch protection prevent broken code from reaching production.

**Remember:**
- Require all status checks to pass before merging
- Protect main branch from direct pushes
- Enforce code reviews for human oversight
- Multiple layers of protection catch different error types

**You'll Practice:**
All three exercises build toward this complete validation pipeline

**Graphic:** Shield protecting production environment

**SPEAKER NOTES:**

"Final points on quality gates:

They prevent broken code from reaching production. No exceptions.

Require all checks to pass. Protect your main branch. Enforce reviews.

Multiple layers catch multiple error types. Automation catches syntax errors. Tests catch logic errors. Reviews catch design errors.

Your exercises this week build this complete pipeline - validation, versioning, testing, and quality gates.

Questions on quality gates?"

[Transition: Click to Closing]

-----

## CLOSING SECTION
### Duration: 3 minutes | Slides 22-24

-----

### SLIDE 22: HOMEWORK OVERVIEW

**Title:** This Week's Practice

**Content:**

| Exercise | Time | Deliverable | Skills Practiced |
|----------|------|-------------|------------------|
| Exercise 1.1: AI Validation Workflow | 25 min | Working GitHub Actions workflow | Workflow creation, triggers, validation steps |
| Exercise 1.2: Prompt Versioning System | 25 min | Versioned directory structure + manifest | Semantic versioning, version tracking |
| Exercise 1.3: Automated Test Suite | 25 min | Test suite with 80%+ coverage | Unit testing, coverage reporting |
| **Total** | **75 min** | | |

**Graphic:** Exercise icons showing progression

**SPEAKER NOTES:**

"Here's your homework for this week. You have 75 minutes of exercises to complete before our next session.

Exercise 1.1 takes about 25 minutes. You'll create your first GitHub Actions validation workflow. This practices everything from Segment 1.

Exercise 1.2 is also 25 minutes. You'll implement a versioned prompt structure with manifest tracking. This applies Segment 2's version control strategies.

Exercise 1.3, another 25 minutes. You'll build an automated test suite with 80%+ coverage. This practices Segment 3's testing patterns.

These exercises build on each other, so I recommend completing them in order.

All the detailed instructions are in your participant guide, along with templates and starter code."

[Transition]

-----

### SLIDE 23: RESOURCES

**Title:** Resources for This Week

**Content:**

**Templates & Files:**
- GitHub Actions workflow templates - In participant guide
- VERSION_MANIFEST.json template - In participant guide
- Test suite examples - In participant guide

**Reference Materials:**
- GitHub Actions Documentation: https://docs.github.com/actions
- Semantic Versioning Spec: https://semver.org
- Testing Best Practices: In module appendices

**Support:**
- Questions: [Async channel name]
- Module Appendices: A, B, C for troubleshooting and reference

**Graphic:** QR codes or simple icons for quick access

**SPEAKER NOTES:**

"You have several resources to support your homework:

All templates are in your participant guide - ready to copy and customize.

GitHub's official documentation for Actions is comprehensive. The semantic versioning spec explains the MAJOR.MINOR.PATCH format.

Module appendices include GitHub Actions reference, troubleshooting guide, and security checklist.

If you get stuck, post in [async channel]. Check the troubleshooting appendix first - it covers common issues."

[Transition]

-----

### SLIDE 24: NEXT WEEK PREVIEW

**Title:** Next Session: Advanced DevOps Patterns

**Content:**

**Preview:**
Next session we'll cover deployment strategies, secrets management, monitoring, and build a complete CI/CD pipeline.

**What to Complete Before Then:**
- [ ] Exercise 1.1: AI Validation Workflow
- [ ] Exercise 1.2: Prompt Versioning System
- [ ] Exercise 1.3: Automated Test Suite

**Key Preparation:**
Ensure your GitHub Actions workflows are running successfully - we'll build on them next session.

**Graphic:** Preview image showing deployment pipeline

**SPEAKER NOTES:**

"Next session we'll cover advanced DevOps patterns - blue-green deployments, canary releases, secrets management, monitoring, and alerting.

We'll take the validation pipeline you build this week and extend it into a complete CI/CD system that deploys to production.

Make sure you've completed all three exercises before next session - we'll be building on them directly.

Specifically, ensure your GitHub Actions workflows are running successfully. That's your foundation.

[Final close]

Great session today. Remember: automation is your friend. The effort you invest in pipelines pays dividends every time they catch a bug before production.

See you next week!"

-----

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | Claude |
