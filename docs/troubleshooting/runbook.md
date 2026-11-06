# Troubleshooting runbook

Use one symptom at a time. Capture timestamps and sanitized evidence, then update the evidence register after resolution.

## Prometheus target is down

1. Check the target's `9100` endpoint from the Prometheus host and confirm the address/port against the live configuration.
2. Check Node Exporter service state and recent logs.
3. Check local firewall rules and routing before changing scrape configuration.
4. Confirm the target recovers in Prometheus before closing the incident.

```bash
systemctl status prometheus-node-exporter --no-pager
```
Description: Checks the recorded Node Exporter systemd unit.

```bash
journalctl -u prometheus-node-exporter --since '1 hour ago' --no-pager
```
Description: Displays recent Node Exporter service logs.

## Grafana shows no Prometheus data

1. Confirm Prometheus is running and targets are healthy.
2. Test the Grafana data source URL recorded as `http://localhost:9090` from the Grafana host.
3. Check Grafana's data-source health and time range; verify the queried metric exists.
4. Inspect Grafana logs before changing dashboards.

## Uptime Kuma unavailable

1. Confirm the container exists and review its status.
2. Review logs and confirm persistent volume mapping before recreating it.
3. Check the host's actual port mapping; `3001` is only the documented value.
4. Do not remove the container or its data volume during diagnosis.

## Alert notifications not received

1. Confirm Prometheus has a firing alert.
2. Check Prometheus-to-Alertmanager connectivity and Alertmanager status.
3. Verify a receiver is configured, credentials are supplied outside Git, and notification delivery logs show a result.
4. Send a controlled test notification only after confirming the receiver and intended recipient.

## BookStack unavailable

The available records do not identify the BookStack installation method, service name, URL, or port. First identify its live service/container and MariaDB dependency, then consult the existing BookStack procedure. Avoid guessed restart commands or data-directory changes.

## Command reference

```bash
journalctl -u prometheus -u grafana-server --since '1 hour ago' --no-pager
```
Description: Reads recent Prometheus and Grafana service logs.

```bash
docker ps -a --filter name=uptime-kuma
```
Description: Shows the Uptime Kuma container including stopped state.
