# **Advanced Module 9: AI Security Fundamentals**
## **Session 2: Security Assessment & Hardening**

**Duration:** 45 min live workshop + 75 min self-paced exercises

-----

## **Entry Criteria**

- [ ] Threat analysis completed
- [ ] Prompt injection defenses implemented
- [ ] Least privilege configuration applied
- [ ] Understanding of defensive patterns

## **Exit Criteria**

- [ ] Security assessment methodology understood
- [ ] AI system security assessment conducted
- [ ] Red teaming basics applied
- [ ] Multi-agent security architecture designed
- [ ] Module capstone (Security Assessment Report) completed

-----

## **Workshop Content (45 minutes)**

### **Segment 1: Data Security & PII Handling (12 min)**

- **Data security risks in AI systems:**
  - Training data leakage
  - Context window exposure
  - Output containing sensitive data
  - Logging sensitive information
  - Tool-mediated data access

- **PII handling framework:**
  ```
  INPUT STAGE:
    ├── Detect PII in input
    ├── Classify sensitivity level
    ├── Apply handling rules
    └── Log (without PII)

  PROCESSING STAGE:
    ├── Minimize PII in context
    ├── Use references, not values
    ├── Apply data masking
    └── Scope access to need

  OUTPUT STAGE:
    ├── Scan for PII leakage
    ├── Redact before display
    ├── Audit trail creation
    └── Secure deletion
  ```

- **PII detection patterns:**

  | PII Type | Detection Pattern | Handling |
  |----------|-------------------|----------|
  | SSN | XXX-XX-XXXX format | Redact |
  | Credit Card | 16-digit patterns | Redact |
  | Email | user@domain format | Mask |
  | Phone | Various formats | Mask |
  | Name + DOB | NER + date | Flag |

- **Data leakage prevention:**
  - Output scanning before delivery
  - Blocking sensitive data patterns
  - Monitoring for unusual data access
  - Restricting data export capabilities
  - Audit logging for compliance

### **Segment 2: Security Assessment Methodology (12 min)**

- **Assessment framework:**
  ```
  PHASE 1: DISCOVERY
    └── Inventory all AI components
    └── Map data flows
    └── Identify integration points

  PHASE 2: THREAT MODELING
    └── Identify threat actors
    └── Map attack vectors
    └── Assess vulnerabilities

  PHASE 3: CONTROL EVALUATION
    └── Review existing controls
    └── Test control effectiveness
    └── Identify gaps

  PHASE 4: TESTING
    └── Controlled attack simulation
    └── Defense validation
    └── Edge case exploration

  PHASE 5: REPORTING
    └── Document findings
    └── Prioritize risks
    └── Recommend remediations
  ```

- **Assessment checklist categories:**

  | Category | Assessment Focus |
  |----------|------------------|
  | **Architecture** | Secure design, isolation, defense in depth |
  | **Access Control** | Authentication, authorization, least privilege |
  | **Data Protection** | Encryption, handling, retention |
  | **Input Security** | Validation, sanitization, injection defense |
  | **Output Security** | Filtering, validation, leakage prevention |
  | **Monitoring** | Logging, alerting, incident detection |
  | **Tool Security** | MCP config, tool permissions, sandboxing |
  | **Compliance** | Regulatory requirements, policies |

- **Documenting findings:**
  ```markdown
  ## Finding: [ID] - [Title]

  **Severity:** Critical/High/Medium/Low
  **Category:** [Category]

  **Description:**
  [What was found]

  **Risk:**
  [What could happen if exploited]

  **Evidence:**
  [How it was discovered]

  **Recommendation:**
  [How to fix]

  **Priority:** Immediate/Short-term/Medium-term
  ```

### **Segment 3: Red Teaming Basics (12 min)**

- **What is AI red teaming?**
  - Controlled adversarial testing
  - Thinking like an attacker
  - Finding vulnerabilities before attackers do
  - NOT about breaking things in production

- **Red team methodology:**
  ```
  1. SCOPE DEFINITION
     - What systems are in scope?
     - What attack types to simulate?
     - What are the rules of engagement?

  2. RECONNAISSANCE
     - Understand system capabilities
     - Identify potential weaknesses
     - Map attack surface

  3. ATTACK SIMULATION
     - Attempt defined attack scenarios
     - Document techniques and results
     - Capture evidence

  4. REPORTING
     - Document successful attacks
     - Explain attack paths
     - Recommend defenses
  ```

