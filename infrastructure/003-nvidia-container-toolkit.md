# Milestone 003 — NVIDIA Container Toolkit

## Objective

Enable GPU acceleration inside Docker containers.

## Environment

- GPU: NVIDIA GeForce RTX 5050 (8 GB)
- Host NVIDIA driver: 595.99.02
- Docker Engine: 29.9.1

## Installation

Installed NVIDIA Container Toolkit from NVIDIA's official
APT repository.

Configured the Docker runtime using:

    sudo nvidia-ctk runtime configure --runtime=docker
    sudo systemctl restart docker

## Verification

GPU access tested using:

    sudo docker run --rm --gpus all \
      nvidia/cuda:13.0.0-base-ubuntu24.04 nvidia-smi

Result: RTX 5050 accessible inside Docker.

## Repository Security

- Added .gitignore entries for secrets and generated files.
- Checked tracked filenames for common credential files.
- Kept server-specific credentials outside the repository.

## Lessons Learned

- The host NVIDIA driver provides GPU functionality.
- NVIDIA Container Toolkit enables GPU access in containers.
- Docker GPU access can be requested with --gpus all.
- The CUDA toolkit does not need to be installed on the host
  just to run GPU-enabled containers.

## Next Milestone

Run a local LLM using Ollama in Docker.
