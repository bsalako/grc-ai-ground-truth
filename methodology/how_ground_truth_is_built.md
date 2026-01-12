# Methodology: How Ground Truth Is Built for GRC AI Evaluation

## Purpose

This document defines the methodology used to create, maintain, and govern ground truth datasets for evaluating AI-generated outputs in Governance, Risk, and Compliance (GRC) workflows.

The goal is to ensure that AI features are:
- Accurate
- Audit-defensible
- Consistent across reviewers
- Safe for customer-facing use

This methodology applies to all datasets, rating guides, and edge case documents in this repository.

---

## Guiding Principles

### 1. Audit Reality Over Theoretical Compliance  
Ground truth reflects how auditors evaluate controls in practice — not how frameworks describe them in theory.

### 2. Enforcement Over Intent  
Policies, plans, and future commitments are not treated as evidence of compliance.  
Only technical or procedural enforcement qualifies as ground truth.

### 3. Risk-Aware Design  
Controls with high customer or audit impact are evaluated more strictly than informational controls.

### 4. Transparency Over Confidence  
AI outputs must prefer uncertainty disclosures over confident but unsupported claims.

---

## How Ground Truth Is Defined

For each compliance question, truth is defined by answering:

1. What would an auditor accept as a **complete and correct** response?
2. What evidence would be required to **defend this answer** in an audit?
3. What common misunderstandings or shortcuts lead to **false confidence**?
4. What edge cases regularly appear in real organizations?

Each ground truth entry includes:
- A canonical correct answer
- Acceptable variations
- Explicit unacceptable answers
- Required evidence
- Evidence quality bar
- Confidence level

This structure ensures answers are judged on **defensibility**, not fluency.

---

## Source of Truth Inputs

Ground truth definitions are informed by:

- SOC 2, ISO 27001, NIST, HIPAA, and PCI DSS control intent
- Real-world audit expectations and common findings
- Security operations best practices
- Known AI failure modes in compliance contexts

Framework text is treated as **guidance**, not as sufficient truth by itself.

---

## Handling Ambiguity

Compliance answers are rarely binary.  
When ambiguity exists:

- It is documented in **acceptable variations**
- Constraints are captured in **confidence level**
- Risk is explained in **edge cases documentation**

If ambiguity cannot be safely resolved:
- The ground truth defaults to **requiring human review**

---

## Edge Case Management

Edge cases are treated as first-class inputs to truth definition.

Each dataset is accompanied by:
- An edge case document
- Clear guidance on how exceptions are evaluated
- Rules for when exceptions require compensating controls

If an AI response fails to address a known edge case:
- It is automatically downgraded to **Partial** or **Fail**

---

## Rating Guide Alignment

Every dataset is paired with a rating guide that defines:

- What qualifies as Pass, Partial, or Fail
- Hallucination indicators
- Evidence expectations
- Launch-readiness criteria

Ground truth is not considered complete until:
- A rating guide exists
- Reviewers can apply it consistently

---

## Change Management

Ground truth is a living system.

All updates follow this process:

1. **Trigger**
   - New audit findings  
   - New product features  
   - Regulatory updates  
   - AI failure patterns  

2. **Review**
   - Impact assessed on existing entries  
   - Edge cases updated if needed  

3. **Revision**
   - Dataset updated  
   - Rating guide adjusted  
   - Methodology documented  

4. **Versioning**
   - Changes committed with clear messages  
   - Prior versions retained for traceability  

---

## Dispute Resolution

When reviewers disagree on what constitutes “correct”:

1. Default to **audit defensibility**
2. Prioritize **customer trust impact**
3. Prefer **conservative interpretation**
4. Document rationale in dataset notes

If uncertainty remains:
- Mark the control as requiring **human review**
- Do not allow autonomous AI output

---

## AI Output Governance Model

AI-generated compliance responses are governed using a three-tier model:

| Tier | Description | Action |
|-----|-------------|--------|
Pass | Accurate, defensible, aligned with ground truth | Customer-facing |
Partial | Incomplete, unclear, or risky | Human review required |
Fail | Incorrect, hallucinated, or misleading | Blocked from use |

This model ensures that AI accelerates GRC workflows without replacing human accountability.

---

## Measuring Quality Over Time

Quality is monitored using:

- Pass / Partial / Fail distribution
- Hallucination frequency
- Evidence alignment rate
- Edge case miss rate

Trends are reviewed regularly to:
- Detect drift
- Identify training gaps
- Trigger ground truth updates

---

## Why This Methodology Exists

AI in compliance does not fail loudly —  
it fails **confidently and quietly**.

This methodology exists to ensure that:
- AI does not overstate compliance
- Customers are not misled
- Audits are not jeopardized
- Trust is built, not borrowed

Ground truth is not just data —  it is the **trust layer** between AI systems and real-world accountability.

