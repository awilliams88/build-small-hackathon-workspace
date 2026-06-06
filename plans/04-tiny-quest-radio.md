# Tiny Quest Radio Implementation Plan

## Summary

Tiny Quest Radio is a small interactive audio story game. The user speaks or
types choices, the app advances a tiny branching story, and characters respond
with generated voice.

## Target awards

- Thousand Token Wood.
- Cohere Transcribe or NVIDIA speech path.
- OpenBMB TTS/Omni path if practical.
- Best Demo due to voice-driven interaction.
- Best Agent if the story planner tracks state and choices.

## Architecture

```text
Voice/text choice
  -> ASR if needed
  -> story state tracker
  -> small-model next scene generator
  -> TTS response
  -> Gradio audio/text playback
```

## Model plan

- Cohere Transcribe or eligible ASR model.
- Small text model for story state and next-scene generation.
- MiniCPM TTS or another eligible small TTS path.

## Implementation phases

1. Text-only branching story MVP.
2. Add ASR input.
3. Add TTS output.
4. Add state summary and replayable examples.
5. Polish for demo and social post.

