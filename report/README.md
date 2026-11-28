# Scientific Report

This directory contains the formal scientific report resulting from the Splinter3D research project.

Its purpose is to present the research problem, scientific background, methodology, experimental results, analysis and conclusions in a structured academic document.

Unlike the research notebook and experimental studies, which preserve the research process, this directory contains the consolidated scientific findings.

The report should be progressively updated throughout the research process rather than written entirely at the end.

## Directory Structure

```text
report/
│
├── README.md
│
├── sections/
│   ├── 0_abstract.tex
│   ├── 1_introduction.tex
│   ├── 2_problem_definition.tex
│   ├── 3_state_of_the_art.tex
│   ├── 4_methodology.tex
│   ├── 5_results.tex
│   ├── 6_discussion.tex
│   └── 7_conclusion.tex
│
├── figures/
│   ├── diagrams/
│   ├── graphs/
│   └── screenshots/
│
├── main.tex
└── references.bib
```

---

## 1. `main.tex` — Main LaTeX Document

**Purpose:** Serve as the entry point of the scientific report.

This file defines the document configuration, imports the necessary packages, includes the different report sections and manages the bibliography.

Individual sections should be maintained in separate `.tex` files rather than being written entirely inside `main.tex`.

### Main structure

A basic structure is already written in [`main.tex`](main.tex).

*This is an initial example. Document configuration and bibliography style can be adapted as the report evolves.*

---

## 2. `sections/` — Scientific Report Sections

**Purpose:** Organize the scientific report into independent and logically structured chapters.

Each section should focus on a specific aspect of the research.

### Sections structure

| File | Purpose |
|---|---|
| `0_abstract.tex` | Provide a concise summary of the research. |
| `1_introduction.tex` | Introduce the research context, objectives and contributions. |
| `2_problem_definition.tex` | Define the problem and its technical and scientific challenges. |
| `3_state_of_the_art.tex` | Present existing approaches, scientific publications and related work. |
| `4_methodology.tex` | Explain the research methodology and experimental protocols. |
| `5_results.tex` | Present experimental measurements, tables and figures. |
| `6_discussion.tex` | Interpret results, compare findings and discuss limitations. |
| `7_conclusion.tex` | Summarize the research contributions and future work. |

Additional sections can be created when necessary.

### Guidelines

- Maintain a logical progression between sections.
- Use scientific and objective language.
- Support technical claims with appropriate references.
- Avoid duplicating information between chapters.
- Refer to experiments using their unique identifiers (`EXP-XXX`) when relevant.
- Keep detailed experimental procedures in `experiments/` and present their relevant methodology in the report.

---

## 3. `references.bib` — Bibliography

**Purpose:** Centralize all bibliographic references used throughout the scientific report.

This file uses the BibTeX format and allows LaTeX to automatically generate citations and the bibliography.

### BibTeX entry example

A basic exemple is already written in [`references.bib`](references.bib).

*This is an initial example.*

### Citing references

References are cited directly inside `.tex` files using their BibTeX identifiers.

```latex
Several approaches have been proposed
for mesh partitioning \cite{<ArticleId>}.
```

For exemple in here:

```bibtex
@article{smith2024mesh,
    author  = {John Smith and Alice Doe},
    title   = {Efficient Mesh Partitioning Algorithms},
    journal = {Journal of Computer Science},
    year    = {2024},
    volume  = {12},
    number  = {3},
    pages   = {45--62},
    doi     = {10.1234/example}
}
```

We have **ArticleId == smith2024mesh**.

### Guidelines

- Use descriptive and unique citation identifiers.
- Include complete bibliographic information whenever available.
- Prefer DOI links for scientific publications.
- Ensure that cited references exist in `references.bib`.
- Avoid manually writing the bibliography inside the report.
- Keep references consistent throughout the document.

---

## 4. `figures/` — Scientific Figures

**Purpose:** Store visual material used in the scientific report.

