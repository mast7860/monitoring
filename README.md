# Grafana Prometheus Setup

This is a local setup to try locally inside docker containers

Prometheus is a time series database, making use of exporters to monitor various servers/services while Grafana is one of the most popular monitoring tools. When combined with Prometheus, Grafana offers powerful visualization tool for time series data.

## Grafana

The setup contains grafana folder, which have 2 files

- grafana.ini

  - copy of https://github.com/grafana/grafana/blob/master/conf/defaults.ini
  - contains default config , can be altered as per needs

- datasource.yml
  - contains details of sources from where grafana gets data (pre configured prometheus)

Can be accessed via http://localhost:3000 ( admin:admin)

## Prometheus

The setup contains promethus folder, which have 1 file

- prometheus.yml
  - contains scraping config from where promethues gets metrics

Can be acessed via http://localhost:9090/

### Note

These files are loaded as volumes in docker compose

check the file path as per your system n update accordingly

The data is lost once the containers are taken down.

In this example , prometheus is scraping logs from https://github.com/mast7860/user-feedback

check the port of the service and update the prometheus config
static_configs: - targets: ["host.docker.internal:8080"]

### References

https://grafana.com

https://prometheus.io
