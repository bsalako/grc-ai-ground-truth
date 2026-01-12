# GRC AI Ground Truth Dataset

Hello, this repository contains structured datasets, rating guides, and methodology for evaluating AI-generated outputs against real-world **Governance, Risk & Compliance (GRC)** standards.

## 📌 Purpose

This repository demonstrates how to:
- Define a **ground truth dataset** for compliance questions
- Build reproducible truth-checking methods
- Evaluate AI responses against audit-ready expectations

It is useful for:
- AI evaluation projects
- Compliance automation research
## 🧩 Directory Structure
datasets/ — Ground truth CSVs

rating_guides/ — Evaluation criteria and guides

edge_cases/ — Complex GRC scenarios

methodology/ — How ground truth was constructed


## 🚀 Getting Started

1. Browse the datasets in `datasets/`
2. Review the rating guide in `rating_guides/`
3. Explore edge cases in `edge_cases/`
4. Read the methodology for context

The methodology in methodology/how_ground_truth_is_built.md defines how truth, risk, and AI evaluation standards are governed across this repository.

Ongoing AI quality is governed through metrics and drift monitoring defined in quality/ai_quality_metrics_and_drift.md.

## Role Mapping: GRC AI SME Responsibilities

## Role Mapping: GRC AI SME Responsibilities

This repository is structured to directly map to the responsibilities of a GRC AI Subject Matter Expert working on AI-powered compliance workflows.

| Role Responsibility (Vanta-style) | Portfolio Artifact | What This Demonstrates |
|----------------------------------|--------------------|------------------------|
Design and test prompts | `ai_evaluations/` | I evaluate how different AI outputs perform against real GRC standards and identify where prompting or guardrails must change to reduce risk. |
Own the ground truth | `datasets/soc2_ground_truth_v1.csv` | I translate compliance frameworks into structured, audit-defensible “truth layers” that define what correct looks like for AI evaluation. |
Define evaluation standards | `rating_guides/soc2_rating_guide.md` | I create consistent scoring rubrics so multiple reviewers can assess AI quality without subjectivity. |
Handle real-world edge cases | `edge_cases/soc2_access_control_edge_cases.md` | I document where compliance is nuanced and ensure AI systems do not overgeneralize or misrepresent risk. |
Ensure responsible AI use | `methodology/how_ground_truth_is_built.md` | I define governance principles that prioritize audit defensibility, transparency, and customer trust over confidence or speed. |
Run side-by-side reviews | `ai_evaluations/soc2_cc6_side_by_side.md` | I demonstrate how to compare AI outputs, detect hallucinations, and make launch-readiness decisions. |
Support core GRC workflows (TPR, risk) | `ai_evaluations/tpr_ai_vendor_risk_evaluation.md` | I apply AI evaluation to high-impact workflows like Third-Party Risk, where false confidence can lead to material business risk. |
Measure ongoing quality and drift | `quality/ai_quality_metrics_and_drift.md` | I design post-launch monitoring to detect degradation, prevent silent failures, and maintain audit readiness over time. |
Document and teach | `README.md` + all guides | I structure this repo so PMs, engineers, and GTM teams can understand and reuse the system without relying on tribal knowledge. |
Collaborate cross-functionally | Repo-wide design | This portfolio is built to mirror how Security, Product, AI Platform, and Compliance teams work together to ship trustworthy AI. |