Figures should support explanations, illustrate technical concepts or present experimental findings.

### Directory organization

```text
figures/
│
├── diagrams/
├── graphs/
└── screenshots/
```

### Expected file formats

| Format | Usage |
|---|---|
| `.pdf` | Vector graphics, plots and technical diagrams. |
| `.svg` | Scalable vector diagrams and illustrations. |
| `.png` | Screenshots, mesh visualizations and raster graphics. |
| `.jpg`, `.jpeg` | Photographs and other raster images. |

### Guidelines

- Use descriptive filenames.
- Include figure captions and labels in LaTeX.
- Reference figures from the report text.
- Include units and descriptive axis labels in scientific graphs.
- Prefer vector formats for graphs and diagrams.
- Record the origin of externally sourced figures and respect their licensing conditions.

### Example of figure inclusion in LaTeX

```latex
\begin{figure}[htbp]
    \centering
    \includegraphics[width=0.8\textwidth]
        {figures/graphs/execution_time_vs_faces.pdf}
    \caption{Execution time as a function of mesh size.}
    \label{fig:execution-time}
\end{figure}
```

Figures generated during experiments can be reused here when they are relevant to the formal report.

---

## 5. Compilation and Generated Files

The report is compiled with the build script located in `scripts/`:

```bash
python scripts/compile_to_pdf.py
```

The final PDF is generated in:

```text
build/report/main.pdf
```

The script requires a LaTeX distribution (TeX Live, or MacTeX on macOS) with `latexmk` and `biber`. See [`scripts/README.md`](../scripts/README.md) for the installation instructions, all available options and other details.

---

## 6. LaTeX and BibTeX Documentation

The following resources provide tutorials and references for writing and maintaining the scientific report.

### LaTeX

- [Overleaf Learn LaTeX](https://www.overleaf.com/learn) — General introduction to LaTeX, document structure, formatting, tables, figures and mathematical equations.
- [LaTeX Project](https://www.latex-project.org/) — Official LaTeX project website and documentation.

### BibTeX

- [Overleaf — Bibliography Management with BibTeX](https://www.overleaf.com/learn/latex/Bibliography_management_with_bibtex) — Introduction to `.bib` files, citations and bibliography generation.
- [BibTeX.org](https://www.bibtex.org/) — Introduction to BibTeX and its bibliography format.

These resources should be used as references when creating or modifying `.tex` and `.bib` files.

---

## General Scientific Writing Guidelines

### Academic Writing

- Write the report in English.
- Use clear, precise and objective language.
- Avoid unsupported claims and subjective statements.
- Distinguish experimental observations from interpretations.
- Support scientific statements with appropriate references.
- Define technical terminology when first introduced.

### References and Citations

- Cite external research and scientific publications.
- Keep bibliographic information in `references.bib`.
- Ensure citations are correctly associated with their sources.
- Avoid plagiarism and acknowledge external contributions.

### Figures and Tables

- Number and caption all figures and tables.
- Reference them explicitly in the text.
- Include appropriate units and descriptions.
- Ensure that visualizations are readable and scientifically meaningful.

### Report Maintenance

- Update the report progressively as research advances.
- Keep individual sections independent.
- Avoid duplicating experimental data unnecessarily.
- Ensure that the final document can be compiled from the committed source files.
- Review references, figures and cross-references before publishing a final version.

---

## Relationship with Other Directories

- `notebook/`: Provides research notes, literature investigations, ideas and hypotheses.
- `experiments/`: Provides documented experimental methodologies, raw measurements and analyses.

The scientific report represents the structured outcome of the research, supported by the documentation and evidence maintained throughout the project.

---

## License

The contents of this directory are licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.

You are free to share and adapt this material, including for commercial purposes, provided that appropriate credit is given to the original author and any modifications are indicated.

See the [LICENSE](../LICENSE) file for the full license terms.

---
