# SiteMap

Website awareness layer for AI agents.

Crawls a URL and returns a structured Site Awareness Object — not raw HTML, but a navigable map the AI can reason over and act on.

## Core Output: Site Awareness Object

```json
{
  "url": "https://example.com",
  "pages": [
    { "path": "/", "title": "Home", "summary": "Landing page with CTA" }
  ],
  "forms": [
    { "page": "/signup", "fields": ["email", "password"], "action": "POST /api/register" }
  ],
  "actions": [
    { "label": "Buy Now", "type": "button", "leads_to": "/checkout" },
    { "label": "Search", "type": "input", "endpoint": "/api/search?q=" }
  ],
  "auth": { "required": true, "method": "cookie/JWT" },
  "api_hints": ["/api/search", "/api/products"]
}
```

## Status
🚧 Scaffolded — implementation coming
