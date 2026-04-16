# UAM-KG-NeuroSym Artifacts

Reproducibility artefacts accompanying the manuscript

**"Knowledge Graph-Driven Neuro-Symbolic Reasoning for Trustworthy Urban Air Mobility: Foundations, Advances, and Challenges"**

submitted to *Knowledge-Based Systems* (Elsevier).

This repository makes the survey's methodology, corpus, coding rubric, and benchmark blueprint openly available so that readers can replicate the literature analysis and extend the UAM-Bench v0 specification.

---

## Why this repository exists

The survey assesses 24 aviation/UAM-specific primary studies and 79 foundational references selected through a systematic, two-stage screening protocol inspired by PRISMA. Rather than asking reviewers to take our counts on trust, we release:

1. the full **search log** (seven databases, Boolean queries, retrieval dates, result counts);
2. the **PRISMA-compatible corpus record** with per-study screening decisions, taxonomic-layer assignments, and certification-readiness tiers;
3. the **certification-readiness rubric** with two-coder inter-rater agreement statistics;
4. the **UAM-Bench v0 schema** (JSON Schema + example scenario) so that the community can begin building compatible datasets immediately.

## Repository layout

```
.
├── README.md                         # This file
├── LICENSE                           # CC-BY-4.0 for documents, MIT for code
├── data/
│   ├── PRISMA-corpus.csv             # 103 references with screening metadata
│   └── search-log.csv                # Per-database queries and result counts
├── queries/
│   ├── ieee-xplore.txt               # Full IEEE Xplore Boolean query
│   ├── acm-dl.txt
│   ├── springer-link.txt
│   ├── elsevier-sciencedirect.txt
│   ├── wos-core.txt
│   ├── scopus.txt
│   └── arxiv.txt
├── rubric/
│   ├── certification-readiness-rubric.md
│   └── two-coder-agreement.md
└── schema/
    ├── UAMBench-v0.schema.json       # Machine-readable schema
    ├── example-scenario.json         # Illustrative scenario record
    └── metrics-catalogue.md          # Specifications for the eight metrics
```

## Using the artefacts

### Replicate the corpus selection

1. Run the Boolean query stored in each `queries/*.txt` against the corresponding database on or after March 2026.
2. Import the returned records into a reference manager and remove duplicates via DOI matching.
3. Cross-check your outputs against `data/search-log.csv` (exact retrieval counts) and `data/PRISMA-corpus.csv` (final inclusion set).

### Extend UAM-Bench v0

1. Consult `schema/UAMBench-v0.schema.json` for the mandatory fields across the four schema layers (telemetry, environment, knowledge graph, regulatory).
2. Mirror the structure of `schema/example-scenario.json` when creating new scenarios.
3. Report the eight metrics defined in `schema/metrics-catalogue.md` so results remain cross-comparable.

### Apply the certification-readiness rubric

`rubric/certification-readiness-rubric.md` defines the four-tier rubric (Auditable / Reviewable / Advisory / Research-only) mapped against DO-178C development assurance levels and the EASA AI concept paper Level 1/2 guidance. `rubric/two-coder-agreement.md` records the coder training protocol and the Cohen's κ computation.

## Citation

If you use these artefacts, please cite the survey:

```bibtex
@article{liu2026uamkg,
  title  = {Knowledge Graph-Driven Neuro-Symbolic Reasoning for Trustworthy Urban Air Mobility: Foundations, Advances, and Challenges},
  author = {Liu, Yushu and Wang, Longbiao},
  journal= {Knowledge-Based Systems},
  year   = {2026},
  note   = {Under review}
}
```

## Licensing

* Documentation, CSV/JSON assets, and rubrics: **Creative Commons Attribution 4.0 (CC-BY-4.0)**.
* Any future source code added under `scripts/`: **MIT License**.

## Contact

Correspondence: YUSHU LIU <liuyushu@tju.edu.cn>
(Tianjin Key Laboratory of Cognitive Computing and Application, School of Artificial Intelligence, Tianjin University.)

Issues and pull requests are welcome. We especially encourage contributions that:

* add operationally labelled UAM scenarios conformant with UAM-Bench v0;
* supply certified rule bases (SWRL/SHACL) aligned with FAA or EASA regulations;
* report baseline results using the eight-metric family.
