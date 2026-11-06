# Architecture overview

## Scope and confidence

This page describes the personal Ubuntu VM lab from the available project memory. The memory records deployment milestones, but no live shell access, configuration archive, or current health evidence was supplied. Read every component as historically recorded until the evidence register is updated.

## Recorded flow

1. Node Exporter exposes host metrics on the documented port `9100`.
2. Prometheus is recorded as scraping itself and Node Exporter every 15 seconds.
3. Grafana queries Prometheus through `http://localhost:9090` and serves dashboards on the documented port `3000`.
4. Alertmanager is recorded as part of the deployment, but its Prometheus integration and notification delivery are not verified.
5. Uptime Kuma provides availability monitoring and is recorded as a Docker deployment on `3001`.
6. BookStack with MariaDB provides operational documentation; its paths and ports are unknown.

## Component boundary

The company CloudOps target architecture describes centralized Proxmox discovery, Blackbox Exporter, Loki and shared monitoring. Those are organizational design goals and are not evidence of deployment on this lab VM. Keep them out of the current-state diagram until verified on the actual host.

## Network and access

No VM address, DNS name, firewall policy, TLS configuration, reverse proxy, external exposure, or authentication configuration is recorded here. Do not publish or infer these values. Record only sanitized labels in this repository.
