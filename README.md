# Review sandbox

This repository is the sandbox for the lab in [AICodeReviewer](https://github.com/Darko-Martinovic/AICodeReviewer). It holds code changes that AI reviewers are asked to review on GitHub, so their comments can be scored against known defects.

## How it is organised

- Each pull request is one case from version 1 of the lab's labelled dataset. There are 28 cases in C#, SQL and TypeScript. A few cases contain no defects, which shows how often a reviewer reports a problem where there is none.
- Each pull request has its own base branch (`base-change-01` to `base-change-28`). The base branch holds the code before the change, or nothing if the change adds a new file. The pull request branch (`change-01` to `change-28`) brings the version under review.
- Branch names and pull request titles say nothing about the defects, so the reviewer only sees the change itself.
- The file [`lab/sandbox/v1.json`](https://github.com/Darko-Martinovic/AICodeReviewer/blob/main/lab/sandbox/v1.json) in the main repository says which pull request holds which case. The expected defects are in the dataset there, not in this repository.

## Reviews so far

| Date | Reviewer | Recall | Precision | F1 |
|---|---|---|---|---|
| 2026-10-29 | The lab's own reviewer (Claude Haiku 5.5) | 85% | 89% | 0.87 |
| 2026-11-02 | GitHub Copilot code review | 85% | 91% | 0.88 |

Each reviewer's line comments are on the pull requests. Only line comments are scored. Because GitHub accepts line comments only on lines in the diff, a defect on an unchanged line can only be mentioned in a review's summary, and those mentions are not counted. The rule is the same for every reviewer. The lab's [README](https://github.com/Darko-Martinovic/AICodeReviewer/blob/main/lab/README.md) explains how the comments are graded and what the results show.

## Reading the comments

The comments by `Darko-Martinovic` were posted by the lab's own reviewer, which uses the repository owner's GitHub account. The comments by `Copilot` come from GitHub Copilot code review.
