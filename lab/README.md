# PALAMEDES Linux Lab

Choose the execution environment based on the behavior under investigation:

- Portable shell and text-processing exercises may run locally.
- Linux-specific behavior must be tested on real Linux.
- Docker is suitable when container or isolation behavior is enough.
- Use a Linux VM or equivalent when host-level behavior matters—for example `systemd`, `/proc`, routing, interfaces, cgroups, host logs, or host services.

Do not verbally simulate failures that can reasonably be reproduced in a suitable lab. Keep experiments isolated and out of production. This directory is guidance only; no lab framework or environment is provisioned yet. See `METHODOLOGY.md` for how environment choice fits exercise design.
