---
title: Papertrail Integration
tags: []
permalink: papertrail.html
summary: Learn about the Wavefront Papertrail Integration.
---
## Papertrail Integration

Papertrail provides cloud hosted log management for troubleshooting of infrastructure and application issues. It seamlessly manages logs from apps, servers, and cloud services. Monitoring Papertrail is easy with Wavefront. This integration installs and configures Telegraf to send Papertrail alerts as metrics into Wavefront. The metrics are tagged with the event name as specified in Papertrail.
Telegraf is a light-weight server process capable of collecting, processing, aggregating, and sending metrics to a [Wavefront proxy](https://docs.wavefront.com/proxies.html).


To see the metrics for this integration, select the integration from <https://github.com/influxdata/telegraf/tree/master/plugins/inputs>.
## Papertrail Setup



### Step 1. Install the Telegraf Agent

This integration uses the Webhooks input plugin for Telegraf. If you've already installed Telegraf on your server(s), you can skip to Step 2.

Run a command to install Telegraf and a Wavefront proxy in your environment. If a proxy is already running in your environment, you can select that proxy and the Telegraf install command connects with that proxy.

### Step 2. Configure Telegraf Webhooks Input Plugin

Create a file called `webhooks.conf` in `/etc/telegraf/telegraf.d` and enter the following snippet:

{% raw %}
```
# # A Webhooks Event collector
[[inputs.webhooks]]
#   ## Address and port to host Webhook listener on
  service_address = ":1619"
#
  [inputs.webhooks.papertrail]
     path = "/papertrail"

```
{% endraw %}

See the [Telegraf documentation](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/webhooks).


### Step 3. Restart Telegraf

Run `sudo service telegraf restart` to restart your agent.

### Setp 4. Configure Papertrail Webhooks Services

To capture metrics from Papertrail, choose the **Webhook** service in the Webhooks section of the Papertrail web interface.
See the [Papertrail documentation](https://help.papertrailapp.com/kb/how-it-works/web-hooks/#webhooks-operated-by-papertrail) for details on Webhook service configuration.
