# Akri (akri)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
