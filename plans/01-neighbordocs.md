# NeighborDocs Implementation Plan

## Summary

NeighborDocs helps users understand everyday paperwork. The first MVP extracts
text from PDFs and text files, then evolves into a small-model document
interpreter with summary, obligations, dates, and next actions.

## Target awards

- Backyard AI.
- NVIDIA document intelligence path.
- Tiny Titan if the reasoning model is small enough.
- Best Demo through a clear before/after document flow.
- OpenAI/Codex through public GitHub history.

## Architecture

```text
Document upload + user context
  -> file type detection
  -> PDF text extraction / OCR path
  -> document parser
  -> small-model summarizer
  -> checklist and risk/date extraction
  -> Gradio result view
```

## Implementation phases

1. MVP scaffold: Gradio UI, PDF/TXT extraction, placeholder summary, clean docs.
2. Add OCR/image path for scanned documents.
3. Add sponsor-model reasoning path for summary and checklist generation.
4. Add example documents and polished demo states.
5. Record video, add social link, and finalize README model table.

## Model plan

- Current: `pypdf` extraction only.
- Planned: NVIDIA Nemotron Parse or equivalent layout-aware parser.
- Planned: small reasoning model under 32B total parameters for summary and
  action extraction.
- Optional: multilingual small model for translation or local-language summary.

## Acceptance criteria

- `./run.sh verify` passes lint, format-check, and Python compile.
- Space boots without build/runtime errors.
- Uploading a PDF returns extracted text and a structured summary.
- README includes GitHub link, Space link, model list, architecture, local setup,
  demo video link, and social post link.
