# pi-cluster

My homelab: a single-node Kubernetes cluster (k3s) on a Raspberry Pi 5 with 4 GB of RAM. Everything that runs on it comes from this repository through Flux. I try to run it the way I'd want a real cluster to be run: secrets encrypted in Git, alerts on my phone, updates as pull requests I actually review, and every decision and incident written down.

## I currently run these services:
- Linkding, a bookmark manager.
- audiobookshelf, an audiobook server. Public through a tunnel.
- Grafana, an open-source analytics and visualization web application.

The platform underneath: k3s with Traefik, ServiceLB and its built-in Helm controller turned off, Flux, SOPS with age for secrets, cloudflared for public access, kube-prometheus-stack for monitoring, and Renovate for dependency updates.

## How I run it

Nothing in the cluster is installed by hand, Flux applies everything from this repo.

UptimeKuma monitors the http(s) services and alerts me through Home Assistant. It repeats while a problem lasts, and I get a message when it's been resolved.

Renovate opens a pull request for every new image or chart version. I read them before merging, and for bigger Helm chart upgrades I render the old and the new chart with my own values and compare the output first.
