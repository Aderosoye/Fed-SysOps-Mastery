# BookStack linking plan

Preserve the existing shelves and books documented in project memory:

- `01 Infrastructure`
- `03 Docker`
- `04 Monitoring`

Within the existing `04 Monitoring` book structure, link to this repository from the current Monitoring Overview and the existing Prometheus, Grafana, Node Exporter, and Monitoring Architecture pages. Add Uptime Kuma and Alertmanager content within the existing monitoring organization rather than creating a parallel shelf hierarchy. Keep BookStack as the readable operational knowledge base and this Git repository as the reviewed, versioned source for sanitized examples and change history.

Suggested cross-links:

| Existing BookStack page | Repository page to link |
|---|---|
| Monitoring Overview | README and architecture overview |
| Node Exporter | Evidence register and troubleshooting runbook |
| Prometheus | Prometheus example and troubleshooting runbook |
| Grafana | Architecture overview and routine checklist |
| Monitoring Architecture | Architecture overview |
| Docker | Uptime Kuma notes in deployment/troubleshooting |

Do not copy secrets, private IP addresses, tokens, recovery codes, or database contents into either location.
