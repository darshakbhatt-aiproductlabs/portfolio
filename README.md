# portfolio

**Darshak Bhatt — AI-first portfolio.** Senior Product Leader · $21M+ impact · AI Generalist.

🌐 **Live:** https://darshakbhatt-portfolio.pages.dev/
📄 **Resume PDF:** [link](https://media.journoportfolio.com/users/327690/uploads/64022180-ce94-42d9-b754-ee676dbd2d6a.pdf)
💼 **LinkedIn:** [in/darshak-bhatt](https://www.linkedin.com/in/darshak-bhatt/)
✉️ **Email:** darshakbhatt94@gmail.com

---

## What this is

A GitHub-hosted, single-file static portfolio designed to be **AI-first**: every interaction is built so an AI agent can read, summarise, and reason about Darshak's work without scraping.

### What makes it AI-first

| Surface                          | What it gives an AI agent                                                        |
| -------------------------------- | -------------------------------------------------------------------------------- |
| [`/llms.txt`](docs/llms.txt)     | Plain-text profile in the emerging LLM-friendly format. Identity, work, projects, fit. |
| [`/resume.json`](docs/resume.json) | Machine-readable [JSON Resume](https://jsonresume.org) — drop into any parser. |
| Inline JSON-LD                   | Schema.org `Person` + credentials + awards. Google/Bing rich results, AI grounding. |
| Open Graph + Twitter cards       | Link previews everywhere a recruiter shares it.                                  |
| `/robots.txt`                    | Explicitly allows GPTBot, ClaudeBot, PerplexityBot, Google-Extended, CCBot, et al. |
| `/sitemap.xml`                   | All anchors enumerated so crawlers see the structure.                            |
| **Ask-the-portfolio prompt box** | A visible UI that lets a visitor (recruiter or AI) ask Claude / ChatGPT / Perplexity a question with `llms.txt` attached as grounding context. |
| Semantic HTML                    | `<article>` per project, `<details>` for FAQs, anchor IDs on every section.      |
| Cmd-K palette                    | Keyboard-accessible navigation for power users.                                  |

## Stack

- Vanilla **HTML + CSS + JS**, single file
- Deployed via **GitHub Pages** from `/docs`
- **No build step.** No framework. No tracking. No CMS.
- Style language mirrors [jira-digest](https://github.com/darshakbhatt-aiproductlabs/jira-digest) — dark theme, purple→cyan gradient, Inter system stack.

## File layout

```
portfolio/
├── README.md
└── docs/                     ← GitHub Pages source
    ├── .nojekyll             ← serve files as-is (no Jekyll processing)
    ├── index.html            ← the entire site
    ├── llms.txt              ← AI-friendly profile
    ├── resume.json           ← JSON Resume schema
    ├── robots.txt            ← welcomes AI crawlers
    ├── sitemap.xml
    └── assets/
        └── headshot.jpg      ← portrait (drop in to replace monogram fallback)
```

## Editing content

Most edits are 1-file changes in `docs/index.html`. The major content blocks:

- **Hero copy** — search for `<header class="hero">`
- **Stat strip** — search for `class="stat-strip"`
- **Story** — search for `<div class="story`
- **Projects** — search for `<article class="project-card"` (each card has a `data-tags="ai,pm,…"` for filter chips)
- **Impact receipts** — search for `<div class="receipt`
- **Repos** — search for `<a class="repo-card"`
- **FAQs** — search for `<details class="faq">`

If you add or remove projects, **also update `llms.txt` and `resume.json`** to keep the AI-readable layer in sync.

## Customising the headshot

Drop a square photo into `docs/assets/headshot.jpg`. If the file is missing, the hero falls back to a typographic "DB" monogram on the gradient.

## Local preview

```bash
cd docs
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploying

GitHub Pages is configured to serve from the `main` branch's `/docs` folder. Any push to `main` redeploys automatically (usually within 30–60 seconds).

## License

Content (the bio, project descriptions, photo) is © Darshak Bhatt — all rights reserved.
The HTML/CSS/JS scaffolding is MIT-licensed; feel free to fork it as a starting template.
