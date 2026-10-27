# Week 1: Hybrid Retrieval That Actually Works

## Goal
A working hybrid search CLI that returns ranked chunks with source IDs and scores.

## Tasks

1. **Data loading**
   - Load your corpus into chunks with metadata (`source_id`, `text`, `title`, etc.)
   - Save as JSONL

2. **BM25**
   - Implement or use `rank-bm25`
   - Tokenize simply (lowercase + split, or use a proper tokenizer)

3. **Dense retrieval**
   - Embed chunks with `text-embedding-3-large`
   - Store in Qdrant (local)

4. **Fusion**
   - Implement Reciprocal Rank Fusion (RRF)
   - Formula: score = sum(1 / (k + rank)) with k=60

5. **CLI**
   - `python -m src.retrieval.cli "your question"`
   - Print top 5–10 results with scores and source IDs

## Success Criteria
- You can run 10 manual queries and see relevant chunks
- Both BM25 and dense contribute (try disabling one to compare)
- Results include clear source identifiers for later citations

## Next
Once this works, move to Week 2 (multi-hop RAG pipeline that uses this retrieval).
