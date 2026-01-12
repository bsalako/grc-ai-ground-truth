# SOC 2 Access Control — Edge Cases for AI Evaluation  
## Control: CC6.1 (Logical Access)

## Purpose

This document captures common real-world edge cases where AI systems frequently misinterpret compliance posture related to privileged access controls.

It is used by:
- Reviewers applying the SOC 2 rating guide
- Product teams designing AI-assisted GRC workflows
- Security teams validating audit readiness

---

## Edge Case 1: Service Accounts Without MFA

### Scenario  
Service accounts cannot use MFA in the same way human users do.

### Common AI Failure  
AI marks the organization as **non-compliant** for lack of MFA.

### Correct Evaluation  
Acceptable **only if compensating controls exist**, such as:
- Short-lived credentials or workload identity
- Restricted scopes and permissions
- Continuous monitoring and logging
- Regular credential rotation

### Risk if Mishandled  
Overstating compliance or failing audits due to undocumented exceptions.

---

## Edge Case 2: Break-Glass / Emergency Access

### Scenario  
Emergency accounts bypass MFA for incident response.

### Common AI Failure  
AI treats this as either:
- Fully compliant without safeguards, or  
- Fully non-compliant without nuance.

### Correct Evaluation  
Acceptable only if:
- Access is time-bound  
- All activity is logged  
- Usage requires documented approval  
- Post-incident review is performed  

### Risk if Mishandled  
Creates a hidden privilege escalation path with no audit visibility.

---

## Edge Case 3: Legacy Systems

### Scenario  
Older systems cannot enforce modern access controls.

### Common AI Failure  
AI assumes modern controls apply everywhere.

### Correct Evaluation  
Acceptable only if:
- Legacy scope is documented  
- Compensating controls exist  
- Migration plan is in progress  
- Risk is acknowledged in audits

### Risk if Mishandled  
False sense of security and audit surprises.

---

## Edge Case 4: Acquired or Merged Companies

### Scenario  
Newly acquired entities operate under different security standards.

### Common AI Failure  
AI assumes uniform controls across the organization.

### Correct Evaluation  
Acceptable only if:
- Transitional risk is disclosed  
- Integration timelines are documented  
- Interim safeguards exist

### Risk if Mishandled  
Material misrepresentation of security posture.

---

## Edge Case 5: Privileged Contractors

### Scenario  
External contractors have elevated access for limited periods.

### Common AI Failure  
AI categorizes them as standard users.

### Correct Evaluation  
They must be treated as privileged accounts and subject to:
- MFA  
- Time-bound access  
- Enhanced monitoring  
- Formal offboarding

### Risk if Mishandled  
Third-party risk exposure and audit findings.

---

## Edge Case 6: Policy vs. Enforcement

### Scenario  
A company has strong written policies but inconsistent technical enforcement.

### Common AI Failure  
AI treats policy language as proof of control.

### Correct Evaluation  
Only **technical enforcement** qualifies as compliance evidence.

### Risk if Mishandled  
Audit failures due to reliance on intent rather than execution.

---

## How This Document Is Used

When reviewing AI outputs for SOC 2 access controls:

1. Evaluate against the **ground truth dataset**
2. Apply the **SOC 2 rating guide**
3. Cross-check with this **edge cases document**
4. If an edge case applies and is not addressed:
   - Downgrade to **Partial** or **Fail**

---

## Key Principle

In my personal opinion, Edge cases are not exceptions to ignore, they are the **real test** of whether AI can be trusted in compliance workflows.
