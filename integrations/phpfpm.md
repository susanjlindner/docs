---
title: PHP-FPM Integration
tags: []
permalink: phpfpm.html
summary: Learn about the Wavefront PHP-FPM Integration.
---
## PHP-FPM Integration
PHP-FPM (FastCGI Process Manager) is a PHP FastCGI implementation with features that are useful for sites of any size. This integration installs and configures Telegraf to send PHP-FPM metrics into Wavefront. Telegraf is a light-weight server process capable of collecting, processing, aggregating, and sending metrics to a [Wavefront proxy](https://docs.wavefront.com/proxies.html).

In addition to setting up the metrics flow, this integration also installs a dashboard. Here are the Overview* and Processes and Queue sections of a dashboard displaying PHP-FPM  metrics:

{% include image.md src="images/overview.png" width="80" %}


To see the metrics for this integration, select the integration from <https://github.com/influxdata/telegraf/tree/master/plugins/inputs>.
## PHP-FPM Setup



### Step 1. Install the Telegraf Agent
This integration uses the phpfpm input plugin for Telegraf. If you've already installed Telegraf on your server(s), you can skip to Step 2.

Run a command to install Telegraf and a Wavefront proxy in your environment. If a proxy is already running in your environment, you can select that proxy and the Telegraf install command connects with that proxy.

### Step 2. Configure the PHP-FPM Input Plugin

Create a `phpfpm.conf` file in `/etc/telegraf/telegraf.d` and add the following snippet:

{% raw %}
```
   [[inputs.phpfpm]]
   #   ## Plugin can be configured using http mode as below:
   #   ##   - http: the URL must start with http:// or https://, ie:
   #   ##       "http://host-ip/status"
        urls = ["http://<host-ip>/status"]
```
{% endraw %}

*** Note *** :  Multiple URLs are not supported. You must install a Telegraf agent on each PHP-FPM host.

### Step 3. Restart Telegraf

Run `sudo service telegraf restart` to restart your Telegraf agent.
