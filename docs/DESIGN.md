# Design notes (for interviews)

Fill this in as you build. The official assignment grades design write-ups;
this file is your portfolio version of that.

## Problem: priority classification

- Prompt strategy:
- Why this beats a single zero-shot label:
- Failure mode you fixed:

## Problem: BM25

- IDF / scoring choices (handout: Lucene IDF, k1=1.5, b=0.75):
- Index structure for fast term lookup:
- Trade-off vs using `rank-bm25`:

## Problem: email QA (multi-hop)

- Hop strategy and query reformulation:
- When you return `answer: null`:
- Citation / support selection:

## Agent loop

- Tool protocol format (how the model emits calls):
- Context budget and compaction policy:
- Memory: what you store and when you read it:
- Human-in-the-loop: confirm vs auto:

## Evaluation

- Live test scores (date, model, slice vs full):
- Simulation personas: one success story, one failure, fix:
