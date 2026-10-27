# Agentic Harness — Email RAG & Tool-calling Agent

From-scratch **agentic harness** over a corporate email archive and internal
docs: LLM pipelines, **BM25 retrieval**, multi-hop **email QA**, and a custom
**tool-calling agent** with memory, context compaction, human-in-the-loop, and
a sandboxed terminal.

Implementation follows Stanford CS329Z’s public
[Assignment 1 starter](https://github.com/cs329z/assignment1-harness) (MIT).
All solution code lives in `cs329z_hw1/`; behavior is validated with the
official `pytest` suite (deterministic + live thresholds).

| | |
|---|---|
| **Author** | [Jatin Prajapati](https://github.com/Jatinprajapati7869) |
| **Spec** | [cs329z/assignment1-harness](https://github.com/cs329z/assignment1-harness) |
| **License** | MIT (see [LICENSE](LICENSE)) |
| **Status** | In progress — adapters ship as stubs until each milestone lands |

## Features (target)

**Part 1 — LLM pipelines**

- Email priority classification with structured labels and reasons
- Daily digest over a day’s inbox
- BM25 index and search (course tokenizer and scoring rules)
- Multi-hop RAG Q&A over ~260k emails with citation support

**Part 2 — Cardinal agent**

- Tool registry with JSON Schema validation
- Custom **text** tool-call protocol (no framework agent loop)
- Document search, terminal tool, session memory, context compaction
- Human approve / deny / redirect and guardrails
- Simulated-user evaluation harness

No LangChain / LangGraph for the core agent loop — aligned with the assignment.

## Quick start

**Requirements:** Python 3.11+, [uv](https://docs.astral.sh/uv/getting-started/installation/)

```bash
git clone https://github.com/Jatinprajapati7869/agentic-harness-email-rag.git
cd agentic-harness-email-rag

cp .env.example .env
# Add OPENROUTER_API_KEY to .env

uv sync
uv run python data/download.py   # unpack email archive (~58 MB)
uv run pytest                    # deterministic tests (no API spend)
```

**Live evaluation** (costs API credits; use a slice while iterating):

```bash
CS329Z_EVAL_SLICE=5 uv run pytest tests/test_priority.py -m live -s
```

**Inspect pipelines on real data** (after you implement them):

```bash
uv run python -m cs329z_hw1.show bm25 "larchfield audit"
uv run python -m cs329z_hw1.show email_qa "Who leads the Basin Analytics move?"
uv run python -m cs329z_hw1.chat --mode confirm
```

Full command reference, sandbox behavior, and layout:
[`docs/ASSIGNMENT_GUIDE.md`](docs/ASSIGNMENT_GUIDE.md) and
[`cs329z_assignment1_harness.pdf`](cs329z_assignment1_harness.pdf).

## Repository map

```
cs329z_hw1/          # Your implementation (pipelines/, agent/, adapters.py)
tests/               # Official test suite (do not edit)
data/                # Email archive + Cardinal Energy docs
docs/
  BUILD_ORDER.md     # Recommended implementation order
  DESIGN.md          # Design notes for interviews / write-up
  PORTFOLIO.md       # Resume wording and attribution
  ASSIGNMENT_GUIDE.md
```

**Upstream course fixes:** `git remote add upstream https://github.com/cs329z/assignment1-harness.git`

## Development workflow

1. Read the problem in the PDF handout.
2. Implement under `cs329z_hw1/` (e.g. `pipelines/priority.py`).
3. Wire `cs329z_hw1/adapters.py` to your code.
4. Run deterministic tests, then live tests for that problem.

See [`docs/BUILD_ORDER.md`](docs/BUILD_ORDER.md).

## Attribution

Starter code, tests, data, and assignment design:
[Stanford CS329Z — assignment1-harness](https://github.com/cs329z/assignment1-harness)
(MIT). This repository is an independent implementation; solution logic in
`cs329z_hw1/` is authored for this project.

Course site: [cs329z.stanford.edu](https://cs329z.stanford.edu/)
