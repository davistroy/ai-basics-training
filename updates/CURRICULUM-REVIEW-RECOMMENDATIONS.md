# Curriculum Review: Comprehensive Recommendations Plan

**Review Date:** 2026-01-01
**Reviewer:** Claude (AI Assistant)
**Scope:** Complete curriculum evaluation for coverage, coherence, and consistency

---

## Executive Summary

The AI Practitioner Training Curriculum is a **well-structured, comprehensive program** with 211 markdown files totaling approximately 1.2 MB of educational content. The curriculum demonstrates strong pedagogical design with consistent patterns across the three main blocks and thoughtful progression from prompting fundamentals through autonomous agent development.

**Overall Assessment:** The curriculum is production-ready with several targeted improvements recommended.

| Category | Status | Priority Items |
|----------|--------|----------------|
| **Coverage** | Excellent | Minor gaps in marketing materials |
| **Coherence** | Very Good | Few broken cross-references to fix |
| **Consistency** | Good | Module 5 structure deviation, time inconsistencies |

---

## Priority Classification

- **P1 - Critical:** Must fix before delivery; breaks functionality or creates confusion
- **P2 - High:** Should fix soon; impacts consistency or professionalism
- **P3 - Medium:** Recommended fix; improves quality
- **P4 - Low:** Nice to have; polish items

---

## P1 - CRITICAL ISSUES

### 1.1 Module 5 Structure Deviation
**File:** `materials/advanced-modules/module-5-github-devops.md`
**Lines:** 24-25, 137-239

**Issue:** Module 5 (GitHub DevOps) uses a completely different structural format than all other advanced modules. It uses "Workshop 1.1, 1.2, 1.3" format with exercises mixed within workshops, rather than the standard:
- Week 1 header
- Entry/Exit Criteria
- Workshop Content (45 min with timed segments)
- Self-Paced Exercises section

**Impact:** Creates confusion and inconsistency; violates the pattern documented in CLAUDE.md.

**Recommendation:** Restructure Module 5 to match the standard format used in Modules 1-4 and 6-10:
```markdown
## Week 1: GitHub Actions & CI/CD Fundamentals

### Entry Criteria
- [ ] [criteria...]

### Exit Criteria
- [ ] [criteria...]

### Workshop Content (45 minutes)
**Segment 1: [Topic] (12 min)**
...

### Self-Paced Exercises (75 minutes total)
**Exercise 1.1: [Name] (X minutes)**
...
```

---

### 1.2 Broken README Navigation Reference
**File:** `README.md`
**Line:** 345

**Issue:** The directory tree shows `facilitator-guide.md` at the repository root, but this file is actually located at `archive/facilitator-guide.md`.

**Impact:** Users looking for the facilitator guide won't find it; creates confusion about repository structure.

**Recommendation:** Update the directory tree in README.md to either:
- Move the reference to the archive section, OR
- Update the path to `archive/facilitator-guide.md`

---

### 1.3 Broken Block Main File Navigation Links
**Files:**
- `materials/block-1/block-1.md` (lines 9, 2634)
- `materials/block-2/block-2.md` (lines 9, 3198)
- `materials/block-3/block-3.md` (lines 9, 3655)

**Issue:** Navigation headers reference `[← README](README.md)` but README.md is in the repository root, not the materials directory.

**Impact:** Broken links in curriculum navigation.

**Recommendation:** Change to `[← README](../../README.md)` in all three files (both at top and bottom of each file).

---

## P2 - HIGH PRIORITY ISSUES

### 2.1 Incomplete Marketing Materials
**Files:**
- `marketing/block2-sales-infographic.md` (28 lines)
- `marketing/block3-sales-infographic.md` (28 lines)

**Issue:** Block 1 marketing infographic has 392 lines with comprehensive specification (design guidelines, ROI calculations, visual specifications, messaging hierarchy). Blocks 2 and 3 are minimal stubs with only headlines and bullet points.

**Impact:** Inconsistent marketing assets; Blocks 2-3 lack the detail needed for actual infographic creation.

**Recommendation:** Expand Block 2 and Block 3 infographics following Block 1's detailed specification format, including:
- Visual design guidelines (color palette, typography)
- Detailed ROI calculations
- Layout specifications
- Complete messaging hierarchy
- Call-to-action sections

---

### 2.2 Advanced Module Time Inconsistencies
**Files:**
- `materials/advanced-modules/module-3-json-schema.md` (line 3)
- `materials/advanced-modules/module-4-visual-documentation.md` (line 3)

**Issue:** These two modules specify "60 min homework" while all other modules (1, 2, 5-10) specify "75 min homework."

**Current:** `## **2 Weeks | 45 min live + 60 min homework per week**`
**Standard:** `## **2 Weeks | 45 min live + 75 min homework per week**`

**Impact:** Creates confusion about time commitments; inconsistent curriculum template.

