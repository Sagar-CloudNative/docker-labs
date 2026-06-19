# Lab 02 — Docker Installation & Setup on Rocky Linux & Ubuntu

[![Docker](https://img.shields.io/badge/Docker-Labs-blue)](https://github.com/Sagar-CloudNative/docker-labs)
[![License](https://img.shields.io/badge/License-MIT-green)](../LICENSE)
[![YouTube](https://img.shields.io/badge/YouTube-Subscribe-red?logo=youtube)](https://www.youtube.com/@TechOpsTutorials)

> **Part of the [Docker Labs](https://github.com/Sagar-CloudNative/docker-labs) series**

---

## 🎯 What You'll Learn

- System requirements for Docker
- Three Docker installation methods and when to use each
- How Docker architecture works — CLI, daemon, images, containers
- Full Docker installation on Rocky Linux 9
- Full Docker installation on Ubuntu 25.10
- Docker group permissions — run Docker without sudo
- Common installation issues and how to fix them

---

## 🧠 Concept Overview

### Docker Installation Methods

| Method | How | Best For |
|--------|-----|---------|
| **Official Docker Repository** | `dnf` / `apt` with Docker repo | Most environments — recommended |
| **OS Package Repository** | `dnf` / `apt` directly | Quick setup, may not be latest version |
| **Offline Installation** | Manual package download | Servers without internet access |

### Docker Architecture — Basic Flow

```
User types command
      ↓
Docker CLI
      ↓
Docker Daemon (dockerd)
      ↓
Checks if image exists locally
      ↓ (if not)
Downloads from Docker Hub
      ↓
Creates and starts container
```

### What is the Docker Daemon?

The Docker daemon (`dockerd`) is the background service that does all the actual work — building images, running containers, managing networks and volumes. Without it, Docker commands have nothing to execute.

```bash
# Check if daemon is running
sudo systemctl status docker
```

---

## 🗂️ Files in This Lab

| File | Description |
|------|-------------|
| `rocky-linux-commands.md` | Full Docker installation steps for Rocky Linux 9 |
| `ubuntu-commands.md` | Full Docker installation steps for Ubuntu 25.10 |
| `troubleshooting.md` | Common issues and fixes |

---

## ⚙️ System Requirements

- 64-bit Linux OS (Rocky Linux 9 or Ubuntu 25.10)
- Minimum 2 CPU cores, 4 GB RAM
- Sufficient disk space for images and containers
- Active internet connection
- `sudo` or root access

---

## 🚀 Demo Overview

| Step | Rocky Linux | Ubuntu |
|------|-------------|--------|
| Verify OS | `cat /etc/os-release` | `cat /etc/os-release` |
| Add repo | `dnf config-manager` | GPG key + apt source |
| Install | `dnf install docker-ce ...` | `apt install docker-ce ...` |
| Start service | `systemctl enable --now docker` | `systemctl enable --now docker` |
| Permissions | `usermod -aG docker $USER` | `usermod -aG docker $USER` |
| Verify | `docker run hello-world` | `docker run hello-world` |

---

## ▶️ Watch the Video

👉 [**Docker Installation & Setup — YouTube**](https://www.youtube.com/watch?v=yR8cP35Nw_U)

---

## ⬅️ Previous Lab

[Lab 01 — Containers & Orchestration Explained](../01-containers-and-orchestration)

## ➡️ Next Lab

[Lab 03 — Docker Images & Containers Explained](../03-docker-images-containers)
