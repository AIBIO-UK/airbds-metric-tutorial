---
tags:
    - YAML
    - command line
    - Git
    - deposit-ready
---

# YAML Walkthrough

**Deposit-ready · Requires a text editor and basic command-line familiarity**

!!! overview "Overview"

    **Questions:**

    - How do I clone the repository and start my review file?
    - How do I fill in reviewer details and answer all 27 questions in YAML?
    - How do I validate the file and calculate a grade?
    - How do I submit via pull request?

    **Learning Objectives**

    By the end of this chapter, you will be able to:

    1. Clone the repository and create a YAML review file from the template below
    2. Fill in all reviewer metadata and 27 question answers
    3. Correctly handle the Ethics questions with the `not_applicable` field
    4. Validate the YAML file and resolve common errors
    5. Calculate a grade and submit via a pull request

    **Time:** 30–60 minutes per dataset review (depending on how well you know the dataset)

    **Prerequisite:** Complete [Chapter 1](chapter_01.md) to confirm YAML is the right route for you.

---

## Prerequisites

Before you begin, make sure you have:

- [Git](https://git-scm.com/) installed — run `git --version` to check
- A plain-text editor (VS Code, Sublime Text, nano, vim, or similar)
- Python 3 — run `python3 --version` to check (used for validation in Step 6)

---

## Step 1 — Get the repository

Fork the repository on GitHub, then clone your fork:

```bash
git clone https://github.com/<your-username>/airbds-metric.git
cd airbds-metric
```

If you just want to **explore locally** without submitting, clone the main repo directly:

```bash
git clone https://github.com/AIBIO-UK/airbds-metric.git
cd airbds-metric
```

---

## Step 2 — Create your review file

The `reviews/` folder is a plain drop folder — there is no template file to
copy from the repository itself. Instead, create a new file in `reviews/`
using this naming convention:

```
<dataset_accession>_<your_initials>_<review_number>.yaml
```

- `<dataset_accession>` — the repository accession, or a short descriptive token if there is none
- `<your_initials>` — uppercase letters only (2–6 characters, no digits)
- `<review_number>` — start at 1; increment if you review the same dataset again

For example: `reviews/E-MTAB-1234_CH_1.yaml`

Create the file and paste in the template below:

```yaml
schema_version: "0.4"

reviewer:
  name: ""            # Full name
  initials: ""        # e.g. CH
  orcid: ""            # e.g. 0000-0000-0000-0000
  affiliation: ""
  review_date: ""     # ISO 8601, e.g. 2026-06-01

dataset:
  name: ""
  url: ""
  hosting_resource: ""
  accession: ""
  comments: ""

process_comments: ""

answers:
  ABC-01: { answer: "", comments: "" }
  ABC-02: { answer: "", comments: "" }
  ABC-03: { answer: "", comments: "" }
  ABC-04: { answer: "", comments: "" }
  ABC-05: { answer: "", comments: "" }
  ABC-06: { answer: "", comments: "" }
  ABC-07: { answer: "", comments: "" }
  ABC-08: { answer: "", comments: "" }
  ABC-09: { answer: "", comments: "" }
  ABC-10: { answer: "", comments: "" }
  ABC-11: { answer: "", comments: "" }
  ABC-12: { answer: "", comments: "" }
  ABC-13: { answer: "", comments: "" }
  ABC-14: { answer: "", comments: "" }
  ABC-15: { answer: "", comments: "" }
  ABC-16: { answer: "", comments: "" }
  ABC-17: { answer: "", comments: "" }
  ABC-18: { answer: "", comments: "" }
  ABC-19: { answer: "", comments: "" }
  ABC-20: { answer: "", comments: "" }
  ABC-21: { answer: "", comments: "" }
  ABC-22: { answer: "", comments: "" }
  ABC-23: { answer: "", comments: "" }
  # Ethics questions — answer "Yes" if the dataset has no human/animal subjects
  ABC-24: { answer: "", comments: "", not_applicable: false }
  ABC-25: { answer: "", comments: "", not_applicable: false }
  ABC-26: { answer: "", comments: "", not_applicable: false }
  ABC-27: { answer: "", comments: "", not_applicable: false }

# Calculated fields — complete after scoring (see Step 7)
result:
  weighted_score: null
  grade: ""   # Caution / Bronze / Silver / Gold
```

!!! tip "Reference file"
    Keep [`metric/airbds_metric_v0.4.yaml`](https://github.com/AIBIO-UK/airbds-metric/blob/main/metric/airbds_metric_v0.4.yaml)
    open in another tab — it contains the full question text and guidance for
    each `ABC` ID, plus the authoritative `grade_points`/`grading` rules.

---

## Step 3 — Fill in reviewer and dataset metadata

Fill in every field in the `reviewer` and `dataset` blocks:

```yaml
reviewer:
  name: "Charlie Harrison"
  initials: "CH"
  orcid: "0000-0001-2345-6789"   # leave as "" if you don't have an ORCID
  affiliation: "Aberystwyth University"
  review_date: "2026-06-01"      # YYYY-MM-DD format

dataset:
  name: "My Dataset Name"
  url: "https://www.ebi.ac.uk/arrayexpress/experiments/E-MTAB-1234/"
  hosting_resource: "ArrayExpress"
  accession: "E-MTAB-1234"
  comments: ""

process_comments: ""
```

---

## Step 4 — Answer the 27 questions

For each question, set `answer` to `"Yes"` or `"No"`:

```yaml
answers:
  ABC-01:
    answer: "Yes"
    comments: "Dataset is fully downloadable via FTP."
  ABC-02:
    answer: "Yes"
    comments: ""
  ABC-03:
    answer: "No"
    comments: "No integrity-checking mechanism provided."
```

!!! warning "Formatting rules"
    - `answer` must be exactly `"Yes"` or `"No"` — case-sensitive and quoted.
    - `comments` is optional — leave as `""` if you have nothing to add.
    - Do **not** delete any question block, even if the answer is `"No"`.
    - YAML is **indentation-sensitive** — do not mix tabs and spaces.

Work through all 27 question blocks (`ABC-01` through `ABC-27`). The full
question text and guidance for each ID is in
[`metric/airbds_metric_v0.4.yaml`](https://github.com/AIBIO-UK/airbds-metric/blob/main/metric/airbds_metric_v0.4.yaml).

!!! tip "Weight matters"
    Eight questions are marked **Critical** (80 pts each): `ABC-04, ABC-09,
    ABC-11, ABC-12, ABC-16, ABC-20, ABC-24, ABC-25`. Read the guidance
    carefully for these — failing one has a large impact on the grade.

---

## Step 5 — Handle Ethics questions (ABC-24 to ABC-27)

These four questions apply only to datasets containing **human or animal
subject data**.

!!! info "Does your dataset contain human or animal subjects?"

    === "No human or animal subjects"

        Set `not_applicable: true` and `answer: "Yes"` for each of `ABC-24` to `ABC-27`:

        ```yaml
          ABC-24:
            answer: "Yes"
            not_applicable: true
            comments: "No human or animal subject data in this dataset."
          ABC-25:
            answer: "Yes"
            not_applicable: true
            comments: ""
          ABC-26:
            answer: "Yes"
            not_applicable: true
            comments: ""
          ABC-27:
            answer: "Yes"
            not_applicable: true
            comments: ""
        ```

    === "Human or animal subjects present"

        Answer each of `ABC-24` to `ABC-27` normally (`"Yes"` or `"No"`) and leave `not_applicable: false`.

---

## Step 6 — Validate your YAML

Before calculating the score, check that your file is syntactically valid:

```bash
python3 -c "import yaml; yaml.safe_load(open('reviews/E-MTAB-1234_CH_1.yaml')); print('YAML is valid')"
```

If you see `YAML is valid`, proceed. If you see an error, it will show the line number.

**Common mistakes:**

| Symptom | Likely cause |
|---|---|
| `could not find expected ':'` | Missing colon after a key |
| `found character '\t'` | Tab used instead of spaces for indentation |
| `expected a block sequence entry` | `answer` value not quoted — write `"Yes"` not `Yes` |
| `mapping values are not allowed here` | Colon inside an unquoted string — quote the value |

---

## Step 7 — Calculate the score

There is no automated scorer yet — you calculate the score yourself. Each
question's points depend on its weight tier (fixed by the metric, not chosen
by the reviewer):

| Weight tier | Points | Questions |
|---|---|---|
| Critical | 80 | `ABC-04, 09, 11, 12, 16, 20, 24, 25` (8 total) — 640 pts max |
| Important | 5 | `ABC-01, 02, 05, 06, 07, 15, 17, 18, 19, 21, 26` (11 total) — 55 pts max |
| Optional | 2 | `ABC-03, 08, 10, 13, 14, 22, 23, 27` (8 total) — 16 pts max |

A `"No"` answer always scores 0. Sum the points for every `"Yes"` answer to
get your `weighted_score` (maximum possible: **711**).

The authoritative numbers live in the metric YAML's `grade_points` block; the
human-readable rationale is in
[`reviews/GUIDANCE.md`](https://github.com/AIBIO-UK/airbds-metric/blob/main/reviews/GUIDANCE.md).

---

## Step 8 — Determine the grade

A dataset earns the **highest** grade for which it meets *both* the pass-rate
requirement for every tier *and* that grade's minimum total score:

| Grade | Critical pass rate | Important pass rate | Optional pass rate | Minimum score |
|---|---|---|---|---|
| 🟡 **Gold** | 100% (8/8) | 100% (11/11) | ≥ 50% | ≥ 703 |
| ⚪ **Silver** | 100% (8/8) | ≥ 50% | any | ≥ 667.5 |
| 🟤 **Bronze** | ≥ 87.5% (≥ 7/8) | any | any | ≥ 560 |
| 🔴 **Caution** | below Bronze | any | any | any |

These thresholds are defined in the metric YAML's `grading` block and can
differ between metric versions — always check
[`metric/airbds_metric_v0.4.yaml`](https://github.com/AIBIO-UK/airbds-metric/blob/main/metric/airbds_metric_v0.4.yaml)
for the version you are scoring against.

Record the score and grade in the `result:` block at the bottom of your YAML file:

```yaml
result:
  weighted_score: 667.5
  grade: "Silver"
```

---

## Step 9 — Submit via pull request

```bash
# Create a feature branch
git checkout -b feat/add-review-E-MTAB-1234

# Stage your file
git add reviews/E-MTAB-1234_CH_1.yaml

# Commit
git commit -m "review: add review for E-MTAB-1234 (CH)"

# Push to your fork
git push -u origin feat/add-review-E-MTAB-1234
```

Then open a **pull request** on GitHub against the `main` branch of [AIBIO-UK/airbds-metric](https://github.com/AIBIO-UK/airbds-metric).

!!! info "Commit message convention"

    | Prefix | Use for |
    |---|---|
    | `review:` | Adding or updating a dataset review |
    | `metric:` | Changes to the metric YAML |
    | `docs:` | Documentation updates |
    | `fix:` | Typos, broken links, formatting |

For full contribution guidelines see [CONTRIBUTING.md](https://github.com/AIBIO-UK/airbds-metric/blob/main/CONTRIBUTING.md).

---

Well done — you have completed a dataset review in the deposit-ready YAML format! 🎉

Continue to [Further Resources](../follow_up_training.md) or return to the [About page](../index.md).
