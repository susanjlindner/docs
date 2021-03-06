---
title: ZooKeeper Integration
tags: []
permalink: zookeeper.html
summary: Learn about the Wavefront ZooKeeper Integration.
---
## ZooKeeper Integration

ZooKeeper is a centralized service for maintaining configuration information, providing distributed synchronization and providing group services.
This integration installs and configures Telegraf to send ZooKeeper server metrics into Wavefront. Telegraf is a light-weight server process capable of collecting, processing, aggregating, and sending metrics to a [Wavefront proxy](https://docs.wavefront.com/proxies.html).

In addition to setting up the metrics flow, this integration also installs a dashboard. Here's a preview of some charts in the ZooKeeper dashboard.

{% include image.md src="images/zookeeper.png" width="80" %}


To see the metrics for this integration, select the integration from <https://github.com/influxdata/telegraf/tree/master/plugins/inputs>.
## ZooKeeper Setup



### Step 1. Install the Telegraf Agent

This integration uses the ZooKeeper input plugin for Telegraf to extract metrics from ZooKeeper.

Run a command to install Telegraf and a Wavefront proxy in your environment. If a proxy is already running in your environment, you can select that proxy and the Telegraf install command connects with that proxy.

### Step 2. Enable the ZooKeeper input plugin

Create a file called `zookeeper.conf` in `/etc/telegraf/telegraf.d` and enter the following snippet:
{% raw %}
   ```
	# # Reads `mntr` stats from one or many zookeeper servers
	[[inputs.zookeeper]]
	#   ## An array of addresses to gather stats about. Specify an IP or hostname
	#   ## with port e.g. localhost:2181, 10.0.0.1:2181, etc.
	#
	#   ## If no servers are specified, then localhost is used as the host.
	#   ## If no port is specified, 2181 is used
	  servers = [":2181"]
	  fielddrop = ["version"]
   ```
{% endraw %}

### Step 3. Restart Telegraf

Run `sudo service telegraf restart` to restart your Telegraf agent.
