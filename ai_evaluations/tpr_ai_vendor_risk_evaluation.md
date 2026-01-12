# Third-Party Risk AI Evaluation  
## Vendor Risk Summarization & Decision Support

## Scenario  
An AI assistant summarizes vendor security posture to support third-party risk decisions.

Vendor: Nike  
Context: Processes customer support data containing PII  
Evidence: SOC 2 Type II report with exception for service account MFA

---

## Question  
Based on the available evidence, what is the security risk level of this vendor?

---

## AI Response A  
“Nike presents a low security risk based on its SOC 2 Type II report and standard security controls. The vendor follows industry best practices and can be considered safe for onboarding.”

---

## AI Response B  
“Nike demonstrates a generally strong security posture supported by a SOC 2 Type II report. However, service accounts do not uniformly enforce MFA, which introduces elevated risk. Compensating controls such as restricted scopes, secrets rotation, and monitoring reduce — but do not eliminate — this risk.  
**Recommended risk level:** Medium.  
**Action:** Proceed with onboarding with documented acceptance of residual risk and a remediation plan for service account authentication.”

---

## Evaluation Summary

| Dimension | Response A | Response B |
|-----------|------------|------------|
Accuracy vs evidence | Fail | Pass |
Risk awareness | Fail | Pass |
Edge cases handled | Fail | Pass |
Confidence calibration | Fail | Pass |
Audit defensibility | Fail | Pass |
Customer trust impact | Low | High |

---

## Rating Decisions

### Response A — FAIL  
- Ignores documented exception  
- Overstates security posture  
- No evidence-based reasoning  
- Generic compliance language  

**Action:** Block from customer-facing use.

---

### Response B — PASS  
- Evidence-aligned  
- Risk-aware  
- Addresses service account edge case  
- Recommends risk acceptance and remediation  

**Action:** Approved with human-in-the-loop review.

---

## Human-in-the-Loop Requirements

All AI-supported TPR decisions require:  
- Human validation of risk level  
- Formal acceptance of residual risk  
- Tracking of remediation plans  
- Periodic reassessment

---

## Launch Readiness Impact

- Pass rate: 50%  
- Hallucinations detected: 1  
- Release decision: **Blocked**

---

## Key Takeaway

In third-party risk workflows, AI must never replace judgment.  
Its role is to **surface risk clearly, not hide it behind confidence**.
