---
title: Google Cloud Platform Integration
tags: []
permalink: gcp.html
summary: Learn about the Wavefront Google Cloud Platform Integration.
---
## Google Cloud Platform Integration

The Google Cloud Platform integration is full-featured native integration offering agentless data ingestion of GCP metric
data, as well as pre-defined dashboards and alert conditions for certain GCP services.

### Metrics Configuration

Wavefront ingests Google Cloud Platform metrics using the v3 Stackdriver Monitoring APIs.  For details on the metrics, see the
 [metrics documentation](https://cloud.google.com/monitoring/api/metrics).

Metrics originating from Google Cloud Platform are prefixed with `gcp.` within Wavefront.  Once the integration has
been set up, you can browse the available GCP metrics in the [metrics browser](/metrics#%28q%3Agcp.%2Cs%3A!f%29).

### Dashboards

<p>Wavefront provides Google Cloud Platform dashboards for the following the services:</p>

<table width="100%" style="max-width: 650px; margin-bottom: 20px;">
<tbody>
<tr>
<td style="text-align:center;vertical-align:top;">
<h5>Google Compute Engine</h5>
<div><img src="images/gce.svg" alt="Google GCE" style="max-width: 70px;"/></div>
</td>
<td style="text-align:center;vertical-align:top;">
<h5>Google Container Engine</h5>
<div><img src="images/gke.svg" alt="Google GKE" style="max-width: 70px;"/></div>
</td>
<td style="text-align:center;vertical-align:top;">
<h5>Google App Engine</h5>
<div><img src="images/app-engine.svg" alt="Google APP" style="max-width: 70px;"/></div>
</td>
<td style="text-align:center;vertical-align:top;">
<h5>Google Cloud Datastore</h5>
<div><img src="images/datastore.svg" alt="Google Cloud Datastore" style="max-width: 70px;"/></div>
</td>
</tr>
</tbody>
</table>

### Alerts

The Google Cloud Platform integration dashboard contains predefined alert conditions. These conditions are embedded as queries in the dashboard's charts. For example:

{% include image.md src="images/alert_condition.png" width="50" %}

To create the alert, click the **Create Alert** link under the query and configure the [alert properties](https://docs.wavefront.com/alerts_managing.html#creating-an-alert) (notification targets, condition checking frequency, etc.).







## Google Cloud Platform Integration



### Adding a GCP Integration

Adding a Google Cloud Platform (GCP) integration requires establishing a trust relationship between GCP and Wavefront. You do that by creating a service account, giving that account viewer privileges, and downloading a JSON key. Follow the instructions on the left. 


