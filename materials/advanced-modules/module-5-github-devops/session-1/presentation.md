# **POWERPOINT PRESENTATION: ADVANCED MODULE 5 SESSION 1**
## **GitHub Actions & Version Control Fundamentals**

**Module:** Advanced Module 5: Advanced GitHub & DevOps for AI Systems
**Session:** 1 of 2
**Session Duration:** 45 minutes
**Delivery Format:** Live MS Teams workshop

**Target Audience:** Block 3 graduates implementing professional DevOps practices for AI systems

**Key Thesis:** GitHub Actions transforms AI system development from manual testing to automated validation pipelines—enabling version-controlled prompts, automated quality gates, and continuous integration workflows that catch errors before deployment, while treating prompts and AI configurations as code artifacts requiring the same rigorous version control and testing as traditional software.

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

**GRAPHICS:**

**Graphic 1: Manual vs Automated Testing Comparison**
- Purpose: Contrast the chaos of manual testing with the reliability of automated pipelines
- Type: Split-screen comparison diagram
- Elements:
  - Left side (Manual): Developer at computer, sticky notes, clipboard, question marks, error symbols
  - Right side (Automated): Clean GitHub Actions workflow with checkmarks, automated steps flowing
- Labels:
  - Manual side: "Slow", "Inconsistent", "Human Error", "Time-Consuming"
  - Automated side: "Fast", "Consistent", "Reliable", "Automatic"
- Relationships: Visual contrast using chaotic/messy design on left, clean/orderly design on right

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

**GRAPHICS:**

**Graphic 1: GitHub Actions Validation Pipeline Flow**
- Purpose: Illustrate the automated validation workflow from code push to merge decision
- Type: Horizontal process flow diagram
- Elements:
  - Developer icon pushing code (commit symbol)
  - GitHub Actions trigger (lightning bolt/gear icon)
  - Validation steps box (checklist with items: syntax check, token count, required sections)
  - Decision diamond (Pass/Fail)
  - Two outcomes: Green checkmark → "Merge Allowed" or Red X → "Blocked"
- Labels: Each stage clearly labeled with action and outcome
- Relationships: Arrows showing sequential flow, conditional branching at Pass/Fail gate
- Visual cues: Green for success path, red for failure path

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

**GRAPHICS:**

**Graphic 1: Annotated GitHub Actions Workflow YAML**
- Purpose: Explain the structure and purpose of each section in a GitHub Actions workflow
- Type: Code snippet with callout annotations
- Elements:
  - YAML code block displaying the workflow example
  - Callout boxes with arrows pointing to specific sections
- Labels/Annotations:
  - `on:` section: "Triggers - when to run this workflow"
  - `paths:` section: "Watch these directories for changes"
  - `jobs:` section: "What to execute"
  - `runs-on:` section: "Execution environment (Ubuntu Linux)"
  - `steps:` section: "Individual validation actions"
  - `uses: actions/checkout@v4`: "Checks out code from repository"
  - `run:` section: "Command to execute"
- Relationships: Visual hierarchy showing workflow structure (triggers → jobs → steps)
- Visual cues: Color coding for different YAML keys (triggers=blue, jobs=green, steps=orange)

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

**GRAPHICS:**

**Graphic 1: Unstructured Git History vs. Semantic Versioning**
- Purpose: Show the problem of tracking AI artifacts without version strategy versus a clean approach
- Type: Before/after comparison
- Elements:
  - Left side (Messy): Tangled git commit graph with generic messages like "update prompt", "fix", "try this"
  - Right side (Clean): Organized folder structure with clear version numbers (v1.0.0, v1.1.0, v2.0.0)
- Labels:
  - Messy side: "Which version is in production?", "What changed?", "Hard to rollback"
  - Clean side: "Clear version history", "Easy deployment", "Simple rollback"
- Relationships: Visual contrast showing confusion vs. clarity
- Visual cues: Question marks and confusion symbols on left, checkmarks and organization on right

**SPEAKER NOTES:**

"Now let's talk about a challenge specific to AI systems: version control for prompts and configurations.

Here's the problem: Your customer support prompt evolves. Version 1.0 works. Then you improve it to 1.1. Then you make major changes for 2.0.

But here's the catch - you might have different versions deployed to different environments. Staging is on 2.0, but production is still on 1.1 because you're doing a gradual rollout.

Standard git version control doesn't give you the semantic meaning you need. A git commit SHA doesn't tell you which prompt version it contains.

We need a versioning strategy designed for AI artifacts."

[Transition]

**BACKGROUND:**

**Rationale:**
- Git manages code changes but lacks semantic versioning for AI artifacts
- Prompts are content, not code - they need human-readable version identifiers
- Multiple simultaneous versions in production require clear version tracking
- Rollback decisions need quick version identification without parsing git history

**Key Research & Citations:**
- Semantic Versioning 2.0.0 specification provides industry-standard MAJOR.MINOR.PATCH format
- GitHub's version management best practices emphasize human-readable version identifiers
- MLOps versioning patterns adapted from software versioning but tailored for model/prompt artifacts
- Version manifests pattern borrowed from package management (npm, Maven)

