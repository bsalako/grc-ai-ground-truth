# AI Quality Metrics & Drift Monitoring  
## GRC Compliance Outputs

## Purpose

This document defines how quality is measured and maintained for AI-generated GRC responses after deployment.

The goal is to:
- Detect accuracy degradation
- Prevent hallucination creep
- Protect audit readiness
- Maintain customer trust over time

These metrics apply to all AI features evaluated using this repository’s ground truth datasets and rating guides.

---

## Quality Dimensions

AI outputs are evaluated across four core dimensions:

1. **Accuracy** – Alignment with ground truth  
2. **Audit Defensibility** – Would an auditor accept this answer?  
3. **Explainability** – Is the logic transparent to customers?  
4. **Risk Awareness** – Are edge cases and uncertainty handled responsibly?

---

## Core Metrics

### 1. Pass / Partial / Fail Distribution

Tracks overall quality health.

| Metric | Target |
|-------|--------|
Pass rate | ≥ 95% |
Partial rate | ≤ 5% |
Fail rate | 0% |

**Action Triggers**
- Fail rate > 0% → Immediate review
- Partial rate > 5% → Quality regression investigation

---

### 2. Hallucination Frequency

Measures how often AI produces:
- Unsupported claims  
- Fabricated evidence  
- Overconfident assertions  

**Target:** 0 hallucinations  
**Action:** Any hallucination blocks customer-facing output.

---

### 3. Evidence Alignment Rate

Percentage of responses that reference:
- Correct evidence types
- Appropriate documentation
- Verifiable artifacts

**Target:** ≥ 98%  
**Action:** < 95% triggers dataset or prompt review.

---

### 4. Edge Case Coverage Rate

Measures how often AI correctly addresses:
- Service accounts  
- Break-glass access  
- Contractors  
- Legacy systems  

**Target:** ≥ 90%  
**Action:** < 85% triggers edge case retraining or guardrails.

---

### 5. Confidence Calibration Score

Tracks mismatch between:
- Confidence of response  
- Actual correctness  

**Red Flag Pattern**
High confidence + incorrect answer = **Critical risk**

---

## Drift Monitoring

### What Is Drift?

Drift occurs when AI behavior changes over time due to:
- Model updates  
- Prompt changes  
- New customer contexts  
- New regulatory interpretations  

Drift is dangerous in GRC because it often:
- Appears as “improvement”  
- But erodes audit defensibility  

---

## Drift Detection Methods

### 1. Scheduled Re-Evaluation

- Weekly sampling of AI outputs  
- Monthly full regression against ground truth  
- Quarterly deep audit review  

---

### 2. Change-Triggered Reviews

Re-evaluate AI whenever:
- Prompts change  
- New compliance frameworks added  
- Product workflows expand  
- New audit findings emerge  

---

### 3. Silent Failure Detection

Monitor for:
- Increase in “generic compliance language”
- Decrease in evidence references
- Rising Partial ratings without obvious cause

These indicate **quality erosion** even if Pass rate appears stable.

---

## Response to Drift

When drift is detected:

1. **Freeze customer-facing deployment**
2. **Identify root cause**
   - Prompt regression  
   - Dataset gaps  
   - Edge case expansion  
3. **Update ground truth**
4. **Revise rating guide if needed**
5. **Re-run evaluations**
6. **Resume deployment only after metrics recover**

---

## Reporting Cadence

| Report | Audience | Frequency |
|--------|----------|-----------|
AI Quality Summary | Product & Security | Weekly |
Hallucination Log | AI Platform | Real-time |
Drift Analysis | Compliance Leadership | Monthly |
Audit Readiness Review | GRC | Quarterly |

---

## Governance & Ownership

| Role | Responsibility |
|------|----------------|
GRC AI SME | Owns quality standards and truth layer |
AI Platform | Implements monitoring and alerts |
Product | Aligns quality thresholds with risk tolerance |
Security & Privacy | Reviews high-risk outputs |
GTM | Ensures customer-facing claims are safe |

---

## Why These Metrics Matter

AI in compliance does not fail like traditional software.

It fails by:
- Sounding confident  
- Being mostly right  
- And occasionally catastrophic  

These metrics exist to ensure:
- No silent erosion of trust  
- No accidental misrepresentation  
- No audit surprises  

Quality is not a one-time gate —  it is a **continuous control**.
