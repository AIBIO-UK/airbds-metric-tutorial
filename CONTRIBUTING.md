# Contributing to the AIRBDS Metric Tutorial

Thank you for your interest in contributing! This document outlines how to
contribute to **this repository** — the interactive tutorial site that walks
readers through scoring a dataset against the [AIRBDS AI-Readiness Dataset
Scoring Metric](https://github.com/AIBIO-UK/airbds-metric), developed by the
[AI-Ready Bioscience Datasets (AIRBDS) working group](https://aibio.ac.uk/about/working-groups/airbds/)
of the AIBIO-UK network.

This repository covers the **tutorial content only**. If you want to propose
a change to the metric itself — new questions, reworded questions, weight or
grading changes — that happens in the
[`airbds-metric`](https://github.com/AIBIO-UK/airbds-metric) repository; see
its own [CONTRIBUTING.md](https://github.com/AIBIO-UK/airbds-metric/blob/main/CONTRIBUTING.md).

We primarily use a GitHub-based workflow. Contributions are made via Pull
Requests (PRs) which are reviewed and merged by the working group maintainers.

---

## Table of Contents

- [Ways to Contribute](#ways-to-contribute)
  - [Reporting Issues](#reporting-issues)
  - [Pull Requests](#pull-requests)
- [What to Contribute](#what-to-contribute)
- [What Not to Contribute](#what-not-to-contribute)
- [Commit Message Convention](#commit-message-convention)
- [Review Process](#review-process)
- [Contribution Licensing](#contribution-licensing)
- [Code of Conduct](#code-of-conduct)

---

## Ways to Contribute

### Reporting Issues

If you find an error, broken link, or inconsistency anywhere in the tutorial:

1. **Check existing issues** to see if it has been reported.
2. **Create a new issue** with a clear title and description. Include:
   - The page and section affected
   - What the error is and what you expected
   - Steps to reproduce (if applicable)

---

### Pull Requests

1. **Fork the repository** and create a new branch:
   ```bash
   git checkout -b docs/fix-broken-link-chapter-2
   ```
2. **Make your changes** to the relevant page(s) under `docs/`.
3. **Preview locally** before submitting:
   ```bash
   pip install -r requirements.txt
   mkdocs serve
   ```
   Then open `http://localhost:8000/` and check your change renders as expected.
4. **Commit your changes** using the [convention below](#commit-message-convention):
   ```bash
   git add docs/chapters/chapter_02_google_sheet.md
   git commit -m "fix: correct broken link in chapter 2"
   ```
5. **Push to your fork:**
   ```bash
   git push origin docs/fix-broken-link-chapter-2
   ```
6. **Open a PR** against the `main` branch. Provide a clear title and description of the change.

---

## What to Contribute

- ✅ Fixes for typos, broken links, or formatting errors
- ✅ Clarifications or improvements to existing chapters
- ✅ New examples or worked walkthroughs that help readers apply the metric
- ✅ Improvements to the README, CONTRIBUTING guide, or site configuration

---

## What Not to Contribute

- ❌ Changes to the metric's questions, weights, or grading rules — propose these in [`airbds-metric`](https://github.com/AIBIO-UK/airbds-metric) instead
- ❌ Proprietary or closed content that cannot be publicly shared
- ❌ Changes to CI/CD or repository infrastructure without prior discussion
- ❌ Promotional content unrelated to the AIRBDS metric or AI-ready bioscience datasets

---

## Commit Message Convention

Use the following prefixes for clarity:

| Prefix | Use for |
|---|---|
| `docs:` | Documentation/content changes (chapters, README, etc.) |
| `fix:` | Typo, broken link, or formatting fix |
| `chore:` | Repo infrastructure (CI, mkdocs config, .gitignore, etc.) |

Example: `docs: clarify Ethics question handling in chapter 3`

---

## Review Process

Working group maintainers will review all Pull Requests.

- We aim to respond within **14 days**.
- Feedback may be provided via PR comments; please respond or revise promptly.
- Once approved, a maintainer will merge into `main`.

---

## Contribution Licensing

By contributing, you agree that your contributions will be licensed under
[**CC BY-SA 4.0**](https://creativecommons.org/licenses/by-sa/4.0/). This is
required because this tutorial is a derivative of the ELIXIR Training Lesson
Template (CC BY-SA 4.0) and the ShareAlike condition applies. All contributed
content must respect the copyrights of others.

---

## Code of Conduct

All contributors are expected to abide by the
[Code of Conduct](CODE_OF_CONDUCT.md). Please read it before participating.
