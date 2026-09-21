# Observe Monitor

Small local monitoring stack using Prometheus, Grafana, and Node Exporter.

## Start

```bash
docker compose up -d
```

Open:

- Prometheus: http://localhost:9090
- Grafana: http://localhost:3000
- Node Exporter metrics: http://localhost:9100/metrics

Prometheus scrapes Node Exporter every 15 seconds and loads the rules in
`alert_rules.yml`.

## Check

```bash
docker compose ps
docker compose exec -T prometheus promtool check rules /etc/prometheus/alert_rules.yml
```

## Stop

```bash
docker compose down
```
