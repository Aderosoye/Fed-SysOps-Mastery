# Deployment and change procedure

## Current-state limitations

Project memory records the Ubuntu platform, systemd-managed Prometheus/Grafana/Node Exporter, Docker-based Uptime Kuma, and BookStack with MariaDB. It does not include exact installation commands, full service unit files, container compose file, BookStack URL/ports, data paths, or a verified configuration export. Therefore this repository intentionally provides no deploy-ready full stack manifest.

## Before making a VM change

1. Capture current service status, package/container versions, listening sockets, and configuration file paths.
2. Back up each affected configuration and persistent application data using the application's supported method.
3. Compare the live file with the corresponding sanitized example; never overwrite blindly.
4. Validate syntax with the installed application's own validator.
5. Apply one change at a time and check service logs and application behavior.
6. Record the change, outcome, and rollback steps in BookStack and the repository changelog.

## Command reference

Commands are examples to run on the Ubuntu VM. Review output for sensitive data before sharing it.

```bash
systemctl status prometheus prometheus-node-exporter grafana-server --no-pager
```
Description: Checks the recorded systemd services and their recent state.

```bash
systemctl cat prometheus
```
Description: Shows the effective Prometheus unit and any overrides.

```bash
docker ps --format 'table {{.Names}}\t{{.Image}}\t{{.Status}}\t{{.Ports}}'
```
Description: Lists running containers without printing environment variables.

```bash
sudo ss -lntup
```
Description: Lists listening TCP/UDP sockets and owning processes.

Do not paste unredacted command output into issues or public repositories; it may reveal hostnames, addresses, or process arguments.