- **Common AI red team scenarios:**

  | Scenario | Objective | Technique |
  |----------|-----------|-----------|
  | Prompt injection | Override instructions | Direct/indirect injection |
  | Data extraction | Exfiltrate sensitive data | Clever questioning |
  | Guardrail bypass | Get prohibited output | Jailbreak techniques |
  | Privilege escalation | Access restricted tools | Tool confusion attacks |
  | Denial of service | Exhaust resources | Token bombing, loops |

- **Ethical guidelines:**
  - Always have authorization
  - Document everything
  - Never test on production without safeguards
  - Report findings responsibly
  - Focus on defense improvement, not just breaking things

### **Segment 4: Multi-Agent Security Architecture (9 min)**

- **Security challenges in multi-agent systems:**
  - Agent-to-agent trust
  - Shared resource access
  - Attack propagation
  - Coordination vulnerabilities
  - Complex attack surfaces

- **Secure multi-agent architecture:**
  ```
  ┌─────────────────────────────────────────────────────────────┐
  │                    SECURITY PERIMETER                       │
  │  ┌─────────────────────────────────────────────────────┐   │
  │  │              ORCHESTRATOR (Trusted)                  │   │
  │  │  - Access control enforcement                        │   │
  │  │  - Inter-agent message validation                    │   │
  │  │  - Resource allocation                               │   │
  │  │  - Audit logging                                     │   │
  │  └─────────────────────────────────────────────────────┘   │
  │              │                │                │            │
  │              ↓                ↓                ↓            │
  │  ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐ │
  │  │   AGENT A       │ │   AGENT B       │ │   AGENT C       │ │
  │  │   (Sandbox A)   │ │   (Sandbox B)   │ │   (Sandbox C)   │ │
  │  │   Scope: Read   │ │   Scope: Write  │ │   Scope: API    │ │
  │  └─────────────────┘ └─────────────────┘ └─────────────────┘ │
  │                                                              │
  │  ┌──────────────────────────────────────────────────────┐  │
  │  │                SHARED SECURE STORAGE                  │  │
  │  │  - Access control per agent                          │  │
  │  │  - Audit trail                                       │  │
  │  │  - Encryption at rest                                │  │
  │  └──────────────────────────────────────────────────────┘  │
  └─────────────────────────────────────────────────────────────┘
  ```

- **Inter-agent security controls:**
  - Validate all messages between agents
  - Prevent agent impersonation
  - Limit information sharing to need-to-know
  - Monitor for abnormal communication patterns
  - Circuit breakers for compromised agents

- **Zero trust for agents:**
  - Verify every agent action
  - Assume any agent could be compromised
  - Continuous validation, not one-time auth
  - Micro-segmentation of capabilities

-----

## **Self-Paced Exercises (75 minutes total)**

### **Exercise 2.1: Data Security Implementation (25 minutes)**

*Implement PII handling and data protection controls*

```markdown
# Data Security Implementation

## System: [Your Agent System Name]

### Data Inventory

| Data Type | Classification | Location | Access Method |
|-----------|---------------|----------|---------------|
| User queries | Internal | Memory | Direct |
| Documents | Confidential | Filesystem | Tool |
| API responses | Internal | Memory | Tool |
| Output logs | Internal | Log files | System |

### PII Detection Configuration

```json
{
  "pii_detection": {
    "enabled": true,
    "patterns": {
      "ssn": {
        "regex": "\\b\\d{3}-\\d{2}-\\d{4}\\b",
        "handling": "redact"
      },
      "credit_card": {
        "regex": "\\b\\d{4}[- ]?\\d{4}[- ]?\\d{4}[- ]?\\d{4}\\b",
        "handling": "redact"
      },
      "email": {
        "regex": "\\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\\.[A-Z|a-z]{2,}\\b",
        "handling": "mask"
      },
      "phone": {
        "regex": "\\b(\\+1)?[- .]?\\(?\\d{3}\\)?[- .]?\\d{3}[- .]?\\d{4}\\b",
        "handling": "mask"
      }
    },
    "scan_points": ["input", "tool_response", "output"],
    "logging": {
      "log_detections": true,
      "log_pii_values": false
    }
  }
}
```

### Data Handling Rules

| Data Classification | Handling Rule | Retention |
|--------------------|---------------|-----------|
| Public | No restrictions | 30 days |
| Internal | Mask in logs | 7 days |
| Confidential | Redact, no logging | Session only |
| Restricted | Block processing | N/A |

### Output Filtering

```json
{
  "output_filter": {
    "scan_enabled": true,
    "block_patterns": [
      "password\\s*[:=]\\s*\\S+",
      "api[_-]?key\\s*[:=]\\s*\\S+",
      "secret\\s*[:=]\\s*\\S+"
    ],
    "on_detection": "redact_and_warn",
    "audit_log": true
  }
}
```

### Data Leakage Prevention

| Control | Implementation | Status |
|---------|---------------|--------|
| Output scanning | PII regex filter | Implemented |
| Tool result filtering | Sensitive data redaction | Implemented |
| Export restrictions | Disable file download of sensitive data | Pending |
| Logging sanitization | Remove PII before logging | Implemented |

### Verification Testing

| Test | Data Type | Expected | Result |
|------|-----------|----------|--------|
| SSN in input | 123-45-6789 | Detected, redacted | |
| SSN in output | Model generates SSN | Blocked | |
| Credit card | 4111-1111-1111-1111 | Redacted | |
| Password in output | password: secret123 | Redacted | |
```

