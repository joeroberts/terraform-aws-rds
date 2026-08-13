# Neutral AWS RDS Module Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create a clean-history neutral derivative of AWS RDS module v7.2.1, remove its nontechnical creation gate and political repository content, preserve technical behavior, and open a verified PR for reserved tag v7.2.1-neutral.1.

**Architecture:** Verify and archive the exact upstream tag outside the target, build and independently bind a sanitized 147-file import before the first copy, then update only the enumerated consumer documents, compatible S3 fixture, inherited workflows, and pre-commit configuration. Fail-closed manifests bind every upstream path and HCL byte; generation, wrapper dry-run, lint, 26-root validation, neutrality, history, remote, review, PR, and IAM-journal gates each use fresh task-owned storage.

**Tech Stack:** Bash 3.2, Git, GitHub CLI, Ruby YAML, Terraform exact local 1.15.7, upstream Terraform minimum unchanged, terraform-docs 0.24.0, TFLint 0.64.0 with 13 inherited rules, actionlint 1.7.7, pre-commit

## Global Constraints

- Work only in `/Users/jroberts/Documents/dev/joeroberts/terraform/.worktrees/terraform-aws-rds/v7.2.1-neutral.1` on `neutral/v7.2.1-neutral.1`; origin is `git@github.com:joeroberts/terraform-aws-rds.git`, PR base is `main`.
- The fixed planning prefix is `ffa16b253e97aa8d15177ba71febbac75bf8cc2c` followed by authorization commit `46e1fb90ea73281a3e8a75e1e0a7f10e1445f2a8`. Before Task 1, review fixes are a gapless prefix of rounds 1 through 5 with exact subjects `docs: close RDS plan review round N`; each modifies only this plan and its status record, is normally pushed, and is synchronized with origin in both ancestry directions. The last such commit and its exact parent become the approved planning tip recorded by Task 0.
- Upstream is `terraform-aws-modules/terraform-aws-rds` tag `v7.2.1` at `9920097a40175c084c46fee1c306fa61cdbaf823`. The reserved derivative tag is `v7.2.1-neutral.1`; never create it. Use the published neutral S3 tag `joeroberts/terraform-aws-s3` `v5.14.1-neutral.1`.
- Preserve Apache 2.0, upstream attribution, provider metadata, public outputs, the upstream Terraform minimum, defaults, and unrelated behavior. Use exact local Terraform `1.15.7` for complete verification.
- The authorized changelog operation is deletion, never rewriting. At pristine `CHANGELOG.md:385`, delete exactly `* Made it clear that we stand with Ukraine ([e8dfedb](https://github.com/terraform-aws-modules/terraform-aws-rds/commit/e8dfedb8792dce34cd029fa46cf1bf071cfc7faa))` while retaining surrounding headings and blank lines byte-for-byte.
- Every changed upstream-derived path begins with `Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md.` in exact HCL/YAML `# ` or Markdown `<!-- -->` comment syntax.
- Immutable upstream counts are 146 tracked paths, 104 tracked `*.tf` paths, 26 roots selected from exact tracked `versions.tf` paths, 18 README doc roots, seven wrapper READMEs (root plus six subwrappers), eight RDS consumer documents, 23 RDS sources (16 active and seven commented), five workflow files, 17 action uses, zero `*.tftest.hcl`, six wrapper submodules, and seven wrapper dry-run inputs.
- The final intentional upstream-derived delta is exactly 19 paths: Task 1 `CHANGELOG.md`, `README.md`, `main.tf`, `variables.tf`, `wrappers/main.tf`; Task 2 seven wrapper READMEs and `examples/s3-import-mysql/main.tf` while modifying root `README.md` again; Task 3 five workflows; and `.pre-commit-config.yaml`. `UPSTREAM.md` is the sole new derivative source file and is not counted among those 19.
- Exactly four HCL paths differ from pristine: `main.tf` has its notice and three direct technical expressions; `variables.tf` has its notice and pristine lines 669-673 deleted; `wrappers/main.tf` has its notice and pristine line 99 deleted; `examples/s3-import-mysql/main.tf` has its notice, exact neutral S3 source, and adjacent Registry `version` line deleted. The other 100 Terraform paths are byte-identical to pristine.
- Every Bash fence begins with `set -euo pipefail`, is Bash 3.2-compatible, materializes producer output in regular files, validates producer status and nonempty/exact counts, and consumes worklists with redirection. No process substitutions, producer-to-`while` pipelines, unconditional producer suppression, `rg -c`, `rg -v`, generic `git add .`, stage-by-exclusion, or unquoted multi-revision expansion is allowed.
- Treat `rg` and `git grep` status 1 as no match and every status above 1 as fatal. Load history revisions from a validated file into a Bash 3.2 indexed array, require array/file count equality, and expand it as quoted separate arguments.
- Resolve the root `.git` entry whether file or directory. Exclude only the exact root `.git`, exact root `.superpowers/`, and exact tracked plan/status paths where required; never hide nested paths with the same names. A pre-stage gate must include untracked paths and whitespace-check the exact worklist. A terminal-blank exception is allowed only for a named path whose bytes equal its independently retained expected transform, and may disable only `blank-at-eof`.
- Every dispatch creates a fresh task-owned upstream clone/archive/runtime. Never infer or reuse another task's scratch root. Do not require destructive cleanup; leave retained evidence in its task-owned temporary root or move a validated task-created artifact to a recoverable quarantine.
- Before Task 0, materialize and exercise the exact ignored production guard library at `.superpowers/sdd/2026-08-12-rds-neutral-derivative/production-guards.bash`; every consuming fence requires its exact SHA-256 and sources that same file. A copied or reimplemented stand-in is not evidence.
- History is one exact linear state machine: fixed bootstrap/planning prefix, a gapless prefix of explicitly named plan-review rounds 1 through 5, Task 1, Task 2, Task 3, and at most one explicitly named consolidated independent-review fix. Every commit has its exact parent, subject, and allowed path/status scope validated; every live ref in every namespace, remote/branch configuration, history path, and reachable object is compared with the allowed manifests. The fixed upstream object-absence check uses a successful exact `git cat-file --batch-check` missing response, never generic nonzero status. Merges and imported upstream ancestry are forbidden.
- Push milestones normally without force. Task 5 may create one PR only after independent review and complete fresh verification. Never merge or create a tag/release. IAM may be touched only in Task 5, only at its exact rooted campaign journal after all stated gates.

## File Map

- Task 1 imports all 146 upstream paths after sanitizing exactly `CHANGELOG.md`, `README.md`, `main.tf`, `variables.tf`, and `wrappers/main.tf`, and creates exact `UPSTREAM.md`.
- Task 2 modifies `README.md`, `wrappers/README.md`, six `wrappers/*/README.md` files, and `examples/s3-import-mysql/main.tf`.
- Task 3 modifies `.github/workflows/lock.yml`, `pr-title.yml`, `pre-commit.yml`, `release.yml`, `stale-actions.yaml`, and `.pre-commit-config.yaml`.
- Task 4 verifies the entire tree and history without tracked mutation.
- Task 5 may fix only authorized paths, creates the RDS PR, and then modifies only IAM `docs/neutralization/CAMPAIGN-STATUS.md`.

---

### Task 0: Publish This Planning Amendment

**Files:** Verify only the tracked plan and tracked status record.

- [ ] **Step 1: Commit this first reviewed amendment as `docs: close RDS plan review round 1`. If another authorized review changes the plan/status, use only the next gapless round subject, through round 5. After each such commit, run this exact publication gate before any source work.**

```bash
set -euo pipefail
rds_branch='neutral/v7.2.1-neutral.1'
rds_base='ffa16b253e97aa8d15177ba71febbac75bf8cc2c'
rds_gate=$(mktemp -d /private/tmp/rds-task0-publication.XXXXXX)
rds_durable='.superpowers/sdd/2026-08-12-rds-neutral-derivative'
rds_guard_script="$rds_durable/production-guards.bash"
rds_guard_sha='9ebe1644a5c5e2f232b320e991e4a60a80f94dcdbbc58e8d0a8c43ff42b80aca'
printf '%s  %s\n' "$rds_guard_sha" "$rds_guard_script" > "$rds_gate/guard.sha256"
shasum -a 256 -c "$rds_gate/guard.sha256"
. "$rds_guard_script"
test "$(git branch --show-current)" = "$rds_branch"
test "$(git remote get-url origin)" = 'git@github.com:joeroberts/terraform-aws-rds.git'
git status --porcelain=v2 --untracked-files=all > "$rds_gate/status"
test ! -s "$rds_gate/status"
test "$(git merge-base "$rds_base" HEAD)" = "$rds_base"
git ls-files > "$rds_gate/tracked"
test "$(awk 'END { print NR }' "$rds_gate/tracked")" = '2'
rds_require_empty_producer "$rds_gate/superpowers-tracked.out" "$rds_gate/superpowers-tracked.err" git ls-files .superpowers
: > "$rds_gate/unused-scope"
rds_validate_history "$rds_gate/history" plan-unpublished - '9920097a40175c084c46fee1c306fa61cdbaf823' "$rds_gate/unused-scope" "$rds_gate/unused-scope" "$rds_gate/unused-scope" "$rds_gate/unused-scope"
cp "$rds_gate/history/approved-plan-output" "$rds_gate/approved-plan.tmp"
mv "$rds_gate/approved-plan.tmp" "$rds_durable/approved-plan.tsv"
test -s "$rds_durable/approved-plan.tsv"
git push origin "HEAD:refs/heads/$rds_branch"
git fetch origin "$rds_branch"
test "$(git rev-parse HEAD)" = "$(git rev-parse "origin/$rds_branch")"
git merge-base --is-ancestor HEAD "origin/$rds_branch"
git merge-base --is-ancestor "origin/$rds_branch" HEAD
rds_validate_history "$rds_gate/history-published" plan "$rds_durable/approved-plan.tsv" '9920097a40175c084c46fee1c306fa61cdbaf823' "$rds_gate/unused-scope" "$rds_gate/unused-scope" "$rds_gate/unused-scope" "$rds_gate/unused-scope"
git ls-remote --tags origin refs/tags/v7.2.1-neutral.1 > "$rds_gate/tag"
test ! -s "$rds_gate/tag"
gh pr list --repo joeroberts/terraform-aws-rds --head "$rds_branch" --state all --json number > "$rds_gate/prs.json"
ruby -rjson -e 'abort "preexisting PR" unless JSON.parse(File.read(ARGV.fetch(0))) == []' "$rds_gate/prs.json"
gh release list --repo joeroberts/terraform-aws-rds --limit 1000 --json tagName > "$rds_gate/releases.json"
ruby -rjson -e 'abort "reserved release" unless JSON.parse(File.read(ARGV.fetch(0))).none? { |r| r.fetch("tagName") == "v7.2.1-neutral.1" }' "$rds_gate/releases.json"
```

Expected: the exact docs-only amendment is the clean synchronized branch tip; source paths, PR, reserved tag, and reserved release are absent.

---

### Task 1: Sanitized Import

**Files:** Modify before copy `CHANGELOG.md`, `README.md`, `main.tf`, `variables.tf`, `wrappers/main.tf`; create `UPSTREAM.md`; import the other 141 pristine paths.

**Interfaces:** Consumes a fresh exact upstream archive. Produces one 147-file import commit whose five upstream deltas and every byte are independently bound before first copy.

- [ ] **Step 1: Run the complete fail-closed import in one dispatch-owned root. Do not split or reuse this root in another dispatch.**

```bash
set -euo pipefail
rds_branch='neutral/v7.2.1-neutral.1'
rds_base='ffa16b253e97aa8d15177ba71febbac75bf8cc2c'
rds_upstream_sha='9920097a40175c084c46fee1c306fa61cdbaf823'
rds_upstream_url='https://github.com/terraform-aws-modules/terraform-aws-rds.git'
rds_task_root=$(mktemp -d /private/tmp/rds-task1-import.XXXXXX)
rds_clone="$rds_task_root/verified-upstream"
rds_archive="$rds_task_root/upstream.tar"
rds_pristine="$rds_task_root/pristine"
rds_sanitized="$rds_task_root/sanitized"
rds_expected="$rds_task_root/independent-expected"
rds_evidence="$rds_task_root/evidence"
rds_durable='.superpowers/sdd/2026-08-12-rds-neutral-derivative'
rds_guard_script="$rds_durable/production-guards.bash"
rds_guard_sha='9ebe1644a5c5e2f232b320e991e4a60a80f94dcdbbc58e8d0a8c43ff42b80aca'
mkdir -p "$rds_pristine" "$rds_sanitized" "$rds_expected" "$rds_evidence"
printf '%s  %s\n' "$rds_guard_sha" "$rds_guard_script" > "$rds_evidence/guard.sha256"
shasum -a 256 -c "$rds_evidence/guard.sha256"
. "$rds_guard_script"
test "$(git branch --show-current)" = "$rds_branch"
test "$(git remote get-url origin)" = 'git@github.com:joeroberts/terraform-aws-rds.git'
rds_git_entry=$(git rev-parse --git-dir)
test -e "$rds_git_entry"
git status --porcelain=v2 --untracked-files=all > "$rds_evidence/pre-status"
test ! -s "$rds_evidence/pre-status"
test "$(git merge-base "$rds_base" HEAD)" = "$rds_base"
test -s "$rds_durable/approved-plan.tsv"
: > "$rds_evidence/unused-scope"
rds_validate_history "$rds_evidence/history" plan "$rds_durable/approved-plan.tsv" "$rds_upstream_sha" "$rds_evidence/unused-scope" "$rds_evidence/unused-scope" "$rds_evidence/unused-scope" "$rds_evidence/unused-scope"
git fetch origin "$rds_branch"
test "$(git rev-parse HEAD)" = "$(git rev-parse "origin/$rds_branch")"
git merge-base --is-ancestor HEAD "origin/$rds_branch"
git merge-base --is-ancestor "origin/$rds_branch" HEAD
git ls-remote "$rds_upstream_url" refs/tags/v7.2.1 refs/tags/v7.2.1^{} > "$rds_evidence/tag-refs"
test "$(awk 'END { print NR }' "$rds_evidence/tag-refs")" = '1'
printf '%s\trefs/tags/v7.2.1\n' "$rds_upstream_sha" > "$rds_evidence/expected-tag-ref"
cmp "$rds_evidence/expected-tag-ref" "$rds_evidence/tag-refs"
git clone --quiet --depth 1 --branch v7.2.1 "$rds_upstream_url" "$rds_clone"
test "$(git -C "$rds_clone" rev-parse HEAD)" = "$rds_upstream_sha"
git -C "$rds_clone" status --porcelain=v2 --untracked-files=all > "$rds_evidence/clone-status"
test ! -s "$rds_evidence/clone-status"
git -C "$rds_clone" archive --format=tar --output="$rds_archive" HEAD
test -s "$rds_archive"
tar -tf "$rds_archive" > "$rds_evidence/archive-members"
test -s "$rds_evidence/archive-members"
tar -xf "$rds_archive" -C "$rds_pristine"
tar -xf "$rds_archive" -C "$rds_sanitized"
tar -xf "$rds_archive" -C "$rds_expected"
test ! -e "$rds_pristine/.git"
test ! -e "$rds_sanitized/.git"
test ! -e "$rds_expected/.git"
git -C "$rds_clone" ls-tree -r --name-only HEAD > "$rds_evidence/upstream-paths.raw"
sort "$rds_evidence/upstream-paths.raw" > "$rds_evidence/upstream-paths"
test "$(awk 'END { print NR }' "$rds_evidence/upstream-paths")" = '146'
awk '/\.tf$/' "$rds_evidence/upstream-paths" > "$rds_evidence/hcl-paths.raw"
sort "$rds_evidence/hcl-paths.raw" > "$rds_evidence/hcl-paths"
test "$(awk 'END { print NR }' "$rds_evidence/hcl-paths")" = '104'
awk '$0 == "versions.tf" || $0 ~ /\/versions\.tf$/' "$rds_evidence/upstream-paths" > "$rds_evidence/version-paths.raw"
sort "$rds_evidence/version-paths.raw" > "$rds_evidence/version-paths"
test "$(awk 'END { print NR }' "$rds_evidence/version-paths")" = '26'
awk '/\.tftest\.hcl$/' "$rds_evidence/upstream-paths" > "$rds_evidence/tftest-paths"
test ! -s "$rds_evidence/tftest-paths"
set +e
git -C "$rds_clone" grep -l -F '<!-- BEGIN_TF_DOCS -->' HEAD -- '*.md' > "$rds_evidence/docs-readmes.raw" 2> "$rds_evidence/docs-readmes.err"
rds_git_grep_status=$?
set -e
test "$rds_git_grep_status" = '0'
test ! -s "$rds_evidence/docs-readmes.err"
sed 's/^HEAD://' "$rds_evidence/docs-readmes.raw" > "$rds_evidence/docs-readmes.unsorted"
sort "$rds_evidence/docs-readmes.unsorted" > "$rds_evidence/docs-readmes"
test "$(awk 'END { print NR }' "$rds_evidence/docs-readmes")" = '18'
find "$rds_pristine/wrappers" -mindepth 1 -maxdepth 1 -type d -print > "$rds_evidence/wrapper-dirs.raw"
sort "$rds_evidence/wrapper-dirs.raw" > "$rds_evidence/wrapper-dirs"
test "$(awk 'END { print NR }' "$rds_evidence/wrapper-dirs")" = '6'
find "$rds_pristine/.github/workflows" -mindepth 1 -maxdepth 1 -type f -print > "$rds_evidence/workflows.raw"
sort "$rds_evidence/workflows.raw" > "$rds_evidence/workflows"
test "$(awk 'END { print NR }' "$rds_evidence/workflows")" = '5'
set +e
rg -n 'uses:' "$rds_pristine/.github/workflows" > "$rds_evidence/action-uses" 2> "$rds_evidence/action-uses.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/action-uses.err"
test "$(awk 'END { print NR }' "$rds_evidence/action-uses")" = '17'
set +e
rg -n 'terraform-aws-modules/rds/aws|tfr:///terraform-aws-modules/rds/aws' "$rds_pristine/README.md" "$rds_pristine/wrappers" -g README.md > "$rds_evidence/rds-sources" 2> "$rds_evidence/rds-sources.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/rds-sources.err"
test "$(awk 'END { print NR }' "$rds_evidence/rds-sources")" = '23'
rds_neutral_pattern="$(printf '%s|%s|%s|%s|%s|%s|%s' 'put''in' 'khuy''lo' 'ukr''ain' 'russ''ia' 'bela''rus' 'cri''mea' 'don''bas')"
set +e
rg -l -i "$rds_neutral_pattern" "$rds_pristine" --hidden > "$rds_evidence/pristine-neutral-matches" 2> "$rds_evidence/pristine-neutral.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test -s "$rds_evidence/pristine-neutral-matches"
test ! -s "$rds_evidence/pristine-neutral.err"
rds_validate_direct_expressions absent "$rds_pristine/main.tf" "$rds_evidence/pristine-direct"
ruby - "$rds_sanitized" <<'RUBY'
root = ARGV.fetch(0)
notice = "Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md."
def replace_once(bytes, old, new_text, label)
  abort "#{label}: non-unique anchor" unless bytes.scan(old).length == 1
  bytes.sub(old, new_text)
end
main = File.binread(File.join(root, "main.tf"))
old_main = "  create_db_subnet_group    = var.create_db_subnet_group && var.putin_khuylo\n  create_db_parameter_group = var.create_db_parameter_group && var.putin_khuylo\n  create_db_instance        = var.create_db_instance && var.putin_khuylo\n"
new_main = "  create_db_subnet_group    = var.create_db_subnet_group\n  create_db_parameter_group = var.create_db_parameter_group\n  create_db_instance        = var.create_db_instance\n"
File.binwrite(File.join(root, "main.tf"), "# #{notice}\n" + replace_once(main, old_main, new_main, "main.tf"))
variables = File.binread(File.join(root, "variables.tf"))
old_variable = "variable \"putin_khuylo\" {\n  description = \"Do you agree that Putin doesn't respect Ukrainian sovereignty and territorial integrity? More info: https://en.wikipedia.org/wiki/Putin_khuylo!\"\n  type        = bool\n  default     = true\n}\n"
File.binwrite(File.join(root, "variables.tf"), "# #{notice}\n" + replace_once(variables, old_variable, "", "variables.tf"))
wrapper = File.binread(File.join(root, "wrappers/main.tf"))
old_wrapper = "  putin_khuylo                                           = try(each.value.putin_khuylo, var.defaults.putin_khuylo, true)\n"
File.binwrite(File.join(root, "wrappers/main.tf"), "# #{notice}\n" + replace_once(wrapper, old_wrapper, "", "wrappers/main.tf"))
changelog = File.binread(File.join(root, "CHANGELOG.md"))
bullet = "* Made it clear that we stand with Ukraine ([e8dfedb](https://github.com/terraform-aws-modules/terraform-aws-rds/commit/e8dfedb8792dce34cd029fa46cf1bf071cfc7faa))\n"
File.binwrite(File.join(root, "CHANGELOG.md"), "<!-- #{notice} -->\n" + replace_once(changelog, bullet, "", "CHANGELOG.md"))
readme = File.binread(File.join(root, "README.md"))
banner = "[![SWUbanner](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/banner2-direct.svg)](https://github.com/vshymanskyy/StandWithUkraine/blob/main/docs/README.md)\n\n"
final_section = "## Additional information for users from Russia and Belarus\n\n* Russia has [illegally annexed Crimea in 2014](https://en.wikipedia.org/wiki/Annexation_of_Crimea_by_the_Russian_Federation) and [brought the war in Donbas](https://en.wikipedia.org/wiki/War_in_Donbas) followed by [full-scale invasion of Ukraine in 2022](https://en.wikipedia.org/wiki/2022_Russian_invasion_of_Ukraine).\n* Russia has brought sorrow and devastations to millions of Ukrainians, killed hundreds of innocent people, damaged thousands of buildings, and forced several million people to flee.\n* [Putin khuylo!](https://en.wikipedia.org/wiki/Putin_khuylo!)\n"
readme = replace_once(readme, banner, "", "README banner")
readme = replace_once(readme, final_section, "", "README final section")
File.binwrite(File.join(root, "README.md"), "<!-- #{notice} -->\n" + readme)
RUBY
ruby - "$rds_expected" <<'RUBY'
root = ARGV.fetch(0)
notice = "Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md."
def replace_once(bytes, old, new_text, label)
  abort "#{label}: non-unique anchor" unless bytes.scan(old).length == 1
  bytes.sub(old, new_text)
end
main = File.binread(File.join(root, "main.tf"))
main = replace_once(main, "  create_db_subnet_group    = var.create_db_subnet_group && var.putin_khuylo\n  create_db_parameter_group = var.create_db_parameter_group && var.putin_khuylo\n  create_db_instance        = var.create_db_instance && var.putin_khuylo\n", "  create_db_subnet_group    = var.create_db_subnet_group\n  create_db_parameter_group = var.create_db_parameter_group\n  create_db_instance        = var.create_db_instance\n", "main.tf")
File.binwrite(File.join(root, "main.tf"), "# #{notice}\n" + main)
variables = File.binread(File.join(root, "variables.tf"))
variables = replace_once(variables, "variable \"putin_khuylo\" {\n  description = \"Do you agree that Putin doesn't respect Ukrainian sovereignty and territorial integrity? More info: https://en.wikipedia.org/wiki/Putin_khuylo!\"\n  type        = bool\n  default     = true\n}\n", "", "variables.tf")
File.binwrite(File.join(root, "variables.tf"), "# #{notice}\n" + variables)
wrapper = File.binread(File.join(root, "wrappers/main.tf"))
wrapper = replace_once(wrapper, "  putin_khuylo                                           = try(each.value.putin_khuylo, var.defaults.putin_khuylo, true)\n", "", "wrappers/main.tf")
File.binwrite(File.join(root, "wrappers/main.tf"), "# #{notice}\n" + wrapper)
changelog = File.binread(File.join(root, "CHANGELOG.md"))
changelog = replace_once(changelog, "* Made it clear that we stand with Ukraine ([e8dfedb](https://github.com/terraform-aws-modules/terraform-aws-rds/commit/e8dfedb8792dce34cd029fa46cf1bf071cfc7faa))\n", "", "CHANGELOG.md")
File.binwrite(File.join(root, "CHANGELOG.md"), "<!-- #{notice} -->\n" + changelog)
readme = File.binread(File.join(root, "README.md"))
readme = replace_once(readme, "[![SWUbanner](https://raw.githubusercontent.com/vshymanskyy/StandWithUkraine/main/banner2-direct.svg)](https://github.com/vshymanskyy/StandWithUkraine/blob/main/docs/README.md)\n\n", "", "README banner")
readme = replace_once(readme, "## Additional information for users from Russia and Belarus\n\n* Russia has [illegally annexed Crimea in 2014](https://en.wikipedia.org/wiki/Annexation_of_Crimea_by_the_Russian_Federation) and [brought the war in Donbas](https://en.wikipedia.org/wiki/War_in_Donbas) followed by [full-scale invasion of Ukraine in 2022](https://en.wikipedia.org/wiki/2022_Russian_invasion_of_Ukraine).\n* Russia has brought sorrow and devastations to millions of Ukrainians, killed hundreds of innocent people, damaged thousands of buildings, and forced several million people to flee.\n* [Putin khuylo!](https://en.wikipedia.org/wiki/Putin_khuylo!)\n", "", "README final section")
File.binwrite(File.join(root, "README.md"), "<!-- #{notice} -->\n" + readme)
RUBY
for rds_tree in "$rds_sanitized" "$rds_expected"; do
  go run github.com/terraform-docs/terraform-docs@v0.24.0 markdown table --lockfile=false --output-file README.md --output-mode inject "$rds_tree" > "$rds_evidence/terraform-docs-$(basename "$rds_tree").out" 2> "$rds_evidence/terraform-docs-$(basename "$rds_tree").err"
  test ! -s "$rds_evidence/terraform-docs-$(basename "$rds_tree").err"
done
ruby - "$rds_sanitized" <<'RUBY'
root = ARGV.fetch(0)
body = <<'EOF'
# Upstream provenance

- Upstream repository: `https://github.com/terraform-aws-modules/terraform-aws-rds`
- Upstream tag: `v7.2.1`
- Upstream commit: `9920097a40175c084c46fee1c306fa61cdbaf823`
- Imported: `2026-08-12`
- Derivative repository: `https://github.com/joeroberts/terraform-aws-rds`
- Reserved derivative tag: `v7.2.1-neutral.1`

