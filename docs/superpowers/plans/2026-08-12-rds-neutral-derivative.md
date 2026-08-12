# Neutral AWS RDS Module Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create a clean-history derivative of AWS RDS module v7.2.1, remove its nontechnical input from three creation controls and the wrapper, preserve default RDS behavior, and open a verified PR for reserved tag v7.2.1-neutral.1.

**Architecture:** Sanitize the exact upstream release outside the target before import. Replace only the three gated creation locals with their technical inputs, delete the variable and wrapper forwarding, repoint derivative-facing sources and the compatible S3 fixture, harden workflows, then validate all 26 Terraform roots and compare every HCL file with an explicitly transformed pristine checkout.

**Tech Stack:** Terraform 1.15.7, Terraform >= 1.11.1, AWS provider >= 6.28, HCL, terraform-docs 0.24.0, TFLint 0.64.0, actionlint 1.7.7, Git, GitHub CLI

## Global Constraints

- Worktree: `/Users/jroberts/Documents/dev/joeroberts/terraform/.worktrees/terraform-aws-rds/v7.2.1-neutral.1`.
- Branch: `neutral/v7.2.1-neutral.1`; PR base: `main`.
- Baseline: upstream `v7.2.1` at `9920097a40175c084c46fee1c306fa61cdbaf823`.
- Reserved tag: `v7.2.1-neutral.1`; never create or push it before review and merge.
- Preserve Apache 2.0, upstream authors/contributors, provider metadata, public outputs, and unrelated behavior.
- Every changed upstream-derived file begins with `Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md.` using its comment syntax.
- The three creation locals must depend only on `create_db_subnet_group`, `create_db_parameter_group`, and `create_db_instance`, respectively.
- Upstream v7.2.1 contains no `*.tftest.hcl`; three direct-expression assertions, full HCL parity, and 26-root init/validate are the focused behavioral tests.
- Do not migrate example dependencies across incompatible major versions. The RDS module itself depends only on local submodules; old IAM/Security Group example fixtures remain upstream because the planned neutral releases are not drop-in for those old APIs. The compatible S3 v5 fixture must use the published neutral S3 tag.
- Never import upstream Git history or copy disallowed material into a target commit.
- Push each milestone without force. If blocked, persist and push `docs/neutralization/BLOCKER.md`, open a draft PR if coherent, update the IAM journal, and finish the campaign report.

## File Map

- Import: complete upstream v7.2.1 tree except `.git/`.
- Modify before copy: `main.tf:2-4`, `variables.tf:669-673`, `wrappers/main.tf:99`, `README.md:5,334,401-405`.
- Modify after copy: `README.md`, `wrappers/README.md`, and six `wrappers/*/README.md` files — derivative sources, navigation, attribution boundary, notices.
- Modify after copy: `examples/s3-import-mysql/main.tf:129-130` — existing neutral S3 v5 tag and no Registry version constraint.
- Modify: five workflow files — notices, pins, permissions.
- Create: `UPSTREAM.md`.
- Preserve: all other HCL, including local root submodules and versioned external example fixtures.

---

### Task 1: Failing Acceptance Checks and Clean Import

**Files:**
- Modify: `main.tf`, `variables.tf`, `wrappers/main.tf`, `README.md`
- Create: `UPSTREAM.md`
- Import: remaining upstream files

**Interfaces:**
- Consumes: immutable v7.2.1 snapshot
- Produces: root interface with three independent technical creation controls and no nontechnical input

- [ ] **Step 1: Verify worktree and exact upstream**

```bash
test "$(git branch --show-current)" = "neutral/v7.2.1-neutral.1"
test "$(git remote get-url origin)" = "git@github.com:joeroberts/terraform-aws-rds.git"
test -z "$(git status --porcelain)"
rds_import_root=$(mktemp -d /private/tmp/terraform-aws-rds-v7.2.1.XXXXXX)
git clone --quiet --depth 1 --branch v7.2.1 \
  https://github.com/terraform-aws-modules/terraform-aws-rds.git \
  "$rds_import_root/source"
test "$(git -C "$rds_import_root/source" rev-parse HEAD)" = \
  "9920097a40175c084c46fee1c306fa61cdbaf823"
```

- [ ] **Step 2: Prove pristine interface and neutrality checks fail**

