# Routine maintenance checklist

These are proposed operating habits, not records of completed maintenance.

## Daily or each study session

- Check that the expected services and containers are running.
- Review Prometheus targets for scrape failures.
- Look at Grafana dashboards for missing data or unexpected host resource use.
- Review Kuma incident history and Prometheus/Alertmanager alerts if configured.

## Weekly

- Check VM disk space and recent service logs.
- Review backup completion for application configuration and persistent data.
- Confirm BookStack notes still match the live setup after changes.

## Monthly and before upgrades

- Record package and image versions; review upstream release/security notes.
- Test restoration of one backup in a safe location where practical.
- Review exposed ports, accounts, notification routes, and retention settings.
- Update this repository changelog and the existing BookStack pages.

## Command reference

```bash
df -h
```
Description: Checks filesystem capacity in human-readable units.

```bash
systemctl --failed
```
Description: Lists systemd units currently in a failed state.

```bash
journalctl -u prometheus -u grafana-server --since '24 hours ago' --no-pager
```
Description: Reviews the last day of logs for the two named services.

```bash
docker logs --since 24h uptime-kuma
```
Description: Shows recent Uptime Kuma container logs; review before sharing for sensitive values.