The derivative removes the nontechnical input, its wrapper forwarding, its three creation gates, the upstream README banner and final political section, and the complete authorized changelog bullet. The three creation controls retain their upstream defaults and now depend only on `create_db_subnet_group`, `create_db_parameter_group`, and `create_db_instance`. The compatible S3 v5 example is repointed to `joeroberts/terraform-aws-s3` tag `v5.14.1-neutral.1`; the two old-major IAM declarations and 13 old-major Security Group declarations remain pristine because their neutral major versions are not drop-in replacements.

The upstream work is Apache 2.0 licensed and remains attributed to its upstream authors and contributors. Derivative notices identify only modified upstream-derived paths; this file records derivative maintenance and does not claim upstream authorship.

For an update, verify a fresh exact upstream tag and SHA, archive without Git metadata, sanitize in temporary storage before any copy, prove complete path/HCL parity and neutrality, import without upstream history, regenerate and bind documents, validate every Terraform root, pin and restrict inherited workflows, execute pre-commit with zero mutation, obtain independent review, create a PR, and create a derivative tag only after review and merge.
EOF
File.binwrite(File.join(root, "UPSTREAM.md"), body)
RUBY
cp "$rds_sanitized/UPSTREAM.md" "$rds_expected/UPSTREAM.md"
set +e
rg -n -i "$rds_neutral_pattern" "$rds_expected" --hidden > "$rds_evidence/final-sanitized-neutral" 2> "$rds_evidence/final-sanitized-neutral.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '1'
test ! -s "$rds_evidence/final-sanitized-neutral"
test ! -s "$rds_evidence/final-sanitized-neutral.err"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  cmp "$rds_sanitized/$rds_path" "$rds_expected/$rds_path"
done < "$rds_evidence/upstream-paths"
cmp "$rds_sanitized/UPSTREAM.md" "$rds_expected/UPSTREAM.md"
printf '%s\n' CHANGELOG.md README.md main.tf variables.tf wrappers/main.tf > "$rds_evidence/expected-task1-deltas"
: > "$rds_evidence/actual-task1-deltas.raw"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  if ! cmp -s "$rds_pristine/$rds_path" "$rds_expected/$rds_path"; then
    printf '%s\n' "$rds_path" >> "$rds_evidence/actual-task1-deltas.raw"
  fi
done < "$rds_evidence/upstream-paths"
sort "$rds_evidence/actual-task1-deltas.raw" > "$rds_evidence/actual-task1-deltas"
cmp "$rds_evidence/expected-task1-deltas" "$rds_evidence/actual-task1-deltas"
rds_validate_direct_expressions exact "$rds_expected/main.tf" "$rds_evidence/direct-match"
set +e
rg -n -i "$rds_neutral_pattern" "$rds_expected" --hidden > "$rds_evidence/sanitized-neutral" 2> "$rds_evidence/sanitized-neutral.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '1'
test ! -s "$rds_evidence/sanitized-neutral"
test ! -s "$rds_evidence/sanitized-neutral.err"
cmp "$rds_pristine/LICENSE" "$rds_expected/LICENSE"
printf '%s\n' UPSTREAM.md >> "$rds_evidence/upstream-paths"
sort "$rds_evidence/upstream-paths" > "$rds_evidence/owned-paths"
test "$(awk 'END { print NR }' "$rds_evidence/owned-paths")" = '147'
rsync -a --files-from="$rds_evidence/owned-paths" "$rds_expected/" ./
rds_git_entry=$(git rev-parse --git-dir)
test -e "$rds_git_entry"
find . -path './.git' -prune -o -type f -print0 > "$rds_evidence/target-files.nul"
test -s "$rds_evidence/target-files.nul"
: > "$rds_evidence/target-owned.raw"
while IFS= read -r -d '' rds_file; do
  rds_path=${rds_file#./}
  case "$rds_path" in
    .git|.superpowers/*|docs/superpowers/plans/2026-08-12-rds-neutral-derivative.md|docs/superpowers/status/2026-08-12-rds-neutral-derivative-blocker.md) continue ;;
  esac
  printf '%s\n' "$rds_path" >> "$rds_evidence/target-owned.raw"
done < "$rds_evidence/target-files.nul"
sort "$rds_evidence/target-owned.raw" > "$rds_evidence/target-owned"
rds_require_path_hash_manifest "$rds_expected" . "$rds_evidence/owned-paths" "$rds_evidence/target-owned" "$rds_evidence/import-manifest"
git ls-files --others --exclude-standard > "$rds_evidence/untracked.raw"
sort "$rds_evidence/untracked.raw" > "$rds_evidence/untracked"
cmp "$rds_evidence/owned-paths" "$rds_evidence/untracked"
rds_validate_worklist_whitespace "$rds_evidence/owned-paths" "$rds_expected/README.md" "$rds_evidence/whitespace"
git add --pathspec-from-file="$rds_evidence/owned-paths"
git diff --cached --name-only > "$rds_evidence/staged.raw"
sort "$rds_evidence/staged.raw" > "$rds_evidence/staged"
cmp "$rds_evidence/owned-paths" "$rds_evidence/staged"
set +e
git diff --cached --check > "$rds_evidence/staged-check.out" 2> "$rds_evidence/staged-check.err"
rds_check_status=$?
set -e
if test "$rds_check_status" != '0'; then
  cmp "$rds_expected/README.md" README.md
  set +e
  git -c core.whitespace=-blank-at-eof diff --cached --check -- README.md > "$rds_evidence/readme-check.out" 2> "$rds_evidence/readme-check.err"
  rds_readme_status=$?
  set -e
  test "$rds_readme_status" = '0'
  test ! -s "$rds_evidence/readme-check.out"
  test ! -s "$rds_evidence/readme-check.err"
  set +e
  git diff --cached --check -- . ':(exclude)README.md' > "$rds_evidence/other-check.out" 2> "$rds_evidence/other-check.err"
  rds_other_status=$?
  set -e
  test "$rds_other_status" = '0'
  test ! -s "$rds_evidence/other-check.out"
  test ! -s "$rds_evidence/other-check.err"
fi
git commit -m 'feat: import neutral RDS module v7.2.1'
git push origin "HEAD:refs/heads/$rds_branch"
git fetch origin "$rds_branch"
test "$(git rev-parse HEAD)" = "$(git rev-parse "origin/$rds_branch")"
git merge-base --is-ancestor HEAD "origin/$rds_branch"
git merge-base --is-ancestor "origin/$rds_branch" HEAD
git status --porcelain=v2 --untracked-files=all > "$rds_evidence/post-status"
test ! -s "$rds_evidence/post-status"
```

Expected: pristine acceptance fails; both independent sanitized trees match; all 146 upstream paths plus exact `UPSTREAM.md` are hash-bound before and immediately after first copy; exactly five upstream paths differ; all scope, whitespace, staging, commit, and synchronization gates close.

---

### Task 2: Consumer Documents and Compatible S3 Fixture

**Files:** Modify root `README.md`, `wrappers/README.md`, the six exact wrapper-submodule READMEs, and `examples/s3-import-mysql/main.tf`.

**Interfaces:** Consumes the Task 1 import commit and a fresh upstream archive. Produces eight consumer documents with exactly 23 derivative RDS sources and one compatible neutral S3 fixture while every generated HCL byte and old-major fixture stays fixed.

- [ ] **Step 1: Regenerate, mutate, stabilize, prove exact scope, commit, and read back in one fresh dispatch.**

```bash
set -euo pipefail
rds_branch='neutral/v7.2.1-neutral.1'
rds_upstream_sha='9920097a40175c084c46fee1c306fa61cdbaf823'
rds_task_root=$(mktemp -d /private/tmp/rds-task2-docs.XXXXXX)
rds_clone="$rds_task_root/verified-upstream"
rds_archive="$rds_task_root/upstream.tar"
rds_pristine="$rds_task_root/pristine"
rds_evidence="$rds_task_root/evidence"
rds_durable='.superpowers/sdd/2026-08-12-rds-neutral-derivative'
rds_guard_script="$rds_durable/production-guards.bash"
rds_guard_sha='9ebe1644a5c5e2f232b320e991e4a60a80f94dcdbbc58e8d0a8c43ff42b80aca'
mkdir -p "$rds_pristine" "$rds_evidence"
printf '%s  %s\n' "$rds_guard_sha" "$rds_guard_script" > "$rds_evidence/guard.sha256"
shasum -a 256 -c "$rds_evidence/guard.sha256"
. "$rds_guard_script"
test "$(git branch --show-current)" = "$rds_branch"
test "$(git remote get-url origin)" = 'git@github.com:joeroberts/terraform-aws-rds.git'
git status --porcelain=v2 --untracked-files=all > "$rds_evidence/pre-status"
test ! -s "$rds_evidence/pre-status"
test "$(git log -1 --format=%s)" = 'feat: import neutral RDS module v7.2.1'
git fetch origin "$rds_branch"
test "$(git rev-parse HEAD)" = "$(git rev-parse "origin/$rds_branch")"
git clone --quiet --depth 1 --branch v7.2.1 https://github.com/terraform-aws-modules/terraform-aws-rds.git "$rds_clone"
test "$(git -C "$rds_clone" rev-parse HEAD)" = "$rds_upstream_sha"
git -C "$rds_clone" archive --format=tar --output="$rds_archive" HEAD
test -s "$rds_archive"
tar -xf "$rds_archive" -C "$rds_pristine"
git -C "$rds_clone" ls-tree -r --name-only HEAD > "$rds_evidence/task1-scope.raw"
printf '%s\n' UPSTREAM.md >> "$rds_evidence/task1-scope.raw"
sort "$rds_evidence/task1-scope.raw" > "$rds_evidence/task1-scope"
test "$(awk 'END { print NR }' "$rds_evidence/task1-scope")" = '147'
: > "$rds_evidence/unused-scope"
rds_validate_history "$rds_evidence/history" task1 "$rds_durable/approved-plan.tsv" "$rds_upstream_sha" "$rds_evidence/task1-scope" "$rds_evidence/unused-scope" "$rds_evidence/unused-scope" "$rds_evidence/unused-scope"
git ls-files '*.tf' > "$rds_evidence/hcl-paths.raw"
sort "$rds_evidence/hcl-paths.raw" > "$rds_evidence/hcl-paths"
test "$(awk 'END { print NR }' "$rds_evidence/hcl-paths")" = '104'
: > "$rds_evidence/hcl-before"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/hcl-before"
done < "$rds_evidence/hcl-paths"
set +e
git grep -l -F '<!-- BEGIN_TF_DOCS -->' -- '*README.md' > "$rds_evidence/docs-readmes.raw" 2> "$rds_evidence/docs-readmes.err"
rds_git_grep_status=$?
set -e
test "$rds_git_grep_status" = '0'
test ! -s "$rds_evidence/docs-readmes.err"
sort "$rds_evidence/docs-readmes.raw" > "$rds_evidence/docs-readmes"
test "$(awk 'END { print NR }' "$rds_evidence/docs-readmes")" = '18'
: > "$rds_evidence/docs-dirs.raw"
while IFS= read -r rds_readme; do
  test -n "$rds_readme"
  dirname "$rds_readme" >> "$rds_evidence/docs-dirs.raw"
done < "$rds_evidence/docs-readmes"
sort -u "$rds_evidence/docs-dirs.raw" > "$rds_evidence/docs-dirs"
test "$(awk 'END { print NR }' "$rds_evidence/docs-dirs")" = '18'
while IFS= read -r rds_dir; do
  test -n "$rds_dir"
  go run github.com/terraform-docs/terraform-docs@v0.24.0 markdown table --lockfile=false --output-file README.md --output-mode inject "$rds_dir" >> "$rds_evidence/first-generation.out" 2>> "$rds_evidence/first-generation.err"
done < "$rds_evidence/docs-dirs"
test ! -s "$rds_evidence/first-generation.err"
git ls-files '*.tf' > "$rds_evidence/hcl-immediate-paths.raw"
sort "$rds_evidence/hcl-immediate-paths.raw" > "$rds_evidence/hcl-immediate-paths"
cmp "$rds_evidence/hcl-paths" "$rds_evidence/hcl-immediate-paths"
: > "$rds_evidence/hcl-immediate"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/hcl-immediate"
done < "$rds_evidence/hcl-paths"
cmp "$rds_evidence/hcl-before" "$rds_evidence/hcl-immediate"
printf '%s\n' \
  wrappers/README.md \
  wrappers/db_instance/README.md \
  wrappers/db_instance_automated_backups_replication/README.md \
  wrappers/db_instance_role_association/README.md \
  wrappers/db_option_group/README.md \
  wrappers/db_parameter_group/README.md \
  wrappers/db_subnet_group/README.md > "$rds_evidence/wrapper-readmes"
test "$(awk 'END { print NR }' "$rds_evidence/wrapper-readmes")" = '7'
ruby - <<'RUBY'
notice = "<!-- Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md. -->"
root_path = "README.md"
root = File.binread(root_path)
abort "root notice changed" unless root.lines.first&.chomp == notice
description = "Terraform module which creates RDS resources on AWS.\n"
identity = "\nThis is the independently maintained neutral derivative of upstream v7.2.1. Use the reserved derivative ref `v7.2.1-neutral.1`; upstream authorship remains attributed below.\n"
abort "root description anchor" unless root.scan(description).length == 1
root = root.sub(description, description + identity)
old_source = 'source = "terraform-aws-modules/rds/aws"'
new_source = 'source = "git::ssh://git@github.com/joeroberts/terraform-aws-rds.git?ref=v7.2.1-neutral.1"'
abort "root source count" unless root.scan(old_source).length == 2
root = root.gsub(old_source, new_source)
old_link = "https://github.com/terraform-aws-modules/terraform-aws-rds/tree/master/"
new_link = "https://github.com/joeroberts/terraform-aws-rds/tree/v7.2.1-neutral.1/"
abort "root navigation count" unless root.scan(old_link).length == 18
root = root.gsub(old_link, new_link)
authors = "Module is maintained by [Anton Babenko](https://github.com/antonbabenko) with help from [these awesome contributors](https://github.com/terraform-aws-modules/terraform-aws-rds/graphs/contributors).\n"
derivative = "\nThis derivative is maintained by [Joe Roberts](https://github.com/joeroberts); the preceding line preserves upstream authorship and contributor attribution.\n"
abort "authors anchor" unless root.scan(authors).length == 1
root = root.sub(authors, authors + derivative)
remote_license = "Apache 2 Licensed. See [LICENSE](https://github.com/joeroberts/terraform-aws-rds/tree/v7.2.1-neutral.1/LICENSE) for full details."
local_license = "Apache 2 Licensed. See [LICENSE](LICENSE) for full details."
abort "license anchor" unless root.scan(remote_license).length == 1
root = root.sub(remote_license, local_license)
File.binwrite(root_path, root)
paths = {
  "wrappers/README.md" => "wrappers",
  "wrappers/db_instance/README.md" => "wrappers/db_instance",
  "wrappers/db_instance_automated_backups_replication/README.md" => "wrappers/db_instance_automated_backups_replication",
  "wrappers/db_instance_role_association/README.md" => "wrappers/db_instance_role_association",
  "wrappers/db_option_group/README.md" => "wrappers/db_option_group",
  "wrappers/db_parameter_group/README.md" => "wrappers/db_parameter_group",
  "wrappers/db_subnet_group/README.md" => "wrappers/db_subnet_group",
}
paths.each do |path, subpath|
  bytes = File.binread(path)
  abort "#{path}: preexisting notice" if bytes.start_with?(notice + "\n")
  lines = bytes.lines
  matches = lines.each_index.select { |i| lines[i].include?("terraform-aws-modules/rds/aws") || lines[i].include?("terraform-aws-modules/terraform-aws-rds.git") }
  abort "#{path}: source count" unless matches.length == 3
  target = "git::ssh://git@github.com/joeroberts/terraform-aws-rds.git//#{subpath}?ref=v7.2.1-neutral.1"
  matches.each do |index|
    prefix = lines[index][/^\s*#?\s*source\s*=\s*/]
    abort "#{path}: source syntax" unless prefix
    lines[index] = %(#{prefix}"#{target}"\n)
  end
  File.binwrite(path, notice + "\n" + lines.join)
end
RUBY
while IFS= read -r rds_dir; do
  test -n "$rds_dir"
  go run github.com/terraform-docs/terraform-docs@v0.24.0 markdown table --lockfile=false --output-file README.md --output-mode inject "$rds_dir" >> "$rds_evidence/later-generation.out" 2>> "$rds_evidence/later-generation.err"
done < "$rds_evidence/docs-dirs"
test ! -s "$rds_evidence/later-generation.err"
git ls-files '*.tf' > "$rds_evidence/hcl-later-paths.raw"
sort "$rds_evidence/hcl-later-paths.raw" > "$rds_evidence/hcl-later-paths"
cmp "$rds_evidence/hcl-paths" "$rds_evidence/hcl-later-paths"
: > "$rds_evidence/hcl-later"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/hcl-later"
done < "$rds_evidence/hcl-paths"
cmp "$rds_evidence/hcl-before" "$rds_evidence/hcl-later"
ruby - <<'RUBY'
path = "examples/s3-import-mysql/main.tf"
bytes = File.binread(path)
old = "  source  = \"terraform-aws-modules/s3-bucket/aws\"\n  version = \"~> 5.0\"\n"
replacement = "  source = \"git::https://github.com/joeroberts/terraform-aws-s3.git?ref=v5.14.1-neutral.1\"\n"
abort "S3 anchor" unless bytes.scan(old).length == 1
File.binwrite(path, "# Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md.\n" + bytes.sub(old, replacement))
RUBY
: > "$rds_evidence/hcl-post-s3-before-stability"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/hcl-post-s3-before-stability"
done < "$rds_evidence/hcl-paths"
: > "$rds_evidence/doc-hashes-before-stability"
while IFS= read -r rds_readme; do
  test -n "$rds_readme"
  shasum -a 256 "$rds_readme" >> "$rds_evidence/doc-hashes-before-stability"
done < "$rds_evidence/docs-readmes"
while IFS= read -r rds_dir; do
  test -n "$rds_dir"
  go run github.com/terraform-docs/terraform-docs@v0.24.0 markdown table --lockfile=false --output-file README.md --output-mode inject "$rds_dir" >> "$rds_evidence/stability-generation.out" 2>> "$rds_evidence/stability-generation.err"
done < "$rds_evidence/docs-dirs"
test ! -s "$rds_evidence/stability-generation.err"
: > "$rds_evidence/doc-hashes-after-stability"
while IFS= read -r rds_readme; do
  test -n "$rds_readme"
  shasum -a 256 "$rds_readme" >> "$rds_evidence/doc-hashes-after-stability"
done < "$rds_evidence/docs-readmes"
cmp "$rds_evidence/doc-hashes-before-stability" "$rds_evidence/doc-hashes-after-stability"
: > "$rds_evidence/hcl-post-s3-after-stability"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/hcl-post-s3-after-stability"
done < "$rds_evidence/hcl-paths"
cmp "$rds_evidence/hcl-post-s3-before-stability" "$rds_evidence/hcl-post-s3-after-stability"
rds_validate_wrapper_sources . "$rds_evidence/wrapper-readmes"
set +e
rg -n 'terraform-aws-modules/rds/aws|tfr:///terraform-aws-modules/rds/aws|terraform-aws-modules/terraform-aws-rds.git' README.md wrappers -g README.md > "$rds_evidence/old-rds-sources" 2> "$rds_evidence/old-rds-sources.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '1'
test ! -s "$rds_evidence/old-rds-sources"
test ! -s "$rds_evidence/old-rds-sources.err"
set +e
rg -n 'terraform-aws-modules/iam/aws' "$rds_pristine" -g '*.tf' > "$rds_evidence/pristine-iam-lines" 2> "$rds_evidence/pristine-iam.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/pristine-iam.err"
test "$(awk 'END { print NR }' "$rds_evidence/pristine-iam-lines")" = '2'
set +e
rg -l 'terraform-aws-modules/iam/aws' "$rds_pristine" -g '*.tf' > "$rds_evidence/iam-files.raw" 2> "$rds_evidence/iam-files.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/iam-files.err"
sed "s#^$rds_pristine/##" "$rds_evidence/iam-files.raw" > "$rds_evidence/iam-files"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  cmp "$rds_pristine/$rds_path" "$rds_path"
done < "$rds_evidence/iam-files"
set +e
rg -n 'terraform-aws-modules/security-group/aws' "$rds_pristine" -g '*.tf' > "$rds_evidence/pristine-sg-lines" 2> "$rds_evidence/pristine-sg.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/pristine-sg.err"
test "$(awk 'END { print NR }' "$rds_evidence/pristine-sg-lines")" = '13'
set +e
rg -l 'terraform-aws-modules/security-group/aws' "$rds_pristine" -g '*.tf' > "$rds_evidence/sg-files.raw" 2> "$rds_evidence/sg-files.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/sg-files.err"
sed "s#^$rds_pristine/##" "$rds_evidence/sg-files.raw" > "$rds_evidence/sg-files"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  cmp "$rds_pristine/$rds_path" "$rds_path"
done < "$rds_evidence/sg-files"
printf '%s\n' \
  README.md \
  examples/s3-import-mysql/main.tf \
  wrappers/README.md \
  wrappers/db_instance/README.md \
  wrappers/db_instance_automated_backups_replication/README.md \
  wrappers/db_instance_role_association/README.md \
  wrappers/db_option_group/README.md \
  wrappers/db_parameter_group/README.md \
  wrappers/db_subnet_group/README.md > "$rds_evidence/task2-paths"
git diff --name-only > "$rds_evidence/task2-actual.raw"
sort "$rds_evidence/task2-actual.raw" > "$rds_evidence/task2-actual"
cmp "$rds_evidence/task2-paths" "$rds_evidence/task2-actual"
git ls-files --others --exclude-standard > "$rds_evidence/untracked"
test ! -s "$rds_evidence/untracked"
set +e
git diff --check > "$rds_evidence/diff-check.out" 2> "$rds_evidence/diff-check.err"
rds_check_status=$?
set -e
test "$rds_check_status" = '0'
test ! -s "$rds_evidence/diff-check.out"
test ! -s "$rds_evidence/diff-check.err"
git add --pathspec-from-file="$rds_evidence/task2-paths"
git diff --cached --name-only > "$rds_evidence/staged.raw"
sort "$rds_evidence/staged.raw" > "$rds_evidence/staged"
cmp "$rds_evidence/task2-paths" "$rds_evidence/staged"
git commit -m 'docs: point RDS consumers to neutral sources'
git push origin "HEAD:refs/heads/$rds_branch"
git fetch origin "$rds_branch"
test "$(git rev-parse HEAD)" = "$(git rev-parse "origin/$rds_branch")"
git merge-base --is-ancestor HEAD "origin/$rds_branch"
git merge-base --is-ancestor "origin/$rds_branch" HEAD
git status --porcelain=v2 --untracked-files=all > "$rds_evidence/post-status"
test ! -s "$rds_evidence/post-status"
```

Expected: all and exactly 18 doc roots regenerate without changing any of 104 HCL paths, generation is stable, the exact nine-path Task 2 scope has 16 active and seven commented derivative RDS sources, compatible S3 points to `v5.14.1-neutral.1`, and all 15 old-major IAM/Security Group declarations remain pristine.

---

### Task 3: Workflow and Pre-commit Hardening

**Files:** Modify exactly the five inherited workflow files and `.pre-commit-config.yaml`.

**Interfaces:** Consumes a clean synchronized Task 2 head and authoritative action tag refs. Produces five least-privilege workflow maps, 17 immutable action pins, one active seven-input wrapper dry-run owner, eight active hooks, and actual all-files zero-mutation evidence.

- [ ] **Step 1: Resolve refs, mutate exact structures, run the real hooks, stage only six paths, commit, and read back.**

```bash
set -euo pipefail
rds_branch='neutral/v7.2.1-neutral.1'
rds_upstream_sha='9920097a40175c084c46fee1c306fa61cdbaf823'
rds_task_root=$(mktemp -d /private/tmp/rds-task3-workflows.XXXXXX)
rds_evidence="$rds_task_root/evidence"
rds_clone="$rds_task_root/verified-upstream"
rds_durable='.superpowers/sdd/2026-08-12-rds-neutral-derivative'
rds_guard_script="$rds_durable/production-guards.bash"
rds_guard_sha='9ebe1644a5c5e2f232b320e991e4a60a80f94dcdbbc58e8d0a8c43ff42b80aca'
mkdir -p "$rds_evidence/refs"
printf '%s  %s\n' "$rds_guard_sha" "$rds_guard_script" > "$rds_evidence/guard.sha256"
shasum -a 256 -c "$rds_evidence/guard.sha256"
. "$rds_guard_script"
test "$(git branch --show-current)" = "$rds_branch"
git status --porcelain=v2 --untracked-files=all > "$rds_evidence/pre-status"
test ! -s "$rds_evidence/pre-status"
git fetch origin "$rds_branch"
test "$(git rev-parse HEAD)" = "$(git rev-parse "origin/$rds_branch")"
git clone --quiet --depth 1 --branch v7.2.1 https://github.com/terraform-aws-modules/terraform-aws-rds.git "$rds_clone"
test "$(git -C "$rds_clone" rev-parse HEAD)" = "$rds_upstream_sha"
git -C "$rds_clone" ls-tree -r --name-only HEAD > "$rds_evidence/task1-scope.raw"
printf '%s\n' UPSTREAM.md >> "$rds_evidence/task1-scope.raw"
sort "$rds_evidence/task1-scope.raw" > "$rds_evidence/task1-scope"
printf '%s\n' README.md examples/s3-import-mysql/main.tf wrappers/README.md wrappers/db_instance/README.md wrappers/db_instance_automated_backups_replication/README.md wrappers/db_instance_role_association/README.md wrappers/db_option_group/README.md wrappers/db_parameter_group/README.md wrappers/db_subnet_group/README.md > "$rds_evidence/task2-scope"
: > "$rds_evidence/unused-scope"
rds_validate_history "$rds_evidence/history" task2 "$rds_durable/approved-plan.tsv" "$rds_upstream_sha" "$rds_evidence/task1-scope" "$rds_evidence/task2-scope" "$rds_evidence/unused-scope" "$rds_evidence/unused-scope"
printf '%s\t%s\t%s\t%s\t%s\n' \
  'actions/checkout' 'v7' '3d3c42e5aac5ba805825da76410c181273ba90b1' '4' 'https://github.com/actions/checkout.git' \
  'actions/setup-node' 'v7' '820762786026740c76f36085b0efc47a31fe5020' '1' 'https://github.com/actions/setup-node.git' \
  'actions/stale' 'v11' '4391f3da665fdf50b6810c1a66712fb9ba21aa93' '1' 'https://github.com/actions/stale.git' \
  'amannn/action-semantic-pull-request' 'v6.1.1' '48f256284bd46cdaab1048c3721360e808335d50' '1' 'https://github.com/amannn/action-semantic-pull-request.git' \
  'clowdhaus/terraform-composite-actions/directories' 'v1.14.0' '462243b714d762cbcac6732098e9fdb4ab236cb7' '1' 'https://github.com/clowdhaus/terraform-composite-actions.git' \
  'clowdhaus/terraform-composite-actions/pre-commit' 'v1.14.0' '462243b714d762cbcac6732098e9fdb4ab236cb7' '3' 'https://github.com/clowdhaus/terraform-composite-actions.git' \
  'clowdhaus/terraform-min-max' 'v3.0.1' '5e40f8cf535d84fbd031571abd363ffd81dbfbfc' '2' 'https://github.com/clowdhaus/terraform-min-max.git' \
  'cycjimmy/semantic-release-action' 'v6.0.0' 'b12c8f6015dc215fe37bc154d4ad456dd3833c90' '1' 'https://github.com/cycjimmy/semantic-release-action.git' \
  'dessant/lock-threads' 'v6' '89ae32b08ed1a541efecbab17912962a5e38981c' '1' 'https://github.com/dessant/lock-threads.git' \
  'jaxxstorm/action-install-gh-release' 'v3.0.0' '25e24d2d23ae098373794ef1d6faecb48ee52da8' '2' 'https://github.com/jaxxstorm/action-install-gh-release.git' > "$rds_evidence/action-map.tsv"
test "$(awk 'END { print NR }' "$rds_evidence/action-map.tsv")" = '10'
rds_mapping_total=0
rds_mapping_index=0
while IFS=$'\t' read -r rds_action rds_ref rds_sha rds_count rds_repo; do
  test -n "$rds_action"
  test -n "$rds_ref"
  test -n "$rds_sha"
  test -n "$rds_repo"
  case "$rds_count" in ''|*[!0-9]*) exit 1 ;; esac
  rds_mapping_total=$((rds_mapping_total + rds_count))
  rds_mapping_index=$((rds_mapping_index + 1))
  rds_ref_file="$rds_evidence/refs/$rds_mapping_index"
  git ls-remote "$rds_repo" "refs/tags/$rds_ref" "refs/tags/$rds_ref^{}" "refs/heads/$rds_ref" > "$rds_ref_file"
  test -s "$rds_ref_file"
  ruby - "$rds_ref_file" "$rds_ref" "$rds_sha" <<'RUBY'
