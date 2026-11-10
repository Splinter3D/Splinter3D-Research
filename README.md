# Splinter3D Research

This repository contains the research, experiments, technical investigations and scientific documentation related to **Splinter3D**.

Its purpose is to maintain a structured and reproducible record of the research process, from initial hypotheses and literature studies to experimental results and the final scientific report.

## Repository Structure

```text
.
│
├── experiments/
├── notebook/
├── report/
│
└── README.md
```

Each directory has a specific purpose and follows its own documentation conventions.

---

## 1. `experiments/` - Experimental Studies

**Purpose:** Store and document individual experiments conducted during the research.

Each experiment must have its own directory, containing its methodology, raw results, observations and supporting material.

Experiments should be reproducible whenever possible. All relevant parameters, software versions and execution conditions must be documented.

### Expected file formats

| Format | Usage |
|---|---|
| `.md` | Experimental methodology, observations and analysis, notes |
| `.csv` | Raw experimental data and measurements |
| `.png`, `.jpg`, `.svg`, `.pdf` | Experimental figures, graphs and visualizations |

### Contents' Architecture

```text
experiments/
│
├── experiment_001/
│   ├── README.md
│   ├── methodology.md
│   ├── results.csv
│   ├── observations.md
│   └── figures/
│
└── experiment_002/
    └── ...
```

### Documentation

See [`experiments/README.md`](experiments/README.md) for experiment naming conventions, required documentation and reporting guidelines.

---

## 2. `notebook/` - Research Notes

**Purpose:** Centralize research notes, scientific literature, ideas, hypotheses and preliminary investigations.

This directory is intended for continuous documentation throughout the research process. It acts as a research journal and should be updated whenever relevant information is discovered.

### Expected file formats

| Format | Usage |
|---|---|
| `.md` | Research notes, literature reviews, hypotheses and technical documentation |
| `.pdf` | Supporting scientific papers or reference documents, when redistribution is permitted |

### Contents

- `Research_Notebook.md`: Chronological record of research activities, discoveries and decisions.
- `Literature_Review.md`: Summary and comparison of relevant scientific publications.
- `Ideas_and_Hypotheses.md`: Research questions, assumptions and ideas to investigate.
- `Notes.md`: Additional notes and observations that don't fit into other categories.

### Documentation

See [`notebook/README.md`](notebook/README.md) for detailed guidelines.

---

## 3. `report/` - Scientific Report

**Purpose:** Maintain the formal scientific report resulting from the research.

Unlike the research notebook, which records the research process chronologically, this directory contains a structured and progressively updated scientific document.

The report should present the research problem, relevant scientific background, methodology, experimental results, discussion and conclusions.

### Expected file formats

| Format | Usage |
|---|---|
| `.tex` | LaTeX document structure and scientific report sections |
| `.bib` | Bibliographic references in BibTeX format |
| `.pdf` | Compiled version of the scientific report |
| `.png`, `.jpg`, `.svg`, `.pdf` | Figures, graphs, screenshots and diagrams |

### Wanted Architecture

```text
report/
│
├── figures/
├── sections/
│
├── main.tex
├── README.md
└── references.bib
```

### Documentation

See [`report/README.md`](report/README.md) for LaTeX conventions, bibliography management, figure organization and compilation instructions.

---

## Research Workflow

The repository follows a continuous research and documentation workflow:

1. **Investigate:** Record scientific literature, technical discoveries and hypotheses in `notebook/`.
2. **Experiment:** Create a dedicated directory in `experiments/` for each experimental study.
3. **Analyze:** Process experimental results, generate visualizations and document observations.
4. **Document:** Integrate validated findings into the corresponding sections of `report/`.
5. **Refine:** Update the report as the research progresses.

The research notebook and experiment records preserve the history of the work, while the scientific report presents the consolidated findings.

## General Conventions

- Use Markdown (`.md`) for documentation.
- Write documentation and scientific content in English.
- Use descriptive and consistent file and directory names.
- Record dates using the `YYYY-MM-DD` format.
- Keep raw experimental data separate from processed results.
- Include relevant references for scientific claims and external resources.
- Document experiment configurations and software versions to support reproducibility.
- Keep each directory's README updated when its structure or conventions change.

---

## License

The contents of this directory are licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.

You are free to share and adapt this material, including for commercial purposes, provided that appropriate credit is given to the original author and any modifications are indicated.

See the [LICENSE](LICENSE) file for the full license terms.

---
