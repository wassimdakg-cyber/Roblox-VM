# Roblox VM (GitHub Actions + KasmVNC)

Runs a free Roblox virtual machine in the cloud using **GitHub Actions** (no credit card)
and exposes the desktop through **KasmVNC** over a `bore.pub` tunnel.

## How to run

1. Create a new GitHub repo and push this folder to it (the `.github/workflows` file
   is what GitHub reads).
2. Open the repo -> **Actions** -> **Roblox VM (KasmVNC)** -> **Run workflow**.
3. Wait ~3 minutes for the runner to boot and install everything.
4. In the run, open the **"Expose KasmVNC through a tunnel"** step and copy the
   `VNC TUNNEL URL:` value into your browser. Password is disabled.

## Limits (important)

- **6 hours max per session** — GitHub Actions terminates free runners at that point.
- **No GPU** — Roblox's client needs hardware rendering. Wine under Xvfb will start
  the process and connect to the launcher, but gameplay rendering will be missing or
  very poor. This is a hard limit of free Linux cloud runners.
- Roblox's launcher may prompt for login / may refuse to run the game without a GPU.

## Files

- `.github/workflows/roblox-vm.yml` — the workflow that runs the whole thing.
- `help.txt` — where to find the tunnel URL.

For anything that actually renders Roblox smoothly you would need a **paid** GPU/Windows
cloud instance (e.g. Paperspace, AWS G-series, Shadow PC) — none are free and cardless.
