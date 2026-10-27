# Resume portfolio: CS329Z-style agent harness

This repository is an **independent implementation** of Stanford’s public
[Assignment 1 starter](https://github.com/cs329z/assignment1-harness) (MIT
license). Use it on your resume as **your own engineering work on a
published, course-designed spec** — not as enrollment in CS329Z unless you
actually took the course.

## How to describe it honestly

**Good (accurate)**

- “Built a from-scratch agent harness on Stanford CS329Z’s public HW1 spec:
  BM25 email retrieval, multi-hop RAG, custom tool-calling protocol, memory,
  compaction, and human-in-the-loop — validated with the project’s pytest
  suite (deterministic + live thresholds).”
- “Implemented Cardinal-style corporate agent over 200k+ synthetic emails and
  internal docs; no LangChain/LangGraph for the agent loop.”

**Avoid**

- “CS329Z student project” / “Stanford coursework” if you are not enrolled.
- “Fork of Stanford solution” — graders replace stubs; your value is **your**
  `cs329z_hw1/` implementation passing tests.

**Attribution line for README / LinkedIn**

> Based on the public MIT-licensed CS329Z Assignment 1 starter
> ([cs329z/assignment1-harness](https://github.com/cs329z/assignment1-harness)).
> Implementation is my own.

## What recruiters care about (mapped to this repo)

| Skill | Where you prove it |
|--------|-------------------|
| LLM application design | Part 1 pipelines (`priority`, `digest`, `email_qa`) |
| Information retrieval | BM25 from scratch (`tokenizer.py` + your index) |
| Agent systems | Part 2 tool registry, text tool protocol, agent loop |
| Reliability | Deterministic pytest cases (malformed model output, tool errors) |
| Production-minded UX | HITL (`confirm` / `auto`), memory, context budget |
| Evaluation | Live tests + `uv run python -m cs329z_hw1.simulation` |

## Suggested resume bullet (fill in after live tests pass)

Built an agentic harness from Stanford’s public CS329Z HW1 specification:
implemented BM25 retrieval, multi-hop email QA, and a custom tool-calling
agent with sandboxed terminal, session memory, and context compaction;
achieved ≥X% on priority labeling and ≥Y% on email QA on the official live
eval suite.

Replace X/Y with numbers from `uv run pytest -m live -s` once you finish.

## GitHub presentation

1. **Public repo** with a short README demo (commands from the official README).
2. **No secrets** — `.env` stays local; use `.env.example` only.
3. **Optional demo video** (2–3 min): `show` commands + one `chat` session.
4. **Design memo** — the handout asks for design write-ups; put yours in
   `docs/DESIGN.md` (interviewers love this).

## API keys

The starter uses **OpenRouter** (`OPENROUTER_API_KEY` in `.env`). You can use
your own key and budget via `CS329Z_BUDGET_USD`. Cached calls under
`.lm_cache/` keep iteration cheap.

## Staying aligned with upstream

```bash
git remote add upstream https://github.com/cs329z/assignment1-harness.git
git fetch upstream
# Merge course fixes to provided files only when you want updates.
```

Your graded code must live entirely under `cs329z_hw1/` (see official README).