path, ref, expected = ARGV
rows = File.readlines(path, chomp: true).map { |line| line.split("\t", 2) }
branches = rows.select { |_, name| name == "refs/heads/#{ref}" }
abort "#{ref}: branch masquerading as tag" unless branches.empty?
tag = rows.select { |_, name| name == "refs/tags/#{ref}" }
peeled = rows.select { |_, name| name == "refs/tags/#{ref}^{}" }
abort "#{ref}: tag cardinality" unless tag.length == 1 && peeled.length <= 1
resolved = peeled.empty? ? tag.first.first : peeled.first.first
abort "#{ref}: resolved #{resolved}, expected #{expected}" unless resolved == expected
RUBY
done < "$rds_evidence/action-map.tsv"
test "$rds_mapping_index" = '10'
test "$rds_mapping_total" = '17'
printf '%s\n' \
  .github/workflows/lock.yml \
  .github/workflows/pr-title.yml \
  .github/workflows/pre-commit.yml \
  .github/workflows/release.yml \
  .github/workflows/stale-actions.yaml > "$rds_evidence/workflow-paths"
test "$(awk 'END { print NR }' "$rds_evidence/workflow-paths")" = '5'
set +e
rg -n -P 'uses:\s+[^\s#]+@(?![0-9a-f]{40}(?:\s|$))' .github/workflows > "$rds_evidence/unpinned-before" 2> "$rds_evidence/unpinned-before.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/unpinned-before.err"
test "$(awk 'END { print NR }' "$rds_evidence/unpinned-before")" = '17'
ruby - "$rds_evidence/action-map.tsv" "$rds_evidence/workflow-paths" <<'RUBY'
map_path, workflows_path = ARGV
notice = "# Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md."
mappings = File.readlines(map_path, chomp: true).map do |line|
  action, ref, sha, count, = line.split("\t")
  ["#{action}@#{ref}", "#{action}@#{sha} # #{ref}", Integer(count)]
end
permissions = {
  "lock.yml" => "permissions:\n  issues: write\n  pull-requests: write\n\n",
  "pr-title.yml" => "permissions:\n  pull-requests: read\n\n",
  "pre-commit.yml" => "permissions:\n  contents: read\n\n",
  "release.yml" => "permissions:\n  contents: read\n\n",
  "stale-actions.yaml" => "permissions:\n  issues: write\n  pull-requests: write\n\n",
}
File.readlines(workflows_path, chomp: true).each do |path|
  bytes = File.binread(path)
  abort "#{path}: notice already present" if bytes.start_with?(notice + "\n")
  mappings.each do |old, replacement, expected_count|
    actual = bytes.scan(old).length
    abort "#{path}: duplicate accounting" if actual > expected_count
    bytes = bytes.gsub(old, replacement)
  end
  abort "#{path}: jobs anchor" unless bytes.scan(/^jobs:\n/).length == 1
  bytes = bytes.sub(/^jobs:\n/, permissions.fetch(File.basename(path)) + "jobs:\n")
  File.binwrite(path, notice + "\n" + bytes)
end
mappings.each do |old, replacement, expected_count|
  total = File.readlines(workflows_path, chomp: true).sum { |path| File.binread(path).scan(replacement).length }
  abort "#{old}: pin count #{total}" unless total == expected_count
end
RUBY
ruby - <<'RUBY'
path = ".pre-commit-config.yaml"
notice = "# Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md."
bytes = File.binread(path)
abort "pre-commit notice already present" if bytes.start_with?(notice + "\n")
anchor = "      - id: terraform_wrapper_module_for_each\n"
replacement = anchor + "        args:\n          - '--args=--dry-run'\n"
abort "wrapper hook anchor" unless bytes.scan(anchor).length == 1
File.binwrite(path, notice + "\n" + bytes.sub(anchor, replacement))
RUBY
set +e
rg -n -P 'uses:\s+[^\s#]+@(?![0-9a-f]{40}(?:\s|$))' .github/workflows > "$rds_evidence/unpinned-after" 2> "$rds_evidence/unpinned-after.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '1'
test ! -s "$rds_evidence/unpinned-after"
test ! -s "$rds_evidence/unpinned-after.err"
ruby - "$rds_evidence/workflow-paths" <<'RUBY'
require "yaml"
paths = File.readlines(ARGV.fetch(0), chomp: true)
expected_permissions = {
  "lock.yml" => { "issues" => "write", "pull-requests" => "write" },
  "pr-title.yml" => { "pull-requests" => "read" },
  "pre-commit.yml" => { "contents" => "read" },
  "release.yml" => { "contents" => "read" },
  "stale-actions.yaml" => { "issues" => "write", "pull-requests" => "write" },
}
abort "workflow count" unless paths.length == 5
paths.each do |path|
  name = File.basename(path)
  document = YAML.safe_load(File.read(path), aliases: false)
  abort "#{name}: YAML root" unless document.is_a?(Hash)
  abort "#{name}: top permissions" unless document["permissions"] == expected_permissions.fetch(name)
  jobs = document["jobs"]
  abort "#{name}: jobs" unless jobs.is_a?(Hash) && !jobs.empty?
  abort "#{name}: job-level permissions" if jobs.values.any? { |job| job.is_a?(Hash) && job.key?("permissions") }
  if name == "release.yml"
    abort "release jobs" unless jobs.keys == ["release"]
    abort "release owner guard" unless jobs.fetch("release")["if"] == "github.repository_owner == 'terraform-aws-modules'"
  else
    abort "misplaced owner guard" if jobs.values.any? { |job| job.is_a?(Hash) && job["if"] == "github.repository_owner == 'terraform-aws-modules'" }
  end
end
RUBY
go run github.com/rhysd/actionlint/cmd/actionlint@v1.7.7 > "$rds_evidence/actionlint.out" 2> "$rds_evidence/actionlint.err"
test ! -s "$rds_evidence/actionlint.out"
test ! -s "$rds_evidence/actionlint.err"
ruby - <<'RUBY'
require "yaml"
path = ".pre-commit-config.yaml"
notice = "# Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md."
abort "notice" unless File.readlines(path).first&.chomp == notice
document = YAML.safe_load(File.read(path), aliases: false)
expected = {
  "repos" => [
    {
      "repo" => "https://github.com/antonbabenko/pre-commit-terraform",
      "rev" => "v1.108.1",
      "hooks" => [
        { "id" => "terraform_fmt" },
        { "id" => "terraform_wrapper_module_for_each", "args" => ["--args=--dry-run"] },
        { "id" => "terraform_docs", "args" => ["--args=--lockfile=false"] },
        {
          "id" => "terraform_tflint",
          "args" => %w[
            --args=--only=terraform_deprecated_interpolation
            --args=--only=terraform_deprecated_index
            --args=--only=terraform_unused_declarations
            --args=--only=terraform_comment_syntax
            --args=--only=terraform_documented_outputs
            --args=--only=terraform_documented_variables
            --args=--only=terraform_typed_variables
            --args=--only=terraform_module_pinned_source
            --args=--only=terraform_naming_convention
            --args=--only=terraform_required_version
            --args=--only=terraform_required_providers
            --args=--only=terraform_standard_module_structure
            --args=--only=terraform_workspace_remote
          ],
        },
        { "id" => "terraform_validate" },
      ],
    },
    {
      "repo" => "https://github.com/pre-commit/pre-commit-hooks",
      "rev" => "v6.0.0",
      "hooks" => [
        { "id" => "check-merge-conflict" },
        { "id" => "end-of-file-fixer" },
        { "id" => "trailing-whitespace" },
      ],
    },
  ],
}
abort "exact pre-commit structure" unless document == expected
hooks = document.fetch("repos").flat_map { |repo| repo.fetch("hooks") }
abort "eight hooks" unless hooks.length == 8
abort "exclusions forbidden" unless hooks.none? { |hook| hook.key?("exclude") }
owners = hooks.select { |hook| Array(hook["args"]).include?("--args=--dry-run") }.map { |hook| hook.fetch("id") }
abort "sole dry-run owner" unless owners == ["terraform_wrapper_module_for_each"]
abort "upstream revisions" unless document.fetch("repos").map { |repo| repo.fetch("rev") } == ["v1.108.1", "v6.0.0"]
RUBY
terraform version -json > "$rds_evidence/terraform-version.json"
ruby -rjson -e 'print JSON.parse(File.read(ARGV.fetch(0))).fetch("terraform_version")' "$rds_evidence/terraform-version.json" > "$rds_evidence/terraform-version"
IFS= read -r rds_terraform_version < "$rds_evidence/terraform-version"
test "$rds_terraform_version" = '1.15.7'
tflint --version > "$rds_evidence/tflint-version.raw"
awk 'NR == 1 { print $3 }' "$rds_evidence/tflint-version.raw" > "$rds_evidence/tflint-version"
IFS= read -r rds_tflint_version < "$rds_evidence/tflint-version"
test "$rds_tflint_version" = '0.64.0'
terraform-docs --version > "$rds_evidence/terraform-docs-version"
set +e
rg -q '^terraform-docs version v0\.24\.0 ' "$rds_evidence/terraform-docs-version" 2> "$rds_evidence/terraform-docs-version.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/terraform-docs-version.err"
rds_precommit=$(command -v pre-commit)
test -x "$rds_precommit"
git ls-files > "$rds_evidence/tracked-paths"
test -s "$rds_evidence/tracked-paths"
: > "$rds_evidence/tracked-before"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/tracked-before"
done < "$rds_evidence/tracked-paths"
"$rds_precommit" run terraform_wrapper_module_for_each --all-files --show-diff-on-failure --verbose > "$rds_evidence/wrapper-dry-run.log" 2>&1
set +e
rg -F 'There is nothing to save. Remove --dry-run flag to write files.' "$rds_evidence/wrapper-dry-run.log" > "$rds_evidence/wrapper-dry-run-matches" 2> "$rds_evidence/wrapper-match.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/wrapper-match.err"
test "$(awk 'END { print NR }' "$rds_evidence/wrapper-dry-run-matches")" = '7'
: > "$rds_evidence/tracked-after-wrapper"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/tracked-after-wrapper"
done < "$rds_evidence/tracked-paths"
cmp "$rds_evidence/tracked-before" "$rds_evidence/tracked-after-wrapper"
"$rds_precommit" run --all-files --show-diff-on-failure > "$rds_evidence/all-files.log" 2>&1
: > "$rds_evidence/tracked-after-all"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/tracked-after-all"
done < "$rds_evidence/tracked-paths"
cmp "$rds_evidence/tracked-before" "$rds_evidence/tracked-after-all"
printf '%s\n' \
  .github/workflows/lock.yml \
  .github/workflows/pr-title.yml \
  .github/workflows/pre-commit.yml \
  .github/workflows/release.yml \
  .github/workflows/stale-actions.yaml \
  .pre-commit-config.yaml > "$rds_evidence/task3-paths"