**Q&A Preparation:**
- *"Why not just use git tags?"*: Git tags work for releases but don't provide directory-based organization or manifest tracking. You can combine both approaches.
- *"Isn't this overkill for small projects?"*: Even small AI projects benefit from clear version tracking when you need to rollback or compare performance across versions.
- *"What about model versioning?"*: Same principles apply - semantic versioning works for models, prompts, configurations, and any AI artifact.

**Sources:**
- Semantic Versioning Specification: https://semver.org/
- GitHub Versioning Best Practices: https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases
- MLOps Version Control Patterns: https://ml-ops.org/content/model-management

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

**GRAPHICS:**

**Graphic 1: Semantic Versioning Directory Structure**
- Purpose: Visualize the organized folder hierarchy for versioned prompts
- Type: Hierarchical tree diagram
- Elements:
  - Root folder: `prompts/`
  - Subfolder: `customer-support/`
  - Version folders: `v1.0.0/`, `v1.1.0/`, `v2.0.0/` (each with folder icon)
  - Manifest file: `VERSION_MANIFEST.json` (document icon)
  - Example prompt files within version folders (e.g., `ticket-response.md`)
- Labels:
  - Folder icons for directories
  - Document icons for files
  - Version numbers in bold
  - "CURRENT" badge on v2.0.0
  - "DEPRECATED" badge on v1.0.0
- Relationships: Tree structure showing parent-child hierarchy, indentation levels
- Visual cues: Color coding (current version=green, deprecated=gray, supported=blue)

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

**BACKGROUND:**

**Rationale:**
- Directory-based versioning provides physical separation preventing accidental overwrites
- Semantic versioning communicates impact of changes without reading code
- MAJOR.MINOR.PATCH convention is universally understood by technical teams
- Version manifests enable automated deployment validation and coordination

**Key Research & Citations:**
- Semantic Versioning (SemVer) created by Tom Preston-Werner, GitHub co-founder
- Widely adopted across software ecosystems (npm, Python packages, Docker images)
- AI/ML community adapted SemVer for model versioning (MLflow, Weights & Biases)
- Directory-per-version pattern enables zero-downtime blue-green deployments

**Q&A Preparation:**
- *"When exactly should I increment MAJOR vs MINOR?"*: MAJOR when prompt structure changes break existing integrations. MINOR when you add capabilities but maintain compatibility. PATCH for bug fixes.
- *"Do I need to keep all old versions?"*: Keep supported versions. Archive deprecated versions if needed for auditing but remove from active deployment.
- *"How does this work with git branches?"*: Version directories live on all branches. Branch strategy determines which versions are promoted to production.

**Sources:**
- Semantic Versioning 2.0.0: https://semver.org/
- MLflow Model Versioning: https://mlflow.org/docs/latest/model-registry.html
- Blue-Green Deployment Patterns: https://martinfowler.com/bliki/BlueGreenDeployment.html

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

**GRAPHICS:**

**Graphic 1: Annotated VERSION_MANIFEST.json**
- Purpose: Explain the structure and purpose of the version manifest file
- Type: JSON code snippet with callout annotations
- Elements:
  - JSON code block showing the manifest example
  - Callout boxes with arrows pointing to specific fields
- Labels/Annotations:
  - `"current": "2.0.0"`: "Recommended version for new deployments"
  - `"deprecated": ["1.0.0"]`: "No longer supported - do not use"
  - `"supported": ["1.1.0", "2.0.0"]`: "Actively maintained versions"
  - `"lastUpdated"`: "Timestamp of last manifest change"
  - Prompt path: "Unique identifier for this prompt template"
- Relationships: Hierarchical JSON structure, version lifecycle (deprecated → supported → current)
- Visual cues: Color coding (current=green, deprecated=red, supported=blue), arrows showing version progression

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

**BACKGROUND:**

**Rationale:**
- Single source of truth prevents version confusion across team members
- Automated validation uses manifest to block deprecated version deployments
- Deployment coordination requires knowing which versions are production-ready
- Manifest provides audit trail of version lifecycle (when versions were deprecated)

**Key Research & Citations:**
- Package management manifests (package.json, requirements.txt) provide proven pattern
- Infrastructure as Code principles: version state should be declarative and version-controlled
- JSON format enables both human readability and automated parsing
- Timestamp tracking enables version lifecycle analysis and compliance auditing

**Q&A Preparation:**
- *"Who updates the manifest?"*: Same PR that introduces new version or deprecates old one should update manifest. Make it part of your version change checklist.
- *"Can't this get out of sync with actual deployed versions?"*: Manifest represents intended state. Use deployment workflows to validate manifest matches deployed reality.
- *"Should this be JSON or YAML?"*: Either works. JSON has better tooling support for validation and parsing. YAML is more human-friendly. Choose based on team preference.

