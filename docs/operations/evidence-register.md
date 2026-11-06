# Evidence register

## Historical facts recorded in project memory

| Item | Recorded evidence | Confidence / limitation |
|---|---|---|
| Host OS | Ubuntu VM | Distribution release and current identity unknown. |
| Prometheus | v3.15.0; self and Node Exporter scrape targets; 15-second interval | Historical deployment/configuration record, not current version check. |
| Node Exporter | v1.12.1; systemd unit name `prometheus-node-exporter`; port 9100 | Confirm unit name and package/source on the VM. |
| Grafana | systemd service; Prometheus URL `http://localhost:9090`; documented port 3000 | Grafana version and saved dashboard data not verified. |
| Uptime Kuma | Docker deployment; container name `uptime-kuma`; documented port 3001 | Image tag, Compose file, volumes and current state unknown. |
| Alertmanager | Deployment work recorded; documented port 9093 | Configuration/receiver pipeline needs verification. |
| BookStack | Deployed with MariaDB | Versions, unit/container, paths and ports unknown. |
| VM health | No present live inspection evidence | Do not describe any component as currently healthy. |

## Not evidenced as implemented in this VM

Blackbox Exporter, Loki, automated Proxmox discovery, dynamic file service discovery, production SNMP/LibreNMS services, and any company-wide centralized monitoring architecture. These appear in separate reference/target materials only.

## Verification log

Add dated rows after checking the VM. Use sanitized host labels and omit sensitive IPs.

| Date | Check | Result | Evidence location | Operator |
|---|---|---|---|---|
| TBD | Initial live audit | Pending | — | — |
