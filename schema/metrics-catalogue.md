# UAM-Bench v0 Metrics Catalogue

Eight metrics span three families.

## Predictive (3 metrics)

| Metric | Symbol | Definition | Notes |
|--------|--------|------------|-------|
| Accuracy / F1 | $\mathrm{acc}$, $F_1$ | Conflict classification | Report both, since classes are imbalanced |
| Trajectory MAE | $\mathrm{MAE}_{4D}$ | Mean absolute error on 4-D trajectory forecasts (m + s) | Per-axis + aggregate |
| Temporal-KG MRR | $\mathrm{MRR}_{\mathrm{TKG}}$ | Mean reciprocal rank over quadruple forecasting | Evaluated per lead-time window |

## Explanatory (3 metrics)

| Metric | Symbol | Definition | Notes |
|--------|--------|------------|-------|
| Rule-Alignment Rate | RAR | Fraction of claims in the explanation that align with a retrieved rule | Requires an authoritative rule base |
| Unsupported-Claim Rate | UCR | Fraction of claims with no retrieved backing | Complement of RAR for disjoint proxies |
| RAGAS faithfulness | $\mathrm{RAGAS}_F$ | Faithfulness score from the RAGAS toolkit | Computed per scenario |

## Systems (2 metrics)

| Metric | Symbol | Definition | Notes |
|--------|--------|------------|-------|
| p95 latency | $\ell_{95}$ | 95th-percentile end-to-end latency | Target: airborne tier $\le 250$ ms |
| Scalability | $\sigma$ | Throughput degradation vs. scenario density | Report curve for densities 1, 10, 100 vehicles/cell |

## Optional robustness add-on

* Adversarial robustness under knowledge poisoning: success rate against relation-inference attacks (Bhardwaj et al., ACL-IJCNLP 2021).

## Reporting rule

Baselines must report all three families (≥1 metric each). Submissions that omit any family are flagged in the public leaderboard.
