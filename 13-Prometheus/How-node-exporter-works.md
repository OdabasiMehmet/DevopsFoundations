Node exporters are installed on Linux operated nodes. Once they are installed, they start collecting metrics from the nodes they are installed on. On the other hand, prometheus is installed on a server, where we will be gathering metrics from nodes of ineterest.

In other words, we will need a server on which Prometheus will be working. But how will Prometheus know which nodes have node exporters and will be sending metrics to Prometheus?

Prometheus gets that information from the prometheus.yml file under /etc folder which is actually the configuration file of prometheus. Under jobs section, we need to add the IP addresses of the nodes that have node exporter installed. By this way, prometheus will know which nodes to contact and pull the metrics.