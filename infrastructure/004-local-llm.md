# Milestone 004 — First Local LLM

## Objective

Run a language model locally using Docker, Ollama,
and NVIDIA GPU acceleration.

## Environment

- OS: Ubuntu Server 26.04.1 LTS
- GPU: NVIDIA RTX 5050 (8 GB)
- NVIDIA driver: 595.99.02
- Docker Engine: 29.9.1
- Ollama: 0.40.5
- Model: qwen3:4b

## Architecture

Ollama runs inside Docker with GPU access enabled.

The API is bound to 127.0.0.1:11434 to avoid
unnecessary network exposure.

Models are stored in a persistent Docker volume.

## Verification

API version:

    curl http://127.0.0.1:11434/api/version

Model execution:

    sudo docker exec -it ollama ollama run qwen3:4b

GPU verification:

    sudo docker exec ollama ollama ps

Result: 100% GPU execution confirmed.

## Decisions

- Use Docker for supporting AI services.
- Use Python directly on Ubuntu for initial development.
- Keep the Ollama API bound to localhost.
- Start with a 4B model suitable for 8 GB VRAM.

## Lessons Learned

- Ollama provides a local LLM inference server.
- Docker can access NVIDIA GPUs through Container Toolkit.
- Model weights persist in a Docker volume.
- GPU execution can be verified using ollama ps.
- The Ollama API can be accessed over HTTP.

## Next Milestone

Build a Python client and explore LLM inference parameters.
