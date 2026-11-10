# Experimental Studies

This directory contains the experimental studies conducted as part of the Splinter3D research project.

Each experiment must be documented in its own dedicated directory. The objective is to maintain a reproducible record of experimental procedures, configurations, measurements, observations and conclusions.

Experiments should be designed to investigate specific research questions or evaluate hypotheses identified during the research process.

Unlike the research notebook, which records general research activities, this directory focuses on structured and measurable investigations.

## Directory Structure

```text
experiments/
│
├── README.md
│
├── experiment_000_template/
│   ├── README.md
│   ├── methodology.md
│   ├── results.csv
│   ├── observations.md
│   └── figures/
...
├── experiment_001_[short-description]/
│   └── ...
...
```

Each experiment directory should contain the documentation and resources necessary to understand and reproduce the experiment.

---

## 1. Experiment Organization

### Naming Convention

Experiments must follow a consistent naming convention:

```text
experiment_XXX_short-description/
```

Examples:

- `experiment_001_mesh-size-impact/`
- `experiment_002_algorithm-comparison/`
- `experiment_003_memory-consumption/`

Each experiment receives a unique sequential identifier (`XXX`), which must never be reused.

### Experiment Identification

Every experiment must have a unique identifier:

```text
EXP-001
EXP-002
EXP-003
```

The identifier should be used when referencing the experiment in the research notebook or scientific report.

---

## 2. `README.md` — Experiment Overview

**Purpose:** Provide a quick overview of the experiment and its current status.

This file should allow someone to understand the experiment without immediately reading all its documentation.

### Recommended structure

```markdown
# EXP-XXX - [Experiment Title]

**Date:** YYYY-MM-DD
**Status:** Planned / In Progress / Completed / Inconclusive

## Objective
What is this experiment trying to investigate?

## Research Question
What specific question does it address?

## Hypothesis
What is expected to happen?

## Methodology
Brief description of the experimental approach.

## Main Results
Short summary of the most important findings.

## Files
- [methodology.md](methodology.md)
- [results.csv](results.csv)
- [observations.md](observations.md)

## Related Research
- [Related notebook entry]
- [Related experiments]
```

---

## 3. `methodology.md` — Experimental Methodology

**Purpose:** Document the experimental setup and procedure in sufficient detail to allow the experiment to be reproduced.

This file must describe how the experiment was conducted, including the input data, software environment, parameters and measurement methods.

### Recommended structure

```markdown
# Experimental Methodology

## 1. Objective

### Research Question
What question is being investigated?

### Motivation
Why is this experiment relevant?

### Hypothesis
What is expected to happen?

## 2. Experimental Setup

### Hardware
- CPU:
- RAM:
- GPU:

### Software
- Operating System:
- Splinter3D Version:
- Algorithm Version / Git Commit:
- Compiler:
- Build Configuration:

### Input Data
Describe the models or datasets used.

| Model | Vertices | Faces | File Size |
|---|---:|---:|---:|
| Model A | | | |
| Model B | | | |

## 3. Experimental Parameters

List all parameters and configurations used.

## 4. Procedure

Describe the experimental steps.

1. Step 1
2. Step 2
3. Step 3

## 5. Measurements

List the metrics collected.

- Execution time:
- Memory consumption:
- Number of vertices:
- Number of faces:
- Other metrics:

## 6. Reproducibility

- Number of executions:
- Warm-up executions:
- Measurement method:
- Relevant environmental conditions:
```

### Guidelines

- Document all relevant experimental parameters.
- Record the exact software version or Git commit whenever possible.
- Describe the input data sufficiently to identify it.
- Explain how measurements are collected.
- Avoid undocumented changes between experimental runs.

---

## 4. `results.csv` — Raw Experimental Data

**Purpose:** Store the raw numerical measurements collected during the experiment.

CSV is preferred because it is easy to process using Python, R, MATLAB, Excel and other scientific tools.

### Example structure

