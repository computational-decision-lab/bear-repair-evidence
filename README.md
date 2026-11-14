# BEAR: When Passing Checks Do Not Verify Repository Repairs

**An executable evidence contract and budget audit for small Gemma 4 agents**

[Read the paper (PDF)](paper.pdf) · [Read the manuscript](paper.md) · [Download LaTeX](latex_source.zip)

A repair agent can pass its own check without checking its repair. BEAR makes source identity, starting-to-current behavior, assertion execution, and a limited result link inspectable. The paper reports designed conformance, real-check applicability, and externally tested repair as separate endpoints.

This is the v6 manuscript and companion resource for the Google Gemma 4 Developer Agent Paper Track. It contains 2,921 wordlike tokens including references, fifteen references, and eight PDF pages. Public hosting is independent of formal Kaggle Writeup submission.

## What the evidence supports

The registered 64-case designed study retains 16/16 supported positive checks and rejects 36/36 specified mechanical negatives. Eight known semantic/dataflow counterexamples still certify, and four valid helper-based checks abstain. Retrospective replay supports 0/10 original real-check shapes and does not improve the comparator judgments. Nine exploratory architecture rounds reuse six issues; 162 assignments are not 162 independent tasks. General repair superiority, causal verification benefit, and a calibrated compute policy remain unestablished.

## Reproduce the resource

Download [the companion archive](resources/bear_paper_review_v6.zip), extract it, and run:

```bash
python reproduce.py
```

Python 3.10 or newer suffices. This checks payload hashes and derived counts and paired arithmetic. It does not rerun model inference or independently annotate the underlying traces.

For an installable, dependency-free diagnostic API/CLI and all 64 designed fixtures, download [bearcheck 0.3.3](resources/bearcheck_0_3_3.zip), extract it separately, and follow its README. Its own `python reproduce.py` reruns generic fixtures from source. These fixtures do not establish real-world repair gains.

No official problem statements, reference patches, hidden tests, model weights, raw agent trajectories, private replay bodies, credentials, or third-party repository snapshots are redistributed. The published materials contain original source, generic fixtures, and content-limited derived measurements.

## Main competition follow-up

The first official 12B submission scored 0.05 (`58289658`). A 31B fixed-workflow follow-up was submitted on 2026-11-14 (`58330973`) and is recorded as pending in [`main_competition/submission_status.json`](main_competition/submission_status.json). The development audit found no reliable BEAR architecture advantage; the next experiments therefore target patch-delivery reliability and model capacity. See [`main_competition/NEXT_SCORE_PLAN.md`](main_competition/NEXT_SCORE_PLAN.md) and the related Kaggle opportunity in [`opportunities/KAGGLE_20261114.md`](opportunities/KAGGLE_20261114.md).

## Version and publication status

This repository publishes the previously private v6 review snapshot, without changing its measured results. Statements in the frozen manuscript and archive about private preparation describe their pre-release status; this repository is the subsequent public release. Prospective evaluations are not reported in this manuscript. The v6 companion has been extracted and checked locally; earlier separate-environment reproduction applies to its inherited v5 evidence and generic fixtures, not a new remote v6 run.

The original BEAR source and manuscript material use Apache-2.0; third-party materials retain their own terms. See [LICENSE](LICENSE) and [third-party notices](THIRD_PARTY_NOTICES.md).