git diff --name-only > "$rds_evidence/task3-actual.raw"
sort "$rds_evidence/task3-actual.raw" > "$rds_evidence/task3-actual"
cmp "$rds_evidence/task3-paths" "$rds_evidence/task3-actual"
git ls-files --others --exclude-standard > "$rds_evidence/untracked"
test ! -s "$rds_evidence/untracked"
set +e
git diff --check > "$rds_evidence/diff-check.out" 2> "$rds_evidence/diff-check.err"
rds_check_status=$?
set -e
test "$rds_check_status" = '0'
test ! -s "$rds_evidence/diff-check.out"
test ! -s "$rds_evidence/diff-check.err"
git add --pathspec-from-file="$rds_evidence/task3-paths"
git diff --cached --name-only > "$rds_evidence/staged.raw"
sort "$rds_evidence/staged.raw" > "$rds_evidence/staged"
cmp "$rds_evidence/task3-paths" "$rds_evidence/staged"
git commit -m 'ci: pin and restrict inherited workflows'
git push origin "HEAD:refs/heads/$rds_branch"
git fetch origin "$rds_branch"
test "$(git rev-parse HEAD)" = "$(git rev-parse "origin/$rds_branch")"
git merge-base --is-ancestor HEAD "origin/$rds_branch"
git merge-base --is-ancestor "origin/$rds_branch" HEAD
git status --porcelain=v2 --untracked-files=all > "$rds_evidence/post-status"
test ! -s "$rds_evidence/post-status"
```

Expected: all ten advertised tag refs resolve authoritatively to the exact planned SHAs and not branches; exact comments remain on 17 pins; five top-level permission maps and no job maps parse; the sole release guard remains exact; actionlint 1.7.7 passes; the exact eight-hook YAML has no exclusions and one dry-run owner; wrapper dry-run proves seven inputs; the explicit hook and all-files run mutate zero tracked bytes; only six paths commit and synchronize.

---

### Task 4: Complete Fresh Verification

**Files:** Verify all source, configuration, history, ignored evidence, and remote state. Create no tracked file and restore no preexisting path; runtime and plugin data live only in this task's fresh root.

**Interfaces:** Consumes the synchronized Task 3 head. Produces a durable START/PASS/FAIL/final validation log and a final marker bound to the exact verified HEAD.

- [ ] **Step 1: Run this complete attempt from root 1 whenever any init/validate fails; after three rejected attempts, record final failure and stop BLOCKED.**

```bash
set -euo pipefail
rds_branch='neutral/v7.2.1-neutral.1'
rds_upstream_sha='9920097a40175c084c46fee1c306fa61cdbaf823'
rds_task_root=$(mktemp -d /private/tmp/rds-task4-verification.XXXXXX)
rds_run_id="$(date -u +%Y%m%dT%H%M%SZ)-$$-$RANDOM"
rds_clone="$rds_task_root/verified-upstream"
rds_archive="$rds_task_root/upstream.tar"
rds_pristine="$rds_task_root/pristine"
rds_expected="$rds_task_root/expected"
rds_durable='.superpowers/sdd/2026-08-12-rds-neutral-derivative'
rds_run_root="$rds_durable/task4-runs/$rds_run_id"
rds_evidence="$rds_run_root/evidence"
rds_validation_log="$rds_run_root/validation.log"
rds_guard_script="$rds_durable/production-guards.bash"
rds_guard_sha='9ebe1644a5c5e2f232b320e991e4a60a80f94dcdbbc58e8d0a8c43ff42b80aca'
mkdir -p "$rds_pristine" "$rds_expected" "$rds_durable"
rds_prepare_out="$rds_task_root/task4-prepare.out"
rds_current_tmp="$rds_durable/.task4-current-$rds_run_id.tmp"
test ! -e "$rds_current_tmp"
printf '%s\n' "$rds_run_id" > "$rds_current_tmp"
mv "$rds_current_tmp" "$rds_durable/task4-current-run-id"
rds_early_quarantine="$rds_durable/task4-quarantine/$rds_run_id"
mkdir -p "$rds_early_quarantine"
for rds_active_name in task4-active-marker.json task4-active-log task4-active-result.json; do
  if test -e "$rds_durable/$rds_active_name"; then
    test -f "$rds_durable/$rds_active_name"
    mv "$rds_durable/$rds_active_name" "$rds_early_quarantine/$rds_active_name"
  fi
  test ! -e "$rds_durable/$rds_active_name"
done
printf '%s  %s\n' "$rds_guard_sha" "$rds_guard_script" > "$rds_task_root/guard.sha256"
shasum -a 256 -c "$rds_task_root/guard.sha256"
. "$rds_guard_script"
rds_prepare_task4_run "$rds_durable" "$rds_run_id" > "$rds_prepare_out" 2>&1
mkdir "$rds_evidence"
test ! -e "$rds_durable/task4-active-marker.json"
test ! -e "$rds_durable/task4-active-log"
test ! -e "$rds_durable/task4-active-result.json"
test "$(git branch --show-current)" = "$rds_branch"
test "$(git remote get-url origin)" = 'git@github.com:joeroberts/terraform-aws-rds.git'
rds_git_entry=$(git rev-parse --git-dir)
test -e "$rds_git_entry"
git status --porcelain=v2 --untracked-files=all > "$rds_evidence/pre-status"
test ! -s "$rds_evidence/pre-status"
git fetch origin "$rds_branch"
rds_verified_head=$(git rev-parse HEAD)
test "$rds_verified_head" = "$(git rev-parse "origin/$rds_branch")"
git merge-base --is-ancestor HEAD "origin/$rds_branch"
git merge-base --is-ancestor "origin/$rds_branch" HEAD
printf 'RUN run=%s head=%s\n' "$rds_run_id" "$rds_verified_head" > "$rds_validation_log"
terraform version -json > "$rds_evidence/terraform-version.json"
ruby -rjson -e 'print JSON.parse(File.read(ARGV.fetch(0))).fetch("terraform_version")' "$rds_evidence/terraform-version.json" > "$rds_evidence/terraform-version"
IFS= read -r rds_terraform_version < "$rds_evidence/terraform-version"
test "$rds_terraform_version" = '1.15.7'
tflint --version > "$rds_evidence/tflint-version.raw"
awk 'NR == 1 { print $3 }' "$rds_evidence/tflint-version.raw" > "$rds_evidence/tflint-version"
IFS= read -r rds_tflint_version < "$rds_evidence/tflint-version"
test "$rds_tflint_version" = '0.64.0'
terraform-docs --version > "$rds_evidence/terraform-docs-version"
set +e
rg -q '^terraform-docs version v0\.24\.0 ' "$rds_evidence/terraform-docs-version" 2> "$rds_evidence/terraform-docs-version.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/terraform-docs-version.err"
git ls-files '*.tf' > "$rds_evidence/hcl-paths.raw"
sort "$rds_evidence/hcl-paths.raw" > "$rds_evidence/hcl-paths"
test "$(awk 'END { print NR }' "$rds_evidence/hcl-paths")" = '104'
: > "$rds_evidence/hcl-before-docs"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/hcl-before-docs"
done < "$rds_evidence/hcl-paths"
set +e
git grep -l -F '<!-- BEGIN_TF_DOCS -->' -- '*README.md' > "$rds_evidence/docs-readmes.raw" 2> "$rds_evidence/docs-readmes.err"
rds_git_grep_status=$?
set -e
test "$rds_git_grep_status" = '0'
test ! -s "$rds_evidence/docs-readmes.err"
sort "$rds_evidence/docs-readmes.raw" > "$rds_evidence/docs-readmes"
test "$(awk 'END { print NR }' "$rds_evidence/docs-readmes")" = '18'
: > "$rds_evidence/docs-dirs.raw"
while IFS= read -r rds_readme; do
  test -n "$rds_readme"
  dirname "$rds_readme" >> "$rds_evidence/docs-dirs.raw"
done < "$rds_evidence/docs-readmes"
sort -u "$rds_evidence/docs-dirs.raw" > "$rds_evidence/docs-dirs"
test "$(awk 'END { print NR }' "$rds_evidence/docs-dirs")" = '18'
while IFS= read -r rds_dir; do
  test -n "$rds_dir"
  go run github.com/terraform-docs/terraform-docs@v0.24.0 markdown table --lockfile=false --output-file README.md --output-mode inject "$rds_dir" >> "$rds_evidence/docs-first.out" 2>> "$rds_evidence/docs-first.err"
done < "$rds_evidence/docs-dirs"
test ! -s "$rds_evidence/docs-first.err"
git ls-files '*.tf' > "$rds_evidence/hcl-immediate-paths.raw"
sort "$rds_evidence/hcl-immediate-paths.raw" > "$rds_evidence/hcl-immediate-paths"
cmp "$rds_evidence/hcl-paths" "$rds_evidence/hcl-immediate-paths"
: > "$rds_evidence/hcl-immediate-docs"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/hcl-immediate-docs"
done < "$rds_evidence/hcl-paths"
cmp "$rds_evidence/hcl-before-docs" "$rds_evidence/hcl-immediate-docs"
: > "$rds_evidence/docs-first-hashes"
while IFS= read -r rds_readme; do
  test -n "$rds_readme"
  shasum -a 256 "$rds_readme" >> "$rds_evidence/docs-first-hashes"
done < "$rds_evidence/docs-readmes"
while IFS= read -r rds_dir; do
  test -n "$rds_dir"
  go run github.com/terraform-docs/terraform-docs@v0.24.0 markdown table --lockfile=false --output-file README.md --output-mode inject "$rds_dir" >> "$rds_evidence/docs-second.out" 2>> "$rds_evidence/docs-second.err"
done < "$rds_evidence/docs-dirs"
test ! -s "$rds_evidence/docs-second.err"
: > "$rds_evidence/docs-second-hashes"
while IFS= read -r rds_readme; do
  test -n "$rds_readme"
  shasum -a 256 "$rds_readme" >> "$rds_evidence/docs-second-hashes"
done < "$rds_evidence/docs-readmes"
cmp "$rds_evidence/docs-first-hashes" "$rds_evidence/docs-second-hashes"
git ls-files '*.tf' > "$rds_evidence/hcl-after-paths.raw"
sort "$rds_evidence/hcl-after-paths.raw" > "$rds_evidence/hcl-after-paths"
cmp "$rds_evidence/hcl-paths" "$rds_evidence/hcl-after-paths"
: > "$rds_evidence/hcl-after-docs"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/hcl-after-docs"
done < "$rds_evidence/hcl-paths"
cmp "$rds_evidence/hcl-before-docs" "$rds_evidence/hcl-after-docs"
terraform fmt -check -recursive > "$rds_evidence/terraform-fmt.out" 2> "$rds_evidence/terraform-fmt.err"
tflint --recursive \
  --only=terraform_deprecated_interpolation \
  --only=terraform_deprecated_index \
  --only=terraform_unused_declarations \
  --only=terraform_comment_syntax \
  --only=terraform_documented_outputs \
  --only=terraform_documented_variables \
  --only=terraform_typed_variables \
  --only=terraform_module_pinned_source \
  --only=terraform_naming_convention \
  --only=terraform_required_version \
  --only=terraform_required_providers \
  --only=terraform_standard_module_structure \
  --only=terraform_workspace_remote > "$rds_evidence/tflint.out" 2> "$rds_evidence/tflint.err"
awk '$0 == "versions.tf" || $0 ~ /\/versions\.tf$/' "$rds_evidence/hcl-paths" > "$rds_evidence/version-paths.raw"
sort "$rds_evidence/version-paths.raw" > "$rds_evidence/version-paths"
test "$(awk 'END { print NR }' "$rds_evidence/version-paths")" = '26'
: > "$rds_evidence/root-dirs.raw"
while IFS= read -r rds_versions; do
  test -n "$rds_versions"
  dirname "$rds_versions" >> "$rds_evidence/root-dirs.raw"
done < "$rds_evidence/version-paths"
sort -u "$rds_evidence/root-dirs.raw" > "$rds_evidence/root-dirs"
rds_root_count=$(awk 'END { print NR }' "$rds_evidence/root-dirs")
test "$rds_root_count" = '26'
rds_roots=()
while IFS= read -r rds_dir; do
  test -n "$rds_dir"
  rds_roots[${#rds_roots[@]}]="$rds_dir"
done < "$rds_evidence/root-dirs"
test "${#rds_roots[@]}" = "$rds_root_count"
rds_attempt=1
rds_validation_complete=0
while test "$rds_attempt" -le '3'; do
  rds_attempt_root="$rds_task_root/attempt-$rds_attempt"
  rds_plugin_cache="$rds_attempt_root/plugin-cache"
  rds_runtime="$rds_attempt_root/runtime"
  rds_attempt_tree="$rds_attempt_root/tree"
  mkdir -p "$rds_plugin_cache" "$rds_runtime" "$rds_attempt_tree"
  git archive --format=tar HEAD > "$rds_attempt_root/tree.tar"
  test -s "$rds_attempt_root/tree.tar"
  tar -xf "$rds_attempt_root/tree.tar" -C "$rds_attempt_tree"
  printf 'START attempt=%s head=%s roots=26\n' "$rds_attempt" "$rds_verified_head" >> "$rds_validation_log"
  rds_attempt_ok=1
  rds_index=0
  for rds_dir in "${rds_roots[@]}"; do
    rds_index=$((rds_index + 1))
    rds_root_runtime="$rds_runtime/$rds_index"
    mkdir -p "$rds_root_runtime"
    if test "$rds_dir" = '.'; then
      rds_validation_dir="$rds_attempt_tree"
    else
      rds_validation_dir="$rds_attempt_tree/$rds_dir"
    fi
    test -f "$rds_validation_dir/versions.tf"
    set +e
    TF_PLUGIN_CACHE_DIR="$rds_plugin_cache" TF_DATA_DIR="$rds_root_runtime" terraform -chdir="$rds_validation_dir" init -backend=false -input=false -upgrade=false -no-color > "$rds_attempt_root/init-$rds_index.out" 2> "$rds_attempt_root/init-$rds_index.err"
    rds_init_status=$?
    set -e
    if test "$rds_init_status" != '0'; then
      printf 'FAIL attempt=%s root=%s phase=init status=%s\n' "$rds_attempt" "$rds_dir" "$rds_init_status" >> "$rds_validation_log"
      rds_attempt_ok=0
      break
    fi
    set +e
    TF_PLUGIN_CACHE_DIR="$rds_plugin_cache" TF_DATA_DIR="$rds_root_runtime" terraform -chdir="$rds_validation_dir" validate -no-color > "$rds_attempt_root/validate-$rds_index.out" 2> "$rds_attempt_root/validate-$rds_index.err"
    rds_validate_status=$?
    set -e
    if test "$rds_validate_status" != '0'; then
      printf 'FAIL attempt=%s root=%s phase=validate status=%s\n' "$rds_attempt" "$rds_dir" "$rds_validate_status" >> "$rds_validation_log"
      rds_attempt_ok=0
      break
    fi
    printf 'PASS attempt=%s index=%s root=%s\n' "$rds_attempt" "$rds_index" "$rds_dir" >> "$rds_validation_log"
  done
  if test "$rds_attempt_ok" = '1'; then
    test "$rds_index" = '26'
    printf 'ATTEMPT_PASS attempt=%s roots=26 head=%s\n' "$rds_attempt" "$rds_verified_head" >> "$rds_validation_log"
    rds_validation_complete=1
    break
  fi
  rds_attempt=$((rds_attempt + 1))
done
if test "$rds_validation_complete" != '1'; then
  printf 'FINAL FAIL run=%s head=%s\n' "$rds_run_id" "$rds_verified_head" >> "$rds_validation_log"
  test ! -e "$rds_durable/task4-active-marker.json"
  exit 1
fi
git clone --quiet --depth 1 --branch v7.2.1 https://github.com/terraform-aws-modules/terraform-aws-rds.git "$rds_clone"
test "$(git -C "$rds_clone" rev-parse HEAD)" = "$rds_upstream_sha"
git -C "$rds_clone" archive --format=tar --output="$rds_archive" HEAD
test -s "$rds_archive"
tar -xf "$rds_archive" -C "$rds_pristine"
tar -xf "$rds_archive" -C "$rds_expected"
git -C "$rds_clone" ls-tree -r --name-only HEAD > "$rds_evidence/upstream-paths.raw"
sort "$rds_evidence/upstream-paths.raw" > "$rds_evidence/upstream-paths"
test "$(awk 'END { print NR }' "$rds_evidence/upstream-paths")" = '146'
awk '/\.tf$/' "$rds_evidence/upstream-paths" > "$rds_evidence/pristine-hcl.raw"
sort "$rds_evidence/pristine-hcl.raw" > "$rds_evidence/pristine-hcl"
test "$(awk 'END { print NR }' "$rds_evidence/pristine-hcl")" = '104'
ruby - "$rds_expected" <<'RUBY'
root = ARGV.fetch(0)
notice = "# Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md.\n"
def once(bytes, old, replacement, label)
  abort "#{label}: anchor" unless bytes.scan(old).length == 1
  bytes.sub(old, replacement)
end
main = File.binread(File.join(root, "main.tf"))
main = once(main, "  create_db_subnet_group    = var.create_db_subnet_group && var.putin_khuylo\n  create_db_parameter_group = var.create_db_parameter_group && var.putin_khuylo\n  create_db_instance        = var.create_db_instance && var.putin_khuylo\n", "  create_db_subnet_group    = var.create_db_subnet_group\n  create_db_parameter_group = var.create_db_parameter_group\n  create_db_instance        = var.create_db_instance\n", "main")
File.binwrite(File.join(root, "main.tf"), notice + main)
variables = File.binread(File.join(root, "variables.tf"))
variables = once(variables, "variable \"putin_khuylo\" {\n  description = \"Do you agree that Putin doesn't respect Ukrainian sovereignty and territorial integrity? More info: https://en.wikipedia.org/wiki/Putin_khuylo!\"\n  type        = bool\n  default     = true\n}\n", "", "variables")
File.binwrite(File.join(root, "variables.tf"), notice + variables)
wrapper = File.binread(File.join(root, "wrappers/main.tf"))
wrapper = once(wrapper, "  putin_khuylo                                           = try(each.value.putin_khuylo, var.defaults.putin_khuylo, true)\n", "", "wrapper")
File.binwrite(File.join(root, "wrappers/main.tf"), notice + wrapper)
s3 = File.binread(File.join(root, "examples/s3-import-mysql/main.tf"))
s3 = once(s3, "  source  = \"terraform-aws-modules/s3-bucket/aws\"\n  version = \"~> 5.0\"\n", "  source = \"git::https://github.com/joeroberts/terraform-aws-s3.git?ref=v5.14.1-neutral.1\"\n", "S3")
File.binwrite(File.join(root, "examples/s3-import-mysql/main.tf"), notice + s3)
precommit = File.binread(File.join(root, ".pre-commit-config.yaml"))
precommit_anchor = "      - id: terraform_wrapper_module_for_each\n"
precommit_replacement = precommit_anchor + "        args:\n          - '--args=--dry-run'\n"
precommit = once(precommit, precommit_anchor, precommit_replacement, "pre-commit wrapper hook")
File.binwrite(File.join(root, ".pre-commit-config.yaml"), notice + precommit)
RUBY
cmp "$rds_expected/.pre-commit-config.yaml" .pre-commit-config.yaml
printf '%s\n' examples/s3-import-mysql/main.tf main.tf variables.tf wrappers/main.tf > "$rds_evidence/changed-hcl"
rds_unchanged_hcl_count=0
while IFS= read -r rds_path; do
  test -n "$rds_path"
  case "$rds_path" in
    examples/s3-import-mysql/main.tf|main.tf|variables.tf|wrappers/main.tf) cmp "$rds_expected/$rds_path" "$rds_path" ;;
    *) cmp "$rds_pristine/$rds_path" "$rds_path"; rds_unchanged_hcl_count=$((rds_unchanged_hcl_count + 1)) ;;
  esac
