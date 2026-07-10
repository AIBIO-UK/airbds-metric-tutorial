---
tags:
    - Google Sheet
    - YAML
    - format choice
---

# Getting Started — Choose Your Route

!!! overview "Overview"

    **Questions:**

    - What is the difference between the Google Sheet route and the YAML route?
    - Which route is right for me?

    **Learning Objectives**

    By the end of this chapter, you will be able to:

    1. Explain in plain terms what the Google Sheet route and the YAML route are
    2. Select the route that best matches your goal and technical background
    3. Navigate to the correct walkthrough chapter

    **Time:** 5 minutes

---

## What route do I need to choose?

The AIRBDS metric is a set of **27 questions**. Both routes below ask exactly the
same questions and produce the same grade — the difference is how you fill
them in.

=== "What is the Google Sheet route?"

    You make your own copy of the working group's **[live Google Sheet](https://docs.google.com/spreadsheets/d/1eriM8bXAoNXsIR9l8OpI1XYEp8FbtBWt05CTIP9cVeg/edit)**
    and fill in `Yes`/`No` answers directly in your copy. Scoring is built into the
    sheet, so your weighted score and grade are calculated for you.

    No installation, terminal, or Git required — only a Google account.

=== "What is the YAML route?"

    **YAML** stands for **YAML Ain't Markup Language**.

    It is a structured plain-text format. You open it in a **text editor** (VS
    Code, Sublime Text, nano, vim) and edit fields by hand — the same format
    used by the canonical [`metric/airbds_metric_v0.4.yaml`](https://github.com/AIBIO-UK/airbds-metric/blob/main/metric/airbds_metric_v0.4.yaml)
    file in [`airbds-metric`](https://github.com/AIBIO-UK/airbds-metric).

    You need basic familiarity with the command line (e.g. `cp`, `git clone`).

    Example of what it looks like in a text editor:

    ```yaml
    ABC-01:
      answer: "Yes"
      comments: "Dataset available via FTP."
    ABC-04:
      answer: "No"
      comments: "Licence not clearly stated."
    ```

---

## Which route should I use?

!!! tip "Recommendation"

    **Just want to quickly score a dataset for yourself?** → Use the **Google
    Sheet route** (Chapter 2).

    **Want a structured, machine-readable file** that matches the metric's own
    format — handy for scripting or keeping a tidy record? → Use the **YAML
    route** (Chapter 3). It requires basic command-line familiarity.

    You can always start with the Google Sheet and transcribe into YAML later —
    both routes ask the same 27 questions, so nothing is lost.

!!! note "No automated scorer or submission process yet"
    Either route, you work out your grade manually — there is no automated
    scorer right now, and no central place to submit a completed review.
    Because the metric itself is structured YAML, the working group hopes it
    can eventually feed shared, automated tooling that's both human- and
    machine-readable — but that infrastructure doesn't exist yet.

:::cards cols=2

- title: "📊 Google Sheet — Quick Assessment"
  content: "Fill in your own copy of the live Google Sheet. Scoring is built in. No installation required."
  url: chapter_02_google_sheet.md

- title: "🗂 YAML — Structured & Machine-Readable"
  content: "Edit in a text editor. Matches the canonical metric file format. Requires basic command-line familiarity."
  url: chapter_03_yaml.md

:::

---

## What you will need

=== "For the Google Sheet route"

    - A Google account (to make your own copy of the sheet)
    - The [live Google Sheet](https://docs.google.com/spreadsheets/d/1eriM8bXAoNXsIR9l8OpI1XYEp8FbtBWt05CTIP9cVeg/edit)
    - The dataset you want to evaluate (its landing page / documentation)

=== "For the YAML route"

    - [Git](https://git-scm.com/) installed on your machine
    - A plain-text editor (VS Code, Sublime Text, nano, vim, or similar)
    - Python 3 (for YAML validation — run `python3 --version` to check)
    - The dataset you want to evaluate

---

!!! info "Ethics questions (ABC-24 to ABC-27)"

    Four of the 27 questions cover ethics, privacy, and security. These apply
    **only to datasets containing human or animal subject data**. If your
    dataset has no such data, you answer "Yes" and mark them as not
    applicable. Both walkthroughs explain this step clearly.

---

**Ready? Jump to your chapter:**

- [Chapter 2 — Google Sheet Walkthrough (Quick Assessment)](chapter_02_google_sheet.md)
- [Chapter 3 — YAML Walkthrough](chapter_03_yaml.md)
