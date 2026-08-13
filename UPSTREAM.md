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
