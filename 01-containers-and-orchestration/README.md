# Lab 01 — Containers & Orchestration Explained | Docker vs VMs

[![Docker](https://img.shields.io/badge/Docker-Labs-blue)](https://github.com/TechOpsTutorials/docker-labs)
[![License](https://img.shields.io/badge/License-MIT-green)](../LICENSE)
[![YouTube](https://img.shields.io/badge/YouTube-Subscribe-red?logo=youtube)](https://www.youtube.com/@TechOpsTutorials)

> **Part of the [Docker Labs](https://github.com/TechOpsTutorials/docker-labs) series**

---

## 🎯 What You'll Learn

- What containers are and why they exist
- The difference between containers and virtual machines
- How Docker works under the hood (shared kernel, namespaces, cgroups)
- Container vs Image — what's the difference
- What container orchestration is and why it's needed
- Popular orchestration tools — Docker Swarm, Kubernetes, Apache Mesos
- Why Kubernetes is the industry standard

---

## 🧠 Concept Overview

### The Problem Containers Solve

In a traditional setup, every developer installs dependencies manually on their own system. This leads to version conflicts, configuration differences, and the classic **"it works on my machine"** problem.

Containers solve this by packaging the application code, libraries, dependencies, and runtime into one portable unit that runs the same everywhere.

---

### Containers vs Virtual Machines

| | Containers | Virtual Machines |
|---|---|---|
| **OS** | Shares host OS kernel | Full OS per VM |
| **Size** | Megabytes | Gigabytes |
| **Startup** | Seconds | Minutes |
| **Resource Usage** | Low | High |
| **Isolation** | Process-level | Hardware-level |
| **Best For** | Microservices, CI/CD | Legacy apps, strong isolation |

---

### Container vs Image

| | Image | Container |
|---|---|---|
| **What it is** | Blueprint | Running instance |
| **State** | Read-only | Read-write |
| **Changes** | Immutable | Stateful |
| **Analogy** | ISO file | OS running from that ISO |

---

### How Docker Works

- Docker Engine runs on the host OS
- Containers share the **Linux kernel** — no full OS inside each container
- Uses **namespace isolation** — containers can't see each other's processes
- Uses **cgroups** — controls CPU and memory per container
- Result: lightweight, fast, and secure

> **Can Docker run Windows containers on Linux?**
> No — containers share the host kernel. Windows containers need a Windows kernel. Linux containers are portable across Ubuntu, Fedora, CentOS, Rocky Linux, and more.

---

### Traditional vs Containerized Setup

| ❌ Traditional | ✅ Containerized |
|---|---|
| Everything installed on host OS | Each app runs in its own container |
| Version conflicts | Fully isolated environments |
| Manual installation | Single command deployment |
| Non-replicable environments | Identical across dev, staging, prod |

---

### What is Container Orchestration?

When running tens or hundreds of containers across multiple machines, managing them manually becomes impossible. **Orchestration** automates:

- Container lifecycle — start, stop, restart, reschedule
- Self-healing — crashed containers restart automatically
- Load balancing — traffic distributed across healthy containers
- Auto-scaling — more containers when demand increases, fewer when it drops
- Service discovery — services find each other automatically

---

### Orchestration Tools Comparison

| Tool | Best For | Complexity |
|------|---------|------------|
| **Docker Swarm** | Small projects, MVPs | Low |
| **Kubernetes** | Production, cloud-native apps | Medium-High |
| **Apache Mesos** | Large enterprises, hybrid workloads | High |

> **Recommendation:** Learn Kubernetes — it is the industry standard backed by CNCF and all major cloud providers (AWS, GCP, Azure).

---

## 📺 Watch the Video

👉 [**Containers & Orchestration Explained — YouTube**](https://www.youtube.com/@TechOpsTutorials)

---

## ➡️ Next Lab

[Lab 02 — Docker Installation & Setup](../02-docker-installation)
