# Milestone 001 — Ubuntu Server Baseline

## Objective

Prepare the Ryzen Server for AI development, local LLM inference,
Docker workloads, and general software development.

## Hardware

- CPU: AMD Ryzen 7 9700X (8 cores / 16 threads)
- GPU: NVIDIA GeForce RTX 5050 (8 GB VRAM)
- RAM: 32 GB DDR5
- Storage: 1 TB NVMe SSD

## Operating System

- Ubuntu Server 26.04.1 LTS
- Python 3.14.4
- Git 2.53.0
- Remote access: SSH
- Development IDE: Google Antigravity via Remote SSH

## Storage Configuration

- Storage management: LVM
- Filesystem: ext4
- Root logical volume: 600 GiB
- Remaining unallocated LVM capacity: ~328 GiB

### Decision

Use a single large root filesystem initially to accommodate
unpredictable development workloads.

Retain unused LVM capacity for future expansion or dedicated volumes.

### Configuration

```bash
sudo lvextend -L 600G -r /dev/ubuntu-vg/ubuntu-lv


Verification
df -hT /
sudo vgs
sudo lvs
```


### NVIDIA GPU Setup
- Driver: 595.99.02
- Driver package: nvidia-driver-595-open
- CUDA driver compatibility: 13.2
- GPU successfully detected using nvidia-smi

#### Installation

```bash
sudo apt install -y nvidia-driver-595-open
sudo reboot
```


#### Verification
```bash
nvidia-smi
```

### Development Access
- SSH access from Windows workstation
- GitHub authentication through SSH keys
- Git repository cloned on Ryzen Server
- Remote development using Google Antigravity

### Lessons Learned
1. LVM separates physical storage capacity from logical volumes.
2. ext4 filesystems can be expanded online.
3. NVIDIA drivers are required for GPU-accelerated inference.
4. The CUDA version reported by nvidia-smi represents driver
   compatibility, not necessarily an installed CUDA toolkit.

## Next Milestone
Install Docker Engine and Docker Compose plugin.