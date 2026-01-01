# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an **AI Practitioner Training Curriculum** - a 24-week professional development program for consulting professionals. It transforms ad-hoc AI users into skilled AI Automation Architects through three progressive blocks plus five optional advanced modules.

**This is a documentation-only repository** - no build, test, or lint commands. All content is Markdown files.

## Repository Structure

```
block-0/           Prerequisites and self-assessment
block-1/           AI Prompting Mastery (8 weeks) - Foundation skills
block-2/           AI Workflow Engineering (8 weeks) - Automation and MCP
block-3/           AI Automation Architecture (8 weeks) - Autonomous agents
advanced-modules/  5 optional post-Block 3 modules (2 weeks each)
checkpoints/       Inter-block skill verification assessments
quick-reference/   One-page reference cards per block
templates/         Reusable templates for instructors and participants
feedback/          Cohort feedback collection
marketing/         Sales and marketing materials
updates/           Changelog and curriculum updates
archive/           Historical documents and presentations
```

## Content Architecture

### Block Structure
Each block follows a consistent pattern:
- Main curriculum file: `block-N/block-N.md` (comprehensive, 78-92KB each)
- Weekly breakdown: `block-N/week-N/week-N.md`
- Each week has: Entry Criteria → Workshop Content (45 min) → Self-Paced Exercises (60-90 min) → Exit Criteria

### Key Frameworks Referenced Throughout
- **ASK-CONTEXT-CONSTRAINTS-EXAMPLE**: Block 1 prompting framework
- **LLM-as-Judge Pattern**: Quality iteration mechanism
- **Two-Agent Pattern**: Core Block 3 multi-agent architecture
- **Domain Memory Meta-Framework**: Three Pillars (Explicit Goals, Progress Records, Operating Procedures)

### Appendices Convention
Each block includes lettered appendices with templates:
- Block 1: Appendices A-I
- Block 2: Appendices J-O
- Block 3: Appendices N-Q (note: some letter overlap)

## Working with This Repository

### When Adding or Modifying Curriculum Content
- Maintain the consistent weekly structure (Entry Criteria, Workshop Content with timed segments, Exercises, Exit Criteria)
- Cross-reference related appendices using letter codes
- Update both the main block file and weekly breakdown files when making changes
- Time segments in workshops: 4 segments totaling ~42 minutes (leaving buffer)

### Assessment Standards
- Quality rubrics use 5-point scale: 5-Excellent, 4-Good, 3-Adequate, 2-Poor, 1-Missing
- Certification threshold: 22/40 points (55%)
- Each block ends with a capstone project

### File Naming Conventions
- Weekly files: `week-N.md` in `block-N/week-N/` directories
- Templates use descriptive names with hyphens: `weekly-instructor-guide-template.md`
- Changelog: `CHANGELOG-YYYY-MM-DD.md` in updates/

## Program Progression

```
Block 1 (Prompting) → Block 2 (Workflows) → Block 3 (Agents) → Advanced Modules
     ↓                      ↓                     ↓
  Practitioner          Engineer              Architect
  Certification       Certification         Certification
```

Prerequisites between blocks are enforced via checkpoint assessments in `checkpoints/`.

## Owner

Troy Davis (troy.davis@hotmail.com)
Repository: https://github.com/davistroy/ai-basics-training
