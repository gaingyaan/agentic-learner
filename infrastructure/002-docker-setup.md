# Milestone 002 — Docker Engine Setup

## Objective

Install Docker Engine on Ubuntu Server to support reproducible
development environments, application builds, and AI workloads.

## Installed Components

- Docker Engine: 29.9.1
- Docker Compose: v5.6.0
- Container runtime: containerd
- Storage driver: overlayfs

## Installation Approach

Docker Engine was installed using Docker's official Ubuntu APT
repository, rather than Docker Desktop.

## Verification

Commands:

    sudo systemctl is-active docker
    sudo docker info --format 'Storage driver: {{.Driver}}'
    sudo docker run --rm hello-world
    docker --version
    docker compose version

Results:

- Docker service: active
- Storage driver: overlayfs
- hello-world container: successful
- Docker and Compose versions verified

## Decisions

- Use Docker Engine directly on Ubuntu Server.
- Keep Docker data on the root filesystem initially.
- Use Docker Compose for multi-container development environments.
- Use sudo for Docker commands initially.
- Configure NVIDIA GPU access separately.

## Lessons Learned

- Docker Engine runs and manages containers.
- Docker Compose defines and manages multi-container applications.
- The overlayfs storage driver manages container filesystem layers.
- Docker containers share the host Linux kernel.
- Docker access requires careful permission management.

## Next Milestone

Configure NVIDIA GPU access inside Docker containers.
