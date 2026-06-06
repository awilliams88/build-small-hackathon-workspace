# Roast My Repo Implementation Plan

## Summary

Roast My Repo reviews a small GitHub repo or uploaded code bundle and produces a
practical improvement plan. The tone can be playful, but the output must be
useful and actionable.

## Target awards

- JetBrains Milo 2 sponsor alignment.
- OpenAI/Codex through public repo history and coding-agent framing.
- Best Agent through inspect -> plan -> recommend -> verify workflow.
- Community Choice because developers can share repo report cards.

## Architecture

```text
Repo URL or zip
  -> file inventory
  -> chunked code summary
  -> small coding model review
  -> issue list + improvement plan
  -> shareable report card
```

## Model plan

- JetBrains Milo 2 12B for code reasoning if practical.
- Optional lightweight embedding or retrieval path for code chunking.
- Modal sandbox may be used for safe code inspection or agent runs.

## Implementation phases

1. Upload/URL input and local file inventory.
2. Add static heuristics and report layout.
3. Integrate coding-model review.
4. Add shareable report card.
5. Finalize README and demo.