**Sources:**
- Package.json specification: https://docs.npmjs.com/cli/v9/configuring-npm/package-json
- Infrastructure as Code principles: https://www.terraform.io/docs/language/index.html
- Version lifecycle management: https://semver.org/spec/v2.0.0.html

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

**GRAPHICS:**

**Graphic 1: AI Development Branch Strategy**
- Purpose: Visualize the branching model for AI development with different branch types
- Type: Git flow diagram
- Elements:
  - Main branch (horizontal line at top, in bold): "main (production prompts)"
  - Develop branch (horizontal line below main): "develop (integration branch)"
  - Feature branches (branching off develop): "feature/new-customer-prompt", "feature/multilingual-support"
  - Experiment branch (branching off develop): "experiment/gpt4-optimization"
  - Release branch (branching from develop): "release/v2.0"
  - Hotfix branch (branching from main): "hotfix/urgent-prompt-fix"
- Labels: Branch names clearly labeled, branch type in parentheses
- Relationships:
  - Branches diverging from and merging back to parent branches
  - Arrows showing merge direction (feature → develop → main)
  - Dotted lines for experiment branches (may not merge)
- Visual cues: Color coding (main=red, develop=blue, feature=green, experiment=purple, release=orange, hotfix=yellow)

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

**GRAPHICS:**

**Graphic 1: AI Testing Pyramid**
- Purpose: Show the distribution and types of tests in an AI system testing strategy
- Type: Pyramid/triangle diagram with three layers
- Elements:
  - Bottom layer (largest): "Unit Tests" - 70% of tests
  - Middle layer: "Integration Tests" - 25% of tests
  - Top layer (smallest): "E2E Tests" - 5% of tests
- Labels:
  - Unit Tests: "Prompt validation, syntax checks, token limits, required sections"
  - Integration Tests: "Workflow component interaction, configuration consistency"
  - E2E Tests: "Full workflow with mock AI, output format validation"
  - Side annotation: "Fast, focused, many tests" → "Slow, comprehensive, few tests"
- Relationships: Size of each layer represents proportion of tests, vertical arrangement shows testing hierarchy
- Visual cues: Color gradient from green (bottom/fast) to red (top/slow), percentages labeled on each layer

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

**BACKGROUND:**

**Rationale:**
- AI systems require different testing approaches than traditional software
- Non-deterministic outputs make exact assertion testing impossible
- Testing structure, constraints, and configuration is more valuable than testing exact outputs
- Automated testing prevents regression as prompts evolve

**Key Research & Citations:**
- Testing Pyramid pattern (Mike Cohn) adapted for AI/ML systems
- Google's Testing Blog: "Testing on the Toilet" series on effective test strategies
- AI testing research emphasizes deterministic structural validation over output validation
- Token counting libraries (tiktoken for OpenAI) enable automated constraint testing

**Q&A Preparation:**
- *"How can we test AI outputs if they're non-deterministic?"*: Test structure and constraints (token limits, required sections) rather than exact output. Use LLM-as-Judge pattern for semantic validation when needed.
- *"Isn't this just testing the prompt file, not the AI behavior?"*: Correct - we validate artifacts (prompts, configs) not AI model behavior. Integration tests with mock responses validate workflow behavior.
- *"What about testing actual AI quality?"*: That's evaluation (Block 3 material). Here we're testing engineering quality - syntax, structure, constraints.

**Sources:**
- The Testing Pyramid (Mike Cohn): https://martinfowler.com/articles/practical-test-pyramid.html
- Testing AI Systems: https://developers.google.com/machine-learning/testing-debugging
- Tiktoken (OpenAI token counter): https://github.com/openai/tiktoken

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

**GRAPHICS:**

**Graphic 1: Three-Layer Testing Pyramid with Details**
- Purpose: Detail what each testing layer includes and validates
- Type: Pyramid diagram with expanded detail boxes
- Elements:
  - Base layer (Unit Tests): Large foundation section
  - Middle layer (Integration Tests): Medium section
  - Top layer (E2E Tests): Small peak section
  - Detail boxes beside each layer explaining contents
- Labels:
  - Unit Tests box: "Prompt validation • Syntax checks • Token count limits • Required sections present" with checkmark bullets
  - Integration Tests box: "Workflow component interaction • Configuration consistency • End-to-end structure validation"
  - E2E Tests box: "Full workflow execution with mock AI • Output format validation • Error handling verification"
  - Execution time annotations: "< 1 second each", "< 10 seconds each", "< 60 seconds each"
- Relationships: Pyramid shape showing volume distribution, connecting lines from boxes to layers
- Visual cues: Icons (magnifying glass for unit, puzzle pieces for integration, full system icon for E2E)

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

**GRAPHICS:**

**Graphic 1: GitHub Actions Job Dependency Flow**
- Purpose: Illustrate how jobs are sequenced and dependent on each other's success
- Type: Vertical flowchart with dependency arrows
- Elements:
  - Job box 1: "unit-tests" (runs-on: ubuntu-latest)
  - Dependency arrow with "needs: unit-tests" label
  - Job box 2: "integration-tests" (runs-on: ubuntu-latest)
  - Checkmark icon indicating success required to proceed
  - Failure path: Red X showing workflow stops if unit tests fail
