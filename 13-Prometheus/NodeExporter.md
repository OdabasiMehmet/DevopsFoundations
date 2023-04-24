A node exporter is a specific type of exporter that is responsible for collecting metrics on a Linux server.

## Installation

```bash
wget https://github.com/prometheus/node_exporter/releases/download/v1.4.0/node_exporter-1.4.0.linux-amd64.tar.gz
tar xvf node_exporter-1.4.0.linux-amd64.tar.gz
cd node_exporter-1.4.0.linux-amd64
./node_exporter
```

## To verify `whether node exporter is working

```bash
curl localhost:9100/metrics
```