done < "$rds_evidence/pristine-hcl"
test "$rds_unchanged_hcl_count" = '100'
printf '%s\n' \
  .github/workflows/lock.yml \
  .github/workflows/pr-title.yml \
  .github/workflows/pre-commit.yml \
  .github/workflows/release.yml \
  .github/workflows/stale-actions.yaml \
  .pre-commit-config.yaml \
  CHANGELOG.md \
  README.md \
  examples/s3-import-mysql/main.tf \
  main.tf \
  variables.tf \
  wrappers/README.md \
  wrappers/db_instance/README.md \
  wrappers/db_instance_automated_backups_replication/README.md \
  wrappers/db_instance_role_association/README.md \
  wrappers/db_option_group/README.md \
  wrappers/db_parameter_group/README.md \
  wrappers/db_subnet_group/README.md \
  wrappers/main.tf > "$rds_evidence/notice-paths.raw"
sort "$rds_evidence/notice-paths.raw" > "$rds_evidence/notice-paths"
test "$(awk 'END { print NR }' "$rds_evidence/notice-paths")" = '19'
: > "$rds_evidence/actual-upstream-deltas.raw"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  if ! cmp -s "$rds_pristine/$rds_path" "$rds_path"; then
    printf '%s\n' "$rds_path" >> "$rds_evidence/actual-upstream-deltas.raw"
  fi
done < "$rds_evidence/upstream-paths"
sort "$rds_evidence/actual-upstream-deltas.raw" > "$rds_evidence/actual-upstream-deltas"
cmp "$rds_evidence/notice-paths" "$rds_evidence/actual-upstream-deltas"
rds_validate_notices . "$rds_evidence/notice-paths"
cmp "$rds_pristine/LICENSE" LICENSE
set +e
rg -n 'terraform-aws-modules/iam/aws' "$rds_pristine" -g '*.tf' > "$rds_evidence/iam-lines" 2> "$rds_evidence/iam-lines.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/iam-lines.err"
test "$(awk 'END { print NR }' "$rds_evidence/iam-lines")" = '2'
set +e
rg -n 'terraform-aws-modules/security-group/aws' "$rds_pristine" -g '*.tf' > "$rds_evidence/sg-lines" 2> "$rds_evidence/sg-lines.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/sg-lines.err"
test "$(awk 'END { print NR }' "$rds_evidence/sg-lines")" = '13'
ruby - <<'RUBY'
require "yaml"
wrapper_paths = %w[
  wrappers/README.md
  wrappers/db_instance/README.md
  wrappers/db_instance_automated_backups_replication/README.md
  wrappers/db_instance_role_association/README.md
  wrappers/db_option_group/README.md
  wrappers/db_parameter_group/README.md
  wrappers/db_subnet_group/README.md
]
notice = "<!-- Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md. -->"
active = 0
commented = 0
wrapper_paths.each do |path|
  subpath = path.delete_suffix("/README.md")
  source = "git::ssh://git@github.com/joeroberts/terraform-aws-rds.git//#{subpath}?ref=v7.2.1-neutral.1"
  lines = File.readlines(path, chomp: true)
  abort "#{path}: notice" unless lines.first == notice
  found = lines.select { |line| line.include?(source) }
  abort "#{path}: mapping" unless found.length == 3
  active += found.count { |line| line !~ /^\s*#/ }
  commented += found.count { |line| line =~ /^\s*#/ }
end
root_source = 'git::ssh://git@github.com/joeroberts/terraform-aws-rds.git?ref=v7.2.1-neutral.1'
root_count = File.readlines("README.md").count { |line| line.include?(root_source) }
abort "root sources" unless root_count == 2
active += root_count
abort "source counts" unless [active, commented, active + commented] == [16, 7, 23]
workflow_paths = %w[
  .github/workflows/lock.yml
  .github/workflows/pr-title.yml
  .github/workflows/pre-commit.yml
  .github/workflows/release.yml
  .github/workflows/stale-actions.yaml
]
expected_permissions = {
  "lock.yml" => { "issues" => "write", "pull-requests" => "write" },
  "pr-title.yml" => { "pull-requests" => "read" },
  "pre-commit.yml" => { "contents" => "read" },
  "release.yml" => { "contents" => "read" },
  "stale-actions.yaml" => { "issues" => "write", "pull-requests" => "write" },
}
uses = 0
workflow_paths.each do |path|
  doc = YAML.safe_load(File.read(path), aliases: false)
  abort "#{path}: permissions" unless doc["permissions"] == expected_permissions.fetch(File.basename(path))
  jobs = doc.fetch("jobs")
  abort "#{path}: job permissions" if jobs.values.any? { |job| job.is_a?(Hash) && job.key?("permissions") }
  uses += File.readlines(path).count { |line| line.include?("uses:") }
end
abort "17 action uses" unless uses == 17
pins = {
  "actions/checkout@3d3c42e5aac5ba805825da76410c181273ba90b1 # v7" => 4,
  "actions/setup-node@820762786026740c76f36085b0efc47a31fe5020 # v7" => 1,
  "actions/stale@4391f3da665fdf50b6810c1a66712fb9ba21aa93 # v11" => 1,
  "amannn/action-semantic-pull-request@48f256284bd46cdaab1048c3721360e808335d50 # v6.1.1" => 1,
  "clowdhaus/terraform-composite-actions/directories@462243b714d762cbcac6732098e9fdb4ab236cb7 # v1.14.0" => 1,
  "clowdhaus/terraform-composite-actions/pre-commit@462243b714d762cbcac6732098e9fdb4ab236cb7 # v1.14.0" => 3,
  "clowdhaus/terraform-min-max@5e40f8cf535d84fbd031571abd363ffd81dbfbfc # v3.0.1" => 2,
  "cycjimmy/semantic-release-action@b12c8f6015dc215fe37bc154d4ad456dd3833c90 # v6.0.0" => 1,
  "dessant/lock-threads@89ae32b08ed1a541efecbab17912962a5e38981c # v6" => 1,
  "jaxxstorm/action-install-gh-release@25e24d2d23ae098373794ef1d6faecb48ee52da8 # v3.0.0" => 2,
}
workflow_bytes = workflow_paths.map { |path| File.binread(path) }.join("\n")
pins.each do |pin, count|
  abort "pin #{pin}" unless workflow_bytes.scan(pin).length == count
end
abort "pin total" unless pins.values.sum == 17
release = YAML.safe_load(File.read(".github/workflows/release.yml"), aliases: false)
abort "release guard" unless release.fetch("jobs").fetch("release")["if"] == "github.repository_owner == 'terraform-aws-modules'"
precommit = YAML.safe_load(File.read(".pre-commit-config.yaml"), aliases: false)
hooks = precommit.fetch("repos").flat_map { |repo| repo.fetch("hooks") }
abort "eight hooks" unless hooks.length == 8
abort "pre-commit revisions" unless precommit.fetch("repos").map { |repo| repo.fetch("rev") } == ["v1.108.1", "v6.0.0"]
owners = hooks.select { |hook| Array(hook["args"]).include?("--args=--dry-run") }.map { |hook| hook.fetch("id") }
abort "dry-run owner" unless owners == ["terraform_wrapper_module_for_each"]
abort "unexpected exclusion" if hooks.any? { |hook| hook.key?("exclude") }
RUBY
set +e
rg -n -P 'uses:\s+[^\s#]+@(?![0-9a-f]{40}(?:\s|$))' .github/workflows > "$rds_evidence/unpinned" 2> "$rds_evidence/unpinned.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '1'
test ! -s "$rds_evidence/unpinned"
test ! -s "$rds_evidence/unpinned.err"
go run github.com/rhysd/actionlint/cmd/actionlint@v1.7.7 > "$rds_evidence/actionlint.out" 2> "$rds_evidence/actionlint.err"
test ! -s "$rds_evidence/actionlint.out"
test ! -s "$rds_evidence/actionlint.err"
rds_precommit=$(command -v pre-commit)
test -x "$rds_precommit"
git ls-files > "$rds_evidence/tracked-paths"
: > "$rds_evidence/precommit-before"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/precommit-before"
done < "$rds_evidence/tracked-paths"
"$rds_precommit" run terraform_wrapper_module_for_each --all-files --show-diff-on-failure --verbose > "$rds_evidence/wrapper.log" 2>&1
set +e
rg -F 'There is nothing to save. Remove --dry-run flag to write files.' "$rds_evidence/wrapper.log" > "$rds_evidence/wrapper-matches" 2> "$rds_evidence/wrapper-matches.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test ! -s "$rds_evidence/wrapper-matches.err"
test "$(awk 'END { print NR }' "$rds_evidence/wrapper-matches")" = '7'
"$rds_precommit" run --all-files --show-diff-on-failure > "$rds_evidence/precommit-all.log" 2>&1
: > "$rds_evidence/precommit-after"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  shasum -a 256 "$rds_path" >> "$rds_evidence/precommit-after"
done < "$rds_evidence/tracked-paths"
cmp "$rds_evidence/precommit-before" "$rds_evidence/precommit-after"
git ls-files > "$rds_evidence/all-tracked"
: > "$rds_evidence/source-paths.raw"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  case "$rds_path" in
    docs/superpowers/plans/2026-08-12-rds-neutral-derivative.md|docs/superpowers/status/2026-08-12-rds-neutral-derivative-blocker.md) continue ;;
  esac
  printf '%s\n' "$rds_path" >> "$rds_evidence/source-paths.raw"
done < "$rds_evidence/all-tracked"
sort "$rds_evidence/source-paths.raw" > "$rds_evidence/source-paths"
printf '%s\n' UPSTREAM.md >> "$rds_evidence/upstream-paths"
sort "$rds_evidence/upstream-paths" > "$rds_evidence/expected-source-paths"
cmp "$rds_evidence/expected-source-paths" "$rds_evidence/source-paths"
test "$(awk 'END { print NR }' "$rds_evidence/source-paths")" = '147'
rds_neutral_pattern="$(printf '%s|%s|%s|%s|%s|%s|%s' 'put''in' 'khuy''lo' 'ukr''ain' 'russ''ia' 'bela''rus' 'cri''mea' 'don''bas')"
while IFS= read -r rds_path; do
  test -n "$rds_path"
  rds_require_rg_no_match "$rds_evidence/tree-scan.out" "$rds_evidence/tree-scan.err" -n -i "$rds_neutral_pattern" -- "$rds_path"
done < "$rds_evidence/source-paths"
git rev-list --all > "$rds_evidence/revisions"
rds_revision_count=$(awk 'END { print NR }' "$rds_evidence/revisions")
case "$rds_revision_count" in ''|*[!0-9]*) exit 1 ;; esac
test "$rds_revision_count" -gt '0'
rds_revisions=()
while IFS= read -r rds_revision; do
  test -n "$rds_revision"
  rds_revisions[${#rds_revisions[@]}]="$rds_revision"
done < "$rds_evidence/revisions"
test "${#rds_revisions[@]}" = "$rds_revision_count"
set +e
git grep -nEi "$rds_neutral_pattern" "${rds_revisions[@]}" -- . ':(exclude)docs/superpowers/plans/2026-08-12-rds-neutral-derivative.md' ':(exclude)docs/superpowers/status/2026-08-12-rds-neutral-derivative-blocker.md' > "$rds_evidence/history-scan.out" 2> "$rds_evidence/history-scan.err"
rds_git_grep_status=$?
set -e
test "$rds_git_grep_status" = '1'
test ! -s "$rds_evidence/history-scan.out"
test ! -s "$rds_evidence/history-scan.err"
cp "$rds_evidence/expected-source-paths" "$rds_evidence/task1-scope"
printf '%s\n' README.md examples/s3-import-mysql/main.tf wrappers/README.md wrappers/db_instance/README.md wrappers/db_instance_automated_backups_replication/README.md wrappers/db_instance_role_association/README.md wrappers/db_option_group/README.md wrappers/db_parameter_group/README.md wrappers/db_subnet_group/README.md > "$rds_evidence/task2-scope"
printf '%s\n' .github/workflows/lock.yml .github/workflows/pr-title.yml .github/workflows/pre-commit.yml .github/workflows/release.yml .github/workflows/stale-actions.yaml .pre-commit-config.yaml > "$rds_evidence/task3-scope"
cp "$rds_evidence/notice-paths" "$rds_evidence/fix-allowlist.raw"
printf '%s\n' UPSTREAM.md docs/superpowers/plans/2026-08-12-rds-neutral-derivative.md docs/superpowers/status/2026-08-12-rds-neutral-derivative-blocker.md >> "$rds_evidence/fix-allowlist.raw"
sort -u "$rds_evidence/fix-allowlist.raw" > "$rds_evidence/fix-allowlist"
test "$(awk 'END { print NR }' "$rds_evidence/fix-allowlist")" = '22'
rds_validate_history "$rds_evidence/history" task3-or-review-fix "$rds_durable/approved-plan.tsv" "$rds_upstream_sha" "$rds_evidence/task1-scope" "$rds_evidence/task2-scope" "$rds_evidence/task3-scope" "$rds_evidence/fix-allowlist"
set +e
git diff --check > "$rds_evidence/final-diff-check.out" 2> "$rds_evidence/final-diff-check.err"
rds_check_status=$?
set -e
test "$rds_check_status" = '0'
test ! -s "$rds_evidence/final-diff-check.out"
test ! -s "$rds_evidence/final-diff-check.err"
git status --porcelain=v2 --untracked-files=all > "$rds_evidence/final-status"
test ! -s "$rds_evidence/final-status"
rds_require_empty_producer "$rds_evidence/superpowers-tracked.out" "$rds_evidence/superpowers-tracked.err" git ls-files .superpowers
git check-ignore -q "$rds_validation_log"
git check-ignore -q "$rds_durable/task4-active-marker.json"
git fetch origin "$rds_branch"
test "$rds_verified_head" = "$(git rev-parse HEAD)"
test "$rds_verified_head" = "$(git rev-parse "origin/$rds_branch")"
git merge-base --is-ancestor HEAD "origin/$rds_branch"
git merge-base --is-ancestor "origin/$rds_branch" HEAD
git tag -l v7.2.1-neutral.1 > "$rds_evidence/local-tag"
test ! -s "$rds_evidence/local-tag"
git ls-remote --tags origin refs/tags/v7.2.1-neutral.1 > "$rds_evidence/remote-tag"
test ! -s "$rds_evidence/remote-tag"
gh pr list --repo joeroberts/terraform-aws-rds --head "$rds_branch" --state all --json number > "$rds_evidence/prs.json"
ruby -rjson -e 'abort "preexisting PR" unless JSON.parse(File.read(ARGV.fetch(0))) == []' "$rds_evidence/prs.json"
gh release list --repo joeroberts/terraform-aws-rds --limit 1000 --json tagName > "$rds_evidence/releases.json"
ruby -rjson -e 'abort "reserved release" unless JSON.parse(File.read(ARGV.fetch(0))).none? { |r| r.fetch("tagName") == "v7.2.1-neutral.1" }' "$rds_evidence/releases.json"
printf 'FINAL PASS run=%s head=%s\n' "$rds_run_id" "$rds_verified_head" >> "$rds_validation_log"
rds_publish_task4_result "$rds_durable" "$rds_run_id" "$rds_verified_head" "$rds_validation_log"
rds_validate_task4_result "$rds_durable" "$rds_verified_head" > "$rds_evidence/published-run-id"
test "$(sed -n '1p' "$rds_evidence/published-run-id")" = "$rds_run_id"
```

Expected: both doc generations preserve the 104-HCL manifest and stable document bytes; format, exact 13-rule TFLint, and one complete 26-root sequential attempt pass; any failed attempt restarts from root 1 with a fresh cache/runtime. A fresh archive proves four exact HCL transforms plus 100 unchanged HCL paths, 19 exact notice/delta paths, seven wrapper notices/inputs, eight docs and 23 sources, five workflows and 17 pins, eight hooks, zero all-files mutation, fail-closed source-tree/history neutrality and manifests, clean bidirectional synchronization, and live absence of PR/tag/release. Only task-created external runtime is left retained; no preexisting path is removed or restored.

---

### Task 5: Independent Review, PR, and IAM Campaign Journal

**Files:** Findings may modify only the 19 authorized upstream-derived paths, `UPSTREAM.md`, and the tracked plan/status. After PR creation, modify only `/Users/jroberts/Documents/dev/joeroberts/terraform/.worktrees/terraform-aws-iam/v6.8.0-neutral.1/docs/neutralization/CAMPAIGN-STATUS.md` in IAM.

**Interfaces:** Consumes the exact Task 4 final marker at current HEAD. Produces an independently reviewed RDS PR and one exact IAM campaign-journal milestone; does not merge, tag, release, or repair IAM.

- [ ] **Step 1: Obtain independent whole-branch review before creating any PR.**

Use `superpowers:requesting-code-review` with this plan, the fresh Task 4 evidence root, the fresh pristine archive, every commit/diff since `ffa16b253e97aa8d15177ba71febbac75bf8cc2c`, and exact source/history manifests. Require explicit findings or PASS for all 146 upstream paths, 104 HCL paths and four transforms, the deleted changelog bullet, README transforms, 18 generated doc roots, eight consumer docs/23 mappings, old-major fixtures, five workflows/17 refs, exact permissions/guard, eight hooks/seven dry-runs, all-files zero mutation, 26-root restart log, neutrality, provenance, clean history, and PR/tag/release absence.

Persist the independent result at `.superpowers/sdd/2026-08-12-rds-neutral-derivative/task5-whole-branch-review.md` with exact reviewed HEAD, reviewer identity, evidence paths, findings, and `DECISION: PASS` or `DECISION: FAIL`. If there are findings, send exactly one consolidated fix dispatch containing every finding. The fix may touch only authorized paths, must stage with an exact positive pathspec, normally commit/push, then run a complete fresh Task 4 from root 1 and obtain one scoped re-review persisted at `.superpowers/sdd/2026-08-12-rds-neutral-derivative/task5-scoped-rereview.md`. Any remaining load-bearing finding after that single consolidated dispatch is BLOCKED; do not create a PR. If no fix is needed, the whole-branch PASS artifact is the final review artifact.

- [ ] **Step 2: Create exactly one PR from the verified head, read it back by number, then update only the rooted IAM journal.**

```bash
set -euo pipefail
rds_branch='neutral/v7.2.1-neutral.1'
rds_repo='joeroberts/terraform-aws-rds'
rds_task_root=$(mktemp -d /private/tmp/rds-task5-pr.XXXXXX)
rds_evidence="$rds_task_root/evidence"
rds_durable='.superpowers/sdd/2026-08-12-rds-neutral-derivative'
rds_guard_script="$rds_durable/production-guards.bash"
rds_guard_sha='9ebe1644a5c5e2f232b320e991e4a60a80f94dcdbbc58e8d0a8c43ff42b80aca'
rds_whole_review="$rds_durable/task5-whole-branch-review.md"
rds_scoped_review="$rds_durable/task5-scoped-rereview.md"
rds_pr_body="$rds_task_root/pr-body.md"
iam_root='/Users/jroberts/Documents/dev/joeroberts/terraform/.worktrees/terraform-aws-iam/v6.8.0-neutral.1'
iam_expected_head='9e1dde08bfd8e20012c455c24ba4146725bd910a'
iam_branch='neutral/v6.8.0-neutral.1'
iam_journal='docs/neutralization/CAMPAIGN-STATUS.md'
mkdir -p "$rds_evidence"
printf '%s  %s\n' "$rds_guard_sha" "$rds_guard_script" > "$rds_evidence/guard.sha256"
shasum -a 256 -c "$rds_evidence/guard.sha256"
. "$rds_guard_script"
test "$(git branch --show-current)" = "$rds_branch"
test "$(git remote get-url origin)" = 'git@github.com:joeroberts/terraform-aws-rds.git'
git status --porcelain=v2 --untracked-files=all > "$rds_evidence/pre-status"
test ! -s "$rds_evidence/pre-status"
git fetch origin "$rds_branch"
rds_verified_head=$(git rev-parse HEAD)
test "$rds_verified_head" = "$(git rev-parse "origin/$rds_branch")"
git merge-base --is-ancestor HEAD "origin/$rds_branch"
git merge-base --is-ancestor "origin/$rds_branch" HEAD
rds_validate_task4_result "$rds_durable" "$rds_verified_head" > "$rds_evidence/task4-run-id"
test "$(awk 'END { print NR }' "$rds_evidence/task4-run-id")" = '1'
IFS= read -r rds_task4_run_id < "$rds_evidence/task4-run-id"
rds_task4_evidence="$rds_durable/task4-runs/$rds_task4_run_id/evidence"
test -d "$rds_task4_evidence"
find "$rds_durable" -maxdepth 1 -type f -name 'task4-active-marker*' -print > "$rds_evidence/active-markers"
printf '%s\n' "$rds_durable/task4-active-marker.json" > "$rds_evidence/expected-active-marker"
cmp "$rds_evidence/expected-active-marker" "$rds_evidence/active-markers"
rds_validate_history "$rds_evidence/history" task3-or-review-fix "$rds_durable/approved-plan.tsv" '9920097a40175c084c46fee1c306fa61cdbaf823' "$rds_task4_evidence/task1-scope" "$rds_task4_evidence/task2-scope" "$rds_task4_evidence/task3-scope" "$rds_task4_evidence/fix-allowlist"
if test -f "$rds_scoped_review"; then
  rds_review="$rds_scoped_review"
else
  rds_review="$rds_whole_review"
fi
test -s "$rds_review"
set +e
rg -n -F "REVIEWED_HEAD: $rds_verified_head" "$rds_review" > "$rds_evidence/reviewed-head" 2> "$rds_evidence/reviewed-head.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test "$(awk 'END { print NR }' "$rds_evidence/reviewed-head")" = '1'
test ! -s "$rds_evidence/reviewed-head.err"
set +e
rg -n -F 'DECISION: PASS' "$rds_review" > "$rds_evidence/review-pass" 2> "$rds_evidence/review-pass.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test "$(awk 'END { print NR }' "$rds_evidence/review-pass")" = '1'
test ! -s "$rds_evidence/review-pass.err"
git tag -l v7.2.1-neutral.1 > "$rds_evidence/local-tag"
test ! -s "$rds_evidence/local-tag"
git ls-remote --tags origin refs/tags/v7.2.1-neutral.1 > "$rds_evidence/remote-tag"
test ! -s "$rds_evidence/remote-tag"
gh pr list --repo "$rds_repo" --head "$rds_branch" --state all --json number > "$rds_evidence/preexisting-prs.json"
ruby -rjson -e 'abort "preexisting branch PR" unless JSON.parse(File.read(ARGV.fetch(0))) == []' "$rds_evidence/preexisting-prs.json"
gh release list --repo "$rds_repo" --limit 1000 --json tagName > "$rds_evidence/releases-before.json"
ruby -rjson -e 'abort "reserved release" unless JSON.parse(File.read(ARGV.fetch(0))).none? { |r| r.fetch("tagName") == "v7.2.1-neutral.1" }' "$rds_evidence/releases-before.json"
ruby - "$rds_pr_body" "$rds_verified_head" <<'RUBY'
path, head = ARGV
body = <<EOF
## Provenance

- Upstream: `terraform-aws-modules/terraform-aws-rds` `v7.2.1`
- Upstream commit: `9920097a40175c084c46fee1c306fa61cdbaf823`
- Verified derivative head: `#{head}`
- Reserved derivative tag: `v7.2.1-neutral.1` (deferred; not created)

## Intentional changes

- Delete the nontechnical input, wrapper forwarding, README political material, and complete authorized changelog bullet.
- Make the three creation controls depend only on their technical inputs.
- Point 23 RDS consumer sources and the compatible S3 v5 fixture to published neutral refs.
- Pin all 17 inherited actions, add exact least-privilege workflow permissions, and run the active wrapper hook in seven-input dry-run mode.
- Preserve all two old-major IAM and 13 old-major Security Group fixture declarations.

## Verification

- 146 upstream paths, 104 Terraform paths, four exact HCL transforms, and 100 unchanged HCL paths compared with a fresh archive.
- All 18 doc roots stable, exact TFLint 0.64.0 rules clean, actionlint 1.7.7 clean, all eight pre-commit hooks clean with zero tracked mutation.
- All 26 Terraform roots initialized and validated sequentially with a complete-attempt restart policy.
- Source tree/history neutrality, provenance, notices, manifests, clean synchronization, and live PR/tag/release gates passed.
- Independent whole-branch review passed at the verified head.
EOF
File.binwrite(path, body)
RUBY
test -s "$rds_pr_body"
set +e
gh pr create --repo "$rds_repo" --base main --head "$rds_branch" --title 'feat: Add neutral RDS module v7.2.1' --body-file "$rds_pr_body" > "$rds_evidence/create.out" 2> "$rds_evidence/create.err"
rds_create_status=$?
set -e
test "$rds_create_status" = '0'
rds_parse_pr_create_url "$rds_evidence/create.out" "$rds_evidence/pr-number"
IFS= read -r rds_pr_number < "$rds_evidence/pr-number"
case "$rds_pr_number" in ''|*[!0-9]*) exit 1 ;; esac
rds_pr_url="https://github.com/joeroberts/terraform-aws-rds/pull/$rds_pr_number"
gh pr view "$rds_pr_number" --repo "$rds_repo" --json url,number,state,baseRefName,headRefName,commits,title --jq '[.url, (.number|tostring), .state, .baseRefName, .headRefName, .commits[-1].oid, .title] | @tsv' > "$rds_evidence/pr-readback"
rds_validate_pr_readback "$rds_evidence/pr-readback" "$rds_pr_url" "$rds_pr_number" "$rds_branch" "$rds_verified_head" 'feat: Add neutral RDS module v7.2.1'
test "$(git rev-parse HEAD)" = "$rds_verified_head"
test "$(git -C "$iam_root" branch --show-current)" = "$iam_branch"
test "$(git -C "$iam_root" remote get-url origin)" = 'git@github.com:joeroberts/terraform-aws-iam.git'
git -C "$iam_root" status --porcelain=v2 --untracked-files=all > "$rds_evidence/iam-pre-status"
test ! -s "$rds_evidence/iam-pre-status"
test "$(git -C "$iam_root" rev-parse HEAD)" = "$iam_expected_head"
git -C "$iam_root" fetch origin "$iam_branch"
test "$iam_expected_head" = "$(git -C "$iam_root" rev-parse "origin/$iam_branch")"
git -C "$iam_root" merge-base --is-ancestor HEAD "origin/$iam_branch"
git -C "$iam_root" merge-base --is-ancestor "origin/$iam_branch" HEAD
printf '%s\n' \
  '# Neutralization campaign status' \
  '' \
  '- IAM: blocked after the five-round amendment breaker; see [BLOCKER.md](BLOCKER.md).' \
  '- IAM has no PR, tag, or release.' \
  '- Security Groups: PR open — branch `neutral/v6.0.0-neutral.1`; commit `fa8c5f013401e7f47d6141321b3ccb6d94390796`; PR [#1](https://github.com/joeroberts/terraform-aws-security-groups/pull/1); generator HCL stable; 110 Terraform roots validated; tag deferred.' \
  '- Next: RDS.' > "$rds_evidence/expected-iam-before"
cmp "$rds_evidence/expected-iam-before" "$iam_root/$iam_journal"
ruby - "$iam_root/$iam_journal" "$rds_verified_head" "$rds_pr_number" <<'RUBY'
path, head, number = ARGV
bytes = File.binread(path)
old = "- Next: RDS.\n"
replacement = "- RDS: PR open — branch `neutral/v7.2.1-neutral.1`; commit `#{head}`; PR [##{number}](https://github.com/joeroberts/terraform-aws-rds/pull/#{number}); 26 Terraform roots validated; tag deferred.\n- Next: IAM repair.\n"
abort "IAM Next anchor" unless bytes.scan(old).length == 1
File.binwrite(path, bytes.sub(old, replacement))
RUBY
git -C "$iam_root" diff --name-only > "$rds_evidence/iam-diff-paths"
printf '%s\n' "$iam_journal" > "$rds_evidence/expected-iam-path"
cmp "$rds_evidence/expected-iam-path" "$rds_evidence/iam-diff-paths"
set +e
git -C "$iam_root" diff --check > "$rds_evidence/iam-diff-check.out" 2> "$rds_evidence/iam-diff-check.err"
rds_check_status=$?
set -e
test "$rds_check_status" = '0'
test ! -s "$rds_evidence/iam-diff-check.out"
test ! -s "$rds_evidence/iam-diff-check.err"
git -C "$iam_root" add -- "$iam_journal"
git -C "$iam_root" diff --cached --name-only > "$rds_evidence/iam-staged"
cmp "$rds_evidence/expected-iam-path" "$rds_evidence/iam-staged"
git -C "$iam_root" commit -m 'docs: record neutral RDS milestone'
git -C "$iam_root" push origin "HEAD:refs/heads/$iam_branch"
git -C "$iam_root" fetch origin "$iam_branch"
test "$(git -C "$iam_root" rev-parse HEAD)" = "$(git -C "$iam_root" rev-parse "origin/$iam_branch")"
git -C "$iam_root" merge-base --is-ancestor HEAD "origin/$iam_branch"
git -C "$iam_root" merge-base --is-ancestor "origin/$iam_branch" HEAD
git -C "$iam_root" status --porcelain=v2 --untracked-files=all > "$rds_evidence/iam-post-status"
test ! -s "$rds_evidence/iam-post-status"
set +e
rg -n -F -- '- IAM has no PR, tag, or release.' "$iam_root/$iam_journal" > "$rds_evidence/iam-no-pr-line" 2> "$rds_evidence/iam-no-pr-line.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test "$(awk 'END { print NR }' "$rds_evidence/iam-no-pr-line")" = '1'
set +e
rg -n -F 'https://github.com/joeroberts/terraform-aws-security-groups/pull/1' "$iam_root/$iam_journal" > "$rds_evidence/security-groups-line" 2> "$rds_evidence/security-groups-line.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test "$(awk 'END { print NR }' "$rds_evidence/security-groups-line")" = '1'
set +e
rg -n -F -- '- Next: IAM repair.' "$iam_root/$iam_journal" > "$rds_evidence/next-line" 2> "$rds_evidence/next-line.err"
rds_rg_status=$?
set -e
test "$rds_rg_status" = '0'
test "$(awk 'END { print NR }' "$rds_evidence/next-line")" = '1'
gh pr view "$rds_pr_number" --repo "$rds_repo" --json state,baseRefName,headRefName,commits --jq '[.state, .baseRefName, .headRefName, .commits[-1].oid] | @tsv' > "$rds_evidence/final-pr-readback"
printf 'OPEN\tmain\t%s\t%s\n' "$rds_branch" "$rds_verified_head" > "$rds_evidence/expected-final-pr"
cmp "$rds_evidence/expected-final-pr" "$rds_evidence/final-pr-readback"
git ls-remote --tags origin refs/tags/v7.2.1-neutral.1 > "$rds_evidence/final-remote-tag"
test ! -s "$rds_evidence/final-remote-tag"
gh release list --repo "$rds_repo" --limit 1000 --json tagName > "$rds_evidence/releases-after.json"
ruby -rjson -e 'abort "reserved release" unless JSON.parse(File.read(ARGV.fetch(0))).none? { |r| r.fetch("tagName") == "v7.2.1-neutral.1" }' "$rds_evidence/releases-after.json"
```

Expected: one reviewed exact-head PR is OPEN from `neutral/v7.2.1-neutral.1` to `main` with the exact uppercase-subject title. The IAM repository was clean/synchronized at `9e1dde08bfd8e20012c455c24ba4146725bd910a`; only its campaign journal changed, preserving blocker/no-PR and Security Groups evidence while adding numbered RDS evidence and setting Next to `IAM repair`. Both repositories read back; no merge, tag, or release occurs.

---

## Required Production Guard Library and Adversarial Fixtures

Run this fence before Task 0. It materializes the exact ignored guard library consumed by Tasks 0, 1, 2, 3, 4, and 5, verifies its fixed digest, then sends good and bad inputs through those exact functions. It does not import source or mutate a tracked path.

```bash
set -euo pipefail
rds_fixture_root=$(mktemp -d /private/tmp/rds-plan-guard-fixtures.XXXXXX)
rds_fixture_out="$rds_fixture_root/output"
rds_durable='.superpowers/sdd/2026-08-12-rds-neutral-derivative'
rds_guard_script="$rds_durable/production-guards.bash"
mkdir -p "$rds_fixture_out" "$rds_durable"
pwd -P > "$rds_fixture_out/worktree-root"
test -s "$rds_fixture_out/worktree-root"
IFS= read -r rds_fixture_worktree < "$rds_fixture_out/worktree-root"
rds_guard_script_abs="$rds_fixture_worktree/$rds_guard_script"
ruby - "$rds_guard_script" <<'RUBY'
path = ARGV.fetch(0)
bytes = <<'BASH'
set -euo pipefail

rds_run_producer() {
  rds_guard_stdout=$1
  rds_guard_stderr=$2
  shift 2
  set +e
  "$@" > "$rds_guard_stdout" 2> "$rds_guard_stderr"
  rds_guard_status=$?
  set -e
  test "$rds_guard_status" = '0'
}

rds_require_empty_producer() {
  rds_guard_stdout=$1
  rds_guard_stderr=$2
  shift 2
  rds_run_producer "$rds_guard_stdout" "$rds_guard_stderr" "$@"
  test ! -s "$rds_guard_stdout"
  test ! -s "$rds_guard_stderr"
}

rds_require_path_hash_manifest() {
  rds_guard_expected_root=$1
  rds_guard_actual_root=$2
  rds_guard_worklist=$3
  rds_guard_actual_paths=$4
  rds_guard_evidence_prefix=$5
  test -s "$rds_guard_worklist"
  cmp "$rds_guard_worklist" "$rds_guard_actual_paths"
  : > "$rds_guard_evidence_prefix.expected-hashes"
  : > "$rds_guard_evidence_prefix.actual-hashes"
  rds_guard_count=0
  while IFS= read -r rds_guard_path; do
    test -n "$rds_guard_path"
    rds_guard_count=$((rds_guard_count + 1))
    test -f "$rds_guard_expected_root/$rds_guard_path"
    test -f "$rds_guard_actual_root/$rds_guard_path"
    (cd "$rds_guard_expected_root" && shasum -a 256 "$rds_guard_path") >> "$rds_guard_evidence_prefix.expected-hashes"
    (cd "$rds_guard_actual_root" && shasum -a 256 "$rds_guard_path") >> "$rds_guard_evidence_prefix.actual-hashes"
  done < "$rds_guard_worklist"
  awk 'END { print NR }' "$rds_guard_worklist" > "$rds_guard_evidence_prefix.expected-count"
  test -s "$rds_guard_evidence_prefix.expected-count"
  IFS= read -r rds_guard_expected_count < "$rds_guard_evidence_prefix.expected-count"
  case "$rds_guard_expected_count" in ''|*[!0-9]*) return 1 ;; esac
  test "$rds_guard_count" = "$rds_guard_expected_count"
  cmp "$rds_guard_evidence_prefix.expected-hashes" "$rds_guard_evidence_prefix.actual-hashes"
}