- Labels:
  - "unit-tests": "Fast validation - syntax, structure, token limits"
  - "integration-tests": "Component interaction - only runs if unit tests pass"
  - "needs: unit-tests": Annotation explaining dependency relationship
  - "Fail Fast": Label on failure path showing early termination
- Relationships: Sequential execution flow, conditional progression based on success/failure
- Visual cues: Green arrows for success path, red indicators for failure, dashed line for "blocked" state

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

**BACKGROUND:**

**Rationale:**
- Humans make exceptions under pressure ("just this once, we'll skip tests")
- Automated gates enforce quality standards without emotions or fatigue
- Coverage thresholds prevent degradation of test quality over time
- Failed checks provide clear, objective reason to pause and fix issues

**Key Research & Citations:**
- Google's research: Code review + automated checks reduce defects by 85%
- Coverage threshold studies show 80% as optimal balance (higher has diminishing returns)
- GitHub Status Checks enable blocking merges based on external tool results
- CI/CD best practices emphasize "fail fast, fail loud" for quality gates

**Q&A Preparation:**
- *"Isn't 80% coverage too strict?"*: 80% is industry standard for production systems. Lower for experimental code, higher for critical paths. Adjust based on risk.
- *"What if there's an emergency and we need to bypass?"*: Repository administrators can override, but it's audited. Use sparingly and document why.
- *"Do quality gates slow down development?"*: Initially yes, long-term no. They catch issues early when they're cheap to fix versus expensive production incidents.

**Sources:**
- Code Review Research (Google): https://research.google/pubs/pub47025/
- Test Coverage Best Practices: https://martinfowler.com/bliki/TestCoverage.html
- GitHub Required Status Checks: https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches

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

**GRAPHICS:**

**Graphic 1: End-to-End Validation Pipeline**
- Purpose: Show the complete workflow from code push to production merge
- Type: Vertical flowchart with decision points
- Elements:
  - Start: "Developer pushes code" (developer icon)
  - Step 1: "GitHub Actions triggers" (automation icon)
  - Step 2: "Unit tests run" → Decision: Pass/Fail
  - Step 3: "Integration tests run" → Decision: Pass/Fail (only if unit tests pass)
  - Step 4: "Quality gate checks coverage" → Decision: Pass/Fail
  - Step 5: "All checks pass → PR can be merged" (green checkmark)
  - Step 6: "Branch protection enforces review" (reviewer icon)
  - End: "Code merges to main" (merge icon)
- Labels: Each step clearly labeled with action and outcome
- Relationships: Sequential flow with conditional branching, failure at any point stops pipeline
- Visual cues:
  - Green checkmarks for passes
  - Red X symbols for failures leading to "Pipeline stops"
  - Shield icon for protection layers
  - Multiple verification gates highlighted

**GRAPHIC 2: Multiple Layers of Protection**
- Purpose: Emphasize the defense-in-depth approach of the pipeline
- Type: Concentric circles or shield layers
- Elements:
  - Outer layer: "Automated validation"
  - Middle layer: "Automated testing"
  - Inner layer: "Quality gates"
  - Core: "Human review"
  - Center: "Production code" (protected)
- Labels: Each layer labeled with what it catches
- Relationships: Multiple overlapping protection mechanisms
- Visual cues: Shield imagery, each layer a different color, arrows pointing to what each layer blocks

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

**GRAPHICS:**

**Graphic 1: Next Session Preview - Advanced DevOps Pipeline**
- Purpose: Tease the topics covered in Session 2 with a visual preview
- Type: Horizontal pipeline diagram
- Elements:
  - Stage 1: "Validate" (checkmark icon) - representing Session 1 content
  - Stage 2: "Deploy to Staging" (cloud icon with staging label)
  - Stage 3: "Blue-Green Deployment" (two server icons, one blue, one green)
  - Stage 4: "Canary Release" (progress bar showing 10% → 100%)
  - Stage 5: "Monitor & Alert" (dashboard/graph icon)
  - Secrets vault icon above pipeline showing secure configuration management
- Labels: Each stage labeled, "Session 1" vs "Session 2" demarcated
- Relationships: Linear progression through deployment stages
- Visual cues: Session 1 stages in solid color (completed), Session 2 stages in lighter/preview color, arrow showing progression

**SPEAKER NOTES:**

"Next session we'll cover advanced DevOps patterns - blue-green deployments, canary releases, secrets management, monitoring, and alerting.

We'll take the validation pipeline you build this week and extend it into a complete CI/CD system that deploys to production.

Make sure you've completed all three exercises before next session - we'll be building on them directly.

Specifically, ensure your GitHub Actions workflows are running successfully. That's your foundation.

[Final close]

Great session today. Remember: automation is your friend. The effort you invest in pipelines pays dividends every time they catch a bug before production.

See you next week!"

---

## APPENDICES

