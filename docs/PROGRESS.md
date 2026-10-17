# AI Learning Progress

Last updated: 2026-10-17

## Current Position

Phase: LLM fundamentals
Next topic: Tokens, context windows, and transformer context processing

## Completed Infrastructure

- Milestone 001: Ubuntu Server baseline
- Milestone 002: Docker Engine
- Milestone 003: NVIDIA Container Toolkit
- Milestone 004: Ollama and first local LLM

## Environment

- Ubuntu Server 26.04.1 LTS
- AMD Ryzen 7 9700X
- NVIDIA RTX 5050, 8 GB VRAM
- 32 GB RAM
- Docker with NVIDIA GPU passthrough
- Ollama 0.40.5
- Local model: qwen3:4b
- Ollama API: http://127.0.0.1:11434

## Completed Experiments

### Python API integration

File: 01-foundations/llm-api/first_request.py

- Successfully called Ollama through HTTP.
- Confirmed local model inference.
- Measured approximately 97 tokens/second.

### Thinking mode

File: 01-foundations/llm-api/thinking_experiment.py

- Compared think=true and think=false.
- Observed reasoning-style text leaking into response
  when think=false.
- Observed separate thinking field when think=true.

### Temperature

File: 01-foundations/llm-api/temperature_experiment.py

- Tested temperature 0 and 1.
- Generation hit the 150-token limit in every run.
- Final answers were truncated by reasoning-style output.
- Temperature comparison was inconclusive.

## Known Issues

Qwen3:4b produces reasoning-style output even with
think=false in the current setup.

This is NOT blocking our learning roadmap.

Do not investigate further unless it becomes necessary
for a later exercise.

## Decisions

- Docker hosts supporting AI services.
- Python applications initially run in a virtual environment.
- Avoid unnecessary frameworks until fundamentals are clear.
- Do not spend excessive time troubleshooting incidental issues.
- Keep the learning roadmap as the primary objective.

## Immediate Next Action

Begin LLM fundamentals:

1. Understand tokens and tokenization.
2. Understand context windows and context limits.
3. Understand how transformers use context.
4. Perform one focused experiment.

Do not repeat completed infrastructure setup or inference
experiments unless verification is necessary.
