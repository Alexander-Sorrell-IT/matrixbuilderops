# matrixbuilderops

AI tooling ops layer — two tools that give AI agents real awareness instead of dumb text dumps.

---

## 🌐 SiteMap — Website Awareness for AI

> *"Don't read a website. Know it."*

SiteMap crawls a URL and builds a structured **Site Awareness Object** — a map of every page, form, button, link, and API endpoint. Instead of flooding the AI with raw HTML, it hands the AI a navigable, queryable graph it can **reason over and act on**.

**What it produces:**
- Page inventory with summaries
- Interactive element registry (forms, buttons, inputs)
- Action toolkit (callable tools per site interaction)
- API endpoint hints
- Auth requirement detection

📁 [`sitemap/`](./sitemap/)

---

## 📁 FileLens — Intelligent File Reading for AI

> *"Don't dump a file. Understand it."*

FileLens replaces naive `cat file` with a 4-mode intelligent reader built for AI agents:

| Mode | What it does |
|---|---|
| `outline` | Returns file structure — classes, functions, sections, line numbers |
| `search` | Semantic/keyword search with context lines |
| `chunk` | Precise line-range extraction |
| `summarize` | Plain-English explanation of what the file does |

AI reads the **outline** first, then surgically fetches only what it needs.

📁 [`filelens/`](./filelens/)

---

## Design Philosophy

Both tools share one principle:

> **Build a map → navigate by query → fetch only what's needed**

| | SiteMap | FileLens |
|---|---|---|
| **Map** | Site graph JSON | File outline |
| **Navigate** | Page/action lookup | Line range / search |
| **Fetch** | Clean page markdown | Targeted chunk |
| **Act** | Form/API call | Edit specific section |

---

## Repo Structure

```
matrixbuilderops/
├── sitemap/          # Website awareness tool
│   ├── src/
│   └── tests/
├── filelens/         # Intelligent file reader
│   ├── src/
│   └── tests/
└── docs/             # Design docs and specs
```

---

## Status

🚧 Active development
