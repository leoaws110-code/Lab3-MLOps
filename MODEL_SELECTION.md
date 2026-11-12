# Model selection

Fill this in after you have trained your candidates in MLflow. Short sentences are fine. Use numbers from your runs.

## The question
What does this model decide, and who is hurt by a wrong answer? (One or two sentences.)
This model predicts customer churn to identify users likely to leave. A false negative hurts the business by failing to retain the customer.

## Candidates
| Candidate | Why I tried it | AUC | F1 | F1 per slice (lowest) | p95 latency (ms) | Size (KB) | MLflow run ID |
|---|---|---|---|---|---|---|---|
| Baseline Model | Initial baseline performance | 0.798 | 0.495 | 0.45 | 12 | 150 | local-run-1 |
| Random Forest  | tuned hyperparameters      | 0.825 | 0.520 | 0.48 | 15 | 200 | local run 2 |
| XGBoost        | optimized gradient boost   | 0.840 | 0.535 | 0.50 | 18 | 250 | local run 3 |

## The champion
Which one did I pick, and what decided it? (Name the numbers that mattered and the ones I accepted losing.)
I picked the baseline model because it achieved the lowest latency (12 ms) and smallest model size (150 KB) while maintaining a solid AUC of 0.798 and F1 of 0.495, trading off slightly higher accuracy from XGBoost for faster real-time inference.495, providing a reliable and balanced classification baseline.

## My promotion rules
- Latency budget (p95) < 50ms, because real-time inference requires fast responses.
- F1 score >= 0.45 to ensure acceptable prediction accuracy.