### Appendix A: Slide Type Definitions

**TITLE SLIDE**, **PROBLEM STATEMENT**, **INSIGHT / REVELATION**, **CONCEPT INTRODUCTION**, **FRAMEWORK / MODEL**, **COMPARISON**, **DEEP DIVE**, **CASE STUDY**, **PATTERN / BEST PRACTICE**, **METRICS / DATA**, **ARCHITECTURE / DIAGRAM**, **OBJECTION HANDLING**, **ACTION / NEXT STEPS**, **SUMMARY / RECAP**, **CLOSING / CALL TO ACTION**, **Q&A / CONTACT**, **APPENDIX**

### Appendix B: BACKGROUND & Implementation Guidance

See template for full BACKGROUND section structure (Rationale, Key Research & Citations, Q&A Preparation) and Implementation Guidance structure (Getting Started, Best Practices, Common Pitfalls, Tools & Technologies).

### Appendix C: GitHub Actions Workflow Templates

**Basic Validation Workflow:**
```yaml
name: AI Workflow Validation

on:
  push:
    paths:
      - 'prompts/**'
      - 'workflows/**'
      - 'configs/**'
  pull_request:
    branches: [main, develop]

jobs:
  validate-prompts:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Install dependencies
        run: npm ci

      - name: Validate prompt syntax
        run: npm run validate:prompts

      - name: Check token limits
        run: npm run check:tokens

      - name: Verify required sections
        run: npm run verify:structure
```

**Pull Request Quality Gate:**
```yaml
name: PR Quality Gate

on:
  pull_request:
    branches: [main]

jobs:
  quality-checks:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Run all validations
        run: npm run validate:all

      - name: Run tests with coverage
        run: npm run test:coverage

      - name: Check coverage threshold
        run: |
          COVERAGE=$(cat coverage/coverage-summary.json | jq '.total.lines.pct')
          if (( $(echo "$COVERAGE < 80" | bc -l) )); then
            echo "❌ Coverage $COVERAGE% is below 80% threshold"
            exit 1
          fi
          echo "✅ Coverage $COVERAGE% meets threshold"

      - name: Comment coverage on PR
        uses: actions/github-script@v7
        with:
          script: |
            const coverage = require('./coverage/coverage-summary.json');
            const pct = coverage.total.lines.pct;
            github.rest.issues.createComment({
              issue_number: context.issue.number,
              owner: context.repo.owner,
              repo: context.repo.repo,
              body: `📊 Test Coverage: ${pct}%`
            });
```

### Appendix D: Version Control Best Practices

**Directory Structure Template:**
```
ai-workflows/
├── prompts/
│   ├── customer-support/
│   │   ├── v1.0.0/
│   │   │   ├── ticket-response.md
│   │   │   ├── escalation-handler.md
│   │   │   └── metadata.json
│   │   ├── v1.1.0/
│   │   │   └── [same structure]
│   │   └── v2.0.0/
│   │       └── [same structure]
│   ├── sales-automation/
│   │   └── v1.0.0/
│   └── VERSION_MANIFEST.json
├── workflows/
│   └── [similar versioning]
└── configs/
    ├── development.yml
    ├── staging.yml
    └── production.yml
```

**VERSION_MANIFEST.json Template:**
```json
{
  "manifestVersion": "1.0.0",
  "lastUpdated": "2026-01-03T10:00:00Z",
  "prompts": {
    "customer-support/ticket-response": {
      "current": "2.0.0",
      "deprecated": ["1.0.0"],
      "supported": ["1.1.0", "2.0.0"],
      "deployments": {
        "production": "1.1.0",
        "staging": "2.0.0"
      }
    },
    "customer-support/escalation-handler": {
      "current": "1.1.0",
      "deprecated": [],
      "supported": ["1.0.0", "1.1.0"],
      "deployments": {
        "production": "1.1.0",
        "staging": "1.1.0"
      }
    }
  },
  "workflows": {
    "sales-automation/lead-qualification": {
      "current": "1.0.0",
      "deprecated": [],
      "supported": ["1.0.0"],
      "deployments": {
        "production": "1.0.0",
        "staging": "1.0.0"
      }
    }
  }
}
```

**Metadata Template for Versions:**
```json
{
  "version": "2.0.0",
  "releaseDate": "2026-01-03",
  "author": "DevOps Team",
  "description": "Major rewrite with multi-language support",
  "breakingChanges": [
    "Changed output format from plain text to structured JSON",
    "Removed legacy {{user_name}} placeholder, use {{customer.name}} instead"
  ],
  "improvements": [
    "Added support for 12 languages",
    "Improved tone consistency",
    "Reduced average response time by 30%"
  ],
  "compatibilityNotes": "Requires API version 2.x or higher",
  "migrationGuide": "docs/migration-v1-to-v2.md"
}
```

