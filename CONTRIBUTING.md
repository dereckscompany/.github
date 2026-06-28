# Contributing

Thanks for your interest in contributing to a Dereck's Company project. This is the org-wide default; an individual repository may add its own `CONTRIBUTING.md` with specifics that take precedence.

## Ground rules

- Open an issue first for anything non-trivial, so the approach can be agreed before code is written.
- One logical change per pull request. For multi-part work, prefer **stacked PRs** (each based on the previous one) so every diff is reviewable in isolation.

## Pull requests

- Open the description with a short, **plain-English paragraph** explaining what the change does and why, before any technical detail.
- Make sure the tests and the formatter pass before requesting review.
- Report security issues **privately** to the maintainer; please don't open a public issue for them.

## Conventions and lessons

We keep our living conventions and the lessons we've learned in the org Discussions board — please skim the **Conventions & Lessons** category before contributing, and follow what's there:

https://github.com/orgs/dereckscompany/discussions

## Working with our R packages

Most of our R packages share one toolchain. Before you start:

- Install dependencies with renv: `renv::restore()`.
- Look in the `scripts/` folder and run them before you commit: `./scripts/FORMAT.sh` (formatting), `./scripts/LINT.sh` (linting), and `./scripts/TEST.R` (tests). Don't hand-format.
- We type our function inputs and outputs with **roxyassert** (built on **assert**) — please use them when you add or change a function:
  - https://github.com/dereckscompany/roxyassert
  - https://github.com/dereckscompany/assert
- Test fixtures must be **synthetic or scrubbed** — never commit real account data, balances, or API keys.

## Using our packages, and reporting problems

Our exchange and data packages are delivered **as is** (see DISCLAIMER.md), and we'd genuinely love for you to use and test them. If you hit a bug:

1. Capture the raw API response (or the exact error) you got.
2. Open a GitHub issue on that package and **paste the content in** — the more raw detail, the faster we can diagnose and fix it.
3. Even better, if you can see the fix, open a pull request. We welcome them.
