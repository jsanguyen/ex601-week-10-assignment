# EX601 Week 10 Assignment — CI with GitHub Actions

## Submission

**Green run screenshot:**

_(paste screenshot here)_

**In one sentence: what event started this run, and who started it?**

A push of a commit to `main` started this run, and Jonathan Nguyen started it.

## What's in this repo

| File | Purpose |
| --- | --- |
| `fee_calculator.py` | `cancellation_fee(hours_before)`: cancelling less than 24 hours before an appointment costs $25, while 24 hours or more ahead is free. Negative hours raise `ValueError`. |
| `test_fee_calculator.py` | pytest tests covering early cancellation, late cancellation, the exact 24-hour boundary, and negative input. |
| `.github/workflows/ci.yaml` | GitHub Actions workflow that runs the tests on every push. |

## Running the tests locally

```bash
pip install pytest
pytest
```

## How the CI pipeline works

Every push triggers the `CI` workflow, which:

1. Checks out the repo on a fresh `ubuntu-latest` machine.
2. Installs Python 3.12.
3. Installs pytest.
4. Runs `pytest`. If any test fails, this step fails and the whole run turns red.
