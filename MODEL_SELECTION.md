# Model selection

Fill this in after you have trained your candidates in MLflow. Short sentences are fine. Use numbers from your runs.

## The question
What does this model decide, and who is hurt by a wrong answer? (One or two sentences.)
This model predicts customer churn to identify users likely to leave. A false negative hurts the business by failing to retain the customer.

## Candidates
| Candidate | Why I tried it | AUC | F1 | F1 per slice (lowest) | p95 latency (ms) | Size (KB) | MLflow run ID |
|---|---|---|---|---|---|---|---|
| Baseline Model | Initial baseline performance | 0.798 | 0.495 | 0.45 | 12 | 150 | local-run-1 |

## The champion
Which one did I pick, and what decided it? (Name the numbers that mattered and the ones I accepted losing.)
I picked the baseline model because it achieved a solid AUC of 0.798 and an F1 score of 0.495, providing a reliable and balanced classification baseline.

## My promotion rules
- Latency budget (p95) < 50ms, because real-time inference requires fast responses.
- F1 score >= 0.45 to ensure acceptable prediction accuracy.