**Deliverable:** `data-security-config.md` + implementation

-----

### **Exercise 2.2: Security Assessment (25 minutes)**

*Conduct a security assessment of an AI system*

```markdown
# AI Security Assessment Report

## Assessment Information
- **System:** [System Name]
- **Assessment Date:** [Date]
- **Assessor:** [Name]
- **Scope:** [What was assessed]

### Executive Summary

[2-3 paragraphs summarizing the assessment, key findings, and overall risk posture]

**Overall Risk Rating:** Critical/High/Medium/Low

### System Overview

**Architecture:**
- Agent type: [Single/Multi-agent]
- Tools/MCP servers: [List]
- Data access: [What data can be accessed]
- User base: [Who uses the system]

**Data Flow Diagram:**
```
[User] ──→ [Input Processing] ──→ [Agent] ──→ [Tools]
                                     │
                                     ↓
                               [Output Processing] ──→ [User]
```

### Assessment Findings

#### Finding 1: [Critical/High] - Insufficient Input Validation
- **Category:** Input Security
- **Description:** User input is passed directly to the agent without validation for injection patterns.
- **Risk:** Attackers could inject malicious instructions that override agent behavior.
- **Evidence:** Test input "ignore previous instructions" was not filtered.
- **Recommendation:** Implement input validation layer with pattern blocking.
- **Priority:** Immediate

#### Finding 2: [High] - Overly Permissive Tool Access
- **Category:** Access Control
- **Description:** Filesystem MCP has full read/write access to entire system.
- **Risk:** Compromised agent could access or modify sensitive files.
- **Evidence:** Agent successfully read /etc/passwd during testing.
- **Recommendation:** Scope filesystem access to required directories only.
- **Priority:** Immediate

#### Finding 3: [Medium] - No Output Filtering
- **Category:** Output Security
- **Description:** Agent outputs are not scanned for sensitive data before display.
- **Risk:** Accidental exposure of PII or credentials in responses.
- **Evidence:** Agent included raw API key in troubleshooting response.
- **Recommendation:** Implement output scanning with sensitive pattern detection.
- **Priority:** Short-term

#### Finding 4: [Continue documenting findings]

### Assessment Summary

| Category | Findings | Critical | High | Medium | Low |
|----------|----------|----------|------|--------|-----|
| Architecture | 2 | 0 | 1 | 1 | 0 |
| Access Control | 3 | 1 | 1 | 1 | 0 |
| Data Protection | 2 | 0 | 1 | 1 | 0 |
| Input Security | 2 | 1 | 1 | 0 | 0 |
| Output Security | 2 | 0 | 1 | 1 | 0 |
| Monitoring | 1 | 0 | 0 | 1 | 0 |
| **Total** | **12** | **2** | **5** | **5** | **0** |

### Remediation Roadmap

| Priority | Finding | Remediation | Effort | Owner |
|----------|---------|-------------|--------|-------|
| Immediate | Input validation | Implement validation layer | 2 days | |
| Immediate | Tool permissions | Scope filesystem access | 1 day | |
| Short-term | Output filtering | Add PII detection | 3 days | |
| Short-term | Logging | Add security logging | 2 days | |
| Medium-term | Architecture | Add defense layers | 1 week | |
```

**Deliverable:** `security-assessment-report.md`

-----

### **Exercise 2.3: Module Capstone - Comprehensive Security Package (25 minutes)**

*Complete your AI security assessment and hardening package*

