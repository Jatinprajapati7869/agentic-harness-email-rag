# Recommended Folder Structure

```
cs329z-agentic-harness/
├── PROJECT_PLAN.md          # Full plan (this package)
├── README.md                # How to run (write later)
├── docs/
│   ├── SOURCES.md
│   ├── ARCHITECTURE.md
│   └── DESIGN_NOTES.md      # Your trade-offs (important for interviews)
├── data/
│   ├── raw/                 # Original PDFs / emails
│   └── processed/           # Chunked JSONL with metadata
├── src/
│   ├── retrieval/           # BM25, dense, fusion, rerank
│   ├── pipelines/           # Multi-hop QA
│   ├── agent/               # Custom agent loop, tool registry
│   ├── memory/              # Session memory + compaction
│   └── eval/                # Scoring scripts
├── evals/
│   ├── questions.jsonl      # Your evaluation set
│   └── results/             # Metric outputs
├── .env.example
├── requirements.txt
└── docker-compose.yml       # Optional: Qdrant + app
```

## Week 1 Starting Point

Create these files first:

- `src/retrieval/bm25.py`
- `src/retrieval/hybrid.py`
- `src/retrieval/cli.py` (simple query interface)

Goal: a command that takes a question and prints top-k chunks with scores and source IDs.