```bash
rds_neutral_pattern="$(printf '%s|%s|%s|%s|%s|%s|%s' \
  'put''in' 'khuy''lo' 'ukr''ain' 'russ''ia' 'bela''rus' 'cri''mea' 'don''bas')"
test -n "$(rg -l -i "$rds_neutral_pattern" "$rds_import_root/source" \
  --hidden --glob '!.git/**')"
for rds_expected in \
  'create_db_subnet_group    = var.create_db_subnet_group' \
  'create_db_parameter_group = var.create_db_parameter_group' \
  'create_db_instance        = var.create_db_instance'; do
  if rg -Fq "$rds_expected" "$rds_import_root/source/main.tf"; then exit 1; fi
done
```

Expected: forbidden matches exist and none of the three direct expressions exists.

- [ ] **Step 3: Apply exact neutralization in temporary storage**

Using `apply_patch`, replace pristine `main.tf:2-4` with:

```hcl
create_db_subnet_group    = var.create_db_subnet_group
create_db_parameter_group = var.create_db_parameter_group
create_db_instance        = var.create_db_instance
```

Delete `variables.tf:669-673`, delete `wrappers/main.tf:99`, delete the banner at
`README.md:5`, and delete final section `README.md:401-405`. Regenerate the root
README so input row 334 disappears:

```bash
go run github.com/terraform-docs/terraform-docs@v0.24.0 markdown table \
  --lockfile=false --output-file README.md --output-mode inject \
  "$rds_import_root/source"
```

Prepend the dated HCL notice to the three changed `.tf` files and the HTML notice
to `README.md`. Assert the three direct expressions and zero disallowed matches.

- [ ] **Step 4: Copy sanitized source and add provenance**

```bash
rsync -a --exclude .git "$rds_import_root/source/" ./
test -f main.tf
test -d modules
test -d examples
test -d wrappers
test -f docs/superpowers/plans/2026-08-12-rds-neutral-derivative.md
```

Create `UPSTREAM.md` with exact URL/tag/SHA/date/reserved tag, three creation
expressions, deleted input/wrapper/docs, unchanged-default statement, Apache
notice and attribution policy, explicit example-fixture scope, and an update
procedure requiring pre-copy sanitation, no upstream history merge, complete
validation/parity/neutrality/workflow checks, independent review, PR, then tag.

- [ ] **Step 5: Prove exact technical delta**

```bash
diff -u \
  <(git -C "$rds_import_root/source" show HEAD:main.tf | perl -pe 's/(create_db_(?:subnet_group|parameter_group|instance)\s+= var\.[A-Za-z0-9_]+) && var\.[A-Za-z0-9_]+/$1/') \
  <(sed '1d' main.tf)
diff -u \
  <(git -C "$rds_import_root/source" show HEAD:variables.tf | sed '669,673d' | perl -0pe 's/\n+\z/\n/') \
  <(sed '1d' variables.tf | perl -0pe 's/\n+\z/\n/')
diff -u \
  <(git -C "$rds_import_root/source" show HEAD:wrappers/main.tf | sed '99d') \
  <(sed '1d' wrappers/main.tf)
```

Expected: no output.

- [ ] **Step 6: Commit and push clean import**

```bash
terraform fmt -check -recursive
git diff --check
git add . ':!docs/superpowers'
git commit -m "feat: import neutral RDS module v7.2.1"
git push -u origin neutral/v7.2.1-neutral.1
```

---

### Task 2: Derivative Documentation and Compatible S3 Fixture

**Files:**
- Modify: `README.md`
- Modify: `wrappers/README.md`
- Modify: `wrappers/{db_instance,db_instance_automated_backups_replication,db_instance_role_association,db_option_group,db_parameter_group,db_subnet_group}/README.md`
- Modify: `examples/s3-import-mysql/main.tf`

**Interfaces:**
- Consumes: neutral RDS tree and existing S3 neutral tag
- Produces: eight RDS consumer documents plus one compatible neutral example dependency

- [ ] **Step 1: Prove upstream-facing sources exist**

```bash
test "$(rg -l 'terraform-aws-modules/rds/aws|tfr:///terraform-aws-modules/rds/aws' \
  README.md wrappers -g README.md | wc -l | tr -d ' ')" = "8"
test -n "$(rg -l 'terraform-aws-modules/s3-bucket/aws' examples/s3-import-mysql -g '*.tf')"
```

- [ ] **Step 2: Update root identity, navigation, and self-sources**

Add derivative identity and reserved-tag guidance after the root description.
Retain upstream maintainer/contributors, add `joeroberts` separately, use local
`LICENSE`, and point all 12 example links plus the five root-submodule links to
the target repository at `v7.2.1-neutral.1`.

