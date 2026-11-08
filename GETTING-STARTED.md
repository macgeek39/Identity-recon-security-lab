# Maintain this Identity Recon portfolio

This repository is already published to GitHub. Keep it focused on engineering outcomes, evidence, risks, and decisions—not copied course instructions.

## Document each milestone

1. Add a concise implementation report under `reports/`.
2. Save useful redacted screenshots under `evidence/checkpoint-XX/` and link them from the report.
3. Add reusable KQL and other safe artifacts under `queries/`.
4. Update the progress table in the root `README.md`.
5. Create CISO-style executive summaries for major findings or decisions, not every minor exercise.

## Current milestone

Checkpoint 2 — Range Setup: [Technical report](reports/2026-11-08-checkpoint-02-technical.md), [Executive update](reports/2026-11-08-checkpoint-02-ciso.md), [Evidence](evidence/checkpoint-02/).

November 8, 2026 validation screenshots show 122 sign-in events and 29 audit events in the queried 24-hour window. Complete log coverage and Sentinel detection rules remain untested.

## Apply future changes from a local clone

```bash
git status
git add README.md reports/ architecture/ evidence/ queries/
git commit -m "docs: add IAM milestone evidence"
git push origin main
```

Inspect `git status` and review all files for secrets, credentials, and unredacted identifiers before committing. Changes can also be made using GitHub's web editor.
