# Certification-Readiness Rubric

Version 1.0 | Aligned with DO-178C development assurance levels and EASA AI Concept Paper Issue 2.

## Tiers

### Tier A — Auditable

Deterministic reasoning with complete, machine-checkable proof traces.

| Criterion | Evidence |
|-----------|----------|
| Every conclusion discharged by a formal reasoner (DL / SWRL / SHACL) | Yes — mandatory |
| Proof trace persistable and independently verifiable | Yes — mandatory |
| No stochastic components in the inference loop | Required |
| Expected DO-178C level | A / B |

### Tier B — Reviewable

Probabilistic reasoning with retrieval-grounded explanations whose faithfulness is measurable.

| Criterion | Evidence |
|-----------|----------|
| Retrieval provenance persisted | Required |
| Faithfulness metric reported (RAGAS / FActScore / SelfCheckGPT) | Required |
| Human-in-the-loop review point defined | Required |
| Expected EASA AI level | 1 / 2 |

### Tier C — Advisory

Black-box prediction with post-hoc attributions.

| Criterion | Evidence |
|-----------|----------|
| Post-hoc explanation method (SHAP, LIME, GNNExplainer, etc.) | Required |
| No formal safety guarantee | Acceptable |
| Decision-support role only; no autonomous safety action | Required |

### Tier D — Research-only

No systematic explanation mechanism; reported on benchmarks but not deployable in operational airspace.

## Coding protocol

1. Two coders independently read the abstract, methods, and evaluation sections of each primary study.
2. Each coder assigns a tier using the table above.
3. Disagreements are resolved through structured discussion; unresolved cases are arbitrated by a third coder.
4. Per-tier assignments and disagreements are logged in `data/PRISMA-corpus.csv`.

## Inter-rater agreement

Across the 24 primary aviation/UAM studies coded, Cohen's κ was 0.82 for the integration-depth layer and 0.78 for the certification-readiness tier, indicating substantial agreement.
