# FileLens

Intelligent file reading for AI agents.

Replaces naive `cat file` with a 4-mode reader that gives AI structure before content.

## Modes

| Mode | Description |
|---|---|
| `outline` | Returns file structure: classes, functions, headings, line numbers |
| `search` | Keyword/semantic search with surrounding context lines |
| `chunk` | Precise line-range extraction |
| `summarize` | Plain-English summary of what the file does |

## Example Outline Output

```
file.py  (843 lines, Python)
├── imports        lines 1–15
├── class UserAuth lines 18–120
│   ├── __init__   line 19
│   ├── login()    line 34
│   └── logout()   line 89
├── class Database lines 123–400
└── main()         lines 403–843
```

AI reads the outline, then fetches only the chunks it needs.

## Status
🚧 Scaffolded — implementation coming
