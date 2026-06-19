# Docker Installation — Rocky Linux 9

---

## Step 1 — Verify Operating System

```bash
cat /etc/os-release
```

---

## Step 2 — Verify Docker Is Not Already Installed

```bash
which docker
```

> No output means Docker is not installed — clean system confirmed.

---

## Step 3 — Install Required Package

```bash
sudo dnf install -y dnf-plugins-core
```

---

## Step 4 — Add Docker Repository

```bash
sudo dnf config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
```

---

## Step 5 — Verify Repository

```bash
sudo dnf repolist | grep docker
```

> Docker repository should appear in the output.

---

## Step 6 — Install Docker Engine

```bash
sudo dnf install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

---

## Step 7 — Start and Enable Docker Service

```bash
sudo systemctl enable --now docker
```

---

## Step 8 — Verify Docker Service

```bash
sudo systemctl status docker
```

> Look for `active (running)` in the output.

---

## Step 9 — Verify Automatic Startup

```bash
systemctl is-enabled docker
```

> Expected output: `enabled`

---

## Step 10 — Verify Docker Installation

```bash
docker --version

docker version

docker info

# Filtered view
docker info | egrep -i 'server version|storage driver|docker root dir'
```

---

## Step 11 — Configure Docker Group Permissions

### Test without permissions first
```bash
docker ps
```

> Expected error: `permission denied while trying to connect to the Docker daemon socket`

### Test with sudo (works but not convenient)
```bash
sudo docker ps
```

### Add user to Docker group
```bash
sudo usermod -aG docker $USER
```

> Log out and log back in for the group change to take effect.

### Verify Docker works without sudo
```bash
docker ps
```

---

## Step 12 — Run First Container

```bash
docker run hello-world
```

> If you see `Hello from Docker!` — installation is successful.

**What happens behind the scenes:**
1. Docker checks if `hello-world` image exists locally
2. If not, downloads it from Docker Hub
3. Creates a container from the image
4. Starts the container, prints the message, and exits

---

## Step 13 — Verify Image and Container

```bash
# Check downloaded image
docker images

# Check container (Exited status is expected for hello-world)
docker ps -a
```
