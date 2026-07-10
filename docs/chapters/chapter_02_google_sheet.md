---
tags:
    - Google Sheets
    - quick assessment
    - beginner
---

# Google Sheet Walkthrough

**Quick assessment · No coding required · Works in Google Sheets**

!!! overview "Overview"

    **Questions:**

    - How do I get my own copy of the metric's Google Sheet?
    - How do I fill in my reviewer details and answer all 27 questions?
    - How do I read off my score and grade?
    - Can I submit this to the `airbds-metric` repository?

    **Learning Objectives**

    By the end of this chapter, you will be able to:

    1. Make your own editable copy of the AIRBDS Google Sheet
    2. Fill in all 27 questions with Yes/No answers
    3. Correctly handle the Ethics questions (`ABC-24`–`ABC-27`)
    4. Read the weighted score and grade the sheet calculates automatically
    5. Understand why this format cannot be deposited into the repository, and what to do if you want it logged

    **Time:** 30–60 minutes per dataset review (depending on how well you know the dataset)

    **Prerequisite:** Complete [Chapter 1](chapter_01.md) to confirm the Google Sheet route is right for you.

---

## Step 1 — Make your own copy of the sheet

Open the working group's live sheet:

**[AIRBDS Metric — Google Sheet](https://docs.google.com/spreadsheets/d/1eriM8bXAoNXsIR9l8OpI1XYEp8FbtBWt05CTIP9cVeg/edit)**

This sheet is the working group's live source of truth for the metric — do not
edit it directly. Instead, make your own copy:

**File → Make a copy** (top-left menu), then choose a location in your own
Google Drive. Give it a name that identifies the dataset you are reviewing,
e.g. `E-MTAB-1234 AIRBDS review`.

All further edits happen in **your copy**, not the original.

---

## Step 2 — Fill in reviewer and dataset details

At the top of your copy, fill in your reviewer information and the dataset's
details: your name, initials, ORCID (if you have one), affiliation, and
today's date, plus the dataset's name, URL, hosting resource, and accession
number.

---

## Step 3 — Answer the 27 questions

Work through each of the 27 questions (`ABC-01` to `ABC-27`). For each row,
read the `question` and `guidance` columns, then enter `Yes` or `No` in the
answer column.

!!! warning "Weight matters"
    Eight questions are marked **Critical** (80 points each):
    `ABC-04, ABC-09, ABC-11, ABC-12, ABC-16, ABC-20, ABC-24, ABC-25`. Getting
    one of these wrong has a large effect on the grade — read the guidance
    carefully before answering.

---

## Step 4 — Handle Ethics questions (ABC-24 to ABC-27)

The last four questions apply only to datasets that contain **human or animal
subject data**.

!!! info "Does your dataset contain human or animal subjects?"

    === "No human or animal subjects"

        For each of `ABC-24` to `ABC-27`:

        - Enter **`Yes`** as the answer
        - Mark it as **not applicable**
        - Optionally add a comment such as "No human or animal subject data in this dataset"

    === "Human or animal subjects present"

        Answer each of `ABC-24` to `ABC-27` normally (`Yes` or `No`) based on
        what you find in the dataset's documentation. Leave it as applicable.

---

## Step 5 — Read your score and grade

Scoring is built into the sheet — once you have answered all 27 questions, the
sheet calculates your weighted score and grade for you. You do not need to
write or copy any formulas.

For the reasoning behind how the score and grade are derived, see
[`reviews/GUIDANCE.md`](https://github.com/AIBIO-UK/airbds-metric/blob/main/reviews/GUIDANCE.md)
in the `airbds-metric` repository. The four possible grades are:

| Grade | Meaning |
|---|---|
| 🔴 **Caution** | May have serious issues — fails one or more Critical criteria |
| 🟤 **Bronze** | Passes most Critical questions |
| ⚪ **Silver** | Passes all Critical + at least half of Important questions |
| 🟡 **Gold** | Passes all Critical and Important + at least half of Optional questions |

---

## Step 6 — What to do with your completed review

!!! warning "This is not a submittable format"

    A completed copy of the Google Sheet is great for a **quick, personal
    assessment** — but the `airbds-metric` repository only accepts **YAML**
    reviews in its [`reviews/`](https://github.com/AIBIO-UK/airbds-metric/tree/main/reviews)
    folder. A Google Sheet copy cannot be deposited there.

    If you want your review logged as part of the public record:

    1. Keep your completed sheet open for reference.
    2. Go to [Chapter 3 — YAML Walkthrough](chapter_03_yaml.md) and transcribe
       your answers into the YAML template. Both routes ask the same 27
       questions, so this is a direct copy of your `Yes`/`No` answers and
       comments.

---

Well done — you have completed a quick dataset assessment using the Google
Sheet! 🎉

Continue to [Chapter 3 — YAML Walkthrough](chapter_03_yaml.md) to log this
review in the repository, or to [Further Resources](../follow_up_training.md) /
the [About page](../index.md).
