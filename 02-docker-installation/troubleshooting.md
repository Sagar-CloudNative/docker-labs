# Troubleshooting — Docker Installation

---

## Issue 1 — Cannot Connect to Docker Daemon

**Error:**
```
Cannot connect to the Docker daemon at unix:///var/run/docker.sock
```

**Fix:**
```bash
sudo systemctl start docker
```

---

## Issue 2 — Permission Denied Error

**Error:**
```
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock
```

**Fix:**
```bash
sudo usermod -aG docker $USER
```

> Log out and log back in after running this command.

---

## Issue 3 — Docker Command Not Found

**Verification:**
```bash
which docker
```

> No output means Docker installation did not complete successfully. Re-run the installation steps.

---

## Issue 4 — Repository or Package Errors

**Steps to verify:**
1. Check internet connectivity
2. Confirm the Docker repository was added correctly

**Rocky Linux:**
```bash
sudo dnf repolist | grep docker
```

**Ubuntu:**
```bash
cat /etc/apt/sources.list.d/docker.list
```
