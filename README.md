# Akri (akri)
Akri is a CNCF Sandbox project that exposes heterogeneous leaf devices (such as IP cameras and USB devices) as resources in a Kubernetes cluster. It enables dynamic discovery and utilization of IoT edge devices through protocol-specific Discovery Handlers for ONVIF, OPC UA, and udev, with automatic workload scheduling and high availability.

**URL:** [https://docs.akri.sh/](https://docs.akri.sh/)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Device Management, Edge Computing, IoT, Kubernetes, CNCF, Open Source, OPC UA, ONVIF, udev

## Timestamps

- **Created:** 2025-01-01
- **Modified:** 2026-04-19

## APIs

### Akri Metrics API
Akri exposes Prometheus metrics on port 8080 at /metrics for the Agent, Controller, and broker pods. Metrics include instance count, discovery response results and latency, and broker pod count. Supports Prometheus Operator ServiceMonitor for metric scraping.

**Human URL:** [https://docs.akri.sh/](https://docs.akri.sh/)

#### Tags:

 - Monitoring, Prometheus, Metrics, Observability

#### Properties

- [Documentation](https://docs.akri.sh/)
- [GitHubRepository](https://github.com/project-akri/akri)
- [OpenAPI](openapi/akri-metrics-openapi.yaml)
- [JSONSchema](json-schema/akri-prometheus-metrics-schema.json)
- [JSONSchema](json-schema/akri-akri-instance-count-schema.json)
- [JSONSchema](json-schema/akri-akri-discovery-response-result-schema.json)
- [JSONSchema](json-schema/akri-akri-discovery-response-time-schema.json)
- [JSONSchema](json-schema/akri-akri-broker-pod-count-schema.json)
- [JSONSchema](json-schema/akri-akri-configuration-schema.json)
- [JSONSchema](json-schema/akri-akri-instance-schema.json)

## Common Properties

- [GitHubOrganization](https://github.com/project-akri)
- [GitHubRepository](https://github.com/project-akri/akri)
- [Documentation](https://docs.akri.sh/)
- [GettingStarted](https://docs.akri.sh/user-guide/getting-started)
- [ChangeLog](https://github.com/project-akri/akri/blob/main/CHANGELOG.md)
- [SDK - Helm Chart](https://artifacthub.io/packages/helm/akri-helm-charts/akri)
- [CodeExamples - Example Brokers and Applications](https://github.com/project-akri/examples)
- [SDK - Discovery Handler Template (Rust)](https://github.com/project-akri/akri-discovery-handler-template)

## Features

| Name | Description |
|------|-------------|
| Dynamic Device Discovery | Automatically discovers heterogeneous leaf devices (IP cameras, USB devices, industrial sensors) across Kubernetes cluster nodes using protocol-specific Discovery Handlers. |
| ONVIF Discovery Handler | Discovers IP cameras via ONVIF standards and RTSP streams, with filtering by IP address, MAC address, ONVIF scopes, and device UUIDs. |
| OPC UA Discovery Handler | Discovers industrial automation servers and Local Discovery Servers via OPC UA protocol, supporting x509 certificate authentication for secure connections. |
| udev Discovery Handler | Discovers locally attached hardware (USB devices, cameras, microphones) on Linux nodes using udev rules with kernel device name and capability filtering. |
| Automatic Workload Scheduling | Automatically schedules broker Pods or Jobs per discovered device based on Akri Configuration specifications, managing the full workload lifecycle. |
| High Availability | Multiple nodes can access a single leaf device, ensuring service continuity if a node fails. Supports multi-node device reservation. |
| Kubernetes Custom Resources | Two CRDs: configurations.akri.sh for discovery specification and instances.akri.sh representing each discovered device as a Kubernetes resource. |
| Extensible Discovery Handler Framework | Community can implement custom Discovery Handlers as DaemonSets using the akri-discovery-handler-template, enabling support for any device protocol. |
| Prometheus Metrics | Built-in Prometheus metrics on port 8080 for instance count, discovery response results, discovery latency, and broker pod count, with Grafana visualization support. |
| Multi-Architecture Support | Supports Linux nodes on amd64, arm64v8, and arm32v7 architectures with Kubernetes v1.16+, K3s, and MicroK8s distributions. |

## Use Cases

| Name | Description |
|------|-------------|
| Edge IoT Device Management | Expose and manage IoT leaf devices such as IP cameras and USB sensors as first-class Kubernetes resources for edge computing workloads. |
| Industrial Automation Integration | Connect industrial OPC UA servers and automation equipment to Kubernetes clusters for real-time monitoring and control workflows. |
| Computer Vision at the Edge | Deploy ONVIF-compliant IP camera brokers automatically as cameras are discovered, enabling distributed computer vision processing. |
| Dynamic Hardware Resource Scheduling | Automatically schedule GPU, FPGA, or specialized hardware workloads based on real-time device availability across cluster nodes. |
| Heterogeneous Device Fleet Management | Manage fleets of diverse edge devices with different protocols from a single Kubernetes control plane using unified Configuration resources. |

## Integrations

| Name | Description |
|------|-------------|
| Prometheus | Native Prometheus metrics integration via ServiceMonitor and PodMonitor custom resources, with Grafana visualization support. |
| Helm | Official Helm chart packaging for deploying Akri Controller, Agent DaemonSet, and Discovery Handler DaemonSets. |
| Kubernetes Device Plugin Framework | Extends the Kubernetes Device Plugin Framework with edge-specific capabilities for heterogeneous leaf device management. |
| ONVIF | Built-in ONVIF protocol support for discovering and managing standards-compliant IP cameras and video devices. |
| OPC UA | Built-in OPC UA protocol support for industrial automation device discovery with certificate-based security. |
| Linux udev | Built-in udev integration for discovering locally attached hardware devices on Linux Kubernetes nodes. |
| CNCF Ecosystem | CNCF Sandbox project integrating with cloud native tooling including K3s, MicroK8s, and standard Kubernetes distributions. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Akri Metrics API](openapi/akri-metrics-openapi.yaml)

### JSON Schema

- [akri-prometheus-metrics-schema.json](json-schema/akri-prometheus-metrics-schema.json)
- [akri-akri-instance-count-schema.json](json-schema/akri-akri-instance-count-schema.json)
- [akri-akri-discovery-response-result-schema.json](json-schema/akri-akri-discovery-response-result-schema.json)
- [akri-akri-discovery-response-time-schema.json](json-schema/akri-akri-discovery-response-time-schema.json)
- [akri-akri-broker-pod-count-schema.json](json-schema/akri-akri-broker-pod-count-schema.json)
- [akri-akri-configuration-schema.json](json-schema/akri-akri-configuration-schema.json)
- [akri-akri-instance-schema.json](json-schema/akri-akri-instance-schema.json)

### JSON Structure

- [akri-prometheus-metrics-structure.json](json-structure/akri-prometheus-metrics-structure.json)
- [akri-akri-instance-count-structure.json](json-structure/akri-akri-instance-count-structure.json)
- [akri-akri-discovery-response-result-structure.json](json-structure/akri-akri-discovery-response-result-structure.json)
- [akri-akri-discovery-response-time-structure.json](json-structure/akri-akri-discovery-response-time-structure.json)
- [akri-akri-broker-pod-count-structure.json](json-structure/akri-akri-broker-pod-count-structure.json)
- [akri-akri-configuration-structure.json](json-structure/akri-akri-configuration-structure.json)
- [akri-akri-instance-structure.json](json-structure/akri-akri-instance-structure.json)

### JSON-LD

- [akri-akri-context.jsonld](json-ld/akri-akri-context.jsonld)

### Examples

- [akri-prometheus-metrics-example.json](examples/akri-prometheus-metrics-example.json)
- [akri-akri-instance-count-example.json](examples/akri-akri-instance-count-example.json)
- [akri-akri-discovery-response-result-example.json](examples/akri-akri-discovery-response-result-example.json)
- [akri-akri-discovery-response-time-example.json](examples/akri-akri-discovery-response-time-example.json)
- [akri-akri-broker-pod-count-example.json](examples/akri-akri-broker-pod-count-example.json)
- [akri-akri-configuration-example.json](examples/akri-akri-configuration-example.json)
- [akri-akri-instance-example.json](examples/akri-akri-instance-example.json)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [Akri Metrics API](capabilities/shared/metrics.yaml) — 1 operation for Prometheus metrics monitoring

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Edge Device Monitoring](capabilities/edge-device-monitoring.yaml) | akri-metrics | 1 | Edge Computing Operator |

## Vocabulary

- [Akri Vocabulary](vocabulary/akri-vocabulary.yaml) — Unified taxonomy mapping 4 resources, 6 actions, 1 workflow, and 1 persona across operational (OpenAPI) and capability (Naftiko) dimensions

## Rules

- [Akri Spectral Rules](rules/akri-spectral-rules.yml) — 25 rules across 9 categories enforcing Akri API conventions

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
