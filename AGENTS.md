# Repository Guidelines

## Project Structure & Module Organization

The root Terraform files (`main.tf`, `variables.tf`, `outputs.tf`, and
`versions.tf`) compose the AWS RDS module. Reusable resource-specific modules
live under `modules/`, each with the same standard Terraform file layout.
`examples/` contains complete configurations for supported engines and
features. `wrappers/` provides Terraform and Terragrunt-friendly wrappers, while
`docs/` contains upgrade and maintenance notes. README sections between
`BEGIN_TF_DOCS` and `END_TF_DOCS` are generated; change the corresponding HCL
and let `terraform-docs` update them.

## Upstream Provenance

This is a derivative of `terraform-aws-modules/terraform-aws-rds` v7.2.1;
`UPSTREAM.md` records the pinned upstream commit, neutralization scope, and
update procedure. Preserve derivative notices on modified upstream-derived
paths. For upstream refreshes, follow that documented import process and keep
upstream Git history out of this repository.

## Build, Test, and Development Commands

There is no compiled build step:

- `terraform fmt -check -recursive` — verify canonical HCL formatting.
- `pre-commit run --all-files` — run formatting, wrapper, documentation,
  TFLint, validation, whitespace, and merge-conflict checks.
- `terraform init -backend=false` — initialize a root without configuring
  remote state.
- `terraform validate` — validate the initialized root module.
- `terraform -chdir=examples/complete-postgres validate` — validate a specific
  initialized example; substitute another module or example directory as needed.

Install the configured hooks with `pre-commit install` before regular work.
Terraform 1.11.1 or newer is required.

## Coding Style & Naming Conventions

Follow `.editorconfig`: UTF-8, LF line endings, final newlines, and two-space
indentation. Run `terraform fmt` instead of aligning HCL manually. Use
lowercase `snake_case` for variables, outputs, locals, and resource labels.
Keep module files organized as `main.tf`, `variables.tf`, `outputs.tf`, and
`versions.tf`; give public variables and outputs clear descriptions and types.
Avoid unrelated formatting or generated-document edits.

## Testing Guidelines

There are no standalone unit tests or coverage threshold. CI validates every
Terraform root at its supported minimum version and runs the full pre-commit
suite at the maximum version. Add or update the smallest relevant example for
behavioral changes, then run its initialization and validation plus
`pre-commit run --all-files`. Review `terraform plan` output when credentials
and safe disposable infrastructure are available; do not apply merely to test.

## Commit & Pull Request Guidelines

Recent history uses Conventional Commit subjects such as `feat: import ...`
and `docs: close ...`. Keep commits focused. PR titles must use `fix`, `feat`,
`docs`, `ci`, or `chore`, with a capitalized subject, for example
`fix: Preserve option-group defaults`. PR descriptions should summarize the
change, note compatibility or infrastructure impact, list validation performed,
and link relevant issues. Screenshots are unnecessary unless documentation has
a visual change.

## Security & Configuration Tips

Never commit credentials, `*.tfvars`, state files, override files, or local
Terraform configuration. Treat examples as potentially billable AWS
infrastructure and inspect plans carefully before any apply.
