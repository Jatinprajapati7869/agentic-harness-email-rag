# Official Sources

This workspace tracks the **official starter layout** (`cs329z_hw1/`, `tests/`,
`pyproject.toml`). Older hybrid-RAG planning notes are in `docs/archive/`.

## Stanford CS329Z (Fall 2026)

- **Main course site:** https://cs329z.stanford.edu/
- **Logistics & coursework (HW1 details):** https://cs329z.stanford.edu/logistics.html
- **Project requirements:** https://cs329z.stanford.edu/project.html
- **Official HW1 starter repository:** https://github.com/cs329z/assignment1-harness
- **Assignment handout PDF:** https://github.com/cs329z/assignment1-harness/blob/main/cs329z_assignment1_harness.pdf

## Key Deadlines (Pacific Time)

- HW1 released: Mon Oct 5, 2026
- HW1 due: Fri Oct 30, 2026
- HW2 released: Mon Oct 26, 2026
- HW2 due: Fri Nov 20, 2026

## What the Assignment Explicitly Requires

From the official handout and logistics page:

**Part 1 — LLM pipelines**
- Single-call email prioritizer
- Daily digest generator
- BM25 retriever built from scratch
- Multi-hop RAG pipeline over the email archive

**Part 2 — Cardinal Agent**
- Tool registry and custom text format for tool calls
- Wrap Part 1 pipelines as tools
- Document retrieval
- Terminal (sandboxed)
- Context budget + compaction
- Memory across sessions
- Human-in-the-loop (approve, deny, redirect)
- Guardrails

Evaluation: deterministic tests, live model tests with thresholds, simulated users, and design write-ups.

## Additional Useful References

- RAGAS documentation: https://docs.ragas.io/
- Qdrant hybrid search: https://qdrant.tech/documentation/guides/hybrid-search/
- rank-bm25: https://github.com/dorianbrown/rank_bm25
- Reciprocal Rank Fusion (original paper concept widely used)
