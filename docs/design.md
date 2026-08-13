# Design Notes

## Core Philosophy

> **Build a map → navigate by query → fetch only what's needed**

Both SiteMap and FileLens exist to solve the same root problem: AI agents are handed raw data (HTML dumps, full file contents) when what they need is *structure first, content on demand*.

## SiteMap Design

### Pipeline
1. Crawl all discoverable routes
2. Parse DOM for interactive elements (forms, buttons, links, inputs)
3. Extract main content per page (via Readability/Trafilatura)
4. Build site graph with relationships
5. Output: Site Awareness Object (JSON)
6. Expose as callable tools the AI can invoke

### Key Insight
Every interactive element becomes a **tool** the AI can call:
- `search_site(query)` → `GET /api/search?q={query}`
- `submit_form(email, password)` → `POST /signup`
- `navigate(path)` → load page content

## FileLens Design

### 4-Mode Interface
- `outline(path)` — structure scan, cheap, always first
- `search(path, query, context=5)` — targeted extraction
- `chunk(path, start, end)` — precise range
- `summarize(path)` — LLM-generated description

### Decision Flow
```
outline → small file? → chunk whole file
        → large file? → search / chunk targeted range / summarize
```

### Key Insight
AI should read a file the way a senior engineer would: scan the structure, identify the relevant section, read only that section.
