My homelab: a single-node Kubernetes cluster (k3s) on a Raspberry Pi 5 with 4 GB of RAM.
Everything that runs on it comes from this repository through Flux.
I try to run it the way I'd want a real cluster to be run: secrets encrypted in Git, alerts (currently via UptimeKuma through Home Assistant) on my phone, updates as pull requests I actually review, and every decision and incident written down.

I currently run these services:
- Linkding, a bookmark manager.
- audiobookshelf, an audiobook server. Public through a tunnel.
- Grafana, an open-source analytics and visualization web application.
