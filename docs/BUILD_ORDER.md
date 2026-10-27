# Build order (official HW1)

Read `cs329z_assignment1_harness.pdf` first. Implement in this order so each
piece unlocks the next. Wire each problem through `cs329z_hw1/adapters.py` as
described in the root `README.md`.

## Part 1 — LLM pipelines

| Step | Adapter | Your code (typical) | Verify |
|------|---------|---------------------|--------|
| 1 | `run_priority` | `pipelines/priority.py` | `uv run pytest tests/test_priority.py` |
| 2 | `run_daily_digest` | `pipelines/digest.py` | `uv run pytest tests/test_daily_digest.py` |
| 3 | `run_bm25_build`, `run_bm25_search` | `pipelines/bm25.py` | `uv run pytest tests/test_bm25.py` |
| 4 | `run_email_qa` | `pipelines/email_qa.py` | `uv run pytest tests/test_email_qa.py` |

**Inspect outputs**

```bash
uv run python -m cs329z_hw1.show priority em-12167
uv run python -m cs329z_hw1.show bm25 "larchfield audit"
uv run python -m cs329z_hw1.show email_qa "Who leads the Basin Analytics move?"
```

## Part 2 — Cardinal agent

| Step | Adapter(s) | Your code (typical) | Verify |
|------|------------|---------------------|--------|
| 5 | `run_tool_registry` | `agent/registry.py` | `tests/test_tool_registry.py` |
| 6 | `run_render_tools`, `run_parse_response` | `agent/protocol.py` | `tests/test_tool_protocol.py` |
| 7 | Tool implementations | `agent/tools/*.py` | per-tool tests |
| 8 | `run_agent_turn` / session | `agent/loop.py` | agent + session tests |
| 9 | Memory, compaction, HITL | `agent/memory.py`, etc. | remaining tests |

**End-to-end**

```bash
uv run python -m cs329z_hw1.chat --mode confirm
uv run python -m cs329z_hw1.simulation --slice 3
```

## Daily workflow

1. Deterministic tests for the problem you are on (fast, free).
2. `CS329Z_EVAL_SLICE=5` for cheap live checks.
3. Full live run when a milestone is done.
4. Note failures in `docs/DESIGN.md` (what broke, what you changed).
