# Nirawit Thepsawade · QA Lead

Personal CV / portfolio site. QA Lead based in Bangkok, 5+ years across
Web, API, Mobile, POS, and Core Banking. Currently building the QA
function at Ayodia.

> **Live site:** <https://bestniawit.github.io/nirawit-cv/>

## What's in this repo

```text
.
├── index.html                                 # the site
├── assets/
│   ├── css/main.css                           # MyResume template (BootstrapMade)
│   ├── js/main.js                             # template JS
│   ├── vendor/                                # Bootstrap 5, AOS, Swiper, GLightbox, Isotope, etc.
│   ├── img/                                   # profile-img.jpg + portfolio thumbs
│   ├── favicon.svg                            # custom SVG favicon
│   └── Nirawit_Thepsawade_CV_2026.pdf         # downloadable CV
├── pipelines/                                 # portfolio: sample QA pipeline I author
│   ├── Jenkinsfile                            #   full Jenkins pipeline
│   └── README.md                              #   what it demonstrates
└── wrangler.jsonc                             # Cloudflare Workers static-asset config
```

Built on the [MyResume](https://bootstrapmade.com/free-html-bootstrap-template-my-resume/)
template by BootstrapMade (Bootstrap 5.3.3).

## Deploy

This site ships as static assets via Cloudflare Workers using
[`wrangler`](https://developers.cloudflare.com/workers/wrangler/).

```bash
npx wrangler deploy
```

`wrangler.jsonc` serves the repo root as static assets.

## Contact

- LinkedIn: [nirawit-thepsawade](https://www.linkedin.com/in/nirawit-thepsawade-169451236)
- Medium: [@nirawit.mail](https://medium.com/@nirawit.mail)
- Email: <nirawit.mail@gmail.com>
