---
title: "My voice coding stack: talk to Claude Code, hear it talk back"
description: "Local speech to text, an LLM cleanup pass, and on-device text to speech, with every gotcha I hit."
date: 2026-09-25
---

I rebuilt my dev setup so I can talk to Claude Code and it talks back.

## The stack

- **Speech to text:** Handy with a Parakeet model, running locally.
- **Cleanup:** a small LLM pass that fixes identifiers and punctuation.
- **Text to speech:** VibeVoice on Apple Silicon.

## Gotchas

- The OpenAI compatible endpoint in Ollama forces `temperature` to 1.0 when the client does not send it. Setting `top_k 1` in a Modelfile makes output deterministic anyway.
- Number examples in a cleanup prompt can make a small model invent amounts that were never spoken.
- Loading a TTS model in float32 on a Mac doubled its memory. Switching to bfloat16 took it from 12 GB to under 7 GB.

This is placeholder content. Replace it with the real post.
