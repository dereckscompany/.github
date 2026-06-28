# Contributing

Thanks for your interest in contributing to a Dereck's Company project. This is the org-wide default; an individual repository may add its own `CONTRIBUTING.md` with specifics that take precedence.

## Ground rules

- Open an issue first for anything non-trivial, so the approach can be agreed before code is written.
- One logical change per pull request. For multi-part work, prefer **stacked PRs** (each based on the previous one) so every diff is reviewable in isolation.

## Pull requests

- Open the description with a short, **plain-English paragraph** explaining what the change does and why, before any technical detail.
- Keep markdown prose to one line per paragraph/bullet — no manual hard-wrapping.
- Make sure the tests and the formatter pass before requesting review.
- Report security issues **privately** to the maintainer; please don't open a public issue for them.

## Conventions

Our living conventions and lessons are kept in the org Discussions board ("Conventions & Lessons") — please skim it; new code is expected to follow it. For example: throw **typed conditions** (classed `rlang::abort(...)`) rather than bare error strings, so callers can react by type.

## R packages

Most of our R packages share one toolchain, scaffolded from `templates-cookiecutter` and kept in sync with cruft:

- Install dependencies with renv: `renv::restore()`.
- Format before committing: `./scripts/FORMAT.sh` (air for R, jq for JSON) — don't hand-format.
- Lint with `./scripts/LINT.sh`; run tests with `./scripts/TEST.R`.
- Type every `@param` and `@return` with roxyassert grammar (not prose), then regenerate docs and contracts with `devtools::document()`.
- Test fixtures must be **synthetic or scrubbed** — never commit real account data, balances, or API keys.
- Project-level files (scripts, lint config, CI) are managed by the cookiecutter template — change the template, not the generated copy.
