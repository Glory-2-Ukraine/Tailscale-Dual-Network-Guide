# How to Connect One Machine to Two Tailscale Networks at the Same Time

A beginner-friendly, step-by-step guide for running two separate Tailscale instances on one Linux machine using two `systemd` services.

## What's in this repo

| File | Description |
|------|-------------|
| `Tailscale-Dual-Network-Guide-EN.docx` | Full guide in English |
| `Tailscale-Dual-Network-Guide-UA.docx` | Full guide in Ukrainian |

## What this guide covers

- Creating a second Tailscale state directory
- Writing a second `tailscaled2.service` systemd unit
- Using `--tun=userspace-networking` and `--port=41642` to avoid conflicts
- Authenticating to the second tailnet
- Verifying both networks work
- Command reference table
- Troubleshooting common errors
- How to cleanly remove the second instance

## Quick reference

```bash
# Check second network status
tailscale --socket=/run/tailscale2/tailscaled.sock status

# Restart second service
sudo systemctl restart tailscaled2

# View second service logs
sudo journalctl -u tailscaled2 -f
```

---
*Part of the [Glory-2-Ukraine](https://github.com/Glory-2-Ukraine) infrastructure toolkit.*
