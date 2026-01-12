# Side-by-Side AI Evaluation  
## SOC 2 – CC6.1 Privileged Access Controls

## Question  
Are privileged accounts protected with multi-factor authentication (MFA)?

---

## AI Response A  
“Yes, our organization uses MFA to protect administrator accounts and ensure secure access to critical systems.”

## AI Response B  
“MFA is enforced for all privileged accounts accessing production systems through our centralized identity provider. Enforcement is verified through IdP configuration and access logs. Service and emergency accounts are protected using compensating controls, including restricted permissions, logging, and post-use review.”

---

## Evaluation Summary

| Dimension | Response A | Response B |
|-----------|------------|------------|
Framework accuracy | Partial | Pass |
Scope clarity | Partial | Pass |
Evidence referenced | Fail | Pass |
Edge cases handled | Fail | Pass |
Hallucination risk | High | Low |
Audit defensibility | Fail | Pass |
Customer trust impact | Low | High |

---

## Rating Decisions

### Response A — FAIL  
- Generic compliance language  
- No proof of enforcement  
- No evidence cited  
- Ignores service and emergency accounts  

**Action:** Block from customer-facing use.

---

### Response B — PASS  
- Matches SOC 2 CC6 intent  
- Evidence-based  
- Addresses edge cases  
- Audit-defensible  

**Action:** Approved for customer-facing use.

---

## Launch Readiness Impact

- Pass rate: 50%  
- Hallucinations detected: 1  
- Release decision: **Blocked**

---

## Key Takeaway

AI outputs must be evaluated not on confidence or fluency, but on **audit defensibility and customer trust**.

