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
same questions and produce the same grade — the difference is how you fill them
in, and whether the result can be logged into the [`airbds-metric`](https://github.com/AIBIO-UK/airbds-metric)
repository.

=== "What is the Google Sheet route?"

    You make your own copy of the working group's **[live Google Sheet](https://docs.google.com/spreadsheets/d/1eriM8bXAoNXsIR9l8OpI1XYEp8FbtBWt05CTIP9cVeg/edit)**
    and fill in `Yes`/`No` answers directly in your copy. Scoring is built into the
    sheet, so your weighted score and grade are calculated for you.

    No installation, terminal, or Git required — only a Google account.

    !!! warning "Not a deposit format"
        A completed Google Sheet copy is useful for a **quick, personal
        assessment** of a dataset. It is **not** a format the `airbds-metric`
        repository accepts — reviews logged into the repository's [`reviews/`](https://github.com/AIBIO-UK/airbds-metric/tree/main/reviews)
        folder must be YAML. If you want your review to become part of the
        public record, transcribe it into YAML afterwards (Chapter 3).

=== "What is the YAML route?"

    **YAML** stands for **YAML Ain't Markup Language**.

    It is a structured plain-text format. You open it in a **text editor** (VS
    Code, Sublime Text, nano, vim) and edit fields by hand. You also use a
    **terminal** to copy files, validate them, and submit via Git.

    You need basic familiarity with the command line (e.g. `cp`, `git add`, `git push`).

    This is the **only format the `airbds-metric` repository accepts** for a
    logged, citable review deposited in [`reviews/`](https://github.com/AIBIO-UK/airbds-metric/tree/main/reviews).

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

    **Want your review logged in the `airbds-metric` repository?** → Use the
    **YAML route** (Chapter 3). It requires basic command-line familiarity.

    You can always start with the Google Sheet and transcribe into YAML later —
    both routes ask the same 27 questions, so nothing is lost.

:::cards cols=2

- title: "📊 Google Sheet — Quick Assessment"
  content: "Fill in your own copy of the live Google Sheet. Scoring is built in. No installation required. Not accepted for deposit into the repository."
  url: chapter_02_google_sheet.md

- title: "🗂 YAML — Deposit-Ready"
  content: "Edit in a text editor. Submit via Git. Requires basic command-line familiarity. The only format the airbds-metric repository accepts for logged reviews."
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
- [Chapter 3 — YAML Walkthrough (Deposit-Ready)](chapter_03_yaml.md)
