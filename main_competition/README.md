# Main competition status

This directory records the public, reproducible status of the BEAR team's Gemma 4 Developer Agent submissions. It is deliberately separate from the frozen v6 paper snapshot.

The first official submission used Gemma 4 12B with the official starter prompt and scored **0.05** on the public leaderboard (`58289658`). A 23-issue offline audit found 9 accepted repairs for the official prompt, 9 for the fixed workflow, 9 for staged history, and 8 for compact staged verification. These are development results, not hidden-task estimates, and they do not establish a BEAR advantage.

On 2026-11-14 UTC, the team submitted a 31B fixed-workflow capacity follow-up (`58330973`). Its status and score are kept in [`submission_status.json`](submission_status.json). The candidate is pending/experimental until Kaggle returns a score.

- [`review.md`](review.md): measured evidence and failure modes.
- [`NEXT_SCORE_PLAN.md`](NEXT_SCORE_PLAN.md): the controlled experiments most likely to improve PASS rate.
- [`submission_58289658.zip`](submission_58289658.zip): the first 12B submission archive.
- [`submission_31b_fixed_20261114.zip`](submission_31b_fixed_20261114.zip): the 31B candidate archive, when copied into this release.

Private task text, hidden tests, reference patches, raw traces, credentials, and repository snapshots are intentionally excluded.
