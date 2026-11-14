# Next score plan

The current objective is accepted patches per evaluation budget. The evidence supports a staged, single-variable search.

## 1. Use the capacity result first

`58330973` keeps the measured fixed workflow and changes only the base model from 12B to 31B. If its public score rises materially above `0.05`, keep the 31B family and tune execution policy on that base. If it does not, do not infer that larger models are useless; inspect patch latency, timeout rate, and model-specific errors before changing prompts.

## 2. Test an early-patch policy

The next controlled prompt should add only these rules to the fixed workflow:

1. Read the issue and make one targeted localization call.
2. Read the exact source slice and its immediate caller.
3. Produce the first minimal **source-only** edit by call 8 or when 90 seconds have elapsed, whichever comes first.
4. Never edit tests, fixtures, dependency files, harness files, or generated artifacts.
5. After an edit, run `git diff --check` and one targeted check; a failed edit gets one exact re-read and one replacement attempt.
6. Reserve the final 60 seconds and four calls for the best patch, `get_status`, and `submit_patch`.

This is a delivery policy, not a claim about an optimal controller. Compare it with byte-identical fixed control on the same issues and record first-patch latency, accepted patches, no-patch rate, protected-file attempts, tool calls, and timeout rate.

## 3. Keep the search honest

Do not add Graph, EVI, staged subagents, LoRA, or test-witness machinery in the same experiment. The previous staged and adaptive variants did not beat the control. A candidate advances only if it improves accepted repairs on a fresh matched cohort or yields a clear reduction in no-patch failures without lowering acceptance.

## 4. Submission rule

Kaggle permits one submission per UTC day. Submit only a package that passes archive/path checks and has a recorded comparison against the current best candidate. Store every ZIP hash, submission reference, status, and score. The final two selected submissions should be chosen from measured leaderboard performance, with E4B considered separately for the small-model prize.