Replace both root usage sources with:

```hcl
source = "git::ssh://git@github.com/joeroberts/terraform-aws-rds.git?ref=v7.2.1-neutral.1"
```

- [ ] **Step 3: Update seven wrapper documents**

For root `wrappers` and each of the six named subwrappers, replace Terraform,
Terragrunt, and commented alternatives with the exact target Git subdirectory at
`v7.2.1-neutral.1`. Prepend the dated HTML notice to all seven files.

Required form:

```bash
for rds_wrapper_path in wrappers wrappers/db_instance \
  wrappers/db_instance_automated_backups_replication \
  wrappers/db_instance_role_association wrappers/db_option_group \
  wrappers/db_parameter_group wrappers/db_subnet_group; do
  rds_wrapper_source="git::ssh://git@github.com/joeroberts/terraform-aws-rds.git//$rds_wrapper_path?ref=v7.2.1-neutral.1"
  printf '%s -> %s\n' "$rds_wrapper_path" "$rds_wrapper_source"
done
```

- [ ] **Step 4: Repoint the compatible S3 fixture only**

Replace `examples/s3-import-mysql/main.tf:129-130` with:

```hcl
source = "git::https://github.com/joeroberts/terraform-aws-s3.git?ref=v5.14.1-neutral.1"
```

Remove the Registry-only version argument and prepend the dated HCL notice.
Leave the old-major IAM and Security Group fixtures unchanged; document that
scope in `UPSTREAM.md` and the PR.

- [ ] **Step 5: Regenerate docs, assert sources, commit, and push**

```bash
while IFS= read -r rds_docs_dir; do
  go run github.com/terraform-docs/terraform-docs@v0.24.0 markdown table \
    --lockfile=false --output-file README.md --output-mode inject "$rds_docs_dir"
done < <(rg -l '<!-- BEGIN_TF_DOCS -->' -g README.md | xargs -n1 dirname | sort -u)
if rg -n 'source\s*=\s*"(terraform-aws-modules/rds/aws|tfr:///terraform-aws-modules/rds/aws)' \
  README.md wrappers -g README.md; then exit 1; fi
if rg -n 'terraform-aws-modules/s3-bucket/aws' examples/s3-import-mysql -g '*.tf'; then exit 1; fi
git diff --check
git add README.md wrappers examples/s3-import-mysql/main.tf
git commit -m "docs: point RDS consumers to neutral sources"
git push
```

---

### Task 3: Current-Generation Workflow Hardening

**Files:**
- Modify: all five inherited workflow files

**Interfaces:**
- Consumes: RDS's newer inherited action versions
- Produces: five permission maps, exact pins, actionlint-clean YAML, inert release automation

- [ ] **Step 1: Confirm unpinned refs and apply exact mapping**

```bash
test -n "$(rg -n -P 'uses:\s+[^\s#]+@(?![0-9a-f]{40}(?:\s|$))' .github/workflows)"
```

Apply with `apply_patch`, retaining version comments:

| Ref | SHA |
| --- | --- |
| `actions/checkout@v7` | `3d3c42e5aac5ba805825da76410c181273ba90b1 # v7` |
| `actions/setup-node@v7` | `820762786026740c76f36085b0efc47a31fe5020 # v7` |
| `actions/stale@v11` | `4391f3da665fdf50b6810c1a66712fb9ba21aa93 # v11` |
| `amannn/action-semantic-pull-request@v6.1.1` | `48f256284bd46cdaab1048c3721360e808335d50 # v6.1.1` |
| `clowdhaus/terraform-composite-actions/directories@v1.14.0` | `462243b714d762cbcac6732098e9fdb4ab236cb7 # v1.14.0` |
| `clowdhaus/terraform-composite-actions/pre-commit@v1.14.0` | `462243b714d762cbcac6732098e9fdb4ab236cb7 # v1.14.0` |
| `clowdhaus/terraform-min-max@v3.0.1` | `5e40f8cf535d84fbd031571abd363ffd81dbfbfc # v3.0.1` |
| `cycjimmy/semantic-release-action@v6.0.0` | `b12c8f6015dc215fe37bc154d4ad456dd3833c90 # v6.0.0` |
| `dessant/lock-threads@v6` | `89ae32b08ed1a541efecbab17912962a5e38981c # v6` |
| `jaxxstorm/action-install-gh-release@v3.0.0` | `25e24d2d23ae098373794ef1d6faecb48ee52da8 # v3.0.0` |