**Recommendation:** Either:
1. Align both to 75 min for consistency, OR
2. Add explicit documentation explaining why these modules require less homework time

---

### 2.3 Module 4 Prerequisite Inconsistency
**File:** `materials/advanced-modules/module-4-visual-documentation.md`
**Lines:** 7-12

**Issue:** Module 4 only requires "Block 1 Certification" while all other advanced modules require Block 3 (or Block 2 for Module 3). This makes Module 4 an outlier in the "advanced" module sequence.

| Module | Prerequisite |
|--------|--------------|
| 1, 2, 5-10 | Block 3 Certification |
| 3 | Block 2 Certification |
| **4** | **Block 1 Certification** (outlier) |

**Impact:** A Block 1 graduate may be unprepared for advanced architectural concepts.

**Recommendation:** Either:
1. Raise Module 4 prerequisites to Block 2 minimum, OR
2. Explicitly document why this module has lower prerequisites, OR
3. Reclassify Module 4 as "intermediate" rather than "advanced"

---

### 2.4 Block 3 Week 7 Appendix Reference Error
**File:** `materials/block-3/week-7/week-7.md`
**Line:** 444

**Issue:** References `#appendix-n` for the Block 3 Capstone Rubric, but the actual appendix is **Appendix P**, not N.

**Current:** `[Block 3 Capstone Rubric](#appendix-n)`
**Should be:** `[Block 3 Capstone Rubric](#appendix-p-block-3-capstone-rubric)`

**Impact:** Broken anchor link; users can't navigate to the rubric.

**Recommendation:** Update the anchor reference to `#appendix-p-block-3-capstone-rubric` or the correct anchor ID from block-3.md.

---

## P3 - MEDIUM PRIORITY ISSUES

### 3.1 Variable Time Exercises Not Defined
**Files:**
- `materials/block-1/week-7/week-7.md` (line 237)
- `materials/block-2/week-7/week-7.md`
- `materials/block-3/week-7/week-7.md`

**Issue:** Week 7 in all three blocks includes exercises with "Variable Time" or "Variable - as needed" without clear guidance on expected duration or what constitutes completion.

**Impact:** Participants and instructors lack clarity on time expectations for capstone preparation.

**Recommendation:** For each variable-time exercise, add:
- Estimated minimum time
- Estimated maximum time
- Clear completion criteria
- Example: "Variable (30-90 minutes depending on number of templates to review)"

---

### 3.2 Prerequisites Reference Path
**File:** `materials/block-1/week-1/week-1.md`
**Line:** 10

**Issue:** References `prerequisites.md` but should use relative path `../../block-0/prerequisites.md`.

**Impact:** Link may not resolve correctly depending on context.

**Recommendation:** Update to proper relative path: `../../block-0/prerequisites.md`

---

### 3.3 Module 3 Exercise Assumption
**File:** `materials/advanced-modules/module-3-json-schema.md`
**Lines:** 308-309

**Issue:** Exercise 1.2 references `style.json` assuming participants have this from Block 2, but entry criteria doesn't explicitly verify this file exists.

**Impact:** Participants without a style.json may be confused.

**Recommendation:** Add note: "If you don't have an existing style.json from Block 2, use the schema provided in this exercise to create one from scratch, or use the provided example."

---

### 3.4 Module 6 Missing Presentation Template
**File:** `materials/advanced-modules/module-6-enterprise-architecture.md`
**Lines:** 895-905

**Issue:** Exercise 2.3 requires "Executive presentation deck" as a deliverable but provides no template, outline, or guidance for creating the presentation.

**Impact:** Inconsistent with other exercises that provide detailed templates.

**Recommendation:** Add presentation outline showing:
- Expected sections
- Timing guidance
- Key points to cover
- Slide structure recommendations

---

### 3.5 Archive Presentation Path from Block 3
**File:** `materials/block-3/block-3.md`
**Line:** 29

**Issue:** References `archive/presentation.md` but should use `../../archive/presentation.md` as a relative path from the block-3 directory.

**Impact:** Link may not resolve correctly.

**Recommendation:** Update to proper relative path: `../../archive/presentation.md`

---

## P4 - LOW PRIORITY (POLISH ITEMS)

### 4.1 Glossary Expansion
**File:** `glossary.md`

**Issue:** Current glossary has 13 terms. Could be expanded to include additional terms used throughout the curriculum.

**Suggested additions:**
- Circuit Breaker Pattern
- Context Window
- Token (in AI context)
- Checkpoint (in agent context)
- Graceful Degradation
- Bulkhead Pattern
- Setup Agent / Worker Agent

---

### 4.2 Marketing Materials Not Linked in README
**File:** `README.md`

**Issue:** The Quick Navigation section doesn't link to marketing materials for Blocks 2 and 3.

**Recommendation:** After completing item 2.1, add links to the marketing section of README.

---

### 4.3 Segment Numbering Consistency
**Files:** Various instructor-guide.md files

