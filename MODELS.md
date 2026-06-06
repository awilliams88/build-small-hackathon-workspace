# Model Plan

This file tracks candidate models for each hackathon project. Final project
READMEs must lock exact model IDs, parameter counts, license notes, and runtime
choices before submission.

## Portfolio model priorities

| Project | Primary model path | Sponsor surface | Badge surface |
| --- | --- | --- | --- |
| NeighborDocs | `nvidia/NVIDIA-Nemotron-Parse-v1.1` plus a small text reasoner | NVIDIA, Backyard AI | Tiny Titan if reasoner is <=4B |
| Pocket Tutor From Photos | `openbmb/MiniCPM-V-4.6` | OpenBMB, Backyard AI | Off the Grid if hosted locally |
| Flux Costume Booth | Flux.1 image generation/editing path | Black Forest Labs, Thousand Token Wood | Off-Brand, Well-Tuned if LoRA is trained |
| Tiny Quest Radio | Cohere Transcribe plus small TTS or MiniCPM voice path | Cohere, OpenBMB | Best Demo, Best Agent |
| Roast My Repo | `JetBrains/Milo-2-12B` | JetBrains, OpenAI/Codex | Best Agent |
| Gradio Workflow Remix Lab | Small multimodal models wired through Gradio Workflow | Gradio/HF, Off-Brand | Bonus Quest Champion |

## Candidate model inventory

| Model | Approx size | Best use | Notes |
| --- | ---: | --- | --- |
| `nvidia/NVIDIA-Nemotron-Parse-v1.1` | <1B class | PDF/PPT text and layout extraction | Strong first choice for NeighborDocs document parsing. |
| `openbmb/MiniCPM-V-4.6` | 1B class | Image understanding, OCR, homework/photo tutoring | Strong for Pocket Tutor and document/image workflows. |
| MiniCPM 1B text model | 1B class | Tiny local text assistant | Good Tiny Titan candidate if exact repo is locked. |
| MiniCPM 4.1 8B text model | 8B class | Stronger reasoning | Use when 1B quality is not enough. |
| MiniCPM Omni / voice models | varies under 32B | Conversational audio and multimodal apps | Candidate for Tiny Quest Radio. |
| Flux.1 4B | 4B class | Text-to-image and image editing | Strong BFL project fit. |
| Flux.1 9B | 9B class | Higher-quality image generation/editing | Use if runtime budget allows. |
| `JetBrains/Milo-2-12B` | 12B | Code review and repo tooling | Strong Roast My Repo fit. |
| Cohere Transcribe | 2B | Low-latency ASR | Strong for audio apps and accessibility. |
| Cohere tiny multilingual LLM family | 3.3B | Summarization, translation, cross-lingual reasoning | Strong for multilingual document/tutor flows. |

## NeighborDocs first choice

Start with a rule-based interpreter plus `pypdf` extraction while the UI and
workflow become polished. Then add:

1. `nvidia/NVIDIA-Nemotron-Parse-v1.1` for document extraction.
2. A <=4B text reasoner for summary, obligations, deadlines, and next actions.
3. Optional MiniCPM-V path for image/scanned-document understanding.

This keeps the first project useful quickly while preserving a clear NVIDIA and
Tiny Titan upgrade path.
