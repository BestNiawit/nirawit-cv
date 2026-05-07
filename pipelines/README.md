# CI/CD Pipeline · Portfolio Sample

A **sample pipeline** authored by Nirawit Thepsawade, included in this
repo as a portfolio piece (not active build configuration for the CV
site itself).

The pipeline models a realistic full-stack QA flow I'd own as QA Lead.
It references fictional services (e.g. `staging.example.com`, the Slack
webhook secret `slack-qa-webhook`) so it will not run successfully if
wired to a real Jenkins instance. It is meant to be **read**.

## Files

| File | Platform | Purpose |
|------|----------|---------|
| [`Jenkinsfile`](Jenkinsfile) | Jenkins | Declarative pipeline, parallel lint, k6 perf gates, Slack + email notify, Grafana metric push |

## Stages

```text
Lint  →  Unit (JEST + coverage)  →  API (Robot Framework)  →
E2E (Playwright)  →  Performance (k6 with p95 + error-rate gates)  →
Quality Gate (coverage ≥ 80%)  →  Slack / Email notify  →  Grafana push
```

## What the gates demonstrate

- **Coverage gate** (`80%`): non-negotiable shipping rule
- **Perf p95 gate** (`< 800ms`): protects user-facing latency
- **Error-rate gate** (`< 1%`): catches regressions during k6 run
- **Slack on success + failure**: closes the loop with the team
- **Grafana pushgateway**: feeds the QA telemetry dashboards I build