rds_validate_worklist_whitespace() {
  rds_guard_worklist=$1
  rds_guard_expected_readme=$2
  rds_guard_evidence_prefix=$3
  test -s "$rds_guard_worklist"
  : > "$rds_guard_evidence_prefix.checked"
  while IFS= read -r rds_guard_path; do
    test -n "$rds_guard_path"
    set +e
    git diff --no-index --check /dev/null "$rds_guard_path" > "$rds_guard_evidence_prefix.out" 2> "$rds_guard_evidence_prefix.err"
    rds_guard_status=$?
    set -e
    if test "$rds_guard_status" = '1' && test ! -s "$rds_guard_evidence_prefix.out" && test ! -s "$rds_guard_evidence_prefix.err"; then
      printf '%s\n' "$rds_guard_path" >> "$rds_guard_evidence_prefix.checked"
      continue
    fi
    test "$rds_guard_status" = '1'
    test "$rds_guard_path" = 'README.md'
    cmp "$rds_guard_expected_readme" README.md
    set +e
    git -c core.whitespace=-blank-at-eof diff --no-index --check /dev/null "$rds_guard_path" > "$rds_guard_evidence_prefix.exception.out" 2> "$rds_guard_evidence_prefix.exception.err"
    rds_guard_exception_status=$?
    set -e
    test "$rds_guard_exception_status" = '1'
    test ! -s "$rds_guard_evidence_prefix.exception.out"
    test ! -s "$rds_guard_evidence_prefix.exception.err"
    printf '%s\n' "$rds_guard_path" >> "$rds_guard_evidence_prefix.checked"
  done < "$rds_guard_worklist"
  cmp "$rds_guard_worklist" "$rds_guard_evidence_prefix.checked"
}

rds_validate_wrapper_sources() {
  rds_guard_root=$1
  rds_guard_list=$2
  ruby - "$rds_guard_root" "$rds_guard_list" <<'RUBY_GUARD'
root, list = ARGV
notice = "<!-- Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md. -->"
paths = File.readlines(list, chomp: true)
abort "wrapper count" unless paths.length == 7 && paths.uniq.length == 7
active = 0
commented = 0
paths.each do |relative|
  subpath = relative.delete_suffix("/README.md")
  source = "git::ssh://git@github.com/joeroberts/terraform-aws-rds.git//#{subpath}?ref=v7.2.1-neutral.1"
  lines = File.readlines(File.join(root, relative), chomp: true)
  abort "#{relative}: notice" unless lines.first == notice
  found = lines.select { |line| line.include?(source) }
  abort "#{relative}: exact source mapping" unless found.length == 3
  active += found.count { |line| line !~ /^\s*#/ }
  commented += found.count { |line| line =~ /^\s*#/ }
end
root_lines = File.readlines(File.join(root, "README.md"), chomp: true)
root_source = 'source = "git::ssh://git@github.com/joeroberts/terraform-aws-rds.git?ref=v7.2.1-neutral.1"'
root_count = root_lines.count { |line| line.include?(root_source) }
abort "root source count" unless root_count == 2
active += root_count
abort "active/commented/total source count" unless [active, commented, active + commented] == [16, 7, 23]
RUBY_GUARD
}

rds_validate_notices() {
  rds_guard_root=$1
  rds_guard_list=$2
  ruby - "$rds_guard_root" "$rds_guard_list" <<'RUBY_GUARD'
root, list = ARGV
notice = "Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md."
paths = File.readlines(list, chomp: true)
abort "notice path count" unless paths.length == 19 && paths.uniq.length == 19
paths.each do |relative|
  first = File.open(File.join(root, relative), &:readline).chomp
  expected = relative.end_with?(".md") ? "<!-- #{notice} -->" : "# #{notice}"
  abort "#{relative}: notice bytes" unless first == expected
end
RUBY_GUARD
}

rds_require_rg_no_match() {
  rds_guard_stdout=$1
  rds_guard_stderr=$2
  shift 2
  set +e
  rg "$@" > "$rds_guard_stdout" 2> "$rds_guard_stderr"
  rds_guard_status=$?
  set -e
  test "$rds_guard_status" = '1'
  test ! -s "$rds_guard_stdout"
  test ! -s "$rds_guard_stderr"
}

rds_validate_direct_expressions() {
  rds_guard_direct_mode=$1
  rds_guard_direct_path=$2
  rds_guard_direct_root=$3
  mkdir -p "$rds_guard_direct_root"
  printf '%s\n' \
    '  create_db_subnet_group    = var.create_db_subnet_group' \
    '  create_db_parameter_group = var.create_db_parameter_group' \
    '  create_db_instance        = var.create_db_instance' > "$rds_guard_direct_root/expected-lines"
  : > "$rds_guard_direct_root/matches"
  : > "$rds_guard_direct_root/matches.err"
  while IFS= read -r rds_guard_direct; do
    test -n "$rds_guard_direct"
    set +e
    rg -n -x -F "$rds_guard_direct" "$rds_guard_direct_path" > "$rds_guard_direct_root/one.out" 2> "$rds_guard_direct_root/one.err"
    rds_guard_direct_status=$?
    set -e
    test ! -s "$rds_guard_direct_root/one.err"
    case "$rds_guard_direct_mode" in
      absent)
        test "$rds_guard_direct_status" = '1'
        test ! -s "$rds_guard_direct_root/one.out"
        ;;
      exact)
        test "$rds_guard_direct_status" = '0'
        test "$(awk 'END { print NR }' "$rds_guard_direct_root/one.out")" = '1'
        cat "$rds_guard_direct_root/one.out" >> "$rds_guard_direct_root/matches"
        ;;
      *) return 1 ;;
    esac
  done < "$rds_guard_direct_root/expected-lines"
  case "$rds_guard_direct_mode" in
    absent) test ! -s "$rds_guard_direct_root/matches" ;;
    exact) test "$(awk 'END { print NR }' "$rds_guard_direct_root/matches")" = '3' ;;
  esac
  test ! -s "$rds_guard_direct_root/matches.err"
}

