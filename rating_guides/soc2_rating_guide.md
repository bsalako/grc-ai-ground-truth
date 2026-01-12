# SOC 2 AI Output Rating Guide  
## Security – Logical Access Controls (CC6)

## Purpose

This rating guide defines how AI-generated responses to SOC 2 access control questions are evaluated for
-  Accuracy
-  Audit readiness
-  Customer trust.

It is designed to:
- Ensure consistent evaluation across reviewers
- Prevent AI hallucinations and overconfident inaccuracies
- Gate AI feature launches based on compliance risk

This guide is used in conjunction with the SOC 2 ground truth dataset.

---

## Rating Categories

### ✅ Pass

An AI response receives a **Pass** if all of the following are true:

- Accurately reflects the intent of the SOC 2 control
- Aligns with the ground truth dataset
- Avoids unsupported assumptions
- Clearly distinguishes enforcement from intent
- References appropriate evidence types

**Pass responses are safe to present to customers.**

---

### ⚠️ Partial

An AI response receives a **Partial** if:

- The control exists but is incompletely described
- Scope is unclear or limited (e.g., applies to some accounts)
- Compensating controls are mentioned but not explained
- Evidence is implied but not explicit

**Partial responses indicate compliance risk and require human review or remediation before use.**

---

### ❌ Fail

An AI response receives a **Fail** if any of the following are true:

- Claims compliance without evidence
- Confuses policy with enforcement
- Uses future tense (“will”, “planned”)
- Overgeneralizes (“all accounts”) without qualification
- Ignores known edge cases (e.g., service accounts, break-glass access)

**Fail responses must not be shown to customers.**

---

## Confidence Level Handling

The ground truth dataset includes a confidence level that determines how strictly AI outputs are evaluated.

### High Confidence Controls
(e.g., CC6.1 – Access Controls)

- No inference allowed
- Missing details result in Partial or Fail
- Overconfidence is penalized
- Explicit evidence is required

---

## Hallucination Indicators

Reviewers should mark responses as **Fail** if any of the following appear:

- Generic compliance language without specifics
- Claims of “full compliance” without proof
- Assumptions about tooling or controls
- Fabricated evidence references
- Inconsistent terminology across answers

---

## Evidence Evaluation

AI responses must reference appropriate evidence types, such as:

- IAM or IdP configuration
- Access control policies
- Authentication logs
- Approval or review records

Statements unsupported by evidence should be downgraded.

---

## Common Failure Patterns

| Pattern | Example | Rating |
|------|------|------|
| Policy ≠ Enforcement | “We require MFA” | Partial |
| Partial Scope | “Admins use MFA” | Partial |
| Future State | “MFA will be enabled” | Fail |
| Silent Exceptions | Ignores service accounts | Fail |
| Overconfidence | “Fully compliant” | Fail |

---

## Edge Case Handling

If an AI response addresses known edge cases (service accounts, emergency access):

- Compensating controls must be explicitly stated
- Logging and review must be mentioned
- Absence of safeguards results in Partial or Fail

Detailed edge case scenarios are documented in edge_cases/soc2_access_control_edge_cases.md and must be consulted during AI output evaluation.

---

## Launch Readiness Criteria

AI features addressing SOC 2 access controls may be launched only if:

- ≥95% of evaluated responses receive a Pass
- 0% of responses contain hallucination indicators
- Partial responses are flagged for human review
- Fail responses block release

---

## Reviewer Notes

Reviewers should prioritize audit defensibility and customer trust over response fluency or verbosity.

A shorter, accurate response is preferred over a detailed but incorrect one.

