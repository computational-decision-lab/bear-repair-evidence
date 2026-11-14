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

## 2a. Minimal-tool candidate prepared for the next UTC submission window

The next local candidate is a 31B fixed-workflow package with six declared tools: `run_command`, `read_file`, `edit_file`, `get_status`, `search_similar_code`, and `submit_patch`. It removes `write_file`, the unused graph tools, and the unreferenced skill adviser. This is motivated by the reviewed traces: the fixed policy made 21 `write_file` calls across the 23-issue cohort, while every public reference patch changed existing files and none required a new scratch file. The candidate also makes the early-patch, exact-edit, source-only, and final-submit rules explicit.

The package is stored as `submission_31b_minimal_20261115.zip`. It has not been submitted or scored. Removing tools can reduce capability on unusual tasks, so it advances only after a matched experiment or an informative leaderboard result.

## 2b. Source-first 31B candidate prepared

The follow-up candidate `submission_31b_source_first_20261115.zip` keeps the six-tool source-only interface and raises the per-task operational ceiling to 60 calls while retaining the four-minute wall-clock budget. Its prompt removes the unavailable skill/graph instructions, requires the first edit by call 4 (and never later than call 8), permits one narrow `run_command` edit fallback after an exact `edit_file` mismatch, and reserves the final 45 seconds for diff review and submission. This is a hypothesis about delivery reliability, not a measured score gain; the archive has not been submitted.

## 3. Keep the search honest

Do not add Graph, EVI, staged subagents, LoRA, or test-witness machinery in the same experiment. The previous staged and adaptive variants did not beat the control. A candidate advances only if it improves accepted repairs on a fresh matched cohort or yields a clear reduction in no-patch failures without lowering acceptance.

## 4. Submission rule

Kaggle permits one submission per UTC day. Submit only a package that passes archive/path checks and has a recorded comparison against the current best candidate. Store every ZIP hash, submission reference, status, and score. The final two selected submissions should be chosen from measured leaderboard performance, with E4B considered separately for the small-model prize.
