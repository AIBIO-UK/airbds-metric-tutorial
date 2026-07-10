# AIRBDS Metric — Tutorial Site

[![Tutorial site](https://img.shields.io/badge/Tutorial-GitHub%20Pages-orange)](https://AIBIO-UK.github.io/airbds-metric-tutorial/)
[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

Source for the interactive tutorial site for the [AIRBDS AI-Readiness Dataset Scoring Metric](https://github.com/AIBIO-UK/airbds-metric).

**Live site:** [AIBIO-UK.github.io/airbds-metric-tutorial](https://AIBIO-UK.github.io/airbds-metric-tutorial/)

Built with the [ELIXIR Training Lesson Template](https://zenodo.org/records/7913092) (van Geest G, Kronander E, Romero Herrera JA, Žlender N, ELIXIR Training Coordination Team & Cardona A, 2023; **CC BY-SA 4.0**; DOI: [10.5281/zenodo.7913092](https://doi.org/10.5281/zenodo.7913092)). Content has been replaced with the AIRBDS tutorial and AIBIO-UK branding applied. This tutorial is therefore also licensed **CC BY-SA 4.0**. Deployed automatically to GitHub Pages on every push to `main`.

## Local preview

```bash
pip install -r requirements.txt
mkdocs serve
```

Then open `http://localhost:8000/`.

## Using the metric

Two routes are covered by this tutorial:

- **Google Sheet** — make your own copy of the [live Google Sheet](https://docs.google.com/spreadsheets/d/1eriM8bXAoNXsIR9l8OpI1XYEp8FbtBWt05CTIP9cVeg/edit) (see [Chapter 2](https://AIBIO-UK.github.io/airbds-metric-tutorial/chapters/chapter_02_google_sheet/))
- **YAML** — copy the template embedded in [Chapter 3](https://AIBIO-UK.github.io/airbds-metric-tutorial/chapters/chapter_03_yaml/), matching the format of the canonical [`metric/airbds_metric_v0.4.yaml`](https://github.com/AIBIO-UK/airbds-metric/blob/main/metric/airbds_metric_v0.4.yaml) in [`airbds-metric`](https://github.com/AIBIO-UK/airbds-metric)

Both ask the same 27 questions and produce the same grade — pick whichever suits your workflow. There's no automated scorer or central submission process yet.
