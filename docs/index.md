---
tags:
    - AI-readiness
    - bioscience datasets
    - FAIR data
    - scoring metric
---

# AIRBDS AI-Readiness Dataset Scoring Metric

**A practical guide to evaluating bioscience datasets for AI/ML use**

Developed by the [AIRBDS Working Group](https://aibio.ac.uk/about/working-groups/airbds/), AIBIO-UK · Funded by BBSRC · Licensed [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

---

!!! overview "Overview"

    **Questions this tutorial answers:**

    - What does the AIRBDS metric measure, and why does it matter?
    - Should I use the Google Sheet (quick assessment) or YAML (structured) route?
    - How do I work through all 27 questions and calculate a grade?
    - How do I record my completed review?

    **Learning Objectives**

    By the end of this tutorial, you will be able to:

    1. Describe what the AIRBDS metric assesses and how it is scored
    2. Choose the route (Google Sheet or YAML) that suits your goal
    3. Complete a full dataset review and assign a grade (Caution / Bronze / Silver / Gold)
    4. Calculate and record your grade

    **Who this is for:** Researchers, data curators, and repository managers working with bioscience datasets

    **Skill levels covered:** Quick assessment (Google Sheet route) · Structured & machine-readable (YAML route)

    **Estimated time:** 30–60 minutes per dataset review

---

## What is the AIRBDS Metric?

The AIRBDS metric is a structured checklist of **27 Yes/No questions** that assesses whether a bioscience dataset is ready for use in AI and machine learning workflows. Questions cover four areas:

| Scope | Questions | What it checks |
|---|---|---|
| **Infrastructure** | ABC-01 – ABC-10 | Access, licensing, unique identifiers, version control |
| **Metadata** | ABC-11 – ABC-17 | Bias documentation, standards, preprocessing, provenance |
| **Content** | ABC-18 – ABC-23 | Completeness, consistency, format |
| **Ethics** | ABC-24 – ABC-27 | Consent, privacy, security, data protection |

Each answer contributes to a weighted score. Datasets receive one of four grades:

| Grade | Meaning |
|---|---|
| 🔴 **Caution** | Fails one or more Critical criteria — serious limitations for AI/ML use |
| 🟤 **Bronze** | Passes most Critical questions (≥ 7/8) |
| ⚪ **Silver** | Passes all Critical + ≥ 50% of Important questions |
| 🟡 **Gold** | Passes all Critical and Important + ≥ 50% of Optional questions |

---

## How to use this tutorial

**Start here → [Chapter 1: Getting Started — Choose Your Route](chapters/chapter_01.md)**

Chapter 1 explains the difference between the Google Sheet and YAML routes and helps you choose the right one based on your goal. You will then follow either:

- **Chapter 2** — Google Sheet walkthrough (quick assessment, no coding required)
- **Chapter 3** — YAML walkthrough (structured & machine-readable, text editor and command line)

---

!!! note "Citation"
    If you use this metric in your research, please cite:

    > AIRBDS Working Group, AIBIO-UK. (2026). *AIRBDS AI-Readiness Dataset Scoring Metric* (v0.4). GitHub. <https://github.com/AIBIO-UK/airbds-metric>

    Full citation metadata is in [`CITATION.cff`](https://github.com/AIBIO-UK/airbds-metric/blob/main/CITATION.cff).

??? info "Template attribution"
    This tutorial site is built using the [ELIXIR Training Lesson Template](https://zenodo.org/records/7913092)
    by van Geest G, Kronander E, Romero Herrera JA, Žlender N, ELIXIR Training Coordination Team & Cardona A (2023).
    DOI: [10.5281/zenodo.7913092](https://doi.org/10.5281/zenodo.7913092) · CC BY-SA 4.0.
    Content has been replaced with the AIRBDS tutorial and AIBIO-UK branding applied.
    This tutorial is therefore also licensed CC BY-SA 4.0.
