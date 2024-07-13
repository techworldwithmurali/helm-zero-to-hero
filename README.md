# Helm Overview

## What is Helm?
Helm is a package manager for Kubernetes, enabling streamlined application deployment and management using charts.

## Why do we require Helm?
Helm simplifies Kubernetes deployment by packaging applications and their dependencies into charts, facilitating easy installation, upgrades, and management.

---

# Helm Usage

## Without and With Helm Chart

- **Without Helm**: Manual creation and management of Kubernetes YAML manifests for each resource.

![Without Helm Chart - Tech World with Murali - Moole Muralidhara Reddy.png](https://github.com/techworldwithmurali/helm-zero-to-hero/blob/main/Day-1/images/Day%20%201-%20Without%20Helm%20chart-%20Moole%20Muralidhara%20Reddy%20-%20Tech%20World%20with%20Murali.png)

- **With Helm Chart**: Applications are packaged into reusable Helm charts, including templates for Kubernetes manifests, values files, and metadata.

![With Helm Chart - Tech World with Murali - Moole Muralidhara Reddy.png](https://github.com/techworldwithmurali/helm-zero-to-hero/blob/main/Day-1/images/Day%20%201-%20With%20Helm%20chart-%20Moole%20Muralidhara%20Reddy%20-%20Tech%20World%20with%20Murali.png)


## Difference between Helm 2 and Helm 3
- **Helm 2**:
  - Uses Tiller (server-side component) for managing releases.
  - Centralized chart repository.
  - Initialization (`helm init`) required.
  - Security concerns related to Tiller.
  
- **Helm 3**:
  - No Tiller; client-only architecture.
  - Charts stored locally or in repositories.
  - Simplified installation and enhanced security.
  - Improved namespace isolation.

---

# Helm Chart Structure

A Helm chart consists of:

- **Chart.yaml**: Metadata about the chart.
- **Templates/**: Directory for Kubernetes manifest templates.
- **Values.yaml**: Default configuration values.
- **Charts/**: Dependency charts (if any).
- **README.md**: Documentation for the chart.

---

# Installation

#### Installing Helm 3 on Linux
#### Installing Helm 3 on Windows