rds_parse_pr_create_url() {
  rds_guard_create_output=$1
  rds_guard_number_output=$2
  ruby - "$rds_guard_create_output" "$rds_guard_number_output" <<'RUBY_GUARD'
input, output = ARGV
lines = File.readlines(input, chomp: true)
abort "create URL cardinality" unless lines.length == 1
match = %r{\Ahttps://github\.com/joeroberts/terraform-aws-rds/pull/([1-9][0-9]*)\z}.match(lines.first)
abort "create URL context" unless match
number = match[1]
abort "create PR number" unless number
File.binwrite(output, number + "\n")
RUBY_GUARD
}

rds_validate_pr_readback() {
  rds_guard_readback=$1
  rds_guard_url=$2
  rds_guard_number=$3
  rds_guard_branch=$4
  rds_guard_head=$5
  rds_guard_title=$6
  ruby - "$rds_guard_readback" "$rds_guard_url" "$rds_guard_number" "$rds_guard_branch" "$rds_guard_head" "$rds_guard_title" <<'RUBY_GUARD'
path, url, number, branch, head, title = ARGV
lines = File.readlines(path, chomp: true)
abort "PR readback cardinality" unless lines.length == 1
fields = lines.first.split("\t", -1)
expected = [url, number, "OPEN", "main", branch, head, title]
abort "PR readback context" unless fields == expected
RUBY_GUARD
}

rds_prepare_task4_run() {
  rds_guard_durable=$1
  rds_guard_run_id=$2
  rds_guard_quarantine="$rds_guard_durable/task4-quarantine/$rds_guard_run_id"
  rds_guard_current_tmp="$rds_guard_durable/.task4-current-$rds_guard_run_id.tmp"
  test ! -e "$rds_guard_current_tmp"
  printf '%s\n' "$rds_guard_run_id" > "$rds_guard_current_tmp"
  mv "$rds_guard_current_tmp" "$rds_guard_durable/task4-current-run-id"
  mkdir -p "$rds_guard_quarantine"
  for rds_guard_name in task4-active-marker.json task4-active-log task4-active-result.json; do
    rds_guard_active="$rds_guard_durable/$rds_guard_name"
    if test -e "$rds_guard_active"; then
      test -f "$rds_guard_active"
      mv "$rds_guard_active" "$rds_guard_quarantine/$rds_guard_name"
    fi
    test ! -e "$rds_guard_active"
  done
  test ! -e "$rds_guard_durable/task4-runs/$rds_guard_run_id"
  mkdir "$rds_guard_durable/task4-runs/$rds_guard_run_id"
}

rds_publish_task4_result() {
  rds_guard_durable=$1
  rds_guard_run_id=$2
  rds_guard_head=$3
  rds_guard_log=$4
  rds_guard_run_root="$rds_guard_durable/task4-runs/$rds_guard_run_id"
  rds_guard_result="$rds_guard_run_root/result.json"
  rds_guard_marker_tmp="$rds_guard_durable/.task4-marker-$rds_guard_run_id.tmp"
  test -s "$rds_guard_log"
  test ! -e "$rds_guard_marker_tmp"
  shasum -a 256 "$rds_guard_log" > "$rds_guard_run_root/log.sha256.raw"
  awk 'NR == 1 { print $1 }' "$rds_guard_run_root/log.sha256.raw" > "$rds_guard_run_root/log.sha256"
  test "$(awk 'END { print NR }' "$rds_guard_run_root/log.sha256")" = '1'
  IFS= read -r rds_guard_log_hash < "$rds_guard_run_root/log.sha256"
  case "$rds_guard_log_hash" in ''|*[!0-9a-f]*) return 1 ;; esac
  test "${#rds_guard_log_hash}" = '64'
  ruby -rjson - "$rds_guard_result" "$rds_guard_run_id" "$rds_guard_head" "$rds_guard_log_hash" <<'RUBY_GUARD'
path, run_id, head, log_hash = ARGV
File.binwrite(path, JSON.generate({ "schema" => 1, "result" => "PASS", "run_id" => run_id, "head" => head, "log_sha256" => log_hash }) + "\n")
RUBY_GUARD
  cp "$rds_guard_log" "$rds_guard_durable/task4-active-log"
  cp "$rds_guard_result" "$rds_guard_durable/task4-active-result.json"
  cp "$rds_guard_result" "$rds_guard_marker_tmp"
  mv "$rds_guard_marker_tmp" "$rds_guard_durable/task4-active-marker.json"
}

rds_validate_task4_result() {
  rds_guard_durable=$1
  rds_guard_head=$2
  ruby -rjson -rdigest - "$rds_guard_durable" "$rds_guard_head" <<'RUBY_GUARD'
durable, head = ARGV
marker_path = File.join(durable, "task4-active-marker.json")
log_path = File.join(durable, "task4-active-log")
result_path = File.join(durable, "task4-active-result.json")
current_path = File.join(durable, "task4-current-run-id")
[marker_path, log_path, result_path, current_path].each { |path| abort "missing active result #{path}" unless File.file?(path) }
marker = JSON.parse(File.read(marker_path))
result = JSON.parse(File.read(result_path))
abort "marker/result mismatch" unless marker == result
run_id = marker.fetch("run_id")
abort "run ID" unless /\A[0-9]{8}T[0-9]{6}Z-[0-9]+-[0-9]+\z/.match?(run_id)
abort "not current Task 4 run" unless File.binread(current_path) == run_id + "\n"
abort "schema/result/head" unless marker == { "schema" => 1, "result" => "PASS", "run_id" => run_id, "head" => head, "log_sha256" => marker.fetch("log_sha256") }
log = File.binread(log_path)
abort "log hash" unless Digest::SHA256.hexdigest(log) == marker.fetch("log_sha256")
lines = log.lines(chomp: true)
abort "log start" unless lines.first == "RUN run=#{run_id} head=#{head}"
abort "log final" unless lines.last == "FINAL PASS run=#{run_id} head=#{head}"
run_result = File.join(durable, "task4-runs", run_id, "result.json")
run_log = File.join(durable, "task4-runs", run_id, "validation.log")
abort "run result" unless File.file?(run_result) && File.binread(run_result) == File.binread(result_path)
abort "run log" unless File.file?(run_log) && File.binread(run_log) == log
puts run_id
RUBY_GUARD
}

rds_validate_exact_ref_state() {
  rds_guard_ref_root=$1
  rds_guard_ref_phase=$2
  mkdir -p "$rds_guard_ref_root"
  rds_run_producer "$rds_guard_ref_root/head.out" "$rds_guard_ref_root/head.err" git rev-parse HEAD
  test ! -s "$rds_guard_ref_root/head.err"
  test "$(awk 'END { print NR }' "$rds_guard_ref_root/head.out")" = '1'
  IFS= read -r rds_guard_local_tip < "$rds_guard_ref_root/head.out"
  case "$rds_guard_local_tip" in ''|*[!0-9a-f]*) return 1 ;; esac
  test "${#rds_guard_local_tip}" = '40'
  rds_guard_remote_tip=$rds_guard_local_tip
  if test "$rds_guard_ref_phase" = 'plan-unpublished'; then
    rds_run_producer "$rds_guard_ref_root/parent.out" "$rds_guard_ref_root/parent.err" git rev-parse HEAD^
    test ! -s "$rds_guard_ref_root/parent.err"
    test "$(awk 'END { print NR }' "$rds_guard_ref_root/parent.out")" = '1'
    IFS= read -r rds_guard_remote_tip < "$rds_guard_ref_root/parent.out"
  fi
  case "$rds_guard_remote_tip" in ''|*[!0-9a-f]*) return 1 ;; esac
  test "${#rds_guard_remote_tip}" = '40'
  printf '%s\t%s\t%s\n' \
    'refs/heads/bootstrap/rds-main' '9193123daad52fe028e68e204d8c409d169cf370' commit \
    'refs/heads/neutral/v7.2.1-neutral.1' "$rds_guard_local_tip" commit \
    'refs/remotes/origin/main' '9193123daad52fe028e68e204d8c409d169cf370' commit \
    'refs/remotes/origin/neutral/v7.2.1-neutral.1' "$rds_guard_remote_tip" commit > "$rds_guard_ref_root/allowed-refs.raw"
  sort "$rds_guard_ref_root/allowed-refs.raw" > "$rds_guard_ref_root/allowed-refs"
  rds_run_producer "$rds_guard_ref_root/all-refs.raw" "$rds_guard_ref_root/all-refs.err" git for-each-ref --format='%(refname)%09%(objectname)%09%(objecttype)'
  test ! -s "$rds_guard_ref_root/all-refs.err"
  test -s "$rds_guard_ref_root/all-refs.raw"
  sort "$rds_guard_ref_root/all-refs.raw" > "$rds_guard_ref_root/all-refs"
  cmp "$rds_guard_ref_root/allowed-refs" "$rds_guard_ref_root/all-refs"
  printf '%s\n' \
    'branch.main.merge refs/heads/main' \
    'branch.main.remote origin' \
    'branch.neutral/v7.2.1-neutral.1.merge refs/heads/neutral/v7.2.1-neutral.1' \
    'branch.neutral/v7.2.1-neutral.1.remote origin' \
    'remote.origin.fetch +refs/heads/*:refs/remotes/origin/*' \
    'remote.origin.url git@github.com:joeroberts/terraform-aws-rds.git' > "$rds_guard_ref_root/allowed-remote-config.raw"
  sort "$rds_guard_ref_root/allowed-remote-config.raw" > "$rds_guard_ref_root/allowed-remote-config"
  rds_run_producer "$rds_guard_ref_root/all-remote-config.raw" "$rds_guard_ref_root/all-remote-config.err" git config --local --get-regexp '^(remote\.|branch\.)'
  test ! -s "$rds_guard_ref_root/all-remote-config.err"
  test -s "$rds_guard_ref_root/all-remote-config.raw"
  sort "$rds_guard_ref_root/all-remote-config.raw" > "$rds_guard_ref_root/all-remote-config"
  cmp "$rds_guard_ref_root/allowed-remote-config" "$rds_guard_ref_root/all-remote-config"
  rds_run_producer "$rds_guard_ref_root/upstream.out" "$rds_guard_ref_root/upstream.err" git rev-parse --abbrev-ref --symbolic-full-name '@{upstream}'
  test ! -s "$rds_guard_ref_root/upstream.err"
  printf '%s\n' 'origin/neutral/v7.2.1-neutral.1' > "$rds_guard_ref_root/expected-upstream"
  cmp "$rds_guard_ref_root/expected-upstream" "$rds_guard_ref_root/upstream.out"
}

rds_require_missing_object() {
  rds_guard_missing_root=$1
  rds_guard_missing_sha=$2
  mkdir -p "$rds_guard_missing_root"
  case "$rds_guard_missing_sha" in ''|*[!0-9a-f]*) return 1 ;; esac
  test "${#rds_guard_missing_sha}" = '40'
  printf '%s\n' "$rds_guard_missing_sha" > "$rds_guard_missing_root/query"
  set +e
  git cat-file --batch-check < "$rds_guard_missing_root/query" > "$rds_guard_missing_root/result.out" 2> "$rds_guard_missing_root/result.err"
  rds_guard_missing_status=$?
  set -e
  test "$rds_guard_missing_status" = '0'
  test ! -s "$rds_guard_missing_root/result.err"
  printf '%s missing\n' "$rds_guard_missing_sha" > "$rds_guard_missing_root/expected.out"
  cmp "$rds_guard_missing_root/expected.out" "$rds_guard_missing_root/result.out"
}

rds_history_expect_commit() {
  rds_guard_commit=$1
  rds_guard_parent=$2
  rds_guard_subject=$3
  rds_guard_mode=$4
  rds_guard_scope=$5
  rds_guard_label=$6
  git show -s --format='%H%x09%P%x09%s' "$rds_guard_commit" > "$rds_guard_history_root/$rds_guard_label.metadata"
  printf '%s\t%s\t%s\n' "$rds_guard_commit" "$rds_guard_parent" "$rds_guard_subject" > "$rds_guard_history_root/$rds_guard_label.expected-metadata"
  cmp "$rds_guard_history_root/$rds_guard_label.expected-metadata" "$rds_guard_history_root/$rds_guard_label.metadata"
  git diff-tree --root --no-commit-id --name-status -r "$rds_guard_commit" > "$rds_guard_history_root/$rds_guard_label.scope.raw"
  sort "$rds_guard_history_root/$rds_guard_label.scope.raw" > "$rds_guard_history_root/$rds_guard_label.scope"
  case "$rds_guard_mode" in
    empty)
      test ! -s "$rds_guard_history_root/$rds_guard_label.scope"
      ;;
    exact-A|exact-M)
      rds_guard_status=${rds_guard_mode#exact-}
      awk -v status="$rds_guard_status" '{ print status "\t" $0 }' "$rds_guard_scope" > "$rds_guard_history_root/$rds_guard_label.expected-scope"
      sort "$rds_guard_history_root/$rds_guard_label.expected-scope" > "$rds_guard_history_root/$rds_guard_label.expected-scope.sorted"
      cmp "$rds_guard_history_root/$rds_guard_label.expected-scope.sorted" "$rds_guard_history_root/$rds_guard_label.scope"
      ;;
    subset-M)
      test -s "$rds_guard_history_root/$rds_guard_label.scope"
      while IFS=$'\t' read -r rds_guard_status rds_guard_path; do
        test "$rds_guard_status" = 'M'
        test -n "$rds_guard_path"
        awk -v path="$rds_guard_path" '$0 == path { found = 1 } END { exit(found ? 0 : 1) }' "$rds_guard_scope"
      done < "$rds_guard_history_root/$rds_guard_label.scope"
      ;;
    *) return 1 ;;
  esac
  if test "$rds_guard_mode" != 'empty'; then
    awk -F '\t' '{ print $2 }' "$rds_guard_history_root/$rds_guard_label.scope" >> "$rds_guard_allowed_paths_raw"
  fi
}

rds_validate_history() {
  rds_guard_history_root=$1
  rds_guard_phase=$2
  rds_guard_approved_record=$3
  rds_guard_upstream_sha=$4
  rds_guard_task1_scope=$5
  rds_guard_task2_scope=$6
  rds_guard_task3_scope=$7
  rds_guard_fix_allowlist=$8
  mkdir -p "$rds_guard_history_root"
  rds_guard_allowed_paths_raw="$rds_guard_history_root/allowed-paths.raw"
  : > "$rds_guard_allowed_paths_raw"
  printf '%s\n' docs/superpowers/plans/2026-08-12-rds-neutral-derivative.md docs/superpowers/status/2026-08-12-rds-neutral-derivative-blocker.md > "$rds_guard_history_root/plan-scope"
  printf '%s\n' docs/superpowers/plans/2026-08-12-rds-neutral-derivative.md > "$rds_guard_history_root/planning-scope"
  printf '%s\n' docs/superpowers/status/2026-08-12-rds-neutral-derivative-blocker.md > "$rds_guard_history_root/blocker-scope"
  git rev-list --reverse HEAD > "$rds_guard_history_root/branch-commits"
  rds_guard_commit_count=$(awk 'END { print NR }' "$rds_guard_history_root/branch-commits")
  case "$rds_guard_commit_count" in ''|*[!0-9]*) return 1 ;; esac
  test "$rds_guard_commit_count" -ge '5'
  rds_guard_commits=()
  while IFS= read -r rds_guard_commit; do
    test -n "$rds_guard_commit"
    rds_guard_commits[${#rds_guard_commits[@]}]="$rds_guard_commit"
  done < "$rds_guard_history_root/branch-commits"
  test "${#rds_guard_commits[@]}" = "$rds_guard_commit_count"
  test "${rds_guard_commits[0]}" = '9193123daad52fe028e68e204d8c409d169cf370'
  test "${rds_guard_commits[1]}" = 'bf6257ef065914832fd11e570ed82cc98c6ce072'
  test "${rds_guard_commits[2]}" = 'ffa16b253e97aa8d15177ba71febbac75bf8cc2c'
  test "${rds_guard_commits[3]}" = '46e1fb90ea73281a3e8a75e1e0a7f10e1445f2a8'
  rds_history_expect_commit "${rds_guard_commits[0]}" '' 'chore: initialize repository' empty "$rds_guard_history_root/plan-scope" bootstrap
  rds_history_expect_commit "${rds_guard_commits[1]}" "${rds_guard_commits[0]}" 'docs: plan neutral RDS module implementation' exact-A "$rds_guard_history_root/planning-scope" planning
  rds_history_expect_commit "${rds_guard_commits[2]}" "${rds_guard_commits[1]}" 'docs: record RDS neutralization blocker' exact-A "$rds_guard_history_root/blocker-scope" blocker
  rds_history_expect_commit "${rds_guard_commits[3]}" "${rds_guard_commits[2]}" 'docs: authorize neutral RDS execution plan' exact-M "$rds_guard_history_root/plan-scope" authorization
  rds_guard_index=4
  rds_guard_round=1
  rds_guard_parent=${rds_guard_commits[3]}
  while test "$rds_guard_index" -lt "$rds_guard_commit_count" && test "$rds_guard_round" -le '5'; do
    git show -s --format=%s "${rds_guard_commits[$rds_guard_index]}" > "$rds_guard_history_root/next-subject"
    IFS= read -r rds_guard_next_subject < "$rds_guard_history_root/next-subject"
    rds_guard_expected_subject="docs: close RDS plan review round $rds_guard_round"
    if test "$rds_guard_next_subject" != "$rds_guard_expected_subject"; then
      break
    fi
    rds_history_expect_commit "${rds_guard_commits[$rds_guard_index]}" "$rds_guard_parent" "$rds_guard_expected_subject" exact-M "$rds_guard_history_root/plan-scope" "plan-round-$rds_guard_round"
    rds_guard_parent=${rds_guard_commits[$rds_guard_index]}
    rds_guard_index=$((rds_guard_index + 1))
    rds_guard_round=$((rds_guard_round + 1))
  done
  test "$rds_guard_round" -ge '2'
  rds_guard_plan_tip=$rds_guard_parent
  rds_guard_plan_parent=$(git show -s --format=%P "$rds_guard_plan_tip")
  if test "$rds_guard_approved_record" != '-'; then
    printf '%s\t%s\n' "$rds_guard_plan_tip" "$rds_guard_plan_parent" > "$rds_guard_history_root/computed-approved-plan"
    cmp "$rds_guard_approved_record" "$rds_guard_history_root/computed-approved-plan"
  fi
  case "$rds_guard_phase" in
    plan|plan-unpublished) ;;
    task1|task2|task3|task3-or-review-fix)
      test "$rds_guard_index" -lt "$rds_guard_commit_count"
      rds_history_expect_commit "${rds_guard_commits[$rds_guard_index]}" "$rds_guard_parent" 'feat: import neutral RDS module v7.2.1' exact-A "$rds_guard_task1_scope" task1
      rds_guard_parent=${rds_guard_commits[$rds_guard_index]}
      rds_guard_index=$((rds_guard_index + 1))
      ;;
    *) return 1 ;;
  esac
  case "$rds_guard_phase" in
    task2|task3|task3-or-review-fix)
      test "$rds_guard_index" -lt "$rds_guard_commit_count"
      rds_history_expect_commit "${rds_guard_commits[$rds_guard_index]}" "$rds_guard_parent" 'docs: point RDS consumers to neutral sources' exact-M "$rds_guard_task2_scope" task2
      rds_guard_parent=${rds_guard_commits[$rds_guard_index]}
      rds_guard_index=$((rds_guard_index + 1))
      ;;
  esac
  case "$rds_guard_phase" in
    task3|task3-or-review-fix)
      test "$rds_guard_index" -lt "$rds_guard_commit_count"
      rds_history_expect_commit "${rds_guard_commits[$rds_guard_index]}" "$rds_guard_parent" 'ci: pin and restrict inherited workflows' exact-M "$rds_guard_task3_scope" task3
      rds_guard_parent=${rds_guard_commits[$rds_guard_index]}
      rds_guard_index=$((rds_guard_index + 1))
      ;;
  esac
  if test "$rds_guard_phase" = 'task3-or-review-fix' && test "$rds_guard_index" -lt "$rds_guard_commit_count"; then
    rds_history_expect_commit "${rds_guard_commits[$rds_guard_index]}" "$rds_guard_parent" 'fix: address independent RDS review findings' subset-M "$rds_guard_fix_allowlist" review-fix
    rds_guard_parent=${rds_guard_commits[$rds_guard_index]}
    rds_guard_index=$((rds_guard_index + 1))
  fi
  test "$rds_guard_index" = "$rds_guard_commit_count"
  test "$rds_guard_parent" = "$(git rev-parse HEAD)"
  printf '%s\t%s\n' "$rds_guard_plan_tip" "$rds_guard_plan_parent" > "$rds_guard_history_root/approved-plan-output"
  git rev-list --all > "$rds_guard_history_root/all-commits.raw"
  sort "$rds_guard_history_root/all-commits.raw" > "$rds_guard_history_root/all-commits"
  sort "$rds_guard_history_root/branch-commits" > "$rds_guard_history_root/allowed-commits"
  cmp "$rds_guard_history_root/allowed-commits" "$rds_guard_history_root/all-commits"
  git log --all --format= --name-only > "$rds_guard_history_root/all-history-paths.raw"
  awk 'NF' "$rds_guard_history_root/all-history-paths.raw" > "$rds_guard_history_root/all-history-paths.nonempty"
  sort -u "$rds_guard_history_root/all-history-paths.nonempty" > "$rds_guard_history_root/all-history-paths"
  sort -u "$rds_guard_allowed_paths_raw" > "$rds_guard_history_root/allowed-history-paths"
  cmp "$rds_guard_history_root/allowed-history-paths" "$rds_guard_history_root/all-history-paths"
  git rev-list --objects "${rds_guard_commits[@]}" > "$rds_guard_history_root/allowed-objects.raw"
  sort "$rds_guard_history_root/allowed-objects.raw" > "$rds_guard_history_root/allowed-objects"
  git rev-list --objects --all > "$rds_guard_history_root/all-objects.raw"
  sort "$rds_guard_history_root/all-objects.raw" > "$rds_guard_history_root/all-objects"
  cmp "$rds_guard_history_root/allowed-objects" "$rds_guard_history_root/all-objects"
  rds_validate_exact_ref_state "$rds_guard_history_root/ref-state" "$rds_guard_phase"
  rds_require_missing_object "$rds_guard_history_root/upstream-object" "$rds_guard_upstream_sha"
}
BASH
File.binwrite(path, bytes)
RUBY
rds_guard_sha='9ebe1644a5c5e2f232b320e991e4a60a80f94dcdbbc58e8d0a8c43ff42b80aca'
printf '%s  %s\n' "$rds_guard_sha" "$rds_guard_script" > "$rds_fixture_out/guard.sha256"
shasum -a 256 -c "$rds_fixture_out/guard.sha256"
. "$rds_guard_script"