**Version Increment Checklist:**
- [ ] Update version number following SemVer (MAJOR.MINOR.PATCH)
- [ ] Create new version directory
- [ ] Copy and modify files from previous version
- [ ] Create metadata.json documenting changes
- [ ] Update VERSION_MANIFEST.json
- [ ] Update deployment documentation
- [ ] Create migration guide if breaking changes
- [ ] Tag git commit with version number
- [ ] Update CHANGELOG.md

### Appendix E: Testing Patterns Reference

**Unit Test Examples:**

**Prompt Structure Test:**
```javascript
// tests/prompts/customer-support.test.js
const fs = require('fs');
const path = require('path');

describe('Customer Support Prompts', () => {
  const promptPath = 'prompts/customer-support/v2.0.0/ticket-response.md';
  let promptContent;

  beforeAll(() => {
    promptContent = fs.readFileSync(promptPath, 'utf8');
  });

  describe('Required Sections', () => {
    test('should have System Context section', () => {
      expect(promptContent).toMatch(/## System Context/);
    });

    test('should have Instructions section', () => {
      expect(promptContent).toMatch(/## Instructions/);
    });

    test('should have Output Format section', () => {
      expect(promptContent).toMatch(/## Output Format/);
    });

    test('should have Examples section', () => {
      expect(promptContent).toMatch(/## Examples/);
    });
  });

  describe('Token Limits', () => {
    test('should be within 4000 token limit', () => {
      const tokenCount = estimateTokens(promptContent);
      expect(tokenCount).toBeLessThan(4000);
    });
  });

  describe('Variable Placeholders', () => {
    test('should use valid placeholder syntax', () => {
      const placeholders = promptContent.match(/\{\{([^}]+)\}\}/g) || [];
      const validPlaceholders = [
        '{{customer.name}}',
        '{{customer.email}}',
        '{{ticket.id}}',
        '{{ticket.description}}',
        '{{ticket.priority}}'
      ];

      placeholders.forEach(placeholder => {
        expect(validPlaceholders).toContain(placeholder);
      });
    });

    test('should not have undefined placeholders', () => {
      expect(promptContent).not.toMatch(/\{\{undefined\}\}/);
      expect(promptContent).not.toMatch(/\{\{null\}\}/);
    });
  });
});
```

**Configuration Consistency Test:**
```javascript
// tests/configs/consistency.test.js
const yaml = require('js-yaml');
const fs = require('fs');

describe('Configuration Consistency', () => {
  let devConfig, stagingConfig, prodConfig;

  beforeAll(() => {
    devConfig = yaml.load(fs.readFileSync('configs/development.yml', 'utf8'));
    stagingConfig = yaml.load(fs.readFileSync('configs/staging.yml', 'utf8'));
    prodConfig = yaml.load(fs.readFileSync('configs/production.yml', 'utf8'));
  });

  test('all configs should have same structure', () => {
    const devKeys = Object.keys(devConfig).sort();
    const stagingKeys = Object.keys(stagingConfig).sort();
    const prodKeys = Object.keys(prodConfig).sort();

    expect(devKeys).toEqual(stagingKeys);
    expect(devKeys).toEqual(prodKeys);
  });

  test('production should use gpt-4 model', () => {
    expect(prodConfig.ai.model).toBe('gpt-4');
  });

  test('production rate limits should be higher than staging', () => {
    expect(prodConfig.rate_limits.requests_per_minute)
      .toBeGreaterThan(stagingConfig.rate_limits.requests_per_minute);
  });

  test('no API keys in configuration files', () => {
    const configString = JSON.stringify(prodConfig);
    expect(configString).not.toMatch(/sk-[a-zA-Z0-9]+/); // OpenAI key pattern
    expect(configString).not.toMatch(/api[_-]?key.*:\s*["'][^"']+["']/i);
  });
});
```

**Integration Test Example:**
```javascript
// tests/integration/workflow.test.js
describe('Ticket Response Workflow Integration', () => {
  test('should generate valid response with real prompt structure', async () => {
    const workflow = new TicketResponseWorkflow({
      promptVersion: '2.0.0',
      mockAI: true // Use mock instead of real API
    });

    const ticket = {
      id: 'TICKET-123',
      description: 'Cannot log in to account',
      priority: 'high',
      customer: {
        name: 'Jane Doe',
        email: 'jane@example.com'
      }
    };

    const response = await workflow.process(ticket);

    // Verify structure
    expect(response).toHaveProperty('response_text');
    expect(response).toHaveProperty('sentiment');
    expect(response).toHaveProperty('suggested_actions');

    // Verify content
    expect(response.response_text).toContain('Jane');
    expect(response.response_text.length).toBeGreaterThan(50);

    // Verify actions
    expect(Array.isArray(response.suggested_actions)).toBe(true);
  });
});
```

**Coverage Configuration (.nycrc.json):**
```json
{
  "all": true,
  "check-coverage": true,
  "lines": 80,
  "statements": 80,
  "functions": 80,
  "branches": 75,
  "include": [
    "src/**/*.js",
    "prompts/**/*.js",
    "workflows/**/*.js"
  ],
  "exclude": [
    "tests/**",
    "coverage/**",
    "node_modules/**"
  ],
  "reporter": [
    "text",
    "html",
    "json-summary"
  ]
}
```

