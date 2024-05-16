# prometheus-grafana-docker-example
Example project showing how to run Prometheus & Grafana locally in Docker containers.


### Getting started
Clone the repo:
```bash
git clone git@github.com:DaveLlewellynMoJ/prometheus-grafana-docker-example.git
```

Update `prometheus/prometheus.yml` to work with your application:

```yaml
scrape_configs:
  - job_name: '<YOUR APPLICATION NAME>'
    metrics_path: '<PATH OF YOUR METRICS ENDPOINT>'
    scrape_interval: 3s
    static_configs:
      - targets: ['host.docker.internal:<YOUR APPLICATION PORT>']
        labels:
          application: 'My Spring Boot Application'
```
From project root dir:
```
docker compose up
```
Assuming everything has started successfully:
- Access the Prometheus UI at http://localhost:9090
- Access Grafana UI at http://localhost:3000

The default Grafana username/password is `admin`/`admin`. Visit the 
[Grafana marketplace](https://grafana.com/grafana/dashboards/) to view/install dashboards suitable for you needs
