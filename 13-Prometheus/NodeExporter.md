A node exporter is a specific type of exporter that is responsible for collecting metrics on a Linux server.

## Installation

* Default metheod
```bash
wget https://github.com/prometheus/node_exporter/releases/download/v1.4.0/node_exporter-1.4.0.linux-amd64.tar.gz
tar xvf node_exporter-1.4.0.linux-amd64.tar.gz
cd node_exporter-1.4.0.linux-amd64
./node_exporter
```

* Systemd unit: We can also install node exporter as a systemd service just like we do it for prometheus.

1. Copy node exporter binary files to /usr/local/bin directory

```bash
sudo cp node_exporter /usr/local/bin
```

2. Create a user for node exporter.

```bash
sudo useradd node_exporter --no-create-home --shell /bin/false
```

3. Change permissions for node exporter executable file.

```bash
sudo chown node_exporter:node_exporter /usr/local/bin/node_exporter
```

4. Create service file

```bash
sudo vi /etc/systemd/system/node_exporter.service # For Amazon Linux
sudo vi /etc/system/systemd/node_exporter.service # For other Linux distros
```

5. Add the following content to service file

```yaml
[Unit]
Description=Node Exporter
Wants=network-online.target
After=network-online.target

[Service]
User=node_exporter
Group=node_exporter
Type=simple
ExecStart=/usr/local/bin/node_exporter

[Install]
WantedBy=multi-user.target
```
6. Reload the system daemon

```bash
sudo systemctl daemon-reload
```
7. Now, we can start and enable node exporter as a service

```bash
sudo systemctl start node_exporter
sudo systemctl enable node_exporter
 ```

## To verify `whether node exporter is working

```bash
curl localhost:9100/metrics #open in a new terminal
```

