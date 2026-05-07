# CI/CD Pipelines · Portfolio Samples

These are **sample pipelines** authored by Nirawit Thepsawade — included
in this repo as a portfolio piece, not as active build configuration for
the CV site itself. The CV site is deployed via [`.github/workflows/deploy.yml`](../.github/workflows/deploy.yml).

Both pipelines model a realistic full-stack QA flow I'd own as QA Lead:
they reference fictional services (e.g. `staging.example.com`, the Slack
webhook secret `slack-qa-webhook`) so they will not run successfully if
wired to a real Jenkins / GitLab instance — they are meant to be **read**.

## Files

| File | Platform | Purpose |
|------|----------|---------|
| [`Jenkinsfile`](Jenkinsfile) | Jenkins | Declarative pipeline, parallel lint, k6 perf gates, Slack + email notify, Grafana metric push |
| [`.gitlab-ci.yml`](.gitlab-ci.yml) | GitLab CI | Same QA flow in GitLab format — JUnit + Cobertura reports, conditional perf stage |

## Stages (both pipelines)

```
Lint  →  Unit (JEST + coverage)  →  API (Robot Framework)  →
E2E (Playwright)  →  Performance (k6 with p95 + error-rate gates)  →
Quality Gate (coverage ≥ 80%)  →  Slack / Email notify  →  Grafana push
```

## Why two formats?

I've delivered both at different employers — Jenkins at TTB and Doppio,
GitLab CI at Fastwork — and want to show fluency in both. The patterns
(parallel stages, perf budgets, metric pushes, dual notifications) are
the same; only the syntax differs.

## What the budgets / gates demonstrate

- **Coverage gate** (`80%`) — non-negotiable shipping rule
- **Perf p95 gate** (`< 800ms`) — protects user-facing latency
- **Error-rate gate** (`< 1%`) — catches regressions during k6 run
- **Slack on success + failure** — closes the loop with the team
- **Grafana pushgateway** — feeds the QA telemetry dashboards I build
