# Evidence review

The first official score is 0.05. The offline 23-issue cohort was reviewed before selecting the public control. It contains 92 assignments across four policies, with the same 12B model, seed, tool budget, and 240-second task limit.

| Policy | Accepted | No patch | Rejected or review-needed |
|---|---:|---:|---:|
| Fixed workflow | 9/23 | 7 | 7 |
| Official prompt | 9/23 | 8 | 6 |
| Staged history | 9/23 | 9 | 6 |
| Staged compact | 8/23 | 11 | 4 |

The fixed workflow ties for the highest accepted count and has fewer no-patch outcomes than the official prompt. Staged compact is worse. The difference is exploratory and not statistically reliable; it is not evidence that BEAR improves repair.

The dominant failure modes are repeated navigation until timeout, a first source edit arriving too late, invalid exact edits followed by repeated retries, protected test-file edits, and verification that starts after the useful budget has been spent. The next intervention therefore targets delivery reliability before adding retrieval or multi-agent machinery.

The 12B public score is an external hidden-task result. The 23-issue table is a development audit and must not be substituted for leaderboard performance. The 31B candidate is a capacity follow-up, not a claimed win.