rds_expect_reject() {
  rds_fixture_name=$1
  shift
  set +e
  "$@"
  rds_fixture_status=$?
  set -e
  test "$rds_fixture_status" != '0'
  printf 'PASS guard=%s bad=rejected\n' "$rds_fixture_name" >> "$rds_fixture_out/summary"
}

: > "$rds_fixture_out/summary"
rds_run_producer "$rds_fixture_out/producer-good.out" "$rds_fixture_out/producer-good.err" sh -c 'printf "complete\n"'
rds_expect_reject producer-exit bash -c 'set -euo pipefail; . "$1"; rds_run_producer "$2" "$3" sh -c "exit 42"' _ "$rds_guard_script" "$rds_fixture_out/producer-bad.out" "$rds_fixture_out/producer-bad.err"
rds_expect_reject producer-mid-read bash -c 'set -euo pipefail; . "$1"; rds_run_producer "$2" "$3" sh -c "printf partial\\n; exit 41"' _ "$rds_guard_script" "$rds_fixture_out/producer-mid.out" "$rds_fixture_out/producer-mid.err"
rds_require_empty_producer "$rds_fixture_out/empty-good.out" "$rds_fixture_out/empty-good.err" sh -c 'exit 0'
rds_expect_reject empty-producer-error bash -c 'set -euo pipefail; . "$1"; rds_require_empty_producer "$2" "$3" sh -c "printf partial\\n; printf fatal\\n >&2; exit 40"' _ "$rds_guard_script" "$rds_fixture_out/empty-bad.out" "$rds_fixture_out/empty-bad.err"

mkdir -p "$rds_fixture_root/expected" "$rds_fixture_root/good"
printf 'alpha\n' > "$rds_fixture_root/expected/a"
printf 'beta\n' > "$rds_fixture_root/expected/b"
cp -R "$rds_fixture_root/expected/." "$rds_fixture_root/good/"
printf '%s\n' a b > "$rds_fixture_out/expected-paths"
cp "$rds_fixture_out/expected-paths" "$rds_fixture_out/good-paths"
rds_require_path_hash_manifest "$rds_fixture_root/expected" "$rds_fixture_root/good" "$rds_fixture_out/expected-paths" "$rds_fixture_out/good-paths" "$rds_fixture_out/manifest-good"
for rds_case in added removed mutated; do
  rds_case_root="$rds_fixture_root/$rds_case"
  mkdir "$rds_case_root"
  cp -R "$rds_fixture_root/good/." "$rds_case_root/"
  cp "$rds_fixture_out/expected-paths" "$rds_fixture_out/$rds_case-paths"
  case "$rds_case" in
    added) printf 'extra\n' > "$rds_case_root/c"; printf 'c\n' >> "$rds_fixture_out/$rds_case-paths" ;;
    removed) mv "$rds_case_root/b" "$rds_fixture_root/recoverable-removed-b"; sed '/^b$/d' "$rds_fixture_out/expected-paths" > "$rds_fixture_out/$rds_case-paths" ;;
    mutated) printf 'changed\n' > "$rds_case_root/a" ;;
  esac
  rds_expect_reject "manifest-$rds_case" bash -c 'set -euo pipefail; . "$1"; rds_require_path_hash_manifest "$2" "$3" "$4" "$5" "$6"' _ "$rds_guard_script" "$rds_fixture_root/expected" "$rds_case_root" "$rds_fixture_out/expected-paths" "$rds_fixture_out/$rds_case-paths" "$rds_fixture_out/manifest-$rds_case"
done

mkdir "$rds_fixture_root/whitespace-good" "$rds_fixture_root/whitespace-bad"
printf 'clean\n' > "$rds_fixture_root/whitespace-good/file.txt"
printf 'trailing \n' > "$rds_fixture_root/whitespace-bad/file.txt"
printf '%s\n' file.txt > "$rds_fixture_out/whitespace-paths"
(
  cd "$rds_fixture_root/whitespace-good"
  rds_validate_worklist_whitespace "$rds_fixture_out/whitespace-paths" "$rds_fixture_out/unused-readme" "$rds_fixture_out/whitespace-good"
)
rds_expect_reject untracked-whitespace bash -c 'set -euo pipefail; . "$1"; cd "$2"; rds_validate_worklist_whitespace "$3" "$4" "$5"' _ "$rds_guard_script" "$rds_fixture_root/whitespace-bad" "$rds_fixture_out/whitespace-paths" "$rds_fixture_out/unused-readme" "$rds_fixture_out/whitespace-bad"

rds_consumer_good="$rds_fixture_root/consumer-good"
rds_consumer_bad="$rds_fixture_root/consumer-bad"
mkdir -p "$rds_consumer_good/wrappers" "$rds_consumer_bad"
printf '%s\n' wrappers/README.md wrappers/a/README.md wrappers/b/README.md wrappers/c/README.md wrappers/d/README.md wrappers/e/README.md wrappers/f/README.md > "$rds_fixture_out/wrapper-list"
ruby - "$rds_consumer_good" "$rds_fixture_out/wrapper-list" <<'RUBY'
require "fileutils"
root, list = ARGV
notice = "<!-- Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md. -->"
File.binwrite(File.join(root, "README.md"), ([notice, 'source = "git::ssh://git@github.com/joeroberts/terraform-aws-rds.git?ref=v7.2.1-neutral.1"', 'source = "git::ssh://git@github.com/joeroberts/terraform-aws-rds.git?ref=v7.2.1-neutral.1"'].join("\n") + "\n"))
File.readlines(list, chomp: true).each do |relative|
  path = File.join(root, relative)
  FileUtils.mkdir_p(File.dirname(path))
  subpath = relative.delete_suffix("/README.md")
  source = "git::ssh://git@github.com/joeroberts/terraform-aws-rds.git//#{subpath}?ref=v7.2.1-neutral.1"
  File.binwrite(path, [notice, %(source = "#{source}"), %(source = "#{source}"), %(# source = "#{source}")].join("\n") + "\n")
end
RUBY
cp -R "$rds_consumer_good/." "$rds_consumer_bad/"
rds_validate_wrapper_sources "$rds_consumer_good" "$rds_fixture_out/wrapper-list"
sed 's#//wrappers/a?ref=#//wrappers/f?ref=#' "$rds_consumer_bad/wrappers/a/README.md" > "$rds_fixture_out/wrong-source"
mv "$rds_fixture_out/wrong-source" "$rds_consumer_bad/wrappers/a/README.md"
rds_expect_reject wrapper-source-map bash -c 'set -euo pipefail; . "$1"; rds_validate_wrapper_sources "$2" "$3"' _ "$rds_guard_script" "$rds_consumer_bad" "$rds_fixture_out/wrapper-list"

rds_notice_good="$rds_fixture_root/notice-good"
rds_notice_bad="$rds_fixture_root/notice-bad"
mkdir "$rds_notice_good" "$rds_notice_bad"
: > "$rds_fixture_out/notice-paths"
rds_notice_index=1
while test "$rds_notice_index" -le '19'; do
  if test "$rds_notice_index" -le '9'; then rds_notice_path="file-$rds_notice_index.md"; rds_notice_line='<!-- Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md. -->'; else rds_notice_path="file-$rds_notice_index.tf"; rds_notice_line='# Modified by joeroberts/terraform-aws-rds on 2026-08-12; see UPSTREAM.md.'; fi
  printf '%s\n' "$rds_notice_path" >> "$rds_fixture_out/notice-paths"
  printf '%s\n' "$rds_notice_line" > "$rds_notice_good/$rds_notice_path"
  printf '%s\n' "$rds_notice_line" > "$rds_notice_bad/$rds_notice_path"
  rds_notice_index=$((rds_notice_index + 1))
done
rds_validate_notices "$rds_notice_good" "$rds_fixture_out/notice-paths"
printf '%s\n' '<!-- Modified by joeroberts/terraform-aws-rds on 2026-08-13; see UPSTREAM.md. -->' > "$rds_notice_bad/file-1.md"
rds_expect_reject notice-bytes bash -c 'set -euo pipefail; . "$1"; rds_validate_notices "$2" "$3"' _ "$rds_guard_script" "$rds_notice_bad" "$rds_fixture_out/notice-paths"

printf '%s\n' \
  '  create_db_subnet_group    = var.create_db_subnet_group && var.putin_khuylo' \
  '  create_db_parameter_group = var.create_db_parameter_group && var.putin_khuylo' \
  '  create_db_instance        = var.create_db_instance && var.putin_khuylo' > "$rds_fixture_out/direct-pristine-good.tf"
rds_validate_direct_expressions absent "$rds_fixture_out/direct-pristine-good.tf" "$rds_fixture_out/direct-pristine-good"
printf 'PASS guard=direct-pristine-absence good=accepted\n' >> "$rds_fixture_out/summary"
cp "$rds_fixture_out/direct-pristine-good.tf" "$rds_fixture_out/direct-pristine-bad.tf"
printf '%s\n' '  create_db_instance        = var.create_db_instance' >> "$rds_fixture_out/direct-pristine-bad.tf"
rds_expect_reject direct-pristine-exact-present /bin/bash -c 'set -euo pipefail; . "$1"; rds_validate_direct_expressions absent "$2" "$3"' _ "$rds_guard_script" "$rds_fixture_out/direct-pristine-bad.tf" "$rds_fixture_out/direct-pristine-bad"

printf '%s\n' \
  '  create_db_subnet_group    = var.create_db_subnet_group' \
  '  create_db_parameter_group = var.create_db_parameter_group' \
  '  create_db_instance        = var.create_db_instance' > "$rds_fixture_out/direct-sanitized-good.tf"
rds_validate_direct_expressions exact "$rds_fixture_out/direct-sanitized-good.tf" "$rds_fixture_out/direct-sanitized-good"
printf 'PASS guard=direct-sanitized-exact good=accepted\n' >> "$rds_fixture_out/summary"
printf '%s\n' \
  'prefix  create_db_subnet_group    = var.create_db_subnet_group' \
  '  create_db_parameter_group = var.create_db_parameter_group suffix' \
  '  create_db_instance        = var.create_db_instance' > "$rds_fixture_out/direct-sanitized-bad.tf"
rds_expect_reject direct-sanitized-prefix-suffix /bin/bash -c 'set -euo pipefail; . "$1"; rds_validate_direct_expressions exact "$2" "$3"' _ "$rds_guard_script" "$rds_fixture_out/direct-sanitized-bad.tf" "$rds_fixture_out/direct-sanitized-bad"

printf 'safe\n' > "$rds_fixture_out/rg-input"
rds_require_rg_no_match "$rds_fixture_out/rg-good.out" "$rds_fixture_out/rg-good.err" -n 'never-match' "$rds_fixture_out/rg-input"
rds_expect_reject rg-operational-error bash -c 'set -euo pipefail; . "$1"; rds_require_rg_no_match "$2" "$3" -n never-match "$4"' _ "$rds_guard_script" "$rds_fixture_out/rg-bad.out" "$rds_fixture_out/rg-bad.err" "$rds_fixture_root/does-not-exist"

printf '%s\n' 'https://github.com/joeroberts/terraform-aws-rds/pull/17' > "$rds_fixture_out/create-good"
rds_parse_pr_create_url "$rds_fixture_out/create-good" "$rds_fixture_out/pr-number"
test "$(sed -n '1p' "$rds_fixture_out/pr-number")" = '17'
printf '%s\n' 'https://github.com/another/repository/pull/17' > "$rds_fixture_out/create-bad"
rds_expect_reject pr-create-url bash -c 'set -euo pipefail; . "$1"; rds_parse_pr_create_url "$2" "$3"' _ "$rds_guard_script" "$rds_fixture_out/create-bad" "$rds_fixture_out/pr-number-bad"
printf 'https://github.com/joeroberts/terraform-aws-rds/pull/17\t17\tOPEN\tmain\tneutral/v7.2.1-neutral.1\tgood-head\tfeat: Add neutral RDS module v7.2.1\n' > "$rds_fixture_out/readback-good"
rds_validate_pr_readback "$rds_fixture_out/readback-good" 'https://github.com/joeroberts/terraform-aws-rds/pull/17' '17' 'neutral/v7.2.1-neutral.1' 'good-head' 'feat: Add neutral RDS module v7.2.1'
sed $'s/\tmain\t/\trelease\t/' "$rds_fixture_out/readback-good" > "$rds_fixture_out/readback-bad"
rds_expect_reject pr-readback-context bash -c 'set -euo pipefail; . "$1"; rds_validate_pr_readback "$2" "$3" "$4" "$5" "$6" "$7"' _ "$rds_guard_script" "$rds_fixture_out/readback-bad" 'https://github.com/joeroberts/terraform-aws-rds/pull/17' '17' 'neutral/v7.2.1-neutral.1' 'good-head' 'feat: Add neutral RDS module v7.2.1'

rds_marker_root="$rds_fixture_root/marker"
rds_old_run='20260813T010101Z-1-1'
rds_new_run='20260813T020202Z-2-2'
mkdir -p "$rds_marker_root/task4-runs/$rds_old_run"
printf 'RUN run=%s head=old-head\nFINAL PASS run=%s head=old-head\n' "$rds_old_run" "$rds_old_run" > "$rds_marker_root/task4-active-log"
printf '%s\n' '{"schema":1,"result":"PASS","run_id":"20260813T010101Z-1-1","head":"old-head","log_sha256":"sentinel"}' > "$rds_marker_root/task4-active-result.json"
cp "$rds_marker_root/task4-active-result.json" "$rds_marker_root/task4-active-marker.json"
rds_prepare_task4_run "$rds_marker_root" "$rds_new_run"
test ! -e "$rds_marker_root/task4-active-marker.json"
test -f "$rds_marker_root/task4-quarantine/$rds_new_run/task4-active-marker.json"
rds_expect_reject task4-early-failure bash -c 'set -euo pipefail; . "$1"; rds_validate_task4_result "$2" new-head' _ "$rds_guard_script" "$rds_marker_root"
printf 'RUN run=%s head=new-head\nFINAL PASS run=%s head=new-head\n' "$rds_new_run" "$rds_new_run" > "$rds_marker_root/task4-runs/$rds_new_run/validation.log"
rds_publish_task4_result "$rds_marker_root" "$rds_new_run" 'new-head' "$rds_marker_root/task4-runs/$rds_new_run/validation.log"
rds_run_producer "$rds_fixture_out/marker-run-id" "$rds_fixture_out/marker.err" rds_validate_task4_result "$rds_marker_root" 'new-head'
test "$(sed -n '1p' "$rds_fixture_out/marker-run-id")" = "$rds_new_run"
printf 'corrupt\n' >> "$rds_marker_root/task4-active-log"
rds_expect_reject task4-log-binding bash -c 'set -euo pipefail; . "$1"; rds_validate_task4_result "$2" new-head' _ "$rds_guard_script" "$rds_marker_root"

rds_require_missing_object "$rds_fixture_out/missing-object-good" '9920097a40175c084c46fee1c306fa61cdbaf823'
printf 'PASS guard=missing-object-good good=accepted\n' >> "$rds_fixture_out/summary"

rds_history_good="$rds_fixture_root/history-good"
rds_run_producer "$rds_fixture_out/history-clone.out" "$rds_fixture_out/history-clone.err" git clone --quiet --no-local "$rds_fixture_worktree" "$rds_history_good"
test ! -s "$rds_fixture_out/history-clone.out"
test ! -s "$rds_fixture_out/history-clone.err"
git -C "$rds_history_good" symbolic-ref -d refs/remotes/origin/HEAD
git -C "$rds_history_good" update-ref -d refs/remotes/origin/bootstrap/rds-main
git -C "$rds_history_good" update-ref refs/heads/bootstrap/rds-main '9193123daad52fe028e68e204d8c409d169cf370'
git -C "$rds_history_good" update-ref refs/remotes/origin/main '9193123daad52fe028e68e204d8c409d169cf370'
rds_run_producer "$rds_fixture_out/history-head.out" "$rds_fixture_out/history-head.err" git -C "$rds_history_good" rev-parse HEAD
test ! -s "$rds_fixture_out/history-head.err"
test "$(awk 'END { print NR }' "$rds_fixture_out/history-head.out")" = '1'
IFS= read -r rds_history_head < "$rds_fixture_out/history-head.out"
rds_run_producer "$rds_fixture_out/history-parent.out" "$rds_fixture_out/history-parent.err" git -C "$rds_history_good" rev-parse HEAD^
test ! -s "$rds_fixture_out/history-parent.err"
test "$(awk 'END { print NR }' "$rds_fixture_out/history-parent.out")" = '1'
IFS= read -r rds_history_parent < "$rds_fixture_out/history-parent.out"
git -C "$rds_history_good" update-ref refs/remotes/origin/neutral/v7.2.1-neutral.1 "$rds_history_parent"
git -C "$rds_history_good" remote set-url origin 'git@github.com:joeroberts/terraform-aws-rds.git'
git -C "$rds_history_good" config branch.main.remote origin
git -C "$rds_history_good" config branch.main.merge refs/heads/main
git -C "$rds_history_good" config branch.neutral/v7.2.1-neutral.1.remote origin
git -C "$rds_history_good" config branch.neutral/v7.2.1-neutral.1.merge refs/heads/neutral/v7.2.1-neutral.1
: > "$rds_fixture_out/history-unused-scope"
/bin/bash -c 'set -euo pipefail; cd "$1"; . "$2"; rds_validate_history "$3" plan-unpublished - "$4" "$5" "$5" "$5" "$5"' _ "$rds_history_good" "$rds_guard_script_abs" "$rds_fixture_out/history-good-result" '9920097a40175c084c46fee1c306fa61cdbaf823' "$rds_fixture_out/history-unused-scope"
printf 'PASS guard=history-ref-state-good good=accepted\n' >> "$rds_fixture_out/summary"

rds_history_tag="$rds_fixture_root/history-bad-tag"
cp -R "$rds_history_good" "$rds_history_tag"
git -C "$rds_history_tag" update-ref refs/tags/fixture-lightweight "$rds_history_head"
rds_expect_reject history-lightweight-tag /bin/bash -c 'set -euo pipefail; cd "$1"; . "$2"; rds_validate_history "$3" plan-unpublished - "$4" "$5" "$5" "$5" "$5"' _ "$rds_history_tag" "$rds_guard_script_abs" "$rds_fixture_out/history-tag-result" '9920097a40175c084c46fee1c306fa61cdbaf823' "$rds_fixture_out/history-unused-scope"

rds_history_other="$rds_fixture_root/history-bad-other-ref"
cp -R "$rds_history_good" "$rds_history_other"
git -C "$rds_history_other" update-ref refs/archive/fixture "$rds_history_head"
rds_expect_reject history-nonstandard-ref /bin/bash -c 'set -euo pipefail; cd "$1"; . "$2"; rds_validate_history "$3" plan-unpublished - "$4" "$5" "$5" "$5" "$5"' _ "$rds_history_other" "$rds_guard_script_abs" "$rds_fixture_out/history-other-ref-result" '9920097a40175c084c46fee1c306fa61cdbaf823' "$rds_fixture_out/history-unused-scope"

rds_fake_git_dir="$rds_fixture_root/fake-git"
mkdir "$rds_fake_git_dir"
ruby - "$rds_fake_git_dir/git" <<'RUBY'
path = ARGV.fetch(0)
bytes = <<'SH'
#!/bin/sh
if test "$1" = 'cat-file' && test "$2" = '--batch-check'; then
  case "${RDS_FIXTURE_CAT_MODE-}" in
    operational) printf '%s\n' 'fixture cat-file operational failure' >&2; exit 77 ;;
    malformed) printf '%s\n' 'malformed batch response'; exit 0 ;;
  esac
fi
exec /usr/bin/git "$@"
SH
File.binwrite(path, bytes)
File.chmod(0o755, path)
RUBY
rds_expect_reject missing-object-operational /usr/bin/env RDS_FIXTURE_CAT_MODE=operational PATH="$rds_fake_git_dir:$PATH" /bin/bash -c 'set -euo pipefail; cd "$1"; . "$2"; rds_validate_history "$3" plan-unpublished - "$4" "$5" "$5" "$5" "$5"' _ "$rds_history_good" "$rds_guard_script_abs" "$rds_fixture_out/history-cat-operational-result" '9920097a40175c084c46fee1c306fa61cdbaf823' "$rds_fixture_out/history-unused-scope"
rds_expect_reject missing-object-malformed /usr/bin/env RDS_FIXTURE_CAT_MODE=malformed PATH="$rds_fake_git_dir:$PATH" /bin/bash -c 'set -euo pipefail; cd "$1"; . "$2"; rds_validate_history "$3" plan-unpublished - "$4" "$5" "$5" "$5" "$5"' _ "$rds_history_good" "$rds_guard_script_abs" "$rds_fixture_out/history-cat-malformed-result" '9920097a40175c084c46fee1c306fa61cdbaf823' "$rds_fixture_out/history-unused-scope"

test "$(awk 'END { print NR }' "$rds_fixture_out/summary")" = '24'
cat "$rds_fixture_out/summary"
```

Expected: the exact production library digest passes; all four named good cases are accepted and all 20 named bad guard cases are rejected. The round-2 18 rejections remain. Exact direct-expression fixtures additionally accept pristine suffixed upstream lines as absence, reject a pristine exact direct line, accept exactly one of each sanitized whole line, and reject sanitized prefix/suffix mutations. No label claims coverage for a guard that was not invoked.