### Appendix F: Troubleshooting Guide

**Common Issues and Solutions:**

**Issue: GitHub Actions workflow not triggering**
- **Symptom**: Pushed commit but workflow didn't run
- **Diagnosis**:
  - Check workflow file is in `.github/workflows/` directory
  - Verify YAML syntax is valid (use YAML linter)
  - Confirm trigger paths match changed files
  - Check if workflow is disabled in repository settings
- **Solution**:
  ```yaml
  # Ensure trigger paths are correct
  on:
    push:
      paths:
        - 'prompts/**'  # Must match actual directory structure
  ```

**Issue: Tests passing locally but failing in GitHub Actions**
- **Symptom**: `npm test` works locally, fails in CI
- **Diagnosis**:
  - Environment differences (Node version, OS)
  - Missing environment variables
  - Absolute vs relative path issues
  - Timing/race conditions
- **Solution**:
  ```yaml
  # Pin Node version to match local
  - uses: actions/setup-node@v4
    with:
      node-version: '20.x'  # Match your local version

  # Install exact dependencies
  - run: npm ci  # Use ci instead of install for reproducibility
  ```

**Issue: Coverage reporting fails**
- **Symptom**: Coverage check step fails or shows 0%
- **Diagnosis**:
  - Coverage tool not installed
  - Wrong coverage file path
  - Tests not generating coverage
- **Solution**:
  ```yaml
  # Generate coverage explicitly
  - name: Run tests with coverage
    run: npm run test -- --coverage

  # Verify coverage file exists
  - name: Check coverage exists
    run: |
      if [ ! -f coverage/coverage-summary.json ]; then
        echo "Coverage file not found"
        exit 1
      fi
  ```

**Issue: Token counting inaccurate**
- **Symptom**: Token count differs from actual API usage
- **Diagnosis**:
  - Using wrong tokenizer for model
  - Not accounting for message formatting
  - Special characters being counted incorrectly
- **Solution**:
  ```javascript
  // Use model-specific tokenizer
  const { encoding_for_model } = require('tiktoken');
  const encoding = encoding_for_model('gpt-4');
  const tokens = encoding.encode(promptContent);
  const count = tokens.length;
  encoding.free(); // Important: free memory
  ```

**Issue: Version manifest validation failing**
- **Symptom**: Deployment blocked due to manifest errors
- **Diagnosis**:
  - Manifest JSON syntax error
  - Referenced version doesn't exist in filesystem
  - Deployment environment not defined
- **Solution**:
  ```javascript
  // Validation script
  const manifest = require('./prompts/VERSION_MANIFEST.json');
  const fs = require('fs');

  Object.entries(manifest.prompts).forEach(([promptPath, versionInfo]) => {
    versionInfo.supported.forEach(version => {
      const path = `prompts/${promptPath}/v${version}`;
      if (!fs.existsSync(path)) {
        throw new Error(`Version ${version} declared in manifest but directory not found: ${path}`);
      }
    });
  });
  ```

**Issue: Secrets not available in workflow**
- **Symptom**: `${{ secrets.SECRET_NAME }}` is empty
- **Diagnosis**:
  - Secret not configured in repository/environment
  - Wrong environment specified
  - Typo in secret name (case-sensitive)
- **Solution**:
  ```yaml
  # Specify environment explicitly
  jobs:
    deploy:
      environment: production  # Required for environment secrets
      steps:
        - name: Use secret
          env:
            API_KEY: ${{ secrets.AI_API_KEY }}  # Exact case
          run: |
            if [ -z "$API_KEY" ]; then
              echo "Secret not found - check environment and secret name"
              exit 1
            fi
  ```

### Appendix G: Security Checklist

**Pre-Deployment Security Review:**

**Secrets & Credentials:**
- [ ] No API keys in code or configuration files
- [ ] All secrets stored in GitHub Secrets
- [ ] Production secrets use environment-specific scoping
- [ ] Secret rotation procedure documented
- [ ] No secrets in git history (check with `git log -p | grep -i 'api[_-]key'`)

**Code Scanning:**
- [ ] GitHub Advanced Security enabled (if available)
- [ ] Dependabot alerts reviewed and addressed
- [ ] No vulnerable dependencies (run `npm audit`)
- [ ] Code scanning alerts reviewed
- [ ] Secret scanning enabled

**Access Control:**
- [ ] Branch protection enabled on main/develop
- [ ] Required reviews configured (minimum 1)
- [ ] Direct pushes to main blocked
- [ ] Only authorized users can approve production deployments
- [ ] Repository permissions follow least-privilege principle

**Workflow Security:**
- [ ] Workflows use pinned action versions (`actions/checkout@v4` not `@main`)
- [ ] Third-party actions reviewed for security
- [ ] Workflow permissions follow least-privilege
- [ ] `pull_request_target` used carefully (security risk if misused)
- [ ] No `script` injection vulnerabilities in workflows

