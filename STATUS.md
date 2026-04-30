# felo-infra — Status

> Last updated: 2026-04-30
> See [program dashboard](https://github.com/RizwanZafaris/felo-docs/blob/main/STATUS.md).

## Purpose
Infrastructure-as-code, reusable GitHub Actions workflows, deploy runbooks, observability config.

## Owner
devops + sre-* (per squad).

## Current head
- branch: `main`
- last commit: scaffold initial commit
- log: https://github.com/RizwanZafaris/felo-infra/commits/main

## Reusable workflows

| Workflow | State | Consumers |
|---|---|---|
| `claude-final-review.yml` | scaffold | all 7 repos |
| `node-ci.yml` | scaffold | appbackendfelo, feloopsportal, felo-contracts |
| `flutter-ci.yml` | scaffold | appuifelo |

## Environments

| Env | State | Hosting target | Owner |
|---|---|---|---|
| dev | not provisioned | TBD | devops |
| staging | not provisioned | TBD | devops |
| prod | not provisioned | TBD | devops |

## Runbooks (planned)
- ocr-vendor-down.md
- fx-vendor-down.md
- payment-webhook-backlog.md
- migration-rollback.md
- mfa-replay-detected.md
- mass-refund-procedure.md

## Observability stack
- Sentry (errors) — not wired
- OpenTelemetry (traces) — not wired
- Grafana / Loki (dashboards + logs) — not wired

## How to update
- devops: update environment + observability rows when each goes live.
