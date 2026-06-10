# fortigate-prometheus-exporter

[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/fortigate-prometheus-exporter)](https://artifacthub.io/packages/search?repo=fortigate-prometheus-exporter)

![Version: 0.3.1](https://img.shields.io/badge/Version-0.3.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.25.0](https://img.shields.io/badge/AppVersion-1.25.0-informational?style=flat-square)

Helm chart for prometheus-community/fortigate_exporter

## Installation

Run the following command to deploy the exporter:

```bash
helm install my-fortigate-prometheus-exporter oci://ghcr.io/claudsonm/fortigate-prometheus-exporter --version 0.3.1
```

**Homepage:** <https://github.com/claudsonm/fortigate-prometheus-exporter-helm>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| claudsonm |  | <https://github.com/claudsonm> |

## Source Code

* <https://github.com/claudsonm/fortigate-prometheus-exporter-helm>
* <https://github.com/prometheus-community/fortigate_exporter>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| auth.existingSecret | string | `""` | Name of an existing Kubernetes Secret containing the API token. |
| auth.secretKey | string | `"token"` | The key inside the existing Secret that holds the token string. |
| config.insecureSkipVerify | bool | `false` | Skips TLS verification for the exporter's target map generation. |
| config.probes | object | `{}` | List of endpoints to explicitly include or exclude from scraping. |
| config.targetUrl | string | `""` | The FortiGate API URL used to generate the internal authentication map. |
| exporter.httpsTimeout | int | `10` | Timeout in seconds for the establishment of HTTPS connections. |
| exporter.insecure | bool | `false` | Allows the exporter binary to turn off TLS validation globally. |
| exporter.maxBgpPaths | int | `10000` | Maximum amount of BGP paths to fetch per IP stack version. |
| exporter.maxVpnUsers | int | `0` | Maximum amount of VPN users to fetch (0 means no limit). |
| exporter.scrapeTimeout | int | `30` | Timeout in seconds for the exporter to fetch data from FortiGate. |
| extraObjects | list | `[]` | Array of extra Kubernetes manifests to deploy alongside the chart. |
| hostAliases | list | `[]` | Custom DNS entries to inject into the pod's /etc/hosts file. |
| image.pullPolicy | string | `"IfNotPresent"` | The image pull policy. |
| image.repository | string | `"quay.io/prometheuscommunity/fortigate-exporter"` | The image repository to pull from. |
| image.tag | string | `"v1.25.0"` | Overrides the image tag. |
| nodeSelector | object | `{}` | Node labels for pod assignment. |
| podLabels | object | `{}` | Additional custom labels to add to the exporter pods. |
| replicaCount | int | `1` | Number of exporter pod replicas. Scale up if scraping many targets simultaneously. |
| resources | object | `{"limits":{"cpu":"200m","memory":"256Mi"},"requests":{"cpu":"50m","memory":"64Mi"}}` | CPU and memory requests and limits for the exporter container. |
| service.enabled | bool | `false` | Creates a Kubernetes Service to expose the exporter metrics port. |
| service.port | int | `9710` | The port the Service will route traffic through. |
| service.type | string | `"ClusterIP"` | The type of Kubernetes Service to create. |
| serviceMonitor.enabled | bool | `false` | Creates a Prometheus Operator ServiceMonitor object. |
| serviceMonitor.interval | string | `"30s"` | The interval at which Prometheus will scrape the exporter. |
| serviceMonitor.labels | object | `{}` | Custom labels to add to the ServiceMonitor to ensure discovery by Prometheus. |
| serviceMonitor.scrapeTimeout | string | `"10s"` | The timeout applied to the Prometheus scrape request. |
| serviceMonitor.targetUrl | string | `""` | The FortiGate API URL passed as a parameter during the Prometheus scrape phase. |
| tolerations | list | `[]` | Tolerations for pod assignment. |
