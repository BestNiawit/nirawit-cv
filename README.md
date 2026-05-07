# Nirawit Thepsawade — QA Lead

[![Deploy CV](https://github.com/BestNiawit/nirawit-cv/actions/workflows/deploy.yml/badge.svg)](https://github.com/BestNiawit/nirawit-cv/actions/workflows/deploy.yml)

Personal CV / portfolio site — QA Lead based in Bangkok, 5+ years across
Web, API, Mobile, POS, and Core Banking. Currently pioneering the QA
function at Ayodia.

> **Live site:** https://bestniawit.github.io/nirawit-cv/

---

## What's in this repo

```
.
├── index.html                       # the site
├── assets/                          # CSS, JS, favicon, CV PDF
│   ├── css/style.css
│   ├── js/main.js
│   └── favicon.svg
├── pipelines/                       # ← portfolio: sample QA pipelines I author
│   ├── Jenkinsfile                  #   full Jenkins pipeline
│   ├── .gitlab-ci.yml               #   GitLab CI equivalent
│   └── README.md                    #   what each demonstrates
└── .github/workflows/deploy.yml     # ← real pipeline that deploys this site
```

## The two pipelines tell two stories

| Folder | Status | What it proves |
|--------|--------|----------------|
| [`pipelines/`](pipelines/) | sample / read-only | I can architect a full QA pipeline (lint → unit → API → E2E → k6 perf → quality gates → Slack + Grafana). Pinned to fake services on purpose. |
| [`.github/workflows/`](.github/workflows/) | live | I actually ship CI/CD — every push to `main` runs HTML validation, link check, Lighthouse budgets, then deploys to GitHub Pages. |

## QA gates on every deploy

The deploy workflow refuses to ship if any of these fail:

- HTML5 validation (W3C)
- Link checker (no broken links)
- Lighthouse: **accessibility ≥ 90**, **SEO ≥ 90** (errors)
- Lighthouse: **performance ≥ 85**, **best-practices ≥ 85** (warnings)

## Contact

- LinkedIn — [nirawit-thepsawade](https://www.linkedin.com/in/nirawit-thepsawade-169451236)
- Medium — [@nirawit.mail](https://medium.com/@nirawit.mail)
- Email — nirawit.mail@gmail.com