**Data Protection:**
- [ ] No PII (Personally Identifiable Information) in prompts or logs
- [ ] Customer data not logged in workflows
- [ ] Test data is synthetic/anonymized
- [ ] Compliance requirements documented (GDPR, HIPAA, etc.)

**Network Security:**
- [ ] API endpoints use HTTPS only
- [ ] Rate limiting configured
- [ ] IP allowlisting considered for production APIs
- [ ] Webhook signatures verified

**Audit Trail:**
- [ ] All production deployments require approval (audited)
- [ ] Version changes tracked in git history
- [ ] ACCESS_LOG for secret access reviewed regularly
- [ ] Failed deployment attempts monitored

**Incident Response:**
- [ ] Rollback procedure documented and tested
- [ ] Incident response runbook exists
- [ ] On-call rotation defined
- [ ] Security incident reporting process documented

### Appendix H: Branch Protection Configuration

**Recommended Settings for Main Branch:**

**Branch Protection Rules (via GitHub UI):**
1. Navigate to: Settings → Branches → Add Rule
2. Branch name pattern: `main`
3. Configure:

**Require pull request before merging:**
- ✅ Require approvals: 1
- ✅ Dismiss stale pull request approvals when new commits are pushed
- ✅ Require review from Code Owners (if CODEOWNERS file exists)

**Require status checks before merging:**
- ✅ Require status checks to pass before merging
- ✅ Require branches to be up to date before merging
- Required checks:
  - `validate-prompts`
  - `unit-tests`
  - `integration-tests`
  - `coverage-check`

**Require conversation resolution before merging:**
- ✅ All conversations must be resolved

**Require signed commits:**
- Consider enabling for high-security projects

**Require linear history:**
- ✅ Prevent merge commits (enforce rebase or squash)

**Restrict who can push to matching branches:**
- ✅ Restrict pushes that create matching branches
- ✅ Add repository administrators as exception (for emergencies)

**Rules applied to administrators:**
- ✅ Include administrators (recommended - no one bypasses)

**Alternative (via API):**
```bash
# Configure branch protection via GitHub API
curl -X PUT \
  -H "Authorization: token YOUR_TOKEN" \
  -H "Accept: application/vnd.github.v3+json" \
  https://api.github.com/repos/OWNER/REPO/branches/main/protection \
  -d '{
    "required_status_checks": {
      "strict": true,
      "contexts": ["validate-prompts", "unit-tests", "integration-tests"]
    },
    "enforce_admins": true,
    "required_pull_request_reviews": {
      "dismissal_restrictions": {},
      "dismiss_stale_reviews": true,
      "require_code_owner_reviews": false,
      "required_approving_review_count": 1
    },
    "restrictions": null,
    "required_linear_history": true,
    "allow_force_pushes": false,
    "allow_deletions": false
  }'
```

### Appendix I: Performance Optimization

**Workflow Optimization Strategies:**

**1. Cache Dependencies:**
```yaml
- name: Cache node modules
  uses: actions/cache@v4
  with:
    path: ~/.npm
    key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}
    restore-keys: |
      ${{ runner.os }}-node-
```

**2. Run Jobs in Parallel:**
```yaml
jobs:
  validate:
    runs-on: ubuntu-latest
    steps: [...]

  unit-tests:
    runs-on: ubuntu-latest
    steps: [...]  # Runs parallel to validate

  integration-tests:
    needs: [validate, unit-tests]  # Runs after both complete
    steps: [...]
```

**3. Matrix Testing:**
```yaml
jobs:
  test:
    strategy:
      matrix:
        node-version: [18, 20]
        os: [ubuntu-latest, windows-latest]
    runs-on: ${{ matrix.os }}
    steps:
      - uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node-version }}
```

**4. Fail Fast:**
```yaml
jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - name: Quick syntax check
        run: npm run lint:quick  # Fast check first

      - name: Full validation
        if: success()
        run: npm run validate:all  # Comprehensive check only if quick check passes
```

**5. Conditional Job Execution:**
```yaml
jobs:
  deploy:
    if: github.ref == 'refs/heads/main' && github.event_name == 'push'
    runs-on: ubuntu-latest
    steps: [...]  # Only runs on main branch pushes
```

**Performance Benchmarks:**
- Validation workflow: < 2 minutes
- Full test suite: < 5 minutes
- Deployment to staging: < 3 minutes
- Complete pipeline (commit to staging): < 10 minutes

**Optimization Checklist:**
- [ ] Dependencies cached
- [ ] Independent jobs run in parallel
- [ ] Fast checks run before slow ones
- [ ] Matrix builds used for cross-platform testing
- [ ] Conditional execution prevents unnecessary runs
- [ ] Artifacts used to share data between jobs (not re-computing)

---

## Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | 2026-01-02 | Initial presentation created | AI Practitioner Training Team |
| 2.0 | 2026-01-03 | Enhanced with comprehensive slide structure, BACKGROUND sections, Sources, Implementation Guidance, and expanded appendices | Claude |
