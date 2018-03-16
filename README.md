# prom-stack
A Monitoring utility for analysing docker stack


#### Pre-requisites:
 * Docker Engine >= 1.13
 * Docker Compose >= 1.11

#### Containers:
 * Prometheus (metrics database) http://<host-ip>:9090
 * AlertManager (alerts management) http://<host-ip>:9093
 * Grafana (visualize metrics) http://<host-ip>:3000
 * NodeExporter (host metrics collector)
 * cAdvisor (containers metrics collector)

#### Setup
 * Prometheus :
    * Update the configuration in `prometheus/prometheus.yml`
    * Prometheus will scrape all the metrics using exporters(`cAdvisor/node-exporter`) from the hosts mentioned in the configuration file.
 * AlertManager :
    * Update the alertmanager configuration in `alertmanager/config.yml`
    * add alert rules in `prometheus/alert.rules`.
 * Grafana :
    * You can configure your dashboards in grafana. It will give you graphical representation of all the metrics collected by prometheus.
## How to run
```ADMIN_USER=admin ADMIN_PASSWORD=admin docker-compose up -d```