**Issue:** Minor inconsistency in how workshop segments are labeled:
- Some use "Opening, Segment 1, 2, 3, Closing"
- Some use "Segment 1, 2, 3, 4, 5"

**Impact:** Minimal; timing is correct in all cases.

**Recommendation:** Standardize labeling in a future polish pass. Not urgent.

---

### 4.4 Advanced Module Dependency Documentation
**Issue:** No documentation exists showing which advanced modules can be taken independently vs. which benefit from taking others first.

**Recommendation:** Create a simple dependency diagram or table showing:
- Independent modules (can be taken in any order after Block 3)
- Recommended sequences (e.g., Module 1 before Module 2)
- Complementary pairs

---

### 4.5 Implementation Plan Phase 3 Items
**File:** `updates/IMPLEMENTATION-PLAN-2026-01-01.md`

**Issue:** Phase 3 (Minor Polish) items were not completed per the implementation plan. These include:
- Advanced module quick reference cards
- Standardized date formats
- Tool name capitalization consistency
- MCP terminology standardization

**Recommendation:** Review Phase 3 items and complete as time permits.

---

## ITEMS VERIFIED AS CORRECT

The following items were checked and found to be properly implemented:

1. **Certification Thresholds:** Block 1-2 at 22/40 (55%), Block 3 at 34/40 (85%) - correctly documented
2. **Appendix Lettering:** Block 1 (A-I), Block 2 (J-O), Block 3 (P-S) - non-overlapping and consistent
3. **Weekly Structure:** All 24 weeks follow consistent Entry Criteria → Workshop → Exercises → Exit Criteria pattern
4. **Workshop Timing:** All workshops correctly total 45 minutes
5. **Exercise Timing:** Blocks 1-2 at 60 minutes, Block 3 at 75 minutes (correctly reflects increased complexity)
6. **File Completeness:** All expected files present (4 files per week × 8 weeks × 3 blocks + supporting materials)
7. **Framework Naming:** ASK-CONTEXT-CONSTRAINTS-EXAMPLE, Two-Agent Pattern, LLM-as-Judge consistent throughout
8. **Checkpoints:** Properly aligned with block exit criteria
9. **Quick Reference Cards:** Accurately summarize key concepts from each block

---

## SUMMARY TABLE

| ID | Issue | File(s) | Priority | Effort |
|----|-------|---------|----------|--------|
| 1.1 | Module 5 structure deviation | module-5-github-devops.md | P1 | High |
| 1.2 | Broken facilitator-guide reference | README.md | P1 | Low |
| 1.3 | Broken README navigation links | block-1/2/3.md | P1 | Low |
| 2.1 | Incomplete marketing materials | block2/3-sales-infographic.md | P2 | High |
| 2.2 | Module time inconsistencies | module-3/4.md | P2 | Low |
| 2.3 | Module 4 prerequisite inconsistency | module-4.md | P2 | Low |
| 2.4 | Appendix reference error | block-3/week-7.md | P2 | Low |
| 3.1 | Variable time exercises undefined | week-7.md (all blocks) | P3 | Medium |
| 3.2 | Prerequisites relative path | block-1/week-1.md | P3 | Low |
| 3.3 | Module 3 assumption | module-3.md | P3 | Low |
| 3.4 | Module 6 missing template | module-6.md | P3 | Medium |
| 3.5 | Archive presentation path | block-3.md | P3 | Low |
| 4.1 | Glossary expansion | glossary.md | P4 | Low |
| 4.2 | Marketing links in README | README.md | P4 | Low |
| 4.3 | Segment numbering consistency | Various | P4 | Medium |
| 4.4 | Advanced module dependencies | New document | P4 | Low |
| 4.5 | Phase 3 polish items | Various | P4 | Medium |

---

## RECOMMENDED EXECUTION ORDER

### Phase 1: Critical Fixes (Immediate)
1. Fix P1 items (1.1, 1.2, 1.3)
2. Fix P2 link/reference issues (2.4)

### Phase 2: High Priority (This Week)
3. Address Module 5 restructuring (1.1 - requires significant work)
4. Decide on Module 3/4 time and prerequisite standardization (2.2, 2.3)
5. Plan Block 2/3 marketing completion (2.1)

### Phase 3: Medium Priority (As Time Permits)
6. Complete P3 items
7. Complete Block 2/3 marketing materials

### Phase 4: Polish (Future)
8. Complete P4 items during next curriculum update cycle

---

## NOTES

- **Block 0→1 Checkpoint:** Intentionally excluded per stakeholder request (documented in IMPLEMENTATION-PLAN-2026-01-01.md line 819)
- **XXX Placeholders:** Most instances are intentional templates for participants to fill in (ROI calculations, example values) - not errors
- **TODO/FIXME markers:** Found instances are in test examples or template instructions - not incomplete content

---

**Document Status:** Ready for Review
**Next Steps:** Stakeholder approval required before execution