```csv
model,run,vertices,faces,execution_time_s,memory_mb
model_A,1,10000,20000,1.25,128
model_A,2,10000,20000,1.21,130
model_A,3,10000,20000,1.28,129
model_B,1,100000,200000,8.42,512
model_B,2,100000,200000,8.37,508
model_B,3,100000,200000,8.51,515
```

*These values are illustrative only.*

### Guidelines

- Keep one row per experimental run whenever possible.
- Use descriptive column names.
- Include measurement units in column names or document them explicitly.
- Do not replace raw measurements with averages.
- Keep processed data separate from the original measurements.
- Use consistent decimal notation and CSV delimiters.
- Document missing or invalid measurements rather than silently removing them.

If an experiment requires multiple datasets or measurement types, additional CSV files may be created.

Examples:

- `execution_times.csv`
- `memory_usage.csv`
- `mesh_statistics.csv`

---

## 5. `observations.md` — Results Analysis and Observations

**Purpose:** Document the observations, anomalies, interpretations and conclusions resulting from the experiment.

This file should distinguish measured results from personal interpretations.

### Recommended structure

```markdown
# Observations and Analysis

## 1. General Observations

Describe the main behaviours observed during the experiment.

## 2. Results Analysis

Identify trends, patterns and relationships between measured variables.

## 3. Unexpected Behaviours

Document anomalies, errors or unexpected results.

## 4. Hypothesis Evaluation

- Confirmed / Partially Confirmed / Rejected / Inconclusive

Explain the evaluation using experimental evidence.

## 5. Limitations

Identify factors that may affect the reliability or interpretation of the results.

## 6. Conclusion

Summarize the main findings.

## 7. Next Steps

List possible follow-up investigations.
```

### Guidelines

- Separate observations from interpretations.
- Support conclusions with actual measurements.
- Avoid claiming causality based only on correlation.
- Document unexpected or negative results.
- Identify limitations and potential sources of experimental error.

---

## 6. `figures/` — Experimental Visualizations

**Purpose:** Store figures and visualizations generated during the experiment.

Examples include:

- Execution time graphs.
- Memory consumption graphs.
- Mesh comparisons.
- Performance comparisons.
- Statistical distributions.
- Screenshots illustrating experimental results.

Expected file formats:

| Format | Usage |
|---|---|
| `.png`, `.jpg` | Screenshots and raster visualizations |
| `.svg`, `.pdf` | Vector graphs and diagrams |

Use descriptive filenames and include titles, axis labels and units in scientific graphs.

Figures intended for the formal scientific report can subsequently be copied or referenced in `report/figures/`.

---

## General Experimental Guidelines

### Reproducibility

- Record the hardware and software environment.
- Document the exact input data and experimental parameters.
- Preserve the original measurements.
- Record the number of executions and measurement procedure.
- Keep experiment scripts and relevant configurations.
- Record the Git commit associated with the tested implementation.

### Data Integrity

- Never overwrite original experimental measurements with processed results.
- Keep failed and incomplete runs when they provide useful information.
- Document exclusions and invalid measurements.
- Avoid manually modifying experimental results without recording the transformation.

### Scientific Integrity

- Do not discard results simply because they contradict the initial hypothesis.
- Distinguish experimental evidence from assumptions.
- Avoid conclusions that go beyond what the experiment demonstrates.
- Document limitations and potential sources of error.

### Relationship with Other Directories

- `notebook/`: Research questions and hypotheses can originate from the research notebook and lead to new experiments.
- `report/`: Validated experimental results, methodologies and analyses can be integrated into the formal scientific report.

Each experiment should provide enough information to understand what was tested, why it was tested, how it was tested and what was discovered.

---

## License

The contents of this directory are licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.

You are free to share and adapt this material, including for commercial purposes, provided that appropriate credit is given to the original author and any modifications are indicated.

See the [LICENSE](../LICENSE) file for the full license terms.

---
