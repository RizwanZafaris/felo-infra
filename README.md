# felo-infra

FELO infrastructure-as-code, reusable GitHub Actions workflows, deploy runbooks, and observability config.

## Owned by

`devops` agent (with `cto` approval for production changes).

## Contents

```
terraform/                # provider configs, modules
.github/workflow-templates/  # reusable workflows referenced by other repos
runbooks/                 # incident + deployment runbooks
observability/            # Sentry, OTel, Grafana dashboards as code
```

## Reusable workflows (consumed by other repos)

- `claude-final-review.yml` — gates merges to `main` behind Claude Code review
- `node-ci.yml` — lint + test + build for Node/TS repos
- `flutter-ci.yml` — analyze + test + build for Flutter
- `next-ci.yml` — lint + test + build for Next.js portal

Repos consume them via:

```yaml
jobs:
  ci:
    uses: RizwanZafaris/felo-infra/.github/workflow-templates/node-ci.yml@main
```

## Deploy environments

| Env     | Purpose                  | Auto-deploy on |
|---------|--------------------------|----------------|
| dev     | engineer scratchpad      | push to feat/* |
| staging | pre-prod verification    | merge to main  |
| prod    | production               | manual approval |
