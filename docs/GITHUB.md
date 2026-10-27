# GitHub setup (one-time)

The repository is configured locally with:

- `origin` → `https://github.com/Jatinprajapati7869/agentic-harness-email-rag.git`
- `upstream` → `https://github.com/cs329z/assignment1-harness.git`

## Push your first commit

From the project root, after [logging into GitHub CLI](https://cli.github.com/):

```bash
gh auth login
git push -u origin main
```

Or use SSH:

```bash
git remote set-url origin git@github.com:Jatinprajapati7869/agentic-harness-email-rag.git
git push -u origin main
```

## Recommended GitHub settings

On the repo **Settings → General**:

| Field | Suggested value |
|--------|------------------|
| **Description** | From-scratch agent harness: BM25, multi-hop email RAG, custom tool-calling agent (CS329Z HW1 spec). |
| **Website** | https://cs329z.stanford.edu/ (spec reference) |

**Topics:** `llm-agents`, `rag`, `bm25`, `information-retrieval`, `python`, `retrieval-augmented-generation`

**About visibility:** Public

Pin the repository on your profile once Part 1 tests start passing.

## CI

GitHub Actions runs on push/PR (`.github/workflows/ci.yml`): `uv sync`, unpack
data, import smoke test. Enable **Actions** in the repo if disabled.

Uncomment the `pytest` step in CI when deterministic tests pass.
