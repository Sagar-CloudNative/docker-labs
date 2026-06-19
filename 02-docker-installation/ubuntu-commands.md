# Docker Installation — Ubuntu 25.10

---

## Step 1 — Verify Operating System

```bash
cat /etc/os-release
```

> Confirm Ubuntu 25.10

---

## Step 2 — Verify Docker Is Not Already Installed

```bash
which docker
```

> No output means Docker is not installed.

---

## Step 3 — Update Package Information

```bash
sudo apt update
```

---

## Step 4 — Install Required Packages

```bash
sudo apt install -y ca-certificates curl gnupg
```

---

## Step 5 — Create Docker Key Directory

```bash
sudo install -m 0755 -d /etc/apt/keyrings
```

---

## Step 6 — Add Docker GPG Key

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

---

## Step 7 — Add Docker Repository

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

---

## Step 8 — Verify Repository

```bash
sudo apt update
```

> Docker repository information should be downloaded successfully.

---

## Step 9 — Install Docker Engine

```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

---

## Step 10 — Start and Enable Docker

```bash
sudo systemctl enable --now docker
```

---

## Step 11 — Verify Service

```bash
sudo systemctl status docker
```

> Look for `active (running)` in the output.

---

## Step 12 — Verify Installation

```bash
docker --version

docker version

docker info
```

---

## Step 13 — Configure Docker Group Permissions

```bash
sudo usermod -aG docker $USER
```

> Log out and log back in for the change to take effect.

---

## Step 14 — Run Hello World Container

```bash
docker run hello-world
```

> `Hello from Docker!` message confirms successful installation.

---

## Step 15 — Verify Image and Container

```bash
docker images

docker ps -a
```