```markdown
# AI Security Assessment - Complete Package

## System: [Your Agent System Name]
## Prepared By: [Your Name]
## Date: [Date]

---

## Part 1: Executive Summary

### Assessment Overview
[Summary of the assessment conducted, methodology used, and scope]

### Key Findings
1. [Most critical finding]
2. [Second most critical]
3. [Third most critical]

### Risk Summary
| Risk Level | Count | Key Risks |
|------------|-------|-----------|
| Critical | X | [Brief description] |
| High | X | [Brief description] |
| Medium | X | [Brief description] |
| Low | X | [Brief description] |

### Recommendations Summary
1. **Immediate (0-7 days):** [Top priority actions]
2. **Short-term (1-4 weeks):** [Important improvements]
3. **Medium-term (1-3 months):** [Strategic enhancements]

---

## Part 2: Threat Analysis Summary

### Threat Landscape
[Reference threat-analysis.md from Exercise 1.1]

### Top Threats by Risk Score
| Rank | Threat | Likelihood | Impact | Score |
|------|--------|------------|--------|-------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |

---

## Part 3: Security Controls Implemented

### Defensive Patterns
| Control | Status | Effectiveness |
|---------|--------|---------------|
| Input validation | Implemented | High |
| Prompt hardening | Implemented | Medium |
| Output filtering | Implemented | High |
| Least privilege | Implemented | High |
| Sandboxing | Partial | Medium |
| Human-in-the-loop | Planned | N/A |

### Configuration Artifacts
- `prompt-injection-defenses.md` - Input validation and prompt security
- `least-privilege-config.md` - Tool and MCP security configuration
- `data-security-config.md` - PII handling and data protection

---

## Part 4: Security Architecture Recommendations

### Current State
[Diagram of current security architecture]

### Recommended Target State
```
┌────────────────────────────────────────────────────────────────┐
│                      SECURITY CONTROLS                          │
│                                                                  │
│  INPUT LAYER          PROCESSING LAYER       OUTPUT LAYER       │
│  ┌──────────┐         ┌──────────────┐       ┌──────────┐      │
│  │Validation│         │   AGENT      │       │ Scanning │      │
│  │Sanitize  │────────→│  (Sandboxed) │──────→│ Filtering│      │
│  │Rate Limit│         │   Monitored  │       │ Audit    │      │
│  └──────────┘         └──────────────┘       └──────────┘      │
│                              │                                   │
│                              ↓                                   │
│                       ┌──────────────┐                          │
│                       │TOOLS (Scoped)│                          │
│                       │Circuit Break │                          │
│                       │Validated I/O │                          │
│                       └──────────────┘                          │
│                                                                  │
│  MONITORING: Security logging, alerting, anomaly detection      │
└────────────────────────────────────────────────────────────────┘
```

### Implementation Roadmap

| Phase | Timeline | Deliverables |
|-------|----------|--------------|
| Phase 1: Foundation | Week 1-2 | Input validation, basic output filtering |
| Phase 2: Hardening | Week 3-4 | Least privilege, sandboxing |
| Phase 3: Monitoring | Week 5-6 | Security logging, alerting |
| Phase 4: Advanced | Week 7-8 | Red team testing, continuous improvement |

---

## Part 5: Red Team Summary

### Tests Conducted
| Test | Objective | Result | Defense Effective |
|------|-----------|--------|-------------------|
| Direct injection | Override instructions | Blocked | Yes |
| Indirect injection | Document-based attack | Partial block | Needs improvement |
| Data extraction | Exfiltrate test data | Blocked | Yes |
| Tool abuse | Unauthorized file access | Blocked | Yes |

### Vulnerabilities Found
1. [Vulnerability description and remediation]
2. [Vulnerability description and remediation]

---

## Part 6: Compliance Mapping

| Requirement | Control | Status |
|-------------|---------|--------|
| Data minimization | Least privilege, scoped access | Compliant |
| PII protection | Detection, redaction | Compliant |
| Audit logging | Security logging | Partial |
| Access control | Tool permissions | Compliant |

---

## Part 7: Ongoing Security Program

### Recommended Activities
| Activity | Frequency | Owner |
|----------|-----------|-------|
| Security review | Quarterly | Security team |
| Penetration testing | Annually | External firm |
| Threat model update | When changes occur | Product team |
| Security training | Annually | All users |

### Metrics to Track
| Metric | Target | Current |
|--------|--------|---------|
| Security incidents | 0 critical | |
| Blocked injection attempts | N/A (tracking) | |
| Time to detect threats | < 1 hour | |
| Patch application time | < 7 days | |
```

**Deliverable:** `ai-security-capstone.md` + all supporting artifacts

-----