- [ ] **Step 2: Add notices, permissions, validate, commit, and push**

Prepend the dated YAML notice. Add top-level permissions:

- `lock.yml`: `issues: write`, `pull-requests: write`
- `pr-title.yml`: `pull-requests: read`
- `pre-commit.yml`: `contents: read`
- `release.yml`: `contents: read`
- `stale-actions.yaml`: `issues: write`, `pull-requests: write`

Retain the upstream-owner release guard, then run:

```bash
if rg -n -P 'uses:\s+[^\s#]+@(?![0-9a-f]{40}(?:\s|$))' .github/workflows; then exit 1; fi
test "$(rg -l '^permissions:' .github/workflows | wc -l | tr -d ' ')" = "5"
go run github.com/rhysd/actionlint/cmd/actionlint@v1.7.7
git diff --check
git add .github/workflows
git commit -m "ci: pin and restrict inherited workflows"
git push
```

---

### Task 4: Complete 26-Root Verification

**Files:**
- Verify: entire tree/history, all HCL, docs, workflows, and remote state
- Do not create: tracked state, lock, cache, or test files

**Interfaces:**
- Consumes: Tasks 1-3
- Produces: final verification record for independent review

- [ ] **Step 1: Stable docs, format, and TFLint 0.64.0**

```bash
while IFS= read -r rds_docs_dir; do
  go run github.com/terraform-docs/terraform-docs@v0.24.0 markdown table \
    --lockfile=false --output-file README.md --output-mode inject "$rds_docs_dir"
done < <(rg -l '<!-- BEGIN_TF_DOCS -->' -g README.md | xargs -n1 dirname | sort -u)
git diff --exit-code
terraform fmt -check -recursive
rds_tflint_tmp=$(mktemp -d)
curl -fsSL https://github.com/terraform-linters/tflint/releases/download/v0.64.0/tflint_darwin_arm64.zip -o "$rds_tflint_tmp/tflint.zip"
unzip -q "$rds_tflint_tmp/tflint.zip" -d "$rds_tflint_tmp"
"$rds_tflint_tmp/tflint" --recursive \
  --only=terraform_deprecated_interpolation --only=terraform_deprecated_index \
  --only=terraform_unused_declarations --only=terraform_comment_syntax \
  --only=terraform_documented_outputs --only=terraform_documented_variables \
  --only=terraform_typed_variables --only=terraform_module_pinned_source \
  --only=terraform_naming_convention --only=terraform_required_version \
  --only=terraform_required_providers --only=terraform_standard_module_structure \
  --only=terraform_workspace_remote
```

- [ ] **Step 2: Initialize and validate exactly 26 roots**

```bash
rds_plugin_cache=$(mktemp -d)
rds_root_count=0
while IFS= read -r rds_tf_dir; do
  rds_root_count=$((rds_root_count + 1))
  TF_PLUGIN_CACHE_DIR="$rds_plugin_cache" terraform -chdir="$rds_tf_dir" init -backend=false -input=false
  TF_PLUGIN_CACHE_DIR="$rds_plugin_cache" terraform -chdir="$rds_tf_dir" validate
done < <(rg --files -g versions.tf | xargs -n1 dirname | sort -u)
test "$rds_root_count" = "26"
```

Expected: root, examples, local modules, and wrappers validate without AWS operations.

- [ ] **Step 3: Full HCL parity and structural assertions**

