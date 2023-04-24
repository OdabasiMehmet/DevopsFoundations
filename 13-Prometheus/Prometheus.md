## Prometheus Overview
* When we have any type of application or a service, it is an essential practice to monitor the service in order to spot and prevent problems that would lead to service downtime. Furthermore, we would want to see how well our application or service performs. One of the most common monitoring tools that is widely used among engineers is Prometheus.

* Prometheus is an open-source monitoring tool that collects numeric metrics and saves them as time series data in order to monitor your infrastructure. Prometheus collects metrics by scraping targets who expose metrics through an HTTP endpoint. 

* Some examples of the metrics are, CPU/Memorry utilization, disk space, service uptime, and application specific metrics, such as latency.

* Prometheus is written in GoLang and it uses PromQI as the query language.

* Prometheus works as a pull system. The targets do not send data. Prometheus pulls the data.

## Installation

1. Go to https://prometheus.io/download/ to obtain the download link for Prometheus

2. Use wget to download prometheus using the link above

```bash
wget https://github.com/prometheus/prometheus/releases/download/v2.41.0/prometheus-2.41.0.linux-amd64.tar.gz

```
3. Untar prometheus, cd into the directory and start prometheus.

```bash
tar xvf prometheus-2.41.0.linux-amd64.tar.gz
cd prometheus-2.41.0.linux-amd64/
./prometheus
```

4. By keeping the terminal window running, go to a browser and access Ip followed by port 9090

```bash
http://localhost:9090
# OR
http://PUBLICIP:9090
```
5. If you are using a cloud service like Google Cloud or AWS, you need to provide permissions for port 9090. You can do it by editing inbound rules for AWS and adding TCP 9090 from anywhere 0.0.0.0/0.

# Using systemd to start prometheus
When you install and start Prometheus, it runs in the foreground. If we close the terminal it stops working. Also, it does not start once we boot up the instance. We have to manually start the executable file with `./prometheus` command. However, we can overcome this issue by starting prometheus as a service as we start many other services in Linux by using `systemctl` command.

```bash
sudo useradd prometheus — no-create-home — shell /bin/false
sudo mkdir /etc/prometheus #for configuration file
sudo mkdir /var/lib/prometheus #to store data
sudo chown prometheus:prometheus /etc/prometheus 
sudo chown prometheus:prometheus /var/lib/prometheus
wget https://github.com/prometheus/prometheus/releases/download/v2.41.0/prometheus-2.41.0.linux-amd64.tar.gz
tar xvf prometheus-2.41.0.linux-amd64.tar.gz
cd prometheus-2.41.0.linux-amd64/
sudo cp prometheus /usr/local/bin # Be sure that you are in the prometheus-2.41.0.linux-amd64 directory
sudo cp promtool /usr/local/bin
sudo chown prometheus:prometheus /usr/local/bin/prometheus
sudo chown prometheus:prometheus /usr/local/bin/promtool
sudo cp -r consoles /etc/prometheus # for dashboard
sudo cp -r console_libraries /etc/prometheus
sudo chown -R prometheus:prometheus /etc/prometheus/consoles
sudo chown -R prometheus:prometheus /etc/prometheus/console_libraries
sudo cp prometheus.yml /etc/prometheus/prometheus.yml
sudo chown prometheus:prometheus /etc/prometheus/prometheus.yml
sudo vi /etc/systemd/system/prometheus.service # Enter the contents below

[Unit]
Description=Prometheus
Wants=network-online.target #this ensures the service is up only if the network is up
After=network-online.target # because if no network, no need to have prometheus work

[Service]
User=prometheus
Group=prometheus
Type=simple
ExecStart=/usr/local/bin/prometheus \
    --config.file /etc/prometheus/prometheus.yml \
    --storage.tsdb.path /var/lib/prometheus \
    --web.console.templates=/etc/prometheus/consoled \
    --web.console.libraries=/etc/prometheus/console_libraries

[Install]
WantedBy=multi-user.target #start service as part of normal system start up


:wq to save and exit
sudo systemctl daemon-reload
sudo systemctl start prometheus
sudo systemctl enable prometheus
