# Research Notebook

This directory centralizes the research notes, scientific literature, hypotheses, ideas and preliminary investigations related to Splinter3D.

It serves as a chronological and exploratory record of the research process. Its purpose is to preserve useful information, document discoveries and provide a foundation for future experiments and scientific writing.

Unlike the formal scientific report, the notebook does not need to follow a strict academic structure. It should prioritize clarity, traceability and completeness.

## Directory Structure

```text
notebook/
│
├── README.md
│
├── Research_Notebook.md
├── Literature_Review.md
├── Ideas_and_Hypotheses.md
└── Notes.md
```

---

## 1. `Research_Notebook.md` - Research Journal

**Purpose:** Maintain a chronological record of research activities, discoveries, investigations and important decisions.

This file should be updated continuously throughout the research process.

Each entry should have a date and a descriptive title.

### Recommended entry structure

```markdown
# Research Notebook

## [YYYY-MM-DD] - [Research Subject]

### Objective
What am I trying to understand or investigate?

### Background
What led to this investigation?

### Research / Activities
What did I study, implement or investigate?

### Findings
What did I discover?

### References
- [Relevant sources]

### Next Steps
What should I investigate next?
```

### What to document

- Scientific and technical discoveries.
- Preliminary investigations.
- Important architectural or algorithmic decisions.
- Problems encountered and possible explanations.
- Relevant discussions and research directions.
- Links between different investigations.

Entries should be concise but sufficiently detailed to understand the context later.

---

## 2. `Literature_Review.md` - Scientific Literature

**Purpose:** Collect, summarize and compare scientific publications, research papers and technical resources relevant to Splinter3D.

Each publication should be documented individually, allowing its contributions and limitations to be understood without having to reread the entire paper.

### Recommended entry structure

```markdown
## [Publication Title]

**Authors:** [Authors]
**Year:** [Publication Year]
**DOI / URL:** [Link]
**Publication type:** Journal / Conference / Thesis / Other

### Research Objective
What problem does the publication address?

### Methodology
What methods, algorithms or approaches are proposed?

### Main Contributions
What are the most important findings or contributions?

### Limitations
What are the limitations or unresolved problems?

### Relevance to Splinter3D
How can this publication contribute to the research?

### Personal Remarks
Questions, observations or ideas inspired by this publication.
```

### Guidelines

- Prefer peer-reviewed scientific publications when available.
- Record complete bibliographic information.
- Distinguish the authors' conclusions from personal interpretations.
- Include relevant page numbers or sections when referencing specific findings.
- Use `references.bib` in the `report/` directory for formal LaTeX citations.

Do not simply collect papers: the objective is to understand, compare and evaluate existing approaches.

---

## 3. `Ideas_and_Hypotheses.md` - Research Directions

**Purpose:** Record research questions, preliminary ideas, assumptions and hypotheses that may lead to future investigations.

This file is exploratory. Ideas do not need to be validated before being documented.

### Recommended entry structure

```markdown
## [Idea / Hypothesis Title]

**Date:** [YYYY-MM-DD]
**Status:** Proposed / Under Investigation / Validated / Rejected

### Description
What is the idea or hypothesis?

### Motivation
Why is this worth investigating?

### Expected Outcome
What do I expect to observe?

### Verification
How could this hypothesis be tested?

### Related Research
- [Related publications or notebook entries]

### Conclusion
To be completed once investigated.
```

### Guidelines

- Keep hypotheses separate from experimentally confirmed results.
- Update their status as research progresses.
- Link relevant experiments when an idea is investigated.
- Do not discard rejected hypotheses: they are part of the research history.

---

## 4. `Notes.md` - Additional Notes

**Purpose:** Store supplementary information that does not naturally belong in the other notebook files.

This file can contain:

- Technical explanations and definitions.
- Useful mathematical concepts.
- Algorithmic details.
- Terminology and vocabulary.
- Interesting references that still need investigation.
- General observations and miscellaneous notes.

**For larger topics, consider creating a dedicated Markdown file rather than allowing this document to become excessively long.**

---

## General Guidelines

### Documentation

- Write all documentation in English.
- Use Markdown (`.md`) for notes and documentation.
- Use descriptive headings and consistent formatting.
- Date research entries using `YYYY-MM-DD`.
- Include references and links whenever external information is used.
- Prefer concise explanations over unstructured blocks of text.

### Research Integrity

- Clearly distinguish facts, hypotheses and personal interpretations.
- Never present an unverified assumption as an established result.
- Preserve relevant negative findings and rejected hypotheses.
- Record the origin of information to ensure traceability.
- Avoid copying scientific publications directly; summarize and cite them appropriately.

### Relationship with Other Directories

The notebook is connected to the other parts of the repository:

- `experiments/`: Ideas and hypotheses can lead to dedicated experimental studies.
- `report/`: Validated findings, literature analysis and relevant conclusions can be integrated into the scientific report.

The notebook preserves the research process; the experimental directories document how investigations were conducted; the scientific report presents the consolidated results.

---

## License

The contents of this directory are licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.

You are free to share and adapt this material, including for commercial purposes, provided that appropriate credit is given to the original author and any modifications are indicated.

See the [LICENSE](../LICENSE) file for the full license terms.

---