```bash
rds_compare_root=$(mktemp -d /private/tmp/terraform-aws-rds-compare.XXXXXX)
git clone --quiet --depth 1 --branch v7.2.1 \
  https://github.com/terraform-aws-modules/terraform-aws-rds.git \
  "$rds_compare_root/upstream"
test "$(git -C "$rds_compare_root/upstream" rev-parse HEAD)" = \
  "9920097a40175c084c46fee1c306fa61cdbaf823"
while IFS= read -r rds_tf_file; do
  case "$rds_tf_file" in
    main.tf|variables.tf|wrappers/main.tf|examples/s3-import-mysql/main.tf) continue ;;
  esac
  diff -u "$rds_compare_root/upstream/$rds_tf_file" "$rds_tf_file"
done < <(git -C "$rds_compare_root/upstream" ls-files '*.tf' | sort)
diff -u \
  <(perl -pe 's/(create_db_(?:subnet_group|parameter_group|instance)\s+= var\.[A-Za-z0-9_]+) && var\.[A-Za-z0-9_]+/$1/' "$rds_compare_root/upstream/main.tf") \
  <(sed '1d' main.tf)
diff -u \
  <(sed '669,673d' "$rds_compare_root/upstream/variables.tf" | perl -0pe 's/\n+\z/\n/') \
  <(sed '1d' variables.tf | perl -0pe 's/\n+\z/\n/')
diff -u \
  <(sed '99d' "$rds_compare_root/upstream/wrappers/main.tf") \
  <(sed '1d' wrappers/main.tf)
diff -u \
  <(perl -0pe 's#  source  = "terraform-aws-modules/s3-bucket/aws"\n  version = "~> 5\.0"#  source = "git::https://github.com/joeroberts/terraform-aws-s3.git?ref=v5.14.1-neutral.1"#' "$rds_compare_root/upstream/examples/s3-import-mysql/main.tf") \
  <(sed '1d' examples/s3-import-mysql/main.tf)
for rds_expected in \
  'create_db_subnet_group    = var.create_db_subnet_group' \
  'create_db_parameter_group = var.create_db_parameter_group' \
  'create_db_instance        = var.create_db_instance'; do
  test "$(rg -Fc "$rds_expected" main.tf)" = "1"
done
```

Expected: only the four approved HCL files differ and each creation expression occurs once.

- [ ] **Step 4: Notices, workflow safety, neutrality/history, and clean remote**

```bash
rds_notice='Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md.'
for rds_notice_file in main.tf variables.tf wrappers/main.tf README.md \
  wrappers/README.md wrappers/*/README.md examples/s3-import-mysql/main.tf \
  .github/workflows/*; do
  head -n 1 "$rds_notice_file" | rg -Fq "$rds_notice"
done
go run github.com/rhysd/actionlint/cmd/actionlint@v1.7.7
rds_neutral_pattern="$(printf '%s|%s|%s|%s|%s|%s|%s' \
  'put''in' 'khuy''lo' 'ukr''ain' 'russ''ia' 'bela''rus' 'cri''mea' 'don''bas')"
if rg -n -i "$rds_neutral_pattern" . --hidden --glob '!.git/**' --glob '!.terraform/**'; then exit 1; fi
if git grep -nEi "$rds_neutral_pattern" $(git rev-list --all); then exit 1; fi
git diff --check
test -z "$(git status --porcelain)"
git fetch origin neutral/v7.2.1-neutral.1
test "$(git rev-parse HEAD)" = "$(git rev-parse origin/neutral/v7.2.1-neutral.1)"
test -z "$(git ls-remote --tags origin refs/tags/v7.2.1-neutral.1)"
```

---

### Task 5: Independent Review, Final PR, and Campaign Report

**Files:**
- Modify only for findings: Tasks 1-3 files
- Modify: IAM `docs/neutralization/CAMPAIGN-STATUS.md`
- External write: RDS GitHub PR

**Interfaces:**
- Consumes: Task 4 evidence and prior three campaign PRs
- Produces: fourth reviewed PR and complete persisted overnight campaign report

- [ ] **Step 1: Obtain fresh requirements and code-quality reviews**

Use `superpowers:requesting-code-review` with the design, plan, pristine release,
full diff, and all evidence. Require explicit review of the three independent
creation controls, removed interface, old-major fixture boundary, neutral S3
fixture, 26 validations, notices, workflow pins, clean history, and deferred
tag. Fix minimally, push, rerun Task 4, and re-review until clear.

- [ ] **Step 2: Create and read back the RDS PR**

Prepare `/private/tmp/terraform-aws-rds-pr-body.md` with provenance, intentional
deltas, fixture scope, validation evidence, independent review, and deferred
tag. Run:

```bash
gh pr create --repo joeroberts/terraform-aws-rds \
  --base main --head neutral/v7.2.1-neutral.1 \
  --title "feat: add neutral RDS module v7.2.1" \
  --body-file /private/tmp/terraform-aws-rds-pr-body.md
gh pr view --repo joeroberts/terraform-aws-rds \
  --json url,state,baseRefName,headRefName,commits,statusCheckRollup
```

- [ ] **Step 3: Complete and push the campaign journal**

Update the IAM journal with the RDS PR URL, final SHA, verification/review result,
and `tag deferred`. Confirm all four rows contain PR URLs or documented blockers,
branch SHAs, and next actions. Commit `docs: complete neutral module campaign
report`, push, read back all available PRs, and stop without merging or tagging.
