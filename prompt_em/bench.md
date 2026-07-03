# bench.md - prompt_em Results

## Overview
| Name | Config (Iterations x Runs x Frames) | Optimized | Results (Median per Iteration) | Comment |
|---|---|---|---|---|
| E13 / em_v1 |  8 x 10 x 2000 | Both | 68.6, 39.8, 73.6, 67.6, 61.7, 63.6, 67.0, 53.5 | See experiment.md for more inforamtion |
| E14 / diag_template | 1 x 6 x 2000 | Neither | 74.64 | See experiment.md for more inforamtion |
| E15 / em_v2_template | 5 x 10 x 1000 | Both | 74.09, 74.75, 45.47, 73.64, 74.64 | See experiment.md for more inforamtion |
| E16 / em_v3_large | 16 x 10 x 1000 | Both | 73.09, 73.0, 74.41, 73.63, 73.42, 65.07, 75.94, 74.55, 75.03, 74.48, 75.77, 74.56, 75.05, 75.9, 73.9, 75.46 | See experiment.md for more inforamtion |
| wording_sequence | 16 x 10 x 1000 | Order | 74.61, 75.57, 74.12, 74.93, 74.67, 74.37, 74.6, 74.28, 74.92, 73.29, 74.42, 74.18, 72.96, 73.24, 74.77, 73.58 | Weights were frozen and not optimized|
| freeze_order | 16 x 10 x 1000 | Weights | 74.16, 72.94, 73.0, 75.54, 71.8, 50.3, 75.14, 75.09, 75.08, 74.49, 75.51, 75.09, 74.94, 74.88, 74.79, 75.57 | Order was frozen and not optimized|
| freeze_both | 4 x 10 x 1000 | Neither | 74.61, 74.16, 74.16, 74.16 | Aborted after 4 iterations|

## Findings
Refer to experiment.md for E13-E16.

- wording_sequence: TBA
- freeze_order: TBA
- freeze_both: While being fully deterministic in theory, produced a different result in iteration 0 as compared to iterations 1-3, which were identical. This may perhaps be a warm-up phenomenon, further investigation is needed.

## Further Work
- Ablation study: Running the suite multiple times, with exactly one heuristic eliminated in each full suite run, for every heuristic (16 x 16 x 10 x 1000).