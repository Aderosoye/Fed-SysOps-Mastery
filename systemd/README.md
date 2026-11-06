# systemd service references

Project memory records Prometheus, Grafana, and Node Exporter as systemd-managed services. It does not include the actual unit contents, overrides, users, flags, or filesystem paths. No reconstructed unit files are provided because guessed units can misrepresent security settings or break the host.

Collect sanitized unit evidence on the VM with `systemctl cat <unit>`.

Description: Prints the effective unit configuration; redact private paths, arguments, and credentials before recording it.

Recorded unit names to confirm: `prometheus`, `prometheus-node-exporter`, and the Grafana service (often `grafana-server`, but confirm before use).
