# PT Training Plan Generation + QA Demo (Synthetic Data)

This repository contains a small end-to-end demonstration of the evaluation and data pipeline layer for an AI-assisted physical therapy workflow.

The demo uses **synthetic, non-identifiable data** and is intended to illustrate system design patterns, not to provide medical advice or clinical guidance.

---

## Problem Context

Personalized physical therapy programming is time-intensive, and clinics face growing patient volumes alongside limited clinician capacity. AI systems can assist with drafting individualized training plans, but only if paired with clear constraints, validation, and auditability.

This demo focuses on the **infrastructure layer** that makes AI-generated outputs reviewable and safer to operationalize.

---

## System Overview (High Level)

**Inputs (two sources):**
- Redacted medical summary (synthetic)
- Patient survey (synthetic)

**Processing steps:**
1. Merge inputs into a unified patient record
2. Extract standardized constraint tags from clinical context and patient-reported text
3. Select and sequence exercises from a curated reference library
4. Generate a draft session plan
5. Run QA checks and assign interpretable quality labels
6. Emit run-level reporting for auditability

**Outputs:**
- A per-patient plans dataset
- A run-level QA and monitoring report

---

## What This Demo Covers

- File-based ingestion of structured inputs
- Multi-source data merge with explicit error handling
- Constraint extraction and normalization
- Deterministic plan generation (rule-based stand-in)
- QA checks with explainable quality labels
- Generation of auditable run artifacts

---

## What This Demo Does NOT Cover

- LLM training or fine-tuning
- Autonomous clinical decision-making
- Use of real patient data
- Regulatory or clinical validation

---

## Files in This Repository

- `01_pt_training_e2e_demo.ipynb`  
  Executable notebook implementing the end-to-end pipeline

- `medical_redacted.csv`  
  Synthetic clinician-provided context input

- `patient_survey.csv`  
  Synthetic patient-reported context input

- `pt_training_plans.csv`  
  Per-patient output including draft plan text, constraints, QA flags, and quality score

- `pt_training_run_report.json`  
  Run-level metadata and quality distribution for auditability

---

## How to Use

Open the notebook and run the single code cell from top to bottom.  
All outputs are written to disk in the same directory.

---

## Notes

This repository is a **portfolio artifact**.  
In a production system, outputs would be stored in external data stores or logging systems rather than committed to version control.
<img width="468" height="646" alt="image" src="https://github.com/user-attachments/assets/c00131b9-2289-4d3d-8c0d-5f6eddc942c7" />
